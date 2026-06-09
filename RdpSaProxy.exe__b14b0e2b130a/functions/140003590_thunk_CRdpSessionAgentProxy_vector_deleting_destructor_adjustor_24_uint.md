# [thunk]:CRdpSessionAgentProxy::`vector deleting destructor'`adjustor{24}' (uint)

- ea: `0x140003590`
- end: `0x140003599`
- name: `??_ECRdpSessionAgentProxy@@WBI@EAAPEAXI@Z`
- size: `9`
- prototype: `CRdpSessionAgentProxy *__fastcall(__int64, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1400035a0`

## pseudocode

```c
CRdpSessionAgentProxy *__fastcall CRdpSessionAgentProxy::`vector deleting destructor'(__int64 a1, char a2)
{
  return CRdpSessionAgentProxy::`vector deleting destructor'((CRdpSessionAgentProxy *)(a1 - 24), a2);
}

```

## disassembly

```asm
0x140003590  sub     rcx, 18h; this
0x140003594  jmp     ??_ECRdpSessionAgentProxy@@UEAAPEAXI@Z; CRdpSessionAgentProxy::`vector deleting destructor'(uint)
```
