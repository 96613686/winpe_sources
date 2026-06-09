# CopyServicesSettingsToProfile(_tag_FW_RULE const *,ICF_PROFILE_ *)

- ea: `0x180032264`
- end: `0x1800324cf`
- name: `?CopyServicesSettingsToProfile@@YAKPEBU_tag_FW_RULE@@PEAUICF_PROFILE_@@@Z`
- size: `619`
- prototype: `unsigned int __fastcall(const struct _tag_FW_RULE *, struct ICF_PROFILE_ *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180032f90`

## callees

- `0x180005954`
- `0x18001cdb4`
- `0x18003104c`
- `0x180031160`
- `0x180032264`
- `0x1800324d8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800323ae`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800323ae`
- `fwbase!FwBaseAlloc` at `0x1800322fc`
- `fwbase!FwBaseAlloc` at `0x1800322fc`
- `fwbase!FwLoadString` at `0x18003233c`
- `fwbase!FwLoadString` at `0x18003233c`
- `fwbase!FwHResultToWindowsError` at `0x1800324ae`
- `fwbase!FwHResultToWindowsError` at `0x1800324ae`

## string_xrefs

- `0x1800322be`: `@FirewallAPI.dll,-28502`
- `0x1800322ac`: `@FirewallAPI.dll,-23006`
- `0x1800322c5`: `@FirewallAPI.dll,-28752`

## pseudocode

```c
__int64 __fastcall CopyServicesSettingsToProfile(const struct _tag_FW_RULE *a1, struct ICF_PROFILE_ *a2)
{
  __int64 v4; // rax
  unsigned int v6; // edi
  __int64 v7; // rsi
  int String; // eax
  const struct _tag_FW_RULE *v9; // r15
  const struct _tag_FW_RULE *v10; // r14
  const WCHAR *v11; // r8
  bool v12; // cf
  __int64 v13; // rax
  int v14; // ecx
  unsigned int v15; // r15d
  FwPolicy2 *v16; // rcx
  __int64 v17; // rdx
  int v18; // [rsp+30h] [rbp-38h]
  int v19; // [rsp+34h] [rbp-34h]
  PCNZWCH v20; // [rsp+38h] [rbp-30h]
  int v21; // [rsp+40h] [rbp-28h]
  int v22; // [rsp+44h] [rbp-24h]
  const WCHAR *v23; // [rsp+48h] [rbp-20h]
  int v24; // [rsp+50h] [rbp-18h]
  int v25; // [rsp+54h] [rbp-14h]
  const WCHAR *v26; // [rsp+58h] [rbp-10h]

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids);
  v18 = 0;
  v23 = L"@FirewallAPI.dll,-23006";
  v19 = 23000;
  v26 = L"@FirewallAPI.dll,-28752";
  v20 = L"@FirewallAPI.dll,-28502";
  v21 = 1;
  v22 = 23006;
  v24 = 2;
  v25 = 23009;
  v4 = FwBaseAlloc(312);
  *((_QWORD *)a2 + 26) = v4;
  if ( !v4 )
    return 8;
  v6 = 0;
LABEL_7:
  if ( v6 >= 3 )
  {
    *((_DWORD *)a2 + 50) = v6;
    return 0;
  }
  v7 = 104LL * v6;
  String = FwLoadString((unsigned int)*(&v19 + 4 * v6), v7 + *((_QWORD *)a2 + 26));
  if ( String < 0 )
    return FwHResultToWindowsError((unsigned int)String);
  v9 = 0;
  v10 = a1;
  *(_DWORD *)(*((_QWORD *)a2 + 26) + v7 + 8) = *(&v18 + 4 * v6);
  *(_DWORD *)(*((_QWORD *)a2 + 26) + v7 + 16) = 1;
  *(_DWORD *)(*((_QWORD *)a2 + 26) + v7 + 12) = 0;
  while ( 1 )
  {
    if ( !v10 )
    {
      ++v6;
      goto LABEL_7;
    }
    v11 = (const WCHAR *)*((_QWORD *)v10 + 39);
    if ( !v11 || CompareStringW(0x7Fu, 1u, v11, -1, (&v20)[2 * v6], -1) != 2 )
      goto LABEL_19;
    v12 = (unsigned int)IsRuleEnabled(v10) != 0;
    v13 = *((_QWORD *)a2 + 26);
    v14 = v12 + 1;
    if ( v9 )
    {
      if ( *(_DWORD *)(v7 + v13 + 16) != v14 )
      {
        *(_DWORD *)(v7 + v13 + 12) = 1;
        *(_DWORD *)(*((_QWORD *)a2 + 26) + v7 + 16) = 1;
      }
      goto LABEL_19;
    }
    *(_DWORD *)(v7 + v13 + 16) = v14;
    v15 = CopySubnetRestrictions(
            v10,
            (struct ICF_SUBNETS_ *)(v7 + *((_QWORD *)a2 + 26) + 24LL),
            (struct ICF_SUBNETS6_ *)(v7 + *((_QWORD *)a2 + 26) + 48LL));
    if ( v15 )
      break;
    v15 = CopyAddrRanges(
            v10,
            (struct ICF_RANGES_ *)(v7 + *((_QWORD *)a2 + 26) + 72LL),
            (struct ICF_RANGES6_ *)(v7 + *((_QWORD *)a2 + 26) + 88LL));
    if ( v15 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v17 = 23;
LABEL_27:
        WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids, v15);
        return v15;
      }
      return v15;
    }
    v9 = v10;
LABEL_19:
    v10 = *(const struct _tag_FW_RULE **)v10;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v17 = 22;
    goto LABEL_27;
  }
  return v15;
}

```

## disassembly

```asm
0x180032264  push    rbp
0x180032266  push    rbx
0x180032267  push    rsi
0x180032268  push    rdi
0x180032269  push    r12
0x18003226b  push    r13
0x18003226d  push    r14
0x18003226f  push    r15
0x180032271  mov     rbp, rsp
0x180032274  sub     rsp, 68h
0x180032278  mov     rbx, rdx
0x18003227b  mov     r13, rcx
0x18003227e  mov     rcx, cs:WPP_GLOBAL_Control
0x180032285  lea     rax, WPP_GLOBAL_Control
0x18003228c  cmp     rcx, rax
0x18003228f  jz      short loc_1800322AC
0x180032291  test    byte ptr [rcx+1Ch], 8
0x180032295  jz      short loc_1800322AC
0x180032297  mov     rcx, [rcx+10h]
0x18003229b  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x1800322a2  mov     edx, 15h
0x1800322a7  call    WPP_SF_
0x1800322ac  lea     rcx, aFirewallapiDll_0; "@FirewallAPI.dll,-23006"
0x1800322b3  mov     [rbp+var_38], 0
0x1800322ba  mov     [rbp+var_20], rcx
0x1800322be  lea     rax, aFirewallapiDll_9; "@FirewallAPI.dll,-28502"
0x1800322c5  lea     rcx, aFirewallapiDll_6; "@FirewallAPI.dll,-28752"
0x1800322cc  mov     [rbp+var_34], 59D8h
0x1800322d3  mov     [rbp+var_10], rcx
0x1800322d7  mov     ecx, 138h
0x1800322dc  mov     [rbp+var_30], rax
0x1800322e0  mov     [rbp+var_28], 1
0x1800322e7  mov     [rbp+var_24], 59DEh
0x1800322ee  mov     [rbp+var_18], 2
0x1800322f5  mov     [rbp+var_14], 59E1h
0x1800322fc  call    cs:__imp_FwBaseAlloc
0x180032302  mov     [rbx+0D0h], rax
0x180032309  test    rax, rax
0x18003230c  jnz     short loc_180032318
0x18003230e  mov     eax, 8
0x180032313  jmp     loc_1800324BE
0x180032318  xor     edi, edi
0x18003231a  cmp     edi, 3
0x18003231d  jnb     loc_1800324B6
0x180032323  mov     rdx, [rbx+0D0h]
0x18003232a  mov     r12d, edi
0x18003232d  imul    rsi, r12, 68h ; 'h'
0x180032331  add     r12, r12
0x180032334  add     rdx, rsi
0x180032337  mov     ecx, [rbp+r12*8+var_34]
0x18003233c  call    cs:__imp_FwLoadString
0x180032342  test    eax, eax
0x180032344  js      loc_1800324AC
0x18003234a  mov     rcx, [rbx+0D0h]
0x180032351  xor     r15d, r15d
0x180032354  mov     eax, [rbp+r12*8+var_38]
0x180032359  mov     r14, r13
0x18003235c  mov     [rcx+rsi+8], eax
0x180032360  mov     rax, [rbx+0D0h]
0x180032367  mov     dword ptr [rax+rsi+10h], 1
0x18003236f  mov     rax, [rbx+0D0h]
0x180032376  mov     [rax+rsi+0Ch], r15d
0x18003237b  test    r14, r14
0x18003237e  jz      loc_18003244F
0x180032384  mov     r8, [r14+138h]; lpString1
0x18003238b  test    r8, r8
0x18003238e  jz      loc_180032447
0x180032394  mov     rax, [rbp+r12*8+var_30]
0x180032399  or      ecx, 0FFFFFFFFh
0x18003239c  mov     [rsp+68h+cchCount2], ecx; cchCount2
0x1800323a0  mov     r9d, ecx; cchCount1
0x1800323a3  mov     [rsp+68h+lpString2], rax; lpString2
0x1800323a8  lea     edx, [rcx+2]; dwCmpFlags
0x1800323ab  lea     ecx, [rdx+7Eh]; Locale
0x1800323ae  call    cs:__imp_CompareStringW
0x1800323b4  cmp     eax, 2
0x1800323b7  jnz     loc_180032447
0x1800323bd  mov     rcx, r14; struct _tag_FW_RULE *
0x1800323c0  call    ?IsRuleEnabled@@YAHPEBU_tag_FW_RULE@@@Z; IsRuleEnabled(_tag_FW_RULE const *)
0x1800323c5  neg     eax
0x1800323c7  mov     rax, [rbx+0D0h]
0x1800323ce  sbb     ecx, ecx
0x1800323d0  neg     ecx
0x1800323d2  inc     ecx
0x1800323d4  test    r15, r15
0x1800323d7  jz      short loc_1800323F8
0x1800323d9  cmp     [rsi+rax+10h], ecx
0x1800323dd  jz      short loc_180032447
0x1800323df  mov     dword ptr [rsi+rax+0Ch], 1
0x1800323e7  mov     rax, [rbx+0D0h]
0x1800323ee  mov     dword ptr [rax+rsi+10h], 1
0x1800323f6  jmp     short loc_180032447
0x1800323f8  mov     [rsi+rax+10h], ecx
0x1800323fc  mov     rcx, r14; struct _tag_FW_RULE *
0x1800323ff  mov     rax, [rbx+0D0h]
0x180032406  lea     r8, [rax+30h]
0x18003240a  lea     rdx, [rax+18h]
0x18003240e  add     r8, rsi; struct ICF_SUBNETS6_ *
0x180032411  add     rdx, rsi; struct ICF_SUBNETS_ *
0x180032414  call    ?CopySubnetRestrictions@@YAKPEBU_tag_FW_RULE@@PEAUICF_SUBNETS_@@PEAUICF_SUBNETS6_@@@Z; CopySubnetRestrictions(_tag_FW_RULE const *,ICF_SUBNETS_ *,ICF_SUBNETS6_ *)
0x180032419  mov     r15d, eax
0x18003241c  test    eax, eax
0x18003241e  jnz     short loc_180032476
0x180032420  mov     rax, [rbx+0D0h]
0x180032427  mov     rcx, r14; struct _tag_FW_RULE *
0x18003242a  lea     r8, [rax+58h]
0x18003242e  lea     rdx, [rax+48h]
0x180032432  add     r8, rsi; struct ICF_RANGES6_ *
0x180032435  add     rdx, rsi; struct ICF_RANGES_ *
0x180032438  call    ?CopyAddrRanges@@YAKPEBU_tag_FW_RULE@@PEAUICF_RANGES_@@PEAUICF_RANGES6_@@@Z; CopyAddrRanges(_tag_FW_RULE const *,ICF_RANGES_ *,ICF_RANGES6_ *)
0x18003243d  mov     r15d, eax
0x180032440  test    eax, eax
0x180032442  jnz     short loc_180032456
0x180032444  mov     r15, r14
0x180032447  mov     r14, [r14]
0x18003244a  jmp     loc_18003237B
0x18003244f  inc     edi
0x180032451  jmp     loc_18003231A
0x180032456  mov     rcx, cs:WPP_GLOBAL_Control
0x18003245d  lea     rax, WPP_GLOBAL_Control
0x180032464  cmp     rcx, rax
0x180032467  jz      short loc_1800324A7
0x180032469  test    byte ptr [rcx+1Ch], 1
0x18003246d  jz      short loc_1800324A7
0x18003246f  mov     edx, 17h
0x180032474  jmp     short loc_180032494
0x180032476  mov     rcx, cs:WPP_GLOBAL_Control
0x18003247d  lea     rax, WPP_GLOBAL_Control
0x180032484  cmp     rcx, rax
0x180032487  jz      short loc_1800324A7
0x180032489  test    byte ptr [rcx+1Ch], 1
0x18003248d  jz      short loc_1800324A7
0x18003248f  mov     edx, 16h
0x180032494  mov     rcx, [rcx+10h]
0x180032498  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x18003249f  mov     r9d, r15d
0x1800324a2  call    WPP_SF_d
0x1800324a7  mov     eax, r15d
0x1800324aa  jmp     short loc_1800324BE
0x1800324ac  mov     ecx, eax
0x1800324ae  call    cs:__imp_FwHResultToWindowsError
0x1800324b4  jmp     short loc_1800324BE
0x1800324b6  mov     [rbx+0C8h], edi
0x1800324bc  xor     eax, eax
0x1800324be  add     rsp, 68h
0x1800324c2  pop     r15
0x1800324c4  pop     r14
0x1800324c6  pop     r13
0x1800324c8  pop     r12
0x1800324ca  pop     rdi
0x1800324cb  pop     rsi
0x1800324cc  pop     rbx
0x1800324cd  pop     rbp
0x1800324ce  retn
```
