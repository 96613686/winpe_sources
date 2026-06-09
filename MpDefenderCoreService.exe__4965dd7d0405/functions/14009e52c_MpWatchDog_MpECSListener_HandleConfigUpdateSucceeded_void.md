# MpWatchDog::MpECSListener::HandleConfigUpdateSucceeded(void)

- ea: `0x14009e52c`
- end: `0x14009f6a8`
- name: `?HandleConfigUpdateSucceeded@MpECSListener@MpWatchDog@@AEAAJXZ`
- size: `4476`
- prototype: `__int64 __fastcall(MpWatchDog::MpECSListener *__hidden this)`
- caller_count: `1`
- callee_count: `40`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400a1680`

## callees

- `0x140011a10`
- `0x1400121a8`
- `0x14001263c`
- `0x1400128e4`
- `0x1400129bc`
- `0x140012a0c`
- `0x140017990`
- `0x14003a130`
- `0x14003a5c0`
- `0x14005a0d0`
- `0x14007d1e0`
- `0x14007d210`
- `0x14007e088`
- `0x14007e3ac`
- `0x140081fc8`
- `0x1400820b4`
- `0x1400833d4`
- `0x1400848c8`
- `0x140084a18`
- `0x140084a8c`
- `0x140085d94`
- `0x140085fb0`
- `0x14008d1fc`
- `0x14008e7c0`
- `0x14008f950`
- `0x14009cbe8`
- `0x14009d014`
- `0x14009d540`
- `0x14009d7a4`
- `0x14009d97c`
- `0x14009e034`
- `0x14009e3c0`
- `0x14009e52c`
- `0x1400a1dec`
- `0x1400a2f10`
- `0x1400c334c`
- `0x1400c38c4`
- `0x140166250`
- `0x140166990`
- `0x140166d30`

## import_xrefs

- `KERNEL32!DebugBreak` at `0x14009eacb`
- `KERNEL32!DebugBreak` at `0x14009eacb`
- `KERNEL32!AcquireSRWLockShared` at `0x14009ebd0`
- `KERNEL32!AcquireSRWLockShared` at `0x14009f5b9`
- `KERNEL32!AcquireSRWLockShared` at `0x14009ebd0`
- `KERNEL32!AcquireSRWLockShared` at `0x14009f5b9`
- `KERNEL32!ReleaseSRWLockShared` at `0x14009ebdd`
- `KERNEL32!ReleaseSRWLockShared` at `0x14009f5dc`
- `KERNEL32!ReleaseSRWLockShared` at `0x14009ebdd`
- `KERNEL32!ReleaseSRWLockShared` at `0x14009f5dc`
- `ADVAPI32!RegCloseKey` at `0x14009e635`
- `ADVAPI32!RegCloseKey` at `0x14009e8c7`
- `ADVAPI32!RegCloseKey` at `0x14009e8db`
- `ADVAPI32!RegCloseKey` at `0x14009e91f`
- `ADVAPI32!RegCloseKey` at `0x14009ea4a`
- `ADVAPI32!RegCloseKey` at `0x14009ea62`
- `ADVAPI32!RegCloseKey` at `0x14009f59d`
- `ADVAPI32!RegCloseKey` at `0x14009f629`
- `ADVAPI32!RegCloseKey` at `0x14009f63d`
- `ADVAPI32!RegCloseKey` at `0x14009e635`
- `ADVAPI32!RegCloseKey` at `0x14009e8c7`
- `ADVAPI32!RegCloseKey` at `0x14009e8db`
- `ADVAPI32!RegCloseKey` at `0x14009e91f`
- `ADVAPI32!RegCloseKey` at `0x14009ea4a`
- `ADVAPI32!RegCloseKey` at `0x14009ea62`
- `ADVAPI32!RegCloseKey` at `0x14009f59d`
- `ADVAPI32!RegCloseKey` at `0x14009f629`
- `ADVAPI32!RegCloseKey` at `0x14009f63d`

## string_xrefs

- `0x14009ea81`: `MdCoreSvc_EcsAgentName`
- `0x14009eb4d`: `DCO_MpFC_EnableEcsConfigDelivery`

## pseudocode

```c
__int64 __fastcall MpWatchDog::MpECSListener::HandleConfigUpdateSucceeded(MpWatchDog::MpECSListener *this)
{
  __int64 v2; // rcx
  int v3; // eax
  const wchar_t *v4; // r8
  bool v5; // di
  MpWatchDog *v6; // rcx
  unsigned int v7; // r8d
  __int128 *v8; // r9
  __int64 *v9; // rbx
  _QWORD *v10; // rdi
  HKEY v11; // rdx
  int v12; // eax
  __int64 **v13; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v16; // r8
  _QWORD *v17; // rcx
  char *v18; // r9
  char *v19; // rdx
  __m128i si128; // xmm6
  int v21; // ebx
  __int64 v22; // rcx
  __int64 v23; // rdx
  const struct std::nothrow_t *v25; // rdx
  int ValueString; // edi
  void *v27; // rbx
  void **v28; // rdx
  void **v29; // rcx
  HKEY *MiscConfigString; // rax
  const struct std::nothrow_t *v31; // rdx
  HKEY v32; // rbx
  MpWatchDog *v33; // rcx
  CommonUtil *v34; // rcx
  unsigned int v35; // r8d
  _QWORD *v36; // r15
  __m128i v37; // xmm7
  char v38; // r12
  const char *v39; // rcx
  __int64 v40; // rcx
  char *v41; // r9
  __int64 v42; // rdx
  const char *v43; // rcx
  MpWatchDog::WdConfigManager *v44; // rdi
  RTL_SRWLOCK *v45; // rsi
  __int64 v46; // rdi
  __int64 (__fastcall *v47)(__int64, __int128 *, _QWORD *, char **); // rsi
  __int64 v48; // r8
  char v49; // di
  __int64 v50; // r12
  char **v51; // rsi
  unsigned __int8 *v52; // r13
  char *v53; // rcx
  unsigned __int8 *v54; // rdi
  __int64 v55; // rdi
  char **v56; // rsi
  __int64 v57; // r12
  char *v58; // rcx
  unsigned __int8 *k; // rcx
  __int64 v60; // rcx
  char **v61; // rax
  char **v62; // rax
  char **v63; // rax
  char **v64; // rax
  const wchar_t *v65; // rsi
  char SignatureForConfigKey; // di
  unsigned int v67; // edi
  MpWatchDog::CMpWdEcsRemediationManager *Instance; // rax
  const wchar_t *v69; // r9
  const char *v70; // rdx
  int v71; // eax
  const char *v72; // rcx
  int v73; // eax
  __int64 v74; // rdi
  __int64 (__fastcall *v75)(__int64, __int128 *, _QWORD *, __int128 *); // rsi
  __int64 v76; // r8
  char v77; // di
  __int64 v78; // rcx
  char *v79; // r9
  __int64 (__fastcall *v80)(__int64, __int128 *, _QWORD *, wchar_t **); // rsi
  __int64 v81; // r8
  char *v82; // rsi
  unsigned __int64 v83; // r12
  unsigned __int64 v84; // rdi
  _QWORD *v85; // rcx
  size_t v86; // r8
  __int64 v87; // r8
  unsigned int v88; // r9d
  int v89; // eax
  _QWORD *v90; // rdx
  char *v91; // rdx
  unsigned __int64 v92; // rax
  HKEY v93; // rdx
  int v94; // eax
  HKEY *v95; // r9
  const wchar_t *v96; // r9
  const wchar_t *SystemTimeAsUlong64; // r15
  void **v98; // r8
  int v99; // eax
  int v100; // eax
  unsigned __int64 v101; // r9
  int v102; // eax
  MpWatchDog::WdConfigManager *v103; // rdi
  RTL_SRWLOCK *v104; // rsi
  const struct std::nothrow_t *v105; // rdx
  unsigned int v106; // [rsp+20h] [rbp-4D8h]
  unsigned int v107; // [rsp+20h] [rbp-4D8h]
  unsigned int v108; // [rsp+20h] [rbp-4D8h]
  unsigned int v109; // [rsp+20h] [rbp-4D8h]
  void *v111; // [rsp+40h] [rbp-4B8h] BYREF
  __int128 v112; // [rsp+48h] [rbp-4B0h] BYREF
  __int128 v113; // [rsp+58h] [rbp-4A0h]
  MpWatchDog::MpECSListener *v114; // [rsp+68h] [rbp-490h]
  char v115; // [rsp+70h] [rbp-488h]
  HKEY v116; // [rsp+88h] [rbp-470h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-468h] BYREF
  HKEY v118; // [rsp+98h] [rbp-460h] BYREF
  char *v119[2]; // [rsp+A0h] [rbp-458h] BYREF
  __int64 v120; // [rsp+B0h] [rbp-448h]
  unsigned __int64 v121; // [rsp+B8h] [rbp-440h]
  wchar_t *v122; // [rsp+C0h] [rbp-438h] BYREF
  HKEY v123; // [rsp+C8h] [rbp-430h] BYREF
  void *Buf2; // [rsp+D0h] [rbp-428h] BYREF
  void *Buf1[2]; // [rsp+D8h] [rbp-420h] BYREF
  __m128i v126; // [rsp+E8h] [rbp-410h]
  __int128 v127; // [rsp+F8h] [rbp-400h] BYREF
  __m128i v128; // [rsp+108h] [rbp-3F0h]
  __int128 v129; // [rsp+118h] [rbp-3E0h] BYREF
  __int128 v130; // [rsp+128h] [rbp-3D0h] BYREF
  __int64 v131; // [rsp+138h] [rbp-3C0h]
  HKEY v132[2]; // [rsp+140h] [rbp-3B8h] BYREF
  __int128 v133; // [rsp+150h] [rbp-3A8h]
  _QWORD v134[3]; // [rsp+160h] [rbp-398h] BYREF
  unsigned __int64 v135; // [rsp+178h] [rbp-380h]
  wchar_t *v136[2]; // [rsp+180h] [rbp-378h] BYREF
  __m128i v137; // [rsp+190h] [rbp-368h]
  wchar_t *v138[2]; // [rsp+1A0h] [rbp-358h] BYREF
  __m128i v139; // [rsp+1B0h] [rbp-348h]
  _BYTE v140[256]; // [rsp+1C0h] [rbp-338h] BYREF
  _BYTE v141[56]; // [rsp+2C0h] [rbp-238h] BYREF
  const wchar_t *v142; // [rsp+2F8h] [rbp-200h]
  char v143[416]; // [rsp+300h] [rbp-1F8h] BYREF

  v116 = (HKEY)this;
  v114 = this;
  v130 = 0;
  v131 = 0;
  MpWatchDog::MpECSListener::GetNewConfigKeysSorted(this, &v130);
  MpWatchDog::MpECSListener::SendDebugNotification(this, 0);
  v129 = 0;
  MpWatchDog::MpECSListener::GetUnusedKeys(v2, &v129, &v130);
  hKey = 0;
  v3 = CommonUtil::UtilRegOpenKey(
         (CommonUtil *)&hKey,
         (HKEY *)0xFFFFFFFF80000002LL,
         (HKEY)&stru_140197750,
         (const wchar_t *)3,
         v106);
  if ( v3 >= 0 )
  {
    v9 = *(__int64 **)v129;
    while ( !*((_BYTE *)v9 + 25) )
    {
      v10 = v9 + 4;
      v11 = (HKEY)(v9 + 4);
      if ( (unsigned __int64)v9[7] > 7 )
        v11 = (HKEY)*v10;
      v12 = CommonUtil::UtilRegDeleteValue((CommonUtil *)hKey, v11, v4);
      if ( v12 < 0
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        if ( (unsigned __int64)v9[7] > 7 )
          v10 = (_QWORD *)*v10;
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          65,
          (unsigned int)&WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids,
          (_DWORD)v10,
          v12);
      }
      v13 = (__int64 **)v9[2];
      if ( *((_BYTE *)v13 + 25) )
      {
        for ( i = (__int64 *)v9[1]; !*((_BYTE *)i + 25) && v9 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v9 = i;
        v9 = i;
      }
      else
      {
        v9 = (__int64 *)v9[2];
        for ( j = *v13; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v9 = j;
      }
    }
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      64,
      &WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids,
      (unsigned int)v3);
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v129);
  v5 = 0;
  if ( MpWatchDog::MpIsCoreSvcInDevMode(v6) )
  {
    v5 = MpWatchDog::GetMiscConfigDword((HKEY)&stru_140197700, 0, v7) == 1;
    (*(void (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 22) + 96LL))(*((_QWORD *)this + 22), &v127);
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      v8 = &v127;
      if ( v128.m128i_i64[1] > 0xFuLL )
        v8 = (__int128 *)v127;
      WPP_SF_s(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 41, &WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids, v8);
    }
    std::string::_Tidy_deallocate(&v127);
  }
  (*(void (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 22) + 88LL))(*((_QWORD *)this + 22), v134);
  v17 = v134;
  if ( v135 > 0xF )
    v17 = (_QWORD *)v134[0];
  v18 = (char *)v17 + v134[2];
  v19 = (char *)v134;
  if ( v135 > 0xF )
    v19 = (char *)v134[0];
  *(_OWORD *)Buf1 = 0;
  v126 = 0;
  if ( v19 == v18 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v126 = si128;
    LOWORD(Buf1[0]) = 0;
  }
  else
  {
    std::wstring::_Construct_from_iter<char const *,char const *,unsigned __int64>(Buf1, v19, v16, v18 - v19);
    si128 = _mm_load_si128((const __m128i *)&_xmm);
  }
  v123 = 0;
  v118 = 0;
  v21 = CommonUtil::UtilRegOpenKey(
          (CommonUtil *)&v123,
          (HKEY *)0xFFFFFFFF80000002LL,
          (HKEY)&stru_140197750,
          (const wchar_t *)3,
          v107);
  if ( v21 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_45;
    v23 = 42;
LABEL_44:
    WPP_SF_d(*(_QWORD *)(v22 + 16), v23, &WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids, (unsigned int)v21);
LABEL_45:
    if ( v118 )
      RegCloseKey(v118);
    if ( v123 )
      RegCloseKey(v123);
    std::wstring::_Tidy_deallocate(Buf1);
    std::string::_Tidy_deallocate(v134);
    std::vector<CsProtocol::M365a>::_Tidy(&v130);
    return (unsigned int)v21;
  }
  if ( v118 )
  {
    RegCloseKey(v118);
    v118 = 0;
  }
  v21 = CommonUtil::UtilRegOpenKey(
          (CommonUtil *)&v118,
          (HKEY *)0xFFFFFFFF80000002LL,
          (HKEY)&stru_140196700,
          (const wchar_t *)3,
          v108);
  if ( v21 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_45;
    v23 = 43;
    goto LABEL_44;
  }
  if ( !v5 )
  {
    Buf2 = 0;
    ValueString = CommonUtil::UtilRegGetValueString(v118, &stru_140196780, &Buf2, 0, 0);
    v27 = Buf2;
    if ( ValueString >= 0 )
    {
      v28 = Buf1;
      if ( v126.m128i_i64[1] > 7uLL )
        v28 = (void **)Buf1[0];
      v29 = Buf1;
      if ( v126.m128i_i64[1] > 7uLL )
        v29 = (void **)Buf1[0];
      if ( !memcmp(v29, Buf2, (char *)v28 + 2 * v126.m128i_i64[0] - (char *)v29) )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        {
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 44, &WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids);
          v27 = Buf2;
        }
        if ( v27 )
          operator delete(v27, v25);
        if ( v118 )
          RegCloseKey(v118);
        if ( v123 )
          RegCloseKey(v123);
        goto LABEL_228;
      }
    }
    if ( v27 )
      operator delete(v27, v25);
  }
  MiscConfigString = (HKEY *)MpWatchDog::GetMiscConfigString(
                               &v111,
                               L"MdCoreSvc_EcsAgentName",
                               "MicrosoftDefenderForWindowsClient");
  v32 = *MiscConfigString;
  *MiscConfigString = 0;
  hKey = v32;
  v33 = (MpWatchDog *)v111;
  if ( v111 )
    operator delete(v111, v31);
  if ( MpWatchDog::MpIsCoreSvcInDevMode(v33) && MpWatchDog::GetMiscConfigDword((HKEY)&stru_140197820, 0, v35) == 1 )
    DebugBreak();
  *(_QWORD *)&v129 = *((_QWORD *)&v130 + 1);
  v36 = (_QWORD *)v130;
  v37 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    v111 = v36;
    if ( v36 == (_QWORD *)v129 )
      break;
    LODWORD(v122) = 0;
    *(_OWORD *)v119 = 0;
    v120 = 0;
    v121 = 15;
    LOBYTE(v119[0]) = 0;
    v38 = 0;
    v39 = (const char *)v36;
    if ( v36[3] > 0xFu )
      v39 = (const char *)*v36;
    if ( !stricmp(v39, "DCO_MpFC_EnableEcsConfigDelivery") )
    {
      v40 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        v41 = (char *)v36;
        if ( v36[3] > 0xFu )
          v41 = (char *)*v36;
        v42 = 45;
        goto LABEL_89;
      }
      goto LABEL_203;
    }
    v43 = (const char *)v36;
    if ( v36[3] > 0xFu )
      v43 = (const char *)*v36;
    if ( !stricmp(v43, "MdCoreSvcRemediationPayload") )
    {
      v44 = MpWatchDog::gMpWdConfigManager;
      v45 = (RTL_SRWLOCK *)((char *)MpWatchDog::gMpWdConfigManager + 848);
      AcquireSRWLockShared((PSRWLOCK)MpWatchDog::gMpWdConfigManager + 106);
      LOBYTE(v44) = *((_BYTE *)v44 + 28);
      ReleaseSRWLockShared(v45);
      if ( !(_BYTE)v44 )
        goto LABEL_203;
      v46 = *((_QWORD *)this + 22);
      v47 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD *, char **))(*(_QWORD *)v46 + 152LL);
      v127 = 0;
      v128 = 0;
      v48 = -1;
      do
        ++v48;
      while ( *((_BYTE *)v32 + v48) );
      std::string::_Construct<1,char const *>(&v127, v32);
      v49 = v47(v46, &v127, v36, v119);
      std::string::_Tidy_deallocate(&v127);
      if ( v49 )
      {
        v50 = v120;
        if ( v120 )
        {
          v51 = v119;
          if ( v121 > 0xF )
            v51 = (char **)v119[0];
          v52 = (unsigned __int8 *)v51 + v120;
          memset(v140, 0, sizeof(v140));
          v53 = " \t\n\r";
          do
            v140[(unsigned __int8)*v53++] = 1;
          while ( v53 != "" );
          v54 = (unsigned __int8 *)v51;
          if ( v51 >= (char **)v52 )
          {
LABEL_105:
            v55 = -1;
          }
          else
          {
            while ( v140[*v54] )
            {
              if ( ++v54 >= v52 )
                goto LABEL_105;
            }
            v55 = v54 - (unsigned __int8 *)v51;
          }
          v56 = v119;
          if ( v121 > 0xF )
            v56 = (char **)v119[0];
          v57 = v50 - 1;
          if ( v57 == -1 )
            v57 = -1;
          memset(v140, 0, sizeof(v140));
          v58 = " \t\n\r";
          do
            v140[(unsigned __int8)*v58++] = 1;
          while ( v58 != "" );
          for ( k = (unsigned __int8 *)v56 + v57; ; --k )
          {
            if ( !v140[*k] )
            {
              v60 = k - (unsigned __int8 *)v56;
              goto LABEL_118;
            }
            if ( k == (unsigned __int8 *)v56 )
              break;
          }
          v60 = -1;
LABEL_118:
          if ( v55 != -1 && v60 != -1 )
          {
            v61 = v119;
            if ( v121 > 0xF )
              v61 = (char **)v119[0];
            if ( *((_BYTE *)v61 + v55) == 123 )
            {
              v62 = v119;
              if ( v121 > 0xF )
                v62 = (char **)v119[0];
              if ( *((_BYTE *)v62 + v60) == 125 )
                goto LABEL_132;
            }
            v63 = v119;
            if ( v121 > 0xF )
              v63 = (char **)v119[0];
            if ( *((_BYTE *)v63 + v55) == 91 )
            {
              v64 = v119;
              if ( v121 > 0xF )
                v64 = (char **)v119[0];
              if ( *((_BYTE *)v64 + v60) == 93 )
              {
LABEL_132:
                v65 = 0;
                *(_OWORD *)v138 = 0;
                v139 = si128;
                LOWORD(v138[0]) = 0;
                *(_OWORD *)v136 = 0;
                v137 = si128;
                LOWORD(v136[0]) = 0;
                if ( (unsigned __int8)MpWatchDog::WdConfigManager::IsKillbitGatedFeatureEnabled(
                                        MpWatchDog::gMpWdConfigManager,
                                        224) )
                {
                  v112 = 0;
                  v113 = 0;
                  std::wstring::_Construct<1,wchar_t const *>(&v112, L"MdCoreSvcRemediationPayload", 27);
                  SignatureForConfigKey = MpWatchDog::MpECSListener::GetSignatureForConfigKey(this, v32, &v112, v138);
                  std::wstring::_Tidy_deallocate(&v112);
                  if ( SignatureForConfigKey )
                  {
                    v65 = (const wchar_t *)v138;
                    if ( v139.m128i_i64[1] > 7uLL )
                      v65 = v138[0];
                    v112 = 0;
                    v113 = 0;
                    std::wstring::_Construct<1,wchar_t const *>(&v112, L"__Thumbprint__", 14);
                    v67 = (unsigned __int8)MpWatchDog::MpECSListener::GetSignatureForConfigKey(this, v32, &v112, v136);
                    std::wstring::_Tidy_deallocate(&v112);
                    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
                    {
                      WPP_SF_d(
                        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                        46,
                        &WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids,
                        v67);
                    }
                  }
                }
                Instance = MpWatchDog::CMpWdEcsRemediationManager::GetInstance();
                v69 = (const wchar_t *)v136;
                if ( v137.m128i_i64[1] > 7uLL )
                  v69 = v136[0];
                v70 = (const char *)v119;
                if ( v121 > 0xF )
                  v70 = v119[0];
                v71 = MpWatchDog::CMpWdEcsRemediationManager::HandleRemediationPayload(Instance, v70, v65, v69, 1);
                if ( v71 >= 0 )
                {
                  std::wstring::_Tidy_deallocate(v136);
                  std::wstring::_Tidy_deallocate(v138);
                  std::string::_Tidy_deallocate(v119);
                  goto LABEL_204;
                }
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
                {
                  WPP_SF_d(
                    *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                    47,
                    &WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids,
                    (unsigned int)v71);
                }
                std::wstring::_Tidy_deallocate(v136);
                std::wstring::_Tidy_deallocate(v138);
              }
            }
          }
        }
        v38 = 0;
      }
      goto LABEL_167;
    }
    v72 = (const char *)v36;
    if ( v36[3] > 0xFu )
      v72 = (const char *)*v36;
    v73 = stricmp(v72, "DCO_Md1dsExcludedList");
    v74 = *((_QWORD *)v114 + 22);
    if ( v73 )
    {
      v80 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD *, wchar_t **))(*(_QWORD *)v74 + 128LL);
      v112 = 0;
      v113 = 0;
      v81 = -1;
      do
        ++v81;
      while ( *((_BYTE *)v32 + v81) );
      std::string::_Construct<1,char const *>(&v112, v32);
      v38 = v80(v74, &v112, v36, &v122);
      std::string::_Tidy_deallocate(&v112);
LABEL_167:
      if ( v38 )
      {
        v82 = (char *)v36;
        if ( v36[3] > 0xFu )
          v82 = (char *)*v36;
        v83 = v36[2];
        v84 = 4;
        if ( v83 < 4 )
          v84 = v36[2];
        v85 = v36;
        if ( v36[3] > 0xFu )
          v85 = (_QWORD *)*v36;
        v86 = v84;
        if ( v84 > 4 )
          v86 = 4;
        if ( memcmp(v85, "DCO_", v86) || (v84 >= 4 ? (v89 = v84 > 4) : (v89 = -1), v89) )
        {
          v91 = (char *)v36;
          if ( v36[3] > 0xFu )
            v91 = (char *)*v36;
        }
        else
        {
          v90 = v36;
          if ( v36[3] > 0xFu )
            v90 = (_QWORD *)*v36;
          v91 = (char *)v90 + 4;
        }
        *(_OWORD *)v132 = 0;
        v133 = 0;
        if ( v91 == &v82[v83] )
        {
          v92 = 7;
          *((_QWORD *)&v133 + 1) = 7;
          LOWORD(v132[0]) = 0;
        }
        else
        {
          std::wstring::_Construct_from_iter<char const *,char const *,unsigned __int64>(
            v132,
            v91,
            v87,
            v83 + v82 - v91);
          v92 = *((_QWORD *)&v133 + 1);
        }
        v93 = (HKEY)v132;
        if ( v92 > 7 )
          v93 = v132[0];
        v94 = CommonUtil::UtilRegSetValueDword((CommonUtil *)v123, v93, (const wchar_t *)(unsigned int)v122, v88);
        if ( v94 < 0
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v95 = v132;
          if ( *((_QWORD *)&v133 + 1) > 7u )
            LODWORD(v95) = v132[0];
          WPP_SF_Sd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            52,
            (unsigned int)&WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids,
            (_DWORD)v95,
            v94);
        }
        std::wstring::_Tidy_deallocate(v132);
      }
      else
      {
        v40 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          v41 = (char *)v36;
          if ( v36[3] > 0xFu )
            v41 = (char *)*v36;
          v42 = 51;
LABEL_89:
          WPP_SF_s(*(_QWORD *)(v40 + 16), v42, &WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids, v41);
        }
      }
LABEL_203:
      std::string::_Tidy_deallocate(v119);
      goto LABEL_204;
    }
    v127 = 0;
    v128 = v37;
    LOBYTE(v127) = 0;
    v75 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD *, __int128 *))(*(_QWORD *)v74 + 112LL);
    v112 = 0;
    v113 = 0;
    v76 = -1;
    do
      ++v76;
    while ( *((_BYTE *)v32 + v76) );
    std::string::_Construct<1,char const *>(&v112, v32);
    v77 = v75(v74, &v112, v36, &v127);
    std::string::_Tidy_deallocate(&v112);
    if ( v77 )
    {
      MpWatchDog::MpECSListener::Handle1dsExcludedListConfig(v78, &v127);
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v79 = (char *)v36;
      if ( v36[3] > 0xFu )
        v79 = (char *)*v36;
      WPP_SF_s(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 48, &WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids, v79);
    }
    std::string::_Tidy_deallocate(&v127);
    std::string::_Tidy_deallocate(v119);
LABEL_204:
    v36 += 4;
  }
  SystemTimeAsUlong64 = (const wchar_t *)CommonUtil::UtilGetSystemTimeAsUlong64(v34);
  v98 = Buf1;
  if ( v126.m128i_i64[1] > 7uLL )
    v98 = (void **)Buf1[0];
  v99 = CommonUtil::UtilRegSetValueString((CommonUtil *)v118, (HKEY)&stru_140196780, (const wchar_t *)v98, v96);
  if ( v99 >= 0 )
  {
    v116 = 0;
    v100 = CommonUtil::UtilRegOpenKey(
             (CommonUtil *)&v116,
             (HKEY *)0xFFFFFFFF80000002LL,
             (HKEY)&stru_1401976A0,
             (const wchar_t *)2,
             v109);
    if ( v100 >= 0 )
    {
      v102 = CommonUtil::UtilRegSetValueULongLongToBinary(
               (CommonUtil *)v116,
               (HKEY)&stru_140196788,
               SystemTimeAsUlong64,
               v101);
      if ( v102 < 0
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          55,
          &WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids,
          (unsigned int)v102);
      }
    }
    else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_Sd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        54,
        (unsigned int)&WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids,
        (unsigned int)&stru_1401976A0,
        v100);
    }
    if ( v116 )
      RegCloseKey(v116);
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      53,
      &WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids,
      (unsigned int)v99);
  }
  v103 = MpWatchDog::gMpWdConfigManager;
  v104 = (RTL_SRWLOCK *)((char *)MpWatchDog::gMpWdConfigManager + 848);
  v114 = (MpWatchDog::WdConfigManager *)((char *)MpWatchDog::gMpWdConfigManager + 848);
  AcquireSRWLockShared((PSRWLOCK)MpWatchDog::gMpWdConfigManager + 106);
  v115 = 1;
  MpWatchDog::DefenderCampConfigs::DefenderCampConfigs(
    (MpWatchDog::DefenderCampConfigs *)v141,
    (MpWatchDog::WdConfigManager *)((char *)v103 + 192));
  ReleaseSRWLockShared(v104);
  std::wstring::operator=(v143);
  v142 = SystemTimeAsUlong64;
  MpWatchDog::DefenderCampConfigs::~DefenderCampConfigs((MpWatchDog::DefenderCampConfigs *)v141);
  if ( v32 )
    operator delete(v32, v105);
  if ( v118 )
    RegCloseKey(v118);
  if ( v123 )
    RegCloseKey(v123);
  ValueString = 0;
LABEL_228:
  std::wstring::_Tidy_deallocate(Buf1);
  std::string::_Tidy_deallocate(v134);
  std::vector<CsProtocol::M365a>::_Tidy(&v130);
  return (unsigned int)ValueString;
}

```

## disassembly

```asm
0x14009e52c  mov     rax, rsp
0x14009e52f  mov     [rax+10h], rbx
0x14009e533  mov     [rax+18h], rsi
0x14009e537  push    rdi
0x14009e538  push    r12
0x14009e53a  push    r13
0x14009e53c  push    r14
0x14009e53e  push    r15
0x14009e540  sub     rsp, 4D0h
0x14009e547  movaps  xmmword ptr [rax-38h], xmm6
0x14009e54b  movaps  xmmword ptr [rax-48h], xmm7
0x14009e54f  mov     rax, cs:__security_cookie
0x14009e556  xor     rax, rsp
0x14009e559  mov     [rsp+4F8h+var_58], rax
0x14009e561  mov     r12, rcx
0x14009e564  mov     [rsp+4F8h+var_4C0], rcx
0x14009e569  mov     [rsp+4F8h+var_470], rcx
0x14009e571  mov     [rsp+4F8h+var_490], rcx
0x14009e576  xor     r14d, r14d
0x14009e579  xorps   xmm0, xmm0
0x14009e57c  xor     eax, eax
0x14009e57e  movups  [rsp+4F8h+var_3D0], xmm0
0x14009e586  mov     [rsp+4F8h+var_3C0], rax
0x14009e58e  lea     rdx, [rsp+4F8h+var_3D0]
0x14009e596  call    ?GetNewConfigKeysSorted@MpECSListener@MpWatchDog@@AEAA?AV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@XZ; MpWatchDog::MpECSListener::GetNewConfigKeysSorted(void)
0x14009e59b  nop
0x14009e59c  xor     edx, edx
0x14009e59e  mov     rcx, r12
0x14009e5a1  call    ?SendDebugNotification@MpECSListener@MpWatchDog@@QEAAXW4eDebugNotificationType@12@PEAX@Z; MpWatchDog::MpECSListener::SendDebugNotification(MpWatchDog::MpECSListener::eDebugNotificationType,void *)
0x14009e5a6  xorps   xmm0, xmm0
0x14009e5a9  movups  [rsp+4F8h+var_3E0], xmm0
0x14009e5b1  lea     r8, [rsp+4F8h+var_3D0]
0x14009e5b9  lea     rdx, [rsp+4F8h+var_3E0]
0x14009e5c1  call    ?GetUnusedKeys@MpECSListener@MpWatchDog@@AEAA?AV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@4@@Z; MpWatchDog::MpECSListener::GetUnusedKeys(std::vector<std::string> const &)
0x14009e5c6  mov     [rsp+4F8h+hKey], r14
0x14009e5ce  lea     r15d, [r14+3]
0x14009e5d2  mov     r9d, r15d; wchar_t *
0x14009e5d5  lea     r8, stru_140197750; HKEY
0x14009e5dc  mov     rdx, 0FFFFFFFF80000002h; HKEY *
0x14009e5e3  lea     rcx, [rsp+4F8h+hKey]; this
0x14009e5eb  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)
0x14009e5f0  test    eax, eax
0x14009e5f2  jns     loc_14009E6E0
0x14009e5f8  lea     r13, WPP_GLOBAL_Control
0x14009e5ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14009e606  cmp     rcx, r13
0x14009e609  jz      short loc_14009E628
0x14009e60b  test    byte ptr [rcx+1Ch], 2
0x14009e60f  jz      short loc_14009E628
0x14009e611  lea     edx, [r14+40h]
0x14009e615  mov     r9d, eax
0x14009e618  lea     r8, WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids
0x14009e61f  mov     rcx, [rcx+10h]
0x14009e623  call    WPP_SF_d
0x14009e628  mov     rcx, [rsp+4F8h+hKey]; hKey
0x14009e630  test    rcx, rcx
0x14009e633  jz      short loc_14009E63B
0x14009e635  call    cs:__imp_RegCloseKey
0x14009e63b  lea     rcx, [rsp+4F8h+var_3E0]
0x14009e643  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x14009e648  mov     dil, r14b
0x14009e64b  call    ?MpIsCoreSvcInDevMode@MpWatchDog@@YA_NXZ; MpWatchDog::MpIsCoreSvcInDevMode(void)
0x14009e650  test    al, al
0x14009e652  jz      loc_14009E7A5
0x14009e658  xor     edx, edx; wchar_t *
0x14009e65a  lea     rcx, stru_140197700; this
0x14009e661  call    ?GetMiscConfigDword@MpWatchDog@@YAKPEB_WK@Z; MpWatchDog::GetMiscConfigDword(wchar_t const *,ulong)
0x14009e666  cmp     eax, 1
0x14009e669  setz    dil
0x14009e66d  mov     rcx, [r12+0B0h]
0x14009e675  mov     rax, [rcx]
0x14009e678  lea     rdx, [rsp+4F8h+var_400]
0x14009e680  mov     rax, [rax+60h]
0x14009e684  call    cs:__guard_dispatch_icall_fptr
0x14009e68a  mov     rcx, cs:WPP_GLOBAL_Control
0x14009e691  mov     esi, 4
0x14009e696  cmp     rcx, r13
0x14009e699  jz      short loc_14009E6CE
0x14009e69b  test    [rcx+1Ch], sil
0x14009e69f  jz      short loc_14009E6CE
0x14009e6a1  lea     r9, [rsp+4F8h+var_400]
0x14009e6a9  cmp     [rsp+4F8h+var_3E8], 0Fh
0x14009e6b2  cmova   r9, qword ptr [rsp+4F8h+var_400]
0x14009e6bb  lea     edx, [rsi+25h]
0x14009e6be  lea     r8, WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids
0x14009e6c5  mov     rcx, [rcx+10h]
0x14009e6c9  call    WPP_SF_s
0x14009e6ce  lea     rcx, [rsp+4F8h+var_400]
0x14009e6d6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14009e6db  jmp     loc_14009E7AA
0x14009e6e0  mov     rbx, qword ptr [rsp+4F8h+var_3E0]
0x14009e6e8  mov     rbx, [rbx]
0x14009e6eb  lea     r13, WPP_GLOBAL_Control
0x14009e6f2  cmp     [rbx+19h], r14b
0x14009e6f6  jnz     loc_14009E628
0x14009e6fc  lea     rdi, [rbx+20h]
0x14009e700  mov     rdx, rdi
0x14009e703  cmp     qword ptr [rbx+38h], 7
0x14009e708  jbe     short loc_14009E70D
0x14009e70a  mov     rdx, [rdi]; HKEY
0x14009e70d  mov     rcx, [rsp+4F8h+hKey]; this
0x14009e715  call    ?UtilRegDeleteValue@CommonUtil@@YAJPEAUHKEY__@@PEB_W@Z; CommonUtil::UtilRegDeleteValue(HKEY__ *,wchar_t const *)
0x14009e71a  test    eax, eax
0x14009e71c  jns     short loc_14009E756
0x14009e71e  mov     rcx, cs:WPP_GLOBAL_Control
0x14009e725  cmp     rcx, r13
0x14009e728  jz      short loc_14009E756
0x14009e72a  test    byte ptr [rcx+1Ch], 2
0x14009e72e  jz      short loc_14009E756
0x14009e730  cmp     qword ptr [rdi+18h], 7
0x14009e735  jbe     short loc_14009E73A
0x14009e737  mov     rdi, [rdi]
0x14009e73a  mov     edx, 41h ; 'A'
0x14009e73f  mov     [rsp+4F8h+var_4D8], eax
0x14009e743  mov     r9, rdi
0x14009e746  lea     r8, WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids
0x14009e74d  mov     rcx, [rcx+10h]
0x14009e751  call    WPP_SF_Sd
0x14009e756  mov     rcx, [rbx+10h]
0x14009e75a  cmp     [rcx+19h], r14b
0x14009e75e  jz      short loc_14009E781
0x14009e760  mov     rax, [rbx+8]
0x14009e764  jmp     short loc_14009E773
0x14009e766  cmp     rbx, [rax+10h]
0x14009e76a  jnz     short loc_14009E779
0x14009e76c  mov     rbx, rax
0x14009e76f  mov     rax, [rax+8]
0x14009e773  cmp     [rax+19h], r14b
0x14009e777  jz      short loc_14009E766
0x14009e779  mov     rbx, rax
0x14009e77c  jmp     loc_14009E6F2
0x14009e781  mov     rbx, rcx
0x14009e784  mov     rcx, [rcx]
0x14009e787  cmp     [rcx+19h], r14b
0x14009e78b  jnz     loc_14009E6F2
0x14009e791  mov     rbx, rcx
0x14009e794  mov     rax, [rcx]
0x14009e797  mov     rcx, rax
0x14009e79a  cmp     [rax+19h], r14b
0x14009e79e  jz      short loc_14009E791
0x14009e7a0  jmp     loc_14009E6F2
0x14009e7a5  mov     esi, 4
0x14009e7aa  mov     rcx, [r12+0B0h]
0x14009e7b2  mov     rax, [rcx]
0x14009e7b5  lea     rdx, [rsp+4F8h+var_398]
0x14009e7bd  mov     rax, [rax+58h]
0x14009e7c1  call    cs:__guard_dispatch_icall_fptr
0x14009e7c7  nop
0x14009e7c8  lea     rcx, [rsp+4F8h+var_398]
0x14009e7d0  cmp     [rsp+4F8h+var_380], 0Fh
0x14009e7d9  cmova   rcx, [rsp+4F8h+var_398]
0x14009e7e2  mov     r9, [rsp+4F8h+var_388]
0x14009e7ea  add     r9, rcx
0x14009e7ed  lea     rdx, [rsp+4F8h+var_398]
0x14009e7f5  cmp     [rsp+4F8h+var_380], 0Fh
0x14009e7fe  cmova   rdx, [rsp+4F8h+var_398]
0x14009e807  xorps   xmm0, xmm0
0x14009e80a  movups  xmmword ptr [rsp+4F8h+Buf1], xmm0
0x14009e812  xorps   xmm1, xmm1
0x14009e815  movdqu  [rsp+4F8h+var_410], xmm1
0x14009e81e  cmp     rdx, r9
0x14009e821  jnz     short loc_14009E83F
0x14009e823  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14009e82b  movdqu  [rsp+4F8h+var_410], xmm6
0x14009e834  mov     word ptr [rsp+4F8h+Buf1], r14w
0x14009e83d  jmp     short loc_14009E857
0x14009e83f  sub     r9, rdx
0x14009e842  lea     rcx, [rsp+4F8h+Buf1]
0x14009e84a  call    ??$_Construct_from_iter@PEBDPEBD_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXPEBDQEBD_K@Z; std::wstring::_Construct_from_iter<char const *,char const *,unsigned __int64>(char const *,char const * const,unsigned __int64)
0x14009e84f  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14009e857  mov     [rsp+4F8h+var_430], r14
0x14009e85f  mov     [rsp+4F8h+var_460], r14
0x14009e867  mov     r9d, r15d; wchar_t *
0x14009e86a  lea     r8, stru_140197750; HKEY
0x14009e871  mov     rdx, 0FFFFFFFF80000002h; HKEY *
0x14009e878  lea     rcx, [rsp+4F8h+var_430]; this
0x14009e880  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)
0x14009e885  mov     ebx, eax
0x14009e887  test    eax, eax
0x14009e889  jns     loc_14009E912
0x14009e88f  mov     rcx, cs:WPP_GLOBAL_Control
0x14009e896  cmp     rcx, r13
0x14009e899  jz      short loc_14009E8BA
0x14009e89b  test    byte ptr [rcx+1Ch], 1
0x14009e89f  jz      short loc_14009E8BA
0x14009e8a1  mov     edx, 2Ah ; '*'
0x14009e8a6  mov     r9d, ebx
0x14009e8a9  lea     r8, WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids
0x14009e8b0  mov     rcx, [rcx+10h]
0x14009e8b4  call    WPP_SF_d
0x14009e8b9  nop
0x14009e8ba  mov     rcx, [rsp+4F8h+var_460]; hKey
0x14009e8c2  test    rcx, rcx
0x14009e8c5  jz      short loc_14009E8CE
0x14009e8c7  call    cs:__imp_RegCloseKey
0x14009e8cd  nop
0x14009e8ce  mov     rcx, [rsp+4F8h+var_430]; hKey
0x14009e8d6  test    rcx, rcx
0x14009e8d9  jz      short loc_14009E8E2
0x14009e8db  call    cs:__imp_RegCloseKey
0x14009e8e1  nop
0x14009e8e2  lea     rcx, [rsp+4F8h+Buf1]
0x14009e8ea  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14009e8ef  nop
0x14009e8f0  lea     rcx, [rsp+4F8h+var_398]
0x14009e8f8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14009e8fd  nop
0x14009e8fe  lea     rcx, [rsp+4F8h+var_3D0]
0x14009e906  call    ?_Tidy@?$vector@UM365a@CsProtocol@@V?$allocator@UM365a@CsProtocol@@@std@@@std@@AEAAXXZ; std::vector<CsProtocol::M365a>::_Tidy(void)
0x14009e90b  mov     eax, ebx
0x14009e90d  jmp     loc_14009F671
0x14009e912  mov     rcx, [rsp+4F8h+var_460]; hKey
0x14009e91a  test    rcx, rcx
0x14009e91d  jz      short loc_14009E92D
0x14009e91f  call    cs:__imp_RegCloseKey
0x14009e925  mov     [rsp+4F8h+var_460], r14
0x14009e92d  mov     r9d, r15d; wchar_t *
0x14009e930  lea     r8, stru_140196700; HKEY
0x14009e937  mov     rdx, 0FFFFFFFF80000002h; HKEY *
0x14009e93e  lea     rcx, [rsp+4F8h+var_460]; this
0x14009e946  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)
0x14009e94b  mov     ebx, eax
0x14009e94d  test    eax, eax
0x14009e94f  jns     short loc_14009E975
0x14009e951  mov     rcx, cs:WPP_GLOBAL_Control
0x14009e958  cmp     rcx, r13
0x14009e95b  jz      loc_14009E8BA
0x14009e961  test    byte ptr [rcx+1Ch], 1
0x14009e965  jz      loc_14009E8BA
0x14009e96b  mov     edx, 2Bh ; '+'
0x14009e970  jmp     loc_14009E8A6
0x14009e975  test    dil, dil
0x14009e978  jnz     loc_14009EA7A
0x14009e97e  mov     [rsp+4F8h+Buf2], r14
0x14009e986  mov     qword ptr [rsp+4F8h+var_4D8], r14; unsigned int
0x14009e98b  xor     r9d, r9d
0x14009e98e  lea     r8, [rsp+4F8h+Buf2]
0x14009e996  lea     rdx, stru_140196780
0x14009e99d  mov     rcx, [rsp+4F8h+var_460]
0x14009e9a5  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAPEA_WW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,wchar_t const *,wchar_t * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x14009e9aa  mov     edi, eax
0x14009e9ac  mov     rbx, [rsp+4F8h+Buf2]
0x14009e9b4  test    eax, eax
0x14009e9b6  js      loc_14009EA6D
0x14009e9bc  lea     rdx, [rsp+4F8h+Buf1]
0x14009e9c4  cmp     qword ptr [rsp+4F8h+var_410+8], 7
0x14009e9cd  cmova   rdx, [rsp+4F8h+Buf1]
0x14009e9d6  mov     rcx, qword ptr [rsp+4F8h+var_410]
0x14009e9de  lea     r8, [rdx+rcx*2]
0x14009e9e2  lea     rcx, [rsp+4F8h+Buf1]
0x14009e9ea  cmova   rcx, [rsp+4F8h+Buf1]; Buf1
0x14009e9f3  sub     r8, rcx; Size
0x14009e9f6  mov     rdx, rbx; Buf2
0x14009e9f9  call    memcmp
0x14009e9fe  test    eax, eax
0x14009ea00  jnz     short loc_14009EA6D
0x14009ea02  mov     rcx, cs:WPP_GLOBAL_Control
0x14009ea09  cmp     rcx, r13
0x14009ea0c  jz      short loc_14009EA2F
0x14009ea0e  test    [rcx+1Ch], sil
0x14009ea12  jz      short loc_14009EA2F
0x14009ea14  lea     edx, [rax+2Ch]
0x14009ea17  lea     r8, WPP_2302b92dd89c3f461ef1ff1dfe596bd8_Traceguids
0x14009ea1e  mov     rcx, [rcx+10h]
0x14009ea22  call    WPP_SF_
0x14009ea27  mov     rbx, [rsp+4F8h+Buf2]
0x14009ea2f  test    rbx, rbx
0x14009ea32  jz      short loc_14009EA3D
0x14009ea34  mov     rcx, rbx; void *
0x14009ea37  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14009ea3c  nop
0x14009ea3d  mov     rcx, [rsp+4F8h+var_460]; hKey
0x14009ea45  test    rcx, rcx
0x14009ea48  jz      short loc_14009EA51
0x14009ea4a  call    cs:__imp_RegCloseKey
0x14009ea50  nop
0x14009ea51  mov     rcx, [rsp+4F8h+var_430]; hKey
0x14009ea59  test    rcx, rcx
0x14009ea5c  jz      loc_14009F646
0x14009ea62  call    cs:__imp_RegCloseKey
0x14009ea68  jmp     loc_14009F646
0x14009ea6d  test    rbx, rbx
0x14009ea70  jz      short loc_14009EA7A
0x14009ea72  mov     rcx, rbx; void *
0x14009ea75  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14009ea7a  lea     r8, aMicrosoftdefen; "MicrosoftDefenderForWindowsClient"
0x14009ea81  lea     rdx, aMdcoresvcEcsag; "MdCoreSvc_EcsAgentName"
0x14009ea88  lea     rcx, [rsp+4F8h+var_4B8]
0x14009ea8d  call    ?GetMiscConfigString@MpWatchDog@@YA?AV?$CReturnHandle@V?$CUniqueHandle@U?$CAutoUniqueArrayPtrDelete2@PEAD@CommonUtil@@@CommonUtil@@@CommonUtil@@PEB_WPEBD@Z; MpWatchDog::GetMiscConfigString(wchar_t const *,char const *)
0x14009ea92  mov     rbx, [rax]
0x14009ea95  mov     [rax], r14
0x14009ea98  mov     [rsp+4F8h+hKey], rbx
0x14009eaa0  mov     rcx, [rsp+4F8h+var_4B8]; void *
0x14009eaa5  test    rcx, rcx
0x14009eaa8  jz      short loc_14009EAAF
0x14009eaaa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14009eaaf  call    ?MpIsCoreSvcInDevMode@MpWatchDog@@YA_NXZ; MpWatchDog::MpIsCoreSvcInDevMode(void)
0x14009eab4  test    al, al
0x14009eab6  jz      short loc_14009EAD1
0x14009eab8  xor     edx, edx; wchar_t *
  ... truncated ...
```
