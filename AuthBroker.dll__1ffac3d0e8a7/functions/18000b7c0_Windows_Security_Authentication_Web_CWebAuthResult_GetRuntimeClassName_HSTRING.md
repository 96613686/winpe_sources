# Windows::Security::Authentication::Web::CWebAuthResult::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18000b7c0`
- end: `0x18000b7dd`
- name: `?GetRuntimeClassName@CWebAuthResult@Web@Authentication@Security@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::Security::Authentication::Web::CWebAuthResult *this, HSTRING__ **runtimeName)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000b7f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000b7d6`

## string_xrefs

- `0x18000b7c7`: `Windows.Security.Authentication.Web.WebAuthenticationResult`

## pseudocode

```c
HRESULT __fastcall Windows::Security::Authentication::Web::CWebAuthResult::GetRuntimeClassName(
        Windows::Security::Authentication::Web::CWebAuthResult *this,
        HSTRING__ **runtimeName)
{
  *runtimeName = 0;
  return WindowsCreateString(L"Windows.Security.Authentication.Web.WebAuthenticationResult", 0x3Bu, runtimeName);
}

```

## disassembly

```asm
0x18000b7c0  mov     qword ptr [runtimeName], 0
0x18000b7c7  lea     this, ?RuntimeClass_Windows_Security_Authentication_Web_WebAuthenticationResult@@3QBGB; "Windows.Security.Authentication.Web.Web"...
0x18000b7ce  mov     r8, runtimeName
0x18000b7d1  mov     edx, 3Bh ; ';'
0x18000b7d6  jmp     cs:__imp_WindowsCreateString
```
