# Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180004f30`
- end: `0x180004f4d`
- name: `?GetRuntimeClassName@AppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::Internal::StateRepository::AppInfoFactoryBrokerServer *this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180004f46`

## string_xrefs

- `0x180004f37`: `Windows.Internal.StateRepository.AppInfoFactoryBroker`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::StateRepository::AppInfoFactoryBrokerServer::GetRuntimeClassName(
        Windows::Internal::StateRepository::AppInfoFactoryBrokerServer *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Internal.StateRepository.AppInfoFactoryBroker", 0x35u, a2);
}

```

## disassembly

```asm
0x180004f30  mov     qword ptr [rdx], 0
0x180004f37  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_AppInfoFactoryBroker@@3QBGB; "Windows.Internal.StateRepository.AppInf"...
0x180004f3e  mov     r8, rdx
0x180004f41  mov     edx, 35h ; '5'
0x180004f46  jmp     cs:__imp_WindowsCreateString
```
