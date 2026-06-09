# MDM_Policy_Config01_WindowsLogon02_InvokeEnumerateInstances

- ea: `0x1801053e8`
- end: `0x18010596f`
- name: `MDM_Policy_Config01_WindowsLogon02_InvokeEnumerateInstances`
- size: `1415`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180104ba0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004e74`
- `0x180004ee4`
- `0x180004f1c`
- `0x180004f54`
- `0x180004f8c`
- `0x180004fc4`
- `0x180004ffc`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1801053e8`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1801057de`
- `msvcrt!_wtoi` at `0x180105858`
- `msvcrt!_wtoi` at `0x1801057de`
- `msvcrt!_wtoi` at `0x180105858`

## string_xrefs

- `0x18010570f`: `ConfigAutomaticRestartSignOn`
- `0x1801057fb`: `EnumerateLocalUsersOnDomainJoinedComputers`
- `0x18010563c`: `./Vendor/MSFT/Policy/Config`
- `0x180105463`: `MDM_Policy_Config01_WindowsLogon02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_WindowsLogon02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  unsigned int v7; // r14d
  WmiRequestHandlerAdd *v8; // rsi
  unsigned int i; // r15d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+48h] [rbp-160h] BYREF
  WmiRequestHandlerAdd *v14; // [rsp+50h] [rbp-158h] BYREF
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
    v7 = CreateRequestHandlerInstance(
           (__int64)self,
           0,
           0,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_WindowsLogon02_NodeList,
           9u,
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_WindowsLogon02_rtti, &instance);
              if ( v7 )
              {
                v6 = v14;
                if ( v14 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_67;
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
                      L"WindowsLogon",
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
                        L"AllowAutomaticRestartSignOn",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_EdpModeId(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigAutomaticRestartSignOn",
                        &String)
                  && String )
                {
                  MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DisableLockScreenAppNotifications",
                        &String)
                  && String )
                {
                  MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DontDisplayNetworkSelectionUI",
                        &String)
                  && String )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EnableFirstLogonAnimation",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EnumerateLocalUsersOnDomainJoinedComputers",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_DnsSuffix(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
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
  return v7;
}

```

## disassembly

```asm
0x1801053e8  mov     [rsp+arg_8], rbx
0x1801053ed  mov     [rsp+arg_10], rsi
0x1801053f2  push    rdi
0x1801053f3  push    r12
0x1801053f5  push    r13
0x1801053f7  push    r14
0x1801053f9  push    r15
0x1801053fb  sub     rsp, 180h
0x180105402  mov     rax, cs:__security_cookie
0x180105409  xor     rax, rsp
0x18010540c  mov     [rsp+1A8h+var_38], rax
0x180105414  mov     r13b, dl
0x180105417  mov     r12, rcx
0x18010541a  xor     edx, edx; Val
0x18010541c  mov     r8d, 0C0h; Size
0x180105422  lea     rcx, [rsp+1A8h+instance]; void *
0x18010542a  call    memset_0
0x18010542f  xor     edi, edi
0x180105431  mov     [rsp+1A8h+var_168], dil
0x180105436  mov     [rsp+1A8h+String], rdi
0x18010543b  mov     [rsp+1A8h+var_120], edi
0x180105442  mov     [rsp+1A8h+var_11C], dil
0x18010544a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180105451  mov     [rsp+1A8h+var_150], rax
0x180105456  lea     rax, [rsp+1A8h+var_120]
0x18010545e  mov     [rsp+1A8h+var_148], rax
0x180105463  lea     rax, aMdmPolicyConfi_64; "MDM_Policy_Config01_WindowsLogon02"
0x18010546a  mov     [rsp+1A8h+var_140], rax
0x18010546f  lea     rcx, [rsp+1A8h+var_120]
0x180105477  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18010547c  mov     eax, cs:dword_180380B68
0x180105482  cmp     eax, 5
0x180105485  jbe     short loc_1801054F7
0x180105487  mov     rdx, 200000000000h
0x180105491  lea     rcx, dword_180380B68
0x180105498  call    _tlgKeywordOn
0x18010549d  test    al, al
0x18010549f  jz      short loc_1801054F7
0x1801054a1  cmp     [rsp+1A8h+var_11C], dil
0x1801054a9  jz      short loc_1801054D9
0x1801054ab  cmp     [rsp+1A8h+var_108], edi
0x1801054b2  jnz     short loc_1801054CF
0x1801054b4  cmp     [rsp+1A8h+var_104], edi
0x1801054bb  jnz     short loc_1801054CF
0x1801054bd  cmp     [rsp+1A8h+var_100], edi
0x1801054c4  jnz     short loc_1801054CF
0x1801054c6  cmp     [rsp+1A8h+var_FC], edi
0x1801054cd  jz      short loc_1801054D9
0x1801054cf  lea     r9, [rsp+1A8h+var_108]
0x1801054d7  jmp     short loc_1801054DC
0x1801054d9  mov     r9, rdi
0x1801054dc  lea     r8, [rsp+1A8h+var_118]
0x1801054e4  lea     rdx, byte_18033EF75
0x1801054eb  lea     rcx, dword_180380B68
0x1801054f2  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801054f7  lea     rcx, [rsp+1A8h+var_150]; this
0x1801054fc  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x180105501  nop
0x180105502  mov     [rsp+1A8h+var_158], rdi
0x180105507  lea     rax, [rsp+1A8h+var_158]
0x18010550c  mov     [rsp+1A8h+var_178], rax
0x180105511  mov     [rsp+1A8h+var_180], 2
0x180105519  mov     [rsp+1A8h+var_188], 9
0x180105521  lea     r9, ?MDM_Policy_Config01_WindowsLogon02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_WindowsLogon02_NodeList
0x180105528  xor     r8d, r8d
0x18010552b  xor     edx, edx
0x18010552d  mov     rcx, r12
0x180105530  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180105535  mov     r14d, eax
0x180105538  test    eax, eax
0x18010553a  jz      short loc_180105541
0x18010553c  jmp     loc_1801058CF
0x180105541  lea     rbx, [rsp+1A8h+var_158]
0x180105546  mov     [rsp+1A8h+var_130], rbx
0x18010554b  mov     r15d, 1
0x180105551  mov     [rsp+1A8h+var_128], r15b
0x180105559  mov     rsi, [rsp+1A8h+var_158]
0x18010555e  test    rsi, rsi
0x180105561  jnz     short loc_18010556B
0x180105563  mov     r14d, r15d
0x180105566  jmp     loc_1801058CF
0x18010556b  mov     rax, [rsi]
0x18010556e  mov     rcx, rsi
0x180105571  mov     rax, [rax+10h]
0x180105575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010557a  mov     r14d, eax
0x18010557d  test    eax, eax
0x18010557f  jz      short loc_18010559F
0x180105581  mov     rcx, [rsp+1A8h+var_158]
0x180105586  test    rcx, rcx
0x180105589  jz      short loc_18010559A
0x18010558b  mov     rax, [rcx]
0x18010558e  mov     edx, r15d
0x180105591  mov     rax, [rax]
0x180105594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105599  nop
0x18010559a  jmp     loc_1801058CF
0x18010559f  mov     rax, [rsi]
0x1801055a2  mov     rcx, rsi
0x1801055a5  mov     rax, [rax+8]
0x1801055a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801055ae  mov     r14d, eax
0x1801055b1  test    eax, eax
0x1801055b3  jz      short loc_1801055D3
0x1801055b5  mov     rcx, [rsp+1A8h+var_158]
0x1801055ba  test    rcx, rcx
0x1801055bd  jz      short loc_1801055CE
0x1801055bf  mov     rax, [rcx]
0x1801055c2  mov     edx, r15d
0x1801055c5  mov     rax, [rax]
0x1801055c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801055cd  nop
0x1801055ce  jmp     loc_1801058CF
0x1801055d3  mov     r15d, edi
0x1801055d6  mov     rax, [rsi+108h]
0x1801055dd  sub     rax, [rsi+100h]
0x1801055e4  sar     rax, 4
0x1801055e8  cmp     r15d, eax
0x1801055eb  jnb     loc_180105897
0x1801055f1  lea     r8, [rsp+1A8h+instance]; instance
0x1801055f9  lea     rdx, MDM_Policy_Config01_WindowsLogon02_rtti; classDecl
0x180105600  mov     rcx, r12; context
0x180105603  call    MI_Context_ConstructInstance
0x180105608  mov     r14d, eax
0x18010560b  test    eax, eax
0x18010560d  jz      short loc_18010562F
0x18010560f  mov     rcx, [rbx]
0x180105612  test    rcx, rcx
0x180105615  jz      short loc_18010562A
0x180105617  mov     rax, [rcx]
0x18010561a  mov     edx, 1
0x18010561f  mov     rax, [rax]
0x180105622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105627  mov     [rbx], rdi
0x18010562a  jmp     loc_1801058CF
0x18010562f  mov     [rsp+1A8h+var_168], 1
0x180105634  mov     rax, [rsi]
0x180105637  lea     r9, [rsp+1A8h+String]
0x18010563c  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x180105643  mov     edx, r15d
0x180105646  mov     rcx, rsi
0x180105649  mov     rax, [rax+18h]
0x18010564d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105652  test    eax, eax
0x180105654  jnz     short loc_18010566D
0x180105656  mov     rdx, [rsp+1A8h+String]
0x18010565b  test    rdx, rdx
0x18010565e  jz      short loc_18010566D
0x180105660  lea     rcx, [rsp+1A8h+instance]
0x180105668  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18010566d  mov     rax, [rsi]
0x180105670  lea     r9, [rsp+1A8h+String]
0x180105675  lea     r8, aWindowslogon; "WindowsLogon"
0x18010567c  mov     edx, r15d
0x18010567f  mov     rcx, rsi
0x180105682  mov     rax, [rax+18h]
0x180105686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010568b  test    eax, eax
0x18010568d  jnz     short loc_1801056A6
0x18010568f  mov     rdx, [rsp+1A8h+String]
0x180105694  test    rdx, rdx
0x180105697  jz      short loc_1801056A6
0x180105699  lea     rcx, [rsp+1A8h+instance]
0x1801056a1  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1801056a6  cmp     r13b, 1
0x1801056aa  jnz     short loc_1801056CE
0x1801056ac  lea     rdx, [rsp+1A8h+instance]
0x1801056b4  mov     rcx, r12; self
0x1801056b7  call    MI_Instance_Destruct
0x1801056bc  lea     rcx, [rsp+1A8h+instance]; self
0x1801056c4  call    MI_Instance_Destruct
0x1801056c9  jmp     loc_18010588A
0x1801056ce  mov     rax, [rsi]
0x1801056d1  lea     r9, [rsp+1A8h+String]
0x1801056d6  lea     r8, aAllowautomatic; "AllowAutomaticRestartSignOn"
0x1801056dd  mov     edx, r15d
0x1801056e0  mov     rcx, rsi
0x1801056e3  mov     rax, [rax+18h]
0x1801056e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801056ec  test    eax, eax
0x1801056ee  jnz     short loc_180105707
0x1801056f0  mov     rdx, [rsp+1A8h+String]
0x1801056f5  test    rdx, rdx
0x1801056f8  jz      short loc_180105707
0x1801056fa  lea     rcx, [rsp+1A8h+instance]
0x180105702  call    MDM_VPNv2_User_01_Set_EdpModeId
0x180105707  mov     rax, [rsi]
0x18010570a  lea     r9, [rsp+1A8h+String]
0x18010570f  lea     r8, aConfigautomati; "ConfigAutomaticRestartSignOn"
0x180105716  mov     edx, r15d
0x180105719  mov     rcx, rsi
0x18010571c  mov     rax, [rax+18h]
0x180105720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105725  test    eax, eax
0x180105727  jnz     short loc_180105740
0x180105729  mov     rdx, [rsp+1A8h+String]
0x18010572e  test    rdx, rdx
0x180105731  jz      short loc_180105740
0x180105733  lea     rcx, [rsp+1A8h+instance]
0x18010573b  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x180105740  mov     rax, [rsi]
0x180105743  lea     r9, [rsp+1A8h+String]
0x180105748  lea     r8, aDisablelockscr; "DisableLockScreenAppNotifications"
0x18010574f  mov     edx, r15d
0x180105752  mov     rcx, rsi
0x180105755  mov     rax, [rax+18h]
0x180105759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010575e  test    eax, eax
0x180105760  jnz     short loc_180105779
0x180105762  mov     rdx, [rsp+1A8h+String]
0x180105767  test    rdx, rdx
0x18010576a  jz      short loc_180105779
0x18010576c  lea     rcx, [rsp+1A8h+instance]
0x180105774  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x180105779  mov     rax, [rsi]
0x18010577c  lea     r9, [rsp+1A8h+String]
0x180105781  lea     r8, aDontdisplaynet; "DontDisplayNetworkSelectionUI"
0x180105788  mov     edx, r15d
0x18010578b  mov     rcx, rsi
0x18010578e  mov     rax, [rax+18h]
0x180105792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105797  test    eax, eax
0x180105799  jnz     short loc_1801057B2
0x18010579b  mov     rdx, [rsp+1A8h+String]
0x1801057a0  test    rdx, rdx
0x1801057a3  jz      short loc_1801057B2
0x1801057a5  lea     rcx, [rsp+1A8h+instance]
0x1801057ad  call    MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges
0x1801057b2  mov     rax, [rsi]
0x1801057b5  lea     r9, [rsp+1A8h+String]
0x1801057ba  lea     r8, aEnablefirstlog; "EnableFirstLogonAnimation"
0x1801057c1  mov     edx, r15d
0x1801057c4  mov     rcx, rsi
0x1801057c7  mov     rax, [rax+18h]
0x1801057cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801057d0  test    eax, eax
0x1801057d2  jnz     short loc_1801057F3
0x1801057d4  mov     rcx, [rsp+1A8h+String]; String
0x1801057d9  test    rcx, rcx
0x1801057dc  jz      short loc_1801057F3
0x1801057de  call    cs:__imp__wtoi
0x1801057e4  mov     [rsp+1A8h+var_58], eax
0x1801057eb  mov     [rsp+1A8h+var_54], 1
0x1801057f3  mov     rax, [rsi]
0x1801057f6  lea     r9, [rsp+1A8h+String]
0x1801057fb  lea     r8, aEnumeratelocal; "EnumerateLocalUsersOnDomainJoinedComput"...
0x180105802  mov     edx, r15d
0x180105805  mov     rcx, rsi
0x180105808  mov     rax, [rax+18h]
0x18010580c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105811  test    eax, eax
0x180105813  jnz     short loc_18010582C
0x180105815  mov     rdx, [rsp+1A8h+String]
0x18010581a  test    rdx, rdx
0x18010581d  jz      short loc_18010582C
0x18010581f  lea     rcx, [rsp+1A8h+instance]
0x180105827  call    MDM_VPNv2_User_01_Set_DnsSuffix
0x18010582c  mov     rax, [rsi]
0x18010582f  lea     r9, [rsp+1A8h+String]
0x180105834  lea     r8, aHidefastusersw; "HideFastUserSwitching"
0x18010583b  mov     edx, r15d
0x18010583e  mov     rcx, rsi
0x180105841  mov     rax, [rax+18h]
0x180105845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010584a  test    eax, eax
0x18010584c  jnz     short loc_18010586D
0x18010584e  mov     rcx, [rsp+1A8h+String]; String
0x180105853  test    rcx, rcx
0x180105856  jz      short loc_18010586D
0x180105858  call    cs:__imp__wtoi
0x18010585e  mov     [rsp+1A8h+var_40], eax
0x180105865  mov     [rsp+1A8h+var_3C], 1
0x18010586d  lea     rdx, [rsp+1A8h+instance]
0x180105875  mov     rcx, r12; self
0x180105878  call    MI_Instance_Destruct
0x18010587d  lea     rcx, [rsp+1A8h+instance]; self
0x180105885  call    MI_Instance_Destruct
0x18010588a  mov     [rsp+1A8h+var_168], dil
0x18010588f  inc     r15d
0x180105892  jmp     loc_1801055D6
0x180105897  mov     rcx, [rbx]
0x18010589a  test    rcx, rcx
0x18010589d  jz      short loc_1801058B2
0x18010589f  mov     rax, [rcx]
0x1801058a2  mov     edx, 1
0x1801058a7  mov     rax, [rax]
0x1801058aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801058af  mov     [rbx], rdi
0x1801058b2  jmp     short loc_1801058CF
0x1801058b4  xor     edi, edi
0x1801058b6  cmp     [rsp+1A8h+var_168], dil
0x1801058bb  jz      short loc_1801058CA
0x1801058bd  lea     rcx, [rsp+1A8h+instance]; self
0x1801058c5  call    MI_Instance_Destruct
0x1801058ca  mov     r14d, dword ptr [rsp+1A8h+var_158]
0x1801058cf  mov     r8d, r14d; int
0x1801058d2  lea     rdx, aEnumerateinsta_1; "EnumerateInstancesEnd"
0x1801058d9  lea     rcx, [rsp+1A8h+var_150]; this
0x1801058de  call    ?WriteEnd@TelemetryEventWriter@@QEAAXPEBDH@Z; TelemetryEventWriter::WriteEnd(char const *,int)
0x1801058e3  mov     [rsp+1A8h+var_120], 2
  ... truncated ...
```
