# _CConfigSource::ParseSourceDatastore_::_1_::dtor$0

- ea: `0x180011c3d`
- end: `0x180011c49`
- name: `_CConfigSource::ParseSourceDatastore_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000cb24`

## pseudocode

```c
__int64 __fastcall CConfigSource::ParseSourceDatastore_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return TraceLoggingActivity<&_tlgProvider_t const * const g_hProvTraceProvider,0,4,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_hProvTraceProvider,0,4,_TlgReflectorTag_Param0IsHProvider>(a2 + 120);
}

```

## disassembly

```asm
0x180011c3d  lea     rcx, [rdx+78h]
0x180011c44  jmp     ??1?$TraceLoggingActivity@$1?g_hProvTraceProvider@@3QEBU_tlgProvider_t@@EB$0A@$03U_TlgReflectorTag_Param0IsHProvider@@@@QEAA@XZ; TraceLoggingActivity<&_tlgProvider_t const * const g_hProvTraceProvider,0,4,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_hProvTraceProvider,0,4,_TlgReflectorTag_Param0IsHProvider>(void)
```
