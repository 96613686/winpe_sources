# __crtCompareStringW_0

- ea: `0x1800268fb`
- end: `0x180026901`
- name: `__crtCompareStringW_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180008740`

## import_xrefs

- `msvcrt!__crtCompareStringW` at `0x1800268fb`

## pseudocode

```c
// attributes: thunk
__int64 _crtCompareStringW_0()
{
  return __crtCompareStringW();
}

```

## disassembly

```asm
0x1800268fb  jmp     cs:__imp___crtCompareStringW
```
