# PrelaunchAppsTask::Execute(void)

- ea: `0x180027250`
- end: `0x1800275dc`
- name: `?Execute@PrelaunchAppsTask@@MEAAXXZ`
- size: `908`
- prototype: `void __fastcall(PrelaunchAppsTask *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003390`
- `0x180008bbc`
- `0x18000e3bc`
- `0x18001094c`
- `0x18001e55c`
- `0x180027250`
- `0x180030dc0`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002732a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002732a`

## string_xrefs

- `0x1800272ab`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\prelaunchappstask.cpp`
- `0x1800272ee`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\prelaunchappstask.cpp`
- `0x18002733b`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\prelaunchappstask.cpp`
- `0x180027370`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\prelaunchappstask.cpp`
- `0x180027561`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\prelaunchappstask.cpp`
- `0x180027576`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\prelaunchappstask.cpp`
- `0x18002758b`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\prelaunchappstask.cpp`
- `0x1800275a0`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\prelaunchappstask.cpp`
- `0x1800275b5`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\prelaunchappstask.cpp`
- `0x1800275ca`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\prelaunchappstask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall PrelaunchAppsTask::Execute(PrelaunchAppsTask *this, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, __int64 *); // rbx
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  HRESULT v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned int i; // esi
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD, GUID *, __int64 **); // rbx
  int v20; // eax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // r8
  int v25; // eax
  __int64 v26; // rax
  int v27; // eax
  unsigned int LaunchOptionFromPrelaunchOptions; // eax
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r8
  int ppv; // [rsp+20h] [rbp-79h]
  int ppva; // [rsp+20h] [rbp-79h]
  unsigned int v36; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v37; // [rsp+54h] [rbp-45h] BYREF
  __int64 *v38; // [rsp+58h] [rbp-41h] BYREF
  int v39; // [rsp+60h] [rbp-39h] BYREF
  LPVOID v40; // [rsp+68h] [rbp-31h] BYREF
  __int64 v41; // [rsp+70h] [rbp-29h] BYREF
  __int64 v42; // [rsp+78h] [rbp-21h] BYREF
  __int64 v43; // [rsp+80h] [rbp-19h] BYREF
  __int64 *v44; // [rsp+88h] [rbp-11h] BYREF
  __int64 v45; // [rsp+90h] [rbp-9h] BYREF
  char v46; // [rsp+98h] [rbp-1h]
  __int128 v47; // [rsp+A0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v42 = 0;
  v3 = *((_QWORD *)this + 8);
  v4 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42, a2, a3);
  v5 = v4(v3, &v42);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\prelaunchappstask.cpp",
      (const char *)(unsigned int)v5,
      ppv);
  v41 = 0;
  v8 = v42;
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 88LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41, v6, v7);
  v10 = v9(v8, &v41);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x25,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\prelaunchappstask.cpp",
      (const char *)(unsigned int)v10,
      ppv);
  v40 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40, v11, v12);
  v13 = CoCreateInstance(
          &GUID_1e46246f_b2ad_4a86_9e08_d0f9e01ee05d,
          0,
          1u,
          &GUID_618f3f46_6b42_407a_9b32_690ac75e2e5e,
          &v40);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\prelaunchappstask.cpp",
      (const char *)(unsigned int)v13,
      ppva);
  v37 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v41 + 24LL))(v41, &v37);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\prelaunchappstask.cpp",
      (const char *)(unsigned int)v14,
      ppva);
  for ( i = 0; i < v37; ++i )
  {
    v38 = 0;
    v18 = v41;
    v19 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 **))(*(_QWORD *)v41 + 32LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38, v15, v16);
    v20 = v19(v18, i, &GUID_368af30e_7a5f_4cca_a390_c844bb9ade09, &v38);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\prelaunchappstask.cpp",
        (const char *)(unsigned int)v20,
        ppva);
    v36 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v38 + 96))(v38, &v36);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\prelaunchappstask.cpp",
        (const char *)(unsigned int)v21,
        ppva);
    v39 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v38 + 56))(v38, &v39);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\prelaunchappstask.cpp",
        (const char *)(unsigned int)v22,
        ppva);
    if ( !v39 && v36 )
    {
      v47 = 0;
      v25 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int128 *))(*(_QWORD *)v40 + 48LL))(v40, v38, &v47);
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3A,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\prelaunchappstask.cpp",
          (const char *)(unsigned int)v25,
          ppva);
      v43 = 0;
      v26 = *v38;
      v44 = &v43;
      v45 = 0;
      v46 = 1;
      v27 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v26 + 48))(v38, &v45);
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3D,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\prelaunchappstask.cpp",
          (const char *)(unsigned int)v27,
          ppva);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v44);
      LaunchOptionFromPrelaunchOptions = RetailDemoUtil::GetLaunchOptionFromPrelaunchOptions(v36, 4);
      ppva = 0;
      v29 = (*(__int64 (__fastcall **)(LPVOID, __int64, const unsigned __int16 *, _QWORD))(*(_QWORD *)v40 + 40LL))(
              v40,
              v43,
              &qword_180057BE0,
              LaunchOptionFromPrelaunchOptions);
      if ( v29 != -2147009295 && v29 != -2144927148 && v29 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x42,
          (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\prelaunchappstask.cpp",
          (const char *)(unsigned int)v29,
          0);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v43);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38, v23, v24);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40, v15, v16);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41, v30, v31);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42, v32, v33);
}

```

## disassembly

```asm
0x180027250  push    rbp
0x180027252  push    rbx
0x180027253  push    rsi
0x180027254  push    rdi
0x180027255  push    r14
0x180027257  push    r15
0x180027259  lea     rbp, [rsp-2Fh]
0x18002725e  sub     rsp, 0C8h
0x180027265  mov     rax, cs:__security_cookie
0x18002726c  xor     rax, rsp
0x18002726f  mov     [rbp+57h+var_40], rax
0x180027273  mov     r14, rcx
0x180027276  xor     r15d, r15d
0x180027279  mov     [rbp+57h+var_78], r15
0x18002727d  mov     rdi, [rcx+40h]
0x180027281  mov     rax, [rdi]
0x180027284  mov     rbx, [rax+60h]
0x180027288  lea     rcx, [rbp+57h+var_78]
0x18002728c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180027291  lea     rdx, [rbp+57h+var_78]
0x180027295  mov     rcx, rdi
0x180027298  mov     rax, rbx
0x18002729b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272a0  mov     rcx, [rbp+5Fh]; this
0x1800272a4  test    eax, eax
0x1800272a6  jns     short loc_1800272BC
0x1800272a8  mov     r9d, eax; char *
0x1800272ab  lea     r8, aPcshellShellRe_10; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800272b2  lea     edx, [r15+23h]; void *
0x1800272b6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800272bc  mov     [rbp+57h+var_80], r15
0x1800272c0  mov     rdi, [rbp+57h+var_78]
0x1800272c4  mov     rax, [rdi]
0x1800272c7  mov     rbx, [rax+58h]
0x1800272cb  lea     rcx, [rbp+57h+var_80]
0x1800272cf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800272d4  lea     rdx, [rbp+57h+var_80]
0x1800272d8  mov     rcx, rdi
0x1800272db  mov     rax, rbx
0x1800272de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272e3  mov     rcx, [rbp+5Fh]; this
0x1800272e7  test    eax, eax
0x1800272e9  jns     short loc_180027300
0x1800272eb  mov     r9d, eax; char *
0x1800272ee  lea     r8, aPcshellShellRe_10; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800272f5  mov     edx, 25h ; '%'; void *
0x1800272fa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027300  mov     [rbp+57h+var_88], r15
0x180027304  lea     rcx, [rbp+57h+var_88]
0x180027308  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002730d  lea     rax, [rbp+57h+var_88]
0x180027311  mov     [rsp+0F0h+ppv], rax; int
0x180027316  lea     r9, _GUID_618f3f46_6b42_407a_9b32_690ac75e2e5e; riid
0x18002731d  xor     edx, edx; pUnkOuter
0x18002731f  lea     r8d, [rdx+1]; dwClsContext
0x180027323  lea     rcx, _GUID_1e46246f_b2ad_4a86_9e08_d0f9e01ee05d; rclsid
0x18002732a  call    cs:__imp_CoCreateInstance
0x180027330  mov     rcx, [rbp+5Fh]; this
0x180027334  test    eax, eax
0x180027336  jns     short loc_18002734D
0x180027338  mov     r9d, eax; char *
0x18002733b  lea     r8, aPcshellShellRe_10; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180027342  mov     edx, 28h ; '('; void *
0x180027347  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002734d  mov     [rbp+57h+var_9C], r15d
0x180027351  mov     rcx, [rbp+57h+var_80]
0x180027355  mov     rax, [rcx]
0x180027358  lea     rdx, [rbp+57h+var_9C]
0x18002735c  mov     rax, [rax+18h]
0x180027360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027365  mov     rcx, [rbp+5Fh]; this
0x180027369  test    eax, eax
0x18002736b  jns     short loc_180027382
0x18002736d  mov     r9d, eax; char *
0x180027370  lea     r8, aPcshellShellRe_10; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180027377  mov     edx, 2Ch ; ','; void *
0x18002737c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027382  mov     esi, r15d
0x180027385  cmp     [rbp+57h+var_9C], r15d
0x180027389  jbe     loc_180027525
0x18002738f  mov     [rbp+57h+var_98], r15
0x180027393  mov     rdi, [rbp+57h+var_80]
0x180027397  mov     rax, [rdi]
0x18002739a  mov     rbx, [rax+20h]
0x18002739e  lea     rcx, [rbp+57h+var_98]
0x1800273a2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800273a7  lea     r9, [rbp+57h+var_98]
0x1800273ab  lea     r8, _GUID_368af30e_7a5f_4cca_a390_c844bb9ade09
0x1800273b2  mov     edx, esi
0x1800273b4  mov     rcx, rdi
0x1800273b7  mov     rax, rbx
0x1800273ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273bf  mov     rcx, [rbp+5Fh]; this
0x1800273c3  test    eax, eax
0x1800273c5  js      loc_1800275C7
0x1800273cb  mov     [rbp+57h+var_A0], r15d
0x1800273cf  mov     rcx, [rbp+57h+var_98]
0x1800273d3  mov     rax, [rcx]
0x1800273d6  lea     rdx, [rbp+57h+var_A0]
0x1800273da  mov     rax, [rax+60h]
0x1800273de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273e3  mov     rcx, [rbp+5Fh]; this
0x1800273e7  test    eax, eax
0x1800273e9  js      loc_1800275B2
0x1800273ef  mov     [rbp+57h+var_90], r15d
0x1800273f3  mov     rcx, [rbp+57h+var_98]
0x1800273f7  mov     rax, [rcx]
0x1800273fa  lea     rdx, [rbp+57h+var_90]
0x1800273fe  mov     rax, [rax+38h]
0x180027402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027407  mov     rcx, [rbp+5Fh]; this
0x18002740b  test    eax, eax
0x18002740d  js      loc_18002759D
0x180027413  cmp     [rbp+57h+var_90], r15d
0x180027417  jnz     loc_180027511
0x18002741d  cmp     [rbp+57h+var_A0], r15d
0x180027421  jz      loc_180027511
0x180027427  xorps   xmm0, xmm0
0x18002742a  movups  [rbp+57h+var_50], xmm0
0x18002742e  mov     rcx, [rbp+57h+var_88]
0x180027432  mov     rax, [rcx]
0x180027435  lea     r8, [rbp+57h+var_50]
0x180027439  mov     rdx, [rbp+57h+var_98]
0x18002743d  mov     rax, [rax+30h]
0x180027441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027446  mov     rcx, [rbp+5Fh]; this
0x18002744a  test    eax, eax
0x18002744c  js      loc_180027588
0x180027452  mov     [rbp+57h+var_70], r15
0x180027456  mov     rcx, [rbp+57h+var_98]
0x18002745a  mov     rax, [rcx]
0x18002745d  lea     rdx, [rbp+57h+var_70]
0x180027461  mov     [rbp+57h+var_68], rdx
0x180027465  mov     [rbp+57h+var_60], r15
0x180027469  mov     [rbp+57h+var_58], 1
0x18002746d  lea     rdx, [rbp+57h+var_60]
0x180027471  mov     rax, [rax+30h]
0x180027475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002747a  mov     rcx, [rbp+5Fh]; this
0x18002747e  test    eax, eax
0x180027480  js      loc_180027573
0x180027486  lea     rcx, [rbp+57h+var_68]
0x18002748a  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18002748f  mov     edx, 4
0x180027494  mov     ecx, [rbp+57h+var_A0]
0x180027497  call    ?GetLaunchOptionFromPrelaunchOptions@RetailDemoUtil@@YA?AW4LaunchOptions@@W4RetailDemoPrelaunchOptions@@W42@@Z; RetailDemoUtil::GetLaunchOptionFromPrelaunchOptions(RetailDemoPrelaunchOptions,LaunchOptions)
0x18002749c  mov     r10, [rbp+57h+var_88]
0x1800274a0  mov     rcx, [r10]
0x1800274a3  mov     r11, [rcx+28h]
0x1800274a7  lea     rdx, [rbp+57h+var_50]
0x1800274ab  cmp     [rbp+57h+var_A0], 1
0x1800274af  cmovnz  rdx, r15
0x1800274b3  mov     rcx, [r14+30h]
0x1800274b7  test    rcx, rcx
0x1800274ba  jz      short loc_1800274C1
0x1800274bc  mov     rcx, [rcx]
0x1800274bf  jmp     short loc_1800274C4
0x1800274c1  mov     rcx, r15
0x1800274c4  mov     [rsp+0F0h+var_B8], r15b
0x1800274c9  mov     [rsp+0F0h+var_C0], rdx
0x1800274ce  mov     [rsp+0F0h+var_C8], rcx
0x1800274d3  mov     dword ptr [rsp+0F0h+ppv], r15d; int
0x1800274d8  mov     r9d, eax
0x1800274db  lea     r8, qword_180057BE0
0x1800274e2  mov     rdx, [rbp+57h+var_70]
0x1800274e6  mov     rcx, r10
0x1800274e9  mov     rax, r11
0x1800274ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274f1  cmp     eax, 80073CF1h
0x1800274f6  jz      short loc_180027507
0x1800274f8  cmp     eax, 80270254h
0x1800274fd  jz      short loc_180027507
0x1800274ff  mov     rcx, [rbp+5Fh]; this
0x180027503  test    eax, eax
0x180027505  js      short loc_18002755E
0x180027507  lea     rcx, [rbp+57h+var_70]
0x18002750b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180027510  nop
0x180027511  lea     rcx, [rbp+57h+var_98]
0x180027515  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002751a  inc     esi
0x18002751c  cmp     esi, [rbp+57h+var_9C]
0x18002751f  jb      loc_18002738F
0x180027525  lea     rcx, [rbp+57h+var_88]
0x180027529  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002752e  nop
0x18002752f  lea     rcx, [rbp+57h+var_80]
0x180027533  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180027538  nop
0x180027539  lea     rcx, [rbp+57h+var_78]
0x18002753d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180027542  mov     rcx, [rbp+57h+var_40]
0x180027546  xor     rcx, rsp; StackCookie
0x180027549  call    __security_check_cookie
0x18002754e  add     rsp, 0C8h
0x180027555  pop     r15
0x180027557  pop     r14
0x180027559  pop     rdi
0x18002755a  pop     rsi
0x18002755b  pop     rbx
0x18002755c  pop     rbp
0x18002755d  retn
0x18002755e  mov     r9d, eax; char *
0x180027561  lea     r8, aPcshellShellRe_10; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180027568  mov     edx, 42h ; 'B'; void *
0x18002756d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027573  mov     r9d, eax; char *
0x180027576  lea     r8, aPcshellShellRe_10; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002757d  mov     edx, 3Dh ; '='; void *
0x180027582  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027588  mov     r9d, eax; char *
0x18002758b  lea     r8, aPcshellShellRe_10; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180027592  mov     edx, 3Ah ; ':'; void *
0x180027597  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002759d  mov     r9d, eax; char *
0x1800275a0  lea     r8, aPcshellShellRe_10; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800275a7  mov     edx, 35h ; '5'; void *
0x1800275ac  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800275b2  mov     r9d, eax; char *
0x1800275b5  lea     r8, aPcshellShellRe_10; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800275bc  mov     edx, 33h ; '3'; void *
0x1800275c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800275c7  mov     r9d, eax; char *
0x1800275ca  lea     r8, aPcshellShellRe_10; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800275d1  mov     edx, 30h ; '0'; void *
0x1800275d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
