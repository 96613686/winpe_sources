# Windows::Internal::ComTaskPoolHandler::Start(Windows::Internal::IComPoolTask *)

- ea: `0x180079148`
- end: `0x18007918b`
- name: `?Start@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIComPoolTask@23@@Z`
- size: `67`
- prototype: `__int64 __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this, struct Windows::Internal::IComPoolTask *)`
- caller_count: `9`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180077450`
- `0x18007de90`
- `0x180092bc0`
- `0x180092c70`
- `0x180092d20`
- `0x18009a770`
- `0x1800b79c0`
- `0x1800c6a50`
- `0x1800caa10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180079158`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180079158`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18007917a`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18007917a`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::Start(
        Windows::Internal::ComTaskPoolHandler *this,
        struct Windows::Internal::IComPoolTask *a2)
{
  DWORD CurrentThreadId; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx

  CurrentThreadId = GetCurrentThreadId();
  v5 = *((unsigned int *)this + 1);
  v6 = *(unsigned int *)this;
  *((_DWORD *)this + 2) = CurrentThreadId;
  return SHTaskPoolQueueTask(v6, v5, CurrentThreadId, 0, a2, 0);
}

```

## disassembly

```asm
0x180079148  mov     [rsp+arg_0], rbx
0x18007914d  push    rdi
0x18007914e  sub     rsp, 30h
0x180079152  mov     rbx, rdx
0x180079155  mov     rdi, rcx
0x180079158  call    cs:__imp_GetCurrentThreadId
0x18007915e  mov     edx, [rdi+4]
0x180079161  xor     r9d, r9d
0x180079164  mov     ecx, [rdi]
0x180079166  mov     r8d, eax
0x180079169  mov     [rsp+38h+var_10], 0
0x180079172  mov     [rdi+8], eax
0x180079175  mov     [rsp+38h+var_18], rbx
0x18007917a  call    cs:__imp_SHTaskPoolQueueTask
0x180079180  mov     rbx, [rsp+38h+arg_0]
0x180079185  add     rsp, 30h
0x180079189  pop     rdi
0x18007918a  retn
```
