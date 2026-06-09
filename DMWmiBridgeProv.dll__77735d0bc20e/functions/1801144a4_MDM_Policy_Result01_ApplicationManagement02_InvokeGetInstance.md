# MDM_Policy_Result01_ApplicationManagement02_InvokeGetInstance

- ea: `0x1801144a4`
- end: `0x180114b33`
- name: `MDM_Policy_Result01_ApplicationManagement02_InvokeGetInstance`
- size: `1679`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x1801132f0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x1800051f4`
- `0x18000529c`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1801144a4`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180114743`
- `msvcrt!_wtoi` at `0x18011477a`
- `msvcrt!_wtoi` at `0x1801147b1`
- `msvcrt!_wtoi` at `0x1801147e8`
- `msvcrt!_wtoi` at `0x18011481f`
- `msvcrt!_wtoi` at `0x180114856`
- `msvcrt!_wtoi` at `0x18011488d`
- `msvcrt!_wtoi` at `0x1801148c4`
- `msvcrt!_wtoi` at `0x18011492a`
- `msvcrt!_wtoi` at `0x180114961`
- `msvcrt!_wtoi` at `0x180114998`
- `msvcrt!_wtoi` at `0x1801149cf`
- `msvcrt!_wtoi` at `0x180114a06`
- `msvcrt!_wtoi` at `0x180114743`
- `msvcrt!_wtoi` at `0x18011477a`
- `msvcrt!_wtoi` at `0x1801147b1`
- `msvcrt!_wtoi` at `0x1801147e8`
- `msvcrt!_wtoi` at `0x18011481f`
- `msvcrt!_wtoi` at `0x180114856`
- `msvcrt!_wtoi` at `0x18011488d`
- `msvcrt!_wtoi` at `0x1801148c4`
- `msvcrt!_wtoi` at `0x18011492a`
- `msvcrt!_wtoi` at `0x180114961`
- `msvcrt!_wtoi` at `0x180114998`
- `msvcrt!_wtoi` at `0x1801149cf`
- `msvcrt!_wtoi` at `0x180114a06`

## string_xrefs

- `0x18011475d`: `AllowAppStoreAutoUpdate`
- `0x180114870`: `BlockNonAdminUserInstall`
- `0x18011490d`: `MSIAllowUserControlOverInstall`
- `0x180114944`: `MSIAlwaysInstallWithElevatedPrivileges`
- `0x180114a20`: `ScheduleForceRestartForUpdateFailures`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_ApplicationManagement02_InvokeGetInstance(
        MI_Context *self,
        struct _MI_Instance *a2)
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
    v5 = CreateRequestHandlerInstance(
           (__int64)self,
           (wchar_t *)a2[1].serverName,
           (const unsigned __int16 *)a2[1].ft,
           (struct WmiNodeInfo *)&MDM_Policy_Result01_ApplicationManagement02_NodeList,
           0x11u,
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
          (struct WmiNodeInfo *)&MDM_Policy_Result01_ApplicationManagement02_NodeList,
          0x11u);
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
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowAllTrustedApps",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v18 = _wtoi(String);
                v19 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowAppStoreAutoUpdate",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v20 = _wtoi(String);
                v21 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowAutomaticAppArchiving",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v22 = _wtoi(String);
                v23 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowDeveloperUnlock",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v24 = _wtoi(String);
                v25 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowGameDVR",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v26 = _wtoi(String);
                v27 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowSharedUserAppData",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v28 = _wtoi(String);
                v29 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"BlockNonAdminUserInstall",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v30 = _wtoi(String);
                v31 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"DisableStoreOriginatedApps",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v32 = _wtoi(String);
                v33 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"LaunchAppAfterLogOn",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"MSIAllowUserControlOverInstall",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v34 = _wtoi(String);
                v35 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"MSIAlwaysInstallWithElevatedPrivileges",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v36 = _wtoi(String);
                v37 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"RequirePrivateStoreOnly",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v38 = _wtoi(String);
                v39 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"RestrictAppDataToSystemVolume",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v40 = _wtoi(String);
                v41 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"RestrictAppToSystemVolume",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v42 = _wtoi(String);
                v43 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ScheduleForceRestartForUpdateFailures",
                                    (const unsigned __int16 **)&String)
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
      &dword_18035E904,
      v15,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v13);
  return v5;
}

```

## disassembly

```asm
0x1801144a4  mov     [rsp+arg_10], rbx
0x1801144a9  push    rsi
0x1801144aa  push    rdi
0x1801144ab  push    r12
0x1801144ad  push    r14
0x1801144af  push    r15
0x1801144b1  sub     rsp, 1B0h
0x1801144b8  mov     rax, cs:__security_cookie
0x1801144bf  xor     rax, rsp
0x1801144c2  mov     [rsp+1D8h+var_38], rax
0x1801144ca  mov     rsi, rdx
0x1801144cd  mov     r15, rcx
0x1801144d0  xor     ebx, ebx
0x1801144d2  mov     [rsp+1D8h+String], rbx
0x1801144d7  xor     edx, edx; Val
0x1801144d9  mov     r8d, 0E8h; Size
0x1801144df  lea     rcx, [rsp+1D8h+instance]; void *
0x1801144e7  call    memset_0
0x1801144ec  mov     [rsp+1D8h+var_150], ebx
0x1801144f3  mov     [rsp+1D8h+var_14C], bl
0x1801144fa  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180114501  mov     [rsp+1D8h+var_180], rax
0x180114506  lea     rax, [rsp+1D8h+var_150]
0x18011450e  mov     [rsp+1D8h+var_178], rax
0x180114513  lea     rax, aMdmPolicyResul_187; "MDM_Policy_Result01_ApplicationManageme"...
0x18011451a  mov     [rsp+1D8h+var_170], rax
0x18011451f  lea     rcx, [rsp+1D8h+var_150]
0x180114527  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18011452c  mov     eax, cs:dword_180380B68
0x180114532  cmp     eax, 5
0x180114535  jbe     short loc_1801145A6
0x180114537  mov     rdx, 200000000000h
0x180114541  lea     rcx, dword_180380B68
0x180114548  call    _tlgKeywordOn
0x18011454d  test    al, al
0x18011454f  jz      short loc_1801145A6
0x180114551  cmp     [rsp+1D8h+var_14C], bl
0x180114558  jz      short loc_180114588
0x18011455a  cmp     [rsp+1D8h+var_138], ebx
0x180114561  jnz     short loc_18011457E
0x180114563  cmp     [rsp+1D8h+var_134], ebx
0x18011456a  jnz     short loc_18011457E
0x18011456c  cmp     [rsp+1D8h+var_130], ebx
0x180114573  jnz     short loc_18011457E
0x180114575  cmp     [rsp+1D8h+var_12C], ebx
0x18011457c  jz      short loc_180114588
0x18011457e  lea     r9, [rsp+1D8h+var_138]
0x180114586  jmp     short loc_18011458B
0x180114588  mov     r9, rbx
0x18011458b  lea     r8, [rsp+1D8h+var_148]
0x180114593  lea     rdx, byte_18035D317
0x18011459a  lea     rcx, dword_180380B68
0x1801145a1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801145a6  cmp     [rsi+48h], bl
0x1801145a9  jz      loc_180114A92
0x1801145af  mov     [rsp+1D8h+var_190], bl
0x1801145b3  cmp     [rsi+58h], bl
0x1801145b6  jz      loc_180114A92
0x1801145bc  mov     r9, [rsi+40h]; unsigned __int16 *
0x1801145c0  mov     r8, [rsi+50h]; unsigned __int16 *
0x1801145c4  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1801145cb  lea     rcx, [rsp+1D8h+var_180]; this
0x1801145d0  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1801145d5  nop
0x1801145d6  mov     [rsp+1D8h+var_188], rbx
0x1801145db  lea     rax, [rsp+1D8h+var_188]
0x1801145e0  mov     [rsp+1D8h+var_1A8], rax
0x1801145e5  mov     [rsp+1D8h+var_1B0], ebx
0x1801145e9  mov     [rsp+1D8h+var_1B8], 11h
0x1801145f1  lea     r9, ?MDM_Policy_Result01_ApplicationManagement02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_ApplicationManagement02_NodeList
0x1801145f8  mov     r8, [rsi+40h]
0x1801145fc  mov     rdx, [rsi+50h]
0x180114600  mov     rcx, r15
0x180114603  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180114608  mov     r14d, eax
0x18011460b  test    eax, eax
0x18011460d  jz      short loc_180114614
0x18011460f  jmp     loc_180114A98
0x180114614  lea     rax, [rsp+1D8h+var_188]
0x180114619  mov     [rsp+1D8h+var_160], rax
0x18011461e  mov     r12d, 1
0x180114624  mov     [rsp+1D8h+var_158], r12b
0x18011462c  mov     rdi, [rsp+1D8h+var_188]
0x180114631  test    rdi, rdi
0x180114634  jnz     short loc_18011463E
0x180114636  mov     r14d, r12d
0x180114639  jmp     loc_180114A98
0x18011463e  mov     r9d, 11h; unsigned int
0x180114644  lea     r8, ?MDM_Policy_Result01_ApplicationManagement02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18011464b  mov     rdx, rsi; struct _MI_Instance *
0x18011464e  mov     rcx, rdi; this
0x180114651  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x180114656  mov     rax, [rdi]
0x180114659  mov     rcx, rdi
0x18011465c  mov     rax, [rax+10h]
0x180114660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114665  mov     r14d, eax
0x180114668  test    eax, eax
0x18011466a  jz      short loc_18011468A
0x18011466c  mov     rcx, [rsp+1D8h+var_188]
0x180114671  test    rcx, rcx
0x180114674  jz      short loc_180114685
0x180114676  mov     rax, [rcx]
0x180114679  mov     edx, r12d
0x18011467c  mov     rax, [rax]
0x18011467f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114684  nop
0x180114685  jmp     loc_180114A98
0x18011468a  mov     rax, [rdi]
0x18011468d  mov     rcx, rdi
0x180114690  mov     rax, [rax+8]
0x180114694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114699  mov     r14d, eax
0x18011469c  test    eax, eax
0x18011469e  jz      short loc_1801146BE
0x1801146a0  mov     rcx, [rsp+1D8h+var_188]
0x1801146a5  test    rcx, rcx
0x1801146a8  jz      short loc_1801146B9
0x1801146aa  mov     rax, [rcx]
0x1801146ad  mov     edx, r12d
0x1801146b0  mov     rax, [rax]
0x1801146b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801146b8  nop
0x1801146b9  jmp     loc_180114A98
0x1801146be  lea     r8, [rsp+1D8h+instance]; instance
0x1801146c6  lea     rdx, MDM_Policy_Result01_ApplicationManagement02_rtti; classDecl
0x1801146cd  mov     rcx, r15; context
0x1801146d0  call    MI_Context_ConstructInstance
0x1801146d5  mov     r14d, eax
0x1801146d8  test    eax, eax
0x1801146da  jz      short loc_1801146FA
0x1801146dc  mov     rcx, [rsp+1D8h+var_188]
0x1801146e1  test    rcx, rcx
0x1801146e4  jz      short loc_1801146F5
0x1801146e6  mov     rax, [rcx]
0x1801146e9  mov     edx, r12d
0x1801146ec  mov     rax, [rax]
0x1801146ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801146f4  nop
0x1801146f5  jmp     loc_180114A98
0x1801146fa  mov     [rsp+1D8h+var_190], r12b
0x1801146ff  mov     rdx, [rsi+40h]
0x180114703  lea     rcx, [rsp+1D8h+instance]
0x18011470b  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180114710  mov     rdx, [rsi+50h]
0x180114714  lea     rcx, [rsp+1D8h+instance]
0x18011471c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180114721  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180114726  lea     rdx, aAllowalltruste; "AllowAllTrustedApps"
0x18011472d  mov     rcx, rdi; this
0x180114730  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180114735  test    eax, eax
0x180114737  jnz     short loc_180114758
0x180114739  mov     rcx, [rsp+1D8h+String]; String
0x18011473e  test    rcx, rcx
0x180114741  jz      short loc_180114758
0x180114743  call    cs:__imp__wtoi
0x180114749  mov     [rsp+1D8h+var_C8], eax
0x180114750  mov     [rsp+1D8h+var_C4], r12b
0x180114758  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18011475d  lea     rdx, aAllowappstorea; "AllowAppStoreAutoUpdate"
0x180114764  mov     rcx, rdi; this
0x180114767  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18011476c  test    eax, eax
0x18011476e  jnz     short loc_18011478F
0x180114770  mov     rcx, [rsp+1D8h+String]; String
0x180114775  test    rcx, rcx
0x180114778  jz      short loc_18011478F
0x18011477a  call    cs:__imp__wtoi
0x180114780  mov     [rsp+1D8h+var_C0], eax
0x180114787  mov     [rsp+1D8h+var_BC], r12b
0x18011478f  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180114794  lea     rdx, aAllowautomatic_0; "AllowAutomaticAppArchiving"
0x18011479b  mov     rcx, rdi; this
0x18011479e  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801147a3  test    eax, eax
0x1801147a5  jnz     short loc_1801147C6
0x1801147a7  mov     rcx, [rsp+1D8h+String]; String
0x1801147ac  test    rcx, rcx
0x1801147af  jz      short loc_1801147C6
0x1801147b1  call    cs:__imp__wtoi
0x1801147b7  mov     [rsp+1D8h+var_B8], eax
0x1801147be  mov     [rsp+1D8h+var_B4], r12b
0x1801147c6  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x1801147cb  lea     rdx, aAllowdeveloper_0; "AllowDeveloperUnlock"
0x1801147d2  mov     rcx, rdi; this
0x1801147d5  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801147da  test    eax, eax
0x1801147dc  jnz     short loc_1801147FD
0x1801147de  mov     rcx, [rsp+1D8h+String]; String
0x1801147e3  test    rcx, rcx
0x1801147e6  jz      short loc_1801147FD
0x1801147e8  call    cs:__imp__wtoi
0x1801147ee  mov     [rsp+1D8h+var_B0], eax
0x1801147f5  mov     [rsp+1D8h+var_AC], r12b
0x1801147fd  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180114802  lea     rdx, aAllowgamedvr; "AllowGameDVR"
0x180114809  mov     rcx, rdi; this
0x18011480c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180114811  test    eax, eax
0x180114813  jnz     short loc_180114834
0x180114815  mov     rcx, [rsp+1D8h+String]; String
0x18011481a  test    rcx, rcx
0x18011481d  jz      short loc_180114834
0x18011481f  call    cs:__imp__wtoi
0x180114825  mov     [rsp+1D8h+var_A8], eax
0x18011482c  mov     [rsp+1D8h+var_A4], r12b
0x180114834  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180114839  lea     rdx, aAllowshareduse; "AllowSharedUserAppData"
0x180114840  mov     rcx, rdi; this
0x180114843  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180114848  test    eax, eax
0x18011484a  jnz     short loc_18011486B
0x18011484c  mov     rcx, [rsp+1D8h+String]; String
0x180114851  test    rcx, rcx
0x180114854  jz      short loc_18011486B
0x180114856  call    cs:__imp__wtoi
0x18011485c  mov     [rsp+1D8h+var_A0], eax
0x180114863  mov     [rsp+1D8h+var_9C], r12b
0x18011486b  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180114870  lea     rdx, aBlocknonadminu; "BlockNonAdminUserInstall"
0x180114877  mov     rcx, rdi; this
0x18011487a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18011487f  test    eax, eax
0x180114881  jnz     short loc_1801148A2
0x180114883  mov     rcx, [rsp+1D8h+String]; String
0x180114888  test    rcx, rcx
0x18011488b  jz      short loc_1801148A2
0x18011488d  call    cs:__imp__wtoi
0x180114893  mov     [rsp+1D8h+var_98], eax
0x18011489a  mov     [rsp+1D8h+var_94], r12b
0x1801148a2  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x1801148a7  lea     rdx, aDisablestoreor; "DisableStoreOriginatedApps"
0x1801148ae  mov     rcx, rdi; this
0x1801148b1  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801148b6  test    eax, eax
0x1801148b8  jnz     short loc_1801148D9
0x1801148ba  mov     rcx, [rsp+1D8h+String]; String
0x1801148bf  test    rcx, rcx
0x1801148c2  jz      short loc_1801148D9
0x1801148c4  call    cs:__imp__wtoi
0x1801148ca  mov     [rsp+1D8h+var_90], eax
0x1801148d1  mov     [rsp+1D8h+var_8C], r12b
0x1801148d9  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x1801148de  lea     rdx, aLaunchappafter; "LaunchAppAfterLogOn"
0x1801148e5  mov     rcx, rdi; this
0x1801148e8  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801148ed  test    eax, eax
0x1801148ef  jnz     short loc_180114908
0x1801148f1  mov     rdx, [rsp+1D8h+String]
0x1801148f6  test    rdx, rdx
0x1801148f9  jz      short loc_180114908
0x1801148fb  lea     rcx, [rsp+1D8h+instance]
0x180114903  call    MDM_VPNv2_01_Set_TrustedNetworkDetection
0x180114908  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18011490d  lea     rdx, aMsiallowuserco; "MSIAllowUserControlOverInstall"
0x180114914  mov     rcx, rdi; this
0x180114917  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18011491c  test    eax, eax
0x18011491e  jnz     short loc_18011493F
0x180114920  mov     rcx, [rsp+1D8h+String]; String
0x180114925  test    rcx, rcx
0x180114928  jz      short loc_18011493F
0x18011492a  call    cs:__imp__wtoi
0x180114930  mov     [rsp+1D8h+var_78], eax
0x180114937  mov     [rsp+1D8h+var_74], r12b
0x18011493f  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x180114944  lea     rdx, aMsialwaysinsta; "MSIAlwaysInstallWithElevatedPrivileges"
0x18011494b  mov     rcx, rdi; this
0x18011494e  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x180114953  test    eax, eax
0x180114955  jnz     short loc_180114976
0x180114957  mov     rcx, [rsp+1D8h+String]; String
0x18011495c  test    rcx, rcx
0x18011495f  jz      short loc_180114976
0x180114961  call    cs:__imp__wtoi
0x180114967  mov     [rsp+1D8h+var_70], eax
0x18011496e  mov     [rsp+1D8h+var_6C], r12b
0x180114976  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x18011497b  lea     rdx, aRequireprivate; "RequirePrivateStoreOnly"
0x180114982  mov     rcx, rdi; this
0x180114985  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18011498a  test    eax, eax
0x18011498c  jnz     short loc_1801149AD
0x18011498e  mov     rcx, [rsp+1D8h+String]; String
0x180114993  test    rcx, rcx
0x180114996  jz      short loc_1801149AD
0x180114998  call    cs:__imp__wtoi
0x18011499e  mov     [rsp+1D8h+var_68], eax
0x1801149a5  mov     [rsp+1D8h+var_64], r12b
0x1801149ad  lea     r8, [rsp+1D8h+String]; unsigned __int16 **
0x1801149b2  lea     rdx, aRestrictappdat; "RestrictAppDataToSystemVolume"
0x1801149b9  mov     rcx, rdi; this
0x1801149bc  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1801149c1  test    eax, eax
0x1801149c3  jnz     short loc_1801149E4
0x1801149c5  mov     rcx, [rsp+1D8h+String]; String
0x1801149ca  test    rcx, rcx
0x1801149cd  jz      short loc_1801149E4
0x1801149cf  call    cs:__imp__wtoi
  ... truncated ...
```
