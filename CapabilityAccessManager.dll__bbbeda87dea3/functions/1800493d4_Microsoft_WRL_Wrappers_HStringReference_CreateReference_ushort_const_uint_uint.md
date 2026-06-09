# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800493d4`
- end: `0x180049415`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800467c8`
- `0x180048784`
- `0x180063238`
- `0x180063ac8`
- `0x180087400`
- `0x18008bb6c`
- `0x18008e090`
- `0x180090bf4`
- `0x180092968`
- `0x18009ca80`
- `0x1800b2694`
- `0x1800b2ddc`

## callees

- `0x1800493d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180049409`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180049409`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800493f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800493f3`

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
0x1800493d4  sub     rsp, 28h
0x1800493d8  mov     eax, r9d
0x1800493db  mov     r10, rdx
0x1800493de  cmp     r9d, r8d
0x1800493e1  jb      short loc_1800493E7
0x1800493e3  lea     eax, [r8-1]
0x1800493e7  lea     r9, [rcx+18h]; string
0x1800493eb  mov     r8, rcx; hstringHeader
0x1800493ee  mov     rcx, r10; sourceString
0x1800493f1  mov     edx, eax; length
0x1800493f3  call    cs:__imp_WindowsCreateStringReference
0x1800493f9  test    eax, eax
0x1800493fb  jns     short loc_180049410
0x1800493fd  xor     r9d, r9d; lpArguments
0x180049400  xor     r8d, r8d; nNumberOfArguments
0x180049403  mov     ecx, eax; dwExceptionCode
0x180049405  lea     edx, [r9+1]; dwExceptionFlags
0x180049409  call    cs:__imp_RaiseException
0x18004940f  int     3; Trap to Debugger
0x180049410  add     rsp, 28h
0x180049414  retn
```
