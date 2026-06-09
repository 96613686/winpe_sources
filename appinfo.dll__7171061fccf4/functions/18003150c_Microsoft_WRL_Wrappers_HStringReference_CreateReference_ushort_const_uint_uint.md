# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18003150c`
- end: `0x18003154d`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000d974`
- `0x180029c9c`
- `0x18002b27c`
- `0x180037274`

## callees

- `0x18003150c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180031541`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180031541`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003152b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003152b`

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
0x18003150c  sub     rsp, 28h
0x180031510  mov     eax, r9d
0x180031513  mov     r10, rdx
0x180031516  cmp     r9d, r8d
0x180031519  jb      short loc_18003151F
0x18003151b  lea     eax, [r8-1]
0x18003151f  lea     r9, [rcx+18h]; string
0x180031523  mov     r8, rcx; hstringHeader
0x180031526  mov     rcx, r10; sourceString
0x180031529  mov     edx, eax; length
0x18003152b  call    cs:__imp_WindowsCreateStringReference
0x180031531  test    eax, eax
0x180031533  jns     short loc_180031548
0x180031535  xor     r9d, r9d; lpArguments
0x180031538  xor     r8d, r8d; nNumberOfArguments
0x18003153b  mov     ecx, eax; dwExceptionCode
0x18003153d  lea     edx, [r9+1]; dwExceptionFlags
0x180031541  call    cs:__imp_RaiseException
0x180031547  int     3; Trap to Debugger
0x180031548  add     rsp, 28h
0x18003154c  retn
```
