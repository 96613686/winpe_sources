# CDfsShell::CDfsShell(void)

- ea: `0x1800028e4`
- end: `0x180002a81`
- name: `??0CDfsShell@@QEAA@XZ`
- size: `413`
- prototype: `CDfsShell *__fastcall(CDfsShell *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004444`
- `0x18000463c`

## callees

- `0x180008ab8`
- `0x18000a9a6`

## pseudocode

```c
CDfsShell *__fastcall CDfsShell::CDfsShell(CDfsShell *this)
{
  char *v1; // r12

  v1 = (char *)this + 40;
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 5) = &CQWizardPageImpl<CDfsShellExtProp>::`vftable';
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  memset_0((char *)this + 108, 0, 0x64u);
  *((_DWORD *)v1 + 16) = 104;
  *((_QWORD *)v1 + 9) = off_180013160;
  *((_QWORD *)v1 + 10) = 201;
  *((_QWORD *)v1 + 13) = ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc;
  *((_DWORD *)v1 + 17) = 2176;
  *((_QWORD *)v1 + 15) = CQWizardPageImpl<CDfsShellExtProp>::PropPageCallback;
  *((_QWORD *)v1 + 24) = 0;
  *((_QWORD *)v1 + 25) = 0;
  *((_QWORD *)v1 + 27) = 0;
  *((_QWORD *)v1 + 28) = 0;
  *((_QWORD *)v1 + 29) = 0;
  *((_QWORD *)v1 + 30) = 0;
  *((_QWORD *)v1 + 31) = 0;
  *((_QWORD *)v1 + 32) = 0;
  *((_QWORD *)v1 + 33) = 0;
  *((_QWORD *)v1 + 14) = v1;
  *(_QWORD *)v1 = &CDfsShellExtProp::`vftable';
  *((_QWORD *)v1 + 26) = 0;
  LoadStringFromResource(0x67u, (unsigned __int16 **)v1 + 27);
  LoadStringFromResource(0x68u, (unsigned __int16 **)v1 + 28);
  LoadStringFromResource(0x69u, (unsigned __int16 **)v1 + 29);
  LoadStringFromResource(0x6Au, (unsigned __int16 **)v1 + 30);
  LoadStringFromResource(0x6Bu, (unsigned __int16 **)v1 + 31);
  LoadStringFromResource(0x6Cu, (unsigned __int16 **)v1 + 32);
  LoadStringFromResource(0x6Du, (unsigned __int16 **)v1 + 33);
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 4) = 0;
  return this;
}

```

## disassembly

```asm
0x1800028e4  push    rbx
0x1800028e6  push    rbp
0x1800028e7  push    rsi
0x1800028e8  push    rdi
0x1800028e9  push    r12
0x1800028eb  push    r13
0x1800028ed  push    r14
0x1800028ef  push    r15
0x1800028f1  sub     rsp, 28h
0x1800028f5  lea     r12, [rcx+28h]
0x1800028f9  xor     ebp, ebp
0x1800028fb  mov     [rcx+10h], ebp
0x1800028fe  lea     rax, ??_7?$CQWizardPageImpl@VCDfsShellExtProp@@@@6B@; const CQWizardPageImpl<CDfsShellExtProp>::`vftable'
0x180002905  mov     r13, rcx
0x180002908  mov     [r12+8], rbp
0x18000290d  mov     [r12+28h], rbp
0x180002912  add     rcx, 6Ch ; 'l'; void *
0x180002916  mov     [r12], rax
0x18000291a  lea     r8d, [rbp+64h]; Size
0x18000291e  xor     edx, edx; Val
0x180002920  mov     [r12+30h], rbp
0x180002925  mov     [r12+38h], ebp
0x18000292a  mov     [r12+0A8h], rbp
0x180002932  mov     [r12+0B0h], rbp
0x18000293a  mov     [r12+0B8h], rbp
0x180002942  call    memset_0
0x180002947  mov     dword ptr [r12+40h], 68h ; 'h'
0x180002950  lea     rdx, [r12+0D8h]; unsigned __int16 **
0x180002958  mov     rax, cs:off_180013160
0x18000295f  lea     rbx, [r12+0E0h]
0x180002967  mov     [r12+48h], rax
0x18000296c  lea     rdi, [r12+0E8h]
0x180002974  mov     qword ptr [r12+50h], 0C9h
0x18000297d  lea     rax, ?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z; ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc(HWND__ *,uint,unsigned __int64,__int64)
0x180002984  mov     [r12+68h], rax
0x180002989  lea     rsi, [r12+0F0h]
0x180002991  mov     dword ptr [r12+44h], 880h
0x18000299a  lea     rax, ?PropPageCallback@?$CQWizardPageImpl@VCDfsShellExtProp@@@@SAIPEAUHWND__@@IPEAU_PROPSHEETPAGEW@@@Z; CQWizardPageImpl<CDfsShellExtProp>::PropPageCallback(HWND__ *,uint,_PROPSHEETPAGEW *)
0x1800029a1  mov     [r12+78h], rax
0x1800029a6  lea     r14, [r12+0F8h]
0x1800029ae  mov     [r12+0C0h], rbp
0x1800029b6  lea     rax, ??_7CDfsShellExtProp@@6B@; const CDfsShellExtProp::`vftable'
0x1800029bd  mov     [r12+0C8h], rbp
0x1800029c5  lea     r15, [r12+100h]
0x1800029cd  mov     [rdx], rbp
0x1800029d0  mov     ecx, 67h ; 'g'; uID
0x1800029d5  mov     [rbx], rbp
0x1800029d8  mov     [rdi], rbp
0x1800029db  mov     [rsi], rbp
0x1800029de  mov     [r14], rbp
0x1800029e1  mov     [r15], rbp
0x1800029e4  lea     rbp, [r12+108h]
0x1800029ec  mov     qword ptr [rbp+0], 0
0x1800029f4  mov     [r12+70h], r12
0x1800029f9  mov     [r12], rax
0x1800029fd  mov     qword ptr [r12+0D0h], 0
0x180002a09  call    ?LoadStringFromResource@@YAJIPEAPEAG@Z; LoadStringFromResource(uint,ushort * *)
0x180002a0e  mov     rdx, rbx; unsigned __int16 **
0x180002a11  mov     ecx, 68h ; 'h'; uID
0x180002a16  call    ?LoadStringFromResource@@YAJIPEAPEAG@Z; LoadStringFromResource(uint,ushort * *)
0x180002a1b  mov     rdx, rdi; unsigned __int16 **
0x180002a1e  mov     ecx, 69h ; 'i'; uID
0x180002a23  call    ?LoadStringFromResource@@YAJIPEAPEAG@Z; LoadStringFromResource(uint,ushort * *)
0x180002a28  mov     rdx, rsi; unsigned __int16 **
0x180002a2b  mov     ecx, 6Ah ; 'j'; uID
0x180002a30  call    ?LoadStringFromResource@@YAJIPEAPEAG@Z; LoadStringFromResource(uint,ushort * *)
0x180002a35  mov     rdx, r14; unsigned __int16 **
0x180002a38  mov     ecx, 6Bh ; 'k'; uID
0x180002a3d  call    ?LoadStringFromResource@@YAJIPEAPEAG@Z; LoadStringFromResource(uint,ushort * *)
0x180002a42  mov     rdx, r15; unsigned __int16 **
0x180002a45  mov     ecx, 6Ch ; 'l'; uID
0x180002a4a  call    ?LoadStringFromResource@@YAJIPEAPEAG@Z; LoadStringFromResource(uint,ushort * *)
0x180002a4f  mov     rdx, rbp; unsigned __int16 **
0x180002a52  mov     ecx, 6Dh ; 'm'; uID
0x180002a57  call    ?LoadStringFromResource@@YAJIPEAPEAG@Z; LoadStringFromResource(uint,ushort * *)
0x180002a5c  xor     eax, eax
0x180002a5e  mov     [r13+18h], rax
0x180002a62  mov     [r13+138h], rax
0x180002a69  mov     [r13+20h], rax
0x180002a6d  mov     rax, r13
0x180002a70  add     rsp, 28h
0x180002a74  pop     r15
0x180002a76  pop     r14
0x180002a78  pop     r13
0x180002a7a  pop     r12
0x180002a7c  pop     rdi
0x180002a7d  pop     rsi
0x180002a7e  pop     rbp
0x180002a7f  pop     rbx
0x180002a80  retn
```
