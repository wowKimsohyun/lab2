# lab2package lambaitaplab2.com;

public class Student {
	private	String name;
	private	String id;
	private	String group;
	private	String email;
	
	public Student(){
		this.name = "Student";
		this.id = "000";
		this.group = "INT22041";
		this.email = "uet@vnu.edu.vn";
	}
	public Student(String tenSV, String maSV, String nEmail){
		this.name = tenSV;
		this.id = maSV;
		this.group = "INT22041";
		this.email = nEmail;
	}
	public Student (Student s){
		this.name = s.getName();
		this.id = s.getID();
		this.group = s.getGroup();
		this.email = s.getEmail();
	}
	public String getName(){
		return name;
	}
	public void setName(String tenSV){
		this.name= tenSV;
	}
	public String getID(){
		return id;
	}
	public void setID(String maSV){
		this.id = maSV;
	}
	public String getGroup(){
		return group;
	}
	public void setGroup(String tenGroup){
		this.group = tenGroup;
	}
	public String getEmail(){
		return email;
	}
	public void setEmail(String nEmail){
		this.email = nEmail;
	}
	public String getInfo(){
		return this.getName()+"\n"+this.getID()+"\n"+this.getGroup()+"\n"+this.getEmail();
	}

}

package lambaitaplab2.com;

package lambaitaplab2.com;

public class StudentManagement{
	Student []students = new Student[100];
	public boolean sameGroup(Student s1, Student s2) {
        return s1.getGroup().equals(s2.getGroup());
	}
	void studentsByGroup() {
		System.out.println("Danh sach sinh vien lop INT22041:");
		for (int i=0;i<this.students.length;i++){
			if (this.students[i].getGroup()=="INT22041"){
				System.out.println(this.students[i].getInfo());
			}
		}
		System.out.println("Danh sach sinh vien lop INT22042");
		for (int i=0;i<this.students.length;i++){
			if (this.students[i].getGroup()=="INT22042"){
				System.out.println(this.students[i].getInfo());
			}
		}
	}
	void removeStudent(String id) {
		int i,j;
		for (i=0;i<this.students.length;i++){
			if (this.students[i].getID()==id){
				break;
			}
		}	
		for (j=i;j<this.students.length;j++){
			this.students[i] = this.students[i+1];
		}
	}

	public static void main (String[] args){
		Student s = new Student();
		s.setName("Cao Quy Dang");
		s.setID("17020680");
		s.setGroup("INT22042");
		s.setEmail("hadesi1999@gmail.com");
		Student b = new Student("KimSoHyun","17020170","wowKimSoHuyn@gmail.com");
		Student a = new Student(s);
		Student c = new Student("Luong Thi Nhu Nguyet", "17020172","nguyet@gmail.com");
		System.out.println("Thong tin sv la:\n"+a.getInfo());
		System.out.println(c.getInfo());
		StudentManagement sm = new StudentManagement();
		System.out.println(sm.sameGroup(s, a));
		
	}
}
