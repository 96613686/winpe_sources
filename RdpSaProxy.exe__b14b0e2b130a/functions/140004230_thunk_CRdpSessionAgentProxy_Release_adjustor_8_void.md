# [thunk]:CRdpSessionAgentProxy::Release`adjustor{8}' (void)

- ea: `0x140004230`
- end: `0x140004239`
- name: `?Release@CRdpSessionAgentProxy@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140004210`

## pseudocode

```c
__int64 __fastcall CRdpSessionAgentProxy::Release(__int64 a1)
{
  return CRdpSessionAgentProxy::Release((CRdpSessionAgentProxy *)(a1 - 8));
}

```

## disassembly

```asm
0x140004230  sub     rcx, 8; this
0x140004234  jmp     ?Release@CRdpSessionAgentProxy@@UEAAKXZ; CRdpSessionAgentProxy::Release(void)
```
