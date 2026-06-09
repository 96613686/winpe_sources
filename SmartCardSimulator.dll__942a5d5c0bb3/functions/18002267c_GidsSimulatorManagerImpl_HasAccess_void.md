# GidsSimulatorManagerImpl::HasAccess(void)

- ea: `0x18002267c`
- end: `0x1800228bb`
- name: `?HasAccess@GidsSimulatorManagerImpl@@AEAA_NXZ`
- size: `575`
- prototype: `char __fastcall(GidsSimulatorManagerImpl *this)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001f6dc`
- `0x18001fbb4`

## callees

- `0x1800041b8`
- `0x180004424`
- `0x1800089e8`
- `0x18000bb10`
- `0x18001e1a8`
- `0x18001ee28`
- `0x18001ee4c`
- `0x1800211dc`
- `0x18002267c`
- `0x180024478`
- `0x18002453c`
- `0x180058700`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800227c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800227c3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800227d7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800227d7`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002269b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002269b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002280f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180022849`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002280f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180022849`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180022716`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180022795`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180022716`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180022795`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180022754`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180022754`

## pseudocode

```c
char __fastcall GidsSimulatorManagerImpl::HasAccess(GidsSimulatorManagerImpl *this)
{
  char v1; // bl
  BOOL v2; // eax
  __int64 winerror_if; // rax
  PSID v4; // rdi
  BOOL v5; // eax
  __int64 v6; // rax
  HANDLE CurrentThread; // rax
  BOOL v8; // eax
  __int64 v9; // rax
  BOOL v10; // eax
  __int64 v11; // rax
  BOOL v12; // eax
  __int64 v13; // rax
  HRESULT v15; // [rsp+60h] [rbp-9h] BYREF
  WINBOOL IsMember; // [rsp+64h] [rbp-5h] BYREF
  _BYTE v17[8]; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v18[8]; // [rsp+70h] [rbp+7h] BYREF
  PSID pSid; // [rsp+78h] [rbp+Fh] BYREF
  void *TokenHandle; // [rsp+80h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+88h] [rbp+1Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+90h] [rbp+27h] BYREF

  v15 = CoImpersonateClient();
  errorlib::scoped_error<hresult_error::tag>::scoped_error<hresult_error::tag>(v18, 2, &v15);
  errorlib::scoped_error<hresult_error::tag>::throwfailed(v18);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(v18);
  *(_WORD *)((char *)&v15 + 1) = 258;
  v1 = 1;
  pSid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SidToCheck = 0;
  v2 = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck);
  winerror_if = make_winerror_if(v18, !v2);
  errorlib::scoped_error<winerror_error::tag>::throwfailed(winerror_if);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(v18);
  v4 = pSid;
  if ( pSid )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v18);
    FreeSid(v4);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v18);
  }
  pSid = 0;
  v5 = AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 6u, 0, 0, 0, 0, 0, 0, 0, &pSid);
  v6 = make_winerror_if(v17, !v5);
  errorlib::scoped_error<winerror_error::tag>::throwfailed(v6);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(v17);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v8 = OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle);
  v9 = make_winerror_if(v17, !v8);
  errorlib::scoped_error<winerror_error::tag>::throwfailed(v9);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(v17);
  IsMember = 0;
  v10 = CheckTokenMembership(TokenHandle, SidToCheck, &IsMember);
  v11 = make_winerror_if(v17, !v10);
  errorlib::scoped_error<winerror_error::tag>::throwfailed(v11);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(v17);
  if ( !IsMember )
  {
    v12 = CheckTokenMembership(TokenHandle, pSid, &IsMember);
    v13 = make_winerror_if(v17, !v12);
    errorlib::scoped_error<winerror_error::tag>::throwfailed(v13);
    errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(v17);
    if ( !IsMember )
      v1 = 0;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pSid);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SidToCheck);
  wil::details::ScopeExitFnGuard__lambda_83b268209b789e85c972463a367149af___::operator()(&v15);
  return v1;
}

```

## disassembly

```asm
0x18002267c  push    rbp
0x18002267e  push    rbx
0x18002267f  push    rsi
0x180022680  push    rdi
0x180022681  lea     rbp, [rsp-3Fh]
0x180022686  sub     rsp, 0A8h
0x18002268d  mov     rax, cs:__security_cookie
0x180022694  xor     rax, rsp
0x180022697  mov     [rbp+57h+var_28], rax
0x18002269b  call    cs:__imp_CoImpersonateClient
0x1800226a1  mov     [rbp+57h+var_60], eax
0x1800226a4  lea     r8, [rbp+57h+var_60]
0x1800226a8  mov     edx, 2
0x1800226ad  lea     rcx, [rbp+57h+var_50]
0x1800226b1  call    ??$?0J@?$scoped_error@Utag@hresult_error@@@errorlib@@QEAA@W4type@ErrorSource@1@$$QEAJ@Z; errorlib::scoped_error<hresult_error::tag>::scoped_error<hresult_error::tag>(errorlib::ErrorSource::type,long &&)
0x1800226b6  nop
0x1800226b7  lea     rcx, [rbp+57h+var_50]
0x1800226bb  call    ?throwfailed@?$scoped_error@Utag@hresult_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<hresult_error::tag>::throwfailed(void)
0x1800226c0  nop
0x1800226c1  lea     rcx, [rbp+57h+var_50]
0x1800226c5  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1800226ca  mov     word ptr [rbp+57h+var_60+1], 102h
0x1800226d0  mov     bl, 1
0x1800226d2  xor     esi, esi
0x1800226d4  mov     [rbp+57h+var_48], rsi
0x1800226d8  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x1800226db  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1800226e1  mov     [rbp+57h+SidToCheck], rsi
0x1800226e5  lea     rax, [rbp+57h+SidToCheck]
0x1800226e9  mov     [rsp+0C0h+pSid], rax; pSid
0x1800226ee  mov     [rsp+0C0h+nSubAuthority7], esi; nSubAuthority7
0x1800226f2  mov     [rsp+0C0h+nSubAuthority6], esi; nSubAuthority6
0x1800226f6  mov     [rsp+0C0h+nSubAuthority5], esi; nSubAuthority5
0x1800226fa  mov     [rsp+0C0h+nSubAuthority4], esi; nSubAuthority4
0x1800226fe  mov     [rsp+0C0h+nSubAuthority3], esi; nSubAuthority3
0x180022702  mov     [rsp+0C0h+nSubAuthority2], esi; nSubAuthority2
0x180022706  mov     r9d, 220h; nSubAuthority1
0x18002270c  lea     r8d, [rsi+20h]; nSubAuthority0
0x180022710  mov     dl, 2; nSubAuthorityCount
0x180022712  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180022716  call    cs:__imp_AllocateAndInitializeSid
0x18002271c  mov     edx, esi
0x18002271e  test    eax, eax
0x180022720  setz    dl
0x180022723  lea     rcx, [rbp+57h+var_50]
0x180022727  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x18002272c  nop
0x18002272d  mov     rcx, rax
0x180022730  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x180022735  nop
0x180022736  lea     rcx, [rbp+57h+var_50]
0x18002273a  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x18002273f  mov     rdi, [rbp+57h+var_48]
0x180022743  test    rdi, rdi
0x180022746  jz      short loc_180022763
0x180022748  lea     rcx, [rbp+57h+var_50]; this
0x18002274c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180022751  mov     rcx, rdi; pSid
0x180022754  call    cs:__imp_FreeSid
0x18002275a  lea     rcx, [rbp+57h+var_50]; this
0x18002275e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180022763  mov     [rbp+57h+var_48], rsi
0x180022767  lea     rax, [rbp+57h+var_48]
0x18002276b  mov     [rsp+0C0h+pSid], rax; pSid
0x180022770  mov     [rsp+0C0h+nSubAuthority7], esi; nSubAuthority7
0x180022774  mov     [rsp+0C0h+nSubAuthority6], esi; nSubAuthority6
0x180022778  mov     [rsp+0C0h+nSubAuthority5], esi; nSubAuthority5
0x18002277c  mov     [rsp+0C0h+nSubAuthority4], esi; nSubAuthority4
0x180022780  mov     [rsp+0C0h+nSubAuthority3], esi; nSubAuthority3
0x180022784  mov     [rsp+0C0h+nSubAuthority2], esi; nSubAuthority2
0x180022788  xor     r9d, r9d; nSubAuthority1
0x18002278b  lea     r8d, [r9+6]; nSubAuthority0
0x18002278f  mov     dl, bl; nSubAuthorityCount
0x180022791  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180022795  call    cs:__imp_AllocateAndInitializeSid
0x18002279b  mov     edx, esi
0x18002279d  test    eax, eax
0x18002279f  setz    dl
0x1800227a2  lea     rcx, [rbp+57h+var_58]
0x1800227a6  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x1800227ab  nop
0x1800227ac  mov     rcx, rax
0x1800227af  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x1800227b4  nop
0x1800227b5  lea     rcx, [rbp+57h+var_58]
0x1800227b9  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1800227be  nop
0x1800227bf  mov     [rbp+57h+TokenHandle], rsi
0x1800227c3  call    cs:__imp_GetCurrentThread
0x1800227c9  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800227cd  xor     r8d, r8d; OpenAsSelf
0x1800227d0  lea     edx, [r8+8]; DesiredAccess
0x1800227d4  mov     rcx, rax; ThreadHandle
0x1800227d7  call    cs:__imp_OpenThreadToken
0x1800227dd  mov     edx, esi
0x1800227df  test    eax, eax
0x1800227e1  setz    dl
0x1800227e4  lea     rcx, [rbp+57h+var_58]
0x1800227e8  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x1800227ed  nop
0x1800227ee  mov     rcx, rax
0x1800227f1  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x1800227f6  nop
0x1800227f7  lea     rcx, [rbp+57h+var_58]
0x1800227fb  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180022800  mov     [rbp+57h+IsMember], esi
0x180022803  lea     r8, [rbp+57h+IsMember]; IsMember
0x180022807  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18002280b  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18002280f  call    cs:__imp_CheckTokenMembership
0x180022815  mov     edx, esi
0x180022817  test    eax, eax
0x180022819  setz    dl
0x18002281c  lea     rcx, [rbp+57h+var_58]
0x180022820  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x180022825  nop
0x180022826  mov     rcx, rax
0x180022829  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x18002282e  nop
0x18002282f  lea     rcx, [rbp+57h+var_58]
0x180022833  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180022838  cmp     [rbp+57h+IsMember], esi
0x18002283b  jnz     short loc_18002287A
0x18002283d  lea     r8, [rbp+57h+IsMember]; IsMember
0x180022841  mov     rdx, [rbp+57h+var_48]; SidToCheck
0x180022845  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180022849  call    cs:__imp_CheckTokenMembership
0x18002284f  mov     edx, esi
0x180022851  test    eax, eax
0x180022853  setz    dl
0x180022856  lea     rcx, [rbp+57h+var_58]
0x18002285a  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x18002285f  nop
0x180022860  mov     rcx, rax
0x180022863  call    ?throwfailed@?$scoped_error@Utag@winerror_error@@@errorlib@@QEBAXXZ; errorlib::scoped_error<winerror_error::tag>::throwfailed(void)
0x180022868  nop
0x180022869  lea     rcx, [rbp+57h+var_58]
0x18002286d  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180022872  cmp     [rbp+57h+IsMember], esi
0x180022875  jnz     short loc_18002287A
0x180022877  mov     bl, sil
0x18002287a  lea     rcx, [rbp+57h+TokenHandle]
0x18002287e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180022883  nop
0x180022884  lea     rcx, [rbp+57h+var_48]
0x180022888  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002288d  nop
0x18002288e  lea     rcx, [rbp+57h+SidToCheck]
0x180022892  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180022897  nop
0x180022898  lea     rcx, [rbp+57h+var_60]
0x18002289c  call    wil__details__ScopeExitFnGuard__lambda_83b268209b789e85c972463a367149af_____operator__
0x1800228a1  mov     al, bl
0x1800228a3  mov     rcx, [rbp+57h+var_28]
0x1800228a7  xor     rcx, rsp; StackCookie
0x1800228aa  call    __security_check_cookie
0x1800228af  add     rsp, 0A8h
0x1800228b6  pop     rdi
0x1800228b7  pop     rsi
0x1800228b8  pop     rbx
0x1800228b9  pop     rbp
0x1800228ba  retn
```
