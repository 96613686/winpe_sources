# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18000f2a8`
- end: `0x18000f2e9`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `31`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000eb10`
- `0x18000ffc0`
- `0x180011d44`
- `0x180012400`
- `0x180013170`
- `0x1800142a0`
- `0x180014630`
- `0x180014c20`
- `0x180015878`
- `0x180019780`
- `0x180022a60`
- `0x18002501c`
- `0x180025bec`
- `0x180026108`
- `0x1800284c0`
- `0x180029ccc`
- `0x18002ba80`
- `0x18002da50`
- `0x18002e0d4`
- `0x18002ea20`
- `0x180030d9c`
- `0x180038640`
- `0x180038c1c`
- `0x18003c120`
- `0x18003ca00`
- `0x18003d19c`
- `0x180040758`
- `0x1800412dc`
- `0x180041720`
- `0x180042160`
- `0x180042ab0`

## callees

- `0x18000f2a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f2dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f2dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f2c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f2c7`

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
0x18000f2a8  sub     rsp, 28h
0x18000f2ac  mov     eax, r9d
0x18000f2af  mov     r10, rdx
0x18000f2b2  cmp     r9d, r8d
0x18000f2b5  jb      short loc_18000F2BB
0x18000f2b7  lea     eax, [r8-1]
0x18000f2bb  lea     r9, [rcx+18h]; string
0x18000f2bf  mov     r8, rcx; hstringHeader
0x18000f2c2  mov     rcx, r10; sourceString
0x18000f2c5  mov     edx, eax; length
0x18000f2c7  call    cs:__imp_WindowsCreateStringReference
0x18000f2cd  test    eax, eax
0x18000f2cf  jns     short loc_18000F2E4
0x18000f2d1  xor     r9d, r9d; lpArguments
0x18000f2d4  xor     r8d, r8d; nNumberOfArguments
0x18000f2d7  mov     ecx, eax; dwExceptionCode
0x18000f2d9  lea     edx, [r9+1]; dwExceptionFlags
0x18000f2dd  call    cs:__imp_RaiseException
0x18000f2e3  int     3; Trap to Debugger
0x18000f2e4  add     rsp, 28h
0x18000f2e8  retn
```
