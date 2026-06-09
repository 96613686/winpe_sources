# [thunk]:Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::Release`adjustor{8}' (void)

- ea: `0x18000a500`
- end: `0x18000a509`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64, volatile int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a4a0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::Release(
        __int64 a1,
        volatile int *a2)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::Release(
           a1 - 8,
           a2);
}

```

## disassembly

```asm
0x18000a500  sub     rcx, 8
0x18000a504  jmp     ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::Release(void)
```
