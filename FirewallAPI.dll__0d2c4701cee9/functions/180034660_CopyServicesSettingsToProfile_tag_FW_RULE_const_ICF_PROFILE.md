# CopyServicesSettingsToProfile(_tag_FW_RULE const *,ICF_PROFILE_ *)

- ea: `0x180034660`
- end: `0x1800348e4`
- name: `?CopyServicesSettingsToProfile@@YAKPEBU_tag_FW_RULE@@PEAUICF_PROFILE_@@@Z`
- size: `644`
- prototype: `unsigned int __fastcall(const struct _tag_FW_RULE *, struct ICF_PROFILE_ *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180035500`

## callees

- `0x180005e0c`
- `0x18001ce34`
- `0x18003336c`
- `0x180033488`
- `0x180034660`
- `0x1800348ec`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800347b6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800347b6`
- `fwbase!FwBaseAlloc` at `0x1800346f8`
- `fwbase!FwBaseAlloc` at `0x1800346f8`
- `fwbase!FwLoadString` at `0x18003473e`
- `fwbase!FwLoadString` at `0x18003473e`
- `fwbase!FwHResultToWindowsError` at `0x1800348bc`
- `fwbase!FwHResultToWindowsError` at `0x1800348bc`

## string_xrefs

- `0x1800346ba`: `@FirewallAPI.dll,-28502`
- `0x1800346a8`: `@FirewallAPI.dll,-23006`
- `0x1800346c1`: `@FirewallAPI.dll,-28752`

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
0x180034660  push    rbp
0x180034662  push    rbx
0x180034663  push    rsi
0x180034664  push    rdi
0x180034665  push    r12
0x180034667  push    r13
0x180034669  push    r14
0x18003466b  push    r15
0x18003466d  mov     rbp, rsp
0x180034670  sub     rsp, 68h
0x180034674  mov     rbx, rdx
0x180034677  mov     r13, rcx
0x18003467a  mov     rcx, cs:WPP_GLOBAL_Control
0x180034681  lea     rax, WPP_GLOBAL_Control
0x180034688  cmp     rcx, rax
0x18003468b  jz      short loc_1800346A8
0x18003468d  test    byte ptr [rcx+1Ch], 8
0x180034691  jz      short loc_1800346A8
0x180034693  mov     rcx, [rcx+10h]
0x180034697  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x18003469e  mov     edx, 15h
0x1800346a3  call    WPP_SF_
0x1800346a8  lea     rcx, aFirewallapiDll_0; "@FirewallAPI.dll,-23006"
0x1800346af  mov     [rbp+var_38], 0
0x1800346b6  mov     [rbp+var_20], rcx
0x1800346ba  lea     rax, aFirewallapiDll_9; "@FirewallAPI.dll,-28502"
0x1800346c1  lea     rcx, aFirewallapiDll_6; "@FirewallAPI.dll,-28752"
0x1800346c8  mov     [rbp+var_34], 59D8h
0x1800346cf  mov     [rbp+var_10], rcx
0x1800346d3  mov     ecx, 138h
0x1800346d8  mov     [rbp+var_30], rax
0x1800346dc  mov     [rbp+var_28], 1
0x1800346e3  mov     [rbp+var_24], 59DEh
0x1800346ea  mov     [rbp+var_18], 2
0x1800346f1  mov     [rbp+var_14], 59E1h
0x1800346f8  call    cs:__imp_FwBaseAlloc
0x1800346ff  nop     dword ptr [rax+rax+00h]
0x180034704  mov     [rbx+0D0h], rax
0x18003470b  test    rax, rax
0x18003470e  jnz     short loc_18003471A
0x180034710  mov     eax, 8
0x180034715  jmp     loc_1800348D2
0x18003471a  xor     edi, edi
0x18003471c  cmp     edi, 3
0x18003471f  jnb     loc_1800348CA
0x180034725  mov     rdx, [rbx+0D0h]
0x18003472c  mov     r12d, edi
0x18003472f  imul    rsi, r12, 68h ; 'h'
0x180034733  add     r12, r12
0x180034736  add     rdx, rsi
0x180034739  mov     ecx, [rbp+r12*8+var_34]
0x18003473e  call    cs:__imp_FwLoadString
0x180034745  nop     dword ptr [rax+rax+00h]
0x18003474a  test    eax, eax
0x18003474c  js      loc_1800348BA
0x180034752  mov     rcx, [rbx+0D0h]
0x180034759  xor     r15d, r15d
0x18003475c  mov     eax, [rbp+r12*8+var_38]
0x180034761  mov     r14, r13
0x180034764  mov     [rcx+rsi+8], eax
0x180034768  mov     rax, [rbx+0D0h]
0x18003476f  mov     dword ptr [rax+rsi+10h], 1
0x180034777  mov     rax, [rbx+0D0h]
0x18003477e  mov     [rax+rsi+0Ch], r15d
0x180034783  test    r14, r14
0x180034786  jz      loc_18003485D
0x18003478c  mov     r8, [r14+138h]; lpString1
0x180034793  test    r8, r8
0x180034796  jz      loc_180034855
0x18003479c  mov     rax, [rbp+r12*8+var_30]
0x1800347a1  or      ecx, 0FFFFFFFFh
0x1800347a4  mov     [rsp+68h+cchCount2], ecx; cchCount2
0x1800347a8  mov     r9d, ecx; cchCount1
0x1800347ab  mov     [rsp+68h+lpString2], rax; lpString2
0x1800347b0  lea     edx, [rcx+2]; dwCmpFlags
0x1800347b3  lea     ecx, [rdx+7Eh]; Locale
0x1800347b6  call    cs:__imp_CompareStringW
0x1800347bd  nop     dword ptr [rax+rax+00h]
0x1800347c2  cmp     eax, 2
0x1800347c5  jnz     loc_180034855
0x1800347cb  mov     rcx, r14; struct _tag_FW_RULE *
0x1800347ce  call    ?IsRuleEnabled@@YAHPEBU_tag_FW_RULE@@@Z; IsRuleEnabled(_tag_FW_RULE const *)
0x1800347d3  neg     eax
0x1800347d5  mov     rax, [rbx+0D0h]
0x1800347dc  sbb     ecx, ecx
0x1800347de  neg     ecx
0x1800347e0  inc     ecx
0x1800347e2  test    r15, r15
0x1800347e5  jz      short loc_180034806
0x1800347e7  cmp     [rsi+rax+10h], ecx
0x1800347eb  jz      short loc_180034855
0x1800347ed  mov     dword ptr [rsi+rax+0Ch], 1
0x1800347f5  mov     rax, [rbx+0D0h]
0x1800347fc  mov     dword ptr [rax+rsi+10h], 1
0x180034804  jmp     short loc_180034855
0x180034806  mov     [rsi+rax+10h], ecx
0x18003480a  mov     rcx, r14; struct _tag_FW_RULE *
0x18003480d  mov     rax, [rbx+0D0h]
0x180034814  lea     r8, [rax+30h]
0x180034818  lea     rdx, [rax+18h]
0x18003481c  add     r8, rsi; struct ICF_SUBNETS6_ *
0x18003481f  add     rdx, rsi; struct ICF_SUBNETS_ *
0x180034822  call    ?CopySubnetRestrictions@@YAKPEBU_tag_FW_RULE@@PEAUICF_SUBNETS_@@PEAUICF_SUBNETS6_@@@Z; CopySubnetRestrictions(_tag_FW_RULE const *,ICF_SUBNETS_ *,ICF_SUBNETS6_ *)
0x180034827  mov     r15d, eax
0x18003482a  test    eax, eax
0x18003482c  jnz     short loc_180034884
0x18003482e  mov     rax, [rbx+0D0h]
0x180034835  mov     rcx, r14; struct _tag_FW_RULE *
0x180034838  lea     r8, [rax+58h]
0x18003483c  lea     rdx, [rax+48h]
0x180034840  add     r8, rsi; struct ICF_RANGES6_ *
0x180034843  add     rdx, rsi; struct ICF_RANGES_ *
0x180034846  call    ?CopyAddrRanges@@YAKPEBU_tag_FW_RULE@@PEAUICF_RANGES_@@PEAUICF_RANGES6_@@@Z; CopyAddrRanges(_tag_FW_RULE const *,ICF_RANGES_ *,ICF_RANGES6_ *)
0x18003484b  mov     r15d, eax
0x18003484e  test    eax, eax
0x180034850  jnz     short loc_180034864
0x180034852  mov     r15, r14
0x180034855  mov     r14, [r14]
0x180034858  jmp     loc_180034783
0x18003485d  inc     edi
0x18003485f  jmp     loc_18003471C
0x180034864  mov     rcx, cs:WPP_GLOBAL_Control
0x18003486b  lea     rax, WPP_GLOBAL_Control
0x180034872  cmp     rcx, rax
0x180034875  jz      short loc_1800348B5
0x180034877  test    byte ptr [rcx+1Ch], 1
0x18003487b  jz      short loc_1800348B5
0x18003487d  mov     edx, 17h
0x180034882  jmp     short loc_1800348A2
0x180034884  mov     rcx, cs:WPP_GLOBAL_Control
0x18003488b  lea     rax, WPP_GLOBAL_Control
0x180034892  cmp     rcx, rax
0x180034895  jz      short loc_1800348B5
0x180034897  test    byte ptr [rcx+1Ch], 1
0x18003489b  jz      short loc_1800348B5
0x18003489d  mov     edx, 16h
0x1800348a2  mov     rcx, [rcx+10h]
0x1800348a6  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x1800348ad  mov     r9d, r15d
0x1800348b0  call    WPP_SF_d
0x1800348b5  mov     eax, r15d
0x1800348b8  jmp     short loc_1800348D2
0x1800348ba  mov     ecx, eax
0x1800348bc  call    cs:__imp_FwHResultToWindowsError
0x1800348c3  nop     dword ptr [rax+rax+00h]
0x1800348c8  jmp     short loc_1800348D2
0x1800348ca  mov     [rbx+0C8h], edi
0x1800348d0  xor     eax, eax
0x1800348d2  add     rsp, 68h
0x1800348d6  pop     r15
0x1800348d8  pop     r14
0x1800348da  pop     r13
0x1800348dc  pop     r12
0x1800348de  pop     rdi
0x1800348df  pop     rsi
0x1800348e0  pop     rbx
0x1800348e1  pop     rbp
0x1800348e2  retn
```
