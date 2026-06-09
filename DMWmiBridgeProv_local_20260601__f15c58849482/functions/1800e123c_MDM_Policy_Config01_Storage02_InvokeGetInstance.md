# MDM_Policy_Config01_Storage02_InvokeGetInstance

- ea: `0x1800e123c`
- end: `0x1800e1813`
- name: `MDM_Policy_Config01_Storage02_InvokeGetInstance`
- size: `1495`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800e0270`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180005240`
- `0x180005358`
- `0x180005438`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800e123c`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800e14d9`
- `msvcrt!_wtoi` at `0x1800e1516`
- `msvcrt!_wtoi` at `0x1800e1553`
- `msvcrt!_wtoi` at `0x1800e1590`
- `msvcrt!_wtoi` at `0x1800e15cd`
- `msvcrt!_wtoi` at `0x1800e160a`
- `msvcrt!_wtoi` at `0x1800e1647`
- `msvcrt!_wtoi` at `0x1800e16b3`
- `msvcrt!_wtoi` at `0x1800e14d9`
- `msvcrt!_wtoi` at `0x1800e1516`
- `msvcrt!_wtoi` at `0x1800e1553`
- `msvcrt!_wtoi` at `0x1800e1590`
- `msvcrt!_wtoi` at `0x1800e15cd`
- `msvcrt!_wtoi` at `0x1800e160a`
- `msvcrt!_wtoi` at `0x1800e1647`
- `msvcrt!_wtoi` at `0x1800e16b3`

## string_xrefs

- `0x1800e14bc`: `AllowDiskHealthModelUpdates`
- `0x1800e1536`: `AllowStorageSenseTemporaryFilesCleanup`
- `0x1800e1573`: `ConfigStorageSenseCloudContentDehydrationThreshold`
- `0x1800e15b0`: `ConfigStorageSenseDownloadsCleanupThreshold`
- `0x1800e15ed`: `ConfigStorageSenseGlobalCadence`
- `0x1800e162a`: `ConfigStorageSenseRecycleBinCleanupThreshold`
- `0x1800e1696`: `RemovableDiskDenyWriteAccess`
- `0x1800e16d3`: `WPDDevicesDenyReadAccessPerDevice`
- `0x1800e1702`: `WPDDevicesDenyWriteAccessPerDevice`
- `0x1800e12ab`: `MDM_Policy_Config01_Storage02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Storage02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  MI_Result v5; // esi
  WmiRequestHandler *v6; // rdi
  wchar_t *String; // [rsp+40h] [rbp-178h] BYREF
  char v9; // [rsp+48h] [rbp-170h]
  WmiRequestHandler *v10; // [rsp+50h] [rbp-168h] BYREF
  _QWORD v11[5]; // [rsp+58h] [rbp-160h] BYREF
  char v12; // [rsp+80h] [rbp-138h]
  int v13; // [rsp+88h] [rbp-130h] BYREF
  char v14; // [rsp+8Ch] [rbp-12Ch]
  _BYTE v15[16]; // [rsp+90h] [rbp-128h] BYREF
  _DWORD v16[4]; // [rsp+A0h] [rbp-118h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-108h] BYREF
  int v18; // [rsp+110h] [rbp-A8h]
  char v19; // [rsp+114h] [rbp-A4h]
  int v20; // [rsp+118h] [rbp-A0h]
  char v21; // [rsp+11Ch] [rbp-9Ch]
  int v22; // [rsp+120h] [rbp-98h]
  char v23; // [rsp+124h] [rbp-94h]
  int v24; // [rsp+128h] [rbp-90h]
  char v25; // [rsp+12Ch] [rbp-8Ch]
  int v26; // [rsp+130h] [rbp-88h]
  char v27; // [rsp+134h] [rbp-84h]
  int v28; // [rsp+138h] [rbp-80h]
  char v29; // [rsp+13Ch] [rbp-7Ch]
  int v30; // [rsp+140h] [rbp-78h]
  char v31; // [rsp+144h] [rbp-74h]
  int v32; // [rsp+158h] [rbp-60h]
  char v33; // [rsp+15Ch] [rbp-5Ch]

  String = 0;
  memset_0(&instance, 0, 0xD0u);
  v13 = 0;
  v14 = 0;
  v11[0] = &TelemetryEventWriter::`vftable';
  v11[1] = &v13;
  v11[2] = "MDM_Policy_Config01_Storage02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18034ED33,
      v15,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    v5 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_62;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v11,
    "GetInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v10 = 0;
  v5 = (unsigned int)CreateRequestHandlerInstance(
                       self,
                       a2[1].serverName,
                       a2[1].ft,
                       &MDM_Policy_Config01_Storage02_NodeList,
                       13,
                       0,
                       &v10);
  if ( v5 == MI_RESULT_OK )
  {
    v11[4] = &v10;
    v12 = 1;
    v6 = v10;
    if ( !v10 )
    {
      v5 = MI_RESULT_FAILED;
      goto LABEL_62;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_Storage02_NodeList,
      0xDu);
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_62;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_62;
    }
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_62;
      goto LABEL_24;
    }
    v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Storage02_rtti, &instance);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_62;
      goto LABEL_24;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AllowDiskHealthModelUpdates",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowStorageSenseGlobal", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v20 = _wtoi(String);
      v21 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AllowStorageSenseTemporaryFilesCleanup",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v22 = _wtoi(String);
      v23 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigStorageSenseCloudContentDehydrationThreshold",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v24 = _wtoi(String);
      v25 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigStorageSenseDownloadsCleanupThreshold",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v26 = _wtoi(String);
      v27 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigStorageSenseGlobalCadence",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v28 = _wtoi(String);
      v29 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ConfigStorageSenseRecycleBinCleanupThreshold",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v30 = _wtoi(String);
      v31 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"EnhancedStorageDevices", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"RemovableDiskDenyWriteAccess",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v32 = _wtoi(String);
      v33 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"WPDDevicesDenyReadAccessPerDevice",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"WPDDevicesDenyWriteAccessPerDevice",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList(&instance);
    }
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v10 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_62:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_180360C18,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800e123c  mov     [rsp+arg_10], rbx
0x1800e1241  push    rsi
0x1800e1242  push    rdi
0x1800e1243  push    r12
0x1800e1245  push    r14
0x1800e1247  push    r15
0x1800e1249  sub     rsp, 190h
0x1800e1250  mov     rax, cs:__security_cookie
0x1800e1257  xor     rax, rsp
0x1800e125a  mov     [rsp+1B8h+var_38], rax
0x1800e1262  mov     r14, rdx
0x1800e1265  mov     r15, rcx
0x1800e1268  xor     ebx, ebx
0x1800e126a  mov     [rsp+1B8h+String], rbx
0x1800e126f  xor     edx, edx; Val
0x1800e1271  mov     r8d, 0D0h; Size
0x1800e1277  lea     rcx, [rsp+1B8h+instance]; void *
0x1800e127f  call    memset_0
0x1800e1284  mov     [rsp+1B8h+var_130], ebx
0x1800e128b  mov     [rsp+1B8h+var_12C], bl
0x1800e1292  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800e1299  mov     [rsp+1B8h+var_160], rax
0x1800e129e  lea     rax, [rsp+1B8h+var_130]
0x1800e12a6  mov     [rsp+1B8h+var_158], rax
0x1800e12ab  lea     rax, aMdmPolicyConfi_172; "MDM_Policy_Config01_Storage02"
0x1800e12b2  mov     [rsp+1B8h+var_150], rax
0x1800e12b7  lea     rcx, [rsp+1B8h+var_130]
0x1800e12bf  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800e12c4  mov     eax, cs:dword_180380B68
0x1800e12ca  cmp     eax, 5
0x1800e12cd  jbe     short loc_1800E133E
0x1800e12cf  mov     rdx, 200000000000h
0x1800e12d9  lea     rcx, dword_180380B68
0x1800e12e0  call    _tlgKeywordOn
0x1800e12e5  test    al, al
0x1800e12e7  jz      short loc_1800E133E
0x1800e12e9  cmp     [rsp+1B8h+var_12C], bl
0x1800e12f0  jz      short loc_1800E1320
0x1800e12f2  cmp     [rsp+1B8h+var_118], ebx
0x1800e12f9  jnz     short loc_1800E1316
0x1800e12fb  cmp     [rsp+1B8h+var_114], ebx
0x1800e1302  jnz     short loc_1800E1316
0x1800e1304  cmp     [rsp+1B8h+var_110], ebx
0x1800e130b  jnz     short loc_1800E1316
0x1800e130d  cmp     [rsp+1B8h+var_10C], ebx
0x1800e1314  jz      short loc_1800E1320
0x1800e1316  lea     r9, [rsp+1B8h+var_118]
0x1800e131e  jmp     short loc_1800E1323
0x1800e1320  mov     r9, rbx
0x1800e1323  lea     r8, [rsp+1B8h+var_128]
0x1800e132b  lea     rdx, byte_18034ED33
0x1800e1332  lea     rcx, dword_180380B68
0x1800e1339  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e133e  cmp     [r14+48h], bl
0x1800e1342  jz      loc_1800E1773
0x1800e1348  mov     [rsp+1B8h+var_170], bl
0x1800e134c  cmp     [r14+58h], bl
0x1800e1350  jz      loc_1800E1773
0x1800e1356  mov     r9, [r14+40h]; unsigned __int16 *
0x1800e135a  mov     r8, [r14+50h]; unsigned __int16 *
0x1800e135e  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1800e1365  lea     rcx, [rsp+1B8h+var_160]; this
0x1800e136a  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800e136f  nop
0x1800e1370  mov     [rsp+1B8h+var_168], rbx
0x1800e1375  lea     rax, [rsp+1B8h+var_168]
0x1800e137a  mov     [rsp+1B8h+var_188], rax
0x1800e137f  mov     [rsp+1B8h+var_190], ebx
0x1800e1383  mov     [rsp+1B8h+var_198], 0Dh
0x1800e138b  lea     r9, ?MDM_Policy_Config01_Storage02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Storage02_NodeList
0x1800e1392  mov     r8, [r14+40h]
0x1800e1396  mov     rdx, [r14+50h]
0x1800e139a  mov     rcx, r15
0x1800e139d  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800e13a2  mov     esi, eax
0x1800e13a4  test    eax, eax
0x1800e13a6  jz      short loc_1800E13AD
0x1800e13a8  jmp     loc_1800E1778
0x1800e13ad  lea     rax, [rsp+1B8h+var_168]
0x1800e13b2  mov     [rsp+1B8h+var_140], rax
0x1800e13b7  mov     r12d, 1
0x1800e13bd  mov     [rsp+1B8h+var_138], r12b
0x1800e13c5  mov     rdi, [rsp+1B8h+var_168]
0x1800e13ca  test    rdi, rdi
0x1800e13cd  jnz     short loc_1800E13D7
0x1800e13cf  mov     esi, r12d
0x1800e13d2  jmp     loc_1800E1778
0x1800e13d7  mov     r9d, 0Dh; unsigned int
0x1800e13dd  lea     r8, ?MDM_Policy_Config01_Storage02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800e13e4  mov     rdx, r14; struct _MI_Instance *
0x1800e13e7  mov     rcx, rdi; this
0x1800e13ea  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800e13ef  mov     rax, [rdi]
0x1800e13f2  mov     rcx, rdi
0x1800e13f5  mov     rax, [rax+10h]
0x1800e13f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e13fe  mov     esi, eax
0x1800e1400  test    eax, eax
0x1800e1402  jz      short loc_1800E1422
0x1800e1404  mov     rcx, [rsp+1B8h+var_168]
0x1800e1409  test    rcx, rcx
0x1800e140c  jz      short loc_1800E141D
0x1800e140e  mov     rax, [rcx]
0x1800e1411  mov     edx, r12d
0x1800e1414  mov     rax, [rax]
0x1800e1417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e141c  nop
0x1800e141d  jmp     loc_1800E1778
0x1800e1422  mov     rax, [rdi]
0x1800e1425  mov     rcx, rdi
0x1800e1428  mov     rax, [rax+8]
0x1800e142c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1431  mov     esi, eax
0x1800e1433  test    eax, eax
0x1800e1435  jz      short loc_1800E1455
0x1800e1437  mov     rcx, [rsp+1B8h+var_168]
0x1800e143c  test    rcx, rcx
0x1800e143f  jz      short loc_1800E1450
0x1800e1441  mov     rax, [rcx]
0x1800e1444  mov     edx, r12d
0x1800e1447  mov     rax, [rax]
0x1800e144a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e144f  nop
0x1800e1450  jmp     loc_1800E1778
0x1800e1455  lea     r8, [rsp+1B8h+instance]; instance
0x1800e145d  lea     rdx, MDM_Policy_Config01_Storage02_rtti; classDecl
0x1800e1464  mov     rcx, r15; context
0x1800e1467  call    MI_Context_ConstructInstance
0x1800e146c  mov     esi, eax
0x1800e146e  test    eax, eax
0x1800e1470  jz      short loc_1800E1490
0x1800e1472  mov     rcx, [rsp+1B8h+var_168]
0x1800e1477  test    rcx, rcx
0x1800e147a  jz      short loc_1800E148B
0x1800e147c  mov     rax, [rcx]
0x1800e147f  mov     edx, r12d
0x1800e1482  mov     rax, [rax]
0x1800e1485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e148a  nop
0x1800e148b  jmp     loc_1800E1778
0x1800e1490  mov     [rsp+1B8h+var_170], r12b
0x1800e1495  mov     rdx, [r14+40h]
0x1800e1499  lea     rcx, [rsp+1B8h+instance]
0x1800e14a1  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800e14a6  mov     rdx, [r14+50h]
0x1800e14aa  lea     rcx, [rsp+1B8h+instance]
0x1800e14b2  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800e14b7  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e14bc  lea     rdx, aAllowdiskhealt; "AllowDiskHealthModelUpdates"
0x1800e14c3  mov     rcx, rdi; this
0x1800e14c6  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e14cb  test    eax, eax
0x1800e14cd  jnz     short loc_1800E14F4
0x1800e14cf  mov     rcx, [rsp+1B8h+String]; String
0x1800e14d4  test    rcx, rcx
0x1800e14d7  jz      short loc_1800E14F4
0x1800e14d9  call    cs:__imp__wtoi
0x1800e14e0  nop     dword ptr [rax+rax+00h]
0x1800e14e5  mov     [rsp+1B8h+var_A8], eax
0x1800e14ec  mov     [rsp+1B8h+var_A4], r12b
0x1800e14f4  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e14f9  lea     rdx, aAllowstoragese_0; "AllowStorageSenseGlobal"
0x1800e1500  mov     rcx, rdi; this
0x1800e1503  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e1508  test    eax, eax
0x1800e150a  jnz     short loc_1800E1531
0x1800e150c  mov     rcx, [rsp+1B8h+String]; String
0x1800e1511  test    rcx, rcx
0x1800e1514  jz      short loc_1800E1531
0x1800e1516  call    cs:__imp__wtoi
0x1800e151d  nop     dword ptr [rax+rax+00h]
0x1800e1522  mov     [rsp+1B8h+var_A0], eax
0x1800e1529  mov     [rsp+1B8h+var_9C], r12b
0x1800e1531  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e1536  lea     rdx, aAllowstoragese; "AllowStorageSenseTemporaryFilesCleanup"
0x1800e153d  mov     rcx, rdi; this
0x1800e1540  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e1545  test    eax, eax
0x1800e1547  jnz     short loc_1800E156E
0x1800e1549  mov     rcx, [rsp+1B8h+String]; String
0x1800e154e  test    rcx, rcx
0x1800e1551  jz      short loc_1800E156E
0x1800e1553  call    cs:__imp__wtoi
0x1800e155a  nop     dword ptr [rax+rax+00h]
0x1800e155f  mov     [rsp+1B8h+var_98], eax
0x1800e1566  mov     [rsp+1B8h+var_94], r12b
0x1800e156e  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e1573  lea     rdx, aConfigstorages; "ConfigStorageSenseCloudContentDehydrati"...
0x1800e157a  mov     rcx, rdi; this
0x1800e157d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e1582  test    eax, eax
0x1800e1584  jnz     short loc_1800E15AB
0x1800e1586  mov     rcx, [rsp+1B8h+String]; String
0x1800e158b  test    rcx, rcx
0x1800e158e  jz      short loc_1800E15AB
0x1800e1590  call    cs:__imp__wtoi
0x1800e1597  nop     dword ptr [rax+rax+00h]
0x1800e159c  mov     [rsp+1B8h+var_90], eax
0x1800e15a3  mov     [rsp+1B8h+var_8C], r12b
0x1800e15ab  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e15b0  lea     rdx, aConfigstorages_2; "ConfigStorageSenseDownloadsCleanupThres"...
0x1800e15b7  mov     rcx, rdi; this
0x1800e15ba  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e15bf  test    eax, eax
0x1800e15c1  jnz     short loc_1800E15E8
0x1800e15c3  mov     rcx, [rsp+1B8h+String]; String
0x1800e15c8  test    rcx, rcx
0x1800e15cb  jz      short loc_1800E15E8
0x1800e15cd  call    cs:__imp__wtoi
0x1800e15d4  nop     dword ptr [rax+rax+00h]
0x1800e15d9  mov     [rsp+1B8h+var_88], eax
0x1800e15e0  mov     [rsp+1B8h+var_84], r12b
0x1800e15e8  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e15ed  lea     rdx, aConfigstorages_0; "ConfigStorageSenseGlobalCadence"
0x1800e15f4  mov     rcx, rdi; this
0x1800e15f7  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e15fc  test    eax, eax
0x1800e15fe  jnz     short loc_1800E1625
0x1800e1600  mov     rcx, [rsp+1B8h+String]; String
0x1800e1605  test    rcx, rcx
0x1800e1608  jz      short loc_1800E1625
0x1800e160a  call    cs:__imp__wtoi
0x1800e1611  nop     dword ptr [rax+rax+00h]
0x1800e1616  mov     [rsp+1B8h+var_80], eax
0x1800e161d  mov     [rsp+1B8h+var_7C], r12b
0x1800e1625  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e162a  lea     rdx, aConfigstorages_1; "ConfigStorageSenseRecycleBinCleanupThre"...
0x1800e1631  mov     rcx, rdi; this
0x1800e1634  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e1639  test    eax, eax
0x1800e163b  jnz     short loc_1800E1662
0x1800e163d  mov     rcx, [rsp+1B8h+String]; String
0x1800e1642  test    rcx, rcx
0x1800e1645  jz      short loc_1800E1662
0x1800e1647  call    cs:__imp__wtoi
0x1800e164e  nop     dword ptr [rax+rax+00h]
0x1800e1653  mov     [rsp+1B8h+var_78], eax
0x1800e165a  mov     [rsp+1B8h+var_74], r12b
0x1800e1662  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e1667  lea     rdx, aEnhancedstorag; "EnhancedStorageDevices"
0x1800e166e  mov     rcx, rdi; this
0x1800e1671  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e1676  test    eax, eax
0x1800e1678  jnz     short loc_1800E1691
0x1800e167a  mov     rdx, [rsp+1B8h+String]
0x1800e167f  test    rdx, rdx
0x1800e1682  jz      short loc_1800E1691
0x1800e1684  lea     rcx, [rsp+1B8h+instance]
0x1800e168c  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x1800e1691  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e1696  lea     rdx, aRemovablediskd; "RemovableDiskDenyWriteAccess"
0x1800e169d  mov     rcx, rdi; this
0x1800e16a0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e16a5  test    eax, eax
0x1800e16a7  jnz     short loc_1800E16CE
0x1800e16a9  mov     rcx, [rsp+1B8h+String]; String
0x1800e16ae  test    rcx, rcx
0x1800e16b1  jz      short loc_1800E16CE
0x1800e16b3  call    cs:__imp__wtoi
0x1800e16ba  nop     dword ptr [rax+rax+00h]
0x1800e16bf  mov     [rsp+1B8h+var_60], eax
0x1800e16c6  mov     [rsp+1B8h+var_5C], r12b
0x1800e16ce  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e16d3  lea     rdx, aWpddevicesdeny_1; "WPDDevicesDenyReadAccessPerDevice"
0x1800e16da  mov     rcx, rdi; this
0x1800e16dd  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e16e2  test    eax, eax
0x1800e16e4  jnz     short loc_1800E16FD
0x1800e16e6  mov     rdx, [rsp+1B8h+String]
0x1800e16eb  test    rdx, rdx
0x1800e16ee  jz      short loc_1800E16FD
0x1800e16f0  lea     rcx, [rsp+1B8h+instance]
0x1800e16f8  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList
0x1800e16fd  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e1702  lea     rdx, aWpddevicesdeny_2; "WPDDevicesDenyWriteAccessPerDevice"
0x1800e1709  mov     rcx, rdi; this
0x1800e170c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e1711  test    eax, eax
0x1800e1713  jnz     short loc_1800E172C
0x1800e1715  mov     rdx, [rsp+1B8h+String]
0x1800e171a  test    rdx, rdx
0x1800e171d  jz      short loc_1800E172C
0x1800e171f  lea     rcx, [rsp+1B8h+instance]
0x1800e1727  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList
0x1800e172c  lea     rdx, [rsp+1B8h+instance]
0x1800e1734  mov     rcx, r15; self
0x1800e1737  call    MI_Instance_Destruct
0x1800e173c  nop
0x1800e173d  mov     rcx, [rsp+1B8h+var_168]
0x1800e1742  test    rcx, rcx
0x1800e1745  jz      short loc_1800E1756
0x1800e1747  mov     rax, [rcx]
0x1800e174a  mov     edx, r12d
0x1800e174d  mov     rax, [rax]
0x1800e1750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1755  nop
0x1800e1756  jmp     short loc_1800E1764
0x1800e1758  xor     ebx, ebx
0x1800e175a  mov     esi, dword ptr [rsp+1B8h+String]
0x1800e175e  cmp     [rsp+1B8h+var_170], bl
  ... truncated ...
```
