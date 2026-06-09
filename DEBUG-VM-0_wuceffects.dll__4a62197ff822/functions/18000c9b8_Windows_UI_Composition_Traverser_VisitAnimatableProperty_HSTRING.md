# Windows::UI::Composition::Traverser::VisitAnimatableProperty(HSTRING__ *)

- ea: `0x18000c9b8`
- end: `0x18000cdcd`
- name: `?VisitAnimatableProperty@Traverser@Composition@UI@Windows@@AEAAXPEAUHSTRING__@@@Z`
- size: `1045`
- prototype: `void __fastcall(Windows::UI::Composition::Traverser *__hidden this, HSTRING string)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18000c868`

## callees

- `0x18000448c`
- `0x180004db8`
- `0x180008ee0`
- `0x18000c9b8`
- `0x18000d710`
- `0x18000d804`
- `0x18000d8fc`
- `0x18000da90`
- `0x18001de54`
- `0x18001eaa0`
- `0x180020fc0`
- `0x180021060`
- `0x18002584c`
- `0x18002699c`
- `0x18002e010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000cb0e`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000cb0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x18000cab1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstringWithSpecifiedLength` at `0x18000cab1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ca15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ca15`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000cc35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18000cc35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ccae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ccbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ccae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ccbe`

## string_xrefs

- `0x18000cac2`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`
- `0x18000cc46`: `onecoreuap\windows\dwm\effects\compiler\graphicseffectgraphtraversal.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::UI::Composition::Traverser::VisitAnimatableProperty(
        Windows::UI::Composition::FlattenedEffectGraph **this,
        HSTRING string)
{
  const unsigned __int16 *StringRawBuffer; // rsi
  const unsigned __int16 *v5; // rbx
  __int64 trivial_2; // rax
  __int64 v7; // r14
  __int64 v8; // rcx
  UINT32 v9; // r11d
  HRESULT v10; // eax
  unsigned int *NamedEffect; // rbx
  __int64 v12; // rdx
  unsigned __int64 v13; // r8
  __int64 v14; // r12
  __int64 v15; // rcx
  unsigned int PropertyCount; // eax
  __int64 v17; // r14
  unsigned __int16 v18; // si
  Windows::UI::Composition::EffectType *v19; // rcx
  __int64 v20; // r14
  __int16 v21; // ax
  HRESULT v22; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30; // [rsp+20h] [rbp-39h]
  unsigned int v31; // [rsp+30h] [rbp-29h] BYREF
  unsigned int v32; // [rsp+34h] [rbp-25h] BYREF
  UINT32 length; // [rsp+38h] [rbp-21h] BYREF
  unsigned int v34; // [rsp+3Ch] [rbp-1Dh] BYREF
  HSTRING stringa; // [rsp+40h] [rbp-19h] BYREF
  unsigned int v36; // [rsp+48h] [rbp-11h]
  unsigned int v37; // [rsp+4Ch] [rbp-Dh]
  int Type; // [rsp+50h] [rbp-9h]
  unsigned int v39; // [rsp+54h] [rbp-5h]
  HSTRING newString; // [rsp+58h] [rbp-1h] BYREF
  __int64 v41; // [rsp+60h] [rbp+7h] BYREF
  __int128 v42; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v43; // [rsp+78h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( !string )
  {
    std::wstring::wstring(&v42, L"Null animatable property name.");
    Windows::UI::Composition::OriginateException(v25, &v42);
  }
  if ( Windows::UI::Composition::FlattenedEffectGraph::FindAnimatableProperty(*this, string, &v34) )
  {
    std::wstring::wstring(&v42, L"Multiply defined animatable property.");
    Windows::UI::Composition::OriginateException(v26, &v42);
  }
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
  v5 = &StringRawBuffer[length];
  trivial_2 = _std_find_trivial_2(StringRawBuffer, v5, 46);
  v7 = trivial_2;
  if ( (const unsigned __int16 *)trivial_2 == v5
    || !Windows::UI::Composition::Traverser::IsValidNameFormat(
          StringRawBuffer,
          (trivial_2 - (__int64)StringRawBuffer) >> 1)
    || !Windows::UI::Composition::Traverser::IsValidNameFormat(
          (const unsigned __int16 *)(v7 + 2),
          (((__int64)v5 - v7) >> 1) - 1) )
  {
    v42 = 0;
    v43 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v42, L"Malformed animatable property name.", 35);
    Windows::UI::Composition::OriginateException(v8, &v42);
  }
  newString = 0;
  v10 = WindowsSubstringWithSpecifiedLength(string, 0, v9, &newString);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x334,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
      (const char *)(unsigned int)v10,
      v30);
  NamedEffect = (unsigned int *)Windows::UI::Composition::Traverser::FindNamedEffect(
                                  (Windows::UI::Composition::Traverser *)this,
                                  newString);
  if ( !NamedEffect )
  {
    std::wstring::wstring(&v42, L"Animatable property refers to an effect not in the graph.");
    Windows::UI::Composition::OriginateException(v27, &v42);
  }
  v12 = *((_QWORD *)*this + 6);
  v13 = NamedEffect[4];
  if ( (*((_QWORD *)*this + 7) - v12) >> 3 <= v13 )
  {
    std::_Xout_of_range("invalid vector subscript");
    __debugbreak();
  }
  v14 = *(_QWORD *)(v12 + 8 * v13);
  v32 = 0;
  v31 = 0;
  if ( (*(int (__fastcall **)(_QWORD, __int64, unsigned int *, unsigned int *))(**(_QWORD **)NamedEffect + 32LL))(
         *(_QWORD *)NamedEffect,
         v7 + 2,
         &v32,
         &v31) < 0
    || !v31
    || (PropertyCount = Windows::UI::Composition::EffectType::GetPropertyCount(*(Windows::UI::Composition::EffectType **)v14),
        v17 = v32,
        v32 >= PropertyCount) )
  {
    v42 = 0;
    v43 = 0;
    std::wstring::_Construct<1,unsigned short const *>(
      &v42,
      L"Specified property does not exist or cannot be animated.",
      56);
    Windows::UI::Composition::OriginateException(v15, &v42);
  }
  v18 = *(_WORD *)(*(_QWORD *)(v14 + 32) + 2LL * v32);
  v19 = *(Windows::UI::Composition::EffectType **)v14;
  v34 = 0;
  v41 = 0;
  (*(void (__fastcall **)(Windows::UI::Composition::EffectType *, unsigned int *, __int64 *))(*(_QWORD *)v19 + 144LL))(
    v19,
    &v34,
    &v41);
  v20 = v41 + 32 * v17;
  if ( *(_DWORD *)(v20 + 16) != 8 )
  {
    std::wstring::wstring(&v42, L"Specified property cannot be animated.");
    Windows::UI::Composition::OriginateException(v28, &v42);
  }
  v21 = 2;
  if ( v31 == 2 )
  {
    v21 = 1;
  }
  else if ( v31 != 3 )
  {
    switch ( v31 )
    {
      case 4u:
        v21 = 4;
        break;
      case 5u:
        v21 = 8;
        break;
      case 9u:
        v21 = 7;
        break;
      default:
        v21 = -1;
        break;
    }
  }
  if ( (v18 & (unsigned __int16)v21) != 0 )
  {
    std::wstring::wstring(&v42, L"Multiple animatable properties animate the same value.");
    Windows::UI::Composition::OriginateException(v29, &v42);
  }
  *(_WORD *)(*(_QWORD *)(v14 + 32) + 2LL * v32) = v21 | v18;
  stringa = 0;
  v22 = WindowsDuplicateString(string, &stringa);
  if ( v22 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x362,
      (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\graphicseffectgraphtraversal.cpp",
      (const char *)(unsigned int)v22,
      v30);
  v36 = NamedEffect[4];
  v37 = v32;
  Type = Windows::UI::Composition::AnimatableProperties::GetType(v20, v31);
  v39 = v31;
  v23 = (_QWORD *)((char *)*this + 72);
  v24 = *((_QWORD *)*this + 10);
  if ( v24 - *v23 == 9000 )
    Windows::UI::Composition::FlattenedEffectGraph::OriginateGraphTooComplexException();
  if ( v24 == *((_QWORD *)*this + 11) )
  {
    std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::_Emplace_reallocate<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>(
      v23,
      v24,
      &stringa);
  }
  else
  {
    *(_QWORD *)v24 = stringa;
    stringa = 0;
    *(_DWORD *)(v24 + 8) = v36;
    *(_DWORD *)(v24 + 12) = v37;
    *(_DWORD *)(v24 + 16) = Type;
    *(_DWORD *)(v24 + 20) = v39;
    v23[1] += 24LL;
  }
  if ( stringa )
    WindowsDeleteString(stringa);
  if ( newString )
    WindowsDeleteString(newString);
}

```

## disassembly

```asm
0x18000c9b8  mov     [rsp-8+arg_10], rbx
0x18000c9bd  mov     [rsp-8+arg_18], rsi
0x18000c9c2  push    rbp
0x18000c9c3  push    rdi
0x18000c9c4  push    r12
0x18000c9c6  push    r14
0x18000c9c8  push    r15
0x18000c9ca  lea     rbp, [rsp-37h]
0x18000c9cf  sub     rsp, 90h
0x18000c9d6  mov     rax, cs:__security_cookie
0x18000c9dd  xor     rax, rsp
0x18000c9e0  mov     [rbp+57h+var_28], rax
0x18000c9e4  mov     rdi, rdx
0x18000c9e7  mov     r15, rcx
0x18000c9ea  test    rdx, rdx
0x18000c9ed  jz      loc_18000CD24
0x18000c9f3  lea     r8, [rbp+57h+var_74]; unsigned int *
0x18000c9f7  mov     rcx, [rcx]; this
0x18000c9fa  call    ?FindAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@QEBA_NPEAUHSTRING__@@PEAI@Z; Windows::UI::Composition::FlattenedEffectGraph::FindAnimatableProperty(HSTRING__ *,uint *)
0x18000c9ff  test    al, al
0x18000ca01  jnz     loc_18000CD3F
0x18000ca07  mov     [rbp+57h+length], 0
0x18000ca0e  lea     rdx, [rbp+57h+length]; length
0x18000ca12  mov     rcx, rdi; string
0x18000ca15  call    cs:__imp_WindowsGetStringRawBuffer
0x18000ca1b  mov     rsi, rax
0x18000ca1e  mov     ecx, [rbp+57h+length]
0x18000ca21  lea     rbx, [rax+rcx*2]
0x18000ca25  mov     r8d, 2Eh ; '.'
0x18000ca2b  mov     rdx, rbx
0x18000ca2e  mov     rcx, rax
0x18000ca31  call    __std_find_trivial_2
0x18000ca36  mov     r14, rax
0x18000ca39  cmp     rax, rbx
0x18000ca3c  jnz     short loc_18000CA6E
0x18000ca3e  xorps   xmm0, xmm0
0x18000ca41  movups  [rbp+57h+var_48], xmm0
0x18000ca45  xorps   xmm1, xmm1
0x18000ca48  movdqu  [rbp+57h+var_38], xmm1
0x18000ca4d  mov     r8d, 23h ; '#'
0x18000ca53  lea     rdx, aMalformedAnima; "Malformed animatable property name."
0x18000ca5a  lea     rcx, [rbp+57h+var_48]
0x18000ca5e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000ca63  nop
0x18000ca64  lea     rdx, [rbp+57h+var_48]
0x18000ca68  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x18000ca6e  mov     r11, r14
0x18000ca71  sub     r11, rsi
0x18000ca74  sar     r11, 1
0x18000ca77  mov     rdx, r11; unsigned __int64
0x18000ca7a  mov     rcx, rsi; unsigned __int16 *
0x18000ca7d  call    ?IsValidNameFormat@Traverser@Composition@UI@Windows@@CA_NPEBG_K@Z; Windows::UI::Composition::Traverser::IsValidNameFormat(ushort const *,unsigned __int64)
0x18000ca82  test    al, al
0x18000ca84  jz      short loc_18000CA3E
0x18000ca86  sub     rbx, r14
0x18000ca89  sar     rbx, 1
0x18000ca8c  lea     rdx, [rbx-1]; unsigned __int64
0x18000ca90  lea     rcx, [r14+2]; unsigned __int16 *
0x18000ca94  call    ?IsValidNameFormat@Traverser@Composition@UI@Windows@@CA_NPEBG_K@Z; Windows::UI::Composition::Traverser::IsValidNameFormat(ushort const *,unsigned __int64)
0x18000ca99  test    al, al
0x18000ca9b  jz      short loc_18000CA3E
0x18000ca9d  mov     [rbp+57h+newString], 0
0x18000caa5  mov     r8d, r11d; length
0x18000caa8  lea     r9, [rbp+57h+newString]; newString
0x18000caac  xor     edx, edx; startIndex
0x18000caae  mov     rcx, rdi; string
0x18000cab1  call    cs:__imp_WindowsSubstringWithSpecifiedLength
0x18000cab7  mov     rcx, [rbp+5Fh]; this
0x18000cabb  test    eax, eax
0x18000cabd  jns     short loc_18000CAD4
0x18000cabf  mov     r9d, eax; char *
0x18000cac2  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18000cac9  mov     edx, 334h; void *
0x18000cace  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000cad4  mov     rdx, [rbp+57h+newString]; HSTRING
0x18000cad8  mov     rcx, r15; this
0x18000cadb  call    ?FindNamedEffect@Traverser@Composition@UI@Windows@@AEAAPEBUNamedEffect@1234@PEAUHSTRING__@@@Z; Windows::UI::Composition::Traverser::FindNamedEffect(HSTRING__ *)
0x18000cae0  mov     rbx, rax
0x18000cae3  test    rax, rax
0x18000cae6  jz      loc_18000CD5A
0x18000caec  mov     rax, [r15]
0x18000caef  mov     rdx, [rax+30h]
0x18000caf3  mov     r8d, [rbx+10h]
0x18000caf7  mov     rcx, [rax+38h]
0x18000cafb  sub     rcx, rdx
0x18000cafe  sar     rcx, 3
0x18000cb02  cmp     rcx, r8
0x18000cb05  ja      short loc_18000CB15
0x18000cb07  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x18000cb0e  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000cb14  int     3; Trap to Debugger
0x18000cb15  mov     r12, [rdx+r8*8]
0x18000cb19  mov     [rbp+57h+var_7C], 0
0x18000cb20  mov     [rbp+57h+var_80], 0
0x18000cb27  mov     rcx, [rbx]
0x18000cb2a  mov     rax, [rcx]
0x18000cb2d  lea     r9, [rbp+57h+var_80]
0x18000cb31  lea     r8, [rbp+57h+var_7C]
0x18000cb35  lea     rdx, [r14+2]
0x18000cb39  mov     rax, [rax+20h]
0x18000cb3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb42  test    eax, eax
0x18000cb44  jns     short loc_18000CB76
0x18000cb46  xorps   xmm0, xmm0
0x18000cb49  movups  [rbp+57h+var_48], xmm0
0x18000cb4d  xorps   xmm1, xmm1
0x18000cb50  movdqu  [rbp+57h+var_38], xmm1
0x18000cb55  mov     r8d, 38h ; '8'
0x18000cb5b  lea     rdx, aSpecifiedPrope; "Specified property does not exist or ca"...
0x18000cb62  lea     rcx, [rbp+57h+var_48]
0x18000cb66  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000cb6b  nop
0x18000cb6c  lea     rdx, [rbp+57h+var_48]
0x18000cb70  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x18000cb76  cmp     [rbp+57h+var_80], 0
0x18000cb7a  jz      short loc_18000CB46
0x18000cb7c  mov     rcx, [r12]; this
0x18000cb80  call    ?GetPropertyCount@EffectType@Composition@UI@Windows@@QEBAIXZ; Windows::UI::Composition::EffectType::GetPropertyCount(void)
0x18000cb85  mov     r14d, [rbp+57h+var_7C]
0x18000cb89  cmp     r14d, eax
0x18000cb8c  jnb     short loc_18000CB46
0x18000cb8e  mov     rax, [r12+20h]
0x18000cb93  movzx   esi, word ptr [rax+r14*2]
0x18000cb98  mov     rcx, [r12]
0x18000cb9c  mov     [rbp+57h+var_74], 0
0x18000cba3  mov     [rbp+57h+var_50], 0
0x18000cbab  mov     rax, [rcx]
0x18000cbae  lea     r8, [rbp+57h+var_50]
0x18000cbb2  lea     rdx, [rbp+57h+var_74]
0x18000cbb6  mov     rax, [rax+90h]
0x18000cbbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbc2  shl     r14, 5
0x18000cbc6  add     r14, [rbp+57h+var_50]
0x18000cbca  mov     edx, 8
0x18000cbcf  cmp     [r14+10h], edx
0x18000cbd3  jnz     loc_18000CD75
0x18000cbd9  mov     ecx, [rbp+57h+var_80]
0x18000cbdc  lea     eax, [rdx-6]
0x18000cbdf  sub     ecx, eax
0x18000cbe1  jz      loc_18000CDA2
0x18000cbe7  sub     ecx, 1
0x18000cbea  jz      short loc_18000CC0E
0x18000cbec  sub     ecx, 1
0x18000cbef  jz      loc_18000CD98
0x18000cbf5  sub     ecx, 1
0x18000cbf8  jz      loc_18000CD90
0x18000cbfe  lea     eax, [rdx-4]
0x18000cc01  cmp     ecx, eax
0x18000cc03  jz      loc_18000CD1A
0x18000cc09  mov     eax, 0FFFFh
0x18000cc0e  test    ax, si
0x18000cc11  jnz     loc_18000CDAC
0x18000cc17  or      si, ax
0x18000cc1a  mov     edx, [rbp+57h+var_7C]
0x18000cc1d  mov     rax, [r12+20h]
0x18000cc22  mov     [rax+rdx*2], si
0x18000cc26  mov     [rbp+57h+string], 0
0x18000cc2e  lea     rdx, [rbp+57h+string]; newString
0x18000cc32  mov     rcx, rdi; string
0x18000cc35  call    cs:__imp_WindowsDuplicateString
0x18000cc3b  mov     rcx, [rbp+5Fh]; this
0x18000cc3f  test    eax, eax
0x18000cc41  jns     short loc_18000CC58
0x18000cc43  mov     r9d, eax; char *
0x18000cc46  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18000cc4d  mov     edx, 362h; void *
0x18000cc52  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000cc58  mov     eax, [rbx+10h]
0x18000cc5b  mov     [rbp+57h+var_68], eax
0x18000cc5e  mov     eax, [rbp+57h+var_7C]
0x18000cc61  mov     [rbp+57h+var_64], eax
0x18000cc64  mov     edx, [rbp+57h+var_80]
0x18000cc67  mov     rcx, r14
0x18000cc6a  call    ?GetType@AnimatableProperties@Composition@UI@Windows@@SA?AW4DCOMPOSITION_EXPRESSION_TYPE@@AEBUEffectPropertyMetadata@234@W4GRAPHICS_EFFECT_PROPERTY_MAPPING@Effects@Graphics@4@@Z; Windows::UI::Composition::AnimatableProperties::GetType(Windows::UI::Composition::EffectPropertyMetadata const &,Windows::Graphics::Effects::GRAPHICS_EFFECT_PROPERTY_MAPPING)
0x18000cc6f  mov     [rbp+57h+var_60], eax
0x18000cc72  mov     eax, [rbp+57h+var_80]
0x18000cc75  mov     [rbp+57h+var_5C], eax
0x18000cc78  mov     rcx, [r15]
0x18000cc7b  add     rcx, 48h ; 'H'
0x18000cc7f  mov     rdx, [rcx+8]
0x18000cc83  mov     rax, rdx
0x18000cc86  sub     rax, [rcx]
0x18000cc89  cmp     rax, 2328h
0x18000cc8f  jz      loc_18000CDC7
0x18000cc95  cmp     rdx, [rcx+10h]
0x18000cc99  jnz     short loc_18000CCEC
0x18000cc9b  lea     r8, [rbp+57h+string]
0x18000cc9f  call    ??$_Emplace_reallocate@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@?$vector@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEAAPEAUAnimatableProperty@FlattenedEffectGraph@Composition@UI@Windows@@QEAU23456@$$QEAU23456@@Z; std::vector<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>::_Emplace_reallocate<Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty>(Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty * const,Windows::UI::Composition::FlattenedEffectGraph::AnimatableProperty &&)
0x18000cca4  nop
0x18000cca5  mov     rcx, [rbp+57h+string]; string
0x18000cca9  test    rcx, rcx
0x18000ccac  jz      short loc_18000CCB5
0x18000ccae  call    cs:__imp_WindowsDeleteString
0x18000ccb4  nop
0x18000ccb5  mov     rcx, [rbp+57h+newString]; string
0x18000ccb9  test    rcx, rcx
0x18000ccbc  jz      short loc_18000CCC4
0x18000ccbe  call    cs:__imp_WindowsDeleteString
0x18000ccc4  mov     rcx, [rbp+57h+var_28]
0x18000ccc8  xor     rcx, rsp; StackCookie
0x18000cccb  call    __security_check_cookie
0x18000ccd0  lea     r11, [rsp+0B0h+var_20]
0x18000ccd8  mov     rbx, [r11+40h]
0x18000ccdc  mov     rsi, [r11+48h]
0x18000cce0  mov     rsp, r11
0x18000cce3  pop     r15
0x18000cce5  pop     r14
0x18000cce7  pop     r12
0x18000cce9  pop     rdi
0x18000ccea  pop     rbp
0x18000cceb  retn
0x18000ccec  mov     rax, [rbp+57h+string]
0x18000ccf0  mov     [rdx], rax
0x18000ccf3  mov     [rbp+57h+string], 0
0x18000ccfb  mov     eax, [rbp+57h+var_68]
0x18000ccfe  mov     [rdx+8], eax
0x18000cd01  mov     eax, [rbp+57h+var_64]
0x18000cd04  mov     [rdx+0Ch], eax
0x18000cd07  mov     eax, [rbp+57h+var_60]
0x18000cd0a  mov     [rdx+10h], eax
0x18000cd0d  mov     eax, [rbp+57h+var_5C]
0x18000cd10  mov     [rdx+14h], eax
0x18000cd13  add     qword ptr [rcx+8], 18h
0x18000cd18  jmp     short loc_18000CCA5
0x18000cd1a  mov     eax, 7
0x18000cd1f  jmp     loc_18000CC0E
0x18000cd24  lea     rdx, aNullAnimatable; "Null animatable property name."
0x18000cd2b  lea     rcx, [rbp+57h+var_48]
0x18000cd2f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000cd34  nop
0x18000cd35  lea     rdx, [rbp+57h+var_48]
0x18000cd39  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x18000cd3f  lea     rdx, aMultiplyDefine; "Multiply defined animatable property."
0x18000cd46  lea     rcx, [rbp+57h+var_48]
0x18000cd4a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000cd4f  nop
0x18000cd50  lea     rdx, [rbp+57h+var_48]
0x18000cd54  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x18000cd5a  lea     rdx, aAnimatableProp; "Animatable property refers to an effect"...
0x18000cd61  lea     rcx, [rbp+57h+var_48]
0x18000cd65  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000cd6a  nop
0x18000cd6b  lea     rdx, [rbp+57h+var_48]
0x18000cd6f  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x18000cd75  lea     rdx, aSpecifiedPrope_0; "Specified property cannot be animated."
0x18000cd7c  lea     rcx, [rbp+57h+var_48]
0x18000cd80  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000cd85  nop
0x18000cd86  lea     rdx, [rbp+57h+var_48]
0x18000cd8a  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x18000cd90  movzx   eax, dx
0x18000cd93  jmp     loc_18000CC0E
0x18000cd98  mov     eax, 4
0x18000cd9d  jmp     loc_18000CC0E
0x18000cda2  mov     eax, 1
0x18000cda7  jmp     loc_18000CC0E
0x18000cdac  lea     rdx, aMultipleAnimat; "Multiple animatable properties animate "...
0x18000cdb3  lea     rcx, [rbp+57h+var_48]
0x18000cdb7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000cdbc  nop
0x18000cdbd  lea     rdx, [rbp+57h+var_48]
0x18000cdc1  call    ?OriginateException@Composition@UI@Windows@@YAXJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::UI::Composition::OriginateException(long,std::wstring const &)
0x18000cdc7  call    ?OriginateGraphTooComplexException@FlattenedEffectGraph@Composition@UI@Windows@@SAXXZ; Windows::UI::Composition::FlattenedEffectGraph::OriginateGraphTooComplexException(void)
```
