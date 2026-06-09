# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180015958`
- end: `0x180015999`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011e44`
- `0x180017c20`

## callees

- `0x180015958`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001598d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001598d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015977`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015977`

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
0x180015958  sub     rsp, 28h
0x18001595c  mov     eax, r9d
0x18001595f  mov     r10, rdx
0x180015962  cmp     r9d, r8d
0x180015965  jb      short loc_18001596B
0x180015967  lea     eax, [r8-1]
0x18001596b  lea     r9, [rcx+18h]; string
0x18001596f  mov     r8, rcx; hstringHeader
0x180015972  mov     rcx, r10; sourceString
0x180015975  mov     edx, eax; length
0x180015977  call    cs:__imp_WindowsCreateStringReference
0x18001597d  test    eax, eax
0x18001597f  jns     short loc_180015994
0x180015981  xor     r9d, r9d; lpArguments
0x180015984  xor     r8d, r8d; nNumberOfArguments
0x180015987  mov     ecx, eax; dwExceptionCode
0x180015989  lea     edx, [r9+1]; dwExceptionFlags
0x18001598d  call    cs:__imp_RaiseException
0x180015993  int     3; Trap to Debugger
0x180015994  add     rsp, 28h
0x180015998  retn
```
