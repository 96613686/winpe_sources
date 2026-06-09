# MDM_Policy_Result01_Security02_InvokeGetInstance

- ea: `0x18018e828`
- end: `0x18018edaf`
- name: `MDM_Policy_Result01_Security02_InvokeGetInstance`
- size: `1415`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18018d940`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x18018e828`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x18018eac5`
- `msvcrt!_wtoi` at `0x18018eb02`
- `msvcrt!_wtoi` at `0x18018eb3f`
- `msvcrt!_wtoi` at `0x18018eb7c`
- `msvcrt!_wtoi` at `0x18018ebb9`
- `msvcrt!_wtoi` at `0x18018ebf6`
- `msvcrt!_wtoi` at `0x18018ec33`
- `msvcrt!_wtoi` at `0x18018ec70`
- `msvcrt!_wtoi` at `0x18018ecad`
- `msvcrt!_wtoi` at `0x18018eac5`
- `msvcrt!_wtoi` at `0x18018eb02`
- `msvcrt!_wtoi` at `0x18018eb3f`
- `msvcrt!_wtoi` at `0x18018eb7c`
- `msvcrt!_wtoi` at `0x18018ebb9`
- `msvcrt!_wtoi` at `0x18018ebf6`
- `msvcrt!_wtoi` at `0x18018ec33`
- `msvcrt!_wtoi` at `0x18018ec70`
- `msvcrt!_wtoi` at `0x18018ecad`

## string_xrefs

- `0x18018eae5`: `AllowRemoveProvisioningPackage`
- `0x18018eb22`: `ClearTPMIfNotReady`
- `0x18018eb5f`: `ConfigureWindowsPasswords`
- `0x18018eb9c`: `PreventAutomaticDeviceEncryptionForAzureADJoinedDevices`
- `0x18018e897`: `MDM_Policy_Result01_Security02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Result01_Security02_InvokeGetInstance(MI_Context *self, struct _MI_Instance *a2)
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
    v5 = (unsigned int)CreateRequestHandlerInstance(
                         self,
                         a2[1].serverName,
                         a2[1].ft,
                         &MDM_Policy_Result01_Security02_NodeList,
                         11,
                         0,
                         &v9);
    if ( v5 == MI_RESULT_OK )
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
        v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 16LL))(v6);
        if ( v5 )
        {
          if ( v9 )
            (**(void (__fastcall ***)(WmiRequestHandler *, __int64))v9)(v9, 1);
        }
        else
        {
          v5 = (*(unsigned int (__fastcall **)(WmiRequestHandler *))(*(_QWORD *)v6 + 8LL))(v6);
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
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"ClearTPMIfNotReady",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v21 = _wtoi(String);
                v22 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"ConfigureWindowsPasswords",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
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
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"RequireDeviceEncryption",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
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
          }
        }
      }
      else
      {
        v5 = MI_RESULT_FAILED;
      }
    }
  }
  else
  {
    v5 = MI_RESULT_INVALID_PARAMETER;
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
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18018e828  mov     [rsp+arg_10], rbx
0x18018e82d  push    rsi
0x18018e82e  push    rdi
0x18018e82f  push    r12
0x18018e831  push    r14
0x18018e833  push    r15
0x18018e835  sub     rsp, 170h
0x18018e83c  mov     rax, cs:__security_cookie
0x18018e843  xor     rax, rsp
0x18018e846  mov     [rsp+198h+var_38], rax
0x18018e84e  mov     r14, rdx
0x18018e851  mov     r15, rcx
0x18018e854  xor     ebx, ebx
0x18018e856  mov     [rsp+198h+String], rbx
0x18018e85b  xor     edx, edx; Val
0x18018e85d  mov     r8d, 0A8h; Size
0x18018e863  lea     rcx, [rsp+198h+instance]; void *
0x18018e86b  call    memset_0
0x18018e870  mov     [rsp+198h+var_110], ebx
0x18018e877  mov     [rsp+198h+var_10C], bl
0x18018e87e  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x18018e885  mov     [rsp+198h+var_140], rax
0x18018e88a  lea     rax, [rsp+198h+var_110]
0x18018e892  mov     [rsp+198h+var_138], rax
0x18018e897  lea     rax, aMdmPolicyResul_141; "MDM_Policy_Result01_Security02"
0x18018e89e  mov     [rsp+198h+var_130], rax
0x18018e8a3  lea     rcx, [rsp+198h+var_110]
0x18018e8ab  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x18018e8b0  mov     eax, cs:dword_180380B68
0x18018e8b6  cmp     eax, 5
0x18018e8b9  jbe     short loc_18018E92A
0x18018e8bb  mov     rdx, 200000000000h
0x18018e8c5  lea     rcx, dword_180380B68
0x18018e8cc  call    _tlgKeywordOn
0x18018e8d1  test    al, al
0x18018e8d3  jz      short loc_18018E92A
0x18018e8d5  cmp     [rsp+198h+var_10C], bl
0x18018e8dc  jz      short loc_18018E90C
0x18018e8de  cmp     [rsp+198h+var_F8], ebx
0x18018e8e5  jnz     short loc_18018E902
0x18018e8e7  cmp     [rsp+198h+var_F4], ebx
0x18018e8ee  jnz     short loc_18018E902
0x18018e8f0  cmp     [rsp+198h+var_F0], ebx
0x18018e8f7  jnz     short loc_18018E902
0x18018e8f9  cmp     [rsp+198h+var_EC], ebx
0x18018e900  jz      short loc_18018E90C
0x18018e902  lea     r9, [rsp+198h+var_F8]
0x18018e90a  jmp     short loc_18018E90F
0x18018e90c  mov     r9, rbx
0x18018e90f  lea     r8, [rsp+198h+var_108]
0x18018e917  lea     rdx, byte_180341221
0x18018e91e  lea     rcx, dword_180380B68
0x18018e925  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18018e92a  cmp     [r14+48h], bl
0x18018e92e  jz      loc_18018ED0F
0x18018e934  mov     [rsp+198h+var_158], bl
0x18018e938  cmp     [r14+58h], bl
0x18018e93c  jz      loc_18018ED0F
0x18018e942  mov     r9, [r14+40h]; unsigned __int16 *
0x18018e946  mov     r8, [r14+50h]; unsigned __int16 *
0x18018e94a  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x18018e951  lea     rcx, [rsp+198h+var_140]; this
0x18018e956  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x18018e95b  nop
0x18018e95c  mov     [rsp+198h+var_148], rbx
0x18018e961  lea     rax, [rsp+198h+var_148]
0x18018e966  mov     [rsp+198h+var_168], rax
0x18018e96b  mov     [rsp+198h+var_170], ebx
0x18018e96f  mov     [rsp+198h+var_178], 0Bh
0x18018e977  lea     r9, ?MDM_Policy_Result01_Security02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Result01_Security02_NodeList
0x18018e97e  mov     r8, [r14+40h]
0x18018e982  mov     rdx, [r14+50h]
0x18018e986  mov     rcx, r15
0x18018e989  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x18018e98e  mov     esi, eax
0x18018e990  test    eax, eax
0x18018e992  jz      short loc_18018E999
0x18018e994  jmp     loc_18018ED14
0x18018e999  lea     rax, [rsp+198h+var_148]
0x18018e99e  mov     [rsp+198h+var_120], rax
0x18018e9a3  mov     r12d, 1
0x18018e9a9  mov     [rsp+198h+var_118], r12b
0x18018e9b1  mov     rdi, [rsp+198h+var_148]
0x18018e9b6  test    rdi, rdi
0x18018e9b9  jnz     short loc_18018E9C3
0x18018e9bb  mov     esi, r12d
0x18018e9be  jmp     loc_18018ED14
0x18018e9c3  mov     r9d, 0Bh; unsigned int
0x18018e9c9  lea     r8, ?MDM_Policy_Result01_Security02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x18018e9d0  mov     rdx, r14; struct _MI_Instance *
0x18018e9d3  mov     rcx, rdi; this
0x18018e9d6  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x18018e9db  mov     rax, [rdi]
0x18018e9de  mov     rcx, rdi
0x18018e9e1  mov     rax, [rax+10h]
0x18018e9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018e9ea  mov     esi, eax
0x18018e9ec  test    eax, eax
0x18018e9ee  jz      short loc_18018EA0E
0x18018e9f0  mov     rcx, [rsp+198h+var_148]
0x18018e9f5  test    rcx, rcx
0x18018e9f8  jz      short loc_18018EA09
0x18018e9fa  mov     rax, [rcx]
0x18018e9fd  mov     edx, r12d
0x18018ea00  mov     rax, [rax]
0x18018ea03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018ea08  nop
0x18018ea09  jmp     loc_18018ED14
0x18018ea0e  mov     rax, [rdi]
0x18018ea11  mov     rcx, rdi
0x18018ea14  mov     rax, [rax+8]
0x18018ea18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018ea1d  mov     esi, eax
0x18018ea1f  test    eax, eax
0x18018ea21  jz      short loc_18018EA41
0x18018ea23  mov     rcx, [rsp+198h+var_148]
0x18018ea28  test    rcx, rcx
0x18018ea2b  jz      short loc_18018EA3C
0x18018ea2d  mov     rax, [rcx]
0x18018ea30  mov     edx, r12d
0x18018ea33  mov     rax, [rax]
0x18018ea36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018ea3b  nop
0x18018ea3c  jmp     loc_18018ED14
0x18018ea41  lea     r8, [rsp+198h+instance]; instance
0x18018ea49  lea     rdx, MDM_Policy_Result01_Security02_rtti; classDecl
0x18018ea50  mov     rcx, r15; context
0x18018ea53  call    MI_Context_ConstructInstance
0x18018ea58  mov     esi, eax
0x18018ea5a  test    eax, eax
0x18018ea5c  jz      short loc_18018EA7C
0x18018ea5e  mov     rcx, [rsp+198h+var_148]
0x18018ea63  test    rcx, rcx
0x18018ea66  jz      short loc_18018EA77
0x18018ea68  mov     rax, [rcx]
0x18018ea6b  mov     edx, r12d
0x18018ea6e  mov     rax, [rax]
0x18018ea71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018ea76  nop
0x18018ea77  jmp     loc_18018ED14
0x18018ea7c  mov     [rsp+198h+var_158], r12b
0x18018ea81  mov     rdx, [r14+40h]
0x18018ea85  lea     rcx, [rsp+198h+instance]
0x18018ea8d  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x18018ea92  mov     rdx, [r14+50h]
0x18018ea96  lea     rcx, [rsp+198h+instance]
0x18018ea9e  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x18018eaa3  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x18018eaa8  lea     rdx, aAllowaddprovis; "AllowAddProvisioningPackage"
0x18018eaaf  mov     rcx, rdi; this
0x18018eab2  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18018eab7  test    eax, eax
0x18018eab9  jnz     short loc_18018EAE0
0x18018eabb  mov     rcx, [rsp+198h+String]; String
0x18018eac0  test    rcx, rcx
0x18018eac3  jz      short loc_18018EAE0
0x18018eac5  call    cs:__imp__wtoi
0x18018eacc  nop     dword ptr [rax+rax+00h]
0x18018ead1  mov     [rsp+198h+var_88], eax
0x18018ead8  mov     [rsp+198h+var_84], r12b
0x18018eae0  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x18018eae5  lea     rdx, aAllowremovepro; "AllowRemoveProvisioningPackage"
0x18018eaec  mov     rcx, rdi; this
0x18018eaef  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18018eaf4  test    eax, eax
0x18018eaf6  jnz     short loc_18018EB1D
0x18018eaf8  mov     rcx, [rsp+198h+String]; String
0x18018eafd  test    rcx, rcx
0x18018eb00  jz      short loc_18018EB1D
0x18018eb02  call    cs:__imp__wtoi
0x18018eb09  nop     dword ptr [rax+rax+00h]
0x18018eb0e  mov     [rsp+198h+var_80], eax
0x18018eb15  mov     [rsp+198h+var_7C], r12b
0x18018eb1d  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x18018eb22  lea     rdx, aCleartpmifnotr; "ClearTPMIfNotReady"
0x18018eb29  mov     rcx, rdi; this
0x18018eb2c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18018eb31  test    eax, eax
0x18018eb33  jnz     short loc_18018EB5A
0x18018eb35  mov     rcx, [rsp+198h+String]; String
0x18018eb3a  test    rcx, rcx
0x18018eb3d  jz      short loc_18018EB5A
0x18018eb3f  call    cs:__imp__wtoi
0x18018eb46  nop     dword ptr [rax+rax+00h]
0x18018eb4b  mov     [rsp+198h+var_78], eax
0x18018eb52  mov     [rsp+198h+var_74], r12b
0x18018eb5a  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x18018eb5f  lea     rdx, aConfigurewindo_2; "ConfigureWindowsPasswords"
0x18018eb66  mov     rcx, rdi; this
0x18018eb69  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18018eb6e  test    eax, eax
0x18018eb70  jnz     short loc_18018EB97
0x18018eb72  mov     rcx, [rsp+198h+String]; String
0x18018eb77  test    rcx, rcx
0x18018eb7a  jz      short loc_18018EB97
0x18018eb7c  call    cs:__imp__wtoi
0x18018eb83  nop     dword ptr [rax+rax+00h]
0x18018eb88  mov     [rsp+198h+var_70], eax
0x18018eb8f  mov     [rsp+198h+var_6C], r12b
0x18018eb97  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x18018eb9c  lea     rdx, aPreventautomat; "PreventAutomaticDeviceEncryptionForAzur"...
0x18018eba3  mov     rcx, rdi; this
0x18018eba6  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18018ebab  test    eax, eax
0x18018ebad  jnz     short loc_18018EBD4
0x18018ebaf  mov     rcx, [rsp+198h+String]; String
0x18018ebb4  test    rcx, rcx
0x18018ebb7  jz      short loc_18018EBD4
0x18018ebb9  call    cs:__imp__wtoi
0x18018ebc0  nop     dword ptr [rax+rax+00h]
0x18018ebc5  mov     [rsp+198h+var_68], eax
0x18018ebcc  mov     [rsp+198h+var_64], r12b
0x18018ebd4  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x18018ebd9  lea     rdx, aRecoveryenviro; "RecoveryEnvironmentAuthentication"
0x18018ebe0  mov     rcx, rdi; this
0x18018ebe3  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18018ebe8  test    eax, eax
0x18018ebea  jnz     short loc_18018EC11
0x18018ebec  mov     rcx, [rsp+198h+String]; String
0x18018ebf1  test    rcx, rcx
0x18018ebf4  jz      short loc_18018EC11
0x18018ebf6  call    cs:__imp__wtoi
0x18018ebfd  nop     dword ptr [rax+rax+00h]
0x18018ec02  mov     [rsp+198h+var_60], eax
0x18018ec09  mov     [rsp+198h+var_5C], r12b
0x18018ec11  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x18018ec16  lea     rdx, aRequiredevicee; "RequireDeviceEncryption"
0x18018ec1d  mov     rcx, rdi; this
0x18018ec20  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18018ec25  test    eax, eax
0x18018ec27  jnz     short loc_18018EC4E
0x18018ec29  mov     rcx, [rsp+198h+String]; String
0x18018ec2e  test    rcx, rcx
0x18018ec31  jz      short loc_18018EC4E
0x18018ec33  call    cs:__imp__wtoi
0x18018ec3a  nop     dword ptr [rax+rax+00h]
0x18018ec3f  mov     [rsp+198h+var_58], eax
0x18018ec46  mov     [rsp+198h+var_54], r12b
0x18018ec4e  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x18018ec53  lea     rdx, aRequireprovisi; "RequireProvisioningPackageSignature"
0x18018ec5a  mov     rcx, rdi; this
0x18018ec5d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18018ec62  test    eax, eax
0x18018ec64  jnz     short loc_18018EC8B
0x18018ec66  mov     rcx, [rsp+198h+String]; String
0x18018ec6b  test    rcx, rcx
0x18018ec6e  jz      short loc_18018EC8B
0x18018ec70  call    cs:__imp__wtoi
0x18018ec77  nop     dword ptr [rax+rax+00h]
0x18018ec7c  mov     [rsp+198h+var_50], eax
0x18018ec83  mov     [rsp+198h+var_4C], r12b
0x18018ec8b  lea     r8, [rsp+198h+String]; unsigned __int16 **
0x18018ec90  lea     rdx, aRequireretriev; "RequireRetrieveHealthCertificateOnBoot"
0x18018ec97  mov     rcx, rdi; this
0x18018ec9a  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x18018ec9f  test    eax, eax
0x18018eca1  jnz     short loc_18018ECC8
0x18018eca3  mov     rcx, [rsp+198h+String]; String
0x18018eca8  test    rcx, rcx
0x18018ecab  jz      short loc_18018ECC8
0x18018ecad  call    cs:__imp__wtoi
0x18018ecb4  nop     dword ptr [rax+rax+00h]
0x18018ecb9  mov     [rsp+198h+var_48], eax
0x18018ecc0  mov     [rsp+198h+var_44], r12b
0x18018ecc8  lea     rdx, [rsp+198h+instance]
0x18018ecd0  mov     rcx, r15; self
0x18018ecd3  call    MI_Instance_Destruct
0x18018ecd8  nop
0x18018ecd9  mov     rcx, [rsp+198h+var_148]
0x18018ecde  test    rcx, rcx
0x18018ece1  jz      short loc_18018ECF2
0x18018ece3  mov     rax, [rcx]
0x18018ece6  mov     edx, r12d
0x18018ece9  mov     rax, [rax]
0x18018ecec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018ecf1  nop
0x18018ecf2  jmp     short loc_18018ED00
0x18018ecf4  xor     ebx, ebx
0x18018ecf6  mov     esi, dword ptr [rsp+198h+String]
0x18018ecfa  cmp     [rsp+198h+var_158], bl
0x18018ecfe  jz      short loc_18018ED14
0x18018ed00  lea     rcx, [rsp+198h+instance]; self
0x18018ed08  call    MI_Instance_Destruct
0x18018ed0d  jmp     short loc_18018ED14
0x18018ed0f  mov     esi, 4
0x18018ed14  mov     r8d, esi; int
0x18018ed17  lea     rdx, aGetinstanceend; "GetInstanceEnd"
0x18018ed1e  lea     rcx, [rsp+198h+var_140]; this
0x18018ed23  call    ?WriteEnd@TelemetryEventWriter@@QEAAXPEBDH@Z; TelemetryEventWriter::WriteEnd(char const *,int)
0x18018ed28  mov     [rsp+198h+var_110], 2
0x18018ed33  mov     eax, cs:dword_180380B68
0x18018ed39  cmp     eax, 5
0x18018ed3c  jbe     short loc_18018ED77
0x18018ed3e  mov     rdx, 200000000000h
0x18018ed48  lea     rcx, dword_180380B68
0x18018ed4f  call    _tlgKeywordOn
0x18018ed54  test    al, al
0x18018ed56  jz      short loc_18018ED77
0x18018ed58  xor     r9d, r9d
0x18018ed5b  lea     r8, [rsp+198h+var_108]
  ... truncated ...
```
