# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x180041700`
- end: `0x1800418a1`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `417`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000cb98`
- `0x1800379a0`

## callees

- `0x1800046f8`
- `0x180023530`
- `0x180026764`
- `0x18004165c`
- `0x180041700`

## import_xrefs

- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x18004187b`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x180041885`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x18004187b`
- `PhotoBase!?Delete@BasePrivate@@YAXPEAX@Z` at `0x180041885`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x18004176e`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x1800417d2`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x18004176e`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x1800417d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CExpansionVector::Add(
        ATL::CExpansionVector *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // r15
  const unsigned __int16 *v4; // r14
  unsigned int v5; // esi
  __int64 v6; // rax
  unsigned __int128 v7; // rax
  BasePrivate *v8; // r12
  BasePrivate *v9; // rdi
  bool v10; // r8
  __int64 v11; // r13
  unsigned __int128 v12; // rax
  __int64 *v13; // rdx
  void *v14; // rbx
  errno_t v15; // ecx
  errno_t v16; // eax
  void *v17; // rdx
  __int64 v19; // [rsp+0h] [rbp-78h] BYREF
  void *v20; // [rsp+20h] [rbp-58h] BYREF
  BasePrivate *v21; // [rsp+28h] [rbp-50h]
  __int64 v22; // [rsp+30h] [rbp-48h]
  rsize_t SourceSize; // [rsp+38h] [rbp-40h]
  BasePrivate *v31; // [rsp+98h] [rbp+20h] BYREF

  v3 = a3;
  v4 = a2;
  v5 = 0;
  if ( !a2 || !a3 )
    return 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  SourceSize = 2 * v6 + 2;
  v31 = 0;
  v7 = SourceSize * (unsigned __int128)2uLL;
  if ( !is_mul_ok(SourceSize, 2u) )
    *(_QWORD *)&v7 = -1;
  try
  {
    BYTE8(v7) = 1;
    v8 = (BasePrivate *)BasePrivate::New((BasePrivate *)v7, *((unsigned __int64 *)&v7 + 1), (bool)a3);
    v31 = v8;
  }
  catch ( ... )
  {
    v5 = 0;
    v3 = a3;
    v4 = a2;
    v8 = v31;
  }
  try
  {
    v9 = v8;
    v21 = v8;
    v11 = 2LL * (int)(ocslen(v3) + 1);
    v22 = v11;
    v20 = 0;
    v12 = (unsigned __int64)v11 * (unsigned __int128)2uLL;
    if ( !is_mul_ok(v11, 2u) )
      *(_QWORD *)&v12 = -1;
    BYTE8(v12) = 1;
    v14 = BasePrivate::New((BasePrivate *)v12, *((unsigned __int64 *)&v12 + 1), v10);
    v20 = v14;
  }
  catch ( ... )
  {
    v13 = &v19;
    v5 = 0;
    v3 = a3;
    v4 = a2;
    v8 = v31;
    v9 = v21;
    v14 = v20;
    v11 = v22;
  }
  if ( v8 )
  {
    if ( v14 )
    {
      v15 = memcpy_s(v8, SourceSize, v4, SourceSize);
      ATL::AtlCrtErrorCheck(v15);
      v16 = memcpy_s(v14, v11, v3, v11);
      ATL::AtlCrtErrorCheck(v16);
      if ( (unsigned int)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::Add(
                           this,
                           &v31,
                           &v20) )
      {
        v9 = 0;
        v14 = 0;
        v5 = 1;
      }
    }
  }
  BasePrivate::Delete((BasePrivate *)v14, v13);
  BasePrivate::Delete(v9, v17);
  return v5;
}

```

## disassembly

```asm
0x180041700  mov     [rsp+arg_10], r8
0x180041705  mov     [rsp+arg_8], rdx
0x18004170a  mov     [rsp+arg_0], rcx
0x18004170f  push    rbx
0x180041710  push    rsi
0x180041711  push    rdi
0x180041712  push    r12
0x180041714  push    r13
0x180041716  push    r14
0x180041718  push    r15
0x18004171a  sub     rsp, 40h
0x18004171e  mov     r15, r8
0x180041721  mov     r14, rdx
0x180041724  xor     esi, esi
0x180041726  test    rdx, rdx
0x180041729  jz      loc_18004188F
0x18004172f  test    r8, r8
0x180041732  jz      loc_18004188F
0x180041738  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004173c  mov     rax, rbx
0x18004173f  inc     rax
0x180041742  cmp     [rdx+rax*2], si
0x180041746  jnz     short loc_18004173F
0x180041748  lea     rcx, ds:2[rax*2]
0x180041750  mov     [rsp+78h+SourceSize], rcx
0x180041755  mov     [rsp+78h+arg_18], rsi
0x18004175d  mov     eax, 2
0x180041762  mul     rcx
0x180041765  cmovb   rax, rbx
0x180041769  mov     dl, 1
0x18004176b  mov     rcx, rax
0x18004176e  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x180041774  mov     r12, rax
0x180041777  mov     [rsp+78h+arg_18], rax
0x18004177f  jmp     short loc_18004179F
0x180041781  xor     esi, esi
0x180041783  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180041787  mov     r15, [rsp+78h+arg_10]
0x18004178f  mov     r14, [rsp+78h+arg_8]
0x180041797  mov     r12, [rsp+78h+arg_18]
0x18004179f  mov     rdi, r12
0x1800417a2  mov     [rsp+78h+var_50], r12
0x1800417a7  mov     rcx, r15; unsigned __int16 *
0x1800417aa  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x1800417af  inc     eax
0x1800417b1  movsxd  r13, eax
0x1800417b4  add     r13, r13
0x1800417b7  mov     [rsp+78h+var_48], r13
0x1800417bc  mov     [rsp+78h+var_58], rsi
0x1800417c1  mov     eax, 2
0x1800417c6  mul     r13
0x1800417c9  cmovb   rax, rbx
0x1800417cd  mov     dl, 1
0x1800417cf  mov     rcx, rax
0x1800417d2  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x1800417d8  mov     rbx, rax
0x1800417db  mov     [rsp+78h+var_58], rax
0x1800417e0  jmp     short loc_18004180B
0x1800417e2  xor     esi, esi
0x1800417e4  mov     r15, [rsp+78h+arg_10]
0x1800417ec  mov     r14, [rsp+78h+arg_8]
0x1800417f4  mov     r12, [rsp+78h+arg_18]
0x1800417fc  mov     rdi, [rsp+78h+var_50]
0x180041801  mov     rbx, [rsp+78h+var_58]
0x180041806  mov     r13, [rsp+78h+var_48]
0x18004180b  mov     [rsp+78h+arg_8], rbx
0x180041813  test    r12, r12
0x180041816  jz      short loc_180041878
0x180041818  test    rbx, rbx
0x18004181b  jz      short loc_180041878
0x18004181d  mov     rdx, [rsp+78h+SourceSize]; DestinationSize
0x180041822  mov     r9, rdx; SourceSize
0x180041825  mov     r8, r14; Source
0x180041828  mov     rcx, r12; Destination
0x18004182b  call    memcpy_s
0x180041830  mov     ecx, eax; int
0x180041832  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180041837  mov     r9, r13; SourceSize
0x18004183a  mov     r8, r15; Source
0x18004183d  mov     rdx, r13; DestinationSize
0x180041840  mov     rcx, rbx; Destination
0x180041843  call    memcpy_s
0x180041848  mov     ecx, eax; int
0x18004184a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18004184f  lea     r8, [rsp+78h+var_58]
0x180041854  lea     rdx, [rsp+78h+arg_18]
0x18004185c  mov     rcx, [rsp+78h+arg_0]
0x180041864  call    ?Add@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAHAEBQEAG0@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::Add(ushort * const &,ushort * const &)
0x180041869  test    eax, eax
0x18004186b  jz      short loc_180041878
0x18004186d  mov     rdi, rsi
0x180041870  mov     rbx, rsi
0x180041873  mov     esi, 1
0x180041878  mov     rcx, rbx
0x18004187b  call    cs:__imp_?Delete@BasePrivate@@YAXPEAX@Z; BasePrivate::Delete(void *)
0x180041881  nop
0x180041882  mov     rcx, rdi
0x180041885  call    cs:__imp_?Delete@BasePrivate@@YAXPEAX@Z; BasePrivate::Delete(void *)
0x18004188b  mov     eax, esi
0x18004188d  jmp     short loc_180041891
0x18004188f  xor     eax, eax
0x180041891  add     rsp, 40h
0x180041895  pop     r15
0x180041897  pop     r14
0x180041899  pop     r13
0x18004189b  pop     r12
0x18004189d  pop     rdi
0x18004189e  pop     rsi
0x18004189f  pop     rbx
0x1800418a0  retn
```
