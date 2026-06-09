# MDM_Policy_Config01_ApplicationManagement02_InvokeEnumerateInstances

- ea: `0x18005c644`
- end: `0x18005cdeb`
- name: `MDM_Policy_Config01_ApplicationManagement02_InvokeEnumerateInstances`
- size: `1959`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x18005bc00`

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
- `0x18005c644`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18005c956`
- `msvcrt!_wtoi` at `0x18005c997`
- `msvcrt!_wtoi` at `0x18005c9d8`
- `msvcrt!_wtoi` at `0x18005ca19`
- `msvcrt!_wtoi` at `0x18005ca5a`
- `msvcrt!_wtoi` at `0x18005ca9b`
- `msvcrt!_wtoi` at `0x18005cadc`
- `msvcrt!_wtoi` at `0x18005cb1d`
- `msvcrt!_wtoi` at `0x18005cb97`
- `msvcrt!_wtoi` at `0x18005cbd8`
- `msvcrt!_wtoi` at `0x18005cc19`
- `msvcrt!_wtoi` at `0x18005cc5a`
- `msvcrt!_wtoi` at `0x18005cc9b`
- `msvcrt!_wtoi` at `0x18005c956`
- `msvcrt!_wtoi` at `0x18005c997`
- `msvcrt!_wtoi` at `0x18005c9d8`
- `msvcrt!_wtoi` at `0x18005ca19`
- `msvcrt!_wtoi` at `0x18005ca5a`
- `msvcrt!_wtoi` at `0x18005ca9b`
- `msvcrt!_wtoi` at `0x18005cadc`
- `msvcrt!_wtoi` at `0x18005cb1d`
- `msvcrt!_wtoi` at `0x18005cb97`
- `msvcrt!_wtoi` at `0x18005cbd8`
- `msvcrt!_wtoi` at `0x18005cc19`
- `msvcrt!_wtoi` at `0x18005cc5a`
- `msvcrt!_wtoi` at `0x18005cc9b`

## string_xrefs

- `0x18005c973`: `AllowAppStoreAutoUpdate`
- `0x18005cab8`: `BlockNonAdminUserInstall`
- `0x18005cb73`: `MSIAllowUserControlOverInstall`
- `0x18005cbb4`: `MSIAlwaysInstallWithElevatedPrivileges`
- `0x18005ccb8`: `ScheduleForceRestartForUpdateFailures`
- `0x18005c898`: `./Vendor/MSFT/Policy/Config`
- `0x18005c6bf`: `MDM_Policy_Config01_ApplicationManagement02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_ApplicationManagement02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  unsigned int v7; // r14d
  WmiRequestHandlerAdd *v8; // rsi
  unsigned int i; // r15d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+48h] [rbp-190h] BYREF
  WmiRequestHandlerAdd *v14; // [rsp+50h] [rbp-188h] BYREF
  _QWORD v15[3]; // [rsp+58h] [rbp-180h] BYREF
  const exception *v16[2]; // [rsp+70h] [rbp-168h] BYREF
  char v17; // [rsp+80h] [rbp-158h]
  int v18; // [rsp+88h] [rbp-150h] BYREF
  char v19; // [rsp+8Ch] [rbp-14Ch]
  _BYTE v20[16]; // [rsp+90h] [rbp-148h] BYREF
  _DWORD v21[4]; // [rsp+A0h] [rbp-138h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-128h] BYREF
  int v23; // [rsp+110h] [rbp-C8h]
  char v24; // [rsp+114h] [rbp-C4h]
  int v25; // [rsp+118h] [rbp-C0h]
  char v26; // [rsp+11Ch] [rbp-BCh]
  int v27; // [rsp+120h] [rbp-B8h]
  char v28; // [rsp+124h] [rbp-B4h]
  int v29; // [rsp+128h] [rbp-B0h]
  char v30; // [rsp+12Ch] [rbp-ACh]
  int v31; // [rsp+130h] [rbp-A8h]
  char v32; // [rsp+134h] [rbp-A4h]
  int v33; // [rsp+138h] [rbp-A0h]
  char v34; // [rsp+13Ch] [rbp-9Ch]
  int v35; // [rsp+140h] [rbp-98h]
  char v36; // [rsp+144h] [rbp-94h]
  int v37; // [rsp+148h] [rbp-90h]
  char v38; // [rsp+14Ch] [rbp-8Ch]
  int v39; // [rsp+160h] [rbp-78h]
  char v40; // [rsp+164h] [rbp-74h]
  int v41; // [rsp+168h] [rbp-70h]
  char v42; // [rsp+16Ch] [rbp-6Ch]
  int v43; // [rsp+170h] [rbp-68h]
  char v44; // [rsp+174h] [rbp-64h]
  int v45; // [rsp+178h] [rbp-60h]
  char v46; // [rsp+17Ch] [rbp-5Ch]
  int v47; // [rsp+180h] [rbp-58h]
  char v48; // [rsp+184h] [rbp-54h]

  memset_0(&instance, 0, 0xE8u);
  String = 0;
  v18 = 0;
  v19 = 0;
  v15[0] = &TelemetryEventWriter::`vftable';
  v15[1] = &v18;
  v15[2] = "MDM_Policy_Config01_ApplicationManagement02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v18);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v19 && (v21[0] || v21[1] || v21[2] || v21[3]) )
      v5 = v21;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      word_18035840A,
      v20,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v15, v4);
  try
  {
    v14 = 0;
    v7 = CreateRequestHandlerInstance(
           (__int64)self,
           0,
           0,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_ApplicationManagement02_NodeList,
           0x11u,
           2,
           &v14);
    if ( !v7 )
    {
      v16[1] = (const exception *)&v14;
      v17 = 1;
      v8 = v14;
      if ( v14 )
      {
        v7 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v14 + 16LL))(v14);
        if ( v7 )
        {
          v6 = v14;
          if ( v14 )
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
        }
        else
        {
          v7 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v8 + 8LL))(v8);
          if ( v7 )
          {
            v6 = v14;
            if ( v14 )
              (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
          }
          else
          {
            for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)v8 + 33) - *((_QWORD *)v8 + 32)) >> 4); ++i )
            {
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_ApplicationManagement02_rtti, &instance);
              if ( v7 )
              {
                v6 = v14;
                if ( v14 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_91;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/Policy/Config",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                      v8,
                      i,
                      L"ApplicationManagement",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, String);
              }
              if ( a2 != 1 )
              {
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowAllTrustedApps",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowAppStoreAutoUpdate",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowAutomaticAppArchiving",
                        &String)
                  && String )
                {
                  v27 = _wtoi(String);
                  v28 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowDeveloperUnlock",
                        &String)
                  && String )
                {
                  v29 = _wtoi(String);
                  v30 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowGameDVR",
                        &String)
                  && String )
                {
                  v31 = _wtoi(String);
                  v32 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowSharedUserAppData",
                        &String)
                  && String )
                {
                  v33 = _wtoi(String);
                  v34 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"BlockNonAdminUserInstall",
                        &String)
                  && String )
                {
                  v35 = _wtoi(String);
                  v36 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableStoreOriginatedApps",
                        &String)
                  && String )
                {
                  v37 = _wtoi(String);
                  v38 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"LaunchAppAfterLogOn",
                        &String)
                  && String )
                {
                  MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"MSIAllowUserControlOverInstall",
                        &String)
                  && String )
                {
                  v39 = _wtoi(String);
                  v40 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"MSIAlwaysInstallWithElevatedPrivileges",
                        &String)
                  && String )
                {
                  v41 = _wtoi(String);
                  v42 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"RequirePrivateStoreOnly",
                        &String)
                  && String )
                {
                  v43 = _wtoi(String);
                  v44 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"RestrictAppDataToSystemVolume",
                        &String)
                  && String )
                {
                  v45 = _wtoi(String);
                  v46 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"RestrictAppToSystemVolume",
                        &String)
                  && String )
                {
                  v47 = _wtoi(String);
                  v48 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ScheduleForceRestartForUpdateFailures",
                        &String)
                  && String )
                {
                  MDM_Policy_User_Result01_InternetExplorer02_Set_AllowLocalMachineZoneTemplate(&instance);
                }
              }
              MI_Instance_Destruct((MI_Instance *)self);
              MI_Instance_Destruct(&instance);
            }
            v6 = v14;
            if ( v14 )
            {
              (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
              v14 = 0;
            }
          }
        }
      }
      else
      {
        v7 = 1;
      }
    }
  }
  catch ( const exception *v16 )
  {
    v11 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v16[0] + 8LL))(v16[0]);
    TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v15, v11);
    LODWORD(v14) = 1;
    v7 = 1;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v6);
    TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v15, v12);
    LODWORD(v14) = 1;
    v7 = 1;
  }
LABEL_91:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v15, "EnumerateInstancesEnd", v7);
  v18 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_18036E83C,
      v20,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v18);
  return v7;
}

```

## disassembly

```asm
0x18005c644  mov     [rsp+arg_8], rbx
0x18005c649  mov     [rsp+arg_10], rsi
0x18005c64e  push    rdi
0x18005c64f  push    r12
0x18005c651  push    r13
0x18005c653  push    r14
0x18005c655  push    r15
0x18005c657  sub     rsp, 1B0h
0x18005c65e  mov     rax, cs:__security_cookie
0x18005c665  xor     rax, rsp
0x18005c668  mov     [rsp+1D8h+var_38], rax
0x18005c670  mov     r13b, dl
0x18005c673  mov     r12, rcx
0x18005c676  xor     edx, edx; Val
0x18005c678  mov     r8d, 0E8h; Size
0x18005c67e  lea     rcx, [rsp+1D8h+instance]; void *
0x18005c686  call    memset_0
0x18005c68b  xor     edi, edi
0x18005c68d  mov     [rsp+1D8h+var_198], dil
0x18005c692  mov     [rsp+1D8h+String], rdi
0x18005c697  mov     [rsp+1D8h+var_150], edi
0x18005c69e  mov     [rsp+1D8h+var_14C], dil
0x18005c6a6  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18005c6ad  mov     [rsp+1D8h+var_180], rax
0x18005c6b2  lea     rax, [rsp+1D8h+var_150]
0x18005c6ba  mov     [rsp+1D8h+var_178], rax
0x18005c6bf  lea     rax, aMdmPolicyConfi_160; "MDM_Policy_Config01_ApplicationManageme"...
0x18005c6c6  mov     [rsp+1D8h+var_170], rax
0x18005c6cb  lea     rcx, [rsp+1D8h+var_150]
0x18005c6d3  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18005c6d8  mov     eax, cs:dword_180380B68
0x18005c6de  cmp     eax, 5
0x18005c6e1  jbe     short loc_18005C753
0x18005c6e3  mov     rdx, 200000000000h
0x18005c6ed  lea     rcx, dword_180380B68
0x18005c6f4  call    _tlgKeywordOn
0x18005c6f9  test    al, al
0x18005c6fb  jz      short loc_18005C753
0x18005c6fd  cmp     [rsp+1D8h+var_14C], dil
0x18005c705  jz      short loc_18005C735
0x18005c707  cmp     [rsp+1D8h+var_138], edi
0x18005c70e  jnz     short loc_18005C72B
0x18005c710  cmp     [rsp+1D8h+var_134], edi
0x18005c717  jnz     short loc_18005C72B
0x18005c719  cmp     [rsp+1D8h+var_130], edi
0x18005c720  jnz     short loc_18005C72B
0x18005c722  cmp     [rsp+1D8h+var_12C], edi
0x18005c729  jz      short loc_18005C735
0x18005c72b  lea     r9, [rsp+1D8h+var_138]
0x18005c733  jmp     short loc_18005C738
0x18005c735  mov     r9, rdi
0x18005c738  lea     r8, [rsp+1D8h+var_148]
0x18005c740  lea     rdx, word_18035840A
0x18005c747  lea     rcx, dword_180380B68
0x18005c74e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18005c753  lea     rcx, [rsp+1D8h+var_180]; this
0x18005c758  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18005c75d  nop
0x18005c75e  mov     [rsp+1D8h+var_188], rdi
0x18005c763  lea     rax, [rsp+1D8h+var_188]
0x18005c768  mov     [rsp+1D8h+var_1A8], rax
0x18005c76d  mov     [rsp+1D8h+var_1B0], 2
0x18005c775  mov     [rsp+1D8h+var_1B8], 11h
0x18005c77d  lea     r9, ?MDM_Policy_Config01_ApplicationManagement02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_ApplicationManagement02_NodeList
0x18005c784  xor     r8d, r8d
0x18005c787  xor     edx, edx
0x18005c789  mov     rcx, r12
0x18005c78c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18005c791  mov     r14d, eax
0x18005c794  test    eax, eax
0x18005c796  jz      short loc_18005C79D
0x18005c798  jmp     loc_18005CD4B
0x18005c79d  lea     rbx, [rsp+1D8h+var_188]
0x18005c7a2  mov     [rsp+1D8h+var_160], rbx
0x18005c7a7  mov     r15d, 1
0x18005c7ad  mov     [rsp+1D8h+var_158], r15b
0x18005c7b5  mov     rsi, [rsp+1D8h+var_188]
0x18005c7ba  test    rsi, rsi
0x18005c7bd  jnz     short loc_18005C7C7
0x18005c7bf  mov     r14d, r15d
0x18005c7c2  jmp     loc_18005CD4B
0x18005c7c7  mov     rax, [rsi]
0x18005c7ca  mov     rcx, rsi
0x18005c7cd  mov     rax, [rax+10h]
0x18005c7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c7d6  mov     r14d, eax
0x18005c7d9  test    eax, eax
0x18005c7db  jz      short loc_18005C7FB
0x18005c7dd  mov     rcx, [rsp+1D8h+var_188]
0x18005c7e2  test    rcx, rcx
0x18005c7e5  jz      short loc_18005C7F6
0x18005c7e7  mov     rax, [rcx]
0x18005c7ea  mov     edx, r15d
0x18005c7ed  mov     rax, [rax]
0x18005c7f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c7f5  nop
0x18005c7f6  jmp     loc_18005CD4B
0x18005c7fb  mov     rax, [rsi]
0x18005c7fe  mov     rcx, rsi
0x18005c801  mov     rax, [rax+8]
0x18005c805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c80a  mov     r14d, eax
0x18005c80d  test    eax, eax
0x18005c80f  jz      short loc_18005C82F
0x18005c811  mov     rcx, [rsp+1D8h+var_188]
0x18005c816  test    rcx, rcx
0x18005c819  jz      short loc_18005C82A
0x18005c81b  mov     rax, [rcx]
0x18005c81e  mov     edx, r15d
0x18005c821  mov     rax, [rax]
0x18005c824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c829  nop
0x18005c82a  jmp     loc_18005CD4B
0x18005c82f  mov     r15d, edi
0x18005c832  mov     rax, [rsi+108h]
0x18005c839  sub     rax, [rsi+100h]
0x18005c840  sar     rax, 4
0x18005c844  cmp     r15d, eax
0x18005c847  jnb     loc_18005CD13
0x18005c84d  lea     r8, [rsp+1D8h+instance]; instance
0x18005c855  lea     rdx, MDM_Policy_Config01_ApplicationManagement02_rtti; classDecl
0x18005c85c  mov     rcx, r12; context
0x18005c85f  call    MI_Context_ConstructInstance
0x18005c864  mov     r14d, eax
0x18005c867  test    eax, eax
0x18005c869  jz      short loc_18005C88B
0x18005c86b  mov     rcx, [rbx]
0x18005c86e  test    rcx, rcx
0x18005c871  jz      short loc_18005C886
0x18005c873  mov     rax, [rcx]
0x18005c876  mov     edx, 1
0x18005c87b  mov     rax, [rax]
0x18005c87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c883  mov     [rbx], rdi
0x18005c886  jmp     loc_18005CD4B
0x18005c88b  mov     [rsp+1D8h+var_198], 1
0x18005c890  mov     rax, [rsi]
0x18005c893  lea     r9, [rsp+1D8h+String]
0x18005c898  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x18005c89f  mov     edx, r15d
0x18005c8a2  mov     rcx, rsi
0x18005c8a5  mov     rax, [rax+18h]
0x18005c8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c8ae  test    eax, eax
0x18005c8b0  jnz     short loc_18005C8C9
0x18005c8b2  mov     rdx, [rsp+1D8h+String]
0x18005c8b7  test    rdx, rdx
0x18005c8ba  jz      short loc_18005C8C9
0x18005c8bc  lea     rcx, [rsp+1D8h+instance]
0x18005c8c4  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18005c8c9  mov     rax, [rsi]
0x18005c8cc  lea     r9, [rsp+1D8h+String]
0x18005c8d1  lea     r8, aApplicationman; "ApplicationManagement"
0x18005c8d8  mov     edx, r15d
0x18005c8db  mov     rcx, rsi
0x18005c8de  mov     rax, [rax+18h]
0x18005c8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c8e7  test    eax, eax
0x18005c8e9  jnz     short loc_18005C902
0x18005c8eb  mov     rdx, [rsp+1D8h+String]
0x18005c8f0  test    rdx, rdx
0x18005c8f3  jz      short loc_18005C902
0x18005c8f5  lea     rcx, [rsp+1D8h+instance]
0x18005c8fd  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18005c902  cmp     r13b, 1
0x18005c906  jnz     short loc_18005C92A
0x18005c908  lea     rdx, [rsp+1D8h+instance]
0x18005c910  mov     rcx, r12; self
0x18005c913  call    MI_Instance_Destruct
0x18005c918  lea     rcx, [rsp+1D8h+instance]; self
0x18005c920  call    MI_Instance_Destruct
0x18005c925  jmp     loc_18005CD06
0x18005c92a  mov     rax, [rsi]
0x18005c92d  lea     r9, [rsp+1D8h+String]
0x18005c932  lea     r8, aAllowalltruste; "AllowAllTrustedApps"
0x18005c939  mov     edx, r15d
0x18005c93c  mov     rcx, rsi
0x18005c93f  mov     rax, [rax+18h]
0x18005c943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c948  test    eax, eax
0x18005c94a  jnz     short loc_18005C96B
0x18005c94c  mov     rcx, [rsp+1D8h+String]; String
0x18005c951  test    rcx, rcx
0x18005c954  jz      short loc_18005C96B
0x18005c956  call    cs:__imp__wtoi
0x18005c95c  mov     [rsp+1D8h+var_C8], eax
0x18005c963  mov     [rsp+1D8h+var_C4], 1
0x18005c96b  mov     rax, [rsi]
0x18005c96e  lea     r9, [rsp+1D8h+String]
0x18005c973  lea     r8, aAllowappstorea; "AllowAppStoreAutoUpdate"
0x18005c97a  mov     edx, r15d
0x18005c97d  mov     rcx, rsi
0x18005c980  mov     rax, [rax+18h]
0x18005c984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c989  test    eax, eax
0x18005c98b  jnz     short loc_18005C9AC
0x18005c98d  mov     rcx, [rsp+1D8h+String]; String
0x18005c992  test    rcx, rcx
0x18005c995  jz      short loc_18005C9AC
0x18005c997  call    cs:__imp__wtoi
0x18005c99d  mov     [rsp+1D8h+var_C0], eax
0x18005c9a4  mov     [rsp+1D8h+var_BC], 1
0x18005c9ac  mov     rax, [rsi]
0x18005c9af  lea     r9, [rsp+1D8h+String]
0x18005c9b4  lea     r8, aAllowautomatic_0; "AllowAutomaticAppArchiving"
0x18005c9bb  mov     edx, r15d
0x18005c9be  mov     rcx, rsi
0x18005c9c1  mov     rax, [rax+18h]
0x18005c9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c9ca  test    eax, eax
0x18005c9cc  jnz     short loc_18005C9ED
0x18005c9ce  mov     rcx, [rsp+1D8h+String]; String
0x18005c9d3  test    rcx, rcx
0x18005c9d6  jz      short loc_18005C9ED
0x18005c9d8  call    cs:__imp__wtoi
0x18005c9de  mov     [rsp+1D8h+var_B8], eax
0x18005c9e5  mov     [rsp+1D8h+var_B4], 1
0x18005c9ed  mov     rax, [rsi]
0x18005c9f0  lea     r9, [rsp+1D8h+String]
0x18005c9f5  lea     r8, aAllowdeveloper_0; "AllowDeveloperUnlock"
0x18005c9fc  mov     edx, r15d
0x18005c9ff  mov     rcx, rsi
0x18005ca02  mov     rax, [rax+18h]
0x18005ca06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca0b  test    eax, eax
0x18005ca0d  jnz     short loc_18005CA2E
0x18005ca0f  mov     rcx, [rsp+1D8h+String]; String
0x18005ca14  test    rcx, rcx
0x18005ca17  jz      short loc_18005CA2E
0x18005ca19  call    cs:__imp__wtoi
0x18005ca1f  mov     [rsp+1D8h+var_B0], eax
0x18005ca26  mov     [rsp+1D8h+var_AC], 1
0x18005ca2e  mov     rax, [rsi]
0x18005ca31  lea     r9, [rsp+1D8h+String]
0x18005ca36  lea     r8, aAllowgamedvr; "AllowGameDVR"
0x18005ca3d  mov     edx, r15d
0x18005ca40  mov     rcx, rsi
0x18005ca43  mov     rax, [rax+18h]
0x18005ca47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca4c  test    eax, eax
0x18005ca4e  jnz     short loc_18005CA6F
0x18005ca50  mov     rcx, [rsp+1D8h+String]; String
0x18005ca55  test    rcx, rcx
0x18005ca58  jz      short loc_18005CA6F
0x18005ca5a  call    cs:__imp__wtoi
0x18005ca60  mov     [rsp+1D8h+var_A8], eax
0x18005ca67  mov     [rsp+1D8h+var_A4], 1
0x18005ca6f  mov     rax, [rsi]
0x18005ca72  lea     r9, [rsp+1D8h+String]
0x18005ca77  lea     r8, aAllowshareduse; "AllowSharedUserAppData"
0x18005ca7e  mov     edx, r15d
0x18005ca81  mov     rcx, rsi
0x18005ca84  mov     rax, [rax+18h]
0x18005ca88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca8d  test    eax, eax
0x18005ca8f  jnz     short loc_18005CAB0
0x18005ca91  mov     rcx, [rsp+1D8h+String]; String
0x18005ca96  test    rcx, rcx
0x18005ca99  jz      short loc_18005CAB0
0x18005ca9b  call    cs:__imp__wtoi
0x18005caa1  mov     [rsp+1D8h+var_A0], eax
0x18005caa8  mov     [rsp+1D8h+var_9C], 1
0x18005cab0  mov     rax, [rsi]
0x18005cab3  lea     r9, [rsp+1D8h+String]
0x18005cab8  lea     r8, aBlocknonadminu; "BlockNonAdminUserInstall"
0x18005cabf  mov     edx, r15d
0x18005cac2  mov     rcx, rsi
0x18005cac5  mov     rax, [rax+18h]
0x18005cac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cace  test    eax, eax
0x18005cad0  jnz     short loc_18005CAF1
0x18005cad2  mov     rcx, [rsp+1D8h+String]; String
0x18005cad7  test    rcx, rcx
0x18005cada  jz      short loc_18005CAF1
0x18005cadc  call    cs:__imp__wtoi
0x18005cae2  mov     [rsp+1D8h+var_98], eax
0x18005cae9  mov     [rsp+1D8h+var_94], 1
0x18005caf1  mov     rax, [rsi]
0x18005caf4  lea     r9, [rsp+1D8h+String]
0x18005caf9  lea     r8, aDisablestoreor; "DisableStoreOriginatedApps"
0x18005cb00  mov     edx, r15d
0x18005cb03  mov     rcx, rsi
0x18005cb06  mov     rax, [rax+18h]
0x18005cb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb0f  test    eax, eax
0x18005cb11  jnz     short loc_18005CB32
0x18005cb13  mov     rcx, [rsp+1D8h+String]; String
0x18005cb18  test    rcx, rcx
0x18005cb1b  jz      short loc_18005CB32
0x18005cb1d  call    cs:__imp__wtoi
0x18005cb23  mov     [rsp+1D8h+var_90], eax
0x18005cb2a  mov     [rsp+1D8h+var_8C], 1
0x18005cb32  mov     rax, [rsi]
0x18005cb35  lea     r9, [rsp+1D8h+String]
0x18005cb3a  lea     r8, aLaunchappafter; "LaunchAppAfterLogOn"
0x18005cb41  mov     edx, r15d
0x18005cb44  mov     rcx, rsi
0x18005cb47  mov     rax, [rax+18h]
0x18005cb4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb50  test    eax, eax
  ... truncated ...
```
