# DirectLaunch::details::GetDirectLaunchService(void)

- ea: `0x1800436bc`
- end: `0x1800437d2`
- name: `?GetDirectLaunchService@details@DirectLaunch@@YA?AUIDirectLaunchService@2Shell@Internal@Windows@winrt@@XZ`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004c13c`

## callees

- `0x180002b20`
- `0x1800046c8`
- `0x180017024`
- `0x180021bc4`
- `0x180037be4`
- `0x1800436bc`
- `0x18005a010`

## string_xrefs

- `0x18004372c`: `OnecoreUAP\Internal\Shell\Inc\SrcPkg\DirectLaunch\inc\DirectLaunchCommon.h`
- `0x180043795`: `OnecoreUAP\Internal\Shell\Inc\SrcPkg\DirectLaunch\inc\DirectLaunchCommon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
winrt *__fastcall DirectLaunch::details::GetDirectLaunchService(winrt *a1, struct IUnknown *a2)
{
  __int64 (__fastcall *v3)(__int64 *, void **); // rbx
  void **v4; // rax
  int v5; // eax
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, __int64 *, __int64 *, void **); // rbx
  struct IUnknown *v8; // rdx
  void **v9; // rax
  int v10; // eax
  int v12; // [rsp+20h] [rbp-38h]
  LPVOID v13; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  *(_QWORD *)a1 = 0;
  v3 = (__int64 (__fastcall *)(__int64 *, void **))DirectLaunch::g_directLaunchServiceRetrievalFn;
  if ( DirectLaunch::g_directLaunchServiceRetrievalFn )
  {
    v4 = winrt::put_abi(a1, a2);
    v5 = v3(winrt::impl::guid_v<winrt::Windows::Internal::Shell::DirectLaunch::IDirectLaunchService>, v4);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xB1,
        (unsigned int)"OnecoreUAP\\Internal\\Shell\\Inc\\SrcPkg\\DirectLaunch\\inc\\DirectLaunchCommon.h",
        (const char *)(unsigned int)v5,
        v12);
  }
  else
  {
    v13 = 0;
    wil::CoCreateInstance<IServiceProvider,wil::err_exception_policy>(&v13);
    v6 = v13;
    v7 = *(__int64 (__fastcall **)(LPVOID, __int64 *, __int64 *, void **))(*(_QWORD *)v13 + 24LL);
    v9 = winrt::put_abi(a1, v8);
    v10 = v7(
            v6,
            qword_180062F10,
            winrt::impl::guid_v<winrt::Windows::Internal::Shell::DirectLaunch::IDirectLaunchService>,
            v9);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"OnecoreUAP\\Internal\\Shell\\Inc\\SrcPkg\\DirectLaunch\\inc\\DirectLaunchCommon.h",
        (const char *)(unsigned int)v10,
        v12);
    wil::com_ptr_t<IServiceProvider,wil::err_exception_policy>::~com_ptr_t<IServiceProvider,wil::err_exception_policy>(&v13);
  }
  return a1;
}

```

## disassembly

```asm
0x1800436bc  mov     [rsp+arg_8], rbx
0x1800436c1  mov     [rsp+arg_10], rsi
0x1800436c6  push    rdi
0x1800436c7  sub     rsp, 50h
0x1800436cb  mov     rax, cs:__security_cookie
0x1800436d2  xor     rax, rsp
0x1800436d5  mov     [rsp+58h+var_10], rax
0x1800436da  mov     rsi, rcx
0x1800436dd  mov     [rsp+58h+var_20], rcx
0x1800436e2  mov     [rsp+58h+var_28], 0
0x1800436ea  mov     qword ptr [rcx], 0
0x1800436f1  mov     [rsp+58h+var_28], 1
0x1800436f9  mov     rbx, cs:?g_directLaunchServiceRetrievalFn@DirectLaunch@@3P6AJAEBU_GUID@@PEAPEAX@_EEA
0x180043700  test    rbx, rbx
0x180043703  jz      short loc_18004373E
0x180043705  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18004370a  mov     rdx, rax
0x18004370d  lea     rcx, ??$guid_v@UIDirectLaunchService@DirectLaunch@Shell@Internal@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Internal::Shell::DirectLaunch::IDirectLaunchService>
0x180043714  mov     rax, rbx
0x180043717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004371c  test    eax, eax
0x18004371e  jns     loc_1800437B1
0x180043724  mov     rcx, [rsp+58h]; this
0x180043729  mov     r9d, eax; char *
0x18004372c  lea     r8, aOnecoreuapInte; "OnecoreUAP\\Internal\\Shell\\Inc\\SrcPk"...
0x180043733  mov     edx, 0B1h; void *
0x180043738  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004373e  mov     [rsp+58h+var_18], 0
0x180043747  lea     rcx, [rsp+58h+var_18]
0x18004374c  call    ??$CoCreateInstance@UIServiceProvider@@Uerr_exception_policy@wil@@@wil@@YA?AV?$com_ptr_t@UIServiceProvider@@Uerr_exception_policy@wil@@@0@AEBU_GUID@@K@Z; wil::CoCreateInstance<IServiceProvider,wil::err_exception_policy>(_GUID const &,ulong)
0x180043751  mov     [rsp+58h+var_28], 3
0x180043759  mov     rdi, [rsp+58h+var_18]
0x18004375e  mov     rax, [rdi]
0x180043761  mov     rbx, [rax+18h]
0x180043765  mov     rcx, rsi; this
0x180043768  call    ?put_abi@winrt@@YAPEAPEAXAEAUIUnknown@Foundation@Windows@1@@Z; winrt::put_abi(winrt::Windows::Foundation::IUnknown &)
0x18004376d  mov     r9, rax
0x180043770  lea     r8, ??$guid_v@UIDirectLaunchService@DirectLaunch@Shell@Internal@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Internal::Shell::DirectLaunch::IDirectLaunchService>
0x180043777  lea     rdx, qword_180062F10
0x18004377e  mov     rcx, rdi
0x180043781  mov     rax, rbx
0x180043784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043789  test    eax, eax
0x18004378b  jns     short loc_1800437A7
0x18004378d  mov     rcx, [rsp+58h]; this
0x180043792  mov     r9d, eax; char *
0x180043795  lea     r8, aOnecoreuapInte; "OnecoreUAP\\Internal\\Shell\\Inc\\SrcPk"...
0x18004379c  mov     edx, 0B9h; void *
0x1800437a1  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800437a7  lea     rcx, [rsp+58h+var_18]
0x1800437ac  call    ??1?$com_ptr_t@UIServiceProvider@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IServiceProvider,wil::err_exception_policy>::~com_ptr_t<IServiceProvider,wil::err_exception_policy>(void)
0x1800437b1  mov     rax, rsi
0x1800437b4  mov     rcx, [rsp+58h+var_10]
0x1800437b9  xor     rcx, rsp; StackCookie
0x1800437bc  call    __security_check_cookie
0x1800437c1  mov     rbx, [rsp+58h+arg_8]
0x1800437c6  mov     rsi, [rsp+58h+arg_10]
0x1800437cb  add     rsp, 50h
0x1800437cf  pop     rdi
0x1800437d0  retn
```
