# _GetThrowImageBase

- ea: `0x1800088c0`
- end: `0x1800088d2`
- name: `_GetThrowImageBase`
- size: `18`
- prototype: `__int64()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180009218`
- `0x180009410`
- `0x1800095ac`
- `0x180009e00`
- `0x180009f20`
- `0x18000a060`
- `0x18000acd0`

## callees

- `0x180008fc8`

## pseudocode

```c
__int64 GetThrowImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 104);
}

```

## disassembly

```asm
0x1800088c0  sub     rsp, 28h
0x1800088c4  call    __vcrt_getptd
0x1800088c9  mov     rax, [rax+68h]
0x1800088cd  add     rsp, 28h
0x1800088d1  retn
```
