# AppV::Client::Publishing::Configurations::ServerTaskRecord::GetTaskService(ATL::CComPtr<ITaskService> &)

- ea: `0x1400610b8`
- end: `0x1400614d3`
- name: `?GetTaskService@ServerTaskRecord@Configurations@Publishing@Client@AppV@@CA_KAEAV?$CComPtr@UITaskService@@@ATL@@@Z`
- size: `1051`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140062bd4`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x14000697c`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x14003becc`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x1400610b8`
- `0x14006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140061204`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14006142a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140061204`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14006142a`
- `OLEAUT32!__imp_VariantInit` at `0x140061255`
- `OLEAUT32!__imp_VariantInit` at `0x14006126c`
- `OLEAUT32!__imp_VariantInit` at `0x140061285`
- `OLEAUT32!__imp_VariantInit` at `0x14006129c`
- `OLEAUT32!__imp_VariantInit` at `0x140061255`
- `OLEAUT32!__imp_VariantInit` at `0x14006126c`
- `OLEAUT32!__imp_VariantInit` at `0x140061285`
- `OLEAUT32!__imp_VariantInit` at `0x14006129c`
- `OLEAUT32!__imp_VariantClear` at `0x1400612ff`
- `OLEAUT32!__imp_VariantClear` at `0x140061312`
- `OLEAUT32!__imp_VariantClear` at `0x140061325`
- `OLEAUT32!__imp_VariantClear` at `0x140061337`
- `OLEAUT32!__imp_VariantClear` at `0x1400612ff`
- `OLEAUT32!__imp_VariantClear` at `0x140061312`
- `OLEAUT32!__imp_VariantClear` at `0x140061325`
- `OLEAUT32!__imp_VariantClear` at `0x140061337`
- `ole32!CoCreateInstance` at `0x140061118`
- `ole32!CoCreateInstance` at `0x140061118`

## string_xrefs

- `0x140061381`: `Task Service couldn't be connected.\n HResult: %1%`
- `0x1400611fd`: `admin\appman\appv\client\publishing\configurations\servertaskrecord.cpp`
- `0x140061214`: `admin\appman\appv\client\publishing\configurations\servertaskrecord.cpp`
- `0x140061423`: `admin\appman\appv\client\publishing\configurations\servertaskrecord.cpp`
- `0x14006143a`: `admin\appman\appv\client\publishing\configurations\servertaskrecord.cpp`
- `0x14006115b`: `Couldn't create Co instance.\n HResult: %1%`
- `0x14006112a`: `AppV::Client::Publishing::Configurations::ServerTaskRecord::GetTaskService`
- `0x140061350`: `AppV::Client::Publishing::Configurations::ServerTaskRecord::GetTaskService`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall AppV::Client::Publishing::Configurations::ServerTaskRecord::GetTaskService(LPVOID *ppv)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rbx
  char *v6; // rax
  const char *v7; // rax
  unsigned __int64 FileId; // rax
  unsigned __int64 v9; // rcx
  __int64 v10; // rax
  LPVOID v12; // rdi
  __int64 (__fastcall *v13)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v14; // xmm10
  char *pRecInfo; // xmm11_8
  __int128 v16; // xmm8
  __int64 v17; // xmm9_8
  __int128 v18; // xmm6
  __int64 v19; // xmm7_8
  HRESULT v20; // eax
  HRESULT v21; // eax
  HRESULT v22; // eax
  HRESULT v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rbx
  char *v28; // rax
  const char *v29; // rax
  unsigned __int64 v30; // rax
  VARIANTARG v31; // [rsp+38h] [rbp-D0h] BYREF
  VARIANTARG v32; // [rsp+50h] [rbp-B8h] BYREF
  VARIANTARG v33; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+80h] [rbp-88h]
  VARIANTARG pvarg; // [rsp+88h] [rbp-80h] BYREF
  __int128 v36; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v37; // [rsp+B8h] [rbp-50h]
  __int128 v38; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v39; // [rsp+D8h] [rbp-30h]
  __int128 v40; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v41; // [rsp+F8h] [rbp-10h]
  int v42; // [rsp+108h] [rbp+0h]
  __int128 v43; // [rsp+118h] [rbp+10h] BYREF
  char *v44[4]; // [rsp+128h] [rbp+20h] BYREF

  *(_DWORD *)&v31.vt = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, ppv);
  if ( *(int *)&v31.vt < 0 )
  {
    std::string::string(&v40, "AppV::Client::Publishing::Configurations::ServerTaskRecord::GetTaskService");
    v42 = 229;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v2);
    v36 = 0;
    v37 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v36, L"Couldn't create Co instance.\n HResult: %1%", 0x2Au);
    v4 = AppV::Log::fmt(v3, &v43, &v36);
    v5 = AppV::LogFormatter::operator%<long>(v4, (__int64)&v31);
    v38 = 0;
    v39 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v38, L"Publishing", 0xAu);
    AppV::DecoratedLog::operator()((char *)&v40, 1, (int)&v38, v5);
    std::wstring::~wstring((char **)&v38);
    *(_QWORD *)&v43 = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v44);
    std::wstring::~wstring((char **)&v36);
    std::string::~string((char **)&v40);
    v6 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\servertaskrecord.cpp", 92);
    if ( v6 )
      v7 = v6 + 1;
    else
      v7 = "admin\\appman\\appv\\client\\publishing\\configurations\\servertaskrecord.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v7);
    v9 = (FileId << 52) | *(unsigned int *)&v31.vt;
    v10 = 0x1C2700000000LL;
    return v9 | v10;
  }
  v12 = *ppv;
  v13 = *(__int64 (__fastcall **)(LPVOID, __int128 *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)v12 + 80LL);
  VariantInit(&pvarg);
  v14 = *(_OWORD *)&pvarg.vt;
  pRecInfo = (char *)pvarg.pRecInfo;
  VariantInit((VARIANTARG *)&v33.decVal.8);
  v16 = *(_OWORD *)&v33.decVal.Lo32;
  v17 = v34;
  VariantInit((VARIANTARG *)&v32.decVal.8);
  v18 = *(_OWORD *)&v32.decVal.Lo32;
  v19 = *(_QWORD *)&v33.vt;
  VariantInit((VARIANTARG *)&v31.decVal.8);
  v43 = v14;
  v44[0] = pRecInfo;
  v40 = v16;
  v41 = v17;
  v36 = v18;
  *(_QWORD *)&v37 = v19;
  v38 = *(_OWORD *)&v31.decVal.Lo32;
  *(_QWORD *)&v39 = *(_QWORD *)&v32.vt;
  *(_DWORD *)&v31.vt = v13(v12, &v38, &v36, &v40, &v43);
  v20 = VariantClear((VARIANTARG *)&v31.decVal.8);
  if ( v20 < 0 )
    _com_issue_error(v20);
  v21 = VariantClear((VARIANTARG *)&v32.decVal.8);
  if ( v21 < 0 )
    _com_issue_error(v21);
  v22 = VariantClear((VARIANTARG *)&v33.decVal.8);
  if ( v22 < 0 )
    _com_issue_error(v22);
  v23 = VariantClear(&pvarg);
  if ( v23 < 0 )
    _com_issue_error(v23);
  if ( *(int *)&v31.vt < 0 )
  {
    std::string::string(&v40, "AppV::Client::Publishing::Configurations::ServerTaskRecord::GetTaskService");
    v42 = 240;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v24);
    v36 = 0;
    v37 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v36,
      L"Task Service couldn't be connected.\n HResult: %1%",
      0x31u);
    v26 = AppV::Log::fmt(v25, &v43, &v36);
    v27 = AppV::LogFormatter::operator%<long>(v26, (__int64)&v31);
    v38 = 0;
    v39 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v38, L"Publishing", 0xAu);
    AppV::DecoratedLog::operator()((char *)&v40, 1, (int)&v38, v27);
    std::wstring::~wstring((char **)&v38);
    *(_QWORD *)&v43 = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v44);
    std::wstring::~wstring((char **)&v36);
    std::string::~string((char **)&v40);
    v28 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\servertaskrecord.cpp", 92);
    if ( v28 )
      v29 = v28 + 1;
    else
      v29 = "admin\\appman\\appv\\client\\publishing\\configurations\\servertaskrecord.cpp";
    v30 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v29);
    v9 = (v30 << 52) | *(unsigned int *)&v31.vt;
    v10 = 0x1E2700000000LL;
    return v9 | v10;
  }
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x1400610b8  mov     rax, rsp
0x1400610bb  mov     [rax+10h], rbx
0x1400610bf  mov     [rax+18h], rdi
0x1400610c3  push    rbp
0x1400610c4  lea     rbp, [rax-0B8h]
0x1400610cb  sub     rsp, 1B0h
0x1400610d2  movaps  xmmword ptr [rax-18h], xmm6
0x1400610d6  movaps  xmmword ptr [rax-28h], xmm7
0x1400610da  movaps  xmmword ptr [rax-38h], xmm8
0x1400610df  movaps  xmmword ptr [rax-48h], xmm9
0x1400610e4  movaps  xmmword ptr [rax-58h], xmm10
0x1400610e9  movaps  xmmword ptr [rax-68h], xmm11
0x1400610ee  mov     rax, cs:__security_cookie
0x1400610f5  xor     rax, rsp
0x1400610f8  mov     [rbp+0B0h+var_70], rax
0x1400610fc  mov     rdi, rcx
0x1400610ff  mov     [rsp+1B0h+ppv], rcx; ppv
0x140061104  lea     r9, IID_ITaskService; riid
0x14006110b  xor     edx, edx; pUnkOuter
0x14006110d  lea     r8d, [rdx+1]; dwClsContext
0x140061111  lea     rcx, CLSID_TaskScheduler; rclsid
0x140061118  call    cs:__imp_CoCreateInstance
0x14006111e  mov     dword ptr [rsp+1B0h+var_180], eax
0x140061122  test    eax, eax
0x140061124  jns     loc_140061247
0x14006112a  lea     rdx, aAppvClientPubl_6; "AppV::Client::Publishing::Configuration"...
0x140061131  lea     rcx, [rbp+0B0h+var_D0]
0x140061135  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14006113a  mov     [rbp+0B0h+var_B0], 0E5h
0x140061141  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140061146  xorps   xmm0, xmm0
0x140061149  movups  [rbp+0B0h+var_110], xmm0
0x14006114d  xorps   xmm1, xmm1
0x140061150  movdqu  [rbp+0B0h+var_100], xmm1
0x140061155  mov     r8d, 2Ah ; '*'
0x14006115b  lea     rdx, aCouldnTCreateC; "Couldn't create Co instance.\n HResult:"...
0x140061162  lea     rcx, [rbp+0B0h+var_110]
0x140061166  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14006116b  nop
0x14006116c  lea     r8, [rbp+0B0h+var_110]
0x140061170  lea     rdx, [rbp+0B0h+var_A0]
0x140061174  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140061179  nop
0x14006117a  lea     rdx, [rsp+1B0h+var_180]
0x14006117f  mov     rcx, rax
0x140061182  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x140061187  mov     rbx, rax
0x14006118a  xorps   xmm0, xmm0
0x14006118d  movups  [rbp+0B0h+var_F0], xmm0
0x140061191  xorps   xmm1, xmm1
0x140061194  movdqu  [rbp+0B0h+var_E0], xmm1
0x140061199  mov     r8d, 0Ah
0x14006119f  lea     rdx, aPublishing; "Publishing"
0x1400611a6  lea     rcx, [rbp+0B0h+var_F0]
0x1400611aa  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400611af  nop
0x1400611b0  mov     r9, rbx
0x1400611b3  lea     r8, [rbp+0B0h+var_F0]
0x1400611b7  mov     edx, 1
0x1400611bc  lea     rcx, [rbp+0B0h+var_D0]
0x1400611c0  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x1400611c5  nop
0x1400611c6  lea     rcx, [rbp+0B0h+var_F0]
0x1400611ca  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400611cf  nop
0x1400611d0  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x1400611d7  mov     qword ptr [rbp+0B0h+var_A0], rax
0x1400611db  lea     rcx, [rbp+0B0h+var_90]
0x1400611df  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400611e4  nop
0x1400611e5  lea     rcx, [rbp+0B0h+var_110]
0x1400611e9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400611ee  nop
0x1400611ef  lea     rcx, [rbp+0B0h+var_D0]
0x1400611f3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400611f8  mov     edx, 5Ch ; '\'; Ch
0x1400611fd  lea     rcx, aAdminAppmanApp_20; "admin\\appman\\appv\\client\\publishing"...
0x140061204  call    cs:__imp_strrchr
0x14006120a  test    rax, rax
0x14006120d  jz      short loc_140061214
0x14006120f  inc     rax
0x140061212  jmp     short loc_14006121B
0x140061214  lea     rax, aAdminAppmanApp_20; "admin\\appman\\appv\\client\\publishing"...
0x14006121b  mov     rdx, rax; char *
0x14006121e  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140061225  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14006122a  shl     rax, 34h
0x14006122e  mov     ecx, dword ptr [rsp+1B0h+var_180]
0x140061232  or      rcx, rax
0x140061235  mov     rax, 1C2700000000h
0x14006123f  or      rax, rcx
0x140061242  jmp     loc_140061474
0x140061247  mov     rdi, [rdi]
0x14006124a  mov     rax, [rdi]
0x14006124d  mov     rbx, [rax+50h]
0x140061251  lea     rcx, [rbp+0B0h+pvarg]; pvarg
0x140061255  call    cs:__imp_VariantInit
0x14006125b  nop
0x14006125c  movups  xmm10, xmmword ptr [rbp+0B0h+pvarg]
0x140061261  movsd   xmm11, qword ptr [rbp+0B0h+pvarg+10h]
0x140061267  lea     rcx, [rsp+1B0h+var_150+8]; pvarg
0x14006126c  call    cs:__imp_VariantInit
0x140061272  nop
0x140061273  movups  xmm8, xmmword ptr [rsp+1B0h+var_150+8]
0x140061279  movsd   xmm9, [rsp+1B0h+var_138]
0x140061280  lea     rcx, [rsp+1B0h+var_168+8]; pvarg
0x140061285  call    cs:__imp_VariantInit
0x14006128b  nop
0x14006128c  movups  xmm6, xmmword ptr [rsp+1B0h+var_168+8]
0x140061291  movsd   xmm7, qword ptr [rsp+1B0h+var_150]
0x140061297  lea     rcx, [rsp+1B0h+var_180+8]; pvarg
0x14006129c  call    cs:__imp_VariantInit
0x1400612a2  nop
0x1400612a3  movups  xmm0, xmmword ptr [rsp+1B0h+var_180+8]
0x1400612a8  movsd   xmm1, qword ptr [rsp+1B0h+var_168]
0x1400612ae  movaps  [rbp+0B0h+var_A0], xmm10
0x1400612b3  movsd   [rbp+0B0h+var_90], xmm11
0x1400612b9  movaps  [rbp+0B0h+var_D0], xmm8
0x1400612be  movsd   [rbp+0B0h+var_C0], xmm9
0x1400612c4  movaps  [rbp+0B0h+var_110], xmm6
0x1400612c8  movsd   qword ptr [rbp+0B0h+var_100], xmm7
0x1400612cd  movaps  [rbp+0B0h+var_F0], xmm0
0x1400612d1  movsd   qword ptr [rbp+0B0h+var_E0], xmm1
0x1400612d6  lea     rax, [rbp+0B0h+var_A0]
0x1400612da  mov     [rsp+1B0h+ppv], rax
0x1400612df  lea     r9, [rbp+0B0h+var_D0]
0x1400612e3  lea     r8, [rbp+0B0h+var_110]
0x1400612e7  lea     rdx, [rbp+0B0h+var_F0]
0x1400612eb  mov     rcx, rdi
0x1400612ee  mov     rax, rbx
0x1400612f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400612f6  mov     dword ptr [rsp+1B0h+var_180], eax
0x1400612fa  lea     rcx, [rsp+1B0h+var_180+8]; pvarg
0x1400612ff  call    cs:__imp_VariantClear
0x140061305  test    eax, eax
0x140061307  js      loc_1400614BB
0x14006130d  lea     rcx, [rsp+1B0h+var_168+8]; pvarg
0x140061312  call    cs:__imp_VariantClear
0x140061318  test    eax, eax
0x14006131a  js      loc_1400614C3
0x140061320  lea     rcx, [rsp+1B0h+var_150+8]; pvarg
0x140061325  call    cs:__imp_VariantClear
0x14006132b  test    eax, eax
0x14006132d  js      loc_1400614CB
0x140061333  lea     rcx, [rbp+0B0h+pvarg]; pvarg
0x140061337  call    cs:__imp_VariantClear
0x14006133d  test    eax, eax
0x14006133f  js      loc_1400614B3
0x140061345  cmp     dword ptr [rsp+1B0h+var_180], 0
0x14006134a  jge     loc_14006146A
0x140061350  lea     rdx, aAppvClientPubl_6; "AppV::Client::Publishing::Configuration"...
0x140061357  lea     rcx, [rbp+0B0h+var_D0]
0x14006135b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140061360  mov     [rbp+0B0h+var_B0], 0F0h
0x140061367  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14006136c  xorps   xmm0, xmm0
0x14006136f  movups  [rbp+0B0h+var_110], xmm0
0x140061373  xorps   xmm1, xmm1
0x140061376  movdqu  [rbp+0B0h+var_100], xmm1
0x14006137b  mov     r8d, 31h ; '1'
0x140061381  lea     rdx, aTaskServiceCou_0; "Task Service couldn't be connected.\n H"...
0x140061388  lea     rcx, [rbp+0B0h+var_110]
0x14006138c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140061391  nop
0x140061392  lea     r8, [rbp+0B0h+var_110]
0x140061396  lea     rdx, [rbp+0B0h+var_A0]
0x14006139a  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14006139f  nop
0x1400613a0  lea     rdx, [rsp+1B0h+var_180]
0x1400613a5  mov     rcx, rax
0x1400613a8  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x1400613ad  mov     rbx, rax
0x1400613b0  xorps   xmm0, xmm0
0x1400613b3  movups  [rbp+0B0h+var_F0], xmm0
0x1400613b7  xorps   xmm1, xmm1
0x1400613ba  movdqu  [rbp+0B0h+var_E0], xmm1
0x1400613bf  mov     r8d, 0Ah
0x1400613c5  lea     rdx, aPublishing; "Publishing"
0x1400613cc  lea     rcx, [rbp+0B0h+var_F0]
0x1400613d0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400613d5  nop
0x1400613d6  mov     r9, rbx
0x1400613d9  lea     r8, [rbp+0B0h+var_F0]
0x1400613dd  mov     edx, 1
0x1400613e2  lea     rcx, [rbp+0B0h+var_D0]
0x1400613e6  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x1400613eb  nop
0x1400613ec  lea     rcx, [rbp+0B0h+var_F0]
0x1400613f0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400613f5  nop
0x1400613f6  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x1400613fd  mov     qword ptr [rbp+0B0h+var_A0], rax
0x140061401  lea     rcx, [rbp+0B0h+var_90]
0x140061405  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14006140a  nop
0x14006140b  lea     rcx, [rbp+0B0h+var_110]
0x14006140f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140061414  nop
0x140061415  lea     rcx, [rbp+0B0h+var_D0]
0x140061419  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14006141e  mov     edx, 5Ch ; '\'; Ch
0x140061423  lea     rcx, aAdminAppmanApp_20; "admin\\appman\\appv\\client\\publishing"...
0x14006142a  call    cs:__imp_strrchr
0x140061430  test    rax, rax
0x140061433  jz      short loc_14006143A
0x140061435  inc     rax
0x140061438  jmp     short loc_140061441
0x14006143a  lea     rax, aAdminAppmanApp_20; "admin\\appman\\appv\\client\\publishing"...
0x140061441  mov     rdx, rax; char *
0x140061444  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14006144b  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140061450  shl     rax, 34h
0x140061454  mov     ecx, dword ptr [rsp+1B0h+var_180]
0x140061458  or      rcx, rax
0x14006145b  mov     rax, 1E2700000000h
0x140061465  jmp     loc_14006123F
0x14006146a  mov     rax, 8000000000h
0x140061474  mov     rcx, [rbp+0B0h+var_70]
0x140061478  xor     rcx, rsp; StackCookie
0x14006147b  call    __security_check_cookie
0x140061480  lea     r11, [rsp+1B0h+var_s0]
0x140061488  mov     rbx, [r11+18h]
0x14006148c  mov     rdi, [r11+20h]
0x140061490  movaps  xmm6, xmmword ptr [r11-10h]
0x140061495  movaps  xmm7, xmmword ptr [r11-20h]
0x14006149a  movaps  xmm8, xmmword ptr [r11-30h]
0x14006149f  movaps  xmm9, xmmword ptr [r11-40h]
0x1400614a4  movaps  xmm10, xmmword ptr [r11-50h]
0x1400614a9  movaps  xmm11, xmmword ptr [r11-60h]
0x1400614ae  mov     rsp, r11
0x1400614b1  pop     rbp
0x1400614b2  retn
0x1400614b3  mov     ecx, eax; int
0x1400614b5  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400614bb  mov     ecx, eax; int
0x1400614bd  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400614c3  mov     ecx, eax; int
0x1400614c5  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1400614cb  mov     ecx, eax; int
0x1400614cd  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
