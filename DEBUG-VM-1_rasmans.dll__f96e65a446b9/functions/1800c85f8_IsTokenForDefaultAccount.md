# IsTokenForDefaultAccount

- ea: `0x1800c85f8`
- end: `0x1800c87ca`
- name: `IsTokenForDefaultAccount`
- size: `466`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d67a8`
- `0x1800dad5c`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x1800b81fc`
- `0x1800c85f8`
- `0x1800e2d24`
- `0x1800e2dbc`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c8671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c86e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c8671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c86e5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800c8667`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800c8667`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800c86d7`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800c86d7`

## string_xrefs

- `0x1800c873a`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800c8797`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800c8731`: `IsTokenForDefaultAccount`
- `0x1800c878a`: `IsTokenForDefaultAccount`

## pseudocode

```c
__int64 __fastcall IsTokenForDefaultAccount(__int64 a1)
{
  DWORD LastError; // eax
  unsigned int v3; // ebx
  __int64 v4; // r8
  DWORD v5; // eax
  unsigned int v7; // [rsp+20h] [rbp-78h] BYREF
  DWORD cbSid[3]; // [rsp+24h] [rbp-74h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-68h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 394, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids);
  cbSid[0] = 68;
  v7 = 0;
  if ( !CreateWellKnownSid(WinAccountProtectedUsersSid|WinCreatorGroupSid, 0, pSid, cbSid) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( !LastError )
      goto LABEL_19;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 395, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, LastError);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      goto LABEL_19;
    v4 = 3927;
    goto LABEL_18;
  }
  if ( (unsigned int)CheckTokenMembershipEx(a1, pSid, 0, &v7) )
    return v7;
  v5 = GetLastError();
  v3 = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 396, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v5);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    {
      v4 = 3940;
LABEL_18:
      TraceVpnWppErrorW32Impl(
        v3,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        v4,
        "IsTokenForDefaultAccount");
    }
  }
LABEL_19:
  v7 = 0;
  if ( (v3 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 397, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v3);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        v3,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        3946,
        "IsTokenForDefaultAccount");
  }
  return v7;
}

```

## disassembly

```asm
0x1800c85f8  mov     [rsp+arg_8], rbx
0x1800c85fd  push    rdi
0x1800c85fe  sub     rsp, 90h
0x1800c8605  mov     rax, cs:__security_cookie
0x1800c860c  xor     rax, rsp
0x1800c860f  mov     [rsp+98h+var_18], rax
0x1800c8617  mov     rbx, rcx
0x1800c861a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8621  lea     rdi, WPP_GLOBAL_Control
0x1800c8628  cmp     rcx, rdi
0x1800c862b  jz      short loc_1800C8648
0x1800c862d  test    byte ptr [rcx+1Ch], 8
0x1800c8631  jz      short loc_1800C8648
0x1800c8633  mov     rcx, [rcx+10h]
0x1800c8637  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800c863e  mov     edx, 18Ah
0x1800c8643  call    WPP_SF_
0x1800c8648  xor     edx, edx; DomainSid
0x1800c864a  mov     [rsp+98h+cbSid], 44h ; 'D'
0x1800c8652  lea     r9, [rsp+98h+cbSid]; cbSid
0x1800c8657  mov     [rsp+98h+var_78], 0
0x1800c865f  lea     r8, [rsp+98h+pSid]; pSid
0x1800c8664  lea     ecx, [rdx+6Fh]; WellKnownSidType
0x1800c8667  call    cs:__imp_CreateWellKnownSid
0x1800c866d  test    eax, eax
0x1800c866f  jnz     short loc_1800C86C7
0x1800c8671  call    cs:__imp_GetLastError
0x1800c8677  mov     ebx, eax
0x1800c8679  test    eax, eax
0x1800c867b  jz      loc_1800C8746
0x1800c8681  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8688  cmp     rcx, rdi
0x1800c868b  jz      short loc_1800C86AB
0x1800c868d  test    byte ptr [rcx+1Ch], 1
0x1800c8691  jz      short loc_1800C86AB
0x1800c8693  mov     rcx, [rcx+10h]
0x1800c8697  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800c869e  mov     edx, 18Bh
0x1800c86a3  mov     r9d, eax
0x1800c86a6  call    WPP_SF_d
0x1800c86ab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800c86b2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800c86b7  test    al, al
0x1800c86b9  jz      loc_1800C8746
0x1800c86bf  mov     r8d, 0F57h
0x1800c86c5  jmp     short loc_1800C8731
0x1800c86c7  lea     r9, [rsp+98h+var_78]
0x1800c86cc  xor     r8d, r8d
0x1800c86cf  lea     rdx, [rsp+98h+pSid]
0x1800c86d4  mov     rcx, rbx
0x1800c86d7  call    cs:__imp_CheckTokenMembershipEx
0x1800c86dd  test    eax, eax
0x1800c86df  jnz     loc_1800C87A5
0x1800c86e5  call    cs:__imp_GetLastError
0x1800c86eb  mov     ebx, eax
0x1800c86ed  test    eax, eax
0x1800c86ef  jz      short loc_1800C8746
0x1800c86f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c86f8  cmp     rcx, rdi
0x1800c86fb  jz      short loc_1800C871B
0x1800c86fd  test    byte ptr [rcx+1Ch], 1
0x1800c8701  jz      short loc_1800C871B
0x1800c8703  mov     rcx, [rcx+10h]
0x1800c8707  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800c870e  mov     edx, 18Ch
0x1800c8713  mov     r9d, eax
0x1800c8716  call    WPP_SF_d
0x1800c871b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800c8722  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800c8727  test    al, al
0x1800c8729  jz      short loc_1800C8746
0x1800c872b  mov     r8d, 0F64h
0x1800c8731  lea     r9, aIstokenfordefa; "IsTokenForDefaultAccount"
0x1800c8738  mov     ecx, ebx
0x1800c873a  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800c8741  call    TraceVpnWppErrorW32Impl
0x1800c8746  xor     eax, eax
0x1800c8748  mov     [rsp+98h+var_78], eax
0x1800c874c  test    ebx, ebx
0x1800c874e  jns     short loc_1800C87A5
0x1800c8750  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8757  cmp     rcx, rdi
0x1800c875a  jz      short loc_1800C877A
0x1800c875c  test    byte ptr [rcx+1Ch], 8
0x1800c8760  jz      short loc_1800C877A
0x1800c8762  mov     rcx, [rcx+10h]
0x1800c8766  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800c876d  mov     edx, 18Dh
0x1800c8772  mov     r9d, ebx
0x1800c8775  call    WPP_SF_d
0x1800c877a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800c8781  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800c8786  test    al, al
0x1800c8788  jz      short loc_1800C87A5
0x1800c878a  lea     r9, aIstokenfordefa; "IsTokenForDefaultAccount"
0x1800c8791  mov     r8d, 0F6Ah
0x1800c8797  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800c879e  mov     ecx, ebx
0x1800c87a0  call    TraceVpnWppErrorHRImpl
0x1800c87a5  mov     eax, [rsp+98h+var_78]
0x1800c87a9  mov     rcx, [rsp+98h+var_18]
0x1800c87b1  xor     rcx, rsp; StackCookie
0x1800c87b4  call    __security_check_cookie
0x1800c87b9  mov     rbx, [rsp+98h+arg_8]
0x1800c87c1  add     rsp, 90h
0x1800c87c8  pop     rdi
0x1800c87c9  retn
```
