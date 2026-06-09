# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180015cb0`
- end: `0x180015cf1`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001415c`
- `0x180023584`

## callees

- `0x180015cb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015ce5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015ce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015ccf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015ccf`

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
0x180015cb0  sub     rsp, 28h
0x180015cb4  mov     eax, r9d
0x180015cb7  mov     r10, rdx
0x180015cba  cmp     r9d, r8d
0x180015cbd  jb      short loc_180015CC3
0x180015cbf  lea     eax, [r8-1]
0x180015cc3  lea     r9, [rcx+18h]; string
0x180015cc7  mov     r8, rcx; hstringHeader
0x180015cca  mov     rcx, r10; sourceString
0x180015ccd  mov     edx, eax; length
0x180015ccf  call    cs:__imp_WindowsCreateStringReference
0x180015cd5  test    eax, eax
0x180015cd7  jns     short loc_180015CEC
0x180015cd9  xor     r9d, r9d; lpArguments
0x180015cdc  xor     r8d, r8d; nNumberOfArguments
0x180015cdf  mov     ecx, eax; dwExceptionCode
0x180015ce1  lea     edx, [r9+1]; dwExceptionFlags
0x180015ce5  call    cs:__imp_RaiseException
0x180015ceb  int     3; Trap to Debugger
0x180015cec  add     rsp, 28h
0x180015cf0  retn
```
