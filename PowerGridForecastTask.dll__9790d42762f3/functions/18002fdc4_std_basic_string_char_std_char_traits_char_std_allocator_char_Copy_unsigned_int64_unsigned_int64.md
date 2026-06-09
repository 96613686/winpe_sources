# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18002fdc4`
- end: `0x18002feb4`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800067e0`
- `0x180008360`
- `0x18002ffc4`
- `0x1800300bc`
- `0x180034034`
- `0x180034120`
- `0x180034d18`

## callees

- `0x1800020c4`
- `0x1800022c8`
- `0x180026796`
- `0x18002fdc4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002fe82`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002fe82`

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
0x18002fdc4  mov     [rsp+arg_10], r8
0x18002fdc9  mov     [rsp+arg_8], rdx
0x18002fdce  mov     [rsp+arg_0], rcx
0x18002fdd3  push    rbx
0x18002fdd4  push    rsi
0x18002fdd5  push    rdi
0x18002fdd6  push    r14
0x18002fdd8  sub     rsp, 28h
0x18002fddc  mov     r14, r8
0x18002fddf  mov     rdi, rdx
0x18002fde2  mov     rbx, rcx
0x18002fde5  or      rdx, 0Fh
0x18002fde9  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18002fdf0  cmp     rdx, r9
0x18002fdf3  ja      short loc_18002FE29
0x18002fdf5  mov     rdi, rdx
0x18002fdf8  mov     r8, [rcx+18h]
0x18002fdfc  mov     rcx, r8
0x18002fdff  shr     rcx, 1
0x18002fe02  mov     rax, 0AAAAAAAAAAAAAAABh
0x18002fe0c  mul     rdx
0x18002fe0f  shr     rdx, 1
0x18002fe12  cmp     rcx, rdx
0x18002fe15  jbe     short loc_18002FE29
0x18002fe17  mov     rax, r9
0x18002fe1a  sub     rax, rcx
0x18002fe1d  cmp     r8, rax
0x18002fe20  lea     rdi, [rcx+r8]
0x18002fe24  jbe     short loc_18002FE29
0x18002fe26  mov     rdi, r9
0x18002fe29  lea     rcx, [rdi+1]; Size
0x18002fe2d  test    rcx, rcx
0x18002fe30  jz      short loc_18002FE41
0x18002fe32  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fe37  mov     rsi, rax
0x18002fe3a  test    rax, rax
0x18002fe3d  jz      short loc_18002FEAD
0x18002fe3f  jmp     short loc_18002FE43
0x18002fe41  xor     esi, esi
0x18002fe43  jmp     short loc_18002FE59
0x18002fe45  mov     rbx, [rsp+48h+arg_0]
0x18002fe4a  mov     r14, [rsp+48h+arg_10]
0x18002fe4f  mov     rdi, [rsp+48h+arg_8]
0x18002fe54  mov     rsi, [rsp+48h+arg_18]
0x18002fe59  test    r14, r14
0x18002fe5c  jz      short loc_18002FE78
0x18002fe5e  cmp     qword ptr [rbx+18h], 10h
0x18002fe63  jb      short loc_18002FE6A
0x18002fe65  mov     rdx, [rbx]
0x18002fe68  jmp     short loc_18002FE6D
0x18002fe6a  mov     rdx, rbx; Src
0x18002fe6d  mov     r8, r14; Size
0x18002fe70  mov     rcx, rsi; void *
0x18002fe73  call    memcpy_0
0x18002fe78  cmp     qword ptr [rbx+18h], 10h
0x18002fe7d  jb      short loc_18002FE88
0x18002fe7f  mov     rcx, [rbx]
0x18002fe82  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002fe88  lea     rax, [rbx+10h]
0x18002fe8c  mov     [rbx], rsi
0x18002fe8f  mov     [rbx+18h], rdi
0x18002fe93  cmp     rdi, 10h
0x18002fe97  cmovnb  rbx, rsi
0x18002fe9b  mov     [rax], r14
0x18002fe9e  mov     byte ptr [rbx+r14], 0
0x18002fea3  add     rsp, 28h
0x18002fea7  pop     r14
0x18002fea9  pop     rdi
0x18002feaa  pop     rsi
0x18002feab  pop     rbx
0x18002feac  retn
0x18002fead  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
