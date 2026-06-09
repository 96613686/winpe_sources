# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180009cb0`
- end: `0x180009cf1`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008b4c`
- `0x1800164b0`
- `0x1800166a0`
- `0x1800167f0`
- `0x1800169e0`
- `0x18002603c`
- `0x180026330`

## callees

- `0x180009cb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009ce5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180009ce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009ccf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180009ccf`

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
0x180009cb0  sub     rsp, 28h
0x180009cb4  mov     eax, r9d
0x180009cb7  mov     r10, rdx
0x180009cba  cmp     r9d, r8d
0x180009cbd  jb      short loc_180009CC3
0x180009cbf  lea     eax, [r8-1]
0x180009cc3  lea     r9, [rcx+18h]; string
0x180009cc7  mov     r8, rcx; hstringHeader
0x180009cca  mov     rcx, r10; sourceString
0x180009ccd  mov     edx, eax; length
0x180009ccf  call    cs:__imp_WindowsCreateStringReference
0x180009cd5  test    eax, eax
0x180009cd7  jns     short loc_180009CEC
0x180009cd9  xor     r9d, r9d; lpArguments
0x180009cdc  xor     r8d, r8d; nNumberOfArguments
0x180009cdf  mov     ecx, eax; dwExceptionCode
0x180009ce1  lea     edx, [r9+1]; dwExceptionFlags
0x180009ce5  call    cs:__imp_RaiseException
0x180009ceb  int     3; Trap to Debugger
0x180009cec  add     rsp, 28h
0x180009cf0  retn
```
