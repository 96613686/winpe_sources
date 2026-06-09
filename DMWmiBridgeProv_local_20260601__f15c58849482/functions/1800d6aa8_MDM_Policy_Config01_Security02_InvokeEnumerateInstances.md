# MDM_Policy_Config01_Security02_InvokeEnumerateInstances

- ea: `0x1800d6aa8`
- end: `0x1800d7110`
- name: `MDM_Policy_Config01_Security02_InvokeEnumerateInstances`
- size: `1640`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d6200`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800d6aa8`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800d6dba`
- `msvcrt!_wtoi` at `0x1800d6e01`
- `msvcrt!_wtoi` at `0x1800d6e48`
- `msvcrt!_wtoi` at `0x1800d6e8f`
- `msvcrt!_wtoi` at `0x1800d6ed6`
- `msvcrt!_wtoi` at `0x1800d6f1d`
- `msvcrt!_wtoi` at `0x1800d6f64`
- `msvcrt!_wtoi` at `0x1800d6fab`
- `msvcrt!_wtoi` at `0x1800d6ff2`
- `msvcrt!_wtoi` at `0x1800d6dba`
- `msvcrt!_wtoi` at `0x1800d6e01`
- `msvcrt!_wtoi` at `0x1800d6e48`
- `msvcrt!_wtoi` at `0x1800d6e8f`
- `msvcrt!_wtoi` at `0x1800d6ed6`
- `msvcrt!_wtoi` at `0x1800d6f1d`
- `msvcrt!_wtoi` at `0x1800d6f64`
- `msvcrt!_wtoi` at `0x1800d6fab`
- `msvcrt!_wtoi` at `0x1800d6ff2`

## string_xrefs

- `0x1800d6ddd`: `AllowRemoveProvisioningPackage`
- `0x1800d6e24`: `ClearTPMIfNotReady`
- `0x1800d6e6b`: `ConfigureWindowsPasswords`
- `0x1800d6eb2`: `PreventAutomaticDeviceEncryptionForAzureADJoinedDevices`
- `0x1800d6cfc`: `./Vendor/MSFT/Policy/Config`
- `0x1800d6b23`: `MDM_Policy_Config01_Security02`
- `0x1800d6d35`: `Security`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Security02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  MI_Result v7; // r14d
  _QWORD *v8; // rsi
  unsigned int i; // r15d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+48h] [rbp-150h] BYREF
  _QWORD *v14; // [rsp+50h] [rbp-148h] BYREF
  _QWORD v15[3]; // [rsp+58h] [rbp-140h] BYREF
  const exception *v16[2]; // [rsp+70h] [rbp-128h] BYREF
  char v17; // [rsp+80h] [rbp-118h]
  int v18; // [rsp+88h] [rbp-110h] BYREF
  char v19; // [rsp+8Ch] [rbp-10Ch]
  _BYTE v20[16]; // [rsp+90h] [rbp-108h] BYREF
  _DWORD v21[4]; // [rsp+A0h] [rbp-F8h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-E8h] BYREF
  int v23; // [rsp+110h] [rbp-88h]
  char v24; // [rsp+114h] [rbp-84h]
  int v25; // [rsp+118h] [rbp-80h]
  char v26; // [rsp+11Ch] [rbp-7Ch]
  int v27; // [rsp+120h] [rbp-78h]
  char v28; // [rsp+124h] [rbp-74h]
  int v29; // [rsp+128h] [rbp-70h]
  char v30; // [rsp+12Ch] [rbp-6Ch]
  int v31; // [rsp+130h] [rbp-68h]
  char v32; // [rsp+134h] [rbp-64h]
  int v33; // [rsp+138h] [rbp-60h]
  char v34; // [rsp+13Ch] [rbp-5Ch]
  int v35; // [rsp+140h] [rbp-58h]
  char v36; // [rsp+144h] [rbp-54h]
  int v37; // [rsp+148h] [rbp-50h]
  char v38; // [rsp+14Ch] [rbp-4Ch]
  int v39; // [rsp+150h] [rbp-48h]
  char v40; // [rsp+154h] [rbp-44h]

  memset_0(&instance, 0, 0xA8u);
  String = 0;
  v18 = 0;
  v19 = 0;
  v15[0] = &TelemetryEventWriter::`vftable';
  v15[1] = &v18;
  v15[2] = "MDM_Policy_Config01_Security02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v18);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v19 && (v21[0] || v21[1] || v21[2] || v21[3]) )
      v5 = v21;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_180367A70,
      v20,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v15, v4);
  try
  {
    v14 = 0;
    v7 = (unsigned int)CreateRequestHandlerInstance(self, 0, 0, &MDM_Policy_Config01_Security02_NodeList, 11, 2, &v14);
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Security02_rtti, &instance);
              if ( v7 )
              {
                v6 = (wil *)v14;
                if ( v14 )
                {
                  (*(void (__fastcall **)(_QWORD *, __int64))*v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_73;
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
                      L"Security",
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
                        L"AllowAddProvisioningPackage",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"AllowRemoveProvisioningPackage",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ClearTPMIfNotReady",
                        &String)
                  && String )
                {
                  v27 = _wtoi(String);
                  v28 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureWindowsPasswords",
                        &String)
                  && String )
                {
                  v29 = _wtoi(String);
                  v30 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"PreventAutomaticDeviceEncryptionForAzureADJoinedDevices",
                        &String)
                  && String )
                {
                  v31 = _wtoi(String);
                  v32 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"RecoveryEnvironmentAuthentication",
                        &String)
                  && String )
                {
                  v33 = _wtoi(String);
                  v34 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"RequireDeviceEncryption",
                        &String)
                  && String )
                {
                  v35 = _wtoi(String);
                  v36 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"RequireProvisioningPackageSignature",
                        &String)
                  && String )
                {
                  v37 = _wtoi(String);
                  v38 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v8 + 24LL))(
                        v8,
                        i,
                        L"RequireRetrieveHealthCertificateOnBoot",
                        &String)
                  && String )
                {
                  v39 = _wtoi(String);
                  v40 = 1;
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
LABEL_73:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v15, "EnumerateInstancesEnd", v7);
  v18 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &byte_18034639F,
      v20,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v18);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800d6aa8  mov     [rsp+arg_8], rbx
0x1800d6aad  mov     [rsp+arg_10], rsi
0x1800d6ab2  push    rdi
0x1800d6ab3  push    r12
0x1800d6ab5  push    r13
0x1800d6ab7  push    r14
0x1800d6ab9  push    r15
0x1800d6abb  sub     rsp, 170h
0x1800d6ac2  mov     rax, cs:__security_cookie
0x1800d6ac9  xor     rax, rsp
0x1800d6acc  mov     [rsp+198h+var_38], rax
0x1800d6ad4  mov     r13b, dl
0x1800d6ad7  mov     r12, rcx
0x1800d6ada  xor     edx, edx; Val
0x1800d6adc  mov     r8d, 0A8h; Size
0x1800d6ae2  lea     rcx, [rsp+198h+instance]; void *
0x1800d6aea  call    memset_0
0x1800d6aef  xor     edi, edi
0x1800d6af1  mov     [rsp+198h+var_158], dil
0x1800d6af6  mov     [rsp+198h+String], rdi
0x1800d6afb  mov     [rsp+198h+var_110], edi
0x1800d6b02  mov     [rsp+198h+var_10C], dil
0x1800d6b0a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800d6b11  mov     [rsp+198h+var_140], rax
0x1800d6b16  lea     rax, [rsp+198h+var_110]
0x1800d6b1e  mov     [rsp+198h+var_138], rax
0x1800d6b23  lea     rax, aMdmPolicyConfi_98; "MDM_Policy_Config01_Security02"
0x1800d6b2a  mov     [rsp+198h+var_130], rax
0x1800d6b2f  lea     rcx, [rsp+198h+var_110]
0x1800d6b37  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800d6b3c  mov     eax, cs:dword_180380B68
0x1800d6b42  cmp     eax, 5
0x1800d6b45  jbe     short loc_1800D6BB7
0x1800d6b47  mov     rdx, 200000000000h
0x1800d6b51  lea     rcx, dword_180380B68
0x1800d6b58  call    _tlgKeywordOn
0x1800d6b5d  test    al, al
0x1800d6b5f  jz      short loc_1800D6BB7
0x1800d6b61  cmp     [rsp+198h+var_10C], dil
0x1800d6b69  jz      short loc_1800D6B99
0x1800d6b6b  cmp     [rsp+198h+var_F8], edi
0x1800d6b72  jnz     short loc_1800D6B8F
0x1800d6b74  cmp     [rsp+198h+var_F4], edi
0x1800d6b7b  jnz     short loc_1800D6B8F
0x1800d6b7d  cmp     [rsp+198h+var_F0], edi
0x1800d6b84  jnz     short loc_1800D6B8F
0x1800d6b86  cmp     [rsp+198h+var_EC], edi
0x1800d6b8d  jz      short loc_1800D6B99
0x1800d6b8f  lea     r9, [rsp+198h+var_F8]
0x1800d6b97  jmp     short loc_1800D6B9C
0x1800d6b99  mov     r9, rdi
0x1800d6b9c  lea     r8, [rsp+198h+var_108]
0x1800d6ba4  lea     rdx, qword_180367A70
0x1800d6bab  lea     rcx, dword_180380B68
0x1800d6bb2  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800d6bb7  lea     rcx, [rsp+198h+var_140]; this
0x1800d6bbc  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800d6bc1  nop
0x1800d6bc2  mov     [rsp+198h+var_148], rdi
0x1800d6bc7  lea     rax, [rsp+198h+var_148]
0x1800d6bcc  mov     [rsp+198h+var_168], rax
0x1800d6bd1  mov     [rsp+198h+var_170], 2
0x1800d6bd9  mov     [rsp+198h+var_178], 0Bh
0x1800d6be1  lea     r9, ?MDM_Policy_Config01_Security02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Security02_NodeList
0x1800d6be8  xor     r8d, r8d
0x1800d6beb  xor     edx, edx
0x1800d6bed  mov     rcx, r12
0x1800d6bf0  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800d6bf5  mov     r14d, eax
0x1800d6bf8  test    eax, eax
0x1800d6bfa  jz      short loc_1800D6C01
0x1800d6bfc  jmp     loc_1800D706F
0x1800d6c01  lea     rbx, [rsp+198h+var_148]
0x1800d6c06  mov     [rsp+198h+var_120], rbx
0x1800d6c0b  mov     r15d, 1
0x1800d6c11  mov     [rsp+198h+var_118], r15b
0x1800d6c19  mov     rsi, [rsp+198h+var_148]
0x1800d6c1e  test    rsi, rsi
0x1800d6c21  jnz     short loc_1800D6C2B
0x1800d6c23  mov     r14d, r15d
0x1800d6c26  jmp     loc_1800D706F
0x1800d6c2b  mov     rax, [rsi]
0x1800d6c2e  mov     rcx, rsi
0x1800d6c31  mov     rax, [rax+10h]
0x1800d6c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6c3a  mov     r14d, eax
0x1800d6c3d  test    eax, eax
0x1800d6c3f  jz      short loc_1800D6C5F
0x1800d6c41  mov     rcx, [rsp+198h+var_148]
0x1800d6c46  test    rcx, rcx
0x1800d6c49  jz      short loc_1800D6C5A
0x1800d6c4b  mov     rax, [rcx]
0x1800d6c4e  mov     edx, r15d
0x1800d6c51  mov     rax, [rax]
0x1800d6c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6c59  nop
0x1800d6c5a  jmp     loc_1800D706F
0x1800d6c5f  mov     rax, [rsi]
0x1800d6c62  mov     rcx, rsi
0x1800d6c65  mov     rax, [rax+8]
0x1800d6c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6c6e  mov     r14d, eax
0x1800d6c71  test    eax, eax
0x1800d6c73  jz      short loc_1800D6C93
0x1800d6c75  mov     rcx, [rsp+198h+var_148]
0x1800d6c7a  test    rcx, rcx
0x1800d6c7d  jz      short loc_1800D6C8E
0x1800d6c7f  mov     rax, [rcx]
0x1800d6c82  mov     edx, r15d
0x1800d6c85  mov     rax, [rax]
0x1800d6c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6c8d  nop
0x1800d6c8e  jmp     loc_1800D706F
0x1800d6c93  mov     r15d, edi
0x1800d6c96  mov     rax, [rsi+108h]
0x1800d6c9d  sub     rax, [rsi+100h]
0x1800d6ca4  sar     rax, 4
0x1800d6ca8  cmp     r15d, eax
0x1800d6cab  jnb     loc_1800D7037
0x1800d6cb1  lea     r8, [rsp+198h+instance]; instance
0x1800d6cb9  lea     rdx, MDM_Policy_Config01_Security02_rtti; classDecl
0x1800d6cc0  mov     rcx, r12; context
0x1800d6cc3  call    MI_Context_ConstructInstance
0x1800d6cc8  mov     r14d, eax
0x1800d6ccb  test    eax, eax
0x1800d6ccd  jz      short loc_1800D6CEF
0x1800d6ccf  mov     rcx, [rbx]
0x1800d6cd2  test    rcx, rcx
0x1800d6cd5  jz      short loc_1800D6CEA
0x1800d6cd7  mov     rax, [rcx]
0x1800d6cda  mov     edx, 1
0x1800d6cdf  mov     rax, [rax]
0x1800d6ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6ce7  mov     [rbx], rdi
0x1800d6cea  jmp     loc_1800D706F
0x1800d6cef  mov     [rsp+198h+var_158], 1
0x1800d6cf4  mov     rax, [rsi]
0x1800d6cf7  lea     r9, [rsp+198h+String]
0x1800d6cfc  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800d6d03  mov     edx, r15d
0x1800d6d06  mov     rcx, rsi
0x1800d6d09  mov     rax, [rax+18h]
0x1800d6d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6d12  test    eax, eax
0x1800d6d14  jnz     short loc_1800D6D2D
0x1800d6d16  mov     rdx, [rsp+198h+String]
0x1800d6d1b  test    rdx, rdx
0x1800d6d1e  jz      short loc_1800D6D2D
0x1800d6d20  lea     rcx, [rsp+198h+instance]
0x1800d6d28  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800d6d2d  mov     rax, [rsi]
0x1800d6d30  lea     r9, [rsp+198h+String]
0x1800d6d35  lea     r8, aSecurity; "Security"
0x1800d6d3c  mov     edx, r15d
0x1800d6d3f  mov     rcx, rsi
0x1800d6d42  mov     rax, [rax+18h]
0x1800d6d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6d4b  test    eax, eax
0x1800d6d4d  jnz     short loc_1800D6D66
0x1800d6d4f  mov     rdx, [rsp+198h+String]
0x1800d6d54  test    rdx, rdx
0x1800d6d57  jz      short loc_1800D6D66
0x1800d6d59  lea     rcx, [rsp+198h+instance]
0x1800d6d61  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800d6d66  cmp     r13b, 1
0x1800d6d6a  jnz     short loc_1800D6D8E
0x1800d6d6c  lea     rdx, [rsp+198h+instance]
0x1800d6d74  mov     rcx, r12; self
0x1800d6d77  call    MI_Instance_Destruct
0x1800d6d7c  lea     rcx, [rsp+198h+instance]; self
0x1800d6d84  call    MI_Instance_Destruct
0x1800d6d89  jmp     loc_1800D702A
0x1800d6d8e  mov     rax, [rsi]
0x1800d6d91  lea     r9, [rsp+198h+String]
0x1800d6d96  lea     r8, aAllowaddprovis; "AllowAddProvisioningPackage"
0x1800d6d9d  mov     edx, r15d
0x1800d6da0  mov     rcx, rsi
0x1800d6da3  mov     rax, [rax+18h]
0x1800d6da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6dac  test    eax, eax
0x1800d6dae  jnz     short loc_1800D6DD5
0x1800d6db0  mov     rcx, [rsp+198h+String]; String
0x1800d6db5  test    rcx, rcx
0x1800d6db8  jz      short loc_1800D6DD5
0x1800d6dba  call    cs:__imp__wtoi
0x1800d6dc1  nop     dword ptr [rax+rax+00h]
0x1800d6dc6  mov     [rsp+198h+var_88], eax
0x1800d6dcd  mov     [rsp+198h+var_84], 1
0x1800d6dd5  mov     rax, [rsi]
0x1800d6dd8  lea     r9, [rsp+198h+String]
0x1800d6ddd  lea     r8, aAllowremovepro; "AllowRemoveProvisioningPackage"
0x1800d6de4  mov     edx, r15d
0x1800d6de7  mov     rcx, rsi
0x1800d6dea  mov     rax, [rax+18h]
0x1800d6dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6df3  test    eax, eax
0x1800d6df5  jnz     short loc_1800D6E1C
0x1800d6df7  mov     rcx, [rsp+198h+String]; String
0x1800d6dfc  test    rcx, rcx
0x1800d6dff  jz      short loc_1800D6E1C
0x1800d6e01  call    cs:__imp__wtoi
0x1800d6e08  nop     dword ptr [rax+rax+00h]
0x1800d6e0d  mov     [rsp+198h+var_80], eax
0x1800d6e14  mov     [rsp+198h+var_7C], 1
0x1800d6e1c  mov     rax, [rsi]
0x1800d6e1f  lea     r9, [rsp+198h+String]
0x1800d6e24  lea     r8, aCleartpmifnotr; "ClearTPMIfNotReady"
0x1800d6e2b  mov     edx, r15d
0x1800d6e2e  mov     rcx, rsi
0x1800d6e31  mov     rax, [rax+18h]
0x1800d6e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6e3a  test    eax, eax
0x1800d6e3c  jnz     short loc_1800D6E63
0x1800d6e3e  mov     rcx, [rsp+198h+String]; String
0x1800d6e43  test    rcx, rcx
0x1800d6e46  jz      short loc_1800D6E63
0x1800d6e48  call    cs:__imp__wtoi
0x1800d6e4f  nop     dword ptr [rax+rax+00h]
0x1800d6e54  mov     [rsp+198h+var_78], eax
0x1800d6e5b  mov     [rsp+198h+var_74], 1
0x1800d6e63  mov     rax, [rsi]
0x1800d6e66  lea     r9, [rsp+198h+String]
0x1800d6e6b  lea     r8, aConfigurewindo_2; "ConfigureWindowsPasswords"
0x1800d6e72  mov     edx, r15d
0x1800d6e75  mov     rcx, rsi
0x1800d6e78  mov     rax, [rax+18h]
0x1800d6e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6e81  test    eax, eax
0x1800d6e83  jnz     short loc_1800D6EAA
0x1800d6e85  mov     rcx, [rsp+198h+String]; String
0x1800d6e8a  test    rcx, rcx
0x1800d6e8d  jz      short loc_1800D6EAA
0x1800d6e8f  call    cs:__imp__wtoi
0x1800d6e96  nop     dword ptr [rax+rax+00h]
0x1800d6e9b  mov     [rsp+198h+var_70], eax
0x1800d6ea2  mov     [rsp+198h+var_6C], 1
0x1800d6eaa  mov     rax, [rsi]
0x1800d6ead  lea     r9, [rsp+198h+String]
0x1800d6eb2  lea     r8, aPreventautomat; "PreventAutomaticDeviceEncryptionForAzur"...
0x1800d6eb9  mov     edx, r15d
0x1800d6ebc  mov     rcx, rsi
0x1800d6ebf  mov     rax, [rax+18h]
0x1800d6ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6ec8  test    eax, eax
0x1800d6eca  jnz     short loc_1800D6EF1
0x1800d6ecc  mov     rcx, [rsp+198h+String]; String
0x1800d6ed1  test    rcx, rcx
0x1800d6ed4  jz      short loc_1800D6EF1
0x1800d6ed6  call    cs:__imp__wtoi
0x1800d6edd  nop     dword ptr [rax+rax+00h]
0x1800d6ee2  mov     [rsp+198h+var_68], eax
0x1800d6ee9  mov     [rsp+198h+var_64], 1
0x1800d6ef1  mov     rax, [rsi]
0x1800d6ef4  lea     r9, [rsp+198h+String]
0x1800d6ef9  lea     r8, aRecoveryenviro; "RecoveryEnvironmentAuthentication"
0x1800d6f00  mov     edx, r15d
0x1800d6f03  mov     rcx, rsi
0x1800d6f06  mov     rax, [rax+18h]
0x1800d6f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6f0f  test    eax, eax
0x1800d6f11  jnz     short loc_1800D6F38
0x1800d6f13  mov     rcx, [rsp+198h+String]; String
0x1800d6f18  test    rcx, rcx
0x1800d6f1b  jz      short loc_1800D6F38
0x1800d6f1d  call    cs:__imp__wtoi
0x1800d6f24  nop     dword ptr [rax+rax+00h]
0x1800d6f29  mov     [rsp+198h+var_60], eax
0x1800d6f30  mov     [rsp+198h+var_5C], 1
0x1800d6f38  mov     rax, [rsi]
0x1800d6f3b  lea     r9, [rsp+198h+String]
0x1800d6f40  lea     r8, aRequiredevicee; "RequireDeviceEncryption"
0x1800d6f47  mov     edx, r15d
0x1800d6f4a  mov     rcx, rsi
0x1800d6f4d  mov     rax, [rax+18h]
0x1800d6f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6f56  test    eax, eax
0x1800d6f58  jnz     short loc_1800D6F7F
0x1800d6f5a  mov     rcx, [rsp+198h+String]; String
0x1800d6f5f  test    rcx, rcx
0x1800d6f62  jz      short loc_1800D6F7F
0x1800d6f64  call    cs:__imp__wtoi
0x1800d6f6b  nop     dword ptr [rax+rax+00h]
0x1800d6f70  mov     [rsp+198h+var_58], eax
0x1800d6f77  mov     [rsp+198h+var_54], 1
0x1800d6f7f  mov     rax, [rsi]
0x1800d6f82  lea     r9, [rsp+198h+String]
0x1800d6f87  lea     r8, aRequireprovisi; "RequireProvisioningPackageSignature"
0x1800d6f8e  mov     edx, r15d
0x1800d6f91  mov     rcx, rsi
0x1800d6f94  mov     rax, [rax+18h]
0x1800d6f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6f9d  test    eax, eax
0x1800d6f9f  jnz     short loc_1800D6FC6
0x1800d6fa1  mov     rcx, [rsp+198h+String]; String
0x1800d6fa6  test    rcx, rcx
0x1800d6fa9  jz      short loc_1800D6FC6
0x1800d6fab  call    cs:__imp__wtoi
0x1800d6fb2  nop     dword ptr [rax+rax+00h]
0x1800d6fb7  mov     [rsp+198h+var_50], eax
0x1800d6fbe  mov     [rsp+198h+var_4C], 1
  ... truncated ...
```
