# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180010a14`
- end: `0x180010a55`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f8bc`
- `0x180010a5c`
- `0x18001248c`

## callees

- `0x180010a14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010a49`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010a49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010a33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010a33`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        HSTRING_HEADER *hstringHeader,
        PCWSTR sourceString,
        UINT32 a3,
        UINT32 a4)
{
  UINT32 v4; // eax
  HRESULT StringReference; // eax

  v4 = a4;
  if ( a4 >= a3 )
    v4 = a3 - 1;
  StringReference = WindowsCreateStringReference(sourceString, v4, hstringHeader, (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
}

```

## disassembly

```asm
0x180010a14  sub     rsp, 28h
0x180010a18  mov     eax, r9d
0x180010a1b  mov     r10, rdx
0x180010a1e  cmp     r9d, r8d
0x180010a21  jb      short loc_180010A27
0x180010a23  lea     eax, [r8-1]
0x180010a27  lea     r9, [rcx+18h]; string
0x180010a2b  mov     r8, rcx; hstringHeader
0x180010a2e  mov     rcx, r10; sourceString
0x180010a31  mov     edx, eax; length
0x180010a33  call    cs:__imp_WindowsCreateStringReference
0x180010a39  test    eax, eax
0x180010a3b  jns     short loc_180010A50
0x180010a3d  xor     r9d, r9d; lpArguments
0x180010a40  xor     r8d, r8d; nNumberOfArguments
0x180010a43  mov     ecx, eax; dwExceptionCode
0x180010a45  lea     edx, [r9+1]; dwExceptionFlags
0x180010a49  call    cs:__imp_RaiseException
0x180010a4f  int     3; Trap to Debugger
0x180010a50  add     rsp, 28h
0x180010a54  retn
```
