# MDM_Policy_Config01_Storage02_InvokeGetInstance

- ea: `0x1800e1ba8`
- end: `0x1800e214e`
- name: `MDM_Policy_Config01_Storage02_InvokeGetInstance`
- size: `1446`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800e0c00`

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
- `0x1800e1ba8`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800e1e45`
- `msvcrt!_wtoi` at `0x1800e1e7c`
- `msvcrt!_wtoi` at `0x1800e1eb3`
- `msvcrt!_wtoi` at `0x1800e1eea`
- `msvcrt!_wtoi` at `0x1800e1f21`
- `msvcrt!_wtoi` at `0x1800e1f58`
- `msvcrt!_wtoi` at `0x1800e1f8f`
- `msvcrt!_wtoi` at `0x1800e1ff5`
- `msvcrt!_wtoi` at `0x1800e1e45`
- `msvcrt!_wtoi` at `0x1800e1e7c`
- `msvcrt!_wtoi` at `0x1800e1eb3`
- `msvcrt!_wtoi` at `0x1800e1eea`
- `msvcrt!_wtoi` at `0x1800e1f21`
- `msvcrt!_wtoi` at `0x1800e1f58`
- `msvcrt!_wtoi` at `0x1800e1f8f`
- `msvcrt!_wtoi` at `0x1800e1ff5`

## string_xrefs

- `0x1800e1e28`: `AllowDiskHealthModelUpdates`
- `0x1800e1e96`: `AllowStorageSenseTemporaryFilesCleanup`
- `0x1800e1ecd`: `ConfigStorageSenseCloudContentDehydrationThreshold`
- `0x1800e1f04`: `ConfigStorageSenseDownloadsCleanupThreshold`
- `0x1800e1f3b`: `ConfigStorageSenseGlobalCadence`
- `0x1800e1f72`: `ConfigStorageSenseRecycleBinCleanupThreshold`
- `0x1800e1fd8`: `RemovableDiskDenyWriteAccess`
- `0x1800e200f`: `WPDDevicesDenyReadAccessPerDevice`
- `0x1800e203e`: `WPDDevicesDenyWriteAccessPerDevice`
- `0x1800e1c17`: `MDM_Policy_Config01_Storage02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Storage02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
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
    v5 = 4;
    goto LABEL_62;
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
         (struct WmiNodeInfo *)&MDM_Policy_Config01_Storage02_NodeList,
         0xDu,
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
      goto LABEL_62;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v10,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_Storage02_NodeList,
      0xDu);
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v10 )
        goto LABEL_62;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
      goto LABEL_62;
    }
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
  return v5;
}

```

## disassembly

```asm
0x1800e1ba8  mov     [rsp+arg_10], rbx
0x1800e1bad  push    rsi
0x1800e1bae  push    rdi
0x1800e1baf  push    r12
0x1800e1bb1  push    r14
0x1800e1bb3  push    r15
0x1800e1bb5  sub     rsp, 190h
0x1800e1bbc  mov     rax, cs:__security_cookie
0x1800e1bc3  xor     rax, rsp
0x1800e1bc6  mov     [rsp+1B8h+var_38], rax
0x1800e1bce  mov     r14, rdx
0x1800e1bd1  mov     r15, rcx
0x1800e1bd4  xor     ebx, ebx
0x1800e1bd6  mov     [rsp+1B8h+String], rbx
0x1800e1bdb  xor     edx, edx; Val
0x1800e1bdd  mov     r8d, 0D0h; Size
0x1800e1be3  lea     rcx, [rsp+1B8h+instance]; void *
0x1800e1beb  call    memset_0
0x1800e1bf0  mov     [rsp+1B8h+var_130], ebx
0x1800e1bf7  mov     [rsp+1B8h+var_12C], bl
0x1800e1bfe  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800e1c05  mov     [rsp+1B8h+var_160], rax
0x1800e1c0a  lea     rax, [rsp+1B8h+var_130]
0x1800e1c12  mov     [rsp+1B8h+var_158], rax
0x1800e1c17  lea     rax, aMdmPolicyConfi_172; "MDM_Policy_Config01_Storage02"
0x1800e1c1e  mov     [rsp+1B8h+var_150], rax
0x1800e1c23  lea     rcx, [rsp+1B8h+var_130]
0x1800e1c2b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800e1c30  mov     eax, cs:dword_180380B68
0x1800e1c36  cmp     eax, 5
0x1800e1c39  jbe     short loc_1800E1CAA
0x1800e1c3b  mov     rdx, 200000000000h
0x1800e1c45  lea     rcx, dword_180380B68
0x1800e1c4c  call    _tlgKeywordOn
0x1800e1c51  test    al, al
0x1800e1c53  jz      short loc_1800E1CAA
0x1800e1c55  cmp     [rsp+1B8h+var_12C], bl
0x1800e1c5c  jz      short loc_1800E1C8C
0x1800e1c5e  cmp     [rsp+1B8h+var_118], ebx
0x1800e1c65  jnz     short loc_1800E1C82
0x1800e1c67  cmp     [rsp+1B8h+var_114], ebx
0x1800e1c6e  jnz     short loc_1800E1C82
0x1800e1c70  cmp     [rsp+1B8h+var_110], ebx
0x1800e1c77  jnz     short loc_1800E1C82
0x1800e1c79  cmp     [rsp+1B8h+var_10C], ebx
0x1800e1c80  jz      short loc_1800E1C8C
0x1800e1c82  lea     r9, [rsp+1B8h+var_118]
0x1800e1c8a  jmp     short loc_1800E1C8F
0x1800e1c8c  mov     r9, rbx
0x1800e1c8f  lea     r8, [rsp+1B8h+var_128]
0x1800e1c97  lea     rdx, byte_18034ED33
0x1800e1c9e  lea     rcx, dword_180380B68
0x1800e1ca5  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800e1caa  cmp     [r14+48h], bl
0x1800e1cae  jz      loc_1800E20AF
0x1800e1cb4  mov     [rsp+1B8h+var_170], bl
0x1800e1cb8  cmp     [r14+58h], bl
0x1800e1cbc  jz      loc_1800E20AF
0x1800e1cc2  mov     r9, [r14+40h]; unsigned __int16 *
0x1800e1cc6  mov     r8, [r14+50h]; unsigned __int16 *
0x1800e1cca  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1800e1cd1  lea     rcx, [rsp+1B8h+var_160]; this
0x1800e1cd6  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800e1cdb  nop
0x1800e1cdc  mov     [rsp+1B8h+var_168], rbx
0x1800e1ce1  lea     rax, [rsp+1B8h+var_168]
0x1800e1ce6  mov     [rsp+1B8h+var_188], rax
0x1800e1ceb  mov     [rsp+1B8h+var_190], ebx
0x1800e1cef  mov     [rsp+1B8h+var_198], 0Dh
0x1800e1cf7  lea     r9, ?MDM_Policy_Config01_Storage02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Storage02_NodeList
0x1800e1cfe  mov     r8, [r14+40h]
0x1800e1d02  mov     rdx, [r14+50h]
0x1800e1d06  mov     rcx, r15
0x1800e1d09  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800e1d0e  mov     esi, eax
0x1800e1d10  test    eax, eax
0x1800e1d12  jz      short loc_1800E1D19
0x1800e1d14  jmp     loc_1800E20B4
0x1800e1d19  lea     rax, [rsp+1B8h+var_168]
0x1800e1d1e  mov     [rsp+1B8h+var_140], rax
0x1800e1d23  mov     r12d, 1
0x1800e1d29  mov     [rsp+1B8h+var_138], r12b
0x1800e1d31  mov     rdi, [rsp+1B8h+var_168]
0x1800e1d36  test    rdi, rdi
0x1800e1d39  jnz     short loc_1800E1D43
0x1800e1d3b  mov     esi, r12d
0x1800e1d3e  jmp     loc_1800E20B4
0x1800e1d43  mov     r9d, 0Dh; unsigned int
0x1800e1d49  lea     r8, ?MDM_Policy_Config01_Storage02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800e1d50  mov     rdx, r14; struct _MI_Instance *
0x1800e1d53  mov     rcx, rdi; this
0x1800e1d56  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800e1d5b  mov     rax, [rdi]
0x1800e1d5e  mov     rcx, rdi
0x1800e1d61  mov     rax, [rax+10h]
0x1800e1d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1d6a  mov     esi, eax
0x1800e1d6c  test    eax, eax
0x1800e1d6e  jz      short loc_1800E1D8E
0x1800e1d70  mov     rcx, [rsp+1B8h+var_168]
0x1800e1d75  test    rcx, rcx
0x1800e1d78  jz      short loc_1800E1D89
0x1800e1d7a  mov     rax, [rcx]
0x1800e1d7d  mov     edx, r12d
0x1800e1d80  mov     rax, [rax]
0x1800e1d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1d88  nop
0x1800e1d89  jmp     loc_1800E20B4
0x1800e1d8e  mov     rax, [rdi]
0x1800e1d91  mov     rcx, rdi
0x1800e1d94  mov     rax, [rax+8]
0x1800e1d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1d9d  mov     esi, eax
0x1800e1d9f  test    eax, eax
0x1800e1da1  jz      short loc_1800E1DC1
0x1800e1da3  mov     rcx, [rsp+1B8h+var_168]
0x1800e1da8  test    rcx, rcx
0x1800e1dab  jz      short loc_1800E1DBC
0x1800e1dad  mov     rax, [rcx]
0x1800e1db0  mov     edx, r12d
0x1800e1db3  mov     rax, [rax]
0x1800e1db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1dbb  nop
0x1800e1dbc  jmp     loc_1800E20B4
0x1800e1dc1  lea     r8, [rsp+1B8h+instance]; instance
0x1800e1dc9  lea     rdx, MDM_Policy_Config01_Storage02_rtti; classDecl
0x1800e1dd0  mov     rcx, r15; context
0x1800e1dd3  call    MI_Context_ConstructInstance
0x1800e1dd8  mov     esi, eax
0x1800e1dda  test    eax, eax
0x1800e1ddc  jz      short loc_1800E1DFC
0x1800e1dde  mov     rcx, [rsp+1B8h+var_168]
0x1800e1de3  test    rcx, rcx
0x1800e1de6  jz      short loc_1800E1DF7
0x1800e1de8  mov     rax, [rcx]
0x1800e1deb  mov     edx, r12d
0x1800e1dee  mov     rax, [rax]
0x1800e1df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1df6  nop
0x1800e1df7  jmp     loc_1800E20B4
0x1800e1dfc  mov     [rsp+1B8h+var_170], r12b
0x1800e1e01  mov     rdx, [r14+40h]
0x1800e1e05  lea     rcx, [rsp+1B8h+instance]
0x1800e1e0d  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800e1e12  mov     rdx, [r14+50h]
0x1800e1e16  lea     rcx, [rsp+1B8h+instance]
0x1800e1e1e  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800e1e23  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e1e28  lea     rdx, aAllowdiskhealt; "AllowDiskHealthModelUpdates"
0x1800e1e2f  mov     rcx, rdi; this
0x1800e1e32  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e1e37  test    eax, eax
0x1800e1e39  jnz     short loc_1800E1E5A
0x1800e1e3b  mov     rcx, [rsp+1B8h+String]; String
0x1800e1e40  test    rcx, rcx
0x1800e1e43  jz      short loc_1800E1E5A
0x1800e1e45  call    cs:__imp__wtoi
0x1800e1e4b  mov     [rsp+1B8h+var_A8], eax
0x1800e1e52  mov     [rsp+1B8h+var_A4], r12b
0x1800e1e5a  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e1e5f  lea     rdx, aAllowstoragese_0; "AllowStorageSenseGlobal"
0x1800e1e66  mov     rcx, rdi; this
0x1800e1e69  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e1e6e  test    eax, eax
0x1800e1e70  jnz     short loc_1800E1E91
0x1800e1e72  mov     rcx, [rsp+1B8h+String]; String
0x1800e1e77  test    rcx, rcx
0x1800e1e7a  jz      short loc_1800E1E91
0x1800e1e7c  call    cs:__imp__wtoi
0x1800e1e82  mov     [rsp+1B8h+var_A0], eax
0x1800e1e89  mov     [rsp+1B8h+var_9C], r12b
0x1800e1e91  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e1e96  lea     rdx, aAllowstoragese; "AllowStorageSenseTemporaryFilesCleanup"
0x1800e1e9d  mov     rcx, rdi; this
0x1800e1ea0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e1ea5  test    eax, eax
0x1800e1ea7  jnz     short loc_1800E1EC8
0x1800e1ea9  mov     rcx, [rsp+1B8h+String]; String
0x1800e1eae  test    rcx, rcx
0x1800e1eb1  jz      short loc_1800E1EC8
0x1800e1eb3  call    cs:__imp__wtoi
0x1800e1eb9  mov     [rsp+1B8h+var_98], eax
0x1800e1ec0  mov     [rsp+1B8h+var_94], r12b
0x1800e1ec8  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e1ecd  lea     rdx, aConfigstorages; "ConfigStorageSenseCloudContentDehydrati"...
0x1800e1ed4  mov     rcx, rdi; this
0x1800e1ed7  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e1edc  test    eax, eax
0x1800e1ede  jnz     short loc_1800E1EFF
0x1800e1ee0  mov     rcx, [rsp+1B8h+String]; String
0x1800e1ee5  test    rcx, rcx
0x1800e1ee8  jz      short loc_1800E1EFF
0x1800e1eea  call    cs:__imp__wtoi
0x1800e1ef0  mov     [rsp+1B8h+var_90], eax
0x1800e1ef7  mov     [rsp+1B8h+var_8C], r12b
0x1800e1eff  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e1f04  lea     rdx, aConfigstorages_2; "ConfigStorageSenseDownloadsCleanupThres"...
0x1800e1f0b  mov     rcx, rdi; this
0x1800e1f0e  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e1f13  test    eax, eax
0x1800e1f15  jnz     short loc_1800E1F36
0x1800e1f17  mov     rcx, [rsp+1B8h+String]; String
0x1800e1f1c  test    rcx, rcx
0x1800e1f1f  jz      short loc_1800E1F36
0x1800e1f21  call    cs:__imp__wtoi
0x1800e1f27  mov     [rsp+1B8h+var_88], eax
0x1800e1f2e  mov     [rsp+1B8h+var_84], r12b
0x1800e1f36  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e1f3b  lea     rdx, aConfigstorages_0; "ConfigStorageSenseGlobalCadence"
0x1800e1f42  mov     rcx, rdi; this
0x1800e1f45  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e1f4a  test    eax, eax
0x1800e1f4c  jnz     short loc_1800E1F6D
0x1800e1f4e  mov     rcx, [rsp+1B8h+String]; String
0x1800e1f53  test    rcx, rcx
0x1800e1f56  jz      short loc_1800E1F6D
0x1800e1f58  call    cs:__imp__wtoi
0x1800e1f5e  mov     [rsp+1B8h+var_80], eax
0x1800e1f65  mov     [rsp+1B8h+var_7C], r12b
0x1800e1f6d  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e1f72  lea     rdx, aConfigstorages_1; "ConfigStorageSenseRecycleBinCleanupThre"...
0x1800e1f79  mov     rcx, rdi; this
0x1800e1f7c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e1f81  test    eax, eax
0x1800e1f83  jnz     short loc_1800E1FA4
0x1800e1f85  mov     rcx, [rsp+1B8h+String]; String
0x1800e1f8a  test    rcx, rcx
0x1800e1f8d  jz      short loc_1800E1FA4
0x1800e1f8f  call    cs:__imp__wtoi
0x1800e1f95  mov     [rsp+1B8h+var_78], eax
0x1800e1f9c  mov     [rsp+1B8h+var_74], r12b
0x1800e1fa4  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e1fa9  lea     rdx, aEnhancedstorag; "EnhancedStorageDevices"
0x1800e1fb0  mov     rcx, rdi; this
0x1800e1fb3  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e1fb8  test    eax, eax
0x1800e1fba  jnz     short loc_1800E1FD3
0x1800e1fbc  mov     rdx, [rsp+1B8h+String]
0x1800e1fc1  test    rdx, rdx
0x1800e1fc4  jz      short loc_1800E1FD3
0x1800e1fc6  lea     rcx, [rsp+1B8h+instance]
0x1800e1fce  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x1800e1fd3  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e1fd8  lea     rdx, aRemovablediskd; "RemovableDiskDenyWriteAccess"
0x1800e1fdf  mov     rcx, rdi; this
0x1800e1fe2  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e1fe7  test    eax, eax
0x1800e1fe9  jnz     short loc_1800E200A
0x1800e1feb  mov     rcx, [rsp+1B8h+String]; String
0x1800e1ff0  test    rcx, rcx
0x1800e1ff3  jz      short loc_1800E200A
0x1800e1ff5  call    cs:__imp__wtoi
0x1800e1ffb  mov     [rsp+1B8h+var_60], eax
0x1800e2002  mov     [rsp+1B8h+var_5C], r12b
0x1800e200a  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e200f  lea     rdx, aWpddevicesdeny_1; "WPDDevicesDenyReadAccessPerDevice"
0x1800e2016  mov     rcx, rdi; this
0x1800e2019  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e201e  test    eax, eax
0x1800e2020  jnz     short loc_1800E2039
0x1800e2022  mov     rdx, [rsp+1B8h+String]
0x1800e2027  test    rdx, rdx
0x1800e202a  jz      short loc_1800E2039
0x1800e202c  lea     rcx, [rsp+1B8h+instance]
0x1800e2034  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList
0x1800e2039  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x1800e203e  lea     rdx, aWpddevicesdeny_2; "WPDDevicesDenyWriteAccessPerDevice"
0x1800e2045  mov     rcx, rdi; this
0x1800e2048  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800e204d  test    eax, eax
0x1800e204f  jnz     short loc_1800E2068
0x1800e2051  mov     rdx, [rsp+1B8h+String]
0x1800e2056  test    rdx, rdx
0x1800e2059  jz      short loc_1800E2068
0x1800e205b  lea     rcx, [rsp+1B8h+instance]
0x1800e2063  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList
0x1800e2068  lea     rdx, [rsp+1B8h+instance]
0x1800e2070  mov     rcx, r15; self
0x1800e2073  call    MI_Instance_Destruct
0x1800e2078  nop
0x1800e2079  mov     rcx, [rsp+1B8h+var_168]
0x1800e207e  test    rcx, rcx
0x1800e2081  jz      short loc_1800E2092
0x1800e2083  mov     rax, [rcx]
0x1800e2086  mov     edx, r12d
0x1800e2089  mov     rax, [rax]
0x1800e208c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2091  nop
0x1800e2092  jmp     short loc_1800E20A0
0x1800e2094  xor     ebx, ebx
0x1800e2096  mov     esi, dword ptr [rsp+1B8h+String]
0x1800e209a  cmp     [rsp+1B8h+var_170], bl
0x1800e209e  jz      short loc_1800E20B4
0x1800e20a0  lea     rcx, [rsp+1B8h+instance]; self
0x1800e20a8  call    MI_Instance_Destruct
0x1800e20ad  jmp     short loc_1800E20B4
0x1800e20af  mov     esi, 4
0x1800e20b4  mov     r8d, esi; int
0x1800e20b7  lea     rdx, aGetinstanceend; "GetInstanceEnd"
0x1800e20be  lea     rcx, [rsp+1B8h+var_160]; this
  ... truncated ...
```
