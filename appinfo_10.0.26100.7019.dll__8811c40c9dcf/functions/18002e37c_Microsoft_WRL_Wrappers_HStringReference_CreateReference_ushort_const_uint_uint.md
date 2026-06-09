# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18002e37c`
- end: `0x18002e3ca`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `78`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180010f3c`
- `0x18002719c`
- `0x180029474`
- `0x180033e6c`

## callees

- `0x18002e37c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002e3b7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002e3b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002e39b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002e39b`

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
0x18002e37c  sub     rsp, 28h
0x18002e380  mov     eax, r9d
0x18002e383  mov     r10, rdx
0x18002e386  cmp     r9d, r8d
0x18002e389  jb      short loc_18002E38F
0x18002e38b  lea     eax, [r8-1]
0x18002e38f  lea     r9, [rcx+18h]; string
0x18002e393  mov     r8, rcx; hstringHeader
0x18002e396  mov     rcx, r10; sourceString
0x18002e399  mov     edx, eax; length
0x18002e39b  call    cs:__imp_WindowsCreateStringReference
0x18002e3a2  nop     dword ptr [rax+rax+00h]
0x18002e3a7  test    eax, eax
0x18002e3a9  jns     short loc_18002E3C4
0x18002e3ab  xor     r9d, r9d; lpArguments
0x18002e3ae  xor     r8d, r8d; nNumberOfArguments
0x18002e3b1  mov     ecx, eax; dwExceptionCode
0x18002e3b3  lea     edx, [r9+1]; dwExceptionFlags
0x18002e3b7  call    cs:__imp_RaiseException
0x18002e3be  nop     dword ptr [rax+rax+00h]
0x18002e3c3  int     3; Trap to Debugger
0x18002e3c4  add     rsp, 28h
0x18002e3c8  retn
```
