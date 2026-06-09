# OSIntegration::DEH::Internal::FirewallRulesHelper::RemoveChanges(void)

- ea: `0x18005a1f0`
- end: `0x18005a4e6`
- name: `?RemoveChanges@FirewallRulesHelper@Internal@DEH@OSIntegration@@UEAAJXZ`
- size: `758`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::FirewallRulesHelper *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180012fc8`
- `0x18001adb4`
- `0x1800225fc`
- `0x180050e60`
- `0x18005a1f0`
- `0x180069eb4`
- `0x1800e4f68`
- `0x1800e4fa4`
- `0x1800e5234`
- `0x180182714`
- `0x180182d54`
- `0x1801833c0`
- `0x1801835e4`

## import_xrefs

- `FirewallAPI!FWQueryFirewallRules` at `0x18005a469`
- `FirewallAPI!FWQueryFirewallRules` at `0x18005a469`
- `FirewallAPI!FWDeleteFirewallRule` at `0x18005a48a`
- `FirewallAPI!FWDeleteFirewallRule` at `0x18005a48a`
- `FirewallAPI!FWFreeFirewallRulesByHandle` at `0x18005a4a9`
- `FirewallAPI!FWFreeFirewallRulesByHandle` at `0x18005a4a9`
- `FirewallAPI!FWClosePolicyStore` at `0x18005a4b9`
- `FirewallAPI!FWClosePolicyStore` at `0x18005a4b9`
- `FirewallAPI!FWOpenPolicyStore` at `0x18005a2da`
- `FirewallAPI!FWOpenPolicyStore` at `0x18005a3cc`
- `FirewallAPI!FWOpenPolicyStore` at `0x18005a2da`
- `FirewallAPI!FWOpenPolicyStore` at `0x18005a3cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OSIntegration::DEH::Internal::FirewallRulesHelper::RemoveChanges(
        OSIntegration::DEH::Internal::FirewallRulesHelper *this)
{
  int v2; // edi
  __int64 v3; // rdx
  unsigned __int16 v5; // di
  __int64 v6; // r9
  Common::Deployment::Configuration *v7; // rcx
  int v8; // esi
  const unsigned __int16 *v9; // r8
  unsigned int v10; // eax
  unsigned __int16 *v11; // r8
  __int64 v12; // rdx
  unsigned int v13; // ebx
  int v14; // eax
  int v15; // eax
  int v16; // ecx
  int v17; // edi
  _QWORD *v18; // rbx
  int v19; // [rsp+20h] [rbp-49h]
  void *v20[2]; // [rsp+30h] [rbp-39h] BYREF
  _QWORD v21[2]; // [rsp+40h] [rbp-29h] BYREF
  _DWORD v22[2]; // [rsp+50h] [rbp-19h] BYREF
  _QWORD *v23; // [rsp+58h] [rbp-11h]
  __int64 v24; // [rsp+60h] [rbp-9h]
  _QWORD v25[3]; // [rsp+68h] [rbp-1h] BYREF
  int v26; // [rsp+80h] [rbp+17h]
  int v27; // [rsp+84h] [rbp+1Bh]
  __int64 v28; // [rsp+88h] [rbp+1Fh]
  const wchar_t *v29; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  int v31; // [rsp+D8h] [rbp+6Fh] BYREF
  Common::Deployment::FirewallRulesRegistration *v32; // [rsp+E0h] [rbp+77h]
  _QWORD *v33; // [rsp+E8h] [rbp+7Fh]

  v20[0] = 0;
  v20[1] = 0;
  v2 = Common::ImpersonationContext::Impersonate(v20, 0);
  if ( v2 < 0 )
  {
    v3 = 405;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewallrules\\firewallruleshelper.cpp",
      (const char *)(unsigned int)v2,
      v19);
    if ( LODWORD(v20[0]) )
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v20);
    return (unsigned int)v2;
  }
  v32 = 0;
  v5 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FirewallDEH_ServiceHardening>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FirewallDEH_ServiceHardening>::GetImpl'::`2'::impl) != 0
     ? 545
     : 532;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FirewallEarlyBoot>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FirewallEarlyBoot>::GetImpl'::`2'::impl) )
  {
    v2 = Common::Deployment::FirewallRulesRegistration::ClearDeferredFirewallRulesDehDataForPackage(
           *(Common::Deployment::FirewallRulesRegistration **)(*((_QWORD *)this + 3) + 48LL),
           *(struct PackageRepository::IRepositorySession **)(*((_QWORD *)this + 3) + 224LL),
           *(const unsigned __int16 **)(*((_QWORD *)this + 3) + 64LL),
           v6);
    if ( v2 < 0 )
    {
      v3 = 421;
      goto LABEL_3;
    }
    v8 = Common::Deployment::Configuration::CheckFirewallServiceRunning(v7);
    if ( v8 < 0 )
    {
      v15 = Common::Deployment::FirewallRulesRegistration::DeferDeleteFirewallRules(
              *(LPCWSTR *)(*((_QWORD *)this + 3) + 224LL),
              *((_WORD **)this + 9),
              v9);
      v17 = v15;
      if ( (byte_180245602 & 1) != 0 )
        McTemplateU0dzd_EventWriteTransfer(
          v16,
          (unsigned int)FirewallRulesDeferringDelete,
          v8,
          *(_QWORD *)(*((_QWORD *)this + 3) + 224LL),
          v15);
      if ( v17 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1BA,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewallrules\\firewallruleshelper.cpp",
          (const char *)(unsigned int)v17,
          v19);
      goto LABEL_29;
    }
    v10 = FWOpenPolicyStore(545, 0, 2, 2);
    if ( v10 )
    {
      v12 = 432;
LABEL_12:
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v12,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewallrules\\firewallruleshelper.cpp",
              (const char *)v10,
              0);
      if ( LODWORD(v20[0]) )
        Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v20);
      return v13;
    }
    v14 = Common::Deployment::FirewallRulesRegistration::DeleteFirewallRulesByApplication(
            v32,
            *((void **)this + 9),
            v11);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1B2,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\firewallrules\\firewallruleshelper.cpp",
        (const char *)(unsigned int)v14,
        0);
  }
  else
  {
    v10 = FWOpenPolicyStore(v5, 0, 2, 2);
    if ( v10 )
    {
      v12 = 453;
      goto LABEL_12;
    }
    v25[1] = 5;
    v28 = 5;
    v21[0] = 2;
    v22[0] = 545;
    v24 = 0x10000;
    v33 = 0;
    v31 = 0;
    v25[0] = 4;
    v25[2] = *((_QWORD *)this + 9);
    v27 = 1;
    v26 = 8;
    v29 = L"{78E1CD88-49E3-476E-B926-580E596AD309}";
    v21[1] = v25;
    v22[1] = 1;
    v23 = v21;
    if ( !(unsigned int)FWQueryFirewallRules(v32, v22, 0, &v31) )
    {
      v18 = v33;
      if ( v33 )
      {
        do
        {
          FWDeleteFirewallRule(v32, v18[2]);
          v18 = (_QWORD *)*v18;
        }
        while ( v18 );
        v18 = v33;
      }
      FWFreeFirewallRulesByHandle(v32, v18);
    }
  }
  FWClosePolicyStore(v32);
LABEL_29:
  if ( LODWORD(v20[0]) )
    Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v20);
  return 0;
}

```

## disassembly

```asm
0x18005a1f0  push    rbp
0x18005a1f2  push    rbx
0x18005a1f3  push    rsi
0x18005a1f4  push    rdi
0x18005a1f5  push    r14
0x18005a1f7  lea     rbp, [rsp-37h]
0x18005a1fc  sub     rsp, 0A0h
0x18005a203  mov     rbx, rcx
0x18005a206  xor     r14d, r14d
0x18005a209  mov     [rbp+57h+var_90], r14
0x18005a20d  mov     [rbp+57h+var_88], r14
0x18005a211  xor     edx, edx; void *
0x18005a213  lea     rcx, [rbp+57h+var_90]; this
0x18005a217  call    ?Impersonate@ImpersonationContext@Common@@QEAAJPEAX@Z; Common::ImpersonationContext::Impersonate(void *)
0x18005a21c  mov     edi, eax
0x18005a21e  test    eax, eax
0x18005a220  jns     short loc_18005A251
0x18005a222  mov     edx, 195h; void *
0x18005a227  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18005a22e  mov     r9d, edi; char *
0x18005a231  mov     rcx, [rbp+5Fh]; this
0x18005a235  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a23a  nop
0x18005a23b  cmp     dword ptr [rbp+57h+var_90], r14d
0x18005a23f  jz      short loc_18005A24A
0x18005a241  lea     rcx, [rbp+57h+var_90]; this
0x18005a245  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18005a24a  mov     eax, edi
0x18005a24c  jmp     loc_18005A4D7
0x18005a251  mov     [rbp+57h+arg_10], r14
0x18005a255  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FirewallDEH_ServiceHardening@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FirewallDEH_ServiceHardening@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FirewallDEH_ServiceHardening> `wil::Feature<__WilFeatureTraits_Feature_FirewallDEH_ServiceHardening>::GetImpl(void)'::`2'::impl
0x18005a25c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FirewallDEH_ServiceHardening@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FirewallDEH_ServiceHardening>::__private_IsEnabled(void)
0x18005a261  neg     al
0x18005a263  sbb     di, di
0x18005a266  and     di, 0Dh
0x18005a26a  add     di, 214h
0x18005a26f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FirewallEarlyBoot@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FirewallEarlyBoot@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FirewallEarlyBoot> `wil::Feature<__WilFeatureTraits_Feature_FirewallEarlyBoot>::GetImpl(void)'::`2'::impl
0x18005a276  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FirewallEarlyBoot@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FirewallEarlyBoot>::__private_IsEnabled(void)
0x18005a27b  test    al, al
0x18005a27d  jz      loc_18005A3AE
0x18005a283  mov     rcx, [rbx+18h]
0x18005a287  mov     r8, [rcx+40h]; unsigned __int16 *
0x18005a28b  mov     rdx, [rcx+0E0h]; struct PackageRepository::IRepositorySession *
0x18005a292  mov     rcx, [rcx+30h]; this
0x18005a296  call    ?ClearDeferredFirewallRulesDehDataForPackage@FirewallRulesRegistration@Deployment@Common@@YAJPEAVIRepositorySession@PackageRepository@@PEBG_J@Z; Common::Deployment::FirewallRulesRegistration::ClearDeferredFirewallRulesDehDataForPackage(PackageRepository::IRepositorySession *,ushort const *,__int64)
0x18005a29b  mov     edi, eax
0x18005a29d  test    eax, eax
0x18005a29f  jns     short loc_18005A2AB
0x18005a2a1  mov     edx, 1A5h
0x18005a2a6  jmp     loc_18005A227
0x18005a2ab  call    ?CheckFirewallServiceRunning@Configuration@Deployment@Common@@YAJXZ; Common::Deployment::Configuration::CheckFirewallServiceRunning(void)
0x18005a2b0  mov     esi, eax
0x18005a2b2  test    eax, eax
0x18005a2b4  js      loc_18005A34C
0x18005a2ba  mov     ecx, 221h
0x18005a2bf  lea     rax, [rbp+57h+arg_10]
0x18005a2c3  mov     [rsp+0C0h+var_98], rax
0x18005a2c8  mov     [rsp+0C0h+var_A0], r14d; int
0x18005a2cd  mov     esi, 2
0x18005a2d2  mov     r9d, esi
0x18005a2d5  mov     r8d, esi
0x18005a2d8  xor     edx, edx
0x18005a2da  call    cs:__imp_FWOpenPolicyStore
0x18005a2e1  nop     dword ptr [rax+rax+00h]
0x18005a2e6  test    eax, eax
0x18005a2e8  jz      short loc_18005A31A
0x18005a2ea  mov     edx, 1B0h; void *
0x18005a2ef  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18005a2f6  mov     r9d, eax; char *
0x18005a2f9  mov     rcx, [rbp+5Fh]; this
0x18005a2fd  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005a302  mov     ebx, eax
0x18005a304  cmp     dword ptr [rbp+57h+var_90], r14d
0x18005a308  jz      short loc_18005A313
0x18005a30a  lea     rcx, [rbp+57h+var_90]; this
0x18005a30e  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18005a313  mov     eax, ebx
0x18005a315  jmp     loc_18005A4D7
0x18005a31a  mov     rdx, [rbx+48h]; void *
0x18005a31e  mov     rcx, [rbp+57h+arg_10]; this
0x18005a322  call    ?DeleteFirewallRulesByApplication@FirewallRulesRegistration@Deployment@Common@@YAJPEAXPEAG@Z; Common::Deployment::FirewallRulesRegistration::DeleteFirewallRulesByApplication(void *,ushort *)
0x18005a327  mov     rcx, [rbp+5Fh]; this
0x18005a32b  test    eax, eax
0x18005a32d  jns     loc_18005A4B5
0x18005a333  mov     r9d, eax; char *
0x18005a336  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18005a33d  mov     edx, 1B2h; void *
0x18005a342  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005a347  jmp     loc_18005A4B5
0x18005a34c  mov     rcx, [rbx+18h]
0x18005a350  mov     rdx, [rbx+48h]; lpData
0x18005a354  mov     rcx, [rcx+0E0h]; lpSubKey
0x18005a35b  call    ?DeferDeleteFirewallRules@FirewallRulesRegistration@Deployment@Common@@YAJPEBG0@Z; Common::Deployment::FirewallRulesRegistration::DeferDeleteFirewallRules(ushort const *,ushort const *)
0x18005a360  mov     edi, eax
0x18005a362  test    cs:byte_180245602, 1
0x18005a369  jz      short loc_18005A389
0x18005a36b  mov     r9, [rbx+18h]
0x18005a36f  mov     [rsp+0C0h+var_A0], eax; int
0x18005a373  mov     r9, [r9+0E0h]
0x18005a37a  mov     r8d, esi
0x18005a37d  lea     rdx, FirewallRulesDeferringDelete
0x18005a384  call    McTemplateU0dzd_EventWriteTransfer
0x18005a389  mov     rcx, [rbp+5Fh]; this
0x18005a38d  test    edi, edi
0x18005a38f  jns     loc_18005A4C6
0x18005a395  mov     r9d, edi; char *
0x18005a398  lea     r8, aOnecoreAdminAp_147; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18005a39f  mov     edx, 1BAh; void *
0x18005a3a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005a3a9  jmp     loc_18005A4C6
0x18005a3ae  lea     rax, [rbp+57h+arg_10]
0x18005a3b2  mov     [rsp+0C0h+var_98], rax
0x18005a3b7  mov     [rsp+0C0h+var_A0], r14d
0x18005a3bc  mov     esi, 2
0x18005a3c1  mov     r9d, esi
0x18005a3c4  mov     r8d, esi
0x18005a3c7  xor     edx, edx
0x18005a3c9  movzx   ecx, di
0x18005a3cc  call    cs:__imp_FWOpenPolicyStore
0x18005a3d3  nop     dword ptr [rax+rax+00h]
0x18005a3d8  test    eax, eax
0x18005a3da  jz      short loc_18005A3E6
0x18005a3dc  mov     edx, 1C5h
0x18005a3e1  jmp     loc_18005A2EF
0x18005a3e6  mov     [rbp+57h+var_50], 5
0x18005a3ee  mov     [rbp+57h+var_38], 5
0x18005a3f6  mov     [rbp+57h+var_80], rsi
0x18005a3fa  mov     [rbp+57h+var_70], 221h
0x18005a401  mov     [rbp+57h+var_60], 10000h
0x18005a409  mov     [rbp+57h+arg_18], r14
0x18005a40d  mov     [rbp+57h+arg_8], r14d
0x18005a411  mov     [rbp+57h+var_58], 4
0x18005a419  mov     rax, [rbx+48h]
0x18005a41d  mov     [rbp+57h+var_48], rax
0x18005a421  mov     [rbp+57h+var_3C], 1
0x18005a428  mov     [rbp+57h+var_40], 8
0x18005a42f  lea     rax, a78e1cd8849e347; "{78E1CD88-49E3-476E-B926-580E596AD309}"
0x18005a436  mov     [rbp+57h+var_30], rax
0x18005a43a  lea     rax, [rbp+57h+var_58]
0x18005a43e  mov     [rbp+57h+var_78], rax
0x18005a442  mov     [rbp+57h+var_6C], 1
0x18005a449  lea     rax, [rbp+57h+var_80]
0x18005a44d  mov     [rbp+57h+var_68], rax
0x18005a451  xor     r8d, r8d
0x18005a454  lea     rax, [rbp+57h+arg_18]
0x18005a458  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18005a45d  lea     r9, [rbp+57h+arg_8]
0x18005a461  lea     rdx, [rbp+57h+var_70]
0x18005a465  mov     rcx, [rbp+57h+arg_10]
0x18005a469  call    cs:__imp_FWQueryFirewallRules
0x18005a470  nop     dword ptr [rax+rax+00h]
0x18005a475  test    eax, eax
0x18005a477  jnz     short loc_18005A4B5
0x18005a479  mov     rbx, [rbp+57h+arg_18]
0x18005a47d  test    rbx, rbx
0x18005a480  jz      short loc_18005A4A2
0x18005a482  mov     rdx, [rbx+10h]
0x18005a486  mov     rcx, [rbp+57h+arg_10]
0x18005a48a  call    cs:__imp_FWDeleteFirewallRule
0x18005a491  nop     dword ptr [rax+rax+00h]
0x18005a496  mov     rbx, [rbx]
0x18005a499  test    rbx, rbx
0x18005a49c  jnz     short loc_18005A482
0x18005a49e  mov     rbx, [rbp+57h+arg_18]
0x18005a4a2  mov     rdx, rbx
0x18005a4a5  mov     rcx, [rbp+57h+arg_10]
0x18005a4a9  call    cs:__imp_FWFreeFirewallRulesByHandle
0x18005a4b0  nop     dword ptr [rax+rax+00h]
0x18005a4b5  mov     rcx, [rbp+57h+arg_10]
0x18005a4b9  call    cs:__imp_FWClosePolicyStore
0x18005a4c0  nop     dword ptr [rax+rax+00h]
0x18005a4c5  nop
0x18005a4c6  cmp     dword ptr [rbp+57h+var_90], r14d
0x18005a4ca  jz      short loc_18005A4D5
0x18005a4cc  lea     rcx, [rbp+57h+var_90]; this
0x18005a4d0  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18005a4d5  xor     eax, eax
0x18005a4d7  add     rsp, 0A0h
0x18005a4de  pop     r14
0x18005a4e0  pop     rdi
0x18005a4e1  pop     rsi
0x18005a4e2  pop     rbx
0x18005a4e3  pop     rbp
0x18005a4e4  retn
```
