# BampTempBoostsTreeCompareRoutine

- ea: `0x14000c464`
- end: `0x14000c46a`
- name: `BampTempBoostsTreeCompareRoutine`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14000c0c8`
- `0x14000c18c`

## pseudocode

```c
__int64 __fastcall BampTempBoostsTreeCompareRoutine(_DWORD *a1, __int64 a2)
{
  return (unsigned int)(*a1 - *(_DWORD *)(a2 + 24));
}

```

## disassembly

```asm
0x14000c464  mov     eax, [rcx]
0x14000c466  sub     eax, [rdx+18h]
0x14000c469  retn
```
