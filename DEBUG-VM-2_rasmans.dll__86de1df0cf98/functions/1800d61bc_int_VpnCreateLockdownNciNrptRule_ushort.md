# int_VpnCreateLockdownNciNrptRule(ushort *)

- ea: `0x1800d61bc`
- end: `0x1800d67a0`
- name: `?int_VpnCreateLockdownNciNrptRule@@YAKPEAG@Z`
- size: `1508`
- prototype: `unsigned int __fastcall(unsigned __int16 *)`
- caller_count: `3`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800c945c`
- `0x1800d4f20`
- `0x1800de2d8`

## callees

- `0x180005e34`
- `0x180005e74`
- `0x18000e5f0`
- `0x1800a5770`
- `0x1800a68d8`
- `0x1800b81fc`
- `0x1800d6120`
- `0x1800d61bc`
- `0x1800e1b9c`
- `0x1800e1e64`
- `0x1800e2294`
- `0x1800e2464`
- `0x1800e2d24`
- `0x1800e2dbc`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `msvcrt!tolower` at `0x1800d6709`
- `msvcrt!tolower` at `0x1800d6709`
- `RPCRT4!UuidCreate` at `0x1800d640d`
- `RPCRT4!UuidCreate` at `0x1800d640d`

## string_xrefs

- `0x1800d62eb`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d639c`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d63f5`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d6474`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d6501`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d65dc`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d66a9`: `onecoreuap\net\netio\vpnplugin\profilemgmt\vpn_profile.cpp`
- `0x1800d624f`: `.msftconnecttest.com`
- `0x1800d62de`: `int_VpnCreateLockdownNciNrptRule`
- `0x1800d631e`: `int_VpnCreateLockdownNciNrptRule`
- `0x1800d638f`: `int_VpnCreateLockdownNciNrptRule`
- `0x1800d63e8`: `int_VpnCreateLockdownNciNrptRule`
- `0x1800d646b`: `int_VpnCreateLockdownNciNrptRule`
- `0x1800d64f4`: `int_VpnCreateLockdownNciNrptRule`
- `0x1800d6538`: `int_VpnCreateLockdownNciNrptRule`
- `0x1800d65cf`: `int_VpnCreateLockdownNciNrptRule`
- `0x1800d669c`: `int_VpnCreateLockdownNciNrptRule`
- `0x1800d66d9`: `int_VpnCreateLockdownNciNrptRule`
- `0x1800d66e3`: `VpnStringCopy wszNcsiServer`

## pseudocode

```c
__int64 __fastcall int_VpnCreateLockdownNciNrptRule(const char *a1)
{
  const char *v2; // r9
  unsigned int v3; // ebx
  void *v4; // r15
  int v5; // eax
  int v6; // edi
  int v7; // eax
  int v8; // ecx
  char *v9; // rdi
  unsigned int v10; // eax
  unsigned int v11; // r8d
  __int64 v12; // r8
  int v13; // esi
  int v14; // eax
  int v15; // ecx
  void *v16; // rcx
  __int64 v18; // rax
  _QWORD *v19; // r14
  int v20; // esi
  int v21; // r8d
  int v22; // eax
  _WORD *v24; // rcx
  __int64 v25; // rsi
  __int64 v26; // rbx
  __int16 v27; // ax
  unsigned int v28; // eax
  void *v29; // [rsp+30h] [rbp-99h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-91h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-89h] BYREF
  __int128 Src; // [rsp+50h] [rbp-79h] BYREF
  _OWORD v33[2]; // [rsp+60h] [rbp-69h]
  unsigned __int16 v34[40]; // [rsp+80h] [rbp-49h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
  {
    v2 = a1;
    if ( !a1 )
      v2 = L"<NULL>";
    WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 601, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v2);
  }
  lpMem = 0;
  v29 = 0;
  v3 = 0;
  v4 = 0;
  Uuid = 0;
  memset_0(v34, 0, 0x4Au);
  Src = *(_OWORD *)L".msftconnecttest.com";
  v33[0] = *(_OWORD *)L"necttest.com";
  *(_OWORD *)((char *)v33 + 10) = *(_OWORD *)L"est.com";
  v5 = VpnStringBuild(&lpMem, L"VPN_PERSISTENT_", a1);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 602, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, (unsigned int)v5);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        (unsigned int)v6,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        5933,
        "int_VpnCreateLockdownNciNrptRule");
    v7 = (v6 >> 16) & 0x1FFF;
    if ( v7 == 7 )
    {
      v8 = (unsigned __int16)v6;
      v7 = 7;
    }
    else
    {
      v8 = v6;
    }
    if ( v8 )
    {
      if ( v7 == 7 )
        v6 = (unsigned __int16)v6;
      VpnReportError("int_VpnCreateLockdownNciNrptRule", "VpnStringBuild", (unsigned int)v6);
      goto LABEL_52;
    }
  }
  v9 = (char *)VpnAlloc(64);
  if ( v9 )
  {
    v10 = UuidCreate(&Uuid);
    if ( !v10 || v10 == 1824 )
    {
      int_StringFromGUID(&Uuid, v34, v11);
      v13 = VpnStringBuild(&v29, lpMem, v34);
      if ( v13 < 0 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control[1].Flink,
            606,
            &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
            (unsigned int)v13);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorHRImpl(
            (unsigned int)v13,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            5959,
            "int_VpnCreateLockdownNciNrptRule");
        v14 = (v13 >> 16) & 0x1FFF;
        if ( v14 == 7 )
        {
          v15 = (unsigned __int16)v13;
          v14 = 7;
        }
        else
        {
          v15 = v13;
        }
        if ( v15 )
        {
          if ( v14 == 7 )
            v13 = (unsigned __int16)v13;
          VpnReportError(
            "int_VpnCreateLockdownNciNrptRule",
            "VpnStringBuild for pNrptRuleUniqueName",
            (unsigned int)v13);
          v4 = v29;
          goto LABEL_51;
        }
      }
      *((_QWORD *)v9 + 6) = v29;
      v18 = -1;
      *((_DWORD *)v9 + 7) = 1;
      *((_DWORD *)v9 + 6) = 0;
      *((_DWORD *)v9 + 3) = 0;
      *((_QWORD *)v9 + 4) = 0;
      do
        ++v18;
      while ( *((_WORD *)&v33[-1] + v18) );
      v19 = v9 + 40;
      *((_DWORD *)v9 + 4) = 2 * v18 + 2;
      v20 = VpnStringCopy(&Src);
      if ( v20 < 0 )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control[1].Flink,
            607,
            &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids,
            (unsigned int)v20);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
          TraceVpnWppErrorHRImpl(
            (unsigned int)v20,
            L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
            5975,
            "int_VpnCreateLockdownNciNrptRule");
        v22 = (v20 >> 16) & 0x1FFF;
        if ( v22 == 7 ? (unsigned __int16)v20 : v20 )
        {
          if ( v22 == 7 )
            v20 = (unsigned __int16)v20;
          VpnReportError("int_VpnCreateLockdownNciNrptRule", "VpnStringCopy wszNcsiServer", (unsigned int)v20);
          goto LABEL_51;
        }
      }
      v24 = (_WORD *)*v19;
      if ( *(_WORD *)*v19 )
      {
        LODWORD(v25) = 0;
        do
        {
          v26 = (unsigned int)v25;
          v27 = tolower((unsigned __int16)v24[(unsigned int)v25]);
          v25 = (unsigned int)(v25 + 1);
          *(_WORD *)(*v19 + 2 * v26) = v27;
          v24 = (_WORD *)*v19;
        }
        while ( *(_WORD *)(*v19 + 2 * v25) );
      }
      *((_DWORD *)v9 + 5) = 0;
      *((_QWORD *)v9 + 7) = 0;
      *(_QWORD *)v9 = 0;
      v28 = RasAddNrptRulesEx((_DWORD)v9, 1, v21, 0, 1, 0);
      v3 = v28;
      if ( !v28 )
        goto LABEL_51;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 608, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v28);
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        goto LABEL_51;
      v12 = 5994;
    }
    else
    {
      v3 = 87;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control[1].Flink, 605, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v10, 87);
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
        goto LABEL_51;
      v12 = 5951;
    }
    TraceVpnWppErrorW32Impl(
      v3,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      v12,
      "int_VpnCreateLockdownNciNrptRule");
LABEL_51:
    MprCommonFree(*((LPVOID *)v9 + 6));
    v16 = (void *)*((_QWORD *)v9 + 5);
    *((_QWORD *)v9 + 6) = 0;
    MprCommonFree(v16);
    *((_QWORD *)v9 + 5) = 0;
    MprCommonFree(v9);
    goto LABEL_52;
  }
  v3 = 14;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 603, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    TraceVpnWppErrorW32Impl(
      14,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      5941,
      "int_VpnCreateLockdownNciNrptRule");
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 604, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, 14);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
    TraceVpnWppErrorW32Impl(
      14,
      L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
      5943,
      "int_VpnCreateLockdownNciNrptRule");
LABEL_52:
  MprCommonFree(lpMem);
  MprCommonFree(v4);
  if ( (v3 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 609, &WPP_838860410ff333de2e2c3a260c8057b0_Traceguids, v3);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl'::`2'::impl) )
      TraceVpnWppErrorHRImpl(
        v3,
        L"onecoreuap\\net\\netio\\vpnplugin\\profilemgmt\\vpn_profile.cpp",
        6015,
        "int_VpnCreateLockdownNciNrptRule");
  }
  return v3;
}

```

## disassembly

```asm
0x1800d61bc  push    rbp
0x1800d61be  push    rbx
0x1800d61bf  push    rsi
0x1800d61c0  push    rdi
0x1800d61c1  push    r12
0x1800d61c3  push    r13
0x1800d61c5  push    r14
0x1800d61c7  push    r15
0x1800d61c9  lea     rbp, [rsp-1Fh]
0x1800d61ce  sub     rsp, 0E8h
0x1800d61d5  mov     rax, cs:__security_cookie
0x1800d61dc  xor     rax, rsp
0x1800d61df  mov     [rbp+57h+var_50], rax
0x1800d61e3  mov     rdi, rcx
0x1800d61e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d61ed  lea     rsi, WPP_GLOBAL_Control
0x1800d61f4  xor     r12d, r12d
0x1800d61f7  cmp     rcx, rsi
0x1800d61fa  jz      short loc_1800D6228
0x1800d61fc  test    byte ptr [rcx+1Ch], 8
0x1800d6200  jz      short loc_1800D6228
0x1800d6202  mov     rcx, [rcx+10h]
0x1800d6206  lea     rax, aNull_5; "<NULL>"
0x1800d620d  test    rdi, rdi
0x1800d6210  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d6217  mov     r9, rdi
0x1800d621a  mov     edx, 259h
0x1800d621f  cmovz   r9, rax
0x1800d6223  call    WPP_SF_S
0x1800d6228  xor     edx, edx; Val
0x1800d622a  mov     [rsp+120h+lpMem], r12
0x1800d622f  xorps   xmm0, xmm0
0x1800d6232  mov     [rsp+120h+var_F0], r12
0x1800d6237  lea     rcx, [rbp+57h+var_A0]; void *
0x1800d623b  mov     ebx, r12d
0x1800d623e  mov     r15, r12
0x1800d6241  lea     r8d, [rdx+4Ah]; Size
0x1800d6245  movups  xmmword ptr [rsp+120h+Uuid.Data1], xmm0
0x1800d624a  call    memset_0
0x1800d624f  movups  xmm0, xmmword ptr cs:aMsftconnecttes; ".msftconnecttest.com"
0x1800d6256  lea     r9, asc_1800FB984; "_"
0x1800d625d  mov     r8, rdi
0x1800d6260  movups  xmm1, xmmword ptr cs:aMsftconnecttes+10h; "necttest.com"
0x1800d6267  lea     rdx, aVpnPersistent; "VPN_PERSISTENT_"
0x1800d626e  mov     [rsp+120h+var_100], r12
0x1800d6273  movups  [rbp+57h+Src], xmm0
0x1800d6277  lea     rcx, [rsp+120h+lpMem]
0x1800d627c  movups  xmm0, xmmword ptr cs:aMsftconnecttes+1Ah; "est.com"
0x1800d6283  movups  xmmword ptr [rbp+57h+var_C0], xmm1
0x1800d6287  movups  xmmword ptr [rbp+57h+var_C0+0Ah], xmm0
0x1800d628b  call    VpnStringBuild
0x1800d6290  mov     r13d, 1
0x1800d6296  mov     edi, eax
0x1800d6298  lea     r14d, [r13+6]
0x1800d629c  test    eax, eax
0x1800d629e  jns     loc_1800D633C
0x1800d62a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d62ab  cmp     rcx, rsi
0x1800d62ae  jz      short loc_1800D62CE
0x1800d62b0  test    [rcx+1Ch], r13b
0x1800d62b4  jz      short loc_1800D62CE
0x1800d62b6  mov     rcx, [rcx+10h]
0x1800d62ba  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d62c1  mov     edx, 25Ah
0x1800d62c6  mov     r9d, eax
0x1800d62c9  call    WPP_SF_d
0x1800d62ce  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d62d5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d62da  test    al, al
0x1800d62dc  jz      short loc_1800D62F9
0x1800d62de  lea     r9, aIntVpncreatelo; "int_VpnCreateLockdownNciNrptRule"
0x1800d62e5  mov     r8d, 172Dh
0x1800d62eb  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d62f2  mov     ecx, edi
0x1800d62f4  call    TraceVpnWppErrorHRImpl
0x1800d62f9  mov     eax, edi
0x1800d62fb  sar     eax, 10h
0x1800d62fe  and     eax, 1FFFh
0x1800d6303  cmp     eax, r14d
0x1800d6306  jnz     short loc_1800D6312
0x1800d6308  movzx   ecx, di
0x1800d630b  mov     eax, r14d
0x1800d630e  mov     edx, ecx
0x1800d6310  jmp     short loc_1800D6317
0x1800d6312  mov     ecx, edi
0x1800d6314  movzx   edx, di
0x1800d6317  test    ecx, ecx
0x1800d6319  jz      short loc_1800D633C
0x1800d631b  cmp     eax, r14d
0x1800d631e  lea     rcx, aIntVpncreatelo; "int_VpnCreateLockdownNciNrptRule"
0x1800d6325  cmovz   edi, edx
0x1800d6328  lea     rdx, aVpnstringbuild_3; "VpnStringBuild"
0x1800d632f  mov     r8d, edi
0x1800d6332  call    VpnReportError
0x1800d6337  jmp     loc_1800D657F
0x1800d633c  mov     ecx, 40h ; '@'
0x1800d6341  call    VpnAlloc
0x1800d6346  mov     rdi, rax
0x1800d6349  test    rax, rax
0x1800d634c  jnz     loc_1800D6408
0x1800d6352  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6359  lea     ebx, [rax+0Eh]
0x1800d635c  cmp     rcx, rsi
0x1800d635f  jz      short loc_1800D637F
0x1800d6361  test    [rcx+1Ch], r13b
0x1800d6365  jz      short loc_1800D637F
0x1800d6367  mov     rcx, [rcx+10h]
0x1800d636b  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d6372  mov     edx, 25Bh
0x1800d6377  mov     r9d, ebx
0x1800d637a  call    WPP_SF_d
0x1800d637f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d6386  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d638b  test    al, al
0x1800d638d  jz      short loc_1800D63AA
0x1800d638f  lea     r9, aIntVpncreatelo; "int_VpnCreateLockdownNciNrptRule"
0x1800d6396  mov     r8d, 1735h
0x1800d639c  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d63a3  mov     ecx, ebx
0x1800d63a5  call    TraceVpnWppErrorW32Impl
0x1800d63aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d63b1  cmp     rcx, rsi
0x1800d63b4  jz      short loc_1800D63D4
0x1800d63b6  test    [rcx+1Ch], r13b
0x1800d63ba  jz      short loc_1800D63D4
0x1800d63bc  mov     rcx, [rcx+10h]
0x1800d63c0  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d63c7  mov     edx, 25Ch
0x1800d63cc  mov     r9d, ebx
0x1800d63cf  call    WPP_SF_d
0x1800d63d4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d63db  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d63e0  test    al, al
0x1800d63e2  jz      loc_1800D657F
0x1800d63e8  lea     r9, aIntVpncreatelo; "int_VpnCreateLockdownNciNrptRule"
0x1800d63ef  mov     r8d, 1737h
0x1800d63f5  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d63fc  mov     ecx, ebx
0x1800d63fe  call    TraceVpnWppErrorW32Impl
0x1800d6403  jmp     loc_1800D657F
0x1800d6408  lea     rcx, [rsp+120h+Uuid]; Uuid
0x1800d640d  call    cs:__imp_UuidCreate
0x1800d6413  test    eax, eax
0x1800d6415  jz      short loc_1800D6485
0x1800d6417  cmp     eax, 720h
0x1800d641c  jz      short loc_1800D6485
0x1800d641e  mov     ebx, 57h ; 'W'
0x1800d6423  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d642a  cmp     rcx, rsi
0x1800d642d  jz      short loc_1800D6451
0x1800d642f  test    [rcx+1Ch], r13b
0x1800d6433  jz      short loc_1800D6451
0x1800d6435  mov     rcx, [rcx+10h]
0x1800d6439  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d6440  mov     edx, 25Dh
0x1800d6445  mov     dword ptr [rsp+120h+var_100], ebx
0x1800d6449  mov     r9d, eax
0x1800d644c  call    WPP_SF_Dd
0x1800d6451  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d6458  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d645d  test    al, al
0x1800d645f  jz      loc_1800D655D
0x1800d6465  mov     r8d, 173Fh
0x1800d646b  lea     r9, aIntVpncreatelo; "int_VpnCreateLockdownNciNrptRule"
0x1800d6472  mov     ecx, ebx
0x1800d6474  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d647b  call    TraceVpnWppErrorW32Impl
0x1800d6480  jmp     loc_1800D655D
0x1800d6485  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x1800d6489  lea     rcx, [rsp+120h+Uuid]; struct _GUID *
0x1800d648e  call    ?int_StringFromGUID@@YAXAEAU_GUID@@PEAGK@Z; int_StringFromGUID(_GUID &,ushort *,ulong)
0x1800d6493  mov     rdx, [rsp+120h+lpMem]
0x1800d6498  lea     r8, [rbp+57h+var_A0]
0x1800d649c  xor     r9d, r9d
0x1800d649f  lea     rcx, [rsp+120h+var_F0]
0x1800d64a4  call    VpnStringBuild
0x1800d64a9  mov     esi, eax
0x1800d64ab  test    eax, eax
0x1800d64ad  jns     loc_1800D660C
0x1800d64b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d64ba  lea     rax, WPP_GLOBAL_Control
0x1800d64c1  cmp     rcx, rax
0x1800d64c4  jz      short loc_1800D64E4
0x1800d64c6  test    [rcx+1Ch], r13b
0x1800d64ca  jz      short loc_1800D64E4
0x1800d64cc  mov     rcx, [rcx+10h]
0x1800d64d0  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d64d7  mov     edx, 25Eh
0x1800d64dc  mov     r9d, esi
0x1800d64df  call    WPP_SF_d
0x1800d64e4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d64eb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d64f0  test    al, al
0x1800d64f2  jz      short loc_1800D650F
0x1800d64f4  lea     r9, aIntVpncreatelo; "int_VpnCreateLockdownNciNrptRule"
0x1800d64fb  mov     r8d, 1747h
0x1800d6501  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d6508  mov     ecx, esi
0x1800d650a  call    TraceVpnWppErrorHRImpl
0x1800d650f  mov     eax, esi
0x1800d6511  sar     eax, 10h
0x1800d6514  and     eax, 1FFFh
0x1800d6519  cmp     eax, r14d
0x1800d651c  jnz     short loc_1800D6528
0x1800d651e  movzx   ecx, si
0x1800d6521  mov     eax, r14d
0x1800d6524  mov     edx, ecx
0x1800d6526  jmp     short loc_1800D652D
0x1800d6528  mov     ecx, esi
0x1800d652a  movzx   edx, si
0x1800d652d  test    ecx, ecx
0x1800d652f  jz      loc_1800D660C
0x1800d6535  cmp     eax, r14d
0x1800d6538  lea     rcx, aIntVpncreatelo; "int_VpnCreateLockdownNciNrptRule"
0x1800d653f  cmovz   esi, edx
0x1800d6542  lea     rdx, aVpnstringbuild_2; "VpnStringBuild for pNrptRuleUniqueName"
0x1800d6549  mov     r8d, esi
0x1800d654c  call    VpnReportError
0x1800d6551  mov     r15, [rsp+120h+var_F0]
0x1800d6556  lea     rsi, WPP_GLOBAL_Control
0x1800d655d  mov     rcx, [rdi+30h]; lpMem
0x1800d6561  call    MprCommonFree
0x1800d6566  mov     rcx, [rdi+28h]; lpMem
0x1800d656a  mov     [rdi+30h], r12
0x1800d656e  call    MprCommonFree
0x1800d6573  mov     rcx, rdi; lpMem
0x1800d6576  mov     [rdi+28h], r12
0x1800d657a  call    MprCommonFree
0x1800d657f  mov     rcx, [rsp+120h+lpMem]; lpMem
0x1800d6584  call    MprCommonFree
0x1800d6589  mov     rcx, r15; lpMem
0x1800d658c  call    MprCommonFree
0x1800d6591  test    ebx, ebx
0x1800d6593  jns     short loc_1800D65EA
0x1800d6595  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d659c  cmp     rcx, rsi
0x1800d659f  jz      short loc_1800D65BF
0x1800d65a1  test    byte ptr [rcx+1Ch], 8
0x1800d65a5  jz      short loc_1800D65BF
0x1800d65a7  mov     rcx, [rcx+10h]
0x1800d65ab  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d65b2  mov     edx, 261h
0x1800d65b7  mov     r9d, ebx
0x1800d65ba  call    WPP_SF_d
0x1800d65bf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d65c6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
0x1800d65cb  test    al, al
0x1800d65cd  jz      short loc_1800D65EA
0x1800d65cf  lea     r9, aIntVpncreatelo; "int_VpnCreateLockdownNciNrptRule"
0x1800d65d6  mov     r8d, 177Fh
0x1800d65dc  lea     rdx, aOnecoreuapNetN_1; "onecoreuap\\net\\netio\\vpnplugin\\prof"...
0x1800d65e3  mov     ecx, ebx
0x1800d65e5  call    TraceVpnWppErrorHRImpl
0x1800d65ea  mov     eax, ebx
0x1800d65ec  mov     rcx, [rbp+57h+var_50]
0x1800d65f0  xor     rcx, rsp; StackCookie
0x1800d65f3  call    __security_check_cookie
0x1800d65f8  add     rsp, 0E8h
0x1800d65ff  pop     r15
0x1800d6601  pop     r14
0x1800d6603  pop     r13
0x1800d6605  pop     r12
0x1800d6607  pop     rdi
0x1800d6608  pop     rsi
0x1800d6609  pop     rbx
0x1800d660a  pop     rbp
0x1800d660b  retn
0x1800d660c  mov     rax, [rsp+120h+var_F0]
0x1800d6611  lea     rcx, [rbp+57h+Src]
0x1800d6615  mov     [rdi+30h], rax
0x1800d6619  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800d661d  mov     [rdi+1Ch], r13d
0x1800d6621  mov     [rdi+18h], r12d
0x1800d6625  mov     [rdi+0Ch], r12d
0x1800d6629  mov     [rdi+20h], r12
0x1800d662d  inc     rax
0x1800d6630  cmp     [rcx+rax*2], r12w
0x1800d6635  jnz     short loc_1800D662D
0x1800d6637  lea     eax, ds:2[rax*2]
0x1800d663e  lea     r14, [rdi+28h]
0x1800d6642  mov     [rdi+10h], eax
0x1800d6645  mov     rdx, r14
0x1800d6648  lea     rcx, [rbp+57h+Src]; Src
0x1800d664c  call    VpnStringCopy
0x1800d6651  mov     esi, eax
0x1800d6653  test    eax, eax
0x1800d6655  jns     loc_1800D66F7
0x1800d665b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6662  lea     rax, WPP_GLOBAL_Control
0x1800d6669  cmp     rcx, rax
0x1800d666c  jz      short loc_1800D668C
0x1800d666e  test    [rcx+1Ch], r13b
0x1800d6672  jz      short loc_1800D668C
0x1800d6674  mov     rcx, [rcx+10h]
0x1800d6678  lea     r8, WPP_838860410ff333de2e2c3a260c8057b0_Traceguids
0x1800d667f  mov     edx, 25Fh
0x1800d6684  mov     r9d, esi
0x1800d6687  call    WPP_SF_d
0x1800d668c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04> `wil::Feature<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::GetImpl(void)'::`2'::impl
0x1800d6693  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_VPN_Tracelog_26_04@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_VPN_Tracelog_26_04>::__private_IsEnabled(void)
  ... truncated ...
```
