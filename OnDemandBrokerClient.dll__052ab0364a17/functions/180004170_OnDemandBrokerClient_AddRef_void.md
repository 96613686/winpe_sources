# OnDemandBrokerClient::AddRef(void)

- ea: `0x180004170`
- end: `0x18000417d`
- name: `?AddRef@OnDemandBrokerClient@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(OnDemandBrokerClient *this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180005210`
- `0x180005220`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerClient::AddRef(OnDemandBrokerClient *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 16);
}

```

## disassembly

```asm
0x180004170  mov     eax, 1
0x180004175  lock xadd [rcx+40h], eax
0x18000417a  inc     eax
0x18000417c  retn
```
