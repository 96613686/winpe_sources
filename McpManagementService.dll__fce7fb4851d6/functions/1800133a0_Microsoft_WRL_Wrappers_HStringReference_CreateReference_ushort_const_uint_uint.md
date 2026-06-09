# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800133a0`
- end: `0x1800133e1`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f7a4`
- `0x180016b54`
- `0x180017b98`
- `0x18001ef30`
- `0x18001f77c`
- `0x18001f9a4`
- `0x1800203b0`
- `0x180020e9c`
- `0x1800256ac`

## callees

- `0x1800133a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800133d5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800133d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800133bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800133bf`

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
0x1800133a0  sub     rsp, 28h
0x1800133a4  mov     eax, r9d
0x1800133a7  mov     r10, rdx
0x1800133aa  cmp     r9d, r8d
0x1800133ad  jb      short loc_1800133B3
0x1800133af  lea     eax, [r8-1]
0x1800133b3  lea     r9, [rcx+18h]; string
0x1800133b7  mov     r8, rcx; hstringHeader
0x1800133ba  mov     rcx, r10; sourceString
0x1800133bd  mov     edx, eax; length
0x1800133bf  call    cs:__imp_WindowsCreateStringReference
0x1800133c5  test    eax, eax
0x1800133c7  jns     short loc_1800133DC
0x1800133c9  xor     r9d, r9d; lpArguments
0x1800133cc  xor     r8d, r8d; nNumberOfArguments
0x1800133cf  mov     ecx, eax; dwExceptionCode
0x1800133d1  lea     edx, [r9+1]; dwExceptionFlags
0x1800133d5  call    cs:__imp_RaiseException
0x1800133db  int     3; Trap to Debugger
0x1800133dc  add     rsp, 28h
0x1800133e0  retn
```
