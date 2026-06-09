# SettingsConfigTaskHandler::Worker(void)

- ea: `0x18001c380`
- end: `0x18001c409`
- name: `?Worker@SettingsConfigTaskHandler@@EEAAJXZ`
- size: `137`
- prototype: `__int64 __fastcall(SettingsConfigTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180013928`
- `0x180018614`
- `0x18001866c`
- `0x1800186c4`
- `0x18001871c`
- `0x180018d58`
- `0x180019150`
- `0x18001916c`
- `0x180019600`
- `0x18001bb84`
- `0x18001bfe4`
- `0x18001c150`
- `0x18001c380`
- `0x18001c8d0`

## string_xrefs

- `0x18001c3da`: `pcshell\shell\settings\settingsconfigtask\lib\settingsconfigtaskhandler.cpp`

## pseudocode

```c
__int64 __fastcall SettingsConfigTaskHandler::Worker(SettingsConfigTaskHandler *this)
{
  int v1; // ebx
  SystemSettings::FeatureEnablement *v2; // rcx
  int v4; // eax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  SettingsDownloadTelemetry::InitialTask_Started();
  if ( ShouldInitializeModel() )
  {
    v1 = 0;
    if ( IsOobeInEnduserSession() || IsOOBEComplete() || (v1 = WaitForEnduserSessionOOBEOrOOBEComplete(), v1 >= 0) )
    {
      if ( SystemSettings::FeatureEnablement::IsCommandSearchEnabled(v2) )
      {
        v4 = EnsureWinAppSDKRegistration();
        if ( v4 >= 0 )
        {
          InstallModels();
          UpdateLCUVersionInRegistry();
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xF6,
            (unsigned int)"pcshell\\shell\\settings\\settingsconfigtask\\lib\\settingsconfigtaskhandler.cpp",
            (const char *)(unsigned int)v4,
            v5);
        }
      }
      else
      {
        SettingsDownloadTelemetry::ModelInstallationBlockedByCommandSearchDisablement();
      }
    }
    else
    {
      SettingsDownloadTelemetry::InitialTask_WaitForCorrectOOBEStateFailed();
    }
    return (unsigned int)v1;
  }
  else
  {
    SettingsDownloadTelemetry::InitialTask_SkippedRunningwithNoUpdate();
    return 0;
  }
}

```

## disassembly

```asm
0x18001c380  push    rbx; int
0x18001c382  sub     rsp, 20h
0x18001c386  call    ?InitialTask_Started@SettingsDownloadTelemetry@@SAXXZ; SettingsDownloadTelemetry::InitialTask_Started(void)
0x18001c38b  call    ?ShouldInitializeModel@@YA_NXZ; ShouldInitializeModel(void)
0x18001c390  test    al, al
0x18001c392  jz      short loc_18001C3FC
0x18001c394  xor     ebx, ebx
0x18001c396  call    ?IsOobeInEnduserSession@@YA_NXZ; IsOobeInEnduserSession(void)
0x18001c39b  test    al, al
0x18001c39d  jnz     short loc_18001C3BC
0x18001c39f  call    ?IsOOBEComplete@@YA_NXZ; IsOOBEComplete(void)
0x18001c3a4  test    al, al
0x18001c3a6  jnz     short loc_18001C3BC
0x18001c3a8  call    ?WaitForEnduserSessionOOBEOrOOBEComplete@@YAJXZ; WaitForEnduserSessionOOBEOrOOBEComplete(void)
0x18001c3ad  mov     ebx, eax
0x18001c3af  test    eax, eax
0x18001c3b1  jns     short loc_18001C3BC
0x18001c3b3  call    ?InitialTask_WaitForCorrectOOBEStateFailed@SettingsDownloadTelemetry@@SAXXZ; SettingsDownloadTelemetry::InitialTask_WaitForCorrectOOBEStateFailed(void)
0x18001c3b8  mov     eax, ebx
0x18001c3ba  jmp     short loc_18001C403
0x18001c3bc  call    ?IsCommandSearchEnabled@FeatureEnablement@SystemSettings@@YA_NXZ; SystemSettings::FeatureEnablement::IsCommandSearchEnabled(void)
0x18001c3c1  test    al, al
0x18001c3c3  jnz     short loc_18001C3CC
0x18001c3c5  call    ?ModelInstallationBlockedByCommandSearchDisablement@SettingsDownloadTelemetry@@SAXXZ; SettingsDownloadTelemetry::ModelInstallationBlockedByCommandSearchDisablement(void)
0x18001c3ca  jmp     short loc_18001C3B8
0x18001c3cc  call    ?EnsureWinAppSDKRegistration@@YAJXZ; EnsureWinAppSDKRegistration(void)
0x18001c3d1  test    eax, eax
0x18001c3d3  jns     short loc_18001C3F0
0x18001c3d5  mov     rcx, [rsp+28h]; this
0x18001c3da  lea     r8, aPcshellShellSe; "pcshell\\shell\\settings\\settingsconfi"...
0x18001c3e1  mov     r9d, eax; char *
0x18001c3e4  mov     edx, 0F6h; void *
0x18001c3e9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c3ee  jmp     short loc_18001C3B8
0x18001c3f0  call    ?InstallModels@@YAXXZ; InstallModels(void)
0x18001c3f5  call    ?UpdateLCUVersionInRegistry@@YAXXZ; UpdateLCUVersionInRegistry(void)
0x18001c3fa  jmp     short loc_18001C3B8
0x18001c3fc  call    ?InitialTask_SkippedRunningwithNoUpdate@SettingsDownloadTelemetry@@SAXXZ; SettingsDownloadTelemetry::InitialTask_SkippedRunningwithNoUpdate(void)
0x18001c401  xor     eax, eax
0x18001c403  add     rsp, 20h
0x18001c407  pop     rbx
0x18001c408  retn
```
