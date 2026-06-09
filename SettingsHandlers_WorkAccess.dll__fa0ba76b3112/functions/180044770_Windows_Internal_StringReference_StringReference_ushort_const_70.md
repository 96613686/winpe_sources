# Windows::Internal::StringReference::StringReference(ushort const (&)[70])

- ea: `0x180044770`
- end: `0x1800447c1`
- name: `??$?0$0EG@@StringReference@Internal@Windows@@QEAA@AEAY0EG@$$CBG@Z`
- size: `81`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[70])`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180048bc8`
- `0x18004a06c`
- `0x18004aff0`

## callees

- `0x180044770`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800447ab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800447ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004478c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004478c`

## string_xrefs

- `0x180044785`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`

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
0x180044770  push    rbx
0x180044772  sub     rsp, 20h
0x180044776  mov     rbx, rcx
0x180044779  lea     r8, [rcx+8]; hstringHeader
0x18004477d  mov     r9, rcx; string
0x180044780  mov     edx, 45h ; 'E'; length
0x180044785  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x18004478c  call    cs:__imp_WindowsCreateStringReference
0x180044793  nop     dword ptr [rax+rax+00h]
0x180044798  test    eax, eax
0x18004479a  jns     short loc_1800447B7
0x18004479c  xor     r9d, r9d; lpArguments
0x18004479f  xor     r8d, r8d; nNumberOfArguments
0x1800447a2  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800447a7  lea     edx, [r9+1]; dwExceptionFlags
0x1800447ab  call    cs:__imp_RaiseException
0x1800447b2  nop     dword ptr [rax+rax+00h]
0x1800447b7  mov     rax, rbx
0x1800447ba  add     rsp, 20h
0x1800447be  pop     rbx
0x1800447bf  retn
```
