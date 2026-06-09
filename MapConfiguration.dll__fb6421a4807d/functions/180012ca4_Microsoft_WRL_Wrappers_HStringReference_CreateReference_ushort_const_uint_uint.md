# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180012ca4`
- end: `0x180012ce5`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180017744`
- `0x180017ad8`
- `0x180017d98`
- `0x180019d6c`
- `0x18001a208`

## callees

- `0x180012ca4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012cc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012cc3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012cd9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012cd9`

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
0x180012ca4  sub     rsp, 28h
0x180012ca8  mov     eax, r9d
0x180012cab  mov     r10, rdx
0x180012cae  cmp     r9d, r8d
0x180012cb1  jb      short loc_180012CB7
0x180012cb3  lea     eax, [r8-1]
0x180012cb7  lea     r9, [rcx+18h]; string
0x180012cbb  mov     r8, rcx; hstringHeader
0x180012cbe  mov     rcx, r10; sourceString
0x180012cc1  mov     edx, eax; length
0x180012cc3  call    cs:__imp_WindowsCreateStringReference
0x180012cc9  test    eax, eax
0x180012ccb  jns     short loc_180012CE0
0x180012ccd  xor     r9d, r9d; lpArguments
0x180012cd0  xor     r8d, r8d; nNumberOfArguments
0x180012cd3  mov     ecx, eax; dwExceptionCode
0x180012cd5  lea     edx, [r9+1]; dwExceptionFlags
0x180012cd9  call    cs:__imp_RaiseException
0x180012cdf  int     3; Trap to Debugger
0x180012ce0  add     rsp, 28h
0x180012ce4  retn
```
