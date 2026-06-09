# Concurrency::task_continuation_context::use_default(void)

- ea: `0x18001c310`
- end: `0x18001c328`
- name: `?use_default@task_continuation_context@Concurrency@@SA?AV12@XZ`
- size: `24`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18001228c`

## import_xrefs

- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x18001c319`
- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x18001c319`

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
0x18001c310  push    rbx
0x18001c312  sub     rsp, 30h
0x18001c316  mov     rbx, rcx
0x18001c319  call    cs:__imp_??0task_continuation_context@Concurrency@@AEAA@XZ; Concurrency::task_continuation_context::task_continuation_context(void)
0x18001c31f  mov     rax, rbx
0x18001c322  add     rsp, 30h
0x18001c326  pop     rbx
0x18001c327  retn
```
