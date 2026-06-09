# WaitToCheckForServerShutdown(void)

- ea: `0x140005030`
- end: `0x1400050b2`
- name: `?WaitToCheckForServerShutdown@@YAHXZ`
- size: `130`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004d60`
- `0x1400054fc`

## callees

- `0x140004d10`
- `0x140005030`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005095`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005095`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140005082`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140005082`

## pseudocode

```c
__int64 WaitToCheckForServerShutdown(void)
{
  unsigned int v0; // ebx
  HANDLE Thread; // rax

  v0 = 0;
  if ( g_fMayExitProcess && !g_fForceServerExit )
  {
    if ( _InterlockedCompareExchange((volatile signed __int32 *)&g_dwTimer, 2, 1) == 1 )
    {
      return 1;
    }
    else if ( !_InterlockedCompareExchange((volatile signed __int32 *)&g_dwTimer, 2, 0) )
    {
      Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)ThreadProc_WaitToCheckForServerShutdown, 0, 0, 0);
      if ( Thread )
      {
        v0 = 1;
        CloseHandle(Thread);
      }
      else
      {
        CheckForServerShutdown();
        _InterlockedExchange((volatile __int32 *)&g_dwTimer, 0);
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x140005030  push    rbx
0x140005032  sub     rsp, 30h
0x140005036  xor     ebx, ebx
0x140005038  cmp     cs:?g_fMayExitProcess@@3_NA, bl; bool g_fMayExitProcess
0x14000503e  jz      short loc_1400050AA
0x140005040  mov     al, cs:?g_fForceServerExit@@3_NC; bool volatile g_fForceServerExit
0x140005046  test    al, al
0x140005048  jnz     short loc_1400050AA
0x14000504a  lea     ecx, [rbx+2]
0x14000504d  lea     eax, [rbx+1]
0x140005050  lock cmpxchg cs:?g_dwTimer@@3KC, ecx; ulong volatile g_dwTimer
0x140005058  jnz     short loc_14000505F
0x14000505a  lea     ebx, [rcx-1]
0x14000505d  jmp     short loc_1400050AA
0x14000505f  xor     eax, eax
0x140005061  lock cmpxchg cs:?g_dwTimer@@3KC, ecx; ulong volatile g_dwTimer
0x140005069  jnz     short loc_1400050AA
0x14000506b  mov     [rsp+38h+lpThreadId], rbx; lpThreadId
0x140005070  lea     r8, ?ThreadProc_WaitToCheckForServerShutdown@@YAKPEAX@Z; lpStartAddress
0x140005077  xor     r9d, r9d; lpParameter
0x14000507a  mov     [rsp+38h+dwCreationFlags], ebx; dwCreationFlags
0x14000507e  xor     edx, edx; dwStackSize
0x140005080  xor     ecx, ecx; lpThreadAttributes
0x140005082  call    cs:__imp_CreateThread
0x140005088  test    rax, rax
0x14000508b  jz      short loc_14000509D
0x14000508d  mov     rcx, rax; hObject
0x140005090  mov     ebx, 1
0x140005095  call    cs:__imp_CloseHandle
0x14000509b  jmp     short loc_1400050AA
0x14000509d  call    ?CheckForServerShutdown@@YAJXZ; CheckForServerShutdown(void)
0x1400050a2  xor     ecx, ecx
0x1400050a4  xchg    ecx, cs:?g_dwTimer@@3KC; ulong volatile g_dwTimer
0x1400050aa  mov     eax, ebx
0x1400050ac  add     rsp, 30h
0x1400050b0  pop     rbx
0x1400050b1  retn
```
