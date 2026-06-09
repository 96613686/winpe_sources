# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x180003cb8`
- end: `0x180003f24`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `620`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180003fe0`
- `0x180008444`

## callees

- `0x180001e84`
- `0x1800022a0`
- `0x180003cb8`
- `0x180004768`
- `0x180008a78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180003e7b`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180003e9a`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180003e7b`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180003e9a`

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
  __int64 v14; // rax
  __int64 v15; // rax
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
      v14 = _o__recalloc(*(_QWORD *)v5, *((_DWORD *)v5 + 4) + 1, 8);
      if ( v14 )
      {
        *(_QWORD *)v5 = v14;
        v15 = _o__recalloc(*((_QWORD *)v5 + 1), *((_DWORD *)v5 + 4) + 1, 8);
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
      operator delete(v10);
      operator delete(v19);
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
0x180003cb8  mov     [rsp+arg_10], r8
0x180003cbd  mov     [rsp+arg_8], rdx
0x180003cc2  mov     [rsp+arg_0], rcx
0x180003cc7  push    rbx
0x180003cc8  push    rsi
0x180003cc9  push    rdi
0x180003cca  push    r12
0x180003ccc  push    r13
0x180003cce  push    r14
0x180003cd0  push    r15
0x180003cd2  sub     rsp, 40h
0x180003cd6  mov     r13, r8
0x180003cd9  mov     r15, rdx
0x180003cdc  mov     r14, rcx
0x180003cdf  xor     esi, esi
0x180003ce1  test    rdx, rdx
0x180003ce4  jz      loc_180003EF1
0x180003cea  test    r8, r8
0x180003ced  jz      loc_180003EF1
0x180003cf3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003cf7  mov     rax, rbx
0x180003cfa  inc     rax
0x180003cfd  cmp     [rdx+rax*2], si
0x180003d01  jnz     short loc_180003CFA
0x180003d03  lea     rcx, ds:2[rax*2]
0x180003d0b  mov     [rsp+78h+SourceSize], rcx
0x180003d10  mov     [rsp+78h+arg_18], rsi
0x180003d18  mov     eax, 2
0x180003d1d  mul     rcx
0x180003d20  cmovb   rax, rbx
0x180003d24  mov     rcx, rax; unsigned __int64
0x180003d27  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003d2c  mov     r12, rax
0x180003d2f  mov     [rsp+78h+arg_18], rax
0x180003d37  jmp     short loc_180003D5F
0x180003d39  xor     esi, esi
0x180003d3b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003d3f  mov     r14, [rsp+78h+arg_0]
0x180003d47  mov     r13, [rsp+78h+arg_10]
0x180003d4f  mov     r15, [rsp+78h+arg_8]
0x180003d57  mov     r12, [rsp+78h+arg_18]
0x180003d5f  mov     rdi, r12
0x180003d62  mov     [rsp+78h+var_48], r12
0x180003d67  mov     rcx, rbx
0x180003d6a  inc     rcx
0x180003d6d  cmp     [r13+rcx*2+0], si
0x180003d73  jnz     short loc_180003D6A
0x180003d75  inc     ecx
0x180003d77  movsxd  rcx, ecx
0x180003d7a  add     rcx, rcx
0x180003d7d  mov     [rsp+78h+DestinationSize], rcx
0x180003d82  mov     [rsp+78h+var_58], rsi
0x180003d87  mov     eax, 2
0x180003d8c  mul     rcx
0x180003d8f  cmovb   rax, rbx
0x180003d93  mov     rcx, rax; unsigned __int64
0x180003d96  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003d9b  mov     rbx, rax
0x180003d9e  mov     [rsp+78h+var_58], rax
0x180003da3  jmp     short loc_180003DD1
0x180003da5  xor     esi, esi
0x180003da7  mov     r14, [rsp+78h+arg_0]
0x180003daf  mov     r13, [rsp+78h+arg_10]
0x180003db7  mov     r15, [rsp+78h+arg_8]
0x180003dbf  mov     r12, [rsp+78h+arg_18]
0x180003dc7  mov     rdi, [rsp+78h+var_48]
0x180003dcc  mov     rbx, [rsp+78h+var_58]
0x180003dd1  mov     [rsp+78h+arg_8], rbx
0x180003dd9  test    r12, r12
0x180003ddc  jz      loc_180003ED8
0x180003de2  test    rbx, rbx
0x180003de5  jz      loc_180003ED8
0x180003deb  mov     rdx, [rsp+78h+SourceSize]; DestinationSize
0x180003df0  mov     r9, rdx; SourceSize
0x180003df3  mov     r8, r15; Source
0x180003df6  mov     rcx, r12; Destination
0x180003df9  call    memcpy_s
0x180003dfe  test    eax, eax
0x180003e00  jz      short loc_180003E26
0x180003e02  cmp     eax, 0Ch
0x180003e05  jz      loc_180003F19
0x180003e0b  cmp     eax, 16h
0x180003e0e  jz      loc_180003F0E
0x180003e14  cmp     eax, 22h ; '"'
0x180003e17  jz      loc_180003F0E
0x180003e1d  cmp     eax, 50h ; 'P'
0x180003e20  jnz     loc_180003F03
0x180003e26  mov     r9, [rsp+78h+DestinationSize]; SourceSize
0x180003e2b  mov     r8, r13; Source
0x180003e2e  mov     rdx, r9; DestinationSize
0x180003e31  mov     rcx, rbx; Destination
0x180003e34  call    memcpy_s
0x180003e39  test    eax, eax
0x180003e3b  jz      short loc_180003E61
0x180003e3d  cmp     eax, 0Ch
0x180003e40  jz      loc_180003F19
0x180003e46  cmp     eax, 16h
0x180003e49  jz      loc_180003F0E
0x180003e4f  cmp     eax, 22h ; '"'
0x180003e52  jz      loc_180003F0E
0x180003e58  cmp     eax, 50h ; 'P'
0x180003e5b  jnz     loc_180003F03
0x180003e61  mov     eax, [r14+10h]
0x180003e65  mov     r15d, 1
0x180003e6b  add     eax, r15d
0x180003e6e  movsxd  rdx, eax
0x180003e71  lea     r13d, [r15+7]
0x180003e75  mov     r8d, r13d
0x180003e78  mov     rcx, [r14]
0x180003e7b  call    cs:__imp__o__recalloc
0x180003e81  test    rax, rax
0x180003e84  jz      short loc_180003ED8
0x180003e86  mov     [r14], rax
0x180003e89  mov     eax, [r14+10h]
0x180003e8d  add     eax, r15d
0x180003e90  movsxd  rdx, eax
0x180003e93  mov     r8d, r13d
0x180003e96  mov     rcx, [r14+8]
0x180003e9a  call    cs:__imp__o__recalloc
0x180003ea0  test    rax, rax
0x180003ea3  jz      short loc_180003ED8
0x180003ea5  mov     [r14+8], rax
0x180003ea9  movsxd  rdx, dword ptr [r14+10h]
0x180003ead  mov     rax, [r14]
0x180003eb0  lea     rcx, [rax+rdx*8]
0x180003eb4  test    rcx, rcx
0x180003eb7  jz      short loc_180003EBC
0x180003eb9  mov     [rcx], r12
0x180003ebc  mov     rax, [r14+8]
0x180003ec0  lea     rcx, [rax+rdx*8]
0x180003ec4  test    rcx, rcx
0x180003ec7  jz      short loc_180003ECC
0x180003ec9  mov     [rcx], rbx
0x180003ecc  add     [r14+10h], r15d
0x180003ed0  mov     rdi, rsi
0x180003ed3  mov     rbx, rsi
0x180003ed6  jmp     short loc_180003EDB
0x180003ed8  mov     r15d, esi
0x180003edb  mov     rcx, rbx; Block
0x180003ede  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003ee3  nop
0x180003ee4  mov     rcx, rdi; Block
0x180003ee7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003eec  mov     eax, r15d
0x180003eef  jmp     short loc_180003EF3
0x180003ef1  xor     eax, eax
0x180003ef3  add     rsp, 40h
0x180003ef7  pop     r15
0x180003ef9  pop     r14
0x180003efb  pop     r13
0x180003efd  pop     r12
0x180003eff  pop     rdi
0x180003f00  pop     rsi
0x180003f01  pop     rbx
0x180003f02  retn
0x180003f03  mov     ecx, 80004005h; int
0x180003f08  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003f0e  mov     ecx, 80070057h; int
0x180003f13  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003f19  mov     ecx, 8007000Eh; int
0x180003f1e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
