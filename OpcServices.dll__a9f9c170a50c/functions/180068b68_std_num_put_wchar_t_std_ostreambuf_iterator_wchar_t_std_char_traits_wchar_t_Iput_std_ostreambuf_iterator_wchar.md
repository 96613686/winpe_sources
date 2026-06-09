# std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t,std::char_traits<wchar_t>>>::_Iput(std::ostreambuf_iterator<wchar_t,std::char_traits<wchar_t>>,std::ios_base &,wchar_t,char *,unsigned __int64)

- ea: `0x180068b68`
- end: `0x180068e79`
- name: `?_Iput@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@2@V32@AEAVios_base@2@_WPEAD_K@Z`
- size: `785`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180068a40`
- `0x1800ddce0`
- `0x1800de0c0`
- `0x1800de170`
- `0x1800de230`

## callees

- `0x180065e20`
- `0x180067514`
- `0x180068b68`
- `0x180068e80`
- `0x180068ff4`
- `0x180069088`
- `0x180069110`
- `0x18008efcc`
- `0x1800cce54`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `msvcrt!memmove_s` at `0x180068db2`
- `msvcrt!memmove_s` at `0x180068db2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_OWORD *__fastcall std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Iput(
        __int64 a1,
        _OWORD *a2,
        __int128 *a3,
        __int64 a4,
        unsigned __int16 a5,
        _BYTE *a6,
        unsigned __int64 a7)
{
  __int64 v7; // r14
  _OWORD *v9; // rdi
  _BYTE *v10; // r12
  unsigned __int64 v11; // r15
  std::locale::facet *v12; // rbx
  __int64 v13; // rsi
  struct std::locale::facet *v14; // rax
  __int64 MultiByteStr; // rsi
  void **v16; // rax
  void **v17; // rax
  __int64 v18; // rbx
  __int64 v19; // rbx
  int v20; // eax
  __int128 v21; // xmm0
  unsigned __int16 v22; // si
  __int16 v23; // ax
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  void **v27; // rdi
  char v28; // al
  __int64 v29; // r14
  int v30; // ecx
  int v31[4]; // [rsp+40h] [rbp-71h] BYREF
  __int64 v32; // [rsp+50h] [rbp-61h] BYREF
  int v33[2]; // [rsp+58h] [rbp-59h] BYREF
  int v34[2]; // [rsp+68h] [rbp-49h]
  __int64 v35; // [rsp+70h] [rbp-41h]
  _BYTE v36[8]; // [rsp+78h] [rbp-39h] BYREF
  void *Block[3]; // [rsp+80h] [rbp-31h] BYREF
  unsigned __int64 v38; // [rsp+98h] [rbp-19h]

  v35 = -2;
  v7 = a4;
  *(_QWORD *)v31 = a4;
  v9 = a2;
  *(_QWORD *)v33 = a2;
  *(_QWORD *)v34 = a1;
  v10 = a6;
  v11 = a7;
  v12 = **(std::locale::facet ***)(a4 + 64);
  v32 = (__int64)v12;
  std::locale::facet::_Incref(v12);
  v13 = std::use_facet<std::numpunct<wchar_t>>((std::locale *)&v32);
  v32 = v13;
  if ( v12 )
  {
    v14 = std::locale::facet::_Decref(v12);
    if ( v14 )
      (**(void (__fastcall ***)(struct std::locale::facet *, __int64))v14)(v14, 1);
  }
  (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v13 + 24LL))(v13, v36);
  if ( ((*a6 - 43) & 0xFD) != 0 )
  {
    if ( *a6 != 48 || ((a6[1] - 88) & 0xDF) != 0 )
      MultiByteStr = 0;
    else
      MultiByteStr = 2;
  }
  else
  {
    MultiByteStr = 1;
  }
  v16 = Block;
  if ( v38 >= 0x10 )
    v16 = (void **)Block[0];
  if ( *(_BYTE *)v16 != 127 )
  {
    v17 = Block;
    if ( v38 >= 0x10 )
      v17 = (void **)Block[0];
    if ( *(char *)v17 > 0 )
    {
      v27 = Block;
      if ( v38 >= 0x10 )
        v27 = (void **)Block[0];
      v28 = *(_BYTE *)v27;
      if ( *(_BYTE *)v27 != 127 )
      {
        v29 = a7;
        do
        {
          if ( v28 <= 0 || v28 >= (unsigned __int64)(v29 - MultiByteStr) )
            break;
          v29 -= v28;
          memmove_s(&a6[v29 + 1], v11 - v29 + 1, &a6[v29], v11 - v29 + 1);
          a6[v29] = 0;
          ++v11;
          if ( *((char *)v27 + 1) > 0 )
            v27 = (void **)((char *)v27 + 1);
          v28 = *(_BYTE *)v27;
        }
        while ( *(_BYTE *)v27 != 127 );
        v7 = *(_QWORD *)v31;
      }
      v9 = *(_OWORD **)v33;
    }
  }
  v18 = *(_QWORD *)(v7 + 40);
  if ( v18 <= 0 || v18 <= v11 )
    v19 = 0;
  else
    v19 = v18 - v11;
  v20 = *(_DWORD *)(v7 + 24) & 0x1C0;
  if ( v20 == 64 )
  {
    v22 = a5;
  }
  else
  {
    v21 = *a3;
    if ( v20 == 256 )
    {
      *(_OWORD *)v31 = *a3;
      v10 = &a6[MultiByteStr];
      v11 -= MultiByteStr;
      *(_OWORD *)v31 = *(_OWORD *)std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Putc(
                                    v34[0],
                                    (int)v33,
                                    (int)v31,
                                    (int)a6,
                                    MultiByteStr);
      v22 = a5;
      *a3 = *(_OWORD *)std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Rep(
                         v30,
                         (unsigned int)v33,
                         (unsigned int)v31,
                         a5,
                         v19);
    }
    else
    {
      *(_OWORD *)v31 = *a3;
      v22 = a5;
      if ( v19 )
      {
        do
        {
          std::ostreambuf_iterator<wchar_t>::operator=(v31, a5);
          --v19;
        }
        while ( v19 );
        v21 = *(_OWORD *)v31;
      }
      *a3 = v21;
    }
    v19 = 0;
  }
  v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  *(_OWORD *)v31 = *a3;
  v24 = *(_OWORD *)std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Putgrouped(
                     *(_QWORD *)v34,
                     v33,
                     v31,
                     v10,
                     v11,
                     v23);
  *(_QWORD *)(v7 + 40) = 0;
  v25 = v24;
  *(_OWORD *)v31 = v24;
  if ( v19 )
  {
    do
    {
      std::ostreambuf_iterator<wchar_t>::operator=(v31, v22);
      --v19;
    }
    while ( v19 );
    v25 = *(_OWORD *)v31;
  }
  *v9 = v25;
  if ( v38 >= 0x10 )
    operator delete(Block[0]);
  return v9;
}

```

## disassembly

```asm
0x180068b68  push    rbp
0x180068b6a  push    rbx
0x180068b6b  push    rsi
0x180068b6c  push    rdi
0x180068b6d  push    r12
0x180068b6f  push    r13
0x180068b71  push    r14
0x180068b73  push    r15
0x180068b75  lea     rbp, [rsp-7]
0x180068b7a  sub     rsp, 0B8h
0x180068b81  mov     [rbp+3Fh+var_80], 0FFFFFFFFFFFFFFFEh
0x180068b89  mov     rax, cs:__security_cookie
0x180068b90  xor     rax, rsp
0x180068b93  mov     [rbp+3Fh+var_50], rax
0x180068b97  mov     r14, r9
0x180068b9a  mov     qword ptr [rbp+3Fh+var_B0], r9
0x180068b9e  mov     r13, r8
0x180068ba1  mov     rdi, rdx
0x180068ba4  mov     qword ptr [rbp+3Fh+var_98], rdx
0x180068ba8  mov     qword ptr [rbp+3Fh+var_88], rcx
0x180068bac  movzx   eax, [rbp+3Fh+arg_20]
0x180068bb0  mov     [rsp+0F0h+var_C0], ax
0x180068bb5  mov     r12, [rbp+3Fh+arg_28]
0x180068bb9  mov     r15, [rbp+3Fh+arg_30]
0x180068bbd  mov     rbx, [r9+40h]
0x180068bc1  mov     rbx, [rbx]
0x180068bc4  mov     [rbp+3Fh+var_A0], rbx
0x180068bc8  mov     rcx, rbx; this
0x180068bcb  call    ?_Incref@facet@locale@std@@QEAAXXZ; std::locale::facet::_Incref(void)
0x180068bd0  nop
0x180068bd1  lea     rcx, [rbp+3Fh+var_A0]; this
0x180068bd5  call    ??$use_facet@V?$numpunct@_W@std@@@std@@YAAEBV?$numpunct@_W@0@AEBVlocale@0@@Z; std::use_facet<std::numpunct<wchar_t>>(std::locale const &)
0x180068bda  mov     rsi, rax
0x180068bdd  mov     [rbp+3Fh+var_A0], rax
0x180068be1  test    rbx, rbx
0x180068be4  jz      short loc_180068BFA
0x180068be6  mov     rcx, rbx; this
0x180068be9  call    ?_Decref@facet@locale@std@@QEAAPEAV123@XZ; std::locale::facet::_Decref(void)
0x180068bee  mov     rcx, rax
0x180068bf1  test    rax, rax
0x180068bf4  jnz     loc_180068D5B
0x180068bfa  mov     rax, [rsi]
0x180068bfd  lea     rdx, [rbp+3Fh+var_78]
0x180068c01  mov     rcx, rsi
0x180068c04  mov     rax, [rax+18h]
0x180068c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068c0d  nop
0x180068c0e  mov     al, [r12]
0x180068c12  sub     al, 2Bh ; '+'
0x180068c14  test    al, 0FDh
0x180068c16  jz      loc_180068D47
0x180068c1c  cmp     byte ptr [r12], 30h ; '0'
0x180068c21  jz      loc_180068D23
0x180068c27  xor     esi, esi
0x180068c29  lea     rax, [rbp+3Fh+Block]
0x180068c2d  mov     rcx, [rbp+3Fh+Block]
0x180068c31  mov     rdx, [rbp+3Fh+var_58]
0x180068c35  cmp     rdx, 10h
0x180068c39  cmovnb  rax, rcx
0x180068c3d  cmp     byte ptr [rax], 7Fh
0x180068c40  jz      short loc_180068C57
0x180068c42  lea     rax, [rbp+3Fh+Block]
0x180068c46  cmp     rdx, 10h
0x180068c4a  cmovnb  rax, rcx
0x180068c4e  cmp     byte ptr [rax], 0
0x180068c51  jg      loc_180068D70
0x180068c57  mov     rbx, [r14+28h]
0x180068c5b  test    rbx, rbx
0x180068c5e  jg      loc_180068DDC
0x180068c64  xor     ebx, ebx
0x180068c66  mov     eax, [r14+18h]
0x180068c6a  and     eax, 1C0h
0x180068c6f  cmp     eax, 40h ; '@'
0x180068c72  jz      loc_180068D51
0x180068c78  movaps  xmm0, xmmword ptr [r13+0]
0x180068c7d  cmp     eax, 100h
0x180068c82  jz      loc_180068E08
0x180068c88  movaps  xmmword ptr [rbp+3Fh+var_B0], xmm0
0x180068c8c  movzx   esi, [rsp+0F0h+var_C0]
0x180068c91  test    rbx, rbx
0x180068c94  jnz     loc_180068DED
0x180068c9a  movdqa  xmmword ptr [r13+0], xmm0
0x180068ca0  xor     ebx, ebx
0x180068ca2  mov     rcx, [rbp+3Fh+var_A0]
0x180068ca6  mov     rax, [rcx]
0x180068ca9  mov     rax, [rax+10h]
0x180068cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068cb2  movaps  xmm0, xmmword ptr [r13+0]
0x180068cb7  movdqa  xmmword ptr [rbp+3Fh+var_B0], xmm0
0x180068cbc  mov     [rsp+0F0h+var_C8], ax
0x180068cc1  mov     qword ptr [rsp+0F0h+MultiByteStr], r15
0x180068cc6  mov     r9, r12
0x180068cc9  lea     r8, [rbp+3Fh+var_B0]
0x180068ccd  lea     rdx, [rbp+3Fh+var_98]
0x180068cd1  mov     rcx, qword ptr [rbp+3Fh+var_88]
0x180068cd5  call    ?_Putgrouped@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@2@V32@PEBD_K_W@Z; std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Putgrouped(std::ostreambuf_iterator<wchar_t>,char const *,unsigned __int64,wchar_t)
0x180068cda  movups  xmm0, xmmword ptr [rax]
0x180068cdd  mov     qword ptr [r14+28h], 0
0x180068ce5  movaps  xmm1, xmm0
0x180068ce8  movaps  xmmword ptr [rbp+3Fh+var_B0], xmm0
0x180068cec  test    rbx, rbx
0x180068cef  jnz     loc_180068E5D
0x180068cf5  movdqu  xmmword ptr [rdi], xmm1
0x180068cf9  cmp     [rbp+3Fh+var_58], 10h
0x180068cfe  jnb     short loc_180068D3C
0x180068d00  mov     rax, rdi
0x180068d03  mov     rcx, [rbp+3Fh+var_50]
0x180068d07  xor     rcx, rsp; StackCookie
0x180068d0a  call    __security_check_cookie
0x180068d0f  add     rsp, 0B8h
0x180068d16  pop     r15
0x180068d18  pop     r14
0x180068d1a  pop     r13
0x180068d1c  pop     r12
0x180068d1e  pop     rdi
0x180068d1f  pop     rsi
0x180068d20  pop     rbx
0x180068d21  pop     rbp
0x180068d22  retn
0x180068d23  mov     al, [r12+1]
0x180068d28  sub     al, 58h ; 'X'
0x180068d2a  test    al, 0DFh
0x180068d2c  jnz     loc_180068C27
0x180068d32  mov     esi, 2
0x180068d37  jmp     loc_180068C29
0x180068d3c  mov     rcx, [rbp+3Fh+Block]; Block
0x180068d40  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180068d45  jmp     short loc_180068D00
0x180068d47  mov     esi, 1
0x180068d4c  jmp     loc_180068C29
0x180068d51  movzx   esi, [rsp+0F0h+var_C0]
0x180068d56  jmp     loc_180068CA2
0x180068d5b  mov     rax, [rax]
0x180068d5e  mov     edx, 1
0x180068d63  mov     rax, [rax]
0x180068d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068d6b  jmp     loc_180068BFA
0x180068d70  lea     rdi, [rbp+3Fh+Block]
0x180068d74  cmp     rdx, 10h
0x180068d78  cmovnb  rdi, rcx
0x180068d7c  mov     al, [rdi]
0x180068d7e  cmp     al, 7Fh
0x180068d80  jz      short loc_180068DD3
0x180068d82  mov     r14, r15
0x180068d85  test    al, al
0x180068d87  jle     short loc_180068DCF
0x180068d89  movsx   rcx, al
0x180068d8d  mov     rax, r14
0x180068d90  sub     rax, rsi
0x180068d93  cmp     rcx, rax
0x180068d96  jnb     short loc_180068DCF
0x180068d98  sub     r14, rcx
0x180068d9b  mov     rdx, r15
0x180068d9e  sub     rdx, r14
0x180068da1  inc     rdx; DestinationSize
0x180068da4  lea     rbx, [r12+r14]
0x180068da8  lea     rcx, [rbx+1]; Destination
0x180068dac  mov     r9, rdx; SourceSize
0x180068daf  mov     r8, rbx; Source
0x180068db2  call    cs:__imp_memmove_s
0x180068db8  mov     byte ptr [rbx], 0
0x180068dbb  inc     r15
0x180068dbe  lea     rax, [rdi+1]
0x180068dc2  cmp     byte ptr [rax], 0
0x180068dc5  cmovg   rdi, rax
0x180068dc9  mov     al, [rdi]
0x180068dcb  cmp     al, 7Fh
0x180068dcd  jnz     short loc_180068D85
0x180068dcf  mov     r14, qword ptr [rbp+3Fh+var_B0]
0x180068dd3  mov     rdi, qword ptr [rbp+3Fh+var_98]
0x180068dd7  jmp     loc_180068C57
0x180068ddc  cmp     rbx, r15
0x180068ddf  jbe     loc_180068C64
0x180068de5  sub     rbx, r15
0x180068de8  jmp     loc_180068C66
0x180068ded  movzx   edx, si
0x180068df0  lea     rcx, [rbp+3Fh+var_B0]
0x180068df4  call    ??4?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_W@Z; std::ostreambuf_iterator<wchar_t>::operator=(wchar_t)
0x180068df9  sub     rbx, 1
0x180068dfd  jnz     short loc_180068DED
0x180068dff  movaps  xmm0, xmmword ptr [rbp+3Fh+var_B0]
0x180068e03  jmp     loc_180068C9A
0x180068e08  movdqa  xmmword ptr [rbp+3Fh+var_B0], xmm0
0x180068e0d  mov     qword ptr [rsp+0F0h+MultiByteStr], rsi; MultiByteStr
0x180068e12  mov     r9, r12; int
0x180068e15  lea     r8, [rbp+3Fh+var_B0]; int
0x180068e19  lea     rdx, [rbp+3Fh+var_98]; int
0x180068e1d  mov     rcx, qword ptr [rbp+3Fh+var_88]; int
0x180068e21  call    ?_Putc@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@2@V32@PEBD_K@Z; std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Putc(std::ostreambuf_iterator<wchar_t>,char const *,unsigned __int64)
0x180068e26  add     r12, rsi
0x180068e29  sub     r15, rsi
0x180068e2c  movups  xmm0, xmmword ptr [rax]
0x180068e2f  movdqu  xmmword ptr [rbp+3Fh+var_B0], xmm0
0x180068e34  mov     qword ptr [rsp+0F0h+MultiByteStr], rbx
0x180068e39  movzx   esi, [rsp+0F0h+var_C0]
0x180068e3e  movzx   r9d, si
0x180068e42  lea     r8, [rbp+3Fh+var_B0]
0x180068e46  lea     rdx, [rbp+3Fh+var_98]
0x180068e4a  call    ?_Rep@?$num_put@_WV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@@std@@AEBA?AV?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@2@V32@_W_K@Z; std::num_put<wchar_t,std::ostreambuf_iterator<wchar_t>>::_Rep(std::ostreambuf_iterator<wchar_t>,wchar_t,unsigned __int64)
0x180068e4f  movups  xmm0, xmmword ptr [rax]
0x180068e52  movdqu  xmmword ptr [r13+0], xmm0
0x180068e58  jmp     loc_180068CA0
0x180068e5d  movzx   edx, si
0x180068e60  lea     rcx, [rbp+3Fh+var_B0]
0x180068e64  call    ??4?$ostreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@_W@Z; std::ostreambuf_iterator<wchar_t>::operator=(wchar_t)
0x180068e69  sub     rbx, 1
0x180068e6d  jnz     short loc_180068E5D
0x180068e6f  movaps  xmm1, xmmword ptr [rbp+3Fh+var_B0]
0x180068e73  jmp     loc_180068CF5
```
