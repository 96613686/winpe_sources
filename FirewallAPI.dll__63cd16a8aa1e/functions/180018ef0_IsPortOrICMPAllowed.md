# IsPortOrICMPAllowed

- ea: `0x180018ef0`
- end: `0x18001979b`
- name: `IsPortOrICMPAllowed`
- size: `2219`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180037170`
- `0x180037230`
- `0x180037560`

## callees

- `0x180005954`
- `0x180008a10`
- `0x180008b30`
- `0x180009080`
- `0x180009e70`
- `0x18000c130`
- `0x18000c560`
- `0x18000d850`
- `0x180018ef0`
- `0x1800197a4`
- `0x1800197d8`
- `0x180023a88`
- `0x1800277b0`
- `0x18003104c`
- `0x180037094`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180019190`
- `ntdll!EtwEventWrite` at `0x180019214`
- `ntdll!EtwEventWrite` at `0x180019190`
- `ntdll!EtwEventWrite` at `0x180019214`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800191b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800191b3`
- `fwbase!FwBaseFree` at `0x18001904e`
- `fwbase!FwBaseFree` at `0x18001904e`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019147`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019163`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019271`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800192c6`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019477`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019488`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019499`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800194a5`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800194ed`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18001951f`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18001954c`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800195ab`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800195c2`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18001964b`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800196ed`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800196f9`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18001970b`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18001972a`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019742`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019147`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019163`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019271`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800192c6`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019477`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019488`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019499`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800194a5`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800194ed`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18001951f`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18001954c`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800195ab`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800195c2`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18001964b`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800196ed`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800196f9`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18001970b`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x18001972a`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180019742`
- `fwbase!FwReportErrorAsWinError` at `0x18001922f`
- `fwbase!FwReportErrorAsWinError` at `0x18001922f`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x18001900d`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x18001900d`
- `fwbase!FwReportReturnError` at `0x180019028`
- `fwbase!FwReportReturnError` at `0x18001978e`
- `fwbase!FwReportReturnError` at `0x180019028`
- `fwbase!FwReportReturnError` at `0x18001978e`

## string_xrefs

- `0x180019637`: `FWOpenPolicyStore`
- `0x18001950c`: `FWGetGlobalConfig`
- `0x180019221`: `FWGetConfig`

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
  v23 = FWOpenPolicyStore(0x221u, 0, 5u, 1u, 0, &v66);
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
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
      GetTickCount64();
      v31 = Int_FWGetOrSetConfig(1, v30, 3, v29, 1, (__int64)&v73, (__int64)&v74, (__int64)&v77);
      v25 = 0;
      v32 = v31;
      if ( v31
        && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v31);
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
0x180018ef0  mov     [rsp-8+arg_10], rbx
0x180018ef5  push    rbp
0x180018ef6  push    rsi
0x180018ef7  push    rdi
0x180018ef8  push    r12
0x180018efa  push    r13
0x180018efc  push    r14
0x180018efe  push    r15
0x180018f00  lea     rbp, [rsp-0A0h]
0x180018f08  sub     rsp, 1A0h
0x180018f0f  mov     rax, cs:__security_cookie
0x180018f16  xor     rax, rsp
0x180018f19  mov     [rbp+0D0h+var_40], rax
0x180018f20  mov     rax, [rbp+0D0h+arg_38]
0x180018f27  mov     r12d, edx
0x180018f2a  mov     [rsp+1D0h+var_170], rax
0x180018f2f  mov     r14, r9
0x180018f32  mov     rax, [rbp+0D0h+arg_30]
0x180018f39  mov     r13d, r8d
0x180018f3c  mov     [rsp+1D0h+var_178], rax
0x180018f41  mov     rsi, rcx
0x180018f44  xor     eax, eax
0x180018f46  mov     [rsp+1D0h+var_17C], edx
0x180018f4a  xor     edx, edx
0x180018f4c  mov     [rbp+0D0h+var_FF], rax
0x180018f50  mov     [rbp+0D0h+var_F7], eax
0x180018f53  mov     edi, edx
0x180018f55  mov     [rbp+0D0h+var_F3], ax
0x180018f59  mov     [rbp+0D0h+var_F1], al
0x180018f5c  lea     eax, [rdx+4]
0x180018f5f  mov     [rsp+1D0h+var_168], r8d
0x180018f64  mov     [rbp+0D0h+var_11C], eax
0x180018f67  mov     [rbp+0D0h+var_108], eax
0x180018f6a  mov     [rbp+0D0h+var_F0], eax
0x180018f6d  mov     [rbp+0D0h+var_EC], eax
0x180018f70  mov     [rbp+0D0h+var_E8], eax
0x180018f73  xor     eax, eax
0x180018f75  mov     qword ptr [rbp+0D0h+var_E0], rax
0x180018f79  mov     [rbp+0D0h+var_D8], eax
0x180018f7c  lea     rax, [rbp+0D0h+var_D0]
0x180018f80  mov     [rbp+0D0h+var_140], rax
0x180018f84  lea     rax, [rbp+0D0h+var_148]
0x180018f88  mov     [rbp+0D0h+var_130], rax
0x180018f8c  mov     [rbp+0D0h+var_10C], edx
0x180018f8f  mov     [rsp+1D0h+var_180], edx
0x180018f93  mov     [rsp+1D0h+var_158], rdx
0x180018f98  mov     [rbp+0D0h+var_100], dl
0x180018f9b  mov     [rbp+0D0h+var_150], rdx
0x180018f9f  mov     [rsp+1D0h+var_160], rdx
0x180018fa4  mov     [rbp+0D0h+var_120], edx
0x180018fa7  mov     [rbp+0D0h+var_118], edx
0x180018faa  mov     [rbp+0D0h+var_148], 6
0x180018fb2  mov     [rbp+0D0h+var_138], 20Ah
0x180018fb9  mov     [rbp+0D0h+var_134], 1
0x180018fc0  mov     [rbp+0D0h+var_128], 10000h
0x180018fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180018fcf  lea     rax, WPP_GLOBAL_Control
0x180018fd6  cmp     rcx, rax
0x180018fd9  jnz     loc_18001923C
0x180018fdf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180018fe3  test    rsi, rsi
0x180018fe6  jz      loc_180019097
0x180018fec  mov     rax, rbx
0x180018fef  inc     rax
0x180018ff2  cmp     [rsi+rax*2], dx
0x180018ff6  jnz     short loc_180018FEF
0x180018ff8  test    rax, rax
0x180018ffb  jz      loc_180019097
0x180019001  lea     r8, [rbp+0D0h+var_10C]
0x180019005  mov     rcx, rsi
0x180019008  lea     rdx, [rsp+1D0h+var_158]
0x18001900d  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x180019013  xor     edx, edx
0x180019015  mov     edi, eax
0x180019017  test    eax, eax
0x180019019  jns     loc_18001960D
0x18001901f  mov     edx, eax
0x180019021  lea     rcx, aIsportoricmpal_0; "IsPortOrICMPAllowed"
0x180019028  call    cs:__imp_FwReportReturnError
0x18001902e  mov     rcx, [rsp+1D0h+var_160]
0x180019033  test    rcx, rcx
0x180019036  jnz     loc_180019776
0x18001903c  mov     rcx, [rbp+0D0h+var_150]
0x180019040  test    rcx, rcx
0x180019043  jnz     loc_180019502
0x180019049  mov     rcx, [rsp+1D0h+var_158]
0x18001904e  call    cs:__imp_FwBaseFree
0x180019054  mov     ecx, edi; int
0x180019056  call    ?IsRpcError@@YAHJ@Z; IsRpcError(long)
0x18001905b  test    eax, eax
0x18001905d  jnz     loc_180019780
0x180019063  test    edi, edi
0x180019065  js      loc_180019785
0x18001906b  mov     eax, edi
0x18001906d  mov     rcx, [rbp+0D0h+var_40]
0x180019074  xor     rcx, rsp; StackCookie
0x180019077  call    __security_check_cookie
0x18001907c  mov     rbx, [rsp+1D0h+arg_10]
0x180019084  add     rsp, 1A0h
0x18001908b  pop     r15
0x18001908d  pop     r14
0x18001908f  pop     r13
0x180019091  pop     r12
0x180019093  pop     rdi
0x180019094  pop     rsi
0x180019095  pop     rbp
0x180019096  retn
0x180019097  mov     r15d, [rbp+0D0h+arg_20]
0x18001909e  test    r13d, r13d
0x1800190a1  jnz     loc_180019622
0x1800190a7  mov     r13d, edx
0x1800190aa  test    r14, r14
0x1800190ad  jnz     loc_1800192D5
0x1800190b3  mov     ebx, 1
0x1800190b8  xor     r14d, r14d
0x1800190bb  lea     rax, [rsp+1D0h+var_160]
0x1800190c0  mov     esi, 221h
0x1800190c5  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x1800190ca  mov     r12d, 5
0x1800190d0  mov     ecx, esi
0x1800190d2  mov     [rsp+1D0h+var_1B0], r14d
0x1800190d7  mov     r8d, r12d
0x1800190da  mov     r9d, ebx
0x1800190dd  xor     edx, edx
0x1800190df  call    FWOpenPolicyStore
0x1800190e4  test    eax, eax
0x1800190e6  jnz     loc_180019637
0x1800190ec  lea     rax, [rbp+0D0h+var_108]
0x1800190f0  mov     ecx, esi
0x1800190f2  mov     [rsp+1D0h+var_1A0], rax
0x1800190f7  lea     r9d, [r12-3]
0x1800190fc  lea     rax, [rbp+0D0h+var_118]
0x180019100  mov     r8d, r12d
0x180019103  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x180019108  xor     edx, edx
0x18001910a  mov     [rsp+1D0h+var_1B0], r14d
0x18001910f  call    FWGetGlobalConfig
0x180019114  test    eax, eax
0x180019116  jnz     loc_18001950C
0x18001911c  mov     [rbp+0D0h+var_114], r14d
0x180019120  xor     esi, esi
0x180019122  cmp     esi, 3
0x180019125  jb      loc_1800195A6
0x18001912b  xor     r14d, r14d
0x18001912e  mov     r12d, r14d
0x180019131  mov     [rsp+1D0h+var_180], r14d
0x180019136  mov     esi, r14d
0x180019139  cmp     esi, 3
0x18001913c  jnb     loc_18001933D
0x180019142  mov     ebx, [rbp+0D0h+var_118]
0x180019145  mov     ecx, esi
0x180019147  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x18001914d  test    ebx, eax
0x18001914f  jnz     short loc_18001915A
0x180019151  mov     ebx, 1
0x180019156  add     esi, ebx
0x180019158  jmp     short loc_180019139
0x18001915a  mov     ecx, esi
0x18001915c  mov     [rbp+0D0h+var_11C], 4
0x180019163  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x180019169  mov     rcx, cs:g_Provider
0x180019170  mov     ebx, eax
0x180019172  mov     r14, [rsp+1D0h+var_160]
0x180019177  mov     [rbp+0D0h+var_110], 0
0x18001917e  test    rcx, rcx
0x180019181  jz      short loc_180019196
0x180019183  xor     r9d, r9d
0x180019186  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x18001918d  xor     r8d, r8d
0x180019190  call    cs:__imp_EtwEventWrite
0x180019196  mov     rcx, cs:WPP_GLOBAL_Control
0x18001919d  lea     rax, WPP_GLOBAL_Control
0x1800191a4  cmp     rcx, rax
0x1800191a7  jz      short loc_1800191B3
0x1800191a9  test    byte ptr [rcx+1Ch], 8
0x1800191ad  jnz     loc_18001966A
0x1800191b3  call    cs:__imp_GetTickCount64
0x1800191b9  lea     rax, [rbp+0D0h+var_110]
0x1800191bd  mov     r9d, ebx
0x1800191c0  mov     [rsp+1D0h+var_198], rax
0x1800191c5  mov     rdx, r14
0x1800191c8  lea     rax, [rbp+0D0h+var_11C]
0x1800191cc  mov     [rsp+1D0h+var_1A0], rax
0x1800191d1  lea     rax, [rbp+0D0h+var_120]
0x1800191d5  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x1800191da  mov     eax, 1
0x1800191df  mov     ecx, eax
0x1800191e1  mov     [rsp+1D0h+var_1B0], eax
0x1800191e5  lea     r8d, [rax+2]
0x1800191e9  call    Int_FWGetOrSetConfig
0x1800191ee  xor     r14d, r14d
0x1800191f1  mov     ebx, eax
0x1800191f3  test    eax, eax
0x1800191f5  jnz     loc_180019568
0x1800191fb  mov     rcx, cs:g_Provider
0x180019202  test    rcx, rcx
0x180019205  jz      short loc_18001921A
0x180019207  xor     r9d, r9d
0x18001920a  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x180019211  xor     r8d, r8d
0x180019214  call    cs:__imp_EtwEventWrite
0x18001921a  test    ebx, ebx
0x18001921c  jz      short loc_180019262
0x18001921e  mov     r8d, ebx
0x180019221  lea     rdx, aFwgetconfig_1; "FWGetConfig"
0x180019228  lea     rcx, aIsportoricmpal_0; "IsPortOrICMPAllowed"
0x18001922f  call    cs:__imp_FwReportErrorAsWinError
0x180019235  mov     edi, eax
0x180019237  jmp     loc_18001902E
0x18001923c  test    byte ptr [rcx+1Ch], 8
0x180019240  jz      loc_180018FDF
0x180019246  mov     rcx, [rcx+10h]
0x18001924a  lea     r8, WPP_78a008cd44403a71577f2350fc67ddf1_Traceguids
0x180019251  mov     edx, 0Dh
0x180019256  call    WPP_SF_
0x18001925b  xor     edx, edx
0x18001925d  jmp     loc_180018FDF
0x180019262  cmp     [rbp+0D0h+var_120], r14d
0x180019266  jz      loc_1800194EB
0x18001926c  mov     ebx, r14d
0x18001926f  mov     ecx, esi
0x180019271  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x180019277  lea     rcx, [rbp+0D0h+var_110]
0x18001927b  mov     [rbp+0D0h+var_110], r14d
0x18001927f  mov     [rsp+1D0h+var_1A0], rcx
0x180019284  mov     r9d, 1
0x18001928a  lea     rcx, [rbp+0D0h+var_11C]
0x18001928e  mov     r8d, eax
0x180019291  mov     qword ptr [rsp+1D0h+var_1A8], rcx
0x180019296  lea     rcx, [rbp+0D0h+var_120]
0x18001929a  mov     qword ptr [rsp+1D0h+var_1B0], rcx
0x18001929f  mov     rcx, [rsp+1D0h+var_160]
0x1800192a4  lea     edx, [r9+10h]
0x1800192a8  call    FWGetConfig2
0x1800192ad  test    eax, eax
0x1800192af  jnz     loc_180019605
0x1800192b5  or      r12d, ebx
0x1800192b8  lea     ebx, [rax+1]
0x1800192bb  cmp     [rbp+0D0h+var_120], ebx
0x1800192be  jnz     loc_1800194FA
0x1800192c4  mov     ecx, esi
0x1800192c6  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x1800192cc  or      [rsp+1D0h+var_180], eax
0x1800192d0  jmp     loc_180019156
0x1800192d5  inc     rbx
0x1800192d8  cmp     [r14+rbx*2], dx
0x1800192dd  jnz     short loc_1800192D5
0x1800192df  test    rbx, rbx
0x1800192e2  jz      loc_1800190B3
0x1800192e8  lea     r8, [rbp+0D0h+var_100]; union FW_INET_ADDR_STORAGE *
0x1800192ec  mov     rdx, r14; unsigned __int16 *
0x1800192ef  mov     ecx, r12d; enum NET_FW_IP_VERSION_
0x1800192f2  call    ?InetAddr@@YAJW4NET_FW_IP_VERSION_@@PEAGPEATFW_INET_ADDR_STORAGE@@@Z; InetAddr(NET_FW_IP_VERSION_,ushort *,FW_INET_ADDR_STORAGE *)
0x1800192f7  xor     r14d, r14d
0x1800192fa  mov     edi, eax
0x1800192fc  test    eax, eax
0x1800192fe  js      loc_18001901F
0x180019304  lea     r8, [rsp+1D0h+var_180]; int *
0x180019309  mov     ecx, r12d; enum NET_FW_IP_VERSION_
0x18001930c  lea     rdx, [rbp+0D0h+var_100]; union FW_INET_ADDR_STORAGE *
0x180019310  call    ?FwIsLoopbackAddress@@YAJW4NET_FW_IP_VERSION_@@PEATFW_INET_ADDR_STORAGE@@PEAH@Z; FwIsLoopbackAddress(NET_FW_IP_VERSION_,FW_INET_ADDR_STORAGE *,int *)
0x180019315  mov     edi, eax
0x180019317  test    eax, eax
0x180019319  js      loc_18001901F
0x18001931f  lea     ebx, [r14+1]
0x180019323  mov     r13d, ebx
0x180019326  cmp     [rsp+1D0h+var_180], r14d
0x18001932b  jz      loc_1800190BB
0x180019331  mov     rcx, [rsp+1D0h+var_178]
0x180019336  mov     [rcx], ebx
0x180019338  jmp     loc_180019769
0x18001933d  movzx   esi, [rbp+0D0h+arg_28]
0x180019344  mov     eax, 100h
0x180019349  cmp     r15d, eax
0x18001934c  jnz     loc_180019684
0x180019352  mov     edx, r14d
0x180019355  cmp     si, ax
0x180019358  jb      loc_180019684
0x18001935e  mov     r8, [rsp+1D0h+var_158]
0x180019363  test    r8, r8
0x180019366  jnz     loc_1800196BC
0x18001936c  mov     eax, edx
0x18001936e  lea     r9, [rbp+0D0h+var_120]
0x180019372  add     edx, ebx
0x180019374  mov     r8d, 0Fh
0x18001937a  lea     rcx, [rax+rax*2]
0x18001937e  mov     eax, [rbp+0D0h+var_118]
0x180019381  mov     dword ptr [rbp+rcx*8+0D0h+var_C0], eax
0x180019385  lea     rax, aS100; "S-1-0-0"
0x18001938c  mov     [rbp+rcx*8+0D0h+var_D0], 0
0x180019395  mov     [rbp+rcx*8+0D0h+var_C8], 3
0x18001939d  lea     rcx, [rdx+rdx*2]
0x1800193a1  mov     [rbp+rcx*8+0D0h+var_D0], 1
0x1800193aa  add     edx, ebx
0x1800193ac  mov     [rbp+rcx*8+0D0h+var_C8], 3
0x1800193b4  mov     dword ptr [rbp+rcx*8+0D0h+var_C0], 30000h
0x1800193bc  lea     rcx, [rdx+rdx*2]
0x1800193c0  add     edx, ebx
0x1800193c2  mov     [rbp+rcx*8+0D0h+var_D0], 0Ah
0x1800193cb  mov     [rbp+rcx*8+0D0h+var_C8], 3
  ... truncated ...
```
