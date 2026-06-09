# SingletonHelpers::SingletonHelper::TryClaimSingletonOrRedirectLaunch(winrt::Windows::Foundation::Collections::ValueSet const &,SingletonHelpers::SingletonHelper::ForegroundOption,bool)

- ea: `0x18004b86c`
- end: `0x18004bc21`
- name: `?TryClaimSingletonOrRedirectLaunch@SingletonHelper@SingletonHelpers@@QEAA?AW4SingletonClaimResult@2@AEBUValueSet@Collections@Foundation@Windows@winrt@@W4ForegroundOption@12@_N@Z`
- size: `949`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18004a43c`

## callees

- `0x180002b20`
- `0x18000e37c`
- `0x18001049c`
- `0x1800176b0`
- `0x18001e0a8`
- `0x180021be8`
- `0x180021e34`
- `0x1800221a8`
- `0x180026ca0`
- `0x18002bf60`
- `0x18002d9cc`
- `0x180049f10`
- `0x18004b86c`
- `0x18004fd14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bb41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bb41`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18004b95b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18004b95b`
- `faultrep!ReportCoreHang` at `0x18004bae4`
- `faultrep!ReportCoreHang` at `0x18004bae4`

## string_xrefs

- `0x18004bbf9`: `ShellCommon\Internal\Shell\Inc\SingletonHelpers.h`
- `0x18004bc0f`: `OneCore\Internal\Sdk\Inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SingletonHelpers::SingletonHelper::TryClaimSingletonOrRedirectLaunch(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  void **v5; // r13
  _QWORD *v6; // rax
  _QWORD *v7; // rdx
  __int64 v8; // rcx
  DWORD v9; // r12d
  unsigned int v10; // ecx
  char v11; // r14
  __int64 v12; // rsi
  void *v13; // rbx
  DWORD v14; // eax
  const char *v15; // r9
  void *v16; // rbx
  _QWORD *v17; // rbx
  _QWORD *v18; // rcx
  __int64 v19; // rax
  _QWORD *v20; // r14
  _QWORD *v21; // rax
  __int64 v22; // rcx
  int ProcessIdForSingletonInstance; // eax
  int v24; // r15d
  int v25; // edx
  unsigned int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rax
  int v29; // ebx
  const char *v31; // r9
  _QWORD *v32; // rax
  __int64 v33; // rcx
  _QWORD *v34; // rdi
  int v35; // [rsp+20h] [rbp-89h]
  char v36; // [rsp+40h] [rbp-69h]
  unsigned int v37; // [rsp+44h] [rbp-65h]
  int v38; // [rsp+48h] [rbp-61h]
  unsigned int v39; // [rsp+4Ch] [rbp-5Dh]
  void *v40; // [rsp+50h] [rbp-59h] BYREF
  char v41[8]; // [rsp+58h] [rbp-51h] BYREF
  _QWORD *v42; // [rsp+60h] [rbp-49h] BYREF
  __int64 v43; // [rsp+68h] [rbp-41h]
  _QWORD *v44; // [rsp+70h] [rbp-39h] BYREF
  __int64 v45; // [rsp+78h] [rbp-31h]
  char v46[8]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v47; // [rsp+88h] [rbp-21h]
  _QWORD v48[2]; // [rsp+90h] [rbp-19h] BYREF
  _QWORD v49[2]; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v50; // [rsp+B0h] [rbp+7h] BYREF
  int v51; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v47 = a2;
  v5 = (void **)(a1 + 112);
  if ( *(_QWORD *)(a1 + 112) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x15C,
      (unsigned int)"ShellCommon\\Internal\\Shell\\Inc\\SingletonHelpers.h",
      a4);
  v50 = 0;
  tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::start(
    &v50,
    &v42);
  v6 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(
                   &v50,
                   &v51);
  v7 = (_QWORD *)(a1 + 72);
  v8 = *v6 + 272LL;
  if ( v8 != a1 + 72 )
  {
    if ( *(_QWORD *)(a1 + 96) > 7u )
      v7 = (_QWORD *)*v7;
    std::wstring::_Assign<wchar_t>(v8, v7, *(_QWORD *)(a1 + 88));
  }
  tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(&v51);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(
                          &v50,
                          &v51)
           + 304LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(&v51);
  v9 = 0;
  v10 = 0;
  v38 = 0;
  v37 = 0;
  v11 = 0;
  v36 = 0;
  v12 = -1;
  while ( 1 )
  {
    v39 = v10;
    if ( v10 >= 0x2710 && !v11 )
    {
LABEL_42:
      tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::complete(&v50);
      wil::com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>(&v50);
      return 2;
    }
    v13 = *(void **)(a1 + 104);
    v14 = WaitForSingleObjectEx(v13, v9, 0);
    if ( v14 == 258 )
    {
      v13 = 0;
    }
    else if ( (v14 & 0xFFFFFF7F) != 0 )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"OneCore\\Internal\\Sdk\\Inc\\wil\\opensource\\wil\\resource.h",
        v15);
    }
    v40 = v13;
    if ( v5 != &v40 )
    {
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        v5,
        v13);
      v40 = 0;
    }
    v16 = *v5;
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v40);
    if ( v16 )
      break;
    if ( v11 )
      goto LABEL_42;
    v17 = (_QWORD *)(a1 + 40);
    if ( *(_QWORD *)(a1 + 64) <= 7u )
      v18 = (_QWORD *)(a1 + 40);
    else
      v18 = (_QWORD *)*v17;
    v48[0] = v18;
    v19 = -1;
    do
      ++v19;
    while ( *((_WORD *)v18 + v19) );
    v48[1] = v19;
    v20 = (_QWORD *)(a1 + 8);
    if ( *(_QWORD *)(a1 + 32) <= 7u )
      v21 = (_QWORD *)(a1 + 8);
    else
      v21 = (_QWORD *)*v20;
    v49[0] = v21;
    v22 = -1;
    do
      ++v22;
    while ( *((_WORD *)v21 + v22) );
    v49[1] = v22;
    ProcessIdForSingletonInstance = SingletonHelpers::details::GetProcessIdForSingletonInstance(v49, v48);
    v24 = ProcessIdForSingletonInstance;
    v25 = v38;
    if ( ProcessIdForSingletonInstance == v38 )
    {
      v26 = v37;
    }
    else
    {
      v25 = ProcessIdForSingletonInstance;
      v38 = ProcessIdForSingletonInstance;
      v26 = 0;
    }
    v37 = v9 + v26;
    if ( !v25 )
      goto LABEL_39;
    *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(
                            &v50,
                            v46)
             + 306LL) = 1;
    tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(v46);
    v27 = *(_QWORD *)(a1 + 56);
    if ( *(_QWORD *)(a1 + 64) > 7u )
      v17 = (_QWORD *)*v17;
    v44 = v17;
    v45 = v27;
    v28 = *(_QWORD *)(a1 + 24);
    if ( *(_QWORD *)(a1 + 32) > 7u )
      v20 = (_QWORD *)*v20;
    v42 = v20;
    v43 = v28;
    v11 = 1;
    v29 = SingletonHelpers::SingletonHelper::TryRedirectLaunchToProcess(
            (unsigned int)&v42,
            (unsigned int)&v44,
            v24,
            v47,
            v35,
            1);
    *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(
                             &v50,
                             v41)
              + 308LL) = v29;
    tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(v41);
    if ( !v29 )
    {
      tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::complete(&v50);
      wil::com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>(&v50);
      return 1;
    }
    if ( v29 == 1 && v37 >= 0x2710 )
    {
      v51 = v24;
      ReportCoreHang(&v51, 1, 0, 32);
      v36 = 1;
    }
    else
    {
LABEL_39:
      v11 = v36;
    }
    v10 = v9 + v39;
    v9 += 200;
  }
  *(_DWORD *)(a1 + 120) = GetCurrentThreadId();
  v32 = (_QWORD *)(a1 + 40);
  if ( *(_QWORD *)(a1 + 64) > 7u )
    v32 = (_QWORD *)*v32;
  v42 = v32;
  v33 = -1;
  do
    ++v33;
  while ( *((_WORD *)v32 + v33) );
  v43 = v33;
  v34 = (_QWORD *)(a1 + 8);
  if ( v34[3] > 7u )
    v34 = (_QWORD *)*v34;
  v44 = v34;
  do
    ++v12;
  while ( *((_WORD *)v34 + v12) );
  v45 = v12;
  SingletonHelpers::details::SetPIDAndClearCommunicationHWNDForSingletonInstance(v5, (__int64)&v44, (__int64)&v42, v31);
  *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(
                          &v50,
                          v41)
           + 305LL) = 1;
  tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(v41);
  tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::complete(&v50);
  wil::com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>(&v50);
  return 0;
}

```

## disassembly

```asm
0x18004b86c  mov     [rsp-8+arg_10], rbx
0x18004b871  push    rbp
0x18004b872  push    rsi
0x18004b873  push    rdi
0x18004b874  push    r12
0x18004b876  push    r13
0x18004b878  push    r14
0x18004b87a  push    r15
0x18004b87c  lea     rbp, [rsp-27h]
0x18004b881  sub     rsp, 0D0h
0x18004b888  mov     rax, cs:__security_cookie
0x18004b88f  xor     rax, rsp
0x18004b892  mov     [rbp+57h+var_40], rax
0x18004b896  mov     [rbp+57h+var_78], rdx
0x18004b89a  mov     rdi, rcx
0x18004b89d  lea     r13, [rcx+70h]
0x18004b8a1  mov     rcx, [rbp+5Fh]; this
0x18004b8a5  xor     r15d, r15d
0x18004b8a8  cmp     [r13+0], r15
0x18004b8ac  jnz     loc_18004BBF9
0x18004b8b2  mov     [rbp+57h+var_50], r15
0x18004b8b6  lea     rdx, [rbp+57h+var_A0]
0x18004b8ba  lea     rcx, [rbp+57h+var_50]
0x18004b8be  call    ?start@?$tip_test@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::start(void)
0x18004b8c3  lea     rdx, [rbp+57h+var_48]
0x18004b8c7  lea     rcx, [rbp+57h+var_50]
0x18004b8cb  call    ??C?$tip_test@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(void)
0x18004b8d0  nop
0x18004b8d1  lea     rdx, [rdi+48h]
0x18004b8d5  mov     rcx, [rax]
0x18004b8d8  add     rcx, 110h
0x18004b8df  cmp     rcx, rdx
0x18004b8e2  jz      short loc_18004B8F8
0x18004b8e4  mov     r8, [rdx+10h]
0x18004b8e8  cmp     qword ptr [rdx+18h], 7
0x18004b8ed  jbe     short loc_18004B8F2
0x18004b8ef  mov     rdx, [rdx]
0x18004b8f2  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18004b8f7  nop
0x18004b8f8  lea     rcx, [rbp+57h+var_48]
0x18004b8fc  call    ??1?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(void)
0x18004b901  lea     rdx, [rbp+57h+var_48]
0x18004b905  lea     rcx, [rbp+57h+var_50]
0x18004b909  call    ??C?$tip_test@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(void)
0x18004b90e  mov     rcx, [rax]
0x18004b911  mov     byte ptr [rcx+130h], 1
0x18004b918  lea     rcx, [rbp+57h+var_48]
0x18004b91c  call    ??1?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(void)
0x18004b921  mov     r12d, r15d
0x18004b924  mov     ecx, r15d
0x18004b927  mov     [rbp+57h+var_B8], r15d
0x18004b92b  mov     [rbp+57h+var_BC], r15d
0x18004b92f  mov     r14b, r15b
0x18004b932  mov     [rbp+57h+var_C0], r15b
0x18004b936  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004b93a  mov     [rbp+57h+var_B4], ecx
0x18004b93d  cmp     ecx, 2710h
0x18004b943  jb      short loc_18004B94E
0x18004b945  test    r14b, r14b
0x18004b948  jz      loc_18004BB24
0x18004b94e  mov     rbx, [rdi+68h]
0x18004b952  xor     r8d, r8d; bAlertable
0x18004b955  mov     edx, r12d; dwMilliseconds
0x18004b958  mov     rcx, rbx; hHandle
0x18004b95b  call    cs:__imp_WaitForSingleObjectEx
0x18004b961  cmp     eax, 102h
0x18004b966  jz      short loc_18004B975
0x18004b968  test    eax, 0FFFFFF7Fh
0x18004b96d  jnz     loc_18004BC0B
0x18004b973  jmp     short loc_18004B978
0x18004b975  mov     rbx, r15
0x18004b978  mov     [rbp+57h+var_B0], rbx
0x18004b97c  lea     rax, [rbp+57h+var_B0]
0x18004b980  cmp     r13, rax
0x18004b983  jz      short loc_18004B994
0x18004b985  mov     rdx, rbx
0x18004b988  mov     rcx, r13
0x18004b98b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18004b990  mov     [rbp+57h+var_B0], r15
0x18004b994  mov     rbx, [r13+0]
0x18004b998  lea     rcx, [rbp+57h+var_B0]
0x18004b99c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004b9a1  test    rbx, rbx
0x18004b9a4  jnz     loc_18004BB41
0x18004b9aa  test    r14b, r14b
0x18004b9ad  jnz     loc_18004BB24
0x18004b9b3  lea     rbx, [rdi+28h]
0x18004b9b7  cmp     qword ptr [rdi+40h], 7
0x18004b9bc  jbe     short loc_18004B9C3
0x18004b9be  mov     rcx, [rbx]
0x18004b9c1  jmp     short loc_18004B9C6
0x18004b9c3  mov     rcx, rbx
0x18004b9c6  mov     [rbp+57h+var_70], rcx
0x18004b9ca  mov     rax, rsi
0x18004b9cd  inc     rax
0x18004b9d0  cmp     [rcx+rax*2], r15w
0x18004b9d5  jnz     short loc_18004B9CD
0x18004b9d7  mov     [rbp+57h+var_68], rax
0x18004b9db  lea     r14, [rdi+8]
0x18004b9df  cmp     qword ptr [rdi+20h], 7
0x18004b9e4  jbe     short loc_18004B9EB
0x18004b9e6  mov     rax, [r14]
0x18004b9e9  jmp     short loc_18004B9EE
0x18004b9eb  mov     rax, r14
0x18004b9ee  mov     [rbp+57h+var_60], rax
0x18004b9f2  mov     rcx, rsi
0x18004b9f5  inc     rcx
0x18004b9f8  cmp     [rax+rcx*2], r15w
0x18004b9fd  jnz     short loc_18004B9F5
0x18004b9ff  mov     [rbp+57h+var_58], rcx
0x18004ba03  lea     rdx, [rbp+57h+var_70]
0x18004ba07  lea     rcx, [rbp+57h+var_60]
0x18004ba0b  call    ?GetProcessIdForSingletonInstance@details@SingletonHelpers@@YAKAEBV?$basic_zstring_view@_W@wil@@0@Z; SingletonHelpers::details::GetProcessIdForSingletonInstance(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &)
0x18004ba10  mov     r15d, eax
0x18004ba13  mov     edx, [rbp+57h+var_B8]
0x18004ba16  cmp     eax, edx
0x18004ba18  jz      short loc_18004BA23
0x18004ba1a  mov     edx, eax
0x18004ba1c  mov     [rbp+57h+var_B8], eax
0x18004ba1f  xor     eax, eax
0x18004ba21  jmp     short loc_18004BA26
0x18004ba23  mov     eax, [rbp+57h+var_BC]
0x18004ba26  add     eax, r12d
0x18004ba29  mov     [rbp+57h+var_BC], eax
0x18004ba2c  test    edx, edx
0x18004ba2e  jz      loc_18004BAF0
0x18004ba34  lea     rdx, [rbp+57h+var_80]
0x18004ba38  lea     rcx, [rbp+57h+var_50]
0x18004ba3c  call    ??C?$tip_test@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(void)
0x18004ba41  mov     rcx, [rax]
0x18004ba44  mov     byte ptr [rcx+132h], 1
0x18004ba4b  lea     rcx, [rbp+57h+var_80]
0x18004ba4f  call    ??1?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(void)
0x18004ba54  mov     rax, [rdi+38h]
0x18004ba58  cmp     qword ptr [rdi+40h], 7
0x18004ba5d  jbe     short loc_18004BA62
0x18004ba5f  mov     rbx, [rbx]
0x18004ba62  mov     [rbp+57h+var_90], rbx
0x18004ba66  mov     [rbp+57h+var_88], rax
0x18004ba6a  mov     rax, [rdi+18h]
0x18004ba6e  cmp     qword ptr [rdi+20h], 7
0x18004ba73  jbe     short loc_18004BA78
0x18004ba75  mov     r14, [r14]
0x18004ba78  mov     [rbp+57h+var_A0], r14
0x18004ba7c  mov     [rbp+57h+var_98], rax
0x18004ba80  mov     r14d, 1
0x18004ba86  mov     [rsp+100h+var_D8], r14b
0x18004ba8b  mov     r9, [rbp+57h+var_78]
0x18004ba8f  mov     r8d, r15d
0x18004ba92  lea     rdx, [rbp+57h+var_90]
0x18004ba96  lea     rcx, [rbp+57h+var_A0]
0x18004ba9a  call    ?TryRedirectLaunchToProcess@SingletonHelper@SingletonHelpers@@KA?AW4RedirectionResult@details@2@AEBV?$basic_zstring_view@_W@wil@@0KAEBUValueSet@Collections@Foundation@Windows@winrt@@W4ForegroundOption@12@_NW4StandardMessage@@PEAVFlowEndpointBase@@@Z; SingletonHelpers::SingletonHelper::TryRedirectLaunchToProcess(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,ulong,winrt::Windows::Foundation::Collections::ValueSet const &,SingletonHelpers::SingletonHelper::ForegroundOption,bool,StandardMessage,FlowEndpointBase *)
0x18004ba9f  mov     ebx, eax
0x18004baa1  lea     rdx, [rbp+57h+var_A8]
0x18004baa5  lea     rcx, [rbp+57h+var_50]
0x18004baa9  call    ??C?$tip_test@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(void)
0x18004baae  mov     rcx, [rax]
0x18004bab1  mov     [rcx+134h], ebx
0x18004bab7  lea     rcx, [rbp+57h+var_A8]
0x18004babb  call    ??1?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(void)
0x18004bac0  test    ebx, ebx
0x18004bac2  jz      short loc_18004BB09
0x18004bac4  cmp     ebx, r14d
0x18004bac7  jnz     short loc_18004BAF0
0x18004bac9  cmp     [rbp+57h+var_BC], 2710h
0x18004bad0  jb      short loc_18004BAF0
0x18004bad2  mov     [rbp+57h+var_48], r15d
0x18004bad6  lea     r9d, [r14+1Fh]
0x18004bada  xor     r8d, r8d
0x18004badd  mov     edx, r14d
0x18004bae0  lea     rcx, [rbp+57h+var_48]
0x18004bae4  call    cs:__imp_ReportCoreHang
0x18004baea  mov     [rbp+57h+var_C0], r14b
0x18004baee  jmp     short loc_18004BAF4
0x18004baf0  mov     r14b, [rbp+57h+var_C0]
0x18004baf4  mov     ecx, [rbp+57h+var_B4]
0x18004baf7  add     ecx, r12d
0x18004bafa  add     r12d, 0C8h
0x18004bb01  xor     r15d, r15d
0x18004bb04  jmp     loc_18004B93A
0x18004bb09  lea     rcx, [rbp+57h+var_50]
0x18004bb0d  call    ?complete@?$tip_test@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::complete(void)
0x18004bb12  nop
0x18004bb13  lea     rcx, [rbp+57h+var_50]
0x18004bb17  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>(void)
0x18004bb1c  mov     eax, r14d
0x18004bb1f  jmp     loc_18004BBD2
0x18004bb24  lea     rcx, [rbp+57h+var_50]
0x18004bb28  call    ?complete@?$tip_test@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::complete(void)
0x18004bb2d  nop
0x18004bb2e  lea     rcx, [rbp+57h+var_50]
0x18004bb32  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>(void)
0x18004bb37  mov     eax, 2
0x18004bb3c  jmp     loc_18004BBD2
0x18004bb41  call    cs:__imp_GetCurrentThreadId
0x18004bb47  mov     [rdi+78h], eax
0x18004bb4a  lea     rax, [rdi+28h]
0x18004bb4e  cmp     qword ptr [rax+18h], 7
0x18004bb53  jbe     short loc_18004BB58
0x18004bb55  mov     rax, [rax]
0x18004bb58  mov     [rbp+57h+var_A0], rax
0x18004bb5c  mov     rcx, rsi
0x18004bb5f  inc     rcx
0x18004bb62  cmp     [rax+rcx*2], r15w
0x18004bb67  jnz     short loc_18004BB5F
0x18004bb69  mov     [rbp+57h+var_98], rcx
0x18004bb6d  add     rdi, 8
0x18004bb71  cmp     qword ptr [rdi+18h], 7
0x18004bb76  jbe     short loc_18004BB7B
0x18004bb78  mov     rdi, [rdi]
0x18004bb7b  mov     [rbp+57h+var_90], rdi
0x18004bb7f  inc     rsi
0x18004bb82  cmp     [rdi+rsi*2], r15w
0x18004bb87  jnz     short loc_18004BB7F
0x18004bb89  mov     [rbp+57h+var_88], rsi
0x18004bb8d  lea     r8, [rbp+57h+var_A0]
0x18004bb91  lea     rdx, [rbp+57h+var_90]
0x18004bb95  mov     rcx, r13
0x18004bb98  call    ?SetPIDAndClearCommunicationHWNDForSingletonInstance@details@SingletonHelpers@@YAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_zstring_view@_W@4@1@Z
0x18004bb9d  lea     rdx, [rbp+57h+var_A8]
0x18004bba1  lea     rcx, [rbp+57h+var_50]
0x18004bba5  call    ??C?$tip_test@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::operator->(void)
0x18004bbaa  mov     rcx, [rax]
0x18004bbad  mov     byte ptr [rcx+131h], 1
0x18004bbb4  lea     rcx, [rbp+57h+var_A8]
0x18004bbb8  call    ??1?$test_data_control@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>::~test_data_control<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>>(void)
0x18004bbbd  lea     rcx, [rbp+57h+var_50]
0x18004bbc1  call    ?complete@?$tip_test@V?$merged_data@U_tip_UXFrameInvocationTest@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::tip_test<tip2::details::merged_data<_tip_UXFrameInvocationTest,_tip_UXFrameInvocationTest>>::complete(void)
0x18004bbc6  nop
0x18004bbc7  lea     rcx, [rbp+57h+var_50]
0x18004bbcb  call    ??1?$com_ptr_t@V?$merged_data@U_tip_SingletonHelperRedirectionTest@details@SingletonHelpers@@U123@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<SingletonHelpers::details::_tip_SingletonHelperRedirectionTest,SingletonHelpers::details::_tip_SingletonHelperRedirectionTest>,wil::err_returncode_policy>(void)
0x18004bbd0  xor     eax, eax
0x18004bbd2  mov     rcx, [rbp+57h+var_40]
0x18004bbd6  xor     rcx, rsp; StackCookie
0x18004bbd9  call    __security_check_cookie
0x18004bbde  mov     rbx, [rsp+100h+arg_10]
0x18004bbe6  add     rsp, 0D0h
0x18004bbed  pop     r15
0x18004bbef  pop     r14
0x18004bbf1  pop     r13
0x18004bbf3  pop     r12
0x18004bbf5  pop     rdi
0x18004bbf6  pop     rsi
0x18004bbf7  pop     rbp
0x18004bbf8  retn
0x18004bbf9  lea     r8, aShellcommonInt; "ShellCommon\\Internal\\Shell\\Inc\\Sing"...
0x18004bc00  mov     edx, 15Ch; void *
0x18004bc05  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004bc0b  mov     rcx, [rbp+5Fh]; this
0x18004bc0f  lea     r8, aOnecoreInterna_2; "OneCore\\Internal\\Sdk\\Inc\\wil\\opens"...
0x18004bc16  mov     edx, 0E01h; void *
0x18004bc1b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
