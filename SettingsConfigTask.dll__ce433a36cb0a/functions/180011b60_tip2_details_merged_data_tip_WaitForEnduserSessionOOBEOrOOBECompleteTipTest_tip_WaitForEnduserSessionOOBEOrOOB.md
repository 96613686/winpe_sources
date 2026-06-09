# tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>(void)

- ea: `0x180011b60`
- end: `0x180011bf2`
- name: `??0?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@QEAA@XZ`
- size: `146`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001e1ac`

## callees

- `0x180011c58`

## string_xrefs

- `0x180011b8b`: `WaitForEnduserSessionOOBEOrOOBECompleteTipTest`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>(
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

  v3[0] = 57086978;
  v6 = 0;
  v7 = 0;
  *(_QWORD *)a1 = &tip2::details::test_data_interface::`vftable';
  v9 = 0;
  v4 = "WaitForEnduserSessionOOBEOrOOBECompleteTipTest";
  v3[1] = 49472;
  v5 = 1;
  v8 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(a1 + 8, a1, v3);
  *(_DWORD *)(a1 + 272) = 1;
  *(_QWORD *)a1 = &tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>::`vftable';
  *(_QWORD *)(a1 + 264) = a1 + 16;
  result = a1;
  *(_DWORD *)(a1 + 280) = 1;
  return result;
}

```

## disassembly

```asm
0x180011b60  push    rbx
0x180011b62  sub     rsp, 50h
0x180011b66  xor     edx, edx
0x180011b68  mov     [rsp+58h+var_38], 3671402h
0x180011b70  mov     rbx, rcx
0x180011b73  mov     [rsp+58h+var_26], edx
0x180011b77  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x180011b7e  mov     [rsp+58h+var_22], dx
0x180011b83  mov     [rcx], rax
0x180011b86  lea     r8, [rsp+58h+var_38]
0x180011b8b  lea     rcx, aWaitforenduser; "WaitForEnduserSessionOOBEOrOOBEComplete"...
0x180011b92  mov     [rsp+58h+var_10], rdx
0x180011b97  mov     [rsp+58h+var_30], rcx
0x180011b9c  xorps   xmm0, xmm0
0x180011b9f  lea     rcx, [rbx+8]
0x180011ba3  mov     [rsp+58h+var_34], 0C140h
0x180011bab  mov     rdx, rbx
0x180011bae  mov     [rsp+58h+var_28], 1
0x180011bb5  movdqu  [rsp+58h+var_20], xmm0
0x180011bbb  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180011bc0  mov     dword ptr [rbx+110h], 1
0x180011bca  lea     rax, ??_7?$merged_data@U_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest,_tip_WaitForEnduserSessionOOBEOrOOBECompleteTipTest>::`vftable'
0x180011bd1  mov     [rbx], rax
0x180011bd4  lea     rax, [rbx+10h]
0x180011bd8  mov     [rbx+108h], rax
0x180011bdf  mov     rax, rbx
0x180011be2  mov     dword ptr [rbx+118h], 1
0x180011bec  add     rsp, 50h
0x180011bf0  pop     rbx
0x180011bf1  retn
```
