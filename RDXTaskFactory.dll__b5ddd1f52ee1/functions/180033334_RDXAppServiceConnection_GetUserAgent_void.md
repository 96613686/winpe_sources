# RDXAppServiceConnection::GetUserAgent(void)

- ea: `0x180033334`
- end: `0x180033477`
- name: `?GetUserAgent@RDXAppServiceConnection@@AEAA?AV?$com_ptr_t@UIRetailDemoUserComAgent@@Uerr_exception_policy@wil@@@wil@@XZ`
- size: `323`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800330f0`
- `0x180033500`

## callees

- `0x18000e330`
- `0x18000e3bc`
- `0x18001094c`
- `0x18001e55c`
- `0x180030538`
- `0x180033334`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800333af`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800333af`

## string_xrefs

- `0x1800333c0`: `shellcommon\shell\retaildemo\util\rdxappserviceconnection.cpp`
- `0x180033422`: `shellcommon\shell\retaildemo\util\rdxappserviceconnection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
unsigned __int16 **__fastcall RDXAppServiceConnection::GetUserAgent(__int64 a1, unsigned __int16 **a2)
{
  unsigned __int16 **v3; // rbx
  HRESULT v4; // eax
  LPVOID v5; // rsi
  __int64 (__fastcall *v6)(LPVOID, __int64, _QWORD, GUID *); // r14
  unsigned __int16 *v7; // rcx
  int v8; // eax
  unsigned __int16 *v9; // rcx
  int ppv; // [rsp+20h] [rbp-30h]
  __int64 *v12; // [rsp+38h] [rbp-18h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-10h] BYREF
  char v14; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  LPVOID v16; // [rsp+70h] [rbp+20h] BYREF
  __int64 v17; // [rsp+80h] [rbp+30h] BYREF

  v3 = (unsigned __int16 **)(a1 + 48);
  if ( !*(_QWORD *)(a1 + 48) )
  {
    v17 = 0;
    v12 = &v17;
    StringSid = 0;
    v14 = 1;
    RetailDemoUtil::GetDemoUserSidString(&StringSid, a2);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v12);
    v16 = 0;
    v4 = CoCreateInstance(
           &GUID_faf85f2e_a8e7_414d_a3e9_6b9e7b4a51ed,
           0,
           1u,
           &GUID_12614617_2e4b_4dd8_9fac_5c5183d3c95e,
           &v16);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2D,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\rdxappserviceconnection.cpp",
        (const char *)(unsigned int)v4,
        ppv);
    v5 = v16;
    v6 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, GUID *))(*(_QWORD *)v16 + 32LL);
    v7 = *v3;
    *v3 = 0;
    if ( v7 )
      (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v7 + 16LL))(v7);
    v8 = v6(v5, v17, 0, &GUID_9eb119d8_774f_4077_a531_1899af39f1ae);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"shellcommon\\shell\\retaildemo\\util\\rdxappserviceconnection.cpp",
        (const char *)(unsigned int)v8,
        (int)v3);
    wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(&v16);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
  }
  v9 = *v3;
  *a2 = *v3;
  if ( v9 )
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v9 + 8LL))(v9);
  return a2;
}

```

## disassembly

```asm
0x180033334  mov     [rsp-18h+arg_8], rbx
0x180033339  mov     [rsp-18h+arg_18], rsi
0x18003333e  push    rbp
0x18003333f  push    rdi
0x180033340  push    r14
0x180033342  mov     rbp, rsp
0x180033345  sub     rsp, 50h
0x180033349  mov     rdi, rdx
0x18003334c  lea     rbx, [rcx+30h]
0x180033350  cmp     qword ptr [rbx], 0
0x180033354  jnz     loc_180033447
0x18003335a  mov     [rbp+arg_10], 0
0x180033362  lea     rax, [rbp+arg_10]
0x180033366  mov     [rbp+var_18], rax
0x18003336a  mov     [rbp+StringSid], 0
0x180033372  mov     [rbp+var_8], 1
0x180033376  lea     rcx, [rbp+StringSid]; StringSid
0x18003337a  call    ?GetDemoUserSidString@RetailDemoUtil@@YAXPEAPEAG@Z; RetailDemoUtil::GetDemoUserSidString(ushort * *)
0x18003337f  nop
0x180033380  lea     rcx, [rbp+var_18]
0x180033384  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180033389  nop
0x18003338a  mov     [rbp+arg_0], 0
0x180033392  lea     rax, [rbp+arg_0]
0x180033396  mov     qword ptr [rsp+50h+ppv], rax; int
0x18003339b  lea     r9, _GUID_12614617_2e4b_4dd8_9fac_5c5183d3c95e; riid
0x1800333a2  xor     edx, edx; pUnkOuter
0x1800333a4  lea     r8d, [rdx+1]; dwClsContext
0x1800333a8  lea     rcx, _GUID_faf85f2e_a8e7_414d_a3e9_6b9e7b4a51ed; rclsid
0x1800333af  call    cs:__imp_CoCreateInstance
0x1800333b5  mov     rcx, [rbp+18h]; this
0x1800333b9  test    eax, eax
0x1800333bb  jns     short loc_1800333D2
0x1800333bd  mov     r9d, eax; char *
0x1800333c0  lea     r8, aShellcommonShe; "shellcommon\\shell\\retaildemo\\util\\r"...
0x1800333c7  mov     edx, 2Dh ; '-'; void *
0x1800333cc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800333d2  mov     rsi, [rbp+arg_0]
0x1800333d6  mov     rax, [rsi]
0x1800333d9  mov     r14, [rax+20h]
0x1800333dd  mov     rcx, [rbx]
0x1800333e0  mov     qword ptr [rbx], 0
0x1800333e7  test    rcx, rcx
0x1800333ea  jz      short loc_1800333F9
0x1800333ec  mov     rax, [rcx]
0x1800333ef  mov     rax, [rax+10h]
0x1800333f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333f8  nop
0x1800333f9  mov     qword ptr [rsp+50h+ppv], rbx; int
0x1800333fe  lea     r9, _GUID_9eb119d8_774f_4077_a531_1899af39f1ae
0x180033405  xor     r8d, r8d
0x180033408  mov     rdx, [rbp+arg_10]
0x18003340c  mov     rcx, rsi
0x18003340f  mov     rax, r14
0x180033412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033417  mov     rcx, [rbp+18h]; this
0x18003341b  test    eax, eax
0x18003341d  jns     short loc_180033434
0x18003341f  mov     r9d, eax; char *
0x180033422  lea     r8, aShellcommonShe; "shellcommon\\shell\\retaildemo\\util\\r"...
0x180033429  mov     edx, 2Eh ; '.'; void *
0x18003342e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180033434  lea     rcx, [rbp+arg_0]
0x180033438  call    ??1?$com_ptr_t@UIWebTokenRequestFactory@Core@Web@Authentication@Security@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>::~com_ptr_t<Windows::Security::Authentication::Web::Core::IWebTokenRequestFactory,wil::err_exception_policy>(void)
0x18003343d  nop
0x18003343e  lea     rcx, [rbp+arg_10]
0x180033442  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180033447  mov     rcx, [rbx]
0x18003344a  mov     [rdi], rcx
0x18003344d  test    rcx, rcx
0x180033450  jz      short loc_18003345F
0x180033452  mov     rax, [rcx]
0x180033455  mov     rax, [rax+8]
0x180033459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003345e  nop
0x18003345f  mov     rax, rdi
0x180033462  lea     r11, [rsp+50h+var_s0]
0x180033467  mov     rbx, [r11+28h]
0x18003346b  mov     rsi, [r11+38h]
0x18003346f  mov     rsp, r11
0x180033472  pop     r14
0x180033474  pop     rdi
0x180033475  pop     rbp
0x180033476  retn
```
