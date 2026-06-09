# [thunk]:Windows::UI::Input::InjectionBrokerImpl::Release`adjustor{8}' (void)

- ea: `0x180007290`
- end: `0x180007299`
- name: `?Release@InjectionBrokerImpl@Input@UI@Windows@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007280`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::InjectionBrokerImpl::Release(__int64 a1)
{
  return Windows::UI::Input::InjectionBrokerImpl::Release((volatile signed __int64 *)(a1 - 8));
}

```

## disassembly

```asm
0x180007290  sub     rcx, 8; this
0x180007294  jmp     ?Release@InjectionBrokerImpl@Input@UI@Windows@@UEAAKXZ; Windows::UI::Input::InjectionBrokerImpl::Release(void)
```
