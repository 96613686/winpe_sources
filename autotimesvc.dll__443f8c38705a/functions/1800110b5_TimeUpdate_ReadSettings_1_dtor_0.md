# _TimeUpdate::ReadSettings_::_1_::dtor$0

- ea: `0x1800110b5`
- end: `0x1800110c1`
- name: `_TimeUpdate::ReadSettings_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180005574`

## pseudocode

```c
__int64 __fastcall TimeUpdate::ReadSettings_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>(a2 + 144);
}

```

## disassembly

```asm
0x1800110b5  lea     rcx, [rdx+90h]
0x1800110bc  jmp     ??1?$TraceLoggingActivity@$1?g_AutoTimeTraceLoggingId@@3QEBU_tlgProvider_t@@EB$0DAA@$03U_TlgReflectorTag_Param0IsHProvider@@@@QEAA@XZ; TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_AutoTimeTraceLoggingId,768,4,_TlgReflectorTag_Param0IsHProvider>(void)
```
