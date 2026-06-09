# AppV::Client::Service::AppVClientImpl::GetDynamicDeploymentConfigurationPath(wchar_t *,wchar_t *,wchar_t * *,unsigned __int64 *)

- ea: `0x140025820`
- end: `0x140025bcd`
- name: `?GetDynamicDeploymentConfigurationPath@AppVClientImpl@Service@Client@AppV@@UEAAJPEA_W0PEAPEA_WPEA_K@Z`
- size: `941`
- prototype: `int(AppV::Client::Service::AppVClientImpl *__hidden this, wchar_t *, wchar_t *, wchar_t **, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140004280`
- `0x140006304`
- `0x140008224`
- `0x140018bec`
- `0x1400233dc`
- `0x140024fa8`
- `0x140025820`
- `0x140026dd0`
- `0x140028e00`
- `0x14003a198`
- `0x14003a24c`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x1400258e0`
- `ADVAPI32!EventActivityIdControl` at `0x140025a47`
- `ADVAPI32!EventActivityIdControl` at `0x140025b0f`
- `ADVAPI32!EventActivityIdControl` at `0x140025b72`
- `ADVAPI32!EventActivityIdControl` at `0x140025b9f`
- `ADVAPI32!EventActivityIdControl` at `0x1400258e0`
- `ADVAPI32!EventActivityIdControl` at `0x140025a47`
- `ADVAPI32!EventActivityIdControl` at `0x140025b0f`
- `ADVAPI32!EventActivityIdControl` at `0x140025b72`
- `ADVAPI32!EventActivityIdControl` at `0x140025b9f`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140025a81`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140025a81`
- `OLEAUT32!__imp_SysAllocString` at `0x140025a65`
- `OLEAUT32!__imp_SysAllocString` at `0x140025a65`

## string_xrefs

- `0x140025a7a`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x140025a91`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x140025860`: `GetDynamicDeploymentConfigurationPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppV::Client::Service::AppVClientImpl::GetDynamicDeploymentConfigurationPath(
        AppV::Client::Service::AppVClientImpl *this,
        wchar_t *a2,
        wchar_t *a3,
        wchar_t **a4,
        unsigned __int64 *a5)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned __int64 PackageIDAndPackageVersionID; // rax
  unsigned __int64 ClientCatalog; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  unsigned __int64 v19; // rax
  const OLECHAR *v20; // rcx
  wchar_t *v21; // rax
  char *v22; // rax
  const char *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rdx
  __int64 v27; // r8
  _BYTE v28[8]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v29[16]; // [rsp+28h] [rbp-D8h] BYREF
  int v30; // [rsp+38h] [rbp-C8h]
  struct AppV::Client::ClientCatalog *v31; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v32[4]; // [rsp+48h] [rbp-B8h] BYREF
  GUID ActivityId; // [rsp+4Ch] [rbp-B4h] BYREF
  struct _GUID v34; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID v35; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v36[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v37; // [rsp+B0h] [rbp-50h] BYREF
  __m128i si128; // [rsp+C0h] [rbp-40h]
  OLECHAR *psz[2]; // [rsp+D0h] [rbp-30h] BYREF
  __m128i v40; // [rsp+E0h] [rbp-20h]
  _OWORD v41[3]; // [rsp+100h] [rbp+0h] BYREF

  AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>((__int64)v32);
  AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(
    (AppV::Client::Service::SmartComMethodLogger *)v29,
    L"GetDynamicDeploymentConfigurationPath");
  if ( !a2 || !a3 || !a4 || !a5 )
  {
    v30 = -2147024809;
    goto LABEL_31;
  }
  *a4 = 0;
  v28[0] = 0;
  v10 = AppV::Client::Service::AppVClientImpl::APICaller::Initialize(
          (AppV::Client::Service::AppVClientImpl::APICaller *)v28,
          0,
          a5);
  v11 = v10;
  if ( v10 < 0 )
  {
    v30 = v10;
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v28);
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)v29,
      v12,
      v13);
    if ( v32[0] )
      EventActivityIdControl(2u, &ActivityId);
    return v11;
  }
  v34 = GUID_NULL;
  v35 = GUID_NULL;
  v36[0] = 0;
  v36[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v36[0]) = 0;
  PackageIDAndPackageVersionID = AppV::Client::Service::AppVClientImpl::GetPackageIDAndPackageVersionID(
                                   a2,
                                   a3,
                                   &v34,
                                   &v35);
  if ( (PackageIDAndPackageVersionID & 0x8000000000LL) == 0 )
  {
    *a5 = PackageIDAndPackageVersionID;
    v30 = -2147024809;
    std::wstring::~wstring((char **)v36);
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v28);
LABEL_31:
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)v29,
      v8,
      v9);
    if ( v32[0] )
      EventActivityIdControl(2u, &ActivityId);
    return 2147942487LL;
  }
  v31 = 0;
  ClientCatalog = AppV::Client::Service::AppVClientImpl::GetClientCatalog(&v31);
  if ( (ClientCatalog & 0x8000000000LL) == 0 )
  {
    *a5 = ClientCatalog;
    v30 = -2147467259;
    std::wstring::~wstring((char **)v36);
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v28);
LABEL_15:
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)v29,
      v17,
      v18);
    if ( v32[0] )
      EventActivityIdControl(2u, &ActivityId);
    return 2147500037LL;
  }
  v37 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v37) = 0;
  *(_OWORD *)psz = 0;
  v40 = si128;
  LOWORD(psz[0]) = 0;
  v41[0] = 0;
  v41[1] = si128;
  LOWORD(v41[0]) = 0;
  v19 = (*(__int64 (__fastcall **)(struct AppV::Client::ClientCatalog *, struct _GUID *, __int128 *))(*(_QWORD *)v31 + 48LL))(
          v31,
          &v34,
          &v37);
  if ( (v19 & 0x8000000000LL) == 0 )
  {
    *a5 = v19;
    v30 = -2147467259;
    std::wstring::~wstring((char **)v41);
    std::wstring::~wstring((char **)psz);
    std::wstring::~wstring((char **)&v37);
    std::wstring::~wstring((char **)v36);
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v28);
    goto LABEL_15;
  }
  v20 = (const OLECHAR *)psz;
  if ( v40.m128i_i64[1] > 7uLL )
    v20 = psz[0];
  v21 = SysAllocString(v20);
  *a4 = v21;
  if ( v21 )
  {
    *a5 = 0x8000000000LL;
    v30 = 0;
    std::wstring::~wstring((char **)v41);
    std::wstring::~wstring((char **)psz);
    std::wstring::~wstring((char **)&v37);
    std::wstring::~wstring((char **)v36);
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v28);
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)v29,
      v26,
      v27);
    if ( v32[0] )
      EventActivityIdControl(2u, &ActivityId);
    return 0;
  }
  else
  {
    v22 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
    if ( v22 )
      v23 = v22 + 1;
    else
      v23 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
    *a5 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v23) << 52)
        | 0x10C230000000ELL;
    v30 = -2147024882;
    std::wstring::~wstring((char **)v41);
    std::wstring::~wstring((char **)psz);
    std::wstring::~wstring((char **)&v37);
    std::wstring::~wstring((char **)v36);
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v28);
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)v29,
      v24,
      v25);
    if ( v32[0] )
      EventActivityIdControl(2u, &ActivityId);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x140025820  mov     [rsp-8+arg_0], rbx
0x140025825  push    rbp
0x140025826  push    rsi
0x140025827  push    rdi
0x140025828  push    r14
0x14002582a  push    r15
0x14002582c  lea     rbp, [rsp-40h]
0x140025831  sub     rsp, 140h
0x140025838  mov     rax, cs:__security_cookie
0x14002583f  xor     rax, rsp
0x140025842  mov     [rbp+60h+var_30], rax
0x140025846  mov     rsi, r9
0x140025849  mov     r14, r8
0x14002584c  mov     r15, rdx
0x14002584f  mov     rbx, [rbp+60h+arg_20]
0x140025856  lea     rcx, [rsp+160h+var_118]
0x14002585b  call    ??0?$ScopedActivity@VUserModeActivityIdControl@ETW@AppV@@@ETW@AppV@@QEAA@XZ; AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(void)
0x140025860  lea     rdx, aGetdynamicdepl; "GetDynamicDeploymentConfigurationPath"
0x140025867  lea     rcx, [rsp+160h+var_138]; this
0x14002586c  call    ??0SmartComMethodLogger@Service@Client@AppV@@QEAA@PEB_W@Z; AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(wchar_t const *)
0x140025871  test    r15, r15
0x140025874  jz      loc_140025B7C
0x14002587a  test    r14, r14
0x14002587d  jz      loc_140025B7C
0x140025883  test    rsi, rsi
0x140025886  jz      loc_140025B7C
0x14002588c  test    rbx, rbx
0x14002588f  jz      loc_140025B7C
0x140025895  mov     qword ptr [rsi], 0
0x14002589c  mov     [rsp+160h+var_140], 0
0x1400258a1  mov     r8, rbx; unsigned __int64 *
0x1400258a4  xor     edx, edx; bool
0x1400258a6  lea     rcx, [rsp+160h+var_140]; this
0x1400258ab  call    ?Initialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJ_NAEA_K@Z; AppV::Client::Service::AppVClientImpl::APICaller::Initialize(bool,unsigned __int64 &)
0x1400258b0  mov     edi, eax
0x1400258b2  test    eax, eax
0x1400258b4  jns     short loc_1400258ED
0x1400258b6  mov     [rsp+160h+var_128], eax
0x1400258ba  lea     rcx, [rsp+160h+var_140]; this
0x1400258bf  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x1400258c4  nop
0x1400258c5  lea     rcx, [rsp+160h+var_138]; this
0x1400258ca  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x1400258cf  cmp     [rsp+160h+var_118], 0
0x1400258d4  jz      short loc_1400258E6
0x1400258d6  lea     rdx, [rsp+160h+ActivityId]; ActivityId
0x1400258db  mov     ecx, 2; ControlCode
0x1400258e0  call    cs:__imp_EventActivityIdControl
0x1400258e6  mov     eax, edi
0x1400258e8  jmp     loc_140025BAA
0x1400258ed  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400258f4  movdqu  xmmword ptr [rsp+160h+var_F0.Data1], xmm0
0x1400258fa  movdqu  xmmword ptr [rbp+60h+var_E0.Data1], xmm0
0x1400258ff  xorps   xmm0, xmm0
0x140025902  movups  [rbp+60h+var_D0], xmm0
0x140025906  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14002590e  movdqa  [rbp+60h+var_C0], xmm1
0x140025913  xor     eax, eax
0x140025915  mov     word ptr [rbp+60h+var_D0], ax
0x140025919  lea     r9, [rbp+60h+var_E0]; struct _GUID *
0x14002591d  lea     r8, [rsp+160h+var_F0]; struct _GUID *
0x140025922  mov     rdx, r14; wchar_t *
0x140025925  mov     rcx, r15; wchar_t *
0x140025928  call    ?GetPackageIDAndPackageVersionID@AppVClientImpl@Service@Client@AppV@@CA_KQEA_W0AEAU_GUID@@1@Z; AppV::Client::Service::AppVClientImpl::GetPackageIDAndPackageVersionID(wchar_t * const,wchar_t * const,_GUID &,_GUID &)
0x14002592d  mov     rdi, 8000000000h
0x140025937  test    rdi, rax
0x14002593a  jnz     short loc_140025961
0x14002593c  mov     [rbx], rax
0x14002593f  mov     [rsp+160h+var_128], 80070057h
0x140025947  lea     rcx, [rbp+60h+var_D0]
0x14002594b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025950  nop
0x140025951  lea     rcx, [rsp+160h+var_140]; this
0x140025956  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x14002595b  nop
0x14002595c  jmp     loc_140025B84
0x140025961  mov     [rsp+160h+var_120], 0
0x14002596a  lea     rcx, [rsp+160h+var_120]; struct AppV::Client::ClientCatalog **
0x14002596f  call    ?GetClientCatalog@AppVClientImpl@Service@Client@AppV@@CA_KAEAPEBVClientCatalog@34@@Z; AppV::Client::Service::AppVClientImpl::GetClientCatalog(AppV::Client::ClientCatalog const * &)
0x140025974  test    rdi, rax
0x140025977  jnz     short loc_14002599E
0x140025979  mov     [rbx], rax
0x14002597c  mov     [rsp+160h+var_128], 80004005h
0x140025984  lea     rcx, [rbp+60h+var_D0]
0x140025988  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002598d  nop
0x14002598e  lea     rcx, [rsp+160h+var_140]; this
0x140025993  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140025998  nop
0x140025999  jmp     loc_140025A2C
0x14002599e  xorps   xmm0, xmm0
0x1400259a1  movups  [rbp+60h+var_B0], xmm0
0x1400259a5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400259ad  movdqa  [rbp+60h+var_A0], xmm1
0x1400259b2  xor     eax, eax
0x1400259b4  mov     word ptr [rbp+60h+var_B0], ax
0x1400259b8  movups  xmmword ptr [rbp+60h+psz], xmm0
0x1400259bc  movdqa  [rbp+60h+var_80], xmm1
0x1400259c1  mov     word ptr [rbp+60h+psz], ax
0x1400259c5  movups  [rbp+60h+var_60], xmm0
0x1400259c9  movdqa  [rbp+60h+var_50], xmm1
0x1400259ce  mov     word ptr [rbp+60h+var_60], ax
0x1400259d2  mov     rcx, [rsp+160h+var_120]
0x1400259d7  mov     rax, [rcx]
0x1400259da  lea     r8, [rbp+60h+var_B0]
0x1400259de  lea     rdx, [rsp+160h+var_F0]
0x1400259e3  mov     rax, [rax+30h]
0x1400259e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400259ec  test    rdi, rax
0x1400259ef  jnz     short loc_140025A57
0x1400259f1  mov     [rbx], rax
0x1400259f4  mov     [rsp+160h+var_128], 80004005h
0x1400259fc  lea     rcx, [rbp+60h+var_60]
0x140025a00  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025a05  lea     rcx, [rbp+60h+psz]
0x140025a09  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025a0e  lea     rcx, [rbp+60h+var_B0]
0x140025a12  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025a17  lea     rcx, [rbp+60h+var_D0]
0x140025a1b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025a20  nop
0x140025a21  lea     rcx, [rsp+160h+var_140]; this
0x140025a26  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140025a2b  nop
0x140025a2c  lea     rcx, [rsp+160h+var_138]; this
0x140025a31  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x140025a36  cmp     [rsp+160h+var_118], 0
0x140025a3b  jz      short loc_140025A4D
0x140025a3d  lea     rdx, [rsp+160h+ActivityId]; ActivityId
0x140025a42  mov     ecx, 2; ControlCode
0x140025a47  call    cs:__imp_EventActivityIdControl
0x140025a4d  mov     eax, 80004005h
0x140025a52  jmp     loc_140025BAA
0x140025a57  lea     rcx, [rbp+60h+psz]
0x140025a5b  cmp     qword ptr [rbp+60h+var_80+8], 7
0x140025a60  cmova   rcx, [rbp+60h+psz]; psz
0x140025a65  call    cs:__imp_SysAllocString
0x140025a6b  mov     [rsi], rax
0x140025a6e  test    rax, rax
0x140025a71  jnz     loc_140025B1C
0x140025a77  lea     edx, [rax+5Ch]; Ch
0x140025a7a  lea     rcx, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140025a81  call    cs:__imp_strrchr
0x140025a87  test    rax, rax
0x140025a8a  jz      short loc_140025A91
0x140025a8c  inc     rax
0x140025a8f  jmp     short loc_140025A98
0x140025a91  lea     rax, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140025a98  mov     rdx, rax; char *
0x140025a9b  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140025aa2  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140025aa7  shl     rax, 34h
0x140025aab  mov     rcx, 10C230000000Eh
0x140025ab5  or      rax, rcx
0x140025ab8  mov     [rbx], rax
0x140025abb  mov     ebx, 8007000Eh
0x140025ac0  mov     [rsp+160h+var_128], ebx
0x140025ac4  lea     rcx, [rbp+60h+var_60]
0x140025ac8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025acd  lea     rcx, [rbp+60h+psz]
0x140025ad1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025ad6  lea     rcx, [rbp+60h+var_B0]
0x140025ada  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025adf  lea     rcx, [rbp+60h+var_D0]
0x140025ae3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025ae8  nop
0x140025ae9  lea     rcx, [rsp+160h+var_140]; this
0x140025aee  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140025af3  nop
0x140025af4  lea     rcx, [rsp+160h+var_138]; this
0x140025af9  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x140025afe  cmp     [rsp+160h+var_118], 0
0x140025b03  jz      short loc_140025B15
0x140025b05  lea     rdx, [rsp+160h+ActivityId]; ActivityId
0x140025b0a  mov     ecx, 2; ControlCode
0x140025b0f  call    cs:__imp_EventActivityIdControl
0x140025b15  mov     eax, ebx
0x140025b17  jmp     loc_140025BAA
0x140025b1c  mov     [rbx], rdi
0x140025b1f  mov     [rsp+160h+var_128], 0
0x140025b27  lea     rcx, [rbp+60h+var_60]
0x140025b2b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025b30  lea     rcx, [rbp+60h+psz]
0x140025b34  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025b39  lea     rcx, [rbp+60h+var_B0]
0x140025b3d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025b42  lea     rcx, [rbp+60h+var_D0]
0x140025b46  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025b4b  nop
0x140025b4c  lea     rcx, [rsp+160h+var_140]; this
0x140025b51  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140025b56  nop
0x140025b57  lea     rcx, [rsp+160h+var_138]; this
0x140025b5c  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x140025b61  cmp     [rsp+160h+var_118], 0
0x140025b66  jz      short loc_140025B78
0x140025b68  lea     rdx, [rsp+160h+ActivityId]; ActivityId
0x140025b6d  mov     ecx, 2; ControlCode
0x140025b72  call    cs:__imp_EventActivityIdControl
0x140025b78  xor     eax, eax
0x140025b7a  jmp     short loc_140025BAA
0x140025b7c  mov     [rsp+160h+var_128], 80070057h
0x140025b84  lea     rcx, [rsp+160h+var_138]; this
0x140025b89  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x140025b8e  cmp     [rsp+160h+var_118], 0
0x140025b93  jz      short loc_140025BA5
0x140025b95  lea     rdx, [rsp+160h+ActivityId]; ActivityId
0x140025b9a  mov     ecx, 2; ControlCode
0x140025b9f  call    cs:__imp_EventActivityIdControl
0x140025ba5  mov     eax, 80070057h
0x140025baa  mov     rcx, [rbp+60h+var_30]
0x140025bae  xor     rcx, rsp; StackCookie
0x140025bb1  call    __security_check_cookie
0x140025bb6  mov     rbx, [rsp+160h+arg_0]
0x140025bbe  add     rsp, 140h
0x140025bc5  pop     r15
0x140025bc7  pop     r14
0x140025bc9  pop     rdi
0x140025bca  pop     rsi
0x140025bcb  pop     rbp
0x140025bcc  retn
```
