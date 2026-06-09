# Windows::Internal::StringReference::StringReference(ushort const (&)[45])

- ea: `0x18002056c`
- end: `0x1800205af`
- name: `??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z`
- size: `67`
- prototype: `HSTRING *__fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800225a0`

## callees

- `0x18002056c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800205a0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800205a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020587`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020587`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0x2Cu, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18002056c  push    rbx
0x18002056e  sub     rsp, 20h
0x180020572  mov     rax, rdx
0x180020575  lea     r8, [rcx+8]; hstringHeader
0x180020579  mov     rbx, rcx
0x18002057c  mov     r9, rcx; string
0x18002057f  mov     rcx, rax; sourceString
0x180020582  mov     edx, 2Ch ; ','; length
0x180020587  call    cs:__imp_WindowsCreateStringReference
0x18002058d  test    eax, eax
0x18002058f  jns     short loc_1800205A6
0x180020591  xor     r9d, r9d; lpArguments
0x180020594  xor     r8d, r8d; nNumberOfArguments
0x180020597  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002059c  lea     edx, [r9+1]; dwExceptionFlags
0x1800205a0  call    cs:__imp_RaiseException
0x1800205a6  mov     rax, rbx
0x1800205a9  add     rsp, 20h
0x1800205ad  pop     rbx
0x1800205ae  retn
```
