# Uev::BackupProfile::GetSettingsStoragePathForMachine(bool,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,boost::filesystem::path &)

- ea: `0x140068c40`
- end: `0x14006905f`
- name: `?GetSettingsStoragePathForMachine@BackupProfile@Uev@@UEBAX_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVpath@filesystem@boost@@@Z`
- size: `1055`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003e50`
- `0x140003e74`
- `0x140004ab4`
- `0x14000adb4`
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
- `0x140023dd4`
- `0x140023e54`
- `0x1400245f0`
- `0x140046e04`
- `0x140046f94`
- `0x140067eb8`
- `0x140068c40`
- `0x14008b63c`
- `0x14008d1c8`
- `0x14009b010`

## string_xrefs

- `0x140068c70`: `UevCommon`
- `0x140068e80`: `UevCommon`
- `0x140068fa3`: `UevCommon`
- `0x140068fec`: `Settings storage path has not been configured`
- `0x140068c69`: `BackupProfile::GetSettingsStoragePathForMachine()`
- `0x140068f65`: `BackupProfile::GetSettingsStoragePathForMachine() - Error %1% occurred while getting the settings storage path from the repository.`
- `0x140068e0e`: `BackupProfile::GetSettingsStoragePathForMachine() - Path = %1%.`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall Uev::BackupProfile::GetSettingsStoragePathForMachine(__int64 a1, bool a2, __int64 a3, _QWORD *a4)
{
  _WORD *v7; // rcx
  Uev::Repository *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 *v11; // r14
  __int64 v12; // rdi
  void *v13; // rbx
  void (__fastcall *v14)(__int64, _QWORD *, __int128 *, _QWORD *); // r14
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdi
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rsi
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rdi
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rbx
  __int128 v35; // [rsp+30h] [rbp-328h] BYREF
  __int64 v36; // [rsp+40h] [rbp-318h]
  __int64 v37; // [rsp+48h] [rbp-310h]
  __int128 v38; // [rsp+50h] [rbp-308h] BYREF
  __int64 (__fastcall *v39)(__int64, __int64); // [rsp+60h] [rbp-2F8h]
  __int64 v40; // [rsp+68h] [rbp-2F0h]
  void (__fastcall ***v41)(_QWORD); // [rsp+70h] [rbp-2E8h] BYREF
  __int128 v42; // [rsp+78h] [rbp-2E0h]
  const Uev::UevException *v43; // [rsp+90h] [rbp-2C8h] BYREF
  _BYTE v44[64]; // [rsp+A0h] [rbp-2B8h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+E0h] [rbp-278h] BYREF
  _BYTE v46[64]; // [rsp+120h] [rbp-238h] BYREF
  _BYTE v47[272]; // [rsp+160h] [rbp-1F8h] BYREF
  int RepositoryPath; // [rsp+270h] [rbp-E8h] BYREF
  __int128 v49; // [rsp+278h] [rbp-E0h] BYREF
  __int64 v50; // [rsp+288h] [rbp-D0h]
  __int64 v51; // [rsp+290h] [rbp-C8h]
  __int64 v52; // [rsp+298h] [rbp-C0h] BYREF
  _BYTE v53[128]; // [rsp+2A0h] [rbp-B8h] BYREF

  Uev::ScopeTracker::ScopeTracker(
    (Uev::ScopeTracker *)v53,
    L"UevCommon",
    L"BackupProfile::GetSettingsStoragePathForMachine()");
  a4[2] = 0;
  if ( a4[3] <= 7u )
    v7 = a4;
  else
    v7 = (_WORD *)*a4;
  *v7 = 0;
  try
  {
    v8 = (Uev::Repository *)Uev::Singleton<Uev::Repository,Uev::Repository>::Instance();
    RepositoryPath = Uev::Repository::GetRepositoryPath(v8, a2, (struct boost::filesystem::path *)a4);
    if ( RepositoryPath < 0 )
    {
      v24 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v9);
      if ( (unsigned __int8)Uev::Log::WriteEnabled(v24, 8) )
      {
        v26 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v25);
        Uev::Singleton<Uev::Log,Uev::Log>::Instance(v27);
        std::wstring::wstring(
          &v49,
          L"BackupProfile::GetSettingsStoragePathForMachine() - Error %1% occurred while getting the settings storage path"
           " from the repository.");
        v29 = Uev::Log::fmt(v28, v47, &v49);
        v30 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator%<long>(
                v29,
                &RepositoryPath);
        std::wstring::wstring(&v35, L"UevCommon");
        Uev::Log::Write(v26, v31, &v35, v30);
        boost::filesystem::path::~path((boost::filesystem::path *)&v35);
        boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v47);
        boost::filesystem::path::~path((boost::filesystem::path *)&v49);
      }
      std::wstring::wstring(&v35, L"Settings storage path has not been configured");
      Uev::UevException::UevException((__int64)pExceptionObject, &v35);
      throw (Uev::UevException *)pExceptionObject;
    }
    v49 = 0;
    v50 = 0;
    v51 = 7;
    LOWORD(v49) = 0;
    v52 = 0;
    v42 = 0;
    v10 = Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance();
    if ( !(unsigned __int8)Uev::Setting<std::wstring>::Get(v10 + 4800, &v49, &v52) )
    {
      std::wstring::wstring(&v35, L"Could not retrieve SyncProviderName setting value");
      Uev::UevException::UevException((__int64)v44, &v35);
      throw (Uev::UevException *)v44;
    }
    v11 = (__int64 *)Uev::RemoteStoreFactory::CreateRemoteStore(&v41, &v49);
    v12 = *v11;
    if ( *v11 )
    {
      v13 = operator new(0x18u);
      *((_DWORD *)v13 + 2) = 1;
      *((_DWORD *)v13 + 3) = 1;
      *(_QWORD *)v13 = &std::_Ref_count_resource<Uev::IRemoteStore *,std::default_delete<Uev::IRemoteStore>>::`vftable';
      *((_QWORD *)v13 + 2) = v12;
      *v11 = 0;
    }
    else
    {
      v13 = 0;
    }
    *(_QWORD *)&v42 = v12;
    *((_QWORD *)&v42 + 1) = v13;
    if ( v41 )
      (**v41)(v41);
    v14 = *(void (__fastcall **)(__int64, _QWORD *, __int128 *, _QWORD *))(*(_QWORD *)v12 + 16LL);
    std::wstring::wstring((__int64)&v35, a3);
    v14(v12, a4, &v35, a4);
    std::wstring::_Tidy_deallocate(&v35);
    if ( (*(_BYTE *)(*(_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(v15) + 32LL) & 8) != 0 )
    {
      v17 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v16);
      Uev::Singleton<Uev::Log,Uev::Log>::Instance(v18);
      v35 = 0;
      v36 = 0;
      v37 = 0;
      std::wstring::_Construct<1,wchar_t *>(
        &v35,
        L"BackupProfile::GetSettingsStoragePathForMachine() - Path = %1%.",
        0x3Fu);
      v20 = Uev::Log::fmt(v19, v47, &v35);
      *(_QWORD *)&v38 = a4;
      *((_QWORD *)&v38 + 1) = boost::on_process_enter;
      v39 = boost::io::detail::call_put_last<wchar_t,std::char_traits<wchar_t>,boost::filesystem::path const>;
      v21 = boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(
              v20,
              &v38);
      v38 = 0;
      v39 = 0;
      v40 = 0;
      std::wstring::_Construct<1,wchar_t *>(&v38, L"UevCommon", 9u);
      Uev::Log::Write(v17, v22, &v38, v21);
      std::wstring::_Tidy_deallocate(&v38);
      boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v47);
      std::wstring::_Tidy_deallocate(&v35);
    }
    if ( v13 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v13)(v13);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
    std::wstring::_Tidy_deallocate(&v49);
    Uev::ScopeTracker::~ScopeTracker((Uev::ScopeTracker *)v53);
  }
  catch ( const Uev::UevException *v43 )
  {
    v32 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v23);
    if ( (unsigned __int8)Uev::Log::WriteEnabled(v32, 8) )
    {
      v34 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v33);
      std::wstring::wstring(
        &v49,
        L"BackupProfile::GetSettingsStoragePathForMachine() - The settings storage path has not been configured.");
      std::wstring::wstring(&v35, L"UevCommon");
      Uev::Log::Write(v34, 8, &v35, &v49);
      boost::filesystem::path::~path((boost::filesystem::path *)&v35);
      boost::filesystem::path::~path((boost::filesystem::path *)&v49);
    }
    std::wstring::wstring(&v35, L"Settings storage path has not been configured");
    Uev::UevException::UevException(v46, &v35, v43);
    throw (Uev::UevException *)v46;
  }
}

```

## disassembly

```asm
0x140068c40  push    rbx
0x140068c42  push    rsi
0x140068c43  push    rdi
0x140068c44  push    r14
0x140068c46  push    r15
0x140068c48  sub     rsp, 330h
0x140068c4f  mov     rax, cs:__security_cookie
0x140068c56  xor     rax, rsp
0x140068c59  mov     [rsp+358h+var_38], rax
0x140068c61  mov     rsi, r9
0x140068c64  mov     r15, r8
0x140068c67  mov     bl, dl
0x140068c69  lea     r8, aBackupprofileG_3; "BackupProfile::GetSettingsStoragePathFo"...
0x140068c70  lea     rdx, aUevcommon; "UevCommon"
0x140068c77  lea     rcx, [rsp+358h+var_B8]; this
0x140068c7f  call    ??0ScopeTracker@Uev@@QEAA@PEB_W0@Z; Uev::ScopeTracker::ScopeTracker(wchar_t const *,wchar_t const *)
0x140068c84  nop
0x140068c85  mov     qword ptr [rsi+10h], 0
0x140068c8d  cmp     qword ptr [rsi+18h], 7
0x140068c92  jbe     short loc_140068C99
0x140068c94  mov     rcx, [rsi]
0x140068c97  jmp     short loc_140068C9C
0x140068c99  mov     rcx, rsi
0x140068c9c  xor     eax, eax
0x140068c9e  mov     [rcx], ax
0x140068ca1  call    ?Instance@?$Singleton@VRepository@Uev@@V12@@Uev@@SAPEAVRepository@2@XZ; Uev::Singleton<Uev::Repository,Uev::Repository>::Instance(void)
0x140068ca6  mov     r8, rsi; struct boost::filesystem::path *
0x140068ca9  mov     dl, bl; bool
0x140068cab  mov     rcx, rax; this
0x140068cae  call    ?GetRepositoryPath@Repository@Uev@@QEAAJ_NAEAVpath@filesystem@boost@@@Z; Uev::Repository::GetRepositoryPath(bool,boost::filesystem::path &)
0x140068cb3  mov     [rsp+358h+var_E8], eax
0x140068cba  test    eax, eax
0x140068cbc  js      loc_140068F3D
0x140068cc2  xorps   xmm0, xmm0
0x140068cc5  movups  [rsp+358h+var_E0], xmm0
0x140068ccd  mov     [rsp+358h+var_D0], 0
0x140068cd9  mov     [rsp+358h+var_C8], 7
0x140068ce5  xor     eax, eax
0x140068ce7  mov     word ptr [rsp+358h+var_E0], ax
0x140068cef  mov     [rsp+358h+var_C0], rax
0x140068cf7  movdqu  [rsp+358h+var_2E0], xmm0
0x140068cfd  call    ?Instance@?$Singleton@VConfiguration@Uev@@V12@@Uev@@SAPEAVConfiguration@2@XZ; Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance(void)
0x140068d02  lea     rcx, [rax+12C0h]
0x140068d09  lea     r8, [rsp+358h+var_C0]
0x140068d11  lea     rdx, [rsp+358h+var_E0]
0x140068d19  call    ?Get@?$Setting@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Uev@@QEBA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAUSettingInfo@2@@Z; Uev::Setting<std::wstring>::Get(std::wstring &,Uev::SettingInfo &)
0x140068d1e  test    al, al
0x140068d20  jz      loc_140069025
0x140068d26  lea     rdx, [rsp+358h+var_E0]
0x140068d2e  lea     rcx, [rsp+358h+var_2E8]
0x140068d33  call    ?CreateRemoteStore@RemoteStoreFactory@Uev@@SA?AV?$unique_ptr@VIRemoteStore@Uev@@U?$default_delete@VIRemoteStore@Uev@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Uev::RemoteStoreFactory::CreateRemoteStore(std::wstring const &)
0x140068d38  mov     r14, rax
0x140068d3b  mov     rdi, [rax]
0x140068d3e  test    rdi, rdi
0x140068d41  jz      short loc_140068D72
0x140068d43  mov     ecx, 18h; Size
0x140068d48  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140068d4d  mov     rbx, rax
0x140068d50  mov     edx, 1
0x140068d55  mov     [rax+8], edx
0x140068d58  mov     [rax+0Ch], edx
0x140068d5b  lea     rax, ??_7?$_Ref_count_resource@PEAVIRemoteStore@Uev@@U?$default_delete@VIRemoteStore@Uev@@@std@@@std@@6B@; const std::_Ref_count_resource<Uev::IRemoteStore *,std::default_delete<Uev::IRemoteStore>>::`vftable'
0x140068d62  mov     [rbx], rax
0x140068d65  mov     [rbx+10h], rdi
0x140068d69  mov     qword ptr [r14], 0
0x140068d70  jmp     short loc_140068D77
0x140068d72  xor     ebx, ebx
0x140068d74  lea     edx, [rbx+1]
0x140068d77  mov     qword ptr [rsp+358h+var_2E0], rdi
0x140068d7c  mov     qword ptr [rsp+358h+var_2E0+8], rbx
0x140068d84  mov     rcx, [rsp+358h+var_2E8]
0x140068d89  test    rcx, rcx
0x140068d8c  jz      short loc_140068D99
0x140068d8e  mov     rax, [rcx]
0x140068d91  mov     rax, [rax]
0x140068d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140068d99  mov     rax, [rdi]
0x140068d9c  mov     r14, [rax+10h]
0x140068da0  mov     rdx, r15
0x140068da3  lea     rcx, [rsp+358h+var_328]
0x140068da8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140068dad  nop
0x140068dae  mov     r9, rsi
0x140068db1  lea     r8, [rsp+358h+var_328]
0x140068db6  mov     rdx, rsi
0x140068db9  mov     rcx, rdi
0x140068dbc  mov     rax, r14
0x140068dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140068dc4  nop
0x140068dc5  lea     rcx, [rsp+358h+var_328]
0x140068dca  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140068dcf  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140068dd4  mov     rax, [rax]
0x140068dd7  test    byte ptr [rax+20h], 8
0x140068ddb  jbe     loc_140068EC7
0x140068de1  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140068de6  mov     rdi, rax
0x140068de9  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140068dee  xorps   xmm0, xmm0
0x140068df1  movups  [rsp+358h+var_328], xmm0
0x140068df6  mov     [rsp+358h+var_318], 0
0x140068dff  mov     [rsp+358h+var_310], 0
0x140068e08  mov     r8d, 3Fh ; '?'
0x140068e0e  lea     rdx, aBackupprofileG_0; "BackupProfile::GetSettingsStoragePathFo"...
0x140068e15  lea     rcx, [rsp+358h+var_328]
0x140068e1a  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140068e1f  nop
0x140068e20  lea     r8, [rsp+358h+var_328]
0x140068e25  lea     rdx, [rsp+358h+var_1F8]
0x140068e2d  call    ?fmt@Log@Uev@@QEAA?AV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::Log::fmt(std::wstring const &)
0x140068e32  nop
0x140068e33  mov     qword ptr [rsp+358h+var_308], rsi
0x140068e38  lea     rcx, ?on_process_enter@boost@@YAXXZ; boost::on_process_enter(void)
0x140068e3f  mov     qword ptr [rsp+358h+var_308+8], rcx
0x140068e44  lea     rcx, ??$call_put_last@_WU?$char_traits@_W@std@@$$CBVpath@filesystem@boost@@@detail@io@boost@@YAXAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@std@@PEBX@Z; boost::io::detail::call_put_last<wchar_t,std::char_traits<wchar_t>,boost::filesystem::path const>(std::wostream &,void const *)
0x140068e4b  mov     [rsp+358h+var_2F8], rcx
0x140068e50  lea     rdx, [rsp+358h+var_308]
0x140068e55  mov     rcx, rax
0x140068e58  call    ??$feed_impl@_WU?$char_traits@_W@std@@V?$allocator@_W@2@AEBU?$put_holder@_WU?$char_traits@_W@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@AEAV32@AEBU?$put_holder@_WU?$char_traits@_W@std@@@012@@Z; boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &)
0x140068e5d  mov     rsi, rax
0x140068e60  xorps   xmm0, xmm0
0x140068e63  movups  [rsp+358h+var_308], xmm0
0x140068e68  mov     [rsp+358h+var_2F8], 0
0x140068e71  mov     [rsp+358h+var_2F0], 0
0x140068e7a  mov     r8d, 9
0x140068e80  lea     rdx, aUevcommon; "UevCommon"
0x140068e87  lea     rcx, [rsp+358h+var_308]
0x140068e8c  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140068e91  nop
0x140068e92  mov     r9, rsi
0x140068e95  lea     r8, [rsp+358h+var_308]
0x140068e9a  mov     rcx, rdi
0x140068e9d  call    ?Write@Log@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@@Z; Uev::Log::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)
0x140068ea2  nop
0x140068ea3  lea     rcx, [rsp+358h+var_308]
0x140068ea8  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140068ead  nop
0x140068eae  lea     rcx, [rsp+358h+var_1F8]
0x140068eb6  call    ??1?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@QEAA@XZ; boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x140068ebb  nop
0x140068ebc  lea     rcx, [rsp+358h+var_328]
0x140068ec1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140068ec6  nop
0x140068ec7  test    rbx, rbx
0x140068eca  jz      short loc_140068F03
0x140068ecc  or      edi, 0FFFFFFFFh
0x140068ecf  mov     eax, edi
0x140068ed1  lock xadd [rbx+8], eax
0x140068ed6  add     eax, edi
0x140068ed8  jnz     short loc_140068F03
0x140068eda  mov     rax, [rbx]
0x140068edd  mov     rcx, rbx
0x140068ee0  mov     rax, [rax]
0x140068ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140068ee8  mov     eax, edi
0x140068eea  lock xadd [rbx+0Ch], eax
0x140068eef  add     eax, edi
0x140068ef1  jnz     short loc_140068F03
0x140068ef3  mov     rax, [rbx]
0x140068ef6  mov     rcx, rbx
0x140068ef9  mov     rax, [rax+8]
0x140068efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140068f02  nop
0x140068f03  lea     rcx, [rsp+358h+var_E0]
0x140068f0b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140068f10  nop
0x140068f11  lea     rcx, [rsp+358h+var_B8]; this
0x140068f19  call    ??1ScopeTracker@Uev@@UEAA@XZ; Uev::ScopeTracker::~ScopeTracker(void)
0x140068f1e  mov     rcx, [rsp+358h+var_38]
0x140068f26  xor     rcx, rsp; StackCookie
0x140068f29  call    __security_check_cookie
0x140068f2e  add     rsp, 330h
0x140068f35  pop     r15
0x140068f37  pop     r14
0x140068f39  pop     rdi
0x140068f3a  pop     rsi
0x140068f3b  pop     rbx
0x140068f3c  retn
0x140068f3d  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140068f42  nop
0x140068f43  mov     edx, 8
0x140068f48  mov     rcx, rax
0x140068f4b  call    ?WriteEnabled@Log@Uev@@QEBA_NW4UEV_LOG_LEVEL@2@@Z; Uev::Log::WriteEnabled(Uev::UEV_LOG_LEVEL)
0x140068f50  test    al, al
0x140068f52  jz      loc_140068FEC
0x140068f58  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140068f5d  mov     rbx, rax
0x140068f60  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140068f65  lea     rdx, aBackupprofileG_1; "BackupProfile::GetSettingsStoragePathFo"...
0x140068f6c  lea     rcx, [rsp+358h+var_E0]
0x140068f74  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140068f79  nop
0x140068f7a  lea     r8, [rsp+358h+var_E0]
0x140068f82  lea     rdx, [rsp+358h+var_1F8]
0x140068f8a  call    ?fmt@Log@Uev@@QEAA?AV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::Log::fmt(std::wstring const &)
0x140068f8f  nop
0x140068f90  lea     rdx, [rsp+358h+var_E8]
0x140068f98  mov     rcx, rax
0x140068f9b  call    ??$?LJ@?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@QEAAAEAV01@AEBJ@Z; boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator%<long>(long const &)
0x140068fa0  mov     rdi, rax
0x140068fa3  lea     rdx, aUevcommon; "UevCommon"
0x140068faa  lea     rcx, [rsp+358h+var_328]
0x140068faf  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140068fb4  nop
0x140068fb5  mov     r9, rdi
0x140068fb8  lea     r8, [rsp+358h+var_328]
0x140068fbd  mov     rcx, rbx
0x140068fc0  call    ?Write@Log@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@@Z; Uev::Log::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)
0x140068fc5  nop
0x140068fc6  lea     rcx, [rsp+358h+var_328]; this
0x140068fcb  call    ??1path@filesystem@boost@@QEAA@XZ; boost::filesystem::path::~path(void)
0x140068fd0  nop
0x140068fd1  lea     rcx, [rsp+358h+var_1F8]
0x140068fd9  call    ??1?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@QEAA@XZ; boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x140068fde  nop
0x140068fdf  lea     rcx, [rsp+358h+var_E0]; this
0x140068fe7  call    ??1path@filesystem@boost@@QEAA@XZ; boost::filesystem::path::~path(void)
0x140068fec  lea     rdx, aSettingsStorag; "Settings storage path has not been conf"...
0x140068ff3  lea     rcx, [rsp+358h+var_328]
0x140068ff8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140068ffd  nop
0x140068ffe  lea     rdx, [rsp+358h+var_328]
0x140069003  lea     rcx, [rsp+358h+pExceptionObject]
0x14006900b  call    ??0UevException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::UevException::UevException(std::wstring const &)
0x140069010  lea     rdx, _TI2?AVUevException@Uev@@; pThrowInfo
0x140069017  lea     rcx, [rsp+358h+pExceptionObject]; pExceptionObject
0x14006901f  call    _CxxThrowException_0
0x140069025  lea     rdx, aCouldNotRetrie_0; "Could not retrieve SyncProviderName set"...
0x14006902c  lea     rcx, [rsp+358h+var_328]
0x140069031  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140069036  nop
0x140069037  lea     rdx, [rsp+358h+var_328]
0x14006903c  lea     rcx, [rsp+358h+var_2B8]
0x140069044  call    ??0UevException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::UevException::UevException(std::wstring const &)
0x140069049  lea     rdx, _TI2?AVUevException@Uev@@; pThrowInfo
0x140069050  lea     rcx, [rsp+358h+var_2B8]; pExceptionObject
0x140069058  call    _CxxThrowException_0
```
