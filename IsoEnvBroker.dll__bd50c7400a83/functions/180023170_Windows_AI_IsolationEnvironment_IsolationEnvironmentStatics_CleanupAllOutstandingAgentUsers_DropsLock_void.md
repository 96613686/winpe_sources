# Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::CleanupAllOutstandingAgentUsers_DropsLock(void)

- ea: `0x180023170`
- end: `0x18002371c`
- name: `?CleanupAllOutstandingAgentUsers_DropsLock@IsolationEnvironmentStatics@IsolationEnvironment@AI@Windows@@SAXXZ`
- size: `1452`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180061100`
- `0x180062ba8`

## callees

- `0x180002520`
- `0x1800075e4`
- `0x18000e50c`
- `0x18001045c`
- `0x180011e18`
- `0x180014c04`
- `0x180015314`
- `0x18001eb90`
- `0x18001f998`
- `0x180020b68`
- `0x180023170`
- `0x180026974`
- `0x1800293e4`
- `0x18002956c`
- `0x18002fc24`
- `0x180040c90`
- `0x1800615a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800231da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023211`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002329b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800232cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002360f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800231da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023211`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002329b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800232cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002360f`

## string_xrefs

- `0x1800236bc`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x1800236ce`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x1800236e0`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x1800236f8`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x18002370a`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x18002342b`: `Could not recall account name for agent %s for owning user %s`
- `0x18002359c`: `Deleted AU account %s for owning user %s`
- `0x180023678`: `Failed to set service to demand start: %#x`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::CleanupAllOutstandingAgentUsers_DropsLock(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  char v3; // r13
  const char *v4; // r9
  int v5; // ebx
  _QWORD *v7; // rdi
  int v8; // ebx
  bool v9; // al
  AgentAccountRegistry *v10; // rcx
  __int64 v11; // r14
  __m128i si128; // xmm6
  _QWORD *v13; // r12
  char **v14; // rsi
  char **v15; // rbx
  __int64 v16; // r15
  int v17; // ebx
  _QWORD *v19; // rbx
  int v20; // esi
  bool v21; // al
  _QWORD *v22; // rsi
  const WCHAR **v23; // r15
  const WCHAR *v24; // r8
  _QWORD *v25; // rax
  char **v26; // r9
  const WCHAR *v27; // r8
  const WCHAR *v28; // r8
  _QWORD *v29; // r9
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 *i; // rbx
  __int64 *v33; // rsi
  int v34; // eax
  __int64 v35; // r9
  _QWORD *v36; // r9
  __int64 *v37; // r8
  _QWORD *v38; // rax
  __int64 *v39; // r8
  const char *v40; // r9
  int v41; // ebx
  int v42; // ebx
  _QWORD *j; // rax
  bool v44; // al
  bool v45; // zf
  int started; // eax
  int v47; // [rsp+38h] [rbp-D0h]
  int v48; // [rsp+38h] [rbp-D0h]
  _QWORD *v49; // [rsp+40h] [rbp-C8h] BYREF
  __int128 v50; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v51; // [rsp+58h] [rbp-B0h]
  char *v52[4]; // [rsp+60h] [rbp-A8h] BYREF
  char v53; // [rsp+80h] [rbp-88h]
  char *v54[2]; // [rsp+88h] [rbp-80h] BYREF
  __m128i v55; // [rsp+98h] [rbp-70h]
  char *v56[2]; // [rsp+A8h] [rbp-60h] BYREF
  __m128i v57; // [rsp+B8h] [rbp-50h]
  char *v58[2]; // [rsp+C8h] [rbp-40h] BYREF
  __m128i v59; // [rsp+D8h] [rbp-30h]
  __int64 v60; // [rsp+E8h] [rbp-20h]
  __int128 v61; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v62; // [rsp+108h] [rbp+0h]
  __int64 v63; // [rsp+110h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+180h] [rbp+78h]

  v47 = 0;
  LOBYTE(a3) = 3;
  v3 = 1;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_IsoBrokerV3Apis>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_IsoBrokerV3Apis>::GetImpl'::`2'::impl,
    a2,
    a3);
  v50 = 0;
  v51 = 0;
  if ( dword_1800B9164 <= 0 )
  {
    v5 = dword_1800B9160;
    if ( v5 != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x175,
        (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
        v4);
  }
  v7 = *(_QWORD **)qword_1800B9470;
  v9 = 0;
  if ( dword_1800B9164 <= 0 )
  {
    v8 = dword_1800B9160;
    if ( v8 != GetCurrentThreadId() )
      v9 = 1;
  }
  v10 = retaddr;
  if ( v9 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x175,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
      v4);
  v11 = qword_1800B9470;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( v7 != (_QWORD *)v11 )
  {
    v13 = v7 + 2;
    v14 = (char **)*((_QWORD *)&v50 + 1);
    v15 = (char **)v50;
    if ( (_QWORD)v50 != *((_QWORD *)&v50 + 1) )
    {
      do
      {
        std::wstring::~wstring(v15 + 8);
        std::wstring::~wstring(v15 + 4);
        std::wstring::~wstring(v15);
        v15 += 13;
      }
      while ( v15 != v14 );
      *((_QWORD *)&v50 + 1) = v50;
    }
    v16 = v7[6];
    if ( dword_1800B9164 <= 0 )
    {
      v17 = dword_1800B9160;
      if ( v17 != GetCurrentThreadId() )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x175,
          (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
          v4);
    }
    v19 = **(_QWORD ***)(v16 + 112);
    v21 = 0;
    if ( dword_1800B9164 <= 0 )
    {
      v20 = dword_1800B9160;
      if ( v20 != GetCurrentThreadId() )
        v21 = 1;
    }
    v10 = retaddr;
    if ( v21 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x175,
        (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
        v4);
    v22 = *(_QWORD **)(v16 + 112);
    while ( v19 != v22 )
    {
      v23 = (const WCHAR **)(v19 + 2);
      if ( v19[5] <= 7u )
        v24 = (const WCHAR *)(v19 + 2);
      else
        v24 = *v23;
      v49 = *(_QWORD **)v7[6];
      wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<std::wstring>(
        (HKEY *)&v49,
        (__int64)v52,
        v24,
        (const WCHAR *)&stru_18009A8D0,
        0x10000006u);
      v48 = v47 | 2;
      v25 = v19 + 5;
      v49 = v19 + 5;
      if ( v53 )
      {
        v26 = v52;
        if ( v52[3] > (char *)7 )
          v26 = (char **)v52[0];
        if ( *v25 <= 7u )
          v27 = (const WCHAR *)(v19 + 2);
        else
          v27 = *v23;
        Log(4u, L"Recalled account name for %s: %s", v27, v26);
        if ( !v53 )
          std::_Throw_bad_optional_access();
        std::wstring::wstring((__int64)&v61, (__int64)v52);
      }
      else
      {
        if ( *v25 <= 7u )
          v28 = (const WCHAR *)(v19 + 2);
        else
          v28 = *v23;
        Log(4u, L"No recorded account name for %s", v28);
        v61 = 0;
        v62 = 0;
        v63 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v61, &word_180096C4C, 0);
      }
      v47 = v48 | 1;
      if ( v53 )
        std::wstring::~wstring(v52);
      if ( v62 )
      {
        std::wstring::wstring((__int64)v54, (__int64)(v19 + 2));
        std::wstring::wstring((__int64)v56, (__int64)&v61);
        std::wstring::wstring((__int64)v58, (__int64)(v19 + 6));
        v30 = v7[6];
        v60 = v30;
        v31 = *((_QWORD *)&v50 + 1);
        if ( *((_QWORD *)&v50 + 1) == v51 )
        {
          std::vector__Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::CleanupAllOutstandingAgentUsers_DropsLock_::_2_::AgentInfoV3_std::allocator__Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::CleanupAllOutstandingAgentUsers_DropsLock_::_2_::AgentInfoV3___::_Emplace_reallocate__Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::CleanupAllOutstandingAgentUsers_DropsLock_::_2_::AgentInfoV3_(
            &v50,
            *((_QWORD *)&v50 + 1),
            v54);
        }
        else
        {
          **((_QWORD **)&v50 + 1) = v54[0];
          *(char **)(v31 + 8) = v54[1];
          *(__m128i *)(v31 + 16) = v55;
          v55 = si128;
          LOWORD(v54[0]) = 0;
          *(char **)(v31 + 32) = v56[0];
          *(char **)(v31 + 40) = v56[1];
          *(__m128i *)(v31 + 48) = v57;
          v57 = si128;
          LOWORD(v56[0]) = 0;
          *(char **)(v31 + 64) = v58[0];
          *(char **)(v31 + 72) = v58[1];
          *(__m128i *)(v31 + 80) = v59;
          v59 = si128;
          LOWORD(v58[0]) = 0;
          *(_QWORD *)(v31 + 96) = v30;
          *((_QWORD *)&v50 + 1) += 104LL;
        }
        std::wstring::~wstring(v58);
        std::wstring::~wstring(v56);
        std::wstring::~wstring(v54);
      }
      else
      {
        if ( v7[5] <= 7u )
          v29 = v7 + 2;
        else
          v29 = (_QWORD *)*v13;
        if ( *v49 > 7u )
          v23 = (const WCHAR **)*v23;
        Log(3u, L"Could not recall account name for agent %s for owning user %s", v23, v29);
      }
      std::wstring::~wstring((char **)&v61);
      v19 = (_QWORD *)*v19;
    }
    v33 = (__int64 *)*((_QWORD *)&v50 + 1);
    for ( i = (__int64 *)v50; i != v33; i += 13 )
    {
      v34 = AgentAccountHelpers::CleanupAgentUserForUser_DropsLock(
              (int)v7 + 16,
              (_DWORD)i,
              (int)i + 64,
              (int)i + 32,
              (struct OwningUserRegistry *)i[12]);
      v35 = (unsigned int)v34;
      if ( v34 < 0 )
      {
        if ( v7[5] <= 7u )
          v38 = v7 + 2;
        else
          v38 = (_QWORD *)*v13;
        if ( (unsigned __int64)i[3] <= 7 )
          v39 = i;
        else
          v39 = (__int64 *)*i;
        Log(2u, L"Failed to clean up AU account %s, error %#x, for owning user %s", v39, v35, v38);
      }
      else
      {
        if ( v7[5] <= 7u )
          v36 = v7 + 2;
        else
          v36 = (_QWORD *)*v13;
        if ( (unsigned __int64)i[3] <= 7 )
          v37 = i;
        else
          v37 = (__int64 *)*i;
        Log(4u, L"Deleted AU account %s for owning user %s", v37, v36);
      }
    }
    v7 = (_QWORD *)*v7;
  }
  AgentAccountRegistry::RemoveEmptyKeys(v10);
  if ( dword_1800B9164 > 0 || (v41 = dword_1800B9160, v41 == GetCurrentThreadId()) )
    v3 = 0;
  if ( v3 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x175,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
      v40);
  v42 = 0;
  for ( j = *(_QWORD **)qword_1800B9470; j != (_QWORD *)qword_1800B9470; j = (_QWORD *)*j )
    v42 += *(_DWORD *)(j[6] + 120LL);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59959135>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59959135>::GetImpl'::`2'::impl) )
  {
    v44 = MopUpMemUserProfiles();
    if ( v42 )
      goto LABEL_90;
    v45 = !v44;
  }
  else
  {
    v45 = v42 == 0;
  }
  if ( v45 )
  {
    started = SetServiceStartType(3u);
    if ( started < 0 )
      Log(2u, L"Failed to set service to demand start: %#x", (unsigned int)started);
  }
LABEL_90:
  std::vector__Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::CleanupAllOutstandingAgentUsers_DropsLock_::_2_::AgentInfoV3_std::allocator__Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::CleanupAllOutstandingAgentUsers_DropsLock_::_2_::AgentInfoV3___::_vector__Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::CleanupAllOutstandingAgentUsers_DropsLock_::_2_::AgentInfoV3_std::allocator__Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::CleanupAllOutstandingAgentUsers_DropsLock_::_2_::AgentInfoV3___(&v50);
}

```

## disassembly

```asm
0x180023170  mov     rax, rsp
0x180023173  push    rbp
0x180023174  push    rbx
0x180023175  push    rsi
0x180023176  push    rdi
0x180023177  push    r12
0x180023179  push    r13
0x18002317b  push    r14
0x18002317d  push    r15
0x18002317f  lea     rbp, [rax-78h]
0x180023183  sub     rsp, 138h
0x18002318a  movaps  xmmword ptr [rax-58h], xmm6
0x18002318e  mov     rax, cs:__security_cookie
0x180023195  xor     rax, rsp
0x180023198  mov     [rbp+70h+var_60], rax
0x18002319c  xor     eax, eax
0x18002319e  mov     dword ptr [rsp+170h+var_140], eax
0x1800231a2  mov     r8b, 3
0x1800231a5  lea     r13d, [rax+1]
0x1800231a9  mov     dl, r13b
0x1800231ac  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_IsoBrokerV3Apis@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_IsoBrokerV3Apis@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IsoBrokerV3Apis> `wil::Feature<__WilFeatureTraits_Feature_IsoBrokerV3Apis>::GetImpl(void)'::`2'::impl
0x1800231b3  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_IsoBrokerV3Apis@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IsoBrokerV3Apis>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800231b8  xorps   xmm0, xmm0
0x1800231bb  movdqu  [rsp+170h+var_138+8], xmm0
0x1800231c1  mov     [rsp+170h+var_120], 0
0x1800231ca  mov     eax, cs:dword_1800B9164
0x1800231d0  test    eax, eax
0x1800231d2  jg      short loc_1800231E9
0x1800231d4  mov     ebx, cs:dword_1800B9160
0x1800231da  call    cs:__imp_GetCurrentThreadId
0x1800231e0  cmp     ebx, eax
0x1800231e2  jz      short loc_1800231E9
0x1800231e4  mov     al, r13b
0x1800231e7  jmp     short loc_1800231EB
0x1800231e9  xor     al, al
0x1800231eb  mov     rcx, [rbp+78h]; this
0x1800231ef  test    al, al
0x1800231f1  jnz     loc_1800236CE
0x1800231f7  mov     rdi, cs:qword_1800B9470
0x1800231fe  mov     rdi, [rdi]
0x180023201  mov     eax, cs:dword_1800B9164
0x180023207  test    eax, eax
0x180023209  jg      short loc_180023220
0x18002320b  mov     ebx, cs:dword_1800B9160
0x180023211  call    cs:__imp_GetCurrentThreadId
0x180023217  cmp     ebx, eax
0x180023219  jz      short loc_180023220
0x18002321b  mov     al, r13b
0x18002321e  jmp     short loc_180023222
0x180023220  xor     al, al
0x180023222  mov     rcx, [rbp+78h]; this
0x180023226  test    al, al
0x180023228  jnz     loc_1800236E0
0x18002322e  mov     r14, cs:qword_1800B9470
0x180023235  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18002323d  cmp     rdi, r14
0x180023240  jz      loc_1800235FA
0x180023246  lea     r12, [rdi+10h]
0x18002324a  mov     rsi, [rsp+170h+var_128]
0x18002324f  mov     rbx, qword ptr [rsp+170h+var_138+8]
0x180023254  cmp     rbx, rsi
0x180023257  jz      short loc_180023286
0x180023259  lea     rcx, [rbx+40h]
0x18002325d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023262  lea     rcx, [rbx+20h]
0x180023266  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002326b  mov     rcx, rbx
0x18002326e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023273  add     rbx, 68h ; 'h'
0x180023277  cmp     rbx, rsi
0x18002327a  jnz     short loc_180023259
0x18002327c  mov     rax, qword ptr [rsp+170h+var_138+8]
0x180023281  mov     [rsp+170h+var_128], rax
0x180023286  mov     r15, [r12+20h]
0x18002328b  mov     eax, cs:dword_1800B9164
0x180023291  test    eax, eax
0x180023293  jg      short loc_1800232AA
0x180023295  mov     ebx, cs:dword_1800B9160
0x18002329b  call    cs:__imp_GetCurrentThreadId
0x1800232a1  cmp     ebx, eax
0x1800232a3  jz      short loc_1800232AA
0x1800232a5  mov     al, r13b
0x1800232a8  jmp     short loc_1800232AC
0x1800232aa  xor     al, al
0x1800232ac  mov     rcx, [rbp+78h]; this
0x1800232b0  test    al, al
0x1800232b2  jnz     loc_18002370A
0x1800232b8  mov     rbx, [r15+70h]
0x1800232bc  mov     rbx, [rbx]
0x1800232bf  mov     eax, cs:dword_1800B9164
0x1800232c5  test    eax, eax
0x1800232c7  jg      short loc_1800232DE
0x1800232c9  mov     esi, cs:dword_1800B9160
0x1800232cf  call    cs:__imp_GetCurrentThreadId
0x1800232d5  cmp     esi, eax
0x1800232d7  jz      short loc_1800232DE
0x1800232d9  mov     al, r13b
0x1800232dc  jmp     short loc_1800232E0
0x1800232de  xor     al, al
0x1800232e0  mov     rcx, [rbp+78h]; this
0x1800232e4  test    al, al
0x1800232e6  jnz     loc_1800236F8
0x1800232ec  mov     rsi, [r15+70h]
0x1800232f0  cmp     rbx, rsi
0x1800232f3  jz      loc_18002354A
0x1800232f9  lea     r15, [rbx+10h]
0x1800232fd  mov     rax, [r12+20h]
0x180023302  cmp     qword ptr [rbx+28h], 7
0x180023307  jbe     short loc_18002330E
0x180023309  mov     r8, [r15]
0x18002330c  jmp     short loc_180023311
0x18002330e  mov     r8, r15
0x180023311  mov     rax, [rax]
0x180023314  mov     qword ptr [rsp+170h+var_138], rax
0x180023319  mov     dword ptr [rsp+20h], 10000006h
0x180023321  lea     r9, stru_18009A8D0
0x180023328  lea     rdx, [rsp+58h]
0x18002332d  lea     rcx, [rsp+170h+var_138]
0x180023332  call    ??$try_get_value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEB_W0K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<std::wstring>(wchar_t const *,wchar_t const *,ulong)
0x180023337  mov     eax, dword ptr [rsp+170h+var_140]
0x18002333b  or      eax, 2
0x18002333e  mov     dword ptr [rsp+170h+var_140], eax
0x180023342  lea     rax, [r15+18h]
0x180023346  mov     qword ptr [rsp+170h+var_138], rax
0x18002334b  cmp     [rsp+170h+var_F8], 0
0x180023350  jz      short loc_18002339D
0x180023352  lea     r9, [rsp+58h]
0x180023357  cmp     qword ptr [rsp+170h+var_100], 7
0x18002335d  cmova   r9, [rsp+58h]
0x180023363  cmp     qword ptr [rax], 7
0x180023367  jbe     short loc_18002336E
0x180023369  mov     r8, [r15]
0x18002336c  jmp     short loc_180023371
0x18002336e  mov     r8, r15
0x180023371  lea     rdx, aRecalledAccoun; "Recalled account name for %s: %s"
0x180023378  mov     ecx, 4; unsigned __int8
0x18002337d  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180023382  cmp     [rsp+170h+var_F8], 0
0x180023387  jz      loc_1800236F2
0x18002338d  lea     rdx, [rsp+58h]
0x180023392  lea     rcx, [rbp+70h+var_80]
0x180023396  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002339b  jmp     short loc_1800233E6
0x18002339d  cmp     qword ptr [rax], 7
0x1800233a1  jbe     short loc_1800233A8
0x1800233a3  mov     r8, [r15]
0x1800233a6  jmp     short loc_1800233AB
0x1800233a8  mov     r8, r15
0x1800233ab  lea     rdx, aNoRecordedAcco; "No recorded account name for %s"
0x1800233b2  mov     ecx, 4; unsigned __int8
0x1800233b7  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800233bc  xorps   xmm0, xmm0
0x1800233bf  movups  [rbp+70h+var_80], xmm0
0x1800233c3  mov     [rbp+70h+var_70], 0
0x1800233cb  mov     [rbp+70h+var_68], 0
0x1800233d3  xor     r8d, r8d
0x1800233d6  lea     rdx, word_180096C4C
0x1800233dd  lea     rcx, [rbp+70h+var_80]
0x1800233e1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800233e6  mov     eax, dword ptr [rsp+170h+var_140]
0x1800233ea  or      eax, r13d
0x1800233ed  mov     dword ptr [rsp+170h+var_140], eax
0x1800233f1  cmp     [rsp+170h+var_F8], 0
0x1800233f6  jz      short loc_180023402
0x1800233f8  lea     rcx, [rsp+58h]
0x1800233fd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023402  mov     rax, qword ptr [rsp+170h+var_138]
0x180023407  cmp     [rbp+70h+var_70], 0
0x18002340c  jnz     short loc_180023441
0x18002340e  cmp     qword ptr [r12+18h], 7
0x180023414  jbe     short loc_18002341C
0x180023416  mov     r9, [r12]
0x18002341a  jmp     short loc_18002341F
0x18002341c  mov     r9, r12
0x18002341f  cmp     qword ptr [rax], 7
0x180023423  jbe     short loc_180023428
0x180023425  mov     r15, [r15]
0x180023428  mov     r8, r15
0x18002342b  lea     rdx, aCouldNotRecall; "Could not recall account name for agent"...
0x180023432  mov     ecx, 3; unsigned __int8
0x180023437  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18002343c  jmp     loc_180023539
0x180023441  mov     rdx, r15
0x180023444  lea     rcx, [rbp+70h+var_F0]
0x180023448  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002344d  nop
0x18002344e  lea     rdx, [rbp+70h+var_80]
0x180023452  lea     rcx, [rbp+70h+var_D0]
0x180023456  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002345b  nop
0x18002345c  lea     rdx, [rbx+30h]
0x180023460  lea     rcx, [rbp+70h+var_B0]
0x180023464  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180023469  mov     rcx, [r12+20h]
0x18002346e  mov     [rbp+70h+var_90], rcx
0x180023472  mov     rdx, [rsp+170h+var_128]
0x180023477  cmp     rdx, [rsp+170h+var_120]
0x18002347c  jz      loc_18002350E
0x180023482  mov     rax, [rbp+70h+var_F0]
0x180023486  mov     [rdx], rax
0x180023489  mov     rax, [rbp+70h+var_E8]
0x18002348d  mov     [rdx+8], rax
0x180023491  mov     rax, qword ptr [rbp+70h+var_E0]
0x180023495  mov     [rdx+10h], rax
0x180023499  mov     rax, qword ptr [rbp+70h+var_E0+8]
0x18002349d  mov     [rdx+18h], rax
0x1800234a1  movdqa  [rbp+70h+var_E0], xmm6
0x1800234a6  xor     eax, eax
0x1800234a8  mov     word ptr [rbp+70h+var_F0], ax
0x1800234ac  mov     rax, [rbp+70h+var_D0]
0x1800234b0  mov     [rdx+20h], rax
0x1800234b4  mov     rax, [rbp+70h+var_C8]
0x1800234b8  mov     [rdx+28h], rax
0x1800234bc  mov     rax, qword ptr [rbp+70h+var_C0]
0x1800234c0  mov     [rdx+30h], rax
0x1800234c4  mov     rax, qword ptr [rbp+70h+var_C0+8]
0x1800234c8  mov     [rdx+38h], rax
0x1800234cc  movdqa  [rbp+70h+var_C0], xmm6
0x1800234d1  xor     eax, eax
0x1800234d3  mov     word ptr [rbp+70h+var_D0], ax
0x1800234d7  mov     rax, [rbp+70h+var_B0]
0x1800234db  mov     [rdx+40h], rax
0x1800234df  mov     rax, [rbp+70h+var_A8]
0x1800234e3  mov     [rdx+48h], rax
0x1800234e7  mov     rax, qword ptr [rbp+70h+var_A0]
0x1800234eb  mov     [rdx+50h], rax
0x1800234ef  mov     rax, qword ptr [rbp+70h+var_A0+8]
0x1800234f3  mov     [rdx+58h], rax
0x1800234f7  movdqa  [rbp+70h+var_A0], xmm6
0x1800234fc  xor     eax, eax
0x1800234fe  mov     word ptr [rbp+70h+var_B0], ax
0x180023502  mov     [rdx+60h], rcx
0x180023506  add     [rsp+170h+var_128], 68h ; 'h'
0x18002350c  jmp     short loc_18002351D
0x18002350e  lea     r8, [rbp+70h+var_F0]
0x180023512  lea     rcx, [rsp+170h+var_138+8]
0x180023517  call    std__vector__Windows__AI__IsolationEnvironment__IsolationEnvironmentStatics__CleanupAllOutstandingAgentUsers_DropsLock____2___AgentInfoV3_std__allocator__Windows__AI__IsolationEnvironment__IsolationEnvironmentStatics__CleanupAllOutstandingAgentUsers_DropsLock____2___AgentInfoV3______Emplace_reallocate__Windows__AI__IsolationEnvironment__IsolationEnvironmentStatics__CleanupAllOutstandingAgentUsers_DropsLock____2___AgentInfoV3_
0x18002351c  nop
0x18002351d  lea     rcx, [rbp+70h+var_B0]
0x180023521  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023526  lea     rcx, [rbp+70h+var_D0]
0x18002352a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002352f  lea     rcx, [rbp+70h+var_F0]
0x180023533  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023538  nop
0x180023539  lea     rcx, [rbp+70h+var_80]
0x18002353d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023542  mov     rbx, [rbx]
0x180023545  jmp     loc_1800232F0
0x18002354a  mov     rbx, qword ptr [rsp+170h+var_138+8]
0x18002354f  mov     rsi, [rsp+170h+var_128]
0x180023554  jmp     loc_1800235E9
0x180023559  lea     r9, [rbx+20h]
0x18002355d  lea     r8, [rbx+40h]
0x180023561  mov     rax, [rbx+60h]
0x180023565  mov     [rsp+20h], rax
0x18002356a  mov     rdx, rbx
0x18002356d  mov     rcx, r12
0x180023570  call    ?CleanupAgentUserForUser_DropsLock@AgentAccountHelpers@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@000AEAVOwningUserRegistry@@@Z; AgentAccountHelpers::CleanupAgentUserForUser_DropsLock(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,OwningUserRegistry &)
0x180023575  mov     r9d, eax
0x180023578  test    eax, eax
0x18002357a  js      short loc_1800235AF
0x18002357c  cmp     qword ptr [r12+18h], 7
0x180023582  jbe     short loc_18002358A
0x180023584  mov     r9, [r12]
0x180023588  jmp     short loc_18002358D
0x18002358a  mov     r9, r12
0x18002358d  cmp     qword ptr [rbx+18h], 7
0x180023592  jbe     short loc_180023599
0x180023594  mov     r8, [rbx]
0x180023597  jmp     short loc_18002359C
0x180023599  mov     r8, rbx
0x18002359c  lea     rdx, aDeletedAuAccou; "Deleted AU account %s for owning user %"...
0x1800235a3  mov     ecx, 4; unsigned __int8
0x1800235a8  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800235ad  jmp     short loc_1800235E5
0x1800235af  cmp     qword ptr [r12+18h], 7
0x1800235b5  jbe     short loc_1800235BD
0x1800235b7  mov     rax, [r12]
0x1800235bb  jmp     short loc_1800235C0
0x1800235bd  mov     rax, r12
0x1800235c0  cmp     qword ptr [rbx+18h], 7
0x1800235c5  jbe     short loc_1800235CC
0x1800235c7  mov     r8, [rbx]
0x1800235ca  jmp     short loc_1800235CF
0x1800235cc  mov     r8, rbx
0x1800235cf  mov     [rsp+20h], rax
0x1800235d4  lea     rdx, aFailedToCleanU; "Failed to clean up AU account %s, error"...
0x1800235db  mov     ecx, 2; unsigned __int8
0x1800235e0  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800235e5  add     rbx, 68h ; 'h'
0x1800235e9  cmp     rbx, rsi
0x1800235ec  jnz     loc_180023559
0x1800235f2  mov     rdi, [rdi]
0x1800235f5  jmp     loc_18002323D
0x1800235fa  call    ?RemoveEmptyKeys@AgentAccountRegistry@@QEAAXXZ; AgentAccountRegistry::RemoveEmptyKeys(void)
0x1800235ff  mov     eax, cs:dword_1800B9164
0x180023605  test    eax, eax
0x180023607  jg      short loc_180023619
0x180023609  mov     ebx, cs:dword_1800B9160
  ... truncated ...
```
