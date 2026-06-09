# DiagHubCommon::ProcessLifetimeMonitor::OnProcessExit(void *,uchar)

- ea: `0x140010fc0`
- end: `0x140010ffc`
- name: `?OnProcessExit@ProcessLifetimeMonitor@DiagHubCommon@@CAXPEAXE@Z`
- size: `60`
- prototype: `void __fastcall(DiagHubCommon::ProcessLifetimeMonitor **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000a278`
- `0x14000a42c`
- `0x140010fc0`
- `0x140010ffc`

## string_xrefs

- `0x140010fdc`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\ProcessLifetimeMonitor.cpp`

## pseudocode

```c
void __fastcall DiagHubCommon::ProcessLifetimeMonitor::OnProcessExit(DiagHubCommon::ProcessLifetimeMonitor **a1)
{
  DiagHubCommon::LogStream *Logger; // rax
  bool v3; // r8

  if ( a1 )
  {
    Logger = DiagHubCommon::Logger::GetLogger();
    DiagHubCommon::LogStream::Write(
      Logger,
      L"D:\\a\\_work\\1\\s\\sources\\Core\\DiagnosticsHub.Common\\ProcessLifetimeMonitor.cpp",
      L"Monitored process (PID: %d) has exited",
      *(unsigned int *)a1);
    DiagHubCommon::ProcessLifetimeMonitor::StopMonitoringProcessEx(a1[4], *(_DWORD *)a1, v3);
  }
}

```

## disassembly

```asm
0x140010fc0  test    rcx, rcx
0x140010fc3  jz      short locret_140010FFB
0x140010fc5  push    rbx
0x140010fc6  sub     rsp, 20h
0x140010fca  mov     rbx, rcx
0x140010fcd  call    ?GetLogger@Logger@DiagHubCommon@@SAAEAV12@XZ
0x140010fd2  mov     r9d, [rbx]
0x140010fd5  lea     r8, aMonitoredProce
0x140010fdc  lea     rdx, aDAWork1SSource_1
0x140010fe3  mov     rcx, rax; this
0x140010fe6  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ
0x140010feb  mov     edx, [rbx]; unsigned int
0x140010fed  mov     rcx, [rbx+20h]; this
0x140010ff1  call    ?StopMonitoringProcessEx@ProcessLifetimeMonitor@DiagHubCommon@@AEAAJI_N@Z
0x140010ff6  add     rsp, 20h
0x140010ffa  pop     rbx
0x140010ffb  retn
```
