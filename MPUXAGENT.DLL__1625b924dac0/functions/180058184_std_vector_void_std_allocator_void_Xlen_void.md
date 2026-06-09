# std::vector<void *,std::allocator<void *>>::_Xlen(void)

- ea: `0x180058184`
- end: `0x180058195`
- name: `?_Xlen@?$vector@PEAXV?$allocator@PEAX@std@@@std@@IEBAXXZ`
- size: `17`
- prototype: `void __noreturn()`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x1800345b0`
- `0x180034b88`
- `0x180034c4c`
- `0x180034d40`
- `0x180034e00`
- `0x180035354`
- `0x18003548c`
- `0x18003561c`
- `0x180035788`
- `0x1800384ec`
- `0x18004b4c0`
- `0x18005fc20`
- `0x18005fd20`
- `0x180060c14`
- `0x180060d5c`
- `0x180060e84`
- `0x180066f24`
- `0x180066fec`

## callees

- `0x180008584`

## pseudocode

```c
void __noreturn std::vector<void *>::_Xlen()
{
  sub_180008584("string too long");
}

```

## disassembly

```asm
0x180058184  sub     rsp, 28h
0x180058188  lea     rcx, aStringTooLong
0x18005818f  call    sub_180008584
```
