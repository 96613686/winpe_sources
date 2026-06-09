# MDM_Policy_Result01_ApplicationManagement02_InvokeEnumerateInstances

- ea: `0x180113cf4`
- end: `0x18011449b`
- name: `MDM_Policy_Result01_ApplicationManagement02_InvokeEnumerateInstances`
- size: `1959`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x1801132b0`

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
- `0x180113cf4`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180114006`
- `msvcrt!_wtoi` at `0x180114047`
- `msvcrt!_wtoi` at `0x180114088`
- `msvcrt!_wtoi` at `0x1801140c9`
- `msvcrt!_wtoi` at `0x18011410a`
- `msvcrt!_wtoi` at `0x18011414b`
- `msvcrt!_wtoi` at `0x18011418c`
- `msvcrt!_wtoi` at `0x1801141cd`
- `msvcrt!_wtoi` at `0x180114247`
- `msvcrt!_wtoi` at `0x180114288`
- `msvcrt!_wtoi` at `0x1801142c9`
- `msvcrt!_wtoi` at `0x18011430a`
- `msvcrt!_wtoi` at `0x18011434b`
- `msvcrt!_wtoi` at `0x180114006`
- `msvcrt!_wtoi` at `0x180114047`
- `msvcrt!_wtoi` at `0x180114088`
- `msvcrt!_wtoi` at `0x1801140c9`
- `msvcrt!_wtoi` at `0x18011410a`
- `msvcrt!_wtoi` at `0x18011414b`
- `msvcrt!_wtoi` at `0x18011418c`
- `msvcrt!_wtoi` at `0x1801141cd`
- `msvcrt!_wtoi` at `0x180114247`
- `msvcrt!_wtoi` at `0x180114288`
- `msvcrt!_wtoi` at `0x1801142c9`
- `msvcrt!_wtoi` at `0x18011430a`
- `msvcrt!_wtoi` at `0x18011434b`

## string_xrefs

- `0x180114023`: `AllowAppStoreAutoUpdate`
- `0x180114168`: `BlockNonAdminUserInstall`
- `0x180114223`: `MSIAllowUserControlOverInstall`
- `0x180114264`: `MSIAlwaysInstallWithElevatedPrivileges`
- `0x180114368`: `ScheduleForceRestartForUpdateFailures`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_ApplicationManagement02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  unsigned int v6; // r14d
  WmiRequestHandlerAdd *v7; // rsi
  unsigned int i; // r15d
  wchar_t *String; // [rsp+48h] [rbp-190h] BYREF
  WmiRequestHandlerAdd *v11; // [rsp+50h] [rbp-188h] BYREF
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
  v6 = CreateRequestHandlerInstance(
         (__int64)self,
         0,
         0,
         (struct WmiNodeInfo *)&MDM_Policy_Result01_ApplicationManagement02_NodeList,
         0x11u,
         2,
         &v11);
  if ( !v6 )
  {
    v12[4] = &v11;
    v13 = 1;
    v7 = v11;
    if ( v11 )
    {
      v6 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v11 + 16LL))(v11);
      if ( v6 )
      {
        if ( v11 )
          (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v11)(v11, 1);
      }
      else
      {
        v6 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v7 + 8LL))(v7);
        if ( v6 )
        {
          if ( v11 )
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v11)(v11, 1);
        }
        else
        {
          for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)v7 + 33) - *((_QWORD *)v7 + 32)) >> 4); ++i )
          {
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_ApplicationManagement02_rtti, &instance);
            if ( v6 )
            {
              if ( v11 )
              {
                (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v11)(v11, 1);
                v11 = 0;
              }
              goto LABEL_83;
            }
            if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                    v7,
                    i,
                    L"./Vendor/MSFT/Policy/Result",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
            }
            if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
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
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowAllTrustedApps",
                      &String)
                && String )
              {
                v19 = _wtoi(String);
                v20 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowAppStoreAutoUpdate",
                      &String)
                && String )
              {
                v21 = _wtoi(String);
                v22 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowAutomaticAppArchiving",
                      &String)
                && String )
              {
                v23 = _wtoi(String);
                v24 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowDeveloperUnlock",
                      &String)
                && String )
              {
                v25 = _wtoi(String);
                v26 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowGameDVR",
                      &String)
                && String )
              {
                v27 = _wtoi(String);
                v28 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowSharedUserAppData",
                      &String)
                && String )
              {
                v29 = _wtoi(String);
                v30 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"BlockNonAdminUserInstall",
                      &String)
                && String )
              {
                v31 = _wtoi(String);
                v32 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"DisableStoreOriginatedApps",
                      &String)
                && String )
              {
                v33 = _wtoi(String);
                v34 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"LaunchAppAfterLogOn",
                      &String)
                && String )
              {
                MDM_VPNv2_01_Set_TrustedNetworkDetection(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"MSIAllowUserControlOverInstall",
                      &String)
                && String )
              {
                v35 = _wtoi(String);
                v36 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"MSIAlwaysInstallWithElevatedPrivileges",
                      &String)
                && String )
              {
                v37 = _wtoi(String);
                v38 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"RequirePrivateStoreOnly",
                      &String)
                && String )
              {
                v39 = _wtoi(String);
                v40 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"RestrictAppDataToSystemVolume",
                      &String)
                && String )
              {
                v41 = _wtoi(String);
                v42 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"RestrictAppToSystemVolume",
                      &String)
                && String )
              {
                v43 = _wtoi(String);
                v44 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
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
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v11)(v11, 1);
            v11 = 0;
          }
        }
      }
    }
    else
    {
      v6 = 1;
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
  return v6;
}

```

## disassembly

```asm
0x180113cf4  mov     [rsp+arg_8], rbx
0x180113cf9  mov     [rsp+arg_10], rsi
0x180113cfe  push    rdi
0x180113cff  push    r12
0x180113d01  push    r13
0x180113d03  push    r14
0x180113d05  push    r15
0x180113d07  sub     rsp, 1B0h
0x180113d0e  mov     rax, cs:__security_cookie
0x180113d15  xor     rax, rsp
0x180113d18  mov     [rsp+1D8h+var_38], rax
0x180113d20  mov     r13b, dl
0x180113d23  mov     r12, rcx
0x180113d26  xor     edx, edx; Val
0x180113d28  mov     r8d, 0E8h; Size
0x180113d2e  lea     rcx, [rsp+1D8h+instance]; void *
0x180113d36  call    memset_0
0x180113d3b  xor     edi, edi
0x180113d3d  mov     [rsp+1D8h+var_198], dil
0x180113d42  mov     [rsp+1D8h+String], rdi
0x180113d47  mov     [rsp+1D8h+var_150], edi
0x180113d4e  mov     [rsp+1D8h+var_14C], dil
0x180113d56  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180113d5d  mov     [rsp+1D8h+var_180], rax
0x180113d62  lea     rax, [rsp+1D8h+var_150]
0x180113d6a  mov     [rsp+1D8h+var_178], rax
0x180113d6f  lea     rax, aMdmPolicyResul_187; "MDM_Policy_Result01_ApplicationManageme"...
0x180113d76  mov     [rsp+1D8h+var_170], rax
0x180113d7b  lea     rcx, [rsp+1D8h+var_150]
0x180113d83  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180113d88  mov     eax, cs:dword_180380B68
0x180113d8e  cmp     eax, 5
0x180113d91  jbe     short loc_180113E03
0x180113d93  mov     rdx, 200000000000h
0x180113d9d  lea     rcx, dword_180380B68
0x180113da4  call    _tlgKeywordOn
0x180113da9  test    al, al
0x180113dab  jz      short loc_180113E03
0x180113dad  cmp     [rsp+1D8h+var_14C], dil
0x180113db5  jz      short loc_180113DE5
0x180113db7  cmp     [rsp+1D8h+var_138], edi
0x180113dbe  jnz     short loc_180113DDB
0x180113dc0  cmp     [rsp+1D8h+var_134], edi
0x180113dc7  jnz     short loc_180113DDB
0x180113dc9  cmp     [rsp+1D8h+var_130], edi
0x180113dd0  jnz     short loc_180113DDB
0x180113dd2  cmp     [rsp+1D8h+var_12C], edi
0x180113dd9  jz      short loc_180113DE5
0x180113ddb  lea     r9, [rsp+1D8h+var_138]
0x180113de3  jmp     short loc_180113DE8
0x180113de5  mov     r9, rdi
0x180113de8  lea     r8, [rsp+1D8h+var_148]
0x180113df0  lea     rdx, dword_180360C5C
0x180113df7  lea     rcx, dword_180380B68
0x180113dfe  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180113e03  lea     rcx, [rsp+1D8h+var_180]; this
0x180113e08  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x180113e0d  nop
0x180113e0e  mov     [rsp+1D8h+var_188], rdi
0x180113e13  lea     rax, [rsp+1D8h+var_188]
0x180113e18  mov     [rsp+1D8h+var_1A8], rax
0x180113e1d  mov     [rsp+1D8h+var_1B0], 2
0x180113e25  mov     [rsp+1D8h+var_1B8], 11h
0x180113e2d  lea     r9, ?MDM_Policy_Result01_ApplicationManagement02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_ApplicationManagement02_NodeList
0x180113e34  xor     r8d, r8d
0x180113e37  xor     edx, edx
0x180113e39  mov     rcx, r12
0x180113e3c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180113e41  mov     r14d, eax
0x180113e44  test    eax, eax
0x180113e46  jz      short loc_180113E4D
0x180113e48  jmp     loc_1801143FB
0x180113e4d  lea     rbx, [rsp+1D8h+var_188]
0x180113e52  mov     [rsp+1D8h+var_160], rbx
0x180113e57  mov     r15d, 1
0x180113e5d  mov     [rsp+1D8h+var_158], r15b
0x180113e65  mov     rsi, [rsp+1D8h+var_188]
0x180113e6a  test    rsi, rsi
0x180113e6d  jnz     short loc_180113E77
0x180113e6f  mov     r14d, r15d
0x180113e72  jmp     loc_1801143FB
0x180113e77  mov     rax, [rsi]
0x180113e7a  mov     rcx, rsi
0x180113e7d  mov     rax, [rax+10h]
0x180113e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113e86  mov     r14d, eax
0x180113e89  test    eax, eax
0x180113e8b  jz      short loc_180113EAB
0x180113e8d  mov     rcx, [rsp+1D8h+var_188]
0x180113e92  test    rcx, rcx
0x180113e95  jz      short loc_180113EA6
0x180113e97  mov     rax, [rcx]
0x180113e9a  mov     edx, r15d
0x180113e9d  mov     rax, [rax]
0x180113ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113ea5  nop
0x180113ea6  jmp     loc_1801143FB
0x180113eab  mov     rax, [rsi]
0x180113eae  mov     rcx, rsi
0x180113eb1  mov     rax, [rax+8]
0x180113eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113eba  mov     r14d, eax
0x180113ebd  test    eax, eax
0x180113ebf  jz      short loc_180113EDF
0x180113ec1  mov     rcx, [rsp+1D8h+var_188]
0x180113ec6  test    rcx, rcx
0x180113ec9  jz      short loc_180113EDA
0x180113ecb  mov     rax, [rcx]
0x180113ece  mov     edx, r15d
0x180113ed1  mov     rax, [rax]
0x180113ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113ed9  nop
0x180113eda  jmp     loc_1801143FB
0x180113edf  mov     r15d, edi
0x180113ee2  mov     rax, [rsi+108h]
0x180113ee9  sub     rax, [rsi+100h]
0x180113ef0  sar     rax, 4
0x180113ef4  cmp     r15d, eax
0x180113ef7  jnb     loc_1801143C3
0x180113efd  lea     r8, [rsp+1D8h+instance]; instance
0x180113f05  lea     rdx, MDM_Policy_Result01_ApplicationManagement02_rtti; classDecl
0x180113f0c  mov     rcx, r12; context
0x180113f0f  call    MI_Context_ConstructInstance
0x180113f14  mov     r14d, eax
0x180113f17  test    eax, eax
0x180113f19  jz      short loc_180113F3B
0x180113f1b  mov     rcx, [rbx]
0x180113f1e  test    rcx, rcx
0x180113f21  jz      short loc_180113F36
0x180113f23  mov     rax, [rcx]
0x180113f26  mov     edx, 1
0x180113f2b  mov     rax, [rax]
0x180113f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113f33  mov     [rbx], rdi
0x180113f36  jmp     loc_1801143FB
0x180113f3b  mov     [rsp+1D8h+var_198], 1
0x180113f40  mov     rax, [rsi]
0x180113f43  lea     r9, [rsp+1D8h+String]
0x180113f48  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x180113f4f  mov     edx, r15d
0x180113f52  mov     rcx, rsi
0x180113f55  mov     rax, [rax+18h]
0x180113f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113f5e  test    eax, eax
0x180113f60  jnz     short loc_180113F79
0x180113f62  mov     rdx, [rsp+1D8h+String]
0x180113f67  test    rdx, rdx
0x180113f6a  jz      short loc_180113F79
0x180113f6c  lea     rcx, [rsp+1D8h+instance]
0x180113f74  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180113f79  mov     rax, [rsi]
0x180113f7c  lea     r9, [rsp+1D8h+String]
0x180113f81  lea     r8, aApplicationman; "ApplicationManagement"
0x180113f88  mov     edx, r15d
0x180113f8b  mov     rcx, rsi
0x180113f8e  mov     rax, [rax+18h]
0x180113f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113f97  test    eax, eax
0x180113f99  jnz     short loc_180113FB2
0x180113f9b  mov     rdx, [rsp+1D8h+String]
0x180113fa0  test    rdx, rdx
0x180113fa3  jz      short loc_180113FB2
0x180113fa5  lea     rcx, [rsp+1D8h+instance]
0x180113fad  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180113fb2  cmp     r13b, 1
0x180113fb6  jnz     short loc_180113FDA
0x180113fb8  lea     rdx, [rsp+1D8h+instance]
0x180113fc0  mov     rcx, r12; self
0x180113fc3  call    MI_Instance_Destruct
0x180113fc8  lea     rcx, [rsp+1D8h+instance]; self
0x180113fd0  call    MI_Instance_Destruct
0x180113fd5  jmp     loc_1801143B6
0x180113fda  mov     rax, [rsi]
0x180113fdd  lea     r9, [rsp+1D8h+String]
0x180113fe2  lea     r8, aAllowalltruste; "AllowAllTrustedApps"
0x180113fe9  mov     edx, r15d
0x180113fec  mov     rcx, rsi
0x180113fef  mov     rax, [rax+18h]
0x180113ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113ff8  test    eax, eax
0x180113ffa  jnz     short loc_18011401B
0x180113ffc  mov     rcx, [rsp+1D8h+String]; String
0x180114001  test    rcx, rcx
0x180114004  jz      short loc_18011401B
0x180114006  call    cs:__imp__wtoi
0x18011400c  mov     [rsp+1D8h+var_C8], eax
0x180114013  mov     [rsp+1D8h+var_C4], 1
0x18011401b  mov     rax, [rsi]
0x18011401e  lea     r9, [rsp+1D8h+String]
0x180114023  lea     r8, aAllowappstorea; "AllowAppStoreAutoUpdate"
0x18011402a  mov     edx, r15d
0x18011402d  mov     rcx, rsi
0x180114030  mov     rax, [rax+18h]
0x180114034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114039  test    eax, eax
0x18011403b  jnz     short loc_18011405C
0x18011403d  mov     rcx, [rsp+1D8h+String]; String
0x180114042  test    rcx, rcx
0x180114045  jz      short loc_18011405C
0x180114047  call    cs:__imp__wtoi
0x18011404d  mov     [rsp+1D8h+var_C0], eax
0x180114054  mov     [rsp+1D8h+var_BC], 1
0x18011405c  mov     rax, [rsi]
0x18011405f  lea     r9, [rsp+1D8h+String]
0x180114064  lea     r8, aAllowautomatic_0; "AllowAutomaticAppArchiving"
0x18011406b  mov     edx, r15d
0x18011406e  mov     rcx, rsi
0x180114071  mov     rax, [rax+18h]
0x180114075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011407a  test    eax, eax
0x18011407c  jnz     short loc_18011409D
0x18011407e  mov     rcx, [rsp+1D8h+String]; String
0x180114083  test    rcx, rcx
0x180114086  jz      short loc_18011409D
0x180114088  call    cs:__imp__wtoi
0x18011408e  mov     [rsp+1D8h+var_B8], eax
0x180114095  mov     [rsp+1D8h+var_B4], 1
0x18011409d  mov     rax, [rsi]
0x1801140a0  lea     r9, [rsp+1D8h+String]
0x1801140a5  lea     r8, aAllowdeveloper_0; "AllowDeveloperUnlock"
0x1801140ac  mov     edx, r15d
0x1801140af  mov     rcx, rsi
0x1801140b2  mov     rax, [rax+18h]
0x1801140b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801140bb  test    eax, eax
0x1801140bd  jnz     short loc_1801140DE
0x1801140bf  mov     rcx, [rsp+1D8h+String]; String
0x1801140c4  test    rcx, rcx
0x1801140c7  jz      short loc_1801140DE
0x1801140c9  call    cs:__imp__wtoi
0x1801140cf  mov     [rsp+1D8h+var_B0], eax
0x1801140d6  mov     [rsp+1D8h+var_AC], 1
0x1801140de  mov     rax, [rsi]
0x1801140e1  lea     r9, [rsp+1D8h+String]
0x1801140e6  lea     r8, aAllowgamedvr; "AllowGameDVR"
0x1801140ed  mov     edx, r15d
0x1801140f0  mov     rcx, rsi
0x1801140f3  mov     rax, [rax+18h]
0x1801140f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801140fc  test    eax, eax
0x1801140fe  jnz     short loc_18011411F
0x180114100  mov     rcx, [rsp+1D8h+String]; String
0x180114105  test    rcx, rcx
0x180114108  jz      short loc_18011411F
0x18011410a  call    cs:__imp__wtoi
0x180114110  mov     [rsp+1D8h+var_A8], eax
0x180114117  mov     [rsp+1D8h+var_A4], 1
0x18011411f  mov     rax, [rsi]
0x180114122  lea     r9, [rsp+1D8h+String]
0x180114127  lea     r8, aAllowshareduse; "AllowSharedUserAppData"
0x18011412e  mov     edx, r15d
0x180114131  mov     rcx, rsi
0x180114134  mov     rax, [rax+18h]
0x180114138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011413d  test    eax, eax
0x18011413f  jnz     short loc_180114160
0x180114141  mov     rcx, [rsp+1D8h+String]; String
0x180114146  test    rcx, rcx
0x180114149  jz      short loc_180114160
0x18011414b  call    cs:__imp__wtoi
0x180114151  mov     [rsp+1D8h+var_A0], eax
0x180114158  mov     [rsp+1D8h+var_9C], 1
0x180114160  mov     rax, [rsi]
0x180114163  lea     r9, [rsp+1D8h+String]
0x180114168  lea     r8, aBlocknonadminu; "BlockNonAdminUserInstall"
0x18011416f  mov     edx, r15d
0x180114172  mov     rcx, rsi
0x180114175  mov     rax, [rax+18h]
0x180114179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011417e  test    eax, eax
0x180114180  jnz     short loc_1801141A1
0x180114182  mov     rcx, [rsp+1D8h+String]; String
0x180114187  test    rcx, rcx
0x18011418a  jz      short loc_1801141A1
0x18011418c  call    cs:__imp__wtoi
0x180114192  mov     [rsp+1D8h+var_98], eax
0x180114199  mov     [rsp+1D8h+var_94], 1
0x1801141a1  mov     rax, [rsi]
0x1801141a4  lea     r9, [rsp+1D8h+String]
0x1801141a9  lea     r8, aDisablestoreor; "DisableStoreOriginatedApps"
0x1801141b0  mov     edx, r15d
0x1801141b3  mov     rcx, rsi
0x1801141b6  mov     rax, [rax+18h]
0x1801141ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801141bf  test    eax, eax
0x1801141c1  jnz     short loc_1801141E2
0x1801141c3  mov     rcx, [rsp+1D8h+String]; String
0x1801141c8  test    rcx, rcx
0x1801141cb  jz      short loc_1801141E2
0x1801141cd  call    cs:__imp__wtoi
0x1801141d3  mov     [rsp+1D8h+var_90], eax
0x1801141da  mov     [rsp+1D8h+var_8C], 1
0x1801141e2  mov     rax, [rsi]
0x1801141e5  lea     r9, [rsp+1D8h+String]
0x1801141ea  lea     r8, aLaunchappafter; "LaunchAppAfterLogOn"
0x1801141f1  mov     edx, r15d
0x1801141f4  mov     rcx, rsi
0x1801141f7  mov     rax, [rax+18h]
0x1801141fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114200  test    eax, eax
  ... truncated ...
```
