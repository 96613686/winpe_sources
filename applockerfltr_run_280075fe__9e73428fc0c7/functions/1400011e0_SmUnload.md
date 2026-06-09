# SmUnload

- ea: `0x1400011e0`
- end: `0x1400012c0`
- name: `SmUnload`
- size: `224`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1400011e0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140001211`
- `ntoskrnl!ZwClose` at `0x140001211`
- `ntoskrnl!EtwUnregister` at `0x140001239`
- `ntoskrnl!EtwUnregister` at `0x140001251`
- `ntoskrnl!EtwUnregister` at `0x140001239`
- `ntoskrnl!EtwUnregister` at `0x140001251`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140001274`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x140001274`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140001297`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x140001297`
- `ntoskrnl!CmUnRegisterCallback` at `0x1400011fe`
- `ntoskrnl!CmUnRegisterCallback` at `0x1400011fe`
- `FLTMGR!FltUnregisterFilter` at `0x1400011eb`
- `FLTMGR!FltUnregisterFilter` at `0x1400011eb`

## pseudocode

```c
__int64 SmUnload()
{
  REGHANDLE v0; // rcx

  FltUnregisterFilter(Filter);
  CmUnRegisterCallback(Cookie);
  ZwClose(Handle);
  v0 = RegHandle;
  dword_140004010 = 0;
  RegHandle = 0;
  EtwUnregister(v0);
  if ( g_EtwEventHandle )
  {
    EtwUnregister(g_EtwEventHandle);
    g_EtwEventHandle = 0;
  }
  if ( g_wil_details_featureChangeNotification )
  {
    RtlUnregisterFeatureConfigurationChangeNotification();
    g_wil_details_featureChangeNotification = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  g_wil_details_isFeatureStagingInitialized = 0;
  return 0;
}

```

## disassembly

```asm
0x1400011e0  sub     rsp, 28h
0x1400011e4  mov     rcx, cs:Filter; Filter
0x1400011eb  call    cs:__imp_FltUnregisterFilter
0x1400011f2  nop     dword ptr [rax+rax+00h]
0x1400011f7  mov     rcx, qword ptr cs:Cookie; Cookie
0x1400011fe  call    cs:__imp_CmUnRegisterCallback
0x140001205  nop     dword ptr [rax+rax+00h]
0x14000120a  mov     rcx, cs:Handle; Handle
0x140001211  call    cs:__imp_ZwClose
0x140001218  nop     dword ptr [rax+rax+00h]
0x14000121d  mov     rcx, cs:RegHandle; RegHandle
0x140001224  mov     cs:dword_140004010, 0
0x14000122e  mov     cs:RegHandle, 0
0x140001239  call    cs:__imp_EtwUnregister
0x140001240  nop     dword ptr [rax+rax+00h]
0x140001245  mov     rcx, cs:g_EtwEventHandle; RegHandle
0x14000124c  test    rcx, rcx
0x14000124f  jz      short loc_140001268
0x140001251  call    cs:__imp_EtwUnregister
0x140001258  nop     dword ptr [rax+rax+00h]
0x14000125d  mov     cs:g_EtwEventHandle, 0
0x140001268  mov     rcx, cs:g_wil_details_featureChangeNotification
0x14000126f  test    rcx, rcx
0x140001272  jz      short loc_14000128B
0x140001274  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14000127b  nop     dword ptr [rax+rax+00h]
0x140001280  mov     cs:g_wil_details_featureChangeNotification, 0
0x14000128b  mov     rcx, cs:g_wil_details_featureUsageProvider
0x140001292  test    rcx, rcx
0x140001295  jz      short loc_1400012AE
0x140001297  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14000129e  nop     dword ptr [rax+rax+00h]
0x1400012a3  mov     cs:g_wil_details_featureUsageProvider, 0
0x1400012ae  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x1400012b8  xor     eax, eax
0x1400012ba  add     rsp, 28h
0x1400012be  retn
```
