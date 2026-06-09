# BaseCentralEventAggregateCallbackWorker(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180005e40`
- end: `0x180006371`
- name: `?BaseCentralEventAggregateCallbackWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `1329`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x180005b10`
- `0x180005c30`
- `0x180005e40`
- `0x18000ea40`
- `0x18000eef0`
- `0x18000f760`
- `0x18000f7cc`
- `0x18001f65c`
- `0x18001f87c`
- `0x18001fbac`
- `0x18001fbe0`
- `0x180020bf6`
- `0x180020c30`
- `0x180022010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006043`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006043`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006366`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006366`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000635b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000635b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000618a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000618a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180006352`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180006352`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005eb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005ed4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006161`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005eb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005ed4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006161`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005fed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800061a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800061b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005f1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005fed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800061a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800061b5`

## pseudocode

```c
void __fastcall BaseCentralEventAggregateCallbackWorker(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context, PTP_WORK Work)
{
  __int64 v4; // rbx
  __int64 *v5; // rdi
  __int64 v6; // r12
  __int64 v7; // r13
  int v8; // r15d
  void **i; // rsi
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r8
  _QWORD *v13; // rcx
  bool v14; // zf
  __int128 v15; // xmm0
  int v16; // eax
  int v17; // ebx
  void *v18; // rcx
  void (__fastcall ***v19)(_QWORD, __int128 *); // rcx
  _QWORD *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  struct CSchedule *j; // rdx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v25; // rbx
  struct _RTL_CRITICAL_SECTION *v26; // rcx
  __int64 v27; // rax
  _QWORD *v28; // rax
  __int64 v29; // rcx
  struct CSchedule *v30; // rax
  _QWORD v31[2]; // [rsp+48h] [rbp-C0h] BYREF
  void **Buf2; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v34; // [rsp+90h] [rbp-78h] BYREF
  __int64 v35; // [rsp+A0h] [rbp-68h]
  __int64 v36; // [rsp+A8h] [rbp-60h]
  int v37; // [rsp+B0h] [rbp-58h]
  int v38; // [rsp+B4h] [rbp-54h]
  int v39; // [rsp+B8h] [rbp-50h]
  struct _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v41; // [rsp+178h] [rbp+70h]
  __int64 v42; // [rsp+188h] [rbp+80h]
  __int64 v43; // [rsp+190h] [rbp+88h]
  int v44; // [rsp+198h] [rbp+90h]
  int v45; // [rsp+19Ch] [rbp+94h]
  __int128 v46; // [rsp+1A8h] [rbp+A0h]
  __int64 v47; // [rsp+1B8h] [rbp+B0h]
  __int64 v48; // [rsp+1C0h] [rbp+B8h]
  int v49; // [rsp+1C8h] [rbp+C0h]
  int v50; // [rsp+1CCh] [rbp+C4h]
  _QWORD Buf1[2]; // [rsp+1D8h] [rbp+D0h] BYREF

  if ( Context )
  {
    v4 = Context[2];
    v5 = (__int64 *)*Context;
    v6 = Context[3];
    v7 = Context[1];
    v8 = *((_DWORD *)Context + 8);
    v31[1] = v31;
    v31[0] = v31;
    EnterCriticalSection(&CriticalSection);
    Buf1[0] = v5;
    if ( !v5 )
    {
LABEL_39:
      v26 = &CriticalSection;
      goto LABEL_37;
    }
    EnterCriticalSection(&CriticalSection);
    for ( i = (void **)g_ScheduleMgr; ; i = (void **)*i )
    {
      if ( i == (void **)&g_ScheduleMgr )
      {
        LeaveCriticalSection(&CriticalSection);
        goto LABEL_39;
      }
      Buf2 = i;
      if ( !memcmp_0(Buf1, &Buf2, 8u) )
        break;
    }
    LeaveCriticalSection(&CriticalSection);
    if ( (byte_180030D06 & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(v10, BrokerFrameworkCentralEventProcessingStart, v11, 1, Buf1);
    TimeInfo::TimeInfo(&TimeZoneInformation);
    TimeInfo::LogTimeETW((TimeInfo *)&TimeZoneInformation);
    v13 = (_QWORD *)v5[25];
    if ( v13 && v5[27] )
    {
      v14 = (*((_BYTE *)v5 + 44) & 8) == 0;
      v39 = 1;
      if ( v14 )
      {
        v15 = v41;
        v35 = v42;
        v36 = v43;
        v37 = v44;
        v16 = v45;
      }
      else
      {
        v15 = v46;
        v35 = v47;
        v36 = v48;
        v37 = v49;
        v16 = v50;
      }
      v38 = v16;
      v34 = v15;
      v17 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *, __int64, __int64, __int64, int))(*v13 + 120LL))(
              v13,
              &v34,
              v7,
              v4,
              v6,
              v8);
      if ( (*((_BYTE *)v5 + 44) & 2) == 0 )
      {
        if ( *((_DWORD *)v5 + 66) )
          goto LABEL_30;
        v13 = v5 + 12;
        if ( !*((_DWORD *)v5 + 34) || (v27 = TimeValue::AtLimitTime(v13, &v33), (unsigned int)operator<=(&v34, v27)) )
        {
          if ( (!*((_DWORD *)v5 + 22) || (unsigned int)operator>=(&v34, v5 + 6)) && *((_DWORD *)v5 + 10) == 4 && v17 )
          {
            v19 = (void (__fastcall ***)(_QWORD, __int128 *))v5[27];
            ++*((_DWORD *)v5 + 36);
            (**v19)(v19, &v34);
            (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v5[25] + 72LL))(v5[25], &v34);
            (*(void (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v5[25] + 96LL))(v5[25], &v34, 1);
            if ( (*((_BYTE *)v5 + 44) & 1) != 0 )
            {
              TaskStore::PersistStatistics(qword_180030AC8, (const struct _GUID *)v5 + 1);
              TaskStore::PersistRuntimeData(qword_180030AC8, (const struct _GUID *)v5 + 1, 1);
            }
            if ( *((_DWORD *)v5 + 66) )
              goto LABEL_30;
            CSchedule::UpdateState((CSchedule *)v5, (const struct TimeInfo *)&TimeZoneInformation);
          }
        }
      }
    }
    else if ( (byte_180030D04 & 1) != 0 )
    {
      McGenEventWrite_EventWriteTransfer(v13, ErrorNullPointer, v12, 1, Buf1);
    }
    if ( !*((_DWORD *)v5 + 66) )
    {
LABEL_14:
      if ( (byte_180030D06 & 4) != 0 )
        McGenEventWrite_EventWriteTransfer(v13, BrokerFrameworkCentralEventProcessingCompleted, v12, 1, Buf1);
      LeaveCriticalSection(&CriticalSection);
      if ( (_QWORD *)v31[0] == v31 )
        goto LABEL_17;
      EnterCriticalSection(&CScheduleMgr::CritLockExpired);
      for ( j = (struct CSchedule *)v31[0]; (_QWORD *)v31[0] != v31; j = (struct CSchedule *)v31[0] )
      {
        v28 = (_QWORD *)*((_QWORD *)j + 1);
        v29 = *(_QWORD *)j;
        *v28 = *(_QWORD *)j;
        *(_QWORD *)(v29 + 8) = v28;
        v30 = CScheduleMgr::ExpiredScheduleList;
        *(_QWORD *)j = CScheduleMgr::ExpiredScheduleList;
        *((_QWORD *)j + 1) = &CScheduleMgr::ExpiredScheduleList;
        *((_QWORD *)v30 + 1) = j;
        CScheduleMgr::ExpiredScheduleList = j;
      }
      ThreadpoolWork = CreateThreadpoolWork(CScheduleMgr::DeleteExpiredWorker, 0, &ThreadpoolCallBackEnvironment);
      v25 = ThreadpoolWork;
      if ( ThreadpoolWork )
      {
        SubmitThreadpoolWork(ThreadpoolWork);
        CloseThreadpoolWork(v25);
      }
      v26 = &CScheduleMgr::CritLockExpired;
LABEL_37:
      LeaveCriticalSection(v26);
LABEL_17:
      v18 = (void *)Context[3];
      if ( v18 )
        operator delete[](v18);
      operator delete(Context);
      return;
    }
LABEL_30:
    if ( (*((_BYTE *)v5 + 44) & 4) != 0 )
    {
      v20 = (_QWORD *)v5[1];
      v21 = *v5;
      *v20 = *v5;
      *(_QWORD *)(v21 + 8) = v20;
      v13 = v31;
      v22 = v31[0];
      *v5 = v31[0];
      v5[1] = (__int64)v31;
      *(_QWORD *)(v22 + 8) = v5;
      v14 = (*((_BYTE *)v5 + 44) & 1) == 0;
      v31[0] = v5;
      if ( !v14 )
        TaskStore::Delete((TaskStore *)v31, (const struct _GUID *)v5 + 1);
    }
    goto LABEL_14;
  }
  if ( (byte_180030D04 & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(Instance, ErrorNullPointer, Work, 1, Buf1);
}

```

## disassembly

```asm
0x180005e40  mov     r11, rsp
0x180005e43  push    rbp
0x180005e44  push    r14
0x180005e46  lea     rbp, [r11-118h]
0x180005e4d  sub     rsp, 208h
0x180005e54  mov     rax, cs:__security_cookie
0x180005e5b  xor     rax, rsp
0x180005e5e  mov     [rbp+110h+var_30], rax
0x180005e65  mov     r14, rdx
0x180005e68  test    rdx, rdx
0x180005e6b  jz      loc_1800061C4
0x180005e71  mov     [r11+8], rbx
0x180005e75  lea     rax, [rsp+210h+var_1D0]
0x180005e7a  mov     rbx, [rdx+10h]
0x180005e7e  lea     rcx, CriticalSection; lpCriticalSection
0x180005e85  mov     [r11+20h], rdi
0x180005e89  mov     rdi, [rdx]
0x180005e8c  mov     [r11-18h], r12
0x180005e90  mov     r12, [rdx+18h]
0x180005e94  mov     [r11-20h], r13
0x180005e98  mov     r13, [rdx+8]
0x180005e9c  mov     [r11-28h], r15
0x180005ea0  mov     r15d, [rdx+20h]
0x180005ea4  mov     [rsp+210h+var_1C8], rax
0x180005ea9  lea     rax, [rsp+210h+var_1D0]
0x180005eae  mov     [r11+18h], rsi
0x180005eb2  mov     [rsp+210h+var_1D0], rax
0x180005eb7  call    cs:__imp_EnterCriticalSection
0x180005ebd  mov     [rbp+110h+Buf1], rdi
0x180005ec4  test    rdi, rdi
0x180005ec7  jz      loc_1800061BB
0x180005ecd  lea     rcx, CriticalSection; lpCriticalSection
0x180005ed4  call    cs:__imp_EnterCriticalSection
0x180005eda  mov     rsi, cs:?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x180005ee1  lea     rax, ?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x180005ee8  cmp     rsi, rax
0x180005eeb  jz      loc_1800061AE
0x180005ef1  mov     r8d, 8; Size
0x180005ef7  mov     [rsp+210h+Buf2], rsi
0x180005efc  lea     rdx, [rsp+210h+Buf2]; Buf2
0x180005f01  lea     rcx, [rbp+110h+Buf1]; Buf1
0x180005f08  call    memcmp_0
0x180005f0d  test    eax, eax
0x180005f0f  jnz     loc_180006063
0x180005f15  lea     rcx, CriticalSection; lpCriticalSection
0x180005f1c  call    cs:__imp_LeaveCriticalSection
0x180005f22  test    cs:byte_180030D06, 4
0x180005f29  jnz     loc_1800061F4
0x180005f2f  lea     rcx, [rbp+110h+TimeZoneInformation]; lpTimeZoneInformation
0x180005f33  call    ??0TimeInfo@@QEAA@XZ; TimeInfo::TimeInfo(void)
0x180005f38  lea     rcx, [rbp+110h+TimeZoneInformation]; this
0x180005f3c  call    ?LogTimeETW@TimeInfo@@QEBAXXZ; TimeInfo::LogTimeETW(void)
0x180005f41  mov     rcx, [rdi+0C8h]
0x180005f48  test    rcx, rcx
0x180005f4b  jz      loc_1800062BA
0x180005f51  cmp     qword ptr [rdi+0D8h], 0
0x180005f59  jz      loc_1800062BA
0x180005f5f  test    byte ptr [rdi+2Ch], 8
0x180005f63  mov     [rbp+110h+var_160], 1
0x180005f6a  jnz     loc_180006217
0x180005f70  mov     rax, [rbp+110h+var_90]
0x180005f77  movaps  xmm0, [rbp+110h+var_A0]
0x180005f7b  mov     [rbp+110h+var_178], rax
0x180005f7f  mov     rax, [rbp+110h+var_88]
0x180005f86  mov     [rbp+110h+var_170], rax
0x180005f8a  mov     eax, [rbp+110h+var_80]
0x180005f90  mov     [rbp+110h+var_168], eax
0x180005f93  mov     eax, [rbp+110h+var_7C]
0x180005f99  mov     [rbp+110h+var_164], eax
0x180005f9c  lea     rdx, [rbp+110h+var_188]
0x180005fa0  movups  [rbp+110h+var_188], xmm0
0x180005fa4  mov     rax, [rcx]
0x180005fa7  mov     r9, rbx
0x180005faa  mov     [rsp+28h], r15d
0x180005faf  mov     r8, r13
0x180005fb2  mov     qword ptr [rsp+210h+var_1F0], r12
0x180005fb7  mov     rax, [rax+78h]
0x180005fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fc0  test    byte ptr [rdi+2Ch], 2
0x180005fc4  mov     ebx, eax
0x180005fc6  jz      loc_18000606B
0x180005fcc  cmp     dword ptr [rdi+108h], 0
0x180005fd3  jnz     loc_180006110
0x180005fd9  test    cs:byte_180030D06, 4
0x180005fe0  jnz     loc_1800062EA
0x180005fe6  lea     rcx, CriticalSection; lpCriticalSection
0x180005fed  call    cs:__imp_LeaveCriticalSection
0x180005ff3  lea     rax, [rsp+210h+var_1D0]
0x180005ff8  cmp     [rsp+210h+var_1D0], rax
0x180005ffd  jnz     loc_18000615A
0x180006003  mov     rcx, [r14+18h]
0x180006007  mov     r15, [rsp+210h+var_20]
0x18000600f  mov     r13, [rsp+210h+var_18]
0x180006017  mov     r12, [rsp+200h]
0x18000601f  mov     rdi, [rsp+210h+arg_18]
0x180006027  mov     rsi, [rsp+210h+arg_10]
0x18000602f  mov     rbx, [rsp+210h+arg_0]
0x180006037  test    rcx, rcx
0x18000603a  jnz     loc_180006366
0x180006040  mov     rcx, r14
0x180006043  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006049  mov     rcx, [rbp+110h+var_30]
0x180006050  xor     rcx, rsp; StackCookie
0x180006053  call    __security_check_cookie
0x180006058  add     rsp, 208h
0x18000605f  pop     r14
0x180006061  pop     rbp
0x180006062  retn
0x180006063  mov     rsi, [rsi]
0x180006066  jmp     loc_180005EE1
0x18000606b  cmp     dword ptr [rdi+108h], 0
0x180006072  jnz     loc_180006110
0x180006078  lea     rcx, [rdi+60h]
0x18000607c  cmp     dword ptr [rcx+28h], 0
0x180006080  jnz     loc_180006248
0x180006086  cmp     dword ptr [rdi+58h], 0
0x18000608a  lea     rdx, [rdi+30h]
0x18000608e  jnz     loc_18000626B
0x180006094  cmp     dword ptr [rdi+28h], 4
0x180006098  jnz     loc_180005FCC
0x18000609e  test    ebx, ebx
0x1800060a0  jz      loc_180005FCC
0x1800060a6  mov     rcx, [rdi+0D8h]
0x1800060ad  lea     rdx, [rbp+110h+var_188]
0x1800060b1  inc     dword ptr [rdi+90h]
0x1800060b7  mov     rax, [rcx]
0x1800060ba  mov     rax, [rax]
0x1800060bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060c2  mov     rcx, [rdi+0C8h]
0x1800060c9  lea     rdx, [rbp+110h+var_188]
0x1800060cd  mov     rax, [rcx]
0x1800060d0  mov     rax, [rax+48h]
0x1800060d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060d9  mov     rcx, [rdi+0C8h]
0x1800060e0  lea     rdx, [rbp+110h+var_188]
0x1800060e4  mov     r9d, 1
0x1800060ea  mov     r8d, r9d
0x1800060ed  mov     rax, [rcx]
0x1800060f0  mov     rax, [rax+60h]
0x1800060f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060f9  test    byte ptr [rdi+2Ch], 1
0x1800060fd  jnz     loc_180006281
0x180006103  cmp     dword ptr [rdi+108h], 0
0x18000610a  jz      loc_1800062A9
0x180006110  test    byte ptr [rdi+2Ch], 4
0x180006114  jz      loc_180005FD9
0x18000611a  mov     rax, [rdi+8]
0x18000611e  mov     rcx, [rdi]
0x180006121  mov     [rax], rcx
0x180006124  mov     [rcx+8], rax
0x180006128  lea     rcx, [rsp+210h+var_1D0]; this
0x18000612d  mov     rax, [rsp+210h+var_1D0]
0x180006132  mov     [rdi], rax
0x180006135  mov     [rdi+8], rcx
0x180006139  mov     [rax+8], rdi
0x18000613d  test    byte ptr [rdi+2Ch], 1
0x180006141  mov     [rsp+210h+var_1D0], rdi
0x180006146  jz      loc_180005FD9
0x18000614c  lea     rdx, [rdi+10h]; struct _GUID *
0x180006150  call    ?Delete@TaskStore@@QEAAJAEBU_GUID@@@Z; TaskStore::Delete(_GUID const &)
0x180006155  jmp     loc_180005FD9
0x18000615a  lea     rcx, ?CritLockExpired@CScheduleMgr@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180006161  call    cs:__imp_EnterCriticalSection
0x180006167  mov     rdx, [rsp+210h+var_1D0]
0x18000616c  lea     rax, [rsp+210h+var_1D0]
0x180006171  cmp     rdx, rax
0x180006174  jnz     loc_18000630D
0x18000617a  lea     r8, ?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x180006181  xor     edx, edx; pv
0x180006183  lea     rcx, ?DeleteExpiredWorker@CScheduleMgr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000618a  call    cs:__imp_CreateThreadpoolWork
0x180006190  mov     rbx, rax
0x180006193  test    rax, rax
0x180006196  jnz     loc_18000634F
0x18000619c  lea     rcx, ?CritLockExpired@CScheduleMgr@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800061a3  call    cs:__imp_LeaveCriticalSection
0x1800061a9  jmp     loc_180006003
0x1800061ae  lea     rcx, CriticalSection; lpCriticalSection
0x1800061b5  call    cs:__imp_LeaveCriticalSection
0x1800061bb  lea     rcx, CriticalSection
0x1800061c2  jmp     short loc_1800061A3
0x1800061c4  test    cs:byte_180030D04, 1
0x1800061cb  jz      loc_180006049
0x1800061d1  lea     rax, [rbp+110h+Buf1]
0x1800061d8  mov     r9d, 1
0x1800061de  lea     rdx, ErrorNullPointer
0x1800061e5  mov     qword ptr [rsp+210h+var_1F0], rax
0x1800061ea  call    McGenEventWrite_EventWriteTransfer
0x1800061ef  jmp     loc_180006049
0x1800061f4  lea     rax, [rbp+110h+Buf1]
0x1800061fb  mov     r9d, 1
0x180006201  lea     rdx, BrokerFrameworkCentralEventProcessingStart
0x180006208  mov     qword ptr [rsp+210h+var_1F0], rax
0x18000620d  call    McGenEventWrite_EventWriteTransfer
0x180006212  jmp     loc_180005F2F
0x180006217  mov     rax, [rbp+110h+var_60]
0x18000621e  movaps  xmm0, [rbp+110h+var_70]
0x180006225  mov     [rbp+110h+var_178], rax
0x180006229  mov     rax, [rbp+110h+var_58]
0x180006230  mov     [rbp+110h+var_170], rax
0x180006234  mov     eax, [rbp+110h+var_50]
0x18000623a  mov     [rbp+110h+var_168], eax
0x18000623d  mov     eax, [rbp+110h+var_4C]
0x180006243  jmp     loc_180005F99
0x180006248  lea     rdx, [rsp+58h]
0x18000624d  call    ?AtLimitTime@TimeValue@@QEBA?AV1@XZ; TimeValue::AtLimitTime(void)
0x180006252  mov     rdx, rax
0x180006255  lea     rcx, [rbp+110h+var_188]
0x180006259  call    ??N@YAHAEBVTimeValue@@0@Z; operator<=(TimeValue const &,TimeValue const &)
0x18000625e  test    eax, eax
0x180006260  jz      loc_180005FCC
0x180006266  jmp     loc_180006086
0x18000626b  lea     rcx, [rbp+110h+var_188]
0x18000626f  call    ??P@YAHAEBVTimeValue@@0@Z; operator>=(TimeValue const &,TimeValue const &)
0x180006274  test    eax, eax
0x180006276  jz      loc_180005FCC
0x18000627c  jmp     loc_180006094
0x180006281  mov     rcx, cs:qword_180030AC8; this
0x180006288  lea     rdx, [rdi+10h]; struct _GUID *
0x18000628c  call    ?PersistStatistics@TaskStore@@QEAAJAEBU_GUID@@@Z; TaskStore::PersistStatistics(_GUID const &)
0x180006291  mov     rcx, cs:qword_180030AC8; this
0x180006298  lea     rdx, [rdi+10h]; struct _GUID *
0x18000629c  mov     r8b, 1; bool
0x18000629f  call    ?PersistRuntimeData@TaskStore@@QEAAJAEBU_GUID@@_N@Z; TaskStore::PersistRuntimeData(_GUID const &,bool)
0x1800062a4  jmp     loc_180006103
0x1800062a9  lea     rdx, [rbp+110h+TimeZoneInformation]; struct TimeInfo *
0x1800062ad  mov     rcx, rdi; this
0x1800062b0  call    ?UpdateState@CSchedule@@AEAAXAEBVTimeInfo@@@Z; CSchedule::UpdateState(TimeInfo const &)
0x1800062b5  jmp     loc_180005FCC
0x1800062ba  test    cs:byte_180030D04, 1
0x1800062c1  jz      loc_180005FCC
0x1800062c7  lea     rax, [rbp+110h+Buf1]
0x1800062ce  mov     r9d, 1
0x1800062d4  lea     rdx, ErrorNullPointer
0x1800062db  mov     qword ptr [rsp+210h+var_1F0], rax
0x1800062e0  call    McGenEventWrite_EventWriteTransfer
0x1800062e5  jmp     loc_180005FCC
0x1800062ea  lea     rax, [rbp+110h+Buf1]
0x1800062f1  mov     r9d, 1
0x1800062f7  lea     rdx, BrokerFrameworkCentralEventProcessingCompleted
0x1800062fe  mov     qword ptr [rsp+210h+var_1F0], rax
0x180006303  call    McGenEventWrite_EventWriteTransfer
0x180006308  jmp     loc_180005FE6
0x18000630d  lea     r8, ?ExpiredScheduleList@CScheduleMgr@@0U_LIST_ENTRY@@A; _LIST_ENTRY CScheduleMgr::ExpiredScheduleList
0x180006314  mov     rax, [rdx+8]
0x180006318  mov     rcx, [rdx]
0x18000631b  mov     [rax], rcx
0x18000631e  mov     [rcx+8], rax
0x180006322  mov     rax, cs:?ExpiredScheduleList@CScheduleMgr@@0U_LIST_ENTRY@@A; _LIST_ENTRY CScheduleMgr::ExpiredScheduleList
0x180006329  mov     [rdx], rax
0x18000632c  mov     [rdx+8], r8
0x180006330  mov     [rax+8], rdx
0x180006334  lea     rax, [rsp+210h+var_1D0]
0x180006339  mov     cs:?ExpiredScheduleList@CScheduleMgr@@0U_LIST_ENTRY@@A, rdx; _LIST_ENTRY CScheduleMgr::ExpiredScheduleList
0x180006340  mov     rdx, [rsp+210h+var_1D0]
0x180006345  cmp     rdx, rax
0x180006348  jnz     short loc_180006314
0x18000634a  jmp     loc_18000617A
0x18000634f  mov     rcx, rbx; pwk
0x180006352  call    cs:__imp_SubmitThreadpoolWork
0x180006358  mov     rcx, rbx; pwk
0x18000635b  call    cs:__imp_CloseThreadpoolWork
0x180006361  jmp     loc_18000619C
0x180006366  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000636c  jmp     loc_180006040
```
