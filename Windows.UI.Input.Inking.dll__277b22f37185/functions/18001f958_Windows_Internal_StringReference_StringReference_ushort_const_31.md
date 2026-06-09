# Windows::Internal::StringReference::StringReference(ushort const (&)[31])

- ea: `0x18001f958`
- end: `0x18001f99c`
- name: `??$?0$0BP@@StringReference@Internal@Windows@@QEAA@AEAY0BP@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[31])`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180030750`

## callees

- `0x18001f958`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001f98d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001f98d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f974`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f974`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[31])
{
  if ( WindowsCreateStringReference(L"Windows.Storage.Streams.Buffer", 0x1Eu, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18001f958  push    rbx
0x18001f95a  sub     rsp, 20h
0x18001f95e  mov     rbx, rcx
0x18001f961  lea     r8, [rcx+8]; hstringHeader
0x18001f965  mov     r9, rcx; string
0x18001f968  mov     edx, 1Eh; length
0x18001f96d  lea     rcx, ?RuntimeClass_Windows_Storage_Streams_Buffer@@3QBGB; "Windows.Storage.Streams.Buffer"
0x18001f974  call    cs:__imp_WindowsCreateStringReference
0x18001f97a  test    eax, eax
0x18001f97c  jns     short loc_18001F993
0x18001f97e  xor     r9d, r9d; lpArguments
0x18001f981  xor     r8d, r8d; nNumberOfArguments
0x18001f984  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001f989  lea     edx, [r9+1]; dwExceptionFlags
0x18001f98d  call    cs:__imp_RaiseException
0x18001f993  mov     rax, rbx
0x18001f996  add     rsp, 20h
0x18001f99a  pop     rbx
0x18001f99b  retn
```
