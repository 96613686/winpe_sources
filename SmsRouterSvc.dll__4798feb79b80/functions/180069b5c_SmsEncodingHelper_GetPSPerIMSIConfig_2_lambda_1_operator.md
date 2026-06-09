# _SmsEncodingHelper::GetPSPerIMSIConfig_::_2_::_lambda_1_::operator()

- ea: `0x180069b5c`
- end: `0x18006a201`
- name: `_SmsEncodingHelper::GetPSPerIMSIConfig_::_2_::_lambda_1_::operator()`
- size: `1701`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18006987c`

## callees

- `0x180003a60`
- `0x1800069f0`
- `0x18000ae8c`
- `0x18000d388`
- `0x1800276a4`
- `0x180069a00`
- `0x180069b5c`
- `0x18006afb4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069d01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069d01`
- `MobileNetworking!PersistentRegPathOpenKey` at `0x180069cf2`
- `MobileNetworking!PersistentRegPathOpenKey` at `0x180069cf2`

## string_xrefs

- `0x180069ca1`: `IMSISpecific\`
- `0x180069e24`: `AttemptThresholdForIMS`
- `0x180069e89`: `IMSISpecific\Default\SMS\3GPP2\ErrorHandling`
- `0x180069e2b`: `IMSISpecific\Default\SMS\3GPP\IMS`
- `0x180069e5f`: `IMSISpecific\Default\SMS\3GPP\IMS`
- `0x180069eb1`: `IMSISpecific\Default\SMS`
- `0x180069eee`: `IMSISpecific\Default\SMS`
- `0x180069f76`: `IMSISpecific\Default\SMS`
- `0x18006a0aa`: `IMSISpecific\Default\SMS`
- `0x18006a0ce`: `IMSISpecific\Default\SMS`
- `0x180069fb9`: `IncompleteMsgDeliverySeconds`
- `0x180069f27`: `IMSISpecific\Default\SMS\3GPP`
- `0x180069fe2`: `IMSISpecific\Default\SMS\Encodings`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall SmsEncodingHelper::GetPSPerIMSIConfig_::_2_::_lambda_1_::operator()(void ***a1)
{
  _WORD *v2; // rdx
  unsigned __int64 v3; // r14
  unsigned __int64 v4; // r8
  char v5; // r15
  __int64 v6; // rdi
  __int64 v7; // rsi
  char v8; // al
  __int64 *v9; // rcx
  __int128 *p_Src; // rdx
  const unsigned __int16 *v11; // rdi
  const unsigned __int16 *v12; // r13
  HKEY v13; // rax
  const unsigned __int16 *v14; // rsi
  const unsigned __int16 *v15; // r12
  void **v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdx
  void **v19; // rax
  __int128 *v20; // rcx
  __int128 v21; // xmm6
  __int128 v22; // xmm7
  __int128 v23; // xmm8
  __int128 v24; // xmm9
  __int128 v25; // xmm10
  int v26; // edi
  _WORD *v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v31[2]; // [rsp+38h] [rbp-C8h] BYREF
  __m128i v32; // [rsp+48h] [rbp-B8h]
  __int128 Src; // [rsp+58h] [rbp-A8h] BYREF
  __m128i si128; // [rsp+68h] [rbp-98h]
  unsigned __int16 *v35[2]; // [rsp+78h] [rbp-88h] BYREF
  __m128i v36; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v37[2]; // [rsp+98h] [rbp-68h] BYREF
  __m128i v38; // [rsp+A8h] [rbp-58h]
  __int128 v39; // [rsp+B8h] [rbp-48h] BYREF
  __m128i v40; // [rsp+C8h] [rbp-38h]
  _OWORD v41[2]; // [rsp+D8h] [rbp-28h] BYREF

  v2 = **a1;
  *(_OWORD *)v31 = 0;
  v32 = 0;
  v3 = -1;
  v4 = -1;
  v5 = 0;
  do
    ++v4;
  while ( v2[v4] );
  std::wstring::_Construct<1,unsigned short const *>((char **)v31, v2, v4);
  v6 = qword_18008DA20;
  v7 = *(_QWORD *)(qword_18008DA20 + 8);
  HIDWORD(Src) = 0;
  while ( !*(_BYTE *)(v7 + 25) )
  {
    v8 = std::operator<<unsigned short>((const wchar_t *)(v7 + 32), (const wchar_t *)v31);
    if ( !v8 )
      v6 = v7;
    v9 = (__int64 *)(v7 + 16);
    if ( !v8 )
      v9 = (__int64 *)v7;
    v7 = *v9;
  }
  if ( *(_BYTE *)(v6 + 25)
    || (unsigned __int8)std::operator<<unsigned short>((const wchar_t *)v31, (const wchar_t *)(v6 + 32)) )
  {
    v6 = qword_18008DA20;
  }
  std::wstring::~wstring((char **)v31);
  if ( v6 == qword_18008DA20 )
  {
    Src = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Src) = 0;
    *(_OWORD *)v31 = 0;
    v32 = si128;
    LOWORD(v31[0]) = 0;
    v39 = 0;
    v40 = si128;
    LOWORD(v39) = 0;
    *(_OWORD *)v37 = 0;
    v38 = si128;
    LOWORD(v37[0]) = 0;
    *(_OWORD *)v35 = 0;
    v36 = si128;
    LOWORD(v35[0]) = 0;
    std::wstring::append(&Src, L"IMSISpecific\\");
    std::wstring::append(&Src, **a1);
    p_Src = &Src;
    if ( si128.m128i_i64[1] > 7uLL )
      p_Src = (__int128 *)Src;
    hKey = 0;
    if ( !(unsigned int)PersistentRegPathOpenKey(1, p_Src, 0, 131097, &hKey) )
    {
      RegCloseKey(hKey);
      v5 = 1;
    }
    std::wstring::append(&Src, L"\\SMS");
    v11 = (const unsigned __int16 *)&Src;
    if ( si128.m128i_i64[1] > 7uLL )
      v11 = (const unsigned __int16 *)Src;
    std::wstring::append(v31, L"IMSISpecific\\");
    std::wstring::append(v31, **a1);
    std::wstring::append(v31, L"\\SMS\\Encodings");
    v12 = (const unsigned __int16 *)v31;
    if ( v32.m128i_i64[1] > 7uLL )
      v12 = v31[0];
    std::wstring::append(&v39, L"IMSISpecific\\");
    std::wstring::append(&v39, **a1);
    std::wstring::append(&v39, L"\\SMS\\3GPP");
    v13 = (HKEY)&v39;
    if ( v40.m128i_i64[1] > 7uLL )
      v13 = (HKEY)v39;
    hKey = v13;
    std::wstring::append(v37, L"IMSISpecific\\");
    std::wstring::append(v37, **a1);
    std::wstring::append(v37, L"\\SMS\\3GPP\\IMS");
    v14 = (const unsigned __int16 *)v37;
    if ( v38.m128i_i64[1] > 7uLL )
      v14 = v37[0];
    std::wstring::append(v35, L"IMSISpecific\\");
    std::wstring::append(v35, **a1);
    std::wstring::append(v35, L"\\SMS\\3GPP2\\ErrorHandling");
    v15 = (const unsigned __int16 *)v35;
    if ( v36.m128i_i64[1] > 7uLL )
      v15 = v35[0];
    *((_DWORD *)*a1[1] + 1) = GetRegistryDwordValueIn2Subkeys(
                                v14,
                                L"IMSISpecific\\Default\\SMS\\3GPP\\IMS",
                                L"AttemptThresholdForIMS",
                                0xFFFFFFFF);
    v16 = a1[1];
    if ( *((_DWORD *)*v16 + 1) == -1 )
      *(_DWORD *)*v16 = 1;
    else
      *(_DWORD *)*a1[1] = GetRegistryDwordValueIn2Subkeys(
                            v14,
                            L"IMSISpecific\\Default\\SMS\\3GPP\\IMS",
                            L"RetryEnabled",
                            1u);
    *((_DWORD *)*a1[1] + 11) = GetRegistryDwordValueIn2Subkeys(
                                 v15,
                                 L"IMSISpecific\\Default\\SMS\\3GPP2\\ErrorHandling",
                                 L"UseReservedAsPermanent",
                                 0);
    *((_DWORD *)*a1[1] + 2) = GetRegistryDwordValueIn2Subkeys(
                                v11,
                                L"IMSISpecific\\Default\\SMS",
                                L"SmsFragmentLimit",
                                0x8Cu);
    v17 = (__int64)*a1[1];
    if ( (unsigned int)(*(_DWORD *)(v17 + 8) - 16) > 0x7C )
      *(_DWORD *)(v17 + 8) = 140;
    *((_DWORD *)*a1[1] + 3) = GetRegistryDwordValueIn2Subkeys(
                                v11,
                                L"IMSISpecific\\Default\\SMS",
                                L"SmsPageLimit",
                                0xFFu);
    v18 = (__int64)*a1[1];
    if ( (unsigned int)(*(_DWORD *)(v18 + 12) - 1) > 0xFE )
      *(_DWORD *)(v18 + 12) = 255;
    *((_DWORD *)*a1[1] + 7) = GetRegistryDwordValueIn2Subkeys(
                                (const unsigned __int16 *)hKey,
                                L"IMSISpecific\\Default\\SMS\\3GPP",
                                L"SmsUse16BitReferenceNumbers",
                                0);
    *((_DWORD *)*a1[1] + 4) = 0;
    *((_DWORD *)*a1[1] + 5) = 0;
    *((_DWORD *)*a1[1] + 6) = 1;
    *((_DWORD *)*a1[1] + 8) = GetRegistryDwordValueIn2Subkeys(
                                v11,
                                L"IMSISpecific\\Default\\SMS",
                                L"MessageExpirySeconds",
                                0x15180u);
    *((_DWORD *)*a1[1] + 9) = GetRegistryDwordValueIn2Subkeys(
                                v11,
                                L"IMSISpecific\\Default\\SMS",
                                L"AckExpirySeconds",
                                0x3Cu);
    *((_DWORD *)*a1[1] + 10) = GetRegistryDwordValueIn2Subkeys(
                                 v11,
                                 L"IMSISpecific\\Default\\SMS",
                                 L"IncompleteMsgDeliverySeconds",
                                 0x12Cu);
    *((_DWORD *)*a1[1] + 12) = GetRegistryDwordValueIn2Subkeys(
                                 v12,
                                 L"IMSISpecific\\Default\\SMS\\Encodings",
                                 L"GSM7BitEncodingPage",
                                 0xD6D8u);
    *((_DWORD *)*a1[1] + 13) = GetRegistryDwordValueIn2Subkeys(
                                 v12,
                                 L"IMSISpecific\\Default\\SMS\\Encodings",
                                 L"GSM8BitEncodingPage",
                                 0xFFFFFFFF);
    *((_DWORD *)*a1[1] + 14) = GetRegistryDwordValueIn2Subkeys(
                                 v12,
                                 L"IMSISpecific\\Default\\SMS\\Encodings",
                                 L"OctetEncodingPage",
                                 0x4E9Fu);
    *((_DWORD *)*a1[1] + 15) = GetRegistryDwordValueIn2Subkeys(
                                 v12,
                                 L"IMSISpecific\\Default\\SMS\\Encodings",
                                 L"UseASCII",
                                 0);
    *((_DWORD *)*a1[1] + 16) = GetRegistryDwordValueIn2Subkeys(
                                 v12,
                                 L"IMSISpecific\\Default\\SMS\\Encodings",
                                 L"UseKeyboardLanguage",
                                 0);
    *((_DWORD *)*a1[1] + 17) = GetRegistryDwordValueIn2Subkeys(
                                 v12,
                                 L"IMSISpecific\\Default\\SMS\\Encodings",
                                 L"SendUDHNLSS",
                                 0);
    *((_DWORD *)*a1[1] + 18) = GetRegistryDwordValueIn2Subkeys(v11, L"IMSISpecific\\Default\\SMS", L"DefaultMCC", 0);
    *((_DWORD *)*a1[1] + 19) = GetRegistryDwordValueIn2Subkeys(
                                 v11,
                                 L"IMSISpecific\\Default\\SMS",
                                 L"SprintFragmentInfoInBody",
                                 0);
    v19 = a1[1];
    if ( *((_DWORD *)*v19 + 19) )
    {
      *((_DWORD *)*v19 + 3) = 6;
      *((_DWORD *)*a1[1] + 20) = 6;
    }
    if ( v5 )
    {
      v20 = (__int128 *)*a1[1];
      v21 = *v20;
      v22 = v20[1];
      v23 = v20[2];
      v24 = v20[3];
      v25 = v20[4];
      v26 = *((_DWORD *)v20 + 20);
      v27 = **a1;
      memset(v41, 0, sizeof(v41));
      do
        ++v3;
      while ( v27[v3] );
      std::wstring::_Construct<1,unsigned short const *>((char **)v41, v27, v3);
      v29 = std::map<std::wstring,_SPerIMSIConfig>::operator[](v28, (__int64)v41);
      *(_OWORD *)v29 = v21;
      *(_OWORD *)(v29 + 16) = v22;
      *(_OWORD *)(v29 + 32) = v23;
      *(_OWORD *)(v29 + 48) = v24;
      *(_OWORD *)(v29 + 64) = v25;
      *(_DWORD *)(v29 + 80) = v26;
      std::wstring::~wstring((char **)v41);
    }
    std::wstring::~wstring((char **)v35);
    std::wstring::~wstring((char **)v37);
    std::wstring::~wstring((char **)&v39);
    std::wstring::~wstring((char **)v31);
    std::wstring::~wstring((char **)&Src);
  }
  else
  {
    *a1[1] = (void *)(v6 + 64);
  }
}

```

## disassembly

```asm
0x180069b5c  mov     rax, rsp
0x180069b5f  push    rbp
0x180069b60  push    rbx
0x180069b61  push    rsi
0x180069b62  push    rdi
0x180069b63  push    r12
0x180069b65  push    r13
0x180069b67  push    r14
0x180069b69  push    r15
0x180069b6b  lea     rbp, [rsp-58h]
0x180069b70  sub     rsp, 158h
0x180069b77  movaps  xmmword ptr [rax-58h], xmm6
0x180069b7b  movaps  xmmword ptr [rax-68h], xmm7
0x180069b7f  movaps  xmmword ptr [rax-78h], xmm8
0x180069b84  movaps  xmmword ptr [rax-88h], xmm9
0x180069b8c  movaps  xmmword ptr [rax-98h], xmm10
0x180069b94  mov     rax, cs:__security_cookie
0x180069b9b  xor     rax, rsp
0x180069b9e  mov     [rbp+90h+var_98], rax
0x180069ba2  mov     rbx, rcx
0x180069ba5  mov     rax, [rcx]
0x180069ba8  mov     rdx, [rax]
0x180069bab  xorps   xmm0, xmm0
0x180069bae  movups  xmmword ptr [rsp+190h+var_158], xmm0
0x180069bb3  xorps   xmm1, xmm1
0x180069bb6  movdqu  [rsp+190h+var_148], xmm1
0x180069bbc  or      r14, 0FFFFFFFFFFFFFFFFh
0x180069bc0  mov     r8, r14
0x180069bc3  xor     r15d, r15d
0x180069bc6  inc     r8
0x180069bc9  cmp     [rdx+r8*2], r15w
0x180069bce  jnz     short loc_180069BC6
0x180069bd0  lea     rcx, [rsp+190h+var_158]
0x180069bd5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180069bda  mov     rdi, cs:qword_18008DA20
0x180069be1  mov     rsi, [rdi+8]
0x180069be5  xor     eax, eax
0x180069be7  mov     dword ptr [rsp+190h+Src+0Ch], eax
0x180069beb  jmp     short loc_180069C0C
0x180069bed  lea     rcx, [rsi+20h]
0x180069bf1  lea     rdx, [rsp+190h+var_158]
0x180069bf6  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180069bfb  test    al, al
0x180069bfd  cmovz   rdi, rsi
0x180069c01  lea     rcx, [rsi+10h]
0x180069c05  cmovz   rcx, rsi
0x180069c09  mov     rsi, [rcx]
0x180069c0c  cmp     [rsi+19h], r15b
0x180069c10  jz      short loc_180069BED
0x180069c12  cmp     [rdi+19h], r15b
0x180069c16  jnz     short loc_180069C2A
0x180069c18  lea     rdx, [rdi+20h]
0x180069c1c  lea     rcx, [rsp+190h+var_158]
0x180069c21  call    ??$?MGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator<<ushort>(std::wstring const &,std::wstring const &)
0x180069c26  test    al, al
0x180069c28  jz      short loc_180069C31
0x180069c2a  mov     rdi, cs:qword_18008DA20
0x180069c31  lea     rcx, [rsp+190h+var_158]; void *
0x180069c36  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180069c3b  cmp     rdi, cs:qword_18008DA20
0x180069c42  jnz     loc_18006A1B9
0x180069c48  xorps   xmm0, xmm0
0x180069c4b  movups  [rsp+190h+Src], xmm0
0x180069c50  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180069c58  movdqu  [rsp+190h+var_128], xmm1
0x180069c5e  mov     word ptr [rsp+190h+Src], r15w
0x180069c64  movups  xmmword ptr [rsp+190h+var_158], xmm0
0x180069c69  movdqu  [rsp+190h+var_148], xmm1
0x180069c6f  mov     word ptr [rsp+190h+var_158], r15w
0x180069c75  movups  [rbp+90h+var_D8], xmm0
0x180069c79  movdqu  [rbp+90h+var_C8], xmm1
0x180069c7e  mov     word ptr [rbp+90h+var_D8], r15w
0x180069c83  movups  xmmword ptr [rbp+90h+var_F8], xmm0
0x180069c87  movdqu  [rbp+90h+var_E8], xmm1
0x180069c8c  mov     word ptr [rbp+90h+var_F8], r15w
0x180069c91  movups  xmmword ptr [rsp+190h+var_118], xmm0
0x180069c96  movdqu  [rbp+90h+var_108], xmm1
0x180069c9b  mov     word ptr [rsp+190h+var_118], r15w
0x180069ca1  lea     r12, aImsispecific; "IMSISpecific\\"
0x180069ca8  mov     rdx, r12; void *
0x180069cab  lea     rcx, [rsp+190h+Src]; Src
0x180069cb0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180069cb5  mov     rdx, [rbx]
0x180069cb8  mov     rdx, [rdx]; void *
0x180069cbb  lea     rcx, [rsp+190h+Src]; Src
0x180069cc0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180069cc5  lea     rdx, [rsp+190h+Src]
0x180069cca  cmp     qword ptr [rsp+190h+var_128+8], 7
0x180069cd0  cmova   rdx, qword ptr [rsp+190h+Src]
0x180069cd6  mov     [rsp+190h+hKey], r15
0x180069cdb  lea     rax, [rsp+190h+hKey]
0x180069ce0  mov     [rsp+190h+var_170], rax
0x180069ce5  mov     r9d, 20019h
0x180069ceb  xor     r8d, r8d
0x180069cee  lea     ecx, [r8+1]
0x180069cf2  call    cs:__imp_PersistentRegPathOpenKey
0x180069cf8  test    eax, eax
0x180069cfa  jnz     short loc_180069D0A
0x180069cfc  mov     rcx, [rsp+190h+hKey]; hKey
0x180069d01  call    cs:__imp_RegCloseKey
0x180069d07  mov     r15b, 1
0x180069d0a  lea     rdx, aSms; "\\SMS"
0x180069d11  lea     rcx, [rsp+190h+Src]; Src
0x180069d16  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180069d1b  lea     rdi, [rsp+190h+Src]
0x180069d20  cmp     qword ptr [rsp+190h+var_128+8], 7
0x180069d26  cmova   rdi, qword ptr [rsp+190h+Src]
0x180069d2c  mov     rdx, r12; void *
0x180069d2f  lea     rcx, [rsp+190h+var_158]; Src
0x180069d34  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180069d39  mov     rdx, [rbx]
0x180069d3c  mov     rdx, [rdx]; void *
0x180069d3f  lea     rcx, [rsp+190h+var_158]; Src
0x180069d44  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180069d49  lea     rdx, aSmsEncodings; "\\SMS\\Encodings"
0x180069d50  lea     rcx, [rsp+190h+var_158]; Src
0x180069d55  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180069d5a  lea     r13, [rsp+190h+var_158]
0x180069d5f  cmp     qword ptr [rsp+190h+var_148+8], 7
0x180069d65  cmova   r13, [rsp+190h+var_158]
0x180069d6b  mov     rdx, r12; void *
0x180069d6e  lea     rcx, [rbp+90h+var_D8]; Src
0x180069d72  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180069d77  mov     rdx, [rbx]
0x180069d7a  mov     rdx, [rdx]; void *
0x180069d7d  lea     rcx, [rbp+90h+var_D8]; Src
0x180069d81  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180069d86  lea     rdx, aSms3gpp; "\\SMS\\3GPP"
0x180069d8d  lea     rcx, [rbp+90h+var_D8]; Src
0x180069d91  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180069d96  lea     rax, [rbp+90h+var_D8]
0x180069d9a  cmp     qword ptr [rbp+90h+var_C8+8], 7
0x180069d9f  cmova   rax, qword ptr [rbp+90h+var_D8]
0x180069da4  mov     [rsp+190h+hKey], rax
0x180069da9  mov     rdx, r12; void *
0x180069dac  lea     rcx, [rbp+90h+var_F8]; Src
0x180069db0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180069db5  mov     rdx, [rbx]
0x180069db8  mov     rdx, [rdx]; void *
0x180069dbb  lea     rcx, [rbp+90h+var_F8]; Src
0x180069dbf  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180069dc4  lea     rdx, aSms3gppIms; "\\SMS\\3GPP\\IMS"
0x180069dcb  lea     rcx, [rbp+90h+var_F8]; Src
0x180069dcf  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180069dd4  lea     rsi, [rbp+90h+var_F8]
0x180069dd8  cmp     qword ptr [rbp+90h+var_E8+8], 7
0x180069ddd  cmova   rsi, [rbp+90h+var_F8]
0x180069de2  mov     rdx, r12; void *
0x180069de5  lea     rcx, [rsp+190h+var_118]; Src
0x180069dea  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180069def  mov     rdx, [rbx]
0x180069df2  mov     rdx, [rdx]; void *
0x180069df5  lea     rcx, [rsp+190h+var_118]; Src
0x180069dfa  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180069dff  lea     rdx, aSms3gpp2Errorh; "\\SMS\\3GPP2\\ErrorHandling"
0x180069e06  lea     rcx, [rsp+190h+var_118]; Src
0x180069e0b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180069e10  lea     r12, [rsp+190h+var_118]
0x180069e15  cmp     qword ptr [rbp+90h+var_108+8], 7
0x180069e1a  cmova   r12, [rsp+190h+var_118]
0x180069e20  or      r9d, 0FFFFFFFFh; unsigned int
0x180069e24  lea     r8, aAttemptthresho; "AttemptThresholdForIMS"
0x180069e2b  lea     rdx, aImsispecificDe_3; "IMSISpecific\\Default\\SMS\\3GPP\\IMS"
0x180069e32  mov     rcx, rsi; unsigned __int16 *
0x180069e35  call    ?GetRegistryDwordValueIn2Subkeys@@YAKPEBG00K@Z; GetRegistryDwordValueIn2Subkeys(ushort const *,ushort const *,ushort const *,ulong)
0x180069e3a  mov     r8, [rbx+8]
0x180069e3e  mov     r9, [r8]
0x180069e41  mov     [r9+4], eax
0x180069e45  mov     rax, [rbx+8]
0x180069e49  mov     rcx, [rax]
0x180069e4c  cmp     dword ptr [rcx+4], 0FFFFFFFFh
0x180069e50  jz      short loc_180069E79
0x180069e52  mov     r9d, 1; unsigned int
0x180069e58  lea     r8, aRetryenabled; "RetryEnabled"
0x180069e5f  lea     rdx, aImsispecificDe_3; "IMSISpecific\\Default\\SMS\\3GPP\\IMS"
0x180069e66  mov     rcx, rsi; unsigned __int16 *
0x180069e69  call    ?GetRegistryDwordValueIn2Subkeys@@YAKPEBG00K@Z; GetRegistryDwordValueIn2Subkeys(ushort const *,ushort const *,ushort const *,ulong)
0x180069e6e  mov     rcx, [rbx+8]
0x180069e72  mov     rdx, [rcx]
0x180069e75  mov     [rdx], eax
0x180069e77  jmp     short loc_180069E7F
0x180069e79  mov     dword ptr [rcx], 1
0x180069e7f  xor     r9d, r9d; unsigned int
0x180069e82  lea     r8, aUsereservedasp; "UseReservedAsPermanent"
0x180069e89  lea     rdx, aImsispecificDe_2; "IMSISpecific\\Default\\SMS\\3GPP2\\Erro"...
0x180069e90  mov     rcx, r12; unsigned __int16 *
0x180069e93  call    ?GetRegistryDwordValueIn2Subkeys@@YAKPEBG00K@Z; GetRegistryDwordValueIn2Subkeys(ushort const *,ushort const *,ushort const *,ulong)
0x180069e98  mov     rcx, [rbx+8]
0x180069e9c  mov     rdx, [rcx]
0x180069e9f  mov     [rdx+2Ch], eax
0x180069ea2  mov     esi, 8Ch
0x180069ea7  mov     r9d, esi; unsigned int
0x180069eaa  lea     r8, aSmsfragmentlim; "SmsFragmentLimit"
0x180069eb1  lea     rdx, aImsispecificDe; "IMSISpecific\\Default\\SMS"
0x180069eb8  mov     rcx, rdi; unsigned __int16 *
0x180069ebb  call    ?GetRegistryDwordValueIn2Subkeys@@YAKPEBG00K@Z; GetRegistryDwordValueIn2Subkeys(ushort const *,ushort const *,ushort const *,ulong)
0x180069ec0  mov     rcx, [rbx+8]
0x180069ec4  mov     rdx, [rcx]
0x180069ec7  mov     [rdx+8], eax
0x180069eca  mov     rax, [rbx+8]
0x180069ece  mov     rcx, [rax]
0x180069ed1  mov     eax, [rcx+8]
0x180069ed4  sub     eax, 10h
0x180069ed7  cmp     eax, 7Ch ; '|'
0x180069eda  jbe     short loc_180069EDF
0x180069edc  mov     [rcx+8], esi
0x180069edf  mov     esi, 0FFh
0x180069ee4  mov     r9d, esi; unsigned int
0x180069ee7  lea     r8, aSmspagelimit; "SmsPageLimit"
0x180069eee  lea     rdx, aImsispecificDe; "IMSISpecific\\Default\\SMS"
0x180069ef5  mov     rcx, rdi; unsigned __int16 *
0x180069ef8  call    ?GetRegistryDwordValueIn2Subkeys@@YAKPEBG00K@Z; GetRegistryDwordValueIn2Subkeys(ushort const *,ushort const *,ushort const *,ulong)
0x180069efd  mov     rcx, [rbx+8]
0x180069f01  mov     rdx, [rcx]
0x180069f04  mov     [rdx+0Ch], eax
0x180069f07  mov     rax, [rbx+8]
0x180069f0b  mov     rdx, [rax]
0x180069f0e  mov     eax, [rdx+0Ch]
0x180069f11  dec     eax
0x180069f13  cmp     eax, 0FEh
0x180069f18  jbe     short loc_180069F1D
0x180069f1a  mov     [rdx+0Ch], esi
0x180069f1d  xor     r9d, r9d; unsigned int
0x180069f20  lea     r8, aSmsuse16bitref; "SmsUse16BitReferenceNumbers"
0x180069f27  lea     rdx, aImsispecificDe_0; "IMSISpecific\\Default\\SMS\\3GPP"
0x180069f2e  mov     rcx, [rsp+190h+hKey]; unsigned __int16 *
0x180069f33  call    ?GetRegistryDwordValueIn2Subkeys@@YAKPEBG00K@Z; GetRegistryDwordValueIn2Subkeys(ushort const *,ushort const *,ushort const *,ulong)
0x180069f38  mov     rcx, [rbx+8]
0x180069f3c  mov     rdx, [rcx]
0x180069f3f  mov     [rdx+1Ch], eax
0x180069f42  mov     rax, [rbx+8]
0x180069f46  mov     rcx, [rax]
0x180069f49  xor     r12d, r12d
0x180069f4c  mov     [rcx+10h], r12d
0x180069f50  mov     rax, [rbx+8]
0x180069f54  mov     rcx, [rax]
0x180069f57  mov     [rcx+14h], r12d
0x180069f5b  mov     rax, [rbx+8]
0x180069f5f  mov     rcx, [rax]
0x180069f62  mov     dword ptr [rcx+18h], 1
0x180069f69  mov     r9d, 15180h; unsigned int
0x180069f6f  lea     r8, aMessageexpirys; "MessageExpirySeconds"
0x180069f76  lea     rsi, aImsispecificDe; "IMSISpecific\\Default\\SMS"
0x180069f7d  mov     rdx, rsi; unsigned __int16 *
0x180069f80  mov     rcx, rdi; unsigned __int16 *
0x180069f83  call    ?GetRegistryDwordValueIn2Subkeys@@YAKPEBG00K@Z; GetRegistryDwordValueIn2Subkeys(ushort const *,ushort const *,ushort const *,ulong)
0x180069f88  mov     rcx, [rbx+8]
0x180069f8c  mov     rdx, [rcx]
0x180069f8f  mov     [rdx+20h], eax
0x180069f92  lea     r9d, [r12+3Ch]; unsigned int
0x180069f97  lea     r8, aAckexpirysecon; "AckExpirySeconds"
0x180069f9e  mov     rdx, rsi; unsigned __int16 *
0x180069fa1  mov     rcx, rdi; unsigned __int16 *
0x180069fa4  call    ?GetRegistryDwordValueIn2Subkeys@@YAKPEBG00K@Z; GetRegistryDwordValueIn2Subkeys(ushort const *,ushort const *,ushort const *,ulong)
0x180069fa9  mov     rcx, [rbx+8]
0x180069fad  mov     rdx, [rcx]
0x180069fb0  mov     [rdx+24h], eax
0x180069fb3  mov     r9d, 12Ch; unsigned int
0x180069fb9  lea     r8, aIncompletemsgd; "IncompleteMsgDeliverySeconds"
0x180069fc0  mov     rdx, rsi; unsigned __int16 *
0x180069fc3  mov     rcx, rdi; unsigned __int16 *
0x180069fc6  call    ?GetRegistryDwordValueIn2Subkeys@@YAKPEBG00K@Z; GetRegistryDwordValueIn2Subkeys(ushort const *,ushort const *,ushort const *,ulong)
0x180069fcb  mov     rcx, [rbx+8]
0x180069fcf  mov     rdx, [rcx]
0x180069fd2  mov     [rdx+28h], eax
0x180069fd5  mov     r9d, 0D6D8h; unsigned int
0x180069fdb  lea     r8, aGsm7bitencodin; "GSM7BitEncodingPage"
0x180069fe2  lea     rsi, aImsispecificDe_1; "IMSISpecific\\Default\\SMS\\Encodings"
0x180069fe9  mov     rdx, rsi; unsigned __int16 *
0x180069fec  mov     rcx, r13; unsigned __int16 *
0x180069fef  call    ?GetRegistryDwordValueIn2Subkeys@@YAKPEBG00K@Z; GetRegistryDwordValueIn2Subkeys(ushort const *,ushort const *,ushort const *,ulong)
0x180069ff4  mov     rcx, [rbx+8]
0x180069ff8  mov     rdx, [rcx]
0x180069ffb  mov     [rdx+30h], eax
0x180069ffe  or      r9d, 0FFFFFFFFh; unsigned int
0x18006a002  lea     r8, aGsm8bitencodin; "GSM8BitEncodingPage"
0x18006a009  mov     rdx, rsi; unsigned __int16 *
0x18006a00c  mov     rcx, r13; unsigned __int16 *
0x18006a00f  call    ?GetRegistryDwordValueIn2Subkeys@@YAKPEBG00K@Z; GetRegistryDwordValueIn2Subkeys(ushort const *,ushort const *,ushort const *,ulong)
0x18006a014  mov     rcx, [rbx+8]
0x18006a018  mov     rdx, [rcx]
0x18006a01b  mov     [rdx+34h], eax
0x18006a01e  mov     r9d, 4E9Fh; unsigned int
0x18006a024  lea     r8, aOctetencodingp; "OctetEncodingPage"
0x18006a02b  mov     rdx, rsi; unsigned __int16 *
0x18006a02e  mov     rcx, r13; unsigned __int16 *
0x18006a031  call    ?GetRegistryDwordValueIn2Subkeys@@YAKPEBG00K@Z; GetRegistryDwordValueIn2Subkeys(ushort const *,ushort const *,ushort const *,ulong)
0x18006a036  mov     rcx, [rbx+8]
0x18006a03a  mov     rdx, [rcx]
0x18006a03d  mov     [rdx+38h], eax
0x18006a040  xor     r9d, r9d; unsigned int
0x18006a043  lea     r8, aUseascii; "UseASCII"
0x18006a04a  mov     rdx, rsi; unsigned __int16 *
0x18006a04d  mov     rcx, r13; unsigned __int16 *
0x18006a050  call    ?GetRegistryDwordValueIn2Subkeys@@YAKPEBG00K@Z; GetRegistryDwordValueIn2Subkeys(ushort const *,ushort const *,ushort const *,ulong)
0x18006a055  mov     r8, [rbx+8]
0x18006a059  mov     r9, [r8]
0x18006a05c  mov     [r9+3Ch], eax
0x18006a060  xor     r9d, r9d; unsigned int
0x18006a063  lea     r8, aUsekeyboardlan; "UseKeyboardLanguage"
  ... truncated ...
```
