# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,unsigned __int64,unsigned __int64)

- ea: `0x140001418`
- end: `0x140001508`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `240`
- prototype: `void **__fastcall(void **, void **, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140001510`

## callees

- `0x140001208`
- `0x140001390`
- `0x140001400`
- `0x140001418`
- `0x1400016f0`
- `0x140001eb6`

## pseudocode

```c
void **__fastcall std::string::assign(void **a1, void **a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rdi
  void **v6; // rsi
  void **v7; // rbx
  unsigned __int64 v8; // rdi
  void *v9; // rax
  void *v10; // rcx
  _BYTE *v11; // rax
  void **v12; // rax

  v4 = (unsigned __int64)a2[2];
  v6 = a2;
  v7 = a1;
  if ( v4 < a3 )
    goto LABEL_27;
  v8 = v4 - a3;
  if ( a4 < v8 )
    v8 = a4;
  if ( a1 == a2 )
  {
    v9 = (void *)(v8 + a3);
    if ( (unsigned __int64)a1[2] >= v8 + a3 )
    {
      if ( (unsigned __int64)a1[3] >= 0x10 )
        a1 = (void **)*a1;
      v7[2] = v9;
      *((_BYTE *)a1 + (_QWORD)v9) = 0;
      std::string::erase(v7, 0);
      return v7;
    }
LABEL_27:
    std::string::_Xran();
  }
  if ( v8 == -1 )
    std::string::_Xlen();
  if ( (unsigned __int64)a1[3] >= v8 )
  {
    if ( !v8 )
    {
      if ( (unsigned __int64)a1[3] < 0x10 )
        v11 = a1;
      else
        v11 = *a1;
      a1[2] = 0;
      *v11 = 0;
      return v7;
    }
  }
  else
  {
    std::string::_Copy((const void **)a1, v8, (size_t)a1[2]);
    if ( !v8 )
      return v7;
  }
  if ( (unsigned __int64)v6[3] >= 0x10 )
    v6 = (void **)*v6;
  if ( (unsigned __int64)v7[3] < 0x10 )
    v10 = v7;
  else
    v10 = *v7;
  memcpy_0(v10, (char *)v6 + a3, v8);
  if ( (unsigned __int64)v7[3] < 0x10 )
    v12 = v7;
  else
    v12 = (void **)*v7;
  v7[2] = (void *)v8;
  *((_BYTE *)v12 + v8) = 0;
  return v7;
}

```

## disassembly

```asm
0x140001418  push    rbx
0x14000141a  push    rbp
0x14000141b  push    rsi
0x14000141c  push    rdi
0x14000141d  sub     rsp, 28h
0x140001421  mov     rdi, [rdx+10h]
0x140001425  mov     rbp, r8
0x140001428  mov     rsi, rdx
0x14000142b  mov     rbx, rcx
0x14000142e  cmp     rdi, r8
0x140001431  jb      loc_1400014FC
0x140001437  sub     rdi, r8
0x14000143a  cmp     r9, rdi
0x14000143d  cmovb   rdi, r9
0x140001441  cmp     rcx, rdx
0x140001444  jnz     short loc_140001472
0x140001446  lea     rax, [rdi+r8]
0x14000144a  cmp     [rcx+10h], rax
0x14000144e  jb      loc_1400014FC
0x140001454  cmp     qword ptr [rcx+18h], 10h
0x140001459  jb      short loc_14000145E
0x14000145b  mov     rcx, [rcx]
0x14000145e  mov     [rbx+10h], rax
0x140001462  xor     edx, edx
0x140001464  mov     byte ptr [rax+rcx], 0
0x140001468  mov     rcx, rbx
0x14000146b  call    ?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_K0@Z; std::string::erase(unsigned __int64,unsigned __int64)
0x140001470  jmp     short loc_1400014F0
0x140001472  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x140001476  ja      loc_140001502
0x14000147c  cmp     [rcx+18h], rdi
0x140001480  jnb     short loc_1400014A9
0x140001482  mov     r8, [rcx+10h]
0x140001486  mov     rdx, rdi
0x140001489  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x14000148e  test    rdi, rdi
0x140001491  jz      short loc_1400014F0
0x140001493  cmp     qword ptr [rsi+18h], 10h
0x140001498  jb      short loc_14000149D
0x14000149a  mov     rsi, [rsi]
0x14000149d  cmp     qword ptr [rbx+18h], 10h
0x1400014a2  jb      short loc_1400014CA
0x1400014a4  mov     rcx, [rbx]
0x1400014a7  jmp     short loc_1400014CD
0x1400014a9  test    rdi, rdi
0x1400014ac  jnz     short loc_140001493
0x1400014ae  cmp     qword ptr [rcx+18h], 10h
0x1400014b3  jb      short loc_1400014BA
0x1400014b5  mov     rax, [rcx]
0x1400014b8  jmp     short loc_1400014BD
0x1400014ba  mov     rax, rbx
0x1400014bd  mov     qword ptr [rcx+10h], 0
0x1400014c5  mov     byte ptr [rax], 0
0x1400014c8  jmp     short loc_1400014F0
0x1400014ca  mov     rcx, rbx; void *
0x1400014cd  lea     rdx, [rsi+rbp]; Src
0x1400014d1  mov     r8, rdi; Size
0x1400014d4  call    memcpy_0
0x1400014d9  cmp     qword ptr [rbx+18h], 10h
0x1400014de  jb      short loc_1400014E5
0x1400014e0  mov     rax, [rbx]
0x1400014e3  jmp     short loc_1400014E8
0x1400014e5  mov     rax, rbx
0x1400014e8  mov     [rbx+10h], rdi
0x1400014ec  mov     byte ptr [rax+rdi], 0
0x1400014f0  mov     rax, rbx
0x1400014f3  add     rsp, 28h
0x1400014f7  pop     rdi
0x1400014f8  pop     rsi
0x1400014f9  pop     rbp
0x1400014fa  pop     rbx
0x1400014fb  retn
0x1400014fc  call    ?_Xran@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xran(void)
0x140001502  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
