# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800198bc`
- end: `0x1800198ff`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `67`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001e0f0`
- `0x1800283a8`
- `0x180028854`
- `0x18002a5b0`
- `0x18002b3c0`
- `0x18002b5b4`
- `0x18003d5fc`
- `0x18004bdac`
- `0x18004c76c`
- `0x18004cde8`
- `0x18004d5bc`

## callees

- `0x1800198bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800198f8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800198f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800198d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800198d7`

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
    JUMPOUT(0x1800198FELL);
  }
}

```

## disassembly

```asm
0x1800198bc  sub     rsp, 28h
0x1800198c0  mov     eax, r9d
0x1800198c3  mov     r10, rdx
0x1800198c6  cmp     r9d, r8d
0x1800198c9  jnb     short loc_1800198E6
0x1800198cb  lea     r9, [rcx+18h]; string
0x1800198cf  mov     r8, rcx; hstringHeader
0x1800198d2  mov     rcx, r10; sourceString
0x1800198d5  mov     edx, eax; length
0x1800198d7  call    cs:__imp_WindowsCreateStringReference
0x1800198dd  test    eax, eax
0x1800198df  js      short loc_1800198EC
0x1800198e1  add     rsp, 28h
0x1800198e5  retn
0x1800198e6  lea     eax, [r8-1]
0x1800198ea  jmp     short loc_1800198CB
0x1800198ec  xor     r9d, r9d; lpArguments
0x1800198ef  xor     r8d, r8d; nNumberOfArguments
0x1800198f2  mov     ecx, eax; dwExceptionCode
0x1800198f4  lea     edx, [r9+1]; dwExceptionFlags
0x1800198f8  call    cs:__imp_RaiseException
```
