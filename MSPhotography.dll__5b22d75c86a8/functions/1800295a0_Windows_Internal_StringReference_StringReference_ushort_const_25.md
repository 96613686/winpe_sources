# Windows::Internal::StringReference::StringReference(ushort const (&)[25])

- ea: `0x1800295a0`
- end: `0x1800295e3`
- name: `??$?0$0BJ@@StringReference@Internal@Windows@@QEAA@AEAY0BJ@$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002a520`
- `0x1800b66b0`

## callees

- `0x1800295a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800295d4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800295d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800295bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800295bb`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0x18u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x1800295a0  push    rbx
0x1800295a2  sub     rsp, 20h
0x1800295a6  mov     rax, rdx
0x1800295a9  lea     r8, [rcx+8]; hstringHeader
0x1800295ad  mov     rbx, rcx
0x1800295b0  mov     r9, rcx; string
0x1800295b3  mov     rcx, rax; sourceString
0x1800295b6  mov     edx, 18h; length
0x1800295bb  call    cs:__imp_WindowsCreateStringReference
0x1800295c1  test    eax, eax
0x1800295c3  jns     short loc_1800295DA
0x1800295c5  xor     r9d, r9d; lpArguments
0x1800295c8  xor     r8d, r8d; nNumberOfArguments
0x1800295cb  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800295d0  lea     edx, [r9+1]; dwExceptionFlags
0x1800295d4  call    cs:__imp_RaiseException
0x1800295da  mov     rax, rbx
0x1800295dd  add     rsp, 20h
0x1800295e1  pop     rbx
0x1800295e2  retn
```
