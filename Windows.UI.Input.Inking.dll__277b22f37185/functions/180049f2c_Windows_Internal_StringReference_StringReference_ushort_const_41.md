# Windows::Internal::StringReference::StringReference(ushort const (&)[41])

- ea: `0x180049f2c`
- end: `0x180049f6f`
- name: `??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z`
- size: `67`
- prototype: `__int64 __fastcall(HSTRING *string, PCWSTR sourceString)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18004e7b0`
- `0x1800c1a20`
- `0x1800d7630`
- `0x1800d7ae0`

## callees

- `0x180049f2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180049f60`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180049f60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180049f47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180049f47`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(HSTRING *string, PCWSTR sourceString)
{
  if ( WindowsCreateStringReference(sourceString, 0x28u, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180049f2c  push    rbx
0x180049f2e  sub     rsp, 20h
0x180049f32  mov     rax, rdx
0x180049f35  lea     r8, [rcx+8]; hstringHeader
0x180049f39  mov     rbx, rcx
0x180049f3c  mov     r9, rcx; string
0x180049f3f  mov     rcx, rax; sourceString
0x180049f42  mov     edx, 28h ; '('; length
0x180049f47  call    cs:__imp_WindowsCreateStringReference
0x180049f4d  test    eax, eax
0x180049f4f  jns     short loc_180049F66
0x180049f51  xor     r9d, r9d; lpArguments
0x180049f54  xor     r8d, r8d; nNumberOfArguments
0x180049f57  mov     ecx, 0C000000Dh; dwExceptionCode
0x180049f5c  lea     edx, [r9+1]; dwExceptionFlags
0x180049f60  call    cs:__imp_RaiseException
0x180049f66  mov     rax, rbx
0x180049f69  add     rsp, 20h
0x180049f6d  pop     rbx
0x180049f6e  retn
```
