# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x180002e98`
- end: `0x180003108`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `624`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003240`
- `0x18000633c`
- `0x1800065d0`

## callees

- `0x18000119c`
- `0x1800022f0`
- `0x180002e98`
- `0x180004328`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002fd9`
- `msvcrt!memcpy_s` at `0x180003015`
- `msvcrt!memcpy_s` at `0x180002fd9`
- `msvcrt!memcpy_s` at `0x180003015`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800030c0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800030ca`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800030c0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800030ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CExpansionVector::Add(
        ATL::CExpansionVector *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // r13
  const unsigned __int16 *v4; // r15
  ATL::CExpansionVector *v5; // r14
  __int64 v6; // rax
  unsigned __int64 v7; // rax
  void *v8; // r12
  __int64 v9; // rcx
  void *v10; // rbx
  errno_t v11; // eax
  errno_t v12; // eax
  unsigned int v13; // r15d
  void *v14; // rax
  void *v15; // rax
  __int64 v16; // rdx
  _QWORD *v17; // rcx
  _QWORD *v18; // rcx
  void *v19; // rdi
  void *v21; // [rsp+20h] [rbp-58h]
  rsize_t DestinationSize; // [rsp+28h] [rbp-50h]
  void *v24; // [rsp+30h] [rbp-48h]
  rsize_t SourceSize; // [rsp+38h] [rbp-40h]
  void *v36; // [rsp+98h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = this;
  if ( a2 && a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    SourceSize = 2 * v6 + 2;
    v7 = 2 * SourceSize;
    if ( !is_mul_ok(SourceSize, 2u) )
      v7 = -1;
    try
    {
      v8 = operator new[](v7);
      v36 = v8;
    }
    catch ( ... )
    {
      v5 = this;
      v3 = a3;
      v4 = a2;
      v8 = v36;
    }
    try
    {
      v19 = v8;
      v24 = v8;
      v9 = -1;
      do
        ++v9;
      while ( v3[v9] );
      DestinationSize = 2LL * ((int)v9 + 1);
      v10 = operator new[](saturated_mul(DestinationSize, 2u));
      v21 = v10;
    }
    catch ( ... )
    {
      v5 = this;
      v3 = a3;
      v4 = a2;
      v8 = v36;
      v19 = v24;
      v10 = v21;
    }
    if ( !v8 || !v10 )
      goto LABEL_28;
    v11 = memcpy_s(v8, SourceSize, v4, SourceSize);
    if ( v11 )
    {
      if ( v11 == 12 )
        goto LABEL_33;
      if ( v11 == 22 || v11 == 34 )
        goto LABEL_32;
      if ( v11 != 80 )
        goto LABEL_31;
    }
    v12 = memcpy_s(v10, DestinationSize, v3, DestinationSize);
    if ( !v12 )
    {
LABEL_21:
      v13 = 1;
      v14 = _recalloc(*(void **)v5, *((_DWORD *)v5 + 4) + 1, 8u);
      if ( v14 )
      {
        *(_QWORD *)v5 = v14;
        v15 = _recalloc(*((void **)v5 + 1), *((_DWORD *)v5 + 4) + 1, 8u);
        if ( v15 )
        {
          *((_QWORD *)v5 + 1) = v15;
          v16 = *((int *)v5 + 4);
          v17 = (_QWORD *)(*(_QWORD *)v5 + 8 * v16);
          if ( v17 )
            *v17 = v8;
          v18 = (_QWORD *)(*((_QWORD *)v5 + 1) + 8 * v16);
          if ( v18 )
            *v18 = v10;
          ++*((_DWORD *)v5 + 4);
          v19 = 0;
          v10 = 0;
          goto LABEL_29;
        }
      }
LABEL_28:
      v13 = 0;
LABEL_29:
      operator delete[](v10);
      operator delete[](v19);
      return v13;
    }
    if ( v12 != 12 )
    {
      if ( v12 != 22 && v12 != 34 )
      {
        if ( v12 == 80 )
          goto LABEL_21;
LABEL_31:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_32:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_33:
    ATL::AtlThrowImpl(-2147024882);
  }
  return 0;
}

```

## disassembly

```asm
0x180002e98  mov     [rsp+arg_10], r8
0x180002e9d  mov     [rsp+arg_8], rdx
0x180002ea2  mov     [rsp+arg_0], rcx
0x180002ea7  push    rbx
0x180002ea8  push    rsi
0x180002ea9  push    rdi
0x180002eaa  push    r12
0x180002eac  push    r13
0x180002eae  push    r14
0x180002eb0  push    r15
0x180002eb2  sub     rsp, 40h
0x180002eb6  mov     r13, r8
0x180002eb9  mov     r15, rdx
0x180002ebc  mov     r14, rcx
0x180002ebf  xor     esi, esi
0x180002ec1  test    rdx, rdx
0x180002ec4  jz      loc_1800030D5
0x180002eca  test    r8, r8
0x180002ecd  jz      loc_1800030D5
0x180002ed3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180002ed7  mov     rax, rbx
0x180002eda  inc     rax
0x180002edd  cmp     [rdx+rax*2], si
0x180002ee1  jnz     short loc_180002EDA
0x180002ee3  lea     rcx, ds:2[rax*2]
0x180002eeb  mov     [rsp+78h+SourceSize], rcx
0x180002ef0  mov     [rsp+78h+arg_18], rsi
0x180002ef8  mov     eax, 2
0x180002efd  mul     rcx
0x180002f00  cmovb   rax, rbx
0x180002f04  mov     rcx, rax; unsigned __int64
0x180002f07  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002f0c  mov     r12, rax
0x180002f0f  mov     [rsp+78h+arg_18], rax
0x180002f17  jmp     short loc_180002F3F
0x180002f19  xor     esi, esi
0x180002f1b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180002f1f  mov     r14, [rsp+78h+arg_0]
0x180002f27  mov     r13, [rsp+78h+arg_10]
0x180002f2f  mov     r15, [rsp+78h+arg_8]
0x180002f37  mov     r12, [rsp+78h+arg_18]
0x180002f3f  mov     rdi, r12
0x180002f42  mov     [rsp+78h+var_48], r12
0x180002f47  mov     rcx, rbx
0x180002f4a  inc     rcx
0x180002f4d  cmp     [r13+rcx*2+0], si
0x180002f53  jnz     short loc_180002F4A
0x180002f55  inc     ecx
0x180002f57  movsxd  rcx, ecx
0x180002f5a  add     rcx, rcx
0x180002f5d  mov     [rsp+78h+DestinationSize], rcx
0x180002f62  mov     [rsp+78h+var_58], rsi
0x180002f67  mov     eax, 2
0x180002f6c  mul     rcx
0x180002f6f  cmovb   rax, rbx
0x180002f73  mov     rcx, rax; unsigned __int64
0x180002f76  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002f7b  mov     rbx, rax
0x180002f7e  mov     [rsp+78h+var_58], rax
0x180002f83  jmp     short loc_180002FB1
0x180002f85  xor     esi, esi
0x180002f87  mov     r14, [rsp+78h+arg_0]
0x180002f8f  mov     r13, [rsp+78h+arg_10]
0x180002f97  mov     r15, [rsp+78h+arg_8]
0x180002f9f  mov     r12, [rsp+78h+arg_18]
0x180002fa7  mov     rdi, [rsp+78h+var_48]
0x180002fac  mov     rbx, [rsp+78h+var_58]
0x180002fb1  mov     [rsp+78h+arg_8], rbx
0x180002fb9  test    r12, r12
0x180002fbc  jz      loc_1800030BA
0x180002fc2  test    rbx, rbx
0x180002fc5  jz      loc_1800030BA
0x180002fcb  mov     rdx, [rsp+78h+SourceSize]; DestinationSize
0x180002fd0  mov     r9, rdx; SourceSize
0x180002fd3  mov     r8, r15; Source
0x180002fd6  mov     rcx, r12; Destination
0x180002fd9  call    cs:__imp_memcpy_s
0x180002fdf  test    eax, eax
0x180002fe1  jz      short loc_180003007
0x180002fe3  cmp     eax, 0Ch
0x180002fe6  jz      loc_1800030FD
0x180002fec  cmp     eax, 16h
0x180002fef  jz      loc_1800030F2
0x180002ff5  cmp     eax, 22h ; '"'
0x180002ff8  jz      loc_1800030F2
0x180002ffe  cmp     eax, 50h ; 'P'
0x180003001  jnz     loc_1800030E7
0x180003007  mov     r9, [rsp+78h+DestinationSize]; SourceSize
0x18000300c  mov     r8, r13; Source
0x18000300f  mov     rdx, r9; DestinationSize
0x180003012  mov     rcx, rbx; Destination
0x180003015  call    cs:__imp_memcpy_s
0x18000301b  test    eax, eax
0x18000301d  jz      short loc_180003043
0x18000301f  cmp     eax, 0Ch
0x180003022  jz      loc_1800030FD
0x180003028  cmp     eax, 16h
0x18000302b  jz      loc_1800030F2
0x180003031  cmp     eax, 22h ; '"'
0x180003034  jz      loc_1800030F2
0x18000303a  cmp     eax, 50h ; 'P'
0x18000303d  jnz     loc_1800030E7
0x180003043  mov     eax, [r14+10h]
0x180003047  mov     r15d, 1
0x18000304d  add     eax, r15d
0x180003050  movsxd  rdx, eax; Count
0x180003053  lea     r13d, [r15+7]
0x180003057  mov     r8d, r13d; Size
0x18000305a  mov     rcx, [r14]; Block
0x18000305d  call    cs:__imp__recalloc
0x180003063  test    rax, rax
0x180003066  jz      short loc_1800030BA
0x180003068  mov     [r14], rax
0x18000306b  mov     eax, [r14+10h]
0x18000306f  add     eax, r15d
0x180003072  movsxd  rdx, eax; Count
0x180003075  mov     r8d, r13d; Size
0x180003078  mov     rcx, [r14+8]; Block
0x18000307c  call    cs:__imp__recalloc
0x180003082  test    rax, rax
0x180003085  jz      short loc_1800030BA
0x180003087  mov     [r14+8], rax
0x18000308b  movsxd  rdx, dword ptr [r14+10h]
0x18000308f  mov     rax, [r14]
0x180003092  lea     rcx, [rax+rdx*8]
0x180003096  test    rcx, rcx
0x180003099  jz      short loc_18000309E
0x18000309b  mov     [rcx], r12
0x18000309e  mov     rax, [r14+8]
0x1800030a2  lea     rcx, [rax+rdx*8]
0x1800030a6  test    rcx, rcx
0x1800030a9  jz      short loc_1800030AE
0x1800030ab  mov     [rcx], rbx
0x1800030ae  add     [r14+10h], r15d
0x1800030b2  mov     rdi, rsi
0x1800030b5  mov     rbx, rsi
0x1800030b8  jmp     short loc_1800030BD
0x1800030ba  mov     r15d, esi
0x1800030bd  mov     rcx, rbx
0x1800030c0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800030c6  nop
0x1800030c7  mov     rcx, rdi
0x1800030ca  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800030d0  mov     eax, r15d
0x1800030d3  jmp     short loc_1800030D7
0x1800030d5  xor     eax, eax
0x1800030d7  add     rsp, 40h
0x1800030db  pop     r15
0x1800030dd  pop     r14
0x1800030df  pop     r13
0x1800030e1  pop     r12
0x1800030e3  pop     rdi
0x1800030e4  pop     rsi
0x1800030e5  pop     rbx
0x1800030e6  retn
0x1800030e7  mov     ecx, 80004005h; int
0x1800030ec  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800030f2  mov     ecx, 80070057h; int
0x1800030f7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800030fd  mov     ecx, 8007000Eh; int
0x180003102  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
