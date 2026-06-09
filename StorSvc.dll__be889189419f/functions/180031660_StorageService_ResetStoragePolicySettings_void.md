# StorageService::ResetStoragePolicySettings(void)

- ea: `0x180031660`
- end: `0x180031bae`
- name: `?ResetStoragePolicySettings@StorageService@@QEAAJXZ`
- size: `1358`
- prototype: `__int64 __fastcall(StorageService *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800378c0`

## callees

- `0x18000d030`
- `0x1800108f4`
- `0x180010d24`
- `0x180012734`
- `0x180012ce0`
- `0x180014a00`
- `0x1800176ec`
- `0x180018d54`
- `0x180019db4`
- `0x18003037c`
- `0x180031660`
- `0x18003e95c`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800316aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800316aa`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180031767`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800318fa`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x180031767`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800318fa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800317f1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800317f1`

## string_xrefs

- `0x1800316ec`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180031963`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x1800319bb`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180031a13`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180031a6b`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180031ac3`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180031b18`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180031b6d`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall StorageService::ResetStoragePolicySettings(StorageService *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  const unsigned __int16 * near **i; // rsi
  unsigned int v4; // r14d
  int v5; // eax
  __int64 v6; // rcx
  HRESULT v7; // eax
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64 *); // rbx
  int v11; // eax
  int v12; // eax
  unsigned int j; // r15d
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, GUID *, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, LPCWSTR *); // rbx
  int v19; // eax
  __int64 v20; // rcx
  int ppv; // [rsp+20h] [rbp-E0h]
  __int64 v23; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v25; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v28; // [rsp+58h] [rbp-A8h] BYREF
  int v29; // [rsp+5Ch] [rbp-A4h] BYREF
  LPCWSTR lpSubKey; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int64 v32; // [rsp+70h] [rbp-90h]
  WCHAR ValueName[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  hKey = 0;
  v1 = OpenStorageRegKey(HKEY_CURRENT_USER, (wchar_t *)L"StoragePolicy", &hKey);
  v2 = v1;
  if ( v1 >= 0 )
  {
    for ( i = (const unsigned __int16 * near **)qword_18008E530; ; i += 3 )
    {
      if ( i == &SystemWellKnownPaths )
      {
        v2 = 0;
        goto LABEL_28;
      }
      v4 = *(_DWORD *)i;
      v5 = StringCchPrintfW(ValueName, 0x104u, L"%02d", (unsigned int)(1 << *(_DWORD *)i));
      v2 = v5;
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAB,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
          (const char *)(unsigned int)v5,
          ppv);
        goto LABEL_28;
      }
      v29 = 0;
      if ( v4 == 1 || v4 == 7 )
        break;
      RegDeleteKeyValueW(hKey, 0, ValueName);
      StorageService::GetStoragePolicySettings(v6, v4, 0, &v29);
LABEL_19:
      ;
    }
    v25 = 0;
    v26 = 0;
    v23 = 0;
    v24 = 0;
    lpSubKey = 0;
    v31 = 0;
    v32 = 0;
    v28 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
    v7 = CoCreateInstance(&stru_1800956D8, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &v25);
    v2 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBB,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
        (const char *)(unsigned int)v7,
        ppv);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
    }
    else
    {
      v8 = Microsoft::WRL::ComPtr<ISyncRootManager>::As<ISyncRootManagerPriv>(
             (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v25,
             (__int64)&v26);
      v2 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBC,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
          (const char *)(unsigned int)v8,
          ppv);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
      }
      else
      {
        v9 = v26;
        v10 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 24LL);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
        v11 = v10(v9, &v23);
        v2 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBD,
            (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
            (const char *)(unsigned int)v11,
            ppv);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
        }
        else
        {
          v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v23 + 24LL))(v23, &v28);
          v2 = v12;
          if ( v12 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xBE,
              (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
              (const char *)(unsigned int)v12,
              ppv);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
          }
          else
          {
            for ( j = 0; ; ++j )
            {
              if ( j >= v28 )
              {
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
                goto LABEL_19;
              }
              v14 = v23;
              v15 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v23 + 32LL);
              Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
              v16 = v15(v14, j, &GUID_ca01c124_2769_4576_bf12_8a54ee671a86, &v24);
              v2 = v16;
              if ( v16 < 0 )
                break;
              v17 = v24;
              v18 = *(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v24 + 24LL);
              Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
              v31 = -1;
              v32 = -1;
              v19 = v18(v17, &lpSubKey);
              v2 = v19;
              if ( v19 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xC3,
                  (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
                  (const char *)(unsigned int)v19,
                  ppv);
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
                Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
                goto LABEL_28;
              }
              RegDeleteKeyValueW(hKey, lpSubKey, ValueName);
              StorageService::GetStoragePolicySettings(v20, v4, lpSubKey, &v29);
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC2,
              (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
              (const char *)(unsigned int)v16,
              ppv);
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpSubKey);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v24);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v26);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
          }
        }
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA6,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)v1,
      ppv);
  }
LABEL_28:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v2;
}

```

## disassembly

```asm
0x180031660  push    rbp
0x180031662  push    rbx
0x180031663  push    rsi
0x180031664  push    rdi
0x180031665  push    r14
0x180031667  push    r15
0x180031669  lea     rbp, [rsp-1A8h]
0x180031671  sub     rsp, 2A8h
0x180031678  mov     rax, cs:__security_cookie
0x18003167f  xor     rax, rsp
0x180031682  mov     [rbp+1D0h+var_40], rax
0x180031689  mov     [rsp+2D0h+hKey], 0
0x180031692  mov     rbx, [rsp+2D0h+hKey]
0x180031697  test    rbx, rbx
0x18003169a  jz      short loc_1800316BB
0x18003169c  lea     rcx, [rsp+2D0h+var_258]; this
0x1800316a1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800316a6  nop
0x1800316a7  mov     rcx, rbx; hKey
0x1800316aa  call    cs:__imp_RegCloseKey
0x1800316b0  nop
0x1800316b1  lea     rcx, [rsp+2D0h+var_258]; this
0x1800316b6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800316bb  mov     [rsp+2D0h+hKey], 0
0x1800316c4  lea     r8, [rsp+2D0h+hKey]; phkResult
0x1800316c9  lea     rdx, aStoragepolicy; "StoragePolicy"
0x1800316d0  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800316d7  call    ?OpenStorageRegKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z; OpenStorageRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x1800316dc  mov     ebx, eax
0x1800316de  test    eax, eax
0x1800316e0  jns     short loc_180031703
0x1800316e2  mov     rcx, [rbp+1D8h]; this
0x1800316e9  mov     r9d, eax; char *
0x1800316ec  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x1800316f3  mov     edx, 0A6h; void *
0x1800316f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800316fd  nop
0x1800316fe  jmp     loc_180031B83
0x180031703  lea     rsi, qword_18008E530
0x18003170a  lea     rax, ?SystemWellKnownPaths@@3PAPEBGA; ushort const * near * SystemWellKnownPaths
0x180031711  cmp     rsi, rax
0x180031714  jz      loc_180031B81
0x18003171a  mov     r14d, [rsi]
0x18003171d  mov     ecx, r14d
0x180031720  mov     r9d, 1
0x180031726  shl     r9d, cl
0x180031729  lea     r8, a02d; "%02d"
0x180031730  mov     edx, 104h; unsigned __int64
0x180031735  lea     rcx, [rbp+1D0h+ValueName]; unsigned __int16 *
0x180031739  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003173e  mov     ebx, eax
0x180031740  test    eax, eax
0x180031742  js      loc_180031B63
0x180031748  mov     [rsp+2D0h+var_274], 0
0x180031750  cmp     r14d, 1
0x180031754  jz      short loc_180031782
0x180031756  cmp     r14d, 7
0x18003175a  jz      short loc_180031782
0x18003175c  lea     r8, [rbp+1D0h+ValueName]; lpValueName
0x180031760  xor     edx, edx; lpSubKey
0x180031762  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180031767  call    cs:__imp_RegDeleteKeyValueW
0x18003176d  lea     r9, [rsp+2D0h+var_274]
0x180031772  xor     r8d, r8d
0x180031775  mov     edx, r14d
0x180031778  call    ?GetStoragePolicySettings@StorageService@@QEAAJW4_STORAGE_POLICY@@PEBGPEAK@Z; StorageService::GetStoragePolicySettings(_STORAGE_POLICY,ushort const *,ulong *)
0x18003177d  jmp     loc_180031950
0x180031782  mov     [rsp+2D0h+var_290], 0
0x18003178b  mov     [rsp+2D0h+var_288], 0
0x180031794  mov     [rsp+2D0h+var_2A0], 0
0x18003179d  mov     [rsp+2D0h+var_298], 0
0x1800317a6  mov     [rsp+2D0h+lpSubKey], 0
0x1800317af  mov     [rsp+2D0h+var_268], 0
0x1800317b8  mov     [rsp+2D0h+var_260], 0
0x1800317c1  mov     [rsp+2D0h+var_278], 0
0x1800317c9  lea     rcx, [rsp+2D0h+var_290]
0x1800317ce  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800317d3  lea     rax, [rsp+2D0h+var_290]
0x1800317d8  mov     qword ptr [rsp+2D0h+ppv], rax; int
0x1800317dd  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x1800317e4  xor     edx, edx; pUnkOuter
0x1800317e6  lea     r8d, [rdx+1]; dwClsContext
0x1800317ea  lea     rcx, stru_1800956D8; rclsid
0x1800317f1  call    cs:__imp_CoCreateInstance
0x1800317f7  mov     ebx, eax
0x1800317f9  test    eax, eax
0x1800317fb  js      loc_180031B0E
0x180031801  lea     rdx, [rsp+2D0h+var_288]
0x180031806  lea     rcx, [rsp+2D0h+var_290]
0x18003180b  call    ??$As@UISyncRootManagerPriv@@@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISyncRootManagerPriv@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ISyncRootManager>::As<ISyncRootManagerPriv>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ISyncRootManagerPriv>>)
0x180031810  mov     ebx, eax
0x180031812  test    eax, eax
0x180031814  js      loc_180031AB9
0x18003181a  mov     rdi, [rsp+2D0h+var_288]
0x18003181f  mov     rax, [rdi]
0x180031822  mov     rbx, [rax+18h]
0x180031826  lea     rcx, [rsp+2D0h+var_2A0]
0x18003182b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031830  lea     rdx, [rsp+2D0h+var_2A0]
0x180031835  mov     rcx, rdi
0x180031838  mov     rax, rbx
0x18003183b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031840  mov     ebx, eax
0x180031842  test    eax, eax
0x180031844  js      loc_180031A61
0x18003184a  mov     rcx, [rsp+2D0h+var_2A0]
0x18003184f  mov     rax, [rcx]
0x180031852  lea     rdx, [rsp+2D0h+var_278]
0x180031857  mov     rax, [rax+18h]
0x18003185b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031860  mov     ebx, eax
0x180031862  test    eax, eax
0x180031864  js      loc_180031A09
0x18003186a  xor     r15d, r15d
0x18003186d  cmp     r15d, [rsp+2D0h+var_278]
0x180031872  jnb     loc_18003191A
0x180031878  mov     rdi, [rsp+2D0h+var_2A0]
0x18003187d  mov     rax, [rdi]
0x180031880  mov     rbx, [rax+20h]
0x180031884  lea     rcx, [rsp+2D0h+var_298]
0x180031889  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003188e  lea     r9, [rsp+2D0h+var_298]
0x180031893  lea     r8, _GUID_ca01c124_2769_4576_bf12_8a54ee671a86
0x18003189a  mov     edx, r15d
0x18003189d  mov     rcx, rdi
0x1800318a0  mov     rax, rbx
0x1800318a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318a8  mov     ebx, eax
0x1800318aa  test    eax, eax
0x1800318ac  js      loc_1800319B1
0x1800318b2  mov     rdi, [rsp+2D0h+var_298]
0x1800318b7  mov     rax, [rdi]
0x1800318ba  mov     rbx, [rax+18h]
0x1800318be  lea     rcx, [rsp+2D0h+lpSubKey]
0x1800318c3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800318c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800318cc  mov     [rsp+2D0h+var_268], rax
0x1800318d1  mov     [rsp+2D0h+var_260], rax
0x1800318d6  lea     rdx, [rsp+2D0h+lpSubKey]
0x1800318db  mov     rcx, rdi
0x1800318de  mov     rax, rbx
0x1800318e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318e6  mov     ebx, eax
0x1800318e8  test    eax, eax
0x1800318ea  js      short loc_180031959
0x1800318ec  lea     r8, [rbp+1D0h+ValueName]; lpValueName
0x1800318f0  mov     rdx, [rsp+2D0h+lpSubKey]; lpSubKey
0x1800318f5  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800318fa  call    cs:__imp_RegDeleteKeyValueW
0x180031900  lea     r9, [rsp+2D0h+var_274]
0x180031905  mov     r8, [rsp+2D0h+lpSubKey]
0x18003190a  mov     edx, r14d
0x18003190d  call    ?GetStoragePolicySettings@StorageService@@QEAAJW4_STORAGE_POLICY@@PEBGPEAK@Z; StorageService::GetStoragePolicySettings(_STORAGE_POLICY,ushort const *,ulong *)
0x180031912  inc     r15d
0x180031915  jmp     loc_18003186D
0x18003191a  lea     rcx, [rsp+2D0h+lpSubKey]
0x18003191f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180031924  nop
0x180031925  lea     rcx, [rsp+2D0h+var_298]
0x18003192a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003192f  nop
0x180031930  lea     rcx, [rsp+2D0h+var_2A0]
0x180031935  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003193a  nop
0x18003193b  lea     rcx, [rsp+2D0h+var_288]
0x180031940  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031945  nop
0x180031946  lea     rcx, [rsp+2D0h+var_290]
0x18003194b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031950  add     rsi, 18h
0x180031954  jmp     loc_18003170A
0x180031959  mov     rcx, [rbp+1D8h]; this
0x180031960  mov     r9d, eax; char *
0x180031963  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18003196a  mov     edx, 0C3h; void *
0x18003196f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031974  nop
0x180031975  lea     rcx, [rsp+2D0h+lpSubKey]
0x18003197a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003197f  nop
0x180031980  lea     rcx, [rsp+2D0h+var_298]
0x180031985  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18003198a  nop
0x18003198b  lea     rcx, [rsp+2D0h+var_2A0]
0x180031990  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031995  nop
0x180031996  lea     rcx, [rsp+2D0h+var_288]
0x18003199b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800319a0  nop
0x1800319a1  lea     rcx, [rsp+2D0h+var_290]
0x1800319a6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800319ab  nop
0x1800319ac  jmp     loc_180031B83
0x1800319b1  mov     rcx, [rbp+1D8h]; this
0x1800319b8  mov     r9d, eax; char *
0x1800319bb  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x1800319c2  mov     edx, 0C2h; void *
0x1800319c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800319cc  nop
0x1800319cd  lea     rcx, [rsp+2D0h+lpSubKey]
0x1800319d2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800319d7  nop
0x1800319d8  lea     rcx, [rsp+2D0h+var_298]
0x1800319dd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800319e2  nop
0x1800319e3  lea     rcx, [rsp+2D0h+var_2A0]
0x1800319e8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800319ed  nop
0x1800319ee  lea     rcx, [rsp+2D0h+var_288]
0x1800319f3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800319f8  nop
0x1800319f9  lea     rcx, [rsp+2D0h+var_290]
0x1800319fe  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031a03  nop
0x180031a04  jmp     loc_180031B83
0x180031a09  mov     rcx, [rbp+1D8h]; this
0x180031a10  mov     r9d, eax; char *
0x180031a13  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180031a1a  mov     edx, 0BEh; void *
0x180031a1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031a24  nop
0x180031a25  lea     rcx, [rsp+2D0h+lpSubKey]
0x180031a2a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180031a2f  nop
0x180031a30  lea     rcx, [rsp+2D0h+var_298]
0x180031a35  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031a3a  nop
0x180031a3b  lea     rcx, [rsp+2D0h+var_2A0]
0x180031a40  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031a45  nop
0x180031a46  lea     rcx, [rsp+2D0h+var_288]
0x180031a4b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031a50  nop
0x180031a51  lea     rcx, [rsp+2D0h+var_290]
0x180031a56  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031a5b  nop
0x180031a5c  jmp     loc_180031B83
0x180031a61  mov     rcx, [rbp+1D8h]; this
0x180031a68  mov     r9d, eax; char *
0x180031a6b  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180031a72  mov     edx, 0BDh; void *
0x180031a77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031a7c  nop
0x180031a7d  lea     rcx, [rsp+2D0h+lpSubKey]
0x180031a82  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180031a87  nop
0x180031a88  lea     rcx, [rsp+2D0h+var_298]
0x180031a8d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031a92  nop
0x180031a93  lea     rcx, [rsp+2D0h+var_2A0]
0x180031a98  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031a9d  nop
0x180031a9e  lea     rcx, [rsp+2D0h+var_288]
0x180031aa3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031aa8  nop
0x180031aa9  lea     rcx, [rsp+2D0h+var_290]
0x180031aae  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031ab3  nop
0x180031ab4  jmp     loc_180031B83
0x180031ab9  mov     rcx, [rbp+1D8h]; this
0x180031ac0  mov     r9d, eax; char *
0x180031ac3  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180031aca  mov     edx, 0BCh; void *
0x180031acf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031ad4  nop
0x180031ad5  lea     rcx, [rsp+2D0h+lpSubKey]
0x180031ada  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180031adf  nop
0x180031ae0  lea     rcx, [rsp+2D0h+var_298]
0x180031ae5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031aea  nop
0x180031aeb  lea     rcx, [rsp+2D0h+var_2A0]
0x180031af0  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031af5  nop
0x180031af6  lea     rcx, [rsp+2D0h+var_288]
0x180031afb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031b00  nop
0x180031b01  lea     rcx, [rsp+2D0h+var_290]
0x180031b06  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031b0b  nop
0x180031b0c  jmp     short loc_180031B83
0x180031b0e  mov     rcx, [rbp+1D8h]; this
0x180031b15  mov     r9d, eax; char *
0x180031b18  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180031b1f  mov     edx, 0BBh; void *
0x180031b24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031b29  nop
0x180031b2a  lea     rcx, [rsp+2D0h+lpSubKey]
0x180031b2f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180031b34  nop
0x180031b35  lea     rcx, [rsp+2D0h+var_298]
0x180031b3a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031b3f  nop
0x180031b40  lea     rcx, [rsp+2D0h+var_2A0]
0x180031b45  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031b4a  nop
0x180031b4b  lea     rcx, [rsp+2D0h+var_288]
0x180031b50  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180031b55  nop
0x180031b56  lea     rcx, [rsp+2D0h+var_290]
  ... truncated ...
```
