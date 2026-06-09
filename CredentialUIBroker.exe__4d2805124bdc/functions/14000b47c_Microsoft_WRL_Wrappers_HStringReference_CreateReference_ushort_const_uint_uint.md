# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x14000b47c`
- end: `0x14000b4bd`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400099a8`
- `0x14000e370`
- `0x1400115c4`
- `0x1400137d4`
- `0x140016940`
- `0x140016a54`
- `0x140018498`

## callees

- `0x14000b47c`

## import_xrefs

- `KERNEL32!RaiseException` at `0x14000b4b1`
- `KERNEL32!RaiseException` at `0x14000b4b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000b49b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000b49b`

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
0x14000b47c  sub     rsp, 28h
0x14000b480  mov     eax, r9d
0x14000b483  mov     r10, rdx
0x14000b486  cmp     r9d, r8d
0x14000b489  jb      short loc_14000B48F
0x14000b48b  lea     eax, [r8-1]
0x14000b48f  lea     r9, [rcx+18h]; string
0x14000b493  mov     r8, rcx; hstringHeader
0x14000b496  mov     rcx, r10; sourceString
0x14000b499  mov     edx, eax; length
0x14000b49b  call    cs:__imp_WindowsCreateStringReference
0x14000b4a1  test    eax, eax
0x14000b4a3  jns     short loc_14000B4B8
0x14000b4a5  xor     r9d, r9d; lpArguments
0x14000b4a8  xor     r8d, r8d; nNumberOfArguments
0x14000b4ab  mov     ecx, eax; dwExceptionCode
0x14000b4ad  lea     edx, [r9+1]; dwExceptionFlags
0x14000b4b1  call    cs:__imp_RaiseException
0x14000b4b7  int     3; Trap to Debugger
0x14000b4b8  add     rsp, 28h
0x14000b4bc  retn
```
