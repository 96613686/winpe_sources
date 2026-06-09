# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000c534`
- end: `0x18000c647`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `275`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `8`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000c6dc`
- `0x18000cde4`
- `0x18000cef4`
- `0x18000d3f8`
- `0x18001656c`
- `0x180016d68`
- `0x180016e68`
- `0x18001e334`

## callees

- `0x180001a30`
- `0x180001bd8`
- `0x180002326`
- `0x18000c534`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c613`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c613`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Copy(const void **Src, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // r14
  const void *v11; // rdx
  _QWORD *result; // rax
  void *v13; // rax
  unsigned __int64 v14; // rcx
  __int64 *v15; // rdx
  __int64 v16; // [rsp+0h] [rbp-48h] BYREF
  void *v20; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
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
      v15 = &v16;
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
    memcpy_0(v10, v11, 2 * v3);
  }
  if ( (unsigned __int64)v5[3] >= 8 )
    operator delete((void *)*v5);
  result = v5 + 2;
  *v5 = v10;
  v5[3] = (const void *)v4;
  if ( v4 >= 8 )
    v5 = (const void **)v10;
  *result = v3;
  *((_WORD *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x18000c534  mov     [rsp+arg_10], r8
0x18000c539  mov     [rsp+arg_8], rdx
0x18000c53e  mov     [rsp+arg_0], rcx
0x18000c543  push    rbx
0x18000c544  push    rsi
0x18000c545  push    rdi
0x18000c546  push    r14
0x18000c548  push    r15
0x18000c54a  sub     rsp, 20h
0x18000c54e  mov     r15, r8
0x18000c551  mov     rdi, rdx
0x18000c554  mov     rbx, rcx
0x18000c557  or      rdx, 7
0x18000c55b  mov     r9, 7FFFFFFFFFFFFFFEh
0x18000c565  cmp     rdx, r9
0x18000c568  ja      short loc_18000C59E
0x18000c56a  mov     rdi, rdx
0x18000c56d  mov     r8, [rcx+18h]
0x18000c571  mov     rcx, r8
0x18000c574  shr     rcx, 1
0x18000c577  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000c581  mul     rdx
0x18000c584  shr     rdx, 1
0x18000c587  cmp     rcx, rdx
0x18000c58a  jbe     short loc_18000C59E
0x18000c58c  mov     rax, r9
0x18000c58f  sub     rax, rcx
0x18000c592  cmp     r8, rax
0x18000c595  lea     rdi, [rcx+r8]
0x18000c599  jbe     short loc_18000C59E
0x18000c59b  mov     rdi, r9
0x18000c59e  lea     rcx, [rdi+1]
0x18000c5a2  xor     esi, esi
0x18000c5a4  test    rcx, rcx
0x18000c5a7  jz      short loc_18000C5CE
0x18000c5a9  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000c5b3  cmp     rcx, rax
0x18000c5b6  ja      loc_18000C640
0x18000c5bc  add     rcx, rcx; Size
0x18000c5bf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c5c4  mov     r14, rax
0x18000c5c7  test    rax, rax
0x18000c5ca  jz      short loc_18000C640
0x18000c5cc  jmp     short loc_18000C5D1
0x18000c5ce  mov     r14, rsi
0x18000c5d1  jmp     short loc_18000C5E9
0x18000c5d3  xor     esi, esi
0x18000c5d5  mov     rbx, [rsp+48h+arg_0]
0x18000c5da  mov     r15, [rsp+48h+arg_10]
0x18000c5df  mov     rdi, [rsp+48h+arg_8]
0x18000c5e4  mov     r14, [rsp+48h+arg_18]
0x18000c5e9  test    r15, r15
0x18000c5ec  jz      short loc_18000C609
0x18000c5ee  cmp     qword ptr [rbx+18h], 8
0x18000c5f3  jb      short loc_18000C5FA
0x18000c5f5  mov     rdx, [rbx]
0x18000c5f8  jmp     short loc_18000C5FD
0x18000c5fa  mov     rdx, rbx; Src
0x18000c5fd  lea     r8, [r15+r15]; Size
0x18000c601  mov     rcx, r14; void *
0x18000c604  call    memcpy_0
0x18000c609  cmp     qword ptr [rbx+18h], 8
0x18000c60e  jb      short loc_18000C619
0x18000c610  mov     rcx, [rbx]
0x18000c613  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c619  lea     rax, [rbx+10h]
0x18000c61d  mov     [rbx], r14
0x18000c620  mov     [rbx+18h], rdi
0x18000c624  cmp     rdi, 8
0x18000c628  cmovnb  rbx, r14
0x18000c62c  mov     [rax], r15
0x18000c62f  mov     [rbx+r15*2], si
0x18000c634  add     rsp, 20h
0x18000c638  pop     r15
0x18000c63a  pop     r14
0x18000c63c  pop     rdi
0x18000c63d  pop     rsi
0x18000c63e  pop     rbx
0x18000c63f  retn
0x18000c640  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
