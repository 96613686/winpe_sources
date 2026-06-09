# ModernDeployment::Autopilot::Core::FwtRetryQueue::DequeueAll(std::vector<std::pair<ulong,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>,std::allocator<std::pair<ulong,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>>> &)

- ea: `0x1800e6140`
- end: `0x1800e66ee`
- name: `?DequeueAll@FwtRetryQueue@Core@Autopilot@ModernDeployment@@SAJAEAV?$vector@U?$pair@KV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@V?$allocator@U?$pair@KV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@2@@std@@@Z`
- size: `1454`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800ded04`

## callees

- `0x18000b8f0`
- `0x18000c504`
- `0x180067e54`
- `0x18006bb78`
- `0x180077de0`
- `0x180077e54`
- `0x180080bac`
- `0x180084574`
- `0x180088144`
- `0x180089660`
- `0x180089850`
- `0x18008e088`
- `0x180094888`
- `0x1800a29ac`
- `0x1800c705c`
- `0x1800e5368`
- `0x1800e53a4`
- `0x1800e552c`
- `0x1800e5d14`
- `0x1800e6010`
- `0x1800e6140`
- `0x1800e6bc8`
- `0x1800e6fd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800e633b`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800e633b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e626f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e626f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e64e5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e64e5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800e624c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800e624c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800e6410`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800e6410`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800e650b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800e650b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800e6576`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800e6576`

## string_xrefs

- `0x1800e6202`: `\*.json`
- `0x1800e61dc`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtretryqueue.cpp`
- `0x1800e6292`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtretryqueue.cpp`
- `0x1800e66ab`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtretryqueue.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
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
0x1800e6140  mov     rax, rsp
0x1800e6143  push    rbx
0x1800e6144  push    rsi
0x1800e6145  push    rdi
0x1800e6146  push    r13
0x1800e6148  push    r14
0x1800e614a  push    r15
0x1800e614c  sub     rsp, 398h
0x1800e6153  movaps  xmmword ptr [rax-48h], xmm6
0x1800e6157  mov     rax, cs:__security_cookie
0x1800e615e  xor     rax, rsp
0x1800e6161  mov     [rsp+3C8h+var_58], rax
0x1800e6169  mov     rdi, rcx
0x1800e616c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800e6173  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800e6178  test    al, al
0x1800e617a  jz      loc_1800E669B
0x1800e6180  mov     rdx, [rdi+8]
0x1800e6184  cmp     [rdi], rdx
0x1800e6187  jz      short loc_1800E6198
0x1800e6189  mov     rcx, [rdi]
0x1800e618c  call    ??$_Destroy_range@V?$allocator@UGenericMapping@?$GenericMappingUtilities@W4DiagnosticAnalysisState@Core@Autopilot@ModernDeployment@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Diagnostics@Autopilot@Windows@Microsoft@@@std@@@std@@YAXPEAUGenericMapping@?$GenericMappingUtilities@W4DiagnosticAnalysisState@Core@Autopilot@ModernDeployment@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Diagnostics@Autopilot@Windows@Microsoft@@QEAU123456@AEAV?$allocator@UGenericMapping@?$GenericMappingUtilities@W4DiagnosticAnalysisState@Core@Autopilot@ModernDeployment@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Diagnostics@Autopilot@Windows@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::Windows::Autopilot::Diagnostics::GenericMappingUtilities<ModernDeployment::Autopilot::Core::DiagnosticAnalysisState,std::string>::GenericMapping>>(Microsoft::Windows::Autopilot::Diagnostics::GenericMappingUtilities<ModernDeployment::Autopilot::Core::DiagnosticAnalysisState,std::string>::GenericMapping *,Microsoft::Windows::Autopilot::Diagnostics::GenericMappingUtilities<ModernDeployment::Autopilot::Core::DiagnosticAnalysisState,std::string>::GenericMapping * const,std::allocator<Microsoft::Windows::Autopilot::Diagnostics::GenericMappingUtilities<ModernDeployment::Autopilot::Core::DiagnosticAnalysisState,std::string>::GenericMapping> &)
0x1800e6191  mov     rax, [rdi]
0x1800e6194  mov     [rdi+8], rax
0x1800e6198  xorps   xmm0, xmm0
0x1800e619b  movups  [rsp+3C8h+var_308], xmm0
0x1800e61a3  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800e61ab  movdqu  [rsp+3C8h+var_2F8], xmm6
0x1800e61b4  xor     eax, eax
0x1800e61b6  mov     word ptr [rsp+3C8h+var_308], ax
0x1800e61be  lea     rcx, [rsp+3C8h+var_308]
0x1800e61c6  call    ?GetQueueFolderPath@FwtRetryQueue@Core@Autopilot@ModernDeployment@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ModernDeployment::Autopilot::Core::FwtRetryQueue::GetQueueFolderPath(std::wstring &)
0x1800e61cb  mov     ebx, eax
0x1800e61cd  test    eax, eax
0x1800e61cf  jns     short loc_1800E6202
0x1800e61d1  mov     rcx, [rsp+3C8h]; this
0x1800e61d9  mov     r9d, eax; char *
0x1800e61dc  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e61e3  mov     edx, 69h ; 'i'; void *
0x1800e61e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e61ed  nop
0x1800e61ee  lea     rcx, [rsp+3C8h+var_308]
0x1800e61f6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e61fb  mov     eax, ebx
0x1800e61fd  jmp     loc_1800E66C4
0x1800e6202  lea     r8, aJson_0; "\\*.json"
0x1800e6209  lea     rdx, [rsp+3C8h+var_308]
0x1800e6211  lea     rcx, [rsp+3C8h+var_2E8]
0x1800e6219  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800e621e  nop
0x1800e621f  xor     edx, edx; Val
0x1800e6221  mov     r8d, 250h; Size
0x1800e6227  lea     rcx, [rsp+3C8h+FindFileData]; void *
0x1800e622f  call    memset_0
0x1800e6234  lea     rcx, [rsp+3C8h+var_2E8]
0x1800e623c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e6241  mov     rcx, rax; lpFileName
0x1800e6244  lea     rdx, [rsp+3C8h+FindFileData]; lpFindFileData
0x1800e624c  call    cs:__imp_FindFirstFileW
0x1800e6253  nop     dword ptr [rax+rax+00h]
0x1800e6258  mov     rbx, rax
0x1800e625b  mov     [rsp+3C8h+var_360], rax
0x1800e6260  inc     rax
0x1800e6263  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800e6269  jnz     loc_1800E62FF
0x1800e626f  call    cs:__imp_GetLastError
0x1800e6276  nop     dword ptr [rax+rax+00h]
0x1800e627b  lea     ecx, [rax-2]
0x1800e627e  cmp     ecx, 1
0x1800e6281  jbe     short loc_1800E62D2
0x1800e6283  test    eax, eax
0x1800e6285  jz      short loc_1800E62FF
0x1800e6287  mov     rcx, [rsp+3C8h]; this
0x1800e628f  mov     r9d, eax; char *
0x1800e6292  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e6299  mov     edx, 76h ; 'v'; void *
0x1800e629e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800e62a3  mov     ebx, eax
0x1800e62a5  lea     rcx, [rsp+3C8h+var_360]
0x1800e62aa  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800e62af  nop
0x1800e62b0  lea     rcx, [rsp+3C8h+var_2E8]
0x1800e62b8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e62bd  nop
0x1800e62be  lea     rcx, [rsp+3C8h+var_308]
0x1800e62c6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e62cb  mov     eax, ebx
0x1800e62cd  jmp     loc_1800E66C4
0x1800e62d2  lea     rcx, [rsp+3C8h+var_360]
0x1800e62d7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800e62dc  nop
0x1800e62dd  lea     rcx, [rsp+3C8h+var_2E8]
0x1800e62e5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e62ea  nop
0x1800e62eb  lea     rcx, [rsp+3C8h+var_308]
0x1800e62f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e62f8  xor     eax, eax
0x1800e62fa  jmp     loc_1800E66C4
0x1800e62ff  xorps   xmm0, xmm0
0x1800e6302  movdqu  [rsp+3C8h+var_378], xmm0
0x1800e6308  mov     [rsp+3C8h+var_368], 0
0x1800e6311  test    byte ptr [rsp+3C8h+FindFileData.dwFileAttributes], 10h
0x1800e6319  jnz     loc_1800E6405
0x1800e631f  mov     [rsp+3C8h+EndPtr], 0
0x1800e6328  mov     r8d, 0Ah; Radix
0x1800e632e  lea     rdx, [rsp+3C8h+EndPtr]; EndPtr
0x1800e6333  lea     rcx, [rsp+3C8h+FindFileData.cFileName]; String
0x1800e633b  call    cs:__imp_wcstoul
0x1800e6342  nop     dword ptr [rax+rax+00h]
0x1800e6347  mov     rcx, [rsp+3C8h+EndPtr]
0x1800e634c  test    rcx, rcx
0x1800e634f  jz      loc_1800E6405
0x1800e6355  cmp     word ptr [rcx], 2Eh ; '.'
0x1800e6359  jnz     loc_1800E6405
0x1800e635f  mov     [rsp+3C8h+var_330], eax
0x1800e6366  xor     eax, eax
0x1800e6368  mov     [rsp+3C8h+var_32C], eax
0x1800e636f  lea     rdx, [rsp+3C8h+FindFileData.cFileName]
0x1800e6377  lea     rcx, [rsp+3C8h+var_328]
0x1800e637f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800e6384  nop
0x1800e6385  mov     rdx, qword ptr [rsp+3C8h+var_378+8]
0x1800e638a  cmp     rdx, [rsp+3C8h+var_368]
0x1800e638f  jz      short loc_1800E63E5
0x1800e6391  mov     eax, [rsp+3C8h+var_330]
0x1800e6398  mov     [rdx], eax
0x1800e639a  mov     rax, [rsp+3C8h+var_328]
0x1800e63a2  mov     [rdx+8], rax
0x1800e63a6  mov     rax, [rsp+3C8h+var_320]
0x1800e63ae  mov     [rdx+10h], rax
0x1800e63b2  mov     rax, qword ptr [rsp+3C8h+var_318]
0x1800e63ba  mov     [rdx+18h], rax
0x1800e63be  mov     rax, qword ptr [rsp+3C8h+var_318+8]
0x1800e63c6  mov     [rdx+20h], rax
0x1800e63ca  movdqu  [rsp+3C8h+var_318], xmm6
0x1800e63d3  xor     eax, eax
0x1800e63d5  mov     word ptr [rsp+3C8h+var_328], ax
0x1800e63dd  add     qword ptr [rsp+3C8h+var_378+8], 28h ; '('
0x1800e63e3  jmp     short loc_1800E63F8
0x1800e63e5  lea     r8, [rsp+3C8h+var_330]
0x1800e63ed  lea     rcx, [rsp+3C8h+var_378]
0x1800e63f2  call    std__vector__ModernDeployment__Autopilot__Core__FwtRetryQueue__DequeueAll____3___PendingFile_std__allocator__ModernDeployment__Autopilot__Core__FwtRetryQueue__DequeueAll____3___PendingFile______Emplace_reallocate__ModernDeployment__Autopilot__Core__FwtRetryQueue__DequeueAll____3___PendingFile_
0x1800e63f7  nop
0x1800e63f8  lea     rcx, [rsp+3C8h+var_328]
0x1800e6400  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e6405  lea     rdx, [rsp+3C8h+FindFileData]; lpFindFileData
0x1800e640d  mov     rcx, rbx; hFindFile
0x1800e6410  call    cs:__imp_FindNextFileW
0x1800e6417  nop     dword ptr [rax+rax+00h]
0x1800e641c  test    eax, eax
0x1800e641e  jnz     loc_1800E6311
0x1800e6424  mov     rdx, qword ptr [rsp+3C8h+var_378+8]
0x1800e6429  mov     rcx, qword ptr [rsp+3C8h+var_378]
0x1800e642e  mov     r8, rdx
0x1800e6431  sub     r8, rcx
0x1800e6434  sar     r8, 3
0x1800e6438  mov     r13, 0CCCCCCCCCCCCCCCDh
0x1800e6442  imul    r8, r13
0x1800e6446  mov     r9b, [rsp+3C8h+var_388]
0x1800e644b  call    std___Sort_unchecked__ModernDeployment__Autopilot__Core__FwtRetryQueue__DequeueAll____3___PendingFile____ModernDeployment__Autopilot__Core__FwtRetryQueue__DequeueAll____3____lambda_1___
0x1800e6450  mov     rcx, qword ptr [rsp+3C8h+var_378]
0x1800e6455  mov     rsi, rcx
0x1800e6458  mov     rdx, qword ptr [rsp+3C8h+var_378+8]
0x1800e645d  mov     r15, rdx
0x1800e6460  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x1800e6468  cmp     rsi, r15
0x1800e646b  jz      loc_1800E6633
0x1800e6471  lea     r8, SubBlock; "\\"
0x1800e6478  lea     rdx, [rsp+3C8h+var_308]
0x1800e6480  lea     rcx, [rsp+3C8h+var_330]
0x1800e6488  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800e648d  nop
0x1800e648e  lea     r8, [rsi+8]
0x1800e6492  mov     rdx, rax
0x1800e6495  lea     rcx, [rsp+3C8h+var_2C8]
0x1800e649d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800e64a2  nop
0x1800e64a3  lea     rcx, [rsp+3C8h+var_330]
0x1800e64ab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e64b0  lea     rcx, [rsp+3C8h+var_2C8]
0x1800e64b8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e64bd  mov     rcx, rax; lpFileName
0x1800e64c0  mov     [rsp+3C8h+hTemplateFile], 0; hTemplateFile
0x1800e64c9  mov     [rsp+3C8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800e64d1  mov     [rsp+3C8h+dwCreationDisposition], 3; dwCreationDisposition
0x1800e64d9  xor     r9d, r9d; lpSecurityAttributes
0x1800e64dc  mov     edx, 80000000h; dwDesiredAccess
0x1800e64e1  lea     r8d, [r9+1]; dwShareMode
0x1800e64e5  call    cs:__imp_CreateFileW
0x1800e64ec  nop     dword ptr [rax+rax+00h]
0x1800e64f1  mov     rbx, rax
0x1800e64f4  mov     [rsp+3C8h+var_358], rax
0x1800e64f9  dec     rax
0x1800e64fc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800e6500  ja      loc_1800E6608
0x1800e6506  xor     edx, edx; lpFileSizeHigh
0x1800e6508  mov     rcx, rbx; hFile
0x1800e650b  call    cs:__imp_GetFileSize
0x1800e6512  nop     dword ptr [rax+rax+00h]
0x1800e6517  mov     r14d, eax
0x1800e651a  lea     ecx, [r14-1]
0x1800e651e  cmp     ecx, 0FFFFFFFDh
0x1800e6521  ja      loc_1800E6608
0x1800e6527  xorps   xmm0, xmm0
0x1800e652a  movups  [rsp+3C8h+var_350], xmm0
0x1800e652f  movdqu  [rsp+3C8h+var_340], xmm6
0x1800e6538  mov     byte ptr [rsp+3C8h+var_350], 0
0x1800e653d  mov     edx, r14d
0x1800e6540  xor     r8d, r8d
0x1800e6543  lea     rcx, [rsp+3C8h+var_350]
0x1800e6548  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_KD@Z; std::string::resize(unsigned __int64,char)
0x1800e654d  mov     dword ptr [rsp+3C8h+EndPtr], 0
0x1800e6555  lea     rcx, [rsp+3C8h+var_350]
0x1800e655a  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800e655f  mov     rdx, rax; lpBuffer
0x1800e6562  mov     qword ptr [rsp+3C8h+dwCreationDisposition], 0; lpOverlapped
0x1800e656b  lea     r9, [rsp+3C8h+EndPtr]; lpNumberOfBytesRead
0x1800e6570  mov     r8d, r14d; nNumberOfBytesToRead
0x1800e6573  mov     rcx, rbx; hFile
0x1800e6576  call    cs:__imp_ReadFile
0x1800e657d  nop     dword ptr [rax+rax+00h]
0x1800e6582  test    eax, eax
0x1800e6584  jz      short loc_1800E65FD
0x1800e6586  mov     eax, dword ptr [rsp+3C8h+EndPtr]
0x1800e658a  test    eax, eax
0x1800e658c  jz      short loc_1800E65FD
0x1800e658e  mov     edx, eax
0x1800e6590  xor     r8d, r8d
0x1800e6593  lea     rcx, [rsp+3C8h+var_350]
0x1800e6598  call    ?resize@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_KD@Z; std::string::resize(unsigned __int64,char)
0x1800e659d  mov     rdx, [rdi+8]
0x1800e65a1  cmp     rdx, [rdi+10h]
0x1800e65a5  jz      short loc_1800E65EC
0x1800e65a7  mov     eax, [rsi]
0x1800e65a9  mov     [rdx], eax
0x1800e65ab  xorps   xmm0, xmm0
0x1800e65ae  movups  xmmword ptr [rdx+8], xmm0
0x1800e65b2  mov     qword ptr [rdx+18h], 0
0x1800e65ba  mov     qword ptr [rdx+20h], 0
0x1800e65c2  movups  xmm0, [rsp+3C8h+var_350]
0x1800e65c7  movups  xmmword ptr [rdx+8], xmm0
0x1800e65cb  movups  xmm1, [rsp+3C8h+var_340]
0x1800e65d3  movups  xmmword ptr [rdx+18h], xmm1
0x1800e65d7  movdqu  [rsp+3C8h+var_340], xmm6
0x1800e65e0  mov     byte ptr [rsp+3C8h+var_350], 0
0x1800e65e5  add     qword ptr [rdi+8], 28h ; '('
0x1800e65ea  jmp     short loc_1800E65FD
0x1800e65ec  lea     r9, [rsp+3C8h+var_350]
0x1800e65f1  mov     r8, rsi
0x1800e65f4  mov     rcx, rdi
0x1800e65f7  call    ??$_Emplace_reallocate@AEBKV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@U?$pair@KV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@V?$allocator@U?$pair@KV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@2@@std@@AEAAPEAU?$pair@KV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@QEAU21@AEBK$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::vector<std::pair<ulong,std::string>>::_Emplace_reallocate<ulong const &,std::string>(std::pair<ulong,std::string> * const,ulong const &,std::string &&)
0x1800e65fc  nop
0x1800e65fd  lea     rcx, [rsp+3C8h+var_350]
0x1800e6602  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e6607  nop
0x1800e6608  lea     rcx, [rsp+3C8h+var_358]
0x1800e660d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800e6612  nop
0x1800e6613  lea     rcx, [rsp+3C8h+var_2C8]
0x1800e661b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e6620  add     rsi, 28h ; '('
0x1800e6624  mov     rdx, qword ptr [rsp+3C8h+var_378+8]
0x1800e6629  mov     rcx, qword ptr [rsp+3C8h+var_378]
0x1800e662e  jmp     loc_1800E6468
0x1800e6633  test    rcx, rcx
0x1800e6636  jz      short loc_1800E6671
0x1800e6638  call    std___Destroy_range_std__allocator__ModernDeployment__Autopilot__Core__FwtRetryQueue__DequeueAll____3___PendingFile___
0x1800e663d  mov     rcx, qword ptr [rsp+3C8h+var_378]
0x1800e6642  mov     rax, [rsp+3C8h+var_368]
0x1800e6647  sub     rax, rcx
0x1800e664a  sar     rax, 3
0x1800e664e  imul    rax, r13
0x1800e6652  lea     rdx, [rax+rax*4]
0x1800e6656  shl     rdx, 3
0x1800e665a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800e665f  xorps   xmm0, xmm0
0x1800e6662  movdqu  [rsp+3C8h+var_378], xmm0
0x1800e6668  mov     [rsp+3C8h+var_368], 0
0x1800e6671  lea     rcx, [rsp+3C8h+var_360]
0x1800e6676  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800e667b  nop
0x1800e667c  lea     rcx, [rsp+3C8h+var_2E8]
0x1800e6684  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e6689  nop
0x1800e668a  lea     rcx, [rsp+3C8h+var_308]
0x1800e6692  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e6697  xor     eax, eax
0x1800e6699  jmp     short loc_1800E66C4
0x1800e669b  mov     rcx, [rsp+3C8h]; this
0x1800e66a3  mov     ebx, 80004001h
0x1800e66a8  mov     r9d, ebx; char *
0x1800e66ab  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e66b2  mov     edx, 64h ; 'd'; void *
0x1800e66b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e66bc  mov     eax, ebx
0x1800e66be  jmp     short loc_1800E66C4
0x1800e66c0  mov     eax, dword ptr [rsp+3C8h+EndPtr]
0x1800e66c4  mov     rcx, [rsp+3C8h+var_58]
0x1800e66cc  xor     rcx, rsp; StackCookie
0x1800e66cf  call    __security_check_cookie
  ... truncated ...
```
