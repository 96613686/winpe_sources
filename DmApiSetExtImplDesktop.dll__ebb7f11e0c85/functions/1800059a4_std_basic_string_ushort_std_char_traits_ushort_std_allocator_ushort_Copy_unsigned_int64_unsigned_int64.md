# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800059a4`
- end: `0x180005ab3`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180005b50`

## callees

- `0x180001184`
- `0x1800059a4`
- `0x180005c60`
- `0x1800062dc`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180005a38`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180005a38`

## pseudocode

```c
const void **__fastcall std::wstring::_Copy(__int64 a1, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
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
  _BYTE *v15; // rdx
  _BYTE v16[72]; // [rsp+0h] [rbp-48h] BYREF
  void *v24; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = (const void **)a1;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = *(_QWORD *)(a1 + 24);
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
      goto LABEL_9;
    if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
    {
      std::_Xbad_alloc();
LABEL_9:
      v10 = 0;
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
      v24 = v13;
    }
    catch ( ... )
    {
      v15 = v16;
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(a1, v15, 0);
      throw;
    }
    v5 = (const void **)a1;
    v3 = a3;
    v4 = a2;
    v10 = v24;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 8 )
      v11 = v5;
    else
      v11 = *v5;
    std::char_traits<unsigned short>::copy(v10, v11, v3);
  }
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v5, v6, 0);
  *v5 = v10;
  v5[3] = (const void *)v4;
  result = v5;
  if ( v4 >= 8 )
    result = (const void **)v10;
  v5[2] = (const void *)v3;
  *((_WORD *)result + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x1800059a4  mov     [rsp+arg_10], r8
0x1800059a9  mov     [rsp+arg_8], rdx
0x1800059ae  mov     [rsp+arg_0], rcx
0x1800059b3  push    rbx
0x1800059b4  push    rsi
0x1800059b5  push    rdi
0x1800059b6  push    r14
0x1800059b8  push    r15
0x1800059ba  sub     rsp, 20h
0x1800059be  mov     r15, r8
0x1800059c1  mov     rbx, rdx
0x1800059c4  mov     rdi, rcx
0x1800059c7  or      rdx, 7
0x1800059cb  mov     r9, 7FFFFFFFFFFFFFFEh
0x1800059d5  cmp     rdx, r9
0x1800059d8  ja      short loc_180005A0E
0x1800059da  mov     rbx, rdx
0x1800059dd  mov     r8, [rcx+18h]
0x1800059e1  mov     rcx, r8
0x1800059e4  shr     rcx, 1
0x1800059e7  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800059f1  mul     rdx
0x1800059f4  shr     rdx, 1
0x1800059f7  cmp     rcx, rdx
0x1800059fa  jbe     short loc_180005A0E
0x1800059fc  mov     rax, r9
0x1800059ff  sub     rax, rcx
0x180005a02  cmp     r8, rax
0x180005a05  lea     rbx, [rcx+r8]
0x180005a09  jbe     short loc_180005A0E
0x180005a0b  mov     rbx, r9
0x180005a0e  lea     rcx, [rbx+1]
0x180005a12  xor     esi, esi
0x180005a14  test    rcx, rcx
0x180005a17  jz      short loc_180005A44
0x180005a19  mov     rax, 7FFFFFFFFFFFFFFFh
0x180005a23  cmp     rcx, rax
0x180005a26  ja      short loc_180005A38
0x180005a28  add     rcx, rcx; Size
0x180005a2b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005a30  mov     r14, rax
0x180005a33  test    rax, rax
0x180005a36  jnz     short loc_180005A47
0x180005a38  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180005a3f  nop     dword ptr [rax+rax+00h]
0x180005a44  mov     r14, rsi
0x180005a47  jmp     short loc_180005A5F
0x180005a49  xor     esi, esi
0x180005a4b  mov     rdi, [rsp+48h+arg_0]
0x180005a50  mov     r15, [rsp+48h+arg_10]
0x180005a55  mov     rbx, [rsp+48h+arg_8]
0x180005a5a  mov     r14, [rsp+48h+arg_18]
0x180005a5f  test    r15, r15
0x180005a62  jz      short loc_180005A7E
0x180005a64  cmp     qword ptr [rdi+18h], 8
0x180005a69  jb      short loc_180005A70
0x180005a6b  mov     rdx, [rdi]
0x180005a6e  jmp     short loc_180005A73
0x180005a70  mov     rdx, rdi
0x180005a73  mov     r8, r15
0x180005a76  mov     rcx, r14
0x180005a79  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x180005a7e  xor     r8d, r8d
0x180005a81  mov     dl, 1
0x180005a83  mov     rcx, rdi
0x180005a86  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180005a8b  mov     [rdi], r14
0x180005a8e  mov     [rdi+18h], rbx
0x180005a92  mov     rax, rdi
0x180005a95  cmp     rbx, 8
0x180005a99  cmovnb  rax, r14
0x180005a9d  mov     [rdi+10h], r15
0x180005aa1  mov     [rax+r15*2], si
0x180005aa6  add     rsp, 20h
0x180005aaa  pop     r15
0x180005aac  pop     r14
0x180005aae  pop     rdi
0x180005aaf  pop     rsi
0x180005ab0  pop     rbx
0x180005ab1  retn
```
