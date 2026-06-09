# _GetThrowImageBase

- ea: `0x180008be0`
- end: `0x180008bf2`
- name: `_GetThrowImageBase`
- size: `18`
- prototype: `__int64()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180009758`
- `0x18000995c`
- `0x180009af4`
- `0x18000a2ec`
- `0x18000a42c`
- `0x18000a578`
- `0x18000b1c0`

## callees

- `0x180009518`

## pseudocode

```c
__int64 GetThrowImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 104);
}

```

## disassembly

```asm
0x180008be0  sub     rsp, 28h
0x180008be4  call    __vcrt_getptd
0x180008be9  mov     rax, [rax+68h]
0x180008bed  add     rsp, 28h
0x180008bf1  retn
```
