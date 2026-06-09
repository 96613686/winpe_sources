# __crtCompareStringA_0

- ea: `0x180026907`
- end: `0x18002690d`
- name: `__crtCompareStringA_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180008734`

## import_xrefs

- `msvcrt!__crtCompareStringA` at `0x180026907`

## pseudocode

```c
// attributes: thunk
__int64 _crtCompareStringA_0()
{
  return __crtCompareStringA();
}

```

## disassembly

```asm
0x180026907  jmp     cs:__imp___crtCompareStringA
```
