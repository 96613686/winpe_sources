# DeviceConfiguration::DeviceInstaller::InstallPrintQueue(std::shared_ptr<DeviceConfiguration::Device>)

- ea: `0x180014e28`
- end: `0x180014f77`
- name: `?InstallPrintQueue@DeviceInstaller@DeviceConfiguration@@QEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@Z`
- size: `335`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x180010ca4`

## callees

- `0x1800020c0`
- `0x18000ae04`
- `0x18000af54`
- `0x18000b838`
- `0x18000f6c4`
- `0x1800115a0`
- `0x180014e28`
- `0x180015088`
- `0x180015d8c`
- `0x180015e58`

## string_xrefs

- `0x180014efa`: `DeviceConfiguration::DeviceInstaller::InstallPrintQueue`
- `0x180014f1d`: `DeviceConfiguration::DeviceInstaller::InstallPrintQueue`
- `0x180014f13`: `_PreAddPrinter failed with hr: 0x%x`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceInstaller::InstallPrintQueue(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  char v4; // r14
  unsigned int v5; // esi
  __m128i si128; // xmm6
  __int64 v7; // rax
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rcx
  int v17; // eax
  std::_Ref_count_base *v18; // rcx
  _BYTE v20[16]; // [rsp+38h] [rbp-29h] BYREF
  _BYTE v21[16]; // [rsp+48h] [rbp-19h] BYREF
  _BYTE v22[16]; // [rsp+58h] [rbp-9h] BYREF
  _OWORD v23[2]; // [rsp+68h] [rbp+7h] BYREF

  v3 = 0;
  v4 = 0;
  v5 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  do
  {
    if ( v4 )
      break;
    v23[0] = 0;
    v23[1] = si128;
    LOWORD(v23[0]) = 0;
    v7 = std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(v20, a2);
    v9 = DeviceConfiguration::DeviceInstaller::_PreAddPrinter(v8, v7, v23);
    v3 = v9;
    if ( v9 < 0 )
    {
      DeviceConfigurationTelemetry::WriteDbgTraceError(
        "DeviceConfiguration::DeviceInstaller::InstallPrintQueue",
        L"_PreAddPrinter failed with hr: 0x%x",
        (unsigned int)v9);
    }
    else
    {
      v10 = std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(v21, a2);
      v12 = DeviceConfiguration::DeviceInstaller::_AddPrinter(v11, v10, v23);
      v3 = v12;
      if ( v12 < 0 )
      {
        DeviceConfigurationTelemetry::WriteDbgTraceError(
          "DeviceConfiguration::DeviceInstaller::InstallPrintQueue",
          L"_AddPrinter failed with hr: 0x%x",
          (unsigned int)v12);
      }
      else
      {
        v4 = 1;
        LOBYTE(v14) = 3;
        LOBYTE(v13) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetImpl'::`2'::impl,
          v13,
          v14);
        v15 = std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(
                v22,
                a2);
        v17 = DeviceConfiguration::DeviceInstaller::_PostAddPrinter(v16, v15);
        v3 = v17;
        if ( v17 < 0 )
        {
          DeviceConfigurationTelemetry::WriteDbgTraceError(
            "DeviceConfiguration::DeviceInstaller::InstallPrintQueue",
            L"_PostAddPrinter failed with hr: 0x%x",
            (unsigned int)v17);
          v3 = 0;
        }
      }
    }
    std::wstring::_Tidy_deallocate(v23);
    ++v5;
  }
  while ( v5 < 5 );
  v18 = *(std::_Ref_count_base **)(a2 + 8);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  return v3;
}

```

## disassembly

```asm
0x180014e28  mov     rax, rsp
0x180014e2b  mov     [rax+8], rbx
0x180014e2f  mov     [rax+18h], rsi
0x180014e33  push    rbp
0x180014e34  push    rdi
0x180014e35  push    r14
0x180014e37  lea     rbp, [rax-5Fh]
0x180014e3b  sub     rsp, 0A0h
0x180014e42  movaps  xmmword ptr [rax-28h], xmm6
0x180014e46  mov     rax, cs:__security_cookie
0x180014e4d  xor     rax, rsp
0x180014e50  mov     [rbp+57h+var_30], rax
0x180014e54  mov     rdi, rdx
0x180014e57  mov     [rbp+57h+var_88], rdx
0x180014e5b  xor     ebx, ebx
0x180014e5d  xor     r14b, r14b
0x180014e60  xor     esi, esi
0x180014e62  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180014e6a  test    r14b, r14b
0x180014e6d  jnz     loc_180014F3E
0x180014e73  xorps   xmm0, xmm0
0x180014e76  movups  [rbp+57h+var_50], xmm0
0x180014e7a  movdqu  [rbp+57h+var_40], xmm6
0x180014e7f  xor     eax, eax
0x180014e81  mov     word ptr [rbp+57h+var_50], ax
0x180014e85  mov     rdx, rdi
0x180014e88  lea     rcx, [rbp+57h+var_80]
0x180014e8c  call    ??0?$shared_ptr@VDeviceManager@DeviceConfiguration@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(std::shared_ptr<DeviceConfiguration::DeviceManager> const &)
0x180014e91  lea     r8, [rbp+57h+var_50]
0x180014e95  mov     rdx, rax
0x180014e98  call    ?_PreAddPrinter@DeviceInstaller@DeviceConfiguration@@AEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; DeviceConfiguration::DeviceInstaller::_PreAddPrinter(std::shared_ptr<DeviceConfiguration::Device>,std::wstring &)
0x180014e9d  mov     ebx, eax
0x180014e9f  test    eax, eax
0x180014ea1  js      short loc_180014F13
0x180014ea3  mov     rdx, rdi
0x180014ea6  lea     rcx, [rbp+57h+var_70]
0x180014eaa  call    ??0?$shared_ptr@VDeviceManager@DeviceConfiguration@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(std::shared_ptr<DeviceConfiguration::DeviceManager> const &)
0x180014eaf  lea     r8, [rbp+57h+var_50]
0x180014eb3  mov     rdx, rax
0x180014eb6  call    ?_AddPrinter@DeviceInstaller@DeviceConfiguration@@AEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; DeviceConfiguration::DeviceInstaller::_AddPrinter(std::shared_ptr<DeviceConfiguration::Device>,std::wstring const &)
0x180014ebb  mov     ebx, eax
0x180014ebd  test    eax, eax
0x180014ebf  js      short loc_180014F0A
0x180014ec1  mov     r14b, 1
0x180014ec4  mov     r8b, 3
0x180014ec7  mov     dl, r14b
0x180014eca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api> `wil::Feature<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetImpl(void)'::`2'::impl
0x180014ed1  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180014ed6  mov     rdx, rdi
0x180014ed9  lea     rcx, [rbp+57h+var_60]
0x180014edd  call    ??0?$shared_ptr@VDeviceManager@DeviceConfiguration@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(std::shared_ptr<DeviceConfiguration::DeviceManager> const &)
0x180014ee2  mov     rdx, rax
0x180014ee5  call    ?_PostAddPrinter@DeviceInstaller@DeviceConfiguration@@AEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@Z; DeviceConfiguration::DeviceInstaller::_PostAddPrinter(std::shared_ptr<DeviceConfiguration::Device>)
0x180014eea  mov     ebx, eax
0x180014eec  test    eax, eax
0x180014eee  jns     short loc_180014F2A
0x180014ef0  mov     r8d, eax
0x180014ef3  lea     rdx, aPostaddprinter; "_PostAddPrinter failed with hr: 0x%x"
0x180014efa  lea     rcx, aDeviceconfigur_6; "DeviceConfiguration::DeviceInstaller::I"...
0x180014f01  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180014f06  xor     ebx, ebx
0x180014f08  jmp     short loc_180014F2A
0x180014f0a  lea     rdx, aAddprinterFail; "_AddPrinter failed with hr: 0x%x"
0x180014f11  jmp     short loc_180014F1A
0x180014f13  lea     rdx, aPreaddprinterF; "_PreAddPrinter failed with hr: 0x%x"
0x180014f1a  mov     r8d, eax
0x180014f1d  lea     rcx, aDeviceconfigur_6; "DeviceConfiguration::DeviceInstaller::I"...
0x180014f24  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180014f29  nop
0x180014f2a  lea     rcx, [rbp+57h+var_50]
0x180014f2e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180014f33  inc     esi
0x180014f35  cmp     esi, 5
0x180014f38  jb      loc_180014E6A
0x180014f3e  mov     rcx, [rdi+8]; this
0x180014f42  test    rcx, rcx
0x180014f45  jz      short loc_180014F4C
0x180014f47  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180014f4c  mov     eax, ebx
0x180014f4e  mov     rcx, [rbp+57h+var_30]
0x180014f52  xor     rcx, rsp; StackCookie
0x180014f55  call    __security_check_cookie
0x180014f5a  lea     r11, [rsp+0B0h+var_10]
0x180014f62  mov     rbx, [r11+20h]
0x180014f66  mov     rsi, [r11+30h]
0x180014f6a  movaps  xmm6, xmmword ptr [r11-10h]
0x180014f6f  mov     rsp, r11
0x180014f72  pop     r14
0x180014f74  pop     rdi
0x180014f75  pop     rbp
0x180014f76  retn
```
