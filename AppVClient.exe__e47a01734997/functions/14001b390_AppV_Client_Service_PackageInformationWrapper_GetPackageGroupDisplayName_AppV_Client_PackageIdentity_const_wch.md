# AppV::Client::Service::PackageInformationWrapper::GetPackageGroupDisplayName(AppV::Client::PackageIdentity const &,wchar_t * &)

- ea: `0x14001b390`
- end: `0x14001b634`
- name: `?GetPackageGroupDisplayName@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEBUPackageIdentity@34@AEAPEA_W@Z`
- size: `676`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Service::PackageInformationWrapper *__hidden this, const struct AppV::Client::PackageIdentity *, wchar_t **)`
- caller_count: `2`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x14001b63c`
- `0x14001d4b0`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x14001b390`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x14003cc28`
- `0x14003cc80`
- `0x14006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001b589`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001b589`
- `OLEAUT32!__imp_SysAllocString` at `0x14001b571`
- `OLEAUT32!__imp_SysAllocString` at `0x14001b571`

## string_xrefs

- `0x14001b582`: `admin\appman\appv\client\host\service\packageinformationwrapper.cpp`
- `0x14001b599`: `admin\appman\appv\client\host\service\packageinformationwrapper.cpp`
- `0x14001b3e2`: `AppV::Client::Service::PackageInformationWrapper::GetPackageGroupDisplayName`
- `0x14001b413`: `Failed to get package group descriptor for package group %1% version %2%, error %3%`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
unsigned __int64 __fastcall AppV::Client::Service::PackageInformationWrapper::GetPackageGroupDisplayName(
        AppV::Client::Service::PackageInformationWrapper *this,
        const struct AppV::Client::PackageIdentity *a2,
        wchar_t **a3)
{
  unsigned __int64 v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rbx
  volatile signed __int32 *v12; // rdi
  const OLECHAR *v14; // rcx
  wchar_t *v15; // rax
  char *v16; // rax
  const char *v17; // rax
  volatile signed __int32 *v18; // rdi
  __int128 v19; // [rsp+20h] [rbp-A9h] BYREF
  unsigned __int64 v20; // [rsp+30h] [rbp-99h] BYREF
  OLECHAR *psz[2]; // [rsp+38h] [rbp-91h] BYREF
  __m128i si128; // [rsp+48h] [rbp-81h]
  _OWORD v23[2]; // [rsp+58h] [rbp-71h] BYREF
  _OWORD v24[2]; // [rsp+78h] [rbp-51h] BYREF
  char *v25[4]; // [rsp+98h] [rbp-31h] BYREF
  int v26; // [rsp+B8h] [rbp-11h]
  void **v27; // [rsp+C0h] [rbp-9h] BYREF
  char *v28; // [rsp+D0h] [rbp+7h] BYREF

  v19 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, const struct AppV::Client::PackageIdentity *, __int128 *))(**(_QWORD **)this + 88LL))(
         *(_QWORD *)this,
         a2,
         &v19);
  if ( (v5 & 0x8000000000LL) == 0 )
  {
    std::string::string(v25, "AppV::Client::Service::PackageInformationWrapper::GetPackageGroupDisplayName");
    v26 = 717;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v6);
    memset(v24, 0, sizeof(v24));
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)v24,
      L"Failed to get package group descriptor for package group %1% version %2%, error %3%",
      0x53u);
    v8 = AppV::Log::fmt(v7, &v27, v24);
    v9 = AppV::LogFormatter::operator%(v8, a2);
    v10 = AppV::LogFormatter::operator%(v9, (char *)a2 + 16);
    v20 = v5;
    v11 = AppV::LogFormatter::operator%(v10, (__int64 *)&v20);
    memset(v23, 0, sizeof(v23));
    std::wstring::_Construct<1,wchar_t const *>((char **)v23, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v25, 8, (int)v23, v11);
    std::wstring::~wstring((char **)v23);
    v27 = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(&v28);
    std::wstring::~wstring((char **)v24);
    std::string::~string(v25);
    goto LABEL_3;
  }
  *(_OWORD *)psz = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(psz[0]) = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR **))(*(_QWORD *)v19 + 48LL))(v19, psz);
  if ( (v5 & 0x8000000000LL) == 0 )
  {
LABEL_9:
    std::wstring::~wstring((char **)psz);
LABEL_3:
    v12 = (volatile signed __int32 *)*((_QWORD *)&v19 + 1);
    if ( *((_QWORD *)&v19 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v19 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
    return v5;
  }
  v14 = (const OLECHAR *)psz;
  if ( si128.m128i_i64[1] > 7uLL )
    v14 = psz[0];
  v15 = SysAllocString(v14);
  *a3 = v15;
  if ( !v15 )
  {
    v16 = strrchr("admin\\appman\\appv\\client\\host\\service\\packageinformationwrapper.cpp", 92);
    if ( v16 )
      v17 = v16 + 1;
    else
      v17 = "admin\\appman\\appv\\client\\host\\service\\packageinformationwrapper.cpp";
    v5 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v17) << 52)
       | 0x5A230000000ELL;
    goto LABEL_9;
  }
  std::wstring::~wstring((char **)psz);
  v18 = (volatile signed __int32 *)*((_QWORD *)&v19 + 1);
  if ( *((_QWORD *)&v19 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v19 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
      if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
    }
  }
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x14001b390  push    rbp
0x14001b392  push    rbx
0x14001b393  push    rsi
0x14001b394  push    rdi
0x14001b395  push    r14
0x14001b397  lea     rbp, [rsp-37h]
0x14001b39c  sub     rsp, 100h
0x14001b3a3  mov     rax, cs:__security_cookie
0x14001b3aa  xor     rax, rsp
0x14001b3ad  mov     [rbp+57h+var_30], rax
0x14001b3b1  mov     rdi, r8
0x14001b3b4  mov     rbx, rdx
0x14001b3b7  xorps   xmm0, xmm0
0x14001b3ba  movdqu  [rsp+120h+var_100], xmm0
0x14001b3c0  mov     rcx, [rcx]
0x14001b3c3  mov     rax, [rcx]
0x14001b3c6  lea     r8, [rsp+120h+var_100]
0x14001b3cb  mov     rax, [rax+58h]
0x14001b3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b3d4  mov     rsi, rax
0x14001b3d7  bt      rax, 27h ; '''
0x14001b3dc  jb      loc_14001B515
0x14001b3e2  lea     rdx, aAppvClientServ_20; "AppV::Client::Service::PackageInformati"...
0x14001b3e9  lea     rcx, [rbp+57h+var_88]
0x14001b3ed  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14001b3f2  mov     [rbp+57h+var_68], 2CDh
0x14001b3f9  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14001b3fe  xorps   xmm0, xmm0
0x14001b401  movups  [rbp+57h+var_A8], xmm0
0x14001b405  xorps   xmm1, xmm1
0x14001b408  movdqu  [rbp+57h+var_98], xmm1
0x14001b40d  mov     r8d, 53h ; 'S'
0x14001b413  lea     rdx, aFailedToGetPac_0; "Failed to get package group descriptor "...
0x14001b41a  lea     rcx, [rbp+57h+var_A8]
0x14001b41e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001b423  nop
0x14001b424  lea     r8, [rbp+57h+var_A8]
0x14001b428  lea     rdx, [rbp+57h+var_60]
0x14001b42c  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14001b431  nop
0x14001b432  mov     rdx, rbx
0x14001b435  mov     rcx, rax
0x14001b438  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBU_GUID@@@Z; AppV::LogFormatter::operator%(_GUID const &)
0x14001b43d  lea     rdx, [rbx+10h]
0x14001b441  mov     rcx, rax
0x14001b444  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBU_GUID@@@Z; AppV::LogFormatter::operator%(_GUID const &)
0x14001b449  mov     [rsp+120h+var_F0], rsi
0x14001b44e  lea     rdx, [rsp+120h+var_F0]
0x14001b453  mov     rcx, rax
0x14001b456  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBVErrorCode@1@@Z; AppV::LogFormatter::operator%(AppV::ErrorCode const &)
0x14001b45b  mov     rbx, rax
0x14001b45e  xorps   xmm0, xmm0
0x14001b461  movups  [rbp+57h+var_C8], xmm0
0x14001b465  xorps   xmm1, xmm1
0x14001b468  movdqu  [rbp+57h+var_B8], xmm1
0x14001b46d  mov     r8d, 6
0x14001b473  lea     rdx, aClient; "Client"
0x14001b47a  lea     rcx, [rbp+57h+var_C8]
0x14001b47e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001b483  nop
0x14001b484  mov     r9, rbx
0x14001b487  lea     r8, [rbp+57h+var_C8]
0x14001b48b  mov     edx, 8
0x14001b490  lea     rcx, [rbp+57h+var_88]
0x14001b494  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14001b499  nop
0x14001b49a  lea     rcx, [rbp+57h+var_C8]
0x14001b49e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001b4a3  nop
0x14001b4a4  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14001b4ab  mov     [rbp+57h+var_60], rax
0x14001b4af  lea     rcx, [rbp+57h+var_50]
0x14001b4b3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001b4b8  nop
0x14001b4b9  lea     rcx, [rbp+57h+var_A8]
0x14001b4bd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001b4c2  nop
0x14001b4c3  lea     rcx, [rbp+57h+var_88]
0x14001b4c7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14001b4cc  nop
0x14001b4cd  mov     rdi, qword ptr [rsp+120h+var_100+8]
0x14001b4d2  test    rdi, rdi
0x14001b4d5  jz      short loc_14001B50D
0x14001b4d7  or      ebx, 0FFFFFFFFh
0x14001b4da  mov     eax, ebx
0x14001b4dc  lock xadd [rdi+8], eax
0x14001b4e1  add     eax, ebx
0x14001b4e3  jnz     short loc_14001B50D
0x14001b4e5  mov     rax, [rdi]
0x14001b4e8  mov     rcx, rdi
0x14001b4eb  mov     rax, [rax]
0x14001b4ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b4f3  mov     eax, ebx
0x14001b4f5  lock xadd [rdi+0Ch], eax
0x14001b4fa  add     eax, ebx
0x14001b4fc  jnz     short loc_14001B50D
0x14001b4fe  mov     rax, [rdi]
0x14001b501  mov     rcx, rdi
0x14001b504  mov     rax, [rax+8]
0x14001b508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b50d  mov     rax, rsi
0x14001b510  jmp     loc_14001B61A
0x14001b515  xorps   xmm0, xmm0
0x14001b518  movups  xmmword ptr [rsp+120h+psz], xmm0
0x14001b51d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14001b525  movdqu  [rsp+120h+var_D8], xmm1
0x14001b52b  xor     ebx, ebx
0x14001b52d  mov     word ptr [rsp+120h+psz], bx
0x14001b532  mov     rcx, qword ptr [rsp+120h+var_100]
0x14001b537  mov     rax, [rcx]
0x14001b53a  lea     rdx, [rsp+120h+psz]
0x14001b53f  mov     rax, [rax+30h]
0x14001b543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b548  mov     rsi, rax
0x14001b54b  bt      rax, 27h ; '''
0x14001b550  jb      short loc_14001B561
0x14001b552  lea     rcx, [rsp+120h+psz]
0x14001b557  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001b55c  jmp     loc_14001B4CD
0x14001b561  lea     rcx, [rsp+120h+psz]
0x14001b566  cmp     qword ptr [rbp+57h+var_D8+8], 7
0x14001b56b  cmova   rcx, [rsp+120h+psz]; psz
0x14001b571  call    cs:__imp_SysAllocString
0x14001b577  mov     [rdi], rax
0x14001b57a  test    rax, rax
0x14001b57d  jnz     short loc_14001B5C5
0x14001b57f  lea     edx, [rax+5Ch]; Ch
0x14001b582  lea     rcx, aAdminAppmanApp_11; "admin\\appman\\appv\\client\\host\\serv"...
0x14001b589  call    cs:__imp_strrchr
0x14001b58f  test    rax, rax
0x14001b592  jz      short loc_14001B599
0x14001b594  inc     rax
0x14001b597  jmp     short loc_14001B5A0
0x14001b599  lea     rax, aAdminAppmanApp_11; "admin\\appman\\appv\\client\\host\\serv"...
0x14001b5a0  mov     rdx, rax; char *
0x14001b5a3  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14001b5aa  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14001b5af  mov     rsi, rax
0x14001b5b2  shl     rsi, 34h
0x14001b5b6  mov     rax, 5A230000000Eh
0x14001b5c0  or      rsi, rax
0x14001b5c3  jmp     short loc_14001B552
0x14001b5c5  lea     rcx, [rsp+120h+psz]
0x14001b5ca  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001b5cf  nop
0x14001b5d0  mov     rdi, qword ptr [rsp+120h+var_100+8]
0x14001b5d5  test    rdi, rdi
0x14001b5d8  jz      short loc_14001B610
0x14001b5da  or      ebx, 0FFFFFFFFh
0x14001b5dd  mov     eax, ebx
0x14001b5df  lock xadd [rdi+8], eax
0x14001b5e4  add     eax, ebx
0x14001b5e6  jnz     short loc_14001B610
0x14001b5e8  mov     rax, [rdi]
0x14001b5eb  mov     rcx, rdi
0x14001b5ee  mov     rax, [rax]
0x14001b5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b5f6  mov     eax, ebx
0x14001b5f8  lock xadd [rdi+0Ch], eax
0x14001b5fd  add     eax, ebx
0x14001b5ff  jnz     short loc_14001B610
0x14001b601  mov     rax, [rdi]
0x14001b604  mov     rcx, rdi
0x14001b607  mov     rax, [rax+8]
0x14001b60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b610  mov     rax, 8000000000h
0x14001b61a  mov     rcx, [rbp+57h+var_30]
0x14001b61e  xor     rcx, rsp; StackCookie
0x14001b621  call    __security_check_cookie
0x14001b626  add     rsp, 100h
0x14001b62d  pop     r14
0x14001b62f  pop     rdi
0x14001b630  pop     rsi
0x14001b631  pop     rbx
0x14001b632  pop     rbp
0x14001b633  retn
```
