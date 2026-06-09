# I_EncodeAndSendRpcRequest(ulong,_GUID,_CTAPCBOR_RPC_REQUEST &,ulong *,uchar * *)

- ea: `0x1800b4170`
- end: `0x1800b4802`
- name: `?I_EncodeAndSendRpcRequest@@YAJKU_GUID@@AEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z`
- size: `1682`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, struct _GUID *@<rdx>, struct _CTAPCBOR_RPC_REQUEST *@<r8>, unsigned int *@<r9>, unsigned __int8 **)`
- caller_count: `25`
- callee_count: `40`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180049800`
- `0x18004d970`
- `0x18004e2e0`
- `0x18004e8a0`
- `0x1800b7f40`
- `0x1800b8500`
- `0x1800b8ad0`
- `0x1800b9030`
- `0x1800b92d0`
- `0x1800b9890`
- `0x1800b9d00`
- `0x1800ba3b0`
- `0x1800ba6c0`
- `0x1800bb110`
- `0x1800bb670`
- `0x1800bbe80`
- `0x1800bc390`
- `0x1800bd060`
- `0x1800bd630`
- `0x1800bdbb0`
- `0x1800be150`
- `0x1800be8a0`
- `0x1800bf5c0`
- `0x1800bf960`
- `0x1800bff80`

## callees

- `0x18000c5ec`
- `0x18001687c`
- `0x180049e00`
- `0x18004baa4`
- `0x18004f070`
- `0x18004f548`
- `0x18004f5b4`
- `0x180053780`
- `0x180060490`
- `0x1800b1610`
- `0x1800b1778`
- `0x1800b18e0`
- `0x1800b1a48`
- `0x1800b1bb0`
- `0x1800b1db4`
- `0x1800b1f1c`
- `0x1800b21ec`
- `0x1800b24bc`
- `0x1800b28fc`
- `0x1800b2918`
- `0x1800b2934`
- `0x1800b2950`
- `0x1800b2988`
- `0x1800b29a4`
- `0x1800b29c0`
- `0x1800b29dc`
- `0x1800b29f8`
- `0x1800b2a14`
- `0x1800b3374`
- `0x1800b33a8`
- `0x1800b33dc`
- `0x1800b3410`
- `0x1800b3444`
- `0x1800b3478`
- `0x1800b34ac`
- `0x1800b3514`
- `0x1800b357c`
- `0x1800b4170`
- `0x1800b70d4`
- `0x1800b715c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b47df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b47df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b42ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4335`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b43be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4443`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4512`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b459b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4620`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b46a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b471c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b42ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4335`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b43be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4443`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4512`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b459b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4620`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b46a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b471c`
- `RPCRT4!UuidCreate` at `0x1800b41c0`
- `RPCRT4!UuidCreate` at `0x1800b41c0`

## string_xrefs

- `0x1800b42e3`: `WebAuthNPluginAddAuthenticatorTest::reason::encoding_failed`
- `0x1800b425d`: `WebAuthNPluginPerformUVTest::reason::encoding_failed`
- `0x1800b43f5`: `WebAuthNPluginRemoveAuthenticatorTest::reason::encoding_failed`
- `0x1800b436c`: `WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::encoding_failed`
- `0x1800b44cf`: `WebAuthNPluginSetAuthenticatorStateTest::reason::encoding_failed`
- `0x1800b447a`: `WebAuthNPluginGetAuthenticatorListTest::reason::encoding_failed`
- `0x1800b45d2`: `WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::encoding_failed`
- `0x1800b4549`: `WebAuthNPluginAuthenticatorAddCredentialsTest::reason::encoding_failed`
- `0x1800b46db`: `WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::encoding_failed`
- `0x1800b4657`: `WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::encoding_failed`
- `0x1800b4753`: `WebAuthNPluginGetOperationSigningPublicKeyTest::reason::encoding_failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall I_EncodeAndSendRpcRequest(
        unsigned int a1,
        struct _GUID *a2,
        struct _CTAPCBOR_RPC_REQUEST *a3,
        unsigned int *a4,
        unsigned __int8 **a5)
{
  int v9; // ebx
  const char *v10; // rdx
  const char *v11; // rax
  __int64 v12; // rdx
  LPVOID v13; // rax
  wil::details::in1diag3 *v14; // rcx
  const char *v15; // rdx
  const char *v16; // rax
  __int64 v17; // rdx
  LPVOID v18; // rax
  wil::details::in1diag3 *v19; // rcx
  const char *v20; // rdx
  const char *v21; // rax
  __int64 v22; // rdx
  LPVOID v23; // rax
  wil::details::in1diag3 *v24; // rcx
  const char *v25; // rdx
  const char *v26; // rax
  __int64 v27; // rdx
  LPVOID v28; // rax
  wil::details::in1diag3 *v29; // rcx
  const char *v30; // rdx
  const char *v31; // rax
  __int64 v32; // rdx
  const char *v33; // rdx
  const char *v34; // rax
  LPVOID v35; // rax
  wil::details::in1diag3 *v36; // rcx
  const char *v37; // rdx
  const char *v38; // rax
  __int64 v39; // rdx
  LPVOID v40; // rax
  wil::details::in1diag3 *v41; // rcx
  const char *v42; // rdx
  const char *v43; // rax
  __int64 v44; // rdx
  LPVOID v45; // rax
  wil::details::in1diag3 *v46; // rcx
  const char *v47; // rdx
  const char *v48; // rax
  __int64 v49; // rdx
  LPVOID v50; // rax
  wil::details::in1diag3 *v51; // rcx
  const char *v52; // rdx
  const char *v53; // rax
  LPVOID v54; // rax
  wil::details::in1diag3 *v55; // rcx
  const char *v56; // rdx
  const char *v57; // rax
  __int64 v58; // rdx
  unsigned int v59; // ebx
  HLOCAL v60; // rcx
  _QWORD v62[2]; // [rsp+80h] [rbp-41h] BYREF
  struct _GUID v63; // [rsp+90h] [rbp-31h] BYREF
  unsigned __int8 *v64[2]; // [rsp+A0h] [rbp-21h] BYREF
  char v65; // [rsp+B0h] [rbp-11h]
  unsigned int v66; // [rsp+C0h] [rbp-1h] BYREF
  unsigned int v67; // [rsp+C4h] [rbp+3h] BYREF
  HLOCAL hMem; // [rsp+C8h] [rbp+7h] BYREF
  unsigned __int8 *v69; // [rsp+D0h] [rbp+Fh] BYREF

  v66 = 0;
  hMem = 0;
  if ( !memcmp_0(a2, &GUID_NULL, 0x10u) )
    UuidCreate(a2);
  v67 = 0;
  v69 = 0;
  v64[0] = (unsigned __int8 *)&hMem;
  v64[1] = 0;
  v65 = 1;
  v9 = I_EncodeRpcRequest(a1, 0, 0, 0, a2, 0, 0, 0, 0, 0, 0, 0, a3, &v66, &v64[1]);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(v64);
  if ( v9 < 0 )
  {
    switch ( a1 )
    {
      case 'm':
        v62[0] = 0;
        v63 = *a2;
        tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::open_helper(
          v62,
          &v63);
        v11 = tip2::details::reason_string((tip2::details *)"WebAuthNPluginPerformUVTest::reason::encoding_failed", v10);
        if ( v62[0] )
        {
          LOBYTE(v12) = 3;
          tip2::details::shared_data<1,0,0>::complete_without_lock(v62[0] + 8LL, v12, 10, v11);
        }
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(v62);
        break;
      case 'd':
        v62[0] = 0;
        *(struct _GUID *)v64 = *a2;
        v13 = CoTaskMemAlloc(0x198u);
        if ( !v13 )
          wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
        *(_QWORD *)&v63.Data1 = tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>(
                                  v13,
                                  v64);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::operator=(
          v62,
          &v63);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(&v63);
        v16 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginAddAuthenticatorTest::reason::encoding_failed",
                v15);
        if ( v62[0] )
        {
          LOBYTE(v17) = 3;
          tip2::details::shared_data<1,0,0>::complete_without_lock(v62[0] + 8LL, v17, 3, v16);
        }
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(v62);
        break;
      case 'f':
        v62[0] = 0;
        *(struct _GUID *)v64 = *a2;
        v18 = CoTaskMemAlloc(0x198u);
        if ( !v18 )
          wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
        *(_QWORD *)&v63.Data1 = tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>(
                                  v18,
                                  v64);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::operator=(
          v62,
          &v63);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(&v63);
        v21 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginUpdateAuthenticatorDetailsTest::reason::encoding_failed",
                v20);
        if ( v62[0] )
        {
          LOBYTE(v22) = 3;
          tip2::details::shared_data<1,0,0>::complete_without_lock(v62[0] + 8LL, v22, 3, v21);
        }
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(v62);
        break;
      case 'e':
        v62[0] = 0;
        *(struct _GUID *)v64 = *a2;
        v23 = CoTaskMemAlloc(0x198u);
        if ( !v23 )
          wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
        *(_QWORD *)&v63.Data1 = tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>(
                                  v23,
                                  v64);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>::operator=(
          v62,
          &v63);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>(&v63);
        v26 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginRemoveAuthenticatorTest::reason::encoding_failed",
                v25);
        if ( v62[0] )
        {
          LOBYTE(v27) = 3;
          tip2::details::shared_data<1,0,0>::complete_without_lock(v62[0] + 8LL, v27, 3, v26);
        }
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>(v62);
        break;
      case 'g':
        v62[0] = 0;
        *(struct _GUID *)v64 = *a2;
        v28 = CoTaskMemAlloc(0x150u);
        if ( !v28 )
          wil::details::in1diag3::_FailFastImmediate_Unexpected(v29);
        *(_QWORD *)&v63.Data1 = tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>(
                                  v28,
                                  v64);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy>::operator=(
          v62,
          &v63);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy>(&v63);
        v31 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginGetAuthenticatorListTest::reason::encoding_failed",
                v30);
        if ( v62[0] )
        {
          LOBYTE(v32) = 3;
          tip2::details::shared_data<1,0,0>::complete_without_lock(v62[0] + 8LL, v32, 7, v31);
        }
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy>(v62);
        break;
      case 'h':
        v62[0] = 0;
        *(struct _GUID *)v64 = *a2;
        tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::open_helper(
          v62,
          v64);
        v34 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginSetAuthenticatorStateTest::reason::encoding_failed",
                v33);
        tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::complete_and_fail(
          v62,
          3,
          v34);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(v62);
        break;
      case 'i':
        v62[0] = 0;
        *(struct _GUID *)v64 = *a2;
        v35 = CoTaskMemAlloc(0x1A0u);
        if ( !v35 )
          wil::details::in1diag3::_FailFastImmediate_Unexpected(v36);
        *(_QWORD *)&v63.Data1 = tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>(
                                  v35,
                                  v64);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::operator=(
          v62,
          &v63);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(&v63);
        v38 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginAuthenticatorAddCredentialsTest::reason::encoding_failed",
                v37);
        if ( v62[0] )
        {
          LOBYTE(v39) = 3;
          tip2::details::shared_data<1,0,0>::complete_without_lock(v62[0] + 8LL, v39, 3, v38);
        }
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(v62);
        break;
      case 'j':
        v62[0] = 0;
        *(struct _GUID *)v64 = *a2;
        v40 = CoTaskMemAlloc(0x1A0u);
        if ( !v40 )
          wil::details::in1diag3::_FailFastImmediate_Unexpected(v41);
        *(_QWORD *)&v63.Data1 = tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>(
                                  v40,
                                  v64);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::operator=(
          v62,
          &v63);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(&v63);
        v43 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginAuthenticatorRemoveCredentialsTest::reason::encoding_failed",
                v42);
        if ( v62[0] )
        {
          LOBYTE(v44) = 3;
          tip2::details::shared_data<1,0,0>::complete_without_lock(v62[0] + 8LL, v44, 3, v43);
        }
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(v62);
        break;
      case 'k':
        v62[0] = 0;
        *(struct _GUID *)v64 = *a2;
        v45 = CoTaskMemAlloc(0x1A0u);
        if ( !v45 )
          wil::details::in1diag3::_FailFastImmediate_Unexpected(v46);
        *(_QWORD *)&v63.Data1 = tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>(
                                  v45,
                                  v64);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>::operator=(
          v62,
          &v63);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>(&v63);
        v48 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginAuthenticatorRemoveAllCredentialsTest::reason::encoding_failed",
                v47);
        if ( v62[0] )
        {
          LOBYTE(v49) = 3;
          tip2::details::shared_data<1,0,0>::complete_without_lock(v62[0] + 8LL, v49, 11, v48);
        }
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>,wil::err_returncode_policy>(v62);
        break;
      case 'n':
        v62[0] = 0;
        *(struct _GUID *)v64 = *a2;
        v50 = CoTaskMemAlloc(0x1A0u);
        if ( !v50 )
          wil::details::in1diag3::_FailFastImmediate_Unexpected(v51);
        *(_QWORD *)&v63.Data1 = tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>(
                                  v50,
                                  v64);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::operator=(
          v62,
          &v63);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(&v63);
        v53 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginAuthenticatorGetAllCredentialsTest::reason::encoding_failed",
                v52);
        tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::complete_and_fail(
          v62,
          8,
          v53);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>,wil::err_returncode_policy>(v62);
        break;
      case 'p':
        v62[0] = 0;
        *(struct _GUID *)v64 = *a2;
        v54 = CoTaskMemAlloc(0x138u);
        if ( !v54 )
          wil::details::in1diag3::_FailFastImmediate_Unexpected(v55);
        *(_QWORD *)&v63.Data1 = tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>(
                                  v54,
                                  v64);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>::operator=(
          v62,
          &v63);
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>(&v63);
        v57 = tip2::details::reason_string(
                (tip2::details *)"WebAuthNPluginGetOperationSigningPublicKeyTest::reason::encoding_failed",
                v56);
        if ( v62[0] )
        {
          LOBYTE(v58) = 3;
          tip2::details::shared_data<1,0,0>::complete_without_lock(v62[0] + 8LL, v58, 3, v57);
        }
        wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetOperationSigningPublicKeyTest,_tip_WebAuthNPluginGetOperationSigningPublicKeyTest>,wil::err_returncode_policy>(v62);
        break;
    }
  }
  v59 = I_SendRpcRequest(0, 0, a3, v66, (unsigned __int8 *)hMem, 1u, &v67, &v69);
  if ( a4 && a5 )
  {
    *a4 = v67;
    *a5 = v69;
  }
  v60 = hMem;
  hMem = 0;
  if ( v60 )
    LocalFree(v60);
  return v59;
}

```

## disassembly

```asm
0x1800b4170  mov     [rsp-8+arg_0], rbx
0x1800b4175  push    rbp
0x1800b4176  push    rsi
0x1800b4177  push    rdi
0x1800b4178  push    r12
0x1800b417a  push    r13
0x1800b417c  push    r14
0x1800b417e  push    r15
0x1800b4180  lea     rbp, [rsp-1Fh]
0x1800b4185  sub     rsp, 0E0h
0x1800b418c  mov     r15, r9
0x1800b418f  mov     r12, r8
0x1800b4192  mov     rsi, rdx
0x1800b4195  mov     edi, ecx
0x1800b4197  mov     r14, [rbp+4Fh+arg_20]
0x1800b419b  xor     r13d, r13d
0x1800b419e  mov     [rbp+4Fh+var_50], r13d
0x1800b41a2  mov     [rbp+4Fh+hMem], r13
0x1800b41a6  lea     r8d, [r13+10h]; Size
0x1800b41aa  lea     rdx, GUID_NULL; Buf2
0x1800b41b1  mov     rcx, rsi; Buf1
0x1800b41b4  call    memcmp_0
0x1800b41b9  test    eax, eax
0x1800b41bb  jnz     short loc_1800B41C6
0x1800b41bd  mov     rcx, rsi; Uuid
0x1800b41c0  call    cs:__imp_UuidCreate
0x1800b41c6  mov     [rbp+4Fh+var_4C], r13d
0x1800b41ca  mov     [rbp+4Fh+var_40], r13
0x1800b41ce  lea     rax, [rbp+4Fh+hMem]
0x1800b41d2  mov     [rbp+4Fh+var_70], rax
0x1800b41d6  mov     [rbp+4Fh+var_70+8], r13
0x1800b41da  mov     [rbp+4Fh+var_60], 1
0x1800b41de  lea     rax, [rbp+4Fh+var_70+8]
0x1800b41e2  mov     [rsp+110h+var_A0], rax; unsigned __int8 **
0x1800b41e7  lea     rax, [rbp+4Fh+var_50]
0x1800b41eb  mov     [rsp+110h+var_A8], rax; unsigned int *
0x1800b41f0  mov     [rsp+110h+var_B0], r12; struct _CTAPCBOR_RPC_REQUEST *
0x1800b41f5  mov     [rsp+110h+var_B8], r13; unsigned __int16 *
0x1800b41fa  mov     [rsp+110h+var_C0], r13; unsigned __int8 *
0x1800b41ff  mov     [rsp+110h+var_C8], r13d; unsigned int
0x1800b4204  mov     [rsp+110h+var_D0], r13; struct _WEBAUTHN_CTAP_RPC_PROTECTED *
0x1800b4209  mov     [rsp+110h+var_D8], r13; unsigned __int8 *
0x1800b420e  mov     dword ptr [rsp+110h+var_E0], r13d; unsigned int
0x1800b4213  mov     [rsp+110h+var_E8], r13; struct _CTAPCBOR_DEVICE_INFO_LIST *
0x1800b4218  mov     [rsp+110h+var_F0], rsi; struct _GUID *
0x1800b421d  xor     r9d, r9d; unsigned int
0x1800b4220  xor     r8d, r8d; unsigned int
0x1800b4223  xor     edx, edx; unsigned int
0x1800b4225  mov     ecx, edi; unsigned int
0x1800b4227  call    ?I_EncodeRpcRequest@@YAJKKKKPEAU_GUID@@PEAU_CTAPCBOR_DEVICE_INFO_LIST@@KPEAEPEAU_WEBAUTHN_CTAP_RPC_PROTECTED@@KPEBEPEBGPEAU_CTAPCBOR_RPC_REQUEST@@PEAKPEAPEAE@Z; I_EncodeRpcRequest(ulong,ulong,ulong,ulong,_GUID *,_CTAPCBOR_DEVICE_INFO_LIST *,ulong,uchar *,_WEBAUTHN_CTAP_RPC_PROTECTED *,ulong,uchar const *,ushort const *,_CTAPCBOR_RPC_REQUEST *,ulong *,uchar * *)
0x1800b422c  mov     ebx, eax
0x1800b422e  lea     rcx, [rbp+4Fh+var_70]
0x1800b4232  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800b4237  test    ebx, ebx
0x1800b4239  jns     loc_1800B4786
0x1800b423f  cmp     edi, 6Dh ; 'm'
0x1800b4242  jnz     short loc_1800B4292
0x1800b4244  mov     [rbp+4Fh+var_90], r13
0x1800b4248  movaps  xmm0, xmmword ptr [rsi]
0x1800b424b  movdqa  [rbp+4Fh+var_80], xmm0
0x1800b4250  lea     rdx, [rbp+4Fh+var_80]
0x1800b4254  lea     rcx, [rbp+4Fh+var_90]
0x1800b4258  call    ?open_helper@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@@tip2@@AEAA_NPEAU_GUID@@@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>>::open_helper(_GUID *)
0x1800b425d  lea     rcx, aWebauthnplugin_144; "WebAuthNPluginPerformUVTest::reason::en"...
0x1800b4264  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800b4269  mov     rcx, [rbp+4Fh+var_90]
0x1800b426d  test    rcx, rcx
0x1800b4270  jz      short loc_1800B4284
0x1800b4272  lea     r8d, [rdi-63h]
0x1800b4276  add     rcx, 8
0x1800b427a  mov     r9, rax
0x1800b427d  mov     dl, 3
0x1800b427f  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<1,0,0>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x1800b4284  lea     rcx, [rbp+4Fh+var_90]
0x1800b4288  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginPerformUVTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginPerformUVTest,_tip_WebAuthNPluginPerformUVTest>,wil::err_returncode_policy>(void)
0x1800b428d  jmp     loc_1800B4786
0x1800b4292  cmp     edi, 64h ; 'd'
0x1800b4295  jnz     loc_1800B431B
0x1800b429b  mov     [rbp+4Fh+var_90], r13
0x1800b429f  movaps  xmm0, xmmword ptr [rsi]
0x1800b42a2  movdqa  xmmword ptr [rbp+4Fh+var_70], xmm0
0x1800b42a7  mov     ecx, 198h; cb
0x1800b42ac  call    cs:__imp_CoTaskMemAlloc
0x1800b42b2  test    rax, rax
0x1800b42b5  jnz     short loc_1800B42BD
0x1800b42b7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800b42bd  lea     rdx, [rbp+4Fh+var_70]
0x1800b42c1  mov     rcx, rax
0x1800b42c4  call    ??0?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>(_GUID *)
0x1800b42c9  mov     qword ptr [rbp+4Fh+var_80], rax
0x1800b42cd  lea     rdx, [rbp+4Fh+var_80]
0x1800b42d1  lea     rcx, [rbp+4Fh+var_90]
0x1800b42d5  call    ??4?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy> &&)
0x1800b42da  lea     rcx, [rbp+4Fh+var_80]
0x1800b42de  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(void)
0x1800b42e3  lea     rcx, aWebauthnplugin_138; "WebAuthNPluginAddAuthenticatorTest::rea"...
0x1800b42ea  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800b42ef  mov     rcx, [rbp+4Fh+var_90]
0x1800b42f3  test    rcx, rcx
0x1800b42f6  jz      short loc_1800B430D
0x1800b42f8  mov     r8d, 3
0x1800b42fe  add     rcx, 8
0x1800b4302  mov     r9, rax
0x1800b4305  mov     dl, r8b
0x1800b4308  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<1,0,0>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x1800b430d  lea     rcx, [rbp+4Fh+var_90]
0x1800b4311  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAddAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAddAuthenticatorTest,_tip_WebAuthNPluginAddAuthenticatorTest>,wil::err_returncode_policy>(void)
0x1800b4316  jmp     loc_1800B4786
0x1800b431b  cmp     edi, 66h ; 'f'
0x1800b431e  jnz     loc_1800B43A4
0x1800b4324  mov     [rbp+4Fh+var_90], r13
0x1800b4328  movaps  xmm0, xmmword ptr [rsi]
0x1800b432b  movdqa  xmmword ptr [rbp+4Fh+var_70], xmm0
0x1800b4330  mov     ecx, 198h; cb
0x1800b4335  call    cs:__imp_CoTaskMemAlloc
0x1800b433b  test    rax, rax
0x1800b433e  jnz     short loc_1800B4346
0x1800b4340  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800b4346  lea     rdx, [rbp+4Fh+var_70]
0x1800b434a  mov     rcx, rax
0x1800b434d  call    ??0?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>(_GUID *)
0x1800b4352  mov     qword ptr [rbp+4Fh+var_80], rax
0x1800b4356  lea     rdx, [rbp+4Fh+var_80]
0x1800b435a  lea     rcx, [rbp+4Fh+var_90]
0x1800b435e  call    ??4?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy> &&)
0x1800b4363  lea     rcx, [rbp+4Fh+var_80]
0x1800b4367  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(void)
0x1800b436c  lea     rcx, aWebauthnplugin_43; "WebAuthNPluginUpdateAuthenticatorDetail"...
0x1800b4373  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800b4378  mov     rcx, [rbp+4Fh+var_90]
0x1800b437c  test    rcx, rcx
0x1800b437f  jz      short loc_1800B4396
0x1800b4381  mov     r8d, 3
0x1800b4387  add     rcx, 8
0x1800b438b  mov     r9, rax
0x1800b438e  mov     dl, r8b
0x1800b4391  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<1,0,0>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x1800b4396  lea     rcx, [rbp+4Fh+var_90]
0x1800b439a  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest,_tip_WebAuthNPluginUpdateAuthenticatorDetailsTest>,wil::err_returncode_policy>(void)
0x1800b439f  jmp     loc_1800B4786
0x1800b43a4  cmp     edi, 65h ; 'e'
0x1800b43a7  jnz     loc_1800B442D
0x1800b43ad  mov     [rbp+4Fh+var_90], r13
0x1800b43b1  movaps  xmm0, xmmword ptr [rsi]
0x1800b43b4  movdqa  xmmword ptr [rbp+4Fh+var_70], xmm0
0x1800b43b9  mov     ecx, 198h; cb
0x1800b43be  call    cs:__imp_CoTaskMemAlloc
0x1800b43c4  test    rax, rax
0x1800b43c7  jnz     short loc_1800B43CF
0x1800b43c9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800b43cf  lea     rdx, [rbp+4Fh+var_70]
0x1800b43d3  mov     rcx, rax
0x1800b43d6  call    ??0?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>(_GUID *)
0x1800b43db  mov     qword ptr [rbp+4Fh+var_80], rax
0x1800b43df  lea     rdx, [rbp+4Fh+var_80]
0x1800b43e3  lea     rcx, [rbp+4Fh+var_90]
0x1800b43e7  call    ??4?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy> &&)
0x1800b43ec  lea     rcx, [rbp+4Fh+var_80]
0x1800b43f0  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>(void)
0x1800b43f5  lea     rcx, aWebauthnplugin_79; "WebAuthNPluginRemoveAuthenticatorTest::"...
0x1800b43fc  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800b4401  mov     rcx, [rbp+4Fh+var_90]
0x1800b4405  test    rcx, rcx
0x1800b4408  jz      short loc_1800B441F
0x1800b440a  mov     r8d, 3
0x1800b4410  add     rcx, 8
0x1800b4414  mov     r9, rax
0x1800b4417  mov     dl, r8b
0x1800b441a  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<1,0,0>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x1800b441f  lea     rcx, [rbp+4Fh+var_90]
0x1800b4423  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginRemoveAuthenticatorTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginRemoveAuthenticatorTest,_tip_WebAuthNPluginRemoveAuthenticatorTest>,wil::err_returncode_policy>(void)
0x1800b4428  jmp     loc_1800B4786
0x1800b442d  cmp     edi, 67h ; 'g'
0x1800b4430  jnz     short loc_1800B44B1
0x1800b4432  mov     [rbp+4Fh+var_90], r13
0x1800b4436  movaps  xmm0, xmmword ptr [rsi]
0x1800b4439  movdqa  xmmword ptr [rbp+4Fh+var_70], xmm0
0x1800b443e  mov     ecx, 150h; cb
0x1800b4443  call    cs:__imp_CoTaskMemAlloc
0x1800b4449  test    rax, rax
0x1800b444c  jnz     short loc_1800B4454
0x1800b444e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800b4454  lea     rdx, [rbp+4Fh+var_70]
0x1800b4458  mov     rcx, rax
0x1800b445b  call    ??0?$merged_data@U_tip_WebAuthNPluginGetAuthenticatorListTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>(_GUID *)
0x1800b4460  mov     qword ptr [rbp+4Fh+var_80], rax
0x1800b4464  lea     rdx, [rbp+4Fh+var_80]
0x1800b4468  lea     rcx, [rbp+4Fh+var_90]
0x1800b446c  call    ??4?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginGetAuthenticatorListTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy> &&)
0x1800b4471  lea     rcx, [rbp+4Fh+var_80]
0x1800b4475  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginGetAuthenticatorListTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy>(void)
0x1800b447a  lea     rcx, aWebauthnplugin_146; "WebAuthNPluginGetAuthenticatorListTest:"...
0x1800b4481  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800b4486  mov     rcx, [rbp+4Fh+var_90]
0x1800b448a  test    rcx, rcx
0x1800b448d  jz      short loc_1800B44A3
0x1800b448f  mov     r8d, 7
0x1800b4495  add     rcx, 8
0x1800b4499  mov     r9, rax
0x1800b449c  mov     dl, 3
0x1800b449e  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<1,0,0>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x1800b44a3  lea     rcx, [rbp+4Fh+var_90]
0x1800b44a7  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginGetAuthenticatorListTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginGetAuthenticatorListTest,_tip_WebAuthNPluginGetAuthenticatorListTest>,wil::err_returncode_policy>(void)
0x1800b44ac  jmp     loc_1800B4786
0x1800b44b1  cmp     edi, 68h ; 'h'
0x1800b44b4  jnz     short loc_1800B44F8
0x1800b44b6  mov     [rbp+4Fh+var_90], r13
0x1800b44ba  movaps  xmm0, xmmword ptr [rsi]
0x1800b44bd  movdqa  xmmword ptr [rbp+4Fh+var_70], xmm0
0x1800b44c2  lea     rdx, [rbp+4Fh+var_70]
0x1800b44c6  lea     rcx, [rbp+4Fh+var_90]
0x1800b44ca  call    ?open_helper@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@@tip2@@AEAA_NPEAU_GUID@@@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>>::open_helper(_GUID *)
0x1800b44cf  lea     rcx, aWebauthnplugin_82; "WebAuthNPluginSetAuthenticatorStateTest"...
0x1800b44d6  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800b44db  mov     r8, rax
0x1800b44de  lea     edx, [rdi-65h]
0x1800b44e1  lea     rcx, [rbp+4Fh+var_90]
0x1800b44e5  call    ?complete_and_fail@?$tip_test@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest@@U1@@details@tip2@@@tip2@@QEAAXGPEBD@Z; tip2::tip_test<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorGetAllCredentialsTest>>::complete_and_fail(ushort,char const *)
0x1800b44ea  lea     rcx, [rbp+4Fh+var_90]
0x1800b44ee  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginSetAuthenticatorStateTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginSetAuthenticatorStateTest,_tip_WebAuthNPluginSetAuthenticatorStateTest>,wil::err_returncode_policy>(void)
0x1800b44f3  jmp     loc_1800B4786
0x1800b44f8  cmp     edi, 69h ; 'i'
0x1800b44fb  jnz     loc_1800B4581
0x1800b4501  mov     [rbp+4Fh+var_90], r13
0x1800b4505  movaps  xmm0, xmmword ptr [rsi]
0x1800b4508  movdqa  xmmword ptr [rbp+4Fh+var_70], xmm0
0x1800b450d  mov     ecx, 1A0h; cb
0x1800b4512  call    cs:__imp_CoTaskMemAlloc
0x1800b4518  test    rax, rax
0x1800b451b  jnz     short loc_1800B4523
0x1800b451d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800b4523  lea     rdx, [rbp+4Fh+var_70]
0x1800b4527  mov     rcx, rax
0x1800b452a  call    ??0?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>(_GUID *)
0x1800b452f  mov     qword ptr [rbp+4Fh+var_80], rax
0x1800b4533  lea     rdx, [rbp+4Fh+var_80]
0x1800b4537  lea     rcx, [rbp+4Fh+var_90]
0x1800b453b  call    ??4?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy> &&)
0x1800b4540  lea     rcx, [rbp+4Fh+var_80]
0x1800b4544  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(void)
0x1800b4549  lea     rcx, aWebauthnplugin_83; "WebAuthNPluginAuthenticatorAddCredentia"...
0x1800b4550  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800b4555  mov     rcx, [rbp+4Fh+var_90]
0x1800b4559  test    rcx, rcx
0x1800b455c  jz      short loc_1800B4573
0x1800b455e  mov     r8d, 3
0x1800b4564  add     rcx, 8
0x1800b4568  mov     r9, rax
0x1800b456b  mov     dl, r8b
0x1800b456e  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<1,0,0>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x1800b4573  lea     rcx, [rbp+4Fh+var_90]
0x1800b4577  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorAddCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorAddCredentialsTest,_tip_WebAuthNPluginAuthenticatorAddCredentialsTest>,wil::err_returncode_policy>(void)
0x1800b457c  jmp     loc_1800B4786
0x1800b4581  cmp     edi, 6Ah ; 'j'
0x1800b4584  jnz     loc_1800B460A
0x1800b458a  mov     [rbp+4Fh+var_90], r13
0x1800b458e  movaps  xmm0, xmmword ptr [rsi]
0x1800b4591  movdqa  xmmword ptr [rbp+4Fh+var_70], xmm0
0x1800b4596  mov     ecx, 1A0h; cb
0x1800b459b  call    cs:__imp_CoTaskMemAlloc
0x1800b45a1  test    rax, rax
0x1800b45a4  jnz     short loc_1800B45AC
0x1800b45a6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800b45ac  lea     rdx, [rbp+4Fh+var_70]
0x1800b45b0  mov     rcx, rax
0x1800b45b3  call    ??0?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>(_GUID *)
0x1800b45b8  mov     qword ptr [rbp+4Fh+var_80], rax
0x1800b45bc  lea     rdx, [rbp+4Fh+var_80]
0x1800b45c0  lea     rcx, [rbp+4Fh+var_90]
0x1800b45c4  call    ??4?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy> &&)
0x1800b45c9  lea     rcx, [rbp+4Fh+var_80]
0x1800b45cd  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(void)
0x1800b45d2  lea     rcx, aWebauthnplugin_55; "WebAuthNPluginAuthenticatorRemoveCreden"...
0x1800b45d9  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x1800b45de  mov     rcx, [rbp+4Fh+var_90]
0x1800b45e2  test    rcx, rcx
0x1800b45e5  jz      short loc_1800B45FC
0x1800b45e7  mov     r8d, 3
0x1800b45ed  add     rcx, 8
0x1800b45f1  mov     r9, rax
0x1800b45f4  mov     dl, r8b
0x1800b45f7  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestCompletionKind@@GPEBD@Z; tip2::details::shared_data<1,0,0>::complete_without_lock(TestCompletionKind,ushort,char const *)
0x1800b45fc  lea     rcx, [rbp+4Fh+var_90]
0x1800b4600  call    ??1?$com_ptr_t@V?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveCredentialsTest>,wil::err_returncode_policy>(void)
0x1800b4605  jmp     loc_1800B4786
0x1800b460a  cmp     edi, 6Bh ; 'k'
0x1800b460d  jnz     short loc_1800B468E
0x1800b460f  mov     [rbp+4Fh+var_90], r13
0x1800b4613  movaps  xmm0, xmmword ptr [rsi]
0x1800b4616  movdqa  xmmword ptr [rbp+4Fh+var_70], xmm0
0x1800b461b  mov     ecx, 1A0h; cb
0x1800b4620  call    cs:__imp_CoTaskMemAlloc
0x1800b4626  test    rax, rax
0x1800b4629  jnz     short loc_1800B4631
0x1800b462b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800b4631  lea     rdx, [rbp+4Fh+var_70]
0x1800b4635  mov     rcx, rax
0x1800b4638  call    ??0?$merged_data@U_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>::merged_data<_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest,_tip_WebAuthNPluginAuthenticatorRemoveAllCredentialsTest>(_GUID *)
0x1800b463d  mov     qword ptr [rbp+4Fh+var_80], rax
0x1800b4641  lea     rdx, [rbp+4Fh+var_80]
  ... truncated ...
```
