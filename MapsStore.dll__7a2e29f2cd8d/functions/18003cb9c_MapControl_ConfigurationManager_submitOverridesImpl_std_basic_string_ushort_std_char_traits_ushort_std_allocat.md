# MapControl::ConfigurationManager::submitOverridesImpl(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Json::Value const &,Pal::Date const &,MapControl::ConfigurationManager::OverridesSource)

- ea: `0x18003cb9c`
- end: `0x18003cf00`
- name: `?submitOverridesImpl@ConfigurationManager@MapControl@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEBVValue@Json@@AEBVDate@Pal@@W4OverridesSource@12@@Z`
- size: `868`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003ca14`

## callees

- `0x18000d090`
- `0x180011d28`
- `0x180011d90`
- `0x180012720`
- `0x180016548`
- `0x1800179ac`
- `0x1800179e8`
- `0x1800206f0`
- `0x180025790`
- `0x180027024`
- `0x180029c50`
- `0x18002f874`
- `0x180032dd8`
- `0x18003a544`
- `0x18003a90c`
- `0x18003aee4`
- `0x18003b2d8`
- `0x18003ba54`
- `0x18003c154`
- `0x18003cb9c`
- `0x18003cf08`
- `0x18003d5fc`
- `0x18003dd5c`
- `0x18003e95c`
- `0x18007bea4`
- `0x18007c26c`
- `0x18007c5a8`
- `0x18007cc9c`
- `0x18007d41c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ccaf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ccaf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cea6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003cea6`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall MapControl::ConfigurationManager::submitOverridesImpl(
        MapControl::ConfigurationManager *this,
        __int64 a2,
        __int64 a3,
        _BYTE *a4,
        __int64 *a5)
{
  __int64 v8; // r8
  __int64 v9; // r9
  char *v10; // r14
  void *v11; // rsi
  char *v12; // rdx
  char *v13; // rdi
  const struct Json::Value *v14; // rax
  __int64 v15; // rbx
  _QWORD *v16; // rax
  __int64 v17; // r15
  __int64 *Overrides; // r12
  __int64 *v19; // rdi
  char v20; // r14
  __int64 v21; // rdi
  __int64 v22; // rax
  int v23; // r10d
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdi
  _QWORD *v28; // rax
  _QWORD *v29; // r15
  _QWORD *v30; // rdi
  __int64 v31; // [rsp+20h] [rbp-B9h] BYREF
  int v32; // [rsp+28h] [rbp-B1h] BYREF
  void *v33[2]; // [rsp+30h] [rbp-A9h] BYREF
  __int64 v34; // [rsp+40h] [rbp-99h] BYREF
  __int64 *v35; // [rsp+48h] [rbp-91h]
  char *v36; // [rsp+50h] [rbp-89h] BYREF
  char *v37; // [rsp+58h] [rbp-81h]
  __int64 v38; // [rsp+60h] [rbp-79h]
  __int64 v39; // [rsp+68h] [rbp-71h] BYREF
  char *v40; // [rsp+78h] [rbp-61h] BYREF
  _BYTE v41[40]; // [rsp+88h] [rbp-51h] BYREF
  _BYTE v42[32]; // [rsp+B0h] [rbp-29h] BYREF

  v31 = a3;
  v39 = a2;
  v35 = a5;
  std::map<enum MapControl::ConfigurationKeys,std::wstring>::map<enum MapControl::ConfigurationKeys,std::wstring>(v33);
  Json::Value::getMemberNames(a4, &v36);
  v10 = v37;
  v11 = v36;
  if ( v36 == v37 )
  {
    if ( v36 )
    {
      v12 = v37;
LABEL_30:
      std::_Destroy_range<std::allocator<std::wstring>>(v11, v12, v8, v9);
      std::_Deallocate<16>(v11, (v38 - (_QWORD)v11) & 0xFFFFFFFFFFFFFFE0uLL);
    }
  }
  else
  {
    v13 = v36;
    do
    {
      v14 = (const struct Json::Value *)Json::Value::operator[](a4, v13);
      Json::Value::Value((Json::Value *)v41, v14);
      if ( v41[8] == 4 )
      {
        v32 = 0;
        if ( (unsigned __int8)MapControl::StringKeyToEnumKeyMap::tryGetKey(v13, &v32) )
        {
          v15 = Json::Value::asString(v41, v42);
          v16 = (_QWORD *)std::map<enum MapControl::ConfigurationKeys,std::wstring>::_Try_emplace<enum MapControl::ConfigurationKeys,>(
                            (__int64 *)v33,
                            (__int64)&v40,
                            (__int64)&v32);
          std::wstring::operator=(*v16 + 40LL, v15);
          std::wstring::_Tidy_deallocate(v42);
        }
      }
      Json::Value::~Value((Json::Value *)v41);
      v13 += 32;
    }
    while ( v13 != v10 );
    v40 = (char *)this + 48;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    v17 = v31;
    Overrides = (__int64 *)MapControl::ConfigurationManager::getOverrides(this, a2, v31);
    v32 = 2;
    std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](Overrides, &v32);
    Pal::Date::convertStringToDate((Pal::Date *)&v34);
    v19 = v35;
    if ( (unsigned int)anonymous_namespace_::CompareFILETIME(*v35, v34) == -1 )
      goto LABEL_27;
    v20 = 0;
    LODWORD(v31) = 2;
    if ( !std::_Tree<std::_Tmap_traits<enum MapControl::ConfigurationKeys,std::wstring,std::less<enum MapControl::ConfigurationKeys>,std::allocator<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>,0>>::count(
            v33,
            &v31) )
    {
      std::wstring::wstring(v41);
      v21 = *v19;
      std::wstring::wstring(v42, L"%d/%02d/%02d %02d:%02d:%02d");
      Pal::DateImplWindows::convertDateToString(v21, v42, v41);
      std::wstring::_Tidy_deallocate(v42);
      LODWORD(v31) = 2;
      v22 = std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](Overrides, &v31);
      std::wstring::operator=(v22, v41);
      std::wstring::_Tidy_deallocate(v41);
    }
    LODWORD(v31) = 1;
    if ( !std::_Tree<std::_Tmap_traits<enum MapControl::ConfigurationKeys,std::wstring,std::less<enum MapControl::ConfigurationKeys>,std::allocator<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>,0>>::count(
            v33,
            &v31) )
    {
      LODWORD(v31) = v23;
      v24 = std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](Overrides, &v31);
      std::wstring::operator=(v24, v39);
    }
    LODWORD(v31) = 0;
    if ( !std::_Tree<std::_Tmap_traits<enum MapControl::ConfigurationKeys,std::wstring,std::less<enum MapControl::ConfigurationKeys>,std::allocator<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>,0>>::count(
            v33,
            &v31) )
    {
      LODWORD(v31) = 0;
      v25 = std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](Overrides, &v31);
      std::wstring::operator=(v25, v17);
    }
    v26 = *(_QWORD *)v33[0];
    v31 = *(_QWORD *)v33[0];
    while ( !*(_BYTE *)(v26 + 25) )
    {
      v27 = v26 + 32;
      if ( (unsigned __int8)MapControl::LocaleMapConfiguration::validateSetting(*(unsigned int *)(v26 + 32), v26 + 40) )
      {
        v28 = (_QWORD *)std::map<enum MapControl::ConfigurationKeys,std::wstring>::_Try_emplace<enum MapControl::ConfigurationKeys,>(
                          Overrides,
                          (__int64)&v39,
                          v27);
        std::wstring::operator=(*v28 + 40LL, v27 + 8);
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>>,std::_Iterator_base0>::operator++(&v31);
      v26 = v31;
    }
    v29 = (_QWORD *)*((_QWORD *)this + 19);
    v30 = (_QWORD *)*((_QWORD *)this + 18);
    if ( v30 != v29 )
    {
      do
      {
        if ( (unsigned __int8)MapControl::LocaleMapConfiguration::applyOverrides(*v30, Overrides) || v20 )
          v20 = 1;
        v30 += 2;
      }
      while ( v30 != v29 );
      if ( v20 )
LABEL_27:
        MapControl::ConfigurationManager::updateFileCache(this);
    }
    Microsoft::WRL::Details::MakeAllocator<Pal::Detail::OfflineDetectorWrapper>::~MakeAllocator<Pal::Detail::OfflineDetectorWrapper>(&v34);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    if ( v11 )
    {
      v12 = v37;
      goto LABEL_30;
    }
  }
  std::_Tree_val<std::_Tree_simple_types<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>,void *>>>(
    v33,
    (__int64)v33);
}

```

## disassembly

```asm
0x18003cb9c  push    rbp
0x18003cb9e  push    rbx
0x18003cb9f  push    rsi
0x18003cba0  push    rdi
0x18003cba1  push    r12
0x18003cba3  push    r13
0x18003cba5  push    r14
0x18003cba7  push    r15
0x18003cba9  lea     rbp, [rsp-0Fh]
0x18003cbae  sub     rsp, 0E8h
0x18003cbb5  mov     rax, cs:__security_cookie
0x18003cbbc  xor     rax, rsp
0x18003cbbf  mov     [rbp+47h+var_50], rax
0x18003cbc3  mov     r15, r9
0x18003cbc6  mov     [rsp+120h+var_100], r8
0x18003cbcb  mov     r12, rdx
0x18003cbce  mov     [rbp+47h+var_B8], rdx
0x18003cbd2  mov     r13, rcx
0x18003cbd5  mov     rax, [rbp+47h+arg_20]
0x18003cbd9  mov     [rsp+120h+var_D8], rax
0x18003cbde  lea     rcx, [rsp+120h+var_F0]
0x18003cbe3  call    ??0?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAA@XZ; std::map<MapControl::ConfigurationKeys,std::wstring>::map<MapControl::ConfigurationKeys,std::wstring>(void)
0x18003cbe8  nop
0x18003cbe9  lea     rdx, [rsp+120h+var_D0]
0x18003cbee  mov     rcx, r15
0x18003cbf1  call    ?getMemberNames@Value@Json@@QEBA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; Json::Value::getMemberNames(void)
0x18003cbf6  nop
0x18003cbf7  mov     r14, [rsp+120h+var_C8]
0x18003cbfc  mov     rsi, [rsp+120h+var_D0]
0x18003cc01  cmp     rsi, r14
0x18003cc04  jnz     short loc_18003CC17
0x18003cc06  test    rsi, rsi
0x18003cc09  jz      loc_18003CED3
0x18003cc0f  mov     rdx, r14
0x18003cc12  jmp     loc_18003CEB7
0x18003cc17  mov     rdi, rsi
0x18003cc1a  mov     rdx, rdi
0x18003cc1d  mov     rcx, r15
0x18003cc20  call    ??AValue@Json@@QEBAAEBV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Json::Value::operator[](std::wstring const &)
0x18003cc25  mov     rdx, rax; struct Json::Value *
0x18003cc28  lea     rcx, [rbp+47h+var_98]; this
0x18003cc2c  call    ??0Value@Json@@QEAA@AEBV01@@Z; Json::Value::Value(Json::Value const &)
0x18003cc31  nop
0x18003cc32  cmp     [rbp+47h+var_90], 4
0x18003cc36  jnz     short loc_18003CC8E
0x18003cc38  mov     [rsp+120h+var_F8], 0
0x18003cc40  lea     rdx, [rsp+120h+var_F8]
0x18003cc45  mov     rcx, rdi
0x18003cc48  call    ?tryGetKey@StringKeyToEnumKeyMap@MapControl@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAW4ConfigurationKeys@2@@Z; MapControl::StringKeyToEnumKeyMap::tryGetKey(std::wstring const &,MapControl::ConfigurationKeys *)
0x18003cc4d  test    al, al
0x18003cc4f  jz      short loc_18003CC8E
0x18003cc51  lea     rdx, [rbp+47h+var_70]
0x18003cc55  lea     rcx, [rbp+47h+var_98]
0x18003cc59  call    ?asString@Value@Json@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Json::Value::asString(void)
0x18003cc5e  mov     rbx, rax
0x18003cc61  lea     r8, [rsp+120h+var_F8]
0x18003cc66  lea     rdx, [rbp+47h+var_A8]
0x18003cc6a  lea     rcx, [rsp+120h+var_F0]
0x18003cc6f  call    ??$_Try_emplace@W4ConfigurationKeys@MapControl@@$$V@?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::_Try_emplace<MapControl::ConfigurationKeys,>(MapControl::ConfigurationKeys &&)
0x18003cc74  mov     rcx, [rax]
0x18003cc77  add     rcx, 28h ; '('
0x18003cc7b  mov     rdx, rbx
0x18003cc7e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003cc83  nop
0x18003cc84  lea     rcx, [rbp+47h+var_70]
0x18003cc88  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003cc8d  nop
0x18003cc8e  lea     rcx, [rbp+47h+var_98]; this
0x18003cc92  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x18003cc97  add     rdi, 20h ; ' '
0x18003cc9b  cmp     rdi, r14
0x18003cc9e  jnz     loc_18003CC1A
0x18003cca4  lea     rbx, [r13+30h]
0x18003cca8  mov     [rbp+47h+var_A8], rbx
0x18003ccac  mov     rcx, rbx; lpCriticalSection
0x18003ccaf  call    cs:__imp_EnterCriticalSection
0x18003ccb5  nop
0x18003ccb6  mov     r15, [rsp+120h+var_100]
0x18003ccbb  mov     r8, r15
0x18003ccbe  mov     rdx, r12
0x18003ccc1  mov     rcx, r13
0x18003ccc4  call    ?getOverrides@ConfigurationManager@MapControl@@AEAAAEAV?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@0@Z; MapControl::ConfigurationManager::getOverrides(std::wstring const &,std::wstring const &)
0x18003ccc9  mov     r12, rax
0x18003cccc  mov     [rsp+120h+var_F8], 2
0x18003ccd4  lea     rdx, [rsp+120h+var_F8]
0x18003ccd9  mov     rcx, rax
0x18003ccdc  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x18003cce1  mov     rdx, rax
0x18003cce4  lea     rcx, [rsp+120h+var_E0]; this
0x18003cce9  call    ?convertStringToDate@Date@Pal@@SA?AV12@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Pal::Date::convertStringToDate(std::wstring const &)
0x18003ccee  nop
0x18003ccef  mov     rdx, [rsp+120h+var_E0]
0x18003ccf4  mov     rdi, [rsp+120h+var_D8]
0x18003ccf9  mov     rcx, [rdi]
0x18003ccfc  call    _anonymous_namespace___CompareFILETIME
0x18003cd01  cmp     eax, 0FFFFFFFFh
0x18003cd04  jz      loc_18003CE8F
0x18003cd0a  xor     r14b, r14b
0x18003cd0d  mov     dword ptr [rsp+120h+var_100], 2
0x18003cd15  lea     rdx, [rsp+120h+var_100]
0x18003cd1a  lea     rcx, [rsp+120h+var_F0]
0x18003cd1f  call    ?count@?$_Tree@V?$_Tmap_traits@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@QEBA_KAEBW4ConfigurationKeys@MapControl@@@Z; std::_Tree<std::_Tmap_traits<MapControl::ConfigurationKeys,std::wstring,std::less<MapControl::ConfigurationKeys>,std::allocator<std::pair<MapControl::ConfigurationKeys const,std::wstring>>,0>>::count(MapControl::ConfigurationKeys const &)
0x18003cd24  test    rax, rax
0x18003cd27  jnz     short loc_18003CD8C
0x18003cd29  lea     rcx, [rbp+47h+var_98]
0x18003cd2d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003cd32  nop
0x18003cd33  mov     rdi, [rdi]
0x18003cd36  lea     rdx, ?kDateStringFormat@Date@Pal@@2QBGB; "%d/%02d/%02d %02d:%02d:%02d"
0x18003cd3d  lea     rcx, [rbp+47h+var_70]
0x18003cd41  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003cd46  nop
0x18003cd47  lea     r8, [rbp+47h+var_98]
0x18003cd4b  lea     rdx, [rbp+47h+var_70]
0x18003cd4f  mov     rcx, rdi
0x18003cd52  call    ?convertDateToString@DateImplWindows@Pal@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV34@@Z; Pal::DateImplWindows::convertDateToString(std::wstring const &,std::wstring *)
0x18003cd57  nop
0x18003cd58  lea     rcx, [rbp+47h+var_70]
0x18003cd5c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003cd61  mov     dword ptr [rsp+120h+var_100], 2
0x18003cd69  lea     rdx, [rsp+120h+var_100]
0x18003cd6e  mov     rcx, r12
0x18003cd71  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x18003cd76  mov     rcx, rax
0x18003cd79  lea     rdx, [rbp+47h+var_98]
0x18003cd7d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003cd82  nop
0x18003cd83  lea     rcx, [rbp+47h+var_98]
0x18003cd87  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003cd8c  mov     r10d, 1
0x18003cd92  mov     dword ptr [rsp+120h+var_100], r10d
0x18003cd97  lea     rdx, [rsp+120h+var_100]
0x18003cd9c  lea     rcx, [rsp+120h+var_F0]
0x18003cda1  call    ?count@?$_Tree@V?$_Tmap_traits@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@QEBA_KAEBW4ConfigurationKeys@MapControl@@@Z; std::_Tree<std::_Tmap_traits<MapControl::ConfigurationKeys,std::wstring,std::less<MapControl::ConfigurationKeys>,std::allocator<std::pair<MapControl::ConfigurationKeys const,std::wstring>>,0>>::count(MapControl::ConfigurationKeys const &)
0x18003cda6  test    rax, rax
0x18003cda9  jnz     short loc_18003CDC9
0x18003cdab  mov     dword ptr [rsp+120h+var_100], r10d
0x18003cdb0  lea     rdx, [rsp+120h+var_100]
0x18003cdb5  mov     rcx, r12
0x18003cdb8  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x18003cdbd  mov     rcx, rax
0x18003cdc0  mov     rdx, [rbp+47h+var_B8]
0x18003cdc4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003cdc9  mov     dword ptr [rsp+120h+var_100], 0
0x18003cdd1  lea     rdx, [rsp+120h+var_100]
0x18003cdd6  lea     rcx, [rsp+120h+var_F0]
0x18003cddb  call    ?count@?$_Tree@V?$_Tmap_traits@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@QEBA_KAEBW4ConfigurationKeys@MapControl@@@Z; std::_Tree<std::_Tmap_traits<MapControl::ConfigurationKeys,std::wstring,std::less<MapControl::ConfigurationKeys>,std::allocator<std::pair<MapControl::ConfigurationKeys const,std::wstring>>,0>>::count(MapControl::ConfigurationKeys const &)
0x18003cde0  test    rax, rax
0x18003cde3  jnz     short loc_18003CE01
0x18003cde5  mov     dword ptr [rsp+120h+var_100], eax
0x18003cde9  lea     rdx, [rsp+120h+var_100]
0x18003cdee  mov     rcx, r12
0x18003cdf1  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x18003cdf6  mov     rcx, rax
0x18003cdf9  mov     rdx, r15
0x18003cdfc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003ce01  mov     rax, [rsp+120h+var_F0]
0x18003ce06  mov     rax, [rax]
0x18003ce09  mov     [rsp+120h+var_100], rax
0x18003ce0e  cmp     byte ptr [rax+19h], 0
0x18003ce12  jnz     short loc_18003CE57
0x18003ce14  lea     rdi, [rax+20h]
0x18003ce18  lea     rdx, [rdi+8]
0x18003ce1c  mov     ecx, [rdi]
0x18003ce1e  call    ?validateSetting@LocaleMapConfiguration@MapControl@@CA_NW4ConfigurationKeys@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MapControl::LocaleMapConfiguration::validateSetting(MapControl::ConfigurationKeys,std::wstring const &)
0x18003ce23  test    al, al
0x18003ce25  jz      short loc_18003CE46
0x18003ce27  mov     r8, rdi
0x18003ce2a  lea     rdx, [rbp+47h+var_B8]
0x18003ce2e  mov     rcx, r12
0x18003ce31  call    ??$_Try_emplace@W4ConfigurationKeys@MapControl@@$$V@?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::_Try_emplace<MapControl::ConfigurationKeys,>(MapControl::ConfigurationKeys &&)
0x18003ce36  mov     rcx, [rax]
0x18003ce39  add     rcx, 28h ; '('
0x18003ce3d  lea     rdx, [rdi+8]
0x18003ce41  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003ce46  lea     rcx, [rsp+120h+var_100]
0x18003ce4b  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<MapControl::ConfigurationKeys const,std::wstring>>>,std::_Iterator_base0>::operator++(void)
0x18003ce50  mov     rax, [rsp+120h+var_100]
0x18003ce55  jmp     short loc_18003CE0E
0x18003ce57  mov     r15, [r13+98h]
0x18003ce5e  mov     rdi, [r13+90h]
0x18003ce65  cmp     rdi, r15
0x18003ce68  jz      short loc_18003CE98
0x18003ce6a  mov     rdx, r12
0x18003ce6d  mov     rcx, [rdi]
0x18003ce70  call    ?applyOverrides@LocaleMapConfiguration@MapControl@@AEAA_NAEBV?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@@Z; MapControl::LocaleMapConfiguration::applyOverrides(std::map<MapControl::ConfigurationKeys,std::wstring> const &)
0x18003ce75  test    al, al
0x18003ce77  jnz     short loc_18003CE7E
0x18003ce79  test    r14b, r14b
0x18003ce7c  jz      short loc_18003CE81
0x18003ce7e  mov     r14b, 1
0x18003ce81  add     rdi, 10h
0x18003ce85  cmp     rdi, r15
0x18003ce88  jnz     short loc_18003CE6A
0x18003ce8a  test    r14b, r14b
0x18003ce8d  jz      short loc_18003CE98
0x18003ce8f  mov     rcx, r13; this
0x18003ce92  call    ?updateFileCache@ConfigurationManager@MapControl@@AEAAXXZ; MapControl::ConfigurationManager::updateFileCache(void)
0x18003ce97  nop
0x18003ce98  lea     rcx, [rsp+120h+var_E0]
0x18003ce9d  call    ??1?$MakeAllocator@VOfflineDetectorWrapper@Detail@Pal@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Pal::Detail::OfflineDetectorWrapper>::~MakeAllocator<Pal::Detail::OfflineDetectorWrapper>(void)
0x18003cea2  nop
0x18003cea3  mov     rcx, rbx; lpCriticalSection
0x18003cea6  call    cs:__imp_LeaveCriticalSection
0x18003ceac  nop
0x18003cead  test    rsi, rsi
0x18003ceb0  jz      short loc_18003CED3
0x18003ceb2  mov     rdx, [rsp+120h+var_C8]
0x18003ceb7  mov     rcx, rsi
0x18003ceba  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18003cebf  mov     rdx, [rbp+47h+var_C0]
0x18003cec3  sub     rdx, rsi
0x18003cec6  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18003ceca  mov     rcx, rsi
0x18003cecd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003ced2  nop
0x18003ced3  lea     rcx, [rsp+120h+var_F0]
0x18003ced8  mov     rdx, rcx
0x18003cedb  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<MapControl::ConfigurationKeys const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<MapControl::ConfigurationKeys const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<MapControl::ConfigurationKeys const,std::wstring>,void *>> &)
0x18003cee0  mov     rcx, [rbp+47h+var_50]
0x18003cee4  xor     rcx, rsp; StackCookie
0x18003cee7  call    __security_check_cookie
0x18003ceec  add     rsp, 0E8h
0x18003cef3  pop     r15
0x18003cef5  pop     r14
0x18003cef7  pop     r13
0x18003cef9  pop     r12
0x18003cefb  pop     rdi
0x18003cefc  pop     rsi
0x18003cefd  pop     rbx
0x18003cefe  pop     rbp
0x18003ceff  retn
```
