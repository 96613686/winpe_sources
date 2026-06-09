# Windows::Internal::Security::Authentication::CAuthBrokerContext::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180012f00`
- end: `0x180012f1d`
- name: `?GetRuntimeClassName@CAuthBrokerContext@Authentication@Security@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::Internal::Security::Authentication::CAuthBrokerContext *this, HSTRING__ **runtimeName)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180012f16`

## string_xrefs

- `0x180012f07`: `Windows.Internal.Security.Authentication.AuthBroker`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::Security::Authentication::CAuthBrokerContext::GetRuntimeClassName(
        Windows::Internal::Security::Authentication::CAuthBrokerContext *this,
        HSTRING__ **runtimeName)
{
  *runtimeName = 0;
  return WindowsCreateString(L"Windows.Internal.Security.Authentication.AuthBroker", 0x33u, runtimeName);
}

```

## disassembly

```asm
0x180012f00  mov     qword ptr [runtimeName], 0
0x180012f07  lea     this, ?RuntimeClass_Windows_Internal_Security_Authentication_AuthBroker@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x180012f0e  mov     r8, runtimeName
0x180012f11  mov     edx, 33h ; '3'
0x180012f16  jmp     cs:__imp_WindowsCreateString
```
