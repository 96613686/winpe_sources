# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18000d65c`
- end: `0x18000d69d`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000aaf8`
- `0x18000abe0`
- `0x18000c7d0`
- `0x18000ff48`
- `0x18001b0c0`
- `0x180022744`
- `0x18002321c`
- `0x1800233c0`
- `0x180039ec0`

## callees

- `0x18000d65c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d691`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d691`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d67b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d67b`

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
0x18000d65c  sub     rsp, 28h
0x18000d660  mov     eax, r9d
0x18000d663  mov     r10, rdx
0x18000d666  cmp     r9d, r8d
0x18000d669  jb      short loc_18000D66F
0x18000d66b  lea     eax, [r8-1]
0x18000d66f  lea     r9, [rcx+18h]; string
0x18000d673  mov     r8, rcx; hstringHeader
0x18000d676  mov     rcx, r10; sourceString
0x18000d679  mov     edx, eax; length
0x18000d67b  call    cs:__imp_WindowsCreateStringReference
0x18000d681  test    eax, eax
0x18000d683  jns     short loc_18000D698
0x18000d685  xor     r9d, r9d; lpArguments
0x18000d688  xor     r8d, r8d; nNumberOfArguments
0x18000d68b  mov     ecx, eax; dwExceptionCode
0x18000d68d  lea     edx, [r9+1]; dwExceptionFlags
0x18000d691  call    cs:__imp_RaiseException
0x18000d697  int     3; Trap to Debugger
0x18000d698  add     rsp, 28h
0x18000d69c  retn
```
