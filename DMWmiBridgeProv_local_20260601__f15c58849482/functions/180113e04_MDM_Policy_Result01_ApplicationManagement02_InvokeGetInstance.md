# MDM_Policy_Result01_ApplicationManagement02_InvokeGetInstance

- ea: `0x180113e04`
- end: `0x1801144e2`
- name: `MDM_Policy_Result01_ApplicationManagement02_InvokeGetInstance`
- size: `1758`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x180112c10`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x1800053c8`
- `0x180005470`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x180113e04`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1801140a3`
- `msvcrt!_wtoi` at `0x1801140e0`
- `msvcrt!_wtoi` at `0x18011411d`
- `msvcrt!_wtoi` at `0x18011415a`
- `msvcrt!_wtoi` at `0x180114197`
- `msvcrt!_wtoi` at `0x1801141d4`
- `msvcrt!_wtoi` at `0x180114211`
- `msvcrt!_wtoi` at `0x18011424e`
- `msvcrt!_wtoi` at `0x1801142ba`
- `msvcrt!_wtoi` at `0x1801142f7`
- `msvcrt!_wtoi` at `0x180114334`
- `msvcrt!_wtoi` at `0x180114371`
- `msvcrt!_wtoi` at `0x1801143ae`
- `msvcrt!_wtoi` at `0x1801140a3`
- `msvcrt!_wtoi` at `0x1801140e0`
- `msvcrt!_wtoi` at `0x18011411d`
- `msvcrt!_wtoi` at `0x18011415a`
- `msvcrt!_wtoi` at `0x180114197`
- `msvcrt!_wtoi` at `0x1801141d4`
- `msvcrt!_wtoi` at `0x180114211`
- `msvcrt!_wtoi` at `0x18011424e`
- `msvcrt!_wtoi` at `0x1801142ba`
- `msvcrt!_wtoi` at `0x1801142f7`
- `msvcrt!_wtoi` at `0x180114334`
- `msvcrt!_wtoi` at `0x180114371`
- `msvcrt!_wtoi` at `0x1801143ae`

## string_xrefs

- `0x1801140c3`: `AllowAppStoreAutoUpdate`
- `0x1801141f4`: `BlockNonAdminUserInstall`
- `0x18011429d`: `MSIAllowUserControlOverInstall`
- `0x1801142da`: `MSIAlwaysInstallWithElevatedPrivileges`
- `0x1801143ce`: `ScheduleForceRestartForUpdateFailures`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_ApplicationManagement02_InvokeGetInstance(
        MI_Context *self,
        struct _MI_Instance *a2)
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
  int v32; // [rsp+148h] [rbp-90h]
  char v33; // [rsp+14Ch] [rbp-8Ch]
  int v34; // [rsp+160h] [rbp-78h]
  char v35; // [rsp+164h] [rbp-74h]
  int v36; // [rsp+168h] [rbp-70h]
  char v37; // [rsp+16Ch] [rbp-6Ch]
  int v38; // [rsp+170h] [rbp-68h]
  char v39; // [rsp+174h] [rbp-64h]
  int v40; // [rsp+178h] [rbp-60h]
  char v41; // [rsp+17Ch] [rbp-5Ch]
  int v42; // [rsp+180h] [rbp-58h]
  char v43; // [rsp+184h] [rbp-54h]

  String = 0;
  memset_0(&instance, 0, 0xE8u);
  v13 = 0;
  v14 = 0;
  v11[0] = &TelemetryEventWriter::`vftable';
  v11[1] = &v13;
  v11[2] = "MDM_Policy_Result01_ApplicationManagement02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v13);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v14 && (v16[0] || v16[1] || v16[2] || v16[3]) )
      v4 = v16;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_18035D317,
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
                         &MDM_Policy_Result01_ApplicationManagement02_NodeList,
                         17,
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
          (struct WmiNodeInfo *)&MDM_Policy_Result01_ApplicationManagement02_NodeList,
          0x11u);
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
            v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_ApplicationManagement02_rtti, &instance);
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
                     L"AllowAllTrustedApps",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v18 = _wtoi(String);
                v19 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowAppStoreAutoUpdate",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowAutomaticAppArchiving",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowDeveloperUnlock",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(v6, L"AllowGameDVR", (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"AllowSharedUserAppData",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"BlockNonAdminUserInstall",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"DisableStoreOriginatedApps",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"LaunchAppAfterLogOn",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"MSIAllowUserControlOverInstall",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"MSIAlwaysInstallWithElevatedPrivileges",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"RequirePrivateStoreOnly",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"RestrictAppDataToSystemVolume",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"RestrictAppToSystemVolume",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"ScheduleForceRestartForUpdateFailures",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
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
      &dword_18035E904,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180113e04  mov     [rsp+arg_10], rbx
0x180113e09  push    rsi
0x180113e0a  push    rdi
0x180113e0b  push    r12
0x180113e0d  push    r14
0x180113e0f  push    r15
0x180113e11  sub     rsp, 1B0h
0x180113e18  mov     rax, cs:__security_cookie
0x180113e1f  xor     rax, rsp
0x180113e22  mov     [rsp+1D8h+var_38], rax
0x180113e2a  mov     rsi, rdx
0x180113e2d  mov     r15, rcx
0x180113e30  xor     ebx, ebx
0x180113e32  mov     [rsp+1D8h+String], rbx
0x180113e37  xor     edx, edx; Val
0x180113e39  mov     r8d, 0E8h; Size
0x180113e3f  lea     rcx, [rsp+1D8h+instance]; void *
0x180113e47  call    memset_0
0x180113e4c  mov     [rsp+1D8h+var_150], ebx
0x180113e53  mov     [rsp+1D8h+var_14C], bl
0x180113e5a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180113e61  mov     [rsp+1D8h+var_180], rax
0x180113e66  lea     rax, [rsp+1D8h+var_150]
0x180113e6e  mov     [rsp+1D8h+var_178], rax
0x180113e73  lea     rax, aMdmPolicyResul_187; "MDM_Policy_Result01_ApplicationManageme"...
0x180113e7a  mov     [rsp+1D8h+var_170], rax
0x180113e7f  lea     rcx, [rsp+1D8h+var_150]
0x180113e87  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180113e8c  mov     eax, cs:dword_180380B68
0x180113e92  cmp     eax, 5
0x180113e95  jbe     short loc_180113F06
0x180113e97  mov     rdx, 200000000000h
0x180113ea1  lea     rcx, dword_180380B68
0x180113ea8  call    _tlgKeywordOn
0x180113ead  test    al, al
0x180113eaf  jz      short loc_180113F06
0x180113eb1  cmp     [rsp+1D8h+var_14C], bl
0x180113eb8  jz      short loc_180113EE8
0x180113eba  cmp     [rsp+1D8h+var_138], ebx
0x180113ec1  jnz     short loc_180113EDE
0x180113ec3  cmp     [rsp+1D8h+var_134], ebx
0x180113eca  jnz     short loc_180113EDE
0x180113ecc  cmp     [rsp+1D8h+var_130], ebx
0x180113ed3  jnz     short loc_180113EDE
0x180113ed5  cmp     [rsp+1D8h+var_12C], ebx
0x180113edc  jz      short loc_180113EE8
0x180113ede  lea     r9, [rsp+1D8h+var_138]
0x180113ee6  jmp     short loc_180113EEB
0x180113ee8  mov     r9, rbx
0x180113eeb  lea     r8, [rsp+1D8h+var_148]
0x180113ef3  lea     rdx, byte_18035D317
0x180113efa  lea     rcx, dword_180380B68
0x180113f01  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180113f06  cmp     [rsi+48h], bl
0x180113f09  jz      loc_180114440
0x180113f0f  mov     [rsp+1D8h+var_190], bl
0x180113f13  cmp     [rsi+58h], bl
0x180113f16  jz      loc_180114440
0x180113f1c  mov     r9, [rsi+40h]; unsigned __int16 *
0x180113f20  mov     r8, [rsi+50h]; unsigned __int16 *
0x180113f24  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x180113f2b  lea     rcx, [rsp+1D8h+var_180]; this
0x180113f30  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x180113f35  nop
0x180113f36  mov     [rsp+1D8h+var_188], rbx
0x180113f3b  lea     rax, [rsp+1D8h+var_188]
0x180113f40  mov     [rsp+1D8h+var_1A8], rax
0x180113f45  mov     [rsp+1D8h+var_1B0], ebx
0x180113f49  mov     [rsp+1D8h+var_1B8], 11h
0x180113f51  lea     r9, ?MDM_Policy_Result01_ApplicationManagement02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_ApplicationManagement02_NodeList
0x180113f58  mov     r8, [rsi+40h]
0x180113f5c  mov     rdx, [rsi+50h]
0x180113f60  mov     rcx, r15
0x180113f63  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180113f68  mov     r14d, eax
0x180113f6b  test    eax, eax
0x180113f6d  jz      short loc_180113F74
0x180113f6f  jmp     loc_180114446
0x180113f74  lea     rax, [rsp+1D8h+var_188]
0x180113f79  mov     [rsp+1D8h+var_160], rax
0x180113f7e  mov     r12d, 1
0x180113f84  mov     [rsp+1D8h+var_158], r12b
0x180113f8c  mov     rdi, [rsp+1D8h+var_188]
0x180113f91  test    rdi, rdi
0x180113f94  jnz     short loc_180113F9E
0x180113f96  mov     r14d, r12d
0x180113f99  jmp     loc_180114446
0x180113f9e  mov     r9d, 11h; unsigned int
0x180113fa4  lea     r8, ?MDM_Policy_Result01_ApplicationManagement02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x180113fab  mov     rdx, rsi; struct _MI_Instance *
0x180113fae  mov     rcx, rdi; this
0x180113fb1  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180113fb6  mov     rax, [rdi]
0x180113fb9  mov     rcx, rdi
0x180113fbc  mov     rax, [rax+10h]
0x180113fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113fc5  mov     r14d, eax
0x180113fc8  test    eax, eax
0x180113fca  jz      short loc_180113FEA
0x180113fcc  mov     rcx, [rsp+1D8h+var_188]
0x180113fd1  test    rcx, rcx
0x180113fd4  jz      short loc_180113FE5
0x180113fd6  mov     rax, [rcx]
0x180113fd9  mov     edx, r12d
0x180113fdc  mov     rax, [rax]
0x180113fdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113fe4  nop
0x180113fe5  jmp     loc_180114446
0x180113fea  mov     rax, [rdi]
0x180113fed  mov     rcx, rdi
0x180113ff0  mov     rax, [rax+8]
0x180113ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113ff9  mov     r14d, eax
0x180113ffc  test    eax, eax
0x180113ffe  jz      short loc_18011401E
0x180114000  mov     rcx, [rsp+1D8h+var_188]
0x180114005  test    rcx, rcx
0x180114008  jz      short loc_180114019
0x18011400a  mov     rax, [rcx]
0x18011400d  mov     edx, r12d
0x180114010  mov     rax, [rax]
0x180114013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114018  nop
0x180114019  jmp     loc_180114446
0x18011401e  lea     r8, [rsp+1D8h+instance]; instance
0x180114026  lea     rdx, MDM_Policy_Result01_ApplicationManagement02_rtti; classDecl
0x18011402d  mov     rcx, r15; context
0x180114030  call    MI_Context_ConstructInstance
0x180114035  mov     r14d, eax
0x180114038  test    eax, eax
0x18011403a  jz      short loc_18011405A
0x18011403c  mov     rcx, [rsp+1D8h+var_188]
0x180114041  test    rcx, rcx
0x180114044  jz      short loc_180114055
0x180114046  mov     rax, [rcx]
0x180114049  mov     edx, r12d
0x18011404c  mov     rax, [rax]
0x18011404f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114054  nop
0x180114055  jmp     loc_180114446
0x18011405a  mov     [rsp+1D8h+var_190], r12b
0x18011405f  mov     rdx, [rsi+40h]
0x180114063  lea     rcx, [rsp+1D8h+instance]
0x18011406b  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180114070  mov     rdx, [rsi+50h]
0x180114074  lea     rcx, [rsp+1D8h+instance]
0x18011407c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180114081  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180114086  lea     rdx, aAllowalltruste; "AllowAllTrustedApps"
0x18011408d  mov     rcx, rdi; this
0x180114090  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180114095  test    eax, eax
0x180114097  jnz     short loc_1801140BE
0x180114099  mov     rcx, [rsp+1D8h+String]; String
0x18011409e  test    rcx, rcx
0x1801140a1  jz      short loc_1801140BE
0x1801140a3  call    cs:__imp__wtoi
0x1801140aa  nop     dword ptr [rax+rax+00h]
0x1801140af  mov     [rsp+1D8h+var_C8], eax
0x1801140b6  mov     [rsp+1D8h+var_C4], r12b
0x1801140be  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x1801140c3  lea     rdx, aAllowappstorea; "AllowAppStoreAutoUpdate"
0x1801140ca  mov     rcx, rdi; this
0x1801140cd  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801140d2  test    eax, eax
0x1801140d4  jnz     short loc_1801140FB
0x1801140d6  mov     rcx, [rsp+1D8h+String]; String
0x1801140db  test    rcx, rcx
0x1801140de  jz      short loc_1801140FB
0x1801140e0  call    cs:__imp__wtoi
0x1801140e7  nop     dword ptr [rax+rax+00h]
0x1801140ec  mov     [rsp+1D8h+var_C0], eax
0x1801140f3  mov     [rsp+1D8h+var_BC], r12b
0x1801140fb  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180114100  lea     rdx, aAllowautomatic_0; "AllowAutomaticAppArchiving"
0x180114107  mov     rcx, rdi; this
0x18011410a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18011410f  test    eax, eax
0x180114111  jnz     short loc_180114138
0x180114113  mov     rcx, [rsp+1D8h+String]; String
0x180114118  test    rcx, rcx
0x18011411b  jz      short loc_180114138
0x18011411d  call    cs:__imp__wtoi
0x180114124  nop     dword ptr [rax+rax+00h]
0x180114129  mov     [rsp+1D8h+var_B8], eax
0x180114130  mov     [rsp+1D8h+var_B4], r12b
0x180114138  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18011413d  lea     rdx, aAllowdeveloper_0; "AllowDeveloperUnlock"
0x180114144  mov     rcx, rdi; this
0x180114147  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18011414c  test    eax, eax
0x18011414e  jnz     short loc_180114175
0x180114150  mov     rcx, [rsp+1D8h+String]; String
0x180114155  test    rcx, rcx
0x180114158  jz      short loc_180114175
0x18011415a  call    cs:__imp__wtoi
0x180114161  nop     dword ptr [rax+rax+00h]
0x180114166  mov     [rsp+1D8h+var_B0], eax
0x18011416d  mov     [rsp+1D8h+var_AC], r12b
0x180114175  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18011417a  lea     rdx, aAllowgamedvr; "AllowGameDVR"
0x180114181  mov     rcx, rdi; this
0x180114184  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180114189  test    eax, eax
0x18011418b  jnz     short loc_1801141B2
0x18011418d  mov     rcx, [rsp+1D8h+String]; String
0x180114192  test    rcx, rcx
0x180114195  jz      short loc_1801141B2
0x180114197  call    cs:__imp__wtoi
0x18011419e  nop     dword ptr [rax+rax+00h]
0x1801141a3  mov     [rsp+1D8h+var_A8], eax
0x1801141aa  mov     [rsp+1D8h+var_A4], r12b
0x1801141b2  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x1801141b7  lea     rdx, aAllowshareduse; "AllowSharedUserAppData"
0x1801141be  mov     rcx, rdi; this
0x1801141c1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801141c6  test    eax, eax
0x1801141c8  jnz     short loc_1801141EF
0x1801141ca  mov     rcx, [rsp+1D8h+String]; String
0x1801141cf  test    rcx, rcx
0x1801141d2  jz      short loc_1801141EF
0x1801141d4  call    cs:__imp__wtoi
0x1801141db  nop     dword ptr [rax+rax+00h]
0x1801141e0  mov     [rsp+1D8h+var_A0], eax
0x1801141e7  mov     [rsp+1D8h+var_9C], r12b
0x1801141ef  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x1801141f4  lea     rdx, aBlocknonadminu; "BlockNonAdminUserInstall"
0x1801141fb  mov     rcx, rdi; this
0x1801141fe  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180114203  test    eax, eax
0x180114205  jnz     short loc_18011422C
0x180114207  mov     rcx, [rsp+1D8h+String]; String
0x18011420c  test    rcx, rcx
0x18011420f  jz      short loc_18011422C
0x180114211  call    cs:__imp__wtoi
0x180114218  nop     dword ptr [rax+rax+00h]
0x18011421d  mov     [rsp+1D8h+var_98], eax
0x180114224  mov     [rsp+1D8h+var_94], r12b
0x18011422c  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180114231  lea     rdx, aDisablestoreor; "DisableStoreOriginatedApps"
0x180114238  mov     rcx, rdi; this
0x18011423b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180114240  test    eax, eax
0x180114242  jnz     short loc_180114269
0x180114244  mov     rcx, [rsp+1D8h+String]; String
0x180114249  test    rcx, rcx
0x18011424c  jz      short loc_180114269
0x18011424e  call    cs:__imp__wtoi
0x180114255  nop     dword ptr [rax+rax+00h]
0x18011425a  mov     [rsp+1D8h+var_90], eax
0x180114261  mov     [rsp+1D8h+var_8C], r12b
0x180114269  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18011426e  lea     rdx, aLaunchappafter; "LaunchAppAfterLogOn"
0x180114275  mov     rcx, rdi; this
0x180114278  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18011427d  test    eax, eax
0x18011427f  jnz     short loc_180114298
0x180114281  mov     rdx, [rsp+1D8h+String]
0x180114286  test    rdx, rdx
0x180114289  jz      short loc_180114298
0x18011428b  lea     rcx, [rsp+1D8h+instance]
0x180114293  call    MDM_VPNv2_01_Set_TrustedNetworkDetection
0x180114298  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18011429d  lea     rdx, aMsiallowuserco; "MSIAllowUserControlOverInstall"
0x1801142a4  mov     rcx, rdi; this
0x1801142a7  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801142ac  test    eax, eax
0x1801142ae  jnz     short loc_1801142D5
0x1801142b0  mov     rcx, [rsp+1D8h+String]; String
0x1801142b5  test    rcx, rcx
0x1801142b8  jz      short loc_1801142D5
0x1801142ba  call    cs:__imp__wtoi
0x1801142c1  nop     dword ptr [rax+rax+00h]
0x1801142c6  mov     [rsp+1D8h+var_78], eax
0x1801142cd  mov     [rsp+1D8h+var_74], r12b
0x1801142d5  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x1801142da  lea     rdx, aMsialwaysinsta; "MSIAlwaysInstallWithElevatedPrivileges"
0x1801142e1  mov     rcx, rdi; this
0x1801142e4  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801142e9  test    eax, eax
0x1801142eb  jnz     short loc_180114312
0x1801142ed  mov     rcx, [rsp+1D8h+String]; String
0x1801142f2  test    rcx, rcx
0x1801142f5  jz      short loc_180114312
0x1801142f7  call    cs:__imp__wtoi
0x1801142fe  nop     dword ptr [rax+rax+00h]
0x180114303  mov     [rsp+1D8h+var_70], eax
0x18011430a  mov     [rsp+1D8h+var_6C], r12b
0x180114312  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180114317  lea     rdx, aRequireprivate; "RequirePrivateStoreOnly"
0x18011431e  mov     rcx, rdi; this
0x180114321  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180114326  test    eax, eax
0x180114328  jnz     short loc_18011434F
0x18011432a  mov     rcx, [rsp+1D8h+String]; String
0x18011432f  test    rcx, rcx
0x180114332  jz      short loc_18011434F
0x180114334  call    cs:__imp__wtoi
0x18011433b  nop     dword ptr [rax+rax+00h]
0x180114340  mov     [rsp+1D8h+var_68], eax
  ... truncated ...
```
