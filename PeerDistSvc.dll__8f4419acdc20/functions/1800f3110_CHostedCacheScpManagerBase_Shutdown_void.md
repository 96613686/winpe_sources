# CHostedCacheScpManagerBase::Shutdown(void)

- ea: `0x1800f3110`
- end: `0x1800f31f5`
- name: `?Shutdown@CHostedCacheScpManagerBase@@UEAAJXZ`
- size: `229`
- prototype: `__int64 __fastcall(CHostedCacheScpManagerBase *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180004510`
- `0x180004874`
- `0x18001f2e0`
- `0x1800f3110`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800f31b2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800f31b2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800f3194`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800f3194`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800f3182`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800f3182`

## pseudocode

```c
__int64 __fastcall CHostedCacheScpManagerBase::Shutdown(CHostedCacheScpManagerBase *this)
{
  unsigned int v2; // ebx
  _BYTE v4[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v5[32]; // [rsp+38h] [rbp-20h] BYREF

  InCritSec::InCritSec((InCritSec *)v5, (CHostedCacheScpManagerBase *)((char *)this + 16), 1);
  InCritSec::InCritSec((InCritSec *)v4, (CHostedCacheScpManagerBase *)((char *)this + 64), 1);
  if ( *((_BYTE *)this + 224) )
  {
    *((_BYTE *)this + 224) = 0;
    InCritSec::~InCritSec((InCritSec *)v4);
    CThreadpoolEnvironment::CleanupGroupMembers((CHostedCacheScpManagerBase *)((char *)this + 112), 1);
    SetThreadpoolTimer(*((PTP_TIMER *)this + 29), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 29), 1);
    InCritSec::InCritSec((InCritSec *)v4, (CHostedCacheScpManagerBase *)((char *)this + 64), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 29));
    *((_QWORD *)this + 29) = 0;
    *((_QWORD *)this + 1) = 0;
    *((_BYTE *)this + 224) = 0;
    InCritSec::~InCritSec((InCritSec *)v4);
    v2 = 0;
  }
  else
  {
    InCritSec::~InCritSec((InCritSec *)v4);
    v2 = -2147020842;
  }
  InCritSec::~InCritSec((InCritSec *)v5);
  return v2;
}

```

## disassembly

```asm
0x1800f3110  mov     [rsp+arg_0], rbx
0x1800f3115  push    rdi
0x1800f3116  sub     rsp, 50h
0x1800f311a  mov     rbx, rcx
0x1800f311d  lea     rdx, [rcx+10h]; struct CritSec *
0x1800f3121  lea     rcx, [rsp+58h+var_20]; this
0x1800f3126  mov     r8b, 1; bool
0x1800f3129  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x1800f312e  mov     r8b, 1; bool
0x1800f3131  lea     rdx, [rbx+40h]; struct CritSec *
0x1800f3135  lea     rcx, [rsp+58h+var_38]; this
0x1800f313a  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x1800f313f  cmp     byte ptr [rbx+0E0h], 0
0x1800f3146  lea     rcx, [rsp+58h+var_38]; this
0x1800f314b  jnz     short loc_1800F315C
0x1800f314d  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1800f3152  mov     ebx, 80070FD6h
0x1800f3157  jmp     loc_1800F31DE
0x1800f315c  mov     byte ptr [rbx+0E0h], 0
0x1800f3163  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1800f3168  lea     rcx, [rbx+70h]; this
0x1800f316c  mov     dl, 1; bool
0x1800f316e  call    ?CleanupGroupMembers@CThreadpoolEnvironment@@QEAAX_N@Z; CThreadpoolEnvironment::CleanupGroupMembers(bool)
0x1800f3173  mov     rcx, [rbx+0E8h]; pti
0x1800f317a  xor     r9d, r9d; msWindowLength
0x1800f317d  xor     r8d, r8d; msPeriod
0x1800f3180  xor     edx, edx; pftDueTime
0x1800f3182  call    cs:__imp_SetThreadpoolTimer
0x1800f3188  mov     rcx, [rbx+0E8h]; pti
0x1800f318f  mov     edx, 1; fCancelPendingCallbacks
0x1800f3194  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800f319a  mov     r8b, 1; bool
0x1800f319d  lea     rdx, [rbx+40h]; struct CritSec *
0x1800f31a1  lea     rcx, [rsp+58h+var_38]; this
0x1800f31a6  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x1800f31ab  mov     rcx, [rbx+0E8h]; pti
0x1800f31b2  call    cs:__imp_CloseThreadpoolTimer
0x1800f31b8  lea     rcx, [rsp+58h+var_38]; this
0x1800f31bd  mov     qword ptr [rbx+0E8h], 0
0x1800f31c8  mov     qword ptr [rbx+8], 0
0x1800f31d0  mov     byte ptr [rbx+0E0h], 0
0x1800f31d7  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1800f31dc  xor     ebx, ebx
0x1800f31de  lea     rcx, [rsp+58h+var_20]; this
0x1800f31e3  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x1800f31e8  mov     eax, ebx
0x1800f31ea  mov     rbx, [rsp+58h+arg_0]
0x1800f31ef  add     rsp, 50h
0x1800f31f3  pop     rdi
0x1800f31f4  retn
```
