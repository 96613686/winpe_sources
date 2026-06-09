# DeviceConfiguration::Device::Initalize(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_GUID,bool,bool,DeviceConfiguration::DeviceType,DeviceConfiguration::DeviceInstallState,ulong)

- ea: `0x1800146ec`
- end: `0x180014814`
- name: `?Initalize@Device@DeviceConfiguration@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000000U_GUID@@_N2W4DeviceType@2@W4DeviceInstallState@2@K@Z`
- size: `296`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, _OWORD *, char, char, int, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000fbe0`

## callees

- `0x18000f6c4`
- `0x180014150`
- `0x18001442c`
- `0x1800146ec`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::Device::Initalize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _OWORD *a9,
        char a10,
        char a11,
        int a12,
        int a13,
        int a14)
{
  __int64 v17; // r8
  __int64 v18; // rdx
  int v19; // ecx
  const char *v20; // r9
  __int64 result; // rax
  int *v22; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v24; // [rsp+40h] [rbp+8h] BYREF

  try
  {
    std::wstring::operator=(a1, a2);
    std::wstring::operator=(a1 + 32, a3);
    std::wstring::operator=(a1 + 64, a4);
    std::wstring::operator=(a1 + 96, a5);
    std::wstring::operator=(a1 + 128, a6);
    std::wstring::operator=(a1 + 160, a7);
    LOBYTE(v17) = 3;
    LOBYTE(v18) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetImpl'::`2'::impl,
      v18,
      v17);
    std::wstring::operator=(a1 + 192, a8);
    *(_OWORD *)(a1 + 224) = *a9;
    *(_BYTE *)(a1 + 240) = a10;
    *(_BYTE *)(a1 + 241) = a11;
    v19 = a12;
    *(_DWORD *)(a1 + 244) = a12;
    *(_DWORD *)(a1 + 252) = a13;
    *(_DWORD *)(a1 + 256) = a14;
    *(_DWORD *)(a1 + 248) = v19 == 3;
    v24 = 512;
    v22 = &v24;
    wil::ResultFromException__lambda_20c5d0bbfa23beba93a5990856bf3efa___(&v22);
    *(_DWORD *)(a1 + 260) = v24;
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x37,
                           (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\device.cpp",
                           v20);
  }
  return result;
}

```

## disassembly

```asm
0x1800146ec  mov     [rsp+arg_8], rbx
0x1800146f1  mov     [rsp+arg_10], rsi
0x1800146f6  push    rdi
0x1800146f7  sub     rsp, 30h
0x1800146fb  mov     rdi, r9
0x1800146fe  mov     rsi, r8
0x180014701  mov     rbx, rcx
0x180014704  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180014709  lea     rcx, [rbx+20h]
0x18001470d  mov     rdx, rsi
0x180014710  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180014715  lea     rcx, [rbx+40h]
0x180014719  mov     rdx, rdi
0x18001471c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180014721  lea     rcx, [rbx+60h]
0x180014725  mov     rdx, [rsp+38h+arg_20]
0x18001472a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001472f  lea     rcx, [rbx+80h]
0x180014736  mov     rdx, [rsp+38h+arg_28]
0x18001473b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180014740  lea     rcx, [rbx+0A0h]
0x180014747  mov     rdx, [rsp+38h+arg_30]
0x18001474c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180014751  mov     r8b, 3
0x180014754  mov     dl, 1
0x180014756  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api> `wil::Feature<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetImpl(void)'::`2'::impl
0x18001475d  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180014762  lea     rcx, [rbx+0C0h]
0x180014769  mov     rdx, [rsp+38h+arg_38]
0x18001476e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180014773  mov     rax, [rsp+38h+arg_40]
0x18001477b  movaps  xmm0, xmmword ptr [rax]
0x18001477e  movdqu  xmmword ptr [rbx+0E0h], xmm0
0x180014786  mov     al, [rsp+38h+arg_48]
0x18001478d  mov     [rbx+0F0h], al
0x180014793  mov     al, [rsp+38h+arg_50]
0x18001479a  mov     [rbx+0F1h], al
0x1800147a0  mov     ecx, [rsp+38h+arg_58]
0x1800147a7  mov     [rbx+0F4h], ecx
0x1800147ad  mov     eax, [rsp+38h+arg_60]
0x1800147b4  mov     [rbx+0FCh], eax
0x1800147ba  mov     eax, [rsp+38h+arg_68]
0x1800147c1  mov     [rbx+100h], eax
0x1800147c7  xor     eax, eax
0x1800147c9  cmp     ecx, 3
0x1800147cc  setz    al
0x1800147cf  mov     [rbx+0F8h], eax
0x1800147d5  mov     [rsp+38h+arg_0], 200h
0x1800147dd  lea     rax, [rsp+38h+arg_0]
0x1800147e2  mov     [rsp+38h+var_18], rax
0x1800147e7  lea     rcx, [rsp+38h+var_18]
0x1800147ec  call    wil__ResultFromException__lambda_20c5d0bbfa23beba93a5990856bf3efa___
0x1800147f1  mov     eax, [rsp+38h+arg_0]
0x1800147f5  mov     [rbx+104h], eax
0x1800147fb  xor     eax, eax
0x1800147fd  jmp     short loc_180014803
0x1800147ff  mov     eax, [rsp+38h+arg_0]
0x180014803  mov     rbx, [rsp+38h+arg_8]
0x180014808  mov     rsi, [rsp+38h+arg_10]
0x18001480d  add     rsp, 30h
0x180014811  pop     rdi
0x180014812  retn
```
