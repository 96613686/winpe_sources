# MDM_Policy_Config01_Security02_InvokeGetInstance

- ea: `0x1800d7b6c`
- end: `0x1800d80bc`
- name: `MDM_Policy_Config01_Security02_InvokeGetInstance`
- size: `1360`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d6cb0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800d7b6c`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800d7e09`
- `msvcrt!_wtoi` at `0x1800d7e40`
- `msvcrt!_wtoi` at `0x1800d7e77`
- `msvcrt!_wtoi` at `0x1800d7eae`
- `msvcrt!_wtoi` at `0x1800d7ee5`
- `msvcrt!_wtoi` at `0x1800d7f1c`
- `msvcrt!_wtoi` at `0x1800d7f53`
- `msvcrt!_wtoi` at `0x1800d7f8a`
- `msvcrt!_wtoi` at `0x1800d7fc1`
- `msvcrt!_wtoi` at `0x1800d7e09`
- `msvcrt!_wtoi` at `0x1800d7e40`
- `msvcrt!_wtoi` at `0x1800d7e77`
- `msvcrt!_wtoi` at `0x1800d7eae`
- `msvcrt!_wtoi` at `0x1800d7ee5`
- `msvcrt!_wtoi` at `0x1800d7f1c`
- `msvcrt!_wtoi` at `0x1800d7f53`
- `msvcrt!_wtoi` at `0x1800d7f8a`
- `msvcrt!_wtoi` at `0x1800d7fc1`

## string_xrefs

- `0x1800d7e23`: `AllowRemoveProvisioningPackage`
- `0x1800d7e5a`: `ClearTPMIfNotReady`
- `0x1800d7e91`: `ConfigureWindowsPasswords`
- `0x1800d7ec8`: `PreventAutomaticDeviceEncryptionForAzureADJoinedDevices`
- `0x1800d7bdb`: `MDM_Policy_Config01_Security02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Security02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
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
  v10[2] = "MDM_Policy_Config01_Security02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      word_180354682,
      v14,
      v4);
  }
  if ( !LOBYTE(a2[1].classDecl) || !LOBYTE(a2[1].nameSpace) )
  {
    v5 = 4;
    goto LABEL_56;
  }
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
         (struct WmiNodeInfo *)&MDM_Policy_Config01_Security02_NodeList,
         0xBu,
         0,
         &v9);
  if ( !v5 )
  {
    v10[4] = &v9;
    v11 = 1;
    v6 = v9;
    if ( !v9 )
    {
      v5 = 1;
      goto LABEL_56;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v9,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_Security02_NodeList,
      0xBu);
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v9 )
        goto LABEL_56;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v9)(v9, 1);
      goto LABEL_56;
    }
    v5 = (*(__int64 (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( v5 )
    {
      if ( !v9 )
        goto LABEL_56;
      goto LABEL_24;
    }
    v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_Security02_rtti, &instance);
    if ( v5 )
    {
      if ( !v9 )
        goto LABEL_56;
      goto LABEL_24;
    }
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
LABEL_56:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v10, "GetInstanceEnd", v5);
  v12 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180361641,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return v5;
}

```

## disassembly

```asm
0x1800d7b6c  mov     [rsp+arg_10], rbx
0x1800d7b71  push    rsi
0x1800d7b72  push    rdi
0x1800d7b73  push    r12
0x1800d7b75  push    r14
0x1800d7b77  push    r15
0x1800d7b79  sub     rsp, 170h
0x1800d7b80  mov     rax, cs:__security_cookie
0x1800d7b87  xor     rax, rsp
0x1800d7b8a  mov     [rsp+198h+var_38], rax
0x1800d7b92  mov     r14, rdx
0x1800d7b95  mov     r15, rcx
0x1800d7b98  xor     ebx, ebx
0x1800d7b9a  mov     [rsp+198h+String], rbx
0x1800d7b9f  xor     edx, edx; Val
0x1800d7ba1  mov     r8d, 0A8h; Size
0x1800d7ba7  lea     rcx, [rsp+198h+instance]; void *
0x1800d7baf  call    memset_0
0x1800d7bb4  mov     [rsp+198h+var_110], ebx
0x1800d7bbb  mov     [rsp+198h+var_10C], bl
0x1800d7bc2  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800d7bc9  mov     [rsp+198h+var_140], rax
0x1800d7bce  lea     rax, [rsp+198h+var_110]
0x1800d7bd6  mov     [rsp+198h+var_138], rax
0x1800d7bdb  lea     rax, aMdmPolicyConfi_98; "MDM_Policy_Config01_Security02"
0x1800d7be2  mov     [rsp+198h+var_130], rax
0x1800d7be7  lea     rcx, [rsp+198h+var_110]
0x1800d7bef  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800d7bf4  mov     eax, cs:dword_180380B68
0x1800d7bfa  cmp     eax, 5
0x1800d7bfd  jbe     short loc_1800D7C6E
0x1800d7bff  mov     rdx, 200000000000h
0x1800d7c09  lea     rcx, dword_180380B68
0x1800d7c10  call    _tlgKeywordOn
0x1800d7c15  test    al, al
0x1800d7c17  jz      short loc_1800D7C6E
0x1800d7c19  cmp     [rsp+198h+var_10C], bl
0x1800d7c20  jz      short loc_1800D7C50
0x1800d7c22  cmp     [rsp+198h+var_F8], ebx
0x1800d7c29  jnz     short loc_1800D7C46
0x1800d7c2b  cmp     [rsp+198h+var_F4], ebx
0x1800d7c32  jnz     short loc_1800D7C46
0x1800d7c34  cmp     [rsp+198h+var_F0], ebx
0x1800d7c3b  jnz     short loc_1800D7C46
0x1800d7c3d  cmp     [rsp+198h+var_EC], ebx
0x1800d7c44  jz      short loc_1800D7C50
0x1800d7c46  lea     r9, [rsp+198h+var_F8]
0x1800d7c4e  jmp     short loc_1800D7C53
0x1800d7c50  mov     r9, rbx
0x1800d7c53  lea     r8, [rsp+198h+var_108]
0x1800d7c5b  lea     rdx, word_180354682
0x1800d7c62  lea     rcx, dword_180380B68
0x1800d7c69  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800d7c6e  cmp     [r14+48h], bl
0x1800d7c72  jz      loc_1800D801D
0x1800d7c78  mov     [rsp+198h+var_158], bl
0x1800d7c7c  cmp     [r14+58h], bl
0x1800d7c80  jz      loc_1800D801D
0x1800d7c86  mov     r9, [r14+40h]; unsigned __int16 *
0x1800d7c8a  mov     r8, [r14+50h]; unsigned __int16 *
0x1800d7c8e  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1800d7c95  lea     rcx, [rsp+198h+var_140]; this
0x1800d7c9a  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800d7c9f  nop
0x1800d7ca0  mov     [rsp+198h+var_148], rbx
0x1800d7ca5  lea     rax, [rsp+198h+var_148]
0x1800d7caa  mov     [rsp+198h+var_168], rax
0x1800d7caf  mov     [rsp+198h+var_170], ebx
0x1800d7cb3  mov     [rsp+198h+var_178], 0Bh
0x1800d7cbb  lea     r9, ?MDM_Policy_Config01_Security02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Security02_NodeList
0x1800d7cc2  mov     r8, [r14+40h]
0x1800d7cc6  mov     rdx, [r14+50h]
0x1800d7cca  mov     rcx, r15
0x1800d7ccd  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800d7cd2  mov     esi, eax
0x1800d7cd4  test    eax, eax
0x1800d7cd6  jz      short loc_1800D7CDD
0x1800d7cd8  jmp     loc_1800D8022
0x1800d7cdd  lea     rax, [rsp+198h+var_148]
0x1800d7ce2  mov     [rsp+198h+var_120], rax
0x1800d7ce7  mov     r12d, 1
0x1800d7ced  mov     [rsp+198h+var_118], r12b
0x1800d7cf5  mov     rdi, [rsp+198h+var_148]
0x1800d7cfa  test    rdi, rdi
0x1800d7cfd  jnz     short loc_1800D7D07
0x1800d7cff  mov     esi, r12d
0x1800d7d02  jmp     loc_1800D8022
0x1800d7d07  mov     r9d, 0Bh; unsigned int
0x1800d7d0d  lea     r8, ?MDM_Policy_Config01_Security02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800d7d14  mov     rdx, r14; struct _MI_Instance *
0x1800d7d17  mov     rcx, rdi; this
0x1800d7d1a  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800d7d1f  mov     rax, [rdi]
0x1800d7d22  mov     rcx, rdi
0x1800d7d25  mov     rax, [rax+10h]
0x1800d7d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7d2e  mov     esi, eax
0x1800d7d30  test    eax, eax
0x1800d7d32  jz      short loc_1800D7D52
0x1800d7d34  mov     rcx, [rsp+198h+var_148]
0x1800d7d39  test    rcx, rcx
0x1800d7d3c  jz      short loc_1800D7D4D
0x1800d7d3e  mov     rax, [rcx]
0x1800d7d41  mov     edx, r12d
0x1800d7d44  mov     rax, [rax]
0x1800d7d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7d4c  nop
0x1800d7d4d  jmp     loc_1800D8022
0x1800d7d52  mov     rax, [rdi]
0x1800d7d55  mov     rcx, rdi
0x1800d7d58  mov     rax, [rax+8]
0x1800d7d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7d61  mov     esi, eax
0x1800d7d63  test    eax, eax
0x1800d7d65  jz      short loc_1800D7D85
0x1800d7d67  mov     rcx, [rsp+198h+var_148]
0x1800d7d6c  test    rcx, rcx
0x1800d7d6f  jz      short loc_1800D7D80
0x1800d7d71  mov     rax, [rcx]
0x1800d7d74  mov     edx, r12d
0x1800d7d77  mov     rax, [rax]
0x1800d7d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7d7f  nop
0x1800d7d80  jmp     loc_1800D8022
0x1800d7d85  lea     r8, [rsp+198h+instance]; instance
0x1800d7d8d  lea     rdx, MDM_Policy_Config01_Security02_rtti; classDecl
0x1800d7d94  mov     rcx, r15; context
0x1800d7d97  call    MI_Context_ConstructInstance
0x1800d7d9c  mov     esi, eax
0x1800d7d9e  test    eax, eax
0x1800d7da0  jz      short loc_1800D7DC0
0x1800d7da2  mov     rcx, [rsp+198h+var_148]
0x1800d7da7  test    rcx, rcx
0x1800d7daa  jz      short loc_1800D7DBB
0x1800d7dac  mov     rax, [rcx]
0x1800d7daf  mov     edx, r12d
0x1800d7db2  mov     rax, [rax]
0x1800d7db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7dba  nop
0x1800d7dbb  jmp     loc_1800D8022
0x1800d7dc0  mov     [rsp+198h+var_158], r12b
0x1800d7dc5  mov     rdx, [r14+40h]
0x1800d7dc9  lea     rcx, [rsp+198h+instance]
0x1800d7dd1  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800d7dd6  mov     rdx, [r14+50h]
0x1800d7dda  lea     rcx, [rsp+198h+instance]
0x1800d7de2  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800d7de7  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x1800d7dec  lea     rdx, aAllowaddprovis; "AllowAddProvisioningPackage"
0x1800d7df3  mov     rcx, rdi; this
0x1800d7df6  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800d7dfb  test    eax, eax
0x1800d7dfd  jnz     short loc_1800D7E1E
0x1800d7dff  mov     rcx, [rsp+198h+String]; String
0x1800d7e04  test    rcx, rcx
0x1800d7e07  jz      short loc_1800D7E1E
0x1800d7e09  call    cs:__imp__wtoi
0x1800d7e0f  mov     [rsp+198h+var_88], eax
0x1800d7e16  mov     [rsp+198h+var_84], r12b
0x1800d7e1e  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x1800d7e23  lea     rdx, aAllowremovepro; "AllowRemoveProvisioningPackage"
0x1800d7e2a  mov     rcx, rdi; this
0x1800d7e2d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800d7e32  test    eax, eax
0x1800d7e34  jnz     short loc_1800D7E55
0x1800d7e36  mov     rcx, [rsp+198h+String]; String
0x1800d7e3b  test    rcx, rcx
0x1800d7e3e  jz      short loc_1800D7E55
0x1800d7e40  call    cs:__imp__wtoi
0x1800d7e46  mov     [rsp+198h+var_80], eax
0x1800d7e4d  mov     [rsp+198h+var_7C], r12b
0x1800d7e55  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x1800d7e5a  lea     rdx, aCleartpmifnotr; "ClearTPMIfNotReady"
0x1800d7e61  mov     rcx, rdi; this
0x1800d7e64  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800d7e69  test    eax, eax
0x1800d7e6b  jnz     short loc_1800D7E8C
0x1800d7e6d  mov     rcx, [rsp+198h+String]; String
0x1800d7e72  test    rcx, rcx
0x1800d7e75  jz      short loc_1800D7E8C
0x1800d7e77  call    cs:__imp__wtoi
0x1800d7e7d  mov     [rsp+198h+var_78], eax
0x1800d7e84  mov     [rsp+198h+var_74], r12b
0x1800d7e8c  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x1800d7e91  lea     rdx, aConfigurewindo_2; "ConfigureWindowsPasswords"
0x1800d7e98  mov     rcx, rdi; this
0x1800d7e9b  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800d7ea0  test    eax, eax
0x1800d7ea2  jnz     short loc_1800D7EC3
0x1800d7ea4  mov     rcx, [rsp+198h+String]; String
0x1800d7ea9  test    rcx, rcx
0x1800d7eac  jz      short loc_1800D7EC3
0x1800d7eae  call    cs:__imp__wtoi
0x1800d7eb4  mov     [rsp+198h+var_70], eax
0x1800d7ebb  mov     [rsp+198h+var_6C], r12b
0x1800d7ec3  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x1800d7ec8  lea     rdx, aPreventautomat; "PreventAutomaticDeviceEncryptionForAzur"...
0x1800d7ecf  mov     rcx, rdi; this
0x1800d7ed2  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800d7ed7  test    eax, eax
0x1800d7ed9  jnz     short loc_1800D7EFA
0x1800d7edb  mov     rcx, [rsp+198h+String]; String
0x1800d7ee0  test    rcx, rcx
0x1800d7ee3  jz      short loc_1800D7EFA
0x1800d7ee5  call    cs:__imp__wtoi
0x1800d7eeb  mov     [rsp+198h+var_68], eax
0x1800d7ef2  mov     [rsp+198h+var_64], r12b
0x1800d7efa  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x1800d7eff  lea     rdx, aRecoveryenviro; "RecoveryEnvironmentAuthentication"
0x1800d7f06  mov     rcx, rdi; this
0x1800d7f09  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800d7f0e  test    eax, eax
0x1800d7f10  jnz     short loc_1800D7F31
0x1800d7f12  mov     rcx, [rsp+198h+String]; String
0x1800d7f17  test    rcx, rcx
0x1800d7f1a  jz      short loc_1800D7F31
0x1800d7f1c  call    cs:__imp__wtoi
0x1800d7f22  mov     [rsp+198h+var_60], eax
0x1800d7f29  mov     [rsp+198h+var_5C], r12b
0x1800d7f31  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x1800d7f36  lea     rdx, aRequiredevicee; "RequireDeviceEncryption"
0x1800d7f3d  mov     rcx, rdi; this
0x1800d7f40  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800d7f45  test    eax, eax
0x1800d7f47  jnz     short loc_1800D7F68
0x1800d7f49  mov     rcx, [rsp+198h+String]; String
0x1800d7f4e  test    rcx, rcx
0x1800d7f51  jz      short loc_1800D7F68
0x1800d7f53  call    cs:__imp__wtoi
0x1800d7f59  mov     [rsp+198h+var_58], eax
0x1800d7f60  mov     [rsp+198h+var_54], r12b
0x1800d7f68  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x1800d7f6d  lea     rdx, aRequireprovisi; "RequireProvisioningPackageSignature"
0x1800d7f74  mov     rcx, rdi; this
0x1800d7f77  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800d7f7c  test    eax, eax
0x1800d7f7e  jnz     short loc_1800D7F9F
0x1800d7f80  mov     rcx, [rsp+198h+String]; String
0x1800d7f85  test    rcx, rcx
0x1800d7f88  jz      short loc_1800D7F9F
0x1800d7f8a  call    cs:__imp__wtoi
0x1800d7f90  mov     [rsp+198h+var_50], eax
0x1800d7f97  mov     [rsp+198h+var_4C], r12b
0x1800d7f9f  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x1800d7fa4  lea     rdx, aRequireretriev; "RequireRetrieveHealthCertificateOnBoot"
0x1800d7fab  mov     rcx, rdi; this
0x1800d7fae  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800d7fb3  test    eax, eax
0x1800d7fb5  jnz     short loc_1800D7FD6
0x1800d7fb7  mov     rcx, [rsp+198h+String]; String
0x1800d7fbc  test    rcx, rcx
0x1800d7fbf  jz      short loc_1800D7FD6
0x1800d7fc1  call    cs:__imp__wtoi
0x1800d7fc7  mov     [rsp+198h+var_48], eax
0x1800d7fce  mov     [rsp+198h+var_44], r12b
0x1800d7fd6  lea     rdx, [rsp+198h+instance]
0x1800d7fde  mov     rcx, r15; self
0x1800d7fe1  call    MI_Instance_Destruct
0x1800d7fe6  nop
0x1800d7fe7  mov     rcx, [rsp+198h+var_148]
0x1800d7fec  test    rcx, rcx
0x1800d7fef  jz      short loc_1800D8000
0x1800d7ff1  mov     rax, [rcx]
0x1800d7ff4  mov     edx, r12d
0x1800d7ff7  mov     rax, [rax]
0x1800d7ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7fff  nop
0x1800d8000  jmp     short loc_1800D800E
0x1800d8002  xor     ebx, ebx
0x1800d8004  mov     esi, dword ptr [rsp+198h+String]
0x1800d8008  cmp     [rsp+198h+var_158], bl
0x1800d800c  jz      short loc_1800D8022
0x1800d800e  lea     rcx, [rsp+198h+instance]; self
0x1800d8016  call    MI_Instance_Destruct
0x1800d801b  jmp     short loc_1800D8022
0x1800d801d  mov     esi, 4
0x1800d8022  mov     r8d, esi; int
0x1800d8025  lea     rdx, aGetinstanceend; "GetInstanceEnd"
0x1800d802c  lea     rcx, [rsp+198h+var_140]; this
0x1800d8031  call    ?WriteEnd@TelemetryEventWriter@@QEAAXPEBDH@Z; TelemetryEventWriter::WriteEnd(char const *,int)
0x1800d8036  mov     [rsp+198h+var_110], 2
0x1800d8041  mov     eax, cs:dword_180380B68
0x1800d8047  cmp     eax, 5
0x1800d804a  jbe     short loc_1800D8085
0x1800d804c  mov     rdx, 200000000000h
0x1800d8056  lea     rcx, dword_180380B68
0x1800d805d  call    _tlgKeywordOn
0x1800d8062  test    al, al
0x1800d8064  jz      short loc_1800D8085
0x1800d8066  xor     r9d, r9d
0x1800d8069  lea     r8, [rsp+198h+var_108]
0x1800d8071  lea     rdx, byte_180361641
0x1800d8078  lea     rcx, dword_180380B68
0x1800d807f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800d8084  nop
0x1800d8085  lea     rcx, [rsp+198h+var_110]
0x1800d808d  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(void)
0x1800d8092  mov     eax, esi
0x1800d8094  mov     rcx, [rsp+198h+var_38]
0x1800d809c  xor     rcx, rsp; StackCookie
  ... truncated ...
```
