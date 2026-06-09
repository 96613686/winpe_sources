# __crtCompareStringA_Stub

- ea: `0x180008734`
- end: `0x180008739`
- name: `__crtCompareStringA_Stub`
- size: `5`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180022d4c`

## callees

- `0x180026907`

## pseudocode

```c
// attributes: thunk
__int64 _crtCompareStringA_Stub()
{
  return _crtCompareStringA_0();
}

```

## disassembly

```asm
0x180008734  jmp     __crtCompareStringA_0
```
