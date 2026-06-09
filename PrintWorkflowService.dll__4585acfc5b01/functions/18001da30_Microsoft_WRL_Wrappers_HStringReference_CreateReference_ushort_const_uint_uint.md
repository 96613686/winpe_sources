# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18001da30`
- end: `0x18001da71`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001cce8`
- `0x18001dee4`
- `0x18001e084`
- `0x18001ecd8`
- `0x18002220c`
- `0x180023378`
- `0x18002b194`
- `0x18002b7c0`
- `0x180048064`
- `0x180055290`

## callees

- `0x18001da30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001da65`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001da65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001da4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001da4f`

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
0x18001da30  sub     rsp, 28h
0x18001da34  mov     eax, r9d
0x18001da37  mov     r10, rdx
0x18001da3a  cmp     r9d, r8d
0x18001da3d  jb      short loc_18001DA43
0x18001da3f  lea     eax, [r8-1]
0x18001da43  lea     r9, [rcx+18h]; string
0x18001da47  mov     r8, rcx; hstringHeader
0x18001da4a  mov     rcx, r10; sourceString
0x18001da4d  mov     edx, eax; length
0x18001da4f  call    cs:__imp_WindowsCreateStringReference
0x18001da55  test    eax, eax
0x18001da57  jns     short loc_18001DA6C
0x18001da59  xor     r9d, r9d; lpArguments
0x18001da5c  xor     r8d, r8d; nNumberOfArguments
0x18001da5f  mov     ecx, eax; dwExceptionCode
0x18001da61  lea     edx, [r9+1]; dwExceptionFlags
0x18001da65  call    cs:__imp_RaiseException
0x18001da6b  int     3; Trap to Debugger
0x18001da6c  add     rsp, 28h
0x18001da70  retn
```
