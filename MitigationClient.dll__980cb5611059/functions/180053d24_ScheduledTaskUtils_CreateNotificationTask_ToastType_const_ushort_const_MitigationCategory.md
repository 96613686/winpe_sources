# ScheduledTaskUtils::CreateNotificationTask(ToastType const &,ushort const *,MitigationCategory)

- ea: `0x180053d24`
- end: `0x18005434c`
- name: `?CreateNotificationTask@ScheduledTaskUtils@@SAJAEBW4ToastType@@PEBGW4MitigationCategory@@@Z`
- size: `1576`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180035818`

## callees

- `0x18000abc4`
- `0x18001055c`
- `0x18001208c`
- `0x18002a488`
- `0x18002a588`
- `0x180053c18`
- `0x180053d00`
- `0x180053d24`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180053d9f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180053d9f`
- `OLEAUT32!__imp_SysFreeString` at `0x180053f23`
- `OLEAUT32!__imp_SysFreeString` at `0x180054045`
- `OLEAUT32!__imp_SysFreeString` at `0x1800541a9`
- `OLEAUT32!__imp_SysFreeString` at `0x180053f23`
- `OLEAUT32!__imp_SysFreeString` at `0x180054045`
- `OLEAUT32!__imp_SysFreeString` at `0x1800541a9`
- `OLEAUT32!__imp_VariantInit` at `0x180053dc7`
- `OLEAUT32!__imp_VariantInit` at `0x180053ddd`
- `OLEAUT32!__imp_VariantInit` at `0x180053df4`
- `OLEAUT32!__imp_VariantInit` at `0x180053e09`
- `OLEAUT32!__imp_VariantInit` at `0x1800540bf`
- `OLEAUT32!__imp_VariantInit` at `0x1800540d4`
- `OLEAUT32!__imp_VariantInit` at `0x1800540ea`
- `OLEAUT32!__imp_VariantInit` at `0x180053dc7`
- `OLEAUT32!__imp_VariantInit` at `0x180053ddd`
- `OLEAUT32!__imp_VariantInit` at `0x180053df4`
- `OLEAUT32!__imp_VariantInit` at `0x180053e09`
- `OLEAUT32!__imp_VariantInit` at `0x1800540bf`
- `OLEAUT32!__imp_VariantInit` at `0x1800540d4`
- `OLEAUT32!__imp_VariantInit` at `0x1800540ea`

## string_xrefs

- `0x180053e97`: `onecore\base\diagnosis\mitigation\client\libs\utils\scheduledtaskutils.cpp`
- `0x180053f59`: `onecore\base\diagnosis\mitigation\client\libs\utils\scheduledtaskutils.cpp`
- `0x180053fb9`: `onecore\base\diagnosis\mitigation\client\libs\utils\scheduledtaskutils.cpp`
- `0x18005407b`: `onecore\base\diagnosis\mitigation\client\libs\utils\scheduledtaskutils.cpp`
- `0x180054202`: `onecore\base\diagnosis\mitigation\client\libs\utils\scheduledtaskutils.cpp`
- `0x180054266`: `onecore\base\diagnosis\mitigation\client\libs\utils\scheduledtaskutils.cpp`
- `0x180053ff4`: `<Task version="1.4" xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task">              <RegistrationInfo>                <Source>Recommended Troubleshooting Service</Source>                <Author>Microsoft Corporation</Author>                <Description>Notify availability of recommended troubleshooters from Microsoft</Description>                <URI>\Microsoft\Windows\Diagnosis\RecommendedTroubleshootingNotifier</URI>              </RegistrationInfo>              <Triggers>         `
- `0x180054101`: `RecommendedTroubleshootingNotifier`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall ScheduledTaskUtils::CreateNotificationTask(unsigned int *a1, __int64 a2, unsigned int a3)
{
  HRESULT v6; // eax
  int v7; // ebx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, VARIANTARG *, __int128 *, int *); // rbx
  __int128 v12; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v14; // xmm8
  IRecordInfo *v15; // xmm9_8
  __int128 v16; // xmm6
  IRecordInfo *v17; // xmm7_8
  LPVOID v18; // rbx
  __int64 (__fastcall *v19)(LPVOID, __int64, __int64 *); // rdi
  _bstr_t *v20; // rax
  __int64 v21; // rdx
  unsigned __int64 v22; // rdx
  int v23; // edi
  __int64 v24; // rbx
  void *v25; // rcx
  LPVOID v26; // rdi
  __int64 (__fastcall *v27)(LPVOID, _QWORD, __int64 *); // rbx
  int v28; // eax
  __int64 v29; // rbx
  __int64 (__fastcall *v30)(__int64, __int64); // rdi
  _bstr_t *v31; // rax
  __int64 v32; // rdx
  unsigned __int64 v33; // rdx
  __int64 v34; // rbx
  void *v35; // rcx
  __int64 v36; // rbx
  __int64 (__fastcall *v37)(__int64, __int64, __int64, __int64); // rsi
  __int128 v38; // xmm6
  IRecordInfo *v39; // xmm7_8
  __int128 v40; // xmm8
  IRecordInfo *v41; // xmm9_8
  __int128 v42; // xmm10
  IRecordInfo *v43; // xmm11_8
  __int64 v44; // rdi
  _bstr_t *v45; // rax
  __int64 v46; // rdx
  unsigned __int64 v47; // rdx
  __int64 v48; // rbx
  void *v49; // rcx
  int v50; // eax
  __int64 v51; // rdx
  int *ppv; // [rsp+28h] [rbp-E0h]
  int ppva; // [rsp+28h] [rbp-E0h]
  __int64 v55; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v56; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v57; // [rsp+68h] [rbp-A0h] BYREF
  LPVOID v58; // [rsp+70h] [rbp-98h] BYREF
  VARIANTARG v59; // [rsp+78h] [rbp-90h] BYREF
  IRecordInfo *v60; // [rsp+90h] [rbp-78h]
  VARIANTARG v61; // [rsp+98h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-58h] BYREF
  int v63[4]; // [rsp+C8h] [rbp-40h] BYREF
  IRecordInfo *v64; // [rsp+D8h] [rbp-30h]
  __int128 v65; // [rsp+E8h] [rbp-20h] BYREF
  IRecordInfo *v66; // [rsp+F8h] [rbp-10h]
  VARIANTARG v67; // [rsp+108h] [rbp+0h] BYREF
  VARIANTARG v68; // [rsp+128h] [rbp+20h] BYREF
  int v69[4]; // [rsp+148h] [rbp+40h] BYREF
  IRecordInfo *v70; // [rsp+158h] [rbp+50h]
  wil::details::in1diag3 *retaddr; // [rsp+210h] [rbp+108h]
  __int64 v72; // [rsp+230h] [rbp+128h] BYREF

  v58 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
  v6 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &v58);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v10 = v58;
    v11 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, int *))(*(_QWORD *)v58 + 80LL);
    VariantInit(&pvarg);
    v12 = *(_OWORD *)&pvarg.vt;
    pRecInfo = pvarg.pRecInfo;
    VariantInit(&v61);
    v14 = *(_OWORD *)&v61.vt;
    v15 = v61.pRecInfo;
    VariantInit((VARIANTARG *)&v59.decVal.8);
    v16 = *(_OWORD *)&v59.decVal.Lo32;
    v17 = v60;
    VariantInit(&v68);
    *(_OWORD *)v69 = v12;
    v70 = pRecInfo;
    *(_OWORD *)v63 = v14;
    v64 = v15;
    v65 = v16;
    v66 = v17;
    v67 = v68;
    ppv = v69;
    v7 = v11(v10, &v67, &v65, v63);
    _variant_t::~_variant_t((_variant_t *)&v68);
    _variant_t::~_variant_t((_variant_t *)&v59.decVal.8);
    _variant_t::~_variant_t((_variant_t *)&v61);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    if ( v7 < 0 )
    {
      v8 = (unsigned int)v7;
      v9 = 99;
      goto LABEL_5;
    }
    v56 = 0;
    v18 = v58;
    v19 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v58 + 56LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
    v20 = _bstr_t::_bstr_t((_bstr_t *)&v59, L"\\Microsoft\\Windows\\Diagnosis");
    if ( *(_QWORD *)v20 )
      v21 = **(_QWORD **)v20;
    else
      v21 = 0;
    v23 = v19(v18, v21, &v56);
    v24 = *(_QWORD *)&v59.vt;
    if ( *(_QWORD *)&v59.vt
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v59.vt + 16LL), 0xFFFFFFFF) == 1
      && v24 )
    {
      if ( *(_QWORD *)v24 )
      {
        SysFreeString(*(BSTR *)v24);
        *(_QWORD *)v24 = 0;
      }
      v25 = *(void **)(v24 + 8);
      if ( v25 )
      {
        operator delete(v25, v22);
        *(_QWORD *)(v24 + 8) = 0;
      }
      operator delete((void *)v24, 0x18u);
    }
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\scheduledtaskutils.cpp",
        (const char *)(unsigned int)v23,
        (int)v69);
LABEL_19:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
      v7 = v23;
      goto LABEL_59;
    }
    v55 = 0;
    v26 = v58;
    v27 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v58 + 72LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
    v28 = v27(v26, 0, &v55);
    v7 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\scheduledtaskutils.cpp",
        (const char *)(unsigned int)v28,
        (int)v69);
LABEL_22:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
      goto LABEL_59;
    }
    v29 = v55;
    v30 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v55 + 160LL);
    v31 = _bstr_t::_bstr_t(
            (_bstr_t *)&v59,
            L"<Task version=\"1.4\" xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\">              <Registr"
             "ationInfo>                <Source>Recommended Troubleshooting Service</Source>                <Author>Micro"
             "soft Corporation</Author>                <Description>Notify availability of recommended troubleshooters fr"
             "om Microsoft</Description>                <URI>\\Microsoft\\Windows\\Diagnosis\\RecommendedTroubleshootingN"
             "otifier</URI>              </RegistrationInfo>              <Triggers>                <SessionStateChangeTr"
             "igger>                  <Enabled>true</Enabled>                  <StateChange>SessionUnlock</StateChange>  "
             "                <Delay>PT30S</Delay>                </SessionStateChangeTrigger>                <WnfStateCh"
             "angeTrigger>                  <StateName>75d0bda33e06830d</StateName>                  <Data>0</Data>      "
             "            <Delay>PT30S</Delay>                </WnfStateChangeTrigger>              </Triggers>          "
             "    <Principals>                <Principal id=\"LocalSystem\">                  <UserId>S-1-5-18</UserId>  "
             "                <RunLevel>HighestAvailable</RunLevel>                </Principal>              </Principals"
             ">              <Settings>                <MultipleInstancesPolicy>IgnoreNew</MultipleInstancesPolicy>      "
             "          <DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries>                <StopIfGoingOnBatte"
             "ries>false</StopIfGoingOnBatteries>                <AllowHardTerminate>true</AllowHardTerminate>           "
             "     <StartWhenAvailable>false</StartWhenAvailable>                <RunOnlyIfNetworkAvailable>false</RunOnl"
             "yIfNetworkAvailable>                <IdleSettings>                  <StopOnIdleEnd>false</StopOnIdleEnd>   "
             "               <RestartOnIdle>false</RestartOnIdle>                </IdleSettings>                <AllowSta"
             "rtOnDemand>true</AllowStartOnDemand>                <Enabled>true</Enabled>                <Hidden>false</H"
             "idden>                <RunOnlyIfIdle>false</RunOnlyIfIdle>                <WakeToRun>false</WakeToRun>     "
             "           <ExecutionTimeLimit>PT1H</ExecutionTimeLimit>                <Priority>7</Priority>             "
             " </Settings>              <Actions Context=\"LocalSystem\">                <ComHandler>                    "
             "<ClassId>{A1B4DD9F-C1D9-4E24-9B7F-C0EF7CFFDB71}</ClassId>                </ComHandler>              </Actio"
             "ns>          </Task>");
    if ( *(_QWORD *)v31 )
      v32 = **(_QWORD **)v31;
    else
      v32 = 0;
    v23 = v30(v29, v32);
    v34 = *(_QWORD *)&v59.vt;
    if ( *(_QWORD *)&v59.vt
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v59.vt + 16LL), 0xFFFFFFFF) == 1
      && v34 )
    {
      if ( *(_QWORD *)v34 )
      {
        SysFreeString(*(BSTR *)v34);
        *(_QWORD *)v34 = 0;
      }
      v35 = *(void **)(v34 + 8);
      if ( v35 )
      {
        operator delete(v35, v33);
        *(_QWORD *)(v34 + 8) = 0;
      }
      operator delete((void *)v34, 0x18u);
    }
    if ( v23 >= 0 )
    {
      v57 = 0;
      v36 = v56;
      v37 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v56 + 136LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
      VariantInit((VARIANTARG *)&v59.decVal.8);
      v38 = *(_OWORD *)&v59.decVal.Lo32;
      v39 = v60;
      VariantInit(&v61);
      v40 = *(_OWORD *)&v61.vt;
      v41 = v61.pRecInfo;
      VariantInit(&pvarg);
      v42 = *(_OWORD *)&pvarg.vt;
      v43 = pvarg.pRecInfo;
      v44 = v55;
      v45 = _bstr_t::_bstr_t((_bstr_t *)&v59, L"RecommendedTroubleshootingNotifier");
      if ( *(_QWORD *)v45 )
        v46 = **(_QWORD **)v45;
      else
        v46 = 0;
      *(_OWORD *)&v67.vt = v38;
      v67.pRecInfo = v39;
      v65 = v40;
      v66 = v41;
      *(_OWORD *)v63 = v42;
      v64 = v43;
      v23 = v37(v36, v46, v44, 6);
      v48 = *(_QWORD *)&v59.vt;
      if ( *(_QWORD *)&v59.vt )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v59.vt + 16LL), 0xFFFFFFFF) == 1 && v48 )
        {
          if ( *(_QWORD *)v48 )
          {
            SysFreeString(*(BSTR *)v48);
            *(_QWORD *)v48 = 0;
          }
          v49 = *(void **)(v48 + 8);
          if ( v49 )
          {
            operator delete(v49, v47);
            *(_QWORD *)(v48 + 8) = 0;
          }
          operator delete((void *)v48, 0x18u);
        }
        *(_QWORD *)&v59.vt = 0;
      }
      _variant_t::~_variant_t((_variant_t *)&pvarg);
      _variant_t::~_variant_t((_variant_t *)&v61);
      _variant_t::~_variant_t((_variant_t *)&v59.decVal.8);
      if ( v23 >= 0 )
      {
        v72 = -2147483646;
        v50 = MitigationRegUtils::SetMitigationRegString(&v72, 1, L"ToastNotificationInfo", a2, 0);
        v7 = v50;
        if ( v50 >= 0 )
        {
          v72 = -2147483646;
          ppva = 0;
          v50 = MitigationRegUtils::SetMitigationRegDWORD(&v72, 1, L"ToastNotificationType", *a1);
          v7 = v50;
          if ( v50 >= 0 )
          {
            v72 = -2147483646;
            ppva = 0;
            v50 = MitigationRegUtils::SetMitigationRegDWORD(&v72, 1, L"ToastNotificationCategory", a3);
            v7 = v50;
            if ( v50 >= 0 )
            {
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v56);
              v7 = 0;
              goto LABEL_59;
            }
            v51 = 126;
          }
          else
          {
            v51 = 123;
          }
        }
        else
        {
          v51 = 120;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v51,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\scheduledtaskutils.cpp",
          (const char *)(unsigned int)v50,
          ppva);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
        goto LABEL_22;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x76,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\scheduledtaskutils.cpp",
        (const char *)(unsigned int)v23,
        (int)v63);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v57);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\scheduledtaskutils.cpp",
        (const char *)(unsigned int)v23,
        (int)v69);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v55);
    goto LABEL_19;
  }
  v8 = (unsigned int)v6;
  v9 = 98;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\scheduledtaskutils.cpp",
    (const char *)v8,
    (int)ppv);
LABEL_59:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v58);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180053d24  mov     rax, rsp
0x180053d27  push    rbp
0x180053d28  push    rbx
0x180053d29  push    rsi
0x180053d2a  push    rdi
0x180053d2b  push    r12
0x180053d2d  push    r13
0x180053d2f  push    r14
0x180053d31  push    r15
0x180053d33  lea     rbp, [rax-108h]
0x180053d3a  sub     rsp, 1C8h
0x180053d41  movaps  xmmword ptr [rax-58h], xmm6
0x180053d45  movaps  xmmword ptr [rax-68h], xmm7
0x180053d49  movaps  xmmword ptr [rax-78h], xmm8
0x180053d4e  movaps  xmmword ptr [rax-88h], xmm9
0x180053d56  movaps  xmmword ptr [rax-98h], xmm10
0x180053d5e  movaps  xmmword ptr [rax-0A8h], xmm11
0x180053d66  mov     r12d, r8d
0x180053d69  mov     r14, rdx
0x180053d6c  mov     r15, rcx
0x180053d6f  xor     r13d, r13d
0x180053d72  mov     [rsp+200h+var_198], r13
0x180053d77  lea     rcx, [rsp+200h+var_198]
0x180053d7c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053d81  lea     rax, [rsp+200h+var_198]
0x180053d86  mov     [rsp+200h+ppv], rax; ppv
0x180053d8b  lea     r9, IID_ITaskService; riid
0x180053d92  xor     edx, edx; pUnkOuter
0x180053d94  lea     r8d, [r13+1]; dwClsContext
0x180053d98  lea     rcx, CLSID_TaskScheduler; rclsid
0x180053d9f  call    cs:__imp_CoCreateInstance
0x180053da5  mov     ebx, eax
0x180053da7  test    eax, eax
0x180053da9  jns     short loc_180053DB7
0x180053dab  mov     r9d, eax
0x180053dae  lea     edx, [r13+62h]
0x180053db2  jmp     loc_180053E97
0x180053db7  mov     rdi, [rsp+200h+var_198]
0x180053dbc  mov     rax, [rdi]
0x180053dbf  mov     rbx, [rax+50h]
0x180053dc3  lea     rcx, [rbp+100h+pvarg]; pvarg
0x180053dc7  call    cs:__imp_VariantInit
0x180053dcd  nop
0x180053dce  movups  xmm10, xmmword ptr [rbp+100h+pvarg]
0x180053dd3  movsd   xmm11, qword ptr [rbp+100h+pvarg+10h]
0x180053dd9  lea     rcx, [rbp+100h+var_170]; pvarg
0x180053ddd  call    cs:__imp_VariantInit
0x180053de3  nop
0x180053de4  movups  xmm8, xmmword ptr [rbp+100h+var_170]
0x180053de9  movsd   xmm9, qword ptr [rbp+100h+var_170+10h]
0x180053def  lea     rcx, [rsp+200h+var_190+8]; pvarg
0x180053df4  call    cs:__imp_VariantInit
0x180053dfa  nop
0x180053dfb  movups  xmm6, xmmword ptr [rsp+200h+var_190+8]
0x180053e00  movsd   xmm7, [rbp+100h+var_178]
0x180053e05  lea     rcx, [rbp+100h+var_E0]; pvarg
0x180053e09  call    cs:__imp_VariantInit
0x180053e0f  nop
0x180053e10  movups  xmm0, xmmword ptr [rbp+100h+var_E0]
0x180053e14  movsd   xmm1, qword ptr [rbp+100h+var_E0+10h]
0x180053e19  movaps  xmmword ptr [rbp+100h+var_C0], xmm10
0x180053e1e  movsd   [rbp+100h+var_B0], xmm11
0x180053e24  movaps  xmmword ptr [rbp+100h+var_140], xmm8
0x180053e29  movsd   [rbp+100h+var_130], xmm9
0x180053e2f  movaps  [rbp+100h+var_120], xmm6
0x180053e33  movsd   [rbp+100h+var_110], xmm7
0x180053e38  movaps  [rbp+100h+var_100], xmm0
0x180053e3c  movsd   [rbp+100h+var_F0], xmm1
0x180053e41  lea     rax, [rbp+100h+var_C0]
0x180053e45  mov     [rsp+200h+ppv], rax; int
0x180053e4a  lea     r9, [rbp+100h+var_140]
0x180053e4e  lea     r8, [rbp+100h+var_120]
0x180053e52  lea     rdx, [rbp+100h+var_100]
0x180053e56  mov     rcx, rdi
0x180053e59  mov     rax, rbx
0x180053e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e61  mov     ebx, eax
0x180053e63  lea     rcx, [rbp+100h+var_E0]; this
0x180053e67  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180053e6c  nop
0x180053e6d  lea     rcx, [rsp+200h+var_190+8]; this
0x180053e72  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180053e77  nop
0x180053e78  lea     rcx, [rbp+100h+var_170]; this
0x180053e7c  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180053e81  nop
0x180053e82  lea     rcx, [rbp+100h+pvarg]; this
0x180053e86  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x180053e8b  test    ebx, ebx
0x180053e8d  jns     short loc_180053EAF
0x180053e8f  mov     r9d, ebx; char *
0x180053e92  mov     edx, 63h ; 'c'; void *
0x180053e97  lea     r8, aOnecoreBaseDia_26; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180053e9e  mov     rcx, [rbp+108h]; this
0x180053ea5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053eaa  jmp     loc_18005430A
0x180053eaf  mov     [rsp+200h+var_1A8], r13
0x180053eb4  mov     rbx, [rsp+200h+var_198]
0x180053eb9  mov     rax, [rbx]
0x180053ebc  mov     rdi, [rax+38h]
0x180053ec0  lea     rcx, [rsp+200h+var_1A8]
0x180053ec5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053eca  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Diagnosis"
0x180053ed1  lea     rcx, [rsp+200h+var_190]; this
0x180053ed6  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180053edb  nop
0x180053edc  mov     rdx, [rax]
0x180053edf  test    rdx, rdx
0x180053ee2  jz      short loc_180053EE9
0x180053ee4  mov     rdx, [rdx]
0x180053ee7  jmp     short loc_180053EEC
0x180053ee9  mov     rdx, r13
0x180053eec  lea     r8, [rsp+200h+var_1A8]
0x180053ef1  mov     rcx, rbx
0x180053ef4  mov     rax, rdi
0x180053ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053efc  mov     edi, eax
0x180053efe  or      esi, 0FFFFFFFFh
0x180053f01  mov     rbx, qword ptr [rsp+200h+var_190]
0x180053f06  test    rbx, rbx
0x180053f09  jz      short loc_180053F4B
0x180053f0b  mov     ecx, esi
0x180053f0d  lock xadd [rbx+10h], ecx
0x180053f12  add     ecx, esi
0x180053f14  jnz     short loc_180053F4B
0x180053f16  test    rbx, rbx
0x180053f19  jz      short loc_180053F4B
0x180053f1b  mov     rcx, [rbx]; bstrString
0x180053f1e  test    rcx, rcx
0x180053f21  jz      short loc_180053F2C
0x180053f23  call    cs:__imp_SysFreeString
0x180053f29  mov     [rbx], r13
0x180053f2c  mov     rcx, [rbx+8]; void *
0x180053f30  test    rcx, rcx
0x180053f33  jz      short loc_180053F3E
0x180053f35  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180053f3a  mov     [rbx+8], r13
0x180053f3e  mov     edx, 18h; unsigned __int64
0x180053f43  mov     rcx, rbx; void *
0x180053f46  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180053f4b  test    edi, edi
0x180053f4d  jns     short loc_180053F7C
0x180053f4f  mov     rcx, [rbp+108h]; this
0x180053f56  mov     r9d, edi; char *
0x180053f59  lea     r8, aOnecoreBaseDia_26; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180053f60  mov     edx, 66h ; 'f'; void *
0x180053f65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053f6a  nop
0x180053f6b  lea     rcx, [rsp+200h+var_1A8]
0x180053f70  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053f75  mov     ebx, edi
0x180053f77  jmp     loc_18005430A
0x180053f7c  mov     [rsp+200h+var_1B0], r13
0x180053f81  mov     rdi, [rsp+200h+var_198]
0x180053f86  mov     rax, [rdi]
0x180053f89  mov     rbx, [rax+48h]
0x180053f8d  lea     rcx, [rsp+200h+var_1B0]
0x180053f92  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053f97  lea     r8, [rsp+200h+var_1B0]
0x180053f9c  xor     edx, edx
0x180053f9e  mov     rcx, rdi
0x180053fa1  mov     rax, rbx
0x180053fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053fa9  mov     ebx, eax
0x180053fab  test    eax, eax
0x180053fad  jns     short loc_180053FE5
0x180053faf  mov     rcx, [rbp+108h]; this
0x180053fb6  mov     r9d, eax; char *
0x180053fb9  lea     r8, aOnecoreBaseDia_26; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180053fc0  mov     edx, 69h ; 'i'; void *
0x180053fc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053fca  nop
0x180053fcb  lea     rcx, [rsp+200h+var_1B0]
0x180053fd0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053fd5  nop
0x180053fd6  lea     rcx, [rsp+200h+var_1A8]
0x180053fdb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180053fe0  jmp     loc_18005430A
0x180053fe5  mov     rbx, [rsp+200h+var_1B0]
0x180053fea  mov     rax, [rbx]
0x180053fed  mov     rdi, [rax+0A0h]
0x180053ff4  lea     rdx, aTaskVersion14X; "<Task version=\"1.4\" xmlns=\"http://sc"...
0x180053ffb  lea     rcx, [rsp+200h+var_190]; this
0x180054000  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180054005  nop
0x180054006  mov     rdx, [rax]
0x180054009  test    rdx, rdx
0x18005400c  jz      short loc_180054013
0x18005400e  mov     rdx, [rdx]
0x180054011  jmp     short loc_180054016
0x180054013  mov     rdx, r13
0x180054016  mov     rcx, rbx
0x180054019  mov     rax, rdi
0x18005401c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054021  mov     edi, eax
0x180054023  mov     rbx, qword ptr [rsp+200h+var_190]
0x180054028  test    rbx, rbx
0x18005402b  jz      short loc_18005406D
0x18005402d  mov     ecx, esi
0x18005402f  lock xadd [rbx+10h], ecx
0x180054034  add     ecx, esi
0x180054036  jnz     short loc_18005406D
0x180054038  test    rbx, rbx
0x18005403b  jz      short loc_18005406D
0x18005403d  mov     rcx, [rbx]; bstrString
0x180054040  test    rcx, rcx
0x180054043  jz      short loc_18005404E
0x180054045  call    cs:__imp_SysFreeString
0x18005404b  mov     [rbx], r13
0x18005404e  mov     rcx, [rbx+8]; void *
0x180054052  test    rcx, rcx
0x180054055  jz      short loc_180054060
0x180054057  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005405c  mov     [rbx+8], r13
0x180054060  mov     edx, 18h; unsigned __int64
0x180054065  mov     rcx, rbx; void *
0x180054068  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005406d  test    edi, edi
0x18005406f  jns     short loc_18005409C
0x180054071  mov     rcx, [rbp+108h]; this
0x180054078  mov     r9d, edi; char *
0x18005407b  lea     r8, aOnecoreBaseDia_26; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180054082  mov     edx, 6Bh ; 'k'; void *
0x180054087  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005408c  nop
0x18005408d  lea     rcx, [rsp+200h+var_1B0]
0x180054092  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180054097  jmp     loc_180053F6B
0x18005409c  mov     [rsp+200h+var_1A0], r13
0x1800540a1  mov     rbx, [rsp+200h+var_1A8]
0x1800540a6  mov     rax, [rbx]
0x1800540a9  mov     rsi, [rax+88h]
0x1800540b0  lea     rcx, [rsp+200h+var_1A0]
0x1800540b5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800540ba  lea     rcx, [rsp+200h+var_190+8]; pvarg
0x1800540bf  call    cs:__imp_VariantInit
0x1800540c5  nop
0x1800540c6  movups  xmm6, xmmword ptr [rsp+200h+var_190+8]
0x1800540cb  movsd   xmm7, [rbp+100h+var_178]
0x1800540d0  lea     rcx, [rbp+100h+var_170]; pvarg
0x1800540d4  call    cs:__imp_VariantInit
0x1800540da  nop
0x1800540db  movups  xmm8, xmmword ptr [rbp+100h+var_170]
0x1800540e0  movsd   xmm9, qword ptr [rbp+100h+var_170+10h]
0x1800540e6  lea     rcx, [rbp+100h+pvarg]; pvarg
0x1800540ea  call    cs:__imp_VariantInit
0x1800540f0  nop
0x1800540f1  movups  xmm10, xmmword ptr [rbp+100h+pvarg]
0x1800540f6  movsd   xmm11, qword ptr [rbp+100h+pvarg+10h]
0x1800540fc  mov     rdi, [rsp+200h+var_1B0]
0x180054101  lea     rdx, aRecommendedtro_1; "RecommendedTroubleshootingNotifier"
0x180054108  lea     rcx, [rsp+200h+var_190]; this
0x18005410d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180054112  nop
0x180054113  mov     rdx, [rax]
0x180054116  test    rdx, rdx
0x180054119  jz      short loc_180054120
0x18005411b  mov     rdx, [rdx]
0x18005411e  jmp     short loc_180054123
0x180054120  mov     rdx, r13
0x180054123  movaps  [rbp+100h+var_100], xmm6
0x180054127  movsd   [rbp+100h+var_F0], xmm7
0x18005412c  movaps  [rbp+100h+var_120], xmm8
0x180054131  movsd   [rbp+100h+var_110], xmm9
0x180054137  movaps  xmmword ptr [rbp+100h+var_140], xmm10
0x18005413c  movsd   [rbp+100h+var_130], xmm11
0x180054142  lea     rax, [rsp+200h+var_1A0]
0x180054147  mov     [rsp+200h+var_1C0], rax
0x18005414c  lea     rax, [rbp+100h+var_100]
0x180054150  mov     [rsp+200h+var_1C8], rax
0x180054155  mov     dword ptr [rsp+200h+var_1D0], 5
0x18005415d  lea     rax, [rbp+100h+var_120]
0x180054161  mov     qword ptr [rsp+200h+var_1D8], rax
0x180054166  lea     rax, [rbp+100h+var_140]
0x18005416a  mov     [rsp+200h+ppv], rax; int
0x18005416f  mov     r9d, 6
0x180054175  mov     r8, rdi
0x180054178  mov     rcx, rbx
0x18005417b  mov     rax, rsi
0x18005417e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054183  mov     edi, eax
0x180054185  mov     rbx, qword ptr [rsp+200h+var_190]
0x18005418a  test    rbx, rbx
0x18005418d  jz      short loc_1800541D6
0x18005418f  or      ecx, 0FFFFFFFFh
0x180054192  lock xadd [rbx+10h], ecx
0x180054197  cmp     ecx, 1
0x18005419a  jnz     short loc_1800541D1
0x18005419c  test    rbx, rbx
0x18005419f  jz      short loc_1800541D1
0x1800541a1  mov     rcx, [rbx]; bstrString
0x1800541a4  test    rcx, rcx
0x1800541a7  jz      short loc_1800541B2
0x1800541a9  call    cs:__imp_SysFreeString
0x1800541af  mov     [rbx], r13
0x1800541b2  mov     rcx, [rbx+8]; void *
0x1800541b6  test    rcx, rcx
0x1800541b9  jz      short loc_1800541C4
0x1800541bb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800541c0  mov     [rbx+8], r13
  ... truncated ...
```
