# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x1800252b0`
- end: `0x1800252f1`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, unsigned int, unsigned int)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800231f0`
- `0x180023464`
- `0x180026a90`
- `0x180039620`
- `0x1800d5ab4`
- `0x1800d768c`
- `0x1800da084`
- `0x1800da724`
- `0x1800dae40`
- `0x1800db168`
- `0x1800dbff4`

## callees

- `0x1800252b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800252e5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800252e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800252cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800252cf`

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
0x1800252b0  sub     rsp, 28h
0x1800252b4  mov     eax, r9d
0x1800252b7  mov     r10, rdx
0x1800252ba  cmp     r9d, r8d
0x1800252bd  jb      short loc_1800252C3
0x1800252bf  lea     eax, [r8-1]
0x1800252c3  lea     r9, [rcx+18h]; string
0x1800252c7  mov     r8, rcx; hstringHeader
0x1800252ca  mov     rcx, r10; sourceString
0x1800252cd  mov     edx, eax; length
0x1800252cf  call    cs:__imp_WindowsCreateStringReference
0x1800252d5  test    eax, eax
0x1800252d7  jns     short loc_1800252EC
0x1800252d9  xor     r9d, r9d; lpArguments
0x1800252dc  xor     r8d, r8d; nNumberOfArguments
0x1800252df  mov     ecx, eax; dwExceptionCode
0x1800252e1  lea     edx, [r9+1]; dwExceptionFlags
0x1800252e5  call    cs:__imp_RaiseException
0x1800252eb  int     3; Trap to Debugger
0x1800252ec  add     rsp, 28h
0x1800252f0  retn
```
