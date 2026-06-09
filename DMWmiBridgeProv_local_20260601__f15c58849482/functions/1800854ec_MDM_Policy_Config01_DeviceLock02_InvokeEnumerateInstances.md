# MDM_Policy_Config01_DeviceLock02_InvokeEnumerateInstances

- ea: `0x1800854ec`
- end: `0x180085d0d`
- name: `MDM_Policy_Config01_DeviceLock02_InvokeEnumerateInstances`
- size: `2081`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180084a80`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005048`
- `0x180005080`
- `0x1800050f0`
- `0x180005160`
- `0x180005198`
- `0x1800051d0`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800854ec`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800857fe`
- `msvcrt!_wtoi` at `0x1800858b7`
- `msvcrt!_wtoi` at `0x180085970`
- `msvcrt!_wtoi` at `0x1800859b7`
- `msvcrt!_wtoi` at `0x1800859fe`
- `msvcrt!_wtoi` at `0x180085a45`
- `msvcrt!_wtoi` at `0x180085a8c`
- `msvcrt!_wtoi` at `0x180085ad3`
- `msvcrt!_wtoi` at `0x180085b1a`
- `msvcrt!_wtoi` at `0x180085b61`
- `msvcrt!_wtoi` at `0x180085ba8`
- `msvcrt!_wtoi` at `0x180085bef`
- `msvcrt!_wtoi` at `0x1800857fe`
- `msvcrt!_wtoi` at `0x1800858b7`
- `msvcrt!_wtoi` at `0x180085970`
- `msvcrt!_wtoi` at `0x1800859b7`
- `msvcrt!_wtoi` at `0x1800859fe`
- `msvcrt!_wtoi` at `0x180085a45`
- `msvcrt!_wtoi` at `0x180085a8c`
- `msvcrt!_wtoi` at `0x180085ad3`
- `msvcrt!_wtoi` at `0x180085b1a`
- `msvcrt!_wtoi` at `0x180085b61`
- `msvcrt!_wtoi` at `0x180085ba8`
- `msvcrt!_wtoi` at `0x180085bef`

## string_xrefs

- `0x1800857da`: `AllowScreenTimeoutWhileLockedUserConfig`
- `0x180085aaf`: `MinDevicePasswordComplexCharacters`
- `0x180085b84`: `MaxDevicePasswordFailedAttempts`
- `0x180085740`: `./Vendor/MSFT/Policy/Config`
- `0x180085567`: `MDM_Policy_Config01_DeviceLock02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_DeviceLock02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  MI_Result v7; // r15d
  _QWORD *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+48h] [rbp-1A0h] BYREF
  _QWORD *v14; // [rsp+50h] [rbp-198h] BYREF
  _QWORD v15[3]; // [rsp+58h] [rbp-190h] BYREF
  const exception *v16[2]; // [rsp+70h] [rbp-178h] BYREF
  char v17; // [rsp+80h] [rbp-168h]
  int v18; // [rsp+88h] [rbp-160h] BYREF
  char v19; // [rsp+8Ch] [rbp-15Ch]
  _BYTE v20[16]; // [rsp+90h] [rbp-158h] BYREF
  _DWORD v21[4]; // [rsp+A0h] [rbp-148h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-138h] BYREF
  int v23; // [rsp+110h] [rbp-D8h]
  char v24; // [rsp+114h] [rbp-D4h]
  int v25; // [rsp+138h] [rbp-B0h]
  char v26; // [rsp+13Ch] [rbp-ACh]
  int v27; // [rsp+160h] [rbp-88h]
  char v28; // [rsp+164h] [rbp-84h]
  int v29; // [rsp+168h] [rbp-80h]
  char v30; // [rsp+16Ch] [rbp-7Ch]
  int v31; // [rsp+170h] [rbp-78h]
  char v32; // [rsp+174h] [rbp-74h]
  int v33; // [rsp+178h] [rbp-70h]
  char v34; // [rsp+17Ch] [rbp-6Ch]
  int v35; // [rsp+180h] [rbp-68h]
  char v36; // [rsp+184h] [rbp-64h]
  int v37; // [rsp+188h] [rbp-60h]
  char v38; // [rsp+18Ch] [rbp-5Ch]
  int v39; // [rsp+190h] [rbp-58h]
  char v40; // [rsp+194h] [rbp-54h]
  int v41; // [rsp+198h] [rbp-50h]
  char v42; // [rsp+19Ch] [rbp-4Ch]
  int v43; // [rsp+1A0h] [rbp-48h]
  char v44; // [rsp+1A4h] [rbp-44h]
  int v45; // [rsp+1A8h] [rbp-40h]
  char v46; // [rsp+1ACh] [rbp-3Ch]

  memset_0(&instance, 0, 0x100u);
  String = 0;
  v18 = 0;
  v19 = 0;
  v15[0] = &TelemetryEventWriter::`vftable';
  v15[1] = &v18;
  v15[2] = "MDM_Policy_Config01_DeviceLock02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v18);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v19 && (v21[0] || v21[1] || v21[2] || v21[3]) )
      v5 = v21;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      word_180359162,
      v20,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v15, v4);
  try
  {
    v14 = 0;
    v7 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Config01_DeviceLock02_NodeList, 18, 2, &v14);
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_DeviceLock02_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v14;
                if ( v14 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_94;
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
                      L"DeviceLock",
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
                        L"AllowScreenTimeoutWhileLockedUserConfig",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EnforceLockScreenAndLogonImage",
                        &String)
                  && String )
                {
                  MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"EnforceLockScreenProvider",
                        &String)
                  && String )
                {
                  MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"MinimumPasswordAge",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"PreventEnablingLockScreenCamera",
                        &String)
                  && String )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"PreventLockScreenSlideShow",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_DnsSuffix(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ScreenTimeoutWhileLocked",
                        &String)
                  && String )
                {
                  v27 = _wtoi(String);
                  v28 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DevicePasswordEnabled",
                        &String)
                  && String )
                {
                  v29 = _wtoi(String);
                  v30 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowSimpleDevicePassword",
                        &String)
                  && String )
                {
                  v31 = _wtoi(String);
                  v32 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"MinDevicePasswordLength",
                        &String)
                  && String )
                {
                  v33 = _wtoi(String);
                  v34 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AlphanumericDevicePasswordRequired",
                        &String)
                  && String )
                {
                  v35 = _wtoi(String);
                  v36 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"MinDevicePasswordComplexCharacters",
                        &String)
                  && String )
                {
                  v37 = _wtoi(String);
                  v38 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DevicePasswordExpiration",
                        &String)
                  && String )
                {
                  v39 = _wtoi(String);
                  v40 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"DevicePasswordHistory",
                        &String)
                  && String )
                {
                  v41 = _wtoi(String);
                  v42 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"MaxDevicePasswordFailedAttempts",
                        &String)
                  && String )
                {
                  v43 = _wtoi(String);
                  v44 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"MaxInactivityTimeDeviceLock",
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
LABEL_94:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v15, "EnumerateInstancesEnd", v7);
  v18 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_18033C32F,
      v20,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800854ec  mov     [rsp+arg_8], rbx
0x1800854f1  mov     [rsp+arg_10], rsi
0x1800854f6  push    rdi
0x1800854f7  push    r12
0x1800854f9  push    r13
0x1800854fb  push    r14
0x1800854fd  push    r15
0x1800854ff  sub     rsp, 1C0h
0x180085506  mov     rax, cs:__security_cookie
0x18008550d  xor     rax, rsp
0x180085510  mov     [rsp+1E8h+var_38], rax
0x180085518  mov     r13b, dl
0x18008551b  mov     r12, rcx
0x18008551e  xor     edx, edx; Val
0x180085520  mov     r8d, 100h; Size
0x180085526  lea     rcx, [rsp+1E8h+instance]; void *
0x18008552e  call    memset_0
0x180085533  xor     edi, edi
0x180085535  mov     [rsp+1E8h+var_1A8], dil
0x18008553a  mov     [rsp+1E8h+String], rdi
0x18008553f  mov     [rsp+1E8h+var_160], edi
0x180085546  mov     [rsp+1E8h+var_15C], dil
0x18008554e  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180085555  mov     [rsp+1E8h+var_190], rax
0x18008555a  lea     rax, [rsp+1E8h+var_160]
0x180085562  mov     [rsp+1E8h+var_188], rax
0x180085567  lea     rax, aMdmPolicyConfi_133; "MDM_Policy_Config01_DeviceLock02"
0x18008556e  mov     [rsp+1E8h+var_180], rax
0x180085573  lea     rcx, [rsp+1E8h+var_160]
0x18008557b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180085580  mov     eax, cs:dword_180380B68
0x180085586  cmp     eax, 5
0x180085589  jbe     short loc_1800855FB
0x18008558b  mov     rdx, 200000000000h
0x180085595  lea     rcx, dword_180380B68
0x18008559c  call    _tlgKeywordOn
0x1800855a1  test    al, al
0x1800855a3  jz      short loc_1800855FB
0x1800855a5  cmp     [rsp+1E8h+var_15C], dil
0x1800855ad  jz      short loc_1800855DD
0x1800855af  cmp     [rsp+1E8h+var_148], edi
0x1800855b6  jnz     short loc_1800855D3
0x1800855b8  cmp     [rsp+1E8h+var_144], edi
0x1800855bf  jnz     short loc_1800855D3
0x1800855c1  cmp     [rsp+1E8h+var_140], edi
0x1800855c8  jnz     short loc_1800855D3
0x1800855ca  cmp     [rsp+1E8h+var_13C], edi
0x1800855d1  jz      short loc_1800855DD
0x1800855d3  lea     r9, [rsp+1E8h+var_148]
0x1800855db  jmp     short loc_1800855E0
0x1800855dd  mov     r9, rdi
0x1800855e0  lea     r8, [rsp+1E8h+var_158]
0x1800855e8  lea     rdx, word_180359162
0x1800855ef  lea     rcx, dword_180380B68
0x1800855f6  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800855fb  lea     rcx, [rsp+1E8h+var_190]; this
0x180085600  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x180085605  nop
0x180085606  mov     [rsp+1E8h+var_198], rdi
0x18008560b  lea     rax, [rsp+1E8h+var_198]
0x180085610  mov     [rsp+1E8h+var_1B8], rax
0x180085615  mov     [rsp+1E8h+var_1C0], 2
0x18008561d  mov     [rsp+1E8h+var_1C8], 12h
0x180085625  lea     r9, ?MDM_Policy_Config01_DeviceLock02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_DeviceLock02_NodeList
0x18008562c  xor     r8d, r8d
0x18008562f  xor     edx, edx
0x180085631  mov     rcx, r12
0x180085634  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180085639  mov     r15d, eax
0x18008563c  test    eax, eax
0x18008563e  jz      short loc_180085645
0x180085640  jmp     loc_180085C6C
0x180085645  lea     rbx, [rsp+1E8h+var_198]
0x18008564a  mov     [rsp+1E8h+var_170], rbx
0x18008564f  mov     r14d, 1
0x180085655  mov     [rsp+1E8h+var_168], r14b
0x18008565d  mov     rsi, [rsp+1E8h+var_198]
0x180085662  test    rsi, rsi
0x180085665  jnz     short loc_18008566F
0x180085667  mov     r15d, r14d
0x18008566a  jmp     loc_180085C6C
0x18008566f  mov     rax, [rsi]
0x180085672  mov     rcx, rsi
0x180085675  mov     rax, [rax+10h]
0x180085679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008567e  mov     r15d, eax
0x180085681  test    eax, eax
0x180085683  jz      short loc_1800856A3
0x180085685  mov     rcx, [rsp+1E8h+var_198]
0x18008568a  test    rcx, rcx
0x18008568d  jz      short loc_18008569E
0x18008568f  mov     rax, [rcx]
0x180085692  mov     edx, r14d
0x180085695  mov     rax, [rax]
0x180085698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008569d  nop
0x18008569e  jmp     loc_180085C6C
0x1800856a3  mov     rax, [rsi]
0x1800856a6  mov     rcx, rsi
0x1800856a9  mov     rax, [rax+8]
0x1800856ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800856b2  mov     r15d, eax
0x1800856b5  test    eax, eax
0x1800856b7  jz      short loc_1800856D7
0x1800856b9  mov     rcx, [rsp+1E8h+var_198]
0x1800856be  test    rcx, rcx
0x1800856c1  jz      short loc_1800856D2
0x1800856c3  mov     rax, [rcx]
0x1800856c6  mov     edx, r14d
0x1800856c9  mov     rax, [rax]
0x1800856cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800856d1  nop
0x1800856d2  jmp     loc_180085C6C
0x1800856d7  mov     r14d, edi
0x1800856da  mov     rax, [rsi+108h]
0x1800856e1  sub     rax, [rsi+100h]
0x1800856e8  sar     rax, 4
0x1800856ec  cmp     r14d, eax
0x1800856ef  jnb     loc_180085C34
0x1800856f5  lea     r8, [rsp+1E8h+instance]; instance
0x1800856fd  lea     rdx, MDM_Policy_Config01_DeviceLock02_rtti; classDecl
0x180085704  mov     rcx, r12; context
0x180085707  call    MI_Context_ConstructInstance
0x18008570c  mov     r15d, eax
0x18008570f  test    eax, eax
0x180085711  jz      short loc_180085733
0x180085713  mov     rcx, [rbx]
0x180085716  test    rcx, rcx
0x180085719  jz      short loc_18008572E
0x18008571b  mov     rax, [rcx]
0x18008571e  mov     edx, 1
0x180085723  mov     rax, [rax]
0x180085726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008572b  mov     [rbx], rdi
0x18008572e  jmp     loc_180085C6C
0x180085733  mov     [rsp+1E8h+var_1A8], 1
0x180085738  mov     rax, [rsi]
0x18008573b  lea     r9, [rsp+1E8h+String]
0x180085740  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x180085747  mov     edx, r14d
0x18008574a  mov     rcx, rsi
0x18008574d  mov     rax, [rax+18h]
0x180085751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085756  test    eax, eax
0x180085758  jnz     short loc_180085771
0x18008575a  mov     rdx, [rsp+1E8h+String]
0x18008575f  test    rdx, rdx
0x180085762  jz      short loc_180085771
0x180085764  lea     rcx, [rsp+1E8h+instance]
0x18008576c  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180085771  mov     rax, [rsi]
0x180085774  lea     r9, [rsp+1E8h+String]
0x180085779  lea     r8, aDevicelock; "DeviceLock"
0x180085780  mov     edx, r14d
0x180085783  mov     rcx, rsi
0x180085786  mov     rax, [rax+18h]
0x18008578a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008578f  test    eax, eax
0x180085791  jnz     short loc_1800857AA
0x180085793  mov     rdx, [rsp+1E8h+String]
0x180085798  test    rdx, rdx
0x18008579b  jz      short loc_1800857AA
0x18008579d  lea     rcx, [rsp+1E8h+instance]
0x1800857a5  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800857aa  cmp     r13b, 1
0x1800857ae  jnz     short loc_1800857D2
0x1800857b0  lea     rdx, [rsp+1E8h+instance]
0x1800857b8  mov     rcx, r12; self
0x1800857bb  call    MI_Instance_Destruct
0x1800857c0  lea     rcx, [rsp+1E8h+instance]; self
0x1800857c8  call    MI_Instance_Destruct
0x1800857cd  jmp     loc_180085C27
0x1800857d2  mov     rax, [rsi]
0x1800857d5  lea     r9, [rsp+1E8h+String]
0x1800857da  lea     r8, aAllowscreentim; "AllowScreenTimeoutWhileLockedUserConfig"
0x1800857e1  mov     edx, r14d
0x1800857e4  mov     rcx, rsi
0x1800857e7  mov     rax, [rax+18h]
0x1800857eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800857f0  test    eax, eax
0x1800857f2  jnz     short loc_180085819
0x1800857f4  mov     rcx, [rsp+1E8h+String]; String
0x1800857f9  test    rcx, rcx
0x1800857fc  jz      short loc_180085819
0x1800857fe  call    cs:__imp__wtoi
0x180085805  nop     dword ptr [rax+rax+00h]
0x18008580a  mov     [rsp+1E8h+var_D8], eax
0x180085811  mov     [rsp+1E8h+var_D4], 1
0x180085819  mov     rax, [rsi]
0x18008581c  lea     r9, [rsp+1E8h+String]
0x180085821  lea     r8, aEnforcelockscr; "EnforceLockScreenAndLogonImage"
0x180085828  mov     edx, r14d
0x18008582b  mov     rcx, rsi
0x18008582e  mov     rax, [rax+18h]
0x180085832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085837  test    eax, eax
0x180085839  jnz     short loc_180085852
0x18008583b  mov     rdx, [rsp+1E8h+String]
0x180085840  test    rdx, rdx
0x180085843  jz      short loc_180085852
0x180085845  lea     rcx, [rsp+1E8h+instance]
0x18008584d  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x180085852  mov     rax, [rsi]
0x180085855  lea     r9, [rsp+1E8h+String]
0x18008585a  lea     r8, aEnforcelockscr_0; "EnforceLockScreenProvider"
0x180085861  mov     edx, r14d
0x180085864  mov     rcx, rsi
0x180085867  mov     rax, [rax+18h]
0x18008586b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085870  test    eax, eax
0x180085872  jnz     short loc_18008588B
0x180085874  mov     rdx, [rsp+1E8h+String]
0x180085879  test    rdx, rdx
0x18008587c  jz      short loc_18008588B
0x18008587e  lea     rcx, [rsp+1E8h+instance]
0x180085886  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x18008588b  mov     rax, [rsi]
0x18008588e  lea     r9, [rsp+1E8h+String]
0x180085893  lea     r8, aMinimumpasswor; "MinimumPasswordAge"
0x18008589a  mov     edx, r14d
0x18008589d  mov     rcx, rsi
0x1800858a0  mov     rax, [rax+18h]
0x1800858a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800858a9  test    eax, eax
0x1800858ab  jnz     short loc_1800858D2
0x1800858ad  mov     rcx, [rsp+1E8h+String]; String
0x1800858b2  test    rcx, rcx
0x1800858b5  jz      short loc_1800858D2
0x1800858b7  call    cs:__imp__wtoi
0x1800858be  nop     dword ptr [rax+rax+00h]
0x1800858c3  mov     [rsp+1E8h+var_B0], eax
0x1800858ca  mov     [rsp+1E8h+var_AC], 1
0x1800858d2  mov     rax, [rsi]
0x1800858d5  lea     r9, [rsp+1E8h+String]
0x1800858da  lea     r8, aPreventenablin; "PreventEnablingLockScreenCamera"
0x1800858e1  mov     edx, r14d
0x1800858e4  mov     rcx, rsi
0x1800858e7  mov     rax, [rax+18h]
0x1800858eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800858f0  test    eax, eax
0x1800858f2  jnz     short loc_18008590B
0x1800858f4  mov     rdx, [rsp+1E8h+String]
0x1800858f9  test    rdx, rdx
0x1800858fc  jz      short loc_18008590B
0x1800858fe  lea     rcx, [rsp+1E8h+instance]
0x180085906  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x18008590b  mov     rax, [rsi]
0x18008590e  lea     r9, [rsp+1E8h+String]
0x180085913  lea     r8, aPreventlockscr; "PreventLockScreenSlideShow"
0x18008591a  mov     edx, r14d
0x18008591d  mov     rcx, rsi
0x180085920  mov     rax, [rax+18h]
0x180085924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085929  test    eax, eax
0x18008592b  jnz     short loc_180085944
0x18008592d  mov     rdx, [rsp+1E8h+String]
0x180085932  test    rdx, rdx
0x180085935  jz      short loc_180085944
0x180085937  lea     rcx, [rsp+1E8h+instance]
0x18008593f  call    MDM_VPNv2_User_01_Set_DnsSuffix
0x180085944  mov     rax, [rsi]
0x180085947  lea     r9, [rsp+1E8h+String]
0x18008594c  lea     r8, aScreentimeoutw; "ScreenTimeoutWhileLocked"
0x180085953  mov     edx, r14d
0x180085956  mov     rcx, rsi
0x180085959  mov     rax, [rax+18h]
0x18008595d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085962  test    eax, eax
0x180085964  jnz     short loc_18008598B
0x180085966  mov     rcx, [rsp+1E8h+String]; String
0x18008596b  test    rcx, rcx
0x18008596e  jz      short loc_18008598B
0x180085970  call    cs:__imp__wtoi
0x180085977  nop     dword ptr [rax+rax+00h]
0x18008597c  mov     [rsp+1E8h+var_88], eax
0x180085983  mov     [rsp+1E8h+var_84], 1
0x18008598b  mov     rax, [rsi]
0x18008598e  lea     r9, [rsp+1E8h+String]
0x180085993  lea     r8, aDevicepassword; "DevicePasswordEnabled"
0x18008599a  mov     edx, r14d
0x18008599d  mov     rcx, rsi
0x1800859a0  mov     rax, [rax+18h]
0x1800859a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800859a9  test    eax, eax
0x1800859ab  jnz     short loc_1800859D2
0x1800859ad  mov     rcx, [rsp+1E8h+String]; String
0x1800859b2  test    rcx, rcx
0x1800859b5  jz      short loc_1800859D2
0x1800859b7  call    cs:__imp__wtoi
0x1800859be  nop     dword ptr [rax+rax+00h]
0x1800859c3  mov     [rsp+1E8h+var_80], eax
0x1800859ca  mov     [rsp+1E8h+var_7C], 1
0x1800859d2  mov     rax, [rsi]
0x1800859d5  lea     r9, [rsp+1E8h+String]
0x1800859da  lea     r8, aAllowsimpledev; "AllowSimpleDevicePassword"
0x1800859e1  mov     edx, r14d
0x1800859e4  mov     rcx, rsi
0x1800859e7  mov     rax, [rax+18h]
0x1800859eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800859f0  test    eax, eax
  ... truncated ...
```
