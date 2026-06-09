# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x1800084b8`
- end: `0x1800085af`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180008730`
- `0x1800087a0`
- `0x180008830`

## callees

- `0x180001ce6`
- `0x180008238`
- `0x180008390`
- `0x1800083c0`
- `0x1800084b8`

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
0x1800084b8  mov     [rsp+arg_0], rbx
0x1800084bd  mov     [rsp+arg_8], rsi
0x1800084c2  push    rdi
0x1800084c3  sub     rsp, 20h
0x1800084c7  mov     rdi, r8
0x1800084ca  mov     rsi, rdx
0x1800084cd  mov     rbx, rcx
0x1800084d0  test    rdx, rdx
0x1800084d3  jz      short loc_180008521
0x1800084d5  cmp     qword ptr [rcx+18h], 10h
0x1800084da  jb      short loc_1800084E1
0x1800084dc  mov     rax, [rcx]
0x1800084df  jmp     short loc_1800084E4
0x1800084e1  mov     rax, rbx
0x1800084e4  cmp     rsi, rax
0x1800084e7  jb      short loc_180008521
0x1800084e9  cmp     qword ptr [rcx+18h], 10h
0x1800084ee  jb      short loc_1800084F3
0x1800084f0  mov     rcx, [rcx]
0x1800084f3  add     rcx, [rbx+10h]
0x1800084f7  cmp     rcx, rsi
0x1800084fa  jbe     short loc_180008521
0x1800084fc  cmp     qword ptr [rbx+18h], 10h
0x180008501  jb      short loc_180008508
0x180008503  mov     rax, [rbx]
0x180008506  jmp     short loc_18000850B
0x180008508  mov     rax, rbx
0x18000850b  sub     rsi, rax
0x18000850e  mov     r9, rdi
0x180008511  mov     r8, rsi
0x180008514  mov     rdx, rbx
0x180008517  mov     rcx, rbx; void *
0x18000851a  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x18000851f  jmp     short loc_180008596
0x180008521  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180008525  ja      short loc_1800085A6
0x180008527  cmp     [rbx+18h], rdi
0x18000852b  jnb     short loc_18000854D
0x18000852d  mov     r8, [rbx+10h]
0x180008531  mov     rdx, rdi
0x180008534  mov     rcx, rbx; Src
0x180008537  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x18000853c  test    rdi, rdi
0x18000853f  jz      short loc_180008593
0x180008541  cmp     qword ptr [rbx+18h], 10h
0x180008546  jb      short loc_18000856E
0x180008548  mov     rcx, [rbx]
0x18000854b  jmp     short loc_180008571
0x18000854d  test    rdi, rdi
0x180008550  jnz     short loc_180008541
0x180008552  cmp     qword ptr [rbx+18h], 10h
0x180008557  jb      short loc_18000855E
0x180008559  mov     rax, [rbx]
0x18000855c  jmp     short loc_180008561
0x18000855e  mov     rax, rbx
0x180008561  mov     qword ptr [rbx+10h], 0
0x180008569  mov     byte ptr [rax], 0
0x18000856c  jmp     short loc_180008593
0x18000856e  mov     rcx, rbx; void *
0x180008571  mov     r8, rdi; Size
0x180008574  mov     rdx, rsi; Src
0x180008577  call    memcpy_0
0x18000857c  cmp     qword ptr [rbx+18h], 10h
0x180008581  jb      short loc_180008588
0x180008583  mov     rax, [rbx]
0x180008586  jmp     short loc_18000858B
0x180008588  mov     rax, rbx
0x18000858b  mov     [rbx+10h], rdi
0x18000858f  mov     byte ptr [rax+rdi], 0
0x180008593  mov     rax, rbx
0x180008596  mov     rbx, [rsp+28h+arg_0]
0x18000859b  mov     rsi, [rsp+28h+arg_8]
0x1800085a0  add     rsp, 20h
0x1800085a4  pop     rdi
0x1800085a5  retn
0x1800085a6  mov     rcx, rbx
0x1800085a9  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
