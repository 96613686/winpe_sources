# Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>::Run(void)

- ea: `0x18000dab0`
- end: `0x18000dac0`
- name: `?Run@?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@UEAAXXZ`
- size: `16`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180011010`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>::Run(
        __int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 24LL))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x18000dab0  mov     rcx, [rcx+10h]
0x18000dab4  mov     rax, [rcx]
0x18000dab7  mov     rax, [rax+18h]
0x18000dabb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
