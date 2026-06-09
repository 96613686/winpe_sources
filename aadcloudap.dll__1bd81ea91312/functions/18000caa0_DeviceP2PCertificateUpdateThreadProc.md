# DeviceP2PCertificateUpdateThreadProc

- ea: `0x18000caa0`
- end: `0x18000cf47`
- name: `DeviceP2PCertificateUpdateThreadProc`
- size: `1191`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003c20`
- `0x1800069c0`
- `0x180006ac4`
- `0x180006e0c`
- `0x18000961c`
- `0x180009874`
- `0x18000a3c8`
- `0x18000a5f4`
- `0x18000a6fc`
- `0x18000caa0`
- `0x18001cfdc`
- `0x18001d16c`
- `0x18001fcdc`
- `0x180027d34`
- `0x18002ba38`
- `0x180032b14`
- `0x18004dc28`
- `0x180071e14`
- `0x18008aa28`
- `0x18009c6c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000ce97`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000ce97`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000cb97`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000cb97`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000ce06`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000ce06`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000cf05`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000cf05`

## string_xrefs

- `0x18000cae7`: `DeviceP2PCertificateUpdateThreadProc`
- `0x18000cc09`: `Retriable P2P device certificate update error`
- `0x18000ccb2`: `DsrTriggerDeviceUpdateTaskIfNeeded call failed`
- `0x18000cc8c`: `TriggerUpdateTaskIfNecessary`
- `0x18000cc93`: `DsrTriggerDeviceUpdateTaskIfNeeded`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DeviceP2PCertificateUpdateThreadProc(char *a1)
{
  unsigned int v2; // r14d
  int v3; // r12d
  DWORD v4; // esi
  struct AadContextFunctions *v5; // rax
  int v6; // eax
  unsigned int v7; // eax
  int updated; // eax
  unsigned int v9; // r12d
  struct AadContextFunctions *v10; // rax
  HttpWebSession *v11; // rcx
  char *v12; // r12
  const char *v14; // [rsp+38h] [rbp-140h]
  int v15; // [rsp+50h] [rbp-128h] BYREF
  int v16; // [rsp+54h] [rbp-124h]
  int v17; // [rsp+58h] [rbp-120h] BYREF
  DWORD v18; // [rsp+5Ch] [rbp-11Ch]
  __int64 v19; // [rsp+60h] [rbp-118h] BYREF
  char *v20; // [rsp+68h] [rbp-110h]
  struct _RTL_CRITICAL_SECTION *v21; // [rsp+70h] [rbp-108h] BYREF
  char *v22; // [rsp+78h] [rbp-100h]
  char *v23; // [rsp+80h] [rbp-F8h]
  struct _RTL_CRITICAL_SECTION *v24; // [rsp+88h] [rbp-F0h] BYREF
  int v25; // [rsp+90h] [rbp-E8h] BYREF
  __int64 v26; // [rsp+98h] [rbp-E0h]
  const char *v27[6]; // [rsp+A0h] [rbp-D8h] BYREF
  _BYTE v28[24]; // [rsp+D0h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+E8h] [rbp-90h]

  v15 = 0;
  v19 = 0;
  DiagnosticContext::DiagnosticContext((DiagnosticContext *)v28);
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v27,
    (int)"aadcloudap.cpp",
    (int)"DeviceP2PCertificateUpdateThreadProc",
    (int)&v15);
  if ( a1 && (v20 = a1 + 144, *((_QWORD *)a1 + 18)) )
  {
    v22 = a1;
    v23 = a1 + 144;
    v2 = 1;
    v16 = 1;
    do
    {
      v3 = *((_DWORD *)a1 + 11);
      v4 = 18000000;
      if ( v3 != 1 )
        v4 = 86400000;
      v18 = v4;
      if ( IsInternetPresent() )
      {
        v17 = 0;
        SyncCriticalSection::SyncCriticalSection((SyncCriticalSection *)&v21, &CriticalSection);
        ++dword_1800E51B8;
        SyncCriticalSection::~SyncCriticalSection(&v21);
        if ( v19 )
        {
          RtlUnsubscribeWnfNotificationWaitForCompletion();
          v19 = 0;
        }
        if ( v3 == 1 )
        {
          v5 = PluginContextHelper::Context();
          try
          {
            v6 = DeviceP2PCertificateUpdate(v5, (struct _AadApPluginHandle *)a1, (struct DiagnosticContext *)v28, &v17);
            v15 = v6;
          }
          catch ( ... )
          {
            v15 = -1073741595;
            v6 = -1073741595;
            a1 = v22;
            v2 = v16;
            v20 = v23;
            v4 = v18;
          }
          if ( v6 >= 0 )
          {
            v2 = 1;
            v16 = 1;
          }
          else if ( v17 )
          {
            if ( (Microsoft_Windows_AADEnableBits & 0x20) != 0 )
              McTemplateU0zq_EventWriteTransfer(
                Microsoft_Windows_AAD_Context,
                Aad_CloudAPPlugin_Warning,
                L"Retriable P2P device certificate update error",
                (unsigned int)v6);
            if ( v2 < 0x78 )
              v4 = 60000 * v2;
            v7 = v2 + 10;
            if ( v2 >= 0x78 )
              v7 = v2;
            v2 = v7;
            v16 = v7;
          }
          else if ( (Microsoft_Windows_AADEnableBits & 2) != 0 )
          {
            McTemplateU0dz_EventWriteTransfer(
              Microsoft_Windows_AAD_Context,
              Aad_CloudAPPlugin_StatusWithCorrelationID_UpdateThreadProc,
              (unsigned int)v6,
              v29);
          }
          updated = TriggerUpdateTaskIfNecessary();
          v9 = updated;
          if ( updated < 0 )
          {
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"DsrTriggerDeviceUpdateTaskIfNeeded",
              L"TriggerUpdateTaskIfNecessary",
              (unsigned int)updated);
            v14 = "DsrTriggerDeviceUpdateTaskIfNeeded call failed";
            WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws");
            if ( (Microsoft_Windows_AADEnableBits & 0x20) != 0 )
              McTemplateU0zq_EventWriteTransfer(
                Microsoft_Windows_AAD_Context,
                Aad_CloudAPPlugin_Warning,
                L"Retriable device sync trigger error",
                v9);
          }
        }
        v25 = 0;
        v26 = 0;
        if ( (int)ImpersonateLoggedOnUserHelper::ImpersonateConsoleUser((ImpersonateLoggedOnUserHelper *)&v25) >= 0 )
        {
          v10 = PluginContextHelper::Context();
          UpdateWorkPlaceP2PCertificates(v10, a1, (struct DiagnosticContext *)v28);
        }
        ImpersonateLoggedOnUserHelper::~ImpersonateLoggedOnUserHelper((ImpersonateLoggedOnUserHelper *)&v25);
        SyncCriticalSection::SyncCriticalSection((SyncCriticalSection *)&v24, &CriticalSection);
        if ( !--dword_1800E51B8 )
          HttpWebSession::Close(v11);
        SyncCriticalSection::~SyncCriticalSection(&v24);
      }
      else if ( !v19 )
      {
        if ( (Microsoft_Windows_AADEnableBits & 0x20) != 0 )
          McTemplateU0zq_EventWriteTransfer(
            Microsoft_Windows_AAD_Context,
            Aad_CloudAPPlugin_Warning,
            L"Internet is not present",
            0);
        LODWORD(v14) = 1;
        v15 = RtlSubscribeWnfStateChangeNotification(
                &v19,
                WNF_SEB_INTERNET_PRESENT,
                0,
                NetworkStateChangeNotificationCallBack,
                a1,
                0,
                0,
                v14);
        if ( v15 < 0 )
        {
          v14 = "RtlSubscribeWnfStateChangeNotification call failed";
          WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws");
          if ( (Microsoft_Windows_AADEnableBits & 2) != 0 )
            McTemplateU0zq_EventWriteTransfer(
              Microsoft_Windows_AAD_Context,
              Aad_CloudAPPlugin_Error,
              L"RtlSubscribeWnfStateChangeNotification",
              (unsigned int)v15);
          v4 = 600000;
        }
      }
      v12 = v20;
    }
    while ( WaitForSingleObject(*(HANDLE *)(*(_QWORD *)v20 + 8LL), v4) != -1 && !*(_DWORD *)(*(_QWORD *)v12 + 20LL) );
  }
  else
  {
    v15 = -1073741811;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws");
  }
  if ( v19 )
    RtlUnsubscribeWnfStateChangeNotification();
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v27);
  DiagnosticContext::~DiagnosticContext((DiagnosticContext *)v28);
  return 0;
}

```

## disassembly

```asm
0x18000caa0  push    rbx
0x18000caa2  push    rsi
0x18000caa3  push    r12
0x18000caa5  push    r14
0x18000caa7  sub     rsp, 158h
0x18000caae  mov     rax, cs:__security_cookie
0x18000cab5  xor     rax, rsp
0x18000cab8  mov     [rsp+178h+var_30], rax
0x18000cac0  mov     rbx, rcx
0x18000cac3  mov     [rsp+178h+var_128], 0
0x18000cacb  mov     [rsp+178h+var_118], 0
0x18000cad4  lea     rcx, [rsp+178h+var_A8]; this
0x18000cadc  call    ??0DiagnosticContext@@QEAA@XZ; DiagnosticContext::DiagnosticContext(void)
0x18000cae1  nop
0x18000cae2  lea     r9, [rsp+178h+var_128]
0x18000cae7  lea     r8, aDevicep2pcerti; "DeviceP2PCertificateUpdateThreadProc"
0x18000caee  lea     rsi, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x18000caf5  mov     rdx, rsi
0x18000caf8  lea     rcx, [rsp+178h+var_D8]
0x18000cb00  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18000cb05  nop
0x18000cb06  test    rbx, rbx
0x18000cb09  jz      loc_18000CEB2
0x18000cb0f  lea     rax, [rbx+90h]
0x18000cb16  mov     [rsp+178h+var_110], rax
0x18000cb1b  cmp     qword ptr [rax], 0
0x18000cb1f  jz      loc_18000CEB2
0x18000cb25  mov     [rsp+178h+var_100], rbx
0x18000cb2a  mov     [rsp+178h+var_F8], rax
0x18000cb32  mov     r14d, 1
0x18000cb38  mov     [rsp+178h+var_124], r14d
0x18000cb3d  mov     r12d, [rbx+2Ch]
0x18000cb41  mov     esi, 112A880h
0x18000cb46  mov     eax, 5265C00h
0x18000cb4b  cmp     r12d, 1
0x18000cb4f  cmovnz  esi, eax
0x18000cb52  mov     [rsp+178h+var_11C], esi
0x18000cb56  call    ?IsInternetPresent@@YA_NXZ; IsInternetPresent(void)
0x18000cb5b  test    al, al
0x18000cb5d  jz      loc_18000CDA0
0x18000cb63  mov     [rsp+178h+var_120], 0
0x18000cb6b  lea     rdx, CriticalSection; struct _RTL_CRITICAL_SECTION *
0x18000cb72  lea     rcx, [rsp+178h+var_108]; this
0x18000cb77  call    ??0SyncCriticalSection@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; SyncCriticalSection::SyncCriticalSection(_RTL_CRITICAL_SECTION *)
0x18000cb7c  inc     cs:dword_1800E51B8
0x18000cb82  lea     rcx, [rsp+178h+var_108]; this
0x18000cb87  call    ??1SyncCriticalSection@@QEAA@XZ; SyncCriticalSection::~SyncCriticalSection(void)
0x18000cb8c  nop
0x18000cb8d  mov     rcx, [rsp+178h+var_118]
0x18000cb92  test    rcx, rcx
0x18000cb95  jz      short loc_18000CBA6
0x18000cb97  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000cb9d  mov     [rsp+178h+var_118], 0
0x18000cba6  cmp     r12d, 1
0x18000cbaa  jnz     loc_18000CD14
0x18000cbb0  call    ?Context@PluginContextHelper@@SAPEAVAadContextFunctions@@XZ; PluginContextHelper::Context(void)
0x18000cbb5  lea     r9, [rsp+178h+var_120]; int *
0x18000cbba  lea     r8, [rsp+178h+var_A8]; struct DiagnosticContext *
0x18000cbc2  mov     rdx, rbx; struct _AadApPluginHandle *
0x18000cbc5  mov     rcx, rax; struct AadContextFunctions *
0x18000cbc8  call    ?DeviceP2PCertificateUpdate@@YAJPEAVAadContextFunctions@@PEAXAEAVDiagnosticContext@@PEAH@Z; DeviceP2PCertificateUpdate(AadContextFunctions *,void *,DiagnosticContext &,int *)
0x18000cbcd  mov     [rsp+178h+var_128], eax
0x18000cbd1  jmp     short loc_18000CBF2
0x18000cbd3  mov     eax, [rsp+178h+var_128]
0x18000cbd7  mov     rbx, [rsp+178h+var_100]
0x18000cbdc  mov     r14d, [rsp+178h+var_124]
0x18000cbe1  mov     rcx, [rsp+178h+var_F8]
0x18000cbe9  mov     [rsp+178h+var_110], rcx
0x18000cbee  mov     esi, [rsp+178h+var_11C]
0x18000cbf2  test    eax, eax
0x18000cbf4  jns     short loc_18000CC6E
0x18000cbf6  cmp     [rsp+178h+var_120], 0
0x18000cbfb  jz      short loc_18000CC45
0x18000cbfd  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 20h
0x18000cc04  jz      short loc_18000CC23
0x18000cc06  mov     r9d, eax
0x18000cc09  lea     r8, aRetriableP2pDe; "Retriable P2P device certificate update"...
0x18000cc10  lea     rdx, Aad_CloudAPPlugin_Warning
0x18000cc17  lea     rcx, Microsoft_Windows_AAD_Context
0x18000cc1e  call    McTemplateU0zq_EventWriteTransfer
0x18000cc23  cmp     r14d, 78h ; 'x'
0x18000cc27  jnb     short loc_18000CC30
0x18000cc29  imul    esi, r14d, 0EA60h
0x18000cc30  lea     eax, [r14+0Ah]
0x18000cc34  cmp     r14d, 78h ; 'x'
0x18000cc38  cmovnb  eax, r14d
0x18000cc3c  mov     r14d, eax
0x18000cc3f  mov     [rsp+178h+var_124], eax
0x18000cc43  jmp     short loc_18000CC79
0x18000cc45  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 2
0x18000cc4c  jz      short loc_18000CC79
0x18000cc4e  mov     r9, [rsp+178h+var_90]
0x18000cc56  mov     r8d, eax
0x18000cc59  lea     rdx, Aad_CloudAPPlugin_StatusWithCorrelationID_UpdateThreadProc
0x18000cc60  lea     rcx, Microsoft_Windows_AAD_Context
0x18000cc67  call    McTemplateU0dz_EventWriteTransfer
0x18000cc6c  jmp     short loc_18000CC79
0x18000cc6e  mov     r14d, 1
0x18000cc74  mov     [rsp+178h+var_124], r14d
0x18000cc79  call    ?TriggerUpdateTaskIfNecessary@@YAJW4_DSREG_JOIN_TYPE@@PEBG@Z; TriggerUpdateTaskIfNecessary(_DSREG_JOIN_TYPE,ushort const *)
0x18000cc7e  mov     r12d, eax
0x18000cc81  test    eax, eax
0x18000cc83  jns     loc_18000CD14
0x18000cc89  mov     r9d, eax
0x18000cc8c  lea     r8, aTriggerupdatet; "TriggerUpdateTaskIfNecessary"
0x18000cc93  lea     rdx, aDsrtriggerdevi; "DsrTriggerDeviceUpdateTaskIfNeeded"
0x18000cc9a  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18000cca1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000cca6  lea     rax, base
0x18000ccad  mov     [rsp+178h+var_138], rax
0x18000ccb2  lea     rax, aDsrtriggerdevi_0; "DsrTriggerDeviceUpdateTaskIfNeeded call"...
0x18000ccb9  mov     [rsp+178h+var_140], rax
0x18000ccbe  mov     [rsp+178h+var_148], 0AC2h
0x18000ccc6  lea     rax, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x18000cccd  mov     [rsp+178h+var_150], rax
0x18000ccd2  mov     dword ptr [rsp+178h+var_158], r12d
0x18000ccd7  mov     r9d, 2
0x18000ccdd  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18000cce4  xor     edx, edx
0x18000cce6  mov     ecx, r9d
0x18000cce9  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18000ccee  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 20h
0x18000ccf5  jz      short loc_18000CD14
0x18000ccf7  mov     r9d, r12d
0x18000ccfa  lea     r8, aRetriableDevic; "Retriable device sync trigger error"
0x18000cd01  lea     rdx, Aad_CloudAPPlugin_Warning
0x18000cd08  lea     rcx, Microsoft_Windows_AAD_Context
0x18000cd0f  call    McTemplateU0zq_EventWriteTransfer
0x18000cd14  mov     [rsp+178h+var_E8], 0
0x18000cd1f  mov     [rsp+178h+var_E0], 0
0x18000cd2b  lea     rcx, [rsp+178h+var_E8]; this
0x18000cd33  call    ?ImpersonateConsoleUser@ImpersonateLoggedOnUserHelper@@QEAAJXZ; ImpersonateLoggedOnUserHelper::ImpersonateConsoleUser(void)
0x18000cd38  test    eax, eax
0x18000cd3a  js      short loc_18000CD55
0x18000cd3c  call    ?Context@PluginContextHelper@@SAPEAVAadContextFunctions@@XZ; PluginContextHelper::Context(void)
0x18000cd41  lea     r8, [rsp+178h+var_A8]; struct DiagnosticContext *
0x18000cd49  mov     rdx, rbx; void *
0x18000cd4c  mov     rcx, rax; struct AadContextFunctions *
0x18000cd4f  call    ?UpdateWorkPlaceP2PCertificates@@YAJPEAVAadContextFunctions@@PEAXAEAVDiagnosticContext@@@Z; UpdateWorkPlaceP2PCertificates(AadContextFunctions *,void *,DiagnosticContext &)
0x18000cd54  nop
0x18000cd55  lea     rcx, [rsp+178h+var_E8]; this
0x18000cd5d  call    ??1ImpersonateLoggedOnUserHelper@@QEAA@XZ; ImpersonateLoggedOnUserHelper::~ImpersonateLoggedOnUserHelper(void)
0x18000cd62  nop
0x18000cd63  lea     rdx, CriticalSection; struct _RTL_CRITICAL_SECTION *
0x18000cd6a  lea     rcx, [rsp+178h+var_F0]; this
0x18000cd72  call    ??0SyncCriticalSection@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; SyncCriticalSection::SyncCriticalSection(_RTL_CRITICAL_SECTION *)
0x18000cd77  mov     eax, cs:dword_1800E51B8
0x18000cd7d  sub     eax, 1
0x18000cd80  mov     cs:dword_1800E51B8, eax
0x18000cd86  jnz     short loc_18000CD8D
0x18000cd88  call    ?Close@HttpWebSession@@AEAAXXZ; HttpWebSession::Close(void)
0x18000cd8d  lea     rcx, [rsp+178h+var_F0]; this
0x18000cd95  call    ??1SyncCriticalSection@@QEAA@XZ; SyncCriticalSection::~SyncCriticalSection(void)
0x18000cd9a  nop
0x18000cd9b  jmp     loc_18000CE88
0x18000cda0  cmp     [rsp+178h+var_118], 0
0x18000cda6  jnz     loc_18000CE88
0x18000cdac  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 20h
0x18000cdb3  jz      short loc_18000CDD2
0x18000cdb5  xor     r9d, r9d
0x18000cdb8  lea     r8, aInternetIsNotP; "Internet is not present"
0x18000cdbf  lea     rdx, Aad_CloudAPPlugin_Warning
0x18000cdc6  lea     rcx, Microsoft_Windows_AAD_Context
0x18000cdcd  call    McTemplateU0zq_EventWriteTransfer
0x18000cdd2  mov     dword ptr [rsp+178h+var_140], 1
0x18000cdda  mov     [rsp+178h+var_148], 0
0x18000cde2  mov     [rsp+178h+var_150], 0
0x18000cdeb  mov     [rsp+178h+var_158], rbx
0x18000cdf0  lea     r9, ?NetworkStateChangeNotificationCallBack@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; NetworkStateChangeNotificationCallBack(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18000cdf7  xor     r8d, r8d
0x18000cdfa  mov     rdx, cs:WNF_SEB_INTERNET_PRESENT
0x18000ce01  lea     rcx, [rsp+178h+var_118]
0x18000ce06  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x18000ce0c  mov     [rsp+178h+var_128], eax
0x18000ce10  test    eax, eax
0x18000ce12  jns     short loc_18000CE88
0x18000ce14  lea     rcx, base
0x18000ce1b  mov     [rsp+178h+var_138], rcx
0x18000ce20  lea     rcx, aRtlsubscribewn_0; "RtlSubscribeWnfStateChangeNotification "...
0x18000ce27  mov     [rsp+178h+var_140], rcx
0x18000ce2c  mov     [rsp+178h+var_148], 0ADFh
0x18000ce34  lea     rcx, aOnecoreuapDsEx_22+21h; "aadcloudap.cpp"
0x18000ce3b  mov     [rsp+178h+var_150], rcx
0x18000ce40  mov     dword ptr [rsp+178h+var_158], eax
0x18000ce44  mov     r9d, 2
0x18000ce4a  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18000ce51  xor     edx, edx
0x18000ce53  mov     ecx, r9d
0x18000ce56  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18000ce5b  test    byte ptr cs:Microsoft_Windows_AADEnableBits, 2
0x18000ce62  jz      short loc_18000CE83
0x18000ce64  mov     r9d, [rsp+178h+var_128]
0x18000ce69  lea     r8, aRtlsubscribewn; "RtlSubscribeWnfStateChangeNotification"
0x18000ce70  lea     rdx, Aad_CloudAPPlugin_Error
0x18000ce77  lea     rcx, Microsoft_Windows_AAD_Context
0x18000ce7e  call    McTemplateU0zq_EventWriteTransfer
0x18000ce83  mov     esi, 927C0h
0x18000ce88  mov     r12, [rsp+178h+var_110]
0x18000ce8d  mov     rcx, [r12]
0x18000ce91  mov     edx, esi; dwMilliseconds
0x18000ce93  mov     rcx, [rcx+8]; hHandle
0x18000ce97  call    cs:__imp_WaitForSingleObject
0x18000ce9d  cmp     eax, 0FFFFFFFFh
0x18000cea0  jz      short loc_18000CEFB
0x18000cea2  mov     rax, [r12]
0x18000cea6  cmp     dword ptr [rax+14h], 0
0x18000ceaa  jbe     loc_18000CB3D
0x18000ceb0  jmp     short loc_18000CEFB
0x18000ceb2  mov     ecx, 0C000000Dh
0x18000ceb7  mov     [rsp+178h+var_128], ecx
0x18000cebb  lea     rax, base
0x18000cec2  mov     [rsp+178h+var_138], rax
0x18000cec7  lea     rax, aNtstatus; "NTSTATUS"
0x18000cece  mov     [rsp+178h+var_140], rax
0x18000ced3  mov     [rsp+178h+var_148], 0A88h
0x18000cedb  mov     [rsp+178h+var_150], rsi
0x18000cee0  mov     dword ptr [rsp+178h+var_158], ecx
0x18000cee4  mov     r9d, 2
0x18000ceea  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18000cef1  xor     edx, edx
0x18000cef3  mov     ecx, r9d
0x18000cef6  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18000cefb  mov     rcx, [rsp+178h+var_118]
0x18000cf00  test    rcx, rcx
0x18000cf03  jz      short loc_18000CF0C
0x18000cf05  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x18000cf0b  nop
0x18000cf0c  lea     rcx, [rsp+178h+var_D8]
0x18000cf14  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18000cf19  nop
0x18000cf1a  lea     rcx, [rsp+178h+var_A8]; this
0x18000cf22  call    ??1DiagnosticContext@@QEAA@XZ; DiagnosticContext::~DiagnosticContext(void)
0x18000cf27  xor     eax, eax
0x18000cf29  mov     rcx, [rsp+178h+var_30]
0x18000cf31  xor     rcx, rsp; StackCookie
0x18000cf34  call    __security_check_cookie
0x18000cf39  add     rsp, 158h
0x18000cf40  pop     r14
0x18000cf42  pop     r12
0x18000cf44  pop     rsi
0x18000cf45  pop     rbx
0x18000cf46  retn
```
