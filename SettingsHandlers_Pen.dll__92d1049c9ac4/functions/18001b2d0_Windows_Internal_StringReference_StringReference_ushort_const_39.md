# Windows::Internal::StringReference::StringReference(ushort const (&)[39])

- ea: `0x18001b2d0`
- end: `0x18001b314`
- name: `??$?0$0CH@@StringReference@Internal@Windows@@QEAA@AEAY0CH@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[39])`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002b6d0`
- `0x18002c690`

## callees

- `0x18001b2d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b305`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001b305`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b2ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b2ec`

## string_xrefs

- `0x18001b2e5`: `Windows.Storage.Pickers.FileOpenPicker`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[39])
{
  if ( WindowsCreateStringReference(
         L"Windows.Storage.Pickers.FileOpenPicker",
         0x26u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18001b2d0  push    rbx
0x18001b2d2  sub     rsp, 20h
0x18001b2d6  mov     rbx, rcx
0x18001b2d9  lea     r8, [rcx+8]; hstringHeader
0x18001b2dd  mov     r9, rcx; string
0x18001b2e0  mov     edx, 26h ; '&'; length
0x18001b2e5  lea     rcx, ?RuntimeClass_Windows_Storage_Pickers_FileOpenPicker@@3QBGB; "Windows.Storage.Pickers.FileOpenPicker"
0x18001b2ec  call    cs:__imp_WindowsCreateStringReference
0x18001b2f2  test    eax, eax
0x18001b2f4  jns     short loc_18001B30B
0x18001b2f6  xor     r9d, r9d; lpArguments
0x18001b2f9  xor     r8d, r8d; nNumberOfArguments
0x18001b2fc  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001b301  lea     edx, [r9+1]; dwExceptionFlags
0x18001b305  call    cs:__imp_RaiseException
0x18001b30b  mov     rax, rbx
0x18001b30e  add     rsp, 20h
0x18001b312  pop     rbx
0x18001b313  retn
```
