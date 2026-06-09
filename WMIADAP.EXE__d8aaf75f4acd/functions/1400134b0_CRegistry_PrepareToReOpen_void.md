# CRegistry::PrepareToReOpen(void)

- ea: `0x1400134b0`
- end: `0x1400134cb`
- name: `?PrepareToReOpen@CRegistry@@AEAAXXZ`
- size: `27`
- prototype: `void __fastcall(CRegistry *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400120e0`
- `0x1400131d0`
- `0x1400132d0`

## callees

- `0x140012040`
- `0x140013b00`

## pseudocode

```c
void __fastcall CRegistry::PrepareToReOpen(CRegistry *this)
{
  CRegistry::Close(this);
  CRegistry::SetDefaultValues(this);
}

```

## disassembly

```asm
0x1400134b0  push    rbx
0x1400134b2  sub     rsp, 20h
0x1400134b6  mov     rbx, rcx
0x1400134b9  call    ?Close@CRegistry@@QEAAXXZ; CRegistry::Close(void)
0x1400134be  mov     rcx, rbx; this
0x1400134c1  add     rsp, 20h
0x1400134c5  pop     rbx
0x1400134c6  jmp     ?SetDefaultValues@CRegistry@@AEAAXXZ; CRegistry::SetDefaultValues(void)
```
