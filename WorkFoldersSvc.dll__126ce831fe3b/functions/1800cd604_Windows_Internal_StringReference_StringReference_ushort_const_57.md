# Windows::Internal::StringReference::StringReference(ushort const (&)[57])

- ea: `0x1800cd604`
- end: `0x1800cd648`
- name: `??$?0$0DJ@@StringReference@Internal@Windows@@QEAA@AEAY0DJ@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[57])`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800ce8cc`

## callees

- `0x1800cd604`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800cd639`
- `KERNEL32!RaiseException` at `0x1800cd639`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cd620`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cd620`

## string_xrefs

- `0x1800cd619`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x1800cd604  push    rbx
0x1800cd606  sub     rsp, 20h
0x1800cd60a  mov     rbx, rcx
0x1800cd60d  lea     r8, [rcx+8]; hstringHeader
0x1800cd611  mov     r9, rcx; string
0x1800cd614  mov     edx, 38h ; '8'; length
0x1800cd619  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x1800cd620  call    cs:__imp_WindowsCreateStringReference
0x1800cd626  test    eax, eax
0x1800cd628  jns     short loc_1800CD63F
0x1800cd62a  xor     r9d, r9d; lpArguments
0x1800cd62d  xor     r8d, r8d; nNumberOfArguments
0x1800cd630  lea     edx, [r9+1]; dwExceptionFlags
0x1800cd634  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800cd639  call    cs:__imp_RaiseException
0x1800cd63f  mov     rax, rbx
0x1800cd642  add     rsp, 20h
0x1800cd646  pop     rbx
0x1800cd647  retn
```
