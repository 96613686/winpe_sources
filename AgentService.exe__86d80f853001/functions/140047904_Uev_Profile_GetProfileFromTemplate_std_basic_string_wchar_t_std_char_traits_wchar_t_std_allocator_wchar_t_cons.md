# Uev::Profile::GetProfileFromTemplate(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,Uev::SettingInfo &)

- ea: `0x140047904`
- end: `0x140047f98`
- name: `?GetProfileFromTemplate@Profile@Uev@@SA?AV?$shared_ptr@VProfile@Uev@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@AEAUSettingInfo@2@@Z`
- size: `1684`
- prototype: ``
- caller_count: `3`
- callee_count: `28`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14003c290`
- `0x140041980`
- `0x140047564`

## callees

- `0x140003e50`
- `0x140004ab4`
- `0x14000afc0`
- `0x14000ba60`
- `0x14000bae4`
- `0x14000c2b8`
- `0x14000d1d8`
- `0x14000ec5c`
- `0x140010a70`
- `0x1400133e4`
- `0x140015190`
- `0x140020568`
- `0x140023dd4`
- `0x140023e54`
- `0x1400245f0`
- `0x14003eb10`
- `0x1400469c8`
- `0x140046a4c`
- `0x140046cf0`
- `0x140046ddc`
- `0x140046e04`
- `0x140046f94`
- `0x1400473b0`
- `0x140047904`
- `0x140048198`
- `0x140067210`
- `0x14006729c`
- `0x14009b010`

## string_xrefs

- `0x140047951`: `UevCommon`
- `0x140047bee`: `UevCommon`
- `0x140047d94`: `UevCommon`
- `0x14004794a`: `Profile::GetProfileFromTemplate()`
- `0x140047e27`: `Template::GetProfile() - Template is assigned to multiple profiles. Error = %1%.`
- `0x140047e91`: `Failed to get template list`
- `0x140047b66`: `Template::GetProfile() - Found profile %1% for template %2%.`
- `0x140047cfd`: `Template::GetProfile() - Defaulting to profile %1% for template %2%.`
- `0x140047ee3`: `Template::GetProfile() - Failed to get the list of profiles. Error = %1%.`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
_QWORD *__fastcall Uev::Profile::GetProfileFromTemplate(_QWORD *a1, __int64 a2, unsigned int *a3)
{
  __m128i si128; // xmm6
  __int64 *v7; // rax
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 *v11; // rax
  __int64 *v12; // rax
  __int64 v13; // rsi
  __int64 v14; // r15
  volatile signed __int32 *v15; // rdi
  void (__fastcall ***v16)(_QWORD, __int64); // rcx
  __int64 v17; // rcx
  __int64 v18; // rdi
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rbx
  __int64 v24; // rdx
  __int128 *v25; // rcx
  __int64 *v26; // rax
  __int64 *v27; // rax
  volatile signed __int32 *v28; // rdi
  void (__fastcall ***v29)(_QWORD, __int64); // rcx
  __int64 v30; // rcx
  __int64 v31; // rdi
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rbx
  __int64 v35; // rax
  __int64 v36; // rbx
  __int64 v37; // rdx
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rdi
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rbx
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // r9
  __int64 v51; // rdi
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rbx
  __int64 v56; // rdx
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // rcx
  void (__fastcall ***v60)(_QWORD, __int64); // [rsp+28h] [rbp-E0h] BYREF
  __int128 v61; // [rsp+30h] [rbp-D8h] BYREF
  __int128 v62; // [rsp+40h] [rbp-C8h]
  __int128 v63; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v64; // [rsp+60h] [rbp-A8h]
  __int128 v65; // [rsp+70h] [rbp-98h]
  _OWORD pExceptionObject[4]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v67[4]; // [rsp+C8h] [rbp-40h] BYREF
  _BYTE v68[272]; // [rsp+E8h] [rbp-20h] BYREF
  _OWORD v69[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  _OWORD v70[2]; // [rsp+218h] [rbp+110h] BYREF
  _BYTE v71[128]; // [rsp+238h] [rbp+130h] BYREF

  v60 = (void (__fastcall ***)(_QWORD, __int64))a1;
  Uev::ScopeTracker::ScopeTracker((Uev::ScopeTracker *)v71, L"UevCommon", L"Profile::GetProfileFromTemplate()");
  v69[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v69[1] = si128;
  LOWORD(v69[0]) = 0;
  (*(void (__fastcall **)(__int64, __int64, _OWORD *))(*(_QWORD *)Uev::Profile::s_templateAdministrator + 96LL))(
    Uev::Profile::s_templateAdministrator,
    a2,
    v69);
  if ( !(unsigned __int8)std::operator!=<wchar_t>(v69, &Data) )
  {
    v65 = 0;
    v70[0] = 0;
    v70[1] = si128;
    LOWORD(v70[0]) = 0;
    v9 = Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance();
    if ( !(unsigned __int8)Uev::SettingGroup<std::wstring>::Get(v9 + 9904, a2, v70, a3) || *a3 )
    {
      if ( *a3 != 2 )
      {
        if ( *a3 == 183 )
        {
          v38 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v10);
          if ( (unsigned __int8)Uev::Log::WriteEnabled(v38, 8) )
          {
            v40 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v39);
            Uev::Singleton<Uev::Log,Uev::Log>::Instance(v41);
            std::wstring::wstring(
              &v63,
              L"Template::GetProfile() - Template is assigned to multiple profiles. Error = %1%.");
            v43 = Uev::Log::fmt(v42, v68, &v63);
            v44 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator%<long>(
                    v43,
                    a3);
            std::wstring::wstring(pExceptionObject, L"UevCommon");
            Uev::Log::Write(v40, v45, pExceptionObject, v44);
            boost::filesystem::path::~path((boost::filesystem::path *)pExceptionObject);
            boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v68);
            boost::filesystem::path::~path((boost::filesystem::path *)&v63);
          }
          std::wstring::wstring(v67, L"Failed to get template list");
          Uev::AssociatedTemplateException::AssociatedTemplateException(pExceptionObject, (__int64)v67);
          throw (Uev::AssociatedTemplateException *)pExceptionObject;
        }
        v46 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v10);
        if ( (unsigned __int8)Uev::Log::WriteEnabled(v46, 8) )
        {
          v51 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v48);
          Uev::Singleton<Uev::Log,Uev::Log>::Instance(v52);
          std::wstring::wstring(&v63, L"Template::GetProfile() - Failed to get the list of profiles. Error = %1%.");
          v54 = Uev::Log::fmt(v53, v68, &v63);
          v55 = boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::operator%<long>(v54, a3);
          std::wstring::wstring(pExceptionObject, L"UevCommon");
          Uev::Log::Write(v51, v56, pExceptionObject, v55);
          boost::filesystem::path::~path((boost::filesystem::path *)pExceptionObject);
          boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v68);
          boost::filesystem::path::~path((boost::filesystem::path *)&v63);
        }
        if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 4) != 0 )
        {
          v57 = std::wstring::c_str(a2, v47, v49, v50);
          McTemplateU0dz_EventWriteTransfer(v59, v58, *a3, v57);
        }
        std::wstring::wstring(v67, L"Failed to get the list of profiles");
        Uev::ProfileConfigurationException::ProfileConfigurationException(pExceptionObject, (__int64)v67);
        throw (Uev::ProfileConfigurationException *)pExceptionObject;
      }
      v26 = (__int64 *)Uev::ProfileFactory::CreateProfile(&v60, 1);
      v27 = std::shared_ptr<Uev::Profile>::shared_ptr<Uev::Profile>(&v61, v26);
      v13 = *v27;
      v14 = v27[1];
      *v27 = 0;
      v27[1] = 0;
      *(_QWORD *)&v65 = v13;
      *((_QWORD *)&v65 + 1) = v14;
      v28 = (volatile signed __int32 *)*((_QWORD *)&v61 + 1);
      if ( *((_QWORD *)&v61 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v61 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
          if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
        }
      }
      v29 = v60;
      if ( v60 )
        (**v60)(v60, 1);
      if ( (*(_BYTE *)(*(_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(v29) + 32LL) & 8) == 0 )
        goto LABEL_25;
      v31 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v30);
      Uev::Singleton<Uev::Log,Uev::Log>::Instance(v32);
      memset(pExceptionObject, 0, 32);
      std::wstring::_Construct<1,wchar_t *>(
        pExceptionObject,
        L"Template::GetProfile() - Defaulting to profile %1% for template %2%.",
        0x44u);
      v34 = Uev::Log::fmt(v33, v68, pExceptionObject);
      *(_QWORD *)&v61 = Uev::Profile::ToString(v67, 1);
      *((_QWORD *)&v61 + 1) = boost::on_process_enter;
      *(_QWORD *)&v62 = std::operator<<<wchar_t>;
      v35 = boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(
              v34,
              &v61);
      *(_QWORD *)&v61 = a2;
      *((_QWORD *)&v61 + 1) = boost::on_process_enter;
      *(_QWORD *)&v62 = std::operator<<<wchar_t>;
      v36 = boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(
              v35,
              &v61);
      v63 = 0;
      v64 = 0;
      std::wstring::_Construct<1,wchar_t *>(&v63, L"UevCommon", 9u);
      Uev::Log::Write(v31, v37, &v63, v36);
      std::wstring::_Tidy_deallocate(&v63);
      std::wstring::_Tidy_deallocate(v67);
      boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v68);
      v25 = pExceptionObject;
    }
    else
    {
      v11 = (__int64 *)Uev::ProfileFactory::CreateProfile(&v60, v70);
      v12 = std::shared_ptr<Uev::Profile>::shared_ptr<Uev::Profile>(&v61, v11);
      v13 = *v12;
      v14 = v12[1];
      *v12 = 0;
      v12[1] = 0;
      *(_QWORD *)&v65 = v13;
      *((_QWORD *)&v65 + 1) = v14;
      v15 = (volatile signed __int32 *)*((_QWORD *)&v61 + 1);
      if ( *((_QWORD *)&v61 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v61 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
      v16 = v60;
      if ( v60 )
        (**v60)(v60, 1);
      if ( (*(_BYTE *)(*(_QWORD *)Uev::Singleton<Uev::Log,Uev::Log>::Instance(v16) + 32LL) & 8) == 0 )
        goto LABEL_25;
      v18 = Uev::Singleton<Uev::Log,Uev::Log>::Instance(v17);
      Uev::Singleton<Uev::Log,Uev::Log>::Instance(v19);
      v63 = 0;
      v64 = 0;
      std::wstring::_Construct<1,wchar_t *>(
        &v63,
        L"Template::GetProfile() - Found profile %1% for template %2%.",
        0x3Cu);
      v21 = Uev::Log::fmt(v20, v68, &v63);
      *(_QWORD *)&v61 = v70;
      *((_QWORD *)&v61 + 1) = boost::on_process_enter;
      *(_QWORD *)&v62 = std::operator<<<wchar_t>;
      v22 = boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(
              v21,
              &v61);
      *(_QWORD *)&v61 = a2;
      *((_QWORD *)&v61 + 1) = boost::on_process_enter;
      *(_QWORD *)&v62 = std::operator<<<wchar_t>;
      v23 = boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(
              v22,
              &v61);
      v61 = 0;
      v62 = 0;
      std::wstring::_Construct<1,wchar_t *>(&v61, L"UevCommon", 9u);
      Uev::Log::Write(v18, v24, &v61, v23);
      std::wstring::_Tidy_deallocate(&v61);
      boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v68);
      v25 = &v63;
    }
    std::wstring::_Tidy_deallocate(v25);
LABEL_25:
    *a1 = v13;
    a1[1] = v14;
    std::wstring::_Tidy_deallocate(v70);
    goto LABEL_4;
  }
  *a3 = 0;
  a3[1] = 6;
  v7 = (__int64 *)Uev::ProfileFactory::CreateProfile(&v60, v69);
  std::shared_ptr<Uev::Profile>::shared_ptr<Uev::Profile>(a1, v7);
  if ( v60 )
    (**v60)(v60, 1);
LABEL_4:
  std::wstring::_Tidy_deallocate(v69);
  Uev::ScopeTracker::~ScopeTracker((Uev::ScopeTracker *)v71);
  return a1;
}

```

## disassembly

```asm
0x140047904  mov     rax, rsp
0x140047907  mov     [rax+20h], rbx
0x14004790b  push    rbp
0x14004790c  push    rsi
0x14004790d  push    rdi
0x14004790e  push    r12
0x140047910  push    r13
0x140047912  push    r14
0x140047914  push    r15
0x140047916  lea     rbp, [rax-208h]
0x14004791d  sub     rsp, 2D0h
0x140047924  movaps  xmmword ptr [rax-48h], xmm6
0x140047928  mov     rax, cs:__security_cookie
0x14004792f  xor     rax, rsp
0x140047932  mov     [rbp+200h+var_50], rax
0x140047939  mov     rsi, r8
0x14004793c  mov     r12, rdx
0x14004793f  mov     r14, rcx
0x140047942  mov     qword ptr [rsp+300h+var_2E0], rcx
0x140047947  xor     r13d, r13d
0x14004794a  lea     r8, aProfileGetprof; "Profile::GetProfileFromTemplate()"
0x140047951  lea     r15, aUevcommon; "UevCommon"
0x140047958  mov     rdx, r15; wchar_t *
0x14004795b  lea     rcx, [rbp+200h+var_D0]; this
0x140047962  call    ??0ScopeTracker@Uev@@QEAA@PEB_W0@Z; Uev::ScopeTracker::ScopeTracker(wchar_t const *,wchar_t const *)
0x140047967  nop
0x140047968  xorps   xmm0, xmm0
0x14004796b  movups  [rbp+200h+var_110], xmm0
0x140047972  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14004797a  movdqu  [rbp+200h+var_100], xmm6
0x140047982  mov     word ptr [rbp+200h+var_110], r13w
0x14004798a  mov     rcx, cs:?s_templateAdministrator@Profile@Uev@@1V?$unique_ptr@VITemplateAdministrator@Uev@@U?$default_delete@VITemplateAdministrator@Uev@@@std@@@std@@A; std::unique_ptr<Uev::ITemplateAdministrator> Uev::Profile::s_templateAdministrator
0x140047991  mov     rax, [rcx]
0x140047994  lea     r8, [rbp+200h+var_110]
0x14004799b  mov     rdx, r12
0x14004799e  mov     rax, [rax+60h]
0x1400479a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400479a7  lea     rdx, Data
0x1400479ae  lea     rcx, [rbp+200h+var_110]
0x1400479b5  call    ??$?9_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_W@Z; std::operator!=<wchar_t>(std::wstring const &,wchar_t const * const)
0x1400479ba  test    al, al
0x1400479bc  jz      loc_140047A4F
0x1400479c2  mov     [rsi], r13d
0x1400479c5  mov     dword ptr [rsi+4], 6
0x1400479cc  lea     rdx, [rbp+200h+var_110]
0x1400479d3  lea     rcx, [rsp+300h+var_2E0]
0x1400479d8  call    ?CreateProfile@ProfileFactory@Uev@@SA?AV?$unique_ptr@VProfile@Uev@@U?$default_delete@VProfile@Uev@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Uev::ProfileFactory::CreateProfile(std::wstring const &)
0x1400479dd  nop
0x1400479de  mov     rdx, rax
0x1400479e1  mov     rcx, r14
0x1400479e4  call    ??$?0VProfile@Uev@@U?$default_delete@VProfile@Uev@@@std@@$0A@@?$shared_ptr@VProfile@Uev@@@std@@QEAA@$$QEAV?$unique_ptr@VProfile@Uev@@U?$default_delete@VProfile@Uev@@@std@@@1@@Z; std::shared_ptr<Uev::Profile>::shared_ptr<Uev::Profile>(std::unique_ptr<Uev::Profile> &&)
0x1400479e9  nop
0x1400479ea  mov     rcx, qword ptr [rsp+300h+var_2E0]
0x1400479ef  test    rcx, rcx
0x1400479f2  jz      short loc_140047A04
0x1400479f4  mov     rax, [rcx]
0x1400479f7  lea     edx, [r13+1]
0x1400479fb  mov     rax, [rax]
0x1400479fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047a03  nop
0x140047a04  lea     rcx, [rbp+200h+var_110]
0x140047a0b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140047a10  nop
0x140047a11  lea     rcx, [rbp+200h+var_D0]; this
0x140047a18  call    ??1ScopeTracker@Uev@@UEAA@XZ; Uev::ScopeTracker::~ScopeTracker(void)
0x140047a1d  mov     rax, r14
0x140047a20  mov     rcx, [rbp+200h+var_50]
0x140047a27  xor     rcx, rsp; StackCookie
0x140047a2a  call    __security_check_cookie
0x140047a2f  lea     r11, [rsp+300h+var_30]
0x140047a37  mov     rbx, [r11+58h]
0x140047a3b  movaps  xmm6, xmmword ptr [r11-10h]
0x140047a40  mov     rsp, r11
0x140047a43  pop     r15
0x140047a45  pop     r14
0x140047a47  pop     r13
0x140047a49  pop     r12
0x140047a4b  pop     rdi
0x140047a4c  pop     rsi
0x140047a4d  pop     rbp
0x140047a4e  retn
0x140047a4f  xorps   xmm0, xmm0
0x140047a52  movdqu  [rsp+300h+var_2A0+8], xmm0
0x140047a58  movups  [rbp+200h+var_F0], xmm0
0x140047a5f  movdqu  [rbp+200h+var_E0], xmm6
0x140047a67  mov     word ptr [rbp+200h+var_F0], r13w
0x140047a6f  call    ?Instance@?$Singleton@VConfiguration@Uev@@V12@@Uev@@SAPEAVConfiguration@2@XZ; Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance(void)
0x140047a74  lea     rcx, [rax+26B0h]
0x140047a7b  mov     r9, rsi
0x140047a7e  lea     r8, [rbp+200h+var_F0]
0x140047a85  mov     rdx, r12
0x140047a88  call    ?Get@?$SettingGroup@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Uev@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV34@AEAUSettingInfo@2@@Z; Uev::SettingGroup<std::wstring>::Get(std::wstring const &,std::wstring &,Uev::SettingInfo &)
0x140047a8d  test    al, al
0x140047a8f  jz      loc_140047C30
0x140047a95  cmp     [rsi], r13d
0x140047a98  jnz     loc_140047C30
0x140047a9e  lea     rdx, [rbp+200h+var_F0]
0x140047aa5  lea     rcx, [rsp+300h+var_2E0]
0x140047aaa  call    ?CreateProfile@ProfileFactory@Uev@@SA?AV?$unique_ptr@VProfile@Uev@@U?$default_delete@VProfile@Uev@@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Uev::ProfileFactory::CreateProfile(std::wstring const &)
0x140047aaf  nop
0x140047ab0  mov     rdx, rax
0x140047ab3  lea     rcx, [rsp+300h+var_2E0+8]
0x140047ab8  call    ??$?0VProfile@Uev@@U?$default_delete@VProfile@Uev@@@std@@$0A@@?$shared_ptr@VProfile@Uev@@@std@@QEAA@$$QEAV?$unique_ptr@VProfile@Uev@@U?$default_delete@VProfile@Uev@@@std@@@1@@Z; std::shared_ptr<Uev::Profile>::shared_ptr<Uev::Profile>(std::unique_ptr<Uev::Profile> &&)
0x140047abd  mov     rsi, [rax]
0x140047ac0  mov     r15, [rax+8]
0x140047ac4  mov     [rax], r13
0x140047ac7  mov     [rax+8], r13
0x140047acb  mov     qword ptr [rsp+300h+var_2A0+8], rsi
0x140047ad0  mov     [rsp+300h+var_290], r15
0x140047ad5  mov     rdi, qword ptr [rsp+300h+var_2D0]
0x140047ada  test    rdi, rdi
0x140047add  jz      short loc_140047B16
0x140047adf  or      ebx, 0FFFFFFFFh
0x140047ae2  mov     eax, ebx
0x140047ae4  lock xadd [rdi+8], eax
0x140047ae9  add     eax, ebx
0x140047aeb  jnz     short loc_140047B16
0x140047aed  mov     rax, [rdi]
0x140047af0  mov     rcx, rdi
0x140047af3  mov     rax, [rax]
0x140047af6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047afb  mov     eax, ebx
0x140047afd  lock xadd [rdi+0Ch], eax
0x140047b02  add     eax, ebx
0x140047b04  jnz     short loc_140047B16
0x140047b06  mov     rax, [rdi]
0x140047b09  mov     rcx, rdi
0x140047b0c  mov     rax, [rax+8]
0x140047b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047b15  nop
0x140047b16  mov     rcx, qword ptr [rsp+300h+var_2E0]
0x140047b1b  test    rcx, rcx
0x140047b1e  jz      short loc_140047B30
0x140047b20  mov     rax, [rcx]
0x140047b23  mov     edx, 1
0x140047b28  mov     rax, [rax]
0x140047b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047b30  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140047b35  mov     rax, [rax]
0x140047b38  test    byte ptr [rax+20h], 8
0x140047b3c  jbe     loc_140047DDF
0x140047b42  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140047b47  mov     rdi, rax
0x140047b4a  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140047b4f  xorps   xmm0, xmm0
0x140047b52  movups  [rsp+300h+var_2C0+8], xmm0
0x140047b57  xorps   xmm1, xmm1
0x140047b5a  movdqu  [rsp+300h+var_2B0+8], xmm1
0x140047b60  mov     r8d, 3Ch ; '<'
0x140047b66  lea     rdx, aTemplateGetpro_2; "Template::GetProfile() - Found profile "...
0x140047b6d  lea     rcx, [rsp+300h+var_2C0+8]
0x140047b72  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140047b77  nop
0x140047b78  lea     r8, [rsp+300h+var_2C0+8]
0x140047b7d  lea     rdx, [rbp+200h+var_220]
0x140047b81  call    ?fmt@Log@Uev@@QEAA?AV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::Log::fmt(std::wstring const &)
0x140047b86  nop
0x140047b87  lea     rcx, [rbp+200h+var_F0]
0x140047b8e  mov     qword ptr [rsp+300h+var_2E0+8], rcx
0x140047b93  lea     r13, ?on_process_enter@boost@@YAXXZ; boost::on_process_enter(void)
0x140047b9a  mov     qword ptr [rsp+300h+var_2D0], r13
0x140047b9f  lea     rbx, ??$?6_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::operator<<<wchar_t>(std::wostream &,std::wstring const &)
0x140047ba6  mov     qword ptr [rsp+300h+var_2D0+8], rbx
0x140047bab  lea     rdx, [rsp+300h+var_2E0+8]
0x140047bb0  mov     rcx, rax
0x140047bb3  call    ??$feed_impl@_WU?$char_traits@_W@std@@V?$allocator@_W@2@AEBU?$put_holder@_WU?$char_traits@_W@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@AEAV32@AEBU?$put_holder@_WU?$char_traits@_W@std@@@012@@Z; boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &)
0x140047bb8  mov     qword ptr [rsp+300h+var_2E0+8], r12
0x140047bbd  mov     qword ptr [rsp+300h+var_2D0], r13
0x140047bc2  mov     qword ptr [rsp+300h+var_2D0+8], rbx
0x140047bc7  lea     rdx, [rsp+300h+var_2E0+8]
0x140047bcc  mov     rcx, rax
0x140047bcf  call    ??$feed_impl@_WU?$char_traits@_W@std@@V?$allocator@_W@2@AEBU?$put_holder@_WU?$char_traits@_W@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@AEAV32@AEBU?$put_holder@_WU?$char_traits@_W@std@@@012@@Z; boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &)
0x140047bd4  mov     rbx, rax
0x140047bd7  xorps   xmm0, xmm0
0x140047bda  movups  [rsp+300h+var_2E0+8], xmm0
0x140047bdf  xorps   xmm1, xmm1
0x140047be2  movdqu  [rsp+300h+var_2D0+8], xmm1
0x140047be8  mov     r8d, 9
0x140047bee  lea     rdx, aUevcommon; "UevCommon"
0x140047bf5  lea     rcx, [rsp+300h+var_2E0+8]
0x140047bfa  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140047bff  nop
0x140047c00  mov     r9, rbx
0x140047c03  lea     r8, [rsp+300h+var_2E0+8]
0x140047c08  mov     rcx, rdi
0x140047c0b  call    ?Write@Log@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@@Z; Uev::Log::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)
0x140047c10  nop
0x140047c11  lea     rcx, [rsp+300h+var_2E0+8]
0x140047c16  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140047c1b  nop
0x140047c1c  lea     rcx, [rbp+200h+var_220]
0x140047c20  call    ??1?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@QEAA@XZ; boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x140047c25  nop
0x140047c26  lea     rcx, [rsp+300h+var_2C0+8]
0x140047c2b  jmp     loc_140047DDA
0x140047c30  cmp     dword ptr [rsi], 2
0x140047c33  jnz     loc_140047DF8
0x140047c39  mov     edx, 1
0x140047c3e  lea     rcx, [rsp+300h+var_2E0]
0x140047c43  call    ?CreateProfile@ProfileFactory@Uev@@SA?AV?$unique_ptr@VProfile@Uev@@U?$default_delete@VProfile@Uev@@@std@@@std@@W4Type@Profile@2@@Z; Uev::ProfileFactory::CreateProfile(Uev::Profile::Type)
0x140047c48  nop
0x140047c49  mov     rdx, rax
0x140047c4c  lea     rcx, [rsp+300h+var_2E0+8]
0x140047c51  call    ??$?0VProfile@Uev@@U?$default_delete@VProfile@Uev@@@std@@$0A@@?$shared_ptr@VProfile@Uev@@@std@@QEAA@$$QEAV?$unique_ptr@VProfile@Uev@@U?$default_delete@VProfile@Uev@@@std@@@1@@Z; std::shared_ptr<Uev::Profile>::shared_ptr<Uev::Profile>(std::unique_ptr<Uev::Profile> &&)
0x140047c56  mov     rsi, [rax]
0x140047c59  mov     r15, [rax+8]
0x140047c5d  mov     [rax], r13
0x140047c60  mov     [rax+8], r13
0x140047c64  mov     qword ptr [rsp+300h+var_2A0+8], rsi
0x140047c69  mov     [rsp+300h+var_290], r15
0x140047c6e  mov     rdi, qword ptr [rsp+300h+var_2D0]
0x140047c73  test    rdi, rdi
0x140047c76  jz      short loc_140047CAF
0x140047c78  or      ebx, 0FFFFFFFFh
0x140047c7b  mov     eax, ebx
0x140047c7d  lock xadd [rdi+8], eax
0x140047c82  add     eax, ebx
0x140047c84  jnz     short loc_140047CAF
0x140047c86  mov     rax, [rdi]
0x140047c89  mov     rcx, rdi
0x140047c8c  mov     rax, [rax]
0x140047c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047c94  mov     eax, ebx
0x140047c96  lock xadd [rdi+0Ch], eax
0x140047c9b  add     eax, ebx
0x140047c9d  jnz     short loc_140047CAF
0x140047c9f  mov     rax, [rdi]
0x140047ca2  mov     rcx, rdi
0x140047ca5  mov     rax, [rax+8]
0x140047ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047cae  nop
0x140047caf  mov     rcx, qword ptr [rsp+300h+var_2E0]
0x140047cb4  test    rcx, rcx
0x140047cb7  jz      short loc_140047CC9
0x140047cb9  mov     rax, [rcx]
0x140047cbc  mov     edx, 1
0x140047cc1  mov     rax, [rax]
0x140047cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047cc9  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140047cce  mov     rax, [rax]
0x140047cd1  test    byte ptr [rax+20h], 8
0x140047cd5  jbe     loc_140047DDF
0x140047cdb  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140047ce0  mov     rdi, rax
0x140047ce3  call    ?Instance@?$Singleton@VLog@Uev@@V12@@Uev@@SAPEAVLog@2@XZ; Uev::Singleton<Uev::Log,Uev::Log>::Instance(void)
0x140047ce8  xorps   xmm0, xmm0
0x140047ceb  movups  [rbp+200h+pExceptionObject], xmm0
0x140047cef  xorps   xmm1, xmm1
0x140047cf2  movdqu  [rbp+200h+var_270], xmm1
0x140047cf7  mov     r8d, 44h ; 'D'
0x140047cfd  lea     rdx, aTemplateGetpro_1; "Template::GetProfile() - Defaulting to "...
0x140047d04  lea     rcx, [rbp+200h+pExceptionObject]
0x140047d08  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140047d0d  nop
0x140047d0e  lea     r8, [rbp+200h+pExceptionObject]
0x140047d12  lea     rdx, [rbp+200h+var_220]
0x140047d16  call    ?fmt@Log@Uev@@QEAA?AV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::Log::fmt(std::wstring const &)
0x140047d1b  mov     rbx, rax
0x140047d1e  mov     edx, 1
0x140047d23  lea     rcx, [rbp+200h+var_240]
0x140047d27  call    ?ToString@Profile@Uev@@SA?BV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4Type@12@@Z; Uev::Profile::ToString(Uev::Profile::Type)
0x140047d2c  nop
0x140047d2d  mov     qword ptr [rsp+300h+var_2E0+8], rax
0x140047d32  lea     r13, ?on_process_enter@boost@@YAXXZ; boost::on_process_enter(void)
0x140047d39  mov     qword ptr [rsp+300h+var_2D0], r13
0x140047d3e  lea     rax, ??$?6_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::operator<<<wchar_t>(std::wostream &,std::wstring const &)
0x140047d45  mov     qword ptr [rsp+300h+var_2D0+8], rax
0x140047d4a  lea     rdx, [rsp+300h+var_2E0+8]
0x140047d4f  mov     rcx, rbx
0x140047d52  call    ??$feed_impl@_WU?$char_traits@_W@std@@V?$allocator@_W@2@AEBU?$put_holder@_WU?$char_traits@_W@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@AEAV32@AEBU?$put_holder@_WU?$char_traits@_W@std@@@012@@Z; boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &)
0x140047d57  mov     qword ptr [rsp+300h+var_2E0+8], r12
0x140047d5c  mov     qword ptr [rsp+300h+var_2D0], r13
0x140047d61  lea     rcx, ??$?6_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::operator<<<wchar_t>(std::wostream &,std::wstring const &)
0x140047d68  mov     qword ptr [rsp+300h+var_2D0+8], rcx
0x140047d6d  lea     rdx, [rsp+300h+var_2E0+8]
0x140047d72  mov     rcx, rax
0x140047d75  call    ??$feed_impl@_WU?$char_traits@_W@std@@V?$allocator@_W@2@AEBU?$put_holder@_WU?$char_traits@_W@std@@@detail@io@boost@@@detail@io@boost@@YAAEAV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@AEAV32@AEBU?$put_holder@_WU?$char_traits@_W@std@@@012@@Z; boost::io::detail::feed_impl<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &>(boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,boost::io::detail::put_holder<wchar_t,std::char_traits<wchar_t>> const &)
0x140047d7a  mov     rbx, rax
0x140047d7d  xorps   xmm0, xmm0
0x140047d80  movups  [rsp+300h+var_2C0+8], xmm0
0x140047d85  xorps   xmm1, xmm1
0x140047d88  movdqu  [rsp+300h+var_2B0+8], xmm1
0x140047d8e  mov     r8d, 9
0x140047d94  lea     rdx, aUevcommon; "UevCommon"
0x140047d9b  lea     rcx, [rsp+300h+var_2C0+8]
0x140047da0  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x140047da5  nop
0x140047da6  mov     r9, rbx
0x140047da9  lea     r8, [rsp+300h+var_2C0+8]
0x140047dae  mov     rcx, rdi
0x140047db1  call    ?Write@Log@Uev@@QEBAXW4UEV_LOG_LEVEL@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@@Z; Uev::Log::Write(Uev::UEV_LOG_LEVEL,std::wstring const &,boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)
0x140047db6  nop
0x140047db7  lea     rcx, [rsp+300h+var_2C0+8]
0x140047dbc  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140047dc1  nop
0x140047dc2  lea     rcx, [rbp+200h+var_240]
0x140047dc6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140047dcb  nop
0x140047dcc  lea     rcx, [rbp+200h+var_220]
0x140047dd0  call    ??1?$basic_format@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@boost@@QEAA@XZ; boost::basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::~basic_format<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
  ... truncated ...
```
