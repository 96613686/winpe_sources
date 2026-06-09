# Uev::VdiProfile::GetSettingsStoragePath(bool,boost::filesystem::path &)

- ea: `0x1400681a0`
- end: `0x14006855d`
- name: `?GetSettingsStoragePath@VdiProfile@Uev@@UEBAX_NAEAVpath@filesystem@boost@@@Z`
- size: `957`
- prototype: `void(Uev::VdiProfile *__hidden this, bool, struct boost::filesystem::path *)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003e50`
- `0x140004ab4`
- `0x140004df0`
- `0x14000afc0`
- `0x14000ba60`
- `0x14000c2b8`
- `0x14000d1d8`
- `0x14000d448`
- `0x14000ec5c`
- `0x140010a70`
- `0x1400133e4`
- `0x140015190`
- `0x1400203ac`
- `0x140020568`
- `0x140023dbc`
- `0x140023dd4`
- `0x140023e54`
- `0x1400245f0`
- `0x140046e04`
- `0x140046f94`
- `0x140067eb8`
- `0x1400681a0`
- `0x14008b63c`

## string_xrefs

- `0x1400681d1`: `UevCommon`
- `0x140068318`: `UevCommon`
- `0x14006843b`: `UevCommon`
- `0x1400684ea`: `UevCommon`
- `0x140068481`: `Settings storage path has not been configured`
- `0x1400681ca`: `VdiProfile::GetSettingsStoragePath()`
- `0x1400684d8`: `VdiProfile::GetSettingsStoragePath() - Unable to get the VDI collection name for a template using the VDI profile.`
- `0x140068403`: `VdiProfile::GetSettingsStoragePath() - Error %1% occurred while getting the settings storage path from the repository.`
- `0x140068529`: `VdiCollectionName has not been configured`
- `0x1400682af`: `VdiProfile::GetSettingsStoragePath() - Path = %1%.`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall Uev::VdiProfile::GetSettingsStoragePath(
        Uev::VdiProfile *this,
        bool a2,
        struct boost::filesystem::path *a3)
{
  struct boost::filesystem::path *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rcx
  Uev::Repository *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rsi
  __int64 v16; // rdx
  __int64 v17; // rcx
  wchar_t **v18; // rax
  const wchar_t *v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rdi
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rbx
  _OWORD v34[2]; // [rsp+20h] [rbp-2E8h] BYREF
  __int128 v35; // [rsp+40h] [rbp-2C8h] BYREF
  __int128 v36; // [rsp+50h] [rbp-2B8h]
  const Uev::UevException *v37; // [rsp+60h] [rbp-2A8h] BYREF
  _BYTE v38[64]; // [rsp+70h] [rbp-298h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+B0h] [rbp-258h] BYREF
  _BYTE v40[64]; // [rsp+F0h] [rbp-218h] BYREF
  _BYTE v41[272]; // [rsp+130h] [rbp-1D8h] BYREF
  int RepositoryPath; // [rsp+240h] [rbp-C8h] BYREF
  wchar_t *v43[2]; // [rsp+248h] [rbp-C0h] BYREF
  __m128i si128; // [rsp+258h] [rbp-B0h]
  __int64 v45; // [rsp+268h] [rbp-A0h] BYREF
  _BYTE v46[128]; // [rsp+270h] [rbp-98h] BYREF

  Uev::ScopeTracker::ScopeTracker((Uev::ScopeTracker *)v46, L"UevCommon", L"VdiProfile::GetSettingsStoragePath()");
  *((_QWORD *)a3 + 2) = 0;
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v5 = a3;
  else
    v5 = *(struct boost::filesystem::path **)a3;
  *(_WORD *)v5 = 0;
  *(_OWORD *)v43 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v43[0]) = 0;
  v45 = 0;
  try
  {
    v6 = Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance();
    if ( !(unsigned __int8)Uev::Setting<std::wstring>::Get(v6 + 10480, v43, &v45) )
    {
      v28 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v7);
      if ( (unsigned __int8)Uev::Log::WriteEnabled(v28, 8) )
      {
        v30 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v29);
        std::wstring::wstring(
          &v35,
          L"VdiProfile::GetSettingsStoragePath() - Unable to get the VDI collection name for a template using the VDI profile.");
        std::wstring::wstring(v34, L"UevCommon");
        Uev::Log::Write(v30, 8, v34, &v35);
        boost::filesystem::path::~path((boost::filesystem::path *)v34);
        boost::filesystem::path::~path((boost::filesystem::path *)&v35);
      }
      std::wstring::wstring(v34, L"VdiCollectionName has not been configured");
      Uev::UevException::UevException((__int64)v38, v34);
      throw (Uev::UevException *)v38;
    }
    v8 = (Uev::Repository *)Uev::Singleton<Uev::Repository,Uev::Repository>::Instance();
    RepositoryPath = Uev::Repository::GetRepositoryPath(v8, a2, a3);
    if ( RepositoryPath < 0 )
    {
      v20 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v9);
      if ( (unsigned __int8)Uev::Log::WriteEnabled(v20, 8) )
      {
        v22 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v21);
        Uev::Singleton<Uev::Log,Uev::Log>::Instance(v23);
        std::wstring::wstring(
          &v35,
          L"VdiProfile::GetSettingsStoragePath() - Error %1% occurred while getting the settings storage path from the repository.");
        v25 = Uev::Log::fmt(v24, v41, &v35);
        v26 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator%<long>(
                v25,
                &RepositoryPath);
        std::wstring::wstring(v34, L"UevCommon");
        Uev::Log::Write(v22, v27, v34, v26);
        boost::filesystem::path::~path((boost::filesystem::path *)v34);
        boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v41);
        boost::filesystem::path::~path((boost::filesystem::path *)&v35);
      }
      std::wstring::wstring(v34, L"Settings storage path has not been configured");
      Uev::UevException::UevException((__int64)pExceptionObject, v34);
      throw (Uev::UevException *)pExceptionObject;
    }
    if ( (*(_BYTE *)(*(_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(v9) + 32LL) & 8) != 0 )
    {
      v11 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v10);
      Uev::Singleton<Uev::Log,Uev::Log>::Instance(v12);
      memset(v34, 0, sizeof(v34));
      std::wstring::_Construct<1,wchar_t *>(v34, L"VdiProfile::GetSettingsStoragePath() - Path = %1%.", 0x32u);
      v14 = Uev::Log::fmt(v13, v41, v34);
      *(_QWORD *)&v35 = a3;
      *((_QWORD *)&v35 + 1) = boost::on_process_enter;
      *(_QWORD *)&v36 = boost::io::detail::call_put_last<wchar_t,std::char_traits<wchar_t>,boost::filesystem::path const>;
      v15 = boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(
              v14,
              &v35);
      v35 = 0;
      v36 = 0;
      std::wstring::_Construct<1,wchar_t *>(&v35, L"UevCommon", 9u);
      Uev::Log::Write(v11, v16, &v35, v15);
      std::wstring::_Tidy_deallocate(&v35);
      boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v41);
      std::wstring::_Tidy_deallocate(v34);
    }
    v17 = si128.m128i_i64[0];
    if ( si128.m128i_i64[1] > 7uLL )
    {
      v18 = (wchar_t **)v43[0];
      v19 = v43[0];
    }
    else
    {
      v18 = v43;
      v19 = (const wchar_t *)v43;
    }
  }
  catch ( const Uev::UevException *v37 )
  {
    v31 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v17);
    if ( (unsigned __int8)Uev::Log::WriteEnabled(v31, 8) )
    {
      v33 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v32);
      std::wstring::wstring(
        v43,
        L"VdiProfile::GetSettingsStoragePath() - The settings storage path has not been configured.");
      std::wstring::wstring(v34, L"UevCommon");
      Uev::Log::Write(v33, 8, v34, v43);
      boost::filesystem::path::~path((boost::filesystem::path *)v34);
      boost::filesystem::path::~path((boost::filesystem::path *)v43);
    }
    std::wstring::wstring(v34, L"Settings storage path has not been configured");
    Uev::UevException::UevException(v40, v34, v37);
    throw (Uev::UevException *)v40;
  }
  boost::filesystem::path::append_v3(a3, v19, (const wchar_t *)v18 + v17);
  std::wstring::_Tidy_deallocate(v43);
  Uev::ScopeTracker::~ScopeTracker((Uev::ScopeTracker *)v46);
}

```

## disassembly

```asm
0x1400681a0  mov     [rsp+arg_0], rbx
0x1400681a5  mov     [rsp+arg_18], rsi
0x1400681aa  push    rdi
0x1400681ab  sub     rsp, 300h
0x1400681b2  mov     rax, cs:__security_cookie
0x1400681b9  xor     rax, rsp
0x1400681bc  mov     [rsp+308h+var_18], rax
0x1400681c4  mov     rbx, r8
0x1400681c7  mov     dil, dl
0x1400681ca  lea     r8, aVdiprofileGets_0; "VdiProfile::GetSettingsStoragePath()"
0x1400681d1  lea     rdx, aUevcommon; "UevCommon"
0x1400681d8  lea     rcx, [rsp+308h+var_98]; this
0x1400681e0  call    ??0ScopeTracker@Uev@@QEAA@PEB_W0@Z; Uev::ScopeTracker::ScopeTracker(wchar_t const *,wchar_t const *)
0x1400681e5  nop
0x1400681e6  mov     qword ptr [rbx+10h], 0
0x1400681ee  cmp     qword ptr [rbx+18h], 7
0x1400681f3  jbe     short loc_1400681FA
0x1400681f5  mov     rcx, [rbx]
0x1400681f8  jmp     short loc_1400681FD
0x1400681fa  mov     rcx, rbx
0x1400681fd  xor     eax, eax
0x1400681ff  mov     [rcx], ax
0x140068202  xorps   xmm0, xmm0
0x140068205  movups  xmmword ptr [rsp+308h+var_C0], xmm0
0x14006820d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140068215  movdqu  [rsp+308h+var_B0], xmm1
0x14006821e  mov     word ptr [rsp+308h+var_C0], ax
0x140068226  mov     [rsp+308h+var_A0], rax
0x14006822e  call    ?Instance@?$Singleton@VConfiguration@Uev@@V12@@Uev@@SAPEAVConfiguration@2@XZ; Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance(void)
0x140068233  lea     rcx, [rax+28F0h]
0x14006823a  lea     r8, [rsp+308h+var_A0]
0x140068242  lea     rdx, [rsp+308h+var_C0]
0x14006824a  call    ?Get@?$Setting@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Uev@@QEBA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAUSettingInfo@2@@Z; Uev::Setting<std::wstring>::Get(std::wstring &,Uev::SettingInfo &)
0x14006824f  test    al, al
0x140068251  jz      loc_1400684BA
0x140068257  call    ?Instance@?$Singleton@VRepository@Uev@@V12@@Uev@@SAPEAVRepository@2@XZ; Uev::Singleton<Uev::Repository,Uev::Repository>::Instance(void)
0x14006825c  mov     r8, rbx; struct boost::filesystem::path *
0x14006825f  mov     dl, dil; bool
0x140068262  mov     rcx, rax; this
0x140068265  call    ?GetRepositoryPath@Repository@Uev@@QEAAJ_NAEAVpath@filesystem@boost@@@Z; Uev::Repository::GetRepositoryPath(bool,boost::filesystem::path &)
0x14006826a  mov     [rsp+308h+var_C8], eax
0x140068271  test    eax, eax
0x140068273  js      loc_1400683DB
0x140068279  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x14006827e  mov     rax, [rax]
0x140068281  test    byte ptr [rax+20h], 8
0x140068285  jbe     loc_14006835E
0x14006828b  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140068290  mov     rdi, rax
0x140068293  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140068298  xorps   xmm0, xmm0
0x14006829b  movups  [rsp+308h+var_2E8], xmm0
0x1400682a0  xorps   xmm1, xmm1
0x1400682a3  movdqu  [rsp+308h+var_2D8], xmm1
0x1400682a9  mov     r8d, 32h ; '2'
0x1400682af  lea     rdx, aVdiprofileGets_3; "VdiProfile::GetSettingsStoragePath() - "...
0x1400682b6  lea     rcx, [rsp+308h+var_2E8]
0x1400682bb  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1400682c0  nop
0x1400682c1  lea     r8, [rsp+308h+var_2E8]
0x1400682c6  lea     rdx, [rsp+308h+var_1D8]
0x1400682ce  call    ?fmt@Log@Uev@@QEAA?AV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::Log::fmt(std::wstring const &)
0x1400682d3  nop
0x1400682d4  mov     qword ptr [rsp+308h+var_2C8], rbx
0x1400682d9  lea     rcx, ?on_process_enter@boost@@YAXXZ; boost::on_process_enter(void)
0x1400682e0  mov     qword ptr [rsp+308h+var_2C8+8], rcx
0x1400682e5  lea     rcx, ??$call_put_last@_WU?$char_traits@_W@std@@$$CBVpath@filesystem@boost@@@detail@io@boost@@YAXAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@std@@PEBX@Z; boost::io::detail::call_put_last<wchar_t,std::char_traits<wchar_t>,boost::filesystem::path const>(std::wostream &,void const *)
0x1400682ec  mov     qword ptr [rsp+308h+var_2B8], rcx
0x1400682f1  lea     rdx, [rsp+308h+var_2C8]
0x1400682f6  mov     rcx, rax
0x1400682f9  call    ??$feed_impl@_WU?$char_traits@_W@std@@V?$allocator@_W@2@AEBU?$put_holder@_WU?$char_traits@_W@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@AEAV32@AEBU?$put_holder@_WU?$char_traits@_W@std@@@012@@Z; boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &)
0x1400682fe  mov     rsi, rax
0x140068301  xorps   xmm0, xmm0
0x140068304  movups  [rsp+308h+var_2C8], xmm0
0x140068309  xorps   xmm1, xmm1
0x14006830c  movdqu  [rsp+308h+var_2B8], xmm1
0x140068312  mov     r8d, 9
0x140068318  lea     rdx, aUevcommon; "UevCommon"
0x14006831f  lea     rcx, [rsp+308h+var_2C8]
0x140068324  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140068329  nop
0x14006832a  mov     r9, rsi
0x14006832d  lea     r8, [rsp+308h+var_2C8]
0x140068332  mov     rcx, rdi
0x140068335  call    ?Write@Log@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@@Z; Uev::Log::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)
0x14006833a  nop
0x14006833b  lea     rcx, [rsp+308h+var_2C8]
0x140068340  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140068345  nop
0x140068346  lea     rcx, [rsp+308h+var_1D8]
0x14006834e  call    ??1?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@QEAA@XZ; boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x140068353  nop
0x140068354  lea     rcx, [rsp+308h+var_2E8]
0x140068359  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006835e  mov     rcx, qword ptr [rsp+308h+var_B0]
0x140068366  cmp     qword ptr [rsp+308h+var_B0+8], 7
0x14006836f  ja      short loc_140068383
0x140068371  lea     rax, [rsp+308h+var_C0]
0x140068379  lea     rdx, [rsp+308h+var_C0]
0x140068381  jmp     short loc_14006838E
0x140068383  mov     rax, [rsp+308h+var_C0]
0x14006838b  mov     rdx, rax; wchar_t *
0x14006838e  lea     r8, [rax+rcx*2]; wchar_t *
0x140068392  mov     rcx, rbx; this
0x140068395  call    ?append_v3@path@filesystem@boost@@AEAAXPEB_W0@Z; boost::filesystem::path::append_v3(wchar_t const *,wchar_t const *)
0x14006839a  nop
0x14006839b  lea     rcx, [rsp+308h+var_C0]
0x1400683a3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400683a8  nop
0x1400683a9  lea     rcx, [rsp+308h+var_98]; this
0x1400683b1  call    ??1ScopeTracker@Uev@@UEAA@XZ; Uev::ScopeTracker::~ScopeTracker(void)
0x1400683b6  mov     rcx, [rsp+308h+var_18]
0x1400683be  xor     rcx, rsp; StackCookie
0x1400683c1  call    __security_check_cookie
0x1400683c6  lea     r11, [rsp+308h+var_8]
0x1400683ce  mov     rbx, [r11+10h]
0x1400683d2  mov     rsi, [r11+28h]
0x1400683d6  mov     rsp, r11
0x1400683d9  pop     rdi
0x1400683da  retn
0x1400683db  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x1400683e0  nop
0x1400683e1  mov     edx, 8
0x1400683e6  mov     rcx, rax
0x1400683e9  call    ?WriteEnabled@Log@Uev@@QEBA_NW4UEV_LOG_LEVEL@2@@Z; Uev::Log::WriteEnabled(Uev::UEV_LOG_LEVEL)
0x1400683ee  test    al, al
0x1400683f0  jz      loc_140068481
0x1400683f6  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x1400683fb  mov     rbx, rax
0x1400683fe  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140068403  lea     rdx, aVdiprofileGets; "VdiProfile::GetSettingsStoragePath() - "...
0x14006840a  lea     rcx, [rsp+308h+var_2C8]
0x14006840f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140068414  nop
0x140068415  lea     r8, [rsp+308h+var_2C8]
0x14006841a  lea     rdx, [rsp+308h+var_1D8]
0x140068422  call    ?fmt@Log@Uev@@QEAA?AV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::Log::fmt(std::wstring const &)
0x140068427  nop
0x140068428  lea     rdx, [rsp+308h+var_C8]
0x140068430  mov     rcx, rax
0x140068433  call    ??$?LJ@?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@QEAAAEAV01@AEBJ@Z; boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator%<long>(long const &)
0x140068438  mov     rdi, rax
0x14006843b  lea     rdx, aUevcommon; "UevCommon"
0x140068442  lea     rcx, [rsp+308h+var_2E8]
0x140068447  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14006844c  nop
0x14006844d  mov     r9, rdi
0x140068450  lea     r8, [rsp+308h+var_2E8]
0x140068455  mov     rcx, rbx
0x140068458  call    ?Write@Log@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@@Z; Uev::Log::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)
0x14006845d  nop
0x14006845e  lea     rcx, [rsp+308h+var_2E8]; this
0x140068463  call    ??1path@filesystem@boost@@QEAA@XZ; boost::filesystem::path::~path(void)
0x140068468  nop
0x140068469  lea     rcx, [rsp+308h+var_1D8]
0x140068471  call    ??1?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@QEAA@XZ; boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x140068476  nop
0x140068477  lea     rcx, [rsp+308h+var_2C8]; this
0x14006847c  call    ??1path@filesystem@boost@@QEAA@XZ; boost::filesystem::path::~path(void)
0x140068481  lea     rdx, aSettingsStorag; "Settings storage path has not been conf"...
0x140068488  lea     rcx, [rsp+308h+var_2E8]
0x14006848d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140068492  nop
0x140068493  lea     rdx, [rsp+308h+var_2E8]
0x140068498  lea     rcx, [rsp+308h+pExceptionObject]
0x1400684a0  call    ??0UevException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::UevException::UevException(std::wstring const &)
0x1400684a5  lea     rdx, _TI2?AVUevException@Uev@@; pThrowInfo
0x1400684ac  lea     rcx, [rsp+308h+pExceptionObject]; pExceptionObject
0x1400684b4  call    _CxxThrowException_0
0x1400684ba  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x1400684bf  mov     edx, 8
0x1400684c4  mov     rcx, rax
0x1400684c7  call    ?WriteEnabled@Log@Uev@@QEBA_NW4UEV_LOG_LEVEL@2@@Z; Uev::Log::WriteEnabled(Uev::UEV_LOG_LEVEL)
0x1400684cc  test    al, al
0x1400684ce  jz      short loc_140068529
0x1400684d0  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x1400684d5  mov     rbx, rax
0x1400684d8  lea     rdx, aVdiprofileGets_1; "VdiProfile::GetSettingsStoragePath() - "...
0x1400684df  lea     rcx, [rsp+308h+var_2C8]
0x1400684e4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400684e9  nop
0x1400684ea  lea     rdx, aUevcommon; "UevCommon"
0x1400684f1  lea     rcx, [rsp+308h+var_2E8]
0x1400684f6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1400684fb  nop
0x1400684fc  lea     r9, [rsp+308h+var_2C8]
0x140068501  lea     r8, [rsp+308h+var_2E8]
0x140068506  mov     edx, 8
0x14006850b  mov     rcx, rbx
0x14006850e  call    ?Write@Log@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; Uev::Log::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140068513  nop
0x140068514  lea     rcx, [rsp+308h+var_2E8]; this
0x140068519  call    ??1path@filesystem@boost@@QEAA@XZ; boost::filesystem::path::~path(void)
0x14006851e  nop
0x14006851f  lea     rcx, [rsp+308h+var_2C8]; this
0x140068524  call    ??1path@filesystem@boost@@QEAA@XZ; boost::filesystem::path::~path(void)
0x140068529  lea     rdx, aVdicollectionn; "VdiCollectionName has not been configur"...
0x140068530  lea     rcx, [rsp+308h+var_2E8]
0x140068535  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14006853a  nop
0x14006853b  lea     rdx, [rsp+308h+var_2E8]
0x140068540  lea     rcx, [rsp+308h+var_298]
0x140068545  call    ??0UevException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::UevException::UevException(std::wstring const &)
0x14006854a  lea     rdx, _TI2?AVUevException@Uev@@; pThrowInfo
0x140068551  lea     rcx, [rsp+308h+var_298]; pExceptionObject
0x140068556  call    _CxxThrowException_0
```
