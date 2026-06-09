# MDM_Policy_Config01_Authentication02_InvokeEnumerateInstances

- ea: `0x180062718`
- end: `0x180062d0f`
- name: `MDM_Policy_Config01_Authentication02_InvokeEnumerateInstances`
- size: `1527`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180061eb0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005080`
- `0x1800050b8`
- `0x180005160`
- `0x180005198`
- `0x180005240`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x180062718`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180062a2a`
- `msvcrt!_wtoi` at `0x180062a71`
- `msvcrt!_wtoi` at `0x180062ab8`
- `msvcrt!_wtoi` at `0x180062b71`
- `msvcrt!_wtoi` at `0x180062bb8`
- `msvcrt!_wtoi` at `0x180062a2a`
- `msvcrt!_wtoi` at `0x180062a71`
- `msvcrt!_wtoi` at `0x180062ab8`
- `msvcrt!_wtoi` at `0x180062b71`
- `msvcrt!_wtoi` at `0x180062bb8`

## string_xrefs

- `0x180062adb`: `ConfigureWebcamAccessDomainNames`
- `0x180062b14`: `ConfigureWebSignInAllowedUrls`
- `0x18006296c`: `./Vendor/MSFT/Policy/Config`
- `0x180062793`: `MDM_Policy_Config01_Authentication02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Authentication02_InvokeEnumerateInstances(MI_Context *self, char a2)
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
  int v23; // [rsp+110h] [rbp-98h]
  char v24; // [rsp+114h] [rbp-94h]
  int v25; // [rsp+118h] [rbp-90h]
  char v26; // [rsp+11Ch] [rbp-8Ch]
  int v27; // [rsp+120h] [rbp-88h]
  char v28; // [rsp+124h] [rbp-84h]
  int v29; // [rsp+148h] [rbp-60h]
  char v30; // [rsp+14Ch] [rbp-5Ch]
  int v31; // [rsp+150h] [rbp-58h]
  char v32; // [rsp+154h] [rbp-54h]

  memset_0(&instance, 0, 0xB8u);
  String = 0;
  v18 = 0;
  v19 = 0;
  v15[0] = &TelemetryEventWriter::`vftable';
  v15[1] = &v18;
  v15[2] = "MDM_Policy_Config01_Authentication02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v18);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v19 && (v21[0] || v21[1] || v21[2] || v21[3]) )
      v5 = v21;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_18033A48F,
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
                         &MDM_Policy_Config01_Authentication02_NodeList,
                         10,
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Authentication02_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v14;
                if ( v14 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_70;
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
                      L"Authentication",
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
                        L"AllowAadPasswordReset",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowFastReconnect",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowSecondaryAuthenticationDevice",
                        &String)
                  && String )
                {
                  v27 = _wtoi(String);
                  v28 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureWebcamAccessDomainNames",
                        &String)
                  && String )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureWebSignInAllowedUrls",
                        &String)
                  && String )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EnableFastFirstSignIn",
                        &String)
                  && String )
                {
                  v29 = _wtoi(String);
                  v30 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EnableWebSignIn",
                        &String)
                  && String )
                {
                  v31 = _wtoi(String);
                  v32 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"PreferredAadTenantDomainName",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_TrustedNetworkDetection(&instance);
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
LABEL_70:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v15, "EnumerateInstancesEnd", v7);
  v18 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_18036B757,
      v20,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180062718  mov     [rsp+arg_8], rbx
0x18006271d  mov     [rsp+arg_10], rsi
0x180062722  push    rdi
0x180062723  push    r12
0x180062725  push    r13
0x180062727  push    r14
0x180062729  push    r15
0x18006272b  sub     rsp, 180h
0x180062732  mov     rax, cs:__security_cookie
0x180062739  xor     rax, rsp
0x18006273c  mov     [rsp+1A8h+var_38], rax
0x180062744  mov     r13b, dl
0x180062747  mov     r12, rcx
0x18006274a  xor     edx, edx; Val
0x18006274c  mov     r8d, 0B8h; Size
0x180062752  lea     rcx, [rsp+1A8h+instance]; void *
0x18006275a  call    memset_0
0x18006275f  xor     edi, edi
0x180062761  mov     [rsp+1A8h+var_168], dil
0x180062766  mov     [rsp+1A8h+String], rdi
0x18006276b  mov     [rsp+1A8h+var_120], edi
0x180062772  mov     [rsp+1A8h+var_11C], dil
0x18006277a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180062781  mov     [rsp+1A8h+var_150], rax
0x180062786  lea     rax, [rsp+1A8h+var_120]
0x18006278e  mov     [rsp+1A8h+var_148], rax
0x180062793  lea     rax, aMdmPolicyConfi_111; "MDM_Policy_Config01_Authentication02"
0x18006279a  mov     [rsp+1A8h+var_140], rax
0x18006279f  lea     rcx, [rsp+1A8h+var_120]
0x1800627a7  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800627ac  mov     eax, cs:dword_180380B68
0x1800627b2  cmp     eax, 5
0x1800627b5  jbe     short loc_180062827
0x1800627b7  mov     rdx, 200000000000h
0x1800627c1  lea     rcx, dword_180380B68
0x1800627c8  call    _tlgKeywordOn
0x1800627cd  test    al, al
0x1800627cf  jz      short loc_180062827
0x1800627d1  cmp     [rsp+1A8h+var_11C], dil
0x1800627d9  jz      short loc_180062809
0x1800627db  cmp     [rsp+1A8h+var_108], edi
0x1800627e2  jnz     short loc_1800627FF
0x1800627e4  cmp     [rsp+1A8h+var_104], edi
0x1800627eb  jnz     short loc_1800627FF
0x1800627ed  cmp     [rsp+1A8h+var_100], edi
0x1800627f4  jnz     short loc_1800627FF
0x1800627f6  cmp     [rsp+1A8h+var_FC], edi
0x1800627fd  jz      short loc_180062809
0x1800627ff  lea     r9, [rsp+1A8h+var_108]
0x180062807  jmp     short loc_18006280C
0x180062809  mov     r9, rdi
0x18006280c  lea     r8, [rsp+1A8h+var_118]
0x180062814  lea     rdx, byte_18033A48F
0x18006281b  lea     rcx, dword_180380B68
0x180062822  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180062827  lea     rcx, [rsp+1A8h+var_150]; this
0x18006282c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x180062831  nop
0x180062832  mov     [rsp+1A8h+var_158], rdi
0x180062837  lea     rax, [rsp+1A8h+var_158]
0x18006283c  mov     [rsp+1A8h+var_178], rax
0x180062841  mov     [rsp+1A8h+var_180], 2
0x180062849  mov     [rsp+1A8h+var_188], 0Ah
0x180062851  lea     r9, ?MDM_Policy_Config01_Authentication02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Authentication02_NodeList
0x180062858  xor     r8d, r8d
0x18006285b  xor     edx, edx
0x18006285d  mov     rcx, r12
0x180062860  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180062865  mov     r14d, eax
0x180062868  test    eax, eax
0x18006286a  jz      short loc_180062871
0x18006286c  jmp     loc_180062C6E
0x180062871  lea     rbx, [rsp+1A8h+var_158]
0x180062876  mov     [rsp+1A8h+var_130], rbx
0x18006287b  mov     r15d, 1
0x180062881  mov     [rsp+1A8h+var_128], r15b
0x180062889  mov     rsi, [rsp+1A8h+var_158]
0x18006288e  test    rsi, rsi
0x180062891  jnz     short loc_18006289B
0x180062893  mov     r14d, r15d
0x180062896  jmp     loc_180062C6E
0x18006289b  mov     rax, [rsi]
0x18006289e  mov     rcx, rsi
0x1800628a1  mov     rax, [rax+10h]
0x1800628a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800628aa  mov     r14d, eax
0x1800628ad  test    eax, eax
0x1800628af  jz      short loc_1800628CF
0x1800628b1  mov     rcx, [rsp+1A8h+var_158]
0x1800628b6  test    rcx, rcx
0x1800628b9  jz      short loc_1800628CA
0x1800628bb  mov     rax, [rcx]
0x1800628be  mov     edx, r15d
0x1800628c1  mov     rax, [rax]
0x1800628c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800628c9  nop
0x1800628ca  jmp     loc_180062C6E
0x1800628cf  mov     rax, [rsi]
0x1800628d2  mov     rcx, rsi
0x1800628d5  mov     rax, [rax+8]
0x1800628d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800628de  mov     r14d, eax
0x1800628e1  test    eax, eax
0x1800628e3  jz      short loc_180062903
0x1800628e5  mov     rcx, [rsp+1A8h+var_158]
0x1800628ea  test    rcx, rcx
0x1800628ed  jz      short loc_1800628FE
0x1800628ef  mov     rax, [rcx]
0x1800628f2  mov     edx, r15d
0x1800628f5  mov     rax, [rax]
0x1800628f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800628fd  nop
0x1800628fe  jmp     loc_180062C6E
0x180062903  mov     r15d, edi
0x180062906  mov     rax, [rsi+108h]
0x18006290d  sub     rax, [rsi+100h]
0x180062914  sar     rax, 4
0x180062918  cmp     r15d, eax
0x18006291b  jnb     loc_180062C36
0x180062921  lea     r8, [rsp+1A8h+instance]; instance
0x180062929  lea     rdx, MDM_Policy_Config01_Authentication02_rtti; classDecl
0x180062930  mov     rcx, r12; context
0x180062933  call    MI_Context_ConstructInstance
0x180062938  mov     r14d, eax
0x18006293b  test    eax, eax
0x18006293d  jz      short loc_18006295F
0x18006293f  mov     rcx, [rbx]
0x180062942  test    rcx, rcx
0x180062945  jz      short loc_18006295A
0x180062947  mov     rax, [rcx]
0x18006294a  mov     edx, 1
0x18006294f  mov     rax, [rax]
0x180062952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062957  mov     [rbx], rdi
0x18006295a  jmp     loc_180062C6E
0x18006295f  mov     [rsp+1A8h+var_168], 1
0x180062964  mov     rax, [rsi]
0x180062967  lea     r9, [rsp+1A8h+String]
0x18006296c  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x180062973  mov     edx, r15d
0x180062976  mov     rcx, rsi
0x180062979  mov     rax, [rax+18h]
0x18006297d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062982  test    eax, eax
0x180062984  jnz     short loc_18006299D
0x180062986  mov     rdx, [rsp+1A8h+String]
0x18006298b  test    rdx, rdx
0x18006298e  jz      short loc_18006299D
0x180062990  lea     rcx, [rsp+1A8h+instance]
0x180062998  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18006299d  mov     rax, [rsi]
0x1800629a0  lea     r9, [rsp+1A8h+String]
0x1800629a5  lea     r8, aAuthentication; "Authentication"
0x1800629ac  mov     edx, r15d
0x1800629af  mov     rcx, rsi
0x1800629b2  mov     rax, [rax+18h]
0x1800629b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800629bb  test    eax, eax
0x1800629bd  jnz     short loc_1800629D6
0x1800629bf  mov     rdx, [rsp+1A8h+String]
0x1800629c4  test    rdx, rdx
0x1800629c7  jz      short loc_1800629D6
0x1800629c9  lea     rcx, [rsp+1A8h+instance]
0x1800629d1  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800629d6  cmp     r13b, 1
0x1800629da  jnz     short loc_1800629FE
0x1800629dc  lea     rdx, [rsp+1A8h+instance]
0x1800629e4  mov     rcx, r12; self
0x1800629e7  call    MI_Instance_Destruct
0x1800629ec  lea     rcx, [rsp+1A8h+instance]; self
0x1800629f4  call    MI_Instance_Destruct
0x1800629f9  jmp     loc_180062C29
0x1800629fe  mov     rax, [rsi]
0x180062a01  lea     r9, [rsp+1A8h+String]
0x180062a06  lea     r8, aAllowaadpasswo; "AllowAadPasswordReset"
0x180062a0d  mov     edx, r15d
0x180062a10  mov     rcx, rsi
0x180062a13  mov     rax, [rax+18h]
0x180062a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a1c  test    eax, eax
0x180062a1e  jnz     short loc_180062A45
0x180062a20  mov     rcx, [rsp+1A8h+String]; String
0x180062a25  test    rcx, rcx
0x180062a28  jz      short loc_180062A45
0x180062a2a  call    cs:__imp__wtoi
0x180062a31  nop     dword ptr [rax+rax+00h]
0x180062a36  mov     [rsp+1A8h+var_98], eax
0x180062a3d  mov     [rsp+1A8h+var_94], 1
0x180062a45  mov     rax, [rsi]
0x180062a48  lea     r9, [rsp+1A8h+String]
0x180062a4d  lea     r8, aAllowfastrecon; "AllowFastReconnect"
0x180062a54  mov     edx, r15d
0x180062a57  mov     rcx, rsi
0x180062a5a  mov     rax, [rax+18h]
0x180062a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062a63  test    eax, eax
0x180062a65  jnz     short loc_180062A8C
0x180062a67  mov     rcx, [rsp+1A8h+String]; String
0x180062a6c  test    rcx, rcx
0x180062a6f  jz      short loc_180062A8C
0x180062a71  call    cs:__imp__wtoi
0x180062a78  nop     dword ptr [rax+rax+00h]
0x180062a7d  mov     [rsp+1A8h+var_90], eax
0x180062a84  mov     [rsp+1A8h+var_8C], 1
0x180062a8c  mov     rax, [rsi]
0x180062a8f  lea     r9, [rsp+1A8h+String]
0x180062a94  lea     r8, aAllowsecondary; "AllowSecondaryAuthenticationDevice"
0x180062a9b  mov     edx, r15d
0x180062a9e  mov     rcx, rsi
0x180062aa1  mov     rax, [rax+18h]
0x180062aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062aaa  test    eax, eax
0x180062aac  jnz     short loc_180062AD3
0x180062aae  mov     rcx, [rsp+1A8h+String]; String
0x180062ab3  test    rcx, rcx
0x180062ab6  jz      short loc_180062AD3
0x180062ab8  call    cs:__imp__wtoi
0x180062abf  nop     dword ptr [rax+rax+00h]
0x180062ac4  mov     [rsp+1A8h+var_88], eax
0x180062acb  mov     [rsp+1A8h+var_84], 1
0x180062ad3  mov     rax, [rsi]
0x180062ad6  lea     r9, [rsp+1A8h+String]
0x180062adb  lea     r8, aConfigurewebca; "ConfigureWebcamAccessDomainNames"
0x180062ae2  mov     edx, r15d
0x180062ae5  mov     rcx, rsi
0x180062ae8  mov     rax, [rax+18h]
0x180062aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062af1  test    eax, eax
0x180062af3  jnz     short loc_180062B0C
0x180062af5  mov     rdx, [rsp+1A8h+String]
0x180062afa  test    rdx, rdx
0x180062afd  jz      short loc_180062B0C
0x180062aff  lea     rcx, [rsp+1A8h+instance]
0x180062b07  call    MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges
0x180062b0c  mov     rax, [rsi]
0x180062b0f  lea     r9, [rsp+1A8h+String]
0x180062b14  lea     r8, aConfigurewebsi; "ConfigureWebSignInAllowedUrls"
0x180062b1b  mov     edx, r15d
0x180062b1e  mov     rcx, rsi
0x180062b21  mov     rax, [rax+18h]
0x180062b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062b2a  test    eax, eax
0x180062b2c  jnz     short loc_180062B45
0x180062b2e  mov     rdx, [rsp+1A8h+String]
0x180062b33  test    rdx, rdx
0x180062b36  jz      short loc_180062B45
0x180062b38  lea     rcx, [rsp+1A8h+instance]
0x180062b40  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x180062b45  mov     rax, [rsi]
0x180062b48  lea     r9, [rsp+1A8h+String]
0x180062b4d  lea     r8, aEnablefastfirs; "EnableFastFirstSignIn"
0x180062b54  mov     edx, r15d
0x180062b57  mov     rcx, rsi
0x180062b5a  mov     rax, [rax+18h]
0x180062b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062b63  test    eax, eax
0x180062b65  jnz     short loc_180062B8C
0x180062b67  mov     rcx, [rsp+1A8h+String]; String
0x180062b6c  test    rcx, rcx
0x180062b6f  jz      short loc_180062B8C
0x180062b71  call    cs:__imp__wtoi
0x180062b78  nop     dword ptr [rax+rax+00h]
0x180062b7d  mov     [rsp+1A8h+var_60], eax
0x180062b84  mov     [rsp+1A8h+var_5C], 1
0x180062b8c  mov     rax, [rsi]
0x180062b8f  lea     r9, [rsp+1A8h+String]
0x180062b94  lea     r8, aEnablewebsigni; "EnableWebSignIn"
0x180062b9b  mov     edx, r15d
0x180062b9e  mov     rcx, rsi
0x180062ba1  mov     rax, [rax+18h]
0x180062ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062baa  test    eax, eax
0x180062bac  jnz     short loc_180062BD3
0x180062bae  mov     rcx, [rsp+1A8h+String]; String
0x180062bb3  test    rcx, rcx
0x180062bb6  jz      short loc_180062BD3
0x180062bb8  call    cs:__imp__wtoi
0x180062bbf  nop     dword ptr [rax+rax+00h]
0x180062bc4  mov     [rsp+1A8h+var_58], eax
0x180062bcb  mov     [rsp+1A8h+var_54], 1
0x180062bd3  mov     rax, [rsi]
0x180062bd6  lea     r9, [rsp+1A8h+String]
0x180062bdb  lea     r8, aPreferredaadte; "PreferredAadTenantDomainName"
0x180062be2  mov     edx, r15d
0x180062be5  mov     rcx, rsi
0x180062be8  mov     rax, [rax+18h]
0x180062bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062bf1  test    eax, eax
0x180062bf3  jnz     short loc_180062C0C
0x180062bf5  mov     rdx, [rsp+1A8h+String]
0x180062bfa  test    rdx, rdx
0x180062bfd  jz      short loc_180062C0C
0x180062bff  lea     rcx, [rsp+1A8h+instance]
0x180062c07  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x180062c0c  lea     rdx, [rsp+1A8h+instance]
0x180062c14  mov     rcx, r12; self
0x180062c17  call    MI_Instance_Destruct
0x180062c1c  lea     rcx, [rsp+1A8h+instance]; self
0x180062c24  call    MI_Instance_Destruct
0x180062c29  mov     [rsp+1A8h+var_168], dil
  ... truncated ...
```
