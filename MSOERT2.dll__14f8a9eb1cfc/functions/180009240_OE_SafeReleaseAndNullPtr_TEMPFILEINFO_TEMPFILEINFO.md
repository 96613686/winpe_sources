# OE_SafeReleaseAndNullPtr<TEMPFILEINFO>(TEMPFILEINFO * &)

- ea: `0x180009240`
- end: `0x180009260`
- name: `??$OE_SafeReleaseAndNullPtr@VTEMPFILEINFO@@@@YAXAEAPEAVTEMPFILEINFO@@@Z`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009834`
- `0x18000a420`

## callees

- `0x180009240`
- `0x180009ec8`

## pseudocode

```c
void __fastcall OE_SafeReleaseAndNullPtr<TEMPFILEINFO>(TEMPFILEINFO **a1)
{
  TEMPFILEINFO *v1; // rax

  v1 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    TEMPFILEINFO::Release(v1);
  }
}

```

## disassembly

```asm
0x180009240  sub     rsp, 28h
0x180009244  mov     rax, [rcx]
0x180009247  test    rax, rax
0x18000924a  jz      short loc_18000925B
0x18000924c  mov     qword ptr [rcx], 0
0x180009253  mov     rcx, rax; this
0x180009256  call    ?Release@TEMPFILEINFO@@QEAAXXZ; TEMPFILEINFO::Release(void)
0x18000925b  add     rsp, 28h
0x18000925f  retn
```
