# OnDemandBrokerServerProxy::AddRef(void)

- ea: `0x1800041e0`
- end: `0x1800041ed`
- name: `?AddRef@OnDemandBrokerServerProxy@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(OnDemandBrokerServerProxy *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerServerProxy::AddRef(OnDemandBrokerServerProxy *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 2);
}

```

## disassembly

```asm
0x1800041e0  mov     eax, 1
0x1800041e5  lock xadd [rcx+8], eax
0x1800041ea  inc     eax
0x1800041ec  retn
```
