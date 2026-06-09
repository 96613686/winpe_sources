# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x140007eac`
- end: `0x140007eed`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007cb0`
- `0x140007ef4`
- `0x1400081bc`

## callees

- `0x140007eac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140007ee1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140007ee1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140007ecb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140007ecb`

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
0x140007eac  sub     rsp, 28h
0x140007eb0  mov     eax, r9d
0x140007eb3  mov     r10, rdx
0x140007eb6  cmp     r9d, r8d
0x140007eb9  jb      short loc_140007EBF
0x140007ebb  lea     eax, [r8-1]
0x140007ebf  lea     r9, [rcx+18h]; string
0x140007ec3  mov     r8, rcx; hstringHeader
0x140007ec6  mov     rcx, r10; sourceString
0x140007ec9  mov     edx, eax; length
0x140007ecb  call    cs:__imp_WindowsCreateStringReference
0x140007ed1  test    eax, eax
0x140007ed3  jns     short loc_140007EE8
0x140007ed5  xor     r9d, r9d; lpArguments
0x140007ed8  xor     r8d, r8d; nNumberOfArguments
0x140007edb  mov     ecx, eax; dwExceptionCode
0x140007edd  lea     edx, [r9+1]; dwExceptionFlags
0x140007ee1  call    cs:__imp_RaiseException
0x140007ee7  int     3; Trap to Debugger
0x140007ee8  add     rsp, 28h
0x140007eec  retn
```
