# Windows::Internal::ComTaskPoolHandler::Start(Windows::Internal::IComPoolTask *)

- ea: `0x18004bcd8`
- end: `0x18004bd1b`
- name: `?Start@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIComPoolTask@23@@Z`
- size: `67`
- prototype: `__int64 __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this, struct Windows::Internal::IComPoolTask *)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180049420`
- `0x1800494d0`
- `0x180049580`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bce8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bce8`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18004bd0a`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18004bd0a`

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
0x18004bcd8  mov     [rsp+arg_0], rbx
0x18004bcdd  push    rdi
0x18004bcde  sub     rsp, 30h
0x18004bce2  mov     rbx, rdx
0x18004bce5  mov     rdi, rcx
0x18004bce8  call    cs:__imp_GetCurrentThreadId
0x18004bcee  mov     edx, [rdi+4]
0x18004bcf1  xor     r9d, r9d
0x18004bcf4  mov     ecx, [rdi]
0x18004bcf6  mov     r8d, eax
0x18004bcf9  mov     [rsp+38h+var_10], 0
0x18004bd02  mov     [rdi+8], eax
0x18004bd05  mov     [rsp+38h+var_18], rbx
0x18004bd0a  call    cs:__imp_SHTaskPoolQueueTask
0x18004bd10  mov     rbx, [rsp+38h+arg_0]
0x18004bd15  add     rsp, 30h
0x18004bd19  pop     rdi
0x18004bd1a  retn
```
