# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18000ade0`
- end: `0x18000ae21`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000cad0`
- `0x180011b80`
- `0x180013fd0`
- `0x180014044`
- `0x180016c90`
- `0x180018750`
- `0x18001b2c0`
- `0x18001b7e8`
- `0x18001bb10`
- `0x18001bde0`
- `0x18001bed0`
- `0x18001c144`

## callees

- `0x18000ade0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ae15`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ae15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000adff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000adff`

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
0x18000ade0  sub     rsp, 28h
0x18000ade4  mov     eax, r9d
0x18000ade7  mov     r10, rdx
0x18000adea  cmp     r9d, r8d
0x18000aded  jb      short loc_18000ADF3
0x18000adef  lea     eax, [r8-1]
0x18000adf3  lea     r9, [rcx+18h]; string
0x18000adf7  mov     r8, rcx; hstringHeader
0x18000adfa  mov     rcx, r10; sourceString
0x18000adfd  mov     edx, eax; length
0x18000adff  call    cs:__imp_WindowsCreateStringReference
0x18000ae05  test    eax, eax
0x18000ae07  jns     short loc_18000AE1C
0x18000ae09  xor     r9d, r9d; lpArguments
0x18000ae0c  xor     r8d, r8d; nNumberOfArguments
0x18000ae0f  mov     ecx, eax; dwExceptionCode
0x18000ae11  lea     edx, [r9+1]; dwExceptionFlags
0x18000ae15  call    cs:__imp_RaiseException
0x18000ae1b  int     3; Trap to Debugger
0x18000ae1c  add     rsp, 28h
0x18000ae20  retn
```
