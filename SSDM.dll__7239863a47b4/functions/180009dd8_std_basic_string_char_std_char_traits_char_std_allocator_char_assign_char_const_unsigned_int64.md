# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180009dd8`
- end: `0x180009ecf`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a120`
- `0x18000a190`
- `0x18000a220`

## callees

- `0x180002ed6`
- `0x180007564`
- `0x180009b70`
- `0x180009ce0`
- `0x180009dd8`

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
0x180009dd8  mov     [rsp+arg_0], rbx
0x180009ddd  mov     [rsp+arg_8], rsi
0x180009de2  push    rdi
0x180009de3  sub     rsp, 20h
0x180009de7  mov     rdi, r8
0x180009dea  mov     rsi, rdx
0x180009ded  mov     rbx, rcx
0x180009df0  test    rdx, rdx
0x180009df3  jz      short loc_180009E41
0x180009df5  cmp     qword ptr [rcx+18h], 10h
0x180009dfa  jb      short loc_180009E01
0x180009dfc  mov     rax, [rcx]
0x180009dff  jmp     short loc_180009E04
0x180009e01  mov     rax, rbx
0x180009e04  cmp     rsi, rax
0x180009e07  jb      short loc_180009E41
0x180009e09  cmp     qword ptr [rcx+18h], 10h
0x180009e0e  jb      short loc_180009E13
0x180009e10  mov     rcx, [rcx]
0x180009e13  add     rcx, [rbx+10h]
0x180009e17  cmp     rcx, rsi
0x180009e1a  jbe     short loc_180009E41
0x180009e1c  cmp     qword ptr [rbx+18h], 10h
0x180009e21  jb      short loc_180009E28
0x180009e23  mov     rax, [rbx]
0x180009e26  jmp     short loc_180009E2B
0x180009e28  mov     rax, rbx
0x180009e2b  sub     rsi, rax
0x180009e2e  mov     r9, rdi
0x180009e31  mov     r8, rsi
0x180009e34  mov     rdx, rbx
0x180009e37  mov     rcx, rbx; void *
0x180009e3a  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180009e3f  jmp     short loc_180009EB6
0x180009e41  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180009e45  ja      short loc_180009EC6
0x180009e47  cmp     [rbx+18h], rdi
0x180009e4b  jnb     short loc_180009E6D
0x180009e4d  mov     r8, [rbx+10h]
0x180009e51  mov     rdx, rdi
0x180009e54  mov     rcx, rbx; Src
0x180009e57  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180009e5c  test    rdi, rdi
0x180009e5f  jz      short loc_180009EB3
0x180009e61  cmp     qword ptr [rbx+18h], 10h
0x180009e66  jb      short loc_180009E8E
0x180009e68  mov     rcx, [rbx]
0x180009e6b  jmp     short loc_180009E91
0x180009e6d  test    rdi, rdi
0x180009e70  jnz     short loc_180009E61
0x180009e72  cmp     qword ptr [rbx+18h], 10h
0x180009e77  jb      short loc_180009E7E
0x180009e79  mov     rax, [rbx]
0x180009e7c  jmp     short loc_180009E81
0x180009e7e  mov     rax, rbx
0x180009e81  mov     qword ptr [rbx+10h], 0
0x180009e89  mov     byte ptr [rax], 0
0x180009e8c  jmp     short loc_180009EB3
0x180009e8e  mov     rcx, rbx; void *
0x180009e91  mov     r8, rdi; Size
0x180009e94  mov     rdx, rsi; Src
0x180009e97  call    memcpy_0
0x180009e9c  cmp     qword ptr [rbx+18h], 10h
0x180009ea1  jb      short loc_180009EA8
0x180009ea3  mov     rax, [rbx]
0x180009ea6  jmp     short loc_180009EAB
0x180009ea8  mov     rax, rbx
0x180009eab  mov     [rbx+10h], rdi
0x180009eaf  mov     byte ptr [rax+rdi], 0
0x180009eb3  mov     rax, rbx
0x180009eb6  mov     rbx, [rsp+28h+arg_0]
0x180009ebb  mov     rsi, [rsp+28h+arg_8]
0x180009ec0  add     rsp, 20h
0x180009ec4  pop     rdi
0x180009ec5  retn
0x180009ec6  mov     rcx, rbx
0x180009ec9  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
