# MDM_Policy_Config01_Connectivity02_InvokeGetInstance

- ea: `0x180071848`
- end: `0x180071e51`
- name: `MDM_Policy_Config01_Connectivity02_InvokeGetInstance`
- size: `1545`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800707b0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000506c`
- `0x1800050dc`
- `0x1800051bc`
- `0x1800051f4`
- `0x180005264`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x180071848`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180071ae7`
- `msvcrt!_wtoi` at `0x180071b1e`
- `msvcrt!_wtoi` at `0x180071b55`
- `msvcrt!_wtoi` at `0x180071b8c`
- `msvcrt!_wtoi` at `0x180071bc3`
- `msvcrt!_wtoi` at `0x180071bfa`
- `msvcrt!_wtoi` at `0x180071c31`
- `msvcrt!_wtoi` at `0x180071cf5`
- `msvcrt!_wtoi` at `0x180071ae7`
- `msvcrt!_wtoi` at `0x180071b1e`
- `msvcrt!_wtoi` at `0x180071b55`
- `msvcrt!_wtoi` at `0x180071b8c`
- `msvcrt!_wtoi` at `0x180071bc3`
- `msvcrt!_wtoi` at `0x180071bfa`
- `msvcrt!_wtoi` at `0x180071c31`
- `msvcrt!_wtoi` at `0x180071cf5`

## string_xrefs

- `0x180071ba6`: `AllowPhonePCLinking`
- `0x180071d0f`: `HardenedUNCPaths`
- `0x180071d3e`: `ProhibitInstallationAndConfigurationOfNetworkBridge`
- `0x1800718b7`: `MDM_Policy_Config01_Connectivity02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Connectivity02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int v5; // r14d
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
    v5 = 4;
    goto LABEL_68;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v11,
    "GetInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v10 = 0;
  v5 = CreateRequestHandlerInstance(
         (__int64)self,
         (wchar_t *)a2[1].serverName,
         (const unsigned __int16 *)a2[1].ft,
         (struct WmiNodeInfo *)&MDM_Policy_Config01_Connectivity02_NodeList,
         0xFu,
         0,
         &v10);
  if ( !v5 )
  {
    v11[4] = &v10;
    v12 = 1;
    v6 = v10;
    if ( !v10 )
    {
      v5 = 1;
      goto LABEL_68;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_Connectivity02_NodeList,
      0xFu);
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_68;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_68;
    }
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowBluetooth",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v18 = _wtoi(String);
      v19 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowCellularData",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v20 = _wtoi(String);
      v21 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowCellularDataRoaming",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v22 = _wtoi(String);
      v23 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowConnectedDevices",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v24 = _wtoi(String);
      v25 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowPhonePCLinking",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v26 = _wtoi(String);
      v27 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowVPNOverCellular",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v28 = _wtoi(String);
      v29 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"AllowVPNRoamingOverCellular",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v30 = _wtoi(String);
      v31 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DiablePrintingOverHTTP",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DisableDownloadingOfPrintDriversOverHTTP",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DisableInternetDownloadForWebPublishingAndOnlineOrderingWizards",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"DisallowNetworkConnectivityActiveTests",
                          (const unsigned __int16 **)&String)
      && String )
    {
      v32 = _wtoi(String);
      v33 = 1;
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"HardenedUNCPaths",
                          (const unsigned __int16 **)&String)
      && String )
    {
      MDM_VPNv2_User_01_Set_ProfileXML(&instance);
    }
    if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                          v6,
                          L"ProhibitInstallationAndConfigurationOfNetworkBridge",
                          (const unsigned __int16 **)&String)
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
  return v5;
}

```

## disassembly

```asm
0x180071848  mov     [rsp+arg_10], rbx
0x18007184d  push    rsi
0x18007184e  push    rdi
0x18007184f  push    r12
0x180071851  push    r14
0x180071853  push    r15
0x180071855  sub     rsp, 1B0h
0x18007185c  mov     rax, cs:__security_cookie
0x180071863  xor     rax, rsp
0x180071866  mov     [rsp+1D8h+var_38], rax
0x18007186e  mov     rsi, rdx
0x180071871  mov     r15, rcx
0x180071874  xor     ebx, ebx
0x180071876  mov     [rsp+1D8h+String], rbx
0x18007187b  xor     edx, edx; Val
0x18007187d  mov     r8d, 0F0h; Size
0x180071883  lea     rcx, [rsp+1D8h+instance]; void *
0x18007188b  call    memset_0
0x180071890  mov     [rsp+1D8h+var_150], ebx
0x180071897  mov     [rsp+1D8h+var_14C], bl
0x18007189e  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800718a5  mov     [rsp+1D8h+var_180], rax
0x1800718aa  lea     rax, [rsp+1D8h+var_150]
0x1800718b2  mov     [rsp+1D8h+var_178], rax
0x1800718b7  lea     rax, aMdmPolicyConfi_107; "MDM_Policy_Config01_Connectivity02"
0x1800718be  mov     [rsp+1D8h+var_170], rax
0x1800718c3  lea     rcx, [rsp+1D8h+var_150]
0x1800718cb  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800718d0  mov     eax, cs:dword_180380B68
0x1800718d6  cmp     eax, 5
0x1800718d9  jbe     short loc_18007194A
0x1800718db  mov     rdx, 200000000000h
0x1800718e5  lea     rcx, dword_180380B68
0x1800718ec  call    _tlgKeywordOn
0x1800718f1  test    al, al
0x1800718f3  jz      short loc_18007194A
0x1800718f5  cmp     [rsp+1D8h+var_14C], bl
0x1800718fc  jz      short loc_18007192C
0x1800718fe  cmp     [rsp+1D8h+var_138], ebx
0x180071905  jnz     short loc_180071922
0x180071907  cmp     [rsp+1D8h+var_134], ebx
0x18007190e  jnz     short loc_180071922
0x180071910  cmp     [rsp+1D8h+var_130], ebx
0x180071917  jnz     short loc_180071922
0x180071919  cmp     [rsp+1D8h+var_12C], ebx
0x180071920  jz      short loc_18007192C
0x180071922  lea     r9, [rsp+1D8h+var_138]
0x18007192a  jmp     short loc_18007192F
0x18007192c  mov     r9, rbx
0x18007192f  lea     r8, [rsp+1D8h+var_148]
0x180071937  lea     rdx, byte_18036EFEF
0x18007193e  lea     rcx, dword_180380B68
0x180071945  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18007194a  cmp     [rsi+48h], bl
0x18007194d  jz      loc_180071DB0
0x180071953  mov     [rsp+1D8h+var_190], bl
0x180071957  cmp     [rsi+58h], bl
0x18007195a  jz      loc_180071DB0
0x180071960  mov     r9, [rsi+40h]; unsigned __int16 *
0x180071964  mov     r8, [rsi+50h]; unsigned __int16 *
0x180071968  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x18007196f  lea     rcx, [rsp+1D8h+var_180]; this
0x180071974  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180071979  nop
0x18007197a  mov     [rsp+1D8h+var_188], rbx
0x18007197f  lea     rax, [rsp+1D8h+var_188]
0x180071984  mov     [rsp+1D8h+var_1A8], rax
0x180071989  mov     [rsp+1D8h+var_1B0], ebx
0x18007198d  mov     [rsp+1D8h+var_1B8], 0Fh
0x180071995  lea     r9, ?MDM_Policy_Config01_Connectivity02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Connectivity02_NodeList
0x18007199c  mov     r8, [rsi+40h]
0x1800719a0  mov     rdx, [rsi+50h]
0x1800719a4  mov     rcx, r15
0x1800719a7  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800719ac  mov     r14d, eax
0x1800719af  test    eax, eax
0x1800719b1  jz      short loc_1800719B8
0x1800719b3  jmp     loc_180071DB6
0x1800719b8  lea     rax, [rsp+1D8h+var_188]
0x1800719bd  mov     [rsp+1D8h+var_160], rax
0x1800719c2  mov     r12d, 1
0x1800719c8  mov     [rsp+1D8h+var_158], r12b
0x1800719d0  mov     rdi, [rsp+1D8h+var_188]
0x1800719d5  test    rdi, rdi
0x1800719d8  jnz     short loc_1800719E2
0x1800719da  mov     r14d, r12d
0x1800719dd  jmp     loc_180071DB6
0x1800719e2  mov     r9d, 0Fh; unsigned int
0x1800719e8  lea     r8, ?MDM_Policy_Config01_Connectivity02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800719ef  mov     rdx, rsi; struct _MI_Instance *
0x1800719f2  mov     rcx, rdi; this
0x1800719f5  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800719fa  mov     rax, [rdi]
0x1800719fd  mov     rcx, rdi
0x180071a00  mov     rax, [rax+10h]
0x180071a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a09  mov     r14d, eax
0x180071a0c  test    eax, eax
0x180071a0e  jz      short loc_180071A2E
0x180071a10  mov     rcx, [rsp+1D8h+var_188]
0x180071a15  test    rcx, rcx
0x180071a18  jz      short loc_180071A29
0x180071a1a  mov     rax, [rcx]
0x180071a1d  mov     edx, r12d
0x180071a20  mov     rax, [rax]
0x180071a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a28  nop
0x180071a29  jmp     loc_180071DB6
0x180071a2e  mov     rax, [rdi]
0x180071a31  mov     rcx, rdi
0x180071a34  mov     rax, [rax+8]
0x180071a38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a3d  mov     r14d, eax
0x180071a40  test    eax, eax
0x180071a42  jz      short loc_180071A62
0x180071a44  mov     rcx, [rsp+1D8h+var_188]
0x180071a49  test    rcx, rcx
0x180071a4c  jz      short loc_180071A5D
0x180071a4e  mov     rax, [rcx]
0x180071a51  mov     edx, r12d
0x180071a54  mov     rax, [rax]
0x180071a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a5c  nop
0x180071a5d  jmp     loc_180071DB6
0x180071a62  lea     r8, [rsp+1D8h+instance]; instance
0x180071a6a  lea     rdx, MDM_Policy_Config01_Connectivity02_rtti; classDecl
0x180071a71  mov     rcx, r15; context
0x180071a74  call    MI_Context_ConstructInstance
0x180071a79  mov     r14d, eax
0x180071a7c  test    eax, eax
0x180071a7e  jz      short loc_180071A9E
0x180071a80  mov     rcx, [rsp+1D8h+var_188]
0x180071a85  test    rcx, rcx
0x180071a88  jz      short loc_180071A99
0x180071a8a  mov     rax, [rcx]
0x180071a8d  mov     edx, r12d
0x180071a90  mov     rax, [rax]
0x180071a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a98  nop
0x180071a99  jmp     loc_180071DB6
0x180071a9e  mov     [rsp+1D8h+var_190], r12b
0x180071aa3  mov     rdx, [rsi+40h]
0x180071aa7  lea     rcx, [rsp+1D8h+instance]
0x180071aaf  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180071ab4  mov     rdx, [rsi+50h]
0x180071ab8  lea     rcx, [rsp+1D8h+instance]
0x180071ac0  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180071ac5  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180071aca  lea     rdx, aAllowbluetooth; "AllowBluetooth"
0x180071ad1  mov     rcx, rdi; this
0x180071ad4  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180071ad9  test    eax, eax
0x180071adb  jnz     short loc_180071AFC
0x180071add  mov     rcx, [rsp+1D8h+String]; String
0x180071ae2  test    rcx, rcx
0x180071ae5  jz      short loc_180071AFC
0x180071ae7  call    cs:__imp__wtoi
0x180071aed  mov     [rsp+1D8h+var_C8], eax
0x180071af4  mov     [rsp+1D8h+var_C4], r12b
0x180071afc  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180071b01  lea     rdx, aAllowcellulard; "AllowCellularData"
0x180071b08  mov     rcx, rdi; this
0x180071b0b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180071b10  test    eax, eax
0x180071b12  jnz     short loc_180071B33
0x180071b14  mov     rcx, [rsp+1D8h+String]; String
0x180071b19  test    rcx, rcx
0x180071b1c  jz      short loc_180071B33
0x180071b1e  call    cs:__imp__wtoi
0x180071b24  mov     [rsp+1D8h+var_C0], eax
0x180071b2b  mov     [rsp+1D8h+var_BC], r12b
0x180071b33  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180071b38  lea     rdx, aAllowcellulard_0; "AllowCellularDataRoaming"
0x180071b3f  mov     rcx, rdi; this
0x180071b42  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180071b47  test    eax, eax
0x180071b49  jnz     short loc_180071B6A
0x180071b4b  mov     rcx, [rsp+1D8h+String]; String
0x180071b50  test    rcx, rcx
0x180071b53  jz      short loc_180071B6A
0x180071b55  call    cs:__imp__wtoi
0x180071b5b  mov     [rsp+1D8h+var_B8], eax
0x180071b62  mov     [rsp+1D8h+var_B4], r12b
0x180071b6a  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180071b6f  lea     rdx, aAllowconnected; "AllowConnectedDevices"
0x180071b76  mov     rcx, rdi; this
0x180071b79  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180071b7e  test    eax, eax
0x180071b80  jnz     short loc_180071BA1
0x180071b82  mov     rcx, [rsp+1D8h+String]; String
0x180071b87  test    rcx, rcx
0x180071b8a  jz      short loc_180071BA1
0x180071b8c  call    cs:__imp__wtoi
0x180071b92  mov     [rsp+1D8h+var_B0], eax
0x180071b99  mov     [rsp+1D8h+var_AC], r12b
0x180071ba1  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180071ba6  lea     rdx, aAllowphonepcli; "AllowPhonePCLinking"
0x180071bad  mov     rcx, rdi; this
0x180071bb0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180071bb5  test    eax, eax
0x180071bb7  jnz     short loc_180071BD8
0x180071bb9  mov     rcx, [rsp+1D8h+String]; String
0x180071bbe  test    rcx, rcx
0x180071bc1  jz      short loc_180071BD8
0x180071bc3  call    cs:__imp__wtoi
0x180071bc9  mov     [rsp+1D8h+var_A8], eax
0x180071bd0  mov     [rsp+1D8h+var_A4], r12b
0x180071bd8  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180071bdd  lea     rdx, aAllowvpnoverce; "AllowVPNOverCellular"
0x180071be4  mov     rcx, rdi; this
0x180071be7  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180071bec  test    eax, eax
0x180071bee  jnz     short loc_180071C0F
0x180071bf0  mov     rcx, [rsp+1D8h+String]; String
0x180071bf5  test    rcx, rcx
0x180071bf8  jz      short loc_180071C0F
0x180071bfa  call    cs:__imp__wtoi
0x180071c00  mov     [rsp+1D8h+var_A0], eax
0x180071c07  mov     [rsp+1D8h+var_9C], r12b
0x180071c0f  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180071c14  lea     rdx, aAllowvpnroamin; "AllowVPNRoamingOverCellular"
0x180071c1b  mov     rcx, rdi; this
0x180071c1e  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180071c23  test    eax, eax
0x180071c25  jnz     short loc_180071C46
0x180071c27  mov     rcx, [rsp+1D8h+String]; String
0x180071c2c  test    rcx, rcx
0x180071c2f  jz      short loc_180071C46
0x180071c31  call    cs:__imp__wtoi
0x180071c37  mov     [rsp+1D8h+var_98], eax
0x180071c3e  mov     [rsp+1D8h+var_94], r12b
0x180071c46  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180071c4b  lea     rdx, aDiableprinting; "DiablePrintingOverHTTP"
0x180071c52  mov     rcx, rdi; this
0x180071c55  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180071c5a  test    eax, eax
0x180071c5c  jnz     short loc_180071C75
0x180071c5e  mov     rdx, [rsp+1D8h+String]
0x180071c63  test    rdx, rdx
0x180071c66  jz      short loc_180071C75
0x180071c68  lea     rcx, [rsp+1D8h+instance]
0x180071c70  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x180071c75  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180071c7a  lea     rdx, aDisabledownloa; "DisableDownloadingOfPrintDriversOverHTT"...
0x180071c81  mov     rcx, rdi; this
0x180071c84  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180071c89  test    eax, eax
0x180071c8b  jnz     short loc_180071CA4
0x180071c8d  mov     rdx, [rsp+1D8h+String]
0x180071c92  test    rdx, rdx
0x180071c95  jz      short loc_180071CA4
0x180071c97  lea     rcx, [rsp+1D8h+instance]
0x180071c9f  call    MDM_VPNv2_01_Set_TrustedNetworkDetection
0x180071ca4  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180071ca9  lea     rdx, aDisableinterne; "DisableInternetDownloadForWebPublishing"...
0x180071cb0  mov     rcx, rdi; this
0x180071cb3  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180071cb8  test    eax, eax
0x180071cba  jnz     short loc_180071CD3
0x180071cbc  mov     rdx, [rsp+1D8h+String]
0x180071cc1  test    rdx, rdx
0x180071cc4  jz      short loc_180071CD3
0x180071cc6  lea     rcx, [rsp+1D8h+instance]
0x180071cce  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList
0x180071cd3  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180071cd8  lea     rdx, aDisallownetwor; "DisallowNetworkConnectivityActiveTests"
0x180071cdf  mov     rcx, rdi; this
0x180071ce2  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180071ce7  test    eax, eax
0x180071ce9  jnz     short loc_180071D0A
0x180071ceb  mov     rcx, [rsp+1D8h+String]; String
0x180071cf0  test    rcx, rcx
0x180071cf3  jz      short loc_180071D0A
0x180071cf5  call    cs:__imp__wtoi
0x180071cfb  mov     [rsp+1D8h+var_60], eax
0x180071d02  mov     [rsp+1D8h+var_5C], r12b
0x180071d0a  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180071d0f  lea     rdx, aHardeneduncpat; "HardenedUNCPaths"
0x180071d16  mov     rcx, rdi; this
0x180071d19  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180071d1e  test    eax, eax
0x180071d20  jnz     short loc_180071D39
0x180071d22  mov     rdx, [rsp+1D8h+String]
0x180071d27  test    rdx, rdx
0x180071d2a  jz      short loc_180071D39
0x180071d2c  lea     rcx, [rsp+1D8h+instance]
0x180071d34  call    MDM_VPNv2_User_01_Set_ProfileXML
0x180071d39  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180071d3e  lea     rdx, aProhibitinstal; "ProhibitInstallationAndConfigurationOfN"...
0x180071d45  mov     rcx, rdi; this
0x180071d48  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180071d4d  test    eax, eax
0x180071d4f  jnz     short loc_180071D68
0x180071d51  mov     rdx, [rsp+1D8h+String]
0x180071d56  test    rdx, rdx
0x180071d59  jz      short loc_180071D68
0x180071d5b  lea     rcx, [rsp+1D8h+instance]
0x180071d63  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetZoneTemplate
0x180071d68  lea     rdx, [rsp+1D8h+instance]
0x180071d70  mov     rcx, r15; self
  ... truncated ...
```
