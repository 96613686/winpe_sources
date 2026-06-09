# IcfGetDynamicFwPorts

- ea: `0x180032ac0`
- end: `0x180032dd2`
- name: `IcfGetDynamicFwPorts`
- size: `786`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009080`
- `0x18000b8c0`
- `0x18000c130`
- `0x18000c560`
- `0x1800197a4`
- `0x1800277b0`
- `0x18003104c`
- `0x180031160`
- `0x1800324d8`
- `0x180032670`
- `0x180032ac0`

## import_xrefs

- `fwbase!FwBaseAlloc` at `0x180032bb6`
- `fwbase!FwBaseAlloc` at `0x180032c45`
- `fwbase!FwBaseAlloc` at `0x180032bb6`
- `fwbase!FwBaseAlloc` at `0x180032c45`
- `fwbase!FwSizeTMultiply` at `0x180032c30`
- `fwbase!FwSizeTMultiply` at `0x180032c30`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180032bf3`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180032c88`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180032bf3`
- `fwbase!IsRuleOldGlobalOpenPort` at `0x180032c88`
- `fwbase!FwHResultToWindowsError` at `0x180032db3`
- `fwbase!FwHResultToWindowsError` at `0x180032db3`
- `fwbase!FwReportErrorAsWinError` at `0x180032b6b`
- `fwbase!FwReportErrorAsWinError` at `0x180032b6b`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180032bdd`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180032c6a`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180032bdd`
- `fwbase!IsRuleOpenPortOrAuthApp` at `0x180032c6a`
- `fwbase!FwStringCopy` at `0x180032cc3`
- `fwbase!FwStringCopy` at `0x180032cc3`

## string_xrefs

- `0x180032b5a`: `FWOpenPolicyStore`
- `0x180032d66`: `CopySubnetRestrictions`
- `0x180032d5a`: `CopyAddrRanges`

## pseudocode

```c
__int64 __fastcall IcfGetDynamicFwPorts(__int64 a1, _QWORD *a2)
{
  unsigned int v3; // eax
  const char *v4; // rdx
  __int64 v5; // r8
  int v6; // ebx
  unsigned int *v7; // rdi
  struct _tag_FW_RULE *i; // rbx
  __int64 v9; // rdx
  __int64 v11; // rax
  struct _tag_FW_RULE *v12; // rbx
  unsigned int v13; // esi
  __int64 v14; // rcx
  int v15; // eax
  unsigned __int64 v16; // r14
  __int64 v17; // rcx
  __int64 v18; // [rsp+30h] [rbp-38h] BYREF
  struct _tag_FW_RULE *v19; // [rsp+38h] [rbp-30h] BYREF
  __int64 v20; // [rsp+40h] [rbp-28h] BYREF
  __int64 v21; // [rsp+48h] [rbp-20h] BYREF
  int v22; // [rsp+50h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids);
  v20 = 0;
  v19 = 0;
  v22 = 0;
  v18 = 0;
  v3 = FWOpenPolicyStore(0x221u, 0, 5u, 1u, 0, &v20);
  if ( v3 )
  {
    v4 = "FWOpenPolicyStore";
LABEL_6:
    v5 = v3;
LABEL_7:
    v6 = FwReportErrorAsWinError("IcfGetDynamicFwPorts", v4, v5);
    goto LABEL_42;
  }
  v3 = FWEnumFirewallRules(v20, 0x10000, 0x80000000, 9, (__int64)&v22, (__int64)&v19);
  if ( v3 )
  {
    v4 = "FWEnumFirewallRules";
    goto LABEL_6;
  }
  v18 = FwBaseAlloc(16);
  v7 = (unsigned int *)v18;
  if ( !v18 )
  {
LABEL_11:
    v5 = 8;
    v4 = "FwAlloc";
    goto LABEL_7;
  }
  for ( i = v19; i; i = *(struct _tag_FW_RULE **)i )
  {
    if ( (unsigned int)IsRuleOpenPortOrAuthApp(i)
      && (*((_BYTE *)i + 292) & 1) != 0
      && (unsigned int)IsRuleOldGlobalOpenPort(i)
      && *((_DWORD *)i + 85) == 3
      && *((_DWORD *)i + 72) == 3 )
    {
      ++*v7;
    }
  }
  if ( *v7 )
  {
    v9 = *v7;
    v21 = 0;
    if ( (int)FwSizeTMultiply(128, v9, &v21) < 0 )
      return 8;
    v11 = FwBaseAlloc(v21);
    *((_QWORD *)v7 + 1) = v11;
    if ( !v11 )
      goto LABEL_11;
    v12 = v19;
    v13 = 0;
    while ( v12 )
    {
      if ( (unsigned int)IsRuleOpenPortOrAuthApp(v12)
        && (*((_BYTE *)v12 + 292) & 1) != 0
        && (unsigned int)IsRuleOldGlobalOpenPort(v12)
        && *((_DWORD *)v12 + 85) == 3
        && *((_DWORD *)v12 + 72) == 3 )
      {
        v14 = *((_QWORD *)v12 + 3);
        if ( v14 )
        {
          v15 = FwStringCopy(v14, *((_QWORD *)v7 + 1) + ((unsigned __int64)v13 << 7));
          if ( v15 < 0 )
          {
            v17 = (unsigned int)v15;
            return FwHResultToWindowsError(v17);
          }
        }
        v16 = (unsigned __int64)v13 << 7;
        *(_DWORD *)(*((_QWORD *)v7 + 1) + v16 + 28) = 2;
        *(_WORD *)(*((_QWORD *)v7 + 1) + v16 + 32) = **((_WORD **)v12 + 9);
        *(_DWORD *)(*((_QWORD *)v7 + 1) + v16 + 36) = *((unsigned __int16 *)v12 + 24);
        *(_DWORD *)(*((_QWORD *)v7 + 1) + v16 + 40) = 1;
        v3 = CopySubnetRestrictions(
               v12,
               (struct ICF_SUBNETS_ *)(v16 + *((_QWORD *)v7 + 1) + 48LL),
               (struct ICF_SUBNETS6_ *)(v16 + *((_QWORD *)v7 + 1) + 72LL));
        if ( v3 )
        {
          v4 = "CopySubnetRestrictions";
          goto LABEL_6;
        }
        v3 = CopyAddrRanges(
               v12,
               (struct ICF_RANGES_ *)(v16 + *((_QWORD *)v7 + 1) + 96LL),
               (struct ICF_RANGES6_ *)(v16 + *((_QWORD *)v7 + 1) + 112LL));
        if ( v3 )
        {
          v4 = "CopyAddrRanges";
          goto LABEL_6;
        }
        ++v13;
      }
      v12 = *(struct _tag_FW_RULE **)v12;
    }
  }
  v6 = 0;
  *a2 = v7;
LABEL_42:
  if ( v20 )
    FWClosePolicyStore();
  if ( v19 )
    FWFreeFirewallRules(v19);
  if ( v6 < 0 )
    IcfFreeDynamicFwPorts(&v18);
  if ( (unsigned int)IsRpcError(v6) )
    v6 = -2147023174;
  v17 = (unsigned int)v6;
  return FwHResultToWindowsError(v17);
}

```

## disassembly

```asm
0x180032ac0  push    rbp
0x180032ac2  push    rbx
0x180032ac3  push    rsi
0x180032ac4  push    rdi
0x180032ac5  push    r14
0x180032ac7  push    r15
0x180032ac9  mov     rbp, rsp
0x180032acc  sub     rsp, 68h
0x180032ad0  mov     rax, cs:__security_cookie
0x180032ad7  xor     rax, rsp
0x180032ada  mov     [rbp+var_10], rax
0x180032ade  mov     r15, rdx
0x180032ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x180032ae8  lea     rax, WPP_GLOBAL_Control
0x180032aef  mov     esi, 8
0x180032af4  cmp     rcx, rax
0x180032af7  jz      short loc_180032B12
0x180032af9  test    [rcx+1Ch], sil
0x180032afd  jz      short loc_180032B12
0x180032aff  mov     rcx, [rcx+10h]
0x180032b03  lea     edx, [rsi+1Fh]
0x180032b06  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x180032b0d  call    WPP_SF_
0x180032b12  xor     edx, edx
0x180032b14  mov     [rbp+var_28], 0
0x180032b1c  lea     rax, [rbp+var_28]
0x180032b20  mov     [rbp+var_30], 0
0x180032b28  mov     [rsp+68h+var_40], rax
0x180032b2d  mov     ecx, 221h
0x180032b32  mov     [rbp+var_18], 0
0x180032b39  lea     r9d, [rdx+1]
0x180032b3d  mov     [rbp+var_38], 0
0x180032b45  lea     r8d, [rdx+5]
0x180032b49  mov     dword ptr [rsp+68h+var_48], 0
0x180032b51  call    FWOpenPolicyStore
0x180032b56  test    eax, eax
0x180032b58  jz      short loc_180032B78
0x180032b5a  lea     rdx, aFwopenpolicyst_1; "FWOpenPolicyStore"
0x180032b61  mov     r8d, eax
0x180032b64  lea     rcx, aIcfgetdynamicf_0; "IcfGetDynamicFwPorts"
0x180032b6b  call    cs:__imp_FwReportErrorAsWinError
0x180032b71  mov     ebx, eax
0x180032b73  jmp     loc_180032D77
0x180032b78  mov     rcx, [rbp+var_28]
0x180032b7c  lea     rax, [rbp+var_30]
0x180032b80  mov     [rsp+68h+var_40], rax
0x180032b85  mov     r9d, 9
0x180032b8b  lea     rax, [rbp+var_18]
0x180032b8f  mov     edx, 10000h
0x180032b94  mov     r8d, 80000000h
0x180032b9a  mov     [rsp+68h+var_48], rax
0x180032b9f  call    FWEnumFirewallRules
0x180032ba4  test    eax, eax
0x180032ba6  jz      short loc_180032BB1
0x180032ba8  lea     rdx, aFwenumfirewall_0; "FWEnumFirewallRules"
0x180032baf  jmp     short loc_180032B61
0x180032bb1  mov     ecx, 10h
0x180032bb6  call    cs:__imp_FwBaseAlloc
0x180032bbc  mov     [rbp+var_38], rax
0x180032bc0  mov     rdi, rax
0x180032bc3  test    rax, rax
0x180032bc6  jnz     short loc_180032BD4
0x180032bc8  mov     r8d, esi
0x180032bcb  lea     rdx, aFwalloc_0; "FwAlloc"
0x180032bd2  jmp     short loc_180032B64
0x180032bd4  mov     rbx, [rbp+var_30]
0x180032bd8  jmp     short loc_180032C14
0x180032bda  mov     rcx, rbx
0x180032bdd  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180032be3  test    eax, eax
0x180032be5  jz      short loc_180032C11
0x180032be7  test    byte ptr [rbx+124h], 1
0x180032bee  jz      short loc_180032C11
0x180032bf0  mov     rcx, rbx
0x180032bf3  call    cs:__imp_IsRuleOldGlobalOpenPort
0x180032bf9  test    eax, eax
0x180032bfb  jz      short loc_180032C11
0x180032bfd  cmp     dword ptr [rbx+154h], 3
0x180032c04  jnz     short loc_180032C11
0x180032c06  cmp     dword ptr [rbx+120h], 3
0x180032c0d  jnz     short loc_180032C11
0x180032c0f  inc     dword ptr [rdi]
0x180032c11  mov     rbx, [rbx]
0x180032c14  test    rbx, rbx
0x180032c17  jnz     short loc_180032BDA
0x180032c19  cmp     [rdi], ebx
0x180032c1b  jz      loc_180032D72
0x180032c21  mov     edx, [rdi]
0x180032c23  lea     r8, [rbp+var_20]
0x180032c27  mov     ecx, 80h
0x180032c2c  mov     [rbp+var_20], rbx
0x180032c30  call    cs:__imp_FwSizeTMultiply
0x180032c36  test    eax, eax
0x180032c38  jns     short loc_180032C41
0x180032c3a  mov     eax, esi
0x180032c3c  jmp     loc_180032DB9
0x180032c41  mov     rcx, [rbp+var_20]
0x180032c45  call    cs:__imp_FwBaseAlloc
0x180032c4b  mov     [rdi+8], rax
0x180032c4f  test    rax, rax
0x180032c52  jz      loc_180032BC8
0x180032c58  mov     rbx, [rbp+var_30]
0x180032c5c  xor     esi, esi
0x180032c5e  test    rbx, rbx
0x180032c61  jz      loc_180032D72
0x180032c67  mov     rcx, rbx
0x180032c6a  call    cs:__imp_IsRuleOpenPortOrAuthApp
0x180032c70  test    eax, eax
0x180032c72  jz      loc_180032D4E
0x180032c78  test    byte ptr [rbx+124h], 1
0x180032c7f  jz      loc_180032D4E
0x180032c85  mov     rcx, rbx
0x180032c88  call    cs:__imp_IsRuleOldGlobalOpenPort
0x180032c8e  test    eax, eax
0x180032c90  jz      loc_180032D4E
0x180032c96  cmp     dword ptr [rbx+154h], 3
0x180032c9d  jnz     loc_180032D4E
0x180032ca3  cmp     dword ptr [rbx+120h], 3
0x180032caa  jnz     loc_180032D4E
0x180032cb0  mov     rcx, [rbx+18h]
0x180032cb4  test    rcx, rcx
0x180032cb7  jz      short loc_180032CD1
0x180032cb9  mov     edx, esi
0x180032cbb  shl     rdx, 7
0x180032cbf  add     rdx, [rdi+8]
0x180032cc3  call    cs:__imp_FwStringCopy
0x180032cc9  test    eax, eax
0x180032ccb  js      loc_180032D56
0x180032cd1  mov     rax, [rdi+8]
0x180032cd5  mov     r14d, esi
0x180032cd8  shl     r14, 7
0x180032cdc  mov     dword ptr [rax+r14+1Ch], 2
0x180032ce5  mov     rax, [rbx+48h]
0x180032ce9  mov     rcx, [rdi+8]
0x180032ced  movzx   eax, word ptr [rax]
0x180032cf0  mov     [rcx+r14+20h], ax
0x180032cf6  mov     rax, [rdi+8]
0x180032cfa  movzx   ecx, word ptr [rbx+30h]
0x180032cfe  mov     [rax+r14+24h], ecx
0x180032d03  mov     rcx, rbx; struct _tag_FW_RULE *
0x180032d06  mov     rax, [rdi+8]
0x180032d0a  mov     dword ptr [rax+r14+28h], 1
0x180032d13  mov     rax, [rdi+8]
0x180032d17  lea     r8, [rax+48h]
0x180032d1b  lea     rdx, [rax+30h]
0x180032d1f  add     r8, r14; struct ICF_SUBNETS6_ *
0x180032d22  add     rdx, r14; struct ICF_SUBNETS_ *
0x180032d25  call    ?CopySubnetRestrictions@@YAKPEBU_tag_FW_RULE@@PEAUICF_SUBNETS_@@PEAUICF_SUBNETS6_@@@Z; CopySubnetRestrictions(_tag_FW_RULE const *,ICF_SUBNETS_ *,ICF_SUBNETS6_ *)
0x180032d2a  test    eax, eax
0x180032d2c  jnz     short loc_180032D66
0x180032d2e  mov     rax, [rdi+8]
0x180032d32  mov     rcx, rbx; struct _tag_FW_RULE *
0x180032d35  lea     r8, [rax+70h]
0x180032d39  lea     rdx, [rax+60h]
0x180032d3d  add     r8, r14; struct ICF_RANGES6_ *
0x180032d40  add     rdx, r14; struct ICF_RANGES_ *
0x180032d43  call    ?CopyAddrRanges@@YAKPEBU_tag_FW_RULE@@PEAUICF_RANGES_@@PEAUICF_RANGES6_@@@Z; CopyAddrRanges(_tag_FW_RULE const *,ICF_RANGES_ *,ICF_RANGES6_ *)
0x180032d48  test    eax, eax
0x180032d4a  jnz     short loc_180032D5A
0x180032d4c  inc     esi
0x180032d4e  mov     rbx, [rbx]
0x180032d51  jmp     loc_180032C5E
0x180032d56  mov     ecx, eax
0x180032d58  jmp     short loc_180032DB3
0x180032d5a  lea     rdx, aCopyaddrranges; "CopyAddrRanges"
0x180032d61  jmp     loc_180032B61
0x180032d66  lea     rdx, aCopysubnetrest; "CopySubnetRestrictions"
0x180032d6d  jmp     loc_180032B61
0x180032d72  xor     ebx, ebx
0x180032d74  mov     [r15], rdi
0x180032d77  mov     rcx, [rbp+var_28]
0x180032d7b  test    rcx, rcx
0x180032d7e  jz      short loc_180032D85
0x180032d80  call    FWClosePolicyStore
0x180032d85  mov     rcx, [rbp+var_30]
0x180032d89  test    rcx, rcx
0x180032d8c  jz      short loc_180032D93
0x180032d8e  call    FWFreeFirewallRules
0x180032d93  test    ebx, ebx
0x180032d95  jns     short loc_180032DA0
0x180032d97  lea     rcx, [rbp+var_38]
0x180032d9b  call    IcfFreeDynamicFwPorts
0x180032da0  mov     ecx, ebx; int
0x180032da2  call    ?IsRpcError@@YAHJ@Z; IsRpcError(long)
0x180032da7  mov     ecx, 800706BAh
0x180032dac  test    eax, eax
0x180032dae  cmovnz  ebx, ecx
0x180032db1  mov     ecx, ebx
0x180032db3  call    cs:__imp_FwHResultToWindowsError
0x180032db9  mov     rcx, [rbp+var_10]
0x180032dbd  xor     rcx, rsp; StackCookie
0x180032dc0  call    __security_check_cookie
0x180032dc5  add     rsp, 68h
0x180032dc9  pop     r15
0x180032dcb  pop     r14
0x180032dcd  pop     rdi
0x180032dce  pop     rsi
0x180032dcf  pop     rbx
0x180032dd0  pop     rbp
0x180032dd1  retn
```
