# CSmsJetDB::SetCurrentIndex(char const *,char const *,ulong)

- ea: `0x1800256e4`
- end: `0x180025798`
- name: `?SetCurrentIndex@CSmsJetDB@@QEAAJPEBD0K@Z`
- size: `180`
- prototype: `int(CSmsJetDB *__hidden this, const char *, const char *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001ce14`
- `0x18001d80c`

## callees

- `0x180023f9c`
- `0x1800256e4`

## import_xrefs

- `ESENT!JetSetCurrentIndexA` at `0x180025721`
- `ESENT!JetSetCurrentIndexA` at `0x180025721`
- `ESENT!JetMove` at `0x180025751`
- `ESENT!JetMove` at `0x180025751`

## pseudocode

```c
__int64 __fastcall CSmsJetDB::SetCurrentIndex(JET_SESID *this, const char *a2, const char *a3)
{
  unsigned int TableIndex; // eax
  unsigned __int64 v7; // rdi
  JET_ERR v8; // eax
  int v9; // ecx
  JET_ERR v10; // eax
  int v11; // eax

  TableIndex = CSmsJetDB::GetTableIndex((CSmsJetDB *)this, a2);
  if ( TableIndex == this[5] )
    return 2147943568LL;
  v7 = (unsigned __int64)TableIndex << 7;
  v8 = JetSetCurrentIndexA(this[6], *(_QWORD *)(v7 + this[1] + 88), a3);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v10 = JetMove(this[6], *(_QWORD *)(v7 + this[1] + 88), 0x80000000, 0);
    v9 = 0;
    if ( v10 != -1603 )
      v9 = v10;
    if ( v9 >= 0 )
      return 0;
    if ( v9 == -1011 )
      return 2147942414LL;
    v8 = v9;
  }
  else if ( v8 == -1011 )
  {
    return 2147942414LL;
  }
  v11 = -v8;
  if ( v11 < 0 )
    LOWORD(v11) = v9;
  return v9 & 0x8E5E0000 | (unsigned __int16)v11 | 0xE5E0000;
}

```

## disassembly

```asm
0x1800256e4  mov     [rsp+arg_0], rbx
0x1800256e9  mov     [rsp+arg_8], rsi
0x1800256ee  push    rdi
0x1800256ef  sub     rsp, 20h
0x1800256f3  mov     rsi, r8
0x1800256f6  mov     rbx, rcx
0x1800256f9  call    ?GetTableIndex@CSmsJetDB@@AEAAKPEBD@Z; CSmsJetDB::GetTableIndex(char const *)
0x1800256fe  mov     edi, eax
0x180025700  cmp     rdi, [rbx+28h]
0x180025704  jnz     short loc_18002570D
0x180025706  mov     eax, 80070490h
0x18002570b  jmp     short loc_180025788
0x18002570d  mov     rdx, [rbx+8]
0x180025711  mov     r8, rsi; szIndexName
0x180025714  mov     rcx, [rbx+30h]; sesid
0x180025718  shl     rdi, 7
0x18002571c  mov     rdx, [rdi+rdx+58h]; tableid
0x180025721  call    cs:__imp_JetSetCurrentIndexA
0x180025727  mov     ecx, eax
0x180025729  test    eax, eax
0x18002572b  jns     short loc_18002573B
0x18002572d  cmp     eax, 0FFFFFC0Dh
0x180025732  jnz     short loc_18002576F
0x180025734  mov     eax, 8007000Eh
0x180025739  jmp     short loc_180025788
0x18002573b  mov     rdx, [rbx+8]
0x18002573f  xor     r9d, r9d; grbit
0x180025742  mov     rcx, [rbx+30h]; sesid
0x180025746  mov     r8d, 80000000h; cRow
0x18002574c  mov     rdx, [rdi+rdx+58h]; tableid
0x180025751  call    cs:__imp_JetMove
0x180025757  xor     ecx, ecx
0x180025759  cmp     eax, 0FFFFF9BDh
0x18002575e  cmovnz  ecx, eax
0x180025761  test    ecx, ecx
0x180025763  jns     short loc_180025786
0x180025765  cmp     ecx, 0FFFFFC0Dh
0x18002576b  jz      short loc_180025734
0x18002576d  mov     eax, ecx
0x18002576f  neg     eax
0x180025771  cmovs   eax, ecx
0x180025774  and     ecx, 8E5E0000h
0x18002577a  movzx   eax, ax
0x18002577d  or      eax, ecx
0x18002577f  or      eax, 0E5E0000h
0x180025784  jmp     short loc_180025788
0x180025786  xor     eax, eax
0x180025788  mov     rbx, [rsp+28h+arg_0]
0x18002578d  mov     rsi, [rsp+28h+arg_8]
0x180025792  add     rsp, 20h
0x180025796  pop     rdi
0x180025797  retn
```
