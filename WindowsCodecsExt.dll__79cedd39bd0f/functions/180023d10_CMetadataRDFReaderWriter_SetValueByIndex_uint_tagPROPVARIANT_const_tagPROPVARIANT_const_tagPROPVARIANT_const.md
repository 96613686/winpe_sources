# CMetadataRDFReaderWriter::SetValueByIndex(uint,tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x180023d10`
- end: `0x180023e2e`
- name: `?SetValueByIndex@CMetadataRDFReaderWriter@@UEAAJIPEBUtagPROPVARIANT@@00@Z`
- size: `286`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, unsigned int, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800058c0`
- `0x18000f1d0`
- `0x18000f760`
- `0x1800171c4`
- `0x180023d10`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180023dfa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180023e04`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180023e0e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180023dfa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180023e04`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180023e0e`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::SetValueByIndex(
        CMetadataRDFReaderWriter *this,
        unsigned int a2,
        struct tagPROPVARIANT *a3,
        struct tagPROPVARIANT *a4,
        const struct tagPROPVARIANT *a5)
{
  __int64 v7; // r8
  UINT v8; // r9d
  int v9; // ebx
  __int64 v10; // r8
  UINT v11; // r9d
  __int64 v12; // r8
  UINT v13; // r9d
  int v14; // ecx
  int v15; // eax
  PROPVARIANT pvar[3]; // [rsp+30h] [rbp-31h] BYREF
  int v18; // [rsp+48h] [rbp-19h]
  int v19; // [rsp+4Ch] [rbp-15h]
  PROPVARIANT v20[3]; // [rsp+50h] [rbp-11h] BYREF
  int v21; // [rsp+68h] [rbp+7h]
  int v22; // [rsp+6Ch] [rbp+Bh]
  PROPVARIANT v23[3]; // [rsp+70h] [rbp+Fh] BYREF
  int v24; // [rsp+88h] [rbp+27h]
  int v25; // [rsp+8Ch] [rbp+2Bh]
  char *v26; // [rsp+C0h] [rbp+5Fh] BYREF
  struct tagPROPVARIANT *v27; // [rsp+D0h] [rbp+6Fh] BYREF
  struct tagPROPVARIANT *v28; // [rsp+D8h] [rbp+77h] BYREF

  v28 = a4;
  v27 = a3;
  v26 = (char *)this + 40;
  CMTALock::Enter((CMetadataRDFReaderWriter *)((char *)this + 40));
  CCoercedVariant::CCoercedVariant((CCoercedVariant *)v23, (const struct tagPROPVARIANT **)&v27, v7, v8);
  v9 = v24;
  CCoercedVariant::CCoercedVariant((CCoercedVariant *)v20, (const struct tagPROPVARIANT **)&v28, v10, v11);
  v25 = 0;
  if ( v9 >= 0 )
  {
    v9 = v21;
    if ( !v28 )
      v9 = -2147024809;
  }
  CCoercedVariant::CCoercedVariant((CCoercedVariant *)pvar, &a5, v12, v13);
  v22 = 0;
  if ( v9 >= 0 )
  {
    if ( !a5 )
    {
      v9 = -2147024809;
      v19 = 0;
      goto LABEL_9;
    }
    v9 = v18;
  }
  v19 = 0;
  if ( v9 < 0 )
  {
LABEL_9:
    if ( g_doStackCaptures )
    {
      v14 = v9;
LABEL_14:
      DoStackCapture(v14);
      goto LABEL_15;
    }
    goto LABEL_15;
  }
  v15 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, _QWORD, struct tagPROPVARIANT *, struct tagPROPVARIANT *, const struct tagPROPVARIANT *))(*(_QWORD *)this + 184LL))(
          this,
          a2,
          v27,
          v28,
          a5);
  v9 = v15;
  if ( v15 < 0 && g_doStackCaptures )
  {
    v14 = v15;
    goto LABEL_14;
  }
LABEL_15:
  PropVariantClear(pvar);
  PropVariantClear(v20);
  PropVariantClear(v23);
  CGuard<CMTALock>::~CGuard<CMTALock>(&v26);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180023d10  mov     [rsp-8+arg_18], r9
0x180023d15  mov     [rsp-8+arg_10], r8
0x180023d1a  push    rbp
0x180023d1b  push    rbx
0x180023d1c  push    rsi
0x180023d1d  push    r12
0x180023d1f  push    r14
0x180023d21  lea     rbp, [rsp-2Fh]
0x180023d26  sub     rsp, 90h
0x180023d2d  mov     rsi, rcx
0x180023d30  mov     r14d, edx
0x180023d33  add     rcx, 28h ; '('; this
0x180023d37  mov     [rbp+4Fh+arg_0], rcx
0x180023d3b  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x180023d40  lea     rdx, [rbp+4Fh+arg_10]; struct tagPROPVARIANT **
0x180023d44  lea     rcx, [rbp+4Fh+var_40]; this
0x180023d48  call    ??0CCoercedVariant@@QEAA@PEAPEBUtagPROPVARIANT@@@Z; CCoercedVariant::CCoercedVariant(tagPROPVARIANT const * *)
0x180023d4d  mov     ebx, [rbp+4Fh+var_28]
0x180023d50  lea     rdx, [rbp+4Fh+arg_18]; struct tagPROPVARIANT **
0x180023d54  lea     rcx, [rbp+4Fh+var_60]; this
0x180023d58  call    ??0CCoercedVariant@@QEAA@PEAPEBUtagPROPVARIANT@@@Z; CCoercedVariant::CCoercedVariant(tagPROPVARIANT const * *)
0x180023d5d  mov     [rbp+4Fh+var_24], 0
0x180023d64  mov     r12d, 80070057h
0x180023d6a  test    ebx, ebx
0x180023d6c  js      short loc_180023D7A
0x180023d6e  cmp     [rbp+4Fh+arg_18], 0
0x180023d73  mov     ebx, [rbp+4Fh+var_48]
0x180023d76  cmovz   ebx, r12d
0x180023d7a  lea     rdx, [rbp+4Fh+arg_20]; struct tagPROPVARIANT **
0x180023d7e  lea     rcx, [rbp+4Fh+pvar]; this
0x180023d82  call    ??0CCoercedVariant@@QEAA@PEAPEBUtagPROPVARIANT@@@Z; CCoercedVariant::CCoercedVariant(tagPROPVARIANT const * *)
0x180023d87  mov     rcx, [rbp+4Fh+arg_20]
0x180023d8b  mov     [rbp+4Fh+var_44], 0
0x180023d92  test    ebx, ebx
0x180023d94  js      short loc_180023DA6
0x180023d96  test    rcx, rcx
0x180023d99  jnz     short loc_180023DA3
0x180023d9b  mov     ebx, r12d
0x180023d9e  mov     [rbp+4Fh+var_64], ecx
0x180023da1  jmp     short loc_180023DB1
0x180023da3  mov     ebx, [rbp+4Fh+var_68]
0x180023da6  mov     [rbp+4Fh+var_64], 0
0x180023dad  test    ebx, ebx
0x180023daf  jns     short loc_180023DBE
0x180023db1  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180023db8  jz      short loc_180023DF6
0x180023dba  mov     ecx, ebx
0x180023dbc  jmp     short loc_180023DF1
0x180023dbe  mov     rax, [rsi]
0x180023dc1  mov     edx, r14d
0x180023dc4  mov     r9, [rbp+4Fh+arg_18]
0x180023dc8  mov     r8, [rbp+4Fh+arg_10]
0x180023dcc  mov     [rsp+0B0h+var_90], rcx
0x180023dd1  mov     rcx, rsi
0x180023dd4  mov     rax, [rax+0B8h]
0x180023ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023de0  mov     ebx, eax
0x180023de2  test    eax, eax
0x180023de4  jns     short loc_180023DF6
0x180023de6  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180023ded  jz      short loc_180023DF6
0x180023def  mov     ecx, eax; int
0x180023df1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180023df6  lea     rcx, [rbp+4Fh+pvar]; pvar
0x180023dfa  call    cs:__imp_PropVariantClear
0x180023e00  lea     rcx, [rbp+4Fh+var_60]; pvar
0x180023e04  call    cs:__imp_PropVariantClear
0x180023e0a  lea     rcx, [rbp+4Fh+var_40]; pvar
0x180023e0e  call    cs:__imp_PropVariantClear
0x180023e14  lea     rcx, [rbp+4Fh+arg_0]
0x180023e18  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x180023e1d  mov     eax, ebx
0x180023e1f  add     rsp, 90h
0x180023e26  pop     r14
0x180023e28  pop     r12
0x180023e2a  pop     rsi
0x180023e2b  pop     rbx
0x180023e2c  pop     rbp
0x180023e2d  retn
```
