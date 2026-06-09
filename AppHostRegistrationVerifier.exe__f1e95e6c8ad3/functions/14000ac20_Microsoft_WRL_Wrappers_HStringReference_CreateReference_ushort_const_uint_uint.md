# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x14000ac20`
- end: `0x14000ac61`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000834c`
- `0x14000bc30`
- `0x14000c848`

## callees

- `0x14000ac20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000ac55`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000ac55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000ac3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000ac3f`

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
0x14000ac20  sub     rsp, 28h
0x14000ac24  mov     eax, r9d
0x14000ac27  mov     r10, rdx
0x14000ac2a  cmp     r9d, r8d
0x14000ac2d  jb      short loc_14000AC33
0x14000ac2f  lea     eax, [r8-1]
0x14000ac33  lea     r9, [rcx+18h]; string
0x14000ac37  mov     r8, rcx; hstringHeader
0x14000ac3a  mov     rcx, r10; sourceString
0x14000ac3d  mov     edx, eax; length
0x14000ac3f  call    cs:__imp_WindowsCreateStringReference
0x14000ac45  test    eax, eax
0x14000ac47  jns     short loc_14000AC5C
0x14000ac49  xor     r9d, r9d; lpArguments
0x14000ac4c  xor     r8d, r8d; nNumberOfArguments
0x14000ac4f  mov     ecx, eax; dwExceptionCode
0x14000ac51  lea     edx, [r9+1]; dwExceptionFlags
0x14000ac55  call    cs:__imp_RaiseException
0x14000ac5b  int     3; Trap to Debugger
0x14000ac5c  add     rsp, 28h
0x14000ac60  retn
```
