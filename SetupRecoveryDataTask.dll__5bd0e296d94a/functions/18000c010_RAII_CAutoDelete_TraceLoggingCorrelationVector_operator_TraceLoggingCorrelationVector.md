# RAII::CAutoDelete<TraceLoggingCorrelationVector *>::operator=(TraceLoggingCorrelationVector *)

- ea: `0x18000c010`
- end: `0x18000c03b`
- name: `??4?$CAutoDelete@PEAVTraceLoggingCorrelationVector@@@RAII@@UEAAXPEAVTraceLoggingCorrelationVector@@@Z`
- size: `43`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000d010`

## pseudocode

```c
__int64 __fastcall RAII::CAutoDelete<TraceLoggingCorrelationVector *>::operator=(_QWORD *a1, __int64 a2)
{
  __int64 result; // rax

  result = (*(__int64 (__fastcall **)(_QWORD *))(*a1 + 96LL))(a1);
  a1[1] = a2;
  return result;
}

```

## disassembly

```asm
0x18000c010  mov     [rsp+arg_0], rbx
0x18000c015  push    rdi
0x18000c016  sub     rsp, 20h
0x18000c01a  mov     rax, [rcx]
0x18000c01d  mov     rdi, rdx
0x18000c020  mov     rbx, rcx
0x18000c023  mov     rax, [rax+60h]
0x18000c027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c02c  mov     [rbx+8], rdi
0x18000c030  mov     rbx, [rsp+28h+arg_0]
0x18000c035  add     rsp, 20h
0x18000c039  pop     rdi
0x18000c03a  retn
```
