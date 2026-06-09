# Windows::Internal::Spelling::TaskConsumer::MergePerLanguageDictionaries(void)

- ea: `0x18003ff68`
- end: `0x1800405cd`
- name: `?MergePerLanguageDictionaries@TaskConsumer@Spelling@Internal@Windows@@AEAA_NXZ`
- size: `1637`
- prototype: `bool __fastcall(Windows::Internal::Spelling::TaskConsumer *__hidden this)`
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180046920`

## callees

- `0x18001c994`
- `0x18001dd2c`
- `0x18001e2e4`
- `0x18001e668`
- `0x18001e9a8`
- `0x18001ee7c`
- `0x18001fae0`
- `0x1800202e4`
- `0x180022e88`
- `0x1800338a0`
- `0x18003d528`
- `0x18003fdc0`
- `0x18003ff68`
- `0x1800405d4`
- `0x180040cc4`
- `0x1800411b4`
- `0x1800414cc`
- `0x180041708`
- `0x180046ef8`
- `0x180047770`
- `0x180047b18`
- `0x18005a99c`
- `0x18005b0e4`
- `0x180061320`
- `0x18006a0e4`
- `0x1800790a0`
- `0x180079f50`
- `0x18007a468`
- `0x18007b188`
- `0x18007cc38`
- `0x18007ee40`
- `0x18007ee64`
- `0x1800802b0`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003ffb5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003ffb5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180040011`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180040415`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180040011`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180040415`

## string_xrefs

- `0x18003fff0`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x180040112`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x1800403ca`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`
- `0x180040404`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
bool __fastcall Windows::Internal::Spelling::TaskConsumer::MergePerLanguageDictionaries(
        Windows::Internal::Spelling::TaskConsumer *this)
{
  unsigned int v2; // esi
  const WCHAR *v3; // r14
  const WCHAR *v4; // rcx
  DWORD FileAttributesW; // eax
  int v6; // eax
  const char *v7; // r9
  bool result; // al
  __int64 v9; // r9
  __int64 v10; // rbx
  __int64 v11; // r12
  __m128i si128; // xmm6
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, _BYTE *); // r15
  const WCHAR *v15; // rax
  __int64 v16; // rax
  int v17; // esi
  int v18; // eax
  char v19; // al
  __int64 v20; // rdi
  __int64 v21; // r15
  __int64 v22; // rdx
  unsigned __int64 UserDictionaryMaxSize; // rax
  unsigned __int64 v24; // rsi
  _QWORD *i; // rbx
  _QWORD *v26; // r15
  _WORD *v27; // rdx
  __int64 v28; // r10
  const WCHAR *v29; // r11
  const WCHAR *v30; // rax
  int v31; // ebx
  __int64 v32; // rax
  __int64 v33; // r8
  int v34; // eax
  int v35; // eax
  __int64 v36; // r8
  int v37; // [rsp+20h] [rbp-2B8h]
  _BYTE v38[4]; // [rsp+30h] [rbp-2A8h] BYREF
  int v39; // [rsp+34h] [rbp-2A4h] BYREF
  const WCHAR *v40; // [rsp+38h] [rbp-2A0h] BYREF
  __int128 v41; // [rsp+40h] [rbp-298h] BYREF
  __int64 v42; // [rsp+50h] [rbp-288h]
  int v43; // [rsp+58h] [rbp-280h] BYREF
  ULONGLONG TickCount64; // [rsp+60h] [rbp-278h] BYREF
  const WCHAR **v45; // [rsp+68h] [rbp-270h] BYREF
  int v46; // [rsp+70h] [rbp-268h]
  __int64 v47; // [rsp+78h] [rbp-260h] BYREF
  _QWORD v48[2]; // [rsp+80h] [rbp-258h] BYREF
  __int128 v49; // [rsp+90h] [rbp-248h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-238h]
  _QWORD v51[2]; // [rsp+B0h] [rbp-228h] BYREF
  _QWORD v52[3]; // [rsp+C0h] [rbp-218h] BYREF
  _QWORD v53[3]; // [rsp+D8h] [rbp-200h] BYREF
  char *FileSizeFromName; // [rsp+F0h] [rbp-1E8h] BYREF
  _QWORD v55[2]; // [rsp+F8h] [rbp-1E0h] BYREF
  __m128i v56; // [rsp+108h] [rbp-1D0h]
  _BYTE v57[40]; // [rsp+118h] [rbp-1C0h] BYREF
  _QWORD v58[42]; // [rsp+140h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  v2 = 0;
  v39 = 0;
  v3 = (const WCHAR *)((char *)this + 16);
  if ( *((_QWORD *)this + 5) <= 7u )
    v4 = (const WCHAR *)((char *)this + 16);
  else
    v4 = *(const WCHAR **)v3;
  FileAttributesW = GetFileAttributesW(v4);
  try
  {
    if ( FileAttributesW != -1 )
    {
      v38[0] = 0;
      v6 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _BYTE *))(**((_QWORD **)this + 6) + 24LL))(
             *((_QWORD *)this + 6),
             L"UserDictionaryMerged",
             v38);
      if ( v6 >= 0 )
      {
        if ( v38[0] )
          return 0;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1CB,
          (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdi"
                        "ctionarymanager.cpp",
          (const char *)(unsigned int)v6,
          v37);
      }
    }
    TickCount64 = GetTickCount64();
    wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v58,
      "ActivityMergeLocalDictionaries");
    v58[0] = &SpellingTelemetry::ActivityMergeLocalDictionaries::`vftable';
    SpellingTelemetry::ActivityMergeLocalDictionaries::StartActivity((SpellingTelemetry::ActivityMergeLocalDictionaries *)v58);
    wil::GetActivationFactory<Windows::Globalization::ILanguageStatics>((const WCHAR *)&v47);
    Windows::Globalization::Spelling::UserDictionaries::GetUserDictionaryExtension(v57);
    Windows::Globalization::Spelling::UserDictionaries::GetUserDictionaryLanguages(v53);
    v41 = 0;
    v42 = 0;
    v10 = v53[0];
    v11 = v53[1];
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( v10 != v11 )
    {
      v38[0] = 0;
      v13 = v47;
      v14 = *(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v47 + 48LL);
      if ( *(_QWORD *)(v10 + 24) <= 7u )
        v15 = (const WCHAR *)v10;
      else
        v15 = *(const WCHAR **)v10;
      v40 = v15;
      v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference((__int64)&FileSizeFromName, &v40);
      v17 = v2 | 1;
      v39 = v17;
      v18 = v14(v13, *(_QWORD *)(v16 + 24), v38);
      if ( v18 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1DF,
          (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdi"
                        "ctionarymanager.cpp",
          (const char *)(unsigned int)v18,
          v37);
LABEL_17:
        v19 = 0;
        goto LABEL_18;
      }
      if ( !v38[0] )
        goto LABEL_17;
      v19 = 1;
LABEL_18:
      v2 = v17 & 0xFFFFFFFE;
      if ( v19 )
      {
        Windows::Globalization::Spelling::UserDictionaries::GetUserDictionaries(v52, v57, v10);
        v20 = v52[0];
        v21 = v52[1];
        while ( v20 != v21 )
        {
          FileSizeFromName = (char *)Windows::Globalization::Spelling::UserDictionaries::GetFileSizeFromName(v20);
          std::wstring::wstring((__int64)v55, v20);
          v2 |= 2u;
          v22 = *((_QWORD *)&v41 + 1);
          if ( *((_QWORD *)&v41 + 1) == v42 )
          {
            std::vector<std::tuple<std::wstring,unsigned __int64>>::_Emplace_reallocate<std::tuple<std::wstring,unsigned __int64>>(
              &v41,
              *((_QWORD *)&v41 + 1),
              &FileSizeFromName);
          }
          else
          {
            **((_QWORD **)&v41 + 1) = FileSizeFromName;
            *(_QWORD *)(v22 + 8) = v55[0];
            *(_QWORD *)(v22 + 16) = v55[1];
            *(__m128i *)(v22 + 24) = v56;
            v56 = si128;
            LOWORD(v55[0]) = 0;
            *((_QWORD *)&v41 + 1) += 40LL;
          }
          std::wstring::_Tidy_deallocate(v55);
          v20 += 32;
        }
        std::vector<std::wstring>::_Tidy(v52);
      }
      v10 += 32;
    }
    LOBYTE(v9) = v38[0];
    std::_Sort_unchecked_std::tuple_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____unsigned___int64_____lambda_dc552cd8447c206d57051d996e6b1f04___(
      v41,
      *((_QWORD *)&v41 + 1),
      0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v41 + 1) - v41) >> 3),
      v9);
    UserDictionaryMaxSize = Windows::Globalization::Spelling::UserDictionaries::GetUserDictionaryMaxSize();
    v24 = 996147;
    if ( UserDictionaryMaxSize > 0x100000 )
      v24 = UserDictionaryMaxSize;
    std::set<std::wstring>::set<std::wstring>(&v45);
    v49 = 0;
    v50 = 0;
    v26 = (_QWORD *)*((_QWORD *)&v41 + 1);
    for ( i = (_QWORD *)v41; i != v26; i += 5 )
    {
      if ( i[4] <= 7u )
        v27 = i + 1;
      else
        v27 = (_WORD *)i[1];
      std::wstring::wstring(&FileSizeFromName, v27);
      Windows::Globalization::Spelling::UserDictionaries::ReadWordsFromFile(
        (__int64)v48,
        (const WCHAR *)&FileSizeFromName,
        0);
      std::wstring::_Tidy_deallocate(&FileSizeFromName);
      v28 = 2;
      v29 = *v45;
      v30 = *v45;
      v40 = *v45;
      while ( !*((_BYTE *)v30 + 25) )
      {
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,EventRegistrationToken>>>,std::_Iterator_base0>::operator++(&v40);
        v30 = v40;
      }
      if ( v28 && v28 + *i > v24 )
      {
        std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
          v48,
          v48);
        break;
      }
      v51[0] = &v45;
      v51[1] = v29;
      std::transform_std::_Tree_const_iterator_std::_Tree_val_std::_Tree_simple_types_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const__std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____________std::insert_iterator_std::set_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::less_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___________lambda_7b08db75ca2233c1d8fc11472fd4da09___(
        v52,
        *(_QWORD *)v48[0],
        v48[0],
        v51);
      if ( *((_QWORD *)&v49 + 1) == v50 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(&v49, *((_QWORD *)&v49 + 1), i + 1);
      }
      else
      {
        std::wstring::wstring(*((__int64 *)&v49 + 1), (__int64)(i + 1));
        *((_QWORD *)&v49 + 1) += 32LL;
      }
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        v48,
        v48);
    }
    Windows::Globalization::Spelling::UserDictionaries::OverwriteWordsToFile(v3, (__int64 **)&v45);
    v31 = Windows::Globalization::Spelling::UserDictionaries::GetFileSizeFromName(v3);
    v32 = std::set<std::wstring>::set<std::wstring>(v51);
    Windows::Internal::Spelling::TaskConsumer::UpdateMtf((__int64)this, 0, (__int64)&v45, v32);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v51);
    LOBYTE(v33) = 1;
    v34 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)this + 6) + 32LL))(
            *((_QWORD *)this + 6),
            L"UserDictionaryMerged",
            v33);
    if ( v34 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x220,
        (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdict"
                      "ionarymanager.cpp",
        (const char *)(unsigned int)v34,
        v37);
    v35 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD))(**((_QWORD **)this + 6) + 32LL))(
            *((_QWORD *)this + 6),
            L"UserDictionaryUploaded",
            0);
    if ( v35 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x221,
        (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdict"
                      "ionarymanager.cpp",
        (const char *)(unsigned int)v35,
        v37);
    v39 = GetTickCount64() - TickCount64;
    v43 = v31;
    LODWORD(TickCount64) = v46;
    LODWORD(v40) = -858993459 * ((__int64)(*((_QWORD *)&v41 + 1) - v41) >> 3);
    SpellingTelemetry::MergeLocalDictionaries<unsigned int,unsigned int,unsigned int,unsigned int>(
      &v40,
      &TickCount64,
      &v43,
      &v39);
    wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v58);
    std::vector<std::wstring>::_Tidy(&v49);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v45);
    if ( (_QWORD)v41 )
    {
      std::_Destroy_range<std::allocator<std::tuple<std::wstring,unsigned __int64>>>(v41, *((_QWORD *)&v41 + 1), v36);
      std::_Deallocate<16>((void *)v41, 8 * ((v42 - (__int64)v41) >> 3));
      v41 = 0;
      v42 = 0;
    }
    std::vector<std::wstring>::_Tidy(v53);
    std::wstring::_Tidy_deallocate(v57);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v47);
    SpellingTelemetry::ActivityMergeLocalDictionaries::~ActivityMergeLocalDictionaries((SpellingTelemetry::ActivityMergeLocalDictionaries *)v58);
    result = 1;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x22A,
      (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdictionarymanager.cpp",
      v7);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18003ff68  mov     rax, rsp
0x18003ff6b  mov     [rax+10h], rbx
0x18003ff6f  mov     [rax+18h], rsi
0x18003ff73  push    rdi
0x18003ff74  push    r12
0x18003ff76  push    r13
0x18003ff78  push    r14
0x18003ff7a  push    r15
0x18003ff7c  sub     rsp, 2B0h
0x18003ff83  movaps  xmmword ptr [rax-38h], xmm6
0x18003ff87  mov     rax, cs:__security_cookie
0x18003ff8e  xor     rax, rsp
0x18003ff91  mov     [rsp+2D8h+var_48], rax
0x18003ff99  mov     r13, rcx
0x18003ff9c  xor     esi, esi
0x18003ff9e  mov     [rsp+2D8h+var_2A4], esi
0x18003ffa2  lea     r14, [rcx+10h]
0x18003ffa6  cmp     qword ptr [r14+18h], 7
0x18003ffab  jbe     short loc_18003FFB2
0x18003ffad  mov     rcx, [r14]
0x18003ffb0  jmp     short loc_18003FFB5
0x18003ffb2  mov     rcx, r14; lpFileName
0x18003ffb5  call    cs:__imp_GetFileAttributesW
0x18003ffbb  cmp     eax, 0FFFFFFFFh
0x18003ffbe  jz      short loc_180040011
0x18003ffc0  mov     [rsp+2D8h+var_2A8], 0
0x18003ffc5  mov     rcx, [r13+30h]
0x18003ffc9  mov     rax, [rcx]
0x18003ffcc  lea     r8, [rsp+2D8h+var_2A8]
0x18003ffd1  lea     rdx, aUserdictionary_0; "UserDictionaryMerged"
0x18003ffd8  mov     rax, [rax+18h]
0x18003ffdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ffe1  mov     rcx, [rsp+2D8h]; this
0x18003ffe9  test    eax, eax
0x18003ffeb  jns     short loc_180040003
0x18003ffed  mov     r9d, eax; char *
0x18003fff0  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x18003fff7  mov     edx, 1CBh; void *
0x18003fffc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040001  jmp     short loc_180040011
0x180040003  cmp     [rsp+2D8h+var_2A8], 0
0x180040008  jz      short loc_180040011
0x18004000a  xor     al, al
0x18004000c  jmp     loc_180040507
0x180040011  call    cs:__imp_GetTickCount64
0x180040017  mov     [rsp+2D8h+var_278], rax
0x18004001c  lea     rdx, aActivitymergel; "ActivityMergeLocalDictionaries"
0x180040023  lea     rcx, [rsp+2D8h+var_198]
0x18004002b  call    ??0?$ActivityBase@VSpellingTelemetryProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180040030  lea     rax, ??_7ActivityMergeLocalDictionaries@SpellingTelemetry@@6B@; const SpellingTelemetry::ActivityMergeLocalDictionaries::`vftable'
0x180040037  mov     [rsp+2D8h+var_198], rax
0x18004003f  lea     rcx, [rsp+2D8h+var_198]; this
0x180040047  call    ?StartActivity@ActivityMergeLocalDictionaries@SpellingTelemetry@@QEAAXXZ; SpellingTelemetry::ActivityMergeLocalDictionaries::StartActivity(void)
0x18004004c  nop
0x18004004d  lea     rcx, [rsp+2D8h+var_260]
0x180040052  call    ??$GetActivationFactory@UILanguageStatics@Globalization@Windows@@@wil@@YA?AV?$com_ptr_t@UILanguageStatics@Globalization@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::Globalization::ILanguageStatics>(ushort const *)
0x180040057  nop
0x180040058  mov     edx, 1
0x18004005d  lea     rcx, [rsp+2D8h+var_1C0]; void *
0x180040065  call    ?GetUserDictionaryExtension@UserDictionaries@Spelling@Globalization@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4WORDLIST_TYPE@@@Z; Windows::Globalization::Spelling::UserDictionaries::GetUserDictionaryExtension(WORDLIST_TYPE)
0x18004006a  nop
0x18004006b  lea     rcx, [rsp+2D8h+var_200]
0x180040073  call    ?GetUserDictionaryLanguages@UserDictionaries@Spelling@Globalization@Windows@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; Windows::Globalization::Spelling::UserDictionaries::GetUserDictionaryLanguages(void)
0x180040078  nop
0x180040079  xorps   xmm0, xmm0
0x18004007c  movdqu  [rsp+2D8h+var_298], xmm0
0x180040082  mov     [rsp+2D8h+var_288], 0
0x18004008b  mov     rbx, [rsp+2D8h+var_200]
0x180040093  mov     r12, [rsp+2D8h+var_1F8]
0x18004009b  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800400a3  cmp     rbx, r12
0x1800400a6  jz      loc_180040238
0x1800400ac  mov     [rsp+2D8h+var_2A8], 0
0x1800400b1  mov     rdi, [rsp+2D8h+var_260]
0x1800400b6  mov     rax, [rdi]
0x1800400b9  mov     r15, [rax+30h]
0x1800400bd  cmp     qword ptr [rbx+18h], 7
0x1800400c2  jbe     short loc_1800400C9
0x1800400c4  mov     rax, [rbx]
0x1800400c7  jmp     short loc_1800400CC
0x1800400c9  mov     rax, rbx
0x1800400cc  mov     [rsp+2D8h+var_2A0], rax
0x1800400d1  lea     rdx, [rsp+2D8h+var_2A0]
0x1800400d6  lea     rcx, [rsp+2D8h+var_1E8]
0x1800400de  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800400e3  nop
0x1800400e4  or      esi, 1
0x1800400e7  mov     [rsp+2D8h+var_2A4], esi
0x1800400eb  lea     r8, [rsp+2D8h+var_2A8]
0x1800400f0  mov     rdx, [rax+18h]
0x1800400f4  mov     rcx, rdi
0x1800400f7  mov     rax, r15
0x1800400fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800400ff  mov     rcx, [rsp+2D8h]; this
0x180040107  test    eax, eax
0x180040109  jns     loc_1800401E7
0x18004010f  mov     r9d, eax; char *
0x180040112  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180040119  mov     edx, 1DFh; void *
0x18004011e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040123  xor     al, al
0x180040125  and     esi, 0FFFFFFFEh
0x180040128  test    al, al
0x18004012a  jz      loc_18004022F
0x180040130  mov     r8, rbx
0x180040133  lea     rdx, [rsp+2D8h+var_1C0]
0x18004013b  lea     rcx, [rsp+2D8h+var_218]
0x180040143  call    ?GetUserDictionaries@UserDictionaries@Spelling@Globalization@Windows@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@0@Z; Windows::Globalization::Spelling::UserDictionaries::GetUserDictionaries(std::wstring const &,std::wstring const &)
0x180040148  nop
0x180040149  mov     rdi, [rsp+2D8h+var_218]
0x180040151  mov     r15, [rsp+2D8h+var_210]
0x180040159  cmp     rdi, r15
0x18004015c  jz      loc_180040222
0x180040162  mov     rcx, rdi
0x180040165  call    ?GetFileSizeFromName@UserDictionaries@Spelling@Globalization@Windows@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Globalization::Spelling::UserDictionaries::GetFileSizeFromName(std::wstring const &)
0x18004016a  mov     [rsp+2D8h+var_1E8], rax
0x180040172  mov     rdx, rdi
0x180040175  lea     rcx, [rsp+2D8h+var_1E0]
0x18004017d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180040182  or      esi, 2
0x180040185  mov     rdx, qword ptr [rsp+2D8h+var_298+8]
0x18004018a  cmp     rdx, [rsp+2D8h+var_288]
0x18004018f  jz      short loc_1800401F9
0x180040191  mov     rax, [rsp+2D8h+var_1E8]
0x180040199  mov     [rdx], rax
0x18004019c  mov     rax, [rsp+2D8h+var_1E0]
0x1800401a4  mov     [rdx+8], rax
0x1800401a8  mov     rax, [rsp+2D8h+var_1D8]
0x1800401b0  mov     [rdx+10h], rax
0x1800401b4  mov     rax, qword ptr [rsp+2D8h+var_1D0]
0x1800401bc  mov     [rdx+18h], rax
0x1800401c0  mov     rax, qword ptr [rsp+2D8h+var_1D0+8]
0x1800401c8  mov     [rdx+20h], rax
0x1800401cc  movdqu  [rsp+2D8h+var_1D0], xmm6
0x1800401d5  xor     eax, eax
0x1800401d7  mov     word ptr [rsp+2D8h+var_1E0], ax
0x1800401df  add     qword ptr [rsp+2D8h+var_298+8], 28h ; '('
0x1800401e5  jmp     short loc_18004020C
0x1800401e7  cmp     [rsp+2D8h+var_2A8], 0
0x1800401ec  jz      loc_180040123
0x1800401f2  mov     al, 1
0x1800401f4  jmp     loc_180040125
0x1800401f9  lea     r8, [rsp+2D8h+var_1E8]
0x180040201  lea     rcx, [rsp+2D8h+var_298]
0x180040206  call    ??$_Emplace_reallocate@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@@std@@AEAAPEAV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@1@QEAV21@$$QEAV21@@Z; std::vector<std::tuple<std::wstring,unsigned __int64>>::_Emplace_reallocate<std::tuple<std::wstring,unsigned __int64>>(std::tuple<std::wstring,unsigned __int64> * const,std::tuple<std::wstring,unsigned __int64> &&)
0x18004020b  nop
0x18004020c  lea     rcx, [rsp+2D8h+var_1E0]
0x180040214  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180040219  add     rdi, 20h ; ' '
0x18004021d  jmp     loc_180040159
0x180040222  lea     rcx, [rsp+2D8h+var_218]
0x18004022a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18004022f  add     rbx, 20h ; ' '
0x180040233  jmp     loc_1800400A3
0x180040238  mov     rdx, qword ptr [rsp+2D8h+var_298+8]
0x18004023d  mov     rcx, qword ptr [rsp+2D8h+var_298]
0x180040242  mov     r8, rdx
0x180040245  sub     r8, rcx
0x180040248  sar     r8, 3
0x18004024c  mov     r12, 0CCCCCCCCCCCCCCCDh
0x180040256  imul    r8, r12
0x18004025a  mov     r9b, [rsp+2D8h+var_2A8]
0x18004025f  call    std___Sort_unchecked_std__tuple_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____unsigned___int64_____lambda_dc552cd8447c206d57051d996e6b1f04___
0x180040264  call    ?GetUserDictionaryMaxSize@UserDictionaries@Spelling@Globalization@Windows@@SA_KXZ; Windows::Globalization::Spelling::UserDictionaries::GetUserDictionaryMaxSize(void)
0x180040269  mov     esi, 0F3333h
0x18004026e  cmp     rax, 100000h
0x180040274  cmova   rsi, rax
0x180040278  lea     rcx, [rsp+2D8h+var_270]
0x18004027d  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180040282  nop
0x180040283  xorps   xmm0, xmm0
0x180040286  movdqu  [rsp+2D8h+var_248], xmm0
0x18004028f  mov     [rsp+2D8h+var_238], 0
0x18004029b  mov     rbx, qword ptr [rsp+2D8h+var_298]
0x1800402a0  mov     r15, qword ptr [rsp+2D8h+var_298+8]
0x1800402a5  cmp     rbx, r15
0x1800402a8  jz      loc_18004035B
0x1800402ae  lea     rdi, [rbx+8]
0x1800402b2  cmp     qword ptr [rbx+20h], 7
0x1800402b7  jbe     short loc_1800402BE
0x1800402b9  mov     rdx, [rdi]
0x1800402bc  jmp     short loc_1800402C1
0x1800402be  mov     rdx, rdi
0x1800402c1  lea     rcx, [rsp+2D8h+var_1E8]
0x1800402c9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800402ce  nop
0x1800402cf  xor     r8d, r8d
0x1800402d2  lea     rdx, [rsp+2D8h+var_1E8]
0x1800402da  lea     rcx, [rsp+2D8h+var_258]
0x1800402e2  call    ?ReadWordsFromFile@UserDictionaries@Spelling@Globalization@Windows@@SA?AV?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@_N@Z; Windows::Globalization::Spelling::UserDictionaries::ReadWordsFromFile(std::wstring const &,bool)
0x1800402e7  nop
0x1800402e8  lea     rcx, [rsp+2D8h+var_1E8]
0x1800402f0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800402f5  mov     r10d, 2
0x1800402fb  mov     rax, [rsp+2D8h+var_270]
0x180040300  mov     r11, [rax]
0x180040303  mov     rax, r11
0x180040306  mov     [rsp+2D8h+var_2A0], rax
0x18004030b  cmp     byte ptr [rax+19h], 0
0x18004030f  jnz     short loc_18004032E
0x180040311  mov     rcx, [rax+30h]
0x180040315  lea     r10, [r10+rcx*2]
0x180040319  add     r10, 4
0x18004031d  lea     rcx, [rsp+2D8h+var_2A0]
0x180040322  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUEventRegistrationToken@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,EventRegistrationToken>>>,std::_Iterator_base0>::operator++(void)
0x180040327  mov     rax, [rsp+2D8h+var_2A0]
0x18004032c  jmp     short loc_18004030B
0x18004032e  test    r10, r10
0x180040331  jz      loc_180040539
0x180040337  mov     rcx, [rbx]
0x18004033a  add     rcx, r10
0x18004033d  cmp     rcx, rsi
0x180040340  jbe     loc_180040539
0x180040346  lea     rdx, [rsp+2D8h+var_258]
0x18004034e  lea     rcx, [rsp+2D8h+var_258]
0x180040356  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x18004035b  lea     rdx, [rsp+2D8h+var_270]
0x180040360  mov     rcx, r14; lpFileName
0x180040363  call    ?OverwriteWordsToFile@UserDictionaries@Spelling@Globalization@Windows@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@6@@Z; Windows::Globalization::Spelling::UserDictionaries::OverwriteWordsToFile(std::wstring const &,std::set<std::wstring> const &)
0x180040368  mov     rcx, r14
0x18004036b  call    ?GetFileSizeFromName@UserDictionaries@Spelling@Globalization@Windows@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Globalization::Spelling::UserDictionaries::GetFileSizeFromName(std::wstring const &)
0x180040370  mov     rbx, rax
0x180040373  lea     rcx, [rsp+2D8h+var_228]
0x18004037b  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180040380  nop
0x180040381  mov     r9, rax
0x180040384  lea     r8, [rsp+2D8h+var_270]
0x180040389  xor     edx, edx
0x18004038b  mov     rcx, r13
0x18004038e  call    ?UpdateMtf@TaskConsumer@Spelling@Internal@Windows@@AEAAX_NAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@1@Z; Windows::Internal::Spelling::TaskConsumer::UpdateMtf(bool,std::set<std::wstring> const &,std::set<std::wstring> const &)
0x180040393  nop
0x180040394  lea     rcx, [rsp+2D8h+var_228]
0x18004039c  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x1800403a1  mov     rcx, [r13+30h]
0x1800403a5  mov     rax, [rcx]
0x1800403a8  mov     r8b, 1
0x1800403ab  lea     rdx, aUserdictionary_0; "UserDictionaryMerged"
0x1800403b2  mov     rax, [rax+20h]
0x1800403b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800403bb  mov     rcx, [rsp+2D8h]; this
0x1800403c3  test    eax, eax
0x1800403c5  jns     short loc_1800403DB
0x1800403c7  mov     r9d, eax; char *
0x1800403ca  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x1800403d1  mov     edx, 220h; void *
0x1800403d6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800403db  mov     rcx, [r13+30h]
0x1800403df  mov     rax, [rcx]
0x1800403e2  xor     r8d, r8d
0x1800403e5  lea     rdx, aUserdictionary; "UserDictionaryUploaded"
0x1800403ec  mov     rax, [rax+20h]
0x1800403f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800403f5  mov     rcx, [rsp+2D8h]; this
0x1800403fd  test    eax, eax
0x1800403ff  jns     short loc_180040415
0x180040401  mov     r9d, eax; char *
0x180040404  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x18004040b  mov     edx, 221h; void *
0x180040410  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040415  call    cs:__imp_GetTickCount64
0x18004041b  sub     eax, dword ptr [rsp+2D8h+var_278]
0x18004041f  mov     [rsp+2D8h+var_2A4], eax
0x180040423  mov     [rsp+2D8h+var_280], ebx
0x180040427  mov     eax, [rsp+2D8h+var_268]
0x18004042b  mov     dword ptr [rsp+2D8h+var_278], eax
0x18004042f  mov     rax, qword ptr [rsp+2D8h+var_298+8]
0x180040434  sub     rax, qword ptr [rsp+2D8h+var_298]
0x180040439  sar     rax, 3
0x18004043d  imul    rax, r12
0x180040441  mov     dword ptr [rsp+2D8h+var_2A0], eax
0x180040445  lea     r9, [rsp+2D8h+var_2A4]
0x18004044a  lea     r8, [rsp+2D8h+var_280]
0x18004044f  lea     rdx, [rsp+2D8h+var_278]
0x180040454  lea     rcx, [rsp+2D8h+var_2A0]
0x180040459  call    ??$MergeLocalDictionaries@IIII@SpellingTelemetry@@SAX$$QEAI000@Z; SpellingTelemetry::MergeLocalDictionaries<uint,uint,uint,uint>(uint &&,uint &&,uint &&,uint &&)
0x18004045e  lea     rcx, [rsp+2D8h+var_198]
0x180040466  call    ?Stop@?$ActivityBase@VSpellingTelemetryProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SpellingTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18004046b  nop
0x18004046c  lea     rcx, [rsp+2D8h+var_248]
0x180040474  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180040479  nop
0x18004047a  lea     rcx, [rsp+2D8h+var_270]
0x18004047f  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180040484  nop
0x180040485  mov     rcx, qword ptr [rsp+2D8h+var_298]
0x18004048a  test    rcx, rcx
0x18004048d  jz      short loc_1800404CD
0x18004048f  mov     rdx, qword ptr [rsp+2D8h+var_298+8]
0x180040494  call    ??$_Destroy_range@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@std@@@std@@YAXPEAV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@0@QEAV10@AEAV?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@0@@Z; std::_Destroy_range<std::allocator<std::tuple<std::wstring,unsigned __int64>>>(std::tuple<std::wstring,unsigned __int64> *,std::tuple<std::wstring,unsigned __int64> * const,std::allocator<std::tuple<std::wstring,unsigned __int64>> &)
0x180040499  mov     rcx, qword ptr [rsp+2D8h+var_298]
0x18004049e  mov     rax, [rsp+2D8h+var_288]
0x1800404a3  sub     rax, rcx
0x1800404a6  sar     rax, 3
0x1800404aa  imul    rax, r12
0x1800404ae  lea     rdx, [rax+rax*4]
0x1800404b2  shl     rdx, 3
0x1800404b6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800404bb  xorps   xmm0, xmm0
0x1800404be  movdqu  [rsp+2D8h+var_298], xmm0
0x1800404c4  mov     [rsp+2D8h+var_288], 0
  ... truncated ...
```
