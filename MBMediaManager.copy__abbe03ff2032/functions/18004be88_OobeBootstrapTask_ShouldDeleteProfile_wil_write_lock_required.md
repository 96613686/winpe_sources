# OobeBootstrapTask::ShouldDeleteProfile(wil::write_lock_required)

- ea: `0x18004be88`
- end: `0x18004bf72`
- name: `?ShouldDeleteProfile@OobeBootstrapTask@@AEAA_NUwrite_lock_required@wil@@@Z`
- size: `234`
- prototype: `char __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f600`
- `0x18004b790`

## callees

- `0x18000ad20`
- `0x18004be88`
- `0x18004c2c0`
- `0x18004c9d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004bf33`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004bf33`

## string_xrefs

- `0x18004be9a`: `Already running/ran deletion`
- `0x18004bea6`: `OobeBootstrapTask::ShouldDeleteProfile`
- `0x18004bef1`: `OobeBootstrapTask::ShouldDeleteProfile`
- `0x18004bf19`: `OobeBootstrapTask::ShouldDeleteProfile`
- `0x18004bf0d`: `Data not available regarding bootstrap profile, Changing state to 'Complete'`
- `0x18004bf45`: `profile is not bootstrap, Changing state to 'Complete'`
- `0x18004bf59`: `Esim Service is not idle`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
char __fastcall OobeBootstrapTask::ShouldDeleteProfile(__int64 a1, char a2)
{
  __int64 v4; // rcx
  HANDLE *v5; // rcx
  char v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = a2;
  if ( *(_DWORD *)(a1 + 96) )
  {
    MBSettingUXLogging::Info("OobeBootstrapTask::ShouldDeleteProfile", 0x110u, "Already running/ran deletion");
    return 0;
  }
  v4 = a1 + 128;
  if ( !*(_QWORD *)(v4 + 16) )
  {
    MBSettingUXLogging::Info("OobeBootstrapTask::ShouldDeleteProfile", 0x117u, "No Enabled profile detected");
    return 0;
  }
  v6 = 0;
  if ( (int)MBUtil::GetIsBootstrapProfile(v4, &v6) < 0 )
  {
    MBSettingUXLogging::Info("OobeBootstrapTask::ShouldDeleteProfile", 0x11Fu, "GetIsBootstrapProfile failed");
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58322156>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_58322156>::GetImpl'::`2'::impl) )
      return 0;
    MBSettingUXLogging::Info(
      "OobeBootstrapTask::ShouldDeleteProfile",
      0x123u,
      "Data not available regarding bootstrap profile, Changing state to 'Complete'");
LABEL_9:
    v5 = *(HANDLE **)(a1 + 88);
    *(_DWORD *)(a1 + 96) = 2;
    SetEvent(*v5);
    return 0;
  }
  if ( !v6 )
  {
    MBSettingUXLogging::Info(
      "OobeBootstrapTask::ShouldDeleteProfile",
      0x12Du,
      "profile is not bootstrap, Changing state to 'Complete'");
    goto LABEL_9;
  }
  if ( *(_DWORD *)(a1 + 104) != 1 )
  {
    MBSettingUXLogging::Info("OobeBootstrapTask::ShouldDeleteProfile", 0x136u, "Esim Service is not idle");
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18004be88  mov     [rsp+arg_8], dl
0x18004be8c  push    rbx
0x18004be8d  sub     rsp, 20h
0x18004be91  cmp     dword ptr [rcx+60h], 0
0x18004be95  mov     rbx, rcx
0x18004be98  jz      short loc_18004BEB9
0x18004be9a  lea     r8, aAlreadyRunning_0; "Already running/ran deletion"
0x18004bea1  mov     edx, 110h; unsigned int
0x18004bea6  lea     rcx, aOobebootstrapt_3; "OobeBootstrapTask::ShouldDeleteProfile"
0x18004bead  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18004beb2  xor     al, al
0x18004beb4  jmp     loc_18004BF6C
0x18004beb9  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18004bebd  cmp     qword ptr [rcx+10h], 0
0x18004bec2  jnz     short loc_18004BED2
0x18004bec4  lea     r8, aNoEnabledProfi; "No Enabled profile detected"
0x18004becb  mov     edx, 117h
0x18004bed0  jmp     short loc_18004BEA6
0x18004bed2  lea     rdx, [rsp+28h+arg_8]
0x18004bed7  mov     [rsp+28h+arg_8], 0
0x18004bedc  call    ?GetIsBootstrapProfile@MBUtil@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEA_N@Z; MBUtil::GetIsBootstrapProfile(std::wstring const &,bool *)
0x18004bee1  test    eax, eax
0x18004bee3  jns     short loc_18004BF3E
0x18004bee5  lea     r8, aGetisbootstrap; "GetIsBootstrapProfile failed"
0x18004beec  mov     edx, 11Fh; unsigned int
0x18004bef1  lea     rcx, aOobebootstrapt_3; "OobeBootstrapTask::ShouldDeleteProfile"
0x18004bef8  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18004befd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58322156@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58322156@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58322156> `wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_58322156>::GetImpl(void)'::`2'::impl
0x18004bf04  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58322156@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58322156>::__private_IsEnabled(void)
0x18004bf09  test    al, al
0x18004bf0b  jz      short loc_18004BEB2
0x18004bf0d  lea     r8, aDataNotAvailab; "Data not available regarding bootstrap "...
0x18004bf14  mov     edx, 123h; unsigned int
0x18004bf19  lea     rcx, aOobebootstrapt_3; "OobeBootstrapTask::ShouldDeleteProfile"
0x18004bf20  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18004bf25  mov     rcx, [rbx+58h]
0x18004bf29  mov     dword ptr [rbx+60h], 2
0x18004bf30  mov     rcx, [rcx]; hEvent
0x18004bf33  call    cs:__imp_SetEvent
0x18004bf39  jmp     loc_18004BEB2
0x18004bf3e  cmp     [rsp+28h+arg_8], 0
0x18004bf43  jnz     short loc_18004BF53
0x18004bf45  lea     r8, aProfileIsNotBo; "profile is not bootstrap, Changing stat"...
0x18004bf4c  mov     edx, 12Dh
0x18004bf51  jmp     short loc_18004BF19
0x18004bf53  cmp     dword ptr [rbx+68h], 1
0x18004bf57  jz      short loc_18004BF6A
0x18004bf59  lea     r8, aEsimServiceIsN; "Esim Service is not idle"
0x18004bf60  mov     edx, 136h
0x18004bf65  jmp     loc_18004BEA6
0x18004bf6a  mov     al, 1
0x18004bf6c  add     rsp, 20h
0x18004bf70  pop     rbx
0x18004bf71  retn
```
