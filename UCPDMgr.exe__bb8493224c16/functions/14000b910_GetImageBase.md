# _GetImageBase

- ea: `0x14000b910`
- end: `0x14000b922`
- name: `_GetImageBase`
- size: `18`
- prototype: `__int64()`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c0fc`
- `0x14000c3c0`
- `0x14000c9e4`
- `0x14000ccf0`
- `0x14000ce18`
- `0x14000d960`
- `0x14000dc74`
- `0x14000dd64`

## callees

- `0x14000be88`

## pseudocode

```c
__int64 GetImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 96);
}

```

## disassembly

```asm
0x14000b910  sub     rsp, 28h
0x14000b914  call    __vcrt_getptd
0x14000b919  mov     rax, [rax+60h]
0x14000b91d  add     rsp, 28h
0x14000b921  retn
```
