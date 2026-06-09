# MDM_Policy_Config01_Authentication02_InvokeEnumerateInstances

- ea: `0x180062ea4`
- end: `0x18006347c`
- name: `MDM_Policy_Config01_Authentication02_InvokeEnumerateInstances`
- size: `1496`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180062620`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004eac`
- `0x180004ee4`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000506c`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x180062ea4`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800631b6`
- `msvcrt!_wtoi` at `0x1800631f7`
- `msvcrt!_wtoi` at `0x180063238`
- `msvcrt!_wtoi` at `0x1800632eb`
- `msvcrt!_wtoi` at `0x18006332c`
- `msvcrt!_wtoi` at `0x1800631b6`
- `msvcrt!_wtoi` at `0x1800631f7`
- `msvcrt!_wtoi` at `0x180063238`
- `msvcrt!_wtoi` at `0x1800632eb`
- `msvcrt!_wtoi` at `0x18006332c`

## string_xrefs

- `0x180063255`: `ConfigureWebcamAccessDomainNames`
- `0x18006328e`: `ConfigureWebSignInAllowedUrls`
- `0x1800630f8`: `./Vendor/MSFT/Policy/Config`
- `0x180062f1f`: `MDM_Policy_Config01_Authentication02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Authentication02_InvokeEnumerateInstances(MI_Context *self, char a2)
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
    v7 = CreateRequestHandlerInstance(
           (__int64)self,
           0,
           0,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_Authentication02_NodeList,
           0xAu,
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Authentication02_rtti, &instance);
              if ( v7 )
              {
                v6 = v14;
                if ( v14 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_70;
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
                      L"Authentication",
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
                        L"AllowAadPasswordReset",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowFastReconnect",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowSecondaryAuthenticationDevice",
                        &String)
                  && String )
                {
                  v27 = _wtoi(String);
                  v28 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureWebcamAccessDomainNames",
                        &String)
                  && String )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureWebSignInAllowedUrls",
                        &String)
                  && String )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EnableFastFirstSignIn",
                        &String)
                  && String )
                {
                  v29 = _wtoi(String);
                  v30 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EnableWebSignIn",
                        &String)
                  && String )
                {
                  v31 = _wtoi(String);
                  v32 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
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
  return v7;
}

```

## disassembly

```asm
0x180062ea4  mov     [rsp+arg_8], rbx
0x180062ea9  mov     [rsp+arg_10], rsi
0x180062eae  push    rdi
0x180062eaf  push    r12
0x180062eb1  push    r13
0x180062eb3  push    r14
0x180062eb5  push    r15
0x180062eb7  sub     rsp, 180h
0x180062ebe  mov     rax, cs:__security_cookie
0x180062ec5  xor     rax, rsp
0x180062ec8  mov     [rsp+1A8h+var_38], rax
0x180062ed0  mov     r13b, dl
0x180062ed3  mov     r12, rcx
0x180062ed6  xor     edx, edx; Val
0x180062ed8  mov     r8d, 0B8h; Size
0x180062ede  lea     rcx, [rsp+1A8h+instance]; void *
0x180062ee6  call    memset_0
0x180062eeb  xor     edi, edi
0x180062eed  mov     [rsp+1A8h+var_168], dil
0x180062ef2  mov     [rsp+1A8h+String], rdi
0x180062ef7  mov     [rsp+1A8h+var_120], edi
0x180062efe  mov     [rsp+1A8h+var_11C], dil
0x180062f06  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180062f0d  mov     [rsp+1A8h+var_150], rax
0x180062f12  lea     rax, [rsp+1A8h+var_120]
0x180062f1a  mov     [rsp+1A8h+var_148], rax
0x180062f1f  lea     rax, aMdmPolicyConfi_111; "MDM_Policy_Config01_Authentication02"
0x180062f26  mov     [rsp+1A8h+var_140], rax
0x180062f2b  lea     rcx, [rsp+1A8h+var_120]
0x180062f33  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180062f38  mov     eax, cs:dword_180380B68
0x180062f3e  cmp     eax, 5
0x180062f41  jbe     short loc_180062FB3
0x180062f43  mov     rdx, 200000000000h
0x180062f4d  lea     rcx, dword_180380B68
0x180062f54  call    _tlgKeywordOn
0x180062f59  test    al, al
0x180062f5b  jz      short loc_180062FB3
0x180062f5d  cmp     [rsp+1A8h+var_11C], dil
0x180062f65  jz      short loc_180062F95
0x180062f67  cmp     [rsp+1A8h+var_108], edi
0x180062f6e  jnz     short loc_180062F8B
0x180062f70  cmp     [rsp+1A8h+var_104], edi
0x180062f77  jnz     short loc_180062F8B
0x180062f79  cmp     [rsp+1A8h+var_100], edi
0x180062f80  jnz     short loc_180062F8B
0x180062f82  cmp     [rsp+1A8h+var_FC], edi
0x180062f89  jz      short loc_180062F95
0x180062f8b  lea     r9, [rsp+1A8h+var_108]
0x180062f93  jmp     short loc_180062F98
0x180062f95  mov     r9, rdi
0x180062f98  lea     r8, [rsp+1A8h+var_118]
0x180062fa0  lea     rdx, byte_18033A48F
0x180062fa7  lea     rcx, dword_180380B68
0x180062fae  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180062fb3  lea     rcx, [rsp+1A8h+var_150]; this
0x180062fb8  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x180062fbd  nop
0x180062fbe  mov     [rsp+1A8h+var_158], rdi
0x180062fc3  lea     rax, [rsp+1A8h+var_158]
0x180062fc8  mov     [rsp+1A8h+var_178], rax
0x180062fcd  mov     [rsp+1A8h+var_180], 2
0x180062fd5  mov     [rsp+1A8h+var_188], 0Ah
0x180062fdd  lea     r9, ?MDM_Policy_Config01_Authentication02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Authentication02_NodeList
0x180062fe4  xor     r8d, r8d
0x180062fe7  xor     edx, edx
0x180062fe9  mov     rcx, r12
0x180062fec  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180062ff1  mov     r14d, eax
0x180062ff4  test    eax, eax
0x180062ff6  jz      short loc_180062FFD
0x180062ff8  jmp     loc_1800633DC
0x180062ffd  lea     rbx, [rsp+1A8h+var_158]
0x180063002  mov     [rsp+1A8h+var_130], rbx
0x180063007  mov     r15d, 1
0x18006300d  mov     [rsp+1A8h+var_128], r15b
0x180063015  mov     rsi, [rsp+1A8h+var_158]
0x18006301a  test    rsi, rsi
0x18006301d  jnz     short loc_180063027
0x18006301f  mov     r14d, r15d
0x180063022  jmp     loc_1800633DC
0x180063027  mov     rax, [rsi]
0x18006302a  mov     rcx, rsi
0x18006302d  mov     rax, [rax+10h]
0x180063031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063036  mov     r14d, eax
0x180063039  test    eax, eax
0x18006303b  jz      short loc_18006305B
0x18006303d  mov     rcx, [rsp+1A8h+var_158]
0x180063042  test    rcx, rcx
0x180063045  jz      short loc_180063056
0x180063047  mov     rax, [rcx]
0x18006304a  mov     edx, r15d
0x18006304d  mov     rax, [rax]
0x180063050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063055  nop
0x180063056  jmp     loc_1800633DC
0x18006305b  mov     rax, [rsi]
0x18006305e  mov     rcx, rsi
0x180063061  mov     rax, [rax+8]
0x180063065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006306a  mov     r14d, eax
0x18006306d  test    eax, eax
0x18006306f  jz      short loc_18006308F
0x180063071  mov     rcx, [rsp+1A8h+var_158]
0x180063076  test    rcx, rcx
0x180063079  jz      short loc_18006308A
0x18006307b  mov     rax, [rcx]
0x18006307e  mov     edx, r15d
0x180063081  mov     rax, [rax]
0x180063084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063089  nop
0x18006308a  jmp     loc_1800633DC
0x18006308f  mov     r15d, edi
0x180063092  mov     rax, [rsi+108h]
0x180063099  sub     rax, [rsi+100h]
0x1800630a0  sar     rax, 4
0x1800630a4  cmp     r15d, eax
0x1800630a7  jnb     loc_1800633A4
0x1800630ad  lea     r8, [rsp+1A8h+instance]; instance
0x1800630b5  lea     rdx, MDM_Policy_Config01_Authentication02_rtti; classDecl
0x1800630bc  mov     rcx, r12; context
0x1800630bf  call    MI_Context_ConstructInstance
0x1800630c4  mov     r14d, eax
0x1800630c7  test    eax, eax
0x1800630c9  jz      short loc_1800630EB
0x1800630cb  mov     rcx, [rbx]
0x1800630ce  test    rcx, rcx
0x1800630d1  jz      short loc_1800630E6
0x1800630d3  mov     rax, [rcx]
0x1800630d6  mov     edx, 1
0x1800630db  mov     rax, [rax]
0x1800630de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800630e3  mov     [rbx], rdi
0x1800630e6  jmp     loc_1800633DC
0x1800630eb  mov     [rsp+1A8h+var_168], 1
0x1800630f0  mov     rax, [rsi]
0x1800630f3  lea     r9, [rsp+1A8h+String]
0x1800630f8  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800630ff  mov     edx, r15d
0x180063102  mov     rcx, rsi
0x180063105  mov     rax, [rax+18h]
0x180063109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006310e  test    eax, eax
0x180063110  jnz     short loc_180063129
0x180063112  mov     rdx, [rsp+1A8h+String]
0x180063117  test    rdx, rdx
0x18006311a  jz      short loc_180063129
0x18006311c  lea     rcx, [rsp+1A8h+instance]
0x180063124  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180063129  mov     rax, [rsi]
0x18006312c  lea     r9, [rsp+1A8h+String]
0x180063131  lea     r8, aAuthentication; "Authentication"
0x180063138  mov     edx, r15d
0x18006313b  mov     rcx, rsi
0x18006313e  mov     rax, [rax+18h]
0x180063142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063147  test    eax, eax
0x180063149  jnz     short loc_180063162
0x18006314b  mov     rdx, [rsp+1A8h+String]
0x180063150  test    rdx, rdx
0x180063153  jz      short loc_180063162
0x180063155  lea     rcx, [rsp+1A8h+instance]
0x18006315d  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180063162  cmp     r13b, 1
0x180063166  jnz     short loc_18006318A
0x180063168  lea     rdx, [rsp+1A8h+instance]
0x180063170  mov     rcx, r12; self
0x180063173  call    MI_Instance_Destruct
0x180063178  lea     rcx, [rsp+1A8h+instance]; self
0x180063180  call    MI_Instance_Destruct
0x180063185  jmp     loc_180063397
0x18006318a  mov     rax, [rsi]
0x18006318d  lea     r9, [rsp+1A8h+String]
0x180063192  lea     r8, aAllowaadpasswo; "AllowAadPasswordReset"
0x180063199  mov     edx, r15d
0x18006319c  mov     rcx, rsi
0x18006319f  mov     rax, [rax+18h]
0x1800631a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800631a8  test    eax, eax
0x1800631aa  jnz     short loc_1800631CB
0x1800631ac  mov     rcx, [rsp+1A8h+String]; String
0x1800631b1  test    rcx, rcx
0x1800631b4  jz      short loc_1800631CB
0x1800631b6  call    cs:__imp__wtoi
0x1800631bc  mov     [rsp+1A8h+var_98], eax
0x1800631c3  mov     [rsp+1A8h+var_94], 1
0x1800631cb  mov     rax, [rsi]
0x1800631ce  lea     r9, [rsp+1A8h+String]
0x1800631d3  lea     r8, aAllowfastrecon; "AllowFastReconnect"
0x1800631da  mov     edx, r15d
0x1800631dd  mov     rcx, rsi
0x1800631e0  mov     rax, [rax+18h]
0x1800631e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800631e9  test    eax, eax
0x1800631eb  jnz     short loc_18006320C
0x1800631ed  mov     rcx, [rsp+1A8h+String]; String
0x1800631f2  test    rcx, rcx
0x1800631f5  jz      short loc_18006320C
0x1800631f7  call    cs:__imp__wtoi
0x1800631fd  mov     [rsp+1A8h+var_90], eax
0x180063204  mov     [rsp+1A8h+var_8C], 1
0x18006320c  mov     rax, [rsi]
0x18006320f  lea     r9, [rsp+1A8h+String]
0x180063214  lea     r8, aAllowsecondary; "AllowSecondaryAuthenticationDevice"
0x18006321b  mov     edx, r15d
0x18006321e  mov     rcx, rsi
0x180063221  mov     rax, [rax+18h]
0x180063225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006322a  test    eax, eax
0x18006322c  jnz     short loc_18006324D
0x18006322e  mov     rcx, [rsp+1A8h+String]; String
0x180063233  test    rcx, rcx
0x180063236  jz      short loc_18006324D
0x180063238  call    cs:__imp__wtoi
0x18006323e  mov     [rsp+1A8h+var_88], eax
0x180063245  mov     [rsp+1A8h+var_84], 1
0x18006324d  mov     rax, [rsi]
0x180063250  lea     r9, [rsp+1A8h+String]
0x180063255  lea     r8, aConfigurewebca; "ConfigureWebcamAccessDomainNames"
0x18006325c  mov     edx, r15d
0x18006325f  mov     rcx, rsi
0x180063262  mov     rax, [rax+18h]
0x180063266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006326b  test    eax, eax
0x18006326d  jnz     short loc_180063286
0x18006326f  mov     rdx, [rsp+1A8h+String]
0x180063274  test    rdx, rdx
0x180063277  jz      short loc_180063286
0x180063279  lea     rcx, [rsp+1A8h+instance]
0x180063281  call    MDM_VPNv2_TrafficFilterList02_01_Set_RemotePortRanges
0x180063286  mov     rax, [rsi]
0x180063289  lea     r9, [rsp+1A8h+String]
0x18006328e  lea     r8, aConfigurewebsi; "ConfigureWebSignInAllowedUrls"
0x180063295  mov     edx, r15d
0x180063298  mov     rcx, rsi
0x18006329b  mov     rax, [rax+18h]
0x18006329f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800632a4  test    eax, eax
0x1800632a6  jnz     short loc_1800632BF
0x1800632a8  mov     rdx, [rsp+1A8h+String]
0x1800632ad  test    rdx, rdx
0x1800632b0  jz      short loc_1800632BF
0x1800632b2  lea     rcx, [rsp+1A8h+instance]
0x1800632ba  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x1800632bf  mov     rax, [rsi]
0x1800632c2  lea     r9, [rsp+1A8h+String]
0x1800632c7  lea     r8, aEnablefastfirs; "EnableFastFirstSignIn"
0x1800632ce  mov     edx, r15d
0x1800632d1  mov     rcx, rsi
0x1800632d4  mov     rax, [rax+18h]
0x1800632d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800632dd  test    eax, eax
0x1800632df  jnz     short loc_180063300
0x1800632e1  mov     rcx, [rsp+1A8h+String]; String
0x1800632e6  test    rcx, rcx
0x1800632e9  jz      short loc_180063300
0x1800632eb  call    cs:__imp__wtoi
0x1800632f1  mov     [rsp+1A8h+var_60], eax
0x1800632f8  mov     [rsp+1A8h+var_5C], 1
0x180063300  mov     rax, [rsi]
0x180063303  lea     r9, [rsp+1A8h+String]
0x180063308  lea     r8, aEnablewebsigni; "EnableWebSignIn"
0x18006330f  mov     edx, r15d
0x180063312  mov     rcx, rsi
0x180063315  mov     rax, [rax+18h]
0x180063319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006331e  test    eax, eax
0x180063320  jnz     short loc_180063341
0x180063322  mov     rcx, [rsp+1A8h+String]; String
0x180063327  test    rcx, rcx
0x18006332a  jz      short loc_180063341
0x18006332c  call    cs:__imp__wtoi
0x180063332  mov     [rsp+1A8h+var_58], eax
0x180063339  mov     [rsp+1A8h+var_54], 1
0x180063341  mov     rax, [rsi]
0x180063344  lea     r9, [rsp+1A8h+String]
0x180063349  lea     r8, aPreferredaadte; "PreferredAadTenantDomainName"
0x180063350  mov     edx, r15d
0x180063353  mov     rcx, rsi
0x180063356  mov     rax, [rax+18h]
0x18006335a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006335f  test    eax, eax
0x180063361  jnz     short loc_18006337A
0x180063363  mov     rdx, [rsp+1A8h+String]
0x180063368  test    rdx, rdx
0x18006336b  jz      short loc_18006337A
0x18006336d  lea     rcx, [rsp+1A8h+instance]
0x180063375  call    MDM_VPNv2_User_01_Set_TrustedNetworkDetection
0x18006337a  lea     rdx, [rsp+1A8h+instance]
0x180063382  mov     rcx, r12; self
0x180063385  call    MI_Instance_Destruct
0x18006338a  lea     rcx, [rsp+1A8h+instance]; self
0x180063392  call    MI_Instance_Destruct
0x180063397  mov     [rsp+1A8h+var_168], dil
0x18006339c  inc     r15d
0x18006339f  jmp     loc_180063092
0x1800633a4  mov     rcx, [rbx]
0x1800633a7  test    rcx, rcx
0x1800633aa  jz      short loc_1800633BF
  ... truncated ...
```
