# CRegistry::PrepareToReOpen(void)

- ea: `0x18001d034`
- end: `0x18001d04f`
- name: `?PrepareToReOpen@CRegistry@@AEAAXXZ`
- size: `27`
- prototype: `void __fastcall(CRegistry *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002ea4`
- `0x18001ceec`

## callees

- `0x180003958`
- `0x180003ef0`

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
0x18001d034  push    rbx
0x18001d036  sub     rsp, 20h
0x18001d03a  mov     rbx, rcx
0x18001d03d  call    ?Close@CRegistry@@QEAAXXZ
0x18001d042  mov     rcx, rbx; this
0x18001d045  add     rsp, 20h
0x18001d049  pop     rbx
0x18001d04a  jmp     ?SetDefaultValues@CRegistry@@AEAAXXZ
```
