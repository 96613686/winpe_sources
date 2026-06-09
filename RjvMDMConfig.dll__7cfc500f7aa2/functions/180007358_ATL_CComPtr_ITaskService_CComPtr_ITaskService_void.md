# ATL::CComPtr<ITaskService>::~CComPtr<ITaskService>(void)

- ea: `0x180007358`
- end: `0x18000735d`
- name: `??1?$CComPtr@UITaskService@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d493`
- `0x18001d4a5`
- `0x18001d4b7`
- `0x18001d552`

## callees

- `0x180007364`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComPtr<ITaskService>::~CComPtr<ITaskService>(__int64 *a1)
{
  return ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(a1);
}

```

## disassembly

```asm
0x180007358  jmp     ??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)
```
