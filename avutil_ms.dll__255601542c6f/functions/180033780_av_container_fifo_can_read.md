# av_container_fifo_can_read

- ea: `0x180033780`
- end: `0x180033788`
- name: `av_container_fifo_can_read`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180039af0`

## pseudocode

```c
unsigned __int64 __fastcall av_container_fifo_can_read(__int64 *a1)
{
  return av_fifo_can_read(*a1);
}

```

## disassembly

```asm
0x180033780  mov     rcx, [rcx]
0x180033783  jmp     av_fifo_can_read
```
