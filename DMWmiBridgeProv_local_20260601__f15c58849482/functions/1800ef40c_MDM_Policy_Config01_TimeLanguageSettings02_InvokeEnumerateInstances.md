# MDM_Policy_Config01_TimeLanguageSettings02_InvokeEnumerateInstances

- ea: `0x1800ef40c`
- end: `0x1800ef8fd`
- name: `MDM_Policy_Config01_TimeLanguageSettings02_InvokeEnumerateInstances`
- size: `1265`
- prototype: `__int64 __fastcall(MI_Instance *self)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800eeca0`

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
- `0x1800ef40c`
- `0x18023f3ac`
- `0x180245824`
- `0x1802458ac`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024f010`

## import_xrefs

- `msvcrt!_wtoi` at `0x1800ef71a`
- `msvcrt!_wtoi` at `0x1800ef79a`
- `msvcrt!_wtoi` at `0x1800ef7e1`
- `msvcrt!_wtoi` at `0x1800ef71a`
- `msvcrt!_wtoi` at `0x1800ef79a`
- `msvcrt!_wtoi` at `0x1800ef7e1`

## string_xrefs

- `0x1800ef6f6`: `BlockCleanupOfUnusedPreinstalledLangPacks`
- `0x1800ef73d`: `ConfigureTimeZone`
- `0x1800ef776`: `MachineUILanguageOverwrite`
- `0x1800ef7bd`: `RestrictLanguagePacksAndFeaturesInstall`
- `0x1800ef65c`: `./Vendor/MSFT/Policy/Config`
- `0x1800ef487`: `MDM_Policy_Config01_TimeLanguageSettings02`

## pseudocode

```c
__int64 __fastcall MDM_Policy_Config01_TimeLanguageSettings02_InvokeEnumerateInstances(MI_Context *self, char a2)
{
  const char *v4; // rdx
  _DWORD *v5; // r9
  MI_Result v6; // esi
  _QWORD *v7; // r14
  unsigned int i; // r15d
  wchar_t *String; // [rsp+48h] [rbp-130h] BYREF
  _QWORD *v11; // [rsp+50h] [rbp-128h] BYREF
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
  v6 = (unsigned int)CreateRequestHandlerInstance(
                       self,
                       0,
                       0,
                       &MDM_Policy_Config01_TimeLanguageSettings02_NodeList,
                       6,
                       2,
                       &v11);
  if ( v6 == MI_RESULT_OK )
  {
    v12[4] = &v11;
    v13 = 1;
    v7 = v11;
    if ( v11 )
    {
      v6 = (*(unsigned int (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
      if ( v6 )
      {
        if ( v11 )
          (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
      }
      else
      {
        v6 = (*(unsigned int (__fastcall **)(_QWORD *))(*v7 + 8LL))(v7);
        if ( v6 )
        {
          if ( v11 )
            (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
        }
        else
        {
          for ( i = 0; i < (unsigned int)((__int64)(v7[33] - v7[32]) >> 4); ++i )
          {
            v6 = MI_Context_ConstructInstance(self, &MDM_Policy_Config01_TimeLanguageSettings02_rtti, &instance);
            if ( v6 )
            {
              if ( v11 )
              {
                (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
                v11 = 0;
              }
              goto LABEL_50;
            }
            if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v7 + 24LL))(
                    v7,
                    i,
                    L"./Vendor/MSFT/Policy/Config",
                    &String)
              && String )
            {
              MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID(&instance, String);
            }
            if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const wchar_t *, wchar_t **))(*v7 + 24LL))(
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
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"BlockCleanupOfUnusedPreinstalledLangPacks",
                      &String)
                && String )
              {
                v19 = _wtoi(String);
                v20 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"ConfigureTimeZone",
                      &String)
                && String )
              {
                MDM_WindowsLicensing_Subscriptions01_01_Set_Name(&instance);
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
                      v7,
                      i,
                      L"MachineUILanguageOverwrite",
                      &String)
                && String )
              {
                v21 = _wtoi(String);
                v22 = 1;
              }
              if ( !(*(unsigned int (__fastcall **)(_QWORD *, _QWORD, const unsigned __int16 *, wchar_t **))(*v7 + 24LL))(
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
            (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
            v11 = 0;
          }
        }
      }
    }
    else
    {
      v6 = MI_RESULT_FAILED;
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
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800ef40c  mov     [rsp+arg_8], rbx
0x1800ef411  mov     [rsp+arg_10], rsi
0x1800ef416  push    rdi
0x1800ef417  push    r12
0x1800ef419  push    r13
0x1800ef41b  push    r14
0x1800ef41d  push    r15
0x1800ef41f  sub     rsp, 150h
0x1800ef426  mov     rax, cs:__security_cookie
0x1800ef42d  xor     rax, rsp
0x1800ef430  mov     [rsp+178h+var_38], rax
0x1800ef438  mov     r13b, dl
0x1800ef43b  mov     r12, rcx
0x1800ef43e  xor     edx, edx; Val
0x1800ef440  mov     r8d, 88h; Size
0x1800ef446  lea     rcx, [rsp+178h+instance]; void *
0x1800ef44e  call    memset_0
0x1800ef453  xor     edi, edi
0x1800ef455  mov     [rsp+178h+var_138], dil
0x1800ef45a  mov     [rsp+178h+String], rdi
0x1800ef45f  mov     [rsp+178h+var_F0], edi
0x1800ef466  mov     [rsp+178h+var_EC], dil
0x1800ef46e  lea     rax, ??_7TelemetryEventWriter@@6B@; const TelemetryEventWriter::`vftable'
0x1800ef475  mov     [rsp+178h+var_120], rax
0x1800ef47a  lea     rax, [rsp+178h+var_F0]
0x1800ef482  mov     [rsp+178h+var_118], rax
0x1800ef487  lea     rax, aMdmPolicyConfi_135; "MDM_Policy_Config01_TimeLanguageSetting"...
0x1800ef48e  mov     [rsp+178h+var_110], rax
0x1800ef493  lea     rcx, [rsp+178h+var_F0]
0x1800ef49b  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::zInternalStart(void)
0x1800ef4a0  mov     eax, cs:dword_180380B68
0x1800ef4a6  cmp     eax, 5
0x1800ef4a9  jbe     short loc_1800EF51B
0x1800ef4ab  mov     rdx, 200000000000h
0x1800ef4b5  lea     rcx, dword_180380B68
0x1800ef4bc  call    _tlgKeywordOn
0x1800ef4c1  test    al, al
0x1800ef4c3  jz      short loc_1800EF51B
0x1800ef4c5  cmp     [rsp+178h+var_EC], dil
0x1800ef4cd  jz      short loc_1800EF4FD
0x1800ef4cf  cmp     [rsp+178h+var_D8], edi
0x1800ef4d6  jnz     short loc_1800EF4F3
0x1800ef4d8  cmp     [rsp+178h+var_D4], edi
0x1800ef4df  jnz     short loc_1800EF4F3
0x1800ef4e1  cmp     [rsp+178h+var_D0], edi
0x1800ef4e8  jnz     short loc_1800EF4F3
0x1800ef4ea  cmp     [rsp+178h+var_CC], edi
0x1800ef4f1  jz      short loc_1800EF4FD
0x1800ef4f3  lea     r9, [rsp+178h+var_D8]
0x1800ef4fb  jmp     short loc_1800EF500
0x1800ef4fd  mov     r9, rdi
0x1800ef500  lea     r8, [rsp+178h+var_E8]
0x1800ef508  lea     rdx, dword_18035933C
0x1800ef50f  lea     rcx, dword_180380B68
0x1800ef516  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800ef51b  lea     rcx, [rsp+178h+var_120]; this
0x1800ef520  call    ?WriteStart@TelemetryEventWriter@@QEAAXPEBD@Z; TelemetryEventWriter::WriteStart(char const *)
0x1800ef525  nop
0x1800ef526  mov     [rsp+178h+var_128], rdi
0x1800ef52b  lea     rax, [rsp+178h+var_128]
0x1800ef530  mov     [rsp+178h+var_148], rax
0x1800ef535  mov     [rsp+178h+var_150], 2
0x1800ef53d  mov     [rsp+178h+var_158], 6
0x1800ef545  lea     r9, ?MDM_Policy_Config01_TimeLanguageSettings02_NodeList@@3PAUWmiNodeInfo@@A; WmiNodeInfo near * MDM_Policy_Config01_TimeLanguageSettings02_NodeList
0x1800ef54c  xor     r8d, r8d
0x1800ef54f  xor     edx, edx
0x1800ef551  mov     rcx, r12
0x1800ef554  call    ?CreateRequestHandlerInstance@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBG1PEAUWmiNodeInfo@@KW4RequestType@@AEAPEAVWmiRequestHandler@@@Z; CreateRequestHandlerInstance(_MI_Context *,ushort const *,ushort const *,WmiNodeInfo *,ulong,RequestType,WmiRequestHandler * &)
0x1800ef559  mov     esi, eax
0x1800ef55b  test    eax, eax
0x1800ef55d  jz      short loc_1800EF564
0x1800ef55f  jmp     loc_1800EF85D
0x1800ef564  lea     rbx, [rsp+178h+var_128]
0x1800ef569  mov     [rsp+178h+var_100], rbx
0x1800ef56e  mov     r15d, 1
0x1800ef574  mov     [rsp+178h+var_F8], r15b
0x1800ef57c  mov     r14, [rsp+178h+var_128]
0x1800ef581  test    r14, r14
0x1800ef584  jnz     short loc_1800EF58E
0x1800ef586  mov     esi, r15d
0x1800ef589  jmp     loc_1800EF85D
0x1800ef58e  mov     rax, [r14]
0x1800ef591  mov     rcx, r14
0x1800ef594  mov     rax, [rax+10h]
0x1800ef598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef59d  mov     esi, eax
0x1800ef59f  test    eax, eax
0x1800ef5a1  jz      short loc_1800EF5C1
0x1800ef5a3  mov     rcx, [rsp+178h+var_128]
0x1800ef5a8  test    rcx, rcx
0x1800ef5ab  jz      short loc_1800EF5BC
0x1800ef5ad  mov     rax, [rcx]
0x1800ef5b0  mov     edx, r15d
0x1800ef5b3  mov     rax, [rax]
0x1800ef5b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef5bb  nop
0x1800ef5bc  jmp     loc_1800EF85D
0x1800ef5c1  mov     rax, [r14]
0x1800ef5c4  mov     rcx, r14
0x1800ef5c7  mov     rax, [rax+8]
0x1800ef5cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef5d0  mov     esi, eax
0x1800ef5d2  test    eax, eax
0x1800ef5d4  jz      short loc_1800EF5F4
0x1800ef5d6  mov     rcx, [rsp+178h+var_128]
0x1800ef5db  test    rcx, rcx
0x1800ef5de  jz      short loc_1800EF5EF
0x1800ef5e0  mov     rax, [rcx]
0x1800ef5e3  mov     edx, r15d
0x1800ef5e6  mov     rax, [rax]
0x1800ef5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef5ee  nop
0x1800ef5ef  jmp     loc_1800EF85D
0x1800ef5f4  mov     r15d, edi
0x1800ef5f7  mov     rax, [r14+108h]
0x1800ef5fe  sub     rax, [r14+100h]
0x1800ef605  sar     rax, 4
0x1800ef609  cmp     r15d, eax
0x1800ef60c  jnb     loc_1800EF826
0x1800ef612  lea     r8, [rsp+178h+instance]; instance
0x1800ef61a  lea     rdx, MDM_Policy_Config01_TimeLanguageSettings02_rtti; classDecl
0x1800ef621  mov     rcx, r12; context
0x1800ef624  call    MI_Context_ConstructInstance
0x1800ef629  mov     esi, eax
0x1800ef62b  test    eax, eax
0x1800ef62d  jz      short loc_1800EF64F
0x1800ef62f  mov     rcx, [rbx]
0x1800ef632  test    rcx, rcx
0x1800ef635  jz      short loc_1800EF64A
0x1800ef637  mov     rax, [rcx]
0x1800ef63a  mov     edx, 1
0x1800ef63f  mov     rax, [rax]
0x1800ef642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef647  mov     [rbx], rdi
0x1800ef64a  jmp     loc_1800EF85D
0x1800ef64f  mov     [rsp+178h+var_138], 1
0x1800ef654  mov     rax, [r14]
0x1800ef657  lea     r9, [rsp+178h+String]
0x1800ef65c  lea     r8, aVendorMsftPoli_23; "./Vendor/MSFT/Policy/Config"
0x1800ef663  mov     edx, r15d
0x1800ef666  mov     rcx, r14
0x1800ef669  mov     rax, [rax+18h]
0x1800ef66d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef672  test    eax, eax
0x1800ef674  jnz     short loc_1800EF68D
0x1800ef676  mov     rdx, [rsp+178h+String]
0x1800ef67b  test    rdx, rdx
0x1800ef67e  jz      short loc_1800EF68D
0x1800ef680  lea     rcx, [rsp+178h+instance]
0x1800ef688  call    MDM_WindowsLicensing_Subscriptions01_01_Set_ParentID
0x1800ef68d  mov     rax, [r14]
0x1800ef690  lea     r9, [rsp+178h+String]
0x1800ef695  lea     r8, aTimelanguagese; "TimeLanguageSettings"
0x1800ef69c  mov     edx, r15d
0x1800ef69f  mov     rcx, r14
0x1800ef6a2  mov     rax, [rax+18h]
0x1800ef6a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef6ab  test    eax, eax
0x1800ef6ad  jnz     short loc_1800EF6C6
0x1800ef6af  mov     rdx, [rsp+178h+String]
0x1800ef6b4  test    rdx, rdx
0x1800ef6b7  jz      short loc_1800EF6C6
0x1800ef6b9  lea     rcx, [rsp+178h+instance]
0x1800ef6c1  call    MDM_WindowsLicensing_Subscriptions01_01_Set_InstanceID
0x1800ef6c6  cmp     r13b, 1
0x1800ef6ca  jnz     short loc_1800EF6EE
0x1800ef6cc  lea     rdx, [rsp+178h+instance]
0x1800ef6d4  mov     rcx, r12; self
0x1800ef6d7  call    MI_Instance_Destruct
0x1800ef6dc  lea     rcx, [rsp+178h+instance]; self
0x1800ef6e4  call    MI_Instance_Destruct
0x1800ef6e9  jmp     loc_1800EF819
0x1800ef6ee  mov     rax, [r14]
0x1800ef6f1  lea     r9, [rsp+178h+String]
0x1800ef6f6  lea     r8, aBlockcleanupof; "BlockCleanupOfUnusedPreinstalledLangPac"...
0x1800ef6fd  mov     edx, r15d
0x1800ef700  mov     rcx, r14
0x1800ef703  mov     rax, [rax+18h]
0x1800ef707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef70c  test    eax, eax
0x1800ef70e  jnz     short loc_1800EF735
0x1800ef710  mov     rcx, [rsp+178h+String]; String
0x1800ef715  test    rcx, rcx
0x1800ef718  jz      short loc_1800EF735
0x1800ef71a  call    cs:__imp__wtoi
0x1800ef721  nop     dword ptr [rax+rax+00h]
0x1800ef726  mov     [rsp+178h+var_68], eax
0x1800ef72d  mov     [rsp+178h+var_64], 1
0x1800ef735  mov     rax, [r14]
0x1800ef738  lea     r9, [rsp+178h+String]
0x1800ef73d  lea     r8, aConfiguretimez; "ConfigureTimeZone"
0x1800ef744  mov     edx, r15d
0x1800ef747  mov     rcx, r14
0x1800ef74a  mov     rax, [rax+18h]
0x1800ef74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef753  test    eax, eax
0x1800ef755  jnz     short loc_1800EF76E
0x1800ef757  mov     rdx, [rsp+178h+String]
0x1800ef75c  test    rdx, rdx
0x1800ef75f  jz      short loc_1800EF76E
0x1800ef761  lea     rcx, [rsp+178h+instance]
0x1800ef769  call    MDM_WindowsLicensing_Subscriptions01_01_Set_Name
0x1800ef76e  mov     rax, [r14]
0x1800ef771  lea     r9, [rsp+178h+String]
0x1800ef776  lea     r8, aMachineuilangu; "MachineUILanguageOverwrite"
0x1800ef77d  mov     edx, r15d
0x1800ef780  mov     rcx, r14
0x1800ef783  mov     rax, [rax+18h]
0x1800ef787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef78c  test    eax, eax
0x1800ef78e  jnz     short loc_1800EF7B5
0x1800ef790  mov     rcx, [rsp+178h+String]; String
0x1800ef795  test    rcx, rcx
0x1800ef798  jz      short loc_1800EF7B5
0x1800ef79a  call    cs:__imp__wtoi
0x1800ef7a1  nop     dword ptr [rax+rax+00h]
0x1800ef7a6  mov     [rsp+178h+var_50], eax
0x1800ef7ad  mov     [rsp+178h+var_4C], 1
0x1800ef7b5  mov     rax, [r14]
0x1800ef7b8  lea     r9, [rsp+178h+String]
0x1800ef7bd  lea     r8, aRestrictlangua; "RestrictLanguagePacksAndFeaturesInstall"
0x1800ef7c4  mov     edx, r15d
0x1800ef7c7  mov     rcx, r14
0x1800ef7ca  mov     rax, [rax+18h]
0x1800ef7ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef7d3  test    eax, eax
0x1800ef7d5  jnz     short loc_1800EF7FC
0x1800ef7d7  mov     rcx, [rsp+178h+String]; String
0x1800ef7dc  test    rcx, rcx
0x1800ef7df  jz      short loc_1800EF7FC
0x1800ef7e1  call    cs:__imp__wtoi
0x1800ef7e8  nop     dword ptr [rax+rax+00h]
0x1800ef7ed  mov     [rsp+178h+var_48], eax
0x1800ef7f4  mov     [rsp+178h+var_44], 1
0x1800ef7fc  lea     rdx, [rsp+178h+instance]
0x1800ef804  mov     rcx, r12; self
0x1800ef807  call    MI_Instance_Destruct
0x1800ef80c  lea     rcx, [rsp+178h+instance]; self
0x1800ef814  call    MI_Instance_Destruct
0x1800ef819  mov     [rsp+178h+var_138], dil
0x1800ef81e  inc     r15d
0x1800ef821  jmp     loc_1800EF5F7
0x1800ef826  mov     rcx, [rbx]
0x1800ef829  test    rcx, rcx
0x1800ef82c  jz      short loc_1800EF841
0x1800ef82e  mov     rax, [rcx]
0x1800ef831  mov     edx, 1
0x1800ef836  mov     rax, [rax]
0x1800ef839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef83e  mov     [rbx], rdi
0x1800ef841  jmp     short loc_1800EF85D
0x1800ef843  xor     edi, edi
0x1800ef845  cmp     [rsp+178h+var_138], dil
0x1800ef84a  jz      short loc_1800EF859
0x1800ef84c  lea     rcx, [rsp+178h+instance]; self
0x1800ef854  call    MI_Instance_Destruct
0x1800ef859  mov     esi, dword ptr [rsp+178h+var_128]
0x1800ef85d  mov     r8d, esi; int
0x1800ef860  lea     rdx, aEnumerateinsta_1; "EnumerateInstancesEnd"
0x1800ef867  lea     rcx, [rsp+178h+var_120]; this
0x1800ef86c  call    ?WriteEnd@TelemetryEventWriter@@QEAAXPEBDH@Z; TelemetryEventWriter::WriteEnd(char const *,int)
0x1800ef871  mov     [rsp+178h+var_F0], 2
0x1800ef87c  mov     eax, cs:dword_180380B68
0x1800ef882  cmp     eax, 5
0x1800ef885  jbe     short loc_1800EF8C0
0x1800ef887  mov     rdx, 200000000000h
0x1800ef891  lea     rcx, dword_180380B68
0x1800ef898  call    _tlgKeywordOn
0x1800ef89d  test    al, al
0x1800ef89f  jz      short loc_1800EF8C0
0x1800ef8a1  xor     r9d, r9d
0x1800ef8a4  lea     r8, [rsp+178h+var_E8]
0x1800ef8ac  lea     rdx, unk_180338B78
0x1800ef8b3  lea     rcx, dword_180380B68
0x1800ef8ba  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800ef8bf  nop
0x1800ef8c0  lea     rcx, [rsp+178h+var_F0]
0x1800ef8c8  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hTraceLoggingProvider@@3QEBU_tlgProvider_t@@EB$0CAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hTraceLoggingProvider,35184372088832,5,_TlgReflectorTag_Param0IsHProvider>,35184372088832,5>(void)
0x1800ef8cd  mov     eax, esi
0x1800ef8cf  mov     rcx, [rsp+178h+var_38]
0x1800ef8d7  xor     rcx, rsp; StackCookie
0x1800ef8da  call    __security_check_cookie
0x1800ef8df  lea     r11, [rsp+178h+var_28]
0x1800ef8e7  mov     rbx, [r11+38h]
0x1800ef8eb  mov     rsi, [r11+40h]
0x1800ef8ef  mov     rsp, r11
0x1800ef8f2  pop     r15
0x1800ef8f4  pop     r14
0x1800ef8f6  pop     r13
0x1800ef8f8  pop     r12
0x1800ef8fa  pop     rdi
0x1800ef8fb  retn
```
