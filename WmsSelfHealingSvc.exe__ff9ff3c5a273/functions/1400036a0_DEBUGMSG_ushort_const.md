# DEBUGMSG(ushort const *,...)

- ea: `0x1400036a0`
- end: `0x1400036d2`
- name: `?DEBUGMSG@@YAXPEBGZZ`
- size: `50`
- prototype: `void(const unsigned __int16 *, ...)`
- caller_count: `25`
- callee_count: `1`
- tags: ``

## callers

- `0x140001cb8`
- `0x140002140`
- `0x140002300`
- `0x140002490`
- `0x1400024d4`
- `0x140002838`
- `0x1400029e8`
- `0x140002c94`
- `0x140005640`
- `0x140005660`
- `0x140005680`
- `0x1400056a0`
- `0x1400056d0`
- `0x1400056f0`
- `0x140005710`
- `0x140005730`
- `0x140005750`
- `0x140005770`
- `0x140006270`
- `0x1400063e0`
- `0x1400068bc`
- `0x140009344`
- `0x140009470`
- `0x14000988c`
- `0x140009cb0`

## callees

- `0x140003948`

## pseudocode

```c
void DEBUGMSG(const unsigned __int16 *a1, ...)
{
  va_list va; // [rsp+48h] [rbp+10h] BYREF

  va_start(va, a1);
  DEBUGMSGV(4u, a1, va);
}

```

## disassembly

```asm
0x1400036a0  mov     rax, rsp
0x1400036a3  mov     [rax+8], rcx
0x1400036a7  mov     [rax+10h], rdx
0x1400036ab  mov     [rax+18h], r8
0x1400036af  mov     [rax+20h], r9
0x1400036b3  sub     rsp, 38h
0x1400036b7  mov     rdx, rcx; unsigned __int16 *
0x1400036ba  mov     qword ptr [rax-18h], 0
0x1400036c2  mov     cl, 4; unsigned __int8
0x1400036c4  lea     r8, [rax+10h]; char *
0x1400036c8  call    ?DEBUGMSGV@@YAXEPEBGPEAD@Z; DEBUGMSGV(uchar,ushort const *,char *)
0x1400036cd  add     rsp, 38h
0x1400036d1  retn
```
