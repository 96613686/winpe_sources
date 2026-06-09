# CRdpSessionAgentProxy::AddRef(void)

- ea: `0x1400039b0`
- end: `0x1400039c0`
- name: `?AddRef@CRdpSessionAgentProxy@@UEAAKXZ`
- size: `16`
- prototype: `__int64 __fastcall(CRdpSessionAgentProxy *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400039d0`

## callees

- `0x140006010`

## pseudocode

```c
__int64 __fastcall CRdpSessionAgentProxy::AddRef(CRdpSessionAgentProxy *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 8LL))(*((_QWORD *)this + 6));
}

```

## disassembly

```asm
0x1400039b0  mov     rcx, [rcx+30h]
0x1400039b4  mov     rax, [rcx]
0x1400039b7  mov     rax, [rax+8]
0x1400039bb  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
