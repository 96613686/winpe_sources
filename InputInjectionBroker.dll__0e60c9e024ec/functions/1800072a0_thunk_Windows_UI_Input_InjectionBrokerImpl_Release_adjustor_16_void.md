# [thunk]:Windows::UI::Input::InjectionBrokerImpl::Release`adjustor{16}' (void)

- ea: `0x1800072a0`
- end: `0x1800072a9`
- name: `?Release@InjectionBrokerImpl@Input@UI@Windows@@WBA@EAAKXZ`
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
  return Windows::UI::Input::InjectionBrokerImpl::Release((volatile signed __int64 *)(a1 - 16));
}

```

## disassembly

```asm
0x1800072a0  sub     rcx, 10h; this
0x1800072a4  jmp     ?Release@InjectionBrokerImpl@Input@UI@Windows@@UEAAKXZ; Windows::UI::Input::InjectionBrokerImpl::Release(void)
```
