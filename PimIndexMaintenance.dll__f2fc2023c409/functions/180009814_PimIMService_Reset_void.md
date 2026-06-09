# PimIMService::Reset(void)

- ea: `0x180009814`
- end: `0x180009a5c`
- name: `?Reset@PimIMService@@QEAAJXZ`
- size: `584`
- prototype: `__int64 __fastcall(PimIMService *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008fe0`

## callees

- `0x180002da8`
- `0x18000428c`
- `0x1800047c8`
- `0x18000502c`
- `0x180009814`
- `0x18000b5b8`
- `0x18000b614`
- `0x18000b634`
- `0x18000b654`
- `0x18000b984`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800099ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800099ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009876`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009876`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800098f6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800098f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800098ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800098ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009900`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009900`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009851`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009851`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000993d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000993d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009861`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009861`

## string_xrefs

- `0x1800098d7`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000991c`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x1800099fc`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::Reset(PimIMService *this)
{
  struct _TP_TIMER *v2; // rcx
  struct IUnknown *v3; // rbx
  struct IUnknown *v4; // rdx
  unsigned int v5; // esi
  int v6; // eax
  void *v7; // rcx
  signed int LastError; // eax
  bool v9; // sf
  __int64 v10; // rcx
  int v11; // eax
  struct IUnknown *v13; // [rsp+50h] [rbp+8h] BYREF
  char *v14; // [rsp+58h] [rbp+10h] BYREF

  *((_DWORD *)this + 59) = 0;
  *((_DWORD *)this + 75) = 0;
  *((_DWORD *)this + 124) = 0;
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 61);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 61), 1);
  }
  v3 = 0;
  v13 = 0;
  EnterCriticalSection(&g_shutdownLock);
  v4 = (struct IUnknown *)*((_QWORD *)this + 28);
  if ( v4 )
  {
    ATL::AtlComPtrAssign(&v13, v4);
    v3 = v13;
  }
  v5 = *((_DWORD *)this + 58);
  *((_DWORD *)this + 58) = 0;
  LeaveCriticalSection(&g_shutdownLock);
  if ( v3 )
  {
    if ( v5 )
    {
      v6 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD))v3->lpVtbl[3].Release)(v3, v5);
      if ( v6 < 0 )
        Log_HREvent(
          (unsigned int)v6,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
          319);
    }
  }
  v7 = (void *)*((_QWORD *)this + 38);
  if ( v7 && !SetEvent(v7) )
  {
    LastError = GetLastError();
    v9 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v9 = LastError < 0;
    }
    if ( v9 )
      Log_HREvent(
        (unsigned int)LastError,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        325);
  }
  CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)this + 67), 1, 0);
  *((_QWORD *)this + 68) = 0;
  *((_DWORD *)this + 138) = 0;
  *((_QWORD *)this + 70) = 0;
  *((_DWORD *)this + 142) = 0;
  *((_QWORD *)this + 72) = 0;
  *((_DWORD *)this + 146) = 0;
  *((_QWORD *)this + 74) = 0;
  *((_DWORD *)this + 150) = 0;
  tlx::auto_xxx<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&void CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),0>::_Delete((struct _TP_CLEANUP_GROUP **)this + 67);
  *((_QWORD *)this + 67) = 0;
  tlx::auto_xxx<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),0>::_Delete((struct _TP_POOL **)this + 64);
  *((_QWORD *)this + 64) = 0;
  *((_QWORD *)this + 76) = 0;
  v14 = (char *)this + 240;
  *((_DWORD *)this + 154) = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 30);
  utl::_HashTable<unsigned long,utl::pair<unsigned long const,SyncPartnerData>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,SyncPartnerData>>,0>::_ClearList((char *)this + 248);
  if ( *((_QWORD *)this + 33) )
    utl::_HashTable<unsigned long,utl::pair<unsigned long const,SyncPartnerData>,utl::hash<unsigned long>,utl::equal_to<unsigned long>,utl::allocator<utl::pair<unsigned long const,SyncPartnerData>>,0>::_InitBuckets((char *)this + 248);
  auto_SRWLockBase<_RTL_SRWLOCK,&void AcquireSRWLockExclusive(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *)>::~auto_SRWLockBase<_RTL_SRWLOCK,&void AcquireSRWLockExclusive(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *)>(&v14);
  v10 = *((_QWORD *)this + 27);
  if ( v10 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 64LL))(v10);
    if ( v11 < 0 )
      Log_HREvent(
        (unsigned int)v11,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        351);
  }
  if ( *((_QWORD *)this + 27) )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 27, 0);
  if ( *((_QWORD *)this + 28) )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 28, 0);
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete((void **)this + 38);
  *((_QWORD *)this + 38) = 0;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v13);
  return 0;
}

```

## disassembly

```asm
0x180009814  mov     [rsp+arg_10], rbx
0x180009819  mov     [rsp+arg_18], rbp
0x18000981e  push    rsi
0x18000981f  push    rdi
0x180009820  push    r14
0x180009822  sub     rsp, 30h
0x180009826  xor     ebp, ebp
0x180009828  mov     rdi, rcx
0x18000982b  mov     [rcx+0ECh], ebp
0x180009831  mov     [rcx+12Ch], ebp
0x180009837  mov     [rcx+1F0h], ebp
0x18000983d  mov     rcx, [rcx+1E8h]; pti
0x180009844  test    rcx, rcx
0x180009847  jz      short loc_180009867
0x180009849  xor     r9d, r9d; msWindowLength
0x18000984c  xor     r8d, r8d; msPeriod
0x18000984f  xor     edx, edx; pftDueTime
0x180009851  call    cs:__imp_SetThreadpoolTimer
0x180009857  mov     rcx, [rdi+1E8h]; pti
0x18000985e  lea     edx, [rbp+1]; fCancelPendingCallbacks
0x180009861  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009867  mov     rbx, rbp
0x18000986a  lea     rcx, ?g_shutdownLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x180009871  mov     [rsp+48h+arg_0], rbx
0x180009876  call    cs:__imp_EnterCriticalSection
0x18000987c  lea     r14, [rdi+0E0h]
0x180009883  mov     rdx, [r14]; struct IUnknown *
0x180009886  test    rdx, rdx
0x180009889  jz      short loc_18000989A
0x18000988b  lea     rcx, [rsp+48h+arg_0]; struct IUnknown **
0x180009890  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180009895  mov     rbx, [rsp+48h+arg_0]
0x18000989a  mov     esi, [rdi+0E8h]
0x1800098a0  lea     rcx, ?g_shutdownLock@@3Vrecursive_mutex@utl@@A; lpCriticalSection
0x1800098a7  mov     [rdi+0E8h], ebp
0x1800098ad  call    cs:__imp_LeaveCriticalSection
0x1800098b3  test    rbx, rbx
0x1800098b6  jz      short loc_1800098E7
0x1800098b8  test    esi, esi
0x1800098ba  jz      short loc_1800098E7
0x1800098bc  mov     rax, [rbx]
0x1800098bf  mov     edx, esi
0x1800098c1  mov     rcx, rbx
0x1800098c4  mov     rax, [rax+58h]
0x1800098c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098cd  test    eax, eax
0x1800098cf  jns     short loc_1800098E7
0x1800098d1  mov     r9d, 13Fh
0x1800098d7  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800098de  xor     edx, edx
0x1800098e0  mov     ecx, eax
0x1800098e2  call    Log_HREvent
0x1800098e7  lea     rsi, [rdi+130h]
0x1800098ee  mov     rcx, [rsi]; hEvent
0x1800098f1  test    rcx, rcx
0x1800098f4  jz      short loc_18000992C
0x1800098f6  call    cs:__imp_SetEvent
0x1800098fc  test    eax, eax
0x1800098fe  jnz     short loc_18000992C
0x180009900  call    cs:__imp_GetLastError
0x180009906  test    eax, eax
0x180009908  jle     short loc_180009914
0x18000990a  movzx   eax, ax
0x18000990d  or      eax, 80070000h
0x180009912  test    eax, eax
0x180009914  jns     short loc_18000992C
0x180009916  mov     r9d, 145h
0x18000991c  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009923  xor     edx, edx
0x180009925  mov     ecx, eax
0x180009927  call    Log_HREvent
0x18000992c  xor     r8d, r8d; pvCleanupContext
0x18000992f  lea     rbx, [rdi+218h]
0x180009936  mov     rcx, [rbx]; ptpcg
0x180009939  lea     edx, [r8+1]; fCancelPendingCallbacks
0x18000993d  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180009943  mov     [rdi+220h], rbp
0x18000994a  mov     rcx, rbx
0x18000994d  mov     [rdi+228h], ebp
0x180009953  mov     [rdi+230h], rbp
0x18000995a  mov     [rdi+238h], ebp
0x180009960  mov     [rdi+240h], rbp
0x180009967  mov     [rdi+248h], ebp
0x18000996d  mov     [rdi+250h], rbp
0x180009974  mov     [rdi+258h], ebp
0x18000997a  call    ?_Delete@?$auto_xxx@PEAU_TP_CLEANUP_GROUP@@P6AXPEAU1@@Z$1?CloseThreadpoolCleanupGroup@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_TP_CLEANUP_GROUP *,void (*)(_TP_CLEANUP_GROUP *),&CloseThreadpoolCleanupGroup(_TP_CLEANUP_GROUP *),0>::_Delete(void)
0x18000997f  mov     [rbx], rbp
0x180009982  lea     rbx, [rdi+200h]
0x180009989  mov     rcx, rbx
0x18000998c  call    ?_Delete@?$auto_xxx@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),0>::_Delete(void)
0x180009991  mov     [rbx], rbp
0x180009994  lea     rcx, [rdi+0F0h]; SRWLock
0x18000999b  mov     [rdi+260h], rbp
0x1800099a2  mov     [rsp+48h+arg_8], rcx
0x1800099a7  mov     [rdi+268h], ebp
0x1800099ad  call    cs:__imp_AcquireSRWLockExclusive
0x1800099b3  lea     rbx, [rdi+0F8h]
0x1800099ba  mov     rcx, rbx
0x1800099bd  call    ?_ClearList@?$_HashTable@KU?$pair@$$CBKUSyncPartnerData@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKUSyncPartnerData@@@utl@@@2@$0A@@utl@@AEAAXXZ; utl::_HashTable<ulong,utl::pair<ulong const,SyncPartnerData>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,SyncPartnerData>>,0>::_ClearList(void)
0x1800099c2  cmp     [rbx+10h], rbp
0x1800099c6  jz      short loc_1800099D0
0x1800099c8  mov     rcx, rbx
0x1800099cb  call    ?_InitBuckets@?$_HashTable@KU?$pair@$$CBKUSyncPartnerData@@@utl@@U?$hash@K@2@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKUSyncPartnerData@@@utl@@@2@$0A@@utl@@AEAAXXZ; utl::_HashTable<ulong,utl::pair<ulong const,SyncPartnerData>,utl::hash<ulong>,utl::equal_to<ulong>,utl::allocator<utl::pair<ulong const,SyncPartnerData>>,0>::_InitBuckets(void)
0x1800099d0  lea     rcx, [rsp+48h+arg_8]
0x1800099d5  call    ??1?$auto_SRWLockBase@U_RTL_SRWLOCK@@$1?AcquireSRWLockExclusive@@YAXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@Z@@QEAA@XZ; auto_SRWLockBase<_RTL_SRWLOCK,&AcquireSRWLockExclusive(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *)>::~auto_SRWLockBase<_RTL_SRWLOCK,&AcquireSRWLockExclusive(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *)>(void)
0x1800099da  mov     rcx, [rdi+0D8h]
0x1800099e1  test    rcx, rcx
0x1800099e4  jz      short loc_180009A0C
0x1800099e6  mov     rax, [rcx]
0x1800099e9  mov     rax, [rax+40h]
0x1800099ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099f2  test    eax, eax
0x1800099f4  jns     short loc_180009A0C
0x1800099f6  mov     r9d, 15Fh
0x1800099fc  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180009a03  xor     edx, edx
0x180009a05  mov     ecx, eax
0x180009a07  call    Log_HREvent
0x180009a0c  cmp     [rdi+0D8h], rbp
0x180009a13  jz      short loc_180009A23
0x180009a15  xor     edx, edx; struct IUnknown *
0x180009a17  lea     rcx, [rdi+0D8h]; struct IUnknown **
0x180009a1e  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180009a23  cmp     [r14], rbp
0x180009a26  jz      short loc_180009A32
0x180009a28  xor     edx, edx; struct IUnknown *
0x180009a2a  mov     rcx, r14; struct IUnknown **
0x180009a2d  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180009a32  mov     rcx, rsi
0x180009a35  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180009a3a  lea     rcx, [rsp+48h+arg_0]
0x180009a3f  mov     [rsi], rbp
0x180009a42  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180009a47  mov     rbx, [rsp+48h+arg_10]
0x180009a4c  xor     eax, eax
0x180009a4e  mov     rbp, [rsp+48h+arg_18]
0x180009a53  add     rsp, 30h
0x180009a57  pop     r14
0x180009a59  pop     rdi
0x180009a5a  pop     rsi
0x180009a5b  retn
```
