# xgc::CDeviceContext::SelectBitmap(uint,uint)

- ea: `0x180027054`
- end: `0x18002714f`
- name: `?SelectBitmap@CDeviceContext@xgc@@AEAAXII@Z`
- size: `251`
- prototype: `void __fastcall(xgc::CDeviceContext *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180024584`

## callees

- `0x180008830`
- `0x180027054`
- `0x180027c54`
- `0x180037278`
- `0x1800372e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800270d0`
- `KERNEL32!GetLastError` at `0x180027116`
- `KERNEL32!GetLastError` at `0x1800270d0`
- `KERNEL32!GetLastError` at `0x180027116`
- `GDI32!SelectObject` at `0x18002710b`
- `GDI32!SelectObject` at `0x18002710b`
- `GDI32!CreateDIBSection` at `0x1800270b7`
- `GDI32!CreateDIBSection` at `0x1800270b7`
- `GDI32!GdiFlush` at `0x1800270f4`
- `GDI32!GdiFlush` at `0x1800270f4`

## pseudocode

```c
void __fastcall xgc::CDeviceContext::SelectBitmap(xgc::CDeviceContext *this, LONG a2, int a3)
{
  void **v3; // rsi
  void **v4; // r9
  HDC v6; // rcx
  HBITMAP v7; // rbx
  signed int LastError; // eax
  int v9; // edx
  const char *v10; // r8
  int v11; // r9d
  const char *v12; // rdx
  xpsrdr *v13; // rcx
  int v14; // r8d
  signed int v15; // eax
  int v16; // edx
  const char *v17; // r8
  int v18; // r9d
  BITMAPINFO v19; // [rsp+30h] [rbp-58h] BYREF

  v19.bmiHeader.biWidth = a2;
  v3 = (void **)((char *)this + 136);
  v19.bmiHeader.biSize = 40;
  v4 = (void **)((char *)this + 112);
  *(_QWORD *)&v19.bmiHeader.biPlanes = 1572865;
  v19.bmiHeader.biHeight = -a3;
  v6 = (HDC)*((_QWORD *)this + 4);
  memset(&v19.bmiHeader.biSizeImage, 0, 24);
  v7 = CreateDIBSection(v6, &v19, 0, v4, 0, 0);
  Holder<HRGN__ *,close_funct<int (*)(void *),&int DeleteObject(void *)>,invalid_const<HRGN__ *,0>>::~Holder<HRGN__ *,close_funct<int (*)(void *),&int DeleteObject(void *)>,invalid_const<HRGN__ *,0>>(v3);
  *v3 = v7;
  if ( !v7 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)LastError, v9, v10, v11);
  }
  if ( !GdiFlush() )
    xpsrdr::ThrowLogicException(v13, v12, v14);
  if ( !SelectObject(*((HDC *)this + 4), *v3) )
  {
    v15 = GetLastError();
    if ( v15 > 0 )
      v15 = (unsigned __int16)v15 | 0x80070000;
    if ( v15 >= 0 )
      v15 = -2147467259;
    xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)v15, v16, v17, v18);
  }
}

```

## disassembly

```asm
0x180027054  mov     r11, rsp
0x180027057  push    rbx
0x180027058  push    rsi
0x180027059  push    rdi
0x18002705a  sub     rsp, 70h
0x18002705e  mov     rax, cs:__security_cookie
0x180027065  xor     rax, rsp
0x180027068  mov     [rsp+88h+var_28], rax
0x18002706d  mov     [rsp+88h+var_54], edx
0x180027071  lea     rsi, [rcx+88h]
0x180027078  mov     [rsp+88h+var_58], 28h ; '('
0x180027080  lea     r9, [rcx+70h]; ppvBits
0x180027084  xor     eax, eax
0x180027086  mov     qword ptr [r11-4Ch], 180001h
0x18002708e  neg     r8d
0x180027091  mov     [rsp+88h+offset], eax; offset
0x180027095  mov     [r11-50h], r8d
0x180027099  lea     rdx, [r11-58h]; pbmi
0x18002709d  xorps   xmm0, xmm0
0x1800270a0  mov     [r11-68h], rax
0x1800270a4  mov     rdi, rcx
0x1800270a7  xor     r8d, r8d; usage
0x1800270aa  mov     rcx, [rcx+20h]; hdc
0x1800270ae  movups  [rsp+88h+var_44], xmm0
0x1800270b3  mov     [r11-34h], rax
0x1800270b7  call    cs:__imp_CreateDIBSection
0x1800270bd  mov     rcx, rsi
0x1800270c0  mov     rbx, rax
0x1800270c3  call    ??1?$Holder@PEAUHRGN__@@U?$close_funct@P6AHPEAX@Z$1?DeleteObject@@YAH0@Z@@U?$invalid_const@PEAUHRGN__@@$0A@@@@@QEAA@XZ; Holder<HRGN__ *,close_funct<int (*)(void *),&DeleteObject(void *)>,invalid_const<HRGN__ *,0>>::~Holder<HRGN__ *,close_funct<int (*)(void *),&DeleteObject(void *)>,invalid_const<HRGN__ *,0>>(void)
0x1800270c8  mov     [rsi], rbx
0x1800270cb  test    rbx, rbx
0x1800270ce  jnz     short loc_1800270F4
0x1800270d0  call    cs:__imp_GetLastError
0x1800270d6  test    eax, eax
0x1800270d8  jle     short loc_1800270E2
0x1800270da  movzx   eax, ax
0x1800270dd  or      eax, 80070000h
0x1800270e2  mov     ecx, 80004005h
0x1800270e7  test    eax, eax
0x1800270e9  cmovns  eax, ecx
0x1800270ec  mov     ecx, eax; this
0x1800270ee  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x1800270f4  call    cs:__imp_GdiFlush
0x1800270fa  test    eax, eax
0x1800270fc  jnz     short loc_180027104
0x1800270fe  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
0x180027104  mov     rdx, [rsi]; h
0x180027107  mov     rcx, [rdi+20h]; hdc
0x18002710b  call    cs:__imp_SelectObject
0x180027111  test    rax, rax
0x180027114  jnz     short loc_18002713A
0x180027116  call    cs:__imp_GetLastError
0x18002711c  test    eax, eax
0x18002711e  jle     short loc_180027128
0x180027120  movzx   eax, ax
0x180027123  or      eax, 80070000h
0x180027128  mov     ecx, 80004005h
0x18002712d  test    eax, eax
0x18002712f  cmovns  eax, ecx
0x180027132  mov     ecx, eax; this
0x180027134  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002713a  mov     rcx, [rsp+88h+var_28]
0x18002713f  xor     rcx, rsp; StackCookie
0x180027142  call    __security_check_cookie
0x180027147  add     rsp, 70h
0x18002714b  pop     rdi
0x18002714c  pop     rsi
0x18002714d  pop     rbx
0x18002714e  retn
```
