# Windows::Internal::StringReference::StringReference(ushort const (&)[51])

- ea: `0x18001fa3c`
- end: `0x18001fa80`
- name: `??$?0$0DD@@StringReference@Internal@Windows@@QEAA@AEAY0DD@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[51])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800248d8`

## callees

- `0x18001fa3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fa71`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001fa71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001fa58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001fa58`

## string_xrefs

- `0x18001fa51`: `Windows.Storage.Streams.InMemoryRandomAccessStream`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[51])
{
  if ( WindowsCreateStringReference(
         L"Windows.Storage.Streams.InMemoryRandomAccessStream",
         0x32u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18001fa3c  push    rbx
0x18001fa3e  sub     rsp, 20h
0x18001fa42  mov     rbx, rcx
0x18001fa45  lea     r8, [rcx+8]; hstringHeader
0x18001fa49  mov     r9, rcx; string
0x18001fa4c  mov     edx, 32h ; '2'; length
0x18001fa51  lea     rcx, ?RuntimeClass_Windows_Storage_Streams_InMemoryRandomAccessStream@@3QBGB; "Windows.Storage.Streams.InMemoryRandomA"...
0x18001fa58  call    cs:__imp_WindowsCreateStringReference
0x18001fa5e  test    eax, eax
0x18001fa60  jns     short loc_18001FA77
0x18001fa62  xor     r9d, r9d; lpArguments
0x18001fa65  xor     r8d, r8d; nNumberOfArguments
0x18001fa68  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001fa6d  lea     edx, [r9+1]; dwExceptionFlags
0x18001fa71  call    cs:__imp_RaiseException
0x18001fa77  mov     rax, rbx
0x18001fa7a  add     rsp, 20h
0x18001fa7e  pop     rbx
0x18001fa7f  retn
```
