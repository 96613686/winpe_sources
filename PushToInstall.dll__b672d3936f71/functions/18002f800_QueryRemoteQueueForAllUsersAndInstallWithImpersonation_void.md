# QueryRemoteQueueForAllUsersAndInstallWithImpersonation(void)

- ea: `0x18002f800`
- end: `0x18002fb46`
- name: `?QueryRemoteQueueForAllUsersAndInstallWithImpersonation@@YAXXZ`
- size: `838`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002fd70`

## callees

- `0x1800026b0`
- `0x18002008c`
- `0x18002e268`
- `0x18002ee24`
- `0x18002f028`
- `0x18002f280`
- `0x18002f800`
- `0x18002fbb4`
- `0x18002fc74`
- `0x180030a68`
- `0x180032cfc`
- `0x1800338b4`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f8f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002f8f5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002f911`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002f911`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002f98a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002f98a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002f929`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18002f929`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002f96d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002f96d`

## string_xrefs

- `0x18002facc`: `onecoreuap\enduser\winstore\pushtoinstall\lib\UserContextHelper.h`
- `0x18002fae0`: `onecoreuap\enduser\winstore\pushtoinstall\lib\UserContextHelper.h`
- `0x18002faf2`: `onecoreuap\enduser\winstore\pushtoinstall\lib\UserContextHelper.h`
- `0x18002fb01`: `onecoreuap\enduser\winstore\pushtoinstall\lib\UserContextHelper.h`
- `0x18002fa97`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`
- `0x18002fab4`: `onecoreuap\enduser\winstore\pushtoinstall\lib\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void QueryRemoteQueueForAllUsersAndInstallWithImpersonation(void)
{
  int v0; // eax
  unsigned int v1; // edx
  unsigned int v2; // edi
  int v3; // eax
  unsigned __int64 v4; // r14
  HANDLE CurrentThread; // rax
  int v6; // eax
  const char *v7; // r9
  const char *v8; // r9
  wil::details::in1diag3 *v9; // rcx
  unsigned int v10; // edx
  struct Windows::System::IUser *v11; // rcx
  __int64 v12; // rcx
  signed int LastError; // eax
  int v14; // edx
  unsigned int v15; // r8d
  signed int v16; // eax
  int v17; // edx
  unsigned int v18; // r8d
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-158h]
  bool v20; // [rsp+40h] [rbp-138h] BYREF
  unsigned int v21; // [rsp+44h] [rbp-134h] BYREF
  int v22; // [rsp+48h] [rbp-130h]
  struct Windows::System::IUser *v23; // [rsp+50h] [rbp-128h] BYREF
  __int64 v24; // [rsp+58h] [rbp-120h] BYREF
  void **v25; // [rsp+60h] [rbp-118h] BYREF
  HANDLE Token; // [rsp+68h] [rbp-110h] BYREF
  void **v27; // [rsp+70h] [rbp-108h] BYREF
  HANDLE hExistingToken; // [rsp+78h] [rbp-100h] BYREF
  unsigned __int64 v29; // [rsp+80h] [rbp-F8h] BYREF
  BOOL v30; // [rsp+88h] [rbp-F0h] BYREF
  void **v31; // [rsp+90h] [rbp-E8h]
  void *TokenHandle; // [rsp+98h] [rbp-E0h] BYREF
  const wil::ResultException *v33; // [rsp+A0h] [rbp-D8h] BYREF
  char Destination[144]; // [rsp+B0h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  ReloadUserState(&v24);
  v21 = 0;
  v0 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v24 + 56LL))(v24, &v21);
  if ( v0 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
      (const char *)(unsigned int)v0,
      TokenType);
  v29 = 0;
  v23 = 0;
  v2 = 0;
  v22 = 0;
  while ( v2 < v21 )
  {
    TraceLoggingCorrelationVector::Increment(_correlationVector, Destination);
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::System::IUser **))(*(_QWORD *)v24 + 48LL))(
             v24,
             v2,
             &v23);
      if ( v3 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xCA,
          (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
          (const char *)(unsigned int)v3,
          TokenType);
      GetUserContext(v23, &v29);
      v20 = 0;
      v4 = v29;
      v30 = 0;
      v31 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      TokenHandle = 0;
      if ( !v29 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x11,
          (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\UserContextHelper.h",
          (const char *)0x80070057LL,
          TokenType);
      CurrentThread = GetCurrentThread();
      OpenThreadToken(CurrentThread, 0x2000Eu, 1, &TokenHandle);
      v27 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      hExistingToken = 0;
      v6 = UMgrQueryUserToken(v4, &hExistingToken);
      if ( v6 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x15,
          (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\UserContextHelper.h",
          (const char *)(unsigned int)v6,
          TokenType);
      v25 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      Token = 0;
      if ( !DuplicateTokenEx(hExistingToken, 0xEu, 0, SecurityImpersonation, TokenImpersonation, &Token) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x1E,
          (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\UserContextHelper.h",
          v7);
      v30 = SetThreadToken(0, Token);
      v9 = retaddr;
      if ( !v30 )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x21,
          (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\UserContextHelper.h",
          v8);
      v25 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      if ( Token )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v25) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v14, v15);
LABEL_34:
          v16 = GetLastError();
          if ( v16 > 0 )
            v16 = (unsigned __int16)v16 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16, v17, v18);
          JUMPOUT(0x18002FB44LL);
        }
        Token = 0;
      }
      v27 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      if ( hExistingToken )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v27) )
          goto LABEL_34;
        hExistingToken = 0;
      }
      QueryRemoteInstallQueueForUser((__int64)v9, Destination, &v20);
      ImpersonateUserContext::~ImpersonateUserContext((ImpersonateUserContext *)&v30);
      ((void (__fastcall *)(bool, unsigned int))UpdateLoginTask)(v20, v10);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &wil::ResultException `RTTI Type Descriptor', &v33) )
      {
        LogMessage(
          2u,
          "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\service.cpp",
          0xD7u,
          "QueryRemoteQueueForAllUsersAndInstallWithImpersonation",
          *((_DWORD *)v33 + 8),
          L"Could not obtain OR impersonate the user CV:%hs",
          Destination);
        v2 = v22;
        __eh34_try_continuation(0, &wil::ResultException `RTTI Type Descriptor', &loc_18002FA19);
      }
    }
    v22 = ++v2;
  }
  if ( !v21 )
    ((void (__fastcall *)(bool, unsigned int))UpdateLoginTask)(1, v1);
  v11 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(struct Windows::System::IUser *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v12 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
}

```

## disassembly

```asm
0x18002f800  push    rbx
0x18002f802  push    rsi
0x18002f803  push    rdi
0x18002f804  push    r14
0x18002f806  sub     rsp, 158h
0x18002f80d  mov     rax, cs:__security_cookie
0x18002f814  xor     rax, rsp
0x18002f817  mov     [rsp+178h+var_38], rax
0x18002f81f  xor     ebx, ebx
0x18002f821  lea     rcx, [rsp+178h+var_120]
0x18002f826  call    ?ReloadUserState@@YA?AV?$ComPtr@U?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@XZ; ReloadUserState(void)
0x18002f82b  nop
0x18002f82c  mov     [rsp+178h+var_134], ebx
0x18002f830  mov     rcx, [rsp+178h+var_120]
0x18002f835  mov     rax, [rcx]
0x18002f838  lea     rdx, [rsp+178h+var_134]
0x18002f83d  mov     rax, [rax+38h]
0x18002f841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f846  mov     rcx, [rsp+178h]; this
0x18002f84e  test    eax, eax
0x18002f850  js      loc_18002FA94
0x18002f856  mov     [rsp+178h+var_F8], rbx
0x18002f85e  mov     [rsp+178h+var_128], rbx
0x18002f863  mov     edi, ebx
0x18002f865  mov     [rsp+178h+var_130], ebx
0x18002f869  lea     rsi, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18002f870  cmp     edi, [rsp+178h+var_134]
0x18002f874  jnb     loc_18002FA31
0x18002f87a  lea     rdx, [rsp+178h+Destination]; Destination
0x18002f882  mov     rcx, cs:?_correlationVector@@3PEAVTraceLoggingCorrelationVector@@EA; this
0x18002f889  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x18002f88e  nop
0x18002f88f  mov     rcx, [rsp+178h+var_120]
0x18002f894  mov     rax, [rcx]
0x18002f897  lea     r8, [rsp+178h+var_128]
0x18002f89c  mov     edx, edi
0x18002f89e  mov     rax, [rax+30h]
0x18002f8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f8a7  test    eax, eax
0x18002f8a9  js      loc_18002FAA9
0x18002f8af  lea     rdx, [rsp+178h+var_F8]; unsigned __int64 *
0x18002f8b7  mov     rcx, [rsp+178h+var_128]; struct Windows::System::IUser *
0x18002f8bc  call    ?GetUserContext@@YAXPEAUIUser@System@Windows@@PEA_K@Z; GetUserContext(Windows::System::IUser *,unsigned __int64 *)
0x18002f8c1  mov     [rsp+178h+var_138], bl
0x18002f8c5  mov     r14, [rsp+178h+var_F8]
0x18002f8cd  mov     [rsp+178h+var_F0], ebx
0x18002f8d4  mov     [rsp+178h+var_E8], rsi
0x18002f8dc  mov     [rsp+178h+TokenHandle], rbx
0x18002f8e4  mov     rcx, [rsp+178h]; this
0x18002f8ec  test    r14, r14
0x18002f8ef  jz      loc_18002FAC6
0x18002f8f5  call    cs:__imp_GetCurrentThread
0x18002f8fb  lea     r9, [rsp+178h+TokenHandle]; TokenHandle
0x18002f903  mov     edx, 2000Eh; DesiredAccess
0x18002f908  mov     r8d, 1; OpenAsSelf
0x18002f90e  mov     rcx, rax; ThreadHandle
0x18002f911  call    cs:__imp_OpenThreadToken
0x18002f917  mov     [rsp+178h+var_108], rsi
0x18002f91c  mov     [rsp+178h+hExistingToken], rbx
0x18002f921  lea     rdx, [rsp+178h+hExistingToken]
0x18002f926  mov     rcx, r14
0x18002f929  call    cs:__imp_UMgrQueryUserToken
0x18002f92f  mov     rcx, [rsp+178h]; this
0x18002f937  test    eax, eax
0x18002f939  js      loc_18002FADD
0x18002f93f  mov     [rsp+178h+var_118], rsi
0x18002f944  mov     [rsp+178h+Token], rbx
0x18002f949  lea     rax, [rsp+178h+Token]
0x18002f94e  mov     [rsp+178h+phNewToken], rax; phNewToken
0x18002f953  mov     [rsp+178h+TokenType], 2; TokenType
0x18002f95b  mov     r9d, 2; ImpersonationLevel
0x18002f961  xor     r8d, r8d; lpTokenAttributes
0x18002f964  lea     edx, [r9+0Ch]; dwDesiredAccess
0x18002f968  mov     rcx, [rsp+178h+hExistingToken]; hExistingToken
0x18002f96d  call    cs:__imp_DuplicateTokenEx
0x18002f973  mov     rcx, [rsp+178h]; this
0x18002f97b  test    eax, eax
0x18002f97d  jz      loc_18002FAF2
0x18002f983  mov     rdx, [rsp+178h+Token]; Token
0x18002f988  xor     ecx, ecx; Thread
0x18002f98a  call    cs:__imp_SetThreadToken
0x18002f990  mov     [rsp+178h+var_F0], eax
0x18002f997  mov     rcx, [rsp+178h]; this
0x18002f99f  test    eax, eax
0x18002f9a1  jz      loc_18002FB01
0x18002f9a7  mov     [rsp+178h+var_118], rsi
0x18002f9ac  cmp     [rsp+178h+Token], rbx
0x18002f9b1  jz      short loc_18002F9CA
0x18002f9b3  lea     rcx, [rsp+178h+var_118]
0x18002f9b8  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x18002f9bd  test    al, al
0x18002f9bf  jz      loc_18002FB11
0x18002f9c5  mov     [rsp+178h+Token], rbx
0x18002f9ca  mov     [rsp+178h+var_108], rsi
0x18002f9cf  cmp     [rsp+178h+hExistingToken], rbx
0x18002f9d4  jz      short loc_18002F9ED
0x18002f9d6  lea     rcx, [rsp+178h+var_108]
0x18002f9db  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x18002f9e0  test    al, al
0x18002f9e2  jz      loc_18002FB2B
0x18002f9e8  mov     [rsp+178h+hExistingToken], rbx
0x18002f9ed  lea     r8, [rsp+178h+var_138]; bool *
0x18002f9f2  lea     rdx, [rsp+178h+Destination]; char *
0x18002f9fa  call    ?QueryRemoteInstallQueueForUser@@YAX_KPEBDAEA_N@Z; QueryRemoteInstallQueueForUser(unsigned __int64,char const *,bool &)
0x18002f9ff  nop
0x18002fa00  lea     rcx, [rsp+178h+var_F0]; this
0x18002fa08  call    ??1ImpersonateUserContext@@QEAA@XZ; ImpersonateUserContext::~ImpersonateUserContext(void)
0x18002fa0d  mov     cl, [rsp+178h+var_138]; bool
0x18002fa11  call    ?UpdateLoginTask@@YAX_NK@Z; UpdateLoginTask(bool,ulong)
0x18002fa16  nop
0x18002fa17  jmp     short loc_18002FA26
0x18002fa19  xor     ebx, ebx
0x18002fa1b  lea     rsi, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18002fa22  mov     edi, [rsp+178h+var_130]
0x18002fa26  inc     edi
0x18002fa28  mov     [rsp+178h+var_130], edi
0x18002fa2c  jmp     loc_18002F870
0x18002fa31  cmp     [rsp+178h+var_134], ebx
0x18002fa35  jnz     short loc_18002FA3F
0x18002fa37  mov     cl, 1; bool
0x18002fa39  call    ?UpdateLoginTask@@YAX_NK@Z; UpdateLoginTask(bool,ulong)
0x18002fa3e  nop
0x18002fa3f  mov     rcx, [rsp+178h+var_128]
0x18002fa44  test    rcx, rcx
0x18002fa47  jz      short loc_18002FA5B
0x18002fa49  mov     [rsp+178h+var_128], rbx
0x18002fa4e  mov     rax, [rcx]
0x18002fa51  mov     rax, [rax+10h]
0x18002fa55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa5a  nop
0x18002fa5b  mov     rcx, [rsp+178h+var_120]
0x18002fa60  test    rcx, rcx
0x18002fa63  jz      short loc_18002FA77
0x18002fa65  mov     [rsp+178h+var_120], rbx
0x18002fa6a  mov     rax, [rcx]
0x18002fa6d  mov     rax, [rax+10h]
0x18002fa71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa76  nop
0x18002fa77  mov     rcx, [rsp+178h+var_38]
0x18002fa7f  xor     rcx, rsp; StackCookie
0x18002fa82  call    __security_check_cookie
0x18002fa87  add     rsp, 158h
0x18002fa8e  pop     r14
0x18002fa90  pop     rdi
0x18002fa91  pop     rsi
0x18002fa92  pop     rbx
0x18002fa93  retn
0x18002fa94  mov     r9d, eax; char *
0x18002fa97  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002fa9e  mov     edx, 0BDh; void *
0x18002faa3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002faa9  mov     rcx, [rsp+178h]; this
0x18002fab1  mov     r9d, eax; char *
0x18002fab4  lea     r8, aOnecoreuapEndu_14; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002fabb  mov     edx, 0CAh; void *
0x18002fac0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002fac6  mov     r9d, 80070057h; char *
0x18002facc  lea     r8, aOnecoreuapEndu_5; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002fad3  lea     edx, [r14+11h]; void *
0x18002fad7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002fadd  mov     r9d, eax; char *
0x18002fae0  lea     r8, aOnecoreuapEndu_5; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002fae7  mov     edx, 15h; void *
0x18002faec  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002faf2  lea     r8, aOnecoreuapEndu_5; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002faf9  lea     edx, [rax+1Eh]; void *
0x18002fafc  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002fb01  lea     r8, aOnecoreuapEndu_5; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002fb08  lea     edx, [rax+21h]; void *
0x18002fb0b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002fb11  call    cs:__imp_GetLastError
0x18002fb17  test    eax, eax
0x18002fb19  jle     short loc_18002FB23
0x18002fb1b  movzx   eax, ax
0x18002fb1e  or      eax, 80070000h
0x18002fb23  mov     ecx, eax; this
0x18002fb25  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002fb2a  nop
0x18002fb2b  call    cs:__imp_GetLastError
0x18002fb31  test    eax, eax
0x18002fb33  jle     short loc_18002FB3D
0x18002fb35  movzx   eax, ax
0x18002fb38  or      eax, 80070000h
0x18002fb3d  mov     ecx, eax; this
0x18002fb3f  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
