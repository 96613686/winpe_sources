# CompatTabTraceLoggingHelper::_dynamic_atexit_destructor_for__TelemetryPiiFilter__

- ea: `0x180016930`
- end: `0x18001697c`
- name: `CompatTabTraceLoggingHelper::_dynamic_atexit_destructor_for__TelemetryPiiFilter__`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180012744`
- `0x180016930`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180016965`
- `ntdll!RtlFreeHeap` at `0x180016965`

## pseudocode

```c
BOOLEAN CompatTabTraceLoggingHelper::_dynamic_atexit_destructor_for__TelemetryPiiFilter__()
{
  char *v0; // rbx
  BOOLEAN result; // al

  v0 = (char *)CompatTabTraceLoggingHelper::TelemetryPiiFilter;
  if ( CompatTabTraceLoggingHelper::TelemetryPiiFilter )
  {
    RtlNameValueArray::Free((RtlNameValueArray *)CompatTabTraceLoggingHelper::TelemetryPiiFilter);
    RtlNameValueArray::Free((RtlNameValueArray *)(v0 + 48));
    result = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v0);
  }
  CompatTabTraceLoggingHelper::TelemetryPiiFilter = 0;
  return result;
}

```

## disassembly

```asm
0x180016930  push    rbx
0x180016932  sub     rsp, 20h
0x180016936  mov     rbx, cs:?TelemetryPiiFilter@CompatTabTraceLoggingHelper@@3VPiiFilter@@A; PiiFilter CompatTabTraceLoggingHelper::TelemetryPiiFilter
0x18001693d  test    rbx, rbx
0x180016940  jz      short loc_18001696B
0x180016942  mov     rcx, rbx; this
0x180016945  call    ?Free@RtlNameValueArray@@QEAAXXZ; RtlNameValueArray::Free(void)
0x18001694a  lea     rcx, [rbx+30h]; this
0x18001694e  call    ?Free@RtlNameValueArray@@QEAAXXZ; RtlNameValueArray::Free(void)
0x180016953  mov     rcx, gs:60h
0x18001695c  mov     r8, rbx; P
0x18001695f  xor     edx, edx; Flags
0x180016961  mov     rcx, [rcx+30h]; HeapHandle
0x180016965  call    cs:__imp_RtlFreeHeap
0x18001696b  mov     cs:?TelemetryPiiFilter@CompatTabTraceLoggingHelper@@3VPiiFilter@@A, 0; PiiFilter CompatTabTraceLoggingHelper::TelemetryPiiFilter
0x180016976  add     rsp, 20h
0x18001697a  pop     rbx
0x18001697b  retn
```
