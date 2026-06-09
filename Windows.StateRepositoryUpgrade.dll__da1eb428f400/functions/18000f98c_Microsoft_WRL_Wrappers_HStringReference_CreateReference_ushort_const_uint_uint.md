# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18000f98c`
- end: `0x18000f9cd`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000efbc`
- `0x180011a40`

## callees

- `0x18000f98c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f9c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f9c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f9ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f9ab`

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
0x18000f98c  sub     rsp, 28h
0x18000f990  mov     eax, r9d
0x18000f993  mov     r10, rdx
0x18000f996  cmp     r9d, r8d
0x18000f999  jb      short loc_18000F99F
0x18000f99b  lea     eax, [r8-1]
0x18000f99f  lea     r9, [rcx+18h]; string
0x18000f9a3  mov     r8, rcx; hstringHeader
0x18000f9a6  mov     rcx, r10; sourceString
0x18000f9a9  mov     edx, eax; length
0x18000f9ab  call    cs:__imp_WindowsCreateStringReference
0x18000f9b1  test    eax, eax
0x18000f9b3  jns     short loc_18000F9C8
0x18000f9b5  xor     r9d, r9d; lpArguments
0x18000f9b8  xor     r8d, r8d; nNumberOfArguments
0x18000f9bb  mov     ecx, eax; dwExceptionCode
0x18000f9bd  lea     edx, [r9+1]; dwExceptionFlags
0x18000f9c1  call    cs:__imp_RaiseException
0x18000f9c7  int     3; Trap to Debugger
0x18000f9c8  add     rsp, 28h
0x18000f9cc  retn
```
