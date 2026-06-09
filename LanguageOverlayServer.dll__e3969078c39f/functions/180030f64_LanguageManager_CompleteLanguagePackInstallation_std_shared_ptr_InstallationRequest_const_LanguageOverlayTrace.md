# LanguageManager::_CompleteLanguagePackInstallation(std::shared_ptr<InstallationRequest> const &,LanguageOverlayTraceProvider::LanguagePackInstallationRequest &,long)

- ea: `0x180030f64`
- end: `0x1800312b2`
- name: `?_CompleteLanguagePackInstallation@LanguageManager@@CAXAEBV?$shared_ptr@VInstallationRequest@@@std@@AEAVLanguagePackInstallationRequest@LanguageOverlayTraceProvider@@J@Z`
- size: `846`
- prototype: `void __fastcall(_QWORD **, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002db90`
- `0x180065564`

## callees

- `0x180003a00`
- `0x18000a024`
- `0x180012a98`
- `0x180016f74`
- `0x18001a570`
- `0x18002be08`
- `0x18002d5ac`
- `0x18002ebf8`
- `0x180030f64`
- `0x180037aac`
- `0x180062f00`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180031047`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180031047`
- `ntdll!NtGetMUIRegistryInfo` at `0x180030fb3`
- `ntdll!NtGetMUIRegistryInfo` at `0x180030fb3`
- `msvcp_win!_Mtx_unlock` at `0x18003117f`
- `msvcp_win!_Mtx_unlock` at `0x180031242`
- `msvcp_win!_Mtx_unlock` at `0x18003117f`
- `msvcp_win!_Mtx_unlock` at `0x180031242`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180030fd7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180030ff8`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800311f7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180031218`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180030fd7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180030ff8`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800311f7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180031218`
- `msvcp_win!_Mtx_lock` at `0x180030fc8`
- `msvcp_win!_Mtx_lock` at `0x1800311e8`
- `msvcp_win!_Mtx_lock` at `0x180030fc8`
- `msvcp_win!_Mtx_lock` at `0x1800311e8`

## string_xrefs

- `0x1800311b6`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagemanager.cpp`
- `0x18003129f`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall LanguageManager::_CompleteLanguagePackInstallation(_QWORD **a1, __int64 a2, unsigned int a3)
{
  __int64 v4; // r14
  __int64 *v6; // rbx
  __int64 v7; // rdi
  _QWORD *v8; // rdx
  _QWORD *v9; // rcx
  __int64 v10; // r8
  const wchar_t *v11; // rdx
  const wchar_t *v12; // rcx
  size_t v13; // r8
  __int64 v14; // r15
  __int64 *v15; // rsi
  __int64 v16; // rax
  __int64 v17; // rcx
  volatile signed __int32 *v18; // r14
  volatile signed __int32 *v19; // rbx
  _QWORD *v20; // rax
  __int64 v21; // rdx
  int v22; // eax
  _QWORD *i; // rbx
  const char *v24; // r9
  __int128 v26; // [rsp+30h] [rbp-58h] BYREF
  __int64 v27; // [rsp+40h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  try
  {
    v4 = a2;
    if ( !(*a1)[13] )
      MicrosoftTelemetryAssertTriggeredNoArgs(a1);
    *((_DWORD *)*a1 + 38) = a3;
    NtGetMUIRegistryInfo(10, 0, 0);
    if ( _Mtx_lock((_Mtx_t)&LanguageManager::s_installationLock) )
      std::_Throw_Cpp_error(5);
    if ( dword_180089E7C == 0x7FFFFFFF )
    {
      dword_180089E7C = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v6 = (__int64 *)LanguageManager::s_installRequests;
    v7 = qword_18008A3A8;
    while ( v6 != (__int64 *)v7 )
    {
      v8 = *a1 + 11;
      v9 = (_QWORD *)(*v6 + 88);
      if ( (*a1)[14] > 7u )
        v8 = (_QWORD *)*v8;
      v10 = *(_QWORD *)(*v6 + 104);
      if ( *(_QWORD *)(*v6 + 112) > 7u )
        v9 = (_QWORD *)*v9;
      if ( v10 == (*a1)[13] && (!v10 || !(unsigned int)_o__wcsnicmp(v9, v8)) )
      {
        v11 = (const wchar_t *)(*a1 + 2);
        v12 = (const wchar_t *)(*v6 + 16);
        if ( (*a1)[5] > 7u )
          v11 = *(const wchar_t **)v11;
        v13 = *(_QWORD *)(*v6 + 32);
        if ( *(_QWORD *)(*v6 + 40) > 7u )
          v12 = *(const wchar_t **)v12;
        if ( v13 == (*a1)[4] && (!v13 || !wmemcmp(v12, v11, v13)) )
          break;
      }
      v6 += 2;
    }
    v14 = qword_18008A3A8;
    if ( v6 == (__int64 *)qword_18008A3A8 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30F,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
        (const char *)0x80070490LL,
        a2);
    v15 = v6 + 2;
    if ( v6 + 2 != (__int64 *)qword_18008A3A8 )
    {
      do
      {
        v16 = *v15;
        v17 = v15[1];
        *v15 = 0;
        v15[1] = 0;
        *v6 = v16;
        v18 = (volatile signed __int32 *)v6[1];
        v6[1] = v17;
        if ( v18 )
        {
          if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
            if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
          }
        }
        v6 += 2;
        v15 += 2;
      }
      while ( v15 != (__int64 *)v14 );
      v4 = a2;
    }
    v19 = *(volatile signed __int32 **)(qword_18008A3A8 - 8);
    if ( v19 )
    {
      if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    qword_18008A3A8 -= 16;
    _Mtx_unlock((_Mtx_t)&LanguageManager::s_installationLock);
    if ( *((_BYTE *)*a1 + 120) )
    {
      v20 = (_QWORD *)**a1;
      v21 = v20 ? *v20 : 0LL;
      v22 = SetDisplayLanguage((const wchar_t *)*a1 + 44, v21);
      if ( v22 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x315,
          (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
          (const char *)(unsigned int)v22,
          a2);
    }
    v26 = 0;
    v27 = 0;
    if ( _Mtx_lock((_Mtx_t)&LanguageManager::s_eventRegistrationLock) )
      std::_Throw_Cpp_error(5);
    if ( dword_180089ECC == 0x7FFFFFFF )
    {
      dword_180089ECC = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    std::vector<std::shared_ptr<ProgressEventRegistration>>::_Assign_counted_range<std::shared_ptr<ProgressEventRegistration> *>(
      &v26,
      LanguageManager::s_eventRegistrations,
      (qword_18008A3C0 - (__int64)LanguageManager::s_eventRegistrations) >> 4);
    _Mtx_unlock((_Mtx_t)&LanguageManager::s_eventRegistrationLock);
    for ( i = (_QWORD *)v26; i != *((_QWORD **)&v26 + 1); i += 2 )
      ProgressEventRegistration::FireLanguagePackInstallComplete(*i, a1);
    wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v4,
      a3);
    std::vector<std::shared_ptr<InstallationRequest>>::~vector<std::shared_ptr<InstallationRequest>>((__int64 *)&v26);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x326,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languagemanager.cpp",
      v24);
  }
}

```

## disassembly

```asm
0x180030f64  push    rbx
0x180030f66  push    rsi
0x180030f67  push    rdi
0x180030f68  push    r12
0x180030f6a  push    r13
0x180030f6c  push    r14
0x180030f6e  push    r15
0x180030f70  sub     rsp, 50h
0x180030f74  mov     rax, cs:__security_cookie
0x180030f7b  xor     rax, rsp
0x180030f7e  mov     [rsp+88h+var_40], rax
0x180030f83  mov     r13d, r8d
0x180030f86  mov     r14, rdx
0x180030f89  mov     [rsp+88h+var_68], rdx
0x180030f8e  mov     r12, rcx
0x180030f91  mov     rax, [rcx]
0x180030f94  cmp     qword ptr [rax+68h], 0
0x180030f99  jnz     short loc_180030FA0
0x180030f9b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180030fa0  mov     rax, [r12]
0x180030fa4  mov     [rax+98h], r13d
0x180030fab  xor     r8d, r8d
0x180030fae  xor     edx, edx
0x180030fb0  lea     ecx, [rdx+0Ah]
0x180030fb3  call    cs:__imp_NtGetMUIRegistryInfo
0x180030fb9  lea     rax, ?s_installationLock@LanguageManager@@0Vrecursive_mutex@std@@A; std::recursive_mutex LanguageManager::s_installationLock
0x180030fc0  mov     [rsp+88h+var_60], rax
0x180030fc5  mov     rcx, rax; _Mtx_t
0x180030fc8  call    cs:__imp__Mtx_lock
0x180030fce  test    eax, eax
0x180030fd0  jz      short loc_180030FDD
0x180030fd2  mov     ecx, 5
0x180030fd7  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180030fdd  cmp     cs:dword_180089E7C, 7FFFFFFFh
0x180030fe7  jnz     short loc_180030FFF
0x180030fe9  mov     cs:dword_180089E7C, 7FFFFFFEh
0x180030ff3  mov     ecx, 6
0x180030ff8  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180030ffe  nop
0x180030fff  mov     rbx, cs:?s_installRequests@LanguageManager@@0V?$vector@V?$shared_ptr@VInstallationRequest@@@std@@V?$allocator@V?$shared_ptr@VInstallationRequest@@@std@@@2@@std@@A; std::vector<std::shared_ptr<InstallationRequest>> LanguageManager::s_installRequests
0x180031006  mov     rdi, cs:qword_18008A3A8
0x18003100d  jmp     loc_180031093
0x180031012  mov     rdx, [r12]
0x180031016  add     rdx, 58h ; 'X'
0x18003101a  mov     rcx, [rbx]
0x18003101d  add     rcx, 58h ; 'X'
0x180031021  mov     rax, [rdx+10h]
0x180031025  cmp     qword ptr [rdx+18h], 7
0x18003102a  jbe     short loc_18003102F
0x18003102c  mov     rdx, [rdx]
0x18003102f  mov     r8, [rcx+10h]
0x180031033  cmp     qword ptr [rcx+18h], 7
0x180031038  jbe     short loc_18003103D
0x18003103a  mov     rcx, [rcx]
0x18003103d  cmp     r8, rax
0x180031040  jnz     short loc_18003108F
0x180031042  test    r8, r8
0x180031045  jz      short loc_180031051
0x180031047  call    cs:__imp__o__wcsnicmp
0x18003104d  test    eax, eax
0x18003104f  jnz     short loc_18003108F
0x180031051  mov     rdx, [r12]
0x180031055  add     rdx, 10h
0x180031059  mov     rcx, [rbx]
0x18003105c  add     rcx, 10h
0x180031060  mov     rax, [rdx+10h]
0x180031064  cmp     qword ptr [rdx+18h], 7
0x180031069  jbe     short loc_18003106E
0x18003106b  mov     rdx, [rdx]; S2
0x18003106e  mov     r8, [rcx+10h]; N
0x180031072  cmp     qword ptr [rcx+18h], 7
0x180031077  jbe     short loc_18003107C
0x180031079  mov     rcx, [rcx]; S1
0x18003107c  cmp     r8, rax
0x18003107f  jnz     short loc_18003108F
0x180031081  test    r8, r8
0x180031084  jz      short loc_18003109C
0x180031086  call    wmemcmp
0x18003108b  test    eax, eax
0x18003108d  jz      short loc_18003109C
0x18003108f  add     rbx, 10h
0x180031093  cmp     rbx, rdi
0x180031096  jnz     loc_180031012
0x18003109c  mov     r15, cs:qword_18008A3A8
0x1800310a3  mov     rcx, [rsp+88h]; this
0x1800310ab  cmp     rbx, r15
0x1800310ae  jz      loc_180031299
0x1800310b4  lea     rsi, [rbx+10h]
0x1800310b8  or      edi, 0FFFFFFFFh
0x1800310bb  cmp     rsi, r15
0x1800310be  jz      short loc_18003112D
0x1800310c0  mov     rax, [rsi]
0x1800310c3  mov     rcx, [rsi+8]
0x1800310c7  mov     qword ptr [rsi], 0
0x1800310ce  mov     qword ptr [rsi+8], 0
0x1800310d6  mov     [rbx], rax
0x1800310d9  mov     r14, [rbx+8]
0x1800310dd  mov     [rbx+8], rcx
0x1800310e1  test    r14, r14
0x1800310e4  jz      short loc_18003111B
0x1800310e6  mov     eax, edi
0x1800310e8  lock xadd [r14+8], eax
0x1800310ee  add     eax, edi
0x1800310f0  jnz     short loc_18003111B
0x1800310f2  mov     rax, [r14]
0x1800310f5  mov     rcx, r14
0x1800310f8  mov     rax, [rax]
0x1800310fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031100  mov     eax, edi
0x180031102  lock xadd [r14+0Ch], eax
0x180031108  add     eax, edi
0x18003110a  jnz     short loc_18003111B
0x18003110c  mov     rax, [r14]
0x18003110f  mov     rcx, r14
0x180031112  mov     rax, [rax+8]
0x180031116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003111b  add     rbx, 10h
0x18003111f  add     rsi, 10h
0x180031123  cmp     rsi, r15
0x180031126  jnz     short loc_1800310C0
0x180031128  mov     r14, [rsp+88h+var_68]
0x18003112d  mov     rax, cs:qword_18008A3A8
0x180031134  mov     rbx, [rax-8]
0x180031138  test    rbx, rbx
0x18003113b  jz      short loc_180031170
0x18003113d  mov     eax, edi
0x18003113f  lock xadd [rbx+8], eax
0x180031144  add     eax, edi
0x180031146  jnz     short loc_180031170
0x180031148  mov     rax, [rbx]
0x18003114b  mov     rcx, rbx
0x18003114e  mov     rax, [rax]
0x180031151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031156  mov     eax, edi
0x180031158  lock xadd [rbx+0Ch], eax
0x18003115d  add     eax, edi
0x18003115f  jnz     short loc_180031170
0x180031161  mov     rax, [rbx]
0x180031164  mov     rcx, rbx
0x180031167  mov     rax, [rax+8]
0x18003116b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031170  sub     cs:qword_18008A3A8, 10h
0x180031178  lea     rcx, ?s_installationLock@LanguageManager@@0Vrecursive_mutex@std@@A; _Mtx_t
0x18003117f  call    cs:__imp__Mtx_unlock
0x180031185  mov     rax, [r12]
0x180031189  lea     rcx, [rax+58h]
0x18003118d  cmp     byte ptr [rcx+20h], 0
0x180031191  jz      short loc_1800311C7
0x180031193  mov     rax, [rax]
0x180031196  test    rax, rax
0x180031199  jz      short loc_1800311A0
0x18003119b  mov     rdx, [rax]
0x18003119e  jmp     short loc_1800311A2
0x1800311a0  xor     edx, edx
0x1800311a2  call    ?SetDisplayLanguage@@YAJAEBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@PEAX@Z; SetDisplayLanguage(std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &,void *)
0x1800311a7  mov     rcx, [rsp+88h]; this
0x1800311af  test    eax, eax
0x1800311b1  jns     short loc_1800311C7
0x1800311b3  mov     r9d, eax; char *
0x1800311b6  lea     r8, aOnecoreBaseLan_4; "onecore\\base\\languageoverlay\\service"...
0x1800311bd  mov     edx, 315h; void *
0x1800311c2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800311c7  xorps   xmm0, xmm0
0x1800311ca  movdqu  [rsp+88h+var_58], xmm0
0x1800311d0  mov     [rsp+88h+var_48], 0
0x1800311d9  lea     rbx, ?s_eventRegistrationLock@LanguageManager@@0Vrecursive_mutex@std@@A; std::recursive_mutex LanguageManager::s_eventRegistrationLock
0x1800311e0  mov     [rsp+88h+var_60], rbx
0x1800311e5  mov     rcx, rbx; _Mtx_t
0x1800311e8  call    cs:__imp__Mtx_lock
0x1800311ee  test    eax, eax
0x1800311f0  jz      short loc_1800311FD
0x1800311f2  mov     ecx, 5
0x1800311f7  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800311fd  cmp     cs:dword_180089ECC, 7FFFFFFFh
0x180031207  jnz     short loc_18003121F
0x180031209  mov     cs:dword_180089ECC, 7FFFFFFEh
0x180031213  mov     ecx, 6
0x180031218  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003121e  nop
0x18003121f  mov     rdx, cs:?s_eventRegistrations@LanguageManager@@0V?$vector@V?$shared_ptr@VProgressEventRegistration@@@std@@V?$allocator@V?$shared_ptr@VProgressEventRegistration@@@std@@@2@@std@@A; std::vector<std::shared_ptr<ProgressEventRegistration>> LanguageManager::s_eventRegistrations
0x180031226  mov     r8, cs:qword_18008A3C0
0x18003122d  sub     r8, rdx
0x180031230  sar     r8, 4
0x180031234  lea     rcx, [rsp+88h+var_58]
0x180031239  call    ??$_Assign_counted_range@PEAV?$shared_ptr@VProgressEventRegistration@@@std@@@?$vector@V?$shared_ptr@VProgressEventRegistration@@@std@@V?$allocator@V?$shared_ptr@VProgressEventRegistration@@@std@@@2@@std@@AEAAXPEAV?$shared_ptr@VProgressEventRegistration@@@1@_K@Z; std::vector<std::shared_ptr<ProgressEventRegistration>>::_Assign_counted_range<std::shared_ptr<ProgressEventRegistration> *>(std::shared_ptr<ProgressEventRegistration> *,unsigned __int64)
0x18003123e  nop
0x18003123f  mov     rcx, rbx; _Mtx_t
0x180031242  call    cs:__imp__Mtx_unlock
0x180031248  mov     rbx, qword ptr [rsp+88h+var_58]
0x18003124d  jmp     short loc_18003125E
0x18003124f  mov     rdx, r12
0x180031252  mov     rcx, [rbx]
0x180031255  call    ?FireLanguagePackInstallComplete@ProgressEventRegistration@@QEAAXAEBV?$shared_ptr@VInstallationRequest@@@std@@@Z; ProgressEventRegistration::FireLanguagePackInstallComplete(std::shared_ptr<InstallationRequest> const &)
0x18003125a  add     rbx, 10h
0x18003125e  cmp     rbx, qword ptr [rsp+88h+var_58+8]
0x180031263  jnz     short loc_18003124F
0x180031265  mov     edx, r13d
0x180031268  mov     rcx, r14
0x18003126b  call    ?Stop@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180031270  nop
0x180031271  lea     rcx, [rsp+88h+var_58]
0x180031276  call    ??1?$vector@V?$shared_ptr@VInstallationRequest@@@std@@V?$allocator@V?$shared_ptr@VInstallationRequest@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<InstallationRequest>>::~vector<std::shared_ptr<InstallationRequest>>(void)
0x18003127b  nop
0x18003127c  mov     rcx, [rsp+88h+var_40]
0x180031281  xor     rcx, rsp; StackCookie
0x180031284  call    __security_check_cookie
0x180031289  add     rsp, 50h
0x18003128d  pop     r15
0x18003128f  pop     r14
0x180031291  pop     r13
0x180031293  pop     r12
0x180031295  pop     rdi
0x180031296  pop     rsi
0x180031297  pop     rbx
0x180031298  retn
0x180031299  mov     r9d, 80070490h; char *
0x18003129f  lea     r8, aOnecoreBaseLan_4; "onecore\\base\\languageoverlay\\service"...
0x1800312a6  mov     edx, 30Fh; void *
0x1800312ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
