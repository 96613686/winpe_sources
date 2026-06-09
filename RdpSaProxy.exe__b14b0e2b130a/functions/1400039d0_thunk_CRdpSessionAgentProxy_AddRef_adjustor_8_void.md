# [thunk]:CRdpSessionAgentProxy::AddRef`adjustor{8}' (void)

- ea: `0x1400039d0`
- end: `0x1400039d9`
- name: `?AddRef@CRdpSessionAgentProxy@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400039b0`

## pseudocode

```c
__int64 __fastcall CRdpSessionAgentProxy::AddRef(__int64 a1)
{
  return CRdpSessionAgentProxy::AddRef((CRdpSessionAgentProxy *)(a1 - 8));
}

```

## disassembly

```asm
0x1400039d0  sub     rcx, 8; this
0x1400039d4  jmp     ?AddRef@CRdpSessionAgentProxy@@UEAAKXZ; CRdpSessionAgentProxy::AddRef(void)
```
