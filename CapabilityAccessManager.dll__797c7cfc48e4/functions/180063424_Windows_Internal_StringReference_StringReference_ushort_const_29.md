# Windows::Internal::StringReference::StringReference(ushort const (&)[29])

- ea: `0x180063424`
- end: `0x180063468`
- name: `??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z`
- size: `68`
- prototype: `HSTRING *__fastcall(HSTRING *string, const unsigned __int16 (*)[29])`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180063ac8`
- `0x180091680`

## callees

- `0x180063424`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180063459`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180063459`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180063440`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180063440`

## string_xrefs

- `0x180063439`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x180063424  push    rbx
0x180063426  sub     rsp, 20h
0x18006342a  mov     rbx, rcx
0x18006342d  lea     r8, [rcx+8]; hstringHeader
0x180063431  mov     r9, rcx; string
0x180063434  mov     edx, 1Ch; length
0x180063439  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180063440  call    cs:__imp_WindowsCreateStringReference
0x180063446  test    eax, eax
0x180063448  jns     short loc_18006345F
0x18006344a  xor     r9d, r9d; lpArguments
0x18006344d  xor     r8d, r8d; nNumberOfArguments
0x180063450  mov     ecx, 0C000000Dh; dwExceptionCode
0x180063455  lea     edx, [r9+1]; dwExceptionFlags
0x180063459  call    cs:__imp_RaiseException
0x18006345f  mov     rax, rbx
0x180063462  add     rsp, 20h
0x180063466  pop     rbx
0x180063467  retn
```
