# MDM_Policy_Config01_TimeLanguageSettings02_InvokeEnumerateInstances

- ea: `0x1800efb84`
- end: `0x1800f0062`
- name: `MDM_Policy_Config01_TimeLanguageSettings02_InvokeEnumerateInstances`
- size: `1246`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800ef400`

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
- `0x1800efb84`
- `0x180240078`
- `0x180246310`
- `0x180246398`
- `0x18024d12e`
- `0x18024d160`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800efe92`
- `msvcrt!_wtoi` at `0x1800eff0c`
- `msvcrt!_wtoi` at `0x1800eff4d`
- `msvcrt!_wtoi` at `0x1800efe92`
- `msvcrt!_wtoi` at `0x1800eff0c`
- `msvcrt!_wtoi` at `0x1800eff4d`

## string_xrefs

- `0x1800efe6e`: `BlockCleanupOfUnusedPreinstalledLangPacks`
- `0x1800efeaf`: `ConfigureTimeZone`
- `0x1800efee8`: `MachineUILanguageOverwrite`
- `0x1800eff29`: `RestrictLanguagePacksAndFeaturesInstall`
- `0x1800efdd4`: `./Vendor/MSFT/Policy/Config`
- `0x1800efbff`: `MDM_Policy_Config01_TimeLanguageSettings02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Config01_TimeLanguageSettings02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  unsigned int v6; // esi
  WmiRequestHandlerAdd *v7; // r14
  unsigned int i; // r15d
  wchar_t *String; // [rsp+48h] [rbp-130h] BYREF
  WmiRequestHandlerAdd *v11; // [rsp+50h] [rbp-128h] BYREF
  _QWORD v12[5]; // [rsp+58h] [rbp-120h] BYREF
  char v13; // [rsp+80h] [rbp-F8h]
  int v14; // [rsp+88h] [rbp-F0h] BYREF
  char v15; // [rsp+8Ch] [rbp-ECh]
  _BYTE v16[16]; // [rsp+90h] [rbp-E8h] BYREF
  _DWORD v17[4]; // [rsp+A0h] [rbp-D8h] BYREF
  MI_Instance instance; // [rsp+B0h] [rbp-C8h] BYREF
  int v19; // [rsp+110h] [rbp-68h]
  char v20; // [rsp+114h] [rbp-64h]
  int v21; // [rsp+128h] [rbp-50h]
  char v22; // [rsp+12Ch] [rbp-4Ch]
  int v23; // [rsp+130h] [rbp-48h]
  char v24; // [rsp+134h] [rbp-44h]

  memset_0(&instance, 0, 0x88u);
  String = 0;
  v14 = 0;
  v15 = 0;
  v12[0] = &TelemetryEventWriter::`vftable';
  v12[1] = &v14;
  v12[2] = "MDM_Policy_Config01_TimeLanguageSettings02";
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(&v14);
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
  {
    if ( v15 && (v17[0] || v17[1] || v17[2] || v17[3]) )
      v5 = v17;
    else
      v5 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &dword_18035933C,
      v16,
      v5);
  }
  TelemetryEventWriter::WriteStart((TelemetryEventWriter *)v12, v4);
  v11 = 0;
  v6 = CreateRequestHandlerInstance(
         (__int64)self,
         0,
         0,
         (struct WmiNodeInfo *)&MDM_Policy_Config01_TimeLanguageSettings02_NodeList,
         6u,
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
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_TimeLanguageSettings02_rtti, &instance);
            if ( v6 )
            {
              if ( v11 )
              {
                (**(void (__fastcall ***)(WmiRequestHandlerAdd *, __int64))v11)(v11, 1);
                v11 = 0;
              }
              goto LABEL_50;
            }
            if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                    v7,
                    i,
                    L"./Vendor/MSFT/Policy/Config",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
            }
            if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const wchar_t *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                    v7,
                    i,
                    L"TimeLanguageSettings",
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
                      L"BlockCleanupOfUnusedPreinstalledLangPacks",
                      &String)
                && String )
              {
                v19 = _wtoi(String);
                v20 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureTimeZone",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"MachineUILanguageOverwrite",
                      &String)
                && String )
              {
                v21 = _wtoi(String);
                v22 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(WmiRequestHandlerAdd *, _QWORD, const unsigned __int16 *, wchar_t **))(*(_QWORD *)v7 + 24LL))(
                      v7,
                      i,
                      L"RestrictLanguagePacksAndFeaturesInstall",
                      &String)
                && String )
              {
                v23 = _wtoi(String);
                v24 = 1;
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
LABEL_50:
  TelemetryEventWriter::WriteEnd((TelemetryEventWriter *)v12, "EnumerateInstancesEnd", v6);
  v14 = 2;
  if ( (unsigned int)dword_180380B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180380B68, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180380B68,
      &unk_180338B78,
      v16,
      0);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(&v14);
  return v6;
}

```

## disassembly

```asm
0x1800efb84  mov     [rsp+arg_8], rbx
0x1800efb89  mov     [rsp+arg_10], rsi
0x1800efb8e  push    rdi
0x1800efb8f  push    r12
0x1800efb91  push    r13
0x1800efb93  push    r14
0x1800efb95  push    r15
0x1800efb97  sub     rsp, 150h
0x1800efb9e  mov     rax, cs:__security_cookie
0x1800efba5  xor     rax, rsp
0x1800efba8  mov     [rsp+178h+var_38], rax
0x1800efbb0  mov     r13b, dl
0x1800efbb3  mov     r12, rcx
0x1800efbb6  xor     edx, edx; Val
0x1800efbb8  mov     r8d, 88h; Size
0x1800efbbe  lea     rcx, [rsp+178h+instance]; void *
0x1800efbc6  call    memset_0
0x1800efbcb  xor     edi, edi
0x1800efbcd  mov     [rsp+178h+var_138], dil
0x1800efbd2  mov     [rsp+178h+String], rdi
0x1800efbd7  mov     [rsp+178h+var_F0], edi
0x1800efbde  mov     [rsp+178h+var_EC], dil
0x1800efbe6  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800efbed  mov     [rsp+178h+var_120], rax
0x1800efbf2  lea     rax, [rsp+178h+var_F0]
0x1800efbfa  mov     [rsp+178h+var_118], rax
0x1800efbff  lea     rax, aMdmPolicyConfi_135; "MDM_Policy_Config01_TimeLanguageSetting"...
0x1800efc06  mov     [rsp+178h+var_110], rax
0x1800efc0b  lea     rcx, [rsp+178h+var_F0]
0x1800efc13  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800efc18  mov     eax, cs:dword_180380B68
0x1800efc1e  cmp     eax, 5
0x1800efc21  jbe     short loc_1800EFC93
0x1800efc23  mov     rdx, 200000000000h
0x1800efc2d  lea     rcx, dword_180380B68
0x1800efc34  call    _tlgKeywordOn
0x1800efc39  test    al, al
0x1800efc3b  jz      short loc_1800EFC93
0x1800efc3d  cmp     [rsp+178h+var_EC], dil
0x1800efc45  jz      short loc_1800EFC75
0x1800efc47  cmp     [rsp+178h+var_D8], edi
0x1800efc4e  jnz     short loc_1800EFC6B
0x1800efc50  cmp     [rsp+178h+var_D4], edi
0x1800efc57  jnz     short loc_1800EFC6B
0x1800efc59  cmp     [rsp+178h+var_D0], edi
0x1800efc60  jnz     short loc_1800EFC6B
0x1800efc62  cmp     [rsp+178h+var_CC], edi
0x1800efc69  jz      short loc_1800EFC75
0x1800efc6b  lea     r9, [rsp+178h+var_D8]
0x1800efc73  jmp     short loc_1800EFC78
0x1800efc75  mov     r9, rdi
0x1800efc78  lea     r8, [rsp+178h+var_E8]
0x1800efc80  lea     rdx, dword_18035933C
0x1800efc87  lea     rcx, dword_180380B68
0x1800efc8e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800efc93  lea     rcx, [rsp+178h+var_120]; this
0x1800efc98  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800efc9d  nop
0x1800efc9e  mov     [rsp+178h+var_128], rdi
0x1800efca3  lea     rax, [rsp+178h+var_128]
0x1800efca8  mov     [rsp+178h+var_148], rax
0x1800efcad  mov     [rsp+178h+var_150], 2
0x1800efcb5  mov     [rsp+178h+var_158], 6
0x1800efcbd  lea     r9, ?MDM_Policy_Config01_TimeLanguageSettings02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_TimeLanguageSettings02_NodeList
0x1800efcc4  xor     r8d, r8d
0x1800efcc7  xor     edx, edx
0x1800efcc9  mov     rcx, r12
0x1800efccc  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800efcd1  mov     esi, eax
0x1800efcd3  test    eax, eax
0x1800efcd5  jz      short loc_1800EFCDC
0x1800efcd7  jmp     loc_1800EFFC3
0x1800efcdc  lea     rbx, [rsp+178h+var_128]
0x1800efce1  mov     [rsp+178h+var_100], rbx
0x1800efce6  mov     r15d, 1
0x1800efcec  mov     [rsp+178h+var_F8], r15b
0x1800efcf4  mov     r14, [rsp+178h+var_128]
0x1800efcf9  test    r14, r14
0x1800efcfc  jnz     short loc_1800EFD06
0x1800efcfe  mov     esi, r15d
0x1800efd01  jmp     loc_1800EFFC3
0x1800efd06  mov     rax, [r14]
0x1800efd09  mov     rcx, r14
0x1800efd0c  mov     rax, [rax+10h]
0x1800efd10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efd15  mov     esi, eax
0x1800efd17  test    eax, eax
0x1800efd19  jz      short loc_1800EFD39
0x1800efd1b  mov     rcx, [rsp+178h+var_128]
0x1800efd20  test    rcx, rcx
0x1800efd23  jz      short loc_1800EFD34
0x1800efd25  mov     rax, [rcx]
0x1800efd28  mov     edx, r15d
0x1800efd2b  mov     rax, [rax]
0x1800efd2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efd33  nop
0x1800efd34  jmp     loc_1800EFFC3
0x1800efd39  mov     rax, [r14]
0x1800efd3c  mov     rcx, r14
0x1800efd3f  mov     rax, [rax+8]
0x1800efd43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efd48  mov     esi, eax
0x1800efd4a  test    eax, eax
0x1800efd4c  jz      short loc_1800EFD6C
0x1800efd4e  mov     rcx, [rsp+178h+var_128]
0x1800efd53  test    rcx, rcx
0x1800efd56  jz      short loc_1800EFD67
0x1800efd58  mov     rax, [rcx]
0x1800efd5b  mov     edx, r15d
0x1800efd5e  mov     rax, [rax]
0x1800efd61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efd66  nop
0x1800efd67  jmp     loc_1800EFFC3
0x1800efd6c  mov     r15d, edi
0x1800efd6f  mov     rax, [r14+108h]
0x1800efd76  sub     rax, [r14+100h]
0x1800efd7d  sar     rax, 4
0x1800efd81  cmp     r15d, eax
0x1800efd84  jnb     loc_1800EFF8C
0x1800efd8a  lea     r8, [rsp+178h+instance]; instance
0x1800efd92  lea     rdx, MDM_Policy_Config01_TimeLanguageSettings02_rtti; classDecl
0x1800efd99  mov     rcx, r12; context
0x1800efd9c  call    MI_Context_ConstructInstance
0x1800efda1  mov     esi, eax
0x1800efda3  test    eax, eax
0x1800efda5  jz      short loc_1800EFDC7
0x1800efda7  mov     rcx, [rbx]
0x1800efdaa  test    rcx, rcx
0x1800efdad  jz      short loc_1800EFDC2
0x1800efdaf  mov     rax, [rcx]
0x1800efdb2  mov     edx, 1
0x1800efdb7  mov     rax, [rax]
0x1800efdba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efdbf  mov     [rbx], rdi
0x1800efdc2  jmp     loc_1800EFFC3
0x1800efdc7  mov     [rsp+178h+var_138], 1
0x1800efdcc  mov     rax, [r14]
0x1800efdcf  lea     r9, [rsp+178h+String]
0x1800efdd4  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800efddb  mov     edx, r15d
0x1800efdde  mov     rcx, r14
0x1800efde1  mov     rax, [rax+18h]
0x1800efde5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efdea  test    eax, eax
0x1800efdec  jnz     short loc_1800EFE05
0x1800efdee  mov     rdx, [rsp+178h+String]
0x1800efdf3  test    rdx, rdx
0x1800efdf6  jz      short loc_1800EFE05
0x1800efdf8  lea     rcx, [rsp+178h+instance]
0x1800efe00  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800efe05  mov     rax, [r14]
0x1800efe08  lea     r9, [rsp+178h+String]
0x1800efe0d  lea     r8, aTimelanguagese; "TimeLanguageSettings"
0x1800efe14  mov     edx, r15d
0x1800efe17  mov     rcx, r14
0x1800efe1a  mov     rax, [rax+18h]
0x1800efe1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efe23  test    eax, eax
0x1800efe25  jnz     short loc_1800EFE3E
0x1800efe27  mov     rdx, [rsp+178h+String]
0x1800efe2c  test    rdx, rdx
0x1800efe2f  jz      short loc_1800EFE3E
0x1800efe31  lea     rcx, [rsp+178h+instance]
0x1800efe39  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800efe3e  cmp     r13b, 1
0x1800efe42  jnz     short loc_1800EFE66
0x1800efe44  lea     rdx, [rsp+178h+instance]
0x1800efe4c  mov     rcx, r12; self
0x1800efe4f  call    MI_Instance_Destruct
0x1800efe54  lea     rcx, [rsp+178h+instance]; self
0x1800efe5c  call    MI_Instance_Destruct
0x1800efe61  jmp     loc_1800EFF7F
0x1800efe66  mov     rax, [r14]
0x1800efe69  lea     r9, [rsp+178h+String]
0x1800efe6e  lea     r8, aBlockcleanupof; "BlockCleanupOfUnusedPreinstalledLangPac"...
0x1800efe75  mov     edx, r15d
0x1800efe78  mov     rcx, r14
0x1800efe7b  mov     rax, [rax+18h]
0x1800efe7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efe84  test    eax, eax
0x1800efe86  jnz     short loc_1800EFEA7
0x1800efe88  mov     rcx, [rsp+178h+String]; String
0x1800efe8d  test    rcx, rcx
0x1800efe90  jz      short loc_1800EFEA7
0x1800efe92  call    cs:__imp__wtoi
0x1800efe98  mov     [rsp+178h+var_68], eax
0x1800efe9f  mov     [rsp+178h+var_64], 1
0x1800efea7  mov     rax, [r14]
0x1800efeaa  lea     r9, [rsp+178h+String]
0x1800efeaf  lea     r8, aConfiguretimez; "ConfigureTimeZone"
0x1800efeb6  mov     edx, r15d
0x1800efeb9  mov     rcx, r14
0x1800efebc  mov     rax, [rax+18h]
0x1800efec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efec5  test    eax, eax
0x1800efec7  jnz     short loc_1800EFEE0
0x1800efec9  mov     rdx, [rsp+178h+String]
0x1800efece  test    rdx, rdx
0x1800efed1  jz      short loc_1800EFEE0
0x1800efed3  lea     rcx, [rsp+178h+instance]
0x1800efedb  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x1800efee0  mov     rax, [r14]
0x1800efee3  lea     r9, [rsp+178h+String]
0x1800efee8  lea     r8, aMachineuilangu; "MachineUILanguageOverwrite"
0x1800efeef  mov     edx, r15d
0x1800efef2  mov     rcx, r14
0x1800efef5  mov     rax, [rax+18h]
0x1800efef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800efefe  test    eax, eax
0x1800eff00  jnz     short loc_1800EFF21
0x1800eff02  mov     rcx, [rsp+178h+String]; String
0x1800eff07  test    rcx, rcx
0x1800eff0a  jz      short loc_1800EFF21
0x1800eff0c  call    cs:__imp__wtoi
0x1800eff12  mov     [rsp+178h+var_50], eax
0x1800eff19  mov     [rsp+178h+var_4C], 1
0x1800eff21  mov     rax, [r14]
0x1800eff24  lea     r9, [rsp+178h+String]
0x1800eff29  lea     r8, aRestrictlangua; "RestrictLanguagePacksAndFeaturesInstall"
0x1800eff30  mov     edx, r15d
0x1800eff33  mov     rcx, r14
0x1800eff36  mov     rax, [rax+18h]
0x1800eff3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eff3f  test    eax, eax
0x1800eff41  jnz     short loc_1800EFF62
0x1800eff43  mov     rcx, [rsp+178h+String]; String
0x1800eff48  test    rcx, rcx
0x1800eff4b  jz      short loc_1800EFF62
0x1800eff4d  call    cs:__imp__wtoi
0x1800eff53  mov     [rsp+178h+var_48], eax
0x1800eff5a  mov     [rsp+178h+var_44], 1
0x1800eff62  lea     rdx, [rsp+178h+instance]
0x1800eff6a  mov     rcx, r12; self
0x1800eff6d  call    MI_Instance_Destruct
0x1800eff72  lea     rcx, [rsp+178h+instance]; self
0x1800eff7a  call    MI_Instance_Destruct
0x1800eff7f  mov     [rsp+178h+var_138], dil
0x1800eff84  inc     r15d
0x1800eff87  jmp     loc_1800EFD6F
0x1800eff8c  mov     rcx, [rbx]
0x1800eff8f  test    rcx, rcx
0x1800eff92  jz      short loc_1800EFFA7
0x1800eff94  mov     rax, [rcx]
0x1800eff97  mov     edx, 1
0x1800eff9c  mov     rax, [rax]
0x1800eff9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800effa4  mov     [rbx], rdi
0x1800effa7  jmp     short loc_1800EFFC3
0x1800effa9  xor     edi, edi
0x1800effab  cmp     [rsp+178h+var_138], dil
0x1800effb0  jz      short loc_1800EFFBF
0x1800effb2  lea     rcx, [rsp+178h+instance]; self
0x1800effba  call    MI_Instance_Destruct
0x1800effbf  mov     esi, dword ptr [rsp+178h+var_128]
0x1800effc3  mov     r8d, esi; int
0x1800effc6  lea     rdx, aEnumerateinsta_1; "EnumerateInstancesEnd"
0x1800effcd  lea     rcx, [rsp+178h+var_120]; this
0x1800effd2  call    ?WriteEnd@TelemetryEventWriter@@QEAAXPEBDH@Z; TelemetryEventWriter::WriteEnd(char const *,int)
0x1800effd7  mov     [rsp+178h+var_F0], 2
0x1800effe2  mov     eax, cs:dword_180380B68
0x1800effe8  cmp     eax, 5
0x1800effeb  jbe     short loc_1800F0026
0x1800effed  mov     rdx, 200000000000h
0x1800efff7  lea     rcx, dword_180380B68
0x1800efffe  call    _tlgKeywordOn
0x1800f0003  test    al, al
0x1800f0005  jz      short loc_1800F0026
0x1800f0007  xor     r9d, r9d
0x1800f000a  lea     r8, [rsp+178h+var_E8]
0x1800f0012  lea     rdx, unk_180338B78
0x1800f0019  lea     rcx, dword_180380B68
0x1800f0020  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800f0025  nop
0x1800f0026  lea     rcx, [rsp+178h+var_F0]
0x1800f002e  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(void)
0x1800f0033  mov     eax, esi
0x1800f0035  mov     rcx, [rsp+178h+var_38]
0x1800f003d  xor     rcx, rsp; StackCookie
0x1800f0040  call    __security_check_cookie
0x1800f0045  lea     r11, [rsp+178h+var_28]
0x1800f004d  mov     rbx, [r11+38h]
0x1800f0051  mov     rsi, [r11+40h]
0x1800f0055  mov     rsp, r11
0x1800f0058  pop     r15
0x1800f005a  pop     r14
0x1800f005c  pop     r13
0x1800f005e  pop     r12
0x1800f0060  pop     rdi
0x1800f0061  retn
```
