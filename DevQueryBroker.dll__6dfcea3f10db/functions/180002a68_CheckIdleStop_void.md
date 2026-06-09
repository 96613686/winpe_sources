# CheckIdleStop(void)

- ea: `0x180002a68`
- end: `0x180002ae5`
- name: `?CheckIdleStop@@YAXXZ`
- size: `125`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002470`
- `0x180002ec0`
- `0x1800043e0`

## callees

- `0x180002a68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ab0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002ab0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a89`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002a89`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002ad9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180002ad9`

## pseudocode

```c
void CheckIdleStop(void)
{
  int v0; // ebx
  struct _LIST_ENTRY *Flink; // rax
  struct _FILETIME *v2; // rdx
  __int64 v3; // [rsp+30h] [rbp+8h] BYREF

  if ( !g_bDqbStopping )
  {
    if ( !g_bDqbRpcIdle )
      goto LABEL_8;
    v0 = 0;
    EnterCriticalSection(&g_csActiveQueriesList);
    Flink = g_activeQueriesList.Flink;
    while ( Flink != &g_activeQueriesList )
    {
      Flink = Flink->Flink;
      ++v0;
    }
    LeaveCriticalSection(&g_csActiveQueriesList);
    if ( v0 )
    {
LABEL_8:
      v2 = 0;
    }
    else
    {
      v3 = -300000000;
      v2 = (struct _FILETIME *)&v3;
    }
    SetThreadpoolTimer(g_dqbIdleStopTimer, v2, 0, 0);
  }
}

```

## disassembly

```asm
0x180002a68  push    rbx
0x180002a6a  sub     rsp, 20h
0x180002a6e  cmp     cs:?g_bDqbStopping@@3JA, 0; long g_bDqbStopping
0x180002a75  jnz     short loc_180002ADF
0x180002a77  cmp     cs:?g_bDqbRpcIdle@@3HA, 0; int g_bDqbRpcIdle
0x180002a7e  jz      short loc_180002ACA
0x180002a80  xor     ebx, ebx
0x180002a82  lea     rcx, ?g_csActiveQueriesList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002a89  call    cs:__imp_EnterCriticalSection
0x180002a8f  mov     rax, cs:?g_activeQueriesList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_activeQueriesList
0x180002a96  lea     rcx, ?g_activeQueriesList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_activeQueriesList
0x180002a9d  jmp     short loc_180002AA4
0x180002a9f  mov     rax, [rax]
0x180002aa2  inc     ebx
0x180002aa4  cmp     rax, rcx
0x180002aa7  jnz     short loc_180002A9F
0x180002aa9  lea     rcx, ?g_csActiveQueriesList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002ab0  call    cs:__imp_LeaveCriticalSection
0x180002ab6  test    ebx, ebx
0x180002ab8  jnz     short loc_180002ACA
0x180002aba  mov     [rsp+28h+arg_0], 0FFFFFFFFEE1E5D00h
0x180002ac3  lea     rdx, [rsp+28h+arg_0]
0x180002ac8  jmp     short loc_180002ACC
0x180002aca  xor     edx, edx; pftDueTime
0x180002acc  mov     rcx, cs:?g_dqbIdleStopTimer@@3PEAU_TP_TIMER@@EA; pti
0x180002ad3  xor     r9d, r9d; msWindowLength
0x180002ad6  xor     r8d, r8d; msPeriod
0x180002ad9  call    cs:__imp_SetThreadpoolTimer
0x180002adf  add     rsp, 20h
0x180002ae3  pop     rbx
0x180002ae4  retn
```
