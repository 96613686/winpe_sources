# Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)

- ea: `0x180006574`
- end: `0x18000658a`
- name: `??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `14`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800063c4`
- `0x180008578`
- `0x180008638`
- `0x18000874c`
- `0x180008844`
- `0x180008950`
- `0x180008a90`
- `0x1800141a0`
- `0x180014268`
- `0x1800143a8`
- `0x1800144e8`
- `0x180014628`
- `0x180014768`
- `0x1800263a2`

## callees

- `0x180003bc4`
- `0x180006574`

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
0x180006574  sub     rsp, 28h
0x180006578  mov     rcx, [rcx]; Block
0x18000657b  test    rcx, rcx
0x18000657e  jz      short loc_180006585
0x180006580  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006585  add     rsp, 28h
0x180006589  retn
```
