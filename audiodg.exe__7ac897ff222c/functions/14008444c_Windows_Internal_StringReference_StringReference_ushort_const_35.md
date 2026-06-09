# Windows::Internal::StringReference::StringReference(ushort const (&)[35])

- ea: `0x14008444c`
- end: `0x140084490`
- name: `??$?0$0CD@@StringReference@Internal@Windows@@QEAA@AEAY0CD@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[35])`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140050440`
- `0x14008b1c0`

## callees

- `0x14008444c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140084481`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140084481`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140084468`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140084468`

## string_xrefs

- `0x140084461`: `Windows.Storage.Streams.DataReader`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[35])
{
  if ( WindowsCreateStringReference(
         L"Windows.Storage.Streams.DataReader",
         0x22u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x14008444c  push    rbx
0x14008444e  sub     rsp, 20h
0x140084452  mov     rbx, rcx
0x140084455  lea     r8, [rcx+8]; hstringHeader
0x140084459  mov     r9, rcx; string
0x14008445c  mov     edx, 22h ; '"'; length
0x140084461  lea     rcx, ?RuntimeClass_Windows_Storage_Streams_DataReader@@3QBGB; "Windows.Storage.Streams.DataReader"
0x140084468  call    cs:__imp_WindowsCreateStringReference
0x14008446e  test    eax, eax
0x140084470  jns     short loc_140084487
0x140084472  xor     r9d, r9d; lpArguments
0x140084475  xor     r8d, r8d; nNumberOfArguments
0x140084478  mov     ecx, 0C000000Dh; dwExceptionCode
0x14008447d  lea     edx, [r9+1]; dwExceptionFlags
0x140084481  call    cs:__imp_RaiseException
0x140084487  mov     rax, rbx
0x14008448a  add     rsp, 20h
0x14008448e  pop     rbx
0x14008448f  retn
```
