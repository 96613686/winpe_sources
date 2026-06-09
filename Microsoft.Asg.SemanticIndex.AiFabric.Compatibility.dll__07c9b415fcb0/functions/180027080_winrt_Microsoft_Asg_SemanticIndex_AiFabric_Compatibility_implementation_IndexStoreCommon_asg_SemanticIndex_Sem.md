# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::ResetVectorSpaceIds(winrt::hstring const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexEncryptionOptions const &,winrt::guid const &,winrt::guid const &)

- ea: `0x180027080`
- end: `0x180027442`
- name: `?ResetVectorSpaceIds@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SAXAEBUhstring@8@AEBUIndexEncryptionOptions@345678@AEBUguid@8@2@Z`
- size: `962`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180022100`

## callees

- `0x180003fb0`
- `0x180004510`
- `0x180007740`
- `0x180007830`
- `0x180007de0`
- `0x18000cf10`
- `0x18000d230`
- `0x180010400`
- `0x180019520`
- `0x180027080`
- `0x180027450`
- `0x18002da90`
- `0x180067b60`
- `0x180067f30`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206ec0`
- `0x180242120`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18002737f`
- `KERNEL32!CloseHandle` at `0x18002737f`

## string_xrefs

- `0x1800273fc`: `could not get exclusive access to the database lock file`
- `0x18002721a`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x1800272e9`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x1800273eb`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x180027226`: `void __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::A`
- `0x1800272f5`: `void __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::A`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::ResetVectorSpaceIds(
        __int64 a1,
        __int64 *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  __int64 result; // rax
  const wchar_t *v8; // rdx
  __int64 v9; // r8
  _QWORD *v10; // rbx
  _QWORD *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 DbAesKeyStore; // rax
  void *v15; // rcx
  void *v16; // rcx
  unsigned int *v17; // rax
  __int64 v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  const char *v20; // [rsp+50h] [rbp-B0h]
  __int128 v21; // [rsp+60h] [rbp-A0h] BYREF
  const char *v22; // [rsp+70h] [rbp-90h]
  __int64 v23; // [rsp+78h] [rbp-88h]
  _BYTE v24[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v25; // [rsp+88h] [rbp-78h]
  __int64 v26; // [rsp+90h] [rbp-70h]
  _QWORD *v27; // [rsp+A0h] [rbp-60h] BYREF
  __int128 *p_pExceptionObject; // [rsp+A8h] [rbp-58h]
  _QWORD *v29; // [rsp+B0h] [rbp-50h]
  _QWORD *v30; // [rsp+B8h] [rbp-48h]
  _QWORD *v31; // [rsp+C0h] [rbp-40h]
  _QWORD Src[3]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v33; // [rsp+E0h] [rbp-20h]
  _QWORD v34[4]; // [rsp+E8h] [rbp-18h] BYREF

  if ( *a3
    || a3[1] != _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0]
    || *a4
    || (result = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0], a4[1] != result) )
  {
    if ( *(_QWORD *)a1 )
      v8 = *(const wchar_t **)(*(_QWORD *)a1 + 16LL);
    else
      v8 = &String;
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    v21 = 0;
    v22 = 0;
    v23 = 0;
    std::basic_string<char16_t>::_Construct<1,char16_t const *>(&v21);
    winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::AppendDbExtensionIfRequired(
      (__int64)v34,
      (std::filesystem *)&v21);
    v18[0] = (__int64)operator new(0x30u);
    std::basic_string<char16_t>::basic_string<char16_t>(v24, v34);
    v10 = (_QWORD *)winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile::IndexLockFile(
                      v18[0],
                      (__int64)v24,
                      1u);
    v31 = v10;
    if ( v10[5] == -1 )
    {
      LODWORD(v21) = 106;
      *((_QWORD *)&v21 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
      v22 = 0;
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)v24,
        L"could not get exclusive access to the database lock file");
      v17 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)v18, -2081706721);
      winrt::hresult_error::hresult_error(&pExceptionObject, *v17, v24, &v21);
      throw (winrt::hresult_error *)&pExceptionObject;
    }
    v11 = v34;
    if ( v34[3] > 7u )
      v11 = (_QWORD *)v34[0];
    *(_QWORD *)&pExceptionObject = v11;
    *((_QWORD *)&pExceptionObject + 1) = v34[2];
    v21 = pExceptionObject;
    std::_Convert_wide_to_narrow<std::char_traits<char8_t>>(Src);
    if ( (unsigned __int8)asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_57460691>>() )
    {
      v12 = *a2;
      v18[0] = v12;
      if ( v12 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDbAesKeyStore(v24, v18);
      *(_QWORD *)&pExceptionObject = v25;
      *((_QWORD *)&pExceptionObject + 1) = v26 - v25;
      *(_QWORD *)&v21 = 0x1100000074LL;
      *((_QWORD *)&v21 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
      v22 = "void __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon"
            "<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compati"
            "bility::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::imple"
            "mentation::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Te"
            "xtEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::"
            "TextEmbeddingsGenerator>::ResetVectorSpaceIds(const struct winrt::hstring &,const struct winrt::Microsoft::A"
            "sg::SemanticIndex::AiFabric::Compatibility::IndexEncryptionOptions &,const struct winrt::guid &,const struct winrt::guid &)";
      v27 = Src;
      p_pExceptionObject = &pExceptionObject;
      v29 = a3;
      v30 = a4;
      ___SemanticIndexCall_V_lambda_2___N___ResetVectorSpaceIds___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SAXAEBUhstring_winrt__AEBUIndexEncryptionOptions_56789winrt__AEBUguid_winrt__2_Z__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__YA_A_P__QEAV_lambda_2___N___ResetVectorSpaceIds___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__0123456_SAXAEBUhstring_6_AEBUIndexEncryptionOptions_123456_AEBUguid_6_2_Z_AEBUsource_location_std___Z(
        &v27,
        &v21);
      std::vector<unsigned char,asg::secure_allocator<unsigned char>>::_Tidy(v24);
    }
    else
    {
      *(_QWORD *)&pExceptionObject = 0;
      v13 = *a2;
      if ( *a2 )
      {
        v18[0] = *a2;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
        DbAesKeyStore = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDbAesKeyStore(
                          v24,
                          v18);
        *(_QWORD *)&pExceptionObject = *(_QWORD *)(DbAesKeyStore + 8);
        *((_QWORD *)&pExceptionObject + 1) = *(_QWORD *)(DbAesKeyStore + 16) - pExceptionObject;
        v21 = pExceptionObject;
        std::vector<unsigned char,asg::secure_allocator<unsigned char>>::_Tidy(v24);
      }
      else
      {
        pExceptionObject = 0u;
        v21 = 0u;
      }
      *(_QWORD *)&pExceptionObject = 0x1100000085LL;
      *((_QWORD *)&pExceptionObject + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\I"
                                           "ndexStoreCommon.h";
      v20 = "void __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon"
            "<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compati"
            "bility::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::imple"
            "mentation::ImageEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Te"
            "xtEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::"
            "TextEmbeddingsGenerator>::ResetVectorSpaceIds(const struct winrt::hstring &,const struct winrt::Microsoft::A"
            "sg::SemanticIndex::AiFabric::Compatibility::IndexEncryptionOptions &,const struct winrt::guid &,const struct winrt::guid &)";
      v27 = Src;
      p_pExceptionObject = &v21;
      v29 = a3;
      v30 = a4;
      ___SemanticIndexCall_V_lambda_2___N___ResetVectorSpaceIds___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SAXAEBUhstring_winrt__AEBUIndexEncryptionOptions_56789winrt__AEBUguid_winrt__2_Z__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__YA_A_P__QEAV_lambda_2___N___ResetVectorSpaceIds___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UImageEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_UTextEmbeddingsGenerator_562789_UTextEmbeddingsGenerator_implementation_562789__0123456_SAXAEBUhstring_6_AEBUIndexEncryptionOptions_123456_AEBUguid_6_2_Z_AEBUsource_location_std___Z(
        &v27,
        &pExceptionObject);
    }
    if ( v33 > 0xF )
    {
      v15 = (void *)Src[0];
      if ( v33 + 1 >= 0x1000 )
      {
        v15 = *(void **)(Src[0] - 8LL);
        if ( (unsigned __int64)(Src[0] - (_QWORD)v15 - 8LL) > 0x1F )
          invoke_watson(0, 0, 0, 0, 0);
      }
      operator delete(v15);
    }
    Src[2] = 0;
    v33 = 15;
    LOBYTE(Src[0]) = 0;
    v16 = (void *)v10[5];
    if ( v16 != (void *)-1LL )
    {
      if ( v16 )
        CloseHandle(v16);
    }
    std::basic_string<char16_t>::_Tidy_deallocate(v10 + 1);
    operator delete(v10);
    return std::basic_string<char16_t>::_Tidy_deallocate(v34);
  }
  return result;
}

```

## disassembly

```asm
0x180027080  mov     [rsp-8+arg_0], rbx
0x180027085  mov     [rsp-8+arg_10], rsi
0x18002708a  mov     [rsp-8+arg_18], rdi
0x18002708f  push    rbp
0x180027090  push    r14
0x180027092  push    r15
0x180027094  lea     rbp, [rsp-10h]
0x180027099  sub     rsp, 110h
0x1800270a0  mov     rax, cs:__security_cookie
0x1800270a7  xor     rax, rsp
0x1800270aa  mov     [rbp+20h+var_18], rax
0x1800270ae  mov     rdi, r9
0x1800270b1  mov     rsi, r8
0x1800270b4  mov     r14, rdx
0x1800270b7  xor     r15d, r15d
0x1800270ba  xorps   xmm0, xmm0
0x1800270bd  movq    rax, xmm0
0x1800270c2  cmp     [r8], rax
0x1800270c5  jnz     short loc_1800270F8
0x1800270c7  psrldq  xmm0, 8
0x1800270cc  movq    rax, xmm0
0x1800270d1  cmp     [r8+8], rax
0x1800270d5  jnz     short loc_1800270F8
0x1800270d7  xorps   xmm0, xmm0
0x1800270da  movq    rax, xmm0
0x1800270df  cmp     [r9], rax
0x1800270e2  jnz     short loc_1800270F8
0x1800270e4  psrldq  xmm0, 8
0x1800270e9  movq    rax, xmm0
0x1800270ee  cmp     [r9+8], rax
0x1800270f2  jz      loc_1800273A5
0x1800270f8  mov     rdx, [rcx]
0x1800270fb  test    rdx, rdx
0x1800270fe  jz      short loc_180027106
0x180027100  mov     rdx, [rdx+10h]
0x180027104  jmp     short loc_18002710D
0x180027106  lea     rdx, String
0x18002710d  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180027114  inc     r8
0x180027117  cmp     [rdx+r8*2], r15w
0x18002711c  jnz     short loc_180027114
0x18002711e  xorps   xmm0, xmm0
0x180027121  movups  [rsp+120h+var_C0], xmm0
0x180027126  mov     [rsp+120h+var_B0], r15
0x18002712b  mov     [rsp+120h+var_A8], r15
0x180027130  lea     rcx, [rsp+120h+var_C0]
0x180027135  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x18002713a  lea     rdx, [rsp+120h+var_C0]
0x18002713f  lea     rcx, [rbp+20h+var_38]
0x180027143  call    ?AppendDbExtensionIfRequired@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AVpath@filesystem@std@@V89std@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::AppendDbExtensionIfRequired(std::filesystem::path)
0x180027148  nop
0x180027149  mov     ecx, 30h ; '0'; Size
0x18002714e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027153  mov     rbx, rax
0x180027156  mov     [rsp+120h+var_F0], rax
0x18002715b  lea     rdx, [rbp+20h+var_38]
0x18002715f  lea     rcx, [rbp+20h+var_A0]
0x180027163  call    ??0?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAA@AEBV01@@Z; std::basic_string<char16_t>::basic_string<char16_t>(std::basic_string<char16_t> const &)
0x180027168  mov     r8b, 1
0x18002716b  lea     rdx, [rbp+20h+var_A0]
0x18002716f  mov     rcx, rbx
0x180027172  call    ??0IndexLockFile@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@Vpath@filesystem@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile::IndexLockFile(std::filesystem::path,bool)
0x180027177  mov     rbx, rax
0x18002717a  mov     [rbp+20h+var_60], rax
0x18002717e  cmp     qword ptr [rax+28h], 0FFFFFFFFFFFFFFFFh
0x180027183  jz      loc_1800273E3
0x180027189  lea     rax, [rbp+20h+var_38]
0x18002718d  cmp     [rbp+20h+var_20], 7
0x180027192  cmova   rax, [rbp+20h+var_38]
0x180027197  mov     qword ptr [rsp+120h+pExceptionObject], rax
0x18002719c  mov     rax, [rbp+20h+var_28]
0x1800271a0  mov     qword ptr [rsp+120h+pExceptionObject+8], rax
0x1800271a5  movaps  xmm0, [rsp+120h+pExceptionObject]
0x1800271aa  movdqa  [rsp+120h+var_C0], xmm0
0x1800271b0  lea     r8, [rsp+120h+var_C0]
0x1800271b5  lea     rcx, [rbp+20h+Src]; Src
0x1800271b9  call    ??$_Convert_wide_to_narrow@U?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@YA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@0@W4__std_code_page@@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@AEBV?$allocator@_Q@0@@Z; std::_Convert_wide_to_narrow<std::char_traits<char8_t>>(__std_code_page,std::wstring_view,std::allocator<char8_t> const &)
0x1800271be  nop
0x1800271bf  call    ??$IsFeatureEnabled@V?$Feature@U__WilFeatureTraits_Feature_57460691@@@wil@@@asg@@YA_NXZ; asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_57460691>>(void)
0x1800271c4  test    al, al
0x1800271c6  jz      loc_180027268
0x1800271cc  mov     rcx, [r14]
0x1800271cf  mov     [rsp+120h+var_F0], rcx
0x1800271d4  test    rcx, rcx
0x1800271d7  jz      short loc_1800271E6
0x1800271d9  mov     rax, [rcx]
0x1800271dc  mov     rax, [rax+8]
0x1800271e0  call    cs:__guard_dispatch_icall_fptr
0x1800271e6  lea     rdx, [rsp+120h+var_F0]
0x1800271eb  lea     rcx, [rbp+20h+var_A0]
0x1800271ef  call    ?GetDbAesKeyStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUDbAesKeyStore@Sqlite@asg@@UIndexEncryptionOptions@234567@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDbAesKeyStore(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexEncryptionOptions)
0x1800271f4  nop
0x1800271f5  mov     rcx, [rbp+20h+var_98]
0x1800271f9  mov     qword ptr [rsp+120h+pExceptionObject], rcx
0x1800271fe  mov     rax, [rbp+20h+var_90]
0x180027202  sub     rax, rcx
0x180027205  mov     qword ptr [rsp+120h+pExceptionObject+8], rax
0x18002720a  mov     dword ptr [rsp+120h+var_C0], 74h ; 't'
0x180027212  mov     dword ptr [rsp+120h+var_C0+4], 11h
0x18002721a  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180027221  mov     qword ptr [rsp+120h+var_C0+8], rax
0x180027226  lea     rax, aVoidCdeclWinrt_5; "void __cdecl winrt::Microsoft::Asg::Sem"...
0x18002722d  mov     [rsp+120h+var_B0], rax
0x180027232  lea     rax, [rbp+20h+Src]
0x180027236  mov     [rbp+20h+var_80], rax
0x18002723a  lea     rax, [rsp+120h+pExceptionObject]
0x18002723f  mov     [rbp+20h+var_78], rax
0x180027243  mov     [rbp+20h+var_70], rsi
0x180027247  mov     [rbp+20h+var_68], rdi
0x18002724b  lea     rdx, [rsp+120h+var_C0]
0x180027250  lea     rcx, [rbp+20h+var_80]
0x180027254  call    ??$SemanticIndexCall@V_lambda_2_@?N@??ResetVectorSpaceIds@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SAXAEBUhstring@winrt@@AEBUIndexEncryptionOptions@56789winrt@@AEBUguid@winrt@@2@Z@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?A_P$$QEAV_lambda_2_@?N@??ResetVectorSpaceIds@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@0123456@SAXAEBUhstring@6@AEBUIndexEncryptionOptions@123456@AEBUguid@6@2@Z@AEBUsource_location@std@@@Z
0x180027259  nop
0x18002725a  lea     rcx, [rbp+20h+var_A0]
0x18002725e  call    ?_Tidy@?$vector@EU?$secure_allocator@E@asg@@@std@@AEAAXXZ; std::vector<uchar,asg::secure_allocator<uchar>>::_Tidy(void)
0x180027263  jmp     loc_180027329
0x180027268  mov     qword ptr [rsp+120h+pExceptionObject], r15
0x18002726d  mov     rcx, [r14]
0x180027270  test    rcx, rcx
0x180027273  jz      short loc_1800272C2
0x180027275  mov     [rsp+120h+var_F0], rcx
0x18002727a  mov     rax, [rcx]
0x18002727d  mov     rax, [rax+8]
0x180027281  call    cs:__guard_dispatch_icall_fptr
0x180027287  lea     rdx, [rsp+120h+var_F0]
0x18002728c  lea     rcx, [rbp+20h+var_A0]
0x180027290  call    ?GetDbAesKeyStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUDbAesKeyStore@Sqlite@asg@@UIndexEncryptionOptions@234567@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDbAesKeyStore(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexEncryptionOptions)
0x180027295  mov     rcx, [rax+8]
0x180027299  mov     qword ptr [rsp+120h+pExceptionObject], rcx
0x18002729e  mov     rax, [rax+10h]
0x1800272a2  sub     rax, rcx
0x1800272a5  mov     qword ptr [rsp+120h+pExceptionObject+8], rax
0x1800272aa  lea     rax, [rsp+120h+pExceptionObject]
0x1800272af  movups  xmm0, xmmword ptr [rax]
0x1800272b2  movups  [rsp+120h+var_C0], xmm0
0x1800272b7  lea     rcx, [rbp+20h+var_A0]
0x1800272bb  call    ?_Tidy@?$vector@EU?$secure_allocator@E@asg@@@std@@AEAAXXZ; std::vector<uchar,asg::secure_allocator<uchar>>::_Tidy(void)
0x1800272c0  jmp     short loc_1800272D9
0x1800272c2  mov     qword ptr [rsp+120h+pExceptionObject], r15
0x1800272c7  mov     qword ptr [rsp+120h+pExceptionObject+8], r15
0x1800272cc  lea     rax, [rsp+120h+pExceptionObject]
0x1800272d1  movups  xmm0, xmmword ptr [rax]
0x1800272d4  movups  [rsp+120h+var_C0], xmm0
0x1800272d9  mov     dword ptr [rsp+120h+pExceptionObject], 85h
0x1800272e1  mov     dword ptr [rsp+120h+pExceptionObject+4], 11h
0x1800272e9  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1800272f0  mov     qword ptr [rsp+120h+pExceptionObject+8], rax
0x1800272f5  lea     rax, aVoidCdeclWinrt_5; "void __cdecl winrt::Microsoft::Asg::Sem"...
0x1800272fc  mov     [rsp+120h+var_D0], rax
0x180027301  lea     rax, [rbp+20h+Src]
0x180027305  mov     [rbp+20h+var_80], rax
0x180027309  lea     rax, [rsp+120h+var_C0]
0x18002730e  mov     [rbp+20h+var_78], rax
0x180027312  mov     [rbp+20h+var_70], rsi
0x180027316  mov     [rbp+20h+var_68], rdi
0x18002731a  lea     rdx, [rsp+120h+pExceptionObject]
0x18002731f  lea     rcx, [rbp+20h+var_80]
0x180027323  call    ??$SemanticIndexCall@V_lambda_2_@?N@??ResetVectorSpaceIds@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SAXAEBUhstring@winrt@@AEBUIndexEncryptionOptions@56789winrt@@AEBUguid@winrt@@2@Z@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?A_P$$QEAV_lambda_2_@?N@??ResetVectorSpaceIds@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@0123456@SAXAEBUhstring@6@AEBUIndexEncryptionOptions@123456@AEBUguid@6@2@Z@AEBUsource_location@std@@@Z
0x180027328  nop
0x180027329  mov     rdx, [rbp+20h+var_40]
0x18002732d  cmp     rdx, 0Fh
0x180027331  jbe     short loc_180027360
0x180027333  inc     rdx
0x180027336  mov     rcx, [rbp+20h+Src]
0x18002733a  mov     rax, rcx
0x18002733d  cmp     rdx, 1000h
0x180027344  jb      short loc_18002735B
0x180027346  add     rdx, 27h ; '''
0x18002734a  mov     rcx, [rcx-8]; Block
0x18002734e  sub     rax, rcx
0x180027351  sub     rax, 8
0x180027355  cmp     rax, 1Fh
0x180027359  ja      short loc_1800273CE
0x18002735b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027360  mov     [rbp+20h+var_48], r15
0x180027364  mov     [rbp+20h+var_40], 0Fh
0x18002736c  mov     byte ptr [rbp+20h+Src], 0
0x180027370  mov     rcx, [rbx+28h]; hObject
0x180027374  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180027378  jz      short loc_180027385
0x18002737a  test    rcx, rcx
0x18002737d  jz      short loc_180027385
0x18002737f  call    cs:__imp_CloseHandle
0x180027385  lea     rcx, [rbx+8]
0x180027389  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x18002738e  mov     edx, 30h ; '0'
0x180027393  mov     rcx, rbx; Block
0x180027396  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002739b  nop
0x18002739c  lea     rcx, [rbp+20h+var_38]
0x1800273a0  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x1800273a5  mov     rcx, [rbp+20h+var_18]
0x1800273a9  xor     rcx, rsp; StackCookie
0x1800273ac  call    __security_check_cookie
0x1800273b1  lea     r11, [rsp+120h+var_10]
0x1800273b9  mov     rbx, [r11+20h]
0x1800273bd  mov     rsi, [r11+30h]
0x1800273c1  mov     rdi, [r11+38h]
0x1800273c5  mov     rsp, r11
0x1800273c8  pop     r15
0x1800273ca  pop     r14
0x1800273cc  pop     rbp
0x1800273cd  retn
0x1800273ce  mov     [rsp+120h+Reserved], r15; Reserved
0x1800273d3  xor     r9d, r9d; LineNo
0x1800273d6  xor     r8d, r8d; FileName
0x1800273d9  xor     edx, edx; FunctionName
0x1800273db  xor     ecx, ecx; Expression
0x1800273dd  call    _invoke_watson
0x1800273e3  mov     dword ptr [rsp+120h+var_C0], 6Ah ; 'j'
0x1800273eb  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1800273f2  mov     qword ptr [rsp+120h+var_C0+8], rax
0x1800273f7  mov     [rsp+120h+var_B0], r15
0x1800273fc  lea     rdx, aCouldNotGetExc; "could not get exclusive access to the d"...
0x180027403  lea     rcx, [rbp+20h+var_A0]; this
0x180027407  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18002740c  mov     edx, 83EBAD1Fh; int
0x180027411  lea     rcx, [rsp+120h+var_F0]; this
0x180027416  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18002741b  lea     r9, [rsp+120h+var_C0]
0x180027420  lea     r8, [rbp+20h+var_A0]
0x180027424  mov     edx, [rax]
0x180027426  lea     rcx, [rsp+120h+pExceptionObject]
0x18002742b  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180027430  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180027437  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x18002743c  call    _CxxThrowException
```
