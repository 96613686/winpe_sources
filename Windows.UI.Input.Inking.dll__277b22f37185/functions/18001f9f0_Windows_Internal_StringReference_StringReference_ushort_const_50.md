# Windows::Internal::StringReference::StringReference(ushort const (&)[50])

- ea: `0x18001f9f0`
- end: `0x18001fa33`
- name: `??$?0$0DC@@StringReference@Internal@Windows@@QEAA@AEAY0DC@$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800248d8`
- `0x1800b7bd0`
- `0x1800bdb10`

## callees

- `0x18001f9f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fa24`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fa24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001fa0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001fa0b`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0x31u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18001f9f0  push    rbx
0x18001f9f2  sub     rsp, 20h
0x18001f9f6  mov     rax, rdx
0x18001f9f9  lea     r8, [rcx+8]; hstringHeader
0x18001f9fd  mov     rbx, rcx
0x18001fa00  mov     r9, rcx; string
0x18001fa03  mov     rcx, rax; sourceString
0x18001fa06  mov     edx, 31h ; '1'; length
0x18001fa0b  call    cs:__imp_WindowsCreateStringReference
0x18001fa11  test    eax, eax
0x18001fa13  jns     short loc_18001FA2A
0x18001fa15  xor     r9d, r9d; lpArguments
0x18001fa18  xor     r8d, r8d; nNumberOfArguments
0x18001fa1b  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001fa20  lea     edx, [r9+1]; dwExceptionFlags
0x18001fa24  call    cs:__imp_RaiseException
0x18001fa2a  mov     rax, rbx
0x18001fa2d  add     rsp, 20h
0x18001fa31  pop     rbx
0x18001fa32  retn
```
