# _CTempSignedLicenseExchangeTaskHandler::Worker_::_1_::dtor$1

- ea: `0x18000cbe8`
- end: `0x18000cbf4`
- name: `_CTempSignedLicenseExchangeTaskHandler::Worker_::_1_::dtor$1`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002398`

## pseudocode

```c
_QWORD *__fastcall CTempSignedLicenseExchangeTaskHandler::Worker_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IApplicationLicenseManager>::~ComPtr<IApplicationLicenseManager>((_QWORD *)(a2 + 120));
}

```

## disassembly

```asm
0x18000cbe8  lea     rcx, [rdx+78h]
0x18000cbef  jmp     ??1?$ComPtr@UIApplicationLicenseManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IApplicationLicenseManager>::~ComPtr<IApplicationLicenseManager>(void)
```
