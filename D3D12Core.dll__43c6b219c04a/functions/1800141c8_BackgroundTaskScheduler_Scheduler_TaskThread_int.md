# BackgroundTaskScheduler::Scheduler::TaskThread(int)

- ea: `0x1800141c8`
- end: `0x180014361`
- name: `?TaskThread@Scheduler@BackgroundTaskScheduler@@IEAAXH@Z`
- size: `409`
- prototype: `void __fastcall(BackgroundTaskScheduler::Scheduler *__hidden this, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180014190`

## callees

- `0x18000ac4c`
- `0x180013dd4`
- `0x1800141c8`
- `0x180014368`
- `0x1800bb480`
- `0x180101b90`
- `0x180262020`

## import_xrefs

- `msvcp_win!_Cnd_wait` at `0x18001426c`
- `msvcp_win!_Cnd_wait` at `0x18001426c`
- `msvcp_win!_Cnd_broadcast` at `0x18001424a`
- `msvcp_win!_Cnd_broadcast` at `0x18001424a`
- `msvcp_win!_Mtx_unlock` at `0x18001427b`
- `msvcp_win!_Mtx_unlock` at `0x1800142e6`
- `msvcp_win!_Mtx_unlock` at `0x18001427b`
- `msvcp_win!_Mtx_unlock` at `0x1800142e6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014317`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014317`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014210`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014210`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18001421e`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18001421e`

## string_xrefs

- `0x1800141f6`: `D3D Background Thread %d`

## pseudocode

```c
void __fastcall BackgroundTaskScheduler::Scheduler::TaskThread(
        BackgroundTaskScheduler::Scheduler *this,
        unsigned int a2)
{
  HANDLE CurrentThread; // rax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rbx
  void (__fastcall *v8)(__int64); // r15
  __int64 v9; // rdi
  volatile signed __int32 *v10; // rbx
  __int64 v11; // rax
  volatile signed __int32 *v12; // rdi
  volatile signed __int32 *v13; // rcx
  WCHAR ThreadDescription[64]; // [rsp+30h] [rbp-B8h] BYREF

  if ( StringCchPrintfW(ThreadDescription, 0x40u, L"D3D Background Thread %d", a2) >= 0 )
  {
    CurrentThread = GetCurrentThread();
    SetThreadDescription(CurrentThread, ThreadDescription);
  }
  std::_Mutex_base::lock((BackgroundTaskScheduler::Scheduler *)((char *)this + 160));
  _InterlockedIncrement((volatile signed __int32 *)this + 17);
  if ( *((_DWORD *)this + 80) == *((_DWORD *)this + 17) )
    _Cnd_broadcast((BackgroundTaskScheduler::Scheduler *)((char *)this + 240));
  while ( (signed int)a2 < *((_DWORD *)this + 80) )
  {
    v5 = *((_QWORD *)this + 7);
    if ( v5 )
    {
      v6 = *((_QWORD *)this + 6);
      v7 = *(_QWORD *)(*((_QWORD *)this + 4) + 8 * (v6 & (*((_QWORD *)this + 5) - 1LL)));
      v8 = *(void (__fastcall **)(__int64))v7;
      v9 = *(_QWORD *)(v7 + 16);
      v10 = *(volatile signed __int32 **)(v7 + 24);
      v11 = v5 - 1;
      *((_QWORD *)this + 7) = v5 - 1;
      if ( v5 != 1 )
        v11 = v6 + 1;
      *((_QWORD *)this + 6) = v11;
      ++*((_DWORD *)this + 16);
      if ( this == (BackgroundTaskScheduler::Scheduler *)-160LL )
        std::_Throw_system_error(1);
      _Mtx_unlock((BackgroundTaskScheduler::Scheduler *)((char *)this + 160));
      v8(v9);
      std::_Mutex_base::lock((BackgroundTaskScheduler::Scheduler *)((char *)this + 160));
      while ( *((_QWORD *)v10 + 3) )
      {
        if ( _InterlockedExchangeAdd(v10 + 4, 0xFFFFFFFF) == 1 )
        {
          SetEvent(*((HANDLE *)v10 + 3));
          v12 = *(volatile signed __int32 **)v10;
          **((_QWORD **)v10 + 1) = *(_QWORD *)v10;
          v13 = *(volatile signed __int32 **)v10;
          *((_QWORD *)v13 + 1) = *((_QWORD *)v10 + 1);
          --*((_QWORD *)this + 1);
          std::_List_node<BackgroundTaskScheduler::Scheduler::QueuedEventSignal,void *>::_Freenode<std::allocator<std::_List_node<BackgroundTaskScheduler::Scheduler::QueuedEventSignal,void *>>>(
            v13,
            v10);
          v10 = v12;
        }
        else
        {
          v10 = *(volatile signed __int32 **)v10;
        }
      }
      --*((_DWORD *)this + 16);
    }
    else
    {
      _Cnd_wait(
        (BackgroundTaskScheduler::Scheduler *)((char *)this + 240),
        (BackgroundTaskScheduler::Scheduler *)((char *)this + 160));
    }
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 17);
  _Mtx_unlock((BackgroundTaskScheduler::Scheduler *)((char *)this + 160));
}

```

## disassembly

```asm
0x1800141c8  mov     [rsp+arg_10], rbx
0x1800141cd  push    rbp
0x1800141ce  push    rsi
0x1800141cf  push    rdi
0x1800141d0  push    r14
0x1800141d2  push    r15
0x1800141d4  sub     rsp, 0C0h
0x1800141db  mov     rax, cs:__security_cookie
0x1800141e2  xor     rax, rsp
0x1800141e5  mov     [rsp+0E8h+var_38], rax
0x1800141ed  mov     r14d, edx
0x1800141f0  mov     rsi, rcx
0x1800141f3  mov     r9d, edx
0x1800141f6  lea     r8, aD3dBackgroundT; "D3D Background Thread %d"
0x1800141fd  mov     edx, 40h ; '@'; unsigned __int64
0x180014202  lea     rcx, [rsp+0E8h+ThreadDescription]; unsigned __int16 *
0x180014207  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001420c  test    eax, eax
0x18001420e  js      short loc_180014224
0x180014210  call    cs:__imp_GetCurrentThread
0x180014216  mov     rcx, rax; hThread
0x180014219  lea     rdx, [rsp+0E8h+ThreadDescription]; lpThreadDescription
0x18001421e  call    cs:__imp_SetThreadDescription
0x180014224  lea     rbp, [rsi+0A0h]
0x18001422b  mov     rcx, rbp; this
0x18001422e  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180014233  lock inc dword ptr [rsi+44h]
0x180014237  mov     eax, [rsi+44h]
0x18001423a  nop
0x18001423b  cmp     [rsi+140h], eax
0x180014241  jnz     short loc_180014250
0x180014243  lea     rcx, [rsi+0F0h]; _Cnd_t
0x18001424a  call    cs:__imp__Cnd_broadcast
0x180014250  cmp     r14d, [rsi+140h]
0x180014257  jge     short loc_180014274
0x180014259  mov     rdx, [rsi+38h]
0x18001425d  test    rdx, rdx
0x180014260  jnz     short loc_1800142A9
0x180014262  lea     rcx, [rsi+0F0h]; _Cnd_t
0x180014269  mov     rdx, rbp; _Mtx_t
0x18001426c  call    cs:__imp__Cnd_wait
0x180014272  jmp     short loc_180014250
0x180014274  lock dec dword ptr [rsi+44h]
0x180014278  mov     rcx, rbp; _Mtx_t
0x18001427b  call    cs:__imp__Mtx_unlock
0x180014281  nop
0x180014282  mov     rcx, [rsp+0E8h+var_38]
0x18001428a  xor     rcx, rsp; StackCookie
0x18001428d  call    __security_check_cookie
0x180014292  mov     rbx, [rsp+0E8h+arg_10]
0x18001429a  add     rsp, 0C0h
0x1800142a1  pop     r15
0x1800142a3  pop     r14
0x1800142a5  pop     rdi
0x1800142a6  pop     rsi
0x1800142a7  pop     rbp
0x1800142a8  retn
0x1800142a9  mov     r8, [rsi+30h]
0x1800142ad  mov     rbx, [rsi+28h]
0x1800142b1  dec     rbx
0x1800142b4  and     rbx, r8
0x1800142b7  mov     rax, [rsi+20h]
0x1800142bb  mov     rbx, [rax+rbx*8]
0x1800142bf  mov     r15, [rbx]
0x1800142c2  mov     rdi, [rbx+10h]
0x1800142c6  mov     rbx, [rbx+18h]
0x1800142ca  lea     rax, [rdx-1]
0x1800142ce  mov     [rsi+38h], rax
0x1800142d2  test    rax, rax
0x1800142d5  jnz     short loc_18001434B
0x1800142d7  mov     [rsi+30h], rax
0x1800142db  inc     dword ptr [rsi+40h]
0x1800142de  test    rbp, rbp
0x1800142e1  jz      short loc_180014356
0x1800142e3  mov     rcx, rbp; _Mtx_t
0x1800142e6  call    cs:__imp__Mtx_unlock
0x1800142ec  mov     rcx, rdi
0x1800142ef  mov     rax, r15
0x1800142f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142f7  mov     rcx, rbp; this
0x1800142fa  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800142ff  cmp     qword ptr [rbx+18h], 0
0x180014304  jz      short loc_180014343
0x180014306  or      eax, 0FFFFFFFFh
0x180014309  lock xadd [rbx+10h], eax
0x18001430e  cmp     eax, 1
0x180014311  jnz     short loc_180014351
0x180014313  mov     rcx, [rbx+18h]; hEvent
0x180014317  call    cs:__imp_SetEvent
0x18001431d  mov     rdi, [rbx]
0x180014320  mov     rax, [rbx+8]
0x180014324  mov     [rax], rdi
0x180014327  mov     rcx, [rbx]
0x18001432a  mov     rax, [rbx+8]
0x18001432e  mov     [rcx+8], rax
0x180014332  dec     qword ptr [rsi+8]
0x180014336  mov     rdx, rbx
0x180014339  call    ??$_Freenode@V?$allocator@U?$_List_node@UQueuedEventSignal@Scheduler@BackgroundTaskScheduler@@PEAX@std@@@std@@@?$_List_node@UQueuedEventSignal@Scheduler@BackgroundTaskScheduler@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@UQueuedEventSignal@Scheduler@BackgroundTaskScheduler@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<BackgroundTaskScheduler::Scheduler::QueuedEventSignal,void *>::_Freenode<std::allocator<std::_List_node<BackgroundTaskScheduler::Scheduler::QueuedEventSignal,void *>>>(std::allocator<std::_List_node<BackgroundTaskScheduler::Scheduler::QueuedEventSignal,void *>> &,std::_List_node<BackgroundTaskScheduler::Scheduler::QueuedEventSignal,void *> *)
0x18001433e  mov     rbx, rdi
0x180014341  jmp     short loc_1800142FF
0x180014343  dec     dword ptr [rsi+40h]
0x180014346  jmp     loc_180014250
0x18001434b  lea     rax, [r8+1]
0x18001434f  jmp     short loc_1800142D7
0x180014351  mov     rbx, [rbx]
0x180014354  jmp     short loc_1800142FF
0x180014356  mov     ecx, 1
0x18001435b  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
```
