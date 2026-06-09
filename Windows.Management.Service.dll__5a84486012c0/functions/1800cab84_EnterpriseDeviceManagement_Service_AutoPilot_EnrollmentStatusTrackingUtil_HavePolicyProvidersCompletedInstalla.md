# EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::HavePolicyProvidersCompletedInstallation(ulong,int &)

- ea: `0x1800cab84`
- end: `0x1800cb158`
- name: `?HavePolicyProvidersCompletedInstallation@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@SAJKAEAH@Z`
- size: `1492`
- prototype: `__int64 __fastcall(unsigned int, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a5b20`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18006c628`
- `0x18007755c`
- `0x18008019c`
- `0x180080bcc`
- `0x1800839bc`
- `0x18008dc94`
- `0x1800951d0`
- `0x1800a13a4`
- `0x1800c4fa4`
- `0x1800cab84`
- `0x1800cb75c`
- `0x1800cd4a4`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800cad02`
- `OLEAUT32!__imp_VariantInit` at `0x1800cae4c`
- `OLEAUT32!__imp_VariantInit` at `0x1800cad02`
- `OLEAUT32!__imp_VariantInit` at `0x1800cae4c`
- `OLEAUT32!__imp_VariantClear` at `0x1800cad92`
- `OLEAUT32!__imp_VariantClear` at `0x1800cae03`
- `OLEAUT32!__imp_VariantClear` at `0x1800caeeb`
- `OLEAUT32!__imp_VariantClear` at `0x1800caf05`
- `OLEAUT32!__imp_VariantClear` at `0x1800caf70`
- `OLEAUT32!__imp_VariantClear` at `0x1800caf8a`
- `OLEAUT32!__imp_VariantClear` at `0x1800cb017`
- `OLEAUT32!__imp_VariantClear` at `0x1800cb054`
- `OLEAUT32!__imp_VariantClear` at `0x1800cb06e`
- `OLEAUT32!__imp_VariantClear` at `0x1800cb0ef`
- `OLEAUT32!__imp_VariantClear` at `0x1800cb139`
- `OLEAUT32!__imp_VariantClear` at `0x1800cad92`
- `OLEAUT32!__imp_VariantClear` at `0x1800cae03`
- `OLEAUT32!__imp_VariantClear` at `0x1800caeeb`
- `OLEAUT32!__imp_VariantClear` at `0x1800caf05`
- `OLEAUT32!__imp_VariantClear` at `0x1800caf70`
- `OLEAUT32!__imp_VariantClear` at `0x1800caf8a`
- `OLEAUT32!__imp_VariantClear` at `0x1800cb017`
- `OLEAUT32!__imp_VariantClear` at `0x1800cb054`
- `OLEAUT32!__imp_VariantClear` at `0x1800cb06e`
- `OLEAUT32!__imp_VariantClear` at `0x1800cb0ef`
- `OLEAUT32!__imp_VariantClear` at `0x1800cb139`

## string_xrefs

- `0x1800cac7e`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cad6d`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cadde`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800caec9`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cb032`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cb0ca`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cad09`: `/InstallationState`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::HavePolicyProvidersCompletedInstallation(
        unsigned int a1,
        int *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  int v9; // ebx
  int v11; // r14d
  __int64 v12; // rsi
  __int64 v13; // r12
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // ebx
  unsigned int Lo; // ebx
  __int64 v18; // rax
  int v19; // r15d
  unsigned __int64 v20; // rcx
  __int64 v21; // [rsp+20h] [rbp-128h] BYREF
  __int64 v22; // [rsp+28h] [rbp-120h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-108h] BYREF
  VARIANTARG v24; // [rsp+58h] [rbp-F0h] BYREF
  _BYTE v25[32]; // [rsp+70h] [rbp-D8h] BYREF
  _BYTE v26[32]; // [rsp+90h] [rbp-B8h] BYREF
  _BYTE v27[32]; // [rsp+B0h] [rbp-98h] BYREF
  _BYTE v28[32]; // [rsp+D0h] [rbp-78h] BYREF
  _BYTE v29[32]; // [rsp+F0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  *a2 = 0;
  std::wstring::wstring(v28);
  v4 = std::wstring::append(v28, L"./Device");
  v5 = std::wstring::append(v4, L"/Vendor/MSFT/EnrollmentStatusTracking");
  v6 = std::wstring::append(v5, L"/DevicePreparation");
  std::wstring::append(v6, L"/PolicyProviders");
  std::_Compressed_pair<std::allocator<unsigned int>,std::_Vector_val<std::_Simple_types<unsigned int>>,1>::_Compressed_pair<std::allocator<unsigned int>,std::_Vector_val<std::_Simple_types<unsigned int>>,1>(&v21);
  v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
  std::wstring::wstring(v25, v7);
  v8 = std::wstring::wstring(v26, &sourceString);
  v9 = EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::LookupChildNodesForUri(
         v8,
         (__int64)v25,
         (__int64)&v21);
  std::wstring::_Tidy_deallocate(v26);
  std::wstring::_Tidy_deallocate(v25);
  if ( v9 >= 0 )
  {
    v11 = 0;
    v12 = v21;
    v13 = v22;
    while ( v12 != v13 )
    {
      v14 = std::operator+<unsigned short>(v25, v28, L"/");
      std::operator+<unsigned short>(v27, v14, v12);
      std::wstring::_Tidy_deallocate(v25);
      VariantInit(&pvarg);
      std::operator+<unsigned short>(v26, v27, L"/InstallationState");
      v15 = std::wstring::wstring(v25, &sourceString);
      v16 = EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::TryLookupNodeValue(
              v15,
              v26,
              &pvarg);
      std::wstring::_Tidy_deallocate(v25);
      if ( !v16 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x286,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
          (const char *)0x80070490LL,
          v21);
        std::wstring::_Tidy_deallocate(v26);
        VariantClear(&pvarg);
        std::wstring::_Tidy_deallocate(v27);
        std::vector<std::wstring>::_Tidy(&v21);
        std::wstring::_Tidy_deallocate(v28);
        return 2147943568LL;
      }
      if ( pvarg.vt != 3 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x287,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
          (const char *)0x8000FFFFLL,
          v21);
        std::wstring::_Tidy_deallocate(v26);
        VariantClear(&pvarg);
        std::wstring::_Tidy_deallocate(v27);
        std::vector<std::wstring>::_Tidy(&v21);
        std::wstring::_Tidy_deallocate(v28);
        return 2147549183LL;
      }
      if ( pvarg.lVal == 1 )
      {
        Lo = 30;
        VariantInit(&v24);
        std::operator+<unsigned short>(v25, v27, L"/Timeout");
        v18 = std::wstring::wstring(v29, &sourceString);
        v19 = EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::TryLookupNodeValue(
                v18,
                v25,
                &v24);
        std::wstring::_Tidy_deallocate(v29);
        if ( v19 )
        {
          if ( v24.vt != 3 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x293,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
              (const char *)0x8000FFFFLL,
              v21);
            std::wstring::_Tidy_deallocate(v25);
            VariantClear(&v24);
            std::wstring::_Tidy_deallocate(v26);
            VariantClear(&pvarg);
            std::wstring::_Tidy_deallocate(v27);
            std::vector<std::wstring>::_Tidy(&v21);
            std::wstring::_Tidy_deallocate(v28);
            return 2147549183LL;
          }
          Lo = v24.cyVal.Lo;
        }
        v20 = 60LL * Lo;
        if ( v20 > 0xFFFFFFFF )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x298,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
            (const char *)0x80070216LL,
            v21);
          std::wstring::_Tidy_deallocate(v25);
          VariantClear(&v24);
          std::wstring::_Tidy_deallocate(v26);
          VariantClear(&pvarg);
          std::wstring::_Tidy_deallocate(v27);
          std::vector<std::wstring>::_Tidy(&v21);
          std::wstring::_Tidy_deallocate(v28);
          return 2147942934LL;
        }
        if ( a1 >= (unsigned int)v20 )
        {
          *a2 = 1;
          std::wstring::_Tidy_deallocate(v25);
          VariantClear(&v24);
LABEL_17:
          std::wstring::_Tidy_deallocate(v26);
          VariantClear(&pvarg);
          std::wstring::_Tidy_deallocate(v27);
          break;
        }
        std::wstring::_Tidy_deallocate(v25);
        VariantClear(&v24);
      }
      else
      {
        if ( pvarg.lVal == 4 )
        {
          *a2 = 1;
          goto LABEL_17;
        }
        if ( (unsigned int)(pvarg.lVal - 2) > 1 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2AF,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
            (const char *)0x8000FFFFLL,
            v21);
          std::wstring::_Tidy_deallocate(v26);
          VariantClear(&pvarg);
          std::wstring::_Tidy_deallocate(v27);
          std::vector<std::wstring>::_Tidy(&v21);
          std::wstring::_Tidy_deallocate(v28);
          return 2147549183LL;
        }
        ++v11;
      }
      std::wstring::_Tidy_deallocate(v26);
      VariantClear(&pvarg);
      std::wstring::_Tidy_deallocate(v27);
      v12 += 32;
    }
    if ( v11 == (v22 - v21) >> 5 )
      *a2 = 1;
    std::vector<std::wstring>::_Tidy(&v21);
    std::wstring::_Tidy_deallocate(v28);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27E,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
      (const char *)(unsigned int)v9,
      v21);
    std::vector<std::wstring>::_Tidy(&v21);
    std::wstring::_Tidy_deallocate(v28);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x1800cab84  mov     r11, rsp
0x1800cab87  mov     [r11+8], rbx
0x1800cab8b  mov     [r11+18h], rsi
0x1800cab8f  push    rdi
0x1800cab90  push    r12
0x1800cab92  push    r13
0x1800cab94  push    r14
0x1800cab96  push    r15
0x1800cab98  sub     rsp, 120h
0x1800cab9f  mov     rax, cs:__security_cookie
0x1800caba6  xor     rax, rsp
0x1800caba9  mov     [rsp+148h+var_38], rax
0x1800cabb1  mov     rdi, rdx
0x1800cabb4  mov     r13d, ecx
0x1800cabb7  mov     dword ptr [rdx], 0
0x1800cabbd  lea     rcx, [r11-78h]
0x1800cabc1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cabc6  nop
0x1800cabc7  lea     rdx, aDevice; "./Device"
0x1800cabce  lea     rcx, [rsp+148h+var_78]
0x1800cabd6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800cabdb  lea     rdx, aVendorMsftEnro; "/Vendor/MSFT/EnrollmentStatusTracking"
0x1800cabe2  mov     rcx, rax
0x1800cabe5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800cabea  lea     rdx, aDevicepreparat_0; "/DevicePreparation"
0x1800cabf1  mov     rcx, rax
0x1800cabf4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800cabf9  lea     rdx, aPolicyprovider; "/PolicyProviders"
0x1800cac00  mov     rcx, rax
0x1800cac03  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800cac08  lea     rcx, [rsp+148h+var_128]
0x1800cac0d  call    ??$?0V?$allocator@I@std@@$$V@?$_Compressed_pair@V?$allocator@I@std@@V?$_Vector_val@U?$_Simple_types@I@std@@@2@$00@std@@QEAA@U_One_then_variadic_args_t@1@$$QEAV?$allocator@I@1@@Z; std::_Compressed_pair<std::allocator<uint>,std::_Vector_val<std::_Simple_types<uint>>,1>::_Compressed_pair<std::allocator<uint>,std::_Vector_val<std::_Simple_types<uint>>,1>(std::_One_then_variadic_args_t,std::allocator<uint> &&)
0x1800cac12  nop
0x1800cac13  lea     rcx, [rsp+148h+var_78]
0x1800cac1b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cac20  mov     rdx, rax
0x1800cac23  lea     rcx, [rsp+148h+var_D8]
0x1800cac28  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cac2d  nop
0x1800cac2e  lea     rdx, sourceString
0x1800cac35  lea     rcx, [rsp+148h+var_B8]
0x1800cac3d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cac42  nop
0x1800cac43  lea     r8, [rsp+148h+var_128]
0x1800cac48  lea     rdx, [rsp+148h+var_D8]
0x1800cac4d  mov     rcx, rax
0x1800cac50  call    ?LookupChildNodesForUri@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@6@@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::LookupChildNodesForUri(std::wstring const &,std::wstring const &,std::vector<std::wstring> &)
0x1800cac55  mov     ebx, eax
0x1800cac57  lea     rcx, [rsp+148h+var_B8]
0x1800cac5f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cac64  nop
0x1800cac65  lea     rcx, [rsp+148h+var_D8]
0x1800cac6a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cac6f  test    ebx, ebx
0x1800cac71  jns     short loc_1800CACAF
0x1800cac73  mov     rcx, [rsp+148h]; this
0x1800cac7b  mov     r9d, ebx; char *
0x1800cac7e  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cac85  mov     edx, 27Eh; void *
0x1800cac8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cac8f  nop
0x1800cac90  lea     rcx, [rsp+148h+var_128]
0x1800cac95  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800cac9a  nop
0x1800cac9b  lea     rcx, [rsp+148h+var_78]
0x1800caca3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800caca8  mov     eax, ebx
0x1800cacaa  jmp     loc_1800CAFDA
0x1800cacaf  xor     r14d, r14d
0x1800cacb2  mov     rsi, [rsp+148h+var_128]
0x1800cacb7  mov     r12, [rsp+148h+var_120]
0x1800cacbc  cmp     rsi, r12
0x1800cacbf  jz      loc_1800CAF9E
0x1800cacc5  lea     r8, S2; "/"
0x1800caccc  lea     rdx, [rsp+148h+var_78]
0x1800cacd4  lea     rcx, [rsp+148h+var_D8]
0x1800cacd9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800cacde  nop
0x1800cacdf  mov     r8, rsi
0x1800cace2  mov     rdx, rax
0x1800cace5  lea     rcx, [rsp+148h+var_98]
0x1800caced  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800cacf2  nop
0x1800cacf3  lea     rcx, [rsp+148h+var_D8]
0x1800cacf8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cacfd  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800cad02  call    cs:__imp_VariantInit
0x1800cad08  nop
0x1800cad09  lea     r8, aInstallationst; "/InstallationState"
0x1800cad10  lea     rdx, [rsp+148h+var_98]
0x1800cad18  lea     rcx, [rsp+148h+var_B8]
0x1800cad20  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800cad25  nop
0x1800cad26  lea     rdx, sourceString
0x1800cad2d  lea     rcx, [rsp+148h+var_D8]
0x1800cad32  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cad37  nop
0x1800cad38  lea     r8, [rsp+148h+pvarg]
0x1800cad3d  lea     rdx, [rsp+148h+var_B8]
0x1800cad45  mov     rcx, rax
0x1800cad48  call    ?TryLookupNodeValue@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAUtagVARIANT@@@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::TryLookupNodeValue(std::wstring const &,std::wstring const &,tagVARIANT *)
0x1800cad4d  mov     ebx, eax
0x1800cad4f  lea     rcx, [rsp+148h+var_D8]
0x1800cad54  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cad59  test    ebx, ebx
0x1800cad5b  jnz     short loc_1800CADC6
0x1800cad5d  mov     rcx, [rsp+148h]; this
0x1800cad65  mov     ebx, 80070490h
0x1800cad6a  mov     r9d, ebx; char *
0x1800cad6d  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cad74  mov     edx, 286h; void *
0x1800cad79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cad7e  nop
0x1800cad7f  lea     rcx, [rsp+148h+var_B8]
0x1800cad87  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cad8c  nop
0x1800cad8d  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800cad92  call    cs:__imp_VariantClear
0x1800cad98  nop
0x1800cad99  lea     rcx, [rsp+148h+var_98]
0x1800cada1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cada6  nop
0x1800cada7  lea     rcx, [rsp+148h+var_128]
0x1800cadac  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800cadb1  nop
0x1800cadb2  lea     rcx, [rsp+148h+var_78]
0x1800cadba  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cadbf  mov     eax, ebx
0x1800cadc1  jmp     loc_1800CAFDA
0x1800cadc6  cmp     word ptr [rsp+148h+pvarg], 3
0x1800cadcc  jz      short loc_1800CAE37
0x1800cadce  mov     rcx, [rsp+148h]; this
0x1800cadd6  mov     ebx, 8000FFFFh
0x1800caddb  mov     r9d, ebx; char *
0x1800cadde  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cade5  mov     edx, 287h; void *
0x1800cadea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cadef  nop
0x1800cadf0  lea     rcx, [rsp+148h+var_B8]
0x1800cadf8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cadfd  nop
0x1800cadfe  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800cae03  call    cs:__imp_VariantClear
0x1800cae09  nop
0x1800cae0a  lea     rcx, [rsp+148h+var_98]
0x1800cae12  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cae17  nop
0x1800cae18  lea     rcx, [rsp+148h+var_128]
0x1800cae1d  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800cae22  nop
0x1800cae23  lea     rcx, [rsp+148h+var_78]
0x1800cae2b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cae30  mov     eax, ebx
0x1800cae32  jmp     loc_1800CAFDA
0x1800cae37  mov     eax, dword ptr [rsp+148h+pvarg+8]
0x1800cae3b  cmp     eax, 1
0x1800cae3e  jnz     loc_1800CB0A2
0x1800cae44  lea     ebx, [rax+1Dh]
0x1800cae47  lea     rcx, [rsp+148h+var_F0]; pvarg
0x1800cae4c  call    cs:__imp_VariantInit
0x1800cae52  nop
0x1800cae53  lea     r8, aTimeout; "/Timeout"
0x1800cae5a  lea     rdx, [rsp+148h+var_98]
0x1800cae62  lea     rcx, [rsp+148h+var_D8]
0x1800cae67  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800cae6c  nop
0x1800cae6d  lea     rdx, sourceString
0x1800cae74  lea     rcx, [rsp+148h+var_58]
0x1800cae7c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cae81  nop
0x1800cae82  lea     r8, [rsp+148h+var_F0]
0x1800cae87  lea     rdx, [rsp+148h+var_D8]
0x1800cae8c  mov     rcx, rax
0x1800cae8f  call    ?TryLookupNodeValue@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAUtagVARIANT@@@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::TryLookupNodeValue(std::wstring const &,std::wstring const &,tagVARIANT *)
0x1800cae94  mov     r15d, eax
0x1800cae97  lea     rcx, [rsp+148h+var_58]
0x1800cae9f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800caea4  test    r15d, r15d
0x1800caea7  jz      loc_1800CAF3D
0x1800caead  cmp     word ptr [rsp+148h+var_F0], 3
0x1800caeb3  jz      loc_1800CAF39
0x1800caeb9  mov     rcx, [rsp+148h]; this
0x1800caec1  mov     ebx, 8000FFFFh
0x1800caec6  mov     r9d, ebx; char *
0x1800caec9  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800caed0  mov     edx, 293h; void *
0x1800caed5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800caeda  nop
0x1800caedb  lea     rcx, [rsp+148h+var_D8]
0x1800caee0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800caee5  nop
0x1800caee6  lea     rcx, [rsp+148h+var_F0]; pvarg
0x1800caeeb  call    cs:__imp_VariantClear
0x1800caef1  nop
0x1800caef2  lea     rcx, [rsp+148h+var_B8]
0x1800caefa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800caeff  nop
0x1800caf00  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800caf05  call    cs:__imp_VariantClear
0x1800caf0b  nop
0x1800caf0c  lea     rcx, [rsp+148h+var_98]
0x1800caf14  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800caf19  nop
0x1800caf1a  lea     rcx, [rsp+148h+var_128]
0x1800caf1f  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800caf24  nop
0x1800caf25  lea     rcx, [rsp+148h+var_78]
0x1800caf2d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800caf32  mov     eax, ebx
0x1800caf34  jmp     loc_1800CAFDA
0x1800caf39  mov     ebx, dword ptr [rsp+148h+var_F0+8]
0x1800caf3d  mov     eax, ebx
0x1800caf3f  imul    rcx, rax, 3Ch ; '<'
0x1800caf43  mov     eax, 0FFFFFFFFh
0x1800caf48  cmp     rcx, rax
0x1800caf4b  ja      loc_1800CB022
0x1800caf51  cmp     r13d, ecx
0x1800caf54  jb      loc_1800CB007
0x1800caf5a  mov     dword ptr [rdi], 1
0x1800caf60  lea     rcx, [rsp+148h+var_D8]
0x1800caf65  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800caf6a  nop
0x1800caf6b  lea     rcx, [rsp+148h+var_F0]; pvarg
0x1800caf70  call    cs:__imp_VariantClear
0x1800caf76  nop
0x1800caf77  lea     rcx, [rsp+148h+var_B8]
0x1800caf7f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800caf84  nop
0x1800caf85  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800caf8a  call    cs:__imp_VariantClear
0x1800caf90  nop
0x1800caf91  lea     rcx, [rsp+148h+var_98]
0x1800caf99  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800caf9e  mov     rcx, [rsp+148h+var_120]
0x1800cafa3  sub     rcx, [rsp+148h+var_128]
0x1800cafa8  sar     rcx, 5
0x1800cafac  mov     eax, r14d
0x1800cafaf  cmp     rax, rcx
0x1800cafb2  jnz     short loc_1800CAFBA
0x1800cafb4  mov     dword ptr [rdi], 1
0x1800cafba  lea     rcx, [rsp+148h+var_128]
0x1800cafbf  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800cafc4  nop
0x1800cafc5  lea     rcx, [rsp+148h+var_78]
0x1800cafcd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cafd2  xor     eax, eax
0x1800cafd4  jmp     short loc_1800CAFDA
0x1800cafd6  mov     eax, [rsp+148h+var_110]
0x1800cafda  mov     rcx, [rsp+148h+var_38]
0x1800cafe2  xor     rcx, rsp; StackCookie
0x1800cafe5  call    __security_check_cookie
0x1800cafea  lea     r11, [rsp+148h+var_28]
0x1800caff2  mov     rbx, [r11+30h]
0x1800caff6  mov     rsi, [r11+40h]
0x1800caffa  mov     rsp, r11
0x1800caffd  pop     r15
0x1800cafff  pop     r14
0x1800cb001  pop     r13
0x1800cb003  pop     r12
0x1800cb005  pop     rdi
0x1800cb006  retn
0x1800cb007  lea     rcx, [rsp+148h+var_D8]
0x1800cb00c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cb011  nop
0x1800cb012  lea     rcx, [rsp+148h+var_F0]; pvarg
0x1800cb017  call    cs:__imp_VariantClear
0x1800cb01d  jmp     loc_1800CB126
0x1800cb022  mov     rcx, [rsp+148h]; this
0x1800cb02a  mov     ebx, 80070216h
0x1800cb02f  mov     r9d, ebx; char *
0x1800cb032  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cb039  mov     edx, 298h; void *
0x1800cb03e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb043  nop
0x1800cb044  lea     rcx, [rsp+148h+var_D8]
0x1800cb049  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cb04e  nop
0x1800cb04f  lea     rcx, [rsp+148h+var_F0]; pvarg
0x1800cb054  call    cs:__imp_VariantClear
0x1800cb05a  nop
0x1800cb05b  lea     rcx, [rsp+148h+var_B8]
0x1800cb063  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cb068  nop
0x1800cb069  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800cb06e  call    cs:__imp_VariantClear
0x1800cb074  nop
0x1800cb075  lea     rcx, [rsp+148h+var_98]
0x1800cb07d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cb082  nop
0x1800cb083  lea     rcx, [rsp+148h+var_128]
0x1800cb088  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800cb08d  nop
0x1800cb08e  lea     rcx, [rsp+148h+var_78]
0x1800cb096  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cb09b  mov     eax, ebx
0x1800cb09d  jmp     loc_1800CAFDA
0x1800cb0a2  cmp     eax, 4
0x1800cb0a5  jnz     short loc_1800CB0B2
0x1800cb0a7  mov     dword ptr [rdi], 1
0x1800cb0ad  jmp     loc_1800CAF77
  ... truncated ...
```
