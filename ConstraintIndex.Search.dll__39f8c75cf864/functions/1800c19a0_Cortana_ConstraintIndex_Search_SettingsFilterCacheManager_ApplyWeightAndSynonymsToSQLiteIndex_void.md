# Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::ApplyWeightAndSynonymsToSQLiteIndex(void)

- ea: `0x1800c19a0`
- end: `0x1800c2218`
- name: `?ApplyWeightAndSynonymsToSQLiteIndex@SettingsFilterCacheManager@Search@ConstraintIndex@Cortana@@AEAAXXZ`
- size: `2168`
- prototype: `void __fastcall(Cortana::ConstraintIndex::Search::SettingsFilterCacheManager *__hidden this)`
- caller_count: `1`
- callee_count: `49`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c0cf0`

## callees

- `0x1800049e0`
- `0x180005e44`
- `0x18000616e`
- `0x18000617a`
- `0x18000619e`
- `0x1800062a0`
- `0x18000696c`
- `0x18000968c`
- `0x1800097dc`
- `0x180009f40`
- `0x18000c840`
- `0x18000c860`
- `0x18000cd60`
- `0x18000cdb0`
- `0x18000cdf0`
- `0x18003a4a0`
- `0x18003a5f4`
- `0x18003a660`
- `0x18003a92c`
- `0x18003b2f4`
- `0x18003fd04`
- `0x18003fee0`
- `0x18003ff8c`
- `0x18007e528`
- `0x1800819a8`
- `0x180081a5c`
- `0x18008e508`
- `0x18008fa58`
- `0x1800951cc`
- `0x1800955a8`
- `0x180095964`
- `0x180095a0c`
- `0x1800a4998`
- `0x1800a5448`
- `0x1800a67b0`
- `0x1800a6950`
- `0x1800bcacc`
- `0x1800bcb00`
- `0x1800bcb0c`
- `0x1800bcb44`
- `0x1800bcf7c`
- `0x1800bd0c8`
- `0x1800becf0`
- `0x1800beda8`
- `0x1800bf55c`
- `0x1800c12a0`
- `0x1800c19a0`
- `0x1800c4710`
- `0x1800cac3c`

## import_xrefs

- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800c2021`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800c2059`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800c2021`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x1800c2059`
- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x1800c1e5c`
- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x1800c1e5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=46
void __fastcall Cortana::ConstraintIndex::Search::SettingsFilterCacheManager::ApplyWeightAndSynonymsToSQLiteIndex(
        Cortana::ConstraintIndex::Search::SettingsFilterCacheManager *this)
{
  HSTRING v1; // r15
  HSTRING ConstraintIndexExtractedCabPath; // rbx
  HSTRING v3; // r14
  __int64 v4; // rdi
  HRESULT v5; // eax
  HSTRING v6; // rbx
  PCWSTR StringRawBuffer_0; // rax
  __int64 GlobalWeights; // rax
  __int64 v9; // rdi
  HRESULT v10; // eax
  HSTRING v11; // rdi
  PCWSTR v12; // rax
  __int64 Synonyms; // rax
  const char *v14; // r9
  __int128 v15; // xmm0
  __int64 *v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rcx
  HSTRING v20; // r12
  __int64 **v21; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 k; // rbx
  __int64 v25; // r8
  __int64 v26; // r8
  __int64 v27; // r8
  __int64 v28; // r8
  const char *v29; // rax
  int v30; // r13d
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rcx
  HSTRING v34; // rdi
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rcx
  HSTRING v38; // r12
  __int64 v39; // rdi
  __int64 v40; // rbx
  HSTRING v41; // r12
  HSTRING v42; // r13
  __int64 v43; // rbx
  __int64 *v44; // rax
  HSTRING v45; // [rsp+20h] [rbp-368h]
  HSTRING v46; // [rsp+20h] [rbp-368h]
  HSTRING v47; // [rsp+28h] [rbp-360h] BYREF
  int v48; // [rsp+30h] [rbp-358h]
  int v49; // [rsp+34h] [rbp-354h]
  _QWORD v50[2]; // [rsp+38h] [rbp-350h] BYREF
  int v51; // [rsp+48h] [rbp-340h]
  int v52; // [rsp+4Ch] [rbp-33Ch]
  HSTRING v53; // [rsp+50h] [rbp-338h]
  _BYTE v54[32]; // [rsp+58h] [rbp-330h] BYREF
  _BYTE v55[32]; // [rsp+78h] [rbp-310h] BYREF
  _BYTE v56[96]; // [rsp+98h] [rbp-2F0h] BYREF
  HSTRING string; // [rsp+F8h] [rbp-290h] BYREF
  __int64 v58; // [rsp+100h] [rbp-288h] BYREF
  __int128 v59; // [rsp+108h] [rbp-280h] BYREF
  __int64 v60; // [rsp+118h] [rbp-270h]
  __int128 v61; // [rsp+120h] [rbp-268h] BYREF
  __int64 v62; // [rsp+130h] [rbp-258h]
  __int128 v63; // [rsp+138h] [rbp-250h] BYREF
  __int64 v64; // [rsp+148h] [rbp-240h]
  __int128 v65; // [rsp+150h] [rbp-238h] BYREF
  HSTRING_HEADER v66; // [rsp+160h] [rbp-228h] BYREF
  HSTRING v67; // [rsp+178h] [rbp-210h]
  HSTRING_HEADER hstringHeader; // [rsp+180h] [rbp-208h] BYREF
  _BYTE v69[16]; // [rsp+1A0h] [rbp-1E8h] BYREF
  __int64 v70; // [rsp+1B0h] [rbp-1D8h]
  _BYTE v71[32]; // [rsp+1C0h] [rbp-1C8h] BYREF
  _BYTE v72[128]; // [rsp+1E0h] [rbp-1A8h] BYREF
  _BYTE v73[240]; // [rsp+260h] [rbp-128h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+0h]

  v1 = (HSTRING)this;
  v47 = (HSTRING)this;
  v58 = 0;
  ConstraintIndexExtractedCabPath = (HSTRING)Cortana::ConstraintIndex::Search::DEUtilities::GetConstraintIndexExtractedCabPath(
                                               *((_QWORD *)this + 2),
                                               (__int64)&v58);
  v3 = (HSTRING)__abi_winrt_ptrto_string_ctor(ConstraintIndexExtractedCabPath);
  v53 = v3;
  WindowsDeleteString_0(ConstraintIndexExtractedCabPath);
  v65 = 0;
  std::map<std::string,int>::map<std::string,int>(&v65);
  v63 = 0;
  v64 = 0;
  std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(&v63);
  try
  {
    v4 = *(_QWORD *)(Platform::StringReference::StringReference(&v66, L"settingsglobals.txt") + 24);
    string = 0;
    v5 = WindowsCreateStringReference_0(L"\\", 1u, &hstringHeader, &string);
    if ( v5 < 0 )
      __abi_WinRTraiseException(v5);
    v6 = (HSTRING)Platform::String::Concat(v3, string);
    string = v6;
    v45 = (HSTRING)Platform::String::Concat(v6, v4);
    StringRawBuffer_0 = WindowsGetStringRawBuffer_0(v45, 0);
    GlobalWeights = Cortana::ConstraintIndex::Search::DEUtilities::ReadGlobalWeights(v50, StringRawBuffer_0);
    std::map<std::string,int>::operator=(&v65, GlobalWeights);
    std::_Tree<std::_Tmap_traits<std::string,int,std::less<std::string>,std::allocator<std::pair<std::string const,int>>,0>>::~_Tree<std::_Tmap_traits<std::string,int,std::less<std::string>,std::allocator<std::pair<std::string const,int>>,0>>(v50);
    WindowsDeleteString_0(v45);
    WindowsDeleteString_0(v6);
    WindowsDeleteString_0(v67);
    v9 = *(_QWORD *)(Platform::StringReference::StringReference(&v66, L"settingssynonyms.txt") + 24);
    string = 0;
    v10 = WindowsCreateStringReference_0(L"\\", 1u, &hstringHeader, &string);
    if ( v10 < 0 )
      __abi_WinRTraiseException(v10);
    v46 = (HSTRING)Platform::String::Concat(v3, string);
    v11 = (HSTRING)Platform::String::Concat(v46, v9);
    string = v11;
    v12 = WindowsGetStringRawBuffer_0(v11, 0);
    Synonyms = Cortana::ConstraintIndex::Search::DEUtilities::ReadSynonyms(v50, v12);
    std::vector<std::string>::operator=(&v63, Synonyms);
    std::vector<std::string>::_Tidy(v50);
    WindowsDeleteString_0(v11);
    WindowsDeleteString_0(v46);
    WindowsDeleteString_0(v67);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x2EF,
      (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\SettingsFilterCacheManager.cpp",
      v14);
    v3 = v53;
    v1 = v47;
  }
  v15 = 0;
  v61 = 0;
  v62 = 0;
  *(double *)&v15 = std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(&v61);
  v59 = v15;
  v60 = 0;
  std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(&v59);
  memset_0(v72, 0, 0x78u);
  std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>(v72);
  v16 = *(__int64 **)v65;
  while ( !*((_BYTE *)v16 + 25) )
  {
    v17 = std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::from_bytes(
            v72,
            &v66,
            v16 + 4);
    v18 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v17);
    v20 = (HSTRING)Platform::String::String(v19, v18);
    v47 = (HSTRING)__abi_winrt_ptrto_string_ctor(v20);
    v48 = *((_DWORD *)v16 + 16);
    v49 = 0;
    if ( *((_QWORD *)&v61 + 1) == v62 )
    {
      std::vector<WindowsUdk::System::Profile::SystemSettingEntryPointRank>::_Emplace_reallocate<WindowsUdk::System::Profile::SystemSettingEntryPointRank>(
        &v61,
        *((_QWORD *)&v61 + 1),
        &v47);
    }
    else
    {
      std::_Construct_in_place<WindowsUdk::System::Profile::SystemSettingEntryPointRank,WindowsUdk::System::Profile::SystemSettingEntryPointRank>(
        *((_QWORD *)&v61 + 1),
        &v47);
      *((_QWORD *)&v61 + 1) += 16LL;
    }
    WindowsDeleteString_0(v47);
    WindowsDeleteString_0(v20);
    std::wstring::_Tidy_deallocate(&v66);
    v21 = (__int64 **)v16[2];
    if ( *((_BYTE *)v21 + 25) )
    {
      for ( i = (__int64 *)v16[1]; !*((_BYTE *)i + 25) && v16 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v16 = i;
      v16 = i;
    }
    else
    {
      v16 = (__int64 *)v16[2];
      for ( j = *v21; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v16 = j;
    }
  }
  for ( k = v63; k != *((_QWORD *)&v63 + 1); k += 32 )
  {
    memset_0(v73, 0, sizeof(v73));
    std::istringstream::istringstream(v73, k);
    std::string::string(&v66);
    std::string::string(v69);
    std::string::string(&hstringHeader);
    std::string::string(v71);
    LOBYTE(v25) = 124;
    std::getline<char,std::char_traits<char>,std::allocator<char>>(v73, &v66, v25);
    LOBYTE(v26) = 9;
    std::getline<char,std::char_traits<char>,std::allocator<char>>(v73, v69, v26);
    LOBYTE(v27) = 124;
    std::getline<char,std::char_traits<char>,std::allocator<char>>(v73, &v66, v27);
    LOBYTE(v28) = 9;
    std::getline<char,std::char_traits<char>,std::allocator<char>>(v73, &hstringHeader, v28);
    std::getline<char,std::char_traits<char>,std::allocator<char>>(v73, v71);
    v29 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v71);
    v30 = atoi(v29);
    if ( v70 && *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] )
    {
      v31 = std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::from_bytes(
              v72,
              v55,
              v69);
      v32 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v31);
      v34 = (HSTRING)Platform::String::String(v33, v32);
      v50[0] = __abi_winrt_ptrto_string_ctor(v34);
      v47 = 0;
      v35 = std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::from_bytes(
              v72,
              v54,
              &hstringHeader);
      v36 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v35);
      v38 = (HSTRING)Platform::String::String(v37, v36);
      v47 = v38;
      v50[1] = __abi_winrt_ptrto_string_ctor(v38);
      v51 = v30;
      v52 = 0;
      if ( *((_QWORD *)&v59 + 1) == v60 )
      {
        std::vector<WindowsUdk::System::Profile::SystemSettingEntryPointSynonym>::_Emplace_reallocate<WindowsUdk::System::Profile::SystemSettingEntryPointSynonym>(
          &v59,
          *((_QWORD *)&v59 + 1),
          v50);
      }
      else
      {
        std::_Construct_in_place<WindowsUdk::System::Profile::SystemSettingEntryPointSynonym,WindowsUdk::System::Profile::SystemSettingEntryPointSynonym>(
          *((_QWORD *)&v59 + 1),
          v50);
        *((_QWORD *)&v59 + 1) += 24LL;
      }
      std::pair<Platform::String __gc * const,Platform::String __gc *>::~pair<Platform::String __gc * const,Platform::String __gc *>(v50);
      WindowsDeleteString_0(v38);
      std::wstring::_Tidy_deallocate(v54);
      WindowsDeleteString_0(v34);
      std::wstring::_Tidy_deallocate(v55);
    }
    std::string::_Tidy_deallocate(v71);
    std::string::_Tidy_deallocate(&hstringHeader);
    std::string::_Tidy_deallocate(v69);
    std::string::_Tidy_deallocate(&v66);
    std::istringstream::`vbase destructor'(v73);
  }
  if ( *((_QWORD *)v1 + 21) )
  {
    v39 = Concurrency::task_options::task_options((Concurrency::task_options *)v56);
    v40 = *((_QWORD *)v1 + 21);
    v47 = (HSTRING)Platform::Details::Heap::Allocate(0x58u, 0x88u);
    v41 = (HSTRING)Platform::Array<WindowsUdk::System::Profile::SystemSettingEntryPointRank,1>::Array<WindowsUdk::System::Profile::SystemSettingEntryPointRank,1>(
                     v47,
                     v61,
                     (__int64)(*((_QWORD *)&v61 + 1) - v61) >> 4);
    v47 = v41;
    string = (HSTRING)Platform::Details::Heap::Allocate(0x58u, 0x88u);
    v42 = (HSTRING)Platform::Array<WindowsUdk::System::Profile::SystemSettingEntryPointSynonym,1>::Array<WindowsUdk::System::Profile::SystemSettingEntryPointSynonym,1>(
                     string,
                     v59,
                     0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v59 + 1) - v59) >> 3));
    string = v42;
    v43 = WindowsUdk::System::Profile::ISystemSettingEntryPointIndex::SetSynonymsAndRanksAsync(v40, v42, v41);
    v44 = (__int64 *)Concurrency::create_task<Windows::Foundation::IAsyncAction __gc *>(v50, v43, v39);
    if ( !*v44 )
      Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl();
    Concurrency::details::_Task_impl_base::_Wait(*v44);
    std::shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>>::~shared_ptr<Concurrency::details::_Task_impl<Windows::Foundation::Collections::IVectorView<Cortana::ConstraintIndex::Search::ISettingResultItem __gc *> __gc *>>(v50);
    __abi_winrt_ptr_dtor(v43);
    __abi_winrt_ptr_dtor(v42);
    __abi_winrt_ptr_dtor(v41);
  }
  std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>(v72);
  if ( (_QWORD)v59 )
  {
    std::_Destroy_range<std::allocator<WindowsUdk::System::Profile::SystemSettingEntryPointSynonym>>(
      v59,
      *((_QWORD *)&v59 + 1));
    std::_Deallocate<16>((void *)v59, 8 * ((v60 - (__int64)v59) >> 3));
    v59 = 0;
    v60 = 0;
  }
  if ( (_QWORD)v61 )
  {
    std::_Destroy_range<std::allocator<WindowsUdk::System::Profile::SystemSettingEntryPointRank>>(
      v61,
      *((_QWORD *)&v61 + 1));
    std::_Deallocate<16>((void *)v61, (v62 - v61) & 0xFFFFFFFFFFFFFFF0uLL);
    v61 = 0;
    v62 = 0;
  }
  std::vector<std::string>::_Tidy(&v63);
  std::_Tree<std::_Tmap_traits<std::string,int,std::less<std::string>,std::allocator<std::pair<std::string const,int>>,0>>::~_Tree<std::_Tmap_traits<std::string,int,std::less<std::string>,std::allocator<std::pair<std::string const,int>>,0>>(&v65);
  WindowsDeleteString_0(v3);
  __abi_winrt_ptr_dtor(v58);
}

```

## disassembly

```asm
0x1800c19a0  mov     r11, rsp
0x1800c19a3  mov     [r11+10h], rbx
0x1800c19a7  mov     [r11+18h], rsi
0x1800c19ab  push    rdi
0x1800c19ac  push    r12
0x1800c19ae  push    r13
0x1800c19b0  push    r14
0x1800c19b2  push    r15
0x1800c19b4  sub     rsp, 360h
0x1800c19bb  mov     rax, cs:__security_cookie
0x1800c19c2  xor     rax, rsp
0x1800c19c5  mov     [rsp+388h+var_38], rax
0x1800c19cd  mov     r15, rcx
0x1800c19d0  mov     [rsp+388h+var_360], rcx
0x1800c19d5  xor     esi, esi
0x1800c19d7  mov     [r11-288h], rsi
0x1800c19de  lea     rdx, [r11-288h]
0x1800c19e5  mov     rcx, [rcx+10h]
0x1800c19e9  call    ?GetConstraintIndexExtractedCabPath@DEUtilities@Search@ConstraintIndex@Cortana@@SAPE$AAVString@Platform@@PE$AAUIConstraintIndexOptions@234@PEAPE$AAVObject@6@@Z; Cortana::ConstraintIndex::Search::DEUtilities::GetConstraintIndexExtractedCabPath(Cortana::ConstraintIndex::Search::IConstraintIndexOptions *,Platform::Object * *)
0x1800c19ee  mov     rbx, rax
0x1800c19f1  mov     [rsp+388h+var_338], rax
0x1800c19f6  mov     rcx, rax
0x1800c19f9  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800c19fe  mov     r14, rax
0x1800c1a01  mov     [rsp+388h+var_338], rax
0x1800c1a06  mov     rcx, rbx; string
0x1800c1a09  call    WindowsDeleteString_0
0x1800c1a0e  nop
0x1800c1a0f  xorps   xmm0, xmm0
0x1800c1a12  movups  [rsp+388h+var_238], xmm0
0x1800c1a1a  lea     rcx, [rsp+388h+var_238]
0x1800c1a22  call    ??0?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HU?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@H@std@@@2@@std@@QEAA@XZ; std::map<std::string,int>::map<std::string,int>(void)
0x1800c1a27  nop
0x1800c1a28  xorps   xmm0, xmm0
0x1800c1a2b  xor     eax, eax
0x1800c1a2d  movups  [rsp+388h+var_250], xmm0
0x1800c1a35  mov     [rsp+388h+var_240], rax
0x1800c1a3d  lea     rcx, [rsp+388h+var_250]
0x1800c1a45  call    ??0?$vector@U?$pair@GG@std@@V?$allocator@U?$pair@GG@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<ushort,ushort>>::vector<std::pair<ushort,ushort>>(void)
0x1800c1a4a  nop
0x1800c1a4b  lea     rdx, aSettingsglobal; "settingsglobals.txt"
0x1800c1a52  lea     rcx, [rsp+388h+var_228]; hstringHeader
0x1800c1a5a  call    ??0StringReference@Platform@@QEAA@PEB_W@Z; Platform::StringReference::StringReference(wchar_t const *)
0x1800c1a5f  nop
0x1800c1a60  mov     rdi, [rax+18h]
0x1800c1a64  mov     [rsp+388h+string], rsi
0x1800c1a6c  lea     r9, [rsp+388h+string]; string
0x1800c1a74  lea     r8, [rsp+388h+hstringHeader]; hstringHeader
0x1800c1a7c  lea     r12d, [rsi+1]
0x1800c1a80  mov     edx, r12d; length
0x1800c1a83  lea     rcx, asc_180104F88; "\\"
0x1800c1a8a  call    WindowsCreateStringReference_0
0x1800c1a8f  test    eax, eax
0x1800c1a91  jns     short loc_1800C1A9A
0x1800c1a93  mov     ecx, eax; int
0x1800c1a95  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1800c1a9a  mov     rdx, [rsp+388h+string]
0x1800c1aa2  mov     rcx, r14
0x1800c1aa5  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x1800c1aaa  mov     rbx, rax
0x1800c1aad  mov     [rsp+388h+string], rax
0x1800c1ab5  mov     rdx, rdi
0x1800c1ab8  mov     rcx, rax
0x1800c1abb  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x1800c1ac0  mov     rdi, rax
0x1800c1ac3  mov     [rsp+388h+var_368], rax
0x1800c1ac8  xor     edx, edx; length
0x1800c1aca  mov     rcx, rax; string
0x1800c1acd  call    WindowsGetStringRawBuffer_0
0x1800c1ad2  mov     rdx, rax
0x1800c1ad5  lea     rcx, [rsp+388h+var_350]
0x1800c1ada  call    ?ReadGlobalWeights@DEUtilities@Search@ConstraintIndex@Cortana@@SA?AV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HU?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@H@std@@@2@@std@@PEB_W@Z; Cortana::ConstraintIndex::Search::DEUtilities::ReadGlobalWeights(wchar_t const *)
0x1800c1adf  mov     rdx, rax
0x1800c1ae2  lea     rcx, [rsp+388h+var_238]
0x1800c1aea  call    ??4?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HU?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@H@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::map<std::string,int>::operator=(std::map<std::string,int> &&)
0x1800c1aef  lea     rcx, [rsp+388h+var_350]
0x1800c1af4  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HU?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@H@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,int,std::less<std::string>,std::allocator<std::pair<std::string const,int>>,0>>::~_Tree<std::_Tmap_traits<std::string,int,std::less<std::string>,std::allocator<std::pair<std::string const,int>>,0>>(void)
0x1800c1af9  nop
0x1800c1afa  mov     rcx, rdi; string
0x1800c1afd  call    WindowsDeleteString_0
0x1800c1b02  nop
0x1800c1b03  mov     rcx, rbx; string
0x1800c1b06  call    WindowsDeleteString_0
0x1800c1b0b  nop
0x1800c1b0c  mov     rcx, [rsp+388h+var_210]; string
0x1800c1b14  call    WindowsDeleteString_0
0x1800c1b19  lea     rdx, aSettingssynony; "settingssynonyms.txt"
0x1800c1b20  lea     rcx, [rsp+388h+var_228]; hstringHeader
0x1800c1b28  call    ??0StringReference@Platform@@QEAA@PEB_W@Z; Platform::StringReference::StringReference(wchar_t const *)
0x1800c1b2d  nop
0x1800c1b2e  mov     rdi, [rax+18h]
0x1800c1b32  mov     [rsp+388h+string], rsi
0x1800c1b3a  lea     r9, [rsp+388h+string]; string
0x1800c1b42  lea     r8, [rsp+388h+hstringHeader]; hstringHeader
0x1800c1b4a  mov     edx, r12d; length
0x1800c1b4d  lea     rcx, asc_180104F88; "\\"
0x1800c1b54  call    WindowsCreateStringReference_0
0x1800c1b59  test    eax, eax
0x1800c1b5b  jns     short loc_1800C1B64
0x1800c1b5d  mov     ecx, eax; int
0x1800c1b5f  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x1800c1b64  mov     rdx, [rsp+388h+string]
0x1800c1b6c  mov     rcx, r14
0x1800c1b6f  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x1800c1b74  mov     rbx, rax
0x1800c1b77  mov     [rsp+388h+var_368], rax
0x1800c1b7c  mov     rdx, rdi
0x1800c1b7f  mov     rcx, rax
0x1800c1b82  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x1800c1b87  mov     rdi, rax
0x1800c1b8a  mov     [rsp+388h+string], rax
0x1800c1b92  xor     edx, edx; length
0x1800c1b94  mov     rcx, rax; string
0x1800c1b97  call    WindowsGetStringRawBuffer_0
0x1800c1b9c  mov     rdx, rax
0x1800c1b9f  lea     rcx, [rsp+388h+var_350]
0x1800c1ba4  call    ?ReadSynonyms@DEUtilities@Search@ConstraintIndex@Cortana@@SA?AV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@PEB_W@Z; Cortana::ConstraintIndex::Search::DEUtilities::ReadSynonyms(wchar_t const *)
0x1800c1ba9  mov     rdx, rax
0x1800c1bac  lea     rcx, [rsp+388h+var_250]
0x1800c1bb4  call    ??4?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<std::string>::operator=(std::vector<std::string> &&)
0x1800c1bb9  lea     rcx, [rsp+388h+var_350]
0x1800c1bbe  call    ?_Tidy@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::string>::_Tidy(void)
0x1800c1bc3  nop
0x1800c1bc4  mov     rcx, rdi; string
0x1800c1bc7  call    WindowsDeleteString_0
0x1800c1bcc  nop
0x1800c1bcd  mov     rcx, rbx; string
0x1800c1bd0  call    WindowsDeleteString_0
0x1800c1bd5  nop
0x1800c1bd6  mov     rcx, [rsp+388h+var_210]; string
0x1800c1bde  call    WindowsDeleteString_0
0x1800c1be3  nop
0x1800c1be4  jmp     short loc_1800C1BF2
0x1800c1be6  xor     esi, esi
0x1800c1be8  mov     r14, [rsp+388h+var_338]
0x1800c1bed  mov     r15, [rsp+388h+var_360]
0x1800c1bf2  xorps   xmm0, xmm0
0x1800c1bf5  xor     eax, eax
0x1800c1bf7  movups  [rsp+388h+var_268], xmm0
0x1800c1bff  mov     [rsp+388h+var_258], rax
0x1800c1c07  lea     rcx, [rsp+388h+var_268]
0x1800c1c0f  call    ??0?$vector@U?$pair@GG@std@@V?$allocator@U?$pair@GG@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<ushort,ushort>>::vector<std::pair<ushort,ushort>>(void)
0x1800c1c14  nop
0x1800c1c15  xor     eax, eax
0x1800c1c17  movups  [rsp+388h+var_280], xmm0
0x1800c1c1f  mov     [rsp+388h+var_270], rax
0x1800c1c27  lea     rcx, [rsp+388h+var_280]
0x1800c1c2f  call    ??0?$vector@U?$pair@GG@std@@V?$allocator@U?$pair@GG@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<ushort,ushort>>::vector<std::pair<ushort,ushort>>(void)
0x1800c1c34  nop
0x1800c1c35  xor     edx, edx; Val
0x1800c1c37  lea     r8d, [rdx+78h]; Size
0x1800c1c3b  lea     rcx, [rsp+388h+var_1A8]; void *
0x1800c1c43  call    memset_0
0x1800c1c48  lea     rcx, [rsp+388h+var_1A8]
0x1800c1c50  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@_W$0BAPPPP@$0A@@std@@_WV?$allocator@_W@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>(void)
0x1800c1c55  nop
0x1800c1c56  mov     rbx, qword ptr [rsp+388h+var_238]
0x1800c1c5e  mov     rbx, [rbx]
0x1800c1c61  cmp     [rbx+19h], sil
0x1800c1c65  jnz     loc_1800C1D6C
0x1800c1c6b  mov     [rsp+388h+var_368], rsi
0x1800c1c70  lea     r8, [rbx+20h]
0x1800c1c74  lea     rdx, [rsp+388h+var_228]
0x1800c1c7c  lea     rcx, [rsp+388h+var_1A8]
0x1800c1c84  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@_W$0BAPPPP@$0A@@std@@_WV?$allocator@_W@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::from_bytes(std::string const &)
0x1800c1c89  nop
0x1800c1c8a  mov     rcx, rax
0x1800c1c8d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800c1c92  mov     rdx, rax
0x1800c1c95  call    ??0String@Platform@@QE$AAA@PEB_W@Z; Platform::String::String(wchar_t const *)
0x1800c1c9a  mov     r12, rax
0x1800c1c9d  mov     [rsp+388h+var_368], rax
0x1800c1ca2  mov     rcx, rax
0x1800c1ca5  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800c1caa  mov     [rsp+388h+var_360], rax
0x1800c1caf  mov     ecx, [rbx+40h]
0x1800c1cb2  mov     [rsp+388h+var_358], ecx
0x1800c1cb6  xor     eax, eax
0x1800c1cb8  mov     [rsp+388h+var_354], eax
0x1800c1cbc  mov     rax, qword ptr [rsp+388h+var_268+8]
0x1800c1cc4  cmp     rax, [rsp+388h+var_258]
0x1800c1ccc  jz      short loc_1800C1CE6
0x1800c1cce  lea     rdx, [rsp+388h+var_360]
0x1800c1cd3  mov     rcx, rax
0x1800c1cd6  call    ??$_Construct_in_place@VSystemSettingEntryPointRank@Profile@System@WindowsUdk@@V1234@@std@@YAXAEAVSystemSettingEntryPointRank@Profile@System@WindowsUdk@@$$QEAV1234@@Z; std::_Construct_in_place<WindowsUdk::System::Profile::SystemSettingEntryPointRank,WindowsUdk::System::Profile::SystemSettingEntryPointRank>(WindowsUdk::System::Profile::SystemSettingEntryPointRank &,WindowsUdk::System::Profile::SystemSettingEntryPointRank &&)
0x1800c1cdb  add     qword ptr [rsp+388h+var_268+8], 10h
0x1800c1ce4  jmp     short loc_1800C1CFC
0x1800c1ce6  lea     r8, [rsp+388h+var_360]
0x1800c1ceb  mov     rdx, rax
0x1800c1cee  lea     rcx, [rsp+388h+var_268]
0x1800c1cf6  call    ??$_Emplace_reallocate@VSystemSettingEntryPointRank@Profile@System@WindowsUdk@@@?$vector@VSystemSettingEntryPointRank@Profile@System@WindowsUdk@@V?$allocator@VSystemSettingEntryPointRank@Profile@System@WindowsUdk@@@std@@@std@@AEAAPEAVSystemSettingEntryPointRank@Profile@System@WindowsUdk@@QEAV2345@$$QEAV2345@@Z; std::vector<WindowsUdk::System::Profile::SystemSettingEntryPointRank>::_Emplace_reallocate<WindowsUdk::System::Profile::SystemSettingEntryPointRank>(WindowsUdk::System::Profile::SystemSettingEntryPointRank * const,WindowsUdk::System::Profile::SystemSettingEntryPointRank &&)
0x1800c1cfb  nop
0x1800c1cfc  mov     rcx, [rsp+388h+var_360]; string
0x1800c1d01  call    WindowsDeleteString_0
0x1800c1d06  nop
0x1800c1d07  mov     rcx, r12; string
0x1800c1d0a  call    WindowsDeleteString_0
0x1800c1d0f  nop
0x1800c1d10  lea     rcx, [rsp+388h+var_228]
0x1800c1d18  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c1d1d  mov     rcx, [rbx+10h]
0x1800c1d21  cmp     [rcx+19h], sil
0x1800c1d25  jz      short loc_1800C1D48
0x1800c1d27  mov     rax, [rbx+8]
0x1800c1d2b  jmp     short loc_1800C1D3A
0x1800c1d2d  cmp     rbx, [rax+10h]
0x1800c1d31  jnz     short loc_1800C1D40
0x1800c1d33  mov     rbx, rax
0x1800c1d36  mov     rax, [rax+8]
0x1800c1d3a  cmp     [rax+19h], sil
0x1800c1d3e  jz      short loc_1800C1D2D
0x1800c1d40  mov     rbx, rax
0x1800c1d43  jmp     loc_1800C1C61
0x1800c1d48  mov     rbx, rcx
0x1800c1d4b  mov     rcx, [rcx]
0x1800c1d4e  cmp     [rcx+19h], sil
0x1800c1d52  jnz     loc_1800C1C61
0x1800c1d58  mov     rbx, rcx
0x1800c1d5b  mov     rax, [rcx]
0x1800c1d5e  mov     rcx, rax
0x1800c1d61  cmp     [rax+19h], sil
0x1800c1d65  jz      short loc_1800C1D58
0x1800c1d67  jmp     loc_1800C1C61
0x1800c1d6c  mov     rbx, qword ptr [rsp+388h+var_250]
0x1800c1d74  jmp     loc_1800C1FD2
0x1800c1d79  xor     edx, edx; Val
0x1800c1d7b  mov     r8d, 0F0h; Size
0x1800c1d81  lea     rcx, [rsp+388h+var_128]; void *
0x1800c1d89  call    memset_0
0x1800c1d8e  mov     rdx, rbx
0x1800c1d91  lea     rcx, [rsp+388h+var_128]
0x1800c1d99  call    ??0?$basic_istringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@H@Z; std::istringstream::istringstream(std::string const &,int)
0x1800c1d9e  nop
0x1800c1d9f  lea     rcx, [rsp+388h+var_228]
0x1800c1da7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x1800c1dac  nop
0x1800c1dad  lea     rcx, [rsp+388h+var_1E8]
0x1800c1db5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x1800c1dba  nop
0x1800c1dbb  lea     rcx, [rsp+388h+hstringHeader]
0x1800c1dc3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x1800c1dc8  nop
0x1800c1dc9  lea     rcx, [rsp+388h+var_1C8]
0x1800c1dd1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x1800c1dd6  nop
0x1800c1dd7  mov     r8b, 7Ch ; '|'
0x1800c1dda  lea     rdx, [rsp+388h+var_228]
0x1800c1de2  lea     rcx, [rsp+388h+var_128]
0x1800c1dea  call    ??$getline@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@YAAEAV?$basic_istream@DU?$char_traits@D@std@@@0@$$QEAV10@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@D@Z; std::getline<char,std::char_traits<char>,std::allocator<char>>(std::istream &&,std::string &,char)
0x1800c1def  mov     r8b, 9
0x1800c1df2  lea     rdx, [rsp+388h+var_1E8]
0x1800c1dfa  lea     rcx, [rsp+388h+var_128]
0x1800c1e02  call    ??$getline@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@YAAEAV?$basic_istream@DU?$char_traits@D@std@@@0@$$QEAV10@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@D@Z; std::getline<char,std::char_traits<char>,std::allocator<char>>(std::istream &&,std::string &,char)
0x1800c1e07  mov     r8b, 7Ch ; '|'
0x1800c1e0a  lea     rdx, [rsp+388h+var_228]
0x1800c1e12  lea     rcx, [rsp+388h+var_128]
0x1800c1e1a  call    ??$getline@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@YAAEAV?$basic_istream@DU?$char_traits@D@std@@@0@$$QEAV10@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@D@Z; std::getline<char,std::char_traits<char>,std::allocator<char>>(std::istream &&,std::string &,char)
0x1800c1e1f  mov     r8b, 9
0x1800c1e22  lea     rdx, [rsp+388h+hstringHeader]
0x1800c1e2a  lea     rcx, [rsp+388h+var_128]
0x1800c1e32  call    ??$getline@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@YAAEAV?$basic_istream@DU?$char_traits@D@std@@@0@$$QEAV10@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@D@Z; std::getline<char,std::char_traits<char>,std::allocator<char>>(std::istream &&,std::string &,char)
0x1800c1e37  lea     rdx, [rsp+388h+var_1C8]
0x1800c1e3f  lea     rcx, [rsp+388h+var_128]
0x1800c1e47  call    ??$getline@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@YAAEAV?$basic_istream@DU?$char_traits@D@std@@@0@AEAV10@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::getline<char,std::char_traits<char>,std::allocator<char>>(std::istream &,std::string &)
0x1800c1e4c  lea     rcx, [rsp+388h+var_1C8]
0x1800c1e54  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800c1e59  mov     rcx, rax; String
0x1800c1e5c  call    cs:__imp_atoi
0x1800c1e62  mov     r13d, eax
0x1800c1e65  cmp     [rsp+388h+var_1D8], rsi
0x1800c1e6d  jz      loc_1800C1F89
0x1800c1e73  cmp     qword ptr [rsp+388h+hstringHeader.Reserved+10h], rsi
0x1800c1e7b  jz      loc_1800C1F89
0x1800c1e81  mov     [rsp+388h+var_368], rsi
0x1800c1e86  lea     r8, [rsp+388h+var_1E8]
0x1800c1e8e  lea     rdx, [rsp+388h+var_310]
0x1800c1e93  lea     rcx, [rsp+388h+var_1A8]
0x1800c1e9b  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@_W$0BAPPPP@$0A@@std@@_WV?$allocator@_W@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::from_bytes(std::string const &)
0x1800c1ea0  nop
0x1800c1ea1  mov     rcx, rax
0x1800c1ea4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800c1ea9  mov     rdx, rax
0x1800c1eac  call    ??0String@Platform@@QE$AAA@PEB_W@Z; Platform::String::String(wchar_t const *)
0x1800c1eb1  mov     rdi, rax
0x1800c1eb4  mov     [rsp+388h+var_368], rax
0x1800c1eb9  mov     rcx, rax
0x1800c1ebc  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x1800c1ec1  mov     [rsp+388h+var_350], rax
0x1800c1ec6  mov     [rsp+388h+var_360], rsi
0x1800c1ecb  lea     r8, [rsp+388h+hstringHeader]
0x1800c1ed3  lea     rdx, [rsp+388h+var_330]
0x1800c1ed8  lea     rcx, [rsp+388h+var_1A8]
0x1800c1ee0  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@_W$0BAPPPP@$0A@@std@@_WV?$allocator@_W@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::wstring_convert<std::codecvt_utf8_utf16<wchar_t,1114111,0>,wchar_t,std::allocator<wchar_t>,std::allocator<char>>::from_bytes(std::string const &)
0x1800c1ee5  nop
0x1800c1ee6  mov     rcx, rax
0x1800c1ee9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800c1eee  mov     rdx, rax
0x1800c1ef1  call    ??0String@Platform@@QE$AAA@PEB_W@Z; Platform::String::String(wchar_t const *)
0x1800c1ef6  mov     r12, rax
0x1800c1ef9  mov     [rsp+388h+var_360], rax
  ... truncated ...
```
