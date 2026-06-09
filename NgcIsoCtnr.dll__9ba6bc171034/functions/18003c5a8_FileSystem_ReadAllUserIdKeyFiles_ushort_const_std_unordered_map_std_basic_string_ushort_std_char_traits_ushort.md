# FileSystem::ReadAllUserIdKeyFiles(ushort const *,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Properties::UserIdKey,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Properties::UserIdKey>>> *)

- ea: `0x18003c5a8`
- end: `0x18003ca38`
- name: `?ReadAllUserIdKeyFiles@FileSystem@@YAJPEBGPEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@@std@@@2@@std@@@Z`
- size: `1168`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019bf0`

## callees

- `0x180007670`
- `0x1800084c8`
- `0x18000d60c`
- `0x18000d62c`
- `0x1800103b0`
- `0x180010750`
- `0x180010ac0`
- `0x180011c1c`
- `0x180011c5c`
- `0x180011c9c`
- `0x180013088`
- `0x1800163e8`
- `0x18001cb98`
- `0x18001cbe8`
- `0x18001d000`
- `0x18001e564`
- `0x1800353cc`
- `0x1800354c8`
- `0x180037188`
- `0x180038d14`
- `0x18003b374`
- `0x18003b428`
- `0x18003b65c`
- `0x18003c23c`
- `0x18003c5a8`
- `0x18003d0dc`
- `0x1800404a4`
- `0x1800713cc`
- `0x180072c40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c96f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c96f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003c934`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003c934`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18003c71e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18003c71e`

## string_xrefs

- `0x18003c67b`: `*.json`
- `0x18003c653`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\filesystem.cpp`
- `0x18003c6cb`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\filesystem.cpp`
- `0x18003c7aa`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\filesystem.cpp`
- `0x18003c82e`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\filesystem.cpp`
- `0x18003c985`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\filesystem.cpp`
- `0x18003c5db`: `NgcIsoContainerReadAllUserIdKeyFiles`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall FileSystem::ReadAllUserIdKeyFiles(int a1, __int64 a2)
{
  __int64 v2; // r14
  __m128i si128; // xmm6
  int KeysDirectoryPath; // eax
  unsigned int LastError; // ebx
  int v7; // eax
  const WCHAR *v8; // rax
  char *FirstFile; // rbx
  int v10; // eax
  int v11; // esi
  const WCHAR *v12; // rcx
  int File; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  _QWORD *v17; // rax
  const char *v18; // r9
  const char *v19; // r9
  int lpSearchFilter; // [rsp+20h] [rbp-608h]
  int lpSearchFiltera; // [rsp+20h] [rbp-608h]
  char *v23; // [rsp+30h] [rbp-5F8h] BYREF
  __int64 v24; // [rsp+38h] [rbp-5F0h]
  _QWORD v25[2]; // [rsp+40h] [rbp-5E8h] BYREF
  __int128 v26; // [rsp+50h] [rbp-5D8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-5C8h]
  _QWORD v28[2]; // [rsp+68h] [rbp-5C0h] BYREF
  char v29[8]; // [rsp+78h] [rbp-5B0h] BYREF
  char v30[16]; // [rsp+80h] [rbp-5A8h] BYREF
  _QWORD v31[8]; // [rsp+90h] [rbp-598h] BYREF
  char v32[16]; // [rsp+D0h] [rbp-558h] BYREF
  _BYTE v33[56]; // [rsp+E0h] [rbp-548h] BYREF
  __int64 v34; // [rsp+118h] [rbp-510h]
  _OWORD v35[2]; // [rsp+120h] [rbp-508h] BYREF
  _OWORD v36[2]; // [rsp+140h] [rbp-4E8h] BYREF
  _OWORD v37[2]; // [rsp+160h] [rbp-4C8h] BYREF
  _BYTE v38[32]; // [rsp+180h] [rbp-4A8h] BYREF
  _BYTE v39[176]; // [rsp+1A0h] [rbp-488h] BYREF
  _QWORD v40[42]; // [rsp+250h] [rbp-3D8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+3A0h] [rbp-288h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+628h] [rbp+0h]

  v2 = a2;
  v24 = a2;
  wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v40);
  v40[0] = &LogProvider::NgcIsoContainerReadAllUserIdKeyFiles::`vftable';
  LogProvider::NgcIsoContainerReadAllUserIdKeyFiles::StartActivity((LogProvider::NgcIsoContainerReadAllUserIdKeyFiles *)v40);
  v36[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v36[1] = si128;
  LOWORD(v36[0]) = 0;
  KeysDirectoryPath = FileSystem::GetKeysDirectoryPath(a1);
  LastError = KeysDirectoryPath;
  if ( KeysDirectoryPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x217,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\filesystem.cpp",
      (const char *)(unsigned int)KeysDirectoryPath,
      lpSearchFilter);
LABEL_17:
    std::wstring::_Tidy_deallocate(v36);
    LogProvider::NgcIsoContainerReadAllUserIdKeyFiles::~NgcIsoContainerReadAllUserIdKeyFiles((LogProvider::NgcIsoContainerReadAllUserIdKeyFiles *)v40);
    return LastError;
  }
  v25[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
  v25[1] = L"*.json";
  v35[0] = 0;
  v35[1] = si128;
  LOWORD(v35[0]) = 0;
  v7 = NgcUtils::ComposePath(v25, 2, v35);
  LastError = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x223,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\filesystem.cpp",
      (const char *)(unsigned int)v7,
      lpSearchFilter);
LABEL_16:
    std::wstring::_Tidy_deallocate(v35);
    goto LABEL_17;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v35);
  FirstFile = (char *)FindFirstFileExW(v8, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
  v23 = FirstFile;
  if ( (unsigned __int64)(FirstFile - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( GetLastError() - 2 > 1 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x23A,
                    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\filesystem.cpp",
                    v19);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v23);
      goto LABEL_16;
    }
    std::_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>::clear(v2);
  }
  else
  {
    std::unordered_map<std::wstring,Properties::UserIdKey>::unordered_map<std::wstring,Properties::UserIdKey>(v31);
    do
    {
      v28[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v36);
      v28[1] = FindFileData.cFileName;
      v37[0] = 0;
      v37[1] = si128;
      LOWORD(v37[0]) = 0;
      v10 = NgcUtils::ComposePath(v28, 2, v37);
      v11 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x24A,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\filesystem.cpp",
          (const char *)(unsigned int)v10,
          lpSearchFiltera);
        std::wstring::_Tidy_deallocate(v37);
        std::_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>(v31);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v23);
        std::wstring::_Tidy_deallocate(v35);
        LastError = v11;
        goto LABEL_17;
      }
      v26 = 0;
      v27 = 0;
      v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v37);
      File = NgcUtils::ReadFile(v12, (__int64)&v26);
      if ( File < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x24F,
          (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\filesystem.cpp",
          (const char *)(unsigned int)File,
          lpSearchFiltera);
      if ( (_QWORD)v26 != *((_QWORD *)&v26 + 1) )
      {
        try
        {
          v25[0] = v33;
          v34 = 0;
          v14 = std::string::string(v38);
          v15 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::parse<std::string>(
                  (__int64)v29,
                  v14,
                  (__int64)v33);
          nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::operator<Properties::UserIdKey,0> Properties::UserIdKey(
            v15,
            (Properties::UserIdKey *)v39);
          LOBYTE(v16) = v29[0];
          nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
            v30,
            v16);
          std::string::_Tidy_deallocate(v38);
          v17 = (_QWORD *)std::_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>::_Try_emplace<std::wstring const &,>(
                            v31,
                            (__int64)v32,
                            (__int64)v39);
          Properties::UserIdKey::operator=(*v17 + 48LL, v39);
          Properties::UserIdKey::~UserIdKey((Properties::UserIdKey *)v39);
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x261,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\filesystem.cpp",
            v18);
          FirstFile = v23;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          v2 = v24;
        }
      }
      std::vector<unsigned char>::_Tidy(&v26);
      std::wstring::_Tidy_deallocate(v37);
    }
    while ( FindNextFileW(FirstFile, &FindFileData) );
    std::_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>::operator=(
      v2,
      v31);
    wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v40);
    std::_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>(v31);
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v23);
  std::wstring::_Tidy_deallocate(v35);
  std::wstring::_Tidy_deallocate(v36);
  LogProvider::NgcIsoContainerReadAllUserIdKeyFiles::~NgcIsoContainerReadAllUserIdKeyFiles((LogProvider::NgcIsoContainerReadAllUserIdKeyFiles *)v40);
  return 0;
}

```

## disassembly

```asm
0x18003c5a8  mov     rax, rsp
0x18003c5ab  mov     [rax+18h], rbx
0x18003c5af  push    rsi
0x18003c5b0  push    rdi
0x18003c5b1  push    r14
0x18003c5b3  sub     rsp, 610h
0x18003c5ba  movaps  xmmword ptr [rax-28h], xmm6
0x18003c5be  mov     rax, cs:__security_cookie
0x18003c5c5  xor     rax, rsp
0x18003c5c8  mov     [rsp+628h+var_38], rax
0x18003c5d0  mov     r14, rdx
0x18003c5d3  mov     rbx, rcx
0x18003c5d6  mov     [rsp+628h+var_5F0], rdx
0x18003c5db  lea     rdx, aNgcisocontaine_30; "NgcIsoContainerReadAllUserIdKeyFiles"
0x18003c5e2  lea     rcx, [rsp+628h+var_3D8]; struct wil::details::IFailureCallback *
0x18003c5ea  call    ??0?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18003c5ef  lea     rax, ??_7NgcIsoContainerReadAllUserIdKeyFiles@LogProvider@@6B@; const LogProvider::NgcIsoContainerReadAllUserIdKeyFiles::`vftable'
0x18003c5f6  mov     [rsp+628h+var_3D8], rax
0x18003c5fe  lea     rcx, [rsp+628h+var_3D8]; this
0x18003c606  call    ?StartActivity@NgcIsoContainerReadAllUserIdKeyFiles@LogProvider@@QEAAXXZ; LogProvider::NgcIsoContainerReadAllUserIdKeyFiles::StartActivity(void)
0x18003c60b  nop
0x18003c60c  xorps   xmm0, xmm0
0x18003c60f  movups  [rsp+628h+var_4E8], xmm0
0x18003c617  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18003c61f  movdqu  [rsp+628h+var_4D8], xmm6
0x18003c628  xor     edi, edi
0x18003c62a  mov     word ptr [rsp+628h+var_4E8], di
0x18003c632  lea     rdx, [rsp+628h+var_4E8]
0x18003c63a  mov     rcx, rbx; int
0x18003c63d  call    FileSystem__GetKeysDirectoryPath
0x18003c642  mov     ebx, eax
0x18003c644  test    eax, eax
0x18003c646  jns     short loc_18003C669
0x18003c648  mov     rcx, [rsp+628h]; this
0x18003c650  mov     r9d, eax; char *
0x18003c653  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003c65a  mov     edx, 217h; void *
0x18003c65f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c664  jmp     loc_18003C9B1
0x18003c669  lea     rcx, [rsp+628h+var_4E8]
0x18003c671  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003c676  mov     [rsp+628h+var_5E8], rax
0x18003c67b  lea     rax, aJson; "*.json"
0x18003c682  mov     [rsp+628h+var_5E0], rax
0x18003c687  xorps   xmm0, xmm0
0x18003c68a  movups  [rsp+628h+var_508], xmm0
0x18003c692  movdqu  [rsp+628h+var_4F8], xmm6
0x18003c69b  mov     word ptr [rsp+628h+var_508], di
0x18003c6a3  lea     r8, [rsp+628h+var_508]
0x18003c6ab  mov     edx, 2
0x18003c6b0  lea     rcx, [rsp+628h+var_5E8]
0x18003c6b5  call    ?ComposePath@NgcUtils@@YAJQEBQEBGKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::ComposePath(ushort const * const * const,ulong,std::wstring *)
0x18003c6ba  mov     ebx, eax
0x18003c6bc  test    eax, eax
0x18003c6be  jns     short loc_18003C6E1
0x18003c6c0  mov     rcx, [rsp+628h]; this
0x18003c6c8  mov     r9d, eax; char *
0x18003c6cb  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003c6d2  mov     edx, 223h; void *
0x18003c6d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c6dc  jmp     loc_18003C9A3
0x18003c6e1  xor     edx, edx; Val
0x18003c6e3  mov     r8d, 250h; Size
0x18003c6e9  lea     rcx, [rsp+628h+FindFileData]; void *
0x18003c6f1  call    memset_0
0x18003c6f6  lea     rcx, [rsp+628h+var_508]
0x18003c6fe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003c703  mov     rcx, rax; lpFileName
0x18003c706  mov     [rsp+628h+dwAdditionalFlags], edi; dwAdditionalFlags
0x18003c70a  mov     [rsp+628h+lpSearchFilter], rdi; int
0x18003c70f  xor     r9d, r9d; fSearchOp
0x18003c712  lea     r8, [rsp+628h+FindFileData]; lpFindFileData
0x18003c71a  lea     edx, [r9+1]; fInfoLevelId
0x18003c71e  call    cs:__imp_FindFirstFileExW
0x18003c724  mov     rbx, rax
0x18003c727  mov     [rsp+628h+var_5F8], rax
0x18003c72c  dec     rax
0x18003c72f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003c733  ja      loc_18003C96F
0x18003c739  lea     rcx, [rsp+628h+var_598]
0x18003c741  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,Properties::UserIdKey>::unordered_map<std::wstring,Properties::UserIdKey>(void)
0x18003c746  nop
0x18003c747  lea     rcx, [rsp+628h+var_4E8]
0x18003c74f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003c754  mov     [rsp+628h+var_5C0], rax
0x18003c759  lea     rax, [rsp+628h+var_25C]
0x18003c761  mov     [rsp+628h+var_5B8], rax
0x18003c766  xorps   xmm0, xmm0
0x18003c769  movups  [rsp+628h+var_4C8], xmm0
0x18003c771  movdqu  [rsp+628h+var_4B8], xmm6
0x18003c77a  mov     word ptr [rsp+628h+var_4C8], di
0x18003c782  lea     r8, [rsp+628h+var_4C8]
0x18003c78a  mov     edx, 2
0x18003c78f  lea     rcx, [rsp+628h+var_5C0]
0x18003c794  call    ?ComposePath@NgcUtils@@YAJQEBQEBGKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::ComposePath(ushort const * const * const,ulong,std::wstring *)
0x18003c799  mov     esi, eax
0x18003c79b  test    eax, eax
0x18003c79d  jns     short loc_18003C7F7
0x18003c79f  mov     rcx, [rsp+628h]; this
0x18003c7a7  mov     r9d, eax; char *
0x18003c7aa  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003c7b1  mov     edx, 24Ah; void *
0x18003c7b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c7bb  nop
0x18003c7bc  lea     rcx, [rsp+628h+var_4C8]
0x18003c7c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c7c9  nop
0x18003c7ca  lea     rcx, [rsp+628h+var_598]
0x18003c7d2  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>(void)
0x18003c7d7  nop
0x18003c7d8  lea     rcx, [rsp+628h+var_5F8]
0x18003c7dd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18003c7e2  nop
0x18003c7e3  lea     rcx, [rsp+628h+var_508]
0x18003c7eb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c7f0  mov     ebx, esi
0x18003c7f2  jmp     loc_18003C9B1
0x18003c7f7  xorps   xmm0, xmm0
0x18003c7fa  movdqu  [rsp+628h+var_5D8], xmm0
0x18003c800  mov     [rsp+628h+var_5C8], rdi
0x18003c805  lea     rcx, [rsp+628h+var_4C8]
0x18003c80d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003c812  mov     rcx, rax
0x18003c815  lea     rdx, [rsp+628h+var_5D8]
0x18003c81a  call    ?ReadFile@NgcUtils@@YAJPEBGPEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcUtils::ReadFile(ushort const *,std::vector<uchar> *)
0x18003c81f  mov     rcx, [rsp+628h]; this
0x18003c827  test    eax, eax
0x18003c829  jns     short loc_18003C83F
0x18003c82b  mov     r9d, eax; char *
0x18003c82e  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003c835  mov     edx, 24Fh; void *
0x18003c83a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c83f  mov     r8, qword ptr [rsp+628h+var_5D8+8]
0x18003c844  mov     rdx, qword ptr [rsp+628h+var_5D8]
0x18003c849  cmp     rdx, r8
0x18003c84c  jz      loc_18003C911
0x18003c852  lea     rax, [rsp+628h+var_548]
0x18003c85a  mov     [rsp+628h+var_5E8], rax
0x18003c85f  mov     [rsp+628h+var_510], rdi
0x18003c867  lea     rcx, [rsp+628h+var_4A8]
0x18003c86f  call    ??$?0PEBD$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD0AEBV?$allocator@D@1@@Z; std::string::string(char const *,char const *,std::allocator<char> const &)
0x18003c874  nop
0x18003c875  lea     r8, [rsp+628h+var_548]
0x18003c87d  mov     rdx, rax
0x18003c880  lea     rcx, [rsp+628h+var_5B0]
0x18003c885  call    ??$parse@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@SA?AV01@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$function@$$A6A_NHW4parse_event_t@detail@nlohmann@@AEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@3@@Z@3@_N2@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::parse<std::string>(std::string &&,std::function<bool (int,nlohmann::detail::parse_event_t,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> &)>,bool,bool)
0x18003c88a  nop
0x18003c88b  lea     rdx, [rsp+628h+var_488]
0x18003c893  mov     rcx, rax
0x18003c896  call    ??$?BUUserIdKey@Properties@@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBA?AUUserIdKey@Properties@@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::operator<Properties::UserIdKey,0> Properties::UserIdKey(void)
0x18003c89b  nop
0x18003c89c  mov     dl, [rsp+628h+var_5B0]
0x18003c8a0  lea     rcx, [rsp+628h+var_5A8]
0x18003c8a8  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18003c8ad  nop
0x18003c8ae  lea     rcx, [rsp+628h+var_4A8]
0x18003c8b6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003c8bb  lea     r8, [rsp+628h+var_488]
0x18003c8c3  lea     rdx, [rsp+628h+var_558]
0x18003c8cb  lea     rcx, [rsp+628h+var_598]
0x18003c8d3  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18003c8d8  mov     rcx, [rax]
0x18003c8db  add     rcx, 30h ; '0'
0x18003c8df  lea     rdx, [rsp+628h+var_488]
0x18003c8e7  call    ??4UserIdKey@Properties@@QEAAAEAU01@$$QEAU01@@Z; Properties::UserIdKey::operator=(Properties::UserIdKey &&)
0x18003c8ec  nop
0x18003c8ed  lea     rcx, [rsp+628h+var_488]; this
0x18003c8f5  call    ??1UserIdKey@Properties@@QEAA@XZ; Properties::UserIdKey::~UserIdKey(void)
0x18003c8fa  nop
0x18003c8fb  jmp     short loc_18003C911
0x18003c8fd  xor     edi, edi
0x18003c8ff  mov     rbx, [rsp+628h+var_5F8]
0x18003c904  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18003c90c  mov     r14, [rsp+628h+var_5F0]
0x18003c911  lea     rcx, [rsp+628h+var_5D8]
0x18003c916  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003c91b  nop
0x18003c91c  lea     rcx, [rsp+628h+var_4C8]
0x18003c924  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c929  lea     rdx, [rsp+628h+FindFileData]; lpFindFileData
0x18003c931  mov     rcx, rbx; hFindFile
0x18003c934  call    cs:__imp_FindNextFileW
0x18003c93a  test    eax, eax
0x18003c93c  jnz     loc_18003C747
0x18003c942  lea     rdx, [rsp+628h+var_598]
0x18003c94a  mov     rcx, r14
0x18003c94d  call    ??4?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@@std@@@2@$0A@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>::operator=(std::_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>> &&)
0x18003c952  lea     rcx, [rsp+628h+var_3D8]
0x18003c95a  call    ?Stop@?$ActivityBase@VLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18003c95f  nop
0x18003c960  lea     rcx, [rsp+628h+var_598]
0x18003c968  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>::~_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>(void)
0x18003c96d  jmp     short loc_18003C9D9
0x18003c96f  call    cs:__imp_GetLastError
0x18003c975  add     eax, 0FFFFFFFEh
0x18003c978  cmp     eax, 1
0x18003c97b  jbe     short loc_18003C9D0
0x18003c97d  mov     rcx, [rsp+628h]; this
0x18003c985  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003c98c  mov     edx, 23Ah; void *
0x18003c991  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c996  mov     ebx, eax
0x18003c998  lea     rcx, [rsp+628h+var_5F8]
0x18003c99d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18003c9a2  nop
0x18003c9a3  lea     rcx, [rsp+628h+var_508]
0x18003c9ab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c9b0  nop
0x18003c9b1  lea     rcx, [rsp+628h+var_4E8]
0x18003c9b9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c9be  nop
0x18003c9bf  lea     rcx, [rsp+628h+var_3D8]; this
0x18003c9c7  call    ??1NgcIsoContainerReadAllUserIdKeyFiles@LogProvider@@QEAA@XZ; LogProvider::NgcIsoContainerReadAllUserIdKeyFiles::~NgcIsoContainerReadAllUserIdKeyFiles(void)
0x18003c9cc  mov     eax, ebx
0x18003c9ce  jmp     short loc_18003CA0F
0x18003c9d0  mov     rcx, r14
0x18003c9d3  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UUserIdKey@Properties@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,Properties::UserIdKey,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Properties::UserIdKey>>,0>>::clear(void)
0x18003c9d8  nop
0x18003c9d9  lea     rcx, [rsp+628h+var_5F8]
0x18003c9de  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x18003c9e3  nop
0x18003c9e4  lea     rcx, [rsp+628h+var_508]
0x18003c9ec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c9f1  nop
0x18003c9f2  lea     rcx, [rsp+628h+var_4E8]
0x18003c9fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c9ff  nop
0x18003ca00  lea     rcx, [rsp+628h+var_3D8]; this
0x18003ca08  call    ??1NgcIsoContainerReadAllUserIdKeyFiles@LogProvider@@QEAA@XZ; LogProvider::NgcIsoContainerReadAllUserIdKeyFiles::~NgcIsoContainerReadAllUserIdKeyFiles(void)
0x18003ca0d  xor     eax, eax
0x18003ca0f  mov     rcx, [rsp+628h+var_38]
0x18003ca17  xor     rcx, rsp; StackCookie
0x18003ca1a  call    __security_check_cookie
0x18003ca1f  lea     r11, [rsp+628h+var_18]
0x18003ca27  mov     rbx, [r11+30h]
0x18003ca2b  movaps  xmm6, xmmword ptr [r11-10h]
0x18003ca30  mov     rsp, r11
0x18003ca33  pop     r14
0x18003ca35  pop     rdi
0x18003ca36  pop     rsi
0x18003ca37  retn
```
