# BdeSvcWorkerThread(void *)

- ea: `0x180007d90`
- end: `0x180008b46`
- name: `?BdeSvcWorkerThread@@YAIPEAX@Z`
- size: `3510`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `0`
- callee_count: `33`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180004974`
- `0x180004a54`
- `0x1800053a0`
- `0x180006260`
- `0x1800065b8`
- `0x180006940`
- `0x180007d10`
- `0x180007d90`
- `0x180009c30`
- `0x180009f30`
- `0x180009f60`
- `0x18000a6b0`
- `0x18000a800`
- `0x18000b570`
- `0x18000c268`
- `0x18000c340`
- `0x18001ca60`
- `0x18001d2a0`
- `0x18001de10`
- `0x18001f820`
- `0x180027ca4`
- `0x180029830`
- `0x18002a2e0`
- `0x18002a5fc`
- `0x18002a774`
- `0x18002afa4`
- `0x18002dc90`
- `0x18003062c`
- `0x180034070`
- `0x180034440`
- `0x18003cd14`
- `0x1800446d4`
- `0x1800486dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007ea3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007e1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007ea3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007ef9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007ef9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800086e5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800086e5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008322`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008391`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008322`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008391`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008690`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008690`

## string_xrefs

- `0x18000830d`: `RDVDenyWriteAccess`
- `0x18000837c`: `RDVDenyWriteAccess`
- `0x18000891e`: `FDVDenyWriteAccess`
- `0x180008936`: `FDVDenyWriteAccess`
- `0x180008a17`: `RDVConfigureBDE`
- `0x180008a32`: `RDVConfigureBDE`
- `0x180008a83`: `Deny_Write`

## pseudocode

```c
__int64 __fastcall BdeSvcWorkerThread(LPCRITICAL_SECTION lpCriticalSection)
{
  PVOID *v2; // rcx
  __int64 **v3; // rsi
  unsigned int v4; // ebx
  PVOID *v5; // rcx
  struct _RTL_CRITICAL_SECTION *v6; // r15
  CBdeSvcSharedState *v7; // rcx
  BdeSvcWorkTracking *v8; // rcx
  unsigned int v9; // r12d
  int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  int v15; // eax
  unsigned int v16; // eax
  int v17; // ebx
  PVOID *v18; // rcx
  __int64 *v19; // rdx
  __int64 v20; // r8
  __int64 InteractiveUserLogonTime; // r13
  __int64 v22; // rbx
  PVOID *v23; // r10
  __int64 v24; // rcx
  __int64 v25; // rdx
  struct _RTL_CRITICAL_SECTION *State; // rax
  int v27; // ebx
  char v28; // r13
  __int64 v29; // rax
  int v30; // eax
  int v31; // eax
  unsigned int ValueW; // eax
  unsigned int v33; // eax
  int v34; // r15d
  __int64 *v35; // rbx
  struct CBdeSvcSharedState *v36; // r12
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rcx
  bool v40; // zf
  _QWORD *v41; // r9
  _QWORD *v42; // r9
  _QWORD *v43; // rdx
  _QWORD *v44; // r9
  _QWORD *v45; // r8
  _QWORD *v46; // r9
  _QWORD *v47; // r8
  _QWORD *v48; // r9
  void *DebugInfo; // rax
  _QWORD *v50; // r9
  struct _RTL_CRITICAL_SECTION *v51; // rax
  struct _RTL_CRITICAL_SECTION *v52; // rbx
  __int64 j; // rax
  __int64 v54; // rax
  __int64 i; // rax
  __int64 v56; // [rsp+0h] [rbp-108h] BYREF
  char v57[4]; // [rsp+40h] [rbp-C8h] BYREF
  int v58[3]; // [rsp+44h] [rbp-C4h] BYREF
  LPCRITICAL_SECTION lpCriticalSectiona; // [rsp+50h] [rbp-B8h]
  unsigned int v60; // [rsp+58h] [rbp-B0h]
  __int64 **v61; // [rsp+60h] [rbp-A8h] BYREF
  struct _RTL_CRITICAL_SECTION *v62; // [rsp+68h] [rbp-A0h]
  unsigned int v63; // [rsp+70h] [rbp-98h]
  struct _RTL_CRITICAL_SECTION *v64; // [rsp+78h] [rbp-90h]
  _BYTE v65[32]; // [rsp+80h] [rbp-88h] BYREF
  int pvData; // [rsp+A0h] [rbp-68h] BYREF
  DWORD pcbData[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v68; // [rsp+B0h] [rbp-58h] BYREF
  _QWORD Src[4]; // [rsp+B8h] [rbp-50h] BYREF

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v68 = 0;
  v3 = 0;
  v61 = 0;
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x20) != 0 )
    WPP_SF_(v2[2], 10, WPP_0854554bfb733ed1d50063ff3037042d_Traceguids);
  EnterCriticalSection(&CBdeSvcSharedState::sm_acsRefCountLock);
  if ( CBdeSvcSharedState::sm_dwRefCount )
  {
    v4 = ++CBdeSvcSharedState::sm_dwRefCount;
LABEL_7:
    v5 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_8;
  }
  v51 = (struct _RTL_CRITICAL_SECTION *)LocalAlloc(0x40u, 0x30u);
  v52 = v51;
  if ( v51 )
  {
    InitializeCriticalSection(v51);
    v52[1].DebugInfo = 0;
    CBdeSvcSharedState::sm_pState = v52;
    CBdeSvcSharedState::sm_dwRefCount = 1;
    v4 = 1;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_8;
  }
  v4 = 0;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_11;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_0854554bfb733ed1d50063ff3037042d_Traceguids);
    goto LABEL_7;
  }
LABEL_8:
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x20) != 0 )
    WPP_SF_(v5[2], 12, WPP_0854554bfb733ed1d50063ff3037042d_Traceguids);
LABEL_11:
  LeaveCriticalSection(&CBdeSvcSharedState::sm_acsRefCountLock);
  v63 = v4;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_0854554bfb733ed1d50063ff3037042d_Traceguids);
  v6 = 0;
  v62 = 0;
  v64 = &CBdeSvcSharedState::sm_acsRefCountLock;
  EnterCriticalSection(&CBdeSvcSharedState::sm_acsRefCountLock);
  if ( CBdeSvcSharedState::sm_pState )
  {
    if ( !CBdeSvcSharedState::InitializeLaunchUiList(v7) )
      v6 = (struct _RTL_CRITICAL_SECTION *)CBdeSvcSharedState::sm_pState;
    v62 = v6;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_0854554bfb733ed1d50063ff3037042d_Traceguids);
  LeaveCriticalSection(&CBdeSvcSharedState::sm_acsRefCountLock);
  if ( !v6 )
  {
    v9 = -1;
    goto LABEL_21;
  }
  BdeSvcProcessWorkerQueue(lpCriticalSection);
  v11 = AllocVolumeMap(&v61);
  v3 = v61;
  if ( v11 )
  {
    v9 = -1;
    goto LABEL_21;
  }
  v9 = 0;
  v60 = 0;
  v12 = EnumVolumes((__int64)v61, 1, &v68, 1, 0);
  if ( v12 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v12);
  v15 = ResumeWithOSVolume::CheckOSVolumeAndResumeFDVs(v3, v13, v14);
  if ( v15 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      155,
      &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
      (unsigned int)v15);
  BdeSvcManageGpNotificationThread((void ***)v3);
  if ( v68 )
  {
    CheckForKernelModeEventsToProcess(v3);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
    v57[0] = 0;
    v16 = TryAutoUnlockVolumes(v3, v57);
    v17 = v16;
    if ( v16 )
    {
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v16);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v17 < 0 )
      {
LABEL_37:
        if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x20) != 0 )
          WPP_SF_(v18[2], 119, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
        InteractiveUserLogonTime = GetInteractiveUserLogonTime();
        v64 = (struct _RTL_CRITICAL_SECTION *)InteractiveUserLogonTime;
        if ( InteractiveUserLogonTime )
        {
          v62 = v6;
          v22 = **v3;
          *(_QWORD *)pcbData = v22;
          v23 = (PVOID *)WPP_GLOBAL_Control;
          while ( 1 )
          {
            if ( (__int64 *)v22 == *v3 )
            {
              CBdeSvcSharedState::ProcessLaunchUiRequests(v6);
              goto LABEL_21;
            }
            if ( !*(_DWORD *)(v22 + 88) || !*(_DWORD *)(v22 + 96) || *(int *)(v22 + 64) < 0 )
              goto LABEL_43;
            v29 = *(_QWORD *)(v22 + 80);
            if ( v29 < InteractiveUserLogonTime )
            {
              if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 8) != 0 )
              {
                v41 = (_QWORD *)(v22 + 32);
                if ( *(_QWORD *)(v22 + 56) > 7u )
                  v41 = (_QWORD *)*v41;
                WPP_SF_Sii((unsigned int)v23[2], 158, v20, (_DWORD)v41, v29, InteractiveUserLogonTime);
                v23 = (PVOID *)WPP_GLOBAL_Control;
              }
              goto LABEL_43;
            }
            if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 8) != 0 )
            {
              v42 = (_QWORD *)(v22 + 32);
              if ( *(_QWORD *)(v22 + 56) > 7u )
                v42 = (_QWORD *)*v42;
              WPP_SF_Sii((unsigned int)v23[2], 159, v20, (_DWORD)v42, v29, InteractiveUserLogonTime);
            }
            v30 = *(_DWORD *)(v22 + 64);
            if ( (v30 & 0x800) != 0 && (v30 & 0x20000000) == 0 )
            {
              try
              {
                v43 = (_QWORD *)(v22 + 104);
                if ( *(_QWORD *)(v22 + 128) > 7u )
                  v43 = (_QWORD *)*v43;
                std::wstring::wstring(Src, v43);
                std::wstring::wstring(v65, L" -toast");
                std::wstring::_Append<unsigned short>(Src);
                std::wstring::~wstring((__int64)v65);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                {
                  v44 = (_QWORD *)(v22 + 32);
                  if ( *(_QWORD *)(v22 + 56) > 7u )
                    v44 = (_QWORD *)*v44;
                  WPP_SF_S(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    160,
                    &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
                    v44);
                }
                v45 = Src;
                if ( Src[3] > 7u )
                  v45 = (_QWORD *)Src[0];
                CBdeSvcSharedState::AddLaunchUiRequest(v6, 1, v45);
                std::wstring::~wstring((__int64)Src);
              }
              catch ( ... )
              {
                v19 = &v56;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
                v9 = 0;
                v6 = v62;
                InteractiveUserLogonTime = (__int64)v64;
                v3 = v61;
                v22 = *(_QWORD *)pcbData;
              }
LABEL_87:
              v23 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_43;
            }
            if ( !*(_BYTE *)(CBdeSvcDE::GetSupportLevel(v58) + 4) )
              goto LABEL_87;
            v31 = *(_DWORD *)(v22 + 64);
            if ( (v31 & 0x1000) != 0 )
            {
              v23 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                goto LABEL_43;
              v50 = (_QWORD *)(v22 + 32);
              if ( *(_QWORD *)(v22 + 56) > 7u )
                v50 = (_QWORD *)*v50;
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 166, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v50);
              goto LABEL_87;
            }
            if ( (v31 & 0x400000) != 0 )
              break;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              v46 = (_QWORD *)(v22 + 32);
              if ( *(_QWORD *)(v22 + 56) > 7u )
                v46 = (_QWORD *)*v46;
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 162, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v46);
            }
            if ( BdeSvcGetGpValue(L"Software\\Policies\\Microsoft\\FVE", L"FDVDenyWriteAccess") != 1
              && BdeSvcGetGpValue(L"System\\CurrentControlSet\\Policies\\Microsoft\\FVE", L"FDVDenyWriteAccess") != 1 )
            {
              goto LABEL_87;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 163, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
            v47 = (_QWORD *)(v22 + 104);
            if ( *(_QWORD *)(v22 + 128) > 7u )
              v47 = (_QWORD *)*v47;
            CBdeSvcSharedState::AddLaunchUiRequest(v6, 3, v47);
            v23 = (PVOID *)WPP_GLOBAL_Control;
LABEL_43:
            v24 = *(_QWORD *)(v22 + 16);
            if ( *(_BYTE *)(v24 + 25) )
            {
              for ( i = *(_QWORD *)(v22 + 8); !*(_BYTE *)(i + 25); i = *(_QWORD *)(i + 8) )
              {
                if ( v22 != *(_QWORD *)(i + 16) )
                  break;
                v22 = i;
              }
              v22 = i;
              *(_QWORD *)pcbData = i;
            }
            else
            {
              v22 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<CSessionState>>>>::_Min(
                      v24,
                      v19,
                      v20);
              *(_QWORD *)pcbData = v22;
            }
          }
          v23 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v48 = (_QWORD *)(v22 + 32);
            if ( *(_QWORD *)(v22 + 56) > 7u )
              v48 = (_QWORD *)*v48;
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 164, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v48);
            v23 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( (*(_DWORD *)(v22 + 152) & 0x1000000) != 0 )
            goto LABEL_43;
          pvData = 0;
          pcbData[0] = 4;
          ValueW = RegGetValueW(
                     HKEY_LOCAL_MACHINE,
                     L"Software\\Policies\\Microsoft\\FVE",
                     L"RDVDenyWriteAccess",
                     0x10u,
                     0,
                     &pvData,
                     pcbData);
          if ( ValueW )
          {
            if ( ValueW != 2
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                70,
                &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids,
                ValueW);
            }
          }
          else if ( pvData == 1 )
          {
LABEL_187:
            if ( !BdeSvcGetGpValue(L"Software\\Policies\\Microsoft\\FVE", L"RDVConfigureBDE") )
              goto LABEL_87;
            if ( !BdeSvcGetGpValue(L"System\\CurrentControlSet\\Policies\\Microsoft\\FVE", L"RDVConfigureBDE") )
              goto LABEL_87;
            if ( !BdeSvcGetGpValue(L"Software\\Policies\\Microsoft\\FVE", L"RDVAllowBDE") )
              goto LABEL_87;
            if ( !BdeSvcGetGpValue(L"System\\CurrentControlSet\\Policies\\Microsoft\\FVE", L"RDVAllowBDE") )
              goto LABEL_87;
            if ( BdeSvcGetGpValue(
                   L"Software\\Policies\\Microsoft\\Windows\\RemovableStorageDevices\\{53f5630d-b6bf-11d0-94f2-00a0c91efb8b}",
                   L"Deny_Write") == 1 )
              goto LABEL_87;
            lpCriticalSectiona = (LPCRITICAL_SECTION)(v22 + 104);
            v54 = std::wstring::wstring(v65, v22 + 104);
            if ( !(unsigned int)BdeSvcIsMediaPresent(v54) )
              goto LABEL_87;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
            DebugInfo = lpCriticalSectiona;
            if ( *(_QWORD *)(v22 + 128) > 7u )
              DebugInfo = lpCriticalSectiona->DebugInfo;
            CBdeSvcSharedState::AddLaunchUiRequest(v6, 3, DebugInfo);
            v23 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_43;
          }
          pvData = 0;
          pcbData[0] = 4;
          v33 = RegGetValueW(
                  HKEY_LOCAL_MACHINE,
                  L"System\\CurrentControlSet\\Policies\\Microsoft\\FVE",
                  L"RDVDenyWriteAccess",
                  0x10u,
                  0,
                  &pvData,
                  pcbData);
          if ( v33 )
          {
            if ( v33 != 2 )
            {
              v23 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_43;
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids, v33);
            }
            goto LABEL_87;
          }
          if ( pvData != 1 )
            goto LABEL_87;
          goto LABEL_187;
        }
        v8 = (BdeSvcWorkTracking *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v25 = 157;
LABEL_52:
          WPP_SF_(*((_QWORD *)v8 + 2), v25, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
          goto LABEL_21;
        }
        goto LABEL_21;
      }
    }
    else
    {
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x20) != 0 )
      WPP_SF_(v18[2], 94, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
    pcbData[0] = CBdeSvcSharedState::Initialize();
    State = (struct _RTL_CRITICAL_SECTION *)CBdeSvcSharedState::GetState();
    lpCriticalSectiona = State;
    if ( State )
    {
      v34 = 0;
      v58[0] = 0;
      v35 = (__int64 *)**v3;
      v36 = (struct CBdeSvcSharedState *)State;
      while ( v35 != *v3 )
      {
        pvData = 0;
        v58[0] = AddLaunchRequestForFveNotifyIfNeeded((const struct VolumeEntry *)(v35 + 8), v36, 0, &pvData);
        if ( v58[0] >= 0 && pvData )
          v34 = 1;
        v39 = v35[2];
        if ( *(_BYTE *)(v39 + 25) )
        {
          for ( j = v35[1]; !*(_BYTE *)(j + 25); j = *(_QWORD *)(j + 8) )
          {
            if ( v35 != *(__int64 **)(j + 16) )
              break;
            v35 = (__int64 *)j;
          }
          v35 = (__int64 *)j;
        }
        else
        {
          v35 = (__int64 *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<CSessionState>>>>::_Min(
                             v39,
                             v37,
                             v38);
        }
      }
      v40 = v34 == 0;
      v6 = v62;
      v9 = v60;
      if ( !v40 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
        v28 = 1;
        CBdeSvcSharedState::ProcessLaunchUiRequests(lpCriticalSectiona);
        v18 = (PVOID *)WPP_GLOBAL_Control;
        v27 = v58[0];
        goto LABEL_65;
      }
      v27 = v58[0];
    }
    else
    {
      v27 = -2147467259;
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_64;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, 2147500037LL);
    }
    v18 = (PVOID *)WPP_GLOBAL_Control;
LABEL_64:
    v28 = 0;
LABEL_65:
    if ( pcbData[0] )
    {
      CBdeSvcSharedState::Cleanup();
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x20) != 0 )
    {
      WPP_SF_(v18[2], 97, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !v27 )
      goto LABEL_88;
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x40) != 0 )
    {
      WPP_SF_d(v18[2], 118, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, (unsigned int)v27);
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v27 >= 0 )
    {
LABEL_88:
      if ( v57[0] || v28 )
      {
        BdeSvcSetProcessVolumesOnLogon(1);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
      else
      {
        BdeSvcSetProcessVolumesOnLogon(0);
        v18 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    goto LABEL_37;
  }
  v8 = (BdeSvcWorkTracking *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v25 = 156;
    goto LABEL_52;
  }
LABEL_21:
  if ( v63 )
    CBdeSvcSharedState::Cleanup();
  if ( v3 )
  {
    std::_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>(v3);
    operator delete(v3, (const struct std::nothrow_t *)0x10);
  }
  BdeSvcWorkTracking::FinishWorkImpl(v8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  return v9;
}

```

## disassembly

```asm
0x180007d90  mov     [rsp+arg_8], rbx
0x180007d95  mov     [rsp+arg_10], rsi
0x180007d9a  push    rdi
0x180007d9b  push    r12
0x180007d9d  push    r13
0x180007d9f  push    r14
0x180007da1  push    r15
0x180007da3  sub     rsp, 0E0h
0x180007daa  mov     rax, cs:__security_cookie
0x180007db1  xor     rax, rsp
0x180007db4  mov     [rsp+108h+var_30], rax
0x180007dbc  mov     r12, rcx
0x180007dbf  lea     rdi, WPP_GLOBAL_Control
0x180007dc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180007dcd  cmp     rcx, rdi
0x180007dd0  jz      short loc_180007DF4
0x180007dd2  test    byte ptr [rcx+1Ch], 20h
0x180007dd6  jz      short loc_180007DF4
0x180007dd8  mov     edx, 99h
0x180007ddd  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180007de4  mov     rcx, [rcx+10h]
0x180007de8  call    WPP_SF_
0x180007ded  mov     rcx, cs:WPP_GLOBAL_Control
0x180007df4  xor     r14d, r14d
0x180007df7  mov     [rsp+108h+var_58], r14
0x180007dff  mov     esi, r14d
0x180007e02  mov     [rsp+108h+var_A8], r14
0x180007e07  cmp     rcx, rdi
0x180007e0a  jnz     loc_1800080C4
0x180007e10  lea     r15, ?sm_acsRefCountLock@CBdeSvcSharedState@@0VCAutoCS@@A; CAutoCS CBdeSvcSharedState::sm_acsRefCountLock
0x180007e17  mov     rcx, r15; lpCriticalSection
0x180007e1a  call    cs:__imp_EnterCriticalSection
0x180007e21  nop     dword ptr [rax+rax+00h]
0x180007e26  mov     ebx, cs:?sm_dwRefCount@CBdeSvcSharedState@@0KA; ulong CBdeSvcSharedState::sm_dwRefCount
0x180007e2c  test    ebx, ebx
0x180007e2e  jz      loc_180008686
0x180007e34  inc     ebx
0x180007e36  mov     cs:?sm_dwRefCount@CBdeSvcSharedState@@0KA, ebx; ulong CBdeSvcSharedState::sm_dwRefCount
0x180007e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e43  mov     r13d, 1
0x180007e49  cmp     rcx, rdi
0x180007e4c  jz      short loc_180007E69
0x180007e4e  test    byte ptr [rcx+1Ch], 20h
0x180007e52  jz      short loc_180007E69
0x180007e54  mov     edx, 0Ch
0x180007e59  lea     r8, WPP_0854554bfb733ed1d50063ff3037042d_Traceguids
0x180007e60  mov     rcx, [rcx+10h]
0x180007e64  call    WPP_SF_
0x180007e69  mov     rcx, r15; lpCriticalSection
0x180007e6c  call    cs:__imp_LeaveCriticalSection
0x180007e73  nop     dword ptr [rax+rax+00h]
0x180007e78  mov     [rsp+108h+var_98], ebx
0x180007e7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e83  cmp     rcx, rdi
0x180007e86  jnz     loc_1800080E8
0x180007e8c  mov     r15, r14
0x180007e8f  mov     [rsp+108h+var_A0], r14
0x180007e94  lea     rbx, ?sm_acsRefCountLock@CBdeSvcSharedState@@0VCAutoCS@@A; CAutoCS CBdeSvcSharedState::sm_acsRefCountLock
0x180007e9b  mov     [rsp+108h+var_90], rbx
0x180007ea0  mov     rcx, rbx; lpCriticalSection
0x180007ea3  call    cs:__imp_EnterCriticalSection
0x180007eaa  nop     dword ptr [rax+rax+00h]
0x180007eaf  nop
0x180007eb0  cmp     cs:?sm_pState@CBdeSvcSharedState@@0PEAV1@EA, 0; CBdeSvcSharedState * CBdeSvcSharedState::sm_pState
0x180007eb8  jz      short loc_180007ECE
0x180007eba  call    ?InitializeLaunchUiList@CBdeSvcSharedState@@QEAAKXZ; CBdeSvcSharedState::InitializeLaunchUiList(void)
0x180007ebf  test    eax, eax
0x180007ec1  cmovz   r15, cs:?sm_pState@CBdeSvcSharedState@@0PEAV1@EA; CBdeSvcSharedState * CBdeSvcSharedState::sm_pState
0x180007ec9  mov     [rsp+108h+var_A0], r15
0x180007ece  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ed5  cmp     rcx, rdi
0x180007ed8  jz      short loc_180007EF6
0x180007eda  test    byte ptr [rcx+1Ch], 20h
0x180007ede  jz      short loc_180007EF6
0x180007ee0  mov     edx, 10h
0x180007ee5  lea     r8, WPP_0854554bfb733ed1d50063ff3037042d_Traceguids
0x180007eec  mov     rcx, [rcx+10h]
0x180007ef0  call    WPP_SF_
0x180007ef5  nop
0x180007ef6  mov     rcx, rbx; lpCriticalSection
0x180007ef9  call    cs:__imp_LeaveCriticalSection
0x180007f00  nop     dword ptr [rax+rax+00h]
0x180007f05  test    r15, r15
0x180007f08  jnz     short loc_180007F7B
0x180007f0a  mov     r12d, 0FFFFFFFFh
0x180007f10  cmp     [rsp+108h+var_98], 0
0x180007f15  jnz     loc_180008248
0x180007f1b  test    rsi, rsi
0x180007f1e  jz      short loc_180007F35
0x180007f20  mov     rcx, rsi
0x180007f23  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>(void)
0x180007f28  mov     edx, 10h; struct std::nothrow_t *
0x180007f2d  mov     rcx, rsi; void *
0x180007f30  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007f35  call    ?FinishWorkImpl@BdeSvcWorkTracking@@AEAAXXZ; BdeSvcWorkTracking::FinishWorkImpl(void)
0x180007f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f41  cmp     rcx, rdi
0x180007f44  jnz     loc_180008883
0x180007f4a  mov     eax, r12d
0x180007f4d  mov     rcx, [rsp+108h+var_30]
0x180007f55  xor     rcx, rsp; StackCookie
0x180007f58  call    __security_check_cookie
0x180007f5d  lea     r11, [rsp+108h+var_28]
0x180007f65  mov     rbx, [r11+38h]
0x180007f69  mov     rsi, [r11+40h]
0x180007f6d  mov     rsp, r11
0x180007f70  pop     r15
0x180007f72  pop     r14
0x180007f74  pop     r13
0x180007f76  pop     r12
0x180007f78  pop     rdi
0x180007f79  retn
0x180007f7b  mov     rcx, r12; lpCriticalSection
0x180007f7e  call    ?BdeSvcProcessWorkerQueue@@YAXPEAU_BDESVC_SVC_CTL_INFO@@@Z; BdeSvcProcessWorkerQueue(_BDESVC_SVC_CTL_INFO *)
0x180007f83  lea     rcx, [rsp+108h+var_A8]
0x180007f88  call    ?AllocVolumeMap@@YAKPEAPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@@Z; AllocVolumeMap(std::map<std::wstring,VolumeEntry> * *)
0x180007f8d  mov     rsi, [rsp+108h+var_A8]
0x180007f92  test    eax, eax
0x180007f94  jnz     loc_1800083DB
0x180007f9a  mov     r12d, r14d
0x180007f9d  mov     [rsp+108h+var_B0], r14d
0x180007fa2  mov     byte ptr [rsp+108h+pdwType], r12b
0x180007fa7  mov     r9b, 1
0x180007faa  lea     r8, [rsp+108h+var_58]
0x180007fb2  movzx   edx, r9b
0x180007fb6  mov     rcx, rsi
0x180007fb9  call    ?EnumVolumes@@YAKPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@_NPEA_K11@Z; EnumVolumes(std::map<std::wstring,VolumeEntry> *,bool,unsigned __int64 *,bool,bool)
0x180007fbe  test    eax, eax
0x180007fc0  jnz     loc_180008718
0x180007fc6  mov     rcx, rsi
0x180007fc9  call    ?CheckOSVolumeAndResumeFDVs@ResumeWithOSVolume@@SAJPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@@Z; ResumeWithOSVolume::CheckOSVolumeAndResumeFDVs(std::map<std::wstring,VolumeEntry> *)
0x180007fce  test    eax, eax
0x180007fd0  js      loc_18000874F
0x180007fd6  mov     rcx, rsi
0x180007fd9  call    ?BdeSvcManageGpNotificationThread@@YAKPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@@Z; BdeSvcManageGpNotificationThread(std::map<std::wstring,VolumeEntry> *)
0x180007fde  cmp     [rsp+108h+var_58], r12
0x180007fe6  jz      loc_180008140
0x180007fec  mov     rcx, rsi
0x180007fef  call    ?CheckForKernelModeEventsToProcess@@YAXPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@@Z; CheckForKernelModeEventsToProcess(std::map<std::wstring,VolumeEntry> *)
0x180007ff4  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ffb  cmp     rcx, rdi
0x180007ffe  jz      short loc_18000801B
0x180008000  test    byte ptr [rcx+1Ch], 20h
0x180008004  jz      short loc_18000801B
0x180008006  mov     edx, 74h ; 't'
0x18000800b  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180008012  mov     rcx, [rcx+10h]
0x180008016  call    WPP_SF_
0x18000801b  mov     [rsp+108h+var_C8], r12b
0x180008020  lea     rdx, [rsp+108h+var_C8]
0x180008025  mov     rcx, rsi
0x180008028  call    ?TryAutoUnlockVolumes@@YAJPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@PEA_N@Z; TryAutoUnlockVolumes(std::map<std::wstring,VolumeEntry> *,bool *)
0x18000802d  mov     ebx, eax
0x18000802f  test    eax, eax
0x180008031  jz      loc_180008185
0x180008037  mov     rcx, cs:WPP_GLOBAL_Control
0x18000803e  cmp     rcx, rdi
0x180008041  jnz     loc_180008786
0x180008047  test    ebx, ebx
0x180008049  jns     loc_18000818C
0x18000804f  cmp     rcx, rdi
0x180008052  jnz     loc_180008161
0x180008058  call    ?GetInteractiveUserLogonTime@@YA_JXZ; GetInteractiveUserLogonTime(void)
0x18000805d  mov     r13, rax
0x180008060  mov     [rsp+108h+var_90], rax
0x180008065  test    rax, rax
0x180008068  jz      loc_18000810C
0x18000806e  mov     [rsp+108h+var_A0], r15
0x180008073  mov     rbx, [rsi]
0x180008076  mov     rbx, [rbx]
0x180008079  mov     qword ptr [rsp+108h+var_60], rbx
0x180008081  mov     r10, cs:WPP_GLOBAL_Control
0x180008088  cmp     rbx, [rsi]
0x18000808b  jnz     short loc_18000809A
0x18000808d  mov     rcx, r15; lpCriticalSection
0x180008090  call    ?ProcessLaunchUiRequests@CBdeSvcSharedState@@QEAAXXZ; CBdeSvcSharedState::ProcessLaunchUiRequests(void)
0x180008095  jmp     loc_180007F10
0x18000809a  cmp     dword ptr [rbx+58h], 0
0x18000809e  jnz     loc_180008252
0x1800080a4  mov     rcx, [rbx+10h]
0x1800080a8  cmp     byte ptr [rcx+19h], 0
0x1800080ac  jnz     loc_180008B19
0x1800080b2  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@VCSessionState@@@std@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@VCSessionState@@@std@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<CSessionState>>>>::_Min(std::_Tree_node<std::pair<ulong const,std::shared_ptr<CSessionState>>,void *> *)
0x1800080b7  mov     rbx, rax
0x1800080ba  mov     qword ptr [rsp+108h+var_60], rax
0x1800080c2  jmp     short loc_180008088
0x1800080c4  test    byte ptr [rcx+1Ch], 20h
0x1800080c8  jz      loc_180007E10
0x1800080ce  mov     edx, 0Ah
0x1800080d3  lea     r8, WPP_0854554bfb733ed1d50063ff3037042d_Traceguids
0x1800080da  mov     rcx, [rcx+10h]
0x1800080de  call    WPP_SF_
0x1800080e3  jmp     loc_180007E10
0x1800080e8  test    byte ptr [rcx+1Ch], 20h
0x1800080ec  jz      loc_180007E8C
0x1800080f2  mov     edx, 0Fh
0x1800080f7  lea     r8, WPP_0854554bfb733ed1d50063ff3037042d_Traceguids
0x1800080fe  mov     rcx, [rcx+10h]
0x180008102  call    WPP_SF_
0x180008107  jmp     loc_180007E8C
0x18000810c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008113  cmp     rcx, rdi
0x180008116  jz      loc_180007F10
0x18000811c  test    byte ptr [rcx+1Ch], 8
0x180008120  jz      loc_180007F10
0x180008126  mov     edx, 9Dh
0x18000812b  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180008132  mov     rcx, [rcx+10h]
0x180008136  call    WPP_SF_
0x18000813b  jmp     loc_180007F10
0x180008140  mov     rcx, cs:WPP_GLOBAL_Control
0x180008147  cmp     rcx, rdi
0x18000814a  jz      loc_180007F10
0x180008150  test    byte ptr [rcx+1Ch], 8
0x180008154  jz      loc_180007F10
0x18000815a  mov     edx, 9Ch
0x18000815f  jmp     short loc_18000812B
0x180008161  test    byte ptr [rcx+1Ch], 20h
0x180008165  jz      loc_180008058
0x18000816b  mov     edx, 77h ; 'w'
0x180008170  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180008177  mov     rcx, [rcx+10h]
0x18000817b  call    WPP_SF_
0x180008180  jmp     loc_180008058
0x180008185  mov     rcx, cs:WPP_GLOBAL_Control
0x18000818c  cmp     rcx, rdi
0x18000818f  jz      short loc_1800081AC
0x180008191  test    byte ptr [rcx+1Ch], 20h
0x180008195  jz      short loc_1800081AC
0x180008197  mov     edx, 5Eh ; '^'
0x18000819c  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x1800081a3  mov     rcx, [rcx+10h]
0x1800081a7  call    WPP_SF_
0x1800081ac  call    ?Initialize@CBdeSvcSharedState@@SAKXZ; CBdeSvcSharedState::Initialize(void)
0x1800081b1  mov     [rsp+108h+var_60], eax
0x1800081b8  call    ?GetState@CBdeSvcSharedState@@SAPEAV1@XZ; CBdeSvcSharedState::GetState(void)
0x1800081bd  mov     [rsp+108h+lpCriticalSection], rax
0x1800081c2  test    rax, rax
0x1800081c5  jnz     loc_1800083FC
0x1800081cb  mov     ebx, 80004005h
0x1800081d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800081d7  cmp     rcx, rdi
0x1800081da  jnz     loc_1800087B4
0x1800081e0  xor     r13b, r13b
0x1800081e3  cmp     [rsp+108h+var_60], 0
0x1800081eb  jz      short loc_1800081F9
0x1800081ed  call    ?Cleanup@CBdeSvcSharedState@@SAKXZ; CBdeSvcSharedState::Cleanup(void)
0x1800081f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800081f9  cmp     rcx, rdi
0x1800081fc  jnz     short loc_180008224
0x1800081fe  test    ebx, ebx
0x180008200  jnz     loc_1800083E6
0x180008206  cmp     [rsp+108h+var_C8], 0
0x18000820b  jz      loc_1800083BF
0x180008211  mov     cl, 1; bool
0x180008213  call    ?BdeSvcSetProcessVolumesOnLogon@@YAX_N@Z; BdeSvcSetProcessVolumesOnLogon(bool)
0x180008218  mov     rcx, cs:WPP_GLOBAL_Control
0x18000821f  jmp     loc_18000804F
0x180008224  test    byte ptr [rcx+1Ch], 20h
0x180008228  jz      short loc_1800081FE
0x18000822a  mov     edx, 61h ; 'a'
0x18000822f  lea     r8, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180008236  mov     rcx, [rcx+10h]
0x18000823a  call    WPP_SF_
0x18000823f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008246  jmp     short loc_1800081FE
0x180008248  call    ?Cleanup@CBdeSvcSharedState@@SAKXZ; CBdeSvcSharedState::Cleanup(void)
0x18000824d  jmp     loc_180007F1B
0x180008252  cmp     dword ptr [rbx+60h], 0
0x180008256  jz      loc_1800080A4
0x18000825c  cmp     dword ptr [rbx+40h], 0
0x180008260  jl      loc_1800080A4
0x180008266  mov     rax, [rbx+50h]
0x18000826a  cmp     rax, r13
0x18000826d  jl      loc_1800088A7
0x180008273  cmp     r10, rdi
0x180008276  jnz     loc_1800088C0
0x18000827c  mov     eax, [rbx+40h]
0x18000827f  bt      eax, 0Bh
0x180008283  jb      loc_1800088D0
0x180008289  lea     rcx, [rsp+108h+var_C4]
0x18000828e  call    ?GetSupportLevel@CBdeSvcDE@@SA?AVDeviceEncryptionSupportLevel@@XZ; CBdeSvcDE::GetSupportLevel(void)
0x180008293  cmp     byte ptr [rax+4], 0
0x180008297  jz      loc_1800083B3
0x18000829d  mov     eax, [rbx+40h]
0x1800082a0  bt      eax, 0Ch
0x1800082a4  jb      loc_180008AF9
0x1800082aa  bt      eax, 16h
0x1800082ae  jnb     loc_180008908
0x1800082b4  mov     r10, cs:WPP_GLOBAL_Control
0x1800082bb  cmp     r10, rdi
0x1800082be  jnz     loc_180008986
0x1800082c4  mov     eax, [rbx+98h]
0x1800082ca  bt      rax, 18h
0x1800082cf  jb      loc_1800080A4
0x1800082d5  mov     [rsp+108h+var_68], r14d
0x1800082dd  mov     [rsp+108h+var_60], 4
0x1800082e8  lea     rax, [rsp+108h+var_60]
0x1800082f0  mov     [rsp+108h+pcbData], rax; pcbData
0x1800082f5  lea     rax, [rsp+108h+var_68]
  ... truncated ...
```
