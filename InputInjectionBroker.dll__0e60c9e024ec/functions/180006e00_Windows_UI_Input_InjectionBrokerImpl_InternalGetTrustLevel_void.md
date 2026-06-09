# Windows::UI::Input::InjectionBrokerImpl::InternalGetTrustLevel(void)

- ea: `0x180006e00`
- end: `0x180006e06`
- name: `?InternalGetTrustLevel@InjectionBrokerImpl@Input@UI@Windows@@SA?AW4TrustLevel@@XZ`
- size: `6`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 Windows::UI::Input::InjectionBrokerImpl::InternalGetTrustLevel(void)
{
  return 1;
}

```

## disassembly

```asm
0x180006e00  mov     eax, 1
0x180006e05  retn
```
