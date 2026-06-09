# _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)

- ea: `0x1800012e0`
- end: `0x1800012e7`
- name: `?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z`
- size: `7`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180007e70`
- `0x18000e048`
- `0x18000e440`
- `0x18000e550`
- `0x18000e6f8`
- `0x18000efb8`

## pseudocode

```c
_QWORD *__fastcall _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(_QWORD *a1, __int64 a2)
{
  *a1 = a2;
  return a1;
}

```

## disassembly

```asm
0x1800012e0  mov     [rcx], rdx
0x1800012e3  mov     rax, rcx
0x1800012e6  retn
```
