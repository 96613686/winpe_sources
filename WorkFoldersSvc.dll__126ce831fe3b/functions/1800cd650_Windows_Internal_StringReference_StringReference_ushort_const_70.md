# Windows::Internal::StringReference::StringReference(ushort const (&)[70])

- ea: `0x1800cd650`
- end: `0x1800cd694`
- name: `??$?0$0EG@@StringReference@Internal@Windows@@QEAA@AEAY0EG@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[70])`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800ce8cc`

## callees

- `0x1800cd650`

## import_xrefs

- `KERNEL32!RaiseException` at `0x1800cd685`
- `KERNEL32!RaiseException` at `0x1800cd685`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cd66c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cd66c`

## string_xrefs

- `0x1800cd665`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x1800cd650  push    rbx
0x1800cd652  sub     rsp, 20h
0x1800cd656  mov     rbx, rcx
0x1800cd659  lea     r8, [rcx+8]; hstringHeader
0x1800cd65d  mov     r9, rcx; string
0x1800cd660  mov     edx, 45h ; 'E'; length
0x1800cd665  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x1800cd66c  call    cs:__imp_WindowsCreateStringReference
0x1800cd672  test    eax, eax
0x1800cd674  jns     short loc_1800CD68B
0x1800cd676  xor     r9d, r9d; lpArguments
0x1800cd679  xor     r8d, r8d; nNumberOfArguments
0x1800cd67c  lea     edx, [r9+1]; dwExceptionFlags
0x1800cd680  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800cd685  call    cs:__imp_RaiseException
0x1800cd68b  mov     rax, rbx
0x1800cd68e  add     rsp, 20h
0x1800cd692  pop     rbx
0x1800cd693  retn
```
