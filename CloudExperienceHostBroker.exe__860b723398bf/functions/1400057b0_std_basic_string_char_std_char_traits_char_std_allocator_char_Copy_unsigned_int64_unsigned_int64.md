# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1400057b0`
- end: `0x140005889`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `217`
- prototype: `const void **__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400058bc`

## callees

- `0x140002226`
- `0x140002fd8`
- `0x1400057b0`
- `0x140005974`

## pseudocode

```c
const void **__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // rsi
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  void *v10; // r14
  const void *v11; // rdx
  __int64 v12; // rdx
  const void **result; // rax
  __int64 *v14; // rdx
  __int64 v15; // [rsp+0h] [rbp-48h] BYREF
  __int64 v23; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    v9 = v6 / 3;
    if ( v7 >> 1 > v9 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  try
  {
    v10 = (void *)std::_Allocate<char>(v4 + 1, 0);
  }
  catch ( ... )
  {
    try
    {
      v23 = std::_Allocate<char>(a2 + 1, 0);
    }
    catch ( ... )
    {
      v14 = &v15;
      LOBYTE(v14) = 1;
      std::string::_Tidy(Src, v14, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = (void *)v23;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v11 = v5;
    else
      v11 = *v5;
    memcpy_0(v10, v11, v3);
  }
  LOBYTE(v12) = 1;
  std::string::_Tidy(v5, v12, 0);
  *v5 = v10;
  v5[3] = (const void *)v4;
  result = v5;
  if ( v4 >= 0x10 )
    result = (const void **)v10;
  v5[2] = (const void *)v3;
  *((_BYTE *)result + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x1400057b0  mov     [rsp+arg_10], r8
0x1400057b5  mov     [rsp+arg_8], rdx
0x1400057ba  mov     [rsp+arg_0], rcx
0x1400057bf  push    rbx
0x1400057c0  push    rsi
0x1400057c1  push    rdi
0x1400057c2  push    r14
0x1400057c4  sub     rsp, 28h
0x1400057c8  mov     rsi, r8
0x1400057cb  mov     rdi, rdx
0x1400057ce  mov     rbx, rcx
0x1400057d1  or      rdx, 0Fh
0x1400057d5  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1400057dc  cmp     rdx, r9
0x1400057df  ja      short loc_140005815
0x1400057e1  mov     rdi, rdx
0x1400057e4  mov     r8, [rcx+18h]
0x1400057e8  mov     rcx, r8
0x1400057eb  shr     rcx, 1
0x1400057ee  mov     rax, 0AAAAAAAAAAAAAAABh
0x1400057f8  mul     rdx
0x1400057fb  shr     rdx, 1
0x1400057fe  cmp     rcx, rdx
0x140005801  jbe     short loc_140005815
0x140005803  mov     rax, r9
0x140005806  sub     rax, rcx
0x140005809  cmp     r8, rax
0x14000580c  lea     rdi, [rcx+r8]
0x140005810  jbe     short loc_140005815
0x140005812  mov     rdi, r9
0x140005815  lea     rcx, [rdi+1]
0x140005819  xor     edx, edx
0x14000581b  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x140005820  mov     r14, rax
0x140005823  jmp     short loc_140005839
0x140005825  mov     rbx, [rsp+48h+arg_0]
0x14000582a  mov     rsi, [rsp+48h+arg_10]
0x14000582f  mov     rdi, [rsp+48h+arg_8]
0x140005834  mov     r14, [rsp+48h+arg_18]
0x140005839  test    rsi, rsi
0x14000583c  jz      short loc_140005858
0x14000583e  cmp     qword ptr [rbx+18h], 10h
0x140005843  jb      short loc_14000584A
0x140005845  mov     rdx, [rbx]
0x140005848  jmp     short loc_14000584D
0x14000584a  mov     rdx, rbx; Src
0x14000584d  mov     r8, rsi; Size
0x140005850  mov     rcx, r14; void *
0x140005853  call    memcpy_0
0x140005858  xor     r8d, r8d
0x14000585b  mov     dl, 1
0x14000585d  mov     rcx, rbx
0x140005860  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x140005865  mov     [rbx], r14
0x140005868  mov     [rbx+18h], rdi
0x14000586c  mov     rax, rbx
0x14000586f  cmp     rdi, 10h
0x140005873  cmovnb  rax, r14
0x140005877  mov     [rbx+10h], rsi
0x14000587b  mov     byte ptr [rax+rsi], 0
0x14000587f  add     rsp, 28h
0x140005883  pop     r14
0x140005885  pop     rdi
0x140005886  pop     rsi
0x140005887  pop     rbx
0x140005888  retn
```
