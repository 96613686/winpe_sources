# ProcessBootErrorLog(void *)

- ea: `0x1800429e0`
- end: `0x18004349c`
- name: `?ProcessBootErrorLog@@YAIPEAX@Z`
- size: `2748`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `28`
- tags: ``

## callees

- `0x18000115c`
- `0x18000188c`
- `0x180001ad0`
- `0x180001fe8`
- `0x180009c30`
- `0x180009f30`
- `0x180009f60`
- `0x18000d904`
- `0x18001b4f0`
- `0x180027508`
- `0x180027980`
- `0x180034070`
- `0x180034d04`
- `0x180034d28`
- `0x18003ab48`
- `0x18003ac50`
- `0x18003ad48`
- `0x1800429e0`
- `0x180044378`
- `0x18004f378`
- `0x1800591ec`
- `0x18005f4c0`
- `0x18005fec0`
- `0x180061f40`
- `0x180062290`
- `0x18006a26c`
- `0x18006a4bc`
- `0x18006a594`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043411`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043436`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043411`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180043436`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800433fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043422`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800433fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180043422`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180042acf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180042acf`
- `FVEAPI!FveGetVolumeNameW` at `0x180043096`
- `FVEAPI!FveGetVolumeNameW` at `0x180043096`
- `FVEAPI!FveCloseVolume` at `0x18004301c`
- `FVEAPI!FveCloseVolume` at `0x18004301c`

## string_xrefs

- `0x180042fcc`: `base\ngscb\cornerstone\bdesvc\svc\thread.cpp`
- `0x1800430b2`: `base\ngscb\cornerstone\bdesvc\svc\thread.cpp`
- `0x180043329`: `base\ngscb\cornerstone\bdesvc\svc\thread.cpp`

## pseudocode

```c
__int64 __fastcall ProcessBootErrorLog(void *a1)
{
  LPVOID v1; // rsi
  struct _DRIVER_LOGGED_EVENT *v2; // rbx
  struct _GUID v3; // xmm6
  struct RecoveryTelemetery *Instance; // r14
  __int64 v5; // r12
  char v6; // r13
  __int64 v7; // rcx
  unsigned int DriverEventsSinceVolumeArrival; // eax
  int v9; // ebx
  unsigned __int64 v10; // r15
  int v11; // r13d
  unsigned __int64 v12; // rdx
  int v13; // eax
  unsigned __int64 v14; // rax
  int v15; // r12d
  __int64 v16; // rdi
  unsigned int v17; // ecx
  unsigned int *v18; // rsi
  __int64 v19; // r8
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  unsigned __int64 v23; // rax
  int v24; // r8d
  int v25; // r9d
  int v26; // r8d
  int v27; // r9d
  unsigned __int64 v28; // rax
  int v29; // r8d
  int v30; // edi
  PVOID *v31; // rdi
  int v32; // edi
  int v33; // eax
  unsigned int v34; // edi
  int v35; // eax
  int VolumeNameW; // eax
  unsigned int v37; // edi
  int v38; // eax
  int v39; // edi
  int v40; // r8d
  int v41; // r9d
  HANDLE ProcessHeap; // rax
  HANDLE v43; // rax
  unsigned int v45; // [rsp+28h] [rbp-E0h]
  char v46[4]; // [rsp+58h] [rbp-B0h] BYREF
  _WORD v47[2]; // [rsp+5Ch] [rbp-ACh] BYREF
  __int64 v48; // [rsp+60h] [rbp-A8h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-A0h]
  __int64 v50; // [rsp+70h] [rbp-98h]
  void *v51; // [rsp+78h] [rbp-90h] BYREF
  __int64 v52; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int64 v53; // [rsp+88h] [rbp-80h]
  __int128 Buf2; // [rsp+90h] [rbp-78h] BYREF
  __int64 v55; // [rsp+A0h] [rbp-68h]
  struct _GUID v56; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v57[2]; // [rsp+B8h] [rbp-50h] BYREF
  struct _DRIVER_LOGGED_EVENT *v58; // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int64 v59; // [rsp+D0h] [rbp-38h] BYREF
  int v60; // [rsp+D8h] [rbp-30h] BYREF
  __int128 Buf1; // [rsp+E0h] [rbp-28h] BYREF
  void **v62; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE v63[36]; // [rsp+F8h] [rbp-10h] BYREF
  _QWORD v64[6]; // [rsp+120h] [rbp+18h] BYREF
  _QWORD v65[6]; // [rsp+150h] [rbp+48h] BYREF
  _QWORD v66[7]; // [rsp+180h] [rbp+78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v67; // [rsp+1B8h] [rbp+B0h] BYREF
  __int128 v68; // [rsp+1C8h] [rbp+C0h]
  __int128 v69; // [rsp+1D8h] [rbp+D0h]
  unsigned __int64 *v70; // [rsp+1E8h] [rbp+E0h]
  __int64 v71; // [rsp+1F0h] [rbp+E8h]
  unsigned __int16 v72[264]; // [rsp+1F8h] [rbp+F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+470h] [rbp+368h]

  v1 = a1;
  lpMem = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  v62 = &CFveEventLogQueryExecutor::`vftable';
  v2 = 0;
  v58 = 0;
  v59 = 0;
  v3 = 0;
  Buf1 = 0;
  Buf2 = 0;
  v56 = 0;
  Instance = RecoveryTelemetery::getInstance();
  v5 = -1;
  v51 = (void *)-1LL;
  v60 = 260;
  memset_0(v72, 0, 0x208u);
  memset(v63, 0, sizeof(v63));
  v6 = 0;
  v46[0] = 0;
  BdeSvcProcessWinREEvents();
  if ( !v1 )
    goto LABEL_74;
  Sleep(0x2710u);
  DriverEventsSinceVolumeArrival = GetDriverEventsSinceVolumeArrival(
                                     *(_QWORD *)v1,
                                     (struct IFveEventLogQueryExecutor *)&v62,
                                     &v58,
                                     &v59);
  v9 = DriverEventsSinceVolumeArrival;
  if ( DriverEventsSinceVolumeArrival )
  {
    v7 = (__int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        116,
        &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
        DriverEventsSinceVolumeArrival);
    if ( v9 < 0 )
      goto LABEL_100;
  }
  v10 = v59;
  if ( !v59 )
  {
LABEL_100:
    v2 = v58;
  }
  else
  {
    v50 = 0;
    v11 = 1;
    v12 = 0;
    v2 = v58;
    do
    {
      v13 = 0;
      if ( *((_WORD *)v58 + 24 * v12) != 24711 )
        v13 = v11;
      v11 = v13;
      ++v12;
    }
    while ( v12 < v59 );
    v14 = 0;
    v53 = 0;
    v15 = 0;
    do
    {
      v16 = 48 * v14;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          117,
          &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
          *(unsigned __int16 *)((char *)v2 + v16));
      v17 = *(_DWORD *)((char *)v2 + v16 + 4);
      if ( v17 )
        AddDriverErrorToSqm(v17, *((_DWORD *)v1 + 2));
      v18 = (unsigned int *)((char *)v2 + v16 + 44);
      if ( *(_WORD *)((char *)v2 + v16) == 24604 )
      {
        AddDriverBCDErrorToSqm(*(_DWORD *)((char *)v2 + v16 + 4), *((_DWORD *)lpMem + 2), *v18);
        if ( (unsigned int)dword_18009A348 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
        {
          LODWORD(v59) = *v18;
          v47[0] = *(_WORD *)((char *)v2 + v16);
          v70 = &v59;
          v71 = v19;
          *(_QWORD *)&v69 = v47;
          *((_QWORD *)&v69 + 1) = 2;
          tlgWriteTransfer_EventWriteTransfer((int)&dword_18009A348, (int)&byte_18008CFD1, 0, 0, v19, &v67);
        }
        if ( (unsigned int)dword_18009A310 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A310, 0x800000000000LL) )
        {
          LODWORD(v59) = *v18;
          LODWORD(v58) = *(_DWORD *)((char *)v2 + v16 + 4);
          v47[0] = *(_WORD *)((char *)v2 + v16);
          v52 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v20,
            (unsigned int)&byte_18008CF7F,
            v21,
            v22,
            (__int64)&v52,
            (__int64)v47,
            (__int64)&v58,
            (__int64)&v59);
        }
        if ( Instance )
          RecoveryTelemetery::AddRecoveryEvent(
            Instance,
            &v56,
            *(_WORD *)((char *)v2 + v16),
            *(_DWORD *)((char *)v2 + v16 + 4),
            0,
            *v18);
      }
      v7 = 24627;
      v23 = *(unsigned __int16 *)((char *)v2 + v16);
      LOWORD(v23) = v23 - 24627;
      if ( (unsigned __int16)v23 <= 0x35u && (v7 = 0x202001C2010B41LL, _bittest64(&v7, v23))
        || *(_WORD *)((char *)v2 + v16) == 24720 )
      {
        if ( (unsigned int)dword_18009A348 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
        {
          v47[0] = *(_WORD *)((char *)v2 + v16);
          LODWORD(v58) = *(_DWORD *)((char *)v2 + v16 + 4);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(
            v7,
            (unsigned int)word_18008CF32,
            v24,
            v25,
            (__int64)&v58,
            (__int64)v47);
        }
        if ( (unsigned int)dword_18009A310 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18009A310, 0x800000000000LL) )
        {
          v18 = (unsigned int *)((char *)v2 + v16 + 44);
          LODWORD(v58) = *v18;
          LODWORD(v59) = *(_DWORD *)((char *)v2 + v16 + 4);
          v47[0] = *(_WORD *)((char *)v2 + v16);
          v52 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v7,
            (unsigned int)qword_18008CEE0,
            v26,
            v27,
            (__int64)&v52,
            (__int64)v47,
            (__int64)&v59,
            (__int64)&v58);
        }
        if ( Instance )
          RecoveryTelemetery::AddRecoveryEvent(
            Instance,
            &v56,
            *(_WORD *)((char *)v2 + v16),
            *(_DWORD *)((char *)v2 + v16 + 4),
            0,
            *v18);
      }
      if ( v15 || !v11 )
      {
        v1 = lpMem;
      }
      else
      {
        v28 = *(unsigned __int16 *)((char *)v2 + v16);
        v7 = 24604;
        LOWORD(v28) = v28 - 24604;
        v1 = lpMem;
        if ( (unsigned __int16)v28 <= 0x36u )
        {
          v7 = 0x64000280000001LL;
          if ( _bittest64(&v7, v28) )
          {
            if ( !*((_DWORD *)lpMem + 2) )
            {
              AttemptTpmAutoReseal();
              v15 = 1;
            }
          }
        }
      }
      if ( !(_DWORD)v50 && (*(_WORD *)((char *)v2 + v16) == 24659 || *(_WORD *)((char *)v2 + v16) == 24672) )
      {
        AttemptProtectorRecovery();
        LODWORD(v50) = 1;
      }
      if ( *(_WORD *)((char *)v2 + v16) == 24652 )
      {
        v29 = 1;
        HIDWORD(v50) = 1;
        v3 = *(struct _GUID *)((char *)v2 + v16 + 12);
        Buf1 = *(_OWORD *)((char *)v2 + v16 + 28);
      }
      else
      {
        v29 = HIDWORD(v50);
      }
      v14 = v53 + 1;
      v53 = v14;
    }
    while ( v14 < v10 );
    v56 = v3;
    v5 = (__int64)v51;
    if ( v29 )
    {
      v30 = CheckDeviceForClientKeyRotation();
      if ( v30 < 0 )
      {
        v7 = (__int64)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            124,
            &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
            (unsigned int)v30);
        if ( v30 != -2144272363 && v30 != -2144272161 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xFAC,
            (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\thread.cpp",
            (const char *)(unsigned int)v30,
            v45);
      }
      else
      {
        if ( Instance )
          *((_BYTE *)Instance + 18) = 1;
        v31 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
          v31 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
        {
          if ( v31 != &WPP_GLOBAL_Control && (*((_BYTE *)v31 + 28) & 2) != 0 )
            WPP_SF_(v31[2], 119, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
          v32 = 0;
          goto LABEL_101;
        }
        *(_DWORD *)v63 = 1;
        *(_OWORD *)&v63[4] = Buf1;
        *(struct _GUID *)&v63[20] = v3;
        v33 = FvepOpenVolumeByGuid(&v56, &v51);
        v34 = v33;
        if ( v33 >= 0 )
        {
          v5 = (__int64)v51;
          VolumeNameW = FveGetVolumeNameW(v51, &v60, v72);
          v37 = VolumeNameW;
          if ( VolumeNameW >= 0 )
          {
            v38 = FveSavePersistentRequest(v72, 1u, (__int64)v63, 0x24u);
            v39 = v38;
            if ( v38 >= 0 )
            {
              v7 = (__int64)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
              v6 = 1;
              goto LABEL_74;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                122,
                &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
                (unsigned int)v38);
            *(_QWORD *)&v56.Data1 = 0;
            Buf2 = 0u;
            v55 = 0;
            v64[2] = L"ProtectorGUID";
            v64[3] = L"GUID";
            v64[4] = &Buf1;
            v64[5] = 16;
            v64[1] = v57;
            v57[0] = v64;
            LODWORD(v58) = 1;
            v65[2] = L"RequestType";
            v65[3] = L"ULONG";
            v65[4] = &v58;
            v65[5] = 4;
            v65[1] = v64;
            v64[0] = v65;
            v68 = 0;
            v69 = 0;
            FveApiEventLogDeclareWSTRING(
              (struct _FVEAPI_EVENT_DATA *)&v67,
              (const unsigned __int16 *)&v58,
              L"VolumeName",
              v72,
              v45);
            *(_QWORD *)&v67.Size = v65;
            v65[0] = &v67;
            LODWORD(v59) = v39;
            v66[2] = L"hr";
            v66[3] = L"HRESULT";
            v66[4] = &v59;
            v66[5] = 4;
            v66[0] = v57;
            v66[1] = &v67;
            v67.Ptr = (ULONGLONG)v66;
            v57[1] = v66;
            *(_QWORD *)v56.Data4 = FVEAPI_SAVE_PERSISTENT_REQ_FAILED;
            FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&Buf2, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v56);
            FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&Buf2);
          }
          else
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xF7A,
              (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\thread.cpp",
              (const char *)(unsigned int)VolumeNameW,
              v45);
            v7 = (__int64)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v37);
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xF6E,
            (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\thread.cpp",
            (const char *)(unsigned int)v33,
            v45);
          v7 = (__int64)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v34);
          v5 = (__int64)v51;
        }
      }
    }
    v6 = v46[0];
  }
LABEL_74:
  v32 = 0;
  if ( v5 != -1 )
    FveCloseVolume(v5);
  if ( v6 )
  {
    v35 = FveTriggerPersistentRequestWNFEvent(1);
    v32 = v35;
    if ( v35 < 0 )
    {
      v7 = (__int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          125,
          &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
          (unsigned int)v35);
    }
  }
LABEL_101:
  if ( Instance
    && (*((_BYTE *)Instance + 16) || *((_BYTE *)Instance + 17))
    && (unsigned int)dword_18009A348 > 4
    && (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
  {
    v52 = 0x1000000;
    LODWORD(v58) = v32;
    v46[0] = *((_BYTE *)Instance + 17);
    LOBYTE(v48) = *((_BYTE *)Instance + 16);
    LOBYTE(v47[0]) = *((_BYTE *)Instance + 18);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v7,
      (unsigned int)&unk_18008CE60,
      v40,
      v41,
      (__int64)v47,
      (__int64)&v48,
      (__int64)v46,
      (__int64)&v58,
      (__int64)&v52);
  }
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
  if ( v2 )
  {
    v43 = GetProcessHeap();
    HeapFree(v43, 0, v2);
  }
  BdeSvcWorkTracking::FinishWorkImpl((BdeSvcWorkTracking *)v7);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1800429e0  mov     rax, rsp
0x1800429e3  push    rbp
0x1800429e4  push    rbx
0x1800429e5  push    rsi
0x1800429e6  push    rdi
0x1800429e7  push    r12
0x1800429e9  push    r13
0x1800429eb  push    r14
0x1800429ed  push    r15
0x1800429ef  lea     rbp, [rax-368h]
0x1800429f6  sub     rsp, 428h
0x1800429fd  movaps  xmmword ptr [rax-58h], xmm6
0x180042a01  mov     rax, cs:__security_cookie
0x180042a08  xor     rax, rsp
0x180042a0b  mov     [rbp+360h+var_60], rax
0x180042a12  mov     rsi, rcx
0x180042a15  mov     [rsp+460h+lpMem], rcx
0x180042a1a  lea     r15, WPP_GLOBAL_Control
0x180042a21  mov     rcx, cs:WPP_GLOBAL_Control
0x180042a28  cmp     rcx, r15
0x180042a2b  jz      short loc_180042A48
0x180042a2d  test    byte ptr [rcx+1Ch], 20h
0x180042a31  jz      short loc_180042A48
0x180042a33  mov     edx, 73h ; 's'
0x180042a38  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180042a3f  mov     rcx, [rcx+10h]
0x180042a43  call    WPP_SF_
0x180042a48  lea     rax, ??_7CFveEventLogQueryExecutor@@6B@; const CFveEventLogQueryExecutor::`vftable'
0x180042a4f  mov     [rbp+360h+var_378], rax
0x180042a53  xor     edi, edi
0x180042a55  mov     ebx, edi
0x180042a57  mov     [rbp+360h+var_3A0], rbx
0x180042a5b  mov     [rbp+360h+var_398], rdi
0x180042a5f  xorps   xmm6, xmm6
0x180042a62  movups  xmmword ptr [rbp+360h+var_3C0.Data1], xmm6
0x180042a66  xorps   xmm0, xmm0
0x180042a69  movups  [rbp+360h+Buf1], xmm0
0x180042a6d  xorps   xmm1, xmm1
0x180042a70  movups  [rbp+360h+Buf2], xmm1
0x180042a74  movups  xmmword ptr [rbp+360h+var_3C0.Data1], xmm0
0x180042a78  call    ?getInstance@RecoveryTelemetery@@SAPEAV1@XZ; RecoveryTelemetery::getInstance(void)
0x180042a7d  mov     r14, rax
0x180042a80  or      r12, 0FFFFFFFFFFFFFFFFh
0x180042a84  mov     [rsp+460h+var_3F0], r12
0x180042a89  mov     [rbp+360h+var_390], 104h
0x180042a90  xor     edx, edx; Val
0x180042a92  mov     r8d, 208h; Size
0x180042a98  lea     rcx, [rbp+360h+var_270]; void *
0x180042a9f  call    memset_0
0x180042aa4  xorps   xmm0, xmm0
0x180042aa7  xor     eax, eax
0x180042aa9  movups  [rbp+360h+var_370], xmm0
0x180042aad  movups  [rbp+360h+var_360], xmm0
0x180042ab1  mov     [rbp+360h+var_350], eax
0x180042ab4  mov     r13b, dil
0x180042ab7  mov     [rsp+460h+var_410], dil
0x180042abc  call    ?BdeSvcProcessWinREEvents@@YAXXZ; BdeSvcProcessWinREEvents(void)
0x180042ac1  test    rsi, rsi
0x180042ac4  jz      loc_180043011
0x180042aca  mov     ecx, 2710h; dwMilliseconds
0x180042acf  call    cs:__imp_Sleep
0x180042ad6  nop     dword ptr [rax+rax+00h]
0x180042adb  lea     r9, [rbp+360h+var_398]; unsigned __int64 *
0x180042adf  lea     r8, [rbp+360h+var_3A0]; struct _DRIVER_LOGGED_EVENT **
0x180042ae3  lea     rdx, [rbp+360h+var_378]; struct IFveEventLogQueryExecutor *
0x180042ae7  mov     rcx, [rsi]; __int64
0x180042aea  call    ?GetDriverEventsSinceVolumeArrival@@YAJ_JPEAVIFveEventLogQueryExecutor@@PEAPEAU_DRIVER_LOGGED_EVENT@@PEA_K@Z; GetDriverEventsSinceVolumeArrival(__int64,IFveEventLogQueryExecutor *,_DRIVER_LOGGED_EVENT * *,unsigned __int64 *)
0x180042aef  mov     ebx, eax
0x180042af1  test    eax, eax
0x180042af3  jz      short loc_180042B25
0x180042af5  mov     rcx, cs:WPP_GLOBAL_Control
0x180042afc  cmp     rcx, r15
0x180042aff  jz      short loc_180042B1D
0x180042b01  test    byte ptr [rcx+1Ch], 40h
0x180042b05  jz      short loc_180042B1D
0x180042b07  lea     edx, [rdi+74h]
0x180042b0a  mov     r9d, eax
0x180042b0d  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180042b14  mov     rcx, [rcx+10h]
0x180042b18  call    WPP_SF_d
0x180042b1d  test    ebx, ebx
0x180042b1f  js      loc_180043347
0x180042b25  mov     r15, [rbp+360h+var_398]
0x180042b29  test    r15, r15
0x180042b2c  jz      loc_180043347
0x180042b32  mov     dword ptr [rsp+460h+var_3F8+4], edi
0x180042b36  mov     dword ptr [rsp+460h+var_3F8], edi
0x180042b3a  mov     r13d, 1
0x180042b40  mov     rdx, rdi
0x180042b43  mov     rbx, [rbp+360h+var_3A0]
0x180042b47  lea     rcx, [rdx+rdx*2]
0x180042b4b  add     rcx, rcx
0x180042b4e  mov     r8d, 6087h
0x180042b54  mov     eax, edi
0x180042b56  cmp     [rbx+rcx*8], r8w
0x180042b5b  cmovnz  eax, r13d
0x180042b5f  mov     r13d, eax
0x180042b62  inc     rdx
0x180042b65  cmp     rdx, r15
0x180042b68  jb      short loc_180042B47
0x180042b6a  mov     rax, rdi
0x180042b6d  mov     [rbp+360h+var_3E0], rax
0x180042b71  test    r15, r15
0x180042b74  jz      loc_18004333F
0x180042b7a  mov     r12d, eax
0x180042b7d  lea     rdi, [rax+rax*2]
0x180042b81  shl     rdi, 4
0x180042b85  mov     rcx, cs:WPP_GLOBAL_Control
0x180042b8c  lea     rax, WPP_GLOBAL_Control
0x180042b93  cmp     rcx, rax
0x180042b96  jz      short loc_180042BB8
0x180042b98  test    byte ptr [rcx+1Ch], 8
0x180042b9c  jz      short loc_180042BB8
0x180042b9e  movzx   r9d, word ptr [rdi+rbx]
0x180042ba3  mov     edx, 75h ; 'u'
0x180042ba8  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180042baf  mov     rcx, [rcx+10h]
0x180042bb3  call    WPP_SF_d
0x180042bb8  mov     ecx, [rdi+rbx+4]; unsigned int
0x180042bbc  test    ecx, ecx
0x180042bbe  jz      short loc_180042BC8
0x180042bc0  mov     edx, [rsi+8]; int
0x180042bc3  call    ?AddDriverErrorToSqm@@YAXKH@Z; AddDriverErrorToSqm(ulong,int)
0x180042bc8  mov     eax, 601Ch
0x180042bcd  lea     rsi, [rbx+2Ch]
0x180042bd1  add     rsi, rdi
0x180042bd4  cmp     [rdi+rbx], ax
0x180042bd8  jnz     loc_180042D1C
0x180042bde  mov     r8d, [rsi]; unsigned int
0x180042be1  mov     rdx, [rsp+460h+lpMem]
0x180042be6  mov     edx, [rdx+8]; int
0x180042be9  mov     ecx, [rdi+rbx+4]; unsigned int
0x180042bed  call    ?AddDriverBCDErrorToSqm@@YAXKHK@Z; AddDriverBCDErrorToSqm(ulong,int,ulong)
0x180042bf2  mov     eax, cs:dword_18009A348
0x180042bf8  mov     r8d, 4
0x180042bfe  cmp     eax, r8d
0x180042c01  jbe     short loc_180042C7E
0x180042c03  mov     rdx, 400000000000h
0x180042c0d  lea     rcx, dword_18009A348
0x180042c14  call    _tlgKeywordOn
0x180042c19  test    al, al
0x180042c1b  jz      short loc_180042C7E
0x180042c1d  mov     eax, [rsi]
0x180042c1f  mov     dword ptr [rbp+360h+var_398], eax
0x180042c22  movzx   eax, word ptr [rdi+rbx]
0x180042c26  mov     [rsp+54h], ax
0x180042c2b  lea     rax, [rbp+360h+var_398]
0x180042c2f  mov     [rbp+360h+var_280], rax
0x180042c36  mov     [rbp+360h+var_278], r8
0x180042c3d  lea     rax, [rsp+54h]
0x180042c42  mov     qword ptr [rbp+360h+var_290], rax
0x180042c49  mov     qword ptr [rbp+360h+var_290+8], 2
0x180042c54  lea     rax, [rbp+360h+var_2B0]
0x180042c5b  mov     [rsp+460h+var_438], rax; PEVENT_DATA_DESCRIPTOR
0x180042c60  mov     [rsp+460h+var_440], r8d; ULONG
0x180042c65  xor     r9d, r9d; int
0x180042c68  xor     r8d, r8d; int
0x180042c6b  lea     rdx, byte_18008CFD1; int
0x180042c72  lea     rcx, dword_18009A348; int
0x180042c79  call    _tlgWriteTransfer_EventWriteTransfer
0x180042c7e  mov     eax, cs:dword_18009A310
0x180042c84  cmp     eax, 5
0x180042c87  jbe     short loc_180042CF3
0x180042c89  mov     rdx, 800000000000h
0x180042c93  lea     rcx, dword_18009A310
0x180042c9a  call    _tlgKeywordOn
0x180042c9f  test    al, al
0x180042ca1  jz      short loc_180042CF3
0x180042ca3  mov     eax, [rsi]
0x180042ca5  mov     dword ptr [rbp+360h+var_398], eax
0x180042ca8  mov     eax, [rdi+rbx+4]
0x180042cac  mov     dword ptr [rbp+360h+var_3A0], eax
0x180042caf  movzx   eax, word ptr [rdi+rbx]
0x180042cb3  mov     [rsp+54h], ax
0x180042cb8  mov     [rsp+460h+var_3E8], 1000000h
0x180042cc1  lea     rax, [rbp+360h+var_398]
0x180042cc5  mov     [rsp+460h+var_428], rax
0x180042cca  lea     rax, [rbp+360h+var_3A0]
0x180042cce  mov     [rsp+460h+var_430], rax
0x180042cd3  lea     rax, [rsp+54h]
0x180042cd8  mov     [rsp+460h+var_438], rax
0x180042cdd  lea     rax, [rsp+460h+var_3E8]
0x180042ce2  mov     qword ptr [rsp+460h+var_440], rax
0x180042ce7  lea     rdx, byte_18008CF7F
0x180042cee  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180042cf3  test    r14, r14
0x180042cf6  jz      short loc_180042D1C
0x180042cf8  mov     eax, [rsi]
0x180042cfa  mov     dword ptr [rsp+460h+var_438], eax; unsigned int
0x180042cfe  mov     [rsp+460h+var_440], 0; unsigned int
0x180042d06  mov     r9d, [rdi+rbx+4]; unsigned int
0x180042d0b  movzx   r8d, word ptr [rdi+rbx]; unsigned __int16
0x180042d10  lea     rdx, [rbp+360h+var_3C0]; struct _GUID *
0x180042d14  mov     rcx, r14; this
0x180042d17  call    ?AddRecoveryEvent@RecoveryTelemetery@@QEAAXAEBU_GUID@@GKKK@Z; RecoveryTelemetery::AddRecoveryEvent(_GUID const &,ushort,ulong,ulong,ulong)
0x180042d1c  mov     ecx, 6033h
0x180042d21  movzx   eax, word ptr [rdi+rbx]
0x180042d25  sub     ax, cx
0x180042d28  cmp     ax, 35h ; '5'
0x180042d2c  ja      short loc_180042D3E
0x180042d2e  mov     rcx, 202001C2010B41h
0x180042d38  bt      rcx, rax
0x180042d3c  jb      short loc_180042D4D
0x180042d3e  mov     eax, 6090h
0x180042d43  cmp     [rdi+rbx], ax
0x180042d47  jnz     loc_180042E46
0x180042d4d  mov     eax, cs:dword_18009A348
0x180042d53  cmp     eax, 4
0x180042d56  jbe     short loc_180042DA1
0x180042d58  mov     rdx, 400000000000h
0x180042d62  lea     rcx, dword_18009A348
0x180042d69  call    _tlgKeywordOn
0x180042d6e  test    al, al
0x180042d70  jz      short loc_180042DA1
0x180042d72  movzx   eax, word ptr [rdi+rbx]
0x180042d76  mov     [rsp+54h], ax
0x180042d7b  mov     eax, [rdi+rbx+4]
0x180042d7f  mov     dword ptr [rbp+360h+var_3A0], eax
0x180042d82  lea     rax, [rsp+54h]
0x180042d87  mov     [rsp+460h+var_438], rax
0x180042d8c  lea     rax, [rbp+360h+var_3A0]
0x180042d90  mov     qword ptr [rsp+460h+var_440], rax
0x180042d95  lea     rdx, word_18008CF32
0x180042d9c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &)
0x180042da1  mov     eax, cs:dword_18009A310
0x180042da7  cmp     eax, 5
0x180042daa  jbe     short loc_180042E1D
0x180042dac  mov     rdx, 800000000000h
0x180042db6  lea     rcx, dword_18009A310
0x180042dbd  call    _tlgKeywordOn
0x180042dc2  test    al, al
0x180042dc4  jz      short loc_180042E1D
0x180042dc6  lea     rsi, [rbx+2Ch]
0x180042dca  add     rsi, rdi
0x180042dcd  mov     eax, [rsi]
0x180042dcf  mov     dword ptr [rbp+360h+var_3A0], eax
0x180042dd2  mov     eax, [rdi+rbx+4]
0x180042dd6  mov     dword ptr [rbp+360h+var_398], eax
0x180042dd9  movzx   eax, word ptr [rdi+rbx]
0x180042ddd  mov     [rsp+54h], ax
0x180042de2  mov     [rsp+460h+var_3E8], 1000000h
0x180042deb  lea     rax, [rbp+360h+var_3A0]
0x180042def  mov     [rsp+460h+var_428], rax
0x180042df4  lea     rax, [rbp+360h+var_398]
0x180042df8  mov     [rsp+460h+var_430], rax
0x180042dfd  lea     rax, [rsp+54h]
0x180042e02  mov     [rsp+460h+var_438], rax
0x180042e07  lea     rax, [rsp+460h+var_3E8]
0x180042e0c  mov     qword ptr [rsp+460h+var_440], rax
0x180042e11  lea     rdx, qword_18008CEE0
0x180042e18  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180042e1d  test    r14, r14
0x180042e20  jz      short loc_180042E46
0x180042e22  mov     eax, [rsi]
0x180042e24  mov     dword ptr [rsp+460h+var_438], eax; unsigned int
0x180042e28  mov     [rsp+460h+var_440], 0; int
0x180042e30  mov     r9d, [rdi+rbx+4]; unsigned int
0x180042e35  movzx   r8d, word ptr [rdi+rbx]; unsigned __int16
0x180042e3a  lea     rdx, [rbp+360h+var_3C0]; struct _GUID *
0x180042e3e  mov     rcx, r14; this
0x180042e41  call    ?AddRecoveryEvent@RecoveryTelemetery@@QEAAXAEBU_GUID@@GKKK@Z; RecoveryTelemetery::AddRecoveryEvent(_GUID const &,ushort,ulong,ulong,ulong)
0x180042e46  test    r12d, r12d
0x180042e49  jnz     short loc_180042E8A
0x180042e4b  test    r13d, r13d
0x180042e4e  jz      short loc_180042E8A
0x180042e50  movzx   eax, word ptr [rdi+rbx]
0x180042e54  mov     ecx, 601Ch
0x180042e59  sub     ax, cx
0x180042e5c  mov     rsi, [rsp+460h+lpMem]
0x180042e61  cmp     ax, 36h ; '6'
0x180042e65  ja      short loc_180042E8F
0x180042e67  mov     rcx, 64000280000001h
0x180042e71  bt      rcx, rax
0x180042e75  jnb     short loc_180042E8F
0x180042e77  cmp     [rsi+8], r12d
0x180042e7b  jnz     short loc_180042E8F
0x180042e7d  call    ?AttemptTpmAutoReseal@@YAJXZ; AttemptTpmAutoReseal(void)
0x180042e82  mov     r12d, 1
0x180042e88  jmp     short loc_180042E8F
0x180042e8a  mov     rsi, [rsp+460h+lpMem]
0x180042e8f  cmp     dword ptr [rsp+460h+var_3F8], 0
0x180042e94  jnz     short loc_180042EB9
0x180042e96  mov     eax, 6053h
0x180042e9b  cmp     [rdi+rbx], ax
0x180042e9f  jz      short loc_180042EAC
0x180042ea1  mov     eax, 6060h
0x180042ea6  cmp     [rdi+rbx], ax
0x180042eaa  jnz     short loc_180042EB9
0x180042eac  call    ?AttemptProtectorRecovery@@YAJXZ; AttemptProtectorRecovery(void)
0x180042eb1  mov     dword ptr [rsp+460h+var_3F8], 1
0x180042eb9  mov     eax, 604Ch
0x180042ebe  cmp     [rdi+rbx], ax
0x180042ec2  jnz     short loc_180042EE0
0x180042ec4  mov     r8d, 1
0x180042eca  mov     dword ptr [rsp+460h+var_3F8+4], r8d
0x180042ecf  movups  xmm6, xmmword ptr [rdi+rbx+0Ch]
0x180042ed4  movups  xmm0, xmmword ptr [rdi+rbx+1Ch]
0x180042ed9  movdqu  [rbp+360h+Buf1], xmm0
0x180042ede  jmp     short loc_180042EE5
0x180042ee0  mov     r8d, dword ptr [rsp+460h+var_3F8+4]
  ... truncated ...
```
