# Windows::Internal::StringReference::StringReference(ushort const (&)[62])

- ea: `0x180008b00`
- end: `0x180008b44`
- name: `??$?0$0DO@@StringReference@Internal@Windows@@QEAA@AEAY0DO@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[62])`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cce0`
- `0x18000ce80`
- `0x18000e150`
- `0x1800162f0`
- `0x180018468`

## callees

- `0x180008b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008b35`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008b35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008b1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008b1c`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[62])
{
  if ( WindowsCreateStringReference(
         L"Windows.Internal.StateRepository.Management.RepositoryManager",
         0x3Du,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180008b00  push    rbx
0x180008b02  sub     rsp, 20h
0x180008b06  mov     rbx, rcx
0x180008b09  lea     r8, [rcx+8]; hstringHeader
0x180008b0d  mov     r9, rcx; string
0x180008b10  mov     edx, 3Dh ; '='; length
0x180008b15  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Management_RepositoryManager@@3QBGB; "Windows.Internal.StateRepository.Manage"...
0x180008b1c  call    cs:__imp_WindowsCreateStringReference
0x180008b22  test    eax, eax
0x180008b24  jns     short loc_180008B3B
0x180008b26  xor     r9d, r9d; lpArguments
0x180008b29  xor     r8d, r8d; nNumberOfArguments
0x180008b2c  mov     ecx, 0C000000Dh; dwExceptionCode
0x180008b31  lea     edx, [r9+1]; dwExceptionFlags
0x180008b35  call    cs:__imp_RaiseException
0x180008b3b  mov     rax, rbx
0x180008b3e  add     rsp, 20h
0x180008b42  pop     rbx
0x180008b43  retn
```
