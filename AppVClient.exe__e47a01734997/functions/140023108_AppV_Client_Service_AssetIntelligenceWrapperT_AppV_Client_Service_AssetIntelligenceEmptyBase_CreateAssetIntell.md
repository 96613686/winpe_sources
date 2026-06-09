# AppV::Client::Service::AssetIntelligenceWrapperT<AppV::Client::Service::AssetIntelligenceEmptyBase>::CreateAssetIntelligenceSafeArray(appv::utility::safe_array_with_structs<AssetIntelligenceProperties> &,uint,AssetIntelligenceProperties * &)

- ea: `0x140023108`
- end: `0x1400233d5`
- name: `?CreateAssetIntelligenceSafeArray@?$AssetIntelligenceWrapperT@VAssetIntelligenceEmptyBase@Service@Client@AppV@@@Service@Client@AppV@@AEAA_KAEAV?$safe_array_with_structs@UAssetIntelligenceProperties@@@utility@appv@@IAEAPEAUAssetIntelligenceProperties@@@Z`
- size: `717`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x140022fe4`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x14000697c`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x140023108`
- `0x140038f54`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x14003cc80`
- `0x14006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14002324b`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14002324b`
- `OLEAUT32!__imp_GetRecordInfoFromGuids` at `0x140023161`
- `OLEAUT32!__imp_GetRecordInfoFromGuids` at `0x140023161`

## string_xrefs

- `0x140023244`: `admin\appman\appv\client\host\service\AssetIntelligenceWrapper.h`
- `0x14002325b`: `admin\appman\appv\client\host\service\AssetIntelligenceWrapper.h`
- `0x140023172`: `AppV::Client::Service::AssetIntelligenceWrapperT<class AppV::Client::Service::AssetIntelligenceEmptyBase>::CreateAssetIntelligenceSafeArray`
- `0x1400232c9`: `AppV::Client::Service::AssetIntelligenceWrapperT<class AppV::Client::Service::AssetIntelligenceEmptyBase>::CreateAssetIntelligenceSafeArray`
- `0x1400232fa`: `Failed to create safe array. Error: %1%.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall AppV::Client::Service::AssetIntelligenceWrapperT<AppV::Client::Service::AssetIntelligenceEmptyBase>::CreateAssetIntelligenceSafeArray(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        _QWORD *a4)
{
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rbx
  char *v11; // rax
  const char *v12; // rax
  unsigned __int64 FileId; // rax
  __int64 v14; // rbx
  __int64 safe_array; // rdi
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rbx
  HRESULT RecordInfoFromGuids; // [rsp+30h] [rbp-79h] BYREF
  IRecordInfo *ppRecInfo; // [rsp+38h] [rbp-71h] BYREF
  __int64 v23; // [rsp+40h] [rbp-69h] BYREF
  __int128 v24; // [rsp+48h] [rbp-61h] BYREF
  __int128 v25; // [rsp+58h] [rbp-51h]
  __int128 v26; // [rsp+68h] [rbp-41h] BYREF
  __int128 v27; // [rsp+78h] [rbp-31h]
  char *v28[4]; // [rsp+88h] [rbp-21h] BYREF
  int v29; // [rsp+A8h] [rbp-1h]
  _QWORD v30[2]; // [rsp+B0h] [rbp+7h] BYREF
  char *v31[4]; // [rsp+C0h] [rbp+17h] BYREF

  ppRecInfo = 0;
  RecordInfoFromGuids = GetRecordInfoFromGuids(
                          &LIBID_AppVClientLib,
                          1u,
                          0,
                          0,
                          &GUID_bfc37837_81c7_4631_a42e_0ef60f0bff5b,
                          &ppRecInfo);
  if ( RecordInfoFromGuids >= 0 )
  {
    safe_array = appv::utility::safe_array_with_structs<AssetIntelligenceProperties>::create_safe_array(
                   a2,
                   (void **)&ppRecInfo,
                   a3,
                   a4);
    if ( (safe_array & 0x8000000000LL) == 0 )
    {
      std::string::string(
        v28,
        "AppV::Client::Service::AssetIntelligenceWrapperT<class AppV::Client::Service::AssetIntelligenceEmptyBase>::Creat"
        "eAssetIntelligenceSafeArray");
      v29 = 164;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v17);
      v24 = 0;
      v25 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v24, L"Failed to create safe array. Error: %1%.", 0x28u);
      v19 = AppV::Log::fmt(v18, v30, &v24);
      v23 = safe_array;
      v20 = AppV::LogFormatter::operator%(v19, &v23);
      v26 = 0;
      v27 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v26, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v28, 8, (int)&v26, v20);
      std::wstring::~wstring((char **)&v26);
      v30[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v31);
      std::wstring::~wstring((char **)&v24);
      std::string::~string(v28);
    }
    if ( ppRecInfo )
      ((void (__fastcall *)(IRecordInfo *))ppRecInfo->lpVtbl->Release)(ppRecInfo);
    return safe_array;
  }
  else
  {
    std::string::string(
      v28,
      "AppV::Client::Service::AssetIntelligenceWrapperT<class AppV::Client::Service::AssetIntelligenceEmptyBase>::CreateA"
      "ssetIntelligenceSafeArray");
    v29 = 156;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v7);
    v26 = 0;
    v27 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v26,
      L"Failed to call GetRecordInfoFromGuids. HRESULT: %1%.",
      0x34u);
    v9 = AppV::Log::fmt(v8, v30, &v26);
    v10 = AppV::LogFormatter::operator%<long>(v9, (__int64)&RecordInfoFromGuids);
    v24 = 0;
    v25 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v24, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v28, 8, (int)&v24, v10);
    std::wstring::~wstring((char **)&v24);
    v30[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v31);
    std::wstring::~wstring((char **)&v26);
    std::string::~string(v28);
    v11 = strrchr("admin\\appman\\appv\\client\\host\\service\\AssetIntelligenceWrapper.h", 92);
    if ( v11 )
      v12 = v11 + 1;
    else
      v12 = "admin\\appman\\appv\\client\\host\\service\\AssetIntelligenceWrapper.h";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v12);
    v14 = (unsigned int)RecordInfoFromGuids | (FileId << 52) | 0x132300000000LL;
    if ( ppRecInfo )
      ((void (__fastcall *)(IRecordInfo *))ppRecInfo->lpVtbl->Release)(ppRecInfo);
    return v14;
  }
}

```

## disassembly

```asm
0x140023108  mov     [rsp-8+arg_0], rbx
0x14002310d  push    rbp
0x14002310e  push    rsi
0x14002310f  push    rdi
0x140023110  lea     rbp, [rsp-47h]
0x140023115  sub     rsp, 0F0h
0x14002311c  mov     rax, cs:__security_cookie
0x140023123  xor     rax, rsp
0x140023126  mov     [rbp+57h+var_20], rax
0x14002312a  mov     rsi, r9
0x14002312d  mov     edi, r8d
0x140023130  mov     rbx, rdx
0x140023133  mov     [rbp+57h+var_C8], 0
0x14002313b  lea     rax, [rbp+57h+var_C8]
0x14002313f  mov     [rsp+100h+ppRecInfo], rax; ppRecInfo
0x140023144  lea     rax, _GUID_bfc37837_81c7_4631_a42e_0ef60f0bff5b
0x14002314b  mov     [rsp+100h+rGuidTypeInfo], rax; rGuidTypeInfo
0x140023150  xor     r9d, r9d; lcid
0x140023153  xor     r8d, r8d; uVerMinor
0x140023156  lea     edx, [r9+1]; uVerMajor
0x14002315a  lea     rcx, LIBID_AppVClientLib; rGuidTypeLib
0x140023161  call    cs:__imp_GetRecordInfoFromGuids
0x140023167  mov     [rbp+57h+var_D0], eax
0x14002316a  test    eax, eax
0x14002316c  jns     loc_1400232A9
0x140023172  lea     rdx, aAppvClientServ_58; "AppV::Client::Service::AssetIntelligenc"...
0x140023179  lea     rcx, [rbp+57h+var_78]
0x14002317d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140023182  mov     [rbp+57h+var_58], 9Ch
0x140023189  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14002318e  xorps   xmm0, xmm0
0x140023191  movups  [rbp+57h+var_98], xmm0
0x140023195  xorps   xmm1, xmm1
0x140023198  movdqu  [rbp+57h+var_88], xmm1
0x14002319d  mov     r8d, 34h ; '4'
0x1400231a3  lea     rdx, aFailedToCallGe; "Failed to call GetRecordInfoFromGuids. "...
0x1400231aa  lea     rcx, [rbp+57h+var_98]
0x1400231ae  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400231b3  nop
0x1400231b4  lea     r8, [rbp+57h+var_98]
0x1400231b8  lea     rdx, [rbp+57h+var_50]
0x1400231bc  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x1400231c1  nop
0x1400231c2  lea     rdx, [rbp+57h+var_D0]
0x1400231c6  mov     rcx, rax
0x1400231c9  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x1400231ce  mov     rbx, rax
0x1400231d1  xorps   xmm0, xmm0
0x1400231d4  movups  [rbp+57h+var_B8], xmm0
0x1400231d8  xorps   xmm1, xmm1
0x1400231db  movdqu  [rbp+57h+var_A8], xmm1
0x1400231e0  mov     r8d, 6
0x1400231e6  lea     rdx, aClient; "Client"
0x1400231ed  lea     rcx, [rbp+57h+var_B8]
0x1400231f1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400231f6  nop
0x1400231f7  mov     r9, rbx
0x1400231fa  lea     r8, [rbp+57h+var_B8]
0x1400231fe  mov     edx, 8
0x140023203  lea     rcx, [rbp+57h+var_78]
0x140023207  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14002320c  nop
0x14002320d  lea     rcx, [rbp+57h+var_B8]
0x140023211  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023216  nop
0x140023217  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14002321e  mov     [rbp+57h+var_50], rax
0x140023222  lea     rcx, [rbp+57h+var_40]
0x140023226  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002322b  nop
0x14002322c  lea     rcx, [rbp+57h+var_98]
0x140023230  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023235  nop
0x140023236  lea     rcx, [rbp+57h+var_78]
0x14002323a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002323f  mov     edx, 5Ch ; '\'; Ch
0x140023244  lea     rcx, aAdminAppmanApp_3; "admin\\appman\\appv\\client\\host\\serv"...
0x14002324b  call    cs:__imp_strrchr
0x140023251  test    rax, rax
0x140023254  jz      short loc_14002325B
0x140023256  inc     rax
0x140023259  jmp     short loc_140023262
0x14002325b  lea     rax, aAdminAppmanApp_3; "admin\\appman\\appv\\client\\host\\serv"...
0x140023262  mov     rdx, rax; char *
0x140023265  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14002326c  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140023271  mov     rbx, rax
0x140023274  shl     rbx, 34h
0x140023278  mov     ecx, [rbp+57h+var_D0]
0x14002327b  or      rbx, rcx
0x14002327e  mov     rax, 132300000000h
0x140023288  or      rbx, rax
0x14002328b  mov     rcx, [rbp+57h+var_C8]
0x14002328f  test    rcx, rcx
0x140023292  jz      short loc_1400232A1
0x140023294  mov     rax, [rcx]
0x140023297  mov     rax, [rax+10h]
0x14002329b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400232a0  nop
0x1400232a1  mov     rax, rbx
0x1400232a4  jmp     loc_1400233B6
0x1400232a9  mov     r9, rsi
0x1400232ac  mov     r8d, edi
0x1400232af  lea     rdx, [rbp+57h+var_C8]
0x1400232b3  mov     rcx, rbx
0x1400232b6  call    ?create_safe_array@?$safe_array_with_structs@UAssetIntelligenceProperties@@@utility@appv@@QEAA_KAEBV?$CComPtr@UIRecordInfo@@@ATL@@IAEAPEAUAssetIntelligenceProperties@@@Z; appv::utility::safe_array_with_structs<AssetIntelligenceProperties>::create_safe_array(ATL::CComPtr<IRecordInfo> const &,uint,AssetIntelligenceProperties * &)
0x1400232bb  mov     rdi, rax
0x1400232be  bt      rax, 27h ; '''
0x1400232c3  jb      loc_14002339D
0x1400232c9  lea     rdx, aAppvClientServ_58; "AppV::Client::Service::AssetIntelligenc"...
0x1400232d0  lea     rcx, [rbp+57h+var_78]
0x1400232d4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400232d9  mov     [rbp+57h+var_58], 0A4h
0x1400232e0  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x1400232e5  xorps   xmm0, xmm0
0x1400232e8  movups  [rbp+57h+var_B8], xmm0
0x1400232ec  xorps   xmm1, xmm1
0x1400232ef  movdqu  [rbp+57h+var_A8], xmm1
0x1400232f4  mov     r8d, 28h ; '('
0x1400232fa  lea     rdx, aFailedToCreate_6; "Failed to create safe array. Error: %1%"...
0x140023301  lea     rcx, [rbp+57h+var_B8]
0x140023305  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14002330a  nop
0x14002330b  lea     r8, [rbp+57h+var_B8]
0x14002330f  lea     rdx, [rbp+57h+var_50]
0x140023313  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140023318  nop
0x140023319  mov     [rbp+57h+var_C0], rdi
0x14002331d  lea     rdx, [rbp+57h+var_C0]
0x140023321  mov     rcx, rax
0x140023324  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBVErrorCode@1@@Z; AppV::LogFormatter::operator%(AppV::ErrorCode const &)
0x140023329  mov     rbx, rax
0x14002332c  xorps   xmm0, xmm0
0x14002332f  movups  [rbp+57h+var_98], xmm0
0x140023333  xorps   xmm1, xmm1
0x140023336  movdqu  [rbp+57h+var_88], xmm1
0x14002333b  mov     r8d, 6
0x140023341  lea     rdx, aClient; "Client"
0x140023348  lea     rcx, [rbp+57h+var_98]
0x14002334c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140023351  nop
0x140023352  mov     r9, rbx
0x140023355  lea     r8, [rbp+57h+var_98]
0x140023359  mov     edx, 8
0x14002335e  lea     rcx, [rbp+57h+var_78]
0x140023362  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140023367  nop
0x140023368  lea     rcx, [rbp+57h+var_98]
0x14002336c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023371  nop
0x140023372  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140023379  mov     [rbp+57h+var_50], rax
0x14002337d  lea     rcx, [rbp+57h+var_40]
0x140023381  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023386  nop
0x140023387  lea     rcx, [rbp+57h+var_B8]
0x14002338b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023390  nop
0x140023391  lea     rcx, [rbp+57h+var_78]
0x140023395  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14002339a  nop
0x14002339b  jmp     short $+2
0x14002339d  mov     rcx, [rbp+57h+var_C8]
0x1400233a1  test    rcx, rcx
0x1400233a4  jz      short loc_1400233B3
0x1400233a6  mov     rax, [rcx]
0x1400233a9  mov     rax, [rax+10h]
0x1400233ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400233b2  nop
0x1400233b3  mov     rax, rdi
0x1400233b6  mov     rcx, [rbp+57h+var_20]
0x1400233ba  xor     rcx, rsp; StackCookie
0x1400233bd  call    __security_check_cookie
0x1400233c2  mov     rbx, [rsp+100h+arg_0]
0x1400233ca  add     rsp, 0F0h
0x1400233d1  pop     rdi
0x1400233d2  pop     rsi
0x1400233d3  pop     rbp
0x1400233d4  retn
```
