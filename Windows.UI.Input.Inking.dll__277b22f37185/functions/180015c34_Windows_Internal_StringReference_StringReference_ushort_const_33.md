# Windows::Internal::StringReference::StringReference(ushort const (&)[33])

- ea: `0x180015c34`
- end: `0x180015c77`
- name: `??$?0$0CB@@StringReference@Internal@Windows@@QEAA@AEAY0CB@$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180018da0`
- `0x18004e7b0`
- `0x180061a50`
- `0x1800a1c1c`

## callees

- `0x180015c34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015c68`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015c68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015c4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015c4f`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0x20u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180015c34  push    rbx
0x180015c36  sub     rsp, 20h
0x180015c3a  mov     rax, rdx
0x180015c3d  lea     r8, [rcx+8]; hstringHeader
0x180015c41  mov     rbx, rcx
0x180015c44  mov     r9, rcx; string
0x180015c47  mov     rcx, rax; sourceString
0x180015c4a  mov     edx, 20h ; ' '; length
0x180015c4f  call    cs:__imp_WindowsCreateStringReference
0x180015c55  test    eax, eax
0x180015c57  jns     short loc_180015C6E
0x180015c59  xor     r9d, r9d; lpArguments
0x180015c5c  xor     r8d, r8d; nNumberOfArguments
0x180015c5f  mov     ecx, 0C000000Dh; dwExceptionCode
0x180015c64  lea     edx, [r9+1]; dwExceptionFlags
0x180015c68  call    cs:__imp_RaiseException
0x180015c6e  mov     rax, rbx
0x180015c71  add     rsp, 20h
0x180015c75  pop     rbx
0x180015c76  retn
```
