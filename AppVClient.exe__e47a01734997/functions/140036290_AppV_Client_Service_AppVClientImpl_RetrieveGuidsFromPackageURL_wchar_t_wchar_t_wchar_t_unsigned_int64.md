# AppV::Client::Service::AppVClientImpl::RetrieveGuidsFromPackageURL(wchar_t *,wchar_t * *,wchar_t * *,unsigned __int64 *)

- ea: `0x140036290`
- end: `0x140036678`
- name: `?RetrieveGuidsFromPackageURL@AppVClientImpl@Service@Client@AppV@@UEAAJPEA_WPEAPEA_W1PEA_K@Z`
- size: `1000`
- prototype: `int(AppV::Client::Service::AppVClientImpl *__hidden this, wchar_t *, wchar_t **, wchar_t **, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004280`
- `0x140006061`
- `0x140006304`
- `0x140007404`
- `0x140008224`
- `0x1400083b4`
- `0x1400090cc`
- `0x140018bec`
- `0x14001a100`
- `0x14001dbe8`
- `0x1400233dc`
- `0x140028e00`
- `0x14002a718`
- `0x1400360a0`
- `0x140036290`
- `0x14003a494`
- `0x14003a6d8`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x1400365b9`
- `ADVAPI32!EventActivityIdControl` at `0x140036626`
- `ADVAPI32!EventActivityIdControl` at `0x140036652`
- `ADVAPI32!EventActivityIdControl` at `0x1400365b9`
- `ADVAPI32!EventActivityIdControl` at `0x140036626`
- `ADVAPI32!EventActivityIdControl` at `0x140036652`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140036467`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003652c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140036467`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14003652c`
- `OLEAUT32!__imp_SysAllocString` at `0x14003644b`
- `OLEAUT32!__imp_SysAllocString` at `0x140036510`
- `OLEAUT32!__imp_SysAllocString` at `0x14003644b`
- `OLEAUT32!__imp_SysAllocString` at `0x140036510`
- `OLEAUT32!__imp_SysStringLen` at `0x140036309`
- `OLEAUT32!__imp_SysStringLen` at `0x140036309`

## string_xrefs

- `0x140036460`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x140036477`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x140036525`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x14003653c`: `admin\appman\appv\client\host\service\publicapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppV::Client::Service::AppVClientImpl::RetrieveGuidsFromPackageURL(
        AppV::Client::Service::AppVClientImpl *this,
        wchar_t *a2,
        wchar_t **a3,
        wchar_t **a4,
        unsigned __int64 *a5)
{
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r8
  unsigned __int64 v11; // rdx
  __int64 v12; // rbx
  int v13; // eax
  int v14; // eax
  const OLECHAR *v15; // rcx
  wchar_t *v16; // rax
  char *v17; // rax
  const char *v18; // rax
  __int64 v19; // rax
  const OLECHAR *v20; // rcx
  wchar_t *v21; // rax
  char *v22; // rax
  const char *v23; // rax
  _BYTE v25[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v26; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h]
  _BYTE v28[16]; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+60h] [rbp-A0h]
  _BYTE v30[4]; // [rsp+90h] [rbp-70h] BYREF
  GUID ActivityId; // [rsp+94h] [rbp-6Ch] BYREF
  OLECHAR *psz[3]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v33; // [rsp+D0h] [rbp-30h]
  _QWORD v34[3]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v35; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 v36; // [rsp+108h] [rbp+8h]
  __int64 v37; // [rsp+110h] [rbp+10h]
  GUID v38; // [rsp+118h] [rbp+18h] BYREF
  GUID v39; // [rsp+128h] [rbp+28h] BYREF
  char *v40[4]; // [rsp+140h] [rbp+40h] BYREF

  AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>((__int64)v30);
  AppV::Client::Service::SmartTelemetryActivityLogger::SmartTelemetryActivityLogger(
    (AppV::Client::Service::SmartTelemetryActivityLogger *)v28,
    L"RetrieveGuidsFromPackageURL");
  if ( !a2 || !a3 || !a4 || !a5 || !SysStringLen(a2) )
  {
    v9 = -2147024809;
    v29 = -2147024809;
    goto LABEL_36;
  }
  v25[0] = 0;
  v8 = AppV::Client::Service::AppVClientImpl::APICaller::Initialize(
         (AppV::Client::Service::AppVClientImpl::APICaller *)v25,
         1,
         a5);
  v9 = v8;
  if ( v8 < 0 )
  {
    v29 = v8;
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v25);
LABEL_36:
    AppV::Client::Service::SmartTelemetryActivityLogger::~SmartTelemetryActivityLogger((AppV::Client::Service::SmartTelemetryActivityLogger *)v28);
    if ( v30[0] )
      EventActivityIdControl(2u, &ActivityId);
    return v9;
  }
  AppV::Client::ActivityData::ActivityData((AppV::Client::ActivityData *)v34);
  v34[0] = &AppV::Client::GetPackageGUIDsFromURLData::`vftable';
  v35 = 0;
  v36 = 0;
  v37 = 7;
  LOWORD(v35) = 0;
  v38 = GUID_NULL;
  v39 = GUID_NULL;
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  if ( v11 > 7 )
  {
    std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(
      (char **)&v35,
      v11,
      v10,
      a2);
  }
  else
  {
    v36 = v11;
    v12 = 2 * v11;
    memmove_0(&v35, a2, 2 * v11);
    *(_WORD *)((char *)&v35 + v12) = 0;
  }
  v26 = 0;
  v27 = 0;
  v13 = AppV::Client::Service::AppVClientImpl::RequestActivity(0x2Du, (__int64)v34, (__int64)&v26);
  v14 = AppV::Client::Service::AppVClientImpl::ProcessFailFastErrors(
          (unsigned int)v28,
          v13,
          (unsigned int)&v26,
          (_DWORD)a5,
          (__int64)v28);
  v9 = v14;
  if ( v14 < 0 )
  {
    v29 = v14;
    std::vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>((char **)&v26);
    std::wstring::~wstring((char **)&v35);
    v34[0] = &AppV::Client::ActivityData::`vftable';
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v25);
    goto LABEL_36;
  }
  softricity::shared::tostring(psz, &v38);
  v15 = (const OLECHAR *)psz;
  if ( v33 > 7 )
    v15 = psz[0];
  v16 = SysAllocString(v15);
  *a3 = v16;
  if ( !v16 )
  {
    v17 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
    if ( v17 )
      v18 = v17 + 1;
    else
      v18 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
    *a5 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v18) << 52)
        | 0x11A230000000ELL;
    v29 = -2147024882;
    std::wstring::~wstring((char **)psz);
    std::vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>((char **)&v26);
    std::wstring::~wstring((char **)&v35);
    v34[0] = &AppV::Client::ActivityData::`vftable';
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v25);
LABEL_29:
    AppV::Client::Service::SmartTelemetryActivityLogger::~SmartTelemetryActivityLogger((AppV::Client::Service::SmartTelemetryActivityLogger *)v28);
    if ( v30[0] )
      EventActivityIdControl(2u, &ActivityId);
    return 2147942414LL;
  }
  v19 = softricity::shared::tostring(v40, &v39);
  std::wstring::operator=((char **)psz, v19);
  std::wstring::~wstring(v40);
  v20 = (const OLECHAR *)psz;
  if ( v33 > 7 )
    v20 = psz[0];
  v21 = SysAllocString(v20);
  *a4 = v21;
  if ( !v21 )
  {
    v22 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
    if ( v22 )
      v23 = v22 + 1;
    else
      v23 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
    *a5 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v23) << 52)
        | 0x11B230000000ELL;
    v29 = -2147024882;
    std::wstring::~wstring((char **)psz);
    std::vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>((char **)&v26);
    std::wstring::~wstring((char **)&v35);
    v34[0] = &AppV::Client::ActivityData::`vftable';
    AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v25);
    goto LABEL_29;
  }
  *a5 = 0x8000000000LL;
  v29 = 0;
  std::wstring::~wstring((char **)psz);
  std::vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<enum AppV::Client::ComponentType,unsigned __int64>>((char **)&v26);
  std::wstring::~wstring((char **)&v35);
  v34[0] = &AppV::Client::ActivityData::`vftable';
  AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v25);
  AppV::Client::Service::SmartTelemetryActivityLogger::~SmartTelemetryActivityLogger((AppV::Client::Service::SmartTelemetryActivityLogger *)v28);
  if ( v30[0] )
    EventActivityIdControl(2u, &ActivityId);
  return 0;
}

```

## disassembly

```asm
0x140036290  push    rbp
0x140036292  push    rbx
0x140036293  push    rsi
0x140036294  push    rdi
0x140036295  push    r12
0x140036297  push    r14
0x140036299  push    r15
0x14003629b  lea     rbp, [rsp-70h]
0x1400362a0  sub     rsp, 170h
0x1400362a7  mov     rax, cs:__security_cookie
0x1400362ae  xor     rax, rsp
0x1400362b1  mov     [rbp+0A0h+var_40], rax
0x1400362b5  mov     r15, r9
0x1400362b8  mov     r14, r8
0x1400362bb  mov     rdi, rdx
0x1400362be  mov     rsi, [rbp+0A0h+arg_20]
0x1400362c5  lea     rcx, [rbp+0A0h+var_110]
0x1400362c9  call    ??0?$ScopedActivity@VUserModeActivityIdControl@ETW@AppV@@@ETW@AppV@@QEAA@XZ; AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(void)
0x1400362ce  lea     rdx, aRetrieveguidsf; "RetrieveGuidsFromPackageURL"
0x1400362d5  lea     rcx, [rsp+1A0h+var_150]; this
0x1400362da  call    ??0SmartTelemetryActivityLogger@Service@Client@AppV@@QEAA@PEB_W@Z; AppV::Client::Service::SmartTelemetryActivityLogger::SmartTelemetryActivityLogger(wchar_t const *)
0x1400362df  xor     r12d, r12d
0x1400362e2  test    rdi, rdi
0x1400362e5  jz      loc_140036630
0x1400362eb  test    r14, r14
0x1400362ee  jz      loc_140036630
0x1400362f4  test    r15, r15
0x1400362f7  jz      loc_140036630
0x1400362fd  test    rsi, rsi
0x140036300  jz      loc_140036630
0x140036306  mov     rcx, rdi; pbstr
0x140036309  call    cs:__imp_SysStringLen
0x14003630f  test    eax, eax
0x140036311  jz      loc_140036630
0x140036317  mov     [rsp+1A0h+var_170], r12b
0x14003631c  mov     r8, rsi; unsigned __int64 *
0x14003631f  mov     dl, 1; bool
0x140036321  lea     rcx, [rsp+1A0h+var_170]; this
0x140036326  call    ?Initialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJ_NAEA_K@Z; AppV::Client::Service::AppVClientImpl::APICaller::Initialize(bool,unsigned __int64 &)
0x14003632b  mov     ebx, eax
0x14003632d  test    eax, eax
0x14003632f  jns     short loc_140036345
0x140036331  mov     [rsp+1A0h+var_140], eax
0x140036335  lea     rcx, [rsp+1A0h+var_170]; this
0x14003633a  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x14003633f  nop
0x140036340  jmp     loc_140036639
0x140036345  lea     rcx, [rbp+0A0h+var_C0]; this
0x140036349  call    ??0ActivityData@Client@AppV@@QEAA@XZ; AppV::Client::ActivityData::ActivityData(void)
0x14003634e  lea     rax, ??_7GetPackageGUIDsFromURLData@Client@AppV@@6B@; const AppV::Client::GetPackageGUIDsFromURLData::`vftable'
0x140036355  mov     [rbp+0A0h+var_C0], rax
0x140036359  xorps   xmm0, xmm0
0x14003635c  movups  [rbp+0A0h+var_A8], xmm0
0x140036360  mov     [rbp+0A0h+var_98], r12
0x140036364  mov     [rbp+0A0h+var_90], 7
0x14003636c  mov     word ptr [rbp+0A0h+var_A8], r12w
0x140036371  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140036378  movdqu  [rbp+0A0h+var_88], xmm0
0x14003637d  movdqu  xmmword ptr [rbp+0A0h+var_78.Data1], xmm0
0x140036382  or      rdx, 0FFFFFFFFFFFFFFFFh
0x140036386  inc     rdx
0x140036389  cmp     [rdi+rdx*2], r12w
0x14003638e  jnz     short loc_140036386
0x140036390  lea     rcx, [rbp+0A0h+var_A8]; void *
0x140036394  cmp     rdx, 7
0x140036398  ja      short loc_1400363B5
0x14003639a  mov     [rbp+0A0h+var_98], rdx
0x14003639e  lea     rbx, [rdx+rdx]
0x1400363a2  mov     r8, rbx; Size
0x1400363a5  mov     rdx, rdi; Src
0x1400363a8  call    memmove_0
0x1400363ad  mov     word ptr [rbp+rbx+0A0h+var_A8], r12w
0x1400363b3  jmp     short loc_1400363BD
0x1400363b5  mov     r9, rdi
0x1400363b8  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x1400363bd  xorps   xmm0, xmm0
0x1400363c0  movdqu  [rsp+1A0h+var_168], xmm0
0x1400363c6  mov     [rsp+1A0h+var_158], r12
0x1400363cb  lea     r8, [rsp+1A0h+var_168]
0x1400363d0  lea     rdx, [rbp+0A0h+var_C0]
0x1400363d4  mov     ecx, 2Dh ; '-'
0x1400363d9  call    ?RequestActivity@AppVClientImpl@Service@Client@AppV@@CA_KW4ActivityType@34@AEAVActivityData@34@AEAV?$vector@U?$pair@W4ComponentType@Client@AppV@@_K@std@@V?$allocator@U?$pair@W4ComponentType@Client@AppV@@_K@std@@@2@@std@@@Z; AppV::Client::Service::AppVClientImpl::RequestActivity(AppV::Client::ActivityType,AppV::Client::ActivityData &,std::vector<std::pair<AppV::Client::ComponentType,unsigned __int64>> &)
0x1400363de  lea     rcx, [rsp+1A0h+var_150]
0x1400363e3  mov     [rsp+1A0h+var_180], rcx
0x1400363e8  mov     r9, rsi
0x1400363eb  lea     r8, [rsp+1A0h+var_168]
0x1400363f0  mov     rdx, rax
0x1400363f3  call    ?ProcessFailFastErrors@AppVClientImpl@Service@Client@AppV@@AEAAJ_KAEBV?$vector@U?$pair@W4ComponentType@Client@AppV@@_K@std@@V?$allocator@U?$pair@W4ComponentType@Client@AppV@@_K@std@@@2@@std@@AEA_KPEAVSmartTelemetryActivityLogger@234@@Z; AppV::Client::Service::AppVClientImpl::ProcessFailFastErrors(unsigned __int64,std::vector<std::pair<AppV::Client::ComponentType,unsigned __int64>> const &,unsigned __int64 &,AppV::Client::Service::SmartTelemetryActivityLogger *)
0x1400363f8  mov     ebx, eax
0x1400363fa  test    eax, eax
0x1400363fc  jns     short loc_140036430
0x1400363fe  mov     [rsp+1A0h+var_140], eax
0x140036402  lea     rcx, [rsp+1A0h+var_168]
0x140036407  call    ??1?$vector@U?$pair@W4ComponentType@Client@AppV@@_K@std@@V?$allocator@U?$pair@W4ComponentType@Client@AppV@@_K@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<AppV::Client::ComponentType,unsigned __int64>>(void)
0x14003640c  lea     rcx, [rbp+0A0h+var_A8]
0x140036410  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140036415  lea     rcx, ??_7ActivityData@Client@AppV@@6B@; const AppV::Client::ActivityData::`vftable'
0x14003641c  mov     [rbp+0A0h+var_C0], rcx
0x140036420  lea     rcx, [rsp+1A0h+var_170]; this
0x140036425  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x14003642a  nop
0x14003642b  jmp     loc_140036639
0x140036430  lea     rdx, [rbp+0A0h+var_88]
0x140036434  lea     rcx, [rbp+0A0h+psz]
0x140036438  call    ?tostring@shared@softricity@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; softricity::shared::tostring(_GUID const &,bool)
0x14003643d  lea     rcx, [rbp+0A0h+psz]
0x140036441  cmp     [rbp+0A0h+var_D0], 7
0x140036446  cmova   rcx, [rbp+0A0h+psz]; psz
0x14003644b  call    cs:__imp_SysAllocString
0x140036451  mov     [r14], rax
0x140036454  test    rax, rax
0x140036457  jnz     loc_1400364E0
0x14003645d  lea     edx, [rax+5Ch]; Ch
0x140036460  lea     rcx, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140036467  call    cs:__imp_strrchr
0x14003646d  test    rax, rax
0x140036470  jz      short loc_140036477
0x140036472  inc     rax
0x140036475  jmp     short loc_14003647E
0x140036477  lea     rax, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x14003647e  mov     rdx, rax; char *
0x140036481  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140036488  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14003648d  shl     rax, 34h
0x140036491  mov     rcx, 11A230000000Eh
0x14003649b  or      rax, rcx
0x14003649e  mov     [rsi], rax
0x1400364a1  mov     [rsp+1A0h+var_140], 8007000Eh
0x1400364a9  lea     rcx, [rbp+0A0h+psz]
0x1400364ad  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400364b2  lea     rcx, [rsp+1A0h+var_168]
0x1400364b7  call    ??1?$vector@U?$pair@W4ComponentType@Client@AppV@@_K@std@@V?$allocator@U?$pair@W4ComponentType@Client@AppV@@_K@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<AppV::Client::ComponentType,unsigned __int64>>(void)
0x1400364bc  lea     rcx, [rbp+0A0h+var_A8]
0x1400364c0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400364c5  lea     rcx, ??_7ActivityData@Client@AppV@@6B@; const AppV::Client::ActivityData::`vftable'
0x1400364cc  mov     [rbp+0A0h+var_C0], rcx
0x1400364d0  lea     rcx, [rsp+1A0h+var_170]; this
0x1400364d5  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x1400364da  nop
0x1400364db  jmp     loc_1400365A0
0x1400364e0  lea     rdx, [rbp+0A0h+var_78]
0x1400364e4  lea     rcx, [rbp+0A0h+var_60]
0x1400364e8  call    ?tostring@shared@softricity@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; softricity::shared::tostring(_GUID const &,bool)
0x1400364ed  mov     rdx, rax
0x1400364f0  lea     rcx, [rbp+0A0h+psz]
0x1400364f4  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400364f9  lea     rcx, [rbp+0A0h+var_60]
0x1400364fd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140036502  lea     rcx, [rbp+0A0h+psz]
0x140036506  cmp     [rbp+0A0h+var_D0], 7
0x14003650b  cmova   rcx, [rbp+0A0h+psz]; psz
0x140036510  call    cs:__imp_SysAllocString
0x140036516  mov     [r15], rax
0x140036519  test    rax, rax
0x14003651c  jnz     loc_1400365C9
0x140036522  lea     edx, [rax+5Ch]; Ch
0x140036525  lea     rcx, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x14003652c  call    cs:__imp_strrchr
0x140036532  test    rax, rax
0x140036535  jz      short loc_14003653C
0x140036537  inc     rax
0x14003653a  jmp     short loc_140036543
0x14003653c  lea     rax, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140036543  mov     rdx, rax; char *
0x140036546  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14003654d  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140036552  shl     rax, 34h
0x140036556  mov     rcx, 11B230000000Eh
0x140036560  or      rax, rcx
0x140036563  mov     [rsi], rax
0x140036566  mov     [rsp+1A0h+var_140], 8007000Eh
0x14003656e  lea     rcx, [rbp+0A0h+psz]
0x140036572  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140036577  lea     rcx, [rsp+1A0h+var_168]
0x14003657c  call    ??1?$vector@U?$pair@W4ComponentType@Client@AppV@@_K@std@@V?$allocator@U?$pair@W4ComponentType@Client@AppV@@_K@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<AppV::Client::ComponentType,unsigned __int64>>(void)
0x140036581  lea     rcx, [rbp+0A0h+var_A8]
0x140036585  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003658a  lea     rcx, ??_7ActivityData@Client@AppV@@6B@; const AppV::Client::ActivityData::`vftable'
0x140036591  mov     [rbp+0A0h+var_C0], rcx
0x140036595  lea     rcx, [rsp+1A0h+var_170]; this
0x14003659a  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x14003659f  nop
0x1400365a0  lea     rcx, [rsp+1A0h+var_150]; this
0x1400365a5  call    ??1SmartTelemetryActivityLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartTelemetryActivityLogger::~SmartTelemetryActivityLogger(void)
0x1400365aa  cmp     [rbp+0A0h+var_110], r12b
0x1400365ae  jz      short loc_1400365BF
0x1400365b0  lea     rdx, [rbp+0A0h+ActivityId]; ActivityId
0x1400365b4  mov     ecx, 2; ControlCode
0x1400365b9  call    cs:__imp_EventActivityIdControl
0x1400365bf  mov     eax, 8007000Eh
0x1400365c4  jmp     loc_14003665A
0x1400365c9  mov     rax, 8000000000h
0x1400365d3  mov     [rsi], rax
0x1400365d6  mov     [rsp+1A0h+var_140], r12d
0x1400365db  lea     rcx, [rbp+0A0h+psz]
0x1400365df  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400365e4  lea     rcx, [rsp+1A0h+var_168]
0x1400365e9  call    ??1?$vector@U?$pair@W4ComponentType@Client@AppV@@_K@std@@V?$allocator@U?$pair@W4ComponentType@Client@AppV@@_K@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<AppV::Client::ComponentType,unsigned __int64>>::~vector<std::pair<AppV::Client::ComponentType,unsigned __int64>>(void)
0x1400365ee  lea     rcx, [rbp+0A0h+var_A8]
0x1400365f2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400365f7  lea     rcx, ??_7ActivityData@Client@AppV@@6B@; const AppV::Client::ActivityData::`vftable'
0x1400365fe  mov     [rbp+0A0h+var_C0], rcx
0x140036602  lea     rcx, [rsp+1A0h+var_170]; this
0x140036607  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x14003660c  nop
0x14003660d  lea     rcx, [rsp+1A0h+var_150]; this
0x140036612  call    ??1SmartTelemetryActivityLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartTelemetryActivityLogger::~SmartTelemetryActivityLogger(void)
0x140036617  cmp     [rbp+0A0h+var_110], r12b
0x14003661b  jz      short loc_14003662C
0x14003661d  lea     rdx, [rbp+0A0h+ActivityId]; ActivityId
0x140036621  mov     ecx, 2; ControlCode
0x140036626  call    cs:__imp_EventActivityIdControl
0x14003662c  xor     eax, eax
0x14003662e  jmp     short loc_14003665A
0x140036630  mov     ebx, 80070057h
0x140036635  mov     [rsp+1A0h+var_140], ebx
0x140036639  lea     rcx, [rsp+1A0h+var_150]; this
0x14003663e  call    ??1SmartTelemetryActivityLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartTelemetryActivityLogger::~SmartTelemetryActivityLogger(void)
0x140036643  cmp     [rbp+0A0h+var_110], r12b
0x140036647  jz      short loc_140036658
0x140036649  lea     rdx, [rbp+0A0h+ActivityId]; ActivityId
0x14003664d  mov     ecx, 2; ControlCode
0x140036652  call    cs:__imp_EventActivityIdControl
0x140036658  mov     eax, ebx
0x14003665a  mov     rcx, [rbp+0A0h+var_40]
0x14003665e  xor     rcx, rsp; StackCookie
0x140036661  call    __security_check_cookie
0x140036666  add     rsp, 170h
0x14003666d  pop     r15
0x14003666f  pop     r14
0x140036671  pop     r12
0x140036673  pop     rdi
0x140036674  pop     rsi
0x140036675  pop     rbx
0x140036676  pop     rbp
0x140036677  retn
```
