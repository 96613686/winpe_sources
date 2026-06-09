# CleanupUserAccount_DropsLock(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,OwningUserRegistry &)

- ea: `0x180040d30`
- end: `0x1800414d4`
- name: `?CleanupUserAccount_DropsLock@@YAJPEB_W000AEAVOwningUserRegistry@@@Z`
- size: `1956`
- prototype: `__int64 __fastcall(LPCWSTR StringSid, PCWSTR SourceString, WCHAR *, const wchar_t *, struct OwningUserRegistry *)`
- caller_count: `2`
- callee_count: `26`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003ff5c`
- `0x180040c90`

## callees

- `0x180002520`
- `0x1800075e4`
- `0x18000a464`
- `0x18001045c`
- `0x180011e18`
- `0x180014c04`
- `0x18001e648`
- `0x18001e8a8`
- `0x18001f7c0`
- `0x1800206a0`
- `0x180020d48`
- `0x180020de4`
- `0x1800214c4`
- `0x180026780`
- `0x18002fc24`
- `0x18003c638`
- `0x180040d30`
- `0x180044884`
- `0x180045918`
- `0x180045acc`
- `0x180045bd0`
- `0x180045ec4`
- `0x1800460e4`
- `0x1800461d0`
- `0x180046bf4`
- `0x18006374c`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180041133`
- `ntdll!RtlInitUnicodeStringEx` at `0x180041156`
- `ntdll!RtlInitUnicodeStringEx` at `0x180041133`
- `ntdll!RtlInitUnicodeStringEx` at `0x180041156`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040fc4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180040fc4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800410dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800413ad`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800410dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800413ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040e87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040eb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004102e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041309`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040e87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040eb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004102e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041309`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040e9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040e9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040fa0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800410be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004138f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040fa0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800410be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004138f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180040e65`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180040e65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040e92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040eec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004110a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041422`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040e92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040eec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004110a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041422`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSLogoffSession` at `0x180041016`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSLogoffSession` at `0x180041016`
- `USERENV!DeleteProfileW` at `0x1800412ff`
- `USERENV!DeleteProfileW` at `0x1800412ff`

## string_xrefs

- `0x180041471`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x180041486`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x1800414c2`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x1800410a6`: `onecoreuap\windows\core\isoenvbroker\lib\common\UserAccountHelpers.h`
- `0x18004145f`: `onecoreuap\windows\core\isoenvbroker\lib\common\UserAccountHelpers.h`
- `0x18004149b`: `onecoreuap\windows\core\isoenvbroker\lib\common\UserAccountHelpers.h`
- `0x1800414b0`: `onecoreuap\windows\core\isoenvbroker\lib\common\UserAccountHelpers.h`
- `0x180040db9`: `Could not find SID for agent user name %s; is it gone already?`
- `0x180040e33`: `Also could not find recorded SID for agent %s.`
- `0x1800411a6`: `LsaDeleteAgentAccount failed for agent %s (%s): %#x`
- `0x180041194`: `LsaDeleteAgentAccount: agent %s (%s) not found.`
- `0x1800411c1`: `Deleted agent %s from LSA (%s).`
- `0x18004132e`: `DeleteProfile failed for MEM account %s: %#x`
- `0x180041345`: `Deleted MEM profile (%s).`
- `0x180040ec1`: `Failed converting owningUserSid to SID: %#x`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CleanupUserAccount_DropsLock(
        LPCWSTR StringSid,
        PCWSTR SourceString,
        WCHAR *a3,
        const wchar_t *a4,
        struct OwningUserRegistry *a5)
{
  const WCHAR *v6; // r12
  struct OwningUserRegistry *v9; // r14
  __int64 v10; // r15
  __int64 v11; // r8
  __int64 v12; // rax
  BOOL v13; // r13d
  PSID v14; // r12
  _QWORD *v15; // r14
  void *v16; // r15
  DWORD LastError; // ebx
  __int64 v18; // rbx
  __int64 v19; // r8
  __int64 v20; // r8
  int v21; // ebx
  const char *v22; // r9
  WCHAR *v23; // rbx
  LPWSTR v24; // r14
  DWORD v25; // eax
  const wchar_t *v26; // r8
  WCHAR *v27; // rdx
  int v28; // eax
  int v29; // r14d
  int v30; // ebx
  DWORD CurrentThreadId; // edi
  const char *v32; // r9
  NTSTATUS inited; // eax
  NTSTATUS v35; // eax
  int v36; // r14d
  int v37; // eax
  int v38; // ebx
  const char *v39; // r9
  __int128 v40; // xmm0
  const WCHAR *v41; // rcx
  DWORD v42; // eax
  LPCWSTR *v43; // r8
  const wchar_t *v44; // rdx
  int v45; // ebx
  DWORD v46; // esi
  const char *v47; // r9
  const wchar_t *v48; // [rsp+20h] [rbp-E0h]
  DWORD SessionId; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v51; // [rsp+40h] [rbp-C0h]
  PSID Sid[2]; // [rsp+50h] [rbp-B0h] BYREF
  char v53; // [rsp+60h] [rbp-A0h]
  struct OwningUserRegistry *v54; // [rsp+68h] [rbp-98h]
  RTL_SRWLOCK *v55; // [rsp+70h] [rbp-90h]
  LPWSTR pObjectName[3]; // [rsp+78h] [rbp-88h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  __int64 v58; // [rsp+A0h] [rbp-60h] BYREF
  char v59; // [rsp+A8h] [rbp-58h]
  _OWORD v60[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v61; // [rsp+D0h] [rbp-30h]
  char v62; // [rsp+D8h] [rbp-28h]
  __int128 v63; // [rsp+E0h] [rbp-20h]
  char v64; // [rsp+F0h] [rbp-10h]
  __int64 v65; // [rsp+F8h] [rbp-8h]
  __int64 v66; // [rsp+100h] [rbp+0h]
  char v67; // [rsp+108h] [rbp+8h]
  _BYTE v68[40]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v69; // [rsp+138h] [rbp+38h] BYREF
  __m128i si128; // [rsp+148h] [rbp+48h]
  LPCWSTR lpSidString[3]; // [rsp+158h] [rbp+58h] BYREF
  unsigned __int64 v72; // [rsp+170h] [rbp+70h]
  WCHAR StringSida[8]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v74; // [rsp+188h] [rbp+88h]
  unsigned __int64 v75; // [rsp+190h] [rbp+90h]
  _OWORD v76[2]; // [rsp+198h] [rbp+98h] BYREF
  wchar_t *v77[4]; // [rsp+1B8h] [rbp+B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v6 = a3;
  v55 = (RTL_SRWLOCK *)a3;
  v9 = a5;
  v54 = a5;
  v48 = a4;
  Log(4u, L"Cleaning up AU %s for owning app %s (%s)", SourceString, a3);
  GetSidForUserName(StringSida, a4);
  v10 = -1;
  if ( !v74 )
  {
    Log(4u, L"Could not find SID for agent user name %s; is it gone already?", a4);
    v69 = 0;
    si128 = 0;
    v11 = -1;
    do
      ++v11;
    while ( SourceString[v11] );
    std::wstring::_Construct<1,wchar_t const *>(&v69, SourceString);
    v12 = OwningUserRegistry::RecallAgentSid(a5, v76, &v69);
    std::wstring::operator=(StringSida, v12);
    std::wstring::~wstring(v76);
    std::wstring::~wstring(&v69);
    if ( !v74 )
      Log(3u, L"Also could not find recorded SID for agent %s.", SourceString);
  }
  hMem = 0;
  Sid[0] = &hMem;
  Sid[1] = 0;
  v53 = 1;
  v13 = ConvertStringSidToSidW(StringSid, &Sid[1]);
  if ( v53 )
  {
    v14 = Sid[1];
    v15 = Sid[0];
    v16 = *(void **)Sid[0];
    if ( *(_QWORD *)Sid[0] )
    {
      LastError = GetLastError();
      LocalFree(v16);
      SetLastError(LastError);
    }
    *v15 = v14;
    v10 = -1;
    v6 = (const WCHAR *)v55;
    v9 = v54;
  }
  if ( !v13 )
  {
    v18 = GetLastError();
    Log(2u, L"Failed converting owningUserSid to SID: %#x", v18);
    if ( (int)v18 > 0 )
      LODWORD(v18) = (unsigned __int16)v18 | 0x80070000;
    if ( hMem )
      LocalFree(hMem);
LABEL_38:
    std::wstring::~wstring(StringSida);
    return (unsigned int)v18;
  }
  v69 = 0;
  si128 = 0;
  v19 = -1;
  do
    ++v19;
  while ( SourceString[v19] );
  std::wstring::_Construct<1,wchar_t const *>(&v69, SourceString);
  OwningUserRegistry::RecallAgentProfileDir(v9, v77, &v69);
  std::wstring::~wstring(&v69);
  memset(v76, 0, sizeof(v76));
  v20 = -1;
  do
    ++v20;
  while ( SourceString[v20] );
  std::wstring::_Construct<1,wchar_t const *>(v76, SourceString);
  OwningUserRegistry::RecallAgentSharedPaths(v9, pObjectName, v76);
  std::wstring::~wstring(v76);
  v21 = dword_1800B9160;
  if ( v21 != GetCurrentThreadId() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x15D,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
      v22);
  v55 = &g_lock;
  dword_1800B9160 = 0;
  ReleaseSRWLockExclusive(&g_lock);
  if ( v74 )
  {
    v23 = pObjectName[0];
    v24 = pObjectName[1];
    while ( v23 != v24 )
    {
      RemoveAllAccessForSid(v23, StringSida);
      v23 += 16;
    }
  }
  SessionId = 0;
  if ( FindSessionForUser(a4, &SessionId) )
  {
    if ( WTSLogoffSession(0, SessionId, 1) )
    {
      Log(4u, L"Successfully logged off %s", a4);
    }
    else
    {
      v25 = GetLastError();
      Log(2u, L"Failed to log off %s: %#x", a4, v25);
    }
  }
  else
  {
    Log(3u, L"Did not find a session for AU %s", a4);
  }
  v26 = (const wchar_t *)v77;
  if ( v77[3] > (wchar_t *)7 )
    v26 = v77[0];
  v27 = StringSida;
  if ( v75 > 7 )
    v27 = *(WCHAR **)StringSida;
  v28 = ReallyDeleteProfile(a4, v27, v26);
  v29 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A1,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\UserAccountHelpers.h",
      (const char *)(unsigned int)v28,
      (int)v48);
    v30 = dword_1800B9160;
    CurrentThreadId = GetCurrentThreadId();
    if ( v30 == CurrentThreadId )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
        v32);
    AcquireSRWLockExclusive(&g_lock);
    dword_1800B9160 = CurrentThreadId;
    std::vector<std::wstring>::~vector<std::wstring>(pObjectName);
    std::wstring::~wstring(v77);
    if ( hMem )
      LocalFree(hMem);
    LODWORD(v18) = v29;
    goto LABEL_38;
  }
  *(_OWORD *)Sid = 0;
  inited = RtlInitUnicodeStringEx((PUNICODE_STRING)Sid, v6);
  if ( inited < 0 )
    wil::details::in1diag3::_FailFast_NtStatus(
      retaddr,
      (void *)0x3A4,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\UserAccountHelpers.h",
      (const char *)(unsigned int)inited,
      (int)v48);
  DestinationString = 0;
  v35 = RtlInitUnicodeStringEx(&DestinationString, SourceString);
  if ( v35 < 0 )
    wil::details::in1diag3::_FailFast_NtStatus(
      retaddr,
      (void *)0x3A8,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\UserAccountHelpers.h",
      (const char *)(unsigned int)v35,
      (int)v48);
  v36 = 0;
  v37 = LsaDeleteAgentAccount(hMem, Sid, &DestinationString);
  v38 = v37;
  if ( v37 >= 0 )
  {
    Log(4u, L"Deleted agent %s from LSA (%s).", SourceString, a4);
  }
  else if ( v37 == -1073741724 )
  {
    Log(3u, L"LsaDeleteAgentAccount: agent %s (%s) not found.", SourceString, a4);
  }
  else
  {
    LODWORD(v48) = v37;
    Log(2u, L"LsaDeleteAgentAccount failed for agent %s (%s): %#x", SourceString, a4, v48);
    v36 = v38 | 0x10000000;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59959135>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59959135>::GetImpl'::`2'::impl)
    && IsMemAuthorityPresent()
    && v74 )
  {
    std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::basic_regex<wchar_t,std::regex_traits<wchar_t>>(v68);
    v58 = 0;
    v59 = 0;
    memset(v60, 0, sizeof(v60));
    v61 = 0;
    v62 = 0;
    v63 = 0;
    v64 = 0;
    v65 = 0;
    v66 = 0;
    v67 = 0;
    if ( !(unsigned __int8)std::regex_match<std::char_traits<wchar_t>,std::allocator<wchar_t>,std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>>,wchar_t,std::regex_traits<wchar_t>>(
                             StringSida,
                             &v58,
                             v68)
      || *((_QWORD *)&v60[0] + 1) - *(_QWORD *)&v60[0] != 72 )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x3CA,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\UserAccountHelpers.h",
        v39);
    }
    if ( *(_BYTE *)(*(_QWORD *)&v60[0] + 64LL) )
      v40 = *(_OWORD *)(*(_QWORD *)&v60[0] + 48LL);
    else
      v40 = 0;
    v51 = v40;
    v69 = 0;
    si128 = 0;
    if ( (_QWORD)v40 == *((_QWORD *)&v40 + 1) )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v69) = 0;
    }
    else
    {
      std::wstring::_Construct<1,wchar_t const *>(&v69, v51);
    }
    *(_QWORD *)&v51 = L"S-1-5-110-{}";
    *((_QWORD *)&v51 + 1) = 12;
    std::format<std::wstring &>(lpSidString);
    v41 = (const WCHAR *)lpSidString;
    if ( v72 > 7 )
      v41 = lpSidString[0];
    if ( DeleteProfileW(v41, 0, 0) )
    {
      v43 = lpSidString;
      v44 = L"Deleted MEM profile (%s).";
    }
    else
    {
      v42 = GetLastError();
      v43 = lpSidString;
      if ( v42 != 2 )
      {
        if ( v72 > 7 )
          v43 = (LPCWSTR *)lpSidString[0];
        Log(3u, L"DeleteProfile failed for MEM account %s: %#x", v43, v42);
        goto LABEL_69;
      }
      v44 = L"No MEM profile found for %s.";
    }
    if ( v72 > 7 )
      v43 = (LPCWSTR *)lpSidString[0];
    Log(4u, v44, v43);
LABEL_69:
    std::wstring::~wstring(lpSidString);
    std::wstring::~wstring(&v69);
    std::vector<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>>::~vector<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>>>(v60);
    std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::~basic_regex<wchar_t,std::regex_traits<wchar_t>>(v68);
  }
  v45 = dword_1800B9160;
  v46 = GetCurrentThreadId();
  if ( v45 == v46 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
      v47);
  AcquireSRWLockExclusive(&g_lock);
  dword_1800B9160 = v46;
  if ( v36 >= 0 )
  {
    v69 = 0;
    si128 = 0;
    do
      ++v10;
    while ( SourceString[v10] );
    std::wstring::_Construct<1,wchar_t const *>(&v69, SourceString);
    OwningUserRegistry::RemoveAgentUserRegKey(v54, &v69);
    std::wstring::~wstring(&v69);
  }
  std::vector<std::wstring>::~vector<std::wstring>(pObjectName);
  std::wstring::~wstring(v77);
  if ( hMem )
    LocalFree(hMem);
  std::wstring::~wstring(StringSida);
  return (unsigned int)v36;
}

```

## disassembly

```asm
0x180040d30  push    rbp
0x180040d32  push    rbx
0x180040d33  push    rsi
0x180040d34  push    rdi
0x180040d35  push    r12
0x180040d37  push    r13
0x180040d39  push    r14
0x180040d3b  push    r15
0x180040d3d  lea     rbp, [rsp-0E8h]
0x180040d45  sub     rsp, 1E8h
0x180040d4c  mov     rax, cs:__security_cookie
0x180040d53  xor     rax, rsp
0x180040d56  mov     [rbp+120h+var_48], rax
0x180040d5d  mov     rsi, r9
0x180040d60  mov     r12, r8
0x180040d63  mov     [rsp+220h+var_1B0], r8
0x180040d68  mov     rdi, rdx
0x180040d6b  mov     rbx, rcx
0x180040d6e  mov     r14, [rbp+120h+arg_20]
0x180040d75  mov     [rsp+220h+var_1B8], r14
0x180040d7a  xor     r13d, r13d
0x180040d7d  mov     [rsp+220h+var_200], r9
0x180040d82  mov     r9, r8
0x180040d85  mov     r8, rdx
0x180040d88  lea     rdx, aCleaningUpAuSF; "Cleaning up AU %s for owning app %s (%s"...
0x180040d8f  lea     ecx, [r13+4]; unsigned __int8
0x180040d93  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180040d98  mov     rdx, rsi
0x180040d9b  lea     rcx, [rbp+120h+StringSid]
0x180040d9f  call    ?GetSidForUserName@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; GetSidForUserName(wchar_t const *)
0x180040da4  nop
0x180040da5  or      r15, 0FFFFFFFFFFFFFFFFh
0x180040da9  cmp     [rbp+120h+var_98], r13
0x180040db0  jnz     loc_180040E44
0x180040db6  mov     r8, rsi
0x180040db9  lea     rdx, aCouldNotFindSi_0; "Could not find SID for agent user name "...
0x180040dc0  lea     ecx, [r13+4]; unsigned __int8
0x180040dc4  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180040dc9  xorps   xmm0, xmm0
0x180040dcc  movups  [rbp+120h+var_E8], xmm0
0x180040dd0  xorps   xmm1, xmm1
0x180040dd3  movdqu  [rbp+120h+var_D8], xmm1
0x180040dd8  mov     r8, r15
0x180040ddb  inc     r8
0x180040dde  cmp     [rdi+r8*2], r13w
0x180040de3  jnz     short loc_180040DDB
0x180040de5  mov     rdx, rdi
0x180040de8  lea     rcx, [rbp+120h+var_E8]
0x180040dec  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180040df1  nop
0x180040df2  lea     r8, [rbp+120h+var_E8]
0x180040df6  lea     rdx, [rbp+120h+var_88]
0x180040dfd  mov     rcx, r14
0x180040e00  call    ?RecallAgentSid@OwningUserRegistry@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@Z; OwningUserRegistry::RecallAgentSid(std::wstring const &)
0x180040e05  mov     rdx, rax
0x180040e08  lea     rcx, [rbp+120h+StringSid]
0x180040e0c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180040e11  lea     rcx, [rbp+120h+var_88]
0x180040e18  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180040e1d  nop
0x180040e1e  lea     rcx, [rbp+120h+var_E8]
0x180040e22  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180040e27  cmp     [rbp+120h+var_98], r13
0x180040e2e  jnz     short loc_180040E44
0x180040e30  mov     r8, rdi
0x180040e33  lea     rdx, aAlsoCouldNotFi; "Also could not find recorded SID for ag"...
0x180040e3a  mov     ecx, 3; unsigned __int8
0x180040e3f  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180040e44  mov     [rsp+220h+hMem], r13
0x180040e49  lea     rax, [rsp+220h+hMem]
0x180040e4e  mov     [rsp+220h+Sid], rax
0x180040e53  mov     [rsp+220h+Sid+8], r13
0x180040e58  mov     [rsp+220h+var_1C0], 1
0x180040e5d  lea     rdx, [rsp+220h+Sid+8]; Sid
0x180040e62  mov     rcx, rbx; StringSid
0x180040e65  call    cs:__imp_ConvertStringSidToSidW
0x180040e6b  mov     r13d, eax
0x180040e6e  cmp     [rsp+220h+var_1C0], 0
0x180040e73  jz      short loc_180040EB1
0x180040e75  mov     r12, [rsp+220h+Sid+8]
0x180040e7a  mov     r14, [rsp+220h+Sid]
0x180040e7f  mov     r15, [r14]
0x180040e82  test    r15, r15
0x180040e85  jz      short loc_180040EA0
0x180040e87  call    cs:__imp_GetLastError
0x180040e8d  mov     ebx, eax
0x180040e8f  mov     rcx, r15; hMem
0x180040e92  call    cs:__imp_LocalFree
0x180040e98  mov     ecx, ebx; dwErrCode
0x180040e9a  call    cs:__imp_SetLastError
0x180040ea0  mov     [r14], r12
0x180040ea3  or      r15, 0FFFFFFFFFFFFFFFFh
0x180040ea7  mov     r12, [rsp+220h+var_1B0]
0x180040eac  mov     r14, [rsp+220h+var_1B8]
0x180040eb1  test    r13d, r13d
0x180040eb4  jnz     short loc_180040EF7
0x180040eb6  call    cs:__imp_GetLastError
0x180040ebc  mov     ebx, eax
0x180040ebe  mov     r8d, eax
0x180040ec1  lea     rdx, aFailedConverti_0; "Failed converting owningUserSid to SID:"...
0x180040ec8  lea     ecx, [r13+2]; unsigned __int8
0x180040ecc  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180040ed1  test    ebx, ebx
0x180040ed3  jle     short loc_180040EDE
0x180040ed5  movzx   ebx, bx
0x180040ed8  or      ebx, 80070000h
0x180040ede  mov     rcx, [rsp+220h+hMem]; hMem
0x180040ee3  test    rcx, rcx
0x180040ee6  jz      loc_180041113
0x180040eec  call    cs:__imp_LocalFree
0x180040ef2  jmp     loc_180041113
0x180040ef7  xorps   xmm0, xmm0
0x180040efa  movups  [rbp+120h+var_E8], xmm0
0x180040efe  xorps   xmm1, xmm1
0x180040f01  movdqu  [rbp+120h+var_D8], xmm1
0x180040f06  mov     r8, r15
0x180040f09  xor     r13d, r13d
0x180040f0c  inc     r8
0x180040f0f  cmp     [rdi+r8*2], r13w
0x180040f14  jnz     short loc_180040F0C
0x180040f16  mov     rdx, rdi
0x180040f19  lea     rcx, [rbp+120h+var_E8]
0x180040f1d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180040f22  nop
0x180040f23  lea     r8, [rbp+120h+var_E8]
0x180040f27  lea     rdx, [rbp+120h+var_68]
0x180040f2e  mov     rcx, r14
0x180040f31  call    ?RecallAgentProfileDir@OwningUserRegistry@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@@Z; OwningUserRegistry::RecallAgentProfileDir(std::wstring const &)
0x180040f36  nop
0x180040f37  lea     rcx, [rbp+120h+var_E8]
0x180040f3b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180040f40  xorps   xmm0, xmm0
0x180040f43  movups  [rbp+120h+var_88], xmm0
0x180040f4a  xorps   xmm1, xmm1
0x180040f4d  movdqu  [rbp+120h+var_78], xmm1
0x180040f55  mov     r8, r15
0x180040f58  inc     r8
0x180040f5b  cmp     [rdi+r8*2], r13w
0x180040f60  jnz     short loc_180040F58
0x180040f62  mov     rdx, rdi
0x180040f65  lea     rcx, [rbp+120h+var_88]
0x180040f6c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180040f71  nop
0x180040f72  lea     r8, [rbp+120h+var_88]
0x180040f79  lea     rdx, [rsp+220h+pObjectName]
0x180040f7e  mov     rcx, r14
0x180040f81  call    ?RecallAgentSharedPaths@OwningUserRegistry@@QEAA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; OwningUserRegistry::RecallAgentSharedPaths(std::wstring const &)
0x180040f86  nop
0x180040f87  lea     rcx, [rbp+120h+var_88]
0x180040f8e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180040f93  mov     ebx, cs:dword_1800B9160
0x180040f99  mov     r14, [rbp+128h]
0x180040fa0  call    cs:__imp_GetCurrentThreadId
0x180040fa6  cmp     ebx, eax
0x180040fa8  jnz     loc_180041471
0x180040fae  lea     rax, ?g_lock@@3Vchecked_srwlock@@A; checked_srwlock g_lock
0x180040fb5  mov     [rsp+220h+var_1B0], rax
0x180040fba  mov     cs:dword_1800B9160, r13d
0x180040fc1  mov     rcx, rax; SRWLock
0x180040fc4  call    cs:__imp_ReleaseSRWLockExclusive
0x180040fca  nop
0x180040fcb  cmp     [rbp+120h+var_98], r13
0x180040fd2  jz      short loc_180040FF4
0x180040fd4  mov     rbx, [rsp+220h+pObjectName]
0x180040fd9  mov     r14, [rbp+120h+var_1A0]
0x180040fdd  jmp     short loc_180040FEF
0x180040fdf  lea     rdx, [rbp+120h+StringSid]; StringSid
0x180040fe3  mov     rcx, rbx; pObjectName
0x180040fe6  call    RemoveAllAccessForSid
0x180040feb  add     rbx, 20h ; ' '
0x180040fef  cmp     rbx, r14
0x180040ff2  jnz     short loc_180040FDF
0x180040ff4  mov     [rsp+220h+SessionId], r13d
0x180040ff9  lea     rdx, [rsp+220h+SessionId]; unsigned int *
0x180040ffe  mov     rcx, rsi; wchar_t *
0x180041001  call    ?FindSessionForUser@@YA_NPEB_WPEAK@Z; FindSessionForUser(wchar_t const *,ulong *)
0x180041006  test    al, al
0x180041008  jz      short loc_18004104D
0x18004100a  mov     r8d, 1; bWait
0x180041010  mov     edx, [rsp+220h+SessionId]; SessionId
0x180041014  xor     ecx, ecx; hServer
0x180041016  call    cs:__imp_WTSLogoffSession
0x18004101c  test    eax, eax
0x18004101e  jz      short loc_18004102E
0x180041020  lea     rdx, aSuccessfullyLo; "Successfully logged off %s"
0x180041027  mov     ecx, 4
0x18004102c  jmp     short loc_180041059
0x18004102e  call    cs:__imp_GetLastError
0x180041034  mov     r9d, eax
0x180041037  mov     r8, rsi
0x18004103a  lea     rdx, aFailedToLogOff; "Failed to log off %s: %#x"
0x180041041  mov     ecx, 2; unsigned __int8
0x180041046  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18004104b  jmp     short loc_180041061
0x18004104d  lea     rdx, aDidNotFindASes_0; "Did not find a session for AU %s"
0x180041054  mov     ecx, 3; unsigned __int8
0x180041059  mov     r8, rsi
0x18004105c  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180041061  lea     r8, [rbp+120h+var_68]
0x180041068  cmp     [rbp+120h+var_50], 7
0x180041070  cmova   r8, [rbp+120h+var_68]; wchar_t *
0x180041078  lea     rdx, [rbp+120h+StringSid]
0x18004107c  cmp     [rbp+120h+var_90], 7
0x180041084  cmova   rdx, qword ptr [rbp+120h+StringSid]; wchar_t *
0x180041089  mov     rcx, rsi; wchar_t *
0x18004108c  call    ?ReallyDeleteProfile@@YAJPEB_W00@Z; ReallyDeleteProfile(wchar_t const *,wchar_t const *,wchar_t const *)
0x180041091  mov     r14d, eax
0x180041094  test    eax, eax
0x180041096  jns     loc_180041123
0x18004109c  mov     rcx, [rbp+128h]; this
0x1800410a3  mov     r9d, eax; char *
0x1800410a6  lea     r8, aOnecoreuapWind_27; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800410ad  mov     edx, 3A1h; void *
0x1800410b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800410b7  nop
0x1800410b8  mov     ebx, cs:dword_1800B9160
0x1800410be  call    cs:__imp_GetCurrentThreadId
0x1800410c4  mov     edi, eax
0x1800410c6  mov     rcx, [rbp+128h]; this
0x1800410cd  cmp     ebx, eax
0x1800410cf  jz      loc_180041486
0x1800410d5  lea     rcx, ?g_lock@@3Vchecked_srwlock@@A; SRWLock
0x1800410dc  call    cs:__imp_AcquireSRWLockExclusive
0x1800410e2  mov     cs:dword_1800B9160, edi
0x1800410e8  lea     rcx, [rsp+220h+pObjectName]
0x1800410ed  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x1800410f2  nop
0x1800410f3  lea     rcx, [rbp+120h+var_68]
0x1800410fa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800410ff  nop
0x180041100  mov     rcx, [rsp+220h+hMem]; hMem
0x180041105  test    rcx, rcx
0x180041108  jz      short loc_180041110
0x18004110a  call    cs:__imp_LocalFree
0x180041110  mov     ebx, r14d
0x180041113  lea     rcx, [rbp+120h+StringSid]
0x180041117  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004111c  mov     eax, ebx
0x18004111e  jmp     loc_180041435
0x180041123  xorps   xmm0, xmm0
0x180041126  movups  xmmword ptr [rsp+220h+Sid], xmm0
0x18004112b  mov     rdx, r12; SourceString
0x18004112e  lea     rcx, [rsp+220h+Sid]; DestinationString
0x180041133  call    cs:__imp_RtlInitUnicodeStringEx
0x180041139  mov     rcx, [rbp+128h]; this
0x180041140  test    eax, eax
0x180041142  js      loc_180041498
0x180041148  xorps   xmm0, xmm0
0x18004114b  movups  xmmword ptr [rbp+120h+DestinationString.Length], xmm0
0x18004114f  mov     rdx, rdi; SourceString
0x180041152  lea     rcx, [rbp+120h+DestinationString]; DestinationString
0x180041156  call    cs:__imp_RtlInitUnicodeStringEx
0x18004115c  mov     rcx, [rbp+128h]; this
0x180041163  test    eax, eax
0x180041165  js      loc_1800414AD
0x18004116b  mov     r14d, r13d
0x18004116e  lea     r8, [rbp+120h+DestinationString]
0x180041172  lea     rdx, [rsp+220h+Sid]
0x180041177  mov     rcx, [rsp+220h+hMem]
0x18004117c  call    LsaDeleteAgentAccount
0x180041181  mov     ebx, eax
0x180041183  mov     r9, rsi
0x180041186  mov     r8, rdi
0x180041189  test    eax, eax
0x18004118b  jns     short loc_1800411C1
0x18004118d  cmp     eax, 0C0000064h
0x180041192  jnz     short loc_1800411A2
0x180041194  lea     rdx, aLsadeleteagent_0; "LsaDeleteAgentAccount: agent %s (%s) no"...
0x18004119b  mov     ecx, 3
0x1800411a0  jmp     short loc_1800411CD
0x1800411a2  mov     dword ptr [rsp+220h+var_200], ebx
0x1800411a6  lea     rdx, aLsadeleteagent; "LsaDeleteAgentAccount failed for agent "...
0x1800411ad  mov     ecx, 2; unsigned __int8
0x1800411b2  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800411b7  mov     r14d, ebx
0x1800411ba  bts     r14d, 1Ch
0x1800411bf  jmp     short loc_1800411D2
0x1800411c1  lea     rdx, aDeletedAgentSF; "Deleted agent %s from LSA (%s)."
0x1800411c8  mov     ecx, 4; unsigned __int8
0x1800411cd  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800411d2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59959135@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59959135@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59959135> `wil::Feature<__WilFeatureTraits_Feature_ID59959135>::GetImpl(void)'::`2'::impl
0x1800411d9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59959135@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59959135>::__private_IsEnabled(void)
0x1800411de  test    al, al
0x1800411e0  jz      loc_180041389
0x1800411e6  call    ?IsMemAuthorityPresent@@YA_NXZ; IsMemAuthorityPresent(void)
0x1800411eb  test    al, al
0x1800411ed  jz      loc_180041389
0x1800411f3  cmp     [rbp+120h+var_98], r13
0x1800411fa  jz      loc_180041389
0x180041200  lea     rcx, [rbp+120h+var_110]
0x180041204  call    ??0?$basic_regex@_WV?$regex_traits@_W@std@@@std@@QEAA@PEB_WW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<wchar_t,std::regex_traits<wchar_t>>::basic_regex<wchar_t,std::regex_traits<wchar_t>>(wchar_t const *,std::regex_constants::syntax_option_type)
0x180041209  nop
0x18004120a  mov     [rbp+120h+var_180], r13
0x18004120e  mov     [rbp+120h+var_178], r13b
0x180041212  xorps   xmm0, xmm0
0x180041215  movdqa  [rbp+120h+var_170], xmm0
0x18004121a  xorps   xmm1, xmm1
0x18004121d  movdqa  [rbp+120h+var_160], xmm1
0x180041222  mov     [rbp+120h+var_150], r13
0x180041226  mov     [rbp+120h+var_148], r13b
  ... truncated ...
```
