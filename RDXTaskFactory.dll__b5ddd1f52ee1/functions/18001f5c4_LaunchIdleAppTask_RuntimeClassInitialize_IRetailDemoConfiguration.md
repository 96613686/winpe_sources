# LaunchIdleAppTask::RuntimeClassInitialize(IRetailDemoConfiguration *)

- ea: `0x18001f5c4`
- end: `0x18001f8cb`
- name: `?RuntimeClassInitialize@LaunchIdleAppTask@@QEAAJPEAUIRetailDemoConfiguration@@@Z`
- size: `775`
- prototype: `__int64 __fastcall(LaunchIdleAppTask *__hidden this, struct IRetailDemoConfiguration *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001dafc`

## callees

- `0x180008bbc`
- `0x18000fde4`
- `0x18001094c`
- `0x18001e19c`
- `0x18001e55c`
- `0x18001ee54`
- `0x18001f5c4`
- `0x180050010`

## string_xrefs

- `0x18001f617`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001f65f`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001f6a7`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001f6ef`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001f732`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001f76a`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001f7d7`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001f80e`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`
- `0x18001f873`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\launchappasusertask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall LaunchIdleAppTask::RuntimeClassInitialize(
        LaunchIdleAppTask *this,
        struct IRetailDemoConfiguration *a2)
{
  __int64 (__fastcall *v4)(struct IRetailDemoConfiguration *, GUID *, __int64 *); // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64 **); // rbx
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdx
  unsigned int v23; // ecx
  __int64 v24; // rcx
  int v25; // eax
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  _QWORD *RetailDemoAppsController; // rax
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // r8
  int v38; // [rsp+20h] [rbp-40h]
  __int64 v39; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v40[8]; // [rsp+38h] [rbp-28h] BYREF
  char *v41; // [rsp+40h] [rbp-20h] BYREF
  __int64 v42; // [rsp+48h] [rbp-18h] BYREF
  char v43; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  unsigned int v45; // [rsp+88h] [rbp+28h] BYREF
  __int64 *v46; // [rsp+90h] [rbp+30h] BYREF
  __int64 v47; // [rsp+98h] [rbp+38h] BYREF

  TaskBase<void,0,0,12>::InitializeWithConfiguration(this, a2);
  v39 = 0;
  v4 = *(__int64 (__fastcall **)(struct IRetailDemoConfiguration *, GUID *, __int64 *))(*(_QWORD *)a2 + 40LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39, v5, v6);
  v7 = v4(a2, &GUID_4f8fdb86_b106_4a8e_8ad8_4299278d7b26, &v39);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
      (const char *)(unsigned int)v7,
      v38);
  v47 = 0;
  v10 = v39;
  v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47, v8, v9);
  v12 = v11(v10, &v47);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
      (const char *)(unsigned int)v12,
      v38);
  v46 = 0;
  v15 = v47;
  v16 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v47 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46, v13, v14);
  v17 = v16(v15, &v46);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
      (const char *)(unsigned int)v17,
      v38);
  v18 = *v46;
  v41 = (char *)this + 88;
  v42 = 0;
  v43 = 1;
  v19 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v18 + 48))(v46, &v42);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
      (const char *)(unsigned int)v19,
      v38);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v41);
  v20 = (*(__int64 (__fastcall **)(__int64 *, char *))(*v46 + 176))(v46, (char *)this + 128);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
      (const char *)(unsigned int)v20,
      v38);
  v45 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v46 + 56))(v46, &v45);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
      (const char *)(unsigned int)v21,
      v38);
  v23 = v45;
  *((_BYTE *)this + 144) = (v45 & 2) != 0;
  v24 = v23 >> 2;
  LOBYTE(v24) = v24 & 1;
  *((_BYTE *)this + 145) = v24;
  v41 = (char *)this + 96;
  v42 = 0;
  v43 = 1;
  if ( (*((_BYTE *)this + 128) & 1) != 0 )
  {
    v25 = _AllocStringWorker<CTCoAllocPolicy>(v24, v22, L"Idle");
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
        (const char *)(unsigned int)v25,
        v38);
  }
  else
  {
    v26 = _AllocStringWorker<CTCoAllocPolicy>(v24, v22, &qword_180057BE0);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
        (const char *)(unsigned int)v26,
        v38);
  }
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v41);
  if ( *((_BYTE *)this + 144) || *((_BYTE *)this + 145) )
  {
    RetailDemoAppsController = (_QWORD *)LaunchAppAsUserTaskBase::GetRetailDemoAppsController(this, v40);
    v30 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, char *))(*(_QWORD *)*RetailDemoAppsController + 48LL))(
            *RetailDemoAppsController,
            v46,
            (char *)this + 112);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x55,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\launchappasusertask.cpp",
        (const char *)(unsigned int)v30,
        v38);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v40, v31, v32);
  }
  else
  {
    *((_OWORD *)this + 7) = 0;
  }
  *((_DWORD *)this + 26) = 0;
  *((_BYTE *)this + 132) = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46, v27, v28);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47, v33, v34);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39, v35, v36);
  return 0;
}

```

## disassembly

```asm
0x18001f5c4  mov     [rsp-18h+arg_0], rbx
0x18001f5c9  push    rbp
0x18001f5ca  push    rsi
0x18001f5cb  push    rdi
0x18001f5cc  mov     rbp, rsp
0x18001f5cf  sub     rsp, 60h
0x18001f5d3  mov     rdi, rdx
0x18001f5d6  mov     rsi, rcx
0x18001f5d9  call    ?InitializeWithConfiguration@?$TaskBase@X$0A@$0A@$0M@@@IEAAXPEAUIRetailDemoConfiguration@@@Z; TaskBase<void,0,0,12>::InitializeWithConfiguration(IRetailDemoConfiguration *)
0x18001f5de  mov     [rbp+var_30], 0
0x18001f5e6  mov     rax, [rdi]
0x18001f5e9  mov     rbx, [rax+28h]
0x18001f5ed  lea     rcx, [rbp+var_30]
0x18001f5f1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f5f6  lea     r8, [rbp+var_30]
0x18001f5fa  lea     rdx, _GUID_4f8fdb86_b106_4a8e_8ad8_4299278d7b26
0x18001f601  mov     rcx, rdi
0x18001f604  mov     rax, rbx
0x18001f607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f60c  mov     rcx, [rbp+18h]; this
0x18001f610  test    eax, eax
0x18001f612  jns     short loc_18001F629
0x18001f614  mov     r9d, eax; char *
0x18001f617  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f61e  mov     edx, 3Ah ; ':'; void *
0x18001f623  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f629  mov     [rbp+arg_18], 0
0x18001f631  mov     rdi, [rbp+var_30]
0x18001f635  mov     rax, [rdi]
0x18001f638  mov     rbx, [rax+60h]
0x18001f63c  lea     rcx, [rbp+arg_18]
0x18001f640  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f645  lea     rdx, [rbp+arg_18]
0x18001f649  mov     rcx, rdi
0x18001f64c  mov     rax, rbx
0x18001f64f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f654  mov     rcx, [rbp+18h]; this
0x18001f658  test    eax, eax
0x18001f65a  jns     short loc_18001F671
0x18001f65c  mov     r9d, eax; char *
0x18001f65f  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f666  mov     edx, 3Ch ; '<'; void *
0x18001f66b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f671  mov     [rbp+arg_10], 0
0x18001f679  mov     rdi, [rbp+arg_18]
0x18001f67d  mov     rax, [rdi]
0x18001f680  mov     rbx, [rax+38h]
0x18001f684  lea     rcx, [rbp+arg_10]
0x18001f688  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f68d  lea     rdx, [rbp+arg_10]
0x18001f691  mov     rcx, rdi
0x18001f694  mov     rax, rbx
0x18001f697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f69c  mov     rcx, [rbp+18h]; this
0x18001f6a0  test    eax, eax
0x18001f6a2  jns     short loc_18001F6B9
0x18001f6a4  mov     r9d, eax; char *
0x18001f6a7  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f6ae  mov     edx, 3Eh ; '>'; void *
0x18001f6b3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f6b9  mov     rcx, [rbp+arg_10]
0x18001f6bd  mov     rax, [rcx]
0x18001f6c0  lea     rdx, [rsi+58h]
0x18001f6c4  mov     [rbp+var_20], rdx
0x18001f6c8  mov     [rbp+var_18], 0
0x18001f6d0  mov     dil, 1
0x18001f6d3  mov     [rbp+var_10], dil
0x18001f6d7  lea     rdx, [rbp+var_18]
0x18001f6db  mov     rax, [rax+30h]
0x18001f6df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6e4  mov     rcx, [rbp+18h]; this
0x18001f6e8  test    eax, eax
0x18001f6ea  jns     short loc_18001F701
0x18001f6ec  mov     r9d, eax; char *
0x18001f6ef  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f6f6  mov     edx, 3Fh ; '?'; void *
0x18001f6fb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f701  lea     rcx, [rbp+var_20]
0x18001f705  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18001f70a  mov     rcx, [rbp+arg_10]
0x18001f70e  lea     rbx, [rsi+80h]
0x18001f715  mov     rax, [rcx]
0x18001f718  mov     rdx, rbx
0x18001f71b  mov     rax, [rax+0B0h]
0x18001f722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f727  mov     rcx, [rbp+18h]; this
0x18001f72b  test    eax, eax
0x18001f72d  jns     short loc_18001F744
0x18001f72f  mov     r9d, eax; char *
0x18001f732  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f739  mov     edx, 40h ; '@'; void *
0x18001f73e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f744  mov     [rbp+arg_8], 0
0x18001f74b  mov     rcx, [rbp+arg_10]
0x18001f74f  mov     rax, [rcx]
0x18001f752  lea     rdx, [rbp+arg_8]
0x18001f756  mov     rax, [rax+38h]
0x18001f75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f75f  mov     rcx, [rbp+18h]; this
0x18001f763  test    eax, eax
0x18001f765  jns     short loc_18001F77C
0x18001f767  mov     r9d, eax; char *
0x18001f76a  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f771  mov     edx, 43h ; 'C'; void *
0x18001f776  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f77c  mov     ecx, [rbp+arg_8]
0x18001f77f  mov     eax, ecx
0x18001f781  shr     eax, 1
0x18001f783  and     al, dil
0x18001f786  mov     [rsi+90h], al
0x18001f78c  shr     ecx, 2
0x18001f78f  and     cl, dil
0x18001f792  mov     [rsi+91h], cl
0x18001f798  lea     rax, [rsi+60h]
0x18001f79c  mov     [rbp+var_20], rax
0x18001f7a0  mov     [rbp+var_18], 0
0x18001f7a8  mov     [rbp+var_10], dil
0x18001f7ac  test    [rbx], dil
0x18001f7af  jz      short loc_18001F7EB
0x18001f7b1  lea     rax, [rbp+var_18]
0x18001f7b5  mov     [rsp+60h+var_38], rax
0x18001f7ba  mov     r9d, 4
0x18001f7c0  lea     r8, aIdle; "Idle"
0x18001f7c7  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18001f7cc  mov     rcx, [rbp+18h]; this
0x18001f7d0  test    eax, eax
0x18001f7d2  jns     short loc_18001F7E9
0x18001f7d4  mov     r9d, eax; char *
0x18001f7d7  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f7de  mov     edx, 49h ; 'I'; void *
0x18001f7e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f7e9  jmp     short loc_18001F820
0x18001f7eb  lea     rax, [rbp+var_18]
0x18001f7ef  mov     [rsp+60h+var_38], rax
0x18001f7f4  xor     r9d, r9d
0x18001f7f7  lea     r8, qword_180057BE0
0x18001f7fe  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x18001f803  mov     rcx, [rbp+18h]; this
0x18001f807  test    eax, eax
0x18001f809  jns     short loc_18001F820
0x18001f80b  mov     r9d, eax; char *
0x18001f80e  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f815  mov     edx, 4Dh ; 'M'; void *
0x18001f81a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f820  lea     rcx, [rbp+var_20]
0x18001f824  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18001f829  cmp     byte ptr [rsi+90h], 0
0x18001f830  jnz     short loc_18001F844
0x18001f832  cmp     byte ptr [rsi+91h], 0
0x18001f839  jnz     short loc_18001F844
0x18001f83b  xorps   xmm0, xmm0
0x18001f83e  movups  xmmword ptr [rsi+70h], xmm0
0x18001f842  jmp     short loc_18001F88E
0x18001f844  lea     rdx, [rbp+var_28]
0x18001f848  mov     rcx, rsi
0x18001f84b  call    ?GetRetailDemoAppsController@LaunchAppAsUserTaskBase@@IEAA?AV?$ComPtr@UIRetailDemoAppsController@@@WRL@Microsoft@@XZ; LaunchAppAsUserTaskBase::GetRetailDemoAppsController(void)
0x18001f850  nop
0x18001f851  mov     rcx, [rax]
0x18001f854  mov     rax, [rcx]
0x18001f857  lea     r8, [rsi+70h]
0x18001f85b  mov     rdx, [rbp+arg_10]
0x18001f85f  mov     rax, [rax+30h]
0x18001f863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f868  mov     rcx, [rbp+18h]; this
0x18001f86c  test    eax, eax
0x18001f86e  jns     short loc_18001F885
0x18001f870  mov     r9d, eax; char *
0x18001f873  lea     r8, aPcshellShellRe_15; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18001f87a  mov     edx, 55h ; 'U'; void *
0x18001f87f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f885  lea     rcx, [rbp+var_28]
0x18001f889  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f88e  mov     dword ptr [rsi+68h], 0
0x18001f895  mov     byte ptr [rsi+84h], 0
0x18001f89c  lea     rcx, [rbp+arg_10]
0x18001f8a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f8a5  nop
0x18001f8a6  lea     rcx, [rbp+arg_18]
0x18001f8aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f8af  nop
0x18001f8b0  lea     rcx, [rbp+var_30]
0x18001f8b4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f8b9  xor     eax, eax
0x18001f8bb  mov     rbx, [rsp+60h+arg_0]
0x18001f8c3  add     rsp, 60h
0x18001f8c7  pop     rdi
0x18001f8c8  pop     rsi
0x18001f8c9  pop     rbp
0x18001f8ca  retn
```
