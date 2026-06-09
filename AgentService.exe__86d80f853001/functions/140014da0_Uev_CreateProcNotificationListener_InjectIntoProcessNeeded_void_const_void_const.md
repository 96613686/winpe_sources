# Uev::CreateProcNotificationListener::InjectIntoProcessNeeded(void * const,void * const)

- ea: `0x140014da0`
- end: `0x140015189`
- name: `?InjectIntoProcessNeeded@CreateProcNotificationListener@Uev@@AEAA_NQEAX0@Z`
- size: `1001`
- prototype: `char __fastcall(Uev::CreateProcNotificationListener *this, void *const, void *const)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140015630`

## callees

- `0x140003e50`
- `0x140003e74`
- `0x140004ab4`
- `0x14000ac28`
- `0x14000ac88`
- `0x14000ba60`
- `0x14000c2b8`
- `0x14000d1d8`
- `0x14000d260`
- `0x14000d5ac`
- `0x14000ed2c`
- `0x14000f074`
- `0x140010a70`
- `0x1400133e4`
- `0x140014a10`
- `0x140014da0`
- `0x140015190`
- `0x1400189fc`
- `0x14001a9c8`
- `0x14001acd8`
- `0x14001b48c`
- `0x14001b6a8`
- `0x1400245f0`
- `0x140069ae4`
- `0x1400754cc`
- `0x14009b010`

## string_xrefs

- `0x140015149`: `Attempting to use an invalid handle.`
- `0x140014dd3`: `AgentService.CreateProcNotificationListener::InjectIntoProcessNeeded: Entry`
- `0x140014f3e`: `AgentService.CreateProcNotificationListener::InjectIntoProcessNeeded: Failed to read syncEnabled from registry. Defaulting to enabled. Error code: %1%`
- `0x14001508a`: `AgentService.CreateProcNotificationListener::InjectIntoProcessNeeded: Process has been identified as a monitored program.`
- `0x1400150a7`: `AgentService.CreateProcNotificationListener::InjectIntoProcessNeeded: Process has been identified as the Shell.`
- `0x14001510c`: `AgentService.CreateProcNotificationListener::InjectIntoProcessNeeded: Exit, retVal = 0x%X`
- `0x140014ff4`: `AgentService.Util::IsLowIntegrityProcess: Entry`
- `0x14001501b`: `AgentService.Util::IsLowIntegrityProcess: Exit, retVal = 0x%X`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Uev::CreateProcNotificationListener::InjectIntoProcessNeeded(
        Uev::CreateProcNotificationListener *this,
        void *const a2,
        void *const a3)
{
  HKEY v5; // rbx
  Uev::Configuration *v6; // rsi
  Uev::ConfigUtil *v7; // rax
  __int64 v8; // rdi
  _DWORD *v9; // rax
  __int64 v10; // rsi
  void *v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  _QWORD *v15; // rax
  unsigned int ProcessIntegrityLevel; // eax
  char v17; // si
  __int128 *v18; // rcx
  const wchar_t *v19; // rcx
  __int64 v21; // rcx
  __int64 v22; // rbx
  _OWORD *v23; // rcx
  __int64 v24; // rax
  _QWORD *v25; // rax
  __int64 v26; // rax
  __int64 v27; // r8
  __int64 v28; // rcx
  __int64 v29; // rbx
  __int128 *v30; // rdx
  char *v31; // r8
  __int128 *v32; // rdx
  __int64 v33; // rax
  _QWORD *v34; // rax
  char v35; // [rsp+20h] [rbp-258h]
  HKEY v36; // [rsp+30h] [rbp-248h] BYREF
  HKEY *v37; // [rsp+38h] [rbp-240h] BYREF
  void (*v38)(void); // [rsp+40h] [rbp-238h]
  __int64 (__fastcall *v39)(); // [rsp+48h] [rbp-230h]
  HKEY v40; // [rsp+50h] [rbp-228h] BYREF
  HKEY v41; // [rsp+58h] [rbp-220h] BYREF
  _OWORD v42[2]; // [rsp+60h] [rbp-218h] BYREF
  _BYTE v43[32]; // [rsp+80h] [rbp-1F8h] BYREF
  Uev::UevException *v44; // [rsp+A0h] [rbp-1D8h] BYREF
  const std::exception *v45; // [rsp+A8h] [rbp-1D0h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+B0h] [rbp-1C8h] BYREF
  _BYTE v47[272]; // [rsp+F0h] [rbp-188h] BYREF
  char v48[16]; // [rsp+200h] [rbp-78h] BYREF
  __int128 v49; // [rsp+210h] [rbp-68h] BYREF
  __int64 v50; // [rsp+220h] [rbp-58h]
  unsigned __int64 v51; // [rsp+228h] [rbp-50h]
  __int128 v52; // [rsp+230h] [rbp-48h] BYREF
  __int64 v53; // [rsp+240h] [rbp-38h]
  unsigned __int64 v54; // [rsp+248h] [rbp-30h]
  __int64 v55; // [rsp+250h] [rbp-28h] BYREF

  v35 = 0;
  DbgTrace<5>(L"AgentService.CreateProcNotificationListener::InjectIntoProcessNeeded: Entry");
  try
  {
    v5 = Uev::Util::OpenUserHive(a3);
    v36 = v5;
    v6 = (Uev::Configuration *)operator new(0x5400u);
    *(_QWORD *)&v42[0] = v6;
    v7 = (Uev::ConfigUtil *)operator new(0x118u);
    if ( !v5 )
    {
      std::wstring::wstring(&v52, L"Attempting to use an invalid handle.");
      Uev::SmartHandleException::SmartHandleException(pExceptionObject, &v52);
      throw (Uev::SmartHandleException *)pExceptionObject;
    }
    v41 = v5;
    v40 = HKEY_LOCAL_MACHINE;
    v8 = Uev::ConfigUtil::ConfigUtil(v7, &v40, &v41);
    v49 = 0;
    v9 = operator new(0x18u);
    v9[2] = 1;
    v9[3] = 1;
    *(_QWORD *)v9 = &std::_Ref_count<Uev::ConfigUtil>::`vftable';
    *((_QWORD *)v9 + 2) = v8;
    *(_QWORD *)&v49 = v8;
    *((_QWORD *)&v49 + 1) = v9;
    v10 = Uev::Configuration::Configuration(v6);
    v42[0] = 0;
    v11 = operator new(0x18u);
    *((_DWORD *)v11 + 2) = 1;
    *((_DWORD *)v11 + 3) = 1;
    *(_QWORD *)v11 = &std::_Ref_count<Uev::Configuration>::`vftable';
    *((_QWORD *)v11 + 2) = v10;
    *(_QWORD *)&v42[0] = v10;
    *((_QWORD *)&v42[0] + 1) = v11;
    v48[0] = 0;
    v55 = 0;
    if ( !(unsigned __int8)Uev::Setting<bool>::Get(v10 + 576, v48, &v55) )
    {
      Uev::Singleton<Uev::Log,Uev::Log>::Instance();
      v52 = 0;
      v53 = 0;
      v54 = 0;
      std::wstring::_Construct<1,wchar_t *>(
        &v52,
        L"AgentService.CreateProcNotificationListener::InjectIntoProcessNeeded: Failed to read syncEnabled from registry. "
         "Defaulting to enabled. Error code: %1%",
        150);
      v13 = Uev::Log::fmt(v12, v47, &v52);
      v37 = (HKEY *)&v55;
      v38 = boost::on_process_enter;
      v39 = boost::io::detail::call_put_last<wchar_t,std::char_traits<wchar_t>,long const>;
      v14 = boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(
              v13,
              &v37);
      v15 = (_QWORD *)boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v14, v43);
      if ( v15[3] > 7u )
        v15 = (_QWORD *)*v15;
      DbgTrace<2>(v15);
      std::wstring::_Tidy_deallocate(v43);
      boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v47);
      std::wstring::_Tidy_deallocate(&v52);
    }
    if ( !v48[0] )
      goto LABEL_20;
    DbgTrace<5>(L"AgentService.Util::IsLowIntegrityProcess: Entry");
    ProcessIntegrityLevel = Uev::Util::GetProcessIntegrityLevel(a3);
    if ( ProcessIntegrityLevel <= 1 || (v17 = 0, ProcessIntegrityLevel == 5) )
      v17 = 1;
    DbgTraceFrmt<5,bool>((wchar_t *)L"AgentService.Util::IsLowIntegrityProcess: Exit, retVal = 0x%X");
    if ( v17 )
      goto LABEL_20;
    Uev::Util::GetFullProcessImageName(&v52, a2);
    v49 = 0;
    _InterlockedIncrement((volatile signed __int32 *)v11 + 2);
    v49 = v42[0];
    v18 = &v52;
    if ( v54 > 7 )
      v18 = (__int128 *)v52;
    if ( (unsigned __int8)Uev::Util::CheckForMatchingApplicationTemplate<Uev::TemplateFactory,Uev::ProgramCharacteristicsHelper>(
                            v18,
                            &v49) )
    {
      v19 = L"AgentService.CreateProcNotificationListener::InjectIntoProcessNeeded: Process has been identified as a monitored program.";
    }
    else
    {
      if ( !(unsigned __int8)Uev::Util::IsProcessTheShell(&v52, v5) )
      {
LABEL_19:
        std::wstring::_Tidy_deallocate(&v52);
LABEL_20:
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(void *))v11)(v11);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 8LL))(v11);
        }
        Uev::SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>(&v36);
        goto LABEL_41;
      }
      v19 = L"AgentService.CreateProcNotificationListener::InjectIntoProcessNeeded: Process has been identified as the Shell.";
    }
    DbgTrace<5>(v19);
    v35 = 1;
    goto LABEL_19;
  }
  catch ( Uev::UevException *v44 )
  {
    Uev::Singleton<Uev::Log,Uev::Log>::Instance();
    v52 = 0;
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t *>(
      &v52,
      L"AgentService.CreateProcNotificationListener::InjectIntoProcessNeeded: UevException occurred: %1%",
      96);
    v22 = Uev::Log::fmt(v21, v47, &v52);
    std::wstring::wstring(&v49, (char *)v44 + 24);
    v23 = &v49;
    if ( v51 > 7 )
      v23 = (_OWORD *)v49;
    v36 = (HKEY)v23;
    v37 = &v36;
    v38 = boost::on_process_enter;
    v39 = boost::io::detail::call_put_last<wchar_t,std::char_traits<wchar_t>,wchar_t const * const>;
    v24 = boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(
            v22,
            &v37);
    v25 = (_QWORD *)boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v24, v43);
    if ( v25[3] > 7u )
      v25 = (_QWORD *)*v25;
    DbgTrace<2>(v25);
    std::wstring::_Tidy_deallocate(v43);
    std::wstring::_Tidy_deallocate(&v49);
    boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v47);
    std::wstring::_Tidy_deallocate(&v52);
  }
  catch ( const std::exception *v45 )
  {
    v26 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v45 + 8LL))(v45);
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v27 = -1;
    do
      ++v27;
    while ( *(_BYTE *)(v26 + v27) );
    std::string::_Construct<1,char const *>(&v49, v26);
    Uev::Singleton<Uev::Log,Uev::Log>::Instance();
    v52 = 0;
    v53 = 0;
    v54 = 0;
    std::wstring::_Construct<1,wchar_t *>(
      &v52,
      L"AgentService.CreateProcNotificationListener::InjectIntoProcessNeeded: std::exception occurred: %1%",
      98);
    v29 = Uev::Log::fmt(v28, v47, &v52);
    v30 = &v49;
    if ( v51 > 0xF )
      v30 = (__int128 *)v49;
    v31 = (char *)v30 + v50;
    v32 = &v49;
    if ( v51 > 0xF )
      v32 = (__int128 *)v49;
    v37 = (HKEY *)std::wstring::wstring(v42, v32, v31);
    v38 = boost::on_process_enter;
    v39 = std::operator<<<wchar_t>;
    v33 = boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(
            v29,
            &v37);
    v34 = (_QWORD *)boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v33, v43);
    if ( v34[3] > 7u )
      v34 = (_QWORD *)*v34;
    DbgTrace<2>(v34);
    std::wstring::_Tidy_deallocate(v43);
    std::wstring::_Tidy_deallocate(v42);
    boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v47);
    std::wstring::_Tidy_deallocate(&v52);
    std::string::_Tidy_deallocate(&v49);
  }
  catch ( ... )
  {
    DbgTrace<2>(L"AgentService.CreateProcNotificationListener::InjectIntoProcessNeeded: Unrecognized exception occurred");
  }
LABEL_41:
  DbgTraceFrmt<5,bool>((wchar_t *)L"AgentService.CreateProcNotificationListener::InjectIntoProcessNeeded: Exit, retVal = 0x%X");
  return v35;
}

```

## disassembly

```asm
0x140014da0  mov     [rsp+arg_0], rbx
0x140014da5  mov     [rsp+arg_18], rsi
0x140014daa  push    rdi
0x140014dab  push    r14
0x140014dad  push    r15
0x140014daf  sub     rsp, 260h
0x140014db6  mov     rax, cs:__security_cookie
0x140014dbd  xor     rax, rsp
0x140014dc0  mov     [rsp+278h+var_20], rax
0x140014dc8  mov     r14, r8
0x140014dcb  mov     r15, rdx
0x140014dce  mov     [rsp+278h+var_258], 0
0x140014dd3  lea     rcx, aAgentserviceCr_35; "AgentService.CreateProcNotificationList"...
0x140014dda  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x140014ddf  nop
0x140014de0  mov     rcx, r14; void *
0x140014de3  call    ?OpenUserHive@Util@Uev@@SAPEAUHKEY__@@PEAX@Z; Uev::Util::OpenUserHive(void *)
0x140014de8  mov     rbx, rax
0x140014deb  mov     [rsp+278h+var_248], rax
0x140014df0  mov     ecx, 5400h; Size
0x140014df5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140014dfa  mov     rsi, rax
0x140014dfd  mov     qword ptr [rsp+278h+var_218], rax
0x140014e02  mov     ecx, 118h; Size
0x140014e07  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140014e0c  mov     [rsp+278h+var_250], rax
0x140014e11  test    rbx, rbx
0x140014e14  jz      loc_140015149
0x140014e1a  mov     [rsp+278h+var_220], rbx
0x140014e1f  mov     [rsp+278h+var_228], 0FFFFFFFF80000002h
0x140014e28  lea     r8, [rsp+278h+var_220]; HKEY *
0x140014e2d  lea     rdx, [rsp+278h+var_228]; HKEY *
0x140014e32  mov     rcx, rax; this
0x140014e35  call    ??0ConfigUtil@Uev@@QEAA@AEBQEAUHKEY__@@0@Z; Uev::ConfigUtil::ConfigUtil(HKEY__ * const &,HKEY__ * const &)
0x140014e3a  mov     rdi, rax
0x140014e3d  xorps   xmm0, xmm0
0x140014e40  movdqu  [rsp+278h+var_68], xmm0
0x140014e49  mov     [rsp+278h+var_250], rax
0x140014e4e  mov     ecx, 18h; Size
0x140014e53  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140014e58  mov     dword ptr [rax+8], 1
0x140014e5f  mov     dword ptr [rax+0Ch], 1
0x140014e66  lea     rcx, ??_7?$_Ref_count@VConfigUtil@Uev@@@std@@6B@; const std::_Ref_count<Uev::ConfigUtil>::`vftable'
0x140014e6d  mov     [rax], rcx
0x140014e70  mov     [rax+10h], rdi
0x140014e74  mov     qword ptr [rsp+278h+var_68], rdi
0x140014e7c  mov     qword ptr [rsp+278h+var_68+8], rax
0x140014e84  lea     rdx, [rsp+278h+var_68]
0x140014e8c  mov     rcx, rsi; this
0x140014e8f  call    ??0Configuration@Uev@@QEAA@V?$shared_ptr@VConfigUtil@Uev@@@std@@@Z; Uev::Configuration::Configuration(std::shared_ptr<Uev::ConfigUtil>)
0x140014e94  mov     rsi, rax
0x140014e97  xorps   xmm0, xmm0
0x140014e9a  movdqa  [rsp+278h+var_218], xmm0
0x140014ea0  mov     [rsp+278h+var_250], rax
0x140014ea5  mov     ecx, 18h; Size
0x140014eaa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140014eaf  mov     rdi, rax
0x140014eb2  mov     dword ptr [rax+8], 1
0x140014eb9  mov     dword ptr [rax+0Ch], 1
0x140014ec0  lea     rax, ??_7?$_Ref_count@VConfiguration@Uev@@@std@@6B@; const std::_Ref_count<Uev::Configuration>::`vftable'
0x140014ec7  mov     [rdi], rax
0x140014eca  mov     [rdi+10h], rsi
0x140014ece  mov     qword ptr [rsp+278h+var_218], rsi
0x140014ed3  mov     qword ptr [rsp+278h+var_218+8], rdi
0x140014ed8  mov     [rsp+278h+var_78], 0
0x140014ee0  mov     [rsp+278h+var_28], 0
0x140014eec  lea     rcx, [rsi+240h]
0x140014ef3  lea     r8, [rsp+278h+var_28]
0x140014efb  lea     rdx, [rsp+278h+var_78]
0x140014f03  call    ?Get@?$Setting@_N@Uev@@QEBA_NAEA_NAEAUSettingInfo@2@@Z; Uev::Setting<bool>::Get(bool &,Uev::SettingInfo &)
0x140014f08  test    al, al
0x140014f0a  jnz     loc_140014FE6
0x140014f10  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140014f15  xorps   xmm0, xmm0
0x140014f18  movups  [rsp+278h+var_48], xmm0
0x140014f20  mov     [rsp+278h+var_38], 0
0x140014f2c  mov     [rsp+278h+var_30], 0
0x140014f38  mov     r8d, 96h
0x140014f3e  lea     rdx, aAgentserviceCr_5; "AgentService.CreateProcNotificationList"...
0x140014f45  lea     rcx, [rsp+278h+var_48]
0x140014f4d  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140014f52  nop
0x140014f53  lea     r8, [rsp+278h+var_48]
0x140014f5b  lea     rdx, [rsp+278h+var_188]
0x140014f63  call    ?fmt@Log@Uev@@QEAA?AV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::Log::fmt(std::wstring const &)
0x140014f68  nop
0x140014f69  lea     rcx, [rsp+278h+var_28]
0x140014f71  mov     [rsp+278h+var_240], rcx
0x140014f76  lea     rcx, ?on_process_enter@boost@@YAXXZ; boost::on_process_enter(void)
0x140014f7d  mov     [rsp+278h+var_238], rcx
0x140014f82  lea     rcx, ??$call_put_last@_WU?$char_traits@_W@std@@$$CBJ@detail@io@boost@@YAXAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@std@@PEBX@Z; boost::io::detail::call_put_last<wchar_t,std::char_traits<wchar_t>,long const>(std::wostream &,void const *)
0x140014f89  mov     [rsp+278h+var_230], rcx
0x140014f8e  lea     rdx, [rsp+278h+var_240]
0x140014f93  mov     rcx, rax
0x140014f96  call    ??$feed_impl@_WU?$char_traits@_W@std@@V?$allocator@_W@2@AEBU?$put_holder@_WU?$char_traits@_W@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@AEAV32@AEBU?$put_holder@_WU?$char_traits@_W@std@@@012@@Z; boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &)
0x140014f9b  lea     rdx, [rsp+278h+var_1F8]
0x140014fa3  mov     rcx, rax
0x140014fa6  call    ?str@?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(void)
0x140014fab  cmp     qword ptr [rax+18h], 7
0x140014fb0  jbe     short loc_140014FB5
0x140014fb2  mov     rax, [rax]
0x140014fb5  mov     rcx, rax
0x140014fb8  call    ??$DbgTrace@$01@@YAXPEB_W@Z; DbgTrace<2>(wchar_t const *)
0x140014fbd  lea     rcx, [rsp+278h+var_1F8]
0x140014fc5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140014fca  nop
0x140014fcb  lea     rcx, [rsp+278h+var_188]
0x140014fd3  call    ??1?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@QEAA@XZ; boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x140014fd8  nop
0x140014fd9  lea     rcx, [rsp+278h+var_48]
0x140014fe1  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140014fe6  cmp     [rsp+278h+var_78], 0
0x140014fee  jz      loc_1400150C6
0x140014ff4  lea     rcx, aAgentserviceUt_20; "AgentService.Util::IsLowIntegrityProces"...
0x140014ffb  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x140015000  mov     rcx, r14
0x140015003  call    ?GetProcessIntegrityLevel@Util@Uev@@SA?AW4ProcessIntegrityLevel@12@PEAX@Z; Uev::Util::GetProcessIntegrityLevel(void *)
0x140015008  cmp     eax, 1
0x14001500b  jbe     short loc_140015015
0x14001500d  xor     sil, sil
0x140015010  cmp     eax, 5
0x140015013  jnz     short loc_140015018
0x140015015  mov     sil, 1
0x140015018  mov     dl, sil
0x14001501b  lea     rcx, aAgentserviceUt_25; "AgentService.Util::IsLowIntegrityProces"...
0x140015022  call    ??$DbgTraceFrmt@$04_N@@YAXPEB_W_N@Z; DbgTraceFrmt<5,bool>(wchar_t const *,bool)
0x140015027  test    sil, sil
0x14001502a  jnz     loc_1400150C6
0x140015030  mov     rdx, r15
0x140015033  lea     rcx, [rsp+278h+var_48]
0x14001503b  call    ?GetFullProcessImageName@Util@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAXK@Z; Uev::Util::GetFullProcessImageName(void *,ulong)
0x140015040  nop
0x140015041  xorps   xmm0, xmm0
0x140015044  movdqa  [rsp+278h+var_68], xmm0
0x14001504d  lock inc dword ptr [rdi+8]
0x140015051  movaps  xmm0, [rsp+278h+var_218]
0x140015056  movdqa  [rsp+278h+var_68], xmm0
0x14001505f  lea     rcx, [rsp+278h+var_48]
0x140015067  cmp     [rsp+278h+var_30], 7
0x140015070  cmova   rcx, qword ptr [rsp+278h+var_48]
0x140015079  lea     rdx, [rsp+278h+var_68]
0x140015081  call    ??$CheckForMatchingApplicationTemplate@VTemplateFactory@Uev@@VProgramCharacteristicsHelper@2@@Util@Uev@@SA_NPEB_WV?$shared_ptr@VConfiguration@Uev@@@std@@@Z; Uev::Util::CheckForMatchingApplicationTemplate<Uev::TemplateFactory,Uev::ProgramCharacteristicsHelper>(wchar_t const *,std::shared_ptr<Uev::Configuration>)
0x140015086  test    al, al
0x140015088  jz      short loc_140015093
0x14001508a  lea     rcx, aAgentserviceCr_17; "AgentService.CreateProcNotificationList"...
0x140015091  jmp     short loc_1400150AE
0x140015093  mov     rdx, rbx
0x140015096  lea     rcx, [rsp+278h+var_48]
0x14001509e  call    ?IsProcessTheShell@Util@Uev@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHKEY__@@@Z; Uev::Util::IsProcessTheShell(std::wstring const &,HKEY__ *)
0x1400150a3  test    al, al
0x1400150a5  jz      short loc_1400150B8
0x1400150a7  lea     rcx, aAgentserviceCr_29; "AgentService.CreateProcNotificationList"...
0x1400150ae  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x1400150b3  mov     [rsp+278h+var_258], 1
0x1400150b8  lea     rcx, [rsp+278h+var_48]
0x1400150c0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400150c5  nop
0x1400150c6  or      ebx, 0FFFFFFFFh
0x1400150c9  mov     eax, ebx
0x1400150cb  lock xadd [rdi+8], eax
0x1400150d0  add     eax, ebx
0x1400150d2  jnz     short loc_1400150FD
0x1400150d4  mov     rax, [rdi]
0x1400150d7  mov     rcx, rdi
0x1400150da  mov     rax, [rax]
0x1400150dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400150e2  mov     eax, ebx
0x1400150e4  lock xadd [rdi+0Ch], eax
0x1400150e9  add     eax, ebx
0x1400150eb  jnz     short loc_1400150FD
0x1400150ed  mov     rax, [rdi]
0x1400150f0  mov     rcx, rdi
0x1400150f3  mov     rax, [rax+8]
0x1400150f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400150fc  nop
0x1400150fd  lea     rcx, [rsp+278h+var_248]
0x140015102  call    ??1?$SmartHandle@PEAUHKEY__@@$1?RegCloseKeyWrapper@Uev@@YAXPEAU1@@Z$0A@@Uev@@QEAA@XZ; Uev::SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>(void)
0x140015107  nop
0x140015108  mov     dl, [rsp+278h+var_258]
0x14001510c  lea     rcx, aAgentserviceCr_43; "AgentService.CreateProcNotificationList"...
0x140015113  call    ??$DbgTraceFrmt@$04_N@@YAXPEB_W_N@Z; DbgTraceFrmt<5,bool>(wchar_t const *,bool)
0x140015118  mov     al, [rsp+278h+var_258]
0x14001511c  mov     rcx, [rsp+278h+var_20]
0x140015124  xor     rcx, rsp; StackCookie
0x140015127  call    __security_check_cookie
0x14001512c  lea     r11, [rsp+278h+var_18]
0x140015134  mov     rbx, [r11+20h]
0x140015138  mov     rsi, [r11+38h]
0x14001513c  mov     rsp, r11
0x14001513f  pop     r15
0x140015141  pop     r14
0x140015143  pop     rdi
0x140015144  retn
0x140015145  jmp     short loc_140015108
0x140015147  jmp     short loc_140015108
0x140015149  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x140015150  lea     rcx, [rsp+278h+var_48]
0x140015158  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14001515d  nop
0x14001515e  lea     rdx, [rsp+278h+var_48]
0x140015166  lea     rcx, [rsp+278h+pExceptionObject]
0x14001516e  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x140015173  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x14001517a  lea     rcx, [rsp+278h+pExceptionObject]; pExceptionObject
0x140015182  call    _CxxThrowException_0
```
