# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x14000891c`
- end: `0x14000895d`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140008758`
- `0x140009448`
- `0x1400095e4`
- `0x140009758`

## callees

- `0x14000891c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140008951`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140008951`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000893b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000893b`

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
0x14000891c  sub     rsp, 28h
0x140008920  mov     eax, r9d
0x140008923  mov     r10, rdx
0x140008926  cmp     r9d, r8d
0x140008929  jb      short loc_14000892F
0x14000892b  lea     eax, [r8-1]
0x14000892f  lea     r9, [rcx+18h]; string
0x140008933  mov     r8, rcx; hstringHeader
0x140008936  mov     rcx, r10; sourceString
0x140008939  mov     edx, eax; length
0x14000893b  call    cs:__imp_WindowsCreateStringReference
0x140008941  test    eax, eax
0x140008943  jns     short loc_140008958
0x140008945  xor     r9d, r9d; lpArguments
0x140008948  xor     r8d, r8d; nNumberOfArguments
0x14000894b  mov     ecx, eax; dwExceptionCode
0x14000894d  lea     edx, [r9+1]; dwExceptionFlags
0x140008951  call    cs:__imp_RaiseException
0x140008957  int     3; Trap to Debugger
0x140008958  add     rsp, 28h
0x14000895c  retn
```
