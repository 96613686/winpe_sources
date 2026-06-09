# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180001720`
- end: `0x180001817`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800019a0`
- `0x180001a10`
- `0x180001aa0`

## callees

- `0x180001418`
- `0x1800015a0`
- `0x180001628`
- `0x180001720`
- `0x180002596`

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
0x180001720  mov     [rsp+arg_0], rbx
0x180001725  mov     [rsp+arg_8], rsi
0x18000172a  push    rdi
0x18000172b  sub     rsp, 20h
0x18000172f  mov     rdi, r8
0x180001732  mov     rsi, rdx
0x180001735  mov     rbx, rcx
0x180001738  test    rdx, rdx
0x18000173b  jz      short loc_180001789
0x18000173d  cmp     qword ptr [rcx+18h], 10h
0x180001742  jb      short loc_180001749
0x180001744  mov     rax, [rcx]
0x180001747  jmp     short loc_18000174C
0x180001749  mov     rax, rbx
0x18000174c  cmp     rsi, rax
0x18000174f  jb      short loc_180001789
0x180001751  cmp     qword ptr [rcx+18h], 10h
0x180001756  jb      short loc_18000175B
0x180001758  mov     rcx, [rcx]
0x18000175b  add     rcx, [rbx+10h]
0x18000175f  cmp     rcx, rsi
0x180001762  jbe     short loc_180001789
0x180001764  cmp     qword ptr [rbx+18h], 10h
0x180001769  jb      short loc_180001770
0x18000176b  mov     rax, [rbx]
0x18000176e  jmp     short loc_180001773
0x180001770  mov     rax, rbx
0x180001773  sub     rsi, rax
0x180001776  mov     r9, rdi
0x180001779  mov     r8, rsi
0x18000177c  mov     rdx, rbx
0x18000177f  mov     rcx, rbx; void *
0x180001782  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180001787  jmp     short loc_1800017FE
0x180001789  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x18000178d  ja      short loc_18000180E
0x18000178f  cmp     [rbx+18h], rdi
0x180001793  jnb     short loc_1800017B5
0x180001795  mov     r8, [rbx+10h]
0x180001799  mov     rdx, rdi
0x18000179c  mov     rcx, rbx; Src
0x18000179f  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x1800017a4  test    rdi, rdi
0x1800017a7  jz      short loc_1800017FB
0x1800017a9  cmp     qword ptr [rbx+18h], 10h
0x1800017ae  jb      short loc_1800017D6
0x1800017b0  mov     rcx, [rbx]
0x1800017b3  jmp     short loc_1800017D9
0x1800017b5  test    rdi, rdi
0x1800017b8  jnz     short loc_1800017A9
0x1800017ba  cmp     qword ptr [rbx+18h], 10h
0x1800017bf  jb      short loc_1800017C6
0x1800017c1  mov     rax, [rbx]
0x1800017c4  jmp     short loc_1800017C9
0x1800017c6  mov     rax, rbx
0x1800017c9  mov     qword ptr [rbx+10h], 0
0x1800017d1  mov     byte ptr [rax], 0
0x1800017d4  jmp     short loc_1800017FB
0x1800017d6  mov     rcx, rbx; void *
0x1800017d9  mov     r8, rdi; Size
0x1800017dc  mov     rdx, rsi; Src
0x1800017df  call    memcpy_0
0x1800017e4  cmp     qword ptr [rbx+18h], 10h
0x1800017e9  jb      short loc_1800017F0
0x1800017eb  mov     rax, [rbx]
0x1800017ee  jmp     short loc_1800017F3
0x1800017f0  mov     rax, rbx
0x1800017f3  mov     [rbx+10h], rdi
0x1800017f7  mov     byte ptr [rax+rdi], 0
0x1800017fb  mov     rax, rbx
0x1800017fe  mov     rbx, [rsp+28h+arg_0]
0x180001803  mov     rsi, [rsp+28h+arg_8]
0x180001808  add     rsp, 20h
0x18000180c  pop     rdi
0x18000180d  retn
0x18000180e  mov     rcx, rbx
0x180001811  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
