# Windows::Internal::ComTaskPoolHandler::Start(Windows::Internal::IComPoolTask *)

- ea: `0x18001ac28`
- end: `0x18001ac6b`
- name: `?Start@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIComPoolTask@23@@Z`
- size: `67`
- prototype: `__int64 __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this, struct Windows::Internal::IComPoolTask *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180018b50`
- `0x18001e770`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ac38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ac38`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001ac5a`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001ac5a`

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
0x18001ac28  mov     [rsp+arg_0], rbx
0x18001ac2d  push    rdi
0x18001ac2e  sub     rsp, 30h
0x18001ac32  mov     rbx, rdx
0x18001ac35  mov     rdi, rcx
0x18001ac38  call    cs:__imp_GetCurrentThreadId
0x18001ac3e  mov     edx, [rdi+4]
0x18001ac41  xor     r9d, r9d
0x18001ac44  mov     ecx, [rdi]
0x18001ac46  mov     r8d, eax
0x18001ac49  mov     [rsp+38h+var_10], 0
0x18001ac52  mov     [rdi+8], eax
0x18001ac55  mov     [rsp+38h+var_18], rbx
0x18001ac5a  call    cs:__imp_SHTaskPoolQueueTask
0x18001ac60  mov     rbx, [rsp+38h+arg_0]
0x18001ac65  add     rsp, 30h
0x18001ac69  pop     rdi
0x18001ac6a  retn
```
