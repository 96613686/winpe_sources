# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::ResetVectorSpaceIds(winrt::hstring const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexEncryptionOptions const &,winrt::guid const &,winrt::guid const &)

- ea: `0x180050d20`
- end: `0x1800510e2`
- name: `?ResetVectorSpaceIds@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SAXAEBUhstring@8@AEBUIndexEncryptionOptions@345678@AEBUguid@8@2@Z`
- size: `962`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004d060`

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
- `0x180027450`
- `0x18002da90`
- `0x180050d20`
- `0x180067b60`
- `0x180067f30`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206ec0`
- `0x180242120`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18005101f`
- `KERNEL32!CloseHandle` at `0x18005101f`

## string_xrefs

- `0x18005109c`: `could not get exclusive access to the database lock file`
- `0x180050eba`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x180050f89`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x18005108b`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x180050ec6`: `void __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiF`
- `0x180050f95`: `void __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiF`

## pseudocode

```c
__int64 __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::ResetVectorSpaceIds(
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
            "bility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implem"
            "entation::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Text"
            "EmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::Te"
            "xtEmbeddingsGenerator>::ResetVectorSpaceIds(const struct winrt::hstring &,const struct winrt::Microsoft::Asg"
            "::SemanticIndex::AiFabric::Compatibility::IndexEncryptionOptions &,const struct winrt::guid &,const struct winrt::guid &)";
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
            "bility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implem"
            "entation::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Text"
            "EmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::Te"
            "xtEmbeddingsGenerator>::ResetVectorSpaceIds(const struct winrt::hstring &,const struct winrt::Microsoft::Asg"
            "::SemanticIndex::AiFabric::Compatibility::IndexEncryptionOptions &,const struct winrt::guid &,const struct winrt::guid &)";
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
0x180050d20  mov     [rsp-8+arg_0], rbx
0x180050d25  mov     [rsp-8+arg_10], rsi
0x180050d2a  mov     [rsp-8+arg_18], rdi
0x180050d2f  push    rbp
0x180050d30  push    r14
0x180050d32  push    r15
0x180050d34  lea     rbp, [rsp-10h]
0x180050d39  sub     rsp, 110h
0x180050d40  mov     rax, cs:__security_cookie
0x180050d47  xor     rax, rsp
0x180050d4a  mov     [rbp+20h+var_18], rax
0x180050d4e  mov     rdi, r9
0x180050d51  mov     rsi, r8
0x180050d54  mov     r14, rdx
0x180050d57  xor     r15d, r15d
0x180050d5a  xorps   xmm0, xmm0
0x180050d5d  movq    rax, xmm0
0x180050d62  cmp     [r8], rax
0x180050d65  jnz     short loc_180050D98
0x180050d67  psrldq  xmm0, 8
0x180050d6c  movq    rax, xmm0
0x180050d71  cmp     [r8+8], rax
0x180050d75  jnz     short loc_180050D98
0x180050d77  xorps   xmm0, xmm0
0x180050d7a  movq    rax, xmm0
0x180050d7f  cmp     [r9], rax
0x180050d82  jnz     short loc_180050D98
0x180050d84  psrldq  xmm0, 8
0x180050d89  movq    rax, xmm0
0x180050d8e  cmp     [r9+8], rax
0x180050d92  jz      loc_180051045
0x180050d98  mov     rdx, [rcx]
0x180050d9b  test    rdx, rdx
0x180050d9e  jz      short loc_180050DA6
0x180050da0  mov     rdx, [rdx+10h]
0x180050da4  jmp     short loc_180050DAD
0x180050da6  lea     rdx, String
0x180050dad  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180050db4  inc     r8
0x180050db7  cmp     [rdx+r8*2], r15w
0x180050dbc  jnz     short loc_180050DB4
0x180050dbe  xorps   xmm0, xmm0
0x180050dc1  movups  [rsp+120h+var_C0], xmm0
0x180050dc6  mov     [rsp+120h+var_B0], r15
0x180050dcb  mov     [rsp+120h+var_A8], r15
0x180050dd0  lea     rcx, [rsp+120h+var_C0]
0x180050dd5  call    ??$_Construct@$00PEB_S@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXQEB_S_K@Z; std::basic_string<char16_t>::_Construct<1,char16_t const *>(char16_t const * const,unsigned __int64)
0x180050dda  lea     rdx, [rsp+120h+var_C0]
0x180050ddf  lea     rcx, [rbp+20h+var_38]
0x180050de3  call    ?AppendDbExtensionIfRequired@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AVpath@filesystem@std@@V89std@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::AppendDbExtensionIfRequired(std::filesystem::path)
0x180050de8  nop
0x180050de9  mov     ecx, 30h ; '0'; Size
0x180050dee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050df3  mov     rbx, rax
0x180050df6  mov     [rsp+120h+var_F0], rax
0x180050dfb  lea     rdx, [rbp+20h+var_38]
0x180050dff  lea     rcx, [rbp+20h+var_A0]
0x180050e03  call    ??0?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@QEAA@AEBV01@@Z; std::basic_string<char16_t>::basic_string<char16_t>(std::basic_string<char16_t> const &)
0x180050e08  mov     r8b, 1
0x180050e0b  lea     rdx, [rbp+20h+var_A0]
0x180050e0f  mov     rcx, rbx
0x180050e12  call    ??0IndexLockFile@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@Vpath@filesystem@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexLockFile::IndexLockFile(std::filesystem::path,bool)
0x180050e17  mov     rbx, rax
0x180050e1a  mov     [rbp+20h+var_60], rax
0x180050e1e  cmp     qword ptr [rax+28h], 0FFFFFFFFFFFFFFFFh
0x180050e23  jz      loc_180051083
0x180050e29  lea     rax, [rbp+20h+var_38]
0x180050e2d  cmp     [rbp+20h+var_20], 7
0x180050e32  cmova   rax, [rbp+20h+var_38]
0x180050e37  mov     qword ptr [rsp+120h+pExceptionObject], rax
0x180050e3c  mov     rax, [rbp+20h+var_28]
0x180050e40  mov     qword ptr [rsp+120h+pExceptionObject+8], rax
0x180050e45  movaps  xmm0, [rsp+120h+pExceptionObject]
0x180050e4a  movdqa  [rsp+120h+var_C0], xmm0
0x180050e50  lea     r8, [rsp+120h+var_C0]
0x180050e55  lea     rcx, [rbp+20h+Src]; Src
0x180050e59  call    ??$_Convert_wide_to_narrow@U?$char_traits@_Q@std@@V?$allocator@_Q@2@@std@@YA?AV?$basic_string@_QU?$char_traits@_Q@std@@V?$allocator@_Q@2@@0@W4__std_code_page@@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@AEBV?$allocator@_Q@0@@Z; std::_Convert_wide_to_narrow<std::char_traits<char8_t>>(__std_code_page,std::wstring_view,std::allocator<char8_t> const &)
0x180050e5e  nop
0x180050e5f  call    ??$IsFeatureEnabled@V?$Feature@U__WilFeatureTraits_Feature_57460691@@@wil@@@asg@@YA_NXZ; asg::IsFeatureEnabled<wil::Feature<__WilFeatureTraits_Feature_57460691>>(void)
0x180050e64  test    al, al
0x180050e66  jz      loc_180050F08
0x180050e6c  mov     rcx, [r14]
0x180050e6f  mov     [rsp+120h+var_F0], rcx
0x180050e74  test    rcx, rcx
0x180050e77  jz      short loc_180050E86
0x180050e79  mov     rax, [rcx]
0x180050e7c  mov     rax, [rax+8]
0x180050e80  call    cs:__guard_dispatch_icall_fptr
0x180050e86  lea     rdx, [rsp+120h+var_F0]
0x180050e8b  lea     rcx, [rbp+20h+var_A0]
0x180050e8f  call    ?GetDbAesKeyStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUDbAesKeyStore@Sqlite@asg@@UIndexEncryptionOptions@234567@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDbAesKeyStore(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexEncryptionOptions)
0x180050e94  nop
0x180050e95  mov     rcx, [rbp+20h+var_98]
0x180050e99  mov     qword ptr [rsp+120h+pExceptionObject], rcx
0x180050e9e  mov     rax, [rbp+20h+var_90]
0x180050ea2  sub     rax, rcx
0x180050ea5  mov     qword ptr [rsp+120h+pExceptionObject+8], rax
0x180050eaa  mov     dword ptr [rsp+120h+var_C0], 74h ; 't'
0x180050eb2  mov     dword ptr [rsp+120h+var_C0+4], 11h
0x180050eba  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180050ec1  mov     qword ptr [rsp+120h+var_C0+8], rax
0x180050ec6  lea     rax, aVoidCdeclWinrt_10; "void __cdecl winrt::Microsoft::Asg::Sem"...
0x180050ecd  mov     [rsp+120h+var_B0], rax
0x180050ed2  lea     rax, [rbp+20h+Src]
0x180050ed6  mov     [rbp+20h+var_80], rax
0x180050eda  lea     rax, [rsp+120h+pExceptionObject]
0x180050edf  mov     [rbp+20h+var_78], rax
0x180050ee3  mov     [rbp+20h+var_70], rsi
0x180050ee7  mov     [rbp+20h+var_68], rdi
0x180050eeb  lea     rdx, [rsp+120h+var_C0]
0x180050ef0  lea     rcx, [rbp+20h+var_80]
0x180050ef4  call    ??$SemanticIndexCall@V_lambda_2_@?N@??ResetVectorSpaceIds@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SAXAEBUhstring@winrt@@AEBUIndexEncryptionOptions@56789winrt@@AEBUguid@winrt@@2@Z@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?A_P$$QEAV_lambda_2_@?N@??ResetVectorSpaceIds@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@0123456@SAXAEBUhstring@6@AEBUIndexEncryptionOptions@123456@AEBUguid@6@2@Z@AEBUsource_location@std@@@Z
0x180050ef9  nop
0x180050efa  lea     rcx, [rbp+20h+var_A0]
0x180050efe  call    ?_Tidy@?$vector@EU?$secure_allocator@E@asg@@@std@@AEAAXXZ; std::vector<uchar,asg::secure_allocator<uchar>>::_Tidy(void)
0x180050f03  jmp     loc_180050FC9
0x180050f08  mov     qword ptr [rsp+120h+pExceptionObject], r15
0x180050f0d  mov     rcx, [r14]
0x180050f10  test    rcx, rcx
0x180050f13  jz      short loc_180050F62
0x180050f15  mov     [rsp+120h+var_F0], rcx
0x180050f1a  mov     rax, [rcx]
0x180050f1d  mov     rax, [rax+8]
0x180050f21  call    cs:__guard_dispatch_icall_fptr
0x180050f27  lea     rdx, [rsp+120h+var_F0]
0x180050f2c  lea     rcx, [rbp+20h+var_A0]
0x180050f30  call    ?GetDbAesKeyStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUDbAesKeyStore@Sqlite@asg@@UIndexEncryptionOptions@234567@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDbAesKeyStore(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexEncryptionOptions)
0x180050f35  mov     rcx, [rax+8]
0x180050f39  mov     qword ptr [rsp+120h+pExceptionObject], rcx
0x180050f3e  mov     rax, [rax+10h]
0x180050f42  sub     rax, rcx
0x180050f45  mov     qword ptr [rsp+120h+pExceptionObject+8], rax
0x180050f4a  lea     rax, [rsp+120h+pExceptionObject]
0x180050f4f  movups  xmm0, xmmword ptr [rax]
0x180050f52  movups  [rsp+120h+var_C0], xmm0
0x180050f57  lea     rcx, [rbp+20h+var_A0]
0x180050f5b  call    ?_Tidy@?$vector@EU?$secure_allocator@E@asg@@@std@@AEAAXXZ; std::vector<uchar,asg::secure_allocator<uchar>>::_Tidy(void)
0x180050f60  jmp     short loc_180050F79
0x180050f62  mov     qword ptr [rsp+120h+pExceptionObject], r15
0x180050f67  mov     qword ptr [rsp+120h+pExceptionObject+8], r15
0x180050f6c  lea     rax, [rsp+120h+pExceptionObject]
0x180050f71  movups  xmm0, xmmword ptr [rax]
0x180050f74  movups  [rsp+120h+var_C0], xmm0
0x180050f79  mov     dword ptr [rsp+120h+pExceptionObject], 85h
0x180050f81  mov     dword ptr [rsp+120h+pExceptionObject+4], 11h
0x180050f89  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180050f90  mov     qword ptr [rsp+120h+pExceptionObject+8], rax
0x180050f95  lea     rax, aVoidCdeclWinrt_10; "void __cdecl winrt::Microsoft::Asg::Sem"...
0x180050f9c  mov     [rsp+120h+var_D0], rax
0x180050fa1  lea     rax, [rbp+20h+Src]
0x180050fa5  mov     [rbp+20h+var_80], rax
0x180050fa9  lea     rax, [rsp+120h+var_C0]
0x180050fae  mov     [rbp+20h+var_78], rax
0x180050fb2  mov     [rbp+20h+var_70], rsi
0x180050fb6  mov     [rbp+20h+var_68], rdi
0x180050fba  lea     rdx, [rsp+120h+pExceptionObject]
0x180050fbf  lea     rcx, [rbp+20h+var_80]
0x180050fc3  call    ??$SemanticIndexCall@V_lambda_2_@?N@??ResetVectorSpaceIds@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SAXAEBUhstring@winrt@@AEBUIndexEncryptionOptions@56789winrt@@AEBUguid@winrt@@2@Z@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?A_P$$QEAV_lambda_2_@?N@??ResetVectorSpaceIds@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@0123456@SAXAEBUhstring@6@AEBUIndexEncryptionOptions@123456@AEBUguid@6@2@Z@AEBUsource_location@std@@@Z
0x180050fc8  nop
0x180050fc9  mov     rdx, [rbp+20h+var_40]
0x180050fcd  cmp     rdx, 0Fh
0x180050fd1  jbe     short loc_180051000
0x180050fd3  inc     rdx
0x180050fd6  mov     rcx, [rbp+20h+Src]
0x180050fda  mov     rax, rcx
0x180050fdd  cmp     rdx, 1000h
0x180050fe4  jb      short loc_180050FFB
0x180050fe6  add     rdx, 27h ; '''
0x180050fea  mov     rcx, [rcx-8]; Block
0x180050fee  sub     rax, rcx
0x180050ff1  sub     rax, 8
0x180050ff5  cmp     rax, 1Fh
0x180050ff9  ja      short loc_18005106E
0x180050ffb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180051000  mov     [rbp+20h+var_48], r15
0x180051004  mov     [rbp+20h+var_40], 0Fh
0x18005100c  mov     byte ptr [rbp+20h+Src], 0
0x180051010  mov     rcx, [rbx+28h]; hObject
0x180051014  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180051018  jz      short loc_180051025
0x18005101a  test    rcx, rcx
0x18005101d  jz      short loc_180051025
0x18005101f  call    cs:__imp_CloseHandle
0x180051025  lea     rcx, [rbx+8]
0x180051029  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x18005102e  mov     edx, 30h ; '0'
0x180051033  mov     rcx, rbx; Block
0x180051036  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18005103b  nop
0x18005103c  lea     rcx, [rbp+20h+var_38]
0x180051040  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x180051045  mov     rcx, [rbp+20h+var_18]
0x180051049  xor     rcx, rsp; StackCookie
0x18005104c  call    __security_check_cookie
0x180051051  lea     r11, [rsp+120h+var_10]
0x180051059  mov     rbx, [r11+20h]
0x18005105d  mov     rsi, [r11+30h]
0x180051061  mov     rdi, [r11+38h]
0x180051065  mov     rsp, r11
0x180051068  pop     r15
0x18005106a  pop     r14
0x18005106c  pop     rbp
0x18005106d  retn
0x18005106e  mov     [rsp+120h+Reserved], r15; Reserved
0x180051073  xor     r9d, r9d; LineNo
0x180051076  xor     r8d, r8d; FileName
0x180051079  xor     edx, edx; FunctionName
0x18005107b  xor     ecx, ecx; Expression
0x18005107d  call    _invoke_watson
0x180051083  mov     dword ptr [rsp+120h+var_C0], 6Ah ; 'j'
0x18005108b  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180051092  mov     qword ptr [rsp+120h+var_C0+8], rax
0x180051097  mov     [rsp+120h+var_B0], r15
0x18005109c  lea     rdx, aCouldNotGetExc; "could not get exclusive access to the d"...
0x1800510a3  lea     rcx, [rbp+20h+var_A0]; this
0x1800510a7  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x1800510ac  mov     edx, 83EBAD1Fh; int
0x1800510b1  lea     rcx, [rsp+120h+var_F0]; this
0x1800510b6  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x1800510bb  lea     r9, [rsp+120h+var_C0]
0x1800510c0  lea     r8, [rbp+20h+var_A0]
0x1800510c4  mov     edx, [rax]
0x1800510c6  lea     rcx, [rsp+120h+pExceptionObject]
0x1800510cb  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x1800510d0  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x1800510d7  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x1800510dc  call    _CxxThrowException
```
