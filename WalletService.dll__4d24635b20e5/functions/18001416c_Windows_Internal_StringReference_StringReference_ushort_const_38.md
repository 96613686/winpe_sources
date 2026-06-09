# Windows::Internal::StringReference::StringReference(ushort const (&)[38])

- ea: `0x18001416c`
- end: `0x1800141b0`
- name: `??$?0$0CG@@StringReference@Internal@Windows@@QEAA@AEAY0CG@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[38])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014d28`

## callees

- `0x18001416c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800141a1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800141a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014188`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014188`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[38])
{
  if ( WindowsCreateStringReference(
         L"Windows.Devices.Geolocation.Geocircle",
         0x25u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18001416c  push    rbx
0x18001416e  sub     rsp, 20h
0x180014172  mov     rbx, rcx
0x180014175  lea     r8, [rcx+8]; hstringHeader
0x180014179  mov     r9, rcx; string
0x18001417c  mov     edx, 25h ; '%'; length
0x180014181  lea     rcx, ?RuntimeClass_Windows_Devices_Geolocation_Geocircle@@3QBGB; "Windows.Devices.Geolocation.Geocircle"
0x180014188  call    cs:__imp_WindowsCreateStringReference
0x18001418e  test    eax, eax
0x180014190  jns     short loc_1800141A7
0x180014192  xor     r9d, r9d; lpArguments
0x180014195  xor     r8d, r8d; nNumberOfArguments
0x180014198  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001419d  lea     edx, [r9+1]; dwExceptionFlags
0x1800141a1  call    cs:__imp_RaiseException
0x1800141a7  mov     rax, rbx
0x1800141aa  add     rsp, 20h
0x1800141ae  pop     rbx
0x1800141af  retn
```
