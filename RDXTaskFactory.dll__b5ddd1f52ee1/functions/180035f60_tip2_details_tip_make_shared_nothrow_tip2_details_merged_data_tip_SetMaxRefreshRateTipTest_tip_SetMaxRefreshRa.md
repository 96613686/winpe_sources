# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_SetMaxRefreshRateTipTest,_tip_SetMaxRefreshRateTipTest>,>(void)

- ea: `0x180035f60`
- end: `0x180036011`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_SetMaxRefreshRateTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_SetMaxRefreshRateTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `177`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180042d08`

## callees

- `0x18000c0cc`
- `0x180016adc`
- `0x180035f60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035f72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035f72`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_SetMaxRefreshRateTipTest,_tip_SetMaxRefreshRateTipTest>,>(
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
  v5[0] = 61266678;
  v8 = 0;
  v6 = "SetMaxRefreshRateTipTest";
  v9 = 0;
  v11 = 0;
  *(_QWORD *)v3 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>::`vftable';
  v5[1] = 16641;
  v7 = 1;
  v10 = 0;
  tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(v3 + 2, v3, v5);
  v3[70] = 1;
  *(_QWORD *)v3 = &tip2::details::merged_data<_tip_SetMaxRefreshRateTipTest,_tip_SetMaxRefreshRateTipTest>::`vftable';
  *((_QWORD *)v3 + 33) = v3 + 4;
  result = a1;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x180035f60  mov     [rsp+arg_0], rbx
0x180035f65  push    rdi
0x180035f66  sub     rsp, 50h
0x180035f6a  mov     rdi, rcx
0x180035f6d  mov     ecx, 120h; cb
0x180035f72  call    cs:__imp_CoTaskMemAlloc
0x180035f78  mov     rbx, rax
0x180035f7b  test    rax, rax
0x180035f7e  jz      loc_18003600B
0x180035f84  xor     edx, edx
0x180035f86  mov     [rsp+58h+var_38], 3A6DAF6h
0x180035f8e  lea     rcx, aSetmaxrefreshr; "SetMaxRefreshRateTipTest"
0x180035f95  mov     [rsp+58h+var_26], edx
0x180035f99  mov     [rsp+58h+var_30], rcx
0x180035f9e  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVAppServiceResponse@AppService@ApplicationModel@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::AppService::AppServiceResponse *>::`vftable'
0x180035fa5  mov     [rsp+58h+var_22], dx
0x180035faa  lea     rcx, [rbx+8]
0x180035fae  mov     [rsp+58h+var_10], rdx
0x180035fb3  lea     r8, [rsp+58h+var_38]
0x180035fb8  xorps   xmm0, xmm0
0x180035fbb  mov     [rbx], rax
0x180035fbe  mov     rdx, rbx
0x180035fc1  mov     [rsp+58h+var_34], 4101h
0x180035fc9  mov     [rsp+58h+var_28], 1
0x180035fd0  movdqu  [rsp+58h+var_20], xmm0
0x180035fd6  call    ??0?$shared_data@$00$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<1,0,0>::shared_data<1,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180035fdb  lea     rax, ??_7?$merged_data@U_tip_SetMaxRefreshRateTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_SetMaxRefreshRateTipTest,_tip_SetMaxRefreshRateTipTest>::`vftable'
0x180035fe2  mov     dword ptr [rbx+118h], 1
0x180035fec  mov     [rbx], rax
0x180035fef  lea     rax, [rbx+10h]
0x180035ff3  mov     [rbx+108h], rax
0x180035ffa  mov     rax, rdi
0x180035ffd  mov     [rdi], rbx
0x180036000  mov     rbx, [rsp+58h+arg_0]
0x180036005  add     rsp, 50h
0x180036009  pop     rdi
0x18003600a  retn
0x18003600b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
