# MDM_Policy_Config01_WindowsLogon02_InvokeEnumerateInstances

- ea: `0x180104e9c`
- end: `0x180105430`
- name: `MDM_Policy_Config01_WindowsLogon02_InvokeEnumerateInstances`
- size: `1428`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180104670`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005048`
- `0x1800050b8`
- `0x1800050f0`
- `0x180005128`
- `0x180005160`
- `0x180005198`
- `0x1800051d0`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x180104e9c`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180105292`
- `msvcrt!_wtoi` at `0x180105312`
- `msvcrt!_wtoi` at `0x180105292`
- `msvcrt!_wtoi` at `0x180105312`

## string_xrefs

- `0x1801051c3`: `ConfigAutomaticRestartSignOn`
- `0x1801052b5`: `EnumerateLocalUsersOnDomainJoinedComputers`
- `0x1801050f0`: `./Vendor/MSFT/Policy/Config`
- `0x180104f17`: `MDM_Policy_Config01_WindowsLogon02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_WindowsLogon02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  MI_Result v7; // r14d
  _QWORD *v8; // rsi
  unsigned int i; // r15d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+48h] [rbp-160h] BYREF
  _QWORD *v14; // [rsp+50h] [rbp-158h] BYREF
  _QWORD v15[3]; // [rsp+58h] [rbp-150h] BYREF
  const exception *v16[2]; // [rsp+70h] [rbp-138h] BYREF
  char v17; // [rsp+80h] [rbp-128h]
  int v18; // [rsp+88h] [rbp-120h] BYREF
  char v19; // [rsp+8Ch] [rbp-11Ch]
  _BYTE v20[16]; // [rsp+90h] [rbp-118h] BYREF
  _DWORD v21[4]; // [rsp+A0h] [rbp-108h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-F8h] BYREF
  int v23; // [rsp+150h] [rbp-58h]
  char v24; // [rsp+154h] [rbp-54h]
  int v25; // [rsp+168h] [rbp-40h]
  char v26; // [rsp+16Ch] [rbp-3Ch]

  memset_0(&instance, 0, 0xC0u);
  String = 0;
  v18 = 0;
  v19 = 0;
  v15[0] = &TelemetryEventWriter::`vftable';
  v15[1] = &v18;
  v15[2] = "MDM_Policy_Config01_WindowsLogon02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v18);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v19 && (v21[0] || v21[1] || v21[2] || v21[3]) )
      v5 = v21;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18033EF75,
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
                         &MDM_Policy_Config01_WindowsLogon02_NodeList,
                         9,
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_WindowsLogon02_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v14;
                if ( v14 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_67;
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
                      L"WindowsLogon",
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
                        L"AllowAutomaticRestartSignOn",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_EdpModeId(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigAutomaticRestartSignOn",
                        &String)
                  && String )
                {
                  MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DisableLockScreenAppNotifications",
                        &String)
                  && String )
                {
                  MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DontDisplayNetworkSelectionUI",
                        &String)
                  && String )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EnableFirstLogonAnimation",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EnumerateLocalUsersOnDomainJoinedComputers",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_DnsSuffix(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"HideFastUserSwitching",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
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
LABEL_67:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v15, "EnumerateInstancesEnd", v7);
  v18 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_18033B1BD,
      v20,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180104e9c  mov     [rsp+arg_8], rbx
0x180104ea1  mov     [rsp+arg_10], rsi
0x180104ea6  push    rdi
0x180104ea7  push    r12
0x180104ea9  push    r13
0x180104eab  push    r14
0x180104ead  push    r15
0x180104eaf  sub     rsp, 180h
0x180104eb6  mov     rax, cs:__security_cookie
0x180104ebd  xor     rax, rsp
0x180104ec0  mov     [rsp+1A8h+var_38], rax
0x180104ec8  mov     r13b, dl
0x180104ecb  mov     r12, rcx
0x180104ece  xor     edx, edx; Val
0x180104ed0  mov     r8d, 0C0h; Size
0x180104ed6  lea     rcx, [rsp+1A8h+instance]; void *
0x180104ede  call    memset_0
0x180104ee3  xor     edi, edi
0x180104ee5  mov     [rsp+1A8h+var_168], dil
0x180104eea  mov     [rsp+1A8h+String], rdi
0x180104eef  mov     [rsp+1A8h+var_120], edi
0x180104ef6  mov     [rsp+1A8h+var_11C], dil
0x180104efe  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180104f05  mov     [rsp+1A8h+var_150], rax
0x180104f0a  lea     rax, [rsp+1A8h+var_120]
0x180104f12  mov     [rsp+1A8h+var_148], rax
0x180104f17  lea     rax, aMdmPolicyConfi_64; "MDM_Policy_Config01_WindowsLogon02"
0x180104f1e  mov     [rsp+1A8h+var_140], rax
0x180104f23  lea     rcx, [rsp+1A8h+var_120]
0x180104f2b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180104f30  mov     eax, cs:dword_180380B68
0x180104f36  cmp     eax, 5
0x180104f39  jbe     short loc_180104FAB
0x180104f3b  mov     rdx, 200000000000h
0x180104f45  lea     rcx, dword_180380B68
0x180104f4c  call    _tlgKeywordOn
0x180104f51  test    al, al
0x180104f53  jz      short loc_180104FAB
0x180104f55  cmp     [rsp+1A8h+var_11C], dil
0x180104f5d  jz      short loc_180104F8D
0x180104f5f  cmp     [rsp+1A8h+var_108], edi
0x180104f66  jnz     short loc_180104F83
0x180104f68  cmp     [rsp+1A8h+var_104], edi
0x180104f6f  jnz     short loc_180104F83
0x180104f71  cmp     [rsp+1A8h+var_100], edi
0x180104f78  jnz     short loc_180104F83
0x180104f7a  cmp     [rsp+1A8h+var_FC], edi
0x180104f81  jz      short loc_180104F8D
0x180104f83  lea     r9, [rsp+1A8h+var_108]
0x180104f8b  jmp     short loc_180104F90
0x180104f8d  mov     r9, rdi
0x180104f90  lea     r8, [rsp+1A8h+var_118]
0x180104f98  lea     rdx, byte_18033EF75
0x180104f9f  lea     rcx, dword_180380B68
0x180104fa6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180104fab  lea     rcx, [rsp+1A8h+var_150]; this
0x180104fb0  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x180104fb5  nop
0x180104fb6  mov     [rsp+1A8h+var_158], rdi
0x180104fbb  lea     rax, [rsp+1A8h+var_158]
0x180104fc0  mov     [rsp+1A8h+var_178], rax
0x180104fc5  mov     [rsp+1A8h+var_180], 2
0x180104fcd  mov     [rsp+1A8h+var_188], 9
0x180104fd5  lea     r9, ?MDM_Policy_Config01_WindowsLogon02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_WindowsLogon02_NodeList
0x180104fdc  xor     r8d, r8d
0x180104fdf  xor     edx, edx
0x180104fe1  mov     rcx, r12
0x180104fe4  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180104fe9  mov     r14d, eax
0x180104fec  test    eax, eax
0x180104fee  jz      short loc_180104FF5
0x180104ff0  jmp     loc_18010538F
0x180104ff5  lea     rbx, [rsp+1A8h+var_158]
0x180104ffa  mov     [rsp+1A8h+var_130], rbx
0x180104fff  mov     r15d, 1
0x180105005  mov     [rsp+1A8h+var_128], r15b
0x18010500d  mov     rsi, [rsp+1A8h+var_158]
0x180105012  test    rsi, rsi
0x180105015  jnz     short loc_18010501F
0x180105017  mov     r14d, r15d
0x18010501a  jmp     loc_18010538F
0x18010501f  mov     rax, [rsi]
0x180105022  mov     rcx, rsi
0x180105025  mov     rax, [rax+10h]
0x180105029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010502e  mov     r14d, eax
0x180105031  test    eax, eax
0x180105033  jz      short loc_180105053
0x180105035  mov     rcx, [rsp+1A8h+var_158]
0x18010503a  test    rcx, rcx
0x18010503d  jz      short loc_18010504E
0x18010503f  mov     rax, [rcx]
0x180105042  mov     edx, r15d
0x180105045  mov     rax, [rax]
0x180105048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010504d  nop
0x18010504e  jmp     loc_18010538F
0x180105053  mov     rax, [rsi]
0x180105056  mov     rcx, rsi
0x180105059  mov     rax, [rax+8]
0x18010505d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105062  mov     r14d, eax
0x180105065  test    eax, eax
0x180105067  jz      short loc_180105087
0x180105069  mov     rcx, [rsp+1A8h+var_158]
0x18010506e  test    rcx, rcx
0x180105071  jz      short loc_180105082
0x180105073  mov     rax, [rcx]
0x180105076  mov     edx, r15d
0x180105079  mov     rax, [rax]
0x18010507c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105081  nop
0x180105082  jmp     loc_18010538F
0x180105087  mov     r15d, edi
0x18010508a  mov     rax, [rsi+108h]
0x180105091  sub     rax, [rsi+100h]
0x180105098  sar     rax, 4
0x18010509c  cmp     r15d, eax
0x18010509f  jnb     loc_180105357
0x1801050a5  lea     r8, [rsp+1A8h+instance]; instance
0x1801050ad  lea     rdx, MDM_Policy_Config01_WindowsLogon02_rtti; classDecl
0x1801050b4  mov     rcx, r12; context
0x1801050b7  call    MI_Context_ConstructInstance
0x1801050bc  mov     r14d, eax
0x1801050bf  test    eax, eax
0x1801050c1  jz      short loc_1801050E3
0x1801050c3  mov     rcx, [rbx]
0x1801050c6  test    rcx, rcx
0x1801050c9  jz      short loc_1801050DE
0x1801050cb  mov     rax, [rcx]
0x1801050ce  mov     edx, 1
0x1801050d3  mov     rax, [rax]
0x1801050d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801050db  mov     [rbx], rdi
0x1801050de  jmp     loc_18010538F
0x1801050e3  mov     [rsp+1A8h+var_168], 1
0x1801050e8  mov     rax, [rsi]
0x1801050eb  lea     r9, [rsp+1A8h+String]
0x1801050f0  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1801050f7  mov     edx, r15d
0x1801050fa  mov     rcx, rsi
0x1801050fd  mov     rax, [rax+18h]
0x180105101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105106  test    eax, eax
0x180105108  jnz     short loc_180105121
0x18010510a  mov     rdx, [rsp+1A8h+String]
0x18010510f  test    rdx, rdx
0x180105112  jz      short loc_180105121
0x180105114  lea     rcx, [rsp+1A8h+instance]
0x18010511c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180105121  mov     rax, [rsi]
0x180105124  lea     r9, [rsp+1A8h+String]
0x180105129  lea     r8, aWindowslogon; "WindowsLogon"
0x180105130  mov     edx, r15d
0x180105133  mov     rcx, rsi
0x180105136  mov     rax, [rax+18h]
0x18010513a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010513f  test    eax, eax
0x180105141  jnz     short loc_18010515A
0x180105143  mov     rdx, [rsp+1A8h+String]
0x180105148  test    rdx, rdx
0x18010514b  jz      short loc_18010515A
0x18010514d  lea     rcx, [rsp+1A8h+instance]
0x180105155  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18010515a  cmp     r13b, 1
0x18010515e  jnz     short loc_180105182
0x180105160  lea     rdx, [rsp+1A8h+instance]
0x180105168  mov     rcx, r12; self
0x18010516b  call    MI_Instance_Destruct
0x180105170  lea     rcx, [rsp+1A8h+instance]; self
0x180105178  call    MI_Instance_Destruct
0x18010517d  jmp     loc_18010534A
0x180105182  mov     rax, [rsi]
0x180105185  lea     r9, [rsp+1A8h+String]
0x18010518a  lea     r8, aAllowautomatic; "AllowAutomaticRestartSignOn"
0x180105191  mov     edx, r15d
0x180105194  mov     rcx, rsi
0x180105197  mov     rax, [rax+18h]
0x18010519b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801051a0  test    eax, eax
0x1801051a2  jnz     short loc_1801051BB
0x1801051a4  mov     rdx, [rsp+1A8h+String]
0x1801051a9  test    rdx, rdx
0x1801051ac  jz      short loc_1801051BB
0x1801051ae  lea     rcx, [rsp+1A8h+instance]
0x1801051b6  call    MDM_VPNv2_User_01_Set_EdpModeId
0x1801051bb  mov     rax, [rsi]
0x1801051be  lea     r9, [rsp+1A8h+String]
0x1801051c3  lea     r8, aConfigautomati; "ConfigAutomaticRestartSignOn"
0x1801051ca  mov     edx, r15d
0x1801051cd  mov     rcx, rsi
0x1801051d0  mov     rax, [rax+18h]
0x1801051d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801051d9  test    eax, eax
0x1801051db  jnz     short loc_1801051F4
0x1801051dd  mov     rdx, [rsp+1A8h+String]
0x1801051e2  test    rdx, rdx
0x1801051e5  jz      short loc_1801051F4
0x1801051e7  lea     rcx, [rsp+1A8h+instance]
0x1801051ef  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x1801051f4  mov     rax, [rsi]
0x1801051f7  lea     r9, [rsp+1A8h+String]
0x1801051fc  lea     r8, aDisablelockscr; "DisableLockScreenAppNotifications"
0x180105203  mov     edx, r15d
0x180105206  mov     rcx, rsi
0x180105209  mov     rax, [rax+18h]
0x18010520d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105212  test    eax, eax
0x180105214  jnz     short loc_18010522D
0x180105216  mov     rdx, [rsp+1A8h+String]
0x18010521b  test    rdx, rdx
0x18010521e  jz      short loc_18010522D
0x180105220  lea     rcx, [rsp+1A8h+instance]
0x180105228  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x18010522d  mov     rax, [rsi]
0x180105230  lea     r9, [rsp+1A8h+String]
0x180105235  lea     r8, aDontdisplaynet; "DontDisplayNetworkSelectionUI"
0x18010523c  mov     edx, r15d
0x18010523f  mov     rcx, rsi
0x180105242  mov     rax, [rax+18h]
0x180105246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010524b  test    eax, eax
0x18010524d  jnz     short loc_180105266
0x18010524f  mov     rdx, [rsp+1A8h+String]
0x180105254  test    rdx, rdx
0x180105257  jz      short loc_180105266
0x180105259  lea     rcx, [rsp+1A8h+instance]
0x180105261  call    MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges
0x180105266  mov     rax, [rsi]
0x180105269  lea     r9, [rsp+1A8h+String]
0x18010526e  lea     r8, aEnablefirstlog; "EnableFirstLogonAnimation"
0x180105275  mov     edx, r15d
0x180105278  mov     rcx, rsi
0x18010527b  mov     rax, [rax+18h]
0x18010527f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105284  test    eax, eax
0x180105286  jnz     short loc_1801052AD
0x180105288  mov     rcx, [rsp+1A8h+String]; String
0x18010528d  test    rcx, rcx
0x180105290  jz      short loc_1801052AD
0x180105292  call    cs:__imp__wtoi
0x180105299  nop     dword ptr [rax+rax+00h]
0x18010529e  mov     [rsp+1A8h+var_58], eax
0x1801052a5  mov     [rsp+1A8h+var_54], 1
0x1801052ad  mov     rax, [rsi]
0x1801052b0  lea     r9, [rsp+1A8h+String]
0x1801052b5  lea     r8, aEnumeratelocal; "EnumerateLocalUsersOnDomainJoinedComput"...
0x1801052bc  mov     edx, r15d
0x1801052bf  mov     rcx, rsi
0x1801052c2  mov     rax, [rax+18h]
0x1801052c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801052cb  test    eax, eax
0x1801052cd  jnz     short loc_1801052E6
0x1801052cf  mov     rdx, [rsp+1A8h+String]
0x1801052d4  test    rdx, rdx
0x1801052d7  jz      short loc_1801052E6
0x1801052d9  lea     rcx, [rsp+1A8h+instance]
0x1801052e1  call    MDM_VPNv2_User_01_Set_DnsSuffix
0x1801052e6  mov     rax, [rsi]
0x1801052e9  lea     r9, [rsp+1A8h+String]
0x1801052ee  lea     r8, aHidefastusersw; "HideFastUserSwitching"
0x1801052f5  mov     edx, r15d
0x1801052f8  mov     rcx, rsi
0x1801052fb  mov     rax, [rax+18h]
0x1801052ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105304  test    eax, eax
0x180105306  jnz     short loc_18010532D
0x180105308  mov     rcx, [rsp+1A8h+String]; String
0x18010530d  test    rcx, rcx
0x180105310  jz      short loc_18010532D
0x180105312  call    cs:__imp__wtoi
0x180105319  nop     dword ptr [rax+rax+00h]
0x18010531e  mov     [rsp+1A8h+var_40], eax
0x180105325  mov     [rsp+1A8h+var_3C], 1
0x18010532d  lea     rdx, [rsp+1A8h+instance]
0x180105335  mov     rcx, r12; self
0x180105338  call    MI_Instance_Destruct
0x18010533d  lea     rcx, [rsp+1A8h+instance]; self
0x180105345  call    MI_Instance_Destruct
0x18010534a  mov     [rsp+1A8h+var_168], dil
0x18010534f  inc     r15d
0x180105352  jmp     loc_18010508A
0x180105357  mov     rcx, [rbx]
0x18010535a  test    rcx, rcx
0x18010535d  jz      short loc_180105372
0x18010535f  mov     rax, [rcx]
0x180105362  mov     edx, 1
0x180105367  mov     rax, [rax]
0x18010536a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010536f  mov     [rbx], rdi
0x180105372  jmp     short loc_18010538F
0x180105374  xor     edi, edi
0x180105376  cmp     [rsp+1A8h+var_168], dil
0x18010537b  jz      short loc_18010538A
0x18010537d  lea     rcx, [rsp+1A8h+instance]; self
0x180105385  call    MI_Instance_Destruct
0x18010538a  mov     r14d, dword ptr [rsp+1A8h+var_158]
0x18010538f  mov     r8d, r14d; int
0x180105392  lea     rdx, aEnumerateinsta_1; "EnumerateInstancesEnd"
0x180105399  lea     rcx, [rsp+1A8h+var_150]; this
  ... truncated ...
```
