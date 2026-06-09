# tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>(_GUID *)

- ea: `0x180011954`
- end: `0x180011a16`
- name: `??0?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@QEAA@PEAU_GUID@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018be0`
- `0x180018d58`

## callees

- `0x180011bf8`
- `0x18001f700`

## string_xrefs

- `0x18001198a`: `CommandSearchPoliciesCheckTest`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>(
        __int64 a1,
        __int64 a2)
{
  _DWORD v5[2]; // [rsp+20h] [rbp-38h] BYREF
  const char *v6; // [rsp+28h] [rbp-30h]
  __int16 v7; // [rsp+30h] [rbp-28h]
  int v8; // [rsp+32h] [rbp-26h]
  __int16 v9; // [rsp+36h] [rbp-22h]
  __int128 v10; // [rsp+38h] [rbp-20h]
  __int64 v11; // [rsp+48h] [rbp-10h]

  v5[0] = 57723064;
  v5[1] = 17152;
  *(_QWORD *)a1 = &tip2::details::test_data_interface::`vftable';
  v6 = "CommandSearchPoliciesCheckTest";
  v8 = 0;
  v9 = 0;
  v7 = 1;
  v10 = 0;
  v11 = 0;
  tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(a1 + 8, a1, v5);
  *(_DWORD *)(a1 + 272) = 0x10000;
  *(_QWORD *)a1 = &tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>::`vftable';
  *(_WORD *)(a1 + 276) = 0;
  *(_QWORD *)(a1 + 264) = a1 + 16;
  *(_BYTE *)(a1 + 278) = 0;
  *(_DWORD *)(a1 + 280) = 1;
  tip2::details::shared_data<1,0,0>::open_without_lock(a1 + 8, a2);
  return a1;
}

```

## disassembly

```asm
0x180011954  mov     r11, rsp
0x180011957  mov     [r11+8], rbx
0x18001195b  mov     [r11+10h], rsi
0x18001195f  push    rdi
0x180011960  sub     rsp, 50h
0x180011964  mov     rsi, rcx
0x180011967  mov     [rsp+58h+var_38], 370C8B8h
0x18001196f  mov     rdi, rdx
0x180011972  mov     [rsp+58h+var_34], 4300h
0x18001197a  xor     edx, edx
0x18001197c  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180011983  mov     [rcx], rax
0x180011986  lea     r8, [r11-38h]
0x18001198a  lea     rcx, aCommandsearchp; "CommandSearchPoliciesCheckTest"
0x180011991  xorps   xmm0, xmm0
0x180011994  mov     [r11-30h], rcx
0x180011998  lea     rcx, [rsi+8]
0x18001199c  mov     [rsp+58h+var_26], edx
0x1800119a0  mov     [rsp+58h+var_22], dx
0x1800119a5  mov     [rsp+58h+var_28], 1
0x1800119ac  movdqu  [rsp+58h+var_20], xmm0
0x1800119b2  mov     [r11-10h], rdx
0x1800119b6  mov     rdx, rsi
0x1800119b9  call    ??0?$shared_data@$00$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x1800119be  lea     rax, ??_7?$merged_data@U_tip_CommandSearchPoliciesCheckTest@FeatureEnablement@SystemSettings@@U123@@details@tip2@@6B@; const tip2::details::merged_data<SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest,SystemSettings::FeatureEnablement::_tip_CommandSearchPoliciesCheckTest>::`vftable'
0x1800119c5  mov     dword ptr [rsi+110h], 10000h
0x1800119cf  mov     [rsi], rax
0x1800119d2  lea     rcx, [rsi+8]
0x1800119d6  lea     rax, [rsi+10h]
0x1800119da  mov     word ptr [rsi+114h], 0
0x1800119e3  mov     rdx, rdi
0x1800119e6  mov     [rsi+108h], rax
0x1800119ed  mov     byte ptr [rsi+116h], 0
0x1800119f4  mov     dword ptr [rsi+118h], 1
0x1800119fe  call    ?open_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@IEAAXPEAU_GUID@@@Z; tip2::details::shared_data<1,0,0>::open_without_lock(_GUID *)
0x180011a03  mov     rbx, [rsp+58h+arg_0]
0x180011a08  mov     rax, rsi
0x180011a0b  mov     rsi, [rsp+58h+arg_8]
0x180011a10  add     rsp, 50h
0x180011a14  pop     rdi
0x180011a15  retn
```
