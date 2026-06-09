# _asg::SemanticIndex::ApplicationDb::InitializeDatabaseFromScript_::_57_::_lambda_1_::operator()

- ea: `0x18019ddb0`
- end: `0x18019e0ee`
- name: `_asg::SemanticIndex::ApplicationDb::InitializeDatabaseFromScript_::_57_::_lambda_1_::operator()`
- size: `830`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1801a21c0`

## callees

- `0x180007de0`
- `0x18000cc40`
- `0x180078ed0`
- `0x18007b3e0`
- `0x18019ddb0`
- `0x1801a51d0`

## string_xrefs

- `0x18019df31`: `Quantization parameters in the database don't match those in the registry.`
- `0x18019dff6`: `Quantization parameters in the database don't match those in the registry.`
- `0x18019e0a0`: `auto __cdecl asg::SemanticIndex::ApplicationDb::InitializeDatabaseFromScript::<lambda_1>::operator ()(enum asg::SemanticRegistry::EmbeddingElementType) const`
- `0x18019e0ce`: `auto __cdecl asg::SemanticIndex::ApplicationDb::InitializeDatabaseFromScript::<lambda_1>::operator ()(enum asg::SemanticRegistry::EmbeddingElementType) const`

## pseudocode

```c
__int64 __fastcall asg::SemanticIndex::ApplicationDb::InitializeDatabaseFromScript_::_57_::_lambda_1_::operator()(
        __int64 a1,
        unsigned int a2)
{
  _QWORD *v4; // rdx
  unsigned __int64 v5; // rcx
  bool v6; // dl
  bool v7; // r9
  __int64 v8; // r8
  unsigned __int64 v9; // rcx
  bool v10; // si
  bool v11; // al
  __int64 result; // rax
  bool *v13; // rcx
  bool v14; // al
  __int64 v15; // rax
  __int64 v16; // r9
  char v17; // cl
  bool *v18; // rcx
  bool v19; // al
  __int64 v20; // rax
  __int64 v21; // r9
  char v22; // cl
  __int128 v23; // [rsp+30h] [rbp-29h] BYREF
  __int128 v24; // [rsp+40h] [rbp-19h]
  __int128 v25; // [rsp+50h] [rbp-9h] BYREF
  __int128 v26; // [rsp+60h] [rbp+7h]
  _BYTE v27[32]; // [rsp+70h] [rbp+17h] BYREF
  char v28; // [rsp+90h] [rbp+37h]
  __int64 v29; // [rsp+C0h] [rbp+67h]

  v4 = *(_QWORD **)a1;
  v5 = **(_QWORD **)a1 - `asg::EmptyGuid'::`2'::empty;
  if ( !v5 )
    v5 = v4[1] - _mm_srli_si128((__m128i)`asg::EmptyGuid'::`2'::empty, 8).m128i_u64[0];
  v6 = v5 && *((_DWORD *)v4 + 6) != a2;
  v7 = *(_BYTE *)(*(_QWORD *)(a1 + 8) + 8LL) || *(_BYTE *)(*(_QWORD *)(a1 + 16) + 8LL);
  v8 = *(_QWORD *)(a1 + 24);
  v9 = *(_QWORD *)v8 - `asg::EmptyGuid'::`2'::empty;
  if ( *(_QWORD *)v8 == (_QWORD)`asg::EmptyGuid'::`2'::empty )
    v9 = *(_QWORD *)(v8 + 8) - _mm_srli_si128((__m128i)`asg::EmptyGuid'::`2'::empty, 8).m128i_u64[0];
  v10 = v9 && *(_DWORD *)(v8 + 24) != a2;
  v11 = *(_BYTE *)(*(_QWORD *)(a1 + 32) + 8LL) || *(_BYTE *)(*(_QWORD *)(a1 + 40) + 8LL);
  if ( (!v6 || v7) && (!v10 || v11) )
  {
    if ( v6 )
    {
      v13 = *(bool **)(a1 + 56);
      v14 = *v13 || !a2;
      *v13 = v14;
      v15 = *(_QWORD *)(a1 + 8);
      v16 = *(_QWORD *)(a1 + 16);
      v17 = *(_BYTE *)(v16 + 8);
      if ( *(_BYTE *)(v15 + 8) )
      {
        if ( v17 && (*(float *)v16 != *(float *)v15 || *(float *)(v16 + 4) != *(float *)(v15 + 4)) )
        {
          BYTE8(v26) = 0;
          v23 = v25;
          v24 = v26;
          asg::details::_asg_Log<std::integral_constant<bool,0>>(
            v27,
            &v23,
            3,
            L"Quantization parameters in the database don't match those in the registry.");
          if ( v28 )
            std::basic_string<char16_t>::_Tidy_deallocate(v27);
        }
        if ( !*(_BYTE *)(*(_QWORD *)(a1 + 8) + 8LL) )
          goto LABEL_59;
      }
      else if ( !v17 )
      {
        *(_QWORD *)&v23 = 0x210000045DLL;
        *((_QWORD *)&v23 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\ApplicationDb.cpp";
        *(_QWORD *)&v24 = "auto __cdecl asg::SemanticIndex::ApplicationDb::InitializeDatabaseFromScript::<lambda_1>::oper"
                          "ator ()(enum asg::SemanticRegistry::EmbeddingElementType) const";
        asg::details::AsgAssertFail(&v23);
      }
      asg::SemanticIndex::ApplicationDb::TransformToElementType(**(_QWORD **)(a1 + 64), 0, a2);
    }
    if ( !v10 )
    {
LABEL_56:
      LODWORD(v29) = a2;
      BYTE4(v29) = 1;
      result = v29;
      **(_QWORD **)(a1 + 48) = v29;
      return result;
    }
    v18 = *(bool **)(a1 + 56);
    v19 = *v18 || !a2;
    *v18 = v19;
    v20 = *(_QWORD *)(a1 + 32);
    v21 = *(_QWORD *)(a1 + 40);
    v22 = *(_BYTE *)(v21 + 8);
    if ( !*(_BYTE *)(v20 + 8) )
    {
      if ( !v22 )
      {
        *(_QWORD *)&v23 = 0x210000047ELL;
        *((_QWORD *)&v23 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\ApplicationDb.cpp";
        *(_QWORD *)&v24 = "auto __cdecl asg::SemanticIndex::ApplicationDb::InitializeDatabaseFromScript::<lambda_1>::oper"
                          "ator ()(enum asg::SemanticRegistry::EmbeddingElementType) const";
        asg::details::AsgAssertFail(&v23);
      }
      goto LABEL_55;
    }
    if ( v22 && (*(float *)v21 != *(float *)v20 || *(float *)(v21 + 4) != *(float *)(v20 + 4)) )
    {
      BYTE8(v26) = 0;
      v23 = v25;
      v24 = v26;
      asg::details::_asg_Log<std::integral_constant<bool,0>>(
        v27,
        &v23,
        3,
        L"Quantization parameters in the database don't match those in the registry.");
      if ( v28 )
        std::basic_string<char16_t>::_Tidy_deallocate(v27);
    }
    if ( *(_BYTE *)(*(_QWORD *)(a1 + 32) + 8LL) )
    {
LABEL_55:
      asg::SemanticIndex::ApplicationDb::TransformToElementType(**(_QWORD **)(a1 + 64), 1, a2);
      goto LABEL_56;
    }
LABEL_59:
    std::_Throw_bad_optional_access();
  }
  BYTE8(v24) = 0;
  v25 = v23;
  v26 = v24;
  asg::details::_asg_Log<std::integral_constant<bool,0>>(
    v27,
    &v25,
    3,
    L"Cannot perform element type conversion: quantization parameters unknown");
  if ( v28 )
    std::basic_string<char16_t>::_Tidy_deallocate(v27);
  result = *(_QWORD *)(a1 + 48);
  *(_BYTE *)(result + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x18019ddb0  mov     [rsp-8+arg_10], rbx
0x18019ddb5  mov     [rsp-8+arg_18], rdi
0x18019ddba  push    rbp
0x18019ddbb  lea     rbp, [rsp-57h]
0x18019ddc0  sub     rsp, 0B0h
0x18019ddc7  movups  xmm1, cs:?empty@?1??EmptyGuid@asg@@YA?AUGuid@2@XZ@4U32@B; asg::Guid const `asg::EmptyGuid(void)'::`2'::empty
0x18019ddce  mov     rbx, rcx
0x18019ddd1  mov     edi, edx
0x18019ddd3  mov     rdx, [rcx]
0x18019ddd6  movq    rax, xmm1
0x18019dddb  mov     rcx, [rdx]
0x18019ddde  sub     rcx, rax
0x18019dde1  jnz     short loc_18019DDF8
0x18019dde3  mov     rcx, [rdx+8]
0x18019dde7  movdqa  xmm0, xmm1
0x18019ddeb  psrldq  xmm0, 8
0x18019ddf0  movq    rax, xmm0
0x18019ddf5  sub     rcx, rax
0x18019ddf8  test    rcx, rcx
0x18019ddfb  jz      short loc_18019DE06
0x18019ddfd  cmp     [rdx+18h], edi
0x18019de00  jz      short loc_18019DE06
0x18019de02  mov     dl, 1
0x18019de04  jmp     short loc_18019DE08
0x18019de06  xor     dl, dl
0x18019de08  mov     rax, [rbx+8]
0x18019de0c  cmp     byte ptr [rax+8], 0
0x18019de10  jnz     short loc_18019DE21
0x18019de12  mov     rax, [rbx+10h]
0x18019de16  cmp     byte ptr [rax+8], 0
0x18019de1a  jnz     short loc_18019DE21
0x18019de1c  xor     r9b, r9b
0x18019de1f  jmp     short loc_18019DE24
0x18019de21  mov     r9b, 1
0x18019de24  mov     r8, [rbx+18h]
0x18019de28  movq    rax, xmm1
0x18019de2d  mov     rcx, [r8]
0x18019de30  sub     rcx, rax
0x18019de33  jnz     short loc_18019DE46
0x18019de35  mov     rcx, [r8+8]
0x18019de39  psrldq  xmm1, 8
0x18019de3e  movq    rax, xmm1
0x18019de43  sub     rcx, rax
0x18019de46  mov     [rsp+0B0h+arg_8], rsi
0x18019de4e  test    rcx, rcx
0x18019de51  jz      short loc_18019DE5E
0x18019de53  cmp     [r8+18h], edi
0x18019de57  jz      short loc_18019DE5E
0x18019de59  mov     sil, 1
0x18019de5c  jmp     short loc_18019DE61
0x18019de5e  xor     sil, sil
0x18019de61  mov     rax, [rbx+20h]
0x18019de65  cmp     byte ptr [rax+8], 0
0x18019de69  jnz     short loc_18019DE79
0x18019de6b  mov     rax, [rbx+28h]
0x18019de6f  cmp     byte ptr [rax+8], 0
0x18019de73  jnz     short loc_18019DE79
0x18019de75  xor     al, al
0x18019de77  jmp     short loc_18019DE7B
0x18019de79  mov     al, 1
0x18019de7b  test    dl, dl
0x18019de7d  jz      short loc_18019DE84
0x18019de7f  test    r9b, r9b
0x18019de82  jz      short loc_18019DE8D
0x18019de84  test    sil, sil
0x18019de87  jz      short loc_18019DED7
0x18019de89  test    al, al
0x18019de8b  jnz     short loc_18019DED7
0x18019de8d  movups  xmm0, [rbp+57h+var_80]
0x18019de91  mov     byte ptr [rbp+57h+var_70+8], 0
0x18019de95  lea     r9, aCannotPerformE; "Cannot perform element type conversion:"...
0x18019de9c  movups  xmm1, [rbp+57h+var_70]
0x18019dea0  mov     r8d, 3
0x18019dea6  lea     rdx, [rbp+57h+var_60]
0x18019deaa  lea     rcx, [rbp+57h+var_40]
0x18019deae  movaps  [rbp+57h+var_60], xmm0
0x18019deb2  movaps  [rbp+57h+var_50], xmm1
0x18019deb6  call    ??$_asg_Log@U?$integral_constant@_N$0A@@std@@@details@asg@@YA?AULogStringView@1@V?$optional@Usource_location@std@@@std@@W4LogLevel@1@PEB_SZZ; asg::details::_asg_Log<std::integral_constant<bool,0>>(std::optional<std::source_location>,asg::LogLevel,char16_t const *,...)
0x18019debb  cmp     [rbp+57h+var_20], 0
0x18019debf  jz      short loc_18019DECA
0x18019dec1  lea     rcx, [rbp+57h+var_40]
0x18019dec5  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x18019deca  mov     rax, [rbx+30h]
0x18019dece  mov     byte ptr [rax+4], 0
0x18019ded2  jmp     loc_18019E065
0x18019ded7  test    dl, dl
0x18019ded9  jz      loc_18019DF8E
0x18019dedf  mov     rcx, [rbx+38h]
0x18019dee3  cmp     byte ptr [rcx], 0
0x18019dee6  jnz     short loc_18019DEF0
0x18019dee8  test    edi, edi
0x18019deea  jz      short loc_18019DEF0
0x18019deec  xor     al, al
0x18019deee  jmp     short loc_18019DEF2
0x18019def0  mov     al, 1
0x18019def2  mov     [rcx], al
0x18019def4  mov     rax, [rbx+8]
0x18019def8  mov     r9, [rbx+10h]
0x18019defc  cmp     byte ptr [rax+8], 0
0x18019df00  movzx   ecx, byte ptr [r9+8]
0x18019df05  jz      loc_18019DFA8
0x18019df0b  test    cl, cl
0x18019df0d  jz      short loc_18019DF66
0x18019df0f  movss   xmm0, dword ptr [r9]
0x18019df14  ucomiss xmm0, dword ptr [rax]
0x18019df17  jp      short loc_18019DF29
0x18019df19  jnz     short loc_18019DF29
0x18019df1b  movss   xmm0, dword ptr [r9+4]
0x18019df21  ucomiss xmm0, dword ptr [rax+4]
0x18019df25  jp      short loc_18019DF29
0x18019df27  jz      short loc_18019DF66
0x18019df29  movups  xmm0, [rbp+57h+var_60]
0x18019df2d  mov     byte ptr [rbp+57h+var_50+8], 0
0x18019df31  lea     r9, aQuantizationPa_0; "Quantization parameters in the database"...
0x18019df38  movups  xmm1, [rbp+57h+var_50]
0x18019df3c  mov     r8d, 3
0x18019df42  lea     rdx, [rbp+57h+var_80]
0x18019df46  lea     rcx, [rbp+57h+var_40]
0x18019df4a  movaps  [rbp+57h+var_80], xmm0
0x18019df4e  movaps  [rbp+57h+var_70], xmm1
0x18019df52  call    ??$_asg_Log@U?$integral_constant@_N$0A@@std@@@details@asg@@YA?AULogStringView@1@V?$optional@Usource_location@std@@@std@@W4LogLevel@1@PEB_SZZ; asg::details::_asg_Log<std::integral_constant<bool,0>>(std::optional<std::source_location>,asg::LogLevel,char16_t const *,...)
0x18019df57  cmp     [rbp+57h+var_20], 0
0x18019df5b  jz      short loc_18019DF66
0x18019df5d  lea     rcx, [rbp+57h+var_40]
0x18019df61  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x18019df66  mov     r9, [rbx+8]
0x18019df6a  mov     rax, [rbx]
0x18019df6d  cmp     byte ptr [r9+8], 0
0x18019df72  jz      loc_18019E08C
0x18019df78  mov     rcx, [rbx+40h]
0x18019df7c  mov     r8d, edi
0x18019df7f  xor     edx, edx
0x18019df81  mov     [rsp+0B0h+var_90], rax
0x18019df86  mov     rcx, [rcx]
0x18019df89  call    ?TransformToElementType@ApplicationDb@SemanticIndex@asg@@SAXAEAVDbTransaction@Sqlite@3@W4TableGroupId@23@W4EmbeddingElementType@SemanticRegistry@3@AEBUEmbeddingQuantizationParameters@83@AEBUEmbeddingInfo@83@@Z; asg::SemanticIndex::ApplicationDb::TransformToElementType(asg::Sqlite::DbTransaction &,asg::SemanticIndex::TableGroupId,asg::SemanticRegistry::EmbeddingElementType,asg::SemanticRegistry::EmbeddingQuantizationParameters const &,asg::SemanticRegistry::EmbeddingInfo const &)
0x18019df8e  test    sil, sil
0x18019df91  jz      loc_18019E053
0x18019df97  mov     rcx, [rbx+38h]
0x18019df9b  cmp     byte ptr [rcx], 0
0x18019df9e  jnz     short loc_18019DFB5
0x18019dfa0  test    edi, edi
0x18019dfa2  jz      short loc_18019DFB5
0x18019dfa4  xor     al, al
0x18019dfa6  jmp     short loc_18019DFB7
0x18019dfa8  test    cl, cl
0x18019dfaa  jz      loc_18019E0C0
0x18019dfb0  mov     rax, [rbx]
0x18019dfb3  jmp     short loc_18019DF78
0x18019dfb5  mov     al, 1
0x18019dfb7  mov     [rcx], al
0x18019dfb9  mov     rax, [rbx+20h]
0x18019dfbd  mov     r9, [rbx+28h]
0x18019dfc1  cmp     byte ptr [rax+8], 0
0x18019dfc5  movzx   ecx, byte ptr [r9+8]
0x18019dfca  jz      loc_18019E082
0x18019dfd0  test    cl, cl
0x18019dfd2  jz      short loc_18019E02B
0x18019dfd4  movss   xmm0, dword ptr [r9]
0x18019dfd9  ucomiss xmm0, dword ptr [rax]
0x18019dfdc  jp      short loc_18019DFEE
0x18019dfde  jnz     short loc_18019DFEE
0x18019dfe0  movss   xmm0, dword ptr [r9+4]
0x18019dfe6  ucomiss xmm0, dword ptr [rax+4]
0x18019dfea  jp      short loc_18019DFEE
0x18019dfec  jz      short loc_18019E02B
0x18019dfee  movups  xmm0, [rbp+57h+var_60]
0x18019dff2  mov     byte ptr [rbp+57h+var_50+8], 0
0x18019dff6  lea     r9, aQuantizationPa_0; "Quantization parameters in the database"...
0x18019dffd  movups  xmm1, [rbp+57h+var_50]
0x18019e001  mov     r8d, 3
0x18019e007  lea     rdx, [rbp+57h+var_80]
0x18019e00b  lea     rcx, [rbp+57h+var_40]
0x18019e00f  movaps  [rbp+57h+var_80], xmm0
0x18019e013  movaps  [rbp+57h+var_70], xmm1
0x18019e017  call    ??$_asg_Log@U?$integral_constant@_N$0A@@std@@@details@asg@@YA?AULogStringView@1@V?$optional@Usource_location@std@@@std@@W4LogLevel@1@PEB_SZZ; asg::details::_asg_Log<std::integral_constant<bool,0>>(std::optional<std::source_location>,asg::LogLevel,char16_t const *,...)
0x18019e01c  cmp     [rbp+57h+var_20], 0
0x18019e020  jz      short loc_18019E02B
0x18019e022  lea     rcx, [rbp+57h+var_40]
0x18019e026  call    ?_Tidy_deallocate@?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEAAXXZ; std::basic_string<char16_t>::_Tidy_deallocate(void)
0x18019e02b  mov     r9, [rbx+20h]
0x18019e02f  mov     rax, [rbx+18h]
0x18019e033  cmp     byte ptr [r9+8], 0
0x18019e038  jz      short loc_18019E08C
0x18019e03a  mov     rcx, [rbx+40h]
0x18019e03e  mov     r8d, edi
0x18019e041  mov     edx, 1
0x18019e046  mov     [rsp+0B0h+var_90], rax
0x18019e04b  mov     rcx, [rcx]
0x18019e04e  call    ?TransformToElementType@ApplicationDb@SemanticIndex@asg@@SAXAEAVDbTransaction@Sqlite@3@W4TableGroupId@23@W4EmbeddingElementType@SemanticRegistry@3@AEBUEmbeddingQuantizationParameters@83@AEBUEmbeddingInfo@83@@Z; asg::SemanticIndex::ApplicationDb::TransformToElementType(asg::Sqlite::DbTransaction &,asg::SemanticIndex::TableGroupId,asg::SemanticRegistry::EmbeddingElementType,asg::SemanticRegistry::EmbeddingQuantizationParameters const &,asg::SemanticRegistry::EmbeddingInfo const &)
0x18019e053  mov     rcx, [rbx+30h]
0x18019e057  mov     dword ptr [rbp+57h+arg_0], edi
0x18019e05a  mov     byte ptr [rbp+57h+arg_0+4], 1
0x18019e05e  mov     rax, [rbp+57h+arg_0]
0x18019e062  mov     [rcx], rax
0x18019e065  mov     rsi, [rsp+0B0h+arg_8]
0x18019e06d  lea     r11, [rsp+0B0h+var_s0]
0x18019e075  mov     rbx, [r11+20h]
0x18019e079  mov     rdi, [r11+28h]
0x18019e07d  mov     rsp, r11
0x18019e080  pop     rbp
0x18019e081  retn
0x18019e082  test    cl, cl
0x18019e084  jz      short loc_18019E092
0x18019e086  mov     rax, [rbx+18h]
0x18019e08a  jmp     short loc_18019E03A
0x18019e08c  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x18019e092  lea     rax, aCW1SSrcSemanti_31; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18019e099  mov     dword ptr [rbp+57h+var_80], 47Eh
0x18019e0a0  lea     rdx, aAutoCdeclAsgSe_5; "auto __cdecl asg::SemanticIndex::Applic"...
0x18019e0a7  mov     qword ptr [rbp+57h+var_80+8], rax
0x18019e0ab  lea     rcx, [rbp+57h+var_80]
0x18019e0af  mov     qword ptr [rbp+57h+var_70], rdx
0x18019e0b3  mov     dword ptr [rbp+57h+var_80+4], 21h ; '!'
0x18019e0ba  call    ?AsgAssertFail@details@asg@@YAXUsource_location@std@@PEBD@Z; asg::details::AsgAssertFail(std::source_location,char const *)
0x18019e0c0  lea     rax, aCW1SSrcSemanti_31; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18019e0c7  mov     dword ptr [rbp+57h+var_80], 45Dh
0x18019e0ce  lea     rdx, aAutoCdeclAsgSe_5; "auto __cdecl asg::SemanticIndex::Applic"...
0x18019e0d5  mov     qword ptr [rbp+57h+var_80+8], rax
0x18019e0d9  lea     rcx, [rbp+57h+var_80]
0x18019e0dd  mov     qword ptr [rbp+57h+var_70], rdx
0x18019e0e1  mov     dword ptr [rbp+57h+var_80+4], 21h ; '!'
0x18019e0e8  call    ?AsgAssertFail@details@asg@@YAXUsource_location@std@@PEBD@Z; asg::details::AsgAssertFail(std::source_location,char const *)
```
