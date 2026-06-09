# ?StartConnect@ServerConnector@@UEAA?AV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@XZ

- ea: `0x180015a70`
- end: `0x180015d25`
- name: `?StartConnect@ServerConnector@@UEAA?AV?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@XZ`
- size: `693`
- prototype: `LPCWSTR *__fastcall(__int64, LPCWSTR *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800054c0`
- `0x180007344`
- `0x180011810`
- `0x180015a70`
- `0x180016010`
- `0x1800161b8`
- `0x180016c74`
- `0x18002991c`
- `0x18002a514`
- `0x18003d414`
- `0x180043680`
- `0x180074d38`
- `0x1800755f8`
- `0x1800759e4`
- `0x180075d1c`
- `0x1800761c8`
- `0x180080854`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c80`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x180015c61`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x180015c61`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x180015b9a`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x180015b9a`

## string_xrefs

- `0x180015bc3`: `onecore\windows\accessibletech\uiamanager\dll\namedpipechannel.cpp`
- `0x180015c6b`: `onecore\windows\accessibletech\uiamanager\dll\namedpipechannel.cpp`
- `0x180015c98`: `onecore\windows\accessibletech\uiamanager\dll\namedpipechannel.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
LPCWSTR *__fastcall ServerConnector::StartConnect(__int64 a1, LPCWSTR *a2)
{
  LPCWSTR *v4; // rsi
  _QWORD *v5; // rax
  __int64 v6; // rcx
  LPCWSTR *v7; // rax
  const WCHAR *v8; // rcx
  HANDLE NamedPipeW; // rax
  const char *v10; // r9
  _QWORD *v11; // r14
  __int64 *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rdx
  std::_Ref_count_base *v15; // rcx
  const char *v16; // r9
  DWORD LastError; // eax
  const char *v18; // r9
  __int64 *v19; // rax
  LPCWSTR *v21; // [rsp+40h] [rbp-59h] BYREF
  LPSECURITY_ATTRIBUTES lpSecurityAttributes[3]; // [rsp+48h] [rbp-51h] BYREF
  char v23; // [rsp+60h] [rbp-39h]
  char v24[16]; // [rsp+68h] [rbp-31h] BYREF
  LPCWSTR lpName[3]; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int64 v26; // [rsp+90h] [rbp-9h]
  _OWORD v27[2]; // [rsp+98h] [rbp-1h] BYREF
  __int128 v28; // [rsp+B8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v21 = a2;
  v4 = (LPCWSTR *)(a1 + 8);
  v5 = *(_QWORD **)(a1 + 8);
  if ( v5 && *v5 )
    ServerConnector::Reset((ServerConnector *)a1);
  lpSecurityAttributes[2] = (LPSECURITY_ATTRIBUTES)a1;
  v23 = 1;
  _create___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
    v4,
    1,
    0);
  *(_OWORD *)(a1 + 40) = 0;
  *(_OWORD *)(a1 + 56) = 0;
  if ( *v4 )
    v6 = *(_QWORD *)*v4;
  else
    v6 = 0;
  *(_QWORD *)(a1 + 64) = v6;
  v27[0] = 0;
  v27[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v27[0]) = 0;
  v28 = *(_OWORD *)(*(_QWORD *)(a1 + 72) + 8LL);
  anonymous_namespace_::GetUiaManagerPipeName(lpName, &v28, v27);
  BasicUtils::GetSecurityAttributesFromCrossMachineService(lpSecurityAttributes, *(_QWORD *)(a1 + 72));
  v7 = lpName;
  if ( v26 > 7 )
    v7 = (LPCWSTR *)lpName[0];
  v21 = v7;
  UiaManagerTraceLoggingProvider::NamedPipeCreateServerPipe<unsigned short const *>(&v21);
  v8 = (const WCHAR *)lpName;
  if ( v26 > 7 )
    v8 = lpName[0];
  NamedPipeW = CreateNamedPipeW(v8, 0x40000003u, 6u, 1u, 0xFF8u, 0xFF8u, 0x1388u, lpSecurityAttributes[0]);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a1 + 24,
    NamedPipeW);
  if ( ((*(_QWORD *)(a1 + 24) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2CC,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\namedpipechannel.cpp",
      v10);
  v11 = (_QWORD *)std::shared_ptr<CoreUiSession::HwndAndViewIdConversionData>::shared_ptr<CoreUiSession::HwndAndViewIdConversionData>(
                    v24,
                    a1 + 72);
  *(_QWORD *)&v28 = v11;
  if ( (*(unsigned int (__fastcall **)(_QWORD, LPCWSTR *, _OWORD *, _QWORD))(*(_QWORD *)*v11 + 8LL))(
         *v11,
         lpName,
         v27,
         0) != 1
    || !*(_QWORD *)(a1 + 32) )
  {
    v12 = (__int64 *)std::make_unique<BasicUtils::CrossMachinePipeNameGuard,std::wstring const &,std::wstring const &,std::shared_ptr<ICrossMachineCommunicationServices> &,0>(
                       &v21,
                       lpName,
                       v27,
                       v11);
    v13 = *v12;
    *v12 = 0;
    v14 = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(a1 + 32) = v13;
    if ( v14 )
      std::default_delete<BasicUtils::CrossMachinePipeNameGuard>::operator()();
    std::unique_ptr<BasicUtils::CrossMachinePipeNameGuard>::~unique_ptr<BasicUtils::CrossMachinePipeNameGuard>(&v21);
  }
  v15 = (std::_Ref_count_base *)v11[1];
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  if ( ConnectNamedPipe(*(HANDLE *)(a1 + 24), (LPOVERLAPPED)(a1 + 40)) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2D5,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\namedpipechannel.cpp",
      v16);
  LastError = GetLastError();
  if ( LastError == 535 )
  {
    _SetEvent___event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil__QEBAXXZ(v4);
  }
  else if ( LastError != 997 )
  {
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2E8,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\namedpipechannel.cpp",
      v18);
  }
  *a2 = 0;
  a2[1] = 0;
  v19 = (__int64 *)v4[1];
  if ( v19 )
    _InterlockedIncrement((volatile signed __int32 *)v19 + 2);
  *a2 = *v4;
  a2[1] = v4[1];
  wil::details::unique_storage<wil::details::resource_policy<_SECURITY_ATTRIBUTES *,void (*)(_SECURITY_ATTRIBUTES *),&private: static void BasicUtils::DestroySecurityAttribute(_SECURITY_ATTRIBUTES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_ATTRIBUTES *,_SECURITY_ATTRIBUTES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_ATTRIBUTES *,void (*)(_SECURITY_ATTRIBUTES *),&private: static void BasicUtils::DestroySecurityAttribute(_SECURITY_ATTRIBUTES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_ATTRIBUTES *,_SECURITY_ATTRIBUTES *,0,std::nullptr_t>>(lpSecurityAttributes);
  std::wstring::_Tidy_deallocate(lpName);
  std::wstring::_Tidy_deallocate(v27);
  return a2;
}

```

## disassembly

```asm
0x180015a70  mov     [rsp-8+arg_10], rbx
0x180015a75  mov     [rsp-8+arg_18], rsi
0x180015a7a  push    rbp
0x180015a7b  push    rdi
0x180015a7c  push    r12
0x180015a7e  push    r14
0x180015a80  push    r15
0x180015a82  lea     rbp, [rsp-37h]
0x180015a87  sub     rsp, 0D0h
0x180015a8e  mov     rax, cs:__security_cookie
0x180015a95  xor     rax, rsp
0x180015a98  mov     [rbp+57h+var_28], rax
0x180015a9c  mov     rdi, rdx
0x180015a9f  mov     rbx, rcx
0x180015aa2  mov     [rbp+57h+var_B0], rdx
0x180015aa6  lea     rsi, [rcx+8]
0x180015aaa  mov     rax, [rsi]
0x180015aad  test    rax, rax
0x180015ab0  jz      short loc_180015ABD
0x180015ab2  cmp     qword ptr [rax], 0
0x180015ab6  jz      short loc_180015ABD
0x180015ab8  call    ?Reset@ServerConnector@@AEAAXXZ; ServerConnector::Reset(void)
0x180015abd  mov     [rbp+57h+var_98], rbx
0x180015ac1  mov     [rbp+57h+var_90], 1
0x180015ac5  xor     r9d, r9d
0x180015ac8  xor     r8d, r8d
0x180015acb  lea     edx, [r9+1]
0x180015acf  mov     rcx, rsi
0x180015ad2  call    ?create@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180015ad7  xorps   xmm0, xmm0
0x180015ada  lea     r15, [rbx+28h]
0x180015ade  movups  xmmword ptr [r15], xmm0
0x180015ae2  movups  xmmword ptr [r15+10h], xmm0
0x180015ae7  mov     rax, [rsi]
0x180015aea  test    rax, rax
0x180015aed  jz      short loc_180015AF4
0x180015aef  mov     rcx, [rax]
0x180015af2  jmp     short loc_180015AF6
0x180015af4  xor     ecx, ecx
0x180015af6  mov     [rbx+40h], rcx
0x180015afa  movups  [rbp+57h+var_58], xmm0
0x180015afe  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180015b06  movdqu  [rbp+57h+var_48], xmm1
0x180015b0b  xor     eax, eax
0x180015b0d  mov     word ptr [rbp+57h+var_58], ax
0x180015b11  lea     r14, [rbx+48h]
0x180015b15  mov     rax, [r14]
0x180015b18  movups  xmm0, xmmword ptr [rax+8]
0x180015b1c  movdqu  [rbp+57h+var_38], xmm0
0x180015b21  lea     r8, [rbp+57h+var_58]
0x180015b25  lea     rdx, [rbp+57h+var_38]
0x180015b29  lea     rcx, [rbp+57h+lpName]
0x180015b2d  call    _anonymous_namespace___GetUiaManagerPipeName
0x180015b32  nop
0x180015b33  mov     rdx, [r14]
0x180015b36  lea     rcx, [rbp+57h+var_A8]
0x180015b3a  call    ?GetSecurityAttributesFromCrossMachineService@BasicUtils@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_SECURITY_ATTRIBUTES@@P6AXPEAU1@@Z$1?DestroySecurityAttribute@BasicUtils@@CAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAVICrossMachineCommunicationServices@@@Z; BasicUtils::GetSecurityAttributesFromCrossMachineService(ICrossMachineCommunicationServices &)
0x180015b3f  nop
0x180015b40  lea     rax, [rbp+57h+lpName]
0x180015b44  cmp     [rbp+57h+var_60], 7
0x180015b49  cmova   rax, [rbp+57h+lpName]
0x180015b4e  mov     [rbp+57h+var_B0], rax
0x180015b52  lea     rcx, [rbp+57h+var_B0]
0x180015b56  call    ??$NamedPipeCreateServerPipe@PEBG@UiaManagerTraceLoggingProvider@@SAX$$QEAPEBG@Z; UiaManagerTraceLoggingProvider::NamedPipeCreateServerPipe<ushort const *>(ushort const * &&)
0x180015b5b  mov     rax, [rbp+57h+var_A8]
0x180015b5f  lea     rcx, [rbp+57h+lpName]
0x180015b63  cmp     [rbp+57h+var_60], 7
0x180015b68  cmova   rcx, [rbp+57h+lpName]; lpName
0x180015b6d  lea     r12, [rbx+18h]
0x180015b71  mov     [rsp+0F0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180015b76  mov     [rsp+0F0h+nDefaultTimeOut], 1388h; nDefaultTimeOut
0x180015b7e  mov     eax, 0FF8h
0x180015b83  mov     [rsp+0F0h+nInBufferSize], eax; nInBufferSize
0x180015b87  mov     [rsp+0F0h+nOutBufferSize], eax; nOutBufferSize
0x180015b8b  mov     edx, 40000003h; dwOpenMode
0x180015b90  mov     r9d, 1; nMaxInstances
0x180015b96  lea     r8d, [r9+5]; dwPipeMode
0x180015b9a  call    cs:__imp_CreateNamedPipeW
0x180015ba0  mov     rdx, rax
0x180015ba3  mov     rcx, r12
0x180015ba6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180015bab  mov     rax, [r12]
0x180015baf  inc     rax
0x180015bb2  test    rax, 0FFFFFFFFFFFFFFFEh
0x180015bb8  setz    al
0x180015bbb  mov     rcx, [rbp+5Fh]; this
0x180015bbf  test    al, al
0x180015bc1  jz      short loc_180015BD5
0x180015bc3  lea     r8, aOnecoreWindows_29; "onecore\\windows\\accessibletech\\uiama"...
0x180015bca  mov     edx, 2CCh; void *
0x180015bcf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180015bd5  mov     rdx, r14
0x180015bd8  lea     rcx, [rbp+57h+var_88]
0x180015bdc  call    ??0?$shared_ptr@UHwndAndViewIdConversionData@CoreUiSession@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<CoreUiSession::HwndAndViewIdConversionData>::shared_ptr<CoreUiSession::HwndAndViewIdConversionData>(std::shared_ptr<CoreUiSession::HwndAndViewIdConversionData> const &)
0x180015be1  mov     r14, rax
0x180015be4  mov     qword ptr [rbp+57h+var_38], rax
0x180015be8  mov     rcx, [rax]
0x180015beb  mov     rax, [rcx]
0x180015bee  xor     r9d, r9d
0x180015bf1  lea     r8, [rbp+57h+var_58]
0x180015bf5  lea     rdx, [rbp+57h+lpName]
0x180015bf9  mov     rax, [rax+8]
0x180015bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c02  cmp     eax, 1
0x180015c05  jnz     short loc_180015C0E
0x180015c07  cmp     qword ptr [rbx+20h], 0
0x180015c0c  jnz     short loc_180015C48
0x180015c0e  mov     r9, r14
0x180015c11  lea     r8, [rbp+57h+var_58]
0x180015c15  lea     rdx, [rbp+57h+lpName]
0x180015c19  lea     rcx, [rbp+57h+var_B0]
0x180015c1d  call    ??$make_unique@UCrossMachinePipeNameGuard@BasicUtils@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@AEAV?$shared_ptr@VICrossMachineCommunicationServices@@@4@$0A@@std@@YA?AV?$unique_ptr@UCrossMachinePipeNameGuard@BasicUtils@@U?$default_delete@UCrossMachinePipeNameGuard@BasicUtils@@@std@@@0@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0AEAV?$shared_ptr@VICrossMachineCommunicationServices@@@0@@Z; std::make_unique<BasicUtils::CrossMachinePipeNameGuard,std::wstring const &,std::wstring const &,std::shared_ptr<ICrossMachineCommunicationServices> &,0>(std::wstring const &,std::wstring const &,std::shared_ptr<ICrossMachineCommunicationServices> &)
0x180015c22  mov     rcx, [rax]
0x180015c25  mov     qword ptr [rax], 0
0x180015c2c  mov     rdx, [rbx+20h]
0x180015c30  mov     [rbx+20h], rcx
0x180015c34  test    rdx, rdx
0x180015c37  jz      short loc_180015C3E
0x180015c39  call    ??R?$default_delete@UCrossMachinePipeNameGuard@BasicUtils@@@std@@QEBAXPEAUCrossMachinePipeNameGuard@BasicUtils@@@Z; std::default_delete<BasicUtils::CrossMachinePipeNameGuard>::operator()(BasicUtils::CrossMachinePipeNameGuard *)
0x180015c3e  lea     rcx, [rbp+57h+var_B0]
0x180015c42  call    ??1?$unique_ptr@UCrossMachinePipeNameGuard@BasicUtils@@U?$default_delete@UCrossMachinePipeNameGuard@BasicUtils@@@std@@@std@@QEAA@XZ; std::unique_ptr<BasicUtils::CrossMachinePipeNameGuard>::~unique_ptr<BasicUtils::CrossMachinePipeNameGuard>(void)
0x180015c47  nop
0x180015c48  mov     rcx, [r14+8]; this
0x180015c4c  test    rcx, rcx
0x180015c4f  jz      short loc_180015C56
0x180015c51  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015c56  mov     rbx, [rbp+5Fh]
0x180015c5a  mov     rdx, r15; lpOverlapped
0x180015c5d  mov     rcx, [r12]; hNamedPipe
0x180015c61  call    cs:__imp_ConnectNamedPipe
0x180015c67  test    eax, eax
0x180015c69  jz      short loc_180015C80
0x180015c6b  lea     r8, aOnecoreWindows_29; "onecore\\windows\\accessibletech\\uiama"...
0x180015c72  mov     edx, 2D5h; void *
0x180015c77  mov     rcx, rbx; this
0x180015c7a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180015c80  call    cs:__imp_GetLastError
0x180015c86  cmp     eax, 217h
0x180015c8b  jz      short loc_180015CAA
0x180015c8d  cmp     eax, 3E5h
0x180015c92  jz      short loc_180015CB2
0x180015c94  mov     rcx, [rbp+5Fh]; this
0x180015c98  lea     r8, aOnecoreWindows_29; "onecore\\windows\\accessibletech\\uiama"...
0x180015c9f  mov     edx, 2E8h; void *
0x180015ca4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180015caa  mov     rcx, rsi
0x180015cad  call    ?SetEvent@?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBAXXZ
0x180015cb2  mov     qword ptr [rdi], 0
0x180015cb9  mov     qword ptr [rdi+8], 0
0x180015cc1  mov     rax, [rsi+8]
0x180015cc5  test    rax, rax
0x180015cc8  jz      short loc_180015CCE
0x180015cca  lock inc dword ptr [rax+8]
0x180015cce  mov     rcx, [rsi]
0x180015cd1  mov     [rdi], rcx
0x180015cd4  mov     rcx, [rsi+8]
0x180015cd8  mov     [rdi+8], rcx
0x180015cdc  lea     rcx, [rbp+57h+var_A8]
0x180015ce0  call    ??1?$unique_storage@U?$resource_policy@PEAU_SECURITY_ATTRIBUTES@@P6AXPEAU1@@Z$1?DestroySecurityAttribute@BasicUtils@@CAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SECURITY_ATTRIBUTES *,void (*)(_SECURITY_ATTRIBUTES *),&BasicUtils::DestroySecurityAttribute(_SECURITY_ATTRIBUTES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_ATTRIBUTES *,_SECURITY_ATTRIBUTES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_ATTRIBUTES *,void (*)(_SECURITY_ATTRIBUTES *),&BasicUtils::DestroySecurityAttribute(_SECURITY_ATTRIBUTES *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_ATTRIBUTES *,_SECURITY_ATTRIBUTES *,0,std::nullptr_t>>(void)
0x180015ce5  nop
0x180015ce6  lea     rcx, [rbp+57h+lpName]
0x180015cea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015cef  nop
0x180015cf0  lea     rcx, [rbp+57h+var_58]
0x180015cf4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015cf9  nop
0x180015cfa  mov     rax, rdi
0x180015cfd  mov     rcx, [rbp+57h+var_28]
0x180015d01  xor     rcx, rsp; StackCookie
0x180015d04  call    __security_check_cookie
0x180015d09  lea     r11, [rsp+0F0h+var_20]
0x180015d11  mov     rbx, [r11+40h]
0x180015d15  mov     rsi, [r11+48h]
0x180015d19  mov     rsp, r11
0x180015d1c  pop     r15
0x180015d1e  pop     r14
0x180015d20  pop     r12
0x180015d22  pop     rdi
0x180015d23  pop     rbp
0x180015d24  retn
```
