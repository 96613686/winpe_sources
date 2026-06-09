# Concurrency::task_continuation_context::use_default(void)

- ea: `0x18001ed08`
- end: `0x18001ed20`
- name: `?use_default@task_continuation_context@Concurrency@@SA?AV12@XZ`
- size: `24`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18000f4d8`
- `0x1800108f0`

## import_xrefs

- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x18001ed11`
- `msvcp_win!??0task_continuation_context@Concurrency@@AEAA@XZ` at `0x18001ed11`

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
0x18001ed08  push    rbx
0x18001ed0a  sub     rsp, 30h
0x18001ed0e  mov     rbx, rcx
0x18001ed11  call    cs:__imp_??0task_continuation_context@Concurrency@@AEAA@XZ; Concurrency::task_continuation_context::task_continuation_context(void)
0x18001ed17  mov     rax, rbx
0x18001ed1a  add     rsp, 30h
0x18001ed1e  pop     rbx
0x18001ed1f  retn
```
