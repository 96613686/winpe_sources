# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18000f7b4`
- end: `0x18000f7f5`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `13`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b894`
- `0x180010f5c`
- `0x180011fe0`
- `0x180012f30`
- `0x180015d0c`
- `0x180016050`
- `0x180016370`
- `0x180016540`
- `0x1800167e0`
- `0x1800169d8`
- `0x180016dc4`
- `0x18001e748`
- `0x18001ea40`

## callees

- `0x18000f7b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f7e9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f7e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f7d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f7d3`

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
0x18000f7b4  sub     rsp, 28h
0x18000f7b8  mov     eax, r9d
0x18000f7bb  mov     r10, rdx
0x18000f7be  cmp     r9d, r8d
0x18000f7c1  jb      short loc_18000F7C7
0x18000f7c3  lea     eax, [r8-1]
0x18000f7c7  lea     r9, [rcx+18h]; string
0x18000f7cb  mov     r8, rcx; hstringHeader
0x18000f7ce  mov     rcx, r10; sourceString
0x18000f7d1  mov     edx, eax; length
0x18000f7d3  call    cs:__imp_WindowsCreateStringReference
0x18000f7d9  test    eax, eax
0x18000f7db  jns     short loc_18000F7F0
0x18000f7dd  xor     r9d, r9d; lpArguments
0x18000f7e0  xor     r8d, r8d; nNumberOfArguments
0x18000f7e3  mov     ecx, eax; dwExceptionCode
0x18000f7e5  lea     edx, [r9+1]; dwExceptionFlags
0x18000f7e9  call    cs:__imp_RaiseException
0x18000f7ef  int     3; Trap to Debugger
0x18000f7f0  add     rsp, 28h
0x18000f7f4  retn
```
