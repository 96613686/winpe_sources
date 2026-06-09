# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18001bf68`
- end: `0x18001bfa9`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `19`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001bfb0`
- `0x180026314`
- `0x18002666c`
- `0x180026850`
- `0x180027b20`
- `0x180030a64`
- `0x180032a28`
- `0x180033a10`
- `0x180038dd4`
- `0x18003f074`
- `0x18004449c`
- `0x180044a94`
- `0x180045828`
- `0x180045dc4`
- `0x18004ad6c`
- `0x18004b8f0`
- `0x18004baf0`
- `0x18004c3c0`
- `0x18004c8e0`

## callees

- `0x18001bf68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001bf9d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001bf9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001bf87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001bf87`

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
0x18001bf68  sub     rsp, 28h
0x18001bf6c  mov     eax, r9d
0x18001bf6f  mov     r10, rdx
0x18001bf72  cmp     r9d, r8d
0x18001bf75  jb      short loc_18001BF7B
0x18001bf77  lea     eax, [r8-1]
0x18001bf7b  lea     r9, [rcx+18h]; string
0x18001bf7f  mov     r8, rcx; hstringHeader
0x18001bf82  mov     rcx, r10; sourceString
0x18001bf85  mov     edx, eax; length
0x18001bf87  call    cs:__imp_WindowsCreateStringReference
0x18001bf8d  test    eax, eax
0x18001bf8f  jns     short loc_18001BFA4
0x18001bf91  xor     r9d, r9d; lpArguments
0x18001bf94  xor     r8d, r8d; nNumberOfArguments
0x18001bf97  mov     ecx, eax; dwExceptionCode
0x18001bf99  lea     edx, [r9+1]; dwExceptionFlags
0x18001bf9d  call    cs:__imp_RaiseException
0x18001bfa3  int     3; Trap to Debugger
0x18001bfa4  add     rsp, 28h
0x18001bfa8  retn
```
