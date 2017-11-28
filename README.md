# tarek
.MODEL FLAT
INCLUDE io.h
.STACK 4096
.DATA
	Num1 DWORD  ?
	Num2 DWORD  ?
	Num3 DWORD  ?
	Message1 BYTE "Please enter integer x: ",0
	Message2 BYTE "Please enter integer y: ",0
	Message3 BYTE "Please enter integer z: ",0
	inp BYTE 40 DUP (?)
	
	resultlb1 BYTE "the value is :",0
	result BYTE 11 DUP (?),0
.CODE
MainProc PROC
	input Message1,inp,40
	atod inp
	mov Num1,eax
	input Message2,inp,40
	atod inp
	mov Num2,eax
	add eax,Num1
	mov Num2,eax
	input Message3,inp,40
	atod inp
	mov Num3,eax
	mov eax,Num2
	sub eax,Num3
	sub eax,Num3
	add eax,1
	mov Num3,eax
	neg Num3
	mov eax,Num3
	dtoa result,eax
	output resultlb1,result
	mov eax,0
	ret
MainProc ENDP
END
///////////////////////////////////////////////////////
# assembly code for solveing   2(X+Y)+Z Equation
.586
.MODEL FLAT
INCLUDE io.h
.STACK 4096
.DATA
	Num1 DWORD  ?
	Num2 DWORD  ?
	Num3 DWORD  ?
	Mesg1 BYTE "Please enter integer x: ",0
	Mesg2 BYTE "Please enter integer y: ",0
	Mesg3 BYTE "Please enter integer z: ",0
	inp BYTE 40 DUP (?)
	resultl BYTE "the value is :",0
	result BYTE 11 DUP (?),0

.CODE
	MainProc PROC
		input mesg1 ,inp,40
		atod inp
		mov Num1,eax
		input mesg2 ,inp,40
		atod inp
		add eax,Num1
		imul eax,2
		mov Num2,eax
		input mesg3 ,inp,40
		atod inp
		add eax,Num2
		dtoa result ,eax
		output resultl,result
		mov eax,0
		ret
	MainProc ENDP
	END
  ////////////////////////////////////////
  # assembly code for perimeter OF rectangle
  .586
.MODEL FLAT
INCLUDE io.h
.STACK 4096
.DATA
	l DWORD ?
	inp BYTE ?
	Mesg1 BYTE "enter the length : ",0
	Mesg2 BYTE "enter the width  : ",0
	resultb1 BYTE " the perimeter is : ",0
	Result BYTE 11 DUP(?),0
.CODE
MainProc PROC
	 input mesg1,inp,4
	 atod inp 
	 mov l , eax
	 input mesg2,inp,4
	 atod inp 
	 add eax,l
	 imul eax,2
	 dtoa Result ,eax
	 output resultb1, Result

mov eax,0
ret
MainProc ENDP
END
///////////////////////////////
 # assembly code for calculat value of the coins Entered
.586
.MODEL FLAT
INCLUDE io.h
.STACK 4096
.DATA

	   Mesg1 BYTE  "enter coins in  pennies   :",0
	   Mesg2 BYTE  "enter coins in  nickels   :",0
	   Mesg3 BYTE  "enter coins in  dimes     :",0
	   Mesg4 BYTE  "enter coins in  quarters  :",0
	   Mesg5 BYTE  "enter coins in  fifty-cent:",0
	   Mesg6 BYTE  "enter coins in  dollar    :",0

	   pen	DWORD ?
	   nic  DWORD ?
	   dim	DWORD ?
	   qur	DWORD ?
	   fic  DWORD ?
	   dol	DWORD ?
	   str1	BYTE 40 DUP (?)
	   Res	BYTE 11 DUP (?),0
	   result1 BYTE	"number of dollars = ",0
	   result2 BYTE	"number of cents   = ",0
.CODE
MainProc PROC
		input Mesg1,str1,40
		atod str1
		mov	pen,eax
		input Mesg2,str1,40
		atod str1
		imul eax,5
		mov	 nic,eax
		input Mesg3,str1,40
		atod str1
    imul eax,10
		mov	 dim,eax
		input Mesg4,str1,40
		atod str1
		imul eax,25
		mov	 qur,eax
		input Mesg5,str1,40
		atod str1
		imul eax,50
		mov	 fic,eax

		input Mesg6,str1,40
		atod str1
		imul eax,100
		mov	 dol,eax

		mov	 eax,dol
		add	 eax,fic
		add	 eax,qur
		add	 eax,dim
		add	 eax,nic
		add	 eax,pen

		mov	 edx,0
		mov	 ecx,100
		div	 ecx

		dtoa Res,eax
		output result1,Res

		dtoa Res,edx
		output result2,Res

		mov	 eax,0
		ret
MainProc ENDP
 END
/////////////////////////////////////////
 # assembly code for calculat  sum and averag of grads
 .586
.MODEL FLAT
INCLUDE io.h
.STACK 4096
.DATA
	num1 DWORD ?
	num2 DWORD ?
	num3 DWORD ?
	num4 DWORD ?
	mesg1 BYTE "enter the grade 1 : ",0
	mesg2 BYTE "enter the grade 2 : ",0
	mesg3 BYTE "enter the grade 3 : ",0
	mesg4 BYTE "enter the grade 4 : ",0
	inp BYTE 40 DUP (?)
	result1 BYTE " the sum is : ",0
	result2 BYTE " the avg is : ",0
	res1 BYTE 11 DUP(?)
	res2 BYTE 11 DUP(?)

.CODE
	MainProc PROC
		input mesg1,inp,40
		atod inp
		mov num1,eax
		input mesg2,inp,40
		atod inp
		add eax,num1
		mov num1,eax
		input mesg3,inp,40
		atod inp
		add eax,num1
		mov num1,eax
		input mesg3,inp,40
		atod inp
		add eax,num1
		dtoa res1,eax
		output  result1 ,res1
		add num2,eax
		mov num1,eax
		mov eax,num2
		mov  edx,0
		mov ecx,4
		div ecx
		;mov num3,edx
		;add eax,num3
		dtoa res2,eax
		output result2,res2
	    mov eax,0
		ret
	MainProc ENDP
    END
    //////////////////////////////////
 # assembly code for calculat 
 .586                  
.MODEL FLAT             
INCLUDE io.h
.STACK 4096             

.DATA                   
   
    G1Msg BYTE "Enter  Grade 1  ",0
    W1Msg BYTE "Enter  weight 1 ",0

    G2Msg BYTE "Enter  Grade 2 ",0
    W2Msg BYTE "Enter  weight 2 ",0

	G3Msg BYTE "Enter  Grade 3 ",0
	W3Msg BYTE "Enter  weight 3 ",0

    G4Msg BYTE "Enter  Grade 4",0
    W4Msg BYTE "Enter weight 4",0
    
	WSmsg  BYTE "  weight   sum    = ",0
    SOWMsg BYTE  "  sum of weights  = ",0
    WavgMsg BYTE "gw ighted average =",0

	
	  G DWORD 4 DUP(?),0
      w DWORD 4 DUP(?),0
	  res1 DWORD ?,0
	  res2 DWORD ?,0
	  res3 DWORD ?,0
.CODE                      
MainProc PROC
	input G1Msg,G,4
	input W1Msg,w,4
	input G2Msg,G+4,4
	input W2Msg,w+4,4
	input G3Msg,G+8,4
	input W3Msg,w+8,4
	input G4Msg,G+12,4
	input W4Msg,w+12,4

	atod G
	mov G ,eax
	atod w
	mov W,eax
	mul G
	mov G,eax  

	atod G+4
	mov G+4,eax
	atod w+4
	add W,eax          
	mul G+4
	add G,eax         

	atod G+8
	mov G+8,eax
	atod w+8
	add W,eax           
	mul G+8
	add G,eax               

	atod G+12
	mov G+12,eax
	atod w+12
	add W,eax
	mul G+12
	add G,eax             

	 mov eax,G
	 dtoa out1,eax
	 output WSmsg,res1 

	 mov eax,W
	 dtoa out2,eax
	 output SOWMsg,res2
 

	 mov eax,G
	 mov edx,0
	 div W
	 dtoa out3,eax
	 output WavgMsg,res3

	 mov eax,0                
	  ret
MainProc ENDP          

END
