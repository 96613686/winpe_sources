# MDM_Policy_Result01_Security02_InvokeEnumerateInstances

- ea: `0x18018e1b8`
- end: `0x18018e820`
- name: `MDM_Policy_Result01_Security02_InvokeEnumerateInstances`
- size: `1640`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18018d910`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18018e1b8`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18018e4ca`
- `msvcrt!_wtoi` at `0x18018e511`
- `msvcrt!_wtoi` at `0x18018e558`
- `msvcrt!_wtoi` at `0x18018e59f`
- `msvcrt!_wtoi` at `0x18018e5e6`
- `msvcrt!_wtoi` at `0x18018e62d`
- `msvcrt!_wtoi` at `0x18018e674`
- `msvcrt!_wtoi` at `0x18018e6bb`
- `msvcrt!_wtoi` at `0x18018e702`
- `msvcrt!_wtoi` at `0x18018e4ca`
- `msvcrt!_wtoi` at `0x18018e511`
- `msvcrt!_wtoi` at `0x18018e558`
- `msvcrt!_wtoi` at `0x18018e59f`
- `msvcrt!_wtoi` at `0x18018e5e6`
- `msvcrt!_wtoi` at `0x18018e62d`
- `msvcrt!_wtoi` at `0x18018e674`
- `msvcrt!_wtoi` at `0x18018e6bb`
- `msvcrt!_wtoi` at `0x18018e702`

## string_xrefs

- `0x18018e4ed`: `AllowRemoveProvisioningPackage`
- `0x18018e534`: `ClearTPMIfNotReady`
- `0x18018e57b`: `ConfigureWindowsPasswords`
- `0x18018e5c2`: `PreventAutomaticDeviceEncryptionForAzureADJoinedDevices`
- `0x18018e233`: `MDM_Policy_Result01_Security02`
- `0x18018e445`: `Security`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Security02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  MI_Result v6; // r14d
  _QWORD *v7; // rsi
  unsigned int i; // r15d
  wchar_t *String; // [rsp+48h] [rbp-150h] BYREF
  _QWORD *v11; // [rsp+50h] [rbp-148h] BYREF
  _QWORD v12[5]; // [rsp+58h] [rbp-140h] BYREF
  char v13; // [rsp+80h] [rbp-118h]
  int v14; // [rsp+88h] [rbp-110h] BYREF
  char v15; // [rsp+8Ch] [rbp-10Ch]
  _BYTE v16[16]; // [rsp+90h] [rbp-108h] BYREF
  _DWORD v17[4]; // [rsp+A0h] [rbp-F8h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-E8h] BYREF
  int v19; // [rsp+110h] [rbp-88h]
  char v20; // [rsp+114h] [rbp-84h]
  int v21; // [rsp+118h] [rbp-80h]
  char v22; // [rsp+11Ch] [rbp-7Ch]
  int v23; // [rsp+120h] [rbp-78h]
  char v24; // [rsp+124h] [rbp-74h]
  int v25; // [rsp+128h] [rbp-70h]
  char v26; // [rsp+12Ch] [rbp-6Ch]
  int v27; // [rsp+130h] [rbp-68h]
  char v28; // [rsp+134h] [rbp-64h]
  int v29; // [rsp+138h] [rbp-60h]
  char v30; // [rsp+13Ch] [rbp-5Ch]
  int v31; // [rsp+140h] [rbp-58h]
  char v32; // [rsp+144h] [rbp-54h]
  int v33; // [rsp+148h] [rbp-50h]
  char v34; // [rsp+14Ch] [rbp-4Ch]
  int v35; // [rsp+150h] [rbp-48h]
  char v36; // [rsp+154h] [rbp-44h]

  memset_0(&instance, 0, 0xA8u);
  String = 0;
  v14 = 0;
  v15 = 0;
  v12[0] = &TelemetryEventWriter::`vftable';
  v12[1] = &v14;
  v12[2] = "MDM_Policy_Result01_Security02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v14);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v15 && (v17[0] || v17[1] || v17[2] || v17[3]) )
      v5 = v17;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_18036E6AF,
      v16,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v12, v4);
  v11 = 0;
  v6 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Result01_Security02_NodeList, 11, 2, &v11);
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
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_Security02_rtti, &instance);
            if ( v6 )
            {
              if ( v11 )
              {
                (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
                v11 = 0;
              }
              goto LABEL_65;
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
                    L"Security",
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
                      L"AllowAddProvisioningPackage",
                      &String)
                && String )
              {
                v19 = _wtoi(String);
                v20 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"AllowRemoveProvisioningPackage",
                      &String)
                && String )
              {
                v21 = _wtoi(String);
                v22 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ClearTPMIfNotReady",
                      &String)
                && String )
              {
                v23 = _wtoi(String);
                v24 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureWindowsPasswords",
                      &String)
                && String )
              {
                v25 = _wtoi(String);
                v26 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"PreventAutomaticDeviceEncryptionForAzureADJoinedDevices",
                      &String)
                && String )
              {
                v27 = _wtoi(String);
                v28 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"RecoveryEnvironmentAuthentication",
                      &String)
                && String )
              {
                v29 = _wtoi(String);
                v30 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"RequireDeviceEncryption",
                      &String)
                && String )
              {
                v31 = _wtoi(String);
                v32 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"RequireProvisioningPackageSignature",
                      &String)
                && String )
              {
                v33 = _wtoi(String);
                v34 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"RequireRetrieveHealthCertificateOnBoot",
                      &String)
                && String )
              {
                v35 = _wtoi(String);
                v36 = 1;
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
LABEL_65:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v12, "EnumerateInstancesEnd", v6);
  v14 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &word_1803470A6,
      v16,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v14);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18018e1b8  mov     [rsp+arg_8], rbx
0x18018e1bd  mov     [rsp+arg_10], rsi
0x18018e1c2  push    rdi
0x18018e1c3  push    r12
0x18018e1c5  push    r13
0x18018e1c7  push    r14
0x18018e1c9  push    r15
0x18018e1cb  sub     rsp, 170h
0x18018e1d2  mov     rax, cs:__security_cookie
0x18018e1d9  xor     rax, rsp
0x18018e1dc  mov     [rsp+198h+var_38], rax
0x18018e1e4  mov     r13b, dl
0x18018e1e7  mov     r12, rcx
0x18018e1ea  xor     edx, edx; Val
0x18018e1ec  mov     r8d, 0A8h; Size
0x18018e1f2  lea     rcx, [rsp+198h+instance]; void *
0x18018e1fa  call    memset_0
0x18018e1ff  xor     edi, edi
0x18018e201  mov     [rsp+198h+var_158], dil
0x18018e206  mov     [rsp+198h+String], rdi
0x18018e20b  mov     [rsp+198h+var_110], edi
0x18018e212  mov     [rsp+198h+var_10C], dil
0x18018e21a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18018e221  mov     [rsp+198h+var_140], rax
0x18018e226  lea     rax, [rsp+198h+var_110]
0x18018e22e  mov     [rsp+198h+var_138], rax
0x18018e233  lea     rax, aMdmPolicyResul_141; "MDM_Policy_Result01_Security02"
0x18018e23a  mov     [rsp+198h+var_130], rax
0x18018e23f  lea     rcx, [rsp+198h+var_110]
0x18018e247  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18018e24c  mov     eax, cs:dword_180380B68
0x18018e252  cmp     eax, 5
0x18018e255  jbe     short loc_18018E2C7
0x18018e257  mov     rdx, 200000000000h
0x18018e261  lea     rcx, dword_180380B68
0x18018e268  call    _tlgKeywordOn
0x18018e26d  test    al, al
0x18018e26f  jz      short loc_18018E2C7
0x18018e271  cmp     [rsp+198h+var_10C], dil
0x18018e279  jz      short loc_18018E2A9
0x18018e27b  cmp     [rsp+198h+var_F8], edi
0x18018e282  jnz     short loc_18018E29F
0x18018e284  cmp     [rsp+198h+var_F4], edi
0x18018e28b  jnz     short loc_18018E29F
0x18018e28d  cmp     [rsp+198h+var_F0], edi
0x18018e294  jnz     short loc_18018E29F
0x18018e296  cmp     [rsp+198h+var_EC], edi
0x18018e29d  jz      short loc_18018E2A9
0x18018e29f  lea     r9, [rsp+198h+var_F8]
0x18018e2a7  jmp     short loc_18018E2AC
0x18018e2a9  mov     r9, rdi
0x18018e2ac  lea     r8, [rsp+198h+var_108]
0x18018e2b4  lea     rdx, byte_18036E6AF
0x18018e2bb  lea     rcx, dword_180380B68
0x18018e2c2  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18018e2c7  lea     rcx, [rsp+198h+var_140]; this
0x18018e2cc  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18018e2d1  nop
0x18018e2d2  mov     [rsp+198h+var_148], rdi
0x18018e2d7  lea     rax, [rsp+198h+var_148]
0x18018e2dc  mov     [rsp+198h+var_168], rax
0x18018e2e1  mov     [rsp+198h+var_170], 2
0x18018e2e9  mov     [rsp+198h+var_178], 0Bh
0x18018e2f1  lea     r9, ?MDM_Policy_Result01_Security02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Security02_NodeList
0x18018e2f8  xor     r8d, r8d
0x18018e2fb  xor     edx, edx
0x18018e2fd  mov     rcx, r12
0x18018e300  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18018e305  mov     r14d, eax
0x18018e308  test    eax, eax
0x18018e30a  jz      short loc_18018E311
0x18018e30c  jmp     loc_18018E77F
0x18018e311  lea     rbx, [rsp+198h+var_148]
0x18018e316  mov     [rsp+198h+var_120], rbx
0x18018e31b  mov     r15d, 1
0x18018e321  mov     [rsp+198h+var_118], r15b
0x18018e329  mov     rsi, [rsp+198h+var_148]
0x18018e32e  test    rsi, rsi
0x18018e331  jnz     short loc_18018E33B
0x18018e333  mov     r14d, r15d
0x18018e336  jmp     loc_18018E77F
0x18018e33b  mov     rax, [rsi]
0x18018e33e  mov     rcx, rsi
0x18018e341  mov     rax, [rax+10h]
0x18018e345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e34a  mov     r14d, eax
0x18018e34d  test    eax, eax
0x18018e34f  jz      short loc_18018E36F
0x18018e351  mov     rcx, [rsp+198h+var_148]
0x18018e356  test    rcx, rcx
0x18018e359  jz      short loc_18018E36A
0x18018e35b  mov     rax, [rcx]
0x18018e35e  mov     edx, r15d
0x18018e361  mov     rax, [rax]
0x18018e364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e369  nop
0x18018e36a  jmp     loc_18018E77F
0x18018e36f  mov     rax, [rsi]
0x18018e372  mov     rcx, rsi
0x18018e375  mov     rax, [rax+8]
0x18018e379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e37e  mov     r14d, eax
0x18018e381  test    eax, eax
0x18018e383  jz      short loc_18018E3A3
0x18018e385  mov     rcx, [rsp+198h+var_148]
0x18018e38a  test    rcx, rcx
0x18018e38d  jz      short loc_18018E39E
0x18018e38f  mov     rax, [rcx]
0x18018e392  mov     edx, r15d
0x18018e395  mov     rax, [rax]
0x18018e398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e39d  nop
0x18018e39e  jmp     loc_18018E77F
0x18018e3a3  mov     r15d, edi
0x18018e3a6  mov     rax, [rsi+108h]
0x18018e3ad  sub     rax, [rsi+100h]
0x18018e3b4  sar     rax, 4
0x18018e3b8  cmp     r15d, eax
0x18018e3bb  jnb     loc_18018E747
0x18018e3c1  lea     r8, [rsp+198h+instance]; instance
0x18018e3c9  lea     rdx, MDM_Policy_Result01_Security02_rtti; classDecl
0x18018e3d0  mov     rcx, r12; context
0x18018e3d3  call    MI_Context_ConstructInstance
0x18018e3d8  mov     r14d, eax
0x18018e3db  test    eax, eax
0x18018e3dd  jz      short loc_18018E3FF
0x18018e3df  mov     rcx, [rbx]
0x18018e3e2  test    rcx, rcx
0x18018e3e5  jz      short loc_18018E3FA
0x18018e3e7  mov     rax, [rcx]
0x18018e3ea  mov     edx, 1
0x18018e3ef  mov     rax, [rax]
0x18018e3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e3f7  mov     [rbx], rdi
0x18018e3fa  jmp     loc_18018E77F
0x18018e3ff  mov     [rsp+198h+var_158], 1
0x18018e404  mov     rax, [rsi]
0x18018e407  lea     r9, [rsp+198h+String]
0x18018e40c  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x18018e413  mov     edx, r15d
0x18018e416  mov     rcx, rsi
0x18018e419  mov     rax, [rax+18h]
0x18018e41d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e422  test    eax, eax
0x18018e424  jnz     short loc_18018E43D
0x18018e426  mov     rdx, [rsp+198h+String]
0x18018e42b  test    rdx, rdx
0x18018e42e  jz      short loc_18018E43D
0x18018e430  lea     rcx, [rsp+198h+instance]
0x18018e438  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18018e43d  mov     rax, [rsi]
0x18018e440  lea     r9, [rsp+198h+String]
0x18018e445  lea     r8, aSecurity; "Security"
0x18018e44c  mov     edx, r15d
0x18018e44f  mov     rcx, rsi
0x18018e452  mov     rax, [rax+18h]
0x18018e456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e45b  test    eax, eax
0x18018e45d  jnz     short loc_18018E476
0x18018e45f  mov     rdx, [rsp+198h+String]
0x18018e464  test    rdx, rdx
0x18018e467  jz      short loc_18018E476
0x18018e469  lea     rcx, [rsp+198h+instance]
0x18018e471  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18018e476  cmp     r13b, 1
0x18018e47a  jnz     short loc_18018E49E
0x18018e47c  lea     rdx, [rsp+198h+instance]
0x18018e484  mov     rcx, r12; self
0x18018e487  call    MI_Instance_Destruct
0x18018e48c  lea     rcx, [rsp+198h+instance]; self
0x18018e494  call    MI_Instance_Destruct
0x18018e499  jmp     loc_18018E73A
0x18018e49e  mov     rax, [rsi]
0x18018e4a1  lea     r9, [rsp+198h+String]
0x18018e4a6  lea     r8, aAllowaddprovis; "AllowAddProvisioningPackage"
0x18018e4ad  mov     edx, r15d
0x18018e4b0  mov     rcx, rsi
0x18018e4b3  mov     rax, [rax+18h]
0x18018e4b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e4bc  test    eax, eax
0x18018e4be  jnz     short loc_18018E4E5
0x18018e4c0  mov     rcx, [rsp+198h+String]; String
0x18018e4c5  test    rcx, rcx
0x18018e4c8  jz      short loc_18018E4E5
0x18018e4ca  call    cs:__imp__wtoi
0x18018e4d1  nop     dword ptr [rax+rax+00h]
0x18018e4d6  mov     [rsp+198h+var_88], eax
0x18018e4dd  mov     [rsp+198h+var_84], 1
0x18018e4e5  mov     rax, [rsi]
0x18018e4e8  lea     r9, [rsp+198h+String]
0x18018e4ed  lea     r8, aAllowremovepro; "AllowRemoveProvisioningPackage"
0x18018e4f4  mov     edx, r15d
0x18018e4f7  mov     rcx, rsi
0x18018e4fa  mov     rax, [rax+18h]
0x18018e4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e503  test    eax, eax
0x18018e505  jnz     short loc_18018E52C
0x18018e507  mov     rcx, [rsp+198h+String]; String
0x18018e50c  test    rcx, rcx
0x18018e50f  jz      short loc_18018E52C
0x18018e511  call    cs:__imp__wtoi
0x18018e518  nop     dword ptr [rax+rax+00h]
0x18018e51d  mov     [rsp+198h+var_80], eax
0x18018e524  mov     [rsp+198h+var_7C], 1
0x18018e52c  mov     rax, [rsi]
0x18018e52f  lea     r9, [rsp+198h+String]
0x18018e534  lea     r8, aCleartpmifnotr; "ClearTPMIfNotReady"
0x18018e53b  mov     edx, r15d
0x18018e53e  mov     rcx, rsi
0x18018e541  mov     rax, [rax+18h]
0x18018e545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e54a  test    eax, eax
0x18018e54c  jnz     short loc_18018E573
0x18018e54e  mov     rcx, [rsp+198h+String]; String
0x18018e553  test    rcx, rcx
0x18018e556  jz      short loc_18018E573
0x18018e558  call    cs:__imp__wtoi
0x18018e55f  nop     dword ptr [rax+rax+00h]
0x18018e564  mov     [rsp+198h+var_78], eax
0x18018e56b  mov     [rsp+198h+var_74], 1
0x18018e573  mov     rax, [rsi]
0x18018e576  lea     r9, [rsp+198h+String]
0x18018e57b  lea     r8, aConfigurewindo_2; "ConfigureWindowsPasswords"
0x18018e582  mov     edx, r15d
0x18018e585  mov     rcx, rsi
0x18018e588  mov     rax, [rax+18h]
0x18018e58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e591  test    eax, eax
0x18018e593  jnz     short loc_18018E5BA
0x18018e595  mov     rcx, [rsp+198h+String]; String
0x18018e59a  test    rcx, rcx
0x18018e59d  jz      short loc_18018E5BA
0x18018e59f  call    cs:__imp__wtoi
0x18018e5a6  nop     dword ptr [rax+rax+00h]
0x18018e5ab  mov     [rsp+198h+var_70], eax
0x18018e5b2  mov     [rsp+198h+var_6C], 1
0x18018e5ba  mov     rax, [rsi]
0x18018e5bd  lea     r9, [rsp+198h+String]
0x18018e5c2  lea     r8, aPreventautomat; "PreventAutomaticDeviceEncryptionForAzur"...
0x18018e5c9  mov     edx, r15d
0x18018e5cc  mov     rcx, rsi
0x18018e5cf  mov     rax, [rax+18h]
0x18018e5d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e5d8  test    eax, eax
0x18018e5da  jnz     short loc_18018E601
0x18018e5dc  mov     rcx, [rsp+198h+String]; String
0x18018e5e1  test    rcx, rcx
0x18018e5e4  jz      short loc_18018E601
0x18018e5e6  call    cs:__imp__wtoi
0x18018e5ed  nop     dword ptr [rax+rax+00h]
0x18018e5f2  mov     [rsp+198h+var_68], eax
0x18018e5f9  mov     [rsp+198h+var_64], 1
0x18018e601  mov     rax, [rsi]
0x18018e604  lea     r9, [rsp+198h+String]
0x18018e609  lea     r8, aRecoveryenviro; "RecoveryEnvironmentAuthentication"
0x18018e610  mov     edx, r15d
0x18018e613  mov     rcx, rsi
0x18018e616  mov     rax, [rax+18h]
0x18018e61a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e61f  test    eax, eax
0x18018e621  jnz     short loc_18018E648
0x18018e623  mov     rcx, [rsp+198h+String]; String
0x18018e628  test    rcx, rcx
0x18018e62b  jz      short loc_18018E648
0x18018e62d  call    cs:__imp__wtoi
0x18018e634  nop     dword ptr [rax+rax+00h]
0x18018e639  mov     [rsp+198h+var_60], eax
0x18018e640  mov     [rsp+198h+var_5C], 1
0x18018e648  mov     rax, [rsi]
0x18018e64b  lea     r9, [rsp+198h+String]
0x18018e650  lea     r8, aRequiredevicee; "RequireDeviceEncryption"
0x18018e657  mov     edx, r15d
0x18018e65a  mov     rcx, rsi
0x18018e65d  mov     rax, [rax+18h]
0x18018e661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e666  test    eax, eax
0x18018e668  jnz     short loc_18018E68F
0x18018e66a  mov     rcx, [rsp+198h+String]; String
0x18018e66f  test    rcx, rcx
0x18018e672  jz      short loc_18018E68F
0x18018e674  call    cs:__imp__wtoi
0x18018e67b  nop     dword ptr [rax+rax+00h]
0x18018e680  mov     [rsp+198h+var_58], eax
0x18018e687  mov     [rsp+198h+var_54], 1
0x18018e68f  mov     rax, [rsi]
0x18018e692  lea     r9, [rsp+198h+String]
0x18018e697  lea     r8, aRequireprovisi; "RequireProvisioningPackageSignature"
0x18018e69e  mov     edx, r15d
0x18018e6a1  mov     rcx, rsi
0x18018e6a4  mov     rax, [rax+18h]
0x18018e6a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e6ad  test    eax, eax
0x18018e6af  jnz     short loc_18018E6D6
0x18018e6b1  mov     rcx, [rsp+198h+String]; String
0x18018e6b6  test    rcx, rcx
0x18018e6b9  jz      short loc_18018E6D6
0x18018e6bb  call    cs:__imp__wtoi
0x18018e6c2  nop     dword ptr [rax+rax+00h]
0x18018e6c7  mov     [rsp+198h+var_50], eax
0x18018e6ce  mov     [rsp+198h+var_4C], 1
  ... truncated ...
```
