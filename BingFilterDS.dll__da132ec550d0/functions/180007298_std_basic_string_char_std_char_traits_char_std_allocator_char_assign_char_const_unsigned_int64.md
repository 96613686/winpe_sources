# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180007298`
- end: `0x18000738f`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800075e0`
- `0x180007650`
- `0x1800076e0`

## callees

- `0x180002766`
- `0x180006fec`
- `0x180007170`
- `0x1800071a0`
- `0x180007298`

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
0x180007298  mov     [rsp+arg_0], rbx
0x18000729d  mov     [rsp+arg_8], rsi
0x1800072a2  push    rdi
0x1800072a3  sub     rsp, 20h
0x1800072a7  mov     rdi, r8
0x1800072aa  mov     rsi, rdx
0x1800072ad  mov     rbx, rcx
0x1800072b0  test    rdx, rdx
0x1800072b3  jz      short loc_180007301
0x1800072b5  cmp     qword ptr [rcx+18h], 10h
0x1800072ba  jb      short loc_1800072C1
0x1800072bc  mov     rax, [rcx]
0x1800072bf  jmp     short loc_1800072C4
0x1800072c1  mov     rax, rbx
0x1800072c4  cmp     rsi, rax
0x1800072c7  jb      short loc_180007301
0x1800072c9  cmp     qword ptr [rcx+18h], 10h
0x1800072ce  jb      short loc_1800072D3
0x1800072d0  mov     rcx, [rcx]
0x1800072d3  add     rcx, [rbx+10h]
0x1800072d7  cmp     rcx, rsi
0x1800072da  jbe     short loc_180007301
0x1800072dc  cmp     qword ptr [rbx+18h], 10h
0x1800072e1  jb      short loc_1800072E8
0x1800072e3  mov     rax, [rbx]
0x1800072e6  jmp     short loc_1800072EB
0x1800072e8  mov     rax, rbx
0x1800072eb  sub     rsi, rax
0x1800072ee  mov     r9, rdi
0x1800072f1  mov     r8, rsi
0x1800072f4  mov     rdx, rbx
0x1800072f7  mov     rcx, rbx; void *
0x1800072fa  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x1800072ff  jmp     short loc_180007376
0x180007301  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180007305  ja      short loc_180007386
0x180007307  cmp     [rbx+18h], rdi
0x18000730b  jnb     short loc_18000732D
0x18000730d  mov     r8, [rbx+10h]
0x180007311  mov     rdx, rdi
0x180007314  mov     rcx, rbx; Src
0x180007317  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x18000731c  test    rdi, rdi
0x18000731f  jz      short loc_180007373
0x180007321  cmp     qword ptr [rbx+18h], 10h
0x180007326  jb      short loc_18000734E
0x180007328  mov     rcx, [rbx]
0x18000732b  jmp     short loc_180007351
0x18000732d  test    rdi, rdi
0x180007330  jnz     short loc_180007321
0x180007332  cmp     qword ptr [rbx+18h], 10h
0x180007337  jb      short loc_18000733E
0x180007339  mov     rax, [rbx]
0x18000733c  jmp     short loc_180007341
0x18000733e  mov     rax, rbx
0x180007341  mov     qword ptr [rbx+10h], 0
0x180007349  mov     byte ptr [rax], 0
0x18000734c  jmp     short loc_180007373
0x18000734e  mov     rcx, rbx; void *
0x180007351  mov     r8, rdi; Size
0x180007354  mov     rdx, rsi; Src
0x180007357  call    memcpy_0
0x18000735c  cmp     qword ptr [rbx+18h], 10h
0x180007361  jb      short loc_180007368
0x180007363  mov     rax, [rbx]
0x180007366  jmp     short loc_18000736B
0x180007368  mov     rax, rbx
0x18000736b  mov     [rbx+10h], rdi
0x18000736f  mov     byte ptr [rax+rdi], 0
0x180007373  mov     rax, rbx
0x180007376  mov     rbx, [rsp+28h+arg_0]
0x18000737b  mov     rsi, [rsp+28h+arg_8]
0x180007380  add     rsp, 20h
0x180007384  pop     rdi
0x180007385  retn
0x180007386  mov     rcx, rbx
0x180007389  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
