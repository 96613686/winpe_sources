# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18001d3e0`
- end: `0x18001d423`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `67`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d188`
- `0x18001d364`
- `0x18002ee68`
- `0x18006052c`
- `0x180065380`
- `0x1800659d8`
- `0x180071e38`

## callees

- `0x18001d3e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001d41c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001d41c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d3fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001d3fb`

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
    JUMPOUT(0x18001D422LL);
  }
}

```

## disassembly

```asm
0x18001d3e0  sub     rsp, 28h
0x18001d3e4  mov     eax, r9d
0x18001d3e7  mov     r10, rdx
0x18001d3ea  cmp     r9d, r8d
0x18001d3ed  jnb     short loc_18001D40A
0x18001d3ef  lea     r9, [rcx+18h]; string
0x18001d3f3  mov     r8, rcx; hstringHeader
0x18001d3f6  mov     rcx, r10; sourceString
0x18001d3f9  mov     edx, eax; length
0x18001d3fb  call    cs:__imp_WindowsCreateStringReference
0x18001d401  test    eax, eax
0x18001d403  js      short loc_18001D410
0x18001d405  add     rsp, 28h
0x18001d409  retn
0x18001d40a  lea     eax, [r8-1]
0x18001d40e  jmp     short loc_18001D3EF
0x18001d410  xor     r9d, r9d; lpArguments
0x18001d413  xor     r8d, r8d; nNumberOfArguments
0x18001d416  mov     ecx, eax; dwExceptionCode
0x18001d418  lea     edx, [r9+1]; dwExceptionFlags
0x18001d41c  call    cs:__imp_RaiseException
```
