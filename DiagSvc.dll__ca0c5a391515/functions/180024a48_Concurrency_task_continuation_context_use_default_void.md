# Concurrency::task_continuation_context::use_default(void)

- ea: `0x180024a48`
- end: `0x180024a60`
- name: `?use_default@task_continuation_context@Concurrency@@SA?AV12@XZ`
- size: `24`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18001dd6c`

## import_xrefs

- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x180024a51`
- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x180024a51`

## pseudocode

```c
Concurrency::task_continuation_context *__fastcall Concurrency::task_continuation_context::use_default(
        Concurrency::task_continuation_context *a1)
{
  Concurrency::task_continuation_context::task_continuation_context(a1);
  return a1;
}

```

## disassembly

```asm
0x180024a48  push    rbx
0x180024a4a  sub     rsp, 30h
0x180024a4e  mov     rbx, rcx
0x180024a51  call    cs:__imp_??0task_continuation_context@Concurrency@@AEAA@XZ; Concurrency::task_continuation_context::task_continuation_context(void)
0x180024a57  mov     rax, rbx
0x180024a5a  add     rsp, 30h
0x180024a5e  pop     rbx
0x180024a5f  retn
```
