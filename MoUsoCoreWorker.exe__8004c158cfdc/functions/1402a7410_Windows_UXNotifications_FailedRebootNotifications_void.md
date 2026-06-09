# Windows::UXNotifications::FailedRebootNotifications(void)

- ea: `0x1402a7410`
- end: `0x1402a80f5`
- name: `?FailedRebootNotifications@UXNotifications@Windows@@UEAA?AV?$list@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@XZ`
- size: `3301`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x140043284`
- `0x1402ab0ac`
- `0x1402ab11c`
- `0x1402ab378`
- `0x140379140`

## string_xrefs

- `0x1402a74b3`: `Reboot_Engaged_Failed_QualityUpdate_BatterySaver`
- `0x1402a7462`: `Reboot_Engaged_Failed_FeatureUpdate_BatterySaver`
- `0x1402a7772`: `Reboot_Engaged_Failed_QualityUpdate_DisplayNeeded`
- `0x1402a771e`: `Reboot_Engaged_Failed_FeatureUpdate_DisplayNeeded`
- `0x1402a7671`: `Reboot_Engaged_Failed_QualityUpdate_BlockRequested`
- `0x1402a761d`: `Reboot_Engaged_Failed_FeatureUpdate_BlockRequested`
- `0x1402a757d`: `Reboot_Engaged_Failed_QualityUpdate_BlockingApps`
- `0x1402a753b`: `Reboot_Engaged_Failed_FeatureUpdate_BlockingApps`
- `0x1402a7948`: `Reboot_Engaged_Failed_FeatureUpdate_LowBattery`
- `0x1402a78b3`: `Reboot_Engaged_Failed_QualityUpdate_GameMode`
- `0x1402a7883`: `Reboot_Engaged_Failed_FeatureUpdate_GameActive`
- `0x1402a7817`: `Reboot_Engaged_Failed_QualityUpdate_FullScreen`
- `0x1402a7803`: `Reboot_Engaged_Failed_FeatureUpdate_FullScreen`
- `0x1402a7af9`: `Reboot_Engaged_Failed_QualityUpdate_OtherUser`
- `0x1402a7aca`: `Reboot_Engaged_Failed_FeatureUpdate_OtherUsers`
- `0x1402a7a35`: `Reboot_Engaged_Failed_QualityUpdate_NotOnAc`
- `0x1402a79e0`: `Reboot_Engaged_Failed_FeatureUpdate_NotOnAc`
- `0x1402a795c`: `Reboot_Engaged_Failed_QualityUpdate_LowBattery`
- `0x1402a7d8f`: `Reboot_Engaged_Failed_QualityUpdate_SBC`
- `0x1402a7d3a`: `Reboot_Engaged_Failed_FeatureUpdate_SBC`
- `0x1402a7cb6`: `Reboot_Engaged_Failed_QualityUpdate_Presenting`
- `0x1402a7ca2`: `Reboot_Engaged_Failed_FeatureUpdate_Presenting`
- `0x1402a7c06`: `Reboot_Engaged_Failed_QualityUpdate_PhoneCall`
- `0x1402a7bad`: `Reboot_Engaged_Failed_FeatureUpdate_PhoneCall`
- `0x1402a7f34`: `Reboot_Engaged_Failed_QualityUpdate_UserActive`
- `0x1402a7f20`: `Reboot_Engaged_Failed_FeatureUpdate_UserActive`
- `0x1402a7e90`: `Reboot_Engaged_Failed_QualityUpdate_SystemNeeded`
- `0x1402a7e3c`: `Reboot_Engaged_Failed_FeatureUpdate_SystemNeeded`

## pseudocode

```c
// Hidden C++ exception states: #wind=82
_OWORD *__fastcall Windows::UXNotifications::FailedRebootNotifications(__int64 a1, _OWORD *a2)
{
  _QWORD v4[2]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v5[4]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v6[4]; // [rsp+68h] [rbp-A0h] BYREF
  _OWORD v7[2]; // [rsp+88h] [rbp-80h] BYREF
  _OWORD v8[2]; // [rsp+A8h] [rbp-60h] BYREF
  _OWORD v9[2]; // [rsp+C8h] [rbp-40h] BYREF
  _OWORD v10[2]; // [rsp+E8h] [rbp-20h] BYREF
  _OWORD v11[2]; // [rsp+108h] [rbp+0h] BYREF
  _OWORD v12[2]; // [rsp+128h] [rbp+20h] BYREF
  _OWORD v13[2]; // [rsp+148h] [rbp+40h] BYREF
  _OWORD v14[2]; // [rsp+168h] [rbp+60h] BYREF
  _OWORD v15[2]; // [rsp+188h] [rbp+80h] BYREF
  _OWORD v16[2]; // [rsp+1A8h] [rbp+A0h] BYREF
  _OWORD v17[2]; // [rsp+1C8h] [rbp+C0h] BYREF
  _OWORD v18[2]; // [rsp+1E8h] [rbp+E0h] BYREF
  _OWORD v19[2]; // [rsp+208h] [rbp+100h] BYREF
  _OWORD v20[2]; // [rsp+228h] [rbp+120h] BYREF
  _OWORD v21[2]; // [rsp+248h] [rbp+140h] BYREF
  _OWORD v22[2]; // [rsp+268h] [rbp+160h] BYREF
  _OWORD v23[2]; // [rsp+288h] [rbp+180h] BYREF
  _OWORD v24[2]; // [rsp+2A8h] [rbp+1A0h] BYREF
  _OWORD v25[2]; // [rsp+2C8h] [rbp+1C0h] BYREF
  _OWORD v26[2]; // [rsp+2E8h] [rbp+1E0h] BYREF
  _OWORD v27[2]; // [rsp+308h] [rbp+200h] BYREF
  _OWORD v28[2]; // [rsp+328h] [rbp+220h] BYREF
  _BYTE v29[64]; // [rsp+348h] [rbp+240h] BYREF
  _BYTE v30[64]; // [rsp+388h] [rbp+280h] BYREF
  _OWORD v31[2]; // [rsp+3C8h] [rbp+2C0h] BYREF
  _OWORD v32[2]; // [rsp+3E8h] [rbp+2E0h] BYREF
  _BYTE v33[64]; // [rsp+408h] [rbp+300h] BYREF
  _OWORD v34[2]; // [rsp+448h] [rbp+340h] BYREF
  _OWORD v35[2]; // [rsp+468h] [rbp+360h] BYREF
  _OWORD v36[2]; // [rsp+488h] [rbp+380h] BYREF
  _OWORD v37[2]; // [rsp+4A8h] [rbp+3A0h] BYREF
  _BYTE v38[64]; // [rsp+4C8h] [rbp+3C0h] BYREF
  _BYTE v39[64]; // [rsp+508h] [rbp+400h] BYREF
  _OWORD v40[2]; // [rsp+548h] [rbp+440h] BYREF
  _OWORD v41[2]; // [rsp+568h] [rbp+460h] BYREF
  _OWORD v42[2]; // [rsp+588h] [rbp+480h] BYREF
  _OWORD v43[2]; // [rsp+5A8h] [rbp+4A0h] BYREF
  _OWORD v44[2]; // [rsp+5C8h] [rbp+4C0h] BYREF
  _OWORD v45[2]; // [rsp+5E8h] [rbp+4E0h] BYREF
  _OWORD v46[2]; // [rsp+608h] [rbp+500h] BYREF
  _OWORD v47[2]; // [rsp+628h] [rbp+520h] BYREF
  _BYTE v48[64]; // [rsp+648h] [rbp+540h] BYREF
  _OWORD v49[2]; // [rsp+688h] [rbp+580h] BYREF
  _OWORD v50[2]; // [rsp+6A8h] [rbp+5A0h] BYREF
  _OWORD v51[2]; // [rsp+6C8h] [rbp+5C0h] BYREF
  _OWORD v52[2]; // [rsp+6E8h] [rbp+5E0h] BYREF
  _OWORD v53[2]; // [rsp+708h] [rbp+600h] BYREF
  _OWORD v54[2]; // [rsp+728h] [rbp+620h] BYREF
  _OWORD v55[2]; // [rsp+748h] [rbp+640h] BYREF
  _OWORD v56[2]; // [rsp+768h] [rbp+660h] BYREF
  _OWORD v57[2]; // [rsp+788h] [rbp+680h] BYREF
  _OWORD v58[2]; // [rsp+7A8h] [rbp+6A0h] BYREF
  _BYTE v59[64]; // [rsp+7C8h] [rbp+6C0h] BYREF
  _BYTE v60[64]; // [rsp+808h] [rbp+700h] BYREF
  _OWORD v61[2]; // [rsp+848h] [rbp+740h] BYREF
  _OWORD v62[2]; // [rsp+868h] [rbp+760h] BYREF
  _OWORD v63[2]; // [rsp+888h] [rbp+780h] BYREF
  _OWORD v64[2]; // [rsp+8A8h] [rbp+7A0h] BYREF
  _OWORD v65[2]; // [rsp+8C8h] [rbp+7C0h] BYREF
  _OWORD v66[2]; // [rsp+8E8h] [rbp+7E0h] BYREF
  _OWORD v67[2]; // [rsp+908h] [rbp+800h] BYREF
  _OWORD v68[2]; // [rsp+928h] [rbp+820h] BYREF
  _OWORD v69[2]; // [rsp+948h] [rbp+840h] BYREF
  _OWORD v70[2]; // [rsp+968h] [rbp+860h] BYREF
  _OWORD v71[2]; // [rsp+988h] [rbp+880h] BYREF
  _OWORD v72[2]; // [rsp+9A8h] [rbp+8A0h] BYREF
  _OWORD v73[2]; // [rsp+9C8h] [rbp+8C0h] BYREF
  _OWORD v74[2]; // [rsp+9E8h] [rbp+8E0h] BYREF
  _BYTE v75[64]; // [rsp+A08h] [rbp+900h] BYREF
  _BYTE v76[64]; // [rsp+A48h] [rbp+940h] BYREF
  _OWORD v77[2]; // [rsp+A88h] [rbp+980h] BYREF
  _OWORD v78[2]; // [rsp+AA8h] [rbp+9A0h] BYREF
  _OWORD v79[2]; // [rsp+AC8h] [rbp+9C0h] BYREF
  _OWORD v80[2]; // [rsp+AE8h] [rbp+9E0h] BYREF
  _OWORD v81[2]; // [rsp+B08h] [rbp+A00h] BYREF
  _OWORD v82[2]; // [rsp+B28h] [rbp+A20h] BYREF
  _BYTE v83[64]; // [rsp+B48h] [rbp+A40h] BYREF
  _BYTE v84[64]; // [rsp+B88h] [rbp+A80h] BYREF
  _BYTE v85[64]; // [rsp+BC8h] [rbp+AC0h] BYREF
  char v86; // [rsp+C08h] [rbp+B00h] BYREF

  *a2 = 0;
  memset(v5, 0, sizeof(v5));
  std::wstring::_Construct<1,wchar_t const *>(v5, L"Reboot_Engaged_Failed_FeatureUpdate_BatterySaver");
  memset(v6, 0, sizeof(v6));
  std::wstring::_Construct<1,wchar_t const *>(v6, L"NonIntrusive");
  memset(v7, 0, sizeof(v7));
  std::wstring::_Construct<1,wchar_t const *>(v7, L"Reboot_Engaged_Failed_QualityUpdate_BatterySaver");
  memset(v8, 0, sizeof(v8));
  std::wstring::_Construct<1,wchar_t const *>(v8, L"NonIntrusive");
  memset(v9, 0, sizeof(v9));
  std::wstring::_Construct<1,wchar_t const *>(v9, L"Reboot_WCOS_Failed_BatterySaver");
  memset(v10, 0, sizeof(v10));
  std::wstring::_Construct<1,wchar_t const *>(v10, L"NonIntrusive");
  memset(v11, 0, sizeof(v11));
  std::wstring::_Construct<1,wchar_t const *>(v11, L"Reboot_Engaged_Failed_FeatureUpdate_BlockingApps");
  memset(v12, 0, sizeof(v12));
  std::wstring::_Construct<1,wchar_t const *>(v12, L"NonIntrusive");
  memset(v13, 0, sizeof(v13));
  std::wstring::_Construct<1,wchar_t const *>(v13, L"Reboot_Engaged_Failed_QualityUpdate_BlockingApps");
  memset(v14, 0, sizeof(v14));
  std::wstring::_Construct<1,wchar_t const *>(v14, L"NonIntrusive");
  memset(v15, 0, sizeof(v15));
  std::wstring::_Construct<1,wchar_t const *>(v15, L"Reboot_WCOS_Failed_BlockingApps");
  memset(v16, 0, sizeof(v16));
  std::wstring::_Construct<1,wchar_t const *>(v16, L"NonIntrusive");
  memset(v17, 0, sizeof(v17));
  std::wstring::_Construct<1,wchar_t const *>(v17, L"Reboot_Engaged_Failed_FeatureUpdate_BlockRequested");
  memset(v18, 0, sizeof(v18));
  std::wstring::_Construct<1,wchar_t const *>(v18, L"NonIntrusive");
  memset(v19, 0, sizeof(v19));
  std::wstring::_Construct<1,wchar_t const *>(v19, L"Reboot_Engaged_Failed_QualityUpdate_BlockRequested");
  memset(v20, 0, sizeof(v20));
  std::wstring::_Construct<1,wchar_t const *>(v20, L"NonIntrusive");
  memset(v21, 0, sizeof(v21));
  std::wstring::_Construct<1,wchar_t const *>(v21, L"Reboot_WCOS_Failed_BlockRequested");
  memset(v22, 0, sizeof(v22));
  std::wstring::_Construct<1,wchar_t const *>(v22, L"NonIntrusive");
  memset(v23, 0, sizeof(v23));
  std::wstring::_Construct<1,wchar_t const *>(v23, L"Reboot_Engaged_Failed_FeatureUpdate_DisplayNeeded");
  memset(v24, 0, sizeof(v24));
  std::wstring::_Construct<1,wchar_t const *>(v24, L"NonIntrusive");
  memset(v25, 0, sizeof(v25));
  std::wstring::_Construct<1,wchar_t const *>(v25, L"Reboot_Engaged_Failed_QualityUpdate_DisplayNeeded");
  memset(v26, 0, sizeof(v26));
  std::wstring::_Construct<1,wchar_t const *>(v26, L"NonIntrusive");
  memset(v27, 0, sizeof(v27));
  std::wstring::_Construct<1,wchar_t const *>(v27, L"Reboot_WCOS_Failed_DisplayNeeded");
  memset(v28, 0, sizeof(v28));
  std::wstring::_Construct<1,wchar_t const *>(v28, L"NonIntrusive");
  std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(
    v29,
    L"Reboot_Engaged_Failed_FeatureUpdate_FullScreen");
  std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(
    v30,
    L"Reboot_Engaged_Failed_QualityUpdate_FullScreen");
  memset(v31, 0, sizeof(v31));
  std::wstring::_Construct<1,wchar_t const *>(v31, L"Reboot_WCOS_Failed_FullScreen");
  memset(v32, 0, sizeof(v32));
  std::wstring::_Construct<1,wchar_t const *>(v32, L"NonIntrusive");
  std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(
    v33,
    L"Reboot_Engaged_Failed_FeatureUpdate_GameActive");
  memset(v34, 0, sizeof(v34));
  std::wstring::_Construct<1,wchar_t const *>(v34, L"Reboot_Engaged_Failed_QualityUpdate_GameMode");
  memset(v35, 0, sizeof(v35));
  std::wstring::_Construct<1,wchar_t const *>(v35, L"NonIntrusive");
  memset(v36, 0, sizeof(v36));
  std::wstring::_Construct<1,wchar_t const *>(v36, L"Reboot_WCOS_Failed_GameMode");
  memset(v37, 0, sizeof(v37));
  std::wstring::_Construct<1,wchar_t const *>(v37, L"NonIntrusive");
  std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(
    v38,
    L"Reboot_Engaged_Failed_FeatureUpdate_LowBattery");
  std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(
    v39,
    L"Reboot_Engaged_Failed_QualityUpdate_LowBattery");
  memset(v40, 0, sizeof(v40));
  std::wstring::_Construct<1,wchar_t const *>(v40, L"Reboot_WCOS_Failed_LowBattery");
  memset(v41, 0, sizeof(v41));
  std::wstring::_Construct<1,wchar_t const *>(v41, L"NonIntrusive");
  memset(v42, 0, sizeof(v42));
  std::wstring::_Construct<1,wchar_t const *>(v42, L"Reboot_Engaged_Failed_FeatureUpdate_NotOnAc");
  memset(v43, 0, sizeof(v43));
  std::wstring::_Construct<1,wchar_t const *>(v43, L"NonIntrusive");
  memset(v44, 0, sizeof(v44));
  std::wstring::_Construct<1,wchar_t const *>(v44, L"Reboot_Engaged_Failed_QualityUpdate_NotOnAc");
  memset(v45, 0, sizeof(v45));
  std::wstring::_Construct<1,wchar_t const *>(v45, L"NonIntrusive");
  memset(v46, 0, sizeof(v46));
  std::wstring::_Construct<1,wchar_t const *>(v46, L"Reboot_WCOS_Failed_NotOnAc");
  memset(v47, 0, sizeof(v47));
  std::wstring::_Construct<1,wchar_t const *>(v47, L"NonIntrusive");
  std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(
    v48,
    L"Reboot_Engaged_Failed_FeatureUpdate_OtherUsers");
  memset(v49, 0, sizeof(v49));
  std::wstring::_Construct<1,wchar_t const *>(v49, L"Reboot_Engaged_Failed_QualityUpdate_OtherUser");
  memset(v50, 0, sizeof(v50));
  std::wstring::_Construct<1,wchar_t const *>(v50, L"NonIntrusive");
  memset(v51, 0, sizeof(v51));
  std::wstring::_Construct<1,wchar_t const *>(v51, L"Reboot_WCOS_Failed_OtherUser");
  memset(v52, 0, sizeof(v52));
  std::wstring::_Construct<1,wchar_t const *>(v52, L"NonIntrusive");
  memset(v53, 0, sizeof(v53));
  std::wstring::_Construct<1,wchar_t const *>(v53, L"Reboot_Engaged_Failed_FeatureUpdate_PhoneCall");
  memset(v54, 0, sizeof(v54));
  std::wstring::_Construct<1,wchar_t const *>(v54, L"NonIntrusive");
  memset(v55, 0, sizeof(v55));
  std::wstring::_Construct<1,wchar_t const *>(v55, L"Reboot_Engaged_Failed_QualityUpdate_PhoneCall");
  memset(v56, 0, sizeof(v56));
  std::wstring::_Construct<1,wchar_t const *>(v56, L"NonIntrusive");
  memset(v57, 0, sizeof(v57));
  std::wstring::_Construct<1,wchar_t const *>(v57, L"Reboot_WCOS_Failed_PhoneCall");
  memset(v58, 0, sizeof(v58));
  std::wstring::_Construct<1,wchar_t const *>(v58, L"NonIntrusive");
  std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(
    v59,
    L"Reboot_Engaged_Failed_FeatureUpdate_Presenting");
  std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(
    v60,
    L"Reboot_Engaged_Failed_QualityUpdate_Presenting");
  memset(v61, 0, sizeof(v61));
  std::wstring::_Construct<1,wchar_t const *>(v61, L"Reboot_WCOS_Failed_Presenting");
  memset(v62, 0, sizeof(v62));
  std::wstring::_Construct<1,wchar_t const *>(v62, L"NonIntrusive");
  memset(v63, 0, sizeof(v63));
  std::wstring::_Construct<1,wchar_t const *>(v63, L"Reboot_Engaged_Failed_FeatureUpdate_SBC");
  memset(v64, 0, sizeof(v64));
  std::wstring::_Construct<1,wchar_t const *>(v64, L"NonIntrusive");
  memset(v65, 0, sizeof(v65));
  std::wstring::_Construct<1,wchar_t const *>(v65, L"Reboot_Engaged_Failed_QualityUpdate_SBC");
  memset(v66, 0, sizeof(v66));
  std::wstring::_Construct<1,wchar_t const *>(v66, L"NonIntrusive");
  memset(v67, 0, sizeof(v67));
  std::wstring::_Construct<1,wchar_t const *>(v67, L"Reboot_WCOS_Failed_SBC");
  memset(v68, 0, sizeof(v68));
  std::wstring::_Construct<1,wchar_t const *>(v68, L"NonIntrusive");
  memset(v69, 0, sizeof(v69));
  std::wstring::_Construct<1,wchar_t const *>(v69, L"Reboot_Engaged_Failed_FeatureUpdate_SystemNeeded");
  memset(v70, 0, sizeof(v70));
  std::wstring::_Construct<1,wchar_t const *>(v70, L"NonIntrusive");
  memset(v71, 0, sizeof(v71));
  std::wstring::_Construct<1,wchar_t const *>(v71, L"Reboot_Engaged_Failed_QualityUpdate_SystemNeeded");
  memset(v72, 0, sizeof(v72));
  std::wstring::_Construct<1,wchar_t const *>(v72, L"NonIntrusive");
  memset(v73, 0, sizeof(v73));
  std::wstring::_Construct<1,wchar_t const *>(v73, L"Reboot_WCOS_Failed_SystemNeeded");
  memset(v74, 0, sizeof(v74));
  std::wstring::_Construct<1,wchar_t const *>(v74, L"NonIntrusive");
  std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(
    v75,
    L"Reboot_Engaged_Failed_FeatureUpdate_UserActive");
  std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(
    v76,
    L"Reboot_Engaged_Failed_QualityUpdate_UserActive");
  memset(v77, 0, sizeof(v77));
  std::wstring::_Construct<1,wchar_t const *>(v77, L"Reboot_WCOS_Failed_UserActive");
  memset(v78, 0, sizeof(v78));
  std::wstring::_Construct<1,wchar_t const *>(v78, L"NonIntrusive");
  memset(v79, 0, sizeof(v79));
  std::wstring::_Construct<1,wchar_t const *>(v79, L"Reboot_EnhancedReboot_Engaged_Failed");
  memset(v80, 0, sizeof(v80));
  std::wstring::_Construct<1,wchar_t const *>(v80, L"Intrusive");
  memset(v81, 0, sizeof(v81));
  std::wstring::_Construct<1,wchar_t const *>(v81, L"Reboot_EnhancedReboot_Engaged_Failed_NearEos");
  memset(v82, 0, sizeof(v82));
  std::wstring::_Construct<1,wchar_t const *>(v82, L"Intrusive");
  std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(
    v83,
    L"Reboot_EnhancedReboot_Engaged_Failed_Eos");
  std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(v84, L"Reboot_Allow_Scheduling_RebootFailed");
  std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(v85, L"Reboot_Failed_Suggested_Active_Hours");
  v4[0] = v5;
  v4[1] = &v86;
  std::list<std::pair<std::wstring,std::wstring>>::list<std::pair<std::wstring,std::wstring>>(a2, v4);
  `eh vector destructor iterator'(
    v5,
    0x40u,
    0x2Fu,
    (void (*)(void *))Windows::Store::StoreUpdateIdentity::~StoreUpdateIdentity);
  return a2;
}

```

## disassembly

```asm
0x1402a7410  mov     rax, rsp
0x1402a7413  mov     [rax+8], rbx
0x1402a7417  mov     [rax+18h], rsi
0x1402a741b  mov     [rax+20h], rdi
0x1402a741f  mov     [rax+10h], rdx
0x1402a7423  push    rbp
0x1402a7424  push    r12
0x1402a7426  push    r13
0x1402a7428  push    r14
0x1402a742a  push    r15
0x1402a742c  lea     rbp, [rax-0B28h]
0x1402a7433  sub     rsp, 0C00h
0x1402a743a  mov     rbx, rdx
0x1402a743d  mov     [rsp+0C20h+var_C00], 0
0x1402a7445  xorps   xmm0, xmm0
0x1402a7448  movups  xmmword ptr [rdx], xmm0
0x1402a744b  movups  [rsp+0C20h+var_BE8+8], xmm0
0x1402a7450  xorps   xmm1, xmm1
0x1402a7453  movdqa  [rsp+0C20h+var_BD8+8], xmm1
0x1402a7459  mov     r13d, 30h ; '0'
0x1402a745f  mov     r8d, r13d
0x1402a7462  lea     rdx, aRebootEngagedF_18; "Reboot_Engaged_Failed_FeatureUpdate_Bat"...
0x1402a7469  lea     rcx, [rsp+0C20h+var_BE8+8]
0x1402a746e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a7473  nop
0x1402a7474  xorps   xmm0, xmm0
0x1402a7477  movups  [rsp+0C20h+var_BC8+8], xmm0
0x1402a747c  xorps   xmm1, xmm1
0x1402a747f  movdqa  [rsp+0C20h+var_BB8+8], xmm1
0x1402a7485  lea     r15d, [r13-24h]
0x1402a7489  mov     r8d, r15d
0x1402a748c  lea     rsi, aNonintrusive; "NonIntrusive"
0x1402a7493  mov     rdx, rsi
0x1402a7496  lea     rcx, [rsp+0C20h+var_BC8+8]
0x1402a749b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a74a0  nop
0x1402a74a1  xorps   xmm0, xmm0
0x1402a74a4  movups  [rbp+0B20h+var_BA0], xmm0
0x1402a74a8  xorps   xmm1, xmm1
0x1402a74ab  movdqa  [rbp+0B20h+var_B90], xmm1
0x1402a74b0  mov     r8d, r13d
0x1402a74b3  lea     rdx, aRebootEngagedF_3; "Reboot_Engaged_Failed_QualityUpdate_Bat"...
0x1402a74ba  lea     rcx, [rbp+0B20h+var_BA0]
0x1402a74be  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a74c3  nop
0x1402a74c4  xorps   xmm0, xmm0
0x1402a74c7  movups  [rbp+0B20h+var_B80], xmm0
0x1402a74cb  xorps   xmm1, xmm1
0x1402a74ce  movdqa  [rbp+0B20h+var_B70], xmm1
0x1402a74d3  mov     r8d, r15d
0x1402a74d6  mov     rdx, rsi
0x1402a74d9  lea     rcx, [rbp+0B20h+var_B80]
0x1402a74dd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a74e2  nop
0x1402a74e3  xorps   xmm0, xmm0
0x1402a74e6  movups  [rbp+0B20h+var_B60], xmm0
0x1402a74ea  xorps   xmm1, xmm1
0x1402a74ed  movdqa  [rbp+0B20h+var_B50], xmm1
0x1402a74f2  lea     r12d, [r13-11h]
0x1402a74f6  mov     r8d, r12d
0x1402a74f9  lea     rdx, aRebootWcosFail_2; "Reboot_WCOS_Failed_BatterySaver"
0x1402a7500  lea     rcx, [rbp+0B20h+var_B60]
0x1402a7504  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a7509  nop
0x1402a750a  xorps   xmm0, xmm0
0x1402a750d  movups  [rbp+0B20h+var_B40], xmm0
0x1402a7511  xorps   xmm1, xmm1
0x1402a7514  movdqa  [rbp+0B20h+var_B30], xmm1
0x1402a7519  mov     r8d, r15d
0x1402a751c  mov     rdx, rsi
0x1402a751f  lea     rcx, [rbp+0B20h+var_B40]
0x1402a7523  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a7528  nop
0x1402a7529  xorps   xmm0, xmm0
0x1402a752c  movups  [rbp+0B20h+var_B20], xmm0
0x1402a7530  xorps   xmm1, xmm1
0x1402a7533  movdqa  [rbp+0B20h+var_B10], xmm1
0x1402a7538  mov     r8d, r13d
0x1402a753b  lea     rdx, aRebootEngagedF_24; "Reboot_Engaged_Failed_FeatureUpdate_Blo"...
0x1402a7542  lea     rcx, [rbp+0B20h+var_B20]
0x1402a7546  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a754b  nop
0x1402a754c  xorps   xmm0, xmm0
0x1402a754f  movups  [rbp+0B20h+var_B00], xmm0
0x1402a7553  xorps   xmm1, xmm1
0x1402a7556  movdqa  [rbp+0B20h+var_AF0], xmm1
0x1402a755b  mov     r8d, r15d
0x1402a755e  mov     rdx, rsi
0x1402a7561  lea     rcx, [rbp+0B20h+var_B00]
0x1402a7565  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a756a  nop
0x1402a756b  xorps   xmm0, xmm0
0x1402a756e  movups  [rbp+0B20h+var_AE0], xmm0
0x1402a7572  xorps   xmm1, xmm1
0x1402a7575  movdqa  [rbp+0B20h+var_AD0], xmm1
0x1402a757a  mov     r8d, r13d
0x1402a757d  lea     rdx, aRebootEngagedF_27; "Reboot_Engaged_Failed_QualityUpdate_Blo"...
0x1402a7584  lea     rcx, [rbp+0B20h+var_AE0]
0x1402a7588  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a758d  nop
0x1402a758e  xorps   xmm0, xmm0
0x1402a7591  movups  [rbp+0B20h+var_AC0], xmm0
0x1402a7595  xorps   xmm1, xmm1
0x1402a7598  movdqa  [rbp+0B20h+var_AB0], xmm1
0x1402a759d  mov     r8d, r15d
0x1402a75a0  mov     rdx, rsi
0x1402a75a3  lea     rcx, [rbp+0B20h+var_AC0]
0x1402a75a7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a75ac  nop
0x1402a75ad  xorps   xmm0, xmm0
0x1402a75b0  movups  [rbp+0B20h+var_AA0], xmm0
0x1402a75b7  xorps   xmm1, xmm1
0x1402a75ba  movdqa  [rbp+0B20h+var_A90], xmm1
0x1402a75c2  mov     r8d, r12d
0x1402a75c5  lea     rdx, aRebootWcosFail_4; "Reboot_WCOS_Failed_BlockingApps"
0x1402a75cc  lea     rcx, [rbp+0B20h+var_AA0]
0x1402a75d3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a75d8  nop
0x1402a75d9  xorps   xmm0, xmm0
0x1402a75dc  movups  [rbp+0B20h+var_A80], xmm0
0x1402a75e3  xorps   xmm1, xmm1
0x1402a75e6  movdqa  [rbp+0B20h+var_A70], xmm1
0x1402a75ee  mov     r8d, r15d
0x1402a75f1  mov     rdx, rsi
0x1402a75f4  lea     rcx, [rbp+0B20h+var_A80]
0x1402a75fb  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a7600  nop
0x1402a7601  xorps   xmm0, xmm0
0x1402a7604  movups  [rbp+0B20h+var_A60], xmm0
0x1402a760b  xorps   xmm1, xmm1
0x1402a760e  movdqa  [rbp+0B20h+var_A50], xmm1
0x1402a7616  lea     edi, [r13+2]
0x1402a761a  mov     r8d, edi
0x1402a761d  lea     rdx, aRebootEngagedF_6; "Reboot_Engaged_Failed_FeatureUpdate_Blo"...
0x1402a7624  lea     rcx, [rbp+0B20h+var_A60]
0x1402a762b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a7630  nop
0x1402a7631  xorps   xmm0, xmm0
0x1402a7634  movups  [rbp+0B20h+var_A40], xmm0
0x1402a763b  xorps   xmm1, xmm1
0x1402a763e  movdqa  [rbp+0B20h+var_A30], xmm1
0x1402a7646  mov     r8d, r15d
0x1402a7649  mov     rdx, rsi
0x1402a764c  lea     rcx, [rbp+0B20h+var_A40]
0x1402a7653  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a7658  nop
0x1402a7659  xorps   xmm0, xmm0
0x1402a765c  movups  [rbp+0B20h+var_A20], xmm0
0x1402a7663  xorps   xmm1, xmm1
0x1402a7666  movdqa  [rbp+0B20h+var_A10], xmm1
0x1402a766e  mov     r8d, edi
0x1402a7671  lea     rdx, aRebootEngagedF_30; "Reboot_Engaged_Failed_QualityUpdate_Blo"...
0x1402a7678  lea     rcx, [rbp+0B20h+var_A20]
0x1402a767f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a7684  nop
0x1402a7685  xorps   xmm0, xmm0
0x1402a7688  movups  [rbp+0B20h+var_A00], xmm0
0x1402a768f  xorps   xmm1, xmm1
0x1402a7692  movdqa  [rbp+0B20h+var_9F0], xmm1
0x1402a769a  mov     r8d, r15d
0x1402a769d  mov     rdx, rsi
0x1402a76a0  lea     rcx, [rbp+0B20h+var_A00]
0x1402a76a7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a76ac  nop
0x1402a76ad  xorps   xmm0, xmm0
0x1402a76b0  movups  [rbp+0B20h+var_9E0], xmm0
0x1402a76b7  xorps   xmm1, xmm1
0x1402a76ba  movdqa  [rbp+0B20h+var_9D0], xmm1
0x1402a76c2  lea     r8d, [r13-0Fh]
0x1402a76c6  lea     rdx, aRebootWcosFail_9; "Reboot_WCOS_Failed_BlockRequested"
0x1402a76cd  lea     rcx, [rbp+0B20h+var_9E0]
0x1402a76d4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a76d9  nop
0x1402a76da  xorps   xmm0, xmm0
0x1402a76dd  movups  [rbp+0B20h+var_9C0], xmm0
0x1402a76e4  xorps   xmm1, xmm1
0x1402a76e7  movdqa  [rbp+0B20h+var_9B0], xmm1
0x1402a76ef  mov     r8d, r15d
0x1402a76f2  mov     rdx, rsi
0x1402a76f5  lea     rcx, [rbp+0B20h+var_9C0]
0x1402a76fc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a7701  nop
0x1402a7702  xorps   xmm0, xmm0
0x1402a7705  movups  [rbp+0B20h+var_9A0], xmm0
0x1402a770c  xorps   xmm1, xmm1
0x1402a770f  movdqa  [rbp+0B20h+var_990], xmm1
0x1402a7717  lea     edi, [r13+1]
0x1402a771b  mov     r8d, edi
0x1402a771e  lea     rdx, aRebootEngagedF_22; "Reboot_Engaged_Failed_FeatureUpdate_Dis"...
0x1402a7725  lea     rcx, [rbp+0B20h+var_9A0]
0x1402a772c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a7731  nop
0x1402a7732  xorps   xmm0, xmm0
0x1402a7735  movups  [rbp+0B20h+var_980], xmm0
0x1402a773c  xorps   xmm1, xmm1
0x1402a773f  movdqa  [rbp+0B20h+var_970], xmm1
0x1402a7747  mov     r8d, r15d
0x1402a774a  mov     rdx, rsi
0x1402a774d  lea     rcx, [rbp+0B20h+var_980]
0x1402a7754  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a7759  nop
0x1402a775a  xorps   xmm0, xmm0
0x1402a775d  movups  [rbp+0B20h+var_960], xmm0
0x1402a7764  xorps   xmm1, xmm1
0x1402a7767  movdqa  [rbp+0B20h+var_950], xmm1
0x1402a776f  mov     r8d, edi
0x1402a7772  lea     rdx, aRebootEngagedF_29; "Reboot_Engaged_Failed_QualityUpdate_Dis"...
0x1402a7779  lea     rcx, [rbp+0B20h+var_960]
0x1402a7780  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a7785  nop
0x1402a7786  xorps   xmm0, xmm0
0x1402a7789  movups  [rbp+0B20h+var_940], xmm0
0x1402a7790  xorps   xmm1, xmm1
0x1402a7793  movdqa  [rbp+0B20h+var_930], xmm1
0x1402a779b  mov     r8d, r15d
0x1402a779e  mov     rdx, rsi
0x1402a77a1  lea     rcx, [rbp+0B20h+var_940]
0x1402a77a8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a77ad  nop
0x1402a77ae  xorps   xmm0, xmm0
0x1402a77b1  movups  [rbp+0B20h+var_920], xmm0
0x1402a77b8  xorps   xmm1, xmm1
0x1402a77bb  movdqa  [rbp+0B20h+var_910], xmm1
0x1402a77c3  lea     r8d, [r13-10h]
0x1402a77c7  lea     rdx, aRebootWcosFail_0; "Reboot_WCOS_Failed_DisplayNeeded"
0x1402a77ce  lea     rcx, [rbp+0B20h+var_920]
0x1402a77d5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a77da  nop
0x1402a77db  xorps   xmm0, xmm0
0x1402a77de  movups  [rbp+0B20h+var_900], xmm0
0x1402a77e5  xorps   xmm1, xmm1
0x1402a77e8  movdqa  [rbp+0B20h+var_8F0], xmm1
0x1402a77f0  mov     r8d, r15d
0x1402a77f3  mov     rdx, rsi
0x1402a77f6  lea     rcx, [rbp+0B20h+var_900]
0x1402a77fd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a7802  nop
0x1402a7803  lea     rdx, aRebootEngagedF_17; "Reboot_Engaged_Failed_FeatureUpdate_Ful"...
0x1402a780a  lea     rcx, [rbp+0B20h+var_8E0]
0x1402a7811  call    ??$?0AEAY0CP@$$CB_WAEAY0N@$$CB_W$0A@@?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@QEAA@AEAY0CP@$$CB_WAEAY0N@$$CB_W@Z; std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(wchar_t const (&)[47],wchar_t const (&)[13])
0x1402a7816  nop
0x1402a7817  lea     rdx, aRebootEngagedF_14; "Reboot_Engaged_Failed_QualityUpdate_Ful"...
0x1402a781e  lea     rcx, [rbp+0B20h+var_8A0]
0x1402a7825  call    ??$?0AEAY0CP@$$CB_WAEAY0N@$$CB_W$0A@@?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@QEAA@AEAY0CP@$$CB_WAEAY0N@$$CB_W@Z; std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(wchar_t const (&)[47],wchar_t const (&)[13])
0x1402a782a  nop
0x1402a782b  xorps   xmm0, xmm0
0x1402a782e  movups  [rbp+0B20h+var_860], xmm0
0x1402a7835  xorps   xmm1, xmm1
0x1402a7838  movdqa  [rbp+0B20h+var_850], xmm1
0x1402a7840  lea     r14d, [r13-13h]
0x1402a7844  mov     r8d, r14d
0x1402a7847  lea     rdx, aRebootWcosFail_7; "Reboot_WCOS_Failed_FullScreen"
0x1402a784e  lea     rcx, [rbp+0B20h+var_860]
0x1402a7855  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a785a  nop
0x1402a785b  xorps   xmm0, xmm0
0x1402a785e  movups  [rbp+0B20h+var_840], xmm0
0x1402a7865  xorps   xmm1, xmm1
0x1402a7868  movdqa  [rbp+0B20h+var_830], xmm1
0x1402a7870  mov     r8d, r15d
0x1402a7873  mov     rdx, rsi
0x1402a7876  lea     rcx, [rbp+0B20h+var_840]
0x1402a787d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a7882  nop
0x1402a7883  lea     rdx, aRebootEngagedF_20; "Reboot_Engaged_Failed_FeatureUpdate_Gam"...
0x1402a788a  lea     rcx, [rbp+0B20h+var_820]
0x1402a7891  call    ??$?0AEAY0CP@$$CB_WAEAY0N@$$CB_W$0A@@?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@QEAA@AEAY0CP@$$CB_WAEAY0N@$$CB_W@Z; std::pair<std::wstring,std::wstring>::pair<std::wstring,std::wstring>(wchar_t const (&)[47],wchar_t const (&)[13])
0x1402a7896  nop
0x1402a7897  xorps   xmm0, xmm0
0x1402a789a  movups  [rbp+0B20h+var_7E0], xmm0
0x1402a78a1  xorps   xmm1, xmm1
0x1402a78a4  movdqa  [rbp+0B20h+var_7D0], xmm1
0x1402a78ac  lea     r15d, [r13-4]
0x1402a78b0  mov     r8d, r15d
0x1402a78b3  lea     rdx, aRebootEngagedF_8; "Reboot_Engaged_Failed_QualityUpdate_Gam"...
0x1402a78ba  lea     rcx, [rbp+0B20h+var_7E0]
0x1402a78c1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a78c6  nop
0x1402a78c7  xorps   xmm0, xmm0
0x1402a78ca  movups  [rbp+0B20h+var_7C0], xmm0
0x1402a78d1  xorps   xmm1, xmm1
0x1402a78d4  movdqa  [rbp+0B20h+var_7B0], xmm1
0x1402a78dc  lea     edi, [r13-24h]
0x1402a78e0  mov     r8d, edi
0x1402a78e3  mov     rdx, rsi
0x1402a78e6  lea     rcx, [rbp+0B20h+var_7C0]
0x1402a78ed  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a78f2  nop
0x1402a78f3  xorps   xmm0, xmm0
0x1402a78f6  movups  [rbp+0B20h+var_7A0], xmm0
0x1402a78fd  xorps   xmm1, xmm1
0x1402a7900  movdqa  [rbp+0B20h+var_790], xmm1
0x1402a7908  lea     r8d, [r13-15h]
0x1402a790c  lea     rdx, aRebootWcosFail_12; "Reboot_WCOS_Failed_GameMode"
0x1402a7913  lea     rcx, [rbp+0B20h+var_7A0]
0x1402a791a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1402a791f  nop
0x1402a7920  xorps   xmm0, xmm0
0x1402a7923  movups  [rbp+0B20h+var_780], xmm0
0x1402a792a  xorps   xmm1, xmm1
  ... truncated ...
```
