# EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::HavePolicyProvidersCompletedInstallation(ulong,int &)

- ea: `0x1800cce4c`
- end: `0x1800cd46f`
- name: `?HavePolicyProvidersCompletedInstallation@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@SAJKAEAH@Z`
- size: `1571`
- prototype: `__int64 __fastcall(unsigned int, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a7250`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x18006cb28`
- `0x180077de0`
- `0x180080bac`
- `0x180081624`
- `0x180084574`
- `0x18008ed78`
- `0x1800964d4`
- `0x1800a29ac`
- `0x1800c705c`
- `0x1800cce4c`
- `0x1800cdaac`
- `0x1800cf888`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800ccfca`
- `OLEAUT32!__imp_VariantInit` at `0x1800cd126`
- `OLEAUT32!__imp_VariantInit` at `0x1800ccfca`
- `OLEAUT32!__imp_VariantInit` at `0x1800cd126`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd060`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd0d7`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd1cb`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd1eb`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd25c`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd27c`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd310`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd353`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd373`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd3fa`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd44a`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd060`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd0d7`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd1cb`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd1eb`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd25c`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd27c`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd310`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd353`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd373`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd3fa`
- `OLEAUT32!__imp_VariantClear` at `0x1800cd44a`

## string_xrefs

- `0x1800ccf46`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cd03b`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cd0b2`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cd1a9`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cd331`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cd3d5`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800ccfd7`: `/InstallationState`

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
0x1800cce4c  mov     r11, rsp
0x1800cce4f  mov     [r11+8], rbx
0x1800cce53  mov     [r11+18h], rsi
0x1800cce57  push    rdi
0x1800cce58  push    r12
0x1800cce5a  push    r13
0x1800cce5c  push    r14
0x1800cce5e  push    r15
0x1800cce60  sub     rsp, 120h
0x1800cce67  mov     rax, cs:__security_cookie
0x1800cce6e  xor     rax, rsp
0x1800cce71  mov     [rsp+148h+var_38], rax
0x1800cce79  mov     rdi, rdx
0x1800cce7c  mov     r13d, ecx
0x1800cce7f  mov     dword ptr [rdx], 0
0x1800cce85  lea     rcx, [r11-78h]
0x1800cce89  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cce8e  nop
0x1800cce8f  lea     rdx, aDevice; "./Device"
0x1800cce96  lea     rcx, [rsp+148h+var_78]
0x1800cce9e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800ccea3  lea     rdx, aVendorMsftEnro; "/Vendor/MSFT/EnrollmentStatusTracking"
0x1800cceaa  mov     rcx, rax
0x1800ccead  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800cceb2  lea     rdx, aDevicepreparat_0; "/DevicePreparation"
0x1800cceb9  mov     rcx, rax
0x1800ccebc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800ccec1  lea     rdx, aPolicyprovider; "/PolicyProviders"
0x1800ccec8  mov     rcx, rax
0x1800ccecb  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800cced0  lea     rcx, [rsp+148h+var_128]
0x1800cced5  call    ??$?0V?$allocator@I@std@@$$V@?$_Compressed_pair@V?$allocator@I@std@@V?$_Vector_val@U?$_Simple_types@I@std@@@2@$00@std@@QEAA@U_One_then_variadic_args_t@1@$$QEAV?$allocator@I@1@@Z; std::_Compressed_pair<std::allocator<uint>,std::_Vector_val<std::_Simple_types<uint>>,1>::_Compressed_pair<std::allocator<uint>,std::_Vector_val<std::_Simple_types<uint>>,1>(std::_One_then_variadic_args_t,std::allocator<uint> &&)
0x1800cceda  nop
0x1800ccedb  lea     rcx, [rsp+148h+var_78]
0x1800ccee3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ccee8  mov     rdx, rax
0x1800cceeb  lea     rcx, [rsp+148h+var_D8]
0x1800ccef0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ccef5  nop
0x1800ccef6  lea     rdx, sourceString
0x1800ccefd  lea     rcx, [rsp+148h+var_B8]
0x1800ccf05  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ccf0a  nop
0x1800ccf0b  lea     r8, [rsp+148h+var_128]
0x1800ccf10  lea     rdx, [rsp+148h+var_D8]
0x1800ccf15  mov     rcx, rax
0x1800ccf18  call    ?LookupChildNodesForUri@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@6@@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::LookupChildNodesForUri(std::wstring const &,std::wstring const &,std::vector<std::wstring> &)
0x1800ccf1d  mov     ebx, eax
0x1800ccf1f  lea     rcx, [rsp+148h+var_B8]
0x1800ccf27  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ccf2c  nop
0x1800ccf2d  lea     rcx, [rsp+148h+var_D8]
0x1800ccf32  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ccf37  test    ebx, ebx
0x1800ccf39  jns     short loc_1800CCF77
0x1800ccf3b  mov     rcx, [rsp+148h]; this
0x1800ccf43  mov     r9d, ebx; char *
0x1800ccf46  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800ccf4d  mov     edx, 27Eh; void *
0x1800ccf52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ccf57  nop
0x1800ccf58  lea     rcx, [rsp+148h+var_128]
0x1800ccf5d  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800ccf62  nop
0x1800ccf63  lea     rcx, [rsp+148h+var_78]
0x1800ccf6b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ccf70  mov     eax, ebx
0x1800ccf72  jmp     loc_1800CD2D2
0x1800ccf77  xor     r14d, r14d
0x1800ccf7a  mov     rsi, [rsp+148h+var_128]
0x1800ccf7f  mov     r12, [rsp+148h+var_120]
0x1800ccf84  cmp     rsi, r12
0x1800ccf87  jz      loc_1800CD296
0x1800ccf8d  lea     r8, S2; "/"
0x1800ccf94  lea     rdx, [rsp+148h+var_78]
0x1800ccf9c  lea     rcx, [rsp+148h+var_D8]
0x1800ccfa1  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800ccfa6  nop
0x1800ccfa7  mov     r8, rsi
0x1800ccfaa  mov     rdx, rax
0x1800ccfad  lea     rcx, [rsp+148h+var_98]
0x1800ccfb5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800ccfba  nop
0x1800ccfbb  lea     rcx, [rsp+148h+var_D8]
0x1800ccfc0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ccfc5  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800ccfca  call    cs:__imp_VariantInit
0x1800ccfd1  nop     dword ptr [rax+rax+00h]
0x1800ccfd6  nop
0x1800ccfd7  lea     r8, aInstallationst; "/InstallationState"
0x1800ccfde  lea     rdx, [rsp+148h+var_98]
0x1800ccfe6  lea     rcx, [rsp+148h+var_B8]
0x1800ccfee  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800ccff3  nop
0x1800ccff4  lea     rdx, sourceString
0x1800ccffb  lea     rcx, [rsp+148h+var_D8]
0x1800cd000  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cd005  nop
0x1800cd006  lea     r8, [rsp+148h+pvarg]
0x1800cd00b  lea     rdx, [rsp+148h+var_B8]
0x1800cd013  mov     rcx, rax
0x1800cd016  call    ?TryLookupNodeValue@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAUtagVARIANT@@@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::TryLookupNodeValue(std::wstring const &,std::wstring const &,tagVARIANT *)
0x1800cd01b  mov     ebx, eax
0x1800cd01d  lea     rcx, [rsp+148h+var_D8]
0x1800cd022  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd027  test    ebx, ebx
0x1800cd029  jnz     short loc_1800CD09A
0x1800cd02b  mov     rcx, [rsp+148h]; this
0x1800cd033  mov     ebx, 80070490h
0x1800cd038  mov     r9d, ebx; char *
0x1800cd03b  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cd042  mov     edx, 286h; void *
0x1800cd047  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd04c  nop
0x1800cd04d  lea     rcx, [rsp+148h+var_B8]
0x1800cd055  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd05a  nop
0x1800cd05b  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800cd060  call    cs:__imp_VariantClear
0x1800cd067  nop     dword ptr [rax+rax+00h]
0x1800cd06c  nop
0x1800cd06d  lea     rcx, [rsp+148h+var_98]
0x1800cd075  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd07a  nop
0x1800cd07b  lea     rcx, [rsp+148h+var_128]
0x1800cd080  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800cd085  nop
0x1800cd086  lea     rcx, [rsp+148h+var_78]
0x1800cd08e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd093  mov     eax, ebx
0x1800cd095  jmp     loc_1800CD2D2
0x1800cd09a  cmp     word ptr [rsp+148h+pvarg], 3
0x1800cd0a0  jz      short loc_1800CD111
0x1800cd0a2  mov     rcx, [rsp+148h]; this
0x1800cd0aa  mov     ebx, 8000FFFFh
0x1800cd0af  mov     r9d, ebx; char *
0x1800cd0b2  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cd0b9  mov     edx, 287h; void *
0x1800cd0be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd0c3  nop
0x1800cd0c4  lea     rcx, [rsp+148h+var_B8]
0x1800cd0cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd0d1  nop
0x1800cd0d2  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800cd0d7  call    cs:__imp_VariantClear
0x1800cd0de  nop     dword ptr [rax+rax+00h]
0x1800cd0e3  nop
0x1800cd0e4  lea     rcx, [rsp+148h+var_98]
0x1800cd0ec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd0f1  nop
0x1800cd0f2  lea     rcx, [rsp+148h+var_128]
0x1800cd0f7  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800cd0fc  nop
0x1800cd0fd  lea     rcx, [rsp+148h+var_78]
0x1800cd105  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd10a  mov     eax, ebx
0x1800cd10c  jmp     loc_1800CD2D2
0x1800cd111  mov     eax, dword ptr [rsp+148h+pvarg+8]
0x1800cd115  cmp     eax, 1
0x1800cd118  jnz     loc_1800CD3AD
0x1800cd11e  lea     ebx, [rax+1Dh]
0x1800cd121  lea     rcx, [rsp+148h+var_F0]; pvarg
0x1800cd126  call    cs:__imp_VariantInit
0x1800cd12d  nop     dword ptr [rax+rax+00h]
0x1800cd132  nop
0x1800cd133  lea     r8, aTimeout; "/Timeout"
0x1800cd13a  lea     rdx, [rsp+148h+var_98]
0x1800cd142  lea     rcx, [rsp+148h+var_D8]
0x1800cd147  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800cd14c  nop
0x1800cd14d  lea     rdx, sourceString
0x1800cd154  lea     rcx, [rsp+148h+var_58]
0x1800cd15c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cd161  nop
0x1800cd162  lea     r8, [rsp+148h+var_F0]
0x1800cd167  lea     rdx, [rsp+148h+var_D8]
0x1800cd16c  mov     rcx, rax
0x1800cd16f  call    ?TryLookupNodeValue@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0PEAUtagVARIANT@@@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::TryLookupNodeValue(std::wstring const &,std::wstring const &,tagVARIANT *)
0x1800cd174  mov     r15d, eax
0x1800cd177  lea     rcx, [rsp+148h+var_58]
0x1800cd17f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd184  test    r15d, r15d
0x1800cd187  jz      loc_1800CD229
0x1800cd18d  cmp     word ptr [rsp+148h+var_F0], 3
0x1800cd193  jz      loc_1800CD225
0x1800cd199  mov     rcx, [rsp+148h]; this
0x1800cd1a1  mov     ebx, 8000FFFFh
0x1800cd1a6  mov     r9d, ebx; char *
0x1800cd1a9  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cd1b0  mov     edx, 293h; void *
0x1800cd1b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd1ba  nop
0x1800cd1bb  lea     rcx, [rsp+148h+var_D8]
0x1800cd1c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd1c5  nop
0x1800cd1c6  lea     rcx, [rsp+148h+var_F0]; pvarg
0x1800cd1cb  call    cs:__imp_VariantClear
0x1800cd1d2  nop     dword ptr [rax+rax+00h]
0x1800cd1d7  nop
0x1800cd1d8  lea     rcx, [rsp+148h+var_B8]
0x1800cd1e0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd1e5  nop
0x1800cd1e6  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800cd1eb  call    cs:__imp_VariantClear
0x1800cd1f2  nop     dword ptr [rax+rax+00h]
0x1800cd1f7  nop
0x1800cd1f8  lea     rcx, [rsp+148h+var_98]
0x1800cd200  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd205  nop
0x1800cd206  lea     rcx, [rsp+148h+var_128]
0x1800cd20b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800cd210  nop
0x1800cd211  lea     rcx, [rsp+148h+var_78]
0x1800cd219  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd21e  mov     eax, ebx
0x1800cd220  jmp     loc_1800CD2D2
0x1800cd225  mov     ebx, dword ptr [rsp+148h+var_F0+8]
0x1800cd229  mov     eax, ebx
0x1800cd22b  imul    rcx, rax, 3Ch ; '<'
0x1800cd22f  mov     eax, 0FFFFFFFFh
0x1800cd234  cmp     rcx, rax
0x1800cd237  ja      loc_1800CD321
0x1800cd23d  cmp     r13d, ecx
0x1800cd240  jb      loc_1800CD300
0x1800cd246  mov     dword ptr [rdi], 1
0x1800cd24c  lea     rcx, [rsp+148h+var_D8]
0x1800cd251  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd256  nop
0x1800cd257  lea     rcx, [rsp+148h+var_F0]; pvarg
0x1800cd25c  call    cs:__imp_VariantClear
0x1800cd263  nop     dword ptr [rax+rax+00h]
0x1800cd268  nop
0x1800cd269  lea     rcx, [rsp+148h+var_B8]
0x1800cd271  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd276  nop
0x1800cd277  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800cd27c  call    cs:__imp_VariantClear
0x1800cd283  nop     dword ptr [rax+rax+00h]
0x1800cd288  nop
0x1800cd289  lea     rcx, [rsp+148h+var_98]
0x1800cd291  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd296  mov     rcx, [rsp+148h+var_120]
0x1800cd29b  sub     rcx, [rsp+148h+var_128]
0x1800cd2a0  sar     rcx, 5
0x1800cd2a4  mov     eax, r14d
0x1800cd2a7  cmp     rax, rcx
0x1800cd2aa  jnz     short loc_1800CD2B2
0x1800cd2ac  mov     dword ptr [rdi], 1
0x1800cd2b2  lea     rcx, [rsp+148h+var_128]
0x1800cd2b7  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800cd2bc  nop
0x1800cd2bd  lea     rcx, [rsp+148h+var_78]
0x1800cd2c5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd2ca  xor     eax, eax
0x1800cd2cc  jmp     short loc_1800CD2D2
0x1800cd2ce  mov     eax, [rsp+148h+var_110]
0x1800cd2d2  mov     rcx, [rsp+148h+var_38]
0x1800cd2da  xor     rcx, rsp; StackCookie
0x1800cd2dd  call    __security_check_cookie
0x1800cd2e2  lea     r11, [rsp+148h+var_28]
0x1800cd2ea  mov     rbx, [r11+30h]
0x1800cd2ee  mov     rsi, [r11+40h]
0x1800cd2f2  mov     rsp, r11
0x1800cd2f5  pop     r15
0x1800cd2f7  pop     r14
0x1800cd2f9  pop     r13
0x1800cd2fb  pop     r12
0x1800cd2fd  pop     rdi
0x1800cd2fe  retn
0x1800cd300  lea     rcx, [rsp+148h+var_D8]
0x1800cd305  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd30a  nop
0x1800cd30b  lea     rcx, [rsp+148h+var_F0]; pvarg
0x1800cd310  call    cs:__imp_VariantClear
0x1800cd317  nop     dword ptr [rax+rax+00h]
0x1800cd31c  jmp     loc_1800CD437
0x1800cd321  mov     rcx, [rsp+148h]; this
0x1800cd329  mov     ebx, 80070216h
0x1800cd32e  mov     r9d, ebx; char *
0x1800cd331  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cd338  mov     edx, 298h; void *
0x1800cd33d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd342  nop
0x1800cd343  lea     rcx, [rsp+148h+var_D8]
0x1800cd348  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd34d  nop
0x1800cd34e  lea     rcx, [rsp+148h+var_F0]; pvarg
0x1800cd353  call    cs:__imp_VariantClear
0x1800cd35a  nop     dword ptr [rax+rax+00h]
0x1800cd35f  nop
0x1800cd360  lea     rcx, [rsp+148h+var_B8]
0x1800cd368  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd36d  nop
0x1800cd36e  lea     rcx, [rsp+148h+pvarg]; pvarg
0x1800cd373  call    cs:__imp_VariantClear
0x1800cd37a  nop     dword ptr [rax+rax+00h]
0x1800cd37f  nop
0x1800cd380  lea     rcx, [rsp+148h+var_98]
0x1800cd388  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd38d  nop
  ... truncated ...
```
