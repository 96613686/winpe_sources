# Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180007180`
- end: `0x18000719d`
- name: `?GetRuntimeClassName@ApplicationResourceResolverServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::Internal::StateRepository::ApplicationResourceResolverServer *this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180007196`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::StateRepository::ApplicationResourceResolverServer::GetRuntimeClassName(
        Windows::Internal::StateRepository::ApplicationResourceResolverServer *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.StateRepository.ApplicationResourceResolver", 0x3Cu, a2);
}

```

## disassembly

```asm
0x180007180  mov     qword ptr [rdx], 0
0x180007187  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationResourceResolver@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18000718e  mov     r8, rdx
0x180007191  mov     edx, 3Ch ; '<'
0x180007196  jmp     cs:__imp_WindowsCreateString
```
