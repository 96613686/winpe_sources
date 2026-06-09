# Uev::RoamingProfile::GetSettingsStoragePath(bool,boost::filesystem::path &)

- ea: `0x140067c10`
- end: `0x140067e7d`
- name: `?GetSettingsStoragePath@RoamingProfile@Uev@@UEBAX_NAEAVpath@filesystem@boost@@@Z`
- size: `621`
- prototype: `void __fastcall(Uev::RoamingProfile *__hidden this, bool, struct boost::filesystem::path *)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003e50`
- `0x140004ab4`
- `0x14000afc0`
- `0x14000ba60`
- `0x14000c2b8`
- `0x14000d1d8`
- `0x14000d448`
- `0x14000ec5c`
- `0x140010a70`
- `0x1400133e4`
- `0x140015190`
- `0x140023dd4`
- `0x140023e54`
- `0x1400245f0`
- `0x140046e04`
- `0x140046f94`
- `0x140067c10`
- `0x140067eb8`
- `0x14008b63c`

## string_xrefs

- `0x140067c3c`: `UevCommon`
- `0x140067d2e`: `UevCommon`
- `0x140067e03`: `UevCommon`
- `0x140067c35`: `RoamingProfile::GetSettingsStoragePath()`
- `0x140067e49`: `Settings storage path has not been configured`
- `0x140067cc5`: `RoamingProfile::GetSettingsStoragePath() - Path = %1%.`
- `0x140067dcb`: `RoamingProfile::GetSettingsStoragePath() - Error %1% occurred while getting the settings storage path from the repository.`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Uev::RoamingProfile::GetSettingsStoragePath(
        Uev::RoamingProfile *this,
        bool a2,
        struct boost::filesystem::path *a3)
{
  struct boost::filesystem::path *v5; // rcx
  Uev::Repository *v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdi
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rbx
  __int128 v27; // [rsp+20h] [rbp-288h] BYREF
  __int128 v28; // [rsp+30h] [rbp-278h]
  _OWORD v29[2]; // [rsp+40h] [rbp-268h] BYREF
  const Uev::UevException *v30; // [rsp+60h] [rbp-248h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+70h] [rbp-238h] BYREF
  _BYTE v32[64]; // [rsp+B0h] [rbp-1F8h] BYREF
  _BYTE v33[272]; // [rsp+F0h] [rbp-1B8h] BYREF
  int v34[4]; // [rsp+200h] [rbp-A8h] BYREF
  _BYTE v35[128]; // [rsp+210h] [rbp-98h] BYREF

  Uev::ScopeTracker::ScopeTracker((Uev::ScopeTracker *)v35, L"UevCommon", L"RoamingProfile::GetSettingsStoragePath()");
  *((_QWORD *)a3 + 2) = 0;
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v5 = a3;
  else
    v5 = *(struct boost::filesystem::path **)a3;
  *(_WORD *)v5 = 0;
  try
  {
    v6 = (Uev::Repository *)Uev::Singleton<Uev::Repository,Uev::Repository>::Instance();
    v34[0] = Uev::Repository::GetRepositoryPath(v6, a2, a3);
    if ( v34[0] < 0 )
    {
      v16 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v7);
      if ( (unsigned __int8)Uev::Log::WriteEnabled(v16, 8) )
      {
        v18 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v17);
        Uev::Singleton<Uev::Log,Uev::Log>::Instance(v19);
        std::wstring::wstring(
          &v27,
          L"RoamingProfile::GetSettingsStoragePath() - Error %1% occurred while getting the settings storage path from the repository.");
        v21 = Uev::Log::fmt(v20, v33, &v27);
        v22 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator%<long>(v21, v34);
        std::wstring::wstring(v29, L"UevCommon");
        Uev::Log::Write(v18, v23, v29, v22);
        boost::filesystem::path::~path((boost::filesystem::path *)v29);
        boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v33);
        boost::filesystem::path::~path((boost::filesystem::path *)&v27);
      }
      std::wstring::wstring(v29, L"Settings storage path has not been configured");
      Uev::UevException::UevException((__int64)pExceptionObject, v29);
      throw (Uev::UevException *)pExceptionObject;
    }
    if ( (*(_BYTE *)(*(_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(v7) + 32LL) & 8) != 0 )
    {
      v9 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v8);
      Uev::Singleton<Uev::Log,Uev::Log>::Instance(v10);
      memset(v29, 0, sizeof(v29));
      std::wstring::_Construct<1,wchar_t *>(v29, L"RoamingProfile::GetSettingsStoragePath() - Path = %1%.", 0x36u);
      v12 = Uev::Log::fmt(v11, v33, v29);
      *(_QWORD *)&v27 = a3;
      *((_QWORD *)&v27 + 1) = boost::on_process_enter;
      *(_QWORD *)&v28 = boost::io::detail::call_put_last<wchar_t,std::char_traits<wchar_t>,boost::filesystem::path const>;
      v13 = boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(
              v12,
              &v27);
      v27 = 0;
      v28 = 0;
      std::wstring::_Construct<1,wchar_t *>(&v27, L"UevCommon", 9u);
      Uev::Log::Write(v9, v14, &v27, v13);
      std::wstring::_Tidy_deallocate(&v27);
      boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v33);
      std::wstring::_Tidy_deallocate(v29);
    }
    Uev::ScopeTracker::~ScopeTracker((Uev::ScopeTracker *)v35);
  }
  catch ( const Uev::UevException *v30 )
  {
    v24 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v15);
    if ( (unsigned __int8)Uev::Log::WriteEnabled(v24, 8) )
    {
      v26 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v25);
      std::wstring::wstring(
        &v27,
        L"RoamingProfile::GetSettingsStoragePath() - The settings storage path has not been configured.");
      std::wstring::wstring(v29, L"UevCommon");
      Uev::Log::Write(v26, 8, v29, &v27);
      boost::filesystem::path::~path((boost::filesystem::path *)v29);
      boost::filesystem::path::~path((boost::filesystem::path *)&v27);
    }
    std::wstring::wstring(v29, L"Settings storage path has not been configured");
    Uev::UevException::UevException(v32, v29, v30);
    throw (Uev::UevException *)v32;
  }
}

```

## disassembly

```asm
0x140067c10  mov     [rsp+arg_0], rbx
0x140067c15  push    rdi
0x140067c16  sub     rsp, 2A0h
0x140067c1d  mov     rax, cs:__security_cookie
0x140067c24  xor     rax, rsp
0x140067c27  mov     [rsp+2A8h+var_18], rax
0x140067c2f  mov     rbx, r8
0x140067c32  mov     dil, dl
0x140067c35  lea     r8, aRoamingprofile_4; "RoamingProfile::GetSettingsStoragePath("...
0x140067c3c  lea     rdx, aUevcommon; "UevCommon"
0x140067c43  lea     rcx, [rsp+2A8h+var_98]; this
0x140067c4b  call    ??0ScopeTracker@Uev@@QEAA@PEB_W0@Z; Uev::ScopeTracker::ScopeTracker(wchar_t const *,wchar_t const *)
0x140067c50  nop
0x140067c51  mov     qword ptr [rbx+10h], 0
0x140067c59  cmp     qword ptr [rbx+18h], 7
0x140067c5e  jbe     short loc_140067C65
0x140067c60  mov     rcx, [rbx]
0x140067c63  jmp     short loc_140067C68
0x140067c65  mov     rcx, rbx
0x140067c68  xor     eax, eax
0x140067c6a  mov     [rcx], ax
0x140067c6d  call    ?Instance@?$Singleton@VRepository@Uev@@V12@@Uev@@SAPEAVRepository@2@XZ; Uev::Singleton<Uev::Repository,Uev::Repository>::Instance(void)
0x140067c72  mov     r8, rbx; struct boost::filesystem::path *
0x140067c75  mov     dl, dil; bool
0x140067c78  mov     rcx, rax; this
0x140067c7b  call    ?GetRepositoryPath@Repository@Uev@@QEAAJ_NAEAVpath@filesystem@boost@@@Z; Uev::Repository::GetRepositoryPath(bool,boost::filesystem::path &)
0x140067c80  mov     [rsp+2A8h+var_A8], eax
0x140067c87  test    eax, eax
0x140067c89  js      loc_140067DA3
0x140067c8f  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140067c94  mov     rax, [rax]
0x140067c97  test    byte ptr [rax+20h], 8
0x140067c9b  jbe     loc_140067D75
0x140067ca1  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140067ca6  mov     rdi, rax
0x140067ca9  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140067cae  xorps   xmm0, xmm0
0x140067cb1  movups  [rsp+2A8h+var_268], xmm0
0x140067cb6  xorps   xmm1, xmm1
0x140067cb9  movdqu  [rsp+2A8h+var_258], xmm1
0x140067cbf  mov     r8d, 36h ; '6'
0x140067cc5  lea     rdx, aRoamingprofile_1; "RoamingProfile::GetSettingsStoragePath("...
0x140067ccc  lea     rcx, [rsp+2A8h+var_268]
0x140067cd1  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140067cd6  nop
0x140067cd7  lea     r8, [rsp+2A8h+var_268]
0x140067cdc  lea     rdx, [rsp+2A8h+var_1B8]
0x140067ce4  call    ?fmt@Log@Uev@@QEAA?AV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::Log::fmt(std::wstring const &)
0x140067ce9  nop
0x140067cea  mov     qword ptr [rsp+2A8h+var_288], rbx
0x140067cef  lea     rcx, ?on_process_enter@boost@@YAXXZ; boost::on_process_enter(void)
0x140067cf6  mov     qword ptr [rsp+2A8h+var_288+8], rcx
0x140067cfb  lea     rcx, ??$call_put_last@_WU?$char_traits@_W@std@@$$CBVpath@filesystem@boost@@@detail@io@boost@@YAXAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@std@@PEBX@Z; boost::io::detail::call_put_last<wchar_t,std::char_traits<wchar_t>,boost::filesystem::path const>(std::wostream &,void const *)
0x140067d02  mov     qword ptr [rsp+2A8h+var_278], rcx
0x140067d07  lea     rdx, [rsp+2A8h+var_288]
0x140067d0c  mov     rcx, rax
0x140067d0f  call    ??$feed_impl@_WU?$char_traits@_W@std@@V?$allocator@_W@2@AEBU?$put_holder@_WU?$char_traits@_W@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@AEAV32@AEBU?$put_holder@_WU?$char_traits@_W@std@@@012@@Z; boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &)
0x140067d14  mov     rbx, rax
0x140067d17  xorps   xmm0, xmm0
0x140067d1a  movups  [rsp+2A8h+var_288], xmm0
0x140067d1f  xorps   xmm1, xmm1
0x140067d22  movdqu  [rsp+2A8h+var_278], xmm1
0x140067d28  mov     r8d, 9
0x140067d2e  lea     rdx, aUevcommon; "UevCommon"
0x140067d35  lea     rcx, [rsp+2A8h+var_288]
0x140067d3a  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140067d3f  nop
0x140067d40  mov     r9, rbx
0x140067d43  lea     r8, [rsp+2A8h+var_288]
0x140067d48  mov     rcx, rdi
0x140067d4b  call    ?Write@Log@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@@Z; Uev::Log::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)
0x140067d50  nop
0x140067d51  lea     rcx, [rsp+2A8h+var_288]
0x140067d56  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140067d5b  nop
0x140067d5c  lea     rcx, [rsp+2A8h+var_1B8]
0x140067d64  call    ??1?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@QEAA@XZ; boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x140067d69  nop
0x140067d6a  lea     rcx, [rsp+2A8h+var_268]
0x140067d6f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140067d74  nop
0x140067d75  lea     rcx, [rsp+2A8h+var_98]; this
0x140067d7d  call    ??1ScopeTracker@Uev@@UEAA@XZ; Uev::ScopeTracker::~ScopeTracker(void)
0x140067d82  mov     rcx, [rsp+2A8h+var_18]
0x140067d8a  xor     rcx, rsp; StackCookie
0x140067d8d  call    __security_check_cookie
0x140067d92  mov     rbx, [rsp+2A8h+arg_0]
0x140067d9a  add     rsp, 2A0h
0x140067da1  pop     rdi
0x140067da2  retn
0x140067da3  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140067da8  nop
0x140067da9  mov     edx, 8
0x140067dae  mov     rcx, rax
0x140067db1  call    ?WriteEnabled@Log@Uev@@QEBA_NW4UEV_LOG_LEVEL@2@@Z; Uev::Log::WriteEnabled(Uev::UEV_LOG_LEVEL)
0x140067db6  test    al, al
0x140067db8  jz      loc_140067E49
0x140067dbe  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140067dc3  mov     rbx, rax
0x140067dc6  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140067dcb  lea     rdx, aRoamingprofile_2; "RoamingProfile::GetSettingsStoragePath("...
0x140067dd2  lea     rcx, [rsp+2A8h+var_288]
0x140067dd7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140067ddc  nop
0x140067ddd  lea     r8, [rsp+2A8h+var_288]
0x140067de2  lea     rdx, [rsp+2A8h+var_1B8]
0x140067dea  call    ?fmt@Log@Uev@@QEAA?AV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::Log::fmt(std::wstring const &)
0x140067def  nop
0x140067df0  lea     rdx, [rsp+2A8h+var_A8]
0x140067df8  mov     rcx, rax
0x140067dfb  call    ??$?LJ@?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@QEAAAEAV01@AEBJ@Z; boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator%<long>(long const &)
0x140067e00  mov     rdi, rax
0x140067e03  lea     rdx, aUevcommon; "UevCommon"
0x140067e0a  lea     rcx, [rsp+2A8h+var_268]
0x140067e0f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140067e14  nop
0x140067e15  mov     r9, rdi
0x140067e18  lea     r8, [rsp+2A8h+var_268]
0x140067e1d  mov     rcx, rbx
0x140067e20  call    ?Write@Log@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@@Z; Uev::Log::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)
0x140067e25  nop
0x140067e26  lea     rcx, [rsp+2A8h+var_268]; this
0x140067e2b  call    ??1path@filesystem@boost@@QEAA@XZ; boost::filesystem::path::~path(void)
0x140067e30  nop
0x140067e31  lea     rcx, [rsp+2A8h+var_1B8]
0x140067e39  call    ??1?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@QEAA@XZ; boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x140067e3e  nop
0x140067e3f  lea     rcx, [rsp+2A8h+var_288]; this
0x140067e44  call    ??1path@filesystem@boost@@QEAA@XZ; boost::filesystem::path::~path(void)
0x140067e49  lea     rdx, aSettingsStorag; "Settings storage path has not been conf"...
0x140067e50  lea     rcx, [rsp+2A8h+var_268]
0x140067e55  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140067e5a  nop
0x140067e5b  lea     rdx, [rsp+2A8h+var_268]
0x140067e60  lea     rcx, [rsp+2A8h+pExceptionObject]
0x140067e65  call    ??0UevException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::UevException::UevException(std::wstring const &)
0x140067e6a  lea     rdx, _TI2?AVUevException@Uev@@; pThrowInfo
0x140067e71  lea     rcx, [rsp+2A8h+pExceptionObject]; pExceptionObject
0x140067e76  call    _CxxThrowException_0
```
