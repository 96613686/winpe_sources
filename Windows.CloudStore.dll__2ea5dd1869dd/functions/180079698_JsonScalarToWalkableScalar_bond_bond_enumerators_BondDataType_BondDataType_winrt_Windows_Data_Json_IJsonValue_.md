# JsonScalarToWalkableScalar(bond::_bond_enumerators::BondDataType::BondDataType,winrt::Windows::Data::Json::IJsonValue const &)

- ea: `0x180079698`
- end: `0x180079c35`
- name: `?JsonScalarToWalkableScalar@@YA?AVscalar@walkable@@W4BondDataType@3_bond_enumerators@bond@@AEBUIJsonValue@Json@Data@Windows@winrt@@@Z`
- size: `1437`
- prototype: ``
- caller_count: `2`
- callee_count: `29`
- tags: `registry_config`

## callers

- `0x18007954c`
- `0x1801cb45c`

## callees

- `0x180019720`
- `0x18001c2b0`
- `0x180021e20`
- `0x1800238d0`
- `0x180023fd4`
- `0x1800246c0`
- `0x180024fd0`
- `0x18006e1d4`
- `0x18006e528`
- `0x180079304`
- `0x180079698`
- `0x180079cdc`
- `0x180079d74`
- `0x180079e5c`
- `0x18007a5a0`
- `0x180082e00`
- `0x180088030`
- `0x1800902d4`
- `0x1800ac3a4`
- `0x1800c3fac`
- `0x1800dd9bc`
- `0x1800de0d8`
- `0x1800de530`
- `0x1800de978`
- `0x1800f47a0`
- `0x1800fb5a0`
- `0x1801201a0`
- `0x1801c7668`
- `0x1801c7808`

## string_xrefs

- `0x180079830`: `onecoreuap\shell\cloudstore\resolver\src\idiomaticjson.cpp`
- `0x1800798a4`: `onecoreuap\shell\cloudstore\resolver\src\idiomaticjson.cpp`
- `0x1800798f7`: `onecoreuap\shell\cloudstore\resolver\src\idiomaticjson.cpp`
- `0x18007994a`: `onecoreuap\shell\cloudstore\resolver\src\idiomaticjson.cpp`
- `0x18007999c`: `onecoreuap\shell\cloudstore\resolver\src\idiomaticjson.cpp`
- `0x1800799ea`: `onecoreuap\shell\cloudstore\resolver\src\idiomaticjson.cpp`
- `0x180079a32`: `onecoreuap\shell\cloudstore\resolver\src\idiomaticjson.cpp`
- `0x180079a55`: `onecoreuap\shell\cloudstore\resolver\src\idiomaticjson.cpp`
- `0x180079a78`: `onecoreuap\shell\cloudstore\resolver\src\idiomaticjson.cpp`
- `0x180079ac2`: `onecoreuap\shell\cloudstore\resolver\src\idiomaticjson.cpp`
- `0x180079b0b`: `onecoreuap\shell\cloudstore\resolver\src\idiomaticjson.cpp`
- `0x180079b54`: `onecoreuap\shell\cloudstore\resolver\src\idiomaticjson.cpp`
- `0x180079b9d`: `onecoreuap\shell\cloudstore\resolver\src\idiomaticjson.cpp`
- `0x180079c23`: `onecoreuap\shell\cloudstore\resolver\src\idiomaticjson.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall JsonScalarToWalkableScalar(__int64 a1, int a2, __int64 a3)
{
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  __int64 *v10; // rax
  __int64 v11; // rcx
  const WCHAR *v12; // rdx
  __int64 v13; // r8
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  float Number; // xmm1_4
  CorruptDataException *v21; // rax
  double v22; // xmm0_8
  unsigned __int64 v23; // rax
  CorruptDataException *v24; // rax
  CorruptDataException *v25; // rax
  CorruptDataException *v26; // rax
  CorruptDataException *v27; // rax
  CorruptDataException *v28; // rax
  CorruptDataException *v29; // rax
  CorruptDataException *v30; // rax
  CorruptDataException *v31; // rax
  double v32; // xmm0_8
  CorruptDataException *v33; // rax
  double v34; // xmm0_8
  CorruptDataException *v35; // rax
  double v36; // xmm0_8
  CorruptDataException *v37; // rax
  double v38; // xmm0_8
  CorruptDataException *v39; // rax
  winrt::hstring *View; // rax
  __int64 v41; // rax
  CorruptDataException *v42; // rax
  float v43[4]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v44[208]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v45; // [rsp+100h] [rbp+0h] BYREF
  __int128 v46; // [rsp+110h] [rbp+10h]
  _BYTE v47[32]; // [rsp+120h] [rbp+20h] BYREF
  void *retaddr; // [rsp+158h] [rbp+58h]

  *(_QWORD *)v43 = a1;
  if ( a2 <= 8 )
  {
    if ( a2 == 8 )
    {
      if ( (unsigned int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(a3) != 2 )
      {
        v29 = CorruptDataException::CorruptDataException((CorruptDataException *)v44);
        wil::details::ReportFailure_CustomException<CorruptDataException>(
          retaddr,
          117,
          "onecoreuap\\shell\\cloudstore\\resolver\\src\\idiomaticjson.cpp",
          v29);
      }
      winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(a3);
      walkable::scalar::make(a1);
    }
    else
    {
      v15 = a2 - 2;
      if ( v15 )
      {
        v16 = v15 - 1;
        if ( v16 )
        {
          v17 = v16 - 1;
          if ( v17 )
          {
            v18 = v17 - 1;
            if ( v18 )
            {
              v19 = v18 - 1;
              if ( v19 )
              {
                if ( v19 != 1 )
                  goto LABEL_47;
                if ( (unsigned int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(a3) != 2 )
                {
                  v21 = CorruptDataException::CorruptDataException((CorruptDataException *)v44);
                  wil::details::ReportFailure_CustomException<CorruptDataException>(
                    retaddr,
                    113,
                    "onecoreuap\\shell\\cloudstore\\resolver\\src\\idiomaticjson.cpp",
                    v21);
                }
                Number = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(a3);
                v43[0] = Number;
                walkable::scalar::make<float>(a1, v43);
              }
              else
              {
                if ( (unsigned int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(a3) != 2 )
                {
                  v24 = CorruptDataException::CorruptDataException((CorruptDataException *)v44);
                  wil::details::ReportFailure_CustomException<CorruptDataException>(
                    retaddr,
                    105,
                    "onecoreuap\\shell\\cloudstore\\resolver\\src\\idiomaticjson.cpp",
                    v24);
                }
                v22 = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(a3);
                v23 = 0;
                if ( v22 >= 9.223372036854776e18 )
                {
                  v22 = v22 - 9.223372036854776e18;
                  if ( v22 < 9.223372036854776e18 )
                    v23 = 0x8000000000000000uLL;
                }
                walkable::scalar::make(a1, v23 + (unsigned int)(int)v22);
              }
            }
            else
            {
              if ( (unsigned int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(a3) != 2 )
              {
                v25 = CorruptDataException::CorruptDataException((CorruptDataException *)v44);
                wil::details::ReportFailure_CustomException<CorruptDataException>(
                  retaddr,
                  97,
                  "onecoreuap\\shell\\cloudstore\\resolver\\src\\idiomaticjson.cpp",
                  v25);
              }
              LODWORD(v43[0]) = (int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(a3);
              walkable::scalar::make<unsigned int>(a1, v43);
            }
          }
          else
          {
            if ( (unsigned int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(a3) != 2 )
            {
              v26 = CorruptDataException::CorruptDataException((CorruptDataException *)v44);
              wil::details::ReportFailure_CustomException<CorruptDataException>(
                retaddr,
                89,
                "onecoreuap\\shell\\cloudstore\\resolver\\src\\idiomaticjson.cpp",
                v26);
            }
            LOWORD(v43[0]) = (int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(a3);
            walkable::scalar::make<unsigned short>(a1, v43);
          }
        }
        else
        {
          if ( (unsigned int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(a3) != 2 )
          {
            v27 = CorruptDataException::CorruptDataException((CorruptDataException *)v44);
            wil::details::ReportFailure_CustomException<CorruptDataException>(
              retaddr,
              81,
              "onecoreuap\\shell\\cloudstore\\resolver\\src\\idiomaticjson.cpp",
              v27);
          }
          LOBYTE(v43[0]) = (int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(a3);
          walkable::scalar::make<unsigned char>(a1, v43);
        }
      }
      else
      {
        if ( (unsigned int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(a3) != 1 )
        {
          v28 = CorruptDataException::CorruptDataException((CorruptDataException *)v44);
          wil::details::ReportFailure_CustomException<CorruptDataException>(
            retaddr,
            77,
            "onecoreuap\\shell\\cloudstore\\resolver\\src\\idiomaticjson.cpp",
            v28);
        }
        LOBYTE(v43[0]) = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetBoolean(a3);
        walkable::scalar::make<bool>(a1, v43);
      }
    }
  }
  else
  {
    v5 = a2 - 9;
    if ( !v5 )
    {
      if ( (unsigned int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(a3) != 3 )
      {
        v42 = CorruptDataException::CorruptDataException((CorruptDataException *)v44);
        wil::details::ReportFailure_CustomException<CorruptDataException>(
          retaddr,
          121,
          "onecoreuap\\shell\\cloudstore\\resolver\\src\\idiomaticjson.cpp",
          v42);
      }
      View = (winrt::hstring *)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>,winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>::GetView(
                                 a3,
                                 v43);
      winrt::hstring::c_str(View);
      std::wstring::wstring(&v45);
      v41 = WideStringToUtf8String(v47, &v45);
      walkable::scalar::make(a1, v41);
      std::string::_Tidy_deallocate(v47);
      std::wstring::~wstring(&v45);
      goto LABEL_13;
    }
    v6 = v5 - 5;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            if ( v9 == 1 )
            {
              if ( (unsigned int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(a3) != 3 )
              {
                v31 = CorruptDataException::CorruptDataException((CorruptDataException *)v44);
                wil::details::ReportFailure_CustomException<CorruptDataException>(
                  retaddr,
                  125,
                  "onecoreuap\\shell\\cloudstore\\resolver\\src\\idiomaticjson.cpp",
                  v31);
              }
              v10 = (__int64 *)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>,winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>::GetView(
                                 a3,
                                 v43);
              v45 = 0;
              v46 = 0;
              v11 = *v10;
              if ( *v10 )
              {
                v12 = *(const WCHAR **)(v11 + 16);
                v13 = *(unsigned int *)(v11 + 4);
              }
              else
              {
                v12 = &LocaleName;
                v13 = 0;
              }
              std::wstring::_Construct<1,unsigned short const *>(&v45, v12, v13);
              walkable::scalar::make(a1, &v45);
              if ( *((_QWORD *)&v46 + 1) > 7u )
                std::_Deallocate<16>((void *)v45, (const struct std::nothrow_t *)(2LL * *((_QWORD *)&v46 + 1) + 2));
LABEL_13:
              winrt::handle_type<winrt::impl::hstring_traits>::close(v43);
              return a1;
            }
LABEL_47:
            v30 = CorruptDataException::CorruptDataException((CorruptDataException *)v44);
            wil::details::ReportFailure_CustomException<CorruptDataException>(
              retaddr,
              129,
              "onecoreuap\\shell\\cloudstore\\resolver\\src\\idiomaticjson.cpp",
              v30);
          }
          if ( (unsigned int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(a3) != 2 )
          {
            v33 = CorruptDataException::CorruptDataException((CorruptDataException *)v44);
            wil::details::ReportFailure_CustomException<CorruptDataException>(
              retaddr,
              109,
              "onecoreuap\\shell\\cloudstore\\resolver\\src\\idiomaticjson.cpp",
              v33);
          }
          v32 = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(a3);
          walkable::scalar::make(a1, (unsigned int)(int)v32);
        }
        else
        {
          if ( (unsigned int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(a3) != 2 )
          {
            v35 = CorruptDataException::CorruptDataException((CorruptDataException *)v44);
            wil::details::ReportFailure_CustomException<CorruptDataException>(
              retaddr,
              101,
              "onecoreuap\\shell\\cloudstore\\resolver\\src\\idiomaticjson.cpp",
              v35);
          }
          v34 = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(a3);
          walkable::scalar::make(a1, (unsigned int)(int)v34);
        }
      }
      else
      {
        if ( (unsigned int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(a3) != 2 )
        {
          v37 = CorruptDataException::CorruptDataException((CorruptDataException *)v44);
          wil::details::ReportFailure_CustomException<CorruptDataException>(
            retaddr,
            93,
            "onecoreuap\\shell\\cloudstore\\resolver\\src\\idiomaticjson.cpp",
            v37);
        }
        v36 = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(a3);
        walkable::scalar::make(a1, (unsigned int)(int)v36);
      }
    }
    else
    {
      if ( (unsigned int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(a3) != 2 )
      {
        v39 = CorruptDataException::CorruptDataException((CorruptDataException *)v44);
        wil::details::ReportFailure_CustomException<CorruptDataException>(
          retaddr,
          85,
          "onecoreuap\\shell\\cloudstore\\resolver\\src\\idiomaticjson.cpp",
          v39);
      }
      v38 = winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(a3);
      walkable::scalar::make(a1, (unsigned int)(int)v38);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180079698  mov     [rsp-8+arg_8], rbx
0x18007969d  mov     [rsp-8+arg_18], rdi
0x1800796a2  push    rbp
0x1800796a3  lea     rbp, [rsp-50h]
0x1800796a8  sub     rsp, 150h
0x1800796af  mov     rax, cs:__security_cookie
0x1800796b6  xor     rax, rsp
0x1800796b9  mov     [rbp+50h+var_10], rax
0x1800796bd  mov     rbx, r8
0x1800796c0  mov     rdi, rcx
0x1800796c3  mov     qword ptr [rsp+150h+var_130], rcx
0x1800796c8  cmp     edx, 8
0x1800796cb  jle     loc_1800797B3
0x1800796d1  sub     edx, 9
0x1800796d4  jz      loc_180079BAF
0x1800796da  sub     edx, 5
0x1800796dd  jz      loc_180079B66
0x1800796e3  sub     edx, 1
0x1800796e6  jz      loc_180079B1D
0x1800796ec  sub     edx, 1
0x1800796ef  jz      loc_180079AD4
0x1800796f5  sub     edx, 1
0x1800796f8  jz      loc_180079A8A
0x1800796fe  cmp     edx, 1
0x180079701  jnz     loc_180079A44
0x180079707  mov     rcx, rbx
0x18007970a  call    ?ValueType@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(void)
0x18007970f  cmp     eax, 3
0x180079712  jnz     loc_180079A67
0x180079718  lea     rdx, [rsp+150h+var_130]
0x18007971d  mov     rcx, rbx
0x180079720  call    ?GetView@?$consume_Windows_Foundation_Collections_IVector@U?$IVector@UProfileDataItemDataItem@Downloader@Cloud@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UProfileDataItemDataItem@Downloader@Cloud@Storage@Internal@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>,winrt::Windows::Internal::Storage::Cloud::Downloader::ProfileDataItemDataItem>::GetView(void)
0x180079725  nop
0x180079726  xorps   xmm0, xmm0
0x180079729  movups  [rbp+50h+var_50], xmm0
0x18007972d  xorps   xmm1, xmm1
0x180079730  movdqu  [rbp+50h+var_40], xmm1
0x180079735  mov     rcx, [rax]
0x180079738  test    rcx, rcx
0x18007973b  jz      short loc_1800797A7
0x18007973d  mov     rdx, [rcx+10h]
0x180079741  mov     r8d, [rcx+4]
0x180079745  lea     rcx, [rbp+50h+var_50]
0x180079749  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007974e  nop
0x18007974f  lea     rdx, [rbp+50h+var_50]
0x180079753  mov     rcx, rdi
0x180079756  call    ?make@scalar@walkable@@SA?AV12@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; walkable::scalar::make(std::wstring const &)
0x18007975b  nop
0x18007975c  mov     rdx, qword ptr [rbp+50h+var_40+8]
0x180079760  cmp     rdx, 7
0x180079764  ja      short loc_180079794
0x180079766  lea     rcx, [rsp+150h+var_130]
0x18007976b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180079770  mov     rax, rdi
0x180079773  mov     rcx, [rbp+50h+var_10]
0x180079777  xor     rcx, rsp; StackCookie
0x18007977a  call    __security_check_cookie
0x18007977f  lea     r11, [rsp+150h+var_s0]
0x180079787  mov     rbx, [r11+18h]
0x18007978b  mov     rdi, [r11+28h]
0x18007978f  mov     rsp, r11
0x180079792  pop     rbp
0x180079793  retn
0x180079794  lea     rdx, ds:2[rdx*2]
0x18007979c  mov     rcx, qword ptr [rbp+50h+var_50]
0x1800797a0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800797a5  jmp     short loc_180079766
0x1800797a7  lea     rdx, LocaleName
0x1800797ae  xor     r8d, r8d
0x1800797b1  jmp     short loc_180079745
0x1800797b3  jz      loc_1800799FC
0x1800797b9  sub     edx, 2
0x1800797bc  jz      loc_1800799AE
0x1800797c2  sub     edx, 1
0x1800797c5  jz      loc_18007995C
0x1800797cb  sub     edx, 1
0x1800797ce  jz      loc_180079909
0x1800797d4  sub     edx, 1
0x1800797d7  jz      loc_1800798B6
0x1800797dd  sub     edx, 1
0x1800797e0  jz      short loc_180079842
0x1800797e2  cmp     edx, 1
0x1800797e5  jnz     loc_180079A44
0x1800797eb  mov     rcx, rbx
0x1800797ee  call    ?ValueType@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(void)
0x1800797f3  cmp     eax, 2
0x1800797f6  jnz     short loc_18007981F
0x1800797f8  mov     rcx, rbx
0x1800797fb  call    ?GetNumber@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(void)
0x180079800  xorps   xmm1, xmm1
0x180079803  cvtsd2ss xmm1, xmm0
0x180079807  movss   [rsp+150h+var_130], xmm1
0x18007980d  lea     rdx, [rsp+150h+var_130]
0x180079812  mov     rcx, rdi
0x180079815  call    ??$make@M@scalar@walkable@@SA?AV01@AEBM@Z; walkable::scalar::make<float>(float const &)
0x18007981a  jmp     loc_180079770
0x18007981f  lea     rcx, [rsp+150h+var_120]; this
0x180079824  call    ??0CorruptDataException@@QEAA@XZ; CorruptDataException::CorruptDataException(void)
0x180079829  mov     rcx, [rbp+58h]
0x18007982d  mov     r9, rax
0x180079830  lea     r8, aOnecoreuapShel_42; "onecoreuap\\shell\\cloudstore\\resolver"...
0x180079837  mov     edx, 71h ; 'q'
0x18007983c  call    ??$ReportFailure_CustomException@VCorruptDataException@@@details@wil@@YAXPEAXIPEBDVCorruptDataException@@@Z; wil::details::ReportFailure_CustomException<CorruptDataException>(void *,uint,char const *,CorruptDataException)
0x180079842  mov     rcx, rbx
0x180079845  call    ?ValueType@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(void)
0x18007984a  cmp     eax, 2
0x18007984d  jnz     short loc_180079893
0x18007984f  mov     rcx, rbx
0x180079852  call    ?GetNumber@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(void)
0x180079857  xor     eax, eax
0x180079859  movsd   xmm1, cs:__real@43e0000000000000
0x180079861  comisd  xmm0, xmm1
0x180079865  jb      short loc_18007987E
0x180079867  subsd   xmm0, xmm1
0x18007986b  comisd  xmm0, xmm1
0x18007986f  jnb     short loc_18007987E
0x180079871  mov     rcx, 8000000000000000h
0x18007987b  mov     rax, rcx
0x18007987e  cvttsd2si rdx, xmm0
0x180079883  add     rdx, rax
0x180079886  mov     rcx, rdi
0x180079889  call    ?make@scalar@walkable@@SA?AV12@_K@Z; walkable::scalar::make(unsigned __int64)
0x18007988e  jmp     loc_180079770
0x180079893  lea     rcx, [rsp+150h+var_120]; this
0x180079898  call    ??0CorruptDataException@@QEAA@XZ; CorruptDataException::CorruptDataException(void)
0x18007989d  mov     rcx, [rbp+58h]
0x1800798a1  mov     r9, rax
0x1800798a4  lea     r8, aOnecoreuapShel_42; "onecoreuap\\shell\\cloudstore\\resolver"...
0x1800798ab  mov     edx, 69h ; 'i'
0x1800798b0  call    ??$ReportFailure_CustomException@VCorruptDataException@@@details@wil@@YAXPEAXIPEBDVCorruptDataException@@@Z; wil::details::ReportFailure_CustomException<CorruptDataException>(void *,uint,char const *,CorruptDataException)
0x1800798b6  mov     rcx, rbx
0x1800798b9  call    ?ValueType@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(void)
0x1800798be  cmp     eax, 2
0x1800798c1  jnz     short loc_1800798E6
0x1800798c3  mov     rcx, rbx
0x1800798c6  call    ?GetNumber@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(void)
0x1800798cb  cvttsd2si rax, xmm0
0x1800798d0  mov     [rsp+150h+var_130], eax
0x1800798d4  lea     rdx, [rsp+150h+var_130]
0x1800798d9  mov     rcx, rdi
0x1800798dc  call    ??$make@I@scalar@walkable@@SA?AV01@AEBI@Z; walkable::scalar::make<uint>(uint const &)
0x1800798e1  jmp     loc_180079770
0x1800798e6  lea     rcx, [rsp+150h+var_120]; this
0x1800798eb  call    ??0CorruptDataException@@QEAA@XZ; CorruptDataException::CorruptDataException(void)
0x1800798f0  mov     rcx, [rbp+58h]
0x1800798f4  mov     r9, rax
0x1800798f7  lea     r8, aOnecoreuapShel_42; "onecoreuap\\shell\\cloudstore\\resolver"...
0x1800798fe  mov     edx, 61h ; 'a'
0x180079903  call    ??$ReportFailure_CustomException@VCorruptDataException@@@details@wil@@YAXPEAXIPEBDVCorruptDataException@@@Z; wil::details::ReportFailure_CustomException<CorruptDataException>(void *,uint,char const *,CorruptDataException)
0x180079909  mov     rcx, rbx
0x18007990c  call    ?ValueType@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(void)
0x180079911  cmp     eax, 2
0x180079914  jnz     short loc_180079939
0x180079916  mov     rcx, rbx
0x180079919  call    ?GetNumber@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(void)
0x18007991e  cvttsd2si eax, xmm0
0x180079922  mov     word ptr [rsp+150h+var_130], ax
0x180079927  lea     rdx, [rsp+150h+var_130]
0x18007992c  mov     rcx, rdi
0x18007992f  call    ??$make@G@scalar@walkable@@SA?AV01@AEBG@Z; walkable::scalar::make<ushort>(ushort const &)
0x180079934  jmp     loc_180079770
0x180079939  lea     rcx, [rsp+150h+var_120]; this
0x18007993e  call    ??0CorruptDataException@@QEAA@XZ; CorruptDataException::CorruptDataException(void)
0x180079943  mov     rcx, [rbp+58h]
0x180079947  mov     r9, rax
0x18007994a  lea     r8, aOnecoreuapShel_42; "onecoreuap\\shell\\cloudstore\\resolver"...
0x180079951  mov     edx, 59h ; 'Y'
0x180079956  call    ??$ReportFailure_CustomException@VCorruptDataException@@@details@wil@@YAXPEAXIPEBDVCorruptDataException@@@Z; wil::details::ReportFailure_CustomException<CorruptDataException>(void *,uint,char const *,CorruptDataException)
0x18007995c  mov     rcx, rbx
0x18007995f  call    ?ValueType@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(void)
0x180079964  cmp     eax, 2
0x180079967  jnz     short loc_18007998B
0x180079969  mov     rcx, rbx
0x18007996c  call    ?GetNumber@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(void)
0x180079971  cvttsd2si eax, xmm0
0x180079975  mov     byte ptr [rsp+150h+var_130], al
0x180079979  lea     rdx, [rsp+150h+var_130]
0x18007997e  mov     rcx, rdi
0x180079981  call    ??$make@E@scalar@walkable@@SA?AV01@AEBE@Z; walkable::scalar::make<uchar>(uchar const &)
0x180079986  jmp     loc_180079770
0x18007998b  lea     rcx, [rsp+150h+var_120]; this
0x180079990  call    ??0CorruptDataException@@QEAA@XZ; CorruptDataException::CorruptDataException(void)
0x180079995  mov     rcx, [rbp+58h]
0x180079999  mov     r9, rax
0x18007999c  lea     r8, aOnecoreuapShel_42; "onecoreuap\\shell\\cloudstore\\resolver"...
0x1800799a3  mov     edx, 51h ; 'Q'
0x1800799a8  call    ??$ReportFailure_CustomException@VCorruptDataException@@@details@wil@@YAXPEAXIPEBDVCorruptDataException@@@Z; wil::details::ReportFailure_CustomException<CorruptDataException>(void *,uint,char const *,CorruptDataException)
0x1800799ae  mov     rcx, rbx
0x1800799b1  call    ?ValueType@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(void)
0x1800799b6  cmp     eax, 1
0x1800799b9  jnz     short loc_1800799D9
0x1800799bb  mov     rcx, rbx
0x1800799be  call    ?GetBoolean@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetBoolean(void)
0x1800799c3  mov     byte ptr [rsp+150h+var_130], al
0x1800799c7  lea     rdx, [rsp+150h+var_130]
0x1800799cc  mov     rcx, rdi
0x1800799cf  call    ??$make@_N@scalar@walkable@@SA?AV01@AEB_N@Z; walkable::scalar::make<bool>(bool const &)
0x1800799d4  jmp     loc_180079770
0x1800799d9  lea     rcx, [rsp+150h+var_120]; this
0x1800799de  call    ??0CorruptDataException@@QEAA@XZ; CorruptDataException::CorruptDataException(void)
0x1800799e3  mov     rcx, [rbp+58h]
0x1800799e7  mov     r9, rax
0x1800799ea  lea     r8, aOnecoreuapShel_42; "onecoreuap\\shell\\cloudstore\\resolver"...
0x1800799f1  mov     edx, 4Dh ; 'M'
0x1800799f6  call    ??$ReportFailure_CustomException@VCorruptDataException@@@details@wil@@YAXPEAXIPEBDVCorruptDataException@@@Z; wil::details::ReportFailure_CustomException<CorruptDataException>(void *,uint,char const *,CorruptDataException)
0x1800799fc  mov     rcx, rbx
0x1800799ff  call    ?ValueType@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(void)
0x180079a04  cmp     eax, 2
0x180079a07  jnz     short loc_180079A21
0x180079a09  mov     rcx, rbx
0x180079a0c  call    ?GetNumber@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(void)
0x180079a11  movaps  xmm1, xmm0
0x180079a14  mov     rcx, rdi
0x180079a17  call    ?make@scalar@walkable@@SA?AV12@N@Z; walkable::scalar::make(double)
0x180079a1c  jmp     loc_180079770
0x180079a21  lea     rcx, [rsp+150h+var_120]; this
0x180079a26  call    ??0CorruptDataException@@QEAA@XZ; CorruptDataException::CorruptDataException(void)
0x180079a2b  mov     rcx, [rbp+58h]
0x180079a2f  mov     r9, rax
0x180079a32  lea     r8, aOnecoreuapShel_42; "onecoreuap\\shell\\cloudstore\\resolver"...
0x180079a39  mov     edx, 75h ; 'u'
0x180079a3e  call    ??$ReportFailure_CustomException@VCorruptDataException@@@details@wil@@YAXPEAXIPEBDVCorruptDataException@@@Z; wil::details::ReportFailure_CustomException<CorruptDataException>(void *,uint,char const *,CorruptDataException)
0x180079a44  lea     rcx, [rsp+150h+var_120]; this
0x180079a49  call    ??0CorruptDataException@@QEAA@XZ; CorruptDataException::CorruptDataException(void)
0x180079a4e  mov     rcx, [rbp+58h]
0x180079a52  mov     r9, rax
0x180079a55  lea     r8, aOnecoreuapShel_42; "onecoreuap\\shell\\cloudstore\\resolver"...
0x180079a5c  mov     edx, 81h
0x180079a61  call    ??$ReportFailure_CustomException@VCorruptDataException@@@details@wil@@YAXPEAXIPEBDVCorruptDataException@@@Z; wil::details::ReportFailure_CustomException<CorruptDataException>(void *,uint,char const *,CorruptDataException)
0x180079a67  lea     rcx, [rsp+150h+var_120]; this
0x180079a6c  call    ??0CorruptDataException@@QEAA@XZ; CorruptDataException::CorruptDataException(void)
0x180079a71  mov     rcx, [rbp+58h]
0x180079a75  mov     r9, rax
0x180079a78  lea     r8, aOnecoreuapShel_42; "onecoreuap\\shell\\cloudstore\\resolver"...
0x180079a7f  mov     edx, 7Dh ; '}'
0x180079a84  call    ??$ReportFailure_CustomException@VCorruptDataException@@@details@wil@@YAXPEAXIPEBDVCorruptDataException@@@Z; wil::details::ReportFailure_CustomException<CorruptDataException>(void *,uint,char const *,CorruptDataException)
0x180079a8a  mov     rcx, rbx
0x180079a8d  call    ?ValueType@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(void)
0x180079a92  cmp     eax, 2
0x180079a95  jnz     short loc_180079AB1
0x180079a97  mov     rcx, rbx
0x180079a9a  call    ?GetNumber@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(void)
0x180079a9f  cvttsd2si rdx, xmm0
0x180079aa4  mov     rcx, rdi
0x180079aa7  call    ?make@scalar@walkable@@SA?AV12@_J@Z; walkable::scalar::make(__int64)
0x180079aac  jmp     loc_180079770
0x180079ab1  lea     rcx, [rsp+150h+var_120]; this
0x180079ab6  call    ??0CorruptDataException@@QEAA@XZ; CorruptDataException::CorruptDataException(void)
0x180079abb  mov     rcx, [rbp+58h]
0x180079abf  mov     r9, rax
0x180079ac2  lea     r8, aOnecoreuapShel_42; "onecoreuap\\shell\\cloudstore\\resolver"...
0x180079ac9  mov     edx, 6Dh ; 'm'
0x180079ace  call    ??$ReportFailure_CustomException@VCorruptDataException@@@details@wil@@YAXPEAXIPEBDVCorruptDataException@@@Z; wil::details::ReportFailure_CustomException<CorruptDataException>(void *,uint,char const *,CorruptDataException)
0x180079ad4  mov     rcx, rbx
0x180079ad7  call    ?ValueType@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(void)
0x180079adc  cmp     eax, 2
0x180079adf  jnz     short loc_180079AFA
0x180079ae1  mov     rcx, rbx
0x180079ae4  call    ?GetNumber@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(void)
0x180079ae9  cvttsd2si edx, xmm0
0x180079aed  mov     rcx, rdi
0x180079af0  call    ?make@scalar@walkable@@SA?AV12@H@Z; walkable::scalar::make(int)
0x180079af5  jmp     loc_180079770
0x180079afa  lea     rcx, [rsp+150h+var_120]; this
0x180079aff  call    ??0CorruptDataException@@QEAA@XZ; CorruptDataException::CorruptDataException(void)
0x180079b04  mov     rcx, [rbp+58h]
0x180079b08  mov     r9, rax
0x180079b0b  lea     r8, aOnecoreuapShel_42; "onecoreuap\\shell\\cloudstore\\resolver"...
0x180079b12  mov     edx, 65h ; 'e'
0x180079b17  call    ??$ReportFailure_CustomException@VCorruptDataException@@@details@wil@@YAXPEAXIPEBDVCorruptDataException@@@Z; wil::details::ReportFailure_CustomException<CorruptDataException>(void *,uint,char const *,CorruptDataException)
0x180079b1d  mov     rcx, rbx
0x180079b20  call    ?ValueType@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(void)
0x180079b25  cmp     eax, 2
0x180079b28  jnz     short loc_180079B43
0x180079b2a  mov     rcx, rbx
0x180079b2d  call    ?GetNumber@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(void)
0x180079b32  cvttsd2si edx, xmm0
0x180079b36  mov     rcx, rdi
0x180079b39  call    ?make@scalar@walkable@@SA?AV12@F@Z; walkable::scalar::make(short)
0x180079b3e  jmp     loc_180079770
0x180079b43  lea     rcx, [rsp+150h+var_120]; this
0x180079b48  call    ??0CorruptDataException@@QEAA@XZ; CorruptDataException::CorruptDataException(void)
0x180079b4d  mov     rcx, [rbp+58h]
0x180079b51  mov     r9, rax
0x180079b54  lea     r8, aOnecoreuapShel_42; "onecoreuap\\shell\\cloudstore\\resolver"...
0x180079b5b  mov     edx, 5Dh ; ']'
0x180079b60  call    ??$ReportFailure_CustomException@VCorruptDataException@@@details@wil@@YAXPEAXIPEBDVCorruptDataException@@@Z; wil::details::ReportFailure_CustomException<CorruptDataException>(void *,uint,char const *,CorruptDataException)
0x180079b66  mov     rcx, rbx
0x180079b69  call    ?ValueType@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(void)
0x180079b6e  cmp     eax, 2
0x180079b71  jnz     short loc_180079B8C
0x180079b73  mov     rcx, rbx
0x180079b76  call    ?GetNumber@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetNumber(void)
0x180079b7b  cvttsd2si edx, xmm0
0x180079b7f  mov     rcx, rdi
0x180079b82  call    ?make@scalar@walkable@@SA?AV12@C@Z; walkable::scalar::make(signed char)
0x180079b87  jmp     loc_180079770
0x180079b8c  lea     rcx, [rsp+150h+var_120]; this
0x180079b91  call    ??0CorruptDataException@@QEAA@XZ; CorruptDataException::CorruptDataException(void)
  ... truncated ...
```
