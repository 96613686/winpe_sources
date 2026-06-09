# operator delete(void *,CLKRhashAllocator *,CLKRhashAllocator::Type)

- ea: `0x180007f38`
- end: `0x180007f5d`
- name: `??3@YAXPEAXPEAVCLKRhashAllocator@@W4Type@0@@Z`
- size: `37`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000ac4c`
- `0x18000ac7b`
- `0x18000acad`
- `0x18000acdf`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall operator delete(__int64 a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a2 + 8LL))(a2, a1, 7);
}

```

## disassembly

```asm
0x180007f38  sub     rsp, 28h
0x180007f3c  mov     r9, rdx
0x180007f3f  mov     rax, [rdx]
0x180007f42  mov     r8d, 7
0x180007f48  mov     rdx, rcx
0x180007f4b  mov     rcx, r9
0x180007f4e  mov     rax, [rax+8]
0x180007f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f57  nop
0x180007f58  add     rsp, 28h
0x180007f5c  retn
```
