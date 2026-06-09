# sqlite3_changes64

- ea: `0x180059310`
- end: `0x18005936c`
- name: `sqlite3_changes64`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180059300`
- `0x18007afb0`

## callees

- `0x1800257e0`
- `0x18002619c`
- `0x180031ee4`
- `0x180059310`

## string_xrefs

- `0x18005933a`: `unopened`

## pseudocode

```c
__int64 __fastcall sqlite3_changes64(__int64 a1)
{
  const char *v2; // r8

  if ( !a1 )
  {
    v2 = "NULL";
LABEL_7:
    sqlite3_log(21, "API call with %s database connection pointer", v2);
    goto LABEL_8;
  }
  if ( *(_BYTE *)(a1 + 113) == 118 )
    return *(_QWORD *)(a1 + 120);
  if ( (unsigned int)sqlite3SafetyCheckSickOrOk() )
  {
    v2 = "unopened";
    goto LABEL_7;
  }
LABEL_8:
  sqlite3ReportError(21, 181347, "misuse");
  return 0;
}

```

## disassembly

```asm
0x180059310  sub     rsp, 28h
0x180059314  test    rcx, rcx
0x180059317  jz      short loc_180059328
0x180059319  cmp     byte ptr [rcx+71h], 76h ; 'v'
0x18005931d  jnz     short loc_180059331
0x18005931f  mov     rax, [rcx+78h]
0x180059323  add     rsp, 28h
0x180059327  retn
0x180059328  lea     r8, aNull_1; "NULL"
0x18005932f  jmp     short loc_180059341
0x180059331  call    sqlite3SafetyCheckSickOrOk
0x180059336  test    eax, eax
0x180059338  jz      short loc_180059352
0x18005933a  lea     r8, aUnopened; "unopened"
0x180059341  lea     rdx, aApiCallWithSDa; "API call with %s database connection po"...
0x180059348  mov     ecx, 15h
0x18005934d  call    sqlite3_log
0x180059352  lea     r8, aMisuse; "misuse"
0x180059359  mov     edx, 2C463h
0x18005935e  mov     ecx, 15h
0x180059363  call    sqlite3ReportError
0x180059368  xor     eax, eax
0x18005936a  jmp     short loc_180059323
```
