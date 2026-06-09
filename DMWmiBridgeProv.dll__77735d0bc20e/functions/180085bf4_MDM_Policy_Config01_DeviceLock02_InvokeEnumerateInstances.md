# MDM_Policy_Config01_DeviceLock02_InvokeEnumerateInstances

- ea: `0x180085bf4`
- end: `0x1800863cc`
- name: `MDM_Policy_Config01_DeviceLock02_InvokeEnumerateInstances`
- size: `2008`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180085170`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004e74`
- `0x180004eac`
- `0x180004f1c`
- `0x180004f8c`
- `0x180004fc4`
- `0x180004ffc`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x180085bf4`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x180085f06`
- `msvcrt!_wtoi` at `0x180085fb9`
- `msvcrt!_wtoi` at `0x18008606c`
- `msvcrt!_wtoi` at `0x1800860ad`
- `msvcrt!_wtoi` at `0x1800860ee`
- `msvcrt!_wtoi` at `0x18008612f`
- `msvcrt!_wtoi` at `0x180086170`
- `msvcrt!_wtoi` at `0x1800861b1`
- `msvcrt!_wtoi` at `0x1800861f2`
- `msvcrt!_wtoi` at `0x180086233`
- `msvcrt!_wtoi` at `0x180086274`
- `msvcrt!_wtoi` at `0x1800862b5`
- `msvcrt!_wtoi` at `0x180085f06`
- `msvcrt!_wtoi` at `0x180085fb9`
- `msvcrt!_wtoi` at `0x18008606c`
- `msvcrt!_wtoi` at `0x1800860ad`
- `msvcrt!_wtoi` at `0x1800860ee`
- `msvcrt!_wtoi` at `0x18008612f`
- `msvcrt!_wtoi` at `0x180086170`
- `msvcrt!_wtoi` at `0x1800861b1`
- `msvcrt!_wtoi` at `0x1800861f2`
- `msvcrt!_wtoi` at `0x180086233`
- `msvcrt!_wtoi` at `0x180086274`
- `msvcrt!_wtoi` at `0x1800862b5`

## string_xrefs

- `0x180085ee2`: `AllowScreenTimeoutWhileLockedUserConfig`
- `0x18008618d`: `MinDevicePasswordComplexCharacters`
- `0x180086250`: `MaxDevicePasswordFailedAttempts`
- `0x180085e48`: `./Vendor/MSFT/Policy/Config`
- `0x180085c6f`: `MDM_Policy_Config01_DeviceLock02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_DeviceLock02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  unsigned int v7; // r15d
  WmiRequestHandlerAdd *v8; // rsi
  unsigned int i; // r14d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+48h] [rbp-1A0h] BYREF
  WmiRequestHandlerAdd *v14; // [rsp+50h] [rbp-198h] BYREF
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
    v7 = CreateRequestHandlerInstance(
           (__int64)self,
           0,
           0,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_DeviceLock02_NodeList,
           0x12u,
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_DeviceLock02_rtti, &instance);
              if ( v7 )
              {
                v6 = v14;
                if ( v14 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_94;
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
                      L"DeviceLock",
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
                        L"AllowScreenTimeoutWhileLockedUserConfig",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EnforceLockScreenAndLogonImage",
                        &String)
                  && String )
                {
                  MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"EnforceLockScreenProvider",
                        &String)
                  && String )
                {
                  MDM_WindowsLicensing_Set_LicenseKeyType(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"MinimumPasswordAge",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"PreventEnablingLockScreenCamera",
                        &String)
                  && String )
                {
                  MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"PreventLockScreenSlideShow",
                        &String)
                  && String )
                {
                  MDM_VPNv2_User_01_Set_DnsSuffix(&instance);
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ScreenTimeoutWhileLocked",
                        &String)
                  && String )
                {
                  v27 = _wtoi(String);
                  v28 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DevicePasswordEnabled",
                        &String)
                  && String )
                {
                  v29 = _wtoi(String);
                  v30 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowSimpleDevicePassword",
                        &String)
                  && String )
                {
                  v31 = _wtoi(String);
                  v32 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"MinDevicePasswordLength",
                        &String)
                  && String )
                {
                  v33 = _wtoi(String);
                  v34 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AlphanumericDevicePasswordRequired",
                        &String)
                  && String )
                {
                  v35 = _wtoi(String);
                  v36 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"MinDevicePasswordComplexCharacters",
                        &String)
                  && String )
                {
                  v37 = _wtoi(String);
                  v38 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DevicePasswordExpiration",
                        &String)
                  && String )
                {
                  v39 = _wtoi(String);
                  v40 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"DevicePasswordHistory",
                        &String)
                  && String )
                {
                  v41 = _wtoi(String);
                  v42 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"MaxDevicePasswordFailedAttempts",
                        &String)
                  && String )
                {
                  v43 = _wtoi(String);
                  v44 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
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
  return v7;
}

```

## disassembly

```asm
0x180085bf4  mov     [rsp+arg_8], rbx
0x180085bf9  mov     [rsp+arg_10], rsi
0x180085bfe  push    rdi
0x180085bff  push    r12
0x180085c01  push    r13
0x180085c03  push    r14
0x180085c05  push    r15
0x180085c07  sub     rsp, 1C0h
0x180085c0e  mov     rax, cs:__security_cookie
0x180085c15  xor     rax, rsp
0x180085c18  mov     [rsp+1E8h+var_38], rax
0x180085c20  mov     r13b, dl
0x180085c23  mov     r12, rcx
0x180085c26  xor     edx, edx; Val
0x180085c28  mov     r8d, 100h; Size
0x180085c2e  lea     rcx, [rsp+1E8h+instance]; void *
0x180085c36  call    memset_0
0x180085c3b  xor     edi, edi
0x180085c3d  mov     [rsp+1E8h+var_1A8], dil
0x180085c42  mov     [rsp+1E8h+String], rdi
0x180085c47  mov     [rsp+1E8h+var_160], edi
0x180085c4e  mov     [rsp+1E8h+var_15C], dil
0x180085c56  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x180085c5d  mov     [rsp+1E8h+var_190], rax
0x180085c62  lea     rax, [rsp+1E8h+var_160]
0x180085c6a  mov     [rsp+1E8h+var_188], rax
0x180085c6f  lea     rax, aMdmPolicyConfi_133; "MDM_Policy_Config01_DeviceLock02"
0x180085c76  mov     [rsp+1E8h+var_180], rax
0x180085c7b  lea     rcx, [rsp+1E8h+var_160]
0x180085c83  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x180085c88  mov     eax, cs:dword_180380B68
0x180085c8e  cmp     eax, 5
0x180085c91  jbe     short loc_180085D03
0x180085c93  mov     rdx, 200000000000h
0x180085c9d  lea     rcx, dword_180380B68
0x180085ca4  call    _tlgKeywordOn
0x180085ca9  test    al, al
0x180085cab  jz      short loc_180085D03
0x180085cad  cmp     [rsp+1E8h+var_15C], dil
0x180085cb5  jz      short loc_180085CE5
0x180085cb7  cmp     [rsp+1E8h+var_148], edi
0x180085cbe  jnz     short loc_180085CDB
0x180085cc0  cmp     [rsp+1E8h+var_144], edi
0x180085cc7  jnz     short loc_180085CDB
0x180085cc9  cmp     [rsp+1E8h+var_140], edi
0x180085cd0  jnz     short loc_180085CDB
0x180085cd2  cmp     [rsp+1E8h+var_13C], edi
0x180085cd9  jz      short loc_180085CE5
0x180085cdb  lea     r9, [rsp+1E8h+var_148]
0x180085ce3  jmp     short loc_180085CE8
0x180085ce5  mov     r9, rdi
0x180085ce8  lea     r8, [rsp+1E8h+var_158]
0x180085cf0  lea     rdx, word_180359162
0x180085cf7  lea     rcx, dword_180380B68
0x180085cfe  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180085d03  lea     rcx, [rsp+1E8h+var_190]; this
0x180085d08  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x180085d0d  nop
0x180085d0e  mov     [rsp+1E8h+var_198], rdi
0x180085d13  lea     rax, [rsp+1E8h+var_198]
0x180085d18  mov     [rsp+1E8h+var_1B8], rax
0x180085d1d  mov     [rsp+1E8h+var_1C0], 2
0x180085d25  mov     [rsp+1E8h+var_1C8], 12h
0x180085d2d  lea     r9, ?MDM_Policy_Config01_DeviceLock02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_DeviceLock02_NodeList
0x180085d34  xor     r8d, r8d
0x180085d37  xor     edx, edx
0x180085d39  mov     rcx, r12
0x180085d3c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x180085d41  mov     r15d, eax
0x180085d44  test    eax, eax
0x180085d46  jz      short loc_180085D4D
0x180085d48  jmp     loc_18008632C
0x180085d4d  lea     rbx, [rsp+1E8h+var_198]
0x180085d52  mov     [rsp+1E8h+var_170], rbx
0x180085d57  mov     r14d, 1
0x180085d5d  mov     [rsp+1E8h+var_168], r14b
0x180085d65  mov     rsi, [rsp+1E8h+var_198]
0x180085d6a  test    rsi, rsi
0x180085d6d  jnz     short loc_180085D77
0x180085d6f  mov     r15d, r14d
0x180085d72  jmp     loc_18008632C
0x180085d77  mov     rax, [rsi]
0x180085d7a  mov     rcx, rsi
0x180085d7d  mov     rax, [rax+10h]
0x180085d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085d86  mov     r15d, eax
0x180085d89  test    eax, eax
0x180085d8b  jz      short loc_180085DAB
0x180085d8d  mov     rcx, [rsp+1E8h+var_198]
0x180085d92  test    rcx, rcx
0x180085d95  jz      short loc_180085DA6
0x180085d97  mov     rax, [rcx]
0x180085d9a  mov     edx, r14d
0x180085d9d  mov     rax, [rax]
0x180085da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085da5  nop
0x180085da6  jmp     loc_18008632C
0x180085dab  mov     rax, [rsi]
0x180085dae  mov     rcx, rsi
0x180085db1  mov     rax, [rax+8]
0x180085db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085dba  mov     r15d, eax
0x180085dbd  test    eax, eax
0x180085dbf  jz      short loc_180085DDF
0x180085dc1  mov     rcx, [rsp+1E8h+var_198]
0x180085dc6  test    rcx, rcx
0x180085dc9  jz      short loc_180085DDA
0x180085dcb  mov     rax, [rcx]
0x180085dce  mov     edx, r14d
0x180085dd1  mov     rax, [rax]
0x180085dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085dd9  nop
0x180085dda  jmp     loc_18008632C
0x180085ddf  mov     r14d, edi
0x180085de2  mov     rax, [rsi+108h]
0x180085de9  sub     rax, [rsi+100h]
0x180085df0  sar     rax, 4
0x180085df4  cmp     r14d, eax
0x180085df7  jnb     loc_1800862F4
0x180085dfd  lea     r8, [rsp+1E8h+instance]; instance
0x180085e05  lea     rdx, MDM_Policy_Config01_DeviceLock02_rtti; classDecl
0x180085e0c  mov     rcx, r12; context
0x180085e0f  call    MI_Context_ConstructInstance
0x180085e14  mov     r15d, eax
0x180085e17  test    eax, eax
0x180085e19  jz      short loc_180085E3B
0x180085e1b  mov     rcx, [rbx]
0x180085e1e  test    rcx, rcx
0x180085e21  jz      short loc_180085E36
0x180085e23  mov     rax, [rcx]
0x180085e26  mov     edx, 1
0x180085e2b  mov     rax, [rax]
0x180085e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085e33  mov     [rbx], rdi
0x180085e36  jmp     loc_18008632C
0x180085e3b  mov     [rsp+1E8h+var_1A8], 1
0x180085e40  mov     rax, [rsi]
0x180085e43  lea     r9, [rsp+1E8h+String]
0x180085e48  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x180085e4f  mov     edx, r14d
0x180085e52  mov     rcx, rsi
0x180085e55  mov     rax, [rax+18h]
0x180085e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085e5e  test    eax, eax
0x180085e60  jnz     short loc_180085E79
0x180085e62  mov     rdx, [rsp+1E8h+String]
0x180085e67  test    rdx, rdx
0x180085e6a  jz      short loc_180085E79
0x180085e6c  lea     rcx, [rsp+1E8h+instance]
0x180085e74  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x180085e79  mov     rax, [rsi]
0x180085e7c  lea     r9, [rsp+1E8h+String]
0x180085e81  lea     r8, aDevicelock; "DeviceLock"
0x180085e88  mov     edx, r14d
0x180085e8b  mov     rcx, rsi
0x180085e8e  mov     rax, [rax+18h]
0x180085e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085e97  test    eax, eax
0x180085e99  jnz     short loc_180085EB2
0x180085e9b  mov     rdx, [rsp+1E8h+String]
0x180085ea0  test    rdx, rdx
0x180085ea3  jz      short loc_180085EB2
0x180085ea5  lea     rcx, [rsp+1E8h+instance]
0x180085ead  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x180085eb2  cmp     r13b, 1
0x180085eb6  jnz     short loc_180085EDA
0x180085eb8  lea     rdx, [rsp+1E8h+instance]
0x180085ec0  mov     rcx, r12; self
0x180085ec3  call    MI_Instance_Destruct
0x180085ec8  lea     rcx, [rsp+1E8h+instance]; self
0x180085ed0  call    MI_Instance_Destruct
0x180085ed5  jmp     loc_1800862E7
0x180085eda  mov     rax, [rsi]
0x180085edd  lea     r9, [rsp+1E8h+String]
0x180085ee2  lea     r8, aAllowscreentim; "AllowScreenTimeoutWhileLockedUserConfig"
0x180085ee9  mov     edx, r14d
0x180085eec  mov     rcx, rsi
0x180085eef  mov     rax, [rax+18h]
0x180085ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085ef8  test    eax, eax
0x180085efa  jnz     short loc_180085F1B
0x180085efc  mov     rcx, [rsp+1E8h+String]; String
0x180085f01  test    rcx, rcx
0x180085f04  jz      short loc_180085F1B
0x180085f06  call    cs:__imp__wtoi
0x180085f0c  mov     [rsp+1E8h+var_D8], eax
0x180085f13  mov     [rsp+1E8h+var_D4], 1
0x180085f1b  mov     rax, [rsi]
0x180085f1e  lea     r9, [rsp+1E8h+String]
0x180085f23  lea     r8, aEnforcelockscr; "EnforceLockScreenAndLogonImage"
0x180085f2a  mov     edx, r14d
0x180085f2d  mov     rcx, rsi
0x180085f30  mov     rax, [rax+18h]
0x180085f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085f39  test    eax, eax
0x180085f3b  jnz     short loc_180085F54
0x180085f3d  mov     rdx, [rsp+1E8h+String]
0x180085f42  test    rdx, rdx
0x180085f45  jz      short loc_180085F54
0x180085f47  lea     rcx, [rsp+1E8h+instance]
0x180085f4f  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x180085f54  mov     rax, [rsi]
0x180085f57  lea     r9, [rsp+1E8h+String]
0x180085f5c  lea     r8, aEnforcelockscr_0; "EnforceLockScreenProvider"
0x180085f63  mov     edx, r14d
0x180085f66  mov     rcx, rsi
0x180085f69  mov     rax, [rax+18h]
0x180085f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085f72  test    eax, eax
0x180085f74  jnz     short loc_180085F8D
0x180085f76  mov     rdx, [rsp+1E8h+String]
0x180085f7b  test    rdx, rdx
0x180085f7e  jz      short loc_180085F8D
0x180085f80  lea     rcx, [rsp+1E8h+instance]
0x180085f88  call    MDM_WindowsLicensing_Set_LicenseKeyType
0x180085f8d  mov     rax, [rsi]
0x180085f90  lea     r9, [rsp+1E8h+String]
0x180085f95  lea     r8, aMinimumpasswor; "MinimumPasswordAge"
0x180085f9c  mov     edx, r14d
0x180085f9f  mov     rcx, rsi
0x180085fa2  mov     rax, [rax+18h]
0x180085fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085fab  test    eax, eax
0x180085fad  jnz     short loc_180085FCE
0x180085faf  mov     rcx, [rsp+1E8h+String]; String
0x180085fb4  test    rcx, rcx
0x180085fb7  jz      short loc_180085FCE
0x180085fb9  call    cs:__imp__wtoi
0x180085fbf  mov     [rsp+1E8h+var_B0], eax
0x180085fc6  mov     [rsp+1E8h+var_AC], 1
0x180085fce  mov     rax, [rsi]
0x180085fd1  lea     r9, [rsp+1E8h+String]
0x180085fd6  lea     r8, aPreventenablin; "PreventEnablingLockScreenCamera"
0x180085fdd  mov     edx, r14d
0x180085fe0  mov     rcx, rsi
0x180085fe3  mov     rax, [rax+18h]
0x180085fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180085fec  test    eax, eax
0x180085fee  jnz     short loc_180086007
0x180085ff0  mov     rdx, [rsp+1E8h+String]
0x180085ff5  test    rdx, rdx
0x180085ff8  jz      short loc_180086007
0x180085ffa  lea     rcx, [rsp+1E8h+instance]
0x180086002  call    MDM_VPNv2_TrafficFilterList02_01_Set_LocalAddressRanges
0x180086007  mov     rax, [rsi]
0x18008600a  lea     r9, [rsp+1E8h+String]
0x18008600f  lea     r8, aPreventlockscr; "PreventLockScreenSlideShow"
0x180086016  mov     edx, r14d
0x180086019  mov     rcx, rsi
0x18008601c  mov     rax, [rax+18h]
0x180086020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086025  test    eax, eax
0x180086027  jnz     short loc_180086040
0x180086029  mov     rdx, [rsp+1E8h+String]
0x18008602e  test    rdx, rdx
0x180086031  jz      short loc_180086040
0x180086033  lea     rcx, [rsp+1E8h+instance]
0x18008603b  call    MDM_VPNv2_User_01_Set_DnsSuffix
0x180086040  mov     rax, [rsi]
0x180086043  lea     r9, [rsp+1E8h+String]
0x180086048  lea     r8, aScreentimeoutw; "ScreenTimeoutWhileLocked"
0x18008604f  mov     edx, r14d
0x180086052  mov     rcx, rsi
0x180086055  mov     rax, [rax+18h]
0x180086059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008605e  test    eax, eax
0x180086060  jnz     short loc_180086081
0x180086062  mov     rcx, [rsp+1E8h+String]; String
0x180086067  test    rcx, rcx
0x18008606a  jz      short loc_180086081
0x18008606c  call    cs:__imp__wtoi
0x180086072  mov     [rsp+1E8h+var_88], eax
0x180086079  mov     [rsp+1E8h+var_84], 1
0x180086081  mov     rax, [rsi]
0x180086084  lea     r9, [rsp+1E8h+String]
0x180086089  lea     r8, aDevicepassword; "DevicePasswordEnabled"
0x180086090  mov     edx, r14d
0x180086093  mov     rcx, rsi
0x180086096  mov     rax, [rax+18h]
0x18008609a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008609f  test    eax, eax
0x1800860a1  jnz     short loc_1800860C2
0x1800860a3  mov     rcx, [rsp+1E8h+String]; String
0x1800860a8  test    rcx, rcx
0x1800860ab  jz      short loc_1800860C2
0x1800860ad  call    cs:__imp__wtoi
0x1800860b3  mov     [rsp+1E8h+var_80], eax
0x1800860ba  mov     [rsp+1E8h+var_7C], 1
0x1800860c2  mov     rax, [rsi]
0x1800860c5  lea     r9, [rsp+1E8h+String]
0x1800860ca  lea     r8, aAllowsimpledev; "AllowSimpleDevicePassword"
0x1800860d1  mov     edx, r14d
0x1800860d4  mov     rcx, rsi
0x1800860d7  mov     rax, [rax+18h]
0x1800860db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800860e0  test    eax, eax
0x1800860e2  jnz     short loc_180086103
0x1800860e4  mov     rcx, [rsp+1E8h+String]; String
0x1800860e9  test    rcx, rcx
0x1800860ec  jz      short loc_180086103
  ... truncated ...
```
