# CPersistStreamInit::WriteTag(uchar,ulong *)

- ea: `0x18001f470`
- end: `0x18001f49a`
- name: `?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z`
- size: `42`
- prototype: `int(CPersistStreamInit *__hidden this, unsigned __int8, unsigned int *)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b728`
- `0x18001ba50`
- `0x18001c6a4`
- `0x18001c818`
- `0x18001ca70`
- `0x18001ce6c`
- `0x18001d168`
- `0x18001d3b4`
- `0x18001d9f4`
- `0x18001e000`
- `0x18001e348`
- `0x18001e384`
- `0x18001e7a4`
- `0x18001eb04`
- `0x18001ec64`
- `0x18001edac`
- `0x18001f1a4`
- `0x18001f2c8`
- `0x18001f36c`

## callees

- `0x18001c6a4`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::WriteTag(CPersistStreamInit *this, unsigned __int8 a2, unsigned int *a3)
{
  return CPersistStreamInit::Write(
           this,
           *(_BYTE **)(*((_QWORD *)this + 9) + 16LL * a2),
           *(unsigned __int8 *)(*((_QWORD *)this + 9) + 16LL * a2 + 8),
           a3,
           0);
}

```

## disassembly

```asm
0x18001f470  sub     rsp, 38h
0x18001f474  movzx   eax, dl
0x18001f477  mov     r9, r8; unsigned int *
0x18001f47a  mov     rdx, [rcx+48h]
0x18001f47e  add     rax, rax
0x18001f481  mov     [rsp+38h+var_18], 0; bool
0x18001f486  movzx   r8d, byte ptr [rdx+rax*8+8]; Size
0x18001f48c  mov     rdx, [rdx+rax*8]; Src
0x18001f490  call    ?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z; CPersistStreamInit::Write(void *,ulong,ulong *,bool)
0x18001f495  add     rsp, 38h
0x18001f499  retn
```
