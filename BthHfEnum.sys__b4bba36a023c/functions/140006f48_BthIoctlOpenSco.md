# BthIoctlOpenSco

- ea: `0x140006f48`
- end: `0x140006f57`
- name: `BthIoctlOpenSco`
- size: `15`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140029170`

## callees

- `0x14001269c`

## pseudocode

```c
__int64 BthIoctlOpenSco()
{
  return ScoConnectionRequest();
}

```

## disassembly

```asm
0x140006f48  sub     rsp, 28h
0x140006f4c  call    ScoConnectionRequest
0x140006f51  add     rsp, 28h
0x140006f55  retn
```
