# unknown_libname_12

- ea: `0x180018f40`
- end: `0x180018f58`
- name: `unknown_libname_12`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018f28`

## import_xrefs

- `MSVCP140!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x180018f49`
- `MSVCP140!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x180018f49`

## pseudocode

```c
// Microsoft VisualC v7/14 64bit runtime
Concurrency::task_continuation_context *__fastcall unknown_libname_12(Concurrency::task_continuation_context *a1)
{
  Concurrency::task_continuation_context::task_continuation_context(a1);
  return a1;
}

```

## disassembly

```asm
0x180018f40  push    rbx
0x180018f42  sub     rsp, 20h
0x180018f46  mov     rbx, rcx
0x180018f49  call    cs:??0task_continuation_context@Concurrency@@AEAA@XZ
0x180018f4f  mov     rax, rbx
0x180018f52  add     rsp, 20h
0x180018f56  pop     rbx
0x180018f57  retn
```
