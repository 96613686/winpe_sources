# MDM_Policy_Result01_Security02_InvokeEnumerateInstances

- ea: `0x18018e8f4`
- end: `0x18018ef25`
- name: `MDM_Policy_Result01_Security02_InvokeEnumerateInstances`
- size: `1585`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18018e030`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x18018e8f4`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18018ec06`
- `msvcrt!_wtoi` at `0x18018ec47`
- `msvcrt!_wtoi` at `0x18018ec88`
- `msvcrt!_wtoi` at `0x18018ecc9`
- `msvcrt!_wtoi` at `0x18018ed0a`
- `msvcrt!_wtoi` at `0x18018ed4b`
- `msvcrt!_wtoi` at `0x18018ed8c`
- `msvcrt!_wtoi` at `0x18018edcd`
- `msvcrt!_wtoi` at `0x18018ee0e`
- `msvcrt!_wtoi` at `0x18018ec06`
- `msvcrt!_wtoi` at `0x18018ec47`
- `msvcrt!_wtoi` at `0x18018ec88`
- `msvcrt!_wtoi` at `0x18018ecc9`
- `msvcrt!_wtoi` at `0x18018ed0a`
- `msvcrt!_wtoi` at `0x18018ed4b`
- `msvcrt!_wtoi` at `0x18018ed8c`
- `msvcrt!_wtoi` at `0x18018edcd`
- `msvcrt!_wtoi` at `0x18018ee0e`

## string_xrefs

- `0x18018ec23`: `AllowRemoveProvisioningPackage`
- `0x18018ec64`: `ClearTPMIfNotReady`
- `0x18018eca5`: `ConfigureWindowsPasswords`
- `0x18018ece6`: `PreventAutomaticDeviceEncryptionForAzureADJoinedDevices`
- `0x18018e96f`: `MDM_Policy_Result01_Security02`
- `0x18018eb81`: `Security`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Security02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  unsigned int v6; // r14d
  WmiRequestHandlerAdd *v7; // rsi
  unsigned int i; // r15d
  wchar_t *String; // [rsp+48h] [rbp-150h] BYREF
  WmiRequestHandlerAdd *v11; // [rsp+50h] [rbp-148h] BYREF
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
  v6 = CreateRequestHandlerInstance(
         (__int64)self,
         0,
         0,
         (struct WmiNodeInfo *)&MDM_Policy_Result01_Security02_NodeList,
         0xBu,
         2,
         &v11);
  if ( !v6 )
  {
    v12[4] = &v11;
    v13 = 1;
    v7 = v11;
    if ( v11 )
    {
      v6 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v11 + 16LL))(v11);
      if ( v6 )
      {
        if ( v11 )
          (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v11)(v11, 1);
      }
      else
      {
        v6 = (*(__int64 (__fastcall **)(WmiRequestHandlerAdd *))(*(_QWORD *)v7 + 8LL))(v7);
        if ( v6 )
        {
          if ( v11 )
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v11)(v11, 1);
        }
        else
        {
          for ( i = 0; i < (unsigned int)((__int64)(*((_QWORD *)v7 + 33) - *((_QWORD *)v7 + 32)) >> 4); ++i )
          {
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_Security02_rtti, &instance);
            if ( v6 )
            {
              if ( v11 )
              {
                (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v11)(v11, 1);
                v11 = 0;
              }
              goto LABEL_65;
            }
            if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                    v7,
                    i,
                    L"./Vendor/MSFT/Policy/Result",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
            }
            if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
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
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowAddProvisioningPackage",
                      &String)
                && String )
              {
                v19 = _wtoi(String);
                v20 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"AllowRemoveProvisioningPackage",
                      &String)
                && String )
              {
                v21 = _wtoi(String);
                v22 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ClearTPMIfNotReady",
                      &String)
                && String )
              {
                v23 = _wtoi(String);
                v24 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureWindowsPasswords",
                      &String)
                && String )
              {
                v25 = _wtoi(String);
                v26 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"PreventAutomaticDeviceEncryptionForAzureADJoinedDevices",
                      &String)
                && String )
              {
                v27 = _wtoi(String);
                v28 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"RecoveryEnvironmentAuthentication",
                      &String)
                && String )
              {
                v29 = _wtoi(String);
                v30 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"RequireDeviceEncryption",
                      &String)
                && String )
              {
                v31 = _wtoi(String);
                v32 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"RequireProvisioningPackageSignature",
                      &String)
                && String )
              {
                v33 = _wtoi(String);
                v34 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
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
            (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v11)(v11, 1);
            v11 = 0;
          }
        }
      }
    }
    else
    {
      v6 = 1;
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
  return v6;
}

```

## disassembly

```asm
0x18018e8f4  mov     [rsp+arg_8], rbx
0x18018e8f9  mov     [rsp+arg_10], rsi
0x18018e8fe  push    rdi
0x18018e8ff  push    r12
0x18018e901  push    r13
0x18018e903  push    r14
0x18018e905  push    r15
0x18018e907  sub     rsp, 170h
0x18018e90e  mov     rax, cs:__security_cookie
0x18018e915  xor     rax, rsp
0x18018e918  mov     [rsp+198h+var_38], rax
0x18018e920  mov     r13b, dl
0x18018e923  mov     r12, rcx
0x18018e926  xor     edx, edx; Val
0x18018e928  mov     r8d, 0A8h; Size
0x18018e92e  lea     rcx, [rsp+198h+instance]; void *
0x18018e936  call    memset_0
0x18018e93b  xor     edi, edi
0x18018e93d  mov     [rsp+198h+var_158], dil
0x18018e942  mov     [rsp+198h+String], rdi
0x18018e947  mov     [rsp+198h+var_110], edi
0x18018e94e  mov     [rsp+198h+var_10C], dil
0x18018e956  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18018e95d  mov     [rsp+198h+var_140], rax
0x18018e962  lea     rax, [rsp+198h+var_110]
0x18018e96a  mov     [rsp+198h+var_138], rax
0x18018e96f  lea     rax, aMdmPolicyResul_141; "MDM_Policy_Result01_Security02"
0x18018e976  mov     [rsp+198h+var_130], rax
0x18018e97b  lea     rcx, [rsp+198h+var_110]
0x18018e983  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18018e988  mov     eax, cs:dword_180380B68
0x18018e98e  cmp     eax, 5
0x18018e991  jbe     short loc_18018EA03
0x18018e993  mov     rdx, 200000000000h
0x18018e99d  lea     rcx, dword_180380B68
0x18018e9a4  call    _tlgKeywordOn
0x18018e9a9  test    al, al
0x18018e9ab  jz      short loc_18018EA03
0x18018e9ad  cmp     [rsp+198h+var_10C], dil
0x18018e9b5  jz      short loc_18018E9E5
0x18018e9b7  cmp     [rsp+198h+var_F8], edi
0x18018e9be  jnz     short loc_18018E9DB
0x18018e9c0  cmp     [rsp+198h+var_F4], edi
0x18018e9c7  jnz     short loc_18018E9DB
0x18018e9c9  cmp     [rsp+198h+var_F0], edi
0x18018e9d0  jnz     short loc_18018E9DB
0x18018e9d2  cmp     [rsp+198h+var_EC], edi
0x18018e9d9  jz      short loc_18018E9E5
0x18018e9db  lea     r9, [rsp+198h+var_F8]
0x18018e9e3  jmp     short loc_18018E9E8
0x18018e9e5  mov     r9, rdi
0x18018e9e8  lea     r8, [rsp+198h+var_108]
0x18018e9f0  lea     rdx, byte_18036E6AF
0x18018e9f7  lea     rcx, dword_180380B68
0x18018e9fe  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18018ea03  lea     rcx, [rsp+198h+var_140]; this
0x18018ea08  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x18018ea0d  nop
0x18018ea0e  mov     [rsp+198h+var_148], rdi
0x18018ea13  lea     rax, [rsp+198h+var_148]
0x18018ea18  mov     [rsp+198h+var_168], rax
0x18018ea1d  mov     [rsp+198h+var_170], 2
0x18018ea25  mov     [rsp+198h+var_178], 0Bh
0x18018ea2d  lea     r9, ?MDM_Policy_Result01_Security02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Security02_NodeList
0x18018ea34  xor     r8d, r8d
0x18018ea37  xor     edx, edx
0x18018ea39  mov     rcx, r12
0x18018ea3c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18018ea41  mov     r14d, eax
0x18018ea44  test    eax, eax
0x18018ea46  jz      short loc_18018EA4D
0x18018ea48  jmp     loc_18018EE85
0x18018ea4d  lea     rbx, [rsp+198h+var_148]
0x18018ea52  mov     [rsp+198h+var_120], rbx
0x18018ea57  mov     r15d, 1
0x18018ea5d  mov     [rsp+198h+var_118], r15b
0x18018ea65  mov     rsi, [rsp+198h+var_148]
0x18018ea6a  test    rsi, rsi
0x18018ea6d  jnz     short loc_18018EA77
0x18018ea6f  mov     r14d, r15d
0x18018ea72  jmp     loc_18018EE85
0x18018ea77  mov     rax, [rsi]
0x18018ea7a  mov     rcx, rsi
0x18018ea7d  mov     rax, [rax+10h]
0x18018ea81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018ea86  mov     r14d, eax
0x18018ea89  test    eax, eax
0x18018ea8b  jz      short loc_18018EAAB
0x18018ea8d  mov     rcx, [rsp+198h+var_148]
0x18018ea92  test    rcx, rcx
0x18018ea95  jz      short loc_18018EAA6
0x18018ea97  mov     rax, [rcx]
0x18018ea9a  mov     edx, r15d
0x18018ea9d  mov     rax, [rax]
0x18018eaa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018eaa5  nop
0x18018eaa6  jmp     loc_18018EE85
0x18018eaab  mov     rax, [rsi]
0x18018eaae  mov     rcx, rsi
0x18018eab1  mov     rax, [rax+8]
0x18018eab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018eaba  mov     r14d, eax
0x18018eabd  test    eax, eax
0x18018eabf  jz      short loc_18018EADF
0x18018eac1  mov     rcx, [rsp+198h+var_148]
0x18018eac6  test    rcx, rcx
0x18018eac9  jz      short loc_18018EADA
0x18018eacb  mov     rax, [rcx]
0x18018eace  mov     edx, r15d
0x18018ead1  mov     rax, [rax]
0x18018ead4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018ead9  nop
0x18018eada  jmp     loc_18018EE85
0x18018eadf  mov     r15d, edi
0x18018eae2  mov     rax, [rsi+108h]
0x18018eae9  sub     rax, [rsi+100h]
0x18018eaf0  sar     rax, 4
0x18018eaf4  cmp     r15d, eax
0x18018eaf7  jnb     loc_18018EE4D
0x18018eafd  lea     r8, [rsp+198h+instance]; instance
0x18018eb05  lea     rdx, MDM_Policy_Result01_Security02_rtti; classDecl
0x18018eb0c  mov     rcx, r12; context
0x18018eb0f  call    MI_Context_ConstructInstance
0x18018eb14  mov     r14d, eax
0x18018eb17  test    eax, eax
0x18018eb19  jz      short loc_18018EB3B
0x18018eb1b  mov     rcx, [rbx]
0x18018eb1e  test    rcx, rcx
0x18018eb21  jz      short loc_18018EB36
0x18018eb23  mov     rax, [rcx]
0x18018eb26  mov     edx, 1
0x18018eb2b  mov     rax, [rax]
0x18018eb2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018eb33  mov     [rbx], rdi
0x18018eb36  jmp     loc_18018EE85
0x18018eb3b  mov     [rsp+198h+var_158], 1
0x18018eb40  mov     rax, [rsi]
0x18018eb43  lea     r9, [rsp+198h+String]
0x18018eb48  lea     r8, aVendorMsftPoli_42; "./Vendor/MSFT/Policy/Result"
0x18018eb4f  mov     edx, r15d
0x18018eb52  mov     rcx, rsi
0x18018eb55  mov     rax, [rax+18h]
0x18018eb59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018eb5e  test    eax, eax
0x18018eb60  jnz     short loc_18018EB79
0x18018eb62  mov     rdx, [rsp+198h+String]
0x18018eb67  test    rdx, rdx
0x18018eb6a  jz      short loc_18018EB79
0x18018eb6c  lea     rcx, [rsp+198h+instance]
0x18018eb74  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18018eb79  mov     rax, [rsi]
0x18018eb7c  lea     r9, [rsp+198h+String]
0x18018eb81  lea     r8, aSecurity; "Security"
0x18018eb88  mov     edx, r15d
0x18018eb8b  mov     rcx, rsi
0x18018eb8e  mov     rax, [rax+18h]
0x18018eb92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018eb97  test    eax, eax
0x18018eb99  jnz     short loc_18018EBB2
0x18018eb9b  mov     rdx, [rsp+198h+String]
0x18018eba0  test    rdx, rdx
0x18018eba3  jz      short loc_18018EBB2
0x18018eba5  lea     rcx, [rsp+198h+instance]
0x18018ebad  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18018ebb2  cmp     r13b, 1
0x18018ebb6  jnz     short loc_18018EBDA
0x18018ebb8  lea     rdx, [rsp+198h+instance]
0x18018ebc0  mov     rcx, r12; self
0x18018ebc3  call    MI_Instance_Destruct
0x18018ebc8  lea     rcx, [rsp+198h+instance]; self
0x18018ebd0  call    MI_Instance_Destruct
0x18018ebd5  jmp     loc_18018EE40
0x18018ebda  mov     rax, [rsi]
0x18018ebdd  lea     r9, [rsp+198h+String]
0x18018ebe2  lea     r8, aAllowaddprovis; "AllowAddProvisioningPackage"
0x18018ebe9  mov     edx, r15d
0x18018ebec  mov     rcx, rsi
0x18018ebef  mov     rax, [rax+18h]
0x18018ebf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018ebf8  test    eax, eax
0x18018ebfa  jnz     short loc_18018EC1B
0x18018ebfc  mov     rcx, [rsp+198h+String]; String
0x18018ec01  test    rcx, rcx
0x18018ec04  jz      short loc_18018EC1B
0x18018ec06  call    cs:__imp__wtoi
0x18018ec0c  mov     [rsp+198h+var_88], eax
0x18018ec13  mov     [rsp+198h+var_84], 1
0x18018ec1b  mov     rax, [rsi]
0x18018ec1e  lea     r9, [rsp+198h+String]
0x18018ec23  lea     r8, aAllowremovepro; "AllowRemoveProvisioningPackage"
0x18018ec2a  mov     edx, r15d
0x18018ec2d  mov     rcx, rsi
0x18018ec30  mov     rax, [rax+18h]
0x18018ec34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018ec39  test    eax, eax
0x18018ec3b  jnz     short loc_18018EC5C
0x18018ec3d  mov     rcx, [rsp+198h+String]; String
0x18018ec42  test    rcx, rcx
0x18018ec45  jz      short loc_18018EC5C
0x18018ec47  call    cs:__imp__wtoi
0x18018ec4d  mov     [rsp+198h+var_80], eax
0x18018ec54  mov     [rsp+198h+var_7C], 1
0x18018ec5c  mov     rax, [rsi]
0x18018ec5f  lea     r9, [rsp+198h+String]
0x18018ec64  lea     r8, aCleartpmifnotr; "ClearTPMIfNotReady"
0x18018ec6b  mov     edx, r15d
0x18018ec6e  mov     rcx, rsi
0x18018ec71  mov     rax, [rax+18h]
0x18018ec75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018ec7a  test    eax, eax
0x18018ec7c  jnz     short loc_18018EC9D
0x18018ec7e  mov     rcx, [rsp+198h+String]; String
0x18018ec83  test    rcx, rcx
0x18018ec86  jz      short loc_18018EC9D
0x18018ec88  call    cs:__imp__wtoi
0x18018ec8e  mov     [rsp+198h+var_78], eax
0x18018ec95  mov     [rsp+198h+var_74], 1
0x18018ec9d  mov     rax, [rsi]
0x18018eca0  lea     r9, [rsp+198h+String]
0x18018eca5  lea     r8, aConfigurewindo_2; "ConfigureWindowsPasswords"
0x18018ecac  mov     edx, r15d
0x18018ecaf  mov     rcx, rsi
0x18018ecb2  mov     rax, [rax+18h]
0x18018ecb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018ecbb  test    eax, eax
0x18018ecbd  jnz     short loc_18018ECDE
0x18018ecbf  mov     rcx, [rsp+198h+String]; String
0x18018ecc4  test    rcx, rcx
0x18018ecc7  jz      short loc_18018ECDE
0x18018ecc9  call    cs:__imp__wtoi
0x18018eccf  mov     [rsp+198h+var_70], eax
0x18018ecd6  mov     [rsp+198h+var_6C], 1
0x18018ecde  mov     rax, [rsi]
0x18018ece1  lea     r9, [rsp+198h+String]
0x18018ece6  lea     r8, aPreventautomat; "PreventAutomaticDeviceEncryptionForAzur"...
0x18018eced  mov     edx, r15d
0x18018ecf0  mov     rcx, rsi
0x18018ecf3  mov     rax, [rax+18h]
0x18018ecf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018ecfc  test    eax, eax
0x18018ecfe  jnz     short loc_18018ED1F
0x18018ed00  mov     rcx, [rsp+198h+String]; String
0x18018ed05  test    rcx, rcx
0x18018ed08  jz      short loc_18018ED1F
0x18018ed0a  call    cs:__imp__wtoi
0x18018ed10  mov     [rsp+198h+var_68], eax
0x18018ed17  mov     [rsp+198h+var_64], 1
0x18018ed1f  mov     rax, [rsi]
0x18018ed22  lea     r9, [rsp+198h+String]
0x18018ed27  lea     r8, aRecoveryenviro; "RecoveryEnvironmentAuthentication"
0x18018ed2e  mov     edx, r15d
0x18018ed31  mov     rcx, rsi
0x18018ed34  mov     rax, [rax+18h]
0x18018ed38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018ed3d  test    eax, eax
0x18018ed3f  jnz     short loc_18018ED60
0x18018ed41  mov     rcx, [rsp+198h+String]; String
0x18018ed46  test    rcx, rcx
0x18018ed49  jz      short loc_18018ED60
0x18018ed4b  call    cs:__imp__wtoi
0x18018ed51  mov     [rsp+198h+var_60], eax
0x18018ed58  mov     [rsp+198h+var_5C], 1
0x18018ed60  mov     rax, [rsi]
0x18018ed63  lea     r9, [rsp+198h+String]
0x18018ed68  lea     r8, aRequiredevicee; "RequireDeviceEncryption"
0x18018ed6f  mov     edx, r15d
0x18018ed72  mov     rcx, rsi
0x18018ed75  mov     rax, [rax+18h]
0x18018ed79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018ed7e  test    eax, eax
0x18018ed80  jnz     short loc_18018EDA1
0x18018ed82  mov     rcx, [rsp+198h+String]; String
0x18018ed87  test    rcx, rcx
0x18018ed8a  jz      short loc_18018EDA1
0x18018ed8c  call    cs:__imp__wtoi
0x18018ed92  mov     [rsp+198h+var_58], eax
0x18018ed99  mov     [rsp+198h+var_54], 1
0x18018eda1  mov     rax, [rsi]
0x18018eda4  lea     r9, [rsp+198h+String]
0x18018eda9  lea     r8, aRequireprovisi; "RequireProvisioningPackageSignature"
0x18018edb0  mov     edx, r15d
0x18018edb3  mov     rcx, rsi
0x18018edb6  mov     rax, [rax+18h]
0x18018edba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018edbf  test    eax, eax
0x18018edc1  jnz     short loc_18018EDE2
0x18018edc3  mov     rcx, [rsp+198h+String]; String
0x18018edc8  test    rcx, rcx
0x18018edcb  jz      short loc_18018EDE2
0x18018edcd  call    cs:__imp__wtoi
0x18018edd3  mov     [rsp+198h+var_50], eax
0x18018edda  mov     [rsp+198h+var_4C], 1
0x18018ede2  mov     rax, [rsi]
0x18018ede5  lea     r9, [rsp+198h+String]
0x18018edea  lea     r8, aRequireretriev; "RequireRetrieveHealthCertificateOnBoot"
0x18018edf1  mov     edx, r15d
0x18018edf4  mov     rcx, rsi
0x18018edf7  mov     rax, [rax+18h]
0x18018edfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018ee00  test    eax, eax
  ... truncated ...
```
