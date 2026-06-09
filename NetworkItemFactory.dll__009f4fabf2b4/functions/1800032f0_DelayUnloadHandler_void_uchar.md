# DelayUnloadHandler(void *,uchar)

- ea: `0x1800032f0`
- end: `0x1800033aa`
- name: `?DelayUnloadHandler@@YAXPEAXE@Z`
- size: `186`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x180002f90`
- `0x1800032f0`
- `0x18000589c`
- `0x1800070f4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180003355`
- `KERNEL32!LeaveCriticalSection` at `0x180003355`
- `KERNEL32!DeleteTimerQueueEx` at `0x180003332`
- `KERNEL32!DeleteTimerQueueEx` at `0x180003332`
- `KERNEL32!EnterCriticalSection` at `0x1800032ff`
- `KERNEL32!EnterCriticalSection` at `0x1800032ff`

## pseudocode

```c
void __fastcall DelayUnloadHandler(PVOID a1)
{
  CNetworkItemFactory *v1; // rbx

  v1 = 0;
  EnterCriticalSection(&g_lockDll);
  if ( g_pFactory && !*((_DWORD *)g_pFactory + 2) )
  {
    v1 = g_pFactory;
    g_pFactory = 0;
  }
  if ( g_hTimerQueue )
  {
    DeleteTimerQueueEx(g_hTimerQueue, 0);
    g_hTimerQueue = 0;
    g_hTimer = 0;
  }
  LeaveCriticalSection(&g_lockDll);
  if ( v1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_182dd27e7f09338048566614cf2976f3_Traceguids);
    }
    CNetworkItemFactory::~CNetworkItemFactory(v1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x1800032f0  push    rbx
0x1800032f2  sub     rsp, 20h
0x1800032f6  lea     rcx, ?g_lockDll@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800032fd  xor     ebx, ebx
0x1800032ff  call    cs:__imp_EnterCriticalSection
0x180003305  mov     rax, cs:?g_pFactory@@3PEAVCNetworkItemFactory@@EA; CNetworkItemFactory * g_pFactory
0x18000330c  test    rax, rax
0x18000330f  jz      short loc_180003324
0x180003311  cmp     [rax+8], ebx
0x180003314  jnz     short loc_180003324
0x180003316  mov     rbx, rax
0x180003319  mov     cs:?g_pFactory@@3PEAVCNetworkItemFactory@@EA, 0; CNetworkItemFactory * g_pFactory
0x180003324  mov     rcx, cs:?g_hTimerQueue@@3PEAXEA; TimerQueue
0x18000332b  test    rcx, rcx
0x18000332e  jz      short loc_18000334E
0x180003330  xor     edx, edx; CompletionEvent
0x180003332  call    cs:__imp_DeleteTimerQueueEx
0x180003338  mov     cs:?g_hTimerQueue@@3PEAXEA, 0; void * g_hTimerQueue
0x180003343  mov     cs:?g_hTimer@@3PEAXEA, 0; void * g_hTimer
0x18000334e  lea     rcx, ?g_lockDll@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003355  call    cs:__imp_LeaveCriticalSection
0x18000335b  test    rbx, rbx
0x18000335e  jz      short loc_1800033A4
0x180003360  mov     rcx, cs:WPP_GLOBAL_Control
0x180003367  lea     rax, WPP_GLOBAL_Control
0x18000336e  cmp     rcx, rax
0x180003371  jz      short loc_180003394
0x180003373  cmp     byte ptr [rcx+19h], 4
0x180003377  jb      short loc_180003394
0x180003379  test    byte ptr [rcx+1Ch], 2
0x18000337d  jz      short loc_180003394
0x18000337f  mov     rcx, [rcx+10h]
0x180003383  lea     r8, WPP_182dd27e7f09338048566614cf2976f3_Traceguids
0x18000338a  mov     edx, 0Ah
0x18000338f  call    WPP_SF_
0x180003394  mov     rcx, rbx; this
0x180003397  call    ??1CNetworkItemFactory@@QEAA@XZ; CNetworkItemFactory::~CNetworkItemFactory(void)
0x18000339c  mov     rcx, rbx; lpMem
0x18000339f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800033a4  add     rsp, 20h
0x1800033a8  pop     rbx
0x1800033a9  retn
```
