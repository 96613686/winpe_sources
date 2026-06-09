# GetLoadedHiveKeyNameInternal(wchar_t const *,wchar_t *,unsigned __int64)

- ea: `0x180025098`
- end: `0x18002547f`
- name: `?GetLoadedHiveKeyNameInternal@@YAJPEB_WPEA_W_K@Z`
- size: `999`
- prototype: `__int64 __fastcall(const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18001a5b4`

## callees

- `0x180003870`
- `0x18000f72c`
- `0x18000fafc`
- `0x18000fef0`
- `0x180024d10`
- `0x180024e7c`
- `0x180024f58`
- `0x180025098`
- `0x180031bec`
- `0x180031bf8`

## string_xrefs

- `0x1800250f3`: `Not-null check failed: FullOfflineHiveFilePath`
- `0x180025238`: `lusSanitizedFilePath.Length != 0`
- `0x180025442`: `::RtlStringCchCopyNW(KeyNameBuffer, KeyNameBufferSize, lusKeyName.Buffer, cchKeyName)`

## pseudocode

```c
__int64 __fastcall GetLoadedHiveKeyNameInternal(const wchar_t *a1, wchar_t *a2)
{
  wchar_t *v2; // rdi
  const char *v4; // rax
  __int64 result; // rax
  __int64 v6; // rbx
  char *v7; // rsi
  __int64 v8; // rcx
  char v9; // r8
  __int64 v10; // rax
  void *v11; // rdx
  __int128 *v12; // rcx
  unsigned __int64 v13; // rcx
  unsigned __int64 i; // rax
  unsigned int v15; // ebx
  __int64 v16; // rcx
  wchar_t *v17; // rcx
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  __int128 v20; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+30h] [rbp-D0h]
  const char *v22; // [rsp+38h] [rbp-C8h]
  __int128 v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h]
  _QWORD v25[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v26[3]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v27; // [rsp+88h] [rbp-78h] BYREF
  void *Buf1; // [rsp+98h] [rbp-68h]
  __int64 v29; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v30[512]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v31; // [rsp+2B0h] [rbp+1B0h]
  __int64 v32; // [rsp+2B8h] [rbp+1B8h]
  wchar_t *v33; // [rsp+2C0h] [rbp+1C0h]

  v2 = a2;
  if ( !a1 )
  {
    v21 = 27;
    *(_QWORD *)&v20 = "onecore\\base\\servicing\\offlinehives\\offlinehives.cpp";
    *((_QWORD *)&v20 + 1) = "GetLoadedHiveKeyNameInternal";
    v4 = "Not-null check failed: FullOfflineHiveFilePath";
LABEL_3:
    v22 = v4;
    RtlReportErrorOrigination(&v20, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a2 )
  {
    v21 = 28;
    *(_QWORD *)&v20 = "onecore\\base\\servicing\\offlinehives\\offlinehives.cpp";
    *((_QWORD *)&v20 + 1) = "GetLoadedHiveKeyNameInternal";
    v4 = "Not-null check failed: KeyNameBuffer";
    goto LABEL_3;
  }
  v32 = 510;
  v33 = (wchar_t *)v30;
  memcpy_0(v30, L"{bf1a281b-ad7b-4476-ac95-f47682990ce7}", 0x4Cu);
  v31 = 76;
  Buf1 = 0;
  v27 = 0;
  result = RtlInitLUnicodeStringFromNullTerminatedString(a1, &v27);
  if ( (int)result >= 0 )
  {
    v6 = v27;
    v7 = (char *)Buf1;
    v20 = 0;
    v21 = 0;
    if ( (unsigned __int64)v27 < 8
      || (memcmp_0(Buf1, L"\\\\?\\", 8u)
        ? (v9 = 0, v10 = 0, v8 = 0, v11 = 0)
        : (v8 = v6 - 8, v9 = 1, v10 = v6 - 8, v11 = v7 + 8),
          !v9) )
    {
      v8 = *((_QWORD *)&v27 + 1);
      v10 = v6;
      v11 = v7;
    }
    *(_QWORD *)&v27 = v10;
    *((_QWORD *)&v27 + 1) = v8;
    Buf1 = v11;
    if ( !v10 )
    {
      v21 = 44;
      *(_QWORD *)&v20 = "onecore\\base\\servicing\\offlinehives\\offlinehives.cpp";
      *((_QWORD *)&v20 + 1) = "GetLoadedHiveKeyNameInternal";
      v4 = "lusSanitizedFilePath.Length != 0";
      goto LABEL_3;
    }
    v12 = &v27;
    if ( (v10 & 0xFFFFFFFFFFFFFFFEuLL) >= 0x1B2 )
    {
      v29 = 0;
      result = RtlHashEncodedLBlob(&v27, RtlDecodeUtf16LE, FsnpDowncaseChar, &v29);
      if ( (int)result < 0 )
        return result;
      v25[1] = 8;
      v25[0] = 6;
      v25[2] = L"..{";
      v26[0] = 6;
      v26[2] = L"}..";
      v26[1] = 8;
      v24 = 0;
      v23 = 0;
      result = Windows::StringUtil::Rtl::SubStringByCharCount<_LUNICODE_STRING>(&v27, 0, 97, &v23, 0, 0, 0);
      if ( (int)result < 0 )
        return result;
      result = ((__int64 (__fastcall *)(__int128 *, unsigned __int64, __int64, __int128 *))Windows::StringUtil::Rtl::SubStringByCharCount<_LUNICODE_STRING>)(
                 &v27,
                 ((unsigned __int64)v27 >> 1) - 98,
                 98,
                 &v20);
      if ( (int)result < 0 )
        return result;
      result = Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(
                 &v23,
                 v30);
      if ( (int)result < 0 )
        return result;
      result = Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(
                 v25,
                 v30);
      if ( (int)result < 0 )
        return result;
      result = Windows::StringUtil::Rtl::AppendInteger<RtlString::FixedString<_LUNICODE_STRING,255> *,unsigned __int64>(
                 v16,
                 v29,
                 v30);
      if ( (int)result < 0 )
        return result;
      result = Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(
                 v26,
                 v30);
      if ( (int)result < 0 )
        return result;
      v12 = &v20;
    }
    result = Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(
               v12,
               v30);
    if ( (int)result < 0 )
      return result;
    v13 = 38;
    for ( i = v31 >> 1; v13 < i; ++v13 )
    {
      if ( v33[v13] == 92 )
        v33[v13] = 47;
    }
    if ( i > 0x7FFFFFFE )
    {
      v15 = -1073741811;
      *v2 = 0;
LABEL_38:
      v21 = 95;
      *(_QWORD *)&v20 = "onecore\\base\\servicing\\offlinehives\\offlinehives.cpp";
      *((_QWORD *)&v20 + 1) = "GetLoadedHiveKeyNameInternal";
      v22 = "::RtlStringCchCopyNW(KeyNameBuffer, KeyNameBufferSize, lusKeyName.Buffer, cchKeyName)";
      RtlReportErrorOrigination(&v20, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, v15);
      return v15;
    }
    v17 = v33;
    v18 = 256;
    do
    {
      if ( !i )
        break;
      if ( !*v17 )
        break;
      *v2++ = *v17++;
      --i;
      --v18;
    }
    while ( v18 );
    v19 = v2 - 1;
    v15 = v18 == 0 ? 0x80000005 : 0;
    if ( v18 )
      v19 = v2;
    *v19 = 0;
    if ( !v18 )
      goto LABEL_38;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180025098  mov     [rsp-8+arg_10], rbx
0x18002509d  push    rbp
0x18002509e  push    rsi
0x18002509f  push    rdi
0x1800250a0  push    r14
0x1800250a2  push    r15
0x1800250a4  lea     rbp, [rsp-1E0h]
0x1800250ac  sub     rsp, 2E0h
0x1800250b3  mov     rax, cs:__security_cookie
0x1800250ba  xor     rax, rsp
0x1800250bd  mov     [rbp+200h+var_30], rax
0x1800250c4  xor     r14d, r14d
0x1800250c7  mov     rdi, rdx
0x1800250ca  mov     rbx, rcx
0x1800250cd  test    rcx, rcx
0x1800250d0  jnz     short loc_180025120
0x1800250d2  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\offlinehives"...
0x1800250d9  mov     [rsp+300h+var_2D0], 1Bh
0x1800250e2  mov     qword ptr [rsp+300h+var_2E0], rax
0x1800250e7  lea     rax, aGetloadedhivek; "GetLoadedHiveKeyNameInternal"
0x1800250ee  mov     qword ptr [rsp+300h+var_2E0+8], rax
0x1800250f3  lea     rax, aNotNullCheckFa; "Not-null check failed: FullOfflineHiveF"...
0x1800250fa  mov     r8d, 0C000000Dh
0x180025100  mov     [rsp+300h+var_2C8], rax
0x180025105  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18002510c  lea     rcx, [rsp+300h+var_2E0]
0x180025111  call    RtlReportErrorOrigination
0x180025116  mov     eax, 0C000000Dh
0x18002511b  jmp     loc_180025459
0x180025120  test    rdi, rdi
0x180025123  jnz     short loc_18002514F
0x180025125  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\offlinehives"...
0x18002512c  mov     [rsp+300h+var_2D0], 1Ch
0x180025135  mov     qword ptr [rsp+300h+var_2E0], rax
0x18002513a  lea     rax, aGetloadedhivek; "GetLoadedHiveKeyNameInternal"
0x180025141  mov     qword ptr [rsp+300h+var_2E0+8], rax
0x180025146  lea     rax, aNotNullCheckFa_5; "Not-null check failed: KeyNameBuffer"
0x18002514d  jmp     short loc_1800250FA
0x18002514f  lea     rax, [rbp+200h+var_250]
0x180025153  mov     [rbp+200h+var_48], 1FEh
0x18002515e  mov     esi, 4Ch ; 'L'
0x180025163  mov     [rbp+200h+var_40], rax
0x18002516a  mov     r8d, esi; Size
0x18002516d  lea     rdx, aBf1a281bAd7b44; "{bf1a281b-ad7b-4476-ac95-f47682990ce7}"
0x180025174  lea     rcx, [rbp+200h+var_250]; void *
0x180025178  call    memcpy_0
0x18002517d  xorps   xmm0, xmm0
0x180025180  mov     [rbp+200h+var_50], rsi
0x180025187  xor     eax, eax
0x180025189  lea     rdx, [rbp+200h+var_278]
0x18002518d  mov     rcx, rbx
0x180025190  mov     [rbp+200h+Buf1], rax
0x180025194  movups  [rbp+200h+var_278], xmm0
0x180025198  call    RtlInitLUnicodeStringFromNullTerminatedString
0x18002519d  test    eax, eax
0x18002519f  js      loc_180025459
0x1800251a5  mov     rbx, qword ptr [rbp+200h+var_278]
0x1800251a9  xor     eax, eax
0x1800251ab  mov     rsi, [rbp+200h+Buf1]
0x1800251af  xorps   xmm0, xmm0
0x1800251b2  movups  [rsp+300h+var_2E0], xmm0
0x1800251b7  mov     [rsp+300h+var_2D0], rax
0x1800251bc  lea     r15d, [rax+8]
0x1800251c0  cmp     rbx, r15
0x1800251c3  jb      short loc_1800251FC
0x1800251c5  mov     r8d, r15d; Size
0x1800251c8  lea     rdx, asc_18003F4E8; "\\\\?\\"
0x1800251cf  mov     rcx, rsi; Buf1
0x1800251d2  call    memcmp_0
0x1800251d7  test    eax, eax
0x1800251d9  jnz     short loc_1800251EB
0x1800251db  lea     rcx, [rbx-8]
0x1800251df  mov     r8b, 1
0x1800251e2  mov     rax, rcx
0x1800251e5  lea     rdx, [rsi+8]
0x1800251e9  jmp     short loc_1800251F7
0x1800251eb  mov     r8b, r14b
0x1800251ee  mov     rax, r14
0x1800251f1  mov     rcx, r14
0x1800251f4  mov     rdx, r14
0x1800251f7  test    r8b, r8b
0x1800251fa  jnz     short loc_180025206
0x1800251fc  mov     rcx, qword ptr [rbp+200h+var_278+8]
0x180025200  mov     rax, rbx
0x180025203  mov     rdx, rsi
0x180025206  mov     qword ptr [rbp+200h+var_278], rax
0x18002520a  mov     qword ptr [rbp+200h+var_278+8], rcx
0x18002520e  mov     [rbp+200h+Buf1], rdx
0x180025212  test    rax, rax
0x180025215  jnz     short loc_180025244
0x180025217  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\offlinehives"...
0x18002521e  mov     [rsp+300h+var_2D0], 2Ch ; ','
0x180025227  mov     qword ptr [rsp+300h+var_2E0], rax
0x18002522c  lea     rax, aGetloadedhivek; "GetLoadedHiveKeyNameInternal"
0x180025233  mov     qword ptr [rsp+300h+var_2E0+8], rax
0x180025238  lea     rax, aLussanitizedfi; "lusSanitizedFilePath.Length != 0"
0x18002523f  jmp     loc_1800250FA
0x180025244  and     rax, 0FFFFFFFFFFFFFFFEh
0x180025248  lea     rcx, [rbp+200h+var_278]
0x18002524c  cmp     rax, 1B2h
0x180025252  jnb     short loc_1800252AF
0x180025254  lea     rdx, [rbp+200h+var_250]
0x180025258  call    ??$AppendString@U_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@$0A@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@@Z; Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(_LUNICODE_STRING const &,RtlString::FixedString<_LUNICODE_STRING,255> *)
0x18002525d  test    eax, eax
0x18002525f  js      loc_180025459
0x180025265  mov     rax, [rbp+200h+var_50]
0x18002526c  mov     ecx, 26h ; '&'
0x180025271  shr     rax, 1
0x180025274  cmp     rax, rcx
0x180025277  jbe     short loc_180025295
0x180025279  mov     rdx, [rbp+200h+var_40]
0x180025280  cmp     word ptr [rdx+rcx*2], 5Ch ; '\'
0x180025285  jnz     short loc_18002528D
0x180025287  mov     word ptr [rdx+rcx*2], 2Fh ; '/'
0x18002528d  inc     rcx
0x180025290  cmp     rcx, rax
0x180025293  jb      short loc_180025279
0x180025295  cmp     rax, 7FFFFFFEh
0x18002529b  jbe     loc_1800253C1
0x1800252a1  mov     ebx, 0C000000Dh
0x1800252a6  mov     [rdi], r14w
0x1800252aa  jmp     loc_180025412
0x1800252af  lea     r9, [rbp+200h+var_260]
0x1800252b3  mov     [rbp+200h+var_260], r14
0x1800252b7  lea     r8, ?FsnpDowncaseChar@@YAKK@Z; FsnpDowncaseChar(ulong)
0x1800252be  lea     rdx, RtlDecodeUtf16LE
0x1800252c5  call    RtlHashEncodedLBlob
0x1800252ca  test    eax, eax
0x1800252cc  js      loc_180025459
0x1800252d2  mov     ecx, 6
0x1800252d7  mov     [rsp+300h+var_2A0], r15
0x1800252dc  lea     rax, ??$LiteralBuffer@$2U?$BaseLiteralBuffer@$03U_LUNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0CO@@0CO@@0HL@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3QB_WB; "..{"
0x1800252e3  mov     [rsp+300h+var_2A8], rcx
0x1800252e8  mov     [rsp+300h+var_298], rax
0x1800252ed  lea     r9, [rsp+300h+var_2C0]
0x1800252f2  lea     rax, ??$LiteralBuffer@$2U?$BaseLiteralBuffer@$03U_LUNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0HN@@0CO@@0CO@@0A@@@@$0A@$00$01$02@Details@RtlStringLiterals@@3QB_WB; "}.."
0x1800252f9  mov     [rsp+300h+var_290], rcx
0x1800252fe  mov     [rbp+200h+var_280], rax
0x180025302  lea     r8d, [rcx+5Bh]
0x180025306  xor     eax, eax
0x180025308  mov     [rsp+300h+var_288], r15
0x18002530d  xorps   xmm0, xmm0
0x180025310  mov     [rsp+300h+var_2B0], rax
0x180025315  xorps   xmm1, xmm1
0x180025318  mov     [rsp+300h+var_2D0], rax
0x18002531d  xor     edx, edx
0x18002531f  lea     rcx, [rbp+200h+var_278]
0x180025323  movups  [rsp+300h+var_2C0], xmm0
0x180025328  movups  [rsp+300h+var_2E0], xmm1
0x18002532d  call    ??$SubStringByCharCount@U_LUNICODE_STRING@@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@_K1PEAU3@@Z; Windows::StringUtil::Rtl::SubStringByCharCount<_LUNICODE_STRING>(_LUNICODE_STRING const &,unsigned __int64,unsigned __int64,_LUNICODE_STRING *)
0x180025332  test    eax, eax
0x180025334  js      loc_180025459
0x18002533a  mov     rdx, qword ptr [rbp+200h+var_278]
0x18002533e  lea     r9, [rsp+300h+var_2E0]
0x180025343  shr     rdx, 1
0x180025346  lea     rcx, [rbp+200h+var_278]
0x18002534a  mov     r8d, 62h ; 'b'
0x180025350  sub     rdx, r8
0x180025353  call    ??$SubStringByCharCount@U_LUNICODE_STRING@@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@_K1PEAU3@@Z; Windows::StringUtil::Rtl::SubStringByCharCount<_LUNICODE_STRING>(_LUNICODE_STRING const &,unsigned __int64,unsigned __int64,_LUNICODE_STRING *)
0x180025358  test    eax, eax
0x18002535a  js      loc_180025459
0x180025360  lea     rdx, [rbp+200h+var_250]
0x180025364  lea     rcx, [rsp+300h+var_2C0]
0x180025369  call    ??$AppendString@U_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@$0A@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@@Z; Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(_LUNICODE_STRING const &,RtlString::FixedString<_LUNICODE_STRING,255> *)
0x18002536e  test    eax, eax
0x180025370  js      loc_180025459
0x180025376  lea     rdx, [rbp+200h+var_250]
0x18002537a  lea     rcx, [rsp+300h+var_2A8]
0x18002537f  call    ??$AppendString@U_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@$0A@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@@Z; Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(_LUNICODE_STRING const &,RtlString::FixedString<_LUNICODE_STRING,255> *)
0x180025384  test    eax, eax
0x180025386  js      loc_180025459
0x18002538c  mov     rdx, [rbp+200h+var_260]
0x180025390  lea     r8, [rbp+200h+var_250]
0x180025394  call    ??$AppendInteger@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@_K@Rtl@StringUtil@Windows@@YAJK_KPEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@@Z; Windows::StringUtil::Rtl::AppendInteger<RtlString::FixedString<_LUNICODE_STRING,255> *,unsigned __int64>(ulong,unsigned __int64,RtlString::FixedString<_LUNICODE_STRING,255> *)
0x180025399  test    eax, eax
0x18002539b  js      loc_180025459
0x1800253a1  lea     rdx, [rbp+200h+var_250]
0x1800253a5  lea     rcx, [rsp+300h+var_290]
0x1800253aa  call    ??$AppendString@U_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@$0A@@Rtl@StringUtil@Windows@@YAJAEBU_LUNICODE_STRING@@PEAV?$FixedString@U_LUNICODE_STRING@@$0PP@@RtlString@@@Z; Windows::StringUtil::Rtl::AppendString<_LUNICODE_STRING,RtlString::FixedString<_LUNICODE_STRING,255> *,0>(_LUNICODE_STRING const &,RtlString::FixedString<_LUNICODE_STRING,255> *)
0x1800253af  test    eax, eax
0x1800253b1  js      loc_180025459
0x1800253b7  lea     rcx, [rsp+300h+var_2E0]
0x1800253bc  jmp     loc_180025254
0x1800253c1  mov     rcx, [rbp+200h+var_40]
0x1800253c8  mov     edx, 100h
0x1800253cd  test    rax, rax
0x1800253d0  jz      short loc_1800253F1
0x1800253d2  movzx   r8d, word ptr [rcx]
0x1800253d6  test    r8w, r8w
0x1800253da  jz      short loc_1800253F1
0x1800253dc  mov     [rdi], r8w
0x1800253e0  add     rcx, 2
0x1800253e4  add     rdi, 2
0x1800253e8  dec     rax
0x1800253eb  sub     rdx, 1
0x1800253ef  jnz     short loc_1800253CD
0x1800253f1  mov     rax, rdx
0x1800253f4  lea     rcx, [rdi-2]
0x1800253f8  neg     rax
0x1800253fb  sbb     ebx, ebx
0x1800253fd  not     ebx
0x1800253ff  and     ebx, 80000005h
0x180025405  test    rdx, rdx
0x180025408  cmovnz  rcx, rdi
0x18002540c  mov     [rcx], r14w
0x180025410  jnz     short loc_180025457
0x180025412  lea     rax, aOnecoreBaseSer; "onecore\\base\\servicing\\offlinehives"...
0x180025419  mov     [rsp+300h+var_2D0], 5Fh ; '_'
0x180025422  mov     qword ptr [rsp+300h+var_2E0], rax
0x180025427  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18002542e  lea     rax, aGetloadedhivek; "GetLoadedHiveKeyNameInternal"
0x180025435  mov     r8d, ebx
0x180025438  mov     qword ptr [rsp+300h+var_2E0+8], rax
0x18002543d  lea     rcx, [rsp+300h+var_2E0]
0x180025442  lea     rax, aRtlstringcchco; "::RtlStringCchCopyNW(KeyNameBuffer, Key"...
0x180025449  mov     [rsp+300h+var_2C8], rax
0x18002544e  call    RtlReportErrorOrigination
0x180025453  mov     eax, ebx
0x180025455  jmp     short loc_180025459
0x180025457  xor     eax, eax
0x180025459  mov     rcx, [rbp+200h+var_30]
0x180025460  xor     rcx, rsp; StackCookie
0x180025463  call    __security_check_cookie
0x180025468  mov     rbx, [rsp+300h+arg_10]
0x180025470  add     rsp, 2E0h
0x180025477  pop     r15
0x180025479  pop     r14
0x18002547b  pop     rdi
0x18002547c  pop     rsi
0x18002547d  pop     rbp
0x18002547e  retn
```
