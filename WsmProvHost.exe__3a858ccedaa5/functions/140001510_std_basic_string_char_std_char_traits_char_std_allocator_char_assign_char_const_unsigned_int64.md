# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x140001510`
- end: `0x140001607`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `void **__fastcall(_QWORD *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140001790`
- `0x140001800`
- `0x140001890`

## callees

- `0x140001208`
- `0x140001390`
- `0x140001418`
- `0x140001510`
- `0x140001eb6`

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
0x140001510  mov     [rsp+arg_0], rbx
0x140001515  mov     [rsp+arg_8], rsi
0x14000151a  push    rdi
0x14000151b  sub     rsp, 20h
0x14000151f  mov     rdi, r8
0x140001522  mov     rsi, rdx
0x140001525  mov     rbx, rcx
0x140001528  test    rdx, rdx
0x14000152b  jz      short loc_140001579
0x14000152d  cmp     qword ptr [rcx+18h], 10h
0x140001532  jb      short loc_140001539
0x140001534  mov     rax, [rcx]
0x140001537  jmp     short loc_14000153C
0x140001539  mov     rax, rbx
0x14000153c  cmp     rsi, rax
0x14000153f  jb      short loc_140001579
0x140001541  cmp     qword ptr [rcx+18h], 10h
0x140001546  jb      short loc_14000154B
0x140001548  mov     rcx, [rcx]
0x14000154b  add     rcx, [rbx+10h]
0x14000154f  cmp     rcx, rsi
0x140001552  jbe     short loc_140001579
0x140001554  cmp     qword ptr [rbx+18h], 10h
0x140001559  jb      short loc_140001560
0x14000155b  mov     rax, [rbx]
0x14000155e  jmp     short loc_140001563
0x140001560  mov     rax, rbx
0x140001563  sub     rsi, rax
0x140001566  mov     r9, rdi
0x140001569  mov     r8, rsi
0x14000156c  mov     rdx, rbx
0x14000156f  mov     rcx, rbx; void *
0x140001572  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x140001577  jmp     short loc_1400015EE
0x140001579  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x14000157d  ja      short loc_1400015FE
0x14000157f  cmp     [rbx+18h], rdi
0x140001583  jnb     short loc_1400015A5
0x140001585  mov     r8, [rbx+10h]
0x140001589  mov     rdx, rdi
0x14000158c  mov     rcx, rbx; Src
0x14000158f  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x140001594  test    rdi, rdi
0x140001597  jz      short loc_1400015EB
0x140001599  cmp     qword ptr [rbx+18h], 10h
0x14000159e  jb      short loc_1400015C6
0x1400015a0  mov     rcx, [rbx]
0x1400015a3  jmp     short loc_1400015C9
0x1400015a5  test    rdi, rdi
0x1400015a8  jnz     short loc_140001599
0x1400015aa  cmp     qword ptr [rbx+18h], 10h
0x1400015af  jb      short loc_1400015B6
0x1400015b1  mov     rax, [rbx]
0x1400015b4  jmp     short loc_1400015B9
0x1400015b6  mov     rax, rbx
0x1400015b9  mov     qword ptr [rbx+10h], 0
0x1400015c1  mov     byte ptr [rax], 0
0x1400015c4  jmp     short loc_1400015EB
0x1400015c6  mov     rcx, rbx; void *
0x1400015c9  mov     r8, rdi; Size
0x1400015cc  mov     rdx, rsi; Src
0x1400015cf  call    memcpy_0
0x1400015d4  cmp     qword ptr [rbx+18h], 10h
0x1400015d9  jb      short loc_1400015E0
0x1400015db  mov     rax, [rbx]
0x1400015de  jmp     short loc_1400015E3
0x1400015e0  mov     rax, rbx
0x1400015e3  mov     [rbx+10h], rdi
0x1400015e7  mov     byte ptr [rax+rdi], 0
0x1400015eb  mov     rax, rbx
0x1400015ee  mov     rbx, [rsp+28h+arg_0]
0x1400015f3  mov     rsi, [rsp+28h+arg_8]
0x1400015f8  add     rsp, 20h
0x1400015fc  pop     rdi
0x1400015fd  retn
0x1400015fe  mov     rcx, rbx
0x140001601  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
