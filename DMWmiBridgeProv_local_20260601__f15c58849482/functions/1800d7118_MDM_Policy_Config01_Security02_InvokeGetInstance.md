# MDM_Policy_Config01_Security02_InvokeGetInstance

- ea: `0x1800d7118`
- end: `0x1800d769f`
- name: `MDM_Policy_Config01_Security02_InvokeGetInstance`
- size: `1415`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d6230`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800d7118`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800d73b5`
- `msvcrt!_wtoi` at `0x1800d73f2`
- `msvcrt!_wtoi` at `0x1800d742f`
- `msvcrt!_wtoi` at `0x1800d746c`
- `msvcrt!_wtoi` at `0x1800d74a9`
- `msvcrt!_wtoi` at `0x1800d74e6`
- `msvcrt!_wtoi` at `0x1800d7523`
- `msvcrt!_wtoi` at `0x1800d7560`
- `msvcrt!_wtoi` at `0x1800d759d`
- `msvcrt!_wtoi` at `0x1800d73b5`
- `msvcrt!_wtoi` at `0x1800d73f2`
- `msvcrt!_wtoi` at `0x1800d742f`
- `msvcrt!_wtoi` at `0x1800d746c`
- `msvcrt!_wtoi` at `0x1800d74a9`
- `msvcrt!_wtoi` at `0x1800d74e6`
- `msvcrt!_wtoi` at `0x1800d7523`
- `msvcrt!_wtoi` at `0x1800d7560`
- `msvcrt!_wtoi` at `0x1800d759d`

## string_xrefs

- `0x1800d73d5`: `AllowRemoveProvisioningPackage`
- `0x1800d7412`: `ClearTPMIfNotReady`
- `0x1800d744f`: `ConfigureWindowsPasswords`
- `0x1800d748c`: `PreventAutomaticDeviceEncryptionForAzureADJoinedDevices`
- `0x1800d7187`: `MDM_Policy_Config01_Security02`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall MDM_Policy_Config01_Security02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  MI_Result v5; // esi
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
    v5 = MI_RESULT_INVALID_PARAMETER;
    goto LABEL_56;
  }
  TelemetryEventWriter::WriteStart(
    (TelemetryEventWriter *)v10,
    "GetInstanceStart",
    a2[1].serverName,
    (const unsigned __int16 *)a2[1].ft);
  v9 = 0;
  v5 = (unsigned int)CreateRequestHandlerInstance(
                       self,
                       a2[1].serverName,
                       a2[1].ft,
                       &MDM_Policy_Config01_Security02_NodeList,
                       11,
                       0,
                       &v9);
  if ( v5 == MI_RESULT_OK )
  {
    v10[4] = &v9;
    v11 = 1;
    v6 = v9;
    if ( !v9 )
    {
      v5 = MI_RESULT_FAILED;
      goto LABEL_56;
    }
    WmiRequestHandler::SetRequestMIInstance(
      v9,
      a2,
      (struct WmiNodeInfo *)&MDM_Policy_Config01_Security02_NodeList,
      0xBu);
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
    if ( v5 )
    {
      if ( !v9 )
        goto LABEL_56;
LABEL_24:
      (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v9)(v9, 1);
      goto LABEL_56;
    }
    v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AllowAddProvisioningPackage",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v17 = _wtoi(String);
      v18 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"AllowRemoveProvisioningPackage",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v19 = _wtoi(String);
      v20 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ClearTPMIfNotReady", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v21 = _wtoi(String);
      v22 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"ConfigureWindowsPasswords", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v23 = _wtoi(String);
      v24 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"PreventAutomaticDeviceEncryptionForAzureADJoinedDevices",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v25 = _wtoi(String);
      v26 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"RecoveryEnvironmentAuthentication",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v27 = _wtoi(String);
      v28 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(v6, L"RequireDeviceEncryption", (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v29 = _wtoi(String);
      v30 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"RequireProvisioningPackageSignature",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
      && String )
    {
      v31 = _wtoi(String);
      v32 = 1;
    }
    if ( WmiRequestHandler::FindResultDataForNode(
           v6,
           L"RequireRetrieveHealthCertificateOnBoot",
           (const unsigned __int16 **)&String) == MI_RESULT_OK
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
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800d7118  mov     [rsp+arg_10], rbx
0x1800d711d  push    rsi
0x1800d711e  push    rdi
0x1800d711f  push    r12
0x1800d7121  push    r14
0x1800d7123  push    r15
0x1800d7125  sub     rsp, 170h
0x1800d712c  mov     rax, cs:__security_cookie
0x1800d7133  xor     rax, rsp
0x1800d7136  mov     [rsp+198h+var_38], rax
0x1800d713e  mov     r14, rdx
0x1800d7141  mov     r15, rcx
0x1800d7144  xor     ebx, ebx
0x1800d7146  mov     [rsp+198h+String], rbx
0x1800d714b  xor     edx, edx; Val
0x1800d714d  mov     r8d, 0A8h; Size
0x1800d7153  lea     rcx, [rsp+198h+instance]; void *
0x1800d715b  call    memset_0
0x1800d7160  mov     [rsp+198h+var_110], ebx
0x1800d7167  mov     [rsp+198h+var_10C], bl
0x1800d716e  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800d7175  mov     [rsp+198h+var_140], rax
0x1800d717a  lea     rax, [rsp+198h+var_110]
0x1800d7182  mov     [rsp+198h+var_138], rax
0x1800d7187  lea     rax, aMdmPolicyConfi_98; "MDM_Policy_Config01_Security02"
0x1800d718e  mov     [rsp+198h+var_130], rax
0x1800d7193  lea     rcx, [rsp+198h+var_110]
0x1800d719b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800d71a0  mov     eax, cs:dword_180380B68
0x1800d71a6  cmp     eax, 5
0x1800d71a9  jbe     short loc_1800D721A
0x1800d71ab  mov     rdx, 200000000000h
0x1800d71b5  lea     rcx, dword_180380B68
0x1800d71bc  call    _tlgKeywordOn
0x1800d71c1  test    al, al
0x1800d71c3  jz      short loc_1800D721A
0x1800d71c5  cmp     [rsp+198h+var_10C], bl
0x1800d71cc  jz      short loc_1800D71FC
0x1800d71ce  cmp     [rsp+198h+var_F8], ebx
0x1800d71d5  jnz     short loc_1800D71F2
0x1800d71d7  cmp     [rsp+198h+var_F4], ebx
0x1800d71de  jnz     short loc_1800D71F2
0x1800d71e0  cmp     [rsp+198h+var_F0], ebx
0x1800d71e7  jnz     short loc_1800D71F2
0x1800d71e9  cmp     [rsp+198h+var_EC], ebx
0x1800d71f0  jz      short loc_1800D71FC
0x1800d71f2  lea     r9, [rsp+198h+var_F8]
0x1800d71fa  jmp     short loc_1800D71FF
0x1800d71fc  mov     r9, rbx
0x1800d71ff  lea     r8, [rsp+198h+var_108]
0x1800d7207  lea     rdx, word_180354682
0x1800d720e  lea     rcx, dword_180380B68
0x1800d7215  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800d721a  cmp     [r14+48h], bl
0x1800d721e  jz      loc_1800D75FF
0x1800d7224  mov     [rsp+198h+var_158], bl
0x1800d7228  cmp     [r14+58h], bl
0x1800d722c  jz      loc_1800D75FF
0x1800d7232  mov     r9, [r14+40h]; unsigned __int16 *
0x1800d7236  mov     r8, [r14+50h]; unsigned __int16 *
0x1800d723a  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1800d7241  lea     rcx, [rsp+198h+var_140]; this
0x1800d7246  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800d724b  nop
0x1800d724c  mov     [rsp+198h+var_148], rbx
0x1800d7251  lea     rax, [rsp+198h+var_148]
0x1800d7256  mov     [rsp+198h+var_168], rax
0x1800d725b  mov     [rsp+198h+var_170], ebx
0x1800d725f  mov     [rsp+198h+var_178], 0Bh
0x1800d7267  lea     r9, ?MDM_Policy_Config01_Security02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_Security02_NodeList
0x1800d726e  mov     r8, [r14+40h]
0x1800d7272  mov     rdx, [r14+50h]
0x1800d7276  mov     rcx, r15
0x1800d7279  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800d727e  mov     esi, eax
0x1800d7280  test    eax, eax
0x1800d7282  jz      short loc_1800D7289
0x1800d7284  jmp     loc_1800D7604
0x1800d7289  lea     rax, [rsp+198h+var_148]
0x1800d728e  mov     [rsp+198h+var_120], rax
0x1800d7293  mov     r12d, 1
0x1800d7299  mov     [rsp+198h+var_118], r12b
0x1800d72a1  mov     rdi, [rsp+198h+var_148]
0x1800d72a6  test    rdi, rdi
0x1800d72a9  jnz     short loc_1800D72B3
0x1800d72ab  mov     esi, r12d
0x1800d72ae  jmp     loc_1800D7604
0x1800d72b3  mov     r9d, 0Bh; unsigned int
0x1800d72b9  lea     r8, ?MDM_Policy_Config01_Security02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800d72c0  mov     rdx, r14; struct _MI_Instance *
0x1800d72c3  mov     rcx, rdi; this
0x1800d72c6  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800d72cb  mov     rax, [rdi]
0x1800d72ce  mov     rcx, rdi
0x1800d72d1  mov     rax, [rax+10h]
0x1800d72d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d72da  mov     esi, eax
0x1800d72dc  test    eax, eax
0x1800d72de  jz      short loc_1800D72FE
0x1800d72e0  mov     rcx, [rsp+198h+var_148]
0x1800d72e5  test    rcx, rcx
0x1800d72e8  jz      short loc_1800D72F9
0x1800d72ea  mov     rax, [rcx]
0x1800d72ed  mov     edx, r12d
0x1800d72f0  mov     rax, [rax]
0x1800d72f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d72f8  nop
0x1800d72f9  jmp     loc_1800D7604
0x1800d72fe  mov     rax, [rdi]
0x1800d7301  mov     rcx, rdi
0x1800d7304  mov     rax, [rax+8]
0x1800d7308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d730d  mov     esi, eax
0x1800d730f  test    eax, eax
0x1800d7311  jz      short loc_1800D7331
0x1800d7313  mov     rcx, [rsp+198h+var_148]
0x1800d7318  test    rcx, rcx
0x1800d731b  jz      short loc_1800D732C
0x1800d731d  mov     rax, [rcx]
0x1800d7320  mov     edx, r12d
0x1800d7323  mov     rax, [rax]
0x1800d7326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d732b  nop
0x1800d732c  jmp     loc_1800D7604
0x1800d7331  lea     r8, [rsp+198h+instance]; instance
0x1800d7339  lea     rdx, MDM_Policy_Config01_Security02_rtti; classDecl
0x1800d7340  mov     rcx, r15; context
0x1800d7343  call    MI_Context_ConstructInstance
0x1800d7348  mov     esi, eax
0x1800d734a  test    eax, eax
0x1800d734c  jz      short loc_1800D736C
0x1800d734e  mov     rcx, [rsp+198h+var_148]
0x1800d7353  test    rcx, rcx
0x1800d7356  jz      short loc_1800D7367
0x1800d7358  mov     rax, [rcx]
0x1800d735b  mov     edx, r12d
0x1800d735e  mov     rax, [rax]
0x1800d7361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7366  nop
0x1800d7367  jmp     loc_1800D7604
0x1800d736c  mov     [rsp+198h+var_158], r12b
0x1800d7371  mov     rdx, [r14+40h]
0x1800d7375  lea     rcx, [rsp+198h+instance]
0x1800d737d  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800d7382  mov     rdx, [r14+50h]
0x1800d7386  lea     rcx, [rsp+198h+instance]
0x1800d738e  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800d7393  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x1800d7398  lea     rdx, aAllowaddprovis; "AllowAddProvisioningPackage"
0x1800d739f  mov     rcx, rdi; this
0x1800d73a2  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800d73a7  test    eax, eax
0x1800d73a9  jnz     short loc_1800D73D0
0x1800d73ab  mov     rcx, [rsp+198h+String]; String
0x1800d73b0  test    rcx, rcx
0x1800d73b3  jz      short loc_1800D73D0
0x1800d73b5  call    cs:__imp__wtoi
0x1800d73bc  nop     dword ptr [rax+rax+00h]
0x1800d73c1  mov     [rsp+198h+var_88], eax
0x1800d73c8  mov     [rsp+198h+var_84], r12b
0x1800d73d0  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x1800d73d5  lea     rdx, aAllowremovepro; "AllowRemoveProvisioningPackage"
0x1800d73dc  mov     rcx, rdi; this
0x1800d73df  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800d73e4  test    eax, eax
0x1800d73e6  jnz     short loc_1800D740D
0x1800d73e8  mov     rcx, [rsp+198h+String]; String
0x1800d73ed  test    rcx, rcx
0x1800d73f0  jz      short loc_1800D740D
0x1800d73f2  call    cs:__imp__wtoi
0x1800d73f9  nop     dword ptr [rax+rax+00h]
0x1800d73fe  mov     [rsp+198h+var_80], eax
0x1800d7405  mov     [rsp+198h+var_7C], r12b
0x1800d740d  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x1800d7412  lea     rdx, aCleartpmifnotr; "ClearTPMIfNotReady"
0x1800d7419  mov     rcx, rdi; this
0x1800d741c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800d7421  test    eax, eax
0x1800d7423  jnz     short loc_1800D744A
0x1800d7425  mov     rcx, [rsp+198h+String]; String
0x1800d742a  test    rcx, rcx
0x1800d742d  jz      short loc_1800D744A
0x1800d742f  call    cs:__imp__wtoi
0x1800d7436  nop     dword ptr [rax+rax+00h]
0x1800d743b  mov     [rsp+198h+var_78], eax
0x1800d7442  mov     [rsp+198h+var_74], r12b
0x1800d744a  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x1800d744f  lea     rdx, aConfigurewindo_2; "ConfigureWindowsPasswords"
0x1800d7456  mov     rcx, rdi; this
0x1800d7459  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800d745e  test    eax, eax
0x1800d7460  jnz     short loc_1800D7487
0x1800d7462  mov     rcx, [rsp+198h+String]; String
0x1800d7467  test    rcx, rcx
0x1800d746a  jz      short loc_1800D7487
0x1800d746c  call    cs:__imp__wtoi
0x1800d7473  nop     dword ptr [rax+rax+00h]
0x1800d7478  mov     [rsp+198h+var_70], eax
0x1800d747f  mov     [rsp+198h+var_6C], r12b
0x1800d7487  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x1800d748c  lea     rdx, aPreventautomat; "PreventAutomaticDeviceEncryptionForAzur"...
0x1800d7493  mov     rcx, rdi; this
0x1800d7496  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800d749b  test    eax, eax
0x1800d749d  jnz     short loc_1800D74C4
0x1800d749f  mov     rcx, [rsp+198h+String]; String
0x1800d74a4  test    rcx, rcx
0x1800d74a7  jz      short loc_1800D74C4
0x1800d74a9  call    cs:__imp__wtoi
0x1800d74b0  nop     dword ptr [rax+rax+00h]
0x1800d74b5  mov     [rsp+198h+var_68], eax
0x1800d74bc  mov     [rsp+198h+var_64], r12b
0x1800d74c4  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x1800d74c9  lea     rdx, aRecoveryenviro; "RecoveryEnvironmentAuthentication"
0x1800d74d0  mov     rcx, rdi; this
0x1800d74d3  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800d74d8  test    eax, eax
0x1800d74da  jnz     short loc_1800D7501
0x1800d74dc  mov     rcx, [rsp+198h+String]; String
0x1800d74e1  test    rcx, rcx
0x1800d74e4  jz      short loc_1800D7501
0x1800d74e6  call    cs:__imp__wtoi
0x1800d74ed  nop     dword ptr [rax+rax+00h]
0x1800d74f2  mov     [rsp+198h+var_60], eax
0x1800d74f9  mov     [rsp+198h+var_5C], r12b
0x1800d7501  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x1800d7506  lea     rdx, aRequiredevicee; "RequireDeviceEncryption"
0x1800d750d  mov     rcx, rdi; this
0x1800d7510  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800d7515  test    eax, eax
0x1800d7517  jnz     short loc_1800D753E
0x1800d7519  mov     rcx, [rsp+198h+String]; String
0x1800d751e  test    rcx, rcx
0x1800d7521  jz      short loc_1800D753E
0x1800d7523  call    cs:__imp__wtoi
0x1800d752a  nop     dword ptr [rax+rax+00h]
0x1800d752f  mov     [rsp+198h+var_58], eax
0x1800d7536  mov     [rsp+198h+var_54], r12b
0x1800d753e  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x1800d7543  lea     rdx, aRequireprovisi; "RequireProvisioningPackageSignature"
0x1800d754a  mov     rcx, rdi; this
0x1800d754d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800d7552  test    eax, eax
0x1800d7554  jnz     short loc_1800D757B
0x1800d7556  mov     rcx, [rsp+198h+String]; String
0x1800d755b  test    rcx, rcx
0x1800d755e  jz      short loc_1800D757B
0x1800d7560  call    cs:__imp__wtoi
0x1800d7567  nop     dword ptr [rax+rax+00h]
0x1800d756c  mov     [rsp+198h+var_50], eax
0x1800d7573  mov     [rsp+198h+var_4C], r12b
0x1800d757b  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x1800d7580  lea     rdx, aRequireretriev; "RequireRetrieveHealthCertificateOnBoot"
0x1800d7587  mov     rcx, rdi; this
0x1800d758a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800d758f  test    eax, eax
0x1800d7591  jnz     short loc_1800D75B8
0x1800d7593  mov     rcx, [rsp+198h+String]; String
0x1800d7598  test    rcx, rcx
0x1800d759b  jz      short loc_1800D75B8
0x1800d759d  call    cs:__imp__wtoi
0x1800d75a4  nop     dword ptr [rax+rax+00h]
0x1800d75a9  mov     [rsp+198h+var_48], eax
0x1800d75b0  mov     [rsp+198h+var_44], r12b
0x1800d75b8  lea     rdx, [rsp+198h+instance]
0x1800d75c0  mov     rcx, r15; self
0x1800d75c3  call    MI_Instance_Destruct
0x1800d75c8  nop
0x1800d75c9  mov     rcx, [rsp+198h+var_148]
0x1800d75ce  test    rcx, rcx
0x1800d75d1  jz      short loc_1800D75E2
0x1800d75d3  mov     rax, [rcx]
0x1800d75d6  mov     edx, r12d
0x1800d75d9  mov     rax, [rax]
0x1800d75dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d75e1  nop
0x1800d75e2  jmp     short loc_1800D75F0
0x1800d75e4  xor     ebx, ebx
0x1800d75e6  mov     esi, dword ptr [rsp+198h+String]
0x1800d75ea  cmp     [rsp+198h+var_158], bl
0x1800d75ee  jz      short loc_1800D7604
0x1800d75f0  lea     rcx, [rsp+198h+instance]; self
0x1800d75f8  call    MI_Instance_Destruct
0x1800d75fd  jmp     short loc_1800D7604
0x1800d75ff  mov     esi, 4
0x1800d7604  mov     r8d, esi; int
0x1800d7607  lea     rdx, aGetinstanceend; "GetInstanceEnd"
0x1800d760e  lea     rcx, [rsp+198h+var_140]; this
0x1800d7613  call    ?WriteEnd@TelemetryEventWriter@@QEAAXPEBDH@Z; TelemetryEventWriter::WriteEnd(char const *,int)
0x1800d7618  mov     [rsp+198h+var_110], 2
0x1800d7623  mov     eax, cs:dword_180380B68
0x1800d7629  cmp     eax, 5
0x1800d762c  jbe     short loc_1800D7667
0x1800d762e  mov     rdx, 200000000000h
0x1800d7638  lea     rcx, dword_180380B68
0x1800d763f  call    _tlgKeywordOn
0x1800d7644  test    al, al
0x1800d7646  jz      short loc_1800D7667
0x1800d7648  xor     r9d, r9d
0x1800d764b  lea     r8, [rsp+198h+var_108]
  ... truncated ...
```
