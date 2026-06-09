# FindOrCreateControlChannelTriggerContext

- ea: `0x18000add0`
- end: `0x18000b9ff`
- name: `FindOrCreateControlChannelTriggerContext`
- size: `3119`
- prototype: ``
- caller_count: `7`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002c30`
- `0x18000cae0`
- `0x1800134f0`
- `0x180014430`
- `0x18001cb50`
- `0x18001ce80`
- `0x180021900`

## callees

- `0x180003ed0`
- `0x18000a0a0`
- `0x18000a160`
- `0x18000add0`
- `0x18000ba08`
- `0x18000bab4`
- `0x18000be70`
- `0x18000c3f0`
- `0x18000c778`
- `0x180014f80`
- `0x18001c500`
- `0x18001d09c`
- `0x18001d8e0`
- `0x180021c34`
- `0x180032108`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x18000b12d`
- `ntdll!RtlLookupEntryHashTable` at `0x18000b12d`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000b622`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000b622`
- `ntdll!RtlInsertEntryHashTable` at `0x18000b06e`
- `ntdll!RtlInsertEntryHashTable` at `0x18000b06e`
- `ntdll!RtlPublishWnfStateData` at `0x18000b0a5`
- `ntdll!RtlPublishWnfStateData` at `0x18000b0a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af3e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000af54`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000af54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b469`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b469`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b6ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b750`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ae98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b152`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ae98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b152`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b0c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b168`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b395`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b49a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b8d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b945`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b99d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b9cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b0c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b168`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b395`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b49a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b8d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b945`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b99d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b9cb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000af6f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000af6f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b551`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b551`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000aee3`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000aee3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000aeff`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000aeff`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000aecb`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18000aecb`
- `RPCRT4!I_RpcOpenClientProcess` at `0x18000aeb3`
- `RPCRT4!I_RpcOpenClientProcess` at `0x18000aeb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b4cb`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000af30`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000af30`

## string_xrefs

- `0x18000b22b`: `NcbReg: Created a new context`
- `0x18000b274`: `Create Context`
- `0x18000b6b0`: `Failed to open client handle %d \n`
- `0x18000b79f`: `Failed to get Process token %d \n`
- `0x18000b802`: `Failed to get duplicate impersonation Process token %d \n`
- `0x18000b84a`: `Not enough memory to create the NC context %d \n`
- `0x18000b92f`: `NcbReg: Failed to create context due to policy restriction`
- `0x18000b9b8`: `NcbReg-FindOrCreateControlChannelTriggerContext: Failed to publish WNF_NCB_APP_AVAILABLE event. Ignore.`
- `0x18000b588`: `NcbReg: Failed to create a new context`

## pseudocode

```c
__int64 __fastcall FindOrCreateControlChannelTriggerContext(
        void *a1,
        __int64 a2,
        __int64 a3,
        char a4,
        __int64 a5,
        char a6,
        __int64 *a7)
{
  char v7; // r12
  PVOID *v8; // rcx
  char *v9; // rdi
  char v10; // r15
  char v11; // r13
  unsigned int v12; // eax
  __int64 v13; // rdx
  unsigned int ApplicationParams; // ebx
  DWORD ProcessId; // eax
  DWORD v16; // r15d
  HANDLE ProcessHeap; // rax
  char *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  unsigned int AppUserModelIdForContext; // eax
  __int64 v22; // rcx
  __int64 v23; // r8
  unsigned int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // r8
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rcx
  char v33; // r12
  unsigned int v34; // eax
  __int64 i; // rax
  PVOID *v36; // rcx
  __int64 v37; // rdx
  PVOID *v38; // rcx
  DWORD LastError; // eax
  __int64 v40; // rdx
  PVOID v41; // rcx
  __int64 v42; // rdx
  PVOID v43; // rcx
  HANDLE v44; // rcx
  void *v45; // rcx
  void *v46; // rcx
  void *v47; // rcx
  void *v48; // rcx
  PVOID v49; // rcx
  DWORD v50; // eax
  __int64 v51; // rdx
  PVOID v52; // rcx
  DWORD v53; // eax
  __int64 v54; // rdx
  PVOID v55; // rcx
  DWORD v56; // eax
  __int64 v57; // rdx
  PVOID v58; // rcx
  PVOID v59; // rcx
  char v60; // [rsp+30h] [rbp-A1h]
  unsigned int v62; // [rsp+38h] [rbp-99h] BYREF
  DWORD pSessionId; // [rsp+40h] [rbp-91h] BYREF
  int v64; // [rsp+44h] [rbp-8Dh] BYREF
  void *Src; // [rsp+48h] [rbp-89h] BYREF
  void *ClientProcess; // [rsp+50h] [rbp-81h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-79h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-71h] BYREF
  __int128 v69; // [rsp+68h] [rbp-69h] BYREF
  __int64 v70; // [rsp+78h] [rbp-59h]
  _BYTE v71[16]; // [rsp+80h] [rbp-51h] BYREF
  const wchar_t *v72; // [rsp+90h] [rbp-41h]
  __int64 v73; // [rsp+98h] [rbp-39h]
  void **v74; // [rsp+A0h] [rbp-31h]
  __int64 v75; // [rsp+A8h] [rbp-29h]
  const char *v76; // [rsp+B0h] [rbp-21h]
  __int64 v77; // [rsp+B8h] [rbp-19h]
  void **p_Src; // [rsp+C0h] [rbp-11h]
  __int64 v79; // [rsp+C8h] [rbp-9h]

  v7 = a3;
  v62 = a2;
  Src = a1;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_ccc(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (unsigned __int8)a3, a4, a6);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  ClientProcess = 0;
  pSessionId = 0;
  TokenHandle = 0;
  hObject = 0;
  v70 = 0;
  v64 = 0;
  v69 = 0;
  if ( !a7 )
  {
    if ( v8 == &WPP_GLOBAL_Control )
      return 87;
    if ( (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 2u )
    {
      WPP_SF_(v8[2], 102, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 1) == 0 || *((_BYTE *)v8 + 25) < 6u )
      return 87;
    v37 = 103;
    goto LABEL_53;
  }
  if ( a5 && a6 == 1 )
  {
    if ( v8 == &WPP_GLOBAL_Control )
      return 87;
    if ( (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 2u )
    {
      WPP_SF_(v8[2], 104, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 1) == 0 || *((_BYTE *)v8 + 25) < 6u )
      return 87;
    v37 = 105;
LABEL_53:
    WPP_SF_d(v8[2], v37, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, 87);
    return 87;
  }
  if ( !a6 && !a5 )
  {
    if ( v8 == &WPP_GLOBAL_Control )
      return 87;
    if ( (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 2u )
    {
      WPP_SF_(v8[2], 106, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 1) == 0 || *((_BYTE *)v8 + 25) < 6u )
      return 87;
    v37 = 107;
    goto LABEL_53;
  }
  v9 = 0;
  v10 = 0;
  v60 = 0;
  v11 = 0;
  *a7 = 0;
  EnterCriticalSection(&g_ControlChannelTriggerContextTableLock);
  if ( !a6 )
  {
    v33 = 0;
    v34 = NcbComputeContextKey(a5);
    v69 = 0;
    for ( i = RtlLookupEntryHashTable(g_ControlChannelTriggerContextTable, v34, &v69);
          ;
          i = RtlGetNextEntryHashTable(g_ControlChannelTriggerContextTable, &v69) )
    {
      if ( !i )
      {
        v36 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_30;
      }
      v9 = (char *)i;
      if ( a5 == i )
        break;
    }
    *a7 = i;
    EnterCriticalSection((LPCRITICAL_SECTION)(i + 24));
    ReferenceContextEx(v9 + 64);
    v33 = 1;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 24));
    v36 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
      ApplicationParams = 0;
      LeaveCriticalSection(&g_ControlChannelTriggerContextTableLock);
      goto LABEL_24;
    }
LABEL_30:
    ApplicationParams = 0;
    if ( !v33 )
    {
      ApplicationParams = 1168;
      if ( v36 != &WPP_GLOBAL_Control && (*((_BYTE *)v36 + 28) & 1) != 0 && *((_BYTE *)v36 + 25) >= 5u )
      {
        WPP_SF_(v36[2], 109, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
        v10 = 0;
        goto LABEL_23;
      }
    }
LABEL_31:
    v10 = 0;
LABEL_23:
    LeaveCriticalSection(&g_ControlChannelTriggerContextTableLock);
    if ( !ApplicationParams )
      goto LABEL_24;
    if ( !a6 )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v31, v30, L"NcbReg: Failed to find the context", ApplicationParams);
      goto LABEL_24;
    }
LABEL_74:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    v44 = hObject;
    if ( hObject )
      CloseHandle(hObject);
    if ( v11 )
      CloseHandle(ClientProcess);
    if ( v10 )
    {
      v45 = (void *)*((_QWORD *)v9 + 30);
      if ( v45 )
      {
        VpnFree(v45);
        *((_QWORD *)v9 + 30) = 0;
      }
      v46 = (void *)*((_QWORD *)v9 + 31);
      if ( v46 )
      {
        VpnFree(v46);
        *((_QWORD *)v9 + 31) = 0;
      }
      v47 = (void *)*((_QWORD *)v9 + 32);
      if ( v47 )
      {
        VpnFree(v47);
        *((_QWORD *)v9 + 32) = 0;
      }
      v44 = (HANDLE)*((_QWORD *)v9 + 34);
      if ( v44 )
      {
        VpnFree(v44);
        *((_QWORD *)v9 + 34) = 0;
      }
    }
    if ( v60 )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 24));
      v48 = (void *)*((_QWORD *)v9 + 35);
      if ( v48 )
      {
        VpnFree(v48);
        *((_QWORD *)v9 + 35) = 0;
      }
      VpnFree(v9);
    }
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v44, v30, L"NcbReg: Failed to create a new context", ApplicationParams);
    goto LABEL_24;
  }
  v12 = I_RpcOpenClientProcess(0, 0x400u, &ClientProcess);
  ApplicationParams = v12;
  if ( v12 )
  {
    v49 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, v12);
    }
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v49, v13, L"Failed to open client handle %d \n", ApplicationParams);
    goto LABEL_154;
  }
  v11 = 1;
  ProcessId = GetProcessId(ClientProcess);
  v16 = ProcessId;
  if ( !ProcessId )
  {
    LastError = GetLastError();
    ApplicationParams = LastError;
    v41 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 111, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, LastError);
    }
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v41, v40, L"Failed to get Process ID %d \n", ApplicationParams);
    goto LABEL_31;
  }
  if ( !ProcessIdToSessionId(ProcessId, &pSessionId) )
  {
    v50 = GetLastError();
    ApplicationParams = v50;
    v52 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, v50);
    }
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      McTemplateU0zq_EventWriteTransfer(v52, v51, L"Failed to get Process session ID %d \n", ApplicationParams);
      v10 = 0;
      goto LABEL_23;
    }
    goto LABEL_31;
  }
  if ( !OpenProcessToken(ClientProcess, 0xAu, &TokenHandle) )
  {
    v53 = GetLastError();
    ApplicationParams = v53;
    v55 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, v53);
    }
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      McTemplateU0zq_EventWriteTransfer(v55, v54, L"Failed to get Process token %d \n", ApplicationParams);
      v10 = 0;
      goto LABEL_23;
    }
    goto LABEL_31;
  }
  if ( !DuplicateTokenEx(TokenHandle, 0xCu, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
  {
    v56 = GetLastError();
    ApplicationParams = v56;
    v58 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, v56);
    }
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      McTemplateU0zq_EventWriteTransfer(
        v58,
        v57,
        L"Failed to get duplicate impersonation Process token %d \n",
        ApplicationParams);
      v10 = 0;
      goto LABEL_23;
    }
    goto LABEL_31;
  }
  ProcessHeap = GetProcessHeap();
  ApplicationParams = 8;
  v18 = (char *)HeapAlloc(ProcessHeap, 8u, 0x1A8u);
  v9 = v18;
  if ( !v18 )
  {
    SetLastError(8u);
    v43 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, 8);
    }
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v43, v42, L"Not enough memory to create the NC context %d \n", 8);
    goto LABEL_73;
  }
  v60 = 1;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v18 + 24));
  memcpy_0(v9 + 68, Src, 2LL * v62);
  *((_DWORD *)v9 + 49) = v16;
  *((_DWORD *)v9 + 52) = pSessionId;
  *((_QWORD *)v9 + 25) = ClientProcess;
  *((_QWORD *)v9 + 27) = TokenHandle;
  *((_QWORD *)v9 + 28) = hObject;
  v9[340] = a4;
  *((_QWORD *)v9 + 52) = NcbRegistrarGetUniqueId();
  ApplicationParams = NcbRegistrarpGetApplicationParams(v9);
  if ( !ApplicationParams )
    goto LABEL_14;
  v38 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      116,
      &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids,
      ApplicationParams);
    v38 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9[232] )
  {
    if ( v38 != &WPP_GLOBAL_Control && (*((_BYTE *)v38 + 28) & 1) != 0 && *((_BYTE *)v38 + 25) >= 5u )
      WPP_SF_(v38[2], 117, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v38, v19, L"App is low box and still failed to get params", ApplicationParams);
LABEL_73:
    LeaveCriticalSection(&g_ControlChannelTriggerContextTableLock);
    v10 = 0;
    goto LABEL_74;
  }
  if ( v38 != &WPP_GLOBAL_Control && (*((_BYTE *)v38 + 28) & 1) != 0 && *((_BYTE *)v38 + 25) >= 5u )
    WPP_SF_(v38[2], 118, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
LABEL_14:
  v10 = 1;
  v9[296] = v7 != 0;
  if ( (unsigned int)NcbRegistrarPolicyIsContextAllowed(v9, 255, v9 + 297) )
  {
    ApplicationParams = 5;
    v59 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, 5);
    }
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v59, v20, L"NcbReg: Failed to create context due to policy restriction", 5);
    goto LABEL_154;
  }
  v9[298] = 0;
  *((_DWORD *)v9 + 91) = 0;
  if ( !v9[297] )
    *((_DWORD *)v9 + 76) = 6;
  AppUserModelIdForContext = NcbpRegistrarpGetAppUserModelIdForContext(v9);
  ApplicationParams = AppUserModelIdForContext;
  if ( AppUserModelIdForContext )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        120,
        &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids,
        AppUserModelIdForContext);
    }
LABEL_154:
    LeaveCriticalSection(&g_ControlChannelTriggerContextTableLock);
    goto LABEL_74;
  }
  *((_DWORD *)v9 + 16) = 1;
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 2) != 0 )
  {
    LODWORD(Src) = 1559;
    v72 = L"Create Context";
    v62 = 1;
    v74 = (void **)&v62;
    v73 = 30;
    v76 = "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\src\\ncbreg.c";
    p_Src = &Src;
    v75 = 4;
    v77 = 47;
    v79 = 4;
    McGenEventWrite_EventWriteTransfer(v22, NcbReference, v23, 5, v71);
  }
  v24 = NcbComputeContextKey(v9);
  RtlInsertEntryHashTable(g_ControlChannelTriggerContextTable, v9, v24, 0);
  *a7 = (__int64)v9;
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    LODWORD(Src) = 0;
    v72 = L"NcbReg: Created a new context";
    v73 = 60;
    v74 = &Src;
    v75 = 4;
    McGenEventWrite_EventWriteTransfer(v25, NcbApiStatus, v26, 3, v71);
  }
  v64 = 1;
  v27 = RtlPublishWnfStateData(WNF_NCB_APP_AVAILABLE, 0, &v64, 4, 0);
  if ( v27 >= 0 || (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
    goto LABEL_23;
  McTemplateU0zq_EventWriteTransfer(
    v29,
    v28,
    L"NcbReg-FindOrCreateControlChannelTriggerContext: Failed to publish WNF_NCB_APP_AVAILABLE event. Ignore.",
    (unsigned int)v27);
  LeaveCriticalSection(&g_ControlChannelTriggerContextTableLock);
LABEL_24:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      121,
      &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids,
      ApplicationParams);
  }
  return ApplicationParams;
}

```

## disassembly

```asm
0x18000add0  push    rbp
0x18000add2  push    rbx
0x18000add3  push    rsi
0x18000add4  push    rdi
0x18000add5  push    r12
0x18000add7  push    r14
0x18000add9  lea     rbp, [rsp-17h]
0x18000adde  sub     rsp, 0E8h
0x18000ade5  mov     rax, cs:__security_cookie
0x18000adec  xor     rax, rsp
0x18000adef  mov     [rbp+3Fh+var_40], rax
0x18000adf3  mov     rbx, [rbp+3Fh+arg_20]
0x18000adf7  movzx   eax, r9b
0x18000adfb  mov     rsi, [rbp+3Fh+arg_30]
0x18000adff  movzx   r12d, r8b
0x18000ae03  mov     [rsp+110h+var_DF], al
0x18000ae07  mov     [rsp+110h+var_D8], edx
0x18000ae0b  mov     [rsp+110h+Src], rcx
0x18000ae10  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae17  lea     rdi, WPP_GLOBAL_Control
0x18000ae1e  movzx   r14d, [rbp+3Fh+arg_28]
0x18000ae23  cmp     rcx, rdi
0x18000ae26  jz      short loc_18000AE32
0x18000ae28  test    byte ptr [rcx+1Ch], 1
0x18000ae2c  jnz     loc_18000B59C
0x18000ae32  xor     edx, edx
0x18000ae34  xor     eax, eax
0x18000ae36  mov     [rsp+110h+ClientProcess], rdx
0x18000ae3b  xorps   xmm0, xmm0
0x18000ae3e  mov     [rsp+110h+pSessionId], edx
0x18000ae42  mov     [rbp+3Fh+TokenHandle], rdx
0x18000ae46  mov     [rbp+3Fh+hObject], rdx
0x18000ae4a  mov     [rbp+3Fh+var_98], rax
0x18000ae4e  mov     [rsp+110h+var_CC], edx
0x18000ae52  movups  [rbp+3Fh+var_A8], xmm0
0x18000ae56  test    rsi, rsi
0x18000ae59  jz      loc_18000B454
0x18000ae5f  test    rbx, rbx
0x18000ae62  jnz     loc_18000B1C9
0x18000ae68  test    r14b, r14b
0x18000ae6b  jz      loc_18000B2EC
0x18000ae71  mov     [rsp+110h+arg_18], r13
0x18000ae79  lea     rcx, g_ControlChannelTriggerContextTableLock; lpCriticalSection
0x18000ae80  mov     [rsp+110h+var_30], r15
0x18000ae88  mov     rdi, rdx
0x18000ae8b  xor     r15b, r15b
0x18000ae8e  mov     [rsp+110h+var_E0], al
0x18000ae92  xor     r13b, r13b
0x18000ae95  mov     [rsi], rdx
0x18000ae98  call    cs:__imp_EnterCriticalSection
0x18000ae9e  test    r14b, r14b
0x18000aea1  jz      loc_18000B10D
0x18000aea7  lea     r8, [rsp+110h+ClientProcess]; ClientProcess
0x18000aeac  mov     edx, 400h; DesiredAccess
0x18000aeb1  xor     ecx, ecx; Binding
0x18000aeb3  call    cs:__imp_I_RpcOpenClientProcess
0x18000aeb9  mov     ebx, eax
0x18000aebb  test    eax, eax
0x18000aebd  jnz     loc_18000B66C
0x18000aec3  mov     rcx, [rsp+110h+ClientProcess]; Process
0x18000aec8  mov     r13b, 1
0x18000aecb  call    cs:__imp_GetProcessId
0x18000aed1  mov     r15d, eax
0x18000aed4  test    eax, eax
0x18000aed6  jz      loc_18000B414
0x18000aedc  lea     rdx, [rsp+110h+pSessionId]; pSessionId
0x18000aee1  mov     ecx, eax; dwProcessId
0x18000aee3  call    cs:__imp_ProcessIdToSessionId
0x18000aee9  test    eax, eax
0x18000aeeb  jz      loc_18000B6ED
0x18000aef1  mov     rcx, [rsp+110h+ClientProcess]; ProcessHandle
0x18000aef6  lea     r8, [rbp+3Fh+TokenHandle]; TokenHandle
0x18000aefa  mov     edx, 0Ah; DesiredAccess
0x18000aeff  call    cs:__imp_OpenProcessToken
0x18000af05  test    eax, eax
0x18000af07  jz      loc_18000B750
0x18000af0d  mov     rcx, [rbp+3Fh+TokenHandle]; hExistingToken
0x18000af11  lea     rax, [rbp+3Fh+hObject]
0x18000af15  mov     [rsp+110h+phNewToken], rax; phNewToken
0x18000af1a  mov     r9d, 2; ImpersonationLevel
0x18000af20  xor     r8d, r8d; lpTokenAttributes
0x18000af23  mov     [rsp+110h+TokenType], 2; TokenType
0x18000af2b  mov     edx, 0Ch; dwDesiredAccess
0x18000af30  call    cs:__imp_DuplicateTokenEx
0x18000af36  test    eax, eax
0x18000af38  jz      loc_18000B7B3
0x18000af3e  call    cs:__imp_GetProcessHeap
0x18000af44  mov     ebx, 8
0x18000af49  mov     r8d, 1A8h; dwBytes
0x18000af4f  mov     rcx, rax; hHeap
0x18000af52  mov     edx, ebx; dwFlags
0x18000af54  call    cs:__imp_HeapAlloc
0x18000af5a  mov     rdi, rax
0x18000af5d  test    rax, rax
0x18000af60  jz      loc_18000B467
0x18000af66  lea     rcx, [rax+18h]; lpCriticalSection
0x18000af6a  mov     [rsp+110h+var_E0], r13b
0x18000af6f  call    cs:__imp_InitializeCriticalSection
0x18000af75  mov     r8d, [rsp+110h+var_D8]
0x18000af7a  lea     rcx, [rdi+44h]; void *
0x18000af7e  mov     rdx, [rsp+110h+Src]; Src
0x18000af83  add     r8, r8; Size
0x18000af86  call    memcpy_0
0x18000af8b  mov     [rdi+0C4h], r15d
0x18000af92  mov     eax, [rsp+110h+pSessionId]
0x18000af96  mov     [rdi+0D0h], eax
0x18000af9c  mov     rax, [rsp+110h+ClientProcess]
0x18000afa1  mov     [rdi+0C8h], rax
0x18000afa8  mov     rax, [rbp+3Fh+TokenHandle]
0x18000afac  mov     [rdi+0D8h], rax
0x18000afb3  mov     rax, [rbp+3Fh+hObject]
0x18000afb7  mov     [rdi+0E0h], rax
0x18000afbe  movzx   eax, [rsp+110h+var_DF]
0x18000afc3  mov     [rdi+154h], al
0x18000afc9  call    NcbRegistrarGetUniqueId
0x18000afce  mov     rcx, rdi
0x18000afd1  mov     [rdi+1A0h], rax
0x18000afd8  call    NcbRegistrarpGetApplicationParams
0x18000afdd  mov     ebx, eax
0x18000afdf  test    eax, eax
0x18000afe1  jnz     loc_18000B3A0
0x18000afe7  test    r12b, r12b
0x18000afea  lea     r8, [rdi+129h]
0x18000aff1  mov     edx, 0FFh
0x18000aff6  mov     rcx, rdi
0x18000aff9  setnz   al
0x18000affc  movzx   r15d, r13b
0x18000b000  mov     [rdi+128h], al
0x18000b006  call    NcbRegistrarPolicyIsContextAllowed
0x18000b00b  test    eax, eax
0x18000b00d  jnz     loc_18000B8EA
0x18000b013  xor     r12d, r12d
0x18000b016  mov     [rdi+12Ah], al
0x18000b01c  mov     [rdi+16Ch], r12d
0x18000b023  cmp     [rdi+129h], r12b
0x18000b02a  jz      loc_18000B950
0x18000b030  mov     rcx, rdi
0x18000b033  call    NcbpRegistrarpGetAppUserModelIdForContext
0x18000b038  mov     ebx, eax
0x18000b03a  test    eax, eax
0x18000b03c  jnz     loc_18000B95F
0x18000b042  mov     dword ptr [rdi+40h], 1
0x18000b049  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 2
0x18000b050  jnz     loc_18000B274
0x18000b056  mov     rcx, rdi
0x18000b059  call    NcbComputeContextKey
0x18000b05e  mov     r8d, eax
0x18000b061  lea     rcx, g_ControlChannelTriggerContextTable
0x18000b068  xor     r9d, r9d
0x18000b06b  mov     rdx, rdi
0x18000b06e  call    cs:__imp_RtlInsertEntryHashTable
0x18000b074  mov     [rsi], rdi
0x18000b077  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, r13b
0x18000b07e  jnz     loc_18000B22B
0x18000b084  mov     rcx, cs:WNF_NCB_APP_AVAILABLE
0x18000b08b  lea     r8, [rsp+110h+var_CC]
0x18000b090  mov     r9d, 4
0x18000b096  mov     [rsp+110h+var_CC], 1
0x18000b09e  xor     edx, edx
0x18000b0a0  mov     qword ptr [rsp+110h+TokenType], r12
0x18000b0a5  call    cs:__imp_RtlPublishWnfStateData
0x18000b0ab  test    eax, eax
0x18000b0ad  js      loc_18000B9A8
0x18000b0b3  lea     rsi, WPP_GLOBAL_Control
0x18000b0ba  lea     rcx, g_ControlChannelTriggerContextTableLock; lpCriticalSection
0x18000b0c1  call    cs:__imp_LeaveCriticalSection
0x18000b0c7  test    ebx, ebx
0x18000b0c9  jnz     loc_18000B9DD
0x18000b0cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0d6  mov     r15, [rsp+110h+var_30]
0x18000b0de  mov     r13, [rsp+110h+arg_18]
0x18000b0e6  cmp     rcx, rsi
0x18000b0e9  jnz     loc_18000B198
0x18000b0ef  mov     eax, ebx
0x18000b0f1  mov     rcx, [rbp+3Fh+var_40]
0x18000b0f5  xor     rcx, rsp; StackCookie
0x18000b0f8  call    __security_check_cookie
0x18000b0fd  add     rsp, 0E8h
0x18000b104  pop     r14
0x18000b106  pop     r12
0x18000b108  pop     rdi
0x18000b109  pop     rsi
0x18000b10a  pop     rbx
0x18000b10b  pop     rbp
0x18000b10c  retn
0x18000b10d  mov     rcx, rbx
0x18000b110  xor     r12b, r12b
0x18000b113  call    NcbComputeContextKey
0x18000b118  xorps   xmm0, xmm0
0x18000b11b  mov     edx, eax
0x18000b11d  lea     r8, [rbp+3Fh+var_A8]
0x18000b121  lea     rcx, g_ControlChannelTriggerContextTable
0x18000b128  movdqu  [rbp+3Fh+var_A8], xmm0
0x18000b12d  call    cs:__imp_RtlLookupEntryHashTable
0x18000b133  mov     r15, rax
0x18000b136  test    rax, rax
0x18000b139  jz      loc_18000B401
0x18000b13f  mov     rdi, rax
0x18000b142  cmp     rbx, rax
0x18000b145  jnz     loc_18000B617
0x18000b14b  lea     rcx, [rax+18h]; lpCriticalSection
0x18000b14f  mov     [rsi], rax
0x18000b152  call    cs:__imp_EnterCriticalSection
0x18000b158  lea     rcx, [rdi+40h]
0x18000b15c  call    ReferenceContextEx
0x18000b161  lea     rcx, [rdi+18h]; lpCriticalSection
0x18000b165  mov     r12b, 1
0x18000b168  call    cs:__imp_LeaveCriticalSection
0x18000b16e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b175  lea     rsi, WPP_GLOBAL_Control
0x18000b17c  cmp     rcx, rsi
0x18000b17f  jnz     loc_18000B363
0x18000b185  xor     ebx, ebx
0x18000b187  test    r12b, r12b
0x18000b18a  jz      loc_18000B62D
0x18000b190  xor     r15b, r15b
0x18000b193  jmp     loc_18000B0BA
0x18000b198  test    byte ptr [rcx+1Ch], 1
0x18000b19c  jz      loc_18000B0EF
0x18000b1a2  cmp     byte ptr [rcx+19h], 6
0x18000b1a6  jb      loc_18000B0EF
0x18000b1ac  mov     rcx, [rcx+10h]
0x18000b1b0  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000b1b7  mov     edx, 79h ; 'y'
0x18000b1bc  mov     r9d, ebx
0x18000b1bf  call    WPP_SF_d
0x18000b1c4  jmp     loc_18000B0EF
0x18000b1c9  cmp     r14b, 1
0x18000b1cd  jnz     loc_18000AE68
0x18000b1d3  cmp     rcx, rdi
0x18000b1d6  jz      loc_18000B45D
0x18000b1dc  test    [rcx+1Ch], r14b
0x18000b1e0  jz      short loc_18000B204
0x18000b1e2  cmp     byte ptr [rcx+19h], 2
0x18000b1e6  jb      short loc_18000B204
0x18000b1e8  mov     rcx, [rcx+10h]
0x18000b1ec  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000b1f3  mov     edx, 68h ; 'h'
0x18000b1f8  call    WPP_SF_
0x18000b1fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b204  cmp     rcx, rdi
0x18000b207  jz      loc_18000B45D
0x18000b20d  test    byte ptr [rcx+1Ch], 1
0x18000b211  jz      loc_18000B45D
0x18000b217  cmp     byte ptr [rcx+19h], 6
0x18000b21b  jb      loc_18000B45D
0x18000b221  mov     edx, 69h ; 'i'
0x18000b226  jmp     loc_18000B348
0x18000b22b  lea     rax, aNcbregCreatedA; "NcbReg: Created a new context"
0x18000b232  mov     dword ptr [rsp+110h+Src], r12d
0x18000b237  mov     [rbp+3Fh+var_80], rax
0x18000b23b  lea     rdx, NcbApiStatus
0x18000b242  lea     rax, [rsp+110h+Src]
0x18000b247  mov     [rbp+3Fh+var_78], 3Ch ; '<'
0x18000b24f  mov     [rbp+3Fh+var_70], rax
0x18000b253  mov     r9d, 3
0x18000b259  lea     rax, [rbp+3Fh+var_90]
0x18000b25d  mov     [rbp+3Fh+var_68], 4
0x18000b265  mov     qword ptr [rsp+110h+TokenType], rax
0x18000b26a  call    McGenEventWrite_EventWriteTransfer
0x18000b26f  jmp     loc_18000B084
0x18000b274  lea     rax, aCreateContext; "Create Context"
0x18000b27b  mov     dword ptr [rsp+110h+Src], 617h
0x18000b283  mov     [rbp+3Fh+var_80], rax
0x18000b287  lea     rdx, NcbReference
0x18000b28e  lea     rax, [rsp+110h+var_D8]
0x18000b293  mov     [rsp+110h+var_D8], 1
0x18000b29b  mov     [rbp+3Fh+var_70], rax
0x18000b29f  mov     r9d, 5
0x18000b2a5  lea     rax, aOnecoreuapNetN_4; "onecoreuap\\net\\netio\\iphlpsvc\\ncb\\"...
0x18000b2ac  mov     [rbp+3Fh+var_78], 1Eh
0x18000b2b4  mov     [rbp+3Fh+var_60], rax
0x18000b2b8  lea     rax, [rsp+110h+Src]
0x18000b2bd  mov     [rbp+3Fh+var_50], rax
0x18000b2c1  lea     rax, [rbp+3Fh+var_90]
0x18000b2c5  mov     qword ptr [rsp+110h+TokenType], rax
0x18000b2ca  mov     [rbp+3Fh+var_68], 4
0x18000b2d2  mov     [rbp+3Fh+var_58], 2Fh ; '/'
0x18000b2da  mov     [rbp+3Fh+var_48], 4
0x18000b2e2  call    McGenEventWrite_EventWriteTransfer
0x18000b2e7  jmp     loc_18000B056
0x18000b2ec  test    rbx, rbx
0x18000b2ef  jnz     loc_18000AE71
0x18000b2f5  cmp     rcx, rdi
0x18000b2f8  jz      loc_18000B45D
0x18000b2fe  test    byte ptr [rcx+1Ch], 1
0x18000b302  jz      short loc_18000B326
0x18000b304  cmp     byte ptr [rcx+19h], 2
0x18000b308  jb      short loc_18000B326
0x18000b30a  mov     rcx, [rcx+10h]
0x18000b30e  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000b315  mov     edx, 6Ah ; 'j'
0x18000b31a  call    WPP_SF_
0x18000b31f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b326  cmp     rcx, rdi
0x18000b329  jz      loc_18000B45D
0x18000b32f  test    byte ptr [rcx+1Ch], 1
0x18000b333  jz      loc_18000B45D
0x18000b339  cmp     byte ptr [rcx+19h], 6
0x18000b33d  jb      loc_18000B45D
  ... truncated ...
```
