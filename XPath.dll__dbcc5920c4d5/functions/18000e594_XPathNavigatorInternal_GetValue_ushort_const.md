# XPathNavigatorInternal::GetValue(ushort const * *)

- ea: `0x18000e594`
- end: `0x18000e5a3`
- name: `?GetValue@XPathNavigatorInternal@@QEAAJPEAPEBG@Z`
- size: `15`
- prototype: `__int64 __fastcall(XPathNavigatorInternal *__hidden this, const unsigned __int16 **)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800087c0`
- `0x18000a894`
- `0x18000bc00`
- `0x18000c040`
- `0x18000cd00`
- `0x18000cdd0`
- `0x18000eaf0`
- `0x18000ee14`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathNavigatorInternal::GetValue(XPathNavigatorInternal *this, const unsigned __int16 **a2)
{
  return (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 **))(**(_QWORD **)this + 72LL))(*(_QWORD *)this, a2);
}

```

## disassembly

```asm
0x18000e594  mov     rcx, [rcx]
0x18000e597  mov     rax, [rcx]
0x18000e59a  mov     rax, [rax+48h]
0x18000e59e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
