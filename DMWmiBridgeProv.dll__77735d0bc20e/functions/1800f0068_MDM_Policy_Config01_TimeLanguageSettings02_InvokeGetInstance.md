# MDM_Policy_Config01_TimeLanguageSettings02_InvokeGetInstance

- ea: `0x1800f0068`
- end: `0x1800f049b`
- name: `MDM_Policy_Config01_TimeLanguageSettings02_InvokeGetInstance`
- size: `1075`
- prototype: `__int64 __fastcall(MI_Instance *self, struct _MI_Instance *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800ef440`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180003a5c`
- `0x180004f1c`
- `0x180004f8c`
- `0x180004fc4`
- `0x18000871c`
- `0x180008764`
- `0x18000a280`
- `0x1800f0068`
- `0x180240078`
- `0x180240ddc`
- `0x180243010`
- `0x180246310`
- `0x180246418`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800f0303`
- `msvcrt!_wtoi` at `0x1800f0369`
- `msvcrt!_wtoi` at `0x1800f03a0`
- `msvcrt!_wtoi` at `0x1800f0303`
- `msvcrt!_wtoi` at `0x1800f0369`
- `msvcrt!_wtoi` at `0x1800f03a0`

## string_xrefs

- `0x1800f02e6`: `BlockCleanupOfUnusedPreinstalledLangPacks`
- `0x1800f031d`: `ConfigureTimeZone`
- `0x1800f034c`: `MachineUILanguageOverwrite`
- `0x1800f0383`: `RestrictLanguagePacksAndFeaturesInstall`
- `0x1800f00d7`: `MDM_Policy_Config01_TimeLanguageSettings02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Config01_TimeLanguageSettings02_InvokeGetInstance(
        MI_Context *self,
        struct _MI_Instance *a2)
{
  _DWORD *v4; // r9
  unsigned int v5; // edi
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
    v5 = CreateRequestHandlerInstance(
           (__int64)self,
           (wchar_t *)a2[1].serverName,
           (const unsigned __int16 *)a2[1].ft,
           (struct WmiNodeInfo *)&MDM_Policy_Config01_TimeLanguageSettings02_NodeList,
           6u,
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
          (struct WmiNodeInfo *)&MDM_Policy_Config01_TimeLanguageSettings02_NodeList,
          6u);
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
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"BlockCleanupOfUnusedPreinstalledLangPacks",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v17 = _wtoi(String);
                v18 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"ConfigureTimeZone",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"MachineUILanguageOverwrite",
                                    (const unsigned __int16 **)&String)
                && String )
              {
                v19 = _wtoi(String);
                v20 = 1;
              }
              if ( !(unsigned int)WmiRequestHandler::FindResultDataForNode(
                                    v6,
                                    L"RestrictLanguagePacksAndFeaturesInstall",
                                    (const unsigned __int16 **)&String)
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
      &dword_18035B844,
      v14,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v12);
  return v5;
}

```

## disassembly

```asm
0x1800f0068  mov     [rsp+arg_10], rbx
0x1800f006d  push    rsi
0x1800f006e  push    rdi
0x1800f006f  push    r12
0x1800f0071  push    r14
0x1800f0073  push    r15
0x1800f0075  sub     rsp, 150h
0x1800f007c  mov     rax, cs:__security_cookie
0x1800f0083  xor     rax, rsp
0x1800f0086  mov     [rsp+178h+var_38], rax
0x1800f008e  mov     rsi, rdx
0x1800f0091  mov     r15, rcx
0x1800f0094  xor     ebx, ebx
0x1800f0096  mov     [rsp+178h+String], rbx
0x1800f009b  xor     edx, edx; Val
0x1800f009d  mov     r8d, 88h; Size
0x1800f00a3  lea     rcx, [rsp+178h+instance]; void *
0x1800f00ab  call    memset_0
0x1800f00b0  mov     [rsp+178h+var_F0], ebx
0x1800f00b7  mov     [rsp+178h+var_EC], bl
0x1800f00be  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800f00c5  mov     [rsp+178h+var_120], rax
0x1800f00ca  lea     rax, [rsp+178h+var_F0]
0x1800f00d2  mov     [rsp+178h+var_118], rax
0x1800f00d7  lea     rax, aMdmPolicyConfi_135; "MDM_Policy_Config01_TimeLanguageSetting"...
0x1800f00de  mov     [rsp+178h+var_110], rax
0x1800f00e3  lea     rcx, [rsp+178h+var_F0]
0x1800f00eb  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800f00f0  mov     eax, cs:dword_180380B68
0x1800f00f6  cmp     eax, 5
0x1800f00f9  jbe     short loc_1800F016A
0x1800f00fb  mov     rdx, 200000000000h
0x1800f0105  lea     rcx, dword_180380B68
0x1800f010c  call    _tlgKeywordOn
0x1800f0111  test    al, al
0x1800f0113  jz      short loc_1800F016A
0x1800f0115  cmp     [rsp+178h+var_EC], bl
0x1800f011c  jz      short loc_1800F014C
0x1800f011e  cmp     [rsp+178h+var_D8], ebx
0x1800f0125  jnz     short loc_1800F0142
0x1800f0127  cmp     [rsp+178h+var_D4], ebx
0x1800f012e  jnz     short loc_1800F0142
0x1800f0130  cmp     [rsp+178h+var_D0], ebx
0x1800f0137  jnz     short loc_1800F0142
0x1800f0139  cmp     [rsp+178h+var_CC], ebx
0x1800f0140  jz      short loc_1800F014C
0x1800f0142  lea     r9, [rsp+178h+var_D8]
0x1800f014a  jmp     short loc_1800F014F
0x1800f014c  mov     r9, rbx
0x1800f014f  lea     r8, [rsp+178h+var_E8]
0x1800f0157  lea     rdx, byte_180338E53
0x1800f015e  lea     rcx, dword_180380B68
0x1800f0165  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800f016a  cmp     [rsi+48h], bl
0x1800f016d  jz      loc_1800F03FC
0x1800f0173  mov     [rsp+178h+var_138], bl
0x1800f0177  cmp     [rsi+58h], bl
0x1800f017a  jz      loc_1800F03FC
0x1800f0180  mov     r9, [rsi+40h]; unsigned __int16 *
0x1800f0184  mov     r8, [rsi+50h]; unsigned __int16 *
0x1800f0188  lea     rdx, aGetinstancesta; "GetInstanceStart"
0x1800f018f  lea     rcx, [rsp+178h+var_120]; this
0x1800f0194  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBDPEBG1@Z; TelemetryEventWriter::WriteStart(char const *,ushort const *,ushort const *)
0x1800f0199  nop
0x1800f019a  mov     [rsp+178h+var_128], rbx
0x1800f019f  lea     rax, [rsp+178h+var_128]
0x1800f01a4  mov     [rsp+178h+var_148], rax
0x1800f01a9  mov     [rsp+178h+var_150], ebx
0x1800f01ad  mov     [rsp+178h+var_158], 6
0x1800f01b5  lea     r9, ?MDM_Policy_Config01_TimeLanguageSettings02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_TimeLanguageSettings02_NodeList
0x1800f01bc  mov     r8, [rsi+40h]
0x1800f01c0  mov     rdx, [rsi+50h]
0x1800f01c4  mov     rcx, r15
0x1800f01c7  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800f01cc  mov     edi, eax
0x1800f01ce  test    eax, eax
0x1800f01d0  jz      short loc_1800F01D7
0x1800f01d2  jmp     loc_1800F0401
0x1800f01d7  lea     rax, [rsp+178h+var_128]
0x1800f01dc  mov     [rsp+178h+var_100], rax
0x1800f01e1  mov     r12d, 1
0x1800f01e7  mov     [rsp+178h+var_F8], r12b
0x1800f01ef  mov     r14, [rsp+178h+var_128]
0x1800f01f4  test    r14, r14
0x1800f01f7  jnz     short loc_1800F0201
0x1800f01f9  mov     edi, r12d
0x1800f01fc  jmp     loc_1800F0401
0x1800f0201  mov     r9d, 6; unsigned int
0x1800f0207  lea     r8, ?MDM_Policy_Config01_TimeLanguageSettings02_NodeList@@3PAUWmiNodeInfo@@A; struct WmiNodeInfo *
0x1800f020e  mov     rdx, rsi; struct _MI_Instance *
0x1800f0211  mov     rcx, r14; this
0x1800f0214  call    ?SetRequestMIInstance@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBU_MI_Instance@@PEAUWmiNodeInfo@@K@Z; WmiRequestHandler::SetRequestMIInstance(_MI_Instance const *,WmiNodeInfo *,ulong)
0x1800f0219  mov     rax, [r14]
0x1800f021c  mov     rcx, r14
0x1800f021f  mov     rax, [rax+10h]
0x1800f0223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0228  mov     edi, eax
0x1800f022a  test    eax, eax
0x1800f022c  jz      short loc_1800F024C
0x1800f022e  mov     rcx, [rsp+178h+var_128]
0x1800f0233  test    rcx, rcx
0x1800f0236  jz      short loc_1800F0247
0x1800f0238  mov     rax, [rcx]
0x1800f023b  mov     edx, r12d
0x1800f023e  mov     rax, [rax]
0x1800f0241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0246  nop
0x1800f0247  jmp     loc_1800F0401
0x1800f024c  mov     rax, [r14]
0x1800f024f  mov     rcx, r14
0x1800f0252  mov     rax, [rax+8]
0x1800f0256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f025b  mov     edi, eax
0x1800f025d  test    eax, eax
0x1800f025f  jz      short loc_1800F027F
0x1800f0261  mov     rcx, [rsp+178h+var_128]
0x1800f0266  test    rcx, rcx
0x1800f0269  jz      short loc_1800F027A
0x1800f026b  mov     rax, [rcx]
0x1800f026e  mov     edx, r12d
0x1800f0271  mov     rax, [rax]
0x1800f0274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0279  nop
0x1800f027a  jmp     loc_1800F0401
0x1800f027f  lea     r8, [rsp+178h+instance]; instance
0x1800f0287  lea     rdx, MDM_Policy_Config01_TimeLanguageSettings02_rtti; classDecl
0x1800f028e  mov     rcx, r15; context
0x1800f0291  call    MI_Context_ConstructInstance
0x1800f0296  mov     edi, eax
0x1800f0298  test    eax, eax
0x1800f029a  jz      short loc_1800F02BA
0x1800f029c  mov     rcx, [rsp+178h+var_128]
0x1800f02a1  test    rcx, rcx
0x1800f02a4  jz      short loc_1800F02B5
0x1800f02a6  mov     rax, [rcx]
0x1800f02a9  mov     edx, r12d
0x1800f02ac  mov     rax, [rax]
0x1800f02af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f02b4  nop
0x1800f02b5  jmp     loc_1800F0401
0x1800f02ba  mov     [rsp+178h+var_138], r12b
0x1800f02bf  mov     rdx, [rsi+40h]
0x1800f02c3  lea     rcx, [rsp+178h+instance]
0x1800f02cb  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800f02d0  mov     rdx, [rsi+50h]
0x1800f02d4  lea     rcx, [rsp+178h+instance]
0x1800f02dc  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800f02e1  lea     r8, [rsp+178h+String]; unsigned __int16 **
0x1800f02e6  lea     rdx, aBlockcleanupof; "BlockCleanupOfUnusedPreinstalledLangPac"...
0x1800f02ed  mov     rcx, r14; this
0x1800f02f0  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800f02f5  test    eax, eax
0x1800f02f7  jnz     short loc_1800F0318
0x1800f02f9  mov     rcx, [rsp+178h+String]; String
0x1800f02fe  test    rcx, rcx
0x1800f0301  jz      short loc_1800F0318
0x1800f0303  call    cs:__imp__wtoi
0x1800f0309  mov     [rsp+178h+var_68], eax
0x1800f0310  mov     [rsp+178h+var_64], r12b
0x1800f0318  lea     r8, [rsp+178h+String]; unsigned __int16 **
0x1800f031d  lea     rdx, aConfiguretimez; "ConfigureTimeZone"
0x1800f0324  mov     rcx, r14; this
0x1800f0327  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800f032c  test    eax, eax
0x1800f032e  jnz     short loc_1800F0347
0x1800f0330  mov     rdx, [rsp+178h+String]
0x1800f0335  test    rdx, rdx
0x1800f0338  jz      short loc_1800F0347
0x1800f033a  lea     rcx, [rsp+178h+instance]
0x1800f0342  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x1800f0347  lea     r8, [rsp+178h+String]; unsigned __int16 **
0x1800f034c  lea     rdx, aMachineuilangu; "MachineUILanguageOverwrite"
0x1800f0353  mov     rcx, r14; this
0x1800f0356  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800f035b  test    eax, eax
0x1800f035d  jnz     short loc_1800F037E
0x1800f035f  mov     rcx, [rsp+178h+String]; String
0x1800f0364  test    rcx, rcx
0x1800f0367  jz      short loc_1800F037E
0x1800f0369  call    cs:__imp__wtoi
0x1800f036f  mov     [rsp+178h+var_50], eax
0x1800f0376  mov     [rsp+178h+var_4C], r12b
0x1800f037e  lea     r8, [rsp+178h+String]; unsigned __int16 **
0x1800f0383  lea     rdx, aRestrictlangua; "RestrictLanguagePacksAndFeaturesInstall"
0x1800f038a  mov     rcx, r14; this
0x1800f038d  call    ?FindResultDataForNode@WmiRequestHandler@@QEAA?AW4_MI_Result@@PEBGAEAPEBG@Z; WmiRequestHandler::FindResultDataForNode(ushort const *,ushort const * &)
0x1800f0392  test    eax, eax
0x1800f0394  jnz     short loc_1800F03B5
0x1800f0396  mov     rcx, [rsp+178h+String]; String
0x1800f039b  test    rcx, rcx
0x1800f039e  jz      short loc_1800F03B5
0x1800f03a0  call    cs:__imp__wtoi
0x1800f03a6  mov     [rsp+178h+var_48], eax
0x1800f03ad  mov     [rsp+178h+var_44], r12b
0x1800f03b5  lea     rdx, [rsp+178h+instance]
0x1800f03bd  mov     rcx, r15; self
0x1800f03c0  call    MI_Instance_Destruct
0x1800f03c5  nop
0x1800f03c6  mov     rcx, [rsp+178h+var_128]
0x1800f03cb  test    rcx, rcx
0x1800f03ce  jz      short loc_1800F03DF
0x1800f03d0  mov     rax, [rcx]
0x1800f03d3  mov     edx, r12d
0x1800f03d6  mov     rax, [rax]
0x1800f03d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f03de  nop
0x1800f03df  jmp     short loc_1800F03ED
0x1800f03e1  xor     ebx, ebx
0x1800f03e3  mov     edi, dword ptr [rsp+178h+String]
0x1800f03e7  cmp     [rsp+178h+var_138], bl
0x1800f03eb  jz      short loc_1800F0401
0x1800f03ed  lea     rcx, [rsp+178h+instance]; self
0x1800f03f5  call    MI_Instance_Destruct
0x1800f03fa  jmp     short loc_1800F0401
0x1800f03fc  mov     edi, 4
0x1800f0401  mov     r8d, edi; int
0x1800f0404  lea     rdx, aGetinstanceend; "GetInstanceEnd"
0x1800f040b  lea     rcx, [rsp+178h+var_120]; this
0x1800f0410  call    ?WriteEnd@TelemetryEventWriter@@QEAAXPEBDH@Z; TelemetryEventWriter::WriteEnd(char const *,int)
0x1800f0415  mov     [rsp+178h+var_F0], 2
0x1800f0420  mov     eax, cs:dword_180380B68
0x1800f0426  cmp     eax, 5
0x1800f0429  jbe     short loc_1800F0464
0x1800f042b  mov     rdx, 200000000000h
0x1800f0435  lea     rcx, dword_180380B68
0x1800f043c  call    _tlgKeywordOn
0x1800f0441  test    al, al
0x1800f0443  jz      short loc_1800F0464
0x1800f0445  xor     r9d, r9d
0x1800f0448  lea     r8, [rsp+178h+var_E8]
0x1800f0450  lea     rdx, dword_18035B844
0x1800f0457  lea     rcx, dword_180380B68
0x1800f045e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800f0463  nop
0x1800f0464  lea     rcx, [rsp+178h+var_F0]
0x1800f046c  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(void)
0x1800f0471  mov     eax, edi
0x1800f0473  mov     rcx, [rsp+178h+var_38]
0x1800f047b  xor     rcx, rsp; StackCookie
0x1800f047e  call    __security_check_cookie
0x1800f0483  mov     rbx, [rsp+178h+arg_10]
0x1800f048b  add     rsp, 150h
0x1800f0492  pop     r15
0x1800f0494  pop     r14
0x1800f0496  pop     r12
0x1800f0498  pop     rdi
0x1800f0499  pop     rsi
0x1800f049a  retn
```
