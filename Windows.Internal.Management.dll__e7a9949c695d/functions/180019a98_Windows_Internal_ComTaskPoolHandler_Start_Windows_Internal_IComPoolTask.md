# Windows::Internal::ComTaskPoolHandler::Start(Windows::Internal::IComPoolTask *)

- ea: `0x180019a98`
- end: `0x180019adb`
- name: `?Start@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIComPoolTask@23@@Z`
- size: `67`
- prototype: `__int64 __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this, struct Windows::Internal::IComPoolTask *)`
- caller_count: `14`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180030e00`
- `0x180030eb0`
- `0x180030f60`
- `0x180031010`
- `0x1800310c0`
- `0x180031170`
- `0x180031220`
- `0x1800312d0`
- `0x180031380`
- `0x18003e300`
- `0x180065c70`
- `0x180065d20`
- `0x180065dd0`
- `0x18006c2d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019aa8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019aa8`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180019aca`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180019aca`

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
0x180019a98  mov     [rsp+arg_0], rbx
0x180019a9d  push    rdi
0x180019a9e  sub     rsp, 30h
0x180019aa2  mov     rbx, rdx
0x180019aa5  mov     rdi, rcx
0x180019aa8  call    cs:__imp_GetCurrentThreadId
0x180019aae  mov     edx, [rdi+4]
0x180019ab1  xor     r9d, r9d
0x180019ab4  mov     ecx, [rdi]
0x180019ab6  mov     r8d, eax
0x180019ab9  mov     [rsp+38h+var_10], 0
0x180019ac2  mov     [rdi+8], eax
0x180019ac5  mov     [rsp+38h+var_18], rbx
0x180019aca  call    cs:__imp_SHTaskPoolQueueTask
0x180019ad0  mov     rbx, [rsp+38h+arg_0]
0x180019ad5  add     rsp, 30h
0x180019ad9  pop     rdi
0x180019ada  retn
```
