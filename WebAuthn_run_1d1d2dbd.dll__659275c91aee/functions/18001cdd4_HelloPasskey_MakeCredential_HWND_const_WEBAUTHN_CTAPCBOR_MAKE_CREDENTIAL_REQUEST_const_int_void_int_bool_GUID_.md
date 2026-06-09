# HelloPasskey::MakeCredential(HWND__ * const,_WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST const *,int,void *,int,bool,_GUID,uchar const *,ulong,uchar * *,ulong *,NgcPasskeys::WebAuthnCredentialAttestation &)

- ea: `0x18001cdd4`
- end: `0x18001d25b`
- name: `?MakeCredential@HelloPasskey@@YAJQEAUHWND__@@PEBU_WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST@@HPEAXH_NU_GUID@@PEBEKPEAPEAEPEAKAEAUWebAuthnCredentialAttestation@NgcPasskeys@@@Z`
- size: `1159`
- prototype: `__int64 __fastcall(HelloPasskey *__hidden this, HWND, const struct _WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST *, int, void *, char, bool, struct _GUID *, const unsigned __int8 *, unsigned int, unsigned __int8 **, unsigned int *, struct NgcPasskeys::WebAuthnCredentialAttestation *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003298c`

## callees

- `0x18001687c`
- `0x18001cd78`
- `0x18001cdd4`
- `0x18001d5fc`
- `0x18001ee7c`
- `0x1800205e4`
- `0x180023bc8`
- `0x180032964`
- `0x1800350b4`
- `0x180036da4`
- `0x180037ed8`
- `0x180037f6c`
- `0x180038e80`
- `0x180047464`
- `0x180062fcc`
- `0x18006f750`
- `0x18007d244`
- `0x18007d358`
- `0x18007d3a4`
- `0x18007da80`
- `0x1800c067c`
- `0x1800c091c`
- `0x1800c70c8`
- `0x1801354ec`
- `0x180139d80`
- `0x18013c090`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ced5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d10b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d230`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ced5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d10b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d230`
- `ntdll!RtlPublishWnfStateData` at `0x18001d1eb`
- `ntdll!RtlPublishWnfStateData` at `0x18001d1eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d0c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d19e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d0c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d19e`

## string_xrefs

- `0x18001ceb2`: `onecore\ds\security\fido\webauthn\dll\webauthnpasskeys.cpp`
- `0x18001d0a3`: `onecore\ds\security\fido\webauthn\dll\webauthnpasskeys.cpp`
- `0x18001d202`: `onecore\ds\security\fido\webauthn\dll\webauthnpasskeys.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall HelloPasskey::MakeCredential(
        HelloPasskey *this,
        struct _WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST *a2,
        const struct _WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST *a3,
        __int64 a4,
        void *a5,
        char a6,
        __int64 a7,
        struct _GUID *a8,
        const unsigned __int8 *a9,
        __int64 a10,
        unsigned __int8 **a11,
        unsigned int *a12)
{
  unsigned int CredentialRequest2; // ebx
  int v16; // eax
  unsigned int v17; // ebx
  HLOCAL v18; // rcx
  __int64 *v20; // rbx
  __int64 v21; // r9
  __int64 v22; // rax
  __int64 v23; // r8
  __int64 PasskeyFooter; // rax
  __int64 v25; // rax
  _QWORD *v26; // r8
  int v27; // edi
  void *v28; // rcx
  HLOCAL v29; // rcx
  char *v30; // rdi
  void *v31; // rcx
  int v32; // eax
  HLOCAL v33; // rcx
  int v34; // [rsp+20h] [rbp-F0h]
  int v35; // [rsp+20h] [rbp-F0h]
  unsigned int v36; // [rsp+90h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp-78h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-70h] BYREF
  int v39; // [rsp+A8h] [rbp-68h]
  __int64 *v40; // [rsp+B0h] [rbp-60h] BYREF
  HLOCAL *p_hMem; // [rsp+B8h] [rbp-58h] BYREF
  __int64 v42; // [rsp+C0h] [rbp-50h] BYREF
  char v43; // [rsp+C8h] [rbp-48h]
  __int128 v44; // [rsp+D0h] [rbp-40h] BYREF
  __int128 v45; // [rsp+E0h] [rbp-30h] BYREF
  unsigned __int8 **v46; // [rsp+F0h] [rbp-20h]
  __int64 v47; // [rsp+F8h] [rbp-18h]
  __int64 v48; // [rsp+100h] [rbp-10h] BYREF
  __int64 v49; // [rsp+118h] [rbp+8h] BYREF
  __int64 v50; // [rsp+120h] [rbp+10h]
  _QWORD v51[4]; // [rsp+130h] [rbp+20h] BYREF
  __int128 v52; // [rsp+150h] [rbp+40h] BYREF
  __int128 v53; // [rsp+160h] [rbp+50h] BYREF
  _BYTE v54[16]; // [rsp+170h] [rbp+60h] BYREF
  _QWORD v55[4]; // [rsp+180h] [rbp+70h] BYREF
  char v56[96]; // [rsp+1A0h] [rbp+90h] BYREF
  _BYTE v57[96]; // [rsp+200h] [rbp+F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1A8h]

  *(_QWORD *)&v44 = a7;
  *(_QWORD *)&v45 = a8;
  v47 = a10;
  v46 = a11;
  v39 = 0;
  hMem = 0;
  p_hMem = &hMem;
  v42 = 0;
  v43 = 1;
  CredentialRequest2 = CtapCborEncodeMakeCredentialRequest2(a2, (__int64)&v42, 0);
  wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( CredentialRequest2 )
  {
    v16 = CtapCborErrorToWin32Error(CredentialRequest2);
    v17 = v16;
    if ( v16 > 0 )
      v17 = (unsigned __int16)v16 | 0x80070000;
    if ( (v17 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnpasskeys.cpp",
        (const char *)v17,
        v34);
    v18 = hMem;
    hMem = 0;
    if ( v18 )
      LocalFree(v18);
    return v17;
  }
  else
  {
    winrt::create_instance<ISyncedPasskeyAuthenticator>(&v40, &winrt::impl::guid_v<SyncedPasskeyAuthenticator>);
    v20 = v40;
    WebAuthNCom::AllowImpersonationCom(v40);
    v44 = *(_OWORD *)v44;
    (*(void (__fastcall **)(__int64 *, __int128 *))(*v20 + 64))(v20, &v44);
    wil::impersonate_token(&v44, a4);
    v52 = *(_OWORD *)wil::basic_zstring_view<unsigned short>::basic_zstring_view<unsigned short>(
                       v54,
                       *((_QWORD *)a2 + 4) + 8LL);
    v53 = *(_OWORD *)wil::basic_zstring_view<unsigned short>::basic_zstring_view<unsigned short>(
                       &p_hMem,
                       *((_QWORD *)a2 + 5) + 16LL);
    v22 = WebAuthNUI::CreatePasskeyHeader(v56, &v53, &v52, v21);
    NgcUtils::CredUiAdditionalInfo::Serialize(v22, &v49);
    NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo((NgcUtils::CredUiAdditionalInfo *)v56);
    LOBYTE(v23) = a6;
    PasskeyFooter = WebAuthNUI::CreatePasskeyFooter(v57, 1250, v23, 112);
    NgcUtils::CredUiAdditionalInfo::Serialize(PasskeyFooter, &v48);
    NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo((NgcUtils::CredUiAdditionalInfo *)v57);
    WebAuthNUI::FormatResourceString<>(v55, 1036);
    pv = 0;
    v36 = 0;
    v25 = *v20;
    p_hMem = &pv;
    v42 = 0;
    v43 = 1;
    v26 = v55;
    if ( v55[3] > 7u )
      v26 = (_QWORD *)v55[0];
    v35 = v50 - v49;
    v27 = (*(__int64 (__fastcall **)(__int64 *, HelloPasskey *, _QWORD *))(v25 + 32))(v20, this, v26);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_hMem);
    if ( v27 >= 0 )
    {
      std::vector<unsigned char>::vector<unsigned char>(v51, pv, (char *)pv + v36);
      *(_QWORD *)&v45 = v51[0];
      *((_QWORD *)&v45 + 1) = v51[1] - v51[0];
      v30 = NgcPasskeys::WebAuthnCredentialAttestation::FromCbor(v56, &v45);
      *(_QWORD *)a12 = *(_QWORD *)v30;
      a12[2] = *((_DWORD *)v30 + 2);
      std::wstring::operator=(a12 + 4, v30 + 16);
      std::vector<unsigned char>::operator=(a12 + 12, v30 + 48);
      NgcPasskeys::WebAuthnCredentialAttestation::~WebAuthnCredentialAttestation((NgcPasskeys::WebAuthnCredentialAttestation *)v56);
      std::vector<unsigned char>::_Tidy(v51);
      v31 = pv;
      pv = 0;
      if ( v31 )
        CoTaskMemFree(v31);
      std::wstring::_Tidy_deallocate(v55);
      std::vector<unsigned char>::_Tidy(&v48);
      std::vector<unsigned char>::_Tidy(&v49);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v44);
      v36 = 2;
      v32 = RtlPublishWnfStateData(WNF_WEBA_PASSKEY_INFO_CHANGED, 0, &v36, 4) | 0x10000000;
      if ( v32 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x3D,
          (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnpasskeys.cpp",
          (const char *)(unsigned int)v32,
          0);
      if ( v20 )
        winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(&v40);
      v33 = hMem;
      hMem = 0;
      if ( v33 )
        LocalFree(v33);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36,
        (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnpasskeys.cpp",
        (const char *)(unsigned int)v27,
        v35);
      v28 = pv;
      pv = 0;
      if ( v28 )
        CoTaskMemFree(v28);
      std::wstring::_Tidy_deallocate(v55);
      std::vector<unsigned char>::_Tidy(&v48);
      std::vector<unsigned char>::_Tidy(&v49);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v44);
      if ( v20 )
        winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(&v40);
      v29 = hMem;
      hMem = 0;
      if ( v29 )
        LocalFree(v29);
      return (unsigned int)v27;
    }
  }
}

```

## disassembly

```asm
0x18001cdd4  push    rbp
0x18001cdd6  push    rbx
0x18001cdd7  push    rsi
0x18001cdd8  push    rdi
0x18001cdd9  push    r12
0x18001cddb  push    r13
0x18001cddd  push    r14
0x18001cddf  push    r15
0x18001cde1  lea     rbp, [rsp-168h]
0x18001cde9  sub     rsp, 278h
0x18001cdf0  mov     rax, cs:__security_cookie
0x18001cdf7  xor     rax, rsp
0x18001cdfa  mov     [rbp+1A0h+var_50], rax
0x18001ce01  mov     rsi, r9
0x18001ce04  mov     r13d, r8d
0x18001ce07  mov     rdi, rdx
0x18001ce0a  mov     r12, rcx
0x18001ce0d  mov     r15, [rbp+1A0h+arg_58]
0x18001ce14  mov     r14b, [rbp+1A0h+arg_28]
0x18001ce1b  mov     rax, [rbp+1A0h+arg_30]
0x18001ce22  mov     qword ptr [rbp+1A0h+var_1E0], rax
0x18001ce26  mov     rax, [rbp+1A0h+arg_38]
0x18001ce2d  mov     [rbp+1A0h+var_1D0], rax
0x18001ce31  mov     rax, [rbp+1A0h+arg_48]
0x18001ce38  mov     [rbp+1A0h+var_1B8], rax
0x18001ce3c  mov     rax, [rbp+1A0h+arg_50]
0x18001ce43  mov     [rbp+1A0h+var_1C0], rax
0x18001ce47  xor     ecx, ecx
0x18001ce49  mov     [rbp+1A0h+var_208], ecx
0x18001ce4c  mov     [rbp+1A0h+hMem], rcx
0x18001ce50  lea     rax, [rbp+1A0h+hMem]
0x18001ce54  mov     [rbp+1A0h+var_1F8], rax
0x18001ce58  mov     [rbp+1A0h+var_1F0], rcx
0x18001ce5c  mov     [rbp+1A0h+var_1E8], 1
0x18001ce60  mov     [rsp+2B0h+var_288], rcx; __int64
0x18001ce65  lea     rax, [rbp+1A0h+var_1F0]
0x18001ce69  mov     [rsp+2B0h+var_290], rax; int
0x18001ce6e  lea     r9, [rbp+1A0h+var_208]
0x18001ce72  xor     r8d, r8d
0x18001ce75  xor     edx, edx
0x18001ce77  mov     rcx, rdi; struct _WEBAUTHN_CTAPCBOR_MAKE_CREDENTIAL_REQUEST *
0x18001ce7a  call    CtapCborEncodeMakeCredentialRequest2
0x18001ce7f  mov     ebx, eax
0x18001ce81  lea     rcx, [rbp+1A0h+var_1F8]
0x18001ce85  call    ??1?$out_param_t@V?$unique_ptr@U_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<_CTAPCBOR_DEVICE_RESPONSE_INFO_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18001ce8a  test    ebx, ebx
0x18001ce8c  jz      short loc_18001CEE2
0x18001ce8e  mov     ecx, ebx
0x18001ce90  call    CtapCborErrorToWin32Error
0x18001ce95  mov     ebx, eax
0x18001ce97  test    eax, eax
0x18001ce99  jle     short loc_18001CEA4
0x18001ce9b  movzx   ebx, ax
0x18001ce9e  or      ebx, 80070000h
0x18001cea4  test    ebx, ebx
0x18001cea6  jns     short loc_18001CEC4
0x18001cea8  mov     rcx, [rbp+1A8h]; this
0x18001ceaf  mov     r9d, ebx; char *
0x18001ceb2  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18001ceb9  mov     edx, 1Ch; void *
0x18001cebe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cec3  nop
0x18001cec4  mov     rcx, [rbp+1A0h+hMem]; hMem
0x18001cec8  mov     [rbp+1A0h+hMem], 0
0x18001ced0  test    rcx, rcx
0x18001ced3  jz      short loc_18001CEDB
0x18001ced5  call    cs:__imp_LocalFree
0x18001cedb  mov     eax, ebx
0x18001cedd  jmp     loc_18001D238
0x18001cee2  lea     rdx, ??$guid_v@VSyncedPasskeyAuthenticator@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<SyncedPasskeyAuthenticator>
0x18001cee9  lea     rcx, [rbp+1A0h+var_200]
0x18001ceed  call    ??$create_instance@UISyncedPasskeyAuthenticator@@@winrt@@YA?A_PAEBUguid@0@IPEAX@Z
0x18001cef2  nop
0x18001cef3  mov     rbx, [rbp+1A0h+var_200]
0x18001cef7  mov     rcx, rbx
0x18001cefa  call    WebAuthNCom__AllowImpersonationCom
0x18001ceff  mov     rax, qword ptr [rbp+1A0h+var_1E0]
0x18001cf03  movaps  xmm0, xmmword ptr [rax]
0x18001cf06  movdqa  [rbp+1A0h+var_1E0], xmm0
0x18001cf0b  mov     rax, [rbx]
0x18001cf0e  lea     rdx, [rbp+1A0h+var_1E0]
0x18001cf12  mov     rcx, rbx
0x18001cf15  mov     rax, [rax+40h]
0x18001cf19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf1e  mov     rdx, rsi
0x18001cf21  lea     rcx, [rbp+1A0h+var_1E0]
0x18001cf25  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x18001cf2a  nop
0x18001cf2b  mov     rdx, [rdi+20h]
0x18001cf2f  add     rdx, 8
0x18001cf33  lea     rcx, [rbp+1A0h+var_140]
0x18001cf37  call    ??$?0AEBQEBG$0A@@?$basic_zstring_view@G@wil@@QEAA@AEBQEBG@Z; wil::basic_zstring_view<ushort>::basic_zstring_view<ushort>(ushort const * const &)
0x18001cf3c  movups  xmm0, xmmword ptr [rax]
0x18001cf3f  movdqu  [rbp+1A0h+var_160], xmm0
0x18001cf44  mov     rdx, [rdi+28h]
0x18001cf48  add     rdx, 10h
0x18001cf4c  lea     rcx, [rbp+1A0h+var_1F8]
0x18001cf50  call    ??$?0AEBQEBG$0A@@?$basic_zstring_view@G@wil@@QEAA@AEBQEBG@Z; wil::basic_zstring_view<ushort>::basic_zstring_view<ushort>(ushort const * const &)
0x18001cf55  movups  xmm0, xmmword ptr [rax]
0x18001cf58  movdqu  [rbp+1A0h+var_150], xmm0
0x18001cf5d  lea     r8, [rbp+1A0h+var_160]
0x18001cf61  lea     rdx, [rbp+1A0h+var_150]
0x18001cf65  lea     rcx, [rbp+1A0h+var_110]
0x18001cf6c  call    ?CreatePasskeyHeader@WebAuthNUI@@YA?AUCredUiAdditionalInfo@NgcUtils@@V?$basic_zstring_view@G@wil@@0@Z; WebAuthNUI::CreatePasskeyHeader(wil::basic_zstring_view<ushort>,wil::basic_zstring_view<ushort>)
0x18001cf71  nop
0x18001cf72  lea     rdx, [rbp+1A0h+var_198]
0x18001cf76  mov     rcx, rax
0x18001cf79  call    ?Serialize@CredUiAdditionalInfo@NgcUtils@@QEBA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; NgcUtils::CredUiAdditionalInfo::Serialize(void)
0x18001cf7e  nop
0x18001cf7f  lea     rcx, [rbp+1A0h+var_110]; this
0x18001cf86  call    ??1CredUiAdditionalInfo@NgcUtils@@QEAA@XZ; NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo(void)
0x18001cf8b  mov     r9d, 70h ; 'p'
0x18001cf91  mov     r8b, r14b
0x18001cf94  mov     edx, 4E2h
0x18001cf99  lea     rcx, [rbp+1A0h+var_B0]
0x18001cfa0  call    ?CreatePasskeyFooter@WebAuthNUI@@YA?AUCredUiAdditionalInfo@NgcUtils@@K_NK@Z; WebAuthNUI::CreatePasskeyFooter(ulong,bool,ulong)
0x18001cfa5  nop
0x18001cfa6  lea     rdx, [rbp+1A0h+var_1B0]
0x18001cfaa  mov     rcx, rax
0x18001cfad  call    ?Serialize@CredUiAdditionalInfo@NgcUtils@@QEBA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; NgcUtils::CredUiAdditionalInfo::Serialize(void)
0x18001cfb2  nop
0x18001cfb3  lea     rcx, [rbp+1A0h+var_B0]; this
0x18001cfba  call    ??1CredUiAdditionalInfo@NgcUtils@@QEAA@XZ; NgcUtils::CredUiAdditionalInfo::~CredUiAdditionalInfo(void)
0x18001cfbf  mov     edx, 40Ch
0x18001cfc4  lea     rcx, [rbp+1A0h+var_130]
0x18001cfc8  call    ??$FormatResourceString@$$V@WebAuthNUI@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; WebAuthNUI::FormatResourceString<>(ulong)
0x18001cfcd  nop
0x18001cfce  xor     edx, edx
0x18001cfd0  mov     [rbp+1A0h+pv], rdx
0x18001cfd4  mov     [rbp+1A0h+var_220], edx
0x18001cfd7  mov     rax, [rbx]
0x18001cfda  lea     rcx, [rbp+1A0h+pv]
0x18001cfde  mov     [rbp+1A0h+var_1F8], rcx
0x18001cfe2  mov     [rbp+1A0h+var_1F0], rdx
0x18001cfe6  mov     [rbp+1A0h+var_1E8], 1
0x18001cfea  mov     r10d, [rbp+1A0h+var_208]
0x18001cfee  mov     r11, [rbp+1A0h+hMem]
0x18001cff2  mov     r14, [rbp+1A0h+var_1B0]
0x18001cff6  mov     rdi, [rbp+1A0h+var_1A8]
0x18001cffa  mov     r9, [rbp+1A0h+var_198]
0x18001cffe  mov     rsi, [rbp+1A0h+var_190]
0x18001d002  lea     r8, [rbp+1A0h+var_130]
0x18001d006  cmp     [rbp+1A0h+var_118], 7
0x18001d00e  cmova   r8, [rbp+1A0h+var_130]
0x18001d013  sub     edi, r14d
0x18001d016  sub     esi, r9d
0x18001d019  lea     rcx, [rbp+1A0h+var_220]
0x18001d01d  mov     [rsp+2B0h+var_230], rcx
0x18001d025  lea     rcx, [rbp+1A0h+var_1F0]
0x18001d029  mov     [rsp+2B0h+var_238], rcx
0x18001d02e  mov     rcx, [rbp+1A0h+var_1C0]
0x18001d032  mov     [rsp+2B0h+var_240], rcx
0x18001d037  mov     rcx, [rbp+1A0h+var_1B8]
0x18001d03b  mov     [rsp+2B0h+var_248], rcx
0x18001d040  mov     ecx, dword ptr [rbp+1A0h+arg_40]
0x18001d046  mov     [rsp+2B0h+var_250], ecx
0x18001d04a  mov     rcx, [rbp+1A0h+var_1D0]
0x18001d04e  mov     [rsp+2B0h+var_258], rcx
0x18001d053  mov     [rsp+2B0h+var_260], r13d
0x18001d058  mov     [rsp+2B0h+var_268], r10d
0x18001d05d  mov     [rsp+2B0h+var_270], r11
0x18001d062  mov     ecx, dword ptr [rbp+1A0h+arg_20]
0x18001d068  mov     [rsp+2B0h+var_278], ecx
0x18001d06c  mov     [rsp+2B0h+var_280], edi
0x18001d070  mov     [rsp+2B0h+var_288], r14
0x18001d075  mov     dword ptr [rsp+2B0h+var_290], esi; int
0x18001d079  mov     rdx, r12
0x18001d07c  mov     rcx, rbx
0x18001d07f  mov     rax, [rax+20h]
0x18001d083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d088  mov     edi, eax
0x18001d08a  lea     rcx, [rbp+1A0h+var_1F8]
0x18001d08e  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18001d093  xor     esi, esi
0x18001d095  test    edi, edi
0x18001d097  jns     short loc_18001D118
0x18001d099  mov     rcx, [rbp+1A8h]; this
0x18001d0a0  mov     r9d, edi; char *
0x18001d0a3  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18001d0aa  lea     edx, [rsi+36h]; void *
0x18001d0ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d0b2  nop
0x18001d0b3  mov     rcx, [rbp+1A0h+pv]; pv
0x18001d0b7  mov     [rbp+1A0h+pv], rsi
0x18001d0bb  test    rcx, rcx
0x18001d0be  jz      short loc_18001D0C7
0x18001d0c0  call    cs:__imp_CoTaskMemFree
0x18001d0c6  nop
0x18001d0c7  lea     rcx, [rbp+1A0h+var_130]
0x18001d0cb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d0d0  nop
0x18001d0d1  lea     rcx, [rbp+1A0h+var_1B0]
0x18001d0d5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001d0da  nop
0x18001d0db  lea     rcx, [rbp+1A0h+var_198]
0x18001d0df  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001d0e4  nop
0x18001d0e5  lea     rcx, [rbp+1A0h+var_1E0]
0x18001d0e9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18001d0ee  nop
0x18001d0ef  test    rbx, rbx
0x18001d0f2  jz      short loc_18001D0FE
0x18001d0f4  lea     rcx, [rbp+1A0h+var_200]
0x18001d0f8  call    ?unconditional_release_ref@?$com_ptr@UISyncedPasskeyAuthenticatorLowPriv@@@winrt@@AEAAXXZ; winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(void)
0x18001d0fd  nop
0x18001d0fe  mov     rcx, [rbp+1A0h+hMem]; hMem
0x18001d102  mov     [rbp+1A0h+hMem], rsi
0x18001d106  test    rcx, rcx
0x18001d109  jz      short loc_18001D111
0x18001d10b  call    cs:__imp_LocalFree
0x18001d111  mov     eax, edi
0x18001d113  jmp     loc_18001D238
0x18001d118  mov     r8d, [rbp+1A0h+var_220]
0x18001d11c  mov     rdx, [rbp+1A0h+pv]
0x18001d120  add     r8, rdx
0x18001d123  lea     rcx, [rbp+1A0h+var_180]
0x18001d127  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x18001d12c  nop
0x18001d12d  mov     rcx, [rbp+1A0h+var_180]
0x18001d131  mov     [rbp+1A0h+var_1D0], rcx
0x18001d135  mov     rax, [rbp+1A0h+var_178]
0x18001d139  sub     rax, rcx
0x18001d13c  mov     [rbp+1A0h+var_1C8], rax
0x18001d140  lea     rdx, [rbp+1A0h+var_1D0]
0x18001d144  lea     rcx, [rbp+1A0h+var_110]
0x18001d14b  call    ?FromCbor@WebAuthnCredentialAttestation@NgcPasskeys@@SA?AU12@V?$span@$$CBE$0?0@std@@@Z; NgcPasskeys::WebAuthnCredentialAttestation::FromCbor(std::span<uchar const,-1>)
0x18001d150  mov     rdi, rax
0x18001d153  mov     rcx, [rax]
0x18001d156  mov     [r15], rcx
0x18001d159  mov     ecx, [rax+8]
0x18001d15c  mov     [r15+8], ecx
0x18001d160  lea     rdx, [rax+10h]
0x18001d164  lea     rcx, [r15+10h]
0x18001d168  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001d16d  lea     rdx, [rdi+30h]
0x18001d171  lea     rcx, [r15+30h]
0x18001d175  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x18001d17a  lea     rcx, [rbp+1A0h+var_110]; this
0x18001d181  call    ??1WebAuthnCredentialAttestation@NgcPasskeys@@QEAA@XZ; NgcPasskeys::WebAuthnCredentialAttestation::~WebAuthnCredentialAttestation(void)
0x18001d186  nop
0x18001d187  lea     rcx, [rbp+1A0h+var_180]
0x18001d18b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001d190  nop
0x18001d191  mov     rcx, [rbp+1A0h+pv]; pv
0x18001d195  mov     [rbp+1A0h+pv], rsi
0x18001d199  test    rcx, rcx
0x18001d19c  jz      short loc_18001D1A5
0x18001d19e  call    cs:__imp_CoTaskMemFree
0x18001d1a4  nop
0x18001d1a5  lea     rcx, [rbp+1A0h+var_130]
0x18001d1a9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001d1ae  nop
0x18001d1af  lea     rcx, [rbp+1A0h+var_1B0]
0x18001d1b3  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001d1b8  nop
0x18001d1b9  lea     rcx, [rbp+1A0h+var_198]
0x18001d1bd  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18001d1c2  nop
0x18001d1c3  lea     rcx, [rbp+1A0h+var_1E0]
0x18001d1c7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18001d1cc  mov     [rbp+1A0h+var_220], 2
0x18001d1d3  mov     [rsp+2B0h+var_290], rsi; int
0x18001d1d8  mov     r9d, 4
0x18001d1de  lea     r8, [rbp+1A0h+var_220]
0x18001d1e2  xor     edx, edx
0x18001d1e4  mov     rcx, cs:WNF_WEBA_PASSKEY_INFO_CHANGED
0x18001d1eb  call    cs:__imp_RtlPublishWnfStateData
0x18001d1f1  or      eax, 10000000h
0x18001d1f6  mov     rcx, [rbp+1A8h]; this
0x18001d1fd  jge     short loc_18001D214
0x18001d1ff  mov     r9d, eax; char *
0x18001d202  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18001d209  mov     edx, 3Dh ; '='; void *
0x18001d20e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d213  nop
0x18001d214  test    rbx, rbx
0x18001d217  jz      short loc_18001D223
0x18001d219  lea     rcx, [rbp+1A0h+var_200]
0x18001d21d  call    ?unconditional_release_ref@?$com_ptr@UISyncedPasskeyAuthenticatorLowPriv@@@winrt@@AEAAXXZ; winrt::com_ptr<ISyncedPasskeyAuthenticatorLowPriv>::unconditional_release_ref(void)
0x18001d222  nop
0x18001d223  mov     rcx, [rbp+1A0h+hMem]; hMem
0x18001d227  mov     [rbp+1A0h+hMem], rsi
0x18001d22b  test    rcx, rcx
0x18001d22e  jz      short loc_18001D236
0x18001d230  call    cs:__imp_LocalFree
0x18001d236  xor     eax, eax
0x18001d238  mov     rcx, [rbp+1A0h+var_50]
0x18001d23f  xor     rcx, rsp; StackCookie
0x18001d242  call    __security_check_cookie
0x18001d247  add     rsp, 278h
0x18001d24e  pop     r15
0x18001d250  pop     r14
0x18001d252  pop     r13
0x18001d254  pop     r12
0x18001d256  pop     rdi
0x18001d257  pop     rsi
0x18001d258  pop     rbx
0x18001d259  pop     rbp
0x18001d25a  retn
```
