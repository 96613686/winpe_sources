# __security_check_cookie

- ea: `0x180001740`
- end: `0x18000175e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `66`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800029a0`
- `0x180002aac`
- `0x180003e8c`
- `0x18000438c`
- `0x180004b34`
- `0x1800060c0`
- `0x180006dd8`
- `0x180008390`
- `0x180008d50`
- `0x18000a860`
- `0x18000f1f0`
- `0x180011ce0`
- `0x180011fe0`
- `0x180021750`
- `0x180021be0`
- `0x180025670`
- `0x180025ad0`
- `0x180026a00`
- `0x180026de0`
- `0x180027e00`
- `0x18002930c`
- `0x18002b040`
- `0x18002b540`
- `0x18002bbc0`
- `0x18002bf20`
- `0x18002c160`
- `0x18002c4c0`
- `0x18002c8e0`
- `0x18002ca50`
- `0x18002d3b8`
- `0x18002d490`
- `0x18002dc44`
- `0x18002ded0`
- `0x18002e568`
- `0x18002ea20`
- `0x18002ef58`
- `0x18002f360`
- `0x18002f8f0`
- `0x180030000`
- `0x180030360`
- `0x180030520`
- `0x180030720`
- `0x180030914`
- `0x180030bc0`
- `0x1800317b8`
- `0x180032690`
- `0x180032b84`
- `0x180032f44`
- `0x180033174`
- `0x180033358`

## callees

- `0x180001740`
- `0x180001d40`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    sub_180001D40(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x180001740  cmp     rcx, cs:__security_cookie
0x180001747  jnz     short ReportFailure
0x180001749  rol     rcx, 10h
0x18000174d  test    cx, 0FFFFh
0x180001752  jnz     short RestoreRcx
0x180001754  retn
0x180001755  ror     rcx, 10h
0x180001759  jmp     sub_180001D40
```
