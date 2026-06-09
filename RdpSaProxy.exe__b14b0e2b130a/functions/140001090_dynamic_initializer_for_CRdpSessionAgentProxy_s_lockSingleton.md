# _dynamic_initializer_for__CRdpSessionAgentProxy::s_lockSingleton__

- ea: `0x140001090`
- end: `0x14000109e`
- name: `_dynamic_initializer_for__CRdpSessionAgentProxy::s_lockSingleton__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `KERNEL32!InitializeSRWLock` at `0x140001097`

## pseudocode

```c
void dynamic_initializer_for__CRdpSessionAgentProxy::s_lockSingleton__()
{
  InitializeSRWLock(&CRdpSessionAgentProxy::s_lockSingleton);
}

```

## disassembly

```asm
0x140001090  lea     rcx, ?s_lockSingleton@CRdpSessionAgentProxy@@0VSlimRWLock@@A; SlimRWLock CRdpSessionAgentProxy::s_lockSingleton
0x140001097  jmp     cs:__imp_InitializeSRWLock
```
