# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18001eaf0`
- end: `0x18001eb31`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002710`
- `0x18001e8a8`

## callees

- `0x18001eaf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001eb25`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001eb25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001eb0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001eb0f`

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
0x18001eaf0  sub     rsp, 28h
0x18001eaf4  mov     eax, r9d
0x18001eaf7  mov     r10, rdx
0x18001eafa  cmp     r9d, r8d
0x18001eafd  jb      short loc_18001EB03
0x18001eaff  lea     eax, [r8-1]
0x18001eb03  lea     r9, [rcx+18h]; string
0x18001eb07  mov     r8, rcx; hstringHeader
0x18001eb0a  mov     rcx, r10; sourceString
0x18001eb0d  mov     edx, eax; length
0x18001eb0f  call    cs:__imp_WindowsCreateStringReference
0x18001eb15  test    eax, eax
0x18001eb17  jns     short loc_18001EB2C
0x18001eb19  xor     r9d, r9d; lpArguments
0x18001eb1c  xor     r8d, r8d; nNumberOfArguments
0x18001eb1f  mov     ecx, eax; dwExceptionCode
0x18001eb21  lea     edx, [r9+1]; dwExceptionFlags
0x18001eb25  call    cs:__imp_RaiseException
0x18001eb2b  int     3; Trap to Debugger
0x18001eb2c  add     rsp, 28h
0x18001eb30  retn
```
