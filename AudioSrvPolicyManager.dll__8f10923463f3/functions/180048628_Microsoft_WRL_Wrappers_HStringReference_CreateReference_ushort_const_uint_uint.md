# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180048628`
- end: `0x180048669`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180048450`

## callees

- `0x180048628`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004865d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004865d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048647`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180048647`

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
0x180048628  sub     rsp, 28h
0x18004862c  mov     eax, r9d
0x18004862f  mov     r10, rdx
0x180048632  cmp     r9d, r8d
0x180048635  jb      short loc_18004863B
0x180048637  lea     eax, [r8-1]
0x18004863b  lea     r9, [rcx+18h]; string
0x18004863f  mov     r8, rcx; hstringHeader
0x180048642  mov     rcx, r10; sourceString
0x180048645  mov     edx, eax; length
0x180048647  call    cs:__imp_WindowsCreateStringReference
0x18004864d  test    eax, eax
0x18004864f  jns     short loc_180048664
0x180048651  xor     r9d, r9d; lpArguments
0x180048654  xor     r8d, r8d; nNumberOfArguments
0x180048657  mov     ecx, eax; dwExceptionCode
0x180048659  lea     edx, [r9+1]; dwExceptionFlags
0x18004865d  call    cs:__imp_RaiseException
0x180048663  int     3; Trap to Debugger
0x180048664  add     rsp, 28h
0x180048668  retn
```
