# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18002ce2c`
- end: `0x18002ce7a`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `78`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001107c`
- `0x180025b5c`
- `0x180028604`
- `0x1800341dc`

## callees

- `0x18002ce2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ce67`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ce67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ce4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002ce4b`

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
0x18002ce2c  sub     rsp, 28h
0x18002ce30  mov     eax, r9d
0x18002ce33  mov     r10, rdx
0x18002ce36  cmp     r9d, r8d
0x18002ce39  jb      short loc_18002CE3F
0x18002ce3b  lea     eax, [r8-1]
0x18002ce3f  lea     r9, [rcx+18h]; string
0x18002ce43  mov     r8, rcx; hstringHeader
0x18002ce46  mov     rcx, r10; sourceString
0x18002ce49  mov     edx, eax; length
0x18002ce4b  call    cs:__imp_WindowsCreateStringReference
0x18002ce52  nop     dword ptr [rax+rax+00h]
0x18002ce57  test    eax, eax
0x18002ce59  jns     short loc_18002CE74
0x18002ce5b  xor     r9d, r9d; lpArguments
0x18002ce5e  xor     r8d, r8d; nNumberOfArguments
0x18002ce61  mov     ecx, eax; dwExceptionCode
0x18002ce63  lea     edx, [r9+1]; dwExceptionFlags
0x18002ce67  call    cs:__imp_RaiseException
0x18002ce6e  nop     dword ptr [rax+rax+00h]
0x18002ce73  int     3; Trap to Debugger
0x18002ce74  add     rsp, 28h
0x18002ce78  retn
```
