# MDM_Policy_Config01_MixedReality02_InvokeEnumerateInstances

- ea: `0x1800ba8e4`
- end: `0x1800bafd8`
- name: `MDM_Policy_Config01_MixedReality02_InvokeEnumerateInstances`
- size: `1780`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b9f60`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800ba8e4`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800babf6`
- `msvcrt!_wtoi` at `0x1800bac37`
- `msvcrt!_wtoi` at `0x1800bac78`
- `msvcrt!_wtoi` at `0x1800bacb9`
- `msvcrt!_wtoi` at `0x1800bacfa`
- `msvcrt!_wtoi` at `0x1800bad3b`
- `msvcrt!_wtoi` at `0x1800bad7c`
- `msvcrt!_wtoi` at `0x1800badbd`
- `msvcrt!_wtoi` at `0x1800badfe`
- `msvcrt!_wtoi` at `0x1800bae3f`
- `msvcrt!_wtoi` at `0x1800bae80`
- `msvcrt!_wtoi` at `0x1800baec1`
- `msvcrt!_wtoi` at `0x1800babf6`
- `msvcrt!_wtoi` at `0x1800bac37`
- `msvcrt!_wtoi` at `0x1800bac78`
- `msvcrt!_wtoi` at `0x1800bacb9`
- `msvcrt!_wtoi` at `0x1800bacfa`
- `msvcrt!_wtoi` at `0x1800bad3b`
- `msvcrt!_wtoi` at `0x1800bad7c`
- `msvcrt!_wtoi` at `0x1800badbd`
- `msvcrt!_wtoi` at `0x1800badfe`
- `msvcrt!_wtoi` at `0x1800bae3f`
- `msvcrt!_wtoi` at `0x1800bae80`
- `msvcrt!_wtoi` at `0x1800baec1`

## string_xrefs

- `0x1800babd2`: `AADGroupMembershipCacheValidityInDays`
- `0x1800bac13`: `AllowLaunchUriInSingleAppKiosk`
- `0x1800bacd6`: `ConfigureMovingPlatform`
- `0x1800bab38`: `./Vendor/MSFT/Policy/Config`
- `0x1800ba95f`: `MDM_Policy_Config01_MixedReality02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_MixedReality02_InvokeEnumerateInstances(MI_Context *self, char a2)
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
    v7 = CreateRequestHandlerInstance(
           (__int64)self,
           0,
           0,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_MixedReality02_NodeList,
           0xEu,
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_MixedReality02_rtti, &instance);
              if ( v7 )
              {
                v6 = v14;
                if ( v14 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_82;
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
                      L"MixedReality",
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
                        L"AADGroupMembershipCacheValidityInDays",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowLaunchUriInSingleAppKiosk",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AutomaticDisplayAdjustment",
                        &String)
                  && String )
                {
                  v27 = _wtoi(String);
                  v28 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"BrightnessButtonDisabled",
                        &String)
                  && String )
                {
                  v29 = _wtoi(String);
                  v30 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureMovingPlatform",
                        &String)
                  && String )
                {
                  v31 = _wtoi(String);
                  v32 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EyeTrackingCalibrationPrompt",
                        &String)
                  && String )
                {
                  v33 = _wtoi(String);
                  v34 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"FallbackDiagnostics",
                        &String)
                  && String )
                {
                  v35 = _wtoi(String);
                  v36 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"HeadTrackingMode",
                        &String)
                  && String )
                {
                  v37 = _wtoi(String);
                  v38 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ManualDownDirectionDisabled",
                        &String)
                  && String )
                {
                  v39 = _wtoi(String);
                  v40 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"MicrophoneDisabled",
                        &String)
                  && String )
                {
                  v41 = _wtoi(String);
                  v42 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"VisitorAutoLogon",
                        &String)
                  && String )
                {
                  v43 = _wtoi(String);
                  v44 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
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
  return v7;
}

```

## disassembly

```asm
0x1800ba8e4  mov     [rsp+arg_8], rbx
0x1800ba8e9  mov     [rsp+arg_10], rsi
0x1800ba8ee  push    rdi
0x1800ba8ef  push    r12
0x1800ba8f1  push    r13
0x1800ba8f3  push    r14
0x1800ba8f5  push    r15
0x1800ba8f7  sub     rsp, 180h
0x1800ba8fe  mov     rax, cs:__security_cookie
0x1800ba905  xor     rax, rsp
0x1800ba908  mov     [rsp+1A8h+var_38], rax
0x1800ba910  mov     r13b, dl
0x1800ba913  mov     r12, rcx
0x1800ba916  xor     edx, edx; Val
0x1800ba918  mov     r8d, 0C0h; Size
0x1800ba91e  lea     rcx, [rsp+1A8h+instance]; void *
0x1800ba926  call    memset_0
0x1800ba92b  xor     edi, edi
0x1800ba92d  mov     [rsp+1A8h+var_168], dil
0x1800ba932  mov     [rsp+1A8h+String], rdi
0x1800ba937  mov     [rsp+1A8h+var_120], edi
0x1800ba93e  mov     [rsp+1A8h+var_11C], dil
0x1800ba946  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800ba94d  mov     [rsp+1A8h+var_150], rax
0x1800ba952  lea     rax, [rsp+1A8h+var_120]
0x1800ba95a  mov     [rsp+1A8h+var_148], rax
0x1800ba95f  lea     rax, aMdmPolicyConfi_149; "MDM_Policy_Config01_MixedReality02"
0x1800ba966  mov     [rsp+1A8h+var_140], rax
0x1800ba96b  lea     rcx, [rsp+1A8h+var_120]
0x1800ba973  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800ba978  mov     eax, cs:dword_180380B68
0x1800ba97e  cmp     eax, 5
0x1800ba981  jbe     short loc_1800BA9F3
0x1800ba983  mov     rdx, 200000000000h
0x1800ba98d  lea     rcx, dword_180380B68
0x1800ba994  call    _tlgKeywordOn
0x1800ba999  test    al, al
0x1800ba99b  jz      short loc_1800BA9F3
0x1800ba99d  cmp     [rsp+1A8h+var_11C], dil
0x1800ba9a5  jz      short loc_1800BA9D5
0x1800ba9a7  cmp     [rsp+1A8h+var_108], edi
0x1800ba9ae  jnz     short loc_1800BA9CB
0x1800ba9b0  cmp     [rsp+1A8h+var_104], edi
0x1800ba9b7  jnz     short loc_1800BA9CB
0x1800ba9b9  cmp     [rsp+1A8h+var_100], edi
0x1800ba9c0  jnz     short loc_1800BA9CB
0x1800ba9c2  cmp     [rsp+1A8h+var_FC], edi
0x1800ba9c9  jz      short loc_1800BA9D5
0x1800ba9cb  lea     r9, [rsp+1A8h+var_108]
0x1800ba9d3  jmp     short loc_1800BA9D8
0x1800ba9d5  mov     r9, rdi
0x1800ba9d8  lea     r8, [rsp+1A8h+var_118]
0x1800ba9e0  lea     rdx, byte_1803595D9
0x1800ba9e7  lea     rcx, dword_180380B68
0x1800ba9ee  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800ba9f3  lea     rcx, [rsp+1A8h+var_150]; this
0x1800ba9f8  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800ba9fd  nop
0x1800ba9fe  mov     [rsp+1A8h+var_158], rdi
0x1800baa03  lea     rax, [rsp+1A8h+var_158]
0x1800baa08  mov     [rsp+1A8h+var_178], rax
0x1800baa0d  mov     [rsp+1A8h+var_180], 2
0x1800baa15  mov     [rsp+1A8h+var_188], 0Eh
0x1800baa1d  lea     r9, ?MDM_Policy_Config01_MixedReality02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_MixedReality02_NodeList
0x1800baa24  xor     r8d, r8d
0x1800baa27  xor     edx, edx
0x1800baa29  mov     rcx, r12
0x1800baa2c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800baa31  mov     r14d, eax
0x1800baa34  test    eax, eax
0x1800baa36  jz      short loc_1800BAA3D
0x1800baa38  jmp     loc_1800BAF38
0x1800baa3d  lea     rbx, [rsp+1A8h+var_158]
0x1800baa42  mov     [rsp+1A8h+var_130], rbx
0x1800baa47  mov     r15d, 1
0x1800baa4d  mov     [rsp+1A8h+var_128], r15b
0x1800baa55  mov     rsi, [rsp+1A8h+var_158]
0x1800baa5a  test    rsi, rsi
0x1800baa5d  jnz     short loc_1800BAA67
0x1800baa5f  mov     r14d, r15d
0x1800baa62  jmp     loc_1800BAF38
0x1800baa67  mov     rax, [rsi]
0x1800baa6a  mov     rcx, rsi
0x1800baa6d  mov     rax, [rax+10h]
0x1800baa71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baa76  mov     r14d, eax
0x1800baa79  test    eax, eax
0x1800baa7b  jz      short loc_1800BAA9B
0x1800baa7d  mov     rcx, [rsp+1A8h+var_158]
0x1800baa82  test    rcx, rcx
0x1800baa85  jz      short loc_1800BAA96
0x1800baa87  mov     rax, [rcx]
0x1800baa8a  mov     edx, r15d
0x1800baa8d  mov     rax, [rax]
0x1800baa90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baa95  nop
0x1800baa96  jmp     loc_1800BAF38
0x1800baa9b  mov     rax, [rsi]
0x1800baa9e  mov     rcx, rsi
0x1800baaa1  mov     rax, [rax+8]
0x1800baaa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baaaa  mov     r14d, eax
0x1800baaad  test    eax, eax
0x1800baaaf  jz      short loc_1800BAACF
0x1800baab1  mov     rcx, [rsp+1A8h+var_158]
0x1800baab6  test    rcx, rcx
0x1800baab9  jz      short loc_1800BAACA
0x1800baabb  mov     rax, [rcx]
0x1800baabe  mov     edx, r15d
0x1800baac1  mov     rax, [rax]
0x1800baac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baac9  nop
0x1800baaca  jmp     loc_1800BAF38
0x1800baacf  mov     r15d, edi
0x1800baad2  mov     rax, [rsi+108h]
0x1800baad9  sub     rax, [rsi+100h]
0x1800baae0  sar     rax, 4
0x1800baae4  cmp     r15d, eax
0x1800baae7  jnb     loc_1800BAF00
0x1800baaed  lea     r8, [rsp+1A8h+instance]; instance
0x1800baaf5  lea     rdx, MDM_Policy_Config01_MixedReality02_rtti; classDecl
0x1800baafc  mov     rcx, r12; context
0x1800baaff  call    MI_Context_ConstructInstance
0x1800bab04  mov     r14d, eax
0x1800bab07  test    eax, eax
0x1800bab09  jz      short loc_1800BAB2B
0x1800bab0b  mov     rcx, [rbx]
0x1800bab0e  test    rcx, rcx
0x1800bab11  jz      short loc_1800BAB26
0x1800bab13  mov     rax, [rcx]
0x1800bab16  mov     edx, 1
0x1800bab1b  mov     rax, [rax]
0x1800bab1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bab23  mov     [rbx], rdi
0x1800bab26  jmp     loc_1800BAF38
0x1800bab2b  mov     [rsp+1A8h+var_168], 1
0x1800bab30  mov     rax, [rsi]
0x1800bab33  lea     r9, [rsp+1A8h+String]
0x1800bab38  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800bab3f  mov     edx, r15d
0x1800bab42  mov     rcx, rsi
0x1800bab45  mov     rax, [rax+18h]
0x1800bab49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bab4e  test    eax, eax
0x1800bab50  jnz     short loc_1800BAB69
0x1800bab52  mov     rdx, [rsp+1A8h+String]
0x1800bab57  test    rdx, rdx
0x1800bab5a  jz      short loc_1800BAB69
0x1800bab5c  lea     rcx, [rsp+1A8h+instance]
0x1800bab64  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800bab69  mov     rax, [rsi]
0x1800bab6c  lea     r9, [rsp+1A8h+String]
0x1800bab71  lea     r8, aMixedreality; "MixedReality"
0x1800bab78  mov     edx, r15d
0x1800bab7b  mov     rcx, rsi
0x1800bab7e  mov     rax, [rax+18h]
0x1800bab82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bab87  test    eax, eax
0x1800bab89  jnz     short loc_1800BABA2
0x1800bab8b  mov     rdx, [rsp+1A8h+String]
0x1800bab90  test    rdx, rdx
0x1800bab93  jz      short loc_1800BABA2
0x1800bab95  lea     rcx, [rsp+1A8h+instance]
0x1800bab9d  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800baba2  cmp     r13b, 1
0x1800baba6  jnz     short loc_1800BABCA
0x1800baba8  lea     rdx, [rsp+1A8h+instance]
0x1800babb0  mov     rcx, r12; self
0x1800babb3  call    MI_Instance_Destruct
0x1800babb8  lea     rcx, [rsp+1A8h+instance]; self
0x1800babc0  call    MI_Instance_Destruct
0x1800babc5  jmp     loc_1800BAEF3
0x1800babca  mov     rax, [rsi]
0x1800babcd  lea     r9, [rsp+1A8h+String]
0x1800babd2  lea     r8, aAadgroupmember; "AADGroupMembershipCacheValidityInDays"
0x1800babd9  mov     edx, r15d
0x1800babdc  mov     rcx, rsi
0x1800babdf  mov     rax, [rax+18h]
0x1800babe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800babe8  test    eax, eax
0x1800babea  jnz     short loc_1800BAC0B
0x1800babec  mov     rcx, [rsp+1A8h+String]; String
0x1800babf1  test    rcx, rcx
0x1800babf4  jz      short loc_1800BAC0B
0x1800babf6  call    cs:__imp__wtoi
0x1800babfc  mov     [rsp+1A8h+var_98], eax
0x1800bac03  mov     [rsp+1A8h+var_94], 1
0x1800bac0b  mov     rax, [rsi]
0x1800bac0e  lea     r9, [rsp+1A8h+String]
0x1800bac13  lea     r8, aAllowlaunchuri; "AllowLaunchUriInSingleAppKiosk"
0x1800bac1a  mov     edx, r15d
0x1800bac1d  mov     rcx, rsi
0x1800bac20  mov     rax, [rax+18h]
0x1800bac24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bac29  test    eax, eax
0x1800bac2b  jnz     short loc_1800BAC4C
0x1800bac2d  mov     rcx, [rsp+1A8h+String]; String
0x1800bac32  test    rcx, rcx
0x1800bac35  jz      short loc_1800BAC4C
0x1800bac37  call    cs:__imp__wtoi
0x1800bac3d  mov     [rsp+1A8h+var_90], eax
0x1800bac44  mov     [rsp+1A8h+var_8C], 1
0x1800bac4c  mov     rax, [rsi]
0x1800bac4f  lea     r9, [rsp+1A8h+String]
0x1800bac54  lea     r8, aAutomaticdispl; "AutomaticDisplayAdjustment"
0x1800bac5b  mov     edx, r15d
0x1800bac5e  mov     rcx, rsi
0x1800bac61  mov     rax, [rax+18h]
0x1800bac65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bac6a  test    eax, eax
0x1800bac6c  jnz     short loc_1800BAC8D
0x1800bac6e  mov     rcx, [rsp+1A8h+String]; String
0x1800bac73  test    rcx, rcx
0x1800bac76  jz      short loc_1800BAC8D
0x1800bac78  call    cs:__imp__wtoi
0x1800bac7e  mov     [rsp+1A8h+var_88], eax
0x1800bac85  mov     [rsp+1A8h+var_84], 1
0x1800bac8d  mov     rax, [rsi]
0x1800bac90  lea     r9, [rsp+1A8h+String]
0x1800bac95  lea     r8, aBrightnessbutt; "BrightnessButtonDisabled"
0x1800bac9c  mov     edx, r15d
0x1800bac9f  mov     rcx, rsi
0x1800baca2  mov     rax, [rax+18h]
0x1800baca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bacab  test    eax, eax
0x1800bacad  jnz     short loc_1800BACCE
0x1800bacaf  mov     rcx, [rsp+1A8h+String]; String
0x1800bacb4  test    rcx, rcx
0x1800bacb7  jz      short loc_1800BACCE
0x1800bacb9  call    cs:__imp__wtoi
0x1800bacbf  mov     [rsp+1A8h+var_80], eax
0x1800bacc6  mov     [rsp+1A8h+var_7C], 1
0x1800bacce  mov     rax, [rsi]
0x1800bacd1  lea     r9, [rsp+1A8h+String]
0x1800bacd6  lea     r8, aConfiguremovin; "ConfigureMovingPlatform"
0x1800bacdd  mov     edx, r15d
0x1800bace0  mov     rcx, rsi
0x1800bace3  mov     rax, [rax+18h]
0x1800bace7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bacec  test    eax, eax
0x1800bacee  jnz     short loc_1800BAD0F
0x1800bacf0  mov     rcx, [rsp+1A8h+String]; String
0x1800bacf5  test    rcx, rcx
0x1800bacf8  jz      short loc_1800BAD0F
0x1800bacfa  call    cs:__imp__wtoi
0x1800bad00  mov     [rsp+1A8h+var_78], eax
0x1800bad07  mov     [rsp+1A8h+var_74], 1
0x1800bad0f  mov     rax, [rsi]
0x1800bad12  lea     r9, [rsp+1A8h+String]
0x1800bad17  lea     r8, aEyetrackingcal; "EyeTrackingCalibrationPrompt"
0x1800bad1e  mov     edx, r15d
0x1800bad21  mov     rcx, rsi
0x1800bad24  mov     rax, [rax+18h]
0x1800bad28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bad2d  test    eax, eax
0x1800bad2f  jnz     short loc_1800BAD50
0x1800bad31  mov     rcx, [rsp+1A8h+String]; String
0x1800bad36  test    rcx, rcx
0x1800bad39  jz      short loc_1800BAD50
0x1800bad3b  call    cs:__imp__wtoi
0x1800bad41  mov     [rsp+1A8h+var_70], eax
0x1800bad48  mov     [rsp+1A8h+var_6C], 1
0x1800bad50  mov     rax, [rsi]
0x1800bad53  lea     r9, [rsp+1A8h+String]
0x1800bad58  lea     r8, aFallbackdiagno; "FallbackDiagnostics"
0x1800bad5f  mov     edx, r15d
0x1800bad62  mov     rcx, rsi
0x1800bad65  mov     rax, [rax+18h]
0x1800bad69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bad6e  test    eax, eax
0x1800bad70  jnz     short loc_1800BAD91
0x1800bad72  mov     rcx, [rsp+1A8h+String]; String
0x1800bad77  test    rcx, rcx
0x1800bad7a  jz      short loc_1800BAD91
0x1800bad7c  call    cs:__imp__wtoi
0x1800bad82  mov     [rsp+1A8h+var_68], eax
0x1800bad89  mov     [rsp+1A8h+var_64], 1
0x1800bad91  mov     rax, [rsi]
0x1800bad94  lea     r9, [rsp+1A8h+String]
0x1800bad99  lea     r8, aHeadtrackingmo; "HeadTrackingMode"
0x1800bada0  mov     edx, r15d
0x1800bada3  mov     rcx, rsi
0x1800bada6  mov     rax, [rax+18h]
0x1800badaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800badaf  test    eax, eax
0x1800badb1  jnz     short loc_1800BADD2
0x1800badb3  mov     rcx, [rsp+1A8h+String]; String
0x1800badb8  test    rcx, rcx
0x1800badbb  jz      short loc_1800BADD2
0x1800badbd  call    cs:__imp__wtoi
0x1800badc3  mov     [rsp+1A8h+var_60], eax
0x1800badca  mov     [rsp+1A8h+var_5C], 1
0x1800badd2  mov     rax, [rsi]
0x1800badd5  lea     r9, [rsp+1A8h+String]
0x1800badda  lea     r8, aManualdowndire; "ManualDownDirectionDisabled"
0x1800bade1  mov     edx, r15d
0x1800bade4  mov     rcx, rsi
0x1800bade7  mov     rax, [rax+18h]
0x1800badeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800badf0  test    eax, eax
  ... truncated ...
```
