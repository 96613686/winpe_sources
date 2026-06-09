# tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>(void)

- ea: `0x18000ae74`
- end: `0x18000af1c`
- name: `??0?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@QEAA@XZ`
- size: `168`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000d5b0`

## callees

- `0x18000af24`

## string_xrefs

- `0x18000aea9`: `HumanPresenceAccessCheckTest`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>(
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

  v3[0] = 43416011;
  v3[1] = 49408;
  *(_QWORD *)a1 = &tip2::details::test_data_interface::`vftable';
  v5 = 257;
  v6 = 0;
  v7 = 0;
  v9 = 0;
  v4 = "HumanPresenceAccessCheckTest";
  v8 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(a1 + 8, a1, v3);
  *(_DWORD *)(a1 + 272) = 0;
  *(_QWORD *)(a1 + 280) = 0;
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)a1 = &tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::`vftable';
  *(_QWORD *)(a1 + 264) = a1 + 16;
  result = a1;
  *(_DWORD *)(a1 + 296) = 1;
  return result;
}

```

## disassembly

```asm
0x18000ae74  push    rbx
0x18000ae76  sub     rsp, 50h
0x18000ae7a  mov     rbx, rcx
0x18000ae7d  mov     [rsp+58h+var_38], 29679CBh
0x18000ae85  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x18000ae8c  mov     [rsp+58h+var_34], 0C100h
0x18000ae94  mov     [rcx], rax
0x18000ae97  lea     r8, [rsp+58h+var_38]
0x18000ae9c  xor     ecx, ecx
0x18000ae9e  mov     [rsp+58h+var_28], 101h
0x18000aea5  mov     [rsp+58h+var_26], ecx
0x18000aea9  lea     rax, aHumanpresencea_0; "HumanPresenceAccessCheckTest"
0x18000aeb0  mov     [rsp+58h+var_22], cx
0x18000aeb5  xorps   xmm0, xmm0
0x18000aeb8  mov     [rsp+58h+var_10], rcx
0x18000aebd  mov     rdx, rbx
0x18000aec0  lea     rcx, [rbx+8]
0x18000aec4  mov     [rsp+58h+var_30], rax
0x18000aec9  movdqu  [rsp+58h+var_20], xmm0
0x18000aecf  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18000aed4  mov     dword ptr [rbx+110h], 0
0x18000aede  lea     rax, ??_7?$merged_data@U_tip_HumanPresenceAccessCheckTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_HumanPresenceAccessCheckTest,_tip_HumanPresenceAccessCheckTest>::`vftable'
0x18000aee5  mov     qword ptr [rbx+118h], 0
0x18000aef0  mov     qword ptr [rbx+120h], 0
0x18000aefb  mov     [rbx], rax
0x18000aefe  lea     rax, [rbx+10h]
0x18000af02  mov     [rbx+108h], rax
0x18000af09  mov     rax, rbx
0x18000af0c  mov     dword ptr [rbx+128h], 1
0x18000af16  add     rsp, 50h
0x18000af1a  pop     rbx
0x18000af1b  retn
```
