# ModernDeployment::Autopilot::Core::FwtRetryQueue::DequeueAll(std::vector<std::pair<ulong,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>,std::allocator<std::pair<ulong,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>> &)

- ea: `0x1800e3800`
- end: `0x1800e3d84`
- name: `?DequeueAll@FwtRetryQueue@Core@Autopilot@ModernDeployment@@SAJAEAV?$vector@U?$pair@KV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@V?$allocator@U?$pair@KV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@2@@std@@@Z`
- size: `1412`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800dc524`

## callees

- `0x18000b820`
- `0x18000c414`
- `0x180067a54`
- `0x18006b690`
- `0x18007755c`
- `0x1800775c4`
- `0x18008019c`
- `0x1800839bc`
- `0x1800873a4`
- `0x1800887b8`
- `0x1800889a0`
- `0x18008cfa4`
- `0x1800935e0`
- `0x1800a13a4`
- `0x1800c4fa4`
- `0x1800e2a44`
- `0x1800e2a7c`
- `0x1800e2c04`
- `0x1800e33e8`
- `0x1800e36e0`
- `0x1800e3800`
- `0x1800e423c`
- `0x1800e462c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800e39ef`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800e39ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3929`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e3929`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e3b8d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e3b8d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800e390c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800e390c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800e3abe`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800e3abe`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800e3bad`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800e3bad`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800e3c12`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800e3c12`

## string_xrefs

- `0x1800e389c`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtretryqueue.cpp`
- `0x1800e3946`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtretryqueue.cpp`
- `0x1800e3d41`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtretryqueue.cpp`
- `0x1800e38c2`: `\*.json`

## pseudocode

```c
// Hidden C++ exception states: #wind=20 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::FwtRetryQueue::DequeueAll(_QWORD *a1)
{
  __m128i si128; // xmm6
  int QueueFolderPath; // eax
  unsigned int v4; // ebx
  const WCHAR *v6; // rax
  HANDLE FirstFileW; // rbx
  DWORD LastError; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned __int64 v13; // rcx
  _DWORD *v14; // rsi
  _DWORD *v15; // r15
  __m128i v16; // xmm6
  __int64 v17; // rax
  const WCHAR *v18; // rax
  char *FileW; // rbx
  DWORD FileSize; // r14d
  void *v21; // rax
  __int64 v22; // rdx
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-3A8h]
  char v24; // [rsp+40h] [rbp-388h]
  wchar_t *EndPtr; // [rsp+48h] [rbp-380h] BYREF
  __int128 v26; // [rsp+50h] [rbp-378h] BYREF
  __int64 v27; // [rsp+60h] [rbp-368h]
  HANDLE v28; // [rsp+68h] [rbp-360h] BYREF
  char *v29; // [rsp+70h] [rbp-358h] BYREF
  __int128 v30; // [rsp+78h] [rbp-350h] BYREF
  __m128i v31; // [rsp+88h] [rbp-340h]
  _DWORD v32[2]; // [rsp+98h] [rbp-330h] BYREF
  _QWORD v33[2]; // [rsp+A0h] [rbp-328h] BYREF
  __m128i v34; // [rsp+B0h] [rbp-318h]
  _OWORD v35[2]; // [rsp+C0h] [rbp-308h] BYREF
  _BYTE v36[32]; // [rsp+E0h] [rbp-2E8h] BYREF
  _BYTE v37[32]; // [rsp+100h] [rbp-2C8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+120h] [rbp-2A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl'::`2'::impl) )
  {
    if ( *a1 != a1[1] )
    {
      std::_Destroy_range<std::allocator<Microsoft::Windows::Autopilot::Diagnostics::GenericMappingUtilities<enum ModernDeployment::Autopilot::Core::DiagnosticAnalysisState,std::string>::GenericMapping>>(*a1);
      a1[1] = *a1;
    }
    v35[0] = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v35[1] = si128;
    LOWORD(v35[0]) = 0;
    QueueFolderPath = ModernDeployment::Autopilot::Core::FwtRetryQueue::GetQueueFolderPath(v35);
    v4 = QueueFolderPath;
    if ( QueueFolderPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtretryqueue.cpp",
        (const char *)(unsigned int)QueueFolderPath,
        dwCreationDisposition);
      std::wstring::_Tidy_deallocate(v35);
      return v4;
    }
    std::operator+<unsigned short>(v36, v35, L"\\*.json");
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
    FirstFileW = FindFirstFileW(v6, &FindFileData);
    v28 = FirstFileW;
    if ( (((unsigned __int64)FirstFileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = GetLastError();
      if ( LastError - 2 <= 1 )
      {
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v28);
        std::wstring::_Tidy_deallocate(v36);
        std::wstring::_Tidy_deallocate(v35);
        return 0;
      }
      if ( LastError )
      {
        v9 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x76,
               (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtretryqueue.cpp",
               (const char *)LastError,
               dwCreationDisposition);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v28);
        std::wstring::_Tidy_deallocate(v36);
        std::wstring::_Tidy_deallocate(v35);
        return v9;
      }
    }
    v26 = 0;
    v27 = 0;
    do
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        EndPtr = 0;
        v10 = wcstoul(FindFileData.cFileName, &EndPtr, 10);
        if ( EndPtr )
        {
          if ( *EndPtr == 46 )
          {
            v32[0] = v10;
            v32[1] = 0;
            std::wstring::wstring(v33, FindFileData.cFileName);
            v11 = *((_QWORD *)&v26 + 1);
            if ( *((_QWORD *)&v26 + 1) == v27 )
            {
              std::vector__ModernDeployment::Autopilot::Core::FwtRetryQueue::DequeueAll_::_3_::PendingFile_std::allocator__ModernDeployment::Autopilot::Core::FwtRetryQueue::DequeueAll_::_3_::PendingFile___::_Emplace_reallocate__ModernDeployment::Autopilot::Core::FwtRetryQueue::DequeueAll_::_3_::PendingFile_(
                &v26,
                *((_QWORD *)&v26 + 1),
                v32);
            }
            else
            {
              **((_DWORD **)&v26 + 1) = v32[0];
              *(_QWORD *)(v11 + 8) = v33[0];
              *(_QWORD *)(v11 + 16) = v33[1];
              *(__m128i *)(v11 + 24) = v34;
              v34 = si128;
              LOWORD(v33[0]) = 0;
              *((_QWORD *)&v26 + 1) += 40LL;
            }
            std::wstring::_Tidy_deallocate(v33);
          }
        }
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    LOBYTE(v12) = v24;
    std::_Sort_unchecked__ModernDeployment::Autopilot::Core::FwtRetryQueue::DequeueAll_::_3_::PendingFile____ModernDeployment::Autopilot::Core::FwtRetryQueue::DequeueAll_::_3_::_lambda_1___(
      v26,
      *((_QWORD *)&v26 + 1),
      0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v26 + 1) - v26) >> 3),
      v12);
    __SET_PAIR__((unsigned __int64)v15, v13, v26);
    v14 = (_DWORD *)v26;
    v16 = _mm_load_si128((const __m128i *)&_xmm);
    while ( v14 != v15 )
    {
      v17 = std::operator+<unsigned short>(v32, v35, L"\\");
      std::operator+<unsigned short>(v37, v17, v14 + 2);
      std::wstring::_Tidy_deallocate(v32);
      v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v37);
      FileW = (char *)CreateFileW(v18, 0x80000000, 1u, 0, 3u, 0x80u, 0);
      v29 = FileW;
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        FileSize = GetFileSize(FileW, 0);
        if ( FileSize - 1 <= 0xFFFFFFFD )
        {
          v30 = 0;
          v31 = v16;
          LOBYTE(v30) = 0;
          std::string::resize(&v30, FileSize, 0);
          LODWORD(EndPtr) = 0;
          v21 = (void *)std::_String_val<std::_Simple_types<char>>::_Myptr(&v30);
          if ( ReadFile(FileW, v21, FileSize, (LPDWORD)&EndPtr, 0) && (_DWORD)EndPtr )
          {
            std::string::resize(&v30, (unsigned int)EndPtr, 0);
            v22 = a1[1];
            if ( v22 == a1[2] )
            {
              std::vector<std::pair<unsigned long,std::string>>::_Emplace_reallocate<unsigned long const &,std::string>(
                a1,
                v22,
                v14,
                &v30);
            }
            else
            {
              *(_DWORD *)v22 = *v14;
              *(_OWORD *)(v22 + 8) = 0;
              *(_QWORD *)(v22 + 24) = 0;
              *(_QWORD *)(v22 + 32) = 0;
              *(_OWORD *)(v22 + 8) = v30;
              *(__m128i *)(v22 + 24) = v31;
              v31 = v16;
              LOBYTE(v30) = 0;
              a1[1] += 40LL;
            }
          }
          std::string::_Tidy_deallocate(&v30);
        }
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v29);
      std::wstring::_Tidy_deallocate(v37);
      v14 += 10;
      v13 = v26;
    }
    if ( v13 )
    {
      std::_Destroy_range_std::allocator__ModernDeployment::Autopilot::Core::FwtRetryQueue::DequeueAll_::_3_::PendingFile___();
      std::_Deallocate<16>(v26, 8 * ((v27 - (__int64)v26) >> 3));
      v26 = 0;
      v27 = 0;
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v28);
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(v35);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtretryqueue.cpp",
      (const char *)0x80004001LL,
      dwCreationDisposition);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1800e3800  mov     rax, rsp
0x1800e3803  push    rbx
0x1800e3804  push    rsi
0x1800e3805  push    rdi
0x1800e3806  push    r13
0x1800e3808  push    r14
0x1800e380a  push    r15
0x1800e380c  sub     rsp, 398h
0x1800e3813  movaps  xmmword ptr [rax-48h], xmm6
0x1800e3817  mov     rax, cs:__security_cookie
0x1800e381e  xor     rax, rsp
0x1800e3821  mov     [rsp+3C8h+var_58], rax
0x1800e3829  mov     rdi, rcx
0x1800e382c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800e3833  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800e3838  test    al, al
0x1800e383a  jz      loc_1800E3D31
0x1800e3840  mov     rdx, [rdi+8]
0x1800e3844  cmp     [rdi], rdx
0x1800e3847  jz      short loc_1800E3858
0x1800e3849  mov     rcx, [rdi]
0x1800e384c  call    ??$_Destroy_range@V?$allocator@UGenericMapping@?$GenericMappingUtilities@W4DiagnosticAnalysisState@Core@Autopilot@ModernDeployment@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Diagnostics@Autopilot@Windows@Microsoft@@@std@@@std@@YAXPEAUGenericMapping@?$GenericMappingUtilities@W4DiagnosticAnalysisState@Core@Autopilot@ModernDeployment@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Diagnostics@Autopilot@Windows@Microsoft@@QEAU123456@AEAV?$allocator@UGenericMapping@?$GenericMappingUtilities@W4DiagnosticAnalysisState@Core@Autopilot@ModernDeployment@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Diagnostics@Autopilot@Windows@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::Windows::Autopilot::Diagnostics::GenericMappingUtilities<ModernDeployment::Autopilot::Core::DiagnosticAnalysisState,std::string>::GenericMapping>>(Microsoft::Windows::Autopilot::Diagnostics::GenericMappingUtilities<ModernDeployment::Autopilot::Core::DiagnosticAnalysisState,std::string>::GenericMapping *,Microsoft::Windows::Autopilot::Diagnostics::GenericMappingUtilities<ModernDeployment::Autopilot::Core::DiagnosticAnalysisState,std::string>::GenericMapping * const,std::allocator<Microsoft::Windows::Autopilot::Diagnostics::GenericMappingUtilities<ModernDeployment::Autopilot::Core::DiagnosticAnalysisState,std::string>::GenericMapping> &)
0x1800e3851  mov     rax, [rdi]
0x1800e3854  mov     [rdi+8], rax
0x1800e3858  xorps   xmm0, xmm0
0x1800e385b  movups  [rsp+3C8h+var_308], xmm0
0x1800e3863  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800e386b  movdqu  [rsp+3C8h+var_2F8], xmm6
0x1800e3874  xor     eax, eax
0x1800e3876  mov     word ptr [rsp+3C8h+var_308], ax
0x1800e387e  lea     rcx, [rsp+3C8h+var_308]
0x1800e3886  call    ?GetQueueFolderPath@FwtRetryQueue@Core@Autopilot@ModernDeployment@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ModernDeployment::Autopilot::Core::FwtRetryQueue::GetQueueFolderPath(std::wstring &)
0x1800e388b  mov     ebx, eax
0x1800e388d  test    eax, eax
0x1800e388f  jns     short loc_1800E38C2
0x1800e3891  mov     rcx, [rsp+3C8h]; this
0x1800e3899  mov     r9d, eax; char *
0x1800e389c  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e38a3  mov     edx, 69h ; 'i'; void *
0x1800e38a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e38ad  nop
0x1800e38ae  lea     rcx, [rsp+3C8h+var_308]
0x1800e38b6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e38bb  mov     eax, ebx
0x1800e38bd  jmp     loc_1800E3D5A
0x1800e38c2  lea     r8, aJson_0; "\\*.json"
0x1800e38c9  lea     rdx, [rsp+3C8h+var_308]
0x1800e38d1  lea     rcx, [rsp+3C8h+var_2E8]
0x1800e38d9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800e38de  nop
0x1800e38df  xor     edx, edx; Val
0x1800e38e1  mov     r8d, 250h; Size
0x1800e38e7  lea     rcx, [rsp+3C8h+FindFileData]; void *
0x1800e38ef  call    memset_0
0x1800e38f4  lea     rcx, [rsp+3C8h+var_2E8]
0x1800e38fc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e3901  mov     rcx, rax; lpFileName
0x1800e3904  lea     rdx, [rsp+3C8h+FindFileData]; lpFindFileData
0x1800e390c  call    cs:__imp_FindFirstFileW
0x1800e3912  mov     rbx, rax
0x1800e3915  mov     [rsp+3C8h+var_360], rax
0x1800e391a  inc     rax
0x1800e391d  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800e3923  jnz     loc_1800E39B3
0x1800e3929  call    cs:__imp_GetLastError
0x1800e392f  lea     ecx, [rax-2]
0x1800e3932  cmp     ecx, 1
0x1800e3935  jbe     short loc_1800E3986
0x1800e3937  test    eax, eax
0x1800e3939  jz      short loc_1800E39B3
0x1800e393b  mov     rcx, [rsp+3C8h]; this
0x1800e3943  mov     r9d, eax; char *
0x1800e3946  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e394d  mov     edx, 76h ; 'v'; void *
0x1800e3952  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800e3957  mov     ebx, eax
0x1800e3959  lea     rcx, [rsp+3C8h+var_360]
0x1800e395e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800e3963  nop
0x1800e3964  lea     rcx, [rsp+3C8h+var_2E8]
0x1800e396c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e3971  nop
0x1800e3972  lea     rcx, [rsp+3C8h+var_308]
0x1800e397a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e397f  mov     eax, ebx
0x1800e3981  jmp     loc_1800E3D5A
0x1800e3986  lea     rcx, [rsp+3C8h+var_360]
0x1800e398b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800e3990  nop
0x1800e3991  lea     rcx, [rsp+3C8h+var_2E8]
0x1800e3999  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e399e  nop
0x1800e399f  lea     rcx, [rsp+3C8h+var_308]
0x1800e39a7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e39ac  xor     eax, eax
0x1800e39ae  jmp     loc_1800E3D5A
0x1800e39b3  xorps   xmm0, xmm0
0x1800e39b6  movdqu  [rsp+3C8h+var_378], xmm0
0x1800e39bc  mov     [rsp+3C8h+var_368], 0
0x1800e39c5  test    byte ptr [rsp+3C8h+FindFileData.dwFileAttributes], 10h
0x1800e39cd  jnz     loc_1800E3AB3
0x1800e39d3  mov     [rsp+3C8h+EndPtr], 0
0x1800e39dc  mov     r8d, 0Ah; Radix
0x1800e39e2  lea     rdx, [rsp+3C8h+EndPtr]; EndPtr
0x1800e39e7  lea     rcx, [rsp+3C8h+FindFileData.cFileName]; String
0x1800e39ef  call    cs:__imp_wcstoul
0x1800e39f5  mov     rcx, [rsp+3C8h+EndPtr]
0x1800e39fa  test    rcx, rcx
0x1800e39fd  jz      loc_1800E3AB3
0x1800e3a03  cmp     word ptr [rcx], 2Eh ; '.'
0x1800e3a07  jnz     loc_1800E3AB3
0x1800e3a0d  mov     [rsp+3C8h+var_330], eax
0x1800e3a14  xor     eax, eax
0x1800e3a16  mov     [rsp+3C8h+var_32C], eax
0x1800e3a1d  lea     rdx, [rsp+3C8h+FindFileData.cFileName]
0x1800e3a25  lea     rcx, [rsp+3C8h+var_328]
0x1800e3a2d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e3a32  nop
0x1800e3a33  mov     rdx, qword ptr [rsp+3C8h+var_378+8]
0x1800e3a38  cmp     rdx, [rsp+3C8h+var_368]
0x1800e3a3d  jz      short loc_1800E3A93
0x1800e3a3f  mov     eax, [rsp+3C8h+var_330]
0x1800e3a46  mov     [rdx], eax
0x1800e3a48  mov     rax, [rsp+3C8h+var_328]
0x1800e3a50  mov     [rdx+8], rax
0x1800e3a54  mov     rax, [rsp+3C8h+var_320]
0x1800e3a5c  mov     [rdx+10h], rax
0x1800e3a60  mov     rax, qword ptr [rsp+3C8h+var_318]
0x1800e3a68  mov     [rdx+18h], rax
0x1800e3a6c  mov     rax, qword ptr [rsp+3C8h+var_318+8]
0x1800e3a74  mov     [rdx+20h], rax
0x1800e3a78  movdqu  [rsp+3C8h+var_318], xmm6
0x1800e3a81  xor     eax, eax
0x1800e3a83  mov     word ptr [rsp+3C8h+var_328], ax
0x1800e3a8b  add     qword ptr [rsp+3C8h+var_378+8], 28h ; '('
0x1800e3a91  jmp     short loc_1800E3AA6
0x1800e3a93  lea     r8, [rsp+3C8h+var_330]
0x1800e3a9b  lea     rcx, [rsp+3C8h+var_378]
0x1800e3aa0  call    std__vector__ModernDeployment__Autopilot__Core__FwtRetryQueue__DequeueAll____3___PendingFile_std__allocator__ModernDeployment__Autopilot__Core__FwtRetryQueue__DequeueAll____3___PendingFile______Emplace_reallocate__ModernDeployment__Autopilot__Core__FwtRetryQueue__DequeueAll____3___PendingFile_
0x1800e3aa5  nop
0x1800e3aa6  lea     rcx, [rsp+3C8h+var_328]
0x1800e3aae  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e3ab3  lea     rdx, [rsp+3C8h+FindFileData]; lpFindFileData
0x1800e3abb  mov     rcx, rbx; hFindFile
0x1800e3abe  call    cs:__imp_FindNextFileW
0x1800e3ac4  test    eax, eax
0x1800e3ac6  jnz     loc_1800E39C5
0x1800e3acc  mov     rdx, qword ptr [rsp+3C8h+var_378+8]
0x1800e3ad1  mov     rcx, qword ptr [rsp+3C8h+var_378]
0x1800e3ad6  mov     r8, rdx
0x1800e3ad9  sub     r8, rcx
0x1800e3adc  sar     r8, 3
0x1800e3ae0  mov     r13, 0CCCCCCCCCCCCCCCDh
0x1800e3aea  imul    r8, r13
0x1800e3aee  mov     r9b, [rsp+3C8h+var_388]
0x1800e3af3  call    std___Sort_unchecked__ModernDeployment__Autopilot__Core__FwtRetryQueue__DequeueAll____3___PendingFile____ModernDeployment__Autopilot__Core__FwtRetryQueue__DequeueAll____3____lambda_1___
0x1800e3af8  mov     rcx, qword ptr [rsp+3C8h+var_378]
0x1800e3afd  mov     rsi, rcx
0x1800e3b00  mov     rdx, qword ptr [rsp+3C8h+var_378+8]
0x1800e3b05  mov     r15, rdx
0x1800e3b08  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x1800e3b10  cmp     rsi, r15
0x1800e3b13  jz      loc_1800E3CC9
0x1800e3b19  lea     r8, SubBlock; "\\"
0x1800e3b20  lea     rdx, [rsp+3C8h+var_308]
0x1800e3b28  lea     rcx, [rsp+3C8h+var_330]
0x1800e3b30  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800e3b35  nop
0x1800e3b36  lea     r8, [rsi+8]
0x1800e3b3a  mov     rdx, rax
0x1800e3b3d  lea     rcx, [rsp+3C8h+var_2C8]
0x1800e3b45  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800e3b4a  nop
0x1800e3b4b  lea     rcx, [rsp+3C8h+var_330]
0x1800e3b53  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e3b58  lea     rcx, [rsp+3C8h+var_2C8]
0x1800e3b60  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e3b65  mov     rcx, rax; lpFileName
0x1800e3b68  mov     [rsp+3C8h+hTemplateFile], 0; hTemplateFile
0x1800e3b71  mov     [rsp+3C8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800e3b79  mov     [rsp+3C8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800e3b81  xor     r9d, r9d; lpSecurityAttributes
0x1800e3b84  mov     edx, 80000000h; dwDesiredAccess
0x1800e3b89  lea     r8d, [r9+1]; dwShareMode
0x1800e3b8d  call    cs:__imp_CreateFileW
0x1800e3b93  mov     rbx, rax
0x1800e3b96  mov     [rsp+3C8h+var_358], rax
0x1800e3b9b  dec     rax
0x1800e3b9e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800e3ba2  ja      loc_1800E3C9E
0x1800e3ba8  xor     edx, edx; lpFileSizeHigh
0x1800e3baa  mov     rcx, rbx; hFile
0x1800e3bad  call    cs:__imp_GetFileSize
0x1800e3bb3  mov     r14d, eax
0x1800e3bb6  lea     ecx, [r14-1]
0x1800e3bba  cmp     ecx, 0FFFFFFFDh
0x1800e3bbd  ja      loc_1800E3C9E
0x1800e3bc3  xorps   xmm0, xmm0
0x1800e3bc6  movups  [rsp+3C8h+var_350], xmm0
0x1800e3bcb  movdqu  [rsp+3C8h+var_340], xmm6
0x1800e3bd4  mov     byte ptr [rsp+3C8h+var_350], 0
0x1800e3bd9  mov     edx, r14d
0x1800e3bdc  xor     r8d, r8d
0x1800e3bdf  lea     rcx, [rsp+3C8h+var_350]
0x1800e3be4  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_KD@Z; std::string::resize(unsigned __int64,char)
0x1800e3be9  mov     dword ptr [rsp+3C8h+EndPtr], 0
0x1800e3bf1  lea     rcx, [rsp+3C8h+var_350]
0x1800e3bf6  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800e3bfb  mov     rdx, rax; lpBuffer
0x1800e3bfe  mov     qword ptr [rsp+3C8h+dwCreationDisposition], 0; lpOverlapped
0x1800e3c07  lea     r9, [rsp+3C8h+EndPtr]; lpNumberOfBytesRead
0x1800e3c0c  mov     r8d, r14d; nNumberOfBytesToRead
0x1800e3c0f  mov     rcx, rbx; hFile
0x1800e3c12  call    cs:__imp_ReadFile
0x1800e3c18  test    eax, eax
0x1800e3c1a  jz      short loc_1800E3C93
0x1800e3c1c  mov     eax, dword ptr [rsp+3C8h+EndPtr]
0x1800e3c20  test    eax, eax
0x1800e3c22  jz      short loc_1800E3C93
0x1800e3c24  mov     edx, eax
0x1800e3c26  xor     r8d, r8d
0x1800e3c29  lea     rcx, [rsp+3C8h+var_350]
0x1800e3c2e  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_KD@Z; std::string::resize(unsigned __int64,char)
0x1800e3c33  mov     rdx, [rdi+8]
0x1800e3c37  cmp     rdx, [rdi+10h]
0x1800e3c3b  jz      short loc_1800E3C82
0x1800e3c3d  mov     eax, [rsi]
0x1800e3c3f  mov     [rdx], eax
0x1800e3c41  xorps   xmm0, xmm0
0x1800e3c44  movups  xmmword ptr [rdx+8], xmm0
0x1800e3c48  mov     qword ptr [rdx+18h], 0
0x1800e3c50  mov     qword ptr [rdx+20h], 0
0x1800e3c58  movups  xmm0, [rsp+3C8h+var_350]
0x1800e3c5d  movups  xmmword ptr [rdx+8], xmm0
0x1800e3c61  movups  xmm1, [rsp+3C8h+var_340]
0x1800e3c69  movups  xmmword ptr [rdx+18h], xmm1
0x1800e3c6d  movdqu  [rsp+3C8h+var_340], xmm6
0x1800e3c76  mov     byte ptr [rsp+3C8h+var_350], 0
0x1800e3c7b  add     qword ptr [rdi+8], 28h ; '('
0x1800e3c80  jmp     short loc_1800E3C93
0x1800e3c82  lea     r9, [rsp+3C8h+var_350]
0x1800e3c87  mov     r8, rsi
0x1800e3c8a  mov     rcx, rdi
0x1800e3c8d  call    ??$_Emplace_reallocate@AEBKV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@U?$pair@KV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@V?$allocator@U?$pair@KV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@2@@std@@AEAAPEAU?$pair@KV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@QEAU21@AEBK$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::vector<std::pair<ulong,std::string>>::_Emplace_reallocate<ulong const &,std::string>(std::pair<ulong,std::string> * const,ulong const &,std::string &&)
0x1800e3c92  nop
0x1800e3c93  lea     rcx, [rsp+3C8h+var_350]
0x1800e3c98  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e3c9d  nop
0x1800e3c9e  lea     rcx, [rsp+3C8h+var_358]
0x1800e3ca3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e3ca8  nop
0x1800e3ca9  lea     rcx, [rsp+3C8h+var_2C8]
0x1800e3cb1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e3cb6  add     rsi, 28h ; '('
0x1800e3cba  mov     rdx, qword ptr [rsp+3C8h+var_378+8]
0x1800e3cbf  mov     rcx, qword ptr [rsp+3C8h+var_378]
0x1800e3cc4  jmp     loc_1800E3B10
0x1800e3cc9  test    rcx, rcx
0x1800e3ccc  jz      short loc_1800E3D07
0x1800e3cce  call    std___Destroy_range_std__allocator__ModernDeployment__Autopilot__Core__FwtRetryQueue__DequeueAll____3___PendingFile___
0x1800e3cd3  mov     rcx, qword ptr [rsp+3C8h+var_378]
0x1800e3cd8  mov     rax, [rsp+3C8h+var_368]
0x1800e3cdd  sub     rax, rcx
0x1800e3ce0  sar     rax, 3
0x1800e3ce4  imul    rax, r13
0x1800e3ce8  lea     rdx, [rax+rax*4]
0x1800e3cec  shl     rdx, 3
0x1800e3cf0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800e3cf5  xorps   xmm0, xmm0
0x1800e3cf8  movdqu  [rsp+3C8h+var_378], xmm0
0x1800e3cfe  mov     [rsp+3C8h+var_368], 0
0x1800e3d07  lea     rcx, [rsp+3C8h+var_360]
0x1800e3d0c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800e3d11  nop
0x1800e3d12  lea     rcx, [rsp+3C8h+var_2E8]
0x1800e3d1a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e3d1f  nop
0x1800e3d20  lea     rcx, [rsp+3C8h+var_308]
0x1800e3d28  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e3d2d  xor     eax, eax
0x1800e3d2f  jmp     short loc_1800E3D5A
0x1800e3d31  mov     rcx, [rsp+3C8h]; this
0x1800e3d39  mov     ebx, 80004001h
0x1800e3d3e  mov     r9d, ebx; char *
0x1800e3d41  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e3d48  mov     edx, 64h ; 'd'; void *
0x1800e3d4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e3d52  mov     eax, ebx
0x1800e3d54  jmp     short loc_1800E3D5A
0x1800e3d56  mov     eax, dword ptr [rsp+3C8h+EndPtr]
0x1800e3d5a  mov     rcx, [rsp+3C8h+var_58]
0x1800e3d62  xor     rcx, rsp; StackCookie
0x1800e3d65  call    __security_check_cookie
0x1800e3d6a  movaps  xmm6, [rsp+3C8h+var_48]
0x1800e3d72  add     rsp, 398h
0x1800e3d79  pop     r15
0x1800e3d7b  pop     r14
0x1800e3d7d  pop     r13
0x1800e3d7f  pop     rdi
0x1800e3d80  pop     rsi
  ... truncated ...
```
