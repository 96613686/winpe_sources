# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::SetWasContinuedAnyway(int)

- ea: `0x180034540`
- end: `0x18003479e`
- name: `?SetWasContinuedAnyway@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJH@Z`
- size: `606`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *__hidden this, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180009be4`
- `0x18000a5c4`
- `0x1800179f8`
- `0x1800187d4`
- `0x18001c920`
- `0x18002335c`
- `0x18002eff0`
- `0x180034540`
- `0x18003a52c`
- `0x1800a0ff8`
- `0x1800a1fa8`
- `0x1800bb010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x180034575`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180034575`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003477f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003477f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034736`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034736`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x18003461e`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x18003461e`

## pseudocode

```c
__int64 __fastcall EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::SetWasContinuedAnyway(
        EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *this,
        int a2)
{
  int ActiveUserSid; // eax
  unsigned int v3; // ebx
  int v4; // eax
  __int64 v5; // rdx
  int v6; // edx
  FirstSync *v7; // rcx
  __int64 DatabaseManagerInstance; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, __int64 *); // rbx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, PCWSTR *); // rdi
  int v16; // eax
  __int64 v17; // rdx
  const WCHAR *StringRawBuffer; // rax
  const unsigned __int16 *v19; // r8
  int v20; // r9d
  PCWSTR pszMore; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v23; // [rsp+28h] [rbp-18h] BYREF
  HSTRING string[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  __int64 v26; // [rsp+60h] [rbp+20h] BYREF
  __int64 v27; // [rsp+68h] [rbp+28h] BYREF

  string[0] = 0;
  v23 = 0;
  if ( a2 )
  {
    Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(string, &v23);
    v4 = FirstSync::PublishDeviceBootstrapCompleteEvent(v7, v6);
    v3 = v4;
    if ( v4 < 0 )
    {
      v5 = 1493;
      goto LABEL_9;
    }
LABEL_5:
    v4 = MarkEspComplete(string[0]);
    v3 = v4;
    if ( v4 < 0 )
    {
      v5 = 1497;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)v4,
        (int)pszMore);
      goto LABEL_24;
    }
    v26 = 0;
    DatabaseManagerInstance = GetDatabaseManagerInstance();
    v9 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)DatabaseManagerInstance + 32LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
    v10 = v9(DatabaseManagerInstance, 8289, &v26);
    v3 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5DC,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)v10,
        (int)pszMore);
LABEL_12:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
      goto LABEL_24;
    }
    v11 = v26;
    v27 = 0;
    v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    v13 = v12(v11, &v27);
    v3 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5DF,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
        (const char *)(unsigned int)v13,
        (int)pszMore);
LABEL_15:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
      goto LABEL_12;
    }
    v14 = v27;
    if ( v27 )
    {
      pszMore = 0;
      v15 = *(__int64 (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v27 + 32LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &pszMore,
        0);
      v16 = v15(v14, &pszMore);
      v3 = v16;
      if ( v16 < 0 )
      {
        v17 = 1508;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
          (const char *)(unsigned int)v16,
          (int)pszMore);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszMore);
        goto LABEL_15;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
      v16 = FirstSync::SetWasContinuedAnyway(pszMore, StringRawBuffer, v19, v20);
      v3 = v16;
      if ( v16 < 0 )
      {
        v17 = 1509;
        goto LABEL_19;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszMore);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
    v3 = 1;
    goto LABEL_24;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v23,
    0);
  ActiveUserSid = DmGetActiveUserSid(&v23);
  v3 = ActiveUserSid;
  if ( ActiveUserSid >= 0 )
  {
    pszMore = v23;
    Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(string, &pszMore);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
    goto LABEL_5;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5CD,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollment\\reflectedenroller.cpp",
    (const char *)(unsigned int)ActiveUserSid,
    (int)pszMore);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
LABEL_24:
  WindowsDeleteString(string[0]);
  return v3;
}

```

## disassembly

```asm
0x180034540  mov     [rsp-8+arg_0], rbx
0x180034545  mov     [rsp-8+arg_8], rdi
0x18003454a  push    rbp
0x18003454b  mov     rbp, rsp
0x18003454e  sub     rsp, 40h
0x180034552  mov     [rbp+string], 0
0x18003455a  mov     [rbp+var_18], 0
0x180034562  test    edx, edx
0x180034564  jnz     short loc_1800345E1
0x180034566  xor     edx, edx
0x180034568  lea     rcx, [rbp+var_18]
0x18003456c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180034571  lea     rcx, [rbp+var_18]
0x180034575  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18003457c  nop     dword ptr [rax+rax+00h]
0x180034581  mov     ebx, eax
0x180034583  test    eax, eax
0x180034585  jns     short loc_1800345AD
0x180034587  mov     rcx, [rbp+8]; this
0x18003458b  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180034592  mov     r9d, eax; char *
0x180034595  mov     edx, 5CDh; void *
0x18003459a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003459f  lea     rcx, [rbp+var_18]
0x1800345a3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800345a8  jmp     loc_18003477B
0x1800345ad  mov     rax, [rbp+var_18]
0x1800345b1  lea     rdx, [rbp+pszMore]
0x1800345b5  lea     rcx, [rbp+string]
0x1800345b9  mov     [rbp+pszMore], rax
0x1800345bd  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x1800345c2  lea     rcx, [rbp+var_18]
0x1800345c6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800345cb  mov     rcx, [rbp+string]
0x1800345cf  call    MarkEspComplete
0x1800345d4  mov     ebx, eax
0x1800345d6  test    eax, eax
0x1800345d8  jns     short loc_180034616
0x1800345da  mov     edx, 5D9h
0x1800345df  jmp     short loc_1800345FE
0x1800345e1  lea     rdx, [rbp+var_18]
0x1800345e5  lea     rcx, [rbp+string]
0x1800345e9  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x1800345ee  call    ?PublishDeviceBootstrapCompleteEvent@FirstSync@@YAJH@Z; FirstSync::PublishDeviceBootstrapCompleteEvent(int)
0x1800345f3  mov     ebx, eax
0x1800345f5  test    eax, eax
0x1800345f7  jns     short loc_1800345CB
0x1800345f9  mov     edx, 5D5h; void *
0x1800345fe  mov     rcx, [rbp+8]; this
0x180034602  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180034609  mov     r9d, eax; char *
0x18003460c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034611  jmp     loc_18003477B
0x180034616  mov     [rbp+arg_10], 0
0x18003461e  call    cs:__imp_GetDatabaseManagerInstance
0x180034625  nop     dword ptr [rax+rax+00h]
0x18003462a  mov     rdi, rax
0x18003462d  mov     rcx, [rax]
0x180034630  mov     rbx, [rcx+20h]
0x180034634  lea     rcx, [rbp+arg_10]
0x180034638  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003463d  lea     r8, [rbp+arg_10]
0x180034641  mov     edx, 2061h
0x180034646  mov     rcx, rdi
0x180034649  mov     rax, rbx
0x18003464c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034651  mov     ebx, eax
0x180034653  test    eax, eax
0x180034655  jns     short loc_18003467D
0x180034657  mov     rcx, [rbp+8]; this
0x18003465b  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180034662  mov     r9d, eax; char *
0x180034665  mov     edx, 5DCh; void *
0x18003466a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003466f  lea     rcx, [rbp+arg_10]
0x180034673  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180034678  jmp     loc_18003477B
0x18003467d  mov     rdi, [rbp+arg_10]
0x180034681  lea     rcx, [rbp+arg_18]
0x180034685  mov     [rbp+arg_18], 0
0x18003468d  mov     rax, [rdi]
0x180034690  mov     rbx, [rax+18h]
0x180034694  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180034699  lea     rdx, [rbp+arg_18]
0x18003469d  mov     rcx, rdi
0x1800346a0  mov     rax, rbx
0x1800346a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800346a8  mov     ebx, eax
0x1800346aa  test    eax, eax
0x1800346ac  jns     short loc_1800346D1
0x1800346ae  mov     rcx, [rbp+8]; this
0x1800346b2  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800346b9  mov     r9d, eax; char *
0x1800346bc  mov     edx, 5DFh; void *
0x1800346c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800346c6  lea     rcx, [rbp+arg_18]
0x1800346ca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800346cf  jmp     short loc_18003466F
0x1800346d1  mov     rbx, [rbp+arg_18]
0x1800346d5  test    rbx, rbx
0x1800346d8  jz      loc_180034764
0x1800346de  mov     [rbp+pszMore], 0
0x1800346e6  lea     rcx, [rbp+pszMore]
0x1800346ea  mov     rax, [rbx]
0x1800346ed  xor     edx, edx
0x1800346ef  mov     rdi, [rax+20h]
0x1800346f3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800346f8  lea     rdx, [rbp+pszMore]
0x1800346fc  mov     rcx, rbx
0x1800346ff  mov     rax, rdi
0x180034702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034707  mov     ebx, eax
0x180034709  test    eax, eax
0x18003470b  jns     short loc_180034730
0x18003470d  mov     edx, 5E4h; void *
0x180034712  mov     rcx, [rbp+8]; this
0x180034716  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003471d  mov     r9d, eax; char *
0x180034720  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180034725  lea     rcx, [rbp+pszMore]
0x180034729  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003472e  jmp     short loc_1800346C6
0x180034730  mov     rcx, [rbp+string]; string
0x180034734  xor     edx, edx; length
0x180034736  call    cs:__imp_WindowsGetStringRawBuffer
0x18003473d  nop     dword ptr [rax+rax+00h]
0x180034742  mov     rcx, [rbp+pszMore]; pszMore
0x180034746  mov     rdx, rax; PCWSTR
0x180034749  call    ?SetWasContinuedAnyway@FirstSync@@YAJPEBG0H@Z; FirstSync::SetWasContinuedAnyway(ushort const *,ushort const *,int)
0x18003474e  mov     ebx, eax
0x180034750  test    eax, eax
0x180034752  jns     short loc_18003475B
0x180034754  mov     edx, 5E5h
0x180034759  jmp     short loc_180034712
0x18003475b  lea     rcx, [rbp+pszMore]
0x18003475f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180034764  lea     rcx, [rbp+arg_18]
0x180034768  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003476d  lea     rcx, [rbp+arg_10]
0x180034771  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180034776  mov     ebx, 1
0x18003477b  mov     rcx, [rbp+string]; string
0x18003477f  call    cs:__imp_WindowsDeleteString
0x180034786  nop     dword ptr [rax+rax+00h]
0x18003478b  mov     rdi, [rsp+40h+arg_8]
0x180034790  mov     eax, ebx
0x180034792  mov     rbx, [rsp+40h+arg_0]
0x180034797  add     rsp, 40h
0x18003479b  pop     rbp
0x18003479c  retn
```
