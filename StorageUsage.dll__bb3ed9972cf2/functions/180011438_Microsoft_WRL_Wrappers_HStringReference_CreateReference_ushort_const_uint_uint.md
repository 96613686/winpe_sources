# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180011438`
- end: `0x180011479`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001151c`
- `0x1800116b4`
- `0x1800130b0`
- `0x18001442c`
- `0x180014550`
- `0x180014994`
- `0x180014adc`
- `0x180014cd0`

## callees

- `0x180011438`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001146d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001146d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011457`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011457`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180011438  sub     rsp, 28h
0x18001143c  mov     eax, r9d
0x18001143f  mov     r10, rdx
0x180011442  cmp     r9d, r8d
0x180011445  jb      short loc_18001144B
0x180011447  lea     eax, [r8-1]
0x18001144b  lea     r9, [rcx+18h]; string
0x18001144f  mov     r8, rcx; hstringHeader
0x180011452  mov     rcx, r10; sourceString
0x180011455  mov     edx, eax; length
0x180011457  call    cs:__imp_WindowsCreateStringReference
0x18001145d  test    eax, eax
0x18001145f  jns     short loc_180011474
0x180011461  xor     r9d, r9d; lpArguments
0x180011464  xor     r8d, r8d; nNumberOfArguments
0x180011467  mov     ecx, eax; dwExceptionCode
0x180011469  lea     edx, [r9+1]; dwExceptionFlags
0x18001146d  call    cs:__imp_RaiseException
0x180011473  int     3; Trap to Debugger
0x180011474  add     rsp, 28h
0x180011478  retn
```
