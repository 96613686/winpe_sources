# CopyPortsSettingsToProfile(void *,_tag_FW_PROFILE_TYPE,_tag_FW_RULE const *,ICF_PROFILE_ *)

- ea: `0x180031d30`
- end: `0x180032177`
- name: `?CopyPortsSettingsToProfile@@YAKPEAXW4_tag_FW_PROFILE_TYPE@@PEBU_tag_FW_RULE@@PEAUICF_PROFILE_@@@Z`
- size: `1095`
- prototype: `unsigned int __high(void *, enum _tag_FW_PROFILE_TYPE, const struct _tag_FW_RULE *, struct ICF_PROFILE_ *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

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
- `0x180031d30`
- `0x1800324d8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031fe0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180032021`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003205e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180031fe0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180032021`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003205e`
- `fwbase!FwBaseAlloc` at `0x180031ef9`
- `fwbase!FwBaseAlloc` at `0x180031ef9`
- `fwbase!FwSizeTMultiply` at `0x180031ee7`
- `fwbase!FwSizeTMultiply` at `0x180031ee7`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180031eae`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180031f2f`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180031eae`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180031f2f`
- `fwbase!FwHResultToWindowsError` at `0x180031db3`
- `fwbase!FwHResultToWindowsError` at `0x1800320ef`
- `fwbase!FwHResultToWindowsError` at `0x180031db3`
- `fwbase!FwHResultToWindowsError` at `0x1800320ef`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180031ea1`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180031f1e`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180031ea1`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180031f1e`
- `fwbase!FwStringCopy` at `0x180031f54`
- `fwbase!FwStringCopy` at `0x180031f54`

## string_xrefs

- `0x180031fc6`: `@FirewallAPI.dll,-28502`
- `0x180032004`: `@FirewallAPI.dll,-23006`
- `0x180032041`: `@FirewallAPI.dll,-28752`

## pseudocode

```c
__int64 __fastcall CopyPortsSettingsToProfile(int a1, int a2, __int64 *a3, __int64 a4)
{
  int v6; // r14d
  int CurrentProfile; // eax
  unsigned int v9; // eax
  unsigned int v10; // ebx
  unsigned int v12; // r14d
  int v13; // eax
  FwPolicy2 *v14; // rcx
  __int64 v15; // rdx
  _QWORD *v16; // r14
  unsigned int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // r15d
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // r14
  const WCHAR *v23; // r8
  __int64 v24; // [rsp+40h] [rbp-20h] BYREF
  int v25; // [rsp+48h] [rbp-18h] BYREF
  int v26; // [rsp+4Ch] [rbp-14h] BYREF

  LODWORD(v24) = a2;
  v25 = 0;
  v6 = a2;
  v26 = 4;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids);
  if ( v6 == 0x80000000 )
  {
    CurrentProfile = FwGetCurrentProfile((enum _tag_FW_PROFILE_TYPE *)&v24);
    if ( CurrentProfile < 0 )
    {
      v9 = FwHResultToWindowsError((unsigned int)CurrentProfile);
      v10 = v9;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids, v9);
      return v10;
    }
    v6 = v24;
  }
  *(_DWORD *)(a4 + 192) = 2;
  LODWORD(v24) = 0;
  v12 = FWGetConfig2(a1, 12, v6, 1, (__int64)&v25, (__int64)&v26, (__int64)&v24);
  if ( v12 == 50 )
  {
    v13 = 1;
    v25 = 1;
  }
  else
  {
    if ( v12 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 26;
LABEL_17:
        WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids, v12);
      }
      return v12;
    }
    v13 = v25;
  }
  *(_DWORD *)(a4 + 176) = 0;
  v16 = a3;
  for ( *(_DWORD *)(a4 + 196) = (v13 != 0) + 1; v16; v16 = (_QWORD *)*v16 )
  {
    if ( (unsigned int)IsRuleOpenPortOrAuthApp(v16) && (unsigned int)IsRuleOldGlobalOpenPort(v16) )
      ++*(_DWORD *)(a4 + 176);
  }
  v17 = *(_DWORD *)(a4 + 176);
  if ( v17 )
  {
    v24 = 0;
    if ( (int)FwSizeTMultiply(112, v17, &v24) >= 0 )
    {
      v18 = FwBaseAlloc(v24);
      *(_QWORD *)(a4 + 184) = v18;
      if ( v18 )
      {
        v19 = 0;
        while ( 1 )
        {
          if ( !a3 )
          {
            *(_DWORD *)(a4 + 176) = v19;
            return 0;
          }
          if ( (unsigned int)IsRuleOpenPortOrAuthApp(a3) && (unsigned int)IsRuleOldGlobalOpenPort(a3) )
          {
            v20 = a3[3];
            if ( v20 )
            {
              v21 = FwStringCopy(v20, *(_QWORD *)(a4 + 184) + 112LL * v19);
              if ( v21 < 0 )
                return FwHResultToWindowsError((unsigned int)v21);
            }
            v22 = 112LL * v19;
            *(_WORD *)(*(_QWORD *)(a4 + 184) + v22 + 8) = *(_WORD *)a3[9];
            *(_DWORD *)(*(_QWORD *)(a4 + 184) + v22 + 12) = *((unsigned __int16 *)a3 + 24);
            *(_DWORD *)(*(_QWORD *)(a4 + 184) + v22 + 96) = IsRuleEnabled((const struct _tag_FW_RULE *)a3);
            *(_DWORD *)(*(_QWORD *)(a4 + 184) + v22 + 100) = 3;
            v23 = (const WCHAR *)a3[39];
            if ( v23 )
            {
              if ( CompareStringW(0x7Fu, 1u, v23, -1, L"@FirewallAPI.dll,-28502", -1) == 2 )
              {
                *(_DWORD *)(*(_QWORD *)(a4 + 184) + v22 + 100) = 0;
              }
              else if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)a3[39], -1, L"@FirewallAPI.dll,-23006", -1) == 2 )
              {
                *(_DWORD *)(*(_QWORD *)(a4 + 184) + v22 + 100) = 1;
              }
              else if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)a3[39], -1, L"@FirewallAPI.dll,-28752", -1) == 2 )
              {
                *(_DWORD *)(*(_QWORD *)(a4 + 184) + v22 + 100) = 2;
              }
            }
            *(_DWORD *)(v22 + *(_QWORD *)(a4 + 184) + 104) = *((_DWORD *)a3 + 85) == 1;
            v12 = CopySubnetRestrictions(
                    (const struct _tag_FW_RULE *)a3,
                    (struct ICF_SUBNETS_ *)(v22 + *(_QWORD *)(a4 + 184) + 16LL),
                    (struct ICF_SUBNETS6_ *)(v22 + *(_QWORD *)(a4 + 184) + 40LL));
            if ( v12 )
            {
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v15 = 27;
                goto LABEL_17;
              }
              return v12;
            }
            v12 = CopyAddrRanges(
                    (const struct _tag_FW_RULE *)a3,
                    (struct ICF_RANGES_ *)(112LL * v19 + *(_QWORD *)(a4 + 184) + 64LL),
                    (struct ICF_RANGES6_ *)(112LL * v19 + *(_QWORD *)(a4 + 184) + 80LL));
            if ( v12 )
            {
              v14 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v15 = 28;
                goto LABEL_17;
              }
              return v12;
            }
            ++v19;
          }
          a3 = (__int64 *)*a3;
        }
      }
    }
    return 8;
  }
  else
  {
    *(_QWORD *)(a4 + 184) = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x180031d30  push    rbp
0x180031d32  push    rbx
0x180031d33  push    rsi
0x180031d34  push    rdi
0x180031d35  push    r13
0x180031d37  push    r14
0x180031d39  push    r15
0x180031d3b  mov     rbp, rsp
0x180031d3e  sub     rsp, 60h
0x180031d42  mov     rax, cs:__security_cookie
0x180031d49  xor     rax, rsp
0x180031d4c  mov     [rbp+var_10], rax
0x180031d50  mov     rbx, r9
0x180031d53  mov     dword ptr [rbp+var_20], edx
0x180031d56  mov     rsi, r8
0x180031d59  mov     [rbp+var_18], 0
0x180031d60  mov     r14d, edx
0x180031d63  mov     [rbp+var_14], 4
0x180031d6a  mov     r15, rcx
0x180031d6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031d74  lea     r13, WPP_GLOBAL_Control
0x180031d7b  cmp     rcx, r13
0x180031d7e  jz      short loc_180031D9B
0x180031d80  test    byte ptr [rcx+1Ch], 8
0x180031d84  jz      short loc_180031D9B
0x180031d86  mov     rcx, [rcx+10h]
0x180031d8a  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x180031d91  mov     edx, 18h
0x180031d96  call    WPP_SF_
0x180031d9b  cmp     r14d, 80000000h
0x180031da2  jnz     short loc_180031DF3
0x180031da4  lea     rcx, [rbp+var_20]; enum _tag_FW_PROFILE_TYPE *
0x180031da8  call    ?FwGetCurrentProfile@@YAJPEAW4_tag_FW_PROFILE_TYPE@@@Z; FwGetCurrentProfile(_tag_FW_PROFILE_TYPE *)
0x180031dad  test    eax, eax
0x180031daf  jns     short loc_180031DEF
0x180031db1  mov     ecx, eax
0x180031db3  call    cs:__imp_FwHResultToWindowsError
0x180031db9  mov     ebx, eax
0x180031dbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180031dc2  cmp     rcx, r13
0x180031dc5  jz      short loc_180031DE8
0x180031dc7  mov     edi, 1
0x180031dcc  test    [rcx+1Ch], dil
0x180031dd0  jz      short loc_180031DE8
0x180031dd2  mov     rcx, [rcx+10h]
0x180031dd6  lea     edx, [rdi+18h]
0x180031dd9  mov     r9d, eax
0x180031ddc  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x180031de3  call    WPP_SF_d
0x180031de8  mov     eax, ebx
0x180031dea  jmp     loc_18003215C
0x180031def  mov     r14d, dword ptr [rbp+var_20]
0x180031df3  lea     rax, [rbp+var_20]
0x180031df7  mov     dword ptr [rbx+0C0h], 2
0x180031e01  mov     [rsp+60h+var_30], rax
0x180031e06  mov     edi, 1
0x180031e0b  lea     rax, [rbp+var_14]
0x180031e0f  mov     dword ptr [rbp+var_20], 0
0x180031e16  mov     qword ptr [rsp+60h+cchCount2], rax
0x180031e1b  mov     r9d, edi
0x180031e1e  lea     rax, [rbp+var_18]
0x180031e22  mov     r8d, r14d
0x180031e25  lea     edx, [rdi+0Bh]
0x180031e28  mov     [rsp+60h+lpString2], rax
0x180031e2d  mov     rcx, r15
0x180031e30  call    FWGetConfig2
0x180031e35  mov     r14d, eax
0x180031e38  cmp     eax, 32h ; '2'
0x180031e3b  jnz     short loc_180031E44
0x180031e3d  mov     eax, edi
0x180031e3f  mov     [rbp+var_18], eax
0x180031e42  jmp     short loc_180031E7E
0x180031e44  test    r14d, r14d
0x180031e47  jz      short loc_180031E7B
0x180031e49  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e50  cmp     rcx, r13
0x180031e53  jz      short loc_180031E73
0x180031e55  test    [rcx+1Ch], dil
0x180031e59  jz      short loc_180031E73
0x180031e5b  mov     edx, 1Ah
0x180031e60  mov     rcx, [rcx+10h]
0x180031e64  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x180031e6b  mov     r9d, r14d
0x180031e6e  call    WPP_SF_d
0x180031e73  mov     eax, r14d
0x180031e76  jmp     loc_18003215C
0x180031e7b  mov     eax, [rbp+var_18]
0x180031e7e  neg     eax
0x180031e80  mov     dword ptr [rbx+0B0h], 0
0x180031e8a  mov     r14, rsi
0x180031e8d  sbb     eax, eax
0x180031e8f  neg     eax
0x180031e91  add     eax, edi
0x180031e93  mov     [rbx+0C4h], eax
0x180031e99  test    rsi, rsi
0x180031e9c  jz      short loc_180031EC6
0x180031e9e  mov     rcx, r14
0x180031ea1  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180031ea7  test    eax, eax
0x180031ea9  jz      short loc_180031EBE
0x180031eab  mov     rcx, r14
0x180031eae  call    cs:__imp_IsRuleOldGlobalOpenPort
0x180031eb4  test    eax, eax
0x180031eb6  jz      short loc_180031EBE
0x180031eb8  add     [rbx+0B0h], edi
0x180031ebe  mov     r14, [r14]
0x180031ec1  test    r14, r14
0x180031ec4  jnz     short loc_180031E9E
0x180031ec6  mov     eax, [rbx+0B0h]
0x180031ecc  test    eax, eax
0x180031ece  jz      loc_18003214F
0x180031ed4  mov     edx, eax
0x180031ed6  mov     [rbp+var_20], 0
0x180031ede  lea     r8, [rbp+var_20]
0x180031ee2  mov     ecx, 70h ; 'p'
0x180031ee7  call    cs:__imp_FwSizeTMultiply
0x180031eed  test    eax, eax
0x180031eef  js      loc_180032148
0x180031ef5  mov     rcx, [rbp+var_20]
0x180031ef9  call    cs:__imp_FwBaseAlloc
0x180031eff  mov     [rbx+0B8h], rax
0x180031f06  test    rax, rax
0x180031f09  jz      loc_180032148
0x180031f0f  xor     r15d, r15d
0x180031f12  test    rsi, rsi
0x180031f15  jz      loc_18003213F
0x180031f1b  mov     rcx, rsi
0x180031f1e  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180031f24  test    eax, eax
0x180031f26  jz      loc_1800320E5
0x180031f2c  mov     rcx, rsi
0x180031f2f  call    cs:__imp_IsRuleOldGlobalOpenPort
0x180031f35  test    eax, eax
0x180031f37  jz      loc_1800320E5
0x180031f3d  mov     rcx, [rsi+18h]
0x180031f41  test    rcx, rcx
0x180031f44  jz      short loc_180031F62
0x180031f46  mov     eax, r15d
0x180031f49  imul    rdx, rax, 70h ; 'p'
0x180031f4d  add     rdx, [rbx+0B8h]
0x180031f54  call    cs:__imp_FwStringCopy
0x180031f5a  test    eax, eax
0x180031f5c  js      loc_1800320ED
0x180031f62  mov     rcx, [rbx+0B8h]
0x180031f69  mov     eax, r15d
0x180031f6c  imul    r14, rax, 70h ; 'p'
0x180031f70  mov     rax, [rsi+48h]
0x180031f74  movzx   eax, word ptr [rax]
0x180031f77  mov     [rcx+r14+8], ax
0x180031f7d  mov     rax, [rbx+0B8h]
0x180031f84  movzx   ecx, word ptr [rsi+30h]
0x180031f88  mov     [rax+r14+0Ch], ecx
0x180031f8d  mov     rcx, rsi; struct _tag_FW_RULE *
0x180031f90  call    ?IsRuleEnabled@@YAHPEBU_tag_FW_RULE@@@Z; IsRuleEnabled(_tag_FW_RULE const *)
0x180031f95  mov     ecx, eax
0x180031f97  mov     rax, [rbx+0B8h]
0x180031f9e  mov     [rax+r14+60h], ecx
0x180031fa3  mov     rax, [rbx+0B8h]
0x180031faa  mov     dword ptr [rax+r14+64h], 3
0x180031fb3  mov     r8, [rsi+138h]; lpString1
0x180031fba  test    r8, r8
0x180031fbd  jz      loc_180032079
0x180031fc3  or      ecx, 0FFFFFFFFh
0x180031fc6  lea     rax, aFirewallapiDll_9; "@FirewallAPI.dll,-28502"
0x180031fcd  mov     [rsp+60h+cchCount2], ecx; cchCount2
0x180031fd1  mov     r9d, ecx; cchCount1
0x180031fd4  mov     ecx, 7Fh; Locale
0x180031fd9  mov     [rsp+60h+lpString2], rax; lpString2
0x180031fde  mov     edx, edi; dwCmpFlags
0x180031fe0  call    cs:__imp_CompareStringW
0x180031fe6  cmp     eax, 2
0x180031fe9  jnz     short loc_180031FFD
0x180031feb  mov     rax, [rbx+0B8h]
0x180031ff2  mov     dword ptr [rax+r14+64h], 0
0x180031ffb  jmp     short loc_180032079
0x180031ffd  mov     r8, [rsi+138h]; lpString1
0x180032004  lea     rax, aFirewallapiDll_0; "@FirewallAPI.dll,-23006"
0x18003200b  or      ecx, 0FFFFFFFFh
0x18003200e  mov     edx, edi; dwCmpFlags
0x180032010  mov     [rsp+60h+cchCount2], ecx; cchCount2
0x180032014  mov     r9d, ecx; cchCount1
0x180032017  mov     ecx, 7Fh; Locale
0x18003201c  mov     [rsp+60h+lpString2], rax; lpString2
0x180032021  call    cs:__imp_CompareStringW
0x180032027  cmp     eax, 2
0x18003202a  jnz     short loc_18003203A
0x18003202c  mov     rax, [rbx+0B8h]
0x180032033  mov     [rax+r14+64h], edi
0x180032038  jmp     short loc_180032079
0x18003203a  mov     r8, [rsi+138h]; lpString1
0x180032041  lea     rax, aFirewallapiDll_6; "@FirewallAPI.dll,-28752"
0x180032048  or      ecx, 0FFFFFFFFh
0x18003204b  mov     edx, edi; dwCmpFlags
0x18003204d  mov     [rsp+60h+cchCount2], ecx; cchCount2
0x180032051  mov     r9d, ecx; cchCount1
0x180032054  mov     ecx, 7Fh; Locale
0x180032059  mov     [rsp+60h+lpString2], rax; lpString2
0x18003205e  call    cs:__imp_CompareStringW
0x180032064  cmp     eax, 2
0x180032067  jnz     short loc_180032079
0x180032069  mov     rax, [rbx+0B8h]
0x180032070  mov     dword ptr [rax+r14+64h], 2
0x180032079  mov     rcx, [rbx+0B8h]
0x180032080  cmp     [rsi+154h], edi
0x180032086  jnz     short loc_18003208C
0x180032088  mov     eax, edi
0x18003208a  jmp     short loc_18003208E
0x18003208c  xor     eax, eax
0x18003208e  mov     [r14+rcx+68h], eax
0x180032093  mov     rcx, rsi; struct _tag_FW_RULE *
0x180032096  mov     rax, [rbx+0B8h]
0x18003209d  lea     r8, [rax+28h]
0x1800320a1  lea     rdx, [rax+10h]
0x1800320a5  add     r8, r14; struct ICF_SUBNETS6_ *
0x1800320a8  add     rdx, r14; struct ICF_SUBNETS_ *
0x1800320ab  call    ?CopySubnetRestrictions@@YAKPEBU_tag_FW_RULE@@PEAUICF_SUBNETS_@@PEAUICF_SUBNETS6_@@@Z; CopySubnetRestrictions(_tag_FW_RULE const *,ICF_SUBNETS_ *,ICF_SUBNETS6_ *)
0x1800320b0  mov     r14d, eax
0x1800320b3  test    eax, eax
0x1800320b5  jnz     short loc_18003211B
0x1800320b7  mov     eax, r15d
0x1800320ba  imul    rcx, rax, 70h ; 'p'
0x1800320be  mov     rax, [rbx+0B8h]
0x1800320c5  lea     r8, [rax+50h]
0x1800320c9  lea     rdx, [rax+40h]
0x1800320cd  add     r8, rcx; struct ICF_RANGES6_ *
0x1800320d0  add     rdx, rcx; struct ICF_RANGES_ *
0x1800320d3  mov     rcx, rsi; struct _tag_FW_RULE *
0x1800320d6  call    ?CopyAddrRanges@@YAKPEBU_tag_FW_RULE@@PEAUICF_RANGES_@@PEAUICF_RANGES6_@@@Z; CopyAddrRanges(_tag_FW_RULE const *,ICF_RANGES_ *,ICF_RANGES6_ *)
0x1800320db  mov     r14d, eax
0x1800320de  test    eax, eax
0x1800320e0  jnz     short loc_1800320F7
0x1800320e2  add     r15d, edi
0x1800320e5  mov     rsi, [rsi]
0x1800320e8  jmp     loc_180031F12
0x1800320ed  mov     ecx, eax
0x1800320ef  call    cs:__imp_FwHResultToWindowsError
0x1800320f5  jmp     short loc_18003215C
0x1800320f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800320fe  cmp     rcx, r13
0x180032101  jz      loc_180031E73
0x180032107  test    [rcx+1Ch], dil
0x18003210b  jz      loc_180031E73
0x180032111  mov     edx, 1Ch
0x180032116  jmp     loc_180031E60
0x18003211b  mov     rcx, cs:WPP_GLOBAL_Control
0x180032122  cmp     rcx, r13
0x180032125  jz      loc_180031E73
0x18003212b  test    [rcx+1Ch], dil
0x18003212f  jz      loc_180031E73
0x180032135  mov     edx, 1Bh
0x18003213a  jmp     loc_180031E60
0x18003213f  mov     [rbx+0B0h], r15d
0x180032146  jmp     short loc_18003215A
0x180032148  mov     eax, 8
0x18003214d  jmp     short loc_18003215C
0x18003214f  mov     qword ptr [rbx+0B8h], 0
0x18003215a  xor     eax, eax
0x18003215c  mov     rcx, [rbp+var_10]
0x180032160  xor     rcx, rsp; StackCookie
0x180032163  call    __security_check_cookie
0x180032168  add     rsp, 60h
0x18003216c  pop     r15
0x18003216e  pop     r14
0x180032170  pop     r13
0x180032172  pop     rdi
0x180032173  pop     rsi
0x180032174  pop     rbx
0x180032175  pop     rbp
0x180032176  retn
```
