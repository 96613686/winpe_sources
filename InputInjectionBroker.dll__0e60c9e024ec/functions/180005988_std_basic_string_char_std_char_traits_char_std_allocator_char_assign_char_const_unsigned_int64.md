# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180005988`
- end: `0x180005a7f`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180005cd0`
- `0x180005d40`
- `0x180005dd0`

## callees

- `0x180001ee6`
- `0x1800056dc`
- `0x180005860`
- `0x180005890`
- `0x180005988`

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
0x180005988  mov     [rsp+arg_0], rbx
0x18000598d  mov     [rsp+arg_8], rsi
0x180005992  push    rdi
0x180005993  sub     rsp, 20h
0x180005997  mov     rdi, r8
0x18000599a  mov     rsi, rdx
0x18000599d  mov     rbx, rcx
0x1800059a0  test    rdx, rdx
0x1800059a3  jz      short loc_1800059F1
0x1800059a5  cmp     qword ptr [rcx+18h], 10h
0x1800059aa  jb      short loc_1800059B1
0x1800059ac  mov     rax, [rcx]
0x1800059af  jmp     short loc_1800059B4
0x1800059b1  mov     rax, rbx
0x1800059b4  cmp     rsi, rax
0x1800059b7  jb      short loc_1800059F1
0x1800059b9  cmp     qword ptr [rcx+18h], 10h
0x1800059be  jb      short loc_1800059C3
0x1800059c0  mov     rcx, [rcx]
0x1800059c3  add     rcx, [rbx+10h]
0x1800059c7  cmp     rcx, rsi
0x1800059ca  jbe     short loc_1800059F1
0x1800059cc  cmp     qword ptr [rbx+18h], 10h
0x1800059d1  jb      short loc_1800059D8
0x1800059d3  mov     rax, [rbx]
0x1800059d6  jmp     short loc_1800059DB
0x1800059d8  mov     rax, rbx
0x1800059db  sub     rsi, rax
0x1800059de  mov     r9, rdi
0x1800059e1  mov     r8, rsi
0x1800059e4  mov     rdx, rbx
0x1800059e7  mov     rcx, rbx; void *
0x1800059ea  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x1800059ef  jmp     short loc_180005A66
0x1800059f1  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x1800059f5  ja      short loc_180005A76
0x1800059f7  cmp     [rbx+18h], rdi
0x1800059fb  jnb     short loc_180005A1D
0x1800059fd  mov     r8, [rbx+10h]
0x180005a01  mov     rdx, rdi
0x180005a04  mov     rcx, rbx; Src
0x180005a07  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180005a0c  test    rdi, rdi
0x180005a0f  jz      short loc_180005A63
0x180005a11  cmp     qword ptr [rbx+18h], 10h
0x180005a16  jb      short loc_180005A3E
0x180005a18  mov     rcx, [rbx]
0x180005a1b  jmp     short loc_180005A41
0x180005a1d  test    rdi, rdi
0x180005a20  jnz     short loc_180005A11
0x180005a22  cmp     qword ptr [rbx+18h], 10h
0x180005a27  jb      short loc_180005A2E
0x180005a29  mov     rax, [rbx]
0x180005a2c  jmp     short loc_180005A31
0x180005a2e  mov     rax, rbx
0x180005a31  mov     qword ptr [rbx+10h], 0
0x180005a39  mov     byte ptr [rax], 0
0x180005a3c  jmp     short loc_180005A63
0x180005a3e  mov     rcx, rbx; void *
0x180005a41  mov     r8, rdi; Size
0x180005a44  mov     rdx, rsi; Src
0x180005a47  call    memcpy_0
0x180005a4c  cmp     qword ptr [rbx+18h], 10h
0x180005a51  jb      short loc_180005A58
0x180005a53  mov     rax, [rbx]
0x180005a56  jmp     short loc_180005A5B
0x180005a58  mov     rax, rbx
0x180005a5b  mov     [rbx+10h], rdi
0x180005a5f  mov     byte ptr [rax+rdi], 0
0x180005a63  mov     rax, rbx
0x180005a66  mov     rbx, [rsp+28h+arg_0]
0x180005a6b  mov     rsi, [rsp+28h+arg_8]
0x180005a70  add     rsp, 20h
0x180005a74  pop     rdi
0x180005a75  retn
0x180005a76  mov     rcx, rbx
0x180005a79  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
