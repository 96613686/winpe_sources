# WnfEventHandlerForPushNotification(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x1800306b0`
- end: `0x1800307f8`
- name: `?WnfEventHandlerForPushNotification@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `328`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, __int64, struct _WNF_TYPE_ID *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18000d75c`
- `0x18002c4b8`
- `0x18002f684`
- `0x1800306b0`
- `0x180030e48`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030782`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030782`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030769`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030769`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x1800306c4`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x18003071b`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x1800306c4`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x18003071b`

## string_xrefs

- `0x1800306ec`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`

## pseudocode

```c
__int64 __fastcall WnfEventHandlerForPushNotification(
        struct _WNF_STATE_NAME a1,
        __int64 a2,
        struct _WNF_TYPE_ID *a3,
        void *a4)
{
  RTL_SRWLOCK *v4; // rbx
  _DWORD *v5; // rax
  __int64 v6; // rcx
  const char *v7; // r9
  volatile signed __int32 *v8; // rbx
  __int64 v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-28h] BYREF
  RTL_SRWLOCK *v12; // [rsp+38h] [rbp-20h]
  __int128 v13; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v11 = 0;
  GetProcessReference(&v11);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
    0x1A0u,
    "WnfEventHandlerForPushNotification",
    -1,
    L"Wnf for push notification received");
  try
  {
    v4 = (RTL_SRWLOCK *)operator new(0x10u);
    v4->Ptr = 0;
    LODWORD(v4[1].Ptr) = 1;
    GetProcessReference(v4);
    v13 = 0;
    v12 = v4;
    v5 = operator new(0x18u);
    v5[2] = 1;
    v5[3] = 1;
    *(_QWORD *)v5 = &std::_Ref_count<WorkItem>::`vftable';
    *((_QWORD *)v5 + 2) = v4;
    *(_QWORD *)&v13 = v4;
    *((_QWORD *)&v13 + 1) = v5;
    AcquireSRWLockExclusive(&srwWorkQueue);
    v12 = &srwWorkQueue;
    std::deque<std::shared_ptr<WorkItem>>::push_back(v6, &v13);
    ReleaseSRWLockExclusive(&srwWorkQueue);
    ProcessWorkQueue();
    v8 = (volatile signed __int32 *)*((_QWORD *)&v13 + 1);
    if ( *((_QWORD *)&v13 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v13 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1A8,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
      v7);
  }
  v9 = v11;
  if ( v11 )
  {
    v11 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return 0;
}

```

## disassembly

```asm
0x1800306b0  push    rbx
0x1800306b2  sub     rsp, 50h
0x1800306b6  mov     [rsp+58h+var_28], 0
0x1800306bf  lea     rcx, [rsp+58h+var_28]
0x1800306c4  call    cs:__imp_GetProcessReference
0x1800306ca  nop
0x1800306cb  lea     rax, aWnfForPushNoti; "Wnf for push notification received"
0x1800306d2  mov     [rsp+58h+var_30], rax; unsigned __int16 *
0x1800306d7  mov     [rsp+58h+var_38], 0FFFFFFFFh; int
0x1800306df  lea     r9, aWnfeventhandle; "WnfEventHandlerForPushNotification"
0x1800306e6  mov     r8d, 1A0h; unsigned int
0x1800306ec  lea     rdx, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x1800306f3  mov     ecx, 3; unsigned int
0x1800306f8  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x1800306fd  mov     ecx, 10h; Size
0x180030702  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030707  mov     rbx, rax
0x18003070a  mov     qword ptr [rax], 0
0x180030711  mov     dword ptr [rax+8], 1
0x180030718  mov     rcx, rax
0x18003071b  call    cs:__imp_GetProcessReference
0x180030721  xorps   xmm0, xmm0
0x180030724  movdqu  [rsp+58h+var_18], xmm0
0x18003072a  mov     [rsp+58h+var_20], rbx
0x18003072f  mov     ecx, 18h; Size
0x180030734  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030739  mov     dword ptr [rax+8], 1
0x180030740  mov     dword ptr [rax+0Ch], 1
0x180030747  lea     rcx, ??_7?$_Ref_count@VWorkItem@@@std@@6B@; const std::_Ref_count<WorkItem>::`vftable'
0x18003074e  mov     [rax], rcx
0x180030751  mov     [rax+10h], rbx
0x180030755  mov     qword ptr [rsp+58h+var_18], rbx
0x18003075a  mov     qword ptr [rsp+58h+var_18+8], rax
0x18003075f  lea     rbx, ?srwWorkQueue@@3VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock srwWorkQueue
0x180030766  mov     rcx, rbx; SRWLock
0x180030769  call    cs:__imp_AcquireSRWLockExclusive
0x18003076f  mov     [rsp+58h+var_20], rbx
0x180030774  lea     rdx, [rsp+58h+var_18]
0x180030779  call    ?push_back@?$deque@V?$shared_ptr@VWorkItem@@@std@@V?$allocator@V?$shared_ptr@VWorkItem@@@std@@@2@@std@@QEAAXAEBV?$shared_ptr@VWorkItem@@@2@@Z; std::deque<std::shared_ptr<WorkItem>>::push_back(std::shared_ptr<WorkItem> const &)
0x18003077e  nop
0x18003077f  mov     rcx, rbx; SRWLock
0x180030782  call    cs:__imp_ReleaseSRWLockExclusive
0x180030788  call    ?ProcessWorkQueue@@YAXXZ; ProcessWorkQueue(void)
0x18003078d  nop
0x18003078e  mov     rbx, qword ptr [rsp+58h+var_18+8]
0x180030793  test    rbx, rbx
0x180030796  jz      short loc_1800307D0
0x180030798  or      eax, 0FFFFFFFFh
0x18003079b  lock xadd [rbx+8], eax
0x1800307a0  cmp     eax, 1
0x1800307a3  jnz     short loc_1800307D0
0x1800307a5  mov     rax, [rbx]
0x1800307a8  mov     rcx, rbx
0x1800307ab  mov     rax, [rax]
0x1800307ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307b3  or      eax, 0FFFFFFFFh
0x1800307b6  lock xadd [rbx+0Ch], eax
0x1800307bb  cmp     eax, 1
0x1800307be  jnz     short loc_1800307D0
0x1800307c0  mov     rax, [rbx]
0x1800307c3  mov     rcx, rbx
0x1800307c6  mov     rax, [rax+8]
0x1800307ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307cf  nop
0x1800307d0  mov     rcx, [rsp+58h+var_28]
0x1800307d5  test    rcx, rcx
0x1800307d8  jz      short loc_1800307F0
0x1800307da  mov     [rsp+58h+var_28], 0
0x1800307e3  mov     rax, [rcx]
0x1800307e6  mov     rax, [rax+10h]
0x1800307ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307ef  nop
0x1800307f0  xor     eax, eax
0x1800307f2  add     rsp, 50h
0x1800307f6  pop     rbx
0x1800307f7  retn
```
