# tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>(void)

- ea: `0x180011a1c`
- end: `0x180011abe`
- name: `??0?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@QEAA@XZ`
- size: `162`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e0f4`

## callees

- `0x180011bf8`

## string_xrefs

- `0x180011a47`: `CommandSearchPoliciesCheckTest`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>(
        __int64 a1)
{
  __int64 result; // rax
  _DWORD v3[2]; // [rsp+20h] [rbp-38h] BYREF
  const char *v4; // [rsp+28h] [rbp-30h]
  __int16 v5; // [rsp+30h] [rbp-28h]
  int v6; // [rsp+32h] [rbp-26h]
  __int16 v7; // [rsp+36h] [rbp-22h]
  __int128 v8; // [rsp+38h] [rbp-20h]
  __int64 v9; // [rsp+48h] [rbp-10h]

  v3[0] = 57723064;
  v6 = 0;
  v7 = 0;
  *(_QWORD *)a1 = &tip2::details::test_data_interface::`vftable';
  v9 = 0;
  v4 = "CommandSearchPoliciesCheckTest";
  v3[1] = 17152;
  v5 = 1;
  v8 = 0;
  tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(a1 + 8, a1, v3);
  *(_DWORD *)(a1 + 272) = 0x10000;
  *(_QWORD *)a1 = &tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>::`vftable';
  *(_QWORD *)(a1 + 264) = a1 + 16;
  result = a1;
  *(_WORD *)(a1 + 276) = 0;
  *(_BYTE *)(a1 + 278) = 0;
  *(_DWORD *)(a1 + 280) = 1;
  return result;
}

```

## disassembly

```asm
0x180011a1c  push    rbx
0x180011a1e  sub     rsp, 50h
0x180011a22  xor     edx, edx
0x180011a24  mov     [rsp+58h+var_38], 370C8B8h
0x180011a2c  mov     rbx, rcx
0x180011a2f  mov     [rsp+58h+var_26], edx
0x180011a33  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180011a3a  mov     [rsp+58h+var_22], dx
0x180011a3f  mov     [rcx], rax
0x180011a42  lea     r8, [rsp+58h+var_38]
0x180011a47  lea     rcx, aCommandsearchp; "CommandSearchPoliciesCheckTest"
0x180011a4e  mov     [rsp+58h+var_10], rdx
0x180011a53  mov     [rsp+58h+var_30], rcx
0x180011a58  xorps   xmm0, xmm0
0x180011a5b  lea     rcx, [rbx+8]
0x180011a5f  mov     [rsp+58h+var_34], 4300h
0x180011a67  mov     rdx, rbx
0x180011a6a  mov     [rsp+58h+var_28], 1
0x180011a71  movdqu  [rsp+58h+var_20], xmm0
0x180011a77  call    ??0?$shared_data@$00$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180011a7c  lea     rax, ??_7?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@6B@; const tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>::`vftable'
0x180011a83  mov     dword ptr [rbx+110h], 10000h
0x180011a8d  mov     [rbx], rax
0x180011a90  lea     rax, [rbx+10h]
0x180011a94  mov     [rbx+108h], rax
0x180011a9b  mov     rax, rbx
0x180011a9e  mov     word ptr [rbx+114h], 0
0x180011aa7  mov     byte ptr [rbx+116h], 0
0x180011aae  mov     dword ptr [rbx+118h], 1
0x180011ab8  add     rsp, 50h
0x180011abc  pop     rbx
0x180011abd  retn
```
