# SqliteDatabase::ReloadBackup(void)

- ea: `0x1800a3180`
- end: `0x1800a39c3`
- name: `?ReloadBackup@SqliteDatabase@@AEAAXXZ`
- size: `2115`
- prototype: `void __fastcall(SqliteDatabase *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a2db0`

## callees

- `0x180004e38`
- `0x180005994`
- `0x180006038`
- `0x18000e090`
- `0x18000e5f4`
- `0x18002ee38`
- `0x180045ab4`
- `0x180048934`
- `0x180079f88`
- `0x18007ca90`
- `0x1800a3180`
- `0x1800a39cc`
- `0x1800a3b2c`
- `0x1800a3c0c`
- `0x1800a8eb0`
- `0x1800af1ec`
- `0x1800b17fc`
- `0x1800b99f0`
- `0x1800ba574`
- `0x180118010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1800a3427`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1800a3715`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1800a3755`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1800a376b`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1800a3427`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1800a3715`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1800a3755`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1800a376b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a372c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a372c`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800a31db`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyW` at `0x1800a31db`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1800a3215`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1800a3215`

## string_xrefs

- `0x1800a3296`: `wnsId`
- `0x1800a3348`: `channelUri`
- `0x1800a3306`: `IconUri`
- `0x1800a3633`: `IconUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
void __fastcall SqliteDatabase::ReloadBackup(SqliteDatabase *this)
{
  SqliteDatabase *v1; // rdi
  DWORD v2; // r14d
  LSTATUS v3; // eax
  int v4; // eax
  __int64 v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rbx
  SqliteDatabase *v20; // rcx
  int v21; // eax
  unsigned __int16 *v22; // rax
  unsigned __int64 v23; // rax
  int v24; // eax
  char *v25; // rsi
  int v26; // eax
  AssetCollection *v27; // rdi
  int v28; // eax
  __int64 v29; // r12
  __int64 v30; // r13
  unsigned __int64 v31; // r15
  __int64 v32; // rbx
  int v33; // eax
  int v34; // eax
  int *v35; // [rsp+20h] [rbp-E0h]
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  struct NotificationSettings *v37; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  int v41[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v42; // [rsp+80h] [rbp-80h] BYREF
  __int64 v43; // [rsp+88h] [rbp-78h] BYREF
  __int64 v44; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v45[3]; // [rsp+98h] [rbp-68h] BYREF
  AssetCollection *v46; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v47[3]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v48[3]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v49[3]; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v50[6]; // [rsp+100h] [rbp+0h] BYREF
  SqliteDatabase *v51; // [rsp+130h] [rbp+30h]
  _QWORD v52[3]; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v53[3]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v54[3]; // [rsp+168h] [rbp+68h] BYREF
  unsigned __int16 *v55[3]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 *v56[3]; // [rsp+198h] [rbp+98h] BYREF
  unsigned __int16 *v57[3]; // [rsp+1B0h] [rbp+B0h] BYREF
  _QWORD v58[3]; // [rsp+1C8h] [rbp+C8h] BYREF
  _QWORD v59[3]; // [rsp+1E0h] [rbp+E0h] BYREF
  _QWORD v60[3]; // [rsp+1F8h] [rbp+F8h] BYREF
  _QWORD v61[3]; // [rsp+210h] [rbp+110h] BYREF
  _QWORD v62[3]; // [rsp+228h] [rbp+128h] BYREF
  WCHAR Name[136]; // [rsp+240h] [rbp+140h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+2A8h]

  v1 = this;
  v51 = this;
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  if ( !RegOpenKeyW(HKEY_CURRENT_USER, *((LPCWSTR *)v1 + 16), &phkResult) )
  {
    v2 = 0;
    memset_0(Name, 0, 0x102u);
    while ( 1 )
    {
      v3 = RegEnumKeyW(phkResult, v2, Name, 0x81u);
      if ( v3 == 234 )
        goto LABEL_18;
      if ( v3 )
        goto LABEL_44;
      memset(v47, 0, sizeof(v47));
      v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
             v47,
             L"%s\\%s",
             *((_QWORD *)v1 + 16),
             Name);
      if ( v4 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD30,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
          (const char *)(unsigned int)v4,
          (int)v35);
      v5 = v47[0];
      SqliteDatabase::ReadRegString(retaddr, v50, v47[0], L"Setting");
      SqliteDatabase::ReadRegString(v6, v59, v5, L"appType");
      SqliteDatabase::ReadRegString(v7, v49, v5, L"wnsId");
      SqliteDatabase::ReadRegString(v8, v58, v5, L"wnfEventName");
      SqliteDatabase::ReadRegString(v9, v62, v5, L"parent");
      SqliteDatabase::ReadRegString(v10, v61, v5, L"container");
      SqliteDatabase::ReadRegString(v11, v57, v5, L"DisplayName");
      SqliteDatabase::ReadRegString(v12, v56, v5, L"IconUri");
      SqliteDatabase::ReadRegString(v13, v55, v5, L"LaunchArgs");
      SqliteDatabase::ReadRegAnsiString(v14, v54, v5, L"channelId");
      SqliteDatabase::ReadRegAnsiString(v15, v53, v5, L"channelUri");
      SqliteDatabase::ReadRegString(v16, v52, v5, L"channelExpiry");
      SqliteDatabase::ReadRegString(v17, v48, v5, L"channelCreation");
      SqliteDatabase::ReadRegString(v18, v60, v5, L"deviceVersion");
      if ( v50[1] == v50[0] )
        goto LABEL_17;
      v19 = v59[0];
      if ( v59[1] == v59[0] )
        goto LABEL_17;
      v37 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
      v21 = SqliteDatabase::ParseSettingsFromRegistry(v20, v50[0], Name, &v37);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD49,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
          (const char *)(unsigned int)v21,
          (int)v35);
      v36 = 0;
      v50[3] = (unsigned __int16 *)v61[0];
      v50[4] = (unsigned __int16 *)v62[0];
      if ( (__int64)(v58[1] - v58[0]) >> 1 )
        v22 = (unsigned __int16 *)_o__wcstoui64(v58[0], 0, 10);
      else
        v22 = 0;
      v50[5] = v22;
      v44 = 0;
      v45[0] = 0;
      *(_QWORD *)v41 = v37;
      v23 = 0;
      if ( (__int64)(v49[1] - v49[0]) >> 1 )
        v23 = v49[0];
      v42 = v23;
      v43 = v19;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
      v35 = v41;
      v24 = Microsoft::WRL::Details::MakeAndInitialize<NotificationHandler,NotificationHandler,unsigned short (&)[129],unsigned short *,unsigned short *,NotificationSettings *,std::nullptr_t,std::nullptr_t,unsigned __int64,unsigned short *,unsigned short *>(
              &v36,
              Name,
              &v43,
              &v42);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD56,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
          (const char *)(unsigned int)v24,
          (int)v41);
      v25 = (char *)v1 + 32;
      v26 = (*(__int64 (__fastcall **)(__int64, __int64))(*((_QWORD *)v1 + 4) + 184LL))(
              (__int64)v1 + 32,
              (v36 + 32) & -(__int64)(v36 != 0));
      if ( v26 < 0 )
        break;
      Microsoft::WRL::Details::Make<AssetCollection,>(&v46);
      v27 = v46;
      if ( v57[1] - v57[0] )
        AssetCollection::AddAsset(v46, Name, L"DisplayName", v57[0]);
      if ( v56[1] - v56[0] )
        AssetCollection::AddAsset(v27, Name, L"IconUri", v56[0]);
      if ( v55[1] - v55[0] )
        AssetCollection::AddAsset(v27, Name, L"LaunchArgs", v55[0]);
      if ( (__int64)(*((_QWORD *)v27 + 7) - *((_QWORD *)v27 + 6)) >> 3 )
      {
        v28 = (*(__int64 (__fastcall **)(char *, WCHAR *, unsigned __int64))(*(_QWORD *)v25 + 160LL))(
                v25,
                Name,
                ((unsigned __int64)v27 + 32) & -(__int64)(v27 != 0));
        if ( v28 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xD70,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
            (const char *)(unsigned int)v28,
            (int)v41);
      }
      if ( (__int64)(v52[1] - v52[0]) >> 1 )
      {
        if ( (__int64)(v48[1] - v48[0]) >> 1 )
        {
          v29 = v54[0];
          if ( v54[1] != v54[0] )
          {
            v30 = v53[0];
            if ( v53[1] != v53[0] )
            {
              v31 = _o__wcstoui64(v52[0], 0, 10);
              SystemTimeAsFileTime = 0;
              GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
              if ( v31 >= *(_QWORD *)&SystemTimeAsFileTime )
              {
                v32 = _o__wcstoui64(v48[0], 0, 10);
                v43 = _o__wcstoui64(v60[0], 0, 10);
                v39 = 0;
                v45[1] = v31;
                v42 = v31;
                v45[2] = v32;
                *(_QWORD *)v41 = v32;
                v45[0] = v30;
                v44 = v29;
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
                v35 = v41;
                v33 = Microsoft::WRL::Details::MakeAndInitialize<WNSChannelDetails,WNSChannelDetails,unsigned short (&)[129],char *,char *,_FILETIME,_FILETIME,unsigned __int64 const &>(
                        &v39,
                        Name,
                        &v44,
                        v45);
                if ( v33 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0xD89,
                    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
                    (const char *)(unsigned int)v33,
                    (int)v41);
                v34 = (*(__int64 (__fastcall **)(char *, WCHAR *, __int64))(*(_QWORD *)v25 + 280LL))(
                        v25,
                        Name,
                        (v39 + 32) & -(__int64)(v39 != 0));
                if ( v34 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0xD8B,
                    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
                    (const char *)(unsigned int)v34,
                    (int)v41);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
              }
            }
          }
        }
      }
      if ( v27 )
      {
        v46 = 0;
        (*(void (__fastcall **)(AssetCollection *))(*(_QWORD *)v27 + 16LL))(v27);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
      std::vector<unsigned short>::_Tidy(v60);
      std::vector<unsigned short>::_Tidy(v48);
      std::vector<unsigned short>::_Tidy(v52);
      std::vector<unsigned char>::_Tidy(v53);
      std::vector<unsigned char>::_Tidy(v54);
      std::vector<unsigned short>::_Tidy(v55);
      std::vector<unsigned short>::_Tidy(v56);
      std::vector<unsigned short>::_Tidy(v57);
      std::vector<unsigned short>::_Tidy(v61);
      std::vector<unsigned short>::_Tidy(v62);
      std::vector<unsigned short>::_Tidy(v58);
      std::vector<unsigned short>::_Tidy(v49);
      std::vector<unsigned short>::_Tidy(v59);
      std::vector<unsigned short>::_Tidy(v50);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v47);
      v1 = v51;
LABEL_18:
      ++v2;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD59,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\sqlitedatabase.cpp",
      (const char *)(unsigned int)v26,
      (int)v41);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
LABEL_17:
    std::vector<unsigned short>::_Tidy(v60);
    std::vector<unsigned short>::_Tidy(v48);
    std::vector<unsigned short>::_Tidy(v52);
    std::vector<unsigned char>::_Tidy(v53);
    std::vector<unsigned char>::_Tidy(v54);
    std::vector<unsigned short>::_Tidy(v55);
    std::vector<unsigned short>::_Tidy(v56);
    std::vector<unsigned short>::_Tidy(v57);
    std::vector<unsigned short>::_Tidy(v61);
    std::vector<unsigned short>::_Tidy(v62);
    std::vector<unsigned short>::_Tidy(v58);
    std::vector<unsigned short>::_Tidy(v49);
    std::vector<unsigned short>::_Tidy(v59);
    std::vector<unsigned short>::_Tidy(v50);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v47);
    goto LABEL_18;
  }
LABEL_44:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
}

```

## disassembly

```asm
0x1800a3180  push    rbp
0x1800a3182  push    rbx
0x1800a3183  push    rsi
0x1800a3184  push    rdi
0x1800a3185  push    r12
0x1800a3187  push    r13
0x1800a3189  push    r14
0x1800a318b  push    r15
0x1800a318d  lea     rbp, [rsp-268h]
0x1800a3195  sub     rsp, 368h
0x1800a319c  mov     rax, cs:__security_cookie
0x1800a31a3  xor     rax, rsp
0x1800a31a6  mov     [rbp+2A0h+var_50], rax
0x1800a31ad  mov     rdi, rcx
0x1800a31b0  mov     [rbp+2A0h+var_270], rcx
0x1800a31b4  xor     r15d, r15d
0x1800a31b7  mov     [rsp+3A0h+phkResult], r15
0x1800a31bc  xor     edx, edx
0x1800a31be  lea     rcx, [rsp+3A0h+phkResult]
0x1800a31c3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a31c8  lea     r8, [rsp+3A0h+phkResult]; phkResult
0x1800a31cd  mov     rdx, [rdi+80h]; lpSubKey
0x1800a31d4  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800a31db  call    cs:__imp_RegOpenKeyW
0x1800a31e1  test    eax, eax
0x1800a31e3  jnz     loc_1800A3996
0x1800a31e9  mov     r14d, r15d
0x1800a31ec  xor     edx, edx; Val
0x1800a31ee  mov     r8d, 102h; Size
0x1800a31f4  lea     rcx, [rbp+2A0h+Name]; void *
0x1800a31fb  call    memset_0
0x1800a3200  mov     r9d, 81h; cchName
0x1800a3206  lea     r8, [rbp+2A0h+Name]; lpName
0x1800a320d  mov     edx, r14d; dwIndex
0x1800a3210  mov     rcx, [rsp+3A0h+phkResult]; hKey
0x1800a3215  call    cs:__imp_RegEnumKeyW
0x1800a321b  cmp     eax, 0EAh
0x1800a3220  jz      loc_1800A35DB
0x1800a3226  test    eax, eax
0x1800a3228  jnz     loc_1800A3996
0x1800a322e  mov     [rbp+2A0h+var_2E8], r15
0x1800a3232  mov     [rbp+2A0h+var_2E0], r15
0x1800a3236  mov     [rbp+2A0h+var_2D8], r15
0x1800a323a  lea     r9, [rbp+2A0h+Name]
0x1800a3241  mov     r8, [rdi+80h]
0x1800a3248  lea     rdx, aSS_0; "%s\\%s"
0x1800a324f  lea     rcx, [rbp+2A0h+var_2E8]
0x1800a3253  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800a3258  mov     rcx, [rbp+2A8h]; this
0x1800a325f  test    eax, eax
0x1800a3261  js      loc_1800A3981
0x1800a3267  lea     r9, aSetting; "Setting"
0x1800a326e  mov     rbx, [rbp+2A0h+var_2E8]
0x1800a3272  mov     r8, rbx
0x1800a3275  lea     rdx, [rbp+2A0h+var_2A0]
0x1800a3279  call    ?ReadRegString@SqliteDatabase@@AEAA?AV?$vector@GV?$allocator@G@std@@@std@@PEBG0@Z; SqliteDatabase::ReadRegString(ushort const *,ushort const *)
0x1800a327e  nop
0x1800a327f  lea     r9, aApptype; "appType"
0x1800a3286  mov     r8, rbx
0x1800a3289  lea     rdx, [rbp+2A0h+var_1C0]
0x1800a3290  call    ?ReadRegString@SqliteDatabase@@AEAA?AV?$vector@GV?$allocator@G@std@@@std@@PEBG0@Z; SqliteDatabase::ReadRegString(ushort const *,ushort const *)
0x1800a3295  nop
0x1800a3296  lea     r9, aWnsid; "wnsId"
0x1800a329d  mov     r8, rbx
0x1800a32a0  lea     rdx, [rbp+2A0h+var_2B8]
0x1800a32a4  call    ?ReadRegString@SqliteDatabase@@AEAA?AV?$vector@GV?$allocator@G@std@@@std@@PEBG0@Z; SqliteDatabase::ReadRegString(ushort const *,ushort const *)
0x1800a32a9  nop
0x1800a32aa  lea     r9, aWnfeventname_0; "wnfEventName"
0x1800a32b1  mov     r8, rbx
0x1800a32b4  lea     rdx, [rbp+2A0h+var_1D8]
0x1800a32bb  call    ?ReadRegString@SqliteDatabase@@AEAA?AV?$vector@GV?$allocator@G@std@@@std@@PEBG0@Z; SqliteDatabase::ReadRegString(ushort const *,ushort const *)
0x1800a32c0  nop
0x1800a32c1  lea     r9, aParent; "parent"
0x1800a32c8  mov     r8, rbx
0x1800a32cb  lea     rdx, [rbp+2A0h+var_178]
0x1800a32d2  call    ?ReadRegString@SqliteDatabase@@AEAA?AV?$vector@GV?$allocator@G@std@@@std@@PEBG0@Z; SqliteDatabase::ReadRegString(ushort const *,ushort const *)
0x1800a32d7  nop
0x1800a32d8  lea     r9, aContainer; "container"
0x1800a32df  mov     r8, rbx
0x1800a32e2  lea     rdx, [rbp+2A0h+var_190]
0x1800a32e9  call    ?ReadRegString@SqliteDatabase@@AEAA?AV?$vector@GV?$allocator@G@std@@@std@@PEBG0@Z; SqliteDatabase::ReadRegString(ushort const *,ushort const *)
0x1800a32ee  nop
0x1800a32ef  lea     r9, aDisplayname; "DisplayName"
0x1800a32f6  mov     r8, rbx
0x1800a32f9  lea     rdx, [rbp+2A0h+var_1F0]
0x1800a3300  call    ?ReadRegString@SqliteDatabase@@AEAA?AV?$vector@GV?$allocator@G@std@@@std@@PEBG0@Z; SqliteDatabase::ReadRegString(ushort const *,ushort const *)
0x1800a3305  nop
0x1800a3306  lea     r9, aIconuri; "IconUri"
0x1800a330d  mov     r8, rbx
0x1800a3310  lea     rdx, [rbp+2A0h+var_208]
0x1800a3317  call    ?ReadRegString@SqliteDatabase@@AEAA?AV?$vector@GV?$allocator@G@std@@@std@@PEBG0@Z; SqliteDatabase::ReadRegString(ushort const *,ushort const *)
0x1800a331c  nop
0x1800a331d  lea     r9, aLaunchargs; "LaunchArgs"
0x1800a3324  mov     r8, rbx
0x1800a3327  lea     rdx, [rbp+2A0h+var_220]
0x1800a332e  call    ?ReadRegString@SqliteDatabase@@AEAA?AV?$vector@GV?$allocator@G@std@@@std@@PEBG0@Z; SqliteDatabase::ReadRegString(ushort const *,ushort const *)
0x1800a3333  nop
0x1800a3334  lea     r9, aChannelid; "channelId"
0x1800a333b  mov     r8, rbx
0x1800a333e  lea     rdx, [rbp+2A0h+var_238]
0x1800a3342  call    ?ReadRegAnsiString@SqliteDatabase@@AEAA?AV?$vector@DV?$allocator@D@std@@@std@@PEBG0@Z; SqliteDatabase::ReadRegAnsiString(ushort const *,ushort const *)
0x1800a3347  nop
0x1800a3348  lea     r9, aChanneluri; "channelUri"
0x1800a334f  mov     r8, rbx
0x1800a3352  lea     rdx, [rbp+2A0h+var_250]
0x1800a3356  call    ?ReadRegAnsiString@SqliteDatabase@@AEAA?AV?$vector@DV?$allocator@D@std@@@std@@PEBG0@Z; SqliteDatabase::ReadRegAnsiString(ushort const *,ushort const *)
0x1800a335b  nop
0x1800a335c  lea     r9, aChannelexpiry; "channelExpiry"
0x1800a3363  mov     r8, rbx
0x1800a3366  lea     rdx, [rbp+2A0h+var_268]
0x1800a336a  call    ?ReadRegString@SqliteDatabase@@AEAA?AV?$vector@GV?$allocator@G@std@@@std@@PEBG0@Z; SqliteDatabase::ReadRegString(ushort const *,ushort const *)
0x1800a336f  nop
0x1800a3370  lea     r9, aChannelcreatio; "channelCreation"
0x1800a3377  mov     r8, rbx
0x1800a337a  lea     rdx, [rbp+2A0h+var_2D0]
0x1800a337e  call    ?ReadRegString@SqliteDatabase@@AEAA?AV?$vector@GV?$allocator@G@std@@@std@@PEBG0@Z; SqliteDatabase::ReadRegString(ushort const *,ushort const *)
0x1800a3383  nop
0x1800a3384  lea     r9, aDeviceversion_0; "deviceVersion"
0x1800a338b  mov     r8, rbx
0x1800a338e  lea     rdx, [rbp+2A0h+var_1A8]
0x1800a3395  call    ?ReadRegString@SqliteDatabase@@AEAA?AV?$vector@GV?$allocator@G@std@@@std@@PEBG0@Z; SqliteDatabase::ReadRegString(ushort const *,ushort const *)
0x1800a339a  nop
0x1800a339b  mov     rax, [rbp+2A0h+var_298]
0x1800a339f  cmp     rax, [rbp+2A0h+var_2A0]
0x1800a33a3  jz      loc_1800A352E
0x1800a33a9  mov     rbx, [rbp+2A0h+var_1C0]
0x1800a33b0  cmp     [rbp+2A0h+var_1B8], rbx
0x1800a33b7  jz      loc_1800A352E
0x1800a33bd  mov     [rsp+3A0h+var_348], r15
0x1800a33c2  lea     rcx, [rsp+3A0h+var_348]
0x1800a33c7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a33cc  lea     r9, [rsp+3A0h+var_348]; struct NotificationSettings **
0x1800a33d1  lea     r8, [rbp+2A0h+Name]; unsigned __int16 *
0x1800a33d8  mov     rdx, [rbp+2A0h+var_2A0]; unsigned __int16 *
0x1800a33dc  call    ?ParseSettingsFromRegistry@SqliteDatabase@@AEAAJPEAGPEBGPEAPEAVNotificationSettings@@@Z; SqliteDatabase::ParseSettingsFromRegistry(ushort *,ushort const *,NotificationSettings * *)
0x1800a33e1  mov     rcx, [rbp+2A8h]; this
0x1800a33e8  test    eax, eax
0x1800a33ea  js      loc_1800A396C
0x1800a33f0  mov     [rsp+3A0h+var_350], r15
0x1800a33f5  mov     rax, [rbp+2A0h+var_190]
0x1800a33fc  mov     [rbp+2A0h+var_288], rax
0x1800a3400  mov     rax, [rbp+2A0h+var_178]
0x1800a3407  mov     [rbp+2A0h+var_280], rax
0x1800a340b  mov     rax, [rbp+2A0h+var_1D0]
0x1800a3412  mov     rcx, [rbp+2A0h+var_1D8]
0x1800a3419  sub     rax, rcx
0x1800a341c  sar     rax, 1
0x1800a341f  jz      short loc_1800A342F
0x1800a3421  xor     edx, edx
0x1800a3423  lea     r8d, [rdx+0Ah]
0x1800a3427  call    cs:__imp__o__wcstoui64
0x1800a342d  jmp     short loc_1800A3432
0x1800a342f  mov     rax, r15
0x1800a3432  mov     [rbp+2A0h+var_278], rax
0x1800a3436  mov     [rbp+2A0h+var_310], r15
0x1800a343a  mov     [rbp+2A0h+var_308], r15
0x1800a343e  mov     rax, [rsp+3A0h+var_348]
0x1800a3443  mov     qword ptr [rsp+3A0h+var_328], rax
0x1800a3448  mov     rcx, [rbp+2A0h+var_2B0]
0x1800a344c  sub     rcx, [rbp+2A0h+var_2B8]
0x1800a3450  mov     rax, r15
0x1800a3453  sar     rcx, 1
0x1800a3456  cmovnz  rax, [rbp+2A0h+var_2B8]
0x1800a345b  mov     [rbp+2A0h+var_320], rax
0x1800a345f  mov     [rbp+2A0h+var_318], rbx
0x1800a3463  lea     rcx, [rsp+3A0h+var_350]
0x1800a3468  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a346d  lea     rax, [rbp+2A0h+var_288]
0x1800a3471  mov     [rsp+3A0h+var_358], rax
0x1800a3476  lea     rax, [rbp+2A0h+var_280]
0x1800a347a  mov     [rsp+3A0h+var_360], rax
0x1800a347f  lea     rax, [rbp+2A0h+var_278]
0x1800a3483  mov     [rsp+3A0h+var_368], rax
0x1800a3488  lea     rax, [rbp+2A0h+var_310]
0x1800a348c  mov     [rsp+3A0h+var_370], rax
0x1800a3491  lea     rax, [rbp+2A0h+var_308]
0x1800a3495  mov     [rsp+3A0h+var_378], rax
0x1800a349a  lea     rax, [rsp+3A0h+var_328]
0x1800a349f  mov     qword ptr [rsp+3A0h+var_380], rax; int
0x1800a34a4  lea     r9, [rbp+2A0h+var_320]
0x1800a34a8  lea     r8, [rbp+2A0h+var_318]
0x1800a34ac  lea     rdx, [rbp+2A0h+Name]
0x1800a34b3  lea     rcx, [rsp+3A0h+var_350]
0x1800a34b8  call    ??$MakeAndInitialize@VNotificationHandler@@V1@AEAY0IB@GPEAGPEAGPEAVNotificationSettings@@$$T$$T_KPEAGPEAG@Details@WRL@Microsoft@@YAJPEAPEAVNotificationHandler@@AEAY0IB@G$$QEAPEAG2$$QEAPEAVNotificationSettings@@$$QEA$$T4$$QEA_K22@Z
0x1800a34bd  mov     rcx, [rbp+2A8h]; this
0x1800a34c4  test    eax, eax
0x1800a34c6  js      loc_1800A3957
0x1800a34cc  lea     rsi, [rdi+20h]
0x1800a34d0  mov     rcx, [rsp+3A0h+var_350]
0x1800a34d5  mov     r8, [rsi]
0x1800a34d8  lea     rax, [rcx+20h]
0x1800a34dc  neg     rcx
0x1800a34df  sbb     rdx, rdx
0x1800a34e2  and     rdx, rax
0x1800a34e5  mov     rcx, rsi
0x1800a34e8  mov     rax, [r8+0B8h]
0x1800a34ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a34f4  mov     rcx, [rbp+2A8h]; this
0x1800a34fb  test    eax, eax
0x1800a34fd  jns     loc_1800A35E3
0x1800a3503  mov     r9d, eax; char *
0x1800a3506  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800a350d  mov     edx, 0D59h; void *
0x1800a3512  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a3517  nop
0x1800a3518  lea     rcx, [rsp+3A0h+var_350]
0x1800a351d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a3522  nop
0x1800a3523  lea     rcx, [rsp+3A0h+var_348]
0x1800a3528  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a352d  nop
0x1800a352e  lea     rcx, [rbp+2A0h+var_1A8]
0x1800a3535  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800a353a  nop
0x1800a353b  lea     rcx, [rbp+2A0h+var_2D0]
0x1800a353f  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800a3544  nop
0x1800a3545  lea     rcx, [rbp+2A0h+var_268]
0x1800a3549  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800a354e  nop
0x1800a354f  lea     rcx, [rbp+2A0h+var_250]
0x1800a3553  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800a3558  nop
0x1800a3559  lea     rcx, [rbp+2A0h+var_238]
0x1800a355d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800a3562  nop
0x1800a3563  lea     rcx, [rbp+2A0h+var_220]
0x1800a356a  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800a356f  nop
0x1800a3570  lea     rcx, [rbp+2A0h+var_208]
0x1800a3577  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800a357c  nop
0x1800a357d  lea     rcx, [rbp+2A0h+var_1F0]
0x1800a3584  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800a3589  nop
0x1800a358a  lea     rcx, [rbp+2A0h+var_190]
0x1800a3591  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800a3596  nop
0x1800a3597  lea     rcx, [rbp+2A0h+var_178]
0x1800a359e  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800a35a3  nop
0x1800a35a4  lea     rcx, [rbp+2A0h+var_1D8]
0x1800a35ab  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800a35b0  nop
0x1800a35b1  lea     rcx, [rbp+2A0h+var_2B8]
0x1800a35b5  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800a35ba  nop
0x1800a35bb  lea     rcx, [rbp+2A0h+var_1C0]
0x1800a35c2  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800a35c7  nop
0x1800a35c8  lea     rcx, [rbp+2A0h+var_2A0]
0x1800a35cc  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800a35d1  nop
0x1800a35d2  lea     rcx, [rbp+2A0h+var_2E8]
0x1800a35d6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a35db  inc     r14d
0x1800a35de  jmp     loc_1800A3200
0x1800a35e3  lea     rcx, [rbp+2A0h+var_2F0]
0x1800a35e7  call    ??$Make@VAssetCollection@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAssetCollection@@@12@XZ; Microsoft::WRL::Details::Make<AssetCollection,>(void)
0x1800a35ec  nop
0x1800a35ed  mov     rax, [rbp+2A0h+var_1E8]
0x1800a35f4  mov     r9, [rbp+2A0h+var_1F0]; unsigned __int16 *
0x1800a35fb  sub     rax, r9
0x1800a35fe  mov     rdi, [rbp+2A0h+var_2F0]
0x1800a3602  sar     rax, 1
0x1800a3605  jz      short loc_1800A361D
0x1800a3607  lea     r8, aDisplayname; "DisplayName"
0x1800a360e  lea     rdx, [rbp+2A0h+Name]; unsigned __int16 *
0x1800a3615  mov     rcx, rdi; this
0x1800a3618  call    ?AddAsset@AssetCollection@@QEAAXPEBG00@Z; AssetCollection::AddAsset(ushort const *,ushort const *,ushort const *)
0x1800a361d  mov     rax, [rbp+2A0h+var_200]
0x1800a3624  mov     r9, [rbp+2A0h+var_208]; unsigned __int16 *
0x1800a362b  sub     rax, r9
0x1800a362e  sar     rax, 1
0x1800a3631  jz      short loc_1800A3649
0x1800a3633  lea     r8, aIconuri; "IconUri"
0x1800a363a  lea     rdx, [rbp+2A0h+Name]; unsigned __int16 *
0x1800a3641  mov     rcx, rdi; this
0x1800a3644  call    ?AddAsset@AssetCollection@@QEAAXPEBG00@Z; AssetCollection::AddAsset(ushort const *,ushort const *,ushort const *)
0x1800a3649  mov     rax, [rbp+2A0h+var_218]
0x1800a3650  mov     r9, [rbp+2A0h+var_220]; unsigned __int16 *
0x1800a3657  sub     rax, r9
0x1800a365a  sar     rax, 1
0x1800a365d  jz      short loc_1800A3675
0x1800a365f  lea     r8, aLaunchargs; "LaunchArgs"
0x1800a3666  lea     rdx, [rbp+2A0h+Name]; unsigned __int16 *
0x1800a366d  mov     rcx, rdi; this
0x1800a3670  call    ?AddAsset@AssetCollection@@QEAAXPEBG00@Z; AssetCollection::AddAsset(ushort const *,ushort const *,ushort const *)
0x1800a3675  mov     rax, [rdi+38h]
0x1800a3679  sub     rax, [rdi+30h]
0x1800a367d  sar     rax, 3
0x1800a3681  test    rax, rax
0x1800a3684  jz      short loc_1800A36CE
0x1800a3686  mov     r9, [rsi]
0x1800a3689  mov     rax, rdi
0x1800a368c  lea     rcx, [rdi+20h]
0x1800a3690  neg     rax
0x1800a3693  sbb     r8, r8
0x1800a3696  and     r8, rcx
0x1800a3699  lea     rdx, [rbp+2A0h+Name]
  ... truncated ...
```
