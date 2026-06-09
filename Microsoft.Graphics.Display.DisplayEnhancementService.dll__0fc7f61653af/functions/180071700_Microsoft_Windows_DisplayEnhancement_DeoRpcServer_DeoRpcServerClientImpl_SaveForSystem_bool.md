# Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerClientImpl::SaveForSystem(bool)

- ea: `0x180071700`
- end: `0x180071933`
- name: `?SaveForSystem@DeoRpcServerClientImpl@DeoRpcServer@DisplayEnhancement@Windows@Microsoft@@UEAAX_N@Z`
- size: `563`
- prototype: `void __fastcall(Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerClientImpl *__hidden this, bool)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000fa0c`
- `0x180013138`
- `0x18006ce0c`
- `0x18006dc20`
- `0x180071700`

## import_xrefs

- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18007175f`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18007175f`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x1800717b6`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x180071885`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x1800717b6`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x180071885`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x1800717ed`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x1800718bc`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x1800717ed`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x1800718bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007191d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007191d`
- `POWRPROF!PowerApplySettingChanges` at `0x180071816`
- `POWRPROF!PowerApplySettingChanges` at `0x1800718e9`
- `POWRPROF!PowerApplySettingChanges` at `0x180071816`
- `POWRPROF!PowerApplySettingChanges` at `0x1800718e9`

## string_xrefs

- `0x18007172b`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserverclient.cpp`
- `0x180071770`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserverclient.cpp`
- `0x1800717c7`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserverclient.cpp`
- `0x1800717fe`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserverclient.cpp`
- `0x18007182b`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserverclient.cpp`
- `0x180071896`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserverclient.cpp`
- `0x1800718cd`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserverclient.cpp`
- `0x1800718fa`: `onecoreuap\drivers\mobilepc\displayenhancement\service\displayenhancementoverride\server\lib\deorpcserverclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerClientImpl::SaveForSystem(
        Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerClientImpl *this,
        char a2)
{
  DWORD ActiveScheme; // eax
  DWORD v5; // eax
  DWORD v6; // eax
  unsigned int v7; // eax
  DWORD BrightnessPercentage; // edi
  DWORD v9; // eax
  DWORD v10; // eax
  unsigned int v11; // eax
  GUID *v12; // rcx
  DWORD AcValueIndex; // [rsp+20h] [rbp-30h]
  DWORD AcValueIndexa; // [rsp+20h] [rbp-30h]
  DWORD AcValueIndexb; // [rsp+20h] [rbp-30h]
  DWORD AcValueIndexc; // [rsp+20h] [rbp-30h]
  DWORD AcValueIndexd; // [rsp+20h] [rbp-30h]
  GUID **p_SchemeGuid; // [rsp+30h] [rbp-20h] BYREF
  GUID *ActivePolicyGuid; // [rsp+38h] [rbp-18h] BYREF
  char v20; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  GUID *SchemeGuid; // [rsp+60h] [rbp+10h] BYREF

  if ( !*((_BYTE *)this + 240) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x295,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverride\\server\\lib\\"
                    "deorpcserverclient.cpp",
      (const char *)0x80070005LL,
      AcValueIndex);
  SchemeGuid = 0;
  p_SchemeGuid = &SchemeGuid;
  ActivePolicyGuid = 0;
  v20 = 1;
  ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
  if ( ActiveScheme )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x299,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverride\\server\\lib\\"
                    "deorpcserverclient.cpp",
      (const char *)ActiveScheme,
      AcValueIndex);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_SchemeGuid);
  if ( a2 )
  {
    v5 = PowerWriteACValueIndex(0, SchemeGuid, &GUID_VIDEO_SUBGROUP, &GUID_VIDEO_ADAPTIVE_DISPLAY_BRIGHTNESS, 1u);
    if ( v5 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x29D,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverride\\server\\li"
                      "b\\deorpcserverclient.cpp",
        (const char *)v5,
        AcValueIndexa);
    v6 = PowerWriteDCValueIndex(0, SchemeGuid, &GUID_VIDEO_SUBGROUP, &GUID_VIDEO_ADAPTIVE_DISPLAY_BRIGHTNESS, 1u);
    if ( v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x29E,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverride\\server\\li"
                      "b\\deorpcserverclient.cpp",
        (const char *)v6,
        AcValueIndexb);
    v7 = PowerApplySettingChanges(&GUID_VIDEO_SUBGROUP, &GUID_VIDEO_ADAPTIVE_DISPLAY_BRIGHTNESS);
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x29F,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverride\\server\\li"
                      "b\\deorpcserverclient.cpp",
        (const char *)v7,
        AcValueIndexb);
  }
  else
  {
    Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerClientImpl::GetBrightnessPercentage(this);
    BrightnessPercentage = 100;
    if ( Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerClientImpl::GetBrightnessPercentage(this) <= 0x64u )
    {
      Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerClientImpl::GetBrightnessPercentage(this);
      BrightnessPercentage = Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerClientImpl::GetBrightnessPercentage(this);
    }
    v9 = PowerWriteACValueIndex(
           0,
           SchemeGuid,
           &GUID_VIDEO_SUBGROUP,
           &GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS,
           BrightnessPercentage);
    if ( v9 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2A4,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverride\\server\\li"
                      "b\\deorpcserverclient.cpp",
        (const char *)v9,
        AcValueIndexc);
    v10 = PowerWriteDCValueIndex(
            0,
            SchemeGuid,
            &GUID_VIDEO_SUBGROUP,
            &GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS,
            BrightnessPercentage);
    if ( v10 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2A5,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverride\\server\\li"
                      "b\\deorpcserverclient.cpp",
        (const char *)v10,
        AcValueIndexd);
    v11 = PowerApplySettingChanges(&GUID_VIDEO_SUBGROUP, &GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS);
    if ( v11 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\displayenhancementoverride\\server\\li"
                      "b\\deorpcserverclient.cpp",
        (const char *)v11,
        AcValueIndexd);
  }
  v12 = SchemeGuid;
  SchemeGuid = 0;
  if ( v12 )
    LocalFree(v12);
}

```

## disassembly

```asm
0x180071700  mov     [rsp-8+arg_8], rbx
0x180071705  mov     [rsp-8+arg_10], rdi
0x18007170a  push    rbp
0x18007170b  mov     rbp, rsp
0x18007170e  sub     rsp, 50h
0x180071712  mov     dil, dl
0x180071715  mov     rbx, rcx
0x180071718  mov     rcx, [rbp+8]; this
0x18007171c  cmp     byte ptr [rbx+0F0h], 0
0x180071723  jnz     short loc_18007173D
0x180071725  mov     r9d, 80070005h; char *
0x18007172b  lea     r8, aOnecoreuapDriv_9; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180071732  mov     edx, 295h; void *
0x180071737  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007173d  mov     [rbp+SchemeGuid], 0
0x180071745  lea     rax, [rbp+SchemeGuid]
0x180071749  mov     [rbp+var_20], rax
0x18007174d  mov     [rbp+ActivePolicyGuid], 0
0x180071755  mov     [rbp+var_10], 1
0x180071759  lea     rdx, [rbp+ActivePolicyGuid]; ActivePolicyGuid
0x18007175d  xor     ecx, ecx; UserRootPowerKey
0x18007175f  call    cs:__imp_PowerGetActiveScheme
0x180071765  mov     rcx, [rbp+8]; this
0x180071769  test    eax, eax
0x18007176b  jz      short loc_180071782
0x18007176d  mov     r9d, eax; char *
0x180071770  lea     r8, aOnecoreuapDriv_9; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180071777  mov     edx, 299h; void *
0x18007177c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180071782  lea     rcx, [rbp+var_20]
0x180071786  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18007178b  test    dil, dil
0x18007178e  jz      loc_18007183D
0x180071794  mov     [rsp+50h+AcValueIndex], 1; unsigned int
0x18007179c  lea     rdi, GUID_VIDEO_ADAPTIVE_DISPLAY_BRIGHTNESS
0x1800717a3  mov     r9, rdi; PowerSettingGuid
0x1800717a6  lea     rbx, GUID_VIDEO_SUBGROUP
0x1800717ad  mov     r8, rbx; SubGroupOfPowerSettingsGuid
0x1800717b0  mov     rdx, [rbp+SchemeGuid]; SchemeGuid
0x1800717b4  xor     ecx, ecx; RootPowerKey
0x1800717b6  call    cs:__imp_PowerWriteACValueIndex
0x1800717bc  mov     rcx, [rbp+8]; this
0x1800717c0  test    eax, eax
0x1800717c2  jz      short loc_1800717D9
0x1800717c4  mov     r9d, eax; char *
0x1800717c7  lea     r8, aOnecoreuapDriv_9; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800717ce  mov     edx, 29Dh; void *
0x1800717d3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800717d9  mov     [rsp+50h+AcValueIndex], 1; unsigned int
0x1800717e1  mov     r9, rdi; PowerSettingGuid
0x1800717e4  mov     r8, rbx; SubGroupOfPowerSettingsGuid
0x1800717e7  mov     rdx, [rbp+SchemeGuid]; SchemeGuid
0x1800717eb  xor     ecx, ecx; RootPowerKey
0x1800717ed  call    cs:__imp_PowerWriteDCValueIndex
0x1800717f3  mov     rcx, [rbp+8]; this
0x1800717f7  test    eax, eax
0x1800717f9  jz      short loc_180071810
0x1800717fb  mov     r9d, eax; char *
0x1800717fe  lea     r8, aOnecoreuapDriv_9; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180071805  mov     edx, 29Eh; void *
0x18007180a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180071810  mov     rdx, rdi
0x180071813  mov     rcx, rbx
0x180071816  call    cs:__imp_PowerApplySettingChanges
0x18007181c  mov     rcx, [rbp+8]; this
0x180071820  test    eax, eax
0x180071822  jz      loc_18007190C
0x180071828  mov     r9d, eax; char *
0x18007182b  lea     r8, aOnecoreuapDriv_9; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180071832  mov     edx, 29Fh; void *
0x180071837  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18007183d  mov     rcx, rbx; this
0x180071840  call    ?GetBrightnessPercentage@DeoRpcServerClientImpl@DeoRpcServer@DisplayEnhancement@Windows@Microsoft@@UEAAEXZ; Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerClientImpl::GetBrightnessPercentage(void)
0x180071845  mov     rcx, rbx; this
0x180071848  call    ?GetBrightnessPercentage@DeoRpcServerClientImpl@DeoRpcServer@DisplayEnhancement@Windows@Microsoft@@UEAAEXZ; Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerClientImpl::GetBrightnessPercentage(void)
0x18007184d  mov     edi, 64h ; 'd'
0x180071852  cmp     al, dil
0x180071855  ja      short loc_18007186A
0x180071857  mov     rcx, rbx; this
0x18007185a  call    ?GetBrightnessPercentage@DeoRpcServerClientImpl@DeoRpcServer@DisplayEnhancement@Windows@Microsoft@@UEAAEXZ; Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerClientImpl::GetBrightnessPercentage(void)
0x18007185f  mov     rcx, rbx; this
0x180071862  call    ?GetBrightnessPercentage@DeoRpcServerClientImpl@DeoRpcServer@DisplayEnhancement@Windows@Microsoft@@UEAAEXZ; Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServerClientImpl::GetBrightnessPercentage(void)
0x180071867  movzx   edi, al
0x18007186a  mov     [rsp+50h+AcValueIndex], edi; unsigned int
0x18007186e  lea     r9, GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS; PowerSettingGuid
0x180071875  lea     rbx, GUID_VIDEO_SUBGROUP
0x18007187c  mov     r8, rbx; SubGroupOfPowerSettingsGuid
0x18007187f  mov     rdx, [rbp+SchemeGuid]; SchemeGuid
0x180071883  xor     ecx, ecx; RootPowerKey
0x180071885  call    cs:__imp_PowerWriteACValueIndex
0x18007188b  mov     rcx, [rbp+8]; this
0x18007188f  test    eax, eax
0x180071891  jz      short loc_1800718A8
0x180071893  mov     r9d, eax; char *
0x180071896  lea     r8, aOnecoreuapDriv_9; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18007189d  mov     edx, 2A4h; void *
0x1800718a2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800718a8  mov     [rsp+50h+AcValueIndex], edi; unsigned int
0x1800718ac  lea     r9, GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS; PowerSettingGuid
0x1800718b3  mov     r8, rbx; SubGroupOfPowerSettingsGuid
0x1800718b6  mov     rdx, [rbp+SchemeGuid]; SchemeGuid
0x1800718ba  xor     ecx, ecx; RootPowerKey
0x1800718bc  call    cs:__imp_PowerWriteDCValueIndex
0x1800718c2  mov     rcx, [rbp+8]; this
0x1800718c6  test    eax, eax
0x1800718c8  jz      short loc_1800718DF
0x1800718ca  mov     r9d, eax; char *
0x1800718cd  lea     r8, aOnecoreuapDriv_9; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800718d4  mov     edx, 2A5h; void *
0x1800718d9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800718df  lea     rdx, GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS
0x1800718e6  mov     rcx, rbx
0x1800718e9  call    cs:__imp_PowerApplySettingChanges
0x1800718ef  mov     rcx, [rbp+8]; this
0x1800718f3  test    eax, eax
0x1800718f5  jz      short loc_18007190C
0x1800718f7  mov     r9d, eax; char *
0x1800718fa  lea     r8, aOnecoreuapDriv_9; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x180071901  mov     edx, 2A6h; void *
0x180071906  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18007190c  mov     rcx, [rbp+SchemeGuid]; hMem
0x180071910  mov     [rbp+SchemeGuid], 0
0x180071918  test    rcx, rcx
0x18007191b  jz      short loc_180071923
0x18007191d  call    cs:__imp_LocalFree
0x180071923  mov     rbx, [rsp+50h+arg_8]
0x180071928  mov     rdi, [rsp+50h+arg_10]
0x18007192d  add     rsp, 50h
0x180071931  pop     rbp
0x180071932  retn
```
