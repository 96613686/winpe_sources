# [thunk]:Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>,Microsoft::WRL::FtmBase>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180015060`
- end: `0x180015069`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncActionWithProgressCompletedHandler@N@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180014f70`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        __int64 *a3)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>,Microsoft::WRL::FtmBase>::QueryInterface(
           a1 - 8,
           a2,
           a3);
}

```

## disassembly

```asm
0x180015060  sub     rcx, 8
0x180015064  jmp     ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncActionWithProgressCompletedHandler@N@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionWithProgressCompletedHandler<double>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)
```
