# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180015244`
- end: `0x180015292`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `78`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180014db8`
- `0x180014e1c`
- `0x180016734`
- `0x1800169b8`

## callees

- `0x180015244`

## import_xrefs

- `KERNEL32!RaiseException` at `0x18001527f`
- `KERNEL32!RaiseException` at `0x18001527f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015263`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180015263`

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
0x180015244  sub     rsp, 28h
0x180015248  mov     eax, r9d
0x18001524b  mov     r10, rdx
0x18001524e  cmp     r9d, r8d
0x180015251  jb      short loc_180015257
0x180015253  lea     eax, [r8-1]
0x180015257  lea     r9, [rcx+18h]; string
0x18001525b  mov     r8, rcx; hstringHeader
0x18001525e  mov     rcx, r10; sourceString
0x180015261  mov     edx, eax; length
0x180015263  call    cs:__imp_WindowsCreateStringReference
0x18001526a  nop     dword ptr [rax+rax+00h]
0x18001526f  test    eax, eax
0x180015271  jns     short loc_18001528C
0x180015273  xor     r9d, r9d; lpArguments
0x180015276  xor     r8d, r8d; nNumberOfArguments
0x180015279  mov     ecx, eax; dwExceptionCode
0x18001527b  lea     edx, [r9+1]; dwExceptionFlags
0x18001527f  call    cs:__imp_RaiseException
0x180015286  nop     dword ptr [rax+rax+00h]
0x18001528b  int     3; Trap to Debugger
0x18001528c  add     rsp, 28h
0x180015290  retn
```
