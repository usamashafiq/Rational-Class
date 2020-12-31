#include<iostream>
#include<conio.h>
using namespace std;
class cmplx {
	friend ostream & operator <<(ostream &, cmplx &);
	friend istream & operator >> (istream &, cmplx &);
public:
	void operator+(cmplx c);
	void operator-(cmplx c);
	void operator*(cmplx c);

private:
	int real1, real2;
	int img1, img2;
};
ostream & operator <<(ostream & print, cmplx & c) {
	print << c.real1 << "," << c.img1 << "i" << endl;
	print << c.real2 << "," << c.img2 << "i";
	return print;
}
istream & operator >> (istream & get, cmplx & c) {
	cout << "Input Real Part ";
	get >> c.real1;
	get >> c.real2;
	cout << "Input Imaginary Part  ";
	get >> c.img1;
	get >> c.img2;
	return get;
}
void cmplx::operator+(cmplx c) {
	real1 = real1 + real2;
	img1 = img1 + img2;
}
	void cmplx::operator-(cmplx c) {
		real1 = real1 - real2;
		img1 = img1 - img2;
	}
	void cmplx::operator*(cmplx c) {
		real1 = real1 * real2;
		img1 = img1 * img2;
	}
	void main() {
		cmplx c1;
		cmplx  d2;

		cin >> c1>>d2;
		cout << c1<<" "<<d2;
		c1 + d2;
		cout << c1;
		c1 - d2;
		cout << c1;
		c1*d2;
		cout << c1;
		_getch();
	}
