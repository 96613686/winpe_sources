# HoldRecallConfigTaskUntilCorrectOOBEStateReached(tip2::tip_test<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>> &)

- ea: `0x18001a754`
- end: `0x18001a842`
- name: `?HoldRecallConfigTaskUntilCorrectOOBEStateReached@@YAJAEAV?$tip_test@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@@tip2@@@Z`
- size: `238`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001fd50`

## callees

- `0x180013bf8`
- `0x18001a754`
- `0x18001cea8`
- `0x18001cfb0`
- `0x18001d6d0`
- `0x18001f604`
- `0x18001f998`
- `0x180020a7c`
- `0x180022070`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a7b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a80e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a7b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a80e`

## pseudocode

```c
__int64 __fastcall HoldRecallConfigTaskUntilCorrectOOBEStateReached(__int64 *a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rbx
  __int64 v5; // rbx
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54587088>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54587088>::GetImpl'::`2'::impl) )
  {
    if ( !IsOobeInEnduserSession()
      && (unsigned int)winrt::Windows::System::Profile::SystemSetupInfo::OutOfBoxExperienceState() != 2 )
    {
      v3 = *tip2::tip_test<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::ensure_data(a1);
      v7 = v3;
      if ( v3 )
        _InterlockedIncrement((volatile signed __int32 *)(v3 + 280));
      EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 200));
      ++*(_DWORD *)(v3 + 240);
      *(_DWORD *)(v3 + 272) = 15;
      tip2::test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::~test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>(&v7);
      return (unsigned int)WaitForEnduserSessionOOBEOrOOBEComplete();
    }
  }
  else if ( !IsNDUPComplete()
         && (unsigned int)winrt::Windows::System::Profile::SystemSetupInfo::OutOfBoxExperienceState() != 2 )
  {
    v5 = *tip2::tip_test<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::ensure_data(a1);
    v7 = v5;
    if ( v5 )
      _InterlockedIncrement((volatile signed __int32 *)(v5 + 280));
    EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 200));
    ++*(_DWORD *)(v5 + 240);
    *(_DWORD *)(v5 + 272) = 10;
    tip2::test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::~test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>(&v7);
    return (unsigned int)WaitForOOBEOrNDUP();
  }
  return v2;
}

```

## disassembly

```asm
0x18001a754  mov     [rsp+arg_0], rbx
0x18001a759  push    rdi
0x18001a75a  sub     rsp, 20h
0x18001a75e  mov     rdi, rcx
0x18001a761  xor     ebx, ebx
0x18001a763  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_54587088@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_54587088@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54587088> `wil::Feature<__WilFeatureTraits_Feature_54587088>::GetImpl(void)'::`2'::impl
0x18001a76a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_54587088@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54587088>::__private_IsEnabled(void)
0x18001a76f  test    al, al
0x18001a771  jz      short loc_18001A7D8
0x18001a773  call    ?IsOobeInEnduserSession@@YA_NXZ; IsOobeInEnduserSession(void)
0x18001a778  test    al, al
0x18001a77a  jnz     loc_18001A835
0x18001a780  call    ?OutOfBoxExperienceState@SystemSetupInfo@Profile@System@Windows@winrt@@SA@XZ; winrt::Windows::System::Profile::SystemSetupInfo::OutOfBoxExperienceState(void)
0x18001a785  cmp     eax, 2
0x18001a788  jz      loc_18001A835
0x18001a78e  mov     rcx, rdi
0x18001a791  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::ensure_data(void)
0x18001a796  mov     rbx, [rax]
0x18001a799  mov     [rsp+28h+arg_8], rbx
0x18001a79e  test    rbx, rbx
0x18001a7a1  jz      short loc_18001A7AA
0x18001a7a3  lock inc dword ptr [rbx+118h]
0x18001a7aa  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001a7b1  call    cs:__imp_EnterCriticalSection
0x18001a7b7  inc     dword ptr [rbx+0F0h]
0x18001a7bd  lea     rcx, [rsp+28h+arg_8]
0x18001a7c2  mov     dword ptr [rbx+110h], 0Fh
0x18001a7cc  call    ??1?$test_data_control@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::~test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>(void)
0x18001a7d1  call    ?WaitForEnduserSessionOOBEOrOOBEComplete@@YAJXZ; WaitForEnduserSessionOOBEOrOOBEComplete(void)
0x18001a7d6  jmp     short loc_18001A833
0x18001a7d8  call    ?IsNDUPComplete@@YA_NXZ; IsNDUPComplete(void)
0x18001a7dd  test    al, al
0x18001a7df  jnz     short loc_18001A835
0x18001a7e1  call    ?OutOfBoxExperienceState@SystemSetupInfo@Profile@System@Windows@winrt@@SA@XZ; winrt::Windows::System::Profile::SystemSetupInfo::OutOfBoxExperienceState(void)
0x18001a7e6  cmp     eax, 2
0x18001a7e9  jz      short loc_18001A835
0x18001a7eb  mov     rcx, rdi
0x18001a7ee  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::ensure_data(void)
0x18001a7f3  mov     rbx, [rax]
0x18001a7f6  mov     [rsp+28h+arg_8], rbx
0x18001a7fb  test    rbx, rbx
0x18001a7fe  jz      short loc_18001A807
0x18001a800  lock inc dword ptr [rbx+118h]
0x18001a807  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001a80e  call    cs:__imp_EnterCriticalSection
0x18001a814  inc     dword ptr [rbx+0F0h]
0x18001a81a  lea     rcx, [rsp+28h+arg_8]
0x18001a81f  mov     dword ptr [rbx+110h], 0Ah
0x18001a829  call    ??1?$test_data_control@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::~test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>(void)
0x18001a82e  call    ?WaitForOOBEOrNDUP@@YAJXZ; WaitForOOBEOrNDUP(void)
0x18001a833  mov     ebx, eax
0x18001a835  mov     eax, ebx
0x18001a837  mov     rbx, [rsp+28h+arg_0]
0x18001a83c  add     rsp, 20h
0x18001a840  pop     rdi
0x18001a841  retn
```
