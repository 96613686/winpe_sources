# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18003f9c8`
- end: `0x18003fa09`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800133a0`
- `0x180015e48`
- `0x1800401e8`
- `0x18004489c`
- `0x180044db4`
- `0x1800512f4`
- `0x180051988`
- `0x180054c4c`
- `0x180055f04`
- `0x18005715c`
- `0x18005ddb4`
- `0x18005ee24`
- `0x180060290`
- `0x180061944`
- `0x180061b0c`

## callees

- `0x18003f9c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003f9fd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003f9fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003f9e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003f9e7`

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
0x18003f9c8  sub     rsp, 28h
0x18003f9cc  mov     eax, r9d
0x18003f9cf  mov     r10, rdx
0x18003f9d2  cmp     r9d, r8d
0x18003f9d5  jb      short loc_18003F9DB
0x18003f9d7  lea     eax, [r8-1]
0x18003f9db  lea     r9, [rcx+18h]; string
0x18003f9df  mov     r8, rcx; hstringHeader
0x18003f9e2  mov     rcx, r10; sourceString
0x18003f9e5  mov     edx, eax; length
0x18003f9e7  call    cs:__imp_WindowsCreateStringReference
0x18003f9ed  test    eax, eax
0x18003f9ef  jns     short loc_18003FA04
0x18003f9f1  xor     r9d, r9d; lpArguments
0x18003f9f4  xor     r8d, r8d; nNumberOfArguments
0x18003f9f7  mov     ecx, eax; dwExceptionCode
0x18003f9f9  lea     edx, [r9+1]; dwExceptionFlags
0x18003f9fd  call    cs:__imp_RaiseException
0x18003fa03  int     3; Trap to Debugger
0x18003fa04  add     rsp, 28h
0x18003fa08  retn
```
