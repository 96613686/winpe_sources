# RemoveRetailDemoOfflineContentTask::RemoveRetailDemoOptionalComponents(void)

- ea: `0x180012c48`
- end: `0x180012fdf`
- name: `?RemoveRetailDemoOptionalComponents@RemoveRetailDemoOfflineContentTask@@CAXXZ`
- size: `919`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800125ac`

## callees

- `0x180008bbc`
- `0x18000e3bc`
- `0x18001094c`
- `0x180010a60`
- `0x180012c48`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012de9`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180012de9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012c85`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012c85`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180012cf2`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180012cf2`

## string_xrefs

- `0x180012f10`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\removeofflinecontent.cpp`
- `0x180012f25`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\removeofflinecontent.cpp`
- `0x180012f3a`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\removeofflinecontent.cpp`
- `0x180012f4f`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\removeofflinecontent.cpp`
- `0x180012f64`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\removeofflinecontent.cpp`
- `0x180012f79`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\removeofflinecontent.cpp`
- `0x180012f8e`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\removeofflinecontent.cpp`
- `0x180012fa3`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\removeofflinecontent.cpp`
- `0x180012fb8`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\removeofflinecontent.cpp`
- `0x180012fcd`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\removeofflinecontent.cpp`
- `0x180012ca6`: `RetailDemoService`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall RemoveRetailDemoOfflineContentTask::RemoveRetailDemoOptionalComponents(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  HRESULT Instance; // eax
  int v4; // eax
  HRESULT v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  IUnknown *v8; // rdi
  ULONG (__stdcall *AddRef)(IUnknown *); // rbx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  char v13; // si
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64, __int64 *, int *); // rbx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, LPCWCH *); // rbx
  int v21; // eax
  unsigned __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  IUnknown *v25; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall *v31)(_QWORD, GUID *, __int64 *); // rdi
  int v32; // eax
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r8
  int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rdx
  __int64 v42; // r8
  int ppv; // [rsp+20h] [rbp-48h]
  int *ppva; // [rsp+20h] [rbp-48h]
  int v45[2]; // [rsp+40h] [rbp-28h] BYREF
  LPCWCH lpString1; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v47[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  int v49; // [rsp+A0h] [rbp+38h] BYREF
  __int64 v50; // [rsp+A8h] [rbp+40h] BYREF
  IUnknown *pProxy; // [rsp+B0h] [rbp+48h] BYREF
  __int64 v52; // [rsp+B8h] [rbp+50h] BYREF

  pProxy = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy, a2, a3);
  Instance = CoCreateInstance(
               &GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed,
               0,
               0x15u,
               &GUID_75207391_23f2_4396_85f0_8fdb879ed0ed,
               (LPVOID *)&pProxy);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  v4 = ((__int64 (__fastcall *)(IUnknown *, __int64, const wchar_t *, _QWORD))pProxy->lpVtbl[1].QueryInterface)(
         pProxy,
         65584,
         L"RetailDemoService",
         0);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
      (const char *)(unsigned int)v4,
      0);
  v5 = CoSetProxyBlanket(
         pProxy,
         0xFFFFFFFF,
         0xFFFFFFFF,
         (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
         5u,
         3u,
         (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
         0);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
      (const char *)(unsigned int)v5,
      (int)ppva);
  v47[0] = 0;
  v8 = pProxy;
  AddRef = pProxy->lpVtbl[2].AddRef;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v47, v6, v7);
  v10 = ((__int64 (__fastcall *)(IUnknown *, __int64, _QWORD *))AddRef)(v8, 16, v47);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
      (const char *)(unsigned int)v10,
      (int)ppva);
  v13 = 0;
  v52 = 0;
  v49 = 0;
  while ( 1 )
  {
    v14 = v47[0];
    v15 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v47[0] + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52, v11, v12);
    v16 = v15(v14, 1, &v52, &v49);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
        (const char *)(unsigned int)v16,
        (int)ppva);
    if ( v16 )
      break;
    lpString1 = 0;
    v19 = v52;
    v20 = *(__int64 (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)v52 + 64LL);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &lpString1,
      0);
    v21 = v20(v19, &lpString1);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
        (const char *)(unsigned int)v21,
        (int)ppva);
    v22 = -1;
    do
      ++v22;
    while ( lpString1[v22] );
    if ( v22 > 0x2B && CompareStringOrdinal(lpString1, 43, L"Microsoft-Windows-RetailDemo-OfflineContent", 43, 0) == 2 )
    {
      *(_QWORD *)v45 = 0;
      v25 = pProxy;
      QueryInterface = pProxy->lpVtbl[2].QueryInterface;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v45, v23, v24);
      ppva = v45;
      v27 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, __int64, _QWORD))QueryInterface)(v25, 0, v52, 0);
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x64,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
          (const char *)(unsigned int)v27,
          (int)v45);
      v50 = 0;
      v30 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v45;
      v31 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v45;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50, v28, v29);
      v32 = v31(v30, &GUID_75207393_23f2_4396_85f0_8fdb879ed0ed, &v50);
      if ( v32 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x66,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
          (const char *)(unsigned int)v32,
          (int)v45);
      v33 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v50 + 88LL))(v50, 1, 0);
      if ( v33 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x67,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
          (const char *)(unsigned int)v33,
          (int)v45);
      v13 = 1;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v50, v34, v35);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v45, v36, v37);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpString1);
  }
  if ( v13 )
  {
    LODWORD(v50) = 0;
    v38 = ((__int64 (__fastcall *)(IUnknown *, __int64 *))pProxy->lpVtbl[1].AddRef)(pProxy, &v50);
    if ( v38 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6E,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\removeofflinecontent.cpp",
        (const char *)(unsigned int)v38,
        (int)ppva);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52, v17, v18);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v47, v39, v40);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy, v41, v42);
}

```

## disassembly

```asm
0x180012c48  push    rbp
0x180012c4a  push    rbx
0x180012c4b  push    rsi
0x180012c4c  push    rdi
0x180012c4d  push    r14
0x180012c4f  push    r15
0x180012c51  mov     rbp, rsp
0x180012c54  sub     rsp, 68h
0x180012c58  xor     r14d, r14d
0x180012c5b  mov     [rbp+pProxy], r14
0x180012c5f  lea     rcx, [rbp+pProxy]
0x180012c63  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012c68  lea     rax, [rbp+pProxy]
0x180012c6c  mov     [rsp+68h+ppv], rax; int
0x180012c71  lea     r9, _GUID_75207391_23f2_4396_85f0_8fdb879ed0ed; riid
0x180012c78  xor     edx, edx; pUnkOuter
0x180012c7a  lea     r8d, [r14+15h]; dwClsContext
0x180012c7e  lea     rcx, _GUID_752073a1_23f2_4396_85f0_8fdb879ed0ed; rclsid
0x180012c85  call    cs:__imp_CoCreateInstance
0x180012c8b  mov     rcx, [rbp+30h]; this
0x180012c8f  test    eax, eax
0x180012c91  js      loc_180012F37
0x180012c97  mov     rcx, [rbp+pProxy]
0x180012c9b  mov     rax, [rcx]
0x180012c9e  mov     [rsp+68h+ppv], r14; int
0x180012ca3  xor     r9d, r9d
0x180012ca6  lea     r8, aRetaildemoserv; "RetailDemoService"
0x180012cad  mov     edx, 10030h
0x180012cb2  mov     rax, [rax+18h]
0x180012cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cbb  mov     rcx, [rbp+30h]; this
0x180012cbf  test    eax, eax
0x180012cc1  js      loc_180012F4C
0x180012cc7  mov     [rsp+68h+dwCapabilities], r14d; dwCapabilities
0x180012ccc  or      r15, 0FFFFFFFFFFFFFFFFh
0x180012cd0  mov     [rsp+68h+pAuthInfo], r15; pAuthInfo
0x180012cd5  mov     [rsp+68h+dwImpLevel], 3; dwImpLevel
0x180012cdd  mov     dword ptr [rsp+68h+ppv], 5; int
0x180012ce5  mov     r9, r15; pServerPrincName
0x180012ce8  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180012ceb  mov     r8d, edx; dwAuthzSvc
0x180012cee  mov     rcx, [rbp+pProxy]; pProxy
0x180012cf2  call    cs:__imp_CoSetProxyBlanket
0x180012cf8  mov     rcx, [rbp+30h]; this
0x180012cfc  test    eax, eax
0x180012cfe  js      loc_180012F61
0x180012d04  mov     [rbp+var_18], r14
0x180012d08  mov     rdi, [rbp+pProxy]
0x180012d0c  mov     rax, [rdi]
0x180012d0f  mov     rbx, [rax+38h]
0x180012d13  lea     rcx, [rbp+var_18]
0x180012d17  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012d1c  lea     r8, [rbp+var_18]
0x180012d20  lea     edx, [r14+10h]
0x180012d24  mov     rcx, rdi
0x180012d27  mov     rax, rbx
0x180012d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d2f  mov     rcx, [rbp+30h]; this
0x180012d33  test    eax, eax
0x180012d35  js      loc_180012F76
0x180012d3b  mov     sil, r14b
0x180012d3e  mov     [rbp+arg_18], r14
0x180012d42  mov     [rbp+arg_0], r14d
0x180012d46  mov     rdi, [rbp+var_18]
0x180012d4a  mov     rax, [rdi]
0x180012d4d  mov     rbx, [rax+18h]
0x180012d51  lea     rcx, [rbp+arg_18]
0x180012d55  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012d5a  lea     r9, [rbp+arg_0]
0x180012d5e  lea     r8, [rbp+arg_18]
0x180012d62  mov     edx, 1
0x180012d67  mov     rcx, rdi
0x180012d6a  mov     rax, rbx
0x180012d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d72  mov     rcx, [rbp+30h]; this
0x180012d76  test    eax, eax
0x180012d78  js      loc_180012F22
0x180012d7e  jnz     loc_180012EBE
0x180012d84  mov     [rbp+lpString1], r14
0x180012d88  mov     rdi, [rbp+arg_18]
0x180012d8c  mov     rax, [rdi]
0x180012d8f  mov     rbx, [rax+40h]
0x180012d93  xor     edx, edx
0x180012d95  lea     rcx, [rbp+lpString1]
0x180012d99  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180012d9e  lea     rdx, [rbp+lpString1]
0x180012da2  mov     rcx, rdi
0x180012da5  mov     rax, rbx
0x180012da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dad  mov     rcx, [rbp+30h]; this
0x180012db1  test    eax, eax
0x180012db3  js      loc_180012FCA
0x180012db9  mov     rcx, [rbp+lpString1]; lpString1
0x180012dbd  mov     rax, r15
0x180012dc0  inc     rax
0x180012dc3  cmp     [rcx+rax*2], r14w
0x180012dc8  jnz     short loc_180012DC0
0x180012dca  cmp     rax, 2Bh ; '+'
0x180012dce  jbe     loc_180012EB0
0x180012dd4  mov     dword ptr [rsp+68h+ppv], r14d; bIgnoreCase
0x180012dd9  mov     r9d, 2Bh ; '+'; cchCount2
0x180012ddf  lea     r8, String2; "Microsoft-Windows-RetailDemo-OfflineCon"...
0x180012de6  mov     edx, r9d; cchCount1
0x180012de9  call    cs:__imp_CompareStringOrdinal
0x180012def  cmp     eax, 2
0x180012df2  jnz     loc_180012EB0
0x180012df8  mov     qword ptr [rbp+var_28], r14
0x180012dfc  mov     rdi, [rbp+pProxy]
0x180012e00  mov     rax, [rdi]
0x180012e03  mov     rbx, [rax+30h]
0x180012e07  lea     rcx, [rbp+var_28]
0x180012e0b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012e10  lea     rax, [rbp+var_28]
0x180012e14  mov     [rsp+68h+ppv], rax; int
0x180012e19  xor     r9d, r9d
0x180012e1c  mov     r8, [rbp+arg_18]
0x180012e20  xor     edx, edx
0x180012e22  mov     rcx, rdi
0x180012e25  mov     rax, rbx
0x180012e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e2d  mov     rcx, [rbp+30h]; this
0x180012e31  test    eax, eax
0x180012e33  js      loc_180012FB5
0x180012e39  mov     [rbp+arg_8], r14
0x180012e3d  mov     rbx, qword ptr [rbp+var_28]
0x180012e41  mov     rax, [rbx]
0x180012e44  mov     rdi, [rax]
0x180012e47  lea     rcx, [rbp+arg_8]
0x180012e4b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012e50  lea     r8, [rbp+arg_8]
0x180012e54  lea     rdx, _GUID_75207393_23f2_4396_85f0_8fdb879ed0ed
0x180012e5b  mov     rcx, rbx
0x180012e5e  mov     rax, rdi
0x180012e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e66  nop
0x180012e67  mov     rcx, [rbp+30h]; this
0x180012e6b  test    eax, eax
0x180012e6d  js      loc_180012FA0
0x180012e73  mov     rcx, [rbp+arg_8]
0x180012e77  mov     rax, [rcx]
0x180012e7a  xor     r9d, r9d
0x180012e7d  xor     r8d, r8d
0x180012e80  lea     edx, [r9+1]
0x180012e84  mov     rax, [rax+58h]
0x180012e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e8d  mov     rcx, [rbp+30h]; this
0x180012e91  test    eax, eax
0x180012e93  js      loc_180012F8B
0x180012e99  mov     sil, 1
0x180012e9c  lea     rcx, [rbp+arg_8]
0x180012ea0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012ea5  nop
0x180012ea6  lea     rcx, [rbp+var_28]
0x180012eaa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012eaf  nop
0x180012eb0  lea     rcx, [rbp+lpString1]
0x180012eb4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180012eb9  jmp     loc_180012D46
0x180012ebe  test    sil, sil
0x180012ec1  jz      short loc_180012EE3
0x180012ec3  mov     dword ptr [rbp+arg_8], r14d
0x180012ec7  mov     rcx, [rbp+pProxy]
0x180012ecb  mov     rax, [rcx]
0x180012ece  lea     rdx, [rbp+arg_8]
0x180012ed2  mov     rax, [rax+20h]
0x180012ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012edb  mov     rcx, [rbp+30h]; this
0x180012edf  test    eax, eax
0x180012ee1  js      short loc_180012F0D
0x180012ee3  lea     rcx, [rbp+arg_18]
0x180012ee7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012eec  nop
0x180012eed  lea     rcx, [rbp+var_18]
0x180012ef1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012ef6  nop
0x180012ef7  lea     rcx, [rbp+pProxy]
0x180012efb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012f00  add     rsp, 68h
0x180012f04  pop     r15
0x180012f06  pop     r14
0x180012f08  pop     rdi
0x180012f09  pop     rsi
0x180012f0a  pop     rbx
0x180012f0b  pop     rbp
0x180012f0c  retn
0x180012f0d  mov     r9d, eax; char *
0x180012f10  lea     r8, aPcshellShellRe_35; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180012f17  mov     edx, 6Eh ; 'n'; void *
0x180012f1c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012f22  mov     r9d, eax; char *
0x180012f25  lea     r8, aPcshellShellRe_35; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180012f2c  mov     edx, 5Ch ; '\'; void *
0x180012f31  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012f37  mov     r9d, eax; char *
0x180012f3a  lea     r8, aPcshellShellRe_35; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180012f41  mov     edx, 54h ; 'T'; void *
0x180012f46  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012f4c  mov     r9d, eax; char *
0x180012f4f  lea     r8, aPcshellShellRe_35; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180012f56  mov     edx, 55h ; 'U'; void *
0x180012f5b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012f61  mov     r9d, eax; char *
0x180012f64  lea     r8, aPcshellShellRe_35; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180012f6b  mov     edx, 56h ; 'V'; void *
0x180012f70  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012f76  mov     r9d, eax; char *
0x180012f79  lea     r8, aPcshellShellRe_35; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180012f80  mov     edx, 58h ; 'X'; void *
0x180012f85  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012f8b  mov     r9d, eax; char *
0x180012f8e  lea     r8, aPcshellShellRe_35; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180012f95  mov     edx, 67h ; 'g'; void *
0x180012f9a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012fa0  mov     r9d, eax; char *
0x180012fa3  lea     r8, aPcshellShellRe_35; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180012faa  mov     edx, 66h ; 'f'; void *
0x180012faf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012fb5  mov     r9d, eax; char *
0x180012fb8  lea     r8, aPcshellShellRe_35; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180012fbf  mov     edx, 64h ; 'd'; void *
0x180012fc4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180012fca  mov     r9d, eax; char *
0x180012fcd  lea     r8, aPcshellShellRe_35; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180012fd4  mov     edx, 5Fh ; '_'; void *
0x180012fd9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
