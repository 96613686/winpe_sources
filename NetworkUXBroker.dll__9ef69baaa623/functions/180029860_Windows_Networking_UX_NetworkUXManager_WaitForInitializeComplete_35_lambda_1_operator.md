# _Windows::Networking::UX::NetworkUXManager::WaitForInitializeComplete_::_35_::_lambda_1_::operator()

- ea: `0x180029860`
- end: `0x180029907`
- name: `_Windows::Networking::UX::NetworkUXManager::WaitForInitializeComplete_::_35_::_lambda_1_::operator()`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180030750`

## callees

- `0x18000f034`
- `0x18002719c`
- `0x180028304`
- `0x180028ec4`
- `0x180029860`
- `0x1800346bc`
- `0x1800357e8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180029882`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180029882`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002989f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002989f`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::NetworkUXManager::WaitForInitializeComplete_::_35_::_lambda_1_::operator()(
        __int128 *a1)
{
  __int128 v2; // xmm0
  LPVOID v3; // rax
  wil::details::in1diag3 *v4; // rcx
  __int128 v6; // [rsp+20h] [rbp-18h] BYREF
  char *v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  WaitForMultipleObjects(
    (__int64)(*((_QWORD *)a1 + 3) - *((_QWORD *)a1 + 2)) >> 3,
    *((const HANDLE **)a1 + 2),
    1,
    0xFFFFFFFF);
  v2 = *a1;
  v7 = 0;
  v6 = v2;
  v3 = CoTaskMemAlloc(0x138u);
  if ( !v3 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v4);
  v8 = tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>(
         v3,
         &v6);
  wil::com_ptr_t<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>,wil::err_returncode_policy>::operator=(
    (void **)&v7,
    (void **)&v8);
  wil::com_ptr_t<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>,wil::err_returncode_policy>((void **)&v8);
  if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(v7 + 8) )
    tip2::tip_test<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>>::complete(&v7);
  return wil::com_ptr_t<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>,wil::err_returncode_policy>((void **)&v7);
}

```

## disassembly

```asm
0x180029860  push    rbx
0x180029862  sub     rsp, 30h
0x180029866  mov     rdx, [rcx+10h]; lpHandles
0x18002986a  mov     rbx, rcx
0x18002986d  mov     rcx, [rcx+18h]
0x180029871  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180029875  sub     rcx, rdx
0x180029878  mov     r8d, 1; bWaitAll
0x18002987e  sar     rcx, 3; nCount
0x180029882  call    cs:__imp_WaitForMultipleObjects
0x180029888  movups  xmm0, xmmword ptr [rbx]
0x18002988b  mov     ecx, 138h; cb
0x180029890  mov     [rsp+38h+arg_0], 0
0x180029899  movdqu  [rsp+38h+var_18], xmm0
0x18002989f  call    cs:__imp_CoTaskMemAlloc
0x1800298a5  test    rax, rax
0x1800298a8  jz      short loc_180029901
0x1800298aa  lea     rdx, [rsp+38h+var_18]
0x1800298af  mov     rcx, rax
0x1800298b2  call    ??0?$merged_data@U_tip_NetworkUXManagerInitializationTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>(_GUID *)
0x1800298b7  lea     rdx, [rsp+38h+arg_8]
0x1800298bc  mov     [rsp+38h+arg_8], rax
0x1800298c1  lea     rcx, [rsp+38h+arg_0]
0x1800298c6  call    ??4?$com_ptr_t@V?$merged_data@U_tip_NetworkUXManagerInitializationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>,wil::err_returncode_policy> &&)
0x1800298cb  lea     rcx, [rsp+38h+arg_8]
0x1800298d0  call    ??1?$com_ptr_t@V?$merged_data@U_tip_NetworkUXManagerInitializationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>,wil::err_returncode_policy>(void)
0x1800298d5  mov     rcx, [rsp+38h+arg_0]
0x1800298da  add     rcx, 8
0x1800298de  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x1800298e3  test    al, al
0x1800298e5  jz      short loc_1800298F1
0x1800298e7  lea     rcx, [rsp+38h+arg_0]
0x1800298ec  call    ?complete@?$tip_test@V?$merged_data@U_tip_NetworkUXManagerInitializationTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>>::complete(void)
0x1800298f1  lea     rcx, [rsp+38h+arg_0]
0x1800298f6  call    ??1?$com_ptr_t@V?$merged_data@U_tip_NetworkUXManagerInitializationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_NetworkUXManagerInitializationTest,_tip_NetworkUXManagerInitializationTest>,wil::err_returncode_policy>(void)
0x1800298fb  add     rsp, 30h
0x1800298ff  pop     rbx
0x180029900  retn
0x180029901  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
