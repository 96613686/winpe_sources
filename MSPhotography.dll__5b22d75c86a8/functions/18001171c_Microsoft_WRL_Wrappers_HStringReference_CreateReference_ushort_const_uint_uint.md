# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18001171c`
- end: `0x18001175d`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c224`
- `0x18000c4fc`
- `0x18002e1d0`
- `0x18002f56c`
- `0x1800a3704`
- `0x1800a5ac0`
- `0x1800aaf5c`
- `0x1800b32fc`

## callees

- `0x18001171c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011751`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011751`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001173b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001173b`

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
0x18001171c  sub     rsp, 28h
0x180011720  mov     eax, r9d
0x180011723  mov     r10, rdx
0x180011726  cmp     r9d, r8d
0x180011729  jb      short loc_18001172F
0x18001172b  lea     eax, [r8-1]
0x18001172f  lea     r9, [rcx+18h]; string
0x180011733  mov     r8, rcx; hstringHeader
0x180011736  mov     rcx, r10; sourceString
0x180011739  mov     edx, eax; length
0x18001173b  call    cs:__imp_WindowsCreateStringReference
0x180011741  test    eax, eax
0x180011743  jns     short loc_180011758
0x180011745  xor     r9d, r9d; lpArguments
0x180011748  xor     r8d, r8d; nNumberOfArguments
0x18001174b  mov     ecx, eax; dwExceptionCode
0x18001174d  lea     edx, [r9+1]; dwExceptionFlags
0x180011751  call    cs:__imp_RaiseException
0x180011757  int     3; Trap to Debugger
0x180011758  add     rsp, 28h
0x18001175c  retn
```
