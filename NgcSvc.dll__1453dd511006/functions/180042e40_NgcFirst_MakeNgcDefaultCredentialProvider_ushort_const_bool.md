# NgcFirst::MakeNgcDefaultCredentialProvider(ushort const *,bool)

- ea: `0x180042e40`
- end: `0x18004470c`
- name: `?MakeNgcDefaultCredentialProvider@NgcFirst@@YAJPEBG_N@Z`
- size: `6348`
- prototype: `__int64 __fastcall(NgcFirst *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800745dc`

## callees

- `0x18000782c`
- `0x180007850`
- `0x180007964`
- `0x1800083d0`
- `0x18000bce0`
- `0x18000e570`
- `0x18000e960`
- `0x1800294c0`
- `0x180029f0c`
- `0x180042a1c`
- `0x180042e40`
- `0x180044714`
- `0x180045318`
- `0x180048304`
- `0x18004d408`
- `0x180053188`
- `0x180053618`
- `0x18005cee0`
- `0x18005d2b0`
- `0x18005d2ec`
- `0x18005dd20`
- `0x18005dd2c`
- `0x18005dd38`
- `0x180069398`
- `0x1800853a0`
- `0x1800856b8`
- `0x18008598c`
- `0x180085ba0`
- `0x180085d04`
- `0x180085e40`
- `0x1800c0a30`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180042fb8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800439e6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180042fb8`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800439e6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004303c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004303c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042eea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800440e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042eea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800440e0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180043a9c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180043a9c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043b00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043b3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043b00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043b3b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043ad3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043ad3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180042ebf`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180042ebf`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180042f06`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x180042f06`

## string_xrefs

- `0x180042e7f`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180042ecd`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180042fcd`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x1800430eb`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x1800431f8`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180043851`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x1800438c5`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180043912`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180043a52`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180043ae5`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180043b11`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180043bb1`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180043c3d`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180043c8a`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180043cd5`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180043d20`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180043d6d`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180043e25`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180043e84`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180043ed8`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180043f33`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180043f81`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180043fef`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180044049`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180044110`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x18004414a`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180044199`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x1800441d7`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180044231`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x18004428f`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x1800442e9`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180044392`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x1800443d1`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180044424`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180044473`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x1800444b1`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x18004450b`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180044569`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x1800445c3`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x18004466c`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x1800446aa`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcFirst::MakeNgcDefaultCredentialProvider(WCHAR *this, const unsigned __int16 *a2)
{
  int LastError; // ebx
  const char *v5; // r9
  int v6; // eax
  int v7; // ebx
  int v8; // ebx
  DWORD LengthSid; // eax
  PSID v10; // rsi
  size_t v11; // rdi
  void *v12; // rax
  void *v13; // rcx
  _QWORD *v14; // rax
  ULONGLONG v15; // rbx
  int v16; // eax
  struct _GUID *v17; // r8
  unsigned __int64 v18; // rdx
  void *v19; // rax
  unsigned __int64 v20; // rdx
  void *v21; // rcx
  unsigned __int64 v22; // rdx
  void *v23; // rcx
  int LastLoggedOnCredProviderForUser; // eax
  int v25; // eax
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // r14
  unsigned __int64 v28; // rdi
  __int64 v29; // rsi
  unsigned __int64 v30; // rdx
  void **v31; // rcx
  char *v32; // r12
  unsigned __int64 v33; // r13
  unsigned __int64 v34; // rbx
  size_t v35; // r8
  char *v36; // r14
  void *v37; // rbx
  unsigned __int64 v38; // rdx
  _BYTE *v39; // rcx
  unsigned __int64 v40; // r14
  unsigned __int64 v41; // rcx
  unsigned __int64 v42; // rdi
  unsigned __int64 v43; // rdi
  void **v44; // rbx
  unsigned __int64 v45; // rcx
  char *v46; // r13
  unsigned __int64 v47; // r12
  unsigned __int64 v48; // rbx
  size_t v49; // r8
  size_t v50; // r14
  char *v51; // rbx
  void *v52; // rbx
  unsigned __int64 v53; // rdx
  _BYTE *v54; // rcx
  unsigned __int64 v55; // r12
  unsigned __int64 v56; // rdi
  unsigned __int64 v57; // rdx
  void **v58; // rcx
  char *v59; // r14
  unsigned __int64 v60; // r13
  unsigned __int64 v61; // rbx
  size_t v62; // r8
  char *v63; // r12
  void *v64; // rbx
  unsigned __int64 v65; // rdx
  _BYTE *v66; // rcx
  unsigned __int64 v67; // r13
  unsigned __int64 v68; // r12
  unsigned __int64 v69; // rdi
  void **v70; // rbx
  unsigned __int64 v71; // rbx
  unsigned __int64 v72; // rcx
  unsigned __int64 v73; // rdx
  char *v74; // rdi
  size_t v75; // r8
  char *v76; // r14
  char *v77; // rsi
  void *v78; // rbx
  unsigned __int64 v79; // rdx
  void *v80; // rcx
  void **v81; // rcx
  int UserOptOutStatus; // eax
  char v83; // si
  void **v84; // rcx
  int v85; // eax
  void **v86; // rcx
  int v87; // eax
  bool v88; // di
  void **v89; // rbx
  unsigned int Key; // eax
  __int64 v91; // rdx
  void **v92; // rcx
  __int64 v93; // rdx
  void **v94; // rcx
  int v95; // eax
  void **v96; // rcx
  int v97; // eax
  void **v98; // rcx
  int v99; // eax
  void **v100; // rcx
  int v101; // eax
  void **v102; // rcx
  int v103; // eax
  void **v104; // rcx
  int v105; // eax
  void **v106; // rcx
  int v107; // eax
  void **v108; // rcx
  int v109; // eax
  void **v110; // rcx
  int v111; // eax
  void *v112; // rdx
  void **v113; // rcx
  void **v114; // rcx
  int v115; // eax
  unsigned int v116; // edi
  void **v117; // rcx
  int v118; // eax
  int v119; // eax
  const struct _GUID *v120; // r8
  int v121; // eax
  int v122; // eax
  const struct _GUID *v123; // r8
  int v124; // eax
  void **v125; // rcx
  int v126; // eax
  void **v127; // rcx
  int v128; // eax
  unsigned int v129; // edi
  void **v130; // rcx
  int v131; // eax
  int v132; // eax
  const struct _GUID *v133; // r8
  void **v134; // rcx
  int v135; // eax
  int BestNgcCredProvForUser; // eax
  const struct _GUID *v137; // r8
  int LoggedOnCredProviderForUser; // eax
  void **v139; // rcx
  int SwitchCounts; // eax
  void **v141; // rcx
  int v142; // eax
  unsigned int v143; // edi
  void **v144; // rcx
  int v145; // eax
  int v146; // eax
  const struct _GUID *v147; // r8
  int v148; // eax
  unsigned int UserDataCount; // [rsp+20h] [rbp-E0h]
  int UserDataCounta; // [rsp+20h] [rbp-E0h]
  int UserDataCountb; // [rsp+20h] [rbp-E0h]
  int UserDataCountc; // [rsp+20h] [rbp-E0h]
  PSID Sid; // [rsp+50h] [rbp-B0h] BYREF
  char v154; // [rsp+58h] [rbp-A8h]
  char v155; // [rsp+59h] [rbp-A7h]
  bool v156; // [rsp+5Ah] [rbp-A6h]
  unsigned int v157; // [rsp+5Ch] [rbp-A4h] BYREF
  char v158; // [rsp+60h] [rbp-A0h]
  BYTE v159[8]; // [rsp+68h] [rbp-98h] BYREF
  char v160; // [rsp+70h] [rbp-90h]
  BYTE Data[4]; // [rsp+74h] [rbp-8Ch] BYREF
  void *Src[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v163; // [rsp+88h] [rbp-78h]
  unsigned __int64 v164; // [rsp+90h] [rbp-70h]
  __int128 Buf1; // [rsp+98h] [rbp-68h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+A8h] [rbp-58h] BYREF
  char *v167; // [rsp+B8h] [rbp-48h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C0h] [rbp-40h] BYREF
  __int16 *v169; // [rsp+D0h] [rbp-30h]
  int v170; // [rsp+D8h] [rbp-28h]
  int v171; // [rsp+DCh] [rbp-24h]
  __int128 *p_Buf1; // [rsp+E0h] [rbp-20h]
  __int64 v173; // [rsp+E8h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v160 = (char)a2;
  if ( !this )
  {
    LastError = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
      (const char *)0x80004003LL,
      UserDataCount);
    return (unsigned int)LastError;
  }
  Sid = 0;
  if ( !ConvertStringSidToSidW(this, &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x51,
                  (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                  v5);
    goto LABEL_6;
  }
  v158 = 1;
  *(_DWORD *)v159 = 0;
  v6 = LsaLookupUserAccountType(Sid, v159);
  v7 = v6;
  if ( v6 >= 0 )
  {
    switch ( *(_DWORD *)v159 )
    {
      case 1:
        v8 = 1;
        break;
      case 2:
      case 3:
        v8 = 3;
        break;
      case 4:
        v8 = 2;
        break;
      case 5:
      case 6:
        v8 = 4;
        break;
      default:
        v8 = 0;
        break;
    }
    v157 = v8;
    if ( (unsigned int)(v8 - 3) <= 1 )
      v158 = 0;
  }
  else
  {
    if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(Buf1) = v6;
      p_Buf1 = &Buf1;
      v173 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_180122078;
      UserData.Size = *(unsigned __int16 *)off_180122078;
      UserData.Reserved = 2;
      v169 = (__int16 *)&unk_180107690;
      v170 = 36;
      v171 = 1;
      v157 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    LastError = v7 | 0x10000000;
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x56,
        (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
        (const char *)(unsigned int)LastError,
        UserDataCount);
      goto LABEL_6;
    }
    v157 = 0;
  }
  LengthSid = GetLengthSid(Sid);
  v10 = Sid;
  EventDescriptor = 0;
  v167 = 0;
  v11 = LengthSid;
  if ( LengthSid )
  {
    if ( LengthSid < 0x1000uLL )
    {
      v14 = operator new(LengthSid);
    }
    else
    {
      if ( (unsigned __int64)LengthSid + 39 < LengthSid )
        std::_Throw_bad_array_new_length();
      v12 = operator new(LengthSid + 39LL);
      v13 = v12;
      if ( !v12 )
        goto LABEL_45;
      v14 = (_QWORD *)(((unsigned __int64)v12 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v14 - 1) = v13;
    }
    *(_QWORD *)&EventDescriptor.Id = v14;
    v15 = (ULONGLONG)v14 + v11;
    v167 = (char *)v14 + v11;
    memmove_0(v14, v10, v11);
    EventDescriptor.Keyword = v15;
  }
  *(_DWORD *)v159 = 0;
  v16 = NgcUtils::QueryLogonCredsAvailableRegState(&EventDescriptor, v159);
  LastError = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
      (const char *)(unsigned int)v16,
      UserDataCount);
    if ( !*(_QWORD *)&EventDescriptor.Id )
      goto LABEL_6;
    v18 = (unsigned __int64)&v167[-*(_QWORD *)&EventDescriptor.Id];
    if ( (unsigned __int64)&v167[-*(_QWORD *)&EventDescriptor.Id] >= 0x1000 )
    {
      v19 = *(void **)(*(_QWORD *)&EventDescriptor.Id - 8LL);
      if ( (unsigned __int64)(*(_QWORD *)&EventDescriptor.Id - (_QWORD)v19 - 8LL) <= 0x1F )
      {
        operator delete(v19, v18 + 39);
        goto LABEL_6;
      }
LABEL_45:
      __fastfail(5u);
    }
    operator delete(*(void **)&EventDescriptor.Id, v18);
LABEL_6:
    if ( Sid )
      LocalFree(Sid);
    return (unsigned int)LastError;
  }
  if ( *(_DWORD *)v159 != 2 )
  {
    if ( *(_QWORD *)&EventDescriptor.Id )
    {
      v20 = (unsigned __int64)&v167[-*(_QWORD *)&EventDescriptor.Id];
      if ( (unsigned __int64)&v167[-*(_QWORD *)&EventDescriptor.Id] < 0x1000 )
      {
        operator delete(*(void **)&EventDescriptor.Id, v20);
      }
      else
      {
        v21 = *(void **)(*(_QWORD *)&EventDescriptor.Id - 8LL);
        if ( (unsigned __int64)(*(_QWORD *)&EventDescriptor.Id - (_QWORD)v21 - 8LL) > 0x1F )
          goto LABEL_45;
        operator delete(v21, v20 + 39);
      }
    }
    goto LABEL_245;
  }
  if ( *(_QWORD *)&EventDescriptor.Id )
  {
    v22 = (unsigned __int64)&v167[-*(_QWORD *)&EventDescriptor.Id];
    if ( (unsigned __int64)&v167[-*(_QWORD *)&EventDescriptor.Id] < 0x1000 )
    {
      v23 = *(void **)&EventDescriptor.Id;
    }
    else
    {
      v23 = *(void **)(*(_QWORD *)&EventDescriptor.Id - 8LL);
      if ( (unsigned __int64)(*(_QWORD *)&EventDescriptor.Id - (_QWORD)v23 - 8LL) > 0x1F )
        goto LABEL_45;
      v22 += 39LL;
    }
    operator delete(v23, v22);
  }
  Buf1 = 0;
  LastLoggedOnCredProviderForUser = CredProvUtils::GetLastLoggedOnCredProviderForUser(
                                      (CredProvUtils *)this,
                                      (const unsigned __int16 *)&Buf1,
                                      v17);
  LastError = LastLoggedOnCredProviderForUser;
  if ( LastLoggedOnCredProviderForUser < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
      (const char *)(unsigned int)LastLoggedOnCredProviderForUser,
      UserDataCount);
    goto LABEL_6;
  }
  if ( memcmp_0(&Buf1, &CLSID_NgcUtils_FidoCredentialProvider, 0x10u) )
  {
    v154 = 0;
    v156 = !memcmp_0(&Buf1, &CLSID_NgcUtils_NgcPinProvider, 0x10u)
        || !memcmp_0(&Buf1, &CLSID_NgcUtils_DeviceNgcProvider, 0x10u)
        || !memcmp_0(&Buf1, &CLSID_NgcUtils_WinBioCredentialProvider, 0x10u)
        || !memcmp_0(&Buf1, &CLSID_NgcUtils_FaceCredentialProvider, 0x10u);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2NgcBioFirst>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_K2NgcBioFirst>::GetImpl'::`2'::impl) )
    {
      if ( !memcmp_0(&Buf1, &CLSID_NgcUtils_WinBioCredentialProvider, 0x10u)
        || (v25 = memcmp_0(&Buf1, &CLSID_NgcUtils_FaceCredentialProvider, 0x10u), v154 = 0, !v25) )
      {
        v154 = 1;
      }
    }
    std::wstring::wstring(
      (char **)Src,
      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Providers\\{D6886603-9D2F-4EB2-B667-1971041FA96B}");
    v27 = v163;
    v28 = v164;
    v29 = 0x7FFFFFFFFFFFFFFELL;
    if ( v164 == v163 )
    {
      if ( v163 == 0x7FFFFFFFFFFFFFFELL )
        goto LABEL_313;
      v33 = v163 + 1;
      v34 = (v163 + 1) | 7;
      if ( v34 <= 0x7FFFFFFFFFFFFFFELL )
      {
        v26 = v164 >> 1;
        if ( v164 <= 0x7FFFFFFFFFFFFFFELL - (v164 >> 1) )
        {
          if ( v34 < v26 + v164 )
            v34 = v26 + v164;
        }
        else
        {
          v34 = 0x7FFFFFFFFFFFFFFELL;
        }
      }
      else
      {
        v34 = 0x7FFFFFFFFFFFFFFELL;
      }
      v32 = (char *)std::allocator<unsigned short>::allocate(v26, v34 + 1);
      v163 = v27 + 1;
      v164 = v34;
      v35 = 2 * v27;
      v36 = &v32[2 * v27];
      if ( v28 <= 7 )
      {
        memcpy_0(v32, Src, v35);
        *(_WORD *)v36 = asc_1800DB4FC[0];
        *(_WORD *)&v32[2 * v33] = 0;
      }
      else
      {
        v37 = Src[0];
        memcpy_0(v32, Src[0], v35);
        *(_WORD *)v36 = asc_1800DB4FC[0];
        *(_WORD *)&v32[2 * v33] = 0;
        v38 = 2 * v28 + 2;
        if ( v38 < 0x1000 )
        {
          operator delete(v37, v38);
        }
        else
        {
          v39 = (_BYTE *)*((_QWORD *)v37 - 1);
          if ( (unsigned __int64)((_BYTE *)v37 - v39 - 8) > 0x1F )
            goto LABEL_130;
          operator delete(v39, 2 * v28 + 41);
        }
      }
      Src[0] = v32;
    }
    else
    {
      v30 = ++v163;
      v31 = Src;
      if ( v164 > 7 )
        v31 = (void **)Src[0];
      *((_WORD *)v31 + v27) = asc_1800DB4FC[0];
      *((_WORD *)v31 + v30) = 0;
      v32 = (char *)Src[0];
    }
    v40 = -1;
    do
      ++v40;
    while ( this[v40] );
    v41 = v163;
    *(_QWORD *)v159 = v163;
    v42 = v164;
    *(_QWORD *)&Buf1 = v164;
    if ( v40 > v164 - v163 )
    {
      if ( 0x7FFFFFFFFFFFFFFELL - v163 < v40 )
        goto LABEL_313;
      v47 = v40 + v163;
      v48 = (v40 + v163) | 7;
      if ( v48 <= 0x7FFFFFFFFFFFFFFELL )
      {
        v41 = v164 >> 1;
        if ( v164 <= 0x7FFFFFFFFFFFFFFELL - (v164 >> 1) )
        {
          if ( v48 < v41 + v164 )
            v48 = v41 + v164;
        }
        else
        {
          v48 = 0x7FFFFFFFFFFFFFFELL;
        }
      }
      else
      {
        v48 = 0x7FFFFFFFFFFFFFFELL;
      }
      v46 = (char *)std::allocator<unsigned short>::allocate(v41, v48 + 1);
      v163 = v47;
      v164 = v48;
      v49 = 2LL * *(_QWORD *)v159;
      v50 = 2 * v40;
      v51 = &v46[2 * *(_QWORD *)v159];
      *(_QWORD *)&Buf1 = v51;
      if ( v42 <= 7 )
      {
        memcpy_0(v46, Src, v49);
        memcpy_0(v51, this, v50);
        *(_WORD *)&v46[2 * v47] = 0;
      }
      else
      {
        v52 = Src[0];
        memcpy_0(v46, Src[0], v49);
        memcpy_0((void *)Buf1, this, v50);
        *(_WORD *)&v46[2 * v47] = 0;
        v53 = 2 * v42 + 2;
        if ( v53 < 0x1000 )
        {
          operator delete(v52, v53);
        }
        else
        {
          v54 = (_BYTE *)*((_QWORD *)v52 - 1);
          if ( (unsigned __int64)((_BYTE *)v52 - v54 - 8) > 0x1F )
            goto LABEL_130;
          operator delete(v54, 2 * v42 + 41);
        }
      }
      Src[0] = v46;
    }
    else
    {
      v43 = v40 + v163;
      v163 += v40;
      v44 = Src;
      if ( (unsigned __int64)Buf1 > 7 )
        v44 = (void **)v32;
      memmove_0((char *)v44 + 2 * v41, this, 2 * v40);
      *((_WORD *)v44 + v43) = 0;
      v46 = (char *)Src[0];
    }
    v55 = v163;
    v56 = v164;
    if ( v164 == v163 )
    {
      if ( v163 == 0x7FFFFFFFFFFFFFFELL )
        goto LABEL_313;
      v60 = v163 + 1;
      v61 = (v163 + 1) | 7;
      if ( v61 <= 0x7FFFFFFFFFFFFFFELL )
      {
        v45 = v164 >> 1;
        if ( v164 <= 0x7FFFFFFFFFFFFFFELL - (v164 >> 1) )
        {
          if ( v61 < v45 + v164 )
            v61 = v45 + v164;
        }
        else
        {
          v61 = 0x7FFFFFFFFFFFFFFELL;
        }
      }
      else
      {
        v61 = 0x7FFFFFFFFFFFFFFELL;
      }
      v59 = (char *)std::allocator<unsigned short>::allocate(v45, v61 + 1);
      v163 = v55 + 1;
      v164 = v61;
      v62 = 2 * v55;
      v63 = &v59[2 * v55];
      if ( v56 <= 7 )
      {
        memcpy_0(v59, Src, v62);
        *(_WORD *)v63 = asc_1800DB4FC[0];
        *(_WORD *)&v59[2 * v60] = 0;
      }
      else
      {
        v64 = Src[0];
        memcpy_0(v59, Src[0], v62);
        *(_WORD *)v63 = asc_1800DB4FC[0];
        *(_WORD *)&v59[2 * v60] = 0;
        v65 = 2 * v56 + 2;
        if ( v65 < 0x1000 )
        {
          operator delete(v64, v65);
        }
        else
        {
          v66 = (_BYTE *)*((_QWORD *)v64 - 1);
          if ( (unsigned __int64)((_BYTE *)v64 - v66 - 8) > 0x1F )
            goto LABEL_130;
          operator delete(v66, 2 * v56 + 41);
        }
      }
      Src[0] = v59;
    }
    else
    {
      v57 = ++v163;
      v58 = Src;
      if ( v164 > 7 )
        v58 = (void **)v46;
      *((_WORD *)v58 + v55) = asc_1800DB4FC[0];
      *((_WORD *)v58 + v57) = 0;
      v59 = (char *)Src[0];
    }
    v67 = v163;
    v68 = v164;
    if ( v164 - v163 >= 8 )
    {
      v69 = v163 + 8;
      v163 += 8LL;
      v70 = Src;
      if ( v164 > 7 )
        v70 = (void **)v59;
      memmove_0((char *)v70 + 2 * v67, L"NgcFirst", 0x10u);
      *((_WORD *)v70 + v69) = 0;
LABEL_134:
      *(_DWORD *)Data = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2NgcBioFirst>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_K2NgcBioFirst>::GetImpl'::`2'::impl) )
      {
        v155 = 0;
        v81 = Src;
        if ( v164 > 7 )
          v81 = (void **)Src[0];
        UserOptOutStatus = NgcFirst::GetUserOptOutStatus((LPCWSTR)v81);
        LastError = UserOptOutStatus;
        if ( UserOptOutStatus < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x8C,
            (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
            (const char *)(unsigned int)UserOptOutStatus,
            UserDataCount);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
          goto LABEL_6;
        }
        v83 = v154;
        if ( v155 )
        {
          if ( v154 )
          {
            v84 = Src;
            if ( v164 > 7 )
              v84 = (void **)Src[0];
            v85 = NgcFirst::SetSwitchCountsHelper(
                    (LPCWSTR)v84,
                    L"ConsecutiveSwitchCountBio",
                    (unsigned int)Data,
                    L"MaxSwitchCountBio",
                    0);
            LastError = v85;
            if ( v85 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x92,
                (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                (const char *)(unsigned int)v85,
                UserDataCount);
              std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
              goto LABEL_6;
            }
            v86 = Src;
            if ( v164 > 7 )
              v86 = (void **)Src[0];
            v87 = NgcFirst::SetUserOptOutStatus((LPCWSTR)v86, L"OptOutBio");
            LastError = v87;
            if ( v87 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x93,
                (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                (const char *)(unsigned int)v87,
                UserDataCount);
              std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
              goto LABEL_6;
            }
            if ( (unsigned int)dword_180122070 > 5
              && (qword_180122080 & 0x400000000000LL) != 0
              && (qword_180122088 & 0x400000000000LL) == qword_180122088 )
            {
              *(_DWORD *)&EventDescriptor.Id = 184549376;
              *(_DWORD *)&EventDescriptor.Level = 5;
              EventDescriptor.Keyword = 0x400000000000LL;
              UserData.Ptr = (ULONGLONG)off_180122078;
              UserData.Size = *(unsigned __int16 *)off_180122078;
              UserData.Reserved = 2;
              v169 = word_180105D62;
              v170 = 25;
              v171 = 1;
              LODWORD(Buf1) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
              EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &UserData);
            }
          }
          v88 = v156;
          if ( v156 )
          {
            v89 = Src;
            if ( v164 > 7 )
              v89 = (void **)Src[0];
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2NgcBioFirst>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_K2NgcBioFirst>::GetImpl'::`2'::impl) )
            {
              LastError = NgcFirst::SetSwitchCountsHelper(
                            (LPCWSTR)v89,
                            L"ConsecutiveSwitchCount",
                            (unsigned int)Data,
                            L"MaxSwitchCount",
                            0);
            }
            else
            {
              if ( !v89 )
              {
                LastError = -2147467261;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1F4,
                  (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                  (const char *)0x80004003LL,
                  UserDataCount);
LABEL_167:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x9B,
                  (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                  (const char *)(unsigned int)LastError,
                  UserDataCount);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                goto LABEL_6;
              }
              *(_QWORD *)&Buf1 = 0;
              Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v89, 0, 0, 0, 0x20006u, 0, (PHKEY)&Buf1, 0);
              if ( Key )
              {
                v91 = 514;
              }
              else
              {
                Key = RegSetValueExW((HKEY)Buf1, L"ConsecutiveSwitchCount", 0, 4u, Data, 4u);
                if ( !Key )
                {
                  if ( (_QWORD)Buf1 )
                    RegCloseKey((HKEY)Buf1);
                  goto LABEL_170;
                }
                v91 = 525;
              }
              LastError = wil::details::in1diag3::Return_Win32(
                            retaddr,
                            (void *)v91,
                            (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                            (const char *)Key,
                            UserDataCount);
              if ( (_QWORD)Buf1 )
                RegCloseKey((HKEY)Buf1);
            }
            if ( LastError < 0 )
              goto LABEL_167;
LABEL_170:
            v92 = Src;
            if ( v164 > 7 )
              v92 = (void **)Src[0];
            LastError = NgcFirst::SetUserOptOutStatus((LPCWSTR)v92, L"OptOut");
            if ( LastError < 0 )
            {
              v93 = 156;
LABEL_279:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v93,
                (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                (const char *)(unsigned int)LastError,
                UserDataCount);
              std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
              goto LABEL_6;
            }
            goto LABEL_244;
          }
LABEL_176:
          v155 = 0;
          v94 = Src;
          if ( v164 > 7 )
            v94 = (void **)Src[0];
          v95 = NgcFirst::GetUserOptOutStatus((LPCWSTR)v94);
          LastError = v95;
          if ( v95 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA3,
              (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
              (const char *)(unsigned int)v95,
              UserDataCount);
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
            goto LABEL_6;
          }
          if ( v155 )
          {
            if ( v88 )
            {
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2NgcBioFirst>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_K2NgcBioFirst>::GetImpl'::`2'::impl) )
              {
                if ( v83 )
                {
                  v96 = Src;
                  if ( v164 > 7 )
                    v96 = (void **)Src[0];
                  v97 = NgcFirst::SetSwitchCountsHelper(
                          (LPCWSTR)v96,
                          L"ConsecutiveSwitchCountBio",
                          (unsigned int)Data,
                          L"MaxSwitchCountBio",
                          0);
                  LastError = v97;
                  if ( v97 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xAE,
                      (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                      (const char *)(unsigned int)v97,
                      UserDataCount);
                    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                    goto LABEL_6;
                  }
                  v98 = Src;
                  if ( v164 > 7 )
                    v98 = (void **)Src[0];
                  v99 = NgcFirst::SetUserOptOutStatus((LPCWSTR)v98, L"OptOutBio");
                  LastError = v99;
                  if ( v99 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0xAF,
                      (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                      (const char *)(unsigned int)v99,
                      UserDataCount);
                    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                    goto LABEL_6;
                  }
                }
                v100 = Src;
                if ( v164 > 7 )
                  v100 = (void **)Src[0];
                v101 = NgcFirst::SetSwitchCounts((LPCWSTR)v100, Data, 0);
                LastError = v101;
                if ( v101 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xB1,
                    (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                    (const char *)(unsigned int)v101,
                    UserDataCount);
                  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                  goto LABEL_6;
                }
              }
              else
              {
                v102 = Src;
                if ( v164 > 7 )
                  v102 = (void **)Src[0];
                v103 = NgcFirst::SetSwitchCounts((LPCWSTR)v102, Data, 0);
                LastError = v103;
                if ( v103 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xB5,
                    (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                    (const char *)(unsigned int)v103,
                    UserDataCount);
                  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                  goto LABEL_6;
                }
              }
              v104 = Src;
              if ( v164 > 7 )
                v104 = (void **)Src[0];
              v105 = NgcFirst::SetUserOptOutStatus((LPCWSTR)v104, L"OptOut");
              LastError = v105;
              if ( v105 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xB7,
                  (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                  (const char *)(unsigned int)v105,
                  UserDataCount);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                goto LABEL_6;
              }
              if ( (unsigned int)dword_180122070 > 5
                && (qword_180122080 & 0x400000000000LL) != 0
                && (qword_180122088 & 0x400000000000LL) == qword_180122088 )
              {
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
                  (__int64)&dword_180122070,
                  (unsigned __int8 *)byte_180105D35,
                  0);
              }
            }
            goto LABEL_244;
          }
          if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2NgcBioFirst>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_K2NgcBioFirst>::GetImpl'::`2'::impl) )
          {
            if ( v88 )
            {
              v134 = Src;
              if ( v164 > 7 )
                v134 = (void **)Src[0];
              v135 = NgcFirst::SetSwitchCounts((LPCWSTR)v134, Data, 0);
              LastError = v135;
              if ( v135 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x114,
                  (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                  (const char *)(unsigned int)v135,
                  UserDataCount);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                goto LABEL_6;
              }
            }
            else if ( v160 )
            {
              EventDescriptor = 0;
              BestNgcCredProvForUser = NgcFirst::GetBestNgcCredProvForUser(this);
              LastError = BestNgcCredProvForUser;
              if ( BestNgcCredProvForUser < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x11C,
                  (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                  (const char *)(unsigned int)BestNgcCredProvForUser,
                  UserDataCount);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                goto LABEL_6;
              }
              LoggedOnCredProviderForUser = CredProvUtils::SetLastLoggedOnCredProviderForUser(
                                              (CredProvUtils *)this,
                                              (IID *)&EventDescriptor,
                                              v137);
              LastError = LoggedOnCredProviderForUser;
              if ( LoggedOnCredProviderForUser < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x11D,
                  (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                  (const char *)(unsigned int)LoggedOnCredProviderForUser,
                  UserDataCount);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                goto LABEL_6;
              }
            }
            else
            {
              *(_DWORD *)v159 = 0;
              LODWORD(Buf1) = 0;
              v139 = Src;
              if ( v164 > 7 )
                v139 = (void **)Src[0];
              SwitchCounts = NgcFirst::GetSwitchCounts((LPCWSTR)v139);
              LastError = SwitchCounts;
              if ( SwitchCounts < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x123,
                  (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                  (const char *)(unsigned int)SwitchCounts,
                  UserDataCount);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                goto LABEL_6;
              }
              if ( *(_DWORD *)v159 == -1 )
                SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
              ++*(_DWORD *)v159;
              v141 = Src;
              if ( v164 > 7 )
                v141 = (void **)Src[0];
              v142 = NgcFirst::SetSwitchCounts((LPCWSTR)v141, v159, 0);
              LastError = v142;
              if ( v142 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x126,
                  (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                  (const char *)(unsigned int)v142,
                  UserDataCount);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                goto LABEL_6;
              }
              v143 = Buf1;
              if ( (unsigned int)Buf1 > *(_DWORD *)v159 )
              {
                EventDescriptor = 0;
                v146 = NgcFirst::GetBestNgcCredProvForUser(this);
                LastError = v146;
                if ( v146 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x134,
                    (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                    (const char *)(unsigned int)v146,
                    UserDataCount);
                  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                  goto LABEL_6;
                }
                v148 = CredProvUtils::SetLastLoggedOnCredProviderForUser(
                         (CredProvUtils *)this,
                         (IID *)&EventDescriptor,
                         v147);
                LastError = v148;
                if ( v148 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x135,
                    (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                    (const char *)(unsigned int)v148,
                    UserDataCount);
                  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                  goto LABEL_6;
                }
              }
              else
              {
                v144 = Src;
                if ( v164 > 7 )
                  v144 = (void **)Src[0];
                v145 = NgcFirst::SetUserOptOutStatus((LPCWSTR)v144, L"OptOut");
                LastError = v145;
                if ( v145 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x12A,
                    (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                    (const char *)(unsigned int)v145,
                    UserDataCount);
                  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                  goto LABEL_6;
                }
                if ( (unsigned int)dword_180122070 > 5
                  && (qword_180122080 & 0x400000000000LL) != 0
                  && (qword_180122088 & 0x400000000000LL) == qword_180122088 )
                {
                  LODWORD(Buf1) = v157;
                  v157 = v143;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                    (__int64)&dword_180122070,
                    (unsigned __int8 *)&word_180105C7E,
                    0,
                    0,
                    (__int64)&v157,
                    (__int64)&Buf1);
                }
              }
            }
            goto LABEL_244;
          }
          if ( v83 )
          {
            v106 = Src;
            if ( v164 > 7 )
              v106 = (void **)Src[0];
            v107 = NgcFirst::SetSwitchCounts((LPCWSTR)v106, Data, 0);
            LastError = v107;
            if ( v107 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC4,
                (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                (const char *)(unsigned int)v107,
                UserDataCount);
              std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
              goto LABEL_6;
            }
            v108 = Src;
            if ( v164 > 7 )
              v108 = (void **)Src[0];
            v109 = NgcFirst::SetSwitchCountsHelper(
                     (LPCWSTR)v108,
                     L"ConsecutiveSwitchCountBio",
                     (unsigned int)Data,
                     L"MaxSwitchCountBio",
                     0);
            LastError = v109;
            if ( v109 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC5,
                (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                (const char *)(unsigned int)v109,
                UserDataCounta);
              std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
              goto LABEL_6;
            }
            goto LABEL_244;
          }
          if ( !v88 )
          {
            if ( v160 )
            {
              EventDescriptor = 0;
              v122 = NgcFirst::GetBestNgcCredProvForUser(this);
              LastError = v122;
              if ( v122 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xF2,
                  (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                  (const char *)(unsigned int)v122,
                  UserDataCount);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                goto LABEL_6;
              }
              v124 = CredProvUtils::SetLastLoggedOnCredProviderForUser(
                       (CredProvUtils *)this,
                       (IID *)&EventDescriptor,
                       v123);
              LastError = v124;
              if ( v124 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xF3,
                  (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                  (const char *)(unsigned int)v124,
                  UserDataCount);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                goto LABEL_6;
              }
            }
            else
            {
              *(_DWORD *)v159 = 0;
              LODWORD(Buf1) = 0;
              v125 = Src;
              if ( v164 > 7 )
                v125 = (void **)Src[0];
              v126 = NgcFirst::GetSwitchCounts((LPCWSTR)v125);
              LastError = v126;
              if ( v126 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xF9,
                  (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                  (const char *)(unsigned int)v126,
                  UserDataCount);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                goto LABEL_6;
              }
              if ( *(_DWORD *)v159 == -1 )
                SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
              ++*(_DWORD *)v159;
              v127 = Src;
              if ( v164 > 7 )
                v127 = (void **)Src[0];
              v128 = NgcFirst::SetSwitchCounts((LPCWSTR)v127, v159, 0);
              LastError = v128;
              if ( v128 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xFC,
                  (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                  (const char *)(unsigned int)v128,
                  UserDataCount);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                goto LABEL_6;
              }
              v129 = Buf1;
              if ( (unsigned int)Buf1 > *(_DWORD *)v159 )
              {
                EventDescriptor = 0;
                v132 = NgcFirst::GetBestNgcCredProvForUser(this);
                LastError = v132;
                if ( v132 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x10A,
                    (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                    (const char *)(unsigned int)v132,
                    UserDataCount);
                  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                  goto LABEL_6;
                }
                LastError = CredProvUtils::SetLastLoggedOnCredProviderForUser(
                              (CredProvUtils *)this,
                              (IID *)&EventDescriptor,
                              v133);
                if ( LastError < 0 )
                {
                  v93 = 267;
                  goto LABEL_279;
                }
              }
              else
              {
                v130 = Src;
                if ( v164 > 7 )
                  v130 = (void **)Src[0];
                v131 = NgcFirst::SetUserOptOutStatus((LPCWSTR)v130, L"OptOut");
                LastError = v131;
                if ( v131 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x100,
                    (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                    (const char *)(unsigned int)v131,
                    UserDataCount);
                  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                  goto LABEL_6;
                }
                if ( (unsigned int)dword_180122070 > 5
                  && (qword_180122080 & 0x400000000000LL) != 0
                  && (qword_180122088 & 0x400000000000LL) == qword_180122088 )
                {
                  LODWORD(Buf1) = v157;
                  v157 = v129;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                    (__int64)&dword_180122070,
                    (unsigned __int8 *)byte_180105CB9,
                    0,
                    0,
                    (__int64)&v157,
                    (__int64)&Buf1);
                }
              }
            }
LABEL_244:
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
            goto LABEL_245;
          }
          v110 = Src;
          if ( v164 > 7 )
            v110 = (void **)Src[0];
          v111 = NgcFirst::SetSwitchCounts((LPCWSTR)v110, Data, 0);
          LastError = v111;
          if ( v111 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xCA,
              (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
              (const char *)(unsigned int)v111,
              UserDataCount);
            std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
            goto LABEL_6;
          }
          if ( (NgcUtils::GetEnrolledBiometricsFromRegistry(Sid, v112) & 0xA) == 0 )
            goto LABEL_244;
          *(_DWORD *)v159 = 0;
          LODWORD(Buf1) = 0;
          if ( v164 <= 7 )
          {
            v113 = Src;
          }
          else
          {
            v113 = (void **)Src[0];
            if ( !Src[0] )
            {
              LastError = -2147467261;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x384,
                (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                (const char *)0x80004003LL,
                UserDataCount);
              goto LABEL_229;
            }
          }
          LastError = NgcFirst::GetSwitchCountsHelper((LPCWSTR)v113, L"ConsecutiveSwitchCountBio", (__int64)&Buf1, 3);
          if ( LastError >= 0 )
          {
            if ( *(_DWORD *)v159 == -1 )
              SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
            ++*(_DWORD *)v159;
            v114 = Src;
            if ( v164 > 7 )
              v114 = (void **)Src[0];
            v115 = NgcFirst::SetSwitchCountsHelper(
                     (LPCWSTR)v114,
                     L"ConsecutiveSwitchCountBio",
                     (unsigned int)v159,
                     L"MaxSwitchCountBio",
                     0);
            LastError = v115;
            if ( v115 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xD7,
                (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                (const char *)(unsigned int)v115,
                UserDataCountc);
              std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
              goto LABEL_6;
            }
            v116 = Buf1;
            if ( (unsigned int)Buf1 > *(_DWORD *)v159 )
            {
              EventDescriptor = 0;
              v119 = NgcFirst::GetBestNgcCredProvForUser(this);
              LastError = v119;
              if ( v119 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xE7,
                  (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                  (const char *)(unsigned int)v119,
                  UserDataCountc);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                goto LABEL_6;
              }
              v121 = CredProvUtils::SetLastLoggedOnCredProviderForUser(
                       (CredProvUtils *)this,
                       (IID *)&EventDescriptor,
                       v120);
              LastError = v121;
              if ( v121 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xE8,
                  (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                  (const char *)(unsigned int)v121,
                  UserDataCountc);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                goto LABEL_6;
              }
            }
            else
            {
              v117 = Src;
              if ( v164 > 7 )
                v117 = (void **)Src[0];
              v118 = NgcFirst::SetUserOptOutStatus((LPCWSTR)v117, L"OptOutBio");
              LastError = v118;
              if ( v118 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xDB,
                  (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
                  (const char *)(unsigned int)v118,
                  UserDataCountc);
                std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
                goto LABEL_6;
              }
              if ( (unsigned int)dword_180122070 > 5
                && (qword_180122080 & 0x400000000000LL) != 0
                && (qword_180122088 & 0x400000000000LL) == qword_180122088 )
              {
                LODWORD(Buf1) = v157;
                v157 = v116;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  (__int64)&dword_180122070,
                  (unsigned __int8 *)&dword_180105CF4,
                  0,
                  0,
                  (__int64)&v157,
                  (__int64)&Buf1);
              }
            }
            goto LABEL_244;
          }
LABEL_229:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD4,
            (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
            (const char *)(unsigned int)LastError,
            UserDataCountb);
          std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Src);
          goto LABEL_6;
        }
      }
      else
      {
        v83 = v154;
      }
      v88 = v156;
      goto LABEL_176;
    }
    if ( 0x7FFFFFFFFFFFFFFELL - v163 >= 8 )
    {
      v71 = v163 + 8;
      v72 = (v163 + 8) | 7;
      if ( v72 <= 0x7FFFFFFFFFFFFFFELL )
      {
        v73 = v164 >> 1;
        if ( v164 <= 0x7FFFFFFFFFFFFFFELL - (v164 >> 1) )
        {
          v29 = (v163 + 8) | 7;
          if ( v72 < v73 + v164 )
            v29 = v73 + v164;
        }
      }
      v74 = (char *)std::allocator<unsigned short>::allocate(v72, v29 + 1);
      v163 = v67 + 8;
      v164 = v29;
      v75 = 2 * v67;
      v76 = &v74[2 * v67];
      v77 = &v74[2 * v71];
      if ( v68 <= 7 )
      {
        memcpy_0(v74, Src, v75);
        *(_OWORD *)v76 = *(_OWORD *)L"NgcFirst";
        *(_WORD *)v77 = 0;
        goto LABEL_133;
      }
      v78 = Src[0];
      memcpy_0(v74, Src[0], v75);
      *(_OWORD *)v76 = *(_OWORD *)L"NgcFirst";
      *(_WORD *)v77 = 0;
      v79 = 2 * v68 + 2;
      if ( v79 < 0x1000 )
      {
        operator delete(v78, v79);
        goto LABEL_133;
      }
      v80 = (void *)*((_QWORD *)v78 - 1);
      if ( (unsigned __int64)((_BYTE *)v78 - (_BYTE *)v80 - 8) <= 0x1F )
      {
        operator delete(v80, 2 * v68 + 41);
LABEL_133:
        Src[0] = v74;
        goto LABEL_134;
      }
LABEL_130:
      __fastfail(5u);
    }
LABEL_313:
    std::_Xlen_string();
  }
LABEL_245:
  if ( Sid )
    LocalFree(Sid);
  return 0;
}

```

## disassembly

```asm
0x180042e40  push    rbp
0x180042e42  push    rbx
0x180042e43  push    rsi
0x180042e44  push    rdi
0x180042e45  push    r12
0x180042e47  push    r13
0x180042e49  push    r14
0x180042e4b  push    r15
0x180042e4d  lea     rbp, [rsp-8]
0x180042e52  sub     rsp, 108h
0x180042e59  mov     rax, cs:__security_cookie
0x180042e60  xor     rax, rsp
0x180042e63  mov     [rbp+40h+var_50], rax
0x180042e67  mov     [rsp+140h+var_D0], dl
0x180042e6b  mov     r15, rcx
0x180042e6e  test    rcx, rcx
0x180042e71  jnz     short loc_180042EB2
0x180042e73  mov     rcx, [rbp+48h]; this
0x180042e77  mov     ebx, 80004003h
0x180042e7c  mov     r9d, ebx; char *
0x180042e7f  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\ngc\\credprov\\u"...
0x180042e86  mov     edx, 4Eh ; 'N'; void *
0x180042e8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042e90  mov     eax, ebx
0x180042e92  mov     rcx, [rbp+40h+var_50]
0x180042e96  xor     rcx, rsp; StackCookie
0x180042e99  call    __security_check_cookie
0x180042e9e  add     rsp, 108h
0x180042ea5  pop     r15
0x180042ea7  pop     r14
0x180042ea9  pop     r13
0x180042eab  pop     r12
0x180042ead  pop     rdi
0x180042eae  pop     rsi
0x180042eaf  pop     rbx
0x180042eb0  pop     rbp
0x180042eb1  retn
0x180042eb2  xor     r13d, r13d
0x180042eb5  mov     [rsp+140h+Sid], r13
0x180042eba  lea     rdx, [rsp+140h+Sid]; Sid
0x180042ebf  call    cs:__imp_ConvertStringSidToSidW
0x180042ec5  test    eax, eax
0x180042ec7  jnz     short loc_180042EF2
0x180042ec9  mov     rcx, [rbp+48h]; this
0x180042ecd  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\ngc\\credprov\\u"...
0x180042ed4  mov     edx, 51h ; 'Q'; void *
0x180042ed9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180042ede  mov     ebx, eax
0x180042ee0  mov     rcx, [rsp+140h+Sid]; hMem
0x180042ee5  test    rcx, rcx
0x180042ee8  jz      short loc_180042E90
0x180042eea  call    cs:__imp_LocalFree
0x180042ef0  jmp     short loc_180042E90
0x180042ef2  mov     [rsp+140h+var_E0], 1
0x180042ef7  mov     dword ptr [rsp+140h+var_D8], r13d
0x180042efc  lea     rdx, [rsp+140h+var_D8]
0x180042f01  mov     rcx, [rsp+140h+Sid]
0x180042f06  call    cs:__imp_LsaLookupUserAccountType
0x180042f0c  mov     ebx, eax
0x180042f0e  lea     rdx, _TraceLoggingMetadata
0x180042f15  test    eax, eax
0x180042f17  jns     loc_180042FEA
0x180042f1d  mov     ecx, cs:dword_180122070
0x180042f23  cmp     ecx, 2
0x180042f26  jbe     loc_180042FBE
0x180042f2c  mov     dword ptr [rbp+40h+Buf1], eax
0x180042f2f  lea     rax, [rbp+40h+Buf1]
0x180042f33  mov     [rbp+40h+var_60], rax
0x180042f37  mov     [rbp+40h+var_58], 4
0x180042f3f  mov     dword ptr [rbp+40h+EventDescriptor.Id], 0B000000h
0x180042f46  movzx   eax, cs:word_180107686
0x180042f4d  mov     dword ptr [rbp+40h+EventDescriptor.Level], eax
0x180042f50  mov     [rbp+40h+EventDescriptor.Keyword], r13
0x180042f54  mov     rax, cs:off_180122078
0x180042f5b  mov     [rbp+40h+var_80.Ptr], rax
0x180042f5f  movzx   eax, word ptr [rax]
0x180042f62  mov     [rbp+40h+var_80.Size], eax
0x180042f65  mov     dword ptr [rbp+40h+var_80.0Ch], 2
0x180042f6c  lea     rax, unk_180107690
0x180042f73  mov     [rbp+40h+var_70], rax
0x180042f77  mov     [rbp+40h+var_68], 24h ; '$'
0x180042f7e  mov     [rbp+40h+var_64], 1
0x180042f85  lea     rax, _TraceLoggingMetadataEnd
0x180042f8c  sub     eax, edx
0x180042f8e  mov     [rsp+140h+var_E4], eax
0x180042f92  mov     eax, [rsp+140h+var_E4]
0x180042f96  lea     rax, [rbp+40h+var_80]
0x180042f9a  mov     [rsp+140h+UserData], rax; UserData
0x180042f9f  mov     [rsp+140h+UserDataCount], 3; int
0x180042fa7  xor     r9d, r9d; RelatedActivityId
0x180042faa  xor     r8d, r8d; ActivityId
0x180042fad  lea     rdx, [rbp+40h+EventDescriptor]; EventDescriptor
0x180042fb1  mov     rcx, cs:RegHandle; RegHandle
0x180042fb8  call    cs:__imp_EventWriteTransfer
0x180042fbe  or      ebx, 10000000h
0x180042fc4  jge     short loc_180042FE3
0x180042fc6  mov     rcx, [rbp+48h]; this
0x180042fca  mov     r9d, ebx; char *
0x180042fcd  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\ngc\\credprov\\u"...
0x180042fd4  mov     edx, 56h ; 'V'; void *
0x180042fd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042fde  jmp     loc_180042EE0
0x180042fe3  mov     [rsp+140h+var_E4], r13d
0x180042fe8  jmp     short loc_180043037
0x180042fea  movsxd  rax, dword ptr [rsp+140h+var_D8]
0x180042fef  cmp     eax, 6; switch 7 cases
0x180042ff2  ja      short def_180043005; jumptable 0000000180043005 default case, case 0
0x180042ff4  lea     rdx, __ImageBase
0x180042ffb  mov     ecx, ds:(jpt_180043005 - 180000000h)[rdx+rax*4]
0x180043002  add     rcx, rdx
0x180043005  jmp     rcx; switch jump
0x180043007  mov     ebx, 1; jumptable 0000000180043005 case 1
0x18004300c  jmp     short loc_180043026
0x18004300e  mov     ebx, 2; jumptable 0000000180043005 case 4
0x180043013  jmp     short loc_180043026
0x180043015  mov     ebx, 3; jumptable 0000000180043005 cases 2,3
0x18004301a  jmp     short loc_180043026
0x18004301c  mov     ebx, 4; jumptable 0000000180043005 cases 5,6
0x180043021  jmp     short loc_180043026
0x180043023  mov     ebx, r13d; jumptable 0000000180043005 default case, case 0
0x180043026  mov     [rsp+140h+var_E4], ebx
0x18004302a  lea     eax, [rbx-3]
0x18004302d  cmp     eax, 1
0x180043030  ja      short loc_180043037
0x180043032  mov     [rsp+140h+var_E0], r13b
0x180043037  mov     rcx, [rsp+140h+Sid]; pSid
0x18004303c  call    cs:__imp_GetLengthSid
0x180043042  mov     edi, eax
0x180043044  mov     rsi, [rsp+140h+Sid]
0x180043049  add     rdi, rsi
0x18004304c  xorps   xmm0, xmm0
0x18004304f  movdqu  xmmword ptr [rbp+40h+EventDescriptor.Id], xmm0
0x180043054  mov     [rbp+40h+var_88], r13
0x180043058  sub     rdi, rsi
0x18004305b  jz      short loc_1800430CB
0x18004305d  mov     rax, 7FFFFFFFFFFFFFFFh
0x180043067  cmp     rdi, rax
0x18004306a  ja      loc_1800446D7
0x180043070  cmp     rdi, 1000h
0x180043077  jb      short loc_1800430A5
0x180043079  lea     rcx, [rdi+27h]; Size
0x18004307d  cmp     rcx, rdi
0x180043080  jbe     loc_1800446DD
0x180043086  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004308b  mov     rcx, rax
0x18004308e  test    rax, rax
0x180043091  jz      loc_1800431C9
0x180043097  add     rax, 27h ; '''
0x18004309b  and     rax, 0FFFFFFFFFFFFFFE0h
0x18004309f  mov     [rax-8], rcx
0x1800430a3  jmp     short loc_1800430AD
0x1800430a5  mov     rcx, rdi; Size
0x1800430a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800430ad  mov     qword ptr [rbp+40h+EventDescriptor.Id], rax
0x1800430b1  lea     rbx, [rax+rdi]
0x1800430b5  mov     [rbp+40h+var_88], rbx
0x1800430b9  mov     r8, rdi; Size
0x1800430bc  mov     rdx, rsi; Src
0x1800430bf  mov     rcx, rax; void *
0x1800430c2  call    memmove_0
0x1800430c7  mov     [rbp+40h+EventDescriptor.Keyword], rbx
0x1800430cb  mov     dword ptr [rsp+140h+var_D8], r13d
0x1800430d0  lea     rdx, [rsp+140h+var_D8]
0x1800430d5  lea     rcx, [rbp+40h+EventDescriptor]
0x1800430d9  call    ?QueryLogonCredsAvailableRegState@NgcUtils@@YAJAEBV?$vector@EV?$allocator@E@std@@@std@@PEAW4LogonCredsAvailableRegState@1@@Z; NgcUtils::QueryLogonCredsAvailableRegState(std::vector<uchar> const &,NgcUtils::LogonCredsAvailableRegState *)
0x1800430de  mov     ebx, eax
0x1800430e0  test    eax, eax
0x1800430e2  jns     short loc_18004314D
0x1800430e4  mov     rcx, [rbp+48h]; this
0x1800430e8  mov     r9d, eax; char *
0x1800430eb  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\ngc\\credprov\\u"...
0x1800430f2  mov     edx, 64h ; 'd'; void *
0x1800430f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800430fc  nop
0x1800430fd  mov     rcx, qword ptr [rbp+40h+EventDescriptor.Id]; void *
0x180043101  test    rcx, rcx
0x180043104  jz      loc_180042EE0
0x18004310a  mov     rdx, [rbp+40h+var_88]
0x18004310e  sub     rdx, rcx; unsigned __int64
0x180043111  cmp     rdx, 1000h
0x180043118  jb      short loc_180043140
0x18004311a  mov     rax, [rcx-8]
0x18004311e  sub     rcx, rax
0x180043121  sub     rcx, 8
0x180043125  cmp     rcx, 1Fh
0x180043129  ja      loc_1800431C9
0x18004312f  add     rdx, 27h ; '''; unsigned __int64
0x180043133  mov     rcx, rax; void *
0x180043136  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004313b  jmp     loc_180042EE0
0x180043140  mov     rax, rcx
0x180043143  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180043148  jmp     loc_180042EE0
0x18004314d  mov     rax, qword ptr [rbp+40h+EventDescriptor.Id]
0x180043151  cmp     dword ptr [rsp+140h+var_D8], 2
0x180043156  jz      short loc_18004319D
0x180043158  test    rax, rax
0x18004315b  jz      loc_1800440D6
0x180043161  mov     rdx, [rbp+40h+var_88]
0x180043165  sub     rdx, rax; unsigned __int64
0x180043168  cmp     rdx, 1000h
0x18004316f  jb      short loc_180043190
0x180043171  mov     rcx, [rax-8]; void *
0x180043175  sub     rax, rcx
0x180043178  sub     rax, 8
0x18004317c  cmp     rax, 1Fh
0x180043180  ja      short loc_1800431C9
0x180043182  add     rdx, 27h ; '''; unsigned __int64
0x180043186  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004318b  jmp     loc_1800440D6
0x180043190  mov     rcx, rax; void *
0x180043193  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180043198  jmp     loc_1800440D6
0x18004319d  test    rax, rax
0x1800431a0  jz      short loc_1800431D8
0x1800431a2  mov     rdx, [rbp+40h+var_88]
0x1800431a6  sub     rdx, rax; unsigned __int64
0x1800431a9  cmp     rdx, 1000h
0x1800431b0  jb      short loc_1800431D0
0x1800431b2  mov     rcx, [rax-8]
0x1800431b6  sub     rax, rcx
0x1800431b9  sub     rax, 8
0x1800431bd  cmp     rax, 1Fh
0x1800431c1  ja      short loc_1800431C9
0x1800431c3  add     rdx, 27h ; '''
0x1800431c7  jmp     short loc_1800431D3
0x1800431c9  mov     ecx, 5
0x1800431ce  int     29h; Win8: RtlFailFast(ecx)
0x1800431d0  mov     rcx, rax; void *
0x1800431d3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800431d8  xorps   xmm0, xmm0
0x1800431db  movups  [rbp+40h+Buf1], xmm0
0x1800431df  lea     rdx, [rbp+40h+Buf1]; unsigned __int16 *
0x1800431e3  mov     rcx, r15; this
0x1800431e6  call    ?GetLastLoggedOnCredProviderForUser@CredProvUtils@@YAJPEBGPEAU_GUID@@@Z; CredProvUtils::GetLastLoggedOnCredProviderForUser(ushort const *,_GUID *)
0x1800431eb  mov     ebx, eax
0x1800431ed  test    eax, eax
0x1800431ef  jns     short loc_18004320E
0x1800431f1  mov     rcx, [rbp+48h]; this
0x1800431f5  mov     r9d, eax; char *
0x1800431f8  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\ngc\\credprov\\u"...
0x1800431ff  mov     edx, 6Fh ; 'o'; void *
0x180043204  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043209  jmp     loc_180042EE0
0x18004320e  mov     r8d, 10h; Size
0x180043214  lea     rdx, CLSID_NgcUtils_FidoCredentialProvider; Buf2
0x18004321b  lea     rcx, [rbp+40h+Buf1]; Buf1
0x18004321f  call    memcmp_0
0x180043224  test    eax, eax
0x180043226  jz      loc_1800440D6
0x18004322c  mov     [rsp+140h+var_E8], 0
0x180043231  mov     r8d, 10h; Size
0x180043237  lea     rdx, CLSID_NgcUtils_NgcPinProvider; Buf2
0x18004323e  lea     rcx, [rbp+40h+Buf1]; Buf1
0x180043242  call    memcmp_0
0x180043247  test    eax, eax
0x180043249  jz      short loc_1800432A1
0x18004324b  mov     r8d, 10h; Size
0x180043251  lea     rdx, CLSID_NgcUtils_DeviceNgcProvider; Buf2
0x180043258  lea     rcx, [rbp+40h+Buf1]; Buf1
0x18004325c  call    memcmp_0
0x180043261  test    eax, eax
0x180043263  jz      short loc_1800432A1
0x180043265  mov     r8d, 10h; Size
0x18004326b  lea     rdx, CLSID_NgcUtils_WinBioCredentialProvider; Buf2
0x180043272  lea     rcx, [rbp+40h+Buf1]; Buf1
0x180043276  call    memcmp_0
0x18004327b  test    eax, eax
0x18004327d  jz      short loc_1800432A1
0x18004327f  mov     r8d, 10h; Size
0x180043285  lea     rdx, CLSID_NgcUtils_FaceCredentialProvider; Buf2
0x18004328c  lea     rcx, [rbp+40h+Buf1]; Buf1
0x180043290  call    memcmp_0
0x180043295  test    eax, eax
0x180043297  jz      short loc_1800432A1
0x180043299  xor     al, al
0x18004329b  mov     [rsp+140h+var_E6], al
0x18004329f  jmp     short loc_1800432A6
0x1800432a1  mov     [rsp+140h+var_E6], 1
0x1800432a6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_K2NgcBioFirst@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_K2NgcBioFirst@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2NgcBioFirst> `wil::Feature<__WilFeatureTraits_Feature_K2NgcBioFirst>::GetImpl(void)'::`2'::impl
0x1800432ad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_K2NgcBioFirst@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2NgcBioFirst>::__private_IsEnabled(void)
0x1800432b2  test    al, al
0x1800432b4  jz      short loc_1800432F4
0x1800432b6  mov     r8d, 10h; Size
0x1800432bc  lea     rdx, CLSID_NgcUtils_WinBioCredentialProvider; Buf2
0x1800432c3  lea     rcx, [rbp+40h+Buf1]; Buf1
0x1800432c7  call    memcmp_0
0x1800432cc  test    eax, eax
0x1800432ce  jz      short loc_1800432EF
0x1800432d0  mov     r8d, 10h; Size
0x1800432d6  lea     rdx, CLSID_NgcUtils_FaceCredentialProvider; Buf2
0x1800432dd  lea     rcx, [rbp+40h+Buf1]; Buf1
0x1800432e1  call    memcmp_0
0x1800432e6  test    eax, eax
0x1800432e8  mov     [rsp+140h+var_E8], 0
0x1800432ed  jnz     short loc_1800432F4
0x1800432ef  mov     [rsp+140h+var_E8], 1
0x1800432f4  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800432fb  lea     rcx, [rsp+140h+Src]
0x180043300  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
  ... truncated ...
```
