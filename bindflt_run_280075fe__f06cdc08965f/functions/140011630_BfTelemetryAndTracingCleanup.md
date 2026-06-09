# BfTelemetryAndTracingCleanup

- ea: `0x140011630`
- end: `0x14001165e`
- name: `BfTelemetryAndTracingCleanup`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140027078`

## callees

- `0x140011710`
- `0x140011748`

## import_xrefs

- `WppRecorder!imp_WppRecorderLogDelete` at `0x140011647`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x140011647`

## pseudocode

```c
__int64 BfTelemetryAndTracingCleanup()
{
  TraceLoggingUnregister_EtwUnregister();
  imp_WppRecorderLogDelete(WPP_GLOBAL_Control, BfTraceRecorder);
  return WppCleanupKm();
}

```

## disassembly

```asm
0x140011630  sub     rsp, 28h
0x140011634  call    TraceLoggingUnregister_EtwUnregister
0x140011639  mov     rdx, cs:_BfTraceRecorder
0x140011640  mov     rcx, cs:WPP_GLOBAL_Control
0x140011647  call    cs:__imp_imp_WppRecorderLogDelete
0x14001164e  nop     dword ptr [rax+rax+00h]
0x140011653  call    WppCleanupKm
0x140011658  add     rsp, 28h
0x14001165c  retn
```
