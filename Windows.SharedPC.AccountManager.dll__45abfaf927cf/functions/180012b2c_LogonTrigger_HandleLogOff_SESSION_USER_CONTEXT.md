# LogonTrigger::HandleLogOff(_SESSION_USER_CONTEXT)

- ea: `0x180012b2c`
- end: `0x180012dc2`
- name: `?HandleLogOff@LogonTrigger@@QEAAXU_SESSION_USER_CONTEXT@@@Z`
- size: `662`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800114d0`

## callees

- `0x180003530`
- `0x1800042c0`
- `0x18000a5c4`
- `0x18000ccd4`
- `0x18000cd50`
- `0x180011a6c`
- `0x1800121c4`
- `0x180012294`
- `0x180012598`
- `0x180012b2c`
- `0x18001357c`
- `0x1800136d4`
- `0x180013c28`
- `0x180013cf0`
- `0x180013dcc`
- `0x180013e2c`
- `0x18001cb4c`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012ba1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012ba1`
- `ntdll!RtlIsMultiSessionSku` at `0x180012c38`
- `ntdll!RtlIsMultiSessionSku` at `0x180012c38`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamFreeBuffer` at `0x180012ca9`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamFreeBuffer` at `0x180012cfb`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamFreeBuffer` at `0x180012ca9`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamFreeBuffer` at `0x180012cfb`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamGetNonCandidateUserSessionIds` at `0x180012c87`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamGetNonCandidateUserSessionIds` at `0x180012ce3`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamGetNonCandidateUserSessionIds` at `0x180012c87`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamGetNonCandidateUserSessionIds` at `0x180012ce3`

## string_xrefs

- `0x180012d9b`: `shellcommon\shell\sharedpc\accountmanager\lib\service\logontrigger.cpp`
- `0x180012daf`: `shellcommon\shell\sharedpc\accountmanager\lib\service\logontrigger.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall LogonTrigger::HandleLogOff(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // r8
  unsigned __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // edi
  const unsigned __int16 *v11; // rax
  int updated; // eax
  int v13; // eax
  const char *v14; // r9
  int v15; // [rsp+20h] [rbp-1C8h] BYREF
  RTL_SRWLOCK *v16; // [rsp+28h] [rbp-1C0h] BYREF
  __int64 v17; // [rsp+30h] [rbp-1B8h] BYREF
  __int128 v18; // [rsp+38h] [rbp-1B0h] BYREF
  __int64 v19; // [rsp+48h] [rbp-1A0h]
  __int64 v20; // [rsp+50h] [rbp-198h]
  _QWORD v21[42]; // [rsp+60h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)v21,
    (__int64)"HandleLogOff");
  v21[0] = &SharedPCAccountManagerTelemetry::HandleLogOff::`vftable';
  SharedPCAccountManagerTelemetry::HandleLogOff::StartActivity((SharedPCAccountManagerTelemetry::HandleLogOff *)v21);
  v18 = 0;
  v19 = 0;
  v20 = 7;
  LOWORD(v18) = 0;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 40));
  try
  {
    v16 = (RTL_SRWLOCK *)(a1 + 40);
    if ( *(_QWORD *)a2 )
    {
      v4 = *(_QWORD *)(a1 + 64);
      if ( v4 != *(_QWORD *)(a1 + 72) )
      {
        do
        {
          if ( *(_DWORD *)(v4 + 8) == *(_DWORD *)(a2 + 8) && *(_QWORD *)v4 == *(_QWORD *)a2 )
            break;
          v4 += 48;
        }
        while ( v4 != *(_QWORD *)(a1 + 72) );
        if ( v4 != *(_QWORD *)(a1 + 72) )
        {
          if ( &v18 != (__int128 *)(v4 + 16) )
          {
            v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
            std::wstring::_Assign<unsigned short>(&v18, v5, *(_QWORD *)(v6 + 16));
          }
          std::vector<SessionUserInfo>::erase(a1 + 64, &v17, v4);
        }
      }
    }
    v7 = 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(a1 + 72) - *(_QWORD *)(a1 + 64)) >> 4);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    if ( (unsigned __int8)RtlIsMultiSessionSku()
      && (unsigned __int8)IsCamIsEphemeralCandidateUserPresent(v8)
      && (unsigned __int8)IsCamIsEphemeralCandidateUserPresent(v9) )
    {
      v15 = 0;
      v16 = 0;
      if ( (unsigned int)GetDeletionPolicyType() )
      {
        if ( (int)CamGetNonCandidateUserSessionIds(&v15, &v16) >= 0 )
          v7 = (unsigned int)v15;
      }
      else
      {
        v10 = 1;
        while ( (int)CamGetNonCandidateUserSessionIds(&v15, &v16) >= 0 && v15 != v7 )
        {
          if ( v10 == 2 )
          {
            v7 = (unsigned int)v15;
            break;
          }
          if ( v16 )
          {
            CamFreeBuffer();
            v16 = 0;
          }
          v17 = 2;
          std::this_thread::sleep_for<__int64,std::ratio<1,1>>(&v17);
          if ( ++v10 > 2 )
            break;
        }
      }
      if ( v16 )
        CamFreeBuffer();
    }
    if ( v19 )
    {
      v11 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      updated = LogonTrigger::UpdateUserAccessTime((LogonTrigger *)a1, v11);
      if ( updated < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xAC,
          (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
          (const char *)(unsigned int)updated,
          v15);
    }
    else if ( *(_QWORD *)a2 )
    {
      SharedPCAccountManagerTelemetry::UserNotActiveButLoggingOff();
    }
    if ( !v7 )
    {
      v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 56) + 24LL))(*(_QWORD *)(a1 + 56), 0);
      if ( v13 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xB7,
          (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
          (const char *)(unsigned int)v13,
          v15);
    }
    wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v21);
    std::wstring::_Tidy_deallocate((__int64)&v18);
    SharedPCAccountManagerTelemetry::HandleLogOff::~HandleLogOff((SharedPCAccountManagerTelemetry::HandleLogOff *)v21);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xBC,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\service\\logontrigger.cpp",
      v14);
  }
}

```

## disassembly

```asm
0x180012b2c  push    rbx
0x180012b2e  push    rsi
0x180012b2f  push    rdi
0x180012b30  push    r14
0x180012b32  sub     rsp, 1C8h
0x180012b39  mov     rax, cs:__security_cookie
0x180012b40  xor     rax, rsp
0x180012b43  mov     [rsp+1E8h+var_38], rax
0x180012b4b  mov     r14, rdx
0x180012b4e  mov     rsi, rcx
0x180012b51  lea     rdx, aHandlelogoff; "HandleLogOff"
0x180012b58  lea     rcx, [rsp+1E8h+var_188]
0x180012b5d  call    ??0?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180012b62  lea     rax, ??_7HandleLogOff@SharedPCAccountManagerTelemetry@@6B@; const SharedPCAccountManagerTelemetry::HandleLogOff::`vftable'
0x180012b69  mov     [rsp+1E8h+var_188], rax
0x180012b6e  lea     rcx, [rsp+1E8h+var_188]; this
0x180012b73  call    ?StartActivity@HandleLogOff@SharedPCAccountManagerTelemetry@@QEAAXXZ; SharedPCAccountManagerTelemetry::HandleLogOff::StartActivity(void)
0x180012b78  nop
0x180012b79  xorps   xmm0, xmm0
0x180012b7c  movups  [rsp+1E8h+var_1B0], xmm0
0x180012b81  mov     [rsp+1E8h+var_1A0], 0
0x180012b8a  mov     [rsp+1E8h+var_198], 7
0x180012b93  xor     eax, eax
0x180012b95  mov     word ptr [rsp+1E8h+var_1B0], ax
0x180012b9a  lea     rbx, [rsi+28h]
0x180012b9e  mov     rcx, rbx; SRWLock
0x180012ba1  call    cs:__imp_AcquireSRWLockExclusive
0x180012ba7  mov     [rsp+1E8h+var_1C0], rbx
0x180012bac  mov     rcx, [r14]
0x180012baf  test    rcx, rcx
0x180012bb2  jz      short loc_180012C14
0x180012bb4  mov     rbx, [rsi+40h]
0x180012bb8  cmp     rbx, [rsi+48h]
0x180012bbc  jz      short loc_180012C14
0x180012bbe  mov     eax, [r14+8]
0x180012bc2  cmp     [rbx+8], eax
0x180012bc5  jnz     short loc_180012BCC
0x180012bc7  cmp     [rbx], rcx
0x180012bca  jz      short loc_180012BD6
0x180012bcc  add     rbx, 30h ; '0'
0x180012bd0  cmp     rbx, [rsi+48h]
0x180012bd4  jnz     short loc_180012BC2
0x180012bd6  cmp     rbx, [rsi+48h]
0x180012bda  jz      short loc_180012C14
0x180012bdc  lea     r8, [rbx+10h]
0x180012be0  lea     rax, [rsp+1E8h+var_1B0]
0x180012be5  cmp     rax, r8
0x180012be8  jz      short loc_180012C03
0x180012bea  mov     rcx, r8
0x180012bed  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180012bf2  mov     r8, [r8+10h]
0x180012bf6  mov     rdx, rax
0x180012bf9  lea     rcx, [rsp+1E8h+var_1B0]
0x180012bfe  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180012c03  mov     r8, rbx
0x180012c06  lea     rdx, [rsp+1E8h+var_1B8]
0x180012c0b  lea     rcx, [rsi+40h]
0x180012c0f  call    ?erase@?$vector@USessionUserInfo@@V?$allocator@USessionUserInfo@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@USessionUserInfo@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@USessionUserInfo@@@std@@@std@@@2@@Z; std::vector<SessionUserInfo>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<SessionUserInfo>>>)
0x180012c14  mov     rbx, [rsi+48h]
0x180012c18  sub     rbx, [rsi+40h]
0x180012c1c  sar     rbx, 4
0x180012c20  mov     rax, 0AAAAAAAAAAAAAAABh
0x180012c2a  imul    rbx, rax
0x180012c2e  lea     rcx, [rsp+1E8h+var_1C0]
0x180012c33  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012c38  call    cs:__imp_RtlIsMultiSessionSku
0x180012c3e  test    al, al
0x180012c40  jz      loc_180012D01
0x180012c46  call    IsCamIsEphemeralCandidateUserPresent
0x180012c4b  test    al, al
0x180012c4d  jz      loc_180012D01
0x180012c53  call    IsCamIsEphemeralCandidateUserPresent
0x180012c58  test    al, al
0x180012c5a  jz      loc_180012D01
0x180012c60  mov     [rsp+1E8h+var_1C8], 0; int
0x180012c68  mov     [rsp+1E8h+var_1C0], 0
0x180012c71  call    ?GetDeletionPolicyType@@YA?AW4DeletionPolicy@@XZ; GetDeletionPolicyType(void)
0x180012c76  test    eax, eax
0x180012c78  jnz     short loc_180012CD9
0x180012c7a  lea     edi, [rax+1]
0x180012c7d  lea     rdx, [rsp+1E8h+var_1C0]
0x180012c82  lea     rcx, [rsp+1E8h+var_1C8]
0x180012c87  call    cs:__imp_CamGetNonCandidateUserSessionIds
0x180012c8d  test    eax, eax
0x180012c8f  js      short loc_180012CF1
0x180012c91  mov     eax, [rsp+1E8h+var_1C8]
0x180012c95  cmp     rax, rbx
0x180012c98  jz      short loc_180012CF1
0x180012c9a  cmp     edi, 2
0x180012c9d  jz      short loc_180012CD4
0x180012c9f  mov     rcx, [rsp+1E8h+var_1C0]
0x180012ca4  test    rcx, rcx
0x180012ca7  jz      short loc_180012CB8
0x180012ca9  call    cs:__imp_CamFreeBuffer
0x180012caf  mov     [rsp+1E8h+var_1C0], 0
0x180012cb8  mov     [rsp+1E8h+var_1B8], 2
0x180012cc1  lea     rcx, [rsp+1E8h+var_1B8]
0x180012cc6  call    ??$sleep_for@_JU?$ratio@$00$00@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1>>(std::chrono::duration<__int64,std::ratio<1,1>> const &)
0x180012ccb  inc     edi
0x180012ccd  cmp     edi, 2
0x180012cd0  jle     short loc_180012C7D
0x180012cd2  jmp     short loc_180012CF1
0x180012cd4  mov     rbx, rax
0x180012cd7  jmp     short loc_180012CF1
0x180012cd9  lea     rdx, [rsp+1E8h+var_1C0]
0x180012cde  lea     rcx, [rsp+1E8h+var_1C8]
0x180012ce3  call    cs:__imp_CamGetNonCandidateUserSessionIds
0x180012ce9  test    eax, eax
0x180012ceb  js      short loc_180012CF1
0x180012ced  mov     ebx, [rsp+1E8h+var_1C8]
0x180012cf1  mov     rcx, [rsp+1E8h+var_1C0]
0x180012cf6  test    rcx, rcx
0x180012cf9  jz      short loc_180012D01
0x180012cfb  call    cs:__imp_CamFreeBuffer
0x180012d01  cmp     [rsp+1E8h+var_1A0], 0
0x180012d07  jz      short loc_180012D2C
0x180012d09  lea     rcx, [rsp+1E8h+var_1B0]
0x180012d0e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180012d13  mov     rdx, rax; unsigned __int16 *
0x180012d16  mov     rcx, rsi; this
0x180012d19  call    ?UpdateUserAccessTime@LogonTrigger@@QEAAJPEBG@Z; LogonTrigger::UpdateUserAccessTime(ushort const *)
0x180012d1e  mov     rcx, [rsp+1E8h]; this
0x180012d26  test    eax, eax
0x180012d28  js      short loc_180012D98
0x180012d2a  jmp     short loc_180012D37
0x180012d2c  cmp     qword ptr [r14], 0
0x180012d30  jz      short loc_180012D37
0x180012d32  call    ?UserNotActiveButLoggingOff@SharedPCAccountManagerTelemetry@@SAXXZ; SharedPCAccountManagerTelemetry::UserNotActiveButLoggingOff(void)
0x180012d37  test    rbx, rbx
0x180012d3a  jnz     short loc_180012D5A
0x180012d3c  mov     rcx, [rsi+38h]
0x180012d40  mov     rax, [rcx]
0x180012d43  xor     edx, edx
0x180012d45  mov     rax, [rax+18h]
0x180012d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d4e  mov     rcx, [rsp+1E8h]; this
0x180012d56  test    eax, eax
0x180012d58  js      short loc_180012DAC
0x180012d5a  lea     rcx, [rsp+1E8h+var_188]
0x180012d5f  call    ?Stop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SharedPCAccountManagerLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180012d64  nop
0x180012d65  lea     rcx, [rsp+1E8h+var_1B0]
0x180012d6a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180012d6f  nop
0x180012d70  lea     rcx, [rsp+1E8h+var_188]; this
0x180012d75  call    ??1HandleLogOff@SharedPCAccountManagerTelemetry@@QEAA@XZ; SharedPCAccountManagerTelemetry::HandleLogOff::~HandleLogOff(void)
0x180012d7a  nop
0x180012d7b  mov     rcx, [rsp+1E8h+var_38]
0x180012d83  xor     rcx, rsp; StackCookie
0x180012d86  call    __security_check_cookie
0x180012d8b  add     rsp, 1C8h
0x180012d92  pop     r14
0x180012d94  pop     rdi
0x180012d95  pop     rsi
0x180012d96  pop     rbx
0x180012d97  retn
0x180012d98  mov     r9d, eax; char *
0x180012d9b  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\sharedpc\\accountma"...
0x180012da2  mov     edx, 0ACh; void *
0x180012da7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180012dac  mov     r9d, eax; char *
0x180012daf  lea     r8, aShellcommonShe_11; "shellcommon\\shell\\sharedpc\\accountma"...
0x180012db6  mov     edx, 0B7h; void *
0x180012dbb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
