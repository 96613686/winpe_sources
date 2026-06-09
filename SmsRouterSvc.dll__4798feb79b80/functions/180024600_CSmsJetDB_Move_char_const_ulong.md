# CSmsJetDB::Move(char const *,ulong)

- ea: `0x180024600`
- end: `0x18002466e`
- name: `?Move@CSmsJetDB@@QEAAJPEBDK@Z`
- size: `110`
- prototype: `__int64 __fastcall(CSmsJetDB *__hidden this, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001d80c`

## callees

- `0x180023f9c`
- `0x180024600`

## import_xrefs

- `ESENT!JetMove` at `0x180024635`
- `ESENT!JetMove` at `0x180024635`

## pseudocode

```c
__int64 __fastcall CSmsJetDB::Move(JET_SESID *this, const char *a2)
{
  unsigned int TableIndex; // eax
  JET_ERR v5; // eax
  JET_ERR v6; // ecx
  int v7; // eax

  TableIndex = CSmsJetDB::GetTableIndex((CSmsJetDB *)this, a2);
  if ( TableIndex == this[5] )
    return 2147943568LL;
  v5 = JetMove(this[6], *(_QWORD *)(((unsigned __int64)TableIndex << 7) + this[1] + 88), 1, 0);
  v6 = v5;
  if ( v5 >= 0 )
    return 0;
  if ( v5 == -1011 )
    return 2147942414LL;
  v7 = -v5;
  if ( v7 < 0 )
    LOWORD(v7) = v6;
  return v6 & 0x8E5E0000 | (unsigned __int16)v7 | 0xE5E0000;
}

```

## disassembly

```asm
0x180024600  push    rbx
0x180024602  sub     rsp, 20h
0x180024606  mov     rbx, rcx
0x180024609  call    ?GetTableIndex@CSmsJetDB@@AEAAKPEBD@Z; CSmsJetDB::GetTableIndex(char const *)
0x18002460e  mov     eax, eax
0x180024610  cmp     rax, [rbx+28h]
0x180024614  jnz     short loc_18002461D
0x180024616  mov     eax, 80070490h
0x18002461b  jmp     short loc_180024668
0x18002461d  mov     rdx, [rbx+8]
0x180024621  xor     r9d, r9d; grbit
0x180024624  mov     rcx, [rbx+30h]; sesid
0x180024628  shl     rax, 7
0x18002462c  lea     r8d, [r9+1]; cRow
0x180024630  mov     rdx, [rax+rdx+58h]; tableid
0x180024635  call    cs:__imp_JetMove
0x18002463b  mov     ecx, eax
0x18002463d  test    eax, eax
0x18002463f  jns     short loc_180024666
0x180024641  cmp     eax, 0FFFFFC0Dh
0x180024646  jnz     short loc_18002464F
0x180024648  mov     eax, 8007000Eh
0x18002464d  jmp     short loc_180024668
0x18002464f  neg     eax
0x180024651  cmovs   eax, ecx
0x180024654  and     ecx, 8E5E0000h
0x18002465a  movzx   eax, ax
0x18002465d  or      eax, ecx
0x18002465f  or      eax, 0E5E0000h
0x180024664  jmp     short loc_180024668
0x180024666  xor     eax, eax
0x180024668  add     rsp, 20h
0x18002466c  pop     rbx
0x18002466d  retn
```
