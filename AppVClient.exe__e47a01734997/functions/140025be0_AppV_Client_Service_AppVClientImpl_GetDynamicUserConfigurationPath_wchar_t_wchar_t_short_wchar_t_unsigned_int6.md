# AppV::Client::Service::AppVClientImpl::GetDynamicUserConfigurationPath(wchar_t *,wchar_t *,short,wchar_t * *,unsigned __int64 *)

- ea: `0x140025be0`
- end: `0x140026046`
- name: `?GetDynamicUserConfigurationPath@AppVClientImpl@Service@Client@AppV@@UEAAJPEA_W0FPEAPEA_WPEA_K@Z`
- size: `1126`
- prototype: `int(AppV::Client::Service::AppVClientImpl *__hidden this, wchar_t *, wchar_t *, __int16, wchar_t **, unsigned __int64 *)`
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
- `0x140025be0`
- `0x140026dd0`
- `0x140028e00`
- `0x14003a198`
- `0x14003a24c`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x140025ca8`
- `ADVAPI32!EventActivityIdControl` at `0x140025ecf`
- `ADVAPI32!EventActivityIdControl` at `0x140025f82`
- `ADVAPI32!EventActivityIdControl` at `0x140025fe6`
- `ADVAPI32!EventActivityIdControl` at `0x140026013`
- `ADVAPI32!EventActivityIdControl` at `0x140025ca8`
- `ADVAPI32!EventActivityIdControl` at `0x140025ecf`
- `ADVAPI32!EventActivityIdControl` at `0x140025f82`
- `ADVAPI32!EventActivityIdControl` at `0x140025fe6`
- `ADVAPI32!EventActivityIdControl` at `0x140026013`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140025dc7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140025dfd`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140025e28`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140025e59`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140025f05`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140025dc7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140025dfd`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140025e28`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140025e59`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140025f05`
- `OLEAUT32!__imp_SysAllocString` at `0x140025eed`
- `OLEAUT32!__imp_SysAllocString` at `0x140025eed`

## string_xrefs

- `0x140025dbd`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x140025c28`: `GetDynamicUserConfigurationPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppV::Client::Service::AppVClientImpl::GetDynamicUserConfigurationPath(
        AppV::Client::Service::AppVClientImpl *this,
        wchar_t *a2,
        wchar_t *a3,
        __int16 a4,
        wchar_t **a5,
        unsigned __int64 *a6)
{
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned __int64 PackageIDAndPackageVersionID; // rax
  unsigned __int64 ClientCatalog; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  unsigned __int64 v21; // rdi
  char *v22; // rax
  const char *v23; // rax
  char *v24; // rax
  const char *v25; // rax
  char *v26; // rax
  const char *v27; // rax
  char *v28; // rax
  const char *v29; // rax
  const OLECHAR *v30; // rcx
  wchar_t *v31; // rax
  char *v32; // rax
  const char *v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r8
  _BYTE v38[8]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v39[16]; // [rsp+38h] [rbp-C8h] BYREF
  int v40; // [rsp+48h] [rbp-B8h]
  struct AppV::Client::ClientCatalog *v41; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v42[4]; // [rsp+58h] [rbp-A8h] BYREF
  GUID ActivityId; // [rsp+5Ch] [rbp-A4h] BYREF
  struct _GUID v44; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v45; // [rsp+90h] [rbp-70h] BYREF
  _OWORD v46[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v47; // [rsp+C0h] [rbp-40h] BYREF
  __m128i si128; // [rsp+D0h] [rbp-30h]
  OLECHAR *psz[2]; // [rsp+E0h] [rbp-20h] BYREF
  __m128i v50; // [rsp+F0h] [rbp-10h]

  AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>((__int64)v42);
  AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(
    (AppV::Client::Service::SmartComMethodLogger *)v39,
    L"GetDynamicUserConfigurationPath");
  if ( !a2 || !a3 || !a5 || !a6 )
  {
    v40 = -2147024809;
    goto LABEL_48;
  }
  *a5 = 0;
  v38[0] = 0;
  v11 = AppV::Client::Service::AppVClientImpl::APICaller::Initialize(
          (AppV::Client::Service::AppVClientImpl::APICaller *)v38,
          0,
          a6);
  v12 = v11;
  if ( v11 < 0 )
  {
    v40 = v11;
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v38);
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)v39,
      v13,
      v14);
    if ( v42[0] )
      EventActivityIdControl(2u, &ActivityId);
    return v12;
  }
  v44 = GUID_NULL;
  v45 = GUID_NULL;
  v46[0] = 0;
  v46[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v46[0]) = 0;
  PackageIDAndPackageVersionID = AppV::Client::Service::AppVClientImpl::GetPackageIDAndPackageVersionID(
                                   a2,
                                   a3,
                                   &v44,
                                   &v45);
  if ( (PackageIDAndPackageVersionID & 0x8000000000LL) == 0 )
  {
    *a6 = PackageIDAndPackageVersionID;
    v40 = -2147024809;
    std::wstring::~wstring((char **)v46);
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v38);
LABEL_48:
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)v39,
      v9,
      v10);
    if ( v42[0] )
      EventActivityIdControl(2u, &ActivityId);
    return 2147942487LL;
  }
  v41 = 0;
  ClientCatalog = AppV::Client::Service::AppVClientImpl::GetClientCatalog(&v41);
  if ( (ClientCatalog & 0x8000000000LL) == 0 )
  {
    *a6 = ClientCatalog;
    v40 = -2147467259;
    std::wstring::~wstring((char **)v46);
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v38);
LABEL_32:
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)v39,
      v18,
      v19);
    if ( v42[0] )
      EventActivityIdControl(2u, &ActivityId);
    return 2147500037LL;
  }
  v47 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v47) = 0;
  *(_OWORD *)psz = 0;
  v50 = si128;
  LOWORD(psz[0]) = 0;
  v20 = 1;
  if ( a4 != -1 )
    v20 = 2;
  v21 = (*(__int64 (__fastcall **)(struct AppV::Client::ClientCatalog *, __int64, struct _GUID *, __int128 *))(*(_QWORD *)v41 + 64LL))(
          v41,
          v20,
          &v44,
          &v47);
  v22 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
  if ( v22 )
    v23 = v22 + 1;
  else
    v23 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
  AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v23);
  if ( (v21 & 0x8000000000LL) == 0 )
  {
    v24 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
    v25 = v24 ? v24 + 1 : "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
    AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v25);
    if ( (v21 & 0x2000000000LL) != 0
      || ((v26 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92)) == 0
        ? (v27 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp")
        : (v27 = v26 + 1),
          (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v27),
           (BYTE4(v21) & 0x1F) != 6)
       || ((v28 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92)) == 0
         ? (v29 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp")
         : (v29 = v28 + 1),
           AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v29),
           (_DWORD)v21 != 8)) )
    {
      *a6 = v21;
      v40 = -2147467259;
      std::wstring::~wstring((char **)psz);
      std::wstring::~wstring((char **)&v47);
      std::wstring::~wstring((char **)v46);
      AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v38);
      goto LABEL_32;
    }
  }
  v30 = (const OLECHAR *)psz;
  if ( v50.m128i_i64[1] > 7uLL )
    v30 = psz[0];
  v31 = SysAllocString(v30);
  *a5 = v31;
  if ( v31 )
  {
    *a6 = 0x8000000000LL;
    v40 = 0;
    std::wstring::~wstring((char **)psz);
    std::wstring::~wstring((char **)&v47);
    std::wstring::~wstring((char **)v46);
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v38);
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)v39,
      v36,
      v37);
    if ( v42[0] )
      EventActivityIdControl(2u, &ActivityId);
    return 0;
  }
  else
  {
    v32 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
    if ( v32 )
      v33 = v32 + 1;
    else
      v33 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
    *a6 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v33) << 52)
        | 0x115230000000ELL;
    v40 = -2147024882;
    std::wstring::~wstring((char **)psz);
    std::wstring::~wstring((char **)&v47);
    std::wstring::~wstring((char **)v46);
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v38);
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)v39,
      v34,
      v35);
    if ( v42[0] )
      EventActivityIdControl(2u, &ActivityId);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x140025be0  mov     [rsp-8+arg_0], rbx
0x140025be5  mov     [rsp-8+arg_18], rsi
0x140025bea  push    rbp
0x140025beb  push    rdi
0x140025bec  push    r12
0x140025bee  push    r14
0x140025bf0  push    r15
0x140025bf2  lea     rbp, [rsp-20h]
0x140025bf7  sub     rsp, 120h
0x140025bfe  mov     rax, cs:__security_cookie
0x140025c05  xor     rax, rsp
0x140025c08  mov     [rbp+40h+var_30], rax
0x140025c0c  movzx   r12d, r9w
0x140025c10  mov     rsi, r8
0x140025c13  mov     r14, rdx
0x140025c16  mov     r15, [rbp+40h+arg_20]
0x140025c1a  mov     rbx, [rbp+40h+arg_28]
0x140025c1e  lea     rcx, [rsp+140h+var_E8]
0x140025c23  call    ??0?$ScopedActivity@VUserModeActivityIdControl@ETW@AppV@@@ETW@AppV@@QEAA@XZ; AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(void)
0x140025c28  lea     rdx, aGetdynamicuser; "GetDynamicUserConfigurationPath"
0x140025c2f  lea     rcx, [rsp+140h+var_108]; this
0x140025c34  call    ??0SmartComMethodLogger@Service@Client@AppV@@QEAA@PEB_W@Z; AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(wchar_t const *)
0x140025c39  test    r14, r14
0x140025c3c  jz      loc_140025FF0
0x140025c42  test    rsi, rsi
0x140025c45  jz      loc_140025FF0
0x140025c4b  test    r15, r15
0x140025c4e  jz      loc_140025FF0
0x140025c54  test    rbx, rbx
0x140025c57  jz      loc_140025FF0
0x140025c5d  mov     qword ptr [r15], 0
0x140025c64  mov     [rsp+140h+var_110], 0
0x140025c69  mov     r8, rbx; unsigned __int64 *
0x140025c6c  xor     edx, edx; bool
0x140025c6e  lea     rcx, [rsp+140h+var_110]; this
0x140025c73  call    ?Initialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJ_NAEA_K@Z; AppV::Client::Service::AppVClientImpl::APICaller::Initialize(bool,unsigned __int64 &)
0x140025c78  mov     edi, eax
0x140025c7a  test    eax, eax
0x140025c7c  jns     short loc_140025CB5
0x140025c7e  mov     [rsp+140h+var_F8], eax
0x140025c82  lea     rcx, [rsp+140h+var_110]; this
0x140025c87  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140025c8c  nop
0x140025c8d  lea     rcx, [rsp+140h+var_108]; this
0x140025c92  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x140025c97  cmp     [rsp+140h+var_E8], 0
0x140025c9c  jz      short loc_140025CAE
0x140025c9e  lea     rdx, [rsp+140h+ActivityId]; ActivityId
0x140025ca3  mov     ecx, 2; ControlCode
0x140025ca8  call    cs:__imp_EventActivityIdControl
0x140025cae  mov     eax, edi
0x140025cb0  jmp     loc_14002601E
0x140025cb5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140025cbc  movdqu  xmmword ptr [rbp+40h+var_C0.Data1], xmm0
0x140025cc1  movdqu  xmmword ptr [rbp+40h+var_B0.Data1], xmm0
0x140025cc6  xorps   xmm0, xmm0
0x140025cc9  movups  [rbp+40h+var_A0], xmm0
0x140025ccd  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140025cd5  movdqa  [rbp+40h+var_90], xmm1
0x140025cda  xor     eax, eax
0x140025cdc  mov     word ptr [rbp+40h+var_A0], ax
0x140025ce0  lea     r9, [rbp+40h+var_B0]; struct _GUID *
0x140025ce4  lea     r8, [rbp+40h+var_C0]; struct _GUID *
0x140025ce8  mov     rdx, rsi; wchar_t *
0x140025ceb  mov     rcx, r14; wchar_t *
0x140025cee  call    ?GetPackageIDAndPackageVersionID@AppVClientImpl@Service@Client@AppV@@CA_KQEA_W0AEAU_GUID@@1@Z; AppV::Client::Service::AppVClientImpl::GetPackageIDAndPackageVersionID(wchar_t * const,wchar_t * const,_GUID &,_GUID &)
0x140025cf3  bt      rax, 27h ; '''
0x140025cf8  jb      short loc_140025D1F
0x140025cfa  mov     [rbx], rax
0x140025cfd  mov     [rsp+140h+var_F8], 80070057h
0x140025d05  lea     rcx, [rbp+40h+var_A0]
0x140025d09  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025d0e  nop
0x140025d0f  lea     rcx, [rsp+140h+var_110]; this
0x140025d14  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140025d19  nop
0x140025d1a  jmp     loc_140025FF8
0x140025d1f  mov     [rsp+140h+var_F0], 0
0x140025d28  lea     rcx, [rsp+140h+var_F0]; struct AppV::Client::ClientCatalog **
0x140025d2d  call    ?GetClientCatalog@AppVClientImpl@Service@Client@AppV@@CA_KAEAPEBVClientCatalog@34@@Z; AppV::Client::Service::AppVClientImpl::GetClientCatalog(AppV::Client::ClientCatalog const * &)
0x140025d32  bt      rax, 27h ; '''
0x140025d37  jb      short loc_140025D5E
0x140025d39  mov     [rbx], rax
0x140025d3c  mov     [rsp+140h+var_F8], 80004005h
0x140025d44  lea     rcx, [rbp+40h+var_A0]
0x140025d48  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025d4d  nop
0x140025d4e  lea     rcx, [rsp+140h+var_110]; this
0x140025d53  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140025d58  nop
0x140025d59  jmp     loc_140025EB4
0x140025d5e  xorps   xmm0, xmm0
0x140025d61  movups  [rbp+40h+var_80], xmm0
0x140025d65  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140025d6d  movdqa  [rbp+40h+var_70], xmm1
0x140025d72  xor     eax, eax
0x140025d74  mov     word ptr [rbp+40h+var_80], ax
0x140025d78  movups  xmmword ptr [rbp+40h+psz], xmm0
0x140025d7c  movdqa  [rbp+40h+var_50], xmm1
0x140025d81  mov     word ptr [rbp+40h+psz], ax
0x140025d85  or      eax, 0FFFFFFFFh
0x140025d88  mov     rcx, [rsp+140h+var_F0]
0x140025d8d  lea     r9, [rbp+40h+var_80]
0x140025d91  lea     r8, [rbp+40h+var_C0]
0x140025d95  cmp     ax, r12w
0x140025d99  mov     rax, [rcx]
0x140025d9c  mov     rax, [rax+40h]
0x140025da0  mov     edx, 1
0x140025da5  jz      short loc_140025DAC
0x140025da7  mov     edx, 2
0x140025dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025db1  mov     rdi, rax
0x140025db4  mov     r14d, 5Ch ; '\'
0x140025dba  mov     edx, r14d; Ch
0x140025dbd  lea     rsi, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140025dc4  mov     rcx, rsi; Str
0x140025dc7  call    cs:__imp_strrchr
0x140025dcd  test    rax, rax
0x140025dd0  jz      short loc_140025DD7
0x140025dd2  inc     rax
0x140025dd5  jmp     short loc_140025DDA
0x140025dd7  mov     rax, rsi
0x140025dda  mov     rdx, rax; char *
0x140025ddd  lea     r12, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; AppV::FileLookUp MeyersSingleton<AppV::FileLookUp>::instance_
0x140025de4  mov     rcx, r12; this
0x140025de7  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140025dec  bt      rdi, 27h ; '''
0x140025df1  jb      loc_140025EDF
0x140025df7  mov     edx, r14d; Ch
0x140025dfa  mov     rcx, rsi; Str
0x140025dfd  call    cs:__imp_strrchr
0x140025e03  test    rax, rax
0x140025e06  jz      short loc_140025E0D
0x140025e08  inc     rax
0x140025e0b  jmp     short loc_140025E10
0x140025e0d  mov     rax, rsi
0x140025e10  mov     rdx, rax; char *
0x140025e13  mov     rcx, r12; this
0x140025e16  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140025e1b  bt      rdi, 25h ; '%'
0x140025e20  jb      short loc_140025E82
0x140025e22  mov     edx, r14d; Ch
0x140025e25  mov     rcx, rsi; Str
0x140025e28  call    cs:__imp_strrchr
0x140025e2e  test    rax, rax
0x140025e31  jz      short loc_140025E38
0x140025e33  inc     rax
0x140025e36  jmp     short loc_140025E3B
0x140025e38  mov     rax, rsi
0x140025e3b  mov     rdx, rax; char *
0x140025e3e  mov     rcx, r12; this
0x140025e41  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140025e46  mov     rax, rdi
0x140025e49  shr     rax, 20h
0x140025e4d  and     al, 1Fh
0x140025e4f  cmp     al, 6
0x140025e51  jnz     short loc_140025E82
0x140025e53  mov     edx, r14d; Ch
0x140025e56  mov     rcx, rsi; Str
0x140025e59  call    cs:__imp_strrchr
0x140025e5f  test    rax, rax
0x140025e62  jz      short loc_140025E69
0x140025e64  inc     rax
0x140025e67  jmp     short loc_140025E6C
0x140025e69  mov     rax, rsi
0x140025e6c  mov     rdx, rax; char *
0x140025e6f  mov     rcx, r12; this
0x140025e72  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140025e77  shl     rax, 34h
0x140025e7b  or      eax, 8
0x140025e7e  cmp     edi, eax
0x140025e80  jz      short loc_140025EDF
0x140025e82  mov     [rbx], rdi
0x140025e85  mov     [rsp+140h+var_F8], 80004005h
0x140025e8d  lea     rcx, [rbp+40h+psz]
0x140025e91  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025e96  lea     rcx, [rbp+40h+var_80]
0x140025e9a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025e9f  lea     rcx, [rbp+40h+var_A0]
0x140025ea3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025ea8  nop
0x140025ea9  lea     rcx, [rsp+140h+var_110]; this
0x140025eae  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140025eb3  nop
0x140025eb4  lea     rcx, [rsp+140h+var_108]; this
0x140025eb9  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x140025ebe  cmp     [rsp+140h+var_E8], 0
0x140025ec3  jz      short loc_140025ED5
0x140025ec5  lea     rdx, [rsp+140h+ActivityId]; ActivityId
0x140025eca  mov     ecx, 2; ControlCode
0x140025ecf  call    cs:__imp_EventActivityIdControl
0x140025ed5  mov     eax, 80004005h
0x140025eda  jmp     loc_14002601E
0x140025edf  lea     rcx, [rbp+40h+psz]
0x140025ee3  cmp     qword ptr [rbp+40h+var_50+8], 7
0x140025ee8  cmova   rcx, [rbp+40h+psz]; psz
0x140025eed  call    cs:__imp_SysAllocString
0x140025ef3  mov     [r15], rax
0x140025ef6  test    rax, rax
0x140025ef9  jnz     loc_140025F8F
0x140025eff  mov     edx, r14d; Ch
0x140025f02  mov     rcx, rsi; Str
0x140025f05  call    cs:__imp_strrchr
0x140025f0b  test    rax, rax
0x140025f0e  jz      short loc_140025F15
0x140025f10  inc     rax
0x140025f13  jmp     short loc_140025F18
0x140025f15  mov     rax, rsi
0x140025f18  mov     rdx, rax; char *
0x140025f1b  mov     rcx, r12; this
0x140025f1e  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140025f23  shl     rax, 34h
0x140025f27  mov     rcx, 115230000000Eh
0x140025f31  or      rax, rcx
0x140025f34  mov     [rbx], rax
0x140025f37  mov     ebx, 8007000Eh
0x140025f3c  mov     [rsp+140h+var_F8], ebx
0x140025f40  lea     rcx, [rbp+40h+psz]
0x140025f44  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025f49  lea     rcx, [rbp+40h+var_80]
0x140025f4d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025f52  lea     rcx, [rbp+40h+var_A0]
0x140025f56  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025f5b  nop
0x140025f5c  lea     rcx, [rsp+140h+var_110]; this
0x140025f61  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140025f66  nop
0x140025f67  lea     rcx, [rsp+140h+var_108]; this
0x140025f6c  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x140025f71  cmp     [rsp+140h+var_E8], 0
0x140025f76  jz      short loc_140025F88
0x140025f78  lea     rdx, [rsp+140h+ActivityId]; ActivityId
0x140025f7d  mov     ecx, 2; ControlCode
0x140025f82  call    cs:__imp_EventActivityIdControl
0x140025f88  mov     eax, ebx
0x140025f8a  jmp     loc_14002601E
0x140025f8f  mov     rax, 8000000000h
0x140025f99  mov     [rbx], rax
0x140025f9c  mov     [rsp+140h+var_F8], 0
0x140025fa4  lea     rcx, [rbp+40h+psz]
0x140025fa8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025fad  lea     rcx, [rbp+40h+var_80]
0x140025fb1  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025fb6  lea     rcx, [rbp+40h+var_A0]
0x140025fba  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025fbf  nop
0x140025fc0  lea     rcx, [rsp+140h+var_110]; this
0x140025fc5  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140025fca  nop
0x140025fcb  lea     rcx, [rsp+140h+var_108]; this
0x140025fd0  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x140025fd5  cmp     [rsp+140h+var_E8], 0
0x140025fda  jz      short loc_140025FEC
0x140025fdc  lea     rdx, [rsp+140h+ActivityId]; ActivityId
0x140025fe1  mov     ecx, 2; ControlCode
0x140025fe6  call    cs:__imp_EventActivityIdControl
0x140025fec  xor     eax, eax
0x140025fee  jmp     short loc_14002601E
0x140025ff0  mov     [rsp+140h+var_F8], 80070057h
0x140025ff8  lea     rcx, [rsp+140h+var_108]; this
0x140025ffd  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x140026002  cmp     [rsp+140h+var_E8], 0
0x140026007  jz      short loc_140026019
0x140026009  lea     rdx, [rsp+140h+ActivityId]; ActivityId
0x14002600e  mov     ecx, 2; ControlCode
0x140026013  call    cs:__imp_EventActivityIdControl
0x140026019  mov     eax, 80070057h
0x14002601e  mov     rcx, [rbp+40h+var_30]
0x140026022  xor     rcx, rsp; StackCookie
0x140026025  call    __security_check_cookie
0x14002602a  lea     r11, [rsp+140h+var_20]
0x140026032  mov     rbx, [r11+30h]
0x140026036  mov     rsi, [r11+48h]
0x14002603a  mov     rsp, r11
0x14002603d  pop     r15
0x14002603f  pop     r14
0x140026041  pop     r12
0x140026043  pop     rdi
0x140026044  pop     rbp
0x140026045  retn
```
