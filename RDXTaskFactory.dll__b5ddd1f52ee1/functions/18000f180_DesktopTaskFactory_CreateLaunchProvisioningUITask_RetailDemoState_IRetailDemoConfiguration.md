# DesktopTaskFactory::CreateLaunchProvisioningUITask(RetailDemoState,IRetailDemoConfiguration *)

- ea: `0x18000f180`
- end: `0x18000f338`
- name: `?CreateLaunchProvisioningUITask@DesktopTaskFactory@@SA?AV?$ComPtr@UIRetailDemoTask@@@WRL@Microsoft@@W4RetailDemoState@@PEAUIRetailDemoConfiguration@@@Z`
- size: `440`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000e330`
- `0x18000e3bc`
- `0x18000f180`
- `0x18001094c`
- `0x180010a60`
- `0x18001dbc4`
- `0x18001f014`
- `0x180050010`

## string_xrefs

- `0x18000f1c8`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskfactory.cpp`
- `0x18000f209`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskfactory.cpp`
- `0x18000f24a`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskfactory.cpp`
- `0x18000f294`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\desktoptaskfactory.cpp`
- `0x18000f2ad`: `ServiceLaunch`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall DesktopTaskFactory::CreateLaunchProvisioningUITask(
        _QWORD *a1,
        __int64 a2,
        struct IRetailDemoConfiguration *a3)
{
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, const unsigned __int16 **); // rbx
  int v13; // eax
  _QWORD *v14; // rax
  int v16; // [rsp+20h] [rbp-50h]
  __int64 v17; // [rsp+38h] [rbp-38h] BYREF
  __int64 *v18; // [rsp+40h] [rbp-30h] BYREF
  __int64 *v19; // [rsp+48h] [rbp-28h] BYREF
  const unsigned __int16 *v20; // [rsp+50h] [rbp-20h] BYREF
  const unsigned __int16 *v21; // [rsp+58h] [rbp-18h] BYREF
  struct IRetailDemoConfiguration *v22; // [rsp+60h] [rbp-10h] BYREF
  __int64 v23; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  unsigned int v25; // [rsp+A0h] [rbp+30h] BYREF
  const unsigned __int16 *v26; // [rsp+A8h] [rbp+38h] BYREF

  v5 = *(_QWORD *)a3;
  v19 = 0;
  v6 = (*(__int64 (__fastcall **)(struct IRetailDemoConfiguration *, GUID *, __int64 **))(v5 + 40))(
         a3,
         &GUID_4f8fdb86_b106_4a8e_8ad8_4299278d7b26,
         &v19);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10E,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskfactory.cpp",
      (const char *)(unsigned int)v6,
      v16);
  v18 = 0;
  v7 = *v19;
  v18 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v7 + 96))(v19, &v18);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x110,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskfactory.cpp",
      (const char *)(unsigned int)v8,
      v16);
  v17 = 0;
  v9 = *v18;
  v17 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v9 + 80))(v18, &v17);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x112,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskfactory.cpp",
      (const char *)(unsigned int)v10,
      v16);
  v26 = 0;
  v11 = v17;
  v12 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 **))(*(_QWORD *)v17 + 48LL);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    (void **)&v26,
    0);
  v13 = v12(v11, &v26);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x114,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\desktoptaskfactory.cpp",
      (const char *)(unsigned int)v13,
      v16);
  v25 = 0;
  v20 = L"ServiceLaunch";
  v21 = v26;
  v22 = a3;
  v14 = wil::MakeAndInitializeOrThrow<LaunchAppAsUserTask,IRetailDemoConfiguration * &,unsigned short const * &,unsigned short const * &,unsigned long &>(
          &v23,
          &v22,
          &v21,
          &v20,
          &v25);
  *a1 = *v14;
  *v14 = 0;
  Microsoft::WRL::ComPtr<LaunchIdleAppTask>::InternalRelease(&v23);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v26);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v17);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v18);
  wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v19);
  return a1;
}

```

## disassembly

```asm
0x18000f180  mov     [rsp-18h+arg_0], rbx
0x18000f185  mov     [rsp-18h+arg_8], rsi
0x18000f18a  push    rbp
0x18000f18b  push    rdi
0x18000f18c  push    r14
0x18000f18e  mov     rbp, rsp
0x18000f191  sub     rsp, 70h
0x18000f195  mov     rsi, r8
0x18000f198  mov     r14, rcx
0x18000f19b  mov     rax, [r8]
0x18000f19e  mov     [rbp+var_28], 0
0x18000f1a6  lea     r8, [rbp+var_28]
0x18000f1aa  lea     rdx, _GUID_4f8fdb86_b106_4a8e_8ad8_4299278d7b26
0x18000f1b1  mov     rcx, rsi
0x18000f1b4  mov     rax, [rax+28h]
0x18000f1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1bd  mov     rcx, [rbp+18h]; this
0x18000f1c1  test    eax, eax
0x18000f1c3  jns     short loc_18000F1DA
0x18000f1c5  mov     r9d, eax; char *
0x18000f1c8  lea     r8, aPcshellShellRe_8; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18000f1cf  mov     edx, 10Eh; void *
0x18000f1d4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f1da  mov     [rbp+var_30], 0
0x18000f1e2  mov     rcx, [rbp+var_28]
0x18000f1e6  mov     rax, [rcx]
0x18000f1e9  mov     [rbp+var_30], 0
0x18000f1f1  lea     rdx, [rbp+var_30]
0x18000f1f5  mov     rax, [rax+60h]
0x18000f1f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1fe  mov     rcx, [rbp+18h]; this
0x18000f202  test    eax, eax
0x18000f204  jns     short loc_18000F21B
0x18000f206  mov     r9d, eax; char *
0x18000f209  lea     r8, aPcshellShellRe_8; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18000f210  mov     edx, 110h; void *
0x18000f215  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f21b  mov     [rbp+var_38], 0
0x18000f223  mov     rcx, [rbp+var_30]
0x18000f227  mov     rax, [rcx]
0x18000f22a  mov     [rbp+var_38], 0
0x18000f232  lea     rdx, [rbp+var_38]
0x18000f236  mov     rax, [rax+50h]
0x18000f23a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f23f  mov     rcx, [rbp+18h]; this
0x18000f243  test    eax, eax
0x18000f245  jns     short loc_18000F25C
0x18000f247  mov     r9d, eax; char *
0x18000f24a  lea     r8, aPcshellShellRe_8; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18000f251  mov     edx, 112h; void *
0x18000f256  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f25c  mov     [rbp+arg_18], 0
0x18000f264  mov     rdi, [rbp+var_38]
0x18000f268  mov     rax, [rdi]
0x18000f26b  mov     rbx, [rax+30h]
0x18000f26f  xor     edx, edx
0x18000f271  lea     rcx, [rbp+arg_18]
0x18000f275  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18000f27a  lea     rdx, [rbp+arg_18]
0x18000f27e  mov     rcx, rdi
0x18000f281  mov     rax, rbx
0x18000f284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f289  mov     rcx, [rbp+18h]; this
0x18000f28d  test    eax, eax
0x18000f28f  jns     short loc_18000F2A6
0x18000f291  mov     r9d, eax; char *
0x18000f294  lea     r8, aPcshellShellRe_8; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18000f29b  mov     edx, 114h; void *
0x18000f2a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000f2a6  mov     [rbp+arg_10], 0
0x18000f2ad  lea     rax, aServicelaunch; "ServiceLaunch"
0x18000f2b4  mov     [rbp+var_20], rax
0x18000f2b8  mov     rax, [rbp+arg_18]
0x18000f2bc  mov     [rbp+var_18], rax
0x18000f2c0  mov     [rbp+var_10], rsi
0x18000f2c4  lea     rax, [rbp+arg_10]
0x18000f2c8  mov     qword ptr [rsp+70h+var_50], rax
0x18000f2cd  lea     r9, [rbp+var_20]
0x18000f2d1  lea     r8, [rbp+var_18]
0x18000f2d5  lea     rdx, [rbp+var_10]
0x18000f2d9  lea     rcx, [rbp+var_8]
0x18000f2dd  call    ??$MakeAndInitializeOrThrow@VLaunchAppAsUserTask@@AEAPEAUIRetailDemoConfiguration@@AEAPEBGAEAPEBGAEAK@wil@@YA?AV?$ComPtr@VLaunchAppAsUserTask@@@WRL@Microsoft@@AEAPEAUIRetailDemoConfiguration@@AEAPEBG1AEAK@Z; wil::MakeAndInitializeOrThrow<LaunchAppAsUserTask,IRetailDemoConfiguration * &,ushort const * &,ushort const * &,ulong &>(IRetailDemoConfiguration * &,ushort const * &,ushort const * &,ulong &)
0x18000f2e2  mov     rcx, [rax]
0x18000f2e5  mov     [r14], rcx
0x18000f2e8  mov     qword ptr [rax], 0
0x18000f2ef  lea     rcx, [rbp+var_8]
0x18000f2f3  call    ?InternalRelease@?$ComPtr@VLaunchIdleAppTask@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<LaunchIdleAppTask>::InternalRelease(void)
0x18000f2f8  nop
0x18000f2f9  lea     rcx, [rbp+arg_18]
0x18000f2fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000f302  nop
0x18000f303  lea     rcx, [rbp+var_38]
0x18000f307  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18000f30c  nop
0x18000f30d  lea     rcx, [rbp+var_30]
0x18000f311  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18000f316  nop
0x18000f317  lea     rcx, [rbp+var_28]
0x18000f31b  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18000f320  mov     rax, r14
0x18000f323  lea     r11, [rsp+70h+var_s0]
0x18000f328  mov     rbx, [r11+20h]
0x18000f32c  mov     rsi, [r11+28h]
0x18000f330  mov     rsp, r11
0x18000f333  pop     r14
0x18000f335  pop     rdi
0x18000f336  pop     rbp
0x18000f337  retn
```
