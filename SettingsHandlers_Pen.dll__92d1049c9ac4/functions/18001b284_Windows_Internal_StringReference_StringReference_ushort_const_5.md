# Windows::Internal::StringReference::StringReference(ushort const (&)[5])

- ea: `0x18001b284`
- end: `0x18001b2c7`
- name: `??$?0$04@StringReference@Internal@Windows@@QEAA@AEAY04$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002b6d0`
- `0x18002c690`

## callees

- `0x18001b284`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b2b8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b2b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b29f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b29f`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 4u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18001b284  push    rbx
0x18001b286  sub     rsp, 20h
0x18001b28a  mov     rax, rdx
0x18001b28d  lea     r8, [rcx+8]; hstringHeader
0x18001b291  mov     rbx, rcx
0x18001b294  mov     r9, rcx; string
0x18001b297  mov     rcx, rax; sourceString
0x18001b29a  mov     edx, 4; length
0x18001b29f  call    cs:__imp_WindowsCreateStringReference
0x18001b2a5  test    eax, eax
0x18001b2a7  jns     short loc_18001B2BE
0x18001b2a9  xor     r9d, r9d; lpArguments
0x18001b2ac  xor     r8d, r8d; nNumberOfArguments
0x18001b2af  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001b2b4  lea     edx, [r9+1]; dwExceptionFlags
0x18001b2b8  call    cs:__imp_RaiseException
0x18001b2be  mov     rax, rbx
0x18001b2c1  add     rsp, 20h
0x18001b2c5  pop     rbx
0x18001b2c6  retn
```
