# RAII::CAutoDelete<TraceLoggingCorrelationVector *>::operator=(TraceLoggingCorrelationVector *)

- ea: `0x180004080`
- end: `0x1800040ab`
- name: `??4?$CAutoDelete@PEAVTraceLoggingCorrelationVector@@@RAII@@UEAAXPEAVTraceLoggingCorrelationVector@@@Z`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180015010`

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
0x180004080  mov     [rsp+arg_0], rbx
0x180004085  push    rdi
0x180004086  sub     rsp, 20h
0x18000408a  mov     rax, [rcx]
0x18000408d  mov     rdi, rdx
0x180004090  mov     rbx, rcx
0x180004093  mov     rax, [rax+60h]
0x180004097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000409c  mov     [rbx+8], rdi
0x1800040a0  mov     rbx, [rsp+28h+arg_0]
0x1800040a5  add     rsp, 20h
0x1800040a9  pop     rdi
0x1800040aa  retn
```
