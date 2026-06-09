# WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::FromJson(winrt::Windows::Data::Json::JsonObject const &)

- ea: `0x18002af94`
- end: `0x18002ba4a`
- name: `?FromJson@MidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@SA?AV?$shared_ptr@VMidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@AEBUJsonObject@Json@Data@Windows@winrt@@@Z`
- size: `2742`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800230a0`

## callees

- `0x180004460`
- `0x1800044a4`
- `0x1800051e6`
- `0x18000526c`
- `0x1800052fc`
- `0x180005374`
- `0x18000c52c`
- `0x18000d1c0`
- `0x180011150`
- `0x180011240`
- `0x1800112b0`
- `0x180014864`
- `0x180014fc4`
- `0x180015348`
- `0x1800156e4`
- `0x180017ce8`
- `0x180021e4c`
- `0x1800222c0`
- `0x180022408`
- `0x180022478`
- `0x180022550`
- `0x1800225bc`
- `0x180023930`
- `0x18002ae94`
- `0x18002af94`
- `0x18002ba50`
- `0x18002bb20`
- `0x18002bc00`
- `0x18002beb0`
- `0x180041010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b264`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b273`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b282`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b79b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b8ef`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b95a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b969`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b264`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b273`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b282`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b79b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b8ef`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b95a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002b969`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002b41c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002b46d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002b41c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002b46d`

## string_xrefs

- `0x18002b4a7`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x18002b78b`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\Windows.Data.Json.h`
- `0x18002b219`: `recommendedControlChangeIntervalMilliseconds`
- `0x18002b3b6`: `classicCompatible`

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
0x18002af94  mov     rax, rsp
0x18002af97  mov     [rax+8], rcx
0x18002af9b  push    rbx
0x18002af9c  push    rsi
0x18002af9d  push    rdi
0x18002af9e  push    r12
0x18002afa0  push    r13
0x18002afa2  push    r14
0x18002afa4  push    r15
0x18002afa6  sub     rsp, 140h
0x18002afad  movaps  xmmword ptr [rax-48h], xmm6
0x18002afb1  mov     rdi, rdx
0x18002afb4  mov     r12, rcx
0x18002afb7  xor     ebx, ebx
0x18002afb9  lea     ecx, [rbx+58h]; Size
0x18002afbc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002afc1  mov     r15, rax
0x18002afc4  mov     [rsp+178h+var_D0], rax
0x18002afcc  mov     [rsp+178h+lpMem], rax
0x18002afd4  lea     r13d, [rbx+1]
0x18002afd8  mov     [rax+8], r13d
0x18002afdc  mov     [rax+0Ch], r13d
0x18002afe0  lea     rax, ??_7?$_Ref_count_obj2@VMidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@@std@@6B@; const std::_Ref_count_obj2<WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties>::`vftable'
0x18002afe7  mov     [r15], rax
0x18002afea  lea     r14, [r15+10h]
0x18002afee  xor     edx, edx; Val
0x18002aff0  lea     r8d, [rbx+48h]; Size
0x18002aff4  mov     rcx, r14; void *
0x18002aff7  call    memset_0
0x18002affc  mov     rcx, r14; this
0x18002afff  call    ??0MidiEndpointCustomProperties@WindowsMidiServicesPluginConfigurationLib@@QEAA@XZ; WindowsMidiServicesPluginConfigurationLib::MidiEndpointCustomProperties::MidiEndpointCustomProperties(void)
0x18002b004  nop
0x18002b005  mov     qword ptr [rsp+178h+var_A0], r14
0x18002b00d  mov     qword ptr [rsp+178h+var_A0+8], r15
0x18002b015  mov     [rsp+178h+var_F8], rbx
0x18002b01d  mov     dword ptr [rsp+178h+var_150], r13d
0x18002b022  mov     dword ptr [rsp+178h+var_150+4], 4
0x18002b02a  lea     rax, aName; "name"
0x18002b031  mov     [rsp+178h+var_140], rax
0x18002b036  lea     rax, [rsp+178h+var_150]
0x18002b03b  mov     [rsp+178h+var_158], rax
0x18002b040  lea     r9, [rsp+178h+var_F8]
0x18002b048  lea     r8, [rsp+178h+var_158]
0x18002b04d  lea     rdx, [rsp+178h+lpMem]
0x18002b055  mov     rcx, rdi
0x18002b058  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18002b05d  mov     rdx, rax
0x18002b060  mov     rcx, r14
0x18002b063  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18002b068  mov     rsi, [rsp+178h+lpMem]
0x18002b070  test    rsi, rsi
0x18002b073  jz      short loc_18002B099
0x18002b075  or      eax, 0FFFFFFFFh
0x18002b078  lock xadd [rsi+18h], eax
0x18002b07d  sub     eax, r13d
0x18002b080  jnz     loc_18002B25C
0x18002b086  nop
0x18002b087  call    WINRT_IMPL_GetProcessHeap
0x18002b08c  mov     rcx, rax; hHeap
0x18002b08f  mov     r8, rsi; lpMem
0x18002b092  xor     edx, edx; dwFlags
0x18002b094  call    WINRT_IMPL_HeapFree
0x18002b099  mov     [rsp+178h+var_F8], rbx
0x18002b0a1  mov     dword ptr [rsp+178h+var_150], r13d
0x18002b0a6  mov     dword ptr [rsp+178h+var_150+4], 0Bh
0x18002b0ae  lea     rax, aDescription; "description"
0x18002b0b5  mov     [rsp+178h+var_140], rax
0x18002b0ba  lea     rax, [rsp+178h+var_150]
0x18002b0bf  mov     [rsp+178h+var_158], rax
0x18002b0c4  lea     r9, [rsp+178h+var_F8]
0x18002b0cc  lea     r8, [rsp+178h+var_158]
0x18002b0d1  lea     rdx, [rsp+178h+lpMem]
0x18002b0d9  mov     rcx, rdi
0x18002b0dc  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18002b0e1  lea     rcx, [r14+8]
0x18002b0e5  mov     rdx, rax
0x18002b0e8  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18002b0ed  mov     rsi, [rsp+178h+lpMem]
0x18002b0f5  test    rsi, rsi
0x18002b0f8  jz      short loc_18002B11E
0x18002b0fa  or      eax, 0FFFFFFFFh
0x18002b0fd  lock xadd [rsi+18h], eax
0x18002b102  sub     eax, 1
0x18002b105  jnz     loc_18002B26B
0x18002b10b  nop
0x18002b10c  call    WINRT_IMPL_GetProcessHeap
0x18002b111  mov     rcx, rax; hHeap
0x18002b114  mov     r8, rsi; lpMem
0x18002b117  xor     edx, edx; dwFlags
0x18002b119  call    WINRT_IMPL_HeapFree
0x18002b11e  mov     [rsp+178h+var_F8], rbx
0x18002b126  mov     dword ptr [rsp+178h+var_150], r13d
0x18002b12b  mov     dword ptr [rsp+178h+var_150+4], 5
0x18002b133  lea     rax, aImage; "image"
0x18002b13a  mov     [rsp+178h+var_140], rax
0x18002b13f  lea     rax, [rsp+178h+var_150]
0x18002b144  mov     [rsp+178h+var_158], rax
0x18002b149  lea     r9, [rsp+178h+var_F8]
0x18002b151  lea     r8, [rsp+178h+var_158]
0x18002b156  lea     rdx, [rsp+178h+lpMem]
0x18002b15e  mov     rcx, rdi
0x18002b161  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18002b166  lea     rcx, [r14+10h]
0x18002b16a  mov     rdx, rax
0x18002b16d  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18002b172  mov     rsi, [rsp+178h+lpMem]
0x18002b17a  test    rsi, rsi
0x18002b17d  jz      short loc_18002B1A3
0x18002b17f  or      eax, 0FFFFFFFFh
0x18002b182  lock xadd [rsi+18h], eax
0x18002b187  sub     eax, 1
0x18002b18a  jnz     loc_18002B27A
0x18002b190  nop
0x18002b191  call    WINRT_IMPL_GetProcessHeap
0x18002b196  mov     rcx, rax; hHeap
0x18002b199  mov     r8, rsi; lpMem
0x18002b19c  xor     edx, edx; dwFlags
0x18002b19e  call    WINRT_IMPL_HeapFree
0x18002b1a3  mov     dword ptr [rsp+178h+var_150], r13d
0x18002b1a8  mov     esi, 1Ah
0x18002b1ad  mov     dword ptr [rsp+178h+var_150+4], esi
0x18002b1b1  lea     rax, aRequiresnoteof; "requiresNoteOffTranslation"
0x18002b1b8  mov     [rsp+178h+var_140], rax
0x18002b1bd  lea     rax, [rsp+178h+var_150]
0x18002b1c2  mov     [rsp+178h+var_158], rax
0x18002b1c7  lea     rdx, [rsp+178h+var_158]
0x18002b1cc  mov     rcx, rdi
0x18002b1cf  call    ?GetNamedBoolean@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@_N@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedBoolean(winrt::param::hstring const &,bool)
0x18002b1d4  mov     [r14+18h], al
0x18002b1d8  mov     dword ptr [rsp+178h+var_150], r13d
0x18002b1dd  mov     dword ptr [rsp+178h+var_150+4], 20h ; ' '
0x18002b1e5  lea     rax, aSupportsmidipo; "supportsMidiPolyphonicExpression"
0x18002b1ec  mov     [rsp+178h+var_140], rax
0x18002b1f1  lea     rax, [rsp+178h+var_150]
0x18002b1f6  mov     [rsp+178h+var_158], rax
0x18002b1fb  lea     rdx, [rsp+178h+var_158]
0x18002b200  mov     rcx, rdi
0x18002b203  call    ?GetNamedBoolean@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@_N@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedBoolean(winrt::param::hstring const &,bool)
0x18002b208  mov     [r14+19h], al
0x18002b20c  mov     dword ptr [rsp+178h+var_150], r13d
0x18002b211  mov     dword ptr [rsp+178h+var_150+4], 2Ch ; ','
0x18002b219  lea     rax, aRecommendedcon; "recommendedControlChangeIntervalMillise"...
0x18002b220  mov     [rsp+178h+var_140], rax
0x18002b225  lea     rax, [rsp+178h+var_150]
0x18002b22a  mov     [rsp+178h+var_158], rax
0x18002b22f  xorps   xmm6, xmm6
0x18002b232  xorps   xmm2, xmm2
0x18002b235  lea     rdx, [rsp+178h+var_158]
0x18002b23a  mov     rcx, rdi
0x18002b23d  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@N@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedNumber(winrt::param::hstring const &,double)
0x18002b242  comisd  xmm0, xmm6
0x18002b246  jbe     short loc_18002B289
0x18002b248  movsd   xmm1, cs:__real@40efffe000000000
0x18002b250  comisd  xmm1, xmm0
0x18002b254  jb      short loc_18002B289
0x18002b256  cvttsd2si eax, xmm0
0x18002b25a  jmp     short loc_18002B28C
0x18002b25c  test    eax, eax
0x18002b25e  jns     loc_18002B099
0x18002b264  call    cs:__imp_abort
0x18002b26b  test    eax, eax
0x18002b26d  jns     loc_18002B11E
0x18002b273  call    cs:__imp_abort
0x18002b27a  test    eax, eax
0x18002b27c  jns     loc_18002B1A3
0x18002b282  call    cs:__imp_abort
0x18002b289  movzx   eax, bx
0x18002b28c  mov     rcx, r14
0x18002b28f  mov     [rsi+rcx], ax
0x18002b293  mov     dword ptr [rsp+178h+var_150], r13d
0x18002b298  mov     dword ptr [rsp+178h+var_150+4], 0Ah
0x18002b2a0  lea     rsi, aMidi1ports; "midi1Ports"
0x18002b2a7  mov     [rsp+178h+var_140], rsi
0x18002b2ac  lea     rax, [rsp+178h+var_150]
0x18002b2b1  mov     [rsp+178h+var_158], rax
0x18002b2b6  lea     rdx, [rsp+178h+var_158]
0x18002b2bb  mov     rcx, rdi
0x18002b2be  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x18002b2c3  test    al, al
0x18002b2c5  jz      loc_18002B9D4
0x18002b2cb  mov     dword ptr [rsp+178h+var_150], r13d
0x18002b2d0  mov     dword ptr [rsp+178h+var_150+4], 0Ah
0x18002b2d8  mov     [rsp+178h+var_140], rsi
0x18002b2dd  lea     rax, [rsp+178h+var_150]
0x18002b2e2  mov     [rsp+178h+var_158], rax
0x18002b2e7  lea     r8, [rsp+178h+var_158]
0x18002b2ec  lea     rdx, [rsp+178h+var_118]
0x18002b2f1  mov     rcx, rdi
0x18002b2f4  call    ?GetNamedObject@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedObject(winrt::param::hstring const &)
0x18002b2f9  nop
0x18002b2fa  mov     [rsp+178h+var_88], r13d
0x18002b302  mov     [rsp+178h+var_84], 7
0x18002b30d  lea     rdi, aDefault; "default"
0x18002b314  mov     [rsp+178h+var_78], rdi
0x18002b31c  lea     rax, [rsp+178h+var_88]
0x18002b324  mov     [rsp+178h+var_90], rax
0x18002b32c  mov     [rsp+178h+var_68], r13d
0x18002b334  mov     [rsp+178h+var_64], 0Eh
0x18002b33f  lea     rax, aNamingapproach; "namingApproach"
0x18002b346  mov     [rsp+178h+var_58], rax
0x18002b34e  lea     rax, [rsp+178h+var_68]
0x18002b356  mov     [rsp+178h+var_70], rax
0x18002b35e  lea     r9, [rsp+178h+var_90]
0x18002b366  lea     r8, [rsp+178h+var_70]
0x18002b36e  lea     rdx, [rsp+178h+var_108]
0x18002b373  lea     rcx, [rsp+178h+var_118]
0x18002b378  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18002b37d  nop
0x18002b37e  mov     rcx, [rsp+178h+var_108]
0x18002b383  test    rcx, rcx
0x18002b386  jz      short loc_18002B402
0x18002b388  mov     r8d, [rcx+4]; N
0x18002b38c  cmp     r8, 7
0x18002b390  jnz     short loc_18002B3A7
0x18002b392  mov     rdx, rdi; S2
0x18002b395  mov     rcx, [rcx+10h]; S1
0x18002b399  call    wmemcmp
0x18002b39e  test    eax, eax
0x18002b3a0  jz      short loc_18002B402
0x18002b3a2  mov     rcx, [rsp+178h+var_108]
0x18002b3a7  test    rcx, rcx
0x18002b3aa  jz      short loc_18002B402
0x18002b3ac  mov     r8d, [rcx+4]; N
0x18002b3b0  cmp     r8, 11h
0x18002b3b4  jnz     short loc_18002B3D5
0x18002b3b6  lea     rdx, aClassiccompati; "classicCompatible"
0x18002b3bd  mov     rcx, [rcx+10h]; S1
0x18002b3c1  call    wmemcmp
0x18002b3c6  test    eax, eax
0x18002b3c8  jnz     short loc_18002B3D0
0x18002b3ca  mov     [r14+1Ch], r13d
0x18002b3ce  jmp     short loc_18002B406
0x18002b3d0  mov     rcx, [rsp+178h+var_108]
0x18002b3d5  test    rcx, rcx
0x18002b3d8  jz      short loc_18002B402
0x18002b3da  mov     r8d, [rcx+4]; N
0x18002b3de  cmp     r8, 8
0x18002b3e2  jnz     short loc_18002B402
0x18002b3e4  lea     rdx, aNewstyle; "newStyle"
0x18002b3eb  mov     rcx, [rcx+10h]; S1
0x18002b3ef  call    wmemcmp
0x18002b3f4  test    eax, eax
0x18002b3f6  jnz     short loc_18002B402
0x18002b3f8  mov     dword ptr [r14+1Ch], 2
0x18002b400  jmp     short loc_18002B406
0x18002b402  mov     [r14+1Ch], ebx
0x18002b406  mov     ecx, 7; this
0x18002b40b  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18002b410  mov     rdi, rax
0x18002b413  lea     rcx, [rax+1Ch]
0x18002b417  test    rcx, rcx
0x18002b41a  jnz     short loc_18002B42F
0x18002b41c  call    cs:__imp__o__errno
0x18002b422  mov     dword ptr [rax], 16h
0x18002b428  call    _invalid_parameter_noinfo
0x18002b42d  jmp     short loc_18002B44F
0x18002b42f  movsd   xmm0, qword ptr cs:aSources; "sources"
0x18002b437  movsd   qword ptr [rcx], xmm0
0x18002b43b  mov     eax, dword ptr cs:aSources+8; "ces"
0x18002b441  mov     [rcx+8], eax
0x18002b444  movzx   eax, word ptr cs:aSources+0Ch; "s"
0x18002b44b  mov     [rcx+0Ch], ax
0x18002b44f  mov     [rsp+178h+var_C8], rdi
0x18002b457  mov     ecx, 0Ch; this
0x18002b45c  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18002b461  mov     rdi, rax
0x18002b464  lea     rcx, [rax+1Ch]
0x18002b468  test    rcx, rcx
0x18002b46b  jnz     short loc_18002B480
0x18002b46d  call    cs:__imp__o__errno
0x18002b473  mov     dword ptr [rax], 16h
0x18002b479  call    _invalid_parameter_noinfo
0x18002b47e  jmp     short loc_18002B497
0x18002b480  movups  xmm0, xmmword ptr cs:aDestinations; "destinations"
0x18002b487  movups  xmmword ptr [rcx], xmm0
0x18002b48a  movsd   xmm1, qword ptr cs:aDestinations+10h; "ions"
0x18002b492  movsd   qword ptr [rcx+10h], xmm1
0x18002b497  mov     [rsp+178h+var_C0], rdi
0x18002b49f  lea     r12, [rsp+178h+var_C8]
0x18002b4a7  lea     rsi, aOnecoreuapInte_4; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18002b4ae  lea     rdi, aGroupindex; "groupIndex"
0x18002b4b5  lea     rax, [rsp+178h+var_B8]
0x18002b4bd  cmp     r12, rax
0x18002b4c0  jz      loc_18002B98A
0x18002b4c6  mov     rax, [r12]
0x18002b4ca  mov     [rsp+178h+var_F8], rax
0x18002b4d2  lea     rdx, [rsp+178h+var_F8]
0x18002b4da  lea     rcx, [rsp+178h+var_118]
0x18002b4df  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x18002b4e4  test    al, al
0x18002b4e6  jz      loc_18002B981
0x18002b4ec  mov     [rsp+178h+lpMem], rbx
0x18002b4f4  mov     rcx, [rsp+178h+var_118]
0x18002b4f9  mov     dword ptr [rsp+178h+var_158], 0E0h
0x18002b501  mov     [rsp+178h+var_150], rsi
0x18002b506  mov     [rsp+178h+var_148], rbx
0x18002b50b  mov     rax, [rcx]
0x18002b50e  lea     r8, [rsp+178h+lpMem]
0x18002b516  mov     rdx, [r12]
0x18002b51a  mov     rax, [rax+48h]
  ... truncated ...
```
