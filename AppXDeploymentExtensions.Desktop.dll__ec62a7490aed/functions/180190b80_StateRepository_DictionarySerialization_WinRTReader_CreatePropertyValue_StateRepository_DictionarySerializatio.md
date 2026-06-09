# StateRepository::DictionarySerialization::WinRTReader::CreatePropertyValue(StateRepository::DictionarySerialization::DataType,uint,unsigned __int64,void const *,RoVariant &)

- ea: `0x180190b80`
- end: `0x180192061`
- name: `?CreatePropertyValue@WinRTReader@DictionarySerialization@StateRepository@@AEAAJW4DataType@23@I_KPEBXAEAVRoVariant@@@Z`
- size: `5345`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1801924d8`

## callees

- `0x180006970`
- `0x180012fc8`
- `0x18001adb4`
- `0x180023bd0`
- `0x180048854`
- `0x180059424`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1800af1fc`
- `0x1800da6cc`
- `0x180190b80`
- `0x180192068`
- `0x180192450`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801912a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180191ef0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801912a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180191ef0`

## string_xrefs

- `0x180190bcc`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180190dad`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180190e05`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180191250`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x1801913e7`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180191423`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180191489`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x1801919ca`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180191a9b`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180191aec`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180191b13`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180191b34`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180191b5e`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180191b88`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180191c08`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180191c5c`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180191f43`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`
- `0x180191fd9`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtreader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StateRepository::DictionarySerialization::WinRTReader::CreatePropertyValue(
        StateRepository::DictionarySerialization::WinRTReader *a1,
        int a2,
        unsigned int a3,
        unsigned __int64 a4,
        PCWSTR sourceString,
        unsigned __int64 a6)
{
  unsigned __int64 v7; // r12
  const WCHAR *v10; // rsi
  __int64 v11; // rdx
  unsigned int IsAvailable; // edi
  __int64 v13; // rdx
  __int64 v15; // r14
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  __int64 v19; // rdx
  HRESULT v20; // ebx
  __int64 v21; // rdx
  char v22; // cl
  unsigned int v23; // esi
  int v24; // ebx
  int v25; // ebx
  int v26; // ebx
  int v27; // ebx
  int v28; // ebx
  int v29; // ebx
  int v30; // ebx
  int v31; // ebx
  int v32; // ebx
  int v33; // ebx
  int v34; // ebx
  UINT32 v35; // edx
  int v36; // eax
  int v37; // eax
  int v38; // ebx
  int v39; // ebx
  int v40; // ebx
  int v41; // ebx
  int v42; // ebx
  int v43; // ebx
  int v44; // ebx
  int v45; // ebx
  int v46; // ebx
  int v47; // ebx
  int v48; // ebx
  int v49; // ebx
  int v50; // ebx
  int v51; // ebx
  int v52; // ebx
  unsigned __int64 v53; // rax
  _QWORD *v54; // rbx
  char *Reserved1; // rax
  unsigned __int64 i; // rdi
  struct IInspectable **v57; // r9
  void *v58; // rax
  unsigned __int64 v59; // rdx
  unsigned __int64 j; // r14
  __int64 v61; // rcx
  __int64 v62; // rdx
  unsigned __int64 k; // rdi
  __int64 v64; // rcx
  unsigned __int64 v65; // rax
  HSTRING_HEADER *v66; // rbx
  unsigned __int64 v67; // rax
  HSTRING *v68; // rdi
  unsigned __int64 v69; // rcx
  unsigned __int64 v70; // rdx
  __int64 v71; // r10
  HRESULT StringReference; // eax
  unsigned __int64 v73; // r9
  __int64 v74; // rdx
  const struct std::nothrow_t *v75; // rdx
  const struct std::nothrow_t *v76; // rdx
  const struct std::nothrow_t *v77; // rdx
  int v78; // [rsp+20h] [rbp-59h]
  int v79; // [rsp+20h] [rbp-59h]
  unsigned __int64 v80; // [rsp+30h] [rbp-49h] BYREF
  __int64 v81; // [rsp+38h] [rbp-41h] BYREF
  HSTRING string; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int64 v83; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int64 v84[2]; // [rsp+50h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]

  v7 = a3;
  v10 = sourceString;
  IsAvailable = StateRepository::DictionarySerialization::WinRTReader::EnsurePropertyValueStaticsIsAvailable(a1);
  if ( (IsAvailable & 0x80000000) != 0 )
  {
    v13 = 198;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
      (const char *)IsAvailable,
      v78);
    return IsAvailable;
  }
  v15 = *(_QWORD *)a1;
  if ( a2 > 21 )
  {
    if ( a2 <= 33 )
    {
      if ( a2 == 33 )
      {
        if ( a4 != 4 * v7 )
        {
          v19 = 445;
          goto LABEL_36;
        }
        v80 = a6;
        v81 = 0;
        v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, __int64 *))(*(_QWORD *)v15 + 264LL))(
                v15,
                (unsigned int)v7,
                sourceString,
                &v81);
        RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
        if ( v20 < 0 )
        {
          v21 = 446;
          goto LABEL_40;
        }
      }
      else if ( a2 > 28 )
      {
        v42 = a2 - 29;
        if ( v42 )
        {
          v43 = v42 - 1;
          if ( v43 )
          {
            v44 = v43 - 1;
            if ( v44 )
            {
              if ( v44 != 1 )
                return 2154233861LL;
              if ( a4 != 16 * v7 )
              {
                v19 = 438;
                goto LABEL_36;
              }
              v80 = a6;
              v81 = 0;
              v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, __int64 *))(*(_QWORD *)v15 + 352LL))(
                      v15,
                      (unsigned int)v7,
                      sourceString,
                      &v81);
              RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
              if ( v20 < 0 )
              {
                v21 = 439;
                goto LABEL_40;
              }
            }
            else
            {
              if ( a4 != 8 * v7 )
              {
                v19 = 430;
                goto LABEL_36;
              }
              v80 = a6;
              v81 = 0;
              v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, __int64 *))(*(_QWORD *)v15 + 336LL))(
                      v15,
                      (unsigned int)v7,
                      sourceString,
                      &v81);
              RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
              if ( v20 < 0 )
              {
                v21 = 431;
                goto LABEL_40;
              }
            }
          }
          else
          {
            if ( a4 != 8 * v7 )
            {
              v19 = 422;
              goto LABEL_36;
            }
            v80 = a6;
            v81 = 0;
            v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, __int64 *))(*(_QWORD *)v15 + 248LL))(
                    v15,
                    (unsigned int)v7,
                    sourceString,
                    &v81);
            RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
            if ( v20 < 0 )
            {
              v21 = 423;
              goto LABEL_40;
            }
          }
        }
        else
        {
          if ( a4 != 4 * v7 )
          {
            v19 = 415;
            goto LABEL_36;
          }
          v80 = a6;
          v81 = 0;
          v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, __int64 *))(*(_QWORD *)v15 + 232LL))(
                  v15,
                  (unsigned int)v7,
                  sourceString,
                  &v81);
          RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
          if ( v20 < 0 )
          {
            v21 = 416;
            goto LABEL_40;
          }
        }
      }
      else if ( a2 == 28 )
      {
        if ( a4 != 2 * v7 )
        {
          v19 = 408;
          goto LABEL_36;
        }
        v80 = a6;
        v81 = 0;
        v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, __int64 *))(*(_QWORD *)v15 + 216LL))(
                v15,
                (unsigned int)v7,
                sourceString,
                &v81);
        RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
        if ( v20 < 0 )
        {
          v21 = 409;
          goto LABEL_40;
        }
      }
      else
      {
        v38 = a2 - 22;
        if ( v38 )
        {
          v39 = v38 - 2;
          if ( v39 )
          {
            v40 = v39 - 1;
            if ( v40 )
            {
              v41 = v40 - 1;
              if ( v41 )
              {
                if ( v41 != 1 )
                  return 2154233861LL;
                if ( a4 != 16 * v7 )
                {
                  v19 = 401;
                  goto LABEL_36;
                }
                v80 = a6;
                v81 = 0;
                v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, __int64 *))(*(_QWORD *)v15 + 312LL))(
                        v15,
                        (unsigned int)v7,
                        sourceString,
                        &v81);
                RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
                if ( v20 < 0 )
                {
                  v21 = 402;
                  goto LABEL_40;
                }
              }
              else
              {
                if ( a4 != 8 * v7 )
                {
                  v19 = 394;
                  goto LABEL_36;
                }
                v80 = a6;
                v81 = 0;
                v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, __int64 *))(*(_QWORD *)v15 + 272LL))(
                        v15,
                        (unsigned int)v7,
                        sourceString,
                        &v81);
                RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
                if ( v20 < 0 )
                {
                  v21 = 395;
                  goto LABEL_40;
                }
              }
            }
            else
            {
              if ( a4 != 8 * v7 )
              {
                v19 = 387;
                goto LABEL_36;
              }
              v80 = a6;
              v81 = 0;
              v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, __int64 *))(*(_QWORD *)v15 + 320LL))(
                      v15,
                      (unsigned int)v7,
                      sourceString,
                      &v81);
              RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
              if ( v20 < 0 )
              {
                v21 = 388;
                goto LABEL_40;
              }
            }
          }
          else
          {
            if ( a4 != 2 * v7 )
            {
              v19 = 379;
              goto LABEL_36;
            }
            v80 = a6;
            v81 = 0;
            v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, __int64 *))(*(_QWORD *)v15 + 280LL))(
                    v15,
                    (unsigned int)v7,
                    sourceString,
                    &v81);
            RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
            if ( v20 < 0 )
            {
              v21 = 380;
              goto LABEL_40;
            }
          }
        }
        else
        {
          if ( a4 != v7 )
          {
            v19 = 372;
            goto LABEL_36;
          }
          v80 = a6;
          v81 = 0;
          v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, __int64 *))(*(_QWORD *)v15 + 288LL))(
                  v15,
                  (unsigned int)v7,
                  sourceString,
                  &v81);
          RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
          if ( v20 < 0 )
          {
            v21 = 373;
            goto LABEL_40;
          }
        }
      }
      return 0;
    }
    v45 = a2 - 34;
    if ( !v45 )
    {
      if ( a4 != 8 * v7 )
      {
        v19 = 453;
        goto LABEL_36;
      }
      v80 = a6;
      v81 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, __int64 *))(*(_QWORD *)v15 + 344LL))(
              v15,
              (unsigned int)v7,
              sourceString,
              &v81);
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
      if ( v20 < 0 )
      {
        v21 = 454;
        goto LABEL_40;
      }
      return 0;
    }
    v46 = v45 - 1;
    if ( !v46 )
    {
      v65 = 24 * v7;
      if ( !is_mul_ok(v7, 0x18u) )
        v65 = -1;
      v66 = (HSTRING_HEADER *)operator new[](v65, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v66 )
      {
        IsAvailable = -2147024882;
        v13 = 465;
        goto LABEL_3;
      }
      v67 = 8 * v7;
      if ( !is_mul_ok(v7, 8u) )
        v67 = -1;
      v68 = (HSTRING *)operator new[](v67, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v68 )
      {
        IsAvailable = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D4,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
          (const char *)0x8007000ELL,
          v78);
        operator delete(v66, v77);
        return IsAvailable;
      }
      v69 = 0;
      v70 = 0;
      while ( 1 )
      {
        v84[0] = v70;
        if ( v70 >= v7 )
          break;
        if ( v69 + 4 > a4 )
        {
          v74 = 475;
          goto LABEL_262;
        }
        v71 = *(unsigned int *)v10;
        if ( (unsigned int)v71 > 0x100000 )
        {
          v74 = 477;
          goto LABEL_262;
        }
        v80 = *(unsigned int *)v10;
        v83 = v71 + v69 + 4;
        if ( v83 > a4 )
        {
          v74 = 484;
          goto LABEL_262;
        }
        hstringHeader.Reserved.Reserved1 = (PVOID)(v10 + 2);
        StringReference = WindowsCreateStringReference(
                            (PCWSTR)((unsigned __int64)(v10 + 2) & -(__int64)((_DWORD)v71 != 0)),
                            (unsigned int)v71 >> 1 != 0 ? ((unsigned int)v71 >> 1) - 1 : 0,
                            &v66[v70],
                            &v68[v70]);
        v23 = StringReference;
        if ( StringReference < 0 )
        {
          v73 = (unsigned int)StringReference;
          v74 = 488;
LABEL_264:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v74,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
            (const char *)v73,
            v78);
          operator delete(v68, (const struct std::nothrow_t *)8);
          operator delete(v66, v75);
          return v23;
        }
        v10 = (const WCHAR *)((char *)hstringHeader.Reserved.Reserved1 + v80);
        v70 = v84[0] + 1;
        v69 = v83;
      }
      if ( v69 == a4 )
      {
        v80 = a6;
        v81 = 0;
        v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *, __int64 *))(*(_QWORD *)v15 + 296LL))(
                v15,
                (unsigned int)v7,
                v68,
                &v81);
        RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
        if ( (v23 & 0x80000000) == 0 )
        {
          operator delete(v68, (const struct std::nothrow_t *)8);
          operator delete(v66, v76);
          return 0;
        }
        v74 = 495;
      }
      else
      {
        v74 = 494;
LABEL_262:
        v23 = -2140733435;
      }
      v73 = v23;
      goto LABEL_264;
    }
    v47 = v46 - 1;
    if ( !v47 )
    {
      if ( a4 != 8 * v7 )
      {
        v19 = 502;
        goto LABEL_36;
      }
      v80 = a6;
      v81 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, __int64 *))(*(_QWORD *)v15 + 328LL))(
              v15,
              (unsigned int)v7,
              sourceString,
              &v81);
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
      if ( v20 < 0 )
      {
        v21 = 503;
        goto LABEL_40;
      }
      return 0;
    }
    v48 = v47 - 1;
    if ( !v48 )
    {
      if ( a4 != v7 )
      {
        v19 = 509;
        goto LABEL_36;
      }
      v80 = a6;
      v81 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, __int64 *))(*(_QWORD *)v15 + 208LL))(
              v15,
              (unsigned int)v7,
              sourceString,
              &v81);
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
      if ( v20 < 0 )
      {
        v21 = 510;
        goto LABEL_40;
      }
      return 0;
    }
    v49 = v48 - 1;
    if ( !v49 )
    {
      if ( a4 != 2 * v7 )
      {
        v19 = 516;
        goto LABEL_36;
      }
      v80 = a6;
      v81 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, __int64 *))(*(_QWORD *)v15 + 224LL))(
              v15,
              (unsigned int)v7,
              sourceString,
              &v81);
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
      if ( v20 < 0 )
      {
        v21 = 517;
        goto LABEL_40;
      }
      return 0;
    }
    v50 = v49 - 1;
    if ( !v50 )
    {
      if ( a4 != 4 * v7 )
      {
        v19 = 523;
        goto LABEL_36;
      }
      v80 = a6;
      v81 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, __int64 *))(*(_QWORD *)v15 + 240LL))(
              v15,
              (unsigned int)v7,
              sourceString,
              &v81);
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
      if ( v20 < 0 )
      {
        v21 = 524;
        goto LABEL_40;
      }
      return 0;
    }
    v51 = v50 - 1;
    if ( !v51 )
    {
      if ( a4 != 8 * v7 )
      {
        v19 = 530;
        goto LABEL_36;
      }
      v80 = a6;
      v81 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, PCWSTR, __int64 *))(*(_QWORD *)v15 + 256LL))(
              v15,
              (unsigned int)v7,
              sourceString,
              &v81);
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
      if ( v20 < 0 )
      {
        v21 = 531;
        goto LABEL_40;
      }
      return 0;
    }
    v52 = v51 - 1;
    if ( v52 )
    {
      if ( v52 != 1 )
        return 2154233861LL;
      v80 = v7;
      v53 = 8 * v7;
      if ( !is_mul_ok(v7, 8u) )
        v53 = -1;
      v54 = operator new[](v53, (const struct std::nothrow_t *)&std::nothrow);
      if ( !v54 )
      {
        IsAvailable = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x220,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
          (const char *)0x8007000ELL,
          v78);
        operator delete(0, (const struct std::nothrow_t *)8);
        return IsAvailable;
      }
      Reserved1 = 0;
      for ( i = 0; i < v7; ++i )
      {
        string = 0;
        v57 = (struct IInspectable **)&v54[i];
        *v57 = 0;
        v84[0] = 0;
        v58 = Reserved1 + 4;
        hstringHeader.Reserved.Reserved1 = v58;
        if ( (unsigned __int64)v58 > a4 )
        {
          v23 = -2140733435;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x229,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
            (const char *)0x80670005LL,
            v78);
          wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&string);
          goto LABEL_214;
        }
        if ( *(_DWORD *)v10 > 0x100000u )
        {
          v23 = -2140733435;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x22B,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
            (const char *)0x80670005LL,
            v78);
          wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&string);
          goto LABEL_214;
        }
        v59 = *(unsigned int *)v10;
        if ( (unsigned __int64)v58 + v59 > a4 )
        {
          v23 = -2140733435;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x22F,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
            (const char *)0x80670005LL,
            v78);
          wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&string);
          goto LABEL_214;
        }
        v83 = (unsigned __int64)(v10 + 2);
        v23 = StateRepository::DictionarySerialization::WinRTReader::Deserialize(
                (StateRepository::DictionarySerialization::WinRTReader *)&string,
                v59,
                v10 + 2,
                v57,
                v84);
        if ( (v23 & 0x80000000) != 0 )
        {
          for ( j = 0; j < i; ++j )
          {
            v61 = v54[j];
            if ( !v61 )
              wil::details::in1diag3::_FailFast_Hr(
                retaddr,
                (void *)0x235,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
                (const char *)0x8000FFFFLL,
                v78);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x238,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
            (const char *)v23,
            v78);
          wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&string);
          goto LABEL_214;
        }
        v10 = (const WCHAR *)(v84[0] + v83);
        hstringHeader.Reserved.Reserved1 = (char *)hstringHeader.Reserved.Reserved1 + v84[0];
        if ( hstringHeader.Reserved.Reserved1 > (PVOID)a4 )
        {
          v23 = -2140733435;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x23D,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
            (const char *)0x80670005LL,
            v78);
          wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&string);
LABEL_214:
          operator delete(v54, (const struct std::nothrow_t *)8);
          return v23;
        }
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&string);
        Reserved1 = (char *)hstringHeader.Reserved.Reserved1;
      }
      if ( Reserved1 == (char *)a4 )
      {
        *(_OWORD *)&hstringHeader.Reserved.Reserved1 = a6;
        v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, char *))(*(_QWORD *)v15 + 304LL))(
                v15,
                (unsigned int)v7,
                v54,
                &hstringHeader.Reserved.Reserved2[8]);
        RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&hstringHeader);
        if ( (v23 & 0x80000000) == 0 )
        {
          for ( k = 0; k < v80; ++k )
          {
            v64 = v54[k];
            if ( !v64 )
              wil::details::in1diag3::_FailFast_Hr(
                retaddr,
                (void *)0x244,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
                (const char *)0x8000FFFFLL,
                v78);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
          }
          operator delete(v54, (const struct std::nothrow_t *)8);
          return 0;
        }
        v62 = 577;
      }
      else
      {
        v23 = -2140733435;
        v62 = 576;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v62,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
        (const char *)v23,
        v78);
      goto LABEL_214;
    }
    return 2147500033LL;
  }
  if ( a2 == 21 )
  {
    v83 = 0;
    string = 0;
    v84[0] = 0;
    v37 = StateRepository::DictionarySerialization::WinRTReader::Deserialize(
            (StateRepository::DictionarySerialization::WinRTReader *)&v83,
            a4,
            sourceString,
            (struct IInspectable **)&string,
            v84);
    v20 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16A,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
        (const char *)(unsigned int)v37,
        v79);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&string);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v83);
      return (unsigned int)v20;
    }
    if ( v84[0] != a4 )
    {
      v23 = -2140733435;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16B,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
        (const char *)0x80670005LL,
        v79);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&string);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v83);
      return v23;
    }
    v80 = a6;
    v81 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v15 + 152LL))(v15, string, &v81);
    RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x16C,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
        (const char *)(unsigned int)v20,
        v79);
      Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&string);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v83);
      return (unsigned int)v20;
    }
    Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&string);
    wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v83);
    return 0;
  }
  if ( a2 > 11 )
  {
    v27 = a2 - 12;
    if ( !v27 )
    {
      if ( a4 != 4 )
      {
        v19 = 285;
        goto LABEL_36;
      }
      v80 = a6;
      v81 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v15 + 112LL))(v15, v11, &v81);
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
      if ( v20 < 0 )
      {
        v21 = 286;
        goto LABEL_40;
      }
      return 0;
    }
    v28 = v27 - 1;
    if ( !v28 )
    {
      if ( a4 != 8 )
      {
        v19 = 293;
        goto LABEL_36;
      }
      v80 = a6;
      v81 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 192LL))(
              v15,
              *(_QWORD *)sourceString,
              &v81);
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
      if ( v20 < 0 )
      {
        v21 = 294;
        goto LABEL_40;
      }
      return 0;
    }
    v29 = v28 - 1;
    if ( !v29 )
    {
      v35 = 0;
      v83 = 0;
      if ( a4 )
      {
        v36 = StringCchLengthW(sourceString, a4 >> 1, &v83);
        if ( v36 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x12F,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
            (const char *)(unsigned int)v36,
            v78);
          v19 = 303;
          goto LABEL_36;
        }
        v35 = v83;
        if ( a4 != 2 * v83 + 2 )
        {
          v19 = 304;
          goto LABEL_36;
        }
      }
      else
      {
        v10 = &Value;
      }
      memset(&hstringHeader, 0, sizeof(hstringHeader));
      string = 0;
      v20 = WindowsCreateStringReference(v10, v35, &hstringHeader, &string);
      if ( v20 < 0 )
      {
        v21 = 312;
        goto LABEL_40;
      }
      v80 = a6;
      v81 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v15 + 144LL))(v15, string, &v81);
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
      if ( v20 < 0 )
      {
        v21 = 313;
        goto LABEL_40;
      }
      return 0;
    }
    v30 = v29 - 1;
    if ( !v30 )
    {
      if ( a4 != 8 )
      {
        v19 = 320;
        goto LABEL_36;
      }
      v80 = a6;
      v81 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 176LL))(
              v15,
              *(_QWORD *)sourceString,
              &v81);
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
      if ( v20 < 0 )
      {
        v21 = 321;
        goto LABEL_40;
      }
      return 0;
    }
    v31 = v30 - 1;
    if ( !v31 )
    {
      if ( a4 != 1 )
      {
        v19 = 327;
        goto LABEL_36;
      }
      v80 = a6;
      v81 = 0;
      LOBYTE(v11) = *(_BYTE *)sourceString;
      v20 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v15 + 56LL))(v15, v11, &v81);
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
      if ( v20 < 0 )
      {
        v21 = 328;
        goto LABEL_40;
      }
      return 0;
    }
    v32 = v31 - 1;
    if ( !v32 )
    {
      if ( a4 != 2 )
      {
        v19 = 334;
        goto LABEL_36;
      }
      v80 = a6;
      v81 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 72LL))(v15, *sourceString, &v81);
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
      if ( v20 < 0 )
      {
        v21 = 335;
        goto LABEL_40;
      }
      return 0;
    }
    v33 = v32 - 1;
    if ( !v33 )
    {
      if ( a4 != 4 )
      {
        v19 = 341;
        goto LABEL_36;
      }
      v80 = a6;
      v81 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 88LL))(
              v15,
              *(unsigned int *)sourceString,
              &v81);
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
      if ( v20 < 0 )
      {
        v21 = 342;
        goto LABEL_40;
      }
      return 0;
    }
    v34 = v33 - 1;
    if ( !v34 )
    {
      if ( a4 != 8 )
      {
        v19 = 348;
        goto LABEL_36;
      }
      v80 = a6;
      v81 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 104LL))(
              v15,
              *(_QWORD *)sourceString,
              &v81);
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
      if ( v20 < 0 )
      {
        v21 = 349;
        goto LABEL_40;
      }
      return 0;
    }
    if ( v34 != 1 )
      return 2154233861LL;
    return 2147500033LL;
  }
  if ( a2 == 11 )
  {
    if ( a4 != 16 )
    {
      v19 = 278;
      goto LABEL_36;
    }
    v80 = a6;
    v81 = 0;
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)sourceString;
    v20 = (*(__int64 (__fastcall **)(__int64, HSTRING_HEADER *, __int64 *))(*(_QWORD *)v15 + 200LL))(
            v15,
            &hstringHeader,
            &v81);
    RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
    if ( v20 < 0 )
    {
      v21 = 279;
      goto LABEL_40;
    }
    return 0;
  }
  if ( a2 > 6 )
  {
    v24 = a2 - 7;
    if ( v24 )
    {
      v25 = v24 - 1;
      if ( v25 )
      {
        v26 = v25 - 1;
        if ( v26 )
        {
          if ( v26 != 1 )
            return 2154233861LL;
          if ( a4 != 8 )
          {
            v19 = 270;
            goto LABEL_36;
          }
          v80 = a6;
          v81 = 0;
          v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 184LL))(
                  v15,
                  *(_QWORD *)sourceString,
                  &v81);
          RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
          if ( v20 < 0 )
          {
            v21 = 271;
            goto LABEL_40;
          }
        }
        else
        {
          if ( a4 != 8 )
          {
            v19 = 262;
            goto LABEL_36;
          }
          v80 = a6;
          v81 = 0;
          v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 96LL))(
                  v15,
                  *(_QWORD *)sourceString,
                  &v81);
          RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
          if ( v20 < 0 )
          {
            v21 = 263;
            goto LABEL_40;
          }
        }
      }
      else
      {
        if ( a4 != 4 )
        {
          v19 = 255;
          goto LABEL_36;
        }
        v80 = a6;
        v81 = 0;
        v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 80LL))(
                v15,
                *(unsigned int *)sourceString,
                &v81);
        RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
        if ( v20 < 0 )
        {
          v21 = 256;
          goto LABEL_40;
        }
      }
    }
    else
    {
      if ( a4 != 2 )
      {
        v19 = 248;
        goto LABEL_36;
      }
      v80 = a6;
      v81 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 64LL))(v15, *sourceString, &v81);
      RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
      if ( v20 < 0 )
      {
        v21 = 249;
        goto LABEL_40;
      }
    }
    return 0;
  }
  if ( a2 == 6 )
  {
    if ( a4 != 16 )
    {
      v19 = 241;
      goto LABEL_36;
    }
    v80 = a6;
    v81 = 0;
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = *(_OWORD *)sourceString;
    v20 = (*(__int64 (__fastcall **)(__int64, HSTRING_HEADER *, __int64 *))(*(_QWORD *)v15 + 160LL))(
            v15,
            &hstringHeader,
            &v81);
    RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
    if ( v20 < 0 )
    {
      v21 = 242;
      goto LABEL_40;
    }
    return 0;
  }
  if ( !a2 )
  {
    if ( a4 )
    {
      v19 = 204;
      goto LABEL_36;
    }
    v80 = a6;
    v81 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 48LL))(v15, &v81);
    RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
    if ( v20 < 0 )
    {
      v21 = 205;
      goto LABEL_40;
    }
    return 0;
  }
  v16 = a2 - 1;
  if ( !v16 )
  {
    v22 = *(_BYTE *)sourceString;
    if ( *(_BYTE *)sourceString >= 2u )
    {
      v19 = 211;
      goto LABEL_36;
    }
    if ( a4 != 1 )
    {
      v19 = 212;
      goto LABEL_36;
    }
    v80 = a6;
    v81 = 0;
    LOBYTE(v11) = v22 != 0;
    v20 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v15 + 136LL))(v15, v11, &v81);
    RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
    if ( v20 < 0 )
    {
      v21 = 213;
      goto LABEL_40;
    }
    return 0;
  }
  v17 = v16 - 2;
  if ( !v17 )
  {
    if ( a4 != 2 )
    {
      v19 = 219;
      goto LABEL_36;
    }
    v80 = a6;
    v81 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 128LL))(v15, *sourceString, &v81);
    RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
    if ( v20 < 0 )
    {
      v21 = 220;
      goto LABEL_40;
    }
    return 0;
  }
  v18 = v17 - 1;
  if ( !v18 )
  {
    if ( a4 != 8 )
    {
      v19 = 227;
      goto LABEL_36;
    }
    v80 = a6;
    v81 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 168LL))(
            v15,
            *(_QWORD *)sourceString,
            &v81);
    RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
    if ( v20 < 0 )
    {
      v21 = 228;
      goto LABEL_40;
    }
    return 0;
  }
  if ( v18 == 1 )
  {
    if ( a4 != 8 )
    {
      v19 = 234;
LABEL_36:
      v23 = -2140733435;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
        (const char *)0x80670005LL,
        v78);
      return v23;
    }
    v80 = a6;
    v81 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v15 + 120LL))(v15, v11, &v81);
    RoVariant::OutRef::~OutRef((RoVariant::OutRef *)&v80);
    if ( v20 < 0 )
    {
      v21 = 235;
LABEL_40:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtreader.cpp",
        (const char *)(unsigned int)v20,
        v78);
      return (unsigned int)v20;
    }
    return 0;
  }
  return 2154233861LL;
}

```

## disassembly

```asm
0x180190b80  mov     [rsp-8+arg_8], rbx
0x180190b85  push    rbp
0x180190b86  push    rsi
0x180190b87  push    rdi
0x180190b88  push    r12
0x180190b8a  push    r13
0x180190b8c  push    r14
0x180190b8e  push    r15
0x180190b90  lea     rbp, [rsp-17h]
0x180190b95  sub     rsp, 90h
0x180190b9c  mov     rax, cs:__security_cookie
0x180190ba3  xor     rax, rsp
0x180190ba6  mov     [rbp+47h+var_40], rax
0x180190baa  mov     r15, r9
0x180190bad  mov     r12d, r8d
0x180190bb0  mov     ebx, edx
0x180190bb2  mov     r14, rcx
0x180190bb5  mov     rsi, [rbp+47h+sourceString]
0x180190bb9  call    ?EnsurePropertyValueStaticsIsAvailable@WinRTReader@DictionarySerialization@StateRepository@@AEAAJXZ; StateRepository::DictionarySerialization::WinRTReader::EnsurePropertyValueStaticsIsAvailable(void)
0x180190bbe  mov     edi, eax
0x180190bc0  xor     r13d, r13d
0x180190bc3  test    eax, eax
0x180190bc5  jns     short loc_180190BE6
0x180190bc7  mov     edx, 0C6h; void *
0x180190bcc  lea     r8, aOnecoreBaseApp_41; "onecore\\base\\appmodel\\staterepositor"...
0x180190bd3  mov     r9d, edi; char *
0x180190bd6  mov     rcx, [rbp+4Fh]; this
0x180190bda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180190bdf  mov     eax, edi
0x180190be1  jmp     loc_1801914C9
0x180190be6  mov     r14, [r14]
0x180190be9  cmp     ebx, 15h
0x180190bec  jg      loc_1801914F1
0x180190bf2  jz      loc_1801913B2
0x180190bf8  cmp     ebx, 0Bh
0x180190bfb  jg      loc_180191036
0x180190c01  jz      loc_180190FDB
0x180190c07  cmp     ebx, 6
0x180190c0a  jg      loc_180190E6D
0x180190c10  jz      loc_180190E18
0x180190c16  test    ebx, ebx
0x180190c18  jz      loc_180190D9E
0x180190c1e  sub     ebx, 1
0x180190c21  jz      loc_180190D42
0x180190c27  sub     ebx, 2
0x180190c2a  jz      loc_180190CF0
0x180190c30  sub     ebx, 1
0x180190c33  jz      short loc_180190C95
0x180190c35  cmp     ebx, 1
0x180190c38  jnz     loc_180191985
0x180190c3e  lea     r13d, [rbx+7]
0x180190c42  cmp     r15, r13
0x180190c45  jz      short loc_180190C51
0x180190c47  mov     edx, 0EAh
0x180190c4c  jmp     loc_180190DA8
0x180190c51  mov     rax, [rbp+47h+arg_28]
0x180190c55  mov     [rbp+47h+var_90], rax
0x180190c59  mov     [rbp+47h+var_88], 0
0x180190c61  mov     rax, [r14]
0x180190c64  lea     r8, [rbp+47h+var_88]
0x180190c68  movsd   xmm1, qword ptr [rsi]
0x180190c6c  mov     rcx, r14
0x180190c6f  mov     rax, [rax+78h]
0x180190c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190c78  mov     ebx, eax
0x180190c7a  lea     rcx, [rbp+47h+var_90]; this
0x180190c7e  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x180190c83  test    ebx, ebx
0x180190c85  jns     loc_1801914C7
0x180190c8b  mov     edx, 0EBh
0x180190c90  jmp     loc_180190DFE
0x180190c95  mov     r13d, 8
0x180190c9b  cmp     r15, r13
0x180190c9e  jz      short loc_180190CAA
0x180190ca0  mov     edx, 0E3h
0x180190ca5  jmp     loc_180190DA8
0x180190caa  mov     rax, [rbp+47h+arg_28]
0x180190cae  mov     [rbp+47h+var_90], rax
0x180190cb2  mov     [rbp+47h+var_88], 0
0x180190cba  mov     rax, [r14]
0x180190cbd  lea     r8, [rbp+47h+var_88]
0x180190cc1  mov     rdx, [rsi]
0x180190cc4  mov     rcx, r14
0x180190cc7  mov     rax, [rax+0A8h]
0x180190cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190cd3  mov     ebx, eax
0x180190cd5  lea     rcx, [rbp+47h+var_90]; this
0x180190cd9  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x180190cde  test    ebx, ebx
0x180190ce0  jns     loc_1801914C7
0x180190ce6  mov     edx, 0E4h
0x180190ceb  jmp     loc_180190DFE
0x180190cf0  cmp     r15, 2
0x180190cf4  jz      short loc_180190D00
0x180190cf6  mov     edx, 0DBh
0x180190cfb  jmp     loc_180190DA8
0x180190d00  mov     rax, [rbp+47h+arg_28]
0x180190d04  mov     [rbp+47h+var_90], rax
0x180190d08  mov     [rbp+47h+var_88], r13
0x180190d0c  mov     rax, [r14]
0x180190d0f  lea     r8, [rbp+47h+var_88]
0x180190d13  movzx   edx, word ptr [rsi]
0x180190d16  mov     rcx, r14
0x180190d19  mov     rax, [rax+80h]
0x180190d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190d25  mov     ebx, eax
0x180190d27  lea     rcx, [rbp+47h+var_90]; this
0x180190d2b  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x180190d30  test    ebx, ebx
0x180190d32  jns     loc_1801914C7
0x180190d38  mov     edx, 0DCh
0x180190d3d  jmp     loc_180190DFE
0x180190d42  mov     cl, [rsi]
0x180190d44  cmp     cl, 2
0x180190d47  jb      short loc_180190D50
0x180190d49  mov     edx, 0D3h
0x180190d4e  jmp     short loc_180190DA8
0x180190d50  cmp     r15, 1
0x180190d54  jz      short loc_180190D5D
0x180190d56  mov     edx, 0D4h
0x180190d5b  jmp     short loc_180190DA8
0x180190d5d  mov     rax, [rbp+47h+arg_28]
0x180190d61  mov     [rbp+47h+var_90], rax
0x180190d65  mov     [rbp+47h+var_88], r13
0x180190d69  mov     rax, [r14]
0x180190d6c  test    cl, cl
0x180190d6e  setnz   dl
0x180190d71  lea     r8, [rbp+47h+var_88]
0x180190d75  mov     rcx, r14
0x180190d78  mov     rax, [rax+88h]
0x180190d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190d84  mov     ebx, eax
0x180190d86  lea     rcx, [rbp+47h+var_90]; this
0x180190d8a  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x180190d8f  test    ebx, ebx
0x180190d91  jns     loc_1801914C7
0x180190d97  mov     edx, 0D5h
0x180190d9c  jmp     short loc_180190DFE
0x180190d9e  test    r15, r15
0x180190da1  jz      short loc_180190DC7
0x180190da3  mov     edx, 0CCh; void *
0x180190da8  mov     esi, 80670005h
0x180190dad  lea     r8, aOnecoreBaseApp_41; "onecore\\base\\appmodel\\staterepositor"...
0x180190db4  mov     r9d, esi; char *
0x180190db7  mov     rcx, [rbp+4Fh]; this
0x180190dbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180190dc0  mov     eax, esi
0x180190dc2  jmp     loc_1801914C9
0x180190dc7  mov     rax, [rbp+47h+arg_28]
0x180190dcb  mov     [rbp+47h+var_90], rax
0x180190dcf  mov     [rbp+47h+var_88], r13
0x180190dd3  mov     rax, [r14]
0x180190dd6  lea     rdx, [rbp+47h+var_88]
0x180190dda  mov     rcx, r14
0x180190ddd  mov     rax, [rax+30h]
0x180190de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190de6  mov     ebx, eax
0x180190de8  lea     rcx, [rbp+47h+var_90]; this
0x180190dec  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x180190df1  test    ebx, ebx
0x180190df3  jns     loc_1801914C7
0x180190df9  mov     edx, 0CDh; void *
0x180190dfe  mov     rcx, [rbp+4Fh]; this
0x180190e02  mov     r9d, ebx; char *
0x180190e05  lea     r8, aOnecoreBaseApp_41; "onecore\\base\\appmodel\\staterepositor"...
0x180190e0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180190e11  mov     eax, ebx
0x180190e13  jmp     loc_1801914C9
0x180190e18  cmp     r15, 10h
0x180190e1c  jz      short loc_180190E25
0x180190e1e  mov     edx, 0F1h
0x180190e23  jmp     short loc_180190DA8
0x180190e25  mov     rax, [rbp+47h+arg_28]
0x180190e29  mov     [rbp+47h+var_90], rax
0x180190e2d  mov     [rbp+47h+var_88], r13
0x180190e31  movups  xmm0, xmmword ptr [rsi]
0x180190e34  movdqu  xmmword ptr [rbp+47h+hstringHeader.Reserved], xmm0
0x180190e39  mov     rax, [r14]
0x180190e3c  lea     r8, [rbp+47h+var_88]
0x180190e40  lea     rdx, [rbp+47h+hstringHeader]
0x180190e44  mov     rcx, r14
0x180190e47  mov     rax, [rax+0A0h]
0x180190e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190e53  mov     ebx, eax
0x180190e55  lea     rcx, [rbp+47h+var_90]; this
0x180190e59  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x180190e5e  test    ebx, ebx
0x180190e60  jns     loc_1801914C7
0x180190e66  mov     edx, 0F2h
0x180190e6b  jmp     short loc_180190DFE
0x180190e6d  sub     ebx, 7
0x180190e70  jz      loc_180190F8C
0x180190e76  sub     ebx, 1
0x180190e79  jz      loc_180190F3E
0x180190e7f  sub     ebx, 1
0x180190e82  jz      short loc_180190EE6
0x180190e84  cmp     ebx, 1
0x180190e87  jnz     loc_180191985
0x180190e8d  lea     r13d, [rbx+7]
0x180190e91  cmp     r15, r13
0x180190e94  jz      short loc_180190EA0
0x180190e96  mov     edx, 10Eh
0x180190e9b  jmp     loc_180190DA8
0x180190ea0  mov     rax, [rbp+47h+arg_28]
0x180190ea4  mov     [rbp+47h+var_90], rax
0x180190ea8  mov     [rbp+47h+var_88], 0
0x180190eb0  mov     rax, [r14]
0x180190eb3  lea     r8, [rbp+47h+var_88]
0x180190eb7  mov     rdx, [rsi]
0x180190eba  mov     rcx, r14
0x180190ebd  mov     rax, [rax+0B8h]
0x180190ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190ec9  mov     ebx, eax
0x180190ecb  lea     rcx, [rbp+47h+var_90]; this
0x180190ecf  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x180190ed4  test    ebx, ebx
0x180190ed6  jns     loc_1801914C7
0x180190edc  mov     edx, 10Fh
0x180190ee1  jmp     loc_180190DFE
0x180190ee6  mov     r13d, 8
0x180190eec  cmp     r15, r13
0x180190eef  jz      short loc_180190EFB
0x180190ef1  mov     edx, 106h
0x180190ef6  jmp     loc_180190DA8
0x180190efb  mov     rax, [rbp+47h+arg_28]
0x180190eff  mov     [rbp+47h+var_90], rax
0x180190f03  mov     [rbp+47h+var_88], 0
0x180190f0b  mov     rax, [r14]
0x180190f0e  lea     r8, [rbp+47h+var_88]
0x180190f12  mov     rdx, [rsi]
0x180190f15  mov     rcx, r14
0x180190f18  mov     rax, [rax+60h]
0x180190f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190f21  mov     ebx, eax
0x180190f23  lea     rcx, [rbp+47h+var_90]; this
0x180190f27  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x180190f2c  test    ebx, ebx
0x180190f2e  jns     loc_1801914C7
0x180190f34  mov     edx, 107h
0x180190f39  jmp     loc_180190DFE
0x180190f3e  cmp     r15, 4
0x180190f42  jz      short loc_180190F4E
0x180190f44  mov     edx, 0FFh
0x180190f49  jmp     loc_180190DA8
0x180190f4e  mov     rax, [rbp+47h+arg_28]
0x180190f52  mov     [rbp+47h+var_90], rax
0x180190f56  mov     [rbp+47h+var_88], r13
0x180190f5a  mov     rax, [r14]
0x180190f5d  lea     r8, [rbp+47h+var_88]
0x180190f61  mov     edx, [rsi]
0x180190f63  mov     rcx, r14
0x180190f66  mov     rax, [rax+50h]
0x180190f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190f6f  mov     ebx, eax
0x180190f71  lea     rcx, [rbp+47h+var_90]; this
0x180190f75  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x180190f7a  test    ebx, ebx
0x180190f7c  jns     loc_1801914C7
0x180190f82  mov     edx, 100h
0x180190f87  jmp     loc_180190DFE
0x180190f8c  cmp     r15, 2
0x180190f90  jz      short loc_180190F9C
0x180190f92  mov     edx, 0F8h
0x180190f97  jmp     loc_180190DA8
0x180190f9c  mov     rax, [rbp+47h+arg_28]
0x180190fa0  mov     [rbp+47h+var_90], rax
0x180190fa4  mov     [rbp+47h+var_88], r13
0x180190fa8  mov     rax, [r14]
0x180190fab  lea     r8, [rbp+47h+var_88]
0x180190faf  movzx   edx, word ptr [rsi]
0x180190fb2  mov     rcx, r14
0x180190fb5  mov     rax, [rax+40h]
0x180190fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180190fbe  mov     ebx, eax
0x180190fc0  lea     rcx, [rbp+47h+var_90]; this
0x180190fc4  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x180190fc9  test    ebx, ebx
0x180190fcb  jns     loc_1801914C7
0x180190fd1  mov     edx, 0F9h
0x180190fd6  jmp     loc_180190DFE
0x180190fdb  cmp     r15, 10h
0x180190fdf  jz      short loc_180190FEB
0x180190fe1  mov     edx, 116h
0x180190fe6  jmp     loc_180190DA8
0x180190feb  mov     rax, [rbp+47h+arg_28]
0x180190fef  mov     [rbp+47h+var_90], rax
0x180190ff3  mov     [rbp+47h+var_88], r13
0x180190ff7  movups  xmm0, xmmword ptr [rsi]
0x180190ffa  movdqu  xmmword ptr [rbp+47h+hstringHeader.Reserved], xmm0
0x180190fff  mov     rax, [r14]
0x180191002  lea     r8, [rbp+47h+var_88]
0x180191006  lea     rdx, [rbp+47h+hstringHeader]
0x18019100a  mov     rcx, r14
0x18019100d  mov     rax, [rax+0C8h]
0x180191014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180191019  mov     ebx, eax
0x18019101b  lea     rcx, [rbp+47h+var_90]; this
0x18019101f  call    ??1OutRef@RoVariant@@QEAA@XZ; RoVariant::OutRef::~OutRef(void)
0x180191024  test    ebx, ebx
0x180191026  jns     loc_1801914C7
  ... truncated ...
```
