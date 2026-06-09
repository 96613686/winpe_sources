# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>,>(void)

- ea: `0x140007a54`
- end: `0x140007b05`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_PassKeySyncOTSTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_PassKeySyncOTSTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `177`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14001bb28`

## callees

- `0x140007a54`
- `0x140007f3c`
- `0x140017d60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140007a66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140007a66`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>,>(
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

  v3 = CoTaskMemAlloc(0x128u);
  if ( !v3 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
  v5[0] = 53416747;
  v8 = 0;
  v6 = "PassKeySyncOTSTipTest";
  v9 = 0;
  v11 = 0;
  *(_QWORD *)v3 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *>::`vftable';
  v5[1] = 49172;
  v7 = 1;
  v10 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v3 + 2, v3, v5);
  v3[72] = 1;
  *(_QWORD *)v3 = &tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>::`vftable';
  *((_QWORD *)v3 + 33) = v3 + 4;
  result = a1;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x140007a54  mov     [rsp+arg_0], rbx
0x140007a59  push    rdi
0x140007a5a  sub     rsp, 50h
0x140007a5e  mov     rdi, rcx
0x140007a61  mov     ecx, 128h; cb
0x140007a66  call    cs:__imp_CoTaskMemAlloc
0x140007a6c  mov     rbx, rax
0x140007a6f  test    rax, rax
0x140007a72  jz      loc_140007AFF
0x140007a78  xor     edx, edx
0x140007a7a  mov     [rsp+58h+var_38], 32F132Bh
0x140007a82  lea     rcx, aPasskeysyncots_0; "PassKeySyncOTSTipTest"
0x140007a89  mov     [rsp+58h+var_26], edx
0x140007a8d  mov     [rsp+58h+var_30], rcx
0x140007a92  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVRequestCredentialsData@Controller@Credentials@UI@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::UI::Credentials::Controller::RequestCredentialsData *>::`vftable'
0x140007a99  mov     [rsp+58h+var_22], dx
0x140007a9e  lea     rcx, [rbx+8]
0x140007aa2  mov     [rsp+58h+var_10], rdx
0x140007aa7  lea     r8, [rsp+58h+var_38]
0x140007aac  xorps   xmm0, xmm0
0x140007aaf  mov     [rbx], rax
0x140007ab2  mov     rdx, rbx
0x140007ab5  mov     [rsp+58h+var_34], 0C014h
0x140007abd  mov     [rsp+58h+var_28], 1
0x140007ac4  movdqu  [rsp+58h+var_20], xmm0
0x140007aca  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x140007acf  lea     rax, ??_7?$merged_data@U_tip_PassKeySyncOTSTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_PassKeySyncOTSTipTest,_tip_PassKeySyncOTSTipTest>::`vftable'
0x140007ad6  mov     dword ptr [rbx+120h], 1
0x140007ae0  mov     [rbx], rax
0x140007ae3  lea     rax, [rbx+10h]
0x140007ae7  mov     [rbx+108h], rax
0x140007aee  mov     rax, rdi
0x140007af1  mov     [rdi], rbx
0x140007af4  mov     rbx, [rsp+58h+arg_0]
0x140007af9  add     rsp, 50h
0x140007afd  pop     rdi
0x140007afe  retn
0x140007aff  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
