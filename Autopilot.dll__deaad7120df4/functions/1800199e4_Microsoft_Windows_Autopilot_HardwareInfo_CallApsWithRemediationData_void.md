# Microsoft::Windows::Autopilot::HardwareInfo::CallApsWithRemediationData(void)

- ea: `0x1800199e4`
- end: `0x180019e12`
- name: `?CallApsWithRemediationData@HardwareInfo@Autopilot@Windows@Microsoft@@SAJXZ`
- size: `1070`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001c190`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180013de4`
- `0x180013f88`
- `0x180014abc`
- `0x180015cd4`
- `0x1800179b8`
- `0x180017a20`
- `0x1800180b8`
- `0x1800199e4`
- `0x18001c448`
- `0x18001d1c0`
- `0x180024878`
- `0x1800260b8`
- `0x18002f010`

## import_xrefs

- `WINHTTP!WinHttpCloseHandle` at `0x180019c1f`
- `WINHTTP!WinHttpCloseHandle` at `0x180019c34`
- `WINHTTP!WinHttpCloseHandle` at `0x180019c49`
- `WINHTTP!WinHttpCloseHandle` at `0x180019d2d`
- `WINHTTP!WinHttpCloseHandle` at `0x180019d42`
- `WINHTTP!WinHttpCloseHandle` at `0x180019d57`
- `WINHTTP!WinHttpCloseHandle` at `0x180019c1f`
- `WINHTTP!WinHttpCloseHandle` at `0x180019c34`
- `WINHTTP!WinHttpCloseHandle` at `0x180019c49`
- `WINHTTP!WinHttpCloseHandle` at `0x180019d2d`
- `WINHTTP!WinHttpCloseHandle` at `0x180019d42`
- `WINHTTP!WinHttpCloseHandle` at `0x180019d57`

## string_xrefs

- `0x180019a95`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x180019b51`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x180019bf7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x180019a6e`: `https://ztd.dds.microsoft.com/ztd/device/UpdateDeviceHardwareMismatchRemediationState`
- `0x180019a75`: `DdsZtdMarkRemediationUri`
- `0x180019b2e`: `https://ztd.dds.microsoft.com`
- `0x180019b35`: `DdsZtdMsaTicketUri`

## pseudocode

```c
__int64 Microsoft::Windows::Autopilot::HardwareInfo::CallApsWithRemediationData(void)
{
  _QWORD *AutopilotCorrelationVector; // rax
  _QWORD *v1; // r8
  __m128i si128; // xmm6
  int RegistryDownloadKey; // eax
  int v4; // ebx
  void (__fastcall ***v5)(_QWORD, __int64); // rax
  int v7; // eax
  __int64 v8; // rdx
  __int128 *v9; // rdx
  void (__fastcall ***v10)(_QWORD, __int64); // rax
  int v11; // [rsp+28h] [rbp-E0h]
  int v12; // [rsp+28h] [rbp-E0h]
  _BYTE v13[40]; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v14; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int64 v15; // [rsp+80h] [rbp-88h]
  unsigned __int64 v16; // [rsp+88h] [rbp-80h]
  WCHAR pwszUrl[8]; // [rsp+90h] [rbp-78h] BYREF
  __m128i v18; // [rsp+A0h] [rbp-68h]
  __int128 v19; // [rsp+B8h] [rbp-50h] BYREF
  __m128i v20; // [rsp+C8h] [rbp-40h]
  _OWORD v21[2]; // [rsp+D8h] [rbp-30h] BYREF
  HINTERNET v22[2]; // [rsp+F8h] [rbp-10h]
  HINTERNET hInternet; // [rsp+108h] [rbp+0h]
  _OWORD v24[2]; // [rsp+118h] [rbp+10h] BYREF
  char *v25[4]; // [rsp+138h] [rbp+30h] BYREF
  _OWORD v26[2]; // [rsp+158h] [rbp+50h] BYREF
  _QWORD v27[3]; // [rsp+178h] [rbp+70h] BYREF
  __int64 v28; // [rsp+190h] [rbp+88h]
  char *v29[4]; // [rsp+198h] [rbp+90h] BYREF
  char *v30[8]; // [rsp+1B8h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+220h] [rbp+118h]

  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v27);
  AutopilotCorrelationVector = (_QWORD *)ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(v26);
  if ( AutopilotCorrelationVector[3] <= 0xFu )
    v1 = AutopilotCorrelationVector;
  else
    v1 = (_QWORD *)*AutopilotCorrelationVector;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
    v27,
    v25,
    v1,
    (char *)v1 + AutopilotCorrelationVector[2]);
  std::string::_Tidy_deallocate((char **)v26);
  *(_OWORD *)pwszUrl = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v18 = si128;
  pwszUrl[0] = 0;
  RegistryDownloadKey = Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::GetRegistryDownloadKey(
                          L"DdsZtdMarkRemediationUri",
                          L"https://ztd.dds.microsoft.com/ztd/device/UpdateDeviceHardwareMismatchRemediationState",
                          pwszUrl);
  v4 = RegistryDownloadKey;
  if ( RegistryDownloadKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)RegistryDownloadKey,
      v11);
LABEL_6:
    std::wstring::_Tidy_deallocate((char **)pwszUrl);
    std::wstring::_Tidy_deallocate(v25);
    v27[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
    std::wstring::_Tidy_deallocate(v30);
    std::string::_Tidy_deallocate(v29);
    if ( v28 )
    {
      v5 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      if ( v5 )
        (**v5)(v5, 1);
    }
    return (unsigned int)v4;
  }
  v24[0] = 0;
  v24[1] = si128;
  LOWORD(v24[0]) = 0;
  v7 = Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::GetRegistryDownloadKey(
         L"DdsZtdMsaTicketUri",
         L"https://ztd.dds.microsoft.com",
         v24);
  v4 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v7,
      v11);
LABEL_12:
    std::wstring::_Tidy_deallocate((char **)v24);
    goto LABEL_6;
  }
  v19 = 0;
  v20 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v19) = 0;
  v21[0] = 0;
  v21[1] = v20;
  LOWORD(v21[0]) = 0;
  *(_OWORD *)v22 = 0;
  hInternet = 0;
  v14 = 0;
  v15 = 0;
  v16 = 7;
  LOWORD(v14) = 0;
  v4 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::MarkDeviceAsRemediationRequired(
         (Microsoft::Windows::Autopilot::DdsNetworkWrapper *)&v19,
         pwszUrl,
         0,
         0,
         (__int64)&v14);
  if ( v4 < 0 )
  {
    v8 = 136;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v4,
      v12);
    std::wstring::_Tidy_deallocate((char **)&v14);
    if ( hInternet )
      WinHttpCloseHandle(hInternet);
    if ( v22[1] )
      WinHttpCloseHandle(v22[1]);
    if ( v22[0] )
      WinHttpCloseHandle(v22[0]);
    std::wstring::_Tidy_deallocate((char **)v21);
    std::wstring::_Tidy_deallocate((char **)&v19);
    goto LABEL_12;
  }
  memset(&v13[8], 0, 32);
  v9 = &v14;
  if ( v16 > 7 )
    v9 = (__int128 *)v14;
  std::wstring::_Construct<2,unsigned short const *>((__int64)&v13[8], v9, v15);
  memset(v26, 0, sizeof(v26));
  std::wstring::_Construct<1,unsigned short const *>(v26, L"MarkRemediationStatusResponse.txt", 0x21u);
  v4 = Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(
         0,
         (__int64)v26,
         (const unsigned __int16 *)&v13[8]);
  std::wstring::_Tidy_deallocate((char **)v26);
  if ( v4 < 0 )
  {
    v8 = 137;
    goto LABEL_15;
  }
  v4 = Microsoft::Windows::Autopilot::HardwareInfo::ProcessRemediationResult(&v14);
  if ( v4 < 0 )
  {
    v8 = 139;
    goto LABEL_15;
  }
  std::wstring::_Tidy_deallocate((char **)&v14);
  if ( hInternet )
    WinHttpCloseHandle(hInternet);
  if ( v22[1] )
    WinHttpCloseHandle(v22[1]);
  if ( v22[0] )
    WinHttpCloseHandle(v22[0]);
  std::wstring::_Tidy_deallocate((char **)v21);
  std::wstring::_Tidy_deallocate((char **)&v19);
  std::wstring::_Tidy_deallocate((char **)v24);
  std::wstring::_Tidy_deallocate((char **)pwszUrl);
  std::wstring::_Tidy_deallocate(v25);
  v27[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
  std::wstring::_Tidy_deallocate(v30);
  std::string::_Tidy_deallocate(v29);
  if ( v28 )
  {
    v10 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    if ( v10 )
      (**v10)(v10, 1);
  }
  return 0;
}

```

## disassembly

```asm
0x1800199e4  mov     rax, rsp
0x1800199e7  mov     [rax+8], rbx
0x1800199eb  push    rbp
0x1800199ec  lea     rbp, [rax-118h]
0x1800199f3  sub     rsp, 210h
0x1800199fa  movaps  xmmword ptr [rax-18h], xmm6
0x1800199fe  mov     rax, cs:__security_cookie
0x180019a05  xor     rax, rsp
0x180019a08  mov     [rbp+110h+var_20], rax
0x180019a0f  lea     rcx, [rbp+110h+var_A0]
0x180019a13  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180019a18  nop
0x180019a19  lea     rcx, [rbp+110h+var_C0]
0x180019a1d  call    ?GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)
0x180019a22  nop
0x180019a23  cmp     qword ptr [rax+18h], 0Fh
0x180019a28  jbe     short loc_180019A2F
0x180019a2a  mov     r8, [rax]
0x180019a2d  jmp     short loc_180019A32
0x180019a2f  mov     r8, rax
0x180019a32  mov     r9, [rax+10h]
0x180019a36  add     r9, r8
0x180019a39  lea     rdx, [rbp+110h+var_E0]
0x180019a3d  lea     rcx, [rbp+110h+var_A0]
0x180019a41  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x180019a46  nop
0x180019a47  lea     rcx, [rbp+110h+var_C0]
0x180019a4b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180019a50  xorps   xmm0, xmm0
0x180019a53  movups  xmmword ptr [rbp+110h+pwszUrl], xmm0
0x180019a57  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180019a5f  movdqu  [rbp+110h+var_178], xmm6
0x180019a64  xor     eax, eax
0x180019a66  mov     [rbp+110h+pwszUrl], ax
0x180019a6a  lea     r8, [rbp+110h+pwszUrl]
0x180019a6e  lea     rdx, aHttpsZtdDdsMic; "https://ztd.dds.microsoft.com/ztd/devic"...
0x180019a75  lea     rcx, aDdsztdmarkreme; "DdsZtdMarkRemediationUri"
0x180019a7c  call    ?GetRegistryDownloadKey@DirectDdsDownloadManagerBase@Autopilot@Windows@Microsoft@@SAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::GetRegistryDownloadKey(ushort const *,ushort const *,std::wstring &)
0x180019a81  mov     ebx, eax
0x180019a83  test    eax, eax
0x180019a85  jns     loc_180019B18
0x180019a8b  mov     rcx, [rbp+118h]; this
0x180019a92  mov     r9d, eax; char *
0x180019a95  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x180019a9c  mov     edx, 81h; void *
0x180019aa1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019aa6  nop
0x180019aa7  lea     rcx, [rbp+110h+pwszUrl]
0x180019aab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019ab0  nop
0x180019ab1  lea     rcx, [rbp+110h+var_E0]
0x180019ab5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019aba  nop
0x180019abb  lea     rax, ??_7?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x180019ac2  mov     [rbp+110h+var_A0], rax
0x180019ac6  lea     rcx, [rbp+110h+var_60]
0x180019acd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019ad2  lea     rcx, [rbp+110h+var_80]
0x180019ad9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180019ade  mov     rcx, [rbp+110h+var_88]
0x180019ae5  test    rcx, rcx
0x180019ae8  jz      short loc_180019B11
0x180019aea  mov     rax, [rcx]
0x180019aed  mov     rax, [rax+10h]
0x180019af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019af6  mov     r8, rax
0x180019af9  test    rax, rax
0x180019afc  jz      short loc_180019B11
0x180019afe  mov     rcx, [rax]
0x180019b01  mov     rax, [rcx]
0x180019b04  mov     edx, 1
0x180019b09  mov     rcx, r8
0x180019b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b11  mov     eax, ebx
0x180019b13  jmp     loc_180019DEC
0x180019b18  xorps   xmm0, xmm0
0x180019b1b  movups  [rbp+110h+var_100], xmm0
0x180019b1f  movdqu  [rbp+110h+var_F0], xmm6
0x180019b24  xor     eax, eax
0x180019b26  mov     word ptr [rbp+110h+var_100], ax
0x180019b2a  lea     r8, [rbp+110h+var_100]
0x180019b2e  lea     rdx, aHttpsZtdDdsMic_0; "https://ztd.dds.microsoft.com"
0x180019b35  lea     rcx, aDdsztdmsaticke; "DdsZtdMsaTicketUri"
0x180019b3c  call    ?GetRegistryDownloadKey@DirectDdsDownloadManagerBase@Autopilot@Windows@Microsoft@@SAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::GetRegistryDownloadKey(ushort const *,ushort const *,std::wstring &)
0x180019b41  mov     ebx, eax
0x180019b43  test    eax, eax
0x180019b45  jns     short loc_180019B71
0x180019b47  mov     rcx, [rbp+118h]; this
0x180019b4e  mov     r9d, eax; char *
0x180019b51  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x180019b58  mov     edx, 84h; void *
0x180019b5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019b62  nop
0x180019b63  lea     rcx, [rbp+110h+var_100]
0x180019b67  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019b6c  jmp     loc_180019AA7
0x180019b71  xorps   xmm0, xmm0
0x180019b74  movups  [rbp+110h+var_160], xmm0
0x180019b78  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180019b80  movdqa  [rbp+110h+var_150], xmm1
0x180019b85  xor     eax, eax
0x180019b87  mov     word ptr [rbp+110h+var_160], ax
0x180019b8b  movups  [rbp+110h+var_140], xmm0
0x180019b8f  movdqa  [rbp+110h+var_130], xmm1
0x180019b94  mov     word ptr [rbp+110h+var_140], ax
0x180019b98  movdqa  xmmword ptr [rbp+110h+var_120], xmm0
0x180019b9d  mov     [rbp+110h+hInternet], rax
0x180019ba1  movups  xmmword ptr [rsp+210h+var_1B0+8], xmm0
0x180019ba6  mov     [rsp+210h+var_198], rax
0x180019bab  mov     [rbp+110h+var_190], 7
0x180019bb3  mov     word ptr [rsp+210h+var_1B0+8], ax
0x180019bb8  lea     rax, [rsp+210h+var_1B0+8]
0x180019bbd  mov     [rsp+210h+var_1E0], rax; __int64
0x180019bc2  mov     qword ptr [rsp+210h+var_1E8], 0; int
0x180019bcb  mov     qword ptr [rsp+210h+var_1F0], 0; int
0x180019bd4  lea     r9, [rbp+110h+var_E0]
0x180019bd8  lea     r8, [rbp+110h+var_100]
0x180019bdc  lea     rdx, [rbp+110h+pwszUrl]; pwszUrl
0x180019be0  lea     rcx, [rbp+110h+var_160]; this
0x180019be4  call    ?MarkDeviceAsRemediationRequired@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00PEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@QEBUTimeoutOverride@1234@AEAV56@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::MarkDeviceAsRemediationRequired(std::wstring const &,std::wstring const &,std::wstring const &,std::map<std::wstring,std::wstring> const *,Microsoft::Windows::Autopilot::DdsNetworkWrapper::TimeoutOverride const * const,std::wstring &)
0x180019be9  mov     ebx, eax
0x180019beb  test    eax, eax
0x180019bed  jns     short loc_180019C6C
0x180019bef  mov     edx, 88h; void *
0x180019bf4  mov     r9d, ebx; char *
0x180019bf7  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x180019bfe  mov     rcx, [rbp+118h]; this
0x180019c05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019c0a  nop
0x180019c0b  lea     rcx, [rsp+210h+var_1B0+8]
0x180019c10  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019c15  nop
0x180019c16  mov     rcx, [rbp+110h+hInternet]; hInternet
0x180019c1a  test    rcx, rcx
0x180019c1d  jz      short loc_180019C2B
0x180019c1f  call    cs:__imp_WinHttpCloseHandle
0x180019c26  nop     dword ptr [rax+rax+00h]
0x180019c2b  mov     rcx, [rbp+110h+var_120+8]; hInternet
0x180019c2f  test    rcx, rcx
0x180019c32  jz      short loc_180019C40
0x180019c34  call    cs:__imp_WinHttpCloseHandle
0x180019c3b  nop     dword ptr [rax+rax+00h]
0x180019c40  mov     rcx, [rbp+110h+var_120]; hInternet
0x180019c44  test    rcx, rcx
0x180019c47  jz      short loc_180019C55
0x180019c49  call    cs:__imp_WinHttpCloseHandle
0x180019c50  nop     dword ptr [rax+rax+00h]
0x180019c55  lea     rcx, [rbp+110h+var_140]
0x180019c59  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019c5e  lea     rcx, [rbp+110h+var_160]
0x180019c62  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019c67  jmp     loc_180019B63
0x180019c6c  lea     rax, [rsp+210h+var_1D0+8]
0x180019c71  mov     qword ptr [rsp+210h+var_1D0], rax
0x180019c76  xorps   xmm0, xmm0
0x180019c79  movups  xmmword ptr [rsp+210h+var_1D0+8], xmm0
0x180019c7e  mov     [rsp+210h+var_1B8], 0
0x180019c87  mov     qword ptr [rsp+210h+var_1B0], 0
0x180019c90  lea     rdx, [rsp+210h+var_1B0+8]
0x180019c95  cmp     [rbp+110h+var_190], 7
0x180019c9a  cmova   rdx, qword ptr [rsp+210h+var_1B0+8]
0x180019ca0  mov     r8, [rsp+210h+var_198]
0x180019ca5  lea     rcx, [rsp+210h+var_1D0+8]
0x180019caa  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180019caf  nop
0x180019cb0  xorps   xmm0, xmm0
0x180019cb3  movups  [rbp+110h+var_C0], xmm0
0x180019cb7  xorps   xmm1, xmm1
0x180019cba  movdqu  [rbp+110h+var_B0], xmm1
0x180019cbf  mov     r8d, 21h ; '!'
0x180019cc5  lea     rdx, aMarkremediatio; "MarkRemediationStatusResponse.txt"
0x180019ccc  lea     rcx, [rbp+110h+var_C0]
0x180019cd0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180019cd5  nop
0x180019cd6  lea     r8, [rsp+210h+var_1D0+8]
0x180019cdb  lea     rdx, [rbp+110h+var_C0]
0x180019cdf  xor     ecx, ecx
0x180019ce1  call    ?WriteStringToStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(Microsoft::Windows::Autopilot::StorageMethod,std::wstring const &,std::wstring)
0x180019ce6  mov     ebx, eax
0x180019ce8  lea     rcx, [rbp+110h+var_C0]
0x180019cec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019cf1  test    ebx, ebx
0x180019cf3  jns     short loc_180019CFF
0x180019cf5  mov     edx, 89h
0x180019cfa  jmp     loc_180019BF4
0x180019cff  lea     rcx, [rsp+210h+var_1B0+8]
0x180019d04  call    ?ProcessRemediationResult@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::HardwareInfo::ProcessRemediationResult(std::wstring const &)
0x180019d09  mov     ebx, eax
0x180019d0b  test    eax, eax
0x180019d0d  jns     short loc_180019D19
0x180019d0f  mov     edx, 8Bh
0x180019d14  jmp     loc_180019BF4
0x180019d19  lea     rcx, [rsp+210h+var_1B0+8]
0x180019d1e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019d23  nop
0x180019d24  mov     rcx, [rbp+110h+hInternet]; hInternet
0x180019d28  test    rcx, rcx
0x180019d2b  jz      short loc_180019D39
0x180019d2d  call    cs:__imp_WinHttpCloseHandle
0x180019d34  nop     dword ptr [rax+rax+00h]
0x180019d39  mov     rcx, [rbp+110h+var_120+8]; hInternet
0x180019d3d  test    rcx, rcx
0x180019d40  jz      short loc_180019D4E
0x180019d42  call    cs:__imp_WinHttpCloseHandle
0x180019d49  nop     dword ptr [rax+rax+00h]
0x180019d4e  mov     rcx, [rbp+110h+var_120]; hInternet
0x180019d52  test    rcx, rcx
0x180019d55  jz      short loc_180019D63
0x180019d57  call    cs:__imp_WinHttpCloseHandle
0x180019d5e  nop     dword ptr [rax+rax+00h]
0x180019d63  lea     rcx, [rbp+110h+var_140]
0x180019d67  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019d6c  lea     rcx, [rbp+110h+var_160]
0x180019d70  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019d75  nop
0x180019d76  lea     rcx, [rbp+110h+var_100]
0x180019d7a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019d7f  nop
0x180019d80  lea     rcx, [rbp+110h+pwszUrl]
0x180019d84  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019d89  nop
0x180019d8a  lea     rcx, [rbp+110h+var_E0]
0x180019d8e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019d93  nop
0x180019d94  lea     rax, ??_7?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x180019d9b  mov     [rbp+110h+var_A0], rax
0x180019d9f  lea     rcx, [rbp+110h+var_60]
0x180019da6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019dab  lea     rcx, [rbp+110h+var_80]
0x180019db2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180019db7  mov     rcx, [rbp+110h+var_88]
0x180019dbe  test    rcx, rcx
0x180019dc1  jz      short loc_180019DEA
0x180019dc3  mov     rax, [rcx]
0x180019dc6  mov     rax, [rax+10h]
0x180019dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dcf  mov     r8, rax
0x180019dd2  test    rax, rax
0x180019dd5  jz      short loc_180019DEA
0x180019dd7  mov     rcx, [rax]
0x180019dda  mov     rax, [rcx]
0x180019ddd  mov     edx, 1
0x180019de2  mov     rcx, r8
0x180019de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dea  xor     eax, eax
0x180019dec  mov     rcx, [rbp+110h+var_20]
0x180019df3  xor     rcx, rsp; StackCookie
0x180019df6  call    __security_check_cookie
0x180019dfb  lea     r11, [rsp+210h+var_s0]
0x180019e03  mov     rbx, [r11+10h]
0x180019e07  movaps  xmm6, xmmword ptr [r11-10h]
0x180019e0c  mov     rsp, r11
0x180019e0f  pop     rbp
0x180019e10  retn
```
