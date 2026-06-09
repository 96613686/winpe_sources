# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x1800300bc`
- end: `0x1800301b3`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x1800068d0`
- `0x180007730`
- `0x180008210`
- `0x18001c924`
- `0x180021930`
- `0x180021980`
- `0x1800304d0`
- `0x180030540`
- `0x1800305d0`

## callees

- `0x180026796`
- `0x18002fdc4`
- `0x18002ff70`
- `0x18002ffc4`
- `0x1800300bc`

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
0x1800300bc  mov     [rsp+arg_0], rbx
0x1800300c1  mov     [rsp+arg_8], rsi
0x1800300c6  push    rdi
0x1800300c7  sub     rsp, 20h
0x1800300cb  mov     rdi, r8
0x1800300ce  mov     rsi, rdx
0x1800300d1  mov     rbx, rcx
0x1800300d4  test    rdx, rdx
0x1800300d7  jz      short loc_180030125
0x1800300d9  cmp     qword ptr [rcx+18h], 10h
0x1800300de  jb      short loc_1800300E5
0x1800300e0  mov     rax, [rcx]
0x1800300e3  jmp     short loc_1800300E8
0x1800300e5  mov     rax, rbx
0x1800300e8  cmp     rsi, rax
0x1800300eb  jb      short loc_180030125
0x1800300ed  cmp     qword ptr [rcx+18h], 10h
0x1800300f2  jb      short loc_1800300F7
0x1800300f4  mov     rcx, [rcx]
0x1800300f7  add     rcx, [rbx+10h]
0x1800300fb  cmp     rcx, rsi
0x1800300fe  jbe     short loc_180030125
0x180030100  cmp     qword ptr [rbx+18h], 10h
0x180030105  jb      short loc_18003010C
0x180030107  mov     rax, [rbx]
0x18003010a  jmp     short loc_18003010F
0x18003010c  mov     rax, rbx
0x18003010f  sub     rsi, rax
0x180030112  mov     r9, rdi
0x180030115  mov     r8, rsi
0x180030118  mov     rdx, rbx
0x18003011b  mov     rcx, rbx; void *
0x18003011e  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180030123  jmp     short loc_18003019A
0x180030125  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180030129  ja      short loc_1800301AA
0x18003012b  cmp     [rbx+18h], rdi
0x18003012f  jnb     short loc_180030151
0x180030131  mov     r8, [rbx+10h]
0x180030135  mov     rdx, rdi
0x180030138  mov     rcx, rbx; Src
0x18003013b  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180030140  test    rdi, rdi
0x180030143  jz      short loc_180030197
0x180030145  cmp     qword ptr [rbx+18h], 10h
0x18003014a  jb      short loc_180030172
0x18003014c  mov     rcx, [rbx]
0x18003014f  jmp     short loc_180030175
0x180030151  test    rdi, rdi
0x180030154  jnz     short loc_180030145
0x180030156  cmp     qword ptr [rbx+18h], 10h
0x18003015b  jb      short loc_180030162
0x18003015d  mov     rax, [rbx]
0x180030160  jmp     short loc_180030165
0x180030162  mov     rax, rbx
0x180030165  mov     qword ptr [rbx+10h], 0
0x18003016d  mov     byte ptr [rax], 0
0x180030170  jmp     short loc_180030197
0x180030172  mov     rcx, rbx; void *
0x180030175  mov     r8, rdi; Size
0x180030178  mov     rdx, rsi; Src
0x18003017b  call    memcpy_0
0x180030180  cmp     qword ptr [rbx+18h], 10h
0x180030185  jb      short loc_18003018C
0x180030187  mov     rax, [rbx]
0x18003018a  jmp     short loc_18003018F
0x18003018c  mov     rax, rbx
0x18003018f  mov     [rbx+10h], rdi
0x180030193  mov     byte ptr [rax+rdi], 0
0x180030197  mov     rax, rbx
0x18003019a  mov     rbx, [rsp+28h+arg_0]
0x18003019f  mov     rsi, [rsp+28h+arg_8]
0x1800301a4  add     rsp, 20h
0x1800301a8  pop     rdi
0x1800301a9  retn
0x1800301aa  mov     rcx, rbx
0x1800301ad  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
