# CRdpSessionAgentProxy::QueryInterface(_GUID const &,void * *)

- ea: `0x1400041e0`
- end: `0x1400041ef`
- name: `?QueryInterface@CRdpSessionAgentProxy@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: `__int64 __fastcall(CRdpSessionAgentProxy *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140004200`

## callees

- `0x140006010`

## pseudocode

```c
__int64 __fastcall CRdpSessionAgentProxy::QueryInterface(
        CRdpSessionAgentProxy *this,
        const struct _GUID *a2,
        void **a3)
{
  return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 6))(
           *((_QWORD *)this + 6),
           a2,
           a3);
}

```

## disassembly

```asm
0x1400041e0  mov     rcx, [rcx+30h]
0x1400041e4  mov     rax, [rcx]
0x1400041e7  mov     rax, [rax]
0x1400041ea  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
