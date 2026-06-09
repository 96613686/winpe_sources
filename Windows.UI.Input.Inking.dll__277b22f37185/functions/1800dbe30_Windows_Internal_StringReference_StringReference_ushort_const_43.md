# Windows::Internal::StringReference::StringReference(ushort const (&)[43])

- ea: `0x1800dbe30`
- end: `0x1800dbe73`
- name: `??$?0$0CL@@StringReference@Internal@Windows@@QEAA@AEAY0CL@$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800dc668`
- `0x1800ebaf4`

## callees

- `0x1800dbe30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dbe64`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800dbe64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dbe4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800dbe4b`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0x2Au, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x1800dbe30  push    rbx
0x1800dbe32  sub     rsp, 20h
0x1800dbe36  mov     rax, rdx
0x1800dbe39  lea     r8, [rcx+8]; hstringHeader
0x1800dbe3d  mov     rbx, rcx
0x1800dbe40  mov     r9, rcx; string
0x1800dbe43  mov     rcx, rax; sourceString
0x1800dbe46  mov     edx, 2Ah ; '*'; length
0x1800dbe4b  call    cs:__imp_WindowsCreateStringReference
0x1800dbe51  test    eax, eax
0x1800dbe53  jns     short loc_1800DBE6A
0x1800dbe55  xor     r9d, r9d; lpArguments
0x1800dbe58  xor     r8d, r8d; nNumberOfArguments
0x1800dbe5b  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800dbe60  lea     edx, [r9+1]; dwExceptionFlags
0x1800dbe64  call    cs:__imp_RaiseException
0x1800dbe6a  mov     rax, rbx
0x1800dbe6d  add     rsp, 20h
0x1800dbe71  pop     rbx
0x1800dbe72  retn
```
