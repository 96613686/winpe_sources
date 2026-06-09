# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18001d0f8`
- end: `0x18001d139`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800149fc`
- `0x180020724`
- `0x180020dcc`
- `0x180021970`
- `0x180025060`
- `0x180025310`
- `0x18002ad2c`
- `0x18002d8a0`
- `0x18002f830`
- `0x18002fe90`
- `0x180040d74`

## callees

- `0x18001d0f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001d12d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001d12d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d117`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d117`

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
0x18001d0f8  sub     rsp, 28h
0x18001d0fc  mov     eax, r9d
0x18001d0ff  mov     r10, rdx
0x18001d102  cmp     r9d, r8d
0x18001d105  jb      short loc_18001D10B
0x18001d107  lea     eax, [r8-1]
0x18001d10b  lea     r9, [rcx+18h]; string
0x18001d10f  mov     r8, rcx; hstringHeader
0x18001d112  mov     rcx, r10; sourceString
0x18001d115  mov     edx, eax; length
0x18001d117  call    cs:__imp_WindowsCreateStringReference
0x18001d11d  test    eax, eax
0x18001d11f  jns     short loc_18001D134
0x18001d121  xor     r9d, r9d; lpArguments
0x18001d124  xor     r8d, r8d; nNumberOfArguments
0x18001d127  mov     ecx, eax; dwExceptionCode
0x18001d129  lea     edx, [r9+1]; dwExceptionFlags
0x18001d12d  call    cs:__imp_RaiseException
0x18001d133  int     3; Trap to Debugger
0x18001d134  add     rsp, 28h
0x18001d138  retn
```
