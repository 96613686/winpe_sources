# MapControl::ConfigurationManager::submitOverridesImpl(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Json::Value const &,Pal::Date const &,MapControl::ConfigurationManager::OverridesSource)

- ea: `0x180022764`
- end: `0x180022ad8`
- name: `?submitOverridesImpl@ConfigurationManager@MapControl@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEBVValue@Json@@AEBVDate@Pal@@W4OverridesSource@12@@Z`
- size: `884`
- prototype: ``
- caller_count: `2`
- callee_count: `29`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800222e4`
- `0x1800225d8`

## callees

- `0x1800094a0`
- `0x18000b938`
- `0x18000ba50`
- `0x18000bb60`
- `0x18000c354`
- `0x18000c850`
- `0x180011ddc`
- `0x180011e18`
- `0x180012158`
- `0x180012c74`
- `0x18001615c`
- `0x18001bbe8`
- `0x18001d6e4`
- `0x18001dc60`
- `0x18001e494`
- `0x18001ef80`
- `0x18001fbe4`
- `0x18002093c`
- `0x1800211b0`
- `0x180022764`
- `0x180022ae0`
- `0x180023f84`
- `0x18002470c`
- `0x1800252ac`
- `0x18003417c`
- `0x180034538`
- `0x1800348d8`
- `0x180035110`
- `0x180035934`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022876`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180022876`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022a80`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022a80`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall MapControl::ConfigurationManager::submitOverridesImpl(
        MapControl::ConfigurationManager *this,
        __int64 a2,
        __int64 a3,
        _BYTE *a4,
        _QWORD *a5,
        int a6)
{
  MapControl::ConfigurationManager *v7; // r12
  __int64 v8; // r8
  __int64 v9; // r9
  char *v10; // r15
  void *v11; // r14
  char *v12; // rdx
  char *v13; // rdi
  const struct Json::Value *v14; // rax
  __int64 v15; // rbx
  _QWORD *v16; // rax
  struct _RTL_CRITICAL_SECTION *v17; // rbx
  __int64 *Overrides; // r13
  char v19; // r15
  __int64 *v20; // r10
  __int64 v21; // rdi
  __int64 v22; // rax
  int v23; // r10d
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  _DWORD *v27; // rdi
  _QWORD *v28; // rax
  _QWORD *v29; // r12
  _QWORD *v30; // rdi
  _QWORD *v31; // [rsp+20h] [rbp-A9h] BYREF
  int v32; // [rsp+28h] [rbp-A1h] BYREF
  __int64 v33; // [rsp+30h] [rbp-99h] BYREF
  void *v34[2]; // [rsp+38h] [rbp-91h] BYREF
  MapControl::ConfigurationManager *v35; // [rsp+48h] [rbp-81h]
  __int64 v36; // [rsp+50h] [rbp-79h] BYREF
  __int64 v37; // [rsp+58h] [rbp-71h] BYREF
  char *v38; // [rsp+68h] [rbp-61h] BYREF
  char *v39; // [rsp+70h] [rbp-59h]
  __int64 v40; // [rsp+78h] [rbp-51h]
  char *v41; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v42[40]; // [rsp+90h] [rbp-39h] BYREF
  _BYTE v43[32]; // [rsp+B8h] [rbp-11h] BYREF

  v33 = a3;
  v37 = a2;
  v7 = this;
  v35 = this;
  v31 = a5;
  std::map<enum MapControl::ConfigurationKeys,std::wstring>::map<enum MapControl::ConfigurationKeys,std::wstring>(v34);
  Json::Value::getMemberNames(a4, &v38);
  v10 = v39;
  v11 = v38;
  if ( v38 == v39 )
  {
    if ( v38 )
    {
      v12 = v39;
LABEL_32:
      std::_Destroy_range<std::allocator<std::wstring>>(v11, v12, v8, v9);
      std::_Deallocate<16>(v11, (v40 - (_QWORD)v11) & 0xFFFFFFFFFFFFFFE0uLL);
      goto LABEL_33;
    }
    goto LABEL_33;
  }
  v13 = v38;
  do
  {
    v14 = (const struct Json::Value *)Json::Value::operator[](a4, v13);
    Json::Value::Value((Json::Value *)v42, v14);
    if ( v42[8] == 4 )
    {
      v32 = 0;
      if ( (unsigned __int8)MapControl::StringKeyToEnumKeyMap::tryGetKey(v13, &v32) )
      {
        v15 = Json::Value::asString(v42, v43);
        v16 = (_QWORD *)std::map<enum MapControl::ConfigurationKeys,std::wstring>::_Try_emplace<enum MapControl::ConfigurationKeys,>(
                          (__int64 *)v34,
                          (__int64)&v41,
                          &v32);
        std::wstring::operator=(*v16 + 40LL, v15);
        std::wstring::_Tidy_deallocate(v43);
      }
    }
    Json::Value::~Value((Json::Value *)v42);
    v13 += 32;
  }
  while ( v13 != v10 );
  v17 = (struct _RTL_CRITICAL_SECTION *)((char *)v7 + 48);
  v41 = (char *)v7 + 48;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 48));
  Overrides = (__int64 *)MapControl::ConfigurationManager::getOverrides(v7, v37, v33);
  v32 = 2;
  std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](Overrides, &v32);
  Pal::Date::convertStringToDate((Pal::Date *)&v36);
  if ( (unsigned int)anonymous_namespace_::CompareFILETIME(*v31, v36) == -1 )
    goto LABEL_28;
  v19 = 0;
  LODWORD(v31) = 2;
  if ( !std::_Tree<std::_Tmap_traits<enum MapControl::ConfigurationKeys,std::wstring,std::less<enum MapControl::ConfigurationKeys>,std::allocator<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>,0>>::count(
          v34,
          &v31) )
  {
    std::wstring::wstring((__int64)v42);
    v21 = *v20;
    std::wstring::wstring((__int64)v43, (__int64)L"%d/%02d/%02d %02d:%02d:%02d");
    Pal::DateImplWindows::convertDateToString(v21, v43, v42);
    std::wstring::_Tidy_deallocate(v43);
    LODWORD(v31) = 2;
    v22 = std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](Overrides, &v31);
    std::wstring::operator=(v22);
    std::wstring::_Tidy_deallocate(v42);
  }
  LODWORD(v31) = 1;
  if ( !std::_Tree<std::_Tmap_traits<enum MapControl::ConfigurationKeys,std::wstring,std::less<enum MapControl::ConfigurationKeys>,std::allocator<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>,0>>::count(
          v34,
          &v31) )
  {
    LODWORD(v31) = v23;
    v24 = std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](Overrides, &v31);
    std::wstring::operator=(v24);
  }
  LODWORD(v31) = 0;
  if ( !std::_Tree<std::_Tmap_traits<enum MapControl::ConfigurationKeys,std::wstring,std::less<enum MapControl::ConfigurationKeys>,std::allocator<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>,0>>::count(
          v34,
          &v31) )
  {
    LODWORD(v31) = 0;
    v25 = std::map<enum MapControl::ConfigurationKeys,std::wstring>::operator[](Overrides, &v31);
    std::wstring::operator=(v25);
  }
  v26 = *(_QWORD *)v34[0];
  v33 = *(_QWORD *)v34[0];
  while ( !*(_BYTE *)(v26 + 25) )
  {
    v27 = (_DWORD *)(v26 + 32);
    if ( (unsigned __int8)MapControl::LocaleMapConfiguration::validateSetting(*(unsigned int *)(v26 + 32), v26 + 40) )
    {
      v28 = (_QWORD *)std::map<enum MapControl::ConfigurationKeys,std::wstring>::_Try_emplace<enum MapControl::ConfigurationKeys,>(
                        Overrides,
                        (__int64)&v37,
                        v27);
      std::wstring::operator=(*v28 + 40LL);
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>>,std::_Iterator_base0>::operator++(&v33);
    v26 = v33;
  }
  v29 = (_QWORD *)*((_QWORD *)v35 + 19);
  v30 = (_QWORD *)*((_QWORD *)v35 + 18);
  if ( v30 != v29 )
  {
    do
    {
      if ( (unsigned __int8)MapControl::LocaleMapConfiguration::applyOverrides(*v30, Overrides) || v19 )
        v19 = 1;
      v30 += 2;
    }
    while ( v30 != v29 );
    if ( v19 )
    {
      v7 = v35;
LABEL_28:
      if ( a6 )
        MapControl::ConfigurationManager::updateFileCache(v7);
    }
  }
  Microsoft::WRL::Details::MakeAllocator<ConfigurationManagerAdapter>::~MakeAllocator<ConfigurationManagerAdapter>(&v36);
  LeaveCriticalSection(v17);
  if ( v11 )
  {
    v12 = v39;
    goto LABEL_32;
  }
LABEL_33:
  std::_Tree_val<std::_Tree_simple_types<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<enum MapControl::ConfigurationKeys const,std::wstring>,void *>>>(
    v34,
    (__int64)v34);
}

```

## disassembly

```asm
0x180022764  push    rbp
0x180022766  push    rbx
0x180022767  push    rdi
0x180022768  push    r12
0x18002276a  push    r13
0x18002276c  push    r14
0x18002276e  push    r15
0x180022770  lea     rbp, [rsp-17h]
0x180022775  sub     rsp, 0E0h
0x18002277c  mov     rax, cs:__security_cookie
0x180022783  xor     rax, rsp
0x180022786  mov     [rbp+47h+var_38], rax
0x18002278a  mov     r13, r9
0x18002278d  mov     [rsp+110h+var_E0], r8
0x180022792  mov     [rbp+47h+var_B8], rdx
0x180022796  mov     r12, rcx
0x180022799  mov     [rsp+110h+var_C8], rcx
0x18002279e  mov     rax, [rbp+47h+arg_20]
0x1800227a2  mov     [rsp+110h+var_F0], rax
0x1800227a7  lea     rcx, [rsp+110h+var_D8]
0x1800227ac  call    ??0?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAA@XZ; std::map<MapControl::ConfigurationKeys,std::wstring>::map<MapControl::ConfigurationKeys,std::wstring>(void)
0x1800227b1  nop
0x1800227b2  lea     rdx, [rbp+47h+var_A8]
0x1800227b6  mov     rcx, r13
0x1800227b9  call    ?getMemberNames@Value@Json@@QEBA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; Json::Value::getMemberNames(void)
0x1800227be  nop
0x1800227bf  mov     r15, [rbp+47h+var_A0]
0x1800227c3  mov     r14, [rbp+47h+var_A8]
0x1800227c7  cmp     r14, r15
0x1800227ca  jnz     short loc_1800227DD
0x1800227cc  test    r14, r14
0x1800227cf  jz      loc_180022AAC
0x1800227d5  mov     rdx, r15
0x1800227d8  jmp     loc_180022A90
0x1800227dd  mov     rdi, r14
0x1800227e0  mov     rdx, rdi
0x1800227e3  mov     rcx, r13
0x1800227e6  call    ??AValue@Json@@QEBAAEBV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Json::Value::operator[](std::wstring const &)
0x1800227eb  mov     rdx, rax; struct Json::Value *
0x1800227ee  lea     rcx, [rbp+47h+var_80]; this
0x1800227f2  call    ??0Value@Json@@QEAA@AEBV01@@Z; Json::Value::Value(Json::Value const &)
0x1800227f7  nop
0x1800227f8  cmp     [rbp+47h+var_78], 4
0x1800227fc  jnz     short loc_180022854
0x1800227fe  mov     [rsp+110h+var_E8], 0
0x180022806  lea     rdx, [rsp+110h+var_E8]
0x18002280b  mov     rcx, rdi
0x18002280e  call    ?tryGetKey@StringKeyToEnumKeyMap@MapControl@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAW4ConfigurationKeys@2@@Z; MapControl::StringKeyToEnumKeyMap::tryGetKey(std::wstring const &,MapControl::ConfigurationKeys *)
0x180022813  test    al, al
0x180022815  jz      short loc_180022854
0x180022817  lea     rdx, [rbp+47h+var_58]
0x18002281b  lea     rcx, [rbp+47h+var_80]
0x18002281f  call    ?asString@Value@Json@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Json::Value::asString(void)
0x180022824  mov     rbx, rax
0x180022827  lea     r8, [rsp+110h+var_E8]
0x18002282c  lea     rdx, [rbp+47h+var_90]
0x180022830  lea     rcx, [rsp+110h+var_D8]
0x180022835  call    ??$_Try_emplace@W4ConfigurationKeys@MapControl@@$$V@?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::_Try_emplace<MapControl::ConfigurationKeys,>(MapControl::ConfigurationKeys &&)
0x18002283a  mov     rcx, [rax]
0x18002283d  add     rcx, 28h ; '('
0x180022841  mov     rdx, rbx
0x180022844  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180022849  nop
0x18002284a  lea     rcx, [rbp+47h+var_58]
0x18002284e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022853  nop
0x180022854  lea     rcx, [rbp+47h+var_80]; this
0x180022858  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x18002285d  add     rdi, 20h ; ' '
0x180022861  cmp     rdi, r15
0x180022864  jnz     loc_1800227E0
0x18002286a  lea     rbx, [r12+30h]
0x18002286f  mov     [rbp+47h+var_90], rbx
0x180022873  mov     rcx, rbx; lpCriticalSection
0x180022876  call    cs:__imp_EnterCriticalSection
0x18002287c  nop
0x18002287d  mov     r8, [rsp+110h+var_E0]
0x180022882  mov     rdi, [rbp+47h+var_B8]
0x180022886  mov     rdx, rdi
0x180022889  mov     rcx, r12
0x18002288c  call    ?getOverrides@ConfigurationManager@MapControl@@AEAAAEAV?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@0@Z; MapControl::ConfigurationManager::getOverrides(std::wstring const &,std::wstring const &)
0x180022891  mov     r13, rax
0x180022894  mov     [rsp+110h+var_E8], 2
0x18002289c  lea     rdx, [rsp+110h+var_E8]
0x1800228a1  mov     rcx, rax
0x1800228a4  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x1800228a9  mov     rdx, rax
0x1800228ac  lea     rcx, [rbp+47h+var_C0]; this
0x1800228b0  call    ?convertStringToDate@Date@Pal@@SA?AV12@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Pal::Date::convertStringToDate(std::wstring const &)
0x1800228b5  nop
0x1800228b6  mov     rdx, [rbp+47h+var_C0]
0x1800228ba  mov     r10, [rsp+110h+var_F0]
0x1800228bf  mov     rcx, [r10]
0x1800228c2  call    _anonymous_namespace___CompareFILETIME
0x1800228c7  cmp     eax, 0FFFFFFFFh
0x1800228ca  jz      loc_180022A64
0x1800228d0  xor     r15b, r15b
0x1800228d3  mov     r12d, 2
0x1800228d9  mov     dword ptr [rsp+110h+var_F0], r12d
0x1800228de  lea     rdx, [rsp+110h+var_F0]
0x1800228e3  lea     rcx, [rsp+110h+var_D8]
0x1800228e8  call    ?count@?$_Tree@V?$_Tmap_traits@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@QEBA_KAEBW4ConfigurationKeys@MapControl@@@Z; std::_Tree<std::_Tmap_traits<MapControl::ConfigurationKeys,std::wstring,std::less<MapControl::ConfigurationKeys>,std::allocator<std::pair<MapControl::ConfigurationKeys const,std::wstring>>,0>>::count(MapControl::ConfigurationKeys const &)
0x1800228ed  test    rax, rax
0x1800228f0  jnz     short loc_180022956
0x1800228f2  lea     rcx, [rbp+47h+var_80]
0x1800228f6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800228fb  nop
0x1800228fc  mov     rdi, [r10]
0x1800228ff  lea     rdx, ?kDateStringFormat@Date@Pal@@2QBGB; "%d/%02d/%02d %02d:%02d:%02d"
0x180022906  lea     rcx, [rbp+47h+var_58]
0x18002290a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002290f  nop
0x180022910  lea     r8, [rbp+47h+var_80]
0x180022914  lea     rdx, [rbp+47h+var_58]
0x180022918  mov     rcx, rdi
0x18002291b  call    ?convertDateToString@DateImplWindows@Pal@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV34@@Z; Pal::DateImplWindows::convertDateToString(std::wstring const &,std::wstring *)
0x180022920  nop
0x180022921  lea     rcx, [rbp+47h+var_58]
0x180022925  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002292a  mov     dword ptr [rsp+110h+var_F0], r12d
0x18002292f  lea     rdx, [rsp+110h+var_F0]
0x180022934  mov     rcx, r13
0x180022937  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x18002293c  mov     rcx, rax
0x18002293f  lea     rdx, [rbp+47h+var_80]
0x180022943  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180022948  nop
0x180022949  lea     rcx, [rbp+47h+var_80]
0x18002294d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180022952  mov     rdi, [rbp+47h+var_B8]
0x180022956  mov     r10d, 1
0x18002295c  mov     dword ptr [rsp+110h+var_F0], r10d
0x180022961  lea     rdx, [rsp+110h+var_F0]
0x180022966  lea     rcx, [rsp+110h+var_D8]
0x18002296b  call    ?count@?$_Tree@V?$_Tmap_traits@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@QEBA_KAEBW4ConfigurationKeys@MapControl@@@Z; std::_Tree<std::_Tmap_traits<MapControl::ConfigurationKeys,std::wstring,std::less<MapControl::ConfigurationKeys>,std::allocator<std::pair<MapControl::ConfigurationKeys const,std::wstring>>,0>>::count(MapControl::ConfigurationKeys const &)
0x180022970  test    rax, rax
0x180022973  jnz     short loc_180022992
0x180022975  mov     dword ptr [rsp+110h+var_F0], r10d
0x18002297a  lea     rdx, [rsp+110h+var_F0]
0x18002297f  mov     rcx, r13
0x180022982  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x180022987  mov     rcx, rax
0x18002298a  mov     rdx, rdi
0x18002298d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180022992  mov     dword ptr [rsp+110h+var_F0], 0
0x18002299a  lea     rdx, [rsp+110h+var_F0]
0x18002299f  lea     rcx, [rsp+110h+var_D8]
0x1800229a4  call    ?count@?$_Tree@V?$_Tmap_traits@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@$0A@@std@@@std@@QEBA_KAEBW4ConfigurationKeys@MapControl@@@Z; std::_Tree<std::_Tmap_traits<MapControl::ConfigurationKeys,std::wstring,std::less<MapControl::ConfigurationKeys>,std::allocator<std::pair<MapControl::ConfigurationKeys const,std::wstring>>,0>>::count(MapControl::ConfigurationKeys const &)
0x1800229a9  test    rax, rax
0x1800229ac  jnz     short loc_1800229CC
0x1800229ae  mov     dword ptr [rsp+110h+var_F0], eax
0x1800229b2  lea     rdx, [rsp+110h+var_F0]
0x1800229b7  mov     rcx, r13
0x1800229ba  call    ??A?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::operator[](MapControl::ConfigurationKeys &&)
0x1800229bf  mov     rcx, rax
0x1800229c2  mov     rdx, [rsp+110h+var_E0]
0x1800229c7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800229cc  mov     rax, [rsp+110h+var_D8]
0x1800229d1  mov     rax, [rax]
0x1800229d4  mov     [rsp+110h+var_E0], rax
0x1800229d9  cmp     byte ptr [rax+19h], 0
0x1800229dd  jnz     short loc_180022A22
0x1800229df  lea     rdi, [rax+20h]
0x1800229e3  lea     rdx, [rdi+8]
0x1800229e7  mov     ecx, [rdi]
0x1800229e9  call    ?validateSetting@LocaleMapConfiguration@MapControl@@CA_NW4ConfigurationKeys@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MapControl::LocaleMapConfiguration::validateSetting(MapControl::ConfigurationKeys,std::wstring const &)
0x1800229ee  test    al, al
0x1800229f0  jz      short loc_180022A11
0x1800229f2  mov     r8, rdi
0x1800229f5  lea     rdx, [rbp+47h+var_B8]
0x1800229f9  mov     rcx, r13
0x1800229fc  call    ??$_Try_emplace@W4ConfigurationKeys@MapControl@@$$V@?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@_N@1@$$QEAW4ConfigurationKeys@MapControl@@@Z; std::map<MapControl::ConfigurationKeys,std::wstring>::_Try_emplace<MapControl::ConfigurationKeys,>(MapControl::ConfigurationKeys &&)
0x180022a01  mov     rcx, [rax]
0x180022a04  add     rcx, 28h ; '('
0x180022a08  lea     rdx, [rdi+8]
0x180022a0c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180022a11  lea     rcx, [rsp+110h+var_E0]
0x180022a16  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<MapControl::ConfigurationKeys const,std::wstring>>>,std::_Iterator_base0>::operator++(void)
0x180022a1b  mov     rax, [rsp+110h+var_E0]
0x180022a20  jmp     short loc_1800229D9
0x180022a22  mov     rdi, [rsp+110h+var_C8]
0x180022a27  mov     r12, [rdi+98h]
0x180022a2e  mov     rdi, [rdi+90h]
0x180022a35  cmp     rdi, r12
0x180022a38  jz      short loc_180022A73
0x180022a3a  mov     rdx, r13
0x180022a3d  mov     rcx, [rdi]
0x180022a40  call    ?applyOverrides@LocaleMapConfiguration@MapControl@@AEAA_NAEBV?$map@W4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@W4ConfigurationKeys@MapControl@@@4@V?$allocator@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@4@@std@@@Z; MapControl::LocaleMapConfiguration::applyOverrides(std::map<MapControl::ConfigurationKeys,std::wstring> const &)
0x180022a45  test    al, al
0x180022a47  jnz     short loc_180022A4E
0x180022a49  test    r15b, r15b
0x180022a4c  jz      short loc_180022A51
0x180022a4e  mov     r15b, 1
0x180022a51  add     rdi, 10h
0x180022a55  cmp     rdi, r12
0x180022a58  jnz     short loc_180022A3A
0x180022a5a  test    r15b, r15b
0x180022a5d  jz      short loc_180022A73
0x180022a5f  mov     r12, [rsp+110h+var_C8]
0x180022a64  cmp     [rbp+47h+arg_28], 0
0x180022a68  jz      short loc_180022A73
0x180022a6a  mov     rcx, r12; this
0x180022a6d  call    ?updateFileCache@ConfigurationManager@MapControl@@AEAAXXZ; MapControl::ConfigurationManager::updateFileCache(void)
0x180022a72  nop
0x180022a73  lea     rcx, [rbp+47h+var_C0]
0x180022a77  call    ??1?$MakeAllocator@VConfigurationManagerAdapter@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<ConfigurationManagerAdapter>::~MakeAllocator<ConfigurationManagerAdapter>(void)
0x180022a7c  nop
0x180022a7d  mov     rcx, rbx; lpCriticalSection
0x180022a80  call    cs:__imp_LeaveCriticalSection
0x180022a86  nop
0x180022a87  test    r14, r14
0x180022a8a  jz      short loc_180022AAC
0x180022a8c  mov     rdx, [rbp+47h+var_A0]
0x180022a90  mov     rcx, r14
0x180022a93  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180022a98  mov     rdx, [rbp+47h+var_98]
0x180022a9c  sub     rdx, r14
0x180022a9f  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180022aa3  mov     rcx, r14
0x180022aa6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180022aab  nop
0x180022aac  lea     rcx, [rsp+110h+var_D8]
0x180022ab1  mov     rdx, rcx
0x180022ab4  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4ConfigurationKeys@MapControl@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<MapControl::ConfigurationKeys const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<MapControl::ConfigurationKeys const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<MapControl::ConfigurationKeys const,std::wstring>,void *>> &)
0x180022ab9  mov     rcx, [rbp+47h+var_38]
0x180022abd  xor     rcx, rsp; StackCookie
0x180022ac0  call    __security_check_cookie
0x180022ac5  add     rsp, 0E0h
0x180022acc  pop     r15
0x180022ace  pop     r14
0x180022ad0  pop     r13
0x180022ad2  pop     r12
0x180022ad4  pop     rdi
0x180022ad5  pop     rbx
0x180022ad6  pop     rbp
0x180022ad7  retn
```
