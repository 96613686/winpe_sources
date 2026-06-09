# Windows::Internal::StringReference::StringReference(ushort const (&)[38])

- ea: `0x180008a1c`
- end: `0x180008a60`
- name: `??$?0$0CG@@StringReference@Internal@Windows@@QEAA@AEAY0CG@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[38])`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000969c`
- `0x18000bf00`
- `0x18000dc20`

## callees

- `0x180008a1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008a51`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008a51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008a38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008a38`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[38])
{
  if ( WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.User",
         0x25u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180008a1c  push    rbx
0x180008a1e  sub     rsp, 20h
0x180008a22  mov     rbx, rcx
0x180008a25  lea     r8, [rcx+8]; hstringHeader
0x180008a29  mov     r9, rcx; string
0x180008a2c  mov     edx, 25h ; '%'; length
0x180008a31  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x180008a38  call    cs:__imp_WindowsCreateStringReference
0x180008a3e  test    eax, eax
0x180008a40  jns     short loc_180008A57
0x180008a42  xor     r9d, r9d; lpArguments
0x180008a45  xor     r8d, r8d; nNumberOfArguments
0x180008a48  mov     ecx, 0C000000Dh; dwExceptionCode
0x180008a4d  lea     edx, [r9+1]; dwExceptionFlags
0x180008a51  call    cs:__imp_RaiseException
0x180008a57  mov     rax, rbx
0x180008a5a  add     rsp, 20h
0x180008a5e  pop     rbx
0x180008a5f  retn
```
