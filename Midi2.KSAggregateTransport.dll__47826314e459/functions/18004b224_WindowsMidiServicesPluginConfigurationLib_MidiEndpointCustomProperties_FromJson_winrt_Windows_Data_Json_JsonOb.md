# WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::FromJson(winrt::Windows::Data::Json::JsonObject const &)

- ea: `0x18004b224`
- end: `0x18004bcda`
- name: `?FromJson@MidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@SA?AV?$shared_ptr@VMidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@AEBUJsonObject@Json@Data@Windows@winrt@@@Z`
- size: `2742`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001dd50`

## callees

- `0x180005070`
- `0x1800050b4`
- `0x180005e16`
- `0x180005e9c`
- `0x180005f2c`
- `0x180005fa4`
- `0x18000d778`
- `0x180010b94`
- `0x180014f00`
- `0x180014f84`
- `0x180014ff4`
- `0x1800199c4`
- `0x18001a124`
- `0x18001a4a8`
- `0x18001a844`
- `0x18001cb00`
- `0x18001cf74`
- `0x18001d0bc`
- `0x18001d12c`
- `0x18001d204`
- `0x18001d270`
- `0x18001e600`
- `0x18004adf4`
- `0x18004b0ec`
- `0x18004b224`
- `0x18004bce0`
- `0x18004bdb0`
- `0x18004be90`
- `0x18004c140`
- `0x18005e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004b6ac`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004b6fd`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004b6ac`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18004b6fd`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004b4f4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004b503`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004b512`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004ba2b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004bb7f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004bbea`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004bbf9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004b4f4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004b503`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004b512`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004ba2b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004bb7f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004bbea`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004bbf9`

## string_xrefs

- `0x18004b737`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x18004ba1b`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x18004b4a9`: `recommendedControlChangeIntervalMilliseconds`
- `0x18004b646`: `classicCompatible`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties **__fastcall WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::FromJson(
        WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties **a1,
        __int64 a2)
{
  WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties **v3; // r12
  _QWORD *v4; // r15
  WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties *v5; // r14
  __int64 NamedString; // rax
  void *v7; // rsi
  int v8; // eax
  HANDLE ProcessHeap; // rax
  __int64 v10; // rax
  void *v11; // rsi
  int v12; // eax
  HANDLE v13; // rax
  __int64 v14; // rax
  void *v15; // rsi
  int v16; // eax
  HANDLE v17; // rax
  char v18; // al
  double NamedNumber; // xmm0_8
  int v20; // eax
  unsigned int v21; // edx
  __int64 v22; // rcx
  struct winrt::impl::shared_hstring_header *v23; // rax
  unsigned int v24; // edx
  struct winrt::impl::shared_hstring_header *v25; // rdi
  struct winrt::impl::shared_hstring_header *v26; // rax
  struct winrt::impl::shared_hstring_header *v27; // rdi
  int **i; // r12
  int v29; // eax
  int v30; // r13d
  int v31; // eax
  int v32; // eax
  __int64 v33; // rax
  struct winrt::impl::hstring_header *v34; // rdx
  void *v35; // rdi
  int v36; // eax
  HANDLE v37; // rax
  int v38; // esi
  winrt::impl *v39; // r15
  winrt::impl *v40; // rdi
  int v41; // ecx
  HANDLE v42; // rax
  int *v43; // rcx
  __int64 v44; // rsi
  struct winrt::impl::hstring_header *v45; // rdx
  struct winrt::impl::hstring_header *v46; // r15
  volatile signed __int32 *v47; // rdi
  int v48; // ecx
  HANDLE v49; // rax
  winrt::impl *v50; // rdi
  int v51; // eax
  HANDLE v52; // rax
  winrt::impl *v53; // rdi
  int v54; // eax
  HANDLE v55; // rax
  int *v56; // rcx
  struct winrt::impl::hstring_header *v57; // rdx
  WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties **result; // rax
  __int64 *v59; // [rsp+20h] [rbp-158h] BYREF
  __int64 v60; // [rsp+28h] [rbp-150h] BYREF
  __int64 v61; // [rsp+30h] [rbp-148h]
  const wchar_t *v62; // [rsp+38h] [rbp-140h]
  __int64 v63; // [rsp+40h] [rbp-138h] BYREF
  __int64 v64; // [rsp+48h] [rbp-130h] BYREF
  winrt::impl *v65; // [rsp+50h] [rbp-128h]
  winrt::impl *v66; // [rsp+58h] [rbp-120h] BYREF
  __int64 v67; // [rsp+60h] [rbp-118h] BYREF
  LPVOID v68; // [rsp+68h] [rbp-110h] BYREF
  __int64 v69; // [rsp+70h] [rbp-108h] BYREF
  double v70; // [rsp+78h] [rbp-100h] BYREF
  int *v71; // [rsp+80h] [rbp-F8h] BYREF
  int v72; // [rsp+88h] [rbp-F0h] BYREF
  int v73; // [rsp+8Ch] [rbp-ECh]
  const wchar_t *v74; // [rsp+98h] [rbp-E0h]
  LPVOID v75; // [rsp+A0h] [rbp-D8h] BYREF
  _QWORD *v76; // [rsp+A8h] [rbp-D0h]
  _QWORD v77[2]; // [rsp+B0h] [rbp-C8h] BYREF
  char v78; // [rsp+C0h] [rbp-B8h] BYREF
  LPVOID *v79; // [rsp+C8h] [rbp-B0h] BYREF
  int v80; // [rsp+D0h] [rbp-A8h]
  __int128 v81; // [rsp+D8h] [rbp-A0h] BYREF
  _DWORD *v82; // [rsp+E8h] [rbp-90h] BYREF
  _DWORD v83[4]; // [rsp+F0h] [rbp-88h] BYREF
  const wchar_t *v84; // [rsp+100h] [rbp-78h]
  _DWORD *v85; // [rsp+108h] [rbp-70h] BYREF
  _DWORD v86[4]; // [rsp+110h] [rbp-68h] BYREF
  const wchar_t *v87; // [rsp+120h] [rbp-58h]
  LPVOID lpMem; // [rsp+190h] [rbp+18h] BYREF
  __int64 v90; // [rsp+198h] [rbp+20h] BYREF

  v3 = a1;
  try
  {
    v4 = operator new(0x58u);
    v76 = v4;
    lpMem = v4;
    *((_DWORD *)v4 + 2) = 1;
    *((_DWORD *)v4 + 3) = 1;
    *v4 = &std::_Ref_count_obj2<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties>::`vftable';
    v5 = (WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties *)(v4 + 2);
    memset_0(v4 + 2, 0, 0x48u);
    WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::MidiEndpointCustomProperties((WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties *)(v4 + 2));
    *(_QWORD *)&v81 = v4 + 2;
    *((_QWORD *)&v81 + 1) = v4;
    v71 = 0;
    v62 = L"name";
    NamedString = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
                    a2,
                    &lpMem,
                    &v59,
                    &v71,
                    &v60,
                    0x400000001LL);
    winrt::hstring::operator=(v4 + 2, NamedString);
    v7 = lpMem;
    if ( lpMem )
    {
      v8 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v8 )
      {
        if ( v8 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v7);
      }
    }
    v71 = 0;
    v60 = 0xB00000001LL;
    v62 = L"description";
    v59 = &v60;
    v10 = ((__int64 (__fastcall *)(__int64, LPVOID *, __int64 **, int **))winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString)(
            a2,
            &lpMem,
            &v59,
            &v71);
    winrt::hstring::operator=(v4 + 3, v10);
    v11 = lpMem;
    if ( lpMem )
    {
      v12 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v12 )
      {
        if ( v12 < 0 )
          abort();
      }
      else
      {
        v13 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v13, 0, v11);
      }
    }
    v71 = 0;
    v60 = 0x500000001LL;
    v62 = L"image";
    v59 = &v60;
    v14 = ((__int64 (__fastcall *)(__int64, LPVOID *, __int64 **, int **))winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString)(
            a2,
            &lpMem,
            &v59,
            &v71);
    winrt::hstring::operator=(v4 + 4, v14);
    v15 = lpMem;
    if ( lpMem )
    {
      v16 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v16 )
      {
        if ( v16 < 0 )
          abort();
      }
      else
      {
        v17 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v17, 0, v15);
      }
    }
    v60 = 0x1A00000001LL;
    v62 = L"requiresNoteOffTranslation";
    v59 = &v60;
    *((_BYTE *)v4 + 40) = ((__int64 (__fastcall *)(__int64, __int64 **))winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedBoolean)(
                            a2,
                            &v59);
    v60 = 0x2000000001LL;
    v62 = L"supportsMidiPolyphonicExpression";
    v59 = &v60;
    winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedBoolean(
      a2,
      &v59);
    *((_BYTE *)v4 + 41) = v18;
    v60 = 0x2C00000001LL;
    v62 = L"recommendedControlChangeIntervalMilliseconds";
    v59 = &v60;
    NamedNumber = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedNumber(
                    a2,
                    &v59);
    if ( NamedNumber <= 0.0 || NamedNumber > 65535.0 )
      LOWORD(v20) = 0;
    else
      v20 = (int)NamedNumber;
    *((_WORD *)v4 + 21) = v20;
    v60 = 0xA00000001LL;
    v62 = L"midi1Ports";
    v59 = &v60;
    if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                            a2,
                            &v59) )
    {
      v60 = 0xA00000001LL;
      v62 = L"midi1Ports";
      v59 = &v60;
      winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(
        a2,
        &v67,
        &v59);
      v83[0] = 1;
      v83[1] = 7;
      v84 = L"default";
      v82 = v83;
      v86[0] = 1;
      v86[1] = 14;
      v87 = L"namingApproach";
      v85 = v86;
      winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
        &v67,
        &v69,
        &v85,
        &v82,
        v59,
        v60);
      v22 = v69;
      if ( v69 )
      {
        if ( *(_DWORD *)(v69 + 4) == 7 )
        {
          if ( !wmemcmp(*(const wchar_t **)(v69 + 16), L"default", 7u) )
            goto LABEL_35;
          v22 = v69;
        }
        if ( v22 )
        {
          if ( *(_DWORD *)(v22 + 4) == 17 )
          {
            if ( !wmemcmp(*(const wchar_t **)(v22 + 16), L"classicCompatible", 0x11u) )
            {
              *((_DWORD *)v4 + 11) = 1;
LABEL_36:
              v23 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)7, v21);
              v25 = v23;
              if ( v23 == (struct winrt::impl::shared_hstring_header *)-28LL )
              {
                *(_DWORD *)_o__errno() = 22;
                invalid_parameter_noinfo();
              }
              else
              {
                *(_QWORD *)((char *)v23 + 28) = *(_QWORD *)L"sources";
                *((_DWORD *)v23 + 9) = *(_DWORD *)L"ces";
                *((_WORD *)v23 + 20) = aSources[6];
              }
              v77[0] = v25;
              v26 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0xC, v24);
              v27 = v26;
              if ( v26 == (struct winrt::impl::shared_hstring_header *)-28LL )
              {
                *(_DWORD *)_o__errno() = 22;
                invalid_parameter_noinfo();
              }
              else
              {
                *(_OWORD *)((char *)v26 + 28) = *(_OWORD *)L"destinations";
                *(_QWORD *)((char *)v26 + 44) = *(_QWORD *)L"ions";
              }
              v77[1] = v27;
              for ( i = (int **)v77; ; ++i )
              {
                if ( i == (int **)&v78 )
                {
                  `eh vector destructor iterator'(v77, 8u, 2u, (void (*)(void *))winrt::hstring::~hstring);
                  winrt::hstring::~hstring((winrt::hstring *)&v69);
                  if ( v67 )
                    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v67);
                  v3 = a1;
                  v4 = v76;
                  goto LABEL_101;
                }
                v71 = *i;
                if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                         &v67,
                                         &v71) )
                  continue;
                lpMem = 0;
                LODWORD(v59) = 224;
                v60 = (__int64)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
                v61 = 0;
                v29 = (*(__int64 (__fastcall **)(__int64, int *, LPVOID *))(*(_QWORD *)v67 + 72LL))(v67, *i, &lpMem);
                if ( v29 < 0 )
                  winrt::throw_hresult((unsigned int)v29, &v59);
                v68 = lpMem;
                v79 = &v68;
                v30 = 0;
                v80 = 0;
                v31 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v68);
                LODWORD(lpMem) = v31;
                while ( v30 != v31 )
                {
                  winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(&v79, &v63);
                  winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObject(
                    &v63,
                    &v90);
                  v70 = 0.0;
                  if ( (unsigned __int8)winrt::Windows::Foundation::operator==(&v90, &v70) )
                    goto LABEL_58;
                  v60 = 0xA00000001LL;
                  v62 = L"groupIndex";
                  v59 = &v60;
                  if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                           &v90,
                                           &v59) )
                    goto LABEL_58;
                  v60 = 0x400000001LL;
                  v62 = L"name";
                  v59 = &v60;
                  if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                                           &v90,
                                           &v59) )
                    goto LABEL_58;
                  v72 = 1;
                  v73 = 10;
                  v74 = L"groupIndex";
                  v71 = &v72;
                  v70 = 0.0;
                  LODWORD(v59) = 260;
                  v60 = (__int64)"onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\Windows.Data.Json.h";
                  v61 = 0;
                  v32 = (*(__int64 (__fastcall **)(__int64, int *, double *))(*(_QWORD *)v90 + 88LL))(v90, &v72, &v70);
                  if ( v32 < 0 )
                    winrt::throw_hresult((unsigned int)v32, &v59);
                  v72 = 1;
                  v73 = 4;
                  v74 = L"name";
                  v71 = &v72;
                  v33 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
                          &v90,
                          &v75,
                          &v71);
                  WindowsMidiServicesInternal::TrimmedHStringCopy(&v66, v33);
                  v35 = v75;
                  if ( v75 )
                  {
                    v36 = _InterlockedDecrement((volatile signed __int32 *)v75 + 6);
                    if ( v36 )
                    {
                      if ( v36 < 0 )
                        abort();
                    }
                    else
                    {
                      v37 = WINRT_IMPL_GetProcessHeap();
                      WINRT_IMPL_HeapFree(v37, 0, v35);
                    }
                    v75 = 0;
                  }
                  v38 = (int)v70;
                  if ( (unsigned int)(int)v70 <= 0xF )
                  {
                    if ( !v66 )
                      goto LABEL_58;
                    v64 = 0;
                    v65 = 0;
                    v39 = winrt::impl::duplicate_hstring(v66, v34);
                    v40 = v65;
                    if ( v65 )
                    {
                      v41 = _InterlockedDecrement((volatile signed __int32 *)v65 + 6);
                      if ( v41 )
                      {
                        if ( v41 < 0 )
                          goto LABEL_86;
                      }
                      else
                      {
                        v42 = WINRT_IMPL_GetProcessHeap();
                        WINRT_IMPL_HeapFree(v42, 0, v40);
                      }
                    }
                    v65 = v39;
                    LOBYTE(v64) = v38;
                    v43 = *i;
                    if ( *i && v43[1] == 7 && !wmemcmp(*((const wchar_t **)v43 + 2), L"sources", 7u) )
                    {
                      v44 = std::map<unsigned char,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>::operator[](
                              (char *)v5 + 32,
                              &v64);
                      *(_BYTE *)v44 = v64;
                      v46 = winrt::impl::duplicate_hstring(v65, v45);
                      goto LABEL_73;
                    }
                    v56 = *i;
                    if ( *i && v56[1] == 12 && !wmemcmp(*((const wchar_t **)v56 + 2), L"destinations", 0xCu) )
                    {
                      v44 = std::map<unsigned char,WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomMidi1PortProperties>::operator[](
                              (char *)v5 + 48,
                              &v64);
                      *(_BYTE *)v44 = v64;
                      v46 = winrt::impl::duplicate_hstring(v65, v57);
LABEL_73:
                      v47 = *(volatile signed __int32 **)(v44 + 8);
                      if ( v47 )
                      {
                        v48 = _InterlockedDecrement(v47 + 6);
                        if ( v48 )
                        {
                          if ( v48 < 0 )
LABEL_86:
                            abort();
                        }
                        else
                        {
                          v49 = WINRT_IMPL_GetProcessHeap();
                          WINRT_IMPL_HeapFree(v49, 0, (LPVOID)v47);
                        }
                      }
                      *(_QWORD *)(v44 + 8) = v46;
                    }
                    v50 = v65;
                    if ( v65 )
                    {
                      v51 = _InterlockedDecrement((volatile signed __int32 *)v65 + 6);
                      if ( v51 )
                      {
                        if ( v51 < 0 )
                          abort();
                      }
                      else
                      {
                        v52 = WINRT_IMPL_GetProcessHeap();
                        WINRT_IMPL_HeapFree(v52, 0, v50);
                      }
                      v65 = 0;
                    }
                  }
                  v53 = v66;
                  if ( v66 )
                  {
                    v54 = _InterlockedDecrement((volatile signed __int32 *)v66 + 6);
                    if ( v54 )
                    {
                      if ( v54 < 0 )
                        abort();
                    }
                    else
                    {
                      v55 = WINRT_IMPL_GetProcessHeap();
                      WINRT_IMPL_HeapFree(v55, 0, v53);
                    }
                    v66 = 0;
                  }
LABEL_58:
                  if ( v90 )
                    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v90);
                  if ( v63 )
                    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v63);
                  v80 = ++v30;
                  v31 = (int)lpMem;
                }
                if ( v68 )
                  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v68);
              }
            }
            v22 = v69;
          }
          if ( v22 && *(_DWORD *)(v22 + 4) == 8 && !wmemcmp(*(const wchar_t **)(v22 + 16), L"newStyle", 8u) )
          {
            *((_DWORD *)v4 + 11) = 2;
            goto LABEL_36;
          }
        }
      }
LABEL_35:
      *((_DWORD *)v4 + 11) = 0;
      goto LABEL_36;
    }
LABEL_101:
    WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::Normalize(v5);
    *v3 = v5;
    v3[1] = (WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties *)v4;
    v81 = 0;
    std::shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>::~shared_ptr<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>(&v81);
    result = v3;
  }
  catch ( ... )
  {
    OutputDebugStringW(L"Exception parsing MIDI Endpoint Custom Properties JSON.");
    result = a1;
    *a1 = 0;
    a1[1] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18004b224  mov     rax, rsp
0x18004b227  mov     [rax+8], rcx
0x18004b22b  push    rbx
0x18004b22c  push    rsi
0x18004b22d  push    rdi
0x18004b22e  push    r12
0x18004b230  push    r13
0x18004b232  push    r14
0x18004b234  push    r15
0x18004b236  sub     rsp, 140h
0x18004b23d  movaps  xmmword ptr [rax-48h], xmm6
0x18004b241  mov     rdi, rdx
0x18004b244  mov     r12, rcx
0x18004b247  xor     ebx, ebx
0x18004b249  lea     ecx, [rbx+58h]; Size
0x18004b24c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004b251  mov     r15, rax
0x18004b254  mov     [rsp+178h+var_D0], rax
0x18004b25c  mov     [rsp+178h+lpMem], rax
0x18004b264  lea     r13d, [rbx+1]
0x18004b268  mov     [rax+8], r13d
0x18004b26c  mov     [rax+0Ch], r13d
0x18004b270  lea     rax, ??_7?$_Ref_count_obj2@VMidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@6B@; const std::_Ref_count_obj2<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties>::`vftable'
0x18004b277  mov     [r15], rax
0x18004b27a  lea     r14, [r15+10h]
0x18004b27e  xor     edx, edx; Val
0x18004b280  lea     r8d, [rbx+48h]; Size
0x18004b284  mov     rcx, r14; void *
0x18004b287  call    memset_0
0x18004b28c  mov     rcx, r14; this
0x18004b28f  call    ??0MidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@QEAA@XZ; WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::MidiEndpointCustomProperties(void)
0x18004b294  nop
0x18004b295  mov     qword ptr [rsp+178h+var_A0], r14
0x18004b29d  mov     qword ptr [rsp+178h+var_A0+8], r15
0x18004b2a5  mov     [rsp+178h+var_F8], rbx
0x18004b2ad  mov     dword ptr [rsp+178h+var_150], r13d
0x18004b2b2  mov     dword ptr [rsp+178h+var_150+4], 4
0x18004b2ba  lea     rax, aName_0; "name"
0x18004b2c1  mov     [rsp+178h+var_140], rax
0x18004b2c6  lea     rax, [rsp+178h+var_150]
0x18004b2cb  mov     [rsp+178h+var_158], rax
0x18004b2d0  lea     r9, [rsp+178h+var_F8]
0x18004b2d8  lea     r8, [rsp+178h+var_158]
0x18004b2dd  lea     rdx, [rsp+178h+lpMem]
0x18004b2e5  mov     rcx, rdi
0x18004b2e8  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18004b2ed  mov     rdx, rax
0x18004b2f0  mov     rcx, r14
0x18004b2f3  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18004b2f8  mov     rsi, [rsp+178h+lpMem]
0x18004b300  test    rsi, rsi
0x18004b303  jz      short loc_18004B329
0x18004b305  or      eax, 0FFFFFFFFh
0x18004b308  lock xadd [rsi+18h], eax
0x18004b30d  sub     eax, r13d
0x18004b310  jnz     loc_18004B4EC
0x18004b316  nop
0x18004b317  call    WINRT_IMPL_GetProcessHeap
0x18004b31c  mov     rcx, rax; hHeap
0x18004b31f  mov     r8, rsi; lpMem
0x18004b322  xor     edx, edx; dwFlags
0x18004b324  call    WINRT_IMPL_HeapFree
0x18004b329  mov     [rsp+178h+var_F8], rbx
0x18004b331  mov     dword ptr [rsp+178h+var_150], r13d
0x18004b336  mov     dword ptr [rsp+178h+var_150+4], 0Bh
0x18004b33e  lea     rax, aDescription; "description"
0x18004b345  mov     [rsp+178h+var_140], rax
0x18004b34a  lea     rax, [rsp+178h+var_150]
0x18004b34f  mov     [rsp+178h+var_158], rax
0x18004b354  lea     r9, [rsp+178h+var_F8]
0x18004b35c  lea     r8, [rsp+178h+var_158]
0x18004b361  lea     rdx, [rsp+178h+lpMem]
0x18004b369  mov     rcx, rdi
0x18004b36c  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18004b371  lea     rcx, [r14+8]
0x18004b375  mov     rdx, rax
0x18004b378  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18004b37d  mov     rsi, [rsp+178h+lpMem]
0x18004b385  test    rsi, rsi
0x18004b388  jz      short loc_18004B3AE
0x18004b38a  or      eax, 0FFFFFFFFh
0x18004b38d  lock xadd [rsi+18h], eax
0x18004b392  sub     eax, 1
0x18004b395  jnz     loc_18004B4FB
0x18004b39b  nop
0x18004b39c  call    WINRT_IMPL_GetProcessHeap
0x18004b3a1  mov     rcx, rax; hHeap
0x18004b3a4  mov     r8, rsi; lpMem
0x18004b3a7  xor     edx, edx; dwFlags
0x18004b3a9  call    WINRT_IMPL_HeapFree
0x18004b3ae  mov     [rsp+178h+var_F8], rbx
0x18004b3b6  mov     dword ptr [rsp+178h+var_150], r13d
0x18004b3bb  mov     dword ptr [rsp+178h+var_150+4], 5
0x18004b3c3  lea     rax, aImage; "image"
0x18004b3ca  mov     [rsp+178h+var_140], rax
0x18004b3cf  lea     rax, [rsp+178h+var_150]
0x18004b3d4  mov     [rsp+178h+var_158], rax
0x18004b3d9  lea     r9, [rsp+178h+var_F8]
0x18004b3e1  lea     r8, [rsp+178h+var_158]
0x18004b3e6  lea     rdx, [rsp+178h+lpMem]
0x18004b3ee  mov     rcx, rdi
0x18004b3f1  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18004b3f6  lea     rcx, [r14+10h]
0x18004b3fa  mov     rdx, rax
0x18004b3fd  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18004b402  mov     rsi, [rsp+178h+lpMem]
0x18004b40a  test    rsi, rsi
0x18004b40d  jz      short loc_18004B433
0x18004b40f  or      eax, 0FFFFFFFFh
0x18004b412  lock xadd [rsi+18h], eax
0x18004b417  sub     eax, 1
0x18004b41a  jnz     loc_18004B50A
0x18004b420  nop
0x18004b421  call    WINRT_IMPL_GetProcessHeap
0x18004b426  mov     rcx, rax; hHeap
0x18004b429  mov     r8, rsi; lpMem
0x18004b42c  xor     edx, edx; dwFlags
0x18004b42e  call    WINRT_IMPL_HeapFree
0x18004b433  mov     dword ptr [rsp+178h+var_150], r13d
0x18004b438  mov     esi, 1Ah
0x18004b43d  mov     dword ptr [rsp+178h+var_150+4], esi
0x18004b441  lea     rax, aRequiresnoteof; "requiresNoteOffTranslation"
0x18004b448  mov     [rsp+178h+var_140], rax
0x18004b44d  lea     rax, [rsp+178h+var_150]
0x18004b452  mov     [rsp+178h+var_158], rax
0x18004b457  lea     rdx, [rsp+178h+var_158]
0x18004b45c  mov     rcx, rdi
0x18004b45f  call    ?GetNamedBoolean@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@_N@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedBoolean(winrt::param::hstring const &,bool)
0x18004b464  mov     [r14+18h], al
0x18004b468  mov     dword ptr [rsp+178h+var_150], r13d
0x18004b46d  mov     dword ptr [rsp+178h+var_150+4], 20h ; ' '
0x18004b475  lea     rax, aSupportsmidipo; "supportsMidiPolyphonicExpression"
0x18004b47c  mov     [rsp+178h+var_140], rax
0x18004b481  lea     rax, [rsp+178h+var_150]
0x18004b486  mov     [rsp+178h+var_158], rax
0x18004b48b  lea     rdx, [rsp+178h+var_158]
0x18004b490  mov     rcx, rdi
0x18004b493  call    ?GetNamedBoolean@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@_N@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedBoolean(winrt::param::hstring const &,bool)
0x18004b498  mov     [r14+19h], al
0x18004b49c  mov     dword ptr [rsp+178h+var_150], r13d
0x18004b4a1  mov     dword ptr [rsp+178h+var_150+4], 2Ch ; ','
0x18004b4a9  lea     rax, aRecommendedcon; "recommendedControlChangeIntervalMillise"...
0x18004b4b0  mov     [rsp+178h+var_140], rax
0x18004b4b5  lea     rax, [rsp+178h+var_150]
0x18004b4ba  mov     [rsp+178h+var_158], rax
0x18004b4bf  xorps   xmm6, xmm6
0x18004b4c2  xorps   xmm2, xmm2
0x18004b4c5  lea     rdx, [rsp+178h+var_158]
0x18004b4ca  mov     rcx, rdi
0x18004b4cd  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@N@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedNumber(winrt::param::hstring const &,double)
0x18004b4d2  comisd  xmm0, xmm6
0x18004b4d6  jbe     short loc_18004B519
0x18004b4d8  movsd   xmm1, cs:__real@40efffe000000000
0x18004b4e0  comisd  xmm1, xmm0
0x18004b4e4  jb      short loc_18004B519
0x18004b4e6  cvttsd2si eax, xmm0
0x18004b4ea  jmp     short loc_18004B51C
0x18004b4ec  test    eax, eax
0x18004b4ee  jns     loc_18004B329
0x18004b4f4  call    cs:__imp_abort
0x18004b4fb  test    eax, eax
0x18004b4fd  jns     loc_18004B3AE
0x18004b503  call    cs:__imp_abort
0x18004b50a  test    eax, eax
0x18004b50c  jns     loc_18004B433
0x18004b512  call    cs:__imp_abort
0x18004b519  movzx   eax, bx
0x18004b51c  mov     rcx, r14
0x18004b51f  mov     [rsi+rcx], ax
0x18004b523  mov     dword ptr [rsp+178h+var_150], r13d
0x18004b528  mov     dword ptr [rsp+178h+var_150+4], 0Ah
0x18004b530  lea     rsi, aMidi1ports; "midi1Ports"
0x18004b537  mov     [rsp+178h+var_140], rsi
0x18004b53c  lea     rax, [rsp+178h+var_150]
0x18004b541  mov     [rsp+178h+var_158], rax
0x18004b546  lea     rdx, [rsp+178h+var_158]
0x18004b54b  mov     rcx, rdi
0x18004b54e  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x18004b553  test    al, al
0x18004b555  jz      loc_18004BC64
0x18004b55b  mov     dword ptr [rsp+178h+var_150], r13d
0x18004b560  mov     dword ptr [rsp+178h+var_150+4], 0Ah
0x18004b568  mov     [rsp+178h+var_140], rsi
0x18004b56d  lea     rax, [rsp+178h+var_150]
0x18004b572  mov     [rsp+178h+var_158], rax
0x18004b577  lea     r8, [rsp+178h+var_158]
0x18004b57c  lea     rdx, [rsp+178h+var_118]
0x18004b581  mov     rcx, rdi
0x18004b584  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(winrt::param::hstring const &)
0x18004b589  nop
0x18004b58a  mov     [rsp+178h+var_88], r13d
0x18004b592  mov     [rsp+178h+var_84], 7
0x18004b59d  lea     rdi, aDefault; "default"
0x18004b5a4  mov     [rsp+178h+var_78], rdi
0x18004b5ac  lea     rax, [rsp+178h+var_88]
0x18004b5b4  mov     [rsp+178h+var_90], rax
0x18004b5bc  mov     [rsp+178h+var_68], r13d
0x18004b5c4  mov     [rsp+178h+var_64], 0Eh
0x18004b5cf  lea     rax, aNamingapproach; "namingApproach"
0x18004b5d6  mov     [rsp+178h+var_58], rax
0x18004b5de  lea     rax, [rsp+178h+var_68]
0x18004b5e6  mov     [rsp+178h+var_70], rax
0x18004b5ee  lea     r9, [rsp+178h+var_90]
0x18004b5f6  lea     r8, [rsp+178h+var_70]
0x18004b5fe  lea     rdx, [rsp+178h+var_108]
0x18004b603  lea     rcx, [rsp+178h+var_118]
0x18004b608  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18004b60d  nop
0x18004b60e  mov     rcx, [rsp+178h+var_108]
0x18004b613  test    rcx, rcx
0x18004b616  jz      short loc_18004B692
0x18004b618  mov     r8d, [rcx+4]; N
0x18004b61c  cmp     r8, 7
0x18004b620  jnz     short loc_18004B637
0x18004b622  mov     rdx, rdi; S2
0x18004b625  mov     rcx, [rcx+10h]; S1
0x18004b629  call    wmemcmp
0x18004b62e  test    eax, eax
0x18004b630  jz      short loc_18004B692
0x18004b632  mov     rcx, [rsp+178h+var_108]
0x18004b637  test    rcx, rcx
0x18004b63a  jz      short loc_18004B692
0x18004b63c  mov     r8d, [rcx+4]; N
0x18004b640  cmp     r8, 11h
0x18004b644  jnz     short loc_18004B665
0x18004b646  lea     rdx, aClassiccompati; "classicCompatible"
0x18004b64d  mov     rcx, [rcx+10h]; S1
0x18004b651  call    wmemcmp
0x18004b656  test    eax, eax
0x18004b658  jnz     short loc_18004B660
0x18004b65a  mov     [r14+1Ch], r13d
0x18004b65e  jmp     short loc_18004B696
0x18004b660  mov     rcx, [rsp+178h+var_108]
0x18004b665  test    rcx, rcx
0x18004b668  jz      short loc_18004B692
0x18004b66a  mov     r8d, [rcx+4]; N
0x18004b66e  cmp     r8, 8
0x18004b672  jnz     short loc_18004B692
0x18004b674  lea     rdx, aNewstyle; "newStyle"
0x18004b67b  mov     rcx, [rcx+10h]; S1
0x18004b67f  call    wmemcmp
0x18004b684  test    eax, eax
0x18004b686  jnz     short loc_18004B692
0x18004b688  mov     dword ptr [r14+1Ch], 2
0x18004b690  jmp     short loc_18004B696
0x18004b692  mov     [r14+1Ch], ebx
0x18004b696  mov     ecx, 7; this
0x18004b69b  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18004b6a0  mov     rdi, rax
0x18004b6a3  lea     rcx, [rax+1Ch]
0x18004b6a7  test    rcx, rcx
0x18004b6aa  jnz     short loc_18004B6BF
0x18004b6ac  call    cs:__imp__o__errno
0x18004b6b2  mov     dword ptr [rax], 16h
0x18004b6b8  call    _invalid_parameter_noinfo
0x18004b6bd  jmp     short loc_18004B6DF
0x18004b6bf  movsd   xmm0, qword ptr cs:aSources; "sources"
0x18004b6c7  movsd   qword ptr [rcx], xmm0
0x18004b6cb  mov     eax, dword ptr cs:aSources+8; "ces"
0x18004b6d1  mov     [rcx+8], eax
0x18004b6d4  movzx   eax, word ptr cs:aSources+0Ch; "s"
0x18004b6db  mov     [rcx+0Ch], ax
0x18004b6df  mov     [rsp+178h+var_C8], rdi
0x18004b6e7  mov     ecx, 0Ch; this
0x18004b6ec  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18004b6f1  mov     rdi, rax
0x18004b6f4  lea     rcx, [rax+1Ch]
0x18004b6f8  test    rcx, rcx
0x18004b6fb  jnz     short loc_18004B710
0x18004b6fd  call    cs:__imp__o__errno
0x18004b703  mov     dword ptr [rax], 16h
0x18004b709  call    _invalid_parameter_noinfo
0x18004b70e  jmp     short loc_18004B727
0x18004b710  movups  xmm0, xmmword ptr cs:aDestinations; "destinations"
0x18004b717  movups  xmmword ptr [rcx], xmm0
0x18004b71a  movsd   xmm1, qword ptr cs:aDestinations+10h; "ions"
0x18004b722  movsd   qword ptr [rcx+10h], xmm1
0x18004b727  mov     [rsp+178h+var_C0], rdi
0x18004b72f  lea     r12, [rsp+178h+var_C8]
0x18004b737  lea     rsi, aOnecoreuapInte_3; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18004b73e  lea     rdi, aGroupindex; "groupIndex"
0x18004b745  lea     rax, [rsp+178h+var_B8]
0x18004b74d  cmp     r12, rax
0x18004b750  jz      loc_18004BC1A
0x18004b756  mov     rax, [r12]
0x18004b75a  mov     [rsp+178h+var_F8], rax
0x18004b762  lea     rdx, [rsp+178h+var_F8]
0x18004b76a  lea     rcx, [rsp+178h+var_118]
0x18004b76f  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x18004b774  test    al, al
0x18004b776  jz      loc_18004BC11
0x18004b77c  mov     [rsp+178h+lpMem], rbx
0x18004b784  mov     rcx, [rsp+178h+var_118]
0x18004b789  mov     dword ptr [rsp+178h+var_158], 0E0h
0x18004b791  mov     [rsp+178h+var_150], rsi
0x18004b796  mov     [rsp+178h+var_148], rbx
0x18004b79b  mov     rax, [rcx]
0x18004b79e  lea     r8, [rsp+178h+lpMem]
0x18004b7a6  mov     rdx, [r12]
0x18004b7aa  mov     rax, [rax+48h]
  ... truncated ...
```
