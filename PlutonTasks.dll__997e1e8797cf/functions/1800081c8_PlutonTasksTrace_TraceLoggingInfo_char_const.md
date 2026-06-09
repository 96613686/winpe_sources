# PlutonTasksTrace::TraceLoggingInfo(char const *,...)

- ea: `0x1800081c8`
- end: `0x180008207`
- name: `?TraceLoggingInfo@PlutonTasksTrace@@SAXPEBDZZ`
- size: `63`
- prototype: `void(const char *, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180008820`

## callees

- `0x180007354`
- `0x180008bd0`

## pseudocode

```c
void PlutonTasksTrace::TraceLoggingInfo(const char *a1, ...)
{
  __int64 *v1; // rax
  __int64 v3; // [rsp+48h] [rbp+10h] BYREF
  va_list va; // [rsp+48h] [rbp+10h]
  va_list va1; // [rsp+50h] [rbp+18h] BYREF

  va_start(va1, a1);
  va_start(va, a1);
  v3 = va_arg(va1, _QWORD);
  v1 = wil::details::static_lazy<PlutonTasksTrace>::get((__int64)a1, v3);
  wil::TraceLoggingProvider::ReportTraceLoggingMessage((wil::TraceLoggingProvider *)v1, a1, va);
}

```

## disassembly

```asm
0x1800081c8  mov     rax, rsp
0x1800081cb  mov     [rax+8], rcx
0x1800081cf  mov     [rax+10h], rdx
0x1800081d3  mov     [rax+18h], r8
0x1800081d7  mov     [rax+20h], r9
0x1800081db  push    rbx
0x1800081dc  sub     rsp, 30h
0x1800081e0  mov     qword ptr [rax-18h], 0
0x1800081e8  lea     rbx, [rax+10h]
0x1800081ec  call    ?get@?$static_lazy@VPlutonTasksTrace@@@details@wil@@QEAAPEAVPlutonTasksTrace@@P6AXXZ@Z; wil::details::static_lazy<PlutonTasksTrace>::get(void (*)(void))
0x1800081f1  mov     rdx, [rsp+38h+arg_0]; char *
0x1800081f6  mov     r8, rbx; char *
0x1800081f9  mov     rcx, rax; this
0x1800081fc  call    ?ReportTraceLoggingMessage@TraceLoggingProvider@wil@@IEAAXPEBDPEAD@Z; wil::TraceLoggingProvider::ReportTraceLoggingMessage(char const *,char *)
0x180008201  add     rsp, 30h
0x180008205  pop     rbx
0x180008206  retn
```
