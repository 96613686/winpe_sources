# locked_pointer<std::list<CThread *,std::allocator<CThread *>>>::locked_pointer<std::list<CThread *,std::allocator<CThread *>>>(void)

- ea: `0x1800066e4`
- end: `0x1800066f7`
- name: `??0?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@QEAA@XZ`
- size: `19`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180006c3c`

## pseudocode

```c
_QWORD *__fastcall locked_pointer<std::list<CThread *>>::locked_pointer<std::list<CThread *>>(_QWORD *a1)
{
  _QWORD *result; // rax

  *a1 = 0;
  result = a1;
  a1[1] = 0;
  return result;
}

```

## disassembly

```asm
0x1800066e4  mov     qword ptr [rcx], 0
0x1800066eb  mov     rax, rcx
0x1800066ee  mov     qword ptr [rcx+8], 0
0x1800066f6  retn
```
