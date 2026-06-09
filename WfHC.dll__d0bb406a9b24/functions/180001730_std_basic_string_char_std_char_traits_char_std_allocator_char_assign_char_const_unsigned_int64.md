# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180001730`
- end: `0x180001827`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800019b0`
- `0x180001a20`
- `0x180001ab0`

## callees

- `0x180001428`
- `0x1800015b0`
- `0x180001638`
- `0x180001730`
- `0x180002576`

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
0x180001730  mov     [rsp+arg_0], rbx
0x180001735  mov     [rsp+arg_8], rsi
0x18000173a  push    rdi
0x18000173b  sub     rsp, 20h
0x18000173f  mov     rdi, r8
0x180001742  mov     rsi, rdx
0x180001745  mov     rbx, rcx
0x180001748  test    rdx, rdx
0x18000174b  jz      short loc_180001799
0x18000174d  cmp     qword ptr [rcx+18h], 10h
0x180001752  jb      short loc_180001759
0x180001754  mov     rax, [rcx]
0x180001757  jmp     short loc_18000175C
0x180001759  mov     rax, rbx
0x18000175c  cmp     rsi, rax
0x18000175f  jb      short loc_180001799
0x180001761  cmp     qword ptr [rcx+18h], 10h
0x180001766  jb      short loc_18000176B
0x180001768  mov     rcx, [rcx]
0x18000176b  add     rcx, [rbx+10h]
0x18000176f  cmp     rcx, rsi
0x180001772  jbe     short loc_180001799
0x180001774  cmp     qword ptr [rbx+18h], 10h
0x180001779  jb      short loc_180001780
0x18000177b  mov     rax, [rbx]
0x18000177e  jmp     short loc_180001783
0x180001780  mov     rax, rbx
0x180001783  sub     rsi, rax
0x180001786  mov     r9, rdi
0x180001789  mov     r8, rsi
0x18000178c  mov     rdx, rbx
0x18000178f  mov     rcx, rbx; void *
0x180001792  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180001797  jmp     short loc_18000180E
0x180001799  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x18000179d  ja      short loc_18000181E
0x18000179f  cmp     [rbx+18h], rdi
0x1800017a3  jnb     short loc_1800017C5
0x1800017a5  mov     r8, [rbx+10h]
0x1800017a9  mov     rdx, rdi
0x1800017ac  mov     rcx, rbx; Src
0x1800017af  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x1800017b4  test    rdi, rdi
0x1800017b7  jz      short loc_18000180B
0x1800017b9  cmp     qword ptr [rbx+18h], 10h
0x1800017be  jb      short loc_1800017E6
0x1800017c0  mov     rcx, [rbx]
0x1800017c3  jmp     short loc_1800017E9
0x1800017c5  test    rdi, rdi
0x1800017c8  jnz     short loc_1800017B9
0x1800017ca  cmp     qword ptr [rbx+18h], 10h
0x1800017cf  jb      short loc_1800017D6
0x1800017d1  mov     rax, [rbx]
0x1800017d4  jmp     short loc_1800017D9
0x1800017d6  mov     rax, rbx
0x1800017d9  mov     qword ptr [rbx+10h], 0
0x1800017e1  mov     byte ptr [rax], 0
0x1800017e4  jmp     short loc_18000180B
0x1800017e6  mov     rcx, rbx; void *
0x1800017e9  mov     r8, rdi; Size
0x1800017ec  mov     rdx, rsi; Src
0x1800017ef  call    memcpy_0
0x1800017f4  cmp     qword ptr [rbx+18h], 10h
0x1800017f9  jb      short loc_180001800
0x1800017fb  mov     rax, [rbx]
0x1800017fe  jmp     short loc_180001803
0x180001800  mov     rax, rbx
0x180001803  mov     [rbx+10h], rdi
0x180001807  mov     byte ptr [rax+rdi], 0
0x18000180b  mov     rax, rbx
0x18000180e  mov     rbx, [rsp+28h+arg_0]
0x180001813  mov     rsi, [rsp+28h+arg_8]
0x180001818  add     rsp, 20h
0x18000181c  pop     rdi
0x18000181d  retn
0x18000181e  mov     rcx, rbx
0x180001821  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
