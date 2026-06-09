# [thunk]:Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CreateObjectServerTaskBase>::AddRef`adjustor{8}' (void)

- ea: `0x140007960`
- end: `0x140007969`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCreateObjectServerTaskBase@@@Details@WRL@Microsoft@@W7EAAKXZ`
- size: `9`
- prototype: `unsigned int __fastcall(__int64, volatile int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140007950`

## pseudocode

```c
unsigned int __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CreateObjectServerTaskBase>::AddRef(
        __int64 a1,
        volatile int *a2)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CreateObjectServerTaskBase>::AddRef(
           a1 - 8,
           a2);
}

```

## disassembly

```asm
0x140007960  sub     rcx, 8
0x140007964  jmp     ?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCreateObjectServerTaskBase@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CreateObjectServerTaskBase>::AddRef(void)
```
