# STRU::Copy(ushort const *)

- ea: `0x180002e90`
- end: `0x180002ec5`
- name: `?Copy@STRU@@QEAAJPEBG@Z`
- size: `53`
- prototype: `__int64 __fastcall(STRU *__hidden this, const unsigned __int16 *)`
- caller_count: `77`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180006784`
- `0x1800067c8`
- `0x180006960`
- `0x180006a08`
- `0x180006b6c`
- `0x180006be0`
- `0x1800082d0`
- `0x180008f00`
- `0x180009890`
- `0x180009aac`
- `0x18000a91c`
- `0x18000ad70`
- `0x18000b0c0`
- `0x18000b400`
- `0x18000bff0`
- `0x18000c5e0`
- `0x18000c800`
- `0x18000ca90`
- `0x18000cd60`
- `0x18000d360`
- `0x18000dce8`
- `0x18000e27c`
- `0x18000eb40`
- `0x18000f234`
- `0x18000fc84`
- `0x180010200`
- `0x18001042c`
- `0x180010850`
- `0x180011fe0`
- `0x1800122a8`
- `0x180012450`
- `0x180012b28`
- `0x180013030`
- `0x1800131d8`
- `0x180013288`
- `0x180013504`
- `0x180013d88`
- `0x180014a40`
- `0x180014ff0`
- `0x180015844`
- `0x1800165d8`
- `0x180016cd0`
- `0x1800172ec`
- `0x180018540`
- `0x180018b78`
- `0x180018d80`
- `0x180019f48`
- `0x18001aff4`
- `0x18001b350`
- `0x18001b7e4`

## callees

- `0x180002e90`
- `0x1800339a4`

## pseudocode

```c
__int64 __fastcall STRU::Copy(STRU *this, const unsigned __int8 *a2)
{
  __int64 v2; // r8

  if ( !a2 )
    return 2147942487LL;
  v2 = -1;
  do
    ++v2;
  while ( *(_WORD *)&a2[2 * v2] );
  return STRU::AuxAppend(this, a2, (unsigned int)(2 * v2), 0, 1);
}

```

## disassembly

```asm
0x180002e90  sub     rsp, 38h
0x180002e94  xor     eax, eax
0x180002e96  test    rdx, rdx
0x180002e99  jz      short loc_180002EBB
0x180002e9b  or      r8, 0FFFFFFFFFFFFFFFFh
0x180002e9f  inc     r8
0x180002ea2  cmp     [rdx+r8*2], ax
0x180002ea7  jnz     short loc_180002E9F
0x180002ea9  add     r8d, r8d; Size
0x180002eac  mov     [rsp+38h+var_18], 1; bool
0x180002eb1  xor     r9d, r9d; unsigned int
0x180002eb4  call    ?AuxAppend@STRU@@AEAAJPEBEKK_N@Z; STRU::AuxAppend(uchar const *,ulong,ulong,bool)
0x180002eb9  jmp     short loc_180002EC0
0x180002ebb  mov     eax, 80070057h
0x180002ec0  add     rsp, 38h
0x180002ec4  retn
```
