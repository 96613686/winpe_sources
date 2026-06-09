# locked_pointer<std::list<CThread *,std::allocator<CThread *>>>::operator->(void)

- ea: `0x180006ae4`
- end: `0x180006ae8`
- name: `??C?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@QEAAPEAV?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@XZ`
- size: `4`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180006c3c`

## pseudocode

```c
__int64 __fastcall locked_pointer<std::list<CThread *>>::operator->(__int64 a1)
{
  return *(_QWORD *)a1;
}

```

## disassembly

```asm
0x180006ae4  mov     rax, [rcx]
0x180006ae7  retn
```
