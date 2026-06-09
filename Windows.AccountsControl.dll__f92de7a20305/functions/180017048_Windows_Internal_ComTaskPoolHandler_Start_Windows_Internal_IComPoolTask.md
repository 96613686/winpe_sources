# Windows::Internal::ComTaskPoolHandler::Start(Windows::Internal::IComPoolTask *)

- ea: `0x180017048`
- end: `0x18001708b`
- name: `?Start@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIComPoolTask@23@@Z`
- size: `67`
- prototype: `__int64 __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this, struct Windows::Internal::IComPoolTask *)`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800142b0`
- `0x180029260`
- `0x18003b460`
- `0x180047320`
- `0x180052a60`
- `0x180052b10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017058`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017058`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001707a`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001707a`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::Start(
        Windows::Internal::ComTaskPoolHandler *this,
        struct Windows::Internal::IComPoolTask *a2)
{
  DWORD CurrentThreadId; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx

  CurrentThreadId = GetCurrentThreadId();
  v4 = *((unsigned int *)this + 1);
  v5 = *(unsigned int *)this;
  *((_DWORD *)this + 2) = CurrentThreadId;
  return SHTaskPoolQueueTask(v5, v4, CurrentThreadId, 0);
}

```

## disassembly

```asm
0x180017048  mov     [rsp+arg_0], rbx
0x18001704d  push    rdi
0x18001704e  sub     rsp, 30h
0x180017052  mov     rbx, rdx
0x180017055  mov     rdi, rcx
0x180017058  call    cs:__imp_GetCurrentThreadId
0x18001705e  mov     edx, [rdi+4]
0x180017061  xor     r9d, r9d
0x180017064  mov     ecx, [rdi]
0x180017066  mov     r8d, eax
0x180017069  mov     [rsp+38h+var_10], 0
0x180017072  mov     [rdi+8], eax
0x180017075  mov     [rsp+38h+var_18], rbx
0x18001707a  call    cs:__imp_SHTaskPoolQueueTask
0x180017080  mov     rbx, [rsp+38h+arg_0]
0x180017085  add     rsp, 30h
0x180017089  pop     rdi
0x18001708a  retn
```
