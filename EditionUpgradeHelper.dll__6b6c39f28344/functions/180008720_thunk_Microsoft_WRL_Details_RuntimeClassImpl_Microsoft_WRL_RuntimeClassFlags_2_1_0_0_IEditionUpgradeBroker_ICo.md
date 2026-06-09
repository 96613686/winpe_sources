# [thunk]:Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::AddRef`adjustor{16}' (void)

- ea: `0x180008720`
- end: `0x180008729`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEditionUpgradeBroker@@UIContainerActivationHelper@@UIClipServiceNotificationHelper@@UIFClipNotificationHelper@@@Details@WRL@Microsoft@@WBA@EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800086e0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::AddRef(
        __int64 a1)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::AddRef(a1 - 16);
}

```

## disassembly

```asm
0x180008720  sub     rcx, 10h
0x180008724  jmp     ?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEditionUpgradeBroker@@UIContainerActivationHelper@@UIClipServiceNotificationHelper@@UIFClipNotificationHelper@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::AddRef(void)
```
