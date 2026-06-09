# [thunk]:Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x18000a010`
- end: `0x18000a019`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEditionUpgradeBroker@@UIContainerActivationHelper@@UIClipServiceNotificationHelper@@UIFClipNotificationHelper@@@Details@WRL@Microsoft@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009eb0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::QueryInterface(
           a1 - 24,
           a2,
           a3);
}

```

## disassembly

```asm
0x18000a010  sub     rcx, 18h
0x18000a014  jmp     ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEditionUpgradeBroker@@UIContainerActivationHelper@@UIClipServiceNotificationHelper@@UIFClipNotificationHelper@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::QueryInterface(_GUID const &,void * *)
```
