# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_EnableHDRSupportTipTest,_tip_EnableHDRSupportTipTest>,>(void)

- ea: `0x180035ea8`
- end: `0x180035f59`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_EnableHDRSupportTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_EnableHDRSupportTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `177`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180042c50`

## callees

- `0x18000c0cc`
- `0x180016adc`
- `0x180035ea8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035eba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035eba`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_EnableHDRSupportTipTest,_tip_EnableHDRSupportTipTest>,>(
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

  v3 = CoTaskMemAlloc(0x120u);
  if ( !v3 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
  v5[0] = 61266683;
  v8 = 0;
  v6 = "EnableHDRSupportTipTest";
  v9 = 0;
  v11 = 0;
  *(_QWORD *)v3 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>::`vftable';
  v5[1] = 16641;
  v7 = 1;
  v10 = 0;
  tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(v3 + 2, v3, v5);
  v3[70] = 1;
  *(_QWORD *)v3 = &tip2::details::merged_data<_tip_EnableHDRSupportTipTest,_tip_EnableHDRSupportTipTest>::`vftable';
  *((_QWORD *)v3 + 33) = v3 + 4;
  result = a1;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x180035ea8  mov     [rsp+arg_0], rbx
0x180035ead  push    rdi
0x180035eae  sub     rsp, 50h
0x180035eb2  mov     rdi, rcx
0x180035eb5  mov     ecx, 120h; cb
0x180035eba  call    cs:__imp_CoTaskMemAlloc
0x180035ec0  mov     rbx, rax
0x180035ec3  test    rax, rax
0x180035ec6  jz      loc_180035F53
0x180035ecc  xor     edx, edx
0x180035ece  mov     [rsp+58h+var_38], 3A6DAFBh
0x180035ed6  lea     rcx, aEnablehdrsuppo; "EnableHDRSupportTipTest"
0x180035edd  mov     [rsp+58h+var_26], edx
0x180035ee1  mov     [rsp+58h+var_30], rcx
0x180035ee6  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>::`vftable'
0x180035eed  mov     [rsp+58h+var_22], dx
0x180035ef2  lea     rcx, [rbx+8]
0x180035ef6  mov     [rsp+58h+var_10], rdx
0x180035efb  lea     r8, [rsp+58h+var_38]
0x180035f00  xorps   xmm0, xmm0
0x180035f03  mov     [rbx], rax
0x180035f06  mov     rdx, rbx
0x180035f09  mov     [rsp+58h+var_34], 4101h
0x180035f11  mov     [rsp+58h+var_28], 1
0x180035f18  movdqu  [rsp+58h+var_20], xmm0
0x180035f1e  call    ??0?$shared_data@$00$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180035f23  lea     rax, ??_7?$merged_data@U_tip_EnableHDRSupportTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_EnableHDRSupportTipTest,_tip_EnableHDRSupportTipTest>::`vftable'
0x180035f2a  mov     dword ptr [rbx+118h], 1
0x180035f34  mov     [rbx], rax
0x180035f37  lea     rax, [rbx+10h]
0x180035f3b  mov     [rbx+108h], rax
0x180035f42  mov     rax, rdi
0x180035f45  mov     [rdi], rbx
0x180035f48  mov     rbx, [rsp+58h+arg_0]
0x180035f4d  add     rsp, 50h
0x180035f51  pop     rdi
0x180035f52  retn
0x180035f53  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
