# MDM_Policy_Config01_Security02_InvokeEnumerateInstances

- ea: `0x1800d7534`
- end: `0x1800d7b65`
- name: `MDM_Policy_Config01_Security02_InvokeEnumerateInstances`
- size: `1585`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d6c70`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800d7534`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800d7846`
- `msvcrt!_wtoi` at `0x1800d7887`
- `msvcrt!_wtoi` at `0x1800d78c8`
- `msvcrt!_wtoi` at `0x1800d7909`
- `msvcrt!_wtoi` at `0x1800d794a`
- `msvcrt!_wtoi` at `0x1800d798b`
- `msvcrt!_wtoi` at `0x1800d79cc`
- `msvcrt!_wtoi` at `0x1800d7a0d`
- `msvcrt!_wtoi` at `0x1800d7a4e`
- `msvcrt!_wtoi` at `0x1800d7846`
- `msvcrt!_wtoi` at `0x1800d7887`
- `msvcrt!_wtoi` at `0x1800d78c8`
- `msvcrt!_wtoi` at `0x1800d7909`
- `msvcrt!_wtoi` at `0x1800d794a`
- `msvcrt!_wtoi` at `0x1800d798b`
- `msvcrt!_wtoi` at `0x1800d79cc`
- `msvcrt!_wtoi` at `0x1800d7a0d`
- `msvcrt!_wtoi` at `0x1800d7a4e`

## string_xrefs

- `0x1800d7863`: `AllowRemoveProvisioningPackage`
- `0x1800d78a4`: `ClearTPMIfNotReady`
- `0x1800d78e5`: `ConfigureWindowsPasswords`
- `0x1800d7926`: `PreventAutomaticDeviceEncryptionForAzureADJoinedDevices`
- `0x1800d7788`: `./Vendor/MSFT/Policy/Config`
- `0x1800d75af`: `MDM_Policy_Config01_Security02`
- `0x1800d77c1`: `Security`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MDM_Policy_Config01_Security02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  wil *v6; // rcx
  unsigned int v7; // r14d
  WmiRequestHandlerAdd *v8; // rsi
  unsigned int i; // r15d
  const char *v11; // rax
  int v12; // eax
  wchar_t *String; // [rsp+48h] [rbp-150h] BYREF
  WmiRequestHandlerAdd *v14; // [rsp+50h] [rbp-148h] BYREF
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
    v7 = CreateRequestHandlerInstance(
           (__int64)self,
           0,
           0,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_Security02_NodeList,
           0xBu,
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
              v7 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Security02_rtti, &instance);
              if ( v7 )
              {
                v6 = v14;
                if ( v14 )
                {
                  (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v14)(v14, 1);
                  v14 = 0;
                }
                goto LABEL_73;
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
                      L"Security",
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
                        L"AllowAddProvisioningPackage",
                        &String)
                  && String )
                {
                  v23 = _wtoi(String);
                  v24 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"AllowRemoveProvisioningPackage",
                        &String)
                  && String )
                {
                  v25 = _wtoi(String);
                  v26 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ClearTPMIfNotReady",
                        &String)
                  && String )
                {
                  v27 = _wtoi(String);
                  v28 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"ConfigureWindowsPasswords",
                        &String)
                  && String )
                {
                  v29 = _wtoi(String);
                  v30 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"PreventAutomaticDeviceEncryptionForAzureADJoinedDevices",
                        &String)
                  && String )
                {
                  v31 = _wtoi(String);
                  v32 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"RecoveryEnvironmentAuthentication",
                        &String)
                  && String )
                {
                  v33 = _wtoi(String);
                  v34 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"RequireDeviceEncryption",
                        &String)
                  && String )
                {
                  v35 = _wtoi(String);
                  v36 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
                        v8,
                        i,
                        L"RequireProvisioningPackageSignature",
                        &String)
                  && String )
                {
                  v37 = _wtoi(String);
                  v38 = 1;
                }
                if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v8 + 24LL))(
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
  return v7;
}

```

## disassembly

```asm
0x1800d7534  mov     [rsp+arg_8], rbx
0x1800d7539  mov     [rsp+arg_10], rsi
0x1800d753e  push    rdi
0x1800d753f  push    r12
0x1800d7541  push    r13
0x1800d7543  push    r14
0x1800d7545  push    r15
0x1800d7547  sub     rsp, 170h
0x1800d754e  mov     rax, cs:__security_cookie
0x1800d7555  xor     rax, rsp
0x1800d7558  mov     [rsp+198h+var_38], rax
0x1800d7560  mov     r13b, dl
0x1800d7563  mov     r12, rcx
0x1800d7566  xor     edx, edx; Val
0x1800d7568  mov     r8d, 0A8h; Size
0x1800d756e  lea     rcx, [rsp+198h+instance]; void *
0x1800d7576  call    memset_0
0x1800d757b  xor     edi, edi
0x1800d757d  mov     [rsp+198h+var_158], dil
0x1800d7582  mov     [rsp+198h+String], rdi
0x1800d7587  mov     [rsp+198h+var_110], edi
0x1800d758e  mov     [rsp+198h+var_10C], dil
0x1800d7596  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800d759d  mov     [rsp+198h+var_140], rax
0x1800d75a2  lea     rax, [rsp+198h+var_110]
0x1800d75aa  mov     [rsp+198h+var_138], rax
0x1800d75af  lea     rax, aMdmPolicyConfi_98; "MDM_Policy_Config01_Security02"
0x1800d75b6  mov     [rsp+198h+var_130], rax
0x1800d75bb  lea     rcx, [rsp+198h+var_110]
0x1800d75c3  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800d75c8  mov     eax, cs:dword_180380B68
0x1800d75ce  cmp     eax, 5
0x1800d75d1  jbe     short loc_1800D7643
0x1800d75d3  mov     rdx, 200000000000h
0x1800d75dd  lea     rcx, dword_180380B68
0x1800d75e4  call    _tlgKeywordOn
0x1800d75e9  test    al, al
0x1800d75eb  jz      short loc_1800D7643
0x1800d75ed  cmp     [rsp+198h+var_10C], dil
0x1800d75f5  jz      short loc_1800D7625
0x1800d75f7  cmp     [rsp+198h+var_F8], edi
0x1800d75fe  jnz     short loc_1800D761B
0x1800d7600  cmp     [rsp+198h+var_F4], edi
0x1800d7607  jnz     short loc_1800D761B
0x1800d7609  cmp     [rsp+198h+var_F0], edi
0x1800d7610  jnz     short loc_1800D761B
0x1800d7612  cmp     [rsp+198h+var_EC], edi
0x1800d7619  jz      short loc_1800D7625
0x1800d761b  lea     r9, [rsp+198h+var_F8]
0x1800d7623  jmp     short loc_1800D7628
0x1800d7625  mov     r9, rdi
0x1800d7628  lea     r8, [rsp+198h+var_108]
0x1800d7630  lea     rdx, qword_180367A70
0x1800d7637  lea     rcx, dword_180380B68
0x1800d763e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800d7643  lea     rcx, [rsp+198h+var_140]; this
0x1800d7648  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800d764d  nop
0x1800d764e  mov     [rsp+198h+var_148], rdi
0x1800d7653  lea     rax, [rsp+198h+var_148]
0x1800d7658  mov     [rsp+198h+var_168], rax
0x1800d765d  mov     [rsp+198h+var_170], 2
0x1800d7665  mov     [rsp+198h+var_178], 0Bh
0x1800d766d  lea     r9, ?MDM_Policy_Config01_Security02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Security02_NodeList
0x1800d7674  xor     r8d, r8d
0x1800d7677  xor     edx, edx
0x1800d7679  mov     rcx, r12
0x1800d767c  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800d7681  mov     r14d, eax
0x1800d7684  test    eax, eax
0x1800d7686  jz      short loc_1800D768D
0x1800d7688  jmp     loc_1800D7AC5
0x1800d768d  lea     rbx, [rsp+198h+var_148]
0x1800d7692  mov     [rsp+198h+var_120], rbx
0x1800d7697  mov     r15d, 1
0x1800d769d  mov     [rsp+198h+var_118], r15b
0x1800d76a5  mov     rsi, [rsp+198h+var_148]
0x1800d76aa  test    rsi, rsi
0x1800d76ad  jnz     short loc_1800D76B7
0x1800d76af  mov     r14d, r15d
0x1800d76b2  jmp     loc_1800D7AC5
0x1800d76b7  mov     rax, [rsi]
0x1800d76ba  mov     rcx, rsi
0x1800d76bd  mov     rax, [rax+10h]
0x1800d76c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d76c6  mov     r14d, eax
0x1800d76c9  test    eax, eax
0x1800d76cb  jz      short loc_1800D76EB
0x1800d76cd  mov     rcx, [rsp+198h+var_148]
0x1800d76d2  test    rcx, rcx
0x1800d76d5  jz      short loc_1800D76E6
0x1800d76d7  mov     rax, [rcx]
0x1800d76da  mov     edx, r15d
0x1800d76dd  mov     rax, [rax]
0x1800d76e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d76e5  nop
0x1800d76e6  jmp     loc_1800D7AC5
0x1800d76eb  mov     rax, [rsi]
0x1800d76ee  mov     rcx, rsi
0x1800d76f1  mov     rax, [rax+8]
0x1800d76f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d76fa  mov     r14d, eax
0x1800d76fd  test    eax, eax
0x1800d76ff  jz      short loc_1800D771F
0x1800d7701  mov     rcx, [rsp+198h+var_148]
0x1800d7706  test    rcx, rcx
0x1800d7709  jz      short loc_1800D771A
0x1800d770b  mov     rax, [rcx]
0x1800d770e  mov     edx, r15d
0x1800d7711  mov     rax, [rax]
0x1800d7714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7719  nop
0x1800d771a  jmp     loc_1800D7AC5
0x1800d771f  mov     r15d, edi
0x1800d7722  mov     rax, [rsi+108h]
0x1800d7729  sub     rax, [rsi+100h]
0x1800d7730  sar     rax, 4
0x1800d7734  cmp     r15d, eax
0x1800d7737  jnb     loc_1800D7A8D
0x1800d773d  lea     r8, [rsp+198h+instance]; instance
0x1800d7745  lea     rdx, MDM_Policy_Config01_Security02_rtti; classDecl
0x1800d774c  mov     rcx, r12; context
0x1800d774f  call    MI_Context_ConstructInstance
0x1800d7754  mov     r14d, eax
0x1800d7757  test    eax, eax
0x1800d7759  jz      short loc_1800D777B
0x1800d775b  mov     rcx, [rbx]
0x1800d775e  test    rcx, rcx
0x1800d7761  jz      short loc_1800D7776
0x1800d7763  mov     rax, [rcx]
0x1800d7766  mov     edx, 1
0x1800d776b  mov     rax, [rax]
0x1800d776e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7773  mov     [rbx], rdi
0x1800d7776  jmp     loc_1800D7AC5
0x1800d777b  mov     [rsp+198h+var_158], 1
0x1800d7780  mov     rax, [rsi]
0x1800d7783  lea     r9, [rsp+198h+String]
0x1800d7788  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800d778f  mov     edx, r15d
0x1800d7792  mov     rcx, rsi
0x1800d7795  mov     rax, [rax+18h]
0x1800d7799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d779e  test    eax, eax
0x1800d77a0  jnz     short loc_1800D77B9
0x1800d77a2  mov     rdx, [rsp+198h+String]
0x1800d77a7  test    rdx, rdx
0x1800d77aa  jz      short loc_1800D77B9
0x1800d77ac  lea     rcx, [rsp+198h+instance]
0x1800d77b4  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800d77b9  mov     rax, [rsi]
0x1800d77bc  lea     r9, [rsp+198h+String]
0x1800d77c1  lea     r8, aSecurity; "Security"
0x1800d77c8  mov     edx, r15d
0x1800d77cb  mov     rcx, rsi
0x1800d77ce  mov     rax, [rax+18h]
0x1800d77d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d77d7  test    eax, eax
0x1800d77d9  jnz     short loc_1800D77F2
0x1800d77db  mov     rdx, [rsp+198h+String]
0x1800d77e0  test    rdx, rdx
0x1800d77e3  jz      short loc_1800D77F2
0x1800d77e5  lea     rcx, [rsp+198h+instance]
0x1800d77ed  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800d77f2  cmp     r13b, 1
0x1800d77f6  jnz     short loc_1800D781A
0x1800d77f8  lea     rdx, [rsp+198h+instance]
0x1800d7800  mov     rcx, r12; self
0x1800d7803  call    MI_Instance_Destruct
0x1800d7808  lea     rcx, [rsp+198h+instance]; self
0x1800d7810  call    MI_Instance_Destruct
0x1800d7815  jmp     loc_1800D7A80
0x1800d781a  mov     rax, [rsi]
0x1800d781d  lea     r9, [rsp+198h+String]
0x1800d7822  lea     r8, aAllowaddprovis; "AllowAddProvisioningPackage"
0x1800d7829  mov     edx, r15d
0x1800d782c  mov     rcx, rsi
0x1800d782f  mov     rax, [rax+18h]
0x1800d7833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7838  test    eax, eax
0x1800d783a  jnz     short loc_1800D785B
0x1800d783c  mov     rcx, [rsp+198h+String]; String
0x1800d7841  test    rcx, rcx
0x1800d7844  jz      short loc_1800D785B
0x1800d7846  call    cs:__imp__wtoi
0x1800d784c  mov     [rsp+198h+var_88], eax
0x1800d7853  mov     [rsp+198h+var_84], 1
0x1800d785b  mov     rax, [rsi]
0x1800d785e  lea     r9, [rsp+198h+String]
0x1800d7863  lea     r8, aAllowremovepro; "AllowRemoveProvisioningPackage"
0x1800d786a  mov     edx, r15d
0x1800d786d  mov     rcx, rsi
0x1800d7870  mov     rax, [rax+18h]
0x1800d7874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7879  test    eax, eax
0x1800d787b  jnz     short loc_1800D789C
0x1800d787d  mov     rcx, [rsp+198h+String]; String
0x1800d7882  test    rcx, rcx
0x1800d7885  jz      short loc_1800D789C
0x1800d7887  call    cs:__imp__wtoi
0x1800d788d  mov     [rsp+198h+var_80], eax
0x1800d7894  mov     [rsp+198h+var_7C], 1
0x1800d789c  mov     rax, [rsi]
0x1800d789f  lea     r9, [rsp+198h+String]
0x1800d78a4  lea     r8, aCleartpmifnotr; "ClearTPMIfNotReady"
0x1800d78ab  mov     edx, r15d
0x1800d78ae  mov     rcx, rsi
0x1800d78b1  mov     rax, [rax+18h]
0x1800d78b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d78ba  test    eax, eax
0x1800d78bc  jnz     short loc_1800D78DD
0x1800d78be  mov     rcx, [rsp+198h+String]; String
0x1800d78c3  test    rcx, rcx
0x1800d78c6  jz      short loc_1800D78DD
0x1800d78c8  call    cs:__imp__wtoi
0x1800d78ce  mov     [rsp+198h+var_78], eax
0x1800d78d5  mov     [rsp+198h+var_74], 1
0x1800d78dd  mov     rax, [rsi]
0x1800d78e0  lea     r9, [rsp+198h+String]
0x1800d78e5  lea     r8, aConfigurewindo_2; "ConfigureWindowsPasswords"
0x1800d78ec  mov     edx, r15d
0x1800d78ef  mov     rcx, rsi
0x1800d78f2  mov     rax, [rax+18h]
0x1800d78f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d78fb  test    eax, eax
0x1800d78fd  jnz     short loc_1800D791E
0x1800d78ff  mov     rcx, [rsp+198h+String]; String
0x1800d7904  test    rcx, rcx
0x1800d7907  jz      short loc_1800D791E
0x1800d7909  call    cs:__imp__wtoi
0x1800d790f  mov     [rsp+198h+var_70], eax
0x1800d7916  mov     [rsp+198h+var_6C], 1
0x1800d791e  mov     rax, [rsi]
0x1800d7921  lea     r9, [rsp+198h+String]
0x1800d7926  lea     r8, aPreventautomat; "PreventAutomaticDeviceEncryptionForAzur"...
0x1800d792d  mov     edx, r15d
0x1800d7930  mov     rcx, rsi
0x1800d7933  mov     rax, [rax+18h]
0x1800d7937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d793c  test    eax, eax
0x1800d793e  jnz     short loc_1800D795F
0x1800d7940  mov     rcx, [rsp+198h+String]; String
0x1800d7945  test    rcx, rcx
0x1800d7948  jz      short loc_1800D795F
0x1800d794a  call    cs:__imp__wtoi
0x1800d7950  mov     [rsp+198h+var_68], eax
0x1800d7957  mov     [rsp+198h+var_64], 1
0x1800d795f  mov     rax, [rsi]
0x1800d7962  lea     r9, [rsp+198h+String]
0x1800d7967  lea     r8, aRecoveryenviro; "RecoveryEnvironmentAuthentication"
0x1800d796e  mov     edx, r15d
0x1800d7971  mov     rcx, rsi
0x1800d7974  mov     rax, [rax+18h]
0x1800d7978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d797d  test    eax, eax
0x1800d797f  jnz     short loc_1800D79A0
0x1800d7981  mov     rcx, [rsp+198h+String]; String
0x1800d7986  test    rcx, rcx
0x1800d7989  jz      short loc_1800D79A0
0x1800d798b  call    cs:__imp__wtoi
0x1800d7991  mov     [rsp+198h+var_60], eax
0x1800d7998  mov     [rsp+198h+var_5C], 1
0x1800d79a0  mov     rax, [rsi]
0x1800d79a3  lea     r9, [rsp+198h+String]
0x1800d79a8  lea     r8, aRequiredevicee; "RequireDeviceEncryption"
0x1800d79af  mov     edx, r15d
0x1800d79b2  mov     rcx, rsi
0x1800d79b5  mov     rax, [rax+18h]
0x1800d79b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d79be  test    eax, eax
0x1800d79c0  jnz     short loc_1800D79E1
0x1800d79c2  mov     rcx, [rsp+198h+String]; String
0x1800d79c7  test    rcx, rcx
0x1800d79ca  jz      short loc_1800D79E1
0x1800d79cc  call    cs:__imp__wtoi
0x1800d79d2  mov     [rsp+198h+var_58], eax
0x1800d79d9  mov     [rsp+198h+var_54], 1
0x1800d79e1  mov     rax, [rsi]
0x1800d79e4  lea     r9, [rsp+198h+String]
0x1800d79e9  lea     r8, aRequireprovisi; "RequireProvisioningPackageSignature"
0x1800d79f0  mov     edx, r15d
0x1800d79f3  mov     rcx, rsi
0x1800d79f6  mov     rax, [rax+18h]
0x1800d79fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d79ff  test    eax, eax
0x1800d7a01  jnz     short loc_1800D7A22
0x1800d7a03  mov     rcx, [rsp+198h+String]; String
0x1800d7a08  test    rcx, rcx
0x1800d7a0b  jz      short loc_1800D7A22
0x1800d7a0d  call    cs:__imp__wtoi
0x1800d7a13  mov     [rsp+198h+var_50], eax
0x1800d7a1a  mov     [rsp+198h+var_4C], 1
0x1800d7a22  mov     rax, [rsi]
0x1800d7a25  lea     r9, [rsp+198h+String]
0x1800d7a2a  lea     r8, aRequireretriev; "RequireRetrieveHealthCertificateOnBoot"
0x1800d7a31  mov     edx, r15d
0x1800d7a34  mov     rcx, rsi
0x1800d7a37  mov     rax, [rax+18h]
0x1800d7a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7a40  test    eax, eax
  ... truncated ...
```
