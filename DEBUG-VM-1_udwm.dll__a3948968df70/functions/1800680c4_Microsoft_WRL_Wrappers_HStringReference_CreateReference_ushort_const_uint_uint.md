# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800680c4`
- end: `0x180068107`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `67`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18006d678`
- `0x180094860`

## callees

- `0x1800680c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800680f5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800680f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800680df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800680df`

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
0x1800680c4  sub     rsp, 28h
0x1800680c8  mov     eax, r9d
0x1800680cb  mov     r10, rdx
0x1800680ce  cmp     r9d, r8d
0x1800680d1  jnb     short loc_180068101
0x1800680d3  lea     r9, [rcx+18h]; string
0x1800680d7  mov     r8, rcx; hstringHeader
0x1800680da  mov     rcx, r10; sourceString
0x1800680dd  mov     edx, eax; length
0x1800680df  call    cs:__imp_WindowsCreateStringReference
0x1800680e5  test    eax, eax
0x1800680e7  jns     short loc_1800680FC
0x1800680e9  xor     r9d, r9d; lpArguments
0x1800680ec  xor     r8d, r8d; nNumberOfArguments
0x1800680ef  mov     ecx, eax; dwExceptionCode
0x1800680f1  lea     edx, [r9+1]; dwExceptionFlags
0x1800680f5  call    cs:__imp_RaiseException
0x1800680fb  int     3; Trap to Debugger
0x1800680fc  add     rsp, 28h
0x180068100  retn
0x180068101  lea     eax, [r8-1]
0x180068105  jmp     short loc_1800680D3
```
