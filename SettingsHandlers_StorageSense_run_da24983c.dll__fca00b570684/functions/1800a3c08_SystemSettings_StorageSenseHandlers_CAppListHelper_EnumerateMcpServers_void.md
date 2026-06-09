# SystemSettings::StorageSenseHandlers::CAppListHelper::EnumerateMcpServers(void)

- ea: `0x1800a3c08`
- end: `0x1800a422c`
- name: `?EnumerateMcpServers@CAppListHelper@StorageSenseHandlers@SystemSettings@@IEAAJXZ`
- size: `1572`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppListHelper *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a3204`

## callees

- `0x1800017e8`
- `0x180006e50`
- `0x18000c964`
- `0x18000e6cc`
- `0x18001fe08`
- `0x180022f50`
- `0x180023578`
- `0x180026f10`
- `0x180029804`
- `0x180034dcc`
- `0x1800352b4`
- `0x180037628`
- `0x1800379c8`
- `0x18003c308`
- `0x18009d2ec`
- `0x18009e268`
- `0x1800a0770`
- `0x1800a29cc`
- `0x1800a3c08`
- `0x1800aa608`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3eed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3fdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a411e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a41b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3eed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a3fdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a411e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a41b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a4007`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a40b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a4007`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a40b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppListHelper::EnumerateMcpServers(
        SystemSettings::StorageSenseHandlers::CAppListHelper *this)
{
  int UnfilteredMcpServerDefinitions; // eax
  HSTRING v3; // rbx
  HSTRING v4; // rdi
  int v5; // esi
  struct SystemSettings::StorageSenseHandlers::McpServerDefinition *v7; // rsi
  unsigned __int64 v8; // r14
  struct SystemSettings::StorageSenseHandlers::McpServerDefinition *i; // rdi
  __int64 v10; // rax
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rdi
  int (__fastcall *v14)(__int64, __int64 *); // rbx
  __int64 v15; // rdi
  int (__fastcall *v16)(__int64, __int64 *); // rbx
  __int64 v17; // rdi
  void (__fastcall *v18)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v20; // rax
  const struct _tlgProvider_t *v21; // rbx
  int v22; // r8d
  int v23; // r9d
  int v24; // ebx
  int v25; // [rsp+20h] [rbp-E0h]
  char v26; // [rsp+30h] [rbp-D0h] BYREF
  char v27; // [rsp+31h] [rbp-CFh] BYREF
  _BYTE v28[6]; // [rsp+32h] [rbp-CEh] BYREF
  HSTRING v29; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v31; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+60h] [rbp-A0h]
  __int64 v35; // [rsp+68h] [rbp-98h] BYREF
  HSTRING *v36; // [rsp+70h] [rbp-90h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v38; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v39; // [rsp+88h] [rbp-78h] BYREF
  __int64 v40; // [rsp+90h] [rbp-70h] BYREF
  struct SystemSettings::StorageSenseHandlers::McpServerDefinition *v41[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-58h]
  _BYTE v43[480]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  *(_OWORD *)v41 = 0;
  v42 = 0;
  UnfilteredMcpServerDefinitions = SystemSettings::StorageSenseHandlers::GetUnfilteredMcpServerDefinitions(v41);
  if ( UnfilteredMcpServerDefinitions < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xD0F,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)(unsigned int)UnfilteredMcpServerDefinitions,
      v25);
  v3 = 0;
  v39 = 0;
  Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission>(&v29);
  v4 = v29;
  if ( v29 )
  {
    v5 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned int>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,unsigned int,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Initialize(v29);
    if ( v5 >= 0 )
    {
      v3 = v4;
      v29 = 0;
      v39 = v4;
    }
  }
  else
  {
    v5 = -2147024882;
  }
  Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v29);
  if ( v5 >= 0 )
  {
    v7 = v41[0];
    v8 = 0xEEEEEEEEEEEEEEEFuLL * ((v41[1] - v41[0]) >> 5);
    for ( i = v41[0]; i != v41[1]; i = (struct SystemSettings::StorageSenseHandlers::McpServerDefinition *)((char *)i + 480) )
    {
      if ( !*((_QWORD *)i + 6) && !*((_BYTE *)i + 448) )
      {
        string = 0;
        v26 = 0;
        v27 = 0;
        v29 = (HSTRING)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i);
        if ( (int)Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&string, &v29) >= 0
          && (*(int (__fastcall **)(_QWORD, HSTRING, char *))(**((_QWORD **)this + 42) + 64LL))(
               *((_QWORD *)this + 42),
               string,
               &v26) >= 0 )
        {
          if ( v26 )
          {
            (*(void (__fastcall **)(_QWORD, HSTRING, _QWORD, char *))(**((_QWORD **)this + 42) + 80LL))(
              *((_QWORD *)this + 42),
              string,
              0,
              &v27);
          }
          else if ( (*(int (__fastcall **)(HSTRING, HSTRING, char *))(*(_QWORD *)v3 + 64LL))(v3, string, &v26) >= 0
                 && !v26 )
          {
            v31 = 0;
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v31);
            if ( (int)SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo::Create(
                        i,
                        (struct SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo **)&v31) >= 0 )
            {
              v33 = 0;
              v32 = (unsigned int)v8;
              v34 = 0;
              v29 = v31;
              LODWORD(v36) = 3;
              v10 = Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,enum SystemSettings::StorageSenseHandlers::AppListType,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo *>(
                      &v35,
                      &v36,
                      &v29);
              Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>::operator=(&v33, v10);
              Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v35);
              if ( v33 )
              {
                if ( *(_DWORD *)SettingsHandlersStorageSenseLogging::Provider() > 4u )
                {
                  v29 = (HSTRING)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)i + 128);
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                    v11,
                    (unsigned int)&unk_18015528F,
                    v11,
                    v12,
                    (__int64)&v29);
                }
                v29 = (HSTRING)&v32;
                v36 = &v29;
                SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppLayoutChangedNotification *>::_Notify<_lambda_42ded661f5f033fea7c28cd183b3a6a8_>(
                  this,
                  &v36);
              }
              (*(void (__fastcall **)(HSTRING, HSTRING, __int64, char *))(*(_QWORD *)v3 + 80LL))(v3, string, 1, &v27);
              Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v33);
            }
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v31);
          }
        }
        WindowsDeleteString(string);
      }
    }
    v37 = 0;
    v28[0] = 0;
    v13 = *((_QWORD *)this + 42);
    v14 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(v13 + 16) + 48LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v37);
    if ( v14(v13 + 16, &v37) >= 0 && (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v37 + 56LL))(v37, v28) >= 0 )
    {
      do
      {
        if ( !v28[0] )
          break;
        v35 = 0;
        v15 = v37;
        v16 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 48LL);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v35);
        if ( v16(v15, &v35) >= 0 )
        {
          v31 = 0;
          LODWORD(v36) = 1;
          (*(void (__fastcall **)(__int64, HSTRING **))(*(_QWORD *)v35 + 56LL))(v35, &v36);
          if ( (_DWORD)v36 )
          {
            v17 = v35;
            v18 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v35 + 48LL);
            WindowsDeleteString(v31);
            v31 = 0;
            v18(v17, &v31);
            SystemSettings::StorageSenseHandlers::McpServerDefinition::McpServerDefinition((SystemSettings::StorageSenseHandlers::McpServerDefinition *)v43);
            StringRawBuffer = WindowsGetStringRawBuffer(v31, 0);
            std::wstring::assign(v43, StringRawBuffer);
            v29 = 0;
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v29);
            if ( (int)SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo::Create(
                        (const struct SystemSettings::StorageSenseHandlers::McpServerDefinition *)v43,
                        (struct SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo **)&v29) >= 0 )
            {
              v33 = 0;
              v32 = (unsigned int)v8 | 0x200000000LL;
              v34 = 0;
              v38 = (__int64 *)v29;
              LODWORD(string) = 3;
              v20 = Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,enum SystemSettings::StorageSenseHandlers::AppListType,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo *>(
                      &v40,
                      &string,
                      &v38);
              Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>::operator=(&v33, v20);
              Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v40);
              if ( v33 )
              {
                v21 = SettingsHandlersStorageSenseLogging::Provider();
                if ( *(_DWORD *)v21 > 4u )
                {
                  v38 = (__int64 *)WindowsGetStringRawBuffer(v31, 0);
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                    (_DWORD)v21,
                    (unsigned int)&unk_180155239,
                    v22,
                    v23,
                    (__int64)&v38);
                }
                v38 = &v32;
                string = (HSTRING)&v38;
                SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppLayoutChangedNotification *>::_Notify<_lambda_42ded661f5f033fea7c28cd183b3a6a8_>(
                  this,
                  &string);
              }
              Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v33);
            }
            Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v29);
            SystemSettings::StorageSenseHandlers::McpServerDefinition::~McpServerDefinition((SystemSettings::StorageSenseHandlers::McpServerDefinition *)v43);
          }
          WindowsDeleteString(v31);
        }
        v24 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v37 + 64LL))(v37, v28);
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v35);
      }
      while ( v24 >= 0 );
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 96LL))(*((_QWORD *)this + 42));
    while ( v7 != v41[1] )
    {
      if ( !*((_QWORD *)v7 + 6) )
      {
        v29 = 0;
        v27 = 0;
        v40 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7);
        if ( (int)Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v29, &v40) >= 0 )
          (*(void (__fastcall **)(_QWORD, HSTRING, __int64, char *))(**((_QWORD **)this + 42) + 80LL))(
            *((_QWORD *)this + 42),
            v29,
            1,
            &v27);
        WindowsDeleteString(v29);
      }
      v7 = (struct SystemSettings::StorageSenseHandlers::McpServerDefinition *)((char *)v7 + 480);
    }
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v37);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v39);
    std::vector<SystemSettings::StorageSenseHandlers::McpServerDefinition>::_Tidy(v41);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD13,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
      (const char *)(unsigned int)v5,
      v25);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v39);
    std::vector<SystemSettings::StorageSenseHandlers::McpServerDefinition>::_Tidy(v41);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x1800a3c08  mov     [rsp-8+arg_8], rbx
0x1800a3c0d  mov     [rsp-8+arg_10], rsi
0x1800a3c12  push    rbp
0x1800a3c13  push    rdi
0x1800a3c14  push    r13
0x1800a3c16  push    r14
0x1800a3c18  push    r15
0x1800a3c1a  lea     rbp, [rsp-1A0h]
0x1800a3c22  sub     rsp, 2A0h
0x1800a3c29  mov     rax, cs:__security_cookie
0x1800a3c30  xor     rax, rsp
0x1800a3c33  mov     [rbp+1C0h+var_30], rax
0x1800a3c3a  mov     r15, rcx
0x1800a3c3d  xorps   xmm0, xmm0
0x1800a3c40  movdqu  xmmword ptr [rbp+1C0h+var_228], xmm0
0x1800a3c45  xor     r13d, r13d
0x1800a3c48  mov     [rbp+1C0h+var_218], r13
0x1800a3c4c  lea     rcx, [rbp+1C0h+var_228]
0x1800a3c50  call    ?GetUnfilteredMcpServerDefinitions@StorageSenseHandlers@SystemSettings@@YAJAEAV?$vector@UMcpServerDefinition@StorageSenseHandlers@SystemSettings@@V?$allocator@UMcpServerDefinition@StorageSenseHandlers@SystemSettings@@@std@@@std@@@Z; SystemSettings::StorageSenseHandlers::GetUnfilteredMcpServerDefinitions(std::vector<SystemSettings::StorageSenseHandlers::McpServerDefinition> &)
0x1800a3c55  mov     rcx, [rbp+1C8h]; this
0x1800a3c5c  test    eax, eax
0x1800a3c5e  js      loc_1800A4217
0x1800a3c64  mov     ebx, r13d
0x1800a3c67  mov     [rbp+1C0h+var_238], rbx
0x1800a3c6b  lea     rcx, [rsp+2C0h+var_288]
0x1800a3c70  call    ??$Make@V?$HashMap@PEAUHSTRING__@@IU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@I@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@IU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEBU?$DefaultHash@PEAUHSTRING__@@@2345@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@2345@Upermission@12345@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$HashMap@PEAUHSTRING__@@IU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@I@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@IU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@@12@AEBU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@5678@$$QEAUpermission@?$HashMap@PEAUHSTRING__@@IU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@I@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@IU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@5678@@Z; Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission>(Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission &&)
0x1800a3c75  mov     rdi, [rsp+2C0h+var_288]
0x1800a3c7a  test    rdi, rdi
0x1800a3c7d  jz      short loc_1800A3C9B
0x1800a3c7f  mov     rcx, rdi
0x1800a3c82  call    ?Initialize@?$HashMap@PEAUHSTRING__@@IU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@I@3456@U?$DefaultHashMapOptions@PEAUHSTRING__@@IU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@AEAAJXZ; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uint>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,uint,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Initialize(void)
0x1800a3c87  mov     esi, eax
0x1800a3c89  test    eax, eax
0x1800a3c8b  js      short loc_1800A3CA0
0x1800a3c8d  mov     rbx, rdi
0x1800a3c90  mov     [rsp+2C0h+var_288], r13
0x1800a3c95  mov     [rbp+1C0h+var_238], rbx
0x1800a3c99  jmp     short loc_1800A3CA0
0x1800a3c9b  mov     esi, 8007000Eh
0x1800a3ca0  lea     rcx, [rsp+2C0h+var_288]
0x1800a3ca5  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a3caa  test    esi, esi
0x1800a3cac  jns     short loc_1800A3CE4
0x1800a3cae  mov     rcx, [rbp+1C8h]; this
0x1800a3cb5  mov     r9d, esi; char *
0x1800a3cb8  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800a3cbf  mov     edx, 0D13h; void *
0x1800a3cc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a3cc9  nop
0x1800a3cca  lea     rcx, [rbp+1C0h+var_238]
0x1800a3cce  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a3cd3  nop
0x1800a3cd4  lea     rcx, [rbp+1C0h+var_228]
0x1800a3cd8  call    ?_Tidy@?$vector@UMcpServerDefinition@StorageSenseHandlers@SystemSettings@@V?$allocator@UMcpServerDefinition@StorageSenseHandlers@SystemSettings@@@std@@@std@@AEAAXXZ; std::vector<SystemSettings::StorageSenseHandlers::McpServerDefinition>::_Tidy(void)
0x1800a3cdd  mov     eax, esi
0x1800a3cdf  jmp     loc_1800A41EC
0x1800a3ce4  mov     rsi, [rbp+1C0h+var_228]
0x1800a3ce8  mov     r14, [rbp+1C0h+var_228+8]
0x1800a3cec  sub     r14, rsi
0x1800a3cef  sar     r14, 5
0x1800a3cf3  mov     rax, 0EEEEEEEEEEEEEEEFh
0x1800a3cfd  imul    r14, rax
0x1800a3d01  mov     rdi, rsi
0x1800a3d04  cmp     rsi, [rbp+1C0h+var_228+8]
0x1800a3d08  jz      loc_1800A3F04
0x1800a3d0e  cmp     [rdi+30h], r13
0x1800a3d12  jnz     loc_1800A3EF3
0x1800a3d18  cmp     [rdi+1C0h], r13b
0x1800a3d1f  jnz     loc_1800A3EF3
0x1800a3d25  mov     [rsp+2C0h+string], r13
0x1800a3d2a  mov     [rsp+2C0h+var_290], r13b
0x1800a3d2f  mov     [rsp+2C0h+var_28F], r13b
0x1800a3d34  mov     rcx, rdi
0x1800a3d37  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a3d3c  mov     [rsp+2C0h+var_288], rax
0x1800a3d41  lea     rdx, [rsp+2C0h+var_288]
0x1800a3d46  lea     rcx, [rsp+2C0h+string]
0x1800a3d4b  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1800a3d50  test    eax, eax
0x1800a3d52  js      loc_1800A3EE8
0x1800a3d58  mov     rcx, [r15+150h]
0x1800a3d5f  mov     rax, [rcx]
0x1800a3d62  lea     r8, [rsp+2C0h+var_290]
0x1800a3d67  mov     rdx, [rsp+2C0h+string]
0x1800a3d6c  mov     rax, [rax+40h]
0x1800a3d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3d75  test    eax, eax
0x1800a3d77  js      loc_1800A3EE8
0x1800a3d7d  mov     rdx, [rsp+2C0h+string]
0x1800a3d82  cmp     [rsp+2C0h+var_290], r13b
0x1800a3d87  jz      short loc_1800A3DA9
0x1800a3d89  mov     rcx, [r15+150h]
0x1800a3d90  mov     rax, [rcx]
0x1800a3d93  lea     r9, [rsp+2C0h+var_28F]
0x1800a3d98  xor     r8d, r8d
0x1800a3d9b  mov     rax, [rax+50h]
0x1800a3d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3da4  jmp     loc_1800A3EE8
0x1800a3da9  mov     rax, [rbx]
0x1800a3dac  lea     r8, [rsp+2C0h+var_290]
0x1800a3db1  mov     rcx, rbx
0x1800a3db4  mov     rax, [rax+40h]
0x1800a3db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3dbd  test    eax, eax
0x1800a3dbf  js      loc_1800A3EE8
0x1800a3dc5  cmp     [rsp+2C0h+var_290], r13b
0x1800a3dca  jnz     loc_1800A3EE8
0x1800a3dd0  mov     [rsp+2C0h+var_278], r13
0x1800a3dd5  lea     rcx, [rsp+2C0h+var_278]
0x1800a3dda  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a3ddf  lea     rdx, [rsp+2C0h+var_278]; struct SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo **
0x1800a3de4  mov     rcx, rdi; struct SystemSettings::StorageSenseHandlers::McpServerDefinition *
0x1800a3de7  call    ?Create@CMcpServerPackageInfo@StorageSenseHandlers@SystemSettings@@SAJAEBUMcpServerDefinition@23@PEAPEAV123@@Z; SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo::Create(SystemSettings::StorageSenseHandlers::McpServerDefinition const &,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo * *)
0x1800a3dec  test    eax, eax
0x1800a3dee  js      loc_1800A3EDD
0x1800a3df4  xor     eax, eax
0x1800a3df6  mov     [rsp+2C0h+var_270], rax
0x1800a3dfb  mov     [rsp+2C0h+var_268], r13
0x1800a3e00  mov     [rsp+2C0h+var_260], rax
0x1800a3e05  mov     dword ptr [rsp+2C0h+var_270], r14d
0x1800a3e0a  mov     byte ptr [rsp+2C0h+var_260], r13b
0x1800a3e0f  mov     dword ptr [rsp+2C0h+var_270+4], r13d
0x1800a3e14  mov     rax, [rsp+2C0h+var_278]
0x1800a3e19  mov     [rsp+2C0h+var_288], rax
0x1800a3e1e  mov     dword ptr [rsp+2C0h+var_250], 3
0x1800a3e26  lea     r8, [rsp+2C0h+var_288]
0x1800a3e2b  lea     rdx, [rsp+2C0h+var_250]
0x1800a3e30  lea     rcx, [rsp+2C0h+var_258]
0x1800a3e35  call    ??$Make@VCAppTileData@StorageSenseHandlers@SystemSettings@@W4AppListType@23@PEAVCMcpServerPackageInfo@23@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@12@$$QEAW4AppListType@StorageSenseHandlers@SystemSettings@@$$QEAPEAVCMcpServerPackageInfo@56@@Z; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,SystemSettings::StorageSenseHandlers::AppListType,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo *>(SystemSettings::StorageSenseHandlers::AppListType &&,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo * &&)
0x1800a3e3a  mov     rdx, rax
0x1800a3e3d  lea     rcx, [rsp+2C0h+var_268]
0x1800a3e42  call    ??4?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>::operator=(Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData> &&)
0x1800a3e47  lea     rcx, [rsp+2C0h+var_258]
0x1800a3e4c  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a3e51  cmp     [rsp+2C0h+var_268], r13
0x1800a3e56  jz      short loc_1800A3EB2
0x1800a3e58  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x1800a3e5d  mov     r8, rax
0x1800a3e60  mov     ecx, [rax]
0x1800a3e62  cmp     ecx, 4
0x1800a3e65  jbe     short loc_1800A3E91
0x1800a3e67  lea     rcx, [rdi+80h]
0x1800a3e6e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a3e73  mov     [rsp+2C0h+var_288], rax
0x1800a3e78  lea     rax, [rsp+2C0h+var_288]
0x1800a3e7d  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x1800a3e82  lea     rdx, unk_18015528F
0x1800a3e89  mov     rcx, r8
0x1800a3e8c  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800a3e91  lea     rax, [rsp+2C0h+var_270]
0x1800a3e96  mov     [rsp+2C0h+var_288], rax
0x1800a3e9b  lea     rax, [rsp+2C0h+var_288]
0x1800a3ea0  mov     [rsp+2C0h+var_250], rax
0x1800a3ea5  lea     rdx, [rsp+2C0h+var_250]
0x1800a3eaa  mov     rcx, r15
0x1800a3ead  call    ??$_Notify@V_lambda_42ded661f5f033fea7c28cd183b3a6a8_@@@?$CSingletonHelper@PEAUAppLayoutChangedNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_42ded661f5f033fea7c28cd183b3a6a8_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppLayoutChangedNotification *>::_Notify<_lambda_42ded661f5f033fea7c28cd183b3a6a8_>(_lambda_42ded661f5f033fea7c28cd183b3a6a8_ const &)
0x1800a3eb2  mov     rax, [rbx]
0x1800a3eb5  lea     r9, [rsp+2C0h+var_28F]
0x1800a3eba  mov     r8d, 1
0x1800a3ec0  mov     rdx, [rsp+2C0h+string]
0x1800a3ec5  mov     rcx, rbx
0x1800a3ec8  mov     rax, [rax+50h]
0x1800a3ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3ed1  nop
0x1800a3ed2  lea     rcx, [rsp+2C0h+var_268]
0x1800a3ed7  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a3edc  nop
0x1800a3edd  lea     rcx, [rsp+2C0h+var_278]
0x1800a3ee2  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a3ee7  nop
0x1800a3ee8  mov     rcx, [rsp+2C0h+string]; string
0x1800a3eed  call    cs:__imp_WindowsDeleteString
0x1800a3ef3  add     rdi, 1E0h
0x1800a3efa  cmp     rdi, [rbp+1C0h+var_228+8]
0x1800a3efe  jnz     loc_1800A3D0E
0x1800a3f04  mov     [rsp+2C0h+var_248], r13
0x1800a3f09  mov     [rsp+2C0h+var_28E], r13b
0x1800a3f0e  mov     rdi, [r15+150h]
0x1800a3f15  mov     rax, [rdi+10h]
0x1800a3f19  mov     rbx, [rax+30h]
0x1800a3f1d  lea     rcx, [rsp+2C0h+var_248]
0x1800a3f22  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a3f27  lea     rdx, [rsp+2C0h+var_248]
0x1800a3f2c  lea     rcx, [rdi+10h]
0x1800a3f30  mov     rax, rbx
0x1800a3f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3f38  test    eax, eax
0x1800a3f3a  js      loc_1800A414E
0x1800a3f40  mov     rcx, [rsp+2C0h+var_248]
0x1800a3f45  mov     rax, [rcx]
0x1800a3f48  lea     rdx, [rsp+2C0h+var_28E]
0x1800a3f4d  mov     rax, [rax+38h]
0x1800a3f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3f56  test    eax, eax
0x1800a3f58  js      loc_1800A414E
0x1800a3f5e  cmp     [rsp+2C0h+var_28E], r13b
0x1800a3f63  jz      loc_1800A414E
0x1800a3f69  mov     [rsp+2C0h+var_258], r13
0x1800a3f6e  mov     rdi, [rsp+2C0h+var_248]
0x1800a3f73  mov     rax, [rdi]
0x1800a3f76  mov     rbx, [rax+30h]
0x1800a3f7a  lea     rcx, [rsp+2C0h+var_258]
0x1800a3f7f  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a3f84  lea     rdx, [rsp+2C0h+var_258]
0x1800a3f89  mov     rcx, rdi
0x1800a3f8c  mov     rax, rbx
0x1800a3f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3f94  test    eax, eax
0x1800a3f96  js      loc_1800A4124
0x1800a3f9c  mov     [rsp+2C0h+var_278], r13
0x1800a3fa1  mov     dword ptr [rsp+2C0h+var_250], 1
0x1800a3fa9  mov     rcx, [rsp+2C0h+var_258]
0x1800a3fae  mov     rax, [rcx]
0x1800a3fb1  lea     rdx, [rsp+2C0h+var_250]
0x1800a3fb6  mov     rax, [rax+38h]
0x1800a3fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3fbf  cmp     dword ptr [rsp+2C0h+var_250], r13d
0x1800a3fc4  jz      loc_1800A4119
0x1800a3fca  mov     rdi, [rsp+2C0h+var_258]
0x1800a3fcf  mov     rax, [rdi]
0x1800a3fd2  mov     rbx, [rax+30h]
0x1800a3fd6  mov     rcx, [rsp+2C0h+var_278]; string
0x1800a3fdb  call    cs:__imp_WindowsDeleteString
0x1800a3fe1  mov     [rsp+2C0h+var_278], r13
0x1800a3fe6  lea     rdx, [rsp+2C0h+var_278]
0x1800a3feb  mov     rcx, rdi
0x1800a3fee  mov     rax, rbx
0x1800a3ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3ff6  lea     rcx, [rbp+1C0h+var_210]; this
0x1800a3ffa  call    ??0McpServerDefinition@StorageSenseHandlers@SystemSettings@@QEAA@XZ; SystemSettings::StorageSenseHandlers::McpServerDefinition::McpServerDefinition(void)
0x1800a3fff  nop
0x1800a4000  xor     edx, edx; length
0x1800a4002  mov     rcx, [rsp+2C0h+var_278]; string
0x1800a4007  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a400d  mov     rdx, rax
0x1800a4010  lea     rcx, [rbp+1C0h+var_210]
0x1800a4014  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800a4019  mov     [rsp+2C0h+var_288], r13
0x1800a401e  lea     rcx, [rsp+2C0h+var_288]
0x1800a4023  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a4028  lea     rdx, [rsp+2C0h+var_288]; struct SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo **
0x1800a402d  lea     rcx, [rbp+1C0h+var_210]; struct SystemSettings::StorageSenseHandlers::McpServerDefinition *
0x1800a4031  call    ?Create@CMcpServerPackageInfo@StorageSenseHandlers@SystemSettings@@SAJAEBUMcpServerDefinition@23@PEAPEAV123@@Z; SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo::Create(SystemSettings::StorageSenseHandlers::McpServerDefinition const &,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo * *)
0x1800a4036  test    eax, eax
0x1800a4038  js      loc_1800A4104
0x1800a403e  xor     eax, eax
0x1800a4040  mov     [rsp+2C0h+var_270], rax
0x1800a4045  mov     [rsp+2C0h+var_268], r13
0x1800a404a  mov     [rsp+2C0h+var_260], rax
0x1800a404f  mov     dword ptr [rsp+2C0h+var_270], r14d
0x1800a4054  mov     byte ptr [rsp+2C0h+var_260], r13b
0x1800a4059  mov     dword ptr [rsp+2C0h+var_270+4], 2
0x1800a4061  mov     rax, [rsp+2C0h+var_288]
0x1800a4066  mov     [rbp+1C0h+var_240], rax
0x1800a406a  mov     dword ptr [rsp+2C0h+string], 3
0x1800a4072  lea     r8, [rbp+1C0h+var_240]
0x1800a4076  lea     rdx, [rsp+2C0h+string]
0x1800a407b  lea     rcx, [rbp+1C0h+var_230]
0x1800a407f  call    ??$Make@VCAppTileData@StorageSenseHandlers@SystemSettings@@W4AppListType@23@PEAVCMcpServerPackageInfo@23@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@12@$$QEAW4AppListType@StorageSenseHandlers@SystemSettings@@$$QEAPEAVCMcpServerPackageInfo@56@@Z; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,SystemSettings::StorageSenseHandlers::AppListType,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo *>(SystemSettings::StorageSenseHandlers::AppListType &&,SystemSettings::StorageSenseHandlers::CMcpServerPackageInfo * &&)
0x1800a4084  mov     rdx, rax
0x1800a4087  lea     rcx, [rsp+2C0h+var_268]
0x1800a408c  call    ??4?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData>::operator=(Microsoft::WRL::ComPtr<SystemSettings::StorageSenseHandlers::CAppTileData> &&)
0x1800a4091  lea     rcx, [rbp+1C0h+var_230]
0x1800a4095  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a409a  cmp     [rsp+2C0h+var_268], r13
0x1800a409f  jz      short loc_1800A40F9
0x1800a40a1  call    ?Provider@SettingsHandlersStorageSenseLogging@@SAPEBU_tlgProvider_t@@XZ; SettingsHandlersStorageSenseLogging::Provider(void)
0x1800a40a6  mov     rbx, rax
0x1800a40a9  mov     ecx, [rax]
0x1800a40ab  cmp     ecx, 4
0x1800a40ae  jbe     short loc_1800A40D9
0x1800a40b0  xor     edx, edx; length
0x1800a40b2  mov     rcx, [rsp+2C0h+var_278]; string
0x1800a40b7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a40bd  mov     [rbp+1C0h+var_240], rax
0x1800a40c1  lea     rax, [rbp+1C0h+var_240]
0x1800a40c5  mov     qword ptr [rsp+2C0h+var_2A0], rax
0x1800a40ca  lea     rdx, unk_180155239
0x1800a40d1  mov     rcx, rbx
0x1800a40d4  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800a40d9  lea     rax, [rsp+2C0h+var_270]
0x1800a40de  mov     [rbp+1C0h+var_240], rax
0x1800a40e2  lea     rax, [rbp+1C0h+var_240]
0x1800a40e6  mov     [rsp+2C0h+string], rax
0x1800a40eb  lea     rdx, [rsp+2C0h+string]
0x1800a40f0  mov     rcx, r15
0x1800a40f3  call    ??$_Notify@V_lambda_42ded661f5f033fea7c28cd183b3a6a8_@@@?$CSingletonHelper@PEAUAppLayoutChangedNotification@StorageSenseHandlers@SystemSettings@@@DataModel@SystemSettings@@AEAAXAEBV_lambda_42ded661f5f033fea7c28cd183b3a6a8_@@@Z; SystemSettings::DataModel::CSingletonHelper<SystemSettings::StorageSenseHandlers::AppLayoutChangedNotification *>::_Notify<_lambda_42ded661f5f033fea7c28cd183b3a6a8_>(_lambda_42ded661f5f033fea7c28cd183b3a6a8_ const &)
0x1800a40f8  nop
0x1800a40f9  lea     rcx, [rsp+2C0h+var_268]
0x1800a40fe  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a4103  nop
0x1800a4104  lea     rcx, [rsp+2C0h+var_288]
0x1800a4109  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800a410e  nop
0x1800a410f  lea     rcx, [rbp+1C0h+var_210]; this
0x1800a4113  call    ??1McpServerDefinition@StorageSenseHandlers@SystemSettings@@QEAA@XZ; SystemSettings::StorageSenseHandlers::McpServerDefinition::~McpServerDefinition(void)
0x1800a4118  nop
0x1800a4119  mov     rcx, [rsp+2C0h+var_278]; string
0x1800a411e  call    cs:__imp_WindowsDeleteString
0x1800a4124  mov     rcx, [rsp+2C0h+var_248]
  ... truncated ...
```
