# OE_DPA_ReleaseCB<TEMPFILEINFO>(TEMPFILEINFO *,void *)

- ea: `0x180009220`
- end: `0x180009238`
- name: `??$OE_DPA_ReleaseCB@VTEMPFILEINFO@@@@YAHPEAVTEMPFILEINFO@@PEAX@Z`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000948c`

## callees

- `0x180009220`
- `0x180009ec8`

## pseudocode

```c
__int64 __fastcall OE_DPA_ReleaseCB<TEMPFILEINFO>(TEMPFILEINFO *a1)
{
  if ( a1 )
    TEMPFILEINFO::Release(a1);
  return 1;
}

```

## disassembly

```asm
0x180009220  sub     rsp, 28h
0x180009224  test    rcx, rcx
0x180009227  jz      short loc_18000922E
0x180009229  call    ?Release@TEMPFILEINFO@@QEAAXXZ; TEMPFILEINFO::Release(void)
0x18000922e  mov     eax, 1
0x180009233  add     rsp, 28h
0x180009237  retn
```
