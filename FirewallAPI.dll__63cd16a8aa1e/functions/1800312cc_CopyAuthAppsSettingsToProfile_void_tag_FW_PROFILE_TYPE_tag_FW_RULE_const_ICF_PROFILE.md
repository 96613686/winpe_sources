# CopyAuthAppsSettingsToProfile(void *,_tag_FW_PROFILE_TYPE,_tag_FW_RULE const *,ICF_PROFILE_ *)

- ea: `0x1800312cc`
- end: `0x180031767`
- name: `?CopyAuthAppsSettingsToProfile@@YAKPEAXW4_tag_FW_PROFILE_TYPE@@PEBU_tag_FW_RULE@@PEAUICF_PROFILE_@@@Z`
- size: `1179`
- prototype: `unsigned int __high(void *, enum _tag_FW_PROFILE_TYPE, const struct _tag_FW_RULE *, struct ICF_PROFILE_ *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032f90`

## callees

- `0x180005954`
- `0x180008a10`
- `0x18001cdb4`
- `0x1800277b0`
- `0x18003104c`
- `0x180031080`
- `0x180031160`
- `0x1800312cc`
- `0x1800324d8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031550`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031550`
- `fwbase!FwBaseAlloc` at `0x180031493`
- `fwbase!FwBaseAlloc` at `0x180031493`
- `fwbase!FwBaseFree` at `0x180031568`
- `fwbase!FwBaseFree` at `0x1800316e7`
- `fwbase!FwBaseFree` at `0x180031568`
- `fwbase!FwBaseFree` at `0x1800316e7`
- `fwbase!FwSizeTMultiply` at `0x180031481`
- `fwbase!FwSizeTMultiply` at `0x180031481`
- `fwbase!FwHResultToWindowsError` at `0x18003134f`
- `fwbase!FwHResultToWindowsError` at `0x180031727`
- `fwbase!FwHResultToWindowsError` at `0x18003134f`
- `fwbase!FwHResultToWindowsError` at `0x180031727`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x1800314f5`
- `fwbase!FwGetExpandedCanonicalLongPathName` at `0x1800314f5`
- `fwbase!IsRuleOldAuthApp` at `0x180031448`
- `fwbase!IsRuleOldAuthApp` at `0x1800314d8`
- `fwbase!IsRuleOldAuthApp` at `0x180031448`
- `fwbase!IsRuleOldAuthApp` at `0x1800314d8`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x18003143b`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x1800314c7`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x18003143b`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x1800314c7`
- `fwbase!FwStringCopy` at `0x18003159b`
- `fwbase!FwStringCopy` at `0x1800315bc`
- `fwbase!FwStringCopy` at `0x18003159b`
- `fwbase!FwStringCopy` at `0x1800315bc`

## pseudocode

```c
__int64 __fastcall CopyAuthAppsSettingsToProfile(int a1, int a2, __int64 *a3, __int64 a4)
{
  int v6; // r14d
  int CurrentProfile; // eax
  unsigned int v9; // eax
  unsigned int v10; // edi
  unsigned int v12; // r14d
  int v13; // eax
  FwPolicy2 *v14; // rcx
  __int64 v15; // rdx
  _QWORD *v16; // r14
  unsigned int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // r12d
  int ExpandedCanonicalLongPathName; // r14d
  const WCHAR *lpString2; // rdx
  unsigned int i; // r14d
  __int64 v23; // r14
  int v24; // eax
  __int64 v25; // rcx
  unsigned int v26; // r15d
  __int64 v27; // rcx
  PCNZWCH v28; // [rsp+40h] [rbp-30h] BYREF
  __int64 v29; // [rsp+48h] [rbp-28h] BYREF
  int v30; // [rsp+50h] [rbp-20h] BYREF
  int v31; // [rsp+58h] [rbp-18h] BYREF
  int v32; // [rsp+5Ch] [rbp-14h] BYREF

  v30 = a2;
  v31 = 0;
  v6 = a2;
  v32 = 4;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids);
  if ( v6 == 0x80000000 )
  {
    CurrentProfile = FwGetCurrentProfile((enum _tag_FW_PROFILE_TYPE *)&v30);
    if ( CurrentProfile < 0 )
    {
      v9 = FwHResultToWindowsError((unsigned int)CurrentProfile);
      v10 = v9;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids, v9);
      return v10;
    }
    v6 = v30;
  }
  *(_DWORD *)(a4 + 232) = 2;
  v30 = 0;
  v12 = FWGetConfig2(a1, 11, v6, 1, (__int64)&v31, (__int64)&v32, (__int64)&v30);
  if ( v12 == 50 )
  {
    v13 = 1;
    v31 = 1;
  }
  else
  {
    if ( v12 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 31;
LABEL_17:
        WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids, v12);
      }
      return v12;
    }
    v13 = v31;
  }
  *(_DWORD *)(a4 + 216) = 0;
  v16 = a3;
  for ( *(_DWORD *)(a4 + 236) = (v13 != 0) + 1; v16; v16 = (_QWORD *)*v16 )
  {
    if ( (unsigned int)IsRuleOpenPortOrAuthApp(v16) && (unsigned int)IsRuleOldAuthApp(v16) )
      ++*(_DWORD *)(a4 + 216);
  }
  v17 = *(_DWORD *)(a4 + 216);
  if ( v17 )
  {
    v29 = 0;
    if ( (int)FwSizeTMultiply(112, v17, &v29) >= 0 )
    {
      v18 = FwBaseAlloc(v29);
      *(_QWORD *)(a4 + 224) = v18;
      if ( v18 )
      {
        v19 = 0;
        while ( 1 )
        {
          if ( !a3 )
          {
            *(_DWORD *)(a4 + 216) = v19;
            return 0;
          }
          v28 = 0;
          v30 = 0;
          if ( (unsigned int)IsRuleOpenPortOrAuthApp(a3) && (unsigned int)IsRuleOldAuthApp(a3) )
          {
            ExpandedCanonicalLongPathName = FwGetExpandedCanonicalLongPathName(a3[34], &v28, &v30);
            if ( ExpandedCanonicalLongPathName < 0 )
            {
              if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  32,
                  WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids,
                  (unsigned int)ExpandedCanonicalLongPathName);
              }
              v27 = (unsigned int)ExpandedCanonicalLongPathName;
              return FwHResultToWindowsError(v27);
            }
            lpString2 = v28;
            if ( !v30 || !v28 )
            {
              if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids);
                lpString2 = v28;
              }
              FwBaseFree(lpString2);
              return 31;
            }
            for ( i = 0; i < v19; ++i )
            {
              if ( CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(112LL * i + *(_QWORD *)(a4 + 224) + 16), -1, lpString2, -1) == 2 )
              {
                FwBaseFree(v28);
                goto LABEL_46;
              }
              lpString2 = v28;
            }
            v23 = 112LL * v19;
            *(_QWORD *)(v23 + *(_QWORD *)(a4 + 224) + 16) = lpString2;
            v24 = FwStringCopy(a3[34], v23 + *(_QWORD *)(a4 + 224) + 8LL);
            if ( v24 < 0 || (v25 = a3[3]) != 0 && (v24 = FwStringCopy(v25, v23 + *(_QWORD *)(a4 + 224)), v24 < 0) )
            {
              v27 = (unsigned int)v24;
              return FwHResultToWindowsError(v27);
            }
            *(_DWORD *)(v23 + *(_QWORD *)(a4 + 224) + 104) = IsRuleEnabled((const struct _tag_FW_RULE *)a3);
            *(_DWORD *)(v23 + *(_QWORD *)(a4 + 224) + 108) = *((_DWORD *)a3 + 85) == 1;
            v26 = CopySubnetRestrictions(
                    (const struct _tag_FW_RULE *)a3,
                    (struct ICF_SUBNETS_ *)(v23 + *(_QWORD *)(a4 + 224) + 24LL),
                    (struct ICF_SUBNETS6_ *)(v23 + *(_QWORD *)(a4 + 224) + 48LL));
            if ( v26 )
            {
              if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids, v26);
              }
              return v26;
            }
            v12 = CopyAddrRanges(
                    (const struct _tag_FW_RULE *)a3,
                    (struct ICF_RANGES_ *)(v23 + *(_QWORD *)(a4 + 224) + 72LL),
                    (struct ICF_RANGES6_ *)(v23 + *(_QWORD *)(a4 + 224) + 88LL));
            if ( v12 )
            {
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v15 = 35;
                goto LABEL_17;
              }
              return v12;
            }
            ++v19;
          }
LABEL_46:
          a3 = (__int64 *)*a3;
        }
      }
    }
    return 8;
  }
  else
  {
    *(_QWORD *)(a4 + 224) = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x1800312cc  push    rbp
0x1800312ce  push    rbx
0x1800312cf  push    rsi
0x1800312d0  push    rdi
0x1800312d1  push    r12
0x1800312d3  push    r14
0x1800312d5  push    r15
0x1800312d7  mov     rbp, rsp
0x1800312da  sub     rsp, 70h
0x1800312de  mov     rax, cs:__security_cookie
0x1800312e5  xor     rax, rsp
0x1800312e8  mov     [rbp+var_10], rax
0x1800312ec  mov     rdi, r9
0x1800312ef  mov     [rbp+var_20], edx
0x1800312f2  mov     rsi, r8
0x1800312f5  mov     [rbp+var_18], 0
0x1800312fc  mov     r14d, edx
0x1800312ff  mov     [rbp+var_14], 4
0x180031306  mov     r15, rcx
0x180031309  mov     rcx, cs:WPP_GLOBAL_Control
0x180031310  lea     r12, WPP_GLOBAL_Control
0x180031317  cmp     rcx, r12
0x18003131a  jz      short loc_180031337
0x18003131c  test    byte ptr [rcx+1Ch], 8
0x180031320  jz      short loc_180031337
0x180031322  mov     rcx, [rcx+10h]
0x180031326  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x18003132d  mov     edx, 1Dh
0x180031332  call    WPP_SF_
0x180031337  cmp     r14d, 80000000h
0x18003133e  jnz     short loc_18003138E
0x180031340  lea     rcx, [rbp+var_20]; enum _tag_FW_PROFILE_TYPE *
0x180031344  call    ?FwGetCurrentProfile@@YAJPEAW4_tag_FW_PROFILE_TYPE@@@Z; FwGetCurrentProfile(_tag_FW_PROFILE_TYPE *)
0x180031349  test    eax, eax
0x18003134b  jns     short loc_18003138A
0x18003134d  mov     ecx, eax
0x18003134f  call    cs:__imp_FwHResultToWindowsError
0x180031355  mov     edi, eax
0x180031357  mov     rcx, cs:WPP_GLOBAL_Control
0x18003135e  cmp     rcx, r12
0x180031361  jz      short loc_180031383
0x180031363  mov     ebx, 1
0x180031368  test    [rcx+1Ch], bl
0x18003136b  jz      short loc_180031383
0x18003136d  mov     rcx, [rcx+10h]
0x180031371  lea     edx, [rbx+1Dh]
0x180031374  mov     r9d, eax
0x180031377  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x18003137e  call    WPP_SF_d
0x180031383  mov     eax, edi
0x180031385  jmp     loc_18003174C
0x18003138a  mov     r14d, [rbp+var_20]
0x18003138e  lea     rax, [rbp+var_20]
0x180031392  mov     dword ptr [rdi+0E8h], 2
0x18003139c  mov     [rsp+70h+var_40], rax
0x1800313a1  mov     ebx, 1
0x1800313a6  lea     rax, [rbp+var_14]
0x1800313aa  mov     [rbp+var_20], 0
0x1800313b1  mov     qword ptr [rsp+70h+cchCount2], rax
0x1800313b6  mov     r9d, ebx
0x1800313b9  lea     rax, [rbp+var_18]
0x1800313bd  mov     r8d, r14d
0x1800313c0  lea     edx, [rbx+0Ah]
0x1800313c3  mov     [rsp+70h+lpString2], rax
0x1800313c8  mov     rcx, r15
0x1800313cb  call    FWGetConfig2
0x1800313d0  mov     r14d, eax
0x1800313d3  cmp     eax, 32h ; '2'
0x1800313d6  jnz     short loc_1800313DF
0x1800313d8  mov     eax, ebx
0x1800313da  mov     [rbp+var_18], ebx
0x1800313dd  jmp     short loc_180031418
0x1800313df  test    r14d, r14d
0x1800313e2  jz      short loc_180031415
0x1800313e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800313eb  cmp     rcx, r12
0x1800313ee  jz      short loc_18003140D
0x1800313f0  test    [rcx+1Ch], bl
0x1800313f3  jz      short loc_18003140D
0x1800313f5  mov     edx, 1Fh
0x1800313fa  mov     rcx, [rcx+10h]
0x1800313fe  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x180031405  mov     r9d, r14d
0x180031408  call    WPP_SF_d
0x18003140d  mov     eax, r14d
0x180031410  jmp     loc_18003174C
0x180031415  mov     eax, [rbp+var_18]
0x180031418  neg     eax
0x18003141a  mov     dword ptr [rdi+0D8h], 0
0x180031424  mov     r14, rsi
0x180031427  sbb     eax, eax
0x180031429  neg     eax
0x18003142b  add     eax, ebx
0x18003142d  mov     [rdi+0ECh], eax
0x180031433  test    rsi, rsi
0x180031436  jz      short loc_180031460
0x180031438  mov     rcx, r14
0x18003143b  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180031441  test    eax, eax
0x180031443  jz      short loc_180031458
0x180031445  mov     rcx, r14
0x180031448  call    cs:__imp_IsRuleOldAuthApp
0x18003144e  test    eax, eax
0x180031450  jz      short loc_180031458
0x180031452  add     [rdi+0D8h], ebx
0x180031458  mov     r14, [r14]
0x18003145b  test    r14, r14
0x18003145e  jnz     short loc_180031438
0x180031460  mov     eax, [rdi+0D8h]
0x180031466  test    eax, eax
0x180031468  jz      loc_18003173F
0x18003146e  mov     edx, eax
0x180031470  mov     [rbp+var_28], 0
0x180031478  lea     r8, [rbp+var_28]
0x18003147c  mov     ecx, 70h ; 'p'
0x180031481  call    cs:__imp_FwSizeTMultiply
0x180031487  test    eax, eax
0x180031489  js      loc_180031738
0x18003148f  mov     rcx, [rbp+var_28]
0x180031493  call    cs:__imp_FwBaseAlloc
0x180031499  mov     [rdi+0E0h], rax
0x1800314a0  test    rax, rax
0x1800314a3  jz      loc_180031738
0x1800314a9  xor     r12d, r12d
0x1800314ac  test    rsi, rsi
0x1800314af  jz      loc_18003172F
0x1800314b5  mov     rcx, rsi
0x1800314b8  mov     [rbp+var_30], 0
0x1800314c0  mov     [rbp+var_20], 0
0x1800314c7  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x1800314cd  test    eax, eax
0x1800314cf  jz      loc_180031645
0x1800314d5  mov     rcx, rsi
0x1800314d8  call    cs:__imp_IsRuleOldAuthApp
0x1800314de  test    eax, eax
0x1800314e0  jz      loc_180031645
0x1800314e6  mov     rcx, [rsi+110h]
0x1800314ed  lea     r8, [rbp+var_20]
0x1800314f1  lea     rdx, [rbp+var_30]
0x1800314f5  call    cs:__imp_FwGetExpandedCanonicalLongPathName
0x1800314fb  mov     r14d, eax
0x1800314fe  test    eax, eax
0x180031500  js      loc_1800316F4
0x180031506  cmp     [rbp+var_20], 0
0x18003150a  mov     rdx, [rbp+var_30]
0x18003150e  jz      loc_1800316B3
0x180031514  test    rdx, rdx
0x180031517  jz      loc_1800316B3
0x18003151d  xor     r14d, r14d
0x180031520  cmp     r14d, r12d
0x180031523  jnb     short loc_180031573
0x180031525  mov     r8, [rdi+0E0h]
0x18003152c  or      r9d, 0FFFFFFFFh; cchCount1
0x180031530  mov     eax, r14d
0x180031533  imul    rcx, rax, 70h ; 'p'
0x180031537  mov     [rsp+70h+cchCount2], 0FFFFFFFFh; cchCount2
0x18003153f  mov     [rsp+70h+lpString2], rdx; lpString2
0x180031544  mov     edx, ebx; dwCmpFlags
0x180031546  mov     r8, [rcx+r8+10h]; lpString1
0x18003154b  mov     ecx, 7Fh; Locale
0x180031550  call    cs:__imp_CompareStringW
0x180031556  cmp     eax, 2
0x180031559  jz      short loc_180031564
0x18003155b  mov     rdx, [rbp+var_30]
0x18003155f  add     r14d, ebx
0x180031562  jmp     short loc_180031520
0x180031564  mov     rcx, [rbp+var_30]
0x180031568  call    cs:__imp_FwBaseFree
0x18003156e  jmp     loc_180031645
0x180031573  mov     eax, r12d
0x180031576  imul    r14, rax, 70h ; 'p'
0x18003157a  mov     rax, [rdi+0E0h]
0x180031581  mov     [r14+rax+10h], rdx
0x180031586  mov     rdx, [rdi+0E0h]
0x18003158d  mov     rcx, [rsi+110h]
0x180031594  add     rdx, 8
0x180031598  add     rdx, r14
0x18003159b  call    cs:__imp_FwStringCopy
0x1800315a1  test    eax, eax
0x1800315a3  js      loc_1800316AF
0x1800315a9  mov     rcx, [rsi+18h]
0x1800315ad  test    rcx, rcx
0x1800315b0  jz      short loc_1800315CA
0x1800315b2  mov     rdx, [rdi+0E0h]
0x1800315b9  add     rdx, r14
0x1800315bc  call    cs:__imp_FwStringCopy
0x1800315c2  test    eax, eax
0x1800315c4  js      loc_1800316AF
0x1800315ca  mov     rcx, rsi; struct _tag_FW_RULE *
0x1800315cd  call    ?IsRuleEnabled@@YAHPEBU_tag_FW_RULE@@@Z; IsRuleEnabled(_tag_FW_RULE const *)
0x1800315d2  mov     ecx, eax
0x1800315d4  mov     rax, [rdi+0E0h]
0x1800315db  mov     [r14+rax+68h], ecx
0x1800315e0  mov     rcx, [rdi+0E0h]
0x1800315e7  cmp     [rsi+154h], ebx
0x1800315ed  jnz     short loc_1800315F3
0x1800315ef  mov     eax, ebx
0x1800315f1  jmp     short loc_1800315F5
0x1800315f3  xor     eax, eax
0x1800315f5  mov     [r14+rcx+6Ch], eax
0x1800315fa  mov     rcx, rsi; struct _tag_FW_RULE *
0x1800315fd  mov     rax, [rdi+0E0h]
0x180031604  lea     r8, [rax+30h]
0x180031608  lea     rdx, [rax+18h]
0x18003160c  add     r8, r14; struct ICF_SUBNETS6_ *
0x18003160f  add     rdx, r14; struct ICF_SUBNETS_ *
0x180031612  call    ?CopySubnetRestrictions@@YAKPEBU_tag_FW_RULE@@PEAUICF_SUBNETS_@@PEAUICF_SUBNETS6_@@@Z; CopySubnetRestrictions(_tag_FW_RULE const *,ICF_SUBNETS_ *,ICF_SUBNETS6_ *)
0x180031617  mov     r15d, eax
0x18003161a  test    eax, eax
0x18003161c  jnz     short loc_180031677
0x18003161e  mov     rax, [rdi+0E0h]
0x180031625  mov     rcx, rsi; struct _tag_FW_RULE *
0x180031628  lea     r8, [rax+58h]
0x18003162c  lea     rdx, [rax+48h]
0x180031630  add     r8, r14; struct ICF_RANGES6_ *
0x180031633  add     rdx, r14; struct ICF_RANGES_ *
0x180031636  call    ?CopyAddrRanges@@YAKPEBU_tag_FW_RULE@@PEAUICF_RANGES_@@PEAUICF_RANGES6_@@@Z; CopyAddrRanges(_tag_FW_RULE const *,ICF_RANGES_ *,ICF_RANGES6_ *)
0x18003163b  mov     r14d, eax
0x18003163e  test    eax, eax
0x180031640  jnz     short loc_18003164D
0x180031642  add     r12d, ebx
0x180031645  mov     rsi, [rsi]
0x180031648  jmp     loc_1800314AC
0x18003164d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031654  lea     rax, WPP_GLOBAL_Control
0x18003165b  cmp     rcx, rax
0x18003165e  jz      loc_18003140D
0x180031664  test    [rcx+1Ch], bl
0x180031667  jz      loc_18003140D
0x18003166d  mov     edx, 23h ; '#'
0x180031672  jmp     loc_1800313FA
0x180031677  mov     rcx, cs:WPP_GLOBAL_Control
0x18003167e  lea     rax, WPP_GLOBAL_Control
0x180031685  cmp     rcx, rax
0x180031688  jz      short loc_1800316A7
0x18003168a  test    [rcx+1Ch], bl
0x18003168d  jz      short loc_1800316A7
0x18003168f  mov     rcx, [rcx+10h]
0x180031693  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x18003169a  mov     edx, 22h ; '"'
0x18003169f  mov     r9d, r15d
0x1800316a2  call    WPP_SF_d
0x1800316a7  mov     eax, r15d
0x1800316aa  jmp     loc_18003174C
0x1800316af  mov     ecx, eax
0x1800316b1  jmp     short loc_180031727
0x1800316b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800316ba  lea     rax, WPP_GLOBAL_Control
0x1800316c1  cmp     rcx, rax
0x1800316c4  jz      short loc_1800316E4
0x1800316c6  test    [rcx+1Ch], bl
0x1800316c9  jz      short loc_1800316E4
0x1800316cb  mov     rcx, [rcx+10h]
0x1800316cf  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x1800316d6  mov     edx, 21h ; '!'
0x1800316db  call    WPP_SF_
0x1800316e0  mov     rdx, [rbp+var_30]
0x1800316e4  mov     rcx, rdx
0x1800316e7  call    cs:__imp_FwBaseFree
0x1800316ed  mov     eax, 1Fh
0x1800316f2  jmp     short loc_18003174C
0x1800316f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800316fb  lea     rax, WPP_GLOBAL_Control
0x180031702  cmp     rcx, rax
0x180031705  jz      short loc_180031724
0x180031707  test    [rcx+1Ch], bl
0x18003170a  jz      short loc_180031724
0x18003170c  mov     rcx, [rcx+10h]
0x180031710  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x180031717  mov     edx, 20h ; ' '
0x18003171c  mov     r9d, r14d
0x18003171f  call    WPP_SF_d
0x180031724  mov     ecx, r14d
0x180031727  call    cs:__imp_FwHResultToWindowsError
0x18003172d  jmp     short loc_18003174C
0x18003172f  mov     [rdi+0D8h], r12d
0x180031736  jmp     short loc_18003174A
0x180031738  mov     eax, 8
0x18003173d  jmp     short loc_18003174C
0x18003173f  mov     qword ptr [rdi+0E0h], 0
0x18003174a  xor     eax, eax
0x18003174c  mov     rcx, [rbp+var_10]
0x180031750  xor     rcx, rsp; StackCookie
0x180031753  call    __security_check_cookie
0x180031758  add     rsp, 70h
0x18003175c  pop     r15
0x18003175e  pop     r14
0x180031760  pop     r12
0x180031762  pop     rdi
0x180031763  pop     rsi
0x180031764  pop     rbx
0x180031765  pop     rbp
0x180031766  retn
```
