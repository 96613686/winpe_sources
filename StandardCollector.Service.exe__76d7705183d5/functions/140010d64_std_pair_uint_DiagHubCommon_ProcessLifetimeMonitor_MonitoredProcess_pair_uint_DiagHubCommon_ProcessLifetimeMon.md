# std::pair<uint,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>::~pair<uint,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>(void)

- ea: `0x140010d64`
- end: `0x140010d8a`
- name: `??1?$pair@IUMonitoredProcess@ProcessLifetimeMonitor@DiagHubCommon@@@std@@QEAA@XZ`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400159ee`

## callees

- `0x140010d64`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140010d76`
- `KERNEL32!CloseHandle` at `0x140010d76`

## pseudocode

```c
BOOL __fastcall std::pair<unsigned int,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>::~pair<unsigned int,DiagHubCommon::ProcessLifetimeMonitor::MonitoredProcess>(
        __int64 a1)
{
  void *v2; // rcx
  BOOL result; // eax

  v2 = *(void **)(a1 + 32);
  if ( v2 )
  {
    result = CloseHandle(v2);
    *(_QWORD *)(a1 + 32) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140010d64  push    rbx
0x140010d66  sub     rsp, 20h
0x140010d6a  mov     rbx, rcx
0x140010d6d  mov     rcx, [rcx+20h]; hObject
0x140010d71  test    rcx, rcx
0x140010d74  jz      short loc_140010D84
0x140010d76  call    cs:__imp_CloseHandle
0x140010d7c  mov     qword ptr [rbx+20h], 0
0x140010d84  add     rsp, 20h
0x140010d88  pop     rbx
0x140010d89  retn
```
