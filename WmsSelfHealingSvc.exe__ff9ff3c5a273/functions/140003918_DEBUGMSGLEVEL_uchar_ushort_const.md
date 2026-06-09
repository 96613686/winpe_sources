# DEBUGMSGLEVEL(uchar,ushort const *,...)

- ea: `0x140003918`
- end: `0x140003941`
- name: `?DEBUGMSGLEVEL@@YAXEPEBGZZ`
- size: `41`
- prototype: `void(unsigned __int8, const unsigned __int16 *, ...)`
- caller_count: `44`
- callee_count: `1`
- tags: ``

## callers

- `0x140001cb8`
- `0x140001e2c`
- `0x140002140`
- `0x140002300`
- `0x1400024d4`
- `0x140002838`
- `0x140002c94`
- `0x14000300c`
- `0x140003150`
- `0x140003218`
- `0x1400036d8`
- `0x140003948`
- `0x140004288`
- `0x14000445c`
- `0x140004760`
- `0x140005988`
- `0x140005bc0`
- `0x1400063e0`
- `0x140006544`
- `0x14000660c`
- `0x1400066f4`
- `0x1400068bc`
- `0x140006a88`
- `0x140006e24`
- `0x140007158`
- `0x1400076e0`
- `0x140007bf8`
- `0x140007d88`
- `0x140007e64`
- `0x140008090`
- `0x140008510`
- `0x140008710`
- `0x140009344`
- `0x140009470`
- `0x14000988c`
- `0x140009cb0`
- `0x140009f88`
- `0x14000a0c8`
- `0x14000a208`
- `0x14000a340`
- `0x14000a4f4`
- `0x14000a61c`
- `0x14000a8dc`
- `0x14000aaa4`

## callees

- `0x140003948`

## pseudocode

```c
void DEBUGMSGLEVEL(unsigned __int8 a1, const unsigned __int16 *a2, ...)
{
  va_list va; // [rsp+50h] [rbp+18h] BYREF

  va_start(va, a2);
  DEBUGMSGV(a1, a2, va);
}

```

## disassembly

```asm
0x140003918  mov     rax, rsp
0x14000391b  mov     [rax+10h], rdx
0x14000391f  mov     [rax+18h], r8
0x140003923  mov     [rax+20h], r9
0x140003927  sub     rsp, 38h
0x14000392b  lea     r8, [rax+18h]; char *
0x14000392f  mov     qword ptr [rax-18h], 0
0x140003937  call    ?DEBUGMSGV@@YAXEPEBGPEAD@Z; DEBUGMSGV(uchar,ushort const *,char *)
0x14000393c  add     rsp, 38h
0x140003940  retn
```
