# Uev::TemplateAdministrator::ModifyTemplate(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x14003d840`
- end: `0x14003df9e`
- name: `?ModifyTemplate@TemplateAdministrator@Uev@@UEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z`
- size: `1886`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `43`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003e50`
- `0x140003e74`
- `0x140004ab4`
- `0x14000adb4`
- `0x14000ba60`
- `0x14000c2b8`
- `0x14000d1d8`
- `0x14000d2d8`
- `0x14000d7b4`
- `0x14000e30c`
- `0x14000e924`
- `0x14000ec40`
- `0x140019748`
- `0x140020568`
- `0x1400270f8`
- `0x1400322b8`
- `0x140034c14`
- `0x140034db4`
- `0x140036624`
- `0x140038f14`
- `0x140039d30`
- `0x14003a304`
- `0x14003a3a4`
- `0x14003a768`
- `0x14003ae64`
- `0x14003c630`
- `0x14003d094`
- `0x14003d840`
- `0x14003e7c8`
- `0x14003f370`
- `0x14003f580`
- `0x140045724`
- `0x140045af8`
- `0x140045db8`
- `0x140045ea8`
- `0x14005e318`
- `0x14005f2e8`
- `0x14005fa90`
- `0x140060310`
- `0x140061ea0`
- `0x140063f54`
- `0x140066060`
- `0x14009b010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x14003dce0`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x14003dce0`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x14003dd9c`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x14003dd9c`

## string_xrefs

- `0x14003dea2`: `Unable to set template registration timestamp`
- `0x14003df62`: ` is newer in the currently registered template.`
- `0x14003dee1`: `New template ID does not match the existing template ID`
- `0x14003df40`: `Template ID `

## pseudocode

```c
__int64 __fastcall Uev::TemplateAdministrator::ModifyTemplate(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  _WORD *v8; // rax
  __int64 i; // rbx
  int v10; // ebx
  int v11; // ebx
  __int64 j; // rbx
  int v13; // edi
  wchar_t **v14; // rdx
  size_t v15; // rdi
  const wchar_t *v16; // rdx
  size_t v17; // rbx
  const wchar_t *v18; // rcx
  size_t v19; // r8
  unsigned int v20; // ebx
  __int64 v21; // rcx
  _WORD *v22; // rax
  __int64 v23; // rcx
  char v24; // si
  __int64 *v25; // rax
  __int64 *v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 k; // rbx
  int v30; // eax
  int v31; // edx
  void *v33; // rbx
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  void **v37; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v38[32]; // [rsp+48h] [rbp-B8h] BYREF
  bool v39; // [rsp+68h] [rbp-98h]
  __int16 v40; // [rsp+69h] [rbp-97h]
  __int128 v41; // [rsp+70h] [rbp-90h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h]
  __int64 v43; // [rsp+88h] [rbp-78h]
  _QWORD pExceptionObject[2]; // [rsp+90h] [rbp-70h] BYREF
  void *v45; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v46; // [rsp+A8h] [rbp-58h]
  __int64 v47; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *S2[2]; // [rsp+C8h] [rbp-38h] BYREF
  size_t N; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v50; // [rsp+E0h] [rbp-20h]
  wchar_t *S1[2]; // [rsp+E8h] [rbp-18h] BYREF
  size_t v52; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v53; // [rsp+100h] [rbp+0h]
  __int128 v54; // [rsp+110h] [rbp+10h] BYREF
  __int64 v55; // [rsp+120h] [rbp+20h]
  __int64 v56; // [rsp+128h] [rbp+28h]
  _BYTE v57[4]; // [rsp+150h] [rbp+50h] BYREF
  int v58; // [rsp+154h] [rbp+54h]
  _QWORD v59[2]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v60; // [rsp+168h] [rbp+68h] BYREF
  __int128 v61; // [rsp+170h] [rbp+70h]
  __int64 v62; // [rsp+180h] [rbp+80h]
  __int64 v63; // [rsp+188h] [rbp+88h]
  __time64_t v64; // [rsp+190h] [rbp+90h] BYREF
  __int128 v65; // [rsp+198h] [rbp+98h] BYREF
  __int64 v66; // [rsp+1A8h] [rbp+A8h]
  _BYTE v67[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  int v68; // [rsp+1B4h] [rbp+B4h]
  _QWORD v69[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v70; // [rsp+1C8h] [rbp+C8h] BYREF
  __int128 v71; // [rsp+1D0h] [rbp+D0h]
  __int64 v72; // [rsp+1E0h] [rbp+E0h]
  __int64 v73; // [rsp+1E8h] [rbp+E8h]
  _QWORD Src[4]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v75; // [rsp+210h] [rbp+110h] BYREF
  __int64 v76; // [rsp+220h] [rbp+120h]
  _QWORD v77[2]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v78[16]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v79[48]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v80[8]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v81[8]; // [rsp+288h] [rbp+188h] BYREF
  _BYTE v82[24]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v83[192]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v84[120]; // [rsp+368h] [rbp+268h] BYREF
  int v85; // [rsp+3E0h] [rbp+2E0h]
  __int64 v86; // [rsp+478h] [rbp+378h]
  __int64 v87; // [rsp+480h] [rbp+380h]

  *(_OWORD *)S1 = 0;
  v52 = 0;
  v53 = 7;
  LOWORD(S1[0]) = 0;
  *(_OWORD *)S2 = 0;
  N = 0;
  v50 = 7;
  LOWORD(S2[0]) = 0;
  v65 = 0;
  v66 = 0;
  v57[0] = 0;
  v58 = 0;
  v59[0] = 0;
  v59[1] = 0;
  v6 = operator new(0x38u);
  *v6 = v6;
  v6[1] = v6;
  v59[0] = v6;
  v60 = 0;
  v61 = 0;
  v62 = 7;
  v63 = 8;
  v58 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    &v60,
    16,
    v6);
  v67[0] = 0;
  v68 = 0;
  v69[0] = 0;
  v69[1] = 0;
  v7 = operator new(0x38u);
  *v7 = v7;
  v7[1] = v7;
  v69[0] = v7;
  v70 = 0;
  v71 = 0;
  v72 = 7;
  v73 = 8;
  v68 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    &v70,
    16,
    v7);
  v37 = &Uev::TemplateParser::`vftable';
  std::wstring::wstring(v38, a3);
  v40 = 1;
  v41 = 0;
  v42 = 0;
  v43 = 7;
  LOWORD(v41) = 0;
  if ( *(_QWORD *)(a3 + 24) <= 7u )
    v8 = (_WORD *)a3;
  else
    v8 = *(_WORD **)a3;
  v39 = *v8 != 60;
  Uev::TemplateSuiteData::TemplateSuiteData((Uev::TemplateSuiteData *)v80);
  v54 = 0;
  v55 = 0;
  v56 = 0;
  std::wstring::_Construct<1,wchar_t *>(&v54, &Data, 0);
  Uev::TemplateParser::Parse(&v37, (_BYTE)v40 != 0 ? 277 : 21, &v54, v80);
  std::wstring::_Tidy_deallocate(&v54);
  if ( (_BYTE)v40 && !v80[0] )
  {
    Uev::InvalidTemplateException::InvalidTemplateException(&v54, v81);
    throw (Uev::InvalidTemplateException *)&v54;
  }
  std::wstring::operator=(S1, v83);
  for ( i = v86; i != v87; i += 272 )
    Uev::TemplateData::GetProcessFileCriteria(i, &v65);
  if ( v87 - v86 == 272 )
  {
    v10 = *(_DWORD *)(v86 + 120);
    *(_DWORD *)stdext::hash_map<std::wstring const,unsigned int,stdext::hash_compare<std::wstring const,std::less<std::wstring const>>,std::allocator<std::pair<std::wstring const,unsigned int>>>::operator[](
                 v57,
                 v86) = v10;
  }
  else
  {
    v11 = v85;
    *(_DWORD *)stdext::hash_map<std::wstring const,unsigned int,stdext::hash_compare<std::wstring const,std::less<std::wstring const>>,std::allocator<std::pair<std::wstring const,unsigned int>>>::operator[](
                 v57,
                 v84) = v11;
    for ( j = v86; j != v87; j += 272 )
    {
      v13 = *(_DWORD *)(j + 120);
      *(_DWORD *)stdext::hash_map<std::wstring const,unsigned int,stdext::hash_compare<std::wstring const,std::less<std::wstring const>>,std::allocator<std::pair<std::wstring const,unsigned int>>>::operator[](
                   v57,
                   j) = v13;
    }
  }
  Uev::TemplateSuiteData::~TemplateSuiteData((Uev::TemplateSuiteData *)v80);
  v37 = &Uev::TemplateParser::`vftable';
  std::wstring::_Tidy_deallocate(&v41);
  std::wstring::_Tidy_deallocate(v38);
  v14 = S1;
  if ( *(_QWORD *)(a2 + 16) )
    v14 = (wchar_t **)a2;
  std::wstring::operator=(S2, v14);
  Uev::TemplateAdministrator::GetTemplateFilenameForId(Src, (__int64)S2);
  v15 = N;
  v16 = (const wchar_t *)S2;
  if ( v50 > 7 )
    v16 = S2[0];
  v17 = v52;
  v18 = (const wchar_t *)S1;
  if ( v53 > 7 )
    v18 = S1[0];
  v19 = v52;
  if ( N < v52 )
    v19 = N;
  if ( wmemcmp(v18, v16, v19) || v17 < v15 || v17 > v15 )
  {
    std::wstring::wstring(&v54, L"New template ID does not match the existing template ID");
    Uev::TemplateNotFoundException::TemplateNotFoundException(&v37, &v54);
    throw (Uev::TemplateNotFoundException *)&v37;
  }
  v20 = 1;
  if ( (*(unsigned __int8 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)a1 + 56LL))(a1, S2) )
  {
    v37 = &Uev::TemplateParser::`vftable';
    std::wstring::wstring(v38, Src);
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 7;
    LOWORD(v41) = 0;
    v22 = Src;
    if ( Src[3] > 7u )
      v22 = (_WORD *)Src[0];
    v39 = *v22 != 60;
    Uev::TemplateParser::ParseVersions(&v37, v67);
    v37 = &Uev::TemplateParser::`vftable';
    std::wstring::_Tidy_deallocate(&v41);
    std::wstring::_Tidy_deallocate(v38);
    v24 = 0;
    v54 = 0;
    v55 = 0;
    v56 = 7;
    LOWORD(v54) = 0;
    v25 = (__int64 *)v69[0];
    v26 = *(__int64 **)v69[0];
    while ( v26 != v25 )
    {
      if ( v24 )
        goto LABEL_48;
      v27 = stdext::hash_compare<std::wstring const,std::less<std::wstring const>>::operator()(v23, v26 + 2);
      v23 = *(_QWORD *)(std::_Hash<stdext::_Hmap_traits<std::wstring const,Uev::SettingBase *,stdext::hash_compare<std::wstring const,std::less<std::wstring const>>,std::allocator<std::pair<std::wstring const,Uev::SettingBase *>>,0>>::_Find_last<std::wstring>(
                          v57,
                          pExceptionObject,
                          v26 + 2,
                          v27)
                      + 8);
      if ( v23 && v23 != v59[0] )
      {
        v28 = stdext::hash_compare<std::wstring const,std::less<std::wstring const>>::operator()(v23, v26 + 2);
        std::_Hash<stdext::_Hmap_traits<std::wstring const,Uev::SettingBase *,stdext::hash_compare<std::wstring const,std::less<std::wstring const>>,std::allocator<std::pair<std::wstring const,Uev::SettingBase *>>,0>>::_Find_last<std::wstring>(
          v57,
          &v45,
          v26 + 2,
          v28);
        if ( !v46 )
        {
          std::_Xout_of_range("invalid hash_map<K, T> key");
          __debugbreak();
        }
        if ( *((_DWORD *)v26 + 12) > *(_DWORD *)(v46 + 48) )
        {
          v24 = 1;
          std::wstring::operator=(&v54, v26 + 2);
        }
      }
      v26 = (__int64 *)*v26;
      v25 = (__int64 *)v69[0];
    }
    if ( v24 )
    {
LABEL_48:
      std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v80);
      v34 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v82, L"Template ID ");
      v35 = std::operator<<<wchar_t>(v34, &v54);
      std::operator<<<wchar_t,std::char_traits<wchar_t>>(v35, L" is newer in the currently registered template.");
      v36 = std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v80, &v45);
      Uev::TemplateVersionException::TemplateVersionException(&v37, v36);
      throw (Uev::TemplateVersionException *)&v37;
    }
    v20 = 4;
    std::wstring::_Tidy_deallocate(&v54);
  }
  Uev::TemplateAdministrator::InstrumentTemplate(v21, a3, v20);
  v75 = 0;
  v76 = 0;
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 16LL))(a1, &v75);
  Uev::Common::WriteUtf8File((LPCWSTR)Src, (LPCWCH)a3);
  Uev::TemplateIndex::TemplateIndex((Uev::TemplateIndex *)v77);
  Uev::TemplateIndex::LoadIndex((Uev::TemplateIndex *)v77);
  Uev::TemplateIndex::RemoveTemplateID(v77, S2);
  for ( k = v65; k != *((_QWORD *)&v65 + 1); k += 168 )
    Uev::TemplateIndex::AddTemplateID((__int64)v77, k, (__int64)S2);
  Uev::TemplateIndex::SaveIndex((Uev::TemplateIndex *)v77);
  v64 = _time64(0);
  v47 = 0;
  v30 = Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance();
  if ( !(unsigned __int8)Uev::SettingGroup<unsigned __int64>::Set(
                           v30 + 19808,
                           v31,
                           (unsigned int)S2,
                           (unsigned int)&v64,
                           (__int64)&v47) )
  {
    v33 = operator new(0x68u);
    v45 = v33;
    std::wstring::wstring(&v54, L"Unable to set template registration timestamp");
    pExceptionObject[0] = Uev::SystemException::SystemException(v33, &v54, (unsigned int)v47);
    throw (Uev::SystemException **)pExceptionObject;
  }
  v77[0] = &Uev::TemplateIndex::`vftable';
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(v79);
  std::list<std::pair<std::wstring const,std::wstring>>::~list<std::pair<std::wstring const,std::wstring>>(v78);
  std::vector<std::wstring>::_Tidy(&v75);
  std::wstring::_Tidy_deallocate(Src);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(&v70);
  std::list<std::pair<std::wstring const,Uev::SettingBase *>>::~list<std::pair<std::wstring const,Uev::SettingBase *>>(v69);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(&v60);
  std::list<std::pair<std::wstring const,Uev::SettingBase *>>::~list<std::pair<std::wstring const,Uev::SettingBase *>>(v59);
  std::vector<Uev::ProcessFileCriteria>::_Tidy(&v65);
  std::wstring::_Tidy_deallocate(S2);
  return std::wstring::_Tidy_deallocate(S1);
}

```

## disassembly

```asm
0x14003d840  mov     [rsp-8+arg_18], rbx
0x14003d845  push    rbp
0x14003d846  push    rsi
0x14003d847  push    rdi
0x14003d848  push    r12
0x14003d84a  push    r13
0x14003d84c  push    r14
0x14003d84e  push    r15
0x14003d850  lea     rbp, [rsp-3D0h]
0x14003d858  sub     rsp, 4D0h
0x14003d85f  mov     rax, cs:__security_cookie
0x14003d866  xor     rax, rsp
0x14003d869  mov     [rbp+400h+var_40], rax
0x14003d870  mov     r14, r8
0x14003d873  mov     rsi, rdx
0x14003d876  mov     r15, rcx
0x14003d879  xor     r13d, r13d
0x14003d87c  mov     [rsp+500h+var_4D0], r13d
0x14003d881  xorps   xmm0, xmm0
0x14003d884  movups  xmmword ptr [rbp+400h+S1], xmm0
0x14003d888  mov     [rbp+400h+var_408], r13
0x14003d88c  lea     ebx, [r13+7]
0x14003d890  mov     [rbp+400h+var_400], rbx
0x14003d894  mov     word ptr [rbp+400h+S1], r13w
0x14003d899  movups  xmmword ptr [rbp+400h+S2], xmm0
0x14003d89d  mov     [rbp+400h+N], r13
0x14003d8a1  mov     [rbp+400h+var_420], rbx
0x14003d8a5  mov     word ptr [rbp+400h+S2], r13w
0x14003d8aa  movdqu  [rbp+400h+var_368], xmm0
0x14003d8b2  mov     [rbp+400h+var_358], r13
0x14003d8b9  xor     eax, eax
0x14003d8bb  mov     [rbp+400h+var_3B0], al
0x14003d8be  mov     [rbp+400h+var_3AC], eax
0x14003d8c1  mov     [rbp+400h+var_3A8], r13
0x14003d8c5  mov     [rbp+400h+var_3A0], r13
0x14003d8c9  lea     r12d, [r13+38h]
0x14003d8cd  mov     ecx, r12d; Size
0x14003d8d0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003d8d5  mov     [rax], rax
0x14003d8d8  mov     [rax+8], rax
0x14003d8dc  mov     [rbp+400h+var_3A8], rax
0x14003d8e0  mov     [rbp+400h+var_398], r13
0x14003d8e4  xorps   xmm0, xmm0
0x14003d8e7  movdqa  [rbp+400h+var_390], xmm0
0x14003d8ec  mov     [rbp+400h+var_380], rbx
0x14003d8f3  lea     edi, [rbx+1]
0x14003d8f6  mov     [rbp+400h+var_378], rdi
0x14003d8fd  mov     [rbp+400h+var_3AC], 3F800000h
0x14003d904  mov     r8, rax
0x14003d907  lea     ebx, [rdi+8]
0x14003d90a  mov     edx, ebx
0x14003d90c  lea     rcx, [rbp+400h+var_398]
0x14003d910  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x14003d915  nop
0x14003d916  xor     eax, eax
0x14003d918  mov     [rbp+400h+var_350], al
0x14003d91e  mov     [rbp+400h+var_34C], eax
0x14003d924  mov     [rbp+400h+var_348], r13
0x14003d92b  mov     [rbp+400h+var_340], r13
0x14003d932  mov     ecx, r12d; Size
0x14003d935  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003d93a  mov     [rax], rax
0x14003d93d  mov     [rax+8], rax
0x14003d941  mov     [rbp+400h+var_348], rax
0x14003d948  mov     [rbp+400h+var_338], r13
0x14003d94f  xorps   xmm0, xmm0
0x14003d952  movdqa  [rbp+400h+var_330], xmm0
0x14003d95a  lea     r12d, [r13+7]
0x14003d95e  mov     [rbp+400h+var_320], r12
0x14003d965  mov     [rbp+400h+var_318], rdi
0x14003d96c  mov     [rbp+400h+var_34C], 3F800000h
0x14003d976  mov     r8, rax
0x14003d979  mov     edx, ebx
0x14003d97b  lea     rcx, [rbp+400h+var_338]
0x14003d982  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x14003d987  nop
0x14003d988  lea     rdi, ??_7TemplateParser@Uev@@6B@; const Uev::TemplateParser::`vftable'
0x14003d98f  mov     [rsp+500h+var_4C0], rdi
0x14003d994  mov     rdx, r14
0x14003d997  lea     rcx, [rsp+500h+var_4B8]
0x14003d99c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14003d9a1  mov     [rsp+500h+var_497], 1
0x14003d9a8  xorps   xmm0, xmm0
0x14003d9ab  movups  [rsp+500h+var_490], xmm0
0x14003d9b0  mov     [rbp+400h+var_480], r13
0x14003d9b4  mov     [rbp+400h+var_478], r12
0x14003d9b8  mov     word ptr [rsp+500h+var_490], r13w
0x14003d9be  cmp     [r14+18h], r12
0x14003d9c2  jbe     short loc_14003D9C9
0x14003d9c4  mov     rax, [r14]
0x14003d9c7  jmp     short loc_14003D9CC
0x14003d9c9  mov     rax, r14
0x14003d9cc  cmp     word ptr [rax], 3Ch ; '<'
0x14003d9d0  setnz   [rsp+500h+var_498]
0x14003d9d5  lea     rcx, [rbp+400h+var_280]; this
0x14003d9dc  call    ??0TemplateSuiteData@Uev@@QEAA@XZ; Uev::TemplateSuiteData::TemplateSuiteData(void)
0x14003d9e1  nop
0x14003d9e2  xorps   xmm0, xmm0
0x14003d9e5  movups  [rbp+400h+var_3F0], xmm0
0x14003d9e9  mov     [rbp+400h+var_3E0], r13
0x14003d9ed  mov     [rbp+400h+var_3D8], r13
0x14003d9f1  xor     r8d, r8d
0x14003d9f4  lea     rdx, Data
0x14003d9fb  lea     rcx, [rbp+400h+var_3F0]
0x14003d9ff  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14003da04  nop
0x14003da05  mov     al, byte ptr [rsp+500h+var_497]
0x14003da09  neg     al
0x14003da0b  sbb     edx, edx
0x14003da0d  and     edx, 100h
0x14003da13  add     edx, 15h
0x14003da16  lea     r9, [rbp+400h+var_280]
0x14003da1d  lea     r8, [rbp+400h+var_3F0]
0x14003da21  lea     rcx, [rsp+500h+var_4C0]
0x14003da26  call    ?Parse@TemplateParser@Uev@@AEAAXIAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVTemplateSuiteData@2@@Z; Uev::TemplateParser::Parse(uint,std::wstring const &,Uev::TemplateSuiteData &)
0x14003da2b  nop
0x14003da2c  lea     rcx, [rbp+400h+var_3F0]
0x14003da30  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003da35  cmp     byte ptr [rsp+500h+var_497], r13b
0x14003da3a  jz      short loc_14003DA49
0x14003da3c  cmp     [rbp+400h+var_280], r13b
0x14003da43  jz      loc_14003DF12
0x14003da49  lea     rdx, [rbp+400h+var_258]
0x14003da50  lea     rcx, [rbp+400h+S1]
0x14003da54  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14003da59  mov     rbx, [rbp+400h+var_88]
0x14003da60  mov     r12d, 110h
0x14003da66  mov     rax, [rbp+400h+var_80]
0x14003da6d  cmp     rbx, rax
0x14003da70  jz      short loc_14003DA86
0x14003da72  lea     rdx, [rbp+400h+var_368]
0x14003da79  mov     rcx, rbx
0x14003da7c  call    ?GetProcessFileCriteria@TemplateData@Uev@@QEBAXAEAV?$vector@VProcessFileCriteria@Uev@@V?$allocator@VProcessFileCriteria@Uev@@@std@@@std@@@Z; Uev::TemplateData::GetProcessFileCriteria(std::vector<Uev::ProcessFileCriteria> &)
0x14003da81  add     rbx, r12
0x14003da84  jmp     short loc_14003DA66
0x14003da86  mov     rdx, [rbp+400h+var_88]
0x14003da8d  sub     rax, rdx
0x14003da90  lea     rcx, [rbp+400h+var_3B0]
0x14003da94  cmp     rax, r12
0x14003da97  jnz     short loc_14003DAA5
0x14003da99  mov     ebx, [rdx+78h]
0x14003da9c  call    ??A?$hash_map@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IV?$hash_compare@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@@stdext@@QEAAAEAIAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; stdext::hash_map<std::wstring const,uint,stdext::hash_compare<std::wstring const,std::less<std::wstring const>>,std::allocator<std::pair<std::wstring const,uint>>>::operator[](std::wstring const &)
0x14003daa1  mov     [rax], ebx
0x14003daa3  jmp     short loc_14003DAE6
0x14003daa5  mov     ebx, [rbp+400h+var_120]
0x14003daab  lea     rdx, [rbp+400h+var_198]
0x14003dab2  call    ??A?$hash_map@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IV?$hash_compare@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@@stdext@@QEAAAEAIAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; stdext::hash_map<std::wstring const,uint,stdext::hash_compare<std::wstring const,std::less<std::wstring const>>,std::allocator<std::pair<std::wstring const,uint>>>::operator[](std::wstring const &)
0x14003dab7  mov     [rax], ebx
0x14003dab9  mov     rbx, [rbp+400h+var_88]
0x14003dac0  cmp     rbx, [rbp+400h+var_80]
0x14003dac7  jz      short loc_14003DADF
0x14003dac9  mov     edi, [rbx+78h]
0x14003dacc  mov     rdx, rbx
0x14003dacf  lea     rcx, [rbp+400h+var_3B0]
0x14003dad3  call    ??A?$hash_map@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IV?$hash_compare@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@@stdext@@QEAAAEAIAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; stdext::hash_map<std::wstring const,uint,stdext::hash_compare<std::wstring const,std::less<std::wstring const>>,std::allocator<std::pair<std::wstring const,uint>>>::operator[](std::wstring const &)
0x14003dad8  mov     [rax], edi
0x14003dada  add     rbx, r12
0x14003dadd  jmp     short loc_14003DAC0
0x14003dadf  lea     rdi, ??_7TemplateParser@Uev@@6B@; const Uev::TemplateParser::`vftable'
0x14003dae6  lea     rcx, [rbp+400h+var_280]; this
0x14003daed  call    ??1TemplateSuiteData@Uev@@QEAA@XZ; Uev::TemplateSuiteData::~TemplateSuiteData(void)
0x14003daf2  nop
0x14003daf3  mov     [rsp+500h+var_4C0], rdi
0x14003daf8  lea     rcx, [rsp+500h+var_490]
0x14003dafd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003db02  lea     rcx, [rsp+500h+var_4B8]
0x14003db07  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003db0c  lea     rdx, [rbp+400h+S1]
0x14003db10  cmp     [rsi+10h], r13
0x14003db14  cmovnz  rdx, rsi
0x14003db18  lea     rcx, [rbp+400h+S2]
0x14003db1c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14003db21  lea     rdx, [rbp+400h+S2]
0x14003db25  lea     rcx, [rbp+400h+Src]; Src
0x14003db2c  call    ?GetTemplateFilenameForId@TemplateAdministrator@Uev@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV34@@Z; Uev::TemplateAdministrator::GetTemplateFilenameForId(std::wstring const &)
0x14003db31  nop
0x14003db32  mov     rdi, [rbp+400h+N]
0x14003db36  lea     rdx, [rbp+400h+S2]
0x14003db3a  mov     r12d, 7
0x14003db40  cmp     [rbp+400h+var_420], r12
0x14003db44  cmova   rdx, [rbp+400h+S2]; S2
0x14003db49  mov     rbx, [rbp+400h+var_408]
0x14003db4d  lea     rcx, [rbp+400h+S1]
0x14003db51  cmp     [rbp+400h+var_400], r12
0x14003db55  cmova   rcx, [rbp+400h+S1]; S1
0x14003db5a  mov     r8, rbx
0x14003db5d  cmp     rdi, rbx
0x14003db60  cmovb   r8, rdi; N
0x14003db64  call    wmemcmp
0x14003db69  test    eax, eax
0x14003db6b  jnz     loc_14003DEE1
0x14003db71  cmp     rbx, rdi
0x14003db74  jb      loc_14003DEE1
0x14003db7a  ja      loc_14003DEE1
0x14003db80  mov     eax, r13d
0x14003db83  test    eax, eax
0x14003db85  jnz     loc_14003DEE1
0x14003db8b  lea     ebx, [r12-6]
0x14003db90  mov     rax, [r15]
0x14003db93  lea     rdx, [rbp+400h+S2]
0x14003db97  mov     rcx, r15
0x14003db9a  mov     rax, [rax+38h]
0x14003db9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dba3  test    al, al
0x14003dba5  jz      loc_14003DCFE
0x14003dbab  lea     rbx, ??_7TemplateParser@Uev@@6B@; const Uev::TemplateParser::`vftable'
0x14003dbb2  mov     [rsp+500h+var_4C0], rbx
0x14003dbb7  lea     rdx, [rbp+400h+Src]
0x14003dbbe  lea     rcx, [rsp+500h+var_4B8]
0x14003dbc3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14003dbc8  mov     [rsp+500h+var_497], r13w
0x14003dbce  xorps   xmm0, xmm0
0x14003dbd1  movups  [rsp+500h+var_490], xmm0
0x14003dbd6  mov     [rbp+400h+var_480], r13
0x14003dbda  mov     [rbp+400h+var_478], r12
0x14003dbde  mov     word ptr [rsp+500h+var_490], r13w
0x14003dbe4  lea     rax, [rbp+400h+Src]
0x14003dbeb  cmp     [rbp+400h+var_2F8], r12
0x14003dbf2  cmova   rax, [rbp+400h+Src]
0x14003dbfa  cmp     word ptr [rax], 3Ch ; '<'
0x14003dbfe  setnz   [rsp+500h+var_498]
0x14003dc03  lea     rdx, [rbp+400h+var_350]
0x14003dc0a  lea     rcx, [rsp+500h+var_4C0]
0x14003dc0f  call    ?ParseVersions@TemplateParser@Uev@@QEAAXAEAV?$hash_map@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IV?$hash_compare@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@@stdext@@@Z; Uev::TemplateParser::ParseVersions(stdext::hash_map<std::wstring const,uint,stdext::hash_compare<std::wstring const,std::less<std::wstring const>>,std::allocator<std::pair<std::wstring const,uint>>> &)
0x14003dc14  nop
0x14003dc15  mov     [rsp+500h+var_4C0], rbx
0x14003dc1a  lea     rcx, [rsp+500h+var_490]
0x14003dc1f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003dc24  lea     rcx, [rsp+500h+var_4B8]
0x14003dc29  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003dc2e  mov     sil, r13b
0x14003dc31  xorps   xmm0, xmm0
0x14003dc34  movups  [rbp+400h+var_3F0], xmm0
0x14003dc38  mov     [rbp+400h+var_3E0], r13
0x14003dc3c  mov     [rbp+400h+var_3D8], r12
0x14003dc40  mov     word ptr [rbp+400h+var_3F0], r13w
0x14003dc45  mov     rax, [rbp+400h+var_348]
0x14003dc4c  mov     rbx, [rax]
0x14003dc4f  cmp     rbx, rax
0x14003dc52  jz      loc_14003DCE7
0x14003dc58  test    sil, sil
0x14003dc5b  jnz     loc_14003DF33
0x14003dc61  lea     rdi, [rbx+10h]
0x14003dc65  mov     rdx, rdi
0x14003dc68  call    ??R?$hash_compare@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@stdext@@QEBA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; stdext::hash_compare<std::wstring const,std::less<std::wstring const>>::operator()(std::wstring const &)
0x14003dc6d  mov     r9, rax
0x14003dc70  mov     r8, rdi
0x14003dc73  lea     rdx, [rbp+400h+pExceptionObject]
0x14003dc77  lea     rcx, [rbp+400h+var_3B0]
0x14003dc7b  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Hmap_traits@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAVSettingBase@Uev@@V?$hash_compare@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAVSettingBase@Uev@@@std@@@2@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAVSettingBase@Uev@@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<stdext::_Hmap_traits<std::wstring const,Uev::SettingBase *,stdext::hash_compare<std::wstring const,std::less<std::wstring const>>,std::allocator<std::pair<std::wstring const,Uev::SettingBase *>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x14003dc80  mov     rcx, [rax+8]
0x14003dc84  test    rcx, rcx
0x14003dc87  jz      short loc_14003DCCA
0x14003dc89  cmp     rcx, [rbp+400h+var_3A8]
0x14003dc8d  jz      short loc_14003DCCA
0x14003dc8f  mov     rdx, rdi
0x14003dc92  call    ??R?$hash_compare@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@stdext@@QEBA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; stdext::hash_compare<std::wstring const,std::less<std::wstring const>>::operator()(std::wstring const &)
0x14003dc97  mov     r9, rax
0x14003dc9a  mov     r8, rdi
0x14003dc9d  lea     rdx, [rbp+400h+var_460]
0x14003dca1  lea     rcx, [rbp+400h+var_3B0]
0x14003dca5  call    ??$_Find_last@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Hash@V?$_Hmap_traits@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAVSettingBase@Uev@@V?$hash_compare@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAVSettingBase@Uev@@@std@@@2@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAVSettingBase@Uev@@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::_Hash<stdext::_Hmap_traits<std::wstring const,Uev::SettingBase *,stdext::hash_compare<std::wstring const,std::less<std::wstring const>>,std::allocator<std::pair<std::wstring const,Uev::SettingBase *>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x14003dcaa  mov     rax, [rbp+400h+var_458]
0x14003dcae  test    rax, rax
0x14003dcb1  jz      short loc_14003DCD9
0x14003dcb3  mov     eax, [rax+30h]
0x14003dcb6  cmp     [rbx+30h], eax
0x14003dcb9  jbe     short loc_14003DCCA
0x14003dcbb  mov     sil, 1
0x14003dcbe  mov     rdx, rdi
0x14003dcc1  lea     rcx, [rbp+400h+var_3F0]
0x14003dcc5  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14003dcca  mov     rbx, [rbx]
0x14003dccd  mov     rax, [rbp+400h+var_348]
0x14003dcd4  jmp     loc_14003DC4F
0x14003dcd9  lea     rcx, aInvalidHashMap; "invalid hash_map<K, T> key"
0x14003dce0  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x14003dce6  int     3; Trap to Debugger
0x14003dce7  test    sil, sil
0x14003dcea  jnz     loc_14003DF33
0x14003dcf0  mov     ebx, 4
0x14003dcf5  lea     rcx, [rbp+400h+var_3F0]
0x14003dcf9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14003dcfe  mov     r8d, ebx
0x14003dd01  mov     rdx, r14
0x14003dd04  call    ?InstrumentTemplate@TemplateAdministrator@Uev@@AEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z; Uev::TemplateAdministrator::InstrumentTemplate(std::wstring const &,ulong)
0x14003dd09  xorps   xmm0, xmm0
0x14003dd0c  movdqu  [rbp+400h+var_2F0], xmm0
0x14003dd14  mov     [rbp+400h+var_2E0], r13
0x14003dd1b  mov     rax, [r15]
0x14003dd1e  lea     rdx, [rbp+400h+var_2F0]
0x14003dd25  mov     rcx, r15
0x14003dd28  mov     rax, [rax+10h]
0x14003dd2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003dd31  mov     rdx, r14; lpWideCharStr
0x14003dd34  lea     rcx, [rbp+400h+Src]; lpFileName
0x14003dd3b  call    ?WriteUtf8File@Common@Uev@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0@Z; Uev::Common::WriteUtf8File(std::wstring const &,std::wstring const &)
0x14003dd40  lea     rcx, [rbp+400h+var_2D0]; this
0x14003dd47  call    ??0TemplateIndex@Uev@@QEAA@XZ; Uev::TemplateIndex::TemplateIndex(void)
0x14003dd4c  nop
  ... truncated ...
```
