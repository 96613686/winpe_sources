# Microsoft::Windows::Autopilot::HardwareInfo::GetRemediationData(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::Windows::Autopilot::HardwareComponentsCacheType)

- ea: `0x18001b430`
- end: `0x18001b751`
- name: `?GetRemediationData@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@W4HardwareComponentsCacheType@234@@Z`
- size: `801`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024878`

## callees

- `0x1800045d0`
- `0x18000ed44`
- `0x180010764`
- `0x180017a20`
- `0x180018678`
- `0x18001a510`
- `0x18001a8b4`
- `0x18001ab2c`
- `0x18001b220`
- `0x18001b430`
- `0x18001f030`
- `0x18001f28c`
- `0x180020d20`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b474`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001b474`

## string_xrefs

- `0x18001b46d`: `Windows.Data.Json.JsonObject`
- `0x18001b4bf`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b508`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b54c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b5bc`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b646`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b68d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001b6d4`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`

## pseudocode

```c
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
  int v13; // eax
  __int64 v14; // rdx
  _WORD *p_hstringHeader; // rcx
  const unsigned __int16 *Reserved1; // r8
  struct Windows::Data::Json::IJsonObject *v17; // rcx
  int AutopilotProfile; // eax
  struct Windows::Data::Json::IJsonObject *v19; // rcx
  int MsaTicket; // eax
  struct Windows::Data::Json::IJsonObject *v21; // rcx
  struct Windows::Data::Json::IJsonObject *v22; // rcx
  struct Windows::Data::Json::IJsonObject *v23; // [rsp+20h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-28h] BYREF
  HSTRING string; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  v23 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    JUMPOUT(0x18001B750LL);
  }
  v5 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>((__int64)string, &v23);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)v5,
      (int)v23);
    v7 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return v6;
  }
  CachedHardwareBlob = Microsoft::Windows::Autopilot::HardwareInfo::GetCachedHardwareBlob(&v23);
  v6 = CachedHardwareBlob;
  if ( CachedHardwareBlob < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)CachedHardwareBlob,
      (int)v23);
    v10 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return v6;
  }
  CurrentHardwareBlob = Microsoft::Windows::Autopilot::HardwareInfo::GetCurrentHardwareBlob(&v23);
  v6 = CurrentHardwareBlob;
  if ( CurrentHardwareBlob < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)CurrentHardwareBlob,
      (int)v23);
    v12 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v6;
  }
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  string = (HSTRING)7;
  LOWORD(hstringHeader.Reserved.Reserved1) = 0;
  v13 = Microsoft::Windows::Autopilot::AutoPilotStateUtils::GetOrSetAutopilotMarker((__int64)&hstringHeader);
  v6 = v13;
  if ( v13 < 0 )
  {
    if ( v13 != -2147024895 )
    {
      v14 = 610;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
        (const char *)(unsigned int)v13,
        (int)v23);
      goto LABEL_28;
    }
    p_hstringHeader = &hstringHeader;
    if ( (unsigned __int64)string > 7 )
      p_hstringHeader = hstringHeader.Reserved.Reserved1;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
    *p_hstringHeader = 0;
  }
  v13 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v23, L"IsUefiSupported");
  v6 = v13;
  if ( v13 < 0 )
  {
    v14 = 618;
    goto LABEL_17;
  }
  Reserved1 = (const unsigned __int16 *)&hstringHeader;
  if ( (unsigned __int64)string > 7 )
    Reserved1 = (const unsigned __int16 *)hstringHeader.Reserved.Reserved1;
  v13 = Microsoft::Windows::Autopilot::JsonHelpers::Append(v23, L"AutopilotDeviceMarker", Reserved1);
  v6 = v13;
  if ( v13 < 0 )
  {
    v14 = 619;
    goto LABEL_17;
  }
  v6 = 0;
LABEL_28:
  std::wstring::_Tidy_deallocate((char **)&hstringHeader);
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)v6,
      (int)v23);
    v17 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return v6;
  }
  AutopilotProfile = Microsoft::Windows::Autopilot::HardwareInfo::GetAutopilotProfile(&v23);
  v6 = AutopilotProfile;
  if ( AutopilotProfile < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)AutopilotProfile,
      (int)v23);
    v19 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return v6;
  }
  MsaTicket = Microsoft::Windows::Autopilot::HardwareInfo::GetMsaTicket(&v23);
  v6 = MsaTicket;
  if ( MsaTicket < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)(unsigned int)MsaTicket,
      (int)v23);
    v21 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v21 + 16LL))(v21);
    }
    return v6;
  }
  v22 = *a1;
  *a1 = v23;
  if ( v22 )
  {
    v23 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonObject *))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return 0;
}

```

## disassembly

```asm
0x18001b430  mov     [rsp-18h+arg_8], rbx
0x18001b435  mov     [rsp-18h+arg_10], rsi
0x18001b43a  push    rbp
0x18001b43b  push    rdi
0x18001b43c  push    r14
0x18001b43e  mov     rbp, rsp
0x18001b441  sub     rsp, 50h
0x18001b445  mov     rax, cs:__security_cookie
0x18001b44c  xor     rax, rsp
0x18001b44f  mov     [rbp+var_8], rax
0x18001b453  mov     rsi, rcx
0x18001b456  xor     r14d, r14d
0x18001b459  mov     [rbp+var_30], r14
0x18001b45d  mov     [rbp+string], r14
0x18001b461  lea     r9, [rbp+string]; string
0x18001b465  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001b469  lea     edx, [r14+1Ch]; length
0x18001b46d  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18001b474  call    cs:__imp_WindowsCreateStringReference
0x18001b47b  nop     dword ptr [rax+rax+00h]
0x18001b480  test    eax, eax
0x18001b482  js      loc_18001B749
0x18001b488  mov     rbx, [rbp+string]
0x18001b48c  mov     rcx, [rbp+var_30]
0x18001b490  test    rcx, rcx
0x18001b493  jz      short loc_18001B4A6
0x18001b495  mov     [rbp+var_30], r14
0x18001b499  mov     rax, [rcx]
0x18001b49c  mov     rax, [rax+10h]
0x18001b4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4a5  nop
0x18001b4a6  lea     rdx, [rbp+var_30]
0x18001b4aa  mov     rcx, rbx
0x18001b4ad  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x18001b4b2  mov     ebx, eax
0x18001b4b4  test    eax, eax
0x18001b4b6  jns     short loc_18001B4F2
0x18001b4b8  mov     rcx, [rbp+18h]; this
0x18001b4bc  mov     r9d, eax; char *
0x18001b4bf  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b4c6  mov     edx, 48h ; 'H'; void *
0x18001b4cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b4d0  nop
0x18001b4d1  mov     rcx, [rbp+var_30]
0x18001b4d5  test    rcx, rcx
0x18001b4d8  jz      short loc_18001B4EB
0x18001b4da  mov     [rbp+var_30], r14
0x18001b4de  mov     rax, [rcx]
0x18001b4e1  mov     rax, [rax+10h]
0x18001b4e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4ea  nop
0x18001b4eb  mov     eax, ebx
0x18001b4ed  jmp     loc_18001B727
0x18001b4f2  lea     rcx, [rbp+var_30]
0x18001b4f6  call    ?GetCachedHardwareBlob@HardwareInfo@Autopilot@Windows@Microsoft@@CAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@W4HardwareComponentsCacheType@234@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetCachedHardwareBlob(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &,Microsoft::Windows::Autopilot::HardwareComponentsCacheType)
0x18001b4fb  mov     ebx, eax
0x18001b4fd  test    eax, eax
0x18001b4ff  jns     short loc_18001B536
0x18001b501  mov     rcx, [rbp+18h]; this
0x18001b505  mov     r9d, eax; char *
0x18001b508  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b50f  mov     edx, 4Bh ; 'K'; void *
0x18001b514  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b519  nop
0x18001b51a  mov     rcx, [rbp+var_30]
0x18001b51e  test    rcx, rcx
0x18001b521  jz      short loc_18001B534
0x18001b523  mov     [rbp+var_30], r14
0x18001b527  mov     rax, [rcx]
0x18001b52a  mov     rax, [rax+10h]
0x18001b52e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b533  nop
0x18001b534  jmp     short loc_18001B4EB
0x18001b536  lea     rcx, [rbp+var_30]
0x18001b53a  call    ?GetCurrentHardwareBlob@HardwareInfo@Autopilot@Windows@Microsoft@@CAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetCurrentHardwareBlob(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x18001b53f  mov     ebx, eax
0x18001b541  test    eax, eax
0x18001b543  jns     short loc_18001B57D
0x18001b545  mov     rcx, [rbp+18h]; this
0x18001b549  mov     r9d, eax; char *
0x18001b54c  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b553  mov     edx, 4Ch ; 'L'; void *
0x18001b558  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b55d  nop
0x18001b55e  mov     rcx, [rbp+var_30]
0x18001b562  test    rcx, rcx
0x18001b565  jz      short loc_18001B578
0x18001b567  mov     [rbp+var_30], r14
0x18001b56b  mov     rax, [rcx]
0x18001b56e  mov     rax, [rax+10h]
0x18001b572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b577  nop
0x18001b578  jmp     loc_18001B4EB
0x18001b57d  xorps   xmm0, xmm0
0x18001b580  movups  xmmword ptr [rbp+hstringHeader.Reserved], xmm0
0x18001b584  mov     qword ptr [rbp+hstringHeader.Reserved+10h], r14
0x18001b588  mov     [rbp+string], 7
0x18001b590  mov     word ptr [rbp+hstringHeader.Reserved], r14w
0x18001b595  mov     edi, 1
0x18001b59a  lea     rcx, [rbp+hstringHeader]
0x18001b59e  call    ?GetOrSetAutopilotMarker@AutoPilotStateUtils@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutoPilotStateUtils::GetOrSetAutopilotMarker(std::wstring &)
0x18001b5a3  mov     ebx, eax
0x18001b5a5  test    eax, eax
0x18001b5a7  jns     short loc_18001B5E4
0x18001b5a9  cmp     eax, 80070001h
0x18001b5ae  jz      short loc_18001B5CB
0x18001b5b0  mov     edx, 262h; void *
0x18001b5b5  mov     rcx, [rbp+18h]; this
0x18001b5b9  mov     r9d, eax; char *
0x18001b5bc  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b5c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b5c8  nop
0x18001b5c9  jmp     short loc_18001B632
0x18001b5cb  lea     rcx, [rbp+hstringHeader]
0x18001b5cf  cmp     [rbp+string], 7
0x18001b5d4  cmova   rcx, qword ptr [rbp+hstringHeader.Reserved]
0x18001b5d9  mov     qword ptr [rbp+hstringHeader.Reserved+10h], r14
0x18001b5dd  mov     [rcx], r14w
0x18001b5e1  mov     edi, r14d
0x18001b5e4  mov     r8d, edi; unsigned int
0x18001b5e7  lea     rdx, aIsuefisupporte; "IsUefiSupported"
0x18001b5ee  mov     rcx, [rbp+var_30]; struct Windows::Data::Json::IJsonObject *
0x18001b5f2  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)
0x18001b5f7  mov     ebx, eax
0x18001b5f9  test    eax, eax
0x18001b5fb  jns     short loc_18001B604
0x18001b5fd  mov     edx, 26Ah
0x18001b602  jmp     short loc_18001B5B5
0x18001b604  lea     r8, [rbp+hstringHeader]
0x18001b608  cmp     [rbp+string], 7
0x18001b60d  cmova   r8, qword ptr [rbp+hstringHeader.Reserved]; unsigned __int16 *
0x18001b612  lea     rdx, aAutopilotdevic; "AutopilotDeviceMarker"
0x18001b619  mov     rcx, [rbp+var_30]; struct Windows::Data::Json::IJsonObject *
0x18001b61d  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)
0x18001b622  mov     ebx, eax
0x18001b624  test    eax, eax
0x18001b626  jns     short loc_18001B62F
0x18001b628  mov     edx, 26Bh
0x18001b62d  jmp     short loc_18001B5B5
0x18001b62f  mov     ebx, r14d
0x18001b632  lea     rcx, [rbp+hstringHeader]
0x18001b636  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b63b  test    ebx, ebx
0x18001b63d  jns     short loc_18001B677
0x18001b63f  mov     rcx, [rbp+18h]; this
0x18001b643  mov     r9d, ebx; char *
0x18001b646  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b64d  mov     edx, 4Dh ; 'M'; void *
0x18001b652  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b657  nop
0x18001b658  mov     rcx, [rbp+var_30]
0x18001b65c  test    rcx, rcx
0x18001b65f  jz      short loc_18001B672
0x18001b661  mov     [rbp+var_30], r14
0x18001b665  mov     rdx, [rcx]
0x18001b668  mov     rax, [rdx+10h]
0x18001b66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b671  nop
0x18001b672  jmp     loc_18001B4EB
0x18001b677  lea     rcx, [rbp+var_30]
0x18001b67b  call    ?GetAutopilotProfile@HardwareInfo@Autopilot@Windows@Microsoft@@CAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetAutopilotProfile(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x18001b680  mov     ebx, eax
0x18001b682  test    eax, eax
0x18001b684  jns     short loc_18001B6BE
0x18001b686  mov     rcx, [rbp+18h]; this
0x18001b68a  mov     r9d, eax; char *
0x18001b68d  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b694  mov     edx, 4Eh ; 'N'; void *
0x18001b699  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b69e  nop
0x18001b69f  mov     rcx, [rbp+var_30]
0x18001b6a3  test    rcx, rcx
0x18001b6a6  jz      short loc_18001B6B9
0x18001b6a8  mov     [rbp+var_30], r14
0x18001b6ac  mov     rax, [rcx]
0x18001b6af  mov     rax, [rax+10h]
0x18001b6b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6b8  nop
0x18001b6b9  jmp     loc_18001B4EB
0x18001b6be  lea     rcx, [rbp+var_30]
0x18001b6c2  call    ?GetMsaTicket@HardwareInfo@Autopilot@Windows@Microsoft@@CAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetMsaTicket(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x18001b6c7  mov     ebx, eax
0x18001b6c9  test    eax, eax
0x18001b6cb  jns     short loc_18001B705
0x18001b6cd  mov     rcx, [rbp+18h]; this
0x18001b6d1  mov     r9d, eax; char *
0x18001b6d4  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001b6db  mov     edx, 4Fh ; 'O'; void *
0x18001b6e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b6e5  nop
0x18001b6e6  mov     rcx, [rbp+var_30]
0x18001b6ea  test    rcx, rcx
0x18001b6ed  jz      short loc_18001B700
0x18001b6ef  mov     [rbp+var_30], r14
0x18001b6f3  mov     rax, [rcx]
0x18001b6f6  mov     rax, [rax+10h]
0x18001b6fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b6ff  nop
0x18001b700  jmp     loc_18001B4EB
0x18001b705  mov     rcx, [rsi]
0x18001b708  mov     rax, [rbp+var_30]
0x18001b70c  mov     [rsi], rax
0x18001b70f  test    rcx, rcx
0x18001b712  jz      short loc_18001B725
0x18001b714  mov     [rbp+var_30], r14
0x18001b718  mov     rax, [rcx]
0x18001b71b  mov     rax, [rax+10h]
0x18001b71f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b724  nop
0x18001b725  xor     eax, eax
0x18001b727  mov     rcx, [rbp+var_8]
0x18001b72b  xor     rcx, rsp; StackCookie
0x18001b72e  call    __security_check_cookie
0x18001b733  lea     r11, [rsp+50h+var_s0]
0x18001b738  mov     rbx, [r11+28h]
0x18001b73c  mov     rsi, [r11+30h]
0x18001b740  mov     rsp, r11
0x18001b743  pop     r14
0x18001b745  pop     rdi
0x18001b746  pop     rbp
0x18001b747  retn
0x18001b749  mov     ecx, eax; this
0x18001b74b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
