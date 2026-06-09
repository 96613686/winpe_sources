# InitializeOneSettings(void)

- ea: `0x1800282c0`
- end: `0x180028325`
- name: `?InitializeOneSettings@@YAXXZ`
- size: `101`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180028470`

## callees

- `0x18001c180`
- `0x1800280ec`
- `0x180028128`
- `0x1800282c0`
- `0x180028858`

## import_xrefs

- `KERNEL32!SubmitThreadpoolWork` at `0x18002830f`
- `KERNEL32!SubmitThreadpoolWork` at `0x18002830f`
- `KERNEL32!CreateThreadpoolWork` at `0x1800282da`
- `KERNEL32!CreateThreadpoolWork` at `0x1800282da`

## string_xrefs

- `0x1800282fc`: `pcshell\shell\cloudrestorelauncher\dll\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void InitializeOneSettings(void)
{
  void (__stdcall *v0)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK); // rax
  PTP_WORK ThreadpoolWork; // rax
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PTP_WORK pwk; // [rsp+30h] [rbp+8h] BYREF

  pwk = 0;
  v0 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK))lambda_4ef018f4a72d779cf3ddabee401a578b_::operator_void____cdecl____TP_CALLBACK_INSTANCE___void____TP_WORK___();
  ThreadpoolWork = CreateThreadpoolWork(v0, 0, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
    &pwk,
    ThreadpoolWork);
  if ( !pwk )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x48,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\dll\\service.cpp",
      v2);
  SubmitThreadpoolWork(pwk);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(&pwk);
}

```

## disassembly

```asm
0x1800282c0  sub     rsp, 28h
0x1800282c4  mov     [rsp+28h+pwk], 0
0x1800282cd  call    _lambda_4ef018f4a72d779cf3ddabee401a578b___operator_void____cdecl____TP_CALLBACK_INSTANCE___void____TP_WORK___
0x1800282d2  mov     rcx, rax; pfnwk
0x1800282d5  xor     r8d, r8d; pcbe
0x1800282d8  xor     edx, edx; pv
0x1800282da  call    cs:__imp_CreateThreadpoolWork
0x1800282e0  mov     rdx, rax
0x1800282e3  lea     rcx, [rsp+28h+pwk]
0x1800282e8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x1800282ed  mov     rax, [rsp+28h]
0x1800282f2  mov     rcx, [rsp+28h+pwk]; pwk
0x1800282f7  test    rcx, rcx
0x1800282fa  jnz     short loc_18002830F
0x1800282fc  lea     r8, aPcshellShellCl_38; "pcshell\\shell\\cloudrestorelauncher\\d"...
0x180028303  lea     edx, [rcx+48h]; void *
0x180028306  mov     rcx, rax; this
0x180028309  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002830f  call    cs:__imp_SubmitThreadpoolWork
0x180028315  nop
0x180028316  lea     rcx, [rsp+28h+pwk]
0x18002831b  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x180028320  add     rsp, 28h
0x180028324  retn
```
