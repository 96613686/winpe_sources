# ThreadProc_WaitToCheckForServerShutdown(void *)

- ea: `0x140004fe0`
- end: `0x14000502a`
- name: `?ThreadProc_WaitToCheckForServerShutdown@@YAKPEAX@Z`
- size: `74`
- prototype: `__int64 __fastcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140004d10`
- `0x140004fe0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004ffa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004ffa`

## pseudocode

```c
__int64 __fastcall ThreadProc_WaitToCheckForServerShutdown(LPVOID lpThreadParameter)
{
  do
  {
    while ( _InterlockedCompareExchange((volatile signed __int32 *)&g_dwTimer, 1, 2) == 2 )
      WaitForSingleObject(g_hQuitEvent, g_ShutdownWaitInMilleseconds);
  }
  while ( _InterlockedCompareExchange((volatile signed __int32 *)&g_dwTimer, 0, 1) != 1 );
  CheckForServerShutdown();
  return 0;
}

```

## disassembly

```asm
0x140004fe0  push    rbx
0x140004fe2  sub     rsp, 20h
0x140004fe6  mov     ebx, 1
0x140004feb  jmp     short loc_140005000
0x140004fed  mov     edx, cs:?g_ShutdownWaitInMilleseconds@@3KA; dwMilliseconds
0x140004ff3  mov     rcx, cs:?g_hQuitEvent@@3PEAXEA; hHandle
0x140004ffa  call    cs:__imp_WaitForSingleObject
0x140005000  mov     eax, 2
0x140005005  lock cmpxchg cs:?g_dwTimer@@3KC, ebx; ulong volatile g_dwTimer
0x14000500d  jz      short loc_140004FED
0x14000500f  xor     ecx, ecx
0x140005011  mov     eax, ebx
0x140005013  lock cmpxchg cs:?g_dwTimer@@3KC, ecx; ulong volatile g_dwTimer
0x14000501b  jnz     short loc_140005000
0x14000501d  call    ?CheckForServerShutdown@@YAJXZ; CheckForServerShutdown(void)
0x140005022  xor     eax, eax
0x140005024  add     rsp, 20h
0x140005028  pop     rbx
0x140005029  retn
```
