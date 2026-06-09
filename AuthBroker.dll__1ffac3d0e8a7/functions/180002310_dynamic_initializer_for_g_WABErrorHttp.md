# _dynamic_initializer_for__g_WABErrorHttp__

- ea: `0x180002310`
- end: `0x180002352`
- name: `_dynamic_initializer_for__g_WABErrorHttp__`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002347`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002347`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000232e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000232e`

## pseudocode

```c
void dynamic_initializer_for__g_WABErrorHttp__()
{
  if ( WindowsCreateStringReference(L"ErrorHttp", 9u, &g_WABErrorHttp._header, &g_WABErrorHttp._hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
}

```

## disassembly

```asm
0x180002310  sub     rsp, 28h
0x180002314  lea     r9, g_WABErrorHttp; string
0x18000231b  mov     edx, 9; length
0x180002320  lea     r8, g_WABErrorHttp._header; hstringHeader
0x180002327  lea     rcx, aErrorhttp; "ErrorHttp"
0x18000232e  call    cs:__imp_WindowsCreateStringReference
0x180002334  test    eax, eax
0x180002336  jns     short loc_18000234D
0x180002338  xor     r9d, r9d; lpArguments
0x18000233b  xor     r8d, r8d; nNumberOfArguments
0x18000233e  mov     ecx, 0C000000Dh; dwExceptionCode
0x180002343  lea     edx, [r9+1]; dwExceptionFlags
0x180002347  call    cs:__imp_RaiseException
0x18000234d  add     rsp, 28h
0x180002351  retn
```
