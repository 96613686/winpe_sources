# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800236f0`
- end: `0x180023731`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `16`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001e03c`
- `0x18001e9e4`
- `0x18001eb88`
- `0x1800257ec`
- `0x180029de0`
- `0x180029f38`
- `0x180035afc`
- `0x180035ca0`
- `0x180035e44`
- `0x180056014`
- `0x180057ff8`
- `0x180059a6c`
- `0x180069e08`
- `0x180072e48`
- `0x1800802a8`
- `0x180086d30`

## callees

- `0x1800236f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023725`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023725`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002370f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002370f`

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
0x1800236f0  sub     rsp, 28h
0x1800236f4  mov     eax, r9d
0x1800236f7  mov     r10, rdx
0x1800236fa  cmp     r9d, r8d
0x1800236fd  jb      short loc_180023703
0x1800236ff  lea     eax, [r8-1]
0x180023703  lea     r9, [rcx+18h]; string
0x180023707  mov     r8, rcx; hstringHeader
0x18002370a  mov     rcx, r10; sourceString
0x18002370d  mov     edx, eax; length
0x18002370f  call    cs:__imp_WindowsCreateStringReference
0x180023715  test    eax, eax
0x180023717  jns     short loc_18002372C
0x180023719  xor     r9d, r9d; lpArguments
0x18002371c  xor     r8d, r8d; nNumberOfArguments
0x18002371f  mov     ecx, eax; dwExceptionCode
0x180023721  lea     edx, [r9+1]; dwExceptionFlags
0x180023725  call    cs:__imp_RaiseException
0x18002372b  int     3; Trap to Debugger
0x18002372c  add     rsp, 28h
0x180023730  retn
```
