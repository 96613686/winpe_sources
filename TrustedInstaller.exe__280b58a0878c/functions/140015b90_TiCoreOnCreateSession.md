# TiCoreOnCreateSession

- ea: `0x140015b90`
- end: `0x140015ff0`
- name: `TiCoreOnCreateSession`
- size: `1120`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1400023e0`
- `0x14000580c`
- `0x14000695c`
- `0x140007630`
- `0x14000ca98`
- `0x14000ceb4`
- `0x14000d420`
- `0x140015a38`
- `0x140015ad8`
- `0x140015b90`
- `0x140015ff8`
- `0x140016098`
- `0x140017658`
- `0x14001afa4`
- `0x14001c360`
- `0x14001c6c0`
- `0x14001c74c`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140015d1b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140015d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015d35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015d35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015cc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015cfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015f2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015f5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015cc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015cfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015f2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015f5c`

## string_xrefs

- `0x140015e99`: `Unable to change Trusted Installer to demand-start service.`
- `0x140015e65`: `System\CurrentControlSet\Control\Winlogon\Notifications\Components\TrustedInstaller`
- `0x140015bf7`: `Winlogon: TiCoreOnCreateSession has been called`
- `0x140015d47`: `Startup: Failed waiting for startup processing to complete, allowing user to logon while processing continues.`
- `0x140015f6c`: `Startup: TiCoreOnCreateSession called with no context.`
- `0x140015f8f`: `Startup: received notification that startup processing completed and a restart has been initiated.`
- `0x140015fa2`: `Startup: received notification that startup processing completed and a restart has been initiated.`
- `0x140015fc3`: `Startup: received notification that startup processing completed, allowing user to logon`
- `0x140015fd6`: `Startup: received notification that startup processing completed, allowing user to logon`
- `0x140015e33`: `Unable to initialize update reserves`

## pseudocode

```c
__int64 __fastcall TiCoreOnCreateSession(volatile int *a1, __int64 a2)
{
  char v2; // r12
  __int64 v4; // rdx
  int v5; // r15d
  unsigned int v6; // ebx
  char v7; // r14
  _QWORD *InitPointer; // rax
  unsigned int v9; // eax
  void *v10; // rcx
  DWORD v11; // edi
  signed int LastError; // eax
  int v13; // eax
  volatile int *v14; // rcx
  int WorkerProcess; // eax
  int v16; // eax
  __int64 v17; // r8
  const wchar_t *v18; // r9
  int v19; // eax
  int v20; // eax
  _QWORD v22[2]; // [rsp+30h] [rbp-40h] BYREF
  char v23; // [rsp+40h] [rbp-30h]
  volatile int *v24; // [rsp+48h] [rbp-28h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-20h] BYREF
  int v26; // [rsp+60h] [rbp-10h] BYREF

  v26 = 0;
  v22[1] = &stru_1400406F8;
  v2 = 0;
  v23 = 0;
  v22[0] = &TiCoreLocker::`vftable';
  v24 = 0;
  if ( !_InterlockedCompareExchange(&dword_14004083C, 1, 0) )
    CBSWdsLogLight(0x4000000u, 0, 0, "Winlogon: TiCoreOnCreateSession has been called");
  if ( !(unsigned int)TiTryChangeStateWithReferenceCount(a1, -2) )
  {
    v5 = 0;
LABEL_5:
    v6 = 0;
    goto LABEL_27;
  }
  v5 = 1;
  if ( !_InterlockedCompareExchange(&dword_14004084C, 0, 0) )
    goto LABEL_5;
  v6 = 0;
  v7 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      v11 = WaitForSingleObject(hObject, 0x3E8u);
      MonitoredCritSecLocker::Lock((MonitoredCritSecLocker *)v22);
      if ( v11 == -1 )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        CBSWdsLogLight(
          0x4000000u,
          (unsigned int)LastError,
          (size_t *)1,
          "Startup: Failed waiting for startup processing to complete, allowing user to logon while processing continues.");
        goto LABEL_27;
      }
      if ( v11 != 258 )
      {
        if ( dword_140040858 )
        {
          CBSWdsLogLight(
            0x4000000u,
            0,
            0,
            "Startup: received notification that startup processing completed and a restart has been initiated.");
          *(_OWORD *)pv = CbsStartupCompleteEvent;
          CbsGenericEventReport(
            pv,
            L"Startup: received notification that startup processing completed and a restart has been initiated.");
          v6 = 1641;
          goto LABEL_30;
        }
        CBSWdsLogLight(
          0x4000000u,
          0,
          0,
          "Startup: received notification that startup processing completed, allowing user to logon");
        *(_OWORD *)pv = CbsStartupCompleteEvent;
        CbsGenericEventReport(
          pv,
          L"Startup: received notification that startup processing completed, allowing user to logon");
LABEL_27:
        if ( dword_140040858 )
          v6 = 1641;
        if ( v5 )
          goto LABEL_30;
        goto LABEL_54;
      }
      if ( dword_140040840 )
        goto LABEL_22;
      if ( !a2 )
      {
        CBSWdsLogLight(0x4000000u, 0x8000FFFF, (size_t *)1, "Startup: TiCoreOnCreateSession called with no context.");
        goto LABEL_27;
      }
      pv[0] = 0;
      InitPointer = Windows::AutoComPtr<IClassFactory>::GetInitPointer(pv);
      v9 = TiCoreCreateSessionNotify(*(unsigned int *)(a2 + 8), &v26, InitPointer);
      v4 = v9;
      if ( (v9 & 0x80000000) == 0 )
        break;
      if ( _InterlockedCompareExchange(&vfTiWorkerShuttingDown, 0, 0) != 1 )
      {
        CBSWdsLogLight(0x4000000u, v9, (size_t *)1, "Startup: Failed getting localized progress string");
LABEL_56:
        v10 = pv[0];
LABEL_57:
        if ( v10 )
          CoTaskMemFree(v10);
        goto LABEL_27;
      }
      if ( !v7 )
      {
        CBSWdsLogLight(
          0x4000000u,
          v9,
          (size_t *)1,
          "Startup: Unable to retrieve localized progress string, but TiWorker is shutting down. Continuing.");
        v7 = 1;
      }
      MonitoredCritSecLocker::Unlock((MonitoredCritSecLocker *)v22);
      if ( pv[0] )
      {
        CoTaskMemFree(pv[0]);
        pv[0] = 0;
      }
    }
    if ( v26 == 1 )
      goto LABEL_56;
    if ( v26 == 3 )
      break;
    v10 = pv[0];
    if ( v26 == 4 )
    {
      v2 = 1;
      goto LABEL_57;
    }
    if ( pv[0] )
    {
      CoTaskMemFree(pv[0]);
      pv[0] = 0;
    }
LABEL_22:
    MonitoredCritSecLocker::Unlock((MonitoredCritSecLocker *)v22);
  }
  StringCchCopyW(*(wchar_t **)(a2 + 16), *(unsigned int *)(a2 + 24), (const wchar_t *)pv[0]);
  v6 = 997;
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
LABEL_30:
  if ( (_InterlockedCompareExchange(&dword_140040844, 0, 1) == 1 || v2)
    && (int)TiCoreGetWorkerProcess(1, (void **)&v24) >= 0 )
  {
    v13 = TiCoreInitiateRestart(v24);
    if ( v13 < 0 )
      CBSWdsLogLight(0x4000000u, (unsigned int)v13, (size_t *)1, "Unable to initiate restart.");
    v6 = 1641;
  }
  LOBYTE(v4) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786>::GetImpl'::`2'::impl,
    v4);
  if ( v6 || !(unsigned __int8)IsRestoreReservesNeeded() )
  {
LABEL_49:
    v14 = v24;
    if ( v24 )
      (*(void (__fastcall **)(volatile int *))(*(_QWORD *)v24 + 16LL))(v24);
  }
  else
  {
    v14 = v24;
    if ( v24 )
      goto LABEL_42;
    WorkerProcess = TiCoreGetWorkerProcess(1, (void **)&v24);
    if ( WorkerProcess < 0 )
      CBSWdsLogLight(0x4000000u, (unsigned int)WorkerProcess, (size_t *)1, "Unable to get worker process");
    v14 = v24;
    if ( v24 )
    {
LABEL_42:
      v16 = (*(__int64 (__fastcall **)(volatile int *))(*(_QWORD *)v14 + 136LL))(v14);
      if ( v16 < 0 )
        CBSWdsLogLight(0x4000000u, (unsigned int)v16, (size_t *)1, "Unable to initialize update reserves");
      if ( !_InterlockedCompareExchange(&dword_140040848, 0, 0) )
      {
        v19 = CbsRegSetStringValue(
                HKEY_LOCAL_MACHINE,
                L"System\\CurrentControlSet\\Control\\Winlogon\\Notifications\\Components\\TrustedInstaller",
                v17,
                v18,
                (BYTE *)&qword_1400353C0);
        if ( v19 < 0 )
          CBSWdsLogLight(
            0x4000000u,
            (unsigned int)v19,
            (size_t *)1,
            "Failed static unregister for winlogon notification");
        v20 = TiCoreSetTiDemandStart();
        if ( v20 < 0 )
          CBSWdsLogLight(
            0x4000000u,
            (unsigned int)v20,
            (size_t *)1,
            "Unable to change Trusted Installer to demand-start service.");
      }
      goto LABEL_49;
    }
  }
  if ( v23 )
    MonitoredCritSecLocker::Unlock((MonitoredCritSecLocker *)v22);
  TiTryChangeStateWithReferenceCount(v14, -3);
LABEL_54:
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v22);
  return v6;
}

```

## disassembly

```asm
0x140015b90  mov     [rsp-28h+arg_0], rbx
0x140015b95  mov     [rsp-28h+arg_10], rsi
0x140015b9a  push    rbp
0x140015b9b  push    rdi
0x140015b9c  push    r12
0x140015b9e  push    r14
0x140015ba0  push    r15
0x140015ba2  mov     rbp, rsp
0x140015ba5  sub     rsp, 70h
0x140015ba9  mov     rax, cs:__security_cookie
0x140015bb0  xor     rax, rsp
0x140015bb3  mov     [rbp+var_8], rax
0x140015bb7  lea     rax, stru_1400406F8
0x140015bbe  mov     [rbp+var_10], 0
0x140015bc5  mov     [rbp+var_38], rax
0x140015bc9  xor     r12b, r12b
0x140015bcc  lea     rax, ??_7TiCoreLocker@@6B@; const TiCoreLocker::`vftable'
0x140015bd3  mov     [rbp+var_30], 0
0x140015bd7  mov     [rbp+var_40], rax
0x140015bdb  mov     rsi, rdx
0x140015bde  xor     eax, eax
0x140015be0  mov     [rbp+var_28], 0
0x140015be8  mov     ebx, 1
0x140015bed  lock cmpxchg cs:dword_14004083C, ebx
0x140015bf5  jnz     short loc_140015C0D
0x140015bf7  lea     r9, aWinlogonTicore; "Winlogon: TiCoreOnCreateSession has bee"...
0x140015bfe  xor     r8d, r8d
0x140015c01  xor     edx, edx
0x140015c03  mov     ecx, 4000000h
0x140015c08  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140015c0d  mov     edx, 0FFFFFFFEh; int
0x140015c12  call    ?TiTryChangeStateWithReferenceCount@@YAHPECJJ@Z; TiTryChangeStateWithReferenceCount(long volatile *,long)
0x140015c17  test    eax, eax
0x140015c19  jnz     short loc_140015C25
0x140015c1b  xor     r15d, r15d
0x140015c1e  xor     ebx, ebx
0x140015c20  jmp     loc_140015D5D
0x140015c25  xor     ecx, ecx
0x140015c27  mov     r15d, ebx
0x140015c2a  xor     eax, eax
0x140015c2c  lock cmpxchg cs:dword_14004084C, ecx
0x140015c34  jz      short loc_140015C1E
0x140015c36  xor     ebx, ebx
0x140015c38  xor     r14b, r14b
0x140015c3b  jmp     loc_140015D0F
0x140015c40  cmp     edi, 102h
0x140015c46  jnz     loc_140015F7D
0x140015c4c  cmp     cs:dword_140040840, ebx
0x140015c52  jnz     loc_140015D06
0x140015c58  test    rsi, rsi
0x140015c5b  jz      loc_140015F6C
0x140015c61  lea     rcx, [rbp+pv]
0x140015c65  mov     [rbp+pv], rbx
0x140015c69  call    ?GetInitPointer@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAPEAPEAUIClassFactory@@XZ; Windows::AutoComPtr<IClassFactory>::GetInitPointer(void)
0x140015c6e  mov     ecx, [rsi+8]
0x140015c71  lea     rdx, [rbp+var_10]
0x140015c75  mov     r8, rax
0x140015c78  call    TiCoreCreateSessionNotify
0x140015c7d  mov     edx, eax
0x140015c7f  test    eax, eax
0x140015c81  jns     short loc_140015CD5
0x140015c83  xor     ecx, ecx
0x140015c85  xor     eax, eax
0x140015c87  lock cmpxchg cs:?vfTiWorkerShuttingDown@@3JA, ecx; long vfTiWorkerShuttingDown
0x140015c8f  mov     edi, r15d
0x140015c92  cmp     eax, r15d
0x140015c95  jnz     loc_140015F0D
0x140015c9b  test    r14b, r14b
0x140015c9e  jnz     short loc_140015CB7
0x140015ca0  lea     r9, aStartupUnableT; "Startup: Unable to retrieve localized p"...
0x140015ca7  mov     r8d, r15d
0x140015caa  mov     ecx, 4000000h
0x140015caf  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140015cb4  mov     r14b, dil
0x140015cb7  lea     rcx, [rbp+var_40]; this
0x140015cbb  call    ?Unlock@MonitoredCritSecLocker@@UEAAXXZ; MonitoredCritSecLocker::Unlock(void)
0x140015cc0  mov     rcx, [rbp+pv]; pv
0x140015cc4  test    rcx, rcx
0x140015cc7  jz      short loc_140015D0F
0x140015cc9  call    cs:__imp_CoTaskMemFree
0x140015ccf  mov     [rbp+pv], rbx
0x140015cd3  jmp     short loc_140015D0F
0x140015cd5  mov     eax, [rbp+var_10]
0x140015cd8  sub     eax, r15d
0x140015cdb  jz      loc_140015F21
0x140015ce1  sub     eax, 2
0x140015ce4  jz      loc_140015F3E
0x140015cea  mov     rcx, [rbp+pv]; pv
0x140015cee  cmp     eax, r15d
0x140015cf1  jz      loc_140015F39
0x140015cf7  test    rcx, rcx
0x140015cfa  jz      short loc_140015D06
0x140015cfc  call    cs:__imp_CoTaskMemFree
0x140015d02  mov     [rbp+pv], rbx
0x140015d06  lea     rcx, [rbp+var_40]; this
0x140015d0a  call    ?Unlock@MonitoredCritSecLocker@@UEAAXXZ; MonitoredCritSecLocker::Unlock(void)
0x140015d0f  mov     rcx, cs:hObject; hHandle
0x140015d16  mov     edx, 3E8h; dwMilliseconds
0x140015d1b  call    cs:__imp_WaitForSingleObject
0x140015d21  lea     rcx, [rbp+var_40]; this
0x140015d25  mov     edi, eax
0x140015d27  call    ?Lock@MonitoredCritSecLocker@@UEAAXXZ; MonitoredCritSecLocker::Lock(void)
0x140015d2c  cmp     edi, 0FFFFFFFFh
0x140015d2f  jnz     loc_140015C40
0x140015d35  call    cs:__imp_GetLastError
0x140015d3b  test    eax, eax
0x140015d3d  jle     short loc_140015D47
0x140015d3f  movzx   eax, ax
0x140015d42  or      eax, 80070000h
0x140015d47  lea     r9, aStartupFailedW; "Startup: Failed waiting for startup pro"...
0x140015d4e  mov     edx, eax
0x140015d50  mov     r8d, r15d
0x140015d53  mov     ecx, 4000000h
0x140015d58  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140015d5d  cmp     cs:dword_140040858, 0
0x140015d64  mov     esi, 669h
0x140015d69  cmovnz  ebx, esi
0x140015d6c  test    r15d, r15d
0x140015d6f  jz      loc_140015EDD
0x140015d75  xor     ecx, ecx
0x140015d77  lea     edi, [rcx+1]
0x140015d7a  mov     eax, edi
0x140015d7c  lock cmpxchg cs:dword_140040844, ecx
0x140015d84  jz      short loc_140015D8B
0x140015d86  test    r12b, r12b
0x140015d89  jz      short loc_140015DC0
0x140015d8b  lea     rdx, [rbp+var_28]
0x140015d8f  mov     cl, dil
0x140015d92  call    TiCoreGetWorkerProcess
0x140015d97  test    eax, eax
0x140015d99  js      short loc_140015DC0
0x140015d9b  mov     rcx, [rbp+var_28]
0x140015d9f  call    TiCoreInitiateRestart
0x140015da4  test    eax, eax
0x140015da6  jns     short loc_140015DBE
0x140015da8  lea     r9, aUnableToInitia_0; "Unable to initiate restart."
0x140015daf  mov     r8d, edi
0x140015db2  mov     edx, eax
0x140015db4  mov     ecx, 4000000h
0x140015db9  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140015dbe  mov     ebx, esi
0x140015dc0  mov     dl, dil
0x140015dc3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786> `wil::Feature<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786>::GetImpl(void)'::`2'::impl
0x140015dca  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140015dcf  test    ebx, ebx
0x140015dd1  jnz     loc_140015EAF
0x140015dd7  call    IsRestoreReservesNeeded
0x140015ddc  test    al, al
0x140015dde  jz      loc_140015EAF
0x140015de4  mov     rcx, [rbp+var_28]
0x140015de8  test    rcx, rcx
0x140015deb  jnz     short loc_140015E20
0x140015ded  lea     rdx, [rbp+var_28]
0x140015df1  mov     cl, dil
0x140015df4  call    TiCoreGetWorkerProcess
0x140015df9  test    eax, eax
0x140015dfb  jns     short loc_140015E13
0x140015dfd  lea     r9, aUnableToGetWor_0; "Unable to get worker process"
0x140015e04  mov     r8d, edi
0x140015e07  mov     edx, eax
0x140015e09  mov     ecx, 4000000h
0x140015e0e  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140015e13  mov     rcx, [rbp+var_28]
0x140015e17  test    rcx, rcx
0x140015e1a  jz      loc_140015EC4
0x140015e20  mov     rax, [rcx]
0x140015e23  mov     rax, [rax+88h]
0x140015e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015e2f  test    eax, eax
0x140015e31  jns     short loc_140015E49
0x140015e33  lea     r9, aUnableToInitia_2; "Unable to initialize update reserves"
0x140015e3a  mov     r8d, edi
0x140015e3d  mov     edx, eax
0x140015e3f  mov     ecx, 4000000h
0x140015e44  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140015e49  xor     ecx, ecx
0x140015e4b  xor     eax, eax
0x140015e4d  lock cmpxchg cs:dword_140040848, ecx
0x140015e55  jnz     short loc_140015EAF
0x140015e57  lea     rax, qword_1400353C0
0x140015e5e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140015e65  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Win"...
0x140015e6c  mov     [rsp+70h+var_50], rax; wchar_t *
0x140015e71  call    ?CbsRegSetStringValue@@YAJPEAUHKEY__@@PEB_WK1QEB_W@Z; CbsRegSetStringValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,wchar_t const * const)
0x140015e76  test    eax, eax
0x140015e78  jns     short loc_140015E90
0x140015e7a  lea     r9, aFailedStaticUn; "Failed static unregister for winlogon n"...
0x140015e81  mov     r8d, edi
0x140015e84  mov     edx, eax
0x140015e86  mov     ecx, 4000000h
0x140015e8b  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140015e90  call    TiCoreSetTiDemandStart
0x140015e95  test    eax, eax
0x140015e97  jns     short loc_140015EAF
0x140015e99  lea     r9, aUnableToChange; "Unable to change Trusted Installer to d"...
0x140015ea0  mov     r8d, edi
0x140015ea3  mov     edx, eax
0x140015ea5  mov     ecx, 4000000h
0x140015eaa  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140015eaf  mov     rcx, [rbp+var_28]
0x140015eb3  test    rcx, rcx
0x140015eb6  jz      short loc_140015EC4
0x140015eb8  mov     rax, [rcx]
0x140015ebb  mov     rax, [rax+10h]
0x140015ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015ec4  cmp     [rbp+var_30], 0
0x140015ec8  jz      short loc_140015ED3
0x140015eca  lea     rcx, [rbp+var_40]; this
0x140015ece  call    ?Unlock@MonitoredCritSecLocker@@UEAAXXZ; MonitoredCritSecLocker::Unlock(void)
0x140015ed3  mov     edx, 0FFFFFFFDh; int
0x140015ed8  call    ?TiTryChangeStateWithReferenceCount@@YAHPECJJ@Z; TiTryChangeStateWithReferenceCount(long volatile *,long)
0x140015edd  lea     rcx, [rbp+var_40]; this
0x140015ee1  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x140015ee6  mov     eax, ebx
0x140015ee8  mov     rcx, [rbp+var_8]
0x140015eec  xor     rcx, rsp; StackCookie
0x140015eef  call    __security_check_cookie
0x140015ef4  lea     r11, [rsp+70h+var_s0]
0x140015ef9  mov     rbx, [r11+30h]
0x140015efd  mov     rsi, [r11+40h]
0x140015f01  mov     rsp, r11
0x140015f04  pop     r15
0x140015f06  pop     r14
0x140015f08  pop     r12
0x140015f0a  pop     rdi
0x140015f0b  pop     rbp
0x140015f0c  retn
0x140015f0d  lea     r9, aStartupFailedG; "Startup: Failed getting localized progr"...
0x140015f14  mov     r8d, edi
0x140015f17  mov     ecx, 4000000h
0x140015f1c  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140015f21  mov     rcx, [rbp+pv]; pv
0x140015f25  test    rcx, rcx
0x140015f28  jz      loc_140015D5D
0x140015f2e  call    cs:__imp_CoTaskMemFree
0x140015f34  jmp     loc_140015D5D
0x140015f39  mov     r12b, r15b
0x140015f3c  jmp     short loc_140015F25
0x140015f3e  mov     edx, [rsi+18h]; unsigned __int64
0x140015f41  mov     r8, [rbp+pv]; wchar_t *
0x140015f45  mov     rcx, [rsi+10h]; wchar_t *
0x140015f49  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140015f4e  mov     rcx, [rbp+pv]; pv
0x140015f52  mov     ebx, 3E5h
0x140015f57  test    rcx, rcx
0x140015f5a  jz      short loc_140015F62
0x140015f5c  call    cs:__imp_CoTaskMemFree
0x140015f62  mov     esi, 669h
0x140015f67  jmp     loc_140015D75
0x140015f6c  lea     r9, aStartupTicoreo; "Startup: TiCoreOnCreateSession called w"...
0x140015f73  mov     edx, 8000FFFFh
0x140015f78  jmp     loc_140015D50
0x140015f7d  xor     r8d, r8d
0x140015f80  xor     edx, edx
0x140015f82  cmp     cs:dword_140040858, ebx
0x140015f88  mov     ecx, 4000000h
0x140015f8d  jz      short loc_140015FC3
0x140015f8f  lea     r9, aStartupReceive; "Startup: received notification that sta"...
0x140015f96  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140015f9b  movups  xmm0, cs:CbsStartupCompleteEvent
0x140015fa2  lea     rdx, aStartupReceive_1; "Startup: received notification that sta"...
0x140015fa9  lea     rcx, [rbp+pv]
0x140015fad  movdqu  xmmword ptr [rbp+pv], xmm0
0x140015fb2  call    CbsGenericEventReport
0x140015fb7  mov     esi, 669h
0x140015fbc  mov     ebx, esi
0x140015fbe  jmp     loc_140015D75
0x140015fc3  lea     r9, aStartupReceive_2; "Startup: received notification that sta"...
0x140015fca  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140015fcf  movups  xmm0, cs:CbsStartupCompleteEvent
0x140015fd6  lea     rdx, aStartupReceive_0; "Startup: received notification that sta"...
0x140015fdd  lea     rcx, [rbp+pv]
0x140015fe1  movdqu  xmmword ptr [rbp+pv], xmm0
0x140015fe6  call    CbsGenericEventReport
0x140015feb  jmp     loc_140015D5D
```
