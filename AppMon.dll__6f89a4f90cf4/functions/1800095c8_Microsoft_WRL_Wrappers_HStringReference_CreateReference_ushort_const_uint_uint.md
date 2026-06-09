# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800095c8`
- end: `0x180009609`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008d9c`
- `0x18000e84c`

## callees

- `0x1800095c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800095fd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800095fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800095e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800095e7`

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
0x1800095c8  sub     rsp, 28h
0x1800095cc  mov     eax, r9d
0x1800095cf  mov     r10, rdx
0x1800095d2  cmp     r9d, r8d
0x1800095d5  jb      short loc_1800095DB
0x1800095d7  lea     eax, [r8-1]
0x1800095db  lea     r9, [rcx+18h]; string
0x1800095df  mov     r8, rcx; hstringHeader
0x1800095e2  mov     rcx, r10; sourceString
0x1800095e5  mov     edx, eax; length
0x1800095e7  call    cs:__imp_WindowsCreateStringReference
0x1800095ed  test    eax, eax
0x1800095ef  jns     short loc_180009604
0x1800095f1  xor     r9d, r9d; lpArguments
0x1800095f4  xor     r8d, r8d; nNumberOfArguments
0x1800095f7  mov     ecx, eax; dwExceptionCode
0x1800095f9  lea     edx, [r9+1]; dwExceptionFlags
0x1800095fd  call    cs:__imp_RaiseException
0x180009603  int     3; Trap to Debugger
0x180009604  add     rsp, 28h
0x180009608  retn
```
