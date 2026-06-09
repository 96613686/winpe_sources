# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800059e0`
- end: `0x180005a24`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `68`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012dc0`
- `0x180027e4c`
- `0x18002b024`
- `0x180031c00`

## callees

- `0x1800059e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005a1d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180005a1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800059fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800059fb`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        HSTRING_HEADER *hstringHeader,
        PCWSTR sourceString,
        UINT32 a3,
        UINT32 a4)
{
  UINT32 v4; // eax
  signed int StringReference; // eax

  v4 = a4;
  if ( a4 >= a3 )
    v4 = a3 - 1;
  StringReference = WindowsCreateStringReference(sourceString, v4, hstringHeader, (HSTRING *)&hstringHeader[1]);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    JUMPOUT(0x180005A23LL);
  }
}

```

## disassembly

```asm
0x1800059e0  sub     rsp, 28h
0x1800059e4  mov     eax, r9d
0x1800059e7  mov     r10, rdx
0x1800059ea  cmp     r9d, r8d
0x1800059ed  jnb     short loc_180005A0A
0x1800059ef  lea     r9, [rcx+18h]; string
0x1800059f3  mov     r8, rcx; hstringHeader
0x1800059f6  mov     rcx, r10; sourceString
0x1800059f9  mov     edx, eax; length
0x1800059fb  call    cs:__imp_WindowsCreateStringReference
0x180005a01  test    eax, eax
0x180005a03  js      short loc_180005A10
0x180005a05  add     rsp, 28h
0x180005a09  retn
0x180005a0a  lea     eax, [r8-1]
0x180005a0e  jmp     short loc_1800059EF
0x180005a10  xor     r9d, r9d; lpArguments
0x180005a13  xor     r8d, r8d; nNumberOfArguments
0x180005a16  mov     edx, 1; dwExceptionFlags
0x180005a1b  mov     ecx, eax; dwExceptionCode
0x180005a1d  call    cs:__imp_RaiseException
```
