# Windows::Security::Authentication::Web::CWebAuthOperation::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180018d30`
- end: `0x180018d4d`
- name: `?GetRuntimeClassName@CWebAuthOperation@Web@Authentication@Security@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `HRESULT __fastcall(Windows::Security::Authentication::Web::CWebAuthOperation *this, HSTRING__ **runtimeName)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180018d60`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018d46`

## string_xrefs

- `0x180018d37`: `Windows.Foundation.IAsyncOperation`1<Windows.Security.Authentication.Web.WebAuthenticationResult>`

## pseudocode

```c
HRESULT __fastcall Windows::Security::Authentication::Web::CWebAuthOperation::GetRuntimeClassName(
        Windows::Security::Authentication::Web::CWebAuthOperation *this,
        HSTRING__ **runtimeName)
{
  *runtimeName = 0;
  return WindowsCreateString(
           L"Windows.Foundation.IAsyncOperation`1<Windows.Security.Authentication.Web.WebAuthenticationResult>",
           0x61u,
           runtimeName);
}

```

## disassembly

```asm
0x180018d30  mov     qword ptr [runtimeName], 0
0x180018d37  lea     this, aWindowsFoundat; "Windows.Foundation.IAsyncOperation`1<Wi"...
0x180018d3e  mov     r8, runtimeName
0x180018d41  mov     edx, 61h ; 'a'
0x180018d46  jmp     cs:__imp_WindowsCreateString
```
