# Microsoft::Windows::Autopilot::HardwareInfo::CallApsWithRemediationData(void)

- ea: `0x1800193e4`
- end: `0x1800197ed`
- name: `?CallApsWithRemediationData@HardwareInfo@Autopilot@Windows@Microsoft@@SAJXZ`
- size: `1033`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001ba54`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x180013a40`
- `0x180013be0`
- `0x180014704`
- `0x180015898`
- `0x180017488`
- `0x1800174f0`
- `0x180017b84`
- `0x1800193e4`
- `0x18001bcf8`
- `0x18001ca58`
- `0x180023cb0`
- `0x1800252ec`
- `0x18002e010`

## import_xrefs

- `WINHTTP!WinHttpCloseHandle` at `0x18001961f`
- `WINHTTP!WinHttpCloseHandle` at `0x18001962e`
- `WINHTTP!WinHttpCloseHandle` at `0x18001963d`
- `WINHTTP!WinHttpCloseHandle` at `0x18001971b`
- `WINHTTP!WinHttpCloseHandle` at `0x18001972a`
- `WINHTTP!WinHttpCloseHandle` at `0x180019739`
- `WINHTTP!WinHttpCloseHandle` at `0x18001961f`
- `WINHTTP!WinHttpCloseHandle` at `0x18001962e`
- `WINHTTP!WinHttpCloseHandle` at `0x18001963d`
- `WINHTTP!WinHttpCloseHandle` at `0x18001971b`
- `WINHTTP!WinHttpCloseHandle` at `0x18001972a`
- `WINHTTP!WinHttpCloseHandle` at `0x180019739`

## string_xrefs

- `0x180019495`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x180019551`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x1800195f7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001946e`: `https://ztd.dds.microsoft.com/ztd/device/UpdateDeviceHardwareMismatchRemediationState`
- `0x180019475`: `DdsZtdMarkRemediationUri`
- `0x18001952e`: `https://ztd.dds.microsoft.com`
- `0x180019535`: `DdsZtdMsaTicketUri`

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
  void (__fastcall ***v9)(_QWORD, __int64); // rax
  int v10; // [rsp+28h] [rbp-E0h]
  int v11; // [rsp+28h] [rbp-E0h]
  _BYTE v12[40]; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v13; // [rsp+70h] [rbp-98h] BYREF
  __int64 v14; // [rsp+80h] [rbp-88h]
  __int64 v15; // [rsp+88h] [rbp-80h]
  WCHAR pwszUrl[8]; // [rsp+90h] [rbp-78h] BYREF
  __m128i v17; // [rsp+A0h] [rbp-68h]
  __int128 v18; // [rsp+B8h] [rbp-50h] BYREF
  __m128i v19; // [rsp+C8h] [rbp-40h]
  _OWORD v20[2]; // [rsp+D8h] [rbp-30h] BYREF
  HINTERNET v21[2]; // [rsp+F8h] [rbp-10h]
  HINTERNET hInternet; // [rsp+108h] [rbp+0h]
  _OWORD v23[2]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v24[32]; // [rsp+138h] [rbp+30h] BYREF
  _OWORD v25[2]; // [rsp+158h] [rbp+50h] BYREF
  _QWORD v26[3]; // [rsp+178h] [rbp+70h] BYREF
  __int64 v27; // [rsp+190h] [rbp+88h]
  _BYTE v28[32]; // [rsp+198h] [rbp+90h] BYREF
  _BYTE v29[64]; // [rsp+1B8h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+220h] [rbp+118h]

  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v26);
  AutopilotCorrelationVector = (_QWORD *)ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(v25);
  if ( AutopilotCorrelationVector[3] <= 0xFu )
    v1 = AutopilotCorrelationVector;
  else
    v1 = (_QWORD *)*AutopilotCorrelationVector;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
    v26,
    v24,
    v1,
    (char *)v1 + AutopilotCorrelationVector[2]);
  std::string::_Tidy_deallocate(v25);
  *(_OWORD *)pwszUrl = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v17 = si128;
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
      v10);
LABEL_6:
    std::wstring::_Tidy_deallocate(pwszUrl);
    std::wstring::_Tidy_deallocate(v24);
    v26[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
    std::wstring::_Tidy_deallocate(v29);
    std::string::_Tidy_deallocate(v28);
    if ( v27 )
    {
      v5 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      if ( v5 )
        (**v5)(v5, 1);
    }
    return (unsigned int)v4;
  }
  v23[0] = 0;
  v23[1] = si128;
  LOWORD(v23[0]) = 0;
  v7 = Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::GetRegistryDownloadKey(
         L"DdsZtdMsaTicketUri",
         L"https://ztd.dds.microsoft.com",
         v23);
  v4 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v7,
      v10);
LABEL_12:
    std::wstring::_Tidy_deallocate(v23);
    goto LABEL_6;
  }
  v18 = 0;
  v19 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v18) = 0;
  v20[0] = 0;
  v20[1] = v19;
  LOWORD(v20[0]) = 0;
  *(_OWORD *)v21 = 0;
  hInternet = 0;
  v13 = 0;
  v14 = 0;
  v15 = 7;
  LOWORD(v13) = 0;
  v4 = Microsoft::Windows::Autopilot::DdsNetworkWrapper::MarkDeviceAsRemediationRequired(
         (Microsoft::Windows::Autopilot::DdsNetworkWrapper *)&v18,
         pwszUrl,
         0,
         0,
         (__int64)&v13);
  if ( v4 < 0 )
  {
    v8 = 136;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v4,
      v11);
    std::wstring::_Tidy_deallocate(&v13);
    if ( hInternet )
      WinHttpCloseHandle(hInternet);
    if ( v21[1] )
      WinHttpCloseHandle(v21[1]);
    if ( v21[0] )
      WinHttpCloseHandle(v21[0]);
    std::wstring::_Tidy_deallocate(v20);
    std::wstring::_Tidy_deallocate(&v18);
    goto LABEL_12;
  }
  memset(&v12[8], 0, 32);
  std::wstring::_Construct<2,unsigned short const *>(&v12[8]);
  memset(v25, 0, sizeof(v25));
  std::wstring::_Construct<1,unsigned short const *>(v25, L"MarkRemediationStatusResponse.txt", 33);
  v4 = Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(
         0,
         (__int64)v25,
         (const unsigned __int16 *)&v12[8]);
  std::wstring::_Tidy_deallocate(v25);
  if ( v4 < 0 )
  {
    v8 = 137;
    goto LABEL_15;
  }
  v4 = Microsoft::Windows::Autopilot::HardwareInfo::ProcessRemediationResult(&v13);
  if ( v4 < 0 )
  {
    v8 = 139;
    goto LABEL_15;
  }
  std::wstring::_Tidy_deallocate(&v13);
  if ( hInternet )
    WinHttpCloseHandle(hInternet);
  if ( v21[1] )
    WinHttpCloseHandle(v21[1]);
  if ( v21[0] )
    WinHttpCloseHandle(v21[0]);
  std::wstring::_Tidy_deallocate(v20);
  std::wstring::_Tidy_deallocate(&v18);
  std::wstring::_Tidy_deallocate(v23);
  std::wstring::_Tidy_deallocate(pwszUrl);
  std::wstring::_Tidy_deallocate(v24);
  v26[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
  std::wstring::_Tidy_deallocate(v29);
  std::string::_Tidy_deallocate(v28);
  if ( v27 )
  {
    v9 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    if ( v9 )
      (**v9)(v9, 1);
  }
  return 0;
}

```

## disassembly

```asm
0x1800193e4  mov     rax, rsp
0x1800193e7  mov     [rax+8], rbx
0x1800193eb  push    rbp
0x1800193ec  lea     rbp, [rax-118h]
0x1800193f3  sub     rsp, 210h
0x1800193fa  movaps  xmmword ptr [rax-18h], xmm6
0x1800193fe  mov     rax, cs:__security_cookie
0x180019405  xor     rax, rsp
0x180019408  mov     [rbp+110h+var_20], rax
0x18001940f  lea     rcx, [rbp+110h+var_A0]
0x180019413  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180019418  nop
0x180019419  lea     rcx, [rbp+110h+var_C0]
0x18001941d  call    ?GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)
0x180019422  nop
0x180019423  cmp     qword ptr [rax+18h], 0Fh
0x180019428  jbe     short loc_18001942F
0x18001942a  mov     r8, [rax]
0x18001942d  jmp     short loc_180019432
0x18001942f  mov     r8, rax
0x180019432  mov     r9, [rax+10h]
0x180019436  add     r9, r8
0x180019439  lea     rdx, [rbp+110h+var_E0]
0x18001943d  lea     rcx, [rbp+110h+var_A0]
0x180019441  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x180019446  nop
0x180019447  lea     rcx, [rbp+110h+var_C0]
0x18001944b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180019450  xorps   xmm0, xmm0
0x180019453  movups  xmmword ptr [rbp+110h+pwszUrl], xmm0
0x180019457  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18001945f  movdqu  [rbp+110h+var_178], xmm6
0x180019464  xor     eax, eax
0x180019466  mov     [rbp+110h+pwszUrl], ax
0x18001946a  lea     r8, [rbp+110h+pwszUrl]
0x18001946e  lea     rdx, aHttpsZtdDdsMic; "https://ztd.dds.microsoft.com/ztd/devic"...
0x180019475  lea     rcx, aDdsztdmarkreme; "DdsZtdMarkRemediationUri"
0x18001947c  call    ?GetRegistryDownloadKey@DirectDdsDownloadManagerBase@Autopilot@Windows@Microsoft@@SAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::GetRegistryDownloadKey(ushort const *,ushort const *,std::wstring &)
0x180019481  mov     ebx, eax
0x180019483  test    eax, eax
0x180019485  jns     loc_180019518
0x18001948b  mov     rcx, [rbp+118h]; this
0x180019492  mov     r9d, eax; char *
0x180019495  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001949c  mov     edx, 81h; void *
0x1800194a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800194a6  nop
0x1800194a7  lea     rcx, [rbp+110h+pwszUrl]
0x1800194ab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800194b0  nop
0x1800194b1  lea     rcx, [rbp+110h+var_E0]
0x1800194b5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800194ba  nop
0x1800194bb  lea     rax, ??_7?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x1800194c2  mov     [rbp+110h+var_A0], rax
0x1800194c6  lea     rcx, [rbp+110h+var_60]
0x1800194cd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800194d2  lea     rcx, [rbp+110h+var_80]
0x1800194d9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800194de  mov     rcx, [rbp+110h+var_88]
0x1800194e5  test    rcx, rcx
0x1800194e8  jz      short loc_180019511
0x1800194ea  mov     rax, [rcx]
0x1800194ed  mov     rax, [rax+10h]
0x1800194f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194f6  mov     r8, rax
0x1800194f9  test    rax, rax
0x1800194fc  jz      short loc_180019511
0x1800194fe  mov     rcx, [rax]
0x180019501  mov     rax, [rcx]
0x180019504  mov     edx, 1
0x180019509  mov     rcx, r8
0x18001950c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019511  mov     eax, ebx
0x180019513  jmp     loc_1800197C8
0x180019518  xorps   xmm0, xmm0
0x18001951b  movups  [rbp+110h+var_100], xmm0
0x18001951f  movdqu  [rbp+110h+var_F0], xmm6
0x180019524  xor     eax, eax
0x180019526  mov     word ptr [rbp+110h+var_100], ax
0x18001952a  lea     r8, [rbp+110h+var_100]
0x18001952e  lea     rdx, aHttpsZtdDdsMic_0; "https://ztd.dds.microsoft.com"
0x180019535  lea     rcx, aDdsztdmsaticke; "DdsZtdMsaTicketUri"
0x18001953c  call    ?GetRegistryDownloadKey@DirectDdsDownloadManagerBase@Autopilot@Windows@Microsoft@@SAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::DirectDdsDownloadManagerBase::GetRegistryDownloadKey(ushort const *,ushort const *,std::wstring &)
0x180019541  mov     ebx, eax
0x180019543  test    eax, eax
0x180019545  jns     short loc_180019571
0x180019547  mov     rcx, [rbp+118h]; this
0x18001954e  mov     r9d, eax; char *
0x180019551  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x180019558  mov     edx, 84h; void *
0x18001955d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019562  nop
0x180019563  lea     rcx, [rbp+110h+var_100]
0x180019567  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001956c  jmp     loc_1800194A7
0x180019571  xorps   xmm0, xmm0
0x180019574  movups  [rbp+110h+var_160], xmm0
0x180019578  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180019580  movdqa  [rbp+110h+var_150], xmm1
0x180019585  xor     eax, eax
0x180019587  mov     word ptr [rbp+110h+var_160], ax
0x18001958b  movups  [rbp+110h+var_140], xmm0
0x18001958f  movdqa  [rbp+110h+var_130], xmm1
0x180019594  mov     word ptr [rbp+110h+var_140], ax
0x180019598  movdqa  xmmword ptr [rbp+110h+var_120], xmm0
0x18001959d  mov     [rbp+110h+hInternet], rax
0x1800195a1  movups  xmmword ptr [rsp+210h+var_1B0+8], xmm0
0x1800195a6  mov     [rsp+210h+var_198], rax
0x1800195ab  mov     [rbp+110h+var_190], 7
0x1800195b3  mov     word ptr [rsp+210h+var_1B0+8], ax
0x1800195b8  lea     rax, [rsp+210h+var_1B0+8]
0x1800195bd  mov     [rsp+210h+var_1E0], rax; __int64
0x1800195c2  mov     qword ptr [rsp+210h+var_1E8], 0; int
0x1800195cb  mov     qword ptr [rsp+210h+var_1F0], 0; int
0x1800195d4  lea     r9, [rbp+110h+var_E0]
0x1800195d8  lea     r8, [rbp+110h+var_100]
0x1800195dc  lea     rdx, [rbp+110h+pwszUrl]; pwszUrl
0x1800195e0  lea     rcx, [rbp+110h+var_160]; this
0x1800195e4  call    ?MarkDeviceAsRemediationRequired@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00PEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@6@QEBUTimeoutOverride@1234@AEAV56@@Z; Microsoft::Windows::Autopilot::DdsNetworkWrapper::MarkDeviceAsRemediationRequired(std::wstring const &,std::wstring const &,std::wstring const &,std::map<std::wstring,std::wstring> const *,Microsoft::Windows::Autopilot::DdsNetworkWrapper::TimeoutOverride const * const,std::wstring &)
0x1800195e9  mov     ebx, eax
0x1800195eb  test    eax, eax
0x1800195ed  jns     short loc_18001965A
0x1800195ef  mov     edx, 88h; void *
0x1800195f4  mov     r9d, ebx; char *
0x1800195f7  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800195fe  mov     rcx, [rbp+118h]; this
0x180019605  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001960a  nop
0x18001960b  lea     rcx, [rsp+210h+var_1B0+8]
0x180019610  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019615  nop
0x180019616  mov     rcx, [rbp+110h+hInternet]; hInternet
0x18001961a  test    rcx, rcx
0x18001961d  jz      short loc_180019625
0x18001961f  call    cs:__imp_WinHttpCloseHandle
0x180019625  mov     rcx, [rbp+110h+var_120+8]; hInternet
0x180019629  test    rcx, rcx
0x18001962c  jz      short loc_180019634
0x18001962e  call    cs:__imp_WinHttpCloseHandle
0x180019634  mov     rcx, [rbp+110h+var_120]; hInternet
0x180019638  test    rcx, rcx
0x18001963b  jz      short loc_180019643
0x18001963d  call    cs:__imp_WinHttpCloseHandle
0x180019643  lea     rcx, [rbp+110h+var_140]
0x180019647  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001964c  lea     rcx, [rbp+110h+var_160]
0x180019650  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019655  jmp     loc_180019563
0x18001965a  lea     rax, [rsp+210h+var_1D0+8]
0x18001965f  mov     qword ptr [rsp+210h+var_1D0], rax
0x180019664  xorps   xmm0, xmm0
0x180019667  movups  xmmword ptr [rsp+210h+var_1D0+8], xmm0
0x18001966c  mov     [rsp+210h+var_1B8], 0
0x180019675  mov     qword ptr [rsp+210h+var_1B0], 0
0x18001967e  lea     rdx, [rsp+210h+var_1B0+8]
0x180019683  cmp     [rbp+110h+var_190], 7
0x180019688  cmova   rdx, qword ptr [rsp+210h+var_1B0+8]
0x18001968e  mov     r8, [rsp+210h+var_198]
0x180019693  lea     rcx, [rsp+210h+var_1D0+8]
0x180019698  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18001969d  nop
0x18001969e  xorps   xmm0, xmm0
0x1800196a1  movups  [rbp+110h+var_C0], xmm0
0x1800196a5  xorps   xmm1, xmm1
0x1800196a8  movdqu  [rbp+110h+var_B0], xmm1
0x1800196ad  mov     r8d, 21h ; '!'
0x1800196b3  lea     rdx, aMarkremediatio; "MarkRemediationStatusResponse.txt"
0x1800196ba  lea     rcx, [rbp+110h+var_C0]
0x1800196be  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800196c3  nop
0x1800196c4  lea     r8, [rsp+210h+var_1D0+8]
0x1800196c9  lea     rdx, [rbp+110h+var_C0]
0x1800196cd  xor     ecx, ecx
0x1800196cf  call    ?WriteStringToStorage@HardwareInfo@Autopilot@Windows@Microsoft@@SAJW4StorageMethod@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V67@@Z; Microsoft::Windows::Autopilot::HardwareInfo::WriteStringToStorage(Microsoft::Windows::Autopilot::StorageMethod,std::wstring const &,std::wstring)
0x1800196d4  mov     ebx, eax
0x1800196d6  lea     rcx, [rbp+110h+var_C0]
0x1800196da  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800196df  test    ebx, ebx
0x1800196e1  jns     short loc_1800196ED
0x1800196e3  mov     edx, 89h
0x1800196e8  jmp     loc_1800195F4
0x1800196ed  lea     rcx, [rsp+210h+var_1B0+8]
0x1800196f2  call    ?ProcessRemediationResult@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::HardwareInfo::ProcessRemediationResult(std::wstring const &)
0x1800196f7  mov     ebx, eax
0x1800196f9  test    eax, eax
0x1800196fb  jns     short loc_180019707
0x1800196fd  mov     edx, 8Bh
0x180019702  jmp     loc_1800195F4
0x180019707  lea     rcx, [rsp+210h+var_1B0+8]
0x18001970c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019711  nop
0x180019712  mov     rcx, [rbp+110h+hInternet]; hInternet
0x180019716  test    rcx, rcx
0x180019719  jz      short loc_180019721
0x18001971b  call    cs:__imp_WinHttpCloseHandle
0x180019721  mov     rcx, [rbp+110h+var_120+8]; hInternet
0x180019725  test    rcx, rcx
0x180019728  jz      short loc_180019730
0x18001972a  call    cs:__imp_WinHttpCloseHandle
0x180019730  mov     rcx, [rbp+110h+var_120]; hInternet
0x180019734  test    rcx, rcx
0x180019737  jz      short loc_18001973F
0x180019739  call    cs:__imp_WinHttpCloseHandle
0x18001973f  lea     rcx, [rbp+110h+var_140]
0x180019743  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019748  lea     rcx, [rbp+110h+var_160]
0x18001974c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019751  nop
0x180019752  lea     rcx, [rbp+110h+var_100]
0x180019756  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001975b  nop
0x18001975c  lea     rcx, [rbp+110h+pwszUrl]
0x180019760  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019765  nop
0x180019766  lea     rcx, [rbp+110h+var_E0]
0x18001976a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001976f  nop
0x180019770  lea     rax, ??_7?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x180019777  mov     [rbp+110h+var_A0], rax
0x18001977b  lea     rcx, [rbp+110h+var_60]
0x180019782  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180019787  lea     rcx, [rbp+110h+var_80]
0x18001978e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180019793  mov     rcx, [rbp+110h+var_88]
0x18001979a  test    rcx, rcx
0x18001979d  jz      short loc_1800197C6
0x18001979f  mov     rax, [rcx]
0x1800197a2  mov     rax, [rax+10h]
0x1800197a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197ab  mov     r8, rax
0x1800197ae  test    rax, rax
0x1800197b1  jz      short loc_1800197C6
0x1800197b3  mov     rcx, [rax]
0x1800197b6  mov     rax, [rcx]
0x1800197b9  mov     edx, 1
0x1800197be  mov     rcx, r8
0x1800197c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800197c6  xor     eax, eax
0x1800197c8  mov     rcx, [rbp+110h+var_20]
0x1800197cf  xor     rcx, rsp; StackCookie
0x1800197d2  call    __security_check_cookie
0x1800197d7  lea     r11, [rsp+210h+var_s0]
0x1800197df  mov     rbx, [r11+10h]
0x1800197e3  movaps  xmm6, xmmword ptr [r11-10h]
0x1800197e8  mov     rsp, r11
0x1800197eb  pop     rbp
0x1800197ec  retn
```
