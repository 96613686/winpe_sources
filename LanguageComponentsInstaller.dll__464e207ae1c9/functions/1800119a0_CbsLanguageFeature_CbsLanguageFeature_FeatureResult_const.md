# CbsLanguageFeature::CbsLanguageFeature(FeatureResult const *)

- ea: `0x1800119a0`
- end: `0x180011d07`
- name: `??0CbsLanguageFeature@@QEAA@PEBUFeatureResult@@@Z`
- size: `871`
- prototype: `CbsLanguageFeature *__fastcall(CbsLanguageFeature *__hidden this, const struct FeatureResult *)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, installer_update`

## callers

- `0x18000b560`
- `0x18001082c`

## callees

- `0x180003520`
- `0x180004154`
- `0x180006380`
- `0x18000c45c`
- `0x18000dbf0`
- `0x180010c84`
- `0x180011038`
- `0x180011534`
- `0x1800119a0`
- `0x1800120b0`
- `0x180012770`
- `0x180012b94`
- `0x180012c04`
- `0x180012c8c`
- `0x180012cfc`
- `0x180017328`
- `0x180021b6c`
- `0x180022a60`
- `0x180023df0`

## string_xrefs

- `0x180011cc1`: `Invalid linguistic payload name - field 'LinguisticPayloadType' in feature manifest is invalid`
- `0x180011ce4`: `CbsLanguageFeature needs to be constructed with an update that is a language feature on demand.`

## pseudocode

```c
CbsLanguageFeature *__fastcall CbsLanguageFeature::CbsLanguageFeature(
        CbsLanguageFeature *this,
        const struct FeatureResult *a2)
{
  char v4; // r14
  _QWORD *v5; // rcx
  _QWORD *v6; // rdx
  char v7; // bl
  __int64 v8; // rax
  __int64 v9; // r8
  char v10; // bl
  char *v11; // rax
  wchar_t **v12; // rbx
  const wchar_t *v13; // rdx
  __int64 v14; // rax
  const wchar_t *v15; // rcx
  __int64 v16; // r8
  const wchar_t *v17; // rdx
  _BYTE pExceptionObject[40]; // [rsp+48h] [rbp-B8h] BYREF
  CbsLanguageFeature *v20; // [rsp+70h] [rbp-90h]
  wchar_t *S1[2]; // [rsp+80h] [rbp-80h] BYREF
  size_t N; // [rsp+90h] [rbp-70h]
  unsigned __int64 v23; // [rsp+98h] [rbp-68h]
  _DWORD v24[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v25; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v26; // [rsp+B8h] [rbp-48h]
  _QWORD v27[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v28; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v29; // [rsp+D8h] [rbp-28h]
  __int64 v30; // [rsp+E0h] [rbp-20h] BYREF
  char v31; // [rsp+E8h] [rbp-18h]
  _OWORD v32[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v33; // [rsp+110h] [rbp+10h]
  char v34; // [rsp+118h] [rbp+18h]
  __int128 v35; // [rsp+120h] [rbp+20h]
  char v36; // [rsp+130h] [rbp+30h]
  __int64 v37; // [rsp+138h] [rbp+38h]
  __int64 v38; // [rsp+140h] [rbp+40h]
  char v39; // [rsp+148h] [rbp+48h] BYREF
  __int64 v40; // [rsp+150h] [rbp+50h] BYREF
  char v41; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v42[8]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v43[32]; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v44[32]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v45[32]; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v46[24]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v47[24]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v48[120]; // [rsp+218h] [rbp+118h] BYREF

  v20 = this;
  v4 = 0;
  CbsFeature::CbsFeature(this, a2);
  *(_OWORD *)((char *)this + 152) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 7;
  *((_WORD *)this + 76) = 0;
  GetCapabilityNameLanguagePair(v24, a2);
  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::basic_regex<unsigned short,std::regex_traits<unsigned short>>(&v40);
  v30 = 0;
  v31 = 0;
  memset(v32, 0, sizeof(v32));
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  if ( v26 <= 7 )
  {
    v5 = v24;
    v6 = v24;
  }
  else
  {
    LODWORD(v5) = v24[0];
    LODWORD(v6) = v24[0];
  }
  if ( !v40 )
    goto LABEL_10;
  std::_Matcher2<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short,std::regex_traits<unsigned short>,std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,void>::_Matcher2<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short,std::regex_traits<unsigned short>,std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,void>(
    (unsigned int)v42,
    (_DWORD)v6,
    (_DWORD)v5 + 2 * v25,
    (unsigned int)&v41,
    v40,
    *(_DWORD *)(v40 + 40),
    *(_DWORD *)(v40 + 32));
  v7 = std::_Matcher2<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short,std::regex_traits<unsigned short>,std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,void>::_Match<std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>>(
         v42,
         &v30);
  std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>::~vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>>(v48);
  std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::~vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>(v47);
  std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::~vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>(v46);
  std::vector<enum PayloadType>::~vector<enum PayloadType>(v45);
  std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::~vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>(v44);
  std::vector<enum PayloadType>::~vector<enum PayloadType>(v43);
  if ( !v7 )
    goto LABEL_10;
  v8 = std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(
         &v30,
         pExceptionObject,
         1);
  v4 = 1;
  v9 = *(_QWORD *)(v8 + 16);
  if ( *(_QWORD *)(v8 + 24) > 7u )
    v8 = *(_QWORD *)v8;
  if ( v9 != 8 || (v10 = 0, wmemcmp((const wchar_t *)v8, L"Language", 8u)) )
LABEL_10:
    v10 = 1;
  if ( (v4 & 1) != 0 )
    std::wstring::~wstring(pExceptionObject);
  if ( v10 )
  {
    std::invalid_argument::invalid_argument(
      (std::invalid_argument *)pExceptionObject,
      "CbsLanguageFeature needs to be constructed with an update that is a language feature on demand.");
    throw (std::invalid_argument *)pExceptionObject;
  }
  std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(
    &v30,
    S1,
    2);
  v11 = &v39;
  if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v32[0] + 1) - *(_QWORD *)&v32[0]) >> 3) > 4 )
    v11 = (char *)(*(_QWORD *)&v32[0] + 112LL);
  if ( *v11 )
  {
    std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::str(
      &v30,
      pExceptionObject,
      3);
    std::wstring::append(S1);
    std::wstring::~wstring(pExceptionObject);
  }
  v12 = &off_18002B450;
  do
  {
    v13 = *v12;
    v14 = -1;
    do
      ++v14;
    while ( v13[v14] );
    v15 = (const wchar_t *)S1;
    if ( v23 > 7 )
      v15 = S1[0];
    if ( N == v14 && (!N || !wmemcmp(v15, v13, N)) )
      break;
    v12 += 2;
  }
  while ( v12 != (wchar_t **)&off_18002B500 );
  if ( v12 == (wchar_t **)&off_18002B500 )
  {
    std::invalid_argument::invalid_argument(
      (std::invalid_argument *)pExceptionObject,
      "Invalid linguistic payload name - field 'LinguisticPayloadType' in feature manifest is invalid");
    throw (std::invalid_argument *)pExceptionObject;
  }
  *((_DWORD *)this + 46) = *((_DWORD *)v12 + 2);
  v16 = v28;
  if ( !v28 )
  {
    v16 = 3;
    v17 = L"zxx";
LABEL_33:
    std::wstring::_Assign<unsigned short>((char *)this + 152, v17, v16);
    goto LABEL_34;
  }
  if ( (_QWORD *)((char *)this + 152) != v27 )
  {
    v17 = (const wchar_t *)v27;
    if ( v29 > 7 )
      v17 = (const wchar_t *)v27[0];
    goto LABEL_33;
  }
LABEL_34:
  std::wstring::~wstring(S1);
  std::vector<CbsLanguageFeatureId>::~vector<CbsLanguageFeatureId>(v32);
  std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(&v40);
  std::wstring::~wstring(v27);
  std::wstring::~wstring(v24);
  return this;
}

```

## disassembly

```asm
0x1800119a0  mov     [rsp-8+arg_10], rbx
0x1800119a5  push    rbp
0x1800119a6  push    rsi
0x1800119a7  push    rdi
0x1800119a8  push    r14
0x1800119aa  push    r15
0x1800119ac  lea     rbp, [rsp-1A0h]
0x1800119b4  sub     rsp, 2A0h
0x1800119bb  mov     rax, cs:__security_cookie
0x1800119c2  xor     rax, rsp
0x1800119c5  mov     [rbp+1C0h+var_30], rax
0x1800119cc  mov     rbx, rdx
0x1800119cf  mov     rsi, rcx
0x1800119d2  mov     [rsp+2C0h+var_250], rcx
0x1800119d7  xor     r15d, r15d
0x1800119da  mov     r14d, r15d
0x1800119dd  mov     [rsp+2C0h+var_280], r15d
0x1800119e2  call    ??0CbsFeature@@QEAA@PEBUFeatureResult@@@Z; CbsFeature::CbsFeature(FeatureResult const *)
0x1800119e7  nop
0x1800119e8  lea     rdi, [rsi+98h]
0x1800119ef  xorps   xmm0, xmm0
0x1800119f2  movups  xmmword ptr [rdi], xmm0
0x1800119f5  mov     [rdi+10h], r15
0x1800119f9  mov     qword ptr [rdi+18h], 7
0x180011a01  mov     [rdi], r15w
0x180011a05  mov     rdx, rbx
0x180011a08  lea     rcx, [rbp+1C0h+var_220]
0x180011a0c  call    ?GetCapabilityNameLanguagePair@@YA?AU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEBUFeatureResult@@@Z; GetCapabilityNameLanguagePair(FeatureResult const *)
0x180011a11  nop
0x180011a12  lea     rcx, [rbp+1C0h+var_170]
0x180011a16  call    ??0?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@PEBGW4syntax_option_type@regex_constants@1@@Z; std::basic_regex<ushort,std::regex_traits<ushort>>::basic_regex<ushort,std::regex_traits<ushort>>(ushort const *,std::regex_constants::syntax_option_type)
0x180011a1b  nop
0x180011a1c  mov     [rbp+1C0h+var_1E0], r15
0x180011a20  mov     [rbp+1C0h+var_1D8], r15b
0x180011a24  xorps   xmm0, xmm0
0x180011a27  movdqa  [rbp+1C0h+var_1D0], xmm0
0x180011a2c  xorps   xmm1, xmm1
0x180011a2f  movdqa  [rbp+1C0h+var_1C0], xmm1
0x180011a34  mov     [rbp+1C0h+var_1B0], r15
0x180011a38  mov     [rbp+1C0h+var_1A8], r15b
0x180011a3c  movdqa  [rbp+1C0h+var_1A0], xmm0
0x180011a41  mov     [rbp+1C0h+var_190], r15b
0x180011a45  mov     [rbp+1C0h+var_188], r15
0x180011a49  mov     [rbp+1C0h+var_180], r15
0x180011a4d  mov     [rbp+1C0h+var_178], r15b
0x180011a51  cmp     [rbp+1C0h+var_208], 7
0x180011a56  jbe     short loc_180011A61
0x180011a58  mov     rcx, qword ptr [rbp+1C0h+var_220]
0x180011a5c  mov     rdx, rcx
0x180011a5f  jmp     short loc_180011A69
0x180011a61  lea     rcx, [rbp+1C0h+var_220]
0x180011a65  lea     rdx, [rbp+1C0h+var_220]
0x180011a69  mov     r9, [rbp+1C0h+var_170]
0x180011a6d  test    r9, r9
0x180011a70  jz      loc_180011B46
0x180011a76  mov     rax, [rbp+1C0h+var_210]
0x180011a7a  lea     r8, [rcx+rax*2]
0x180011a7e  mov     eax, [r9+20h]
0x180011a82  mov     [rsp+2C0h+var_290], eax
0x180011a86  mov     eax, [r9+28h]
0x180011a8a  mov     [rsp+2C0h+var_298], eax
0x180011a8e  mov     [rsp+2C0h+var_2A0], r9
0x180011a93  lea     r9, [rbp+1C0h+var_168]
0x180011a97  lea     rcx, [rbp+1C0h+var_140]
0x180011a9e  call    ??0?$_Matcher2@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@GV?$regex_traits@G@2@V12@X@std@@QEAA@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0AEBV?$regex_traits@G@1@PEAV_Root_node@1@IW4syntax_option_type@regex_constants@1@W4match_flag_type@61@@Z; std::_Matcher2<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort,std::regex_traits<ushort>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,void>::_Matcher2<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort,std::regex_traits<ushort>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,void>(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::regex_traits<ushort> const &,std::_Root_node *,uint,std::regex_constants::syntax_option_type,std::regex_constants::match_flag_type)
0x180011aa3  nop
0x180011aa4  lea     rdx, [rbp+1C0h+var_1E0]
0x180011aa8  lea     rcx, [rbp+1C0h+var_140]
0x180011aaf  call    ??$_Match@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@std@@@?$_Matcher2@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@GV?$regex_traits@G@2@V12@X@std@@QEAA_NPEAV?$match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@1@_N@Z; std::_Matcher2<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort,std::regex_traits<ushort>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,void>::_Match<std::allocator<std::sub_match<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>>(std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>> *,bool)
0x180011ab4  mov     bl, al
0x180011ab6  lea     rcx, [rbp+1C0h+var_A8]
0x180011abd  call    ??1?$vector@V?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@V?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>::~vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>>(void)
0x180011ac2  lea     rcx, [rbp+1C0h+var_C0]
0x180011ac9  call    ??1?$vector@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>::~vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>(void)
0x180011ace  lea     rcx, [rbp+1C0h+var_D8]
0x180011ad5  call    ??1?$vector@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>::~vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>(void)
0x180011ada  lea     rcx, [rbp+1C0h+var_F8]
0x180011ae1  call    ??1?$vector@W4PayloadType@@V?$allocator@W4PayloadType@@@std@@@std@@QEAA@XZ; std::vector<PayloadType>::~vector<PayloadType>(void)
0x180011ae6  lea     rcx, [rbp+1C0h+var_118]
0x180011aed  call    ??1?$vector@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@3@@std@@QEAA@XZ; std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>::~vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>(void)
0x180011af2  lea     rcx, [rbp+1C0h+var_138]
0x180011af9  call    ??1?$vector@W4PayloadType@@V?$allocator@W4PayloadType@@@std@@@std@@QEAA@XZ; std::vector<PayloadType>::~vector<PayloadType>(void)
0x180011afe  test    bl, bl
0x180011b00  jz      short loc_180011B46
0x180011b02  mov     r8d, 1
0x180011b08  lea     rdx, [rsp+2C0h+pExceptionObject]
0x180011b0d  lea     rcx, [rbp+1C0h+var_1E0]
0x180011b11  call    ?str@?$match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_K@Z; std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(unsigned __int64)
0x180011b16  mov     r14d, 1
0x180011b1c  mov     r8, [rax+10h]; N
0x180011b20  cmp     qword ptr [rax+18h], 7
0x180011b25  jbe     short loc_180011B2A
0x180011b27  mov     rax, [rax]
0x180011b2a  cmp     r8, 8
0x180011b2e  jnz     short loc_180011B46
0x180011b30  lea     rdx, aLanguage; "Language"
0x180011b37  mov     rcx, rax; S1
0x180011b3a  call    wmemcmp
0x180011b3f  test    eax, eax
0x180011b41  mov     bl, r15b
0x180011b44  jz      short loc_180011B48
0x180011b46  mov     bl, 1
0x180011b48  test    r14b, 1
0x180011b4c  jz      short loc_180011B58
0x180011b4e  lea     rcx, [rsp+2C0h+pExceptionObject]; void *
0x180011b53  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011b58  test    bl, bl
0x180011b5a  jnz     loc_180011CE4
0x180011b60  mov     r8d, 2
0x180011b66  lea     rdx, [rbp+1C0h+S1]
0x180011b6a  lea     rcx, [rbp+1C0h+var_1E0]
0x180011b6e  call    ?str@?$match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_K@Z; std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(unsigned __int64)
0x180011b73  nop
0x180011b74  mov     rcx, qword ptr [rbp+1C0h+var_1D0]
0x180011b78  mov     rax, qword ptr [rbp+1C0h+var_1D0+8]
0x180011b7c  sub     rax, rcx
0x180011b7f  sar     rax, 3
0x180011b83  mov     rdx, 0AAAAAAAAAAAAAAABh
0x180011b8d  imul    rax, rdx
0x180011b91  cmp     rax, 4
0x180011b95  lea     rax, [rbp+1C0h+var_178]
0x180011b99  jbe     short loc_180011B9F
0x180011b9b  lea     rax, [rcx+70h]
0x180011b9f  cmp     [rax], r15b
0x180011ba2  jz      short loc_180011BD0
0x180011ba4  mov     r8d, 3
0x180011baa  lea     rdx, [rsp+2C0h+pExceptionObject]
0x180011baf  lea     rcx, [rbp+1C0h+var_1E0]
0x180011bb3  call    ?str@?$match_results@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V?$allocator@V?$sub_match@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@2@@std@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@_K@Z; std::match_results<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::str(unsigned __int64)
0x180011bb8  nop
0x180011bb9  mov     rdx, rax
0x180011bbc  lea     rcx, [rbp+1C0h+S1]; Src
0x180011bc0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180011bc5  nop
0x180011bc6  lea     rcx, [rsp+2C0h+pExceptionObject]; void *
0x180011bcb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011bd0  lea     rbx, off_18002B450; "Basic"
0x180011bd7  lea     r14, off_18002B500; "zxx"
0x180011bde  mov     rdx, [rbx]; S2
0x180011be1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011be5  inc     rax
0x180011be8  cmp     [rdx+rax*2], r15w
0x180011bed  jnz     short loc_180011BE5
0x180011bef  mov     r8, [rbp+1C0h+N]; N
0x180011bf3  lea     rcx, [rbp+1C0h+S1]
0x180011bf7  cmp     [rbp+1C0h+var_228], 7
0x180011bfc  cmova   rcx, [rbp+1C0h+S1]; S1
0x180011c01  cmp     r8, rax
0x180011c04  jnz     short loc_180011C14
0x180011c06  test    r8, r8
0x180011c09  jz      short loc_180011C1D
0x180011c0b  call    wmemcmp
0x180011c10  test    eax, eax
0x180011c12  jz      short loc_180011C1D
0x180011c14  add     rbx, 10h
0x180011c18  cmp     rbx, r14
0x180011c1b  jnz     short loc_180011BDE
0x180011c1d  cmp     rbx, r14
0x180011c20  jz      loc_180011CC1
0x180011c26  mov     eax, [rbx+8]
0x180011c29  mov     [rsi+0B8h], eax
0x180011c2f  mov     r8, [rbp+1C0h+var_1F0]
0x180011c33  test    r8, r8
0x180011c36  jnz     short loc_180011C47
0x180011c38  mov     r8d, 3
0x180011c3e  lea     rdx, aZxx; "zxx"
0x180011c45  jmp     short loc_180011C5E
0x180011c47  lea     rax, [rbp+1C0h+var_200]
0x180011c4b  cmp     rdi, rax
0x180011c4e  jz      short loc_180011C67
0x180011c50  lea     rdx, [rbp+1C0h+var_200]
0x180011c54  cmp     [rbp+1C0h+var_1E8], 7
0x180011c59  cmova   rdx, [rbp+1C0h+var_200]
0x180011c5e  mov     rcx, rdi
0x180011c61  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180011c66  nop
0x180011c67  lea     rcx, [rbp+1C0h+S1]; void *
0x180011c6b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011c70  nop
0x180011c71  lea     rcx, [rbp+1C0h+var_1D0]
0x180011c75  call    ??1?$vector@UCbsLanguageFeatureId@@V?$allocator@UCbsLanguageFeatureId@@@std@@@std@@QEAA@XZ; std::vector<CbsLanguageFeatureId>::~vector<CbsLanguageFeatureId>(void)
0x180011c7a  nop
0x180011c7b  lea     rcx, [rbp+1C0h+var_170]
0x180011c7f  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x180011c84  nop
0x180011c85  lea     rcx, [rbp+1C0h+var_200]; void *
0x180011c89  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011c8e  lea     rcx, [rbp+1C0h+var_220]; void *
0x180011c92  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011c97  nop
0x180011c98  mov     rax, rsi
0x180011c9b  mov     rcx, [rbp+1C0h+var_30]
0x180011ca2  xor     rcx, rsp; StackCookie
0x180011ca5  call    __security_check_cookie
0x180011caa  mov     rbx, [rsp+2C0h+arg_10]
0x180011cb2  add     rsp, 2A0h
0x180011cb9  pop     r15
0x180011cbb  pop     r14
0x180011cbd  pop     rdi
0x180011cbe  pop     rsi
0x180011cbf  pop     rbp
0x180011cc0  retn
0x180011cc1  lea     rdx, aInvalidLinguis; "Invalid linguistic payload name - field"...
0x180011cc8  lea     rcx, [rsp+2C0h+pExceptionObject]; this
0x180011ccd  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x180011cd2  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x180011cd9  lea     rcx, [rsp+2C0h+pExceptionObject]; pExceptionObject
0x180011cde  call    _CxxThrowException_0
0x180011ce4  lea     rdx, aCbslanguagefea; "CbsLanguageFeature needs to be construc"...
0x180011ceb  lea     rcx, [rsp+2C0h+pExceptionObject]; this
0x180011cf0  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x180011cf5  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x180011cfc  lea     rcx, [rsp+2C0h+pExceptionObject]; pExceptionObject
0x180011d01  call    _CxxThrowException_0
```
