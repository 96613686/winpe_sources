# EnterpriseDeviceManagement::Enrollment::ReflectedEnroller::SetWasContinuedAnyway(int)

- ea: `0x1800353e0`
- end: `0x180035625`
- name: `?SetWasContinuedAnyway@ReflectedEnroller@Enrollment@EnterpriseDeviceManagement@@UEAAJH@Z`
- size: `581`
- prototype: `__int64 __fastcall(EnterpriseDeviceManagement::Enrollment::ReflectedEnroller *__hidden this, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000992c`
- `0x18000a2a4`
- `0x180017204`
- `0x180019fb8`
- `0x18001e414`
- `0x180024cd0`
- `0x180030378`
- `0x1800353e0`
- `0x18003b198`
- `0x18009e034`
- `0x18009ef78`
- `0x1800b7010`

## import_xrefs

- `DMCmnUtils!DmGetActiveUserSid` at `0x180035415`
- `DMCmnUtils!DmGetActiveUserSid` at `0x180035415`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003560d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003560d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800355ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800355ca`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x1800354b8`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x1800354b8`

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
0x1800353e0  mov     [rsp-8+arg_0], rbx
0x1800353e5  mov     [rsp-8+arg_8], rdi
0x1800353ea  push    rbp
0x1800353eb  mov     rbp, rsp
0x1800353ee  sub     rsp, 40h
0x1800353f2  mov     [rbp+string], 0
0x1800353fa  mov     [rbp+var_18], 0
0x180035402  test    edx, edx
0x180035404  jnz     short loc_18003547B
0x180035406  xor     edx, edx
0x180035408  lea     rcx, [rbp+var_18]
0x18003540c  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180035411  lea     rcx, [rbp+var_18]
0x180035415  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x18003541b  mov     ebx, eax
0x18003541d  test    eax, eax
0x18003541f  jns     short loc_180035447
0x180035421  mov     rcx, [rbp+8]; this
0x180035425  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003542c  mov     r9d, eax; char *
0x18003542f  mov     edx, 5CDh; void *
0x180035434  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035439  lea     rcx, [rbp+var_18]
0x18003543d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180035442  jmp     loc_180035609
0x180035447  mov     rax, [rbp+var_18]
0x18003544b  lea     rdx, [rbp+pszMore]
0x18003544f  lea     rcx, [rbp+string]
0x180035453  mov     [rbp+pszMore], rax
0x180035457  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x18003545c  lea     rcx, [rbp+var_18]
0x180035460  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180035465  mov     rcx, [rbp+string]
0x180035469  call    MarkEspComplete
0x18003546e  mov     ebx, eax
0x180035470  test    eax, eax
0x180035472  jns     short loc_1800354B0
0x180035474  mov     edx, 5D9h
0x180035479  jmp     short loc_180035498
0x18003547b  lea     rdx, [rbp+var_18]
0x18003547f  lea     rcx, [rbp+string]
0x180035483  call    ??$Set@$$T@HString@Wrappers@WRL@Microsoft@@QEAAJAEB$$TUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<std::nullptr_t>(Microsoft::WRL::Details::$$TUDummy const &)
0x180035488  call    ?PublishDeviceBootstrapCompleteEvent@FirstSync@@YAJH@Z; FirstSync::PublishDeviceBootstrapCompleteEvent(int)
0x18003548d  mov     ebx, eax
0x18003548f  test    eax, eax
0x180035491  jns     short loc_180035465
0x180035493  mov     edx, 5D5h; void *
0x180035498  mov     rcx, [rbp+8]; this
0x18003549c  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800354a3  mov     r9d, eax; char *
0x1800354a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800354ab  jmp     loc_180035609
0x1800354b0  mov     [rbp+arg_10], 0
0x1800354b8  call    cs:__imp_GetDatabaseManagerInstance
0x1800354be  mov     rdi, rax
0x1800354c1  mov     rcx, [rax]
0x1800354c4  mov     rbx, [rcx+20h]
0x1800354c8  lea     rcx, [rbp+arg_10]
0x1800354cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800354d1  lea     r8, [rbp+arg_10]
0x1800354d5  mov     edx, 2061h
0x1800354da  mov     rcx, rdi
0x1800354dd  mov     rax, rbx
0x1800354e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800354e5  mov     ebx, eax
0x1800354e7  test    eax, eax
0x1800354e9  jns     short loc_180035511
0x1800354eb  mov     rcx, [rbp+8]; this
0x1800354ef  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800354f6  mov     r9d, eax; char *
0x1800354f9  mov     edx, 5DCh; void *
0x1800354fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035503  lea     rcx, [rbp+arg_10]
0x180035507  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003550c  jmp     loc_180035609
0x180035511  mov     rdi, [rbp+arg_10]
0x180035515  lea     rcx, [rbp+arg_18]
0x180035519  mov     [rbp+arg_18], 0
0x180035521  mov     rax, [rdi]
0x180035524  mov     rbx, [rax+18h]
0x180035528  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003552d  lea     rdx, [rbp+arg_18]
0x180035531  mov     rcx, rdi
0x180035534  mov     rax, rbx
0x180035537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003553c  mov     ebx, eax
0x18003553e  test    eax, eax
0x180035540  jns     short loc_180035565
0x180035542  mov     rcx, [rbp+8]; this
0x180035546  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003554d  mov     r9d, eax; char *
0x180035550  mov     edx, 5DFh; void *
0x180035555  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003555a  lea     rcx, [rbp+arg_18]
0x18003555e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180035563  jmp     short loc_180035503
0x180035565  mov     rbx, [rbp+arg_18]
0x180035569  test    rbx, rbx
0x18003556c  jz      loc_1800355F2
0x180035572  mov     [rbp+pszMore], 0
0x18003557a  lea     rcx, [rbp+pszMore]
0x18003557e  mov     rax, [rbx]
0x180035581  xor     edx, edx
0x180035583  mov     rdi, [rax+20h]
0x180035587  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003558c  lea     rdx, [rbp+pszMore]
0x180035590  mov     rcx, rbx
0x180035593  mov     rax, rdi
0x180035596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003559b  mov     ebx, eax
0x18003559d  test    eax, eax
0x18003559f  jns     short loc_1800355C4
0x1800355a1  mov     edx, 5E4h; void *
0x1800355a6  mov     rcx, [rbp+8]; this
0x1800355aa  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800355b1  mov     r9d, eax; char *
0x1800355b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800355b9  lea     rcx, [rbp+pszMore]
0x1800355bd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800355c2  jmp     short loc_18003555A
0x1800355c4  mov     rcx, [rbp+string]; string
0x1800355c8  xor     edx, edx; length
0x1800355ca  call    cs:__imp_WindowsGetStringRawBuffer
0x1800355d0  mov     rcx, [rbp+pszMore]; pszMore
0x1800355d4  mov     rdx, rax; PCWSTR
0x1800355d7  call    ?SetWasContinuedAnyway@FirstSync@@YAJPEBG0H@Z; FirstSync::SetWasContinuedAnyway(ushort const *,ushort const *,int)
0x1800355dc  mov     ebx, eax
0x1800355de  test    eax, eax
0x1800355e0  jns     short loc_1800355E9
0x1800355e2  mov     edx, 5E5h
0x1800355e7  jmp     short loc_1800355A6
0x1800355e9  lea     rcx, [rbp+pszMore]
0x1800355ed  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800355f2  lea     rcx, [rbp+arg_18]
0x1800355f6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800355fb  lea     rcx, [rbp+arg_10]
0x1800355ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180035604  mov     ebx, 1
0x180035609  mov     rcx, [rbp+string]; string
0x18003560d  call    cs:__imp_WindowsDeleteString
0x180035613  mov     rdi, [rsp+40h+arg_8]
0x180035618  mov     eax, ebx
0x18003561a  mov     rbx, [rsp+40h+arg_0]
0x18003561f  add     rsp, 40h
0x180035623  pop     rbp
0x180035624  retn
```
