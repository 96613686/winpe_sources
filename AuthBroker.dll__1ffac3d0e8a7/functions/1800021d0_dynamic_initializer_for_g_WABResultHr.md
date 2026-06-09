# _dynamic_initializer_for__g_WABResultHr__

- ea: `0x1800021d0`
- end: `0x180002212`
- name: `_dynamic_initializer_for__g_WABResultHr__`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800021d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002207`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180002207`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800021ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800021ee`

## pseudocode

```c
void dynamic_initializer_for__g_WABResultHr__()
{
  if ( WindowsCreateStringReference(L"ResultHr", 8u, &g_WABResultHr._header, &g_WABResultHr._hstring) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
}

```

## disassembly

```asm
0x1800021d0  sub     rsp, 28h
0x1800021d4  lea     r9, g_WABResultHr; string
0x1800021db  mov     edx, 8; length
0x1800021e0  lea     r8, g_WABResultHr._header; hstringHeader
0x1800021e7  lea     rcx, aResulthr; "ResultHr"
0x1800021ee  call    cs:__imp_WindowsCreateStringReference
0x1800021f4  test    eax, eax
0x1800021f6  jns     short loc_18000220D
0x1800021f8  xor     r9d, r9d; lpArguments
0x1800021fb  xor     r8d, r8d; nNumberOfArguments
0x1800021fe  mov     ecx, 0C000000Dh; dwExceptionCode
0x180002203  lea     edx, [r9+1]; dwExceptionFlags
0x180002207  call    cs:__imp_RaiseException
0x18000220d  add     rsp, 28h
0x180002211  retn
```
