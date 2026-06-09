# __security_check_cookie

- ea: `0x180026e30`
- end: `0x180026e4f`
- name: `__security_check_cookie`
- size: `31`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `68`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001a10`
- `0x180003024`
- `0x1800046b0`
- `0x1800062a4`
- `0x180006810`
- `0x1800083a0`
- `0x1800093c0`
- `0x180009704`
- `0x1800098d0`
- `0x18000a30c`
- `0x18000b468`
- `0x18000b680`
- `0x18000bc98`
- `0x18000d360`
- `0x18000dd64`
- `0x18000ebf4`
- `0x18000f0c0`
- `0x180011364`
- `0x180011ab8`
- `0x180011e8c`
- `0x180012264`
- `0x1800126bc`
- `0x18001285c`
- `0x180013b7c`
- `0x180013cac`
- `0x180013d24`
- `0x180013d94`
- `0x180013e4c`
- `0x180013eb8`
- `0x1800140dc`
- `0x1800160b8`
- `0x1800166a0`
- `0x180016ad0`
- `0x180017b30`
- `0x18001818c`
- `0x18001866c`
- `0x1800193a0`
- `0x180019b9c`
- `0x18001a970`
- `0x18001b0cc`
- `0x18001bc08`
- `0x18001c3dc`
- `0x18001c780`
- `0x18001cd84`
- `0x18001cf98`
- `0x18001d268`
- `0x18001d4e0`
- `0x18001d7c0`
- `0x18001defc`
- `0x18001e0e4`

## callees

- `0x180026e30`
- `0x1800271c0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x180026e30  cmp     rcx, cs:__security_cookie
0x180026e37  jnz     short loc_180026E4A
0x180026e39  rol     rcx, 10h
0x180026e3d  test    cx, 0FFFFh
0x180026e42  jnz     short loc_180026E46
0x180026e44  nop
0x180026e45  retn
0x180026e46  ror     rcx, 10h
0x180026e4a  jmp     __report_gsfailure
```
