# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18006b108`
- end: `0x18006b149`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `66`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180084738`
- `0x180084e28`
- `0x1800852d8`
- `0x180088b64`
- `0x180089b30`
- `0x18008de94`
- `0x18008fa44`
- `0x180090670`
- `0x180090934`
- `0x180090bfc`
- `0x180090ed0`
- `0x180092a60`
- `0x180093d98`
- `0x1800948d0`
- `0x180095ab0`
- `0x180097014`
- `0x1800972d0`
- `0x180097d60`
- `0x180098f80`
- `0x180099520`
- `0x18009c524`
- `0x18009cf40`
- `0x18009d168`
- `0x18009e390`
- `0x18009ed30`
- `0x18009fb80`
- `0x1800a0500`
- `0x1800a1f78`
- `0x1800a3004`
- `0x1800a3cb0`
- `0x1800a47c0`
- `0x1800a53e0`
- `0x1800a6730`
- `0x1800a73c0`
- `0x1800a77c0`
- `0x1800a83f0`
- `0x1800a8fc0`
- `0x1800a9d90`
- `0x1800aa830`
- `0x1800ac0a0`
- `0x1800acbe0`
- `0x1800acfe0`
- `0x1800adcd0`
- `0x1800aea08`
- `0x1800aed50`
- `0x1800afb20`
- `0x1800b0830`
- `0x1800b26f8`
- `0x1800b2f8c`
- `0x1800b4c98`

## callees

- `0x18006b108`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006b13d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006b13d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006b127`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006b127`

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
0x18006b108  sub     rsp, 28h
0x18006b10c  mov     eax, r9d
0x18006b10f  mov     r10, rdx
0x18006b112  cmp     r9d, r8d
0x18006b115  jb      short loc_18006B11B
0x18006b117  lea     eax, [r8-1]
0x18006b11b  lea     r9, [rcx+18h]; string
0x18006b11f  mov     r8, rcx; hstringHeader
0x18006b122  mov     rcx, r10; sourceString
0x18006b125  mov     edx, eax; length
0x18006b127  call    cs:__imp_WindowsCreateStringReference
0x18006b12d  test    eax, eax
0x18006b12f  jns     short loc_18006B144
0x18006b131  xor     r9d, r9d; lpArguments
0x18006b134  xor     r8d, r8d; nNumberOfArguments
0x18006b137  mov     ecx, eax; dwExceptionCode
0x18006b139  lea     edx, [r9+1]; dwExceptionFlags
0x18006b13d  call    cs:__imp_RaiseException
0x18006b143  int     3; Trap to Debugger
0x18006b144  add     rsp, 28h
0x18006b148  retn
```
