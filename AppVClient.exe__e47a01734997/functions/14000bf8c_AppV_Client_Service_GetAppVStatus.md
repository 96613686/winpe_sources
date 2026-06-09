# AppV::Client::Service::GetAppVStatus

- ea: `0x14000bf8c`
- end: `0x14000c3fa`
- name: `AppV::Client::Service::GetAppVStatus`
- size: `1134`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x14000e504`

## callees

- `0x140004280`
- `0x140004558`
- `0x1400060e8`
- `0x140006304`
- `0x14000697c`
- `0x1400079b0`
- `0x140008e64`
- `0x14000bf8c`
- `0x140010158`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x14003d01c`
- `0x14006a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x14000bff7`
- `ole32!CoCreateInstance` at `0x14000bff7`

## string_xrefs

- `0x14000c001`: `AppV::Client::Service::GetAppVStatus`
- `0x14000c0fd`: `AppV::Client::Service::GetAppVStatus`
- `0x14000c26e`: `AppV::Client::Service::GetAppVStatus`
- `0x14000c032`: `appvConfiguration.CoCreateInstance: hr=%1%`
- `0x14000c12d`: `appvConfiguration get_IsEnabled: hr=%1%, enabled=%2%`
- `0x14000c29f`: `appvConfiguration get_IsRebootRequired: hr=%1%, rebootRequired=%2%`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall AppV::Client::Service::GetAppVStatus(char *a1, char *a2)
{
  char v4; // di
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rsi
  _QWORD *v13; // rcx
  _QWORD *v14; // rbx
  char v15; // al
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rsi
  _QWORD *v20; // rcx
  _QWORD *v21; // rbx
  _WORD v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  HRESULT v23; // [rsp+34h] [rbp-CCh] BYREF
  void *Block; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v26; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h]
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int128 v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int64 v31; // [rsp+88h] [rbp-78h]
  __int128 v32; // [rsp+90h] [rbp-70h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int128 v35; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v36; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+C8h] [rbp-38h]
  int v38; // [rsp+D0h] [rbp-30h]
  char *v39[2]; // [rsp+D8h] [rbp-28h] BYREF
  char *v40[2]; // [rsp+E8h] [rbp-18h] BYREF
  int v41; // [rsp+F8h] [rbp-8h]
  void **v42; // [rsp+108h] [rbp+8h] BYREF
  char *v43; // [rsp+118h] [rbp+18h] BYREF

  *a1 = 0;
  *a2 = 0;
  v22[0] = 0;
  ppv = 0;
  v4 = 1;
  v23 = CoCreateInstance(
          &GUID_52bc3999_6e52_4e8a_87c4_0a2a0cc359b1,
          0,
          1u,
          &GUID_2b478abb_f15e_4d52_9ea7_48d702b6c20e,
          &ppv);
  std::string::string(&v35, "AppV::Client::Service::GetAppVStatus");
  v38 = 57;
  AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v5);
  v29 = 0;
  v30 = 0;
  v31 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v29, L"appvConfiguration.CoCreateInstance: hr=%1%", 0x2Au);
  v7 = AppV::Log::fmt(v6, v39, &v29);
  v8 = AppV::LogFormatter::operator%<long>(v7, (__int64)&v23);
  v26 = 0;
  v27 = 0;
  v28 = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)&v26, L"Client", 6u);
  AppV::DecoratedLog::operator()((char *)&v35, 8, (int)&v26, v8);
  std::wstring::~wstring((char **)&v26);
  v39[0] = (char *)&AppV::LogFormatter::`vftable';
  std::wstring::~wstring(v40);
  std::wstring::~wstring((char **)&v29);
  std::string::~string((char **)&v35);
  if ( v23 >= 0 )
  {
    v23 = (*(__int64 (__fastcall **)(LPVOID, _WORD *))(*(_QWORD *)ppv + 40LL))(ppv, v22);
    std::string::string(&v35, "AppV::Client::Service::GetAppVStatus");
    v38 = 64;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v9);
    v32 = 0;
    v33 = 0;
    v34 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v32,
      L"appvConfiguration get_IsEnabled: hr=%1%, enabled=%2%",
      0x34u);
    v11 = AppV::Log::fmt(v10, v39, &v32);
    v12 = AppV::LogFormatter::operator%<long>(v11, (__int64)&v23);
    ++*(_DWORD *)(v12 + 8);
    AppV::LogFormatter::build_substitution_list(v12, &Block);
    v13 = Block;
    if ( Block )
    {
      *(_QWORD *)&v29 = v12;
      *((_QWORD *)&v29 + 1) = v22;
      std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_3c439174f6f5510bdb35d501e16de662_>(
        &v26,
        Block,
        0,
        &v29);
      v13 = Block;
    }
    Block = 0;
    if ( v13 )
    {
      do
      {
        v14 = (_QWORD *)*v13;
        operator delete(v13);
        v13 = v14;
      }
      while ( v14 );
    }
    v26 = 0;
    v27 = 0;
    v28 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v26, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)&v35, 8, (int)&v26, v12);
    std::wstring::~wstring((char **)&v26);
    v39[0] = (char *)&AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v40);
    std::wstring::~wstring((char **)&v32);
    std::string::~string((char **)&v35);
    if ( v23 < 0 || (v15 = 1, v22[0] != 0xFFFF) )
      v15 = 0;
    *a1 = v15;
    v23 = (*(__int64 (__fastcall **)(LPVOID, _WORD *))(*(_QWORD *)ppv + 48LL))(ppv, v22);
    std::string::string(v39, "AppV::Client::Service::GetAppVStatus");
    v41 = 70;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v16);
    v35 = 0;
    v36 = 0;
    v37 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v35,
      L"appvConfiguration get_IsRebootRequired: hr=%1%, rebootRequired=%2%",
      0x42u);
    v18 = AppV::Log::fmt(v17, &v42, &v35);
    v19 = AppV::LogFormatter::operator%<long>(v18, (__int64)&v23);
    ++*(_DWORD *)(v19 + 8);
    AppV::LogFormatter::build_substitution_list(v19, &Block);
    v20 = Block;
    if ( Block )
    {
      *(_QWORD *)&v29 = v19;
      *((_QWORD *)&v29 + 1) = v22;
      std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_3c439174f6f5510bdb35d501e16de662_>(
        &v26,
        Block,
        0,
        &v29);
      v20 = Block;
    }
    Block = 0;
    if ( v20 )
    {
      do
      {
        v21 = (_QWORD *)*v20;
        operator delete(v20);
        v20 = v21;
      }
      while ( v21 );
    }
    v32 = 0;
    v33 = 0;
    v34 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v32, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v39, 8, (int)&v32, v19);
    std::wstring::~wstring((char **)&v32);
    v42 = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(&v43);
    std::wstring::~wstring((char **)&v35);
    std::string::~string(v39);
    if ( v23 < 0 || v22[0] != 0xFFFF )
      v4 = 0;
    *a2 = v4;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
}

```

## disassembly

```asm
0x14000bf8c  mov     [rsp-8+arg_10], rbx
0x14000bf91  push    rbp
0x14000bf92  push    rsi
0x14000bf93  push    rdi
0x14000bf94  push    r12
0x14000bf96  push    r13
0x14000bf98  push    r14
0x14000bf9a  push    r15
0x14000bf9c  lea     rbp, [rsp-40h]
0x14000bfa1  sub     rsp, 140h
0x14000bfa8  mov     rax, cs:__security_cookie
0x14000bfaf  xor     rax, rsp
0x14000bfb2  mov     [rbp+70h+var_38], rax
0x14000bfb6  mov     r14, rdx
0x14000bfb9  mov     r15, rcx
0x14000bfbc  xor     r12d, r12d
0x14000bfbf  mov     [rcx], r12b
0x14000bfc2  mov     [rdx], r12b
0x14000bfc5  mov     [rsp+170h+var_13C], r12d
0x14000bfca  mov     [rsp+170h+var_140], r12w
0x14000bfd0  mov     [rsp+170h+var_130], r12
0x14000bfd5  lea     rax, [rsp+170h+var_130]
0x14000bfda  mov     [rsp+170h+ppv], rax; ppv
0x14000bfdf  lea     r9, _GUID_2b478abb_f15e_4d52_9ea7_48d702b6c20e; riid
0x14000bfe6  lea     edi, [r12+1]
0x14000bfeb  mov     r8d, edi; dwClsContext
0x14000bfee  xor     edx, edx; pUnkOuter
0x14000bff0  lea     rcx, _GUID_52bc3999_6e52_4e8a_87c4_0a2a0cc359b1; rclsid
0x14000bff7  call    cs:__imp_CoCreateInstance
0x14000bffd  mov     [rsp+170h+var_13C], eax
0x14000c001  lea     rdx, aAppvClientServ_44; "AppV::Client::Service::GetAppVStatus"
0x14000c008  lea     rcx, [rbp+70h+var_C0]
0x14000c00c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14000c011  mov     [rbp+70h+var_A0], 39h ; '9'
0x14000c018  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14000c01d  xorps   xmm0, xmm0
0x14000c020  movups  [rsp+170h+var_100], xmm0
0x14000c025  mov     [rbp+70h+var_F0], r12
0x14000c029  mov     [rbp+70h+var_E8], r12
0x14000c02d  lea     r8d, [r12+2Ah]
0x14000c032  lea     rdx, aAppvconfigurat_1; "appvConfiguration.CoCreateInstance: hr="...
0x14000c039  lea     rcx, [rsp+170h+var_100]
0x14000c03e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000c043  nop
0x14000c044  lea     r8, [rsp+170h+var_100]
0x14000c049  lea     rdx, [rbp+70h+var_98]
0x14000c04d  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14000c052  nop
0x14000c053  lea     rdx, [rsp+170h+var_13C]
0x14000c058  mov     rcx, rax
0x14000c05b  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14000c060  mov     rbx, rax
0x14000c063  xorps   xmm0, xmm0
0x14000c066  movups  [rsp+170h+var_128], xmm0
0x14000c06b  mov     [rsp+170h+var_118], r12
0x14000c070  mov     [rsp+170h+var_110], r12
0x14000c075  lea     r13d, [r12+6]
0x14000c07a  mov     r8d, r13d
0x14000c07d  lea     rdx, aClient; "Client"
0x14000c084  lea     rcx, [rsp+170h+var_128]
0x14000c089  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000c08e  nop
0x14000c08f  mov     r9, rbx
0x14000c092  lea     r8, [rsp+170h+var_128]
0x14000c097  lea     edx, [rdi+7]
0x14000c09a  lea     rcx, [rbp+70h+var_C0]
0x14000c09e  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14000c0a3  nop
0x14000c0a4  lea     rcx, [rsp+170h+var_128]
0x14000c0a9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000c0ae  nop
0x14000c0af  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14000c0b6  mov     [rbp+70h+var_98], rax
0x14000c0ba  lea     rcx, [rbp+70h+var_88]
0x14000c0be  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000c0c3  nop
0x14000c0c4  lea     rcx, [rsp+170h+var_100]
0x14000c0c9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000c0ce  nop
0x14000c0cf  lea     rcx, [rbp+70h+var_C0]
0x14000c0d3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000c0d8  cmp     [rsp+170h+var_13C], r12d
0x14000c0dd  jl      loc_14000C3BC
0x14000c0e3  mov     rcx, [rsp+170h+var_130]
0x14000c0e8  mov     rax, [rcx]
0x14000c0eb  lea     rdx, [rsp+170h+var_140]
0x14000c0f0  mov     rax, [rax+28h]
0x14000c0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c0f9  mov     [rsp+170h+var_13C], eax
0x14000c0fd  lea     rdx, aAppvClientServ_44; "AppV::Client::Service::GetAppVStatus"
0x14000c104  lea     rcx, [rbp+70h+var_C0]
0x14000c108  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14000c10d  mov     [rbp+70h+var_A0], 40h ; '@'
0x14000c114  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14000c119  xorps   xmm0, xmm0
0x14000c11c  movups  [rbp+70h+var_E0], xmm0
0x14000c120  mov     [rbp+70h+var_D0], r12
0x14000c124  mov     [rbp+70h+var_C8], r12
0x14000c128  lea     r8d, [r12+34h]
0x14000c12d  lea     rdx, aAppvconfigurat_0; "appvConfiguration get_IsEnabled: hr=%1%"...
0x14000c134  lea     rcx, [rbp+70h+var_E0]
0x14000c138  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000c13d  nop
0x14000c13e  lea     r8, [rbp+70h+var_E0]
0x14000c142  lea     rdx, [rbp+70h+var_98]
0x14000c146  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14000c14b  nop
0x14000c14c  lea     rdx, [rsp+170h+var_13C]
0x14000c151  mov     rcx, rax
0x14000c154  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14000c159  mov     rsi, rax
0x14000c15c  mov     r8d, [rax+8]
0x14000c160  lea     ecx, [r8+1]
0x14000c164  mov     [rax+8], ecx
0x14000c167  lea     rdx, [rsp+170h+Block]
0x14000c16c  mov     rcx, rax
0x14000c16f  call    ?build_substitution_list@LogFormatter@AppV@@AEAA?AV?$forward_list@VOffsetMarker@LogFormatter@AppV@@V?$allocator@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@H@Z; AppV::LogFormatter::build_substitution_list(int)
0x14000c174  nop
0x14000c175  mov     rcx, [rsp+170h+Block]
0x14000c17a  test    rcx, rcx
0x14000c17d  jz      short loc_14000C1A8
0x14000c17f  mov     r8d, r12d
0x14000c182  mov     qword ptr [rsp+170h+var_100], rsi
0x14000c187  lea     rax, [rsp+170h+var_140]
0x14000c18c  mov     qword ptr [rsp+170h+var_100+8], rax
0x14000c191  lea     r9, [rsp+170h+var_100]
0x14000c196  mov     rdx, rcx
0x14000c199  lea     rcx, [rsp+170h+var_128]
0x14000c19e  call    ??$for_each@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@std@@V_lambda_3c439174f6f5510bdb35d501e16de662_@@@std@@YA?AV_lambda_3c439174f6f5510bdb35d501e16de662_@@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@0@0V1@@Z; std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_3c439174f6f5510bdb35d501e16de662_>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_3c439174f6f5510bdb35d501e16de662_)
0x14000c1a3  mov     rcx, [rsp+170h+Block]; Block
0x14000c1a8  mov     [rsp+170h+Block], r12
0x14000c1ad  test    rcx, rcx
0x14000c1b0  jz      short loc_14000C1C7
0x14000c1b2  mov     rbx, [rcx]
0x14000c1b5  mov     edx, 20h ; ' '
0x14000c1ba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000c1bf  mov     rcx, rbx
0x14000c1c2  test    rbx, rbx
0x14000c1c5  jnz     short loc_14000C1B2
0x14000c1c7  xorps   xmm0, xmm0
0x14000c1ca  movups  [rsp+170h+var_128], xmm0
0x14000c1cf  mov     [rsp+170h+var_118], r12
0x14000c1d4  mov     [rsp+170h+var_110], r12
0x14000c1d9  mov     r8, r13
0x14000c1dc  lea     rdx, aClient; "Client"
0x14000c1e3  lea     rcx, [rsp+170h+var_128]
0x14000c1e8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000c1ed  nop
0x14000c1ee  mov     r9, rsi
0x14000c1f1  lea     r8, [rsp+170h+var_128]
0x14000c1f6  mov     edx, 8
0x14000c1fb  lea     rcx, [rbp+70h+var_C0]
0x14000c1ff  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14000c204  nop
0x14000c205  lea     rcx, [rsp+170h+var_128]
0x14000c20a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000c20f  nop
0x14000c210  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14000c217  mov     [rbp+70h+var_98], rax
0x14000c21b  lea     rcx, [rbp+70h+var_88]
0x14000c21f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000c224  nop
0x14000c225  lea     rcx, [rbp+70h+var_E0]
0x14000c229  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000c22e  nop
0x14000c22f  lea     rcx, [rbp+70h+var_C0]
0x14000c233  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000c238  or      r13d, 0FFFFFFFFh
0x14000c23c  cmp     [rsp+170h+var_13C], r12d
0x14000c241  jl      short loc_14000C24E
0x14000c243  cmp     r13w, [rsp+170h+var_140]
0x14000c249  mov     al, dil
0x14000c24c  jz      short loc_14000C251
0x14000c24e  mov     al, r12b
0x14000c251  mov     [r15], al
0x14000c254  mov     rcx, [rsp+170h+var_130]
0x14000c259  mov     rax, [rcx]
0x14000c25c  lea     rdx, [rsp+170h+var_140]
0x14000c261  mov     rax, [rax+30h]
0x14000c265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c26a  mov     [rsp+170h+var_13C], eax
0x14000c26e  lea     rdx, aAppvClientServ_44; "AppV::Client::Service::GetAppVStatus"
0x14000c275  lea     rcx, [rbp+70h+var_98]
0x14000c279  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14000c27e  mov     [rbp+70h+var_78], 46h ; 'F'
0x14000c285  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14000c28a  xorps   xmm0, xmm0
0x14000c28d  movups  [rbp+70h+var_C0], xmm0
0x14000c291  mov     [rbp+70h+var_B0], r12
0x14000c295  mov     [rbp+70h+var_A8], r12
0x14000c299  mov     r8d, 42h ; 'B'
0x14000c29f  lea     rdx, aAppvconfigurat; "appvConfiguration get_IsRebootRequired:"...
0x14000c2a6  lea     rcx, [rbp+70h+var_C0]
0x14000c2aa  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000c2af  nop
0x14000c2b0  lea     r8, [rbp+70h+var_C0]
0x14000c2b4  lea     rdx, [rbp+70h+var_68]
0x14000c2b8  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14000c2bd  nop
0x14000c2be  lea     rdx, [rsp+170h+var_13C]
0x14000c2c3  mov     rcx, rax
0x14000c2c6  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14000c2cb  mov     rsi, rax
0x14000c2ce  mov     r8d, [rax+8]
0x14000c2d2  lea     ecx, [r8+1]
0x14000c2d6  mov     [rax+8], ecx
0x14000c2d9  lea     rdx, [rsp+170h+Block]
0x14000c2de  mov     rcx, rax
0x14000c2e1  call    ?build_substitution_list@LogFormatter@AppV@@AEAA?AV?$forward_list@VOffsetMarker@LogFormatter@AppV@@V?$allocator@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@H@Z; AppV::LogFormatter::build_substitution_list(int)
0x14000c2e6  nop
0x14000c2e7  mov     rcx, [rsp+170h+Block]
0x14000c2ec  test    rcx, rcx
0x14000c2ef  jz      short loc_14000C31A
0x14000c2f1  mov     r8, r12
0x14000c2f4  mov     qword ptr [rsp+170h+var_100], rsi
0x14000c2f9  lea     rax, [rsp+170h+var_140]
0x14000c2fe  mov     qword ptr [rsp+170h+var_100+8], rax
0x14000c303  lea     r9, [rsp+170h+var_100]
0x14000c308  mov     rdx, rcx
0x14000c30b  lea     rcx, [rsp+170h+var_128]
0x14000c310  call    ??$for_each@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@std@@V_lambda_3c439174f6f5510bdb35d501e16de662_@@@std@@YA?AV_lambda_3c439174f6f5510bdb35d501e16de662_@@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@0@0V1@@Z; std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_3c439174f6f5510bdb35d501e16de662_>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_3c439174f6f5510bdb35d501e16de662_)
0x14000c315  mov     rcx, [rsp+170h+Block]; Block
0x14000c31a  mov     [rsp+170h+Block], r12
0x14000c31f  test    rcx, rcx
0x14000c322  jz      short loc_14000C339
0x14000c324  mov     rbx, [rcx]
0x14000c327  mov     edx, 20h ; ' '
0x14000c32c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000c331  mov     rcx, rbx
0x14000c334  test    rbx, rbx
0x14000c337  jnz     short loc_14000C324
0x14000c339  xorps   xmm0, xmm0
0x14000c33c  movups  [rbp+70h+var_E0], xmm0
0x14000c340  mov     [rbp+70h+var_D0], r12
0x14000c344  mov     [rbp+70h+var_C8], r12
0x14000c348  mov     r8d, 6
0x14000c34e  lea     rdx, aClient; "Client"
0x14000c355  lea     rcx, [rbp+70h+var_E0]
0x14000c359  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14000c35e  nop
0x14000c35f  mov     r9, rsi
0x14000c362  lea     r8, [rbp+70h+var_E0]
0x14000c366  mov     edx, 8
0x14000c36b  lea     rcx, [rbp+70h+var_98]
0x14000c36f  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14000c374  nop
0x14000c375  lea     rcx, [rbp+70h+var_E0]
0x14000c379  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000c37e  nop
0x14000c37f  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14000c386  mov     [rbp+70h+var_68], rax
0x14000c38a  lea     rcx, [rbp+70h+var_58]
0x14000c38e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000c393  nop
0x14000c394  lea     rcx, [rbp+70h+var_C0]
0x14000c398  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000c39d  nop
0x14000c39e  lea     rcx, [rbp+70h+var_98]
0x14000c3a2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000c3a7  cmp     [rsp+170h+var_13C], r12d
0x14000c3ac  jl      short loc_14000C3B6
0x14000c3ae  cmp     r13w, [rsp+170h+var_140]
0x14000c3b4  jz      short loc_14000C3B9
0x14000c3b6  mov     dil, r12b
0x14000c3b9  mov     [r14], dil
0x14000c3bc  mov     rcx, [rsp+170h+var_130]
0x14000c3c1  test    rcx, rcx
0x14000c3c4  jz      short loc_14000C3D3
0x14000c3c6  mov     rax, [rcx]
0x14000c3c9  mov     rax, [rax+10h]
0x14000c3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c3d2  nop
0x14000c3d3  mov     rcx, [rbp+70h+var_38]
0x14000c3d7  xor     rcx, rsp; StackCookie
0x14000c3da  call    __security_check_cookie
0x14000c3df  mov     rbx, [rsp+170h+arg_10]
0x14000c3e7  add     rsp, 140h
0x14000c3ee  pop     r15
0x14000c3f0  pop     r14
0x14000c3f2  pop     r13
0x14000c3f4  pop     r12
0x14000c3f6  pop     rdi
0x14000c3f7  pop     rsi
0x14000c3f8  pop     rbp
0x14000c3f9  retn
```
