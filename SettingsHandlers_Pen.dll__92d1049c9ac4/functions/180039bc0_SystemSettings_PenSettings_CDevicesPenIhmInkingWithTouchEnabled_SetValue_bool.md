# SystemSettings::PenSettings::CDevicesPenIhmInkingWithTouchEnabled::SetValue(bool)

- ea: `0x180039bc0`
- end: `0x180039d59`
- name: `?SetValue@CDevicesPenIhmInkingWithTouchEnabled@PenSettings@SystemSettings@@UEAAJ_N@Z`
- size: `409`
- prototype: `__int64 __fastcall(SystemSettings::PenSettings::CDevicesPenIhmInkingWithTouchEnabled *__hidden this, bool)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800030e0`
- `0x18000a2bc`
- `0x1800115d8`
- `0x1800134b8`
- `0x180019fcc`
- `0x18001a378`
- `0x18001d98c`
- `0x18001fe00`
- `0x180031460`
- `0x1800390a0`
- `0x180039bc0`
- `0x180045764`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendNotifyMessageW` at `0x180039c99`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendNotifyMessageW` at `0x180039c99`

## string_xrefs

- `0x180039c60`: `shellcommon\shell\settingshandlers\pen\lib\penhandlers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::PenSettings::CDevicesPenIhmInkingWithTouchEnabled::SetValue(
        SystemSettings::PenSettings::CDevicesPenIhmInkingWithTouchEnabled *this,
        unsigned __int8 a2)
{
  int v2; // edi
  __int64 HandwritingViewRegKeySDDLForCurrentContext; // rax
  const unsigned __int16 *v5; // rax
  const unsigned __int16 *v6; // rdx
  HKEY v7; // rcx
  int v8; // eax
  const char *v9; // r9
  unsigned int v10; // ebx
  __int64 v12; // rdx
  int v13; // [rsp+20h] [rbp-F8h]
  unsigned int v14; // [rsp+30h] [rbp-E8h] BYREF
  unsigned int *v15; // [rsp+38h] [rbp-E0h] BYREF
  _BYTE v16[8]; // [rsp+40h] [rbp-D8h] BYREF
  __int64 (__fastcall **v17)(); // [rsp+48h] [rbp-D0h] BYREF
  char v18; // [rsp+50h] [rbp-C8h]
  __int64 (__fastcall ***v19)(); // [rsp+B0h] [rbp-68h]
  __m128i v20[2]; // [rsp+B8h] [rbp-60h] BYREF
  _BYTE v21[40]; // [rsp+D8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  try
  {
    v2 = a2;
    v20[0] = 0;
    v20[1] = _mm_load_si128((const __m128i *)&_xmm);
    v20[0].m128i_i16[0] = 0;
    HandwritingViewRegKeySDDLForCurrentContext = Helpers::PenAndInkSettingsInternal::GetHandwritingViewRegKeySDDLForCurrentContext(v21);
    std::wstring::operator=(v20, HandwritingViewRegKeySDDLForCurrentContext);
    std::wstring::_Tidy_deallocate(v21);
    v5 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
    v8 = SHRegSetBOOLWithSSDL(v7, v6, L"EnableInkingWithTouch", v5, v2);
  }
  catch ( ... )
  {
    v14 = wil::details::in1diag3::Return_CaughtException(
            retaddr,
            (void *)0x3A4,
            (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
            v9);
    std::wstring::_Tidy_deallocate(v20);
    return v14;
  }
  v10 = v8;
  if ( v8 >= 0 )
  {
    SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"touch keyboard");
    v17 = off_1800632F0;
    v18 = v2;
    v19 = &v17;
    v12 = wil::cloud_store::cloud_store(
            (wil::cloud_store *)v21,
            (SystemSettings::PenSettings::CDevicesPenIhmInkingWithTouchEnabled *)((char *)this + 248));
    UpdateCDS<Windows::Data::Input::InkAndPen::InkPlatformSettings>(v16, v12);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl'::`2'::impl) )
    {
      v14 = 8;
      v15 = &v14;
      SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::PenSettings::PenCommandsSyncArgs>::_Notify<_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_>(
        &SystemSettings::PenSettings::PenCommandsSyncSingleton::m_instance,
        &v15);
    }
    std::wstring::_Tidy_deallocate(v20);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A6,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\pen\\lib\\penhandlers.cpp",
      (const char *)(unsigned int)v8,
      v13);
    std::wstring::_Tidy_deallocate(v20);
    return v10;
  }
}

```

## disassembly

```asm
0x180039bc0  mov     r11, rsp
0x180039bc3  mov     [r11+18h], rbx
0x180039bc7  mov     [r11+20h], rsi
0x180039bcb  push    rdi
0x180039bcc  sub     rsp, 110h
0x180039bd3  mov     rax, cs:__security_cookie
0x180039bda  xor     rax, rsp
0x180039bdd  mov     [rsp+118h+var_18], rax
0x180039be5  movzx   edi, dl
0x180039be8  mov     rsi, rcx
0x180039beb  xorps   xmm0, xmm0
0x180039bee  movups  xmmword ptr [r11-60h], xmm0
0x180039bf3  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180039bfb  movdqu  xmmword ptr [r11-50h], xmm1
0x180039c01  xor     eax, eax
0x180039c03  mov     [r11-60h], ax
0x180039c08  lea     rcx, [r11-40h]
0x180039c0c  call    Helpers__PenAndInkSettingsInternal__GetHandwritingViewRegKeySDDLForCurrentContext
0x180039c11  mov     rdx, rax
0x180039c14  lea     rcx, [rsp+118h+var_60]
0x180039c1c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180039c21  lea     rcx, [rsp+118h+var_40]
0x180039c29  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039c2e  nop
0x180039c2f  lea     rcx, [rsp+118h+var_60]
0x180039c37  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180039c3c  mov     r9, rax; unsigned __int16 *
0x180039c3f  mov     [rsp+118h+var_F8], edi; int
0x180039c43  lea     r8, aEnableinkingwi; "EnableInkingWithTouch"
0x180039c4a  call    ?SHRegSetBOOLWithSSDL@@YAJPEAUHKEY__@@PEBG11H@Z; SHRegSetBOOLWithSSDL(HKEY__ *,ushort const *,ushort const *,ushort const *,int)
0x180039c4f  mov     ebx, eax
0x180039c51  test    eax, eax
0x180039c53  jns     short loc_180039C86
0x180039c55  mov     rcx, [rsp+118h]; this
0x180039c5d  mov     r9d, eax; char *
0x180039c60  lea     r8, aShellcommonShe; "shellcommon\\shell\\settingshandlers\\p"...
0x180039c67  mov     edx, 3A6h; void *
0x180039c6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039c71  nop
0x180039c72  lea     rcx, [rsp+118h+var_60]
0x180039c7a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039c7f  mov     eax, ebx
0x180039c81  jmp     loc_180039D34
0x180039c86  lea     r9, lParam; "touch keyboard"
0x180039c8d  xor     r8d, r8d; wParam
0x180039c90  lea     edx, [r8+1Ah]; Msg
0x180039c94  mov     ecx, 0FFFFh; hWnd
0x180039c99  call    cs:__imp_SendNotifyMessageW
0x180039c9f  lea     rdx, [rsi+0F8h]; struct wil::cloud_store *
0x180039ca6  lea     rcx, [rsp+118h+var_40]; this
0x180039cae  call    ??0cloud_store@wil@@QEAA@AEBV01@@Z; wil::cloud_store::cloud_store(wil::cloud_store const &)
0x180039cb3  lea     rcx, off_1800632F0
0x180039cba  mov     [rsp+118h+var_D0], rcx
0x180039cbf  mov     [rsp+118h+var_C8], dil
0x180039cc4  lea     rcx, [rsp+118h+var_D0]
0x180039cc9  mov     [rsp+118h+var_68], rcx
0x180039cd1  mov     rdx, rax
0x180039cd4  lea     rcx, [rsp+118h+var_D8]
0x180039cd9  call    ??$UpdateCDS@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@@YAXV?$function@$$A6AXAEAV?$cloud_store_data@UInkPlatformSettings@InkAndPen@Input@Data@Windows@@@wil@@@Z@wistd@@Vcloud_store@wil@@@Z; UpdateCDS<Windows::Data::Input::InkAndPen::InkPlatformSettings>(wistd::function<void (wil::cloud_store_data<Windows::Data::Input::InkAndPen::InkPlatformSettings> &)>,wil::cloud_store)
0x180039cde  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56834065@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065> `wil::Feature<__WilFeatureTraits_Feature_56834065>::GetImpl(void)'::`2'::impl
0x180039ce5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56834065@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56834065>::__private_IsEnabled(void)
0x180039cea  test    al, al
0x180039cec  jz      short loc_180039D12
0x180039cee  mov     [rsp+118h+var_E8], 8
0x180039cf6  lea     rax, [rsp+118h+var_E8]
0x180039cfb  mov     [rsp+118h+var_E0], rax
0x180039d00  lea     rdx, [rsp+118h+var_E0]
0x180039d05  lea     rcx, ?m_instance@PenCommandsSyncSingleton@PenSettings@SystemSettings@@0V123@A; SystemSettings::PenSettings::PenCommandsSyncSingleton SystemSettings::PenSettings::PenCommandsSyncSingleton::m_instance
0x180039d0c  call    ??$_Notify@V_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_@@@?$CSingletonHelper@W4PenCommandsSyncArgs@PenSettings@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::PenSettings::PenCommandsSyncArgs>::_Notify<_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_>(_lambda_595e60df2ebf0cdb0e9c80f920e0f4d5_ const &)
0x180039d11  nop
0x180039d12  lea     rcx, [rsp+118h+var_60]
0x180039d1a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039d1f  xor     eax, eax
0x180039d21  jmp     short loc_180039D34
0x180039d23  lea     rcx, [rsp+118h+var_60]
0x180039d2b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180039d30  mov     eax, [rsp+118h+var_E8]
0x180039d34  mov     rcx, [rsp+118h+var_18]
0x180039d3c  xor     rcx, rsp; StackCookie
0x180039d3f  call    __security_check_cookie
0x180039d44  lea     r11, [rsp+118h+var_8]
0x180039d4c  mov     rbx, [r11+20h]
0x180039d50  mov     rsi, [r11+28h]
0x180039d54  mov     rsp, r11
0x180039d57  pop     rdi
0x180039d58  retn
```
