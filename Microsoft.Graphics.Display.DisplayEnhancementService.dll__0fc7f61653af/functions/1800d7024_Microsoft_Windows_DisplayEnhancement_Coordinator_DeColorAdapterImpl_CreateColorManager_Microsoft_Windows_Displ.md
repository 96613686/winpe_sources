# Microsoft::Windows::DisplayEnhancement::Coordinator::DeColorAdapterImpl::CreateColorManager(Microsoft::Windows::DisplayEnhancement::Foundation::MonitorAdapterTargetId)

- ea: `0x1800d7024`
- end: `0x1800d71ff`
- name: `?CreateColorManager@DeColorAdapterImpl@Coordinator@DisplayEnhancement@Windows@Microsoft@@AEAA?AUDisplayColorManagement@6Display@Graphics@Internal@4winrt@@UMonitorAdapterTargetId@Foundation@345@@Z`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d73ac`

## callees

- `0x180005860`
- `0x180006440`
- `0x180009050`
- `0x18000fb14`
- `0x180013138`
- `0x180029404`
- `0x18003b120`
- `0x18003b8e4`
- `0x18003b948`
- `0x18003bbb4`
- `0x18003c044`
- `0x18003c214`
- `0x18003c350`
- `0x18003d7c4`
- `0x1800753fc`
- `0x1800d7024`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x1800d7096`
- `api-ms-win-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x1800d7096`

## string_xrefs

- `0x1800d719e`: `Microsoft.Graphics.Display.DisplayEnhancementService.dll`
- `0x1800d71ed`: `onecoreuap\drivers\mobilepc\displayenhancement\service\derequestcoordinator\lib\decoloradapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall Microsoft::Windows::DisplayEnhancement::Coordinator::DeColorAdapterImpl::CreateColorManager(
        __int64 a1,
        __int64 *a2,
        LUID *a3)
{
  __int64 *v4; // rdi
  int DeviceInfo; // eax
  _QWORD *ColorManager; // rax
  const char *v7; // r9
  __int64 v8; // rcx
  unsigned int v9; // ebx
  unsigned int *v10; // rax
  __int64 v12; // [rsp+20h] [rbp-238h] BYREF
  _QWORD v13[2]; // [rsp+28h] [rbp-230h] BYREF
  _BYTE v14[32]; // [rsp+38h] [rbp-220h] BYREF
  __int128 v15; // [rsp+58h] [rbp-200h]
  _BYTE v16[40]; // [rsp+68h] [rbp-1F0h] BYREF
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+90h] [rbp-1C8h] BYREF
  char v18[144]; // [rsp+A4h] [rbp-1B4h] BYREF
  char v19[268]; // [rsp+134h] [rbp-124h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v4 = a2;
  *(_QWORD *)&v15 = a2;
  memset_0(v18, 0, 0x190u);
  requestPacket.type = DISPLAYCONFIG_DEVICE_INFO_GET_TARGET_NAME;
  requestPacket.size = 420;
  requestPacket.adapterId = *a3;
  requestPacket.id = a3[1].LowPart;
  DeviceInfo = DisplayConfigGetDeviceInfo(&requestPacket);
  if ( DeviceInfo > 0 )
    DeviceInfo = (unsigned __int16)DeviceInfo | 0x80070000;
  if ( DeviceInfo < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\derequestcoordinator\\lib\\decoloradapter.cpp",
      (const char *)(unsigned int)DeviceInfo,
      v12);
  std::wstring::wstring(v16, v19);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExternalBrightness>::GetImpl'::`2'::impl) )
  {
    try
    {
      v12 = 0;
      ColorManager = Microsoft::Windows::DisplayEnhancement::Foundation::ColorManagerHelper::CreateColorManager(
                       v13,
                       (__int64)v16,
                       (int *)&xmmword_1801292C0);
      winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(&v12, ColorManager);
      winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(v13);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\derequestcoordinator\\lib\\decoloradapter.cpp",
        v7);
      v4 = (__int64 *)v15;
    }
    v8 = v12;
    v12 = 0;
    *v4 = v8;
    winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(&v12);
  }
  else
  {
    v15 = xmmword_1801292C0;
    winrt::param::hstring::hstring((winrt::param::hstring *)v14);
    winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement::GetColorManagerForDisplayAsync(
      (const struct winrt::param::hstring *)&v12,
      (const struct winrt::guid *)v14);
    v9 = winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>>(
           &v12,
           0x2710u);
    if ( v9 == 1 )
    {
      winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>,winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::get(
        &v12,
        v4);
    }
    else
    {
      v10 = (unsigned int *)winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>>::ErrorCode(
                              &v12,
                              v13);
      MicrosoftTelemetryAssertTriggeredArgs("Microsoft.Graphics.Display.DisplayEnhancementService.dll", v9, *v10);
      *v4 = 0;
    }
    winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(&v12);
  }
  std::wstring::_Tidy_deallocate(v16);
  return v4;
}

```

## disassembly

```asm
0x1800d7024  mov     [rsp+arg_0], rbx
0x1800d7029  push    rdi
0x1800d702a  sub     rsp, 250h
0x1800d7031  mov     rax, cs:__security_cookie
0x1800d7038  xor     rax, rsp
0x1800d703b  mov     [rsp+258h+var_18], rax
0x1800d7043  mov     rbx, r8
0x1800d7046  mov     rdi, rdx
0x1800d7049  mov     qword ptr [rsp+258h+var_200], rdx
0x1800d704e  xor     edx, edx; Val
0x1800d7050  mov     r8d, 190h; Size
0x1800d7056  lea     rcx, [rsp+258h+var_1B4]; void *
0x1800d705e  call    memset_0
0x1800d7063  mov     [rsp+258h+requestPacket.type], 2
0x1800d706e  mov     [rsp+258h+requestPacket.size], 1A4h
0x1800d7079  mov     rax, [rbx]
0x1800d707c  mov     qword ptr [rsp+258h+requestPacket.adapterId.LowPart], rax
0x1800d7084  mov     eax, [rbx+8]
0x1800d7087  mov     [rsp+258h+requestPacket.id], eax
0x1800d708e  lea     rcx, [rsp+258h+requestPacket]; requestPacket
0x1800d7096  call    cs:__imp_DisplayConfigGetDeviceInfo
0x1800d709c  test    eax, eax
0x1800d709e  jle     short loc_1800D70A8
0x1800d70a0  movzx   eax, ax
0x1800d70a3  or      eax, 80070000h
0x1800d70a8  mov     rcx, [rsp+258h]; this
0x1800d70b0  test    eax, eax
0x1800d70b2  js      loc_1800D71EA
0x1800d70b8  lea     rdx, [rsp+258h+var_124]
0x1800d70c0  lea     rcx, [rsp+258h+var_1F0]
0x1800d70c5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800d70ca  nop
0x1800d70cb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ExternalBrightness@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ExternalBrightness@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness> `wil::Feature<__WilFeatureTraits_Feature_ExternalBrightness>::GetImpl(void)'::`2'::impl
0x1800d70d2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ExternalBrightness@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExternalBrightness>::__private_IsEnabled(void)
0x1800d70d7  test    al, al
0x1800d70d9  jz      short loc_1800D7139
0x1800d70db  mov     [rsp+258h+var_238], 0
0x1800d70e4  lea     r8, xmmword_1801292C0
0x1800d70eb  lea     rdx, [rsp+258h+var_1F0]
0x1800d70f0  lea     rcx, [rsp+258h+var_230]
0x1800d70f5  call    ?CreateColorManager@ColorManagerHelper@Foundation@DisplayEnhancement@Windows@Microsoft@@SA?AUDisplayColorManagement@6Display@Graphics@Internal@4winrt@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z; Microsoft::Windows::DisplayEnhancement::Foundation::ColorManagerHelper::CreateColorManager(std::wstring const &,_GUID const &)
0x1800d70fa  mov     rdx, rax
0x1800d70fd  lea     rcx, [rsp+258h+var_238]
0x1800d7102  call    ??4?$com_ptr@UIRestrictedErrorInfo@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::impl::IRestrictedErrorInfo>::operator=(winrt::com_ptr<winrt::impl::IRestrictedErrorInfo> &&)
0x1800d7107  lea     rcx, [rsp+258h+var_230]
0x1800d710c  call    ??1?$IAsyncOperation@UDisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(void)
0x1800d7111  nop
0x1800d7112  jmp     short loc_1800D7119
0x1800d7114  mov     rdi, qword ptr [rsp+258h+var_200]
0x1800d7119  mov     rcx, [rsp+258h+var_238]
0x1800d711e  mov     [rsp+258h+var_238], 0
0x1800d7127  mov     [rdi], rcx
0x1800d712a  lea     rcx, [rsp+258h+var_238]
0x1800d712f  call    ??1?$IAsyncOperation@UDisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(void)
0x1800d7134  jmp     loc_1800D71BC
0x1800d7139  movups  xmm0, cs:xmmword_1801292C0
0x1800d7140  movdqu  [rsp+258h+var_200], xmm0
0x1800d7146  lea     rdx, [rsp+258h+var_1F0]
0x1800d714b  lea     rcx, [rsp+258h+var_220]; this
0x1800d7150  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x1800d7155  lea     r8, [rsp+258h+var_200]
0x1800d715a  lea     rdx, [rsp+258h+var_220]; struct winrt::guid *
0x1800d715f  lea     rcx, [rsp+258h+var_238]; struct winrt::param::hstring *
0x1800d7164  call    ?GetColorManagerForDisplayAsync@DisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@SA@AEBUhstring@param@6@AEBUguid@6@@Z; winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement::GetColorManagerForDisplayAsync(winrt::param::hstring const &,winrt::guid const &)
0x1800d7169  nop
0x1800d716a  mov     edx, 2710h
0x1800d716f  lea     rcx, [rsp+258h+var_238]
0x1800d7174  call    ??$wait_for_completed@U?$IAsyncOperation@UDisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBU?$IAsyncOperation@UDisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@@Foundation@Windows@1@I@Z
0x1800d7179  mov     ebx, eax
0x1800d717b  lea     rcx, [rsp+258h+var_238]
0x1800d7180  cmp     eax, 1
0x1800d7183  jnz     short loc_1800D718F
0x1800d7185  mov     rdx, rdi
0x1800d7188  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UDisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UDisplayColorManagement@5Display@Graphics@Internal@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>,winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::get(void)
0x1800d718d  jmp     short loc_1800D71B1
0x1800d718f  lea     rdx, [rsp+258h+var_230]
0x1800d7194  call    ?ErrorCode@?$consume_Windows_Foundation_IAsyncInfo@U?$IAsyncOperation@UDisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncInfo<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>>::ErrorCode(void)
0x1800d7199  mov     r8d, [rax]
0x1800d719c  mov     edx, ebx
0x1800d719e  lea     rcx, aMicrosoftGraph_0; "Microsoft.Graphics.Display.DisplayEnhan"...
0x1800d71a5  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800d71aa  mov     qword ptr [rdi], 0
0x1800d71b1  lea     rcx, [rsp+258h+var_238]
0x1800d71b6  call    ??1?$IAsyncOperation@UDisplayColorManagement@1Display@Graphics@Internal@Windows@winrt@@@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>::~IAsyncOperation<winrt::Windows::Internal::Graphics::Display::DisplayColorManagement::DisplayColorManagement>(void)
0x1800d71bb  nop
0x1800d71bc  lea     rcx, [rsp+258h+var_1F0]
0x1800d71c1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d71c6  mov     rax, rdi
0x1800d71c9  mov     rcx, [rsp+258h+var_18]
0x1800d71d1  xor     rcx, rsp; StackCookie
0x1800d71d4  call    __security_check_cookie
0x1800d71d9  mov     rbx, [rsp+258h+arg_0]
0x1800d71e1  add     rsp, 250h
0x1800d71e8  pop     rdi
0x1800d71e9  retn
0x1800d71ea  mov     r9d, eax; char *
0x1800d71ed  lea     r8, aOnecoreuapDriv_7; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800d71f4  mov     edx, 7Dh ; '}'; void *
0x1800d71f9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
