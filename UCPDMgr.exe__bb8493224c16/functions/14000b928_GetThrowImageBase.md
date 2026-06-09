# _GetThrowImageBase

- ea: `0x14000b928`
- end: `0x14000b93a`
- name: `_GetThrowImageBase`
- size: `18`
- prototype: `__int64()`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c0fc`
- `0x14000c2f8`
- `0x14000c4a4`
- `0x14000ccf0`
- `0x14000ce18`
- `0x14000cf60`
- `0x14000dc74`

## callees

- `0x14000be88`

## pseudocode

```c
__int64 GetThrowImageBase()
{
  return *(_QWORD *)(_vcrt_getptd() + 104);
}

```

## disassembly

```asm
0x14000b928  sub     rsp, 28h
0x14000b92c  call    __vcrt_getptd
0x14000b931  mov     rax, [rax+68h]
0x14000b935  add     rsp, 28h
0x14000b939  retn
```
