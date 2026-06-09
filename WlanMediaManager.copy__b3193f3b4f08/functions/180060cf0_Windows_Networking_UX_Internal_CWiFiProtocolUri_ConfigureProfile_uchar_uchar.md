# Windows::Networking::UX::Internal::CWiFiProtocolUri::ConfigureProfile(uchar,uchar *)

- ea: `0x180060cf0`
- end: `0x18006120c`
- name: `?ConfigureProfile@CWiFiProtocolUri@Internal@UX@Networking@Windows@@UEAAJEPEAE@Z`
- size: `1308`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::CWiFiProtocolUri *__hidden this, unsigned __int8, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008e30`
- `0x1800097b4`
- `0x18000a394`
- `0x18000de4c`
- `0x18000e1dc`
- `0x18001d4d4`
- `0x180021064`
- `0x18002354c`
- `0x180024de8`
- `0x180025cec`
- `0x1800396c8`
- `0x18003a000`
- `0x18003a108`
- `0x18003ae0c`
- `0x18004da20`
- `0x18004dd08`
- `0x18004e244`
- `0x18004f768`
- `0x1800504fc`
- `0x180060bb0`
- `0x180060cf0`
- `0x180061430`
- `0x180061870`
- `0x1800622cc`
- `0x1800626d4`
- `0x1800632fc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060ee3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060f2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061191`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060ee3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180060f2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061191`

## string_xrefs

- `0x180060e90`: `onecoreuap\net\ux\wlanmediamanager\lib\cwifiprotocoluri.cpp`
- `0x180060f12`: `onecoreuap\net\ux\wlanmediamanager\lib\cwifiprotocoluri.cpp`
- `0x1800611c8`: `onecoreuap\net\ux\wlanmediamanager\lib\cwifiprotocoluri.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::CWiFiProtocolUri::ConfigureProfile(
        Windows::Networking::UX::Internal::CWiFiProtocolUri *this,
        char a2,
        unsigned __int8 *a3)
{
  wil::details::in1diag3 *v6; // rcx
  __int64 v7; // rax
  _QWORD *v8; // rax
  __int64 *v9; // rbx
  __int64 v10; // rax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  struct IInspectable *v18; // rsi
  int FirstAvailableProfileName; // eax
  __int64 v20; // rdx
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned __int8 v24; // r14
  bool v25; // bl
  __int64 v26; // r9
  struct _GUID v27; // xmm0
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // r8
  int v33; // [rsp+20h] [rbp-99h]
  HSTRING string; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int8 v35[8]; // [rsp+58h] [rbp-61h] BYREF
  __int64 v36; // [rsp+60h] [rbp-59h] BYREF
  struct IInspectable *v37; // [rsp+68h] [rbp-51h] BYREF
  struct Windows::Networking::UX::IWiFiProfile *v38[2]; // [rsp+70h] [rbp-49h] BYREF
  struct _GUID v39; // [rsp+80h] [rbp-39h] BYREF
  struct _GUID v40; // [rsp+90h] [rbp-29h] BYREF
  void **v41; // [rsp+A0h] [rbp-19h] BYREF
  _BYTE v42[48]; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v43; // [rsp+D8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_798799ef23c633adda075654372160e0_Traceguids);
  v36 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_49660148>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_49660148>::GetImpl'::`2'::impl) )
  {
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::ensure_data(&v36)
             + 41LL) = 2;
    if ( v36 && (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v36 + 8) )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v6);
    v7 = tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::ensure_data(&v36);
    *(_DWORD *)(*(_QWORD *)v7 + 28LL) |= 0x80000u;
  }
  if ( v36 && (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v36 + 8) )
    wil::com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>::reset(&v36);
  v8 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::ensure_data(&v36);
  tip2::details::shared_data<1,0,0>::start(*v8 + 8LL, &v39);
  v9 = (__int64 *)tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::ensure_data(&v36);
  v41 = &tip2::test_watcher<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v42,
    (struct wil::details::IFailureCallback *)&v41,
    0,
    1);
  v10 = *v9;
  v43 = v10;
  if ( v10 )
    _InterlockedIncrement((volatile signed __int32 *)(v10 + 288));
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::operator->(
                           &v36,
                           &v39)
            + 276LL) = 0;
  tip2::test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::~test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>(&v39);
  *a3 = 0;
  if ( !*((_BYTE *)this + 144) || *((_BYTE *)this + 145) )
  {
    v11 = -2147024809;
    v12 = 163;
    goto LABEL_55;
  }
  if ( !*((_QWORD *)this + 8) )
  {
    v11 = -2147467261;
    v12 = 164;
LABEL_55:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprotocoluri.cpp",
      (const char *)v11,
      v33);
    goto LABEL_56;
  }
  v37 = 0;
  v13 = Microsoft::WRL::WeakRef::As<Windows::Networking::UX::Internal::IMediaManager>(
          (Windows::Networking::UX::Internal::CWiFiProtocolUri *)((char *)this + 64),
          &v37);
  v11 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprotocoluri.cpp",
      (const char *)(unsigned int)v13,
      v33);
LABEL_19:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37, v16, v17);
LABEL_56:
    tip2::test_watcher<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::~test_watcher<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>(&v41);
    wil::com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>(&v36);
    return v11;
  }
  v18 = v37;
  if ( !v37 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37, v14, v15);
    v11 = -2147467261;
    goto LABEL_56;
  }
  v38[0] = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v38, v14, v15);
  WindowsDeleteString(0);
  string = 0;
  FirstAvailableProfileName = Windows::Networking::UX::Internal::CWiFiProtocolUri::_FindFirstAvailableProfileName(
                                this,
                                (struct Windows::Networking::UX::Internal::WlanMediaManager *)v18,
                                &string,
                                v38);
  v11 = FirstAvailableProfileName;
  if ( FirstAvailableProfileName < 0 )
  {
    v20 = 174;
LABEL_24:
    v21 = (unsigned int)FirstAvailableProfileName;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\cwifiprotocoluri.cpp",
      (const char *)v21,
      v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v38, v22, v23);
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_19;
  }
  v35[0] = 0;
  v39.Data1 = 0;
  FirstAvailableProfileName = Windows::Networking::UX::Internal::CWiFiProtocolUri::_IsNetworkVisible(
                                this,
                                (struct Windows::Networking::UX::Internal::WlanMediaManager *)v18,
                                v35,
                                (enum Windows::Networking::UX::WiFiSecurityType *)&v39);
  v11 = FirstAvailableProfileName;
  if ( FirstAvailableProfileName < 0 )
  {
    v20 = 178;
    goto LABEL_24;
  }
  v24 = v35[0];
  v25 = v35[0] != 0;
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::operator->(
                          &v36,
                          &v40)
           + 272LL) = v25;
  tip2::test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::~test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>(&v40);
  v40.Data1 = 0;
  if ( v38[0] )
  {
    FirstAvailableProfileName = Windows::Networking::UX::Internal::WlanMediaManager::Category_DeleteProfile(
                                  (Windows::Networking::UX::Internal::WlanMediaManager *)v18,
                                  v38[0],
                                  (enum Windows::Networking::UX::WiFiProfileDeleteStatus *)&v40);
    v11 = FirstAvailableProfileName;
    if ( FirstAvailableProfileName < 0 )
    {
      v20 = 185;
      goto LABEL_24;
    }
    if ( v40.Data1 == 3 )
    {
      v11 = -2147023728;
      v20 = 186;
      v21 = 2147943568LL;
      goto LABEL_25;
    }
    if ( v40.Data1 != 1 )
    {
      v11 = -2147024891;
      v20 = 187;
      v21 = 2147942405LL;
      goto LABEL_25;
    }
  }
  v26 = *((_QWORD *)this + 15);
  LOBYTE(v33) = a2;
  v39 = *(struct _GUID *)((char *)this + 72);
  FirstAvailableProfileName = Windows::Networking::UX::Internal::WlanMediaManager::ConfigureProfile(
                                v18,
                                &v39,
                                string,
                                v26);
  v11 = FirstAvailableProfileName;
  if ( FirstAvailableProfileName < 0 )
  {
    v20 = 199;
    goto LABEL_24;
  }
  FirstAvailableProfileName = Windows::Networking::UX::Internal::CWiFiProtocolUri::_SetProfileMetadata(this, string);
  v11 = FirstAvailableProfileName;
  if ( FirstAvailableProfileName < 0 )
  {
    v20 = 200;
    goto LABEL_24;
  }
  *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::operator->(
                           &v36,
                           &v39)
            + 276LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::~test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>(&v39);
  v39 = *(struct _GUID *)((char *)this + 72);
  FirstAvailableProfileName = Windows::Networking::UX::Internal::WlanMediaManager::RefreshNetworkList(
                                (Windows::Networking::UX::Internal::WlanMediaManager *)v18,
                                &v39);
  v11 = FirstAvailableProfileName;
  if ( FirstAvailableProfileName < 0 )
  {
    v20 = 203;
    goto LABEL_24;
  }
  if ( v24 )
  {
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::operator->(
                             &v36,
                             &v39)
              + 276LL) = 2;
    tip2::test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::~test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>(&v39);
    if ( v36 )
      v27 = *(struct _GUID *)(v36 + 152);
    else
      v27 = 0;
    v39 = v27;
    v40 = *(struct _GUID *)((char *)this + 72);
    FirstAvailableProfileName = Windows::Networking::UX::Internal::WlanMediaManager::StartConnectionAddNetworkWiFiUriTipTest(
                                  (Windows::Networking::UX::Internal::WlanMediaManager *)v18,
                                  &v40,
                                  &v39,
                                  string);
    v11 = FirstAvailableProfileName;
    if ( FirstAvailableProfileName < 0 )
    {
      v20 = 209;
      goto LABEL_24;
    }
    FirstAvailableProfileName = Windows::Networking::UX::Internal::CWiFiProtocolUri::_StartConnection(
                                  this,
                                  (struct Windows::Networking::UX::Internal::WlanMediaManager *)v18,
                                  string);
    v11 = FirstAvailableProfileName;
    if ( FirstAvailableProfileName < 0 )
    {
      v20 = 210;
      goto LABEL_24;
    }
  }
  else
  {
    tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::complete(&v36);
  }
  *a3 = v24;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_798799ef23c633adda075654372160e0_Traceguids, 0);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v38, v28, v29);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37, v30, v31);
  tip2::test_watcher<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::~test_watcher<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>(&v41);
  wil::com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>(&v36);
  return 0;
}

```

## disassembly

```asm
0x180060cf0  mov     [rsp-8+arg_18], rbx
0x180060cf5  push    rbp
0x180060cf6  push    rsi
0x180060cf7  push    rdi
0x180060cf8  push    r12
0x180060cfa  push    r13
0x180060cfc  push    r14
0x180060cfe  push    r15
0x180060d00  lea     rbp, [rsp-27h]
0x180060d05  sub     rsp, 0E0h
0x180060d0c  mov     r15, r8
0x180060d0f  mov     r12b, dl
0x180060d12  mov     rdi, rcx
0x180060d15  mov     rcx, cs:WPP_GLOBAL_Control
0x180060d1c  lea     rax, WPP_GLOBAL_Control
0x180060d23  cmp     rcx, rax
0x180060d26  jz      short loc_180060D43
0x180060d28  test    byte ptr [rcx+1Ch], 40h
0x180060d2c  jz      short loc_180060D43
0x180060d2e  mov     rcx, [rcx+10h]
0x180060d32  lea     r8, WPP_798799ef23c633adda075654372160e0_Traceguids
0x180060d39  mov     edx, 16h
0x180060d3e  call    WPP_SF_
0x180060d43  xor     r13d, r13d
0x180060d46  mov     [rbp+57h+var_B0], r13
0x180060d4a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NetworkUX_BugFix_49660148@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_49660148@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_49660148> `wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_49660148>::GetImpl(void)'::`2'::impl
0x180060d51  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_49660148@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_49660148>::__private_IsEnabled(void)
0x180060d56  test    al, al
0x180060d58  jz      short loc_180060DAF
0x180060d5a  mov     rcx, [rbp+57h+var_B0]
0x180060d5e  test    rcx, rcx
0x180060d61  jz      short loc_180060D74
0x180060d63  add     rcx, 8
0x180060d67  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x180060d6c  test    al, al
0x180060d6e  jnz     loc_180061206
0x180060d74  lea     rcx, [rbp+57h+var_B0]
0x180060d78  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::ensure_data(void)
0x180060d7d  mov     rcx, [rax]
0x180060d80  mov     byte ptr [rcx+29h], 2
0x180060d84  mov     rcx, [rbp+57h+var_B0]
0x180060d88  test    rcx, rcx
0x180060d8b  jz      short loc_180060D9E
0x180060d8d  add     rcx, 8
0x180060d91  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x180060d96  test    al, al
0x180060d98  jnz     loc_180061206
0x180060d9e  lea     rcx, [rbp+57h+var_B0]
0x180060da2  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::ensure_data(void)
0x180060da7  mov     rcx, [rax]
0x180060daa  bts     dword ptr [rcx+1Ch], 13h
0x180060daf  mov     rcx, [rbp+57h+var_B0]
0x180060db3  test    rcx, rcx
0x180060db6  jz      short loc_180060DCE
0x180060db8  add     rcx, 8
0x180060dbc  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x180060dc1  test    al, al
0x180060dc3  jz      short loc_180060DCE
0x180060dc5  lea     rcx, [rbp+57h+var_B0]
0x180060dc9  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>,wil::err_returncode_policy>::reset(void)
0x180060dce  lea     rcx, [rbp+57h+var_B0]
0x180060dd2  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::ensure_data(void)
0x180060dd7  lea     rdx, [rbp+57h+var_90]
0x180060ddb  mov     rcx, [rax]
0x180060dde  add     rcx, 8
0x180060de2  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x180060de7  lea     rcx, [rbp+57h+var_B0]
0x180060deb  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::ensure_data(void)
0x180060df0  mov     rbx, rax
0x180060df3  lea     rdx, [rbp+57h+var_70]; struct wil::details::IFailureCallback *
0x180060df7  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::`vftable'
0x180060dfe  mov     r9b, 1; bool
0x180060e01  xor     r8d, r8d; struct wil::CallContextInfo *
0x180060e04  mov     [rbp+57h+var_70], rax
0x180060e08  lea     rcx, [rbp+57h+var_68]; this
0x180060e0c  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x180060e11  mov     rax, [rbx]
0x180060e14  mov     [rbp+57h+var_38], rax
0x180060e18  test    rax, rax
0x180060e1b  jz      short loc_180060E24
0x180060e1d  lock inc dword ptr [rax+120h]
0x180060e24  lea     rdx, [rbp+57h+var_90]
0x180060e28  lea     rcx, [rbp+57h+var_B0]
0x180060e2c  call    ??C?$tip_test@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::operator->(void)
0x180060e31  mov     rcx, [rax]
0x180060e34  mov     [rcx+114h], r13d
0x180060e3b  lea     rcx, [rbp+57h+var_90]
0x180060e3f  call    ??1?$test_data_control@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::~test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>(void)
0x180060e44  mov     [r15], r13b
0x180060e47  cmp     [rdi+90h], r13b
0x180060e4e  jz      loc_1800611BA
0x180060e54  cmp     [rdi+91h], r13b
0x180060e5b  jnz     loc_1800611BA
0x180060e61  lea     rcx, [rdi+40h]; this
0x180060e65  cmp     [rcx], r13
0x180060e68  jnz     short loc_180060E79
0x180060e6a  mov     ebx, 80004003h
0x180060e6f  mov     edx, 0A4h
0x180060e74  jmp     loc_1800611C4
0x180060e79  lea     rdx, [rbp+57h+var_A8]; struct IInspectable **
0x180060e7d  mov     [rbp+57h+var_A8], r13
0x180060e81  call    ??$As@UIMediaManager@Internal@UX@Networking@Windows@@@WeakRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIMediaManager@Internal@UX@Networking@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::WeakRef::As<Windows::Networking::UX::Internal::IMediaManager>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Networking::UX::Internal::IMediaManager>>)
0x180060e86  mov     ebx, eax
0x180060e88  test    eax, eax
0x180060e8a  jns     short loc_180060EB2
0x180060e8c  mov     rcx, [rbp+5Fh]; this
0x180060e90  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180060e97  mov     r9d, eax; char *
0x180060e9a  mov     edx, 0A7h; void *
0x180060e9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060ea4  lea     rcx, [rbp+57h+var_A8]
0x180060ea8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180060ead  jmp     loc_1800611D7
0x180060eb2  mov     rsi, [rbp+57h+var_A8]
0x180060eb6  test    rsi, rsi
0x180060eb9  jnz     short loc_180060ECE
0x180060ebb  lea     rcx, [rbp+57h+var_A8]
0x180060ebf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180060ec4  mov     ebx, 80004003h
0x180060ec9  jmp     loc_1800611D7
0x180060ece  lea     rcx, [rbp+57h+var_A0]
0x180060ed2  mov     [rbp+57h+string], r13
0x180060ed6  mov     [rbp+57h+var_A0], r13
0x180060eda  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180060edf  mov     rcx, [rbp+57h+string]; string
0x180060ee3  call    cs:__imp_WindowsDeleteString
0x180060ee9  lea     r9, [rbp+57h+var_A0]; struct Windows::Networking::UX::IWiFiProfile **
0x180060eed  mov     [rbp+57h+string], r13
0x180060ef1  lea     r8, [rbp+57h+string]; HSTRING *
0x180060ef5  mov     rdx, rsi; struct Windows::Networking::UX::Internal::WlanMediaManager *
0x180060ef8  mov     rcx, rdi; this
0x180060efb  call    ?_FindFirstAvailableProfileName@CWiFiProtocolUri@Internal@UX@Networking@Windows@@AEAAJPEAVWlanMediaManager@2345@PEAPEAUHSTRING__@@PEAPEAUIWiFiProfile@345@@Z; Windows::Networking::UX::Internal::CWiFiProtocolUri::_FindFirstAvailableProfileName(Windows::Networking::UX::Internal::WlanMediaManager *,HSTRING__ * *,Windows::Networking::UX::IWiFiProfile * *)
0x180060f00  mov     ebx, eax
0x180060f02  test    eax, eax
0x180060f04  jns     short loc_180060F3A
0x180060f06  mov     edx, 0AEh; void *
0x180060f0b  mov     r9d, eax; char *
0x180060f0e  mov     rcx, [rbp+5Fh]; this
0x180060f12  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180060f19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060f1e  lea     rcx, [rbp+57h+var_A0]
0x180060f22  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180060f27  mov     rcx, [rbp+57h+string]; string
0x180060f2b  call    cs:__imp_WindowsDeleteString
0x180060f31  mov     [rbp+57h+string], r13
0x180060f35  jmp     loc_180060EA4
0x180060f3a  lea     r9, [rbp+57h+var_90]; enum Windows::Networking::UX::WiFiSecurityType *
0x180060f3e  mov     [rbp+57h+var_B8], r13b
0x180060f42  lea     r8, [rbp+57h+var_B8]; unsigned __int8 *
0x180060f46  mov     [rbp+57h+var_90.Data1], r13d
0x180060f4a  mov     rdx, rsi; struct Windows::Networking::UX::Internal::WlanMediaManager *
0x180060f4d  mov     rcx, rdi; this
0x180060f50  call    ?_IsNetworkVisible@CWiFiProtocolUri@Internal@UX@Networking@Windows@@AEAAJPEAVWlanMediaManager@2345@PEAEPEAW4WiFiSecurityType@345@@Z; Windows::Networking::UX::Internal::CWiFiProtocolUri::_IsNetworkVisible(Windows::Networking::UX::Internal::WlanMediaManager *,uchar *,Windows::Networking::UX::WiFiSecurityType *)
0x180060f55  mov     ebx, eax
0x180060f57  test    eax, eax
0x180060f59  jns     short loc_180060F62
0x180060f5b  mov     edx, 0B2h
0x180060f60  jmp     short loc_180060F0B
0x180060f62  mov     r14b, [rbp+57h+var_B8]
0x180060f66  lea     rdx, [rbp+57h+var_80]
0x180060f6a  test    r14b, r14b
0x180060f6d  lea     rcx, [rbp+57h+var_B0]
0x180060f71  setnz   bl
0x180060f74  call    ??C?$tip_test@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::operator->(void)
0x180060f79  mov     rcx, [rax]
0x180060f7c  mov     [rcx+110h], bl
0x180060f82  lea     rcx, [rbp+57h+var_80]
0x180060f86  call    ??1?$test_data_control@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::~test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>(void)
0x180060f8b  mov     rdx, [rbp+57h+var_A0]; struct Windows::Networking::UX::IWiFiProfile *
0x180060f8f  mov     [rbp+57h+var_80.Data1], r13d
0x180060f93  test    rdx, rdx
0x180060f96  jz      short loc_180060FE4
0x180060f98  lea     r8, [rbp+57h+var_80]; enum Windows::Networking::UX::WiFiProfileDeleteStatus *
0x180060f9c  mov     rcx, rsi; this
0x180060f9f  call    ?Category_DeleteProfile@WlanMediaManager@Internal@UX@Networking@Windows@@QEAAJPEAUIWiFiProfile@345@PEAW4WiFiProfileDeleteStatus@345@@Z; Windows::Networking::UX::Internal::WlanMediaManager::Category_DeleteProfile(Windows::Networking::UX::IWiFiProfile *,Windows::Networking::UX::WiFiProfileDeleteStatus *)
0x180060fa4  mov     ebx, eax
0x180060fa6  test    eax, eax
0x180060fa8  jns     short loc_180060FB4
0x180060faa  mov     edx, 0B9h
0x180060faf  jmp     loc_180060F0B
0x180060fb4  cmp     [rbp+57h+var_80.Data1], 3
0x180060fb8  jnz     short loc_180060FCC
0x180060fba  mov     ebx, 80070490h
0x180060fbf  mov     edx, 0BAh
0x180060fc4  mov     r9d, ebx
0x180060fc7  jmp     loc_180060F0E
0x180060fcc  cmp     [rbp+57h+var_80.Data1], 1
0x180060fd0  jz      short loc_180060FE4
0x180060fd2  mov     ebx, 80070005h
0x180060fd7  mov     edx, 0BBh
0x180060fdc  mov     r9d, ebx
0x180060fdf  jmp     loc_180060F0E
0x180060fe4  movzx   ecx, byte ptr [rdi+93h]
0x180060feb  test    r14b, r14b
0x180060fee  jz      short loc_180060FFC
0x180060ff0  test    cl, cl
0x180060ff2  jz      short loc_180060FFC
0x180060ff4  cmp     [rbp+57h+var_90.Data1], 0Ch
0x180060ff8  cmovz   ecx, r13d
0x180060ffc  mov     rax, [rdi+80h]
0x180061003  lea     rdx, [rbp+57h+var_90]
0x180061007  movups  xmm0, xmmword ptr [rdi+48h]
0x18006100b  mov     r9, [rdi+78h]
0x18006100f  mov     r8, [rbp+57h+string]
0x180061013  mov     [rsp+110h+var_D0], rax
0x180061018  mov     eax, [rdi+8Ch]
0x18006101e  mov     [rsp+110h+var_D8], eax
0x180061022  mov     al, [rdi+88h]
0x180061028  mov     [rsp+110h+var_E0], cl
0x18006102c  mov     rcx, rsi
0x18006102f  mov     [rsp+110h+var_E8], al
0x180061033  mov     [rsp+110h+var_F0], r12b
0x180061038  movdqu  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x18006103d  call    ?ConfigureProfile@WlanMediaManager@Internal@UX@Networking@Windows@@QEAAJU_GUID@@PEAUHSTRING__@@1EEEW4WiFiSecurityType@345@1@Z; Windows::Networking::UX::Internal::WlanMediaManager::ConfigureProfile(_GUID,HSTRING__ *,HSTRING__ *,uchar,uchar,uchar,Windows::Networking::UX::WiFiSecurityType,HSTRING__ *)
0x180061042  mov     ebx, eax
0x180061044  test    eax, eax
0x180061046  jns     short loc_180061052
0x180061048  mov     edx, 0C7h
0x18006104d  jmp     loc_180060F0B
0x180061052  mov     rdx, [rbp+57h+string]; HSTRING
0x180061056  mov     rcx, rdi; this
0x180061059  call    ?_SetProfileMetadata@CWiFiProtocolUri@Internal@UX@Networking@Windows@@AEAAJPEAUHSTRING__@@@Z; Windows::Networking::UX::Internal::CWiFiProtocolUri::_SetProfileMetadata(HSTRING__ *)
0x18006105e  mov     ebx, eax
0x180061060  test    eax, eax
0x180061062  jns     short loc_18006106E
0x180061064  mov     edx, 0C8h
0x180061069  jmp     loc_180060F0B
0x18006106e  lea     rdx, [rbp+57h+var_90]
0x180061072  lea     rcx, [rbp+57h+var_B0]
0x180061076  call    ??C?$tip_test@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::operator->(void)
0x18006107b  mov     rcx, [rax]
0x18006107e  mov     dword ptr [rcx+114h], 1
0x180061088  lea     rcx, [rbp+57h+var_90]
0x18006108c  call    ??1?$test_data_control@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::~test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>(void)
0x180061091  movups  xmm0, xmmword ptr [rdi+48h]
0x180061095  lea     rdx, [rbp+57h+var_90]; struct _GUID
0x180061099  mov     rcx, rsi; this
0x18006109c  movdqu  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x1800610a1  call    ?RefreshNetworkList@WlanMediaManager@Internal@UX@Networking@Windows@@QEAAJU_GUID@@@Z; Windows::Networking::UX::Internal::WlanMediaManager::RefreshNetworkList(_GUID)
0x1800610a6  mov     ebx, eax
0x1800610a8  test    eax, eax
0x1800610aa  jns     short loc_1800610B6
0x1800610ac  mov     edx, 0CBh
0x1800610b1  jmp     loc_180060F0B
0x1800610b6  lea     rcx, [rbp+57h+var_B0]
0x1800610ba  test    r14b, r14b
0x1800610bd  jz      loc_18006114B
0x1800610c3  lea     rdx, [rbp+57h+var_90]
0x1800610c7  call    ??C?$tip_test@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::operator->(void)
0x1800610cc  mov     rcx, [rax]
0x1800610cf  mov     dword ptr [rcx+114h], 2
0x1800610d9  lea     rcx, [rbp+57h+var_90]
0x1800610dd  call    ??1?$test_data_control@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::~test_data_control<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>(void)
0x1800610e2  mov     rax, [rbp+57h+var_B0]
0x1800610e6  test    rax, rax
0x1800610e9  jz      short loc_1800610F4
0x1800610eb  movups  xmm0, xmmword ptr [rax+98h]
0x1800610f2  jmp     short loc_1800610F7
0x1800610f4  xorps   xmm0, xmm0
0x1800610f7  mov     r9, [rbp+57h+string]; HSTRING
0x1800610fb  lea     r8, [rbp+57h+var_90]; struct _GUID
0x1800610ff  movdqa  xmmword ptr [rbp+57h+var_90.Data1], xmm0
0x180061104  lea     rdx, [rbp+57h+var_80]; struct _GUID
0x180061108  movups  xmm0, xmmword ptr [rdi+48h]
0x18006110c  mov     rcx, rsi; this
0x18006110f  movdqu  xmmword ptr [rbp+57h+var_80.Data1], xmm0
0x180061114  call    ?StartConnectionAddNetworkWiFiUriTipTest@WlanMediaManager@Internal@UX@Networking@Windows@@QEAAJU_GUID@@0PEAUHSTRING__@@@Z; Windows::Networking::UX::Internal::WlanMediaManager::StartConnectionAddNetworkWiFiUriTipTest(_GUID,_GUID,HSTRING__ *)
0x180061119  mov     ebx, eax
0x18006111b  test    eax, eax
0x18006111d  jns     short loc_180061129
0x18006111f  mov     edx, 0D1h
0x180061124  jmp     loc_180060F0B
0x180061129  mov     r8, [rbp+57h+string]; HSTRING
0x18006112d  mov     r9b, r12b; unsigned __int8
0x180061130  mov     rdx, rsi; struct Windows::Networking::UX::Internal::WlanMediaManager *
0x180061133  mov     rcx, rdi; this
0x180061136  call    ?_StartConnection@CWiFiProtocolUri@Internal@UX@Networking@Windows@@AEAAJPEAVWlanMediaManager@2345@PEAUHSTRING__@@E@Z; Windows::Networking::UX::Internal::CWiFiProtocolUri::_StartConnection(Windows::Networking::UX::Internal::WlanMediaManager *,HSTRING__ *,uchar)
0x18006113b  mov     ebx, eax
0x18006113d  test    eax, eax
0x18006113f  jns     short loc_180061150
0x180061141  mov     edx, 0D2h
0x180061146  jmp     loc_180060F0B
0x18006114b  call    ?complete@?$tip_test@V?$merged_data@U_tip_WiFiProvisioningFromUri@QRCodeTipTest@@U12@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<QRCodeTipTest::_tip_WiFiProvisioningFromUri,QRCodeTipTest::_tip_WiFiProvisioningFromUri>>::complete(void)
0x180061150  mov     [r15], r14b
0x180061153  mov     rcx, cs:WPP_GLOBAL_Control
0x18006115a  lea     rax, WPP_GLOBAL_Control
0x180061161  cmp     rcx, rax
0x180061164  jz      short loc_180061184
0x180061166  test    byte ptr [rcx+1Ch], 8
0x18006116a  jz      short loc_180061184
0x18006116c  mov     rcx, [rcx+10h]
0x180061170  lea     r8, WPP_798799ef23c633adda075654372160e0_Traceguids
0x180061177  mov     edx, 17h
0x18006117c  xor     r9d, r9d
0x18006117f  call    WPP_SF_d
0x180061184  lea     rcx, [rbp+57h+var_A0]
0x180061188  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006118d  mov     rcx, [rbp+57h+string]; string
0x180061191  call    cs:__imp_WindowsDeleteString
0x180061197  lea     rcx, [rbp+57h+var_A8]
  ... truncated ...
```
