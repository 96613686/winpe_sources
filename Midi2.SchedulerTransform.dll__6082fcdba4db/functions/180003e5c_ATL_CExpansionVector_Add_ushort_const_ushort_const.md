# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x180003e5c`
- end: `0x1800040c8`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `620`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180004180`
- `0x1800085f4`

## callees

- `0x180002024`
- `0x180002440`
- `0x180003e5c`
- `0x180004908`
- `0x180008c28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18000401f`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18000403e`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18000401f`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x18000403e`

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
0x180003e5c  mov     [rsp+arg_10], r8
0x180003e61  mov     [rsp+arg_8], rdx
0x180003e66  mov     [rsp+arg_0], rcx
0x180003e6b  push    rbx
0x180003e6c  push    rsi
0x180003e6d  push    rdi
0x180003e6e  push    r12
0x180003e70  push    r13
0x180003e72  push    r14
0x180003e74  push    r15
0x180003e76  sub     rsp, 40h
0x180003e7a  mov     r13, r8
0x180003e7d  mov     r15, rdx
0x180003e80  mov     r14, rcx
0x180003e83  xor     esi, esi
0x180003e85  test    rdx, rdx
0x180003e88  jz      loc_180004095
0x180003e8e  test    r8, r8
0x180003e91  jz      loc_180004095
0x180003e97  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003e9b  mov     rax, rbx
0x180003e9e  inc     rax
0x180003ea1  cmp     [rdx+rax*2], si
0x180003ea5  jnz     short loc_180003E9E
0x180003ea7  lea     rcx, ds:2[rax*2]
0x180003eaf  mov     [rsp+78h+SourceSize], rcx
0x180003eb4  mov     [rsp+78h+arg_18], rsi
0x180003ebc  mov     eax, 2
0x180003ec1  mul     rcx
0x180003ec4  cmovb   rax, rbx
0x180003ec8  mov     rcx, rax; unsigned __int64
0x180003ecb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003ed0  mov     r12, rax
0x180003ed3  mov     [rsp+78h+arg_18], rax
0x180003edb  jmp     short loc_180003F03
0x180003edd  xor     esi, esi
0x180003edf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003ee3  mov     r14, [rsp+78h+arg_0]
0x180003eeb  mov     r13, [rsp+78h+arg_10]
0x180003ef3  mov     r15, [rsp+78h+arg_8]
0x180003efb  mov     r12, [rsp+78h+arg_18]
0x180003f03  mov     rdi, r12
0x180003f06  mov     [rsp+78h+var_48], r12
0x180003f0b  mov     rcx, rbx
0x180003f0e  inc     rcx
0x180003f11  cmp     [r13+rcx*2+0], si
0x180003f17  jnz     short loc_180003F0E
0x180003f19  inc     ecx
0x180003f1b  movsxd  rcx, ecx
0x180003f1e  add     rcx, rcx
0x180003f21  mov     [rsp+78h+DestinationSize], rcx
0x180003f26  mov     [rsp+78h+var_58], rsi
0x180003f2b  mov     eax, 2
0x180003f30  mul     rcx
0x180003f33  cmovb   rax, rbx
0x180003f37  mov     rcx, rax; unsigned __int64
0x180003f3a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003f3f  mov     rbx, rax
0x180003f42  mov     [rsp+78h+var_58], rax
0x180003f47  jmp     short loc_180003F75
0x180003f49  xor     esi, esi
0x180003f4b  mov     r14, [rsp+78h+arg_0]
0x180003f53  mov     r13, [rsp+78h+arg_10]
0x180003f5b  mov     r15, [rsp+78h+arg_8]
0x180003f63  mov     r12, [rsp+78h+arg_18]
0x180003f6b  mov     rdi, [rsp+78h+var_48]
0x180003f70  mov     rbx, [rsp+78h+var_58]
0x180003f75  mov     [rsp+78h+arg_8], rbx
0x180003f7d  test    r12, r12
0x180003f80  jz      loc_18000407C
0x180003f86  test    rbx, rbx
0x180003f89  jz      loc_18000407C
0x180003f8f  mov     rdx, [rsp+78h+SourceSize]; DestinationSize
0x180003f94  mov     r9, rdx; SourceSize
0x180003f97  mov     r8, r15; Source
0x180003f9a  mov     rcx, r12; Destination
0x180003f9d  call    memcpy_s
0x180003fa2  test    eax, eax
0x180003fa4  jz      short loc_180003FCA
0x180003fa6  cmp     eax, 0Ch
0x180003fa9  jz      loc_1800040BD
0x180003faf  cmp     eax, 16h
0x180003fb2  jz      loc_1800040B2
0x180003fb8  cmp     eax, 22h ; '"'
0x180003fbb  jz      loc_1800040B2
0x180003fc1  cmp     eax, 50h ; 'P'
0x180003fc4  jnz     loc_1800040A7
0x180003fca  mov     r9, [rsp+78h+DestinationSize]; SourceSize
0x180003fcf  mov     r8, r13; Source
0x180003fd2  mov     rdx, r9; DestinationSize
0x180003fd5  mov     rcx, rbx; Destination
0x180003fd8  call    memcpy_s
0x180003fdd  test    eax, eax
0x180003fdf  jz      short loc_180004005
0x180003fe1  cmp     eax, 0Ch
0x180003fe4  jz      loc_1800040BD
0x180003fea  cmp     eax, 16h
0x180003fed  jz      loc_1800040B2
0x180003ff3  cmp     eax, 22h ; '"'
0x180003ff6  jz      loc_1800040B2
0x180003ffc  cmp     eax, 50h ; 'P'
0x180003fff  jnz     loc_1800040A7
0x180004005  mov     eax, [r14+10h]
0x180004009  mov     r15d, 1
0x18000400f  add     eax, r15d
0x180004012  movsxd  rdx, eax
0x180004015  lea     r13d, [r15+7]
0x180004019  mov     r8d, r13d
0x18000401c  mov     rcx, [r14]
0x18000401f  call    cs:__imp__o__recalloc
0x180004025  test    rax, rax
0x180004028  jz      short loc_18000407C
0x18000402a  mov     [r14], rax
0x18000402d  mov     eax, [r14+10h]
0x180004031  add     eax, r15d
0x180004034  movsxd  rdx, eax
0x180004037  mov     r8d, r13d
0x18000403a  mov     rcx, [r14+8]
0x18000403e  call    cs:__imp__o__recalloc
0x180004044  test    rax, rax
0x180004047  jz      short loc_18000407C
0x180004049  mov     [r14+8], rax
0x18000404d  movsxd  rdx, dword ptr [r14+10h]
0x180004051  mov     rax, [r14]
0x180004054  lea     rcx, [rax+rdx*8]
0x180004058  test    rcx, rcx
0x18000405b  jz      short loc_180004060
0x18000405d  mov     [rcx], r12
0x180004060  mov     rax, [r14+8]
0x180004064  lea     rcx, [rax+rdx*8]
0x180004068  test    rcx, rcx
0x18000406b  jz      short loc_180004070
0x18000406d  mov     [rcx], rbx
0x180004070  add     [r14+10h], r15d
0x180004074  mov     rdi, rsi
0x180004077  mov     rbx, rsi
0x18000407a  jmp     short loc_18000407F
0x18000407c  mov     r15d, esi
0x18000407f  mov     rcx, rbx; Block
0x180004082  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004087  nop
0x180004088  mov     rcx, rdi; Block
0x18000408b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004090  mov     eax, r15d
0x180004093  jmp     short loc_180004097
0x180004095  xor     eax, eax
0x180004097  add     rsp, 40h
0x18000409b  pop     r15
0x18000409d  pop     r14
0x18000409f  pop     r13
0x1800040a1  pop     r12
0x1800040a3  pop     rdi
0x1800040a4  pop     rsi
0x1800040a5  pop     rbx
0x1800040a6  retn
0x1800040a7  mov     ecx, 80004005h; int
0x1800040ac  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800040b2  mov     ecx, 80070057h; int
0x1800040b7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800040bd  mov     ecx, 8007000Eh; int
0x1800040c2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
