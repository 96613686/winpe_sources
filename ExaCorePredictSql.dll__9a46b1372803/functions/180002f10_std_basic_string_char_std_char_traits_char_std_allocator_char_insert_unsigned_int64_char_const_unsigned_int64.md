# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::insert(unsigned __int64,char const *,unsigned __int64)

- ea: `0x180002f10`
- end: `0x18000307d`
- name: `?insert@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KPEBD0@Z`
- size: `365`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002bd0`

## callees

- `0x1800017a0`
- `0x180002f10`
- `0x180003080`
- `0x180003640`
- `0x180004acc`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x18000301d`
- `VCRUNTIME140!memmove` at `0x18000301d`

## pseudocode

```c
_QWORD *__fastcall std::string::insert(_QWORD *a1, __int64 a2, __int64 a3, size_t a4)
{
  unsigned __int64 v4; // rdx
  _QWORD *v6; // rbx
  const char *v7; // rax
  char *v8; // rax
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // rax
  const void *v12; // rdx
  _QWORD *v13; // rax
  size_t v14; // r8
  void *v15; // rcx
  bool v16; // cf
  _QWORD *v17; // rax

  v4 = a1[3];
  v6 = a1;
  if ( v4 < 0x10 )
    v7 = (const char *)a1;
  else
    v7 = (const char *)*a1;
  if ( "Bad blob size. The minimum valid size is " < v7 )
    goto LABEL_12;
  if ( v4 >= 0x10 )
    a1 = (_QWORD *)*a1;
  if ( (char *)a1 + v6[2] <= "Bad blob size. The minimum valid size is " )
  {
LABEL_12:
    if ( ~v6[2] <= a4 )
      std::string::_Xlen();
    v10 = v6[2] + a4;
    if ( !a4 )
      return v6;
    if ( v10 == -1 )
      std::string::_Xlen();
    if ( v4 >= v10 )
    {
      if ( v10 )
        goto LABEL_17;
      v6[2] = 0;
      if ( v4 < 0x10 )
        *(_BYTE *)v6 = 0;
      else
        *(_BYTE *)*v6 = 0;
    }
    else
    {
      std::string::_Copy(v6);
      if ( v10 )
      {
LABEL_17:
        v11 = v6[3];
        if ( v11 < 0x10 )
          v12 = v6;
        else
          v12 = (const void *)*v6;
        if ( v11 < 0x10 )
          v13 = v6;
        else
          v13 = (_QWORD *)*v6;
        v14 = v6[2];
        if ( v14 )
          memmove((char *)v13 + a4, v12, v14);
        if ( v6[3] < 0x10u )
          v15 = v6;
        else
          v15 = (void *)*v6;
        if ( a4 )
          memcpy_0(v15, "Bad blob size. The minimum valid size is ", a4);
        v16 = v6[3] < 0x10u;
        v6[2] = v10;
        if ( v16 )
          v17 = v6;
        else
          v17 = (_QWORD *)*v6;
        *((_BYTE *)v17 + v10) = 0;
      }
    }
    return v6;
  }
  if ( v4 < 0x10 )
    v8 = (char *)v6;
  else
    v8 = (char *)*v6;
  return std::string::insert(v6, v4, v6, "Bad blob size. The minimum valid size is " - v8, a4);
}

```

## disassembly

```asm
0x180002f10  mov     [rsp+arg_8], rbx
0x180002f15  mov     [rsp+arg_10], rbp
0x180002f1a  push    rsi
0x180002f1b  sub     rsp, 30h
0x180002f1f  mov     rdx, [rcx+18h]
0x180002f23  mov     rsi, r9
0x180002f26  mov     rbx, rcx
0x180002f29  cmp     rdx, 10h
0x180002f2d  jb      short loc_180002F34
0x180002f2f  mov     rax, [rcx]
0x180002f32  jmp     short loc_180002F37
0x180002f34  mov     rax, rbx
0x180002f37  lea     rbp, aBadBlobSizeThe; "Bad blob size. The minimum valid size i"...
0x180002f3e  cmp     rbp, rax
0x180002f41  jb      short loc_180002F89
0x180002f43  cmp     rdx, 10h
0x180002f47  jb      short loc_180002F4C
0x180002f49  mov     rcx, [rcx]
0x180002f4c  add     rcx, [rbx+10h]
0x180002f50  cmp     rcx, rbp
0x180002f53  jbe     short loc_180002F89
0x180002f55  cmp     rdx, 10h
0x180002f59  jb      short loc_180002F60
0x180002f5b  mov     rax, [rbx]
0x180002f5e  jmp     short loc_180002F63
0x180002f60  mov     rax, rbx
0x180002f63  sub     rbp, rax
0x180002f66  mov     [rsp+38h+var_18], rsi; __int64
0x180002f6b  mov     r9, rbp
0x180002f6e  mov     r8, rbx
0x180002f71  mov     rcx, rbx; void *
0x180002f74  call    ?insert@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KAEBV12@00@Z; std::string::insert(unsigned __int64,std::string const &,unsigned __int64,unsigned __int64)
0x180002f79  mov     rbx, [rsp+38h+arg_8]
0x180002f7e  mov     rbp, [rsp+38h+arg_10]
0x180002f83  add     rsp, 30h
0x180002f87  pop     rsi
0x180002f88  retn
0x180002f89  mov     r8, [rbx+10h]
0x180002f8d  mov     rax, r8
0x180002f90  not     rax
0x180002f93  cmp     rax, rsi
0x180002f96  jbe     loc_180003071
0x180002f9c  mov     [rsp+38h+arg_0], rdi
0x180002fa1  lea     rdi, [r8+r9]
0x180002fa5  test    rsi, rsi
0x180002fa8  jz      loc_180003059
0x180002fae  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180002fb2  ja      loc_180003077
0x180002fb8  cmp     rdx, rdi
0x180002fbb  jnb     short loc_180002FE0
0x180002fbd  mov     rdx, rdi
0x180002fc0  mov     rcx, rbx; Src
0x180002fc3  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180002fc8  test    rdi, rdi
0x180002fcb  jz      loc_180003059
0x180002fd1  mov     rax, [rbx+18h]
0x180002fd5  cmp     rax, 10h
0x180002fd9  jb      short loc_180002FFF
0x180002fdb  mov     rdx, [rbx]
0x180002fde  jmp     short loc_180003002
0x180002fe0  test    rdi, rdi
0x180002fe3  jnz     short loc_180002FD1
0x180002fe5  mov     [rbx+10h], rdi
0x180002fe9  cmp     rdx, 10h
0x180002fed  jb      short loc_180002FF7
0x180002fef  mov     rax, [rbx]
0x180002ff2  mov     [rax], dil
0x180002ff5  jmp     short loc_180003059
0x180002ff7  mov     rax, rbx
0x180002ffa  mov     byte ptr [rbx], 0
0x180002ffd  jmp     short loc_180003059
0x180002fff  mov     rdx, rbx; Src
0x180003002  cmp     rax, 10h
0x180003006  jb      short loc_18000300D
0x180003008  mov     rax, [rbx]
0x18000300b  jmp     short loc_180003010
0x18000300d  mov     rax, rbx
0x180003010  mov     r8, [rbx+10h]; Size
0x180003014  test    r8, r8
0x180003017  jz      short loc_180003023
0x180003019  lea     rcx, [rax+rsi]; void *
0x18000301d  call    cs:__imp_memmove
0x180003023  cmp     qword ptr [rbx+18h], 10h
0x180003028  jb      short loc_18000302F
0x18000302a  mov     rcx, [rbx]
0x18000302d  jmp     short loc_180003032
0x18000302f  mov     rcx, rbx; void *
0x180003032  test    rsi, rsi
0x180003035  jz      short loc_180003042
0x180003037  mov     r8, rsi; Size
0x18000303a  mov     rdx, rbp; Src
0x18000303d  call    memcpy_0
0x180003042  cmp     qword ptr [rbx+18h], 10h
0x180003047  mov     [rbx+10h], rdi
0x18000304b  jb      short loc_180003052
0x18000304d  mov     rax, [rbx]
0x180003050  jmp     short loc_180003055
0x180003052  mov     rax, rbx
0x180003055  mov     byte ptr [rax+rdi], 0
0x180003059  mov     rdi, [rsp+38h+arg_0]
0x18000305e  mov     rax, rbx
0x180003061  mov     rbx, [rsp+38h+arg_8]
0x180003066  mov     rbp, [rsp+38h+arg_10]
0x18000306b  add     rsp, 30h
0x18000306f  pop     rsi
0x180003070  retn
0x180003071  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
0x180003077  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
