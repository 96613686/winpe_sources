# sqlite3_get_autocommit

- ea: `0x18004b210`
- end: `0x18004b26c`
- name: `sqlite3_get_autocommit`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800275f0`
- `0x18004b210`
- `0x18004d3f8`
- `0x180060134`

## string_xrefs

- `0x18004b23a`: `unopened`

## pseudocode

```c
__int64 __fastcall sqlite3_get_autocommit(__int64 a1)
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
    return *(unsigned __int8 *)(a1 + 101);
  if ( (unsigned int)sqlite3SafetyCheckSickOrOk() )
  {
    v2 = "unopened";
    goto LABEL_7;
  }
LABEL_8:
  sqlite3ReportError(21, 184943, "misuse");
  return 0;
}

```

## disassembly

```asm
0x18004b210  sub     rsp, 28h
0x18004b214  test    rcx, rcx
0x18004b217  jz      short loc_18004B228
0x18004b219  cmp     byte ptr [rcx+71h], 76h ; 'v'
0x18004b21d  jnz     short loc_18004B231
0x18004b21f  movzx   eax, byte ptr [rcx+65h]
0x18004b223  add     rsp, 28h
0x18004b227  retn
0x18004b228  lea     r8, aNull_1; "NULL"
0x18004b22f  jmp     short loc_18004B241
0x18004b231  call    sqlite3SafetyCheckSickOrOk
0x18004b236  test    eax, eax
0x18004b238  jz      short loc_18004B252
0x18004b23a  lea     r8, aUnopened; "unopened"
0x18004b241  lea     rdx, aApiCallWithSDa; "API call with %s database connection po"...
0x18004b248  mov     ecx, 15h
0x18004b24d  call    sqlite3_log
0x18004b252  lea     r8, aMisuse; "misuse"
0x18004b259  mov     edx, 2D26Fh
0x18004b25e  mov     ecx, 15h
0x18004b263  call    sqlite3ReportError
0x18004b268  xor     eax, eax
0x18004b26a  jmp     short loc_18004B223
```
