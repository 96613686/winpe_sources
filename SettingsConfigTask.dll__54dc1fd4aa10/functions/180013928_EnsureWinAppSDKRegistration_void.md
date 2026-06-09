# EnsureWinAppSDKRegistration(void)

- ea: `0x180013928`
- end: `0x1800139a8`
- name: `?EnsureWinAppSDKRegistration@@YAJXZ`
- size: `128`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001c380`

## callees

- `0x18000972c`
- `0x18000f884`
- `0x180012094`
- `0x1800135d8`
- `0x180013928`
- `0x18001a388`
- `0x18001d09c`

## string_xrefs

- `0x180013993`: `pcshell\shell\settings\settingsconfigtask\lib\settingsconfigtaskhandler.cpp`

## pseudocode

```c
__int64 EnsureWinAppSDKRegistration(void)
{
  unsigned int v0; // r8d
  const char *v1; // r9
  int v3; // eax
  unsigned int v4; // ebx
  int v5[10]; // [rsp+0h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v7; // [rsp+30h] [rbp+8h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion>::GetImpl'::`2'::impl) )
  {
    v7 = 4;
    try
    {
      winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension::AddKnownPackageToProcessPackageGraph((const enum winrt::WindowsUdk::ApplicationModel::AppExtensions::KnownPackage *)&v7);
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, v5, v0, v1);
    }
  }
  else
  {
    winrt::hstring::hstring((winrt::hstring *)&v7, L"Microsoft.WindowsAppRuntime.CBS.1.6_8wekyb3d8bbwe", 0x31u);
    v3 = RegisterPackageDependency(&v7);
    v4 = v3;
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCC,
        (unsigned int)"pcshell\\shell\\settings\\settingsconfigtask\\lib\\settingsconfigtaskhandler.cpp",
        (const char *)(unsigned int)v3,
        v5[8]);
      return v4;
    }
  }
  winrt::impl::call_factory_cast<void (*)(winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics const &),winrt::Microsoft::Windows::Workloads::WorkloadManager,winrt::Microsoft::Windows::Workloads::IWorkloadManagerStatics,_lambda_9c7b9a15a6c0fa0ef4a186a43afb0906_>();
  return 0;
}

```

## disassembly

```asm
0x180013928  push    rbx; int
0x18001392a  sub     rsp, 20h
0x18001392e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion> `wil::Feature<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion>::GetImpl(void)'::`2'::impl
0x180013935  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion>::__private_IsEnabled(void)
0x18001393a  test    al, al
0x18001393c  jz      short loc_180013964
0x18001393e  mov     [rsp+28h+arg_0], 4
0x180013946  lea     rcx, [rsp+28h+arg_0]; enum winrt::WindowsUdk::ApplicationModel::AppExtensions::KnownPackage *
0x18001394b  call    ?AddKnownPackageToProcessPackageGraph@AppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@SA@AEBW4KnownPackage@2345@@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension::AddKnownPackageToProcessPackageGraph(winrt::WindowsUdk::ApplicationModel::AppExtensions::KnownPackage const &)
0x180013950  nop
0x180013951  call    ??$call_factory_cast@P6AXAEBUIWorkloadManagerStatics@Workloads@Windows@Microsoft@winrt@@@ZUWorkloadManager@2345@U12345@V_lambda_9c7b9a15a6c0fa0ef4a186a43afb0906_@@@impl@winrt@@YA?A_P$$QEAV_lambda_9c7b9a15a6c0fa0ef4a186a43afb0906_@@@Z
0x180013956  xor     eax, eax
0x180013958  add     rsp, 20h
0x18001395c  pop     rbx
0x18001395d  retn
0x18001395e  mov     eax, [rsp+28h+arg_0]
0x180013962  jmp     short loc_180013958
0x180013964  mov     r8d, 31h ; '1'; unsigned int
0x18001396a  lea     rdx, aMicrosoftWindo_2; "Microsoft.WindowsAppRuntime.CBS.1.6_8we"...
0x180013971  lea     rcx, [rsp+28h+arg_0]; this
0x180013976  call    ??0hstring@winrt@@QEAA@PEBGI@Z; winrt::hstring::hstring(ushort const *,uint)
0x18001397b  lea     rcx, [rsp+28h+arg_0]
0x180013980  call    ?RegisterPackageDependency@@YAJUhstring@winrt@@@Z; RegisterPackageDependency(winrt::hstring)
0x180013985  mov     ebx, eax
0x180013987  test    eax, eax
0x180013989  jns     short loc_180013951
0x18001398b  mov     rcx, [rsp+28h]; this
0x180013990  mov     r9d, eax; char *
0x180013993  lea     r8, aPcshellShellSe; "pcshell\\shell\\settings\\settingsconfi"...
0x18001399a  mov     edx, 0CCh; void *
0x18001399f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800139a4  mov     eax, ebx
0x1800139a6  jmp     short loc_180013958
```
