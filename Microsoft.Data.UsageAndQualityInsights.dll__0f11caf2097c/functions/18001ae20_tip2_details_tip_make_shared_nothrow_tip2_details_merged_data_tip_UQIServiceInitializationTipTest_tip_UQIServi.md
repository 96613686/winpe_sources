# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIServiceInitializationTipTest,_tip_UQIServiceInitializationTipTest>,>(void)

- ea: `0x18001ae20`
- end: `0x18001aed1`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_UQIServiceInitializationTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_UQIServiceInitializationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ac5c`

## callees

- `0x18000c258`
- `0x180013064`
- `0x18001ae20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ae32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ae32`

## string_xrefs

- `0x18001ae4e`: `UQIServiceInitializationTipTest`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_UQIServiceInitializationTipTest,_tip_UQIServiceInitializationTipTest>,>(
        _QWORD *a1)
{
  wil::details::in1diag3 *v2; // rcx
  _DWORD *v3; // rbx
  _QWORD *result; // rax
  _DWORD v5[2]; // [rsp+20h] [rbp-38h] BYREF
  const char *v6; // [rsp+28h] [rbp-30h]
  __int16 v7; // [rsp+30h] [rbp-28h]
  int v8; // [rsp+32h] [rbp-26h]
  __int16 v9; // [rsp+36h] [rbp-22h]
  __int128 v10; // [rsp+38h] [rbp-20h]
  __int64 v11; // [rsp+48h] [rbp-10h]

  v3 = CoTaskMemAlloc(0x118u);
  if ( !v3 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
  v5[0] = 58920970;
  v8 = 0;
  v6 = "UQIServiceInitializationTipTest";
  v9 = 0;
  v11 = 0;
  *(_QWORD *)v3 = &tip2::details::test_data_interface::`vftable';
  v5[1] = 49408;
  v7 = 1;
  v10 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v3 + 2, v3, v5);
  v3[68] = 1;
  *(_QWORD *)v3 = &tip2::details::merged_data<_tip_UQIEnableMetricGroupTipTest,_tip_UQIEnableMetricGroupTipTest>::`vftable';
  *((_QWORD *)v3 + 33) = v3 + 4;
  result = a1;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x18001ae20  mov     [rsp+arg_0], rbx
0x18001ae25  push    rdi
0x18001ae26  sub     rsp, 50h
0x18001ae2a  mov     rdi, rcx
0x18001ae2d  mov     ecx, 118h; cb
0x18001ae32  call    cs:__imp_CoTaskMemAlloc
0x18001ae38  mov     rbx, rax
0x18001ae3b  test    rax, rax
0x18001ae3e  jz      loc_18001AECB
0x18001ae44  xor     edx, edx
0x18001ae46  mov     [rsp+58h+var_38], 383100Ah
0x18001ae4e  lea     rcx, aUqiserviceinit; "UQIServiceInitializationTipTest"
0x18001ae55  mov     [rsp+58h+var_26], edx
0x18001ae59  mov     [rsp+58h+var_30], rcx
0x18001ae5e  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x18001ae65  mov     [rsp+58h+var_22], dx
0x18001ae6a  lea     rcx, [rbx+8]
0x18001ae6e  mov     [rsp+58h+var_10], rdx
0x18001ae73  lea     r8, [rsp+58h+var_38]
0x18001ae78  xorps   xmm0, xmm0
0x18001ae7b  mov     [rbx], rax
0x18001ae7e  mov     rdx, rbx
0x18001ae81  mov     [rsp+58h+var_34], 0C100h
0x18001ae89  mov     [rsp+58h+var_28], 1
0x18001ae90  movdqu  [rsp+58h+var_20], xmm0
0x18001ae96  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18001ae9b  lea     rax, ??_7?$merged_data@U_tip_UQIEnableMetricGroupTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_UQIEnableMetricGroupTipTest,_tip_UQIEnableMetricGroupTipTest>::`vftable'
0x18001aea2  mov     dword ptr [rbx+110h], 1
0x18001aeac  mov     [rbx], rax
0x18001aeaf  lea     rax, [rbx+10h]
0x18001aeb3  mov     [rbx+108h], rax
0x18001aeba  mov     rax, rdi
0x18001aebd  mov     [rdi], rbx
0x18001aec0  mov     rbx, [rsp+58h+arg_0]
0x18001aec5  add     rsp, 50h
0x18001aec9  pop     rdi
0x18001aeca  retn
0x18001aecb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
