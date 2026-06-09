# ChatServiceMessage::_PackMessage(ISmMessage *,AsyncMediaServiceDocument *,_GUID const *)

- ea: `0x180092a60`
- end: `0x180093d91`
- name: `?_PackMessage@ChatServiceMessage@@AEAAJPEAUISmMessage@@PEAVAsyncMediaServiceDocument@@PEBU_GUID@@@Z`
- size: `4913`
- prototype: `__int64 __fastcall(ChatServiceMessage *__hidden this, struct ISmMessage *, struct AsyncMediaServiceDocument *, const struct _GUID *)`
- caller_count: `0`
- callee_count: `29`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005c50`
- `0x180008870`
- `0x18000a754`
- `0x18000b6d4`
- `0x18000b7d4`
- `0x18000b7fc`
- `0x1800176b4`
- `0x180030bd0`
- `0x18003214c`
- `0x180033bd0`
- `0x18006b108`
- `0x1800761a4`
- `0x180084738`
- `0x1800847b8`
- `0x180084864`
- `0x1800848b4`
- `0x18008ebb4`
- `0x18008ed18`
- `0x180092810`
- `0x180092840`
- `0x180092a60`
- `0x180093d98`
- `0x18009a588`
- `0x18009a700`
- `0x1800b2f8c`
- `0x1800b33ec`
- `0x1800c50ec`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180093460`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180093460`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093c75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093c75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093c30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093c63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093ca0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093c30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093c63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093ca0`

## string_xrefs

- `0x180093435`: `Windows.Data.Json.JsonValue`
- `0x180093157`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
__int64 __fastcall ChatServiceMessage::_PackMessage(
        ChatServiceMessage *this,
        struct ISmMessage *a2,
        struct AsyncMediaServiceDocument *a3,
        const struct _GUID *a4)
{
  __int64 v4; // rax
  int v8; // ebx
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // eax
  int v17; // eax
  int v18; // ecx
  int v19; // eax
  struct ISmRecipient **v20; // rcx
  int v21; // eax
  int v22; // eax
  int v23; // ecx
  __int64 v24; // rax
  int v25; // eax
  int v26; // eax
  int v27; // ecx
  int IsServerSupportedId; // eax
  signed __int64 v29; // r8
  int v30; // eax
  int v31; // ecx
  unsigned int i; // ebx
  int v33; // eax
  int v34; // edi
  int v35; // eax
  int v36; // eax
  int v37; // eax
  __int64 v38; // rax
  int v39; // eax
  int v40; // eax
  int v41; // ecx
  int Md5Hash; // eax
  int v43; // ecx
  int ActivationFactory; // eax
  char v45; // r8
  const WCHAR *v46; // rdx
  __int64 v47; // rdi
  __int64 (__fastcall *v48)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v49; // rax
  int v50; // eax
  char v51; // r8
  __int64 v52; // rsi
  __int64 v53; // rbx
  __int64 (__fastcall *v54)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  int v58; // eax
  int v59; // ecx
  unsigned int v60; // eax
  __int64 v61; // rdx
  char v62; // r8
  const WCHAR *v63; // rdx
  __int64 v64; // rdi
  __int64 (__fastcall *v65)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v66; // rax
  int v67; // eax
  char v68; // r8
  int v69; // ecx
  __int64 v70; // rsi
  __int64 v71; // rbx
  __int64 (__fastcall *v72)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v73; // rax
  char v74; // r8
  const WCHAR *v75; // rdx
  __int64 v76; // rdi
  __int64 (__fastcall *v77)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v78; // rax
  int v79; // eax
  char v80; // r8
  __int64 v81; // rsi
  __int64 v82; // rbx
  __int64 (__fastcall *v83)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v84; // rax
  __int64 v85; // rax
  char v86; // r8
  const WCHAR *v87; // rdx
  __int64 v88; // rdi
  __int64 (__fastcall *v89)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v90; // rax
  int v91; // eax
  char v92; // r8
  __int64 v93; // rsi
  __int64 v94; // rbx
  __int64 (__fastcall *v95)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v96; // rax
  int v97; // eax
  char v98; // r8
  __int64 v99; // rdi
  __int64 (__fastcall *v100)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v101; // rax
  int v102; // eax
  char v103; // r8
  __int64 v104; // rsi
  __int64 v105; // rbx
  __int64 (__fastcall *v106)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v107; // rax
  char v108; // r8
  const WCHAR *v109; // rdx
  __int64 v110; // rdi
  __int64 (__fastcall *v111)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v112; // rax
  int v113; // eax
  char v114; // r8
  int v115; // ecx
  __int64 v116; // rsi
  __int64 v117; // rbx
  __int64 (__fastcall *v118)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v119; // rax
  char v120; // r8
  const WCHAR *v121; // rdx
  __int64 v122; // rdi
  __int64 (__fastcall *v123)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v124; // rax
  int v125; // eax
  char v126; // r8
  __int64 v127; // rsi
  __int64 v128; // rbx
  __int64 (__fastcall *v129)(__int64, PVOID, __int64, _BYTE *); // rdi
  HSTRING_HEADER *v130; // rax
  int v131; // eax
  __int64 v132; // rdi
  __int64 (__fastcall *v133)(__int64, HSTRING *); // rbx
  int v134; // eax
  int v135; // ecx
  PCWSTR StringRawBuffer; // rax
  const WCHAR *v138; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING_HEADER v139; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v140; // [rsp+50h] [rbp-B0h]
  __int64 v141; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v142[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v143; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall ***v144)(_QWORD, GUID *, __int64); // [rsp+70h] [rbp-90h] BYREF
  __int64 v145; // [rsp+78h] [rbp-88h] BYREF
  __int64 v146; // [rsp+80h] [rbp-80h] BYREF
  __int64 v147; // [rsp+88h] [rbp-78h] BYREF
  __int64 v148; // [rsp+90h] [rbp-70h] BYREF
  __int64 v149; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v150[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v151; // [rsp+B0h] [rbp-50h]
  __int64 v152; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v153[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v154; // [rsp+D8h] [rbp-28h]
  __int64 v155; // [rsp+E8h] [rbp-18h] BYREF
  struct ChatServiceParticipant *v156; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v157[2]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned int v158; // [rsp+118h] [rbp+18h] BYREF
  __int64 v159; // [rsp+120h] [rbp+20h] BYREF
  int v160; // [rsp+128h] [rbp+28h] BYREF
  HSTRING string; // [rsp+130h] [rbp+30h] BYREF
  __int64 v162; // [rsp+138h] [rbp+38h] BYREF
  __int64 v163; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v164; // [rsp+148h] [rbp+48h] BYREF
  int v165; // [rsp+14Ch] [rbp+4Ch] BYREF
  __int64 v166; // [rsp+150h] [rbp+50h] BYREF
  __int64 v167; // [rsp+158h] [rbp+58h] BYREF
  __int64 v168; // [rsp+160h] [rbp+60h] BYREF
  struct ISmRecipient *v169; // [rsp+168h] [rbp+68h] BYREF
  __int64 v170; // [rsp+170h] [rbp+70h] BYREF
  __int64 v171; // [rsp+178h] [rbp+78h] BYREF
  __int64 v172; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v173; // [rsp+188h] [rbp+88h] BYREF
  struct _FILETIME v174; // [rsp+190h] [rbp+90h] BYREF
  _OWORD v175[2]; // [rsp+198h] [rbp+98h] BYREF
  unsigned __int16 *v176[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  __int128 v177; // [rsp+1C8h] [rbp+C8h]
  __int128 hstringHeader; // [rsp+1D8h] [rbp+D8h] BYREF
  __int128 hstringHeader_16; // [rsp+1E8h] [rbp+E8h]
  _OWORD v180[2]; // [rsp+1F8h] [rbp+F8h] BYREF
  _OWORD v181[2]; // [rsp+218h] [rbp+118h] BYREF
  _OWORD v182[2]; // [rsp+238h] [rbp+138h] BYREF

  v4 = *(_QWORD *)a2;
  v165 = 0;
  v8 = (*(__int64 (__fastcall **)(struct ISmMessage *, int *, struct AsyncMediaServiceDocument *, const struct _GUID *))(v4 + 192))(
         a2,
         &v165,
         a3,
         a4);
  if ( v8 < 0 )
    goto LABEL_176;
  if ( v165 == 3 || v165 <= 0 || v165 >= 6 )
  {
    v8 = -2147024809;
LABEL_176:
    Log_HREvent_68(v8);
    return (unsigned int)v8;
  }
  v9 = *(_QWORD *)a2;
  v172 = 0;
  v10 = (*(__int64 (__fastcall **)(struct ISmMessage *, __int64 *))(v9 + 168))(a2, &v172);
  v8 = v10;
  if ( v10 >= 0 )
  {
    v158 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v172 + 56LL))(v172, &v158);
    v8 = v10;
    if ( v10 >= 0 )
    {
      if ( !v158 )
      {
        Log_AssertionEvent_51(v12, v11, 379);
        if ( !v158 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      v13 = *(_QWORD *)a2;
      v160 = 0;
      v10 = (*(__int64 (__fastcall **)(struct ISmMessage *, int *))(v13 + 432))(a2, &v160);
      v8 = v10;
      if ( v10 >= 0 )
      {
        v14 = *(_QWORD *)a2;
        v173 = 0;
        v141 = 0;
        v10 = (*(__int64 (__fastcall **)(struct ISmMessage *, unsigned int *, __int64 *))(v14 + 752))(a2, &v173, &v141);
        v8 = v10;
        if ( v10 >= 0 )
        {
          *(_OWORD *)v153 = 0;
          v154 = 0;
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v153);
          if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                   v153,
                                   v141,
                                   (unsigned __int64)v173 >> 1) )
          {
            v8 = -2147024882;
            Log_HREvent_68(-2147024882);
LABEL_15:
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v153);
            goto LABEL_174;
          }
          *(_OWORD *)v150 = 0;
          v151 = 0;
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v150);
          if ( (unsigned int)MessagingThreading::IsThreadedByRemoteConversationId(v153[0]) )
          {
            v15 = *(_QWORD *)a2;
            v162 = 0;
            v16 = (*(__int64 (__fastcall **)(struct ISmMessage *, __int64 *))(v15 + 400))(a2, &v162);
            v8 = v16;
            if ( v16 < 0 )
            {
              Log_HREvent_68(v16);
LABEL_19:
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v162);
LABEL_20:
              utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v150);
              goto LABEL_15;
            }
            v167 = 0;
            v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v162 + 64LL))(v162, &v167);
            v8 = v17;
            if ( v17 < 0 )
            {
              v18 = v17;
LABEL_23:
              Log_HREvent_68(v18);
              tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v167);
              goto LABEL_19;
            }
            if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                     (char *)this + 88,
                                     L"22:",
                                     3)
              || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                     (char *)this + 88,
                                     L"group_",
                                     6)
              || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                     v150,
                                     v167) )
            {
              v8 = -2147024882;
              v18 = -2147024882;
              goto LABEL_23;
            }
            tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v167);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v162);
            goto LABEL_55;
          }
          if ( v158 == 1 )
          {
            if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                     (char *)this + 88,
                                     L"21:",
                                     3) )
              goto LABEL_31;
            if ( !v160 )
            {
              v24 = *(_QWORD *)a2;
              v168 = 0;
              v25 = (*(__int64 (__fastcall **)(struct ISmMessage *, __int64 *))(v24 + 496))(a2, &v168);
              v8 = v25;
              if ( v25 >= 0 )
              {
                memset(v181, 0, sizeof(v181));
                utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v181);
                v26 = ChatServiceParticipant::FormatAddress(v168, v181);
                v8 = v26;
                if ( v26 >= 0 )
                {
                  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                          v150,
                                          *(_QWORD *)&v181[0],
                                          (__int64)(*((_QWORD *)&v181[0] + 1) - *(_QWORD *)&v181[0]) >> 1) )
                  {
                    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v181);
                    tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v168);
                    goto LABEL_55;
                  }
                  v8 = -2147024882;
                  v27 = -2147024882;
                }
                else
                {
                  v27 = v26;
                }
                Log_HREvent_68(v27);
                utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v181);
              }
              else
              {
                Log_HREvent_68(v25);
              }
              tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v168);
              goto LABEL_20;
            }
            v166 = 0;
            v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v172 + 48LL))(v172, 0, &v166);
            v8 = v19;
            if ( v19 < 0 )
            {
              Log_HREvent_68(v19);
              goto LABEL_35;
            }
            v171 = 0;
            v21 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v166 + 24LL))(v166, &v171);
            v8 = v21;
            if ( v21 < 0 )
            {
              Log_HREvent_68(v21);
LABEL_39:
              tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v171);
LABEL_35:
              v20 = (struct ISmRecipient **)&v166;
LABEL_36:
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v20);
              goto LABEL_20;
            }
            memset(v180, 0, sizeof(v180));
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v180);
            v22 = ChatServiceParticipant::FormatAddress(v171, v180);
            v8 = v22;
            if ( v22 < 0 )
            {
              v23 = v22;
LABEL_42:
              Log_HREvent_68(v23);
              utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v180);
              goto LABEL_39;
            }
            if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                     v150,
                                     *(_QWORD *)&v180[0],
                                     (__int64)(*((_QWORD *)&v180[0] + 1) - *(_QWORD *)&v180[0]) >> 1) )
            {
              v8 = -2147024882;
              v23 = -2147024882;
              goto LABEL_42;
            }
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v180);
            tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v171);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v166);
          }
LABEL_55:
          IsServerSupportedId = ChatServiceAlgorithms::IsServerSupportedId(v150[0]);
          v29 = v150[1] - v150[0];
          if ( IsServerSupportedId )
          {
            if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                     (char *)this + 88,
                                     v150[0],
                                     v29) )
              goto LABEL_31;
LABEL_65:
            for ( i = 0; i < v158; ++i )
            {
              v169 = 0;
              v33 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct ISmRecipient **))(*(_QWORD *)v172 + 48LL))(
                      v172,
                      i,
                      &v169);
              v34 = v33;
              if ( v33 < 0 )
              {
                Log_HREvent_68(v33);
                goto LABEL_74;
              }
              v156 = 0;
              v35 = ChatServiceParticipant::CreateInstance(v169, &v156);
              v34 = v35;
              if ( v35 < 0 )
              {
                Log_HREvent_68(v35);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v156);
LABEL_74:
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v169);
                utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v150);
                utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v153);
                v8 = v34;
                goto LABEL_174;
              }
              if ( !utl::vector<ATL::CComPtr<MessageChangeItem>,utl::allocator<ATL::CComPtr<MessageChangeItem>>>::emplace_back<ATL::CComPtr<MessageChangeItem> &,0>(
                      (__int64)this + 528,
                      &v156) )
              {
                v8 = -2147024882;
                Log_HREvent_68(-2147024882);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v156);
                v20 = &v169;
                goto LABEL_36;
              }
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v156);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v169);
            }
            v144 = 0;
            *((_QWORD *)&hstringHeader_16 + 1) = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              (HSTRING_HEADER *)&hstringHeader,
              L"Windows.Data.Json.JsonObject",
              0x1Du,
              0x1Cu);
            v36 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(
                    *((__int64 *)&hstringHeader_16 + 1),
                    &v144);
            v8 = v36;
            if ( v36 < 0 )
            {
              Log_HREvent_68(v36);
LABEL_77:
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v144);
              goto LABEL_20;
            }
            v143 = 0;
            v37 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,Windows::Data::Json::IJsonValue *>>(
                    &v144,
                    (__int64)&v143);
            v8 = v37;
            if ( v37 < 0 )
            {
              Log_HREvent_68(v37);
LABEL_80:
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v143);
              goto LABEL_77;
            }
            memset(v157, 0, sizeof(v157));
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v157);
            if ( v160 )
            {
              if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                       v157,
                                       L"ME",
                                       2) )
              {
LABEL_83:
                v8 = -2147024882;
                Log_HREvent_68(-2147024882);
LABEL_84:
                utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v157);
                goto LABEL_80;
              }
LABEL_102:
              if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                       (char *)this + 152,
                                       *(_QWORD *)&v157[0],
                                       (__int64)(*((_QWORD *)&v157[0] + 1) - *(_QWORD *)&v157[0]) >> 1)
                || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                       (char *)this + 120,
                                       L"21:",
                                       3)
                || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                       (char *)this + 120,
                                       *(_QWORD *)&v157[0],
                                       (__int64)(*((_QWORD *)&v157[0] + 1) - *(_QWORD *)&v157[0]) >> 1) )
              {
                goto LABEL_83;
              }
              v145 = 0;
              v140 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(
                &v139,
                L"Windows.Data.Json.JsonValue",
                0x1Cu,
                0x1Bu);
              ActivationFactory = RoGetActivationFactory(v140, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v145);
              v8 = ActivationFactory;
              if ( ActivationFactory < 0 )
              {
                Log_HREvent_68(ActivationFactory);
LABEL_107:
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v145);
                goto LABEL_84;
              }
              v46 = (const WCHAR *)*((_QWORD *)this + 15);
              v146 = 0;
              v47 = v145;
              v138 = v46;
              v48 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v145 + 80LL);
              v49 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v139, &v138, v45);
              v50 = v48(v47, v49[1].Reserved.Reserved1, &v146);
              v8 = v50;
              if ( v50 < 0 )
                goto LABEL_109;
              v52 = v143;
              v53 = v146;
              v142[0] = 0;
              v54 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v143 + 80LL);
              v55 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &v139,
                      (const WCHAR **)off_1800FD740,
                      v51);
              v50 = v54(v52, v55[1].Reserved.Reserved1, v53, v142);
              v8 = v50;
              if ( v50 < 0
                || (v56 = *(_QWORD *)a2,
                    v164 = -1,
                    v50 = (*(__int64 (__fastcall **)(struct ISmMessage *, unsigned int *))(v56 + 560))(a2, &v164),
                    v8 = v50,
                    v50 < 0) )
              {
LABEL_109:
                Log_HREvent_68(v50);
LABEL_110:
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v146);
                goto LABEL_107;
              }
              v57 = *(_QWORD *)a2;
              v147 = 0;
              v58 = (*(__int64 (__fastcall **)(struct ISmMessage *, __int64 *))(v57 + 656))(a2, &v147);
              v8 = v58;
              if ( v58 < 0
                || (v58 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                            (char *)this + 216,
                            L"%c%lu%c%s",
                            59,
                            v164,
                            59,
                            v147),
                    v8 = v58,
                    v58 < 0) )
              {
                v59 = v58;
LABEL_115:
                Log_HREvent_68(v59);
LABEL_116:
                tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v147);
                goto LABEL_110;
              }
              v60 = v164;
              v61 = v147;
              *(GUID *)((char *)this + 248) = GUID_NULL;
              *((_DWORD *)this + 66) = v60;
              if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                       (char *)this + 272,
                                       v61) )
              {
                v8 = -2147024882;
                v59 = -2147024882;
                goto LABEL_115;
              }
              v63 = (const WCHAR *)*((_QWORD *)this + 27);
              v64 = v145;
              v148 = 0;
              v138 = v63;
              v65 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v145 + 80LL);
              v66 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v139, &v138, v62);
              v67 = v65(v64, v66[1].Reserved.Reserved1, &v148);
              v8 = v67;
              if ( v67 < 0
                || (v70 = v143,
                    v71 = v148,
                    v72 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v143 + 80LL),
                    v73 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                            &v139,
                            (const WCHAR **)off_1800FD730,
                            v68),
                    v67 = v72(v70, v73[1].Reserved.Reserved1, v71, v142),
                    v8 = v67,
                    v67 < 0) )
              {
                v69 = v67;
LABEL_122:
                Log_HREvent_68(v69);
LABEL_123:
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v148);
                goto LABEL_116;
              }
              if ( v165 == 1 || v165 == 4 )
              {
                if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                         (char *)this + 304,
                                         L"RichText/Sms",
                                         12) )
                {
LABEL_132:
                  v8 = -2147024882;
                  v69 = -2147024882;
                  goto LABEL_122;
                }
              }
              else if ( (v165 == 2 || v165 == 5)
                     && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                            (char *)this + 304,
                                            L"RichText/Mms",
                                            12) )
              {
                goto LABEL_132;
              }
              v75 = (const WCHAR *)*((_QWORD *)this + 38);
              v76 = v145;
              v149 = 0;
              v138 = v75;
              v77 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v145 + 80LL);
              v78 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v139, &v138, v74);
              v79 = v77(v76, v78[1].Reserved.Reserved1, &v149);
              v8 = v79;
              if ( v79 < 0 )
                goto LABEL_134;
              v81 = v143;
              v82 = v149;
              v83 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v143 + 80LL);
              v84 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                      &v139,
                      (const WCHAR **)off_1800FD738,
                      v80);
              v79 = v83(v81, v84[1].Reserved.Reserved1, v82, v142);
              v8 = v79;
              if ( v79 < 0 )
                goto LABEL_134;
              v85 = *(_QWORD *)a2;
              v174 = 0;
              if ( v160 )
              {
                v79 = (*(__int64 (__fastcall **)(struct ISmMessage *, struct _FILETIME *))(v85 + 152))(a2, &v174);
                v8 = v79;
                if ( v79 < 0 )
                  goto LABEL_134;
              }
              else
              {
                v79 = (*(__int64 (__fastcall **)(struct ISmMessage *, struct _FILETIME *))(v85 + 136))(a2, &v174);
                v8 = v79;
                if ( v79 < 0 )
                  goto LABEL_134;
              }
              *((struct _FILETIME *)this + 47) = v174;
              v79 = CloudServiceDateTime::FileTimeToIsoTime(&v174, (char *)this + 336);
              v8 = v79;
              if ( v79 >= 0 )
              {
                v87 = (const WCHAR *)*((_QWORD *)this + 42);
                v152 = 0;
                v88 = v145;
                v138 = v87;
                v89 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v145 + 80LL);
                v90 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v139, &v138, v86);
                v91 = v89(v88, v90[1].Reserved.Reserved1, &v152);
                v8 = v91;
                if ( v91 < 0
                  || (v93 = v143,
                      v94 = v152,
                      v95 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v143 + 80LL),
                      v96 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                              &v139,
                              (const WCHAR **)off_1800FD728,
                              v92),
                      v91 = v95(v93, v96[1].Reserved.Reserved1, v94, v142),
                      v8 = v91,
                      v91 < 0) )
                {
                  Log_HREvent_68(v91);
LABEL_144:
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v152);
                  goto LABEL_135;
                }
                *((_QWORD *)this + 46) = CloudServiceDateTime::GetUtcTimeFromFileTimeInSeconds(&v174);
                *((_QWORD *)this + 74) = (*(__int64 (__fastcall **)(struct ISmMessage *))(*(_QWORD *)a2 + 704LL))(a2);
                memset(v175, 0, sizeof(v175));
                utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v175);
                v97 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                        v175,
                        L"%I64u");
                v8 = v97;
                if ( v97 < 0 )
                {
                  Log_HREvent_68(v97);
LABEL_148:
                  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v175);
                  goto LABEL_144;
                }
                v99 = v145;
                v155 = 0;
                v138 = *(const WCHAR **)&v175[0];
                v100 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v145 + 80LL);
                v101 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v139, &v138, v98);
                v102 = v100(v99, v101[1].Reserved.Reserved1, &v155);
                v8 = v102;
                if ( v102 < 0 )
                  goto LABEL_150;
                v104 = v143;
                v105 = v155;
                v106 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v143 + 80LL);
                v107 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                         &v139,
                         (const WCHAR **)off_1800FD720,
                         v103);
                v102 = v106(v104, v107[1].Reserved.Reserved1, v105, v142);
                v8 = v102;
                if ( v102 < 0
                  || (v102 = ChatServiceMessage::_PackMessageEnvelope(
                               (__int64)this,
                               (__int64 *)a2,
                               a3,
                               (__int64)this + 392),
                      v8 = v102,
                      v102 < 0) )
                {
LABEL_150:
                  Log_HREvent_68(v102);
LABEL_151:
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v155);
                  goto LABEL_148;
                }
                v109 = (const WCHAR *)*((_QWORD *)this + 49);
                v110 = v145;
                v159 = 0;
                v138 = v109;
                v111 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v145 + 80LL);
                v112 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v139, &v138, v108);
                v113 = v111(v110, v112[1].Reserved.Reserved1, &v159);
                v8 = v113;
                if ( v113 < 0
                  || (v116 = v143,
                      v117 = v159,
                      v118 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v143 + 80LL),
                      v119 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                               &v139,
                               (const WCHAR **)off_1800FD708,
                               v114),
                      v113 = v118(v116, v119[1].Reserved.Reserved1, v117, v142),
                      v8 = v113,
                      v113 < 0) )
                {
                  v115 = v113;
                }
                else
                {
                  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                          (char *)this + 432,
                                          L"text/plain",
                                          10) )
                  {
                    v121 = (const WCHAR *)*((_QWORD *)this + 54);
                    v122 = v145;
                    v163 = 0;
                    v138 = v121;
                    v123 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v145 + 80LL);
                    v124 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v139, &v138, v120);
                    v125 = v123(v122, v124[1].Reserved.Reserved1, &v163);
                    v8 = v125;
                    if ( v125 < 0
                      || (v127 = v143,
                          v128 = v163,
                          v129 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)v143 + 80LL),
                          v130 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                                   &v139,
                                   (const WCHAR **)off_1800FD710,
                                   v126),
                          v125 = v129(v127, v130[1].Reserved.Reserved1, v128, v142),
                          v8 = v125,
                          v125 < 0) )
                    {
                      Log_HREvent_68(v125);
                    }
                    else
                    {
                      v170 = 0;
                      v131 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>::As<Windows::Data::Json::IJsonValue>(
                               &v144,
                               (__int64)&v170);
                      v8 = v131;
                      if ( v131 >= 0 )
                      {
                        v132 = v170;
                        string = 0;
                        v133 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v170 + 56LL);
                        WindowsDeleteString(0);
                        string = 0;
                        v134 = v133(v132, &string);
                        v8 = v134;
                        if ( v134 >= 0 )
                        {
                          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                                  (char *)this + 24,
                                                  StringRawBuffer) )
                          {
                            WindowsDeleteString(string);
                            string = 0;
                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v170);
                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v163);
                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v159);
                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v155);
                            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v175);
                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v152);
                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v149);
                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v148);
                            tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v147);
                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v146);
                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v145);
                            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v157);
                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v143);
                            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v144);
                            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v150);
                            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v153);
                            v8 = 0;
                            goto LABEL_174;
                          }
                          v8 = -2147024882;
                          v135 = -2147024882;
                        }
                        else
                        {
                          v135 = v134;
                        }
                        Log_HREvent_68(v135);
                        WindowsDeleteString(string);
                        string = 0;
                      }
                      else
                      {
                        Log_HREvent_68(v131);
                      }
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v170);
                    }
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v163);
                    goto LABEL_157;
                  }
                  v8 = -2147024882;
                  v115 = -2147024882;
                }
                Log_HREvent_68(v115);
LABEL_157:
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v159);
                goto LABEL_151;
              }
LABEL_134:
              Log_HREvent_68(v79);
LABEL_135:
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v149);
              goto LABEL_123;
            }
            v38 = *(_QWORD *)a2;
            v156 = 0;
            v39 = (*(__int64 (__fastcall **)(struct ISmMessage *, struct ChatServiceParticipant **))(v38 + 496))(
                    a2,
                    &v156);
            v8 = v39;
            if ( v39 < 0 )
            {
              Log_HREvent_68(v39);
LABEL_87:
              tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v156);
              goto LABEL_84;
            }
            *(_OWORD *)v176 = 0;
            v177 = 0;
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v176);
            v40 = ChatServiceParticipant::FormatAddress(v156, v176);
            v8 = v40;
            if ( v40 < 0 )
            {
              v41 = v40;
LABEL_90:
              Log_HREvent_68(v41);
LABEL_91:
              utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v176);
              goto LABEL_87;
            }
            if ( (unsigned int)ChatServiceAlgorithms::IsServerSupportedId(v176[0]) )
            {
              if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                       v157,
                                       v176[0],
                                       v176[1] - v176[0]) )
              {
                v8 = -2147024882;
                v41 = -2147024882;
                goto LABEL_90;
              }
LABEL_101:
              utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v176);
              tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::_Delete(&v156);
              goto LABEL_102;
            }
            hstringHeader = 0;
            hstringHeader_16 = 0;
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(&hstringHeader);
            Md5Hash = ChatServiceAlgorithms::GetMd5Hash((__int64)v176[0], (__int64)&hstringHeader);
            v8 = Md5Hash;
            if ( Md5Hash >= 0 )
            {
              if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                      v157,
                                      hstringHeader,
                                      (__int64)(*((_QWORD *)&hstringHeader + 1) - hstringHeader) >> 1) )
              {
                utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&hstringHeader);
                goto LABEL_101;
              }
              v8 = -2147024882;
              v43 = -2147024882;
            }
            else
            {
              v43 = Md5Hash;
            }
            Log_HREvent_68(v43);
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(&hstringHeader);
            goto LABEL_91;
          }
          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                  (char *)this + 184,
                                  v150[0],
                                  v29) )
          {
            memset(v182, 0, sizeof(v182));
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v182);
            v30 = ChatServiceAlgorithms::GetMd5Hash((__int64)v150[0], (__int64)v182);
            v8 = v30;
            if ( v30 >= 0 )
            {
              if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                      (char *)this + 88,
                                      *(_QWORD *)&v182[0],
                                      (__int64)(*((_QWORD *)&v182[0] + 1) - *(_QWORD *)&v182[0]) >> 1) )
              {
                utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v182);
                goto LABEL_65;
              }
              v8 = -2147024882;
              v31 = -2147024882;
            }
            else
            {
              v31 = v30;
            }
            Log_HREvent_68(v31);
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v182);
            goto LABEL_20;
          }
LABEL_31:
          v8 = -2147024882;
          Log_HREvent_68(-2147024882);
          goto LABEL_20;
        }
      }
    }
  }
  Log_HREvent_68(v10);
LABEL_174:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v172);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180092a60  mov     [rsp-8+arg_18], rbx
0x180092a65  push    rbp
0x180092a66  push    rsi
0x180092a67  push    rdi
0x180092a68  push    r12
0x180092a6a  push    r13
0x180092a6c  push    r14
0x180092a6e  push    r15
0x180092a70  lea     rbp, [rsp-160h]
0x180092a78  sub     rsp, 260h
0x180092a7f  mov     rax, cs:__security_cookie
0x180092a86  xor     rax, rsp
0x180092a89  mov     [rbp+190h+var_38], rax
0x180092a90  mov     rax, [rdx]
0x180092a93  mov     r12, rdx
0x180092a96  mov     r15, rcx
0x180092a99  lea     rdx, [rbp+190h+var_144]
0x180092a9d  xor     edi, edi
0x180092a9f  mov     rcx, r12
0x180092aa2  mov     r13, r8
0x180092aa5  mov     [rbp+190h+var_144], edi
0x180092aa8  mov     rax, [rax+0C0h]
0x180092aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092ab4  mov     ebx, eax
0x180092ab6  test    eax, eax
0x180092ab8  jns     short loc_180092AC8
0x180092aba  lea     edx, [rdi+1]
0x180092abd  mov     r9d, 170h
0x180092ac3  jmp     loc_180093D5E
0x180092ac8  mov     eax, [rbp+190h+var_144]
0x180092acb  mov     esi, 3
0x180092ad0  cmp     eax, esi
0x180092ad2  jz      loc_180093D51
0x180092ad8  test    eax, eax
0x180092ada  jle     loc_180093D51
0x180092ae0  cmp     eax, 6
0x180092ae3  jge     loc_180093D51
0x180092ae9  mov     rax, [r12]
0x180092aed  lea     rdx, [rbp+190h+var_110]
0x180092af4  mov     rcx, r12
0x180092af7  mov     [rbp+190h+var_110], rdi
0x180092afe  mov     rax, [rax+0A8h]
0x180092b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092b0a  mov     ebx, eax
0x180092b0c  test    eax, eax
0x180092b0e  jns     short loc_180092B18
0x180092b10  mov     r9d, 177h
0x180092b16  jmp     short loc_180092B3E
0x180092b18  mov     rcx, [rbp+190h+var_110]
0x180092b1f  lea     rdx, [rbp+190h+var_178]
0x180092b23  mov     [rbp+190h+var_178], edi
0x180092b26  mov     rax, [rcx]
0x180092b29  mov     rax, [rax+38h]
0x180092b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092b32  mov     ebx, eax
0x180092b34  test    eax, eax
0x180092b36  jns     short loc_180092B4F
0x180092b38  mov     r9d, 17Ah
0x180092b3e  mov     edx, 1
0x180092b43  mov     ecx, eax; int
0x180092b45  call    Log_HREvent_68
0x180092b4a  jmp     loc_180093D43
0x180092b4f  cmp     [rbp+190h+var_178], edi
0x180092b52  ja      short loc_180092B69
0x180092b54  mov     r8d, 17Bh
0x180092b5a  call    Log_AssertionEvent_51
0x180092b5f  cmp     [rbp+190h+var_178], edi
0x180092b62  ja      short loc_180092B69
0x180092b64  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180092b69  mov     rax, [r12]
0x180092b6d  lea     rdx, [rbp+190h+var_168]
0x180092b71  mov     rcx, r12
0x180092b74  mov     [rbp+190h+var_168], edi
0x180092b77  mov     rax, [rax+1B0h]
0x180092b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092b83  mov     ebx, eax
0x180092b85  test    eax, eax
0x180092b87  jns     short loc_180092B91
0x180092b89  mov     r9d, 17Eh
0x180092b8f  jmp     short loc_180092B3E
0x180092b91  mov     rax, [r12]
0x180092b95  lea     r8, [rsp+290h+var_238]
0x180092b9a  lea     rdx, [rbp+190h+var_108]
0x180092ba1  mov     [rbp+190h+var_108], edi
0x180092ba7  mov     rcx, r12
0x180092baa  mov     [rsp+290h+var_238], rdi
0x180092baf  mov     rax, [rax+2F0h]
0x180092bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092bbb  mov     ebx, eax
0x180092bbd  test    eax, eax
0x180092bbf  jns     short loc_180092BCC
0x180092bc1  mov     r9d, 182h
0x180092bc7  jmp     loc_180092B3E
0x180092bcc  xorps   xmm0, xmm0
0x180092bcf  lea     rcx, [rbp+190h+var_1C8]
0x180092bd3  movups  xmmword ptr [rbp+190h+var_1C8], xmm0
0x180092bd7  movups  [rbp+190h+var_1B8], xmm0
0x180092bdb  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180092be0  mov     r8d, [rbp+190h+var_108]
0x180092be7  lea     rcx, [rbp+190h+var_1C8]
0x180092beb  mov     rdx, [rsp+290h+var_238]
0x180092bf0  shr     r8, 1
0x180092bf3  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180092bf8  test    al, al
0x180092bfa  jnz     short loc_180092C1E
0x180092bfc  mov     ebx, 8007000Eh
0x180092c01  xor     edx, edx
0x180092c03  mov     ecx, ebx; int
0x180092c05  mov     r9d, 185h
0x180092c0b  call    Log_HREvent_68
0x180092c10  lea     rcx, [rbp+190h+var_1C8]
0x180092c14  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180092c19  jmp     loc_180093D43
0x180092c1e  xorps   xmm0, xmm0
0x180092c21  lea     rcx, [rbp+190h+var_1F0]
0x180092c25  movups  xmmword ptr [rbp+190h+var_1F0], xmm0
0x180092c29  movups  [rbp+190h+var_1E0], xmm0
0x180092c2d  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180092c32  mov     rcx, [rbp+190h+var_1C8]; unsigned __int16 *
0x180092c36  call    ?IsThreadedByRemoteConversationId@MessagingThreading@@SAHPEBG@Z; MessagingThreading::IsThreadedByRemoteConversationId(ushort const *)
0x180092c3b  mov     r14d, 1
0x180092c41  test    eax, eax
0x180092c43  jz      loc_180092D41
0x180092c49  mov     rax, [r12]
0x180092c4d  lea     rdx, [rbp+190h+var_158]
0x180092c51  mov     rcx, r12
0x180092c54  mov     [rbp+190h+var_158], rdi
0x180092c58  mov     rax, [rax+190h]
0x180092c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092c64  mov     ebx, eax
0x180092c66  test    eax, eax
0x180092c68  jns     short loc_180092C8E
0x180092c6a  mov     r9d, 18Fh
0x180092c70  mov     edx, r14d
0x180092c73  mov     ecx, eax; int
0x180092c75  call    Log_HREvent_68
0x180092c7a  lea     rcx, [rbp+190h+var_158]
0x180092c7e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180092c83  lea     rcx, [rbp+190h+var_1F0]
0x180092c87  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180092c8c  jmp     short loc_180092C10
0x180092c8e  mov     rcx, [rbp+190h+var_158]
0x180092c92  lea     rdx, [rbp+190h+var_138]
0x180092c96  mov     [rbp+190h+var_138], rdi
0x180092c9a  mov     rax, [rcx]
0x180092c9d  mov     rax, [rax+40h]
0x180092ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092ca6  mov     ebx, eax
0x180092ca8  test    eax, eax
0x180092caa  jns     short loc_180092CC7
0x180092cac  mov     r9d, 191h
0x180092cb2  mov     edx, r14d
0x180092cb5  mov     ecx, eax; int
0x180092cb7  call    Log_HREvent_68
0x180092cbc  lea     rcx, [rbp+190h+var_138]
0x180092cc0  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x180092cc5  jmp     short loc_180092C7A
0x180092cc7  mov     r8, rsi
0x180092cca  lea     rdx, a22; "22:"
0x180092cd1  lea     rcx, [r15+58h]
0x180092cd5  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180092cda  test    al, al
0x180092cdc  jnz     short loc_180092CEF
0x180092cde  mov     r9d, 193h
0x180092ce4  mov     ebx, 8007000Eh
0x180092ce9  xor     edx, edx
0x180092ceb  mov     ecx, ebx
0x180092ced  jmp     short loc_180092CB7
0x180092cef  mov     r8d, 6
0x180092cf5  lea     rdx, aGroup; "group_"
0x180092cfc  lea     rcx, [r15+58h]
0x180092d00  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180092d05  test    al, al
0x180092d07  jnz     short loc_180092D11
0x180092d09  mov     r9d, 194h
0x180092d0f  jmp     short loc_180092CE4
0x180092d11  mov     rdx, [rbp+190h+var_138]
0x180092d15  lea     rcx, [rbp+190h+var_1F0]
0x180092d19  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180092d1e  test    al, al
0x180092d20  jnz     short loc_180092D2A
0x180092d22  mov     r9d, 195h
0x180092d28  jmp     short loc_180092CE4
0x180092d2a  lea     rcx, [rbp+190h+var_138]
0x180092d2e  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x180092d33  lea     rcx, [rbp+190h+var_158]
0x180092d37  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180092d3c  jmp     loc_180092F7B
0x180092d41  cmp     [rbp+190h+var_178], r14d
0x180092d45  jnz     loc_180092F7B
0x180092d4b  lea     rcx, [r15+58h]
0x180092d4f  mov     r8, rsi
0x180092d52  lea     rdx, a21; "21:"
0x180092d59  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180092d5e  test    al, al
0x180092d60  jnz     short loc_180092D7B
0x180092d62  mov     r9d, 199h
0x180092d68  mov     ebx, 8007000Eh
0x180092d6d  xor     edx, edx
0x180092d6f  mov     ecx, ebx; int
0x180092d71  call    Log_HREvent_68
0x180092d76  jmp     loc_180092C83
0x180092d7b  cmp     [rbp+190h+var_168], edi
0x180092d7e  jz      loc_180092EA4
0x180092d84  mov     rcx, [rbp+190h+var_110]
0x180092d8b  lea     r8, [rbp+190h+var_140]
0x180092d8f  mov     [rbp+190h+var_140], rdi
0x180092d93  xor     edx, edx
0x180092d95  mov     rax, [rcx]
0x180092d98  mov     rax, [rax+30h]
0x180092d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092da1  mov     ebx, eax
0x180092da3  test    eax, eax
0x180092da5  jns     short loc_180092DC5
0x180092da7  mov     r9d, 19Eh
0x180092dad  mov     edx, r14d
0x180092db0  mov     ecx, eax; int
0x180092db2  call    Log_HREvent_68
0x180092db7  lea     rcx, [rbp+190h+var_140]
0x180092dbb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180092dc0  jmp     loc_180092C83
0x180092dc5  mov     rcx, [rbp+190h+var_140]
0x180092dc9  lea     rdx, [rbp+190h+var_118]
0x180092dcd  mov     [rbp+190h+var_118], rdi
0x180092dd1  mov     rax, [rcx]
0x180092dd4  mov     rax, [rax+18h]
0x180092dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092ddd  mov     ebx, eax
0x180092ddf  test    eax, eax
0x180092de1  jns     short loc_180092DFE
0x180092de3  mov     r9d, 1A1h
0x180092de9  mov     edx, r14d
0x180092dec  mov     ecx, eax; int
0x180092dee  call    Log_HREvent_68
0x180092df3  lea     rcx, [rbp+190h+var_118]
0x180092df7  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x180092dfc  jmp     short loc_180092DB7
0x180092dfe  xorps   xmm0, xmm0
0x180092e01  lea     rcx, [rbp+190h+var_98]
0x180092e08  movups  [rbp+190h+var_98], xmm0
0x180092e0f  movups  [rbp+190h+var_88], xmm0
0x180092e16  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180092e1b  mov     rcx, [rbp+190h+var_118]
0x180092e1f  lea     rdx, [rbp+190h+var_98]
0x180092e26  call    ?FormatAddress@ChatServiceParticipant@@SAJPEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; ChatServiceParticipant::FormatAddress(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180092e2b  mov     ebx, eax
0x180092e2d  test    eax, eax
0x180092e2f  jns     short loc_180092E4F
0x180092e31  mov     r9d, 1A4h
0x180092e37  mov     edx, r14d
0x180092e3a  mov     ecx, eax; int
0x180092e3c  call    Log_HREvent_68
0x180092e41  lea     rcx, [rbp+190h+var_98]
0x180092e48  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180092e4d  jmp     short loc_180092DF3
0x180092e4f  mov     r8, qword ptr [rbp+190h+var_98+8]
0x180092e56  lea     rcx, [rbp+190h+var_1F0]
0x180092e5a  mov     rdx, qword ptr [rbp+190h+var_98]
0x180092e61  sub     r8, rdx
0x180092e64  sar     r8, 1
0x180092e67  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180092e6c  test    al, al
0x180092e6e  jnz     short loc_180092E81
0x180092e70  mov     ebx, 8007000Eh
0x180092e75  xor     edx, edx
0x180092e77  mov     ecx, ebx
0x180092e79  mov     r9d, 1A6h
0x180092e7f  jmp     short loc_180092E3C
0x180092e81  lea     rcx, [rbp+190h+var_98]
0x180092e88  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180092e8d  lea     rcx, [rbp+190h+var_118]
0x180092e91  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x180092e96  lea     rcx, [rbp+190h+var_140]
0x180092e9a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180092e9f  jmp     loc_180092F7B
0x180092ea4  mov     rax, [r12]
0x180092ea8  lea     rdx, [rbp+190h+var_130]
0x180092eac  mov     rcx, r12
0x180092eaf  mov     [rbp+190h+var_130], rdi
0x180092eb3  mov     rax, [rax+1F0h]
0x180092eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092ebf  mov     ebx, eax
0x180092ec1  test    eax, eax
0x180092ec3  jns     short loc_180092EE3
0x180092ec5  mov     r9d, 1ACh
0x180092ecb  mov     edx, r14d
0x180092ece  mov     ecx, eax; int
0x180092ed0  call    Log_HREvent_68
0x180092ed5  lea     rcx, [rbp+190h+var_130]
0x180092ed9  call    ?_Delete@?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>::_Delete(void)
0x180092ede  jmp     loc_180092C83
0x180092ee3  xorps   xmm0, xmm0
0x180092ee6  lea     rcx, [rbp+190h+var_78]
0x180092eed  movups  [rbp+190h+var_78], xmm0
0x180092ef4  movups  [rbp+190h+var_68], xmm0
0x180092efb  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180092f00  mov     rcx, [rbp+190h+var_130]
0x180092f04  lea     rdx, [rbp+190h+var_78]
0x180092f0b  call    ?FormatAddress@ChatServiceParticipant@@SAJPEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; ChatServiceParticipant::FormatAddress(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180092f10  mov     ebx, eax
  ... truncated ...
```
