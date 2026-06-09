# Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>(void)

- ea: `0x180003ee4`
- end: `0x180003efa`
- name: `??1?$MakeAllocator@V?$SimpleSealedActivationFactory@VAppInfoFactoryBrokerServer@StateRepository@Internal@Windows@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(void **)`
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003184`
- `0x180003244`
- `0x1800032fc`
- `0x180003400`
- `0x180003498`
- `0x180006d10`
- `0x180007370`
- `0x180009474`

## callees

- `0x180002154`
- `0x180003ee4`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>::~MakeAllocator<Microsoft::WRL::SimpleSealedActivationFactory<Windows::Internal::StateRepository::AppInfoFactoryBrokerServer,0>>(
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
0x180003ee4  sub     rsp, 28h
0x180003ee8  mov     rcx, [rcx]; Block
0x180003eeb  test    rcx, rcx
0x180003eee  jz      short loc_180003EF5
0x180003ef0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003ef5  add     rsp, 28h
0x180003ef9  retn
```
