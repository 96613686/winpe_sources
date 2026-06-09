# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180016c24`
- end: `0x180016c65`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `22`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800116bc`
- `0x180023c54`
- `0x180027b8c`
- `0x18002ab1c`
- `0x18004efec`
- `0x18004f1f4`
- `0x18004f79c`
- `0x18005291c`
- `0x18006d0ac`
- `0x18006da1c`
- `0x18006dc3c`
- `0x180071c88`
- `0x1800750cc`
- `0x180075354`
- `0x180083f28`
- `0x180086774`
- `0x18008972c`
- `0x18008995c`
- `0x180089cbc`
- `0x18008b5c0`
- `0x18008b90c`
- `0x18008c380`

## callees

- `0x180016c24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016c59`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016c59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016c43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180016c43`

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
0x180016c24  sub     rsp, 28h
0x180016c28  mov     eax, r9d
0x180016c2b  mov     r10, rdx
0x180016c2e  cmp     r9d, r8d
0x180016c31  jb      short loc_180016C37
0x180016c33  lea     eax, [r8-1]
0x180016c37  lea     r9, [rcx+18h]; string
0x180016c3b  mov     r8, rcx; hstringHeader
0x180016c3e  mov     rcx, r10; sourceString
0x180016c41  mov     edx, eax; length
0x180016c43  call    cs:__imp_WindowsCreateStringReference
0x180016c49  test    eax, eax
0x180016c4b  jns     short loc_180016C60
0x180016c4d  xor     r9d, r9d; lpArguments
0x180016c50  xor     r8d, r8d; nNumberOfArguments
0x180016c53  mov     ecx, eax; dwExceptionCode
0x180016c55  lea     edx, [r9+1]; dwExceptionFlags
0x180016c59  call    cs:__imp_RaiseException
0x180016c5f  int     3; Trap to Debugger
0x180016c60  add     rsp, 28h
0x180016c64  retn
```
