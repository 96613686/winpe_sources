# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x140006618`
- end: `0x140006708`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140008ab0`
- `0x140008ba8`

## callees

- `0x1400016e8`
- `0x1400017a0`
- `0x140003356`
- `0x140006618`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400066d6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400066d6`

## pseudocode

```c
size_t *__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // r14
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  void *v9; // rsi
  const void *v10; // rdx
  size_t *result; // rax
  void *v12; // rax
  __int64 *v13; // rdx
  __int64 v14; // [rsp+0h] [rbp-48h] BYREF
  void *v18; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  try
  {
    if ( v4 == -1 )
    {
      v9 = 0;
    }
    else
    {
      v9 = operator new(v4 + 1);
      if ( !v9 )
        std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    try
    {
      v12 = 0;
      if ( a2 != -1 )
      {
        v12 = operator new(a2 + 1);
        if ( !v12 )
          std::_Xbad_alloc();
      }
      v18 = v12;
    }
    catch ( ... )
    {
      v13 = &v14;
      LOBYTE(v13) = 1;
      std::string::_Tidy(Src, v13, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v9 = v18;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v10 = v5;
    else
      v10 = *v5;
    memcpy_0(v9, v10, v3);
  }
  if ( (unsigned __int64)v5[3] >= 0x10 )
    operator delete((void *)*v5);
  result = (size_t *)(v5 + 2);
  *v5 = v9;
  v5[3] = (const void *)v4;
  if ( v4 >= 0x10 )
    v5 = (const void **)v9;
  *result = v3;
  *((_BYTE *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x140006618  mov     [rsp+arg_10], r8
0x14000661d  mov     [rsp+arg_8], rdx
0x140006622  mov     [rsp+arg_0], rcx
0x140006627  push    rbx
0x140006628  push    rsi
0x140006629  push    rdi
0x14000662a  push    r14
0x14000662c  sub     rsp, 28h
0x140006630  mov     r14, r8
0x140006633  mov     rdi, rdx
0x140006636  mov     rbx, rcx
0x140006639  or      rdx, 0Fh
0x14000663d  mov     r9, 0FFFFFFFFFFFFFFFEh
0x140006644  cmp     rdx, r9
0x140006647  ja      short loc_14000667D
0x140006649  mov     rdi, rdx
0x14000664c  mov     r8, [rcx+18h]
0x140006650  mov     rcx, r8
0x140006653  shr     rcx, 1
0x140006656  mov     rax, 0AAAAAAAAAAAAAAABh
0x140006660  mul     rdx
0x140006663  shr     rdx, 1
0x140006666  cmp     rcx, rdx
0x140006669  jbe     short loc_14000667D
0x14000666b  mov     rax, r9
0x14000666e  sub     rax, rcx
0x140006671  cmp     r8, rax
0x140006674  lea     rdi, [rcx+r8]
0x140006678  jbe     short loc_14000667D
0x14000667a  mov     rdi, r9
0x14000667d  lea     rcx, [rdi+1]; Size
0x140006681  test    rcx, rcx
0x140006684  jz      short loc_140006695
0x140006686  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000668b  mov     rsi, rax
0x14000668e  test    rax, rax
0x140006691  jz      short loc_140006701
0x140006693  jmp     short loc_140006697
0x140006695  xor     esi, esi
0x140006697  jmp     short loc_1400066AD
0x140006699  mov     rbx, [rsp+48h+arg_0]
0x14000669e  mov     r14, [rsp+48h+arg_10]
0x1400066a3  mov     rdi, [rsp+48h+arg_8]
0x1400066a8  mov     rsi, [rsp+48h+arg_18]
0x1400066ad  test    r14, r14
0x1400066b0  jz      short loc_1400066CC
0x1400066b2  cmp     qword ptr [rbx+18h], 10h
0x1400066b7  jb      short loc_1400066BE
0x1400066b9  mov     rdx, [rbx]
0x1400066bc  jmp     short loc_1400066C1
0x1400066be  mov     rdx, rbx; Src
0x1400066c1  mov     r8, r14; Size
0x1400066c4  mov     rcx, rsi; void *
0x1400066c7  call    memcpy_0
0x1400066cc  cmp     qword ptr [rbx+18h], 10h
0x1400066d1  jb      short loc_1400066DC
0x1400066d3  mov     rcx, [rbx]
0x1400066d6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400066dc  lea     rax, [rbx+10h]
0x1400066e0  mov     [rbx], rsi
0x1400066e3  mov     [rbx+18h], rdi
0x1400066e7  cmp     rdi, 10h
0x1400066eb  cmovnb  rbx, rsi
0x1400066ef  mov     [rax], r14
0x1400066f2  mov     byte ptr [rbx+r14], 0
0x1400066f7  add     rsp, 28h
0x1400066fb  pop     r14
0x1400066fd  pop     rdi
0x1400066fe  pop     rsi
0x1400066ff  pop     rbx
0x140006700  retn
0x140006701  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
