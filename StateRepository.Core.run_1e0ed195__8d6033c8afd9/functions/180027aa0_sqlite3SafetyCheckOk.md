# sqlite3SafetyCheckOk

- ea: `0x180027aa0`
- end: `0x180027ae9`
- name: `sqlite3SafetyCheckOk`
- size: `73`
- prototype: ``
- caller_count: `55`
- callee_count: `3`
- tags: ``

## callers

- `0x180001010`
- `0x180028c94`
- `0x1800293e0`
- `0x1800461e0`
- `0x180046800`
- `0x180050420`
- `0x180055e50`
- `0x1800562e0`
- `0x180056370`
- `0x180056c50`
- `0x180056cd0`
- `0x180057a40`
- `0x18005bcb0`
- `0x18005c780`
- `0x1800650b0`
- `0x180065450`
- `0x180066f40`
- `0x18008611c`
- `0x18008bcc0`
- `0x18008be50`
- `0x18008c9b0`
- `0x18008d0b0`
- `0x18008d130`
- `0x18008d2e0`
- `0x18008d7a0`
- `0x18008d860`
- `0x18008dac0`
- `0x18008dbc0`
- `0x18008dcf0`
- `0x18008ddf0`
- `0x18008df10`
- `0x18008df50`
- `0x18008dfb0`
- `0x18008e280`
- `0x18008e440`
- `0x18008e510`
- `0x18008e950`
- `0x18008ecf0`
- `0x18008ed40`
- `0x18008ee30`
- `0x18008efc0`
- `0x18008f200`
- `0x18008f280`
- `0x18008f610`
- `0x18008f680`
- `0x18008f8f0`
- `0x18008fb80`
- `0x180090110`
- `0x1800908c0`
- `0x180090900`

## callees

- `0x1800275f0`
- `0x180027aa0`
- `0x18004d3f8`

## string_xrefs

- `0x180027ac2`: `unopened`

## pseudocode

```c
__int64 __fastcall sqlite3SafetyCheckOk(__int64 a1)
{
  const char *v2; // r8

  if ( !a1 )
  {
    v2 = "NULL";
LABEL_5:
    sqlite3_log(21, "API call with %s database connection pointer", v2);
    return 0;
  }
  if ( *(_BYTE *)(a1 + 113) == 118 )
    return 1;
  if ( (unsigned int)sqlite3SafetyCheckSickOrOk() )
  {
    v2 = "unopened";
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x180027aa0  sub     rsp, 28h
0x180027aa4  test    rcx, rcx
0x180027aa7  jz      short loc_180027AB9
0x180027aa9  cmp     byte ptr [rcx+71h], 76h ; 'v'
0x180027aad  jnz     short loc_180027ADE
0x180027aaf  mov     eax, 1
0x180027ab4  add     rsp, 28h
0x180027ab8  retn
0x180027ab9  lea     r8, aNull_1; "NULL"
0x180027ac0  jmp     short loc_180027AC9
0x180027ac2  lea     r8, aUnopened; "unopened"
0x180027ac9  lea     rdx, aApiCallWithSDa; "API call with %s database connection po"...
0x180027ad0  mov     ecx, 15h
0x180027ad5  call    sqlite3_log
0x180027ada  xor     eax, eax
0x180027adc  jmp     short loc_180027AB4
0x180027ade  call    sqlite3SafetyCheckSickOrOk
0x180027ae3  test    eax, eax
0x180027ae5  jz      short loc_180027ADA
0x180027ae7  jmp     short loc_180027AC2
```
