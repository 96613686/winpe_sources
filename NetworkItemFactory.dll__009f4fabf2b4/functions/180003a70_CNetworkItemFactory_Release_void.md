# CNetworkItemFactory::Release(void)

- ea: `0x180003a70`
- end: `0x180003b8d`
- name: `?Release@CNetworkItemFactory@@UEAAKXZ`
- size: `285`
- prototype: `unsigned int __fastcall(CNetworkItemFactory *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callees

- `0x180002f90`
- `0x180003a70`
- `0x18000589c`
- `0x1800070f4`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x180003b20`
- `KERNEL32!CreateTimerQueueTimer` at `0x180003b20`
- `KERNEL32!CreateTimerQueue` at `0x180003aea`
- `KERNEL32!CreateTimerQueue` at `0x180003aea`
- `KERNEL32!LeaveCriticalSection` at `0x180003b60`
- `KERNEL32!LeaveCriticalSection` at `0x180003b60`
- `KERNEL32!DeleteTimerQueueEx` at `0x180003b33`
- `KERNEL32!DeleteTimerQueueEx` at `0x180003b33`
- `KERNEL32!EnterCriticalSection` at `0x180003a8b`
- `KERNEL32!EnterCriticalSection` at `0x180003a8b`

## pseudocode

```c
__int64 __fastcall CNetworkItemFactory::Release(CNetworkItemFactory *this)
{
  CNetworkItemFactory *v2; // rbx
  unsigned __int32 v3; // edi
  HANDLE TimerQueue; // rax

  v2 = 0;
  EnterCriticalSection(&g_lockDll);
  v3 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v3 )
  {
    if ( *((_DWORD *)this + 14) )
    {
      if ( g_hTimer )
        goto LABEL_12;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_182dd27e7f09338048566614cf2976f3_Traceguids);
      }
      TimerQueue = CreateTimerQueue();
      g_hTimerQueue = TimerQueue;
      if ( TimerQueue )
      {
        if ( CreateTimerQueueTimer(&g_hTimer, TimerQueue, DelayUnloadHandler, 0, 0xEA60u, 0, 0) )
          goto LABEL_12;
        DeleteTimerQueueEx(g_hTimerQueue, 0);
        g_hTimerQueue = 0;
        g_hTimer = 0;
      }
    }
    v2 = g_pFactory;
    g_pFactory = 0;
  }
LABEL_12:
  LeaveCriticalSection(&g_lockDll);
  if ( v2 )
  {
    CNetworkItemFactory::~CNetworkItemFactory(v2);
    operator delete(v2);
  }
  return v3;
}

```

## disassembly

```asm
0x180003a70  mov     [rsp+arg_0], rbx
0x180003a75  mov     [rsp+arg_8], rsi
0x180003a7a  push    rdi
0x180003a7b  sub     rsp, 40h
0x180003a7f  mov     rsi, rcx
0x180003a82  xor     ebx, ebx
0x180003a84  lea     rcx, ?g_lockDll@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003a8b  call    cs:__imp_EnterCriticalSection
0x180003a91  or      edi, 0FFFFFFFFh
0x180003a94  lock xadd [rsi+8], edi
0x180003a99  sub     edi, 1
0x180003a9c  jnz     loc_180003B59
0x180003aa2  cmp     [rsi+38h], ebx
0x180003aa5  jz      loc_180003B47
0x180003aab  cmp     cs:?g_hTimer@@3PEAXEA, rbx; void * g_hTimer
0x180003ab2  jnz     loc_180003B59
0x180003ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x180003abf  lea     rax, WPP_GLOBAL_Control
0x180003ac6  cmp     rcx, rax
0x180003ac9  jz      short loc_180003AEA
0x180003acb  cmp     byte ptr [rcx+19h], 4
0x180003acf  jb      short loc_180003AEA
0x180003ad1  test    byte ptr [rcx+1Ch], 2
0x180003ad5  jz      short loc_180003AEA
0x180003ad7  mov     rcx, [rcx+10h]
0x180003adb  lea     edx, [rbx+0Bh]
0x180003ade  lea     r8, WPP_182dd27e7f09338048566614cf2976f3_Traceguids
0x180003ae5  call    WPP_SF_
0x180003aea  call    cs:__imp_CreateTimerQueue
0x180003af0  mov     cs:?g_hTimerQueue@@3PEAXEA, rax; void * g_hTimerQueue
0x180003af7  test    rax, rax
0x180003afa  jz      short loc_180003B47
0x180003afc  mov     [rsp+48h+Flags], ebx; Flags
0x180003b00  lea     r8, ?DelayUnloadHandler@@YAXPEAXE@Z; Callback
0x180003b07  mov     [rsp+48h+Period], ebx; Period
0x180003b0b  lea     rcx, ?g_hTimer@@3PEAXEA; phNewTimer
0x180003b12  xor     r9d, r9d; Parameter
0x180003b15  mov     [rsp+48h+DueTime], 0EA60h; DueTime
0x180003b1d  mov     rdx, rax; TimerQueue
0x180003b20  call    cs:__imp_CreateTimerQueueTimer
0x180003b26  test    eax, eax
0x180003b28  jnz     short loc_180003B59
0x180003b2a  mov     rcx, cs:?g_hTimerQueue@@3PEAXEA; TimerQueue
0x180003b31  xor     edx, edx; CompletionEvent
0x180003b33  call    cs:__imp_DeleteTimerQueueEx
0x180003b39  mov     cs:?g_hTimerQueue@@3PEAXEA, rbx; void * g_hTimerQueue
0x180003b40  mov     cs:?g_hTimer@@3PEAXEA, rbx; void * g_hTimer
0x180003b47  mov     rbx, cs:?g_pFactory@@3PEAVCNetworkItemFactory@@EA; CNetworkItemFactory * g_pFactory
0x180003b4e  mov     cs:?g_pFactory@@3PEAVCNetworkItemFactory@@EA, 0; CNetworkItemFactory * g_pFactory
0x180003b59  lea     rcx, ?g_lockDll@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180003b60  call    cs:__imp_LeaveCriticalSection
0x180003b66  test    rbx, rbx
0x180003b69  jz      short loc_180003B7B
0x180003b6b  mov     rcx, rbx; this
0x180003b6e  call    ??1CNetworkItemFactory@@QEAA@XZ; CNetworkItemFactory::~CNetworkItemFactory(void)
0x180003b73  mov     rcx, rbx; lpMem
0x180003b76  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003b7b  mov     rbx, [rsp+48h+arg_0]
0x180003b80  mov     eax, edi
0x180003b82  mov     rsi, [rsp+48h+arg_8]
0x180003b87  add     rsp, 40h
0x180003b8b  pop     rdi
0x180003b8c  retn
```
