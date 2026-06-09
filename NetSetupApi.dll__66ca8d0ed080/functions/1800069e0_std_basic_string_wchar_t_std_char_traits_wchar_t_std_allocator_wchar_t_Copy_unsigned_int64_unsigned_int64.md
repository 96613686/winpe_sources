# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800069e0`
- end: `0x180006af0`
- name: `?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K0@Z`
- size: `272`
- prototype: `const void **__fastcall(const void **Src, unsigned __int64, const void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000eacc`

## callees

- `0x1800069e0`
- `0x180007274`
- `0x180008088`
- `0x180008208`
- `0x180008976`

## pseudocode

```c
const void **__fastcall std::wstring::_Copy(const void **Src, unsigned __int64 a2, const void *a3)
{
  const void *v3; // r15
  unsigned __int64 v4; // rbx
  const void **v5; // rdi
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // r14
  const void *v11; // rdx
  const void **result; // rax
  void *v13; // rax
  unsigned __int64 v14; // rcx
  _QWORD *v15; // rdx
  _QWORD v16[11]; // [rsp+0h] [rbp-58h] BYREF
  void *v20; // [rsp+78h] [rbp+20h]

  v16[4] = -2;
  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    v6 /= 3u;
    if ( v7 >> 1 > v6 )
    {
      v4 = v8 + v7;
      if ( v7 > 0x7FFFFFFFFFFFFFFELL - v8 )
        v4 = 0x7FFFFFFFFFFFFFFELL;
    }
  }
  try
  {
    v9 = v4 + 1;
    if ( v4 == -1 )
    {
      v10 = 0;
    }
    else if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
    {
      std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    v6 = (unsigned __int64)v16;
    try
    {
      v13 = 0;
      v14 = a2 + 1;
      if ( a2 != -1 && (v14 > 0x7FFFFFFFFFFFFFFFLL || (v13 = operator new(2 * v14)) == 0) )
        std::_Xbad_alloc();
      v20 = v13;
    }
    catch ( ... )
    {
      v15 = v16;
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(Src, v15, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = v20;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 8 )
      v11 = v5;
    else
      v11 = *v5;
    memcpy_0(v10, v11, 2LL * (_QWORD)v3);
  }
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v5, v6, 0);
  *v5 = v10;
  v5[3] = (const void *)v4;
  result = v5;
  if ( v4 >= 8 )
    result = (const void **)v10;
  v5[2] = v3;
  *((_WORD *)result + (_QWORD)v3) = 0;
  return result;
}

```

## disassembly

```asm
0x1800069e0  mov     rax, rsp
0x1800069e3  mov     [rax+18h], r8
0x1800069e7  mov     [rax+10h], rdx
0x1800069eb  mov     [rax+8], rcx
0x1800069ef  push    rbx
0x1800069f0  push    rsi
0x1800069f1  push    rdi
0x1800069f2  push    r14
0x1800069f4  push    r15
0x1800069f6  sub     rsp, 30h
0x1800069fa  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180006a02  mov     r15, r8
0x180006a05  mov     rbx, rdx
0x180006a08  mov     rdi, rcx
0x180006a0b  or      rdx, 7
0x180006a0f  mov     r9, 7FFFFFFFFFFFFFFEh
0x180006a19  cmp     rdx, r9
0x180006a1c  ja      short loc_180006A52
0x180006a1e  mov     rbx, rdx
0x180006a21  mov     r8, [rcx+18h]
0x180006a25  mov     rcx, r8
0x180006a28  shr     rcx, 1
0x180006a2b  mov     rax, 0AAAAAAAAAAAAAAABh
0x180006a35  mul     rdx
0x180006a38  shr     rdx, 1
0x180006a3b  cmp     rcx, rdx
0x180006a3e  jbe     short loc_180006A52
0x180006a40  mov     rax, r9
0x180006a43  sub     rax, rcx
0x180006a46  cmp     r8, rax
0x180006a49  lea     rbx, [rcx+r8]
0x180006a4d  jbe     short loc_180006A52
0x180006a4f  mov     rbx, r9
0x180006a52  lea     rcx, [rbx+1]
0x180006a56  xor     esi, esi
0x180006a58  test    rcx, rcx
0x180006a5b  jz      short loc_180006A81
0x180006a5d  mov     rax, 7FFFFFFFFFFFFFFFh
0x180006a67  cmp     rcx, rax
0x180006a6a  ja      short loc_180006A7C
0x180006a6c  add     rcx, rcx; Size
0x180006a6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006a74  mov     r14, rax
0x180006a77  test    rax, rax
0x180006a7a  jnz     short loc_180006A84
0x180006a7c  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180006a81  mov     r14, rsi
0x180006a84  jmp     short loc_180006A9C
0x180006a86  xor     esi, esi
0x180006a88  mov     rdi, [rsp+58h+arg_0]
0x180006a8d  mov     r15, [rsp+58h+arg_10]
0x180006a92  mov     rbx, [rsp+58h+arg_8]
0x180006a97  mov     r14, [rsp+58h+arg_18]
0x180006a9c  test    r15, r15
0x180006a9f  jz      short loc_180006ABC
0x180006aa1  cmp     qword ptr [rdi+18h], 8
0x180006aa6  jb      short loc_180006AAD
0x180006aa8  mov     rdx, [rdi]
0x180006aab  jmp     short loc_180006AB0
0x180006aad  mov     rdx, rdi; Src
0x180006ab0  lea     r8, [r15+r15]; Size
0x180006ab4  mov     rcx, r14; void *
0x180006ab7  call    memcpy_0
0x180006abc  xor     r8d, r8d
0x180006abf  mov     dl, 1
0x180006ac1  mov     rcx, rdi
0x180006ac4  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180006ac9  mov     [rdi], r14
0x180006acc  mov     [rdi+18h], rbx
0x180006ad0  mov     rax, rdi
0x180006ad3  cmp     rbx, 8
0x180006ad7  cmovnb  rax, r14
0x180006adb  mov     [rdi+10h], r15
0x180006adf  mov     [rax+r15*2], si
0x180006ae4  add     rsp, 30h
0x180006ae8  pop     r15
0x180006aea  pop     r14
0x180006aec  pop     rdi
0x180006aed  pop     rsi
0x180006aee  pop     rbx
0x180006aef  retn
```
