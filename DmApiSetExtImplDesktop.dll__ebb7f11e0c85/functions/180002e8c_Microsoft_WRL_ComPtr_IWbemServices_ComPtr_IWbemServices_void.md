# Microsoft::WRL::ComPtr<IWbemServices>::~ComPtr<IWbemServices>(void)

- ea: `0x180002e8c`
- end: `0x180002e91`
- name: `??1?$ComPtr@UIWbemServices@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a730`
- `0x18000a742`
- `0x18000a79c`
- `0x18000a7ae`

## callees

- `0x180004304`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<IWbemServices>::~ComPtr<IWbemServices>(__int64 *a1)
{
  return Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(a1);
}

```

## disassembly

```asm
0x180002e8c  jmp     ?InternalRelease@?$ComPtr@UIMobileBroadbandDeviceInformation@NetworkOperators@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandDeviceInformation>::InternalRelease(void)
```
