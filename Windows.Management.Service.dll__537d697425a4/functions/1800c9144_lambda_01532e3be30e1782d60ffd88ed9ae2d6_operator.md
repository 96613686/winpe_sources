# _lambda_01532e3be30e1782d60ffd88ed9ae2d6_::operator()

- ea: `0x1800c9144`
- end: `0x1800c9616`
- name: `_lambda_01532e3be30e1782d60ffd88ed9ae2d6_::operator()`
- size: `1234`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800ceb30`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x180077de0`
- `0x180080984`
- `0x180080bac`
- `0x180081cac`
- `0x180084574`
- `0x180088144`
- `0x18008ed40`
- `0x18008ed78`
- `0x1800964d4`
- `0x1800a29ac`
- `0x1800a29e0`
- `0x1800c705c`
- `0x1800c9144`
- `0x1800cc5f0`
- `0x1800cd7b4`
- `0x1800cf888`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800c956d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800c956d`
- `OLEAUT32!__imp_VariantInit` at `0x1800c9288`
- `OLEAUT32!__imp_VariantInit` at `0x1800c9288`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9327`
- `OLEAUT32!__imp_VariantClear` at `0x1800c938d`
- `OLEAUT32!__imp_VariantClear` at `0x1800c93d5`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9411`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9439`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9327`
- `OLEAUT32!__imp_VariantClear` at `0x1800c938d`
- `OLEAUT32!__imp_VariantClear` at `0x1800c93d5`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9411`
- `OLEAUT32!__imp_VariantClear` at `0x1800c9439`

## string_xrefs

- `0x1800c92c3`: `/TrackingPoliciesCreated`
- `0x1800c9223`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800c9368`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800c9588`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall lambda_01532e3be30e1782d60ffd88ed9ae2d6_::operator()(__int64 a1, __int64 a2)
{
  const wchar_t *v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  int RegisteredPolicyProvidersForType; // edi
  __int64 i; // rdi
  __int64 v12; // r14
  const unsigned __int16 *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // eax
  wil *v17; // rcx
  bool v18; // al
  const wchar_t *v19; // rdx
  __int64 v20; // rdi
  __int64 v21; // rax
  char v22; // bl
  __int64 v23; // rax
  __int64 v24; // rax
  const WCHAR *v25; // rax
  unsigned int v26; // eax
  unsigned int v27; // ebx
  unsigned int v28; // eax
  char v29; // bl
  int v30; // eax
  int v31; // ecx
  int lpData; // [rsp+20h] [rbp-128h]
  unsigned int lpDataa; // [rsp+20h] [rbp-128h]
  unsigned int v34; // [rsp+30h] [rbp-118h]
  int Data; // [rsp+34h] [rbp-114h] BYREF
  __int128 v36; // [rsp+38h] [rbp-110h] BYREF
  __int64 v37; // [rsp+48h] [rbp-100h]
  __int64 v38; // [rsp+50h] [rbp-F8h]
  VARIANTARG pvarg; // [rsp+58h] [rbp-F0h] BYREF
  _BYTE v40[32]; // [rsp+70h] [rbp-D8h] BYREF
  _BYTE v41[32]; // [rsp+90h] [rbp-B8h] BYREF
  _BYTE v42[32]; // [rsp+B0h] [rbp-98h] BYREF
  _BYTE v43[32]; // [rsp+D0h] [rbp-78h] BYREF
  _BYTE v44[32]; // [rsp+F0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v4 = L"./Device";
  if ( *(_QWORD *)(a1 + 24) )
    v4 = L"./User";
  std::wstring::wstring(v40, v4);
  v5 = std::wstring::append(v40, L"/Vendor/MSFT/EnrollmentStatusTracking");
  v6 = std::wstring::append(v5, L"/Setup");
  v7 = std::wstring::append(v6, L"/Apps");
  std::wstring::append(v7, L"/PolicyProviders");
  v36 = 0;
  v37 = 0;
  v8 = std::wstring::wstring(v41, L"/Apps");
  RegisteredPolicyProvidersForType = EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::GetRegisteredPolicyProvidersForType(
                                       v8,
                                       &v36);
  std::wstring::_Tidy_deallocate(v41);
  if ( RegisteredPolicyProvidersForType >= 0 )
  {
    v12 = *((_QWORD *)&v36 + 1);
    for ( i = v36; ; i += 32 )
    {
      v38 = i;
      if ( i == v12 )
        break;
      v13 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i);
      EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::LogTrackingListState(
        v13,
        L"ListRetrievalStarted",
        0);
      VariantInit(&pvarg);
      v14 = std::operator+<unsigned short>(v44, v40, L"/");
      v15 = std::operator+<unsigned short>(v43, v14, i);
      std::operator+<unsigned short>(v41, v15, L"/TrackingPoliciesCreated");
      std::wstring::_Tidy_deallocate(v43);
      std::wstring::_Tidy_deallocate(v44);
      try
      {
        v16 = EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::TryLookupNodeValue(
                a1 + 8,
                v41,
                &pvarg);
      }
      catch ( ... )
      {
        v28 = wil::ResultFromCaughtException(v17);
        v29 = v28;
        v34 = v28;
        if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
        {
          v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38);
          McTemplateU0zzd_EventWriteTransfer(
            v31,
            (unsigned int)AutopilotManagerProviderTrackingListRetrievalFailed,
            (unsigned int)L"Provider",
            v30,
            v29);
        }
        std::wstring::_Tidy_deallocate(v41);
        VariantClear(&pvarg);
        std::vector<std::wstring>::_Tidy(&v36);
        std::wstring::_Tidy_deallocate(v40);
        return v34;
      }
      if ( !v16 )
      {
LABEL_9:
        *(_BYTE *)(a2 + 16) = 0;
        std::wstring::_Tidy_deallocate(v41);
        VariantClear(&pvarg);
        std::vector<std::wstring>::_Tidy(&v36);
        std::wstring::_Tidy_deallocate(v40);
        return 0;
      }
      if ( pvarg.vt != 11 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x149,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
          (const char *)0x8000FFFFLL,
          lpData);
        std::wstring::_Tidy_deallocate(v41);
        VariantClear(&pvarg);
        std::vector<std::wstring>::_Tidy(&v36);
        std::wstring::_Tidy_deallocate(v40);
        return 2147549183LL;
      }
      if ( !pvarg.iVal )
        goto LABEL_9;
      std::wstring::_Tidy_deallocate(v41);
      VariantClear(&pvarg);
    }
    *(_BYTE *)(a2 + 16) = 1;
    Data = -1;
    v18 = ZTPIsStateSeparationEnabled();
    v19 = L"OSData\\SOFTWARE\\Microsoft\\Windows\\Autopilot\\EnrollmentStatusTracking";
    if ( !v18 )
      v19 = L"SOFTWARE\\Microsoft\\Windows\\Autopilot\\EnrollmentStatusTracking";
    std::wstring::wstring(v42, v19);
    v20 = std::wstring::append(v42, L"\\");
    if ( *(_QWORD *)(a1 + 24) )
    {
      v21 = std::wstring::wstring(v44, a1 + 8);
      v22 = 2;
    }
    else
    {
      v21 = std::wstring::wstring(v43, L"Device");
      v22 = 1;
    }
    v23 = std::wstring::append(v20, v21);
    v24 = std::wstring::append(v23, L"\\Setup");
    std::wstring::append(v24, L"\\Apps");
    if ( (v22 & 2) != 0 )
    {
      v22 &= ~2u;
      std::wstring::_Tidy_deallocate(v44);
    }
    if ( (v22 & 1) != 0 )
      std::wstring::_Tidy_deallocate(v43);
    v25 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v42);
    v26 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v25, L"Locked", 4u, &Data, 4u);
    if ( v26 )
    {
      v27 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x169,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
              (const char *)v26,
              lpDataa);
      std::wstring::_Tidy_deallocate(v42);
      std::vector<std::wstring>::_Tidy(&v36);
      std::wstring::_Tidy_deallocate(v40);
      return v27;
    }
    else
    {
      std::wstring::_Tidy_deallocate(v42);
      std::vector<std::wstring>::_Tidy(&v36);
      std::wstring::_Tidy_deallocate(v40);
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x138,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
      (const char *)(unsigned int)RegisteredPolicyProvidersForType,
      lpData);
    std::vector<std::wstring>::_Tidy(&v36);
    std::wstring::_Tidy_deallocate(v40);
    return (unsigned int)RegisteredPolicyProvidersForType;
  }
}

```

## disassembly

```asm
0x1800c9144  mov     [rsp+arg_10], rbx
0x1800c9149  push    rsi
0x1800c914a  push    rdi
0x1800c914b  push    r12
0x1800c914d  push    r14
0x1800c914f  push    r15
0x1800c9151  sub     rsp, 120h
0x1800c9158  mov     rax, cs:__security_cookie
0x1800c915f  xor     rax, rsp
0x1800c9162  mov     [rsp+148h+var_38], rax
0x1800c916a  mov     rsi, rdx
0x1800c916d  mov     r15, rcx
0x1800c9170  xor     ebx, ebx
0x1800c9172  mov     [rsp+148h+var_118], ebx
0x1800c9176  lea     rax, aUser; "./User"
0x1800c917d  lea     rdx, aDevice; "./Device"
0x1800c9184  cmp     [rcx+18h], rbx
0x1800c9188  cmovnz  rdx, rax
0x1800c918c  lea     rcx, [rsp+148h+var_D8]
0x1800c9191  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c9196  nop
0x1800c9197  lea     rdx, aVendorMsftEnro; "/Vendor/MSFT/EnrollmentStatusTracking"
0x1800c919e  lea     rcx, [rsp+148h+var_D8]
0x1800c91a3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800c91a8  lea     rdx, aSetup; "/Setup"
0x1800c91af  mov     rcx, rax
0x1800c91b2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800c91b7  lea     rdx, aApps_0; "/Apps"
0x1800c91be  mov     rcx, rax
0x1800c91c1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800c91c6  lea     rdx, aPolicyprovider; "/PolicyProviders"
0x1800c91cd  mov     rcx, rax
0x1800c91d0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800c91d5  xorps   xmm0, xmm0
0x1800c91d8  movdqu  [rsp+148h+var_110], xmm0
0x1800c91de  mov     [rsp+148h+var_100], rbx
0x1800c91e3  lea     rdx, aApps_0; "/Apps"
0x1800c91ea  lea     rcx, [rsp+148h+var_B8]
0x1800c91f2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c91f7  nop
0x1800c91f8  lea     rdx, [rsp+148h+var_110]
0x1800c91fd  mov     rcx, rax
0x1800c9200  call    ?GetRegisteredPolicyProvidersForType@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@6@@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::GetRegisteredPolicyProvidersForType(std::wstring const &,std::vector<std::wstring> &)
0x1800c9205  mov     edi, eax
0x1800c9207  lea     rcx, [rsp+148h+var_B8]
0x1800c920f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c9214  test    edi, edi
0x1800c9216  jns     short loc_1800C9251
0x1800c9218  mov     rcx, [rsp+148h]; this
0x1800c9220  mov     r9d, edi; char *
0x1800c9223  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800c922a  mov     edx, 138h; void *
0x1800c922f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9234  nop
0x1800c9235  lea     rcx, [rsp+148h+var_110]
0x1800c923a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800c923f  nop
0x1800c9240  lea     rcx, [rsp+148h+var_D8]
0x1800c9245  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c924a  mov     eax, edi
0x1800c924c  jmp     loc_1800C95ED
0x1800c9251  mov     rdi, qword ptr [rsp+148h+var_110]
0x1800c9256  mov     r14, qword ptr [rsp+148h+var_110+8]
0x1800c925b  mov     [rsp+148h+var_F8], rdi
0x1800c9260  cmp     rdi, r14
0x1800c9263  jz      loc_1800C9464
0x1800c9269  mov     rcx, rdi
0x1800c926c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c9271  xor     r8d, r8d; unsigned __int64
0x1800c9274  lea     rdx, aListretrievals; "ListRetrievalStarted"
0x1800c927b  mov     rcx, rax; unsigned __int16 *
0x1800c927e  call    ?LogTrackingListState@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAJQEBG0_K@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::LogTrackingListState(ushort const * const,ushort const * const,unsigned __int64)
0x1800c9283  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800c9288  call    cs:__imp_VariantInit
0x1800c928f  nop     dword ptr [rax+rax+00h]
0x1800c9294  nop
0x1800c9295  lea     r8, S2; "/"
0x1800c929c  lea     rdx, [rsp+148h+var_D8]
0x1800c92a1  lea     rcx, [rsp+148h+var_58]
0x1800c92a9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800c92ae  nop
0x1800c92af  mov     r8, rdi
0x1800c92b2  mov     rdx, rax
0x1800c92b5  lea     rcx, [rsp+148h+var_78]
0x1800c92bd  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800c92c2  nop
0x1800c92c3  lea     r8, aTrackingpolici; "/TrackingPoliciesCreated"
0x1800c92ca  mov     rdx, rax
0x1800c92cd  lea     rcx, [rsp+148h+var_B8]
0x1800c92d5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800c92da  nop
0x1800c92db  lea     rcx, [rsp+148h+var_78]
0x1800c92e3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c92e8  nop
0x1800c92e9  lea     rcx, [rsp+148h+var_58]
0x1800c92f1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c92f6  nop
0x1800c92f7  lea     r8, [rsp+148h+pvarg]
0x1800c92fc  lea     rdx, [rsp+148h+var_B8]
0x1800c9304  lea     rcx, [r15+8]
0x1800c9308  call    ?TryLookupNodeValue@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAUtagVARIANT@@@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::TryLookupNodeValue(std::wstring const &,std::wstring const &,tagVARIANT *)
0x1800c930d  test    eax, eax
0x1800c930f  jnz     short loc_1800C9350
0x1800c9311  mov     [rsi+10h], al
0x1800c9314  lea     rcx, [rsp+148h+var_B8]
0x1800c931c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c9321  nop
0x1800c9322  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800c9327  call    cs:__imp_VariantClear
0x1800c932e  nop     dword ptr [rax+rax+00h]
0x1800c9333  nop
0x1800c9334  lea     rcx, [rsp+148h+var_110]
0x1800c9339  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800c933e  nop
0x1800c933f  lea     rcx, [rsp+148h+var_D8]
0x1800c9344  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c9349  xor     eax, eax
0x1800c934b  jmp     loc_1800C95ED
0x1800c9350  cmp     word ptr [rsp+148h+pvarg], 0Bh
0x1800c9356  jz      short loc_1800C93B6
0x1800c9358  mov     rcx, [rsp+148h]; this
0x1800c9360  mov     ebx, 8000FFFFh
0x1800c9365  mov     r9d, ebx; char *
0x1800c9368  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800c936f  mov     edx, 149h; void *
0x1800c9374  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9379  nop
0x1800c937a  lea     rcx, [rsp+148h+var_B8]
0x1800c9382  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c9387  nop
0x1800c9388  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800c938d  call    cs:__imp_VariantClear
0x1800c9394  nop     dword ptr [rax+rax+00h]
0x1800c9399  nop
0x1800c939a  lea     rcx, [rsp+148h+var_110]
0x1800c939f  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800c93a4  nop
0x1800c93a5  lea     rcx, [rsp+148h+var_D8]
0x1800c93aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c93af  mov     eax, ebx
0x1800c93b1  jmp     loc_1800C95ED
0x1800c93b6  xor     eax, eax
0x1800c93b8  cmp     ax, word ptr [rsp+148h+pvarg+8]
0x1800c93bd  jnz     short loc_1800C93FE
0x1800c93bf  mov     [rsi+10h], al
0x1800c93c2  lea     rcx, [rsp+148h+var_B8]
0x1800c93ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c93cf  nop
0x1800c93d0  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800c93d5  call    cs:__imp_VariantClear
0x1800c93dc  nop     dword ptr [rax+rax+00h]
0x1800c93e1  nop
0x1800c93e2  lea     rcx, [rsp+148h+var_110]
0x1800c93e7  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800c93ec  nop
0x1800c93ed  lea     rcx, [rsp+148h+var_D8]
0x1800c93f2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c93f7  xor     eax, eax
0x1800c93f9  jmp     loc_1800C95ED
0x1800c93fe  lea     rcx, [rsp+148h+var_B8]
0x1800c9406  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c940b  nop
0x1800c940c  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800c9411  call    cs:__imp_VariantClear
0x1800c9418  nop     dword ptr [rax+rax+00h]
0x1800c941d  add     rdi, 20h ; ' '
0x1800c9421  jmp     loc_1800C925B
0x1800c9426  lea     rcx, [rsp+148h+var_B8]
0x1800c942e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c9433  nop
0x1800c9434  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800c9439  call    cs:__imp_VariantClear
0x1800c9440  nop     dword ptr [rax+rax+00h]
0x1800c9445  nop
0x1800c9446  lea     rcx, [rsp+148h+var_110]
0x1800c944b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800c9450  nop
0x1800c9451  lea     rcx, [rsp+148h+var_D8]
0x1800c9456  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c945b  mov     eax, [rsp+148h+var_118]
0x1800c945f  jmp     loc_1800C95ED
0x1800c9464  mov     byte ptr [rsi+10h], 1
0x1800c9468  mov     [rsp+148h+Data], 0FFFFFFFFh
0x1800c9470  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800c9475  lea     rcx, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Windows\\Autopilot"...
0x1800c947c  lea     rdx, aOsdataSoftware_10; "OSData\\SOFTWARE\\Microsoft\\Windows\\A"...
0x1800c9483  test    al, al
0x1800c9485  cmovz   rdx, rcx
0x1800c9489  lea     rcx, [rsp+148h+var_98]
0x1800c9491  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c9496  nop
0x1800c9497  lea     rdx, SubBlock; "\\"
0x1800c949e  lea     rcx, [rsp+148h+var_98]
0x1800c94a6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800c94ab  mov     rdi, rax
0x1800c94ae  cmp     qword ptr [r15+18h], 0
0x1800c94b3  jnz     short loc_1800C94CF
0x1800c94b5  lea     rdx, aDevice_0; "Device"
0x1800c94bc  lea     rcx, [rsp+148h+var_78]
0x1800c94c4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c94c9  nop
0x1800c94ca  or      ebx, 1
0x1800c94cd  jmp     short loc_1800C94E4
0x1800c94cf  lea     rdx, [r15+8]
0x1800c94d3  lea     rcx, [rsp+148h+var_58]
0x1800c94db  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800c94e0  nop
0x1800c94e1  or      ebx, 2
0x1800c94e4  mov     [rsp+148h+var_118], ebx
0x1800c94e8  mov     rdx, rax
0x1800c94eb  mov     rcx, rdi
0x1800c94ee  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800c94f3  lea     rdx, aSetup_0; "\\Setup"
0x1800c94fa  mov     rcx, rax
0x1800c94fd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800c9502  lea     rdx, aApps; "\\Apps"
0x1800c9509  mov     rcx, rax
0x1800c950c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800c9511  nop
0x1800c9512  test    bl, 2
0x1800c9515  jz      short loc_1800C9528
0x1800c9517  and     ebx, 0FFFFFFFDh
0x1800c951a  lea     rcx, [rsp+148h+var_58]
0x1800c9522  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c9527  nop
0x1800c9528  test    bl, 1
0x1800c952b  jz      short loc_1800C953A
0x1800c952d  lea     rcx, [rsp+148h+var_78]
0x1800c9535  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c953a  lea     rcx, [rsp+148h+var_98]
0x1800c9542  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c9547  mov     rdx, rax; lpSubKey
0x1800c954a  mov     r9d, 4; dwType
0x1800c9550  mov     [rsp+148h+cbData], r9d; cbData
0x1800c9555  lea     rax, [rsp+148h+Data]
0x1800c955a  mov     [rsp+148h+lpData], rax; unsigned int
0x1800c955f  lea     r8, aLocked; "Locked"
0x1800c9566  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c956d  call    cs:__imp_RegSetKeyValueW
0x1800c9574  nop     dword ptr [rax+rax+00h]
0x1800c9579  test    eax, eax
0x1800c957b  jz      short loc_1800C95C2
0x1800c957d  mov     rcx, [rsp+148h]; this
0x1800c9585  mov     r9d, eax; char *
0x1800c9588  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800c958f  mov     edx, 169h; void *
0x1800c9594  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800c9599  mov     ebx, eax
0x1800c959b  lea     rcx, [rsp+148h+var_98]
0x1800c95a3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c95a8  nop
0x1800c95a9  lea     rcx, [rsp+148h+var_110]
0x1800c95ae  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800c95b3  nop
0x1800c95b4  lea     rcx, [rsp+148h+var_D8]
0x1800c95b9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c95be  mov     eax, ebx
0x1800c95c0  jmp     short loc_1800C95ED
0x1800c95c2  lea     rcx, [rsp+148h+var_98]
0x1800c95ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c95cf  nop
0x1800c95d0  lea     rcx, [rsp+148h+var_110]
0x1800c95d5  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800c95da  nop
0x1800c95db  lea     rcx, [rsp+148h+var_D8]
0x1800c95e0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c95e5  xor     eax, eax
0x1800c95e7  jmp     short loc_1800C95ED
0x1800c95e9  mov     eax, [rsp+148h+Data]
0x1800c95ed  mov     rcx, [rsp+148h+var_38]
0x1800c95f5  xor     rcx, rsp; StackCookie
0x1800c95f8  call    __security_check_cookie
0x1800c95fd  mov     rbx, [rsp+148h+arg_10]
0x1800c9605  add     rsp, 120h
0x1800c960c  pop     r15
0x1800c960e  pop     r14
0x1800c9610  pop     r12
0x1800c9612  pop     rdi
0x1800c9613  pop     rsi
0x1800c9614  retn
```
