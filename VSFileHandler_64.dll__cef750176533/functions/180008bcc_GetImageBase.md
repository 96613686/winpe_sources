# _GetImageBase

- ea: `0x180008bcc`
- end: `0x180008bde`
- name: `_GetImageBase`
- size: `18`
- prototype: `__int64()`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180009758`
- `0x180009a20`
- `0x180009ff8`
- `0x18000a2ec`
- `0x18000a42c`
- `0x18000aeb8`
- `0x18000b1c0`
- `0x18000b2b0`

## callees

- `0x180009518`

## pseudocode

```c
__int64 GetImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 96);
}

```

## disassembly

```asm
0x180008bcc  sub     rsp, 28h
0x180008bd0  call    __vcrt_getptd
0x180008bd5  mov     rax, [rax+60h]
0x180008bd9  add     rsp, 28h
0x180008bdd  retn
```
