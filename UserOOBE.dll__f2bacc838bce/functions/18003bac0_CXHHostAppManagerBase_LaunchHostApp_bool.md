# CXHHostAppManagerBase::_LaunchHostApp(bool)

- ea: `0x18003bac0`
- end: `0x18003bd55`
- name: `?_LaunchHostApp@CXHHostAppManagerBase@@AEAAJ_N@Z`
- size: `661`
- prototype: `__int64 __fastcall(CXHHostAppManagerBase *__hidden this, bool)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180039740`

## callees

- `0x1800067b0`
- `0x180007134`
- `0x18000876c`
- `0x18000a664`
- `0x18000a684`
- `0x18000b418`
- `0x18000e270`
- `0x1800169b0`
- `0x18003204c`
- `0x1800320d8`
- `0x180032164`
- `0x180038d68`
- `0x18003a954`
- `0x18003b7c8`
- `0x18003bac0`
- `0x18003fbe8`
- `0x180040914`
- `0x1800423bc`
- `0x18004b15c`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003bb56`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003bc82`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003bb56`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003bc82`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CXHHostAppManagerBase::_LaunchHostApp(CXHHostAppManagerBase *this, char a2)
{
  HostAppEnvironment *Instance; // rax
  int v4; // eax
  HRESULT v5; // eax
  __int64 v6; // rbx
  unsigned __int16 **v7; // r8
  HRESULT PackageFullNameFromAppId; // eax
  __int64 v9; // rdx
  unsigned __int64 v10; // r9
  char v11; // bl
  void *v12; // rdx
  int ppv; // [rsp+20h] [rbp-30h]
  int ppva; // [rsp+20h] [rbp-30h]
  unsigned __int16 v16[4]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v17; // [rsp+38h] [rbp-18h]
  __int64 v18; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  LPVOID v20; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v21; // [rsp+88h] [rbp+38h]
  char v22; // [rsp+90h] [rbp+40h] BYREF

  LOBYTE(v21) = a2;
  CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[26],unsigned short const (&)[13]>();
  Instance = HostAppEnvironment::GetInstance();
  v4 = HostAppEnvironment::Setup(Instance);
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2A5,
      (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
      (const char *)(unsigned int)v4,
      ppv);
  wil::AcquireSRWLockExclusive(&v22, (char *)this + 16);
  *((_BYTE *)this + 24) = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
  v20 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  v5 = CoCreateInstance(&CLSID_PackageDebugSettings, 0, 1u, &GUID_f27c3930_8029_4ad1_94e3_3dba417810c1, &v20);
  LODWORD(v6) = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B5,
      (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
      (const char *)(unsigned int)v5,
      ppva);
    goto LABEL_22;
  }
  *(_QWORD *)v16 = 0;
  v17 = 0;
  v18 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v16);
  v17 = -1;
  v18 = -1;
  PackageFullNameFromAppId = CallerIdentity::GetPackageFullNameFromAppId(*((CallerIdentity **)this + 8), v16, v7);
  LODWORD(v6) = PackageFullNameFromAppId;
  if ( PackageFullNameFromAppId < 0 )
  {
    v9 = 696;
LABEL_7:
    v10 = (unsigned int)PackageFullNameFromAppId;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"shell\\lib\\cloudexperiencehostappmanager\\appmanager.cpp",
      (const char *)v10,
      ppva);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v16);
    goto LABEL_22;
  }
  PackageFullNameFromAppId = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v20 + 24LL))(
                               v20,
                               *(_QWORD *)v16,
                               0,
                               0);
  LODWORD(v6) = PackageFullNameFromAppId;
  if ( PackageFullNameFromAppId < 0 )
  {
    v9 = 697;
    goto LABEL_7;
  }
  v21 = 0;
  ppva = 4;
  v6 = (unsigned int)ActivateApplicationForExperienceWithPropertySet(
                       *((_QWORD *)this + 8),
                       *((_QWORD *)this + 11),
                       *((_QWORD *)this + 15));
  (*(void (__fastcall **)(CXHHostAppManagerBase *, __int64))(*(_QWORD *)this + 40LL))(this, v6);
  if ( (int)v6 < 0 )
  {
    v10 = (unsigned int)v6;
    v9 = 708;
    goto LABEL_8;
  }
  CXHHostAppManagerBase::_EndExistingTaskCompletion(this);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 152);
  PackageFullNameFromAppId = CoCreateInstance(
                               &CLSID_OSTaskCompletion,
                               0,
                               1u,
                               &GUID_c7e40572_c36a_43ea_9a40_f3b168da5558,
                               (LPVOID *)this + 19);
  LODWORD(v6) = PackageFullNameFromAppId;
  if ( PackageFullNameFromAppId < 0 )
  {
    v9 = 712;
    goto LABEL_7;
  }
  PackageFullNameFromAppId = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 19) + 24LL))(
                               *((_QWORD *)this + 19),
                               v21,
                               0x100000);
  LODWORD(v6) = PackageFullNameFromAppId;
  if ( PackageFullNameFromAppId < 0 )
  {
    v9 = 713;
    goto LABEL_7;
  }
  wil::AcquireSRWLockShared(&v22, (char *)this + 16);
  v11 = *((_BYTE *)this + 25);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
  if ( !v11 )
  {
    CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[26],unsigned short const (&)[26]>();
    wil::details::ResetEvent(*((wil::details **)this + 4), v12);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2));
  }
  wil::AcquireSRWLockExclusive(&v22, (char *)this + 16);
  *((_BYTE *)this + 24) = 0;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v22);
  CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[26],unsigned short const (&)[11]>();
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v16);
  LODWORD(v6) = 0;
LABEL_22:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003bac0  mov     [rsp-28h+arg_18], rbx
0x18003bac5  mov     byte ptr [rsp-28h+arg_8], dl
0x18003bac9  push    rbp
0x18003baca  push    rsi
0x18003bacb  push    rdi
0x18003bacc  push    r12
0x18003bace  push    r14
0x18003bad0  mov     rbp, rsp
0x18003bad3  sub     rsp, 50h
0x18003bad7  mov     rdi, rcx
0x18003bada  call    ??$CoreEvent1@AEAY0BK@$$CBDAEAY0N@$$CBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0BK@$$CBDAEAY0N@$$CBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[26],ushort const (&)[13]>(char const (&)[26],ushort const (&)[13])
0x18003badf  call    ?GetInstance@HostAppEnvironment@@SAAEAV1@XZ; HostAppEnvironment::GetInstance(void)
0x18003bae4  mov     rcx, rax; this
0x18003bae7  call    ?Setup@HostAppEnvironment@@QEAAJXZ; HostAppEnvironment::Setup(void)
0x18003baec  mov     rcx, [rbp+28h]; this
0x18003baf0  lea     r12, aShellLibCloude; "shell\\lib\\cloudexperiencehostappmanag"...
0x18003baf7  test    eax, eax
0x18003baf9  jns     short loc_18003BB0B
0x18003bafb  mov     r9d, eax; char *
0x18003bafe  mov     r8, r12; unsigned int
0x18003bb01  mov     edx, 2A5h; void *
0x18003bb06  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003bb0b  lea     r14, [rdi+10h]
0x18003bb0f  mov     rdx, r14
0x18003bb12  lea     rcx, [rbp+arg_10]
0x18003bb16  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18003bb1b  mov     byte ptr [rdi+18h], 1
0x18003bb1f  lea     rcx, [rbp+arg_10]
0x18003bb23  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003bb28  mov     [rbp+arg_0], 0
0x18003bb30  lea     rcx, [rbp+arg_0]
0x18003bb34  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003bb39  lea     rax, [rbp+arg_0]
0x18003bb3d  mov     [rsp+50h+ppv], rax; int
0x18003bb42  lea     r9, _GUID_f27c3930_8029_4ad1_94e3_3dba417810c1; riid
0x18003bb49  xor     edx, edx; pUnkOuter
0x18003bb4b  lea     r8d, [rdx+1]; dwClsContext
0x18003bb4f  lea     rcx, CLSID_PackageDebugSettings; rclsid
0x18003bb56  call    cs:__imp_CoCreateInstance
0x18003bb5c  mov     ebx, eax
0x18003bb5e  test    eax, eax
0x18003bb60  jns     short loc_18003BB7B
0x18003bb62  mov     rcx, [rbp+28h]; this
0x18003bb66  mov     r9d, eax; char *
0x18003bb69  mov     r8, r12; unsigned int
0x18003bb6c  mov     edx, 2B5h; void *
0x18003bb71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bb76  jmp     loc_18003BD36
0x18003bb7b  mov     qword ptr [rbp+var_20], 0
0x18003bb83  mov     [rbp+var_18], 0
0x18003bb8b  mov     [rbp+var_10], 0
0x18003bb93  lea     rcx, [rbp+var_20]
0x18003bb97  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003bb9c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003bba0  mov     [rbp+var_18], rax
0x18003bba4  mov     [rbp+var_10], rax
0x18003bba8  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x18003bbac  mov     rcx, [rdi+40h]; this
0x18003bbb0  call    ?GetPackageFullNameFromAppId@CallerIdentity@@YAJPEBGPEAPEAG@Z; CallerIdentity::GetPackageFullNameFromAppId(ushort const *,ushort * *)
0x18003bbb5  mov     ebx, eax
0x18003bbb7  test    eax, eax
0x18003bbb9  jns     short loc_18003BBDE
0x18003bbbb  mov     edx, 2B8h; void *
0x18003bbc0  mov     r9d, eax; char *
0x18003bbc3  mov     rcx, [rbp+28h]; this
0x18003bbc7  mov     r8, r12; unsigned int
0x18003bbca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bbcf  nop
0x18003bbd0  lea     rcx, [rbp+var_20]
0x18003bbd4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003bbd9  jmp     loc_18003BD36
0x18003bbde  mov     rcx, [rbp+arg_0]
0x18003bbe2  mov     rax, [rcx]
0x18003bbe5  xor     r9d, r9d
0x18003bbe8  xor     r8d, r8d
0x18003bbeb  mov     rdx, qword ptr [rbp+var_20]
0x18003bbef  mov     rax, [rax+18h]
0x18003bbf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbf8  mov     ebx, eax
0x18003bbfa  test    eax, eax
0x18003bbfc  jns     short loc_18003BC05
0x18003bbfe  mov     edx, 2B9h
0x18003bc03  jmp     short loc_18003BBC0
0x18003bc05  mov     [rbp+arg_8], 0
0x18003bc0c  lea     rax, [rbp+arg_8]
0x18003bc10  mov     [rsp+50h+var_28], rax
0x18003bc15  mov     dword ptr [rsp+50h+ppv], 4
0x18003bc1d  mov     r8, [rdi+78h]
0x18003bc21  mov     rdx, [rdi+58h]
0x18003bc25  mov     rcx, [rdi+40h]
0x18003bc29  call    ?ActivateApplicationForExperienceWithPropertySet@@YAJPEBG00PEAUIPropertySet@Collections@Foundation@Windows@@W4ActivateApplicationForExperienceOptions@@PEAK@Z; ActivateApplicationForExperienceWithPropertySet(ushort const *,ushort const *,ushort const *,Windows::Foundation::Collections::IPropertySet *,ActivateApplicationForExperienceOptions,ulong *)
0x18003bc2e  mov     ebx, eax
0x18003bc30  mov     rcx, [rdi]
0x18003bc33  mov     rax, [rcx+28h]
0x18003bc37  mov     edx, ebx
0x18003bc39  mov     rcx, rdi
0x18003bc3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc41  test    ebx, ebx
0x18003bc43  jns     short loc_18003BC52
0x18003bc45  mov     r9d, ebx
0x18003bc48  mov     edx, 2C4h
0x18003bc4d  jmp     loc_18003BBC3
0x18003bc52  mov     rcx, rdi; this
0x18003bc55  call    ?_EndExistingTaskCompletion@CXHHostAppManagerBase@@AEAAXXZ; CXHHostAppManagerBase::_EndExistingTaskCompletion(void)
0x18003bc5a  lea     rsi, [rdi+98h]
0x18003bc61  mov     rcx, rsi
0x18003bc64  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003bc69  mov     [rsp+50h+ppv], rsi; ppv
0x18003bc6e  lea     r9, _GUID_c7e40572_c36a_43ea_9a40_f3b168da5558; riid
0x18003bc75  xor     edx, edx; pUnkOuter
0x18003bc77  lea     r8d, [rdx+1]; dwClsContext
0x18003bc7b  lea     rcx, CLSID_OSTaskCompletion; rclsid
0x18003bc82  call    cs:__imp_CoCreateInstance
0x18003bc88  mov     ebx, eax
0x18003bc8a  test    eax, eax
0x18003bc8c  jns     short loc_18003BC98
0x18003bc8e  mov     edx, 2C8h
0x18003bc93  jmp     loc_18003BBC0
0x18003bc98  mov     rcx, [rsi]
0x18003bc9b  mov     rax, [rcx]
0x18003bc9e  mov     r8d, 100000h
0x18003bca4  mov     edx, [rbp+arg_8]
0x18003bca7  mov     rax, [rax+18h]
0x18003bcab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bcb0  mov     ebx, eax
0x18003bcb2  test    eax, eax
0x18003bcb4  jns     short loc_18003BCC0
0x18003bcb6  mov     edx, 2C9h
0x18003bcbb  jmp     loc_18003BBC0
0x18003bcc0  mov     rdx, r14
0x18003bcc3  lea     rcx, [rbp+arg_10]
0x18003bcc7  call    ?AcquireSRWLockShared@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockShared(_RTL_SRWLOCK *)
0x18003bccc  mov     bl, [rdi+19h]
0x18003bccf  lea     rcx, [rbp+arg_10]
0x18003bcd3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003bcd8  test    bl, bl
0x18003bcda  jnz     short loc_18003BD0C
0x18003bcdc  call    ??$CoreEvent1@AEAY0BK@$$CBDAEAY0BK@$$CBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0BK@$$CBDAEAY0BK@$$CBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[26],ushort const (&)[26]>(char const (&)[26],ushort const (&)[26])
0x18003bce1  mov     rcx, [rdi+20h]; this
0x18003bce5  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x18003bcea  lea     rax, WPP_GLOBAL_Control
0x18003bcf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bcf8  cmp     rcx, rax
0x18003bcfb  jz      short loc_18003BD0C
0x18003bcfd  test    byte ptr [rcx+1Ch], 8
0x18003bd01  jz      short loc_18003BD0C
0x18003bd03  mov     rcx, [rcx+10h]
0x18003bd07  call    WPP_SF_
0x18003bd0c  mov     rdx, r14
0x18003bd0f  lea     rcx, [rbp+arg_10]
0x18003bd13  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18003bd18  mov     byte ptr [rdi+18h], 0
0x18003bd1c  lea     rcx, [rbp+arg_10]
0x18003bd20  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003bd25  call    ??$CoreEvent1@AEAY0BK@$$CBDAEAY0L@$$CBG@CloudExperienceHostCoreTelemetry@@SAXAEAY0BK@$$CBDAEAY0L@$$CBG@Z; CloudExperienceHostCoreTelemetry::CoreEvent1<char const (&)[26],ushort const (&)[11]>(char const (&)[26],ushort const (&)[11])
0x18003bd2a  nop
0x18003bd2b  lea     rcx, [rbp+var_20]
0x18003bd2f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003bd34  xor     ebx, ebx
0x18003bd36  lea     rcx, [rbp+arg_0]
0x18003bd3a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003bd3f  mov     eax, ebx
0x18003bd41  mov     rbx, [rsp+50h+arg_18]
0x18003bd49  add     rsp, 50h
0x18003bd4d  pop     r14
0x18003bd4f  pop     r12
0x18003bd51  pop     rdi
0x18003bd52  pop     rsi
0x18003bd53  pop     rbp
0x18003bd54  retn
```
