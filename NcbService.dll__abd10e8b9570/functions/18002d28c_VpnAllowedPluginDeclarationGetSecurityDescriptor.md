# VpnAllowedPluginDeclarationGetSecurityDescriptor

- ea: `0x18002d28c`
- end: `0x18002d3f3`
- name: `VpnAllowedPluginDeclarationGetSecurityDescriptor`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180025af0`

## callees

- `0x180003ed0`
- `0x18001c500`
- `0x18001d09c`
- `0x18002d28c`
- `0x1800316fc`
- `0x180031aec`
- `0x180031b7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d30b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d30b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d384`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d384`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002d301`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002d301`

## string_xrefs

- `0x18002d3d5`: `onecoreuap\net\netio\vpnplugin\protocolengine\vpn_proteng_common.c`
- `0x18002d34d`: `VpnAllowedPluginDeclarationGetSecurityDescriptor`
- `0x18002d3c8`: `VpnAllowedPluginDeclarationGetSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall VpnAllowedPluginDeclarationGetSecurityDescriptor(PSECURITY_DESCRIPTOR *a1, ULONG *a2)
{
  DWORD LastError; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  ULONG SecurityDescriptorSize; // [rsp+40h] [rbp+8h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 165, WPP_672b541566103487d192f0b957157036_Traceguids);
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  *a1 = 0;
  *a2 = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"O:SYG:SYD:(A;;RCWDCC;;;BA)(A;;RCWD;;;NO)(A;;RCWDCC;;;AU)(A;;RCWDCC;;;S-1-15-3-1024-2579400809-3867311217-398499"
          "4116-908665914-3508570097-1336497314-873935804-1444405236)(A;;RCWDCC;;;S-1-15-3-1024-1068037383-729401668-2768"
          "096886-125909118-1680096985-174794564-3112554050-3241210738)",
         1u,
         &SecurityDescriptor,
         &SecurityDescriptorSize) )
  {
    v5 = 0;
    *a1 = SecurityDescriptor;
    *a2 = SecurityDescriptorSize;
    SecurityDescriptor = 0;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 166, WPP_672b541566103487d192f0b957157036_Traceguids, LastError);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorW32Impl(v5, v6, 1323, "VpnAllowedPluginDeclarationGetSecurityDescriptor");
  }
  VpnFree(0);
  LocalFree(SecurityDescriptor);
  if ( (v5 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, WPP_672b541566103487d192f0b957157036_Traceguids, v5);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        v5,
        L"onecoreuap\\net\\netio\\vpnplugin\\protocolengine\\vpn_proteng_common.c",
        1332,
        "VpnAllowedPluginDeclarationGetSecurityDescriptor");
  }
  return v5;
}

```

## disassembly

```asm
0x18002d28c  mov     [rsp+arg_10], rbx
0x18002d291  push    rsi
0x18002d292  push    rdi
0x18002d293  push    r14
0x18002d295  sub     rsp, 20h
0x18002d299  mov     rdi, rdx
0x18002d29c  mov     rsi, rcx
0x18002d29f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d2a6  lea     r14, WPP_GLOBAL_Control
0x18002d2ad  cmp     rcx, r14
0x18002d2b0  jz      short loc_18002D2CD
0x18002d2b2  test    byte ptr [rcx+1Ch], 8
0x18002d2b6  jz      short loc_18002D2CD
0x18002d2b8  mov     rcx, [rcx+10h]
0x18002d2bc  lea     r8, WPP_672b541566103487d192f0b957157036_Traceguids
0x18002d2c3  mov     edx, 0A5h
0x18002d2c8  call    WPP_SF_
0x18002d2cd  lea     r9, [rsp+38h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18002d2d2  mov     [rsp+38h+SecurityDescriptor], 0
0x18002d2db  lea     r8, [rsp+38h+SecurityDescriptor]; SecurityDescriptor
0x18002d2e0  mov     [rsp+38h+SecurityDescriptorSize], 0
0x18002d2e8  mov     edx, 1; StringSDRevision
0x18002d2ed  mov     qword ptr [rsi], 0
0x18002d2f4  lea     rcx, aOSygSydARcwdcc; "O:SYG:SYD:(A;;RCWDCC;;;BA)(A;;RCWD;;;NO"...
0x18002d2fb  mov     dword ptr [rdi], 0
0x18002d301  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002d307  test    eax, eax
0x18002d309  jnz     short loc_18002D363
0x18002d30b  call    cs:__imp_GetLastError
0x18002d311  mov     ebx, eax
0x18002d313  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d31a  cmp     rcx, r14
0x18002d31d  jz      short loc_18002D33D
0x18002d31f  test    byte ptr [rcx+1Ch], 1
0x18002d323  jz      short loc_18002D33D
0x18002d325  mov     rcx, [rcx+10h]
0x18002d329  lea     r8, WPP_672b541566103487d192f0b957157036_Traceguids
0x18002d330  mov     edx, 0A6h
0x18002d335  mov     r9d, eax
0x18002d338  call    WPP_SF_d
0x18002d33d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x18002d344  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x18002d349  test    al, al
0x18002d34b  jz      short loc_18002D378
0x18002d34d  lea     r9, aVpnallowedplug_0; "VpnAllowedPluginDeclarationGetSecurityD"...
0x18002d354  mov     r8d, 52Bh
0x18002d35a  mov     ecx, ebx
0x18002d35c  call    TraceVpnWppErrorW32Impl
0x18002d361  jmp     short loc_18002D378
0x18002d363  mov     rax, [rsp+38h+SecurityDescriptor]
0x18002d368  xor     ebx, ebx
0x18002d36a  mov     [rsi], rax
0x18002d36d  mov     eax, [rsp+38h+SecurityDescriptorSize]
0x18002d371  mov     [rdi], eax
0x18002d373  mov     [rsp+38h+SecurityDescriptor], rbx
0x18002d378  xor     ecx, ecx; lpMem
0x18002d37a  call    VpnFree
0x18002d37f  mov     rcx, [rsp+38h+SecurityDescriptor]; hMem
0x18002d384  call    cs:__imp_LocalFree
0x18002d38a  test    ebx, ebx
0x18002d38c  jns     short loc_18002D3E3
0x18002d38e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d395  cmp     rcx, r14
0x18002d398  jz      short loc_18002D3B8
0x18002d39a  test    byte ptr [rcx+1Ch], 8
0x18002d39e  jz      short loc_18002D3B8
0x18002d3a0  mov     rcx, [rcx+10h]
0x18002d3a4  lea     r8, WPP_672b541566103487d192f0b957157036_Traceguids
0x18002d3ab  mov     edx, 0A7h
0x18002d3b0  mov     r9d, ebx
0x18002d3b3  call    WPP_SF_d
0x18002d3b8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x18002d3bf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x18002d3c4  test    al, al
0x18002d3c6  jz      short loc_18002D3E3
0x18002d3c8  lea     r9, aVpnallowedplug_0; "VpnAllowedPluginDeclarationGetSecurityD"...
0x18002d3cf  mov     r8d, 534h
0x18002d3d5  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prot"...
0x18002d3dc  mov     ecx, ebx
0x18002d3de  call    TraceVpnWppErrorHRImpl
0x18002d3e3  mov     eax, ebx
0x18002d3e5  mov     rbx, [rsp+38h+arg_10]
0x18002d3ea  add     rsp, 20h
0x18002d3ee  pop     r14
0x18002d3f0  pop     rdi
0x18002d3f1  pop     rsi
0x18002d3f2  retn
```
