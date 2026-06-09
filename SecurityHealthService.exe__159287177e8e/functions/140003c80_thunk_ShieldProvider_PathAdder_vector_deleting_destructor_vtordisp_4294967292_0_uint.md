# [thunk]:ShieldProvider::PathAdder::`vector deleting destructor'`vtordisp{4294967292,0}' (uint)

- ea: `0x140003c80`
- end: `0x140003c8c`
- name: `??_EPathAdder@ShieldProvider@@$4PPPPPPPM@A@EAAPEAXI@Z`
- size: `12`
- prototype: `void *__fastcall(__int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003d24`

## pseudocode

```c
void *__fastcall ShieldProvider::PathAdder::`vector deleting destructor'(__int64 a1, unsigned int a2)
{
  return ShieldProvider::PathAdder::`vector deleting destructor'(
           (ShieldProvider::PathAdder *)(a1 - *(int *)(a1 - 4)),
           a2);
}

```

## disassembly

```asm
0x140003c80  movsxd  rax, dword ptr [rcx-4]
0x140003c84  sub     rcx, rax; this
0x140003c87  jmp     ??_EPathAdder@ShieldProvider@@UEAAPEAXI@Z; ShieldProvider::PathAdder::`vector deleting destructor'(uint)
```
