# _CTieringEngineLib::ManipulateOptimizationTask_::_1_::catch$12

- ea: `0x14003ffb3`
- end: `0x14003ffe0`
- name: `_CTieringEngineLib::ManipulateOptimizationTask_::_1_::catch$12`
- size: `45`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall CTieringEngineLib::ManipulateOptimizationTask_::_1_::catch_12(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 472) = **(_DWORD **)(a2 + 168);
  return 0;
}

```

## disassembly

```asm
0x14003ffb3  mov     [rsp+arg_8], rdx
0x14003ffb8  push    rbp
0x14003ffb9  sub     rsp, 30h
0x14003ffbd  mov     rbp, rdx
0x14003ffc0  mov     rax, [rbp+0A8h]
0x14003ffc7  mov     ecx, [rax]
0x14003ffc9  mov     [rbp+1D8h], ecx
0x14003ffcf  mov     rax, 0
0x14003ffd9  add     rsp, 30h
0x14003ffdd  pop     rbp
0x14003ffde  retn
```
