# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180010c14`
- end: `0x180010c55`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800132f8`
- `0x180013408`
- `0x180015fe0`
- `0x18001b1d0`

## callees

- `0x180010c14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010c49`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010c49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010c33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010c33`

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
0x180010c14  sub     rsp, 28h
0x180010c18  mov     eax, r9d
0x180010c1b  mov     r10, rdx
0x180010c1e  cmp     r9d, r8d
0x180010c21  jb      short loc_180010C27
0x180010c23  lea     eax, [r8-1]
0x180010c27  lea     r9, [rcx+18h]; string
0x180010c2b  mov     r8, rcx; hstringHeader
0x180010c2e  mov     rcx, r10; sourceString
0x180010c31  mov     edx, eax; length
0x180010c33  call    cs:__imp_WindowsCreateStringReference
0x180010c39  test    eax, eax
0x180010c3b  jns     short loc_180010C50
0x180010c3d  xor     r9d, r9d; lpArguments
0x180010c40  xor     r8d, r8d; nNumberOfArguments
0x180010c43  mov     ecx, eax; dwExceptionCode
0x180010c45  lea     edx, [r9+1]; dwExceptionFlags
0x180010c49  call    cs:__imp_RaiseException
0x180010c4f  int     3; Trap to Debugger
0x180010c50  add     rsp, 28h
0x180010c54  retn
```
