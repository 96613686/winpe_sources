# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x18001ca74`
- end: `0x18001cab5`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z`
- size: `65`
- prototype: `void __fastcall(HSTRING_HEADER *hstringHeader, PCWSTR sourceString, UINT32, UINT32)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001bf70`
- `0x18001d7a0`
- `0x180024dbc`
- `0x180026330`
- `0x180028880`
- `0x180028a30`

## callees

- `0x18001ca74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001caa9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001caa9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ca93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ca93`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x18001ca74  sub     rsp, 28h
0x18001ca78  mov     eax, r9d
0x18001ca7b  mov     r10, rdx
0x18001ca7e  cmp     r9d, r8d
0x18001ca81  jb      short loc_18001CA87
0x18001ca83  lea     eax, [r8-1]
0x18001ca87  lea     r9, [rcx+18h]; string
0x18001ca8b  mov     r8, rcx; hstringHeader
0x18001ca8e  mov     rcx, r10; sourceString
0x18001ca91  mov     edx, eax; length
0x18001ca93  call    cs:__imp_WindowsCreateStringReference
0x18001ca99  test    eax, eax
0x18001ca9b  jns     short loc_18001CAB0
0x18001ca9d  xor     r9d, r9d; lpArguments
0x18001caa0  xor     r8d, r8d; nNumberOfArguments
0x18001caa3  mov     ecx, eax; dwExceptionCode
0x18001caa5  lea     edx, [r9+1]; dwExceptionFlags
0x18001caa9  call    cs:__imp_RaiseException
0x18001caaf  int     3; Trap to Debugger
0x18001cab0  add     rsp, 28h
0x18001cab4  retn
```
