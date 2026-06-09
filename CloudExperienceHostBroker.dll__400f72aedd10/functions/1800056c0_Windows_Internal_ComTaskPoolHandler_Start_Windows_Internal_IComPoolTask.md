# Windows::Internal::ComTaskPoolHandler::Start(Windows::Internal::IComPoolTask *)

- ea: `0x1800056c0`
- end: `0x180005703`
- name: `?Start@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIComPoolTask@23@@Z`
- size: `67`
- prototype: `__int64 __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this, struct Windows::Internal::IComPoolTask *)`
- caller_count: `5`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ec60`
- `0x1800248c0`
- `0x180024970`
- `0x18002dad0`
- `0x18002db80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800056d0`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800056f2`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800056f2`

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
0x1800056c0  mov     [rsp+arg_0], rbx
0x1800056c5  push    rdi
0x1800056c6  sub     rsp, 30h
0x1800056ca  mov     rbx, rdx
0x1800056cd  mov     rdi, rcx
0x1800056d0  call    cs:__imp_GetCurrentThreadId
0x1800056d6  mov     edx, [rdi+4]
0x1800056d9  xor     r9d, r9d
0x1800056dc  mov     ecx, [rdi]
0x1800056de  mov     r8d, eax
0x1800056e1  mov     [rsp+38h+var_10], 0
0x1800056ea  mov     [rdi+8], eax
0x1800056ed  mov     [rsp+38h+var_18], rbx
0x1800056f2  call    cs:__imp_SHTaskPoolQueueTask
0x1800056f8  mov     rbx, [rsp+38h+arg_0]
0x1800056fd  add     rsp, 30h
0x180005701  pop     rdi
0x180005702  retn
```
