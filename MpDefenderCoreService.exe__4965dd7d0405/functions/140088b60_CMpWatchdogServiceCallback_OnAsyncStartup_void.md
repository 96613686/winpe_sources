# CMpWatchdogServiceCallback::OnAsyncStartup(void)

- ea: `0x140088b60`
- end: `0x1400894a9`
- name: `?OnAsyncStartup@CMpWatchdogServiceCallback@@UEAAXXZ`
- size: `2377`
- prototype: `void __fastcall(CMpWatchdogServiceCallback *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1400010ac`
- `0x140001374`
- `0x140013394`
- `0x1400177d4`
- `0x1400177dc`
- `0x14007d1e0`
- `0x14007d210`
- `0x14007d774`
- `0x140081fc8`
- `0x1400833d4`
- `0x140085d94`
- `0x140088b60`
- `0x14008a040`
- `0x14008aac8`
- `0x14008d0a0`
- `0x140095200`
- `0x140166250`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x140088b91`
- `KERNEL32!DebugBreak` at `0x140088b91`
- `KERNEL32!DeleteTimerQueueTimer` at `0x140088c5c`
- `KERNEL32!DeleteTimerQueueTimer` at `0x140088c5c`

## string_xrefs

- `0x140088bc5`: `ReinforceDefenderCoreServiceAcls`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
void __fastcall CMpWatchdogServiceCallback::OnAsyncStartup(
        CMpWatchdogServiceCallback *this,
        __int64 a2,
        unsigned int a3)
{
  int v3; // eax
  int v4; // ebx
  signed __int32 v5; // eax
  MpWatchDog *v6; // rcx
  signed __int32 v7; // ett
  unsigned int v8; // ebx
  int TimerQueueTimer; // eax
  __int64 v10; // rcx
  unsigned __int64 i; // r14
  __int64 v12; // rdi
  __int64 (*v13)(void); // rax
  __int64 v14; // rcx
  struct _RTL_CRITICAL_SECTION *v15; // r13
  struct _RTL_CRITICAL_SECTION *v16; // r13
  signed __int32 v17; // eax
  signed __int32 v18; // ett
  struct _RTL_CRITICAL_SECTION *v19; // r13
  int v20; // eax
  int v21; // [rsp+20h] [rbp-198h]
  void *v22; // [rsp+28h] [rbp-190h]
  unsigned int v23; // [rsp+30h] [rbp-188h]
  __int64 v24; // [rsp+B0h] [rbp-108h] BYREF
  __int64 v25; // [rsp+B8h] [rbp-100h] BYREF
  __int64 v26; // [rsp+C0h] [rbp-F8h] BYREF
  int v27; // [rsp+C8h] [rbp-F0h] BYREF
  int v28; // [rsp+CCh] [rbp-ECh] BYREF
  int v29; // [rsp+D0h] [rbp-E8h] BYREF
  int v30; // [rsp+D4h] [rbp-E4h] BYREF
  int v31; // [rsp+D8h] [rbp-E0h] BYREF
  int v32; // [rsp+DCh] [rbp-DCh] BYREF
  int v33; // [rsp+E0h] [rbp-D8h] BYREF
  int v34; // [rsp+E4h] [rbp-D4h] BYREF
  int v35; // [rsp+E8h] [rbp-D0h] BYREF
  int v36; // [rsp+ECh] [rbp-CCh] BYREF
  __int64 v37; // [rsp+F0h] [rbp-C8h] BYREF
  __int64 v38; // [rsp+F8h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+100h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+108h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+110h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+118h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+120h] [rbp-98h] BYREF
  __int64 v44; // [rsp+128h] [rbp-90h] BYREF
  __int64 v45; // [rsp+130h] [rbp-88h] BYREF
  __int64 v46; // [rsp+138h] [rbp-80h] BYREF
  __int64 v47; // [rsp+140h] [rbp-78h] BYREF
  __int64 v48; // [rsp+148h] [rbp-70h] BYREF
  __int64 v49; // [rsp+150h] [rbp-68h] BYREF
  __int64 v50; // [rsp+158h] [rbp-60h] BYREF
  __int64 v51[11]; // [rsp+160h] [rbp-58h] BYREF
  int v52; // [rsp+1C8h] [rbp+10h] BYREF
  __int64 v53; // [rsp+1D0h] [rbp+18h] BYREF
  __int64 v54; // [rsp+1D8h] [rbp+20h] BYREF

  LODWORD(v53) = -1;
  if ( MpWatchDog::GetMiscConfigDword((HKEY)&stru_1401952C8, 0, a3) == 1 )
    DebugBreak();
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 61, &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids);
  v26 = (__int64)L"ReinforceDefenderCoreServiceAcls";
  v3 = ReinforceDefenderCoreServiceAcls();
  v4 = v3;
  if ( v3 >= 0 )
  {
    _m_prefetchw(&dword_1401E72E8);
    v5 = (int)dword_1401E72E8;
    do
    {
      v6 = (MpWatchDog *)(unsigned int)v5;
      v7 = v5;
      v5 = _InterlockedCompareExchange((volatile signed __int32 *)&dword_1401E72E8, v5, v5);
    }
    while ( v7 != v5 );
    if ( v5 > 0 )
    {
LABEL_67:
      v10 = WPP_GLOBAL_Control;
LABEL_68:
      if ( (_UNKNOWN *)v10 != &WPP_GLOBAL_Control && (*(_BYTE *)(v10 + 28) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(v10 + 16), 69, &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids);
      v20 = MpWatchDog::WdTracingFlushTraceSession((MpWatchDog *)v10);
      if ( v20 < 0
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          70,
          &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
          (unsigned int)v20);
      }
      FlushUpdateLoggingTraceSession();
      return;
    }
    v8 = MpWatchDog::MpIsCoreSvcInDevMode(v6) == 0 ? 0xEA60 : 0;
    if ( gs_ServiceConfigureTimer )
    {
      DeleteTimerQueueTimer(0, gs_ServiceConfigureTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      gs_ServiceConfigureTimer = 0;
    }
    LODWORD(v22) = 0;
    TimerQueueTimer = CommonUtil::UtilCreateTimerQueueTimer(
                        (CommonUtil *)&gs_ServiceConfigureTimer,
                        (void **)v8,
                        0,
                        (unsigned int)ConfigureServiceTimerCallback,
                        0,
                        v22,
                        v23);
    if ( TimerQueueTimer < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      {
LABEL_21:
        v26 = (__int64)L"InitializingModules";
        for ( i = 0; ; ++i )
        {
          v24 = i;
          if ( i >= 0xA )
            break;
          LODWORD(v54) = i;
          LODWORD(v53) = i;
          v12 = 4 * i;
          v25 = 32 * i;
          v13 = (__int64 (*)(void))*(&off_1401D90D0 + 4 * i + 1);
          if ( v13 )
            v4 = v13();
          else
            v4 = 0;
          v52 = v4;
          v14 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          {
            WPP_SF_PdSd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v21, (__int64)(&off_1401D90D0)[v12], v4);
            v14 = WPP_GLOBAL_Control;
          }
          *((_BYTE *)&off_1401D90D0 + 8 * v12 + 25) = v4 >= 0;
          if ( v4 < 0 )
          {
            if ( (_UNKNOWN *)v14 != &WPP_GLOBAL_Control && (*(_BYTE *)(v14 + 28) & 1) != 0 )
              WPP_SF_PdSd(*(_QWORD *)(v14 + 16), v21, (__int64)(&off_1401D90D0)[v12], v4);
            v15 = g_pcsAsimovLock;
            if ( g_pcsAsimovLock )
            {
              Mtxlock(g_pcsAsimovLock);
              if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
                && (*(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider + 16LL) & 0x400000000000LL) != 0
                && (*(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider + 24LL) & 0x400000000000LL) == *(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider + 24LL) )
              {
                v27 = v4;
                v28 = v54;
                v54 = (__int64)(&off_1401D90D0)[v12];
                v29 = *((_DWORD *)g_aAsimov + 18);
                v30 = *((_DWORD *)g_aAsimov + 17);
                v31 = *((_DWORD *)g_aAsimov + 16);
                v32 = *((unsigned __int8 *)g_aAsimov + 60);
                v33 = *((unsigned __int8 *)g_aAsimov + 59);
                v34 = *((unsigned __int8 *)g_aAsimov + 58);
                v35 = *((unsigned __int8 *)g_aAsimov + 57);
                v36 = *((unsigned __int8 *)g_aAsimov + 56);
                v41 = *((_QWORD *)g_aAsimov + 6);
                v40 = *((_QWORD *)g_aAsimov + 5);
                v39 = *((_QWORD *)g_aAsimov + 4);
                v38 = *((_QWORD *)g_aAsimov + 3);
                v42 = *((_QWORD *)g_aAsimov + 2);
                v43 = *((_QWORD *)g_aAsimov + 1);
                v44 = 0x2000000;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  g_hMpAsimovProvider,
                  (int)&byte_1401B910D,
                  (__int64)&v44,
                  (__int64)&v43,
                  (__int64)&v42,
                  (__int64)&v38,
                  (__int64)&v39,
                  (__int64)&v40,
                  (__int64)&v41,
                  (__int64)&v36,
                  (__int64)&v35,
                  (__int64)&v34,
                  (__int64)&v33,
                  (__int64)&v32,
                  (__int64)&v31,
                  (__int64)&v30,
                  (__int64)&v29,
                  (__int64)&v54,
                  (__int64)&v28,
                  (__int64)&v27);
              }
              Mtxunlock(v15);
            }
            v16 = g_pcsAsimovLock;
            if ( g_pcsAsimovLock )
            {
              Mtxlock(g_pcsAsimovLock);
              if ( **(_DWORD **)&g_hMp1dsProvider > 5u
                && (*(_QWORD *)(*(_QWORD *)&g_hMp1dsProvider + 16LL) & 0x400000000000LL) != 0
                && (*(_QWORD *)(*(_QWORD *)&g_hMp1dsProvider + 24LL) & 0x400000000000LL) == *(_QWORD *)(*(_QWORD *)&g_hMp1dsProvider + 24LL) )
              {
                v37 = (unsigned int)v4;
                v54 = (__int64)(&off_1401D90D0)[v12];
                v45 = 2048;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
                  g_hMp1dsProvider,
                  (__int64)&v45,
                  (__int64)&v37 + 4,
                  (__int64)&v54,
                  (__int64)&v37);
              }
              Mtxunlock(v16);
            }
            if ( *((_BYTE *)&off_1401D90D0 + 8 * v12 + 24) || MpWatchDog::MpIsCoreSvcInDevMode((MpWatchDog *)v14) )
            {
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                WPP_SF_Sd(
                  *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                  66,
                  (unsigned int)&WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
                  (unsigned int)(&off_1401D90D0)[v12],
                  v4);
              }
              if ( *((_BYTE *)&off_1401D90D0 + 8 * v12 + 24) )
                goto LABEL_58;
            }
            else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            {
              WPP_SF_Sd(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                67,
                (unsigned int)&WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
                (unsigned int)(&off_1401D90D0)[v12],
                v4);
            }
          }
          _m_prefetchw(&dword_1401E72E8);
          v17 = (int)dword_1401E72E8;
          do
          {
            v18 = v17;
            v17 = _InterlockedCompareExchange((volatile signed __int32 *)&dword_1401E72E8, v17, v17);
          }
          while ( v18 != v17 );
          if ( v17 > 0 )
            goto LABEL_67;
          v10 = WPP_GLOBAL_Control;
        }
        goto LABEL_68;
      }
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        63,
        &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
        (unsigned int)TimerQueueTimer);
    }
    v10 = WPP_GLOBAL_Control;
    goto LABEL_21;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      62,
      &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
      (unsigned int)v3);
LABEL_58:
  v19 = g_pcsAsimovLock;
  if ( g_pcsAsimovLock )
  {
    Mtxlock(g_pcsAsimovLock);
    if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
      && (*(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider + 16LL) & 0x400000000000LL) != 0
      && (*(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider + 24LL) & 0x400000000000LL) == *(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider
                                                                                               + 24LL) )
    {
      v52 = v4;
      v43 = v26;
      LODWORD(v54) = *((_DWORD *)g_aAsimov + 18);
      LODWORD(v38) = *((_DWORD *)g_aAsimov + 17);
      LODWORD(v39) = *((_DWORD *)g_aAsimov + 16);
      LODWORD(v40) = *((unsigned __int8 *)g_aAsimov + 60);
      LODWORD(v41) = *((unsigned __int8 *)g_aAsimov + 59);
      LODWORD(v26) = *((unsigned __int8 *)g_aAsimov + 58);
      LODWORD(v25) = *((unsigned __int8 *)g_aAsimov + 57);
      LODWORD(v24) = *((unsigned __int8 *)g_aAsimov + 56);
      v42 = *((_QWORD *)g_aAsimov + 6);
      v46 = *((_QWORD *)g_aAsimov + 5);
      v47 = *((_QWORD *)g_aAsimov + 4);
      v48 = *((_QWORD *)g_aAsimov + 3);
      v49 = *((_QWORD *)g_aAsimov + 2);
      v50 = *((_QWORD *)g_aAsimov + 1);
      v51[0] = 0x2000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        g_hMpAsimovProvider,
        (int)&byte_1401B8F8B,
        (__int64)v51,
        (__int64)&v50,
        (__int64)&v49,
        (__int64)&v48,
        (__int64)&v47,
        (__int64)&v46,
        (__int64)&v42,
        (__int64)&v24,
        (__int64)&v25,
        (__int64)&v26,
        (__int64)&v41,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v38,
        (__int64)&v54,
        (__int64)&v43,
        (__int64)&v53,
        (__int64)&v52);
    }
    Mtxunlock(v19);
  }
  StopDefederCoreService(v4);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      68,
      &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
      (unsigned int)v4);
}

```

## disassembly

```asm
0x140088b60  push    rbx
0x140088b62  push    rsi
0x140088b63  push    rdi
0x140088b64  push    r12
0x140088b66  push    r13
0x140088b68  push    r14
0x140088b6a  push    r15
0x140088b6c  sub     rsp, 180h
0x140088b73  mov     dword ptr [rsp+1B8h+arg_10], 0FFFFFFFFh
0x140088b7e  xor     edx, edx; wchar_t *
0x140088b80  lea     rcx, stru_1401952C8; this
0x140088b87  call    ?GetMiscConfigDword@MpWatchDog@@YAKPEB_WK@Z; MpWatchDog::GetMiscConfigDword(wchar_t const *,ulong)
0x140088b8c  cmp     eax, 1
0x140088b8f  jnz     short loc_140088B97
0x140088b91  call    cs:__imp_DebugBreak
0x140088b97  lea     rsi, WPP_GLOBAL_Control
0x140088b9e  mov     rcx, cs:WPP_GLOBAL_Control
0x140088ba5  cmp     rcx, rsi
0x140088ba8  jz      short loc_140088BC5
0x140088baa  test    byte ptr [rcx+1Ch], 4
0x140088bae  jz      short loc_140088BC5
0x140088bb0  mov     edx, 3Dh ; '='
0x140088bb5  lea     r8, WPP_015d1d1aad8334bf574fd190c463be63_Traceguids
0x140088bbc  mov     rcx, [rcx+10h]
0x140088bc0  call    WPP_SF_
0x140088bc5  lea     rax, aReinforcedefen; "ReinforceDefenderCoreServiceAcls"
0x140088bcc  mov     [rsp+1B8h+var_F8], rax
0x140088bd4  call    ReinforceDefenderCoreServiceAcls
0x140088bd9  mov     ebx, eax
0x140088bdb  test    eax, eax
0x140088bdd  jns     short loc_140088C18
0x140088bdf  mov     rcx, cs:WPP_GLOBAL_Control
0x140088be6  cmp     rcx, rsi
0x140088be9  jz      short loc_140088C09
0x140088beb  test    byte ptr [rcx+1Ch], 1
0x140088bef  jz      short loc_140088C09
0x140088bf1  mov     edx, 3Eh ; '>'
0x140088bf6  mov     r9d, eax
0x140088bf9  lea     r8, WPP_015d1d1aad8334bf574fd190c463be63_Traceguids
0x140088c00  mov     rcx, [rcx+10h]
0x140088c04  call    WPP_SF_d
0x140088c09  mov     r12, 400000000000h
0x140088c13  jmp     loc_1400891D3
0x140088c18  prefetchw byte ptr cs:dword_1401E72E8
0x140088c1f  mov     eax, cs:dword_1401E72E8
0x140088c25  mov     ecx, eax; this
0x140088c27  lock cmpxchg cs:dword_1401E72E8, ecx
0x140088c2f  jnz     short loc_140088C25
0x140088c31  test    eax, eax
0x140088c33  jg      loc_140089436
0x140088c39  call    ?MpIsCoreSvcInDevMode@MpWatchDog@@YA_NXZ; MpWatchDog::MpIsCoreSvcInDevMode(void)
0x140088c3e  neg     al
0x140088c40  sbb     ebx, ebx
0x140088c42  not     ebx
0x140088c44  and     ebx, 0EA60h
0x140088c4a  mov     rdx, cs:?gs_ServiceConfigureTimer@@3V?$CUniqueHandle@UCAutoDeleteTimerQueueTimer@CommonUtil@@@CommonUtil@@A; Timer
0x140088c51  test    rdx, rdx
0x140088c54  jz      short loc_140088C6D
0x140088c56  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x140088c5a  xor     ecx, ecx; TimerQueue
0x140088c5c  call    cs:__imp_DeleteTimerQueueTimer
0x140088c62  mov     cs:?gs_ServiceConfigureTimer@@3V?$CUniqueHandle@UCAutoDeleteTimerQueueTimer@CommonUtil@@@CommonUtil@@A, 0; CommonUtil::CUniqueHandle<CommonUtil::CAutoDeleteTimerQueueTimer> gs_ServiceConfigureTimer
0x140088c6d  mov     dword ptr [rsp+1B8h+var_190], 0; void *
0x140088c75  mov     [rsp+1B8h+var_198], 0; int
0x140088c7e  lea     r9, ?ConfigureServiceTimerCallback@@YAXPEAXE@Z; unsigned int
0x140088c85  xor     r8d, r8d; unsigned int
0x140088c88  mov     edx, ebx; void **
0x140088c8a  lea     rcx, ?gs_ServiceConfigureTimer@@3V?$CUniqueHandle@UCAutoDeleteTimerQueueTimer@CommonUtil@@@CommonUtil@@A; this
0x140088c91  call    ?UtilCreateTimerQueueTimer@CommonUtil@@YAJPEAPEAXKKP6AXPEAXE@Z1K@Z; CommonUtil::UtilCreateTimerQueueTimer(void * *,ulong,ulong,void (*)(void *,uchar),void *,ulong)
0x140088c96  test    eax, eax
0x140088c98  jns     short loc_140088CC4
0x140088c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140088ca1  cmp     rcx, rsi
0x140088ca4  jz      short loc_140088CCB
0x140088ca6  test    byte ptr [rcx+1Ch], 2
0x140088caa  jz      short loc_140088CCB
0x140088cac  mov     edx, 3Fh ; '?'
0x140088cb1  mov     r9d, eax
0x140088cb4  lea     r8, WPP_015d1d1aad8334bf574fd190c463be63_Traceguids
0x140088cbb  mov     rcx, [rcx+10h]
0x140088cbf  call    WPP_SF_d
0x140088cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140088ccb  lea     rax, aInitializingmo; "InitializingModules"
0x140088cd2  mov     [rsp+1B8h+var_F8], rax
0x140088cda  xor     r14d, r14d
0x140088cdd  lea     r15, off_1401D90D0; "WdTargetManager"
0x140088ce4  mov     r12, 400000000000h
0x140088cee  mov     [rsp+1B8h+var_108], r14
0x140088cf6  cmp     r14, 0Ah
0x140088cfa  jnb     loc_14008943D
0x140088d00  mov     dword ptr [rsp+1B8h+arg_18], r14d
0x140088d08  mov     dword ptr [rsp+1B8h+arg_10], r14d
0x140088d10  mov     rdi, r14
0x140088d13  shl     rdi, 5
0x140088d17  mov     [rsp+1B8h+var_100], rdi
0x140088d1f  mov     rax, [rdi+r15+8]
0x140088d24  test    rax, rax
0x140088d27  jz      short loc_140088D33
0x140088d29  call    cs:__guard_dispatch_icall_fptr
0x140088d2f  mov     ebx, eax
0x140088d31  jmp     short loc_140088D35
0x140088d33  xor     ebx, ebx
0x140088d35  mov     [rsp+1B8h+arg_8], ebx
0x140088d3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140088d43  cmp     rcx, rsi
0x140088d46  jz      short loc_140088D73
0x140088d48  test    byte ptr [rcx+1Ch], 4
0x140088d4c  jz      short loc_140088D73
0x140088d4e  mov     edx, 40h ; '@'
0x140088d53  mov     dword ptr [rsp+1B8h+var_188], ebx; char
0x140088d57  mov     rax, [rdi+r15]
0x140088d5b  mov     [rsp+1B8h+var_190], rax; __int64
0x140088d60  mov     r9, r14
0x140088d63  mov     rcx, [rcx+10h]; LoggerHandle
0x140088d67  call    WPP_SF_PdSd
0x140088d6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140088d73  mov     eax, ebx
0x140088d75  shr     eax, 1Fh
0x140088d78  xor     al, 1
0x140088d7a  mov     [rdi+r15+19h], al
0x140088d7f  jmp     short loc_140088DEF
0x140088d81  lea     rsi, WPP_GLOBAL_Control
0x140088d88  lea     r15, off_1401D90D0; "WdTargetManager"
0x140088d8f  mov     r12, 400000000000h
0x140088d99  mov     ebx, [rsp+1B8h+arg_8]
0x140088da0  mov     r14, [rsp+1B8h+var_108]
0x140088da8  mov     rcx, cs:WPP_GLOBAL_Control
0x140088daf  mov     rdi, [rsp+1B8h+var_100]
0x140088db7  jmp     short loc_140088DF7
0x140088db9  lea     rsi, WPP_GLOBAL_Control
0x140088dc0  lea     r15, off_1401D90D0; "WdTargetManager"
0x140088dc7  mov     r12, 400000000000h
0x140088dd1  mov     ebx, [rsp+1B8h+arg_8]
0x140088dd8  mov     r14, [rsp+1B8h+var_108]
0x140088de0  mov     rcx, cs:WPP_GLOBAL_Control
0x140088de7  mov     rdi, [rsp+1B8h+var_100]
0x140088def  test    ebx, ebx
0x140088df1  jns     loc_14008916C
0x140088df7  cmp     rcx, rsi
0x140088dfa  jz      short loc_140088E20
0x140088dfc  test    byte ptr [rcx+1Ch], 1
0x140088e00  jz      short loc_140088E20
0x140088e02  mov     edx, 41h ; 'A'
0x140088e07  mov     dword ptr [rsp+1B8h+var_188], ebx; char
0x140088e0b  mov     rax, [rdi+r15]
0x140088e0f  mov     [rsp+1B8h+var_190], rax; __int64
0x140088e14  mov     r9, r14
0x140088e17  mov     rcx, [rcx+10h]; LoggerHandle
0x140088e1b  call    WPP_SF_PdSd
0x140088e20  test    ebx, ebx
0x140088e22  jns     loc_14008916C
0x140088e28  mov     r13, cs:?g_pcsAsimovLock@@3PEAVCMpCriticalSection@CommonUtil@@EA; CommonUtil::CMpCriticalSection * g_pcsAsimovLock
0x140088e2f  test    r13, r13
0x140088e32  jz      loc_140089051
0x140088e38  mov     rcx, r13; lpCriticalSection
0x140088e3b  call    _Mtxlock
0x140088e40  mov     r8, cs:g_hMpAsimovProvider
0x140088e47  cmp     dword ptr [r8], 5
0x140088e4b  jbe     loc_140089048
0x140088e51  test    [r8+10h], r12
0x140088e55  jz      loc_140089048
0x140088e5b  mov     rax, [r8+18h]
0x140088e5f  and     rax, r12
0x140088e62  cmp     rax, [r8+18h]
0x140088e66  jnz     loc_140089048
0x140088e6c  mov     dword ptr [rsp+1B8h+var_F0], ebx
0x140088e73  mov     eax, dword ptr [rsp+1B8h+arg_18]
0x140088e7a  mov     dword ptr [rsp+1B8h+var_F0+4], eax
0x140088e81  mov     rax, [rdi+r15]
0x140088e85  mov     [rsp+1B8h+arg_18], rax
0x140088e8d  mov     rcx, cs:?g_aAsimov@@3PEAVCMpAsimov@@EA; CMpAsimov * g_aAsimov
0x140088e94  mov     eax, [rcx+48h]
0x140088e97  mov     dword ptr [rsp+1B8h+var_E8], eax
0x140088e9e  mov     eax, [rcx+44h]
0x140088ea1  mov     dword ptr [rsp+1B8h+var_E8+4], eax
0x140088ea8  mov     eax, [rcx+40h]
0x140088eab  mov     [rsp+1B8h+var_E0], eax
0x140088eb2  movzx   eax, byte ptr [rcx+3Ch]
0x140088eb6  mov     [rsp+1B8h+var_DC], eax
0x140088ebd  movzx   eax, byte ptr [rcx+3Bh]
0x140088ec1  mov     [rsp+1B8h+var_D8], eax
0x140088ec8  movzx   eax, byte ptr [rcx+3Ah]
0x140088ecc  mov     [rsp+1B8h+var_D4], eax
0x140088ed3  movzx   eax, byte ptr [rcx+39h]
0x140088ed7  mov     [rsp+1B8h+var_D0], eax
0x140088ede  movzx   eax, byte ptr [rcx+38h]
0x140088ee2  mov     [rsp+1B8h+var_CC], eax
0x140088ee9  mov     rax, [rcx+30h]
0x140088eed  mov     [rsp+1B8h+var_A8], rax
0x140088ef5  mov     rax, [rcx+28h]
0x140088ef9  mov     [rsp+1B8h+var_B0], rax
0x140088f01  mov     rax, [rcx+20h]
0x140088f05  mov     [rsp+1B8h+var_B8], rax
0x140088f0d  mov     rax, [rcx+18h]
0x140088f11  mov     [rsp+1B8h+var_C0], rax
0x140088f19  mov     rax, [rcx+10h]
0x140088f1d  mov     [rsp+1B8h+var_A0], rax
0x140088f25  mov     rax, [rcx+8]
0x140088f29  mov     [rsp+1B8h+var_98], rax
0x140088f31  mov     [rsp+1B8h+var_90], 2000000h
0x140088f3d  lea     rax, [rsp+1B8h+var_F0]
0x140088f45  mov     [rsp+1B8h+var_110], rax; __int64
0x140088f4d  lea     rax, [rsp+1B8h+var_F0+4]
0x140088f55  mov     [rsp+1B8h+var_118], rax; __int64
0x140088f5d  lea     rax, [rsp+1B8h+arg_18]
0x140088f65  mov     [rsp+1B8h+var_120], rax; __int64
0x140088f6d  lea     rax, [rsp+1B8h+var_E8]
0x140088f75  mov     [rsp+1B8h+var_128], rax; __int64
0x140088f7d  lea     rax, [rsp+1B8h+var_E8+4]
0x140088f85  mov     [rsp+1B8h+var_130], rax; __int64
0x140088f8d  lea     rax, [rsp+1B8h+var_E0]
0x140088f95  mov     [rsp+1B8h+var_138], rax; __int64
0x140088f9d  lea     rax, [rsp+1B8h+var_DC]
0x140088fa5  mov     [rsp+1B8h+var_140], rax; __int64
0x140088faa  lea     rax, [rsp+1B8h+var_D8]
0x140088fb2  mov     [rsp+1B8h+var_148], rax; __int64
0x140088fb7  lea     rax, [rsp+1B8h+var_D4]
0x140088fbf  mov     [rsp+1B8h+var_150], rax; __int64
0x140088fc4  lea     rax, [rsp+1B8h+var_D0]
0x140088fcc  mov     [rsp+1B8h+var_158], rax; __int64
0x140088fd1  lea     rax, [rsp+1B8h+var_CC]
0x140088fd9  mov     [rsp+1B8h+var_160], rax; __int64
0x140088fde  lea     rax, [rsp+1B8h+var_A8]
0x140088fe6  mov     [rsp+1B8h+var_168], rax; __int64
0x140088feb  lea     rax, [rsp+1B8h+var_B0]
0x140088ff3  mov     [rsp+1B8h+var_170], rax; __int64
0x140088ff8  lea     rax, [rsp+1B8h+var_B8]
0x140089000  mov     [rsp+1B8h+var_178], rax; __int64
0x140089005  lea     rax, [rsp+1B8h+var_C0]
0x14008900d  mov     [rsp+1B8h+var_180], rax; __int64
0x140089012  lea     rax, [rsp+1B8h+var_A0]
0x14008901a  mov     qword ptr [rsp+1B8h+var_188], rax; __int64
0x14008901f  lea     rax, [rsp+1B8h+var_98]
0x140089027  mov     [rsp+1B8h+var_190], rax; __int64
0x14008902c  lea     rax, [rsp+1B8h+var_90]
0x140089034  mov     [rsp+1B8h+var_198], rax; __int64
0x140089039  lea     rdx, byte_1401B910D; int
0x140089040  mov     rcx, r8; int
0x140089043  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@_W@@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@U3@U3@U2@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@_W@@44444AEBU?$_tlgWrapperByVal@$03@@5555555455@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140089048  mov     rcx, r13; lpCriticalSection
0x14008904b  call    _Mtxunlock
0x140089050  nop
0x140089051  mov     r13, cs:?g_pcsAsimovLock@@3PEAVCMpCriticalSection@CommonUtil@@EA; CommonUtil::CMpCriticalSection * g_pcsAsimovLock
0x140089058  test    r13, r13
0x14008905b  jz      loc_1400890FB
0x140089061  mov     rcx, r13; lpCriticalSection
0x140089064  call    _Mtxlock
0x140089069  mov     rcx, cs:g_hMp1dsProvider; int
0x140089070  cmp     dword ptr [rcx], 5
0x140089073  jbe     short loc_1400890F2
0x140089075  test    [rcx+10h], r12
0x140089079  jz      short loc_1400890F2
0x14008907b  mov     rax, [rcx+18h]
0x14008907f  and     rax, r12
0x140089082  cmp     rax, [rcx+18h]
0x140089086  jnz     short loc_1400890F2
0x140089088  mov     dword ptr [rsp+1B8h+var_C8], ebx
0x14008908f  mov     rax, [rdi+r15]
0x140089093  mov     [rsp+1B8h+arg_18], rax
0x14008909b  mov     dword ptr [rsp+1B8h+var_C8+4], 0
0x1400890a6  mov     [rsp+1B8h+var_88], 800h
0x1400890b2  lea     rax, [rsp+1B8h+var_C8]
0x1400890ba  mov     [rsp+1B8h+var_180], rax; __int64
0x1400890bf  lea     rax, [rsp+1B8h+arg_18]
0x1400890c7  mov     qword ptr [rsp+1B8h+var_188], rax; __int64
0x1400890cc  lea     rax, [rsp+1B8h+var_C8+4]
0x1400890d4  mov     [rsp+1B8h+var_190], rax; __int64
0x1400890d9  lea     rax, [rsp+1B8h+var_88]
0x1400890e1  mov     [rsp+1B8h+var_198], rax; __int64
0x1400890e6  lea     rdx, byte_1401B90B3
0x1400890ed  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1400890f2  mov     rcx, r13; lpCriticalSection
0x1400890f5  call    _Mtxunlock
0x1400890fa  nop
0x1400890fb  jmp     short loc_14008912C
0x1400890fd  mov     rdi, [rsp+1B8h+var_100]
0x140089105  mov     r14, [rsp+1B8h+var_108]
0x14008910d  mov     ebx, [rsp+1B8h+arg_8]
0x140089114  mov     r12, 400000000000h
0x14008911e  lea     r15, off_1401D90D0; "WdTargetManager"
0x140089125  lea     rsi, WPP_GLOBAL_Control
0x14008912c  cmp     byte ptr [rdi+r15+18h], 0
0x140089132  jnz     short loc_14008919C
0x140089134  call    ?MpIsCoreSvcInDevMode@MpWatchDog@@YA_NXZ; MpWatchDog::MpIsCoreSvcInDevMode(void)
0x140089139  test    al, al
0x14008913b  jnz     short loc_14008919C
0x14008913d  mov     rcx, cs:WPP_GLOBAL_Control
0x140089144  cmp     rcx, rsi
0x140089147  jz      short loc_14008916C
0x140089149  test    byte ptr [rcx+1Ch], 2
0x14008914d  jz      short loc_14008916C
0x14008914f  mov     edx, 43h ; 'C'
0x140089154  mov     dword ptr [rsp+1B8h+var_198], ebx
0x140089158  mov     r9, [rdi+r15]
0x14008915c  lea     r8, WPP_015d1d1aad8334bf574fd190c463be63_Traceguids
0x140089163  mov     rcx, [rcx+10h]
0x140089167  call    WPP_SF_Sd
0x14008916c  prefetchw byte ptr cs:dword_1401E72E8
0x140089173  mov     eax, cs:dword_1401E72E8
0x140089179  mov     ecx, eax
  ... truncated ...
```
