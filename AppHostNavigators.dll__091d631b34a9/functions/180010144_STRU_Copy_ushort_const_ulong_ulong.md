# STRU::Copy(ushort const *,ulong,ulong)

- ea: `0x180010144`
- end: `0x180010186`
- name: `?Copy@STRU@@QEAAJPEBGKK@Z`
- size: `66`
- prototype: `int __fastcall(STRU *this, const unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001018c`
- `0x1800120ac`
- `0x180012458`
- `0x1800127d0`

## callees

- `0x18000ac50`
- `0x18000b774`
- `0x180010144`

## pseudocode

```c
int __fastcall STRU::Copy(STRU *this, const unsigned __int16 *a2, unsigned int a3)
{
  int result; // eax
  const unsigned __int16 *v5; // r11
  unsigned int v6[2]; // [rsp+20h] [rbp-18h] BYREF

  *(_QWORD *)v6 = 0;
  result = STRU::GetStringCbLengthW(a2, a3, a3, (unsigned __int64 *)v6);
  if ( result >= 0 )
    return STRU::AuxAppend(this, v5, v6[0], 0);
  return result;
}

```

## disassembly

```asm
0x180010144  push    rbx
0x180010146  sub     rsp, 30h
0x18001014a  mov     r11, rdx
0x18001014d  mov     qword ptr [rsp+38h+var_18], 0
0x180010156  mov     rbx, rcx
0x180010159  lea     r9, [rsp+38h+var_18]; unsigned __int64 *
0x18001015e  mov     rcx, r11; unsigned __int16 *
0x180010161  mov     edx, r8d; unsigned int
0x180010164  call    ?GetStringCbLengthW@STRU@@CAJPEBGKKPEA_K@Z; STRU::GetStringCbLengthW(ushort const *,ulong,ulong,unsigned __int64 *)
0x180010169  test    eax, eax
0x18001016b  js      short loc_180010180
0x18001016d  mov     r8d, [rsp+38h+var_18]; unsigned int
0x180010172  xor     r9d, r9d; unsigned int
0x180010175  mov     rdx, r11; unsigned __int16 *
0x180010178  mov     rcx, rbx; this
0x18001017b  call    ?AuxAppend@STRU@@AEAAJPEBGKK@Z; STRU::AuxAppend(ushort const *,ulong,ulong)
0x180010180  add     rsp, 30h
0x180010184  pop     rbx
0x180010185  retn
```
