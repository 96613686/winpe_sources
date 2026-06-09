# Windows::Internal::StringReference::StringReference(ushort const (&)[14])

- ea: `0x18000ae08`
- end: `0x18000ae4c`
- name: `??$?0$0O@@StringReference@Internal@Windows@@QEAA@AEAY0O@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[14])`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b760`
- `0x18000bd80`
- `0x180019de0`

## callees

- `0x18000ae08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ae3d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ae3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ae24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ae24`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[14])
{
  if ( WindowsCreateStringReference(L"DetectionMode", 0xDu, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18000ae08  push    rbx
0x18000ae0a  sub     rsp, 20h
0x18000ae0e  mov     rbx, rcx
0x18000ae11  lea     r8, [rcx+8]; hstringHeader
0x18000ae15  mov     r9, rcx; string
0x18000ae18  mov     edx, 0Dh; length
0x18000ae1d  lea     rcx, aDetectionmode; "DetectionMode"
0x18000ae24  call    cs:__imp_WindowsCreateStringReference
0x18000ae2a  test    eax, eax
0x18000ae2c  jns     short loc_18000AE43
0x18000ae2e  xor     r9d, r9d; lpArguments
0x18000ae31  xor     r8d, r8d; nNumberOfArguments
0x18000ae34  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000ae39  lea     edx, [r9+1]; dwExceptionFlags
0x18000ae3d  call    cs:__imp_RaiseException
0x18000ae43  mov     rax, rbx
0x18000ae46  add     rsp, 20h
0x18000ae4a  pop     rbx
0x18000ae4b  retn
```
