# Windows::Internal::StringReference::StringReference(ushort const (&)[70])

- ea: `0x1800729d0`
- end: `0x180072a21`
- name: `??$?0$0EG@@StringReference@Internal@Windows@@QEAA@AEAY0EG@$$CBG@Z`
- size: `81`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[70])`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800759c0`
- `0x18007759c`

## callees

- `0x1800729d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180072a0b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180072a0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800729ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800729ec`

## string_xrefs

- `0x1800729e5`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[70])
{
  if ( WindowsCreateStringReference(
         L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
         0x45u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x1800729d0  push    rbx
0x1800729d2  sub     rsp, 20h
0x1800729d6  mov     rbx, rcx
0x1800729d9  lea     r8, [rcx+8]; hstringHeader
0x1800729dd  mov     r9, rcx; string
0x1800729e0  mov     edx, 45h ; 'E'; length
0x1800729e5  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x1800729ec  call    cs:__imp_WindowsCreateStringReference
0x1800729f3  nop     dword ptr [rax+rax+00h]
0x1800729f8  test    eax, eax
0x1800729fa  jns     short loc_180072A17
0x1800729fc  xor     r9d, r9d; lpArguments
0x1800729ff  xor     r8d, r8d; nNumberOfArguments
0x180072a02  mov     ecx, 0C000000Dh; dwExceptionCode
0x180072a07  lea     edx, [r9+1]; dwExceptionFlags
0x180072a0b  call    cs:__imp_RaiseException
0x180072a12  nop     dword ptr [rax+rax+00h]
0x180072a17  mov     rax, rbx
0x180072a1a  add     rsp, 20h
0x180072a1e  pop     rbx
0x180072a1f  retn
```
