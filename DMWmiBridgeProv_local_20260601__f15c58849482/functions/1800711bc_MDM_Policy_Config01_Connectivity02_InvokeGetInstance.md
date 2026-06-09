# MDM_Policy_Config01_Connectivity02_InvokeGetInstance

- ea: `0x1800711bc`
- end: `0x1800717f6`
- name: `MDM_Policy_Config01_Connectivity02_InvokeGetInstance`
- size: `1594`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180070100`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180005240`
- `0x1800052b0`
- `0x180005390`
- `0x1800053c8`
- `0x180005438`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800711bc`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18007145b`
- `msvcrt!_wtoi` at `0x180071498`
- `msvcrt!_wtoi` at `0x1800714d5`
- `msvcrt!_wtoi` at `0x180071512`
- `msvcrt!_wtoi` at `0x18007154f`
- `msvcrt!_wtoi` at `0x18007158c`
- `msvcrt!_wtoi` at `0x1800715c9`
- `msvcrt!_wtoi` at `0x180071693`
- `msvcrt!_wtoi` at `0x18007145b`
- `msvcrt!_wtoi` at `0x180071498`
- `msvcrt!_wtoi` at `0x1800714d5`
- `msvcrt!_wtoi` at `0x180071512`
- `msvcrt!_wtoi` at `0x18007154f`
- `msvcrt!_wtoi` at `0x18007158c`
- `msvcrt!_wtoi` at `0x1800715c9`
- `msvcrt!_wtoi` at `0x180071693`

## string_xrefs

- `0x180071532`: `AllowPhonePCLinking`
- `0x1800716b3`: `HardenedUNCPaths`
- `0x1800716e2`: `ProhibitInstallationAndConfigurationOfNetworkBridge`
- `0x18007122b`: `MDM_Policy_Config01_Connectivity02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Connectivity02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  MI_Result v5; // r14d
  WmiRequestHandler *v6; // rdi
  wchar_t *String; // [rsp+40h] [rbp-198h] BYREF
  char v9; // [rsp+48h] [rbp-190h]
  WmiRequestHandler *v10; // [rsp+50h] [rbp-188h] BYREF
  _QWORD v11[5]; // [rsp+58h] [rbp-180h] BYREF
  char v12; // [rsp+80h] [rbp-158h]
  int v13; // [rsp+88h] [rbp-150h] BYREF
  char v14; // [rsp+8Ch] [rbp-14Ch]
  _BYTE v15[16]; // [rsp+90h] [rbp-148h] BYREF
  _DWORD v16[4]; // [rsp+A0h] [rbp-138h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-128h] BYREF
  int v18; // [rsp+110h] [rbp-C8h]
  char v19; // [rsp+114h] [rbp-C4h]
  int v20; // [rsp+118h] [rbp-C0h]
  char v21; // [rsp+11Ch] [rbp-BCh]
  int v22; // [rsp+120h] [rbp-B8h]
  char v23; // [rsp+124h] [rbp-B4h]
  int v24; // [rsp+128h] [rbp-B0h]
  char v25; // [rsp+12Ch] [rbp-ACh]
  int v26; // [rsp+130h] [rbp-A8h]
  char v27; // [rsp+134h] [rbp-A4h]
  int v28; // [rsp+138h] [rbp-A0h]
  char v29; // [rsp+13Ch] [rbp-9Ch]
  int v30; // [rsp+140h] [rbp-98h]
  char v31; // [rsp+144h] [rbp-94h]
  int v32; // [rsp+178h] [rbp-60h]
  char v33; // [rsp+17Ch] [rbp-5Ch]

  String = 0;
  memset_0(&instance, 0, 0xF0u);
  v13 = 0;
  v14 = 0;
  v11[0] = &TelemetryEventWriter::`vftable';
  v11[1] = &v13;
  v11[2] = "MDM_Policy_Config01_Connectivity02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_18036EFEF,
      v15,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || (v9 = 0, !LOBYTE(a2[1].nameSpace)) )
  {
    v5 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_68;
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
                       &MDM_Policy_Config01_Connectivity02_NodeList,
                       15,
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
      goto LABEL_68;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_Connectivity02_NodeList,
      0xFu);
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_68;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_68;
    }
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_68;
      goto LABEL_24;
    }
    v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Connectivity02_rtti, &instance);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_68;
      goto LABEL_24;
    }
    v9 = 1;
    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowBluetooth", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowCellularData", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v20 = _wtoi(String);
      v21 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowCellularDataRoaming", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v22 = _wtoi(String);
      v23 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowConnectedDevices", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v24 = _wtoi(String);
      v25 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowPhonePCLinking", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v26 = _wtoi(String);
      v27 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowVPNOverCellular", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v28 = _wtoi(String);
      v29 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AllowVPNRoamingOverCellular",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v30 = _wtoi(String);
      v31 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"DiablePrintingOverHTTP", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"DisableDownloadingOfPrintDriversOverHTTP",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"DisableInternetDownloadForWebPublishingAndOnlineOrderingWizards",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"DisallowNetworkConnectivityActiveTests",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v32 = _wtoi(String);
      v33 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"HardenedUNCPaths", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_VPNv2_User_01_Set_ProfileXML(&instance);
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"ProhibitInstallationAndConfigurationOfNetworkBridge",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetZoneTemplate(&instance);
    }
    MI_Instance_Destruct((MI_Instance *)self);
    if ( v10 )
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
    MI_Instance_Destruct(&instance);
  }
LABEL_68:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_18033A52F,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800711bc  mov     [rsp+arg_10], rbx
0x1800711c1  push    rsi
0x1800711c2  push    rdi
0x1800711c3  push    r12
0x1800711c5  push    r14
0x1800711c7  push    r15
0x1800711c9  sub     rsp, 1B0h
0x1800711d0  mov     rax, cs:__security_cookie
0x1800711d7  xor     rax, rsp
0x1800711da  mov     [rsp+1D8h+var_38], rax
0x1800711e2  mov     rsi, rdx
0x1800711e5  mov     r15, rcx
0x1800711e8  xor     ebx, ebx
0x1800711ea  mov     [rsp+1D8h+String], rbx
0x1800711ef  xor     edx, edx; Val
0x1800711f1  mov     r8d, 0F0h; Size
0x1800711f7  lea     rcx, [rsp+1D8h+instance]; void *
0x1800711ff  call    memset_0
0x180071204  mov     [rsp+1D8h+var_150], ebx
0x18007120b  mov     [rsp+1D8h+var_14C], bl
0x180071212  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180071219  mov     [rsp+1D8h+var_180], rax
0x18007121e  lea     rax, [rsp+1D8h+var_150]
0x180071226  mov     [rsp+1D8h+var_178], rax
0x18007122b  lea     rax, aMdmPolicyConfi_107; "MDM_Policy_Config01_Connectivity02"
0x180071232  mov     [rsp+1D8h+var_170], rax
0x180071237  lea     rcx, [rsp+1D8h+var_150]
0x18007123f  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180071244  mov     eax, cs:dword_180380B68
0x18007124a  cmp     eax, 5
0x18007124d  jbe     short loc_1800712BE
0x18007124f  mov     rdx, 200000000000h
0x180071259  lea     rcx, dword_180380B68
0x180071260  call    _tlgKeywordOn
0x180071265  test    al, al
0x180071267  jz      short loc_1800712BE
0x180071269  cmp     [rsp+1D8h+var_14C], bl
0x180071270  jz      short loc_1800712A0
0x180071272  cmp     [rsp+1D8h+var_138], ebx
0x180071279  jnz     short loc_180071296
0x18007127b  cmp     [rsp+1D8h+var_134], ebx
0x180071282  jnz     short loc_180071296
0x180071284  cmp     [rsp+1D8h+var_130], ebx
0x18007128b  jnz     short loc_180071296
0x18007128d  cmp     [rsp+1D8h+var_12C], ebx
0x180071294  jz      short loc_1800712A0
0x180071296  lea     r9, [rsp+1D8h+var_138]
0x18007129e  jmp     short loc_1800712A3
0x1800712a0  mov     r9, rbx
0x1800712a3  lea     r8, [rsp+1D8h+var_148]
0x1800712ab  lea     rdx, byte_18036EFEF
0x1800712b2  lea     rcx, dword_180380B68
0x1800712b9  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800712be  cmp     [rsi+48h], bl
0x1800712c1  jz      loc_180071754
0x1800712c7  mov     [rsp+1D8h+var_190], bl
0x1800712cb  cmp     [rsi+58h], bl
0x1800712ce  jz      loc_180071754
0x1800712d4  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800712d8  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800712dc  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1800712e3  lea     rcx, [rsp+1D8h+var_180]; this
0x1800712e8  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800712ed  nop
0x1800712ee  mov     [rsp+1D8h+var_188], rbx
0x1800712f3  lea     rax, [rsp+1D8h+var_188]
0x1800712f8  mov     [rsp+1D8h+var_1A8], rax
0x1800712fd  mov     [rsp+1D8h+var_1B0], ebx
0x180071301  mov     [rsp+1D8h+var_1B8], 0Fh
0x180071309  lea     r9, ?MDM_Policy_Config01_Connectivity02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Connectivity02_NodeList
0x180071310  mov     r8, [rsi+40h]
0x180071314  mov     rdx, [rsi+50h]
0x180071318  mov     rcx, r15
0x18007131b  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180071320  mov     r14d, eax
0x180071323  test    eax, eax
0x180071325  jz      short loc_18007132C
0x180071327  jmp     loc_18007175A
0x18007132c  lea     rax, [rsp+1D8h+var_188]
0x180071331  mov     [rsp+1D8h+var_160], rax
0x180071336  mov     r12d, 1
0x18007133c  mov     [rsp+1D8h+var_158], r12b
0x180071344  mov     rdi, [rsp+1D8h+var_188]
0x180071349  test    rdi, rdi
0x18007134c  jnz     short loc_180071356
0x18007134e  mov     r14d, r12d
0x180071351  jmp     loc_18007175A
0x180071356  mov     r9d, 0Fh; unsigned int
0x18007135c  lea     r8, ?MDM_Policy_Config01_Connectivity02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180071363  mov     rdx, rsi; struct _MI_Instance *
0x180071366  mov     rcx, rdi; this
0x180071369  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18007136e  mov     rax, [rdi]
0x180071371  mov     rcx, rdi
0x180071374  mov     rax, [rax+10h]
0x180071378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007137d  mov     r14d, eax
0x180071380  test    eax, eax
0x180071382  jz      short loc_1800713A2
0x180071384  mov     rcx, [rsp+1D8h+var_188]
0x180071389  test    rcx, rcx
0x18007138c  jz      short loc_18007139D
0x18007138e  mov     rax, [rcx]
0x180071391  mov     edx, r12d
0x180071394  mov     rax, [rax]
0x180071397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007139c  nop
0x18007139d  jmp     loc_18007175A
0x1800713a2  mov     rax, [rdi]
0x1800713a5  mov     rcx, rdi
0x1800713a8  mov     rax, [rax+8]
0x1800713ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800713b1  mov     r14d, eax
0x1800713b4  test    eax, eax
0x1800713b6  jz      short loc_1800713D6
0x1800713b8  mov     rcx, [rsp+1D8h+var_188]
0x1800713bd  test    rcx, rcx
0x1800713c0  jz      short loc_1800713D1
0x1800713c2  mov     rax, [rcx]
0x1800713c5  mov     edx, r12d
0x1800713c8  mov     rax, [rax]
0x1800713cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800713d0  nop
0x1800713d1  jmp     loc_18007175A
0x1800713d6  lea     r8, [rsp+1D8h+instance]; instance
0x1800713de  lea     rdx, MDM_Policy_Config01_Connectivity02_rtti; classDecl
0x1800713e5  mov     rcx, r15; context
0x1800713e8  call    MI_Context_ConstructInstance
0x1800713ed  mov     r14d, eax
0x1800713f0  test    eax, eax
0x1800713f2  jz      short loc_180071412
0x1800713f4  mov     rcx, [rsp+1D8h+var_188]
0x1800713f9  test    rcx, rcx
0x1800713fc  jz      short loc_18007140D
0x1800713fe  mov     rax, [rcx]
0x180071401  mov     edx, r12d
0x180071404  mov     rax, [rax]
0x180071407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007140c  nop
0x18007140d  jmp     loc_18007175A
0x180071412  mov     [rsp+1D8h+var_190], r12b
0x180071417  mov     rdx, [rsi+40h]
0x18007141b  lea     rcx, [rsp+1D8h+instance]
0x180071423  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180071428  mov     rdx, [rsi+50h]
0x18007142c  lea     rcx, [rsp+1D8h+instance]
0x180071434  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180071439  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18007143e  lea     rdx, aAllowbluetooth; "AllowBluetooth"
0x180071445  mov     rcx, rdi; this
0x180071448  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007144d  test    eax, eax
0x18007144f  jnz     short loc_180071476
0x180071451  mov     rcx, [rsp+1D8h+String]; String
0x180071456  test    rcx, rcx
0x180071459  jz      short loc_180071476
0x18007145b  call    cs:__imp__wtoi
0x180071462  nop     dword ptr [rax+rax+00h]
0x180071467  mov     [rsp+1D8h+var_C8], eax
0x18007146e  mov     [rsp+1D8h+var_C4], r12b
0x180071476  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18007147b  lea     rdx, aAllowcellulard; "AllowCellularData"
0x180071482  mov     rcx, rdi; this
0x180071485  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007148a  test    eax, eax
0x18007148c  jnz     short loc_1800714B3
0x18007148e  mov     rcx, [rsp+1D8h+String]; String
0x180071493  test    rcx, rcx
0x180071496  jz      short loc_1800714B3
0x180071498  call    cs:__imp__wtoi
0x18007149f  nop     dword ptr [rax+rax+00h]
0x1800714a4  mov     [rsp+1D8h+var_C0], eax
0x1800714ab  mov     [rsp+1D8h+var_BC], r12b
0x1800714b3  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x1800714b8  lea     rdx, aAllowcellulard_0; "AllowCellularDataRoaming"
0x1800714bf  mov     rcx, rdi; this
0x1800714c2  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800714c7  test    eax, eax
0x1800714c9  jnz     short loc_1800714F0
0x1800714cb  mov     rcx, [rsp+1D8h+String]; String
0x1800714d0  test    rcx, rcx
0x1800714d3  jz      short loc_1800714F0
0x1800714d5  call    cs:__imp__wtoi
0x1800714dc  nop     dword ptr [rax+rax+00h]
0x1800714e1  mov     [rsp+1D8h+var_B8], eax
0x1800714e8  mov     [rsp+1D8h+var_B4], r12b
0x1800714f0  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x1800714f5  lea     rdx, aAllowconnected; "AllowConnectedDevices"
0x1800714fc  mov     rcx, rdi; this
0x1800714ff  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180071504  test    eax, eax
0x180071506  jnz     short loc_18007152D
0x180071508  mov     rcx, [rsp+1D8h+String]; String
0x18007150d  test    rcx, rcx
0x180071510  jz      short loc_18007152D
0x180071512  call    cs:__imp__wtoi
0x180071519  nop     dword ptr [rax+rax+00h]
0x18007151e  mov     [rsp+1D8h+var_B0], eax
0x180071525  mov     [rsp+1D8h+var_AC], r12b
0x18007152d  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180071532  lea     rdx, aAllowphonepcli; "AllowPhonePCLinking"
0x180071539  mov     rcx, rdi; this
0x18007153c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180071541  test    eax, eax
0x180071543  jnz     short loc_18007156A
0x180071545  mov     rcx, [rsp+1D8h+String]; String
0x18007154a  test    rcx, rcx
0x18007154d  jz      short loc_18007156A
0x18007154f  call    cs:__imp__wtoi
0x180071556  nop     dword ptr [rax+rax+00h]
0x18007155b  mov     [rsp+1D8h+var_A8], eax
0x180071562  mov     [rsp+1D8h+var_A4], r12b
0x18007156a  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18007156f  lea     rdx, aAllowvpnoverce; "AllowVPNOverCellular"
0x180071576  mov     rcx, rdi; this
0x180071579  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18007157e  test    eax, eax
0x180071580  jnz     short loc_1800715A7
0x180071582  mov     rcx, [rsp+1D8h+String]; String
0x180071587  test    rcx, rcx
0x18007158a  jz      short loc_1800715A7
0x18007158c  call    cs:__imp__wtoi
0x180071593  nop     dword ptr [rax+rax+00h]
0x180071598  mov     [rsp+1D8h+var_A0], eax
0x18007159f  mov     [rsp+1D8h+var_9C], r12b
0x1800715a7  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x1800715ac  lea     rdx, aAllowvpnroamin; "AllowVPNRoamingOverCellular"
0x1800715b3  mov     rcx, rdi; this
0x1800715b6  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800715bb  test    eax, eax
0x1800715bd  jnz     short loc_1800715E4
0x1800715bf  mov     rcx, [rsp+1D8h+String]; String
0x1800715c4  test    rcx, rcx
0x1800715c7  jz      short loc_1800715E4
0x1800715c9  call    cs:__imp__wtoi
0x1800715d0  nop     dword ptr [rax+rax+00h]
0x1800715d5  mov     [rsp+1D8h+var_98], eax
0x1800715dc  mov     [rsp+1D8h+var_94], r12b
0x1800715e4  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x1800715e9  lea     rdx, aDiableprinting; "DiablePrintingOverHTTP"
0x1800715f0  mov     rcx, rdi; this
0x1800715f3  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800715f8  test    eax, eax
0x1800715fa  jnz     short loc_180071613
0x1800715fc  mov     rdx, [rsp+1D8h+String]
0x180071601  test    rdx, rdx
0x180071604  jz      short loc_180071613
0x180071606  lea     rcx, [rsp+1D8h+instance]
0x18007160e  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x180071613  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180071618  lea     rdx, aDisabledownloa; "DisableDownloadingOfPrintDriversOverHTT"...
0x18007161f  mov     rcx, rdi; this
0x180071622  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180071627  test    eax, eax
0x180071629  jnz     short loc_180071642
0x18007162b  mov     rdx, [rsp+1D8h+String]
0x180071630  test    rdx, rdx
0x180071633  jz      short loc_180071642
0x180071635  lea     rcx, [rsp+1D8h+instance]
0x18007163d  call    MDM_VPNv2_01_Set_TrustedNetworkDetection
0x180071642  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180071647  lea     rdx, aDisableinterne; "DisableInternetDownloadForWebPublishing"...
0x18007164e  mov     rcx, rdi; this
0x180071651  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180071656  test    eax, eax
0x180071658  jnz     short loc_180071671
0x18007165a  mov     rdx, [rsp+1D8h+String]
0x18007165f  test    rdx, rdx
0x180071662  jz      short loc_180071671
0x180071664  lea     rcx, [rsp+1D8h+instance]
0x18007166c  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList
0x180071671  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180071676  lea     rdx, aDisallownetwor; "DisallowNetworkConnectivityActiveTests"
0x18007167d  mov     rcx, rdi; this
0x180071680  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180071685  test    eax, eax
0x180071687  jnz     short loc_1800716AE
0x180071689  mov     rcx, [rsp+1D8h+String]; String
0x18007168e  test    rcx, rcx
0x180071691  jz      short loc_1800716AE
0x180071693  call    cs:__imp__wtoi
0x18007169a  nop     dword ptr [rax+rax+00h]
0x18007169f  mov     [rsp+1D8h+var_60], eax
0x1800716a6  mov     [rsp+1D8h+var_5C], r12b
0x1800716ae  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x1800716b3  lea     rdx, aHardeneduncpat; "HardenedUNCPaths"
0x1800716ba  mov     rcx, rdi; this
0x1800716bd  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800716c2  test    eax, eax
0x1800716c4  jnz     short loc_1800716DD
0x1800716c6  mov     rdx, [rsp+1D8h+String]
0x1800716cb  test    rdx, rdx
0x1800716ce  jz      short loc_1800716DD
0x1800716d0  lea     rcx, [rsp+1D8h+instance]
0x1800716d8  call    MDM_VPNv2_User_01_Set_ProfileXML
0x1800716dd  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x1800716e2  lea     rdx, aProhibitinstal; "ProhibitInstallationAndConfigurationOfN"...
0x1800716e9  mov     rcx, rdi; this
0x1800716ec  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800716f1  test    eax, eax
  ... truncated ...
```
