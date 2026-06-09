# ProcessUpdateType(_XML_TOKENIZATION_STATE *,ParsingSession *,PACKAGE_TYPE *,UPDATE_TYPE *)

- ea: `0x18008b2f4`
- end: `0x18008c74d`
- name: `?ProcessUpdateType@@YAJPEAU_XML_TOKENIZATION_STATE@@PEAUParsingSession@@PEAUPACKAGE_TYPE@@PEAUUPDATE_TYPE@@@Z`
- size: `5209`
- prototype: `__int64 __fastcall(struct _XML_TOKENIZATION_STATE *, struct ParsingSession *, struct PACKAGE_TYPE *, struct UPDATE_TYPE *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180088054`

## callees

- `0x180028830`
- `0x1800348cc`
- `0x180075640`
- `0x18007c1e0`
- `0x18007c660`
- `0x18007d1e0`
- `0x18007f590`
- `0x18007fc50`
- `0x180080df0`
- `0x180081630`
- `0x180087e24`
- `0x180088274`
- `0x1800886dc`
- `0x180088ca8`
- `0x1800898b8`
- `0x18008a278`
- `0x18008abb8`
- `0x18008b2f4`
- `0x18008c754`
- `0x18008cbb0`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x18010c010`
- `0x18020b0a4`

## string_xrefs

- `0x18008b448`: `No update result specified`
- `0x18008b786`: `Failed to expect token`
- `0x18008bc26`: `Failed to process update group`
- `0x18008c6d8`: `Failed to peek next token.`
- `0x18008b3b2`: `onecore\base\cbs\parser\update.cpp`
- `0x18008b6b9`: `onecore\base\cbs\parser\update.cpp`
- `0x18008bb69`: `onecore\base\cbs\parser\update.cpp`
- `0x18008c71b`: `onecore\base\cbs\parser\update.cpp`
- `0x18008c2d5`: `cannot have more than one package in one update`
- `0x18008c371`: `Failed to process DriverUpdateType`
- `0x18008c51e`: `Failed to process ComponentUpdateType`
- `0x18008c27b`: `allocating UPDATE_TYPE`
- `0x18008c3c9`: `allocating UPDATE_TYPE`
- `0x18008c576`: `allocating UPDATE_TYPE`
- `0x18008c0d4`: `Failed to process CapabilityUpdateType`
- `0x18008c12c`: `allocating allocating UPDATE_TYPE`
- `0x18008c187`: `cannot have more than one capability in one update`
- `0x18008c223`: `Failed to process packageUpdateType`
- `0x18008ba2f`: `Validation on updateType failed.`
- `0x18008c473`: `Failed to get update root element.`
- `0x18008b72e`: `Invalid update attributes`
- `0x18008b83f`: `unexpected update attribute; found {}`
- `0x18008c1d0`: `cannot mix different types in one update`
- `0x18008c31e`: `cannot mix different types in one update`
- `0x18008c41f`: `cannot mix different types in one update`
- `0x18008c5cc`: `cannot mix different types in one update`
- `0x18008bd6f`: `Failed to get update root elment.`
- `0x18008bce7`: `Failed to save last token`

## pseudocode

```c
__int64 __fastcall ProcessUpdateType(
        struct _XML_TOKENIZATION_STATE *a1,
        struct ParsingSession *a2,
        struct PACKAGE_TYPE *a3,
        struct UPDATE_TYPE *a4)
{
  unsigned int v7; // edi
  __int64 v8; // rdx
  int Token; // esi
  int Value; // eax
  __int64 v12; // rdx
  int v13; // edx
  int v14; // r8d
  int UINTFromString; // eax
  int v16; // ebx
  __int64 v17; // rdx
  int updated; // eax
  int v19; // eax
  void *v20; // r12
  wchar_t **v21; // rax
  wchar_t **v22; // rsi
  int v23; // eax
  struct _XML_TOKENIZATION_STATE *v24; // rdx
  int v25; // r15d
  __int64 v26; // rdx
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int NextElementEnumValue; // eax
  unsigned int v31; // esi
  _QWORD *v32; // rax
  _QWORD *v33; // r15
  _QWORD *v34; // rax
  _DWORD *v35; // rax
  _QWORD *v36; // rax
  char *v37; // rax
  __int64 *v38; // rcx
  __int64 v39; // rax
  int v40; // [rsp+20h] [rbp-99h]
  bool v41; // [rsp+40h] [rbp-79h] BYREF
  bool v42; // [rsp+41h] [rbp-78h] BYREF
  int v43[2]; // [rsp+48h] [rbp-71h] BYREF
  int *v44; // [rsp+50h] [rbp-69h] BYREF
  int *v45; // [rsp+58h] [rbp-61h] BYREF
  int *v46; // [rsp+60h] [rbp-59h] BYREF
  void *v47[2]; // [rsp+68h] [rbp-51h] BYREF
  __int128 v48; // [rsp+78h] [rbp-41h]
  bool v49[4]; // [rsp+88h] [rbp-31h] BYREF
  int v50; // [rsp+8Ch] [rbp-2Dh] BYREF
  struct PACKAGE_TYPE *v51; // [rsp+90h] [rbp-29h] BYREF
  int v52; // [rsp+98h] [rbp-21h] BYREF
  unsigned __int16 v53[2]; // [rsp+9Ch] [rbp-1Dh] BYREF
  int v54; // [rsp+A0h] [rbp-19h] BYREF
  int v55; // [rsp+A4h] [rbp-15h] BYREF
  int v56[4]; // [rsp+A8h] [rbp-11h] BYREF
  __int128 v57; // [rsp+B8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v51 = a3;
  v53[0] = 0;
  v49[0] = 0;
  v42 = 0;
  v41 = 0;
  *(_OWORD *)v56 = 0;
  v57 = 0;
  *(_OWORD *)v47 = 0;
  v48 = 0;
  if ( !a1 )
  {
    v7 = -2147024809;
    v52 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No state specified");
      v51 = (struct PACKAGE_TYPE *)&v52;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v51);
    }
    v8 = 606;
    goto LABEL_5;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    v52 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No parsing session specified");
      v51 = (struct PACKAGE_TYPE *)&v52;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v51);
    }
    v8 = 607;
    goto LABEL_5;
  }
  if ( !a4 )
  {
    v7 = -2147467261;
    v52 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No update result specified");
      v51 = (struct PACKAGE_TYPE *)&v52;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v51);
    }
    v8 = 608;
    goto LABEL_5;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        Token = PeekNextToken(a1, (struct _XML_TOKEN *)v56);
        if ( Token < 0 )
        {
          LODWORD(v51) = Token;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to peek next token.");
            *(_QWORD *)v43 = &v51;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v43);
          }
          v12 = 618;
LABEL_207:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v12,
            (unsigned int)"onecore\\base\\cbs\\parser\\update.cpp",
            (const char *)(unsigned int)Token,
            v40);
          return (unsigned int)Token;
        }
        if ( DWORD2(v57) != 7 )
          break;
        Token = ExpectToken(a1, 7, v56);
        if ( Token < 0 )
        {
          v52 = Token;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to expect token");
            v51 = (struct PACKAGE_TYPE *)&v52;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v51);
          }
          v12 = 621;
          goto LABEL_207;
        }
        Value = GetValue(a1, (const struct _XML_TOKEN *)v56, (struct _XML_TOKEN *)v47);
        Token = Value;
        if ( Value < 0 )
        {
          v52 = Value;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get value.");
            v51 = (struct PACKAGE_TYPE *)&v52;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v51);
          }
          v12 = 623;
          goto LABEL_207;
        }
      }
      if ( !(unsigned int)GetNextAttributeEnumValue(
                            a2,
                            a1,
                            (struct enumType *const)&UPDATE_TYPE_ATTRIBUTE_MAP,
                            v49,
                            (struct _XML_TOKEN *)v56,
                            v53,
                            0) )
        break;
      Token = GetValue(a1, (const struct _XML_TOKEN *)v56, (struct _XML_TOKEN *)v47);
      if ( Token < 0 )
      {
        LODWORD(v51) = Token;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"failed to get value");
          *(_QWORD *)v43 = &v51;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v43);
        }
        v12 = 694;
        goto LABEL_207;
      }
      updated = ProcessCommonUpdateAttributesGroup(
                  a1,
                  a2,
                  (const struct _XML_TOKEN *)v56,
                  (const struct _XML_TOKEN *)v47,
                  &v42,
                  &v41,
                  a4);
      Token = updated;
      if ( updated < 0 )
      {
        LODWORD(v51) = updated;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid update attributes");
          *(_QWORD *)v43 = &v51;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v43);
        }
        v12 = 702;
        goto LABEL_207;
      }
    }
    if ( v49[0] )
      break;
    Token = GetValue(a1, (const struct _XML_TOKEN *)v56, (struct _XML_TOKEN *)v47);
    if ( Token < 0 )
    {
      v50 = Token;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"failed to get value");
        v51 = (struct PACKAGE_TYPE *)&v50;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v51);
      }
      v12 = 643;
      goto LABEL_207;
    }
    switch ( v53[0] )
    {
      case 1u:
        if ( *((_QWORD *)a4 + 1) )
        {
          v7 = -2146498546;
          v52 = -2146498546;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Duplicate name.");
            v51 = (struct PACKAGE_TYPE *)&v52;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v51);
          }
          v8 = 647;
          goto LABEL_5;
        }
        v16 = DuplicateXmlString(
                (wchar_t **)a4 + 1,
                a1,
                (struct _XML_EXTENT *)v47,
                (struct ParsingSession *)((char *)a2 + 48));
        if ( v16 < 0 )
        {
          v17 = 653;
          goto LABEL_42;
        }
        break;
      case 2u:
        if ( *((_QWORD *)a4 + 2) )
        {
          v7 = -2146498546;
          v52 = -2146498546;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Duplicate displayName.");
            v51 = (struct PACKAGE_TYPE *)&v52;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v51);
          }
          v8 = 658;
LABEL_5:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v8,
            (unsigned int)"onecore\\base\\cbs\\parser\\update.cpp",
            (const char *)v7,
            v40);
          return v7;
        }
        v16 = DuplicateXmlString(
                (wchar_t **)a4 + 2,
                a1,
                (struct _XML_EXTENT *)v47,
                (struct ParsingSession *)((char *)a2 + 48));
        if ( v16 < 0 )
        {
          v17 = 664;
          goto LABEL_42;
        }
        break;
      case 3u:
        if ( *((_QWORD *)a4 + 3) )
        {
          v7 = -2146498546;
          v52 = -2146498546;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Duplicate description.");
            v51 = (struct PACKAGE_TYPE *)&v52;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v51);
          }
          v8 = 669;
          goto LABEL_5;
        }
        v16 = DuplicateXmlString(
                (wchar_t **)a4 + 3,
                a1,
                (struct _XML_EXTENT *)v47,
                (struct ParsingSession *)((char *)a2 + 48));
        if ( v16 < 0 )
        {
          v17 = 675;
LABEL_42:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"onecore\\base\\cbs\\parser\\update.cpp",
            (const char *)(unsigned int)v16,
            v40);
          return (unsigned int)v16;
        }
        break;
      case 4u:
        if ( *((_DWORD *)a4 + 8) )
        {
          v7 = -2146498546;
          v52 = -2146498546;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Duplicate downloadSize.");
            v51 = (struct PACKAGE_TYPE *)&v52;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v51);
          }
          v8 = 680;
          goto LABEL_5;
        }
        UINTFromString = GetUINTFromString(v47[0], (unsigned __int64)v47[1], (unsigned int *)a4 + 8);
        Token = UINTFromString;
        if ( UINTFromString < 0 )
        {
          v52 = UINTFromString;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get download size.");
            v51 = (struct PACKAGE_TYPE *)&v52;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v51);
          }
          v12 = 684;
          goto LABEL_207;
        }
        break;
      default:
        v7 = -2146498547;
        v52 = -2146498547;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<unsigned short>(
            (_DWORD)LogAdapter::g_Logger,
            v13,
            v14,
            (unsigned int)"unexpected update attribute; found {}",
            (__int64)v53);
          v51 = (struct PACKAGE_TYPE *)&v52;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)&v51);
        }
        v8 = 688;
        goto LABEL_5;
    }
  }
  if ( IsElementClosed(a1) )
  {
    ExpectNoElement(a2, a1);
    goto LABEL_71;
  }
  v20 = (void *)*((_QWORD *)a1 + 4);
  if ( GetNextElementEnumValue(
         1u,
         a2,
         a1,
         (struct enumType *const)&UPDATE_TYPE_ROOT_ELEMENT_MAP,
         v49,
         (struct _XML_TOKEN *)v56,
         v53) < 0
    || v49[0]
    || v53[0] != 4 )
  {
    v29 = SaveToken(a2, (const struct _XML_TOKEN *)v56, v49[0]);
    Token = v29;
    if ( v29 < 0 )
    {
      v50 = v29;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to save last token");
        v51 = (struct PACKAGE_TYPE *)&v50;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v51);
      }
      v12 = 763;
      goto LABEL_207;
    }
  }
  else
  {
    v21 = (wchar_t **)CMemoryAllocator::Alloc((struct ParsingSession *)((char *)a2 + 48), 0x30u);
    v22 = v21;
    if ( !v21 )
    {
      v7 = -2147024882;
      v50 = -2147024882;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate custom information");
        v51 = (struct PACKAGE_TYPE *)&v50;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v51);
      }
      v8 = 741;
      goto LABEL_5;
    }
    *v21 = 0;
    v21[1] = 0;
    v21[2] = 0;
    v21[3] = 0;
    v21[4] = 0;
    v21[5] = 0;
    v23 = ProcessCustomInformation(a1, a2, 0, 0, (struct CUSTOM_INFORMATION_TYPE *)v21);
    v25 = v23;
    if ( v23 < 0 )
    {
      v50 = v23;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to process custom information");
        v51 = (struct PACKAGE_TYPE *)&v50;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v51);
      }
      v26 = 749;
LABEL_83:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"onecore\\base\\cbs\\parser\\update.cpp",
        (const char *)(unsigned int)v25,
        v40);
      return (unsigned int)v25;
    }
    v27 = DuplicateXmlBlobToString(v22 + 5, v24, v20, *((void **)a1 + 4), (struct ParsingSession *)((char *)a2 + 48));
    v25 = v27;
    if ( v27 < 0 )
    {
      v50 = v27;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to convert custom information blob to string");
        v51 = (struct PACKAGE_TYPE *)&v50;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v51);
      }
      v26 = 755;
      goto LABEL_83;
    }
    *((_QWORD *)a4 + 12) = v22;
  }
  v28 = ProcessUpdateGroupType(a1, a2, (struct APPLICABLE_TYPE_NODE **)a4 + 5);
  Token = v28;
  if ( v28 < 0 )
  {
    v50 = v28;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to process update group");
      v51 = (struct PACKAGE_TYPE *)&v50;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v51);
    }
    v12 = 766;
    goto LABEL_207;
  }
  NextElementEnumValue = GetNextElementEnumValue(
                           0,
                           a2,
                           a1,
                           (struct enumType *const)&UPDATE_TYPE_ROOT_ELEMENT_MAP,
                           v49,
                           (struct _XML_TOKEN *)v56,
                           v53);
  Token = NextElementEnumValue;
  if ( NextElementEnumValue < 0 )
  {
    v50 = NextElementEnumValue;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get update root elment.");
      v51 = (struct PACKAGE_TYPE *)&v50;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&v51);
    }
    v12 = 779;
    goto LABEL_207;
  }
  v31 = 0;
  while ( !v49[0] )
  {
    v32 = CMemoryAllocator::Alloc((struct ParsingSession *)((char *)a2 + 48), 0x18u);
    v33 = v32;
    if ( !v32 )
    {
      v7 = -2147024882;
      LODWORD(v51) = -2147024882;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"allocating deployment node");
        *(_QWORD *)v43 = &v51;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v43);
      }
      v8 = 783;
      goto LABEL_5;
    }
    *(_DWORD *)v32 = 0;
    v32[1] = 0;
    v32[2] = 0;
    switch ( v53[0] )
    {
      case 1u:
        if ( v31 > 2 )
        {
          v7 = -2146498547;
          LODWORD(v51) = -2146498547;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"cannot mix different types in one update");
            *(_QWORD *)v43 = &v51;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v43);
          }
          v8 = 790;
          goto LABEL_5;
        }
        v37 = (char *)CMemoryAllocator::Alloc((struct ParsingSession *)((char *)a2 + 48), 0x50u);
        if ( v37 )
        {
          *(_QWORD *)v37 = 0;
          *((_QWORD *)v37 + 1) = 0;
          *((_QWORD *)v37 + 2) = 0;
          *((_QWORD *)v37 + 3) = 0;
          *((_QWORD *)v37 + 4) = 0;
          *((_QWORD *)v37 + 5) = 0;
          *((_QWORD *)v37 + 6) = 0;
          *((_QWORD *)v37 + 7) = 0;
          *((_QWORD *)v37 + 8) = 0;
          *((_WORD *)v37 + 36) = 0;
          v37[74] = 0;
          *(_DWORD *)(v37 + 75) = 0;
          v37[79] = 0;
        }
        else
        {
          v37 = 0;
        }
        v33[1] = v37;
        if ( !v37 )
        {
          v7 = -2147024882;
          LODWORD(v51) = -2147024882;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"allocating UPDATE_TYPE");
            *(_QWORD *)v43 = &v51;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v43);
          }
          v8 = 795;
          goto LABEL_5;
        }
        Token = ProcessComponentUpdateType(a1, a2, (struct COMPONENT_UPDATE_TYPE *)v37);
        if ( Token < 0 )
        {
          LODWORD(v51) = Token;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to process ComponentUpdateType");
            *(_QWORD *)v43 = &v51;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)v43);
          }
          v12 = 801;
          goto LABEL_207;
        }
        v31 = 1;
        break;
      case 2u:
        if ( v31 > 2 )
        {
          v7 = -2146498547;
          v54 = -2146498547;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"cannot mix different types in one update");
            v44 = &v54;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v44);
          }
          v8 = 807;
          goto LABEL_5;
        }
        v36 = CMemoryAllocator::Alloc((struct ParsingSession *)((char *)a2 + 48), 0x58u);
        if ( v36 )
        {
          *v36 = 0;
          v36[1] = 0;
          v36[2] = 0;
          v36[3] = 0;
          v36[4] = 0;
          v36[5] = 0;
          v36[6] = 0;
          v36[7] = 0;
          v36[8] = 0;
          v36[9] = 0;
          *((_DWORD *)v36 + 20) = 0;
          *((_WORD *)v36 + 42) = 256;
        }
        else
        {
          v36 = 0;
        }
        v33[1] = v36;
        if ( !v36 )
        {
          v7 = -2147024882;
          v54 = -2147024882;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"allocating UPDATE_TYPE");
            v44 = &v54;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v44);
          }
          v8 = 812;
          goto LABEL_5;
        }
        Token = ProcessDriverUpdateType(a1, a2, (struct DRIVER_UPDATE_TYPE *)v36);
        if ( Token < 0 )
        {
          v54 = Token;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to process DriverUpdateType");
            v44 = &v54;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v44);
          }
          v12 = 817;
          goto LABEL_207;
        }
        v31 = 2;
        break;
      case 3u:
        if ( v31 )
        {
          v7 = -2146498547;
          v50 = -2146498547;
          if ( v31 == 3 )
          {
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"cannot have more than one package in one update");
              v46 = &v50;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)&v46);
            }
            v8 = 825;
          }
          else
          {
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"cannot mix different types in one update");
              v46 = &v50;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)&v46);
            }
            v8 = 829;
          }
          goto LABEL_5;
        }
        v35 = CMemoryAllocator::Alloc((struct ParsingSession *)((char *)a2 + 48), 0x68u);
        if ( v35 )
        {
          *(_BYTE *)v35 = 0;
          v35[1] = 2;
          *((_QWORD *)v35 + 1) = 0;
          *((_QWORD *)v35 + 2) = 0;
          *((_QWORD *)v35 + 3) = 0;
          *((_QWORD *)v35 + 4) = 0;
          *((_QWORD *)v35 + 5) = 0;
          *((_QWORD *)v35 + 6) = 0;
          *((_QWORD *)v35 + 7) = 0;
          *((_QWORD *)v35 + 8) = 0;
          *((_QWORD *)v35 + 9) = 0;
          *((_WORD *)v35 + 40) = 0;
          *((_BYTE *)v35 + 82) = 0;
          *(_DWORD *)((char *)v35 + 83) = 0;
          *((_BYTE *)v35 + 87) = 0;
          *((_QWORD *)v35 + 11) = 0;
          v35[24] = 0;
        }
        else
        {
          v35 = 0;
        }
        v33[1] = v35;
        if ( !v35 )
        {
          v7 = -2147024882;
          v50 = -2147024882;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"allocating UPDATE_TYPE");
            v46 = &v50;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v46);
          }
          v8 = 835;
          goto LABEL_5;
        }
        Token = ProcessPackageUpdateType(a1, a2, v51, (struct PACKAGE_UPDATE_TYPE *)v35);
        if ( Token < 0 )
        {
          v52 = Token;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to process packageUpdateType");
            v46 = &v52;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v46);
          }
          v12 = 841;
          goto LABEL_207;
        }
        v31 = 3;
        break;
      case 5u:
        if ( v31 )
        {
          v7 = -2146498547;
          v50 = -2146498547;
          if ( v31 == 5 )
          {
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"cannot have more than one capability in one update");
              v45 = &v50;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)&v45);
            }
            v8 = 849;
          }
          else
          {
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(
                (__int64)LogAdapter::g_Logger,
                0,
                3,
                (struct Windows::Rtl::IRtlFormattedOutputStream *)"cannot mix different types in one update");
              v45 = &v50;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                (__int64)LogAdapter::g_Logger,
                1,
                3,
                (__int64)": {}",
                (__int64)&v45);
            }
            v8 = 853;
          }
          goto LABEL_5;
        }
        v34 = CMemoryAllocator::Alloc((struct ParsingSession *)((char *)a2 + 48), 0x68u);
        if ( v34 )
        {
          *v34 = 0;
          v34[1] = 0;
          v34[2] = 0;
          v34[3] = 0;
          v34[4] = 0;
          v34[5] = 0;
          v34[6] = 0;
          v34[7] = 0;
          v34[8] = 0;
          *((_DWORD *)v34 + 18) = 96;
          *((_DWORD *)v34 + 19) = 1;
          *((_DWORD *)v34 + 20) = 1;
          *((_DWORD *)v34 + 21) = 1;
          *((_DWORD *)v34 + 22) = 1;
          *((_DWORD *)v34 + 23) = 1;
          v34[12] = 1;
        }
        else
        {
          v34 = 0;
        }
        v33[1] = v34;
        if ( !v34 )
        {
          v7 = -2147024882;
          v50 = -2147024882;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"allocating allocating UPDATE_TYPE");
            v45 = &v50;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v45);
          }
          v8 = 859;
          goto LABEL_5;
        }
        Token = ProcessCapabilityUpdateType(a1, a2, (struct CAPABILITY_UPDATE_TYPE *)v34);
        if ( Token < 0 )
        {
          v50 = Token;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to process CapabilityUpdateType");
            v45 = &v50;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&v45);
          }
          v12 = 864;
          goto LABEL_207;
        }
        v31 = 5;
        break;
    }
    v38 = (__int64 *)((char *)a4 + 80);
    *(_DWORD *)v33 = v53[0];
    if ( a4 == (struct UPDATE_TYPE *)-80LL )
    {
      v7 = -2147024809;
      v55 = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to add deployment node");
        v44 = &v55;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v44);
      }
      v8 = 873;
      goto LABEL_5;
    }
    v39 = *v38;
    if ( *v38 )
    {
      while ( *(_QWORD *)(v39 + 16) )
        v39 = *(_QWORD *)(v39 + 16);
      *(_QWORD *)(v39 + 16) = v33;
      v33[2] = 0;
    }
    else
    {
      *v38 = (__int64)v33;
    }
    ++*((_DWORD *)a4 + 22);
    v25 = GetNextElementEnumValue(
            0,
            a2,
            a1,
            (struct enumType *const)&UPDATE_TYPE_ROOT_ELEMENT_MAP,
            v49,
            (struct _XML_TOKEN *)v56,
            v53);
    if ( v25 < 0 )
    {
      v54 = v25;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get update root element.");
        v44 = &v54;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v44);
      }
      v26 = 885;
      goto LABEL_83;
    }
  }
LABEL_71:
  v19 = ValidateUpdateType(a4);
  v7 = v19;
  if ( v19 < 0 )
  {
    LODWORD(v51) = v19;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Validation on updateType failed.");
      *(_QWORD *)v43 = &v51;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v43);
    }
    v8 = 891;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x18008b2f4  push    rbp
0x18008b2f6  push    rbx
0x18008b2f7  push    rsi
0x18008b2f8  push    rdi
0x18008b2f9  push    r12
0x18008b2fb  push    r13
0x18008b2fd  push    r14
0x18008b2ff  push    r15
0x18008b301  lea     rbp, [rsp-1Fh]
0x18008b306  sub     rsp, 0D8h
0x18008b30d  mov     rax, cs:__security_cookie
0x18008b314  xor     rax, rsp
0x18008b317  mov     [rbp+57h+var_48], rax
0x18008b31b  xor     r15d, r15d
0x18008b31e  mov     [rbp+57h+var_80], r8
0x18008b322  mov     [rbp+57h+var_74], r15w
0x18008b327  xorps   xmm0, xmm0
0x18008b32a  mov     [rbp+57h+var_88], r15b
0x18008b32e  xorps   xmm1, xmm1
0x18008b331  mov     [rbp+57h+var_CF], r15b
0x18008b335  mov     r13, r9
0x18008b338  mov     [rbp+57h+var_D0], r15b
0x18008b33c  mov     r14, rdx
0x18008b33f  mov     rdi, rcx
0x18008b342  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x18008b346  movups  [rbp+57h+var_58], xmm0
0x18008b34a  movups  xmmword ptr [rbp+57h+var_A8], xmm1
0x18008b34e  movups  [rbp+57h+var_98], xmm1
0x18008b352  test    rcx, rcx
0x18008b355  jnz     short loc_18008B3C8
0x18008b357  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b35e  mov     edi, 80070057h
0x18008b363  mov     [rbp+57h+var_78], edi
0x18008b366  test    rcx, rcx
0x18008b369  jz      short loc_18008B3A9
0x18008b36b  lea     ebx, [r15+3]
0x18008b36f  xor     edx, edx
0x18008b371  mov     r8d, ebx
0x18008b374  lea     r9, aNoStateSpecifi_0; "No state specified"
0x18008b37b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008b380  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b387  lea     rax, [rbp+57h+var_78]
0x18008b38b  mov     [rbp+57h+var_80], rax
0x18008b38f  lea     r9, asc_1802EE7AC; ": {}"
0x18008b396  lea     rax, [rbp+57h+var_80]
0x18008b39a  mov     r8d, ebx
0x18008b39d  mov     dl, 1
0x18008b39f  mov     [rsp+110h+var_F0], rax; int
0x18008b3a4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008b3a9  mov     edx, 25Eh; void *
0x18008b3ae  mov     rcx, [rbp+5Fh]; this
0x18008b3b2  lea     r8, aOnecoreBaseCbs_131; "onecore\\base\\cbs\\parser\\update.cpp"
0x18008b3b9  mov     r9d, edi; char *
0x18008b3bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b3c1  mov     eax, edi
0x18008b3c3  jmp     loc_18008C72C
0x18008b3c8  test    r14, r14
0x18008b3cb  jnz     short loc_18008B426
0x18008b3cd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b3d4  mov     edi, 80070057h
0x18008b3d9  mov     [rbp+57h+var_78], edi
0x18008b3dc  test    rcx, rcx
0x18008b3df  jz      short loc_18008B41F
0x18008b3e1  lea     ebx, [r14+3]
0x18008b3e5  xor     edx, edx
0x18008b3e7  mov     r8d, ebx
0x18008b3ea  lea     r9, aNoParsingSessi_0; "No parsing session specified"
0x18008b3f1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008b3f6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b3fd  lea     rax, [rbp+57h+var_78]
0x18008b401  mov     [rbp+57h+var_80], rax
0x18008b405  lea     r9, asc_1802EE7AC; ": {}"
0x18008b40c  lea     rax, [rbp+57h+var_80]
0x18008b410  mov     r8d, ebx
0x18008b413  mov     dl, 1
0x18008b415  mov     [rsp+110h+var_F0], rax
0x18008b41a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008b41f  mov     edx, 25Fh
0x18008b424  jmp     short loc_18008B3AE
0x18008b426  test    r13, r13
0x18008b429  jnz     short loc_18008B487
0x18008b42b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b432  mov     edi, 80004003h
0x18008b437  mov     [rbp+57h+var_78], edi
0x18008b43a  test    rcx, rcx
0x18008b43d  jz      short loc_18008B47D
0x18008b43f  lea     ebx, [r13+3]
0x18008b443  xor     edx, edx
0x18008b445  mov     r8d, ebx
0x18008b448  lea     r9, aNoUpdateResult; "No update result specified"
0x18008b44f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008b454  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b45b  lea     rax, [rbp+57h+var_78]
0x18008b45f  mov     [rbp+57h+var_80], rax
0x18008b463  lea     r9, asc_1802EE7AC; ": {}"
0x18008b46a  lea     rax, [rbp+57h+var_80]
0x18008b46e  mov     r8d, ebx
0x18008b471  mov     dl, 1
0x18008b473  mov     [rsp+110h+var_F0], rax
0x18008b478  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008b47d  mov     edx, 260h
0x18008b482  jmp     loc_18008B3AE
0x18008b487  lea     rdx, [rbp+57h+var_68]; struct _XML_TOKEN *
0x18008b48b  mov     rcx, rdi; struct _XML_TOKENIZATION_STATE *
0x18008b48e  call    ?PeekNextToken@@YAJPEAU_XML_TOKENIZATION_STATE@@PEAU_XML_TOKEN@@@Z; PeekNextToken(_XML_TOKENIZATION_STATE *,_XML_TOKEN *)
0x18008b493  mov     esi, eax
0x18008b495  test    eax, eax
0x18008b497  js      loc_18008C6C4
0x18008b49d  cmp     dword ptr [rbp+57h+var_58+8], 7
0x18008b4a1  jnz     loc_18008B530
0x18008b4a7  lea     r8, [rbp+57h+var_68]
0x18008b4ab  mov     edx, 7
0x18008b4b0  mov     rcx, rdi
0x18008b4b3  call    ?ExpectToken@@YAJPEAU_XML_TOKENIZATION_STATE@@W4XML_TOKENIZATION_SPECIFIC_STATE@@PEAU_XML_TOKEN@@@Z; ExpectToken(_XML_TOKENIZATION_STATE *,XML_TOKENIZATION_SPECIFIC_STATE,_XML_TOKEN *)
0x18008b4b8  mov     esi, eax
0x18008b4ba  test    eax, eax
0x18008b4bc  js      loc_18008B772
0x18008b4c2  lea     r8, [rbp+57h+var_A8]; struct _XML_TOKEN *
0x18008b4c6  mov     rcx, rdi; struct _XML_TOKENIZATION_STATE *
0x18008b4c9  lea     rdx, [rbp+57h+var_68]; struct _XML_TOKEN *
0x18008b4cd  call    ?GetValue@@YAJPEAU_XML_TOKENIZATION_STATE@@PEBU_XML_TOKEN@@PEAU2@@Z; GetValue(_XML_TOKENIZATION_STATE *,_XML_TOKEN const *,_XML_TOKEN *)
0x18008b4d2  mov     esi, eax
0x18008b4d4  test    eax, eax
0x18008b4d6  jns     short loc_18008B487
0x18008b4d8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b4df  mov     [rbp+57h+var_78], eax
0x18008b4e2  test    rcx, rcx
0x18008b4e5  jz      short loc_18008B526
0x18008b4e7  mov     ebx, 3
0x18008b4ec  lea     r9, aFailedToGetVal_0; "Failed to get value."
0x18008b4f3  mov     r8d, ebx
0x18008b4f6  xor     edx, edx
0x18008b4f8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008b4fd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b504  lea     rax, [rbp+57h+var_78]
0x18008b508  mov     [rbp+57h+var_80], rax
0x18008b50c  lea     r9, asc_1802EE7AC; ": {}"
0x18008b513  lea     rax, [rbp+57h+var_80]
0x18008b517  mov     r8d, ebx
0x18008b51a  mov     dl, 1
0x18008b51c  mov     [rsp+110h+var_F0], rax
0x18008b521  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008b526  mov     edx, 26Fh
0x18008b52b  jmp     loc_18008C717
0x18008b530  lea     rax, [rbp+57h+var_74]
0x18008b534  mov     byte ptr [rsp+110h+var_E0], r15b; bool
0x18008b539  mov     [rsp+110h+var_E8], rax; unsigned __int16 *
0x18008b53e  lea     r9, [rbp+57h+var_88]; bool *
0x18008b542  lea     rax, [rbp+57h+var_68]
0x18008b546  mov     rdx, rdi; struct _XML_TOKENIZATION_STATE *
0x18008b549  lea     r8, ?UPDATE_TYPE_ATTRIBUTE_MAP@@3PAUenumType@@A; struct enumType *
0x18008b550  mov     [rsp+110h+var_F0], rax; int
0x18008b555  mov     rcx, r14; struct ParsingSession *
0x18008b558  call    ?GetNextAttributeEnumValue@@YAJPEAUParsingSession@@PEAU_XML_TOKENIZATION_STATE@@QEAUenumType@@PEA_NPEAU_XML_TOKEN@@PEAG_N@Z; GetNextAttributeEnumValue(ParsingSession *,_XML_TOKENIZATION_STATE *,enumType * const,bool *,_XML_TOKEN *,ushort *,bool)
0x18008b55d  mov     rcx, rdi; struct _XML_TOKENIZATION_STATE *
0x18008b560  test    eax, eax
0x18008b562  jnz     loc_18008B6CF
0x18008b568  cmp     [rbp+57h+var_88], r15b
0x18008b56c  jnz     loc_18008B9F5
0x18008b572  lea     r8, [rbp+57h+var_A8]; struct _XML_TOKEN *
0x18008b576  lea     rdx, [rbp+57h+var_68]; struct _XML_TOKEN *
0x18008b57a  call    ?GetValue@@YAJPEAU_XML_TOKENIZATION_STATE@@PEBU_XML_TOKEN@@PEAU2@@Z; GetValue(_XML_TOKENIZATION_STATE *,_XML_TOKEN const *,_XML_TOKEN *)
0x18008b57f  mov     esi, eax
0x18008b581  test    eax, eax
0x18008b583  js      loc_18008B99D
0x18008b589  movzx   ecx, [rbp+57h+var_74]
0x18008b58d  sub     ecx, 1
0x18008b590  jz      loc_18008B689
0x18008b596  sub     ecx, 1
0x18008b599  jz      loc_18008B65B
0x18008b59f  sub     ecx, 1
0x18008b5a2  jz      loc_18008B62D
0x18008b5a8  cmp     ecx, 1
0x18008b5ab  jnz     loc_18008B827
0x18008b5b1  lea     r8, [r13+20h]; unsigned int *
0x18008b5b5  cmp     [r8], r15d
0x18008b5b8  jnz     loc_18008B7CA
0x18008b5be  mov     rdx, [rbp+57h+var_A8+8]; unsigned __int64
0x18008b5c2  mov     rcx, [rbp+57h+var_A8]; void *
0x18008b5c6  call    ?GetUINTFromString@@YAJQEAX_KPEAI@Z; GetUINTFromString(void * const,unsigned __int64,uint *)
0x18008b5cb  mov     esi, eax
0x18008b5cd  test    eax, eax
0x18008b5cf  jns     loc_18008B487
0x18008b5d5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b5dc  mov     [rbp+57h+var_78], eax
0x18008b5df  test    rcx, rcx
0x18008b5e2  jz      short loc_18008B623
0x18008b5e4  mov     ebx, 3
0x18008b5e9  lea     r9, aFailedToGetDow_0; "Failed to get download size."
0x18008b5f0  mov     r8d, ebx
0x18008b5f3  xor     edx, edx
0x18008b5f5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008b5fa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b601  lea     rax, [rbp+57h+var_78]
0x18008b605  mov     [rbp+57h+var_80], rax
0x18008b609  lea     r9, asc_1802EE7AC; ": {}"
0x18008b610  lea     rax, [rbp+57h+var_80]
0x18008b614  mov     r8d, ebx
0x18008b617  mov     dl, 1
0x18008b619  mov     [rsp+110h+var_F0], rax
0x18008b61e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008b623  mov     edx, 2ACh
0x18008b628  jmp     loc_18008C717
0x18008b62d  lea     rcx, [r13+18h]; wchar_t **
0x18008b631  cmp     [rcx], r15
0x18008b634  jnz     loc_18008B886
0x18008b63a  lea     r9, [r14+30h]; struct CMemoryAllocator *
0x18008b63e  mov     rdx, rdi; struct _XML_TOKENIZATION_STATE *
0x18008b641  lea     r8, [rbp+57h+var_A8]; struct _XML_EXTENT *
0x18008b645  call    ?DuplicateXmlString@@YAJPEAPEA_WPEAU_XML_TOKENIZATION_STATE@@PEAU_XML_EXTENT@@PEAVCMemoryAllocator@@@Z; DuplicateXmlString(wchar_t * *,_XML_TOKENIZATION_STATE *,_XML_EXTENT *,CMemoryAllocator *)
0x18008b64a  mov     ebx, eax
0x18008b64c  test    eax, eax
0x18008b64e  jns     loc_18008B487
0x18008b654  mov     edx, 2A3h
0x18008b659  jmp     short loc_18008B6B5
0x18008b65b  lea     rcx, [r13+10h]; wchar_t **
0x18008b65f  cmp     [rcx], r15
0x18008b662  jnz     loc_18008B8E3
0x18008b668  lea     r9, [r14+30h]; struct CMemoryAllocator *
0x18008b66c  mov     rdx, rdi; struct _XML_TOKENIZATION_STATE *
0x18008b66f  lea     r8, [rbp+57h+var_A8]; struct _XML_EXTENT *
0x18008b673  call    ?DuplicateXmlString@@YAJPEAPEA_WPEAU_XML_TOKENIZATION_STATE@@PEAU_XML_EXTENT@@PEAVCMemoryAllocator@@@Z; DuplicateXmlString(wchar_t * *,_XML_TOKENIZATION_STATE *,_XML_EXTENT *,CMemoryAllocator *)
0x18008b678  mov     ebx, eax
0x18008b67a  test    eax, eax
0x18008b67c  jns     loc_18008B487
0x18008b682  mov     edx, 298h
0x18008b687  jmp     short loc_18008B6B5
0x18008b689  lea     rcx, [r13+8]; wchar_t **
0x18008b68d  cmp     [rcx], r15
0x18008b690  jnz     loc_18008B940
0x18008b696  lea     r9, [r14+30h]; struct CMemoryAllocator *
0x18008b69a  mov     rdx, rdi; struct _XML_TOKENIZATION_STATE *
0x18008b69d  lea     r8, [rbp+57h+var_A8]; struct _XML_EXTENT *
0x18008b6a1  call    ?DuplicateXmlString@@YAJPEAPEA_WPEAU_XML_TOKENIZATION_STATE@@PEAU_XML_EXTENT@@PEAVCMemoryAllocator@@@Z; DuplicateXmlString(wchar_t * *,_XML_TOKENIZATION_STATE *,_XML_EXTENT *,CMemoryAllocator *)
0x18008b6a6  mov     ebx, eax
0x18008b6a8  test    eax, eax
0x18008b6aa  jns     loc_18008B487
0x18008b6b0  mov     edx, 28Dh; void *
0x18008b6b5  mov     rcx, [rbp+5Fh]; this
0x18008b6b9  lea     r8, aOnecoreBaseCbs_131; "onecore\\base\\cbs\\parser\\update.cpp"
0x18008b6c0  mov     r9d, ebx; char *
0x18008b6c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008b6c8  mov     eax, ebx
0x18008b6ca  jmp     loc_18008C72C
0x18008b6cf  lea     r8, [rbp+57h+var_A8]; struct _XML_TOKEN *
0x18008b6d3  lea     rdx, [rbp+57h+var_68]; struct _XML_TOKEN *
0x18008b6d7  call    ?GetValue@@YAJPEAU_XML_TOKENIZATION_STATE@@PEBU_XML_TOKEN@@PEAU2@@Z; GetValue(_XML_TOKENIZATION_STATE *,_XML_TOKEN const *,_XML_TOKEN *)
0x18008b6dc  mov     esi, eax
0x18008b6de  test    eax, eax
0x18008b6e0  js      loc_18008C66F
0x18008b6e6  lea     rax, [rbp+57h+var_D0]
0x18008b6ea  mov     [rsp+110h+var_E0], r13; struct COMMON_UPDATE_ATTRIBUTES_GROUP *
0x18008b6ef  mov     [rsp+110h+var_E8], rax; bool *
0x18008b6f4  lea     r9, [rbp+57h+var_A8]; struct _XML_TOKEN *
0x18008b6f8  lea     rax, [rbp+57h+var_CF]
0x18008b6fc  mov     rdx, r14; struct ParsingSession *
0x18008b6ff  lea     r8, [rbp+57h+var_68]; struct _XML_TOKEN *
0x18008b703  mov     [rsp+110h+var_F0], rax; bool *
0x18008b708  mov     rcx, rdi; struct _XML_TOKENIZATION_STATE *
0x18008b70b  call    ?ProcessCommonUpdateAttributesGroup@@YAJPEAU_XML_TOKENIZATION_STATE@@PEAUParsingSession@@PEBU_XML_TOKEN@@2PEA_N3PEAUCOMMON_UPDATE_ATTRIBUTES_GROUP@@@Z; ProcessCommonUpdateAttributesGroup(_XML_TOKENIZATION_STATE *,ParsingSession *,_XML_TOKEN const *,_XML_TOKEN const *,bool *,bool *,COMMON_UPDATE_ATTRIBUTES_GROUP *)
0x18008b710  mov     esi, eax
0x18008b712  test    eax, eax
0x18008b714  jns     loc_18008B487
0x18008b71a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b721  mov     dword ptr [rbp+57h+var_80], eax
0x18008b724  test    rcx, rcx
0x18008b727  jz      short loc_18008B768
0x18008b729  mov     ebx, 3
0x18008b72e  lea     r9, aInvalidUpdateA_0; "Invalid update attributes"
0x18008b735  mov     r8d, ebx
0x18008b738  xor     edx, edx
0x18008b73a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008b73f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b746  lea     rax, [rbp+57h+var_80]
0x18008b74a  mov     qword ptr [rbp+57h+var_C8], rax
0x18008b74e  lea     r9, asc_1802EE7AC; ": {}"
0x18008b755  lea     rax, [rbp+57h+var_C8]
0x18008b759  mov     r8d, ebx
0x18008b75c  mov     dl, 1
0x18008b75e  mov     [rsp+110h+var_F0], rax
0x18008b763  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18008b768  mov     edx, 2BEh
0x18008b76d  jmp     loc_18008C717
0x18008b772  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b779  mov     [rbp+57h+var_78], esi
0x18008b77c  test    rcx, rcx
0x18008b77f  jz      short loc_18008B7C0
0x18008b781  mov     ebx, 3
0x18008b786  lea     r9, aFailedToExpect_0; "Failed to expect token"
0x18008b78d  mov     r8d, ebx
0x18008b790  xor     edx, edx
0x18008b792  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18008b797  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18008b79e  lea     rax, [rbp+57h+var_78]
0x18008b7a2  mov     [rbp+57h+var_80], rax
0x18008b7a6  lea     r9, asc_1802EE7AC; ": {}"
0x18008b7ad  lea     rax, [rbp+57h+var_80]
0x18008b7b1  mov     r8d, ebx
0x18008b7b4  mov     dl, 1
0x18008b7b6  mov     [rsp+110h+var_F0], rax
  ... truncated ...
```
