# NgcIsoPregenPool::LoadPregenKeys(void)

- ea: `0x180049478`
- end: `0x180049b81`
- name: `?LoadPregenKeys@NgcIsoPregenPool@@AEAAJXZ`
- size: `1801`
- prototype: `__int64 __fastcall(NgcIsoPregenPool *__hidden this)`
- caller_count: `1`
- callee_count: `38`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180049100`

## callees

- `0x180007670`
- `0x1800084c8`
- `0x18000a168`
- `0x18000b408`
- `0x18000d62c`
- `0x180011c1c`
- `0x180011c5c`
- `0x180011c9c`
- `0x180018388`
- `0x18001cb98`
- `0x18001cbe8`
- `0x18002ccf0`
- `0x1800353cc`
- `0x180038d14`
- `0x18003b374`
- `0x1800404a4`
- `0x180044678`
- `0x1800474c0`
- `0x180047c94`
- `0x180047f30`
- `0x1800480e8`
- `0x180048170`
- `0x1800483b4`
- `0x180048464`
- `0x1800484b8`
- `0x18004852c`
- `0x180049478`
- `0x18004a0e0`
- `0x18004a4fc`
- `0x18004aca4`
- `0x18004ce28`
- `0x18004d060`
- `0x18004d1cc`
- `0x1800543dc`
- `0x180066710`
- `0x1800713cc`
- `0x180072c40`
- `0x180073ef4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800499ff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800499ff`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180049ad4`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180049ad4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800495b0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x1800495b0`

## string_xrefs

- `0x180049504`: `*.json`
- `0x18004955d`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\pregenpool.cpp`
- `0x180049658`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\pregenpool.cpp`
- `0x1800496e5`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\pregenpool.cpp`
- `0x180049873`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\pregenpool.cpp`
- `0x180049935`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\pregenpool.cpp`
- `0x180049955`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\pregenpool.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall NgcIsoPregenPool::LoadPregenKeys(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // r13
  unsigned int v2; // r14d
  RTL_SRWLOCK *v3; // rdi
  __m128i si128; // xmm6
  int v5; // eax
  unsigned int LastErrorFailHr; // ebx
  const WCHAR *v7; // rax
  wil::details *v8; // rcx
  char *FirstFile; // rbx
  unsigned int v10; // r15d
  unsigned int v11; // r12d
  int v12; // eax
  const WCHAR *v13; // rcx
  int File; // eax
  __int64 v15; // rax
  __int64 v16; // r8
  __int64 v17; // rdx
  unsigned int v18; // r8d
  int v19; // edi
  const char *v20; // r9
  int v21; // edi
  int v22; // eax
  __int64 future; // rax
  int lpSearchFilter; // [rsp+20h] [rbp-638h]
  void **lpSearchFiltera; // [rsp+20h] [rbp-638h]
  unsigned int *dwAdditionalFlags; // [rsp+28h] [rbp-630h]
  unsigned int v28; // [rsp+30h] [rbp-628h]
  struct _GUID *v29; // [rsp+38h] [rbp-620h] BYREF
  unsigned int v30; // [rsp+40h] [rbp-618h]
  unsigned int v31[2]; // [rsp+48h] [rbp-610h] BYREF
  char *v32; // [rsp+50h] [rbp-608h] BYREF
  RTL_SRWLOCK *v33; // [rsp+58h] [rbp-600h]
  __int128 v34; // [rsp+60h] [rbp-5F8h] BYREF
  __int64 v35; // [rsp+70h] [rbp-5E8h]
  unsigned int *v36; // [rsp+78h] [rbp-5E0h] BYREF
  unsigned int v37[2]; // [rsp+80h] [rbp-5D8h] BYREF
  char v38; // [rsp+88h] [rbp-5D0h]
  _QWORD v39[2]; // [rsp+90h] [rbp-5C8h] BYREF
  __int16 v40; // [rsp+A0h] [rbp-5B8h]
  RTL_SRWLOCK *v41; // [rsp+A8h] [rbp-5B0h]
  RTL_SRWLOCK *v42; // [rsp+B0h] [rbp-5A8h]
  NgcIsoPregenPool *v43; // [rsp+B8h] [rbp-5A0h]
  _QWORD v44[2]; // [rsp+C0h] [rbp-598h] BYREF
  char v45[8]; // [rsp+D0h] [rbp-588h] BYREF
  char v46[8]; // [rsp+D8h] [rbp-580h] BYREF
  _BYTE v47[24]; // [rsp+E0h] [rbp-578h] BYREF
  _BYTE v48[16]; // [rsp+F8h] [rbp-560h] BYREF
  _BYTE v49[56]; // [rsp+108h] [rbp-550h] BYREF
  __int64 v50; // [rsp+140h] [rbp-518h]
  _OWORD v51[2]; // [rsp+148h] [rbp-510h] BYREF
  _OWORD v52[2]; // [rsp+168h] [rbp-4F0h] BYREF
  _OWORD v53[2]; // [rsp+188h] [rbp-4D0h] BYREF
  unsigned __int8 v54[8]; // [rsp+1A8h] [rbp-4B0h] BYREF
  __int128 v55; // [rsp+1B0h] [rbp-4A8h] BYREF
  _OWORD v56[2]; // [rsp+1C0h] [rbp-498h] BYREF
  NgcUtils *v57[2]; // [rsp+1E0h] [rbp-478h]
  __int64 v58; // [rsp+1F0h] [rbp-468h]
  _BYTE v59[32]; // [rsp+200h] [rbp-458h] BYREF
  _BYTE v60[80]; // [rsp+220h] [rbp-438h] BYREF
  _QWORD v61[42]; // [rsp+270h] [rbp-3E8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+3C0h] [rbp-298h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+658h] [rbp+0h]

  v1 = this;
  v43 = (NgcIsoPregenPool *)this;
  v2 = 0;
  wil::ActivityBase<LogProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v61);
  v61[0] = &LogProvider::NgcIsoPregenPoolLoadPregenKeys::`vftable';
  LogProvider::NgcIsoPregenPoolLoadPregenKeys::StartActivity((LogProvider::NgcIsoPregenPoolLoadPregenKeys *)v61);
  v3 = v1 + 1;
  v33 = v1 + 1;
  v36 = (unsigned int *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v1[1]);
  *(_QWORD *)v37 = L"*.json";
  v52[0] = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v52[1] = si128;
  LOWORD(v52[0]) = 0;
  v5 = NgcUtils::ComposePath(&v36, 2, v52);
  LastErrorFailHr = v5;
  if ( v5 >= 0 )
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v52);
    FirstFile = (char *)FindFirstFileExW(v7, FindExInfoBasic, &FindFileData, FindExSearchNameMatch, 0, 0);
    v32 = FirstFile;
    if ( (unsigned __int64)(FirstFile - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(v8);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v32);
      goto LABEL_22;
    }
    v42 = v1 + 1;
    v41 = v1;
    v10 = 0;
    v11 = 0;
    v30 = 0;
    while ( 1 )
    {
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        v44[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v3);
        v44[1] = FindFileData.cFileName;
        v51[0] = 0;
        v51[1] = si128;
        LOWORD(v51[0]) = 0;
        v12 = NgcUtils::ComposePath(v44, 2, v51);
        if ( v12 >= 0 )
        {
          v39[0] = v51;
          v39[1] = v41;
          v40 = 257;
          LODWORD(v29) = ++v10;
          v34 = 0;
          v35 = 0;
          v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v51);
          File = NgcUtils::ReadFile(v13, (__int64)&v34);
          if ( File >= 0 )
          {
            try
            {
              v55 = 0;
              v56[0] = 0;
              v56[1] = si128;
              LOWORD(v56[0]) = 0;
              *(_OWORD *)v57 = 0;
              v58 = 0;
              v36 = (unsigned int *)v49;
              v50 = 0;
              v15 = std::string::string(v59);
              nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::parse<std::string>(
                (__int64)v45,
                v15,
                (__int64)v49);
              Properties::SerializedPregenKey::SerializedPregenKey((Properties::SerializedPregenKey *)v60);
              Properties::from_json(v16, v60);
              v2 = v2 & 0xFFFFFFFC | 1;
              v28 = v2;
              Properties::SerializedPregenKey::operator=(&v55, v60);
              Properties::SerializedPregenKey::~SerializedPregenKey((Properties::SerializedPregenKey *)v60);
              LOBYTE(v17) = v45[0];
              nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
                v46,
                v17);
              std::string::_Tidy_deallocate(v59);
              *(_QWORD *)v31 = 0;
              LODWORD(v29) = 0;
              v36 = v31;
              *(_QWORD *)v37 = 0;
              v38 = 1;
              v19 = NgcUtils::UnprotectData(
                      v57[0],
                      (const unsigned __int8 *)(unsigned int)(LODWORD(v57[1]) - LODWORD(v57[0])),
                      v18,
                      (unsigned int)v37,
                      (unsigned __int8 **)&v29,
                      dwAdditionalFlags);
              wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&v36);
            }
            catch ( ... )
            {
              wil::details::in1diag3::Log_CaughtException(
                retaddr,
                (void *)0x1EB,
                (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
                v20);
              Properties::SerializedPregenKey::~SerializedPregenKey((Properties::SerializedPregenKey *)&v55);
              std::vector<unsigned char>::_Tidy(&v34);
              wil::details::ScopeExitFnGuard__lambda_82ed4d1a4a6c46574ab2a866d5c3b88e___::operator()(v39);
              std::wstring::_Tidy_deallocate(v51);
              v10 = (unsigned int)v29;
              v11 = v30;
              FirstFile = v32;
              si128 = _mm_load_si128((const __m128i *)&_xmm);
              v3 = v42;
              v33 = v42;
              v2 = v28;
              v1 = (RTL_SRWLOCK *)v43;
              goto LABEL_19;
            }
            if ( v19 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1F8,
                (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
                (const char *)(unsigned int)v19,
                (int)lpSearchFiltera);
              wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>::reset(v31, 0);
              Properties::SerializedPregenKey::~SerializedPregenKey((Properties::SerializedPregenKey *)&v55);
              std::vector<unsigned char>::_Tidy(&v34);
              wil::details::ScopeExitFnGuard__lambda_82ed4d1a4a6c46574ab2a866d5c3b88e___::operator()(v39);
              std::wstring::_Tidy_deallocate(v51);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v32);
              LastErrorFailHr = v19;
              goto LABEL_22;
            }
            v53[0] = 0;
            v53[1] = si128;
            LOWORD(v53[0]) = 0;
            *(_QWORD *)v54 = 0;
            v21 = NgcIsoTrustlet::DeserializePregenKey(
                    (NgcIsoTrustlet *)&v55,
                    (const struct _GUID *)(unsigned int)v29,
                    v31[0],
                    v54,
                    lpSearchFiltera);
            v22 = NgcIsoPregenPool::SaveTpmCounterStore((NgcIsoPregenPool *)v1);
            if ( v22 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x200,
                (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
                (const char *)(unsigned int)v22,
                (int)lpSearchFiltera);
            if ( v21 >= 0 )
            {
              std::wstring::operator=(v53, v56);
              std::promise<NgcIsoPregenPool::PregenKey>::promise<NgcIsoPregenPool::PregenKey>(v47);
              std::promise<NgcIsoPregenPool::PregenKey>::set_value(v47, v53);
              AcquireSRWLockExclusive(v1 + 15);
              v29 = (struct _GUID *)&v1[15];
              future = std::promise<NgcIsoPregenPool::PregenKey>::get_future(v47, v48);
              std::queue<std::future<NgcIsoPregenPool::PregenKey>>::push(&v1[16], future);
              std::_State_manager<NgcIsoPregenPool::PregenKey>::~_State_manager<NgcIsoPregenPool::PregenKey>(v48);
              v30 = ++v11;
              wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v29);
              std::promise<NgcIsoPregenPool::PregenKey>::~promise<NgcIsoPregenPool::PregenKey>(v47);
            }
            else
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x201,
                (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
                (const char *)(unsigned int)v21,
                (int)lpSearchFiltera);
            }
            std::wstring::_Tidy_deallocate(v53);
            wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>::reset(v31, 0);
            Properties::SerializedPregenKey::~SerializedPregenKey((Properties::SerializedPregenKey *)&v55);
            std::vector<unsigned char>::_Tidy(&v34);
            wil::details::ScopeExitFnGuard__lambda_82ed4d1a4a6c46574ab2a866d5c3b88e___::operator()(v39);
            std::wstring::_Tidy_deallocate(v51);
            v3 = v33;
            goto LABEL_19;
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1DC,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
            (const char *)(unsigned int)File,
            (int)lpSearchFiltera);
          std::vector<unsigned char>::_Tidy(&v34);
          wil::details::ScopeExitFnGuard__lambda_82ed4d1a4a6c46574ab2a866d5c3b88e___::operator()(v39);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1C8,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
            (const char *)(unsigned int)v12,
            (int)lpSearchFiltera);
        }
        std::wstring::_Tidy_deallocate(v51);
      }
LABEL_19:
      if ( !FindNextFileW(FirstFile, &FindFileData) )
      {
        LogProvider::NgcIsoPregenPoolLoadPregenKeys::Stop((LogProvider::NgcIsoPregenPoolLoadPregenKeys *)v61, v10, v11);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v32);
        std::wstring::_Tidy_deallocate(v52);
        LogProvider::NgcIsoPregenPoolLoadPregenKeys::~NgcIsoPregenPoolLoadPregenKeys((LogProvider::NgcIsoPregenPoolLoadPregenKeys *)v61);
        return 0;
      }
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1AA,
    (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\pregenpool.cpp",
    (const char *)(unsigned int)v5,
    lpSearchFilter);
LABEL_22:
  std::wstring::_Tidy_deallocate(v52);
  LogProvider::NgcIsoPregenPoolLoadPregenKeys::~NgcIsoPregenPoolLoadPregenKeys((LogProvider::NgcIsoPregenPoolLoadPregenKeys *)v61);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180049478  mov     rax, rsp
0x18004947b  mov     [rax+10h], rbx
0x18004947f  mov     [rax+18h], rsi
0x180049483  push    rdi
0x180049484  push    r12
0x180049486  push    r13
0x180049488  push    r14
0x18004948a  push    r15
0x18004948c  sub     rsp, 630h
0x180049493  movaps  xmmword ptr [rax-38h], xmm6
0x180049497  mov     rax, cs:__security_cookie
0x18004949e  xor     rax, rsp
0x1800494a1  mov     [rsp+658h+var_48], rax
0x1800494a9  mov     r13, rcx
0x1800494ac  mov     [rsp+658h+var_5A0], rcx
0x1800494b4  xor     esi, esi
0x1800494b6  mov     r14d, esi
0x1800494b9  mov     [rsp+658h+var_628], esi
0x1800494bd  lea     rdx, aNgcisopregenpo_1; "NgcIsoPregenPoolLoadPregenKeys"
0x1800494c4  lea     rcx, [rsp+658h+var_3E8]; struct wil::details::IFailureCallback *
0x1800494cc  call    ??0?$ActivityBase@VLogProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LogProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LogProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800494d1  lea     rax, ??_7NgcIsoPregenPoolLoadPregenKeys@LogProvider@@6B@; const LogProvider::NgcIsoPregenPoolLoadPregenKeys::`vftable'
0x1800494d8  mov     [rsp+658h+var_3E8], rax
0x1800494e0  lea     rcx, [rsp+658h+var_3E8]; this
0x1800494e8  call    ?StartActivity@NgcIsoPregenPoolLoadPregenKeys@LogProvider@@QEAAXXZ; LogProvider::NgcIsoPregenPoolLoadPregenKeys::StartActivity(void)
0x1800494ed  nop
0x1800494ee  lea     rdi, [r13+8]
0x1800494f2  mov     [rsp+658h+var_600], rdi
0x1800494f7  mov     rcx, rdi
0x1800494fa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800494ff  mov     [rsp+658h+var_5E0], rax
0x180049504  lea     rax, aJson; "*.json"
0x18004950b  mov     qword ptr [rsp+658h+var_5D8], rax
0x180049513  xorps   xmm0, xmm0
0x180049516  movups  [rsp+658h+var_4F0], xmm0
0x18004951e  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180049526  movdqu  [rsp+658h+var_4E0], xmm6
0x18004952f  mov     word ptr [rsp+658h+var_4F0], si
0x180049537  lea     r8, [rsp+658h+var_4F0]
0x18004953f  lea     edx, [rsi+2]
0x180049542  lea     rcx, [rsp+658h+var_5E0]
0x180049547  call    ?ComposePath@NgcUtils@@YAJQEBQEBGKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::ComposePath(ushort const * const * const,ulong,std::wstring *)
0x18004954c  mov     ebx, eax
0x18004954e  test    eax, eax
0x180049550  jns     short loc_180049573
0x180049552  mov     rcx, [rsp+658h]; this
0x18004955a  mov     r9d, eax; char *
0x18004955d  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180049564  mov     edx, 1AAh; void *
0x180049569  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004956e  jmp     loc_180049B32
0x180049573  xor     edx, edx; Val
0x180049575  mov     r8d, 250h; Size
0x18004957b  lea     rcx, [rsp+658h+FindFileData]; void *
0x180049583  call    memset_0
0x180049588  lea     rcx, [rsp+658h+var_4F0]
0x180049590  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049595  mov     rcx, rax; lpFileName
0x180049598  mov     dword ptr [rsp+658h+dwAdditionalFlags], esi; unsigned int *
0x18004959c  mov     [rsp+658h+lpSearchFilter], rsi; int
0x1800495a1  xor     r9d, r9d; fSearchOp
0x1800495a4  lea     r8, [rsp+658h+FindFileData]; lpFindFileData
0x1800495ac  lea     edx, [r9+1]; fInfoLevelId
0x1800495b0  call    cs:__imp_FindFirstFileExW
0x1800495b6  mov     rbx, rax
0x1800495b9  mov     [rsp+658h+var_608], rax
0x1800495be  dec     rax
0x1800495c1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800495c5  ja      loc_180049B20
0x1800495cb  mov     [rsp+658h+var_5A8], rdi
0x1800495d3  mov     [rsp+658h+var_5B0], r13
0x1800495db  mov     r15d, esi
0x1800495de  mov     r12d, esi
0x1800495e1  mov     [rsp+658h+var_618], esi
0x1800495e5  test    [rsp+658h+FindFileData], 10h
0x1800495ed  jnz     loc_180049AC9
0x1800495f3  mov     rcx, rdi
0x1800495f6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800495fb  mov     [rsp+658h+var_598], rax
0x180049603  lea     rax, [rsp+658h+var_26C]
0x18004960b  mov     [rsp+658h+var_590], rax
0x180049613  xorps   xmm0, xmm0
0x180049616  movups  [rsp+658h+var_510], xmm0
0x18004961e  movdqu  [rsp+658h+var_500], xmm6
0x180049627  mov     word ptr [rsp+658h+var_510], si
0x18004962f  lea     r8, [rsp+658h+var_510]
0x180049637  mov     edx, 2
0x18004963c  lea     rcx, [rsp+658h+var_598]
0x180049644  call    ?ComposePath@NgcUtils@@YAJQEBQEBGKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::ComposePath(ushort const * const * const,ulong,std::wstring *)
0x180049649  mov     rcx, [rsp+658h]; this
0x180049651  test    eax, eax
0x180049653  jns     short loc_18004967C
0x180049655  mov     r9d, eax; char *
0x180049658  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18004965f  mov     edx, 1C8h; void *
0x180049664  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049669  nop
0x18004966a  lea     rcx, [rsp+658h+var_510]
0x180049672  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049677  jmp     loc_180049AC9
0x18004967c  lea     rax, [rsp+658h+var_510]
0x180049684  mov     [rsp+658h+var_5C8], rax
0x18004968c  mov     rax, [rsp+658h+var_5B0]
0x180049694  mov     [rsp+658h+var_5C0], rax
0x18004969c  mov     [rsp+658h+var_5B8], 101h
0x1800496a6  inc     r15d
0x1800496a9  mov     dword ptr [rsp+658h+var_620], r15d
0x1800496ae  xorps   xmm0, xmm0
0x1800496b1  movdqu  [rsp+658h+var_5F8], xmm0
0x1800496b7  mov     [rsp+658h+var_5E8], rsi
0x1800496bc  lea     rcx, [rsp+658h+var_510]
0x1800496c4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800496c9  mov     rcx, rax
0x1800496cc  lea     rdx, [rsp+658h+var_5F8]
0x1800496d1  call    ?ReadFile@NgcUtils@@YAJPEBGPEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcUtils::ReadFile(ushort const *,std::vector<uchar> *)
0x1800496d6  mov     rcx, [rsp+658h]; this
0x1800496de  test    eax, eax
0x1800496e0  jns     short loc_180049714
0x1800496e2  mov     r9d, eax; char *
0x1800496e5  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x1800496ec  mov     edx, 1DCh; void *
0x1800496f1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800496f6  nop
0x1800496f7  lea     rcx, [rsp+658h+var_5F8]
0x1800496fc  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180049701  nop
0x180049702  lea     rcx, [rsp+658h+var_5C8]
0x18004970a  call    wil__details__ScopeExitFnGuard__lambda_82ed4d1a4a6c46574ab2a866d5c3b88e_____operator__
0x18004970f  jmp     loc_18004966A
0x180049714  xorps   xmm0, xmm0
0x180049717  movups  [rsp+658h+var_4A8], xmm0
0x18004971f  xorps   xmm1, xmm1
0x180049722  movups  [rsp+658h+var_498], xmm1
0x18004972a  movdqa  [rsp+658h+var_488], xmm6
0x180049733  mov     word ptr [rsp+658h+var_498], si
0x18004973b  movdqa  xmmword ptr [rsp+658h+var_478], xmm0
0x180049744  mov     [rsp+658h+var_468], rsi
0x18004974c  lea     rax, [rsp+658h+var_550]
0x180049754  mov     [rsp+658h+var_5E0], rax
0x180049759  mov     [rsp+658h+var_518], rsi
0x180049761  mov     r8, qword ptr [rsp+658h+var_5F8+8]
0x180049766  mov     rdx, qword ptr [rsp+658h+var_5F8]
0x18004976b  lea     rcx, [rsp+658h+var_458]
0x180049773  call    ??$?0PEBD$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD0AEBV?$allocator@D@1@@Z; std::string::string(char const *,char const *,std::allocator<char> const &)
0x180049778  nop
0x180049779  lea     r8, [rsp+658h+var_550]
0x180049781  mov     rdx, rax
0x180049784  lea     rcx, [rsp+658h+var_588]
0x18004978c  call    ??$parse@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@SA?AV01@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$function@$$A6A_NHW4parse_event_t@detail@nlohmann@@AEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@3@@Z@3@_N2@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::parse<std::string>(std::string &&,std::function<bool (int,nlohmann::detail::parse_event_t,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> &)>,bool,bool)
0x180049791  mov     r8, rax
0x180049794  lea     rcx, [rsp+658h+var_438]; this
0x18004979c  call    ??0SerializedPregenKey@Properties@@QEAA@XZ; Properties::SerializedPregenKey::SerializedPregenKey(void)
0x1800497a1  or      r14d, 2
0x1800497a5  mov     [rsp+658h+var_628], r14d
0x1800497aa  lea     rdx, [rsp+658h+var_438]
0x1800497b2  mov     rcx, r8
0x1800497b5  call    ?from_json@Properties@@YAXAEBV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@AEAUSerializedPregenKey@1@@Z; Properties::from_json(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> const &,Properties::SerializedPregenKey &)
0x1800497ba  and     r14d, 0FFFFFFFDh
0x1800497be  or      r14d, 1
0x1800497c2  mov     [rsp+658h+var_628], r14d
0x1800497c7  lea     rdx, [rsp+658h+var_438]
0x1800497cf  lea     rcx, [rsp+658h+var_4A8]
0x1800497d7  call    ??4SerializedPregenKey@Properties@@QEAAAEAU01@$$QEAU01@@Z; Properties::SerializedPregenKey::operator=(Properties::SerializedPregenKey &&)
0x1800497dc  lea     rcx, [rsp+658h+var_438]; this
0x1800497e4  call    ??1SerializedPregenKey@Properties@@QEAA@XZ; Properties::SerializedPregenKey::~SerializedPregenKey(void)
0x1800497e9  nop
0x1800497ea  mov     dl, [rsp+658h+var_588]
0x1800497f1  lea     rcx, [rsp+658h+var_580]
0x1800497f9  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x1800497fe  nop
0x1800497ff  lea     rcx, [rsp+658h+var_458]
0x180049807  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004980c  nop
0x18004980d  mov     qword ptr [rsp+658h+var_610], rsi
0x180049812  mov     dword ptr [rsp+658h+var_620], esi
0x180049816  lea     rax, [rsp+658h+var_610]
0x18004981b  mov     [rsp+658h+var_5E0], rax
0x180049820  mov     qword ptr [rsp+658h+var_5D8], rsi
0x180049828  mov     [rsp+658h+var_5D0], 1
0x180049830  mov     rcx, [rsp+658h+var_478]; this
0x180049838  mov     edx, dword ptr [rsp+658h+var_478+8]
0x18004983f  sub     edx, ecx; unsigned __int8 *
0x180049841  lea     rax, [rsp+658h+var_620]
0x180049846  mov     [rsp+658h+lpSearchFilter], rax; int
0x18004984b  lea     r9, [rsp+658h+var_5D8]; unsigned int
0x180049853  call    ?UnprotectData@NgcUtils@@YAJPEBEKKPEAPEAEPEAK@Z; NgcUtils::UnprotectData(uchar const *,ulong,ulong,uchar * *,ulong *)
0x180049858  mov     edi, eax
0x18004985a  lea     rcx, [rsp+658h+var_5E0]
0x18004985f  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x180049864  test    edi, edi
0x180049866  jns     short loc_1800498D8
0x180049868  mov     rcx, [rsp+658h]; this
0x180049870  mov     r9d, edi; char *
0x180049873  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18004987a  mov     edx, 1F8h; void *
0x18004987f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049884  nop
0x180049885  xor     edx, edx
0x180049887  lea     rcx, [rsp+658h+var_610]
0x18004988c  call    ?reset@?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>::reset(uchar *)
0x180049891  nop
0x180049892  lea     rcx, [rsp+658h+var_4A8]; this
0x18004989a  call    ??1SerializedPregenKey@Properties@@QEAA@XZ; Properties::SerializedPregenKey::~SerializedPregenKey(void)
0x18004989f  nop
0x1800498a0  lea     rcx, [rsp+658h+var_5F8]
0x1800498a5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800498aa  nop
0x1800498ab  lea     rcx, [rsp+658h+var_5C8]
0x1800498b3  call    wil__details__ScopeExitFnGuard__lambda_82ed4d1a4a6c46574ab2a866d5c3b88e_____operator__
0x1800498b8  nop
0x1800498b9  lea     rcx, [rsp+658h+var_510]
0x1800498c1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800498c6  nop
0x1800498c7  lea     rcx, [rsp+658h+var_608]
0x1800498cc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800498d1  mov     ebx, edi
0x1800498d3  jmp     loc_180049B32
0x1800498d8  xorps   xmm0, xmm0
0x1800498db  movups  [rsp+658h+var_4D0], xmm0
0x1800498e3  movdqu  [rsp+658h+var_4C0], xmm6
0x1800498ec  mov     word ptr [rsp+658h+var_4D0], si
0x1800498f4  xor     eax, eax
0x1800498f6  mov     qword ptr [rsp+658h+var_4B0], rax
0x1800498fe  lea     r9, [rsp+658h+var_4B0]; unsigned __int8 *
0x180049906  mov     r8, qword ptr [rsp+658h+var_610]; unsigned int
0x18004990b  mov     edx, dword ptr [rsp+658h+var_620]; struct _GUID *
0x18004990f  lea     rcx, [rsp+658h+var_4A8]; this
0x180049917  call    ?DeserializePregenKey@NgcIsoTrustlet@@YAJAEBU_GUID@@KPEAEPEAPEAX@Z; NgcIsoTrustlet::DeserializePregenKey(_GUID const &,ulong,uchar *,void * *)
0x18004991c  mov     edi, eax
0x18004991e  mov     rcx, r13; this
0x180049921  call    ?SaveTpmCounterStore@NgcIsoPregenPool@@QEAAJXZ; NgcIsoPregenPool::SaveTpmCounterStore(void)
0x180049926  mov     rcx, [rsp+658h]; this
0x18004992e  test    eax, eax
0x180049930  jns     short loc_180049946
0x180049932  mov     r9d, eax; char *
0x180049935  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18004993c  mov     edx, 200h; void *
0x180049941  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049946  mov     rcx, [rsp+658h]; this
0x18004994e  test    edi, edi
0x180049950  jns     short loc_1800499C0
0x180049952  mov     r9d, edi; char *
0x180049955  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18004995c  mov     edx, 201h; void *
0x180049961  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049966  nop
0x180049967  lea     rcx, [rsp+658h+var_4D0]
0x18004996f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049974  nop
0x180049975  xor     edx, edx
0x180049977  lea     rcx, [rsp+658h+var_610]
0x18004997c  call    ?reset@?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>::reset(uchar *)
0x180049981  nop
0x180049982  lea     rcx, [rsp+658h+var_4A8]; this
0x18004998a  call    ??1SerializedPregenKey@Properties@@QEAA@XZ; Properties::SerializedPregenKey::~SerializedPregenKey(void)
0x18004998f  nop
0x180049990  lea     rcx, [rsp+658h+var_5F8]
0x180049995  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18004999a  nop
0x18004999b  lea     rcx, [rsp+658h+var_5C8]
0x1800499a3  call    wil__details__ScopeExitFnGuard__lambda_82ed4d1a4a6c46574ab2a866d5c3b88e_____operator__
0x1800499a8  nop
0x1800499a9  lea     rcx, [rsp+658h+var_510]
0x1800499b1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800499b6  mov     rdi, [rsp+658h+var_600]
0x1800499bb  jmp     loc_180049AC9
0x1800499c0  lea     rdx, [rsp+658h+var_498]
0x1800499c8  lea     rcx, [rsp+658h+var_4D0]
0x1800499d0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800499d5  lea     rcx, [rsp+658h+var_578]
0x1800499dd  call    ??0?$promise@UPregenKey@NgcIsoPregenPool@@@std@@QEAA@XZ; std::promise<NgcIsoPregenPool::PregenKey>::promise<NgcIsoPregenPool::PregenKey>(void)
0x1800499e2  nop
0x1800499e3  lea     rdx, [rsp+658h+var_4D0]
0x1800499eb  lea     rcx, [rsp+658h+var_578]
0x1800499f3  call    ?set_value@?$promise@UPregenKey@NgcIsoPregenPool@@@std@@QEAAX$$QEAUPregenKey@NgcIsoPregenPool@@@Z; std::promise<NgcIsoPregenPool::PregenKey>::set_value(NgcIsoPregenPool::PregenKey &&)
0x1800499f8  lea     rdi, [r13+78h]
0x1800499fc  mov     rcx, rdi; SRWLock
0x1800499ff  call    cs:__imp_AcquireSRWLockExclusive
0x180049a05  mov     [rsp+658h+var_620], rdi
0x180049a0a  lea     rdx, [rsp+658h+var_560]
0x180049a12  lea     rcx, [rsp+658h+var_578]
0x180049a1a  call    ?get_future@?$promise@UPregenKey@NgcIsoPregenPool@@@std@@QEAA?AV?$future@UPregenKey@NgcIsoPregenPool@@@2@XZ; std::promise<NgcIsoPregenPool::PregenKey>::get_future(void)
0x180049a1f  nop
0x180049a20  lea     rcx, [r13+80h]
0x180049a27  mov     rdx, rax
0x180049a2a  call    ?push@?$queue@V?$future@UPregenKey@NgcIsoPregenPool@@@std@@V?$deque@V?$future@UPregenKey@NgcIsoPregenPool@@@std@@V?$allocator@V?$future@UPregenKey@NgcIsoPregenPool@@@std@@@2@@2@@std@@QEAAX$$QEAV?$future@UPregenKey@NgcIsoPregenPool@@@2@@Z; std::queue<std::future<NgcIsoPregenPool::PregenKey>>::push(std::future<NgcIsoPregenPool::PregenKey> &&)
0x180049a2f  nop
0x180049a30  lea     rcx, [rsp+658h+var_560]
0x180049a38  call    ??1?$_State_manager@UPregenKey@NgcIsoPregenPool@@@std@@QEAA@XZ; std::_State_manager<NgcIsoPregenPool::PregenKey>::~_State_manager<NgcIsoPregenPool::PregenKey>(void)
0x180049a3d  inc     r12d
0x180049a40  mov     [rsp+658h+var_618], r12d
0x180049a45  lea     rcx, [rsp+658h+var_620]
0x180049a4a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180049a4f  nop
0x180049a50  lea     rcx, [rsp+658h+var_578]
0x180049a58  call    ??1?$promise@UPregenKey@NgcIsoPregenPool@@@std@@QEAA@XZ; std::promise<NgcIsoPregenPool::PregenKey>::~promise<NgcIsoPregenPool::PregenKey>(void)
0x180049a5d  jmp     loc_180049967
0x180049a62  lea     rcx, [rsp+658h+var_4A8]; this
0x180049a6a  call    ??1SerializedPregenKey@Properties@@QEAA@XZ; Properties::SerializedPregenKey::~SerializedPregenKey(void)
0x180049a6f  nop
  ... truncated ...
```
