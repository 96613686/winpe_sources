# wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(void)

- ea: `0x180010b6c`
- end: `0x180010cdc`
- name: `??0?$svchost_module@UAggregatedDataPlatform@1Internal@Windows@winrt@@@details@wil@@QEAA@XZ`
- size: `368`
- prototype: `LPVOID *__fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001195c`

## callees

- `0x180002250`
- `0x180003add`
- `0x180010348`
- `0x180010b6c`
- `0x180011c3c`
- `0x180011e9c`
- `0x1800ca010`

## string_xrefs

- `0x180010c57`: `onecore\internal\sdk\inc\wil\cppwinrtservice.h`

## pseudocode

```c
LPVOID *__fastcall wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(
        LPVOID *a1)
{
  HRESULT v2; // eax
  LPVOID v3; // rdi
  int v4; // eax
  LPVOID ppv; // [rsp+40h] [rbp+7h] BYREF
  LPVOID v7; // [rsp+48h] [rbp+Fh] BYREF
  int v8; // [rsp+50h] [rbp+17h] BYREF
  const char *v9; // [rsp+58h] [rbp+1Fh]
  __int64 v10; // [rsp+60h] [rbp+27h]
  LPVOID *v11; // [rsp+68h] [rbp+2Fh]
  IID rclsid; // [rsp+70h] [rbp+37h] BYREF

  v11 = a1;
  *a1 = 0;
  a1[1] = 0;
  *((_DWORD *)a1 + 4) = 0;
  __builtin_array_init_helper_eh<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned long,long (*)(unsigned long),&long CoRevokeClassObject(unsigned long),wistd::integral_constant<unsigned __int64,0>,unsigned long,unsigned long,0,std::nullptr_t>>>>();
  rclsid = CLSID_ContextSwitcher;
  ppv = 0;
  v8 = 2729;
  v9 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\base.h";
  v10 = 0;
  v2 = CoCreateInstance_0(&rclsid, 0, 1u, &winrt::impl::guid_v<IContextCallback>, &ppv);
  if ( v2 < 0 )
    winrt::throw_hresult((unsigned int)v2, &v8);
  v3 = ppv;
  v7 = ppv;
  if ( a1 == &v7 )
  {
    if ( ppv )
      winrt::com_ptr<IContextCallback>::unconditional_release_ref(&v7);
  }
  else
  {
    if ( *a1 )
      winrt::com_ptr<IContextCallback>::unconditional_release_ref(a1);
    *a1 = v3;
  }
  ppv = a1;
  *(_QWORD *)&rclsid.Data1 = 0;
  *(_QWORD *)rclsid.Data4 = &ppv;
  v8 = 192;
  v9 = "onecore\\internal\\sdk\\inc\\wil\\cppwinrtservice.h";
  v10 = 0;
  v4 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(), IID *, GUID *, int, _QWORD))(*(_QWORD *)*a1 + 24LL))(
         *a1,
         __lambda_invoker_cdecl___lambda_1___1____RunInContext_V_lambda_1___1___0__svchost_module_UAggregatedDataPlatform_1Internal_Windows_winrt___details_wil__QEAA_XZ____svchost_module_UAggregatedDataPlatform_1Internal_Windows_winrt___details_wil__AEAAX__QEAV1_1___0234_QEAA_XZ__Z_SAJPEAUtagComCallData___Z,
         &rclsid,
         &IID_IContextCallback,
         5,
         0);
  if ( v4 < 0 )
    winrt::throw_hresult((unsigned int)v4, &v8);
  return a1;
}

```

## disassembly

```asm
0x180010b6c  mov     [rsp-8+arg_8], rbx
0x180010b71  mov     [rsp-8+arg_10], rdi
0x180010b76  push    rbp
0x180010b77  lea     rbp, [rsp-57h]
0x180010b7c  sub     rsp, 90h
0x180010b83  mov     rax, cs:__security_cookie
0x180010b8a  xor     rax, rsp
0x180010b8d  mov     [rbp+57h+var_10], rax
0x180010b91  mov     rbx, rcx
0x180010b94  mov     [rbp+57h+var_28], rcx
0x180010b98  mov     qword ptr [rcx], 0
0x180010b9f  mov     qword ptr [rcx+8], 0
0x180010ba7  add     rcx, 10h
0x180010bab  xor     eax, eax
0x180010bad  mov     [rcx], eax
0x180010baf  call    ??$__builtin_array_init_helper_eh@V?$unique_any_t@V?$unique_storage@U?$resource_policy@KP6AJK@Z$1?CoRevokeClassObject@@YAJK@ZU?$integral_constant@_K$0A@@wistd@@KK$0A@$$T@details@wil@@@details@wil@@@wil@@@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@KP6AJK@Z$1?CoRevokeClassObject@@YAJK@ZU?$integral_constant@_K$0A@@wistd@@KK$0A@$$T@details@wil@@@details@wil@@@wil@@_KP6AXPEAX@Z@Z; __builtin_array_init_helper_eh<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ulong,long (*)(ulong),&CoRevokeClassObject(ulong),wistd::integral_constant<unsigned __int64,0>,ulong,ulong,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ulong,long (*)(ulong),&CoRevokeClassObject(ulong),wistd::integral_constant<unsigned __int64,0>,ulong,ulong,0,std::nullptr_t>>> *,unsigned __int64,void (*)(void *))
0x180010bb4  nop
0x180010bb5  movups  xmm0, xmmword ptr cs:CLSID_ContextSwitcher.Data1
0x180010bbc  movdqu  xmmword ptr [rbp+57h+rclsid.Data1], xmm0
0x180010bc1  mov     [rbp+57h+var_50], 0
0x180010bc9  mov     [rbp+57h+var_40], 0AA9h
0x180010bd0  lea     rax, aOnecoreuapInte_4; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180010bd7  mov     [rbp+57h+var_38], rax
0x180010bdb  mov     [rbp+57h+var_30], 0
0x180010be3  lea     rax, [rbp+57h+var_50]
0x180010be7  mov     [rsp+90h+ppv], rax; ppv
0x180010bec  lea     r9, ??$guid_v@UIContextCallback@@@impl@winrt@@3Uguid@2@B; riid
0x180010bf3  xor     edx, edx; pUnkOuter
0x180010bf5  lea     r8d, [rdx+1]; dwClsContext
0x180010bf9  lea     rcx, [rbp+57h+rclsid]; rclsid
0x180010bfd  call    CoCreateInstance_0
0x180010c02  test    eax, eax
0x180010c04  js      loc_180010CD0
0x180010c0a  mov     rdi, [rbp+57h+var_50]
0x180010c0e  mov     [rbp+57h+var_48], rdi
0x180010c12  lea     rax, [rbp+57h+var_48]
0x180010c16  cmp     rbx, rax
0x180010c19  jz      short loc_180010C2E
0x180010c1b  cmp     qword ptr [rbx], 0
0x180010c1f  jz      short loc_180010C29
0x180010c21  mov     rcx, rbx
0x180010c24  call    ?unconditional_release_ref@?$com_ptr@UIContextCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IContextCallback>::unconditional_release_ref(void)
0x180010c29  mov     [rbx], rdi
0x180010c2c  jmp     short loc_180010C3C
0x180010c2e  test    rdi, rdi
0x180010c31  jz      short loc_180010C3C
0x180010c33  lea     rcx, [rbp+57h+var_48]
0x180010c37  call    ?unconditional_release_ref@?$com_ptr@UIContextCallback@@@winrt@@AEAAXXZ; winrt::com_ptr<IContextCallback>::unconditional_release_ref(void)
0x180010c3c  mov     [rbp+57h+var_50], rbx
0x180010c40  mov     qword ptr [rbp+57h+rclsid.Data1], 0
0x180010c48  lea     rax, [rbp+57h+var_50]
0x180010c4c  mov     qword ptr [rbp+57h+rclsid.Data4], rax
0x180010c50  mov     [rbp+57h+var_40], 0C0h
0x180010c57  lea     rax, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\cppwi"...
0x180010c5e  mov     [rbp+57h+var_38], rax
0x180010c62  mov     [rbp+57h+var_30], 0
0x180010c6a  mov     rcx, [rbx]
0x180010c6d  mov     rax, [rcx]
0x180010c70  mov     [rsp+90h+var_68], 0
0x180010c79  mov     dword ptr [rsp+90h+ppv], 5
0x180010c81  lea     r9, IID_IContextCallback
0x180010c88  lea     r8, [rbp+57h+rclsid]
0x180010c8c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RunInContext@V_lambda_1_@?1???0?$svchost_module@UAggregatedDataPlatform@1Internal@Windows@winrt@@@details@wil@@QEAA@XZ@@?$svchost_module@UAggregatedDataPlatform@1Internal@Windows@winrt@@@details@wil@@AEAAX$$QEAV1?1???0234@QEAA@XZ@@Z@SAJPEAUtagComCallData@@@Z; `wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::RunInContext<`wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(void)'::`2'::_lambda_1_>(`wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(void)'::`2'::_lambda_1_ &&)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(tagComCallData *)
0x180010c93  mov     rax, [rax+18h]
0x180010c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c9c  test    eax, eax
0x180010c9e  js      short loc_180010CC4
0x180010ca0  mov     rax, rbx
0x180010ca3  mov     rcx, [rbp+57h+var_10]
0x180010ca7  xor     rcx, rsp; StackCookie
0x180010caa  call    __security_check_cookie
0x180010caf  lea     r11, [rsp+90h+var_s0]
0x180010cb7  mov     rbx, [r11+18h]
0x180010cbb  mov     rdi, [r11+20h]
0x180010cbf  mov     rsp, r11
0x180010cc2  pop     rbp
0x180010cc3  retn
0x180010cc4  lea     rdx, [rbp+57h+var_40]
0x180010cc8  mov     ecx, eax
0x180010cca  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180010cd0  lea     rdx, [rbp+57h+var_40]
0x180010cd4  mov     ecx, eax
0x180010cd6  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
