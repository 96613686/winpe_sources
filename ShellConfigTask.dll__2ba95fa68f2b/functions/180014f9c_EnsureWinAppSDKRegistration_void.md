# EnsureWinAppSDKRegistration(void)

- ea: `0x180014f9c`
- end: `0x180015127`
- name: `?EnsureWinAppSDKRegistration@@YAJXZ`
- size: `395`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001fd50`

## callees

- `0x18000ab14`
- `0x18000cdf0`
- `0x1800106d4`
- `0x180011384`
- `0x180014f9c`
- `0x18001d918`
- `0x18002166c`
- `0x180023588`
- `0x180024b4c`
- `0x180033010`

## string_xrefs

- `0x1800150c8`: `pcshell\shell\aix\shellconfigtask\lib\recallconfigtaskhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 EnsureWinAppSDKRegistration(void)
{
  unsigned int v0; // edx
  int v1; // eax
  const char *v2; // r9
  int v3; // eax
  volatile signed __int32 *v4; // rbx
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-28h] BYREF
  __int128 v9; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  volatile signed __int32 *v11; // [rsp+50h] [rbp+8h] BYREF
  volatile signed __int32 **v12; // [rsp+58h] [rbp+10h] BYREF
  __int64 *v13; // [rsp+60h] [rbp+18h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion>::GetImpl'::`2'::impl) )
  {
    try
    {
      LODWORD(v11) = 4;
      v12 = &v11;
      v13 = &qword_1800420B8;
      _InterlockedIncrement64(&qword_1800420B8);
      if ( winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2> )
      {
        v8 = 0;
        v9 = 0;
        v1 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>
                                                        + 48LL))(
               winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>,
               (unsigned int)v11);
        if ( v1 < 0 )
          winrt::throw_hresult((unsigned int)v1, &v8);
        _InterlockedDecrement64(&qword_1800420B8);
      }
      else
      {
        _InterlockedDecrement64(&qword_1800420B8);
        winrt::impl::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>::call<_lambda_e52b8f1ff41f26bfae44258b1f1df26e_ &>(
          0,
          (unsigned int **)&v12);
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0xDA,
                             (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\recallconfigtaskhandler.cpp",
                             v2);
    }
  }
  else
  {
    v4 = (volatile signed __int32 *)winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x31, v0);
    memcpy_s((void *const)(v4 + 7), 0x62u, L"Microsoft.WindowsAppRuntime.CBS.1.6_8wekyb3d8bbwe", 0x62u);
    v11 = v4;
    v5 = RegisterPackageDependency(&v11);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\recallconfigtaskhandler.cpp",
        (const char *)(unsigned int)v5,
        v8);
      return v6;
    }
  }
  v11 = (volatile signed __int32 *)&qword_180042098;
  _InterlockedIncrement64(&qword_180042098);
  if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics> )
  {
    v8 = 0;
    v9 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics>
                                            + 56LL))(winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics>);
    if ( v3 < 0 )
      winrt::throw_hresult((unsigned int)v3, &v8);
    _InterlockedDecrement64(&qword_180042098);
  }
  else
  {
    _InterlockedDecrement64(&qword_180042098);
    v11 = (volatile signed __int32 *)_lambda_9c7b9a15a6c0fa0ef4a186a43afb0906_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics>::call<void (*)(winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics const &)>(
      0,
      &v11);
  }
  return 0;
}

```

## disassembly

```asm
0x180014f9c  push    rbx
0x180014f9e  sub     rsp, 40h
0x180014fa2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion> `wil::Feature<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion>::GetImpl(void)'::`2'::impl
0x180014fa9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion>::__private_IsEnabled(void)
0x180014fae  test    al, al
0x180014fb0  jz      loc_180015082
0x180014fb6  mov     dword ptr [rsp+48h+arg_0], 4
0x180014fbe  lea     rax, [rsp+48h+arg_0]
0x180014fc3  mov     [rsp+48h+arg_8], rax
0x180014fc8  lea     rax, qword_1800420B8
0x180014fcf  mov     [rsp+48h+arg_10], rax
0x180014fd4  lock inc cs:qword_1800420B8
0x180014fdc  mov     rcx, cs:??$factory_cache_entry_v@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics2@2345@@impl@winrt@@3U?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics2@2345@@12@A; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension,winrt::WindowsUdk::ApplicationModel::AppExtensions::IAppExtensionStatics2>
0x180014fe3  test    rcx, rcx
0x180014fe6  jz      short loc_18001501B
0x180014fe8  mov     [rsp+48h+var_28], 0
0x180014ff0  xorps   xmm0, xmm0
0x180014ff3  movdqu  [rsp+48h+var_20], xmm0
0x180014ff9  mov     rax, [rcx]
0x180014ffc  mov     edx, dword ptr [rsp+48h+arg_0]
0x180015000  mov     rax, [rax+30h]
0x180015004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015009  test    eax, eax
0x18001500b  js      loc_18001510D
0x180015011  lock dec cs:qword_1800420B8
0x180015019  jmp     short loc_18001502E
0x18001501b  lock dec cs:qword_1800420B8
0x180015023  lea     rdx, [rsp+48h+arg_8]
0x180015028  call    ??$call@AEAV_lambda_e52b8f1ff41f26bfae44258b1f1df26e_@@@?$factory_cache_entry@UAppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@UIAppExtensionStatics2@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_e52b8f1ff41f26bfae44258b1f1df26e_@@@Z
0x18001502d  nop
0x18001502e  lea     rax, qword_180042098
0x180015035  mov     [rsp+48h+arg_0], rax
0x18001503a  lock inc cs:qword_180042098
0x180015042  mov     rcx, cs:??$factory_cache_entry_v@UWorkloadManager@Workloads@Windows@Microsoft@winrt@@UIWorkloadManagerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UWorkloadManager@Workloads@Windows@Microsoft@winrt@@UIWorkloadManagerStatics@2345@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics>
0x180015049  test    rcx, rcx
0x18001504c  jz      loc_1800150E7
0x180015052  mov     [rsp+48h+var_28], 0
0x18001505a  xorps   xmm0, xmm0
0x18001505d  movdqu  [rsp+48h+var_20], xmm0
0x180015063  mov     rax, [rcx]
0x180015066  mov     rax, [rax+38h]
0x18001506a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001506f  test    eax, eax
0x180015071  js      loc_18001511A
0x180015077  jmp     short loc_1800150DD
0x180015079  mov     eax, dword ptr [rsp+48h+arg_0]
0x18001507d  jmp     loc_180015107
0x180015082  mov     ecx, 31h ; '1'; this
0x180015087  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18001508c  mov     rbx, rax
0x18001508f  lea     rcx, [rax+1Ch]; Destination
0x180015093  mov     edx, 62h ; 'b'; DestinationSize
0x180015098  mov     r9d, edx; SourceSize
0x18001509b  lea     r8, aMicrosoftWindo_3; "Microsoft.WindowsAppRuntime.CBS.1.6_8we"...
0x1800150a2  call    memcpy_s
0x1800150a7  mov     [rsp+48h+arg_0], rbx
0x1800150ac  lea     rcx, [rsp+48h+arg_0]
0x1800150b1  call    ?RegisterPackageDependency@@YAJUhstring@winrt@@@Z; RegisterPackageDependency(winrt::hstring)
0x1800150b6  mov     ebx, eax
0x1800150b8  test    eax, eax
0x1800150ba  jns     loc_18001502E
0x1800150c0  mov     rcx, [rsp+48h]; this
0x1800150c5  mov     r9d, eax; char *
0x1800150c8  lea     r8, aPcshellShellAi; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x1800150cf  mov     edx, 0DEh; void *
0x1800150d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800150d9  mov     eax, ebx
0x1800150db  jmp     short loc_180015107
0x1800150dd  lock dec cs:qword_180042098
0x1800150e5  jmp     short loc_180015105
0x1800150e7  lock dec cs:qword_180042098
0x1800150ef  lea     rax, ?_lambda_invoker_cdecl_@_lambda_9c7b9a15a6c0fa0ef4a186a43afb0906_@@CA@AEBUIWorkloadManagerStatics@Workloads@Windows@Microsoft@winrt@@@Z; _lambda_9c7b9a15a6c0fa0ef4a186a43afb0906_::_lambda_invoker_cdecl_(winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics const &)
0x1800150f6  mov     [rsp+48h+arg_0], rax
0x1800150fb  lea     rdx, [rsp+48h+arg_0]
0x180015100  call    ??$call@P6AXAEBUIWorkloadManagerStatics@Workloads@Windows@Microsoft@winrt@@@Z@?$factory_cache_entry@UWorkloadManager@Workloads@Windows@Microsoft@winrt@@UIWorkloadManagerStatics@2345@@impl@winrt@@QEAA?A_P$$QEAP6AXAEBUIWorkloadManagerStatics@Workloads@Windows@Microsoft@2@@Z@Z
0x180015105  xor     eax, eax
0x180015107  add     rsp, 40h
0x18001510b  pop     rbx
0x18001510c  retn
0x18001510d  lea     rdx, [rsp+48h+var_28]
0x180015112  mov     ecx, eax
0x180015114  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001511a  lea     rdx, [rsp+48h+var_28]
0x18001511f  mov     ecx, eax
0x180015121  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
