# MDM_Policy_Result01_ApplicationManagement02_InvokeEnumerateInstances

- ea: `0x180113608`
- end: `0x180113dfe`
- name: `MDM_Policy_Result01_ApplicationManagement02_InvokeEnumerateInstances`
- size: `2038`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x180112be0`

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
- `0x180113608`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18011391a`
- `msvcrt!_wtoi` at `0x180113961`
- `msvcrt!_wtoi` at `0x1801139a8`
- `msvcrt!_wtoi` at `0x1801139ef`
- `msvcrt!_wtoi` at `0x180113a36`
- `msvcrt!_wtoi` at `0x180113a7d`
- `msvcrt!_wtoi` at `0x180113ac4`
- `msvcrt!_wtoi` at `0x180113b0b`
- `msvcrt!_wtoi` at `0x180113b8b`
- `msvcrt!_wtoi` at `0x180113bd2`
- `msvcrt!_wtoi` at `0x180113c19`
- `msvcrt!_wtoi` at `0x180113c60`
- `msvcrt!_wtoi` at `0x180113ca7`
- `msvcrt!_wtoi` at `0x18011391a`
- `msvcrt!_wtoi` at `0x180113961`
- `msvcrt!_wtoi` at `0x1801139a8`
- `msvcrt!_wtoi` at `0x1801139ef`
- `msvcrt!_wtoi` at `0x180113a36`
- `msvcrt!_wtoi` at `0x180113a7d`
- `msvcrt!_wtoi` at `0x180113ac4`
- `msvcrt!_wtoi` at `0x180113b0b`
- `msvcrt!_wtoi` at `0x180113b8b`
- `msvcrt!_wtoi` at `0x180113bd2`
- `msvcrt!_wtoi` at `0x180113c19`
- `msvcrt!_wtoi` at `0x180113c60`
- `msvcrt!_wtoi` at `0x180113ca7`

## string_xrefs

- `0x18011393d`: `AllowAppStoreAutoUpdate`
- `0x180113aa0`: `BlockNonAdminUserInstall`
- `0x180113b67`: `MSIAllowUserControlOverInstall`
- `0x180113bae`: `MSIAlwaysInstallWithElevatedPrivileges`
- `0x180113cca`: `ScheduleForceRestartForUpdateFailures`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_ApplicationManagement02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  MI_Result v6; // r14d
  _QWORD *v7; // rsi
  unsigned int i; // r15d
  wchar_t *String; // [rsp+48h] [rbp-190h] BYREF
  _QWORD *v11; // [rsp+50h] [rbp-188h] BYREF
  _QWORD v12[5]; // [rsp+58h] [rbp-180h] BYREF
  char v13; // [rsp+80h] [rbp-158h]
  int v14; // [rsp+88h] [rbp-150h] BYREF
  char v15; // [rsp+8Ch] [rbp-14Ch]
  _BYTE v16[16]; // [rsp+90h] [rbp-148h] BYREF
  _DWORD v17[4]; // [rsp+A0h] [rbp-138h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-128h] BYREF
  int v19; // [rsp+110h] [rbp-C8h]
  char v20; // [rsp+114h] [rbp-C4h]
  int v21; // [rsp+118h] [rbp-C0h]
  char v22; // [rsp+11Ch] [rbp-BCh]
  int v23; // [rsp+120h] [rbp-B8h]
  char v24; // [rsp+124h] [rbp-B4h]
  int v25; // [rsp+128h] [rbp-B0h]
  char v26; // [rsp+12Ch] [rbp-ACh]
  int v27; // [rsp+130h] [rbp-A8h]
  char v28; // [rsp+134h] [rbp-A4h]
  int v29; // [rsp+138h] [rbp-A0h]
  char v30; // [rsp+13Ch] [rbp-9Ch]
  int v31; // [rsp+140h] [rbp-98h]
  char v32; // [rsp+144h] [rbp-94h]
  int v33; // [rsp+148h] [rbp-90h]
  char v34; // [rsp+14Ch] [rbp-8Ch]
  int v35; // [rsp+160h] [rbp-78h]
  char v36; // [rsp+164h] [rbp-74h]
  int v37; // [rsp+168h] [rbp-70h]
  char v38; // [rsp+16Ch] [rbp-6Ch]
  int v39; // [rsp+170h] [rbp-68h]
  char v40; // [rsp+174h] [rbp-64h]
  int v41; // [rsp+178h] [rbp-60h]
  char v42; // [rsp+17Ch] [rbp-5Ch]
  int v43; // [rsp+180h] [rbp-58h]
  char v44; // [rsp+184h] [rbp-54h]

  memset_0(&instance, 0, 0xE8u);
  String = 0;
  v14 = 0;
  v15 = 0;
  v12[0] = &TelemetryEventWriter::`vftable';
  v12[1] = &v14;
  v12[2] = "MDM_Policy_Result01_ApplicationManagement02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v14);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v15 && (v17[0] || v17[1] || v17[2] || v17[3]) )
      v5 = v17;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_180360C5C,
      v16,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v12, v4);
  v11 = 0;
  v6 = (unsigned int)CreateRequestHandlerInstance(
                       self,
                       0,
                       0,
                       &MDM_Policy_Result01_ApplicationManagement02_NodeList,
                       17,
                       2,
                       &v11);
  if ( v6 == MI_RESULT_OK )
  {
    v12[4] = &v11;
    v13 = 1;
    v7 = v11;
    if ( v11 )
    {
      v6 = (*(unsigned int (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
      if ( v6 )
      {
        if ( v11 )
          (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
      }
      else
      {
        v6 = (*(unsigned int (__fastcall **)(_QWORD *))(*v7 + 8LL))(v7);
        if ( v6 )
        {
          if ( v11 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
        }
        else
        {
          for ( i = 0; i < (unsigned int)((__int64)(v7[33] - v7[32]) >> 4); ++i )
          {
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_ApplicationManagement02_rtti, &instance);
            if ( v6 )
            {
              if ( v11 )
              {
                (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
                v11 = 0;
              }
              goto LABEL_83;
            }
            if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v7 + 24LL))(
                    v7,
                    i,
                    L"./Vendor/MSFT/Policy/Result",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
            }
            if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v7 + 24LL))(
                    v7,
                    i,
                    L"ApplicationManagement",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, String);
            }
            if ( a2 != 1 )
            {
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowAllTrustedApps",
                      &String)
                && String )
              {
                v19 = _wtoi(String);
                v20 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowAppStoreAutoUpdate",
                      &String)
                && String )
              {
                v21 = _wtoi(String);
                v22 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowAutomaticAppArchiving",
                      &String)
                && String )
              {
                v23 = _wtoi(String);
                v24 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowDeveloperUnlock",
                      &String)
                && String )
              {
                v25 = _wtoi(String);
                v26 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowGameDVR",
                      &String)
                && String )
              {
                v27 = _wtoi(String);
                v28 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowSharedUserAppData",
                      &String)
                && String )
              {
                v29 = _wtoi(String);
                v30 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"BlockNonAdminUserInstall",
                      &String)
                && String )
              {
                v31 = _wtoi(String);
                v32 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"DisableStoreOriginatedApps",
                      &String)
                && String )
              {
                v33 = _wtoi(String);
                v34 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"LaunchAppAfterLogOn",
                      &String)
                && String )
              {
                MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"MSIAllowUserControlOverInstall",
                      &String)
                && String )
              {
                v35 = _wtoi(String);
                v36 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"MSIAlwaysInstallWithElevatedPrivileges",
                      &String)
                && String )
              {
                v37 = _wtoi(String);
                v38 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"RequirePrivateStoreOnly",
                      &String)
                && String )
              {
                v39 = _wtoi(String);
                v40 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"RestrictAppDataToSystemVolume",
                      &String)
                && String )
              {
                v41 = _wtoi(String);
                v42 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"RestrictAppToSystemVolume",
                      &String)
                && String )
              {
                v43 = _wtoi(String);
                v44 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
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
          if ( v11 )
          {
            (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
            v11 = 0;
          }
        }
      }
    }
    else
    {
      v6 = MI_RESULT_FAILED;
    }
  }
LABEL_83:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v12, "EnumerateInstancesEnd", v6);
  v14 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180339EA3,
      v16,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v14);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180113608  mov     [rsp+arg_8], rbx
0x18011360d  mov     [rsp+arg_10], rsi
0x180113612  push    rdi
0x180113613  push    r12
0x180113615  push    r13
0x180113617  push    r14
0x180113619  push    r15
0x18011361b  sub     rsp, 1B0h
0x180113622  mov     rax, cs:__security_cookie
0x180113629  xor     rax, rsp
0x18011362c  mov     [rsp+1D8h+var_38], rax
0x180113634  mov     r13b, dl
0x180113637  mov     r12, rcx
0x18011363a  xor     edx, edx; Val
0x18011363c  mov     r8d, 0E8h; Size
0x180113642  lea     rcx, [rsp+1D8h+instance]; void *
0x18011364a  call    memset_0
0x18011364f  xor     edi, edi
0x180113651  mov     [rsp+1D8h+var_198], dil
0x180113656  mov     [rsp+1D8h+String], rdi
0x18011365b  mov     [rsp+1D8h+var_150], edi
0x180113662  mov     [rsp+1D8h+var_14C], dil
0x18011366a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180113671  mov     [rsp+1D8h+var_180], rax
0x180113676  lea     rax, [rsp+1D8h+var_150]
0x18011367e  mov     [rsp+1D8h+var_178], rax
0x180113683  lea     rax, aMdmPolicyResul_187; "MDM_Policy_Result01_ApplicationManageme"...
0x18011368a  mov     [rsp+1D8h+var_170], rax
0x18011368f  lea     rcx, [rsp+1D8h+var_150]
0x180113697  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18011369c  mov     eax, cs:dword_180380B68
0x1801136a2  cmp     eax, 5
0x1801136a5  jbe     short loc_180113717
0x1801136a7  mov     rdx, 200000000000h
0x1801136b1  lea     rcx, dword_180380B68
0x1801136b8  call    _tlgKeywordOn
0x1801136bd  test    al, al
0x1801136bf  jz      short loc_180113717
0x1801136c1  cmp     [rsp+1D8h+var_14C], dil
0x1801136c9  jz      short loc_1801136F9
0x1801136cb  cmp     [rsp+1D8h+var_138], edi
0x1801136d2  jnz     short loc_1801136EF
0x1801136d4  cmp     [rsp+1D8h+var_134], edi
0x1801136db  jnz     short loc_1801136EF
0x1801136dd  cmp     [rsp+1D8h+var_130], edi
0x1801136e4  jnz     short loc_1801136EF
0x1801136e6  cmp     [rsp+1D8h+var_12C], edi
0x1801136ed  jz      short loc_1801136F9
0x1801136ef  lea     r9, [rsp+1D8h+var_138]
0x1801136f7  jmp     short loc_1801136FC
0x1801136f9  mov     r9, rdi
0x1801136fc  lea     r8, [rsp+1D8h+var_148]
0x180113704  lea     rdx, dword_180360C5C
0x18011370b  lea     rcx, dword_180380B68
0x180113712  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180113717  lea     rcx, [rsp+1D8h+var_180]; this
0x18011371c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x180113721  nop
0x180113722  mov     [rsp+1D8h+var_188], rdi
0x180113727  lea     rax, [rsp+1D8h+var_188]
0x18011372c  mov     [rsp+1D8h+var_1A8], rax
0x180113731  mov     [rsp+1D8h+var_1B0], 2
0x180113739  mov     [rsp+1D8h+var_1B8], 11h
0x180113741  lea     r9, ?MDM_Policy_Result01_ApplicationManagement02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_ApplicationManagement02_NodeList
0x180113748  xor     r8d, r8d
0x18011374b  xor     edx, edx
0x18011374d  mov     rcx, r12
0x180113750  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180113755  mov     r14d, eax
0x180113758  test    eax, eax
0x18011375a  jz      short loc_180113761
0x18011375c  jmp     loc_180113D5D
0x180113761  lea     rbx, [rsp+1D8h+var_188]
0x180113766  mov     [rsp+1D8h+var_160], rbx
0x18011376b  mov     r15d, 1
0x180113771  mov     [rsp+1D8h+var_158], r15b
0x180113779  mov     rsi, [rsp+1D8h+var_188]
0x18011377e  test    rsi, rsi
0x180113781  jnz     short loc_18011378B
0x180113783  mov     r14d, r15d
0x180113786  jmp     loc_180113D5D
0x18011378b  mov     rax, [rsi]
0x18011378e  mov     rcx, rsi
0x180113791  mov     rax, [rax+10h]
0x180113795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011379a  mov     r14d, eax
0x18011379d  test    eax, eax
0x18011379f  jz      short loc_1801137BF
0x1801137a1  mov     rcx, [rsp+1D8h+var_188]
0x1801137a6  test    rcx, rcx
0x1801137a9  jz      short loc_1801137BA
0x1801137ab  mov     rax, [rcx]
0x1801137ae  mov     edx, r15d
0x1801137b1  mov     rax, [rax]
0x1801137b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801137b9  nop
0x1801137ba  jmp     loc_180113D5D
0x1801137bf  mov     rax, [rsi]
0x1801137c2  mov     rcx, rsi
0x1801137c5  mov     rax, [rax+8]
0x1801137c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801137ce  mov     r14d, eax
0x1801137d1  test    eax, eax
0x1801137d3  jz      short loc_1801137F3
0x1801137d5  mov     rcx, [rsp+1D8h+var_188]
0x1801137da  test    rcx, rcx
0x1801137dd  jz      short loc_1801137EE
0x1801137df  mov     rax, [rcx]
0x1801137e2  mov     edx, r15d
0x1801137e5  mov     rax, [rax]
0x1801137e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801137ed  nop
0x1801137ee  jmp     loc_180113D5D
0x1801137f3  mov     r15d, edi
0x1801137f6  mov     rax, [rsi+108h]
0x1801137fd  sub     rax, [rsi+100h]
0x180113804  sar     rax, 4
0x180113808  cmp     r15d, eax
0x18011380b  jnb     loc_180113D25
0x180113811  lea     r8, [rsp+1D8h+instance]; instance
0x180113819  lea     rdx, MDM_Policy_Result01_ApplicationManagement02_rtti; classDecl
0x180113820  mov     rcx, r12; context
0x180113823  call    MI_Context_ConstructInstance
0x180113828  mov     r14d, eax
0x18011382b  test    eax, eax
0x18011382d  jz      short loc_18011384F
0x18011382f  mov     rcx, [rbx]
0x180113832  test    rcx, rcx
0x180113835  jz      short loc_18011384A
0x180113837  mov     rax, [rcx]
0x18011383a  mov     edx, 1
0x18011383f  mov     rax, [rax]
0x180113842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113847  mov     [rbx], rdi
0x18011384a  jmp     loc_180113D5D
0x18011384f  mov     [rsp+1D8h+var_198], 1
0x180113854  mov     rax, [rsi]
0x180113857  lea     r9, [rsp+1D8h+String]
0x18011385c  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x180113863  mov     edx, r15d
0x180113866  mov     rcx, rsi
0x180113869  mov     rax, [rax+18h]
0x18011386d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113872  test    eax, eax
0x180113874  jnz     short loc_18011388D
0x180113876  mov     rdx, [rsp+1D8h+String]
0x18011387b  test    rdx, rdx
0x18011387e  jz      short loc_18011388D
0x180113880  lea     rcx, [rsp+1D8h+instance]
0x180113888  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18011388d  mov     rax, [rsi]
0x180113890  lea     r9, [rsp+1D8h+String]
0x180113895  lea     r8, aApplicationman; "ApplicationManagement"
0x18011389c  mov     edx, r15d
0x18011389f  mov     rcx, rsi
0x1801138a2  mov     rax, [rax+18h]
0x1801138a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801138ab  test    eax, eax
0x1801138ad  jnz     short loc_1801138C6
0x1801138af  mov     rdx, [rsp+1D8h+String]
0x1801138b4  test    rdx, rdx
0x1801138b7  jz      short loc_1801138C6
0x1801138b9  lea     rcx, [rsp+1D8h+instance]
0x1801138c1  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801138c6  cmp     r13b, 1
0x1801138ca  jnz     short loc_1801138EE
0x1801138cc  lea     rdx, [rsp+1D8h+instance]
0x1801138d4  mov     rcx, r12; self
0x1801138d7  call    MI_Instance_Destruct
0x1801138dc  lea     rcx, [rsp+1D8h+instance]; self
0x1801138e4  call    MI_Instance_Destruct
0x1801138e9  jmp     loc_180113D18
0x1801138ee  mov     rax, [rsi]
0x1801138f1  lea     r9, [rsp+1D8h+String]
0x1801138f6  lea     r8, aAllowalltruste; "AllowAllTrustedApps"
0x1801138fd  mov     edx, r15d
0x180113900  mov     rcx, rsi
0x180113903  mov     rax, [rax+18h]
0x180113907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011390c  test    eax, eax
0x18011390e  jnz     short loc_180113935
0x180113910  mov     rcx, [rsp+1D8h+String]; String
0x180113915  test    rcx, rcx
0x180113918  jz      short loc_180113935
0x18011391a  call    cs:__imp__wtoi
0x180113921  nop     dword ptr [rax+rax+00h]
0x180113926  mov     [rsp+1D8h+var_C8], eax
0x18011392d  mov     [rsp+1D8h+var_C4], 1
0x180113935  mov     rax, [rsi]
0x180113938  lea     r9, [rsp+1D8h+String]
0x18011393d  lea     r8, aAllowappstorea; "AllowAppStoreAutoUpdate"
0x180113944  mov     edx, r15d
0x180113947  mov     rcx, rsi
0x18011394a  mov     rax, [rax+18h]
0x18011394e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113953  test    eax, eax
0x180113955  jnz     short loc_18011397C
0x180113957  mov     rcx, [rsp+1D8h+String]; String
0x18011395c  test    rcx, rcx
0x18011395f  jz      short loc_18011397C
0x180113961  call    cs:__imp__wtoi
0x180113968  nop     dword ptr [rax+rax+00h]
0x18011396d  mov     [rsp+1D8h+var_C0], eax
0x180113974  mov     [rsp+1D8h+var_BC], 1
0x18011397c  mov     rax, [rsi]
0x18011397f  lea     r9, [rsp+1D8h+String]
0x180113984  lea     r8, aAllowautomatic_0; "AllowAutomaticAppArchiving"
0x18011398b  mov     edx, r15d
0x18011398e  mov     rcx, rsi
0x180113991  mov     rax, [rax+18h]
0x180113995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011399a  test    eax, eax
0x18011399c  jnz     short loc_1801139C3
0x18011399e  mov     rcx, [rsp+1D8h+String]; String
0x1801139a3  test    rcx, rcx
0x1801139a6  jz      short loc_1801139C3
0x1801139a8  call    cs:__imp__wtoi
0x1801139af  nop     dword ptr [rax+rax+00h]
0x1801139b4  mov     [rsp+1D8h+var_B8], eax
0x1801139bb  mov     [rsp+1D8h+var_B4], 1
0x1801139c3  mov     rax, [rsi]
0x1801139c6  lea     r9, [rsp+1D8h+String]
0x1801139cb  lea     r8, aAllowdeveloper_0; "AllowDeveloperUnlock"
0x1801139d2  mov     edx, r15d
0x1801139d5  mov     rcx, rsi
0x1801139d8  mov     rax, [rax+18h]
0x1801139dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801139e1  test    eax, eax
0x1801139e3  jnz     short loc_180113A0A
0x1801139e5  mov     rcx, [rsp+1D8h+String]; String
0x1801139ea  test    rcx, rcx
0x1801139ed  jz      short loc_180113A0A
0x1801139ef  call    cs:__imp__wtoi
0x1801139f6  nop     dword ptr [rax+rax+00h]
0x1801139fb  mov     [rsp+1D8h+var_B0], eax
0x180113a02  mov     [rsp+1D8h+var_AC], 1
0x180113a0a  mov     rax, [rsi]
0x180113a0d  lea     r9, [rsp+1D8h+String]
0x180113a12  lea     r8, aAllowgamedvr; "AllowGameDVR"
0x180113a19  mov     edx, r15d
0x180113a1c  mov     rcx, rsi
0x180113a1f  mov     rax, [rax+18h]
0x180113a23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113a28  test    eax, eax
0x180113a2a  jnz     short loc_180113A51
0x180113a2c  mov     rcx, [rsp+1D8h+String]; String
0x180113a31  test    rcx, rcx
0x180113a34  jz      short loc_180113A51
0x180113a36  call    cs:__imp__wtoi
0x180113a3d  nop     dword ptr [rax+rax+00h]
0x180113a42  mov     [rsp+1D8h+var_A8], eax
0x180113a49  mov     [rsp+1D8h+var_A4], 1
0x180113a51  mov     rax, [rsi]
0x180113a54  lea     r9, [rsp+1D8h+String]
0x180113a59  lea     r8, aAllowshareduse; "AllowSharedUserAppData"
0x180113a60  mov     edx, r15d
0x180113a63  mov     rcx, rsi
0x180113a66  mov     rax, [rax+18h]
0x180113a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113a6f  test    eax, eax
0x180113a71  jnz     short loc_180113A98
0x180113a73  mov     rcx, [rsp+1D8h+String]; String
0x180113a78  test    rcx, rcx
0x180113a7b  jz      short loc_180113A98
0x180113a7d  call    cs:__imp__wtoi
0x180113a84  nop     dword ptr [rax+rax+00h]
0x180113a89  mov     [rsp+1D8h+var_A0], eax
0x180113a90  mov     [rsp+1D8h+var_9C], 1
0x180113a98  mov     rax, [rsi]
0x180113a9b  lea     r9, [rsp+1D8h+String]
0x180113aa0  lea     r8, aBlocknonadminu; "BlockNonAdminUserInstall"
0x180113aa7  mov     edx, r15d
0x180113aaa  mov     rcx, rsi
0x180113aad  mov     rax, [rax+18h]
0x180113ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113ab6  test    eax, eax
0x180113ab8  jnz     short loc_180113ADF
0x180113aba  mov     rcx, [rsp+1D8h+String]; String
0x180113abf  test    rcx, rcx
0x180113ac2  jz      short loc_180113ADF
0x180113ac4  call    cs:__imp__wtoi
0x180113acb  nop     dword ptr [rax+rax+00h]
0x180113ad0  mov     [rsp+1D8h+var_98], eax
0x180113ad7  mov     [rsp+1D8h+var_94], 1
0x180113adf  mov     rax, [rsi]
0x180113ae2  lea     r9, [rsp+1D8h+String]
0x180113ae7  lea     r8, aDisablestoreor; "DisableStoreOriginatedApps"
0x180113aee  mov     edx, r15d
0x180113af1  mov     rcx, rsi
0x180113af4  mov     rax, [rax+18h]
0x180113af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113afd  test    eax, eax
0x180113aff  jnz     short loc_180113B26
0x180113b01  mov     rcx, [rsp+1D8h+String]; String
0x180113b06  test    rcx, rcx
0x180113b09  jz      short loc_180113B26
0x180113b0b  call    cs:__imp__wtoi
0x180113b12  nop     dword ptr [rax+rax+00h]
0x180113b17  mov     [rsp+1D8h+var_90], eax
0x180113b1e  mov     [rsp+1D8h+var_8C], 1
  ... truncated ...
```
