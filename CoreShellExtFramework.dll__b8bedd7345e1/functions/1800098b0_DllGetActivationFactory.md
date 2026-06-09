# DllGetActivationFactory

- ea: `0x1800098b0`
- end: `0x1800098dd`
- name: `DllGetActivationFactory`
- size: `45`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180003110`
- `0x180009488`

## pseudocode

```c
__int64 DllGetActivationFactory()
{
  int v0; // eax

  v0 = sub_180003110();
  return sub_180009488(v0);
}

```

## disassembly

```asm
0x1800098b0  mov     [rsp+arg_0], rbx
0x1800098b5  push    rdi
0x1800098b6  sub     rsp, 20h
0x1800098ba  mov     rbx, rdx
0x1800098bd  mov     rdi, rcx
0x1800098c0  call    sub_180003110
0x1800098c5  mov     r9, rbx
0x1800098c8  mov     r8, rdi
0x1800098cb  mov     rcx, rax; int
0x1800098ce  mov     rbx, [rsp+28h+arg_0]
0x1800098d3  add     rsp, 20h
0x1800098d7  pop     rdi
0x1800098d8  jmp     sub_180009488
```
