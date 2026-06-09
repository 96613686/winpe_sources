# CMetadataRDFReaderWriter::RemoveValue(tagPROPVARIANT const *,tagPROPVARIANT const *)

- ea: `0x180023ae0`
- end: `0x180023bae`
- name: `?RemoveValue@CMetadataRDFReaderWriter@@UEAAJPEBUtagPROPVARIANT@@0@Z`
- size: `206`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800058c0`
- `0x18000f1d0`
- `0x18000f760`
- `0x1800171c4`
- `0x180023ae0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180023b8b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180023b95`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180023b8b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180023b95`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::RemoveValue(
        CMetadataRDFReaderWriter *this,
        struct tagPROPVARIANT *a2,
        struct tagPROPVARIANT *a3)
{
  __int64 v4; // r8
  UINT v5; // r9d
  int v6; // ebx
  __int64 v7; // r8
  UINT v8; // r9d
  int v9; // ecx
  int v10; // eax
  PROPVARIANT pvar[3]; // [rsp+20h] [rbp-40h] BYREF
  int v13; // [rsp+38h] [rbp-28h]
  int v14; // [rsp+3Ch] [rbp-24h]
  PROPVARIANT v15[3]; // [rsp+40h] [rbp-20h] BYREF
  int v16; // [rsp+58h] [rbp-8h]
  int v17; // [rsp+5Ch] [rbp-4h]
  char *v18; // [rsp+80h] [rbp+20h] BYREF
  struct tagPROPVARIANT *v19; // [rsp+88h] [rbp+28h] BYREF
  struct tagPROPVARIANT *v20; // [rsp+90h] [rbp+30h] BYREF

  v20 = a3;
  v19 = a2;
  v18 = (char *)this + 40;
  CMTALock::Enter((CMetadataRDFReaderWriter *)((char *)this + 40));
  CCoercedVariant::CCoercedVariant((CCoercedVariant *)v15, (const struct tagPROPVARIANT **)&v19, v4, v5);
  v6 = v16;
  CCoercedVariant::CCoercedVariant((CCoercedVariant *)pvar, (const struct tagPROPVARIANT **)&v20, v7, v8);
  v17 = 0;
  if ( v6 >= 0 )
  {
    if ( !v20 )
    {
      v6 = -2147024809;
      v14 = 0;
      goto LABEL_6;
    }
    v6 = v13;
  }
  v14 = 0;
  if ( v6 < 0 )
  {
LABEL_6:
    if ( g_doStackCaptures )
    {
      v9 = v6;
LABEL_11:
      DoStackCapture(v9);
      goto LABEL_12;
    }
    goto LABEL_12;
  }
  v10 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, struct tagPROPVARIANT *, struct tagPROPVARIANT *))(*(_QWORD *)this + 192LL))(
          this,
          v19,
          v20);
  v6 = v10;
  if ( v10 < 0 && g_doStackCaptures )
  {
    v9 = v10;
    goto LABEL_11;
  }
LABEL_12:
  PropVariantClear(pvar);
  PropVariantClear(v15);
  CGuard<CMTALock>::~CGuard<CMTALock>(&v18);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180023ae0  mov     [rsp-18h+arg_10], r8
0x180023ae5  mov     [rsp-18h+arg_8], rdx
0x180023aea  push    rbp
0x180023aeb  push    rbx
0x180023aec  push    rdi
0x180023aed  mov     rbp, rsp
0x180023af0  sub     rsp, 60h
0x180023af4  mov     rdi, rcx
0x180023af7  add     rcx, 28h ; '('; this
0x180023afb  mov     [rbp+arg_0], rcx
0x180023aff  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x180023b04  lea     rdx, [rbp+arg_8]; struct tagPROPVARIANT **
0x180023b08  lea     rcx, [rbp+var_20]; this
0x180023b0c  call    ??0CCoercedVariant@@QEAA@PEAPEBUtagPROPVARIANT@@@Z; CCoercedVariant::CCoercedVariant(tagPROPVARIANT const * *)
0x180023b11  mov     ebx, [rbp+var_8]
0x180023b14  lea     rdx, [rbp+arg_10]; struct tagPROPVARIANT **
0x180023b18  lea     rcx, [rbp+pvar]; this
0x180023b1c  call    ??0CCoercedVariant@@QEAA@PEAPEBUtagPROPVARIANT@@@Z; CCoercedVariant::CCoercedVariant(tagPROPVARIANT const * *)
0x180023b21  mov     r8, [rbp+arg_10]
0x180023b25  mov     [rbp+var_4], 0
0x180023b2c  test    ebx, ebx
0x180023b2e  js      short loc_180023B43
0x180023b30  test    r8, r8
0x180023b33  jnz     short loc_180023B40
0x180023b35  mov     ebx, 80070057h
0x180023b3a  mov     [rbp+var_24], r8d
0x180023b3e  jmp     short loc_180023B4E
0x180023b40  mov     ebx, [rbp+var_28]
0x180023b43  mov     [rbp+var_24], 0
0x180023b4a  test    ebx, ebx
0x180023b4c  jns     short loc_180023B5B
0x180023b4e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180023b55  jz      short loc_180023B87
0x180023b57  mov     ecx, ebx
0x180023b59  jmp     short loc_180023B82
0x180023b5b  mov     rax, [rdi]
0x180023b5e  mov     rcx, rdi
0x180023b61  mov     rdx, [rbp+arg_8]
0x180023b65  mov     rax, [rax+0C0h]
0x180023b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b71  mov     ebx, eax
0x180023b73  test    eax, eax
0x180023b75  jns     short loc_180023B87
0x180023b77  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180023b7e  jz      short loc_180023B87
0x180023b80  mov     ecx, eax; int
0x180023b82  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180023b87  lea     rcx, [rbp+pvar]; pvar
0x180023b8b  call    cs:__imp_PropVariantClear
0x180023b91  lea     rcx, [rbp+var_20]; pvar
0x180023b95  call    cs:__imp_PropVariantClear
0x180023b9b  lea     rcx, [rbp+arg_0]
0x180023b9f  call    ??1?$CGuard@VCMTALock@@@@QEAA@XZ; CGuard<CMTALock>::~CGuard<CMTALock>(void)
0x180023ba4  mov     eax, ebx
0x180023ba6  add     rsp, 60h
0x180023baa  pop     rdi
0x180023bab  pop     rbx
0x180023bac  pop     rbp
0x180023bad  retn
```
