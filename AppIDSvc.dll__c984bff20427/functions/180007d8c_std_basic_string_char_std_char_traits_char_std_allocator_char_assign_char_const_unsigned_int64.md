# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180007d8c`
- end: `0x180007e83`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800082e0`
- `0x180008360`
- `0x1800083c0`

## callees

- `0x180001bb6`
- `0x1800078c8`
- `0x180007c4c`
- `0x180007c94`
- `0x180007d8c`

## pseudocode

```c
size_t *__fastcall std::string::assign(size_t *a1, char *Src, size_t Size)
{
  size_t *v5; // rbx
  char *v6; // rax
  void *v8; // rcx
  _BYTE *v9; // rax
  size_t v10; // rax

  v5 = a1;
  if ( Src )
  {
    v6 = a1[3] < 0x10 ? (char *)a1 : (char *)*a1;
    if ( Src >= v6 )
    {
      if ( a1[3] >= 0x10 )
        a1 = (size_t *)*a1;
      if ( (char *)a1 + v5[2] > Src )
        return (size_t *)std::string::assign(v5);
    }
  }
  if ( Size == -1 )
    std::wstring::_Xlen();
  if ( v5[3] >= Size )
  {
    if ( !Size )
    {
      if ( v5[3] < 0x10 )
        v9 = v5;
      else
        v9 = (_BYTE *)*v5;
      v5[2] = 0;
      *v9 = 0;
      return v5;
    }
    goto LABEL_13;
  }
  std::string::_Copy((const void **)v5, Size, v5[2]);
  if ( Size )
  {
LABEL_13:
    if ( v5[3] < 0x10 )
      v8 = v5;
    else
      v8 = (void *)*v5;
    memcpy_0(v8, Src, Size);
    if ( v5[3] < 0x10 )
      v10 = (size_t)v5;
    else
      v10 = *v5;
    v5[2] = Size;
    *(_BYTE *)(v10 + Size) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180007d8c  mov     [rsp+arg_0], rbx
0x180007d91  mov     [rsp+arg_8], rsi
0x180007d96  push    rdi
0x180007d97  sub     rsp, 20h
0x180007d9b  mov     rdi, r8
0x180007d9e  mov     rsi, rdx
0x180007da1  mov     rbx, rcx
0x180007da4  test    rdx, rdx
0x180007da7  jz      short loc_180007DF5
0x180007da9  cmp     qword ptr [rcx+18h], 10h
0x180007dae  jb      short loc_180007DB5
0x180007db0  mov     rax, [rcx]
0x180007db3  jmp     short loc_180007DB8
0x180007db5  mov     rax, rbx
0x180007db8  cmp     rsi, rax
0x180007dbb  jb      short loc_180007DF5
0x180007dbd  cmp     qword ptr [rcx+18h], 10h
0x180007dc2  jb      short loc_180007DC7
0x180007dc4  mov     rcx, [rcx]
0x180007dc7  add     rcx, [rbx+10h]
0x180007dcb  cmp     rcx, rsi
0x180007dce  jbe     short loc_180007DF5
0x180007dd0  cmp     qword ptr [rbx+18h], 10h
0x180007dd5  jb      short loc_180007DDC
0x180007dd7  mov     rax, [rbx]
0x180007dda  jmp     short loc_180007DDF
0x180007ddc  mov     rax, rbx
0x180007ddf  sub     rsi, rax
0x180007de2  mov     r9, rdi
0x180007de5  mov     r8, rsi
0x180007de8  mov     rdx, rbx
0x180007deb  mov     rcx, rbx; void *
0x180007dee  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180007df3  jmp     short loc_180007E6A
0x180007df5  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180007df9  ja      short loc_180007E7A
0x180007dfb  cmp     [rbx+18h], rdi
0x180007dff  jnb     short loc_180007E21
0x180007e01  mov     r8, [rbx+10h]
0x180007e05  mov     rdx, rdi
0x180007e08  mov     rcx, rbx; Src
0x180007e0b  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180007e10  test    rdi, rdi
0x180007e13  jz      short loc_180007E67
0x180007e15  cmp     qword ptr [rbx+18h], 10h
0x180007e1a  jb      short loc_180007E42
0x180007e1c  mov     rcx, [rbx]
0x180007e1f  jmp     short loc_180007E45
0x180007e21  test    rdi, rdi
0x180007e24  jnz     short loc_180007E15
0x180007e26  cmp     qword ptr [rbx+18h], 10h
0x180007e2b  jb      short loc_180007E32
0x180007e2d  mov     rax, [rbx]
0x180007e30  jmp     short loc_180007E35
0x180007e32  mov     rax, rbx
0x180007e35  mov     qword ptr [rbx+10h], 0
0x180007e3d  mov     byte ptr [rax], 0
0x180007e40  jmp     short loc_180007E67
0x180007e42  mov     rcx, rbx; void *
0x180007e45  mov     r8, rdi; Size
0x180007e48  mov     rdx, rsi; Src
0x180007e4b  call    memcpy_0
0x180007e50  cmp     qword ptr [rbx+18h], 10h
0x180007e55  jb      short loc_180007E5C
0x180007e57  mov     rax, [rbx]
0x180007e5a  jmp     short loc_180007E5F
0x180007e5c  mov     rax, rbx
0x180007e5f  mov     [rbx+10h], rdi
0x180007e63  mov     byte ptr [rax+rdi], 0
0x180007e67  mov     rax, rbx
0x180007e6a  mov     rbx, [rsp+28h+arg_0]
0x180007e6f  mov     rsi, [rsp+28h+arg_8]
0x180007e74  add     rsp, 20h
0x180007e78  pop     rdi
0x180007e79  retn
0x180007e7a  mov     rcx, rbx
0x180007e7d  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
