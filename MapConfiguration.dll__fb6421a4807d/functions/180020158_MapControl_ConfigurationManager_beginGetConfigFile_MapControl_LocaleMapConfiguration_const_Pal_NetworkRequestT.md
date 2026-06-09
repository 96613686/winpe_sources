# MapControl::ConfigurationManager::beginGetConfigFile(MapControl::LocaleMapConfiguration const &,Pal::NetworkRequestType)

- ea: `0x180020158`
- end: `0x180020557`
- name: `?beginGetConfigFile@ConfigurationManager@MapControl@@AEAAXAEBVLocaleMapConfiguration@2@W4NetworkRequestType@Pal@@@Z`
- size: `1023`
- prototype: ``
- caller_count: `3`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020e18`
- `0x180020ec0`
- `0x180021694`

## callees

- `0x1800094a0`
- `0x18000b7fc`
- `0x18000ba50`
- `0x18000c354`
- `0x18000c3ac`
- `0x18000c850`
- `0x18000fe30`
- `0x18000fe68`
- `0x180010f34`
- `0x180011ddc`
- `0x180013da8`
- `0x18001ad38`
- `0x18001b824`
- `0x18001c8b4`
- `0x18001ec94`
- `0x18001f640`
- `0x18001f9ec`
- `0x180020158`
- `0x180022eb0`
- `0x180023a88`
- `0x180024c68`
- `0x180029f74`
- `0x18002a2cc`
- `0x18002a6e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall MapControl::ConfigurationManager::beginGetConfigFile(__int64 a1, __int64 a2)
{
  Pal::LocalSettings *Instance; // rax
  __int64 v5; // rdx
  __int64 v6; // rax
  const wchar_t *v7; // rdx
  _QWORD *v8; // rax
  __int64 v9; // r14
  _QWORD *v10; // rax
  __int64 v11; // r15
  _QWORD *v12; // rax
  __int64 v13; // rbx
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  __int64 v16; // rbx
  int v17; // eax
  std::_Ref_count_base *v18; // rdi
  _QWORD *v19; // rbx
  _QWORD v21[2]; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v23[56]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v24; // [rsp+98h] [rbp-68h]
  _BYTE v25[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v26[32]; // [rsp+C0h] [rbp-40h] BYREF
  std::_Ref_count_base *v27[2]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD Src[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v29[32]; // [rsp+120h] [rbp+20h] BYREF
  __int64 (__fastcall *v30)(MapControl::ConfigurationManager *); // [rsp+140h] [rbp+40h]
  _BYTE v31[32]; // [rsp+148h] [rbp+48h] BYREF
  _BYTE v32[40]; // [rsp+168h] [rbp+68h] BYREF
  __int64 v33; // [rsp+190h] [rbp+90h]

  std::wstring::wstring((__int64)v26);
  Instance = (Pal::LocalSettings *)Pal::LocalSettingsSingleton<MapControl::ConfigurationLocalSettings>::getInstance();
  if ( !(unsigned __int8)Pal::LocalSettings::querySetting(
                           Instance,
                           (struct Pal::LocalSettingId *)&MapControl::ConfigurationLocalSettings::sConfigUrl) )
    MapControl::MapConfiguration::getValueString(*(_QWORD *)(a1 + 168), v5, v26);
  std::wstring::wstring((__int64)v29, (__int64)L"prod");
  LODWORD(v21[0]) = 0;
  v6 = Pal::LocalSettingsSingleton<MapControl::ConfigurationLocalSettings>::getInstance();
  if ( (unsigned __int8)Pal::LocalSettings::querySetting<int>(
                          v6,
                          &MapControl::ConfigurationLocalSettings::sUseIntData,
                          v21)
    && LODWORD(v21[0]) )
  {
    v7 = L"intcn";
    if ( *(_DWORD *)(a1 + 408) != 1 )
      v7 = L"int";
    std::wstring::assign(v29, v7);
  }
  std::wstring::wstring((__int64)v27, (__int64)L"3.220.2005.0");
  std::wstring::wstring((__int64)v25, (__int64)L"{version}");
  v8 = Utility::StringUtils::replace<unsigned short>(Src, (__int64)v26, (__int64)v25, (__int64)v27);
  std::wstring::operator=(v26, v8);
  std::wstring::_Tidy_deallocate(Src);
  std::wstring::_Tidy_deallocate(v25);
  std::wstring::_Tidy_deallocate(v27);
  v9 = a2 + 352;
  std::wstring::wstring((__int64)v25, (__int64)L"{region}");
  v10 = Utility::StringUtils::replace<unsigned short>(v27, (__int64)v26, (__int64)v25, a2 + 352);
  std::wstring::operator=(v26, v10);
  std::wstring::_Tidy_deallocate(v27);
  std::wstring::_Tidy_deallocate(v25);
  v11 = a2 + 384;
  std::wstring::wstring((__int64)v25, (__int64)L"{language}");
  v12 = Utility::StringUtils::replace<unsigned short>(v27, (__int64)v26, (__int64)v25, a2 + 384);
  std::wstring::operator=(v26, v12);
  std::wstring::_Tidy_deallocate(v27);
  std::wstring::_Tidy_deallocate(v25);
  v13 = MapControl::ClientBucket::toString(a1 + 448, Src);
  std::wstring::wstring((__int64)v25, (__int64)L"{clientbucket}");
  v14 = Utility::StringUtils::replace<unsigned short>(v27, (__int64)v26, (__int64)v25, v13);
  std::wstring::operator=(v26, v14);
  std::wstring::_Tidy_deallocate(v27);
  std::wstring::_Tidy_deallocate(v25);
  std::wstring::_Tidy_deallocate(Src);
  std::wstring::wstring((__int64)v25, (__int64)L"{env}");
  v15 = Utility::StringUtils::replace<unsigned short>(v27, (__int64)v26, (__int64)v25, (__int64)v29);
  std::wstring::operator=(v26, v15);
  std::wstring::_Tidy_deallocate(v27);
  std::wstring::_Tidy_deallocate(v25);
  v16 = *(_QWORD *)(a1 + 312);
  *(_OWORD *)v27 = 0;
  v17 = Pal::FixedPriorityTag::create(v25);
  Pal::NetworkManager::beginGetUrl(v16, (unsigned int)v22, (unsigned int)v26, v17, (__int64)v27, 0);
  Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v25);
  if ( v27[1] )
    std::_Ref_count_base::_Decref(v27[1]);
  Src[0] = 0;
  if ( v22[1] )
    _InterlockedIncrement((volatile signed __int32 *)v22[1] + 2);
  Src[0] = *(_OWORD *)v22;
  Pal::UntypedAsyncOperationCancelList::add(a1 + 456, Src);
  v18 = v22[0];
  v21[0] = v23;
  v30 = MapControl::ConfigurationManager::getOverridesAsyncComplete;
  *(_QWORD *)&Src[0] = v31;
  std::wstring::wstring((__int64)v31, v11);
  std::wstring::wstring((__int64)v32, v9);
  v33 = a1;
  v24 = 0;
  v19 = std::_Allocate<16,std::_Default_allocate_traits>(0x60u);
  *v19 = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (MapControl::ConfigurationManager::*)(Pal::NetworkAsyncOperation const &,std::wstring const &,std::wstring const &),MapControl::ConfigurationManager *,std::_Ph<1> const &,std::wstring const &,std::wstring const &>,void,Pal::NetworkAsyncOperation &>::`vftable';
  v19[1] = v30;
  std::wstring::wstring(v19 + 2, v31);
  std::wstring::wstring(v19 + 6, v32);
  *((_BYTE *)v19 + 80) = v32[32];
  v19[11] = v33;
  v21[0] = 0;
  `std::_Global_new<std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (MapControl::ConfigurationManager::*)(Pal::NetworkAsyncOperation const &,std::wstring const &,std::wstring const &),MapControl::ConfigurationManager *,std::_Ph<1> const &,std::wstring const &,std::wstring const &>,void,Pal::NetworkAsyncOperation &>,std::_Binder<std::_Unforced,void (MapControl::ConfigurationManager::*)(Pal::NetworkAsyncOperation const &,std::wstring const &,std::wstring const &),MapControl::ConfigurationManager *,std::_Ph<1> const &,std::wstring const &,std::wstring const &> const &>'::`2'::_Guard_type::~_Guard_type(v21);
  v24 = v19;
  Pal::NetworkAsyncOperation::setCallback(v18, v23);
  std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v31);
  if ( v22[1] )
    std::_Ref_count_base::_Decref(v22[1]);
  std::wstring::_Tidy_deallocate(v29);
  return std::wstring::_Tidy_deallocate(v26);
}

```

## disassembly

```asm
0x180020158  mov     [rsp-8+arg_10], rbx
0x18002015d  push    rbp
0x18002015e  push    rsi
0x18002015f  push    rdi
0x180020160  push    r14
0x180020162  push    r15
0x180020164  lea     rbp, [rsp-0B0h]
0x18002016c  sub     rsp, 1B0h
0x180020173  mov     rax, cs:__security_cookie
0x18002017a  xor     rax, rsp
0x18002017d  mov     [rbp+0D0h+var_30], rax
0x180020184  mov     rbx, rdx
0x180020187  mov     rsi, rcx
0x18002018a  lea     rcx, [rbp+0D0h+var_110]
0x18002018e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180020193  nop
0x180020194  call    ?getInstance@?$LocalSettingsSingleton@VConfigurationLocalSettings@MapControl@@@Pal@@KAAEAVConfigurationLocalSettings@MapControl@@XZ; Pal::LocalSettingsSingleton<MapControl::ConfigurationLocalSettings>::getInstance(void)
0x180020199  lea     r8, [rbp+0D0h+var_110]
0x18002019d  lea     rdx, ?sConfigUrl@ConfigurationLocalSettings@MapControl@@0VLocalSettingId@Pal@@B; struct Pal::LocalSettingId *
0x1800201a4  mov     rcx, rax; this
0x1800201a7  call    ?querySetting@LocalSettings@Pal@@IEAA_NAEBVLocalSettingId@2@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Pal::LocalSettings::querySetting(Pal::LocalSettingId const &,std::wstring *)
0x1800201ac  test    al, al
0x1800201ae  jnz     short loc_1800201C0
0x1800201b0  lea     r8, [rbp+0D0h+var_110]
0x1800201b4  mov     rcx, [rsi+0A8h]
0x1800201bb  call    ?getValueString@MapConfiguration@MapControl@@QEBA_NW4ConfigurationKeys@2@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MapControl::MapConfiguration::getValueString(MapControl::ConfigurationKeys,std::wstring *)
0x1800201c0  lea     rdx, aProd; "prod"
0x1800201c7  lea     rcx, [rbp+0D0h+var_B0]
0x1800201cb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800201d0  nop
0x1800201d1  mov     dword ptr [rsp+1D0h+var_190], 0
0x1800201d9  call    ?getInstance@?$LocalSettingsSingleton@VConfigurationLocalSettings@MapControl@@@Pal@@KAAEAVConfigurationLocalSettings@MapControl@@XZ; Pal::LocalSettingsSingleton<MapControl::ConfigurationLocalSettings>::getInstance(void)
0x1800201de  lea     r8, [rsp+1D0h+var_190]
0x1800201e3  lea     rdx, ?sUseIntData@ConfigurationLocalSettings@MapControl@@0VLocalSettingId@Pal@@B; Pal::LocalSettingId const MapControl::ConfigurationLocalSettings::sUseIntData
0x1800201ea  mov     rcx, rax
0x1800201ed  call    ??$querySetting@H@LocalSettings@Pal@@IEAA_NAEBVLocalSettingId@1@PEAH@Z; Pal::LocalSettings::querySetting<int>(Pal::LocalSettingId const &,int *)
0x1800201f2  test    al, al
0x1800201f4  jz      short loc_180020224
0x1800201f6  cmp     dword ptr [rsp+1D0h+var_190], 0
0x1800201fb  setnz   al
0x1800201fe  test    al, al
0x180020200  jz      short loc_180020224
0x180020202  lea     rax, aInt; "int"
0x180020209  lea     rdx, aIntcn; "intcn"
0x180020210  cmp     dword ptr [rsi+198h], 1
0x180020217  cmovnz  rdx, rax
0x18002021b  lea     rcx, [rbp+0D0h+var_B0]
0x18002021f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180020224  lea     rdx, a322020050; "3.220.2005.0"
0x18002022b  lea     rcx, [rbp+0D0h+var_F0]
0x18002022f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180020234  nop
0x180020235  lea     rdx, aVersion_0; "{version}"
0x18002023c  lea     rcx, [rbp+0D0h+var_130]
0x180020240  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180020245  nop
0x180020246  lea     r9, [rbp+0D0h+var_F0]
0x18002024a  lea     r8, [rbp+0D0h+var_130]
0x18002024e  lea     rdx, [rbp+0D0h+var_110]
0x180020252  lea     rcx, [rbp+0D0h+Src]; Src
0x180020256  call    ??$replace@G@StringUtils@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00@Z; Utility::StringUtils::replace<ushort>(std::wstring const &,std::wstring const &,std::wstring const &)
0x18002025b  mov     rdx, rax
0x18002025e  lea     rcx, [rbp+0D0h+var_110]
0x180020262  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180020267  lea     rcx, [rbp+0D0h+Src]
0x18002026b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020270  nop
0x180020271  lea     rcx, [rbp+0D0h+var_130]
0x180020275  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002027a  nop
0x18002027b  lea     rcx, [rbp+0D0h+var_F0]
0x18002027f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020284  lea     r14, [rbx+160h]
0x18002028b  lea     rdx, aRegion; "{region}"
0x180020292  lea     rcx, [rbp+0D0h+var_130]
0x180020296  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002029b  nop
0x18002029c  mov     r9, r14
0x18002029f  lea     r8, [rbp+0D0h+var_130]
0x1800202a3  lea     rdx, [rbp+0D0h+var_110]
0x1800202a7  lea     rcx, [rbp+0D0h+var_F0]; Src
0x1800202ab  call    ??$replace@G@StringUtils@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00@Z; Utility::StringUtils::replace<ushort>(std::wstring const &,std::wstring const &,std::wstring const &)
0x1800202b0  mov     rdx, rax
0x1800202b3  lea     rcx, [rbp+0D0h+var_110]
0x1800202b7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800202bc  lea     rcx, [rbp+0D0h+var_F0]
0x1800202c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800202c5  nop
0x1800202c6  lea     rcx, [rbp+0D0h+var_130]
0x1800202ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800202cf  lea     r15, [rbx+180h]
0x1800202d6  lea     rdx, aLanguage; "{language}"
0x1800202dd  lea     rcx, [rbp+0D0h+var_130]
0x1800202e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800202e6  nop
0x1800202e7  mov     r9, r15
0x1800202ea  lea     r8, [rbp+0D0h+var_130]
0x1800202ee  lea     rdx, [rbp+0D0h+var_110]
0x1800202f2  lea     rcx, [rbp+0D0h+var_F0]; Src
0x1800202f6  call    ??$replace@G@StringUtils@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00@Z; Utility::StringUtils::replace<ushort>(std::wstring const &,std::wstring const &,std::wstring const &)
0x1800202fb  mov     rdx, rax
0x1800202fe  lea     rcx, [rbp+0D0h+var_110]
0x180020302  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180020307  lea     rcx, [rbp+0D0h+var_F0]
0x18002030b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020310  nop
0x180020311  lea     rcx, [rbp+0D0h+var_130]
0x180020315  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002031a  lea     rcx, [rsi+1C0h]
0x180020321  lea     rdx, [rbp+0D0h+Src]
0x180020325  call    ?toString@ClientBucket@MapControl@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; MapControl::ClientBucket::toString(void)
0x18002032a  mov     rbx, rax
0x18002032d  lea     rdx, aClientbucket; "{clientbucket}"
0x180020334  lea     rcx, [rbp+0D0h+var_130]
0x180020338  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002033d  nop
0x18002033e  mov     r9, rbx
0x180020341  lea     r8, [rbp+0D0h+var_130]
0x180020345  lea     rdx, [rbp+0D0h+var_110]
0x180020349  lea     rcx, [rbp+0D0h+var_F0]; Src
0x18002034d  call    ??$replace@G@StringUtils@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00@Z; Utility::StringUtils::replace<ushort>(std::wstring const &,std::wstring const &,std::wstring const &)
0x180020352  mov     rdx, rax
0x180020355  lea     rcx, [rbp+0D0h+var_110]
0x180020359  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002035e  lea     rcx, [rbp+0D0h+var_F0]
0x180020362  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020367  nop
0x180020368  lea     rcx, [rbp+0D0h+var_130]
0x18002036c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020371  nop
0x180020372  lea     rcx, [rbp+0D0h+Src]
0x180020376  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002037b  lea     rdx, aEnv; "{env}"
0x180020382  lea     rcx, [rbp+0D0h+var_130]
0x180020386  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002038b  nop
0x18002038c  lea     r9, [rbp+0D0h+var_B0]
0x180020390  lea     r8, [rbp+0D0h+var_130]
0x180020394  lea     rdx, [rbp+0D0h+var_110]
0x180020398  lea     rcx, [rbp+0D0h+var_F0]; Src
0x18002039c  call    ??$replace@G@StringUtils@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00@Z; Utility::StringUtils::replace<ushort>(std::wstring const &,std::wstring const &,std::wstring const &)
0x1800203a1  mov     rdx, rax
0x1800203a4  lea     rcx, [rbp+0D0h+var_110]
0x1800203a8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800203ad  lea     rcx, [rbp+0D0h+var_F0]
0x1800203b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800203b6  nop
0x1800203b7  lea     rcx, [rbp+0D0h+var_130]
0x1800203bb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800203c0  mov     rbx, [rsi+138h]
0x1800203c7  xorps   xmm0, xmm0
0x1800203ca  movdqu  xmmword ptr [rbp+0D0h+var_F0], xmm0
0x1800203cf  lea     rcx, [rbp+0D0h+var_130]
0x1800203d3  call    ?create@FixedPriorityTag@Pal@@SA?AV?$PresentSharedPtr@VPriorityTag@Pal@@@Core@@I@Z; Pal::FixedPriorityTag::create(uint)
0x1800203d8  nop
0x1800203d9  mov     [rsp+1D0h+var_1A8], 0
0x1800203e1  lea     rcx, [rbp+0D0h+var_F0]
0x1800203e5  mov     [rsp+1D0h+var_1B0], rcx
0x1800203ea  mov     r9, rax
0x1800203ed  lea     r8, [rbp+0D0h+var_110]
0x1800203f1  lea     rdx, [rsp+1D0h+var_180]
0x1800203f6  mov     rcx, rbx
0x1800203f9  call    ?beginGetUrl@NetworkManager@Pal@@QEAA?AV?$shared_ptr@VNetworkAsyncOperation@Pal@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@AEBV?$shared_ptr@VPriorityTag@Pal@@@4@AEBV?$shared_ptr@V?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@std@@@4@W4NetworkRequestType@2@W4CancelType@NetworkAsyncOperation@2@@Z; Pal::NetworkManager::beginGetUrl(std::wstring const &,std::shared_ptr<Pal::PriorityTag> const &,std::shared_ptr<std::vector<Pal::HttpHeader>> const &,Pal::NetworkRequestType,Pal::NetworkAsyncOperation::CancelType)
0x1800203fe  nop
0x1800203ff  lea     rcx, [rbp+0D0h+var_130]
0x180020403  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180020408  nop
0x180020409  mov     rcx, [rbp+0D0h+var_F0+8]; this
0x18002040d  test    rcx, rcx
0x180020410  jz      short loc_180020417
0x180020412  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180020417  xorps   xmm0, xmm0
0x18002041a  movdqa  [rbp+0D0h+Src], xmm0
0x18002041f  mov     rax, [rsp+1D0h+var_180+8]
0x180020424  test    rax, rax
0x180020427  jz      short loc_18002042D
0x180020429  lock inc dword ptr [rax+8]
0x18002042d  movaps  xmm0, xmmword ptr [rsp+1D0h+var_180]
0x180020432  movdqa  [rbp+0D0h+Src], xmm0
0x180020437  lea     rcx, [rsi+1C8h]
0x18002043e  lea     rdx, [rbp+0D0h+Src]
0x180020442  call    ?add@UntypedAsyncOperationCancelList@Pal@@QEAAXV?$shared_ptr@VUntypedAsyncOperation@Pal@@@std@@@Z; Pal::UntypedAsyncOperationCancelList::add(std::shared_ptr<Pal::UntypedAsyncOperation>)
0x180020447  mov     rdi, [rsp+1D0h+var_180]
0x18002044c  lea     rax, [rsp+1D0h+var_170]
0x180020451  mov     [rsp+1D0h+var_190], rax
0x180020456  lea     rax, ?getOverridesAsyncComplete@ConfigurationManager@MapControl@@AEAAXAEBVNetworkAsyncOperation@Pal@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1@Z; MapControl::ConfigurationManager::getOverridesAsyncComplete(Pal::NetworkAsyncOperation const &,std::wstring const &,std::wstring const &)
0x18002045d  mov     [rbp+0D0h+var_90], rax
0x180020461  lea     rax, [rbp+0D0h+var_88]
0x180020465  mov     qword ptr [rbp+0D0h+Src], rax
0x180020469  mov     rdx, r15
0x18002046c  lea     rcx, [rbp+0D0h+var_88]
0x180020470  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180020475  nop
0x180020476  mov     rdx, r14
0x180020479  lea     rcx, [rbp+0D0h+var_68]
0x18002047d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180020482  nop
0x180020483  mov     [rbp+0D0h+var_40], rsi
0x18002048a  mov     [rbp+0D0h+var_138], 0
0x180020492  mov     ecx, 60h ; '`'
0x180020497  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002049c  mov     rbx, rax
0x18002049f  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8ConfigurationManager@MapControl@@EAAXAEBVNetworkAsyncOperation@Pal@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@1@ZPEAV34@AEBU?$_Ph@$00@2@AEBV72@AEBV72@@std@@XAEAVNetworkAsyncOperation@Pal@@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (MapControl::ConfigurationManager::*)(Pal::NetworkAsyncOperation const &,std::wstring const &,std::wstring const &),MapControl::ConfigurationManager *,std::_Ph<1> const &,std::wstring const &,std::wstring const &>,void,Pal::NetworkAsyncOperation &>::`vftable'
0x1800204a6  mov     [rbx], rax
0x1800204a9  mov     rcx, [rbp+0D0h+var_90]
0x1800204ad  mov     [rbx+8], rcx
0x1800204b1  lea     rdx, [rbp+0D0h+var_88]
0x1800204b5  lea     rcx, [rbx+10h]
0x1800204b9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800204be  lea     rcx, [rbx+30h]
0x1800204c2  lea     rdx, [rbp+0D0h+var_68]
0x1800204c6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800204cb  mov     dl, [rbp+0D0h+var_48]
0x1800204d1  mov     [rbx+50h], dl
0x1800204d4  mov     rax, [rbp+0D0h+var_40]
0x1800204db  mov     [rbx+58h], rax
0x1800204df  mov     [rsp+1D0h+var_190], 0
0x1800204e8  lea     rcx, [rsp+1D0h+var_190]
0x1800204ed  call    ??1_Guard_type@?1???$_Global_new@V?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8ConfigurationManager@MapControl@@EAAXAEBVNetworkAsyncOperation@Pal@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@1@ZPEAV34@AEBU?$_Ph@$00@2@AEBV72@AEBV72@@std@@XAEAVNetworkAsyncOperation@Pal@@@std@@AEBV?$_Binder@U_Unforced@std@@P8ConfigurationManager@MapControl@@EAAXAEBVNetworkAsyncOperation@Pal@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@1@ZPEAV34@AEBU?$_Ph@$00@2@AEBV72@AEBV72@@2@@std@@YAPEAV?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@P8ConfigurationManager@MapControl@@EAAXAEBVNetworkAsyncOperation@Pal@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@1@ZPEAV34@AEBU?$_Ph@$00@2@AEBV72@AEBV72@@std@@XAEAVNetworkAsyncOperation@Pal@@@1@AEBV?$_Binder@U_Unforced@std@@P8ConfigurationManager@MapControl@@EAAXAEBVNetworkAsyncOperation@Pal@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@1@ZPEAV34@AEBU?$_Ph@$00@2@AEBV72@AEBV72@@1@@Z@QEAA@XZ; `std::_Global_new<std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (MapControl::ConfigurationManager::*)(Pal::NetworkAsyncOperation const &,std::wstring const &,std::wstring const &),MapControl::ConfigurationManager *,std::_Ph<1> const &,std::wstring const &,std::wstring const &>,void,Pal::NetworkAsyncOperation &>,std::_Binder<std::_Unforced,void (MapControl::ConfigurationManager::*)(Pal::NetworkAsyncOperation const &,std::wstring const &,std::wstring const &),MapControl::ConfigurationManager *,std::_Ph<1> const &,std::wstring const &,std::wstring const &> const &>(std::_Binder<std::_Unforced,void (MapControl::ConfigurationManager::*)(Pal::NetworkAsyncOperation const &,std::wstring const &,std::wstring const &),MapControl::ConfigurationManager *,std::_Ph<1> const &,std::wstring const &,std::wstring const &> const &)'::`2'::_Guard_type::~_Guard_type(void)
0x1800204f2  mov     [rbp+0D0h+var_138], rbx
0x1800204f6  lea     rdx, [rsp+1D0h+var_170]
0x1800204fb  mov     rcx, rdi
0x1800204fe  call    ?setCallback@NetworkAsyncOperation@Pal@@QEAAXV?$function@$$A6AXAEAVNetworkAsyncOperation@Pal@@@Z@std@@@Z; Pal::NetworkAsyncOperation::setCallback(std::function<void (Pal::NetworkAsyncOperation &)>)
0x180020503  nop
0x180020504  lea     rcx, [rbp+0D0h+var_88]
0x180020508  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x18002050d  nop
0x18002050e  mov     rcx, [rsp+1D0h+var_180+8]; this
0x180020513  test    rcx, rcx
0x180020516  jz      short loc_18002051E
0x180020518  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002051d  nop
0x18002051e  lea     rcx, [rbp+0D0h+var_B0]
0x180020522  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020527  nop
0x180020528  lea     rcx, [rbp+0D0h+var_110]
0x18002052c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020531  mov     rcx, [rbp+0D0h+var_30]
0x180020538  xor     rcx, rsp; StackCookie
0x18002053b  call    __security_check_cookie
0x180020540  mov     rbx, [rsp+1D0h+arg_10]
0x180020548  add     rsp, 1B0h
0x18002054f  pop     r15
0x180020551  pop     r14
0x180020553  pop     rdi
0x180020554  pop     rsi
0x180020555  pop     rbp
0x180020556  retn
```
