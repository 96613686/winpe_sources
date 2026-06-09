# _lambda_20d2c7ee46cffd5931666fc616fd88dd_::operator()(void)

- ea: `0x180186634`
- end: `0x180186b22`
- name: `??R_lambda_20d2c7ee46cffd5931666fc616fd88dd_@@QEAA?AV?$shared_ptr@VIAutopilotUpdateSearchResult@Autopilot@Windows@Microsoft@@@std@@XZ`
- size: `1262`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18018d840`

## callees

- `0x18000bd0c`
- `0x180067008`
- `0x18008013c`
- `0x1800841e8`
- `0x180093a28`
- `0x180181124`
- `0x18018564c`
- `0x180185d88`
- `0x180185ddc`
- `0x180185e00`
- `0x180186634`
- `0x1801882c8`
- `0x18018b128`
- `0x18018bf0c`
- `0x18018bf58`
- `0x18018ded0`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180186acd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180186acd`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18018667d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18018667d`

## string_xrefs

- `0x180186707`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotupdate.cpp`
- `0x180186b10`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotupdate.cpp`
- `0x1801867d5`: `Unable to get_Updates`
- `0x18018697b`: `Unable to get_UpdateID at %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
_QWORD *__fastcall _lambda_20d2c7ee46cffd5931666fc616fd88dd_::operator()(__int64 *a1, _QWORD *a2)
{
  Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Search *v4; // r12
  void **v5; // rcx
  void *v6; // rcx
  const char *v7; // r9
  __int64 v8; // rbx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64, __int64 *); // rbx
  unsigned int v11; // eax
  __int64 *v12; // r13
  unsigned int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64 *); // rbx
  unsigned int v16; // eax
  unsigned int v17; // eax
  signed int v18; // r13d
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64 **); // rbx
  unsigned int v21; // eax
  __int64 v22; // rax
  __int64 *v23; // rdi
  __int64 (__fastcall *v24)(__int64 *, __int64 **); // rbx
  unsigned int v25; // eax
  __int64 v26; // rax
  _QWORD *v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rcx
  const char *v30; // r9
  char *v32; // [rsp+28h] [rbp-B1h]
  char *v33; // [rsp+28h] [rbp-B1h]
  char *v34; // [rsp+28h] [rbp-B1h]
  char *v35; // [rsp+28h] [rbp-B1h]
  char *v36; // [rsp+28h] [rbp-B1h]
  char *v37; // [rsp+28h] [rbp-B1h]
  char *v38; // [rsp+28h] [rbp-B1h]
  char *v39; // [rsp+28h] [rbp-B1h]
  char *v40; // [rsp+30h] [rbp-A9h]
  _QWORD *v41; // [rsp+40h] [rbp-99h] BYREF
  __int64 *v42; // [rsp+48h] [rbp-91h] BYREF
  __int64 v43; // [rsp+50h] [rbp-89h] BYREF
  __int64 v44; // [rsp+58h] [rbp-81h] BYREF
  __int64 *v45; // [rsp+60h] [rbp-79h] BYREF
  __int64 v46; // [rsp+68h] [rbp-71h] BYREF
  __int64 *v47; // [rsp+70h] [rbp-69h] BYREF
  __int64 v48; // [rsp+78h] [rbp-61h] BYREF
  char v49; // [rsp+80h] [rbp-59h]
  _QWORD *v50; // [rsp+88h] [rbp-51h] BYREF
  __int64 v51; // [rsp+98h] [rbp-41h] BYREF
  __int64 v52; // [rsp+A0h] [rbp-39h] BYREF
  char v53; // [rsp+A8h] [rbp-31h]
  _BYTE v54[128]; // [rsp+B0h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]
  _DWORD *v56; // [rsp+140h] [rbp+67h]
  unsigned int v57; // [rsp+150h] [rbp+77h] BYREF
  char *v58; // [rsp+158h] [rbp+7Fh] BYREF

  v4 = (Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Search *)(a1 + 5);
  wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(
    (struct wil::details::IFailureCallback *)(a1 + 5),
    (struct wil::CallContextInfo *)v54);
  v5 = (void **)a1[47];
  if ( v5 )
    v6 = *v5;
  else
    v6 = 0;
  if ( !ImpersonateLoggedOnUser(v6) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x224,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
      v7);
  v8 = a1[2];
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(a1[2]);
  v52 = v8;
  v41 = 0;
  v53 = 1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  v44 = 0;
  v9 = a1[1];
  v10 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v9 + 128LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  v11 = v10(v9, a1[2], &v44);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x234,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
    (const char *)v11,
    (int)"EndSearch failed",
    v32);
  v12 = a1 + 3;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1[3] + 32LL))(a1[3]);
  LODWORD(v58) = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v44 + 56LL))(v44, &v58);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x23A,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
    (const char *)v13,
    (int)"get_ResultCode failed",
    v33);
  LODWORD(v40) = (_DWORD)v58;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x240,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
    (const char *)0x80004004LL,
    (unsigned int)((_DWORD)v58 - 2) > 1,
    (bool)"Search did not return a success code: %d",
    v40);
  v43 = 0;
  v14 = v44;
  v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v44 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  v16 = v15(v14, &v43);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x244,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
    (const char *)v16,
    (int)"Unable to get_Updates",
    v34);
  v57 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v43 + 80LL))(v43, &v57);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x248,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
    (const char *)v17,
    (int)"Unable to get_Count",
    v35);
  if ( (int)v57 > 0 )
  {
    v18 = 0;
    do
    {
      v42 = 0;
      v45 = 0;
      v19 = v43;
      v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v43 + 56LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      v21 = v20(v19, (unsigned int)v18, &v42);
      LODWORD(v36) = v18;
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x24F,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
        (const char *)v21,
        (int)"Unable to get_Item at %d",
        v36);
      v41 = 0;
      v22 = *v42;
      v47 = (__int64 *)&v41;
      v48 = 0;
      v49 = 1;
      LODWORD(v20) = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v22 + 56))(v42, &v48);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v47);
      LODWORD(v37) = v18;
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x253,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
        (const char *)(unsigned int)v20,
        (int)"Unable to get_Title at %d",
        v37);
      v23 = v42;
      v24 = *(__int64 (__fastcall **)(__int64 *, __int64 **))(*v42 + 152);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      v25 = v24(v23, &v45);
      LODWORD(v38) = v18;
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x256,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
        (const char *)v25,
        (int)"Unable to get_Identity at %d",
        v38);
      v46 = 0;
      v26 = *v45;
      v47 = &v46;
      v48 = 0;
      v49 = 1;
      LODWORD(v24) = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v26 + 64))(v45, &v48);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v47);
      LODWORD(v39) = v18;
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x25A,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
        (const char *)(unsigned int)v24,
        (int)"Unable to get_UpdateID at %d",
        v39);
      v51 = v46;
      v50 = v41;
      Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Search::AppendSearchResult<unsigned short *,unsigned short *>(
        v4,
        &v50,
        &v51);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v46);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      ++v18;
    }
    while ( v18 < (int)v57 );
    v12 = a1 + 3;
  }
  v27 = operator new(0x28u);
  v50 = v27;
  *v27 = &Microsoft::Windows::Autopilot::AutopilotUpdateSearchResult::`vftable';
  v28 = *a1;
  v27[1] = *a1;
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
  v29 = v43;
  v27[2] = v43;
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
  std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(
    v27 + 3,
    v12);
  *a2 = 0;
  a2[1] = 0;
  v41 = v27;
  v56 = operator new(0x18u);
  *(_OWORD *)v56 = 0;
  v56[2] = 1;
  v56[3] = 1;
  *(_QWORD *)v56 = &std::_Ref_count<Microsoft::Windows::Autopilot::AutopilotUpdatePayload>::`vftable';
  *((_QWORD *)v56 + 2) = v27;
  *a2 = v27;
  a2[1] = v56;
  v41 = 0;
  std::_Temporary_owner<Microsoft::Windows::Autopilot::AutopilotUpdatePayload>::~_Temporary_owner<Microsoft::Windows::Autopilot::AutopilotUpdatePayload>(&v41);
  Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Search::Stop(v4, (unsigned int)v58, v57);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  wil::details::ScopeExitFn<_lambda_9bd34d3b12309d70cad0cb1103cc422a_>::~ScopeExitFn<_lambda_9bd34d3b12309d70cad0cb1103cc422a_>(&v52);
  if ( !RevertToSelf() )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x227,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotupdate.cpp",
      v30);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v54);
  return a2;
}

```

## disassembly

```asm
0x180186634  mov     [rsp-8+arg_8], rbx
0x180186639  push    rbp
0x18018663a  push    rsi
0x18018663b  push    rdi
0x18018663c  push    r12
0x18018663e  push    r13
0x180186640  push    r14
0x180186642  push    r15
0x180186644  lea     rbp, [rsp-27h]
0x180186649  sub     rsp, 100h
0x180186650  mov     rsi, rdx
0x180186653  mov     r14, rcx
0x180186656  xor     edi, edi
0x180186658  lea     r12, [rcx+28h]
0x18018665c  lea     rdx, [rbp+57h+var_80]; struct wil::CallContextInfo *
0x180186660  mov     rcx, r12; struct wil::details::IFailureCallback *
0x180186663  call    ?ContinueOnCurrentThread@?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x180186668  nop
0x180186669  mov     rcx, [r14+178h]
0x180186670  test    rcx, rcx
0x180186673  jz      short loc_18018667A
0x180186675  mov     rcx, [rcx]
0x180186678  jmp     short loc_18018667D
0x18018667a  mov     rcx, rdi; hToken
0x18018667d  call    cs:__imp_ImpersonateLoggedOnUser
0x180186683  mov     rcx, [rbp+5Fh]; this
0x180186687  test    eax, eax
0x180186689  jz      loc_180186B10
0x18018668f  mov     [rbp+57h+arg_1], 1
0x180186693  mov     rbx, [r14+10h]
0x180186697  test    rbx, rbx
0x18018669a  jz      short loc_1801866AC
0x18018669c  mov     rax, [rbx]
0x18018669f  mov     rcx, rbx
0x1801866a2  mov     rax, [rax+8]
0x1801866a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801866ab  nop
0x1801866ac  mov     [rbp+57h+var_90], rbx
0x1801866b0  mov     [rsp+130h+var_F0], rdi
0x1801866b5  mov     [rbp+57h+var_88], 1
0x1801866b9  lea     rcx, [rsp+130h+var_F0]
0x1801866be  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801866c3  mov     [rsp+130h+var_D8], rdi
0x1801866c8  mov     rdi, [r14+8]
0x1801866cc  mov     rax, [rdi]
0x1801866cf  mov     rbx, [rax+80h]
0x1801866d6  lea     rcx, [rsp+130h+var_D8]
0x1801866db  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801866e0  lea     r8, [rsp+130h+var_D8]
0x1801866e5  mov     rdx, [r14+10h]
0x1801866e9  mov     rcx, rdi
0x1801866ec  mov     rax, rbx
0x1801866ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801866f4  mov     rcx, [rbp+5Fh]; this
0x1801866f8  lea     rdx, aEndsearchFaile; "EndSearch failed"
0x1801866ff  mov     qword ptr [rsp+130h+var_110], rdx; int
0x180186704  mov     r9d, eax; char *
0x180186707  lea     r15, aOnecoreuapAdmi_110; "onecoreuap\\admin\\moderndeployment\\au"...
0x18018670e  mov     r8, r15; unsigned int
0x180186711  mov     edx, 234h; void *
0x180186716  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018671b  lea     r13, [r14+18h]
0x18018671f  mov     rcx, [r13+0]
0x180186723  mov     rax, [rcx]
0x180186726  mov     rax, [rax+20h]
0x18018672a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018672f  mov     dword ptr [rbp+57h+arg_18], 0
0x180186736  mov     rcx, [rsp+130h+var_D8]
0x18018673b  mov     rax, [rcx]
0x18018673e  lea     rdx, [rbp+57h+arg_18]
0x180186742  mov     rax, [rax+38h]
0x180186746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018674b  mov     rcx, [rbp+5Fh]; this
0x18018674f  lea     rdx, aGetResultcodeF; "get_ResultCode failed"
0x180186756  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18018675b  mov     r9d, eax; char *
0x18018675e  mov     r8, r15; unsigned int
0x180186761  mov     edx, 23Ah; void *
0x180186766  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018676b  mov     edx, dword ptr [rbp+57h+arg_18]
0x18018676e  lea     eax, [rdx-2]
0x180186771  cmp     eax, 1
0x180186774  setnbe  al
0x180186777  mov     rcx, [rbp+5Fh]; this
0x18018677b  mov     dword ptr [rsp+130h+var_100], edx; char *
0x18018677f  lea     rdx, aSearchDidNotRe; "Search did not return a success code: %"...
0x180186786  mov     [rsp+130h+var_108], rdx; char *
0x18018678b  mov     [rsp+130h+var_110], al; char
0x18018678f  mov     r9d, 80004004h; char *
0x180186795  mov     r8, r15; unsigned int
0x180186798  mov     edx, 240h; void *
0x18018679d  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801867a2  mov     [rsp+130h+var_E0], 0
0x1801867ab  mov     rdi, [rsp+130h+var_D8]
0x1801867b0  mov     rax, [rdi]
0x1801867b3  mov     rbx, [rax+48h]
0x1801867b7  lea     rcx, [rsp+130h+var_E0]
0x1801867bc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801867c1  lea     rdx, [rsp+130h+var_E0]
0x1801867c6  mov     rcx, rdi
0x1801867c9  mov     rax, rbx
0x1801867cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801867d1  mov     rcx, [rbp+5Fh]; this
0x1801867d5  lea     rdx, aUnableToGetUpd; "Unable to get_Updates"
0x1801867dc  mov     qword ptr [rsp+130h+var_110], rdx; int
0x1801867e1  mov     r9d, eax; char *
0x1801867e4  mov     r8, r15; unsigned int
0x1801867e7  mov     edx, 244h; void *
0x1801867ec  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1801867f1  xor     edi, edi
0x1801867f3  mov     [rbp+57h+arg_10], edi
0x1801867f6  mov     rcx, [rsp+130h+var_E0]
0x1801867fb  mov     rax, [rcx]
0x1801867fe  lea     rdx, [rbp+57h+arg_10]
0x180186802  mov     rax, [rax+50h]
0x180186806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018680b  mov     rcx, [rbp+5Fh]; this
0x18018680f  lea     rdx, aUnableToGetCou; "Unable to get_Count"
0x180186816  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18018681b  mov     r9d, eax; char *
0x18018681e  mov     r8, r15; unsigned int
0x180186821  mov     edx, 248h; void *
0x180186826  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018682b  cmp     [rbp+57h+arg_10], edi
0x18018682e  jle     loc_1801869F3
0x180186834  mov     r13d, edi
0x180186837  mov     [rsp+130h+var_E8], rdi
0x18018683c  mov     [rbp+57h+var_D0], rdi
0x180186840  mov     rdi, [rsp+130h+var_E0]
0x180186845  mov     rax, [rdi]
0x180186848  mov     rbx, [rax+38h]
0x18018684c  lea     rcx, [rsp+130h+var_E8]
0x180186851  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180186856  lea     r8, [rsp+130h+var_E8]
0x18018685b  mov     edx, r13d
0x18018685e  mov     rcx, rdi
0x180186861  mov     rax, rbx
0x180186864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180186869  mov     rcx, [rbp+5Fh]; this
0x18018686d  mov     dword ptr [rsp+130h+var_108], r13d; char *
0x180186872  lea     rdx, aUnableToGetIte; "Unable to get_Item at %d"
0x180186879  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18018687e  mov     r9d, eax; char *
0x180186881  mov     r8, r15; unsigned int
0x180186884  mov     edx, 24Fh; void *
0x180186889  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018688e  mov     [rsp+130h+var_F0], 0
0x180186897  mov     rcx, [rsp+130h+var_E8]
0x18018689c  mov     rax, [rcx]
0x18018689f  lea     rdx, [rsp+130h+var_F0]
0x1801868a4  mov     [rbp+57h+var_C0], rdx
0x1801868a8  mov     [rbp+57h+var_B8], 0
0x1801868b0  mov     [rbp+57h+var_B0], 1
0x1801868b4  lea     rdx, [rbp+57h+var_B8]
0x1801868b8  mov     rax, [rax+38h]
0x1801868bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801868c1  mov     ebx, eax
0x1801868c3  lea     rcx, [rbp+57h+var_C0]
0x1801868c7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1801868cc  mov     rcx, [rbp+5Fh]; this
0x1801868d0  mov     dword ptr [rsp+130h+var_108], r13d; char *
0x1801868d5  lea     rax, aUnableToGetTit; "Unable to get_Title at %d"
0x1801868dc  mov     qword ptr [rsp+130h+var_110], rax; int
0x1801868e1  mov     r9d, ebx; char *
0x1801868e4  mov     r8, r15; unsigned int
0x1801868e7  mov     edx, 253h; void *
0x1801868ec  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1801868f1  mov     rdi, [rsp+130h+var_E8]
0x1801868f6  mov     rax, [rdi]
0x1801868f9  mov     rbx, [rax+98h]
0x180186900  lea     rcx, [rbp+57h+var_D0]
0x180186904  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180186909  lea     rdx, [rbp+57h+var_D0]
0x18018690d  mov     rcx, rdi
0x180186910  mov     rax, rbx
0x180186913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180186918  mov     rcx, [rbp+5Fh]; this
0x18018691c  mov     dword ptr [rsp+130h+var_108], r13d; char *
0x180186921  lea     rdx, aUnableToGetIde; "Unable to get_Identity at %d"
0x180186928  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18018692d  mov     r9d, eax; char *
0x180186930  mov     r8, r15; unsigned int
0x180186933  mov     edx, 256h; void *
0x180186938  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018693d  xor     edi, edi
0x18018693f  mov     [rbp+57h+var_C8], rdi
0x180186943  mov     rcx, [rbp+57h+var_D0]
0x180186947  mov     rax, [rcx]
0x18018694a  lea     rdx, [rbp+57h+var_C8]
0x18018694e  mov     [rbp+57h+var_C0], rdx
0x180186952  mov     [rbp+57h+var_B8], rdi
0x180186956  mov     [rbp+57h+var_B0], 1
0x18018695a  lea     rdx, [rbp+57h+var_B8]
0x18018695e  mov     rax, [rax+40h]
0x180186962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180186967  mov     ebx, eax
0x180186969  lea     rcx, [rbp+57h+var_C0]
0x18018696d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180186972  mov     rcx, [rbp+5Fh]; this
0x180186976  mov     dword ptr [rsp+130h+var_108], r13d; char *
0x18018697b  lea     rax, aUnableToGetUpd_0; "Unable to get_UpdateID at %d"
0x180186982  mov     qword ptr [rsp+130h+var_110], rax; int
0x180186987  mov     r9d, ebx; char *
0x18018698a  mov     r8, r15; unsigned int
0x18018698d  mov     edx, 25Ah; void *
0x180186992  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180186997  mov     rax, [rbp+57h+var_C8]
0x18018699b  mov     [rbp+57h+var_98], rax
0x18018699f  mov     rax, [rsp+130h+var_F0]
0x1801869a4  mov     [rbp+57h+var_A8], rax
0x1801869a8  lea     r8, [rbp+57h+var_98]
0x1801869ac  lea     rdx, [rbp+57h+var_A8]
0x1801869b0  mov     rcx, r12
0x1801869b3  call    ??$AppendSearchResult@PEAGPEAG@Search@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAAX$$QEAPEAG0@Z; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Search::AppendSearchResult<ushort *,ushort *>(ushort * &&,ushort * &&)
0x1801869b8  nop
0x1801869b9  lea     rcx, [rbp+57h+var_C8]
0x1801869bd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801869c2  nop
0x1801869c3  lea     rcx, [rsp+130h+var_F0]
0x1801869c8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801869cd  nop
0x1801869ce  lea     rcx, [rbp+57h+var_D0]
0x1801869d2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801869d7  nop
0x1801869d8  lea     rcx, [rsp+130h+var_E8]
0x1801869dd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801869e2  inc     r13d
0x1801869e5  cmp     r13d, [rbp+57h+arg_10]
0x1801869e9  jl      loc_180186837
0x1801869ef  lea     r13, [r14+18h]
0x1801869f3  mov     ecx, 28h ; '('; Size
0x1801869f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801869fd  mov     rbx, rax
0x180186a00  mov     [rbp+57h+var_A8], rax
0x180186a04  lea     rax, ??_7AutopilotUpdateSearchResult@Autopilot@Windows@Microsoft@@6B@; const Microsoft::Windows::Autopilot::AutopilotUpdateSearchResult::`vftable'
0x180186a0b  mov     [rbx], rax
0x180186a0e  mov     rcx, [r14]
0x180186a11  mov     [rbx+8], rcx
0x180186a15  test    rcx, rcx
0x180186a18  jz      short loc_180186A27
0x180186a1a  mov     rdx, [rcx]
0x180186a1d  mov     rax, [rdx+8]
0x180186a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180186a26  nop
0x180186a27  mov     rcx, [rsp+130h+var_E0]
0x180186a2c  mov     [rbx+10h], rcx
0x180186a30  test    rcx, rcx
0x180186a33  jz      short loc_180186A42
0x180186a35  mov     rax, [rcx]
0x180186a38  mov     rax, [rax+8]
0x180186a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180186a41  nop
0x180186a42  lea     rcx, [rbx+18h]
0x180186a46  mov     rdx, r13
0x180186a49  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x180186a4e  mov     [rsi], rdi
0x180186a51  mov     [rsi+8], rdi
0x180186a55  mov     [rsp+130h+var_F0], rbx
0x180186a5a  mov     ecx, 18h; Size
0x180186a5f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180186a64  mov     [rbp+67h], rax
0x180186a68  xorps   xmm0, xmm0
0x180186a6b  movups  xmmword ptr [rax], xmm0
0x180186a6e  mov     ecx, 1
0x180186a73  mov     [rax+8], ecx
0x180186a76  mov     [rax+0Ch], ecx
0x180186a79  lea     rcx, ??_7?$_Ref_count@VAutopilotUpdatePayload@Autopilot@Windows@Microsoft@@@std@@6B@; const std::_Ref_count<Microsoft::Windows::Autopilot::AutopilotUpdatePayload>::`vftable'
0x180186a80  mov     [rax], rcx
0x180186a83  mov     [rax+10h], rbx
0x180186a87  mov     [rsi], rbx
0x180186a8a  mov     [rsi+8], rax
0x180186a8e  mov     [rsp+130h+var_F0], rdi
0x180186a93  lea     rcx, [rsp+130h+var_F0]
0x180186a98  call    ??1?$_Temporary_owner@VAutopilotUpdatePayload@Autopilot@Windows@Microsoft@@@std@@QEAA@XZ; std::_Temporary_owner<Microsoft::Windows::Autopilot::AutopilotUpdatePayload>::~_Temporary_owner<Microsoft::Windows::Autopilot::AutopilotUpdatePayload>(void)
0x180186a9d  mov     r8d, [rbp+57h+arg_10]; unsigned int
0x180186aa1  mov     edx, dword ptr [rbp+57h+arg_18]; unsigned int
0x180186aa4  mov     rcx, r12; this
0x180186aa7  call    ?Stop@Search@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAAXKK@Z; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Search::Stop(ulong,ulong)
0x180186aac  nop
0x180186aad  lea     rcx, [rsp+130h+var_E0]
0x180186ab2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180186ab7  nop
0x180186ab8  lea     rcx, [rsp+130h+var_D8]
0x180186abd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180186ac2  nop
0x180186ac3  lea     rcx, [rbp+57h+var_90]
0x180186ac7  call    ??1?$ScopeExitFn@V_lambda_9bd34d3b12309d70cad0cb1103cc422a_@@@details@wil@@QEAA@XZ; wil::details::ScopeExitFn<_lambda_9bd34d3b12309d70cad0cb1103cc422a_>::~ScopeExitFn<_lambda_9bd34d3b12309d70cad0cb1103cc422a_>(void)
0x180186acc  nop
0x180186acd  call    cs:__imp_RevertToSelf
0x180186ad3  mov     rcx, [rbp+5Fh]; this
0x180186ad7  test    eax, eax
0x180186ad9  jnz     short loc_180186AE9
0x180186adb  mov     r8, r15; unsigned int
0x180186ade  mov     edx, 227h; void *
0x180186ae3  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180186ae8  nop
0x180186ae9  lea     rcx, [rbp+57h+var_80]; this
0x180186aed  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180186af2  mov     rax, rsi
0x180186af5  mov     rbx, [rsp+130h+arg_8]
  ... truncated ...
```
