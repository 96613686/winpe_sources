# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x140002020`
- end: `0x140002117`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `void **__fastcall(_QWORD *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400022a0`
- `0x140002310`
- `0x1400023a0`

## callees

- `0x140001d18`
- `0x140001ea0`
- `0x140001f28`
- `0x140002020`
- `0x140002516`

## pseudocode

```c
void **__fastcall std::string::assign(_QWORD *a1, char *Src, size_t Size)
{
  _QWORD *v5; // rbx
  char *v6; // rax
  _BYTE *v7; // rax
  void *v9; // rcx
  _BYTE *v10; // rax
  _BYTE *v11; // rax

  v5 = a1;
  if ( !Src )
    goto LABEL_13;
  v6 = a1[3] < 0x10u ? (char *)a1 : (char *)*a1;
  if ( Src < v6 )
    goto LABEL_13;
  if ( a1[3] >= 0x10u )
    a1 = (_QWORD *)*a1;
  if ( (char *)a1 + v5[2] <= Src )
  {
LABEL_13:
    if ( Size == -1 )
      std::string::_Xlen();
    if ( v5[3] >= Size )
    {
      if ( !Size )
      {
        if ( v5[3] < 0x10u )
          v10 = v5;
        else
          v10 = (_BYTE *)*v5;
        v5[2] = 0;
        *v10 = 0;
        return (void **)v5;
      }
    }
    else
    {
      std::string::_Copy((const void **)v5, Size, v5[2]);
      if ( !Size )
        return (void **)v5;
    }
    if ( v5[3] < 0x10u )
      v9 = v5;
    else
      v9 = (void *)*v5;
    memcpy_0(v9, Src, Size);
    if ( v5[3] < 0x10u )
      v11 = v5;
    else
      v11 = (_BYTE *)*v5;
    v5[2] = Size;
    v11[Size] = 0;
    return (void **)v5;
  }
  if ( v5[3] < 0x10u )
    v7 = v5;
  else
    v7 = (_BYTE *)*v5;
  return std::string::assign((void **)v5, (void **)v5, Src - v7, Size);
}

```

## disassembly

```asm
0x140002020  mov     [rsp+arg_0], rbx
0x140002025  mov     [rsp+arg_8], rsi
0x14000202a  push    rdi
0x14000202b  sub     rsp, 20h
0x14000202f  mov     rdi, r8
0x140002032  mov     rsi, rdx
0x140002035  mov     rbx, rcx
0x140002038  test    rdx, rdx
0x14000203b  jz      short loc_140002089
0x14000203d  cmp     qword ptr [rcx+18h], 10h
0x140002042  jb      short loc_140002049
0x140002044  mov     rax, [rcx]
0x140002047  jmp     short loc_14000204C
0x140002049  mov     rax, rbx
0x14000204c  cmp     rsi, rax
0x14000204f  jb      short loc_140002089
0x140002051  cmp     qword ptr [rcx+18h], 10h
0x140002056  jb      short loc_14000205B
0x140002058  mov     rcx, [rcx]
0x14000205b  add     rcx, [rbx+10h]
0x14000205f  cmp     rcx, rsi
0x140002062  jbe     short loc_140002089
0x140002064  cmp     qword ptr [rbx+18h], 10h
0x140002069  jb      short loc_140002070
0x14000206b  mov     rax, [rbx]
0x14000206e  jmp     short loc_140002073
0x140002070  mov     rax, rbx
0x140002073  sub     rsi, rax
0x140002076  mov     r9, rdi
0x140002079  mov     r8, rsi
0x14000207c  mov     rdx, rbx
0x14000207f  mov     rcx, rbx; void *
0x140002082  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x140002087  jmp     short loc_1400020FE
0x140002089  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x14000208d  ja      short loc_14000210E
0x14000208f  cmp     [rbx+18h], rdi
0x140002093  jnb     short loc_1400020B5
0x140002095  mov     r8, [rbx+10h]
0x140002099  mov     rdx, rdi
0x14000209c  mov     rcx, rbx; Src
0x14000209f  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x1400020a4  test    rdi, rdi
0x1400020a7  jz      short loc_1400020FB
0x1400020a9  cmp     qword ptr [rbx+18h], 10h
0x1400020ae  jb      short loc_1400020D6
0x1400020b0  mov     rcx, [rbx]
0x1400020b3  jmp     short loc_1400020D9
0x1400020b5  test    rdi, rdi
0x1400020b8  jnz     short loc_1400020A9
0x1400020ba  cmp     qword ptr [rbx+18h], 10h
0x1400020bf  jb      short loc_1400020C6
0x1400020c1  mov     rax, [rbx]
0x1400020c4  jmp     short loc_1400020C9
0x1400020c6  mov     rax, rbx
0x1400020c9  mov     qword ptr [rbx+10h], 0
0x1400020d1  mov     byte ptr [rax], 0
0x1400020d4  jmp     short loc_1400020FB
0x1400020d6  mov     rcx, rbx; void *
0x1400020d9  mov     r8, rdi; Size
0x1400020dc  mov     rdx, rsi; Src
0x1400020df  call    memcpy_0
0x1400020e4  cmp     qword ptr [rbx+18h], 10h
0x1400020e9  jb      short loc_1400020F0
0x1400020eb  mov     rax, [rbx]
0x1400020ee  jmp     short loc_1400020F3
0x1400020f0  mov     rax, rbx
0x1400020f3  mov     [rbx+10h], rdi
0x1400020f7  mov     byte ptr [rax+rdi], 0
0x1400020fb  mov     rax, rbx
0x1400020fe  mov     rbx, [rsp+28h+arg_0]
0x140002103  mov     rsi, [rsp+28h+arg_8]
0x140002108  add     rsp, 20h
0x14000210c  pop     rdi
0x14000210d  retn
0x14000210e  mov     rcx, rbx
0x140002111  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
