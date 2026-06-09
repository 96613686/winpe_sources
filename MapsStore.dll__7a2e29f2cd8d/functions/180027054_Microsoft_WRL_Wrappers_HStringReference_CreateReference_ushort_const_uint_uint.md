# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x180027054`
- end: `0x180027095`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002afa4`
- `0x18002b428`
- `0x18002cf9c`
- `0x18002d438`

## callees

- `0x180027054`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180027089`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180027089`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027073`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027073`

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
0x180027054  sub     rsp, 28h
0x180027058  mov     eax, r9d
0x18002705b  mov     r10, rdx
0x18002705e  cmp     r9d, r8d
0x180027061  jb      short loc_180027067
0x180027063  lea     eax, [r8-1]
0x180027067  lea     r9, [rcx+18h]; string
0x18002706b  mov     r8, rcx; hstringHeader
0x18002706e  mov     rcx, r10; sourceString
0x180027071  mov     edx, eax; length
0x180027073  call    cs:__imp_WindowsCreateStringReference
0x180027079  test    eax, eax
0x18002707b  jns     short loc_180027090
0x18002707d  xor     r9d, r9d; lpArguments
0x180027080  xor     r8d, r8d; nNumberOfArguments
0x180027083  mov     ecx, eax; dwExceptionCode
0x180027085  lea     edx, [r9+1]; dwExceptionFlags
0x180027089  call    cs:__imp_RaiseException
0x18002708f  int     3; Trap to Debugger
0x180027090  add     rsp, 28h
0x180027094  retn
```
