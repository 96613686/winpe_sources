# Windows::Internal::StringReference::StringReference(ushort const (&)[57])

- ea: `0x180044718`
- end: `0x180044769`
- name: `??$?0$0DJ@@StringReference@Internal@Windows@@QEAA@AEAY0DJ@$$CBG@Z`
- size: `81`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[57])`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180048bc8`
- `0x18004a06c`
- `0x18004aff0`

## callees

- `0x180044718`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044753`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180044753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044734`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180044734`

## string_xrefs

- `0x18004472d`: `Windows.Security.Authentication.Web.Core.WebTokenRequest`

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
0x180044718  push    rbx
0x18004471a  sub     rsp, 20h
0x18004471e  mov     rbx, rcx
0x180044721  lea     r8, [rcx+8]; hstringHeader
0x180044725  mov     r9, rcx; string
0x180044728  mov     edx, 38h ; '8'; length
0x18004472d  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebTokenRequest@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x180044734  call    cs:__imp_WindowsCreateStringReference
0x18004473b  nop     dword ptr [rax+rax+00h]
0x180044740  test    eax, eax
0x180044742  jns     short loc_18004475F
0x180044744  xor     r9d, r9d; lpArguments
0x180044747  xor     r8d, r8d; nNumberOfArguments
0x18004474a  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004474f  lea     edx, [r9+1]; dwExceptionFlags
0x180044753  call    cs:__imp_RaiseException
0x18004475a  nop     dword ptr [rax+rax+00h]
0x18004475f  mov     rax, rbx
0x180044762  add     rsp, 20h
0x180044766  pop     rbx
0x180044767  retn
```
