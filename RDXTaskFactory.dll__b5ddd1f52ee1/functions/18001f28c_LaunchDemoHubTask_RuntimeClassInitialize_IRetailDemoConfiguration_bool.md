# LaunchDemoHubTask::RuntimeClassInitialize(IRetailDemoConfiguration *,bool)

- ea: `0x18001f28c`
- end: `0x18001f5bb`
- name: `?RuntimeClassInitialize@LaunchDemoHubTask@@QEAAJPEAUIRetailDemoConfiguration@@_N@Z`
- size: `815`
- prototype: `__int64 __fastcall(LaunchDemoHubTask *__hidden this, struct IRetailDemoConfiguration *, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001da34`

## callees

- `0x180008bbc`
- `0x18000e374`
- `0x18000fde4`
- `0x18001094c`
- `0x18001e19c`
- `0x18001e55c`
- `0x18001ee54`
- `0x18001f28c`
- `0x180030dc0`
- `0x180050010`

## string_xrefs

- `0x18001f2e6`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001f32e`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001f376`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001f3bb`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001f3fe`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001f44f`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001f486`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001f4d0`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001f511`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001f56c`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall LaunchDemoHubTask::RuntimeClassInitialize(
        LaunchDemoHubTask *this,
        struct IRetailDemoConfiguration *a2,
        char a3)
{
  __int64 (__fastcall *v6)(struct IRetailDemoConfiguration *, GUID *, __int64 *); // rbx
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 **); // rbx
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rdx
  int v24; // eax
  int v25; // eax
  _QWORD *RetailDemoAppsController; // rax
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 v38; // r8
  int v40; // [rsp+20h] [rbp-40h]
  __int64 v41; // [rsp+30h] [rbp-30h] BYREF
  __int64 v42; // [rsp+38h] [rbp-28h] BYREF
  _BYTE v43[8]; // [rsp+40h] [rbp-20h] BYREF
  char *v44; // [rsp+48h] [rbp-18h] BYREF
  __int64 v45; // [rsp+50h] [rbp-10h] BYREF
  char v46; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  unsigned int v48; // [rsp+98h] [rbp+38h] BYREF
  __int64 *v49; // [rsp+A8h] [rbp+48h] BYREF

  TaskBase<void,0,0,12>::InitializeWithConfiguration(this, a2);
  v42 = 0;
  v6 = *(__int64 (__fastcall **)(struct IRetailDemoConfiguration *, GUID *, __int64 *))(*(_QWORD *)a2 + 40LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42, v7, v8);
  v9 = v6(a2, &GUID_4f8fdb86_b106_4a8e_8ad8_4299278d7b26, &v42);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
      (const char *)(unsigned int)v9,
      v40);
  v41 = 0;
  v12 = v42;
  v13 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41, v10, v11);
  v14 = v13(v12, &v41);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
      (const char *)(unsigned int)v14,
      v40);
  v49 = 0;
  v17 = v41;
  v18 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v41 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49, v15, v16);
  v19 = v18(v17, &v49);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
      (const char *)(unsigned int)v19,
      v40);
  v20 = *v49;
  v44 = (char *)this + 88;
  v45 = 0;
  v46 = 1;
  v21 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v20 + 48))(v49, &v45);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
      (const char *)(unsigned int)v21,
      v40);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v44);
  v22 = (*(__int64 (__fastcall **)(__int64 *, char *))(*v49 + 176))(v49, (char *)this + 128);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
      (const char *)(unsigned int)v22,
      v40);
  v44 = (char *)this + 96;
  v45 = 0;
  v46 = 1;
  if ( (*((_BYTE *)this + 128) & 2) != 0 )
  {
    v24 = _AllocStringWorker<CTCoAllocPolicy>(retaddr, v23, L"Hub");
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA2,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
        (const char *)(unsigned int)v24,
        v40);
  }
  else
  {
    v25 = _AllocStringWorker<CTCoAllocPolicy>(retaddr, v23, &qword_180057BE0);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA6,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
        (const char *)(unsigned int)v25,
        v40);
  }
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v44);
  RetailDemoAppsController = (_QWORD *)LaunchAppAsUserTaskBase::GetRetailDemoAppsController(this, v43);
  v27 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, char *))(*(_QWORD *)*RetailDemoAppsController + 48LL))(
          *RetailDemoAppsController,
          v49,
          (char *)this + 112);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA9,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
      (const char *)(unsigned int)v27,
      v40);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v43, v28, v29);
  v48 = 0;
  v30 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v49 + 96))(v49, &v48);
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
      (const char *)(unsigned int)v30,
      v40);
  *((_DWORD *)this + 26) = RetailDemoUtil::GetLaunchOptionFromPrelaunchOptions(v48, 2);
  *((_BYTE *)this + 132) = a3;
  v31 = *(_QWORD *)a2;
  v44 = (char *)this + 48;
  v45 = 0;
  v46 = 1;
  v32 = (*(__int64 (__fastcall **)(struct IRetailDemoConfiguration *, __int64 *))(v31 + 24))(a2, &v45);
  if ( v32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB0,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
      (const char *)(unsigned int)v32,
      v40);
  __1__out_param_t_V__shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__QEAA_XZ(&v44);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49, v33, v34);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41, v35, v36);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42, v37, v38);
  return 0;
}

```

## disassembly

```asm
0x18001f28c  mov     [rsp-28h+arg_0], rbx
0x18001f291  push    rbp
0x18001f292  push    rsi
0x18001f293  push    rdi
0x18001f294  push    r14
0x18001f296  push    r15
0x18001f298  mov     rbp, rsp
0x18001f29b  sub     rsp, 60h
0x18001f29f  mov     r15b, r8b
0x18001f2a2  mov     r14, rdx
0x18001f2a5  mov     rsi, rcx
0x18001f2a8  call    ?InitializeWithConfiguration@?$TaskBase@X$0A@$0A@$0M@@@IEAAXPEAUIRetailDemoConfiguration@@@Z; TaskBase<void,0,0,12>::InitializeWithConfiguration(IRetailDemoConfiguration *)
0x18001f2ad  mov     [rbp+var_28], 0
0x18001f2b5  mov     rax, [r14]
0x18001f2b8  mov     rbx, [rax+28h]
0x18001f2bc  lea     rcx, [rbp+var_28]
0x18001f2c0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f2c5  lea     r8, [rbp+var_28]
0x18001f2c9  lea     rdx, _GUID_4f8fdb86_b106_4a8e_8ad8_4299278d7b26
0x18001f2d0  mov     rcx, r14
0x18001f2d3  mov     rax, rbx
0x18001f2d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2db  mov     rcx, [rbp+28h]; this
0x18001f2df  test    eax, eax
0x18001f2e1  jns     short loc_18001F2F8
0x18001f2e3  mov     r9d, eax; char *
0x18001f2e6  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f2ed  mov     edx, 98h; void *
0x18001f2f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f2f8  mov     [rbp+var_30], 0
0x18001f300  mov     rdi, [rbp+var_28]
0x18001f304  mov     rax, [rdi]
0x18001f307  mov     rbx, [rax+60h]
0x18001f30b  lea     rcx, [rbp+var_30]
0x18001f30f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f314  lea     rdx, [rbp+var_30]
0x18001f318  mov     rcx, rdi
0x18001f31b  mov     rax, rbx
0x18001f31e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f323  mov     rcx, [rbp+28h]; this
0x18001f327  test    eax, eax
0x18001f329  jns     short loc_18001F340
0x18001f32b  mov     r9d, eax; char *
0x18001f32e  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f335  mov     edx, 9Ah; void *
0x18001f33a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f340  mov     [rbp+arg_18], 0
0x18001f348  mov     rdi, [rbp+var_30]
0x18001f34c  mov     rax, [rdi]
0x18001f34f  mov     rbx, [rax+40h]
0x18001f353  lea     rcx, [rbp+arg_18]
0x18001f357  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f35c  lea     rdx, [rbp+arg_18]
0x18001f360  mov     rcx, rdi
0x18001f363  mov     rax, rbx
0x18001f366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f36b  mov     rcx, [rbp+28h]; this
0x18001f36f  test    eax, eax
0x18001f371  jns     short loc_18001F388
0x18001f373  mov     r9d, eax; char *
0x18001f376  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f37d  mov     edx, 9Ch; void *
0x18001f382  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f388  mov     rcx, [rbp+arg_18]
0x18001f38c  mov     rax, [rcx]
0x18001f38f  lea     rdx, [rsi+58h]
0x18001f393  mov     [rbp+var_18], rdx
0x18001f397  mov     [rbp+var_10], 0
0x18001f39f  mov     [rbp+var_8], 1
0x18001f3a3  lea     rdx, [rbp+var_10]
0x18001f3a7  mov     rax, [rax+30h]
0x18001f3ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3b0  mov     rcx, [rbp+28h]; this
0x18001f3b4  test    eax, eax
0x18001f3b6  jns     short loc_18001F3CD
0x18001f3b8  mov     r9d, eax; char *
0x18001f3bb  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f3c2  mov     edx, 9Dh; void *
0x18001f3c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f3cd  lea     rcx, [rbp+var_18]
0x18001f3d1  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18001f3d6  mov     rcx, [rbp+arg_18]
0x18001f3da  lea     rbx, [rsi+80h]
0x18001f3e1  mov     rax, [rcx]
0x18001f3e4  mov     rdx, rbx
0x18001f3e7  mov     rax, [rax+0B0h]
0x18001f3ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3f3  mov     rcx, [rbp+28h]; this
0x18001f3f7  test    eax, eax
0x18001f3f9  jns     short loc_18001F410
0x18001f3fb  mov     r9d, eax; char *
0x18001f3fe  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f405  mov     edx, 9Fh; void *
0x18001f40a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f410  lea     rax, [rsi+60h]
0x18001f414  mov     [rbp+var_18], rax
0x18001f418  mov     [rbp+var_10], 0
0x18001f420  mov     [rbp+var_8], 1
0x18001f424  test    byte ptr [rbx], 2
0x18001f427  jz      short loc_18001F463
0x18001f429  lea     rax, [rbp+var_10]
0x18001f42d  mov     [rsp+60h+var_38], rax
0x18001f432  mov     r9d, 3
0x18001f438  lea     r8, aHub; "Hub"
0x18001f43f  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18001f444  mov     rcx, [rbp+28h]; this
0x18001f448  test    eax, eax
0x18001f44a  jns     short loc_18001F461
0x18001f44c  mov     r9d, eax; char *
0x18001f44f  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f456  mov     edx, 0A2h; void *
0x18001f45b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f461  jmp     short loc_18001F498
0x18001f463  lea     rax, [rbp+var_10]
0x18001f467  mov     [rsp+60h+var_38], rax
0x18001f46c  xor     r9d, r9d
0x18001f46f  lea     r8, qword_180057BE0
0x18001f476  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18001f47b  mov     rcx, [rbp+28h]; this
0x18001f47f  test    eax, eax
0x18001f481  jns     short loc_18001F498
0x18001f483  mov     r9d, eax; char *
0x18001f486  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f48d  mov     edx, 0A6h; void *
0x18001f492  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f498  lea     rcx, [rbp+var_18]
0x18001f49c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18001f4a1  lea     rdx, [rbp+var_20]
0x18001f4a5  mov     rcx, rsi
0x18001f4a8  call    ?GetRetailDemoAppsController@LaunchAppAsUserTaskBase@@IEAA?AV?$ComPtr@UIRetailDemoAppsController@@@WRL@Microsoft@@XZ; LaunchAppAsUserTaskBase::GetRetailDemoAppsController(void)
0x18001f4ad  nop
0x18001f4ae  mov     rcx, [rax]
0x18001f4b1  mov     rax, [rcx]
0x18001f4b4  lea     r8, [rsi+70h]
0x18001f4b8  mov     rdx, [rbp+arg_18]
0x18001f4bc  mov     rax, [rax+30h]
0x18001f4c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4c5  mov     rcx, [rbp+28h]; this
0x18001f4c9  test    eax, eax
0x18001f4cb  jns     short loc_18001F4E2
0x18001f4cd  mov     r9d, eax; char *
0x18001f4d0  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f4d7  mov     edx, 0A9h; void *
0x18001f4dc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f4e2  lea     rcx, [rbp+var_20]
0x18001f4e6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f4eb  mov     [rbp+arg_8], 0
0x18001f4f2  mov     rcx, [rbp+arg_18]
0x18001f4f6  mov     rax, [rcx]
0x18001f4f9  lea     rdx, [rbp+arg_8]
0x18001f4fd  mov     rax, [rax+60h]
0x18001f501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f506  mov     rcx, [rbp+28h]; this
0x18001f50a  test    eax, eax
0x18001f50c  jns     short loc_18001F523
0x18001f50e  mov     r9d, eax; char *
0x18001f511  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f518  mov     edx, 0ACh; void *
0x18001f51d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f523  mov     edx, 2
0x18001f528  mov     ecx, [rbp+arg_8]
0x18001f52b  call    ?GetLaunchOptionFromPrelaunchOptions@RetailDemoUtil@@YA?AW4LaunchOptions@@W4RetailDemoPrelaunchOptions@@W42@@Z; RetailDemoUtil::GetLaunchOptionFromPrelaunchOptions(RetailDemoPrelaunchOptions,LaunchOptions)
0x18001f530  mov     [rsi+68h], eax
0x18001f533  mov     [rsi+84h], r15b
0x18001f53a  mov     rax, [r14]
0x18001f53d  lea     rcx, [rsi+30h]
0x18001f541  mov     [rbp+var_18], rcx
0x18001f545  mov     [rbp+var_10], 0
0x18001f54d  mov     [rbp+var_8], 1
0x18001f551  lea     rdx, [rbp+var_10]
0x18001f555  mov     rcx, r14
0x18001f558  mov     rax, [rax+18h]
0x18001f55c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f561  mov     rcx, [rbp+28h]; this
0x18001f565  test    eax, eax
0x18001f567  jns     short loc_18001F57E
0x18001f569  mov     r9d, eax; char *
0x18001f56c  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f573  mov     edx, 0B0h; void *
0x18001f578  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f57e  lea     rcx, [rbp+var_18]
0x18001f582  call    ??1?$out_param_t@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@QEAA@XZ
0x18001f587  nop
0x18001f588  lea     rcx, [rbp+arg_18]
0x18001f58c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f591  nop
0x18001f592  lea     rcx, [rbp+var_30]
0x18001f596  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f59b  nop
0x18001f59c  lea     rcx, [rbp+var_28]
0x18001f5a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f5a5  xor     eax, eax
0x18001f5a7  mov     rbx, [rsp+60h+arg_0]
0x18001f5af  add     rsp, 60h
0x18001f5b3  pop     r15
0x18001f5b5  pop     r14
0x18001f5b7  pop     rdi
0x18001f5b8  pop     rsi
0x18001f5b9  pop     rbp
0x18001f5ba  retn
```
