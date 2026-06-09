# Windows::Internal::ComTaskPoolHandler::Start(Windows::Internal::IComPoolTask *)

- ea: `0x180014d88`
- end: `0x180014dcb`
- name: `?Start@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIComPoolTask@23@@Z`
- size: `67`
- prototype: `__int64 __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this, struct Windows::Internal::IComPoolTask *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180012e30`
- `0x180019bf0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014d98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014d98`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180014dba`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180014dba`

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
0x180014d88  mov     [rsp+arg_0], rbx
0x180014d8d  push    rdi
0x180014d8e  sub     rsp, 30h
0x180014d92  mov     rbx, rdx
0x180014d95  mov     rdi, rcx
0x180014d98  call    cs:__imp_GetCurrentThreadId
0x180014d9e  mov     edx, [rdi+4]
0x180014da1  xor     r9d, r9d
0x180014da4  mov     ecx, [rdi]
0x180014da6  mov     r8d, eax
0x180014da9  mov     [rsp+38h+var_10], 0
0x180014db2  mov     [rdi+8], eax
0x180014db5  mov     [rsp+38h+var_18], rbx
0x180014dba  call    cs:__imp_SHTaskPoolQueueTask
0x180014dc0  mov     rbx, [rsp+38h+arg_0]
0x180014dc5  add     rsp, 30h
0x180014dc9  pop     rdi
0x180014dca  retn
```
