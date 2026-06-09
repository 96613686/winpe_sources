# Windows::UI::Input::InjectionBrokerImpl::Release(void)

- ea: `0x180007280`
- end: `0x180007285`
- name: `?Release@InjectionBrokerImpl@Input@UI@Windows@@UEAAKXZ`
- size: `5`
- prototype: `__int64 __fastcall(volatile signed __int64 *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007290`
- `0x1800072a0`

## callees

- `0x180007150`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Windows::UI::Input::InjectionBrokerImpl::Release(volatile signed __int64 *this)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::IInjectionBroker,Microsoft::WRL::FtmBase>::Release(this);
}

```

## disassembly

```asm
0x180007280  jmp     ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInjectionBroker@Input@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::IInjectionBroker,Microsoft::WRL::FtmBase>::Release(void)
```
