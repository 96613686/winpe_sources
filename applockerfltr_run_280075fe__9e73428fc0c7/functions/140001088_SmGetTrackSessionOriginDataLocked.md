# SmGetTrackSessionOriginDataLocked

- ea: `0x140001088`
- end: `0x14000109a`
- name: `SmGetTrackSessionOriginDataLocked`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140007e00`

## callees

- `0x140001088`

## pseudocode

```c
__int64 SmGetTrackSessionOriginDataLocked()
{
  __int64 result; // rax

  result = qword_140004078;
  if ( qword_140004078 )
    return *(_QWORD *)qword_140004078;
  return result;
}

```

## disassembly

```asm
0x140001088  mov     rax, cs:qword_140004078
0x14000108f  test    rax, rax
0x140001092  jz      short locret_140001099
0x140001094  mov     rax, [rax]
0x140001097  retn
0x140001099  retn
```
