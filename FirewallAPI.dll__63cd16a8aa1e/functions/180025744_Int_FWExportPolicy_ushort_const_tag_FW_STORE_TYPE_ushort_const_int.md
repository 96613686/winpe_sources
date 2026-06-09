# Int_FWExportPolicy(ushort const *,_tag_FW_STORE_TYPE,ushort const *,int *)

- ea: `0x180025744`
- end: `0x1800261f1`
- name: `?Int_FWExportPolicy@@YAKPEBGW4_tag_FW_STORE_TYPE@@0PEAH@Z`
- size: `2733`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004d5f0`

## callees

- `0x180005954`
- `0x180008a10`
- `0x180009080`
- `0x18000b8c0`
- `0x18000c130`
- `0x18000c560`
- `0x18000f920`
- `0x180021440`
- `0x18002514c`
- `0x180025744`
- `0x180026200`
- `0x180026390`
- `0x180026540`
- `0x1800266b0`
- `0x180026820`
- `0x1800268e0`
- `0x1800277b0`
- `0x1800284c4`
- `0x18003104c`
- `0x18004d920`
- `0x18004dcc0`
- `0x180058318`
- `0x180058368`
- `0x18005856c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x1800261a8`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x1800261a8`
- `fwbase!FwBaseAlloc` at `0x180025f42`
- `fwbase!FwBaseAlloc` at `0x180025f42`
- `fwbase!FwBaseFree` at `0x180025f38`
- `fwbase!FwBaseFree` at `0x18002600a`
- `fwbase!FwBaseFree` at `0x180026158`
- `fwbase!FwBaseFree` at `0x180025f38`
- `fwbase!FwBaseFree` at `0x18002600a`
- `fwbase!FwBaseFree` at `0x180026158`
- `fwbase!FwHResultToWindowsError` at `0x180026160`
- `fwbase!FwHResultToWindowsError` at `0x180026160`
- `fwbase!FwReleasePrivilege` at `0x1800260f6`
- `fwbase!FwReleasePrivilege` at `0x1800260f6`
- `FWPolicyIOMgr!FwSetConfig` at `0x1800259ed`
- `FWPolicyIOMgr!FwSetConfig` at `0x1800259ed`
- `FWPolicyIOMgr!FwAddRule` at `0x180025b00`
- `FWPolicyIOMgr!FwAddRule` at `0x180025be0`
- `FWPolicyIOMgr!FwAddRule` at `0x180025cc8`
- `FWPolicyIOMgr!FwAddRule` at `0x180025b00`
- `FWPolicyIOMgr!FwAddRule` at `0x180025be0`
- `FWPolicyIOMgr!FwAddRule` at `0x180025cc8`
- `FWPolicyIOMgr!FwAddSet` at `0x180025d8a`
- `FWPolicyIOMgr!FwAddSet` at `0x180025e18`
- `FWPolicyIOMgr!FwAddSet` at `0x180025d8a`
- `FWPolicyIOMgr!FwAddSet` at `0x180025e18`
- `FWPolicyIOMgr!FwCreateLocalTempStore` at `0x18002585b`
- `FWPolicyIOMgr!FwCreateLocalTempStore` at `0x18002585b`
- `FWPolicyIOMgr!FwDestroyLocalTempStore` at `0x180026106`
- `FWPolicyIOMgr!FwDestroyLocalTempStore` at `0x180026106`
- `FWPolicyIOMgr!FwSetGlobalConfigInLocalTempStore` at `0x180025fef`
- `FWPolicyIOMgr!FwSetGlobalConfigInLocalTempStore` at `0x180025fef`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Int_FWExportPolicy(__int64 a1, unsigned int a2, const WCHAR *a3, _DWORD *a4)
{
  _BYTE *v7; // r12
  int v8; // eax
  signed int v9; // ebx
  FwPolicy2 *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  int v13; // eax
  int v14; // eax
  unsigned int v15; // r14d
  unsigned int kk; // esi
  int v17; // eax
  unsigned int v18; // eax
  int v19; // eax
  __int64 *i; // rsi
  int v21; // eax
  __int64 *j; // rsi
  signed int v23; // eax
  bool v24; // sf
  __int64 *k; // rsi
  unsigned int m; // r14d
  int v27; // eax
  __int64 *n; // rsi
  int v29; // eax
  __int64 *ii; // rsi
  unsigned int jj; // esi
  int v32; // eax
  FwPolicy2 *v33; // rcx
  __int64 v34; // rdx
  unsigned int v35; // ebx
  LSTATUS v37; // eax
  __int128 v38; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h]
  LPCWSTR lpFile; // [rsp+58h] [rbp-A8h]
  unsigned int v41; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+68h] [rbp-98h] BYREF
  __int64 v43; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v44; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v45; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v46; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v47; // [rsp+90h] [rbp-70h] BYREF
  __int64 *v48; // [rsp+98h] [rbp-68h] BYREF
  int v49; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v50[3]; // [rsp+A4h] [rbp-5Ch] BYREF
  void **v51; // [rsp+B0h] [rbp-50h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp-48h]
  __int128 v53; // [rsp+C0h] [rbp-40h]
  _BYTE v54[176]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v55[1024]; // [rsp+180h] [rbp+80h] BYREF

  lpFile = a3;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids);
  v43 = 0;
  v42 = 0;
  v44 = 0;
  v46 = 0;
  v45 = 0;
  v47 = 0;
  v48 = 0;
  v7 = 0;
  v41 = 0;
  v50[0] = 0;
  *a4 = 0;
  memset_0(&v51, 0, 0xD0u);
  v51 = &CTempRegKey::`vftable';
  hKey = 0;
  v53 = 0;
  v8 = CTempRegKey::Init((CTempRegKey *)&v51);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_174;
    v11 = 20;
LABEL_8:
    v12 = (unsigned int)v8;
    goto LABEL_9;
  }
  v8 = FwCreateLocalTempStore(v54, hKey, &v43);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_174;
    v11 = 21;
    goto LABEL_8;
  }
  v13 = FWOpenPolicyStore(0x221u, a1, a2, 1u, 0, &v42);
  v9 = v13;
  if ( v13 > 0 )
    v9 = (unsigned __int16)v13 | 0x80070000;
  if ( v9 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_174;
    v11 = 22;
    goto LABEL_20;
  }
  if ( a2 == 6 )
  {
    v14 = FWChangeTransactionalState(v42, 1);
    v9 = v14;
    if ( v14 > 0 )
      v9 = (unsigned __int16)v14 | 0x80070000;
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_174;
      v11 = 23;
      goto LABEL_20;
    }
  }
  v15 = 0;
LABEL_29:
  if ( v15 >= 3 )
  {
    v19 = FWEnumFirewallRules(v42, 458752, 0x7FFFFFFF, 0, (__int64)&v41, (__int64)&v44);
    v9 = v19;
    if ( v19 > 0 )
      v9 = (unsigned __int16)v19 | 0x80070000;
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_174;
      v11 = 26;
      goto LABEL_20;
    }
    for ( i = v44; i; i = (__int64 *)*i )
    {
      if ( (i[42] & 0x60000) != 0 )
        *a4 = 1;
      if ( (i[42] & 0x40000) == 0 )
      {
        v9 = FwAddRule(v43, 0, i);
        if ( v9 < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_174;
          v11 = 27;
          goto LABEL_20;
        }
      }
    }
    FWFreeFirewallRules(v44);
    v44 = 0;
    v21 = FWEnumConnectionSecurityRules(v42, 458752, 0x7FFFFFFF, 0, (__int64)&v41, (__int64)&v46);
    v9 = v21;
    if ( v21 > 0 )
      v9 = (unsigned __int16)v21 | 0x80070000;
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_174;
      v11 = 28;
      goto LABEL_20;
    }
    for ( j = v46; j; j = (__int64 *)*j )
    {
      if ( (j[48] & 0x60000) != 0 )
        *a4 = 1;
      if ( (j[48] & 0x40000) == 0 )
      {
        v9 = FwAddRule(v43, 1, j);
        if ( v9 < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_174;
          v11 = 29;
          goto LABEL_20;
        }
      }
    }
    FWFreeConnectionSecurityRules(v46);
    v46 = 0;
    v23 = FWEnumMainModeRules(v42, 458752, 0x7FFFFFFF, 0, (__int64)&v41, (__int64)&v45);
    v9 = 0;
    if ( v23 != 50 )
      v9 = v23;
    v24 = v9 < 0;
    if ( v9 > 0 )
    {
      v9 = (unsigned __int16)v9 | 0x80070000;
      v24 = v9 < 0;
    }
    if ( v24 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_174;
      v11 = 30;
      goto LABEL_20;
    }
    for ( k = v45; k; k = (__int64 *)*k )
    {
      if ( (k[32] & 0x60000) != 0 )
        *a4 = 1;
      if ( (k[32] & 0x40000) == 0 )
      {
        v9 = FwAddRule(v43, 2, k);
        if ( v9 < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_174;
          v11 = 31;
          goto LABEL_20;
        }
      }
    }
    FWFreeMainModeRules(v45);
    v45 = 0;
    for ( m = 1; m <= 2; ++m )
    {
      v27 = FWEnumAuthenticationSets(v42, m, 458752, 0, (__int64)&v41, (__int64)&v47);
      v9 = v27;
      if ( v27 > 0 )
        v9 = (unsigned __int16)v27 | 0x80070000;
      if ( v9 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_174;
        v11 = 32;
        goto LABEL_20;
      }
      for ( n = v47; n; n = (__int64 *)*n )
      {
        if ( (n[10] & 0x60000) != 0 )
          *a4 = 1;
        if ( (n[10] & 0x40000) == 0 )
        {
          v9 = FwAddSet(v43, 0, m, n);
          if ( v9 < 0 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_174;
            }
            v11 = 33;
            goto LABEL_20;
          }
        }
      }
      FWFreeAuthenticationSets(v47);
      v47 = 0;
      v29 = FWEnumCryptoSets(v42, m, 458752, 0, (__int64)&v41, (__int64)&v48);
      v9 = v29;
      if ( v29 > 0 )
        v9 = (unsigned __int16)v29 | 0x80070000;
      if ( v9 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_174;
        v11 = 34;
        goto LABEL_20;
      }
      for ( ii = v48; ii; ii = (__int64 *)*ii )
      {
        if ( (ii[11] & 0x60000) != 0 )
          *a4 = 1;
        if ( (ii[11] & 0x40000) == 0 )
        {
          v9 = FwAddSet(v43, 1, m, ii);
          if ( v9 < 0 )
          {
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_174;
            }
            v11 = 35;
            goto LABEL_20;
          }
        }
      }
      FWFreeCryptoSets(v48);
      v48 = 0;
    }
    for ( jj = 1; jj < 0x13; ++jj )
    {
      if ( jj - 1 <= 1 || jj == 11 )
        continue;
      v7 = v55;
      v41 = 1024;
      v9 = 0;
      do
      {
        if ( v9 == 234 )
        {
          if ( v7 != v55 )
            FwBaseFree(v7);
          v7 = (_BYTE *)FwBaseAlloc(v41);
          if ( !v7 )
          {
            v9 = -2147024882;
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_174;
            }
            v11 = 36;
            goto LABEL_20;
          }
        }
        v32 = FWGetGlobalConfig3(v42, jj, 0, (_DWORD)v7, (__int64)&v41, (__int64)v50);
        v9 = v32;
      }
      while ( v32 == 234 );
      if ( v32 != 2 && v32 != 50 )
      {
        if ( v32 > 0 )
          v9 = (unsigned __int16)v32 | 0x80070000;
LABEL_149:
        if ( v9 < 0 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_174;
          v11 = 37;
        }
        else
        {
          if ( !v41 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          if ( jj == 10 && *(_DWORD *)v7 > 0x221u )
          {
            *a4 = 1;
            *(_DWORD *)v7 = 545;
            v41 = 4;
          }
          v9 = FwSetGlobalConfigInLocalTempStore(hKey, jj, v7, v41);
          if ( v9 >= 0 )
          {
            if ( v7 != v55 )
            {
              FwBaseFree(v7);
              v7 = 0;
            }
            continue;
          }
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_174;
          v11 = 38;
        }
LABEL_20:
        v12 = (unsigned int)v9;
LABEL_9:
        WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids, v12);
        goto LABEL_174;
      }
      if ( jj == 10 )
      {
        *(_DWORD *)v7 = 545;
        v41 = 4;
        v9 = 0;
        goto LABEL_149;
      }
    }
    v38 = 0;
    v39 = 0;
    CPrivilegeEnabler::CPrivilegeEnabler((CPrivilegeEnabler *)&v38, 0x11u);
    v9 = DWORD2(v38);
    if ( (SDWORD2(v38) & 0x80000000) == 0 )
    {
      v37 = RegSaveKeyExW(hKey, lpFile, 0, 2u);
      v9 = v37;
      if ( v37 > 0 )
        v9 = (unsigned __int16)v37 | 0x80070000;
      if ( v9 >= 0 )
        goto LABEL_173;
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_173;
      v34 = 40;
    }
    else
    {
      v33 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_173;
      v34 = 39;
    }
    WPP_SF_d(*((_QWORD *)v33 + 2), v34, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids, (unsigned int)v9);
LABEL_173:
    FwReleasePrivilege(v39);
    goto LABEL_174;
  }
  for ( kk = 1; ; ++kk )
  {
    if ( kk >= 0x13 )
    {
      ++v15;
      goto LABEL_29;
    }
    v41 = 1024;
    v49 = 0;
    v17 = FWGetConfig2(v42, kk, *((_DWORD *)qword_18008A2B0 + v15), 0, (__int64)v55, (__int64)&v41, (__int64)&v49);
    v9 = v17;
    if ( v17 == 2 || v17 == 50 )
      continue;
    if ( v17 > 0 )
      v9 = (unsigned __int16)v17 | 0x80070000;
    if ( v9 < 0 )
      break;
    v18 = v41;
    if ( !v41 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v18 = v41;
    }
    v9 = FwSetConfig(v43, kk, *((unsigned int *)qword_18008A2B0 + v15), v55, v18);
    if ( v9 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 25;
        goto LABEL_20;
      }
      goto LABEL_174;
    }
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 24;
    goto LABEL_20;
  }
LABEL_174:
  if ( v43 )
    FwDestroyLocalTempStore();
  if ( v42 )
    FWClosePolicyStore();
  FWFreeFirewallRules(v44);
  FWFreeMainModeRules(v45);
  FWFreeConnectionSecurityRules(v46);
  FWFreeAuthenticationSets(v47);
  FWFreeCryptoSets(v48);
  if ( v7 != v55 )
    FwBaseFree(v7);
  v35 = FwHResultToWindowsError((unsigned int)v9);
  CTempRegKey::~CTempRegKey((CTempRegKey *)&v51);
  return v35;
}

```

## disassembly

```asm
0x180025744  push    rbp
0x180025746  push    rbx
0x180025747  push    rsi
0x180025748  push    rdi
0x180025749  push    r12
0x18002574b  push    r13
0x18002574d  push    r14
0x18002574f  push    r15
0x180025751  lea     rbp, [rsp-498h]
0x180025759  sub     rsp, 598h
0x180025760  mov     rax, cs:__security_cookie
0x180025767  xor     rax, rsp
0x18002576a  mov     [rbp+4D0h+var_50], rax
0x180025771  mov     r13, r9
0x180025774  mov     [rsp+5D0h+lpFile], r8
0x180025779  mov     esi, edx
0x18002577b  mov     r14, rcx
0x18002577e  lea     rdi, WPP_GLOBAL_Control
0x180025785  mov     rcx, cs:WPP_GLOBAL_Control
0x18002578c  cmp     rcx, rdi
0x18002578f  jz      short loc_1800257AC
0x180025791  test    byte ptr [rcx+1Ch], 8
0x180025795  jz      short loc_1800257AC
0x180025797  mov     edx, 13h
0x18002579c  lea     r8, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids
0x1800257a3  mov     rcx, [rcx+10h]
0x1800257a7  call    WPP_SF_
0x1800257ac  xor     r15d, r15d
0x1800257af  mov     [rsp+5D0h+var_560], r15
0x1800257b4  mov     [rsp+5D0h+var_568], r15
0x1800257b9  mov     [rsp+5D0h+var_558], r15
0x1800257be  mov     [rbp+4D0h+var_548], r15
0x1800257c2  mov     [rbp+4D0h+var_550], r15
0x1800257c6  mov     [rbp+4D0h+var_540], r15
0x1800257ca  mov     [rbp+4D0h+var_538], r15
0x1800257ce  mov     r12d, r15d
0x1800257d1  mov     [rsp+5D0h+var_570], r15d
0x1800257d6  mov     [rbp+4D0h+var_52C], r15d
0x1800257da  mov     [r13+0], r15d
0x1800257de  xor     edx, edx; Val
0x1800257e0  mov     r8d, 0D0h; Size
0x1800257e6  lea     rcx, [rbp+4D0h+var_520]; void *
0x1800257ea  call    memset_0
0x1800257ef  lea     rax, ??_7CTempRegKey@@6B@; const CTempRegKey::`vftable'
0x1800257f6  mov     [rbp+4D0h+var_520], rax
0x1800257fa  mov     [rbp+4D0h+hKey], r15
0x1800257fe  xorps   xmm0, xmm0
0x180025801  movdqa  [rbp+4D0h+var_510], xmm0
0x180025806  lea     rcx, [rbp+4D0h+var_520]; this
0x18002580a  call    ?Init@CTempRegKey@@QEAAJXZ; CTempRegKey::Init(void)
0x18002580f  mov     ebx, eax
0x180025811  test    eax, eax
0x180025813  jns     short loc_18002584E
0x180025815  mov     rcx, cs:WPP_GLOBAL_Control
0x18002581c  cmp     rcx, rdi
0x18002581f  jz      loc_1800260FC
0x180025825  lea     edi, [r15+1]
0x180025829  test    [rcx+1Ch], dil
0x18002582d  jz      loc_1800260FC
0x180025833  lea     edx, [rdi+13h]
0x180025836  mov     r9d, eax
0x180025839  lea     r8, WPP_2f6b21c908e13dc8e0666271515fc0dc_Traceguids
0x180025840  mov     rcx, [rcx+10h]
0x180025844  call    WPP_SF_d
0x180025849  jmp     loc_1800260FC
0x18002584e  lea     r8, [rsp+5D0h+var_560]
0x180025853  mov     rdx, [rbp+4D0h+hKey]
0x180025857  lea     rcx, [rbp+4D0h+var_500]
0x18002585b  call    cs:__imp_FwCreateLocalTempStore
0x180025861  mov     ebx, eax
0x180025863  test    eax, eax
0x180025865  jns     short loc_18002588B
0x180025867  mov     rcx, cs:WPP_GLOBAL_Control
0x18002586e  cmp     rcx, rdi
0x180025871  jz      loc_1800260FC
0x180025877  mov     edi, 1
0x18002587c  test    [rcx+1Ch], dil
0x180025880  jz      loc_1800260FC
0x180025886  lea     edx, [rdi+14h]
0x180025889  jmp     short loc_180025836
0x18002588b  mov     ecx, 221h
0x180025890  lea     rax, [rsp+5D0h+var_568]
0x180025895  mov     [rsp+5D0h+var_5A8], rax
0x18002589a  mov     dword ptr [rsp+5D0h+var_5B0], r15d
0x18002589f  mov     edi, 1
0x1800258a4  mov     r9d, edi
0x1800258a7  mov     r8d, esi
0x1800258aa  mov     rdx, r14
0x1800258ad  call    FWOpenPolicyStore
0x1800258b2  mov     ebx, eax
0x1800258b4  mov     r14d, 80070000h
0x1800258ba  test    eax, eax
0x1800258bc  jle     short loc_1800258C4
0x1800258be  movzx   ebx, ax
0x1800258c1  or      ebx, r14d
0x1800258c4  test    ebx, ebx
0x1800258c6  jns     short loc_1800258F6
0x1800258c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800258cf  lea     rax, WPP_GLOBAL_Control
0x1800258d6  cmp     rcx, rax
0x1800258d9  jz      loc_1800260FC
0x1800258df  test    [rcx+1Ch], dil
0x1800258e3  jz      loc_1800260FC
0x1800258e9  mov     edx, 16h
0x1800258ee  mov     r9d, ebx
0x1800258f1  jmp     loc_180025839
0x1800258f6  cmp     esi, 6
0x1800258f9  jnz     short loc_18002593F
0x1800258fb  mov     edx, edi
0x1800258fd  mov     rcx, [rsp+5D0h+var_568]
0x180025902  call    FWChangeTransactionalState
0x180025907  mov     ebx, eax
0x180025909  test    eax, eax
0x18002590b  jle     short loc_180025913
0x18002590d  movzx   ebx, ax
0x180025910  or      ebx, r14d
0x180025913  test    ebx, ebx
0x180025915  jns     short loc_18002593F
0x180025917  mov     rcx, cs:WPP_GLOBAL_Control
0x18002591e  lea     rax, WPP_GLOBAL_Control
0x180025925  cmp     rcx, rax
0x180025928  jz      loc_1800260FC
0x18002592e  test    [rcx+1Ch], dil
0x180025932  jz      loc_1800260FC
0x180025938  mov     edx, 17h
0x18002593d  jmp     short loc_1800258EE
0x18002593f  mov     r14d, r15d
0x180025942  cmp     r14d, 3
0x180025946  jnb     loc_180025A63
0x18002594c  mov     esi, edi
0x18002594e  cmp     esi, 13h
0x180025951  jnb     loc_180025A30
0x180025957  mov     [rsp+5D0h+var_570], 400h
0x18002595f  mov     r15d, r14d
0x180025962  lea     rcx, qword_18008A2B0
0x180025969  mov     [rbp+4D0h+var_530], 0
0x180025970  lea     rax, [rbp+4D0h+var_530]
0x180025974  mov     [rsp+5D0h+var_5A0], rax
0x180025979  lea     rax, [rsp+5D0h+var_570]
0x18002597e  mov     [rsp+5D0h+var_5A8], rax
0x180025983  lea     rax, [rbp+4D0h+var_450]
0x18002598a  mov     [rsp+5D0h+var_5B0], rax
0x18002598f  xor     r9d, r9d
0x180025992  mov     r8d, [rcx+r15*4]
0x180025996  mov     edx, esi
0x180025998  mov     rcx, [rsp+5D0h+var_568]
0x18002599d  call    FWGetConfig2
0x1800259a2  mov     ebx, eax
0x1800259a4  cmp     eax, 2
0x1800259a7  jz      short loc_180025A26
0x1800259a9  cmp     eax, 32h ; '2'
0x1800259ac  jz      short loc_180025A26
0x1800259ae  test    eax, eax
0x1800259b0  jle     short loc_1800259BB
0x1800259b2  movzx   ebx, ax
0x1800259b5  or      ebx, 80070000h
0x1800259bb  test    ebx, ebx
0x1800259bd  js      short loc_180025A38
0x1800259bf  mov     eax, [rsp+5D0h+var_570]
0x1800259c3  test    eax, eax
0x1800259c5  jnz     short loc_1800259D0
0x1800259c7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800259cc  mov     eax, [rsp+5D0h+var_570]
0x1800259d0  mov     dword ptr [rsp+5D0h+var_5B0], eax
0x1800259d4  lea     r9, [rbp+4D0h+var_450]
0x1800259db  lea     r8, qword_18008A2B0
0x1800259e2  mov     r8d, [r8+r15*4]
0x1800259e6  mov     edx, esi
0x1800259e8  mov     rcx, [rsp+5D0h+var_560]
0x1800259ed  call    cs:__imp_FwSetConfig
0x1800259f3  mov     ebx, eax
0x1800259f5  xor     r15d, r15d
0x1800259f8  test    eax, eax
0x1800259fa  jns     short loc_180025A29
0x1800259fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a03  lea     rax, WPP_GLOBAL_Control
0x180025a0a  cmp     rcx, rax
0x180025a0d  jz      loc_1800260FC
0x180025a13  test    [rcx+1Ch], dil
0x180025a17  jz      loc_1800260FC
0x180025a1d  lea     edx, [r15+19h]
0x180025a21  jmp     loc_1800258EE
0x180025a26  xor     r15d, r15d
0x180025a29  add     esi, edi
0x180025a2b  jmp     loc_18002594E
0x180025a30  add     r14d, edi
0x180025a33  jmp     loc_180025942
0x180025a38  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a3f  lea     rax, WPP_GLOBAL_Control
0x180025a46  cmp     rcx, rax
0x180025a49  jz      loc_1800260FC
0x180025a4f  test    [rcx+1Ch], dil
0x180025a53  jz      loc_1800260FC
0x180025a59  mov     edx, 18h
0x180025a5e  jmp     loc_1800258EE
0x180025a63  xor     r9d, r9d
0x180025a66  lea     rax, [rsp+5D0h+var_558]
0x180025a6b  mov     [rsp+5D0h+var_5A8], rax
0x180025a70  lea     rax, [rsp+5D0h+var_570]
0x180025a75  mov     [rsp+5D0h+var_5B0], rax
0x180025a7a  mov     r14d, 7FFFFFFFh
0x180025a80  mov     r8d, r14d
0x180025a83  mov     edx, 70000h
0x180025a88  mov     rcx, [rsp+5D0h+var_568]
0x180025a8d  call    FWEnumFirewallRules
0x180025a92  mov     ebx, eax
0x180025a94  test    eax, eax
0x180025a96  jle     short loc_180025AA1
0x180025a98  movzx   ebx, ax
0x180025a9b  or      ebx, 80070000h
0x180025aa1  test    ebx, ebx
0x180025aa3  jns     short loc_180025AD0
0x180025aa5  mov     rcx, cs:WPP_GLOBAL_Control
0x180025aac  lea     rax, WPP_GLOBAL_Control
0x180025ab3  cmp     rcx, rax
0x180025ab6  jz      loc_1800260FC
0x180025abc  test    [rcx+1Ch], dil
0x180025ac0  jz      loc_1800260FC
0x180025ac6  mov     edx, 1Ah
0x180025acb  jmp     loc_1800258EE
0x180025ad0  mov     rsi, [rsp+5D0h+var_558]
0x180025ad5  test    rsi, rsi
0x180025ad8  jz      short loc_180025B3C
0x180025ada  test    dword ptr [rsi+150h], 60000h
0x180025ae4  jz      short loc_180025AEA
0x180025ae6  mov     [r13+0], edi
0x180025aea  test    dword ptr [rsi+150h], 40000h
0x180025af4  jnz     short loc_180025B0C
0x180025af6  mov     r8, rsi
0x180025af9  xor     edx, edx
0x180025afb  mov     rcx, [rsp+5D0h+var_560]
0x180025b00  call    cs:__imp_FwAddRule
0x180025b06  mov     ebx, eax
0x180025b08  test    eax, eax
0x180025b0a  js      short loc_180025B11
0x180025b0c  mov     rsi, [rsi]
0x180025b0f  jmp     short loc_180025AD5
0x180025b11  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b18  lea     rax, WPP_GLOBAL_Control
0x180025b1f  cmp     rcx, rax
0x180025b22  jz      loc_1800260FC
0x180025b28  test    [rcx+1Ch], dil
0x180025b2c  jz      loc_1800260FC
0x180025b32  mov     edx, 1Bh
0x180025b37  jmp     loc_1800258EE
0x180025b3c  mov     rcx, [rsp+5D0h+var_558]
0x180025b41  call    FWFreeFirewallRules
0x180025b46  mov     [rsp+5D0h+var_558], r15
0x180025b4b  xor     r9d, r9d
0x180025b4e  lea     rax, [rbp+4D0h+var_548]
0x180025b52  mov     [rsp+5D0h+var_5A8], rax
0x180025b57  lea     rax, [rsp+5D0h+var_570]
0x180025b5c  mov     [rsp+5D0h+var_5B0], rax
0x180025b61  mov     r8d, r14d
0x180025b64  mov     edx, 70000h
0x180025b69  mov     rcx, [rsp+5D0h+var_568]
0x180025b6e  call    FWEnumConnectionSecurityRules
0x180025b73  mov     ebx, eax
0x180025b75  test    eax, eax
0x180025b77  jle     short loc_180025B82
0x180025b79  movzx   ebx, ax
0x180025b7c  or      ebx, 80070000h
0x180025b82  test    ebx, ebx
0x180025b84  jns     short loc_180025BB1
0x180025b86  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b8d  lea     rax, WPP_GLOBAL_Control
0x180025b94  cmp     rcx, rax
0x180025b97  jz      loc_1800260FC
0x180025b9d  test    [rcx+1Ch], dil
0x180025ba1  jz      loc_1800260FC
0x180025ba7  mov     edx, 1Ch
0x180025bac  jmp     loc_1800258EE
0x180025bb1  mov     rsi, [rbp+4D0h+var_548]
0x180025bb5  test    rsi, rsi
0x180025bb8  jz      short loc_180025C1C
0x180025bba  test    dword ptr [rsi+180h], 60000h
0x180025bc4  jz      short loc_180025BCA
0x180025bc6  mov     [r13+0], edi
0x180025bca  test    dword ptr [rsi+180h], 40000h
0x180025bd4  jnz     short loc_180025BEC
0x180025bd6  mov     r8, rsi
0x180025bd9  mov     edx, edi
0x180025bdb  mov     rcx, [rsp+5D0h+var_560]
0x180025be0  call    cs:__imp_FwAddRule
0x180025be6  mov     ebx, eax
0x180025be8  test    eax, eax
0x180025bea  js      short loc_180025BF1
0x180025bec  mov     rsi, [rsi]
0x180025bef  jmp     short loc_180025BB5
0x180025bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180025bf8  lea     rax, WPP_GLOBAL_Control
0x180025bff  cmp     rcx, rax
0x180025c02  jz      loc_1800260FC
0x180025c08  test    [rcx+1Ch], dil
0x180025c0c  jz      loc_1800260FC
0x180025c12  mov     edx, 1Dh
0x180025c17  jmp     loc_1800258EE
0x180025c1c  mov     rcx, [rbp+4D0h+var_548]
0x180025c20  call    FWFreeConnectionSecurityRules
0x180025c25  mov     [rbp+4D0h+var_548], r15
  ... truncated ...
```
