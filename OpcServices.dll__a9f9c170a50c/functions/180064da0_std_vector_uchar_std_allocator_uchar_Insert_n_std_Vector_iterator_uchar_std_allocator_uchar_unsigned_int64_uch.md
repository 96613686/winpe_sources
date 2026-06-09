# std::vector<uchar,std::allocator<uchar>>::_Insert_n(std::_Vector_iterator<uchar,std::allocator<uchar>>,unsigned __int64,uchar const &)

- ea: `0x180064da0`
- end: `0x180065047`
- name: `?_Insert_n@?$vector@EV?$allocator@E@std@@@std@@IEAAXV?$_Vector_iterator@EV?$allocator@E@std@@@2@_KAEBE@Z`
- size: `679`
- prototype: ``
- caller_count: `13`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180050310`
- `0x180063964`
- `0x180064310`
- `0x180064768`
- `0x1800649a8`
- `0x180064a58`
- `0x180064b08`
- `0x180064be4`
- `0x180064c8c`
- `0x180064d20`
- `0x18010e694`
- `0x18010e960`
- `0x180111d1c`

## callees

- `0x180060268`
- `0x180064da0`
- `0x180091c7c`
- `0x1800b377c`
- `0x1800cce08`
- `0x1800cce54`
- `0x1800cd38c`
- `0x1800d5fe4`

## import_xrefs

- `msvcrt!memmove_s` at `0x180064eb3`
- `msvcrt!memmove_s` at `0x180064eda`
- `msvcrt!memmove_s` at `0x180064f69`
- `msvcrt!memmove_s` at `0x180064fc8`
- `msvcrt!memmove_s` at `0x180064eb3`
- `msvcrt!memmove_s` at `0x180064eda`
- `msvcrt!memmove_s` at `0x180064f69`
- `msvcrt!memmove_s` at `0x180064fc8`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180065023`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180065023`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall std::vector<unsigned char>::_Insert_n(__int64 a1, _BYTE *a2, rsize_t a3, _BYTE *a4)
{
  char *result; // rax
  char v8; // r12
  __int64 v9; // rdx
  unsigned __int64 v10; // r8
  void **v11; // r14
  unsigned __int64 v12; // rax
  char *v13; // rax
  size_t v14; // rdi
  char *v15; // rax
  char *v16; // rax
  size_t v17; // rcx
  char *v18; // rax
  char *v19; // r15
  _BYTE *v20; // r8
  rsize_t v21; // rdx
  char *v22; // r12
  _BYTE *v23; // rcx
  char *v24; // r15
  rsize_t v25; // rdx
  size_t v26; // rdi
  _BYTE *v27; // rcx
  size_t v28; // r8
  _QWORD pExceptionObject[3]; // [rsp+28h] [rbp-40h] BYREF
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h] BYREF
  const char *Val; // [rsp+70h] [rbp+8h] BYREF
  char *v32; // [rsp+80h] [rbp+18h] BYREF

  result = (char *)&retaddr;
  LOBYTE(Val) = *a4;
  v8 = (char)Val;
  LOBYTE(v32) = (_BYTE)Val;
  v9 = *(_QWORD *)(a1 + 8);
  if ( v9 )
    v10 = *(_QWORD *)(a1 + 24) - v9;
  else
    v10 = 0;
  if ( a3 )
  {
    v11 = (void **)(a1 + 16);
    if ( v9 )
      v12 = (unsigned __int64)*v11 - v9;
    else
      v12 = 0;
    if ( ~v12 < a3 )
      std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(a1);
    if ( v9 )
      v13 = (char *)*v11 - v9;
    else
      v13 = 0;
    if ( v10 >= (unsigned __int64)&v13[a3] )
    {
      v24 = (char *)*v11;
      v25 = (_BYTE *)*v11 - a2;
      if ( v25 >= a3 )
      {
        memmove_s(*v11, a3, &v24[-a3], a3);
        *v11 = &v24[a3];
        std::copy_backward<unsigned char *,unsigned char *>(a2);
        return (char *)std::fill<unsigned char *,unsigned char>(a2, &a2[a3], &v32);
      }
      else
      {
        if ( v25 )
          memmove_s(&a2[a3], v25, a2, (_BYTE *)*v11 - a2);
        v26 = &a2[a3] - (_BYTE *)*v11;
        if ( v26 )
        {
          LOBYTE(v25) = v8;
          memset_0(*v11, v25, v26);
        }
        v27 = *v11;
        *v11 = (char *)*v11 + a3;
        v28 = v27 - a2;
        result = 0;
        if ( a2 > v27 )
          v28 = 0;
        if ( v28 )
        {
          LOBYTE(v25) = v8;
          return (char *)memset_0(a2, v25, v28);
        }
      }
    }
    else
    {
      if ( ~(v10 >> 1) < v10 )
        v14 = 0;
      else
        v14 = (v10 >> 1) + v10;
      if ( v9 )
        v15 = (char *)*v11 - v9;
      else
        v15 = 0;
      if ( v14 < (unsigned __int64)&v15[a3] )
      {
        if ( v9 )
          v16 = (char *)*v11 - v9;
        else
          v16 = 0;
        v14 = (size_t)&v16[a3];
      }
      if ( v14 )
      {
        if ( !(0xFFFFFFFFFFFFFFFFuLL / v14) )
        {
          Val = 0;
          exception::exception((exception *)pExceptionObject, &Val);
          pExceptionObject[0] = &std::bad_alloc::`vftable';
          throw (std::bad_alloc *)pExceptionObject;
        }
        v17 = v14;
      }
      else
      {
        v17 = 0;
      }
      v18 = (char *)operator new(v17);
      v19 = v18;
      v32 = v18;
      v20 = *(_BYTE **)(a1 + 8);
      v21 = a2 - v20;
      v22 = &v18[a2 - v20];
      if ( a2 != v20 )
        memmove_s(v18, v21, v20, a2 - v20);
      LOBYTE(v21) = (_BYTE)Val;
      memset_0(v22, v21, a3);
      if ( *v11 != a2 )
        memmove_s(&v22[a3], (_BYTE *)*v11 - a2, a2, (_BYTE *)*v11 - a2);
      v23 = *(_BYTE **)(a1 + 8);
      if ( v23 )
      {
        a3 += (_BYTE *)*v11 - v23;
        operator delete(v23);
      }
      *(_QWORD *)(a1 + 24) = &v19[v14];
      result = &v19[a3];
      *v11 = &v19[a3];
      *(_QWORD *)(a1 + 8) = v19;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180064da0  mov     rax, rsp
0x180064da3  push    rdi
0x180064da4  push    r12
0x180064da6  push    r13
0x180064da8  push    r14
0x180064daa  push    r15
0x180064dac  sub     rsp, 40h
0x180064db0  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180064db8  mov     [rax+10h], rbx
0x180064dbc  mov     [rax+20h], rsi
0x180064dc0  mov     rsi, r8
0x180064dc3  mov     rbx, rdx
0x180064dc6  mov     r13, rcx
0x180064dc9  mov     r12b, [r9]
0x180064dcc  mov     [rax+8], r12b
0x180064dd0  mov     [rax+18h], r12b
0x180064dd4  mov     rdx, [rcx+8]
0x180064dd8  test    rdx, rdx
0x180064ddb  jz      loc_180064F41
0x180064de1  mov     r8, [rcx+18h]
0x180064de5  sub     r8, rdx
0x180064de8  test    rsi, rsi
0x180064deb  jz      loc_180064F0B
0x180064df1  lea     r14, [rcx+10h]
0x180064df5  test    rdx, rdx
0x180064df8  jz      loc_180064F25
0x180064dfe  mov     rax, [r14]
0x180064e01  sub     rax, rdx
0x180064e04  not     rax
0x180064e07  cmp     rax, rsi
0x180064e0a  jb      loc_180065003
0x180064e10  test    rdx, rdx
0x180064e13  jz      loc_180064F2C
0x180064e19  mov     rax, [r14]
0x180064e1c  sub     rax, rdx
0x180064e1f  add     rax, rsi
0x180064e22  cmp     r8, rax
0x180064e25  jnb     loc_180064F49
0x180064e2b  mov     rcx, r8
0x180064e2e  shr     rcx, 1
0x180064e31  mov     rax, rcx
0x180064e34  not     rax
0x180064e37  cmp     rax, r8
0x180064e3a  jb      loc_180064FFC
0x180064e40  lea     rdi, [rcx+r8]
0x180064e44  test    rdx, rdx
0x180064e47  jz      loc_180064F33
0x180064e4d  mov     rax, [r14]
0x180064e50  sub     rax, rdx
0x180064e53  add     rax, rsi
0x180064e56  cmp     rdi, rax
0x180064e59  jnb     short loc_180064E6E
0x180064e5b  test    rdx, rdx
0x180064e5e  jz      loc_180064F3A
0x180064e64  mov     rax, [r14]
0x180064e67  sub     rax, rdx
0x180064e6a  lea     rdi, [rax+rsi]
0x180064e6e  test    rdi, rdi
0x180064e71  jz      loc_180065009
0x180064e77  xor     edx, edx
0x180064e79  or      rax, 0FFFFFFFFFFFFFFFFh
0x180064e7d  div     rdi
0x180064e80  cmp     rax, 1
0x180064e84  jb      loc_180065010
0x180064e8a  mov     rcx, rdi; Size
0x180064e8d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180064e92  mov     r15, rax
0x180064e95  mov     [rsp+68h+arg_10], rax
0x180064e9d  mov     r8, [r13+8]; Source
0x180064ea1  mov     rdx, rbx
0x180064ea4  sub     rdx, r8; DestinationSize
0x180064ea7  lea     r12, [rdx+rax]
0x180064eab  jz      short loc_180064EB9
0x180064ead  mov     r9, rdx; SourceSize
0x180064eb0  mov     rcx, rax; Destination
0x180064eb3  call    cs:__imp_memmove_s
0x180064eb9  mov     r8, rsi; Size
0x180064ebc  mov     dl, byte ptr [rsp+68h+Val]; Val
0x180064ec0  mov     rcx, r12; void *
0x180064ec3  call    memset_0
0x180064ec8  mov     rdx, [r14]
0x180064ecb  sub     rdx, rbx; DestinationSize
0x180064ece  jz      short loc_180064EE1
0x180064ed0  lea     rcx, [r12+rsi]; Destination
0x180064ed4  mov     r9, rdx; SourceSize
0x180064ed7  mov     r8, rbx; Source
0x180064eda  call    cs:__imp_memmove_s
0x180064ee0  nop
0x180064ee1  mov     rcx, [r13+8]; Block
0x180064ee5  test    rcx, rcx
0x180064ee8  jz      short loc_180064EF8
0x180064eea  mov     rax, [r14]
0x180064eed  sub     rax, rcx
0x180064ef0  add     rsi, rax
0x180064ef3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180064ef8  lea     rax, [r15+rdi]
0x180064efc  mov     [r13+18h], rax
0x180064f00  lea     rax, [rsi+r15]
0x180064f04  mov     [r14], rax
0x180064f07  mov     [r13+8], r15
0x180064f0b  lea     r11, [rsp+68h+var_28]
0x180064f10  mov     rbx, [r11+38h]
0x180064f14  mov     rsi, [r11+48h]
0x180064f18  mov     rsp, r11
0x180064f1b  pop     r15
0x180064f1d  pop     r14
0x180064f1f  pop     r13
0x180064f21  pop     r12
0x180064f23  pop     rdi
0x180064f24  retn
0x180064f25  xor     eax, eax
0x180064f27  jmp     loc_180064E04
0x180064f2c  xor     eax, eax
0x180064f2e  jmp     loc_180064E1F
0x180064f33  xor     eax, eax
0x180064f35  jmp     loc_180064E53
0x180064f3a  xor     eax, eax
0x180064f3c  jmp     loc_180064E6A
0x180064f41  xor     r8d, r8d
0x180064f44  jmp     loc_180064DE8
0x180064f49  mov     r15, [r14]
0x180064f4c  mov     rdx, r15
0x180064f4f  sub     rdx, rbx; DestinationSize
0x180064f52  cmp     rdx, rsi
0x180064f55  jnb     short loc_180064FB6
0x180064f57  lea     rdi, [rbx+rsi]
0x180064f5b  test    rdx, rdx
0x180064f5e  jz      short loc_180064F70
0x180064f60  mov     r9, rdx; SourceSize
0x180064f63  mov     r8, rbx; Source
0x180064f66  mov     rcx, rdi; Destination
0x180064f69  call    cs:__imp_memmove_s
0x180064f6f  nop
0x180064f70  sub     rdi, [r14]
0x180064f73  jz      short loc_180064F84
0x180064f75  mov     r8, rdi; Size
0x180064f78  mov     dl, r12b; Val
0x180064f7b  mov     rcx, [r14]; void *
0x180064f7e  call    memset_0
0x180064f83  nop
0x180064f84  mov     rcx, [r14]
0x180064f87  lea     rax, [rcx+rsi]
0x180064f8b  mov     [r14], rax
0x180064f8e  mov     r8, rcx
0x180064f91  sub     r8, rbx
0x180064f94  xor     eax, eax
0x180064f96  cmp     rbx, rcx
0x180064f99  cmova   r8, rax; Size
0x180064f9d  test    r8, r8
0x180064fa0  jz      loc_180064F0B
0x180064fa6  mov     dl, r12b; Val
0x180064fa9  mov     rcx, rbx; void *
0x180064fac  call    memset_0
0x180064fb1  jmp     loc_180064F0B
0x180064fb6  mov     rdi, r15
0x180064fb9  sub     rdi, rsi
0x180064fbc  mov     r9, rsi; SourceSize
0x180064fbf  mov     r8, rdi; Source
0x180064fc2  mov     rdx, rsi; DestinationSize
0x180064fc5  mov     rcx, r15; Destination
0x180064fc8  call    cs:__imp_memmove_s
0x180064fce  lea     rax, [r15+rsi]
0x180064fd2  mov     [r14], rax
0x180064fd5  mov     r8, r15
0x180064fd8  mov     rdx, rdi
0x180064fdb  mov     rcx, rbx; Source
0x180064fde  call    ??$copy_backward@PEAEPEAE@std@@YAPEAEPEAE00@Z; std::copy_backward<uchar *,uchar *>(uchar *,uchar *,uchar *)
0x180064fe3  lea     rdx, [rbx+rsi]
0x180064fe7  lea     r8, [rsp+68h+arg_10]
0x180064fef  mov     rcx, rbx
0x180064ff2  call    ??$fill@PEAEE@std@@YAXPEAE0AEBE@Z; std::fill<uchar *,uchar>(uchar *,uchar *,uchar const &)
0x180064ff7  jmp     loc_180064F0B
0x180064ffc  xor     edi, edi
0x180064ffe  jmp     loc_180064E44
0x180065003  call    ?_Xlen@?$vector@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@V?$allocator@Viterator@?$list@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@VOpcRelationship@win_dox@@@std@@@2@@std@@@3@@std@@KAXXZ; std::vector<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator,std::allocator<std::list<std::pair<std::wstring const,win_dox::OpcRelationship>>::iterator>>::_Xlen(void)
0x180065009  xor     ecx, ecx
0x18006500b  jmp     loc_180064E8D
0x180065010  mov     [rsp+68h+Val], 0
0x180065019  lea     rdx, [rsp+68h+Val]
0x18006501e  lea     rcx, [rsp+68h+pExceptionObject]
0x180065023  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180065029  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180065030  mov     [rsp+68h+pExceptionObject], rax
0x180065035  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18006503c  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180065041  call    _CxxThrowException_0
```
