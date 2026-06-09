# MDM_Policy_Result01_Storage02_InvokeGetInstance

- ea: `0x180198f68`
- end: `0x18019950e`
- name: `MDM_Policy_Result01_Storage02_InvokeGetInstance`
- size: `1446`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180197fc0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000506c`
- `0x180005184`
- `0x180005264`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x180198f68`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180199205`
- `msvcrt!_wtoi` at `0x18019923c`
- `msvcrt!_wtoi` at `0x180199273`
- `msvcrt!_wtoi` at `0x1801992aa`
- `msvcrt!_wtoi` at `0x1801992e1`
- `msvcrt!_wtoi` at `0x180199318`
- `msvcrt!_wtoi` at `0x18019934f`
- `msvcrt!_wtoi` at `0x1801993b5`
- `msvcrt!_wtoi` at `0x180199205`
- `msvcrt!_wtoi` at `0x18019923c`
- `msvcrt!_wtoi` at `0x180199273`
- `msvcrt!_wtoi` at `0x1801992aa`
- `msvcrt!_wtoi` at `0x1801992e1`
- `msvcrt!_wtoi` at `0x180199318`
- `msvcrt!_wtoi` at `0x18019934f`
- `msvcrt!_wtoi` at `0x1801993b5`

## string_xrefs

- `0x1801991e8`: `AllowDiskHealthModelUpdates`
- `0x180199256`: `AllowStorageSenseTemporaryFilesCleanup`
- `0x18019928d`: `ConfigStorageSenseCloudContentDehydrationThreshold`
- `0x1801992c4`: `ConfigStorageSenseDownloadsCleanupThreshold`
- `0x1801992fb`: `ConfigStorageSenseGlobalCadence`
- `0x180199332`: `ConfigStorageSenseRecycleBinCleanupThreshold`
- `0x180199398`: `RemovableDiskDenyWriteAccess`
- `0x1801993cf`: `WPDDevicesDenyReadAccessPerDevice`
- `0x1801993fe`: `WPDDevicesDenyWriteAccessPerDevice`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Storage02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int v5; // esi
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
  v11[2] = "MDM_Policy_Result01_Storage02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      word_180345D22,
      v15,
      v4);
  }
  if ( LOBYTE(a2[1].classDecl) && (v9 = 0, LOBYTE(a2[1].nameSpace)) )
  {
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
           (struct WmiNodeInfo *)&MDM_Policy_Result01_Storage02_NodeList,
           0xDu,
           0,
           &v10);
    if ( !v5 )
    {
      v11[4] = &v10;
      v12 = 1;
      v6 = v10;
      if ( v10 )
      {
        WmiRequestHandler::SetRequestMIInstance(
          v10,
          a2,
          (struct WmiNodeInfo *)&MDM_Policy_Result01_Storage02_NodeList,
          0xDu);
        v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v5 )
        {
          if ( v10 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
        }
        else
        {
          v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
          if ( v5 )
          {
            if ( v10 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
          }
          else
          {
            v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_Storage02_rtti, &instance);
            if ( v5 )
            {
              if ( v10 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
            }
            else
            {
              v9 = 1;
              MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowDiskHealthModelUpdates",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v18 = _wtoi(String);
                v19 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowStorageSenseGlobal",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowStorageSenseTemporaryFilesCleanup",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ConfigStorageSenseCloudContentDehydrationThreshold",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ConfigStorageSenseDownloadsCleanupThreshold",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ConfigStorageSenseGlobalCadence",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ConfigStorageSenseRecycleBinCleanupThreshold",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"EnhancedStorageDevices",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"RemovableDiskDenyWriteAccess",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"WPDDevicesDenyReadAccessPerDevice",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"WPDDevicesDenyWriteAccessPerDevice",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList(&instance);
              }
              MI_Instance_Destruct((MI_Instance *)self);
              if ( v10 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
              MI_Instance_Destruct(&instance);
            }
          }
        }
      }
      else
      {
        v5 = 1;
      }
    }
  }
  else
  {
    v5 = 4;
  }
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v11, "GetInstanceEnd", v5);
  v13 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_1803408B1,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return v5;
}

```

## disassembly

```asm
0x180198f68  mov     [rsp+arg_10], rbx
0x180198f6d  push    rsi
0x180198f6e  push    rdi
0x180198f6f  push    r12
0x180198f71  push    r14
0x180198f73  push    r15
0x180198f75  sub     rsp, 190h
0x180198f7c  mov     rax, cs:__security_cookie
0x180198f83  xor     rax, rsp
0x180198f86  mov     [rsp+1B8h+var_38], rax
0x180198f8e  mov     r14, rdx
0x180198f91  mov     r15, rcx
0x180198f94  xor     ebx, ebx
0x180198f96  mov     [rsp+1B8h+String], rbx
0x180198f9b  xor     edx, edx; Val
0x180198f9d  mov     r8d, 0D0h; Size
0x180198fa3  lea     rcx, [rsp+1B8h+instance]; void *
0x180198fab  call    memset_0
0x180198fb0  mov     [rsp+1B8h+var_130], ebx
0x180198fb7  mov     [rsp+1B8h+var_12C], bl
0x180198fbe  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180198fc5  mov     [rsp+1B8h+var_160], rax
0x180198fca  lea     rax, [rsp+1B8h+var_130]
0x180198fd2  mov     [rsp+1B8h+var_158], rax
0x180198fd7  lea     rax, aMdmPolicyResul_127; "MDM_Policy_Result01_Storage02"
0x180198fde  mov     [rsp+1B8h+var_150], rax
0x180198fe3  lea     rcx, [rsp+1B8h+var_130]
0x180198feb  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180198ff0  mov     eax, cs:dword_180380B68
0x180198ff6  cmp     eax, 5
0x180198ff9  jbe     short loc_18019906A
0x180198ffb  mov     rdx, 200000000000h
0x180199005  lea     rcx, dword_180380B68
0x18019900c  call    _tlgKeywordOn
0x180199011  test    al, al
0x180199013  jz      short loc_18019906A
0x180199015  cmp     [rsp+1B8h+var_12C], bl
0x18019901c  jz      short loc_18019904C
0x18019901e  cmp     [rsp+1B8h+var_118], ebx
0x180199025  jnz     short loc_180199042
0x180199027  cmp     [rsp+1B8h+var_114], ebx
0x18019902e  jnz     short loc_180199042
0x180199030  cmp     [rsp+1B8h+var_110], ebx
0x180199037  jnz     short loc_180199042
0x180199039  cmp     [rsp+1B8h+var_10C], ebx
0x180199040  jz      short loc_18019904C
0x180199042  lea     r9, [rsp+1B8h+var_118]
0x18019904a  jmp     short loc_18019904F
0x18019904c  mov     r9, rbx
0x18019904f  lea     r8, [rsp+1B8h+var_128]
0x180199057  lea     rdx, word_180345D22
0x18019905e  lea     rcx, dword_180380B68
0x180199065  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18019906a  cmp     [r14+48h], bl
0x18019906e  jz      loc_18019946F
0x180199074  mov     [rsp+1B8h+var_170], bl
0x180199078  cmp     [r14+58h], bl
0x18019907c  jz      loc_18019946F
0x180199082  mov     r9, [r14+40h]; unsigned __int16 *
0x180199086  mov     r8, [r14+50h]; unsigned __int16 *
0x18019908a  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x180199091  lea     rcx, [rsp+1B8h+var_160]; this
0x180199096  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18019909b  nop
0x18019909c  mov     [rsp+1B8h+var_168], rbx
0x1801990a1  lea     rax, [rsp+1B8h+var_168]
0x1801990a6  mov     [rsp+1B8h+var_188], rax
0x1801990ab  mov     [rsp+1B8h+var_190], ebx
0x1801990af  mov     [rsp+1B8h+var_198], 0Dh
0x1801990b7  lea     r9, ?MDM_Policy_Result01_Storage02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Storage02_NodeList
0x1801990be  mov     r8, [r14+40h]
0x1801990c2  mov     rdx, [r14+50h]
0x1801990c6  mov     rcx, r15
0x1801990c9  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1801990ce  mov     esi, eax
0x1801990d0  test    eax, eax
0x1801990d2  jz      short loc_1801990D9
0x1801990d4  jmp     loc_180199474
0x1801990d9  lea     rax, [rsp+1B8h+var_168]
0x1801990de  mov     [rsp+1B8h+var_140], rax
0x1801990e3  mov     r12d, 1
0x1801990e9  mov     [rsp+1B8h+var_138], r12b
0x1801990f1  mov     rdi, [rsp+1B8h+var_168]
0x1801990f6  test    rdi, rdi
0x1801990f9  jnz     short loc_180199103
0x1801990fb  mov     esi, r12d
0x1801990fe  jmp     loc_180199474
0x180199103  mov     r9d, 0Dh; unsigned int
0x180199109  lea     r8, ?MDM_Policy_Result01_Storage02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180199110  mov     rdx, r14; struct _MI_Instance *
0x180199113  mov     rcx, rdi; this
0x180199116  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18019911b  mov     rax, [rdi]
0x18019911e  mov     rcx, rdi
0x180199121  mov     rax, [rax+10h]
0x180199125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019912a  mov     esi, eax
0x18019912c  test    eax, eax
0x18019912e  jz      short loc_18019914E
0x180199130  mov     rcx, [rsp+1B8h+var_168]
0x180199135  test    rcx, rcx
0x180199138  jz      short loc_180199149
0x18019913a  mov     rax, [rcx]
0x18019913d  mov     edx, r12d
0x180199140  mov     rax, [rax]
0x180199143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199148  nop
0x180199149  jmp     loc_180199474
0x18019914e  mov     rax, [rdi]
0x180199151  mov     rcx, rdi
0x180199154  mov     rax, [rax+8]
0x180199158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019915d  mov     esi, eax
0x18019915f  test    eax, eax
0x180199161  jz      short loc_180199181
0x180199163  mov     rcx, [rsp+1B8h+var_168]
0x180199168  test    rcx, rcx
0x18019916b  jz      short loc_18019917C
0x18019916d  mov     rax, [rcx]
0x180199170  mov     edx, r12d
0x180199173  mov     rax, [rax]
0x180199176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019917b  nop
0x18019917c  jmp     loc_180199474
0x180199181  lea     r8, [rsp+1B8h+instance]; instance
0x180199189  lea     rdx, MDM_Policy_Result01_Storage02_rtti; classDecl
0x180199190  mov     rcx, r15; context
0x180199193  call    MI_Context_ConstructInstance
0x180199198  mov     esi, eax
0x18019919a  test    eax, eax
0x18019919c  jz      short loc_1801991BC
0x18019919e  mov     rcx, [rsp+1B8h+var_168]
0x1801991a3  test    rcx, rcx
0x1801991a6  jz      short loc_1801991B7
0x1801991a8  mov     rax, [rcx]
0x1801991ab  mov     edx, r12d
0x1801991ae  mov     rax, [rax]
0x1801991b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801991b6  nop
0x1801991b7  jmp     loc_180199474
0x1801991bc  mov     [rsp+1B8h+var_170], r12b
0x1801991c1  mov     rdx, [r14+40h]
0x1801991c5  lea     rcx, [rsp+1B8h+instance]
0x1801991cd  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801991d2  mov     rdx, [r14+50h]
0x1801991d6  lea     rcx, [rsp+1B8h+instance]
0x1801991de  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1801991e3  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1801991e8  lea     rdx, aAllowdiskhealt; "AllowDiskHealthModelUpdates"
0x1801991ef  mov     rcx, rdi; this
0x1801991f2  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801991f7  test    eax, eax
0x1801991f9  jnz     short loc_18019921A
0x1801991fb  mov     rcx, [rsp+1B8h+String]; String
0x180199200  test    rcx, rcx
0x180199203  jz      short loc_18019921A
0x180199205  call    cs:__imp__wtoi
0x18019920b  mov     [rsp+1B8h+var_A8], eax
0x180199212  mov     [rsp+1B8h+var_A4], r12b
0x18019921a  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x18019921f  lea     rdx, aAllowstoragese_0; "AllowStorageSenseGlobal"
0x180199226  mov     rcx, rdi; this
0x180199229  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019922e  test    eax, eax
0x180199230  jnz     short loc_180199251
0x180199232  mov     rcx, [rsp+1B8h+String]; String
0x180199237  test    rcx, rcx
0x18019923a  jz      short loc_180199251
0x18019923c  call    cs:__imp__wtoi
0x180199242  mov     [rsp+1B8h+var_A0], eax
0x180199249  mov     [rsp+1B8h+var_9C], r12b
0x180199251  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x180199256  lea     rdx, aAllowstoragese; "AllowStorageSenseTemporaryFilesCleanup"
0x18019925d  mov     rcx, rdi; this
0x180199260  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180199265  test    eax, eax
0x180199267  jnz     short loc_180199288
0x180199269  mov     rcx, [rsp+1B8h+String]; String
0x18019926e  test    rcx, rcx
0x180199271  jz      short loc_180199288
0x180199273  call    cs:__imp__wtoi
0x180199279  mov     [rsp+1B8h+var_98], eax
0x180199280  mov     [rsp+1B8h+var_94], r12b
0x180199288  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x18019928d  lea     rdx, aConfigstorages; "ConfigStorageSenseCloudContentDehydrati"...
0x180199294  mov     rcx, rdi; this
0x180199297  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019929c  test    eax, eax
0x18019929e  jnz     short loc_1801992BF
0x1801992a0  mov     rcx, [rsp+1B8h+String]; String
0x1801992a5  test    rcx, rcx
0x1801992a8  jz      short loc_1801992BF
0x1801992aa  call    cs:__imp__wtoi
0x1801992b0  mov     [rsp+1B8h+var_90], eax
0x1801992b7  mov     [rsp+1B8h+var_8C], r12b
0x1801992bf  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1801992c4  lea     rdx, aConfigstorages_2; "ConfigStorageSenseDownloadsCleanupThres"...
0x1801992cb  mov     rcx, rdi; this
0x1801992ce  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801992d3  test    eax, eax
0x1801992d5  jnz     short loc_1801992F6
0x1801992d7  mov     rcx, [rsp+1B8h+String]; String
0x1801992dc  test    rcx, rcx
0x1801992df  jz      short loc_1801992F6
0x1801992e1  call    cs:__imp__wtoi
0x1801992e7  mov     [rsp+1B8h+var_88], eax
0x1801992ee  mov     [rsp+1B8h+var_84], r12b
0x1801992f6  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1801992fb  lea     rdx, aConfigstorages_0; "ConfigStorageSenseGlobalCadence"
0x180199302  mov     rcx, rdi; this
0x180199305  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019930a  test    eax, eax
0x18019930c  jnz     short loc_18019932D
0x18019930e  mov     rcx, [rsp+1B8h+String]; String
0x180199313  test    rcx, rcx
0x180199316  jz      short loc_18019932D
0x180199318  call    cs:__imp__wtoi
0x18019931e  mov     [rsp+1B8h+var_80], eax
0x180199325  mov     [rsp+1B8h+var_7C], r12b
0x18019932d  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x180199332  lea     rdx, aConfigstorages_1; "ConfigStorageSenseRecycleBinCleanupThre"...
0x180199339  mov     rcx, rdi; this
0x18019933c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180199341  test    eax, eax
0x180199343  jnz     short loc_180199364
0x180199345  mov     rcx, [rsp+1B8h+String]; String
0x18019934a  test    rcx, rcx
0x18019934d  jz      short loc_180199364
0x18019934f  call    cs:__imp__wtoi
0x180199355  mov     [rsp+1B8h+var_78], eax
0x18019935c  mov     [rsp+1B8h+var_74], r12b
0x180199364  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x180199369  lea     rdx, aEnhancedstorag; "EnhancedStorageDevices"
0x180199370  mov     rcx, rdi; this
0x180199373  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180199378  test    eax, eax
0x18019937a  jnz     short loc_180199393
0x18019937c  mov     rdx, [rsp+1B8h+String]
0x180199381  test    rdx, rdx
0x180199384  jz      short loc_180199393
0x180199386  lea     rcx, [rsp+1B8h+instance]
0x18019938e  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x180199393  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x180199398  lea     rdx, aRemovablediskd; "RemovableDiskDenyWriteAccess"
0x18019939f  mov     rcx, rdi; this
0x1801993a2  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801993a7  test    eax, eax
0x1801993a9  jnz     short loc_1801993CA
0x1801993ab  mov     rcx, [rsp+1B8h+String]; String
0x1801993b0  test    rcx, rcx
0x1801993b3  jz      short loc_1801993CA
0x1801993b5  call    cs:__imp__wtoi
0x1801993bb  mov     [rsp+1B8h+var_60], eax
0x1801993c2  mov     [rsp+1B8h+var_5C], r12b
0x1801993ca  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1801993cf  lea     rdx, aWpddevicesdeny_1; "WPDDevicesDenyReadAccessPerDevice"
0x1801993d6  mov     rcx, rdi; this
0x1801993d9  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801993de  test    eax, eax
0x1801993e0  jnz     short loc_1801993F9
0x1801993e2  mov     rdx, [rsp+1B8h+String]
0x1801993e7  test    rdx, rdx
0x1801993ea  jz      short loc_1801993F9
0x1801993ec  lea     rcx, [rsp+1B8h+instance]
0x1801993f4  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList
0x1801993f9  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1801993fe  lea     rdx, aWpddevicesdeny_2; "WPDDevicesDenyWriteAccessPerDevice"
0x180199405  mov     rcx, rdi; this
0x180199408  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18019940d  test    eax, eax
0x18019940f  jnz     short loc_180199428
0x180199411  mov     rdx, [rsp+1B8h+String]
0x180199416  test    rdx, rdx
0x180199419  jz      short loc_180199428
0x18019941b  lea     rcx, [rsp+1B8h+instance]
0x180199423  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList
0x180199428  lea     rdx, [rsp+1B8h+instance]
0x180199430  mov     rcx, r15; self
0x180199433  call    MI_Instance_Destruct
0x180199438  nop
0x180199439  mov     rcx, [rsp+1B8h+var_168]
0x18019943e  test    rcx, rcx
0x180199441  jz      short loc_180199452
0x180199443  mov     rax, [rcx]
0x180199446  mov     edx, r12d
0x180199449  mov     rax, [rax]
0x18019944c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199451  nop
0x180199452  jmp     short loc_180199460
0x180199454  xor     ebx, ebx
0x180199456  mov     esi, dword ptr [rsp+1B8h+String]
0x18019945a  cmp     [rsp+1B8h+var_170], bl
0x18019945e  jz      short loc_180199474
0x180199460  lea     rcx, [rsp+1B8h+instance]; self
0x180199468  call    MI_Instance_Destruct
0x18019946d  jmp     short loc_180199474
0x18019946f  mov     esi, 4
0x180199474  mov     r8d, esi; int
0x180199477  lea     rdx, aGetinstanceend; "GetInstanceEnd"
0x18019947e  lea     rcx, [rsp+1B8h+var_160]; this
  ... truncated ...
```
