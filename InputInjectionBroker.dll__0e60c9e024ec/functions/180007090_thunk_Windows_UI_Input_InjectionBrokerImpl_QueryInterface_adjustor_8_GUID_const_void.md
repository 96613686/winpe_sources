# [thunk]:Windows::UI::Input::InjectionBrokerImpl::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180007090`
- end: `0x180007099`
- name: `?QueryInterface@InjectionBrokerImpl@Input@UI@Windows@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007080`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::InjectionBrokerImpl::QueryInterface(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  return Windows::UI::Input::InjectionBrokerImpl::QueryInterface(a1 - 8, a2, a3);
}

```

## disassembly

```asm
0x180007090  sub     rcx, 8; this
0x180007094  jmp     ?QueryInterface@InjectionBrokerImpl@Input@UI@Windows@@UEAAJAEBU_GUID@@PEAPEAX@Z; Windows::UI::Input::InjectionBrokerImpl::QueryInterface(_GUID const &,void * *)
```
