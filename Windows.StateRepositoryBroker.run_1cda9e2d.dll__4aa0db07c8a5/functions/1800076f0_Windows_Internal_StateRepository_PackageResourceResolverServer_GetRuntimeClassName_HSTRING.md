# Windows::Internal::StateRepository::PackageResourceResolverServer::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800076f0`
- end: `0x18000770d`
- name: `?GetRuntimeClassName@PackageResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Internal::StateRepository::PackageResourceResolverServer *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180007706`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::StateRepository::PackageResourceResolverServer::GetRuntimeClassName(
        Windows::Internal::StateRepository::PackageResourceResolverServer *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.StateRepository.PackageResourceResolver", 0x38u, a2);
}

```

## disassembly

```asm
0x1800076f0  mov     qword ptr [rdx], 0
0x1800076f7  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackageResourceResolver@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x1800076fe  mov     r8, rdx
0x180007701  mov     edx, 38h ; '8'
0x180007706  jmp     cs:__imp_WindowsCreateString
```
