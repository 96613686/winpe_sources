# std::vector<void *,std::allocator<void *>>::_Xlen(void)

- ea: `0x180058198`
- end: `0x1800581a9`
- name: `?_Xlen@?$vector@PEAXV?$allocator@PEAX@std@@@std@@IEBAXXZ_0`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180034ed8`
- `0x1800358f0`
- `0x180036ac8`
- `0x180057734`
- `0x18005e844`
- `0x18005e960`
- `0x18005ea34`
- `0x18006019c`
- `0x180061650`
- `0x180063ac8`
- `0x180063d50`
- `0x180063ed4`
- `0x180065ce8`

## callees

- `0x180008584`

## pseudocode

```c
void __noreturn std::vector<void *>::_Xlen()
{
  sub_180008584("vector too long");
}

```

## disassembly

```asm
0x180058198  sub     rsp, 28h
0x18005819c  lea     rcx, aVectorTooLong
0x1800581a3  call    sub_180008584
```
