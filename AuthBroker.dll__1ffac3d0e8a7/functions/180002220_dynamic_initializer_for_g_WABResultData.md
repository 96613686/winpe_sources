# _dynamic_initializer_for__g_WABResultData__

- ea: `0x180002220`
- end: `0x180002262`
- name: `_dynamic_initializer_for__g_WABResultData__`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002220`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002257`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002257`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000223e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000223e`

## pseudocode

```c
void dynamic_initializer_for__g_WABResultData__()
{
  if ( WindowsCreateStringReference(L"ResultData", 0xAu, &g_WABResultData._header, &g_WABResultData._hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
}

```

## disassembly

```asm
0x180002220  sub     rsp, 28h
0x180002224  lea     r9, g_WABResultData; string
0x18000222b  mov     edx, 0Ah; length
0x180002230  lea     r8, g_WABResultData._header; hstringHeader
0x180002237  lea     rcx, aResultdata; "ResultData"
0x18000223e  call    cs:__imp_WindowsCreateStringReference
0x180002244  test    eax, eax
0x180002246  jns     short loc_18000225D
0x180002248  xor     r9d, r9d; lpArguments
0x18000224b  xor     r8d, r8d; nNumberOfArguments
0x18000224e  mov     ecx, 0C000000Dh; dwExceptionCode
0x180002253  lea     edx, [r9+1]; dwExceptionFlags
0x180002257  call    cs:__imp_RaiseException
0x18000225d  add     rsp, 28h
0x180002261  retn
```
