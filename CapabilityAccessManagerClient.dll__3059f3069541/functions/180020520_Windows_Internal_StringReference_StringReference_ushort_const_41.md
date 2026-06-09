# Windows::Internal::StringReference::StringReference(ushort const (&)[41])

- ea: `0x180020520`
- end: `0x180020564`
- name: `??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[41])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180022728`

## callees

- `0x180020520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020555`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002053c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002053c`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[41])
{
  if ( WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.Package",
         0x28u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180020520  push    rbx
0x180020522  sub     rsp, 20h
0x180020526  mov     rbx, rcx
0x180020529  lea     r8, [rcx+8]; hstringHeader
0x18002052d  mov     r9, rcx; string
0x180020530  mov     edx, 28h ; '('; length
0x180020535  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18002053c  call    cs:__imp_WindowsCreateStringReference
0x180020542  test    eax, eax
0x180020544  jns     short loc_18002055B
0x180020546  xor     r9d, r9d; lpArguments
0x180020549  xor     r8d, r8d; nNumberOfArguments
0x18002054c  mov     ecx, 0C000000Dh; dwExceptionCode
0x180020551  lea     edx, [r9+1]; dwExceptionFlags
0x180020555  call    cs:__imp_RaiseException
0x18002055b  mov     rax, rbx
0x18002055e  add     rsp, 20h
0x180020562  pop     rbx
0x180020563  retn
```
