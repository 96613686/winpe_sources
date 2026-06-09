# AppV::Client::Publishing::Configurations::ServerRegRecord::RemoveServer(uint)

- ea: `0x14005d298`
- end: `0x14005d680`
- name: `?RemoveServer@ServerRegRecord@Configurations@Publishing@Client@AppV@@SA_KI@Z`
- size: `1000`
- prototype: `unsigned __int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config`

## callers

- `0x14005b390`

## callees

- `0x140004280`
- `0x140004558`
- `0x1400060e8`
- `0x140006304`
- `0x14000697c`
- `0x140006a94`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x14003d01c`
- `0x14005bc9c`
- `0x14005bf98`
- `0x14005c32c`
- `0x14005d298`

## import_xrefs

- `ADVAPI32!RegDeleteTreeW` at `0x14005d4c8`
- `ADVAPI32!RegDeleteTreeW` at `0x14005d4c8`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005d467`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005d5ef`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005d467`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005d5ef`

## string_xrefs

- `0x14005d460`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005d477`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005d5e8`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005d5ff`: `admin\appman\appv\client\publishing\configurations\serverregrecord.cpp`
- `0x14005d520`: `Couldn't delete registry tree.\n winerr = %1%\n sub key: %2%`
- `0x14005d328`: `AppV::Client::Publishing::Configurations::ServerRegRecord::RemoveServer`
- `0x14005d4ec`: `AppV::Client::Publishing::Configurations::ServerRegRecord::RemoveServer`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
unsigned __int64 __fastcall AppV::Client::Publishing::Configurations::ServerRegRecord::RemoveServer(unsigned int a1)
{
  unsigned __int64 v1; // rbx
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rdi
  _QWORD *v5; // rcx
  _QWORD *v6; // rbx
  char *v7; // rax
  const char *v8; // rax
  const WCHAR *v9; // rdx
  LSTATUS v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  LPCWSTR *v15; // rcx
  __int64 v16; // rbx
  char *v17; // rax
  const char *v18; // rax
  unsigned __int64 FileId; // rax
  bool v21; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v22; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int v23; // [rsp+30h] [rbp-D0h] BYREF
  void *Block; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v25[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h] BYREF
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int64 v31; // [rsp+88h] [rbp-78h]
  LPCWSTR lpSubKey[3]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v33; // [rsp+A8h] [rbp-58h]
  char *v34[4]; // [rsp+B0h] [rbp-50h] BYREF
  int v35; // [rsp+D0h] [rbp-30h]
  _QWORD v36[2]; // [rsp+D8h] [rbp-28h] BYREF
  char *v37[5]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v38[8]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v39; // [rsp+118h] [rbp+18h] BYREF
  __int64 v40; // [rsp+128h] [rbp+28h]
  __int64 v41; // [rsp+130h] [rbp+30h]
  __int128 v42; // [rsp+138h] [rbp+38h] BYREF
  __int64 v43; // [rsp+148h] [rbp+48h]
  __int64 v44; // [rsp+150h] [rbp+50h]

  v22 = a1;
  v38[5] = 0;
  v39 = 0;
  v40 = 0;
  v41 = 7;
  LOWORD(v39) = 0;
  v42 = 0;
  v43 = 0;
  v44 = 7;
  LOWORD(v42) = 0;
  v21 = 0;
  v1 = AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRecord(
         1,
         a1,
         (struct AppV::Client::Publishing::Configurations::ServerProperties *)v38,
         &v21);
  if ( (v1 & 0x8000000000LL) != 0 )
  {
    if ( v21 )
    {
      AppV::Client::Publishing::Configurations::ServerRegRecord::GetRegServerKeyPath((__int64)lpSubKey, 0, v22);
      v9 = (const WCHAR *)lpSubKey;
      if ( v33 > 7 )
        v9 = lpSubKey[0];
      v10 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, v9);
      v23 = v10;
      if ( !v10 || v10 == 3 || v10 == 2 )
      {
        std::wstring::~wstring((char **)lpSubKey);
        v1 = 0x8000000000LL;
      }
      else
      {
        std::string::string(v34, "AppV::Client::Publishing::Configurations::ServerRegRecord::RemoveServer");
        v35 = 152;
        AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v11);
        v26 = 0;
        v27 = 0;
        v28 = 0;
        std::wstring::_Construct<1,wchar_t const *>(
          (char **)&v26,
          L"Couldn't delete registry tree.\n winerr = %1%\n sub key: %2%",
          0x3Au);
        v13 = AppV::Log::fmt(v12, v36, &v26);
        v14 = AppV::LogFormatter::operator%<long>(v13, (__int64)&v23);
        v15 = lpSubKey;
        if ( v33 > 7 )
          v15 = (LPCWSTR *)lpSubKey[0];
        Block = v15;
        v16 = AppV::LogFormatter::operator%<wchar_t const *>(v14, &Block);
        v29 = 0;
        v30 = 0;
        v31 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v29, L"Publishing", 0xAu);
        AppV::DecoratedLog::operator()((char *)v34, 1, (int)&v29, v16);
        std::wstring::~wstring((char **)&v29);
        v36[0] = &AppV::LogFormatter::`vftable';
        std::wstring::~wstring(v37);
        std::wstring::~wstring((char **)&v26);
        std::string::~string(v34);
        v17 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp", 92);
        if ( v17 )
          v18 = v17 + 1;
        else
          v18 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp";
        FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v18);
        v1 = v23 | (FileId << 52) | 0x132700000000LL;
        std::wstring::~wstring((char **)lpSubKey);
      }
    }
    else
    {
      std::string::string(v34, "AppV::Client::Publishing::Configurations::ServerRegRecord::RemoveServer");
      v35 = 139;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v2);
      v29 = 0;
      v30 = 0;
      v31 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v29,
        L"Failed to modify the server entry [%1%] since it is controlled by Group Policy.",
        0x4Fu);
      v4 = AppV::Log::fmt(v3, v36, &v29);
      ++*(_DWORD *)(v4 + 8);
      AppV::LogFormatter::build_substitution_list(v4, &Block);
      v5 = Block;
      if ( Block )
      {
        v25[0] = v4;
        v25[1] = &v22;
        std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_660ab698431ada8fe6f3f7d090bba4fe_>(
          &v26,
          Block,
          0,
          v25);
        v5 = Block;
      }
      Block = 0;
      if ( v5 )
      {
        do
        {
          v6 = (_QWORD *)*v5;
          operator delete(v5);
          v5 = v6;
        }
        while ( v6 );
      }
      v26 = 0;
      v27 = 0;
      v28 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v26, L"Publishing", 0xAu);
      AppV::DecoratedLog::operator()((char *)v34, 1, (int)&v26, v4);
      std::wstring::~wstring((char **)&v26);
      v36[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v37);
      std::wstring::~wstring((char **)&v29);
      std::string::~string(v34);
      v7 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp", 92);
      if ( v7 )
        v8 = v7 + 1;
      else
        v8 = "admin\\appman\\appv\\client\\publishing\\configurations\\serverregrecord.cpp";
      v1 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v8) << 52)
         | 0x110700000701LL;
    }
  }
  std::wstring::~wstring((char **)&v42);
  std::wstring::~wstring((char **)&v39);
  return v1;
}

```

## disassembly

```asm
0x14005d298  mov     [rsp-8+arg_8], rbx
0x14005d29d  mov     [rsp-8+arg_10], rsi
0x14005d2a2  push    rbp
0x14005d2a3  push    rdi
0x14005d2a4  push    r14
0x14005d2a6  lea     rbp, [rsp-80h]
0x14005d2ab  sub     rsp, 180h
0x14005d2b2  mov     rax, cs:__security_cookie
0x14005d2b9  xor     rax, rsp
0x14005d2bc  mov     [rbp+90h+var_20], rax
0x14005d2c0  mov     [rsp+190h+var_168], ecx
0x14005d2c4  xor     esi, esi
0x14005d2c6  mov     [rbp+90h+var_7B], sil
0x14005d2ca  xorps   xmm0, xmm0
0x14005d2cd  movups  [rbp+90h+var_78], xmm0
0x14005d2d1  mov     [rbp+90h+var_68], rsi
0x14005d2d5  lea     edi, [rsi+7]
0x14005d2d8  mov     [rbp+90h+var_60], rdi
0x14005d2dc  mov     word ptr [rbp+90h+var_78], si
0x14005d2e0  movups  [rbp+90h+var_58], xmm0
0x14005d2e4  mov     [rbp+90h+var_48], rsi
0x14005d2e8  mov     [rbp+90h+var_40], rdi
0x14005d2ec  mov     word ptr [rbp+90h+var_58], si
0x14005d2f0  mov     [rsp+190h+var_170], sil
0x14005d2f5  lea     r9, [rsp+190h+var_170]; bool *
0x14005d2fa  lea     r8, [rbp+90h+var_80]; struct AppV::Client::Publishing::Configurations::ServerProperties *
0x14005d2fe  mov     edx, ecx; unsigned int
0x14005d300  mov     cl, 1; bool
0x14005d302  call    ?ReadRegServerRecord@ServerRegRecord@Configurations@Publishing@Client@AppV@@CA_K_NIAEAUServerProperties@2345@AEA_N@Z; AppV::Client::Publishing::Configurations::ServerRegRecord::ReadRegServerRecord(bool,uint,AppV::Client::Publishing::Configurations::ServerProperties &,bool &)
0x14005d307  mov     rbx, rax
0x14005d30a  mov     r14, 8000000000h
0x14005d314  test    r14, rax
0x14005d317  jz      loc_14005D647
0x14005d31d  cmp     [rsp+190h+var_170], sil
0x14005d322  jnz     loc_14005D4A3
0x14005d328  lea     rdx, aAppvClientPubl_9; "AppV::Client::Publishing::Configuration"...
0x14005d32f  lea     rcx, [rbp+90h+var_E0]
0x14005d333  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005d338  mov     [rbp+90h+var_C0], 8Bh
0x14005d33f  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005d344  xorps   xmm0, xmm0
0x14005d347  movups  [rsp+190h+var_120], xmm0
0x14005d34c  mov     [rbp+90h+var_110], rsi
0x14005d350  mov     [rbp+90h+var_108], rsi
0x14005d354  lea     r8d, [rsi+4Fh]
0x14005d358  lea     rdx, aFailedToModify; "Failed to modify the server entry [%1%]"...
0x14005d35f  lea     rcx, [rsp+190h+var_120]
0x14005d364  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005d369  nop
0x14005d36a  lea     r8, [rsp+190h+var_120]
0x14005d36f  lea     rdx, [rbp+90h+var_B8]
0x14005d373  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005d378  mov     rdi, rax
0x14005d37b  mov     r8d, [rax+8]
0x14005d37f  lea     ecx, [r8+1]
0x14005d383  mov     [rax+8], ecx
0x14005d386  lea     rdx, [rsp+190h+Block]
0x14005d38b  mov     rcx, rax
0x14005d38e  call    ?build_substitution_list@LogFormatter@AppV@@AEAA?AV?$forward_list@VOffsetMarker@LogFormatter@AppV@@V?$allocator@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@H@Z; AppV::LogFormatter::build_substitution_list(int)
0x14005d393  nop
0x14005d394  mov     rcx, [rsp+190h+Block]
0x14005d399  test    rcx, rcx
0x14005d39c  jz      short loc_14005D3C7
0x14005d39e  mov     r8d, esi
0x14005d3a1  mov     [rsp+190h+var_150], rdi
0x14005d3a6  lea     rax, [rsp+190h+var_168]
0x14005d3ab  mov     [rsp+190h+var_148], rax
0x14005d3b0  lea     r9, [rsp+190h+var_150]
0x14005d3b5  mov     rdx, rcx
0x14005d3b8  lea     rcx, [rsp+190h+var_140]
0x14005d3bd  call    ??$for_each@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@std@@V_lambda_660ab698431ada8fe6f3f7d090bba4fe_@@@std@@YA?AV_lambda_660ab698431ada8fe6f3f7d090bba4fe_@@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@0@0V1@@Z; std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_660ab698431ada8fe6f3f7d090bba4fe_>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_660ab698431ada8fe6f3f7d090bba4fe_)
0x14005d3c2  mov     rcx, [rsp+190h+Block]; Block
0x14005d3c7  mov     [rsp+190h+Block], rsi
0x14005d3cc  test    rcx, rcx
0x14005d3cf  jz      short loc_14005D3E6
0x14005d3d1  mov     rbx, [rcx]
0x14005d3d4  mov     edx, 20h ; ' '
0x14005d3d9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14005d3de  mov     rcx, rbx
0x14005d3e1  test    rbx, rbx
0x14005d3e4  jnz     short loc_14005D3D1
0x14005d3e6  xorps   xmm0, xmm0
0x14005d3e9  movups  [rsp+190h+var_140], xmm0
0x14005d3ee  mov     [rsp+190h+var_130], rsi
0x14005d3f3  mov     [rsp+190h+var_128], rsi
0x14005d3f8  mov     r8d, 0Ah
0x14005d3fe  lea     rdx, aPublishing; "Publishing"
0x14005d405  lea     rcx, [rsp+190h+var_140]
0x14005d40a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005d40f  nop
0x14005d410  mov     r9, rdi
0x14005d413  lea     r8, [rsp+190h+var_140]
0x14005d418  mov     edx, 1
0x14005d41d  lea     rcx, [rbp+90h+var_E0]
0x14005d421  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005d426  nop
0x14005d427  lea     rcx, [rsp+190h+var_140]
0x14005d42c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005d431  nop
0x14005d432  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005d439  mov     [rbp+90h+var_B8], rax
0x14005d43d  lea     rcx, [rbp+90h+var_A8]
0x14005d441  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005d446  nop
0x14005d447  lea     rcx, [rsp+190h+var_120]
0x14005d44c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005d451  nop
0x14005d452  lea     rcx, [rbp+90h+var_E0]
0x14005d456  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005d45b  mov     edx, 5Ch ; '\'; Ch
0x14005d460  lea     rcx, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005d467  call    cs:__imp_strrchr
0x14005d46d  test    rax, rax
0x14005d470  jz      short loc_14005D477
0x14005d472  inc     rax
0x14005d475  jmp     short loc_14005D47E
0x14005d477  lea     rax, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005d47e  mov     rdx, rax; char *
0x14005d481  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005d488  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005d48d  shl     rax, 34h
0x14005d491  mov     rbx, 110700000701h
0x14005d49b  or      rbx, rax
0x14005d49e  jmp     loc_14005D647
0x14005d4a3  mov     r8d, [rsp+190h+var_168]
0x14005d4a8  xor     edx, edx
0x14005d4aa  lea     rcx, [rbp+90h+lpSubKey]
0x14005d4ae  call    ?GetRegServerKeyPath@ServerRegRecord@Configurations@Publishing@Client@AppV@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NI@Z; AppV::Client::Publishing::Configurations::ServerRegRecord::GetRegServerKeyPath(bool,uint)
0x14005d4b3  nop
0x14005d4b4  lea     rdx, [rbp+90h+lpSubKey]
0x14005d4b8  cmp     [rbp+90h+var_E8], rdi
0x14005d4bc  cmova   rdx, [rbp+90h+lpSubKey]; lpSubKey
0x14005d4c1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14005d4c8  call    cs:__imp_RegDeleteTreeW
0x14005d4ce  mov     [rsp+190h+var_160], eax
0x14005d4d2  test    eax, eax
0x14005d4d4  jz      loc_14005D63B
0x14005d4da  cmp     eax, 3
0x14005d4dd  jz      loc_14005D63B
0x14005d4e3  cmp     eax, 2
0x14005d4e6  jz      loc_14005D63B
0x14005d4ec  lea     rdx, aAppvClientPubl_9; "AppV::Client::Publishing::Configuration"...
0x14005d4f3  lea     rcx, [rbp+90h+var_E0]
0x14005d4f7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005d4fc  mov     [rbp+90h+var_C0], 98h
0x14005d503  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14005d508  xorps   xmm0, xmm0
0x14005d50b  movups  [rsp+190h+var_140], xmm0
0x14005d510  mov     [rsp+190h+var_130], rsi
0x14005d515  mov     [rsp+190h+var_128], rsi
0x14005d51a  mov     r8d, 3Ah ; ':'
0x14005d520  lea     rdx, aCouldnTDeleteR; "Couldn't delete registry tree.\n winerr"...
0x14005d527  lea     rcx, [rsp+190h+var_140]
0x14005d52c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005d531  nop
0x14005d532  lea     r8, [rsp+190h+var_140]
0x14005d537  lea     rdx, [rbp+90h+var_B8]
0x14005d53b  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005d540  nop
0x14005d541  lea     rdx, [rsp+190h+var_160]
0x14005d546  mov     rcx, rax
0x14005d549  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14005d54e  lea     rcx, [rbp+90h+lpSubKey]
0x14005d552  cmp     [rbp+90h+var_E8], rdi
0x14005d556  cmova   rcx, [rbp+90h+lpSubKey]
0x14005d55b  mov     [rsp+190h+Block], rcx
0x14005d560  lea     rdx, [rsp+190h+Block]
0x14005d565  mov     rcx, rax
0x14005d568  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x14005d56d  mov     rbx, rax
0x14005d570  xorps   xmm0, xmm0
0x14005d573  movups  [rsp+190h+var_120], xmm0
0x14005d578  mov     [rbp+90h+var_110], rsi
0x14005d57c  mov     [rbp+90h+var_108], rsi
0x14005d580  mov     r8d, 0Ah
0x14005d586  lea     rdx, aPublishing; "Publishing"
0x14005d58d  lea     rcx, [rsp+190h+var_120]
0x14005d592  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005d597  nop
0x14005d598  mov     r9, rbx
0x14005d59b  lea     r8, [rsp+190h+var_120]
0x14005d5a0  mov     edx, 1
0x14005d5a5  lea     rcx, [rbp+90h+var_E0]
0x14005d5a9  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005d5ae  nop
0x14005d5af  lea     rcx, [rsp+190h+var_120]
0x14005d5b4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005d5b9  nop
0x14005d5ba  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005d5c1  mov     [rbp+90h+var_B8], rax
0x14005d5c5  lea     rcx, [rbp+90h+var_A8]
0x14005d5c9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005d5ce  nop
0x14005d5cf  lea     rcx, [rsp+190h+var_140]
0x14005d5d4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005d5d9  nop
0x14005d5da  lea     rcx, [rbp+90h+var_E0]
0x14005d5de  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14005d5e3  mov     edx, 5Ch ; '\'; Ch
0x14005d5e8  lea     rcx, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005d5ef  call    cs:__imp_strrchr
0x14005d5f5  test    rax, rax
0x14005d5f8  jz      short loc_14005D5FF
0x14005d5fa  inc     rax
0x14005d5fd  jmp     short loc_14005D606
0x14005d5ff  lea     rax, aAdminAppmanApp_6; "admin\\appman\\appv\\client\\publishing"...
0x14005d606  mov     rdx, rax; char *
0x14005d609  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005d610  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005d615  mov     rbx, rax
0x14005d618  shl     rbx, 34h
0x14005d61c  mov     ecx, [rsp+190h+var_160]
0x14005d620  or      rbx, rcx
0x14005d623  mov     rax, 132700000000h
0x14005d62d  or      rbx, rax
0x14005d630  lea     rcx, [rbp+90h+lpSubKey]
0x14005d634  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005d639  jmp     short loc_14005D647
0x14005d63b  lea     rcx, [rbp+90h+lpSubKey]
0x14005d63f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005d644  mov     rbx, r14
0x14005d647  lea     rcx, [rbp+90h+var_58]
0x14005d64b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005d650  lea     rcx, [rbp+90h+var_78]
0x14005d654  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005d659  mov     rax, rbx
0x14005d65c  mov     rcx, [rbp+90h+var_20]
0x14005d660  xor     rcx, rsp; StackCookie
0x14005d663  call    __security_check_cookie
0x14005d668  lea     r11, [rsp+190h+var_10]
0x14005d670  mov     rbx, [r11+28h]
0x14005d674  mov     rsi, [r11+30h]
0x14005d678  mov     rsp, r11
0x14005d67b  pop     r14
0x14005d67d  pop     rdi
0x14005d67e  pop     rbp
0x14005d67f  retn
```
