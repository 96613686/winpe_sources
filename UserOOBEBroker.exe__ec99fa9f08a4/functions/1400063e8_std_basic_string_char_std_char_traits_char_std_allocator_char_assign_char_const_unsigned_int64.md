# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x1400063e8`
- end: `0x1400064df`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140006730`
- `0x1400067a0`
- `0x140006830`

## callees

- `0x140002656`
- `0x14000613c`
- `0x1400062c0`
- `0x1400062f0`
- `0x1400063e8`

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
0x1400063e8  mov     [rsp+arg_0], rbx
0x1400063ed  mov     [rsp+arg_8], rsi
0x1400063f2  push    rdi
0x1400063f3  sub     rsp, 20h
0x1400063f7  mov     rdi, r8
0x1400063fa  mov     rsi, rdx
0x1400063fd  mov     rbx, rcx
0x140006400  test    rdx, rdx
0x140006403  jz      short loc_140006451
0x140006405  cmp     qword ptr [rcx+18h], 10h
0x14000640a  jb      short loc_140006411
0x14000640c  mov     rax, [rcx]
0x14000640f  jmp     short loc_140006414
0x140006411  mov     rax, rbx
0x140006414  cmp     rsi, rax
0x140006417  jb      short loc_140006451
0x140006419  cmp     qword ptr [rcx+18h], 10h
0x14000641e  jb      short loc_140006423
0x140006420  mov     rcx, [rcx]
0x140006423  add     rcx, [rbx+10h]
0x140006427  cmp     rcx, rsi
0x14000642a  jbe     short loc_140006451
0x14000642c  cmp     qword ptr [rbx+18h], 10h
0x140006431  jb      short loc_140006438
0x140006433  mov     rax, [rbx]
0x140006436  jmp     short loc_14000643B
0x140006438  mov     rax, rbx
0x14000643b  sub     rsi, rax
0x14000643e  mov     r9, rdi
0x140006441  mov     r8, rsi
0x140006444  mov     rdx, rbx
0x140006447  mov     rcx, rbx; void *
0x14000644a  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x14000644f  jmp     short loc_1400064C6
0x140006451  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x140006455  ja      short loc_1400064D6
0x140006457  cmp     [rbx+18h], rdi
0x14000645b  jnb     short loc_14000647D
0x14000645d  mov     r8, [rbx+10h]
0x140006461  mov     rdx, rdi
0x140006464  mov     rcx, rbx; Src
0x140006467  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x14000646c  test    rdi, rdi
0x14000646f  jz      short loc_1400064C3
0x140006471  cmp     qword ptr [rbx+18h], 10h
0x140006476  jb      short loc_14000649E
0x140006478  mov     rcx, [rbx]
0x14000647b  jmp     short loc_1400064A1
0x14000647d  test    rdi, rdi
0x140006480  jnz     short loc_140006471
0x140006482  cmp     qword ptr [rbx+18h], 10h
0x140006487  jb      short loc_14000648E
0x140006489  mov     rax, [rbx]
0x14000648c  jmp     short loc_140006491
0x14000648e  mov     rax, rbx
0x140006491  mov     qword ptr [rbx+10h], 0
0x140006499  mov     byte ptr [rax], 0
0x14000649c  jmp     short loc_1400064C3
0x14000649e  mov     rcx, rbx; void *
0x1400064a1  mov     r8, rdi; Size
0x1400064a4  mov     rdx, rsi; Src
0x1400064a7  call    memcpy_0
0x1400064ac  cmp     qword ptr [rbx+18h], 10h
0x1400064b1  jb      short loc_1400064B8
0x1400064b3  mov     rax, [rbx]
0x1400064b6  jmp     short loc_1400064BB
0x1400064b8  mov     rax, rbx
0x1400064bb  mov     [rbx+10h], rdi
0x1400064bf  mov     byte ptr [rax+rdi], 0
0x1400064c3  mov     rax, rbx
0x1400064c6  mov     rbx, [rsp+28h+arg_0]
0x1400064cb  mov     rsi, [rsp+28h+arg_8]
0x1400064d0  add     rsp, 20h
0x1400064d4  pop     rdi
0x1400064d5  retn
0x1400064d6  mov     rcx, rbx
0x1400064d9  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
