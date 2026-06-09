# IcfGetProfile

- ea: `0x180032f90`
- end: `0x1800332b1`
- name: `IcfGetProfile`
- size: `801`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, service_task`

## callees

- `0x180009080`
- `0x18000b8c0`
- `0x18000c130`
- `0x18000c560`
- `0x1800197a4`
- `0x1800277b0`
- `0x18003104c`
- `0x1800312cc`
- `0x180031770`
- `0x180031b70`
- `0x180031d30`
- `0x180032180`
- `0x180032264`
- `0x180032720`
- `0x180032a20`
- `0x180032f90`

## import_xrefs

- `fwbase!FwBaseAlloc` at `0x180033085`
- `fwbase!FwBaseAlloc` at `0x1800330d5`
- `fwbase!FwBaseAlloc` at `0x180033085`
- `fwbase!FwBaseAlloc` at `0x1800330d5`
- `fwbase!FwHResultToWindowsError` at `0x18003328e`
- `fwbase!FwHResultToWindowsError` at `0x18003328e`
- `fwbase!FwReportErrorAsWinError` at `0x1800330a8`
- `fwbase!FwReportErrorAsWinError` at `0x1800330a8`
- `fwbase!FwReportReturnError` at `0x180033025`
- `fwbase!FwReportReturnError` at `0x180033025`

## string_xrefs

- `0x1800330c7`: `FWOpenPolicyStore`
- `0x180033120`: `CopyConfigToProfile`
- `0x180033185`: `CopyRemoteAdminSettingsToProfile`
- `0x1800331a4`: `CopyServicesSettingsToProfile`
- `0x1800331c9`: `CopyPortsSettingsToProfile`
- `0x1800331f0`: `CopyAuthAppsSettingsToProfile`

## pseudocode

```c
__int64 __fastcall IcfGetProfile(__int64 a1, int a2, int a3, __int64 *a4)
{
  __int16 v7; // r13
  int v8; // edi
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // r14d
  unsigned int v12; // edi
  unsigned int v13; // eax
  __int64 v14; // rax
  __int64 v15; // r8
  const char *v16; // rdx
  _DWORD *v18; // rax
  __int64 v19; // rbx
  unsigned int CurrentProfileType; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  _DWORD *v27; // [rsp+30h] [rbp-38h] BYREF
  struct _tag_FW_RULE *v28; // [rsp+38h] [rbp-30h] BYREF
  __int64 v29; // [rsp+40h] [rbp-28h] BYREF
  int v30; // [rsp+48h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids);
  v29 = 0;
  v27 = 0;
  v28 = 0;
  v30 = 0;
  v7 = 1;
  switch ( a2 )
  {
    case 0:
      v11 = 1;
LABEL_11:
      if ( a3 )
      {
        if ( a3 == 1 )
        {
          v12 = 2;
        }
        else
        {
          if ( a3 != 2 )
            break;
          v12 = 0x80000000;
        }
      }
      else
      {
        v12 = 1;
      }
      v13 = FWOpenPolicyStore(0x221u, 0, v11, 1u, 0, &v29);
      if ( v13 == 2 )
      {
        v14 = FwBaseAlloc(240);
        v27 = (_DWORD *)v14;
        if ( v14 )
        {
          *a4 = v14;
          return 0;
        }
      }
      else
      {
        if ( v13 )
        {
          v15 = v13;
          v16 = "FWOpenPolicyStore";
          goto LABEL_20;
        }
        v18 = (_DWORD *)FwBaseAlloc(240);
        v27 = v18;
        v19 = (__int64)v18;
        if ( v18 )
        {
          if ( a3 == 2 )
          {
            CurrentProfileType = IcfGetCurrentProfileType(0, v18);
            if ( CurrentProfileType )
            {
              v15 = CurrentProfileType;
              v16 = "IcfGetCurrentProfileType";
              goto LABEL_20;
            }
          }
          else
          {
            *v18 = a3;
          }
          v21 = CopyConfigToProfile(v29, v12, v11, v19);
          if ( v21 )
          {
            v15 = v21;
            v16 = "CopyConfigToProfile";
          }
          else
          {
            v22 = FWEnumFirewallRules(v29, 196608, v12, v7, (__int64)&v30, (__int64)&v28);
            if ( v22 )
            {
              v15 = v22;
              v16 = "FWEnumFirewallRules";
            }
            else
            {
              CopyICMPSettingsToProfile(v28, (struct ICF_PROFILE_ *)v19);
              v23 = CopyRemoteAdminSettingsToProfile(v28, (struct ICF_PROFILE_ *)v19);
              if ( v23 )
              {
                v15 = v23;
                v16 = "CopyRemoteAdminSettingsToProfile";
              }
              else
              {
                v24 = CopyServicesSettingsToProfile(v28, (struct ICF_PROFILE_ *)v19);
                if ( v24 )
                {
                  v15 = v24;
                  v16 = "CopyServicesSettingsToProfile";
                }
                else
                {
                  v25 = CopyPortsSettingsToProfile(v29, v12, (__int64 *)v28, v19);
                  if ( v25 )
                  {
                    v15 = v25;
                    v16 = "CopyPortsSettingsToProfile";
                  }
                  else
                  {
                    v26 = CopyAuthAppsSettingsToProfile(v29, v12, (__int64 *)v28, v19);
                    if ( !v26 )
                    {
                      *a4 = v19;
                      v8 = 0;
                      if ( a2
                        || (*(_DWORD *)(v19 + 4) = 0, v30)
                        || *(_DWORD *)(v19 + 8)
                        || *(_DWORD *)(v19 + 12)
                        || *(_DWORD *)(v19 + 16)
                        || *(_DWORD *)(v19 + 20)
                        || *(_DWORD *)(v19 + 124)
                        || *(_DWORD *)(v19 + 128)
                        || !*(_DWORD *)(v19 + 120)
                        || !*(_QWORD *)(v19 + 112)
                        || *(_DWORD *)(v19 + 196)
                        || *(_DWORD *)(v19 + 236) )
                      {
                        *(_DWORD *)(v19 + 4) = 2;
                      }
                      goto LABEL_54;
                    }
                    v15 = v26;
                    v16 = "CopyAuthAppsSettingsToProfile";
                  }
                }
              }
            }
          }
          goto LABEL_20;
        }
      }
      v15 = 8;
      v16 = "FwAlloc";
LABEL_20:
      v8 = FwReportErrorAsWinError("IcfGetProfile", v16, v15);
      goto LABEL_54;
    case 1:
      v11 = 2;
      goto LABEL_11;
    case 2:
      v11 = 5;
      v7 = 9;
      goto LABEL_11;
  }
  v8 = -2147024809;
  FwReportReturnError("IcfGetProfile", 2147942487LL);
LABEL_54:
  if ( v29 )
    FWClosePolicyStore(v29);
  if ( v28 )
    FWFreeFirewallRules((__int64)v28, v9, v10);
  if ( v8 < 0 )
    IcfFreeProfile(&v27);
  if ( (unsigned int)IsRpcError(v8) )
    v8 = -2147023174;
  return FwHResultToWindowsError((unsigned int)v8);
}

```

## disassembly

```asm
0x180032f90  push    rbp
0x180032f92  push    rbx
0x180032f93  push    rsi
0x180032f94  push    rdi
0x180032f95  push    r12
0x180032f97  push    r13
0x180032f99  push    r14
0x180032f9b  push    r15
0x180032f9d  mov     rbp, rsp
0x180032fa0  sub     rsp, 68h
0x180032fa4  mov     rax, cs:__security_cookie
0x180032fab  xor     rax, rsp
0x180032fae  mov     [rbp+var_18], rax
0x180032fb2  mov     r12, r9
0x180032fb5  mov     esi, r8d
0x180032fb8  mov     r15d, edx
0x180032fbb  mov     rcx, cs:WPP_GLOBAL_Control
0x180032fc2  lea     rax, WPP_GLOBAL_Control
0x180032fc9  cmp     rcx, rax
0x180032fcc  jz      short loc_180032FE9
0x180032fce  test    byte ptr [rcx+1Ch], 8
0x180032fd2  jz      short loc_180032FE9
0x180032fd4  mov     rcx, [rcx+10h]
0x180032fd8  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x180032fdf  mov     edx, 25h ; '%'
0x180032fe4  call    WPP_SF_
0x180032fe9  xor     edx, edx
0x180032feb  mov     ecx, r15d
0x180032fee  mov     [rbp+var_28], rdx
0x180032ff2  mov     [rbp+var_38], rdx
0x180032ff6  mov     [rbp+var_30], rdx
0x180032ffa  mov     [rbp+var_20], edx
0x180032ffd  lea     r9d, [rdx+1]
0x180033001  lea     ebx, [rdx+2]
0x180033004  movzx   r13d, r9w
0x180033008  test    r15d, r15d
0x18003300b  jz      short loc_180033041
0x18003300d  sub     ecx, r9d
0x180033010  jz      short loc_18003303C
0x180033012  cmp     ecx, r9d
0x180033015  jz      short loc_180033030
0x180033017  mov     edx, 80070057h
0x18003301c  lea     rcx, aIcfgetprofile_0; "IcfGetProfile"
0x180033023  mov     edi, edx
0x180033025  call    cs:__imp_FwReportReturnError
0x18003302b  jmp     loc_180033252
0x180033030  mov     r14d, 5
0x180033036  lea     r13d, [r14+4]
0x18003303a  jmp     short loc_180033044
0x18003303c  mov     r14d, ebx
0x18003303f  jmp     short loc_180033044
0x180033041  mov     r14d, r9d
0x180033044  mov     ecx, esi
0x180033046  test    esi, esi
0x180033048  jz      short loc_18003305F
0x18003304a  sub     ecx, r9d
0x18003304d  jz      short loc_18003305B
0x18003304f  cmp     ecx, r9d
0x180033052  jnz     short loc_180033017
0x180033054  mov     edi, 80000000h
0x180033059  jmp     short loc_180033062
0x18003305b  mov     edi, ebx
0x18003305d  jmp     short loc_180033062
0x18003305f  mov     edi, r9d
0x180033062  lea     rax, [rbp+var_28]
0x180033066  mov     ecx, 221h
0x18003306b  mov     [rsp+68h+var_40], rax
0x180033070  mov     r8d, r14d
0x180033073  mov     dword ptr [rsp+68h+var_48], edx
0x180033077  call    FWOpenPolicyStore
0x18003307c  cmp     eax, ebx
0x18003307e  jnz     short loc_1800330C0
0x180033080  mov     ecx, 0F0h
0x180033085  call    cs:__imp_FwBaseAlloc
0x18003308b  mov     [rbp+var_38], rax
0x18003308f  test    rax, rax
0x180033092  jnz     short loc_1800330B5
0x180033094  mov     r8d, 8
0x18003309a  lea     rdx, aFwalloc_0; "FwAlloc"
0x1800330a1  lea     rcx, aIcfgetprofile_0; "IcfGetProfile"
0x1800330a8  call    cs:__imp_FwReportErrorAsWinError
0x1800330ae  mov     edi, eax
0x1800330b0  jmp     loc_180033252
0x1800330b5  mov     [r12], rax
0x1800330b9  xor     eax, eax
0x1800330bb  jmp     loc_180033294
0x1800330c0  test    eax, eax
0x1800330c2  jz      short loc_1800330D0
0x1800330c4  mov     r8d, eax
0x1800330c7  lea     rdx, aFwopenpolicyst_1; "FWOpenPolicyStore"
0x1800330ce  jmp     short loc_1800330A1
0x1800330d0  mov     ecx, 0F0h
0x1800330d5  call    cs:__imp_FwBaseAlloc
0x1800330db  mov     [rbp+var_38], rax
0x1800330df  mov     rbx, rax
0x1800330e2  test    rax, rax
0x1800330e5  jz      short loc_180033094
0x1800330e7  cmp     esi, 2
0x1800330ea  jnz     short loc_180033106
0x1800330ec  mov     rdx, rax
0x1800330ef  xor     ecx, ecx
0x1800330f1  call    IcfGetCurrentProfileType
0x1800330f6  test    eax, eax
0x1800330f8  jz      short loc_180033108
0x1800330fa  mov     r8d, eax
0x1800330fd  lea     rdx, aIcfgetcurrentp_0; "IcfGetCurrentProfileType"
0x180033104  jmp     short loc_1800330A1
0x180033106  mov     [rax], esi
0x180033108  mov     rcx, [rbp+var_28]
0x18003310c  mov     r9, rbx
0x18003310f  mov     r8d, r14d
0x180033112  mov     edx, edi
0x180033114  call    ?CopyConfigToProfile@@YAKPEAXW4_tag_FW_PROFILE_TYPE@@W4_tag_FW_STORE_TYPE@@PEAUICF_PROFILE_@@@Z; CopyConfigToProfile(void *,_tag_FW_PROFILE_TYPE,_tag_FW_STORE_TYPE,ICF_PROFILE_ *)
0x180033119  test    eax, eax
0x18003311b  jz      short loc_18003312C
0x18003311d  mov     r8d, eax
0x180033120  lea     rdx, aCopyconfigtopr; "CopyConfigToProfile"
0x180033127  jmp     loc_1800330A1
0x18003312c  mov     rcx, [rbp+var_28]
0x180033130  lea     rax, [rbp+var_30]
0x180033134  mov     [rsp+68h+var_40], rax
0x180033139  movzx   r9d, r13w
0x18003313d  lea     rax, [rbp+var_20]
0x180033141  mov     r8d, edi
0x180033144  mov     edx, 30000h
0x180033149  mov     [rsp+68h+var_48], rax
0x18003314e  call    FWEnumFirewallRules
0x180033153  test    eax, eax
0x180033155  jz      short loc_180033166
0x180033157  mov     r8d, eax
0x18003315a  lea     rdx, aFwenumfirewall_0; "FWEnumFirewallRules"
0x180033161  jmp     loc_1800330A1
0x180033166  mov     rcx, [rbp+var_30]; struct _tag_FW_RULE *
0x18003316a  mov     rdx, rbx; struct ICF_PROFILE_ *
0x18003316d  call    ?CopyICMPSettingsToProfile@@YAXPEAU_tag_FW_RULE@@PEAUICF_PROFILE_@@@Z; CopyICMPSettingsToProfile(_tag_FW_RULE *,ICF_PROFILE_ *)
0x180033172  mov     rcx, [rbp+var_30]; struct _tag_FW_RULE *
0x180033176  mov     rdx, rbx; struct ICF_PROFILE_ *
0x180033179  call    ?CopyRemoteAdminSettingsToProfile@@YAKPEAU_tag_FW_RULE@@PEAUICF_PROFILE_@@@Z; CopyRemoteAdminSettingsToProfile(_tag_FW_RULE *,ICF_PROFILE_ *)
0x18003317e  test    eax, eax
0x180033180  jz      short loc_180033191
0x180033182  mov     r8d, eax
0x180033185  lea     rdx, aCopyremoteadmi; "CopyRemoteAdminSettingsToProfile"
0x18003318c  jmp     loc_1800330A1
0x180033191  mov     rcx, [rbp+var_30]; struct _tag_FW_RULE *
0x180033195  mov     rdx, rbx; struct ICF_PROFILE_ *
0x180033198  call    ?CopyServicesSettingsToProfile@@YAKPEBU_tag_FW_RULE@@PEAUICF_PROFILE_@@@Z; CopyServicesSettingsToProfile(_tag_FW_RULE const *,ICF_PROFILE_ *)
0x18003319d  test    eax, eax
0x18003319f  jz      short loc_1800331B0
0x1800331a1  mov     r8d, eax
0x1800331a4  lea     rdx, aCopyservicesse; "CopyServicesSettingsToProfile"
0x1800331ab  jmp     loc_1800330A1
0x1800331b0  mov     r8, [rbp+var_30]
0x1800331b4  mov     r9, rbx
0x1800331b7  mov     rcx, [rbp+var_28]
0x1800331bb  mov     edx, edi
0x1800331bd  call    ?CopyPortsSettingsToProfile@@YAKPEAXW4_tag_FW_PROFILE_TYPE@@PEBU_tag_FW_RULE@@PEAUICF_PROFILE_@@@Z; CopyPortsSettingsToProfile(void *,_tag_FW_PROFILE_TYPE,_tag_FW_RULE const *,ICF_PROFILE_ *)
0x1800331c2  test    eax, eax
0x1800331c4  jz      short loc_1800331D5
0x1800331c6  mov     r8d, eax
0x1800331c9  lea     rdx, aCopyportssetti; "CopyPortsSettingsToProfile"
0x1800331d0  jmp     loc_1800330A1
0x1800331d5  mov     r8, [rbp+var_30]
0x1800331d9  mov     r9, rbx
0x1800331dc  mov     rcx, [rbp+var_28]
0x1800331e0  mov     edx, edi
0x1800331e2  call    ?CopyAuthAppsSettingsToProfile@@YAKPEAXW4_tag_FW_PROFILE_TYPE@@PEBU_tag_FW_RULE@@PEAUICF_PROFILE_@@@Z; CopyAuthAppsSettingsToProfile(void *,_tag_FW_PROFILE_TYPE,_tag_FW_RULE const *,ICF_PROFILE_ *)
0x1800331e7  xor     ecx, ecx
0x1800331e9  test    eax, eax
0x1800331eb  jz      short loc_1800331FC
0x1800331ed  mov     r8d, eax
0x1800331f0  lea     rdx, aCopyauthappsse; "CopyAuthAppsSettingsToProfile"
0x1800331f7  jmp     loc_1800330A1
0x1800331fc  mov     [r12], rbx
0x180033200  mov     edi, ecx
0x180033202  test    r15d, r15d
0x180033205  jnz     short loc_18003324B
0x180033207  mov     [rbx+4], ecx
0x18003320a  cmp     [rbp+var_20], ecx
0x18003320d  jnz     short loc_18003324B
0x18003320f  cmp     [rbx+8], ecx
0x180033212  jnz     short loc_18003324B
0x180033214  cmp     [rbx+0Ch], ecx
0x180033217  jnz     short loc_18003324B
0x180033219  cmp     [rbx+10h], ecx
0x18003321c  jnz     short loc_18003324B
0x18003321e  cmp     [rbx+14h], ecx
0x180033221  jnz     short loc_18003324B
0x180033223  cmp     [rbx+7Ch], ecx
0x180033226  jnz     short loc_18003324B
0x180033228  cmp     [rbx+80h], ecx
0x18003322e  jnz     short loc_18003324B
0x180033230  cmp     [rbx+78h], ecx
0x180033233  jz      short loc_18003324B
0x180033235  cmp     [rbx+70h], rcx
0x180033239  jz      short loc_18003324B
0x18003323b  cmp     [rbx+0C4h], ecx
0x180033241  jnz     short loc_18003324B
0x180033243  cmp     [rbx+0ECh], ecx
0x180033249  jz      short loc_180033252
0x18003324b  mov     dword ptr [rbx+4], 2
0x180033252  mov     rcx, [rbp+var_28]
0x180033256  test    rcx, rcx
0x180033259  jz      short loc_180033260
0x18003325b  call    FWClosePolicyStore
0x180033260  mov     rcx, [rbp+var_30]
0x180033264  test    rcx, rcx
0x180033267  jz      short loc_18003326E
0x180033269  call    FWFreeFirewallRules
0x18003326e  test    edi, edi
0x180033270  jns     short loc_18003327B
0x180033272  lea     rcx, [rbp+var_38]
0x180033276  call    IcfFreeProfile
0x18003327b  mov     ecx, edi; int
0x18003327d  call    ?IsRpcError@@YAHJ@Z; IsRpcError(long)
0x180033282  mov     ecx, 800706BAh
0x180033287  test    eax, eax
0x180033289  cmovnz  edi, ecx
0x18003328c  mov     ecx, edi
0x18003328e  call    cs:__imp_FwHResultToWindowsError
0x180033294  mov     rcx, [rbp+var_18]
0x180033298  xor     rcx, rsp; StackCookie
0x18003329b  call    __security_check_cookie
0x1800332a0  add     rsp, 68h
0x1800332a4  pop     r15
0x1800332a6  pop     r14
0x1800332a8  pop     r13
0x1800332aa  pop     r12
0x1800332ac  pop     rdi
0x1800332ad  pop     rsi
0x1800332ae  pop     rbx
0x1800332af  pop     rbp
0x1800332b0  retn
```
