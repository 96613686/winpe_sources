# BdeSvcDeviceEventCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)

- ea: `0x1800090d0`
- end: `0x180009c26`
- name: `?BdeSvcDeviceEventCallback@@YAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z`
- size: `2902`
- prototype: `__int64 __fastcall(__int64, struct _RTL_CRITICAL_SECTION *, unsigned int, __int64, unsigned int dwBytes)`
- caller_count: `0`
- callee_count: `14`
- tags: ``

## callees

- `0x1800090d0`
- `0x180009c30`
- `0x180009f30`
- `0x180009f60`
- `0x180009fd0`
- `0x18000a010`
- `0x18001f500`
- `0x18001f820`
- `0x18002b6ac`
- `0x18002db24`
- `0x180034d10`
- `0x180039284`
- `0x1800448c0`
- `0x180054ce8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000912b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009884`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800099d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000912b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009884`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800099d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800091ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800098ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009a03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800091ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800098ae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009a03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009476`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180009476`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009436`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180009436`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800091a5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800091a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800095ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800095ca`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000955a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009819`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009980`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000955a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009819`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180009980`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009543`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800095b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800097ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009969`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009543`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800095b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800097ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009969`

## string_xrefs

- `0x18000974c`: `InvalidateCache`

## pseudocode

```c
__int64 __fastcall BdeSvcDeviceEventCallback(
        __int64 a1,
        struct _RTL_CRITICAL_SECTION *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int dwBytes)
{
  struct _RTL_CRITICAL_SECTION *v7; // r13
  int v9; // r14d
  HANDLE v10; // rdx
  PVOID *v11; // rcx
  PVOID *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // rdx
  unsigned int v19; // edi
  __int64 v20; // rax
  unsigned int v21; // edx
  __int64 v22; // r8
  int v23; // edx
  __int64 v25; // rdx
  PVOID *v26; // rcx
  __int64 v27; // rdx
  int v28; // eax
  char v29; // di
  int v30; // eax
  HANDLE v31; // rax
  _OWORD *v32; // rax
  void *v33; // rdi
  signed int v34; // eax
  HANDLE v35; // rax
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rax
  unsigned int v39; // eax
  int v40; // ebx
  unsigned int v41; // edi
  HANDLE ProcessHeap; // rax
  _QWORD *v43; // rax
  _QWORD *v44; // rcx
  __int64 v45; // rdx
  HANDLE v46; // rax
  _QWORD *v47; // rax
  int v48; // eax
  _QWORD *v49; // rcx
  __int64 v50; // rdx
  HANDLE v51; // rax
  HANDLE v52; // rax
  const char *v53; // [rsp+28h] [rbp-60h]
  int v54; // [rsp+30h] [rbp-58h]
  LPVOID v55; // [rsp+38h] [rbp-50h] BYREF
  struct _RTL_CRITICAL_SECTION *v56; // [rsp+40h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v7 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
  v9 = 0;
  v54 = 0;
  EnterCriticalSection(&BdeSvcWorkTracking::_svcWorkTracking);
  v10 = hEvent;
  if ( !hEvent )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_17;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_14;
    v25 = 16;
    goto LABEL_98;
  }
  if ( !HIBYTE(word_18009B8E8) )
  {
    if ( !dword_18009B8D8 )
    {
      if ( ++dword_18009B8C8 == 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
          v10 = hEvent;
        }
        SetEvent(v10);
      }
      v9 = 1;
      v54 = 1;
      goto LABEL_13;
    }
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_17;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_14;
    v25 = 18;
LABEL_98:
    WPP_SF_(v11[2], v25, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
LABEL_13:
    v11 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_14;
  }
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_17;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v25 = 17;
    goto LABEL_98;
  }
LABEL_14:
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 0x20) != 0 )
    WPP_SF_(v11[2], 20, &WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids);
LABEL_17:
  LeaveCriticalSection(&BdeSvcWorkTracking::_svcWorkTracking);
  if ( !v9 )
    goto LABEL_62;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_ee35f73b350036074f815e40b51ef636_Traceguids, a3);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 != 6 )
  {
    if ( a3 )
    {
      v41 = a3 - 1;
      if ( !v41 )
      {
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
        {
          WPP_SF_(v12[2], 44, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
          v12 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( *(_DWORD *)a4 )
          goto LABEL_62;
        v36 = *(_QWORD *)(a4 + 8) - *(_QWORD *)&GUID_DEVINTERFACE_VOLUME.Data1;
        if ( !v36 )
          v36 = *(_QWORD *)(a4 + 16) - *(_QWORD *)GUID_DEVINTERFACE_VOLUME.Data4;
        if ( v36 )
          goto LABEL_62;
        if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 8) == 0 )
          goto LABEL_148;
        v37 = 45;
        goto LABEL_147;
      }
      if ( v41 != 4 )
        goto LABEL_62;
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
      {
        WPP_SF_(v12[2], 46, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( *(_DWORD *)a4 != 1 )
        goto LABEL_62;
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
        WPP_SF_(v12[2], 47, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
      ProcessHeap = GetProcessHeap();
      v43 = HeapAlloc(ProcessHeap, 8u, 0x20u);
      v55 = v43;
      if ( v43 )
      {
        *(_DWORD *)v43 = 2;
        v43[1] = 10;
        v43[2] = a1;
        v56 = v7;
        EnterCriticalSection(v7);
        try
        {
          std::list<_BDESVC_WORKER_PARAMS *>::_Emplace<_BDESVC_WORKER_PARAMS * const &>(
            v7[1].OwningThread,
            *(_QWORD *)v7[1].OwningThread,
            &v55);
          v55 = 0;
          LeaveCriticalSection(v7);
        }
        catch ( ... )
        {
          v51 = GetProcessHeap();
          HeapFree(v51, 0, v55);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
          v7 = a2;
          v9 = v54;
          goto LABEL_73;
        }
        goto LABEL_73;
      }
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v45 = 48;
LABEL_140:
        WPP_SF_(v44[2], v45, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
      }
    }
    else
    {
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
      {
        WPP_SF_(v12[2], 39, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( *(_DWORD *)a4 )
        goto LABEL_62;
      v38 = *(_QWORD *)(a4 + 8) - *(_QWORD *)&GUID_DEVINTERFACE_VOLUME.Data1;
      if ( !v38 )
        v38 = *(_QWORD *)(a4 + 16) - *(_QWORD *)GUID_DEVINTERFACE_VOLUME.Data4;
      if ( v38 )
        goto LABEL_62;
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
      {
        WPP_SF_(v12[2], 40, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( dwBytes <= 0x18 )
      {
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
          WPP_SF_d(v12[2], 41, WPP_ee35f73b350036074f815e40b51ef636_Traceguids, dwBytes);
        goto LABEL_62;
      }
      CBdeSvcDE::InvalidateDeviceProtectionStatusCache();
      v46 = GetProcessHeap();
      v47 = HeapAlloc(v46, 8u, dwBytes);
      v55 = v47;
      if ( v47 )
      {
        *(_DWORD *)v47 = 1;
        v47[1] = dwBytes - 24LL;
        memcpy_0(v47 + 2, (const void *)(a4 + 24), dwBytes - 24LL);
        try
        {
          v56 = v7;
          EnterCriticalSection(v7);
          std::list<_BDESVC_WORKER_PARAMS *>::_Emplace<_BDESVC_WORKER_PARAMS * const &>(
            v7[1].OwningThread,
            *(_QWORD *)v7[1].OwningThread,
            &v55);
          v55 = 0;
          LeaveCriticalSection(v7);
        }
        catch ( ... )
        {
          v52 = GetProcessHeap();
          HeapFree(v52, 0, v55);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
          v7 = a2;
          v9 = v54;
          goto LABEL_73;
        }
        goto LABEL_73;
      }
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v45 = 42;
        goto LABEL_140;
      }
    }
LABEL_73:
    if ( !(unsigned int)WorkerThreadLauncher(BdeSvcWorkerThread, v7, 5, 0) )
      goto LABEL_62;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_62;
    v27 = 62;
    goto LABEL_77;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
  {
    WPP_SF_(v12[2], 50, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)a4 != 1 )
    goto LABEL_62;
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
  {
    WPP_SF__guid_(v12[2], 51, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  v13 = *(_QWORD *)(a4 + 8) - *(_QWORD *)&GUID_IO_MEDIA_ARRIVAL.Data1;
  if ( !v13 )
    v13 = *(_QWORD *)(a4 + 16) - *(_QWORD *)GUID_IO_MEDIA_ARRIVAL.Data4;
  if ( !v13 )
  {
    if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
      WPP_SF_(v12[2], 52, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
    AcquireSRWLockShared(&CBdeSvcDE::s_InstanceSrwLock);
    v26 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
      v26 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( CBdeSvcDE::s_Instance && *((_QWORD *)CBdeSvcDE::s_Instance + 19) )
    {
      if ( !*((_BYTE *)CBdeSvcDE::s_Instance + 4) && !*((_BYTE *)CBdeSvcDE::s_Instance + 5) )
        goto LABEL_166;
      v39 = CDeviceEncryptionStateCache::InvalidateCache(*((CDeviceEncryptionStateCache **)CBdeSvcDE::s_Instance + 19));
      v40 = v39;
      v26 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, v39);
        v26 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v40 >= 0 )
        goto LABEL_166;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xF3,
        (unsigned int)"base\\ngscb\\cornerstone\\bdesvc\\svc\\deviceencryption.cpp",
        (const char *)(unsigned int)v40,
        (int)"InvalidateCache",
        v53);
    }
    else
    {
      if ( v26 == &WPP_GLOBAL_Control )
      {
LABEL_72:
        ReleaseSRWLockShared(&CBdeSvcDE::s_InstanceSrwLock);
        goto LABEL_73;
      }
      if ( (*((_BYTE *)v26 + 28) & 0x40) == 0 )
      {
LABEL_166:
        if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 0x20) != 0 )
          WPP_SF_(v26[2], 20, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids);
        goto LABEL_72;
      }
      WPP_SF_d(v26[2], 18, &WPP_8ca5a05efc5a3e8b3a7084d7dd9d51f9_Traceguids, 2147942450LL);
    }
    v26 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_166;
  }
  v14 = *(_QWORD *)(a4 + 8) - *(_QWORD *)&GUID_IO_MEDIA_REMOVAL.Data1;
  if ( !v14 )
    v14 = *(_QWORD *)(a4 + 16) - *(_QWORD *)GUID_IO_MEDIA_REMOVAL.Data4;
  if ( !v14 )
  {
    if ( v12 == &WPP_GLOBAL_Control || (*((_BYTE *)v12 + 28) & 8) == 0 )
      goto LABEL_148;
    v37 = 53;
LABEL_147:
    WPP_SF_(v12[2], v37, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
LABEL_148:
    CBdeSvcDE::InvalidateDeviceProtectionStatusCache();
    goto LABEL_73;
  }
  v15 = *(_QWORD *)(a4 + 8) - *(_QWORD *)&GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data1;
  if ( !v15 )
    v15 = *(_QWORD *)(a4 + 16) - *(_QWORD *)GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data4;
  if ( v15 )
  {
    v16 = *(_QWORD *)&GUID_IO_VOLUME_MOUNT.Data1;
    v17 = *(_QWORD *)(a4 + 8) - *(_QWORD *)&GUID_IO_VOLUME_MOUNT.Data1;
    v18 = *(_QWORD *)GUID_IO_VOLUME_MOUNT.Data4;
    if ( !v17 )
      v17 = *(_QWORD *)(a4 + 16) - *(_QWORD *)GUID_IO_VOLUME_MOUNT.Data4;
    if ( !v17 )
    {
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
      {
        WPP_SF_(v12[2], 61, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
        v12 = (PVOID *)WPP_GLOBAL_Control;
        v18 = *(_QWORD *)GUID_IO_VOLUME_MOUNT.Data4;
        v16 = *(_QWORD *)&GUID_IO_VOLUME_MOUNT.Data1;
      }
      v19 = 0;
      if ( *(_DWORD *)a4 == 1 )
      {
        v20 = *(_QWORD *)(a4 + 8) - v16;
        if ( !v20 )
          v20 = *(_QWORD *)(a4 + 16) - v18;
        if ( !v20 )
        {
          v21 = *(_DWORD *)(a4 + 28);
          if ( v21 >= 0x10 && *(_DWORD *)(a4 + 32) == 1 && *(_DWORD *)(a4 + 40) == 6 )
          {
            v22 = *(unsigned int *)(a4 + 44);
            if ( (unsigned int)v22 <= v21 && (int)v22 + 6 <= v21 )
            {
              v23 = *(_DWORD *)(v22 + a4 + 32) - 4259922;
              if ( *(_DWORD *)(v22 + a4 + 32) == 4259922 )
                v23 = *(unsigned __int16 *)(v22 + a4 + 36) - 87;
              if ( !v23 )
                v19 = 1;
            }
          }
        }
      }
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
        WPP_SF_d(v12[2], 37, WPP_ee35f73b350036074f815e40b51ef636_Traceguids, v19);
      if ( !v19 )
        CBdeSvcDE::InvalidateDeviceProtectionStatusCache();
    }
    goto LABEL_62;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    WPP_SF_(v12[2], 54, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
  v28 = *(_DWORD *)(a4 + 36);
  if ( v28 == 34 )
  {
    v31 = GetProcessHeap();
    v32 = HeapAlloc(v31, 0, 0x10u);
    v33 = v32;
    if ( v32 )
    {
      *v32 = *(_OWORD *)(a4 + 304);
      v34 = WorkerThreadLauncher(BdeSvcProcessMetadataDeleteEventThread, v32, 5, 0);
      if ( !v34 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
          goto LABEL_62;
        v27 = 58;
LABEL_77:
        WPP_SF_(v12[2], v27, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
        goto LABEL_62;
      }
      if ( v34 > 0 )
        v34 = (unsigned __int16)v34 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          57,
          WPP_ee35f73b350036074f815e40b51ef636_Traceguids,
          (unsigned int)v34);
      v35 = GetProcessHeap();
      HeapFree(v35, 0, v33);
    }
    else
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_ee35f73b350036074f815e40b51ef636_Traceguids);
          v12 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 0x40) != 0 )
          WPP_SF_d(v12[2], 56, WPP_ee35f73b350036074f815e40b51ef636_Traceguids, 2147942414LL);
      }
    }
    goto LABEL_62;
  }
  v29 = 0;
  if ( v28 == 24 )
  {
    v48 = FveCheckAndSetMsaNudgeCriteriaKey(1u);
    if ( v48 < 0 )
    {
      v49 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v50 = 59;
LABEL_191:
        WPP_SF_d(v49[2], v50, WPP_ee35f73b350036074f815e40b51ef636_Traceguids, (unsigned int)v48);
      }
    }
  }
  else if ( (unsigned int)(v28 - 25) <= 1 )
  {
    v48 = FveCheckAndSetMsaNudgeCriteriaKey(0);
    if ( v48 < 0 )
    {
      v49 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v50 = 60;
        goto LABEL_191;
      }
    }
  }
  v30 = BdeSvcFveEventGetRequiredProcessingLevel(a4) - 1;
  if ( v30 )
  {
    if ( v30 == 1 )
      BdeSvcSetProcessVolumesOnLogon(1);
  }
  else
  {
    v29 = 1;
  }
  CBdeSvcDE::InvalidateDeviceProtectionStatusCache();
  if ( v29 )
    goto LABEL_73;
LABEL_62:
  if ( v9 )
    BdeSvcWorkTracking::FinishWorkImpl((BdeSvcWorkTracking *)v12);
  return 0;
}

```

## disassembly

```asm
0x1800090d0  mov     [rsp+arg_8], rdx
0x1800090d5  push    rbx
0x1800090d6  push    rsi
0x1800090d7  push    rdi
0x1800090d8  push    r13
0x1800090da  push    r14
0x1800090dc  push    r15
0x1800090de  sub     rsp, 58h
0x1800090e2  mov     rbx, r9
0x1800090e5  mov     edi, r8d
0x1800090e8  mov     r13, rdx
0x1800090eb  mov     r15, rcx
0x1800090ee  lea     rsi, WPP_GLOBAL_Control
0x1800090f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090fc  cmp     rcx, rsi
0x1800090ff  jz      short loc_18000911C
0x180009101  test    byte ptr [rcx+1Ch], 20h
0x180009105  jz      short loc_18000911C
0x180009107  mov     edx, 0Fh
0x18000910c  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180009113  mov     rcx, [rcx+10h]
0x180009117  call    WPP_SF_
0x18000911c  xor     r14d, r14d
0x18000911f  mov     [rsp+88h+var_58], r14d
0x180009124  lea     rcx, ?_svcWorkTracking@BdeSvcWorkTracking@@0V1@A; lpCriticalSection
0x18000912b  call    cs:__imp_EnterCriticalSection
0x180009132  nop     dword ptr [rax+rax+00h]
0x180009137  mov     rdx, cs:hEvent
0x18000913e  test    rdx, rdx
0x180009141  jz      loc_1800093FF
0x180009147  cmp     byte ptr cs:word_18009B8E8+1, r14b
0x18000914e  jnz     loc_180009771
0x180009154  cmp     cs:dword_18009B8D8, r14d
0x18000915b  jnz     loc_1800095DB
0x180009161  mov     eax, cs:dword_18009B8C8
0x180009167  inc     eax
0x180009169  mov     cs:dword_18009B8C8, eax
0x18000916f  cmp     eax, 1
0x180009172  jnz     short loc_1800091B1
0x180009174  mov     rcx, cs:WPP_GLOBAL_Control
0x18000917b  cmp     rcx, rsi
0x18000917e  jz      short loc_1800091A2
0x180009180  test    byte ptr [rcx+1Ch], 8
0x180009184  jz      short loc_1800091A2
0x180009186  mov     edx, 13h
0x18000918b  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x180009192  mov     rcx, [rcx+10h]
0x180009196  call    WPP_SF_
0x18000919b  mov     rdx, cs:hEvent
0x1800091a2  mov     rcx, rdx; hEvent
0x1800091a5  call    cs:__imp_SetEvent
0x1800091ac  nop     dword ptr [rax+rax+00h]
0x1800091b1  mov     r14d, 1
0x1800091b7  mov     [rsp+88h+var_58], r14d
0x1800091bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800091c3  cmp     rcx, rsi
0x1800091c6  jz      short loc_1800091E3
0x1800091c8  test    byte ptr [rcx+1Ch], 20h
0x1800091cc  jz      short loc_1800091E3
0x1800091ce  mov     edx, 14h
0x1800091d3  lea     r8, WPP_87bbf11076dc3c61a5de4204d50ff79d_Traceguids
0x1800091da  mov     rcx, [rcx+10h]
0x1800091de  call    WPP_SF_
0x1800091e3  lea     rcx, ?_svcWorkTracking@BdeSvcWorkTracking@@0V1@A; lpCriticalSection
0x1800091ea  call    cs:__imp_LeaveCriticalSection
0x1800091f1  nop     dword ptr [rax+rax+00h]
0x1800091f6  mov     [rsp+88h+var_54], r14d
0x1800091fb  test    r14d, r14d
0x1800091fe  jz      loc_1800093E3
0x180009204  mov     rcx, cs:WPP_GLOBAL_Control
0x18000920b  cmp     rcx, rsi
0x18000920e  jz      short loc_180009235
0x180009210  test    byte ptr [rcx+1Ch], 8
0x180009214  jz      short loc_180009235
0x180009216  mov     edx, 26h ; '&'
0x18000921b  mov     r9d, edi
0x18000921e  lea     r8, WPP_ee35f73b350036074f815e40b51ef636_Traceguids
0x180009225  mov     rcx, [rcx+10h]
0x180009229  call    WPP_SF_d
0x18000922e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009235  cmp     edi, 6
0x180009238  jnz     loc_180009795
0x18000923e  cmp     rcx, rsi
0x180009241  jz      short loc_180009265
0x180009243  test    byte ptr [rcx+1Ch], 8
0x180009247  jz      short loc_180009265
0x180009249  mov     edx, 32h ; '2'
0x18000924e  lea     r8, WPP_ee35f73b350036074f815e40b51ef636_Traceguids
0x180009255  mov     rcx, [rcx+10h]
0x180009259  call    WPP_SF_
0x18000925e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009265  cmp     dword ptr [rbx], 1
0x180009268  jnz     loc_1800093E3
0x18000926e  cmp     rcx, rsi
0x180009271  jz      short loc_180009299
0x180009273  test    byte ptr [rcx+1Ch], 8
0x180009277  jz      short loc_180009299
0x180009279  lea     r9, [rbx+8]
0x18000927d  mov     edx, 33h ; '3'
0x180009282  lea     r8, WPP_ee35f73b350036074f815e40b51ef636_Traceguids
0x180009289  mov     rcx, [rcx+10h]
0x18000928d  call    WPP_SF__guid_
0x180009292  mov     rcx, cs:WPP_GLOBAL_Control
0x180009299  mov     rax, [rbx+8]
0x18000929d  sub     rax, qword ptr cs:GUID_IO_MEDIA_ARRIVAL.Data1
0x1800092a4  jnz     short loc_1800092B1
0x1800092a6  mov     rax, [rbx+10h]
0x1800092aa  sub     rax, qword ptr cs:GUID_IO_MEDIA_ARRIVAL.Data4
0x1800092b1  test    rax, rax
0x1800092b4  jz      loc_180009423
0x1800092ba  mov     rax, [rbx+8]
0x1800092be  sub     rax, qword ptr cs:GUID_IO_MEDIA_REMOVAL.Data1
0x1800092c5  jnz     short loc_1800092D2
0x1800092c7  mov     rax, [rbx+10h]
0x1800092cb  sub     rax, qword ptr cs:GUID_IO_MEDIA_REMOVAL.Data4
0x1800092d2  test    rax, rax
0x1800092d5  jz      loc_180009AD2
0x1800092db  mov     rax, [rbx+8]
0x1800092df  sub     rax, qword ptr cs:GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data1
0x1800092e6  jnz     short loc_1800092F3
0x1800092e8  mov     rax, [rbx+10h]
0x1800092ec  sub     rax, qword ptr cs:GUID_IO_VOLUME_FVE_STATUS_CHANGE.Data4
0x1800092f3  test    rax, rax
0x1800092f6  jz      loc_1800094D6
0x1800092fc  mov     rax, [rbx+8]
0x180009300  mov     r8, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data1
0x180009307  sub     rax, r8
0x18000930a  mov     rdx, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data4
0x180009311  jnz     short loc_18000931A
0x180009313  mov     rax, [rbx+10h]
0x180009317  sub     rax, rdx
0x18000931a  test    rax, rax
0x18000931d  jnz     loc_1800093E3
0x180009323  cmp     rcx, rsi
0x180009326  jz      short loc_180009358
0x180009328  test    byte ptr [rcx+1Ch], 8
0x18000932c  jz      short loc_180009358
0x18000932e  mov     edx, 3Dh ; '='
0x180009333  lea     r8, WPP_ee35f73b350036074f815e40b51ef636_Traceguids
0x18000933a  mov     rcx, [rcx+10h]
0x18000933e  call    WPP_SF_
0x180009343  mov     rcx, cs:WPP_GLOBAL_Control
0x18000934a  mov     rdx, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data4
0x180009351  mov     r8, qword ptr cs:GUID_IO_VOLUME_MOUNT.Data1
0x180009358  xor     edi, edi
0x18000935a  cmp     dword ptr [rbx], 1
0x18000935d  jnz     short loc_1800093B8
0x18000935f  mov     rax, [rbx+8]
0x180009363  sub     rax, r8
0x180009366  jnz     short loc_18000936F
0x180009368  mov     rax, [rbx+10h]
0x18000936c  sub     rax, rdx
0x18000936f  test    rax, rax
0x180009372  jnz     short loc_1800093B8
0x180009374  mov     edx, [rbx+1Ch]
0x180009377  cmp     edx, 10h
0x18000937a  jb      short loc_1800093B8
0x18000937c  cmp     dword ptr [rbx+20h], 1
0x180009380  jnz     short loc_1800093B8
0x180009382  cmp     dword ptr [rbx+28h], 6
0x180009386  jnz     short loc_1800093B8
0x180009388  mov     r8d, [rbx+2Ch]
0x18000938c  cmp     r8d, edx
0x18000938f  ja      short loc_1800093B8
0x180009391  lea     eax, [r8+6]
0x180009395  cmp     eax, edx
0x180009397  ja      short loc_1800093B8
0x180009399  mov     edx, [r8+rbx+20h]
0x18000939e  sub     edx, 410052h
0x1800093a4  jnz     short loc_1800093AF
0x1800093a6  movzx   edx, word ptr [r8+rbx+24h]
0x1800093ac  sub     edx, 57h ; 'W'
0x1800093af  test    edx, edx
0x1800093b1  jnz     short loc_1800093B8
0x1800093b3  mov     edi, 1
0x1800093b8  cmp     rcx, rsi
0x1800093bb  jz      short loc_1800093DB
0x1800093bd  test    byte ptr [rcx+1Ch], 8
0x1800093c1  jz      short loc_1800093DB
0x1800093c3  mov     edx, 25h ; '%'
0x1800093c8  mov     r9d, edi
0x1800093cb  lea     r8, WPP_ee35f73b350036074f815e40b51ef636_Traceguids
0x1800093d2  mov     rcx, [rcx+10h]
0x1800093d6  call    WPP_SF_d
0x1800093db  test    edi, edi
0x1800093dd  jz      loc_180009C1B
0x1800093e3  test    r14d, r14d
0x1800093e6  jz      short loc_1800093EE
0x1800093e8  call    ?FinishWorkImpl@BdeSvcWorkTracking@@AEAAXXZ; BdeSvcWorkTracking::FinishWorkImpl(void)
0x1800093ed  nop
0x1800093ee  xor     eax, eax
0x1800093f0  add     rsp, 58h
0x1800093f4  pop     r15
0x1800093f6  pop     r14
0x1800093f8  pop     r13
0x1800093fa  pop     rdi
0x1800093fb  pop     rsi
0x1800093fc  pop     rbx
0x1800093fd  retn
0x1800093ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180009406  cmp     rcx, rsi
0x180009409  jz      loc_1800091E3
0x18000940f  test    byte ptr [rcx+1Ch], 2
0x180009413  jz      loc_1800091C3
0x180009419  mov     edx, 10h
0x18000941e  jmp     loc_1800095FA
0x180009423  cmp     rcx, rsi
0x180009426  jnz     loc_180009A2E
0x18000942c  lea     rdi, ?s_InstanceSrwLock@CBdeSvcDE@@0VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock CBdeSvcDE::s_InstanceSrwLock
0x180009433  mov     rcx, rdi; SRWLock
0x180009436  call    cs:__imp_AcquireSRWLockShared
0x18000943d  nop     dword ptr [rax+rax+00h]
0x180009442  mov     [rsp+88h+arg_8], rdi
0x18000944a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009451  cmp     rcx, rsi
0x180009454  jnz     loc_180009A52
0x18000945a  mov     rax, cs:?s_Instance@CBdeSvcDE@@0PEAV1@EA; CBdeSvcDE * CBdeSvcDE::s_Instance
0x180009461  test    rax, rax
0x180009464  jnz     loc_1800096E1
0x18000946a  cmp     rcx, rsi
0x18000946d  jnz     loc_180009A7D
0x180009473  mov     rcx, rdi; SRWLock
0x180009476  call    cs:__imp_ReleaseSRWLockShared
0x18000947d  nop     dword ptr [rax+rax+00h]
0x180009482  xor     r9d, r9d
0x180009485  mov     r8d, 5
0x18000948b  mov     rdx, r13
0x18000948e  lea     rcx, ?BdeSvcWorkerThread@@YAIPEAX@Z; BdeSvcWorkerThread(void *)
0x180009495  call    ?WorkerThreadLauncher@@YAKP6AIPEAX@Z0W4WorkerThreadFlags@@PEAK@Z; WorkerThreadLauncher(uint (*)(void *),void *,WorkerThreadFlags,ulong *)
0x18000949a  test    eax, eax
0x18000949c  jz      loc_1800093E3
0x1800094a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094a9  cmp     rcx, rsi
0x1800094ac  jz      loc_1800093E3
0x1800094b2  test    byte ptr [rcx+1Ch], 2
0x1800094b6  jz      loc_1800093E3
0x1800094bc  mov     edx, 3Eh ; '>'
0x1800094c1  lea     r8, WPP_ee35f73b350036074f815e40b51ef636_Traceguids
0x1800094c8  mov     rcx, [rcx+10h]
0x1800094cc  call    WPP_SF_
0x1800094d1  jmp     loc_1800093E3
0x1800094d6  cmp     rcx, rsi
0x1800094d9  jz      short loc_1800094F6
0x1800094db  test    byte ptr [rcx+1Ch], 8
0x1800094df  jz      short loc_1800094F6
0x1800094e1  mov     edx, 36h ; '6'
0x1800094e6  lea     r8, WPP_ee35f73b350036074f815e40b51ef636_Traceguids
0x1800094ed  mov     rcx, [rcx+10h]
0x1800094f1  call    WPP_SF_
0x1800094f6  mov     eax, [rbx+24h]
0x1800094f9  cmp     eax, 22h ; '"'
0x1800094fc  jz      short loc_180009543
0x1800094fe  xor     dil, dil
0x180009501  cmp     eax, 18h
0x180009504  jz      loc_180009B9A
0x18000950a  add     eax, 0FFFFFFE7h
0x18000950d  cmp     eax, 1
0x180009510  jbe     loc_180009BCD
0x180009516  mov     rcx, rbx
0x180009519  call    ?BdeSvcFveEventGetRequiredProcessingLevel@@YA?AW4FveEventRequiredProcessingLevel@@PEAU_CM_NOTIFY_EVENT_DATA@@@Z; BdeSvcFveEventGetRequiredProcessingLevel(_CM_NOTIFY_EVENT_DATA *)
0x18000951e  sub     eax, 1
0x180009521  jz      loc_180009C13
0x180009527  cmp     eax, 1
0x18000952a  jz      loc_18000960F
0x180009530  call    ?InvalidateDeviceProtectionStatusCache@CBdeSvcDE@@SAJXZ; CBdeSvcDE::InvalidateDeviceProtectionStatusCache(void)
0x180009535  test    dil, dil
0x180009538  jz      loc_1800093E3
0x18000953e  jmp     loc_180009482
0x180009543  call    cs:__imp_GetProcessHeap
0x18000954a  nop     dword ptr [rax+rax+00h]
0x18000954f  mov     rcx, rax; hHeap
0x180009552  xor     edx, edx; dwFlags
0x180009554  mov     r8d, 10h; dwBytes
0x18000955a  call    cs:__imp_HeapAlloc
0x180009561  nop     dword ptr [rax+rax+00h]
0x180009566  mov     rdi, rax
0x180009569  test    rax, rax
0x18000956c  jz      loc_180009AEA
0x180009572  movups  xmm0, xmmword ptr [rbx+130h]
0x180009579  movups  xmmword ptr [rax], xmm0
0x18000957c  xor     r9d, r9d
0x18000957f  mov     r8d, 5
0x180009585  mov     rdx, rax
0x180009588  lea     rcx, ?BdeSvcProcessMetadataDeleteEventThread@@YAIPEAX@Z; BdeSvcProcessMetadataDeleteEventThread(void *)
0x18000958f  call    ?WorkerThreadLauncher@@YAKP6AIPEAX@Z0W4WorkerThreadFlags@@PEAK@Z; WorkerThreadLauncher(uint (*)(void *),void *,WorkerThreadFlags,ulong *)
0x180009594  test    eax, eax
0x180009596  jz      loc_180009B76
0x18000959c  jle     short loc_1800095A6
0x18000959e  movzx   eax, ax
0x1800095a1  or      eax, 80070000h
0x1800095a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095ad  cmp     rcx, rsi
0x1800095b0  jnz     loc_180009B4F
0x1800095b6  call    cs:__imp_GetProcessHeap
0x1800095bd  nop     dword ptr [rax+rax+00h]
0x1800095c2  mov     rcx, rax; hHeap
0x1800095c5  mov     r8, rdi; lpMem
0x1800095c8  xor     edx, edx; dwFlags
0x1800095ca  call    cs:__imp_HeapFree
0x1800095d1  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
