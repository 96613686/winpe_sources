# AppV::Client::Service::AppVClientImpl::GetPackagePath(wchar_t *,wchar_t *,wchar_t * *,unsigned __int64 *)

- ea: `0x1400271d0`
- end: `0x1400274f4`
- name: `?GetPackagePath@AppVClientImpl@Service@Client@AppV@@UEAAJPEA_W0PEAPEA_WPEA_K@Z`
- size: `804`
- prototype: `int(AppV::Client::Service::AppVClientImpl *__hidden this, wchar_t *, wchar_t *, wchar_t **, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004280`
- `0x140006304`
- `0x140008224`
- `0x1400083b4`
- `0x1400090cc`
- `0x140018bec`
- `0x1400233dc`
- `0x140026dd0`
- `0x1400271d0`
- `0x140028e00`
- `0x14002a718`
- `0x1400360a0`
- `0x14003a494`
- `0x14003a6d8`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x140027288`
- `ADVAPI32!EventActivityIdControl` at `0x14002744f`
- `ADVAPI32!EventActivityIdControl` at `0x1400274a0`
- `ADVAPI32!EventActivityIdControl` at `0x1400274cb`
- `ADVAPI32!EventActivityIdControl` at `0x140027288`
- `ADVAPI32!EventActivityIdControl` at `0x14002744f`
- `ADVAPI32!EventActivityIdControl` at `0x1400274a0`
- `ADVAPI32!EventActivityIdControl` at `0x1400274cb`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400273ca`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400273ca`
- `OLEAUT32!__imp_SysAllocString` at `0x1400273ae`
- `OLEAUT32!__imp_SysAllocString` at `0x1400273ae`

## string_xrefs

- `0x1400273c3`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x1400273da`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x14002720e`: `GetPackagePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppV::Client::Service::AppVClientImpl::GetPackagePath(
        AppV::Client::Service::AppVClientImpl *this,
        wchar_t *a2,
        wchar_t *a3,
        wchar_t **a4,
        unsigned __int64 *a5)
{
  int v8; // eax
  unsigned int v9; // edi
  unsigned __int64 PackageIDAndPackageVersionID; // rax
  int v12; // eax
  int v13; // eax
  const OLECHAR *v14; // rcx
  wchar_t *v15; // rax
  char *v16; // rax
  const char *v17; // rax
  _BYTE v18[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h]
  _BYTE v21[16]; // [rsp+50h] [rbp-B0h] BYREF
  int v22; // [rsp+60h] [rbp-A0h]
  _BYTE v23[4]; // [rsp+90h] [rbp-70h] BYREF
  GUID ActivityId; // [rsp+94h] [rbp-6Ch] BYREF
  _QWORD v25[3]; // [rsp+C0h] [rbp-40h] BYREF
  struct _GUID v26; // [rsp+D8h] [rbp-28h] BYREF
  struct _GUID v27; // [rsp+E8h] [rbp-18h] BYREF
  char v28; // [rsp+F8h] [rbp-8h]
  OLECHAR *psz[2]; // [rsp+100h] [rbp+0h] BYREF
  __m128i si128; // [rsp+110h] [rbp+10h]
  __int64 v31; // [rsp+120h] [rbp+20h]
  __int64 v32; // [rsp+128h] [rbp+28h]
  __int16 v33; // [rsp+130h] [rbp+30h]

  AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>((__int64)v23);
  AppV::Client::Service::SmartTelemetryActivityLogger::SmartTelemetryActivityLogger(
    (AppV::Client::Service::SmartTelemetryActivityLogger *)v21,
    L"GetPackagePath");
  if ( !a2 || !a3 || !a5 || !a4 )
  {
    v22 = -2147024809;
    goto LABEL_27;
  }
  v18[0] = 0;
  v8 = AppV::Client::Service::AppVClientImpl::APICaller::Initialize(
         (AppV::Client::Service::AppVClientImpl::APICaller *)v18,
         0,
         a5);
  v9 = v8;
  if ( v8 < 0 )
  {
    v22 = v8;
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v18);
LABEL_7:
    AppV::Client::Service::SmartTelemetryActivityLogger::~SmartTelemetryActivityLogger((AppV::Client::Service::SmartTelemetryActivityLogger *)v21);
    if ( v23[0] )
      EventActivityIdControl(2u, &ActivityId);
    return v9;
  }
  AppV::Client::ActivityData::ActivityData((AppV::Client::ActivityData *)v25);
  v25[0] = &AppV::Client::GetPackageStreamingAttributesData::`vftable';
  v26 = GUID_NULL;
  v27 = GUID_NULL;
  v28 = 0;
  *(_OWORD *)psz = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(psz[0]) = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  PackageIDAndPackageVersionID = AppV::Client::Service::AppVClientImpl::GetPackageIDAndPackageVersionID(
                                   a2,
                                   a3,
                                   &v26,
                                   &v27);
  if ( (PackageIDAndPackageVersionID & 0x8000000000LL) == 0 )
  {
    *a5 = PackageIDAndPackageVersionID;
    v22 = -2147024809;
    std::wstring::~wstring((char **)psz);
    v25[0] = &AppV::Client::ActivityData::`vftable';
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v18);
LABEL_27:
    AppV::Client::Service::SmartTelemetryActivityLogger::~SmartTelemetryActivityLogger((AppV::Client::Service::SmartTelemetryActivityLogger *)v21);
    if ( v23[0] )
      EventActivityIdControl(2u, &ActivityId);
    return 2147942487LL;
  }
  v19 = 0;
  v20 = 0;
  v12 = AppV::Client::Service::AppVClientImpl::RequestActivity(0x2Cu, (__int64)v25, (__int64)&v19);
  v13 = AppV::Client::Service::AppVClientImpl::ProcessFailFastErrors(
          (unsigned int)v21,
          v12,
          (unsigned int)&v19,
          (_DWORD)a5,
          (__int64)v21);
  v9 = v13;
  if ( v13 < 0 )
  {
    v22 = v13;
    std::vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>((char **)&v19);
    std::wstring::~wstring((char **)psz);
    v25[0] = &AppV::Client::ActivityData::`vftable';
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v18);
    goto LABEL_7;
  }
  v14 = (const OLECHAR *)psz;
  if ( si128.m128i_i64[1] > 7uLL )
    v14 = psz[0];
  v15 = SysAllocString(v14);
  *a4 = v15;
  if ( v15 )
  {
    v22 = 0;
    std::vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>((char **)&v19);
    std::wstring::~wstring((char **)psz);
    v25[0] = &AppV::Client::ActivityData::`vftable';
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v18);
    AppV::Client::Service::SmartTelemetryActivityLogger::~SmartTelemetryActivityLogger((AppV::Client::Service::SmartTelemetryActivityLogger *)v21);
    if ( v23[0] )
      EventActivityIdControl(2u, &ActivityId);
    return 0;
  }
  else
  {
    v16 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
    if ( v16 )
      v17 = v16 + 1;
    else
      v17 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
    *a5 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v17) << 52)
        | 0x12C230000000ELL;
    v22 = -2147024882;
    std::vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>((char **)&v19);
    std::wstring::~wstring((char **)psz);
    v25[0] = &AppV::Client::ActivityData::`vftable';
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v18);
    AppV::Client::Service::SmartTelemetryActivityLogger::~SmartTelemetryActivityLogger((AppV::Client::Service::SmartTelemetryActivityLogger *)v21);
    if ( v23[0] )
      EventActivityIdControl(2u, &ActivityId);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1400271d0  push    rbp
0x1400271d2  push    rbx
0x1400271d3  push    rsi
0x1400271d4  push    rdi
0x1400271d5  push    r12
0x1400271d7  push    r14
0x1400271d9  push    r15
0x1400271db  lea     rbp, [rsp-50h]
0x1400271e0  sub     rsp, 150h
0x1400271e7  mov     rax, cs:__security_cookie
0x1400271ee  xor     rax, rsp
0x1400271f1  mov     [rbp+80h+var_40], rax
0x1400271f5  mov     rsi, r9
0x1400271f8  mov     r14, r8
0x1400271fb  mov     r15, rdx
0x1400271fe  mov     rbx, [rbp+80h+arg_20]
0x140027205  lea     rcx, [rbp+80h+var_F0]
0x140027209  call    ??0?$ScopedActivity@VUserModeActivityIdControl@ETW@AppV@@@ETW@AppV@@QEAA@XZ; AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(void)
0x14002720e  lea     rdx, aGetpackagepath; "GetPackagePath"
0x140027215  lea     rcx, [rsp+180h+var_130]; this
0x14002721a  call    ??0SmartTelemetryActivityLogger@Service@Client@AppV@@QEAA@PEB_W@Z; AppV::Client::Service::SmartTelemetryActivityLogger::SmartTelemetryActivityLogger(wchar_t const *)
0x14002721f  xor     r12d, r12d
0x140027222  test    r15, r15
0x140027225  jz      loc_1400274AA
0x14002722b  test    r14, r14
0x14002722e  jz      loc_1400274AA
0x140027234  test    rbx, rbx
0x140027237  jz      loc_1400274AA
0x14002723d  test    rsi, rsi
0x140027240  jz      loc_1400274AA
0x140027246  mov     [rsp+180h+var_150], r12b
0x14002724b  mov     r8, rbx; unsigned __int64 *
0x14002724e  xor     edx, edx; bool
0x140027250  lea     rcx, [rsp+180h+var_150]; this
0x140027255  call    ?Initialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJ_NAEA_K@Z; AppV::Client::Service::AppVClientImpl::APICaller::Initialize(bool,unsigned __int64 &)
0x14002725a  mov     edi, eax
0x14002725c  test    eax, eax
0x14002725e  jns     short loc_140027295
0x140027260  mov     [rsp+180h+var_120], eax
0x140027264  lea     rcx, [rsp+180h+var_150]; this
0x140027269  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x14002726e  nop
0x14002726f  lea     rcx, [rsp+180h+var_130]; this
0x140027274  call    ??1SmartTelemetryActivityLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartTelemetryActivityLogger::~SmartTelemetryActivityLogger(void)
0x140027279  cmp     [rbp+80h+var_F0], r12b
0x14002727d  jz      short loc_14002728E
0x14002727f  lea     rdx, [rbp+80h+ActivityId]; ActivityId
0x140027283  mov     ecx, 2; ControlCode
0x140027288  call    cs:__imp_EventActivityIdControl
0x14002728e  mov     eax, edi
0x140027290  jmp     loc_1400274D6
0x140027295  lea     rcx, [rbp+80h+var_C0]; this
0x140027299  call    ??0ActivityData@Client@AppV@@QEAA@XZ; AppV::Client::ActivityData::ActivityData(void)
0x14002729e  lea     rax, ??_7GetPackageStreamingAttributesData@Client@AppV@@6B@; const AppV::Client::GetPackageStreamingAttributesData::`vftable'
0x1400272a5  mov     [rbp+80h+var_C0], rax
0x1400272a9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400272b0  movdqu  xmmword ptr [rbp+80h+var_A8.Data1], xmm0
0x1400272b5  movdqu  xmmword ptr [rbp+80h+var_98.Data1], xmm0
0x1400272ba  mov     [rbp+80h+var_88], r12b
0x1400272be  xorps   xmm0, xmm0
0x1400272c1  movups  xmmword ptr [rbp+80h+psz], xmm0
0x1400272c5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1400272cd  movdqa  [rbp+80h+var_70], xmm1
0x1400272d2  mov     word ptr [rbp+80h+psz], r12w
0x1400272d7  mov     [rbp+80h+var_60], r12
0x1400272db  mov     [rbp+80h+var_58], r12
0x1400272df  mov     [rbp+80h+var_50], r12w
0x1400272e4  lea     r9, [rbp+80h+var_98]; struct _GUID *
0x1400272e8  lea     r8, [rbp+80h+var_A8]; struct _GUID *
0x1400272ec  mov     rdx, r14; wchar_t *
0x1400272ef  mov     rcx, r15; wchar_t *
0x1400272f2  call    ?GetPackageIDAndPackageVersionID@AppVClientImpl@Service@Client@AppV@@CA_KQEA_W0AEAU_GUID@@1@Z; AppV::Client::Service::AppVClientImpl::GetPackageIDAndPackageVersionID(wchar_t * const,wchar_t * const,_GUID &,_GUID &)
0x1400272f7  bt      rax, 27h ; '''
0x1400272fc  jb      short loc_14002732D
0x1400272fe  mov     [rbx], rax
0x140027301  mov     [rsp+180h+var_120], 80070057h
0x140027309  lea     rcx, [rbp+80h+psz]
0x14002730d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140027312  lea     rax, ??_7ActivityData@Client@AppV@@6B@; const AppV::Client::ActivityData::`vftable'
0x140027319  mov     [rbp+80h+var_C0], rax
0x14002731d  lea     rcx, [rsp+180h+var_150]; this
0x140027322  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140027327  nop
0x140027328  jmp     loc_1400274B2
0x14002732d  xorps   xmm0, xmm0
0x140027330  movdqu  [rsp+180h+var_148], xmm0
0x140027336  mov     [rsp+180h+var_138], r12
0x14002733b  lea     r8, [rsp+180h+var_148]
0x140027340  lea     rdx, [rbp+80h+var_C0]
0x140027344  mov     ecx, 2Ch ; ','
0x140027349  call    ?RequestActivity@AppVClientImpl@Service@Client@AppV@@CA_KW4ActivityType@34@AEAVActivityData@34@AEAV?$vector@U?$pair@W4ComponentType@Client@AppV@@_K@std@@V?$allocator@U?$pair@W4ComponentType@Client@AppV@@_K@std@@@2@@std@@@Z; AppV::Client::Service::AppVClientImpl::RequestActivity(AppV::Client::ActivityType,AppV::Client::ActivityData &,std::vector<std::pair<AppV::Client::ComponentType,unsigned __int64>> &)
0x14002734e  lea     rcx, [rsp+180h+var_130]
0x140027353  mov     [rsp+180h+var_160], rcx
0x140027358  mov     r9, rbx
0x14002735b  lea     r8, [rsp+180h+var_148]
0x140027360  mov     rdx, rax
0x140027363  call    ?ProcessFailFastErrors@AppVClientImpl@Service@Client@AppV@@AEAAJ_KAEBV?$vector@U?$pair@W4ComponentType@Client@AppV@@_K@std@@V?$allocator@U?$pair@W4ComponentType@Client@AppV@@_K@std@@@2@@std@@AEA_KPEAVSmartTelemetryActivityLogger@234@@Z; AppV::Client::Service::AppVClientImpl::ProcessFailFastErrors(unsigned __int64,std::vector<std::pair<AppV::Client::ComponentType,unsigned __int64>> const &,unsigned __int64 &,AppV::Client::Service::SmartTelemetryActivityLogger *)
0x140027368  mov     edi, eax
0x14002736a  test    eax, eax
0x14002736c  jns     short loc_1400273A0
0x14002736e  mov     [rsp+180h+var_120], eax
0x140027372  lea     rcx, [rsp+180h+var_148]
0x140027377  call    ??1?$vector@U?$pair@W4ComponentType@Client@AppV@@_K@std@@V?$allocator@U?$pair@W4ComponentType@Client@AppV@@_K@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<AppV::Client::ComponentType,unsigned __int64>>(void)
0x14002737c  lea     rcx, [rbp+80h+psz]
0x140027380  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140027385  lea     rax, ??_7ActivityData@Client@AppV@@6B@; const AppV::Client::ActivityData::`vftable'
0x14002738c  mov     [rbp+80h+var_C0], rax
0x140027390  lea     rcx, [rsp+180h+var_150]; this
0x140027395  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x14002739a  nop
0x14002739b  jmp     loc_14002726F
0x1400273a0  lea     rcx, [rbp+80h+psz]
0x1400273a4  cmp     qword ptr [rbp+80h+var_70+8], 7
0x1400273a9  cmova   rcx, [rbp+80h+psz]; psz
0x1400273ae  call    cs:__imp_SysAllocString
0x1400273b4  mov     [rsi], rax
0x1400273b7  test    rax, rax
0x1400273ba  jnz     loc_140027459
0x1400273c0  lea     edx, [rax+5Ch]; Ch
0x1400273c3  lea     rcx, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x1400273ca  call    cs:__imp_strrchr
0x1400273d0  test    rax, rax
0x1400273d3  jz      short loc_1400273DA
0x1400273d5  inc     rax
0x1400273d8  jmp     short loc_1400273E1
0x1400273da  lea     rax, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x1400273e1  mov     rdx, rax; char *
0x1400273e4  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400273eb  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400273f0  shl     rax, 34h
0x1400273f4  mov     rcx, 12C230000000Eh
0x1400273fe  or      rax, rcx
0x140027401  mov     [rbx], rax
0x140027404  mov     ebx, 8007000Eh
0x140027409  mov     [rsp+180h+var_120], ebx
0x14002740d  lea     rcx, [rsp+180h+var_148]
0x140027412  call    ??1?$vector@U?$pair@W4ComponentType@Client@AppV@@_K@std@@V?$allocator@U?$pair@W4ComponentType@Client@AppV@@_K@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<AppV::Client::ComponentType,unsigned __int64>>(void)
0x140027417  lea     rcx, [rbp+80h+psz]
0x14002741b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140027420  lea     rax, ??_7ActivityData@Client@AppV@@6B@; const AppV::Client::ActivityData::`vftable'
0x140027427  mov     [rbp+80h+var_C0], rax
0x14002742b  lea     rcx, [rsp+180h+var_150]; this
0x140027430  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140027435  nop
0x140027436  lea     rcx, [rsp+180h+var_130]; this
0x14002743b  call    ??1SmartTelemetryActivityLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartTelemetryActivityLogger::~SmartTelemetryActivityLogger(void)
0x140027440  cmp     [rbp+80h+var_F0], r12b
0x140027444  jz      short loc_140027455
0x140027446  lea     rdx, [rbp+80h+ActivityId]; ActivityId
0x14002744a  mov     ecx, 2; ControlCode
0x14002744f  call    cs:__imp_EventActivityIdControl
0x140027455  mov     eax, ebx
0x140027457  jmp     short loc_1400274D6
0x140027459  mov     [rsp+180h+var_120], r12d
0x14002745e  lea     rcx, [rsp+180h+var_148]
0x140027463  call    ??1?$vector@U?$pair@W4ComponentType@Client@AppV@@_K@std@@V?$allocator@U?$pair@W4ComponentType@Client@AppV@@_K@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<AppV::Client::ComponentType,unsigned __int64>>(void)
0x140027468  lea     rcx, [rbp+80h+psz]
0x14002746c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140027471  lea     rax, ??_7ActivityData@Client@AppV@@6B@; const AppV::Client::ActivityData::`vftable'
0x140027478  mov     [rbp+80h+var_C0], rax
0x14002747c  lea     rcx, [rsp+180h+var_150]; this
0x140027481  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140027486  nop
0x140027487  lea     rcx, [rsp+180h+var_130]; this
0x14002748c  call    ??1SmartTelemetryActivityLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartTelemetryActivityLogger::~SmartTelemetryActivityLogger(void)
0x140027491  cmp     [rbp+80h+var_F0], r12b
0x140027495  jz      short loc_1400274A6
0x140027497  lea     rdx, [rbp+80h+ActivityId]; ActivityId
0x14002749b  mov     ecx, 2; ControlCode
0x1400274a0  call    cs:__imp_EventActivityIdControl
0x1400274a6  xor     eax, eax
0x1400274a8  jmp     short loc_1400274D6
0x1400274aa  mov     [rsp+180h+var_120], 80070057h
0x1400274b2  lea     rcx, [rsp+180h+var_130]; this
0x1400274b7  call    ??1SmartTelemetryActivityLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartTelemetryActivityLogger::~SmartTelemetryActivityLogger(void)
0x1400274bc  cmp     [rbp+80h+var_F0], r12b
0x1400274c0  jz      short loc_1400274D1
0x1400274c2  lea     rdx, [rbp+80h+ActivityId]; ActivityId
0x1400274c6  mov     ecx, 2; ControlCode
0x1400274cb  call    cs:__imp_EventActivityIdControl
0x1400274d1  mov     eax, 80070057h
0x1400274d6  mov     rcx, [rbp+80h+var_40]
0x1400274da  xor     rcx, rsp; StackCookie
0x1400274dd  call    __security_check_cookie
0x1400274e2  add     rsp, 150h
0x1400274e9  pop     r15
0x1400274eb  pop     r14
0x1400274ed  pop     r12
0x1400274ef  pop     rdi
0x1400274f0  pop     rsi
0x1400274f1  pop     rbx
0x1400274f2  pop     rbp
0x1400274f3  retn
```
