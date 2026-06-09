# OnDemandBrokerServerProxy::OnDemandBrokerServerProxy(void)

- ea: `0x180001d60`
- end: `0x180001d75`
- name: `??0OnDemandBrokerServerProxy@@AEAA@XZ`
- size: `21`
- prototype: `OnDemandBrokerServerProxy *__fastcall(OnDemandBrokerServerProxy *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001c20`

## pseudocode

```c
OnDemandBrokerServerProxy *__fastcall OnDemandBrokerServerProxy::OnDemandBrokerServerProxy(
        OnDemandBrokerServerProxy *this)
{
  OnDemandBrokerServerProxy *result; // rax

  *(_QWORD *)this = &OnDemandBrokerServerProxy::`vftable';
  result = this;
  *((_DWORD *)this + 2) = 1;
  return result;
}

```

## disassembly

```asm
0x180001d60  lea     rax, ??_7OnDemandBrokerServerProxy@@6B@; const OnDemandBrokerServerProxy::`vftable'
0x180001d67  mov     [rcx], rax
0x180001d6a  mov     rax, rcx
0x180001d6d  mov     dword ptr [rcx+8], 1
0x180001d74  retn
```
