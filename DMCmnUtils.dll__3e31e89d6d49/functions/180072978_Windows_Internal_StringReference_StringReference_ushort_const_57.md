# Windows::Internal::StringReference::StringReference(ushort const (&)[57])

- ea: `0x180072978`
- end: `0x1800729c9`
- name: `??$?0$0DJ@@StringReference@Internal@Windows@@QEAA@AEAY0DJ@$$CBG@Z`
- size: `81`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[57])`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800759c0`

## callees

- `0x180072978`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800729b3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800729b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180072994`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180072994`

## string_xrefs

- `0x18007298d`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[57])
{
  if ( WindowsCreateStringReference(
         L"Windows.Security.Authentication.Web.Core.WebTokenRequest",
         0x38u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180072978  push    rbx
0x18007297a  sub     rsp, 20h
0x18007297e  mov     rbx, rcx
0x180072981  lea     r8, [rcx+8]; hstringHeader
0x180072985  mov     r9, rcx; string
0x180072988  mov     edx, 38h ; '8'; length
0x18007298d  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180072994  call    cs:__imp_WindowsCreateStringReference
0x18007299b  nop     dword ptr [rax+rax+00h]
0x1800729a0  test    eax, eax
0x1800729a2  jns     short loc_1800729BF
0x1800729a4  xor     r9d, r9d; lpArguments
0x1800729a7  xor     r8d, r8d; nNumberOfArguments
0x1800729aa  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800729af  lea     edx, [r9+1]; dwExceptionFlags
0x1800729b3  call    cs:__imp_RaiseException
0x1800729ba  nop     dword ptr [rax+rax+00h]
0x1800729bf  mov     rax, rbx
0x1800729c2  add     rsp, 20h
0x1800729c6  pop     rbx
0x1800729c7  retn
```
