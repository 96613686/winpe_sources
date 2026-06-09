# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180047728`
- end: `0x180047769`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180045864`
- `0x180047480`
- `0x18007257c`
- `0x180099754`

## callees

- `0x180047728`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004775d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004775d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180047747`

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
0x180047728  sub     rsp, 28h
0x18004772c  mov     eax, r9d
0x18004772f  mov     r10, rdx
0x180047732  cmp     r9d, r8d
0x180047735  jb      short loc_18004773B
0x180047737  lea     eax, [r8-1]
0x18004773b  lea     r9, [rcx+18h]; string
0x18004773f  mov     r8, rcx; hstringHeader
0x180047742  mov     rcx, r10; sourceString
0x180047745  mov     edx, eax; length
0x180047747  call    cs:__imp_WindowsCreateStringReference
0x18004774d  test    eax, eax
0x18004774f  jns     short loc_180047764
0x180047751  xor     r9d, r9d; lpArguments
0x180047754  xor     r8d, r8d; nNumberOfArguments
0x180047757  mov     ecx, eax; dwExceptionCode
0x180047759  lea     edx, [r9+1]; dwExceptionFlags
0x18004775d  call    cs:__imp_RaiseException
0x180047763  int     3; Trap to Debugger
0x180047764  add     rsp, 28h
0x180047768  retn
```
