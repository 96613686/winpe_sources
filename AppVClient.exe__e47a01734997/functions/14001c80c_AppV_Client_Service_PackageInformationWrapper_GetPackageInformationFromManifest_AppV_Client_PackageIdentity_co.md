# AppV::Client::Service::PackageInformationWrapper::GetPackageInformationFromManifest(AppV::Client::PackageIdentity const &,wchar_t * &,wchar_t * &,short *)

- ea: `0x14001c80c`
- end: `0x14001ceb4`
- name: `?GetPackageInformationFromManifest@PackageInformationWrapper@Service@Client@AppV@@AEAA_KAEBUPackageIdentity@34@AEAPEA_W1PEAF@Z`
- size: `1704`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Service::PackageInformationWrapper *__hidden this, const struct AppV::Client::PackageIdentity *, wchar_t **, wchar_t **, __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x14001b254`
- `0x14001d5e0`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x14001c80c`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x14003cc28`
- `0x14003cc80`
- `0x14006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001cc2f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001cc9f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001cc2f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14001cc9f`
- `OLEAUT32!__imp_SysAllocString` at `0x14001cc17`
- `OLEAUT32!__imp_SysAllocString` at `0x14001cc79`
- `OLEAUT32!__imp_SysAllocString` at `0x14001cc17`
- `OLEAUT32!__imp_SysAllocString` at `0x14001cc79`
- `OLEAUT32!__imp_SysFreeString` at `0x14001cc8a`
- `OLEAUT32!__imp_SysFreeString` at `0x14001cc8a`

## string_xrefs

- `0x14001cc28`: `admin\appman\appv\client\host\service\packageinformationwrapper.cpp`
- `0x14001cc3f`: `admin\appman\appv\client\host\service\packageinformationwrapper.cpp`
- `0x14001cc98`: `admin\appman\appv\client\host\service\packageinformationwrapper.cpp`
- `0x14001ccaf`: `admin\appman\appv\client\host\service\packageinformationwrapper.cpp`
- `0x14001c873`: `AppV::Client::Service::PackageInformationWrapper::GetPackageInformationFromManifest`
- `0x14001c9d6`: `AppV::Client::Service::PackageInformationWrapper::GetPackageInformationFromManifest`
- `0x14001cb06`: `AppV::Client::Service::PackageInformationWrapper::GetPackageInformationFromManifest`
- `0x14001cd0c`: `AppV::Client::Service::PackageInformationWrapper::GetPackageInformationFromManifest`
- `0x14001c8a6`: `Failed to get package manifest, error %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
unsigned __int64 __fastcall AppV::Client::Service::PackageInformationWrapper::GetPackageInformationFromManifest(
        AppV::Client::Service::PackageInformationWrapper *this,
        const struct AppV::Client::PackageIdentity *a2,
        wchar_t **a3,
        wchar_t **a4,
        __int16 *a5)
{
  __int64 v8; // r14
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rbx
  volatile signed __int32 *v13; // rbx
  __m128i si128; // xmm6
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rbx
  const OLECHAR *v28; // rcx
  wchar_t *v29; // rax
  char *v30; // rax
  const char *v31; // rax
  unsigned __int64 FileId; // r14
  __int64 v33; // rax
  const OLECHAR *v34; // rcx
  wchar_t *v35; // rax
  char *v36; // rax
  const char *v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rbx
  __int16 v44; // ax
  volatile signed __int32 *v45; // rbx
  __int64 v46; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v47; // [rsp+30h] [rbp-D8h] BYREF
  __int128 v48; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v49; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v50; // [rsp+58h] [rbp-B0h]
  __int128 v51; // [rsp+68h] [rbp-A0h] BYREF
  __int128 v52; // [rsp+78h] [rbp-90h]
  OLECHAR *v53[2]; // [rsp+88h] [rbp-80h] BYREF
  __m128i v54; // [rsp+98h] [rbp-70h]
  char *v55[4]; // [rsp+A8h] [rbp-60h] BYREF
  int v56; // [rsp+C8h] [rbp-40h]
  OLECHAR *psz[2]; // [rsp+D0h] [rbp-38h] BYREF
  __m128i v58; // [rsp+E0h] [rbp-28h]
  _QWORD v59[2]; // [rsp+F0h] [rbp-18h] BYREF
  char *v60[4]; // [rsp+100h] [rbp-8h] BYREF

  v48 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, const struct AppV::Client::PackageIdentity *, __int128 *))(**(_QWORD **)this + 32LL))(
         *(_QWORD *)this,
         a2,
         &v48);
  if ( (v8 & 0x8000000000LL) == 0 )
  {
    std::string::string(v55, "AppV::Client::Service::PackageInformationWrapper::GetPackageInformationFromManifest");
    v56 = 569;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v9);
    v51 = 0;
    v52 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v51, L"Failed to get package manifest, error %1%", 0x29u);
    v11 = AppV::Log::fmt(v10, v59, &v51);
    v47 = v8;
    v12 = AppV::LogFormatter::operator%(v11, &v47);
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v49, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v55, 8, (int)&v49, v12);
    std::wstring::~wstring((char **)&v49);
    v59[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v60);
    std::wstring::~wstring((char **)&v51);
    std::string::~string(v55);
    goto LABEL_3;
  }
  *(_OWORD *)v53 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v54 = si128;
  LOWORD(v53[0]) = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR **))(*(_QWORD *)v48 + 48LL))(v48, v53);
  if ( (v8 & 0x8000000000LL) == 0 )
  {
    std::string::string(v55, "AppV::Client::Service::PackageInformationWrapper::GetPackageInformationFromManifest");
    v56 = 580;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v16);
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v49,
      L"Failed to get version for package %1% package version %2%, error %3%",
      0x44u);
    v18 = AppV::Log::fmt(v17, v59, &v49);
    v19 = AppV::LogFormatter::operator%(v18, a2);
    v20 = AppV::LogFormatter::operator%(v19, (char *)a2 + 16);
    v47 = v8;
    v21 = AppV::LogFormatter::operator%(v20, &v47);
    v51 = 0;
    v52 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v51, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v55, 8, (int)&v51, v21);
    std::wstring::~wstring((char **)&v51);
    v59[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v60);
    std::wstring::~wstring((char **)&v49);
    std::string::~string(v55);
LABEL_10:
    std::wstring::~wstring((char **)v53);
LABEL_3:
    v13 = (volatile signed __int32 *)*((_QWORD *)&v48 + 1);
    if ( *((_QWORD *)&v48 + 1) )
      goto LABEL_4;
    return v8;
  }
  *(_OWORD *)psz = 0;
  v58 = si128;
  LOWORD(psz[0]) = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR **))(*(_QWORD *)v48 + 32LL))(v48, psz);
  if ( (v8 & 0x8000000000LL) == 0 )
  {
    std::string::string(v55, "AppV::Client::Service::PackageInformationWrapper::GetPackageInformationFromManifest");
    v56 = 591;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v22);
    v49 = 0;
    v50 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v49,
      L"Failed to get display name for package %1% package version %2%, error %3%",
      0x49u);
    v24 = AppV::Log::fmt(v23, v59, &v49);
    v25 = AppV::LogFormatter::operator%(v24, a2);
    v26 = AppV::LogFormatter::operator%(v25, (char *)a2 + 16);
    v47 = v8;
    v27 = AppV::LogFormatter::operator%(v26, &v47);
    v51 = 0;
    v52 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v51, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v55, 8, (int)&v51, v27);
    std::wstring::~wstring((char **)&v51);
    v59[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v60);
    std::wstring::~wstring((char **)&v49);
    std::string::~string(v55);
LABEL_13:
    std::wstring::~wstring((char **)psz);
    goto LABEL_10;
  }
  v28 = (const OLECHAR *)psz;
  if ( v58.m128i_i64[1] > 7uLL )
    v28 = psz[0];
  v29 = SysAllocString(v28);
  *a3 = v29;
  if ( !v29 )
  {
    v30 = strrchr("admin\\appman\\appv\\client\\host\\service\\packageinformationwrapper.cpp", 92);
    if ( v30 )
      v31 = v30 + 1;
    else
      v31 = "admin\\appman\\appv\\client\\host\\service\\packageinformationwrapper.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v31);
    v33 = 0x4A230000000ELL;
LABEL_21:
    v8 = v33 | (FileId << 52);
    goto LABEL_13;
  }
  v34 = (const OLECHAR *)v53;
  if ( v54.m128i_i64[1] > 7uLL )
    v34 = v53[0];
  v35 = SysAllocString(v34);
  *a4 = v35;
  if ( !v35 )
  {
    SysFreeString(*a3);
    *a3 = 0;
    v36 = strrchr("admin\\appman\\appv\\client\\host\\service\\packageinformationwrapper.cpp", 92);
    if ( v36 )
      v37 = v36 + 1;
    else
      v37 = "admin\\appman\\appv\\client\\host\\service\\packageinformationwrapper.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v37);
    v33 = 0x4B230000000ELL;
    goto LABEL_21;
  }
  if ( a5 )
  {
    LOBYTE(v46) = 0;
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)v48 + 160LL))(v48, &v46);
    if ( (v8 & 0x8000000000LL) == 0 )
    {
      std::string::string(v55, "AppV::Client::Service::PackageInformationWrapper::GetPackageInformationFromManifest");
      v56 = 616;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v38);
      v49 = 0;
      v50 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v49,
        L"Failed when checking if there is Asset Intelligence data for package %1% package version %2%, error %3%",
        0x67u);
      v40 = AppV::Log::fmt(v39, v59, &v49);
      v41 = AppV::LogFormatter::operator%(v40, a2);
      v42 = AppV::LogFormatter::operator%(v41, (char *)a2 + 16);
      v47 = v8;
      v43 = AppV::LogFormatter::operator%(v42, &v47);
      v51 = 0;
      v52 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v51, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v55, 8, (int)&v51, v43);
      std::wstring::~wstring((char **)&v51);
      v59[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v60);
      std::wstring::~wstring((char **)&v49);
      std::string::~string(v55);
      std::wstring::~wstring((char **)psz);
      std::wstring::~wstring((char **)v53);
      v13 = (volatile signed __int32 *)*((_QWORD *)&v48 + 1);
      if ( *((_QWORD *)&v48 + 1) )
      {
LABEL_4:
        if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
      return v8;
    }
    v44 = -1;
    if ( !(_BYTE)v46 )
      v44 = 0;
    *a5 = v44;
  }
  std::wstring::~wstring((char **)psz);
  std::wstring::~wstring((char **)v53);
  v45 = (volatile signed __int32 *)*((_QWORD *)&v48 + 1);
  if ( *((_QWORD *)&v48 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v48 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
      if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
    }
  }
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x14001c80c  mov     rax, rsp
0x14001c80f  push    rbp
0x14001c810  push    rbx
0x14001c811  push    rsi
0x14001c812  push    rdi
0x14001c813  push    r12
0x14001c815  push    r13
0x14001c817  push    r14
0x14001c819  push    r15
0x14001c81b  lea     rbp, [rax-78h]
0x14001c81f  sub     rsp, 138h
0x14001c826  movaps  xmmword ptr [rax-58h], xmm6
0x14001c82a  mov     rax, cs:__security_cookie
0x14001c831  xor     rax, rsp
0x14001c834  mov     qword ptr [rbp+70h+var_58], rax
0x14001c838  mov     rdi, r9
0x14001c83b  mov     rbx, r8
0x14001c83e  mov     r13, rdx
0x14001c841  mov     r15, [rbp+70h+arg_20]
0x14001c848  xorps   xmm0, xmm0
0x14001c84b  movdqu  [rsp+170h+var_148+8], xmm0
0x14001c851  mov     rcx, [rcx]
0x14001c854  mov     rax, [rcx]
0x14001c857  lea     r8, [rsp+170h+var_148+8]
0x14001c85c  mov     rax, [rax+20h]
0x14001c860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c865  mov     r14, rax
0x14001c868  bt      rax, 27h ; '''
0x14001c86d  jb      loc_14001C999
0x14001c873  lea     rdx, aAppvClientServ_11; "AppV::Client::Service::PackageInformati"...
0x14001c87a  lea     rcx, [rbp+70h+var_D0]
0x14001c87e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14001c883  mov     [rbp+70h+var_B0], 239h
0x14001c88a  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14001c88f  xorps   xmm0, xmm0
0x14001c892  movups  [rsp+170h+var_118+8], xmm0
0x14001c897  xorps   xmm1, xmm1
0x14001c89a  movdqu  xmmword ptr [rsp+170h+var_108+8], xmm1
0x14001c8a0  mov     r8d, 29h ; ')'
0x14001c8a6  lea     rdx, aFailedToGetPac; "Failed to get package manifest, error %"...
0x14001c8ad  lea     rcx, [rsp+170h+var_118+8]
0x14001c8b2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001c8b7  nop
0x14001c8b8  lea     r8, [rsp+170h+var_118+8]
0x14001c8bd  lea     rdx, [rbp+70h+var_88]
0x14001c8c1  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14001c8c6  nop
0x14001c8c7  mov     qword ptr [rsp+170h+var_148], r14
0x14001c8cc  lea     rdx, [rsp+170h+var_148]
0x14001c8d1  mov     rcx, rax
0x14001c8d4  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBVErrorCode@1@@Z; AppV::LogFormatter::operator%(AppV::ErrorCode const &)
0x14001c8d9  mov     rbx, rax
0x14001c8dc  xorps   xmm0, xmm0
0x14001c8df  movups  [rsp+170h+var_138+8], xmm0
0x14001c8e4  xorps   xmm1, xmm1
0x14001c8e7  movdqu  [rsp+170h+var_128+8], xmm1
0x14001c8ed  mov     r8d, 6
0x14001c8f3  lea     rdx, aClient; "Client"
0x14001c8fa  lea     rcx, [rsp+170h+var_138+8]
0x14001c8ff  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001c904  nop
0x14001c905  mov     r9, rbx
0x14001c908  lea     r8, [rsp+170h+var_138+8]
0x14001c90d  mov     edx, 8
0x14001c912  lea     rcx, [rbp+70h+var_D0]
0x14001c916  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14001c91b  nop
0x14001c91c  lea     rcx, [rsp+170h+var_138+8]
0x14001c921  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001c926  nop
0x14001c927  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14001c92e  mov     [rbp+70h+var_88], rax
0x14001c932  lea     rcx, [rbp+70h+var_78]
0x14001c936  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001c93b  nop
0x14001c93c  lea     rcx, [rsp+170h+var_118+8]
0x14001c941  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001c946  nop
0x14001c947  lea     rcx, [rbp+70h+var_D0]
0x14001c94b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14001c950  nop
0x14001c951  mov     rbx, qword ptr [rsp+170h+var_138]
0x14001c956  test    rbx, rbx
0x14001c959  jz      short loc_14001C991
0x14001c95b  or      edi, 0FFFFFFFFh
0x14001c95e  mov     eax, edi
0x14001c960  lock xadd [rbx+8], eax
0x14001c965  add     eax, edi
0x14001c967  jnz     short loc_14001C991
0x14001c969  mov     rax, [rbx]
0x14001c96c  mov     rcx, rbx
0x14001c96f  mov     rax, [rax]
0x14001c972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c977  mov     eax, edi
0x14001c979  lock xadd [rbx+0Ch], eax
0x14001c97e  add     eax, edi
0x14001c980  jnz     short loc_14001C991
0x14001c982  mov     rax, [rbx]
0x14001c985  mov     rcx, rbx
0x14001c988  mov     rax, [rax+8]
0x14001c98c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c991  mov     rax, r14
0x14001c994  jmp     loc_14001CE8C
0x14001c999  xorps   xmm0, xmm0
0x14001c99c  movups  xmmword ptr [rbp+70h+var_F0], xmm0
0x14001c9a0  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14001c9a8  movdqu  [rbp+70h+var_E0], xmm6
0x14001c9ad  xor     esi, esi
0x14001c9af  mov     word ptr [rbp+70h+var_F0], si
0x14001c9b3  mov     rcx, qword ptr [rsp+170h+var_148+8]
0x14001c9b8  mov     rax, [rcx]
0x14001c9bb  lea     rdx, [rbp+70h+var_F0]
0x14001c9bf  mov     rax, [rax+30h]
0x14001c9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c9c8  mov     r14, rax
0x14001c9cb  bt      rax, 27h ; '''
0x14001c9d0  jb      loc_14001CAD3
0x14001c9d6  lea     rdx, aAppvClientServ_11; "AppV::Client::Service::PackageInformati"...
0x14001c9dd  lea     rcx, [rbp+70h+var_D0]
0x14001c9e1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14001c9e6  mov     [rbp+70h+var_B0], 244h
0x14001c9ed  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14001c9f2  xorps   xmm0, xmm0
0x14001c9f5  movups  [rsp+170h+var_138+8], xmm0
0x14001c9fa  xorps   xmm1, xmm1
0x14001c9fd  movdqu  [rsp+170h+var_128+8], xmm1
0x14001ca03  lea     r8d, [rsi+44h]
0x14001ca07  lea     rdx, aFailedToGetVer; "Failed to get version for package %1% p"...
0x14001ca0e  lea     rcx, [rsp+170h+var_138+8]
0x14001ca13  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001ca18  nop
0x14001ca19  lea     r8, [rsp+170h+var_138+8]
0x14001ca1e  lea     rdx, [rbp+70h+var_88]
0x14001ca22  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14001ca27  nop
0x14001ca28  mov     rdx, r13
0x14001ca2b  mov     rcx, rax
0x14001ca2e  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBU_GUID@@@Z; AppV::LogFormatter::operator%(_GUID const &)
0x14001ca33  lea     rdx, [r13+10h]
0x14001ca37  mov     rcx, rax
0x14001ca3a  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBU_GUID@@@Z; AppV::LogFormatter::operator%(_GUID const &)
0x14001ca3f  mov     qword ptr [rsp+170h+var_148], r14
0x14001ca44  lea     rdx, [rsp+170h+var_148]
0x14001ca49  mov     rcx, rax
0x14001ca4c  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBVErrorCode@1@@Z; AppV::LogFormatter::operator%(AppV::ErrorCode const &)
0x14001ca51  mov     rbx, rax
0x14001ca54  xorps   xmm0, xmm0
0x14001ca57  movups  [rsp+170h+var_118+8], xmm0
0x14001ca5c  xorps   xmm1, xmm1
0x14001ca5f  movdqu  xmmword ptr [rsp+170h+var_108+8], xmm1
0x14001ca65  lea     r8d, [rsi+6]
0x14001ca69  lea     rdx, aClient; "Client"
0x14001ca70  lea     rcx, [rsp+170h+var_118+8]
0x14001ca75  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001ca7a  nop
0x14001ca7b  mov     r9, rbx
0x14001ca7e  lea     r8, [rsp+170h+var_118+8]
0x14001ca83  lea     edx, [rsi+8]
0x14001ca86  lea     rcx, [rbp+70h+var_D0]
0x14001ca8a  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14001ca8f  nop
0x14001ca90  lea     rcx, [rsp+170h+var_118+8]
0x14001ca95  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001ca9a  nop
0x14001ca9b  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14001caa2  mov     [rbp+70h+var_88], rax
0x14001caa6  lea     rcx, [rbp+70h+var_78]
0x14001caaa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001caaf  nop
0x14001cab0  lea     rcx, [rsp+170h+var_138+8]
0x14001cab5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001caba  nop
0x14001cabb  lea     rcx, [rbp+70h+var_D0]
0x14001cabf  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14001cac4  nop
0x14001cac5  lea     rcx, [rbp+70h+var_F0]
0x14001cac9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001cace  jmp     loc_14001C951
0x14001cad3  xorps   xmm0, xmm0
0x14001cad6  movups  xmmword ptr [rbp+70h+psz], xmm0
0x14001cada  movdqu  [rbp+70h+var_98], xmm6
0x14001cadf  mov     word ptr [rbp+70h+psz], si
0x14001cae3  mov     rcx, qword ptr [rsp+170h+var_148+8]
0x14001cae8  mov     rax, [rcx]
0x14001caeb  lea     rdx, [rbp+70h+psz]
0x14001caef  mov     rax, [rax+20h]
0x14001caf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001caf8  mov     r14, rax
0x14001cafb  bt      rax, 27h ; '''
0x14001cb00  jb      loc_14001CC09
0x14001cb06  lea     rdx, aAppvClientServ_11; "AppV::Client::Service::PackageInformati"...
0x14001cb0d  lea     rcx, [rbp+70h+var_D0]
0x14001cb11  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14001cb16  mov     [rbp+70h+var_B0], 24Fh
0x14001cb1d  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14001cb22  xorps   xmm0, xmm0
0x14001cb25  movups  [rsp+170h+var_138+8], xmm0
0x14001cb2a  xorps   xmm1, xmm1
0x14001cb2d  movdqu  [rsp+170h+var_128+8], xmm1
0x14001cb33  mov     r8d, 49h ; 'I'
0x14001cb39  lea     rdx, aFailedToGetDis; "Failed to get display name for package "...
0x14001cb40  lea     rcx, [rsp+170h+var_138+8]
0x14001cb45  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001cb4a  nop
0x14001cb4b  lea     r8, [rsp+170h+var_138+8]
0x14001cb50  lea     rdx, [rbp+70h+var_88]
0x14001cb54  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14001cb59  nop
0x14001cb5a  mov     rdx, r13
0x14001cb5d  mov     rcx, rax
0x14001cb60  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBU_GUID@@@Z; AppV::LogFormatter::operator%(_GUID const &)
0x14001cb65  lea     rdx, [r13+10h]
0x14001cb69  mov     rcx, rax
0x14001cb6c  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBU_GUID@@@Z; AppV::LogFormatter::operator%(_GUID const &)
0x14001cb71  mov     qword ptr [rsp+170h+var_148], r14
0x14001cb76  lea     rdx, [rsp+170h+var_148]
0x14001cb7b  mov     rcx, rax
0x14001cb7e  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBVErrorCode@1@@Z; AppV::LogFormatter::operator%(AppV::ErrorCode const &)
0x14001cb83  mov     rbx, rax
0x14001cb86  xorps   xmm0, xmm0
0x14001cb89  movups  [rsp+170h+var_118+8], xmm0
0x14001cb8e  xorps   xmm1, xmm1
0x14001cb91  movdqu  xmmword ptr [rsp+170h+var_108+8], xmm1
0x14001cb97  mov     r8d, 6
0x14001cb9d  lea     rdx, aClient; "Client"
0x14001cba4  lea     rcx, [rsp+170h+var_118+8]
0x14001cba9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14001cbae  nop
0x14001cbaf  mov     r9, rbx
0x14001cbb2  lea     r8, [rsp+170h+var_118+8]
0x14001cbb7  mov     edx, 8
0x14001cbbc  lea     rcx, [rbp+70h+var_D0]
0x14001cbc0  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14001cbc5  nop
0x14001cbc6  lea     rcx, [rsp+170h+var_118+8]
0x14001cbcb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001cbd0  nop
0x14001cbd1  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14001cbd8  mov     [rbp+70h+var_88], rax
0x14001cbdc  lea     rcx, [rbp+70h+var_78]
0x14001cbe0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001cbe5  nop
0x14001cbe6  lea     rcx, [rsp+170h+var_138+8]
0x14001cbeb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001cbf0  nop
0x14001cbf1  lea     rcx, [rbp+70h+var_D0]
0x14001cbf5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14001cbfa  nop
0x14001cbfb  lea     rcx, [rbp+70h+psz]
0x14001cbff  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14001cc04  jmp     loc_14001CAC5
0x14001cc09  lea     rcx, [rbp+70h+psz]
0x14001cc0d  cmp     qword ptr [rbp+70h+var_98+8], 7
0x14001cc12  cmova   rcx, [rbp+70h+psz]; psz
0x14001cc17  call    cs:__imp_SysAllocString
0x14001cc1d  mov     [rbx], rax
0x14001cc20  test    rax, rax
0x14001cc23  jnz     short loc_14001CC6B
0x14001cc25  lea     edx, [rax+5Ch]; Ch
0x14001cc28  lea     rcx, aAdminAppmanApp_11; "admin\\appman\\appv\\client\\host\\serv"...
0x14001cc2f  call    cs:__imp_strrchr
0x14001cc35  test    rax, rax
0x14001cc38  jz      short loc_14001CC3F
0x14001cc3a  inc     rax
0x14001cc3d  jmp     short loc_14001CC46
0x14001cc3f  lea     rax, aAdminAppmanApp_11; "admin\\appman\\appv\\client\\host\\serv"...
0x14001cc46  mov     rdx, rax; char *
0x14001cc49  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14001cc50  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14001cc55  mov     r14, rax
0x14001cc58  mov     rax, 4A230000000Eh
0x14001cc62  shl     r14, 34h
0x14001cc66  or      r14, rax
0x14001cc69  jmp     short loc_14001CBFB
0x14001cc6b  lea     rcx, [rbp+70h+var_F0]
0x14001cc6f  cmp     qword ptr [rbp+70h+var_E0+8], 7
0x14001cc74  cmova   rcx, [rbp+70h+var_F0]; psz
0x14001cc79  call    cs:__imp_SysAllocString
0x14001cc7f  mov     [rdi], rax
0x14001cc82  test    rax, rax
0x14001cc85  jnz     short loc_14001CCD4
0x14001cc87  mov     rcx, [rbx]; bstrString
0x14001cc8a  call    cs:__imp_SysFreeString
0x14001cc90  mov     [rbx], rsi
0x14001cc93  mov     edx, 5Ch ; '\'; Ch
0x14001cc98  lea     rcx, aAdminAppmanApp_11; "admin\\appman\\appv\\client\\host\\serv"...
0x14001cc9f  call    cs:__imp_strrchr
0x14001cca5  test    rax, rax
0x14001cca8  jz      short loc_14001CCAF
0x14001ccaa  inc     rax
0x14001ccad  jmp     short loc_14001CCB6
0x14001ccaf  lea     rax, aAdminAppmanApp_11; "admin\\appman\\appv\\client\\host\\serv"...
0x14001ccb6  mov     rdx, rax; char *
0x14001ccb9  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14001ccc0  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14001ccc5  mov     r14, rax
0x14001ccc8  mov     rax, 4B230000000Eh
0x14001ccd2  jmp     short loc_14001CC62
0x14001ccd4  or      edi, 0FFFFFFFFh
0x14001ccd7  test    r15, r15
  ... truncated ...
```
