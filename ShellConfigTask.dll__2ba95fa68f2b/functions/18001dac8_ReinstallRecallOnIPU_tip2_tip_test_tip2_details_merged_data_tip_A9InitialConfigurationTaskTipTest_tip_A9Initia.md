# ReinstallRecallOnIPU(tip2::tip_test<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &)

- ea: `0x18001dac8`
- end: `0x18001dbd8`
- name: `?ReinstallRecallOnIPU@@YAJAEAV?$tip_test@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@@tip2@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001fd50`

## callees

- `0x180013bf8`
- `0x18001b7fc`
- `0x18001dac8`
- `0x18001e450`
- `0x18002065c`
- `0x180020f7c`
- `0x180022070`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001db2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001db8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001db2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001db8c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001db54`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001db54`

## string_xrefs

- `0x18001dbc3`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
__int64 __fastcall ReinstallRecallOnIPU(__int64 *a1, HKEY *a2)
{
  __int64 v4; // rdx
  int v5; // edi
  __int64 v6; // rbx
  int v7; // eax
  bool v8; // sf
  __int64 v9; // rbx
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v13; // [rsp+40h] [rbp+18h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769617>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56769617>::GetImpl'::`2'::impl) )
    AIXPolicyHelper::SetLastOperationKind(3, v4);
  v5 = InstallRecall(2);
  if ( v5 < 0 )
  {
    v9 = *tip2::tip_test<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::ensure_data(a1);
    v13 = v9;
    if ( v9 )
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 280));
    EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 200));
    ++*(_DWORD *)(v9 + 240);
    *(_DWORD *)(v9 + 272) = 17;
    tip2::test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::~test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>(&v13);
  }
  else
  {
    v6 = *tip2::tip_test<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::ensure_data(a1);
    v13 = v6;
    if ( v6 )
      _InterlockedIncrement((volatile signed __int32 *)(v6 + 280));
    EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 200));
    ++*(_DWORD *)(v6 + 240);
    *(_DWORD *)(v6 + 272) = 16;
    tip2::test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::~test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>(&v13);
    v7 = RegDeleteValueW(*a2, L"Selection");
    v8 = v7 < 0;
    if ( v7 > 0 )
    {
      v7 = (unsigned __int16)v7 | 0x80070000;
      v8 = v7 < 0;
    }
    if ( v8 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v7,
        v11);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001dac8  mov     [rsp+arg_0], rbx
0x18001dacd  mov     [rsp+arg_8], rsi
0x18001dad2  push    rdi; int
0x18001dad3  sub     rsp, 20h
0x18001dad7  mov     rsi, rdx
0x18001dada  mov     rbx, rcx
0x18001dadd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56769617@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56769617@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769617> `wil::Feature<__WilFeatureTraits_Feature_56769617>::GetImpl(void)'::`2'::impl
0x18001dae4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56769617@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769617>::__private_IsEnabled(void)
0x18001dae9  test    al, al
0x18001daeb  jz      short loc_18001DAF7
0x18001daed  mov     ecx, 3
0x18001daf2  call    ?SetLastOperationKind@AIXPolicyHelper@@YAXW4LastOperationKind@@PEAUHKEY__@@@Z; AIXPolicyHelper::SetLastOperationKind(LastOperationKind,HKEY__ *)
0x18001daf7  mov     ecx, 2
0x18001dafc  call    ?InstallRecall@@YAJW4TaskType@@@Z; InstallRecall(TaskType)
0x18001db01  mov     edi, eax
0x18001db03  mov     rcx, rbx
0x18001db06  test    eax, eax
0x18001db08  js      short loc_18001DB6C
0x18001db0a  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::ensure_data(void)
0x18001db0f  mov     rbx, [rax]
0x18001db12  mov     [rsp+28h+arg_10], rbx
0x18001db17  test    rbx, rbx
0x18001db1a  jz      short loc_18001DB23
0x18001db1c  lock inc dword ptr [rbx+118h]
0x18001db23  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001db2a  call    cs:__imp_EnterCriticalSection
0x18001db30  inc     dword ptr [rbx+0F0h]
0x18001db36  lea     rcx, [rsp+28h+arg_10]
0x18001db3b  mov     dword ptr [rbx+110h], 10h
0x18001db45  call    ??1?$test_data_control@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::~test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>(void)
0x18001db4a  mov     rcx, [rsi]; hKey
0x18001db4d  lea     rdx, aSelection; "Selection"
0x18001db54  call    cs:__imp_RegDeleteValueW
0x18001db5a  test    eax, eax
0x18001db5c  jle     short loc_18001DB68
0x18001db5e  movzx   eax, ax
0x18001db61  or      eax, 80070000h
0x18001db66  test    eax, eax
0x18001db68  js      short loc_18001DBBE
0x18001db6a  jmp     short loc_18001DBAC
0x18001db6c  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::ensure_data(void)
0x18001db71  mov     rbx, [rax]
0x18001db74  mov     [rsp+28h+arg_10], rbx
0x18001db79  test    rbx, rbx
0x18001db7c  jz      short loc_18001DB85
0x18001db7e  lock inc dword ptr [rbx+118h]
0x18001db85  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18001db8c  call    cs:__imp_EnterCriticalSection
0x18001db92  inc     dword ptr [rbx+0F0h]
0x18001db98  lea     rcx, [rsp+28h+arg_10]
0x18001db9d  mov     dword ptr [rbx+110h], 11h
0x18001dba7  call    ??1?$test_data_control@V?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>::~test_data_control<tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>>(void)
0x18001dbac  mov     rbx, [rsp+28h+arg_0]
0x18001dbb1  mov     eax, edi
0x18001dbb3  mov     rsi, [rsp+28h+arg_8]
0x18001dbb8  add     rsp, 20h
0x18001dbbc  pop     rdi
0x18001dbbd  retn
0x18001dbbe  mov     rcx, [rsp+28h]; this
0x18001dbc3  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001dbca  mov     r9d, eax; char *
0x18001dbcd  mov     edx, 1CBEh; void *
0x18001dbd2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
