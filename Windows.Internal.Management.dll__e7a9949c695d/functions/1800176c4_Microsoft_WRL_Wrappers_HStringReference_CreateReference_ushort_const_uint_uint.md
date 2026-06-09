# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800176c4`
- end: `0x180017705`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `14`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016b74`
- `0x1800250d8`
- `0x180028068`
- `0x1800300a0`
- `0x180030378`
- `0x18003d4c4`
- `0x180041390`
- `0x18004c770`
- `0x18005aa50`
- `0x18006c0c4`
- `0x1800746ac`
- `0x1800767b0`
- `0x180095ec8`
- `0x18009a308`

## callees

- `0x1800176c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800176f9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800176f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800176e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800176e3`

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
0x1800176c4  sub     rsp, 28h
0x1800176c8  mov     eax, r9d
0x1800176cb  mov     r10, rdx
0x1800176ce  cmp     r9d, r8d
0x1800176d1  jb      short loc_1800176D7
0x1800176d3  lea     eax, [r8-1]
0x1800176d7  lea     r9, [rcx+18h]; string
0x1800176db  mov     r8, rcx; hstringHeader
0x1800176de  mov     rcx, r10; sourceString
0x1800176e1  mov     edx, eax; length
0x1800176e3  call    cs:__imp_WindowsCreateStringReference
0x1800176e9  test    eax, eax
0x1800176eb  jns     short loc_180017700
0x1800176ed  xor     r9d, r9d; lpArguments
0x1800176f0  xor     r8d, r8d; nNumberOfArguments
0x1800176f3  mov     ecx, eax; dwExceptionCode
0x1800176f5  lea     edx, [r9+1]; dwExceptionFlags
0x1800176f9  call    cs:__imp_RaiseException
0x1800176ff  int     3; Trap to Debugger
0x180017700  add     rsp, 28h
0x180017704  retn
```
