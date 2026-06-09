# Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::HandlePromptForUserWithAdditionalContext(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool,Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue)

- ea: `0x18006f230`
- end: `0x18006f8b6`
- name: `?HandlePromptForUserWithAdditionalContext@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@QEAA?AW4CapabilityConsentValue@2345@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0_NW462345@@Z`
- size: `1670`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x18006f1d0`
- `0x1800b6080`

## callees

- `0x1800094c0`
- `0x18001649c`
- `0x18001c3b4`
- `0x18001d00c`
- `0x18001e118`
- `0x18001e42c`
- `0x1800210d4`
- `0x1800257a4`
- `0x180028188`
- `0x180029408`
- `0x18002f93c`
- `0x18002f978`
- `0x18003fd60`
- `0x180041a88`
- `0x180041e2c`
- `0x18004f644`
- `0x180064fe4`
- `0x180067560`
- `0x18006f230`
- `0x18006fe24`
- `0x180070168`
- `0x180070824`
- `0x180074984`
- `0x18007a060`
- `0x18007e070`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18006f55d`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18006f5b2`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18006f55d`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18006f5b2`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContextFromSid` at `0x18006f38d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContextFromSid` at `0x18006f38d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18006f3c2`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18006f3c2`

## string_xrefs

- `0x18006f3a2`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x18006f3d7`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::HandlePromptForUserWithAdditionalContext(
        Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager *this,
        __int64 a2,
        int a3,
        char a4,
        unsigned int a5)
{
  char v5; // di
  __int64 v7; // r15
  Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager *v8; // r14
  Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore *v9; // rcx
  __int64 v10; // rax
  int v11; // eax
  Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager *v12; // rcx
  int v13; // eax
  unsigned __int64 v14; // rdx
  __int64 ImageFullPathFromProcessId; // rax
  __int64 AppFriendlyName; // rax
  _QWORD *FriendlyNameFromPackageFamilyAndUser; // rax
  int v18; // ebx
  int v19; // r9d
  const enum Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue *v20; // rdx
  const unsigned __int16 *v21; // rax
  const enum Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue *v22; // rdx
  const unsigned __int16 *v23; // rax
  unsigned __int64 v24; // rbx
  int v25; // r12d
  int v26; // r13d
  int v27; // eax
  __int64 v28; // rdi
  int v29; // ebx
  __int64 ConsentIdFromObjectId; // rax
  unsigned int v31; // ebx
  Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager *v33; // rbx
  const unsigned __int16 *v34; // rax
  __int64 v35; // r13
  const enum Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue *v36; // rdx
  const unsigned __int16 *v37; // rax
  __int64 v38; // r12
  int v39; // r15d
  __int64 v40; // r14
  int v41; // esi
  int v42; // edi
  wil *v43; // rcx
  int v44; // eax
  wil *v45; // rcx
  __int64 v46; // [rsp+0h] [rbp-398h] BYREF
  __int64 v47; // [rsp+20h] [rbp-378h]
  bool v48; // [rsp+70h] [rbp-328h]
  char v49; // [rsp+71h] [rbp-327h] BYREF
  char v50; // [rsp+72h] [rbp-326h] BYREF
  int v51; // [rsp+74h] [rbp-324h] BYREF
  char v52; // [rsp+78h] [rbp-320h]
  unsigned __int64 v53; // [rsp+80h] [rbp-318h] BYREF
  unsigned __int64 v54; // [rsp+88h] [rbp-310h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+90h] [rbp-308h] BYREF
  Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager *v56; // [rsp+98h] [rbp-300h]
  __int64 v57; // [rsp+A0h] [rbp-2F8h]
  __int64 v58; // [rsp+A8h] [rbp-2F0h]
  __int64 v59; // [rsp+B0h] [rbp-2E8h]
  _BYTE *v60; // [rsp+B8h] [rbp-2E0h]
  _BYTE *v61; // [rsp+C0h] [rbp-2D8h]
  _BYTE *v62; // [rsp+C8h] [rbp-2D0h]
  _BYTE *v63; // [rsp+D0h] [rbp-2C8h]
  _BYTE *v64; // [rsp+D8h] [rbp-2C0h]
  _BYTE *v65; // [rsp+E0h] [rbp-2B8h]
  _QWORD v66[6]; // [rsp+E8h] [rbp-2B0h] BYREF
  char v67; // [rsp+118h] [rbp-280h]
  unsigned __int64 v68; // [rsp+120h] [rbp-278h] BYREF
  unsigned int v69; // [rsp+128h] [rbp-270h]
  _BYTE v70[32]; // [rsp+130h] [rbp-268h] BYREF
  _BYTE v71[32]; // [rsp+150h] [rbp-248h] BYREF
  _BYTE v72[32]; // [rsp+170h] [rbp-228h] BYREF
  _BYTE v73[32]; // [rsp+190h] [rbp-208h] BYREF
  _BYTE v74[32]; // [rsp+1B0h] [rbp-1E8h] BYREF
  _BYTE v75[224]; // [rsp+1D0h] [rbp-1C8h] BYREF
  _BYTE v76[32]; // [rsp+2B0h] [rbp-E8h] BYREF
  _OWORD v77[2]; // [rsp+2D0h] [rbp-C8h] BYREF
  _BYTE v78[32]; // [rsp+2F0h] [rbp-A8h] BYREF
  _QWORD v79[4]; // [rsp+310h] [rbp-88h] BYREF
  _BYTE v80[32]; // [rsp+330h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+0h]

  v5 = a4;
  v7 = a2;
  v8 = this;
  v56 = this;
  v57 = a2;
  v52 = a4;
  LODWORD(v53) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids);
  }
  wil::ThreadFailureCache::ThreadFailureCache((wil::ThreadFailureCache *)v75);
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v66[0] = v75;
  v66[1] = v8;
  v66[2] = &v50;
  v66[3] = &v51;
  v66[4] = v7;
  v66[5] = &v49;
  v67 = 1;
  if ( *((_QWORD *)v8 + 14)
    && Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore::IsAutoAcceptConsentPromptsEnabled(v9) )
  {
    v49 = 1;
    std::wstring::wstring(v78, L"Auto accepting consent prompt. Returning 'Allow'");
    std::wstring::_Tidy_deallocate(v78);
    v51 = 1;
  }
  else
  {
    if ( *((_BYTE *)v8 + 37) || *((_BYTE *)v8 + 38) )
    {
      std::wstring::wstring(v76, L"Consent prompt suppressed by request of the caller. Returning '%ws'");
      std::wstring::_Tidy_deallocate(v76);
      v50 = 1;
      v67 = 0;
      lambda_233952395b2364fb4dca71b14338669a_::operator()(v66);
      wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v75);
      return a5;
    }
    v54 = 0;
    v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7);
    v11 = UMgrQueryUserContextFromSid(v10, &v54);
    v12 = retaddr;
    if ( v11 >= 0
      || (wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x835,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
            (const char *)(unsigned int)v11,
            v47),
          v13 = UMgrQueryUserContext(*((_QWORD *)v8 + 56), &v54),
          v12 = retaddr,
          v13 >= 0) )
    {
      v14 = v54;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x838,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
        (const char *)(unsigned int)v13,
        v47);
      v14 = 0;
      v54 = 0;
    }
    if ( v14 && Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::IsConsentPromptBlocked(v12, v14) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids);
      }
      v51 = 2;
      Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::NotifyUserConsentPromptBlocked(
        (HANDLE *)v8,
        v54);
    }
    else
    {
      v77[0] = 0;
      v77[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v77[0]) = 0;
      if ( *((_BYTE *)v8 + 36) )
      {
        std::wstring::operator=(v77, (char *)v8 + 168);
      }
      else
      {
        ImageFullPathFromProcessId = Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(
                                       v78,
                                       *((unsigned int *)v8 + 12));
        std::wstring::operator=(v77, ImageFullPathFromProcessId);
        std::wstring::_Tidy_deallocate(v78);
      }
      try
      {
        if ( *((_QWORD *)v8 + 10) )
        {
          AppFriendlyName = Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::get_AppFriendlyName();
          FriendlyNameFromPackageFamilyAndUser = (_QWORD *)std::wstring::wstring(v80, AppFriendlyName);
          v18 = 1;
        }
        else
        {
          FriendlyNameFromPackageFamilyAndUser = Windows::Internal::CapabilityAccess::Private::GetFriendlyNameFromPackageFamilyAndUser(
                                                   v79,
                                                   (__int64)v8 + 168,
                                                   v7,
                                                   (HANDLE *)v8 + 56);
          v18 = 2;
        }
        LODWORD(v53) = v18;
        std::wstring::wstring(v78, FriendlyNameFromPackageFamilyAndUser);
        if ( (v18 & 2) != 0 )
        {
          LOBYTE(v18) = v18 & 0xFD;
          std::wstring::_Tidy_deallocate(v79);
        }
        if ( (v18 & 1) != 0 )
          std::wstring::_Tidy_deallocate(v80);
        UnbiasedTime = 0;
        QueryUnbiasedInterruptTime(&UnbiasedTime);
        LOBYTE(v19) = v5;
        v51 = Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::RequestConsentFromUser(
                (_DWORD)v8,
                v54,
                a3,
                v19,
                (__int64)v78,
                9);
        Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::QueryUserConsentStoreCreatedCount(
          &v68,
          v7);
        v53 = 0;
        QueryUnbiasedInterruptTime(&v53);
        v48 = *((_BYTE *)v8 + 29);
        v60 = v70;
        v21 = Windows::Internal::CapabilityAccess::Private::CapabilityConsentValueToString(
                (Windows::Internal::CapabilityAccess::Private *)&v51,
                v20);
        v58 = std::wstring::wstring(v70, v21);
        v61 = v71;
        v23 = Windows::Internal::CapabilityAccess::Private::CapabilityConsentValueToString(
                (Windows::Internal::CapabilityAccess::Private *)&a5,
                v22);
        v59 = std::wstring::wstring(v71, v23);
        v24 = v53 - UnbiasedTime;
        v25 = 2 - (*((_BYTE *)v8 + 36) != 0);
        v62 = v72;
        UnbiasedTime = std::wstring::wstring(v72, v77);
        v63 = v73;
        v53 = std::wstring::wstring(v73, (char *)v8 + 264);
        v64 = v74;
        v26 = std::wstring::wstring(v74, (char *)v8 + 296);
        v27 = std::wstring::wstring(v76, v7);
        LogPromptAttempted(0, v27, v26, v53, UnbiasedTime, v25, v59, v58, v48, 1, 9u, v24, v69, v68);
        std::wstring::_Tidy_deallocate(v78);
      }
      catch ( wil::ResultException )
      {
        v33 = v56;
        v48 = *((_BYTE *)v56 + 29);
        v65 = v76;
        v34 = Windows::Internal::CapabilityAccess::Private::CapabilityConsentValueToString(
                (Windows::Internal::CapabilityAccess::Private *)&v51,
                (const enum Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue *)&v46);
        v35 = std::wstring::wstring(v76, v34);
        v64 = v74;
        v37 = Windows::Internal::CapabilityAccess::Private::CapabilityConsentValueToString(
                (Windows::Internal::CapabilityAccess::Private *)&a5,
                v36);
        v38 = std::wstring::wstring(v74, v37);
        v39 = 2 - (*((_BYTE *)v33 + 36) != 0);
        v63 = v73;
        v40 = std::wstring::wstring(v73, v77);
        v62 = v72;
        v41 = std::wstring::wstring(v72, (char *)v33 + 296);
        v61 = v71;
        v42 = std::wstring::wstring(v71, (char *)v33 + 296);
        LODWORD(v33) = std::wstring::wstring(v70, v57);
        v44 = wil::ResultFromCaughtException(v43);
        LogPromptAttempted(v44, (_DWORD)v33, v42, v41, v40, v39, v38, v35, v48, 0, 9u, 0, 0, 0);
        if ( (unsigned int)wil::ResultFromCaughtException(v45) == -2147023673 )
        {
          v51 = 2;
          v8 = v56;
          v7 = v57;
          v5 = v52;
          goto LABEL_32;
        }
        throw;
      }
LABEL_32:
      std::wstring::_Tidy_deallocate(v77);
    }
  }
  if ( v5 && *((_QWORD *)v8 + 12) && v51 != 6 )
  {
    std::wstring::wstring(v76, L"Persisting consent value '%ws' in the consent store");
    std::wstring::_Tidy_deallocate(v76);
    v28 = *((_QWORD *)v8 + 12);
    v29 = v51;
    ConsentIdFromObjectId = Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::GetConsentIdFromObjectId(
                              v28,
                              v76,
                              (char *)v8 + 360);
    Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::SetUserAppConsent(
      v28,
      v7,
      ConsentIdFromObjectId,
      (char *)v8 + 168,
      v29);
    std::wstring::_Tidy_deallocate(v76);
  }
  std::wstring::wstring(v76, L"Returning with '%ws'");
  std::wstring::_Tidy_deallocate(v76);
  v31 = v51;
  v67 = 0;
  lambda_233952395b2364fb4dca71b14338669a_::operator()(v66);
  wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v75);
  return v31;
}

```

## disassembly

```asm
0x18006f230  push    rbx
0x18006f232  push    rsi
0x18006f233  push    rdi
0x18006f234  push    r12
0x18006f236  push    r13
0x18006f238  push    r14
0x18006f23a  push    r15
0x18006f23c  sub     rsp, 360h
0x18006f243  mov     rax, cs:__security_cookie
0x18006f24a  xor     rax, rsp
0x18006f24d  mov     [rsp+398h+var_48], rax
0x18006f255  mov     dil, r9b
0x18006f258  mov     r12, r8
0x18006f25b  mov     r15, rdx
0x18006f25e  mov     r14, rcx
0x18006f261  mov     [rsp+398h+var_300], rcx
0x18006f269  mov     [rsp+398h+var_2F8], rdx
0x18006f271  mov     [rsp+398h+var_320], r9b
0x18006f276  xor     esi, esi
0x18006f278  mov     dword ptr [rsp+398h+var_318], esi
0x18006f27f  lea     rbx, WPP_GLOBAL_Control
0x18006f286  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f28d  cmp     rcx, rbx
0x18006f290  jz      short loc_18006F2B1
0x18006f292  test    byte ptr [rcx+1Ch], 1
0x18006f296  jz      short loc_18006F2B1
0x18006f298  cmp     byte ptr [rcx+19h], 5
0x18006f29c  jb      short loc_18006F2B1
0x18006f29e  lea     edx, [rsi+22h]
0x18006f2a1  lea     r8, WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids
0x18006f2a8  mov     rcx, [rcx+10h]
0x18006f2ac  call    WPP_SF_
0x18006f2b1  lea     rcx, [rsp+398h+var_1C8]; this
0x18006f2b9  call    ??0ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::ThreadFailureCache(void)
0x18006f2be  nop
0x18006f2bf  mov     [rsp+398h+var_327], sil
0x18006f2c4  mov     [rsp+398h+var_326], sil
0x18006f2c9  mov     [rsp+398h+var_324], esi
0x18006f2cd  lea     rax, [rsp+398h+var_1C8]
0x18006f2d5  mov     [rsp+398h+var_2B0], rax
0x18006f2dd  mov     [rsp+398h+var_2A8], r14
0x18006f2e5  lea     rax, [rsp+398h+var_326]
0x18006f2ea  mov     [rsp+398h+var_2A0], rax
0x18006f2f2  lea     rax, [rsp+398h+var_324]
0x18006f2f7  mov     [rsp+398h+var_298], rax
0x18006f2ff  mov     [rsp+398h+var_290], r15
0x18006f307  lea     rax, [rsp+398h+var_327]
0x18006f30c  mov     [rsp+398h+var_288], rax
0x18006f314  mov     [rsp+398h+var_280], 1
0x18006f31c  cmp     [r14+70h], rsi
0x18006f320  jz      short loc_18006F35E
0x18006f322  call    ?IsAutoAcceptConsentPromptsEnabled@CapabilityConsentPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA_NXZ; Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore::IsAutoAcceptConsentPromptsEnabled(void)
0x18006f327  test    al, al
0x18006f329  jz      short loc_18006F35E
0x18006f32b  mov     [rsp+398h+var_327], 1
0x18006f330  lea     rdx, aAutoAcceptingC; "Auto accepting consent prompt. Returnin"...
0x18006f337  lea     rcx, [rsp+398h+var_A8]
0x18006f33f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006f344  lea     rcx, [rsp+398h+var_A8]
0x18006f34c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f351  mov     [rsp+398h+var_324], 1
0x18006f359  jmp     loc_18006F77D
0x18006f35e  cmp     [r14+25h], sil
0x18006f362  jnz     loc_18006F843
0x18006f368  cmp     [r14+26h], sil
0x18006f36c  jnz     loc_18006F843
0x18006f372  mov     [rsp+398h+var_310], rsi
0x18006f37a  mov     rcx, r15
0x18006f37d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18006f382  lea     rdx, [rsp+398h+var_310]
0x18006f38a  mov     rcx, rax
0x18006f38d  call    cs:__imp_UMgrQueryUserContextFromSid
0x18006f393  mov     rcx, [rsp+398h]; this
0x18006f39b  test    eax, eax
0x18006f39d  jns     short loc_18006F3F5
0x18006f39f  mov     r9d, eax; char *
0x18006f3a2  lea     r8, aOnecoreBaseDev_58; "onecore\\base\\devices\\cam\\core\\capa"...
0x18006f3a9  mov     edx, 835h; void *
0x18006f3ae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006f3b3  lea     rdx, [rsp+398h+var_310]
0x18006f3bb  mov     rcx, [r14+1C0h]
0x18006f3c2  call    cs:__imp_UMgrQueryUserContext
0x18006f3c8  mov     rcx, [rsp+398h]; this
0x18006f3d0  test    eax, eax
0x18006f3d2  jns     short loc_18006F3F5
0x18006f3d4  mov     r9d, eax; char *
0x18006f3d7  lea     r8, aOnecoreBaseDev_58; "onecore\\base\\devices\\cam\\core\\capa"...
0x18006f3de  mov     edx, 838h; void *
0x18006f3e3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006f3e8  mov     rdx, rsi
0x18006f3eb  mov     [rsp+398h+var_310], rdx
0x18006f3f3  jmp     short loc_18006F3FD
0x18006f3f5  mov     rdx, [rsp+398h+var_310]; unsigned __int64
0x18006f3fd  test    rdx, rdx
0x18006f400  jz      short loc_18006F455
0x18006f402  call    ?IsConsentPromptBlocked@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@AEAA_N_K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::IsConsentPromptBlocked(unsigned __int64)
0x18006f407  test    al, al
0x18006f409  jz      short loc_18006F455
0x18006f40b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f412  cmp     rcx, rbx
0x18006f415  jz      short loc_18006F438
0x18006f417  test    byte ptr [rcx+1Ch], 1
0x18006f41b  jz      short loc_18006F438
0x18006f41d  cmp     byte ptr [rcx+19h], 2
0x18006f421  jb      short loc_18006F438
0x18006f423  mov     edx, 23h ; '#'
0x18006f428  lea     r8, WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids
0x18006f42f  mov     rcx, [rcx+10h]
0x18006f433  call    WPP_SF_
0x18006f438  mov     [rsp+398h+var_324], 2
0x18006f440  mov     rdx, [rsp+398h+var_310]; unsigned __int64
0x18006f448  mov     rcx, r14; this
0x18006f44b  call    ?NotifyUserConsentPromptBlocked@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@AEAAX_K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::NotifyUserConsentPromptBlocked(unsigned __int64)
0x18006f450  jmp     loc_18006F77D
0x18006f455  xorps   xmm0, xmm0
0x18006f458  movups  [rsp+398h+var_C8], xmm0
0x18006f460  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18006f468  movdqu  [rsp+398h+var_B8], xmm1
0x18006f471  mov     word ptr [rsp+398h+var_C8], si
0x18006f479  lea     rbx, [r14+0A8h]
0x18006f480  cmp     [r14+24h], sil
0x18006f484  jz      short loc_18006F498
0x18006f486  mov     rdx, rbx
0x18006f489  lea     rcx, [rsp+398h+var_C8]
0x18006f491  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18006f496  jmp     short loc_18006F4C7
0x18006f498  mov     edx, [r14+30h]
0x18006f49c  lea     rcx, [rsp+398h+var_A8]
0x18006f4a4  call    ?GetImageFullPathFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(ulong)
0x18006f4a9  mov     rdx, rax
0x18006f4ac  lea     rcx, [rsp+398h+var_C8]
0x18006f4b4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006f4b9  lea     rcx, [rsp+398h+var_A8]
0x18006f4c1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f4c6  nop
0x18006f4c7  mov     rcx, [r14+50h]
0x18006f4cb  test    rcx, rcx
0x18006f4ce  jz      short loc_18006F4ED
0x18006f4d0  call    ?get_AppFriendlyName@AdjustedAppDisplayInfo@Private@CapabilityAccess@Internal@Windows@@QEAAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::AdjustedAppDisplayInfo::get_AppFriendlyName(void)
0x18006f4d5  mov     rdx, rax
0x18006f4d8  lea     rcx, [rsp+398h+var_68]
0x18006f4e0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006f4e5  nop
0x18006f4e6  mov     ebx, 1
0x18006f4eb  jmp     short loc_18006F50D
0x18006f4ed  lea     r9, [r14+1C0h]
0x18006f4f4  mov     r8, r15
0x18006f4f7  mov     rdx, rbx
0x18006f4fa  lea     rcx, [rsp+398h+var_88]
0x18006f502  call    ?GetFriendlyNameFromPackageFamilyAndUser@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@0AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::GetFriendlyNameFromPackageFamilyAndUser(std::wstring const &,std::wstring const &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x18006f507  nop
0x18006f508  mov     ebx, 2
0x18006f50d  mov     dword ptr [rsp+398h+var_318], ebx
0x18006f514  mov     rdx, rax
0x18006f517  lea     rcx, [rsp+398h+var_A8]
0x18006f51f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006f524  nop
0x18006f525  test    bl, 2
0x18006f528  jz      short loc_18006F53B
0x18006f52a  and     ebx, 0FFFFFFFDh
0x18006f52d  lea     rcx, [rsp+398h+var_88]
0x18006f535  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f53a  nop
0x18006f53b  test    bl, 1
0x18006f53e  jz      short loc_18006F54D
0x18006f540  lea     rcx, [rsp+398h+var_68]
0x18006f548  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f54d  mov     [rsp+398h+UnbiasedTime], rsi
0x18006f555  lea     rcx, [rsp+398h+UnbiasedTime]; UnbiasedTime
0x18006f55d  call    cs:__imp_QueryUnbiasedInterruptTime
0x18006f563  mov     [rsp+398h+var_370], 9
0x18006f56b  lea     rax, [rsp+398h+var_A8]
0x18006f573  mov     [rsp+398h+var_378], rax
0x18006f578  mov     r9b, dil
0x18006f57b  mov     r8, r12
0x18006f57e  mov     rdx, [rsp+398h+var_310]
0x18006f586  mov     rcx, r14
0x18006f589  call    ?RequestConsentFromUser@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@QEAA?AW4CapabilityConsentValue@2345@_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N1W4DeviceAccessConsentType@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::RequestConsentFromUser(unsigned __int64,std::wstring const &,bool,std::wstring const &,DeviceAccessConsentType)
0x18006f58e  mov     [rsp+398h+var_324], eax
0x18006f592  mov     rdx, r15
0x18006f595  lea     rcx, [rsp+398h+var_278]
0x18006f59d  call    ?QueryUserConsentStoreCreatedCount@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$tuple@I_K@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::QueryUserConsentStoreCreatedCount(std::wstring const &)
0x18006f5a2  mov     [rsp+398h+var_318], rsi
0x18006f5aa  lea     rcx, [rsp+398h+var_318]; UnbiasedTime
0x18006f5b2  call    cs:__imp_QueryUnbiasedInterruptTime
0x18006f5b8  mov     al, [r14+1Dh]
0x18006f5bc  mov     [rsp+398h+var_328], al
0x18006f5c0  lea     rcx, [rsp+398h+var_268]
0x18006f5c8  mov     [rsp+398h+var_2E0], rcx
0x18006f5d0  lea     rcx, [rsp+398h+var_324]; this
0x18006f5d5  call    ?CapabilityConsentValueToString@Private@CapabilityAccess@Internal@Windows@@YAPEBGAEBW4CapabilityConsentValue@1234@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentValueToString(Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue const &)
0x18006f5da  mov     rdx, rax
0x18006f5dd  lea     rcx, [rsp+398h+var_268]
0x18006f5e5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006f5ea  mov     [rsp+398h+var_2F0], rax
0x18006f5f2  lea     rax, [rsp+398h+var_248]
0x18006f5fa  mov     [rsp+398h+var_2D8], rax
0x18006f602  lea     rcx, [rsp+398h+arg_20]; this
0x18006f60a  call    ?CapabilityConsentValueToString@Private@CapabilityAccess@Internal@Windows@@YAPEBGAEBW4CapabilityConsentValue@1234@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentValueToString(Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue const &)
0x18006f60f  mov     rdx, rax
0x18006f612  lea     rcx, [rsp+398h+var_248]
0x18006f61a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006f61f  mov     [rsp+398h+var_2E8], rax
0x18006f627  mov     rbx, [rsp+398h+var_318]
0x18006f62f  sub     rbx, [rsp+398h+UnbiasedTime]
0x18006f637  mov     cl, [r14+24h]
0x18006f63b  neg     cl
0x18006f63d  sbb     r12d, r12d
0x18006f640  add     r12d, 2
0x18006f644  lea     rax, [rsp+398h+var_228]
0x18006f64c  mov     [rsp+398h+var_2D0], rax
0x18006f654  lea     rdx, [rsp+398h+var_C8]
0x18006f65c  lea     rcx, [rsp+398h+var_228]
0x18006f664  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006f669  mov     [rsp+398h+UnbiasedTime], rax
0x18006f671  lea     rax, [rsp+398h+var_208]
0x18006f679  mov     [rsp+398h+var_2C8], rax
0x18006f681  lea     rdx, [r14+108h]
0x18006f688  lea     rcx, [rsp+398h+var_208]
0x18006f690  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006f695  mov     [rsp+398h+var_318], rax
0x18006f69d  lea     rax, [rsp+398h+var_1E8]
0x18006f6a5  mov     [rsp+398h+var_2C0], rax
0x18006f6ad  lea     rdx, [r14+128h]
0x18006f6b4  lea     rcx, [rsp+398h+var_1E8]
0x18006f6bc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006f6c1  mov     r13, rax
0x18006f6c4  mov     rdx, r15
0x18006f6c7  lea     rcx, [rsp+398h+var_E8]
0x18006f6cf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006f6d4  nop
0x18006f6d5  mov     rcx, [rsp+398h+var_278]
0x18006f6dd  mov     [rsp+398h+var_330], rcx
0x18006f6e2  mov     ecx, [rsp+398h+var_270]
0x18006f6e9  mov     [rsp+398h+var_338], ecx
0x18006f6ed  mov     [rsp+398h+var_340], rbx
0x18006f6f2  mov     [rsp+398h+var_348], 9
0x18006f6fa  mov     [rsp+398h+var_350], 1
0x18006f6ff  mov     cl, [rsp+398h+var_328]
0x18006f703  mov     [rsp+398h+var_358], cl
0x18006f707  mov     rcx, [rsp+398h+var_2F0]
0x18006f70f  mov     [rsp+398h+var_360], rcx
0x18006f714  mov     rcx, [rsp+398h+var_2E8]
0x18006f71c  mov     [rsp+398h+var_368], rcx
0x18006f721  mov     [rsp+398h+var_370], r12d
0x18006f726  mov     rcx, [rsp+398h+UnbiasedTime]
0x18006f72e  mov     [rsp+398h+var_378], rcx
0x18006f733  mov     r9, [rsp+398h+var_318]
0x18006f73b  mov     r8, r13
0x18006f73e  mov     rdx, rax
0x18006f741  xor     ecx, ecx
0x18006f743  call    ?LogPromptAttempted@@YAXJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000W4AppIdType@Private@CapabilityAccess@Internal@Windows@@00_N2I_KI3@Z; LogPromptAttempted(long,std::wstring,std::wstring,std::wstring,std::wstring,Windows::Internal::CapabilityAccess::Private::AppIdType,std::wstring,std::wstring,bool,bool,uint,unsigned __int64,uint,unsigned __int64)
0x18006f748  nop
0x18006f749  lea     rcx, [rsp+398h+var_A8]
0x18006f751  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f756  nop
0x18006f757  jmp     short loc_18006F770
0x18006f759  xor     esi, esi
0x18006f75b  mov     r14, [rsp+398h+var_300]
0x18006f763  mov     r15, [rsp+398h+var_2F8]
0x18006f76b  mov     dil, [rsp+398h+var_320]
0x18006f770  lea     rcx, [rsp+398h+var_C8]
0x18006f778  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f77d  test    dil, dil
0x18006f780  jz      short loc_18006F7F7
0x18006f782  cmp     [r14+60h], rsi
0x18006f786  jz      short loc_18006F7F7
0x18006f788  cmp     [rsp+398h+var_324], 6
0x18006f78d  jz      short loc_18006F7F7
0x18006f78f  lea     rdx, aPersistingCons; "Persisting consent value '%ws' in the c"...
0x18006f796  lea     rcx, [rsp+398h+var_E8]
0x18006f79e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006f7a3  lea     rcx, [rsp+398h+var_E8]
0x18006f7ab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f7b0  mov     rdi, [r14+60h]
0x18006f7b4  mov     ebx, [rsp+398h+var_324]
0x18006f7b8  lea     r8, [r14+168h]
0x18006f7bf  lea     rdx, [rsp+398h+var_E8]
0x18006f7c7  mov     rcx, rdi
0x18006f7ca  call    ?GetConsentIdFromObjectId@CapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV67@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::GetConsentIdFromObjectId(std::wstring const &)
0x18006f7cf  nop
0x18006f7d0  lea     r9, [r14+0A8h]
0x18006f7d7  mov     dword ptr [rsp+398h+var_378], ebx
0x18006f7db  mov     r8, rax
0x18006f7de  mov     rdx, r15
0x18006f7e1  mov     rcx, rdi
0x18006f7e4  call    ?SetUserAppConsent@CapabilityConsentManager@Private@CapabilityAccess@Internal@Windows@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00W4CapabilityConsentValue@2345@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::SetUserAppConsent(std::wstring const &,std::wstring const &,std::wstring const &,Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue)
0x18006f7e9  nop
0x18006f7ea  lea     rcx, [rsp+398h+var_E8]
0x18006f7f2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f7f7  lea     rdx, aReturningWithW; "Returning with '%ws'"
0x18006f7fe  lea     rcx, [rsp+398h+var_E8]
0x18006f806  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006f80b  lea     rcx, [rsp+398h+var_E8]
0x18006f813  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f818  mov     ebx, [rsp+398h+var_324]
0x18006f81c  mov     [rsp+398h+var_280], sil
0x18006f824  lea     rcx, [rsp+398h+var_2B0]
0x18006f82c  call    _lambda_233952395b2364fb4dca71b14338669a___operator__
0x18006f831  nop
  ... truncated ...
```
