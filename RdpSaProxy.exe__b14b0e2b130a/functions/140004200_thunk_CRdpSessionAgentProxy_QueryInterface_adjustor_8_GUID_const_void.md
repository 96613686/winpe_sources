# [thunk]:CRdpSessionAgentProxy::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x140004200`
- end: `0x140004209`
- name: `?QueryInterface@CRdpSessionAgentProxy@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400041e0`

## pseudocode

```c
__int64 __fastcall CRdpSessionAgentProxy::QueryInterface(__int64 a1, const struct _GUID *a2, void **a3)
{
  return CRdpSessionAgentProxy::QueryInterface((CRdpSessionAgentProxy *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x140004200  sub     rcx, 8; this
0x140004204  jmp     ?QueryInterface@CRdpSessionAgentProxy@@UEAAJAEBU_GUID@@PEAPEAX@Z; CRdpSessionAgentProxy::QueryInterface(_GUID const &,void * *)
```
