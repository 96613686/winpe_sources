# _lambda_01532e3be30e1782d60ffd88ed9ae2d6_::operator()

- ea: `0x1800c7050`
- end: `0x1800c74f8`
- name: `_lambda_01532e3be30e1782d60ffd88ed9ae2d6_::operator()`
- size: `1192`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800cc7b0`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18007755c`
- `0x18007ff90`
- `0x18008019c`
- `0x18008122c`
- `0x1800839bc`
- `0x1800873a4`
- `0x18008dc5c`
- `0x18008dc94`
- `0x1800951d0`
- `0x1800a13a4`
- `0x1800a13d8`
- `0x1800c4fa4`
- `0x1800c7050`
- `0x1800ca37c`
- `0x1800cb47c`
- `0x1800cd4a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800c7455`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800c7455`
- `OLEAUT32!__imp_VariantInit` at `0x1800c7194`
- `OLEAUT32!__imp_VariantInit` at `0x1800c7194`
- `OLEAUT32!__imp_VariantClear` at `0x1800c722d`
- `OLEAUT32!__imp_VariantClear` at `0x1800c728d`
- `OLEAUT32!__imp_VariantClear` at `0x1800c72cf`
- `OLEAUT32!__imp_VariantClear` at `0x1800c7305`
- `OLEAUT32!__imp_VariantClear` at `0x1800c7327`
- `OLEAUT32!__imp_VariantClear` at `0x1800c722d`
- `OLEAUT32!__imp_VariantClear` at `0x1800c728d`
- `OLEAUT32!__imp_VariantClear` at `0x1800c72cf`
- `OLEAUT32!__imp_VariantClear` at `0x1800c7305`
- `OLEAUT32!__imp_VariantClear` at `0x1800c7327`

## string_xrefs

- `0x1800c712f`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800c7268`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800c746a`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800c71c9`: `/TrackingPoliciesCreated`

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
0x1800c7050  mov     [rsp+arg_10], rbx
0x1800c7055  push    rsi
0x1800c7056  push    rdi
0x1800c7057  push    r12
0x1800c7059  push    r14
0x1800c705b  push    r15
0x1800c705d  sub     rsp, 120h
0x1800c7064  mov     rax, cs:__security_cookie
0x1800c706b  xor     rax, rsp
0x1800c706e  mov     [rsp+148h+var_38], rax
0x1800c7076  mov     rsi, rdx
0x1800c7079  mov     r15, rcx
0x1800c707c  xor     ebx, ebx
0x1800c707e  mov     [rsp+148h+var_118], ebx
0x1800c7082  lea     rax, aUser; "./User"
0x1800c7089  lea     rdx, aDevice; "./Device"
0x1800c7090  cmp     [rcx+18h], rbx
0x1800c7094  cmovnz  rdx, rax
0x1800c7098  lea     rcx, [rsp+148h+var_D8]
0x1800c709d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c70a2  nop
0x1800c70a3  lea     rdx, aVendorMsftEnro; "/Vendor/MSFT/EnrollmentStatusTracking"
0x1800c70aa  lea     rcx, [rsp+148h+var_D8]
0x1800c70af  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800c70b4  lea     rdx, aSetup; "/Setup"
0x1800c70bb  mov     rcx, rax
0x1800c70be  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800c70c3  lea     rdx, aApps_0; "/Apps"
0x1800c70ca  mov     rcx, rax
0x1800c70cd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800c70d2  lea     rdx, aPolicyprovider; "/PolicyProviders"
0x1800c70d9  mov     rcx, rax
0x1800c70dc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800c70e1  xorps   xmm0, xmm0
0x1800c70e4  movdqu  [rsp+148h+var_110], xmm0
0x1800c70ea  mov     [rsp+148h+var_100], rbx
0x1800c70ef  lea     rdx, aApps_0; "/Apps"
0x1800c70f6  lea     rcx, [rsp+148h+var_B8]
0x1800c70fe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c7103  nop
0x1800c7104  lea     rdx, [rsp+148h+var_110]
0x1800c7109  mov     rcx, rax
0x1800c710c  call    ?GetRegisteredPolicyProvidersForType@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@6@@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::GetRegisteredPolicyProvidersForType(std::wstring const &,std::vector<std::wstring> &)
0x1800c7111  mov     edi, eax
0x1800c7113  lea     rcx, [rsp+148h+var_B8]
0x1800c711b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c7120  test    edi, edi
0x1800c7122  jns     short loc_1800C715D
0x1800c7124  mov     rcx, [rsp+148h]; this
0x1800c712c  mov     r9d, edi; char *
0x1800c712f  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800c7136  mov     edx, 138h; void *
0x1800c713b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7140  nop
0x1800c7141  lea     rcx, [rsp+148h+var_110]
0x1800c7146  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800c714b  nop
0x1800c714c  lea     rcx, [rsp+148h+var_D8]
0x1800c7151  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c7156  mov     eax, edi
0x1800c7158  jmp     loc_1800C74CF
0x1800c715d  mov     rdi, qword ptr [rsp+148h+var_110]
0x1800c7162  mov     r14, qword ptr [rsp+148h+var_110+8]
0x1800c7167  mov     [rsp+148h+var_F8], rdi
0x1800c716c  cmp     rdi, r14
0x1800c716f  jz      loc_1800C734C
0x1800c7175  mov     rcx, rdi
0x1800c7178  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c717d  xor     r8d, r8d; unsigned __int64
0x1800c7180  lea     rdx, aListretrievals; "ListRetrievalStarted"
0x1800c7187  mov     rcx, rax; unsigned __int16 *
0x1800c718a  call    ?LogTrackingListState@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAJQEBG0_K@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::LogTrackingListState(ushort const * const,ushort const * const,unsigned __int64)
0x1800c718f  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800c7194  call    cs:__imp_VariantInit
0x1800c719a  nop
0x1800c719b  lea     r8, S2; "/"
0x1800c71a2  lea     rdx, [rsp+148h+var_D8]
0x1800c71a7  lea     rcx, [rsp+148h+var_58]
0x1800c71af  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800c71b4  nop
0x1800c71b5  mov     r8, rdi
0x1800c71b8  mov     rdx, rax
0x1800c71bb  lea     rcx, [rsp+148h+var_78]
0x1800c71c3  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800c71c8  nop
0x1800c71c9  lea     r8, aTrackingpolici; "/TrackingPoliciesCreated"
0x1800c71d0  mov     rdx, rax
0x1800c71d3  lea     rcx, [rsp+148h+var_B8]
0x1800c71db  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800c71e0  nop
0x1800c71e1  lea     rcx, [rsp+148h+var_78]
0x1800c71e9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c71ee  nop
0x1800c71ef  lea     rcx, [rsp+148h+var_58]
0x1800c71f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c71fc  nop
0x1800c71fd  lea     r8, [rsp+148h+pvarg]
0x1800c7202  lea     rdx, [rsp+148h+var_B8]
0x1800c720a  lea     rcx, [r15+8]
0x1800c720e  call    ?TryLookupNodeValue@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAUtagVARIANT@@@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::TryLookupNodeValue(std::wstring const &,std::wstring const &,tagVARIANT *)
0x1800c7213  test    eax, eax
0x1800c7215  jnz     short loc_1800C7250
0x1800c7217  mov     [rsi+10h], al
0x1800c721a  lea     rcx, [rsp+148h+var_B8]
0x1800c7222  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c7227  nop
0x1800c7228  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800c722d  call    cs:__imp_VariantClear
0x1800c7233  nop
0x1800c7234  lea     rcx, [rsp+148h+var_110]
0x1800c7239  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800c723e  nop
0x1800c723f  lea     rcx, [rsp+148h+var_D8]
0x1800c7244  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c7249  xor     eax, eax
0x1800c724b  jmp     loc_1800C74CF
0x1800c7250  cmp     word ptr [rsp+148h+pvarg], 0Bh
0x1800c7256  jz      short loc_1800C72B0
0x1800c7258  mov     rcx, [rsp+148h]; this
0x1800c7260  mov     ebx, 8000FFFFh
0x1800c7265  mov     r9d, ebx; char *
0x1800c7268  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800c726f  mov     edx, 149h; void *
0x1800c7274  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c7279  nop
0x1800c727a  lea     rcx, [rsp+148h+var_B8]
0x1800c7282  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c7287  nop
0x1800c7288  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800c728d  call    cs:__imp_VariantClear
0x1800c7293  nop
0x1800c7294  lea     rcx, [rsp+148h+var_110]
0x1800c7299  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800c729e  nop
0x1800c729f  lea     rcx, [rsp+148h+var_D8]
0x1800c72a4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c72a9  mov     eax, ebx
0x1800c72ab  jmp     loc_1800C74CF
0x1800c72b0  xor     eax, eax
0x1800c72b2  cmp     ax, word ptr [rsp+148h+pvarg+8]
0x1800c72b7  jnz     short loc_1800C72F2
0x1800c72b9  mov     [rsi+10h], al
0x1800c72bc  lea     rcx, [rsp+148h+var_B8]
0x1800c72c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c72c9  nop
0x1800c72ca  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800c72cf  call    cs:__imp_VariantClear
0x1800c72d5  nop
0x1800c72d6  lea     rcx, [rsp+148h+var_110]
0x1800c72db  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800c72e0  nop
0x1800c72e1  lea     rcx, [rsp+148h+var_D8]
0x1800c72e6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c72eb  xor     eax, eax
0x1800c72ed  jmp     loc_1800C74CF
0x1800c72f2  lea     rcx, [rsp+148h+var_B8]
0x1800c72fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c72ff  nop
0x1800c7300  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800c7305  call    cs:__imp_VariantClear
0x1800c730b  add     rdi, 20h ; ' '
0x1800c730f  jmp     loc_1800C7167
0x1800c7314  lea     rcx, [rsp+148h+var_B8]
0x1800c731c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c7321  nop
0x1800c7322  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800c7327  call    cs:__imp_VariantClear
0x1800c732d  nop
0x1800c732e  lea     rcx, [rsp+148h+var_110]
0x1800c7333  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800c7338  nop
0x1800c7339  lea     rcx, [rsp+148h+var_D8]
0x1800c733e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c7343  mov     eax, [rsp+148h+var_118]
0x1800c7347  jmp     loc_1800C74CF
0x1800c734c  mov     byte ptr [rsi+10h], 1
0x1800c7350  mov     [rsp+148h+Data], 0FFFFFFFFh
0x1800c7358  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800c735d  lea     rcx, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Windows\\Autopilot"...
0x1800c7364  lea     rdx, aOsdataSoftware_10; "OSData\\SOFTWARE\\Microsoft\\Windows\\A"...
0x1800c736b  test    al, al
0x1800c736d  cmovz   rdx, rcx
0x1800c7371  lea     rcx, [rsp+148h+var_98]
0x1800c7379  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c737e  nop
0x1800c737f  lea     rdx, SubBlock; "\\"
0x1800c7386  lea     rcx, [rsp+148h+var_98]
0x1800c738e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800c7393  mov     rdi, rax
0x1800c7396  cmp     qword ptr [r15+18h], 0
0x1800c739b  jnz     short loc_1800C73B7
0x1800c739d  lea     rdx, aDevice_0; "Device"
0x1800c73a4  lea     rcx, [rsp+148h+var_78]
0x1800c73ac  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c73b1  nop
0x1800c73b2  or      ebx, 1
0x1800c73b5  jmp     short loc_1800C73CC
0x1800c73b7  lea     rdx, [r15+8]
0x1800c73bb  lea     rcx, [rsp+148h+var_58]
0x1800c73c3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800c73c8  nop
0x1800c73c9  or      ebx, 2
0x1800c73cc  mov     [rsp+148h+var_118], ebx
0x1800c73d0  mov     rdx, rax
0x1800c73d3  mov     rcx, rdi
0x1800c73d6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1800c73db  lea     rdx, aSetup_0; "\\Setup"
0x1800c73e2  mov     rcx, rax
0x1800c73e5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800c73ea  lea     rdx, aApps; "\\Apps"
0x1800c73f1  mov     rcx, rax
0x1800c73f4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800c73f9  nop
0x1800c73fa  test    bl, 2
0x1800c73fd  jz      short loc_1800C7410
0x1800c73ff  and     ebx, 0FFFFFFFDh
0x1800c7402  lea     rcx, [rsp+148h+var_58]
0x1800c740a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c740f  nop
0x1800c7410  test    bl, 1
0x1800c7413  jz      short loc_1800C7422
0x1800c7415  lea     rcx, [rsp+148h+var_78]
0x1800c741d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c7422  lea     rcx, [rsp+148h+var_98]
0x1800c742a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c742f  mov     rdx, rax; lpSubKey
0x1800c7432  mov     r9d, 4; dwType
0x1800c7438  mov     [rsp+148h+cbData], r9d; cbData
0x1800c743d  lea     rax, [rsp+148h+Data]
0x1800c7442  mov     [rsp+148h+lpData], rax; unsigned int
0x1800c7447  lea     r8, aLocked; "Locked"
0x1800c744e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c7455  call    cs:__imp_RegSetKeyValueW
0x1800c745b  test    eax, eax
0x1800c745d  jz      short loc_1800C74A4
0x1800c745f  mov     rcx, [rsp+148h]; this
0x1800c7467  mov     r9d, eax; char *
0x1800c746a  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800c7471  mov     edx, 169h; void *
0x1800c7476  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800c747b  mov     ebx, eax
0x1800c747d  lea     rcx, [rsp+148h+var_98]
0x1800c7485  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c748a  nop
0x1800c748b  lea     rcx, [rsp+148h+var_110]
0x1800c7490  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800c7495  nop
0x1800c7496  lea     rcx, [rsp+148h+var_D8]
0x1800c749b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c74a0  mov     eax, ebx
0x1800c74a2  jmp     short loc_1800C74CF
0x1800c74a4  lea     rcx, [rsp+148h+var_98]
0x1800c74ac  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c74b1  nop
0x1800c74b2  lea     rcx, [rsp+148h+var_110]
0x1800c74b7  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800c74bc  nop
0x1800c74bd  lea     rcx, [rsp+148h+var_D8]
0x1800c74c2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c74c7  xor     eax, eax
0x1800c74c9  jmp     short loc_1800C74CF
0x1800c74cb  mov     eax, [rsp+148h+Data]
0x1800c74cf  mov     rcx, [rsp+148h+var_38]
0x1800c74d7  xor     rcx, rsp; StackCookie
0x1800c74da  call    __security_check_cookie
0x1800c74df  mov     rbx, [rsp+148h+arg_10]
0x1800c74e7  add     rsp, 120h
0x1800c74ee  pop     r15
0x1800c74f0  pop     r14
0x1800c74f2  pop     r12
0x1800c74f4  pop     rdi
0x1800c74f5  pop     rsi
0x1800c74f6  retn
```
