# _lambda_20d2c7ee46cffd5931666fc616fd88dd_::operator()(void)

- ea: `0x18018b1f4`
- end: `0x18018b6ef`
- name: `??R_lambda_20d2c7ee46cffd5931666fc616fd88dd_@@QEAA?AV?$shared_ptr@VIAutopilotUpdateSearchResult@Autopilot@Windows@Microsoft@@@std@@XZ`
- size: `1275`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180192680`

## callees

- `0x18000bddc`
- `0x180067398`
- `0x180080b4c`
- `0x180084d5c`
- `0x180094ce0`
- `0x180185c88`
- `0x18018a1c8`
- `0x18018a924`
- `0x18018a97c`
- `0x18018a9a0`
- `0x18018b1f4`
- `0x18018cf98`
- `0x18018fed8`
- `0x180190cd0`
- `0x180190d1c`
- `0x180192d90`
- `0x180200010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18018b693`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18018b693`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18018b23d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18018b23d`

## string_xrefs

- `0x18018b2cd`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotupdate.cpp`
- `0x18018b6dd`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotupdate.cpp`
- `0x18018b39b`: `Unable to get_Updates`
- `0x18018b541`: `Unable to get_UpdateID at %d`

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
0x18018b1f4  mov     [rsp-8+arg_8], rbx
0x18018b1f9  push    rbp
0x18018b1fa  push    rsi
0x18018b1fb  push    rdi
0x18018b1fc  push    r12
0x18018b1fe  push    r13
0x18018b200  push    r14
0x18018b202  push    r15
0x18018b204  lea     rbp, [rsp-27h]
0x18018b209  sub     rsp, 100h
0x18018b210  mov     rsi, rdx
0x18018b213  mov     r14, rcx
0x18018b216  xor     edi, edi
0x18018b218  lea     r12, [rcx+28h]
0x18018b21c  lea     rdx, [rbp+57h+var_80]; struct wil::CallContextInfo *
0x18018b220  mov     rcx, r12; struct wil::details::IFailureCallback *
0x18018b223  call    ?ContinueOnCurrentThread@?$ActivityBase@VAutopilotUpdateLoggingProvider@Logging@Autopilot@Management@Windows@Microsoft@@$00$0IAAAAAAAAAAA@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<Microsoft::Windows::Management::Autopilot::Logging::AutopilotUpdateLoggingProvider,1,140737488355328,4,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x18018b228  nop
0x18018b229  mov     rcx, [r14+178h]
0x18018b230  test    rcx, rcx
0x18018b233  jz      short loc_18018B23A
0x18018b235  mov     rcx, [rcx]
0x18018b238  jmp     short loc_18018B23D
0x18018b23a  mov     rcx, rdi; hToken
0x18018b23d  call    cs:__imp_ImpersonateLoggedOnUser
0x18018b244  nop     dword ptr [rax+rax+00h]
0x18018b249  mov     rcx, [rbp+5Fh]; this
0x18018b24d  test    eax, eax
0x18018b24f  jz      loc_18018B6DD
0x18018b255  mov     [rbp+57h+arg_1], 1
0x18018b259  mov     rbx, [r14+10h]
0x18018b25d  test    rbx, rbx
0x18018b260  jz      short loc_18018B272
0x18018b262  mov     rax, [rbx]
0x18018b265  mov     rcx, rbx
0x18018b268  mov     rax, [rax+8]
0x18018b26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b271  nop
0x18018b272  mov     [rbp+57h+var_90], rbx
0x18018b276  mov     [rsp+130h+var_F0], rdi
0x18018b27b  mov     [rbp+57h+var_88], 1
0x18018b27f  lea     rcx, [rsp+130h+var_F0]
0x18018b284  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018b289  mov     [rsp+130h+var_D8], rdi
0x18018b28e  mov     rdi, [r14+8]
0x18018b292  mov     rax, [rdi]
0x18018b295  mov     rbx, [rax+80h]
0x18018b29c  lea     rcx, [rsp+130h+var_D8]
0x18018b2a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018b2a6  lea     r8, [rsp+130h+var_D8]
0x18018b2ab  mov     rdx, [r14+10h]
0x18018b2af  mov     rcx, rdi
0x18018b2b2  mov     rax, rbx
0x18018b2b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b2ba  mov     rcx, [rbp+5Fh]; this
0x18018b2be  lea     rdx, aEndsearchFaile; "EndSearch failed"
0x18018b2c5  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18018b2ca  mov     r9d, eax; char *
0x18018b2cd  lea     r15, aOnecoreuapAdmi_110; "onecoreuap\\admin\\moderndeployment\\au"...
0x18018b2d4  mov     r8, r15; unsigned int
0x18018b2d7  mov     edx, 234h; void *
0x18018b2dc  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018b2e1  lea     r13, [r14+18h]
0x18018b2e5  mov     rcx, [r13+0]
0x18018b2e9  mov     rax, [rcx]
0x18018b2ec  mov     rax, [rax+20h]
0x18018b2f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b2f5  mov     dword ptr [rbp+57h+arg_18], 0
0x18018b2fc  mov     rcx, [rsp+130h+var_D8]
0x18018b301  mov     rax, [rcx]
0x18018b304  lea     rdx, [rbp+57h+arg_18]
0x18018b308  mov     rax, [rax+38h]
0x18018b30c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b311  mov     rcx, [rbp+5Fh]; this
0x18018b315  lea     rdx, aGetResultcodeF; "get_ResultCode failed"
0x18018b31c  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18018b321  mov     r9d, eax; char *
0x18018b324  mov     r8, r15; unsigned int
0x18018b327  mov     edx, 23Ah; void *
0x18018b32c  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018b331  mov     edx, dword ptr [rbp+57h+arg_18]
0x18018b334  lea     eax, [rdx-2]
0x18018b337  cmp     eax, 1
0x18018b33a  setnbe  al
0x18018b33d  mov     rcx, [rbp+5Fh]; this
0x18018b341  mov     dword ptr [rsp+130h+var_100], edx; char *
0x18018b345  lea     rdx, aSearchDidNotRe; "Search did not return a success code: %"...
0x18018b34c  mov     [rsp+130h+var_108], rdx; char *
0x18018b351  mov     [rsp+130h+var_110], al; char
0x18018b355  mov     r9d, 80004004h; char *
0x18018b35b  mov     r8, r15; unsigned int
0x18018b35e  mov     edx, 240h; void *
0x18018b363  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18018b368  mov     [rsp+130h+var_E0], 0
0x18018b371  mov     rdi, [rsp+130h+var_D8]
0x18018b376  mov     rax, [rdi]
0x18018b379  mov     rbx, [rax+48h]
0x18018b37d  lea     rcx, [rsp+130h+var_E0]
0x18018b382  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018b387  lea     rdx, [rsp+130h+var_E0]
0x18018b38c  mov     rcx, rdi
0x18018b38f  mov     rax, rbx
0x18018b392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b397  mov     rcx, [rbp+5Fh]; this
0x18018b39b  lea     rdx, aUnableToGetUpd; "Unable to get_Updates"
0x18018b3a2  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18018b3a7  mov     r9d, eax; char *
0x18018b3aa  mov     r8, r15; unsigned int
0x18018b3ad  mov     edx, 244h; void *
0x18018b3b2  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018b3b7  xor     edi, edi
0x18018b3b9  mov     [rbp+57h+arg_10], edi
0x18018b3bc  mov     rcx, [rsp+130h+var_E0]
0x18018b3c1  mov     rax, [rcx]
0x18018b3c4  lea     rdx, [rbp+57h+arg_10]
0x18018b3c8  mov     rax, [rax+50h]
0x18018b3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b3d1  mov     rcx, [rbp+5Fh]; this
0x18018b3d5  lea     rdx, aUnableToGetCou; "Unable to get_Count"
0x18018b3dc  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18018b3e1  mov     r9d, eax; char *
0x18018b3e4  mov     r8, r15; unsigned int
0x18018b3e7  mov     edx, 248h; void *
0x18018b3ec  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018b3f1  cmp     [rbp+57h+arg_10], edi
0x18018b3f4  jle     loc_18018B5B9
0x18018b3fa  mov     r13d, edi
0x18018b3fd  mov     [rsp+130h+var_E8], rdi
0x18018b402  mov     [rbp+57h+var_D0], rdi
0x18018b406  mov     rdi, [rsp+130h+var_E0]
0x18018b40b  mov     rax, [rdi]
0x18018b40e  mov     rbx, [rax+38h]
0x18018b412  lea     rcx, [rsp+130h+var_E8]
0x18018b417  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018b41c  lea     r8, [rsp+130h+var_E8]
0x18018b421  mov     edx, r13d
0x18018b424  mov     rcx, rdi
0x18018b427  mov     rax, rbx
0x18018b42a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b42f  mov     rcx, [rbp+5Fh]; this
0x18018b433  mov     dword ptr [rsp+130h+var_108], r13d; char *
0x18018b438  lea     rdx, aUnableToGetIte; "Unable to get_Item at %d"
0x18018b43f  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18018b444  mov     r9d, eax; char *
0x18018b447  mov     r8, r15; unsigned int
0x18018b44a  mov     edx, 24Fh; void *
0x18018b44f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018b454  mov     [rsp+130h+var_F0], 0
0x18018b45d  mov     rcx, [rsp+130h+var_E8]
0x18018b462  mov     rax, [rcx]
0x18018b465  lea     rdx, [rsp+130h+var_F0]
0x18018b46a  mov     [rbp+57h+var_C0], rdx
0x18018b46e  mov     [rbp+57h+var_B8], 0
0x18018b476  mov     [rbp+57h+var_B0], 1
0x18018b47a  lea     rdx, [rbp+57h+var_B8]
0x18018b47e  mov     rax, [rax+38h]
0x18018b482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b487  mov     ebx, eax
0x18018b489  lea     rcx, [rbp+57h+var_C0]
0x18018b48d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18018b492  mov     rcx, [rbp+5Fh]; this
0x18018b496  mov     dword ptr [rsp+130h+var_108], r13d; char *
0x18018b49b  lea     rax, aUnableToGetTit; "Unable to get_Title at %d"
0x18018b4a2  mov     qword ptr [rsp+130h+var_110], rax; int
0x18018b4a7  mov     r9d, ebx; char *
0x18018b4aa  mov     r8, r15; unsigned int
0x18018b4ad  mov     edx, 253h; void *
0x18018b4b2  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018b4b7  mov     rdi, [rsp+130h+var_E8]
0x18018b4bc  mov     rax, [rdi]
0x18018b4bf  mov     rbx, [rax+98h]
0x18018b4c6  lea     rcx, [rbp+57h+var_D0]
0x18018b4ca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018b4cf  lea     rdx, [rbp+57h+var_D0]
0x18018b4d3  mov     rcx, rdi
0x18018b4d6  mov     rax, rbx
0x18018b4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b4de  mov     rcx, [rbp+5Fh]; this
0x18018b4e2  mov     dword ptr [rsp+130h+var_108], r13d; char *
0x18018b4e7  lea     rdx, aUnableToGetIde; "Unable to get_Identity at %d"
0x18018b4ee  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18018b4f3  mov     r9d, eax; char *
0x18018b4f6  mov     r8, r15; unsigned int
0x18018b4f9  mov     edx, 256h; void *
0x18018b4fe  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018b503  xor     edi, edi
0x18018b505  mov     [rbp+57h+var_C8], rdi
0x18018b509  mov     rcx, [rbp+57h+var_D0]
0x18018b50d  mov     rax, [rcx]
0x18018b510  lea     rdx, [rbp+57h+var_C8]
0x18018b514  mov     [rbp+57h+var_C0], rdx
0x18018b518  mov     [rbp+57h+var_B8], rdi
0x18018b51c  mov     [rbp+57h+var_B0], 1
0x18018b520  lea     rdx, [rbp+57h+var_B8]
0x18018b524  mov     rax, [rax+40h]
0x18018b528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b52d  mov     ebx, eax
0x18018b52f  lea     rcx, [rbp+57h+var_C0]
0x18018b533  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18018b538  mov     rcx, [rbp+5Fh]; this
0x18018b53c  mov     dword ptr [rsp+130h+var_108], r13d; char *
0x18018b541  lea     rax, aUnableToGetUpd_0; "Unable to get_UpdateID at %d"
0x18018b548  mov     qword ptr [rsp+130h+var_110], rax; int
0x18018b54d  mov     r9d, ebx; char *
0x18018b550  mov     r8, r15; unsigned int
0x18018b553  mov     edx, 25Ah; void *
0x18018b558  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18018b55d  mov     rax, [rbp+57h+var_C8]
0x18018b561  mov     [rbp+57h+var_98], rax
0x18018b565  mov     rax, [rsp+130h+var_F0]
0x18018b56a  mov     [rbp+57h+var_A8], rax
0x18018b56e  lea     r8, [rbp+57h+var_98]
0x18018b572  lea     rdx, [rbp+57h+var_A8]
0x18018b576  mov     rcx, r12
0x18018b579  call    ??$AppendSearchResult@PEAGPEAG@Search@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAAX$$QEAPEAG0@Z; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Search::AppendSearchResult<ushort *,ushort *>(ushort * &&,ushort * &&)
0x18018b57e  nop
0x18018b57f  lea     rcx, [rbp+57h+var_C8]
0x18018b583  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18018b588  nop
0x18018b589  lea     rcx, [rsp+130h+var_F0]
0x18018b58e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18018b593  nop
0x18018b594  lea     rcx, [rbp+57h+var_D0]
0x18018b598  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018b59d  nop
0x18018b59e  lea     rcx, [rsp+130h+var_E8]
0x18018b5a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018b5a8  inc     r13d
0x18018b5ab  cmp     r13d, [rbp+57h+arg_10]
0x18018b5af  jl      loc_18018B3FD
0x18018b5b5  lea     r13, [r14+18h]
0x18018b5b9  mov     ecx, 28h ; '('; Size
0x18018b5be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18018b5c3  mov     rbx, rax
0x18018b5c6  mov     [rbp+57h+var_A8], rax
0x18018b5ca  lea     rax, ??_7AutopilotUpdateSearchResult@Autopilot@Windows@Microsoft@@6B@; const Microsoft::Windows::Autopilot::AutopilotUpdateSearchResult::`vftable'
0x18018b5d1  mov     [rbx], rax
0x18018b5d4  mov     rcx, [r14]
0x18018b5d7  mov     [rbx+8], rcx
0x18018b5db  test    rcx, rcx
0x18018b5de  jz      short loc_18018B5ED
0x18018b5e0  mov     rdx, [rcx]
0x18018b5e3  mov     rax, [rdx+8]
0x18018b5e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b5ec  nop
0x18018b5ed  mov     rcx, [rsp+130h+var_E0]
0x18018b5f2  mov     [rbx+10h], rcx
0x18018b5f6  test    rcx, rcx
0x18018b5f9  jz      short loc_18018B608
0x18018b5fb  mov     rax, [rcx]
0x18018b5fe  mov     rax, [rax+8]
0x18018b602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018b607  nop
0x18018b608  lea     rcx, [rbx+18h]
0x18018b60c  mov     rdx, r13
0x18018b60f  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x18018b614  mov     [rsi], rdi
0x18018b617  mov     [rsi+8], rdi
0x18018b61b  mov     [rsp+130h+var_F0], rbx
0x18018b620  mov     ecx, 18h; Size
0x18018b625  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18018b62a  mov     [rbp+67h], rax
0x18018b62e  xorps   xmm0, xmm0
0x18018b631  movups  xmmword ptr [rax], xmm0
0x18018b634  mov     ecx, 1
0x18018b639  mov     [rax+8], ecx
0x18018b63c  mov     [rax+0Ch], ecx
0x18018b63f  lea     rcx, ??_7?$_Ref_count@VAutopilotUpdatePayload@Autopilot@Windows@Microsoft@@@std@@6B@; const std::_Ref_count<Microsoft::Windows::Autopilot::AutopilotUpdatePayload>::`vftable'
0x18018b646  mov     [rax], rcx
0x18018b649  mov     [rax+10h], rbx
0x18018b64d  mov     [rsi], rbx
0x18018b650  mov     [rsi+8], rax
0x18018b654  mov     [rsp+130h+var_F0], rdi
0x18018b659  lea     rcx, [rsp+130h+var_F0]
0x18018b65e  call    ??1?$_Temporary_owner@VAutopilotUpdatePayload@Autopilot@Windows@Microsoft@@@std@@QEAA@XZ; std::_Temporary_owner<Microsoft::Windows::Autopilot::AutopilotUpdatePayload>::~_Temporary_owner<Microsoft::Windows::Autopilot::AutopilotUpdatePayload>(void)
0x18018b663  mov     r8d, [rbp+57h+arg_10]; unsigned int
0x18018b667  mov     edx, dword ptr [rbp+57h+arg_18]; unsigned int
0x18018b66a  mov     rcx, r12; this
0x18018b66d  call    ?Stop@Search@UpdateOperations@Logging@Autopilot@Management@Windows@Microsoft@@QEAAXKK@Z; Microsoft::Windows::Management::Autopilot::Logging::UpdateOperations::Search::Stop(ulong,ulong)
0x18018b672  nop
0x18018b673  lea     rcx, [rsp+130h+var_E0]
0x18018b678  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018b67d  nop
0x18018b67e  lea     rcx, [rsp+130h+var_D8]
0x18018b683  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18018b688  nop
0x18018b689  lea     rcx, [rbp+57h+var_90]
0x18018b68d  call    ??1?$ScopeExitFn@V_lambda_9bd34d3b12309d70cad0cb1103cc422a_@@@details@wil@@QEAA@XZ; wil::details::ScopeExitFn<_lambda_9bd34d3b12309d70cad0cb1103cc422a_>::~ScopeExitFn<_lambda_9bd34d3b12309d70cad0cb1103cc422a_>(void)
0x18018b692  nop
0x18018b693  call    cs:__imp_RevertToSelf
0x18018b69a  nop     dword ptr [rax+rax+00h]
0x18018b69f  mov     rcx, [rbp+5Fh]; this
0x18018b6a3  test    eax, eax
0x18018b6a5  jnz     short loc_18018B6B5
0x18018b6a7  mov     r8, r15; unsigned int
0x18018b6aa  mov     edx, 227h; void *
0x18018b6af  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18018b6b4  nop
0x18018b6b5  lea     rcx, [rbp+57h+var_80]; this
0x18018b6b9  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
  ... truncated ...
```
