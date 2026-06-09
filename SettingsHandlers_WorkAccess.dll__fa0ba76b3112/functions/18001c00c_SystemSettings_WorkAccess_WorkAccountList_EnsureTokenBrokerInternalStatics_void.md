# SystemSettings::WorkAccess::WorkAccountList::EnsureTokenBrokerInternalStatics(void)

- ea: `0x18001c00c`
- end: `0x18001c4ae`
- name: `?EnsureTokenBrokerInternalStatics@WorkAccountList@WorkAccess@SystemSettings@@AEAAJXZ`
- size: `1186`
- prototype: `__int64 __fastcall(SystemSettings::WorkAccess::WorkAccountList *__hidden this)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c960`
- `0x18001d274`

## callees

- `0x180002a60`
- `0x1800076ac`
- `0x1800096ec`
- `0x18001197c`
- `0x1800189ec`
- `0x180018a94`
- `0x180018b24`
- `0x180018bb4`
- `0x180018c24`
- `0x180018e3c`
- `0x18001a100`
- `0x18001a11c`
- `0x18001a26c`
- `0x18001a9b0`
- `0x18001aa44`
- `0x18001aa88`
- `0x18001aacc`
- `0x18001c00c`
- `0x180052010`

## string_xrefs

- `0x18001c07d`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001c15b`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001c21e`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001c2e2`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001c3a6`: `shellcommon\shell\settingshandlers\workaccess\lib\workaccountlist.cpp`
- `0x18001c054`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`
- `0x18001c0b0`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall SystemSettings::WorkAccess::WorkAccountList::EnsureTokenBrokerInternalStatics(
        SystemSettings::WorkAccess::WorkAccountList *this)
{
  char *v2; // rbx
  int v3; // eax
  int v4; // ebx
  int v6; // eax
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, char *); // rbx
  __int64 v11; // rax
  __int64 v12; // r14
  __int64 *v13; // rax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, char *); // rbx
  __int64 v16; // rax
  __int64 v17; // r14
  __int64 *v18; // rax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD, char *); // rbx
  __int64 v21; // rax
  __int64 v22; // r14
  __int64 *v23; // rax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, _QWORD, char *); // rbx
  __int64 v26; // rax
  __int64 v27; // r14
  PVOID *v28; // rax
  __int64 v29; // rbx
  int v30[4]; // [rsp+20h] [rbp-79h] BYREF
  __int64 (__fastcall *v31)(SystemSettings::WorkAccess::WorkAccountList *, struct Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *, struct Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *); // [rsp+30h] [rbp-69h] BYREF
  int v32; // [rsp+38h] [rbp-61h] BYREF
  __int64 v33; // [rsp+40h] [rbp-59h] BYREF
  __int64 v34; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v35[8]; // [rsp+50h] [rbp-49h] BYREF
  char v36; // [rsp+58h] [rbp-41h]
  __int64 v37; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v38[8]; // [rsp+68h] [rbp-31h] BYREF
  char v39; // [rsp+70h] [rbp-29h]
  __int64 v40; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v41[8]; // [rsp+80h] [rbp-19h] BYREF
  char v42; // [rsp+88h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-9h] BYREF
  __int64 v44; // [rsp+A8h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v2 = (char *)this + 304;
  if ( !*((_QWORD *)this + 38) )
  {
    v44 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
      0x41u,
      0x40u);
    v3 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(
           v44,
           v2);
    v4 = v3;
    if ( v3 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x216,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)(unsigned int)v3,
        v30[0]);
      return (unsigned int)v4;
    }
  }
  if ( !*((_QWORD *)this + 39) )
  {
    v33 = 0;
    v44 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
      0x41u,
      0x40u);
    v6 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>>(
           v44,
           &v33);
    v4 = v6;
    if ( v6 < 0 )
    {
      v7 = (unsigned int)v6;
      v8 = 541;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)v7,
        v30[0]);
LABEL_27:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
      return (unsigned int)v4;
    }
    v9 = v33;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v33 + 48LL);
    v31 = SystemSettings::WorkAccess::WorkAccountList::OnAccountAdded;
    v32 = 0;
    *(_QWORD *)v30 = this;
    v11 = _lambda_0039e74b727d5a193a763b907f7d4013_::_lambda_0039e74b727d5a193a763b907f7d4013_(
            &hstringHeader,
            v30,
            &v31);
    Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountAddedEventArgs *>,_lambda_71dbe22df9e05443ae9181bee9f1e2dd_>(
      v30,
      v11);
    v12 = *(_QWORD *)v30;
    v4 = v10(v9, *(_QWORD *)v30, (char *)this + 320);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    if ( v4 < 0 )
    {
      v7 = (unsigned int)v4;
      v8 = 542;
      goto LABEL_12;
    }
    v13 = (__int64 *)lambda_b9c4b3a6ec2a670c90e6efe7056662b5_::_lambda_b9c4b3a6ec2a670c90e6efe7056662b5_(
                       &v31,
                       this,
                       &v33);
    v34 = *v13;
    Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>(
      v35,
      v13 + 1);
    v36 = 1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    v14 = v33;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v33 + 64LL);
    v31 = SystemSettings::WorkAccess::WorkAccountList::OnAccountChanged;
    v32 = 0;
    *(_QWORD *)v30 = this;
    v16 = _lambda_0039e74b727d5a193a763b907f7d4013_::_lambda_0039e74b727d5a193a763b907f7d4013_(
            &hstringHeader,
            v30,
            &v31);
    Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountChangedEventArgs *>,_lambda_8cb5cad1601e58da4a0639525ef39568_>(
      v30,
      v16);
    v17 = *(_QWORD *)v30;
    v4 = v15(v14, *(_QWORD *)v30, (char *)this + 328);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x224,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)(unsigned int)v4,
        v30[0]);
LABEL_26:
      wil::details::ScopeExitFn__lambda_b9c4b3a6ec2a670c90e6efe7056662b5___::_ScopeExitFn__lambda_b9c4b3a6ec2a670c90e6efe7056662b5___(&v34);
      goto LABEL_27;
    }
    v18 = (__int64 *)lambda_b9c4b3a6ec2a670c90e6efe7056662b5_::_lambda_b9c4b3a6ec2a670c90e6efe7056662b5_(
                       &v31,
                       this,
                       &v33);
    v37 = *v18;
    Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>(
      v38,
      v18 + 1);
    v39 = 1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    v19 = v33;
    v20 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v33 + 96LL);
    v31 = SystemSettings::WorkAccess::WorkAccountList::OnAccountDeletePending;
    v32 = 0;
    *(_QWORD *)v30 = this;
    v21 = _lambda_0039e74b727d5a193a763b907f7d4013_::_lambda_0039e74b727d5a193a763b907f7d4013_(
            &hstringHeader,
            v30,
            &v31);
    Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *>,_lambda_b69842130674797083d794350c9637e7_>(
      v30,
      v21);
    v22 = *(_QWORD *)v30;
    v4 = v20(v19, *(_QWORD *)v30, (char *)this + 336);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22A,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)(unsigned int)v4,
        v30[0]);
LABEL_25:
      wil::details::ScopeExitFn__lambda_8661696ee35613628e989d669094044b___::_ScopeExitFn__lambda_8661696ee35613628e989d669094044b___(&v37);
      goto LABEL_26;
    }
    v23 = (__int64 *)lambda_b9c4b3a6ec2a670c90e6efe7056662b5_::_lambda_b9c4b3a6ec2a670c90e6efe7056662b5_(
                       &v31,
                       this,
                       &v33);
    v40 = *v23;
    Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>(
      v41,
      v23 + 1);
    v42 = 1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    v24 = v33;
    v25 = *(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v33 + 80LL);
    v31 = SystemSettings::WorkAccess::WorkAccountList::OnAccountDeleted;
    v32 = 0;
    *(_QWORD *)v30 = this;
    v26 = _lambda_0039e74b727d5a193a763b907f7d4013_::_lambda_0039e74b727d5a193a763b907f7d4013_(
            &hstringHeader,
            v30,
            &v31);
    Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletedEventArgs *>,_lambda_0039e74b727d5a193a763b907f7d4013_>(
      v30,
      v26);
    v27 = *(_QWORD *)v30;
    v4 = v25(v24, *(_QWORD *)v30, (char *)this + 344);
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x230,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\workaccountlist.cpp",
        (const char *)(unsigned int)v4,
        v30[0]);
      wil::details::ScopeExitFn__lambda_84662d640e4c581e4628c01eaf4088b6___::_ScopeExitFn__lambda_84662d640e4c581e4628c01eaf4088b6___(&v40);
      goto LABEL_25;
    }
    v28 = (PVOID *)lambda_b9c4b3a6ec2a670c90e6efe7056662b5_::_lambda_b9c4b3a6ec2a670c90e6efe7056662b5_(&v31, this, &v33);
    hstringHeader.Reserved.Reserved1 = *v28;
    Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>(
      &hstringHeader.Reserved.Reserved2[8],
      v28 + 1);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    v29 = v33;
    if ( *((_QWORD *)this + 39) != v33 )
    {
      if ( v33 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
      *(_QWORD *)v30 = *((_QWORD *)this + 39);
      *((_QWORD *)this + 39) = v29;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v30);
    }
    v36 = 0;
    v39 = 0;
    v42 = 0;
    hstringHeader.Reserved.Reserved2[16] = 0;
    wil::details::ScopeExitFn__lambda_b3c48af00f84a260a41742a323e4571d___::_ScopeExitFn__lambda_b3c48af00f84a260a41742a323e4571d___(&hstringHeader);
    wil::details::ScopeExitFn__lambda_84662d640e4c581e4628c01eaf4088b6___::_ScopeExitFn__lambda_84662d640e4c581e4628c01eaf4088b6___(&v40);
    wil::details::ScopeExitFn__lambda_8661696ee35613628e989d669094044b___::_ScopeExitFn__lambda_8661696ee35613628e989d669094044b___(&v37);
    wil::details::ScopeExitFn__lambda_b9c4b3a6ec2a670c90e6efe7056662b5___::_ScopeExitFn__lambda_b9c4b3a6ec2a670c90e6efe7056662b5___(&v34);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  }
  return 0;
}

```

## disassembly

```asm
0x18001c00c  push    rbp
0x18001c00e  push    rbx
0x18001c00f  push    rsi
0x18001c010  push    rdi
0x18001c011  push    r14
0x18001c013  push    r15
0x18001c015  lea     rbp, [rsp-2Fh]
0x18001c01a  sub     rsp, 0C8h
0x18001c021  mov     rax, cs:__security_cookie
0x18001c028  xor     rax, rsp
0x18001c02b  mov     [rbp+57h+var_40], rax
0x18001c02f  mov     rsi, rcx
0x18001c032  lea     rbx, [rcx+130h]
0x18001c039  mov     edi, 40h ; '@'
0x18001c03e  lea     r14d, [rdi+1]
0x18001c042  xor     r15d, r15d
0x18001c045  cmp     [rbx], r15
0x18001c048  jnz     short loc_18001C095
0x18001c04a  mov     [rbp+57h+var_48], r15
0x18001c04e  mov     r9d, edi; unsigned int
0x18001c051  mov     r8d, r14d; unsigned int
0x18001c054  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x18001c05b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001c05f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001c064  mov     rdx, rbx
0x18001c067  mov     rcx, [rbp+57h+var_48]
0x18001c06b  call    ??$GetActivationFactory@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>)
0x18001c070  mov     ebx, eax
0x18001c072  test    eax, eax
0x18001c074  jns     short loc_18001C095
0x18001c076  mov     rcx, [rbp+5Fh]; this
0x18001c07a  mov     r9d, eax; char *
0x18001c07d  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001c084  mov     edx, 216h; void *
0x18001c089  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c08e  mov     eax, ebx
0x18001c090  jmp     loc_18001C491
0x18001c095  cmp     [rsi+138h], r15
0x18001c09c  jnz     loc_18001C48F
0x18001c0a2  mov     [rbp+57h+var_B0], r15
0x18001c0a6  mov     [rbp+57h+var_48], r15
0x18001c0aa  mov     r9d, edi; unsigned int
0x18001c0ad  mov     r8d, r14d; unsigned int
0x18001c0b0  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x18001c0b7  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001c0bb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001c0c0  lea     rdx, [rbp+57h+var_B0]
0x18001c0c4  mov     rcx, [rbp+57h+var_48]
0x18001c0c8  call    ??$ActivateInstance@V?$ComPtr@UITokenBrokerListenerInternal@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UITokenBrokerListenerInternal@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>>)
0x18001c0cd  mov     ebx, eax
0x18001c0cf  test    eax, eax
0x18001c0d1  jns     short loc_18001C0DD
0x18001c0d3  mov     r9d, eax
0x18001c0d6  mov     edx, 21Dh
0x18001c0db  jmp     short loc_18001C15B
0x18001c0dd  mov     rdi, [rbp+57h+var_B0]
0x18001c0e1  mov     rax, [rdi]
0x18001c0e4  mov     rbx, [rax+30h]
0x18001c0e8  lea     rax, ?OnAccountAdded@WorkAccountList@WorkAccess@SystemSettings@@QEAAJPEAUITokenBrokerListenerInternal@Web@Authentication@Security@Internal@Windows@@PEAUIWebAccountAddedEventArgs@56789@@Z; SystemSettings::WorkAccess::WorkAccountList::OnAccountAdded(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountAddedEventArgs *)
0x18001c0ef  mov     [rbp+57h+var_C0], rax
0x18001c0f3  mov     [rbp+57h+var_B8], r15d
0x18001c0f7  mov     eax, [rbp+57h+var_B4]
0x18001c0fa  mov     [rbp+57h+var_B4], eax
0x18001c0fd  mov     qword ptr [rbp+57h+var_D0], rsi
0x18001c101  lea     r8, [rbp+57h+var_C0]
0x18001c105  lea     rdx, [rbp+57h+var_D0]
0x18001c109  lea     rcx, [rbp+57h+hstringHeader]
0x18001c10d  call    ??0_lambda_0039e74b727d5a193a763b907f7d4013_@@QEAA@AEBQEAVWorkAccountList@WorkAccess@SystemSettings@@AEBQ8123@EAAJPEAUITokenBrokerListenerInternal@Web@Authentication@Security@Internal@Windows@@PEAUIWebAccountDeletedEventArgs@56789@@Z@Z; _lambda_0039e74b727d5a193a763b907f7d4013_::_lambda_0039e74b727d5a193a763b907f7d4013_(SystemSettings::WorkAccess::WorkAccountList * const &,long (SystemSettings::WorkAccess::WorkAccountList::*const &)(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletedEventArgs *))
0x18001c112  mov     rdx, rax
0x18001c115  lea     rcx, [rbp+57h+var_D0]
0x18001c119  call    ??$Callback@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountAddedEventArgs@23456@@Foundation@Windows@@V_lambda_71dbe22df9e05443ae9181bee9f1e2dd_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountAddedEventArgs@23456@@Foundation@Windows@@@01@$$QEAV_lambda_71dbe22df9e05443ae9181bee9f1e2dd_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountAddedEventArgs *>,_lambda_71dbe22df9e05443ae9181bee9f1e2dd_>(_lambda_71dbe22df9e05443ae9181bee9f1e2dd_ &&)
0x18001c11e  nop
0x18001c11f  mov     r14, qword ptr [rbp+57h+var_D0]
0x18001c123  lea     r8, [rsi+140h]
0x18001c12a  mov     rdx, r14
0x18001c12d  mov     rcx, rdi
0x18001c130  mov     rax, rbx
0x18001c133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c138  mov     ebx, eax
0x18001c13a  test    r14, r14
0x18001c13d  jz      short loc_18001C14F
0x18001c13f  mov     rdx, [r14]
0x18001c142  mov     rcx, r14
0x18001c145  mov     rax, [rdx+10h]
0x18001c149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c14e  nop
0x18001c14f  test    ebx, ebx
0x18001c151  jns     short loc_18001C170
0x18001c153  mov     r9d, ebx; char *
0x18001c156  mov     edx, 21Eh; void *
0x18001c15b  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001c162  mov     rcx, [rbp+5Fh]; this
0x18001c166  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c16b  jmp     loc_18001C3D6
0x18001c170  lea     r8, [rbp+57h+var_B0]
0x18001c174  mov     rdx, rsi
0x18001c177  lea     rcx, [rbp+57h+var_C0]
0x18001c17b  call    _lambda_b9c4b3a6ec2a670c90e6efe7056662b5____lambda_b9c4b3a6ec2a670c90e6efe7056662b5_
0x18001c180  mov     rcx, [rax]
0x18001c183  mov     [rbp+57h+var_A8], rcx
0x18001c187  lea     rdx, [rax+8]
0x18001c18b  lea     rcx, [rbp+57h+var_A0]
0x18001c18f  call    ??0?$ComPtr@UITokenBrokerListenerInternal@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>(Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal> &&)
0x18001c194  mov     [rbp+57h+var_98], 1
0x18001c198  lea     rcx, [rbp+57h+var_B8]
0x18001c19c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c1a1  mov     rdi, [rbp+57h+var_B0]
0x18001c1a5  mov     rax, [rdi]
0x18001c1a8  mov     rbx, [rax+40h]
0x18001c1ac  lea     rax, ?OnAccountChanged@WorkAccountList@WorkAccess@SystemSettings@@QEAAJPEAUITokenBrokerListenerInternal@Web@Authentication@Security@Internal@Windows@@PEAUIWebAccountChangedEventArgs@56789@@Z; SystemSettings::WorkAccess::WorkAccountList::OnAccountChanged(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountChangedEventArgs *)
0x18001c1b3  mov     [rbp+57h+var_C0], rax
0x18001c1b7  mov     [rbp+57h+var_B8], r15d
0x18001c1bb  mov     eax, [rbp+57h+var_B4]
0x18001c1be  mov     [rbp+57h+var_B4], eax
0x18001c1c1  mov     qword ptr [rbp+57h+var_D0], rsi
0x18001c1c5  lea     r8, [rbp+57h+var_C0]
0x18001c1c9  lea     rdx, [rbp+57h+var_D0]
0x18001c1cd  lea     rcx, [rbp+57h+hstringHeader]
0x18001c1d1  call    ??0_lambda_0039e74b727d5a193a763b907f7d4013_@@QEAA@AEBQEAVWorkAccountList@WorkAccess@SystemSettings@@AEBQ8123@EAAJPEAUITokenBrokerListenerInternal@Web@Authentication@Security@Internal@Windows@@PEAUIWebAccountDeletedEventArgs@56789@@Z@Z; _lambda_0039e74b727d5a193a763b907f7d4013_::_lambda_0039e74b727d5a193a763b907f7d4013_(SystemSettings::WorkAccess::WorkAccountList * const &,long (SystemSettings::WorkAccess::WorkAccountList::*const &)(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletedEventArgs *))
0x18001c1d6  mov     rdx, rax
0x18001c1d9  lea     rcx, [rbp+57h+var_D0]
0x18001c1dd  call    ??$Callback@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountChangedEventArgs@23456@@Foundation@Windows@@V_lambda_8cb5cad1601e58da4a0639525ef39568_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountChangedEventArgs@23456@@Foundation@Windows@@@01@$$QEAV_lambda_8cb5cad1601e58da4a0639525ef39568_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountChangedEventArgs *>,_lambda_8cb5cad1601e58da4a0639525ef39568_>(_lambda_8cb5cad1601e58da4a0639525ef39568_ &&)
0x18001c1e2  nop
0x18001c1e3  mov     r14, qword ptr [rbp+57h+var_D0]
0x18001c1e7  lea     r8, [rsi+148h]
0x18001c1ee  mov     rdx, r14
0x18001c1f1  mov     rcx, rdi
0x18001c1f4  mov     rax, rbx
0x18001c1f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c1fc  mov     ebx, eax
0x18001c1fe  test    r14, r14
0x18001c201  jz      short loc_18001C213
0x18001c203  mov     rdx, [r14]
0x18001c206  mov     rcx, r14
0x18001c209  mov     rax, [rdx+10h]
0x18001c20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c212  nop
0x18001c213  test    ebx, ebx
0x18001c215  jns     short loc_18001C234
0x18001c217  mov     rcx, [rbp+5Fh]; this
0x18001c21b  mov     r9d, ebx; char *
0x18001c21e  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001c225  mov     edx, 224h; void *
0x18001c22a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c22f  jmp     loc_18001C3CC
0x18001c234  lea     r8, [rbp+57h+var_B0]
0x18001c238  mov     rdx, rsi
0x18001c23b  lea     rcx, [rbp+57h+var_C0]
0x18001c23f  call    _lambda_b9c4b3a6ec2a670c90e6efe7056662b5____lambda_b9c4b3a6ec2a670c90e6efe7056662b5_
0x18001c244  mov     rcx, [rax]
0x18001c247  mov     [rbp+57h+var_90], rcx
0x18001c24b  lea     rdx, [rax+8]
0x18001c24f  lea     rcx, [rbp+57h+var_88]
0x18001c253  call    ??0?$ComPtr@UITokenBrokerListenerInternal@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>(Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal> &&)
0x18001c258  mov     [rbp+57h+var_80], 1
0x18001c25c  lea     rcx, [rbp+57h+var_B8]
0x18001c260  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c265  mov     rdi, [rbp+57h+var_B0]
0x18001c269  mov     rax, [rdi]
0x18001c26c  mov     rbx, [rax+60h]
0x18001c270  lea     rax, ?OnAccountDeletePending@WorkAccountList@WorkAccess@SystemSettings@@QEAAJPEAUITokenBrokerListenerInternal@Web@Authentication@Security@Internal@Windows@@PEAUIWebAccountDeletePendingEventArgs@56789@@Z; SystemSettings::WorkAccess::WorkAccountList::OnAccountDeletePending(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletePendingEventArgs *)
0x18001c277  mov     [rbp+57h+var_C0], rax
0x18001c27b  mov     [rbp+57h+var_B8], r15d
0x18001c27f  mov     eax, [rbp+57h+var_B4]
0x18001c282  mov     [rbp+57h+var_B4], eax
0x18001c285  mov     qword ptr [rbp+57h+var_D0], rsi
0x18001c289  lea     r8, [rbp+57h+var_C0]
0x18001c28d  lea     rdx, [rbp+57h+var_D0]
0x18001c291  lea     rcx, [rbp+57h+hstringHeader]
0x18001c295  call    ??0_lambda_0039e74b727d5a193a763b907f7d4013_@@QEAA@AEBQEAVWorkAccountList@WorkAccess@SystemSettings@@AEBQ8123@EAAJPEAUITokenBrokerListenerInternal@Web@Authentication@Security@Internal@Windows@@PEAUIWebAccountDeletedEventArgs@56789@@Z@Z; _lambda_0039e74b727d5a193a763b907f7d4013_::_lambda_0039e74b727d5a193a763b907f7d4013_(SystemSettings::WorkAccess::WorkAccountList * const &,long (SystemSettings::WorkAccess::WorkAccountList::*const &)(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletedEventArgs *))
0x18001c29a  mov     rdx, rax
0x18001c29d  lea     rcx, [rbp+57h+var_D0]
0x18001c2a1  call    ??$Callback@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountDeletePendingEventArgs@23456@@Foundation@Windows@@V_lambda_b69842130674797083d794350c9637e7_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountDeletePendingEventArgs@23456@@Foundation@Windows@@@01@$$QEAV_lambda_b69842130674797083d794350c9637e7_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletePendingEventArgs *>,_lambda_b69842130674797083d794350c9637e7_>(_lambda_b69842130674797083d794350c9637e7_ &&)
0x18001c2a6  nop
0x18001c2a7  mov     r14, qword ptr [rbp+57h+var_D0]
0x18001c2ab  lea     r8, [rsi+150h]
0x18001c2b2  mov     rdx, r14
0x18001c2b5  mov     rcx, rdi
0x18001c2b8  mov     rax, rbx
0x18001c2bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2c0  mov     ebx, eax
0x18001c2c2  test    r14, r14
0x18001c2c5  jz      short loc_18001C2D7
0x18001c2c7  mov     rdx, [r14]
0x18001c2ca  mov     rcx, r14
0x18001c2cd  mov     rax, [rdx+10h]
0x18001c2d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2d6  nop
0x18001c2d7  test    ebx, ebx
0x18001c2d9  jns     short loc_18001C2F8
0x18001c2db  mov     rcx, [rbp+5Fh]; this
0x18001c2df  mov     r9d, ebx; char *
0x18001c2e2  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001c2e9  mov     edx, 22Ah; void *
0x18001c2ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c2f3  jmp     loc_18001C3C2
0x18001c2f8  lea     r8, [rbp+57h+var_B0]
0x18001c2fc  mov     rdx, rsi
0x18001c2ff  lea     rcx, [rbp+57h+var_C0]
0x18001c303  call    _lambda_b9c4b3a6ec2a670c90e6efe7056662b5____lambda_b9c4b3a6ec2a670c90e6efe7056662b5_
0x18001c308  mov     rcx, [rax]
0x18001c30b  mov     [rbp+57h+var_78], rcx
0x18001c30f  lea     rdx, [rax+8]
0x18001c313  lea     rcx, [rbp+57h+var_70]
0x18001c317  call    ??0?$ComPtr@UITokenBrokerListenerInternal@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>(Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal> &&)
0x18001c31c  mov     [rbp+57h+var_68], 1
0x18001c320  lea     rcx, [rbp+57h+var_B8]
0x18001c324  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c329  mov     rdi, [rbp+57h+var_B0]
0x18001c32d  mov     rax, [rdi]
0x18001c330  mov     rbx, [rax+50h]
0x18001c334  lea     rax, ?OnAccountDeleted@WorkAccountList@WorkAccess@SystemSettings@@QEAAJPEAUITokenBrokerListenerInternal@Web@Authentication@Security@Internal@Windows@@PEAUIWebAccountDeletedEventArgs@56789@@Z; SystemSettings::WorkAccess::WorkAccountList::OnAccountDeleted(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletedEventArgs *)
0x18001c33b  mov     [rbp+57h+var_C0], rax
0x18001c33f  mov     [rbp+57h+var_B8], r15d
0x18001c343  mov     eax, [rbp+57h+var_B4]
0x18001c346  mov     [rbp+57h+var_B4], eax
0x18001c349  mov     qword ptr [rbp+57h+var_D0], rsi
0x18001c34d  lea     r8, [rbp+57h+var_C0]
0x18001c351  lea     rdx, [rbp+57h+var_D0]
0x18001c355  lea     rcx, [rbp+57h+hstringHeader]
0x18001c359  call    ??0_lambda_0039e74b727d5a193a763b907f7d4013_@@QEAA@AEBQEAVWorkAccountList@WorkAccess@SystemSettings@@AEBQ8123@EAAJPEAUITokenBrokerListenerInternal@Web@Authentication@Security@Internal@Windows@@PEAUIWebAccountDeletedEventArgs@56789@@Z@Z; _lambda_0039e74b727d5a193a763b907f7d4013_::_lambda_0039e74b727d5a193a763b907f7d4013_(SystemSettings::WorkAccess::WorkAccountList * const &,long (SystemSettings::WorkAccess::WorkAccountList::*const &)(Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal *,Windows::Internal::Security::Authentication::Web::IWebAccountDeletedEventArgs *))
0x18001c35e  mov     rdx, rax
0x18001c361  lea     rcx, [rbp+57h+var_D0]
0x18001c365  call    ??$Callback@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountDeletedEventArgs@23456@@Foundation@Windows@@V_lambda_0039e74b727d5a193a763b907f7d4013_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVTokenBrokerInternal@Web@Authentication@Security@Internal@Windows@@PEAVWebAccountDeletedEventArgs@23456@@Foundation@Windows@@@01@$$QEAV_lambda_0039e74b727d5a193a763b907f7d4013_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::Security::Authentication::Web::TokenBrokerInternal *,Windows::Internal::Security::Authentication::Web::WebAccountDeletedEventArgs *>,_lambda_0039e74b727d5a193a763b907f7d4013_>(_lambda_0039e74b727d5a193a763b907f7d4013_ &&)
0x18001c36a  nop
0x18001c36b  mov     r14, qword ptr [rbp+57h+var_D0]
0x18001c36f  lea     r8, [rsi+158h]
0x18001c376  mov     rdx, r14
0x18001c379  mov     rcx, rdi
0x18001c37c  mov     rax, rbx
0x18001c37f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c384  mov     ebx, eax
0x18001c386  test    r14, r14
0x18001c389  jz      short loc_18001C39B
0x18001c38b  mov     rdx, [r14]
0x18001c38e  mov     rcx, r14
0x18001c391  mov     rax, [rdx+10h]
0x18001c395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c39a  nop
0x18001c39b  test    ebx, ebx
0x18001c39d  jns     short loc_18001C3E4
0x18001c39f  mov     rcx, [rbp+5Fh]; this
0x18001c3a3  mov     r9d, ebx; char *
0x18001c3a6  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\settingshandlers\\w"...
0x18001c3ad  mov     edx, 230h; void *
0x18001c3b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c3b7  nop
0x18001c3b8  lea     rcx, [rbp+57h+var_78]
0x18001c3bc  call    wil__details__ScopeExitFn__lambda_84662d640e4c581e4628c01eaf4088b6______ScopeExitFn__lambda_84662d640e4c581e4628c01eaf4088b6___
0x18001c3c1  nop
0x18001c3c2  lea     rcx, [rbp+57h+var_90]
0x18001c3c6  call    wil__details__ScopeExitFn__lambda_8661696ee35613628e989d669094044b______ScopeExitFn__lambda_8661696ee35613628e989d669094044b___
0x18001c3cb  nop
0x18001c3cc  lea     rcx, [rbp+57h+var_A8]
0x18001c3d0  call    wil__details__ScopeExitFn__lambda_b9c4b3a6ec2a670c90e6efe7056662b5______ScopeExitFn__lambda_b9c4b3a6ec2a670c90e6efe7056662b5___
0x18001c3d5  nop
0x18001c3d6  lea     rcx, [rbp+57h+var_B0]
0x18001c3da  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c3df  jmp     loc_18001C08E
0x18001c3e4  lea     r8, [rbp+57h+var_B0]
0x18001c3e8  mov     rdx, rsi
0x18001c3eb  lea     rcx, [rbp+57h+var_C0]
0x18001c3ef  call    _lambda_b9c4b3a6ec2a670c90e6efe7056662b5____lambda_b9c4b3a6ec2a670c90e6efe7056662b5_
0x18001c3f4  mov     rcx, [rax]
0x18001c3f7  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rcx
0x18001c3fb  lea     rdx, [rax+8]
0x18001c3ff  lea     rcx, [rbp+57h+hstringHeader.Reserved+8]
0x18001c403  call    ??0?$ComPtr@UITokenBrokerListenerInternal@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@QEAA@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal>(Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerListenerInternal> &&)
0x18001c408  lea     rcx, [rbp+57h+var_B8]
0x18001c40c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c411  mov     rbx, [rbp+57h+var_B0]
0x18001c415  cmp     [rsi+138h], rbx
0x18001c41c  jz      short loc_18001C44E
0x18001c41e  test    rbx, rbx
0x18001c421  jz      short loc_18001C433
0x18001c423  mov     rax, [rbx]
0x18001c426  mov     rcx, rbx
0x18001c429  mov     rax, [rax+8]
0x18001c42d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c432  nop
0x18001c433  mov     rax, [rsi+138h]
0x18001c43a  mov     qword ptr [rbp+57h+var_D0], rax
0x18001c43e  mov     [rsi+138h], rbx
0x18001c445  lea     rcx, [rbp+57h+var_D0]
0x18001c449  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c44e  mov     [rbp+57h+var_98], r15b
0x18001c452  mov     [rbp+57h+var_80], r15b
0x18001c456  mov     [rbp+57h+var_68], r15b
0x18001c45a  mov     byte ptr [rbp+57h+hstringHeader.Reserved+10h], r15b
0x18001c45e  lea     rcx, [rbp+57h+hstringHeader]
0x18001c462  call    wil__details__ScopeExitFn__lambda_b3c48af00f84a260a41742a323e4571d______ScopeExitFn__lambda_b3c48af00f84a260a41742a323e4571d___
0x18001c467  nop
0x18001c468  lea     rcx, [rbp+57h+var_78]
0x18001c46c  call    wil__details__ScopeExitFn__lambda_84662d640e4c581e4628c01eaf4088b6______ScopeExitFn__lambda_84662d640e4c581e4628c01eaf4088b6___
0x18001c471  nop
0x18001c472  lea     rcx, [rbp+57h+var_90]
0x18001c476  call    wil__details__ScopeExitFn__lambda_8661696ee35613628e989d669094044b______ScopeExitFn__lambda_8661696ee35613628e989d669094044b___
0x18001c47b  nop
0x18001c47c  lea     rcx, [rbp+57h+var_A8]
0x18001c480  call    wil__details__ScopeExitFn__lambda_b9c4b3a6ec2a670c90e6efe7056662b5______ScopeExitFn__lambda_b9c4b3a6ec2a670c90e6efe7056662b5___
  ... truncated ...
```
