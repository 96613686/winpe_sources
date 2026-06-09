# AutoPilotGetPolicyStringByName

- ea: `0x1800129b0`
- end: `0x180012a52`
- name: `AutoPilotGetPolicyStringByName`
- size: `162`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800105f4`
- `0x1800129b0`
- `0x1800132d8`
- `0x180013370`
- `0x1800133f0`
- `0x18001891c`

## string_xrefs

- `0x180012a0e`: `onecoreuap\admin\moderndeployment\autopilot\dll\dllmain.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AutoPilotGetPolicyStringByName(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  int StringPolicy; // eax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
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
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\dllmain.cpp",
      (const char *)v5,
      v7);
    return v5;
  }
}

```

## disassembly

```asm
0x1800129b0  mov     [rsp+arg_0], rbx
0x1800129b5  push    rdi; int
0x1800129b6  sub     rsp, 20h
0x1800129ba  mov     rdi, rcx
0x1800129bd  call    ?GetStringPolicy@AutopilotPolicyCache@Autopilot@Windows@Microsoft@@SAJPEBGPEAPEAG@Z; Microsoft::Windows::Autopilot::AutopilotPolicyCache::GetStringPolicy(ushort const *,ushort * *)
0x1800129c2  mov     ebx, eax
0x1800129c4  test    eax, eax
0x1800129c6  jns     short loc_180012A26
0x1800129c8  cmp     eax, 80070491h
0x1800129cd  jnz     short loc_1800129EE
0x1800129cf  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 1
0x1800129d6  jz      short loc_1800129E7
0x1800129d8  mov     r8, rdi
0x1800129db  lea     rdx, AutopilotPolicyNotFound
0x1800129e2  call    McTemplateU0z_EventWriteTransfer
0x1800129e7  mov     eax, 80070491h
0x1800129ec  jmp     short loc_180012A47
0x1800129ee  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x1800129f5  jz      short loc_180012A09
0x1800129f7  mov     r9, rdi
0x1800129fa  lea     rdx, AutopilotGetPolicyStringByNameFailed
0x180012a01  mov     r8d, ebx
0x180012a04  call    McTemplateU0dz_EventWriteTransfer
0x180012a09  mov     rcx, [rsp+28h]; this
0x180012a0e  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\moderndeployment\\au"...
0x180012a15  mov     r9d, ebx; char *
0x180012a18  mov     edx, 0B2h; void *
0x180012a1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a22  mov     eax, ebx
0x180012a24  jmp     short loc_180012A47
0x180012a26  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180012a2d  jz      short loc_180012A45
0x180012a2f  lea     r9, asc_1800365C0; "********"
0x180012a36  mov     r8, rdi
0x180012a39  lea     rdx, AutopilotGetPolicyStringByNameSucceeded
0x180012a40  call    McTemplateU0zz_EventWriteTransfer
0x180012a45  xor     eax, eax
0x180012a47  mov     rbx, [rsp+28h+arg_0]
0x180012a4c  add     rsp, 20h
0x180012a50  pop     rdi
0x180012a51  retn
```
