# NetSetupService::GetRpcIdleTimeout(void)

- ea: `0x18000a570`
- end: `0x18000a640`
- name: `?GetRpcIdleTimeout@NetSetupService@@AEAA?AV?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@XZ`
- size: `208`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000a6d4`

## callees

- `0x1800027c0`
- `0x180008e3c`
- `0x18000a570`
- `0x18000da24`
- `0x1800275e4`
- `0x1800285cc`
- `0x1800286d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall NetSetupService::GetRpcIdleTimeout(__int64 a1, _QWORD *a2)
{
  HKEY v5; // [rsp+30h] [rbp-18h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DemandStartNetsetupInAI>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DemandStartNetsetupInAI>::GetImpl'::`2'::impl)
    && *(_BYTE *)(a1 + 400) )
  {
    *a2 = 60;
  }
  else
  {
    RegistryKey::TryOpenSubKey(a1 + 280, &v5, L"Control\\NetworkSetup2\\Parameters", 1, 0);
    if ( v5 && RegistryKey::ValueExists((RegistryKey *)&v5, L"NetSetupSvcIdleTimeout") )
      *a2 = (unsigned int)RegistryKey::GetValueDword(&v5, L"NetSetupSvcIdleTimeout", 0, 0);
    else
      *a2 = 3;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v5);
  }
  return a2;
}

```

## disassembly

```asm
0x18000a570  mov     [rsp+arg_10], rbx
0x18000a575  push    rdi
0x18000a576  sub     rsp, 40h
0x18000a57a  mov     rax, cs:__security_cookie
0x18000a581  xor     rax, rsp
0x18000a584  mov     [rsp+48h+var_10], rax
0x18000a589  mov     rbx, rdx
0x18000a58c  mov     rdi, rcx
0x18000a58f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DemandStartNetsetupInAI@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DemandStartNetsetupInAI@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DemandStartNetsetupInAI> `wil::Feature<__WilFeatureTraits_Feature_DemandStartNetsetupInAI>::GetImpl(void)'::`2'::impl
0x18000a596  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DemandStartNetsetupInAI@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DemandStartNetsetupInAI>::__private_IsEnabled(void)
0x18000a59b  test    al, al
0x18000a59d  jz      short loc_18000A5B1
0x18000a59f  cmp     byte ptr [rdi+190h], 0
0x18000a5a6  jz      short loc_18000A5B1
0x18000a5a8  mov     qword ptr [rbx], 3Ch ; '<'
0x18000a5af  jmp     short loc_18000A625
0x18000a5b1  lea     rcx, [rdi+118h]
0x18000a5b8  mov     [rsp+48h+var_28], 0
0x18000a5c1  mov     r9d, 1
0x18000a5c7  lea     r8, aControlNetwork; "Control\\NetworkSetup2\\Parameters"
0x18000a5ce  lea     rdx, [rsp+48h+var_18]
0x18000a5d3  call    ?TryOpenSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAX@Z; RegistryKey::TryOpenSubKey(wchar_t const *,ulong,void *)
0x18000a5d8  nop
0x18000a5d9  cmp     [rsp+48h+var_18], 0
0x18000a5df  jz      short loc_18000A614
0x18000a5e1  lea     rdx, aNetsetupsvcidl; "NetSetupSvcIdleTimeout"
0x18000a5e8  lea     rcx, [rsp+48h+var_18]; this
0x18000a5ed  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18000a5f2  test    al, al
0x18000a5f4  jz      short loc_18000A614
0x18000a5f6  xor     r9d, r9d
0x18000a5f9  xor     r8d, r8d
0x18000a5fc  lea     rdx, aNetsetupsvcidl; "NetSetupSvcIdleTimeout"
0x18000a603  lea     rcx, [rsp+48h+var_18]
0x18000a608  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x18000a60d  mov     ecx, eax
0x18000a60f  mov     [rbx], rcx
0x18000a612  jmp     short loc_18000A61B
0x18000a614  mov     qword ptr [rbx], 3
0x18000a61b  lea     rcx, [rsp+48h+var_18]
0x18000a620  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18000a625  mov     rax, rbx
0x18000a628  mov     rcx, [rsp+48h+var_10]
0x18000a62d  xor     rcx, rsp; StackCookie
0x18000a630  call    __security_check_cookie
0x18000a635  mov     rbx, [rsp+48h+arg_10]
0x18000a63a  add     rsp, 40h
0x18000a63e  pop     rdi
0x18000a63f  retn
```
