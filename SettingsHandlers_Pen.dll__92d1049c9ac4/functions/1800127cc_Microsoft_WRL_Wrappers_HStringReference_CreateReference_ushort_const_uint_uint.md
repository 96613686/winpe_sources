# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800127cc`
- end: `0x18001280d`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000cb8c`
- `0x180013fc0`
- `0x1800149d4`
- `0x180016400`
- `0x180019af4`
- `0x180022654`
- `0x180051668`

## callees

- `0x1800127cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012801`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012801`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800127eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800127eb`

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
0x1800127cc  sub     rsp, 28h
0x1800127d0  mov     eax, r9d
0x1800127d3  mov     r10, rdx
0x1800127d6  cmp     r9d, r8d
0x1800127d9  jb      short loc_1800127DF
0x1800127db  lea     eax, [r8-1]
0x1800127df  lea     r9, [rcx+18h]; string
0x1800127e3  mov     r8, rcx; hstringHeader
0x1800127e6  mov     rcx, r10; sourceString
0x1800127e9  mov     edx, eax; length
0x1800127eb  call    cs:__imp_WindowsCreateStringReference
0x1800127f1  test    eax, eax
0x1800127f3  jns     short loc_180012808
0x1800127f5  xor     r9d, r9d; lpArguments
0x1800127f8  xor     r8d, r8d; nNumberOfArguments
0x1800127fb  mov     ecx, eax; dwExceptionCode
0x1800127fd  lea     edx, [r9+1]; dwExceptionFlags
0x180012801  call    cs:__imp_RaiseException
0x180012807  int     3; Trap to Debugger
0x180012808  add     rsp, 28h
0x18001280c  retn
```
