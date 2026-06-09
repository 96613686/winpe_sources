# DqbIdleStopTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180002ba0`
- end: `0x180002c19`
- name: `?DqbIdleStopTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `121`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180002ba0`
- `0x180002c20`

## import_xrefs

- `RPCRT4!RpcServerInterfaceGroupDeactivate` at `0x180002bd8`
- `RPCRT4!RpcServerInterfaceGroupDeactivate` at `0x180002bd8`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180002bfb`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180002bfb`

## pseudocode

```c
void __fastcall DqbIdleStopTimerCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)
{
  _m_prefetchw((const void *)&g_dqbSeviceControlFlags);
  if ( (_InterlockedOr64((volatile signed __int64 *)&g_dqbSeviceControlFlags, 4u) & 1) == 0
    && (unsigned int)RpcServerInterfaceGroupDeactivate(g_dqbRpcInterfaceGroup, 0, Timer) != 1723
    && !_InterlockedExchange(&g_bDqbStopping, 1)
    && !TrySubmitThreadpoolCallback(DqbStopThreadProc, 0, 0) )
  {
    DqbServiceStop();
  }
  _InterlockedAnd64((volatile signed __int64 *)&g_dqbSeviceControlFlags, 0xFFFFFFFFFFFFFFFBuLL);
}

```

## disassembly

```asm
0x180002ba0  push    rbx
0x180002ba2  sub     rsp, 20h
0x180002ba6  prefetchw byte ptr cs:?g_dqbSeviceControlFlags@@3_KC; unsigned __int64 volatile g_dqbSeviceControlFlags
0x180002bad  mov     rax, cs:?g_dqbSeviceControlFlags@@3_KC; unsigned __int64 volatile g_dqbSeviceControlFlags
0x180002bb4  mov     rcx, rax
0x180002bb7  or      rcx, 4
0x180002bbb  lock cmpxchg cs:?g_dqbSeviceControlFlags@@3_KC, rcx; unsigned __int64 volatile g_dqbSeviceControlFlags
0x180002bc4  jnz     short loc_180002BB4
0x180002bc6  mov     ebx, 1
0x180002bcb  test    bl, al
0x180002bcd  jnz     short loc_180002C0A
0x180002bcf  mov     rcx, cs:?g_dqbRpcInterfaceGroup@@3PEAXEA; void * g_dqbRpcInterfaceGroup
0x180002bd6  xor     edx, edx
0x180002bd8  call    cs:__imp_RpcServerInterfaceGroupDeactivate
0x180002bde  cmp     eax, 6BBh
0x180002be3  jz      short loc_180002C0A
0x180002be5  xchg    ebx, cs:?g_bDqbStopping@@3JA; long g_bDqbStopping
0x180002beb  test    ebx, ebx
0x180002bed  jnz     short loc_180002C0A
0x180002bef  xor     r8d, r8d; pcbe
0x180002bf2  lea     rcx, ?DqbStopThreadProc@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180002bf9  xor     edx, edx; pv
0x180002bfb  call    cs:__imp_TrySubmitThreadpoolCallback
0x180002c01  test    eax, eax
0x180002c03  jnz     short loc_180002C0A
0x180002c05  call    ?DqbServiceStop@@YAXXZ; DqbServiceStop(void)
0x180002c0a  lock and cs:?g_dqbSeviceControlFlags@@3_KC, 0FFFFFFFFFFFFFFFBh; unsigned __int64 volatile g_dqbSeviceControlFlags
0x180002c13  add     rsp, 20h
0x180002c17  pop     rbx
0x180002c18  retn
```
