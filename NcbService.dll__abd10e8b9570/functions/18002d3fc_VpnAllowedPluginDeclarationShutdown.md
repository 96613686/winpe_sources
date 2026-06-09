# VpnAllowedPluginDeclarationShutdown

- ea: `0x18002d3fc`
- end: `0x18002d50a`
- name: `VpnAllowedPluginDeclarationShutdown`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180025af0`

## callees

- `0x180003ed0`
- `0x18001c500`
- `0x18001d09c`
- `0x18002d3fc`
- `0x1800316fc`
- `0x180031b7c`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18002d4ac`
- `ntdll!RtlFreeSid` at `0x18002d4bc`
- `ntdll!RtlFreeSid` at `0x18002d4ac`
- `ntdll!RtlFreeSid` at `0x18002d4bc`

## string_xrefs

- `0x18002d477`: `VpnAllowedPluginDeclarationShutdown`

## pseudocode

```c
PVOID VpnAllowedPluginDeclarationShutdown()
{
  PVOID *v0; // rcx
  PVOID result; // rax
  __int64 v2; // rdx
  __int64 v3; // rdi
  __int64 v4; // rbx
  wchar_t *v5; // rcx
  wchar_t *v6; // rcx

  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 174, WPP_672b541566103487d192f0b957157036_Traceguids);
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( g_bAllowedPluginDeclInit )
  {
    v3 = 0;
    v4 = 0;
    do
    {
      result = (PVOID)VpnFree(allowedPluginDecl[v4 + 8]);
      v5 = allowedPluginDecl[v4 + 3];
      if ( v5 )
        result = RtlFreeSid(v5);
      v6 = allowedPluginDecl[v4 + 5];
      if ( v6 )
        result = RtlFreeSid(v6);
      ++v3;
      v4 += 10;
    }
    while ( v3 != 4 );
    g_bAllowedPluginDeclInit = 0;
  }
  else
  {
    if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 1) != 0 )
      WPP_SF_d(v0[2], 175, WPP_672b541566103487d192f0b957157036_Traceguids, 0);
    result = (PVOID)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl);
    if ( (_BYTE)result )
      result = (PVOID)TraceVpnWppErrorW32Impl(0, v2, 1376, "VpnAllowedPluginDeclarationShutdown");
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    return (PVOID)WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 176, WPP_672b541566103487d192f0b957157036_Traceguids);
  return result;
}

```

## disassembly

```asm
0x18002d3fc  push    rbx
0x18002d3fe  push    rsi
0x18002d3ff  push    rdi
0x18002d400  push    r14
0x18002d402  sub     rsp, 28h
0x18002d406  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d40d  lea     rsi, WPP_GLOBAL_Control
0x18002d414  cmp     rcx, rsi
0x18002d417  jz      short loc_18002D43B
0x18002d419  test    byte ptr [rcx+1Ch], 8
0x18002d41d  jz      short loc_18002D43B
0x18002d41f  mov     rcx, [rcx+10h]
0x18002d423  lea     r8, WPP_672b541566103487d192f0b957157036_Traceguids
0x18002d42a  mov     edx, 0AEh
0x18002d42f  call    WPP_SF_
0x18002d434  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d43b  cmp     cs:g_bAllowedPluginDeclInit, 0
0x18002d442  jnz     short loc_18002D48D
0x18002d444  cmp     rcx, rsi
0x18002d447  jz      short loc_18002D467
0x18002d449  test    byte ptr [rcx+1Ch], 1
0x18002d44d  jz      short loc_18002D467
0x18002d44f  mov     rcx, [rcx+10h]
0x18002d453  lea     r8, WPP_672b541566103487d192f0b957157036_Traceguids
0x18002d45a  mov     edx, 0AFh
0x18002d45f  xor     r9d, r9d
0x18002d462  call    WPP_SF_d
0x18002d467  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x18002d46e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x18002d473  test    al, al
0x18002d475  jz      short loc_18002D4D9
0x18002d477  lea     r9, aVpnallowedplug; "VpnAllowedPluginDeclarationShutdown"
0x18002d47e  xor     ecx, ecx
0x18002d480  mov     r8d, 560h
0x18002d486  call    TraceVpnWppErrorW32Impl
0x18002d48b  jmp     short loc_18002D4D9
0x18002d48d  xor     edi, edi
0x18002d48f  lea     r14, allowedPluginDecl
0x18002d496  xor     ebx, ebx
0x18002d498  mov     rcx, [rbx+r14+40h]; lpMem
0x18002d49d  call    VpnFree
0x18002d4a2  mov     rcx, [rbx+r14+18h]; Sid
0x18002d4a7  test    rcx, rcx
0x18002d4aa  jz      short loc_18002D4B2
0x18002d4ac  call    cs:__imp_RtlFreeSid
0x18002d4b2  mov     rcx, [rbx+r14+28h]; Sid
0x18002d4b7  test    rcx, rcx
0x18002d4ba  jz      short loc_18002D4C2
0x18002d4bc  call    cs:__imp_RtlFreeSid
0x18002d4c2  inc     rdi
0x18002d4c5  add     rbx, 50h ; 'P'
0x18002d4c9  cmp     rdi, 4
0x18002d4cd  jnz     short loc_18002D498
0x18002d4cf  mov     cs:g_bAllowedPluginDeclInit, 0
0x18002d4d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d4e0  cmp     rcx, rsi
0x18002d4e3  jz      short loc_18002D500
0x18002d4e5  test    byte ptr [rcx+1Ch], 8
0x18002d4e9  jz      short loc_18002D500
0x18002d4eb  mov     rcx, [rcx+10h]
0x18002d4ef  lea     r8, WPP_672b541566103487d192f0b957157036_Traceguids
0x18002d4f6  mov     edx, 0B0h
0x18002d4fb  call    WPP_SF_
0x18002d500  add     rsp, 28h
0x18002d504  pop     r14
0x18002d506  pop     rdi
0x18002d507  pop     rsi
0x18002d508  pop     rbx
0x18002d509  retn
```
