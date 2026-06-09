# StateRepository::DictionarySerialization::WinRTWriter::AddKeyValue(ushort const *,IInspectable *)

- ea: `0x180024170`
- end: `0x1800251e0`
- name: `?AddKeyValue@WinRTWriter@DictionarySerialization@StateRepository@@AEAAJPEBGPEAUIInspectable@@@Z`
- size: `4208`
- prototype: `int(StateRepository::DictionarySerialization::WinRTWriter *__hidden this, const unsigned __int16 *, struct IInspectable *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800251e8`

## callees

- `0x180002980`
- `0x180003d04`
- `0x1800075e4`
- `0x18000b348`
- `0x180021594`
- `0x180021668`
- `0x180024150`
- `0x180024170`
- `0x1800251e8`
- `0x180025458`
- `0x180025474`
- `0x1800254c8`
- `0x1800257d8`
- `0x1800258d8`
- `0x180025b00`
- `0x180026030`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024832`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024ea3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024832`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024ea3`

## string_xrefs

- `0x1800241ae`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtwriter.cpp`
- `0x18002426c`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtwriter.cpp`
- `0x18002442b`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtwriter.cpp`
- `0x18002480a`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtwriter.cpp`
- `0x180024e6c`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtwriter.cpp`
- `0x180024f7e`: `onecore\base\appmodel\staterepository\dataaccesslayer\dictionarywinrtwriter.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::DictionarySerialization::WinRTWriter::AddKeyValue(
        StateRepository::DictionarySerialization::WinRTWriter *this,
        const unsigned __int16 *a2,
        struct IInspectable *a3)
{
  __int64 v6; // rdx
  struct IInspectableVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v10; // edi
  __int64 v11; // rbx
  int v12; // edi
  int Type; // eax
  int v14; // r15d
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v19; // r8
  unsigned __int64 v20; // rax
  _QWORD *v21; // rbx
  __int64 v22; // r8
  __int64 v23; // rdx
  void *v24; // rcx
  unsigned int v25; // eax
  unsigned int i; // r15d
  int v27; // eax
  unsigned __int64 v28; // rax
  unsigned int j; // edx
  __int64 v30; // rcx
  int v31; // [rsp+20h] [rbp-69h]
  HSTRING string; // [rsp+30h] [rbp-59h] BYREF
  __int64 v33; // [rsp+38h] [rbp-51h] BYREF
  int v34; // [rsp+40h] [rbp-49h]
  _BYTE v35[8]; // [rsp+48h] [rbp-41h] BYREF
  __int16 v36; // [rsp+50h] [rbp-39h] BYREF
  __int64 v37; // [rsp+58h] [rbp-31h] BYREF
  int v38; // [rsp+60h] [rbp-29h]
  unsigned int v39; // [rsp+68h] [rbp-21h] BYREF
  int v40; // [rsp+70h] [rbp-19h] BYREF
  int v41; // [rsp+78h] [rbp-11h] BYREF
  int v42; // [rsp+7Ch] [rbp-Dh] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v43; // [rsp+80h] [rbp-9h] BYREF
  __int64 v44; // [rsp+88h] [rbp-1h] BYREF
  __int128 v45; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  if ( !a2 )
  {
    v6 = 103;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtwriter.cpp",
      (const char *)0x80004003LL,
      v31);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    v6 = 104;
    goto LABEL_3;
  }
  lpVtbl = a3->lpVtbl;
  v43 = 0;
  QueryInterface = lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v43);
  if ( ((int (__fastcall *)(struct IInspectable *, GUID *, struct Windows::Foundation::Collections::IPropertySet **))QueryInterface)(
         a3,
         &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c,
         &v43) < 0
    || !v43 )
  {
    RoVariant::RoVariant((RoVariant *)&v37, a3, 0, 0);
    v11 = v37;
    if ( !v37 )
    {
      RoVariant::~RoVariant((RoVariant *)&v37);
      v10 = -2147024809;
      goto LABEL_210;
    }
    v12 = v38;
    v34 = v38;
    v41 = 0;
    v33 = v37;
    Type = RoVariant::Accessor::get_Type((RoVariant::Accessor *)&v33, (enum Windows::Foundation::PropertyType *)&v41);
    v14 = Type;
    if ( Type < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x83,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtwriter.cpp",
        (const char *)(unsigned int)Type,
        v31);
      RoVariant::~RoVariant((RoVariant *)&v37);
      v10 = v14;
      goto LABEL_210;
    }
    if ( v41 > 1025 )
    {
      switch ( v41 )
      {
        case 1026:
          *(_QWORD *)&v45 = v11;
          DWORD2(v45) = v12;
          LODWORD(string) = 0;
          v33 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *, __int64 *))(*(_QWORD *)v11 + 216LL))(
                        v11,
                        &string,
                        &v33),
                v10 < 0) )
          {
            v15 = 277;
            goto LABEL_39;
          }
          v19 = 28;
          goto LABEL_120;
        case 1027:
          *(_QWORD *)&v45 = v11;
          DWORD2(v45) = v12;
          LODWORD(string) = 0;
          v33 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *, __int64 *))(*(_QWORD *)v11 + 224LL))(
                        v11,
                        &string,
                        &v33),
                v10 < 0) )
          {
            v15 = 284;
            goto LABEL_39;
          }
          v19 = 38;
          goto LABEL_120;
        case 1028:
          *(_QWORD *)&v45 = v11;
          DWORD2(v45) = v12;
          LODWORD(string) = 0;
          v33 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *, __int64 *))(*(_QWORD *)v11 + 232LL))(
                        v11,
                        &string,
                        &v33),
                v10 < 0) )
          {
            v15 = 291;
            goto LABEL_39;
          }
          v19 = 29;
          goto LABEL_120;
        case 1029:
          *(_QWORD *)&v45 = v11;
          DWORD2(v45) = v12;
          LODWORD(string) = 0;
          v33 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *, __int64 *))(*(_QWORD *)v11 + 240LL))(
                        v11,
                        &string,
                        &v33),
                v10 < 0) )
          {
            v15 = 298;
            goto LABEL_39;
          }
          v19 = 39;
          goto LABEL_120;
        case 1030:
          *(_QWORD *)&v45 = v11;
          DWORD2(v45) = v12;
          LODWORD(string) = 0;
          v33 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *, __int64 *))(*(_QWORD *)v11 + 248LL))(
                        v11,
                        &string,
                        &v33),
                v10 < 0) )
          {
            v15 = 305;
            goto LABEL_39;
          }
          v19 = 30;
          goto LABEL_120;
        case 1031:
          *(_QWORD *)&v45 = v11;
          DWORD2(v45) = v12;
          LODWORD(string) = 0;
          v33 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *, __int64 *))(*(_QWORD *)v11 + 256LL))(
                        v11,
                        &string,
                        &v33),
                v10 < 0) )
          {
            v15 = 312;
            goto LABEL_39;
          }
          v19 = 40;
          goto LABEL_120;
        case 1032:
          *(_QWORD *)&v45 = v11;
          DWORD2(v45) = v12;
          LODWORD(string) = 0;
          v33 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *, __int64 *))(*(_QWORD *)v11 + 264LL))(
                        v11,
                        &string,
                        &v33),
                v10 < 0) )
          {
            v15 = 319;
            goto LABEL_39;
          }
          v19 = 33;
          goto LABEL_120;
        case 1033:
          *(_QWORD *)&v45 = v11;
          DWORD2(v45) = v12;
          LODWORD(string) = 0;
          v33 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *, __int64 *))(*(_QWORD *)v11 + 272LL))(
                        v11,
                        &string,
                        &v33),
                v10 < 0) )
          {
            v15 = 326;
            goto LABEL_39;
          }
          v19 = 26;
          goto LABEL_120;
        case 1034:
          *(_QWORD *)&v45 = v11;
          DWORD2(v45) = v12;
          LODWORD(string) = 0;
          v33 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *, __int64 *))(*(_QWORD *)v11 + 280LL))(
                        v11,
                        &string,
                        &v33),
                v10 < 0) )
          {
            v15 = 333;
            goto LABEL_39;
          }
          v19 = 24;
          goto LABEL_120;
        case 1035:
          *(_QWORD *)&v45 = v11;
          DWORD2(v45) = v12;
          LODWORD(string) = 0;
          v33 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *, __int64 *))(*(_QWORD *)v11 + 288LL))(
                        v11,
                        &string,
                        &v33),
                v10 < 0) )
          {
            v15 = 342;
            goto LABEL_39;
          }
          v19 = 22;
          goto LABEL_120;
        case 1036:
          *(_QWORD *)&v45 = v11;
          DWORD2(v45) = v12;
          v39 = 0;
          v33 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *, __int64 *))(*(_QWORD *)v11 + 296LL))(
                        v11,
                        &v39,
                        &v33),
                v10 < 0) )
          {
            v15 = 350;
            goto LABEL_39;
          }
          v20 = 8LL * v39;
          if ( !is_mul_ok(v39, 8u) )
            v20 = -1;
          v21 = operator new[](v20, (const struct std::nothrow_t *)&std::nothrow);
          if ( !v21 )
          {
            v23 = 352;
            goto LABEL_169;
          }
          v25 = v39;
          for ( i = 0; i < v39; v25 = v39 )
          {
            v21[i] = WindowsGetStringRawBuffer(*(HSTRING *)(v33 + 8LL * i), 0);
            ++i;
          }
          v27 = StateRepository::DictionarySerialization::Writer::AddArrayOfString(this, a2, v22, v25, v21);
          goto LABEL_174;
        case 1038:
          *(_QWORD *)&v45 = v11;
          DWORD2(v45) = v12;
          v39 = 0;
          v33 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *, __int64 *))(*(_QWORD *)v11 + 320LL))(
                    v11,
                    &v39,
                    &v33);
            if ( v10 >= 0 )
            {
              v28 = 8LL * v39;
              if ( !is_mul_ok(v39, 8u) )
                v28 = -1;
              v21 = operator new[](v28, (const struct std::nothrow_t *)&std::nothrow);
              if ( v21 )
              {
                for ( j = 0; j < v39; ++j )
                {
                  v30 = *(_QWORD *)(v33 + 8LL * j);
                  if ( v30 < 0 )
                  {
                    v10 = -2147483637;
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x176,
                      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtwriter.cpp",
                      (const char *)0x8000000BLL,
                      v31);
                    goto LABEL_175;
                  }
                  v21[j] = v30;
                }
                v27 = StateRepository::DictionarySerialization::Writer::AddArrayOfFixedLengthData(
                        this,
                        a2,
                        25,
                        v39,
                        v21);
LABEL_174:
                v10 = v27;
LABEL_175:
                v24 = v21;
              }
              else
              {
                v23 = 370;
LABEL_169:
                v10 = -2147024882;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v23,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtwriter.cpp",
                  (const char *)0x8007000ELL,
                  v31);
                v24 = 0;
              }
              operator delete(v24);
              goto LABEL_40;
            }
          }
          v15 = 368;
          break;
        case 1039:
          *(_QWORD *)&v45 = v11;
          DWORD2(v45) = v12;
          LODWORD(string) = 0;
          v33 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *, __int64 *))(*(_QWORD *)v11 + 328LL))(
                        v11,
                        &string,
                        &v33),
                v10 < 0) )
          {
            v15 = 384;
            goto LABEL_39;
          }
          v19 = 36;
          goto LABEL_120;
        case 1040:
          *(_QWORD *)&v45 = v11;
          DWORD2(v45) = v12;
          LODWORD(string) = 0;
          v33 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *, __int64 *))(*(_QWORD *)v11 + 312LL))(
                        v11,
                        &string,
                        &v33),
                v10 < 0) )
          {
            v15 = 394;
            goto LABEL_39;
          }
          v19 = 27;
          goto LABEL_120;
        case 1041:
          *(_QWORD *)&v45 = v11;
          DWORD2(v45) = v12;
          LODWORD(string) = 0;
          v33 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *, __int64 *))(*(_QWORD *)v11 + 336LL))(
                        v11,
                        &string,
                        &v33),
                v10 < 0) )
          {
            v15 = 401;
            goto LABEL_39;
          }
          v19 = 31;
          goto LABEL_120;
        case 1042:
          *(_QWORD *)&v45 = v11;
          DWORD2(v45) = v12;
          LODWORD(string) = 0;
          v33 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *, __int64 *))(*(_QWORD *)v11 + 344LL))(
                        v11,
                        &string,
                        &v33),
                v10 < 0) )
          {
            v15 = 411;
            goto LABEL_39;
          }
          v19 = 34;
          goto LABEL_120;
        case 1043:
          *(_QWORD *)&v45 = v11;
          DWORD2(v45) = v12;
          LODWORD(string) = 0;
          v33 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *, __int64 *))(*(_QWORD *)v11 + 352LL))(
                        v11,
                        &string,
                        &v33),
                v10 < 0) )
          {
            v15 = 421;
            goto LABEL_39;
          }
          v19 = 32;
          goto LABEL_120;
        default:
          goto LABEL_209;
      }
      goto LABEL_39;
    }
    if ( v41 == 1025 )
    {
      *(_QWORD *)&v45 = v11;
      DWORD2(v45) = v12;
      LODWORD(string) = 0;
      v33 = 0;
      v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
      if ( v10 < 0
        || (v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *, __int64 *))(*(_QWORD *)v11 + 208LL))(
                    v11,
                    &string,
                    &v33),
            v10 < 0) )
      {
        v15 = 270;
        goto LABEL_39;
      }
      v19 = 37;
LABEL_120:
      v17 = StateRepository::DictionarySerialization::Writer::AddArrayOfFixedLengthData(
              this,
              a2,
              v19,
              (unsigned int)string,
              v33);
LABEL_43:
      v10 = v17;
      goto LABEL_40;
    }
    if ( v41 > 10 )
    {
      if ( v41 > 16 )
      {
        switch ( v41 )
        {
          case 17:
            *(_QWORD *)&v45 = v11;
            v33 = 0;
            DWORD2(v45) = v12;
            v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
            if ( v10 < 0
              || (v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 184LL))(v11, &v33), v10 < 0) )
            {
              v15 = 240;
              goto LABEL_39;
            }
            *(_QWORD *)&v45 = v33;
            v16 = 10;
            break;
          case 18:
            *(_QWORD *)&v45 = v11;
            v33 = 0;
            DWORD2(v45) = v12;
            v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
            if ( v10 < 0
              || (v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 192LL))(v11, &v33), v10 < 0) )
            {
              v15 = 248;
              goto LABEL_39;
            }
            *(_QWORD *)&v45 = v33;
            v16 = 13;
            break;
          case 19:
            v33 = v11;
            v34 = v12;
            v45 = 0;
            v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v33);
            if ( v10 < 0
              || (v10 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v11 + 200LL))(v11, &v45), v10 < 0) )
            {
              v15 = 256;
              goto LABEL_39;
            }
            v16 = 11;
            break;
          default:
            goto LABEL_209;
        }
      }
      else
      {
        switch ( v41 )
        {
          case 16:
            v33 = v11;
            v45 = 0;
            v34 = v12;
            v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v33);
            if ( v10 < 0
              || (v10 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v11 + 160LL))(v11, &v45), v10 < 0) )
            {
              v15 = 234;
              goto LABEL_39;
            }
            v16 = 6;
            break;
          case 11:
            v33 = v11;
            v34 = v12;
            v35[0] = 0;
            v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v33);
            if ( v10 < 0
              || (v10 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v11 + 144LL))(v11, v35), v10 < 0) )
            {
              v15 = 202;
              goto LABEL_39;
            }
            v16 = 1;
            LOBYTE(v36) = v35[0] != 0;
            break;
          case 12:
            v33 = v11;
            v34 = v12;
            string = 0;
            v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v33);
            if ( v10 >= 0
              && (v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v11 + 152LL))(v11, &string), v10 >= 0) )
            {
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              v10 = StateRepository::DictionarySerialization::Writer::AddString(this, a2, StringRawBuffer);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xD0,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtwriter.cpp",
                (const char *)(unsigned int)v10,
                v31);
            }
            Windows::Internal::String::~String((Windows::Internal::String *)&string);
            goto LABEL_40;
          case 13:
            goto LABEL_209;
          case 14:
            *(_QWORD *)&v45 = v11;
            DWORD2(v45) = v12;
            v33 = 0;
            v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
            if ( v10 < 0
              || (v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 168LL))(v11, &v33), v10 < 0) )
            {
              v15 = 220;
              goto LABEL_39;
            }
            if ( v33 < 0 )
            {
              v10 = -2147483637;
              v15 = 222;
              goto LABEL_39;
            }
            *(_QWORD *)&v45 = v33;
            v16 = 4;
            break;
          default:
            *(_QWORD *)&v45 = v11;
            DWORD2(v45) = v12;
            v33 = 0;
            v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
            if ( v10 < 0
              || (v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 176LL))(v11, &v33), v10 < 0) )
            {
              v15 = 228;
              goto LABEL_39;
            }
            *(_QWORD *)&v45 = v33;
            v16 = 15;
            break;
        }
      }
    }
    else if ( v41 == 10 )
    {
      v33 = v11;
      v34 = v12;
      LOWORD(v39) = 0;
      v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v33);
      if ( v10 < 0
        || (v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v11 + 136LL))(v11, &v39), v10 < 0) )
      {
        v15 = 196;
        goto LABEL_39;
      }
      v36 = v39;
      v16 = 3;
    }
    else if ( v41 > 5 )
    {
      switch ( v41 )
      {
        case 6:
          *(_QWORD *)&v45 = v11;
          DWORD2(v45) = v12;
          v33 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v45);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 104LL))(v11, &v33), v10 < 0) )
          {
            v15 = 172;
            goto LABEL_39;
          }
          *(_QWORD *)&v45 = v33;
          v16 = 9;
          break;
        case 7:
          v33 = v11;
          v34 = v12;
          *(_QWORD *)&v45 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v33);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v11 + 112LL))(v11, &v45), v10 < 0) )
          {
            v15 = 178;
            goto LABEL_39;
          }
          v33 = v45;
          v16 = 19;
          break;
        case 8:
          v33 = v11;
          v34 = v12;
          LODWORD(string) = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v33);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v11 + 120LL))(v11, &string), v10 < 0) )
          {
            v15 = 184;
            goto LABEL_39;
          }
          v40 = (int)string;
          v16 = 12;
          break;
        default:
          v33 = v11;
          v44 = 0;
          v34 = v12;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v33);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 128LL))(v11, &v44), v10 < 0) )
          {
            v15 = 190;
            goto LABEL_39;
          }
          v33 = v44;
          v16 = 5;
          break;
      }
    }
    else
    {
      switch ( v41 )
      {
        case 5:
          v33 = v11;
          v34 = v12;
          v40 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v33);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v11 + 96LL))(v11, &v40), v10 < 0) )
          {
            v15 = 166;
            goto LABEL_39;
          }
          LODWORD(string) = v40;
          v16 = 18;
          break;
        case 0:
          RoVariant::~RoVariant((RoVariant *)&v37);
          v10 = -2147418113;
          goto LABEL_210;
        case 1:
          v33 = v11;
          v34 = v12;
          v35[0] = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v33);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v11 + 64LL))(v11, v35), v10 < 0) )
          {
            v15 = 142;
            goto LABEL_39;
          }
          LOBYTE(v36) = v35[0];
          v16 = 16;
          break;
        case 2:
          v33 = v11;
          v34 = v12;
          LOWORD(v39) = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v33);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v11 + 72LL))(v11, &v39), v10 < 0) )
          {
            v15 = 148;
            goto LABEL_39;
          }
          v36 = v39;
          v16 = 7;
          break;
        case 3:
          v33 = v11;
          v34 = v12;
          v36 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v33);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v11 + 80LL))(v11, &v36), v10 < 0) )
          {
            v15 = 154;
            goto LABEL_39;
          }
          LOWORD(v39) = v36;
          v16 = 17;
          break;
        case 4:
          v33 = v11;
          v34 = v12;
          v42 = 0;
          v10 = RoVariant::Accessor::VerifyPV((RoVariant::Accessor *)&v33);
          if ( v10 < 0
            || (v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v11 + 88LL))(v11, &v42), v10 < 0) )
          {
            v15 = 160;
LABEL_39:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v15,
              (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\dictionarywinrtwriter.cpp",
              (const char *)(unsigned int)v10,
              v31);
LABEL_40:
            RoVariant::~RoVariant((RoVariant *)&v37);
            goto LABEL_210;
          }
          LODWORD(string) = v42;
          v16 = 8;
          break;
        default:
LABEL_209:
          RoVariant::~RoVariant((RoVariant *)&v37);
          v10 = -2147023266;
          goto LABEL_210;
      }
    }
    v17 = StateRepository::DictionarySerialization::Writer::Add(this, a2, v16);
    goto LABEL_43;
  }
  v10 = StateRepository::DictionarySerialization::WinRTWriter::AddPropertySet(this, v43);
LABEL_210:
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v43);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180024170  push    rbp
0x180024172  push    rbx
0x180024173  push    rsi
0x180024174  push    rdi
0x180024175  push    r12
0x180024177  push    r14
0x180024179  push    r15
0x18002417b  lea     rbp, [rsp-27h]
0x180024180  sub     rsp, 0B0h
0x180024187  mov     rax, cs:__security_cookie
0x18002418e  xor     rax, rsp
0x180024191  mov     [rbp+57h+var_40], rax
0x180024195  xor     r12d, r12d
0x180024198  mov     rdi, r8
0x18002419b  mov     r14, rdx
0x18002419e  mov     rsi, rcx
0x1800241a1  test    rdx, rdx
0x1800241a4  jnz     short loc_1800241C9
0x1800241a6  lea     edx, [r14+67h]; void *
0x1800241aa  mov     rcx, [rbp+5Fh]; this
0x1800241ae  lea     r8, aOnecoreBaseApp_33; "onecore\\base\\appmodel\\staterepositor"...
0x1800241b5  mov     ebx, 80004003h
0x1800241ba  mov     r9d, ebx; char *
0x1800241bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800241c2  mov     eax, ebx
0x1800241c4  jmp     loc_180025173
0x1800241c9  test    rdi, rdi
0x1800241cc  jnz     short loc_1800241D3
0x1800241ce  lea     edx, [rdi+68h]
0x1800241d1  jmp     short loc_1800241AA
0x1800241d3  mov     rax, [r8]
0x1800241d6  lea     rcx, [rbp+57h+var_60]
0x1800241da  mov     [rbp+57h+var_60], r12
0x1800241de  mov     rbx, [rax]
0x1800241e1  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x1800241e6  lea     r8, [rbp+57h+var_60]
0x1800241ea  mov     rcx, rdi
0x1800241ed  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x1800241f4  mov     rax, rbx
0x1800241f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241fc  test    eax, eax
0x1800241fe  js      short loc_180024218
0x180024200  mov     rdx, [rbp+57h+var_60]; struct Windows::Foundation::Collections::IPropertySet *
0x180024204  test    rdx, rdx
0x180024207  jz      short loc_180024218
0x180024209  mov     rcx, rsi; this
0x18002420c  call    ?AddPropertySet@WinRTWriter@DictionarySerialization@StateRepository@@AEAAJPEAUIPropertySet@Collections@Foundation@Windows@@@Z; StateRepository::DictionarySerialization::WinRTWriter::AddPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x180024211  mov     edi, eax
0x180024213  jmp     loc_180025168
0x180024218  xor     r9d, r9d; bool
0x18002421b  lea     rcx, [rbp+57h+var_88]; this
0x18002421f  xor     r8d, r8d; bool
0x180024222  mov     rdx, rdi; struct IInspectable *
0x180024225  call    ??0RoVariant@@AEAA@PEAUIInspectable@@_N1@Z; RoVariant::RoVariant(IInspectable *,bool,bool)
0x18002422a  mov     rbx, [rbp+57h+var_88]
0x18002422e  test    rbx, rbx
0x180024231  jnz     short loc_180024246
0x180024233  lea     rcx, [rbp+57h+var_88]; this
0x180024237  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18002423c  mov     edi, 80070057h
0x180024241  jmp     loc_180025168
0x180024246  mov     edi, [rbp+57h+var_80]
0x180024249  lea     rdx, [rbp+57h+var_68]; enum Windows::Foundation::PropertyType *
0x18002424d  lea     rcx, [rbp+57h+var_A8]; this
0x180024251  mov     [rbp+57h+var_A0], edi
0x180024254  mov     [rbp+57h+var_68], r12d
0x180024258  mov     [rbp+57h+var_A8], rbx
0x18002425c  call    ?get_Type@Accessor@RoVariant@@QEBAJPEAW4PropertyType@Foundation@Windows@@@Z; RoVariant::Accessor::get_Type(Windows::Foundation::PropertyType *)
0x180024261  mov     r15d, eax
0x180024264  test    eax, eax
0x180024266  jns     short loc_180024291
0x180024268  mov     rcx, [rbp+5Fh]; this
0x18002426c  lea     r8, aOnecoreBaseApp_33; "onecore\\base\\appmodel\\staterepositor"...
0x180024273  mov     r9d, eax; char *
0x180024276  mov     edx, 83h; void *
0x18002427b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024280  lea     rcx, [rbp+57h+var_88]; this
0x180024284  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180024289  mov     edi, r15d
0x18002428c  jmp     loc_180025168
0x180024291  mov     ecx, [rbp+57h+var_68]
0x180024294  mov     eax, 401h
0x180024299  cmp     ecx, eax
0x18002429b  jg      loc_180024A8B
0x1800242a1  jz      loc_180024A20
0x1800242a7  cmp     ecx, 0Ah
0x1800242aa  jg      loc_1800246C2
0x1800242b0  jz      loc_180024666
0x1800242b6  cmp     ecx, 5
0x1800242b9  jg      loc_1800244DB
0x1800242bf  jz      loc_180024488
0x1800242c5  test    ecx, ecx
0x1800242c7  jz      loc_180024475
0x1800242cd  sub     ecx, 1
0x1800242d0  jz      loc_1800243EF
0x1800242d6  sub     ecx, 1
0x1800242d9  jz      loc_18002439C
0x1800242df  sub     ecx, 1
0x1800242e2  jz      short loc_180024343
0x1800242e4  cmp     ecx, 1
0x1800242e7  jnz     def_180024AAE; jumptable 0000000180024AAE default case, cases 1037,1044
0x1800242ed  lea     rcx, [rbp+57h+var_A8]; this
0x1800242f1  mov     [rbp+57h+var_A8], rbx
0x1800242f5  mov     [rbp+57h+var_A0], edi
0x1800242f8  mov     [rbp+57h+var_64], r12d
0x1800242fc  call    ?VerifyPV@Accessor@RoVariant@@AEBAJXZ; RoVariant::Accessor::VerifyPV(void)
0x180024301  mov     edi, eax
0x180024303  test    eax, eax
0x180024305  js      short loc_180024320
0x180024307  mov     rax, [rbx]
0x18002430a  lea     rdx, [rbp+57h+var_64]
0x18002430e  mov     rcx, rbx
0x180024311  mov     rax, [rax+58h]
0x180024315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002431a  mov     edi, eax
0x18002431c  test    eax, eax
0x18002431e  jns     short loc_18002432A
0x180024320  mov     edx, 0A0h
0x180024325  jmp     loc_180024427
0x18002432a  mov     eax, [rbp+57h+var_64]
0x18002432d  mov     r9d, 4
0x180024333  mov     dword ptr [rbp+57h+string], eax
0x180024336  lea     rax, [rbp+57h+string]
0x18002433a  lea     r8d, [r9+4]
0x18002433e  jmp     loc_18002445C
0x180024343  lea     rcx, [rbp+57h+var_A8]; this
0x180024347  mov     [rbp+57h+var_A8], rbx
0x18002434b  mov     [rbp+57h+var_A0], edi
0x18002434e  mov     [rbp+57h+var_90], r12w
0x180024353  call    ?VerifyPV@Accessor@RoVariant@@AEBAJXZ; RoVariant::Accessor::VerifyPV(void)
0x180024358  mov     edi, eax
0x18002435a  test    eax, eax
0x18002435c  js      short loc_180024377
0x18002435e  mov     rax, [rbx]
0x180024361  lea     rdx, [rbp+57h+var_90]
0x180024365  mov     rcx, rbx
0x180024368  mov     rax, [rax+50h]
0x18002436c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024371  mov     edi, eax
0x180024373  test    eax, eax
0x180024375  jns     short loc_180024381
0x180024377  mov     edx, 9Ah
0x18002437c  jmp     loc_180024427
0x180024381  movzx   eax, [rbp+57h+var_90]
0x180024385  mov     r9d, 2
0x18002438b  mov     word ptr [rbp+57h+var_78], ax
0x18002438f  lea     rax, [rbp+57h+var_78]
0x180024393  lea     r8d, [r9+0Fh]
0x180024397  jmp     loc_18002445C
0x18002439c  lea     rcx, [rbp+57h+var_A8]; this
0x1800243a0  mov     [rbp+57h+var_A8], rbx
0x1800243a4  mov     [rbp+57h+var_A0], edi
0x1800243a7  mov     word ptr [rbp+57h+var_78], r12w
0x1800243ac  call    ?VerifyPV@Accessor@RoVariant@@AEBAJXZ; RoVariant::Accessor::VerifyPV(void)
0x1800243b1  mov     edi, eax
0x1800243b3  test    eax, eax
0x1800243b5  js      short loc_1800243D0
0x1800243b7  mov     rax, [rbx]
0x1800243ba  lea     rdx, [rbp+57h+var_78]
0x1800243be  mov     rcx, rbx
0x1800243c1  mov     rax, [rax+48h]
0x1800243c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243ca  mov     edi, eax
0x1800243cc  test    eax, eax
0x1800243ce  jns     short loc_1800243D7
0x1800243d0  mov     edx, 94h
0x1800243d5  jmp     short loc_180024427
0x1800243d7  movzx   eax, word ptr [rbp+57h+var_78]
0x1800243db  mov     r9d, 2
0x1800243e1  mov     [rbp+57h+var_90], ax
0x1800243e5  lea     rax, [rbp+57h+var_90]
0x1800243e9  lea     r8d, [r9+5]
0x1800243ed  jmp     short loc_18002445C
0x1800243ef  lea     rcx, [rbp+57h+var_A8]; this
0x1800243f3  mov     [rbp+57h+var_A8], rbx
0x1800243f7  mov     [rbp+57h+var_A0], edi
0x1800243fa  mov     [rbp+57h+var_98], r12b
0x1800243fe  call    ?VerifyPV@Accessor@RoVariant@@AEBAJXZ; RoVariant::Accessor::VerifyPV(void)
0x180024403  mov     edi, eax
0x180024405  test    eax, eax
0x180024407  js      short loc_180024422
0x180024409  mov     rax, [rbx]
0x18002440c  lea     rdx, [rbp+57h+var_98]
0x180024410  mov     rcx, rbx
0x180024413  mov     rax, [rax+40h]
0x180024417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002441c  mov     edi, eax
0x18002441e  test    eax, eax
0x180024420  jns     short loc_180024448
0x180024422  mov     edx, 8Eh; void *
0x180024427  mov     rcx, [rbp+5Fh]; this
0x18002442b  lea     r8, aOnecoreBaseApp_33; "onecore\\base\\appmodel\\staterepositor"...
0x180024432  mov     r9d, edi; char *
0x180024435  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002443a  lea     rcx, [rbp+57h+var_88]; this
0x18002443e  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x180024443  jmp     loc_180025168
0x180024448  mov     al, [rbp+57h+var_98]
0x18002444b  mov     r9d, 1
0x180024451  mov     byte ptr [rbp+57h+var_90], al
0x180024454  lea     r8d, [r9+0Fh]
0x180024458  lea     rax, [rbp+57h+var_90]
0x18002445c  mov     [rsp+0E0h+var_B8], r12
0x180024461  mov     rdx, r14
0x180024464  mov     rcx, rsi
0x180024467  mov     [rsp+0E0h+var_C0], rax
0x18002446c  call    ?Add@Writer@DictionarySerialization@StateRepository@@QEAAJPEBGW4DataType@23@_KPEBXPEB_K@Z; StateRepository::DictionarySerialization::Writer::Add(ushort const *,StateRepository::DictionarySerialization::DataType,unsigned __int64,void const *,unsigned __int64 const *)
0x180024471  mov     edi, eax
0x180024473  jmp     short loc_18002443A
0x180024475  lea     rcx, [rbp+57h+var_88]; this
0x180024479  call    ??1RoVariant@@QEAA@XZ; RoVariant::~RoVariant(void)
0x18002447e  mov     edi, 8000FFFFh
0x180024483  jmp     loc_180025168
0x180024488  lea     rcx, [rbp+57h+var_A8]; this
0x18002448c  mov     [rbp+57h+var_A8], rbx
0x180024490  mov     [rbp+57h+var_A0], edi
0x180024493  mov     [rbp+57h+var_70], r12d
0x180024497  call    ?VerifyPV@Accessor@RoVariant@@AEBAJXZ; RoVariant::Accessor::VerifyPV(void)
0x18002449c  mov     edi, eax
0x18002449e  test    eax, eax
0x1800244a0  js      short loc_1800244BB
0x1800244a2  mov     rax, [rbx]
0x1800244a5  lea     rdx, [rbp+57h+var_70]
0x1800244a9  mov     rcx, rbx
0x1800244ac  mov     rax, [rax+60h]
0x1800244b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244b5  mov     edi, eax
0x1800244b7  test    eax, eax
0x1800244b9  jns     short loc_1800244C5
0x1800244bb  mov     edx, 0A6h
0x1800244c0  jmp     loc_180024427
0x1800244c5  mov     eax, [rbp+57h+var_70]
0x1800244c8  mov     r9d, 4
0x1800244ce  mov     dword ptr [rbp+57h+string], eax
0x1800244d1  lea     rax, [rbp+57h+string]
0x1800244d5  lea     r8d, [r9+0Eh]
0x1800244d9  jmp     short loc_18002445C
0x1800244db  sub     ecx, 6
0x1800244de  jz      loc_18002460E
0x1800244e4  sub     ecx, 1
0x1800244e7  jz      loc_1800245B6
0x1800244ed  sub     ecx, 1
0x1800244f0  jz      short loc_18002455C
0x1800244f2  cmp     ecx, 1
0x1800244f5  jnz     def_180024AAE; jumptable 0000000180024AAE default case, cases 1037,1044
0x1800244fb  xorps   xmm0, xmm0
0x1800244fe  mov     [rbp+57h+var_A8], rbx
0x180024502  lea     rcx, [rbp+57h+var_A8]; this
0x180024506  movsd   [rbp+57h+var_58], xmm0
0x18002450b  mov     [rbp+57h+var_A0], edi
0x18002450e  call    ?VerifyPV@Accessor@RoVariant@@AEBAJXZ; RoVariant::Accessor::VerifyPV(void)
0x180024513  mov     edi, eax
0x180024515  test    eax, eax
0x180024517  js      short loc_180024535
0x180024519  mov     rax, [rbx]
0x18002451c  lea     rdx, [rbp+57h+var_58]
0x180024520  mov     rcx, rbx
0x180024523  mov     rax, [rax+80h]
0x18002452a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002452f  mov     edi, eax
0x180024531  test    eax, eax
0x180024533  jns     short loc_18002453F
0x180024535  mov     edx, 0BEh
0x18002453a  jmp     loc_180024427
0x18002453f  movsd   xmm0, [rbp+57h+var_58]
0x180024544  lea     rax, [rbp+57h+var_A8]
0x180024548  mov     r9d, 8
0x18002454e  movsd   [rbp+57h+var_A8], xmm0
0x180024553  lea     r8d, [r9-3]
0x180024557  jmp     loc_18002445C
0x18002455c  lea     rcx, [rbp+57h+var_A8]; this
0x180024560  mov     [rbp+57h+var_A8], rbx
0x180024564  mov     [rbp+57h+var_A0], edi
0x180024567  mov     dword ptr [rbp+57h+string], r12d
0x18002456b  call    ?VerifyPV@Accessor@RoVariant@@AEBAJXZ; RoVariant::Accessor::VerifyPV(void)
0x180024570  mov     edi, eax
0x180024572  test    eax, eax
0x180024574  js      short loc_18002458F
0x180024576  mov     rax, [rbx]
0x180024579  lea     rdx, [rbp+57h+string]
0x18002457d  mov     rcx, rbx
0x180024580  mov     rax, [rax+78h]
0x180024584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024589  mov     edi, eax
0x18002458b  test    eax, eax
0x18002458d  jns     short loc_180024599
0x18002458f  mov     edx, 0B8h
0x180024594  jmp     loc_180024427
0x180024599  movss   xmm0, dword ptr [rbp+57h+string]
0x18002459e  lea     rax, [rbp+57h+var_70]
0x1800245a2  mov     r9d, 4
0x1800245a8  movss   [rbp+57h+var_70], xmm0
0x1800245ad  lea     r8d, [r9+8]
0x1800245b1  jmp     loc_18002445C
0x1800245b6  lea     rcx, [rbp+57h+var_A8]; this
0x1800245ba  mov     [rbp+57h+var_A8], rbx
0x1800245be  mov     [rbp+57h+var_A0], edi
0x1800245c1  mov     qword ptr [rbp+57h+var_50], r12
0x1800245c5  call    ?VerifyPV@Accessor@RoVariant@@AEBAJXZ; RoVariant::Accessor::VerifyPV(void)
0x1800245ca  mov     edi, eax
  ... truncated ...
```
