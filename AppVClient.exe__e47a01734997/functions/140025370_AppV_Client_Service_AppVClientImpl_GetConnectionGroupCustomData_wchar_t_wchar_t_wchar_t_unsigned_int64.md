# AppV::Client::Service::AppVClientImpl::GetConnectionGroupCustomData(wchar_t *,wchar_t *,wchar_t * *,unsigned __int64 *)

- ea: `0x140025370`
- end: `0x140025815`
- name: `?GetConnectionGroupCustomData@AppVClientImpl@Service@Client@AppV@@UEAAJPEA_W0PEAPEA_WPEA_K@Z`
- size: `1189`
- prototype: `int(AppV::Client::Service::AppVClientImpl *__hidden this, wchar_t *, wchar_t *, wchar_t **, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004280`
- `0x140006304`
- `0x140008224`
- `0x140018bec`
- `0x1400233dc`
- `0x140024fa8`
- `0x140025370`
- `0x140026dd0`
- `0x140028e00`
- `0x14003a198`
- `0x14003a24c`
- `0x14006a010`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x14002544a`
- `ADVAPI32!EventActivityIdControl` at `0x140025647`
- `ADVAPI32!EventActivityIdControl` at `0x140025737`
- `ADVAPI32!EventActivityIdControl` at `0x1400257c3`
- `ADVAPI32!EventActivityIdControl` at `0x1400257ef`
- `ADVAPI32!EventActivityIdControl` at `0x14002544a`
- `ADVAPI32!EventActivityIdControl` at `0x140025647`
- `ADVAPI32!EventActivityIdControl` at `0x140025737`
- `ADVAPI32!EventActivityIdControl` at `0x1400257c3`
- `ADVAPI32!EventActivityIdControl` at `0x1400257ef`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14002567d`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14002567d`
- `OLEAUT32!__imp_SysAllocString` at `0x140025661`
- `OLEAUT32!__imp_SysAllocString` at `0x140025661`
- `OLEAUT32!__imp_SysStringLen` at `0x1400253cb`
- `OLEAUT32!__imp_SysStringLen` at `0x1400253e5`
- `OLEAUT32!__imp_SysStringLen` at `0x1400253cb`
- `OLEAUT32!__imp_SysStringLen` at `0x1400253e5`

## string_xrefs

- `0x140025676`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x14002568d`: `admin\appman\appv\client\host\service\publicapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AppV::Client::Service::AppVClientImpl::GetConnectionGroupCustomData(
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
  __int64 v16; // rdx
  __int64 v17; // r8
  unsigned __int64 v18; // rax
  volatile signed __int32 *v19; // rdi
  unsigned __int64 v20; // rax
  const OLECHAR *v21; // rcx
  volatile signed __int32 *v22; // rdi
  wchar_t *v23; // rax
  char *v24; // rax
  const char *v25; // rax
  volatile signed __int32 *v26; // rdi
  __int64 v27; // rdx
  __int64 v28; // r8
  volatile signed __int32 *v29; // rdi
  __int64 v30; // rdx
  __int64 v31; // r8
  _BYTE v32[8]; // [rsp+20h] [rbp-B1h] BYREF
  _BYTE v33[16]; // [rsp+28h] [rbp-A9h] BYREF
  int v34; // [rsp+38h] [rbp-99h]
  __int128 v35; // [rsp+40h] [rbp-91h] BYREF
  struct AppV::Client::ClientCatalog *v36; // [rsp+50h] [rbp-81h] BYREF
  _BYTE v37[4]; // [rsp+58h] [rbp-79h] BYREF
  GUID ActivityId; // [rsp+5Ch] [rbp-75h] BYREF
  OLECHAR *psz[2]; // [rsp+80h] [rbp-51h] BYREF
  __m128i si128; // [rsp+90h] [rbp-41h]
  struct _GUID v41; // [rsp+A0h] [rbp-31h] BYREF
  struct _GUID v42; // [rsp+B0h] [rbp-21h] BYREF
  _OWORD v43[2]; // [rsp+C0h] [rbp-11h] BYREF

  AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>((__int64)v37);
  AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(
    (AppV::Client::Service::SmartComMethodLogger *)v33,
    L"GetConnectionGroupCustomData");
  if ( a2 && SysStringLen(a2) && a3 && SysStringLen(a3) && a4 && a5 )
  {
    *a4 = 0;
    v32[0] = 0;
    v10 = AppV::Client::Service::AppVClientImpl::APICaller::Initialize(
            (AppV::Client::Service::AppVClientImpl::APICaller *)v32,
            0,
            a5);
    v11 = v10;
    if ( v10 < 0 )
    {
      v34 = v10;
      AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v32);
      AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
        (AppV::Client::Service::SmartComMethodLogger *)v33,
        v12,
        v13);
      if ( v37[0] )
        EventActivityIdControl(2u, &ActivityId);
      return v11;
    }
    v41 = GUID_NULL;
    v42 = GUID_NULL;
    v43[0] = 0;
    v43[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v43[0]) = 0;
    PackageIDAndPackageVersionID = AppV::Client::Service::AppVClientImpl::GetPackageIDAndPackageVersionID(
                                     a2,
                                     a3,
                                     &v41,
                                     &v42);
    if ( (PackageIDAndPackageVersionID & 0x8000000000LL) == 0
      || (v36 = 0,
          PackageIDAndPackageVersionID = AppV::Client::Service::AppVClientImpl::GetClientCatalog(&v36),
          (PackageIDAndPackageVersionID & 0x8000000000LL) == 0) )
    {
      *a5 = PackageIDAndPackageVersionID;
      v34 = -2147467259;
      std::wstring::~wstring((char **)v43);
      AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v32);
LABEL_26:
      AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
        (AppV::Client::Service::SmartComMethodLogger *)v33,
        v16,
        v17);
      if ( v37[0] )
        EventActivityIdControl(2u, &ActivityId);
      return 2147500037LL;
    }
    v35 = 0;
    v18 = (*(__int64 (__fastcall **)(struct AppV::Client::ClientCatalog *, struct _GUID *, __int128 *))(*(_QWORD *)v36 + 88LL))(
            v36,
            &v41,
            &v35);
    if ( (v18 & 0x8000000000LL) == 0 )
    {
      *a5 = v18;
      v34 = -2147467259;
      v19 = (volatile signed __int32 *)*((_QWORD *)&v35 + 1);
      if ( *((_QWORD *)&v35 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v35 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
          if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        }
      }
LABEL_25:
      std::wstring::~wstring((char **)v43);
      AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v32);
      goto LABEL_26;
    }
    *(_OWORD *)psz = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(psz[0]) = 0;
    v20 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR **))(*(_QWORD *)v35 + 72LL))(v35, psz);
    v21 = (const OLECHAR *)psz;
    if ( (v20 & 0x8000000000LL) == 0 )
    {
      *a5 = v20;
      v34 = -2147467259;
      std::wstring::~wstring((char **)psz);
      v22 = (volatile signed __int32 *)*((_QWORD *)&v35 + 1);
      if ( *((_QWORD *)&v35 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v35 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
          if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
        }
      }
      goto LABEL_25;
    }
    if ( si128.m128i_i64[1] > 7uLL )
      v21 = psz[0];
    v23 = SysAllocString(v21);
    *a4 = v23;
    if ( v23 )
    {
      *a5 = 0x8000000000LL;
      v34 = 0;
      std::wstring::~wstring((char **)psz);
      v29 = (volatile signed __int32 *)*((_QWORD *)&v35 + 1);
      if ( *((_QWORD *)&v35 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v35 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
          if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
        }
      }
      std::wstring::~wstring((char **)v43);
      AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v32);
      AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
        (AppV::Client::Service::SmartComMethodLogger *)v33,
        v30,
        v31);
      if ( v37[0] )
        EventActivityIdControl(2u, &ActivityId);
      return 0;
    }
    else
    {
      v24 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
      if ( v24 )
        v25 = v24 + 1;
      else
        v25 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
      *a5 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v25) << 52)
          | 0x18C230000000ELL;
      v34 = -2147024882;
      std::wstring::~wstring((char **)psz);
      v26 = (volatile signed __int32 *)*((_QWORD *)&v35 + 1);
      if ( *((_QWORD *)&v35 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v35 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
          if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
        }
      }
      std::wstring::~wstring((char **)v43);
      AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize((AppV::Client::Service::AppVClientImpl::APICaller *)v32);
      AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
        (AppV::Client::Service::SmartComMethodLogger *)v33,
        v27,
        v28);
      if ( v37[0] )
        EventActivityIdControl(2u, &ActivityId);
      return 2147942414LL;
    }
  }
  else
  {
    v34 = -2147024809;
    AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(
      (AppV::Client::Service::SmartComMethodLogger *)v33,
      v8,
      v9);
    if ( v37[0] )
      EventActivityIdControl(2u, &ActivityId);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140025370  push    rbp
0x140025372  push    rbx
0x140025373  push    rsi
0x140025374  push    rdi
0x140025375  push    r12
0x140025377  push    r14
0x140025379  push    r15
0x14002537b  lea     rbp, [rsp-1Fh]
0x140025380  sub     rsp, 0F0h
0x140025387  mov     rax, cs:__security_cookie
0x14002538e  xor     rax, rsp
0x140025391  mov     [rbp+4Fh+var_40], rax
0x140025395  mov     rsi, r9
0x140025398  mov     r14, r8
0x14002539b  mov     r15, rdx
0x14002539e  mov     rbx, [rbp+4Fh+arg_20]
0x1400253a2  lea     rcx, [rbp+4Fh+var_C8]
0x1400253a6  call    ??0?$ScopedActivity@VUserModeActivityIdControl@ETW@AppV@@@ETW@AppV@@QEAA@XZ; AppV::ETW::ScopedActivity<AppV::ETW::UserModeActivityIdControl>::ScopedActivity<AppV::ETW::UserModeActivityIdControl>(void)
0x1400253ab  lea     rdx, aGetconnectiong; "GetConnectionGroupCustomData"
0x1400253b2  lea     rcx, [rsp+120h+var_F8]; this
0x1400253b7  call    ??0SmartComMethodLogger@Service@Client@AppV@@QEAA@PEB_W@Z; AppV::Client::Service::SmartComMethodLogger::SmartComMethodLogger(wchar_t const *)
0x1400253bc  xor     r12d, r12d
0x1400253bf  test    r15, r15
0x1400253c2  jz      loc_1400257CD
0x1400253c8  mov     rcx, r15; pbstr
0x1400253cb  call    cs:__imp_SysStringLen
0x1400253d1  test    eax, eax
0x1400253d3  jz      loc_1400257CD
0x1400253d9  test    r14, r14
0x1400253dc  jz      loc_1400257CD
0x1400253e2  mov     rcx, r14; pbstr
0x1400253e5  call    cs:__imp_SysStringLen
0x1400253eb  test    eax, eax
0x1400253ed  jz      loc_1400257CD
0x1400253f3  test    rsi, rsi
0x1400253f6  jz      loc_1400257CD
0x1400253fc  test    rbx, rbx
0x1400253ff  jz      loc_1400257CD
0x140025405  mov     [rsi], r12
0x140025408  mov     [rsp+120h+var_100], r12b
0x14002540d  mov     r8, rbx; unsigned __int64 *
0x140025410  xor     edx, edx; bool
0x140025412  lea     rcx, [rsp+120h+var_100]; this
0x140025417  call    ?Initialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJ_NAEA_K@Z; AppV::Client::Service::AppVClientImpl::APICaller::Initialize(bool,unsigned __int64 &)
0x14002541c  mov     edi, eax
0x14002541e  test    eax, eax
0x140025420  jns     short loc_140025457
0x140025422  mov     [rsp+120h+var_E8], eax
0x140025426  lea     rcx, [rsp+120h+var_100]; this
0x14002542b  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140025430  nop
0x140025431  lea     rcx, [rsp+120h+var_F8]; this
0x140025436  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x14002543b  cmp     [rbp+4Fh+var_C8], r12b
0x14002543f  jz      short loc_140025450
0x140025441  lea     rdx, [rbp+4Fh+ActivityId]; ActivityId
0x140025445  lea     ecx, [r12+2]; ControlCode
0x14002544a  call    cs:__imp_EventActivityIdControl
0x140025450  mov     eax, edi
0x140025452  jmp     loc_1400257F7
0x140025457  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14002545e  movdqu  xmmword ptr [rbp+4Fh+var_80.Data1], xmm0
0x140025463  movdqu  xmmword ptr [rbp+4Fh+var_70.Data1], xmm0
0x140025468  xorps   xmm0, xmm0
0x14002546b  movups  [rbp+4Fh+var_60], xmm0
0x14002546f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140025477  movdqa  [rbp+4Fh+var_50], xmm1
0x14002547c  mov     word ptr [rbp+4Fh+var_60], r12w
0x140025481  lea     r9, [rbp+4Fh+var_70]; struct _GUID *
0x140025485  lea     r8, [rbp+4Fh+var_80]; struct _GUID *
0x140025489  mov     rdx, r14; wchar_t *
0x14002548c  mov     rcx, r15; wchar_t *
0x14002548f  call    ?GetPackageIDAndPackageVersionID@AppVClientImpl@Service@Client@AppV@@CA_KQEA_W0AEAU_GUID@@1@Z; AppV::Client::Service::AppVClientImpl::GetPackageIDAndPackageVersionID(wchar_t * const,wchar_t * const,_GUID &,_GUID &)
0x140025494  mov     rdi, 8000000000h
0x14002549e  test    rdi, rax
0x1400254a1  jnz     short loc_1400254C8
0x1400254a3  mov     [rbx], rax
0x1400254a6  mov     [rsp+120h+var_E8], 80004005h
0x1400254ae  lea     rcx, [rbp+4Fh+var_60]
0x1400254b2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400254b7  nop
0x1400254b8  lea     rcx, [rsp+120h+var_100]; this
0x1400254bd  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x1400254c2  nop
0x1400254c3  jmp     loc_14002562E
0x1400254c8  mov     [rsp+120h+var_D0], r12
0x1400254cd  lea     rcx, [rsp+120h+var_D0]; struct AppV::Client::ClientCatalog **
0x1400254d2  call    ?GetClientCatalog@AppVClientImpl@Service@Client@AppV@@CA_KAEAPEBVClientCatalog@34@@Z; AppV::Client::Service::AppVClientImpl::GetClientCatalog(AppV::Client::ClientCatalog const * &)
0x1400254d7  test    rdi, rax
0x1400254da  jnz     short loc_140025501
0x1400254dc  mov     [rbx], rax
0x1400254df  mov     [rsp+120h+var_E8], 80004005h
0x1400254e7  lea     rcx, [rbp+4Fh+var_60]
0x1400254eb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400254f0  nop
0x1400254f1  lea     rcx, [rsp+120h+var_100]; this
0x1400254f6  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x1400254fb  nop
0x1400254fc  jmp     loc_14002562E
0x140025501  xorps   xmm0, xmm0
0x140025504  movdqu  [rsp+120h+var_E0], xmm0
0x14002550a  mov     rcx, [rsp+120h+var_D0]
0x14002550f  mov     rax, [rcx]
0x140025512  lea     r8, [rsp+120h+var_E0]
0x140025517  lea     rdx, [rbp+4Fh+var_80]
0x14002551b  mov     rax, [rax+58h]
0x14002551f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025524  test    rdi, rax
0x140025527  jnz     short loc_14002558E
0x140025529  mov     [rbx], rax
0x14002552c  mov     [rsp+120h+var_E8], 80004005h
0x140025534  mov     rdi, qword ptr [rsp+120h+var_E0+8]
0x140025539  test    rdi, rdi
0x14002553c  jz      short loc_140025574
0x14002553e  or      ebx, 0FFFFFFFFh
0x140025541  mov     eax, ebx
0x140025543  lock xadd [rdi+8], eax
0x140025548  add     eax, ebx
0x14002554a  jnz     short loc_140025574
0x14002554c  mov     rax, [rdi]
0x14002554f  mov     rcx, rdi
0x140025552  mov     rax, [rax]
0x140025555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002555a  mov     eax, ebx
0x14002555c  lock xadd [rdi+0Ch], eax
0x140025561  add     eax, ebx
0x140025563  jnz     short loc_140025574
0x140025565  mov     rax, [rdi]
0x140025568  mov     rcx, rdi
0x14002556b  mov     rax, [rax+8]
0x14002556f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025574  lea     rcx, [rbp+4Fh+var_60]
0x140025578  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002557d  nop
0x14002557e  lea     rcx, [rsp+120h+var_100]; this
0x140025583  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x140025588  nop
0x140025589  jmp     loc_14002562E
0x14002558e  xorps   xmm0, xmm0
0x140025591  movups  xmmword ptr [rbp+4Fh+psz], xmm0
0x140025595  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14002559d  movdqu  [rbp+4Fh+var_90], xmm1
0x1400255a2  mov     word ptr [rbp+4Fh+psz], r12w
0x1400255a7  mov     rcx, qword ptr [rsp+120h+var_E0]
0x1400255ac  mov     rax, [rcx]
0x1400255af  lea     rdx, [rbp+4Fh+psz]
0x1400255b3  mov     rax, [rax+48h]
0x1400255b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400255bc  lea     rcx, [rbp+4Fh+psz]
0x1400255c0  test    rdi, rax
0x1400255c3  jnz     loc_140025657
0x1400255c9  mov     [rbx], rax
0x1400255cc  mov     [rsp+120h+var_E8], 80004005h
0x1400255d4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400255d9  mov     rdi, qword ptr [rsp+120h+var_E0+8]
0x1400255de  test    rdi, rdi
0x1400255e1  jz      short loc_140025619
0x1400255e3  or      ebx, 0FFFFFFFFh
0x1400255e6  mov     eax, ebx
0x1400255e8  lock xadd [rdi+8], eax
0x1400255ed  add     eax, ebx
0x1400255ef  jnz     short loc_140025619
0x1400255f1  mov     rax, [rdi]
0x1400255f4  mov     rcx, rdi
0x1400255f7  mov     rax, [rax]
0x1400255fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400255ff  mov     eax, ebx
0x140025601  lock xadd [rdi+0Ch], eax
0x140025606  add     eax, ebx
0x140025608  jnz     short loc_140025619
0x14002560a  mov     rax, [rdi]
0x14002560d  mov     rcx, rdi
0x140025610  mov     rax, [rax+8]
0x140025614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025619  lea     rcx, [rbp+4Fh+var_60]
0x14002561d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025622  nop
0x140025623  lea     rcx, [rsp+120h+var_100]; this
0x140025628  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x14002562d  nop
0x14002562e  lea     rcx, [rsp+120h+var_F8]; this
0x140025633  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x140025638  cmp     [rbp+4Fh+var_C8], r12b
0x14002563c  jz      short loc_14002564D
0x14002563e  lea     rdx, [rbp+4Fh+ActivityId]; ActivityId
0x140025642  mov     ecx, 2; ControlCode
0x140025647  call    cs:__imp_EventActivityIdControl
0x14002564d  mov     eax, 80004005h
0x140025652  jmp     loc_1400257F7
0x140025657  cmp     qword ptr [rbp+4Fh+var_90+8], 7
0x14002565c  cmova   rcx, [rbp+4Fh+psz]; psz
0x140025661  call    cs:__imp_SysAllocString
0x140025667  mov     [rsi], rax
0x14002566a  test    rax, rax
0x14002566d  jnz     loc_140025744
0x140025673  lea     edx, [rax+5Ch]; Ch
0x140025676  lea     rcx, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x14002567d  call    cs:__imp_strrchr
0x140025683  test    rax, rax
0x140025686  jz      short loc_14002568D
0x140025688  inc     rax
0x14002568b  jmp     short loc_140025694
0x14002568d  lea     rax, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140025694  mov     rdx, rax; char *
0x140025697  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14002569e  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400256a3  shl     rax, 34h
0x1400256a7  mov     rcx, 18C230000000Eh
0x1400256b1  or      rax, rcx
0x1400256b4  mov     [rbx], rax
0x1400256b7  mov     esi, 8007000Eh
0x1400256bc  mov     [rsp+120h+var_E8], esi
0x1400256c0  lea     rcx, [rbp+4Fh+psz]
0x1400256c4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400256c9  mov     rdi, qword ptr [rsp+120h+var_E0+8]
0x1400256ce  test    rdi, rdi
0x1400256d1  jz      short loc_140025709
0x1400256d3  or      ebx, 0FFFFFFFFh
0x1400256d6  mov     eax, ebx
0x1400256d8  lock xadd [rdi+8], eax
0x1400256dd  add     eax, ebx
0x1400256df  jnz     short loc_140025709
0x1400256e1  mov     rax, [rdi]
0x1400256e4  mov     rcx, rdi
0x1400256e7  mov     rax, [rax]
0x1400256ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400256ef  mov     eax, ebx
0x1400256f1  lock xadd [rdi+0Ch], eax
0x1400256f6  add     eax, ebx
0x1400256f8  jnz     short loc_140025709
0x1400256fa  mov     rax, [rdi]
0x1400256fd  mov     rcx, rdi
0x140025700  mov     rax, [rax+8]
0x140025704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025709  lea     rcx, [rbp+4Fh+var_60]
0x14002570d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025712  nop
0x140025713  lea     rcx, [rsp+120h+var_100]; this
0x140025718  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x14002571d  nop
0x14002571e  lea     rcx, [rsp+120h+var_F8]; this
0x140025723  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x140025728  cmp     [rbp+4Fh+var_C8], r12b
0x14002572c  jz      short loc_14002573D
0x14002572e  lea     rdx, [rbp+4Fh+ActivityId]; ActivityId
0x140025732  mov     ecx, 2; ControlCode
0x140025737  call    cs:__imp_EventActivityIdControl
0x14002573d  mov     eax, esi
0x14002573f  jmp     loc_1400257F7
0x140025744  mov     [rbx], rdi
0x140025747  mov     [rsp+120h+var_E8], r12d
0x14002574c  lea     rcx, [rbp+4Fh+psz]
0x140025750  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140025755  mov     rdi, qword ptr [rsp+120h+var_E0+8]
0x14002575a  test    rdi, rdi
0x14002575d  jz      short loc_140025795
0x14002575f  or      ebx, 0FFFFFFFFh
0x140025762  mov     eax, ebx
0x140025764  lock xadd [rdi+8], eax
0x140025769  add     eax, ebx
0x14002576b  jnz     short loc_140025795
0x14002576d  mov     rax, [rdi]
0x140025770  mov     rcx, rdi
0x140025773  mov     rax, [rax]
0x140025776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002577b  mov     eax, ebx
0x14002577d  lock xadd [rdi+0Ch], eax
0x140025782  add     eax, ebx
0x140025784  jnz     short loc_140025795
0x140025786  mov     rax, [rdi]
0x140025789  mov     rcx, rdi
0x14002578c  mov     rax, [rax+8]
0x140025790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025795  lea     rcx, [rbp+4Fh+var_60]
0x140025799  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002579e  nop
0x14002579f  lea     rcx, [rsp+120h+var_100]; this
0x1400257a4  call    ?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ; AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)
0x1400257a9  nop
0x1400257aa  lea     rcx, [rsp+120h+var_F8]; this
0x1400257af  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x1400257b4  cmp     [rbp+4Fh+var_C8], r12b
0x1400257b8  jz      short loc_1400257C9
0x1400257ba  lea     rdx, [rbp+4Fh+ActivityId]; ActivityId
0x1400257be  mov     ecx, 2; ControlCode
0x1400257c3  call    cs:__imp_EventActivityIdControl
0x1400257c9  xor     eax, eax
0x1400257cb  jmp     short loc_1400257F7
0x1400257cd  mov     ebx, 80070057h
0x1400257d2  mov     [rsp+120h+var_E8], ebx
0x1400257d6  lea     rcx, [rsp+120h+var_F8]; this
0x1400257db  call    ??1SmartComMethodLogger@Service@Client@AppV@@UEAA@XZ; AppV::Client::Service::SmartComMethodLogger::~SmartComMethodLogger(void)
0x1400257e0  cmp     [rbp+4Fh+var_C8], r12b
0x1400257e4  jz      short loc_1400257F5
0x1400257e6  lea     rdx, [rbp+4Fh+ActivityId]; ActivityId
0x1400257ea  mov     ecx, 2; ControlCode
0x1400257ef  call    cs:__imp_EventActivityIdControl
0x1400257f5  mov     eax, ebx
0x1400257f7  mov     rcx, [rbp+4Fh+var_40]
0x1400257fb  xor     rcx, rsp; StackCookie
  ... truncated ...
```
