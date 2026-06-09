# Windows::Networking::UX::Internal::MBMediaManager::_EnumAndCreateCategories(wil::write_lock_required)

- ea: `0x18001a1ec`
- end: `0x18001a48d`
- name: `?_EnumAndCreateCategories@MBMediaManager@Internal@UX@Networking@Windows@@AEAAJUwrite_lock_required@wil@@@Z`
- size: `673`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008da0`
- `0x18001c0cc`
- `0x180032940`

## callees

- `0x180002150`
- `0x180008c84`
- `0x180008f00`
- `0x180009150`
- `0x18000ad20`
- `0x18000bde0`
- `0x18000fe58`
- `0x180016ae8`
- `0x180016bb0`
- `0x180017ac4`
- `0x18001a1ec`
- `0x18001aeec`
- `0x18001b1d4`
- `0x18002cd20`
- `0x18003237c`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18001a424`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18001a463`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18001a424`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18001a463`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18001a233`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18001a233`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x18001a282`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x18001a282`

## string_xrefs

- `0x18001a329`: `Windows::Networking::UX::Internal::MBMediaManager::_EnumAndCreateCategories`
- `0x18001a382`: `Windows::Networking::UX::Internal::MBMediaManager::_EnumAndCreateCategories`
- `0x18001a3d2`: `Windows::Networking::UX::Internal::MBMediaManager::_EnumAndCreateCategories`
- `0x18001a3c6`: `_CreateUXCategory failed. `

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Networking::UX::Internal::MBMediaManager::_EnumAndCreateCategories(
        Windows::Networking::UX::Internal::MediaManagerBase *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int v4; // ebx
  __int64 v5; // rcx
  unsigned int *v6; // rdx
  __int64 v7; // rdx
  int v8; // edi
  int v9; // edi
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned int *v13; // rcx
  unsigned int v14; // [rsp+20h] [rbp-69h]
  __int64 v15; // [rsp+28h] [rbp-61h]
  unsigned int *v16; // [rsp+30h] [rbp-59h] BYREF
  struct Windows::Networking::UX::IUXCategory *v17; // [rsp+38h] [rbp-51h] BYREF
  __int64 v18; // [rsp+40h] [rbp-49h] BYREF
  int v19; // [rsp+48h] [rbp-41h] BYREF
  char v20[40]; // [rsp+50h] [rbp-39h] BYREF
  __int128 v21; // [rsp+78h] [rbp-11h] BYREF
  char v22; // [rsp+88h] [rbp-1h]
  __int128 v23; // [rsp+90h] [rbp+7h] BYREF
  _BYTE v24[19]; // [rsp+A0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v18 = -1;
  v19 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::reset(&v18);
  v2 = WwanOpenHandle(1, 0, &v19, &v18);
  if ( v2 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x63,
           (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbmediamanager.cpp",
           (const char *)v2,
           v14);
LABEL_19:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(&v18);
    return v3;
  }
  v16 = 0;
  v21 = (unsigned __int64)&v16;
  v22 = 1;
  v4 = WwanEnumerateInterfaces(v18, 0, (char *)&v21 + 8);
  wil::details::out_param_ptr_t<WWAN_INTERFACE_INFO_LIST * *,wistd::unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>::~out_param_ptr_t<WWAN_INTERFACE_INFO_LIST * *,wistd::unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>(&v21);
  if ( v4 )
  {
    if ( v4 != 632 )
    {
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x91,
             (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbmediamanager.cpp",
             (const char *)v4,
             v14);
      v13 = v16;
      v16 = 0;
      if ( v13 )
        WwanFreeMemory(v13);
      goto LABEL_19;
    }
    LODWORD(v17) = -2147024264;
    MBSettingUXLogging::InfoHRESULT<char const (&)[62],long>(v5, &v17);
    v6 = v16;
  }
  else
  {
    v6 = v16;
    if ( *v16 )
    {
      do
      {
        v17 = 0;
        v21 = *(_OWORD *)&v6[147 * v4 + 1];
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
        v8 = Windows::Networking::UX::Internal::MBMediaManager::_CreateUXCategory(a1, v7, &v21, &v17);
        if ( v8 < 0 )
        {
          v11 = MbLoggingHelperGuidToString(v20);
          v23 = *(_OWORD *)v11;
          *(_OWORD *)v24 = *(_OWORD *)(v11 + 16);
          *(_DWORD *)&v24[15] = *(_DWORD *)(v11 + 31);
          LODWORD(v15) = v8;
          MBSettingUXLogging::Warn(
            "Windows::Networking::UX::Internal::MBMediaManager::_EnumAndCreateCategories",
            133,
            "_CreateUXCategory failed. ",
            "Interface GUID=%hs, HRESULT=0x%x",
            &v23,
            v15);
        }
        else
        {
          v9 = Windows::Networking::UX::Internal::MediaManagerBase::_AddCategory(a1, v17);
          v10 = MbLoggingHelperGuidToString(v20);
          v23 = *(_OWORD *)v10;
          *(_OWORD *)v24 = *(_OWORD *)(v10 + 16);
          *(_DWORD *)&v24[15] = *(_DWORD *)(v10 + 31);
          if ( v9 < 0 )
          {
            LODWORD(v15) = v9;
            MBSettingUXLogging::Error(
              "Windows::Networking::UX::Internal::MBMediaManager::_EnumAndCreateCategories",
              0x7Fu,
              "Failed to Add Category. ",
              "Interface GUID=%hs, HRESULT=0x%x",
              &v23,
              v15);
          }
          else
          {
            MBSettingUXLogging::Info(
              "Windows::Networking::UX::Internal::MBMediaManager::_EnumAndCreateCategories",
              121,
              "Category added, Fire event for ChangeEventType_Added. Interface GUID=%hs",
              (const char *)&v23);
            Windows::Networking::UX::Internal::MBMediaManager::_FireCategoryEvent(a1, 0, &v21);
          }
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
        ++v4;
        v6 = v16;
      }
      while ( v4 < *v16 );
    }
  }
  v16 = 0;
  if ( v6 )
    WwanFreeMemory(v6);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(&v18);
  return 0;
}

```

## disassembly

```asm
0x18001a1ec  push    rbp
0x18001a1ee  push    rbx
0x18001a1ef  push    rsi
0x18001a1f0  push    rdi
0x18001a1f1  lea     rbp, [rsp-3Fh]
0x18001a1f6  sub     rsp, 0C8h
0x18001a1fd  mov     rax, cs:__security_cookie
0x18001a204  xor     rax, rsp
0x18001a207  mov     [rbp+57h+var_28], rax
0x18001a20b  mov     rsi, rcx
0x18001a20e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001a212  mov     [rbp+57h+var_A0], rdx
0x18001a216  mov     [rbp+57h+var_98], 0
0x18001a21d  lea     rcx, [rbp+57h+var_A0]
0x18001a221  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::reset(void *)
0x18001a226  lea     r9, [rbp+57h+var_A0]
0x18001a22a  lea     r8, [rbp+57h+var_98]
0x18001a22e  xor     edx, edx
0x18001a230  lea     ecx, [rdx+1]
0x18001a233  call    cs:__imp_WwanOpenHandle
0x18001a239  test    eax, eax
0x18001a23b  jz      short loc_18001A25C
0x18001a23d  mov     rcx, [rbp+5Fh]; this
0x18001a241  mov     r9d, eax; char *
0x18001a244  lea     r8, aOnecoreuapNetU_15; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001a24b  mov     edx, 63h ; 'c'; void *
0x18001a250  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001a255  mov     ebx, eax
0x18001a257  jmp     loc_18001A46A
0x18001a25c  mov     [rbp+57h+var_B0], 0
0x18001a264  lea     rax, [rbp+57h+var_B0]
0x18001a268  mov     qword ptr [rbp+57h+var_68], rax
0x18001a26c  mov     qword ptr [rbp+57h+var_68+8], 0
0x18001a274  mov     [rbp+57h+var_58], 1
0x18001a278  lea     r8, [rbp+57h+var_68+8]
0x18001a27c  xor     edx, edx
0x18001a27e  mov     rcx, [rbp+57h+var_A0]
0x18001a282  call    cs:__imp_WwanEnumerateInterfaces
0x18001a288  mov     ebx, eax
0x18001a28a  lea     rcx, [rbp+57h+var_68]
0x18001a28e  call    ??1?$out_param_ptr_t@PEAPEAUWWAN_INTERFACE_INFO_LIST@@V?$unique_ptr@UWWAN_INTERFACE_INFO_LIST@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<WWAN_INTERFACE_INFO_LIST * *,wistd::unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>::~out_param_ptr_t<WWAN_INTERFACE_INFO_LIST * *,wistd::unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>(void)
0x18001a293  test    ebx, ebx
0x18001a295  jnz     loc_18001A3F8
0x18001a29b  mov     rdx, [rbp+57h+var_B0]
0x18001a29f  cmp     [rdx], ebx
0x18001a2a1  jbe     loc_18001A414
0x18001a2a7  mov     eax, ebx
0x18001a2a9  imul    rcx, rax, 24Ch
0x18001a2b0  mov     [rbp+57h+var_A8], 0
0x18001a2b8  movups  xmm0, xmmword ptr [rcx+rdx+4]
0x18001a2bd  movdqu  [rbp+57h+var_68], xmm0
0x18001a2c2  lea     rcx, [rbp+57h+var_A8]
0x18001a2c6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a2cb  lea     r9, [rbp+57h+var_A8]
0x18001a2cf  lea     r8, [rbp+57h+var_68]
0x18001a2d3  mov     rcx, rsi
0x18001a2d6  call    ?_CreateUXCategory@MBMediaManager@Internal@UX@Networking@Windows@@AEAAJUread_lock_required@wil@@AEBU_GUID@@PEAPEAUIUXCategory@345@@Z; Windows::Networking::UX::Internal::MBMediaManager::_CreateUXCategory(wil::read_lock_required,_GUID const &,Windows::Networking::UX::IUXCategory * *)
0x18001a2db  mov     edi, eax
0x18001a2dd  test    eax, eax
0x18001a2df  js      loc_18001A390
0x18001a2e5  mov     rdx, [rbp+57h+var_A8]; struct Windows::Networking::UX::IUXCategory *
0x18001a2e9  mov     rcx, rsi; this
0x18001a2ec  call    ?_AddCategory@MediaManagerBase@Internal@UX@Networking@Windows@@IEAAJPEAUIUXCategory@345@@Z; Windows::Networking::UX::Internal::MediaManagerBase::_AddCategory(Windows::Networking::UX::IUXCategory *)
0x18001a2f1  mov     edi, eax
0x18001a2f3  lea     rdx, [rbp+57h+var_68]
0x18001a2f7  lea     rcx, [rbp+57h+var_90]; char *
0x18001a2fb  test    eax, eax
0x18001a2fd  js      short loc_18001A348
0x18001a2ff  call    ?MbLoggingHelperGuidToString@@YA?AV?$array@D$0CD@@std@@AEBU_GUID@@@Z; MbLoggingHelperGuidToString(_GUID const &)
0x18001a304  movups  xmm0, xmmword ptr [rax]
0x18001a307  movups  [rbp+57h+var_50], xmm0
0x18001a30b  movups  xmm1, xmmword ptr [rax+10h]
0x18001a30f  movups  xmmword ptr [rbp+57h+var_40], xmm1
0x18001a313  mov     eax, [rax+1Fh]
0x18001a316  mov     dword ptr [rbp+57h+var_40+0Fh], eax
0x18001a319  lea     r9, [rbp+57h+var_50]
0x18001a31d  lea     r8, aCategoryAddedF; "Category added, Fire event for ChangeEv"...
0x18001a324  mov     edx, 79h ; 'y'; unsigned int
0x18001a329  lea     rcx, aWindowsNetwork_202; "Windows::Networking::UX::Internal::MBMe"...
0x18001a330  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x18001a335  lea     r8, [rbp+57h+var_68]
0x18001a339  xor     edx, edx
0x18001a33b  mov     rcx, rsi
0x18001a33e  call    ?_FireCategoryEvent@MBMediaManager@Internal@UX@Networking@Windows@@AEAAJW4ChangeEventType@345@AEBU_GUID@@@Z; Windows::Networking::UX::Internal::MBMediaManager::_FireCategoryEvent(Windows::Networking::UX::ChangeEventType,_GUID const &)
0x18001a343  jmp     loc_18001A3DF
0x18001a348  call    ?MbLoggingHelperGuidToString@@YA?AV?$array@D$0CD@@std@@AEBU_GUID@@@Z; MbLoggingHelperGuidToString(_GUID const &)
0x18001a34d  movups  xmm0, xmmword ptr [rax]
0x18001a350  movups  [rbp+57h+var_50], xmm0
0x18001a354  movups  xmm1, xmmword ptr [rax+10h]
0x18001a358  movups  xmmword ptr [rbp+57h+var_40], xmm1
0x18001a35c  mov     eax, [rax+1Fh]
0x18001a35f  mov     dword ptr [rbp+57h+var_40+0Fh], eax
0x18001a362  mov     dword ptr [rsp+0E0h+var_B8], edi
0x18001a366  lea     rax, [rbp+57h+var_50]
0x18001a36a  mov     [rsp+0E0h+var_C0], rax
0x18001a36f  lea     r9, aInterfaceGuidH; "Interface GUID=%hs, HRESULT=0x%x"
0x18001a376  lea     r8, aFailedToAddCat_0; "Failed to Add Category. "
0x18001a37d  mov     edx, 7Fh; unsigned int
0x18001a382  lea     rcx, aWindowsNetwork_202; "Windows::Networking::UX::Internal::MBMe"...
0x18001a389  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x18001a38e  jmp     short loc_18001A3DF
0x18001a390  lea     rdx, [rbp+57h+var_68]
0x18001a394  lea     rcx, [rbp+57h+var_90]; char *
0x18001a398  call    ?MbLoggingHelperGuidToString@@YA?AV?$array@D$0CD@@std@@AEBU_GUID@@@Z; MbLoggingHelperGuidToString(_GUID const &)
0x18001a39d  movups  xmm0, xmmword ptr [rax]
0x18001a3a0  movups  [rbp+57h+var_50], xmm0
0x18001a3a4  movups  xmm1, xmmword ptr [rax+10h]
0x18001a3a8  movups  xmmword ptr [rbp+57h+var_40], xmm1
0x18001a3ac  mov     eax, [rax+1Fh]
0x18001a3af  mov     dword ptr [rbp+57h+var_40+0Fh], eax
0x18001a3b2  mov     dword ptr [rsp+0E0h+var_B8], edi
0x18001a3b6  lea     rax, [rbp+57h+var_50]
0x18001a3ba  mov     [rsp+0E0h+var_C0], rax
0x18001a3bf  lea     r9, aInterfaceGuidH; "Interface GUID=%hs, HRESULT=0x%x"
0x18001a3c6  lea     r8, aCreateuxcatego; "_CreateUXCategory failed. "
0x18001a3cd  mov     edx, 85h; unsigned int
0x18001a3d2  lea     rcx, aWindowsNetwork_202; "Windows::Networking::UX::Internal::MBMe"...
0x18001a3d9  call    ?Warn@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Warn(char const *,ulong,char const *,...)
0x18001a3de  nop
0x18001a3df  lea     rcx, [rbp+57h+var_A8]
0x18001a3e3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001a3e8  inc     ebx
0x18001a3ea  mov     rdx, [rbp+57h+var_B0]
0x18001a3ee  cmp     ebx, [rdx]
0x18001a3f0  jb      loc_18001A2A7
0x18001a3f6  jmp     short loc_18001A414
0x18001a3f8  cmp     ebx, 278h
0x18001a3fe  jnz     short loc_18001A438
0x18001a400  mov     dword ptr [rbp+57h+var_A8], 80070278h
0x18001a407  lea     rdx, [rbp+57h+var_A8]
0x18001a40b  call    ??$InfoHRESULT@AEAY0DO@$$CBDJ@MBSettingUXLogging@@SAXAEAY0DO@$$CBD$$QEAJ@Z; MBSettingUXLogging::InfoHRESULT<char const (&)[62],long>(char const (&)[62],long &&)
0x18001a410  mov     rdx, [rbp+57h+var_B0]
0x18001a414  mov     [rbp+57h+var_B0], 0
0x18001a41c  test    rdx, rdx
0x18001a41f  jz      short loc_18001A42B
0x18001a421  mov     rcx, rdx
0x18001a424  call    cs:__imp_WwanFreeMemory
0x18001a42a  nop
0x18001a42b  lea     rcx, [rbp+57h+var_A0]
0x18001a42f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
0x18001a434  xor     eax, eax
0x18001a436  jmp     short loc_18001A475
0x18001a438  mov     rcx, [rbp+5Fh]; this
0x18001a43c  mov     r9d, ebx; char *
0x18001a43f  lea     r8, aOnecoreuapNetU_15; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18001a446  mov     edx, 91h; void *
0x18001a44b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001a450  mov     ebx, eax
0x18001a452  mov     rcx, [rbp+57h+var_B0]
0x18001a456  mov     [rbp+57h+var_B0], 0
0x18001a45e  test    rcx, rcx
0x18001a461  jz      short loc_18001A46A
0x18001a463  call    cs:__imp_WwanFreeMemory
0x18001a469  nop
0x18001a46a  lea     rcx, [rbp+57h+var_A0]
0x18001a46e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseWwanHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAX_J$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::CloseWwanHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,__int64,-1,std::nullptr_t>>(void)
0x18001a473  mov     eax, ebx
0x18001a475  mov     rcx, [rbp+57h+var_28]
0x18001a479  xor     rcx, rsp; StackCookie
0x18001a47c  call    __security_check_cookie
0x18001a481  add     rsp, 0C8h
0x18001a488  pop     rdi
0x18001a489  pop     rsi
0x18001a48a  pop     rbx
0x18001a48b  pop     rbp
0x18001a48c  retn
```
