# DeviceConfiguration::DeviceInstaller::_AddPrinter(std::shared_ptr<DeviceConfiguration::Device>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180015088`
- end: `0x1800153b3`
- name: `?_AddPrinter@DeviceInstaller@DeviceConfiguration@@AEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z`
- size: `811`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180014e28`

## callees

- `0x1800020c0`
- `0x180002b28`
- `0x18000aeac`
- `0x18000af54`
- `0x18000b7f8`
- `0x18000b838`
- `0x18000ea68`
- `0x18000f6c4`
- `0x1800115a0`
- `0x180011664`
- `0x18001436c`
- `0x18001442c`
- `0x18001467c`
- `0x1800146a0`
- `0x180015088`
- `0x180015678`

## import_xrefs

- `WINSPOOL!AddPrinterW` at `0x180015282`
- `WINSPOOL!AddPrinterW` at `0x180015282`

## string_xrefs

- `0x1800152a7`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\deviceinstaller.cpp`
- `0x1800152d9`: `DeviceConfiguration::DeviceInstaller::_AddPrinter`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceInstaller::_AddPrinter(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v5; // r8
  _QWORD *v6; // rax
  __int64 v7; // rcx
  int *v8; // rax
  _QWORD *v9; // rax
  const wchar_t *v10; // rax
  const wchar_t *v11; // rdx
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // r8
  HANDLE v18; // rbx
  _QWORD *v19; // r8
  __int64 v20; // r8
  __int64 v21; // rdx
  const char *v22; // r9
  std::_Ref_count_base *v23; // rcx
  __int64 result; // rax
  std::_Ref_count_base *v25; // rcx
  unsigned int v26[4]; // [rsp+30h] [rbp-768h] BYREF
  _QWORD *v27; // [rsp+40h] [rbp-758h]
  BYTE pPrinter[8]; // [rsp+50h] [rbp-748h] BYREF
  _QWORD *v29; // [rsp+58h] [rbp-740h]
  int *v30; // [rsp+60h] [rbp-738h]
  _QWORD *v31; // [rsp+68h] [rbp-730h]
  const wchar_t *v32; // [rsp+70h] [rbp-728h]
  _QWORD *v33; // [rsp+78h] [rbp-720h]
  _QWORD *v34; // [rsp+80h] [rbp-718h]
  __int64 v35; // [rsp+98h] [rbp-700h]
  const wchar_t *v36; // [rsp+A0h] [rbp-6F8h]
  _BYTE *v37; // [rsp+A8h] [rbp-6F0h]
  __int64 v38; // [rsp+B0h] [rbp-6E8h]
  int v39; // [rsp+B8h] [rbp-6E0h]
  _QWORD v40[3]; // [rsp+E0h] [rbp-6B8h] BYREF
  unsigned __int64 v41; // [rsp+F8h] [rbp-6A0h]
  _QWORD v42[4]; // [rsp+100h] [rbp-698h] BYREF
  _QWORD v43[4]; // [rsp+120h] [rbp-678h] BYREF
  _QWORD v44[4]; // [rsp+140h] [rbp-658h] BYREF
  _BYTE v45[1568]; // [rsp+160h] [rbp-638h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+798h] [rbp+0h]

  try
  {
    v27 = a2;
    DeviceConfiguration::Device::GetPrinterName(*a2, v40);
    DeviceConfiguration::Device::GetPortName(*a2, v44);
    std::wstring::wstring(v43, *a2 + 96LL);
    std::wstring::wstring(v42, *a2 + 128LL);
    memset_0(pPrinter, 0, 0x88u);
    v6 = v40;
    if ( v41 > 7 )
      v6 = (_QWORD *)v40[0];
    v29 = v6;
    v7 = *a2;
    v8 = &dword_180019E84;
    if ( *(_DWORD *)(*a2 + 244LL) == 3 )
      v8 = 0;
    v30 = v8;
    v9 = v44;
    if ( v44[3] > 7u )
      v9 = (_QWORD *)v44[0];
    v31 = v9;
    v10 = L"Microsoft IPP Class Driver";
    v11 = L"Universal Print Class Driver";
    if ( *(_DWORD *)(v7 + 248) )
      v10 = L"Universal Print Class Driver";
    v32 = v10;
    v12 = v43;
    if ( v43[3] > 7u )
      v12 = (_QWORD *)v43[0];
    v34 = v12;
    v13 = v42;
    if ( v42[3] > 7u )
      v13 = (_QWORD *)v42[0];
    v33 = v13;
    v35 = 0;
    v36 = L"RAW";
    v39 = *(_DWORD *)(v7 + 260);
    v38 = 0;
    if ( a3[2] )
    {
      if ( a3[3] <= 7u )
        v14 = a3;
      else
        v14 = (_QWORD *)*a3;
      v29 = v14;
      LOBYTE(v5) = 3;
      LOBYTE(v11) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetImpl'::`2'::impl,
        v11,
        v5);
      std::wstring::operator=(v40, a3);
    }
    memset_0(v45, 0, 0x618u);
    v15 = std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(v26, a2);
    DeviceConfiguration::DeviceInstaller::_FillPrinterParameters(v16, v15, v17, v45);
    v37 = v45;
    v18 = AddPrinterW(0, 2u, pPrinter);
    *(_QWORD *)v26 = v18;
    wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(
      retaddr,
      151,
      "printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
      v18,
      "AddPrinter failed!");
    v19 = v40;
    if ( v41 > 7 )
      v19 = (_QWORD *)v40[0];
    DeviceConfigurationTelemetry::WriteDbgTraceInfo(
      "DeviceConfiguration::DeviceInstaller::_AddPrinter",
      L"Printer %ws added successfully",
      v19);
    LOBYTE(v20) = 3;
    LOBYTE(v21) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetImpl'::`2'::impl,
      v21,
      v20);
    std::wstring::operator=(*a2 + 32LL, v40);
    *(_QWORD *)v26 = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      *a2 + 264LL,
      v18);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v26);
    std::wstring::_Tidy_deallocate(v42);
    std::wstring::_Tidy_deallocate(v43);
    std::wstring::_Tidy_deallocate(v44);
    std::wstring::_Tidy_deallocate(v40);
    v23 = (std::_Ref_count_base *)a2[1];
    if ( v23 )
      std::_Ref_count_base::_Decref(v23);
    result = 0;
  }
  catch ( ... )
  {
    v26[0] = wil::details::in1diag3::Return_CaughtException(
               retaddr,
               (void *)0xA3,
               (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\deviceinstaller.cpp",
               v22);
    v25 = (std::_Ref_count_base *)v27[1];
    if ( v25 )
      std::_Ref_count_base::_Decref(v25);
    return v26[0];
  }
  return result;
}

```

## disassembly

```asm
0x180015088  mov     [rsp+arg_0], rbx
0x18001508d  mov     [rsp+arg_18], rsi
0x180015092  push    rdi
0x180015093  sub     rsp, 790h
0x18001509a  mov     rax, cs:__security_cookie
0x1800150a1  xor     rax, rsp
0x1800150a4  mov     [rsp+798h+var_18], rax
0x1800150ac  mov     rbx, r8
0x1800150af  mov     rdi, rdx
0x1800150b2  mov     [rsp+798h+var_758], rdx
0x1800150b7  xor     esi, esi
0x1800150b9  lea     rdx, [rsp+798h+var_6B8]
0x1800150c1  mov     rcx, [rdi]
0x1800150c4  call    ?GetPrinterName@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetPrinterName(void)
0x1800150c9  nop
0x1800150ca  lea     rdx, [rsp+798h+var_658]
0x1800150d2  mov     rcx, [rdi]
0x1800150d5  call    ?GetPortName@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetPortName(void)
0x1800150da  nop
0x1800150db  mov     rdx, [rdi]
0x1800150de  add     rdx, 60h ; '`'
0x1800150e2  lea     rcx, [rsp+798h+var_678]
0x1800150ea  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800150ef  nop
0x1800150f0  mov     rdx, [rdi]
0x1800150f3  sub     rdx, 0FFFFFFFFFFFFFF80h
0x1800150f7  lea     rcx, [rsp+798h+var_698]
0x1800150ff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180015104  nop
0x180015105  xor     edx, edx; Val
0x180015107  mov     r8d, 88h; Size
0x18001510d  lea     rcx, [rsp+798h+pPrinter]; void *
0x180015112  call    memset_0
0x180015117  lea     rax, [rsp+798h+var_6B8]
0x18001511f  cmp     [rsp+798h+var_6A0], 7
0x180015128  cmova   rax, [rsp+798h+var_6B8]
0x180015131  mov     [rsp+798h+var_740], rax
0x180015136  mov     rcx, [rdi]
0x180015139  lea     rax, dword_180019E84
0x180015140  cmp     dword ptr [rcx+0F4h], 3
0x180015147  cmovz   rax, rsi
0x18001514b  mov     [rsp+798h+var_738], rax
0x180015150  lea     rax, [rsp+798h+var_658]
0x180015158  cmp     [rsp+798h+var_640], 7
0x180015161  cmova   rax, [rsp+798h+var_658]
0x18001516a  mov     [rsp+798h+var_730], rax
0x18001516f  lea     rax, aMicrosoftIppCl; "Microsoft IPP Class Driver"
0x180015176  lea     rdx, aUniversalPrint; "Universal Print Class Driver"
0x18001517d  cmp     [rcx+0F8h], esi
0x180015183  cmovnz  rax, rdx
0x180015187  mov     [rsp+798h+var_728], rax
0x18001518c  lea     rax, [rsp+798h+var_678]
0x180015194  cmp     [rsp+798h+var_660], 7
0x18001519d  cmova   rax, [rsp+798h+var_678]
0x1800151a6  mov     [rsp+798h+var_718], rax
0x1800151ae  lea     rax, [rsp+798h+var_698]
0x1800151b6  cmp     [rsp+798h+var_680], 7
0x1800151bf  cmova   rax, [rsp+798h+var_698]
0x1800151c8  mov     [rsp+798h+var_720], rax
0x1800151cd  mov     [rsp+798h+var_700], rsi
0x1800151d5  lea     rax, aRaw; "RAW"
0x1800151dc  mov     [rsp+798h+var_6F8], rax
0x1800151e4  mov     eax, [rcx+104h]
0x1800151ea  mov     [rsp+798h+var_6E0], eax
0x1800151f1  mov     [rsp+798h+var_6E8], rsi
0x1800151f9  cmp     [rbx+10h], rsi
0x1800151fd  jz      short loc_180015234
0x1800151ff  cmp     qword ptr [rbx+18h], 7
0x180015204  jbe     short loc_18001520B
0x180015206  mov     rax, [rbx]
0x180015209  jmp     short loc_18001520E
0x18001520b  mov     rax, rbx
0x18001520e  mov     [rsp+798h+var_740], rax
0x180015213  mov     r8b, 3
0x180015216  mov     dl, 1
0x180015218  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api> `wil::Feature<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetImpl(void)'::`2'::impl
0x18001521f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180015224  mov     rdx, rbx
0x180015227  lea     rcx, [rsp+798h+var_6B8]
0x18001522f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180015234  xor     edx, edx; Val
0x180015236  mov     r8d, 618h; Size
0x18001523c  lea     rcx, [rsp+798h+var_638]; void *
0x180015244  call    memset_0
0x180015249  mov     rdx, rdi
0x18001524c  lea     rcx, [rsp+798h+var_768]
0x180015251  call    ??0?$shared_ptr@VDeviceManager@DeviceConfiguration@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(std::shared_ptr<DeviceConfiguration::DeviceManager> const &)
0x180015256  lea     r9, [rsp+798h+var_638]
0x18001525e  mov     rdx, rax
0x180015261  call    ?_FillPrinterParameters@DeviceInstaller@DeviceConfiguration@@AEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@_KPEAG@Z; DeviceConfiguration::DeviceInstaller::_FillPrinterParameters(std::shared_ptr<DeviceConfiguration::Device>,unsigned __int64,ushort *)
0x180015266  lea     rax, [rsp+798h+var_638]
0x18001526e  mov     [rsp+798h+var_6F0], rax
0x180015276  lea     r8, [rsp+798h+pPrinter]; pPrinter
0x18001527b  mov     edx, 2; Level
0x180015280  xor     ecx, ecx; pName
0x180015282  call    cs:__imp_AddPrinterW
0x180015288  mov     rbx, rax
0x18001528b  mov     qword ptr [rsp+798h+var_768], rax
0x180015290  mov     rcx, [rsp+798h]
0x180015298  lea     rax, aAddprinterFail_0; "AddPrinter failed!"
0x18001529f  mov     [rsp+798h+var_778], rax
0x1800152a4  mov     r9, rbx
0x1800152a7  lea     r8, aPrintscanPrint_5; "printscan\\print\\spooler\\configuratio"...
0x1800152ae  mov     edx, 97h
0x1800152b3  call    ??$Throw_GetLastErrorIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBD01ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<void *,0>(void *,uint,char const *,void *,char const *,...)
0x1800152b8  lea     r8, [rsp+798h+var_6B8]
0x1800152c0  cmp     [rsp+798h+var_6A0], 7
0x1800152c9  cmova   r8, [rsp+798h+var_6B8]
0x1800152d2  lea     rdx, aPrinterWsAdded; "Printer %ws added successfully"
0x1800152d9  lea     rcx, aDeviceconfigur_14; "DeviceConfiguration::DeviceInstaller::_"...
0x1800152e0  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800152e5  mov     r8b, 3
0x1800152e8  mov     dl, 1
0x1800152ea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api> `wil::Feature<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetImpl(void)'::`2'::impl
0x1800152f1  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800152f6  mov     rcx, [rdi]
0x1800152f9  add     rcx, 20h ; ' '
0x1800152fd  lea     rdx, [rsp+798h+var_6B8]
0x180015305  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001530a  mov     qword ptr [rsp+798h+var_768], rsi
0x18001530f  mov     rcx, [rdi]
0x180015312  add     rcx, 108h
0x180015319  mov     rdx, rbx
0x18001531c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180015321  nop
0x180015322  lea     rcx, [rsp+798h+var_768]
0x180015327  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001532c  nop
0x18001532d  lea     rcx, [rsp+798h+var_698]
0x180015335  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001533a  nop
0x18001533b  lea     rcx, [rsp+798h+var_678]
0x180015343  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015348  nop
0x180015349  lea     rcx, [rsp+798h+var_658]
0x180015351  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015356  nop
0x180015357  lea     rcx, [rsp+798h+var_6B8]
0x18001535f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015364  nop
0x180015365  mov     rcx, [rdi+8]; this
0x180015369  test    rcx, rcx
0x18001536c  jz      short loc_180015373
0x18001536e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015373  xor     eax, eax
0x180015375  jmp     short loc_18001538E
0x180015377  mov     rax, [rsp+798h+var_758]
0x18001537c  mov     rcx, [rax+8]; this
0x180015380  test    rcx, rcx
0x180015383  jz      short loc_18001538A
0x180015385  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001538a  mov     eax, [rsp+798h+var_768]
0x18001538e  mov     rcx, [rsp+798h+var_18]
0x180015396  xor     rcx, rsp; StackCookie
0x180015399  call    __security_check_cookie
0x18001539e  lea     r11, [rsp+798h+var_8]
0x1800153a6  mov     rbx, [r11+10h]
0x1800153aa  mov     rsi, [r11+28h]
0x1800153ae  mov     rsp, r11
0x1800153b1  pop     rdi
0x1800153b2  retn
```
