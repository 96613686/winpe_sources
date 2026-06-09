# DllGetActivationFactory

- ea: `0x1800bed10`
- end: `0x1800bedbf`
- name: `DllGetActivationFactory`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800be92c`
- `0x1800bed10`
- `0x1800d46fc`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bed44`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bed73`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800beda6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bed44`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800bed73`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800beda6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bed21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bed21`

## pseudocode

```c
__int64 __fastcall DllGetActivationFactory(HSTRING a1, __int64 a2)
{
  const WCHAR *StringRawBuffer; // rsi
  __int64 v6; // rdx
  __int64 v7; // r8

  StringRawBuffer = WindowsGetStringRawBuffer(a1, 0);
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"Windows.Storage.Provider.StorageProviderQueryResultSet", -1, 1) == 2 )
    return FederatedCloudSearch_GetActivationFactory(a1, a2);
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"Windows.Storage.Provider.StorageProviderSearchResult", -1, 1) == 2 )
    return FederatedCloudSearch_GetActivationFactory(a1, a2);
  LOBYTE(v7) = 3;
  LOBYTE(v6) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI50481181>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_FI50481181>::GetImpl'::`2'::impl,
    v6,
    v7);
  if ( CompareStringOrdinal(StringRawBuffer, -1, L"Windows.Storage.Provider.StorageProviderSuggestionResult", -1, 1) == 2 )
    return FederatedCloudSearch_GetActivationFactory(a1, a2);
  else
    return 2147746065LL;
}

```

## disassembly

```asm
0x1800bed10  push    rbx
0x1800bed12  push    rbp
0x1800bed13  push    rsi
0x1800bed14  push    rdi
0x1800bed15  sub     rsp, 38h
0x1800bed19  mov     rdi, rdx
0x1800bed1c  mov     rbx, rcx
0x1800bed1f  xor     edx, edx; length
0x1800bed21  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bed27  or      ebp, 0FFFFFFFFh
0x1800bed2a  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x1800bed32  mov     r9d, ebp; cchCount2
0x1800bed35  lea     r8, aWindowsStorage_2; "Windows.Storage.Provider.StorageProvide"...
0x1800bed3c  mov     edx, ebp; cchCount1
0x1800bed3e  mov     rcx, rax; lpString1
0x1800bed41  mov     rsi, rax
0x1800bed44  call    cs:__imp_CompareStringOrdinal
0x1800bed4a  cmp     eax, 2
0x1800bed4d  jnz     short loc_1800BED5C
0x1800bed4f  mov     rdx, rdi
0x1800bed52  mov     rcx, rbx
0x1800bed55  call    FederatedCloudSearch_GetActivationFactory
0x1800bed5a  jmp     short loc_1800BEDB6
0x1800bed5c  mov     r9d, ebp; cchCount2
0x1800bed5f  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x1800bed67  lea     r8, aWindowsStorage_4; "Windows.Storage.Provider.StorageProvide"...
0x1800bed6e  mov     edx, ebp; cchCount1
0x1800bed70  mov     rcx, rsi; lpString1
0x1800bed73  call    cs:__imp_CompareStringOrdinal
0x1800bed79  cmp     eax, 2
0x1800bed7c  jz      short loc_1800BED4F
0x1800bed7e  mov     r8b, 3
0x1800bed81  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FI50481181@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FI50481181@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI50481181> `wil::Feature<__WilFeatureTraits_Feature_FI50481181>::GetImpl(void)'::`2'::impl
0x1800bed88  mov     dl, 1
0x1800bed8a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_FI50481181@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FI50481181>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800bed8f  mov     r9d, ebp; cchCount2
0x1800bed92  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x1800bed9a  lea     r8, aWindowsStorage_3; "Windows.Storage.Provider.StorageProvide"...
0x1800beda1  mov     edx, ebp; cchCount1
0x1800beda3  mov     rcx, rsi; lpString1
0x1800beda6  call    cs:__imp_CompareStringOrdinal
0x1800bedac  cmp     eax, 2
0x1800bedaf  jz      short loc_1800BED4F
0x1800bedb1  mov     eax, 80040111h
0x1800bedb6  add     rsp, 38h
0x1800bedba  pop     rdi
0x1800bedbb  pop     rsi
0x1800bedbc  pop     rbp
0x1800bedbd  pop     rbx
0x1800bedbe  retn
```
