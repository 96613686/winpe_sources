# IsPortOrICMPAllowed

- ea: `0x1800191e0`
- end: `0x180019b2e`
- name: `IsPortOrICMPAllowed`
- size: `2382`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180039a30`
- `0x180039af0`
- `0x180039e50`

## callees

- `0x180005e0c`
- `0x1800090d0`
- `0x180009210`
- `0x180009780`
- `0x18000a3e0`
- `0x18000cc80`
- `0x18000d0f0`
- `0x18000ed70`
- `0x1800191e0`
- `0x180019b34`
- `0x180019b6c`
- `0x180025570`
- `0x1800294b0`
- `0x18003336c`
- `0x18003994c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001949f`
- `ntdll!EtwEventWrite` at `0x18001952f`
- `ntdll!EtwEventWrite` at `0x18001949f`
- `ntdll!EtwEventWrite` at `0x18001952f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800194c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800194c8`
- `fwbase!FwBaseFree` at `0x18001934a`
- `fwbase!FwBaseFree` at `0x18001934a`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18001944a`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18001946c`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019598`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800195f3`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800197aa`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800197c1`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800197d8`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800197ea`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019838`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019870`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800198a3`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019908`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019925`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800199b4`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019a5c`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019a6e`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019a86`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019aab`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019ac9`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18001944a`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18001946c`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019598`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800195f3`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800197aa`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800197c1`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800197d8`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800197ea`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019838`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019870`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800198a3`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019908`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019925`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800199b4`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019a5c`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019a6e`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019a86`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019aab`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019ac9`
- `fwbase!FwReportErrorAsWinError` at `0x180019550`
- `fwbase!FwReportErrorAsWinError` at `0x180019550`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x1800192fd`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x1800192fd`
- `fwbase!FwReportReturnError` at `0x18001931e`
- `fwbase!FwReportReturnError` at `0x180019b1b`
- `fwbase!FwReportReturnError` at `0x18001931e`
- `fwbase!FwReportReturnError` at `0x180019b1b`

## string_xrefs

- `0x1800199a0`: `FWOpenPolicyStore`
- `0x18001985d`: `FWGetGlobalConfig`
- `0x180019542`: `FWGetConfig`

## pseudocode

```c
__int64 __fastcall IsPortOrICMPAllowed(
        __int64 a1,
        enum NET_FW_IP_VERSION_ a2,
        int a3,
        unsigned __int16 *a4,
        enum NET_FW_IP_PROTOCOL_ a5,
        unsigned __int16 a6,
        _DWORD *a7,
        _DWORD *a8)
{
  unsigned int v12; // edi
  __int64 v13; // rbx
  __int64 v14; // rax
  int ExpandedCanonicalLongPathName; // eax
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  int v21; // r13d
  int v22; // r14d
  unsigned int v23; // eax
  unsigned int i; // esi
  int v25; // r14d
  int v26; // r12d
  unsigned int j; // esi
  int v28; // ebx
  int v29; // ebx
  int v30; // r14d
  unsigned int v31; // eax
  unsigned int v32; // ebx
  __int64 v33; // r8
  const char *v34; // rdx
  int v35; // ebx
  int v36; // eax
  unsigned int v37; // eax
  int v38; // eax
  unsigned int v39; // edx
  unsigned __int16 *v40; // r8
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rcx
  int v49; // ebx
  int v50; // r15d
  __int64 v51; // rsi
  int v52; // eax
  int v53; // ebx
  __int64 v54; // rsi
  int v55; // eax
  int v56; // ebx
  int ProfileTypeFromProfileIndex; // eax
  int v58; // eax
  __int64 v59; // rax
  __int64 v60; // rcx
  int v61; // [rsp+50h] [rbp-B0h] BYREF
  enum NET_FW_IP_VERSION_ v62; // [rsp+54h] [rbp-ACh]
  _DWORD *v63; // [rsp+58h] [rbp-A8h]
  _DWORD *v64; // [rsp+60h] [rbp-A0h]
  int v65; // [rsp+68h] [rbp-98h]
  __int64 v66; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v67; // [rsp+78h] [rbp-88h] BYREF
  struct _tag_FW_RULE *v68; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v69[2]; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v70[2]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD *v71; // [rsp+A0h] [rbp-60h]
  __int64 v72; // [rsp+A8h] [rbp-58h]
  int v73; // [rsp+B0h] [rbp-50h] BYREF
  int v74; // [rsp+B4h] [rbp-4Ch] BYREF
  int v75; // [rsp+B8h] [rbp-48h] BYREF
  int v76; // [rsp+BCh] [rbp-44h] BYREF
  int v77; // [rsp+C0h] [rbp-40h] BYREF
  int v78; // [rsp+C4h] [rbp-3Ch] BYREF
  int v79; // [rsp+C8h] [rbp-38h] BYREF
  char v80; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v81; // [rsp+D1h] [rbp-2Fh]
  int v82; // [rsp+D9h] [rbp-27h]
  __int16 v83; // [rsp+DDh] [rbp-23h]
  char v84; // [rsp+DFh] [rbp-21h]
  _DWORD v85[4]; // [rsp+E0h] [rbp-20h] BYREF
  int v86[2]; // [rsp+F0h] [rbp-10h] BYREF
  int v87; // [rsp+F8h] [rbp-8h]
  __int64 v88; // [rsp+100h] [rbp+0h] BYREF
  int v89; // [rsp+108h] [rbp+8h]
  _QWORD v90[16]; // [rsp+110h] [rbp+10h]

  v64 = a8;
  v63 = a7;
  v62 = a2;
  v81 = 0;
  v82 = 0;
  v12 = 0;
  v83 = 0;
  v84 = 0;
  v65 = a3;
  v74 = 4;
  v79 = 4;
  v85[0] = 4;
  v85[1] = 4;
  v85[2] = 4;
  *(_QWORD *)v86 = 0;
  v87 = 0;
  v69[1] = &v88;
  v71 = v69;
  v78 = 0;
  v61 = 0;
  v67 = 0;
  v80 = 0;
  v68 = 0;
  v66 = 0;
  v73 = 0;
  v75 = 0;
  v69[0] = 6;
  v70[0] = 522;
  v70[1] = 1;
  v72 = 0x10000;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_78a008cd44403a71577f2350fc67ddf1_Traceguids);
  v13 = -1;
  if ( a1 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(a1 + 2 * v14) );
    if ( v14 )
    {
      ExpandedCanonicalLongPathName = FwGetExpandedCanonicalLongPathName(a1, &v67, &v78);
      v12 = ExpandedCanonicalLongPathName;
      if ( ExpandedCanonicalLongPathName < 0 )
      {
LABEL_7:
        v16 = (unsigned int)ExpandedCanonicalLongPathName;
LABEL_8:
        FwReportReturnError("IsPortOrICMPAllowed", v16);
        goto LABEL_9;
      }
      if ( !v78 )
        goto LABEL_88;
    }
  }
  if ( a3 && a5 != NET_FW_IP_PROTOCOL_UDP && a5 != NET_FW_IP_PROTOCOL_TCP )
  {
LABEL_88:
    v16 = 2147942487LL;
    v12 = -2147024809;
    goto LABEL_8;
  }
  v21 = 0;
  if ( !a4 )
    goto LABEL_18;
  do
    ++v13;
  while ( a4[v13] );
  if ( v13 )
  {
    ExpandedCanonicalLongPathName = InetAddr(a2, a4, (union FW_INET_ADDR_STORAGE *)&v80);
    v22 = 0;
    v12 = ExpandedCanonicalLongPathName;
    if ( ExpandedCanonicalLongPathName < 0 )
      goto LABEL_7;
    ExpandedCanonicalLongPathName = FwIsLoopbackAddress(a2, (union FW_INET_ADDR_STORAGE *)&v80, &v61);
    v12 = ExpandedCanonicalLongPathName;
    if ( ExpandedCanonicalLongPathName < 0 )
      goto LABEL_7;
    v21 = 1;
    if ( v61 )
    {
      *v63 = 1;
      goto LABEL_115;
    }
  }
  else
  {
LABEL_18:
    v22 = 0;
  }
  v23 = FWOpenPolicyStore(545, 0, 5, 1, 0, (__int64)&v66);
  if ( v23 )
  {
    v34 = "FWOpenPolicyStore";
    goto LABEL_70;
  }
  v23 = FWGetGlobalConfig(545, 0, 5, 2, 0, (__int64)&v75, (__int64)&v79);
  if ( v23 )
  {
    v34 = "FWGetGlobalConfig";
LABEL_70:
    v33 = v23;
    goto LABEL_38;
  }
  v76 = 0;
  for ( i = 0; i < 3; ++i )
  {
    v56 = v75;
    if ( ((unsigned int)FwGetProfileTypeFromProfileIndex(i) & v56) != 0 )
    {
      v74 = 4;
      ProfileTypeFromProfileIndex = FwGetProfileTypeFromProfileIndex(i);
      v76 = 0;
      v37 = FWGetConfig2(v66, 1, ProfileTypeFromProfileIndex, 1, (__int64)&v73, (__int64)&v74, (__int64)&v76);
      if ( v37 )
      {
LABEL_86:
        v33 = v37;
LABEL_37:
        v34 = "FWGetConfig";
LABEL_38:
        v12 = FwReportErrorAsWinError("IsPortOrICMPAllowed", v34, v33);
        goto LABEL_9;
      }
      if ( v73 )
        v58 = 0;
      else
        v58 = FwGetProfileTypeFromProfileIndex(i);
      v22 |= v58;
      v76 = v22;
    }
  }
  v25 = 0;
  v26 = 0;
  v61 = 0;
  for ( j = 0; j < 3; ++j )
  {
    v28 = v75;
    if ( ((unsigned int)FwGetProfileTypeFromProfileIndex(j) & v28) != 0 )
    {
      v74 = 4;
      v29 = FwGetProfileTypeFromProfileIndex(j);
      v30 = v66;
      v77 = 0;
      if ( g_Provider )
        EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
      GetTickCount64();
      v31 = Int_FWGetOrSetConfig(1, v30, 3, v29, 1, (__int64)&v73, (__int64)&v74, (__int64)&v77);
      v25 = 0;
      v32 = v31;
      if ( v31
        && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v31);
      }
      if ( g_Provider )
        EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
      if ( v32 )
      {
        v33 = v32;
        goto LABEL_37;
      }
      if ( v73 )
        v35 = 0;
      else
        v35 = FwGetProfileTypeFromProfileIndex(j);
      v36 = FwGetProfileTypeFromProfileIndex(j);
      v77 = 0;
      v37 = FWGetConfig2(v66, 17, v36, 1, (__int64)&v73, (__int64)&v74, (__int64)&v77);
      if ( v37 )
        goto LABEL_86;
      v26 |= v35;
      if ( v73 == 1 )
        v38 = FwGetProfileTypeFromProfileIndex(j);
      else
        v38 = 0;
      v61 |= v38;
    }
  }
  if ( a5 != NET_FW_IP_PROTOCOL_ANY || (v39 = 0, a6 < 0x100u) )
  {
    v88 = 5;
    v89 = 2;
    if ( a6 >= 0x100u )
    {
      LOWORD(v90[0]) = a5;
    }
    else if ( v62 )
    {
      LOWORD(v90[0]) = 58;
    }
    else
    {
      LOWORD(v90[0]) = 1;
    }
    v39 = 1;
  }
  v40 = v67;
  if ( v67 )
  {
    v59 = v39++;
    v60 = 3 * v59;
    *(&v88 + v60) = 4;
    LODWORD(v90[v60]) = 5;
    v90[v60] = v40;
  }
  v41 = v39;
  v42 = v39 + 1;
  v43 = 3 * v41;
  LODWORD(v90[v43]) = v75;
  *(&v88 + v43) = 0;
  LODWORD(v90[v43]) = 3;
  v44 = 3 * v42;
  *(&v88 + v44) = 1;
  v45 = (unsigned int)(v42 + 1);
  LODWORD(v90[v44]) = 3;
  LODWORD(v90[v44]) = 196608;
  v46 = 3 * v45;
  v47 = (unsigned int)(v45 + 1);
  *(&v88 + v46) = 10;
  LODWORD(v90[v46]) = 3;
  LODWORD(v90[v46]) = 1;
  v48 = 3 * v47;
  v90[v48] = L"S-1-0-0";
  LODWORD(v69[0]) = v47 + 1;
  *(&v88 + v48) = 12;
  LODWORD(v90[v48]) = 5;
  v23 = FWQueryFirewallRules(v66, (unsigned int)v70, 15, (unsigned int)&v73, (__int64)&v68);
  if ( v23 )
  {
    v34 = "FWQueryFirewallRules";
    goto LABEL_70;
  }
  v49 = 0;
  if ( FindMatchingPortRule(
         v68,
         v67,
         v62,
         v65,
         a5,
         a6,
         (union FW_INET_ADDR_STORAGE *)((unsigned __int64)&v80 & -(__int64)(v21 != 0)),
         (enum _tag_FW_RULE_ACTION *const)v85,
         v86) )
  {
    v54 = 0;
    do
    {
      v55 = FwGetProfileTypeFromProfileIndex((unsigned int)v54);
      if ( v86[v54] )
        v25 |= v55;
      else
        v25 &= ~v55;
      switch ( v85[v54] )
      {
        case 1:
          goto LABEL_77;
        case 2:
          v49 &= ~(unsigned int)FwGetProfileTypeFromProfileIndex((unsigned int)v54);
          break;
        case 3:
LABEL_77:
          v49 |= FwGetProfileTypeFromProfileIndex((unsigned int)v54);
          break;
        default:
          v49 &= ~(unsigned int)FwGetProfileTypeFromProfileIndex((unsigned int)v54);
          v25 &= ~(unsigned int)FwGetProfileTypeFromProfileIndex((unsigned int)v54);
          break;
      }
      v54 = (unsigned int)(v54 + 1);
    }
    while ( (unsigned int)v54 < 3 );
  }
  v50 = v61;
  v51 = 0;
  do
  {
    if ( ((unsigned int)FwGetProfileTypeFromProfileIndex((unsigned int)v51) & v50) != 0 )
    {
      if ( ((unsigned int)FwGetProfileTypeFromProfileIndex((unsigned int)v51) & v26) == 0 || v85[v51] == 4 )
      {
        v49 &= ~(unsigned int)FwGetProfileTypeFromProfileIndex((unsigned int)v51);
LABEL_63:
        v25 &= ~(unsigned int)FwGetProfileTypeFromProfileIndex((unsigned int)v51);
      }
    }
    else if ( ((unsigned int)FwGetProfileTypeFromProfileIndex((unsigned int)v51) & v26) == 0 || v85[v51] == 4 )
    {
      v49 |= FwGetProfileTypeFromProfileIndex((unsigned int)v51);
      goto LABEL_63;
    }
    v51 = (unsigned int)(v51 + 1);
  }
  while ( (unsigned int)v51 < 3 );
  v52 = v75;
  v53 = v75 & (v76 | v49);
  if ( v53 == v75 )
  {
    *v63 = 1;
    *v64 = (v25 & v52) != 0;
    goto LABEL_9;
  }
  if ( v53 )
  {
    *v63 = 1;
    *v64 = 1;
    goto LABEL_9;
  }
  *v63 = 0;
LABEL_115:
  *v64 = 0;
LABEL_9:
  if ( v66 )
    FWClosePolicyStore(v66, v17, v18, v19);
  if ( v68 )
    FWFreeFirewallRules(v68);
  FwBaseFree(v67);
  if ( (unsigned int)IsRpcError(v12) )
  {
    v12 = -2147023174;
    return (unsigned int)FwReportReturnError("IsPortOrICMPAllowed", v12);
  }
  if ( (v12 & 0x80000000) != 0 )
    return (unsigned int)FwReportReturnError("IsPortOrICMPAllowed", v12);
  return v12;
}

```

## disassembly

```asm
0x1800191e0  mov     [rsp-8+arg_10], rbx
0x1800191e5  push    rbp
0x1800191e6  push    rsi
0x1800191e7  push    rdi
0x1800191e8  push    r12
0x1800191ea  push    r13
0x1800191ec  push    r14
0x1800191ee  push    r15
0x1800191f0  lea     rbp, [rsp-0A0h]
0x1800191f8  sub     rsp, 1A0h
0x1800191ff  mov     rax, cs:__security_cookie
0x180019206  xor     rax, rsp
0x180019209  mov     [rbp+0D0h+var_40], rax
0x180019210  mov     rax, [rbp+0D0h+arg_38]
0x180019217  mov     r12d, edx
0x18001921a  mov     [rsp+1D0h+var_170], rax
0x18001921f  mov     r14, r9
0x180019222  mov     rax, [rbp+0D0h+arg_30]
0x180019229  mov     r13d, r8d
0x18001922c  mov     [rsp+1D0h+var_178], rax
0x180019231  mov     rsi, rcx
0x180019234  xor     eax, eax
0x180019236  mov     [rsp+1D0h+var_17C], edx
0x18001923a  xor     edx, edx
0x18001923c  mov     [rbp+0D0h+var_FF], rax
0x180019240  mov     [rbp+0D0h+var_F7], eax
0x180019243  mov     edi, edx
0x180019245  mov     [rbp+0D0h+var_F3], ax
0x180019249  mov     [rbp+0D0h+var_F1], al
0x18001924c  lea     eax, [rdx+4]
0x18001924f  mov     [rsp+1D0h+var_168], r8d
0x180019254  mov     [rbp+0D0h+var_11C], eax
0x180019257  mov     [rbp+0D0h+var_108], eax
0x18001925a  mov     [rbp+0D0h+var_F0], eax
0x18001925d  mov     [rbp+0D0h+var_EC], eax
0x180019260  mov     [rbp+0D0h+var_E8], eax
0x180019263  xor     eax, eax
0x180019265  mov     qword ptr [rbp+0D0h+var_E0], rax
0x180019269  mov     [rbp+0D0h+var_D8], eax
0x18001926c  lea     rax, [rbp+0D0h+var_D0]
0x180019270  mov     [rbp+0D0h+var_140], rax
0x180019274  lea     rax, [rbp+0D0h+var_148]
0x180019278  mov     [rbp+0D0h+var_130], rax
0x18001927c  mov     [rbp+0D0h+var_10C], edx
0x18001927f  mov     [rsp+1D0h+var_180], edx
0x180019283  mov     [rsp+1D0h+var_158], rdx
0x180019288  mov     [rbp+0D0h+var_100], dl
0x18001928b  mov     [rbp+0D0h+var_150], rdx
0x18001928f  mov     [rsp+1D0h+var_160], rdx
0x180019294  mov     [rbp+0D0h+var_120], edx
0x180019297  mov     [rbp+0D0h+var_118], edx
0x18001929a  mov     [rbp+0D0h+var_148], 6
0x1800192a2  mov     [rbp+0D0h+var_138], 20Ah
0x1800192a9  mov     [rbp+0D0h+var_134], 1
0x1800192b0  mov     [rbp+0D0h+var_128], 10000h
0x1800192b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192bf  lea     rax, WPP_GLOBAL_Control
0x1800192c6  cmp     rcx, rax
0x1800192c9  jnz     loc_180019563
0x1800192cf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800192d3  test    rsi, rsi
0x1800192d6  jz      loc_18001939A
0x1800192dc  mov     rax, rbx
0x1800192df  inc     rax
0x1800192e2  cmp     [rsi+rax*2], dx
0x1800192e6  jnz     short loc_1800192DF
0x1800192e8  test    rax, rax
0x1800192eb  jz      loc_18001939A
0x1800192f1  lea     r8, [rbp+0D0h+var_10C]
0x1800192f5  mov     rcx, rsi
0x1800192f8  lea     rdx, [rsp+1D0h+var_158]
0x1800192fd  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x180019304  nop     dword ptr [rax+rax+00h]
0x180019309  xor     edx, edx
0x18001930b  mov     edi, eax
0x18001930d  test    eax, eax
0x18001930f  jns     loc_180019976
0x180019315  mov     edx, eax
0x180019317  lea     rcx, aIsportoricmpal_0; "IsPortOrICMPAllowed"
0x18001931e  call    cs:__imp_FwReportReturnError
0x180019325  nop     dword ptr [rax+rax+00h]
0x18001932a  mov     rcx, [rsp+1D0h+var_160]
0x18001932f  test    rcx, rcx
0x180019332  jnz     loc_180019B03
0x180019338  mov     rcx, [rbp+0D0h+var_150]
0x18001933c  test    rcx, rcx
0x18001933f  jnz     loc_180019853
0x180019345  mov     rcx, [rsp+1D0h+var_158]
0x18001934a  call    cs:__imp_FwBaseFree
0x180019351  nop     dword ptr [rax+rax+00h]
0x180019356  mov     ecx, edi; int
0x180019358  call    ?IsRpcError@@YAHJ@Z; IsRpcError(long)
0x18001935d  test    eax, eax
0x18001935f  jnz     loc_180019B0D
0x180019365  test    edi, edi
0x180019367  js      loc_180019B12
0x18001936d  mov     eax, edi
0x18001936f  mov     rcx, [rbp+0D0h+var_40]
0x180019376  xor     rcx, rsp; StackCookie
0x180019379  call    __security_check_cookie
0x18001937e  mov     rbx, [rsp+1D0h+arg_10]
0x180019386  add     rsp, 1A0h
0x18001938d  pop     r15
0x18001938f  pop     r14
0x180019391  pop     r13
0x180019393  pop     r12
0x180019395  pop     rdi
0x180019396  pop     rsi
0x180019397  pop     rbp
0x180019398  retn
0x18001939a  mov     r15d, [rbp+0D0h+arg_20]
0x1800193a1  test    r13d, r13d
0x1800193a4  jnz     loc_18001998B
0x1800193aa  mov     r13d, edx
0x1800193ad  test    r14, r14
0x1800193b0  jnz     loc_180019608
0x1800193b6  mov     ebx, 1
0x1800193bb  xor     r14d, r14d
0x1800193be  lea     rax, [rsp+1D0h+var_160]
0x1800193c3  mov     esi, 221h
0x1800193c8  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x1800193cd  mov     r12d, 5
0x1800193d3  mov     ecx, esi
0x1800193d5  mov     [rsp+1D0h+var_1B0], r14d
0x1800193da  mov     r8d, r12d
0x1800193dd  mov     r9d, ebx
0x1800193e0  xor     edx, edx
0x1800193e2  call    FWOpenPolicyStore
0x1800193e7  test    eax, eax
0x1800193e9  jnz     loc_1800199A0
0x1800193ef  lea     rax, [rbp+0D0h+var_108]
0x1800193f3  mov     ecx, esi
0x1800193f5  mov     [rsp+1D0h+var_1A0], rax
0x1800193fa  lea     r9d, [r12-3]
0x1800193ff  lea     rax, [rbp+0D0h+var_118]
0x180019403  mov     r8d, r12d
0x180019406  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x18001940b  xor     edx, edx
0x18001940d  mov     [rsp+1D0h+var_1B0], r14d
0x180019412  call    FWGetGlobalConfig
0x180019417  test    eax, eax
0x180019419  jnz     loc_18001985D
0x18001941f  mov     [rbp+0D0h+var_114], r14d
0x180019423  xor     esi, esi
0x180019425  cmp     esi, 3
0x180019428  jb      loc_180019903
0x18001942e  xor     r14d, r14d
0x180019431  mov     r12d, r14d
0x180019434  mov     [rsp+1D0h+var_180], r14d
0x180019439  mov     esi, r14d
0x18001943c  cmp     esi, 3
0x18001943f  jnb     loc_180019670
0x180019445  mov     ebx, [rbp+0D0h+var_118]
0x180019448  mov     ecx, esi
0x18001944a  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x180019451  nop     dword ptr [rax+rax+00h]
0x180019456  test    ebx, eax
0x180019458  jnz     short loc_180019463
0x18001945a  mov     ebx, 1
0x18001945f  add     esi, ebx
0x180019461  jmp     short loc_18001943C
0x180019463  mov     ecx, esi
0x180019465  mov     [rbp+0D0h+var_11C], 4
0x18001946c  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x180019473  nop     dword ptr [rax+rax+00h]
0x180019478  mov     rcx, cs:g_Provider
0x18001947f  mov     ebx, eax
0x180019481  mov     r14, [rsp+1D0h+var_160]
0x180019486  mov     [rbp+0D0h+var_110], 0
0x18001948d  test    rcx, rcx
0x180019490  jz      short loc_1800194AB
0x180019492  xor     r9d, r9d
0x180019495  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x18001949c  xor     r8d, r8d
0x18001949f  call    cs:__imp_EtwEventWrite
0x1800194a6  nop     dword ptr [rax+rax+00h]
0x1800194ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800194b2  lea     rax, WPP_GLOBAL_Control
0x1800194b9  cmp     rcx, rax
0x1800194bc  jz      short loc_1800194C8
0x1800194be  test    byte ptr [rcx+1Ch], 8
0x1800194c2  jnz     loc_1800199D9
0x1800194c8  call    cs:__imp_GetTickCount64
0x1800194cf  nop     dword ptr [rax+rax+00h]
0x1800194d4  lea     rax, [rbp+0D0h+var_110]
0x1800194d8  mov     r9d, ebx
0x1800194db  mov     [rsp+1D0h+var_198], rax
0x1800194e0  mov     rdx, r14
0x1800194e3  lea     rax, [rbp+0D0h+var_11C]
0x1800194e7  mov     [rsp+1D0h+var_1A0], rax
0x1800194ec  lea     rax, [rbp+0D0h+var_120]
0x1800194f0  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x1800194f5  mov     eax, 1
0x1800194fa  mov     ecx, eax
0x1800194fc  mov     [rsp+1D0h+var_1B0], eax
0x180019500  lea     r8d, [rax+2]
0x180019504  call    Int_FWGetOrSetConfig
0x180019509  xor     r14d, r14d
0x18001950c  mov     ebx, eax
0x18001950e  test    eax, eax
0x180019510  jnz     loc_1800198C5
0x180019516  mov     rcx, cs:g_Provider
0x18001951d  test    rcx, rcx
0x180019520  jz      short loc_18001953B
0x180019522  xor     r9d, r9d
0x180019525  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x18001952c  xor     r8d, r8d
0x18001952f  call    cs:__imp_EtwEventWrite
0x180019536  nop     dword ptr [rax+rax+00h]
0x18001953b  test    ebx, ebx
0x18001953d  jz      short loc_180019589
0x18001953f  mov     r8d, ebx
0x180019542  lea     rdx, aFwgetconfig_1; "FWGetConfig"
0x180019549  lea     rcx, aIsportoricmpal_0; "IsPortOrICMPAllowed"
0x180019550  call    cs:__imp_FwReportErrorAsWinError
0x180019557  nop     dword ptr [rax+rax+00h]
0x18001955c  mov     edi, eax
0x18001955e  jmp     loc_18001932A
0x180019563  test    byte ptr [rcx+1Ch], 8
0x180019567  jz      loc_1800192CF
0x18001956d  mov     rcx, [rcx+10h]
0x180019571  lea     r8, WPP_78a008cd44403a71577f2350fc67ddf1_Traceguids
0x180019578  mov     edx, 0Dh
0x18001957d  call    WPP_SF_
0x180019582  xor     edx, edx
0x180019584  jmp     loc_1800192CF
0x180019589  cmp     [rbp+0D0h+var_120], r14d
0x18001958d  jz      loc_180019836
0x180019593  mov     ebx, r14d
0x180019596  mov     ecx, esi
0x180019598  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x18001959f  nop     dword ptr [rax+rax+00h]
0x1800195a4  lea     rcx, [rbp+0D0h+var_110]
0x1800195a8  mov     [rbp+0D0h+var_110], r14d
0x1800195ac  mov     [rsp+1D0h+var_1A0], rcx
0x1800195b1  mov     r9d, 1
0x1800195b7  lea     rcx, [rbp+0D0h+var_11C]
0x1800195bb  mov     r8d, eax
0x1800195be  mov     qword ptr [rsp+1D0h+var_1A8], rcx
0x1800195c3  lea     rcx, [rbp+0D0h+var_120]
0x1800195c7  mov     qword ptr [rsp+1D0h+var_1B0], rcx
0x1800195cc  mov     rcx, [rsp+1D0h+var_160]
0x1800195d1  lea     edx, [r9+10h]
0x1800195d5  call    FWGetConfig2
0x1800195da  test    eax, eax
0x1800195dc  jnz     loc_18001996E
0x1800195e2  or      r12d, ebx
0x1800195e5  lea     ebx, [rax+1]
0x1800195e8  cmp     [rbp+0D0h+var_120], ebx
0x1800195eb  jnz     loc_18001984B
0x1800195f1  mov     ecx, esi
0x1800195f3  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x1800195fa  nop     dword ptr [rax+rax+00h]
0x1800195ff  or      [rsp+1D0h+var_180], eax
0x180019603  jmp     loc_18001945F
0x180019608  inc     rbx
0x18001960b  cmp     [r14+rbx*2], dx
0x180019610  jnz     short loc_180019608
0x180019612  test    rbx, rbx
0x180019615  jz      loc_1800193B6
0x18001961b  lea     r8, [rbp+0D0h+var_100]; union FW_INET_ADDR_STORAGE *
0x18001961f  mov     rdx, r14; unsigned __int16 *
0x180019622  mov     ecx, r12d; enum NET_FW_IP_VERSION_
0x180019625  call    ?InetAddr@@YAJW4NET_FW_IP_VERSION_@@PEAGPEATFW_INET_ADDR_STORAGE@@@Z; InetAddr(NET_FW_IP_VERSION_,ushort *,FW_INET_ADDR_STORAGE *)
0x18001962a  xor     r14d, r14d
0x18001962d  mov     edi, eax
0x18001962f  test    eax, eax
0x180019631  js      loc_180019315
0x180019637  lea     r8, [rsp+1D0h+var_180]; int *
0x18001963c  mov     ecx, r12d; enum NET_FW_IP_VERSION_
0x18001963f  lea     rdx, [rbp+0D0h+var_100]; union FW_INET_ADDR_STORAGE *
0x180019643  call    ?FwIsLoopbackAddress@@YAJW4NET_FW_IP_VERSION_@@PEATFW_INET_ADDR_STORAGE@@PEAH@Z; FwIsLoopbackAddress(NET_FW_IP_VERSION_,FW_INET_ADDR_STORAGE *,int *)
0x180019648  mov     edi, eax
0x18001964a  test    eax, eax
0x18001964c  js      loc_180019315
0x180019652  lea     ebx, [r14+1]
0x180019656  mov     r13d, ebx
0x180019659  cmp     [rsp+1D0h+var_180], r14d
0x18001965e  jz      loc_1800193BE
0x180019664  mov     rcx, [rsp+1D0h+var_178]
0x180019669  mov     [rcx], ebx
0x18001966b  jmp     loc_180019AF6
0x180019670  movzx   esi, [rbp+0D0h+arg_28]
0x180019677  mov     eax, 100h
0x18001967c  cmp     r15d, eax
0x18001967f  jnz     loc_1800199F3
0x180019685  mov     edx, r14d
0x180019688  cmp     si, ax
0x18001968b  jb      loc_1800199F3
0x180019691  mov     r8, [rsp+1D0h+var_158]
0x180019696  test    r8, r8
0x180019699  jnz     loc_180019A2B
0x18001969f  mov     eax, edx
0x1800196a1  lea     r9, [rbp+0D0h+var_120]
0x1800196a5  add     edx, ebx
0x1800196a7  mov     r8d, 0Fh
0x1800196ad  lea     rcx, [rax+rax*2]
0x1800196b1  mov     eax, [rbp+0D0h+var_118]
0x1800196b4  mov     dword ptr [rbp+rcx*8+0D0h+var_C0], eax
0x1800196b8  lea     rax, aS100; "S-1-0-0"
  ... truncated ...
```
