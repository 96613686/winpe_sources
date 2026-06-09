# AutoPilotGetPolicyDwordByName

- ea: `0x180012870`
- end: `0x18001299b`
- name: `AutoPilotGetPolicyDwordByName`
- size: `299`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x180012870`
- `0x180013280`
- `0x1800132d8`
- `0x180013370`
- `0x180018430`

## string_xrefs

- `0x1800128e9`: `onecoreuap\admin\moderndeployment\autopilot\dll\dllmain.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AutoPilotGetPolicyDwordByName(const unsigned __int16 *a1, unsigned int *a2)
{
  const wchar_t *v3; // rbx
  int DwordPolicy; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  unsigned int v7; // edi
  __int64 v9; // rax
  int v10; // eax
  int v11; // [rsp+20h] [rbp-58h]
  unsigned int v12; // [rsp+30h] [rbp-48h] BYREF
  const wchar_t *v13; // [rsp+48h] [rbp-30h]
  int v14; // [rsp+50h] [rbp-28h]
  int v15; // [rsp+54h] [rbp-24h]
  unsigned int *v16; // [rsp+58h] [rbp-20h]
  __int64 v17; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v3 = a1;
  DwordPolicy = Microsoft::Windows::Autopilot::AutopilotPolicyCache::GetDwordPolicy(a1, a2);
  v7 = DwordPolicy;
  if ( DwordPolicy >= 0 )
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
    {
      v12 = *a2;
      if ( v3 )
      {
        v9 = -1;
        do
          ++v9;
        while ( v3[v9] );
        v10 = 2 * v9 + 2;
      }
      else
      {
        v10 = 10;
      }
      v14 = v10;
      v15 = 0;
      v16 = &v12;
      v17 = 4;
      if ( !v3 )
        v3 = L"NULL";
      v13 = v3;
      McGenEventWrite_EventWriteTransfer(L"NULL", AutopilotGetPolicyDwordByNameSucceeded, v6, 3);
    }
    return 0;
  }
  else if ( DwordPolicy == -2147023727 )
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v5, AutopilotPolicyNotFound, v3);
    return 2147943569LL;
  }
  else
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      McTemplateU0dz_EventWriteTransfer(v5, AutopilotGetPolicyDwordByNameFailed, (unsigned int)DwordPolicy, v3);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\dllmain.cpp",
      (const char *)v7,
      v11);
    return v7;
  }
}

```

## disassembly

```asm
0x180012870  mov     [rsp+arg_10], rbx
0x180012875  mov     [rsp+arg_18], rsi
0x18001287a  push    rdi
0x18001287b  sub     rsp, 70h
0x18001287f  mov     rax, cs:__security_cookie
0x180012886  xor     rax, rsp
0x180012889  mov     [rsp+78h+var_10], rax
0x18001288e  mov     rsi, rdx
0x180012891  mov     rbx, rcx
0x180012894  call    ?GetDwordPolicy@AutopilotPolicyCache@Autopilot@Windows@Microsoft@@SAJPEBGPEAK@Z; Microsoft::Windows::Autopilot::AutopilotPolicyCache::GetDwordPolicy(ushort const *,ulong *)
0x180012899  xor     edx, edx
0x18001289b  mov     edi, eax
0x18001289d  test    eax, eax
0x18001289f  jns     short loc_180012901
0x1800128a1  mov     esi, 80070491h
0x1800128a6  cmp     eax, esi
0x1800128a8  jnz     short loc_1800128C9
0x1800128aa  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 1
0x1800128b1  jz      short loc_1800128C2
0x1800128b3  mov     r8, rbx
0x1800128b6  lea     rdx, AutopilotPolicyNotFound
0x1800128bd  call    McTemplateU0z_EventWriteTransfer
0x1800128c2  mov     eax, esi
0x1800128c4  jmp     loc_18001297C
0x1800128c9  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x1800128d0  jz      short loc_1800128E4
0x1800128d2  mov     r9, rbx
0x1800128d5  lea     rdx, AutopilotGetPolicyDwordByNameFailed
0x1800128dc  mov     r8d, edi
0x1800128df  call    McTemplateU0dz_EventWriteTransfer
0x1800128e4  mov     rcx, [rsp+78h]; this
0x1800128e9  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800128f0  mov     r9d, edi; char *
0x1800128f3  mov     edx, 97h; void *
0x1800128f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800128fd  mov     eax, edi
0x1800128ff  jmp     short loc_18001297C
0x180012901  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180012908  jz      short loc_18001297A
0x18001290a  mov     eax, [rsi]
0x18001290c  mov     [rsp+78h+var_48], eax
0x180012910  test    rbx, rbx
0x180012913  jz      short loc_18001292B
0x180012915  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012919  inc     rax
0x18001291c  cmp     [rbx+rax*2], dx
0x180012920  jnz     short loc_180012919
0x180012922  lea     eax, ds:2[rax*2]
0x180012929  jmp     short loc_180012930
0x18001292b  mov     eax, 0Ah
0x180012930  mov     [rsp+78h+var_28], eax
0x180012934  lea     rcx, aNull_0; "NULL"
0x18001293b  lea     rax, [rsp+78h+var_48]
0x180012940  mov     [rsp+78h+var_24], edx
0x180012944  test    rbx, rbx
0x180012947  mov     [rsp+78h+var_20], rax
0x18001294c  lea     rax, [rsp+78h+var_40]
0x180012951  mov     [rsp+78h+var_18], 4
0x18001295a  cmovz   rbx, rcx
0x18001295e  mov     qword ptr [rsp+78h+var_58], rax
0x180012963  mov     r9d, 3
0x180012969  mov     [rsp+78h+var_30], rbx
0x18001296e  lea     rdx, AutopilotGetPolicyDwordByNameSucceeded
0x180012975  call    McGenEventWrite_EventWriteTransfer
0x18001297a  xor     eax, eax
0x18001297c  mov     rcx, [rsp+78h+var_10]
0x180012981  xor     rcx, rsp; StackCookie
0x180012984  call    __security_check_cookie
0x180012989  lea     r11, [rsp+78h+var_8]
0x18001298e  mov     rbx, [r11+20h]
0x180012992  mov     rsi, [r11+28h]
0x180012996  mov     rsp, r11
0x180012999  pop     rdi
0x18001299a  retn
```
