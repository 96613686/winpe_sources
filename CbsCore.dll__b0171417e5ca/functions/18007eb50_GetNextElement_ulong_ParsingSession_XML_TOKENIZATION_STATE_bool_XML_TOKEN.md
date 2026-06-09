# GetNextElement(ulong,ParsingSession *,_XML_TOKENIZATION_STATE *,bool *,_XML_TOKEN *)

- ea: `0x18007eb50`
- end: `0x18007f583`
- name: `?GetNextElement@@YAJKPEAUParsingSession@@PEAU_XML_TOKENIZATION_STATE@@PEA_NPEAU_XML_TOKEN@@@Z`
- size: `2611`
- prototype: `__int64 __fastcall(unsigned int, struct ParsingSession *, struct _XML_TOKENIZATION_STATE *, bool *, struct _XML_TOKEN *)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x180078c9c`
- `0x18007f590`
- `0x180089214`

## callees

- `0x18007c660`
- `0x18007eb50`
- `0x18007f9b0`
- `0x180080c70`
- `0x1800812d0`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x1800ec854`
- `0x180205e4c`
- `0x1802cf7d8`

## string_xrefs

- `0x18007ecf4`: `Failed to expect token`
- `0x18007f084`: `Failed to expect token`
- `0x18007f244`: `Failed to expect token`
- `0x18007ec8e`: `onecore\base\cbs\parser\token.cpp`
- `0x18007ed38`: `onecore\base\cbs\parser\token.cpp`
- `0x18007edcc`: `onecore\base\cbs\parser\token.cpp`
- `0x18007ee5e`: `onecore\base\cbs\parser\token.cpp`
- `0x18007ef3f`: `onecore\base\cbs\parser\token.cpp`
- `0x18007efcc`: `onecore\base\cbs\parser\token.cpp`
- `0x18007f03d`: `onecore\base\cbs\parser\token.cpp`
- `0x18007f0c8`: `onecore\base\cbs\parser\token.cpp`
- `0x18007f14f`: `onecore\base\cbs\parser\token.cpp`
- `0x18007f288`: `onecore\base\cbs\parser\token.cpp`
- `0x18007f2fa`: `onecore\base\cbs\parser\token.cpp`
- `0x18007f36f`: `onecore\base\cbs\parser\token.cpp`
- `0x18007f3fa`: `onecore\base\cbs\parser\token.cpp`
- `0x18007f472`: `onecore\base\cbs\parser\token.cpp`
- `0x18007f4ea`: `onecore\base\cbs\parser\token.cpp`
- `0x18007f562`: `onecore\base\cbs\parser\token.cpp`
- `0x18007f32b`: `Failed to get next token`
- `0x18007f2b6`: `Mismatch between open element and close element`
- `0x18007eefb`: `No matching open element for the close tag`
- `0x18007f10b`: `No matching open element for the close tag`
- `0x18007eff9`: `Element in unrecognized namespace closed without having been opened.`

## pseudocode

```c
__int64 __fastcall GetNextElement(
        char a1,
        struct ParsingSession *a2,
        struct _XML_TOKENIZATION_STATE *a3,
        bool *a4,
        struct _XML_TOKEN *a5)
{
  int NextToken; // r14d
  int v10; // eax
  wil::details::in1diag3 *v11; // rcx
  const char *v12; // r9
  __int64 v13; // rdx
  __int64 result; // rax
  int v15; // eax
  unsigned int v16; // esi
  char *v17; // r14
  __int64 v18; // rsi
  int RoomAt; // eax
  unsigned int v20; // ebx
  __int64 v21; // rax
  __int64 v22; // rsi
  __int64 v23; // rcx
  _BYTE *v24; // rax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rdx
  __m128i *v28; // rcx
  __m128i v29; // xmm7
  __m128i v30; // xmm6
  __int64 v31; // rcx
  _BYTE *v32; // rax
  size_t v33; // r8
  int v34; // eax
  unsigned int v35; // ebx
  int v36; // [rsp+20h] [rbp-41h]
  bool v37; // [rsp+30h] [rbp-31h] BYREF
  int v38[2]; // [rsp+38h] [rbp-29h] BYREF
  int v39; // [rsp+40h] [rbp-21h] BYREF
  int v40[2]; // [rsp+48h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+57h]

  v37 = 0;
  if ( a2 )
  {
    if ( a3 )
    {
      if ( a4 )
      {
        if ( a5 )
        {
          while ( 1 )
          {
            *a4 = 0;
            if ( *(_BYTE *)a2 )
            {
              *a4 = *((_BYTE *)a2 + 1);
              result = 0;
              *(_OWORD *)a5 = *(_OWORD *)((char *)a2 + 8);
              *((_OWORD *)a5 + 1) = *(_OWORD *)((char *)a2 + 24);
              *(_BYTE *)a2 = 0;
              return result;
            }
            NextToken = GetNextToken(a3, a5);
            if ( NextToken < 0 )
            {
              v40[0] = NextToken;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get next token");
                *(_QWORD *)v38 = v40;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)v38);
              }
              v11 = retaddr;
              v12 = (const char *)(unsigned int)NextToken;
              v13 = 267;
              goto LABEL_16;
            }
            v10 = *((_DWORD *)a5 + 6);
            if ( v10 == 34 )
              break;
            if ( v10 == 27 )
            {
              if ( *((_QWORD *)a2 + 63) )
              {
                --*((_QWORD *)a2 + 63);
                v23 = 32;
                v24 = (_BYTE *)(*((_QWORD *)a2 + 65) + 32LL * *((_QWORD *)a2 + 63));
                do
                {
                  *v24++ = 0;
                  --v23;
                }
                while ( v23 );
                goto LABEL_34;
              }
              v39 = -2146498547;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"No matching open element for the close tag");
                *(_QWORD *)v40 = &v39;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)v40);
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x135,
                (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                (const char *)0x800F080DLL,
                v36);
              return 2148468749LL;
            }
            NextToken = ProcessNamespacePrefix(a2, a3, 0, &v37);
            if ( NextToken < 0 )
            {
              v39 = NextToken;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to process namespace prefix.");
                *(_QWORD *)v40 = &v39;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)v40);
              }
              v11 = retaddr;
              v12 = (const char *)(unsigned int)NextToken;
              v13 = 317;
              goto LABEL_16;
            }
            if ( v37 )
            {
              v15 = ExpectToken(a3, 6, a5);
              v16 = v15;
              if ( v15 < 0 )
              {
                v39 = v15;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to expect token");
                  *(_QWORD *)v40 = &v39;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)v40);
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x140,
                  (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                  (const char *)v16,
                  v36);
                return v16;
              }
              if ( (a1 & 2) == 0 )
              {
                v17 = (char *)a2 + 480;
                v18 = *((_QWORD *)a2 + 63);
                RoomAt = CCbsArrayBase<_XML_TOKEN,CCbsArray<_XML_TOKEN>>::MakeRoomAt((char *)a2 + 480, v18);
                v20 = RoomAt;
                if ( RoomAt < 0 )
                {
                  v39 = RoomAt;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      (__int64)LogAdapter::g_Logger,
                      0,
                      3,
                      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to push element.");
                    *(_QWORD *)v40 = &v39;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (__int64)LogAdapter::g_Logger,
                      1,
                      3,
                      (__int64)": {}",
                      (__int64)v40);
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x146,
                    (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                    (const char *)v20,
                    v36);
                  return v20;
                }
                v21 = *((_QWORD *)v17 + 5);
                v22 = 32 * v18;
                *(_OWORD *)(v22 + v21) = *(_OWORD *)a5;
                *(_OWORD *)(v22 + v21 + 16) = *((_OWORD *)a5 + 1);
              }
              *a4 = 0;
              return 0;
            }
            NextToken = ProcessExtensionBlock(a2, a3);
            if ( NextToken < 0 )
            {
              v39 = NextToken;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to processs extenstion block");
                *(_QWORD *)v40 = &v39;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)v40);
              }
              v11 = retaddr;
              v12 = (const char *)(unsigned int)NextToken;
              v13 = 333;
LABEL_16:
              wil::details::in1diag3::Return_Hr(
                v11,
                (void *)v13,
                (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                v12,
                v36);
              return (unsigned int)NextToken;
            }
            a1 = 0;
            v37 = 0;
          }
          v25 = ProcessNamespacePrefix(a2, a3, 0, &v37);
          NextToken = v25;
          if ( v25 < 0 )
          {
            v39 = v25;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to process namespace prefix.");
              *(_QWORD *)v38 = &v39;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v38);
            }
            v11 = retaddr;
            v12 = (const char *)(unsigned int)NextToken;
            v13 = 276;
            goto LABEL_16;
          }
          if ( v37 )
          {
            v26 = ExpectToken(a3, 35, a5);
            NextToken = v26;
            if ( v26 < 0 )
            {
              v40[0] = v26;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to expect token");
                *(_QWORD *)v38 = v40;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)v38);
              }
              v11 = retaddr;
              v12 = (const char *)(unsigned int)NextToken;
              v13 = 286;
              goto LABEL_16;
            }
            v27 = *((_QWORD *)a2 + 63);
            if ( v27 )
            {
              v28 = (__m128i *)(*((_QWORD *)a2 + 65) + 32 * (v27 - 1));
              v29 = *v28;
              v30 = v28[1];
              --*((_QWORD *)a2 + 63);
              v31 = 32;
              v32 = (_BYTE *)(*((_QWORD *)a2 + 65) + 32LL * *((_QWORD *)a2 + 63));
              do
              {
                *v32++ = 0;
                --v31;
              }
              while ( v31 );
              if ( _mm_cvtsi128_si32(_mm_srli_si128(v30, 8)) == 6
                && *((_DWORD *)a5 + 6) == 35
                && (v33 = _mm_srli_si128(v29, 8).m128i_u64[0], v33 == *((_QWORD *)a5 + 1))
                && !o__strnicmp_0((const char *)v29.m128i_i64[0], *(const char **)a5, v33) )
              {
                v34 = ExpectToken(a3, 37, a5);
                v35 = v34;
                if ( v34 >= 0 )
                {
LABEL_34:
                  *a4 = 1;
                  return 0;
                }
                v40[0] = v34;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to expect token");
                  *(_QWORD *)v38 = v40;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)v38);
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x12D,
                  (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                  (const char *)v35,
                  v36);
                return v35;
              }
              else
              {
                v39 = -2146498547;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    (__int64)LogAdapter::g_Logger,
                    0,
                    3,
                    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Mismatch between open element and close element");
                  *(_QWORD *)v38 = &v39;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (__int64)LogAdapter::g_Logger,
                    1,
                    3,
                    (__int64)": {}",
                    (__int64)v38);
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x12A,
                  (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                  (const char *)0x800F080DLL,
                  v36);
                return 2148468749LL;
              }
            }
            else
            {
              v39 = -2146498547;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  (__int64)LogAdapter::g_Logger,
                  0,
                  3,
                  (struct Windows::Rtl::IRtlFormattedOutputStream *)"No matching open element for the close tag");
                *(_QWORD *)v38 = &v39;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (__int64)LogAdapter::g_Logger,
                  1,
                  3,
                  (__int64)": {}",
                  (__int64)v38);
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x126,
                (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
                (const char *)0x800F080DLL,
                v36);
              return 2148468749LL;
            }
          }
          else
          {
            v40[0] = -2146498547;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"Element in unrecognized namespace closed without having been opened.");
              *(_QWORD *)v38 = v40;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)v38);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x11B,
              (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
              (const char *)0x800F080DLL,
              v36);
            return 2148468749LL;
          }
        }
        else
        {
          v40[0] = -2147467261;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"No next result specified");
            *(_QWORD *)v38 = v40;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v38);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xFF,
            (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
            (const char *)0x80004003LL,
            v36);
          return 2147500035LL;
        }
      }
      else
      {
        v40[0] = -2147467261;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"No end of element result specified");
          *(_QWORD *)v38 = v40;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v38);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFE,
          (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
          (const char *)0x80004003LL,
          v36);
        return 2147500035LL;
      }
    }
    else
    {
      v40[0] = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"No state specified");
        *(_QWORD *)v38 = v40;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v38);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFD,
        (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
        (const char *)0x80070057LL,
        v36);
      return 2147942487LL;
    }
  }
  else
  {
    v40[0] = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No parsing session specified");
      *(_QWORD *)v38 = v40;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v38);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFC,
      (unsigned int)"onecore\\base\\cbs\\parser\\token.cpp",
      (const char *)0x80070057LL,
      v36);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18007eb50  push    rbp
0x18007eb52  push    rbx
0x18007eb53  push    rsi
0x18007eb54  push    rdi
0x18007eb55  push    r12
0x18007eb57  push    r15
0x18007eb59  lea     rbp, [rsp-27h]
0x18007eb5e  sub     rsp, 88h
0x18007eb65  mov     rax, cs:__security_cookie
0x18007eb6c  xor     rax, rsp
0x18007eb6f  mov     [rbp+4Fh+var_60], rax
0x18007eb73  mov     rdi, [rbp+4Fh+arg_20]
0x18007eb77  mov     r15, r9
0x18007eb7a  mov     [rbp+4Fh+var_80], 0
0x18007eb7e  mov     rsi, r8
0x18007eb81  mov     rbx, rdx
0x18007eb84  mov     r12d, ecx
0x18007eb87  test    rdx, rdx
0x18007eb8a  jz      loc_18007F50B
0x18007eb90  test    r8, r8
0x18007eb93  jz      loc_18007F493
0x18007eb99  test    r9, r9
0x18007eb9c  jz      loc_18007F41B
0x18007eba2  test    rdi, rdi
0x18007eba5  jz      loc_18007F3A3
0x18007ebab  mov     [rsp+0B0h+var_30], r14
0x18007ebb3  movaps  [rsp+0B0h+var_50], xmm7
0x18007ebb8  nop     dword ptr [rax+rax+00000000h]
0x18007ebc0  mov     byte ptr [r15], 0
0x18007ebc4  cmp     byte ptr [rbx], 0
0x18007ebc7  jnz     loc_18007F383
0x18007ebcd  mov     rdx, rdi; struct _XML_TOKEN *
0x18007ebd0  mov     rcx, rsi; struct _XML_TOKENIZATION_STATE *
0x18007ebd3  call    ?GetNextToken@@YAJPEAU_XML_TOKENIZATION_STATE@@PEAU_XML_TOKEN@@@Z; GetNextToken(_XML_TOKENIZATION_STATE *,_XML_TOKEN *)
0x18007ebd8  mov     r14d, eax
0x18007ebdb  test    eax, eax
0x18007ebdd  js      loc_18007F31B
0x18007ebe3  mov     eax, [rdi+18h]
0x18007ebe6  cmp     eax, 22h ; '"'
0x18007ebe9  jz      loc_18007EF60
0x18007ebef  cmp     eax, 1Bh
0x18007ebf2  jz      loc_18007EE72
0x18007ebf8  lea     r9, [rbp+4Fh+var_80]; bool *
0x18007ebfc  xor     r8d, r8d; bool
0x18007ebff  mov     rdx, rsi; struct _XML_TOKENIZATION_STATE *
0x18007ec02  mov     rcx, rbx; struct ParsingSession *
0x18007ec05  call    ?ProcessNamespacePrefix@@YAJPEAUParsingSession@@PEAU_XML_TOKENIZATION_STATE@@_NPEA_N@Z; ProcessNamespacePrefix(ParsingSession *,_XML_TOKENIZATION_STATE *,bool,bool *)
0x18007ec0a  mov     r14d, eax
0x18007ec0d  test    eax, eax
0x18007ec0f  js      loc_18007EE0A
0x18007ec15  cmp     [rbp+4Fh+var_80], 0
0x18007ec19  jnz     loc_18007ECCF
0x18007ec1f  mov     rdx, rsi; struct _XML_TOKENIZATION_STATE *
0x18007ec22  mov     rcx, rbx; struct ParsingSession *
0x18007ec25  call    ?ProcessExtensionBlock@@YAJPEAUParsingSession@@PEAU_XML_TOKENIZATION_STATE@@@Z; ProcessExtensionBlock(ParsingSession *,_XML_TOKENIZATION_STATE *)
0x18007ec2a  mov     r14d, eax
0x18007ec2d  test    eax, eax
0x18007ec2f  js      short loc_18007EC3A
0x18007ec31  xor     r12d, r12d
0x18007ec34  mov     [rbp+4Fh+var_80], r12b
0x18007ec38  jmp     short loc_18007EBC0
0x18007ec3a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007ec41  mov     [rbp+4Fh+var_70], r14d
0x18007ec45  test    rcx, rcx
0x18007ec48  jz      short loc_18007EC8A
0x18007ec4a  lea     r9, aFailedToProces_55; "Failed to processs extenstion block"
0x18007ec51  xor     edx, edx
0x18007ec53  mov     r8d, 3
0x18007ec59  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007ec5e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007ec65  lea     rax, [rbp+4Fh+var_70]
0x18007ec69  mov     qword ptr [rbp+4Fh+var_68], rax
0x18007ec6d  lea     r9, asc_1802EE7AC; ": {}"
0x18007ec74  lea     rax, [rbp+4Fh+var_68]
0x18007ec78  mov     r8d, 3
0x18007ec7e  mov     dl, 1
0x18007ec80  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x18007ec85  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007ec8a  mov     rcx, [rbp+57h]; this
0x18007ec8e  lea     r8, aOnecoreBaseCbs_62; "onecore\\base\\cbs\\parser\\token.cpp"
0x18007ec95  mov     r9d, r14d; char *
0x18007ec98  mov     edx, 14Dh; void *
0x18007ec9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007eca2  mov     eax, r14d
0x18007eca5  mov     r14, [rsp+0B0h+var_30]
0x18007ecad  movaps  xmm7, [rsp+0B0h+var_50]
0x18007ecb2  mov     rcx, [rbp+4Fh+var_60]
0x18007ecb6  xor     rcx, rsp; StackCookie
0x18007ecb9  call    __security_check_cookie
0x18007ecbe  add     rsp, 88h
0x18007ecc5  pop     r15
0x18007ecc7  pop     r12
0x18007ecc9  pop     rdi
0x18007ecca  pop     rsi
0x18007eccb  pop     rbx
0x18007eccc  pop     rbp
0x18007eccd  retn
0x18007eccf  mov     r8, rdi
0x18007ecd2  mov     edx, 6
0x18007ecd7  mov     rcx, rsi
0x18007ecda  call    ?ExpectToken@@YAJPEAU_XML_TOKENIZATION_STATE@@W4XML_TOKENIZATION_SPECIFIC_STATE@@PEAU_XML_TOKEN@@@Z; ExpectToken(_XML_TOKENIZATION_STATE *,XML_TOKENIZATION_SPECIFIC_STATE,_XML_TOKEN *)
0x18007ecdf  mov     esi, eax
0x18007ece1  test    eax, eax
0x18007ece3  jns     short loc_18007ED53
0x18007ece5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007ecec  mov     [rbp+4Fh+var_70], eax
0x18007ecef  test    rcx, rcx
0x18007ecf2  jz      short loc_18007ED34
0x18007ecf4  lea     r9, aFailedToExpect_0; "Failed to expect token"
0x18007ecfb  xor     edx, edx
0x18007ecfd  mov     r8d, 3
0x18007ed03  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007ed08  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007ed0f  lea     rax, [rbp+4Fh+var_70]
0x18007ed13  mov     qword ptr [rbp+4Fh+var_68], rax
0x18007ed17  lea     r9, asc_1802EE7AC; ": {}"
0x18007ed1e  lea     rax, [rbp+4Fh+var_68]
0x18007ed22  mov     r8d, 3
0x18007ed28  mov     dl, 1
0x18007ed2a  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x18007ed2f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007ed34  mov     rcx, [rbp+57h]; this
0x18007ed38  lea     r8, aOnecoreBaseCbs_62; "onecore\\base\\cbs\\parser\\token.cpp"
0x18007ed3f  mov     r9d, esi; char *
0x18007ed42  mov     edx, 140h; void *
0x18007ed47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ed4c  mov     eax, esi
0x18007ed4e  jmp     loc_18007ECA5
0x18007ed53  test    r12b, 2
0x18007ed57  jnz     loc_18007EDFF
0x18007ed5d  lea     r14, [rbx+1E0h]
0x18007ed64  mov     rsi, [r14+18h]
0x18007ed68  mov     rcx, r14
0x18007ed6b  mov     rdx, rsi
0x18007ed6e  call    ?MakeRoomAt@?$CCbsArrayBase@U_XML_TOKEN@@V?$CCbsArray@U_XML_TOKEN@@@@@@IEAAJ_K@Z; CCbsArrayBase<_XML_TOKEN,CCbsArray<_XML_TOKEN>>::MakeRoomAt(unsigned __int64)
0x18007ed73  mov     ebx, eax
0x18007ed75  test    eax, eax
0x18007ed77  jns     short loc_18007EDE7
0x18007ed79  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007ed80  mov     [rbp+4Fh+var_70], eax
0x18007ed83  test    rcx, rcx
0x18007ed86  jz      short loc_18007EDC8
0x18007ed88  lea     r9, aFailedToPushEl; "Failed to push element."
0x18007ed8f  xor     edx, edx
0x18007ed91  mov     r8d, 3
0x18007ed97  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007ed9c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007eda3  lea     rax, [rbp+4Fh+var_70]
0x18007eda7  mov     qword ptr [rbp+4Fh+var_68], rax
0x18007edab  lea     r9, asc_1802EE7AC; ": {}"
0x18007edb2  lea     rax, [rbp+4Fh+var_68]
0x18007edb6  mov     r8d, 3
0x18007edbc  mov     dl, 1
0x18007edbe  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x18007edc3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007edc8  mov     rcx, [rbp+57h]; this
0x18007edcc  lea     r8, aOnecoreBaseCbs_62; "onecore\\base\\cbs\\parser\\token.cpp"
0x18007edd3  mov     r9d, ebx; char *
0x18007edd6  mov     edx, 146h; void *
0x18007eddb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ede0  mov     eax, ebx
0x18007ede2  jmp     loc_18007ECA5
0x18007ede7  mov     rax, [r14+28h]
0x18007edeb  movups  xmm0, xmmword ptr [rdi]
0x18007edee  shl     rsi, 5
0x18007edf2  movups  xmmword ptr [rsi+rax], xmm0
0x18007edf6  movups  xmm1, xmmword ptr [rdi+10h]
0x18007edfa  movups  xmmword ptr [rsi+rax+10h], xmm1
0x18007edff  mov     byte ptr [r15], 0
0x18007ee03  xor     eax, eax
0x18007ee05  jmp     loc_18007ECA5
0x18007ee0a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007ee11  mov     [rbp+4Fh+var_70], r14d
0x18007ee15  test    rcx, rcx
0x18007ee18  jz      short loc_18007EE5A
0x18007ee1a  lea     r9, aFailedToProces_3; "Failed to process namespace prefix."
0x18007ee21  xor     edx, edx
0x18007ee23  mov     r8d, 3
0x18007ee29  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007ee2e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007ee35  lea     rax, [rbp+4Fh+var_70]
0x18007ee39  mov     qword ptr [rbp+4Fh+var_68], rax
0x18007ee3d  lea     r9, asc_1802EE7AC; ": {}"
0x18007ee44  lea     rax, [rbp+4Fh+var_68]
0x18007ee48  mov     r8d, 3
0x18007ee4e  mov     dl, 1
0x18007ee50  mov     qword ptr [rsp+0B0h+var_90], rax
0x18007ee55  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007ee5a  mov     rcx, [rbp+57h]
0x18007ee5e  lea     r8, aOnecoreBaseCbs_62; "onecore\\base\\cbs\\parser\\token.cpp"
0x18007ee65  mov     r9d, r14d
0x18007ee68  mov     edx, 13Dh
0x18007ee6d  jmp     loc_18007EC9D
0x18007ee72  mov     rcx, [rbx+1F8h]
0x18007ee79  test    rcx, rcx
0x18007ee7c  jz      short loc_18007EEE8
0x18007ee7e  lea     rdx, [rcx-1]
0x18007ee82  cmp     rdx, rcx
0x18007ee85  jnb     short loc_18007EEE8
0x18007ee87  mov     r8, rdx
0x18007ee8a  not     r8
0x18007ee8d  add     r8, rcx
0x18007ee90  jz      short loc_18007EEAD
0x18007ee92  mov     rcx, [rbx+208h]
0x18007ee99  shl     rdx, 5
0x18007ee9d  add     rcx, rdx; void *
0x18007eea0  shl     r8, 5; Size
0x18007eea4  lea     rdx, [rcx+20h]; Src
0x18007eea8  call    memmove_0
0x18007eead  dec     qword ptr [rbx+1F8h]
0x18007eeb4  mov     ecx, 20h ; ' '
0x18007eeb9  mov     rax, [rbx+1F8h]
0x18007eec0  shl     rax, 5
0x18007eec4  add     rax, [rbx+208h]
0x18007eecb  nop     dword ptr [rax+rax+00h]
0x18007eed0  mov     byte ptr [rax], 0
0x18007eed3  lea     rax, [rax+1]
0x18007eed7  sub     rcx, 1
0x18007eedb  jnz     short loc_18007EED0
0x18007eedd  mov     byte ptr [r15], 1
0x18007eee1  xor     eax, eax
0x18007eee3  jmp     loc_18007ECA5
0x18007eee8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007eeef  mov     [rbp+4Fh+var_70], 800F080Dh
0x18007eef6  test    rcx, rcx
0x18007eef9  jz      short loc_18007EF3B
0x18007eefb  lea     r9, aNoMatchingOpen; "No matching open element for the close "...
0x18007ef02  xor     edx, edx
0x18007ef04  mov     r8d, 3
0x18007ef0a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007ef0f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007ef16  lea     rax, [rbp+4Fh+var_70]
0x18007ef1a  mov     qword ptr [rbp+4Fh+var_68], rax
0x18007ef1e  lea     r9, asc_1802EE7AC; ": {}"
0x18007ef25  lea     rax, [rbp+4Fh+var_68]
0x18007ef29  mov     r8d, 3
0x18007ef2f  mov     dl, 1
0x18007ef31  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x18007ef36  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007ef3b  mov     rcx, [rbp+57h]; this
0x18007ef3f  lea     r8, aOnecoreBaseCbs_62; "onecore\\base\\cbs\\parser\\token.cpp"
0x18007ef46  mov     r9d, 800F080Dh; char *
0x18007ef4c  mov     edx, 135h; void *
0x18007ef51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ef56  mov     eax, 800F080Dh
0x18007ef5b  jmp     loc_18007ECA5
0x18007ef60  lea     r9, [rbp+4Fh+var_80]; bool *
0x18007ef64  xor     r8d, r8d; bool
0x18007ef67  mov     rdx, rsi; struct _XML_TOKENIZATION_STATE *
0x18007ef6a  mov     rcx, rbx; struct ParsingSession *
0x18007ef6d  call    ?ProcessNamespacePrefix@@YAJPEAUParsingSession@@PEAU_XML_TOKENIZATION_STATE@@_NPEA_N@Z; ProcessNamespacePrefix(ParsingSession *,_XML_TOKENIZATION_STATE *,bool,bool *)
0x18007ef72  mov     r14d, eax
0x18007ef75  test    eax, eax
0x18007ef77  jns     short loc_18007EFE0
0x18007ef79  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007ef80  mov     [rbp+4Fh+var_70], eax
0x18007ef83  test    rcx, rcx
0x18007ef86  jz      short loc_18007EFC8
0x18007ef88  lea     r9, aFailedToProces_3; "Failed to process namespace prefix."
0x18007ef8f  xor     edx, edx
0x18007ef91  mov     r8d, 3
0x18007ef97  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007ef9c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007efa3  lea     rax, [rbp+4Fh+var_70]
0x18007efa7  mov     qword ptr [rbp+4Fh+var_78], rax
0x18007efab  lea     r9, asc_1802EE7AC; ": {}"
0x18007efb2  lea     rax, [rbp+4Fh+var_78]
0x18007efb6  mov     r8d, 3
0x18007efbc  mov     dl, 1
0x18007efbe  mov     qword ptr [rsp+0B0h+var_90], rax
0x18007efc3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007efc8  mov     rcx, [rbp+57h]
0x18007efcc  lea     r8, aOnecoreBaseCbs_62; "onecore\\base\\cbs\\parser\\token.cpp"
0x18007efd3  mov     r9d, r14d
0x18007efd6  mov     edx, 114h
0x18007efdb  jmp     loc_18007EC9D
0x18007efe0  cmp     [rbp+4Fh+var_80], 0
0x18007efe4  jnz     short loc_18007F05E
0x18007efe6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007efed  mov     [rbp+4Fh+var_68], 800F080Dh
0x18007eff4  test    rcx, rcx
0x18007eff7  jz      short loc_18007F039
0x18007eff9  lea     r9, aElementInUnrec; "Element in unrecognized namespace close"...
0x18007f000  xor     edx, edx
0x18007f002  mov     r8d, 3
0x18007f008  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18007f00d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18007f014  lea     rax, [rbp+4Fh+var_68]
0x18007f018  mov     qword ptr [rbp+4Fh+var_78], rax
0x18007f01c  lea     r9, asc_1802EE7AC; ": {}"
0x18007f023  lea     rax, [rbp+4Fh+var_78]
0x18007f027  mov     r8d, 3
0x18007f02d  mov     dl, 1
0x18007f02f  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x18007f034  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18007f039  mov     rcx, [rbp+57h]; this
0x18007f03d  lea     r8, aOnecoreBaseCbs_62; "onecore\\base\\cbs\\parser\\token.cpp"
0x18007f044  mov     r9d, 800F080Dh; char *
0x18007f04a  mov     edx, 11Bh; void *
0x18007f04f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
