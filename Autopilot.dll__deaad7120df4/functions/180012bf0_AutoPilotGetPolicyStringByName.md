# AutoPilotGetPolicyStringByName

- ea: `0x180012bf0`
- end: `0x180012c93`
- name: `AutoPilotGetPolicyStringByName`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180010764`
- `0x180012bf0`
- `0x180013580`
- `0x180013618`
- `0x18001369c`
- `0x180018ed0`

## string_xrefs

- `0x180012c4e`: `onecoreuap\admin\moderndeployment\autopilot\dll\dllmain.cpp`

## pseudocode

```c
__int64 __fastcall AutoPilotGetPolicyStringByName(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  int StringPolicy; // eax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  StringPolicy = Microsoft::Windows::Autopilot::AutopilotPolicyCache::GetStringPolicy(a1, a2);
  v5 = StringPolicy;
  if ( StringPolicy >= 0 )
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
      McTemplateU0zz_EventWriteTransfer(v4, AutopilotGetPolicyStringByNameSucceeded, a1, L"********");
    return 0;
  }
  else if ( StringPolicy == -2147023727 )
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v4, AutopilotPolicyNotFound, a1);
    return 2147943569LL;
  }
  else
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      McTemplateU0dz_EventWriteTransfer(v4, AutopilotGetPolicyStringByNameFailed, (unsigned int)StringPolicy, a1);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB2,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\dllmain.cpp",
      (const char *)v5);
    return v5;
  }
}

```

## disassembly

```asm
0x180012bf0  mov     [rsp+arg_0], rbx
0x180012bf5  push    rdi; int
0x180012bf6  sub     rsp, 20h
0x180012bfa  mov     rdi, rcx
0x180012bfd  call    ?GetStringPolicy@AutopilotPolicyCache@Autopilot@Windows@Microsoft@@SAJPEBGPEAPEAG@Z; Microsoft::Windows::Autopilot::AutopilotPolicyCache::GetStringPolicy(ushort const *,ushort * *)
0x180012c02  mov     ebx, eax
0x180012c04  test    eax, eax
0x180012c06  jns     short loc_180012C66
0x180012c08  cmp     eax, 80070491h
0x180012c0d  jnz     short loc_180012C2E
0x180012c0f  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 1
0x180012c16  jz      short loc_180012C27
0x180012c18  mov     r8, rdi
0x180012c1b  lea     rdx, AutopilotPolicyNotFound
0x180012c22  call    McTemplateU0z_EventWriteTransfer
0x180012c27  mov     eax, 80070491h
0x180012c2c  jmp     short loc_180012C87
0x180012c2e  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x180012c35  jz      short loc_180012C49
0x180012c37  mov     r9, rdi
0x180012c3a  lea     rdx, AutopilotGetPolicyStringByNameFailed
0x180012c41  mov     r8d, ebx
0x180012c44  call    McTemplateU0dz_EventWriteTransfer
0x180012c49  mov     rcx, [rsp+28h]; this
0x180012c4e  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012c55  mov     r9d, ebx; char *
0x180012c58  mov     edx, 0B2h; void *
0x180012c5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012c62  mov     eax, ebx
0x180012c64  jmp     short loc_180012C87
0x180012c66  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180012c6d  jz      short loc_180012C85
0x180012c6f  lea     r9, asc_1800375E0; "********"
0x180012c76  mov     r8, rdi
0x180012c79  lea     rdx, AutopilotGetPolicyStringByNameSucceeded
0x180012c80  call    McTemplateU0zz_EventWriteTransfer
0x180012c85  xor     eax, eax
0x180012c87  mov     rbx, [rsp+28h+arg_0]
0x180012c8c  add     rsp, 20h
0x180012c90  pop     rdi
0x180012c91  retn
```
