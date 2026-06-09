# CRdpSessionAgentProxy::Release(void)

- ea: `0x140004210`
- end: `0x140004220`
- name: `?Release@CRdpSessionAgentProxy@@UEAAKXZ`
- size: `16`
- prototype: `__int64 __fastcall(CRdpSessionAgentProxy *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140004230`

## callees

- `0x140006010`

## pseudocode

```c
__int64 __fastcall CRdpSessionAgentProxy::Release(CRdpSessionAgentProxy *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 16LL))(*((_QWORD *)this + 6));
}

```

## disassembly

```asm
0x140004210  mov     rcx, [rcx+30h]
0x140004214  mov     rax, [rcx]
0x140004217  mov     rax, [rax+10h]
0x14000421b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
