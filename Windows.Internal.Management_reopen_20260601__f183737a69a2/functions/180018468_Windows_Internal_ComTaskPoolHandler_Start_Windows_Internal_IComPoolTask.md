# Windows::Internal::ComTaskPoolHandler::Start(Windows::Internal::IComPoolTask *)

- ea: `0x180018468`
- end: `0x1800184b8`
- name: `?Start@ComTaskPoolHandler@Internal@Windows@@QEAAJPEAUIComPoolTask@23@@Z`
- size: `80`
- prototype: `__int64 __fastcall(Windows::Internal::ComTaskPoolHandler *__hidden this, struct Windows::Internal::IComPoolTask *)`
- caller_count: `14`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002fa80`
- `0x18002fb30`
- `0x18002fbe0`
- `0x18002fc90`
- `0x18002fd40`
- `0x18002fdf0`
- `0x18002fea0`
- `0x18002ff50`
- `0x180030000`
- `0x18003dcd0`
- `0x180066d40`
- `0x180066df0`
- `0x180066ea0`
- `0x18006d600`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018478`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018478`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800184a0`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1800184a0`

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
0x180018468  mov     [rsp+arg_0], rbx
0x18001846d  push    rdi
0x18001846e  sub     rsp, 30h
0x180018472  mov     rbx, rdx
0x180018475  mov     rdi, rcx
0x180018478  call    cs:__imp_GetCurrentThreadId
0x18001847f  nop     dword ptr [rax+rax+00h]
0x180018484  mov     edx, [rdi+4]
0x180018487  xor     r9d, r9d
0x18001848a  mov     ecx, [rdi]
0x18001848c  mov     r8d, eax
0x18001848f  mov     [rsp+38h+var_10], 0
0x180018498  mov     [rdi+8], eax
0x18001849b  mov     [rsp+38h+var_18], rbx
0x1800184a0  call    cs:__imp_SHTaskPoolQueueTask
0x1800184a7  nop     dword ptr [rax+rax+00h]
0x1800184ac  mov     rbx, [rsp+38h+arg_0]
0x1800184b1  add     rsp, 30h
0x1800184b5  pop     rdi
0x1800184b6  retn
```
