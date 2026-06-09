# StructuredQuery1::QueryExpressionCustomization::Initialize(SemanticsUM::SchemaEngine *)

- ea: `0x18000d4b0`
- end: `0x18000dd4b`
- name: `?Initialize@QueryExpressionCustomization@StructuredQuery1@@AEAAJPEAVSchemaEngine@SemanticsUM@@@Z`
- size: `2203`
- prototype: `__int64 __fastcall(StructuredQuery1::QueryExpressionCustomization *__hidden this, struct SemanticsUM::SchemaEngine *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180027a7c`

## callees

- `0x18000bec0`
- `0x18000d4b0`
- `0x18000eb84`
- `0x18001b2b4`
- `0x18001d030`
- `0x180020250`
- `0x18004e4d0`
- `0x18004e5b8`
- `0x18004e674`
- `0x180050b08`
- `0x180052d94`
- `0x18005e740`
- `0x18005e85c`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d87a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d8c3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000da1b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dae3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000db19`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000db4f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dbb5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dbeb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dc21`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d87a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000d8c3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000da1b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dae3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000db19`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000db4f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dbb5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dbeb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000dc21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d985`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d985`
- `PROPSYS!PSPropertyKeyFromString` at `0x18000dce5`
- `PROPSYS!PSPropertyKeyFromString` at `0x18000dd1f`
- `PROPSYS!PSPropertyKeyFromString` at `0x18000dce5`
- `PROPSYS!PSPropertyKeyFromString` at `0x18000dd1f`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x18000d93e`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x18000da81`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x18000d93e`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x18000da81`

## string_xrefs

- `0x18000db65`: `System.StructuredQuery.Compound.%lu`
- `0x18000dc37`: `System.StructuredQuery.Compound.%lu`
- `0x18000db28`: `System.StructuredQuery.Directory`
- `0x18000dbfa`: `System.StructuredQuery.Directory`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::QueryExpressionCustomization::Initialize(
        StructuredQuery1::QueryExpressionCustomization *this,
        struct SemanticsUM::SchemaEngine *a2)
{
  int Instance; // r15d
  const struct _GUID *v5; // rdx
  struct IUnknown *v6; // rcx
  const wchar_t *v7; // r8
  const wchar_t *v8; // r9
  struct IConditionGenerator *v9; // rbx
  __int64 v10; // rax
  struct IConditionGenerator *v11; // rsi
  const struct _GUID *v12; // rdx
  struct IUnknown *v13; // rcx
  struct IConditionGenerator *v14; // rbx
  struct IConditionGenerator *v15; // rbx
  struct IConditionGenerator *v16; // rbx
  struct IConditionGenerator *v17; // rbx
  int v18; // r14d
  __int64 v19; // r13
  struct IConditionGenerator *v20; // rbp
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // rsi
  __int64 (__fastcall ***j)(_QWORD); // rdi
  void **v24; // r12
  unsigned __int64 v25; // rbx
  unsigned __int64 v26; // rsi
  unsigned int v27; // r14d
  __int64 (__fastcall ***v28)(_QWORD); // rdi
  const WCHAR *v30; // rax
  const WCHAR *v31; // rax
  PROPERTYKEY *v32; // r13
  const WCHAR *v33; // rax
  const wchar_t *v34; // rdi
  __int64 v35; // rcx
  _QWORD *v36; // rax
  char *v37; // rdi
  void *v38; // rax
  size_t v39; // rax
  _DWORD *v40; // rax
  unsigned int v41; // r12d
  unsigned __int64 v42; // rdi
  const WCHAR *v43; // rax
  PROPERTYKEY *v44; // r13
  const WCHAR *v45; // rax
  const WCHAR *v46; // r14
  wchar_t lpString2; // [rsp+20h] [rbp-78h]
  const struct _GUID *cchCount2; // [rsp+28h] [rbp-70h]
  struct IConditionGenerator *i; // [rsp+A8h] [rbp+10h] BYREF
  unsigned __int64 v51; // [rsp+B0h] [rbp+18h]
  void **v52; // [rsp+B8h] [rbp+20h]

  Instance = 0;
  IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = a2;
  (*(void (__fastcall **)(struct SemanticsUM::SchemaEngine *))(*(_QWORD *)a2 + 8LL))(a2);
  if ( !*(_QWORD *)(*((_QWORD *)this + 6) + 96LL)
    || (i = 0,
        Instance = StructuredQuery1::DateTimeConditionGenerator::CreateInstance(v6, v5, (void **)&i),
        Instance >= 0)
    && (v9 = i,
        Instance = StructuredQuery1::QueryExpressionCustomization::SetHandlerForType(
                     this,
                     *(const struct IEntity **)(*((_QWORD *)this + 6) + 96LL),
                     i),
        ((void (__fastcall *)(struct IConditionGenerator *))v9->lpVtbl->Release)(v9),
        Instance >= 0) )
  {
    v10 = *((_QWORD *)this + 6);
    if ( *(_QWORD *)(v10 + 64) )
    {
      if ( *(_QWORD *)(v10 + 72) )
      {
        i = 0;
        Instance = StructuredQuery1::IntegerConditionGenerator::CreateInstance(v6, v5, (void **)&i);
        if ( Instance < 0 )
          return (unsigned int)Instance;
        v11 = i;
        Instance = StructuredQuery1::QueryExpressionCustomization::SetHandlerForType(
                     this,
                     *(const struct IEntity **)(*((_QWORD *)this + 6) + 64LL),
                     i);
        if ( Instance >= 0 )
        {
          i = 0;
          Instance = StructuredQuery1::FloatingPointConditionGenerator::CreateInstance(v13, v12, (void **)&i);
          if ( Instance >= 0 )
          {
            v14 = i;
            Instance = StructuredQuery1::QueryExpressionCustomization::SetHandlerForType(
                         this,
                         *(const struct IEntity **)(*((_QWORD *)this + 6) + 72LL),
                         i);
            ((void (__fastcall *)(struct IConditionGenerator *))v14->lpVtbl->Release)(v14);
          }
        }
        ((void (__fastcall *)(struct IConditionGenerator *))v11->lpVtbl->Release)(v11);
      }
      if ( Instance < 0 )
        return (unsigned int)Instance;
    }
    if ( !*(_QWORD *)(*((_QWORD *)this + 6) + 88LL)
      || (i = 0,
          Instance = StructuredQuery1::BooleanConditionGenerator::CreateInstance(v6, v5, (void **)&i),
          Instance >= 0)
      && (v15 = i,
          Instance = StructuredQuery1::QueryExpressionCustomization::SetHandlerForType(
                       this,
                       *(const struct IEntity **)(*((_QWORD *)this + 6) + 88LL),
                       i),
          ((void (__fastcall *)(struct IConditionGenerator *))v15->lpVtbl->Release)(v15),
          Instance >= 0) )
    {
      if ( !*(_QWORD *)(*((_QWORD *)this + 6) + 120LL)
        || (i = 0,
            (int)StructuredQuery1::FilePathQueryGenerator::CreateInstance(
                   (const wchar_t *)v6,
                   (const wchar_t *)v5,
                   v7,
                   v8,
                   lpString2,
                   cchCount2,
                   (void **)&i) < 0)
        || (v16 = i,
            Instance = StructuredQuery1::QueryExpressionCustomization::SetHandlerForType(
                         this,
                         *(const struct IEntity **)(*((_QWORD *)this + 6) + 120LL),
                         i),
            ((void (__fastcall *)(struct IConditionGenerator *))v16->lpVtbl->Release)(v16),
            Instance >= 0) )
      {
        if ( !*(_QWORD *)(*((_QWORD *)this + 6) + 128LL)
          || (i = 0, (int)StructuredQuery1::NullConditionGenerator::CreateInstance(v6, v5, (void **)&i) < 0)
          || (v17 = i,
              Instance = StructuredQuery1::QueryExpressionCustomization::SetHandlerForType(
                           this,
                           *(const struct IEntity **)(*((_QWORD *)this + 6) + 128LL),
                           i),
              ((void (__fastcall *)(struct IConditionGenerator *))v17->lpVtbl->Release)(v17),
              Instance >= 0) )
        {
          v18 = 0;
          v19 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 6) + 8LL) + 200LL);
          v20 = *(struct IConditionGenerator **)(v19 + 32);
          v21 = *(_QWORD *)(v19 + 24);
          for ( i = v20; v21 < (unsigned __int64)v20; v21 += 64LL )
          {
            v22 = *(_QWORD *)(v21 + 48);
            for ( j = *(__int64 (__fastcall ****)(_QWORD))(v21 + 40); (unsigned __int64)j < v22; j += 3 )
            {
              v30 = (const WCHAR *)(**j)(j);
              if ( CompareStringW(0x7Fu, 0, v30, -1, L"mapsToRelation", -1) == 2 )
              {
                ++v18;
                break;
              }
            }
          }
          v24 = (void **)((char *)this + 32);
          *v24 = 0;
          v52 = v24;
          v51 = 0;
          if ( is_mul_ok((unsigned int)(v18 + 10), 0x28u) )
          {
            Instance = CTCoAllocPolicy::Alloc(
                         (IMalloc *)(unsigned int)(v18 + 10),
                         1,
                         40LL * (unsigned int)(v18 + 10),
                         v24);
            if ( Instance >= 0 )
            {
              *((_DWORD *)this + 10) = v18 + 10;
              v25 = *(_QWORD *)(v19 + 24);
              v51 = v25;
              while ( 1 )
              {
                if ( v25 >= (unsigned __int64)v20 )
                  return (unsigned int)Instance;
                v26 = *(_QWORD *)(v25 + 48);
                v27 = 0;
                v28 = *(__int64 (__fastcall ****)(_QWORD))(v25 + 40);
                if ( (unsigned __int64)v28 < v26 )
                {
                  do
                  {
                    v31 = (const WCHAR *)(**v28)(v28);
                    if ( CompareStringW(0x7Fu, 0, v31, -1, L"mapsToRelation", -1) == 2 )
                      ++v27;
                    v28 += 3;
                  }
                  while ( (unsigned __int64)v28 < v26 );
                  v20 = i;
                  if ( v27 )
                  {
                    v32 = (PROPERTYKEY *)((char *)*v24 + 40 * *((unsigned int *)this + 11));
                    v33 = (const WCHAR *)(**(__int64 (__fastcall ***)(unsigned __int64))v25)(v25);
                    v34 = v33;
                    *v32 = PKEY_Null;
                    if ( v33 )
                    {
                      if ( *v33 == 123 )
                      {
                        Instance = PSPropertyKeyFromString(v33, v32);
                        if ( Instance < 0 )
                          return (unsigned int)Instance;
                      }
                      else
                      {
                        Instance = PSGetPropertyKeyFromName(v33, v32);
                        if ( Instance < 0 )
                        {
                          if ( CompareStringW(0x7Fu, 1u, v34, -1, L"*", -1) == 2 )
                          {
                            *v32 = PKEY_FullText;
                          }
                          else if ( CompareStringW(0x7Fu, 1u, v34, -1, L"System.StructuredQuery.Scope", -1) == 2 )
                          {
                            v32->fmtid = (GUID)PKEY_SCOPE_PSEUDOPROPERTY;
                            v32->pid = 100;
                          }
                          else if ( CompareStringW(0x7Fu, 1u, v34, -1, L"System.StructuredQuery.Directory", -1) == 2 )
                          {
                            v32->fmtid = (GUID)PKEY_DIRECTORY_PSEUDOPROPERTY;
                            v32->pid = 101;
                          }
                          else
                          {
                            if ( swscanf(v34, L"System.StructuredQuery.Compound.%lu", &v32->pid) != 1 )
                              return (unsigned int)Instance;
                            v32->fmtid = (GUID)xmmword_18009B810;
                          }
                        }
                      }
                    }
                    v35 = 5LL * *((unsigned int *)this + 11);
                    v36 = *v24;
                    v36[v35 + 3] = 0;
                    v37 = (char *)&v36[v35];
                    if ( !is_mul_ok(v27, 0x14u) )
                      return (unsigned int)-2147024362;
                    v38 = CoTaskMemAlloc(20LL * v27);
                    *((_QWORD *)v37 + 3) = v38;
                    if ( v38 )
                    {
                      v39 = CTCoAllocPolicy::_CoTaskMemSize(v38);
                      memset_0(*((void **)v37 + 3), 0, v39);
                      Instance = 0;
                    }
                    else
                    {
                      Instance = -2147024882;
                    }
                    if ( Instance >= 0 )
                      break;
                  }
                }
LABEL_30:
                v25 += 64LL;
                v51 = v25;
                if ( Instance < 0 )
                  return (unsigned int)Instance;
              }
              v40 = *v24;
              v41 = 0;
              v40[10 * *((unsigned int *)this + 11) + 8] = v27;
              v42 = *(_QWORD *)(v25 + 40);
              while ( 1 )
              {
                if ( v42 >= v26 )
                {
LABEL_54:
                  ++*((_DWORD *)this + 11);
                  v20 = i;
                  v25 = v51;
                  v24 = v52;
                  goto LABEL_30;
                }
                v43 = (const WCHAR *)(**(__int64 (__fastcall ***)(unsigned __int64))v42)(v42);
                if ( CompareStringW(0x7Fu, 0, v43, -1, L"mapsToRelation", -1) == 2 )
                {
                  v44 = (PROPERTYKEY *)(*(_QWORD *)(*((_QWORD *)this + 4) + 40LL * *((unsigned int *)this + 11) + 24)
                                      + 20LL * v41);
                  v45 = (const WCHAR *)(*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)v42 + 8LL))(v42);
                  Instance = 0;
                  v46 = v45;
                  *v44 = PKEY_Null;
                  if ( v45 )
                  {
                    if ( *v45 == 123 )
                    {
                      Instance = PSPropertyKeyFromString(v45, v44);
                    }
                    else
                    {
                      Instance = PSGetPropertyKeyFromName(v45, v44);
                      if ( Instance < 0 )
                      {
                        if ( CompareStringW(0x7Fu, 1u, v46, -1, L"*", -1) == 2 )
                        {
                          Instance = 0;
                          *v44 = PKEY_FullText;
                          goto LABEL_52;
                        }
                        if ( CompareStringW(0x7Fu, 1u, v46, -1, L"System.StructuredQuery.Scope", -1) == 2 )
                        {
                          Instance = 0;
                          v44->fmtid = (GUID)PKEY_SCOPE_PSEUDOPROPERTY;
                          v44->pid = 100;
                          goto LABEL_52;
                        }
                        if ( CompareStringW(0x7Fu, 1u, v46, -1, L"System.StructuredQuery.Directory", -1) == 2 )
                        {
                          Instance = 0;
                          v44->fmtid = (GUID)PKEY_DIRECTORY_PSEUDOPROPERTY;
                          v44->pid = 101;
                          goto LABEL_52;
                        }
                        if ( swscanf(v46, L"System.StructuredQuery.Compound.%lu", &v44->pid) == 1 )
                        {
                          Instance = 0;
                          v44->fmtid = (GUID)xmmword_18009B810;
LABEL_52:
                          ++v41;
                          goto LABEL_53;
                        }
                      }
                    }
                  }
                  if ( Instance >= 0 )
                    goto LABEL_52;
                }
LABEL_53:
                v42 += 24LL;
                if ( Instance < 0 )
                  goto LABEL_54;
              }
            }
          }
          else
          {
            return (unsigned int)-2147024362;
          }
        }
      }
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000d4b0  mov     [rsp+arg_0], rcx
0x18000d4b5  push    rbx
0x18000d4b6  push    rdi
0x18000d4b7  push    r12
0x18000d4b9  push    r15
0x18000d4bb  sub     rsp, 78h
0x18000d4bf  mov     r12, rcx
0x18000d4c2  mov     rbx, rdx
0x18000d4c5  add     rcx, 30h ; '0'
0x18000d4c9  xor     r15d, r15d
0x18000d4cc  call    ??$IUnknown_SafeReleaseAndNullPtr@V?$GrowableBuffer@UtagHITRANGE@@@@@@YAXAEAPEAV?$GrowableBuffer@UtagHITRANGE@@@@@Z; IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(GrowableBuffer<tagHITRANGE> * &)
0x18000d4d1  mov     [r12+30h], rbx
0x18000d4d6  mov     rcx, rbx
0x18000d4d9  mov     rax, [rbx]
0x18000d4dc  mov     rax, [rax+8]
0x18000d4e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4e5  mov     rax, [r12+30h]
0x18000d4ea  cmp     [rax+60h], r15
0x18000d4ee  jz      short loc_18000D547
0x18000d4f0  lea     r8, [rsp+98h+arg_8]; void **
0x18000d4f8  mov     [rsp+98h+arg_8], r15
0x18000d500  call    ?CreateInstance@DateTimeConditionGenerator@StructuredQuery1@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::DateTimeConditionGenerator::CreateInstance(IUnknown *,_GUID const &,void * *)
0x18000d505  mov     r15d, eax
0x18000d508  test    eax, eax
0x18000d50a  js      loc_18000D841
0x18000d510  mov     rdx, [r12+30h]
0x18000d515  mov     rcx, r12; this
0x18000d518  mov     rbx, [rsp+98h+arg_8]
0x18000d520  mov     r8, rbx; struct IConditionGenerator *
0x18000d523  mov     rdx, [rdx+60h]; struct IEntity *
0x18000d527  call    ?SetHandlerForType@QueryExpressionCustomization@StructuredQuery1@@QEAAJPEBVIEntity@SemanticsUM@@PEAUIConditionGenerator@@@Z; StructuredQuery1::QueryExpressionCustomization::SetHandlerForType(SemanticsUM::IEntity const *,IConditionGenerator *)
0x18000d52c  mov     r15d, eax
0x18000d52f  mov     rcx, rbx
0x18000d532  mov     rax, [rbx]
0x18000d535  mov     rax, [rax+10h]
0x18000d539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d53e  test    r15d, r15d
0x18000d541  js      loc_18000D841
0x18000d547  mov     rax, [r12+30h]
0x18000d54c  mov     [rsp+98h+var_30], rsi
0x18000d551  cmp     qword ptr [rax+40h], 0
0x18000d556  jz      loc_18000D614
0x18000d55c  cmp     qword ptr [rax+48h], 0
0x18000d561  jz      loc_18000D60B
0x18000d567  lea     r8, [rsp+98h+arg_8]; void **
0x18000d56f  mov     [rsp+98h+arg_8], 0
0x18000d57b  call    ?CreateInstance@IntegerConditionGenerator@StructuredQuery1@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::IntegerConditionGenerator::CreateInstance(IUnknown *,_GUID const &,void * *)
0x18000d580  mov     r15d, eax
0x18000d583  test    eax, eax
0x18000d585  js      loc_18000D83C
0x18000d58b  mov     rdx, [r12+30h]
0x18000d590  mov     rcx, r12; this
0x18000d593  mov     rsi, [rsp+98h+arg_8]
0x18000d59b  mov     r8, rsi; struct IConditionGenerator *
0x18000d59e  mov     rdx, [rdx+40h]; struct IEntity *
0x18000d5a2  call    ?SetHandlerForType@QueryExpressionCustomization@StructuredQuery1@@QEAAJPEBVIEntity@SemanticsUM@@PEAUIConditionGenerator@@@Z; StructuredQuery1::QueryExpressionCustomization::SetHandlerForType(SemanticsUM::IEntity const *,IConditionGenerator *)
0x18000d5a7  mov     r15d, eax
0x18000d5aa  test    eax, eax
0x18000d5ac  js      short loc_18000D5FC
0x18000d5ae  lea     r8, [rsp+98h+arg_8]; void **
0x18000d5b6  mov     [rsp+98h+arg_8], 0
0x18000d5c2  call    ?CreateInstance@FloatingPointConditionGenerator@StructuredQuery1@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::FloatingPointConditionGenerator::CreateInstance(IUnknown *,_GUID const &,void * *)
0x18000d5c7  mov     r15d, eax
0x18000d5ca  test    eax, eax
0x18000d5cc  js      short loc_18000D5FC
0x18000d5ce  mov     rdx, [r12+30h]
0x18000d5d3  mov     rcx, r12; this
0x18000d5d6  mov     rbx, [rsp+98h+arg_8]
0x18000d5de  mov     r8, rbx; struct IConditionGenerator *
0x18000d5e1  mov     rdx, [rdx+48h]; struct IEntity *
0x18000d5e5  call    ?SetHandlerForType@QueryExpressionCustomization@StructuredQuery1@@QEAAJPEBVIEntity@SemanticsUM@@PEAUIConditionGenerator@@@Z; StructuredQuery1::QueryExpressionCustomization::SetHandlerForType(SemanticsUM::IEntity const *,IConditionGenerator *)
0x18000d5ea  mov     r15d, eax
0x18000d5ed  mov     rcx, rbx
0x18000d5f0  mov     rax, [rbx]
0x18000d5f3  mov     rax, [rax+10h]
0x18000d5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5fc  mov     rax, [rsi]
0x18000d5ff  mov     rcx, rsi
0x18000d602  mov     rax, [rax+10h]
0x18000d606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d60b  test    r15d, r15d
0x18000d60e  js      loc_18000D83C
0x18000d614  mov     rax, [r12+30h]
0x18000d619  cmp     qword ptr [rax+58h], 0
0x18000d61e  jz      short loc_18000D67B
0x18000d620  lea     r8, [rsp+98h+arg_8]; void **
0x18000d628  mov     [rsp+98h+arg_8], 0
0x18000d634  call    ?CreateInstance@BooleanConditionGenerator@StructuredQuery1@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::BooleanConditionGenerator::CreateInstance(IUnknown *,_GUID const &,void * *)
0x18000d639  mov     r15d, eax
0x18000d63c  test    eax, eax
0x18000d63e  js      loc_18000D83C
0x18000d644  mov     rdx, [r12+30h]
0x18000d649  mov     rcx, r12; this
0x18000d64c  mov     rbx, [rsp+98h+arg_8]
0x18000d654  mov     r8, rbx; struct IConditionGenerator *
0x18000d657  mov     rdx, [rdx+58h]; struct IEntity *
0x18000d65b  call    ?SetHandlerForType@QueryExpressionCustomization@StructuredQuery1@@QEAAJPEBVIEntity@SemanticsUM@@PEAUIConditionGenerator@@@Z; StructuredQuery1::QueryExpressionCustomization::SetHandlerForType(SemanticsUM::IEntity const *,IConditionGenerator *)
0x18000d660  mov     r15d, eax
0x18000d663  mov     rcx, rbx
0x18000d666  mov     rax, [rbx]
0x18000d669  mov     rax, [rax+10h]
0x18000d66d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d672  test    r15d, r15d
0x18000d675  js      loc_18000D83C
0x18000d67b  mov     rax, [r12+30h]
0x18000d680  cmp     qword ptr [rax+78h], 0
0x18000d685  jz      short loc_18000D6E0
0x18000d687  lea     rax, [rsp+98h+arg_8]
0x18000d68f  mov     [rsp+98h+arg_8], 0
0x18000d69b  mov     [rsp+98h+var_68], rax; void **
0x18000d6a0  call    ?CreateInstance@FilePathQueryGenerator@StructuredQuery1@@SAJPEB_W0000AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::FilePathQueryGenerator::CreateInstance(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,_GUID const &,void * *)
0x18000d6a5  test    eax, eax
0x18000d6a7  js      short loc_18000D6E0
0x18000d6a9  mov     rdx, [r12+30h]
0x18000d6ae  mov     rcx, r12; this
0x18000d6b1  mov     rbx, [rsp+98h+arg_8]
0x18000d6b9  mov     r8, rbx; struct IConditionGenerator *
0x18000d6bc  mov     rdx, [rdx+78h]; struct IEntity *
0x18000d6c0  call    ?SetHandlerForType@QueryExpressionCustomization@StructuredQuery1@@QEAAJPEBVIEntity@SemanticsUM@@PEAUIConditionGenerator@@@Z; StructuredQuery1::QueryExpressionCustomization::SetHandlerForType(SemanticsUM::IEntity const *,IConditionGenerator *)
0x18000d6c5  mov     r15d, eax
0x18000d6c8  mov     rcx, rbx
0x18000d6cb  mov     rax, [rbx]
0x18000d6ce  mov     rax, [rax+10h]
0x18000d6d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6d7  test    r15d, r15d
0x18000d6da  js      loc_18000D83C
0x18000d6e0  mov     rax, [r12+30h]
0x18000d6e5  cmp     qword ptr [rax+80h], 0
0x18000d6ed  jz      short loc_18000D746
0x18000d6ef  lea     r8, [rsp+98h+arg_8]; void **
0x18000d6f7  mov     [rsp+98h+arg_8], 0
0x18000d703  call    ?CreateInstance@NullConditionGenerator@StructuredQuery1@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::NullConditionGenerator::CreateInstance(IUnknown *,_GUID const &,void * *)
0x18000d708  test    eax, eax
0x18000d70a  js      short loc_18000D746
0x18000d70c  mov     rdx, [r12+30h]
0x18000d711  mov     rcx, r12; this
0x18000d714  mov     rbx, [rsp+98h+arg_8]
0x18000d71c  mov     r8, rbx; struct IConditionGenerator *
0x18000d71f  mov     rdx, [rdx+80h]; struct IEntity *
0x18000d726  call    ?SetHandlerForType@QueryExpressionCustomization@StructuredQuery1@@QEAAJPEBVIEntity@SemanticsUM@@PEAUIConditionGenerator@@@Z; StructuredQuery1::QueryExpressionCustomization::SetHandlerForType(SemanticsUM::IEntity const *,IConditionGenerator *)
0x18000d72b  mov     r15d, eax
0x18000d72e  mov     rcx, rbx
0x18000d731  mov     rax, [rbx]
0x18000d734  mov     rax, [rax+10h]
0x18000d738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d73d  test    r15d, r15d
0x18000d740  js      loc_18000D83C
0x18000d746  mov     rax, [r12+30h]
0x18000d74b  lea     r15, aMapstorelation; "mapsToRelation"
0x18000d752  mov     [rsp+98h+var_28], rbp
0x18000d757  mov     [rsp+98h+var_38], r13
0x18000d75c  mov     [rsp+98h+var_40], r14
0x18000d761  xor     r14d, r14d
0x18000d764  mov     rcx, [rax+8]
0x18000d768  mov     r13, [rcx+0C8h]
0x18000d76f  mov     rbp, [r13+20h]
0x18000d773  mov     rbx, [r13+18h]
0x18000d777  mov     [rsp+98h+arg_8], rbp
0x18000d77f  cmp     rbx, rbp
0x18000d782  jnb     short loc_18000D79E
0x18000d784  mov     rsi, [rbx+30h]
0x18000d788  mov     rdi, [rbx+28h]
0x18000d78c  cmp     rdi, rsi
0x18000d78f  jb      loc_18000D84F
0x18000d795  add     rbx, 40h ; '@'
0x18000d799  cmp     rbx, rbp
0x18000d79c  jb      short loc_18000D784
0x18000d79e  add     r12, 20h ; ' '
0x18000d7a2  lea     ebx, [r14+0Ah]
0x18000d7a6  mov     ecx, ebx; void *
0x18000d7a8  mov     eax, 28h ; '('
0x18000d7ad  mul     rcx
0x18000d7b0  mov     qword ptr [r12], 0
0x18000d7b8  mov     [rsp+98h+arg_18], r12
0x18000d7c0  mov     [rsp+98h+arg_10], 0
0x18000d7cc  test    rdx, rdx
0x18000d7cf  jnz     loc_18000DCA1
0x18000d7d5  mov     r9, r12; void **
0x18000d7d8  mov     r8, rax; unsigned __int64
0x18000d7db  mov     edx, 1; unsigned int
0x18000d7e0  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18000d7e5  mov     r15d, eax
0x18000d7e8  test    eax, eax
0x18000d7ea  js      short loc_18000D82D
0x18000d7ec  mov     rax, [rsp+98h+arg_0]
0x18000d7f4  mov     [rax+28h], ebx
0x18000d7f7  mov     rbx, [r13+18h]
0x18000d7fb  mov     [rsp+98h+arg_10], rbx
0x18000d803  cmp     rbx, rbp
0x18000d806  jnb     short loc_18000D82D
0x18000d808  mov     rsi, [rbx+30h]
0x18000d80c  xor     r14d, r14d
0x18000d80f  mov     rdi, [rbx+28h]
0x18000d813  cmp     rdi, rsi
0x18000d816  jb      loc_18000D891
0x18000d81c  add     rbx, 40h ; '@'
0x18000d820  mov     [rsp+98h+arg_10], rbx
0x18000d828  test    r15d, r15d
0x18000d82b  jns     short loc_18000D803
0x18000d82d  mov     r13, [rsp+98h+var_38]
0x18000d832  mov     rbp, [rsp+98h+var_28]
0x18000d837  mov     r14, [rsp+98h+var_40]
0x18000d83c  mov     rsi, [rsp+98h+var_30]
0x18000d841  mov     eax, r15d
0x18000d844  add     rsp, 78h
0x18000d848  pop     r15
0x18000d84a  pop     r12
0x18000d84c  pop     rdi
0x18000d84d  pop     rbx
0x18000d84e  retn
0x18000d84f  mov     rax, [rdi]
0x18000d852  mov     rcx, rdi
0x18000d855  mov     rax, [rax]
0x18000d858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d85d  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000d863  mov     dword ptr [rsp+98h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000d86b  mov     r8, rax; lpString1
0x18000d86e  mov     [rsp+98h+lpString2], r15; lpString2
0x18000d873  xor     edx, edx; dwCmpFlags
0x18000d875  mov     ecx, 7Fh; Locale
0x18000d87a  call    cs:__imp_CompareStringW
0x18000d880  cmp     eax, 2
0x18000d883  jnz     loc_18000DCFB
0x18000d889  inc     r14d
0x18000d88c  jmp     loc_18000D795
0x18000d891  lea     rbp, aMapstorelation; "mapsToRelation"
0x18000d898  mov     rax, [rdi]
0x18000d89b  mov     rcx, rdi
0x18000d89e  mov     rax, [rax]
0x18000d8a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8a6  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000d8ac  mov     dword ptr [rsp+98h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000d8b4  mov     r8, rax; lpString1
0x18000d8b7  mov     [rsp+98h+lpString2], rbp; lpString2
0x18000d8bc  xor     edx, edx; dwCmpFlags
0x18000d8be  mov     ecx, 7Fh; Locale
0x18000d8c3  call    cs:__imp_CompareStringW
0x18000d8c9  cmp     eax, 2
0x18000d8cc  jnz     short loc_18000D8D1
0x18000d8ce  inc     r14d
0x18000d8d1  add     rdi, 18h
0x18000d8d5  cmp     rdi, rsi
0x18000d8d8  jb      short loc_18000D898
0x18000d8da  mov     rbp, [rsp+98h+arg_8]
0x18000d8e2  test    r14d, r14d
0x18000d8e5  jz      loc_18000D81C
0x18000d8eb  mov     rax, [rsp+98h+arg_0]
0x18000d8f3  mov     eax, [rax+2Ch]
0x18000d8f6  lea     rcx, [rax+rax*4]
0x18000d8fa  mov     rax, [r12]
0x18000d8fe  lea     r13, [rax+rcx*8]
0x18000d902  mov     rax, [rbx]
0x18000d905  mov     rcx, rbx
0x18000d908  mov     rax, [rax]
0x18000d90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d910  mov     rdi, rax
0x18000d913  movups  xmm0, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x18000d91a  movups  xmmword ptr [r13+0], xmm0
0x18000d91f  mov     ecx, cs:PKEY_Null.pid
0x18000d925  mov     [r13+10h], ecx
0x18000d929  test    rax, rax
0x18000d92c  jz      short loc_18000D94F
0x18000d92e  cmp     word ptr [rax], 7Bh ; '{'
0x18000d932  mov     rdx, r13; pkey
0x18000d935  mov     rcx, rax; pszString
0x18000d938  jz      loc_18000DCE5
0x18000d93e  call    cs:__imp_PSGetPropertyKeyFromName
0x18000d944  mov     r15d, eax
0x18000d947  test    eax, eax
0x18000d949  js      loc_18000DB8E
0x18000d94f  mov     rax, [rsp+98h+arg_0]
0x18000d957  xor     r13d, r13d
0x18000d95a  mov     eax, [rax+2Ch]
0x18000d95d  lea     rcx, [rax+rax*4]
0x18000d961  mov     rax, [r12]
0x18000d965  mov     [rax+rcx*8+18h], r13
0x18000d96a  lea     rdi, [rax+rcx*8]
0x18000d96e  mov     ecx, r14d
0x18000d971  mov     eax, 14h
0x18000d976  mul     rcx
0x18000d979  test    rdx, rdx
0x18000d97c  jnz     loc_18000DCA1
0x18000d982  mov     rcx, rax; cb
0x18000d985  call    cs:__imp_CoTaskMemAlloc
0x18000d98b  mov     [rdi+18h], rax
0x18000d98f  test    rax, rax
0x18000d992  jz      loc_18000DC5D
0x18000d998  mov     rcx, rax; void *
0x18000d99b  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18000d9a0  mov     rcx, [rdi+18h]; void *
0x18000d9a4  mov     r8, rax; Size
0x18000d9a7  xor     edx, edx; Val
0x18000d9a9  call    memset_0
0x18000d9ae  mov     r15d, r13d
0x18000d9b1  test    r15d, r15d
0x18000d9b4  js      loc_18000D81C
0x18000d9ba  mov     rbp, [rsp+98h+arg_0]
0x18000d9c2  mov     eax, [rbp+2Ch]
0x18000d9c5  lea     rcx, [rax+rax*4]
0x18000d9c9  mov     rax, [r12]
  ... truncated ...
```
