# Windows::Internal::StringReference::StringReference(ushort const (&)[51])

- ea: `0x180011df8`
- end: `0x180011e3c`
- name: `??$?0$0DD@@StringReference@Internal@Windows@@QEAA@AEAY0DD@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[51])`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18001a224`
- `0x18001f014`
- `0x18001f424`
- `0x180024440`

## callees

- `0x180011df8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011e2d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011e2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011e14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011e14`

## string_xrefs

- `0x180011e0d`: `Windows.Internal.CapabilityAccess.CapabilityAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[51])
{
  if ( WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.CapabilityAccess",
         0x32u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180011df8  push    rbx
0x180011dfa  sub     rsp, 20h
0x180011dfe  mov     rbx, rcx
0x180011e01  lea     r8, [rcx+8]; hstringHeader
0x180011e05  mov     r9, rcx; string
0x180011e08  mov     edx, 32h ; '2'; length
0x180011e0d  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x180011e14  call    cs:__imp_WindowsCreateStringReference
0x180011e1a  test    eax, eax
0x180011e1c  jns     short loc_180011E33
0x180011e1e  xor     r9d, r9d; lpArguments
0x180011e21  xor     r8d, r8d; nNumberOfArguments
0x180011e24  mov     ecx, 0C000000Dh; dwExceptionCode
0x180011e29  lea     edx, [r9+1]; dwExceptionFlags
0x180011e2d  call    cs:__imp_RaiseException
0x180011e33  mov     rax, rbx
0x180011e36  add     rsp, 20h
0x180011e3a  pop     rbx
0x180011e3b  retn
```
