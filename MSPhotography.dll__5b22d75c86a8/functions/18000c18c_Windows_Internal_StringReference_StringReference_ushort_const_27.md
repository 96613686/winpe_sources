# Windows::Internal::StringReference::StringReference(ushort const (&)[27])

- ea: `0x18000c18c`
- end: `0x18000c1d0`
- name: `??$?0$0BL@@StringReference@Internal@Windows@@QEAA@AEAY0BL@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[27])`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180019de0`
- `0x1800afe40`

## callees

- `0x18000c18c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c1c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c1c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c1a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c1a8`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[27])
{
  if ( WindowsCreateStringReference(L"MFCaptureEngineSessionGuid", 0x1Au, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18000c18c  push    rbx
0x18000c18e  sub     rsp, 20h
0x18000c192  mov     rbx, rcx
0x18000c195  lea     r8, [rcx+8]; hstringHeader
0x18000c199  mov     r9, rcx; string
0x18000c19c  mov     edx, 1Ah; length
0x18000c1a1  lea     rcx, aMfcaptureengin; "MFCaptureEngineSessionGuid"
0x18000c1a8  call    cs:__imp_WindowsCreateStringReference
0x18000c1ae  test    eax, eax
0x18000c1b0  jns     short loc_18000C1C7
0x18000c1b2  xor     r9d, r9d; lpArguments
0x18000c1b5  xor     r8d, r8d; nNumberOfArguments
0x18000c1b8  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000c1bd  lea     edx, [r9+1]; dwExceptionFlags
0x18000c1c1  call    cs:__imp_RaiseException
0x18000c1c7  mov     rax, rbx
0x18000c1ca  add     rsp, 20h
0x18000c1ce  pop     rbx
0x18000c1cf  retn
```
