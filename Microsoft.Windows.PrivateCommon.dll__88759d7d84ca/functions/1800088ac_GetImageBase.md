# _GetImageBase

- ea: `0x1800088ac`
- end: `0x1800088be`
- name: `_GetImageBase`
- size: `18`
- prototype: `__int64()`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180009218`
- `0x1800094d4`
- `0x180009af8`
- `0x180009e00`
- `0x180009f20`
- `0x18000a9c4`
- `0x18000acd0`
- `0x18000adb8`

## callees

- `0x180008fc8`

## pseudocode

```c
__int64 GetImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 96);
}

```

## disassembly

```asm
0x1800088ac  sub     rsp, 28h
0x1800088b0  call    __vcrt_getptd
0x1800088b5  mov     rax, [rax+60h]
0x1800088b9  add     rsp, 28h
0x1800088bd  retn
```
