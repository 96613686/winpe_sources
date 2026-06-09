# Windows::Internal::StringReference::StringReference(ushort const (&)[41])

- ea: `0x180008a68`
- end: `0x180008aac`
- name: `??$?0$0CJ@@StringReference@Internal@Windows@@QEAA@AEAY0CJ@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[41])`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dc20`
- `0x18000de90`

## callees

- `0x180008a68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008a9d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008a9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008a84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008a84`

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
0x180008a68  push    rbx
0x180008a6a  sub     rsp, 20h
0x180008a6e  mov     rbx, rcx
0x180008a71  lea     r8, [rcx+8]; hstringHeader
0x180008a75  mov     r9, rcx; string
0x180008a78  mov     edx, 28h ; '('; length
0x180008a7d  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180008a84  call    cs:__imp_WindowsCreateStringReference
0x180008a8a  test    eax, eax
0x180008a8c  jns     short loc_180008AA3
0x180008a8e  xor     r9d, r9d; lpArguments
0x180008a91  xor     r8d, r8d; nNumberOfArguments
0x180008a94  mov     ecx, 0C000000Dh; dwExceptionCode
0x180008a99  lea     edx, [r9+1]; dwExceptionFlags
0x180008a9d  call    cs:__imp_RaiseException
0x180008aa3  mov     rax, rbx
0x180008aa6  add     rsp, 20h
0x180008aaa  pop     rbx
0x180008aab  retn
```
