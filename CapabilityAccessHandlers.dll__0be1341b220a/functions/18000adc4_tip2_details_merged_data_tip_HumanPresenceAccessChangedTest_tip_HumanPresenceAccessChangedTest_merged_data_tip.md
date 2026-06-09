# tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>(void)

- ea: `0x18000adc4`
- end: `0x18000ae6d`
- name: `??0?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@QEAA@XZ`
- size: `169`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d550`

## callees

- `0x18000af24`

## string_xrefs

- `0x18000adf9`: `HumanPresenceAccessChangedTest`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>(
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

  v3[0] = 43472638;
  v3[1] = 49408;
  *(_QWORD *)a1 = &tip2::details::test_data_interface::`vftable';
  v5 = 257;
  v6 = 0;
  v7 = 0;
  v9 = 0;
  v4 = "HumanPresenceAccessChangedTest";
  v8 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(a1 + 8, a1, v3);
  *(_QWORD *)(a1 + 272) = 0;
  *(_QWORD *)(a1 + 280) = 0;
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)a1 = &tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>::`vftable';
  *(_QWORD *)(a1 + 264) = a1 + 16;
  result = a1;
  *(_DWORD *)(a1 + 296) = 1;
  return result;
}

```

## disassembly

```asm
0x18000adc4  push    rbx
0x18000adc6  sub     rsp, 50h
0x18000adca  mov     rbx, rcx
0x18000adcd  mov     [rsp+58h+var_38], 29756FEh
0x18000add5  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x18000addc  mov     [rsp+58h+var_34], 0C100h
0x18000ade4  mov     [rcx], rax
0x18000ade7  lea     r8, [rsp+58h+var_38]
0x18000adec  xor     ecx, ecx
0x18000adee  mov     [rsp+58h+var_28], 101h
0x18000adf5  mov     [rsp+58h+var_26], ecx
0x18000adf9  lea     rax, aHumanpresencea; "HumanPresenceAccessChangedTest"
0x18000ae00  mov     [rsp+58h+var_22], cx
0x18000ae05  xorps   xmm0, xmm0
0x18000ae08  mov     [rsp+58h+var_10], rcx
0x18000ae0d  mov     rdx, rbx
0x18000ae10  lea     rcx, [rbx+8]
0x18000ae14  mov     [rsp+58h+var_30], rax
0x18000ae19  movdqu  [rsp+58h+var_20], xmm0
0x18000ae1f  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18000ae24  mov     qword ptr [rbx+110h], 0
0x18000ae2f  lea     rax, ??_7?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>::`vftable'
0x18000ae36  mov     qword ptr [rbx+118h], 0
0x18000ae41  mov     qword ptr [rbx+120h], 0
0x18000ae4c  mov     [rbx], rax
0x18000ae4f  lea     rax, [rbx+10h]
0x18000ae53  mov     [rbx+108h], rax
0x18000ae5a  mov     rax, rbx
0x18000ae5d  mov     dword ptr [rbx+128h], 1
0x18000ae67  add     rsp, 50h
0x18000ae6b  pop     rbx
0x18000ae6c  retn
```
