# AppV::Client::Publishing::Configurations::ServerTaskRecord::GetTaskFolder(ATL::CComPtr<ITaskService> const &,ATL::CComPtr<ITaskFolder> &)

- ea: `0x140060830`
- end: `0x140060f18`
- name: `?GetTaskFolder@ServerTaskRecord@Configurations@Publishing@Client@AppV@@CA_KAEBV?$CComPtr@UITaskService@@@ATL@@AEAV?$CComPtr@UITaskFolder@@@7@@Z`
- size: `1768`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x140062bd4`

## callees

- `0x140004280`
- `0x140004558`
- `0x1400060e8`
- `0x140006304`
- `0x14000697c`
- `0x140006a94`
- `0x140008e64`
- `0x14000a2e8`
- `0x140010158`
- `0x140018bec`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x14003d01c`
- `0x14005e938`
- `0x140060830`
- `0x14006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140060a05`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140060c1e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140060e5e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140060a05`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140060c1e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140060e5e`
- `OLEAUT32!__imp_SysAllocString` at `0x14006087f`
- `OLEAUT32!__imp_SysAllocString` at `0x140060ac7`
- `OLEAUT32!__imp_SysAllocString` at `0x140060cb8`
- `OLEAUT32!__imp_SysAllocString` at `0x140060d01`
- `OLEAUT32!__imp_SysAllocString` at `0x14006087f`
- `OLEAUT32!__imp_SysAllocString` at `0x140060ac7`
- `OLEAUT32!__imp_SysAllocString` at `0x140060cb8`
- `OLEAUT32!__imp_SysAllocString` at `0x140060d01`
- `OLEAUT32!__imp_SysFreeString` at `0x1400608b1`
- `OLEAUT32!__imp_SysFreeString` at `0x140060af7`
- `OLEAUT32!__imp_SysFreeString` at `0x140060d41`
- `OLEAUT32!__imp_SysFreeString` at `0x1400608b1`
- `OLEAUT32!__imp_SysFreeString` at `0x140060af7`
- `OLEAUT32!__imp_SysFreeString` at `0x140060d41`
- `OLEAUT32!__imp_VariantClear` at `0x140060ca5`
- `OLEAUT32!__imp_VariantClear` at `0x140060d4d`
- `OLEAUT32!__imp_VariantClear` at `0x140060ca5`
- `OLEAUT32!__imp_VariantClear` at `0x140060d4d`

## string_xrefs

- `0x1400609fe`: `admin\appman\appv\client\publishing\configurations\servertaskrecord.cpp`
- `0x140060a15`: `admin\appman\appv\client\publishing\configurations\servertaskrecord.cpp`
- `0x140060c17`: `admin\appman\appv\client\publishing\configurations\servertaskrecord.cpp`
- `0x140060c2e`: `admin\appman\appv\client\publishing\configurations\servertaskrecord.cpp`
- `0x140060e57`: `admin\appman\appv\client\publishing\configurations\servertaskrecord.cpp`
- `0x140060e6e`: `admin\appman\appv\client\publishing\configurations\servertaskrecord.cpp`
- `0x140060d90`: `Task Folder couldn't create the desired folder.\n HResult: %1%\n Folder: %2%`
- `0x140060b50`: `Task Folder couldn't get the desired folder.\n HResult: %1%\n Folder: %2%`
- `0x1400608f2`: `Task Service couldn't get the desired folder.\n HResult: %1%\n Folder: %2%`
- `0x1400608c2`: `AppV::Client::Publishing::Configurations::ServerTaskRecord::GetTaskFolder`
- `0x140060b1e`: `AppV::Client::Publishing::Configurations::ServerTaskRecord::GetTaskFolder`
- `0x140060d5e`: `AppV::Client::Publishing::Configurations::ServerTaskRecord::GetTaskFolder`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall AppV::Client::Publishing::Configurations::ServerTaskRecord::GetTaskFolder(__int64 **a1, __int64 a2)
{
  __int64 *v3; // rdi
  __int64 v4; // rsi
  BSTR v5; // rax
  OLECHAR *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rdi
  _QWORD *v11; // rcx
  _QWORD *v12; // rbx
  char *v13; // rax
  const char *v14; // rax
  unsigned __int64 FileId; // rax
  __int64 v16; // rbx
  __int64 *v18; // rsi
  __int64 v19; // r15
  OLECHAR *v20; // rdi
  const OLECHAR *v21; // rcx
  OLECHAR *v22; // rbx
  BSTR v23; // rdx
  BSTR v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rbx
  char *v30; // rax
  const char *v31; // rax
  unsigned __int64 v32; // rax
  __int64 *v33; // rsi
  __int64 v34; // r15
  const OLECHAR *v35; // rbx
  __int128 v36; // xmm6
  __int64 v37; // xmm7_8
  const OLECHAR *v38; // rcx
  OLECHAR *v39; // rbx
  BSTR v40; // rdx
  BSTR v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rbx
  char *v47; // rax
  const char *v48; // rax
  unsigned __int64 v49; // rax
  __int64 v50; // [rsp+38h] [rbp-D0h] BYREF
  void *Block; // [rsp+40h] [rbp-C8h] BYREF
  __int64 *v52; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v53; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v54; // [rsp+68h] [rbp-A0h]
  VARIANTARG pvarg; // [rsp+70h] [rbp-98h] BYREF
  __int64 v56; // [rsp+88h] [rbp-80h]
  __int64 v57; // [rsp+90h] [rbp-78h]
  __int128 v58; // [rsp+98h] [rbp-70h] BYREF
  __int64 v59; // [rsp+A8h] [rbp-60h]
  __int64 v60; // [rsp+B0h] [rbp-58h]
  char *v61[4]; // [rsp+B8h] [rbp-50h] BYREF
  int v62; // [rsp+D8h] [rbp-30h]
  _QWORD v63[2]; // [rsp+E0h] [rbp-28h] BYREF
  char *v64[4]; // [rsp+F0h] [rbp-18h] BYREF

  v52 = 0;
  v3 = *a1;
  v4 = **a1;
  v5 = SysAllocString(L"\\");
  v6 = v5;
  Block = v5;
  if ( !v5 )
    goto LABEL_53;
  LODWORD(v50) = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64 **))(v4 + 56))(v3, v5, &v52);
  SysFreeString(v6);
  if ( (int)v50 < 0 )
  {
    std::string::string(v61, "AppV::Client::Publishing::Configurations::ServerTaskRecord::GetTaskFolder");
    v62 = 258;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v7);
    v58 = 0;
    v59 = 0;
    v60 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v58,
      L"Task Service couldn't get the desired folder.\n HResult: %1%\n Folder: %2%",
      0x48u);
    v9 = AppV::Log::fmt(v8, v63, &v58);
    v10 = AppV::LogFormatter::operator%<long>(v9, (__int64)&v50);
    ++*(_DWORD *)(v10 + 8);
    AppV::LogFormatter::build_substitution_list(v10, &Block);
    v11 = Block;
    if ( Block )
    {
      *(_QWORD *)&v53 = v10;
      *((_QWORD *)&v53 + 1) = L"\\";
      std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_c2119dd01f4d093de1625b48a4432ff6_>(
        &pvarg.decVal.Lo32,
        Block,
        0,
        &v53);
      v11 = Block;
    }
    Block = 0;
    if ( v11 )
    {
      do
      {
        v12 = (_QWORD *)*v11;
        operator delete(v11);
        v11 = v12;
      }
      while ( v12 );
    }
    *(_OWORD *)&pvarg.decVal.Lo32 = 0;
    v56 = 0;
    v57 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&pvarg.pcVal, L"Publishing", 0xAu);
    AppV::DecoratedLog::operator()((char *)v61, 1, (int)&pvarg.lVal, v10);
    std::wstring::~wstring(&pvarg.pcVal);
    v63[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v64);
    std::wstring::~wstring((char **)&v58);
    std::string::~string(v61);
    v13 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\servertaskrecord.cpp", 92);
    if ( v13 )
      v14 = v13 + 1;
    else
      v14 = "admin\\appman\\appv\\client\\publishing\\configurations\\servertaskrecord.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v14);
    v16 = (unsigned int)v50 | (FileId << 52) | 0x202700000000LL;
    if ( v52 )
      (*(void (__fastcall **)(__int64 *))(*v52 + 16))(v52);
    return v16;
  }
  v18 = v52;
  v19 = *v52;
  v20 = &AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_folderPath;
  if ( (unsigned __int64)qword_1400B0FE8 <= 7 )
  {
    v21 = &AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_folderPath;
  }
  else
  {
    v21 = *(const OLECHAR **)&AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_folderPath;
    if ( !*(_QWORD *)&AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_folderPath )
    {
      v22 = 0;
      Block = 0;
      v23 = 0;
      goto LABEL_19;
    }
  }
  v24 = SysAllocString(v21);
  v22 = v24;
  Block = v24;
  if ( !v24 )
LABEL_53:
    ATL::AtlThrowImpl(-2147024882);
  v23 = v24;
LABEL_19:
  LODWORD(v50) = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64))(v19 + 72))(v18, v23, a2);
  SysFreeString(v22);
  if ( (int)v50 >= 0 )
    goto LABEL_49;
  if ( (unsigned __int16)v50 != 3 && (unsigned __int16)v50 != 2 )
  {
    std::string::string(v61, "AppV::Client::Publishing::Configurations::ServerTaskRecord::GetTaskFolder");
    v62 = 271;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v25);
    *(_OWORD *)&pvarg.decVal.Lo32 = 0;
    v56 = 0;
    v57 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      &pvarg.pcVal,
      L"Task Folder couldn't get the desired folder.\n HResult: %1%\n Folder: %2%",
      0x47u);
    v27 = AppV::Log::fmt(v26, v63, &pvarg.decVal.Lo32);
    v28 = AppV::LogFormatter::operator%<long>(v27, (__int64)&v50);
    if ( (unsigned __int64)qword_1400B0FE8 > 7 )
      v20 = *(OLECHAR **)&AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_folderPath;
    Block = v20;
    v29 = AppV::LogFormatter::operator%<wchar_t const *>(v28, &Block);
    v58 = 0;
    v59 = 0;
    v60 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v58, L"Publishing", 0xAu);
    AppV::DecoratedLog::operator()((char *)v61, 1, (int)&v58, v29);
    std::wstring::~wstring((char **)&v58);
    v63[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v64);
    std::wstring::~wstring(&pvarg.pcVal);
    std::string::~string(v61);
    v30 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\servertaskrecord.cpp", 92);
    if ( v30 )
      v31 = v30 + 1;
    else
      v31 = "admin\\appman\\appv\\client\\publishing\\configurations\\servertaskrecord.cpp";
    v32 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v31);
    v16 = (unsigned int)v50 | (v32 << 52) | 0x222700000000LL;
    if ( v52 )
      (*(void (__fastcall **)(__int64 *))(*v52 + 16))(v52);
    return v16;
  }
  v33 = v52;
  v34 = *v52;
  v35 = (const OLECHAR *)&AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_folderSDDL;
  if ( (unsigned __int64)qword_1400B1308 > 7 )
    v35 = AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_folderSDDL;
  pvarg.iVal = 0;
  VariantClear((VARIANTARG *)&pvarg.decVal.8);
  pvarg.iVal = 8;
  pvarg.pRecInfo = (IRecordInfo *)SysAllocString(v35);
  if ( !pvarg.pRecInfo && v35 )
  {
    pvarg.iVal = 10;
    *((_DWORD *)&pvarg.decVal + 4) = -2147024882;
    ATL::AtlThrowImpl(-2147024882);
  }
  v36 = *(_OWORD *)&pvarg.decVal.Lo32;
  v37 = v56;
  if ( (unsigned __int64)qword_1400B0FE8 <= 7 )
  {
    v38 = &AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_folderPath;
  }
  else
  {
    v38 = *(const OLECHAR **)&AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_folderPath;
    if ( !*(_QWORD *)&AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_folderPath )
    {
      v39 = 0;
      Block = 0;
      v40 = 0;
      goto LABEL_40;
    }
  }
  v41 = SysAllocString(v38);
  v39 = v41;
  Block = v41;
  if ( !v41 )
    ATL::AtlThrowImpl(-2147024882);
  v40 = v41;
LABEL_40:
  v53 = v36;
  v54 = v37;
  LODWORD(v50) = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int128 *, __int64))(v34 + 88))(v33, v40, &v53, a2);
  SysFreeString(v39);
  VariantClear((VARIANTARG *)&pvarg.decVal.8);
  if ( (int)v50 < 0 )
  {
    std::string::string(v61, "AppV::Client::Publishing::Configurations::ServerTaskRecord::GetTaskFolder");
    v62 = 282;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v42);
    *(_OWORD *)&pvarg.decVal.Lo32 = 0;
    v56 = 0;
    v57 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      &pvarg.pcVal,
      L"Task Folder couldn't create the desired folder.\n HResult: %1%\n Folder: %2%",
      0x4Au);
    v44 = AppV::Log::fmt(v43, v63, &pvarg.decVal.Lo32);
    v45 = AppV::LogFormatter::operator%<long>(v44, (__int64)&v50);
    if ( (unsigned __int64)qword_1400B0FE8 > 7 )
      v20 = *(OLECHAR **)&AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_folderPath;
    Block = v20;
    v46 = AppV::LogFormatter::operator%<wchar_t const *>(v45, &Block);
    v58 = 0;
    v59 = 0;
    v60 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v58, L"Publishing", 0xAu);
    AppV::DecoratedLog::operator()((char *)v61, 1, (int)&v58, v46);
    std::wstring::~wstring((char **)&v58);
    v63[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v64);
    std::wstring::~wstring(&pvarg.pcVal);
    std::string::~string(v61);
    v47 = strrchr("admin\\appman\\appv\\client\\publishing\\configurations\\servertaskrecord.cpp", 92);
    if ( v47 )
      v48 = v47 + 1;
    else
      v48 = "admin\\appman\\appv\\client\\publishing\\configurations\\servertaskrecord.cpp";
    v49 = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v48);
    v16 = (unsigned int)v50 | (v49 << 52) | 0x232700000000LL;
    if ( v52 )
      (*(void (__fastcall **)(__int64 *))(*v52 + 16))(v52);
    return v16;
  }
LABEL_49:
  if ( v52 )
    (*(void (__fastcall **)(__int64 *))(*v52 + 16))(v52);
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x140060830  mov     rax, rsp
0x140060833  mov     [rax+18h], rbx
0x140060837  mov     [rax+20h], rsi
0x14006083b  push    rbp
0x14006083c  push    rdi
0x14006083d  push    r12
0x14006083f  push    r14
0x140060841  push    r15
0x140060843  lea     rbp, [rax-58h]
0x140060847  sub     rsp, 130h
0x14006084e  movaps  xmmword ptr [rax-38h], xmm6
0x140060852  movaps  xmmword ptr [rax-48h], xmm7
0x140060856  mov     rax, cs:__security_cookie
0x14006085d  xor     rax, rsp
0x140060860  mov     [rbp+50h+var_48], rax
0x140060864  mov     r14, rdx
0x140060867  xor     r12d, r12d
0x14006086a  mov     [rsp+150h+var_110], r12
0x14006086f  mov     rdi, [rcx]
0x140060872  mov     rsi, [rdi]
0x140060875  lea     r15, psz; "\\"
0x14006087c  mov     rcx, r15; psz
0x14006087f  call    cs:__imp_SysAllocString
0x140060885  mov     rbx, rax
0x140060888  mov     [rsp+150h+Block], rax
0x14006088d  test    rax, rax
0x140060890  jz      loc_140060EEE
0x140060896  lea     r8, [rsp+150h+var_110]
0x14006089b  mov     rdx, rax
0x14006089e  mov     rcx, rdi
0x1400608a1  mov     rax, [rsi+38h]
0x1400608a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400608aa  mov     dword ptr [rsp+150h+var_120], eax
0x1400608ae  mov     rcx, rbx; bstrString
0x1400608b1  call    cs:__imp_SysFreeString
0x1400608b7  cmp     dword ptr [rsp+150h+var_120], r12d
0x1400608bc  jge     loc_140060A92
0x1400608c2  lea     rdx, aAppvClientPubl_5; "AppV::Client::Publishing::Configuration"...
0x1400608c9  lea     rcx, [rbp+50h+var_A0]
0x1400608cd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400608d2  mov     [rbp+50h+var_80], 102h
0x1400608d9  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x1400608de  xorps   xmm0, xmm0
0x1400608e1  movups  [rbp+50h+var_C0], xmm0
0x1400608e5  mov     [rbp+50h+var_B0], r12
0x1400608e9  mov     [rbp+50h+var_A8], r12
0x1400608ed  lea     r8d, [r12+48h]
0x1400608f2  lea     rdx, aTaskServiceCou; "Task Service couldn't get the desired f"...
0x1400608f9  lea     rcx, [rbp+50h+var_C0]
0x1400608fd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140060902  nop
0x140060903  lea     r8, [rbp+50h+var_C0]
0x140060907  lea     rdx, [rbp+50h+var_78]
0x14006090b  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140060910  nop
0x140060911  lea     rdx, [rsp+150h+var_120]
0x140060916  mov     rcx, rax
0x140060919  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x14006091e  mov     rdi, rax
0x140060921  mov     r8d, [rax+8]
0x140060925  lea     ecx, [r8+1]
0x140060929  mov     [rax+8], ecx
0x14006092c  lea     rdx, [rsp+150h+Block]
0x140060931  mov     rcx, rax
0x140060934  call    ?build_substitution_list@LogFormatter@AppV@@AEAA?AV?$forward_list@VOffsetMarker@LogFormatter@AppV@@V?$allocator@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@H@Z; AppV::LogFormatter::build_substitution_list(int)
0x140060939  nop
0x14006093a  mov     rcx, [rsp+150h+Block]
0x14006093f  test    rcx, rcx
0x140060942  jz      short loc_140060968
0x140060944  mov     r8d, r12d
0x140060947  mov     qword ptr [rsp+150h+var_108+8], rdi
0x14006094c  mov     [rsp+150h+var_F8], r15
0x140060951  lea     r9, [rsp+150h+var_108+8]
0x140060956  mov     rdx, rcx
0x140060959  lea     rcx, [rsp+150h+pvarg+8]
0x14006095e  call    ??$for_each@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@std@@V_lambda_c2119dd01f4d093de1625b48a4432ff6_@@@std@@YA?AV_lambda_c2119dd01f4d093de1625b48a4432ff6_@@V?$_Flist_const_iterator@V?$_Flist_val@U?$_Flist_simple_types@VOffsetMarker@LogFormatter@AppV@@@std@@@std@@@0@0V1@@Z; std::for_each<std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_c2119dd01f4d093de1625b48a4432ff6_>(std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,std::_Flist_const_iterator<std::_Flist_val<std::_Flist_simple_types<AppV::LogFormatter::OffsetMarker>>>,_lambda_c2119dd01f4d093de1625b48a4432ff6_)
0x140060963  mov     rcx, [rsp+150h+Block]; Block
0x140060968  mov     [rsp+150h+Block], r12
0x14006096d  test    rcx, rcx
0x140060970  jz      short loc_140060987
0x140060972  mov     rbx, [rcx]
0x140060975  mov     edx, 20h ; ' '
0x14006097a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14006097f  mov     rcx, rbx
0x140060982  test    rbx, rbx
0x140060985  jnz     short loc_140060972
0x140060987  xorps   xmm0, xmm0
0x14006098a  movups  xmmword ptr [rsp+150h+pvarg+8], xmm0
0x14006098f  mov     [rbp+50h+var_D0], r12
0x140060993  mov     [rbp+50h+var_C8], r12
0x140060997  mov     r8d, 0Ah
0x14006099d  lea     rdx, aPublishing; "Publishing"
0x1400609a4  lea     rcx, [rsp+150h+pvarg+8]
0x1400609a9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400609ae  nop
0x1400609af  mov     r9, rdi
0x1400609b2  lea     r8, [rsp+150h+pvarg+8]
0x1400609b7  mov     edx, 1
0x1400609bc  lea     rcx, [rbp+50h+var_A0]
0x1400609c0  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x1400609c5  nop
0x1400609c6  lea     rcx, [rsp+150h+pvarg+8]
0x1400609cb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400609d0  nop
0x1400609d1  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x1400609d8  mov     [rbp+50h+var_78], rax
0x1400609dc  lea     rcx, [rbp+50h+var_68]
0x1400609e0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400609e5  nop
0x1400609e6  lea     rcx, [rbp+50h+var_C0]
0x1400609ea  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400609ef  nop
0x1400609f0  lea     rcx, [rbp+50h+var_A0]
0x1400609f4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400609f9  mov     edx, 5Ch ; '\'; Ch
0x1400609fe  lea     rcx, aAdminAppmanApp_20; "admin\\appman\\appv\\client\\publishing"...
0x140060a05  call    cs:__imp_strrchr
0x140060a0b  test    rax, rax
0x140060a0e  jz      short loc_140060A15
0x140060a10  inc     rax
0x140060a13  jmp     short loc_140060A1C
0x140060a15  lea     rax, aAdminAppmanApp_20; "admin\\appman\\appv\\client\\publishing"...
0x140060a1c  mov     rdx, rax; char *
0x140060a1f  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140060a26  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140060a2b  mov     rbx, rax
0x140060a2e  shl     rbx, 34h
0x140060a32  mov     ecx, dword ptr [rsp+150h+var_120]
0x140060a36  or      rbx, rcx
0x140060a39  mov     rax, 202700000000h
0x140060a43  or      rbx, rax
0x140060a46  mov     rcx, [rsp+150h+var_110]
0x140060a4b  test    rcx, rcx
0x140060a4e  jz      short loc_140060A5D
0x140060a50  mov     rax, [rcx]
0x140060a53  mov     rax, [rax+10h]
0x140060a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060a5c  nop
0x140060a5d  mov     rax, rbx
0x140060a60  mov     rcx, [rbp+50h+var_48]
0x140060a64  xor     rcx, rsp; StackCookie
0x140060a67  call    __security_check_cookie
0x140060a6c  lea     r11, [rsp+150h+var_20]
0x140060a74  mov     rbx, [r11+40h]
0x140060a78  mov     rsi, [r11+48h]
0x140060a7c  movaps  xmm6, xmmword ptr [r11-10h]
0x140060a81  movaps  xmm7, xmmword ptr [r11-20h]
0x140060a86  mov     rsp, r11
0x140060a89  pop     r15
0x140060a8b  pop     r14
0x140060a8d  pop     r12
0x140060a8f  pop     rdi
0x140060a90  pop     rbp
0x140060a91  retn
0x140060a92  mov     rsi, [rsp+150h+var_110]
0x140060a97  mov     r15, [rsi]
0x140060a9a  lea     rdi, ?sm_folderPath@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_folderPath
0x140060aa1  cmp     cs:qword_1400B0FE8, 7
0x140060aa9  jbe     short loc_140060AC4
0x140060aab  mov     rcx, cs:?sm_folderPath@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_folderPath
0x140060ab2  test    rcx, rcx
0x140060ab5  jnz     short loc_140060AC7
0x140060ab7  mov     rbx, r12
0x140060aba  mov     [rsp+150h+Block], rbx
0x140060abf  mov     rdx, r12
0x140060ac2  jmp     short loc_140060AE1
0x140060ac4  mov     rcx, rdi; psz
0x140060ac7  call    cs:__imp_SysAllocString
0x140060acd  mov     rbx, rax
0x140060ad0  mov     [rsp+150h+Block], rax
0x140060ad5  test    rax, rax
0x140060ad8  jz      loc_140060EEE
0x140060ade  mov     rdx, rax
0x140060ae1  mov     r8, r14
0x140060ae4  mov     rcx, rsi
0x140060ae7  mov     rax, [r15+48h]
0x140060aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060af0  mov     dword ptr [rsp+150h+var_120], eax
0x140060af4  mov     rcx, rbx; bstrString
0x140060af7  call    cs:__imp_SysFreeString
0x140060afd  mov     eax, dword ptr [rsp+150h+var_120]
0x140060b01  test    eax, eax
0x140060b03  jns     loc_140060EBD
0x140060b09  movzx   eax, ax
0x140060b0c  cmp     eax, 3
0x140060b0f  jz      loc_140060C7B
0x140060b15  cmp     eax, 2
0x140060b18  jz      loc_140060C7B
0x140060b1e  lea     rdx, aAppvClientPubl_5; "AppV::Client::Publishing::Configuration"...
0x140060b25  lea     rcx, [rbp+50h+var_A0]
0x140060b29  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140060b2e  mov     [rbp+50h+var_80], 10Fh
0x140060b35  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140060b3a  xorps   xmm0, xmm0
0x140060b3d  movups  xmmword ptr [rsp+150h+pvarg+8], xmm0
0x140060b42  mov     [rbp+50h+var_D0], r12
0x140060b46  mov     [rbp+50h+var_C8], r12
0x140060b4a  mov     r8d, 47h ; 'G'
0x140060b50  lea     rdx, aTaskFolderCoul_1; "Task Folder couldn't get the desired fo"...
0x140060b57  lea     rcx, [rsp+150h+pvarg+8]
0x140060b5c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140060b61  nop
0x140060b62  lea     r8, [rsp+150h+pvarg+8]
0x140060b67  lea     rdx, [rbp+50h+var_78]
0x140060b6b  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140060b70  nop
0x140060b71  lea     rdx, [rsp+150h+var_120]
0x140060b76  mov     rcx, rax
0x140060b79  call    ??$?LJ@LogFormatter@AppV@@QEAAAEAV01@AEAJ@Z; AppV::LogFormatter::operator%<long>(long &)
0x140060b7e  cmp     cs:qword_1400B0FE8, 7
0x140060b86  cmova   rdi, cs:?sm_folderPath@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_folderPath
0x140060b8e  mov     [rsp+150h+Block], rdi
0x140060b93  lea     rdx, [rsp+150h+Block]
0x140060b98  mov     rcx, rax
0x140060b9b  call    ??$?LPEB_W@LogFormatter@AppV@@QEAAAEAV01@AEBQEB_W@Z; AppV::LogFormatter::operator%<wchar_t const *>(wchar_t const * const &)
0x140060ba0  mov     rbx, rax
0x140060ba3  xorps   xmm0, xmm0
0x140060ba6  movups  [rbp+50h+var_C0], xmm0
0x140060baa  mov     [rbp+50h+var_B0], r12
0x140060bae  mov     [rbp+50h+var_A8], r12
0x140060bb2  mov     r8d, 0Ah
0x140060bb8  lea     rdx, aPublishing; "Publishing"
0x140060bbf  lea     rcx, [rbp+50h+var_C0]
0x140060bc3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140060bc8  nop
0x140060bc9  mov     r9, rbx
0x140060bcc  lea     r8, [rbp+50h+var_C0]
0x140060bd0  mov     edx, 1
0x140060bd5  lea     rcx, [rbp+50h+var_A0]
0x140060bd9  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140060bde  nop
0x140060bdf  lea     rcx, [rbp+50h+var_C0]
0x140060be3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140060be8  nop
0x140060be9  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140060bf0  mov     [rbp+50h+var_78], rax
0x140060bf4  lea     rcx, [rbp+50h+var_68]
0x140060bf8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140060bfd  nop
0x140060bfe  lea     rcx, [rsp+150h+pvarg+8]
0x140060c03  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140060c08  nop
0x140060c09  lea     rcx, [rbp+50h+var_A0]
0x140060c0d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140060c12  mov     edx, 5Ch ; '\'; Ch
0x140060c17  lea     rcx, aAdminAppmanApp_20; "admin\\appman\\appv\\client\\publishing"...
0x140060c1e  call    cs:__imp_strrchr
0x140060c24  test    rax, rax
0x140060c27  jz      short loc_140060C2E
0x140060c29  inc     rax
0x140060c2c  jmp     short loc_140060C35
0x140060c2e  lea     rax, aAdminAppmanApp_20; "admin\\appman\\appv\\client\\publishing"...
0x140060c35  mov     rdx, rax; char *
0x140060c38  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140060c3f  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140060c44  mov     rbx, rax
0x140060c47  shl     rbx, 34h
0x140060c4b  mov     ecx, dword ptr [rsp+150h+var_120]
0x140060c4f  or      rbx, rcx
0x140060c52  mov     rax, 222700000000h
0x140060c5c  or      rbx, rax
0x140060c5f  mov     rcx, [rsp+150h+var_110]
0x140060c64  test    rcx, rcx
0x140060c67  jz      short loc_140060C76
0x140060c69  mov     rax, [rcx]
0x140060c6c  mov     rax, [rax+10h]
0x140060c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140060c75  nop
0x140060c76  jmp     loc_140060A5D
0x140060c7b  mov     rsi, [rsp+150h+var_110]
0x140060c80  mov     r15, [rsi]
0x140060c83  lea     rbx, ?sm_folderSDDL@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_folderSDDL
0x140060c8a  cmp     cs:qword_1400B1308, 7
0x140060c92  cmova   rbx, cs:?sm_folderSDDL@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_folderSDDL
0x140060c9a  mov     word ptr [rsp+150h+pvarg+8], r12w
0x140060ca0  lea     rcx, [rsp+150h+pvarg+8]; pvarg
0x140060ca5  call    cs:__imp_VariantClear
0x140060cab  mov     eax, 8
0x140060cb0  mov     word ptr [rsp+150h+pvarg+8], ax
0x140060cb5  mov     rcx, rbx; psz
0x140060cb8  call    cs:__imp_SysAllocString
0x140060cbe  mov     qword ptr [rsp+150h+pvarg+10h], rax
0x140060cc3  test    rax, rax
0x140060cc6  jnz     short loc_140060CD1
0x140060cc8  test    rbx, rbx
0x140060ccb  jnz     loc_140060EF9
0x140060cd1  movups  xmm6, xmmword ptr [rsp+150h+pvarg+8]
0x140060cd6  movsd   xmm7, [rbp+50h+var_D0]
0x140060cdb  cmp     cs:qword_1400B0FE8, 7
0x140060ce3  jbe     short loc_140060CFE
0x140060ce5  mov     rcx, cs:?sm_folderPath@ServerTaskRecord@Configurations@Publishing@Client@AppV@@0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const AppV::Client::Publishing::Configurations::ServerTaskRecord::sm_folderPath
0x140060cec  test    rcx, rcx
0x140060cef  jnz     short loc_140060D01
0x140060cf1  mov     rbx, r12
0x140060cf4  mov     [rsp+150h+Block], rbx
0x140060cf9  mov     rdx, r12
0x140060cfc  jmp     short loc_140060D1B
0x140060cfe  mov     rcx, rdi; psz
0x140060d01  call    cs:__imp_SysAllocString
0x140060d07  mov     rbx, rax
  ... truncated ...
```
