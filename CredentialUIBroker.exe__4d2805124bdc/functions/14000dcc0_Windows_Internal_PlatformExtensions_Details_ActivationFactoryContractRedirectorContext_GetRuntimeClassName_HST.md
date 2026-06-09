# Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x14000dcc0`
- end: `0x14000dcdd`
- name: `?GetRuntimeClassName@ActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext *this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x14000dcd6`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext::GetRuntimeClassName(
        Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(
           L"Windows.Internal.Foundation.Contracts.ActivationFactoryContractRedirectorContext",
           0x50u,
           a2);
}

```

## disassembly

```asm
0x14000dcc0  mov     qword ptr [rdx], 0
0x14000dcc7  lea     rcx, ?RuntimeClass_Windows_Internal_Foundation_Contracts_ActivationFactoryContractRedirectorContext@@3QBGB; "Windows.Internal.Foundation.Contracts.A"...
0x14000dcce  mov     r8, rdx
0x14000dcd1  mov     edx, 50h ; 'P'
0x14000dcd6  jmp     cs:__imp_WindowsCreateString
```
