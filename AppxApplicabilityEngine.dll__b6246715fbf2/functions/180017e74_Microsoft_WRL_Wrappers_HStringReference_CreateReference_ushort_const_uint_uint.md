# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180017e74`
- end: `0x180017eb5`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180017d70`
- `0x18001e910`

## callees

- `0x180017e74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017ea9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017ea9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017e93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017e93`

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
0x180017e74  sub     rsp, 28h
0x180017e78  mov     eax, r9d
0x180017e7b  mov     r10, rdx
0x180017e7e  cmp     r9d, r8d
0x180017e81  jb      short loc_180017E87
0x180017e83  lea     eax, [r8-1]
0x180017e87  lea     r9, [rcx+18h]; string
0x180017e8b  mov     r8, rcx; hstringHeader
0x180017e8e  mov     rcx, r10; sourceString
0x180017e91  mov     edx, eax; length
0x180017e93  call    cs:__imp_WindowsCreateStringReference
0x180017e99  test    eax, eax
0x180017e9b  jns     short loc_180017EB0
0x180017e9d  xor     r9d, r9d; lpArguments
0x180017ea0  xor     r8d, r8d; nNumberOfArguments
0x180017ea3  mov     ecx, eax; dwExceptionCode
0x180017ea5  lea     edx, [r9+1]; dwExceptionFlags
0x180017ea9  call    cs:__imp_RaiseException
0x180017eaf  int     3; Trap to Debugger
0x180017eb0  add     rsp, 28h
0x180017eb4  retn
```
