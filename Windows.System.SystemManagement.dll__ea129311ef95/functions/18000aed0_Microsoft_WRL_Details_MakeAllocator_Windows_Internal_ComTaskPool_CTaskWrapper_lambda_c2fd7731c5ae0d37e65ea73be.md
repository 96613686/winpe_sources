# Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)

- ea: `0x18000aed0`
- end: `0x18000aee6`
- name: `??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `19`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000a31c`
- `0x18000a3dc`
- `0x18000a4c0`
- `0x18000a558`
- `0x18000a5f0`
- `0x18000a688`
- `0x18000a71c`
- `0x18000a808`
- `0x180010088`
- `0x1800101bc`
- `0x1800134f0`
- `0x1800135b8`
- `0x180017e14`
- `0x180018948`
- `0x180018a1c`
- `0x180018b2c`
- `0x180018c3c`
- `0x180028fed`
- `0x180029276`

## callees

- `0x1800032a4`
- `0x18000aed0`

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
0x18000aed0  sub     rsp, 28h
0x18000aed4  mov     rcx, [rcx]; Block
0x18000aed7  test    rcx, rcx
0x18000aeda  jz      short loc_18000AEE1
0x18000aedc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000aee1  add     rsp, 28h
0x18000aee5  retn
```
