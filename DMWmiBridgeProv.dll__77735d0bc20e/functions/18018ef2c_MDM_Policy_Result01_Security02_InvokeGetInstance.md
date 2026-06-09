# MDM_Policy_Result01_Security02_InvokeGetInstance

- ea: `0x18018ef2c`
- end: `0x18018f47c`
- name: `MDM_Policy_Result01_Security02_InvokeGetInstance`
- size: `1360`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18018e070`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x18018ef2c`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18018f1c9`
- `msvcrt!_wtoi` at `0x18018f200`
- `msvcrt!_wtoi` at `0x18018f237`
- `msvcrt!_wtoi` at `0x18018f26e`
- `msvcrt!_wtoi` at `0x18018f2a5`
- `msvcrt!_wtoi` at `0x18018f2dc`
- `msvcrt!_wtoi` at `0x18018f313`
- `msvcrt!_wtoi` at `0x18018f34a`
- `msvcrt!_wtoi` at `0x18018f381`
- `msvcrt!_wtoi` at `0x18018f1c9`
- `msvcrt!_wtoi` at `0x18018f200`
- `msvcrt!_wtoi` at `0x18018f237`
- `msvcrt!_wtoi` at `0x18018f26e`
- `msvcrt!_wtoi` at `0x18018f2a5`
- `msvcrt!_wtoi` at `0x18018f2dc`
- `msvcrt!_wtoi` at `0x18018f313`
- `msvcrt!_wtoi` at `0x18018f34a`
- `msvcrt!_wtoi` at `0x18018f381`

## string_xrefs

- `0x18018f1e3`: `AllowRemoveProvisioningPackage`
- `0x18018f21a`: `ClearTPMIfNotReady`
- `0x18018f251`: `ConfigureWindowsPasswords`
- `0x18018f288`: `PreventAutomaticDeviceEncryptionForAzureADJoinedDevices`
- `0x18018ef9b`: `MDM_Policy_Result01_Security02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Security02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int v5; // esi
  WmiRequestHandler *v6; // rdi
  wchar_t *String; // [rsp+48h] [rbp-150h] BYREF
  WmiRequestHandler *v9; // [rsp+50h] [rbp-148h] BYREF
  _QWORD v10[5]; // [rsp+58h] [rbp-140h] BYREF
  char v11; // [rsp+80h] [rbp-118h]
  int v12; // [rsp+88h] [rbp-110h] BYREF
  char v13; // [rsp+8Ch] [rbp-10Ch]
  _BYTE v14[16]; // [rsp+90h] [rbp-108h] BYREF
  _DWORD v15[4]; // [rsp+A0h] [rbp-F8h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-E8h] BYREF
  int v17; // [rsp+110h] [rbp-88h]
  char v18; // [rsp+114h] [rbp-84h]
  int v19; // [rsp+118h] [rbp-80h]
  char v20; // [rsp+11Ch] [rbp-7Ch]
  int v21; // [rsp+120h] [rbp-78h]
  char v22; // [rsp+124h] [rbp-74h]
  int v23; // [rsp+128h] [rbp-70h]
  char v24; // [rsp+12Ch] [rbp-6Ch]
  int v25; // [rsp+130h] [rbp-68h]
  char v26; // [rsp+134h] [rbp-64h]
  int v27; // [rsp+138h] [rbp-60h]
  char v28; // [rsp+13Ch] [rbp-5Ch]
  int v29; // [rsp+140h] [rbp-58h]
  char v30; // [rsp+144h] [rbp-54h]
  int v31; // [rsp+148h] [rbp-50h]
  char v32; // [rsp+14Ch] [rbp-4Ch]
  int v33; // [rsp+150h] [rbp-48h]
  char v34; // [rsp+154h] [rbp-44h]

  String = 0;
  memset_0(&instance, 0, 0xA8u);
  v12 = 0;
  v13 = 0;
  v10[0] = &TelemetryEventWriter::`vftable';
  v10[1] = &v12;
  v10[2] = "MDM_Policy_Result01_Security02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180341221,
      v14,
      v4);
  }
  if ( LOBYTE(a2[1].classDecl) && LOBYTE(a2[1].nameSpace) )
  {
    TelemetryEventWriter::WriteStart(
      (TelemetryEventWriter *)v10,
      "GetInstanceStart",
      a2[1].serverName,
      (const unsigned __int16 *)a2[1].ft);
    v9 = 0;
    v5 = CreateRequestHandlerInstance(
           (__int64)self,
           (wchar_t *)a2[1].serverName,
           (const unsigned __int16 *)a2[1].ft,
           (struct WmiNodeInfo *)&MDM_Policy_Result01_Security02_NodeList,
           0xBu,
           0,
           &v9);
    if ( !v5 )
    {
      v10[4] = &v9;
      v11 = 1;
      v6 = v9;
      if ( v9 )
      {
        WmiRequestHandler::SetRequestMIInstance(
          v9,
          a2,
          (struct WmiNodeInfo *)&MDM_Policy_Result01_Security02_NodeList,
          0xBu);
        v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v5 )
        {
          if ( v9 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v9)(v9, 1);
        }
        else
        {
          v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
          if ( v5 )
          {
            if ( v9 )
              (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v9)(v9, 1);
          }
          else
          {
            v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Result01_Security02_rtti, &instance);
            if ( v5 )
            {
              if ( v9 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v9)(v9, 1);
            }
            else
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID(&instance, a2[1].ft);
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, a2[1].serverName);
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowAddProvisioningPackage",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v17 = _wtoi(String);
                v18 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"AllowRemoveProvisioningPackage",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v19 = _wtoi(String);
                v20 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ClearTPMIfNotReady",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v21 = _wtoi(String);
                v22 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ConfigureWindowsPasswords",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v23 = _wtoi(String);
                v24 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"PreventAutomaticDeviceEncryptionForAzureADJoinedDevices",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v25 = _wtoi(String);
                v26 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"RecoveryEnvironmentAuthentication",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v27 = _wtoi(String);
                v28 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"RequireDeviceEncryption",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v29 = _wtoi(String);
                v30 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"RequireProvisioningPackageSignature",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v31 = _wtoi(String);
                v32 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"RequireRetrieveHealthCertificateOnBoot",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v33 = _wtoi(String);
                v34 = 1;
              }
              MI_Instance_Destruct((MI_Instance *)self);
              if ( v9 )
                (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v9)(v9, 1);
              MI_Instance_Destruct(&instance);
            }
          }
        }
      }
      else
      {
        v5 = 1;
      }
    }
  }
  else
  {
    v5 = 4;
  }
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v10, "GetInstanceEnd", v5);
  v12 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      qword_18035C2C8,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return v5;
}

```

## disassembly

```asm
0x18018ef2c  mov     [rsp+arg_10], rbx
0x18018ef31  push    rsi
0x18018ef32  push    rdi
0x18018ef33  push    r12
0x18018ef35  push    r14
0x18018ef37  push    r15
0x18018ef39  sub     rsp, 170h
0x18018ef40  mov     rax, cs:__security_cookie
0x18018ef47  xor     rax, rsp
0x18018ef4a  mov     [rsp+198h+var_38], rax
0x18018ef52  mov     r14, rdx
0x18018ef55  mov     r15, rcx
0x18018ef58  xor     ebx, ebx
0x18018ef5a  mov     [rsp+198h+String], rbx
0x18018ef5f  xor     edx, edx; Val
0x18018ef61  mov     r8d, 0A8h; Size
0x18018ef67  lea     rcx, [rsp+198h+instance]; void *
0x18018ef6f  call    memset_0
0x18018ef74  mov     [rsp+198h+var_110], ebx
0x18018ef7b  mov     [rsp+198h+var_10C], bl
0x18018ef82  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18018ef89  mov     [rsp+198h+var_140], rax
0x18018ef8e  lea     rax, [rsp+198h+var_110]
0x18018ef96  mov     [rsp+198h+var_138], rax
0x18018ef9b  lea     rax, aMdmPolicyResul_141; "MDM_Policy_Result01_Security02"
0x18018efa2  mov     [rsp+198h+var_130], rax
0x18018efa7  lea     rcx, [rsp+198h+var_110]
0x18018efaf  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18018efb4  mov     eax, cs:dword_180380B68
0x18018efba  cmp     eax, 5
0x18018efbd  jbe     short loc_18018F02E
0x18018efbf  mov     rdx, 200000000000h
0x18018efc9  lea     rcx, dword_180380B68
0x18018efd0  call    _tlgKeywordOn
0x18018efd5  test    al, al
0x18018efd7  jz      short loc_18018F02E
0x18018efd9  cmp     [rsp+198h+var_10C], bl
0x18018efe0  jz      short loc_18018F010
0x18018efe2  cmp     [rsp+198h+var_F8], ebx
0x18018efe9  jnz     short loc_18018F006
0x18018efeb  cmp     [rsp+198h+var_F4], ebx
0x18018eff2  jnz     short loc_18018F006
0x18018eff4  cmp     [rsp+198h+var_F0], ebx
0x18018effb  jnz     short loc_18018F006
0x18018effd  cmp     [rsp+198h+var_EC], ebx
0x18018f004  jz      short loc_18018F010
0x18018f006  lea     r9, [rsp+198h+var_F8]
0x18018f00e  jmp     short loc_18018F013
0x18018f010  mov     r9, rbx
0x18018f013  lea     r8, [rsp+198h+var_108]
0x18018f01b  lea     rdx, byte_180341221
0x18018f022  lea     rcx, dword_180380B68
0x18018f029  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18018f02e  cmp     [r14+48h], bl
0x18018f032  jz      loc_18018F3DD
0x18018f038  mov     [rsp+198h+var_158], bl
0x18018f03c  cmp     [r14+58h], bl
0x18018f040  jz      loc_18018F3DD
0x18018f046  mov     r9, [r14+40h]; unsigned __int16 *
0x18018f04a  mov     r8, [r14+50h]; unsigned __int16 *
0x18018f04e  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x18018f055  lea     rcx, [rsp+198h+var_140]; this
0x18018f05a  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18018f05f  nop
0x18018f060  mov     [rsp+198h+var_148], rbx
0x18018f065  lea     rax, [rsp+198h+var_148]
0x18018f06a  mov     [rsp+198h+var_168], rax
0x18018f06f  mov     [rsp+198h+var_170], ebx
0x18018f073  mov     [rsp+198h+var_178], 0Bh
0x18018f07b  lea     r9, ?MDM_Policy_Result01_Security02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Security02_NodeList
0x18018f082  mov     r8, [r14+40h]
0x18018f086  mov     rdx, [r14+50h]
0x18018f08a  mov     rcx, r15
0x18018f08d  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18018f092  mov     esi, eax
0x18018f094  test    eax, eax
0x18018f096  jz      short loc_18018F09D
0x18018f098  jmp     loc_18018F3E2
0x18018f09d  lea     rax, [rsp+198h+var_148]
0x18018f0a2  mov     [rsp+198h+var_120], rax
0x18018f0a7  mov     r12d, 1
0x18018f0ad  mov     [rsp+198h+var_118], r12b
0x18018f0b5  mov     rdi, [rsp+198h+var_148]
0x18018f0ba  test    rdi, rdi
0x18018f0bd  jnz     short loc_18018F0C7
0x18018f0bf  mov     esi, r12d
0x18018f0c2  jmp     loc_18018F3E2
0x18018f0c7  mov     r9d, 0Bh; unsigned int
0x18018f0cd  lea     r8, ?MDM_Policy_Result01_Security02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18018f0d4  mov     rdx, r14; struct _MI_Instance *
0x18018f0d7  mov     rcx, rdi; this
0x18018f0da  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18018f0df  mov     rax, [rdi]
0x18018f0e2  mov     rcx, rdi
0x18018f0e5  mov     rax, [rax+10h]
0x18018f0e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f0ee  mov     esi, eax
0x18018f0f0  test    eax, eax
0x18018f0f2  jz      short loc_18018F112
0x18018f0f4  mov     rcx, [rsp+198h+var_148]
0x18018f0f9  test    rcx, rcx
0x18018f0fc  jz      short loc_18018F10D
0x18018f0fe  mov     rax, [rcx]
0x18018f101  mov     edx, r12d
0x18018f104  mov     rax, [rax]
0x18018f107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f10c  nop
0x18018f10d  jmp     loc_18018F3E2
0x18018f112  mov     rax, [rdi]
0x18018f115  mov     rcx, rdi
0x18018f118  mov     rax, [rax+8]
0x18018f11c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f121  mov     esi, eax
0x18018f123  test    eax, eax
0x18018f125  jz      short loc_18018F145
0x18018f127  mov     rcx, [rsp+198h+var_148]
0x18018f12c  test    rcx, rcx
0x18018f12f  jz      short loc_18018F140
0x18018f131  mov     rax, [rcx]
0x18018f134  mov     edx, r12d
0x18018f137  mov     rax, [rax]
0x18018f13a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f13f  nop
0x18018f140  jmp     loc_18018F3E2
0x18018f145  lea     r8, [rsp+198h+instance]; instance
0x18018f14d  lea     rdx, MDM_Policy_Result01_Security02_rtti; classDecl
0x18018f154  mov     rcx, r15; context
0x18018f157  call    MI_Context_ConstructInstance
0x18018f15c  mov     esi, eax
0x18018f15e  test    eax, eax
0x18018f160  jz      short loc_18018F180
0x18018f162  mov     rcx, [rsp+198h+var_148]
0x18018f167  test    rcx, rcx
0x18018f16a  jz      short loc_18018F17B
0x18018f16c  mov     rax, [rcx]
0x18018f16f  mov     edx, r12d
0x18018f172  mov     rax, [rax]
0x18018f175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f17a  nop
0x18018f17b  jmp     loc_18018F3E2
0x18018f180  mov     [rsp+198h+var_158], r12b
0x18018f185  mov     rdx, [r14+40h]
0x18018f189  lea     rcx, [rsp+198h+instance]
0x18018f191  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18018f196  mov     rdx, [r14+50h]
0x18018f19a  lea     rcx, [rsp+198h+instance]
0x18018f1a2  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18018f1a7  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x18018f1ac  lea     rdx, aAllowaddprovis; "AllowAddProvisioningPackage"
0x18018f1b3  mov     rcx, rdi; this
0x18018f1b6  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18018f1bb  test    eax, eax
0x18018f1bd  jnz     short loc_18018F1DE
0x18018f1bf  mov     rcx, [rsp+198h+String]; String
0x18018f1c4  test    rcx, rcx
0x18018f1c7  jz      short loc_18018F1DE
0x18018f1c9  call    cs:__imp__wtoi
0x18018f1cf  mov     [rsp+198h+var_88], eax
0x18018f1d6  mov     [rsp+198h+var_84], r12b
0x18018f1de  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x18018f1e3  lea     rdx, aAllowremovepro; "AllowRemoveProvisioningPackage"
0x18018f1ea  mov     rcx, rdi; this
0x18018f1ed  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18018f1f2  test    eax, eax
0x18018f1f4  jnz     short loc_18018F215
0x18018f1f6  mov     rcx, [rsp+198h+String]; String
0x18018f1fb  test    rcx, rcx
0x18018f1fe  jz      short loc_18018F215
0x18018f200  call    cs:__imp__wtoi
0x18018f206  mov     [rsp+198h+var_80], eax
0x18018f20d  mov     [rsp+198h+var_7C], r12b
0x18018f215  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x18018f21a  lea     rdx, aCleartpmifnotr; "ClearTPMIfNotReady"
0x18018f221  mov     rcx, rdi; this
0x18018f224  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18018f229  test    eax, eax
0x18018f22b  jnz     short loc_18018F24C
0x18018f22d  mov     rcx, [rsp+198h+String]; String
0x18018f232  test    rcx, rcx
0x18018f235  jz      short loc_18018F24C
0x18018f237  call    cs:__imp__wtoi
0x18018f23d  mov     [rsp+198h+var_78], eax
0x18018f244  mov     [rsp+198h+var_74], r12b
0x18018f24c  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x18018f251  lea     rdx, aConfigurewindo_2; "ConfigureWindowsPasswords"
0x18018f258  mov     rcx, rdi; this
0x18018f25b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18018f260  test    eax, eax
0x18018f262  jnz     short loc_18018F283
0x18018f264  mov     rcx, [rsp+198h+String]; String
0x18018f269  test    rcx, rcx
0x18018f26c  jz      short loc_18018F283
0x18018f26e  call    cs:__imp__wtoi
0x18018f274  mov     [rsp+198h+var_70], eax
0x18018f27b  mov     [rsp+198h+var_6C], r12b
0x18018f283  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x18018f288  lea     rdx, aPreventautomat; "PreventAutomaticDeviceEncryptionForAzur"...
0x18018f28f  mov     rcx, rdi; this
0x18018f292  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18018f297  test    eax, eax
0x18018f299  jnz     short loc_18018F2BA
0x18018f29b  mov     rcx, [rsp+198h+String]; String
0x18018f2a0  test    rcx, rcx
0x18018f2a3  jz      short loc_18018F2BA
0x18018f2a5  call    cs:__imp__wtoi
0x18018f2ab  mov     [rsp+198h+var_68], eax
0x18018f2b2  mov     [rsp+198h+var_64], r12b
0x18018f2ba  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x18018f2bf  lea     rdx, aRecoveryenviro; "RecoveryEnvironmentAuthentication"
0x18018f2c6  mov     rcx, rdi; this
0x18018f2c9  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18018f2ce  test    eax, eax
0x18018f2d0  jnz     short loc_18018F2F1
0x18018f2d2  mov     rcx, [rsp+198h+String]; String
0x18018f2d7  test    rcx, rcx
0x18018f2da  jz      short loc_18018F2F1
0x18018f2dc  call    cs:__imp__wtoi
0x18018f2e2  mov     [rsp+198h+var_60], eax
0x18018f2e9  mov     [rsp+198h+var_5C], r12b
0x18018f2f1  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x18018f2f6  lea     rdx, aRequiredevicee; "RequireDeviceEncryption"
0x18018f2fd  mov     rcx, rdi; this
0x18018f300  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18018f305  test    eax, eax
0x18018f307  jnz     short loc_18018F328
0x18018f309  mov     rcx, [rsp+198h+String]; String
0x18018f30e  test    rcx, rcx
0x18018f311  jz      short loc_18018F328
0x18018f313  call    cs:__imp__wtoi
0x18018f319  mov     [rsp+198h+var_58], eax
0x18018f320  mov     [rsp+198h+var_54], r12b
0x18018f328  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x18018f32d  lea     rdx, aRequireprovisi; "RequireProvisioningPackageSignature"
0x18018f334  mov     rcx, rdi; this
0x18018f337  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18018f33c  test    eax, eax
0x18018f33e  jnz     short loc_18018F35F
0x18018f340  mov     rcx, [rsp+198h+String]; String
0x18018f345  test    rcx, rcx
0x18018f348  jz      short loc_18018F35F
0x18018f34a  call    cs:__imp__wtoi
0x18018f350  mov     [rsp+198h+var_50], eax
0x18018f357  mov     [rsp+198h+var_4C], r12b
0x18018f35f  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x18018f364  lea     rdx, aRequireretriev; "RequireRetrieveHealthCertificateOnBoot"
0x18018f36b  mov     rcx, rdi; this
0x18018f36e  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18018f373  test    eax, eax
0x18018f375  jnz     short loc_18018F396
0x18018f377  mov     rcx, [rsp+198h+String]; String
0x18018f37c  test    rcx, rcx
0x18018f37f  jz      short loc_18018F396
0x18018f381  call    cs:__imp__wtoi
0x18018f387  mov     [rsp+198h+var_48], eax
0x18018f38e  mov     [rsp+198h+var_44], r12b
0x18018f396  lea     rdx, [rsp+198h+instance]
0x18018f39e  mov     rcx, r15; self
0x18018f3a1  call    MI_Instance_Destruct
0x18018f3a6  nop
0x18018f3a7  mov     rcx, [rsp+198h+var_148]
0x18018f3ac  test    rcx, rcx
0x18018f3af  jz      short loc_18018F3C0
0x18018f3b1  mov     rax, [rcx]
0x18018f3b4  mov     edx, r12d
0x18018f3b7  mov     rax, [rax]
0x18018f3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018f3bf  nop
0x18018f3c0  jmp     short loc_18018F3CE
0x18018f3c2  xor     ebx, ebx
0x18018f3c4  mov     esi, dword ptr [rsp+198h+String]
0x18018f3c8  cmp     [rsp+198h+var_158], bl
0x18018f3cc  jz      short loc_18018F3E2
0x18018f3ce  lea     rcx, [rsp+198h+instance]; self
0x18018f3d6  call    MI_Instance_Destruct
0x18018f3db  jmp     short loc_18018F3E2
0x18018f3dd  mov     esi, 4
0x18018f3e2  mov     r8d, esi; int
0x18018f3e5  lea     rdx, aGetinstanceend; "GetInstanceEnd"
0x18018f3ec  lea     rcx, [rsp+198h+var_140]; this
0x18018f3f1  call    ?WriteEnd@TelemetryEventWriter@@QEAAXPEBDH@Z; TelemetryEventWriter::WriteEnd(char const *,int)
0x18018f3f6  mov     [rsp+198h+var_110], 2
0x18018f401  mov     eax, cs:dword_180380B68
0x18018f407  cmp     eax, 5
0x18018f40a  jbe     short loc_18018F445
0x18018f40c  mov     rdx, 200000000000h
0x18018f416  lea     rcx, dword_180380B68
0x18018f41d  call    _tlgKeywordOn
0x18018f422  test    al, al
0x18018f424  jz      short loc_18018F445
0x18018f426  xor     r9d, r9d
0x18018f429  lea     r8, [rsp+198h+var_108]
0x18018f431  lea     rdx, qword_18035C2C8
0x18018f438  lea     rcx, dword_180380B68
0x18018f43f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18018f444  nop
0x18018f445  lea     rcx, [rsp+198h+var_110]
0x18018f44d  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(void)
0x18018f452  mov     eax, esi
0x18018f454  mov     rcx, [rsp+198h+var_38]
0x18018f45c  xor     rcx, rsp; StackCookie
  ... truncated ...
```
