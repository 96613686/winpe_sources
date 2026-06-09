# Windows::Internal::StringReference::StringReference(ushort const (&)[29])

- ea: `0x180024d34`
- end: `0x180024d78`
- name: `??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[29])`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180025a08`
- `0x1800262dc`
- `0x180039d10`

## callees

- `0x180024d34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024d69`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024d69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024d50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024d50`

## string_xrefs

- `0x180024d49`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[29])
{
  if ( WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, (HSTRING_HEADER *)(string + 1), string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x180024d34  push    rbx
0x180024d36  sub     rsp, 20h
0x180024d3a  mov     rbx, rcx
0x180024d3d  lea     r8, [rcx+8]; hstringHeader
0x180024d41  mov     r9, rcx; string
0x180024d44  mov     edx, 1Ch; length
0x180024d49  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180024d50  call    cs:__imp_WindowsCreateStringReference
0x180024d56  test    eax, eax
0x180024d58  jns     short loc_180024D6F
0x180024d5a  xor     r9d, r9d; lpArguments
0x180024d5d  xor     r8d, r8d; nNumberOfArguments
0x180024d60  mov     ecx, 0C000000Dh; dwExceptionCode
0x180024d65  lea     edx, [r9+1]; dwExceptionFlags
0x180024d69  call    cs:__imp_RaiseException
0x180024d6f  mov     rax, rbx
0x180024d72  add     rsp, 20h
0x180024d76  pop     rbx
0x180024d77  retn
```
