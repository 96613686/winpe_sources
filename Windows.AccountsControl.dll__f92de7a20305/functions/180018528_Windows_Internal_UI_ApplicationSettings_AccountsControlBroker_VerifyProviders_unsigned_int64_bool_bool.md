# Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::VerifyProviders(unsigned __int64,bool,bool *)

- ea: `0x180018528`
- end: `0x18001895c`
- name: `?VerifyProviders@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJ_K_NPEA_N@Z`
- size: `1076`
- prototype: `int(Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *__hidden this, unsigned __int64, bool, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800183c0`

## callees

- `0x180006eac`
- `0x180011ffc`
- `0x1800121ac`
- `0x180018528`
- `0x18006c010`

## string_xrefs

- `0x1800185ae`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180018712`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180018731`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180018755`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800187ad`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800188e9`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180018908`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::VerifyProviders(
        Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *this,
        unsigned __int64 a2,
        char a3,
        bool *a4)
{
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 *); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  unsigned int i; // esi
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int IsAssociatedSameUser; // eax
  Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *v23; // rcx
  Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64 *); // rbx
  int v28; // eax
  __int64 v29; // rdx
  unsigned int j; // esi
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, _QWORD, __int64 *); // rbx
  int v33; // eax
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int v36; // eax
  Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *v37; // rcx
  Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *v38; // rcx
  __int64 v39; // rdx
  unsigned int v41; // [rsp+20h] [rbp-40h] BYREF
  __int64 v42; // [rsp+28h] [rbp-38h] BYREF
  __int64 v43; // [rsp+30h] [rbp-30h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v44; // [rsp+38h] [rbp-28h] BYREF
  __int64 v45; // [rsp+40h] [rbp-20h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v46; // [rsp+48h] [rbp-18h] BYREF
  __int64 v47; // [rsp+50h] [rbp-10h] BYREF
  __int64 v48; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  bool v50; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v51; // [rsp+B8h] [rbp+58h] BYREF

  *a4 = 0;
  v48 = 0;
  v8 = *((_QWORD *)this + 78);
  v9 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 56LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
  v10 = v9(v8, &v48);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = 207;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v10,
      v41);
    goto LABEL_51;
  }
  v51 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v48 + 56LL))(v48, &v51);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = 210;
    goto LABEL_5;
  }
  for ( i = 0; i < v51; ++i )
  {
    v43 = 0;
    v14 = v48;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v48 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    v16 = v15(v14, i, &v43);
    v11 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD7,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v16,
        v41);
      goto LABEL_25;
    }
    v45 = 0;
    v17 = v43;
    v18 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v43 + 96LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
    v19 = v18(v17, &v45);
    v11 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDA,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v19,
        v41);
      goto LABEL_23;
    }
    v44 = 0;
    v20 = v45;
    v21 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)v45 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    IsAssociatedSameUser = v21(v20, &v44);
    v11 = IsAssociatedSameUser;
    if ( IsAssociatedSameUser < 0 )
    {
      v25 = 221;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v25,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)IsAssociatedSameUser,
        v41);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
LABEL_23:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
LABEL_25:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      goto LABEL_51;
    }
    v50 = 0;
    IsAssociatedSameUser = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::IsAssociatedSameUser(
                             v23,
                             a2,
                             v44,
                             &v50);
    v11 = IsAssociatedSameUser;
    if ( IsAssociatedSameUser < 0 )
    {
      v25 = 225;
      goto LABEL_21;
    }
    if ( !v50 )
    {
      if ( a3 )
        goto LABEL_18;
      IsAssociatedSameUser = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::IsAssociatedSameUser(
                               v24,
                               0,
                               v44,
                               &v50);
      v11 = IsAssociatedSameUser;
      if ( IsAssociatedSameUser < 0 )
      {
        v25 = 235;
        goto LABEL_21;
      }
      if ( !v50 )
      {
LABEL_18:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
        v11 = 0;
        goto LABEL_51;
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  }
  v42 = 0;
  v26 = *((_QWORD *)this + 78);
  v27 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  v28 = v27(v26, &v42);
  v11 = v28;
  if ( v28 < 0 )
  {
    v29 = 246;
    goto LABEL_28;
  }
  v41 = 0;
  v28 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v42 + 56LL))(v42, &v41);
  v11 = v28;
  if ( v28 < 0 )
  {
    v29 = 249;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v28,
      v41);
LABEL_29:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    goto LABEL_51;
  }
  for ( j = 0; j < v41; ++j )
  {
    v47 = 0;
    v31 = v42;
    v32 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v42 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    v33 = v32(v31, j, &v47);
    v11 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFE,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v33,
        v41);
      goto LABEL_48;
    }
    v46 = 0;
    v34 = v47;
    v35 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)v47 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    v36 = v35(v34, &v46);
    v11 = v36;
    if ( v36 < 0 )
    {
      v39 = 257;
LABEL_46:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v39,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v36,
        v41);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
LABEL_48:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      goto LABEL_29;
    }
    v50 = 0;
    v36 = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::IsAssociatedSameUser(v37, a2, v46, &v50);
    v11 = v36;
    if ( v36 < 0 )
    {
      v39 = 260;
      goto LABEL_46;
    }
    if ( !v50 )
    {
      if ( a3 )
        goto LABEL_43;
      v36 = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::IsAssociatedSameUser(v38, 0, v46, &v50);
      v11 = v36;
      if ( v36 < 0 )
      {
        v39 = 271;
        goto LABEL_46;
      }
      if ( !v50 )
      {
LABEL_43:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
        goto LABEL_50;
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  }
  *a4 = 1;
LABEL_50:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  v11 = 0;
LABEL_51:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
  return v11;
}

```

## disassembly

```asm
0x180018528  mov     [rsp-38h+arg_8], rbx
0x18001852d  push    rbp
0x18001852e  push    rsi
0x18001852f  push    rdi
0x180018530  push    r12
0x180018532  push    r13
0x180018534  push    r14
0x180018536  push    r15
0x180018538  mov     rbp, rsp
0x18001853b  sub     rsp, 60h
0x18001853f  mov     r12, r9
0x180018542  mov     r14b, r8b
0x180018545  mov     r15, rdx
0x180018548  mov     r13, rcx
0x18001854b  mov     byte ptr [r9], 0
0x18001854f  mov     [rbp+var_8], 0
0x180018557  mov     rdi, [rcx+270h]
0x18001855e  mov     rax, [rdi]
0x180018561  mov     rbx, [rax+38h]
0x180018565  lea     rcx, [rbp+var_8]
0x180018569  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001856e  lea     rdx, [rbp+var_8]
0x180018572  mov     rcx, rdi
0x180018575  mov     rax, rbx
0x180018578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001857d  mov     ebx, eax
0x18001857f  xor     edi, edi
0x180018581  test    eax, eax
0x180018583  jns     short loc_18001858C
0x180018585  mov     edx, 0CFh
0x18001858a  jmp     short loc_1800185AE
0x18001858c  mov     [rbp+arg_18], edi
0x18001858f  mov     rcx, [rbp+var_8]
0x180018593  mov     rax, [rcx]
0x180018596  lea     rdx, [rbp+arg_18]
0x18001859a  mov     rax, [rax+38h]
0x18001859e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185a3  mov     ebx, eax
0x1800185a5  test    eax, eax
0x1800185a7  jns     short loc_1800185C6
0x1800185a9  mov     edx, 0D2h; void *
0x1800185ae  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800185b5  mov     r9d, eax; char *
0x1800185b8  mov     rcx, [rbp+38h]; this
0x1800185bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800185c1  jmp     loc_180018939
0x1800185c6  mov     esi, edi
0x1800185c8  cmp     esi, [rbp+arg_18]
0x1800185cb  jnb     loc_180018775
0x1800185d1  mov     [rbp+var_30], rdi
0x1800185d5  mov     rdi, [rbp+var_8]
0x1800185d9  mov     rax, [rdi]
0x1800185dc  mov     rbx, [rax+30h]
0x1800185e0  lea     rcx, [rbp+var_30]
0x1800185e4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800185e9  lea     r8, [rbp+var_30]
0x1800185ed  mov     edx, esi
0x1800185ef  mov     rcx, rdi
0x1800185f2  mov     rax, rbx
0x1800185f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185fa  mov     ebx, eax
0x1800185fc  test    eax, eax
0x1800185fe  js      loc_18001874E
0x180018604  mov     [rbp+var_20], 0
0x18001860c  mov     rdi, [rbp+var_30]
0x180018610  mov     rax, [rdi]
0x180018613  mov     rbx, [rax+60h]
0x180018617  lea     rcx, [rbp+var_20]
0x18001861b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018620  lea     rdx, [rbp+var_20]
0x180018624  mov     rcx, rdi
0x180018627  mov     rax, rbx
0x18001862a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001862f  mov     ebx, eax
0x180018631  test    eax, eax
0x180018633  js      loc_18001872A
0x180018639  mov     [rbp+var_28], 0
0x180018641  mov     rdi, [rbp+var_20]
0x180018645  mov     rax, [rdi]
0x180018648  mov     rbx, [rax+30h]
0x18001864c  lea     rcx, [rbp+var_28]
0x180018650  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018655  lea     rdx, [rbp+var_28]
0x180018659  mov     rcx, rdi
0x18001865c  mov     rax, rbx
0x18001865f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018664  mov     ebx, eax
0x180018666  xor     edi, edi
0x180018668  test    eax, eax
0x18001866a  js      loc_180018706
0x180018670  mov     [rbp+arg_0], dil
0x180018674  lea     r9, [rbp+arg_0]; bool *
0x180018678  mov     r8, [rbp+var_28]; struct Windows::Security::Credentials::IWebAccountProvider *
0x18001867c  mov     rdx, r15; unsigned __int64
0x18001867f  call    ?IsAssociatedSameUser@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJ_KPEAUIWebAccountProvider@Credentials@Security@5@PEA_N@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::IsAssociatedSameUser(unsigned __int64,Windows::Security::Credentials::IWebAccountProvider *,bool *)
0x180018684  mov     ebx, eax
0x180018686  test    eax, eax
0x180018688  js      short loc_1800186FF
0x18001868a  cmp     [rbp+arg_0], dil
0x18001868e  jnz     short loc_1800186B0
0x180018690  test    r14b, r14b
0x180018693  jnz     short loc_1800186DB
0x180018695  lea     r9, [rbp+arg_0]; bool *
0x180018699  mov     r8, [rbp+var_28]; struct Windows::Security::Credentials::IWebAccountProvider *
0x18001869d  xor     edx, edx; unsigned __int64
0x18001869f  call    ?IsAssociatedSameUser@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJ_KPEAUIWebAccountProvider@Credentials@Security@5@PEA_N@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::IsAssociatedSameUser(unsigned __int64,Windows::Security::Credentials::IWebAccountProvider *,bool *)
0x1800186a4  mov     ebx, eax
0x1800186a6  test    eax, eax
0x1800186a8  js      short loc_1800186D4
0x1800186aa  cmp     [rbp+arg_0], dil
0x1800186ae  jz      short loc_1800186DB
0x1800186b0  lea     rcx, [rbp+var_28]
0x1800186b4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800186b9  nop
0x1800186ba  lea     rcx, [rbp+var_20]
0x1800186be  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800186c3  nop
0x1800186c4  lea     rcx, [rbp+var_30]
0x1800186c8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800186cd  inc     esi
0x1800186cf  jmp     loc_1800185C8
0x1800186d4  mov     edx, 0EBh
0x1800186d9  jmp     short loc_18001870B
0x1800186db  lea     rcx, [rbp+var_28]
0x1800186df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800186e4  nop
0x1800186e5  lea     rcx, [rbp+var_20]
0x1800186e9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800186ee  nop
0x1800186ef  lea     rcx, [rbp+var_30]
0x1800186f3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800186f8  mov     ebx, edi
0x1800186fa  jmp     loc_180018939
0x1800186ff  mov     edx, 0E1h
0x180018704  jmp     short loc_18001870B
0x180018706  mov     edx, 0DDh; void *
0x18001870b  mov     rcx, [rbp+38h]; this
0x18001870f  mov     r9d, eax; char *
0x180018712  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180018719  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001871e  nop
0x18001871f  lea     rcx, [rbp+var_28]
0x180018723  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018728  jmp     short loc_180018743
0x18001872a  mov     rcx, [rbp+38h]; this
0x18001872e  mov     r9d, eax; char *
0x180018731  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180018738  mov     edx, 0DAh; void *
0x18001873d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018742  nop
0x180018743  lea     rcx, [rbp+var_20]
0x180018747  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001874c  jmp     short loc_180018767
0x18001874e  mov     rcx, [rbp+38h]; this
0x180018752  mov     r9d, eax; char *
0x180018755  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18001875c  mov     edx, 0D7h; void *
0x180018761  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018766  nop
0x180018767  lea     rcx, [rbp+var_30]
0x18001876b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018770  jmp     loc_180018939
0x180018775  mov     [rbp+var_38], rdi
0x180018779  mov     rdi, [r13+270h]
0x180018780  mov     rax, [rdi]
0x180018783  mov     rbx, [rax+30h]
0x180018787  lea     rcx, [rbp+var_38]
0x18001878b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018790  lea     rdx, [rbp+var_38]
0x180018794  mov     rcx, rdi
0x180018797  mov     rax, rbx
0x18001879a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001879f  mov     ebx, eax
0x1800187a1  xor     r13d, r13d
0x1800187a4  test    eax, eax
0x1800187a6  jns     short loc_1800187CF
0x1800187a8  mov     edx, 0F6h; void *
0x1800187ad  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800187b4  mov     r9d, eax; char *
0x1800187b7  mov     rcx, [rbp+38h]; this
0x1800187bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800187c0  nop
0x1800187c1  lea     rcx, [rbp+var_38]
0x1800187c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800187ca  jmp     loc_180018939
0x1800187cf  mov     [rbp+var_40], r13d
0x1800187d3  mov     rcx, [rbp+var_38]
0x1800187d7  mov     rax, [rcx]
0x1800187da  lea     rdx, [rbp+var_40]
0x1800187de  mov     rax, [rax+38h]
0x1800187e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187e7  mov     ebx, eax
0x1800187e9  test    eax, eax
0x1800187eb  jns     short loc_1800187F4
0x1800187ed  mov     edx, 0F9h
0x1800187f2  jmp     short loc_1800187AD
0x1800187f4  mov     esi, r13d
0x1800187f7  cmp     esi, [rbp+var_40]
0x1800187fa  jnb     loc_180018928
0x180018800  mov     [rbp+var_10], r13
0x180018804  mov     rdi, [rbp+var_38]
0x180018808  mov     rax, [rdi]
0x18001880b  mov     rbx, [rax+30h]
0x18001880f  lea     rcx, [rbp+var_10]
0x180018813  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018818  lea     r8, [rbp+var_10]
0x18001881c  mov     edx, esi
0x18001881e  mov     rcx, rdi
0x180018821  mov     rax, rbx
0x180018824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018829  mov     ebx, eax
0x18001882b  test    eax, eax
0x18001882d  js      loc_180018901
0x180018833  mov     [rbp+var_18], r13
0x180018837  mov     rdi, [rbp+var_10]
0x18001883b  mov     rax, [rdi]
0x18001883e  mov     rbx, [rax+50h]
0x180018842  lea     rcx, [rbp+var_18]
0x180018846  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001884b  lea     rdx, [rbp+var_18]
0x18001884f  mov     rcx, rdi
0x180018852  mov     rax, rbx
0x180018855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001885a  mov     ebx, eax
0x18001885c  test    eax, eax
0x18001885e  js      short loc_1800188DD
0x180018860  mov     [rbp+arg_0], r13b
0x180018864  lea     r9, [rbp+arg_0]; bool *
0x180018868  mov     r8, [rbp+var_18]; struct Windows::Security::Credentials::IWebAccountProvider *
0x18001886c  mov     rdx, r15; unsigned __int64
0x18001886f  call    ?IsAssociatedSameUser@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJ_KPEAUIWebAccountProvider@Credentials@Security@5@PEA_N@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::IsAssociatedSameUser(unsigned __int64,Windows::Security::Credentials::IWebAccountProvider *,bool *)
0x180018874  mov     ebx, eax
0x180018876  test    eax, eax
0x180018878  js      short loc_1800188D6
0x18001887a  cmp     [rbp+arg_0], r13b
0x18001887e  jnz     short loc_1800188A0
0x180018880  test    r14b, r14b
0x180018883  jnz     short loc_1800188C1
0x180018885  lea     r9, [rbp+arg_0]; bool *
0x180018889  mov     r8, [rbp+var_18]; struct Windows::Security::Credentials::IWebAccountProvider *
0x18001888d  xor     edx, edx; unsigned __int64
0x18001888f  call    ?IsAssociatedSameUser@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJ_KPEAUIWebAccountProvider@Credentials@Security@5@PEA_N@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::IsAssociatedSameUser(unsigned __int64,Windows::Security::Credentials::IWebAccountProvider *,bool *)
0x180018894  mov     ebx, eax
0x180018896  test    eax, eax
0x180018898  js      short loc_1800188BA
0x18001889a  cmp     [rbp+arg_0], r13b
0x18001889e  jz      short loc_1800188C1
0x1800188a0  lea     rcx, [rbp+var_18]
0x1800188a4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800188a9  nop
0x1800188aa  lea     rcx, [rbp+var_10]
0x1800188ae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800188b3  inc     esi
0x1800188b5  jmp     loc_1800187F7
0x1800188ba  mov     edx, 10Fh
0x1800188bf  jmp     short loc_1800188E2
0x1800188c1  lea     rcx, [rbp+var_18]
0x1800188c5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800188ca  nop
0x1800188cb  lea     rcx, [rbp+var_10]
0x1800188cf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800188d4  jmp     short loc_18001892D
0x1800188d6  mov     edx, 104h
0x1800188db  jmp     short loc_1800188E2
0x1800188dd  mov     edx, 101h; void *
0x1800188e2  mov     rcx, [rbp+38h]; this
0x1800188e6  mov     r9d, eax; char *
0x1800188e9  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800188f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800188f5  nop
0x1800188f6  lea     rcx, [rbp+var_18]
0x1800188fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800188ff  jmp     short loc_18001891A
0x180018901  mov     rcx, [rbp+38h]; this
0x180018905  mov     r9d, eax; char *
0x180018908  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18001890f  mov     edx, 0FEh; void *
0x180018914  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018919  nop
0x18001891a  lea     rcx, [rbp+var_10]
0x18001891e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018923  jmp     loc_1800187C1
0x180018928  mov     byte ptr [r12], 1
0x18001892d  lea     rcx, [rbp+var_38]
0x180018931  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018936  mov     ebx, r13d
0x180018939  lea     rcx, [rbp+var_8]
0x18001893d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180018942  mov     eax, ebx
0x180018944  mov     rbx, [rsp+60h+arg_8]
0x18001894c  add     rsp, 60h
0x180018950  pop     r15
0x180018952  pop     r14
0x180018954  pop     r13
0x180018956  pop     r12
0x180018958  pop     rdi
0x180018959  pop     rsi
0x18001895a  pop     rbp
0x18001895b  retn
```
