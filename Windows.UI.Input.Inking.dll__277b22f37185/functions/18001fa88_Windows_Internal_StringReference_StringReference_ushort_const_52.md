# Windows::Internal::StringReference::StringReference(ushort const (&)[52])

- ea: `0x18001fa88`
- end: `0x18001facb`
- name: `??$?0$0DE@@StringReference@Internal@Windows@@QEAA@AEAY0DE@$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800248d8`
- `0x1800b66c4`
- `0x1800b7bd0`

## callees

- `0x18001fa88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fabc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fabc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001faa3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001faa3`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0x33u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18001fa88  push    rbx
0x18001fa8a  sub     rsp, 20h
0x18001fa8e  mov     rax, rdx
0x18001fa91  lea     r8, [rcx+8]; hstringHeader
0x18001fa95  mov     rbx, rcx
0x18001fa98  mov     r9, rcx; string
0x18001fa9b  mov     rcx, rax; sourceString
0x18001fa9e  mov     edx, 33h ; '3'; length
0x18001faa3  call    cs:__imp_WindowsCreateStringReference
0x18001faa9  test    eax, eax
0x18001faab  jns     short loc_18001FAC2
0x18001faad  xor     r9d, r9d; lpArguments
0x18001fab0  xor     r8d, r8d; nNumberOfArguments
0x18001fab3  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001fab8  lea     edx, [r9+1]; dwExceptionFlags
0x18001fabc  call    cs:__imp_RaiseException
0x18001fac2  mov     rax, rbx
0x18001fac5  add     rsp, 20h
0x18001fac9  pop     rbx
0x18001faca  retn
```
