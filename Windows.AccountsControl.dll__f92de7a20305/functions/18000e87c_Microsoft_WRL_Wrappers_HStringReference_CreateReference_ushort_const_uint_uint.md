# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18000e87c`
- end: `0x18000e8bd`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `95`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007f68`
- `0x180008778`
- `0x18000891c`
- `0x180008ac0`
- `0x18000cc30`
- `0x18000cdc0`
- `0x18000cf4c`
- `0x18000db14`
- `0x18000f5b0`
- `0x18000fc40`
- `0x180010594`
- `0x180010d7c`
- `0x18001113c`
- `0x180011448`
- `0x180011c24`
- `0x180011ed0`
- `0x180013210`
- `0x1800137b0`
- `0x180016198`
- `0x18001667c`
- `0x18001a4d4`
- `0x18001a678`
- `0x18001d868`
- `0x18001ea78`
- `0x180021e18`
- `0x180021fbc`
- `0x180022160`
- `0x180022304`
- `0x180022520`
- `0x180022744`
- `0x180022968`
- `0x180022b8c`
- `0x18002694c`
- `0x180027010`
- `0x1800276dc`
- `0x180029308`
- `0x180029954`
- `0x180029ef8`
- `0x18002f654`
- `0x18002fab4`
- `0x18002fc8c`
- `0x180033270`
- `0x180039178`
- `0x18003987c`
- `0x1800411d0`
- `0x180042770`
- `0x180043cb0`
- `0x180043ee4`
- `0x180047b8c`
- `0x180048a58`

## callees

- `0x18000e87c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e8b1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000e8b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e89b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000e89b`

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
0x18000e87c  sub     rsp, 28h
0x18000e880  mov     eax, r9d
0x18000e883  mov     r10, rdx
0x18000e886  cmp     r9d, r8d
0x18000e889  jb      short loc_18000E88F
0x18000e88b  lea     eax, [r8-1]
0x18000e88f  lea     r9, [rcx+18h]; string
0x18000e893  mov     r8, rcx; hstringHeader
0x18000e896  mov     rcx, r10; sourceString
0x18000e899  mov     edx, eax; length
0x18000e89b  call    cs:__imp_WindowsCreateStringReference
0x18000e8a1  test    eax, eax
0x18000e8a3  jns     short loc_18000E8B8
0x18000e8a5  xor     r9d, r9d; lpArguments
0x18000e8a8  xor     r8d, r8d; nNumberOfArguments
0x18000e8ab  mov     ecx, eax; dwExceptionCode
0x18000e8ad  lea     edx, [r9+1]; dwExceptionFlags
0x18000e8b1  call    cs:__imp_RaiseException
0x18000e8b7  int     3; Trap to Debugger
0x18000e8b8  add     rsp, 28h
0x18000e8bc  retn
```
