# Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800175a0`
- end: `0x1800175bd`
- name: `?GetRuntimeClassName@AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800175d0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800175b6`

## string_xrefs

- `0x1800175a7`: `Windows.Security.Authorization.AppCapabilityAccess.AppCapability`

## pseudocode

```c
HRESULT __fastcall Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::GetRuntimeClassName(
        Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Windows.Security.Authorization.AppCapabilityAccess.AppCapability", 0x40u, a2);
}

```

## disassembly

```asm
0x1800175a0  mov     qword ptr [rdx], 0
0x1800175a7  lea     rcx, ?RuntimeClass_Windows_Security_Authorization_AppCapabilityAccess_AppCapability@@3QBGB; "Windows.Security.Authorization.AppCapab"...
0x1800175ae  mov     r8, rdx
0x1800175b1  mov     edx, 40h ; '@'
0x1800175b6  jmp     cs:__imp_WindowsCreateString
```
