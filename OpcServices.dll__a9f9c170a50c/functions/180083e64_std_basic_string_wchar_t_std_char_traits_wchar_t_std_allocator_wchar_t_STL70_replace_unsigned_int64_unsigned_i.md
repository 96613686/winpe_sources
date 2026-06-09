# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70>::replace(unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)

- ea: `0x180083e64`
- end: `0x1800840b3`
- name: `?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@_K0PEB_W0@Z`
- size: `591`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180039898`
- `0x180067550`
- `0x180083d94`

## callees

- `0x18001c5d0`
- `0x180083e64`
- `0x1800cdb60`
- `0x1800cdbbc`
- `0x1800de618`

## import_xrefs

- `msvcrt!memmove_s` at `0x180083f72`
- `msvcrt!memmove_s` at `0x180084079`
- `msvcrt!memmove_s` at `0x180083f72`
- `msvcrt!memmove_s` at `0x180084079`
- `msvcrt!memcpy_s` at `0x180083f96`
- `msvcrt!memcpy_s` at `0x180083f96`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        char *a4,
        unsigned __int64 a5)
{
  char *v5; // rbx
  unsigned __int64 v7; // rsi
  char *v10; // rax
  _QWORD *v11; // rcx
  unsigned __int64 v12; // r13
  unsigned __int64 v13; // rbp
  unsigned __int64 v14; // rdx
  _QWORD *v15; // rcx
  _QWORD *v16; // r8
  unsigned __int64 v17; // rdx
  _QWORD *v18; // rax
  unsigned __int64 v20; // rdx
  _QWORD *v21; // rcx
  _QWORD *v22; // r8

  v5 = (char *)(a1 + 1);
  v7 = a3;
  if ( a1[4] < 8u )
    v10 = (char *)(a1 + 1);
  else
    v10 = *(char **)v5;
  if ( a4 < v10 || (a1[4] < 8u ? (v11 = a1 + 1) : (v11 = *(_QWORD **)v5), (char *)v11 + 2 * a1[3] <= a4) )
  {
    if ( a1[3] < a2 )
      std::_String_base::_Xran();
    if ( a1[3] - a2 < a3 )
      v7 = a1[3] - a2;
    if ( ~a5 <= a1[3] - v7 )
      std::_String_base::_Xlen();
    v12 = a1[3] - a2 - v7;
    if ( a5 < v7 )
    {
      v20 = a1[4];
      if ( v20 < 8 )
      {
        v21 = v5;
        v22 = v5;
      }
      else
      {
        v21 = *(_QWORD **)v5;
        v22 = *(_QWORD **)v5;
      }
      memmove_s((char *)v21 + 2 * a2 + 2 * a5, 2 * (v20 - a2 - a5), (char *)v22 + 2 * a2 + 2 * v7, 2 * v12);
    }
    if ( !a5 && !v7 )
      return a1;
    v13 = a5 + a1[3] - v7;
    if ( v13 > 0x7FFFFFFFFFFFFFFELL )
      std::_String_base::_Xlen();
    if ( a1[4] < v13 )
    {
      std::wstring::_Copy(a1, a5 + a1[3] - v7, a1[3]);
      if ( !v13 )
        return a1;
    }
    else if ( !v13 )
    {
      if ( a1[4] >= 8u )
        v5 = *(char **)v5;
      a1[3] = 0;
      *(_WORD *)v5 = 0;
      return a1;
    }
    if ( v7 < a5 )
    {
      v14 = a1[4];
      if ( v14 < 8 )
      {
        v15 = v5;
        v16 = v5;
      }
      else
      {
        v15 = *(_QWORD **)v5;
        v16 = *(_QWORD **)v5;
      }
      memmove_s((char *)v15 + 2 * a2 + 2 * a5, 2 * (v14 - a2 - a5), (char *)v16 + 2 * a2 + 2 * v7, 2 * v12);
    }
    v17 = a1[4];
    if ( v17 < 8 )
      v18 = v5;
    else
      v18 = *(_QWORD **)v5;
    memcpy_s((char *)v18 + 2 * a2, 2 * (v17 - a2), a4, 2 * a5);
    if ( a1[4] >= 8u )
      v5 = *(char **)v5;
    a1[3] = v13;
    *(_WORD *)&v5[2 * v13] = 0;
    return a1;
  }
  if ( a1[4] >= 8u )
    v5 = *(char **)v5;
  return std::wstring::replace(a1, a2, a3, a1, (a4 - v5) >> 1, a5);
}

```

## disassembly

```asm
0x180083e64  push    rbx
0x180083e66  push    rbp
0x180083e67  push    rsi
0x180083e68  push    rdi
0x180083e69  push    r12
0x180083e6b  push    r13
0x180083e6d  push    r14
0x180083e6f  push    r15
0x180083e71  sub     rsp, 38h
0x180083e75  cmp     qword ptr [rcx+20h], 8
0x180083e7a  lea     rbx, [rcx+8]
0x180083e7e  mov     r12, r9
0x180083e81  mov     rsi, r8
0x180083e84  mov     r15, rdx
0x180083e87  mov     rdi, rcx
0x180083e8a  jb      loc_180083FDD
0x180083e90  mov     rax, [rbx]
0x180083e93  cmp     r12, rax
0x180083e96  jb      short loc_180083EB7
0x180083e98  cmp     qword ptr [rcx+20h], 8
0x180083e9d  jb      loc_180083FE5
0x180083ea3  mov     rcx, [rbx]
0x180083ea6  mov     rax, [rdi+18h]
0x180083eaa  lea     rcx, [rcx+rax*2]
0x180083eae  cmp     rcx, r12
0x180083eb1  ja      loc_180084016
0x180083eb7  cmp     [rdi+18h], r15
0x180083ebb  jb      loc_18008408C
0x180083ec1  mov     rcx, [rdi+18h]
0x180083ec5  mov     r14, [rsp+78h+arg_20]
0x180083ecd  mov     rax, rcx
0x180083ed0  sub     rax, r15
0x180083ed3  cmp     rax, rsi
0x180083ed6  cmovb   rsi, rax
0x180083eda  mov     rax, r14
0x180083edd  not     rax
0x180083ee0  sub     rcx, rsi
0x180083ee3  cmp     rax, rcx
0x180083ee6  jbe     loc_180084096
0x180083eec  mov     r13, [rdi+18h]
0x180083ef0  sub     r13, r15
0x180083ef3  sub     r13, rsi
0x180083ef6  cmp     r14, rsi
0x180083ef9  jb      loc_180084048
0x180083eff  test    r14, r14
0x180083f02  jz      loc_1800840A0
0x180083f08  mov     rbp, [rdi+18h]
0x180083f0c  mov     rax, 7FFFFFFFFFFFFFFEh
0x180083f16  sub     rbp, rsi
0x180083f19  add     rbp, r14
0x180083f1c  cmp     rbp, rax
0x180083f1f  ja      loc_1800840AE
0x180083f25  cmp     [rdi+20h], rbp
0x180083f29  jb      loc_180083FC4
0x180083f2f  test    rbp, rbp
0x180083f32  jz      loc_180083FFD
0x180083f38  cmp     rsi, r14
0x180083f3b  jnb     short loc_180083F78
0x180083f3d  mov     rdx, [rdi+20h]
0x180083f41  cmp     rdx, 8
0x180083f45  jb      loc_180083FF2
0x180083f4b  mov     rcx, [rbx]
0x180083f4e  mov     r8, rcx
0x180083f51  sub     rdx, r15
0x180083f54  lea     rax, [r15+rsi]
0x180083f58  lea     r8, [r8+rax*2]; Source
0x180083f5c  sub     rdx, r14
0x180083f5f  lea     rax, [r15+r14]
0x180083f63  add     rdx, rdx; DestinationSize
0x180083f66  lea     rcx, [rcx+rax*2]; Destination
0x180083f6a  lea     r9, ds:0[r13*2]; SourceSize
0x180083f72  call    cs:__imp_memmove_s
0x180083f78  mov     rdx, [rdi+20h]
0x180083f7c  cmp     rdx, 8
0x180083f80  jb      short loc_180083FED
0x180083f82  mov     rax, [rbx]
0x180083f85  sub     rdx, r15
0x180083f88  lea     r9, [r14+r14]; SourceSize
0x180083f8c  add     rdx, rdx; DestinationSize
0x180083f8f  lea     rcx, [rax+r15*2]; Destination
0x180083f93  mov     r8, r12; Source
0x180083f96  call    cs:__imp_memcpy_s
0x180083f9c  cmp     qword ptr [rdi+20h], 8
0x180083fa1  jb      short loc_180083FA6
0x180083fa3  mov     rbx, [rbx]
0x180083fa6  xor     eax, eax
0x180083fa8  mov     [rdi+18h], rbp
0x180083fac  mov     [rbx+rbp*2], ax
0x180083fb0  mov     rax, rdi
0x180083fb3  add     rsp, 38h
0x180083fb7  pop     r15
0x180083fb9  pop     r14
0x180083fbb  pop     r13
0x180083fbd  pop     r12
0x180083fbf  pop     rdi
0x180083fc0  pop     rsi
0x180083fc1  pop     rbp
0x180083fc2  pop     rbx
0x180083fc3  retn
0x180083fc4  mov     r8, [rdi+18h]
0x180083fc8  mov     rdx, rbp
0x180083fcb  mov     rcx, rdi
0x180083fce  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180083fd3  test    rbp, rbp
0x180083fd6  jz      short loc_180083FB0
0x180083fd8  jmp     loc_180083F38
0x180083fdd  mov     rax, rbx
0x180083fe0  jmp     loc_180083E93
0x180083fe5  mov     rcx, rbx
0x180083fe8  jmp     loc_180083EA6
0x180083fed  mov     rax, rbx
0x180083ff0  jmp     short loc_180083F85
0x180083ff2  mov     rcx, rbx
0x180083ff5  mov     r8, rbx
0x180083ff8  jmp     loc_180083F51
0x180083ffd  cmp     qword ptr [rdi+20h], 8
0x180084002  jb      short loc_180084007
0x180084004  mov     rbx, [rbx]
0x180084007  xor     eax, eax
0x180084009  mov     qword ptr [rdi+18h], 0
0x180084011  mov     [rbx], ax
0x180084014  jmp     short loc_180083FB0
0x180084016  cmp     qword ptr [rdi+20h], 8
0x18008401b  jb      short loc_180084020
0x18008401d  mov     rbx, [rbx]
0x180084020  mov     rax, [rsp+78h+arg_20]
0x180084028  sub     r12, rbx
0x18008402b  sar     r12, 1
0x18008402e  mov     r9, rdi
0x180084031  mov     [rsp+78h+var_50], rax
0x180084036  mov     rcx, rdi
0x180084039  mov     [rsp+78h+var_58], r12
0x18008403e  call    ?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@_K0AEBV12@00@Z; std::wstring::replace(unsigned __int64,unsigned __int64,std::wstring const &,unsigned __int64,unsigned __int64)
0x180084043  jmp     loc_180083FB3
0x180084048  mov     rdx, [rdi+20h]
0x18008404c  cmp     rdx, 8
0x180084050  jb      short loc_180084084
0x180084052  mov     rcx, [rbx]
0x180084055  mov     r8, rcx
0x180084058  sub     rdx, r15
0x18008405b  lea     rax, [r15+rsi]
0x18008405f  lea     r8, [r8+rax*2]; Source
0x180084063  sub     rdx, r14
0x180084066  lea     rax, [r15+r14]
0x18008406a  add     rdx, rdx; DestinationSize
0x18008406d  lea     rcx, [rcx+rax*2]; Destination
0x180084071  lea     r9, ds:0[r13*2]; SourceSize
0x180084079  call    cs:__imp_memmove_s
0x18008407f  jmp     loc_180083EFF
0x180084084  mov     rcx, rbx
0x180084087  mov     r8, rbx
0x18008408a  jmp     short loc_180084058
0x18008408c  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x180084091  jmp     loc_180083EC1
0x180084096  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x18008409b  jmp     loc_180083EEC
0x1800840a0  test    rsi, rsi
0x1800840a3  jz      loc_180083FB0
0x1800840a9  jmp     loc_180083F08
0x1800840ae  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
```
