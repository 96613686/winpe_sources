# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18002cd5c`
- end: `0x18002cdaa`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `78`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001107c`
- `0x180025b5c`
- `0x180027d78`
- `0x180033f1c`

## callees

- `0x18002cd5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002cd97`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002cd97`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002cd7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002cd7b`

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
0x18002cd5c  sub     rsp, 28h
0x18002cd60  mov     eax, r9d
0x18002cd63  mov     r10, rdx
0x18002cd66  cmp     r9d, r8d
0x18002cd69  jb      short loc_18002CD6F
0x18002cd6b  lea     eax, [r8-1]
0x18002cd6f  lea     r9, [rcx+18h]; string
0x18002cd73  mov     r8, rcx; hstringHeader
0x18002cd76  mov     rcx, r10; sourceString
0x18002cd79  mov     edx, eax; length
0x18002cd7b  call    cs:__imp_WindowsCreateStringReference
0x18002cd82  nop     dword ptr [rax+rax+00h]
0x18002cd87  test    eax, eax
0x18002cd89  jns     short loc_18002CDA4
0x18002cd8b  xor     r9d, r9d; lpArguments
0x18002cd8e  xor     r8d, r8d; nNumberOfArguments
0x18002cd91  mov     ecx, eax; dwExceptionCode
0x18002cd93  lea     edx, [r9+1]; dwExceptionFlags
0x18002cd97  call    cs:__imp_RaiseException
0x18002cd9e  nop     dword ptr [rax+rax+00h]
0x18002cda3  int     3; Trap to Debugger
0x18002cda4  add     rsp, 28h
0x18002cda8  retn
```
