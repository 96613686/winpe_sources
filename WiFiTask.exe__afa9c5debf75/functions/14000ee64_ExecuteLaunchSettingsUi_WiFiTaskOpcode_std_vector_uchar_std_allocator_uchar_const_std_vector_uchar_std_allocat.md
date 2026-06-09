# ExecuteLaunchSettingsUi(WiFiTaskOpcode,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x14000ee64`
- end: `0x14000f1c1`
- name: `?ExecuteLaunchSettingsUi@@YAKW4WiFiTaskOpcode@@AEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z`
- size: `861`
- prototype: `__int64 __fastcall(__int64, _DWORD **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140006b40`

## callees

- `0x1400016a0`
- `0x14000bf20`
- `0x14000ee64`
- `0x1400100ec`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000f0e4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000f0e4`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x14000ee96`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x14000ee96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000eeee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000ef71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000efb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000eeee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000ef71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000efb5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000ef28`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000efef`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000ef28`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000efef`

## string_xrefs

- `0x14000f0b2`: `page=SettingsPageNetworkWiFi&target=SystemSettings_Connections_AdditionalWifiSettingsLink&invoke=true`
- `0x14000eee7`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall ExecuteLaunchSettingsUi(__int64 a1, _DWORD **a2)
{
  _DWORD *v2; // rbx
  int v3; // ecx
  char v4; // di
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  HSTRING v8; // rbx
  _QWORD *v9; // rcx
  HRESULT ActivationFactory; // ebx
  _QWORD *v11; // rbx
  __int64 v12; // rdi
  __int64 v13; // rcx
  HRESULT v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  HRESULT v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  HSTRING v20; // rbx
  __int64 v21; // rcx
  __int64 v22; // rbx
  __int64 (__fastcall *v23)(__int64, __int64, LPVOID *); // rdi
  LPVOID v24; // rcx
  LPVOID v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  _QWORD *v28; // rcx
  const wchar_t *v29; // rsi
  const wchar_t *v30; // rax
  const wchar_t *v31; // rdx
  __int64 v33; // [rsp+30h] [rbp-50h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-48h] BYREF
  __int64 v35; // [rsp+40h] [rbp-40h] BYREF
  _QWORD *v36; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF

  v2 = *a2;
  LODWORD(v33) = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v33, 0);
  if ( (unsigned int)v33 > 9 || (v3 = 586, v4 = 1, !_bittest(&v3, v33)) )
    v4 = 0;
  if ( *v2 == 2 && v4 )
  {
    v36 = 0;
    v35 = 0;
    v33 = 0;
    ppv = 0;
    string = 0;
    v5 = WindowsCreateStringReference(L"Windows.Foundation.Uri", 0x16u, &hstringHeader, &string);
    if ( v5 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
      __debugbreak();
    }
    v8 = string;
    v9 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    }
    ActivationFactory = RoGetActivationFactory(v8, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v36);
    if ( ActivationFactory >= 0 )
    {
      v11 = v36;
      v12 = *v36;
      v13 = v35;
      if ( v35 )
      {
        v35 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      string = 0;
      v14 = WindowsCreateStringReference(L"ms-availablenetworks:", 0x15u, &hstringHeader, &string);
      if ( v14 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v14, v15, v16);
        JUMPOUT(0x14000F1C0LL);
      }
      ActivationFactory = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v12 + 48))(v11, string, &v35);
      if ( ActivationFactory >= 0 )
      {
        string = 0;
        v17 = WindowsCreateStringReference(L"Windows.System.Launcher", 0x17u, &hstringHeader, &string);
        if ( v17 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
          __debugbreak();
        }
        v20 = string;
        v21 = v33;
        if ( v33 )
        {
          v33 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        ActivationFactory = RoGetActivationFactory(v20, &GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451, &v33);
        if ( ActivationFactory >= 0 )
        {
          v22 = v33;
          v23 = *(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v33 + 64LL);
          v24 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
          }
          ActivationFactory = v23(v22, v35, &ppv);
        }
      }
    }
    v25 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v26 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v27 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v28 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v28 + 16LL))(v28);
    }
  }
  else
  {
    LODWORD(v33) = 0;
    v29 = L"page=SettingsPageNetworkWiFi&target=SystemSettings_Connections_Wifi_Adapter_List&invoke=false";
    if ( *v2 == 1 )
    {
      v30 = L"page=SettingsPageNetworkWiFi&target=SystemSettings_Connections_AdditionalWifiSettingsLink&invoke=true";
      if ( v4 )
        v30 = L"page=SettingsPageNetworkWiFi&target=SystemSettings_Connections_Wifi_Adapter_List&invoke=false";
      v29 = v30;
    }
    ppv = 0;
    ActivationFactory = CoCreateInstance(
                          &CLSID_ApplicationActivationManager,
                          0,
                          1u,
                          &GUID_2e941141_7f97_4756_ba1d_9decde894a3d,
                          &ppv);
    if ( ActivationFactory >= 0 )
    {
      v31 = L"BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw5n1h2txyewy!App";
      if ( v4 )
        v31 = L"windows.immersivecontrolpanel_cw5n1h2txyewy!microsoft.windows.immersivecontrolpanel";
      ActivationFactory = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, const wchar_t *, _QWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(
                            ppv,
                            v31,
                            v29,
                            0,
                            &v33);
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      &WPP_d7e0deef0d8c389735c42bf67fb2c31a_Traceguids,
      (unsigned int)ActivationFactory);
  }
  if ( ActivationFactory < 0 )
  {
    if ( (ActivationFactory & 0x1FFF0000) == 0x70000 )
      return (unsigned __int16)ActivationFactory;
  }
  else
  {
    return 0;
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x14000ee64  push    rbp
0x14000ee66  push    rbx
0x14000ee67  push    rsi
0x14000ee68  push    rdi
0x14000ee69  push    r14
0x14000ee6b  mov     rbp, rsp
0x14000ee6e  sub     rsp, 80h
0x14000ee75  mov     rax, cs:__security_cookie
0x14000ee7c  xor     rax, rsp
0x14000ee7f  mov     [rbp+var_10], rax
0x14000ee83  mov     rbx, [rdx]
0x14000ee86  xor     r14d, r14d
0x14000ee89  mov     dword ptr [rbp+var_50], r14d
0x14000ee8d  xor     r8d, r8d
0x14000ee90  lea     rdx, [rbp+var_50]
0x14000ee94  xor     ecx, ecx
0x14000ee96  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x14000ee9c  mov     eax, dword ptr [rbp+var_50]
0x14000ee9f  cmp     eax, 9
0x14000eea2  ja      short loc_14000EEB1
0x14000eea4  mov     ecx, 24Ah
0x14000eea9  bt      ecx, eax
0x14000eeac  mov     dil, 1
0x14000eeaf  jb      short loc_14000EEB4
0x14000eeb1  mov     dil, r14b
0x14000eeb4  cmp     dword ptr [rbx], 2
0x14000eeb7  jnz     loc_14000F0A2
0x14000eebd  test    dil, dil
0x14000eec0  jz      loc_14000F0A2
0x14000eec6  mov     [rbp+var_38], r14
0x14000eeca  mov     [rbp+var_40], r14
0x14000eece  mov     [rbp+var_50], r14
0x14000eed2  mov     [rbp+var_48], r14
0x14000eed6  mov     [rbp+string], r14
0x14000eeda  lea     r9, [rbp+string]; string
0x14000eede  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14000eee2  mov     edx, 16h; length
0x14000eee7  lea     rcx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x14000eeee  call    cs:__imp_WindowsCreateStringReference
0x14000eef4  test    eax, eax
0x14000eef6  js      loc_14000F1B1
0x14000eefc  mov     rbx, [rbp+string]
0x14000ef00  mov     rcx, [rbp+var_38]
0x14000ef04  test    rcx, rcx
0x14000ef07  jz      short loc_14000EF1A
0x14000ef09  mov     [rbp+var_38], r14
0x14000ef0d  mov     rax, [rcx]
0x14000ef10  mov     rax, [rax+10h]
0x14000ef14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef19  nop
0x14000ef1a  lea     r8, [rbp+var_38]
0x14000ef1e  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x14000ef25  mov     rcx, rbx
0x14000ef28  call    cs:__imp_RoGetActivationFactory
0x14000ef2e  mov     ebx, eax
0x14000ef30  test    eax, eax
0x14000ef32  js      loc_14000F035
0x14000ef38  mov     rbx, [rbp+var_38]
0x14000ef3c  mov     rdi, [rbx]
0x14000ef3f  mov     rcx, [rbp+var_40]
0x14000ef43  test    rcx, rcx
0x14000ef46  jz      short loc_14000EF59
0x14000ef48  mov     [rbp+var_40], r14
0x14000ef4c  mov     rax, [rcx]
0x14000ef4f  mov     rax, [rax+10h]
0x14000ef53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef58  nop
0x14000ef59  mov     [rbp+string], r14
0x14000ef5d  lea     r9, [rbp+string]; string
0x14000ef61  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14000ef65  mov     edx, 15h; length
0x14000ef6a  lea     rcx, sourceString; "ms-availablenetworks:"
0x14000ef71  call    cs:__imp_WindowsCreateStringReference
0x14000ef77  test    eax, eax
0x14000ef79  js      loc_14000F1B9
0x14000ef7f  lea     r8, [rbp+var_40]
0x14000ef83  mov     rdx, [rbp+string]
0x14000ef87  mov     rcx, rbx
0x14000ef8a  mov     rax, [rdi+30h]
0x14000ef8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef93  mov     ebx, eax
0x14000ef95  test    eax, eax
0x14000ef97  js      loc_14000F035
0x14000ef9d  mov     [rbp+string], r14
0x14000efa1  lea     r9, [rbp+string]; string
0x14000efa5  lea     r8, [rbp+hstringHeader]; hstringHeader
0x14000efa9  mov     edx, 17h; length
0x14000efae  lea     rcx, ?RuntimeClass_Windows_System_Launcher@@3QBGB; "Windows.System.Launcher"
0x14000efb5  call    cs:__imp_WindowsCreateStringReference
0x14000efbb  test    eax, eax
0x14000efbd  js      loc_14000F1A9
0x14000efc3  mov     rbx, [rbp+string]
0x14000efc7  mov     rcx, [rbp+var_50]
0x14000efcb  test    rcx, rcx
0x14000efce  jz      short loc_14000EFE1
0x14000efd0  mov     [rbp+var_50], r14
0x14000efd4  mov     rax, [rcx]
0x14000efd7  mov     rax, [rax+10h]
0x14000efdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000efe0  nop
0x14000efe1  lea     r8, [rbp+var_50]
0x14000efe5  lea     rdx, _GUID_277151c3_9e3e_42f6_91a4_5dfdeb232451
0x14000efec  mov     rcx, rbx
0x14000efef  call    cs:__imp_RoGetActivationFactory
0x14000eff5  mov     ebx, eax
0x14000eff7  test    eax, eax
0x14000eff9  js      short loc_14000F035
0x14000effb  mov     rbx, [rbp+var_50]
0x14000efff  mov     rax, [rbx]
0x14000f002  mov     rdi, [rax+40h]
0x14000f006  mov     rcx, [rbp+var_48]
0x14000f00a  test    rcx, rcx
0x14000f00d  jz      short loc_14000F020
0x14000f00f  mov     [rbp+var_48], r14
0x14000f013  mov     rdx, [rcx]
0x14000f016  mov     rax, [rdx+10h]
0x14000f01a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f01f  nop
0x14000f020  lea     r8, [rbp+var_48]
0x14000f024  mov     rdx, [rbp+var_40]
0x14000f028  mov     rcx, rbx
0x14000f02b  mov     rax, rdi
0x14000f02e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f033  mov     ebx, eax
0x14000f035  mov     rcx, [rbp+var_48]
0x14000f039  test    rcx, rcx
0x14000f03c  jz      short loc_14000F04F
0x14000f03e  mov     [rbp+var_48], r14
0x14000f042  mov     rax, [rcx]
0x14000f045  mov     rax, [rax+10h]
0x14000f049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f04e  nop
0x14000f04f  mov     rcx, [rbp+var_50]
0x14000f053  test    rcx, rcx
0x14000f056  jz      short loc_14000F069
0x14000f058  mov     [rbp+var_50], r14
0x14000f05c  mov     rax, [rcx]
0x14000f05f  mov     rax, [rax+10h]
0x14000f063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f068  nop
0x14000f069  mov     rcx, [rbp+var_40]
0x14000f06d  test    rcx, rcx
0x14000f070  jz      short loc_14000F083
0x14000f072  mov     [rbp+var_40], r14
0x14000f076  mov     rax, [rcx]
0x14000f079  mov     rax, [rax+10h]
0x14000f07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f082  nop
0x14000f083  mov     rcx, [rbp+var_38]
0x14000f087  test    rcx, rcx
0x14000f08a  jz      short loc_14000F09D
0x14000f08c  mov     [rbp+var_38], r14
0x14000f090  mov     rax, [rcx]
0x14000f093  mov     rax, [rax+10h]
0x14000f097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f09c  nop
0x14000f09d  jmp     loc_14000F13C
0x14000f0a2  mov     dword ptr [rbp+var_50], r14d
0x14000f0a6  lea     rsi, aPageSettingspa; "page=SettingsPageNetworkWiFi&target=Sys"...
0x14000f0ad  cmp     dword ptr [rbx], 1
0x14000f0b0  jnz     short loc_14000F0C3
0x14000f0b2  lea     rax, aPageSettingspa_0; "page=SettingsPageNetworkWiFi&target=Sys"...
0x14000f0b9  test    dil, dil
0x14000f0bc  cmovnz  rax, rsi
0x14000f0c0  mov     rsi, rax
0x14000f0c3  mov     [rbp+var_48], r14
0x14000f0c7  lea     rax, [rbp+var_48]
0x14000f0cb  mov     [rsp+80h+ppv], rax; ppv
0x14000f0d0  lea     r9, _GUID_2e941141_7f97_4756_ba1d_9decde894a3d; riid
0x14000f0d7  xor     edx, edx; pUnkOuter
0x14000f0d9  lea     r8d, [rdx+1]; dwClsContext
0x14000f0dd  lea     rcx, CLSID_ApplicationActivationManager; rclsid
0x14000f0e4  call    cs:__imp_CoCreateInstance
0x14000f0ea  mov     ebx, eax
0x14000f0ec  test    eax, eax
0x14000f0ee  js      short loc_14000F126
0x14000f0f0  mov     rcx, [rbp+var_48]
0x14000f0f4  mov     rax, [rcx]
0x14000f0f7  lea     r8, aWindowsImmersi; "windows.immersivecontrolpanel_cw5n1h2tx"...
0x14000f0fe  lea     rdx, aBaeaef159bab47; "BAEAEF15-9BAB-47FC-800B-ACECAD2AE94B_cw"...
0x14000f105  test    dil, dil
0x14000f108  cmovnz  rdx, r8
0x14000f10c  lea     r8, [rbp+var_50]
0x14000f110  mov     [rsp+80h+ppv], r8
0x14000f115  xor     r9d, r9d
0x14000f118  mov     r8, rsi
0x14000f11b  mov     rax, [rax+18h]
0x14000f11f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f124  mov     ebx, eax
0x14000f126  mov     rcx, [rbp+var_48]
0x14000f12a  test    rcx, rcx
0x14000f12d  jz      short loc_14000F13C
0x14000f12f  mov     rax, [rcx]
0x14000f132  mov     rax, [rax+10h]
0x14000f136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f13b  nop
0x14000f13c  lea     rax, WPP_GLOBAL_Control
0x14000f143  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f14a  cmp     rcx, rax
0x14000f14d  jz      short loc_14000F173
0x14000f14f  cmp     byte ptr [rcx+19h], 4
0x14000f153  jb      short loc_14000F173
0x14000f155  test    byte ptr [rcx+1Ch], 1
0x14000f159  jz      short loc_14000F173
0x14000f15b  mov     edx, 17h
0x14000f160  mov     r9d, ebx
0x14000f163  lea     r8, WPP_d7e0deef0d8c389735c42bf67fb2c31a_Traceguids
0x14000f16a  mov     rcx, [rcx+10h]
0x14000f16e  call    WPP_SF_d
0x14000f173  test    ebx, ebx
0x14000f175  js      short loc_14000F17C
0x14000f177  mov     ebx, r14d
0x14000f17a  jmp     short loc_14000F18D
0x14000f17c  mov     eax, ebx
0x14000f17e  and     eax, 1FFF0000h
0x14000f183  cmp     eax, 70000h
0x14000f188  jnz     short loc_14000F18D
0x14000f18a  movzx   ebx, bx
0x14000f18d  mov     eax, ebx
0x14000f18f  mov     rcx, [rbp+var_10]
0x14000f193  xor     rcx, rsp; StackCookie
0x14000f196  call    __security_check_cookie
0x14000f19b  add     rsp, 80h
0x14000f1a2  pop     r14
0x14000f1a4  pop     rdi
0x14000f1a5  pop     rsi
0x14000f1a6  pop     rbx
0x14000f1a7  pop     rbp
0x14000f1a8  retn
0x14000f1a9  mov     ecx, eax; this
0x14000f1ab  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14000f1b0  int     3; Trap to Debugger
0x14000f1b1  mov     ecx, eax; this
0x14000f1b3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14000f1b8  int     3; Trap to Debugger
0x14000f1b9  mov     ecx, eax; this
0x14000f1bb  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
