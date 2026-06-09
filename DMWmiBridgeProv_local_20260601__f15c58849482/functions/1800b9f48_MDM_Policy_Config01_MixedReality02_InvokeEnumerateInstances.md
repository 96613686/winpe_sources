# MDM_Policy_Config01_MixedReality02_InvokeEnumerateInstances

- ea: `0x1800b9f48`
- end: `0x1800ba685`
- name: `MDM_Policy_Config01_MixedReality02_InvokeEnumerateInstances`
- size: `1853`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b95e0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800b9f48`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800ba25a`
- `msvcrt!_wtoi` at `0x1800ba2a1`
- `msvcrt!_wtoi` at `0x1800ba2e8`
- `msvcrt!_wtoi` at `0x1800ba32f`
- `msvcrt!_wtoi` at `0x1800ba376`
- `msvcrt!_wtoi` at `0x1800ba3bd`
- `msvcrt!_wtoi` at `0x1800ba404`
- `msvcrt!_wtoi` at `0x1800ba44b`
- `msvcrt!_wtoi` at `0x1800ba492`
- `msvcrt!_wtoi` at `0x1800ba4d9`
- `msvcrt!_wtoi` at `0x1800ba520`
- `msvcrt!_wtoi` at `0x1800ba567`
- `msvcrt!_wtoi` at `0x1800ba25a`
- `msvcrt!_wtoi` at `0x1800ba2a1`
- `msvcrt!_wtoi` at `0x1800ba2e8`
- `msvcrt!_wtoi` at `0x1800ba32f`
- `msvcrt!_wtoi` at `0x1800ba376`
- `msvcrt!_wtoi` at `0x1800ba3bd`
- `msvcrt!_wtoi` at `0x1800ba404`
- `msvcrt!_wtoi` at `0x1800ba44b`
- `msvcrt!_wtoi` at `0x1800ba492`
- `msvcrt!_wtoi` at `0x1800ba4d9`
- `msvcrt!_wtoi` at `0x1800ba520`
- `msvcrt!_wtoi` at `0x1800ba567`

## string_xrefs

- `0x1800ba236`: `AADGroupMembershipCacheValidityInDays`
- `0x1800ba27d`: `AllowLaunchUriInSingleAppKiosk`
- `0x1800ba352`: `ConfigureMovingPlatform`
- `0x1800ba19c`: `./Vendor/MSFT/Policy/Config`
- `0x1800b9fc3`: `MDM_Policy_Config01_MixedReality02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_MixedReality02_InvokeEnumerateInstances(MI_Context *self, char a2)
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
  int v29; // [rsp+128h] [rbp-80h]
  char v30; // [rsp+12Ch] [rbp-7Ch]
  int v31; // [rsp+130h] [rbp-78h]
  char v32; // [rsp+134h] [rbp-74h]
  int v33; // [rsp+138h] [rbp-70h]
  char v34; // [rsp+13Ch] [rbp-6Ch]
  int v35; // [rsp+140h] [rbp-68h]
  char v36; // [rsp+144h] [rbp-64h]
  int v37; // [rsp+148h] [rbp-60h]
  char v38; // [rsp+14Ch] [rbp-5Ch]
  int v39; // [rsp+150h] [rbp-58h]
  char v40; // [rsp+154h] [rbp-54h]
  int v41; // [rsp+158h] [rbp-50h]
  char v42; // [rsp+15Ch] [rbp-4Ch]
  int v43; // [rsp+160h] [rbp-48h]
  char v44; // [rsp+164h] [rbp-44h]
  int v45; // [rsp+168h] [rbp-40h]
  char v46; // [rsp+16Ch] [rbp-3Ch]

  memset_0(&instance, 0, 0xC0u);
  String = 0;
  v18 = 0;
  v19 = 0;
  v15[0] = &TelemetryEventWriter::`vftable';
  v15[1] = &v18;
  v15[2] = "MDM_Policy_Config01_MixedReality02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v18);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v19 && (v21[0] || v21[1] || v21[2] || v21[3]) )
      v5 = v21;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_1803595D9,
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
                         &MDM_Policy_Config01_MixedReality02_NodeList,
                         14,
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_MixedReality02_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v14;
                if ( v14 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_82;
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
                      L"MixedReality",
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
                        L"AADGroupMembershipCacheValidityInDays",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowLaunchUriInSingleAppKiosk",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AutomaticDisplayAdjustment",
                        &String)
                  && String )
                {
                  v27 = _wtoi(String);
                  v28 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"BrightnessButtonDisabled",
                        &String)
                  && String )
                {
                  v29 = _wtoi(String);
                  v30 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureMovingPlatform",
                        &String)
                  && String )
                {
                  v31 = _wtoi(String);
                  v32 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EyeTrackingCalibrationPrompt",
                        &String)
                  && String )
                {
                  v33 = _wtoi(String);
                  v34 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"FallbackDiagnostics",
                        &String)
                  && String )
                {
                  v35 = _wtoi(String);
                  v36 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"HeadTrackingMode",
                        &String)
                  && String )
                {
                  v37 = _wtoi(String);
                  v38 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ManualDownDirectionDisabled",
                        &String)
                  && String )
                {
                  v39 = _wtoi(String);
                  v40 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"MicrophoneDisabled",
                        &String)
                  && String )
                {
                  v41 = _wtoi(String);
                  v42 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"VisitorAutoLogon",
                        &String)
                  && String )
                {
                  v43 = _wtoi(String);
                  v44 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"VolumeButtonDisabled",
                        &String)
                  && String )
                {
                  v45 = _wtoi(String);
                  v46 = 1;
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
LABEL_82:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v15, "EnumerateInstancesEnd", v7);
  v18 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &unk_18036F088,
      v20,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800b9f48  mov     [rsp+arg_8], rbx
0x1800b9f4d  mov     [rsp+arg_10], rsi
0x1800b9f52  push    rdi
0x1800b9f53  push    r12
0x1800b9f55  push    r13
0x1800b9f57  push    r14
0x1800b9f59  push    r15
0x1800b9f5b  sub     rsp, 180h
0x1800b9f62  mov     rax, cs:__security_cookie
0x1800b9f69  xor     rax, rsp
0x1800b9f6c  mov     [rsp+1A8h+var_38], rax
0x1800b9f74  mov     r13b, dl
0x1800b9f77  mov     r12, rcx
0x1800b9f7a  xor     edx, edx; Val
0x1800b9f7c  mov     r8d, 0C0h; Size
0x1800b9f82  lea     rcx, [rsp+1A8h+instance]; void *
0x1800b9f8a  call    memset_0
0x1800b9f8f  xor     edi, edi
0x1800b9f91  mov     [rsp+1A8h+var_168], dil
0x1800b9f96  mov     [rsp+1A8h+String], rdi
0x1800b9f9b  mov     [rsp+1A8h+var_120], edi
0x1800b9fa2  mov     [rsp+1A8h+var_11C], dil
0x1800b9faa  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800b9fb1  mov     [rsp+1A8h+var_150], rax
0x1800b9fb6  lea     rax, [rsp+1A8h+var_120]
0x1800b9fbe  mov     [rsp+1A8h+var_148], rax
0x1800b9fc3  lea     rax, aMdmPolicyConfi_149; "MDM_Policy_Config01_MixedReality02"
0x1800b9fca  mov     [rsp+1A8h+var_140], rax
0x1800b9fcf  lea     rcx, [rsp+1A8h+var_120]
0x1800b9fd7  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800b9fdc  mov     eax, cs:dword_180380B68
0x1800b9fe2  cmp     eax, 5
0x1800b9fe5  jbe     short loc_1800BA057
0x1800b9fe7  mov     rdx, 200000000000h
0x1800b9ff1  lea     rcx, dword_180380B68
0x1800b9ff8  call    _tlgKeywordOn
0x1800b9ffd  test    al, al
0x1800b9fff  jz      short loc_1800BA057
0x1800ba001  cmp     [rsp+1A8h+var_11C], dil
0x1800ba009  jz      short loc_1800BA039
0x1800ba00b  cmp     [rsp+1A8h+var_108], edi
0x1800ba012  jnz     short loc_1800BA02F
0x1800ba014  cmp     [rsp+1A8h+var_104], edi
0x1800ba01b  jnz     short loc_1800BA02F
0x1800ba01d  cmp     [rsp+1A8h+var_100], edi
0x1800ba024  jnz     short loc_1800BA02F
0x1800ba026  cmp     [rsp+1A8h+var_FC], edi
0x1800ba02d  jz      short loc_1800BA039
0x1800ba02f  lea     r9, [rsp+1A8h+var_108]
0x1800ba037  jmp     short loc_1800BA03C
0x1800ba039  mov     r9, rdi
0x1800ba03c  lea     r8, [rsp+1A8h+var_118]
0x1800ba044  lea     rdx, byte_1803595D9
0x1800ba04b  lea     rcx, dword_180380B68
0x1800ba052  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800ba057  lea     rcx, [rsp+1A8h+var_150]; this
0x1800ba05c  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800ba061  nop
0x1800ba062  mov     [rsp+1A8h+var_158], rdi
0x1800ba067  lea     rax, [rsp+1A8h+var_158]
0x1800ba06c  mov     [rsp+1A8h+var_178], rax
0x1800ba071  mov     [rsp+1A8h+var_180], 2
0x1800ba079  mov     [rsp+1A8h+var_188], 0Eh
0x1800ba081  lea     r9, ?MDM_Policy_Config01_MixedReality02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_MixedReality02_NodeList
0x1800ba088  xor     r8d, r8d
0x1800ba08b  xor     edx, edx
0x1800ba08d  mov     rcx, r12
0x1800ba090  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800ba095  mov     r14d, eax
0x1800ba098  test    eax, eax
0x1800ba09a  jz      short loc_1800BA0A1
0x1800ba09c  jmp     loc_1800BA5E4
0x1800ba0a1  lea     rbx, [rsp+1A8h+var_158]
0x1800ba0a6  mov     [rsp+1A8h+var_130], rbx
0x1800ba0ab  mov     r15d, 1
0x1800ba0b1  mov     [rsp+1A8h+var_128], r15b
0x1800ba0b9  mov     rsi, [rsp+1A8h+var_158]
0x1800ba0be  test    rsi, rsi
0x1800ba0c1  jnz     short loc_1800BA0CB
0x1800ba0c3  mov     r14d, r15d
0x1800ba0c6  jmp     loc_1800BA5E4
0x1800ba0cb  mov     rax, [rsi]
0x1800ba0ce  mov     rcx, rsi
0x1800ba0d1  mov     rax, [rax+10h]
0x1800ba0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba0da  mov     r14d, eax
0x1800ba0dd  test    eax, eax
0x1800ba0df  jz      short loc_1800BA0FF
0x1800ba0e1  mov     rcx, [rsp+1A8h+var_158]
0x1800ba0e6  test    rcx, rcx
0x1800ba0e9  jz      short loc_1800BA0FA
0x1800ba0eb  mov     rax, [rcx]
0x1800ba0ee  mov     edx, r15d
0x1800ba0f1  mov     rax, [rax]
0x1800ba0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba0f9  nop
0x1800ba0fa  jmp     loc_1800BA5E4
0x1800ba0ff  mov     rax, [rsi]
0x1800ba102  mov     rcx, rsi
0x1800ba105  mov     rax, [rax+8]
0x1800ba109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba10e  mov     r14d, eax
0x1800ba111  test    eax, eax
0x1800ba113  jz      short loc_1800BA133
0x1800ba115  mov     rcx, [rsp+1A8h+var_158]
0x1800ba11a  test    rcx, rcx
0x1800ba11d  jz      short loc_1800BA12E
0x1800ba11f  mov     rax, [rcx]
0x1800ba122  mov     edx, r15d
0x1800ba125  mov     rax, [rax]
0x1800ba128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba12d  nop
0x1800ba12e  jmp     loc_1800BA5E4
0x1800ba133  mov     r15d, edi
0x1800ba136  mov     rax, [rsi+108h]
0x1800ba13d  sub     rax, [rsi+100h]
0x1800ba144  sar     rax, 4
0x1800ba148  cmp     r15d, eax
0x1800ba14b  jnb     loc_1800BA5AC
0x1800ba151  lea     r8, [rsp+1A8h+instance]; instance
0x1800ba159  lea     rdx, MDM_Policy_Config01_MixedReality02_rtti; classDecl
0x1800ba160  mov     rcx, r12; context
0x1800ba163  call    MI_Context_ConstructInstance
0x1800ba168  mov     r14d, eax
0x1800ba16b  test    eax, eax
0x1800ba16d  jz      short loc_1800BA18F
0x1800ba16f  mov     rcx, [rbx]
0x1800ba172  test    rcx, rcx
0x1800ba175  jz      short loc_1800BA18A
0x1800ba177  mov     rax, [rcx]
0x1800ba17a  mov     edx, 1
0x1800ba17f  mov     rax, [rax]
0x1800ba182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba187  mov     [rbx], rdi
0x1800ba18a  jmp     loc_1800BA5E4
0x1800ba18f  mov     [rsp+1A8h+var_168], 1
0x1800ba194  mov     rax, [rsi]
0x1800ba197  lea     r9, [rsp+1A8h+String]
0x1800ba19c  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800ba1a3  mov     edx, r15d
0x1800ba1a6  mov     rcx, rsi
0x1800ba1a9  mov     rax, [rax+18h]
0x1800ba1ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba1b2  test    eax, eax
0x1800ba1b4  jnz     short loc_1800BA1CD
0x1800ba1b6  mov     rdx, [rsp+1A8h+String]
0x1800ba1bb  test    rdx, rdx
0x1800ba1be  jz      short loc_1800BA1CD
0x1800ba1c0  lea     rcx, [rsp+1A8h+instance]
0x1800ba1c8  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800ba1cd  mov     rax, [rsi]
0x1800ba1d0  lea     r9, [rsp+1A8h+String]
0x1800ba1d5  lea     r8, aMixedreality; "MixedReality"
0x1800ba1dc  mov     edx, r15d
0x1800ba1df  mov     rcx, rsi
0x1800ba1e2  mov     rax, [rax+18h]
0x1800ba1e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba1eb  test    eax, eax
0x1800ba1ed  jnz     short loc_1800BA206
0x1800ba1ef  mov     rdx, [rsp+1A8h+String]
0x1800ba1f4  test    rdx, rdx
0x1800ba1f7  jz      short loc_1800BA206
0x1800ba1f9  lea     rcx, [rsp+1A8h+instance]
0x1800ba201  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800ba206  cmp     r13b, 1
0x1800ba20a  jnz     short loc_1800BA22E
0x1800ba20c  lea     rdx, [rsp+1A8h+instance]
0x1800ba214  mov     rcx, r12; self
0x1800ba217  call    MI_Instance_Destruct
0x1800ba21c  lea     rcx, [rsp+1A8h+instance]; self
0x1800ba224  call    MI_Instance_Destruct
0x1800ba229  jmp     loc_1800BA59F
0x1800ba22e  mov     rax, [rsi]
0x1800ba231  lea     r9, [rsp+1A8h+String]
0x1800ba236  lea     r8, aAadgroupmember; "AADGroupMembershipCacheValidityInDays"
0x1800ba23d  mov     edx, r15d
0x1800ba240  mov     rcx, rsi
0x1800ba243  mov     rax, [rax+18h]
0x1800ba247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba24c  test    eax, eax
0x1800ba24e  jnz     short loc_1800BA275
0x1800ba250  mov     rcx, [rsp+1A8h+String]; String
0x1800ba255  test    rcx, rcx
0x1800ba258  jz      short loc_1800BA275
0x1800ba25a  call    cs:__imp__wtoi
0x1800ba261  nop     dword ptr [rax+rax+00h]
0x1800ba266  mov     [rsp+1A8h+var_98], eax
0x1800ba26d  mov     [rsp+1A8h+var_94], 1
0x1800ba275  mov     rax, [rsi]
0x1800ba278  lea     r9, [rsp+1A8h+String]
0x1800ba27d  lea     r8, aAllowlaunchuri; "AllowLaunchUriInSingleAppKiosk"
0x1800ba284  mov     edx, r15d
0x1800ba287  mov     rcx, rsi
0x1800ba28a  mov     rax, [rax+18h]
0x1800ba28e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba293  test    eax, eax
0x1800ba295  jnz     short loc_1800BA2BC
0x1800ba297  mov     rcx, [rsp+1A8h+String]; String
0x1800ba29c  test    rcx, rcx
0x1800ba29f  jz      short loc_1800BA2BC
0x1800ba2a1  call    cs:__imp__wtoi
0x1800ba2a8  nop     dword ptr [rax+rax+00h]
0x1800ba2ad  mov     [rsp+1A8h+var_90], eax
0x1800ba2b4  mov     [rsp+1A8h+var_8C], 1
0x1800ba2bc  mov     rax, [rsi]
0x1800ba2bf  lea     r9, [rsp+1A8h+String]
0x1800ba2c4  lea     r8, aAutomaticdispl; "AutomaticDisplayAdjustment"
0x1800ba2cb  mov     edx, r15d
0x1800ba2ce  mov     rcx, rsi
0x1800ba2d1  mov     rax, [rax+18h]
0x1800ba2d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba2da  test    eax, eax
0x1800ba2dc  jnz     short loc_1800BA303
0x1800ba2de  mov     rcx, [rsp+1A8h+String]; String
0x1800ba2e3  test    rcx, rcx
0x1800ba2e6  jz      short loc_1800BA303
0x1800ba2e8  call    cs:__imp__wtoi
0x1800ba2ef  nop     dword ptr [rax+rax+00h]
0x1800ba2f4  mov     [rsp+1A8h+var_88], eax
0x1800ba2fb  mov     [rsp+1A8h+var_84], 1
0x1800ba303  mov     rax, [rsi]
0x1800ba306  lea     r9, [rsp+1A8h+String]
0x1800ba30b  lea     r8, aBrightnessbutt; "BrightnessButtonDisabled"
0x1800ba312  mov     edx, r15d
0x1800ba315  mov     rcx, rsi
0x1800ba318  mov     rax, [rax+18h]
0x1800ba31c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba321  test    eax, eax
0x1800ba323  jnz     short loc_1800BA34A
0x1800ba325  mov     rcx, [rsp+1A8h+String]; String
0x1800ba32a  test    rcx, rcx
0x1800ba32d  jz      short loc_1800BA34A
0x1800ba32f  call    cs:__imp__wtoi
0x1800ba336  nop     dword ptr [rax+rax+00h]
0x1800ba33b  mov     [rsp+1A8h+var_80], eax
0x1800ba342  mov     [rsp+1A8h+var_7C], 1
0x1800ba34a  mov     rax, [rsi]
0x1800ba34d  lea     r9, [rsp+1A8h+String]
0x1800ba352  lea     r8, aConfiguremovin; "ConfigureMovingPlatform"
0x1800ba359  mov     edx, r15d
0x1800ba35c  mov     rcx, rsi
0x1800ba35f  mov     rax, [rax+18h]
0x1800ba363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba368  test    eax, eax
0x1800ba36a  jnz     short loc_1800BA391
0x1800ba36c  mov     rcx, [rsp+1A8h+String]; String
0x1800ba371  test    rcx, rcx
0x1800ba374  jz      short loc_1800BA391
0x1800ba376  call    cs:__imp__wtoi
0x1800ba37d  nop     dword ptr [rax+rax+00h]
0x1800ba382  mov     [rsp+1A8h+var_78], eax
0x1800ba389  mov     [rsp+1A8h+var_74], 1
0x1800ba391  mov     rax, [rsi]
0x1800ba394  lea     r9, [rsp+1A8h+String]
0x1800ba399  lea     r8, aEyetrackingcal; "EyeTrackingCalibrationPrompt"
0x1800ba3a0  mov     edx, r15d
0x1800ba3a3  mov     rcx, rsi
0x1800ba3a6  mov     rax, [rax+18h]
0x1800ba3aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba3af  test    eax, eax
0x1800ba3b1  jnz     short loc_1800BA3D8
0x1800ba3b3  mov     rcx, [rsp+1A8h+String]; String
0x1800ba3b8  test    rcx, rcx
0x1800ba3bb  jz      short loc_1800BA3D8
0x1800ba3bd  call    cs:__imp__wtoi
0x1800ba3c4  nop     dword ptr [rax+rax+00h]
0x1800ba3c9  mov     [rsp+1A8h+var_70], eax
0x1800ba3d0  mov     [rsp+1A8h+var_6C], 1
0x1800ba3d8  mov     rax, [rsi]
0x1800ba3db  lea     r9, [rsp+1A8h+String]
0x1800ba3e0  lea     r8, aFallbackdiagno; "FallbackDiagnostics"
0x1800ba3e7  mov     edx, r15d
0x1800ba3ea  mov     rcx, rsi
0x1800ba3ed  mov     rax, [rax+18h]
0x1800ba3f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba3f6  test    eax, eax
0x1800ba3f8  jnz     short loc_1800BA41F
0x1800ba3fa  mov     rcx, [rsp+1A8h+String]; String
0x1800ba3ff  test    rcx, rcx
0x1800ba402  jz      short loc_1800BA41F
0x1800ba404  call    cs:__imp__wtoi
0x1800ba40b  nop     dword ptr [rax+rax+00h]
0x1800ba410  mov     [rsp+1A8h+var_68], eax
0x1800ba417  mov     [rsp+1A8h+var_64], 1
0x1800ba41f  mov     rax, [rsi]
0x1800ba422  lea     r9, [rsp+1A8h+String]
0x1800ba427  lea     r8, aHeadtrackingmo; "HeadTrackingMode"
0x1800ba42e  mov     edx, r15d
0x1800ba431  mov     rcx, rsi
0x1800ba434  mov     rax, [rax+18h]
0x1800ba438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba43d  test    eax, eax
0x1800ba43f  jnz     short loc_1800BA466
0x1800ba441  mov     rcx, [rsp+1A8h+String]; String
0x1800ba446  test    rcx, rcx
0x1800ba449  jz      short loc_1800BA466
0x1800ba44b  call    cs:__imp__wtoi
0x1800ba452  nop     dword ptr [rax+rax+00h]
0x1800ba457  mov     [rsp+1A8h+var_60], eax
0x1800ba45e  mov     [rsp+1A8h+var_5C], 1
  ... truncated ...
```
