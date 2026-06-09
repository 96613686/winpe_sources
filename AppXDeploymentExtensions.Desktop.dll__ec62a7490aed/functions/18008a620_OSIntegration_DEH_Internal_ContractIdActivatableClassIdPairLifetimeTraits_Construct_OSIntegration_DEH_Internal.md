# OSIntegration::DEH::Internal::ContractIdActivatableClassIdPairLifetimeTraits::Construct(OSIntegration::DEH::Internal::ContractIdActivatableClassIdPair *,OSIntegration::DEH::Internal::ContractIdActivatableClassIdPair const &)

- ea: `0x18008a620`
- end: `0x18008a739`
- name: `?Construct@ContractIdActivatableClassIdPairLifetimeTraits@Internal@DEH@OSIntegration@@SAJPEAUContractIdActivatableClassIdPair@234@AEBU5234@@Z`
- size: `281`
- prototype: `__int64 __fastcall(HSTRING *newString, const struct OSIntegration::DEH::Internal::ContractIdActivatableClassIdPair *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18013efa0`
- `0x18013f948`
- `0x180141cd0`

## callees

- `0x18006a4c8`
- `0x18008a620`
- `0x18008a740`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008a63b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008a689`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008a63b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18008a689`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008a6cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008a6cf`

## string_xrefs

- `0x18008a667`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\ExtensionCatalogCollector.hpp`
- `0x18008a6b6`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\ExtensionCatalogCollector.hpp`
- `0x18008a6ef`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\ExtensionCatalogCollector.hpp`
- `0x18008a66e`: `OSIntegration::DEH::Internal::ContractIdActivatableClassIdPairLifetimeTraits::Construct`
- `0x18008a6af`: `OSIntegration::DEH::Internal::ContractIdActivatableClassIdPairLifetimeTraits::Construct`
- `0x18008a6e4`: `OSIntegration::DEH::Internal::ContractIdActivatableClassIdPairLifetimeTraits::Construct`
- `0x18008a6f6`: `WindowsDeleteString(uninitializedElement->contractId)`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::ContractIdActivatableClassIdPairLifetimeTraits::Construct(
        HSTRING *newString,
        HSTRING *a2)
{
  HRESULT v4; // eax
  unsigned int v5; // edi
  HRESULT v7; // eax
  HRESULT v8; // eax
  wil::details *v9; // [rsp+28h] [rbp-10h]
  wil::details *v10; // [rsp+28h] [rbp-10h]
  int v11; // [rsp+30h] [rbp-8h]
  int v12; // [rsp+30h] [rbp-8h]
  wil::details::in1diag5 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = WindowsDuplicateString(*a2, newString);
  v5 = v4;
  if ( v4 < 0 )
  {
    LODWORD(v9) = v4;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\ExtensionCatalogCollector.hpp",
      "OSIntegration::DEH::Internal::ContractIdActivatableClassIdPairLifetimeTraits::Construct",
      "WindowsDuplicateString(source.contractId, &uninitializedElement->contractId)",
      (const char *)v9,
      v11);
    return v5;
  }
  v7 = WindowsDuplicateString(a2[1], newString + 1);
  v5 = v7;
  if ( v7 < 0 )
  {
    LODWORD(v9) = v7;
    wil::details::in1diag5::_Log_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\ExtensionCatalogCollector.hpp",
      "OSIntegration::DEH::Internal::ContractIdActivatableClassIdPairLifetimeTraits::Construct",
      "hrDuplicateString",
      v9,
      v11);
    v8 = WindowsDeleteString(*newString);
    if ( v8 < 0 )
    {
      LODWORD(v10) = v8;
      wil::details::in1diag5::_Log_Hr(
        retaddr,
        (void *)0x26,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\ExtensionCatalogCollector.hpp",
        "OSIntegration::DEH::Internal::ContractIdActivatableClassIdPairLifetimeTraits::Construct",
        "WindowsDeleteString(uninitializedElement->contractId)",
        v10,
        v12);
    }
    LODWORD(v10) = v5;
    *newString = 0;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\ExtensionCatalogCollector.hpp",
      "OSIntegration::DEH::Internal::ContractIdActivatableClassIdPairLifetimeTraits::Construct",
      "hrDuplicateString",
      (const char *)v10,
      v12);
    return v5;
  }
  return 0;
}

```

## disassembly

```asm
0x18008a620  mov     [rsp+arg_0], rbx
0x18008a625  mov     [rsp+arg_8], rsi
0x18008a62a  push    rdi; int
0x18008a62b  sub     rsp, 30h
0x18008a62f  mov     rsi, rdx
0x18008a632  mov     rbx, rcx
0x18008a635  mov     rdx, rcx; newString
0x18008a638  mov     rcx, [rsi]; string
0x18008a63b  call    cs:__imp_WindowsDuplicateString
0x18008a642  nop     dword ptr [rax+rax+00h]
0x18008a647  mov     edi, eax
0x18008a649  test    eax, eax
0x18008a64b  jns     short loc_18008A681
0x18008a64d  mov     dword ptr [rsp+38h+var_10], eax; char *
0x18008a651  mov     edx, 22h ; '"'; void *
0x18008a656  lea     rax, aWindowsduplica; "WindowsDuplicateString(source.contractI"...
0x18008a65d  mov     [rsp+38h+var_18], rax; char *
0x18008a662  mov     rcx, [rsp+38h]; this
0x18008a667  lea     r8, aOnecoreAdminAp_151; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18008a66e  lea     r9, aOsintegrationD_52; "OSIntegration::DEH::Internal::ContractI"...
0x18008a675  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18008a67a  mov     eax, edi
0x18008a67c  jmp     loc_18008A728
0x18008a681  mov     rcx, [rsi+8]; string
0x18008a685  lea     rdx, [rbx+8]; newString
0x18008a689  call    cs:__imp_WindowsDuplicateString
0x18008a690  nop     dword ptr [rax+rax+00h]
0x18008a695  mov     edi, eax
0x18008a697  test    eax, eax
0x18008a699  jns     loc_18008A726
0x18008a69f  mov     rcx, [rsp+38h]; this
0x18008a6a4  lea     rsi, aHrduplicatestr; "hrDuplicateString"
0x18008a6ab  mov     dword ptr [rsp+38h+var_10], eax; wil::details *
0x18008a6af  lea     r9, aOsintegrationD_52; "OSIntegration::DEH::Internal::ContractI"...
0x18008a6b6  lea     r8, aOnecoreAdminAp_151; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18008a6bd  mov     [rsp+38h+var_18], rsi; char *
0x18008a6c2  mov     edx, 24h ; '$'; void *
0x18008a6c7  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18008a6cc  mov     rcx, [rbx]; string
0x18008a6cf  call    cs:__imp_WindowsDeleteString
0x18008a6d6  nop     dword ptr [rax+rax+00h]
0x18008a6db  test    eax, eax
0x18008a6dd  jns     short loc_18008A70C
0x18008a6df  mov     rcx, [rsp+38h]; this
0x18008a6e4  lea     r9, aOsintegrationD_52; "OSIntegration::DEH::Internal::ContractI"...
0x18008a6eb  mov     dword ptr [rsp+38h+var_10], eax; wil::details *
0x18008a6ef  lea     r8, aOnecoreAdminAp_151; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18008a6f6  lea     rax, aWindowsdeletes_0; "WindowsDeleteString(uninitializedElemen"...
0x18008a6fd  mov     edx, 26h ; '&'; void *
0x18008a702  mov     [rsp+38h+var_18], rax; char *
0x18008a707  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18008a70c  mov     dword ptr [rsp+38h+var_10], edi
0x18008a710  mov     edx, 28h ; '('
0x18008a715  mov     [rsp+38h+var_18], rsi
0x18008a71a  mov     qword ptr [rbx], 0
0x18008a721  jmp     loc_18008A662
0x18008a726  xor     eax, eax
0x18008a728  mov     rbx, [rsp+38h+arg_0]
0x18008a72d  mov     rsi, [rsp+38h+arg_8]
0x18008a732  add     rsp, 30h
0x18008a736  pop     rdi
0x18008a737  retn
```
