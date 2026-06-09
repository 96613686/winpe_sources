# PimIMService::SubmitTpWork(TpWorkInfo *)

- ea: `0x18000a670`
- end: `0x18000a6b7`
- name: `?SubmitTpWork@PimIMService@@QEAAXPEAUTpWorkInfo@@@Z`
- size: `71`
- prototype: `void __fastcall(PimIMService *__hidden this, struct TpWorkInfo *)`
- caller_count: `7`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180008ab0`
- `0x180008da0`
- `0x18000a610`
- `0x18000cbb0`
- `0x18000cee0`
- `0x18000cf70`
- `0x18000d020`

## callees

- `0x18000a670`
- `0x18000d63c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a680`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a680`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a6b0`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000a69e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000a69e`

## pseudocode

```c
void __fastcall PimIMService::SubmitTpWork(PimIMService *this, struct TpWorkInfo *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8

  EnterCriticalSection(&g_shutdownLock);
  if ( !_InterlockedExchange((volatile __int32 *)a2 + 2, 1) && (int)FailOnServiceShutdown(v4, v3, v5) >= 0 )
    SubmitThreadpoolWork(*(PTP_WORK *)a2);
  LeaveCriticalSection(&g_shutdownLock);
}

```

## disassembly

```asm
0x18000a670  push    rbx
0x18000a672  sub     rsp, 20h
0x18000a676  lea     rcx, ?g_shutdownLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x18000a67d  mov     rbx, rdx
0x18000a680  call    cs:__imp_EnterCriticalSection
0x18000a686  mov     eax, 1
0x18000a68b  xchg    eax, [rbx+8]
0x18000a68e  test    eax, eax
0x18000a690  jnz     short loc_18000A6A4
0x18000a692  call    ?FailOnServiceShutdown@@YAJXZ; FailOnServiceShutdown(void)
0x18000a697  test    eax, eax
0x18000a699  js      short loc_18000A6A4
0x18000a69b  mov     rcx, [rbx]; pwk
0x18000a69e  call    cs:__imp_SubmitThreadpoolWork
0x18000a6a4  lea     rcx, ?g_shutdownLock@@3Vrecursive_mutex@utl@@A; utl::recursive_mutex g_shutdownLock
0x18000a6ab  add     rsp, 20h
0x18000a6af  pop     rbx
0x18000a6b0  jmp     cs:__imp_LeaveCriticalSection
```
