# std::unique_ptr<TraceLoggingCorrelationVector,std::default_delete<TraceLoggingCorrelationVector>>::~unique_ptr<TraceLoggingCorrelationVector,std::default_delete<TraceLoggingCorrelationVector>>(void)

- ea: `0x140009c0c`
- end: `0x140009c27`
- name: `??1?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@std@@@std@@QEAA@XZ`
- size: `27`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1400121d8`

## callees

- `0x140002dd8`
- `0x140009c0c`

## pseudocode

```c
void __fastcall std::unique_ptr<TraceLoggingCorrelationVector>::~unique_ptr<TraceLoggingCorrelationVector>(void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    operator delete(v1);
}

```

## disassembly

```asm
0x140009c0c  sub     rsp, 28h
0x140009c10  mov     rcx, [rcx]; Block
0x140009c13  test    rcx, rcx
0x140009c16  jz      short loc_140009C22
0x140009c18  mov     edx, 90h
0x140009c1d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140009c22  add     rsp, 28h
0x140009c26  retn
```
