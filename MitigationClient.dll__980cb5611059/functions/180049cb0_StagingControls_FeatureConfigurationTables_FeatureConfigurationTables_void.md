# StagingControls::FeatureConfigurationTables::FeatureConfigurationTables(void)

- ea: `0x180049cb0`
- end: `0x180049e67`
- name: `??0FeatureConfigurationTables@StagingControls@@QEAA@XZ`
- size: `439`
- prototype: `StagingControls::FeatureConfigurationTables *__fastcall(StagingControls::FeatureConfigurationTables *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x1800312bc`

## callees

- `0x18000a704`
- `0x18003330c`
- `0x1800335c0`
- `0x18003c970`
- `0x180047070`
- `0x1800490a0`
- `0x180049b78`
- `0x180049cb0`
- `0x18004a158`
- `0x18004a240`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180049cfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180049cfe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180049d1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180049d32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180049d1e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180049d32`

## string_xrefs

- `0x180049cf7`: `ntdll.dll`
- `0x180049d28`: `RtlQueryAllInternalFeatureConfigurations`
- `0x180049d14`: `RtlQueryAllInternalRuntimeFeatureConfigurations`
- `0x180049e55`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\featureconfigurationtables.cpp`

## pseudocode

```c
StagingControls::FeatureConfigurationTables *__fastcall StagingControls::FeatureConfigurationTables::FeatureConfigurationTables(
        StagingControls::FeatureConfigurationTables *this)
{
  HMODULE ModuleHandleW; // rax
  const char *v3; // r9
  HMODULE v4; // r14
  _QWORD *v5; // rax
  void *v6; // rax
  __int64 v7; // rax
  std::_Ref_count_base *v8; // rcx
  _QWORD *v9; // rax
  std::_Ref_count_base *v11[2]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v12; // [rsp+40h] [rbp-30h] BYREF
  std::_Ref_count_base *v13; // [rsp+48h] [rbp-28h]
  __int128 v14; // [rsp+50h] [rbp-20h] BYREF
  __int64 v15; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  __int64 v17; // [rsp+90h] [rbp+20h] BYREF
  __int64 v18; // [rsp+98h] [rbp+28h] BYREF

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  v4 = ModuleHandleW;
  if ( !ModuleHandleW )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)8,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\featureconfigurationtables.cpp",
      v3);
  *((_QWORD *)this + 6) = GetProcAddress(ModuleHandleW, "RtlQueryAllInternalRuntimeFeatureConfigurations");
  *((_QWORD *)this + 7) = GetProcAddress(v4, "RtlQueryAllInternalFeatureConfigurations");
  v14 = 0;
  v15 = 0;
  *(_OWORD *)v11 = 0;
  v18 = 0;
  v17 = 0;
  if ( (unsigned __int8)StagingControls::FeatureConfigurationTables::GetAllRuntimeConfigurations(
                          (_DWORD)this,
                          (unsigned int)&v17,
                          (unsigned int)v11,
                          (unsigned int)&v18,
                          (__int64)&v14) )
  {
    v5 = std::make_shared<StagingControls::FeatureOverrides,std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> &,unsigned __int64 &>(
           &v12,
           (__int64)&v14,
           &v17);
    std::shared_ptr<StagingControls::FeatureOverrides>::operator=((char *)this + 16, v5);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    v6 = operator new(0x58u);
    v7 = std::_Ref_count_obj2<StagingControls::GovernedFeaturesTable>::_Ref_count_obj2<StagingControls::GovernedFeaturesTable>(
           v6,
           &v18,
           v11,
           &v17);
    *(_QWORD *)this = v7 + 16;
    v8 = (std::_Ref_count_base *)*((_QWORD *)this + 1);
    *((_QWORD *)this + 1) = v7;
    if ( v8 )
      std::_Ref_count_base::_Decref(v8);
  }
  if ( (unsigned __int8)StagingControls::FeatureConfigurationTables::GetAllBootConfigurations(this, &v17, &v14) )
  {
    v9 = std::make_shared<StagingControls::FeatureOverrides,std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> &,unsigned __int64 &>(
           &v12,
           (__int64)&v14,
           &v17);
    std::shared_ptr<StagingControls::FeatureOverrides>::operator=((char *)this + 32, v9);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
  }
  if ( v11[1] )
    std::_Ref_count_base::_Decref(v11[1]);
  std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::_Tidy(&v14);
  return this;
}

```

## disassembly

```asm
0x180049cb0  mov     [rsp-18h+arg_10], rbx
0x180049cb5  mov     [rsp-18h+arg_18], rsi
0x180049cba  push    rbp
0x180049cbb  push    rdi
0x180049cbc  push    r14
0x180049cbe  mov     rbp, rsp
0x180049cc1  sub     rsp, 70h
0x180049cc5  mov     rbx, rcx
0x180049cc8  mov     qword ptr [rcx], 0
0x180049ccf  mov     qword ptr [rcx+8], 0
0x180049cd7  mov     qword ptr [rcx+10h], 0
0x180049cdf  mov     qword ptr [rcx+18h], 0
0x180049ce7  mov     qword ptr [rcx+20h], 0
0x180049cef  mov     qword ptr [rcx+28h], 0
0x180049cf7  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180049cfe  call    cs:__imp_GetModuleHandleW
0x180049d04  mov     r14, rax
0x180049d07  mov     rcx, [rbp+18h]; this
0x180049d0b  test    rax, rax
0x180049d0e  jz      loc_180049E55
0x180049d14  lea     rdx, aRtlqueryallint_0; "RtlQueryAllInternalRuntimeFeatureConfig"...
0x180049d1b  mov     rcx, rax; hModule
0x180049d1e  call    cs:__imp_GetProcAddress
0x180049d24  mov     [rbx+30h], rax
0x180049d28  lea     rdx, aRtlqueryallint; "RtlQueryAllInternalFeatureConfiguration"...
0x180049d2f  mov     rcx, r14; hModule
0x180049d32  call    cs:__imp_GetProcAddress
0x180049d38  mov     [rbx+38h], rax
0x180049d3c  xorps   xmm0, xmm0
0x180049d3f  movdqu  [rbp+var_20], xmm0
0x180049d44  mov     [rbp+var_10], 0
0x180049d4c  xorps   xmm1, xmm1
0x180049d4f  movdqu  xmmword ptr [rbp+var_40], xmm1
0x180049d54  mov     [rbp+arg_8], 0
0x180049d5c  mov     [rbp+arg_0], 0
0x180049d64  lea     rax, [rbp+var_20]
0x180049d68  mov     [rsp+70h+var_50], rax
0x180049d6d  lea     r9, [rbp+arg_8]
0x180049d71  lea     r8, [rbp+var_40]
0x180049d75  lea     rdx, [rbp+arg_0]
0x180049d79  mov     rcx, rbx
0x180049d7c  call    ?GetAllRuntimeConfigurations@FeatureConfigurationTables@StagingControls@@AEAA_NAEA_KAEAV?$shared_ptr@E@std@@0AEAV?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@4@@Z; StagingControls::FeatureConfigurationTables::GetAllRuntimeConfigurations(unsigned __int64 &,std::shared_ptr<uchar> &,unsigned __int64 &,std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> &)
0x180049d81  test    al, al
0x180049d83  jz      short loc_180049DE7
0x180049d85  lea     r8, [rbp+arg_0]
0x180049d89  lea     rdx, [rbp+var_20]
0x180049d8d  lea     rcx, [rbp+var_30]
0x180049d91  call    ??$make_shared@VFeatureOverrides@StagingControls@@AEAV?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@AEA_K@std@@YA?AV?$shared_ptr@VFeatureOverrides@StagingControls@@@0@AEAV?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@0@AEA_K@Z; std::make_shared<StagingControls::FeatureOverrides,std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> &,unsigned __int64 &>(std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> &,unsigned __int64 &)
0x180049d96  mov     rdx, rax
0x180049d99  lea     rcx, [rbx+10h]
0x180049d9d  call    ??4?$shared_ptr@VFeatureOverrides@StagingControls@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<StagingControls::FeatureOverrides>::operator=(std::shared_ptr<StagingControls::FeatureOverrides> &&)
0x180049da2  mov     rcx, [rbp+var_28]; this
0x180049da6  test    rcx, rcx
0x180049da9  jz      short loc_180049DB0
0x180049dab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049db0  mov     ecx, 58h ; 'X'; Size
0x180049db5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049dba  lea     r9, [rbp+arg_0]
0x180049dbe  lea     r8, [rbp+var_40]
0x180049dc2  lea     rdx, [rbp+arg_8]
0x180049dc6  mov     rcx, rax
0x180049dc9  call    ??$?0AEA_KAEAV?$shared_ptr@E@std@@AEA_K@?$_Ref_count_obj2@VGovernedFeaturesTable@StagingControls@@@std@@QEAA@AEA_KAEAV?$shared_ptr@E@1@0@Z; std::_Ref_count_obj2<StagingControls::GovernedFeaturesTable>::_Ref_count_obj2<StagingControls::GovernedFeaturesTable>(unsigned __int64 &,std::shared_ptr<uchar> &,unsigned __int64 &)
0x180049dce  lea     rcx, [rax+10h]
0x180049dd2  mov     [rbx], rcx
0x180049dd5  mov     rcx, [rbx+8]; this
0x180049dd9  mov     [rbx+8], rax
0x180049ddd  test    rcx, rcx
0x180049de0  jz      short loc_180049DE7
0x180049de2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049de7  lea     r8, [rbp+var_20]
0x180049deb  lea     rdx, [rbp+arg_0]
0x180049def  mov     rcx, rbx
0x180049df2  call    ?GetAllBootConfigurations@FeatureConfigurationTables@StagingControls@@AEAA_NAEA_KAEAV?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@@Z; StagingControls::FeatureConfigurationTables::GetAllBootConfigurations(unsigned __int64 &,std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> &)
0x180049df7  test    al, al
0x180049df9  jz      short loc_180049E26
0x180049dfb  lea     r8, [rbp+arg_0]
0x180049dff  lea     rdx, [rbp+var_20]
0x180049e03  lea     rcx, [rbp+var_30]
0x180049e07  call    ??$make_shared@VFeatureOverrides@StagingControls@@AEAV?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@AEA_K@std@@YA?AV?$shared_ptr@VFeatureOverrides@StagingControls@@@0@AEAV?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@0@AEA_K@Z; std::make_shared<StagingControls::FeatureOverrides,std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> &,unsigned __int64 &>(std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> &,unsigned __int64 &)
0x180049e0c  mov     rdx, rax
0x180049e0f  lea     rcx, [rbx+20h]
0x180049e13  call    ??4?$shared_ptr@VFeatureOverrides@StagingControls@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<StagingControls::FeatureOverrides>::operator=(std::shared_ptr<StagingControls::FeatureOverrides> &&)
0x180049e18  mov     rcx, [rbp+var_28]; this
0x180049e1c  test    rcx, rcx
0x180049e1f  jz      short loc_180049E26
0x180049e21  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049e26  mov     rcx, [rbp+var_40+8]; this
0x180049e2a  test    rcx, rcx
0x180049e2d  jz      short loc_180049E34
0x180049e2f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180049e34  lea     rcx, [rbp+var_20]
0x180049e38  call    ?_Tidy@?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@AEAAXXZ; std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::_Tidy(void)
0x180049e3d  mov     rax, rbx
0x180049e40  lea     r11, [rsp+70h+var_s0]
0x180049e45  mov     rbx, [r11+30h]
0x180049e49  mov     rsi, [r11+38h]
0x180049e4d  mov     rsp, r11
0x180049e50  pop     r14
0x180049e52  pop     rdi
0x180049e53  pop     rbp
0x180049e54  retn
0x180049e55  lea     r8, aOnecoreBaseFli; "onecore\\base\\flighting\\featuremanage"...
0x180049e5c  mov     edx, 8; void *
0x180049e61  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
