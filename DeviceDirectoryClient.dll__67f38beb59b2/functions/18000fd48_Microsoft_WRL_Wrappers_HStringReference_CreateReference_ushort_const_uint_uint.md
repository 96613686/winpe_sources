# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18000fd48`
- end: `0x18000fd89`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `30`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fc64`
- `0x1800115e0`
- `0x18001386c`
- `0x180015120`
- `0x180015504`
- `0x180015d80`
- `0x180015fbc`
- `0x18001691c`
- `0x180016aa4`
- `0x1800183c4`
- `0x18001bf54`
- `0x18001c978`
- `0x18001d588`
- `0x18001dcfc`
- `0x18001e164`
- `0x18001e8a0`
- `0x18001f2e0`
- `0x18001fd74`
- `0x180020068`
- `0x1800204a4`
- `0x18002099c`
- `0x180020d2c`
- `0x18002166c`
- `0x180022240`
- `0x180023180`
- `0x180023f8c`
- `0x180024fb8`
- `0x180026474`
- `0x180026a08`
- `0x180027dc8`

## callees

- `0x18000fd48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000fd7d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000fd7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fd67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000fd67`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18000fd48  sub     rsp, 28h
0x18000fd4c  mov     eax, r9d
0x18000fd4f  mov     r10, rdx
0x18000fd52  cmp     r9d, r8d
0x18000fd55  jb      short loc_18000FD5B
0x18000fd57  lea     eax, [r8-1]
0x18000fd5b  lea     r9, [rcx+18h]; string
0x18000fd5f  mov     r8, rcx; hstringHeader
0x18000fd62  mov     rcx, r10; sourceString
0x18000fd65  mov     edx, eax; length
0x18000fd67  call    cs:__imp_WindowsCreateStringReference
0x18000fd6d  test    eax, eax
0x18000fd6f  jns     short loc_18000FD84
0x18000fd71  xor     r9d, r9d; lpArguments
0x18000fd74  xor     r8d, r8d; nNumberOfArguments
0x18000fd77  mov     ecx, eax; dwExceptionCode
0x18000fd79  lea     edx, [r9+1]; dwExceptionFlags
0x18000fd7d  call    cs:__imp_RaiseException
0x18000fd83  int     3; Trap to Debugger
0x18000fd84  add     rsp, 28h
0x18000fd88  retn
```
