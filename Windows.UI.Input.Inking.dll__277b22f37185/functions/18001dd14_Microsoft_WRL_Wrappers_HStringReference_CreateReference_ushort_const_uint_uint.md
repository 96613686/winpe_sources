# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18001dd14`
- end: `0x18001dd55`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `29`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001bb64`
- `0x18001bf00`
- `0x1800203fc`
- `0x1800205a0`
- `0x18002d160`
- `0x180038154`
- `0x1800382f8`
- `0x18003849c`
- `0x180047874`
- `0x18004a28c`
- `0x180060658`
- `0x180061814`
- `0x180075658`
- `0x180075850`
- `0x180078820`
- `0x180086f20`
- `0x1800882b4`
- `0x180088914`
- `0x18008d030`
- `0x18009ecb8`
- `0x1800aa164`
- `0x1800ac9c0`
- `0x1800b5190`
- `0x1800bb4d0`
- `0x1800c8b2c`
- `0x1800d28d0`
- `0x1800d3fa4`
- `0x1800e363c`
- `0x1800e51e0`

## callees

- `0x18001dd14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001dd49`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001dd49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001dd33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001dd33`

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
0x18001dd14  sub     rsp, 28h
0x18001dd18  mov     eax, r9d
0x18001dd1b  mov     r10, rdx
0x18001dd1e  cmp     r9d, r8d
0x18001dd21  jb      short loc_18001DD27
0x18001dd23  lea     eax, [r8-1]
0x18001dd27  lea     r9, [rcx+18h]; string
0x18001dd2b  mov     r8, rcx; hstringHeader
0x18001dd2e  mov     rcx, r10; sourceString
0x18001dd31  mov     edx, eax; length
0x18001dd33  call    cs:__imp_WindowsCreateStringReference
0x18001dd39  test    eax, eax
0x18001dd3b  jns     short loc_18001DD50
0x18001dd3d  xor     r9d, r9d; lpArguments
0x18001dd40  xor     r8d, r8d; nNumberOfArguments
0x18001dd43  mov     ecx, eax; dwExceptionCode
0x18001dd45  lea     edx, [r9+1]; dwExceptionFlags
0x18001dd49  call    cs:__imp_RaiseException
0x18001dd4f  int     3; Trap to Debugger
0x18001dd50  add     rsp, 28h
0x18001dd54  retn
```
