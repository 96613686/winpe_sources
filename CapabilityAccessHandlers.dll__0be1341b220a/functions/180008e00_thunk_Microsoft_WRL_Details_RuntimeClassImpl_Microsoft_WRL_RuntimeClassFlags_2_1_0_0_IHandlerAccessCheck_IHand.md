# [thunk]:Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180008e00`
- end: `0x180008e09`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerAccessCheck@@UIHandlerCustomConsent@@UIHandlerAccessChange@@@Details@WRL@Microsoft@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800024b0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>::QueryInterface(
           a1 - 8,
           a2,
           a3);
}

```

## disassembly

```asm
0x180008e00  sub     rcx, 8
0x180008e04  jmp     ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerAccessCheck@@UIHandlerCustomConsent@@UIHandlerAccessChange@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerCustomConsent,IHandlerAccessChange>::QueryInterface(_GUID const &,void * *)
```
