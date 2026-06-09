# _anonymous_namespace_::GetUsersToSyncOnMSATrigger

- ea: `0x180019378`
- end: `0x1800199af`
- name: `_anonymous_namespace_::GetUsersToSyncOnMSATrigger`
- size: `1591`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation`

## callers

- `0x18001bb40`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x1800082bc`
- `0x180008d50`
- `0x1800093ac`
- `0x180009a80`
- `0x18000bba8`
- `0x18000e59c`
- `0x18001398c`
- `0x180014788`
- `0x18001484c`
- `0x18001527c`
- `0x180015ed8`
- `0x180018ed4`
- `0x1800192e8`
- `0x180019378`
- `0x1800199b8`
- `0x18001a5f4`
- `0x18001ccf0`
- `0x180035e0c`
- `0x1800717b8`
- `0x180071e94`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019430`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001973f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019430`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001973f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001940c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001971b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800193fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001940c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001971b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019418`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001989a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800198d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019418`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001989a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800198d8`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800193ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800193ea`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800193d1`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800193d1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800194da`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800194da`

## string_xrefs

- `0x18001965e`: `Active session: {0}, user:{1}, sid:{2}`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall anonymous_namespace_::GetUsersToSyncOnMSATrigger(_QWORD *a1)
{
  void *v2; // rdx
  HANDLE Event; // rsi
  unsigned int v4; // r8d
  const char *v5; // r9
  __int64 v6; // rcx
  __int64 v7; // r8
  int wnf_subscription; // eax
  void (__fastcall ***v9)(_QWORD, __int64); // rbx
  bool v10; // si
  bool v11; // r15
  __int128 *v12; // rcx
  Private::Format *v13; // rax
  Private::Format *v14; // rax
  Private::Format *v15; // r14
  __int64 v16; // rax
  DWORD LastError; // r14d
  _OWORD *v18; // rbx
  _QWORD *v19; // rdx
  _OWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  int v29; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v30; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE hObject; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v32; // [rsp+38h] [rbp-C8h]
  __int128 v33; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v34; // [rsp+58h] [rbp-A8h]
  _BYTE v35[8]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v36[4]; // [rsp+78h] [rbp-88h] BYREF
  int v37; // [rsp+B8h] [rbp-48h]
  _BYTE v38[32]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD *v39; // [rsp+E0h] [rbp-20h]
  _BYTE pExceptionObject[40]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v41; // [rsp+118h] [rbp+18h] BYREF
  __int128 v42; // [rsp+128h] [rbp+28h]
  __int128 v43; // [rsp+138h] [rbp+38h]
  __int128 v44; // [rsp+148h] [rbp+48h]
  int v45; // [rsp+158h] [rbp+58h]
  _BYTE v46[40]; // [rsp+160h] [rbp+60h] BYREF
  char *v47; // [rsp+188h] [rbp+88h]
  _QWORD v48[7]; // [rsp+190h] [rbp+90h] BYREF
  _QWORD *v49; // [rsp+1C8h] [rbp+C8h]
  void **v50; // [rsp+1D0h] [rbp+D0h] BYREF
  RTL_SRWLOCK SRWLock; // [rsp+1D8h] [rbp+D8h] BYREF
  char v52; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v53; // [rsp+250h] [rbp+150h]
  _BYTE v54[48]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v55[120]; // [rsp+290h] [rbp+190h] BYREF
  __int64 v56; // [rsp+308h] [rbp+208h]
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+248h]

  v32 = a1;
  v50 = &LockBox<Optional<Sid>,4294967295>::`vftable';
  v53 = 0;
  InitializeSRWLock(&SRWLock);
  hObject = 0;
  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v2, v4, v5);
  GetLastError();
  hObject = Event;
  *((_QWORD *)&v41 + 1) = &wistd::__function::__func<_lambda_65fab60310a7e6513d8e52dbb8ae2497_,void (_WNF_UMGR_USER_CHANGED_DATA const &)>::`vftable';
  *(_QWORD *)&v42 = &hObject;
  *((_QWORD *)&v42 + 1) = &v50;
  v47 = (char *)&v41 + 8;
  v30 = 0;
  wnf_subscription = wil::details::make_wnf_subscription_state<_WNF_UMGR_USER_CHANGED_DATA>(v6, &v41, v7, &v30);
  if ( wnf_subscription < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43C,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)(unsigned int)wnf_subscription,
      v29);
  v9 = (void (__fastcall ***)(_QWORD, __int64))v30;
  v32 = (_QWORD *)v30;
  if ( v47 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v47 + 24LL))(v47);
  v10 = 0;
  v39 = 0;
  anonymous_namespace_::GetActiveUserSession(v55);
  if ( v56 )
  {
    v41 = *(_OWORD *)(v56 + 8);
    v42 = *(_OWORD *)(v56 + 24);
    v43 = *(_OWORD *)(v56 + 40);
    v44 = *(_OWORD *)(v56 + 56);
    v45 = *(_DWORD *)(v56 + 72);
    std::wstring::wstring(v46, v56 + 80);
    Optional<Sid>::operator=<Sid>(v35, &v41);
    if ( !v56 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
      throw (ErrorCodeException *)pExceptionObject;
    }
    LODWORD(v30) = *(_DWORD *)v56;
    anonymous_namespace_::GetUserNameFromSession(pExceptionObject);
    v33 = 0;
    v34 = 0u;
    std::wstring::_Construct<1,unsigned short const *>(&v33, L"Active session: {0}, user:{1}, sid:{2}", 38);
    v13 = (Private::Format *)StringAlgo::FormatString(v54, &v33);
    v14 = (Private::Format *)Private::Format::operator%<unsigned long>(v13);
    v15 = (Private::Format *)Private::Format::operator%<std::wstring>(v14);
    if ( !v39 )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)&v33, -2147467261);
      throw (ErrorCodeException *)&v33;
    }
    v11 = 1;
    std::wstring::wstring(&v33, (char *)v39 + 72);
    v16 = Private::Format::operator%<std::wstring>(v15);
    LODWORD(v30) = 2;
    wpc::Sync::Internal::SyncLogger::LogMessage(&v30, v16);
    std::wstring::~wstring(&v33);
    std::wstring::~wstring(v54);
    v12 = (__int128 *)pExceptionObject;
    goto LABEL_16;
  }
  v11 = 0;
  if ( WaitForSingleObject(hObject, 0xEA60u) )
  {
    v33 = 0;
    v34 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v33, L"Wait for login event timed out", 30);
    LODWORD(v30) = 2;
    wpc::Sync::Internal::SyncLogger::LogMessage(&v30, &v33);
    v12 = &v33;
LABEL_16:
    std::wstring::~wstring(v12);
    goto LABEL_17;
  }
  *(_QWORD *)&v33 = &v50;
  *((_QWORD *)&v33 + 1) = &v52;
  ((void (__fastcall *)(void ***))*v50)(&v50);
  if ( v39 )
  {
    std::wstring::~wstring((char *)v39 + 72);
    v39 = 0;
  }
  if ( v53 )
  {
    v36[0] = *(_OWORD *)v53;
    v36[1] = *(_OWORD *)(v53 + 16);
    v36[2] = *(_OWORD *)(v53 + 32);
    v36[3] = *(_OWORD *)(v53 + 48);
    v37 = *(_DWORD *)(v53 + 64);
    std::wstring::wstring(v38, v53 + 72);
    v39 = v36;
  }
  ((void (__fastcall *)(void ***))v50[1])(&v50);
  v10 = v39 != 0;
LABEL_17:
  if ( v56 )
    std::wstring::~wstring(v56 + 80);
  if ( v9 )
  {
    LastError = GetLastError();
    (**v9)(v9, 1);
    SetLastError(LastError);
  }
  v32 = 0;
  LOBYTE(v29) = v10;
  if ( v39 )
  {
    v48[0] = &std::_Func_impl_no_alloc<_lambda_00caa309640a4c375a763fddc9530d0d_,void,>::`vftable';
    v48[1] = &v29;
    v49 = v48;
    v30 = 1200000000;
    v18 = v39;
    v33 = 0;
    v34 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v33, L"SyncOnMSATrigger", 16);
    RegHelpers::LimitFrequencyForUser(&v33, v18, &v30, v48);
    std::wstring::~wstring(&v33);
    if ( v49 )
    {
      v19 = v48;
      LOBYTE(v19) = v49 != v48;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v49 + 32LL))(v49, v19);
    }
  }
  wpc::Sync::Internal::SyncLogger::LogGetUserForSyncOnMSATrigger(v11, v10, v29);
  v20 = v39;
  if ( v39 && (_BYTE)v29 )
  {
    v33 = 0;
    *(_QWORD *)&v34 = 0;
    std::vector<std::pair<Sid,std::optional<std::wstring>>>::_Emplace_reallocate<Sid &,std::nullopt_t const &>(
      &v33,
      0,
      v39);
    v21 = v34;
    *(_QWORD *)&v34 = 0;
    v22 = *((_QWORD *)&v33 + 1);
    v23 = v33;
    v33 = 0u;
    *a1 = v23;
    a1[1] = v22;
    a1[2] = v21;
    std::vector<std::pair<Sid,std::optional<std::wstring>>>::_Tidy(&v33);
    if ( v39 )
    {
      std::wstring::~wstring((char *)v39 + 72);
      v39 = 0;
    }
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
  }
  else
  {
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
    if ( v20 )
    {
      std::wstring::~wstring((char *)v20 + 72);
      v39 = 0;
    }
    if ( hObject && !CloseHandle(hObject) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
  }
  if ( v53 )
    std::wstring::~wstring(v53 + 72);
  return a1;
}

```

## disassembly

```asm
0x180019378  mov     [rsp-8+arg_8], rbx
0x18001937d  mov     [rsp-8+arg_10], rsi
0x180019382  push    rbp
0x180019383  push    rdi
0x180019384  push    r12
0x180019386  push    r14
0x180019388  push    r15
0x18001938a  lea     rbp, [rsp-220h]
0x180019392  sub     rsp, 320h
0x180019399  mov     rax, cs:__security_cookie
0x1800193a0  xor     rax, rsp
0x1800193a3  mov     [rbp+240h+var_30], rax
0x1800193aa  mov     rdi, rcx
0x1800193ad  mov     [rsp+340h+var_308], rcx
0x1800193b2  xor     r12d, r12d
0x1800193b5  lea     rax, ??_7?$LockBox@V?$Optional@VSid@@@@$0PPPPPPPP@@@6B@; const LockBox<Optional<Sid>,4294967295>::`vftable'
0x1800193bc  mov     [rbp+240h+var_170], rax
0x1800193c3  mov     [rbp+240h+var_F0], r12
0x1800193ca  lea     rcx, [rbp+240h+SRWLock]; SRWLock
0x1800193d1  call    cs:__imp_InitializeSRWLock
0x1800193d7  nop
0x1800193d8  mov     [rsp+340h+hObject], r12
0x1800193dd  mov     r9d, 1F0003h; dwDesiredAccess
0x1800193e3  xor     r8d, r8d; dwFlags
0x1800193e6  xor     edx, edx; lpName
0x1800193e8  xor     ecx, ecx; lpEventAttributes
0x1800193ea  call    cs:__imp_CreateEventExW
0x1800193f0  mov     rsi, rax
0x1800193f3  test    rax, rax
0x1800193f6  jz      loc_180019942
0x1800193fc  call    cs:__imp_GetLastError
0x180019402  mov     rbx, [rsp+340h+hObject]
0x180019407  test    rbx, rbx
0x18001940a  jz      short loc_180019436
0x18001940c  call    cs:__imp_GetLastError
0x180019412  mov     r14d, eax
0x180019415  mov     rcx, rbx; hObject
0x180019418  call    cs:__imp_CloseHandle
0x18001941e  mov     rcx, [rbp+248h]; this
0x180019425  test    eax, eax
0x180019427  jz      loc_18001994F
0x18001942d  mov     ecx, r14d; dwErrCode
0x180019430  call    cs:__imp_SetLastError
0x180019436  mov     [rsp+340h+hObject], rsi
0x18001943b  lea     rax, ??_7?$__func@V_lambda_65fab60310a7e6513d8e52dbb8ae2497_@@$$A6AXAEBU_WNF_UMGR_USER_CHANGED_DATA@@@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_65fab60310a7e6513d8e52dbb8ae2497_,void (_WNF_UMGR_USER_CHANGED_DATA const &)>::`vftable'
0x180019442  mov     qword ptr [rbp+240h+var_228+8], rax
0x180019446  lea     rax, [rsp+340h+hObject]
0x18001944b  mov     qword ptr [rbp+240h+var_218], rax
0x18001944f  lea     rax, [rbp+240h+var_170]
0x180019456  mov     qword ptr [rbp+240h+var_218+8], rax
0x18001945a  lea     rax, [rbp+240h+var_228+8]
0x18001945e  mov     [rbp+240h+var_1B8], rax
0x180019465  mov     [rsp+340h+var_318], r12
0x18001946a  lea     r9, [rsp+340h+var_318]
0x18001946f  lea     rdx, [rbp+240h+var_228]
0x180019473  call    ??$make_wnf_subscription_state@U_WNF_UMGR_USER_CHANGED_DATA@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXAEBU_WNF_UMGR_USER_CHANGED_DATA@@@Z@wistd@@KPEAPEAU?$wnf_subscription_state@U_WNF_UMGR_USER_CHANGED_DATA@@@01@@Z; wil::details::make_wnf_subscription_state<_WNF_UMGR_USER_CHANGED_DATA>(_WNF_STATE_NAME const &,wistd::function<void (_WNF_UMGR_USER_CHANGED_DATA const &)> &&,ulong,wil::details::wnf_subscription_state<_WNF_UMGR_USER_CHANGED_DATA> * *)
0x180019478  mov     rcx, [rbp+248h]; this
0x18001947f  test    eax, eax
0x180019481  js      loc_18001995A
0x180019487  mov     rbx, [rsp+340h+var_318]
0x18001948c  mov     [rsp+340h+var_308], rbx
0x180019491  mov     rcx, [rbp+240h+var_1B8]
0x180019498  test    rcx, rcx
0x18001949b  jz      short loc_1800194A9
0x18001949d  mov     rax, [rcx]
0x1800194a0  mov     rax, [rax+18h]
0x1800194a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194a9  mov     sil, r12b
0x1800194ac  mov     [rbp+240h+var_260], r12
0x1800194b0  lea     rcx, [rbp+240h+var_B0]
0x1800194b7  call    _anonymous_namespace___GetActiveUserSession
0x1800194bc  nop
0x1800194bd  mov     rdx, [rbp+240h+var_38]
0x1800194c4  test    rdx, rdx
0x1800194c7  jnz     loc_1800195E5
0x1800194cd  mov     r15b, r12b
0x1800194d0  mov     edx, 0EA60h; dwMilliseconds
0x1800194d5  mov     rcx, [rsp+340h+hObject]; hHandle
0x1800194da  call    cs:__imp_WaitForSingleObject
0x1800194e0  test    eax, eax
0x1800194e2  jnz     loc_18001959A
0x1800194e8  lea     rax, [rbp+240h+var_170]
0x1800194ef  mov     qword ptr [rsp+340h+var_2F8], rax
0x1800194f4  lea     rax, [rbp+240h+var_160]
0x1800194fb  mov     qword ptr [rsp+340h+var_2F8+8], rax
0x180019500  mov     rax, [rbp+240h+var_170]
0x180019507  lea     rcx, [rbp+240h+var_170]
0x18001950e  mov     rax, [rax]
0x180019511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019516  nop
0x180019517  mov     rcx, [rbp+240h+var_260]
0x18001951b  test    rcx, rcx
0x18001951e  jz      short loc_18001952D
0x180019520  add     rcx, 48h ; 'H'
0x180019524  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019529  mov     [rbp+240h+var_260], r12
0x18001952d  mov     rdx, [rbp+240h+var_F0]
0x180019534  test    rdx, rdx
0x180019537  jz      short loc_180019575
0x180019539  movups  xmm0, xmmword ptr [rdx]
0x18001953c  movups  [rsp+340h+var_2C8], xmm0
0x180019541  movups  xmm1, xmmword ptr [rdx+10h]
0x180019545  movups  [rbp+240h+var_2B8], xmm1
0x180019549  movups  xmm0, xmmword ptr [rdx+20h]
0x18001954d  movups  [rbp+240h+var_2A8], xmm0
0x180019551  movups  xmm1, xmmword ptr [rdx+30h]
0x180019555  movups  [rbp+240h+var_298], xmm1
0x180019559  mov     eax, [rdx+40h]
0x18001955c  mov     [rbp+240h+var_288], eax
0x18001955f  add     rdx, 48h ; 'H'
0x180019563  lea     rcx, [rbp+240h+var_280]
0x180019567  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001956c  lea     rax, [rsp+340h+var_2C8]
0x180019571  mov     [rbp+240h+var_260], rax
0x180019575  mov     rax, [rbp+240h+var_170]
0x18001957c  lea     rcx, [rbp+240h+var_170]
0x180019583  mov     rax, [rax+8]
0x180019587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001958c  nop
0x18001958d  cmp     [rbp+240h+var_260], r12
0x180019591  setnz   sil
0x180019595  jmp     loc_180019701
0x18001959a  xorps   xmm0, xmm0
0x18001959d  movups  [rsp+340h+var_2F8], xmm0
0x1800195a2  xorps   xmm1, xmm1
0x1800195a5  movdqu  [rsp+340h+var_2E8], xmm1
0x1800195ab  mov     r8d, 1Eh
0x1800195b1  lea     rdx, aWaitForLoginEv; "Wait for login event timed out"
0x1800195b8  lea     rcx, [rsp+340h+var_2F8]
0x1800195bd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800195c2  nop
0x1800195c3  mov     dword ptr [rsp+340h+var_318], 2
0x1800195cb  lea     rdx, [rsp+340h+var_2F8]
0x1800195d0  lea     rcx, [rsp+340h+var_318]
0x1800195d5  call    ?LogMessage@SyncLogger@Internal@Sync@wpc@@SAXAEBW4LogLevel@Logging@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::Sync::Internal::SyncLogger::LogMessage(wpc::Logging::LogLevel const &,std::wstring const &)
0x1800195da  nop
0x1800195db  lea     rcx, [rsp+340h+var_2F8]
0x1800195e0  jmp     loc_1800196FB
0x1800195e5  movups  xmm0, xmmword ptr [rdx+8]
0x1800195e9  movups  [rbp+240h+var_228], xmm0
0x1800195ed  movups  xmm1, xmmword ptr [rdx+18h]
0x1800195f1  movups  [rbp+240h+var_218], xmm1
0x1800195f5  movups  xmm0, xmmword ptr [rdx+28h]
0x1800195f9  movups  [rbp+240h+var_208], xmm0
0x1800195fd  movups  xmm1, xmmword ptr [rdx+38h]
0x180019601  movups  [rbp+240h+var_1F8], xmm1
0x180019605  mov     eax, [rdx+48h]
0x180019608  mov     [rbp+240h+var_1E8], eax
0x18001960b  add     rdx, 50h ; 'P'
0x18001960f  lea     rcx, [rbp+240h+var_1E0]
0x180019613  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180019618  lea     rdx, [rbp+240h+var_228]
0x18001961c  lea     rcx, [rsp+340h+var_2D0]
0x180019621  call    ??$?4VSid@@@?$Optional@VSid@@@@QEAAAEAV0@VSid@@@Z; Optional<Sid>::operator=<Sid>(Sid)
0x180019626  mov     rdx, [rbp+240h+var_38]
0x18001962d  test    rdx, rdx
0x180019630  jz      loc_18001996F
0x180019636  mov     edx, [rdx]
0x180019638  mov     dword ptr [rsp+340h+var_318], edx
0x18001963c  lea     rcx, [rbp+240h+pExceptionObject]
0x180019640  call    _anonymous_namespace___GetUserNameFromSession
0x180019645  nop
0x180019646  xorps   xmm0, xmm0
0x180019649  movups  [rsp+340h+var_2F8], xmm0
0x18001964e  mov     qword ptr [rsp+340h+var_2E8], r12
0x180019653  mov     qword ptr [rsp+340h+var_2E8+8], r12
0x180019658  mov     r8d, 26h ; '&'
0x18001965e  lea     rdx, aActiveSession0; "Active session: {0}, user:{1}, sid:{2}"
0x180019665  lea     rcx, [rsp+340h+var_2F8]
0x18001966a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001966f  lea     rdx, [rsp+340h+var_2F8]
0x180019674  lea     rcx, [rbp+240h+var_E0]
0x18001967b  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x180019680  nop
0x180019681  lea     rdx, [rsp+340h+var_318]
0x180019686  mov     rcx, rax; this
0x180019689  call    ??$?LK@Format@Private@@QEAAAEAV01@AEBK@Z; Private::Format::operator%<ulong>(ulong const &)
0x18001968e  lea     rdx, [rbp+240h+pExceptionObject]
0x180019692  mov     rcx, rax; this
0x180019695  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x18001969a  mov     r14, rax
0x18001969d  mov     rdx, [rbp+240h+var_260]
0x1800196a1  test    rdx, rdx
0x1800196a4  jz      loc_18001998E
0x1800196aa  mov     r15b, 1
0x1800196ad  add     rdx, 48h ; 'H'
0x1800196b1  lea     rcx, [rsp+340h+var_2F8]
0x1800196b6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800196bb  nop
0x1800196bc  lea     rdx, [rsp+340h+var_2F8]
0x1800196c1  mov     rcx, r14; this
0x1800196c4  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x1800196c9  mov     dword ptr [rsp+340h+var_318], 2
0x1800196d1  mov     rdx, rax
0x1800196d4  lea     rcx, [rsp+340h+var_318]
0x1800196d9  call    ?LogMessage@SyncLogger@Internal@Sync@wpc@@SAXAEBW4LogLevel@Logging@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::Sync::Internal::SyncLogger::LogMessage(wpc::Logging::LogLevel const &,std::wstring const &)
0x1800196de  nop
0x1800196df  lea     rcx, [rsp+340h+var_2F8]
0x1800196e4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800196e9  nop
0x1800196ea  lea     rcx, [rbp+240h+var_E0]
0x1800196f1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800196f6  nop
0x1800196f7  lea     rcx, [rbp+240h+pExceptionObject]
0x1800196fb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019700  nop
0x180019701  mov     rcx, [rbp+240h+var_38]
0x180019708  test    rcx, rcx
0x18001970b  jz      short loc_180019716
0x18001970d  add     rcx, 50h ; 'P'
0x180019711  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180019716  test    rbx, rbx
0x180019719  jz      short loc_180019745
0x18001971b  call    cs:__imp_GetLastError
0x180019721  mov     r14d, eax
0x180019724  test    rbx, rbx
0x180019727  jz      short loc_18001973C
0x180019729  mov     rax, [rbx]
0x18001972c  mov     edx, 1
0x180019731  mov     rcx, rbx
0x180019734  mov     rax, [rax]
0x180019737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001973c  mov     ecx, r14d; dwErrCode
0x18001973f  call    cs:__imp_SetLastError
0x180019745  mov     [rsp+340h+var_308], r12
0x18001974a  mov     byte ptr [rsp+340h+var_320], sil
0x18001974f  cmp     [rbp+240h+var_260], r12
0x180019753  jz      loc_180019801
0x180019759  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_00caa309640a4c375a763fddc9530d0d_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_00caa309640a4c375a763fddc9530d0d_,void,>::`vftable'
0x180019760  mov     [rbp+240h+var_1B0], rax
0x180019767  lea     rax, [rsp+340h+var_320]
0x18001976c  mov     [rbp+240h+var_1A8], rax
0x180019773  lea     rax, [rbp+240h+var_1B0]
0x18001977a  mov     [rbp+240h+var_178], rax
0x180019781  mov     [rsp+340h+var_318], 47868C00h
0x18001978a  mov     rbx, [rbp+240h+var_260]
0x18001978e  xorps   xmm0, xmm0
0x180019791  movups  [rsp+340h+var_2F8], xmm0
0x180019796  xorps   xmm1, xmm1
0x180019799  movdqu  [rsp+340h+var_2E8], xmm1
0x18001979f  mov     r8d, 10h
0x1800197a5  lea     rdx, aSynconmsatrigg; "SyncOnMSATrigger"
0x1800197ac  lea     rcx, [rsp+340h+var_2F8]
0x1800197b1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800197b6  nop
0x1800197b7  lea     r9, [rbp+240h+var_1B0]
0x1800197be  lea     r8, [rsp+340h+var_318]
0x1800197c3  mov     rdx, rbx
0x1800197c6  lea     rcx, [rsp+340h+var_2F8]
0x1800197cb  call    ?LimitFrequencyForUser@RegHelpers@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVSid@@AEBVTimeSpan@@AEBV?$function@$$A6AXXZ@3@@Z; RegHelpers::LimitFrequencyForUser(std::wstring const &,Sid const &,TimeSpan const &,std::function<void (void)> const &)
0x1800197d0  nop
0x1800197d1  lea     rcx, [rsp+340h+var_2F8]
0x1800197d6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800197db  nop
0x1800197dc  mov     rcx, [rbp+240h+var_178]
0x1800197e3  test    rcx, rcx
0x1800197e6  jz      short loc_180019801
0x1800197e8  mov     rax, [rcx]
0x1800197eb  lea     rdx, [rbp+240h+var_1B0]
0x1800197f2  cmp     rcx, rdx
0x1800197f5  setnz   dl
0x1800197f8  mov     rax, [rax+20h]
0x1800197fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019801  mov     r8b, byte ptr [rsp+340h+var_320]; bool
0x180019806  mov     dl, sil; bool
0x180019809  mov     cl, r15b; bool
0x18001980c  call    ?LogGetUserForSyncOnMSATrigger@SyncLogger@Internal@Sync@wpc@@SAX_N00@Z; wpc::Sync::Internal::SyncLogger::LogGetUserForSyncOnMSATrigger(bool,bool,bool)
0x180019811  mov     rcx, [rbp+240h+var_260]
0x180019815  test    rcx, rcx
0x180019818  jz      loc_1800198B1
0x18001981e  cmp     byte ptr [rsp+340h+var_320], r12b
0x180019823  jz      loc_1800198B1
0x180019829  xorps   xmm0, xmm0
0x18001982c  movdqu  [rsp+340h+var_2F8], xmm0
0x180019832  mov     qword ptr [rsp+340h+var_2E8], r12
0x180019837  mov     r8, rcx
0x18001983a  xor     edx, edx
0x18001983c  lea     rcx, [rsp+340h+var_2F8]
0x180019841  call    ??$_Emplace_reallocate@AEAVSid@@AEBUnullopt_t@std@@@?$vector@U?$pair@VSid@@V?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@V?$allocator@U?$pair@VSid@@V?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@@std@@AEAAPEAU?$pair@VSid@@V?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@1@QEAU21@AEAVSid@@AEBUnullopt_t@1@@Z; std::vector<std::pair<Sid,std::optional<std::wstring>>>::_Emplace_reallocate<Sid &,std::nullopt_t const &>(std::pair<Sid,std::optional<std::wstring>> * const,Sid &,std::nullopt_t const &)
0x180019846  mov     rdx, qword ptr [rsp+340h+var_2E8]
0x18001984b  mov     qword ptr [rsp+340h+var_2E8], r12
0x180019850  mov     rcx, qword ptr [rsp+340h+var_2F8+8]
0x180019855  mov     qword ptr [rsp+340h+var_2F8+8], r12
0x18001985a  mov     rax, qword ptr [rsp+340h+var_2F8]
0x18001985f  mov     qword ptr [rsp+340h+var_2F8], r12
0x180019864  mov     [rdi], rax
0x180019867  mov     [rdi+8], rcx
0x18001986b  mov     [rdi+10h], rdx
0x18001986f  lea     rcx, [rsp+340h+var_2F8]
0x180019874  call    ?_Tidy@?$vector@U?$pair@VSid@@V?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@V?$allocator@U?$pair@VSid@@V?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<Sid,std::optional<std::wstring>>>::_Tidy(void)
0x180019879  nop
0x18001987a  mov     rcx, [rbp+240h+var_260]
0x18001987e  test    rcx, rcx
0x180019881  jz      short loc_180019890
0x180019883  add     rcx, 48h ; 'H'
0x180019887  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001988c  mov     [rbp+240h+var_260], r12
0x180019890  mov     rcx, [rsp+340h+hObject]; hObject
0x180019895  test    rcx, rcx
0x180019898  jz      short loc_1800198E9
  ... truncated ...
```
