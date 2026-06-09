# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180006bd8`
- end: `0x180006ccf`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180006fb0`
- `0x180007020`
- `0x1800070b0`

## callees

- `0x1800027a6`
- `0x1800065a4`
- `0x180006a98`
- `0x180006ae0`
- `0x180006bd8`

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
0x180006bd8  mov     [rsp+arg_0], rbx
0x180006bdd  mov     [rsp+arg_8], rsi
0x180006be2  push    rdi
0x180006be3  sub     rsp, 20h
0x180006be7  mov     rdi, r8
0x180006bea  mov     rsi, rdx
0x180006bed  mov     rbx, rcx
0x180006bf0  test    rdx, rdx
0x180006bf3  jz      short loc_180006C41
0x180006bf5  cmp     qword ptr [rcx+18h], 10h
0x180006bfa  jb      short loc_180006C01
0x180006bfc  mov     rax, [rcx]
0x180006bff  jmp     short loc_180006C04
0x180006c01  mov     rax, rbx
0x180006c04  cmp     rsi, rax
0x180006c07  jb      short loc_180006C41
0x180006c09  cmp     qword ptr [rcx+18h], 10h
0x180006c0e  jb      short loc_180006C13
0x180006c10  mov     rcx, [rcx]
0x180006c13  add     rcx, [rbx+10h]
0x180006c17  cmp     rcx, rsi
0x180006c1a  jbe     short loc_180006C41
0x180006c1c  cmp     qword ptr [rbx+18h], 10h
0x180006c21  jb      short loc_180006C28
0x180006c23  mov     rax, [rbx]
0x180006c26  jmp     short loc_180006C2B
0x180006c28  mov     rax, rbx
0x180006c2b  sub     rsi, rax
0x180006c2e  mov     r9, rdi
0x180006c31  mov     r8, rsi
0x180006c34  mov     rdx, rbx
0x180006c37  mov     rcx, rbx; void *
0x180006c3a  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180006c3f  jmp     short loc_180006CB6
0x180006c41  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180006c45  ja      short loc_180006CC6
0x180006c47  cmp     [rbx+18h], rdi
0x180006c4b  jnb     short loc_180006C6D
0x180006c4d  mov     r8, [rbx+10h]
0x180006c51  mov     rdx, rdi
0x180006c54  mov     rcx, rbx; Src
0x180006c57  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180006c5c  test    rdi, rdi
0x180006c5f  jz      short loc_180006CB3
0x180006c61  cmp     qword ptr [rbx+18h], 10h
0x180006c66  jb      short loc_180006C8E
0x180006c68  mov     rcx, [rbx]
0x180006c6b  jmp     short loc_180006C91
0x180006c6d  test    rdi, rdi
0x180006c70  jnz     short loc_180006C61
0x180006c72  cmp     qword ptr [rbx+18h], 10h
0x180006c77  jb      short loc_180006C7E
0x180006c79  mov     rax, [rbx]
0x180006c7c  jmp     short loc_180006C81
0x180006c7e  mov     rax, rbx
0x180006c81  mov     qword ptr [rbx+10h], 0
0x180006c89  mov     byte ptr [rax], 0
0x180006c8c  jmp     short loc_180006CB3
0x180006c8e  mov     rcx, rbx; void *
0x180006c91  mov     r8, rdi; Size
0x180006c94  mov     rdx, rsi; Src
0x180006c97  call    memcpy_0
0x180006c9c  cmp     qword ptr [rbx+18h], 10h
0x180006ca1  jb      short loc_180006CA8
0x180006ca3  mov     rax, [rbx]
0x180006ca6  jmp     short loc_180006CAB
0x180006ca8  mov     rax, rbx
0x180006cab  mov     [rbx+10h], rdi
0x180006caf  mov     byte ptr [rax+rdi], 0
0x180006cb3  mov     rax, rbx
0x180006cb6  mov     rbx, [rsp+28h+arg_0]
0x180006cbb  mov     rsi, [rsp+28h+arg_8]
0x180006cc0  add     rsp, 20h
0x180006cc4  pop     rdi
0x180006cc5  retn
0x180006cc6  mov     rcx, rbx
0x180006cc9  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
