# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180001c10`
- end: `0x180001d07`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180001e90`
- `0x180001f00`
- `0x180001f90`

## callees

- `0x180001908`
- `0x180001a90`
- `0x180001b18`
- `0x180001c10`
- `0x180002706`

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
    std::string::_Xlen(v5);
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
0x180001c10  mov     [rsp+arg_0], rbx
0x180001c15  mov     [rsp+arg_8], rsi
0x180001c1a  push    rdi
0x180001c1b  sub     rsp, 20h
0x180001c1f  mov     rdi, r8
0x180001c22  mov     rsi, rdx
0x180001c25  mov     rbx, rcx
0x180001c28  test    rdx, rdx
0x180001c2b  jz      short loc_180001C79
0x180001c2d  cmp     qword ptr [rcx+18h], 10h
0x180001c32  jb      short loc_180001C39
0x180001c34  mov     rax, [rcx]
0x180001c37  jmp     short loc_180001C3C
0x180001c39  mov     rax, rbx
0x180001c3c  cmp     rsi, rax
0x180001c3f  jb      short loc_180001C79
0x180001c41  cmp     qword ptr [rcx+18h], 10h
0x180001c46  jb      short loc_180001C4B
0x180001c48  mov     rcx, [rcx]
0x180001c4b  add     rcx, [rbx+10h]
0x180001c4f  cmp     rcx, rsi
0x180001c52  jbe     short loc_180001C79
0x180001c54  cmp     qword ptr [rbx+18h], 10h
0x180001c59  jb      short loc_180001C60
0x180001c5b  mov     rax, [rbx]
0x180001c5e  jmp     short loc_180001C63
0x180001c60  mov     rax, rbx
0x180001c63  sub     rsi, rax
0x180001c66  mov     r9, rdi
0x180001c69  mov     r8, rsi
0x180001c6c  mov     rdx, rbx
0x180001c6f  mov     rcx, rbx; void *
0x180001c72  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180001c77  jmp     short loc_180001CEE
0x180001c79  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180001c7d  ja      short loc_180001CFE
0x180001c7f  cmp     [rbx+18h], rdi
0x180001c83  jnb     short loc_180001CA5
0x180001c85  mov     r8, [rbx+10h]
0x180001c89  mov     rdx, rdi
0x180001c8c  mov     rcx, rbx; Src
0x180001c8f  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180001c94  test    rdi, rdi
0x180001c97  jz      short loc_180001CEB
0x180001c99  cmp     qword ptr [rbx+18h], 10h
0x180001c9e  jb      short loc_180001CC6
0x180001ca0  mov     rcx, [rbx]
0x180001ca3  jmp     short loc_180001CC9
0x180001ca5  test    rdi, rdi
0x180001ca8  jnz     short loc_180001C99
0x180001caa  cmp     qword ptr [rbx+18h], 10h
0x180001caf  jb      short loc_180001CB6
0x180001cb1  mov     rax, [rbx]
0x180001cb4  jmp     short loc_180001CB9
0x180001cb6  mov     rax, rbx
0x180001cb9  mov     qword ptr [rbx+10h], 0
0x180001cc1  mov     byte ptr [rax], 0
0x180001cc4  jmp     short loc_180001CEB
0x180001cc6  mov     rcx, rbx; void *
0x180001cc9  mov     r8, rdi; Size
0x180001ccc  mov     rdx, rsi; Src
0x180001ccf  call    memcpy_0
0x180001cd4  cmp     qword ptr [rbx+18h], 10h
0x180001cd9  jb      short loc_180001CE0
0x180001cdb  mov     rax, [rbx]
0x180001cde  jmp     short loc_180001CE3
0x180001ce0  mov     rax, rbx
0x180001ce3  mov     [rbx+10h], rdi
0x180001ce7  mov     byte ptr [rax+rdi], 0
0x180001ceb  mov     rax, rbx
0x180001cee  mov     rbx, [rsp+28h+arg_0]
0x180001cf3  mov     rsi, [rsp+28h+arg_8]
0x180001cf8  add     rsp, 20h
0x180001cfc  pop     rdi
0x180001cfd  retn
0x180001cfe  mov     rcx, rbx
0x180001d01  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
