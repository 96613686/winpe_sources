# DockedClient::DoTFLUpdate(tagAppUpdateResult *)

- ea: `0x1800310c0`
- end: `0x180031979`
- name: `?DoTFLUpdate@DockedClient@@UEAAJPEAUtagAppUpdateResult@@@Z`
- size: `2233`
- prototype: `__int64 __fastcall(DockedClient *this, struct tagAppUpdateResult *, __int64)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180007660`
- `0x180007dfc`
- `0x1800183f4`
- `0x18001ba70`
- `0x18001ee04`
- `0x180026b8c`
- `0x180028394`
- `0x18002a048`
- `0x18002a0c0`
- `0x1800310c0`
- `0x180031f7c`
- `0x1800328f0`
- `0x180032dd0`
- `0x180033b78`
- `0x180035658`
- `0x18003738c`
- `0x18003a228`
- `0x18003aa30`
- `0x18003bf74`
- `0x180071010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800311da`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800311f7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800311da`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800311f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180031390`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180031390`
- `api-ms-win-core-localization-l1-2-3!GetUserDefaultGeoName` at `0x1800311c1`
- `api-ms-win-core-localization-l1-2-3!GetUserDefaultGeoName` at `0x1800311c1`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180031196`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180031196`

## string_xrefs

- `0x180031111`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedclient.cpp`
- `0x180031294`: `TFLUpdateTimeoutMins`
- `0x180031482`: `https://go.microsoft.com/fwlink/?linkid=2261411`
- `0x1800313bf`: `https://go.microsoft.com/fwlink/?linkid=2261410`
- `0x1800313d1`: `https://go.microsoft.com/fwlink/?linkid=2261412`

## pseudocode

```c
__int64 __fastcall DockedClient::DoTFLUpdate(DockedClient *this, struct tagAppUpdateResult *a2, __int64 a3)
{
  struct tagAppUpdateResult *v3; // rsi
  int v4; // r15d
  int v5; // edi
  __int64 result; // rax
  __int64 v7; // rdx
  Utils *v8; // rcx
  _DWORD *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  const wchar_t *v12; // rax
  const char *v13; // r9
  volatile signed __int32 *v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rbx
  void (__fastcall ***v17)(_QWORD, __int64); // rcx
  int v18; // r15d
  void (__fastcall ***v19)(_QWORD, __int64); // rcx
  __int64 v20; // rax
  int v21; // r13d
  __int64 *v22; // rcx
  __int64 v23; // rdx
  char v24; // r15
  char v25; // r12
  volatile signed __int32 *v26; // rbx
  volatile signed __int32 *v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rbx
  int v30; // ebx
  int v31; // eax
  int v32; // [rsp+20h] [rbp-1B8h]
  char v33; // [rsp+30h] [rbp-1A8h]
  char v34; // [rsp+31h] [rbp-1A7h]
  int v35; // [rsp+34h] [rbp-1A4h]
  unsigned int v36; // [rsp+38h] [rbp-1A0h]
  __int64 v37; // [rsp+40h] [rbp-198h]
  __int64 v38; // [rsp+50h] [rbp-188h] BYREF
  int v39; // [rsp+58h] [rbp-180h]
  __int16 v40; // [rsp+5Ch] [rbp-17Ch]
  int v41; // [rsp+60h] [rbp-178h]
  int v42; // [rsp+64h] [rbp-174h]
  _QWORD v43[2]; // [rsp+68h] [rbp-170h] BYREF
  __int16 v44; // [rsp+7Eh] [rbp-15Ah]
  _QWORD v45[2]; // [rsp+80h] [rbp-158h] BYREF
  _QWORD v46[2]; // [rsp+90h] [rbp-148h] BYREF
  __int128 *v47; // [rsp+A0h] [rbp-138h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-130h] BYREF
  char v49; // [rsp+B0h] [rbp-128h]
  __int128 v50; // [rsp+C0h] [rbp-118h] BYREF
  __int64 v51; // [rsp+D0h] [rbp-108h]
  __int64 v52; // [rsp+D8h] [rbp-100h]
  struct _SYSTEM_INFO SystemInfo; // [rsp+E0h] [rbp-F8h] BYREF
  _BYTE v54[96]; // [rsp+110h] [rbp-C8h] BYREF
  volatile signed __int32 *v55; // [rsp+170h] [rbp-68h]
  _BYTE v56[40]; // [rsp+178h] [rbp-60h] BYREF
  WCHAR geoName[4]; // [rsp+1A0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  v3 = a2;
  v4 = (int)this;
  v46[1] = a2;
  v5 = 0;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x238,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedclient.cpp",
      (const char *)0x80004003LL,
      v32);
    return 2147500035LL;
  }
  try
  {
    LODWORD(v45[0]) = -1;
    v41 = -1;
    v42 = 0;
    v36 = 0;
    v33 = 0;
    v35 = 3;
    LOBYTE(a3) = 3;
    LOBYTE(a2) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TFLHydrate>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_TFLHydrate>::GetImpl'::`2'::impl,
      a2,
      a3);
    v37 = 0;
    v38 = 0;
    LODWORD(v47) = 0;
    RtlGetDeviceFamilyInfoEnum(0, &v47, 0);
    if ( (_DWORD)v47 != 3
      || (*(_QWORD *)geoName = 0, GetUserDefaultGeoName(geoName, 4))
      && (!(unsigned int)_o__wcsicmp(geoName, L"CN") || !(unsigned int)_o__wcsicmp(geoName, L"CHN"))
      || !Utils::IsAutoInstallAllowedForSku(v8) )
    {
      v21 = 0;
      v28 = 0;
      v37 = 0;
      v35 = 1;
      v24 = 0;
      v25 = 0;
      v38 = 0;
      v39 = 1;
      v40 = 0;
LABEL_57:
      if ( v25 || (v34 = 0, !v24) )
        v34 = 1;
      v42 = v21;
      v29 = v28;
      *(_QWORD *)geoName = v28;
      if ( v28 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
        v28 = v37;
      }
      if ( v28 )
      {
        v36 = *(_DWORD *)winrt::impl::consume_Windows_Management_Deployment_IDeploymentResult<winrt::Windows::Management::Deployment::IDeploymentResult>::ExtendedErrorCode(
                           geoName,
                           &v47);
        v29 = *(_QWORD *)geoName;
      }
      if ( v29 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(geoName);
      if ( v37 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v38);
      v30 = v45[0];
      if ( v34 )
      {
        v31 = 1;
      }
      else
      {
        v7 = v36;
        v31 = 0;
      }
      *(_DWORD *)v3 = v31;
      LOBYTE(v7) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_TFLHydrate>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_TFLHydrate>::GetImpl'::`2'::impl,
        v7,
        0);
      *((_DWORD *)v3 + 1) = 1;
      *((_DWORD *)v3 + 2) = v30;
      *((_DWORD *)v3 + 3) = v25 != 0;
      *((_DWORD *)v3 + 4) = v24 != 0;
      *((_DWORD *)v3 + 5) = v35;
      *((_DWORD *)v3 + 6) = v21;
      *((_DWORD *)v3 + 7) = v36;
      LOBYTE(v5) = v33 != 0;
      *((_DWORD *)v3 + 8) = v5;
      return 0;
    }
    v9 = operator new(0x18u);
    v9[2] = 1;
    v9[3] = 1;
    *(_QWORD *)v9 = &std::_Ref_count_obj2<Windows::Network>::`vftable';
    *((_QWORD *)v9 + 2) = &Windows::Registry::`vftable';
    v43[0] = v9 + 4;
    v43[1] = v9;
    v50 = 0;
    Windows::Settings::Settings(v54, v43, 0);
    LODWORD(v47) = 15;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v50, L"TFLUpdateTimeoutMins", 20);
    v46[0] = 60LL * (int)Windows::Settings::GetSettingOrDefault(v54, &v50, &v47);
    std::wstring::_Tidy_deallocate(&v50);
    winrt::Windows::Management::Deployment::PackageManager::PackageManager((winrt::Windows::Management::Deployment::PackageManager *)geoName);
    v10 = *(_QWORD *)geoName;
    v43[0] = *(_QWORD *)geoName;
    if ( *(_QWORD *)geoName )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)geoName + 8LL))(*(_QWORD *)geoName);
    *(_QWORD *)&v50 = L"MSTeams_8wekyb3d8bbwe";
    *((_QWORD *)&v50 + 1) = 21;
    DockedClient::GetProvisionedPackageVersion(v10, &v47, v43, &v50);
    if ( (_WORD)v47 != 1 || *(_DWORD *)((char *)&v47 + 2) )
    {
      v21 = 0;
      DWORD1(v50) = 0;
      v37 = 0;
      v24 = 0;
      v25 = 1;
      HIWORD(v51) = 0;
      v38 = 0;
      v39 = 3;
      v40 = 256;
LABEL_50:
      if ( *(_QWORD *)geoName )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(geoName);
      std::wstring::_Tidy_deallocate(v56);
      v27 = v55;
      if ( v55 )
      {
        if ( _InterlockedExchangeAdd(v55 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
          if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
        }
      }
      v28 = v37;
      goto LABEL_57;
    }
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    GetSystemInfo(&SystemInfo);
    if ( SystemInfo.wProcessorArchitecture == 9 )
    {
      v35 = 6;
    }
    else
    {
      v35 = 6;
      if ( SystemInfo.wProcessorArchitecture != 6 )
      {
        if ( SystemInfo.wProcessorArchitecture )
        {
          if ( SystemInfo.wProcessorArchitecture != 12 )
          {
            *(_DWORD *)v3 = 1;
            LOBYTE(v11) = 1;
            wil::details::FeatureImpl<__WilFeatureTraits_Feature_TFLHydrate>::ReportUsage(
              `wil::Feature<__WilFeatureTraits_Feature_TFLHydrate>::GetImpl'::`2'::impl,
              v11,
              0);
            *((_DWORD *)v3 + 1) = 1;
            *((_DWORD *)v3 + 2) = -1;
            *(_QWORD *)((char *)v3 + 12) = 0;
            *((_DWORD *)v3 + 5) = 4;
            *(_QWORD *)((char *)v3 + 28) = 0;
            if ( *(_QWORD *)geoName )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(geoName);
            std::wstring::_Tidy_deallocate(v56);
            v14 = v55;
            if ( v55 )
            {
              if ( _InterlockedExchangeAdd(v55 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
                if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
              }
            }
            return 0;
          }
          v12 = L"https://go.microsoft.com/fwlink/?linkid=2261412";
        }
        else
        {
          v12 = L"https://go.microsoft.com/fwlink/?linkid=2261410";
        }
        goto LABEL_27;
      }
    }
    v12 = L"https://go.microsoft.com/fwlink/?linkid=2261411";
LABEL_27:
    v33 = 1;
    v47 = (__int128 *)v12;
    v48 = 47;
    v43[0] = *(_QWORD *)geoName;
    if ( *(_QWORD *)geoName )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)geoName + 8LL))(*(_QWORD *)geoName);
    v45[0] = L"MSTeams_8wekyb3d8bbwe";
    v45[1] = 21;
    DockedClient::InstallAppForAllUsers(v4, (unsigned int)&v50, (unsigned int)v43, (unsigned int)&v47, (__int64)v45);
    v47 = &v50;
    v45[0] = operator new(0x120u);
    v15 = std::_Task_async_state_void_::_Task_async_state_void__std::_Fake_no_copy_callable_adapter__lambda_e657120094277e2db8af056ea83b5203_____(
            v45[0],
            &v47);
    v16 = v15;
    v47 = (__int128 *)v15;
    LOBYTE(v48) = 0;
    v49 = 0;
    if ( !v15 )
      std::_Throw_future_error2(4);
    v47 = (__int128 *)v15;
    LOBYTE(v48) = 1;
    _InterlockedAdd((volatile signed __int32 *)(v15 + 8), 1u);
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v15 + 8)) )
    {
      v17 = *(void (__fastcall ****)(_QWORD, __int64))(v15 + 200);
      if ( v17 )
        (**v17)(v17, v15);
      else
        (**(void (__fastcall ***)(__int64, __int64))v15)(v15, 1);
    }
    if ( *(_BYTE *)(v16 + 184) )
      std::_Throw_future_error2(4);
    v18 = std::_Associated_state<int>::_Wait_for<__int64,std::ratio<1,1>>(v16, v46);
    LODWORD(v45[0]) = v18;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v16 + 8), 0xFFFFFFFF) == 1 )
    {
      v19 = *(void (__fastcall ****)(_QWORD, __int64))(v16 + 200);
      if ( v19 )
        (**v19)(v19, v16);
      else
        (**(void (__fastcall ***)(__int64, __int64))v16)(v16, 1);
    }
    v41 = v18;
    if ( v18 )
    {
      v21 = 0;
      HIDWORD(v43[0]) = 0;
      v37 = 0;
      v24 = 1;
      v25 = 0;
      v44 = 0;
      v38 = 0;
      v39 = 6;
      v40 = 1;
    }
    else
    {
      v20 = Concurrency::task<DockedClient::AppInstallResult>::get(&v50, &v47);
      v21 = *(_DWORD *)v20;
      v22 = (__int64 *)(v20 + 8);
      if ( &v38 != (__int64 *)(v20 + 8) )
      {
        v37 = *v22;
        v23 = *v22;
        *v22 = 0;
        v38 = v23;
      }
      v35 = *(_DWORD *)(v20 + 16);
      v39 = v35;
      v24 = *(_BYTE *)(v20 + 20);
      LOBYTE(v40) = v24;
      v25 = *(_BYTE *)(v20 + 21);
      HIBYTE(v40) = v25;
      if ( v48 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v48);
    }
    v26 = (volatile signed __int32 *)*((_QWORD *)&v50 + 1);
    if ( *((_QWORD *)&v50 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v50 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
        if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
      }
    }
    goto LABEL_50;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2D7,
                           (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\d"
                                         "ll\\dockedclient.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x1800310c0  mov     [rsp+arg_10], rbx
0x1800310c5  mov     [rsp+arg_18], rsi
0x1800310ca  push    rdi
0x1800310cb  push    r12
0x1800310cd  push    r13
0x1800310cf  push    r14
0x1800310d1  push    r15
0x1800310d3  sub     rsp, 1B0h
0x1800310da  mov     rax, cs:__security_cookie
0x1800310e1  xor     rax, rsp
0x1800310e4  mov     [rsp+1D8h+var_30], rax
0x1800310ec  mov     rsi, rdx
0x1800310ef  mov     r15, rcx
0x1800310f2  mov     [rsp+1D8h+var_140], rdx
0x1800310fa  xor     edi, edi
0x1800310fc  test    rdx, rdx
0x1800310ff  jnz     short loc_180031129
0x180031101  mov     rcx, [rsp+1D8h]; this
0x180031109  mov     ebx, 80004003h
0x18003110e  mov     r9d, ebx; char *
0x180031111  lea     r8, aOnecoreEnduser_23; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180031118  mov     edx, 238h; void *
0x18003111d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031122  mov     eax, ebx
0x180031124  jmp     loc_180031939
0x180031129  or      r12d, 0FFFFFFFFh
0x18003112d  mov     eax, r12d
0x180031130  mov     dword ptr [rsp+1D8h+var_158], eax
0x180031137  mov     [rsp+1D8h+var_178], eax
0x18003113b  mov     [rsp+1D8h+var_174], edi
0x18003113f  mov     eax, edi
0x180031141  mov     [rsp+1D8h+var_1A0], eax
0x180031145  mov     [rsp+1D8h+var_19C], eax
0x180031149  mov     al, dil
0x18003114c  mov     [rsp+1D8h+var_1A8], al
0x180031150  mov     [rsp+1D8h+var_1A6], al
0x180031154  lea     ebx, [r12+4]
0x180031159  mov     [rsp+1D8h+var_1A4], ebx
0x18003115d  mov     r8b, bl
0x180031160  lea     r14d, [r12+2]
0x180031165  mov     dl, r14b
0x180031168  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TFLHydrate@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TFLHydrate@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TFLHydrate> `wil::Feature<__WilFeatureTraits_Feature_TFLHydrate>::GetImpl(void)'::`2'::impl
0x18003116f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_TFLHydrate@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TFLHydrate>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180031174  nop
0x180031175  mov     rdx, rdi
0x180031178  mov     [rsp+1D8h+var_198], rdx
0x18003117d  mov     [rsp+1D8h+var_188], rdx
0x180031182  mov     dword ptr [rsp+1D8h+var_138], edi
0x180031189  xor     r8d, r8d
0x18003118c  lea     rdx, [rsp+1D8h+var_138]
0x180031194  xor     ecx, ecx
0x180031196  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18003119c  cmp     dword ptr [rsp+1D8h+var_138], ebx
0x1800311a3  jnz     loc_18003185F
0x1800311a9  mov     qword ptr [rsp+1D8h+geoName], rdi
0x1800311b1  lea     r13d, [r12+5]
0x1800311b6  mov     edx, r13d; geoNameCount
0x1800311b9  lea     rcx, [rsp+1D8h+geoName]; geoName
0x1800311c1  call    cs:__imp_GetUserDefaultGeoName
0x1800311c7  test    eax, eax
0x1800311c9  jz      short loc_180031205
0x1800311cb  lea     rdx, aCn; "CN"
0x1800311d2  lea     rcx, [rsp+1D8h+geoName]
0x1800311da  call    cs:__imp__o__wcsicmp
0x1800311e0  test    eax, eax
0x1800311e2  jz      loc_18003185F
0x1800311e8  lea     rdx, aChn; "CHN"
0x1800311ef  lea     rcx, [rsp+1D8h+geoName]
0x1800311f7  call    cs:__imp__o__wcsicmp
0x1800311fd  test    eax, eax
0x1800311ff  jz      loc_18003185F
0x180031205  call    ?IsAutoInstallAllowedForSku@Utils@@YA_NXZ; Utils::IsAutoInstallAllowedForSku(void)
0x18003120a  test    al, al
0x18003120c  jz      loc_18003185F
0x180031212  mov     ecx, 18h; Size
0x180031217  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003121c  mov     [rax+8], r14d
0x180031220  mov     [rax+0Ch], r14d
0x180031224  lea     rcx, ??_7?$_Ref_count_obj2@VNetwork@Windows@@@std@@6B@; const std::_Ref_count_obj2<Windows::Network>::`vftable'
0x18003122b  mov     [rax], rcx
0x18003122e  lea     rcx, [rax+10h]
0x180031232  lea     rdx, ??_7Registry@Windows@@6B@; const Windows::Registry::`vftable'
0x180031239  mov     [rcx], rdx
0x18003123c  mov     [rsp+1D8h+var_170], rcx
0x180031241  mov     [rsp+1D8h+var_168], rax
0x180031246  xorps   xmm0, xmm0
0x180031249  movdqu  [rsp+1D8h+var_118], xmm0
0x180031252  xor     r8d, r8d
0x180031255  lea     rdx, [rsp+1D8h+var_170]
0x18003125a  lea     rcx, [rsp+1D8h+var_C8]
0x180031262  call    ??0Settings@Windows@@QEAA@V?$shared_ptr@VRegistry@SystemInterface@@@std@@_N@Z; Windows::Settings::Settings(std::shared_ptr<SystemInterface::Registry>,bool)
0x180031267  nop
0x180031268  mov     dword ptr [rsp+1D8h+var_138], 0Fh
0x180031273  xorps   xmm0, xmm0
0x180031276  movups  [rsp+1D8h+var_118], xmm0
0x18003127e  mov     [rsp+1D8h+var_108], rdi
0x180031286  mov     [rsp+1D8h+var_100], rdi
0x18003128e  mov     r8d, 14h
0x180031294  lea     rdx, aTflupdatetimeo; "TFLUpdateTimeoutMins"
0x18003129b  lea     rcx, [rsp+1D8h+var_118]
0x1800312a3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800312a8  nop
0x1800312a9  lea     r8, [rsp+1D8h+var_138]
0x1800312b1  lea     rdx, [rsp+1D8h+var_118]
0x1800312b9  lea     rcx, [rsp+1D8h+var_C8]
0x1800312c1  call    ?GetSettingOrDefault@Settings@Windows@@UEAAIAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBI@Z; Windows::Settings::GetSettingOrDefault(std::wstring const &,uint const &)
0x1800312c6  cdqe
0x1800312c8  imul    rcx, rax, 3Ch ; '<'
0x1800312cc  mov     [rsp+1D8h+var_148], rcx
0x1800312d4  lea     rcx, [rsp+1D8h+var_118]
0x1800312dc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800312e1  lea     rcx, [rsp+1D8h+geoName]; this
0x1800312e9  call    ??0PackageManager@Deployment@Management@Windows@winrt@@QEAA@XZ; winrt::Windows::Management::Deployment::PackageManager::PackageManager(void)
0x1800312ee  nop
0x1800312ef  mov     rcx, qword ptr [rsp+1D8h+geoName]
0x1800312f7  mov     [rsp+1D8h+var_170], rcx
0x1800312fc  test    rcx, rcx
0x1800312ff  jz      short loc_18003130D
0x180031301  mov     rax, [rcx]
0x180031304  mov     rax, [rax+8]
0x180031308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003130d  lea     rax, aMsteams8wekyb3; "MSTeams_8wekyb3d8bbwe"
0x180031314  mov     qword ptr [rsp+1D8h+var_118], rax
0x18003131c  mov     qword ptr [rsp+1D8h+var_118+8], 15h
0x180031328  lea     r9, [rsp+1D8h+var_118]
0x180031330  lea     r8, [rsp+1D8h+var_170]
0x180031335  lea     rdx, [rsp+1D8h+var_138]
0x18003133d  call    ?GetProvisionedPackageVersion@DockedClient@@AEAA?AUPackageVersion@ApplicationModel@Windows@winrt@@UPackageManager@Deployment@Management@45@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; DockedClient::GetProvisionedPackageVersion(winrt::Windows::Management::Deployment::PackageManager,std::basic_string_view<ushort>)
0x180031342  cmp     word ptr [rsp+1D8h+var_138], r14w
0x18003134b  jnz     loc_180031719
0x180031351  cmp     word ptr [rsp+1D8h+var_138+2], di
0x180031359  jnz     loc_180031719
0x18003135f  cmp     word ptr [rsp+1D8h+var_138+4], di
0x180031367  jnz     loc_180031719
0x18003136d  xorps   xmm0, xmm0
0x180031370  movups  xmmword ptr [rsp+1D8h+SystemInfo], xmm0
0x180031378  movups  xmmword ptr [rsp+1D8h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180031380  movups  xmmword ptr [rsp+1D8h+SystemInfo.dwNumberOfProcessors], xmm0
0x180031388  lea     rcx, [rsp+1D8h+SystemInfo]; lpSystemInfo
0x180031390  call    cs:__imp_GetSystemInfo
0x180031396  movzx   eax, word ptr [rsp+1D8h+SystemInfo]
0x18003139e  cmp     ax, 9
0x1800313a2  jz      loc_18003147A
0x1800313a8  mov     ecx, 6
0x1800313ad  mov     [rsp+1D8h+var_1A4], ecx
0x1800313b1  cmp     ax, cx
0x1800313b4  jz      loc_180031482
0x1800313ba  test    ax, ax
0x1800313bd  jnz     short loc_1800313CB
0x1800313bf  lea     rax, aHttpsGoMicroso_2; "https://go.microsoft.com/fwlink/?linkid"...
0x1800313c6  jmp     loc_180031489
0x1800313cb  cmp     ax, 0Ch
0x1800313cf  jnz     short loc_1800313DD
0x1800313d1  lea     rax, aHttpsGoMicroso_4; "https://go.microsoft.com/fwlink/?linkid"...
0x1800313d8  jmp     loc_180031489
0x1800313dd  mov     [rsi], r14d
0x1800313e0  xor     r8d, r8d
0x1800313e3  mov     dl, r14b
0x1800313e6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_TFLHydrate@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_TFLHydrate@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TFLHydrate> `wil::Feature<__WilFeatureTraits_Feature_TFLHydrate>::GetImpl(void)'::`2'::impl
0x1800313ed  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_TFLHydrate@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TFLHydrate>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800313f2  mov     [rsi+4], r14d
0x1800313f6  mov     dword ptr [rsi+8], 0FFFFFFFFh
0x1800313fd  mov     [rsi+0Ch], rdi
0x180031401  mov     [rsi+14h], r13d
0x180031405  mov     [rsi+1Ch], rdi
0x180031409  cmp     qword ptr [rsp+1D8h+geoName], rdi
0x180031411  jz      short loc_180031421
0x180031413  lea     rcx, [rsp+1D8h+geoName]
0x18003141b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180031420  nop
0x180031421  lea     rcx, [rsp+1D8h+var_60]
0x180031429  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003142e  mov     rbx, [rsp+1D8h+var_68]
0x180031436  test    rbx, rbx
0x180031439  jz      short loc_180031473
0x18003143b  mov     eax, r12d
0x18003143e  lock xadd [rbx+8], eax
0x180031443  add     eax, r12d
0x180031446  jnz     short loc_180031473
0x180031448  mov     rax, [rbx]
0x18003144b  mov     rcx, rbx
0x18003144e  mov     rax, [rax]
0x180031451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031456  mov     eax, r12d
0x180031459  lock xadd [rbx+0Ch], eax
0x18003145e  add     eax, r12d
0x180031461  jnz     short loc_180031473
0x180031463  mov     rax, [rbx]
0x180031466  mov     rcx, rbx
0x180031469  mov     rax, [rax+8]
0x18003146d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031472  nop
0x180031473  xor     eax, eax
0x180031475  jmp     loc_180031939
0x18003147a  mov     [rsp+1D8h+var_1A4], 6
0x180031482  lea     rax, aHttpsGoMicroso_1; "https://go.microsoft.com/fwlink/?linkid"...
0x180031489  mov     cl, r14b
0x18003148c  mov     [rsp+1D8h+var_1A8], cl
0x180031490  mov     [rsp+1D8h+var_1A6], cl
0x180031494  mov     qword ptr [rsp+1D8h+var_138], rax
0x18003149c  mov     qword ptr [rsp+1D8h+var_138+8], 2Fh ; '/'
0x1800314a8  mov     rcx, qword ptr [rsp+1D8h+geoName]
0x1800314b0  mov     [rsp+1D8h+var_170], rcx
0x1800314b5  test    rcx, rcx
0x1800314b8  jz      short loc_1800314C6
0x1800314ba  mov     rax, [rcx]
0x1800314bd  mov     rax, [rax+8]
0x1800314c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800314c6  lea     rax, aMsteams8wekyb3; "MSTeams_8wekyb3d8bbwe"
0x1800314cd  mov     [rsp+1D8h+var_158], rax
0x1800314d5  mov     [rsp+1D8h+var_150], 15h
0x1800314e1  movups  xmm0, [rsp+1D8h+var_138]
0x1800314e9  movdqu  [rsp+1D8h+var_138], xmm0
0x1800314f2  lea     rax, [rsp+1D8h+var_158]
0x1800314fa  mov     qword ptr [rsp+1D8h+var_1B8], rax
0x1800314ff  lea     r9, [rsp+1D8h+var_138]
0x180031507  lea     r8, [rsp+1D8h+var_170]
0x18003150c  lea     rdx, [rsp+1D8h+var_118]
0x180031514  mov     rcx, r15
0x180031517  call    ?InstallAppForAllUsers@DockedClient@@AEAA?AV?$task@UAppInstallResult@DockedClient@@@Concurrency@@UPackageManager@Deployment@Management@Windows@winrt@@V?$basic_string_view@GU?$char_traits@G@std@@@std@@1@Z; DockedClient::InstallAppForAllUsers(winrt::Windows::Management::Deployment::PackageManager,std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x18003151c  nop
0x18003151d  lea     rax, [rsp+1D8h+var_118]
0x180031525  mov     qword ptr [rsp+1D8h+var_138], rax
0x18003152d  mov     ecx, 120h; Size
0x180031532  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180031537  mov     [rsp+1D8h+var_158], rax
0x18003153f  lea     rdx, [rsp+1D8h+var_138]
0x180031547  mov     rcx, rax
0x18003154a  call    std___Task_async_state_void____Task_async_state_void__std___Fake_no_copy_callable_adapter__lambda_e657120094277e2db8af056ea83b5203_____
0x18003154f  mov     rbx, rax
0x180031552  mov     qword ptr [rsp+1D8h+var_138], rax
0x18003155a  mov     byte ptr [rsp+1D8h+var_138+8], dil
0x180031562  mov     [rsp+1D8h+var_128], dil
0x18003156a  test    rax, rax
0x18003156d  jz      loc_180031966
0x180031573  mov     qword ptr [rsp+1D8h+var_138], rbx
0x18003157b  mov     byte ptr [rsp+1D8h+var_138+8], r14b
0x180031583  lock add [rax+8], r14d
0x180031588  mov     eax, r12d
0x18003158b  lock xadd [rbx+8], eax
0x180031590  add     eax, r12d
0x180031593  jnz     short loc_1800315C3
0x180031595  mov     rcx, [rbx+0C8h]
0x18003159c  test    rcx, rcx
0x18003159f  jz      short loc_1800315B1
0x1800315a1  mov     rax, [rcx]
0x1800315a4  mov     rdx, rbx
0x1800315a7  mov     rax, [rax]
0x1800315aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800315af  jmp     short loc_1800315C3
0x1800315b1  mov     rax, [rbx]
0x1800315b4  mov     edx, r14d
0x1800315b7  mov     rcx, rbx
0x1800315ba  mov     rax, [rax]
0x1800315bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800315c2  nop
0x1800315c3  cmp     [rbx+0B8h], dil
0x1800315ca  jnz     loc_18003196F
0x1800315d0  lea     rdx, [rsp+1D8h+var_148]
0x1800315d8  mov     rcx, rbx
0x1800315db  call    ??$_Wait_for@_JU?$ratio@$00$00@std@@@?$_Associated_state@H@std@@QEAA?AW4future_status@1@AEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@1@@Z; std::_Associated_state<int>::_Wait_for<__int64,std::ratio<1,1>>(std::chrono::duration<__int64,std::ratio<1,1>> const &)
0x1800315e0  mov     r15d, eax
0x1800315e3  mov     dword ptr [rsp+1D8h+var_158], eax
0x1800315ea  mov     ecx, r12d
0x1800315ed  lock xadd [rbx+8], ecx
0x1800315f2  add     ecx, r12d
0x1800315f5  jnz     short loc_180031624
0x1800315f7  mov     rcx, [rbx+0C8h]
0x1800315fe  test    rcx, rcx
0x180031601  jz      short loc_180031613
0x180031603  mov     rax, [rcx]
0x180031606  mov     rdx, rbx
0x180031609  mov     rax, [rax]
0x18003160c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031611  jmp     short loc_180031624
0x180031613  mov     rax, [rbx]
0x180031616  mov     edx, r14d
0x180031619  mov     rcx, rbx
0x18003161c  mov     rax, [rax]
0x18003161f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031624  mov     [rsp+1D8h+var_178], r15d
0x180031629  test    r15d, r15d
0x18003162c  jnz     short loc_18003169F
0x18003162e  lea     rdx, [rsp+1D8h+var_138]
0x180031636  lea     rcx, [rsp+1D8h+var_118]
0x18003163e  call    ?get@?$task@UAppInstallResult@DockedClient@@@Concurrency@@QEBA?AUAppInstallResult@DockedClient@@XZ; Concurrency::task<DockedClient::AppInstallResult>::get(void)
0x180031643  mov     r13d, [rax]
0x180031646  mov     [rsp+1D8h+var_190], r13d
0x18003164b  lea     rcx, [rax+8]
0x18003164f  lea     rdx, [rsp+1D8h+var_188]
0x180031654  cmp     rdx, rcx
0x180031657  jz      short loc_180031669
0x180031659  mov     rdx, [rcx]
0x18003165c  mov     [rsp+1D8h+var_198], rdx
0x180031661  mov     [rcx], rdi
0x180031664  mov     [rsp+1D8h+var_188], rdx
0x180031669  mov     ecx, [rax+10h]
0x18003166c  mov     [rsp+1D8h+var_1A4], ecx
0x180031670  mov     [rsp+1D8h+var_180], ecx
0x180031674  mov     r15b, [rax+14h]
  ... truncated ...
```
