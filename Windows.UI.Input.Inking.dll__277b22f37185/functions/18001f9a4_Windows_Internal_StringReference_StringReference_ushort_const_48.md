# Windows::Internal::StringReference::StringReference(ushort const (&)[48])

- ea: `0x18001f9a4`
- end: `0x18001f9e8`
- name: `??$?0$0DA@@StringReference@Internal@Windows@@QEAA@AEAY0DA@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[48])`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180026e60`
- `0x1800276f0`
- `0x180030750`

## callees

- `0x18001f9a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001f9d9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001f9d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f9c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f9c0`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[48])
{
  if ( WindowsCreateStringReference(
         L"Windows.ApplicationModel.DataTransfer.Clipboard",
         0x2Fu,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18001f9a4  push    rbx
0x18001f9a6  sub     rsp, 20h
0x18001f9aa  mov     rbx, rcx
0x18001f9ad  lea     r8, [rcx+8]; hstringHeader
0x18001f9b1  mov     r9, rcx; string
0x18001f9b4  mov     edx, 2Fh ; '/'; length
0x18001f9b9  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_DataTransfer_Clipboard@@3QBGB; "Windows.ApplicationModel.DataTransfer.C"...
0x18001f9c0  call    cs:__imp_WindowsCreateStringReference
0x18001f9c6  test    eax, eax
0x18001f9c8  jns     short loc_18001F9DF
0x18001f9ca  xor     r9d, r9d; lpArguments
0x18001f9cd  xor     r8d, r8d; nNumberOfArguments
0x18001f9d0  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001f9d5  lea     edx, [r9+1]; dwExceptionFlags
0x18001f9d9  call    cs:__imp_RaiseException
0x18001f9df  mov     rax, rbx
0x18001f9e2  add     rsp, 20h
0x18001f9e6  pop     rbx
0x18001f9e7  retn
```
