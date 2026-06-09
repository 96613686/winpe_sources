# sqlite3SafetyCheckOk

- ea: `0x18003f840`
- end: `0x18003f889`
- name: `sqlite3SafetyCheckOk`
- size: `73`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `57`
- callee_count: `3`
- tags: ``

## callers

- `0x180030390`
- `0x180030410`
- `0x180030570`
- `0x1800306e0`
- `0x180030858`
- `0x1800325b0`
- `0x1800379d0`
- `0x18003f440`
- `0x18003f730`
- `0x180043a80`
- `0x180053c60`
- `0x18005ee40`
- `0x18005f0c0`
- `0x18005f150`
- `0x18005fde0`
- `0x18005fe60`
- `0x180062ea0`
- `0x18006b7a0`
- `0x180072ad0`
- `0x1800976d8`
- `0x180099fe0`
- `0x18009a080`
- `0x18009a580`
- `0x18009ac50`
- `0x18009acd0`
- `0x18009ae80`
- `0x18009b340`
- `0x18009b560`
- `0x18009b720`
- `0x18009b820`
- `0x18009b940`
- `0x18009b9b0`
- `0x18009b9f0`
- `0x18009ba50`
- `0x18009bab0`
- `0x18009bf50`
- `0x18009c220`
- `0x18009c3e0`
- `0x18009c650`
- `0x18009c890`
- `0x18009cc30`
- `0x18009cc80`
- `0x18009cdf0`
- `0x18009cf10`
- `0x18009d180`
- `0x18009d200`
- `0x18009d990`
- `0x18009da00`
- `0x18009dc70`
- `0x18009df00`

## callees

- `0x1800257e0`
- `0x180031ee4`
- `0x18003f840`

## string_xrefs

- `0x18003f862`: `unopened`

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
0x18003f840  sub     rsp, 28h
0x18003f844  test    rcx, rcx
0x18003f847  jz      short loc_18003F859
0x18003f849  cmp     byte ptr [rcx+71h], 76h ; 'v'
0x18003f84d  jnz     short loc_18003F87E
0x18003f84f  mov     eax, 1
0x18003f854  add     rsp, 28h
0x18003f858  retn
0x18003f859  lea     r8, aNull_1; "NULL"
0x18003f860  jmp     short loc_18003F869
0x18003f862  lea     r8, aUnopened; "unopened"
0x18003f869  lea     rdx, aApiCallWithSDa; "API call with %s database connection po"...
0x18003f870  mov     ecx, 15h
0x18003f875  call    sqlite3_log
0x18003f87a  xor     eax, eax
0x18003f87c  jmp     short loc_18003F854
0x18003f87e  call    sqlite3SafetyCheckSickOrOk
0x18003f883  test    eax, eax
0x18003f885  jz      short loc_18003F87A
0x18003f887  jmp     short loc_18003F862
```
