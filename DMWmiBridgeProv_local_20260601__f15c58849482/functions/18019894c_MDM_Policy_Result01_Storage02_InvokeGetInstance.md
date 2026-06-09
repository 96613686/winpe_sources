# MDM_Policy_Result01_Storage02_InvokeGetInstance

- ea: `0x18019894c`
- end: `0x180198f23`
- name: `MDM_Policy_Result01_Storage02_InvokeGetInstance`
- size: `1495`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180197980`

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
- `0x18019894c`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180198be9`
- `msvcrt!_wtoi` at `0x180198c26`
- `msvcrt!_wtoi` at `0x180198c63`
- `msvcrt!_wtoi` at `0x180198ca0`
- `msvcrt!_wtoi` at `0x180198cdd`
- `msvcrt!_wtoi` at `0x180198d1a`
- `msvcrt!_wtoi` at `0x180198d57`
- `msvcrt!_wtoi` at `0x180198dc3`
- `msvcrt!_wtoi` at `0x180198be9`
- `msvcrt!_wtoi` at `0x180198c26`
- `msvcrt!_wtoi` at `0x180198c63`
- `msvcrt!_wtoi` at `0x180198ca0`
- `msvcrt!_wtoi` at `0x180198cdd`
- `msvcrt!_wtoi` at `0x180198d1a`
- `msvcrt!_wtoi` at `0x180198d57`
- `msvcrt!_wtoi` at `0x180198dc3`

## string_xrefs

- `0x180198bcc`: `AllowDiskHealthModelUpdates`
- `0x180198c46`: `AllowStorageSenseTemporaryFilesCleanup`
- `0x180198c83`: `ConfigStorageSenseCloudContentDehydrationThreshold`
- `0x180198cc0`: `ConfigStorageSenseDownloadsCleanupThreshold`
- `0x180198cfd`: `ConfigStorageSenseGlobalCadence`
- `0x180198d3a`: `ConfigStorageSenseRecycleBinCleanupThreshold`
- `0x180198da6`: `RemovableDiskDenyWriteAccess`
- `0x180198de3`: `WPDDevicesDenyReadAccessPerDevice`
- `0x180198e12`: `WPDDevicesDenyWriteAccessPerDevice`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Storage02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
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
    v5 = (unsigned int)CreateRequestHandlerInstance(
                         self,
                         a2[1].serverName,
                         a2[1].ft,
                         &MDM_Policy_Result01_Storage02_NodeList,
                         13,
                         0,
                         &v10);
    if ( v5 == MI_RESULT_OK )
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
        v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v5 )
        {
          if ( v10 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v10)(v10, 1);
        }
        else
        {
          v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowDiskHealthModelUpdates",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v18 = _wtoi(String);
                v19 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowStorageSenseGlobal",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
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
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"EnhancedStorageDevices",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
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
          }
        }
      }
      else
      {
        v5 = MI_RESULT_FAILED;
      }
    }
  }
  else
  {
    v5 = MI_RESULT_INVALID_PARAMETER;
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
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18019894c  mov     [rsp+arg_10], rbx
0x180198951  push    rsi
0x180198952  push    rdi
0x180198953  push    r12
0x180198955  push    r14
0x180198957  push    r15
0x180198959  sub     rsp, 190h
0x180198960  mov     rax, cs:__security_cookie
0x180198967  xor     rax, rsp
0x18019896a  mov     [rsp+1B8h+var_38], rax
0x180198972  mov     r14, rdx
0x180198975  mov     r15, rcx
0x180198978  xor     ebx, ebx
0x18019897a  mov     [rsp+1B8h+String], rbx
0x18019897f  xor     edx, edx; Val
0x180198981  mov     r8d, 0D0h; Size
0x180198987  lea     rcx, [rsp+1B8h+instance]; void *
0x18019898f  call    memset_0
0x180198994  mov     [rsp+1B8h+var_130], ebx
0x18019899b  mov     [rsp+1B8h+var_12C], bl
0x1801989a2  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1801989a9  mov     [rsp+1B8h+var_160], rax
0x1801989ae  lea     rax, [rsp+1B8h+var_130]
0x1801989b6  mov     [rsp+1B8h+var_158], rax
0x1801989bb  lea     rax, aMdmPolicyResul_127; "MDM_Policy_Result01_Storage02"
0x1801989c2  mov     [rsp+1B8h+var_150], rax
0x1801989c7  lea     rcx, [rsp+1B8h+var_130]
0x1801989cf  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1801989d4  mov     eax, cs:dword_180380B68
0x1801989da  cmp     eax, 5
0x1801989dd  jbe     short loc_180198A4E
0x1801989df  mov     rdx, 200000000000h
0x1801989e9  lea     rcx, dword_180380B68
0x1801989f0  call    _tlgKeywordOn
0x1801989f5  test    al, al
0x1801989f7  jz      short loc_180198A4E
0x1801989f9  cmp     [rsp+1B8h+var_12C], bl
0x180198a00  jz      short loc_180198A30
0x180198a02  cmp     [rsp+1B8h+var_118], ebx
0x180198a09  jnz     short loc_180198A26
0x180198a0b  cmp     [rsp+1B8h+var_114], ebx
0x180198a12  jnz     short loc_180198A26
0x180198a14  cmp     [rsp+1B8h+var_110], ebx
0x180198a1b  jnz     short loc_180198A26
0x180198a1d  cmp     [rsp+1B8h+var_10C], ebx
0x180198a24  jz      short loc_180198A30
0x180198a26  lea     r9, [rsp+1B8h+var_118]
0x180198a2e  jmp     short loc_180198A33
0x180198a30  mov     r9, rbx
0x180198a33  lea     r8, [rsp+1B8h+var_128]
0x180198a3b  lea     rdx, word_180345D22
0x180198a42  lea     rcx, dword_180380B68
0x180198a49  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180198a4e  cmp     [r14+48h], bl
0x180198a52  jz      loc_180198E83
0x180198a58  mov     [rsp+1B8h+var_170], bl
0x180198a5c  cmp     [r14+58h], bl
0x180198a60  jz      loc_180198E83
0x180198a66  mov     r9, [r14+40h]; unsigned __int16 *
0x180198a6a  mov     r8, [r14+50h]; unsigned __int16 *
0x180198a6e  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x180198a75  lea     rcx, [rsp+1B8h+var_160]; this
0x180198a7a  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180198a7f  nop
0x180198a80  mov     [rsp+1B8h+var_168], rbx
0x180198a85  lea     rax, [rsp+1B8h+var_168]
0x180198a8a  mov     [rsp+1B8h+var_188], rax
0x180198a8f  mov     [rsp+1B8h+var_190], ebx
0x180198a93  mov     [rsp+1B8h+var_198], 0Dh
0x180198a9b  lea     r9, ?MDM_Policy_Result01_Storage02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Storage02_NodeList
0x180198aa2  mov     r8, [r14+40h]
0x180198aa6  mov     rdx, [r14+50h]
0x180198aaa  mov     rcx, r15
0x180198aad  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180198ab2  mov     esi, eax
0x180198ab4  test    eax, eax
0x180198ab6  jz      short loc_180198ABD
0x180198ab8  jmp     loc_180198E88
0x180198abd  lea     rax, [rsp+1B8h+var_168]
0x180198ac2  mov     [rsp+1B8h+var_140], rax
0x180198ac7  mov     r12d, 1
0x180198acd  mov     [rsp+1B8h+var_138], r12b
0x180198ad5  mov     rdi, [rsp+1B8h+var_168]
0x180198ada  test    rdi, rdi
0x180198add  jnz     short loc_180198AE7
0x180198adf  mov     esi, r12d
0x180198ae2  jmp     loc_180198E88
0x180198ae7  mov     r9d, 0Dh; unsigned int
0x180198aed  lea     r8, ?MDM_Policy_Result01_Storage02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180198af4  mov     rdx, r14; struct _MI_Instance *
0x180198af7  mov     rcx, rdi; this
0x180198afa  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180198aff  mov     rax, [rdi]
0x180198b02  mov     rcx, rdi
0x180198b05  mov     rax, [rax+10h]
0x180198b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198b0e  mov     esi, eax
0x180198b10  test    eax, eax
0x180198b12  jz      short loc_180198B32
0x180198b14  mov     rcx, [rsp+1B8h+var_168]
0x180198b19  test    rcx, rcx
0x180198b1c  jz      short loc_180198B2D
0x180198b1e  mov     rax, [rcx]
0x180198b21  mov     edx, r12d
0x180198b24  mov     rax, [rax]
0x180198b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198b2c  nop
0x180198b2d  jmp     loc_180198E88
0x180198b32  mov     rax, [rdi]
0x180198b35  mov     rcx, rdi
0x180198b38  mov     rax, [rax+8]
0x180198b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198b41  mov     esi, eax
0x180198b43  test    eax, eax
0x180198b45  jz      short loc_180198B65
0x180198b47  mov     rcx, [rsp+1B8h+var_168]
0x180198b4c  test    rcx, rcx
0x180198b4f  jz      short loc_180198B60
0x180198b51  mov     rax, [rcx]
0x180198b54  mov     edx, r12d
0x180198b57  mov     rax, [rax]
0x180198b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198b5f  nop
0x180198b60  jmp     loc_180198E88
0x180198b65  lea     r8, [rsp+1B8h+instance]; instance
0x180198b6d  lea     rdx, MDM_Policy_Result01_Storage02_rtti; classDecl
0x180198b74  mov     rcx, r15; context
0x180198b77  call    MI_Context_ConstructInstance
0x180198b7c  mov     esi, eax
0x180198b7e  test    eax, eax
0x180198b80  jz      short loc_180198BA0
0x180198b82  mov     rcx, [rsp+1B8h+var_168]
0x180198b87  test    rcx, rcx
0x180198b8a  jz      short loc_180198B9B
0x180198b8c  mov     rax, [rcx]
0x180198b8f  mov     edx, r12d
0x180198b92  mov     rax, [rax]
0x180198b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198b9a  nop
0x180198b9b  jmp     loc_180198E88
0x180198ba0  mov     [rsp+1B8h+var_170], r12b
0x180198ba5  mov     rdx, [r14+40h]
0x180198ba9  lea     rcx, [rsp+1B8h+instance]
0x180198bb1  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180198bb6  mov     rdx, [r14+50h]
0x180198bba  lea     rcx, [rsp+1B8h+instance]
0x180198bc2  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180198bc7  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x180198bcc  lea     rdx, aAllowdiskhealt; "AllowDiskHealthModelUpdates"
0x180198bd3  mov     rcx, rdi; this
0x180198bd6  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180198bdb  test    eax, eax
0x180198bdd  jnz     short loc_180198C04
0x180198bdf  mov     rcx, [rsp+1B8h+String]; String
0x180198be4  test    rcx, rcx
0x180198be7  jz      short loc_180198C04
0x180198be9  call    cs:__imp__wtoi
0x180198bf0  nop     dword ptr [rax+rax+00h]
0x180198bf5  mov     [rsp+1B8h+var_A8], eax
0x180198bfc  mov     [rsp+1B8h+var_A4], r12b
0x180198c04  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x180198c09  lea     rdx, aAllowstoragese_0; "AllowStorageSenseGlobal"
0x180198c10  mov     rcx, rdi; this
0x180198c13  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180198c18  test    eax, eax
0x180198c1a  jnz     short loc_180198C41
0x180198c1c  mov     rcx, [rsp+1B8h+String]; String
0x180198c21  test    rcx, rcx
0x180198c24  jz      short loc_180198C41
0x180198c26  call    cs:__imp__wtoi
0x180198c2d  nop     dword ptr [rax+rax+00h]
0x180198c32  mov     [rsp+1B8h+var_A0], eax
0x180198c39  mov     [rsp+1B8h+var_9C], r12b
0x180198c41  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x180198c46  lea     rdx, aAllowstoragese; "AllowStorageSenseTemporaryFilesCleanup"
0x180198c4d  mov     rcx, rdi; this
0x180198c50  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180198c55  test    eax, eax
0x180198c57  jnz     short loc_180198C7E
0x180198c59  mov     rcx, [rsp+1B8h+String]; String
0x180198c5e  test    rcx, rcx
0x180198c61  jz      short loc_180198C7E
0x180198c63  call    cs:__imp__wtoi
0x180198c6a  nop     dword ptr [rax+rax+00h]
0x180198c6f  mov     [rsp+1B8h+var_98], eax
0x180198c76  mov     [rsp+1B8h+var_94], r12b
0x180198c7e  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x180198c83  lea     rdx, aConfigstorages; "ConfigStorageSenseCloudContentDehydrati"...
0x180198c8a  mov     rcx, rdi; this
0x180198c8d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180198c92  test    eax, eax
0x180198c94  jnz     short loc_180198CBB
0x180198c96  mov     rcx, [rsp+1B8h+String]; String
0x180198c9b  test    rcx, rcx
0x180198c9e  jz      short loc_180198CBB
0x180198ca0  call    cs:__imp__wtoi
0x180198ca7  nop     dword ptr [rax+rax+00h]
0x180198cac  mov     [rsp+1B8h+var_90], eax
0x180198cb3  mov     [rsp+1B8h+var_8C], r12b
0x180198cbb  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x180198cc0  lea     rdx, aConfigstorages_2; "ConfigStorageSenseDownloadsCleanupThres"...
0x180198cc7  mov     rcx, rdi; this
0x180198cca  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180198ccf  test    eax, eax
0x180198cd1  jnz     short loc_180198CF8
0x180198cd3  mov     rcx, [rsp+1B8h+String]; String
0x180198cd8  test    rcx, rcx
0x180198cdb  jz      short loc_180198CF8
0x180198cdd  call    cs:__imp__wtoi
0x180198ce4  nop     dword ptr [rax+rax+00h]
0x180198ce9  mov     [rsp+1B8h+var_88], eax
0x180198cf0  mov     [rsp+1B8h+var_84], r12b
0x180198cf8  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x180198cfd  lea     rdx, aConfigstorages_0; "ConfigStorageSenseGlobalCadence"
0x180198d04  mov     rcx, rdi; this
0x180198d07  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180198d0c  test    eax, eax
0x180198d0e  jnz     short loc_180198D35
0x180198d10  mov     rcx, [rsp+1B8h+String]; String
0x180198d15  test    rcx, rcx
0x180198d18  jz      short loc_180198D35
0x180198d1a  call    cs:__imp__wtoi
0x180198d21  nop     dword ptr [rax+rax+00h]
0x180198d26  mov     [rsp+1B8h+var_80], eax
0x180198d2d  mov     [rsp+1B8h+var_7C], r12b
0x180198d35  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x180198d3a  lea     rdx, aConfigstorages_1; "ConfigStorageSenseRecycleBinCleanupThre"...
0x180198d41  mov     rcx, rdi; this
0x180198d44  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180198d49  test    eax, eax
0x180198d4b  jnz     short loc_180198D72
0x180198d4d  mov     rcx, [rsp+1B8h+String]; String
0x180198d52  test    rcx, rcx
0x180198d55  jz      short loc_180198D72
0x180198d57  call    cs:__imp__wtoi
0x180198d5e  nop     dword ptr [rax+rax+00h]
0x180198d63  mov     [rsp+1B8h+var_78], eax
0x180198d6a  mov     [rsp+1B8h+var_74], r12b
0x180198d72  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x180198d77  lea     rdx, aEnhancedstorag; "EnhancedStorageDevices"
0x180198d7e  mov     rcx, rdi; this
0x180198d81  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180198d86  test    eax, eax
0x180198d88  jnz     short loc_180198DA1
0x180198d8a  mov     rdx, [rsp+1B8h+String]
0x180198d8f  test    rdx, rdx
0x180198d92  jz      short loc_180198DA1
0x180198d94  lea     rcx, [rsp+1B8h+instance]
0x180198d9c  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x180198da1  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x180198da6  lea     rdx, aRemovablediskd; "RemovableDiskDenyWriteAccess"
0x180198dad  mov     rcx, rdi; this
0x180198db0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180198db5  test    eax, eax
0x180198db7  jnz     short loc_180198DDE
0x180198db9  mov     rcx, [rsp+1B8h+String]; String
0x180198dbe  test    rcx, rcx
0x180198dc1  jz      short loc_180198DDE
0x180198dc3  call    cs:__imp__wtoi
0x180198dca  nop     dword ptr [rax+rax+00h]
0x180198dcf  mov     [rsp+1B8h+var_60], eax
0x180198dd6  mov     [rsp+1B8h+var_5C], r12b
0x180198dde  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x180198de3  lea     rdx, aWpddevicesdeny_1; "WPDDevicesDenyReadAccessPerDevice"
0x180198dea  mov     rcx, rdi; this
0x180198ded  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180198df2  test    eax, eax
0x180198df4  jnz     short loc_180198E0D
0x180198df6  mov     rdx, [rsp+1B8h+String]
0x180198dfb  test    rdx, rdx
0x180198dfe  jz      short loc_180198E0D
0x180198e00  lea     rcx, [rsp+1B8h+instance]
0x180198e08  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowEnterpriseModeSiteList
0x180198e0d  lea     r8, [rsp+1B8h+String]; unsigned __int16 **
0x180198e12  lea     rdx, aWpddevicesdeny_2; "WPDDevicesDenyWriteAccessPerDevice"
0x180198e19  mov     rcx, rdi; this
0x180198e1c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180198e21  test    eax, eax
0x180198e23  jnz     short loc_180198E3C
0x180198e25  mov     rdx, [rsp+1B8h+String]
0x180198e2a  test    rdx, rdx
0x180198e2d  jz      short loc_180198E3C
0x180198e2f  lea     rcx, [rsp+1B8h+instance]
0x180198e37  call    MDM_Policy_User_Result01_InternetExplorer02_Set_AllowInternetExplorer7PolicyList
0x180198e3c  lea     rdx, [rsp+1B8h+instance]
0x180198e44  mov     rcx, r15; self
0x180198e47  call    MI_Instance_Destruct
0x180198e4c  nop
0x180198e4d  mov     rcx, [rsp+1B8h+var_168]
0x180198e52  test    rcx, rcx
0x180198e55  jz      short loc_180198E66
0x180198e57  mov     rax, [rcx]
0x180198e5a  mov     edx, r12d
0x180198e5d  mov     rax, [rax]
0x180198e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198e65  nop
0x180198e66  jmp     short loc_180198E74
0x180198e68  xor     ebx, ebx
0x180198e6a  mov     esi, dword ptr [rsp+1B8h+String]
0x180198e6e  cmp     [rsp+1B8h+var_170], bl
  ... truncated ...
```
