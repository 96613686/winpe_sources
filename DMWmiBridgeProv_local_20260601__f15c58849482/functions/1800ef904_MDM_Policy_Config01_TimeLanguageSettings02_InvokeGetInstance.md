# MDM_Policy_Config01_TimeLanguageSettings02_InvokeGetInstance

- ea: `0x1800ef904`
- end: `0x1800efd4a`
- name: `MDM_Policy_Config01_TimeLanguageSettings02_InvokeGetInstance`
- size: `1094`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800eecd0`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003abc`
- `0x1800050f0`
- `0x180005160`
- `0x180005198`
- `0x180008ac0`
- `0x180008b08`
- `0x18000a768`
- `0x1800ef904`
- `0x18023f3ac`
- `0x1802400f0`
- `0x18024237c`
- `0x180245824`
- `0x180245930`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800efb9f`
- `msvcrt!_wtoi` at `0x1800efc0b`
- `msvcrt!_wtoi` at `0x1800efc48`
- `msvcrt!_wtoi` at `0x1800efb9f`
- `msvcrt!_wtoi` at `0x1800efc0b`
- `msvcrt!_wtoi` at `0x1800efc48`

## string_xrefs

- `0x1800efb82`: `BlockCleanupOfUnusedPreinstalledLangPacks`
- `0x1800efbbf`: `ConfigureTimeZone`
- `0x1800efbee`: `MachineUILanguageOverwrite`
- `0x1800efc2b`: `RestrictLanguagePacksAndFeaturesInstall`
- `0x1800ef973`: `MDM_Policy_Config01_TimeLanguageSettings02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Config01_TimeLanguageSettings02_InvokeGetInstance(
        MI_Context *self,
        struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  MI_Result v5; // edi
  WmiRequestHandler *v6; // r14
  wchar_t *String; // [rsp+48h] [rbp-130h] BYREF
  WmiRequestHandler *v9; // [rsp+50h] [rbp-128h] BYREF
  _QWORD v10[5]; // [rsp+58h] [rbp-120h] BYREF
  char v11; // [rsp+80h] [rbp-F8h]
  int v12; // [rsp+88h] [rbp-F0h] BYREF
  char v13; // [rsp+8Ch] [rbp-ECh]
  _BYTE v14[16]; // [rsp+90h] [rbp-E8h] BYREF
  _DWORD v15[4]; // [rsp+A0h] [rbp-D8h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-C8h] BYREF
  int v17; // [rsp+110h] [rbp-68h]
  char v18; // [rsp+114h] [rbp-64h]
  int v19; // [rsp+128h] [rbp-50h]
  char v20; // [rsp+12Ch] [rbp-4Ch]
  int v21; // [rsp+130h] [rbp-48h]
  char v22; // [rsp+134h] [rbp-44h]

  String = 0;
  memset_0(&instance, 0, 0x88u);
  v12 = 0;
  v13 = 0;
  v10[0] = &TelemetryEventWriter::`vftable';
  v10[1] = &v12;
  v10[2] = "MDM_Policy_Config01_TimeLanguageSettings02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v12);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v13 && (v15[0] || v15[1] || v15[2] || v15[3]) )
      v4 = v15;
    else
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      byte_180338E53,
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
                         &MDM_Policy_Config01_TimeLanguageSettings02_NodeList,
                         6,
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
          (struct WmiNodeInfo *)&MDM_Policy_Config01_TimeLanguageSettings02_NodeList,
          6u);
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
            v5 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_TimeLanguageSettings02_rtti, &instance);
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
                     L"BlockCleanupOfUnusedPreinstalledLangPacks",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v17 = _wtoi(String);
                v18 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"ConfigureTimeZone",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"MachineUILanguageOverwrite",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v19 = _wtoi(String);
                v20 = 1;
              }
              if ( WmiRequestHandler::FindResultDataForNode(
                     v6,
                     L"RestrictLanguagePacksAndFeaturesInstall",
                     (const unsigned __int16 **)&String) == MI_RESULT_OK
                && String )
              {
                v21 = _wtoi(String);
                v22 = 1;
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
      &dword_18035B844,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800ef904  mov     [rsp+arg_10], rbx
0x1800ef909  push    rsi
0x1800ef90a  push    rdi
0x1800ef90b  push    r12
0x1800ef90d  push    r14
0x1800ef90f  push    r15
0x1800ef911  sub     rsp, 150h
0x1800ef918  mov     rax, cs:__security_cookie
0x1800ef91f  xor     rax, rsp
0x1800ef922  mov     [rsp+178h+var_38], rax
0x1800ef92a  mov     rsi, rdx
0x1800ef92d  mov     r15, rcx
0x1800ef930  xor     ebx, ebx
0x1800ef932  mov     [rsp+178h+String], rbx
0x1800ef937  xor     edx, edx; Val
0x1800ef939  mov     r8d, 88h; Size
0x1800ef93f  lea     rcx, [rsp+178h+instance]; void *
0x1800ef947  call    memset_0
0x1800ef94c  mov     [rsp+178h+var_F0], ebx
0x1800ef953  mov     [rsp+178h+var_EC], bl
0x1800ef95a  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800ef961  mov     [rsp+178h+var_120], rax
0x1800ef966  lea     rax, [rsp+178h+var_F0]
0x1800ef96e  mov     [rsp+178h+var_118], rax
0x1800ef973  lea     rax, aMdmPolicyConfi_135; "MDM_Policy_Config01_TimeLanguageSetting"...
0x1800ef97a  mov     [rsp+178h+var_110], rax
0x1800ef97f  lea     rcx, [rsp+178h+var_F0]
0x1800ef987  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800ef98c  mov     eax, cs:dword_180380B68
0x1800ef992  cmp     eax, 5
0x1800ef995  jbe     short loc_1800EFA06
0x1800ef997  mov     rdx, 200000000000h
0x1800ef9a1  lea     rcx, dword_180380B68
0x1800ef9a8  call    _tlgKeywordOn
0x1800ef9ad  test    al, al
0x1800ef9af  jz      short loc_1800EFA06
0x1800ef9b1  cmp     [rsp+178h+var_EC], bl
0x1800ef9b8  jz      short loc_1800EF9E8
0x1800ef9ba  cmp     [rsp+178h+var_D8], ebx
0x1800ef9c1  jnz     short loc_1800EF9DE
0x1800ef9c3  cmp     [rsp+178h+var_D4], ebx
0x1800ef9ca  jnz     short loc_1800EF9DE
0x1800ef9cc  cmp     [rsp+178h+var_D0], ebx
0x1800ef9d3  jnz     short loc_1800EF9DE
0x1800ef9d5  cmp     [rsp+178h+var_CC], ebx
0x1800ef9dc  jz      short loc_1800EF9E8
0x1800ef9de  lea     r9, [rsp+178h+var_D8]
0x1800ef9e6  jmp     short loc_1800EF9EB
0x1800ef9e8  mov     r9, rbx
0x1800ef9eb  lea     r8, [rsp+178h+var_E8]
0x1800ef9f3  lea     rdx, byte_180338E53
0x1800ef9fa  lea     rcx, dword_180380B68
0x1800efa01  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800efa06  cmp     [rsi+48h], bl
0x1800efa09  jz      loc_1800EFCAA
0x1800efa0f  mov     [rsp+178h+var_138], bl
0x1800efa13  cmp     [rsi+58h], bl
0x1800efa16  jz      loc_1800EFCAA
0x1800efa1c  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800efa20  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800efa24  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1800efa2b  lea     rcx, [rsp+178h+var_120]; this
0x1800efa30  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800efa35  nop
0x1800efa36  mov     [rsp+178h+var_128], rbx
0x1800efa3b  lea     rax, [rsp+178h+var_128]
0x1800efa40  mov     [rsp+178h+var_148], rax
0x1800efa45  mov     [rsp+178h+var_150], ebx
0x1800efa49  mov     [rsp+178h+var_158], 6
0x1800efa51  lea     r9, ?MDM_Policy_Config01_TimeLanguageSettings02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_TimeLanguageSettings02_NodeList
0x1800efa58  mov     r8, [rsi+40h]
0x1800efa5c  mov     rdx, [rsi+50h]
0x1800efa60  mov     rcx, r15
0x1800efa63  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800efa68  mov     edi, eax
0x1800efa6a  test    eax, eax
0x1800efa6c  jz      short loc_1800EFA73
0x1800efa6e  jmp     loc_1800EFCAF
0x1800efa73  lea     rax, [rsp+178h+var_128]
0x1800efa78  mov     [rsp+178h+var_100], rax
0x1800efa7d  mov     r12d, 1
0x1800efa83  mov     [rsp+178h+var_F8], r12b
0x1800efa8b  mov     r14, [rsp+178h+var_128]
0x1800efa90  test    r14, r14
0x1800efa93  jnz     short loc_1800EFA9D
0x1800efa95  mov     edi, r12d
0x1800efa98  jmp     loc_1800EFCAF
0x1800efa9d  mov     r9d, 6; unsigned int
0x1800efaa3  lea     r8, ?MDM_Policy_Config01_TimeLanguageSettings02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800efaaa  mov     rdx, rsi; struct _MI_Instance *
0x1800efaad  mov     rcx, r14; this
0x1800efab0  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800efab5  mov     rax, [r14]
0x1800efab8  mov     rcx, r14
0x1800efabb  mov     rax, [rax+10h]
0x1800efabf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efac4  mov     edi, eax
0x1800efac6  test    eax, eax
0x1800efac8  jz      short loc_1800EFAE8
0x1800efaca  mov     rcx, [rsp+178h+var_128]
0x1800efacf  test    rcx, rcx
0x1800efad2  jz      short loc_1800EFAE3
0x1800efad4  mov     rax, [rcx]
0x1800efad7  mov     edx, r12d
0x1800efada  mov     rax, [rax]
0x1800efadd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efae2  nop
0x1800efae3  jmp     loc_1800EFCAF
0x1800efae8  mov     rax, [r14]
0x1800efaeb  mov     rcx, r14
0x1800efaee  mov     rax, [rax+8]
0x1800efaf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efaf7  mov     edi, eax
0x1800efaf9  test    eax, eax
0x1800efafb  jz      short loc_1800EFB1B
0x1800efafd  mov     rcx, [rsp+178h+var_128]
0x1800efb02  test    rcx, rcx
0x1800efb05  jz      short loc_1800EFB16
0x1800efb07  mov     rax, [rcx]
0x1800efb0a  mov     edx, r12d
0x1800efb0d  mov     rax, [rax]
0x1800efb10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efb15  nop
0x1800efb16  jmp     loc_1800EFCAF
0x1800efb1b  lea     r8, [rsp+178h+instance]; instance
0x1800efb23  lea     rdx, MDM_Policy_Config01_TimeLanguageSettings02_rtti; classDecl
0x1800efb2a  mov     rcx, r15; context
0x1800efb2d  call    MI_Context_ConstructInstance
0x1800efb32  mov     edi, eax
0x1800efb34  test    eax, eax
0x1800efb36  jz      short loc_1800EFB56
0x1800efb38  mov     rcx, [rsp+178h+var_128]
0x1800efb3d  test    rcx, rcx
0x1800efb40  jz      short loc_1800EFB51
0x1800efb42  mov     rax, [rcx]
0x1800efb45  mov     edx, r12d
0x1800efb48  mov     rax, [rax]
0x1800efb4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efb50  nop
0x1800efb51  jmp     loc_1800EFCAF
0x1800efb56  mov     [rsp+178h+var_138], r12b
0x1800efb5b  mov     rdx, [rsi+40h]
0x1800efb5f  lea     rcx, [rsp+178h+instance]
0x1800efb67  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800efb6c  mov     rdx, [rsi+50h]
0x1800efb70  lea     rcx, [rsp+178h+instance]
0x1800efb78  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800efb7d  lea     r8, [rsp+178h+String]; unsigned __int16 **
0x1800efb82  lea     rdx, aBlockcleanupof; "BlockCleanupOfUnusedPreinstalledLangPac"...
0x1800efb89  mov     rcx, r14; this
0x1800efb8c  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800efb91  test    eax, eax
0x1800efb93  jnz     short loc_1800EFBBA
0x1800efb95  mov     rcx, [rsp+178h+String]; String
0x1800efb9a  test    rcx, rcx
0x1800efb9d  jz      short loc_1800EFBBA
0x1800efb9f  call    cs:__imp__wtoi
0x1800efba6  nop     dword ptr [rax+rax+00h]
0x1800efbab  mov     [rsp+178h+var_68], eax
0x1800efbb2  mov     [rsp+178h+var_64], r12b
0x1800efbba  lea     r8, [rsp+178h+String]; unsigned __int16 **
0x1800efbbf  lea     rdx, aConfiguretimez; "ConfigureTimeZone"
0x1800efbc6  mov     rcx, r14; this
0x1800efbc9  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800efbce  test    eax, eax
0x1800efbd0  jnz     short loc_1800EFBE9
0x1800efbd2  mov     rdx, [rsp+178h+String]
0x1800efbd7  test    rdx, rdx
0x1800efbda  jz      short loc_1800EFBE9
0x1800efbdc  lea     rcx, [rsp+178h+instance]
0x1800efbe4  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x1800efbe9  lea     r8, [rsp+178h+String]; unsigned __int16 **
0x1800efbee  lea     rdx, aMachineuilangu; "MachineUILanguageOverwrite"
0x1800efbf5  mov     rcx, r14; this
0x1800efbf8  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800efbfd  test    eax, eax
0x1800efbff  jnz     short loc_1800EFC26
0x1800efc01  mov     rcx, [rsp+178h+String]; String
0x1800efc06  test    rcx, rcx
0x1800efc09  jz      short loc_1800EFC26
0x1800efc0b  call    cs:__imp__wtoi
0x1800efc12  nop     dword ptr [rax+rax+00h]
0x1800efc17  mov     [rsp+178h+var_50], eax
0x1800efc1e  mov     [rsp+178h+var_4C], r12b
0x1800efc26  lea     r8, [rsp+178h+String]; unsigned __int16 **
0x1800efc2b  lea     rdx, aRestrictlangua; "RestrictLanguagePacksAndFeaturesInstall"
0x1800efc32  mov     rcx, r14; this
0x1800efc35  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800efc3a  test    eax, eax
0x1800efc3c  jnz     short loc_1800EFC63
0x1800efc3e  mov     rcx, [rsp+178h+String]; String
0x1800efc43  test    rcx, rcx
0x1800efc46  jz      short loc_1800EFC63
0x1800efc48  call    cs:__imp__wtoi
0x1800efc4f  nop     dword ptr [rax+rax+00h]
0x1800efc54  mov     [rsp+178h+var_48], eax
0x1800efc5b  mov     [rsp+178h+var_44], r12b
0x1800efc63  lea     rdx, [rsp+178h+instance]
0x1800efc6b  mov     rcx, r15; self
0x1800efc6e  call    MI_Instance_Destruct
0x1800efc73  nop
0x1800efc74  mov     rcx, [rsp+178h+var_128]
0x1800efc79  test    rcx, rcx
0x1800efc7c  jz      short loc_1800EFC8D
0x1800efc7e  mov     rax, [rcx]
0x1800efc81  mov     edx, r12d
0x1800efc84  mov     rax, [rax]
0x1800efc87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efc8c  nop
0x1800efc8d  jmp     short loc_1800EFC9B
0x1800efc8f  xor     ebx, ebx
0x1800efc91  mov     edi, dword ptr [rsp+178h+String]
0x1800efc95  cmp     [rsp+178h+var_138], bl
0x1800efc99  jz      short loc_1800EFCAF
0x1800efc9b  lea     rcx, [rsp+178h+instance]; self
0x1800efca3  call    MI_Instance_Destruct
0x1800efca8  jmp     short loc_1800EFCAF
0x1800efcaa  mov     edi, 4
0x1800efcaf  mov     r8d, edi; int
0x1800efcb2  lea     rdx, aGetinstanceend; "GetInstanceEnd"
0x1800efcb9  lea     rcx, [rsp+178h+var_120]; this
0x1800efcbe  call    ?WriteEnd@TelemetryEventWriter@@QEAAXPEBDH@Z; TelemetryEventWriter::WriteEnd(char const *,int)
0x1800efcc3  mov     [rsp+178h+var_F0], 2
0x1800efcce  mov     eax, cs:dword_180380B68
0x1800efcd4  cmp     eax, 5
0x1800efcd7  jbe     short loc_1800EFD12
0x1800efcd9  mov     rdx, 200000000000h
0x1800efce3  lea     rcx, dword_180380B68
0x1800efcea  call    _tlgKeywordOn
0x1800efcef  test    al, al
0x1800efcf1  jz      short loc_1800EFD12
0x1800efcf3  xor     r9d, r9d
0x1800efcf6  lea     r8, [rsp+178h+var_E8]
0x1800efcfe  lea     rdx, dword_18035B844
0x1800efd05  lea     rcx, dword_180380B68
0x1800efd0c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800efd11  nop
0x1800efd12  lea     rcx, [rsp+178h+var_F0]
0x1800efd1a  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(void)
0x1800efd1f  mov     eax, edi
0x1800efd21  mov     rcx, [rsp+178h+var_38]
0x1800efd29  xor     rcx, rsp; StackCookie
0x1800efd2c  call    __security_check_cookie
0x1800efd31  mov     rbx, [rsp+178h+arg_10]
0x1800efd39  add     rsp, 150h
0x1800efd40  pop     r15
0x1800efd42  pop     r14
0x1800efd44  pop     r12
0x1800efd46  pop     rdi
0x1800efd47  pop     rsi
0x1800efd48  retn
```
