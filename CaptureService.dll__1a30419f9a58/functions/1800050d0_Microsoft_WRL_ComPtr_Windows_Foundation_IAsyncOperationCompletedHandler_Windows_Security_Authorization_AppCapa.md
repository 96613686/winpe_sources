# Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::~ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>(void)

- ea: `0x1800050d0`
- end: `0x1800050d5`
- name: `??1?$ComPtr@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(void *)`
- caller_count: `11`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180020a81`
- `0x180020b48`
- `0x180020ba2`
- `0x180020bb4`
- `0x180020bc6`
- `0x180020bd8`
- `0x180020bea`
- `0x180020bfc`
- `0x180020c20`
- `0x180020c32`
- `0x180020c44`

## callees

- `0x180007630`

## pseudocode

```c
// attributes: thunk
void __fastcall Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>::~ComPtr<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>>(
        void *a1)
{
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
}

```

## disassembly

```asm
0x1800050d0  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
