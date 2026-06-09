# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18000e958`
- end: `0x18000e999`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `26`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800028b0`
- `0x1800028f0`
- `0x180002930`
- `0x180002970`
- `0x1800029b0`
- `0x1800029f0`
- `0x180002a30`
- `0x180002a70`
- `0x180002c30`
- `0x180002c70`
- `0x180002cb0`
- `0x180002cf0`
- `0x180002d30`
- `0x180002d70`
- `0x180002db0`
- `0x180002df0`
- `0x180002eb0`
- `0x18000b48c`
- `0x180016044`
- `0x18001c58c`
- `0x1800247a0`
- `0x180026e10`
- `0x18002b21c`
- `0x18002e654`
- `0x18003cd90`
- `0x18003eaa4`

## callees

- `0x18000e958`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e98d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e98d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e977`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e977`

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
0x18000e958  sub     rsp, 28h
0x18000e95c  mov     eax, r9d
0x18000e95f  mov     r10, rdx
0x18000e962  cmp     r9d, r8d
0x18000e965  jb      short loc_18000E96B
0x18000e967  lea     eax, [r8-1]
0x18000e96b  lea     r9, [rcx+18h]; string
0x18000e96f  mov     r8, rcx; hstringHeader
0x18000e972  mov     rcx, r10; sourceString
0x18000e975  mov     edx, eax; length
0x18000e977  call    cs:__imp_WindowsCreateStringReference
0x18000e97d  test    eax, eax
0x18000e97f  jns     short loc_18000E994
0x18000e981  xor     r9d, r9d; lpArguments
0x18000e984  xor     r8d, r8d; nNumberOfArguments
0x18000e987  mov     ecx, eax; dwExceptionCode
0x18000e989  lea     edx, [r9+1]; dwExceptionFlags
0x18000e98d  call    cs:__imp_RaiseException
0x18000e993  int     3; Trap to Debugger
0x18000e994  add     rsp, 28h
0x18000e998  retn
```
