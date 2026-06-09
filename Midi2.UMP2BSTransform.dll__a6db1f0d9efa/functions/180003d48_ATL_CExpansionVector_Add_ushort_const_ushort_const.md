# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x180003d48`
- end: `0x180003fb4`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `620`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180004070`
- `0x1800084d4`

## callees

- `0x180001f14`
- `0x180002330`
- `0x180003d48`
- `0x1800047f8`
- `0x180008b08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180003f0b`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180003f2a`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180003f0b`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x180003f2a`

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
0x180003d48  mov     [rsp+arg_10], r8
0x180003d4d  mov     [rsp+arg_8], rdx
0x180003d52  mov     [rsp+arg_0], rcx
0x180003d57  push    rbx
0x180003d58  push    rsi
0x180003d59  push    rdi
0x180003d5a  push    r12
0x180003d5c  push    r13
0x180003d5e  push    r14
0x180003d60  push    r15
0x180003d62  sub     rsp, 40h
0x180003d66  mov     r13, r8
0x180003d69  mov     r15, rdx
0x180003d6c  mov     r14, rcx
0x180003d6f  xor     esi, esi
0x180003d71  test    rdx, rdx
0x180003d74  jz      loc_180003F81
0x180003d7a  test    r8, r8
0x180003d7d  jz      loc_180003F81
0x180003d83  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003d87  mov     rax, rbx
0x180003d8a  inc     rax
0x180003d8d  cmp     [rdx+rax*2], si
0x180003d91  jnz     short loc_180003D8A
0x180003d93  lea     rcx, ds:2[rax*2]
0x180003d9b  mov     [rsp+78h+SourceSize], rcx
0x180003da0  mov     [rsp+78h+arg_18], rsi
0x180003da8  mov     eax, 2
0x180003dad  mul     rcx
0x180003db0  cmovb   rax, rbx
0x180003db4  mov     rcx, rax; unsigned __int64
0x180003db7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003dbc  mov     r12, rax
0x180003dbf  mov     [rsp+78h+arg_18], rax
0x180003dc7  jmp     short loc_180003DEF
0x180003dc9  xor     esi, esi
0x180003dcb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003dcf  mov     r14, [rsp+78h+arg_0]
0x180003dd7  mov     r13, [rsp+78h+arg_10]
0x180003ddf  mov     r15, [rsp+78h+arg_8]
0x180003de7  mov     r12, [rsp+78h+arg_18]
0x180003def  mov     rdi, r12
0x180003df2  mov     [rsp+78h+var_48], r12
0x180003df7  mov     rcx, rbx
0x180003dfa  inc     rcx
0x180003dfd  cmp     [r13+rcx*2+0], si
0x180003e03  jnz     short loc_180003DFA
0x180003e05  inc     ecx
0x180003e07  movsxd  rcx, ecx
0x180003e0a  add     rcx, rcx
0x180003e0d  mov     [rsp+78h+DestinationSize], rcx
0x180003e12  mov     [rsp+78h+var_58], rsi
0x180003e17  mov     eax, 2
0x180003e1c  mul     rcx
0x180003e1f  cmovb   rax, rbx
0x180003e23  mov     rcx, rax; unsigned __int64
0x180003e26  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003e2b  mov     rbx, rax
0x180003e2e  mov     [rsp+78h+var_58], rax
0x180003e33  jmp     short loc_180003E61
0x180003e35  xor     esi, esi
0x180003e37  mov     r14, [rsp+78h+arg_0]
0x180003e3f  mov     r13, [rsp+78h+arg_10]
0x180003e47  mov     r15, [rsp+78h+arg_8]
0x180003e4f  mov     r12, [rsp+78h+arg_18]
0x180003e57  mov     rdi, [rsp+78h+var_48]
0x180003e5c  mov     rbx, [rsp+78h+var_58]
0x180003e61  mov     [rsp+78h+arg_8], rbx
0x180003e69  test    r12, r12
0x180003e6c  jz      loc_180003F68
0x180003e72  test    rbx, rbx
0x180003e75  jz      loc_180003F68
0x180003e7b  mov     rdx, [rsp+78h+SourceSize]; DestinationSize
0x180003e80  mov     r9, rdx; SourceSize
0x180003e83  mov     r8, r15; Source
0x180003e86  mov     rcx, r12; Destination
0x180003e89  call    memcpy_s
0x180003e8e  test    eax, eax
0x180003e90  jz      short loc_180003EB6
0x180003e92  cmp     eax, 0Ch
0x180003e95  jz      loc_180003FA9
0x180003e9b  cmp     eax, 16h
0x180003e9e  jz      loc_180003F9E
0x180003ea4  cmp     eax, 22h ; '"'
0x180003ea7  jz      loc_180003F9E
0x180003ead  cmp     eax, 50h ; 'P'
0x180003eb0  jnz     loc_180003F93
0x180003eb6  mov     r9, [rsp+78h+DestinationSize]; SourceSize
0x180003ebb  mov     r8, r13; Source
0x180003ebe  mov     rdx, r9; DestinationSize
0x180003ec1  mov     rcx, rbx; Destination
0x180003ec4  call    memcpy_s
0x180003ec9  test    eax, eax
0x180003ecb  jz      short loc_180003EF1
0x180003ecd  cmp     eax, 0Ch
0x180003ed0  jz      loc_180003FA9
0x180003ed6  cmp     eax, 16h
0x180003ed9  jz      loc_180003F9E
0x180003edf  cmp     eax, 22h ; '"'
0x180003ee2  jz      loc_180003F9E
0x180003ee8  cmp     eax, 50h ; 'P'
0x180003eeb  jnz     loc_180003F93
0x180003ef1  mov     eax, [r14+10h]
0x180003ef5  mov     r15d, 1
0x180003efb  add     eax, r15d
0x180003efe  movsxd  rdx, eax
0x180003f01  lea     r13d, [r15+7]
0x180003f05  mov     r8d, r13d
0x180003f08  mov     rcx, [r14]
0x180003f0b  call    cs:__imp__o__recalloc
0x180003f11  test    rax, rax
0x180003f14  jz      short loc_180003F68
0x180003f16  mov     [r14], rax
0x180003f19  mov     eax, [r14+10h]
0x180003f1d  add     eax, r15d
0x180003f20  movsxd  rdx, eax
0x180003f23  mov     r8d, r13d
0x180003f26  mov     rcx, [r14+8]
0x180003f2a  call    cs:__imp__o__recalloc
0x180003f30  test    rax, rax
0x180003f33  jz      short loc_180003F68
0x180003f35  mov     [r14+8], rax
0x180003f39  movsxd  rdx, dword ptr [r14+10h]
0x180003f3d  mov     rax, [r14]
0x180003f40  lea     rcx, [rax+rdx*8]
0x180003f44  test    rcx, rcx
0x180003f47  jz      short loc_180003F4C
0x180003f49  mov     [rcx], r12
0x180003f4c  mov     rax, [r14+8]
0x180003f50  lea     rcx, [rax+rdx*8]
0x180003f54  test    rcx, rcx
0x180003f57  jz      short loc_180003F5C
0x180003f59  mov     [rcx], rbx
0x180003f5c  add     [r14+10h], r15d
0x180003f60  mov     rdi, rsi
0x180003f63  mov     rbx, rsi
0x180003f66  jmp     short loc_180003F6B
0x180003f68  mov     r15d, esi
0x180003f6b  mov     rcx, rbx; Block
0x180003f6e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003f73  nop
0x180003f74  mov     rcx, rdi; Block
0x180003f77  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003f7c  mov     eax, r15d
0x180003f7f  jmp     short loc_180003F83
0x180003f81  xor     eax, eax
0x180003f83  add     rsp, 40h
0x180003f87  pop     r15
0x180003f89  pop     r14
0x180003f8b  pop     r13
0x180003f8d  pop     r12
0x180003f8f  pop     rdi
0x180003f90  pop     rsi
0x180003f91  pop     rbx
0x180003f92  retn
0x180003f93  mov     ecx, 80004005h; int
0x180003f98  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003f9e  mov     ecx, 80070057h; int
0x180003fa3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003fa9  mov     ecx, 8007000Eh; int
0x180003fae  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
