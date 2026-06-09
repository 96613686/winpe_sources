# sqlite3SafetyCheckOk

- ea: `0x18003ad5c`
- end: `0x18003ada3`
- name: `sqlite3SafetyCheckOk`
- size: `71`
- prototype: ``
- caller_count: `57`
- callee_count: `3`
- tags: ``

## callers

- `0x180016bf4`
- `0x1800334f0`
- `0x1800337f4`
- `0x18003ab40`
- `0x18003aca0`
- `0x18005b974`
- `0x180088a8c`
- `0x180092130`
- `0x1800922c0`
- `0x180092ec0`
- `0x180093500`
- `0x180093590`
- `0x1800936a0`
- `0x1800937a0`
- `0x180093820`
- `0x180093bd0`
- `0x1800944c0`
- `0x180094580`
- `0x1800947e0`
- `0x180094950`
- `0x1800949c0`
- `0x180094af0`
- `0x180094bf0`
- `0x180094d10`
- `0x180094da0`
- `0x180094de0`
- `0x180094e40`
- `0x180094ea0`
- `0x180095340`
- `0x180095610`
- `0x1800957d0`
- `0x180095b30`
- `0x180095d50`
- `0x180095e50`
- `0x1800961f0`
- `0x180096240`
- `0x180096310`
- `0x180096370`
- `0x180096630`
- `0x180096850`
- `0x180096a00`
- `0x180096a80`
- `0x1800971b0`
- `0x180097220`
- `0x180097490`
- `0x180097720`
- `0x180097f10`
- `0x1800986f0`
- `0x180098730`
- `0x1800987b0`

## callees

- `0x18003ad5c`
- `0x18003af40`
- `0x18008a884`

## string_xrefs

- `0x18003ad90`: `unopened`

## pseudocode

```c
__int64 __fastcall sqlite3SafetyCheckOk(__int64 a1)
{
  const char *v1; // r8

  if ( !a1 )
  {
    v1 = "NULL";
    goto LABEL_3;
  }
  if ( *(_BYTE *)(a1 + 113) != 118 )
  {
    if ( !(unsigned int)sqlite3SafetyCheckSickOrOk() )
      return 0;
    v1 = "unopened";
LABEL_3:
    sqlite3_log(21, "API call with %s database connection pointer", v1);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18003ad5c  sub     rsp, 28h
0x18003ad60  test    rcx, rcx
0x18003ad63  jnz     short loc_18003AD81
0x18003ad65  lea     r8, aNull_1; "NULL"
0x18003ad6c  lea     rdx, aApiCallWithSDa; "API call with %s database connection po"...
0x18003ad73  mov     ecx, 15h
0x18003ad78  call    sqlite3_log
0x18003ad7d  xor     eax, eax
0x18003ad7f  jmp     short loc_18003AD9E
0x18003ad81  cmp     byte ptr [rcx+71h], 76h ; 'v'
0x18003ad85  jz      short loc_18003AD99
0x18003ad87  call    sqlite3SafetyCheckSickOrOk
0x18003ad8c  test    eax, eax
0x18003ad8e  jz      short loc_18003AD7D
0x18003ad90  lea     r8, aUnopened; "unopened"
0x18003ad97  jmp     short loc_18003AD6C
0x18003ad99  mov     eax, 1
0x18003ad9e  add     rsp, 28h
0x18003ada2  retn
```
