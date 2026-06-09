# CMetadataRDFReaderWriter::SetValue(tagPROPVARIANT const *,tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x18000f630`
- end: `0x18000f74b`
- name: `?SetValue@CMetadataRDFReaderWriter@@UEAAJPEBUtagPROPVARIANT@@00@Z`
- size: `283`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800058c0`
- `0x1800058e0`
- `0x18000f630`
- `0x18000f760`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f713`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f71d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f727`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f713`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f71d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f727`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::SetValue(
        CMetadataRDFReaderWriter *this,
        struct tagPROPVARIANT *a2,
        struct tagPROPVARIANT *a3,
        struct tagPROPVARIANT *a4)
{
  CMTALock *v4; // rdi
  __int64 v6; // r8
  UINT v7; // r9d
  int v8; // ebx
  __int64 v9; // r8
  UINT v10; // r9d
  __int64 v11; // r8
  UINT v12; // r9d
  int v13; // ecx
  int v14; // eax
  PROPVARIANT pvar[3]; // [rsp+38h] [rbp-29h] BYREF
  int v17; // [rsp+50h] [rbp-11h]
  int v18; // [rsp+54h] [rbp-Dh]
  PROPVARIANT v19[3]; // [rsp+58h] [rbp-9h] BYREF
  int v20; // [rsp+70h] [rbp+Fh]
  int v21; // [rsp+74h] [rbp+13h]
  PROPVARIANT v22[3]; // [rsp+78h] [rbp+17h] BYREF
  int v23; // [rsp+90h] [rbp+2Fh]
  int v24; // [rsp+94h] [rbp+33h]
  struct tagPROPVARIANT *v25; // [rsp+D0h] [rbp+6Fh] BYREF
  struct tagPROPVARIANT *v26; // [rsp+D8h] [rbp+77h] BYREF
  struct tagPROPVARIANT *v27; // [rsp+E0h] [rbp+7Fh] BYREF

  v27 = a4;
  v26 = a3;
  v25 = a2;
  v4 = (CMetadataRDFReaderWriter *)((char *)this + 40);
  CMTALock::Enter((CMetadataRDFReaderWriter *)((char *)this + 40));
  CCoercedVariant::CCoercedVariant((CCoercedVariant *)v22, (const struct tagPROPVARIANT **)&v25, v6, v7);
  v8 = v23;
  CCoercedVariant::CCoercedVariant((CCoercedVariant *)v19, (const struct tagPROPVARIANT **)&v26, v9, v10);
  v24 = 0;
  if ( v8 >= 0 )
  {
    v8 = v20;
    if ( !v26 )
      v8 = -2147024809;
  }
  CCoercedVariant::CCoercedVariant((CCoercedVariant *)pvar, (const struct tagPROPVARIANT **)&v27, v11, v12);
  v21 = 0;
  if ( v8 >= 0 )
  {
    if ( !v27 )
    {
      v8 = -2147024809;
      v18 = 0;
LABEL_9:
      if ( !g_doStackCaptures )
        goto LABEL_15;
      v13 = v8;
      goto LABEL_14;
    }
    v8 = v17;
  }
  v18 = 0;
  if ( v8 < 0 )
    goto LABEL_9;
  v14 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, struct tagPROPVARIANT *, struct tagPROPVARIANT *, struct tagPROPVARIANT *))(*(_QWORD *)this + 176LL))(
          this,
          v25,
          v26,
          v27);
  v8 = v14;
  if ( v14 < 0 && g_doStackCaptures )
  {
    v13 = v14;
LABEL_14:
    DoStackCapture(v13);
  }
LABEL_15:
  PropVariantClear(pvar);
  PropVariantClear(v19);
  PropVariantClear(v22);
  if ( v4 )
    CMTALock::Leave(v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000f630  mov     rax, rsp
0x18000f633  mov     [rax+20h], r9
0x18000f637  mov     [rax+18h], r8
0x18000f63b  mov     [rax+10h], rdx
0x18000f63f  push    rbp
0x18000f640  push    rbx
0x18000f641  push    rdi
0x18000f642  push    r12
0x18000f644  push    r14
0x18000f646  lea     rbp, [rax-5Fh]
0x18000f64a  sub     rsp, 90h
0x18000f651  lea     rdi, [rcx+28h]
0x18000f655  mov     r14, rcx
0x18000f658  mov     rcx, rdi; this
0x18000f65b  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x18000f660  lea     rdx, [rbp+57h+arg_8]; struct tagPROPVARIANT **
0x18000f664  lea     rcx, [rbp+57h+var_40]; this
0x18000f668  call    ??0CCoercedVariant@@QEAA@PEAPEBUtagPROPVARIANT@@@Z; CCoercedVariant::CCoercedVariant(tagPROPVARIANT const * *)
0x18000f66d  mov     ebx, [rbp+57h+var_28]
0x18000f670  lea     rdx, [rbp+57h+arg_10]; struct tagPROPVARIANT **
0x18000f674  lea     rcx, [rbp+57h+var_60]; this
0x18000f678  call    ??0CCoercedVariant@@QEAA@PEAPEBUtagPROPVARIANT@@@Z; CCoercedVariant::CCoercedVariant(tagPROPVARIANT const * *)
0x18000f67d  mov     [rbp+57h+var_24], 0
0x18000f684  mov     r12d, 80070057h
0x18000f68a  test    ebx, ebx
0x18000f68c  js      short loc_18000F69A
0x18000f68e  cmp     [rbp+57h+arg_10], 0
0x18000f693  mov     ebx, [rbp+57h+var_48]
0x18000f696  cmovz   ebx, r12d
0x18000f69a  lea     rdx, [rbp+57h+arg_18]; struct tagPROPVARIANT **
0x18000f69e  lea     rcx, [rbp+57h+pvar]; this
0x18000f6a2  call    ??0CCoercedVariant@@QEAA@PEAPEBUtagPROPVARIANT@@@Z; CCoercedVariant::CCoercedVariant(tagPROPVARIANT const * *)
0x18000f6a7  mov     r9, [rbp+57h+arg_18]
0x18000f6ab  mov     [rbp+57h+var_44], 0
0x18000f6b2  test    ebx, ebx
0x18000f6b4  js      short loc_18000F6C7
0x18000f6b6  test    r9, r9
0x18000f6b9  jnz     short loc_18000F6C4
0x18000f6bb  mov     ebx, r12d
0x18000f6be  mov     [rbp+57h+var_64], r9d
0x18000f6c2  jmp     short loc_18000F6D2
0x18000f6c4  mov     ebx, [rbp+57h+var_68]
0x18000f6c7  mov     [rbp+57h+var_64], 0
0x18000f6ce  test    ebx, ebx
0x18000f6d0  jns     short loc_18000F6DF
0x18000f6d2  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000f6d9  jz      short loc_18000F70F
0x18000f6db  mov     ecx, ebx
0x18000f6dd  jmp     short loc_18000F70A
0x18000f6df  mov     rax, [r14]
0x18000f6e2  mov     rcx, r14
0x18000f6e5  mov     r8, [rbp+57h+arg_10]
0x18000f6e9  mov     rdx, [rbp+57h+arg_8]
0x18000f6ed  mov     rax, [rax+0B0h]
0x18000f6f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6f9  mov     ebx, eax
0x18000f6fb  test    eax, eax
0x18000f6fd  jns     short loc_18000F70F
0x18000f6ff  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000f706  jz      short loc_18000F70F
0x18000f708  mov     ecx, eax; int
0x18000f70a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000f70f  lea     rcx, [rbp+57h+pvar]; pvar
0x18000f713  call    cs:__imp_PropVariantClear
0x18000f719  lea     rcx, [rbp+57h+var_60]; pvar
0x18000f71d  call    cs:__imp_PropVariantClear
0x18000f723  lea     rcx, [rbp+57h+var_40]; pvar
0x18000f727  call    cs:__imp_PropVariantClear
0x18000f72d  test    rdi, rdi
0x18000f730  jz      short loc_18000F73A
0x18000f732  mov     rcx, rdi; this
0x18000f735  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x18000f73a  mov     eax, ebx
0x18000f73c  add     rsp, 90h
0x18000f743  pop     r14
0x18000f745  pop     r12
0x18000f747  pop     rdi
0x18000f748  pop     rbx
0x18000f749  pop     rbp
0x18000f74a  retn
```
