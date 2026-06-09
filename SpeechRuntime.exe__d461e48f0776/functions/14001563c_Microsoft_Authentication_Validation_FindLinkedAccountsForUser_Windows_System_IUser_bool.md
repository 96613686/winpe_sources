# Microsoft::Authentication::Validation::FindLinkedAccountsForUser(Windows::System::IUser *,bool *)

- ea: `0x14001563c`
- end: `0x14001599b`
- name: `?FindLinkedAccountsForUser@Validation@Authentication@Microsoft@@CAJPEAUIUser@System@Windows@@PEA_N@Z`
- size: `863`
- prototype: `__int64 __fastcall(struct Windows::System::IUser *, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400152cc`

## callees

- `0x140002d30`
- `0x14000aab8`
- `0x14000c32c`
- `0x14000e030`
- `0x1400132cc`
- `0x14001360c`
- `0x14001563c`
- `0x1400159a4`
- `0x140031010`

## string_xrefs

- `0x1400156f5`: `onecoreuap\enduser\NUI\OneCore\common\include\EnterpriseAttached.h`
- `0x140015746`: `onecoreuap\enduser\NUI\OneCore\common\include\EnterpriseAttached.h`
- `0x140015796`: `onecoreuap\enduser\NUI\OneCore\common\include\EnterpriseAttached.h`
- `0x140015860`: `onecoreuap\enduser\NUI\OneCore\common\include\EnterpriseAttached.h`
- `0x140015927`: `onecoreuap\enduser\NUI\OneCore\common\include\EnterpriseAttached.h`
- `0x140015680`: `https://login.microsoft.com`
- `0x14001571c`: `Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Microsoft::Authentication::Validation::FindLinkedAccountsForUser(
        struct Windows::System::IUser *a1,
        bool *a2)
{
  int ProviderForUser; // eax
  int AllAccounts; // ebx
  int v6; // eax
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v8)(_QWORD, GUID *, __int64 *); // rdi
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, struct Windows::Security::Credentials::IWebAccountProvider *, __int64, __int64 *); // rbx
  int v12; // eax
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rdi
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64 *); // rbx
  int v21; // [rsp+20h] [rbp-89h]
  __int64 v22; // [rsp+30h] [rbp-79h] BYREF
  __int64 v23; // [rsp+38h] [rbp-71h] BYREF
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-69h] BYREF
  __int64 v25; // [rsp+48h] [rbp-61h] BYREF
  __int64 v26; // [rsp+50h] [rbp-59h] BYREF
  int v27; // [rsp+58h] [rbp-51h] BYREF
  int v28; // [rsp+5Ch] [rbp-4Dh] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v29; // [rsp+60h] [rbp-49h] BYREF
  HSTRING_HEADER v30; // [rsp+68h] [rbp-41h] BYREF
  __int64 v31; // [rsp+80h] [rbp-29h]
  HSTRING_HEADER v32; // [rsp+88h] [rbp-21h] BYREF
  HSTRING v33; // [rsp+A0h] [rbp-9h]
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-1h] BYREF
  HSTRING v35; // [rsp+C0h] [rbp+17h]
  HSTRING_HEADER v36; // [rsp+C8h] [rbp+1Fh] BYREF
  __int64 v37; // [rsp+E0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  *a2 = 0;
  v29 = 0;
  v35 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"https://login.microsoft.com",
    0x1Cu,
    0x1Bu);
  v33 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v32, L"organizations", 0xEu, 0xDu);
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v30,
    L"4bb3f24c-685f-4567-883a-0c050aa439b5",
    0x25u,
    0x24u);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
  ProviderForUser = Microsoft::Authentication::Validation::FindProviderForUser(a1, v35, v33, &v29);
  AllAccounts = ProviderForUser;
  if ( ProviderForUser >= 0 )
  {
    v24 = 0;
    v37 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &v36,
      L"Windows.Security.Authentication.Web.Core.WebAuthenticationCoreManager",
      0x46u,
      0x45u);
    v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(
           v37,
           &v24);
    AllAccounts = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"onecoreuap\\enduser\\NUI\\OneCore\\common\\include\\EnterpriseAttached.h",
        (const char *)(unsigned int)v6,
        v21);
LABEL_25:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
      goto LABEL_26;
    }
    v23 = 0;
    v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v24;
    v8 = **v24;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
    v9 = v8(v7, &GUID_54e633fe_96e0_41e8_9832_1298897c2aaf, &v23);
    AllAccounts = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecoreuap\\enduser\\NUI\\OneCore\\common\\include\\EnterpriseAttached.h",
        (const char *)(unsigned int)v9,
        v21);
LABEL_24:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
      goto LABEL_25;
    }
    v25 = 0;
    v22 = 0;
    v10 = v23;
    v11 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccountProvider *, __int64, __int64 *))(*(_QWORD *)v23 + 56LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
    v12 = v11(v10, v29, v31, &v25);
    AllAccounts = v12;
    if ( v12 < 0 )
    {
      v13 = (unsigned int)v12;
      v14 = 105;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\enduser\\NUI\\OneCore\\common\\include\\EnterpriseAttached.h",
        (const char *)v13,
        v21);
      goto LABEL_23;
    }
    v15 = v25;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
    AllAccounts = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::FindAllAccountsResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::FindAllAccountsResult *>>(v15);
    if ( AllAccounts < 0
      || (AllAccounts = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 64LL))(v15, &v22),
          AllAccounts < 0) )
    {
      v13 = (unsigned int)AllAccounts;
      v14 = 106;
      goto LABEL_22;
    }
    v27 = 0;
    v26 = 0;
    v28 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 56LL))(v22, &v27);
    AllAccounts = v16;
    if ( v16 < 0 )
    {
      v17 = 112;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecoreuap\\enduser\\NUI\\OneCore\\common\\include\\EnterpriseAttached.h",
        (const char *)(unsigned int)v16,
        v21);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
LABEL_23:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
      goto LABEL_24;
    }
    if ( !v27 )
    {
      v18 = v22;
      v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 48LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
      v16 = v19(v18, &v26);
      AllAccounts = v16;
      if ( v16 < 0 )
      {
        v17 = 119;
        goto LABEL_13;
      }
      v16 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v26 + 56LL))(v26, &v28);
      AllAccounts = v16;
      if ( v16 < 0 )
      {
        v17 = 121;
        goto LABEL_13;
      }
      *a2 = v28 != 0;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
    AllAccounts = 0;
    goto LABEL_26;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5B,
    (unsigned int)"onecoreuap\\enduser\\NUI\\OneCore\\common\\include\\EnterpriseAttached.h",
    (const char *)(unsigned int)ProviderForUser,
    v21);
LABEL_26:
  v31 = 0;
  v33 = 0;
  v35 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
  return (unsigned int)AllAccounts;
}

```

## disassembly

```asm
0x14001563c  mov     [rsp-8+arg_10], rbx
0x140015641  mov     [rsp-8+arg_18], rsi
0x140015646  push    rbp
0x140015647  push    rdi
0x140015648  push    r14
0x14001564a  lea     rbp, [rsp-47h]
0x14001564f  sub     rsp, 0F0h
0x140015656  mov     rax, cs:__security_cookie
0x14001565d  xor     rax, rsp
0x140015660  mov     [rbp+57h+var_18], rax
0x140015664  mov     rsi, rdx
0x140015667  mov     rbx, rcx
0x14001566a  xor     r14d, r14d
0x14001566d  mov     [rdx], r14b
0x140015670  mov     [rbp+57h+var_A0], r14
0x140015674  mov     [rbp+57h+var_40], r14
0x140015678  lea     r9d, [r14+1Bh]; unsigned int
0x14001567c  lea     r8d, [r14+1Ch]; unsigned int
0x140015680  lea     rdx, aHttpsLoginMicr; "https://login.microsoft.com"
0x140015687  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x14001568b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140015690  nop
0x140015691  mov     [rbp+57h+var_60], r14
0x140015695  lea     r9d, [r14+0Dh]; unsigned int
0x140015699  lea     r8d, [r14+0Eh]; unsigned int
0x14001569d  lea     rdx, aOrganizations; "organizations"
0x1400156a4  lea     rcx, [rbp+57h+var_78]; hstringHeader
0x1400156a8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400156ad  nop
0x1400156ae  mov     [rbp+57h+var_80], r14
0x1400156b2  lea     r9d, [r14+24h]; unsigned int
0x1400156b6  lea     r8d, [r14+25h]; unsigned int
0x1400156ba  lea     rdx, a4bb3f24c685f45; "4bb3f24c-685f-4567-883a-0c050aa439b5"
0x1400156c1  lea     rcx, [rbp+57h+var_98]; hstringHeader
0x1400156c5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400156ca  nop
0x1400156cb  lea     rcx, [rbp+57h+var_A0]
0x1400156cf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400156d4  lea     r9, [rbp+57h+var_A0]; struct Windows::Security::Credentials::IWebAccountProvider **
0x1400156d8  mov     r8, [rbp+57h+var_60]; HSTRING
0x1400156dc  mov     rdx, [rbp+57h+var_40]; HSTRING
0x1400156e0  mov     rcx, rbx; struct Windows::System::IUser *
0x1400156e3  call    ?FindProviderForUser@Validation@Authentication@Microsoft@@CAJPEAUIUser@System@Windows@@PEAUHSTRING__@@1PEAPEAUIWebAccountProvider@Credentials@Security@6@@Z; Microsoft::Authentication::Validation::FindProviderForUser(Windows::System::IUser *,HSTRING__ *,HSTRING__ *,Windows::Security::Credentials::IWebAccountProvider * *)
0x1400156e8  mov     ebx, eax
0x1400156ea  test    eax, eax
0x1400156ec  jns     short loc_14001570A
0x1400156ee  mov     rcx, [rbp+5Fh]; this
0x1400156f2  mov     r9d, eax; char *
0x1400156f5  lea     r8, aOnecoreuapEndu_59; "onecoreuap\\enduser\\NUI\\OneCore\\comm"...
0x1400156fc  lea     edx, [r14+5Bh]; void *
0x140015700  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015705  jmp     loc_140015960
0x14001570a  mov     [rbp+57h+var_C0], r14
0x14001570e  mov     [rbp+57h+var_20], r14
0x140015712  mov     r9d, 45h ; 'E'; unsigned int
0x140015718  lea     r8d, [r9+1]; unsigned int
0x14001571c  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_Core_WebAuthenticationCoreManager@@3QBGB; "Windows.Security.Authentication.Web.Cor"...
0x140015723  lea     rcx, [rbp+57h+var_38]; hstringHeader
0x140015727  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14001572c  lea     rdx, [rbp+57h+var_C0]
0x140015730  mov     rcx, [rbp+57h+var_20]
0x140015734  call    ??$GetActivationFactory@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIWebAuthenticationCoreManagerStatics@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebAuthenticationCoreManagerStatics>>)
0x140015739  mov     ebx, eax
0x14001573b  test    eax, eax
0x14001573d  jns     short loc_14001575C
0x14001573f  mov     rcx, [rbp+5Fh]; this
0x140015743  mov     r9d, eax; char *
0x140015746  lea     r8, aOnecoreuapEndu_59; "onecoreuap\\enduser\\NUI\\OneCore\\comm"...
0x14001574d  mov     edx, 62h ; 'b'; void *
0x140015752  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015757  jmp     loc_140015956
0x14001575c  mov     [rbp+57h+var_C8], r14
0x140015760  mov     rbx, [rbp+57h+var_C0]
0x140015764  mov     rax, [rbx]
0x140015767  mov     rdi, [rax]
0x14001576a  lea     rcx, [rbp+57h+var_C8]
0x14001576e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140015773  lea     r8, [rbp+57h+var_C8]
0x140015777  lea     rdx, _GUID_54e633fe_96e0_41e8_9832_1298897c2aaf
0x14001577e  mov     rcx, rbx
0x140015781  mov     rax, rdi
0x140015784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015789  mov     ebx, eax
0x14001578b  test    eax, eax
0x14001578d  jns     short loc_1400157AC
0x14001578f  mov     rcx, [rbp+5Fh]; this
0x140015793  mov     r9d, eax; char *
0x140015796  lea     r8, aOnecoreuapEndu_59; "onecoreuap\\enduser\\NUI\\OneCore\\comm"...
0x14001579d  mov     edx, 65h ; 'e'; void *
0x1400157a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400157a7  jmp     loc_14001594C
0x1400157ac  mov     [rbp+57h+var_B8], r14
0x1400157b0  mov     [rbp+57h+var_D0], r14
0x1400157b4  mov     rdi, [rbp+57h+var_C8]
0x1400157b8  mov     rax, [rdi]
0x1400157bb  mov     rbx, [rax+38h]
0x1400157bf  lea     rcx, [rbp+57h+var_B8]
0x1400157c3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400157c8  lea     r9, [rbp+57h+var_B8]
0x1400157cc  mov     r8, [rbp+57h+var_80]
0x1400157d0  mov     rdx, [rbp+57h+var_A0]
0x1400157d4  mov     rcx, rdi
0x1400157d7  mov     rax, rbx
0x1400157da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400157df  mov     ebx, eax
0x1400157e1  test    eax, eax
0x1400157e3  jns     short loc_1400157F2
0x1400157e5  mov     r9d, eax
0x1400157e8  mov     edx, 69h ; 'i'
0x1400157ed  jmp     loc_140015927
0x1400157f2  mov     rdi, [rbp+57h+var_B8]
0x1400157f6  lea     rcx, [rbp+57h+var_D0]
0x1400157fa  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400157ff  mov     rcx, rdi
0x140015802  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVFindAllAccountsResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVFindAllAccountsResult@Core@Web@Authentication@Security@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVFindAllAccountsResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::FindAllAccountsResult *>,Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::FindAllAccountsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::Web::Core::FindAllAccountsResult *> *,tagCOWAIT_FLAGS,void *)
0x140015807  mov     ebx, eax
0x140015809  test    eax, eax
0x14001580b  js      loc_14001591F
0x140015811  mov     rax, [rdi]
0x140015814  lea     rdx, [rbp+57h+var_D0]
0x140015818  mov     rcx, rdi
0x14001581b  mov     rax, [rax+40h]
0x14001581f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015824  mov     ebx, eax
0x140015826  test    eax, eax
0x140015828  js      loc_14001591F
0x14001582e  mov     [rbp+57h+var_A8], r14d
0x140015832  mov     [rbp+57h+var_B0], r14
0x140015836  mov     [rbp+57h+var_A4], r14d
0x14001583a  mov     rcx, [rbp+57h+var_D0]
0x14001583e  mov     rax, [rcx]
0x140015841  lea     rdx, [rbp+57h+var_A8]
0x140015845  mov     rax, [rax+38h]
0x140015849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001584e  mov     ebx, eax
0x140015850  test    eax, eax
0x140015852  jns     short loc_14001587B
0x140015854  mov     edx, 70h ; 'p'; void *
0x140015859  mov     rcx, [rbp+5Fh]; this
0x14001585d  mov     r9d, eax; char *
0x140015860  lea     r8, aOnecoreuapEndu_59; "onecoreuap\\enduser\\NUI\\OneCore\\comm"...
0x140015867  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001586c  nop
0x14001586d  lea     rcx, [rbp+57h+var_B0]
0x140015871  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140015876  jmp     loc_140015938
0x14001587b  cmp     [rbp+57h+var_A8], r14d
0x14001587f  jz      short loc_1400158BA
0x140015881  lea     rcx, [rbp+57h+var_B0]
0x140015885  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001588a  nop
0x14001588b  lea     rcx, [rbp+57h+var_D0]
0x14001588f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140015894  nop
0x140015895  lea     rcx, [rbp+57h+var_B8]
0x140015899  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001589e  nop
0x14001589f  lea     rcx, [rbp+57h+var_C8]
0x1400158a3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400158a8  nop
0x1400158a9  lea     rcx, [rbp+57h+var_C0]
0x1400158ad  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400158b2  mov     ebx, r14d
0x1400158b5  jmp     loc_140015960
0x1400158ba  mov     rdi, [rbp+57h+var_D0]
0x1400158be  mov     rax, [rdi]
0x1400158c1  mov     rbx, [rax+30h]
0x1400158c5  lea     rcx, [rbp+57h+var_B0]
0x1400158c9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1400158ce  lea     rdx, [rbp+57h+var_B0]
0x1400158d2  mov     rcx, rdi
0x1400158d5  mov     rax, rbx
0x1400158d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400158dd  mov     ebx, eax
0x1400158df  test    eax, eax
0x1400158e1  jns     short loc_1400158ED
0x1400158e3  mov     edx, 77h ; 'w'
0x1400158e8  jmp     loc_140015859
0x1400158ed  mov     rcx, [rbp+57h+var_B0]
0x1400158f1  mov     rax, [rcx]
0x1400158f4  lea     rdx, [rbp+57h+var_A4]
0x1400158f8  mov     rax, [rax+38h]
0x1400158fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015901  mov     ebx, eax
0x140015903  test    eax, eax
0x140015905  jns     short loc_140015911
0x140015907  mov     edx, 79h ; 'y'
0x14001590c  jmp     loc_140015859
0x140015911  cmp     [rbp+57h+var_A4], r14d
0x140015915  setnz   al
0x140015918  mov     [rsi], al
0x14001591a  jmp     loc_140015881
0x14001591f  mov     r9d, ebx; char *
0x140015922  mov     edx, 6Ah ; 'j'; void *
0x140015927  lea     r8, aOnecoreuapEndu_59; "onecoreuap\\enduser\\NUI\\OneCore\\comm"...
0x14001592e  mov     rcx, [rbp+5Fh]; this
0x140015932  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140015937  nop
0x140015938  lea     rcx, [rbp+57h+var_D0]
0x14001593c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140015941  nop
0x140015942  lea     rcx, [rbp+57h+var_B8]
0x140015946  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001594b  nop
0x14001594c  lea     rcx, [rbp+57h+var_C8]
0x140015950  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140015955  nop
0x140015956  lea     rcx, [rbp+57h+var_C0]
0x14001595a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x14001595f  nop
0x140015960  mov     [rbp+57h+var_80], r14
0x140015964  mov     [rbp+57h+var_60], r14
0x140015968  mov     [rbp+57h+var_40], r14
0x14001596c  lea     rcx, [rbp+57h+var_A0]
0x140015970  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140015975  mov     eax, ebx
0x140015977  mov     rcx, [rbp+57h+var_18]
0x14001597b  xor     rcx, rsp; StackCookie
0x14001597e  call    __security_check_cookie
0x140015983  lea     r11, [rsp+100h+var_10]
0x14001598b  mov     rbx, [r11+30h]
0x14001598f  mov     rsi, [r11+38h]
0x140015993  mov     rsp, r11
0x140015996  pop     r14
0x140015998  pop     rdi
0x140015999  pop     rbp
0x14001599a  retn
```
