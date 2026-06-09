# CleanupUserAccount_DropsLock_OLD(wchar_t const *,wchar_t const *,OwningUserRegistry &)

- ea: `0x1800414dc`
- end: `0x180041b5b`
- name: `?CleanupUserAccount_DropsLock_OLD@@YAJPEB_W0AEAVOwningUserRegistry@@@Z`
- size: `1663`
- prototype: `__int64 __fastcall(LPCWSTR username, const wchar_t *SubStr, struct OwningUserRegistry *)`
- caller_count: `5`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004fe3c`
- `0x1800507a8`
- `0x18005469c`
- `0x18005917c`
- `0x180059200`

## callees

- `0x180002520`
- `0x1800075e4`
- `0x18001045c`
- `0x180011e18`
- `0x180014c04`
- `0x18001e648`
- `0x18001e8a8`
- `0x18001f7c0`
- `0x1800206a0`
- `0x180020d48`
- `0x180020de4`
- `0x180026780`
- `0x18002fc24`
- `0x18003c638`
- `0x1800414dc`
- `0x180043304`
- `0x180044884`
- `0x180045918`
- `0x180045acc`
- `0x180045bd0`
- `0x1800460e4`
- `0x1800461d0`
- `0x1800470fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800415af`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800415af`
- `NETAPI32!NetUserGetInfo` at `0x180041577`
- `NETAPI32!NetUserGetInfo` at `0x180041577`
- `NETAPI32!NetUserDel` at `0x1800417d1`
- `NETAPI32!NetUserDel` at `0x1800417d1`
- `NETAPI32!NetApiBufferFree` at `0x1800415f1`
- `NETAPI32!NetApiBufferFree` at `0x180041a84`
- `NETAPI32!NetApiBufferFree` at `0x180041acd`
- `NETAPI32!NetApiBufferFree` at `0x1800415f1`
- `NETAPI32!NetApiBufferFree` at `0x180041a84`
- `NETAPI32!NetApiBufferFree` at `0x180041acd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800416f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800416f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800417b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180041a07`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800417b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180041a07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041961`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041961`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800416d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041798`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800419e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800416d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041798`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800419e8`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSLogoffSession` at `0x18004171d`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSLogoffSession` at `0x18004171d`
- `USERENV!DeleteProfileW` at `0x180041957`
- `USERENV!DeleteProfileW` at `0x180041957`

## string_xrefs

- `0x180041b22`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x180041b37`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x180041b49`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x180041b10`: `onecoreuap\windows\core\isoenvbroker\lib\common\UserAccountHelpers.h`
- `0x180041541`: `Could not find SID for user name %s; it must be gone already.`
- `0x1800415ce`: `Marker GUID %s NOT found in account comment for %s: "%s"`
- `0x180041a63`: `No account comment set for %s`
- `0x1800417f8`: `Failed to delete user %s: %#x`
- `0x1800417e0`: `User %s already gone.`
- `0x18004181c`: `Deleted user %s`
- `0x180041986`: `DeleteProfile failed for MEM account %s: %#x`
- `0x18004199d`: `Deleted MEM profile (%s).`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CleanupUserAccount_DropsLock_OLD(
        LPCWSTR username,
        const wchar_t *SubStr,
        struct OwningUserRegistry *a3)
{
  DWORD Info; // ebx
  const wchar_t *v8; // rcx
  LPBYTE v9; // rcx
  unsigned __int64 v10; // r15
  unsigned __int64 v11; // r8
  unsigned __int64 v12; // r8
  WCHAR *v13; // rbx
  LPCWSTR v14; // rsi
  int v15; // ebx
  const char *v16; // r9
  DWORD LastError; // eax
  const wchar_t *v18; // r8
  WCHAR *v19; // rdx
  int v20; // esi
  int v21; // ebx
  DWORD CurrentThreadId; // edi
  const char *v23; // r9
  DWORD v24; // eax
  int v25; // ebx
  const char *v26; // r9
  __int128 v27; // xmm0
  const WCHAR *v28; // rcx
  DWORD v29; // eax
  LPCWSTR *v30; // r8
  const wchar_t *v31; // rdx
  int v32; // ebx
  const char *v33; // r9
  DWORD v34; // r14d
  LPBYTE v35; // rcx
  bool v36; // zf
  LPBYTE v37; // rcx
  LPBYTE bufptr[2]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD SessionId[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B0h] BYREF
  char v41; // [rsp+58h] [rbp-A8h]
  _OWORD v42[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+80h] [rbp-80h]
  char v44; // [rsp+88h] [rbp-78h]
  __int128 v45; // [rsp+90h] [rbp-70h]
  char v46; // [rsp+A0h] [rbp-60h]
  __int64 v47; // [rsp+A8h] [rbp-58h]
  __int64 v48; // [rsp+B0h] [rbp-50h]
  char v49; // [rsp+B8h] [rbp-48h]
  RTL_SRWLOCK *v50; // [rsp+C0h] [rbp-40h]
  _BYTE v51[40]; // [rsp+C8h] [rbp-38h] BYREF
  LPCWSTR lpSidString[3]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v53; // [rsp+108h] [rbp+8h]
  __int128 v54; // [rsp+110h] [rbp+10h] BYREF
  __m128i si128; // [rsp+120h] [rbp+20h]
  WCHAR StringSid[4]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v57; // [rsp+140h] [rbp+40h]
  unsigned __int64 v58; // [rsp+148h] [rbp+48h]
  wchar_t *v59[4]; // [rsp+150h] [rbp+50h] BYREF
  _OWORD v60[2]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  Log(4u, L"Cleaning up user %s", username);
  GetSidForUserName(StringSid, username);
  if ( !v57 )
  {
    Log(3u, L"Could not find SID for user name %s; it must be gone already.", username);
    std::wstring::~wstring((char **)StringSid);
    return 0;
  }
  bufptr[0] = 0;
  Info = NetUserGetInfo(0, username, 1u, bufptr);
  if ( !Info && bufptr[0] )
  {
    v8 = (const wchar_t *)*((_QWORD *)bufptr[0] + 4);
    if ( !v8 || !*v8 )
    {
      Log(3u, L"No account comment set for %s", username);
      goto LABEL_70;
    }
    if ( !wcsstr(v8, SubStr) )
    {
      Log(
        Info + 3,
        L"Marker GUID %s NOT found in account comment for %s: \"%s\"",
        SubStr,
        username,
        *((_QWORD *)bufptr[0] + 4));
LABEL_70:
      v35 = bufptr[0];
      v36 = bufptr[0] == 0;
      bufptr[0] = 0;
      if ( !v36 )
        NetApiBufferFree(v35);
      v20 = 0;
      goto LABEL_73;
    }
    v9 = bufptr[0];
    bufptr[0] = 0;
    if ( v9 )
      NetApiBufferFree(v9);
    memset(v60, 0, sizeof(v60));
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( username[v11] );
    std::wstring::_Construct<1,wchar_t const *>((char **)v60, username, v11);
    OwningUserRegistry::RecallAgentProfileDir(a3, v59, v60);
    std::wstring::~wstring((char **)v60);
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AclCleanup>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AclCleanup>::GetImpl'::`2'::impl) )
    {
      v54 = 0;
      si128 = 0;
      v12 = -1;
      do
        ++v12;
      while ( username[v12] );
      std::wstring::_Construct<1,wchar_t const *>((char **)&v54, username, v12);
      OwningUserRegistry::RecallAgentSharedPaths(a3, lpSidString, &v54);
      std::wstring::~wstring((char **)&v54);
      v13 = (WCHAR *)lpSidString[0];
      v14 = lpSidString[1];
      while ( v13 != v14 )
      {
        RemoveAllAccessForSid(v13, StringSid);
        v13 += 16;
      }
      std::vector<std::wstring>::~vector<std::wstring>((__int64)lpSidString);
    }
    DisableAgentAccount(username);
    v15 = dword_1800B9160;
    if ( v15 != GetCurrentThreadId() )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x15D,
        (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
        v16);
    v50 = &g_lock;
    dword_1800B9160 = 0;
    ReleaseSRWLockExclusive(&g_lock);
    SessionId[0] = 0;
    if ( FindSessionForUser(username, SessionId) )
    {
      if ( WTSLogoffSession(0, SessionId[0], 1) )
      {
        Log(4u, L"Successfully logged off %s", username);
      }
      else
      {
        LastError = GetLastError();
        Log(2u, L"Failed to log off %s: %#x", username, LastError);
      }
    }
    else
    {
      Log(3u, L"Did not find a session for AU %s", username);
    }
    v18 = (const wchar_t *)v59;
    if ( v59[3] > (wchar_t *)7 )
      v18 = v59[0];
    v19 = StringSid;
    if ( v58 > 7 )
      v19 = *(WCHAR **)StringSid;
    v20 = ReallyDeleteProfile(username, v19, v18);
    if ( v20 < 0 )
    {
      v21 = dword_1800B9160;
      CurrentThreadId = GetCurrentThreadId();
      if ( v21 == CurrentThreadId )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x2C,
          (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
          v23);
      AcquireSRWLockExclusive(&g_lock);
      dword_1800B9160 = CurrentThreadId;
LABEL_33:
      std::wstring::~wstring((char **)v59);
LABEL_73:
      std::wstring::~wstring((char **)StringSid);
      return (unsigned int)v20;
    }
    v24 = NetUserDel(0, username);
    v25 = v24;
    if ( v24 == 2221 )
    {
      Log(3u, L"User %s already gone.", username);
    }
    else if ( v24 )
    {
      Log(2u, L"Failed to delete user %s: %#x", username, v24);
      if ( v25 > 0 )
        v20 = (unsigned __int16)v25 | 0x80070000;
      else
        v20 = v25;
    }
    else
    {
      Log(4u, L"Deleted user %s", username);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59959135>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59959135>::GetImpl'::`2'::impl)
      || !IsMemAuthorityPresent() )
    {
LABEL_64:
      v32 = dword_1800B9160;
      v34 = GetCurrentThreadId();
      if ( v32 == v34 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x2C,
          (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
          v33);
      AcquireSRWLockExclusive(&g_lock);
      dword_1800B9160 = v34;
      if ( v20 >= 0 )
      {
        v54 = 0;
        si128 = 0;
        do
          ++v10;
        while ( username[v10] );
        std::wstring::_Construct<1,wchar_t const *>((char **)&v54, username, v10);
        OwningUserRegistry::RemoveAgentUserRegKey(a3, &v54);
        std::wstring::~wstring((char **)&v54);
      }
      goto LABEL_33;
    }
    std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::basic_regex<wchar_t,std::regex_traits<wchar_t>>(v51);
    v40 = 0;
    v41 = 0;
    memset(v42, 0, sizeof(v42));
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v49 = 0;
    if ( !(unsigned __int8)std::regex_match<std::char_traits<wchar_t>,std::allocator<wchar_t>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>>,wchar_t,std::regex_traits<wchar_t>>(
                             StringSid,
                             &v40,
                             v51)
      || *((_QWORD *)&v42[0] + 1) - *(_QWORD *)&v42[0] != 72 )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x31D,
        (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\UserAccountHelpers.h",
        v26);
    }
    if ( *(_BYTE *)(*(_QWORD *)&v42[0] + 64LL) )
      v27 = *(_OWORD *)(*(_QWORD *)&v42[0] + 48LL);
    else
      v27 = 0;
    *(_OWORD *)bufptr = v27;
    v54 = 0;
    si128 = 0;
    if ( (_QWORD)v27 == *((_QWORD *)&v27 + 1) )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v54) = 0;
    }
    else
    {
      std::wstring::_Construct<1,wchar_t const *>((char **)&v54, bufptr[0], (bufptr[1] - bufptr[0]) >> 1);
    }
    bufptr[0] = (LPBYTE)L"S-1-5-110-{}";
    bufptr[1] = (LPBYTE)12;
    std::format<std::wstring &>(lpSidString);
    v28 = (const WCHAR *)lpSidString;
    if ( v53 > 7 )
      v28 = lpSidString[0];
    if ( DeleteProfileW(v28, 0, 0) )
    {
      v30 = lpSidString;
      v31 = L"Deleted MEM profile (%s).";
    }
    else
    {
      v29 = GetLastError();
      v30 = lpSidString;
      if ( v29 != 2 )
      {
        if ( v53 > 7 )
          v30 = (LPCWSTR *)lpSidString[0];
        Log(3u, L"DeleteProfile failed for MEM account %s: %#x", v30, v29);
        goto LABEL_63;
      }
      v31 = L"No MEM profile found for %s.";
    }
    if ( v53 > 7 )
      v30 = (LPCWSTR *)lpSidString[0];
    Log(4u, v31, v30);
LABEL_63:
    std::wstring::~wstring((char **)lpSidString);
    std::wstring::~wstring((char **)&v54);
    std::vector<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>>::~vector<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>>(v42);
    std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::~basic_regex<wchar_t,std::regex_traits<wchar_t>>(v51);
    goto LABEL_64;
  }
  Log(2u, L"NetUserGetInfo(level 1) failed for %s: %#x", username, Info);
  if ( (int)Info > 0 )
    Info = (unsigned __int16)Info | 0x80070000;
  v37 = bufptr[0];
  bufptr[0] = 0;
  if ( v37 )
    NetApiBufferFree(v37);
  std::wstring::~wstring((char **)StringSid);
  return Info;
}

```

## disassembly

```asm
0x1800414dc  mov     [rsp-8+arg_18], rbx
0x1800414e1  push    rbp
0x1800414e2  push    rsi
0x1800414e3  push    rdi
0x1800414e4  push    r12
0x1800414e6  push    r13
0x1800414e8  push    r14
0x1800414ea  push    r15
0x1800414ec  lea     rbp, [rsp-0A0h]
0x1800414f4  sub     rsp, 1A0h
0x1800414fb  mov     rax, cs:__security_cookie
0x180041502  xor     rax, rsp
0x180041505  mov     [rbp+0D0h+var_40], rax
0x18004150c  mov     r12, r8
0x18004150f  mov     rsi, rdx
0x180041512  mov     rdi, rcx
0x180041515  xor     r13d, r13d
0x180041518  mov     r8, rcx
0x18004151b  lea     rdx, aCleaningUpUser; "Cleaning up user %s"
0x180041522  lea     ecx, [r13+4]; unsigned __int8
0x180041526  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18004152b  mov     rdx, rdi
0x18004152e  lea     rcx, [rbp+0D0h+StringSid]
0x180041532  call    ?GetSidForUserName@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; GetSidForUserName(wchar_t const *)
0x180041537  nop
0x180041538  cmp     [rbp+0D0h+var_90], r13
0x18004153c  jnz     short loc_180041562
0x18004153e  mov     r8, rdi
0x180041541  lea     rdx, aCouldNotFindSi; "Could not find SID for user name %s; it"...
0x180041548  lea     ecx, [r13+3]; unsigned __int8
0x18004154c  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180041551  nop
0x180041552  lea     rcx, [rbp+0D0h+StringSid]
0x180041556  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004155b  xor     eax, eax
0x18004155d  jmp     loc_180041ADF
0x180041562  mov     [rsp+1D0h+bufptr], r13
0x180041567  lea     r9, [rsp+1D0h+bufptr]; bufptr
0x18004156c  mov     r8d, 1; level
0x180041572  mov     rdx, rdi; username
0x180041575  xor     ecx, ecx; servername
0x180041577  call    cs:__imp_NetUserGetInfo
0x18004157d  mov     ebx, eax
0x18004157f  test    eax, eax
0x180041581  jnz     loc_180041A9A
0x180041587  mov     rax, [rsp+1D0h+bufptr]
0x18004158c  test    rax, rax
0x18004158f  jz      loc_180041A9A
0x180041595  mov     rcx, [rax+20h]; Str
0x180041599  test    rcx, rcx
0x18004159c  jz      loc_180041A60
0x1800415a2  cmp     [rcx], r13w
0x1800415a6  jz      loc_180041A60
0x1800415ac  mov     rdx, rsi; SubStr
0x1800415af  call    cs:__imp_wcsstr
0x1800415b5  test    rax, rax
0x1800415b8  jnz     short loc_1800415E2
0x1800415ba  mov     rax, [rsp+1D0h+bufptr]
0x1800415bf  mov     rcx, [rax+20h]
0x1800415c3  mov     [rsp+1D0h+var_1B0], rcx
0x1800415c8  mov     r9, rdi
0x1800415cb  mov     r8, rsi
0x1800415ce  lea     rdx, aMarkerGuidSNot; "Marker GUID %s NOT found in account com"...
0x1800415d5  lea     ecx, [rbx+3]; unsigned __int8
0x1800415d8  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800415dd  jmp     loc_180041A75
0x1800415e2  mov     rcx, [rsp+1D0h+bufptr]; Buffer
0x1800415e7  mov     [rsp+1D0h+bufptr], r13
0x1800415ec  test    rcx, rcx
0x1800415ef  jz      short loc_1800415F7
0x1800415f1  call    cs:__imp_NetApiBufferFree
0x1800415f7  xorps   xmm0, xmm0
0x1800415fa  movups  [rbp+0D0h+var_60], xmm0
0x1800415fe  xorps   xmm1, xmm1
0x180041601  movdqu  [rbp+0D0h+var_50], xmm1
0x180041609  or      r15, 0FFFFFFFFFFFFFFFFh
0x18004160d  mov     r8, r15
0x180041610  inc     r8
0x180041613  cmp     [rdi+r8*2], r13w
0x180041618  jnz     short loc_180041610
0x18004161a  mov     rdx, rdi
0x18004161d  lea     rcx, [rbp+0D0h+var_60]
0x180041621  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180041626  nop
0x180041627  lea     r8, [rbp+0D0h+var_60]
0x18004162b  lea     rdx, [rbp+0D0h+var_80]
0x18004162f  mov     rcx, r12
0x180041632  call    ?RecallAgentProfileDir@OwningUserRegistry@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@Z; OwningUserRegistry::RecallAgentProfileDir(std::wstring const &)
0x180041637  nop
0x180041638  lea     rcx, [rbp+0D0h+var_60]
0x18004163c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180041641  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AclCleanup@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AclCleanup@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AclCleanup> `wil::Feature<__WilFeatureTraits_Feature_AclCleanup>::GetImpl(void)'::`2'::impl
0x180041648  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AclCleanup@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AclCleanup>::__private_IsEnabled(void)
0x18004164d  test    al, al
0x18004164f  jz      short loc_1800416BC
0x180041651  xorps   xmm0, xmm0
0x180041654  movups  [rbp+0D0h+var_C0], xmm0
0x180041658  xorps   xmm1, xmm1
0x18004165b  movdqu  [rbp+0D0h+var_B0], xmm1
0x180041660  mov     r8, r15
0x180041663  inc     r8
0x180041666  cmp     [rdi+r8*2], r13w
0x18004166b  jnz     short loc_180041663
0x18004166d  mov     rdx, rdi
0x180041670  lea     rcx, [rbp+0D0h+var_C0]
0x180041674  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180041679  nop
0x18004167a  lea     r8, [rbp+0D0h+var_C0]
0x18004167e  lea     rdx, [rbp+0D0h+lpSidString]
0x180041682  mov     rcx, r12
0x180041685  call    ?RecallAgentSharedPaths@OwningUserRegistry@@QEAA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; OwningUserRegistry::RecallAgentSharedPaths(std::wstring const &)
0x18004168a  nop
0x18004168b  lea     rcx, [rbp+0D0h+var_C0]
0x18004168f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180041694  mov     rbx, [rbp+0D0h+lpSidString]
0x180041698  mov     rsi, [rbp+0D0h+var_D8]
0x18004169c  jmp     short loc_1800416AE
0x18004169e  lea     rdx, [rbp+0D0h+StringSid]; StringSid
0x1800416a2  mov     rcx, rbx; pObjectName
0x1800416a5  call    RemoveAllAccessForSid
0x1800416aa  add     rbx, 20h ; ' '
0x1800416ae  cmp     rbx, rsi
0x1800416b1  jnz     short loc_18004169E
0x1800416b3  lea     rcx, [rbp+0D0h+lpSidString]
0x1800416b7  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x1800416bc  mov     rcx, rdi; username
0x1800416bf  call    DisableAgentAccount
0x1800416c4  mov     ebx, cs:dword_1800B9160
0x1800416ca  mov     rsi, [rbp+0D8h]
0x1800416d1  call    cs:__imp_GetCurrentThreadId
0x1800416d7  cmp     ebx, eax
0x1800416d9  jnz     loc_180041B22
0x1800416df  lea     r14, ?g_lock@@3Vchecked_srwlock@@A; checked_srwlock g_lock
0x1800416e6  mov     [rbp+0D0h+var_110], r14
0x1800416ea  mov     cs:dword_1800B9160, r13d
0x1800416f1  mov     rcx, r14; SRWLock
0x1800416f4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800416fa  nop
0x1800416fb  mov     [rsp+1D0h+SessionId], r13d
0x180041700  lea     rdx, [rsp+1D0h+SessionId]; unsigned int *
0x180041705  mov     rcx, rdi; wchar_t *
0x180041708  call    ?FindSessionForUser@@YA_NPEB_WPEAK@Z; FindSessionForUser(wchar_t const *,ulong *)
0x18004170d  test    al, al
0x18004170f  jz      short loc_180041754
0x180041711  mov     r8d, 1; bWait
0x180041717  mov     edx, [rsp+1D0h+SessionId]; SessionId
0x18004171b  xor     ecx, ecx; hServer
0x18004171d  call    cs:__imp_WTSLogoffSession
0x180041723  test    eax, eax
0x180041725  jz      short loc_180041735
0x180041727  lea     rdx, aSuccessfullyLo; "Successfully logged off %s"
0x18004172e  mov     ecx, 4
0x180041733  jmp     short loc_180041760
0x180041735  call    cs:__imp_GetLastError
0x18004173b  mov     r9d, eax
0x18004173e  mov     r8, rdi
0x180041741  lea     rdx, aFailedToLogOff; "Failed to log off %s: %#x"
0x180041748  mov     ecx, 2; unsigned __int8
0x18004174d  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180041752  jmp     short loc_180041768
0x180041754  lea     rdx, aDidNotFindASes_0; "Did not find a session for AU %s"
0x18004175b  mov     ecx, 3; unsigned __int8
0x180041760  mov     r8, rdi
0x180041763  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180041768  lea     r8, [rbp+0D0h+var_80]
0x18004176c  cmp     [rbp+0D0h+var_68], 7
0x180041771  cmova   r8, [rbp+0D0h+var_80]; wchar_t *
0x180041776  lea     rdx, [rbp+0D0h+StringSid]
0x18004177a  cmp     [rbp+0D0h+var_88], 7
0x18004177f  cmova   rdx, qword ptr [rbp+0D0h+StringSid]; wchar_t *
0x180041784  mov     rcx, rdi; wchar_t *
0x180041787  call    ?ReallyDeleteProfile@@YAJPEB_W00@Z; ReallyDeleteProfile(wchar_t const *,wchar_t const *,wchar_t const *)
0x18004178c  mov     esi, eax
0x18004178e  test    eax, eax
0x180041790  jns     short loc_1800417CC
0x180041792  mov     ebx, cs:dword_1800B9160
0x180041798  call    cs:__imp_GetCurrentThreadId
0x18004179e  mov     edi, eax
0x1800417a0  mov     rcx, [rbp+0D8h]; this
0x1800417a7  cmp     ebx, eax
0x1800417a9  jz      loc_180041B37
0x1800417af  mov     rcx, r14; SRWLock
0x1800417b2  call    cs:__imp_AcquireSRWLockExclusive
0x1800417b8  mov     cs:dword_1800B9160, edi
0x1800417be  lea     rcx, [rbp+0D0h+var_80]
0x1800417c2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800417c7  jmp     loc_180041A8D
0x1800417cc  mov     rdx, rdi; username
0x1800417cf  xor     ecx, ecx; servername
0x1800417d1  call    cs:__imp_NetUserDel
0x1800417d7  mov     ebx, eax
0x1800417d9  cmp     eax, 8ADh
0x1800417de  jnz     short loc_1800417EE
0x1800417e0  lea     rdx, aUserSAlreadyGo; "User %s already gone."
0x1800417e7  mov     ecx, 3
0x1800417ec  jmp     short loc_180041828
0x1800417ee  test    ebx, ebx
0x1800417f0  jz      short loc_18004181C
0x1800417f2  mov     r9d, ebx
0x1800417f5  mov     r8, rdi
0x1800417f8  lea     rdx, aFailedToDelete_1; "Failed to delete user %s: %#x"
0x1800417ff  mov     ecx, 2; unsigned __int8
0x180041804  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180041809  test    ebx, ebx
0x18004180b  jg      short loc_180041811
0x18004180d  mov     esi, ebx
0x18004180f  jmp     short loc_180041830
0x180041811  movzx   esi, bx
0x180041814  or      esi, 80070000h
0x18004181a  jmp     short loc_180041830
0x18004181c  lea     rdx, aDeletedUserS; "Deleted user %s"
0x180041823  mov     ecx, 4; unsigned __int8
0x180041828  mov     r8, rdi
0x18004182b  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180041830  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59959135@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59959135@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59959135> `wil::Feature<__WilFeatureTraits_Feature_ID59959135>::GetImpl(void)'::`2'::impl
0x180041837  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59959135@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59959135>::__private_IsEnabled(void)
0x18004183c  test    al, al
0x18004183e  jz      loc_1800419E2
0x180041844  call    ?IsMemAuthorityPresent@@YA_NXZ; IsMemAuthorityPresent(void)
0x180041849  test    al, al
0x18004184b  jz      loc_1800419E2
0x180041851  lea     rcx, [rbp+0D0h+var_108]
0x180041855  call    ??0?$basic_regex@_WV?$regex_traits@_W@std@@@std@@QEAA@PEB_WW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::basic_regex<wchar_t,std::regex_traits<wchar_t>>(wchar_t const *,std::regex_constants::syntax_option_type)
0x18004185a  nop
0x18004185b  mov     [rsp+1D0h+var_180], r13
0x180041860  mov     [rsp+1D0h+var_178], r13b
0x180041865  xorps   xmm0, xmm0
0x180041868  movdqa  [rsp+1D0h+var_170], xmm0
0x18004186e  xorps   xmm1, xmm1
0x180041871  movdqa  [rsp+1D0h+var_160], xmm1
0x180041877  mov     [rbp+0D0h+var_150], r13
0x18004187b  mov     [rbp+0D0h+var_148], r13b
0x18004187f  movdqa  [rbp+0D0h+var_140], xmm0
0x180041884  mov     [rbp+0D0h+var_130], r13b
0x180041888  mov     [rbp+0D0h+var_128], r13
0x18004188c  mov     [rbp+0D0h+var_120], r13
0x180041890  mov     [rbp+0D0h+var_118], r13b
0x180041894  lea     r8, [rbp+0D0h+var_108]
0x180041898  lea     rdx, [rsp+1D0h+var_180]
0x18004189d  lea     rcx, [rbp+0D0h+StringSid]
0x1800418a1  call    ??$regex_match@U?$char_traits@_W@std@@V?$allocator@_W@2@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@@std@@@2@_WV?$regex_traits@_W@2@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEAV?$match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@std@@@std@@@2@@0@AEBV?$basic_regex@_WV?$regex_traits@_W@std@@@0@W4match_flag_type@regex_constants@0@@Z; std::regex_match<std::char_traits<wchar_t>,std::allocator<wchar_t>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>>,wchar_t,std::regex_traits<wchar_t>>(std::wstring const &,std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>> &,std::basic_regex<wchar_t,std::regex_traits<wchar_t>> const &,std::regex_constants::match_flag_type)
0x1800418a6  test    al, al
0x1800418a8  jz      loc_180041B09
0x1800418ae  mov     rcx, qword ptr [rsp+1D0h+var_170]
0x1800418b3  mov     rax, qword ptr [rsp+1D0h+var_170+8]
0x1800418b8  sub     rax, rcx
0x1800418bb  cmp     rax, 48h ; 'H'
0x1800418bf  jnz     loc_180041B09
0x1800418c5  cmp     [rcx+40h], r13b
0x1800418c9  jz      short loc_1800418D1
0x1800418cb  movups  xmm0, xmmword ptr [rcx+30h]
0x1800418cf  jmp     short loc_1800418D4
0x1800418d1  xorps   xmm0, xmm0
0x1800418d4  movdqu  xmmword ptr [rsp+1D0h+bufptr], xmm0
0x1800418da  xorps   xmm0, xmm0
0x1800418dd  movups  [rbp+0D0h+var_C0], xmm0
0x1800418e1  xorps   xmm1, xmm1
0x1800418e4  movdqu  [rbp+0D0h+var_B0], xmm1
0x1800418e9  mov     rdx, [rsp+1D0h+bufptr]
0x1800418ee  mov     r8, [rsp+1D0h+bufptr+8]
0x1800418f3  cmp     rdx, r8
0x1800418f6  jnz     short loc_18004190C
0x1800418f8  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180041900  movdqu  [rbp+0D0h+var_B0], xmm0
0x180041905  mov     word ptr [rbp+0D0h+var_C0], r13w
0x18004190a  jmp     short loc_18004191C
0x18004190c  sub     r8, rdx
0x18004190f  sar     r8, 1
0x180041912  lea     rcx, [rbp+0D0h+var_C0]
0x180041916  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004191b  nop
0x18004191c  lea     rax, aS15110_0; "S-1-5-110-{}"
0x180041923  mov     [rsp+1D0h+bufptr], rax
0x180041928  mov     [rsp+1D0h+bufptr+8], 0Ch
0x180041931  lea     r8, [rbp+0D0h+var_C0]
0x180041935  lea     rdx, [rsp+1D0h+bufptr]
0x18004193a  lea     rcx, [rbp+0D0h+lpSidString]; Src
0x18004193e  call    ??$format@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@U?$basic_format_string@_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@AEAV10@@Z; std::format<std::wstring &>(std::basic_format_string<wchar_t,std::wstring &>,std::wstring &)
0x180041943  nop
0x180041944  lea     rcx, [rbp+0D0h+lpSidString]
0x180041948  cmp     [rbp+0D0h+var_C8], 7
0x18004194d  cmova   rcx, [rbp+0D0h+lpSidString]; lpSidString
0x180041952  xor     r8d, r8d; lpComputerName
0x180041955  xor     edx, edx; lpProfilePath
0x180041957  call    cs:__imp_DeleteProfileW
0x18004195d  test    eax, eax
0x18004195f  jnz     short loc_180041999
0x180041961  call    cs:__imp_GetLastError
0x180041967  lea     r8, [rbp+0D0h+lpSidString]
0x18004196b  cmp     eax, 2
0x18004196e  jnz     short loc_180041979
0x180041970  lea     rdx, aNoMemProfileFo; "No MEM profile found for %s."
0x180041977  jmp     short loc_1800419A4
0x180041979  cmp     [rbp+0D0h+var_C8], 7
0x18004197e  cmova   r8, [rbp+0D0h+lpSidString]
0x180041983  mov     r9d, eax
0x180041986  lea     rdx, aDeleteprofileF; "DeleteProfile failed for MEM account %s"...
0x18004198d  mov     ecx, 3; unsigned __int8
0x180041992  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180041997  jmp     short loc_1800419B9
  ... truncated ...
```
