# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::insert(unsigned __int64,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,unsigned __int64,unsigned __int64)

- ea: `0x182dcbaf0`
- end: `0x182dcbc9d`
- name: `?insert@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KAEBV12@00@Z`
- size: `429`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x182dbf6f0`
- `0x182dcbca0`

## callees

- `0x1815cbc80`
- `0x1815cc2c0`
- `0x182dcbaf0`
- `0x182fd88b0`
- `0x1832dbedc`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x182dcbbd4`
- `VCRUNTIME140!memmove` at `0x182dcbc19`
- `VCRUNTIME140!memmove` at `0x182dcbbd4`
- `VCRUNTIME140!memmove` at `0x182dcbc19`

## pseudocode

```c
_QWORD *__fastcall std::string::insert(_QWORD *a1, unsigned __int64 a2, _QWORD *a3, size_t a4, unsigned __int64 a5)
{
  unsigned __int64 v7; // r8
  size_t v10; // rax
  unsigned __int64 v11; // rax
  size_t v12; // rdi
  size_t v13; // rbp
  unsigned __int64 v14; // rax
  _QWORD *v15; // rcx
  _QWORD *v16; // rax
  size_t v17; // r8
  unsigned __int64 v18; // rax
  size_t v19; // rdx
  _QWORD *v20; // rcx
  _QWORD *v21; // rax
  _QWORD *v22; // rax
  bool v23; // cf
  _QWORD *v24; // rax

  v7 = a1[2];
  if ( v7 < a2 )
    ((void (__noreturn *)(void))std::wstring::_Xran)();
  v10 = a3[2];
  if ( v10 < a4 )
    std::wstring::_Xran(a3);
  v11 = v10 - a4;
  v12 = a5;
  if ( a5 > v11 )
    v12 = v11;
  if ( ~v7 <= v12 )
    std::string::_Xlen();
  v13 = v7 + v12;
  if ( v12 )
  {
    if ( v13 == -1 )
      std::string::_Xlen();
    if ( a1[3] >= v13 )
    {
      if ( !v13 )
      {
        a1[2] = 0;
        if ( a1[3] < 0x10u )
          *(_BYTE *)a1 = 0;
        else
          *(_BYTE *)*a1 = 0;
        return a1;
      }
    }
    else
    {
      std::string::_Copy(a1);
      if ( !v13 )
        return a1;
    }
    v14 = a1[3];
    if ( v14 < 0x10 )
      v15 = a1;
    else
      v15 = (_QWORD *)*a1;
    if ( v14 < 0x10 )
      v16 = a1;
    else
      v16 = (_QWORD *)*a1;
    v17 = a1[2] - a2;
    if ( v17 )
      memmove((char *)v16 + a2 + v12, (char *)v15 + a2, v17);
    if ( a1 == a3 )
    {
      v18 = a1[3];
      v19 = a4 + v12;
      if ( a2 >= a4 )
        v19 = a4;
      if ( v18 < 0x10 )
        v20 = a1;
      else
        v20 = (_QWORD *)*a1;
      if ( v18 < 0x10 )
        v21 = a1;
      else
        v21 = (_QWORD *)*a1;
      memmove((char *)v21 + a2, (char *)v20 + v19, v12);
    }
    else
    {
      if ( a3[3] >= 0x10u )
        a3 = (_QWORD *)*a3;
      if ( a1[3] < 0x10u )
        v22 = a1;
      else
        v22 = (_QWORD *)*a1;
      memcpy_0((char *)v22 + a2, (char *)a3 + a4, v12);
    }
    v23 = a1[3] < 0x10u;
    a1[2] = v13;
    if ( v23 )
      v24 = a1;
    else
      v24 = (_QWORD *)*a1;
    *((_BYTE *)v24 + v13) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x182dcbaf0  mov     [rsp+arg_10], rbx
0x182dcbaf5  push    rsi
0x182dcbaf6  push    r14
0x182dcbaf8  push    r15
0x182dcbafa  sub     rsp, 20h
0x182dcbafe  mov     rsi, r8
0x182dcbb01  mov     r14, r9
0x182dcbb04  mov     r8, [rcx+10h]
0x182dcbb08  mov     r15, rdx
0x182dcbb0b  mov     rbx, rcx
0x182dcbb0e  cmp     r8, rdx
0x182dcbb11  jb      loc_182DCBC82
0x182dcbb17  mov     rax, [rsi+10h]
0x182dcbb1b  cmp     rax, r9
0x182dcbb1e  jb      loc_182DCBC88
0x182dcbb24  sub     rax, r9
0x182dcbb27  mov     [rsp+38h+arg_8], rdi
0x182dcbb2c  mov     rdi, [rsp+38h+arg_20]
0x182dcbb31  cmp     rdi, rax
0x182dcbb34  cmova   rdi, rax
0x182dcbb38  mov     rax, r8
0x182dcbb3b  not     rax
0x182dcbb3e  cmp     rax, rdi
0x182dcbb41  jbe     loc_182DCBC91
0x182dcbb47  mov     [rsp+38h+arg_0], rbp
0x182dcbb4c  lea     rbp, [r8+rdi]
0x182dcbb50  test    rdi, rdi
0x182dcbb53  jz      loc_182DCBC66
0x182dcbb59  cmp     rbp, 0FFFFFFFFFFFFFFFEh
0x182dcbb5d  ja      loc_182DCBC97
0x182dcbb63  cmp     [rcx+18h], rbp
0x182dcbb67  jnb     short loc_182DCBB89
0x182dcbb69  mov     rdx, rbp
0x182dcbb6c  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x182dcbb71  test    rbp, rbp
0x182dcbb74  jz      loc_182DCBC66
0x182dcbb7a  mov     rax, [rbx+18h]
0x182dcbb7e  cmp     rax, 10h
0x182dcbb82  jb      short loc_182DCBBAF
0x182dcbb84  mov     rcx, [rbx]
0x182dcbb87  jmp     short loc_182DCBBB2
0x182dcbb89  test    rbp, rbp
0x182dcbb8c  jnz     short loc_182DCBB7A
0x182dcbb8e  mov     [rcx+10h], rbp
0x182dcbb92  cmp     qword ptr [rcx+18h], 10h
0x182dcbb97  jb      short loc_182DCBBA4
0x182dcbb99  mov     rax, [rcx]
0x182dcbb9c  mov     [rax], bpl
0x182dcbb9f  jmp     loc_182DCBC66
0x182dcbba4  mov     rax, rbx
0x182dcbba7  mov     byte ptr [rbx], 0
0x182dcbbaa  jmp     loc_182DCBC66
0x182dcbbaf  mov     rcx, rbx
0x182dcbbb2  cmp     rax, 10h
0x182dcbbb6  jb      short loc_182DCBBBD
0x182dcbbb8  mov     rax, [rbx]
0x182dcbbbb  jmp     short loc_182DCBBC0
0x182dcbbbd  mov     rax, rbx
0x182dcbbc0  mov     r8, [rbx+10h]
0x182dcbbc4  sub     r8, r15; Size
0x182dcbbc7  jz      short loc_182DCBBDA
0x182dcbbc9  lea     rdx, [rcx+r15]; Src
0x182dcbbcd  lea     rcx, [rax+r15]
0x182dcbbd1  add     rcx, rdi; void *
0x182dcbbd4  call    cs:__imp_memmove
0x182dcbbda  cmp     rbx, rsi
0x182dcbbdd  jnz     short loc_182DCBC21
0x182dcbbdf  mov     rax, [rbx+18h]
0x182dcbbe3  lea     rdx, [r14+rdi]
0x182dcbbe7  cmp     r15, r14
0x182dcbbea  cmovnb  rdx, r14
0x182dcbbee  cmp     rax, 10h
0x182dcbbf2  jb      short loc_182DCBBF9
0x182dcbbf4  mov     rcx, [rbx]
0x182dcbbf7  jmp     short loc_182DCBBFC
0x182dcbbf9  mov     rcx, rbx
0x182dcbbfc  cmp     rax, 10h
0x182dcbc00  jb      short loc_182DCBC07
0x182dcbc02  mov     rax, [rbx]
0x182dcbc05  jmp     short loc_182DCBC0A
0x182dcbc07  mov     rax, rbx
0x182dcbc0a  test    rdi, rdi
0x182dcbc0d  jz      short loc_182DCBC4F
0x182dcbc0f  add     rdx, rcx; Src
0x182dcbc12  mov     r8, rdi; Size
0x182dcbc15  lea     rcx, [rax+r15]; void *
0x182dcbc19  call    cs:__imp_memmove
0x182dcbc1f  jmp     short loc_182DCBC4F
0x182dcbc21  cmp     qword ptr [rsi+18h], 10h
0x182dcbc26  jb      short loc_182DCBC2B
0x182dcbc28  mov     rsi, [rsi]
0x182dcbc2b  cmp     qword ptr [rbx+18h], 10h
0x182dcbc30  jb      short loc_182DCBC37
0x182dcbc32  mov     rax, [rbx]
0x182dcbc35  jmp     short loc_182DCBC3A
0x182dcbc37  mov     rax, rbx
0x182dcbc3a  test    rdi, rdi
0x182dcbc3d  jz      short loc_182DCBC4F
0x182dcbc3f  lea     rdx, [rsi+r14]; Src
0x182dcbc43  mov     r8, rdi; Size
0x182dcbc46  lea     rcx, [rax+r15]; void *
0x182dcbc4a  call    memcpy_0
0x182dcbc4f  cmp     qword ptr [rbx+18h], 10h
0x182dcbc54  mov     [rbx+10h], rbp
0x182dcbc58  jb      short loc_182DCBC5F
0x182dcbc5a  mov     rax, [rbx]
0x182dcbc5d  jmp     short loc_182DCBC62
0x182dcbc5f  mov     rax, rbx
0x182dcbc62  mov     byte ptr [rax+rbp], 0
0x182dcbc66  mov     rbp, [rsp+38h+arg_0]
0x182dcbc6b  mov     rax, rbx
0x182dcbc6e  mov     rbx, [rsp+38h+arg_10]
0x182dcbc73  mov     rdi, [rsp+38h+arg_8]
0x182dcbc78  add     rsp, 20h
0x182dcbc7c  pop     r15
0x182dcbc7e  pop     r14
0x182dcbc80  pop     rsi
0x182dcbc81  retn
0x182dcbc82  call    ?_Xran@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x182dcbc88  mov     rcx, rsi
0x182dcbc8b  call    ?_Xran@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x182dcbc91  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
0x182dcbc97  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
