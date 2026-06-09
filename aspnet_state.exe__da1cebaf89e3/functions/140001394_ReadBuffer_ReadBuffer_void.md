# ReadBuffer::~ReadBuffer(void)

- ea: `0x140001394`
- end: `0x1400013c3`
- name: `??1ReadBuffer@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(void **this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140003588`

## callees

- `0x140001394`
- `0x140004760`
- `0x140004fc8`

## pseudocode

```c
void __fastcall ReadBuffer::~ReadBuffer(void **this)
{
  StateItem *v2; // rcx

  MemFree(this[5]);
  MemFree(this[1]);
  v2 = (StateItem *)this[9];
  if ( v2 )
    StateItem::Release(v2);
}

```

## disassembly

```asm
0x140001394  push    rbx
0x140001396  sub     rsp, 20h
0x14000139a  mov     rbx, rcx
0x14000139d  mov     rcx, [rcx+28h]; lpMem
0x1400013a1  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1400013a6  mov     rcx, [rbx+8]; lpMem
0x1400013aa  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1400013af  mov     rcx, [rbx+48h]; this
0x1400013b3  test    rcx, rcx
0x1400013b6  jz      short loc_1400013BD
0x1400013b8  call    ?Release@StateItem@@QEAAKXZ; StateItem::Release(void)
0x1400013bd  add     rsp, 20h
0x1400013c1  pop     rbx
0x1400013c2  retn
```
