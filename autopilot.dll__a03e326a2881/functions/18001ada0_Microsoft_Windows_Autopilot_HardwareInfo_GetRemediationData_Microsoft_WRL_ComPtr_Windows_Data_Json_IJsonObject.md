# Microsoft::Windows::Autopilot::HardwareInfo::GetRemediationData(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::Windows::Autopilot::HardwareComponentsCacheType)

- ea: `0x18001ada0`
- end: `0x18001b0ba`
- name: `?GetRemediationData@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@W4HardwareComponentsCacheType@234@@Z`
- size: `794`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023cb0`

## callees

- `0x1800045b0`
- `0x18000ec40`
- `0x1800105f4`
- `0x1800174f0`
- `0x180018120`
- `0x180019ef0`
- `0x18001a280`
- `0x18001a4e4`
- `0x18001ab88`
- `0x18001ada0`
- `0x18001e7b4`
- `0x18001ea04`
- `0x1800203bc`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ade4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ade4`

## string_xrefs

- `0x18001addd`: `Windows.Data.Json.JsonObject`
- `0x18001ae29`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001ae72`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001aeb6`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001af26`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001afb0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001aff7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b03e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::GetRemediationData(
        struct Windows::Data::Json::IJsonObject **a1)
{
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  int v5; // eax
  unsigned int v6; // ebx
  struct Windows::Data::Json::IJsonObject *v7; // rcx
  int CachedHardwareBlob; // eax
  struct Windows::Data::Json::IJsonObject *v10; // rcx
  int CurrentHardwareBlob; // eax
  struct Windows::Data::Json::IJsonObject *v12; // rcx
  unsigned int v13; // edi
  int v14; // eax
  __int64 v15; // rdx
  _WORD *p_hstringHeader; // rcx
  const unsigned __int16 *Reserved1; // r8
  struct Windows::Data::Json::IJsonObject *v18; // rcx
  int AutopilotProfile; // eax
  struct Windows::Data::Json::IJsonObject *v20; // rcx
  int MsaTicket; // eax
  struct Windows::Data::Json::IJsonObject *v22; // rcx
  struct Windows::Data::Json::IJsonObject *v23; // rcx
  struct Windows::Data::Json::IJsonObject *v24; // [rsp+20h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-28h] BYREF
  HSTRING string; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  v24 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    JUMPOUT(0x18001B0B9LL);
  }
  v5 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(string, &v24);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v5,
      (int)v24);
    v7 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return v6;
  }
  CachedHardwareBlob = Microsoft::Windows::Autopilot::HardwareInfo::GetCachedHardwareBlob(&v24);
  v6 = CachedHardwareBlob;
  if ( CachedHardwareBlob < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)CachedHardwareBlob,
      (int)v24);
    v10 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return v6;
  }
  CurrentHardwareBlob = Microsoft::Windows::Autopilot::HardwareInfo::GetCurrentHardwareBlob(&v24);
  v6 = CurrentHardwareBlob;
  if ( CurrentHardwareBlob < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)CurrentHardwareBlob,
      (int)v24);
    v12 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v6;
  }
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  string = (HSTRING)7;
  LOWORD(hstringHeader.Reserved.Reserved1) = 0;
  v13 = 1;
  v14 = Microsoft::Windows::Autopilot::AutoPilotStateUtils::GetOrSetAutopilotMarker((__int64)&hstringHeader);
  v6 = v14;
  if ( v14 < 0 )
  {
    if ( v14 != -2147024895 )
    {
      v15 = 610;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
        (const char *)(unsigned int)v14,
        (int)v24);
      goto LABEL_28;
    }
    p_hstringHeader = &hstringHeader;
    if ( (unsigned __int64)string > 7 )
      p_hstringHeader = hstringHeader.Reserved.Reserved1;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
    *p_hstringHeader = 0;
    v13 = 0;
  }
  v14 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v24, L"IsUefiSupported", v13);
  v6 = v14;
  if ( v14 < 0 )
  {
    v15 = 618;
    goto LABEL_17;
  }
  Reserved1 = (const unsigned __int16 *)&hstringHeader;
  if ( (unsigned __int64)string > 7 )
    Reserved1 = (const unsigned __int16 *)hstringHeader.Reserved.Reserved1;
  v14 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v24, L"AutopilotDeviceMarker", Reserved1);
  v6 = v14;
  if ( v14 < 0 )
  {
    v15 = 619;
    goto LABEL_17;
  }
  v6 = 0;
LABEL_28:
  std::wstring::_Tidy_deallocate(&hstringHeader);
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)v6,
      (int)v24);
    v18 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return v6;
  }
  AutopilotProfile = Microsoft::Windows::Autopilot::HardwareInfo::GetAutopilotProfile(&v24);
  v6 = AutopilotProfile;
  if ( AutopilotProfile < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)AutopilotProfile,
      (int)v24);
    v20 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return v6;
  }
  MsaTicket = Microsoft::Windows::Autopilot::HardwareInfo::GetMsaTicket(&v24);
  v6 = MsaTicket;
  if ( MsaTicket < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)MsaTicket,
      (int)v24);
    v22 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v22 + 16LL))(v22);
    }
    return v6;
  }
  v23 = *a1;
  *a1 = v24;
  if ( v23 )
  {
    v24 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v23 + 16LL))(v23);
  }
  return 0;
}

```

## disassembly

```asm
0x18001ada0  mov     [rsp-18h+arg_8], rbx
0x18001ada5  mov     [rsp-18h+arg_10], rsi
0x18001adaa  push    rbp
0x18001adab  push    rdi
0x18001adac  push    r14
0x18001adae  mov     rbp, rsp
0x18001adb1  sub     rsp, 50h
0x18001adb5  mov     rax, cs:__security_cookie
0x18001adbc  xor     rax, rsp
0x18001adbf  mov     [rbp+var_8], rax
0x18001adc3  mov     rsi, rcx
0x18001adc6  xor     r14d, r14d
0x18001adc9  mov     [rbp+var_30], r14
0x18001adcd  mov     [rbp+string], r14
0x18001add1  lea     r9, [rbp+string]; string
0x18001add5  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001add9  lea     edx, [r14+1Ch]; length
0x18001addd  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18001ade4  call    cs:__imp_WindowsCreateStringReference
0x18001adea  test    eax, eax
0x18001adec  js      loc_18001B0B2
0x18001adf2  mov     rbx, [rbp+string]
0x18001adf6  mov     rcx, [rbp+var_30]
0x18001adfa  test    rcx, rcx
0x18001adfd  jz      short loc_18001AE10
0x18001adff  mov     [rbp+var_30], r14
0x18001ae03  mov     rax, [rcx]
0x18001ae06  mov     rax, [rax+10h]
0x18001ae0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae0f  nop
0x18001ae10  lea     rdx, [rbp+var_30]
0x18001ae14  mov     rcx, rbx
0x18001ae17  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18001ae1c  mov     ebx, eax
0x18001ae1e  test    eax, eax
0x18001ae20  jns     short loc_18001AE5C
0x18001ae22  mov     rcx, [rbp+18h]; this
0x18001ae26  mov     r9d, eax; char *
0x18001ae29  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ae30  mov     edx, 48h ; 'H'; void *
0x18001ae35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ae3a  nop
0x18001ae3b  mov     rcx, [rbp+var_30]
0x18001ae3f  test    rcx, rcx
0x18001ae42  jz      short loc_18001AE55
0x18001ae44  mov     [rbp+var_30], r14
0x18001ae48  mov     rax, [rcx]
0x18001ae4b  mov     rax, [rax+10h]
0x18001ae4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae54  nop
0x18001ae55  mov     eax, ebx
0x18001ae57  jmp     loc_18001B091
0x18001ae5c  lea     rcx, [rbp+var_30]
0x18001ae60  call    ?GetCachedHardwareBlob@HardwareInfo@Autopilot@Windows@Microsoft@@CAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@W4HardwareComponentsCacheType@234@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetCachedHardwareBlob(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::Windows::Autopilot::HardwareComponentsCacheType)
0x18001ae65  mov     ebx, eax
0x18001ae67  test    eax, eax
0x18001ae69  jns     short loc_18001AEA0
0x18001ae6b  mov     rcx, [rbp+18h]; this
0x18001ae6f  mov     r9d, eax; char *
0x18001ae72  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ae79  mov     edx, 4Bh ; 'K'; void *
0x18001ae7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ae83  nop
0x18001ae84  mov     rcx, [rbp+var_30]
0x18001ae88  test    rcx, rcx
0x18001ae8b  jz      short loc_18001AE9E
0x18001ae8d  mov     [rbp+var_30], r14
0x18001ae91  mov     rax, [rcx]
0x18001ae94  mov     rax, [rax+10h]
0x18001ae98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae9d  nop
0x18001ae9e  jmp     short loc_18001AE55
0x18001aea0  lea     rcx, [rbp+var_30]
0x18001aea4  call    ?GetCurrentHardwareBlob@HardwareInfo@Autopilot@Windows@Microsoft@@CAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetCurrentHardwareBlob(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x18001aea9  mov     ebx, eax
0x18001aeab  test    eax, eax
0x18001aead  jns     short loc_18001AEE7
0x18001aeaf  mov     rcx, [rbp+18h]; this
0x18001aeb3  mov     r9d, eax; char *
0x18001aeb6  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001aebd  mov     edx, 4Ch ; 'L'; void *
0x18001aec2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aec7  nop
0x18001aec8  mov     rcx, [rbp+var_30]
0x18001aecc  test    rcx, rcx
0x18001aecf  jz      short loc_18001AEE2
0x18001aed1  mov     [rbp+var_30], r14
0x18001aed5  mov     rax, [rcx]
0x18001aed8  mov     rax, [rax+10h]
0x18001aedc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aee1  nop
0x18001aee2  jmp     loc_18001AE55
0x18001aee7  xorps   xmm0, xmm0
0x18001aeea  movups  xmmword ptr [rbp+hstringHeader.Reserved], xmm0
0x18001aeee  mov     qword ptr [rbp+hstringHeader.Reserved+10h], r14
0x18001aef2  mov     [rbp+string], 7
0x18001aefa  mov     word ptr [rbp+hstringHeader.Reserved], r14w
0x18001aeff  mov     edi, 1
0x18001af04  lea     rcx, [rbp+hstringHeader]
0x18001af08  call    ?GetOrSetAutopilotMarker@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::GetOrSetAutopilotMarker(std::wstring &)
0x18001af0d  mov     ebx, eax
0x18001af0f  test    eax, eax
0x18001af11  jns     short loc_18001AF4E
0x18001af13  cmp     eax, 80070001h
0x18001af18  jz      short loc_18001AF35
0x18001af1a  mov     edx, 262h; void *
0x18001af1f  mov     rcx, [rbp+18h]; this
0x18001af23  mov     r9d, eax; char *
0x18001af26  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001af2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001af32  nop
0x18001af33  jmp     short loc_18001AF9C
0x18001af35  lea     rcx, [rbp+hstringHeader]
0x18001af39  cmp     [rbp+string], 7
0x18001af3e  cmova   rcx, qword ptr [rbp+hstringHeader.Reserved]
0x18001af43  mov     qword ptr [rbp+hstringHeader.Reserved+10h], r14
0x18001af47  mov     [rcx], r14w
0x18001af4b  mov     edi, r14d
0x18001af4e  mov     r8d, edi; unsigned int
0x18001af51  lea     rdx, aIsuefisupporte; "IsUefiSupported"
0x18001af58  mov     rcx, [rbp+var_30]; struct Windows::Data::Json::IJsonObject *
0x18001af5c  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x18001af61  mov     ebx, eax
0x18001af63  test    eax, eax
0x18001af65  jns     short loc_18001AF6E
0x18001af67  mov     edx, 26Ah
0x18001af6c  jmp     short loc_18001AF1F
0x18001af6e  lea     r8, [rbp+hstringHeader]
0x18001af72  cmp     [rbp+string], 7
0x18001af77  cmova   r8, qword ptr [rbp+hstringHeader.Reserved]; unsigned __int16 *
0x18001af7c  lea     rdx, aAutopilotdevic; "AutopilotDeviceMarker"
0x18001af83  mov     rcx, [rbp+var_30]; struct Windows::Data::Json::IJsonObject *
0x18001af87  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18001af8c  mov     ebx, eax
0x18001af8e  test    eax, eax
0x18001af90  jns     short loc_18001AF99
0x18001af92  mov     edx, 26Bh
0x18001af97  jmp     short loc_18001AF1F
0x18001af99  mov     ebx, r14d
0x18001af9c  lea     rcx, [rbp+hstringHeader]
0x18001afa0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001afa5  test    ebx, ebx
0x18001afa7  jns     short loc_18001AFE1
0x18001afa9  mov     rcx, [rbp+18h]; this
0x18001afad  mov     r9d, ebx; char *
0x18001afb0  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001afb7  mov     edx, 4Dh ; 'M'; void *
0x18001afbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001afc1  nop
0x18001afc2  mov     rcx, [rbp+var_30]
0x18001afc6  test    rcx, rcx
0x18001afc9  jz      short loc_18001AFDC
0x18001afcb  mov     [rbp+var_30], r14
0x18001afcf  mov     rdx, [rcx]
0x18001afd2  mov     rax, [rdx+10h]
0x18001afd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afdb  nop
0x18001afdc  jmp     loc_18001AE55
0x18001afe1  lea     rcx, [rbp+var_30]
0x18001afe5  call    ?GetAutopilotProfile@HardwareInfo@Autopilot@Windows@Microsoft@@CAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetAutopilotProfile(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x18001afea  mov     ebx, eax
0x18001afec  test    eax, eax
0x18001afee  jns     short loc_18001B028
0x18001aff0  mov     rcx, [rbp+18h]; this
0x18001aff4  mov     r9d, eax; char *
0x18001aff7  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001affe  mov     edx, 4Eh ; 'N'; void *
0x18001b003  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b008  nop
0x18001b009  mov     rcx, [rbp+var_30]
0x18001b00d  test    rcx, rcx
0x18001b010  jz      short loc_18001B023
0x18001b012  mov     [rbp+var_30], r14
0x18001b016  mov     rax, [rcx]
0x18001b019  mov     rax, [rax+10h]
0x18001b01d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b022  nop
0x18001b023  jmp     loc_18001AE55
0x18001b028  lea     rcx, [rbp+var_30]
0x18001b02c  call    ?GetMsaTicket@HardwareInfo@Autopilot@Windows@Microsoft@@CAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetMsaTicket(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x18001b031  mov     ebx, eax
0x18001b033  test    eax, eax
0x18001b035  jns     short loc_18001B06F
0x18001b037  mov     rcx, [rbp+18h]; this
0x18001b03b  mov     r9d, eax; char *
0x18001b03e  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b045  mov     edx, 4Fh ; 'O'; void *
0x18001b04a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b04f  nop
0x18001b050  mov     rcx, [rbp+var_30]
0x18001b054  test    rcx, rcx
0x18001b057  jz      short loc_18001B06A
0x18001b059  mov     [rbp+var_30], r14
0x18001b05d  mov     rax, [rcx]
0x18001b060  mov     rax, [rax+10h]
0x18001b064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b069  nop
0x18001b06a  jmp     loc_18001AE55
0x18001b06f  mov     rcx, [rsi]
0x18001b072  mov     rax, [rbp+var_30]
0x18001b076  mov     [rsi], rax
0x18001b079  test    rcx, rcx
0x18001b07c  jz      short loc_18001B08F
0x18001b07e  mov     [rbp+var_30], r14
0x18001b082  mov     rax, [rcx]
0x18001b085  mov     rax, [rax+10h]
0x18001b089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b08e  nop
0x18001b08f  xor     eax, eax
0x18001b091  mov     rcx, [rbp+var_8]
0x18001b095  xor     rcx, rsp; StackCookie
0x18001b098  call    __security_check_cookie
0x18001b09d  lea     r11, [rsp+50h+var_s0]
0x18001b0a2  mov     rbx, [r11+28h]
0x18001b0a6  mov     rsi, [r11+30h]
0x18001b0aa  mov     rsp, r11
0x18001b0ad  pop     r14
0x18001b0af  pop     rdi
0x18001b0b0  pop     rbp
0x18001b0b1  retn
0x18001b0b2  mov     ecx, eax; this
0x18001b0b4  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
