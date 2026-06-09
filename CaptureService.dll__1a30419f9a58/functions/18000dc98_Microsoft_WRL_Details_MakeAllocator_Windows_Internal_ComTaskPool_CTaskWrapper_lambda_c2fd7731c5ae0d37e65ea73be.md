# Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)

- ea: `0x18000dc98`
- end: `0x18000dcae`
- name: `??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `12`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000c1c4`
- `0x18000c28c`
- `0x18000c34c`
- `0x18000c3e4`
- `0x18000c4d0`
- `0x18000c5bc`
- `0x18000c714`
- `0x180018ee4`
- `0x18001aa94`
- `0x18001ab78`
- `0x18001bbf4`
- `0x180020a93`

## callees

- `0x180003380`
- `0x18000dc98`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x18000dc98  sub     rsp, 28h
0x18000dc9c  mov     rcx, [rcx]; Block
0x18000dc9f  test    rcx, rcx
0x18000dca2  jz      short loc_18000DCA9
0x18000dca4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000dca9  add     rsp, 28h
0x18000dcad  retn
```
