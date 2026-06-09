# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x14000f208`
- end: `0x14000f2e6`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f5a8`

## callees

- `0x14000cec0`
- `0x14000f208`
- `0x14000f998`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000f2af`
- `msvcrt!memcpy_s` at `0x14000f2af`

## pseudocode

```c
__int64 __fastcall std::string::_Copy(__int64 a1, unsigned __int64 a2, rsize_t a3)
{
  rsize_t v3; // r14
  unsigned __int64 v4; // rbx
  __int64 v5; // rdi
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  void *v10; // r15
  const void **v11; // rsi
  const void *v12; // r8
  __int64 v13; // rdx
  __int64 result; // rax
  __int64 *v15; // rdx
  __int64 v16; // [rsp+0h] [rbp-48h] BYREF
  __int64 v24; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = *(_QWORD *)(a1 + 32);
    v8 = v7 >> 1;
    v9 = v6 / 3;
    if ( v9 < v7 >> 1 && v7 <= -2LL - v8 )
      v4 = v8 + v7;
  }
  try
  {
    v10 = (void *)std::_Allocate<char>(v4 + 1, 0);
  }
  catch ( ... )
  {
    try
    {
      v24 = std::_Allocate<char>(a2 + 1, 0);
    }
    catch ( ... )
    {
      v15 = &v16;
      LOBYTE(v15) = 1;
      std::string::_Tidy(a1, v15, 0);
      throw;
    }
    v5 = a1;
    v3 = a3;
    v4 = a2;
    v10 = (void *)v24;
  }
  v11 = (const void **)(v5 + 8);
  if ( v3 )
  {
    if ( *(_QWORD *)(v5 + 32) < 0x10u )
      v12 = (const void *)(v5 + 8);
    else
      v12 = *v11;
    memcpy_s(v10, v4 + 1, v12, v3);
  }
  LOBYTE(v13) = 1;
  result = std::string::_Tidy(v5, v13, 0);
  *v11 = v10;
  *(_QWORD *)(v5 + 32) = v4;
  if ( v4 >= 0x10 )
    v11 = (const void **)v10;
  *(_QWORD *)(v5 + 24) = v3;
  *((_BYTE *)v11 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x14000f208  mov     [rsp+arg_10], r8
0x14000f20d  mov     [rsp+arg_8], rdx
0x14000f212  mov     [rsp+arg_0], rcx
0x14000f217  push    rbx
0x14000f218  push    rsi
0x14000f219  push    rdi
0x14000f21a  push    r14
0x14000f21c  push    r15
0x14000f21e  sub     rsp, 20h
0x14000f222  mov     r14, r8
0x14000f225  mov     rbx, rdx
0x14000f228  mov     rdi, rcx
0x14000f22b  or      rdx, 0Fh
0x14000f22f  mov     r9, 0FFFFFFFFFFFFFFFEh
0x14000f236  cmp     rdx, r9
0x14000f239  ja      short loc_14000F269
0x14000f23b  mov     rbx, rdx
0x14000f23e  mov     r8, [rcx+20h]
0x14000f242  mov     rcx, r8
0x14000f245  shr     rcx, 1
0x14000f248  mov     rax, 0AAAAAAAAAAAAAAABh
0x14000f252  mul     rdx
0x14000f255  shr     rdx, 1
0x14000f258  cmp     rdx, rcx
0x14000f25b  jnb     short loc_14000F269
0x14000f25d  sub     r9, rcx
0x14000f260  cmp     r8, r9
0x14000f263  ja      short loc_14000F269
0x14000f265  lea     rbx, [rcx+r8]
0x14000f269  lea     rcx, [rbx+1]
0x14000f26d  xor     edx, edx
0x14000f26f  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x14000f274  mov     r15, rax
0x14000f277  jmp     short loc_14000F28D
0x14000f279  mov     rdi, [rsp+48h+arg_0]
0x14000f27e  mov     r14, [rsp+48h+arg_10]
0x14000f283  mov     rbx, [rsp+48h+arg_8]
0x14000f288  mov     r15, [rsp+48h+arg_18]
0x14000f28d  lea     rsi, [rdi+8]
0x14000f291  test    r14, r14
0x14000f294  jz      short loc_14000F2B5
0x14000f296  cmp     qword ptr [rdi+20h], 10h
0x14000f29b  jb      short loc_14000F2A2
0x14000f29d  mov     r8, [rsi]
0x14000f2a0  jmp     short loc_14000F2A5
0x14000f2a2  mov     r8, rsi; Source
0x14000f2a5  lea     rdx, [rbx+1]; DestinationSize
0x14000f2a9  mov     r9, r14; SourceSize
0x14000f2ac  mov     rcx, r15; Destination
0x14000f2af  call    cs:__imp_memcpy_s
0x14000f2b5  xor     r8d, r8d
0x14000f2b8  mov     dl, 1
0x14000f2ba  mov     rcx, rdi
0x14000f2bd  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x14000f2c2  mov     [rsi], r15
0x14000f2c5  mov     [rdi+20h], rbx
0x14000f2c9  cmp     rbx, 10h
0x14000f2cd  cmovnb  rsi, r15
0x14000f2d1  mov     [rdi+18h], r14
0x14000f2d5  mov     byte ptr [rsi+r14], 0
0x14000f2da  add     rsp, 20h
0x14000f2de  pop     r15
0x14000f2e0  pop     r14
0x14000f2e2  pop     rdi
0x14000f2e3  pop     rsi
0x14000f2e4  pop     rbx
0x14000f2e5  retn
```
