# IsMandatoryUpdateAllowed(void)

- ea: `0x180027104`
- end: `0x18002716f`
- name: `?IsMandatoryUpdateAllowed@@YA_NXZ`
- size: `107`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180028b44`

## callees

- `0x180027104`
- `0x18002aa78`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002715e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002715e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002713c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002713c`

## pseudocode

```c
bool IsMandatoryUpdateAllowed(void)
{
  BOOL (__stdcall *v0)(PINIT_ONCE, PVOID, PVOID *); // rdx
  union _RTL_RUN_ONCE *v1; // rcx

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CatalogCacheImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CatalogCacheImprovements>::GetImpl'::`2'::impl) )
  {
    v0 = (BOOL (__stdcall *)(PINIT_ONCE, PVOID, PVOID *))InitializeOneSettingsConfiguration;
    v1 = (union _RTL_RUN_ONCE *)&qword_180083C78;
  }
  else
  {
    v0 = InitializeInstallServiceConfiguration;
    v1 = &InitOnce;
  }
  InitOnceExecuteOnce(v1, v0, 0, 0);
  return CompareStringOrdinal(lpString1, -1, L"1", -1, 1) == 2;
}

```

## disassembly

```asm
0x180027104  sub     rsp, 38h
0x180027108  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CatalogCacheImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CatalogCacheImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CatalogCacheImprovements> `wil::Feature<__WilFeatureTraits_Feature_CatalogCacheImprovements>::GetImpl(void)'::`2'::impl
0x18002710f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CatalogCacheImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CatalogCacheImprovements>::__private_IsEnabled(void)
0x180027114  xor     r9d, r9d; Context
0x180027117  xor     r8d, r8d; Parameter
0x18002711a  test    al, al
0x18002711c  jz      short loc_18002712E
0x18002711e  lea     rdx, InitializeOneSettingsConfiguration
0x180027125  lea     rcx, qword_180083C78
0x18002712c  jmp     short loc_18002713C
0x18002712e  lea     rdx, InitializeInstallServiceConfiguration; InitFn
0x180027135  lea     rcx, InitOnce; InitOnce
0x18002713c  call    cs:__imp_InitOnceExecuteOnce
0x180027142  mov     rcx, cs:lpString1; lpString1
0x180027149  lea     r8, a1; "1"
0x180027150  or      edx, 0FFFFFFFFh; cchCount1
0x180027153  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18002715b  mov     r9d, edx; cchCount2
0x18002715e  call    cs:__imp_CompareStringOrdinal
0x180027164  cmp     eax, 2
0x180027167  setz    al
0x18002716a  add     rsp, 38h
0x18002716e  retn
```
