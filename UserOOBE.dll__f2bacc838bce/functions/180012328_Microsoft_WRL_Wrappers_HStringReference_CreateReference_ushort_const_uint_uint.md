# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180012328`
- end: `0x180012369`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `24`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ee5c`
- `0x180011820`
- `0x180012370`
- `0x1800134a4`
- `0x180013760`
- `0x180013b40`
- `0x180014cc4`
- `0x1800157fc`
- `0x1800158f4`
- `0x180015d00`
- `0x180016500`
- `0x1800174a8`
- `0x18001bd7c`
- `0x18001c0e0`
- `0x180027510`
- `0x18002c1b0`
- `0x180038f8c`
- `0x18004112c`
- `0x180042a94`
- `0x180044f58`
- `0x180045adc`
- `0x180045cdc`
- `0x1800465b0`
- `0x180046ab0`

## callees

- `0x180012328`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001235d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001235d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012347`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012347`

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
0x180012328  sub     rsp, 28h
0x18001232c  mov     eax, r9d
0x18001232f  mov     r10, rdx
0x180012332  cmp     r9d, r8d
0x180012335  jb      short loc_18001233B
0x180012337  lea     eax, [r8-1]
0x18001233b  lea     r9, [rcx+18h]; string
0x18001233f  mov     r8, rcx; hstringHeader
0x180012342  mov     rcx, r10; sourceString
0x180012345  mov     edx, eax; length
0x180012347  call    cs:__imp_WindowsCreateStringReference
0x18001234d  test    eax, eax
0x18001234f  jns     short loc_180012364
0x180012351  xor     r9d, r9d; lpArguments
0x180012354  xor     r8d, r8d; nNumberOfArguments
0x180012357  mov     ecx, eax; dwExceptionCode
0x180012359  lea     edx, [r9+1]; dwExceptionFlags
0x18001235d  call    cs:__imp_RaiseException
0x180012363  int     3; Trap to Debugger
0x180012364  add     rsp, 28h
0x180012368  retn
```
