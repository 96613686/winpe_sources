# DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess::~MonitoredProcess(void)

- ea: `0x140010d3c`
- end: `0x140010d62`
- name: `??1MonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400159e2`

## callees

- `0x140010d3c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140010d4e`
- `KERNEL32!CloseHandle` at `0x140010d4e`

## pseudocode

```c
void __fastcall DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess::~MonitoredProcess(
        DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 3);
  if ( v2 )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x140010d3c  push    rbx
0x140010d3e  sub     rsp, 20h
0x140010d42  mov     rbx, rcx
0x140010d45  mov     rcx, [rcx+18h]; hObject
0x140010d49  test    rcx, rcx
0x140010d4c  jz      short loc_140010D5C
0x140010d4e  call    cs:__imp_CloseHandle
0x140010d54  mov     qword ptr [rbx+18h], 0
0x140010d5c  add     rsp, 20h
0x140010d60  pop     rbx
0x140010d61  retn
```
