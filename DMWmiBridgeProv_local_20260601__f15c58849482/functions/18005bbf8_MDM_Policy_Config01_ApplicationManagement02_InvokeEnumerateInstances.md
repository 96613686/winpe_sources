# MDM_Policy_Config01_ApplicationManagement02_InvokeEnumerateInstances

- ea: `0x18005bbf8`
- end: `0x18005c3ee`
- name: `MDM_Policy_Config01_ApplicationManagement02_InvokeEnumerateInstances`
- size: `2038`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x18005b1d0`

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
- `0x18005bbf8`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18005bf0a`
- `msvcrt!_wtoi` at `0x18005bf51`
- `msvcrt!_wtoi` at `0x18005bf98`
- `msvcrt!_wtoi` at `0x18005bfdf`
- `msvcrt!_wtoi` at `0x18005c026`
- `msvcrt!_wtoi` at `0x18005c06d`
- `msvcrt!_wtoi` at `0x18005c0b4`
- `msvcrt!_wtoi` at `0x18005c0fb`
- `msvcrt!_wtoi` at `0x18005c17b`
- `msvcrt!_wtoi` at `0x18005c1c2`
- `msvcrt!_wtoi` at `0x18005c209`
- `msvcrt!_wtoi` at `0x18005c250`
- `msvcrt!_wtoi` at `0x18005c297`
- `msvcrt!_wtoi` at `0x18005bf0a`
- `msvcrt!_wtoi` at `0x18005bf51`
- `msvcrt!_wtoi` at `0x18005bf98`
- `msvcrt!_wtoi` at `0x18005bfdf`
- `msvcrt!_wtoi` at `0x18005c026`
- `msvcrt!_wtoi` at `0x18005c06d`
- `msvcrt!_wtoi` at `0x18005c0b4`
- `msvcrt!_wtoi` at `0x18005c0fb`
- `msvcrt!_wtoi` at `0x18005c17b`
- `msvcrt!_wtoi` at `0x18005c1c2`
- `msvcrt!_wtoi` at `0x18005c209`
- `msvcrt!_wtoi` at `0x18005c250`
- `msvcrt!_wtoi` at `0x18005c297`

## string_xrefs

- `0x18005bf2d`: `AllowAppStoreAutoUpdate`
- `0x18005c090`: `BlockNonAdminUserInstall`
- `0x18005c157`: `MSIAllowUserControlOverInstall`
- `0x18005c19e`: `MSIAlwaysInstallWithElevatedPrivileges`
- `0x18005c2ba`: `ScheduleForceRestartForUpdateFailures`
- `0x18005be4c`: `./Vendor/MSFT/Policy/Config`
- `0x18005bc73`: `MDM_Policy_Config01_ApplicationManagement02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_ApplicationManagement02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  MI_Result v7; // r14d
  _QWORD *v8; // rsi
  unsigned int i; // r15d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+48h] [rbp-190h] BYREF
  _QWORD *v14; // [rsp+50h] [rbp-188h] BYREF
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
    v7 = (unsigned int)CreateRequestHandlerInstance(
                         self,
                         0,
                         0,
                         &MDM_Policy_Config01_ApplicationManagement02_NodeList,
                         17,
                         2,
                         &v14);
    if ( v7 == MI_RESULT_OK )
    {
      v16[1] = (const exception *)&v14;
      v17 = 1;
      v8 = v14;
      if ( v14 )
      {
        v7 = (*(unsigned int (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
        if ( v7 )
        {
          v6 = (wil *)v14;
          if ( v14 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
        }
        else
        {
          v7 = (*(unsigned int (__fastcall **)(_QWORD *))(*v8 + 8LL))(v8);
          if ( v7 )
          {
            v6 = (wil *)v14;
            if ( v14 )
              (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
          }
          else
          {
            for ( i = 0; i < (unsigned int)((__int64)(v8[33] - v8[32]) >> 4); ++i )
            {
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_ApplicationManagement02_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v14;
                if ( v14 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_91;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v8 + 24LL))(
                      v8,
                      i,
                      L"./Vendor/MSFT/Policy/Config",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v8 + 24LL))(
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
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowAllTrustedApps",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowAppStoreAutoUpdate",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowAutomaticAppArchiving",
                        &String)
                  && String )
                {
                  v27 = _wtoi(String);
                  v28 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowDeveloperUnlock",
                        &String)
                  && String )
                {
                  v29 = _wtoi(String);
                  v30 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowGameDVR",
                        &String)
                  && String )
                {
                  v31 = _wtoi(String);
                  v32 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowSharedUserAppData",
                        &String)
                  && String )
                {
                  v33 = _wtoi(String);
                  v34 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"BlockNonAdminUserInstall",
                        &String)
                  && String )
                {
                  v35 = _wtoi(String);
                  v36 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableStoreOriginatedApps",
                        &String)
                  && String )
                {
                  v37 = _wtoi(String);
                  v38 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"LaunchAppAfterLogOn",
                        &String)
                  && String )
                {
                  MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"MSIAllowUserControlOverInstall",
                        &String)
                  && String )
                {
                  v39 = _wtoi(String);
                  v40 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"MSIAlwaysInstallWithElevatedPrivileges",
                        &String)
                  && String )
                {
                  v41 = _wtoi(String);
                  v42 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"RequirePrivateStoreOnly",
                        &String)
                  && String )
                {
                  v43 = _wtoi(String);
                  v44 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"RestrictAppDataToSystemVolume",
                        &String)
                  && String )
                {
                  v45 = _wtoi(String);
                  v46 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"RestrictAppToSystemVolume",
                        &String)
                  && String )
                {
                  v47 = _wtoi(String);
                  v48 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
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
            v6 = (wil *)v14;
            if ( v14 )
            {
              (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
              v14 = 0;
            }
          }
        }
      }
      else
      {
        v7 = MI_RESULT_FAILED;
      }
    }
  }
  catch ( const exception *v16 )
  {
    v11 = (const char *)(*(__int64 (__fastcall **)(const exception *))(*(_QWORD *)v16[0] + 8LL))(v16[0]);
    TelemetryEventWriter::WriteStdException((TelemetryEventWriter *)v15, v11);
    LODWORD(v14) = 1;
    v7 = MI_RESULT_FAILED;
  }
  catch ( ... )
  {
    v12 = wil::ResultFromCaughtException(v6);
    TelemetryEventWriter::WriteDefaultExceptionHr((TelemetryEventWriter *)v15, v12);
    LODWORD(v14) = 1;
    v7 = MI_RESULT_FAILED;
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
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18005bbf8  mov     [rsp+arg_8], rbx
0x18005bbfd  mov     [rsp+arg_10], rsi
0x18005bc02  push    rdi
0x18005bc03  push    r12
0x18005bc05  push    r13
0x18005bc07  push    r14
0x18005bc09  push    r15
0x18005bc0b  sub     rsp, 1B0h
0x18005bc12  mov     rax, cs:__security_cookie
0x18005bc19  xor     rax, rsp
0x18005bc1c  mov     [rsp+1D8h+var_38], rax
0x18005bc24  mov     r13b, dl
0x18005bc27  mov     r12, rcx
0x18005bc2a  xor     edx, edx; Val
0x18005bc2c  mov     r8d, 0E8h; Size
0x18005bc32  lea     rcx, [rsp+1D8h+instance]; void *
0x18005bc3a  call    memset_0
0x18005bc3f  xor     edi, edi
0x18005bc41  mov     [rsp+1D8h+var_198], dil
0x18005bc46  mov     [rsp+1D8h+String], rdi
0x18005bc4b  mov     [rsp+1D8h+var_150], edi
0x18005bc52  mov     [rsp+1D8h+var_14C], dil
0x18005bc5a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18005bc61  mov     [rsp+1D8h+var_180], rax
0x18005bc66  lea     rax, [rsp+1D8h+var_150]
0x18005bc6e  mov     [rsp+1D8h+var_178], rax
0x18005bc73  lea     rax, aMdmPolicyConfi_160; "MDM_Policy_Config01_ApplicationManageme"...
0x18005bc7a  mov     [rsp+1D8h+var_170], rax
0x18005bc7f  lea     rcx, [rsp+1D8h+var_150]
0x18005bc87  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18005bc8c  mov     eax, cs:dword_180380B68
0x18005bc92  cmp     eax, 5
0x18005bc95  jbe     short loc_18005BD07
0x18005bc97  mov     rdx, 200000000000h
0x18005bca1  lea     rcx, dword_180380B68
0x18005bca8  call    _tlgKeywordOn
0x18005bcad  test    al, al
0x18005bcaf  jz      short loc_18005BD07
0x18005bcb1  cmp     [rsp+1D8h+var_14C], dil
0x18005bcb9  jz      short loc_18005BCE9
0x18005bcbb  cmp     [rsp+1D8h+var_138], edi
0x18005bcc2  jnz     short loc_18005BCDF
0x18005bcc4  cmp     [rsp+1D8h+var_134], edi
0x18005bccb  jnz     short loc_18005BCDF
0x18005bccd  cmp     [rsp+1D8h+var_130], edi
0x18005bcd4  jnz     short loc_18005BCDF
0x18005bcd6  cmp     [rsp+1D8h+var_12C], edi
0x18005bcdd  jz      short loc_18005BCE9
0x18005bcdf  lea     r9, [rsp+1D8h+var_138]
0x18005bce7  jmp     short loc_18005BCEC
0x18005bce9  mov     r9, rdi
0x18005bcec  lea     r8, [rsp+1D8h+var_148]
0x18005bcf4  lea     rdx, word_18035840A
0x18005bcfb  lea     rcx, dword_180380B68
0x18005bd02  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18005bd07  lea     rcx, [rsp+1D8h+var_180]; this
0x18005bd0c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18005bd11  nop
0x18005bd12  mov     [rsp+1D8h+var_188], rdi
0x18005bd17  lea     rax, [rsp+1D8h+var_188]
0x18005bd1c  mov     [rsp+1D8h+var_1A8], rax
0x18005bd21  mov     [rsp+1D8h+var_1B0], 2
0x18005bd29  mov     [rsp+1D8h+var_1B8], 11h
0x18005bd31  lea     r9, ?MDM_Policy_Config01_ApplicationManagement02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_ApplicationManagement02_NodeList
0x18005bd38  xor     r8d, r8d
0x18005bd3b  xor     edx, edx
0x18005bd3d  mov     rcx, r12
0x18005bd40  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18005bd45  mov     r14d, eax
0x18005bd48  test    eax, eax
0x18005bd4a  jz      short loc_18005BD51
0x18005bd4c  jmp     loc_18005C34D
0x18005bd51  lea     rbx, [rsp+1D8h+var_188]
0x18005bd56  mov     [rsp+1D8h+var_160], rbx
0x18005bd5b  mov     r15d, 1
0x18005bd61  mov     [rsp+1D8h+var_158], r15b
0x18005bd69  mov     rsi, [rsp+1D8h+var_188]
0x18005bd6e  test    rsi, rsi
0x18005bd71  jnz     short loc_18005BD7B
0x18005bd73  mov     r14d, r15d
0x18005bd76  jmp     loc_18005C34D
0x18005bd7b  mov     rax, [rsi]
0x18005bd7e  mov     rcx, rsi
0x18005bd81  mov     rax, [rax+10h]
0x18005bd85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd8a  mov     r14d, eax
0x18005bd8d  test    eax, eax
0x18005bd8f  jz      short loc_18005BDAF
0x18005bd91  mov     rcx, [rsp+1D8h+var_188]
0x18005bd96  test    rcx, rcx
0x18005bd99  jz      short loc_18005BDAA
0x18005bd9b  mov     rax, [rcx]
0x18005bd9e  mov     edx, r15d
0x18005bda1  mov     rax, [rax]
0x18005bda4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bda9  nop
0x18005bdaa  jmp     loc_18005C34D
0x18005bdaf  mov     rax, [rsi]
0x18005bdb2  mov     rcx, rsi
0x18005bdb5  mov     rax, [rax+8]
0x18005bdb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bdbe  mov     r14d, eax
0x18005bdc1  test    eax, eax
0x18005bdc3  jz      short loc_18005BDE3
0x18005bdc5  mov     rcx, [rsp+1D8h+var_188]
0x18005bdca  test    rcx, rcx
0x18005bdcd  jz      short loc_18005BDDE
0x18005bdcf  mov     rax, [rcx]
0x18005bdd2  mov     edx, r15d
0x18005bdd5  mov     rax, [rax]
0x18005bdd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bddd  nop
0x18005bdde  jmp     loc_18005C34D
0x18005bde3  mov     r15d, edi
0x18005bde6  mov     rax, [rsi+108h]
0x18005bded  sub     rax, [rsi+100h]
0x18005bdf4  sar     rax, 4
0x18005bdf8  cmp     r15d, eax
0x18005bdfb  jnb     loc_18005C315
0x18005be01  lea     r8, [rsp+1D8h+instance]; instance
0x18005be09  lea     rdx, MDM_Policy_Config01_ApplicationManagement02_rtti; classDecl
0x18005be10  mov     rcx, r12; context
0x18005be13  call    MI_Context_ConstructInstance
0x18005be18  mov     r14d, eax
0x18005be1b  test    eax, eax
0x18005be1d  jz      short loc_18005BE3F
0x18005be1f  mov     rcx, [rbx]
0x18005be22  test    rcx, rcx
0x18005be25  jz      short loc_18005BE3A
0x18005be27  mov     rax, [rcx]
0x18005be2a  mov     edx, 1
0x18005be2f  mov     rax, [rax]
0x18005be32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be37  mov     [rbx], rdi
0x18005be3a  jmp     loc_18005C34D
0x18005be3f  mov     [rsp+1D8h+var_198], 1
0x18005be44  mov     rax, [rsi]
0x18005be47  lea     r9, [rsp+1D8h+String]
0x18005be4c  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x18005be53  mov     edx, r15d
0x18005be56  mov     rcx, rsi
0x18005be59  mov     rax, [rax+18h]
0x18005be5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be62  test    eax, eax
0x18005be64  jnz     short loc_18005BE7D
0x18005be66  mov     rdx, [rsp+1D8h+String]
0x18005be6b  test    rdx, rdx
0x18005be6e  jz      short loc_18005BE7D
0x18005be70  lea     rcx, [rsp+1D8h+instance]
0x18005be78  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18005be7d  mov     rax, [rsi]
0x18005be80  lea     r9, [rsp+1D8h+String]
0x18005be85  lea     r8, aApplicationman; "ApplicationManagement"
0x18005be8c  mov     edx, r15d
0x18005be8f  mov     rcx, rsi
0x18005be92  mov     rax, [rax+18h]
0x18005be96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be9b  test    eax, eax
0x18005be9d  jnz     short loc_18005BEB6
0x18005be9f  mov     rdx, [rsp+1D8h+String]
0x18005bea4  test    rdx, rdx
0x18005bea7  jz      short loc_18005BEB6
0x18005bea9  lea     rcx, [rsp+1D8h+instance]
0x18005beb1  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18005beb6  cmp     r13b, 1
0x18005beba  jnz     short loc_18005BEDE
0x18005bebc  lea     rdx, [rsp+1D8h+instance]
0x18005bec4  mov     rcx, r12; self
0x18005bec7  call    MI_Instance_Destruct
0x18005becc  lea     rcx, [rsp+1D8h+instance]; self
0x18005bed4  call    MI_Instance_Destruct
0x18005bed9  jmp     loc_18005C308
0x18005bede  mov     rax, [rsi]
0x18005bee1  lea     r9, [rsp+1D8h+String]
0x18005bee6  lea     r8, aAllowalltruste; "AllowAllTrustedApps"
0x18005beed  mov     edx, r15d
0x18005bef0  mov     rcx, rsi
0x18005bef3  mov     rax, [rax+18h]
0x18005bef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005befc  test    eax, eax
0x18005befe  jnz     short loc_18005BF25
0x18005bf00  mov     rcx, [rsp+1D8h+String]; String
0x18005bf05  test    rcx, rcx
0x18005bf08  jz      short loc_18005BF25
0x18005bf0a  call    cs:__imp__wtoi
0x18005bf11  nop     dword ptr [rax+rax+00h]
0x18005bf16  mov     [rsp+1D8h+var_C8], eax
0x18005bf1d  mov     [rsp+1D8h+var_C4], 1
0x18005bf25  mov     rax, [rsi]
0x18005bf28  lea     r9, [rsp+1D8h+String]
0x18005bf2d  lea     r8, aAllowappstorea; "AllowAppStoreAutoUpdate"
0x18005bf34  mov     edx, r15d
0x18005bf37  mov     rcx, rsi
0x18005bf3a  mov     rax, [rax+18h]
0x18005bf3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf43  test    eax, eax
0x18005bf45  jnz     short loc_18005BF6C
0x18005bf47  mov     rcx, [rsp+1D8h+String]; String
0x18005bf4c  test    rcx, rcx
0x18005bf4f  jz      short loc_18005BF6C
0x18005bf51  call    cs:__imp__wtoi
0x18005bf58  nop     dword ptr [rax+rax+00h]
0x18005bf5d  mov     [rsp+1D8h+var_C0], eax
0x18005bf64  mov     [rsp+1D8h+var_BC], 1
0x18005bf6c  mov     rax, [rsi]
0x18005bf6f  lea     r9, [rsp+1D8h+String]
0x18005bf74  lea     r8, aAllowautomatic_0; "AllowAutomaticAppArchiving"
0x18005bf7b  mov     edx, r15d
0x18005bf7e  mov     rcx, rsi
0x18005bf81  mov     rax, [rax+18h]
0x18005bf85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf8a  test    eax, eax
0x18005bf8c  jnz     short loc_18005BFB3
0x18005bf8e  mov     rcx, [rsp+1D8h+String]; String
0x18005bf93  test    rcx, rcx
0x18005bf96  jz      short loc_18005BFB3
0x18005bf98  call    cs:__imp__wtoi
0x18005bf9f  nop     dword ptr [rax+rax+00h]
0x18005bfa4  mov     [rsp+1D8h+var_B8], eax
0x18005bfab  mov     [rsp+1D8h+var_B4], 1
0x18005bfb3  mov     rax, [rsi]
0x18005bfb6  lea     r9, [rsp+1D8h+String]
0x18005bfbb  lea     r8, aAllowdeveloper_0; "AllowDeveloperUnlock"
0x18005bfc2  mov     edx, r15d
0x18005bfc5  mov     rcx, rsi
0x18005bfc8  mov     rax, [rax+18h]
0x18005bfcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bfd1  test    eax, eax
0x18005bfd3  jnz     short loc_18005BFFA
0x18005bfd5  mov     rcx, [rsp+1D8h+String]; String
0x18005bfda  test    rcx, rcx
0x18005bfdd  jz      short loc_18005BFFA
0x18005bfdf  call    cs:__imp__wtoi
0x18005bfe6  nop     dword ptr [rax+rax+00h]
0x18005bfeb  mov     [rsp+1D8h+var_B0], eax
0x18005bff2  mov     [rsp+1D8h+var_AC], 1
0x18005bffa  mov     rax, [rsi]
0x18005bffd  lea     r9, [rsp+1D8h+String]
0x18005c002  lea     r8, aAllowgamedvr; "AllowGameDVR"
0x18005c009  mov     edx, r15d
0x18005c00c  mov     rcx, rsi
0x18005c00f  mov     rax, [rax+18h]
0x18005c013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c018  test    eax, eax
0x18005c01a  jnz     short loc_18005C041
0x18005c01c  mov     rcx, [rsp+1D8h+String]; String
0x18005c021  test    rcx, rcx
0x18005c024  jz      short loc_18005C041
0x18005c026  call    cs:__imp__wtoi
0x18005c02d  nop     dword ptr [rax+rax+00h]
0x18005c032  mov     [rsp+1D8h+var_A8], eax
0x18005c039  mov     [rsp+1D8h+var_A4], 1
0x18005c041  mov     rax, [rsi]
0x18005c044  lea     r9, [rsp+1D8h+String]
0x18005c049  lea     r8, aAllowshareduse; "AllowSharedUserAppData"
0x18005c050  mov     edx, r15d
0x18005c053  mov     rcx, rsi
0x18005c056  mov     rax, [rax+18h]
0x18005c05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c05f  test    eax, eax
0x18005c061  jnz     short loc_18005C088
0x18005c063  mov     rcx, [rsp+1D8h+String]; String
0x18005c068  test    rcx, rcx
0x18005c06b  jz      short loc_18005C088
0x18005c06d  call    cs:__imp__wtoi
0x18005c074  nop     dword ptr [rax+rax+00h]
0x18005c079  mov     [rsp+1D8h+var_A0], eax
0x18005c080  mov     [rsp+1D8h+var_9C], 1
0x18005c088  mov     rax, [rsi]
0x18005c08b  lea     r9, [rsp+1D8h+String]
0x18005c090  lea     r8, aBlocknonadminu; "BlockNonAdminUserInstall"
0x18005c097  mov     edx, r15d
0x18005c09a  mov     rcx, rsi
0x18005c09d  mov     rax, [rax+18h]
0x18005c0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c0a6  test    eax, eax
0x18005c0a8  jnz     short loc_18005C0CF
0x18005c0aa  mov     rcx, [rsp+1D8h+String]; String
0x18005c0af  test    rcx, rcx
0x18005c0b2  jz      short loc_18005C0CF
0x18005c0b4  call    cs:__imp__wtoi
0x18005c0bb  nop     dword ptr [rax+rax+00h]
0x18005c0c0  mov     [rsp+1D8h+var_98], eax
0x18005c0c7  mov     [rsp+1D8h+var_94], 1
0x18005c0cf  mov     rax, [rsi]
0x18005c0d2  lea     r9, [rsp+1D8h+String]
0x18005c0d7  lea     r8, aDisablestoreor; "DisableStoreOriginatedApps"
0x18005c0de  mov     edx, r15d
0x18005c0e1  mov     rcx, rsi
0x18005c0e4  mov     rax, [rax+18h]
0x18005c0e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c0ed  test    eax, eax
0x18005c0ef  jnz     short loc_18005C116
0x18005c0f1  mov     rcx, [rsp+1D8h+String]; String
0x18005c0f6  test    rcx, rcx
0x18005c0f9  jz      short loc_18005C116
0x18005c0fb  call    cs:__imp__wtoi
0x18005c102  nop     dword ptr [rax+rax+00h]
0x18005c107  mov     [rsp+1D8h+var_90], eax
0x18005c10e  mov     [rsp+1D8h+var_8C], 1
  ... truncated ...
```
