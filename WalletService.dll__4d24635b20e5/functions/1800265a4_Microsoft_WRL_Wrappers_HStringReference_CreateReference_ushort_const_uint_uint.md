# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800265a4`
- end: `0x1800265e5`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180027bd0`
- `0x18003932c`

## callees

- `0x1800265a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800265d9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800265d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800265c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800265c3`

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
0x1800265a4  sub     rsp, 28h
0x1800265a8  mov     eax, r9d
0x1800265ab  mov     r10, rdx
0x1800265ae  cmp     r9d, r8d
0x1800265b1  jb      short loc_1800265B7
0x1800265b3  lea     eax, [r8-1]
0x1800265b7  lea     r9, [rcx+18h]; string
0x1800265bb  mov     r8, rcx; hstringHeader
0x1800265be  mov     rcx, r10; sourceString
0x1800265c1  mov     edx, eax; length
0x1800265c3  call    cs:__imp_WindowsCreateStringReference
0x1800265c9  test    eax, eax
0x1800265cb  jns     short loc_1800265E0
0x1800265cd  xor     r9d, r9d; lpArguments
0x1800265d0  xor     r8d, r8d; nNumberOfArguments
0x1800265d3  mov     ecx, eax; dwExceptionCode
0x1800265d5  lea     edx, [r9+1]; dwExceptionFlags
0x1800265d9  call    cs:__imp_RaiseException
0x1800265df  int     3; Trap to Debugger
0x1800265e0  add     rsp, 28h
0x1800265e4  retn
```
