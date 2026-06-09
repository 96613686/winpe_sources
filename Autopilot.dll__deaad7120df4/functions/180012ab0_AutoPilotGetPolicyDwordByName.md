# AutoPilotGetPolicyDwordByName

- ea: `0x180012ab0`
- end: `0x180012bdc`
- name: `AutoPilotGetPolicyDwordByName`
- size: `300`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180012ab0`
- `0x180013520`
- `0x180013580`
- `0x180013618`
- `0x1800189a4`

## string_xrefs

- `0x180012b29`: `onecoreuap\admin\moderndeployment\autopilot\dll\dllmain.cpp`

## pseudocode

```c
__int64 __fastcall AutoPilotGetPolicyDwordByName(const unsigned __int16 *a1, unsigned int *a2)
{
  const wchar_t *v3; // rbx
  int DwordPolicy; // eax
  __int64 v5; // rcx
  __int64 v6; // r8
  unsigned int v7; // edi
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+38h] [rbp-40h] BYREF
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
      v11 = *a2;
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
      v16 = &v11;
      v17 = 4;
      if ( !v3 )
        v3 = L"NULL";
      v13 = v3;
      McGenEventWrite_EventWriteTransfer(
        (__int64)L"NULL",
        (const EVENT_DESCRIPTOR *)AutopilotGetPolicyDwordByNameSucceeded,
        v6,
        3u,
        &v12);
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
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\dllmain.cpp",
      (const char *)v7);
    return v7;
  }
}

```

## disassembly

```asm
0x180012ab0  mov     [rsp+arg_10], rbx
0x180012ab5  mov     [rsp+arg_18], rsi
0x180012aba  push    rdi
0x180012abb  sub     rsp, 70h
0x180012abf  mov     rax, cs:__security_cookie
0x180012ac6  xor     rax, rsp
0x180012ac9  mov     [rsp+78h+var_10], rax
0x180012ace  mov     rsi, rdx
0x180012ad1  mov     rbx, rcx
0x180012ad4  call    ?GetDwordPolicy@AutopilotPolicyCache@Autopilot@Windows@Microsoft@@SAJPEBGPEAK@Z; Microsoft::Windows::Autopilot::AutopilotPolicyCache::GetDwordPolicy(ushort const *,ulong *)
0x180012ad9  xor     edx, edx
0x180012adb  mov     edi, eax
0x180012add  test    eax, eax
0x180012adf  jns     short loc_180012B41
0x180012ae1  mov     esi, 80070491h
0x180012ae6  cmp     eax, esi
0x180012ae8  jnz     short loc_180012B09
0x180012aea  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 1
0x180012af1  jz      short loc_180012B02
0x180012af3  mov     r8, rbx
0x180012af6  lea     rdx, AutopilotPolicyNotFound
0x180012afd  call    McTemplateU0z_EventWriteTransfer
0x180012b02  mov     eax, esi
0x180012b04  jmp     loc_180012BBC
0x180012b09  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180012b10  jz      short loc_180012B24
0x180012b12  mov     r9, rbx
0x180012b15  lea     rdx, AutopilotGetPolicyDwordByNameFailed
0x180012b1c  mov     r8d, edi
0x180012b1f  call    McTemplateU0dz_EventWriteTransfer
0x180012b24  mov     rcx, [rsp+78h]; this
0x180012b29  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012b30  mov     r9d, edi; char *
0x180012b33  mov     edx, 97h; void *
0x180012b38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012b3d  mov     eax, edi
0x180012b3f  jmp     short loc_180012BBC
0x180012b41  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180012b48  jz      short loc_180012BBA
0x180012b4a  mov     eax, [rsi]
0x180012b4c  mov     [rsp+78h+var_48], eax
0x180012b50  test    rbx, rbx
0x180012b53  jz      short loc_180012B6B
0x180012b55  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012b59  inc     rax
0x180012b5c  cmp     [rbx+rax*2], dx
0x180012b60  jnz     short loc_180012B59
0x180012b62  lea     eax, ds:2[rax*2]
0x180012b69  jmp     short loc_180012B70
0x180012b6b  mov     eax, 0Ah
0x180012b70  mov     [rsp+78h+var_28], eax
0x180012b74  lea     rcx, aNull_0; "NULL"
0x180012b7b  lea     rax, [rsp+78h+var_48]
0x180012b80  mov     [rsp+78h+var_24], edx
0x180012b84  test    rbx, rbx
0x180012b87  mov     [rsp+78h+var_20], rax
0x180012b8c  lea     rax, [rsp+78h+var_40]
0x180012b91  mov     [rsp+78h+var_18], 4
0x180012b9a  cmovz   rbx, rcx
0x180012b9e  mov     [rsp+78h+var_58], rax
0x180012ba3  mov     r9d, 3
0x180012ba9  mov     [rsp+78h+var_30], rbx
0x180012bae  lea     rdx, AutopilotGetPolicyDwordByNameSucceeded
0x180012bb5  call    McGenEventWrite_EventWriteTransfer
0x180012bba  xor     eax, eax
0x180012bbc  mov     rcx, [rsp+78h+var_10]
0x180012bc1  xor     rcx, rsp; StackCookie
0x180012bc4  call    __security_check_cookie
0x180012bc9  lea     r11, [rsp+78h+var_8]
0x180012bce  mov     rbx, [r11+20h]
0x180012bd2  mov     rsi, [r11+28h]
0x180012bd6  mov     rsp, r11
0x180012bd9  pop     rdi
0x180012bda  retn
```
