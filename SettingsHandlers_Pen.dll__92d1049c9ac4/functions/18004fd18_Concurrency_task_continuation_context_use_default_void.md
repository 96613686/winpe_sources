# Concurrency::task_continuation_context::use_default(void)

- ea: `0x18004fd18`
- end: `0x18004fd30`
- name: `?use_default@task_continuation_context@Concurrency@@SA?AV12@XZ`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x180048808`
- `0x180048c60`

## import_xrefs

- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x18004fd21`
- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x18004fd21`

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
0x18004fd18  push    rbx
0x18004fd1a  sub     rsp, 30h
0x18004fd1e  mov     rbx, rcx
0x18004fd21  call    cs:__imp_??0task_continuation_context@Concurrency@@AEAA@XZ; Concurrency::task_continuation_context::task_continuation_context(void)
0x18004fd27  mov     rax, rbx
0x18004fd2a  add     rsp, 30h
0x18004fd2e  pop     rbx
0x18004fd2f  retn
```
