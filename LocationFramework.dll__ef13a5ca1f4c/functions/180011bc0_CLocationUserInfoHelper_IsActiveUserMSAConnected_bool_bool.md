# CLocationUserInfoHelper::IsActiveUserMSAConnected(bool,bool)

- ea: `0x180011bc0`
- end: `0x180011f8f`
- name: `?IsActiveUserMSAConnected@CLocationUserInfoHelper@@UEAAJ_N0@Z`
- size: `975`
- prototype: `__int64 __fastcall(CLocationUserInfoHelper *__hidden this, bool, bool)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180011bc0`
- `0x180011fa0`
- `0x1800122a8`
- `0x180012310`
- `0x18001e170`
- `0x1800a98c0`
- `0x1800c3cf0`
- `0x1800c3ea4`
- `0x1800c4980`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011c74`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011c74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011c5e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180011c5e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011c96`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180011c96`

## string_xrefs

- `0x180011c57`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CLocationUserInfoHelper::IsActiveUserMSAConnected(CLocationUserInfoHelper *this, bool a2, char a3)
{
  int active; // ebx
  HRESULT v5; // eax
  HSTRING v6; // rbx
  void *v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  void *v11; // rdx
  __int64 v12; // rdi
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, struct Windows::Security::Credentials::IWebAccount **); // rbx
  void *v15; // rdx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  __int64 v18; // rdi
  unsigned int i; // esi
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, struct Windows::Security::Credentials::IWebAccount **); // rbx
  void *v22; // rdx
  void *v24; // rdx
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-69h] BYREF
  HSTRING string; // [rsp+48h] [rbp-51h] BYREF
  __int64 v27; // [rsp+50h] [rbp-49h] BYREF
  __int64 v28; // [rsp+58h] [rbp-41h] BYREF
  __int64 v29; // [rsp+60h] [rbp-39h] BYREF
  __int64 v30; // [rsp+68h] [rbp-31h] BYREF
  __int64 v31; // [rsp+70h] [rbp-29h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v32; // [rsp+78h] [rbp-21h] BYREF
  struct Windows::Security::Credentials::IWebAccount *v33; // [rsp+80h] [rbp-19h] BYREF
  void **v34; // [rsp+88h] [rbp-11h] BYREF
  __int128 v35; // [rsp+90h] [rbp-9h]
  __int64 v36; // [rsp+A0h] [rbp+7h]
  unsigned int v37; // [rsp+A8h] [rbp+Fh] BYREF

  v34 = &ATL::CAccessToken::`vftable';
  v35 = 0;
  v36 = 0;
  v27 = 0;
  active = CLocationUserInfoHelper::ImpersonateActiveUser(this, a2, (struct ATL::CAccessToken *)&v34);
  if ( active < 0 )
    goto LABEL_31;
  string = 0;
  v5 = WindowsCreateStringReference(
         L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
         0x40u,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v6 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  active = RoGetActivationFactory(v6, &GUID_07650a66_66ea_489d_aa90_0dabc75f3567, &v27);
  if ( active < 0 )
  {
    ATL::CAccessToken::Revert((ATL::CAccessToken *)&v34, v7);
    v8 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    goto LABEL_31;
  }
  if ( a3 )
  {
    v32 = 0;
    v31 = 0;
    v30 = 0;
    v9 = v27;
    v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 232LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    active = v10(v9, &v30);
    if ( active >= 0 )
    {
      v12 = v30;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
      active = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(v12);
      if ( active >= 0 )
      {
        active = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 64LL))(v12, &v31);
        if ( active >= 0 )
        {
          v13 = v31;
          v14 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccount **))(*(_QWORD *)v31 + 48LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
          active = v14(v13, &v32);
          if ( active >= 0 )
          {
            if ( !v32 )
            {
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
              ATL::CAccessToken::Revert((ATL::CAccessToken *)&v34, v15);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
              active = -2147023579;
LABEL_31:
              v34 = &ATL::CAccessToken::`vftable';
              ATL::CAccessToken::Clear((ATL::CAccessToken *)&v34);
              return (unsigned int)active;
            }
            active = IsMSA(v32);
          }
        }
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
LABEL_30:
    ATL::CAccessToken::Revert((ATL::CAccessToken *)&v34, v11);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    goto LABEL_31;
  }
  v29 = 0;
  v16 = v27;
  v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v27 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  active = v17(v16, &v29);
  if ( active < 0 )
  {
LABEL_29:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    goto LABEL_30;
  }
  v28 = 0;
  v18 = v29;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  active = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(v18);
  if ( active < 0
    || (active = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 64LL))(v18, &v28), active < 0)
    || (v37 = 0,
        active = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v28 + 56LL))(v28, &v37),
        active < 0) )
  {
LABEL_28:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    goto LABEL_29;
  }
  for ( i = 0; i < v37; ++i )
  {
    v33 = 0;
    v20 = v28;
    v21 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Security::Credentials::IWebAccount **))(*(_QWORD *)v28 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    active = v21(v20, i, &v33);
    if ( active < 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
      goto LABEL_28;
    }
    if ( (int)IsMSA(v33) >= 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
      ATL::CAccessToken::Revert((ATL::CAccessToken *)&v34, v22);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
      active = 0;
      goto LABEL_31;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  ATL::CAccessToken::Revert((ATL::CAccessToken *)&v34, v24);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  v34 = &ATL::CAccessToken::`vftable';
  ATL::CAccessToken::Clear((ATL::CAccessToken *)&v34);
  return 2147943568LL;
}

```

## disassembly

```asm
0x180011bc0  push    rbp
0x180011bc2  push    rbx
0x180011bc3  push    rsi
0x180011bc4  push    rdi
0x180011bc5  push    r14
0x180011bc7  push    r15
0x180011bc9  lea     rbp, [rsp-2Fh]
0x180011bce  sub     rsp, 0C8h
0x180011bd5  mov     rax, cs:__security_cookie
0x180011bdc  xor     rax, rsp
0x180011bdf  mov     [rbp+57h+var_40], rax
0x180011be3  mov     dil, r8b
0x180011be6  xorps   xmm0, xmm0
0x180011be9  movups  [rbp+57h+var_68], xmm0
0x180011bed  movups  [rbp+57h+var_58], xmm0
0x180011bf1  lea     r15, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x180011bf8  mov     qword ptr [rbp+57h+var_68], r15
0x180011bfc  movdqu  [rbp+57h+var_68+8], xmm0
0x180011c01  xor     r14d, r14d
0x180011c04  mov     qword ptr [rbp+57h+var_58+8], r14
0x180011c08  mov     [rbp+57h+var_A0], r14
0x180011c0c  lea     r8, [rbp+57h+var_68]; struct ATL::CAccessToken *
0x180011c10  call    ?ImpersonateActiveUser@CLocationUserInfoHelper@@UEAAJ_NAEAVCAccessToken@ATL@@@Z; CLocationUserInfoHelper::ImpersonateActiveUser(bool,ATL::CAccessToken &)
0x180011c15  mov     ebx, eax
0x180011c17  test    eax, eax
0x180011c19  jns     short loc_180011C3A
0x180011c1b  mov     rcx, [rbp+57h+var_A0]
0x180011c1f  test    rcx, rcx
0x180011c22  jz      short loc_180011C35
0x180011c24  mov     [rbp+57h+var_A0], r14
0x180011c28  mov     rdx, [rcx]
0x180011c2b  mov     rax, [rdx+10h]
0x180011c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c34  nop
0x180011c35  jmp     loc_180011F28
0x180011c3a  lea     rax, [rbp+57h+var_68]
0x180011c3e  mov     [rbp+57h+var_D0], rax
0x180011c42  mov     [rbp+57h+var_C8], 1
0x180011c46  mov     [rbp+57h+string], r14
0x180011c4a  lea     r9, [rbp+57h+string]; string
0x180011c4e  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180011c52  mov     edx, 40h ; '@'; length
0x180011c57  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x180011c5e  call    cs:__imp_WindowsCreateStringReference
0x180011c64  test    eax, eax
0x180011c66  jns     short loc_180011C7B
0x180011c68  xor     r9d, r9d; lpArguments
0x180011c6b  xor     r8d, r8d; nNumberOfArguments
0x180011c6e  lea     edx, [r9+1]; dwExceptionFlags
0x180011c72  mov     ecx, eax; dwExceptionCode
0x180011c74  call    cs:__imp_RaiseException
0x180011c7a  int     3; Trap to Debugger
0x180011c7b  mov     rbx, [rbp+57h+string]
0x180011c7f  lea     rcx, [rbp+57h+var_A0]
0x180011c83  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011c88  lea     r8, [rbp+57h+var_A0]
0x180011c8c  lea     rdx, _GUID_07650a66_66ea_489d_aa90_0dabc75f3567
0x180011c93  mov     rcx, rbx
0x180011c96  call    cs:__imp_RoGetActivationFactory
0x180011c9c  mov     ebx, eax
0x180011c9e  test    eax, eax
0x180011ca0  jns     short loc_180011CCB
0x180011ca2  lea     rcx, [rbp+57h+var_68]; this
0x180011ca6  call    ?Revert@CAccessToken@ATL@@QEBA_NPEAX@Z; ATL::CAccessToken::Revert(void *)
0x180011cab  nop
0x180011cac  mov     rcx, [rbp+57h+var_A0]
0x180011cb0  test    rcx, rcx
0x180011cb3  jz      short loc_180011CC6
0x180011cb5  mov     [rbp+57h+var_A0], r14
0x180011cb9  mov     rax, [rcx]
0x180011cbc  mov     rax, [rax+10h]
0x180011cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cc5  nop
0x180011cc6  jmp     loc_180011F28
0x180011ccb  test    dil, dil
0x180011cce  jz      loc_180011DDB
0x180011cd4  mov     [rbp+57h+var_78], r14
0x180011cd8  mov     [rbp+57h+var_80], r14
0x180011cdc  mov     [rbp+57h+var_88], r14
0x180011ce0  mov     rdi, [rbp+57h+var_A0]
0x180011ce4  mov     rax, [rdi]
0x180011ce7  mov     rbx, [rax+0E8h]
0x180011cee  lea     rcx, [rbp+57h+var_88]
0x180011cf2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011cf7  lea     rdx, [rbp+57h+var_88]
0x180011cfb  mov     rcx, rdi
0x180011cfe  mov     rax, rbx
0x180011d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d06  mov     ebx, eax
0x180011d08  test    eax, eax
0x180011d0a  jns     short loc_180011D2E
0x180011d0c  lea     rcx, [rbp+57h+var_88]
0x180011d10  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011d15  nop
0x180011d16  lea     rcx, [rbp+57h+var_80]
0x180011d1a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011d1f  nop
0x180011d20  lea     rcx, [rbp+57h+var_78]
0x180011d24  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011d29  jmp     loc_180011F14
0x180011d2e  mov     rdi, [rbp+57h+var_88]
0x180011d32  lea     rcx, [rbp+57h+var_80]
0x180011d36  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011d3b  mov     rcx, rdi
0x180011d3e  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>>(Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *,tagCOWAIT_FLAGS,void *)
0x180011d43  mov     ebx, eax
0x180011d45  test    eax, eax
0x180011d47  js      short loc_180011D0C
0x180011d49  mov     rax, [rdi]
0x180011d4c  lea     rdx, [rbp+57h+var_80]
0x180011d50  mov     rcx, rdi
0x180011d53  mov     rax, [rax+40h]
0x180011d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d5c  mov     ebx, eax
0x180011d5e  test    eax, eax
0x180011d60  js      short loc_180011D0C
0x180011d62  mov     rdi, [rbp+57h+var_80]
0x180011d66  mov     rax, [rdi]
0x180011d69  mov     rbx, [rax+30h]
0x180011d6d  lea     rcx, [rbp+57h+var_78]
0x180011d71  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011d76  lea     rdx, [rbp+57h+var_78]
0x180011d7a  mov     rcx, rdi
0x180011d7d  mov     rax, rbx
0x180011d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d85  mov     ebx, eax
0x180011d87  test    eax, eax
0x180011d89  js      short loc_180011D0C
0x180011d8b  mov     rcx, [rbp+57h+var_78]; struct Windows::Security::Credentials::IWebAccount *
0x180011d8f  test    rcx, rcx
0x180011d92  jnz     short loc_180011DCF
0x180011d94  lea     rcx, [rbp+57h+var_88]
0x180011d98  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011d9d  nop
0x180011d9e  lea     rcx, [rbp+57h+var_80]
0x180011da2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011da7  nop
0x180011da8  lea     rcx, [rbp+57h+var_78]
0x180011dac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011db1  nop
0x180011db2  lea     rcx, [rbp+57h+var_68]; this
0x180011db6  call    ?Revert@CAccessToken@ATL@@QEBA_NPEAX@Z; ATL::CAccessToken::Revert(void *)
0x180011dbb  nop
0x180011dbc  lea     rcx, [rbp+57h+var_A0]
0x180011dc0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011dc5  mov     ebx, 80070525h
0x180011dca  jmp     loc_180011F28
0x180011dcf  call    ?IsMSA@@YAJPEAUIWebAccount@Credentials@Security@Windows@@@Z; IsMSA(Windows::Security::Credentials::IWebAccount *)
0x180011dd4  mov     ebx, eax
0x180011dd6  jmp     loc_180011D0C
0x180011ddb  mov     [rbp+57h+var_90], r14
0x180011ddf  mov     rdi, [rbp+57h+var_A0]
0x180011de3  mov     rax, [rdi]
0x180011de6  mov     rbx, [rax+60h]
0x180011dea  lea     rcx, [rbp+57h+var_90]
0x180011dee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011df3  lea     rdx, [rbp+57h+var_90]
0x180011df7  mov     rcx, rdi
0x180011dfa  mov     rax, rbx
0x180011dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e02  mov     ebx, eax
0x180011e04  test    eax, eax
0x180011e06  js      loc_180011F0A
0x180011e0c  mov     [rbp+57h+var_98], r14
0x180011e10  mov     rdi, [rbp+57h+var_90]
0x180011e14  lea     rcx, [rbp+57h+var_98]
0x180011e18  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011e1d  mov     rcx, rdi
0x180011e20  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>,Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *>>(Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *> *,tagCOWAIT_FLAGS,void *)
0x180011e25  mov     ebx, eax
0x180011e27  test    eax, eax
0x180011e29  js      loc_180011F00
0x180011e2f  mov     rax, [rdi]
0x180011e32  lea     rdx, [rbp+57h+var_98]
0x180011e36  mov     rcx, rdi
0x180011e39  mov     rax, [rax+40h]
0x180011e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e42  mov     ebx, eax
0x180011e44  test    eax, eax
0x180011e46  js      loc_180011F00
0x180011e4c  mov     [rbp+57h+var_48], r14d
0x180011e50  mov     rcx, [rbp+57h+var_98]
0x180011e54  mov     rax, [rcx]
0x180011e57  lea     rdx, [rbp+57h+var_48]
0x180011e5b  mov     rax, [rax+38h]
0x180011e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e64  mov     ebx, eax
0x180011e66  test    eax, eax
0x180011e68  js      loc_180011F00
0x180011e6e  mov     esi, r14d
0x180011e71  cmp     esi, [rbp+57h+var_48]
0x180011e74  jnb     loc_180011F53
0x180011e7a  mov     [rbp+57h+var_70], r14
0x180011e7e  mov     rdi, [rbp+57h+var_98]
0x180011e82  mov     rax, [rdi]
0x180011e85  mov     rbx, [rax+30h]
0x180011e89  lea     rcx, [rbp+57h+var_70]
0x180011e8d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011e92  lea     r8, [rbp+57h+var_70]
0x180011e96  mov     edx, esi
0x180011e98  mov     rcx, rdi
0x180011e9b  mov     rax, rbx
0x180011e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ea3  mov     ebx, eax
0x180011ea5  test    eax, eax
0x180011ea7  js      short loc_180011EF6
0x180011ea9  mov     rcx, [rbp+57h+var_70]; struct Windows::Security::Credentials::IWebAccount *
0x180011ead  call    ?IsMSA@@YAJPEAUIWebAccount@Credentials@Security@Windows@@@Z; IsMSA(Windows::Security::Credentials::IWebAccount *)
0x180011eb2  nop
0x180011eb3  lea     rcx, [rbp+57h+var_70]
0x180011eb7  test    eax, eax
0x180011eb9  jns     short loc_180011EC4
0x180011ebb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011ec0  inc     esi
0x180011ec2  jmp     short loc_180011E71
0x180011ec4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011ec9  nop
0x180011eca  lea     rcx, [rbp+57h+var_98]
0x180011ece  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011ed3  nop
0x180011ed4  lea     rcx, [rbp+57h+var_90]
0x180011ed8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011edd  nop
0x180011ede  lea     rcx, [rbp+57h+var_68]; this
0x180011ee2  call    ?Revert@CAccessToken@ATL@@QEBA_NPEAX@Z; ATL::CAccessToken::Revert(void *)
0x180011ee7  nop
0x180011ee8  lea     rcx, [rbp+57h+var_A0]
0x180011eec  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011ef1  mov     ebx, r14d
0x180011ef4  jmp     short loc_180011F28
0x180011ef6  lea     rcx, [rbp+57h+var_70]
0x180011efa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011eff  nop
0x180011f00  lea     rcx, [rbp+57h+var_98]
0x180011f04  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011f09  nop
0x180011f0a  lea     rcx, [rbp+57h+var_90]
0x180011f0e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011f13  nop
0x180011f14  lea     rcx, [rbp+57h+var_68]; this
0x180011f18  call    ?Revert@CAccessToken@ATL@@QEBA_NPEAX@Z; ATL::CAccessToken::Revert(void *)
0x180011f1d  nop
0x180011f1e  lea     rcx, [rbp+57h+var_A0]
0x180011f22  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011f27  nop
0x180011f28  mov     qword ptr [rbp+57h+var_68], r15
0x180011f2c  lea     rcx, [rbp+57h+var_68]; this
0x180011f30  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180011f35  mov     eax, ebx
0x180011f37  mov     rcx, [rbp+57h+var_40]
0x180011f3b  xor     rcx, rsp; StackCookie
0x180011f3e  call    __security_check_cookie
0x180011f43  add     rsp, 0C8h
0x180011f4a  pop     r15
0x180011f4c  pop     r14
0x180011f4e  pop     rdi
0x180011f4f  pop     rsi
0x180011f50  pop     rbx
0x180011f51  pop     rbp
0x180011f52  retn
0x180011f53  lea     rcx, [rbp+57h+var_98]
0x180011f57  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011f5c  nop
0x180011f5d  lea     rcx, [rbp+57h+var_90]
0x180011f61  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011f66  nop
0x180011f67  lea     rcx, [rbp+57h+var_68]; this
0x180011f6b  call    ?Revert@CAccessToken@ATL@@QEBA_NPEAX@Z; ATL::CAccessToken::Revert(void *)
0x180011f70  nop
0x180011f71  lea     rcx, [rbp+57h+var_A0]
0x180011f75  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011f7a  nop
0x180011f7b  mov     qword ptr [rbp+57h+var_68], r15
0x180011f7f  lea     rcx, [rbp+57h+var_68]; this
0x180011f83  call    ?Clear@CAccessToken@ATL@@MEAAXXZ; ATL::CAccessToken::Clear(void)
0x180011f88  mov     eax, 80070490h
0x180011f8d  jmp     short loc_180011F37
```
