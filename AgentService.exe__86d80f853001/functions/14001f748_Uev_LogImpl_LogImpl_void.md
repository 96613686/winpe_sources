# Uev::LogImpl::LogImpl(void)

- ea: `0x14001f748`
- end: `0x14001ff8a`
- name: `??0LogImpl@Uev@@QEAA@XZ`
- size: `2114`
- prototype: `Uev::LogImpl *__fastcall(Uev::LogImpl *this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140023800`

## callees

- `0x140003e50`
- `0x140003e74`
- `0x140004d40`
- `0x140005b30`
- `0x140006ce0`
- `0x14000adb4`
- `0x14000ba60`
- `0x14000e924`
- `0x140011ab4`
- `0x14001358c`
- `0x140018d78`
- `0x14001f1c4`
- `0x14001f324`
- `0x14001f594`
- `0x14001f748`
- `0x1400202b0`
- `0x1400203ac`
- `0x140020568`
- `0x140020cd4`
- `0x140020f6c`
- `0x14009b010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14001fdb9`
- `KERNEL32!GetCurrentProcessId` at `0x14001fdb9`
- `KERNEL32!GetFileAttributesW` at `0x14001fcb9`
- `KERNEL32!GetFileAttributesW` at `0x14001fcb9`
- `msvcp_win!??1?$basic_ostream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x14001ff18`
- `msvcp_win!??1?$basic_ostream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x14001ff18`
- `msvcp_win!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x14001ff26`
- `msvcp_win!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x14001ff26`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x14001fdc4`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x14001fdc4`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x14001fec0`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x14001fec0`

## string_xrefs

- `0x14001f9a2`: `AppAgent`
- `0x14001fa0e`: `AppAgentCommon`
- `0x14001f9d8`: `AgentService`
- `0x14001fa44`: `UevCommon`
- `0x14001fab0`: `Configuration`
- `0x14001fbf4`: `TemplateService`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
Uev::LogImpl *__fastcall Uev::LogImpl::LogImpl(Uev::LogImpl *this)
{
  Uev::LogImpl *v1; // rsi
  _QWORD *v2; // rax
  _QWORD *v3; // rax
  __int128 *v4; // rdi
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  DWORD FileAttributesW; // eax
  char v9; // bl
  __int64 v10; // rbx
  __int128 *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rbx
  DWORD CurrentProcessId; // eax
  __int64 v15; // rbx
  const wchar_t **v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rbx
  void (__fastcall ***v19)(_QWORD, __int64); // rcx
  Uev::LogImpl *v21; // rdi
  __int64 v22; // rbx
  int v23; // [rsp+30h] [rbp-1F8h] BYREF
  __int64 v24; // [rsp+38h] [rbp-1F0h] BYREF
  Uev::LogImpl *v25; // [rsp+40h] [rbp-1E8h]
  int v26; // [rsp+4Ch] [rbp-1DCh]
  __int64 v27; // [rsp+50h] [rbp-1D8h] BYREF
  _BYTE v28[8]; // [rsp+58h] [rbp-1D0h] BYREF
  _BYTE v29[120]; // [rsp+60h] [rbp-1C8h] BYREF
  _BYTE v30[104]; // [rsp+D8h] [rbp-150h] BYREF
  const wchar_t *v31; // [rsp+140h] [rbp-E8h] BYREF
  __int64 *v32; // [rsp+148h] [rbp-E0h]
  unsigned __int64 v33; // [rsp+158h] [rbp-D0h]
  __int128 v34; // [rsp+160h] [rbp-C8h] BYREF
  __int128 v35; // [rsp+170h] [rbp-B8h]
  __int128 v36; // [rsp+180h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+190h] [rbp-98h]
  __int64 v38; // [rsp+198h] [rbp-90h]
  __int128 v39; // [rsp+1A0h] [rbp-88h] BYREF
  __int128 v40; // [rsp+1B0h] [rbp-78h]
  __int128 v41; // [rsp+1C0h] [rbp-68h] BYREF
  __int64 v42; // [rsp+1D0h] [rbp-58h]
  __int64 v43; // [rsp+1D8h] [rbp-50h]
  _BYTE v44[32]; // [rsp+1E0h] [rbp-48h] BYREF

  v1 = this;
  v25 = this;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  v2 = operator new(0x48u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  *(_QWORD *)v1 = v2;
  *((_QWORD *)v1 + 2) = 0;
  *((_QWORD *)v1 + 3) = 0;
  v3 = operator new(0x48u);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  *((_QWORD *)v1 + 2) = v3;
  v4 = (__int128 *)((char *)v1 + 40);
  *(_OWORD *)((char *)v1 + 40) = 0;
  *((_QWORD *)v1 + 7) = 0;
  *((_QWORD *)v1 + 8) = 7;
  *((_WORD *)v1 + 20) = 0;
  *((_QWORD *)v1 + 9) = 0;
  v24 = 0;
  v23 = 0;
  v5 = Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance();
  Uev::Setting<unsigned long>::Get(v5 + 13488, &v23, &v24);
  *((_DWORD *)v1 + 8) = v23;
  LODWORD(v31) = 0;
  v32 = (__int64 *)L"<unknown log level>";
  std::map<enum Uev::UEV_LOG_LEVEL,std::wstring const>::insert<std::pair<enum Uev::UEV_LOG_LEVEL,wchar_t const *>,0>(
    v1,
    &v34,
    &v31);
  LODWORD(v31) = 1;
  v32 = (__int64 *)L"ERROR";
  std::map<enum Uev::UEV_LOG_LEVEL,std::wstring const>::insert<std::pair<enum Uev::UEV_LOG_LEVEL,wchar_t const *>,0>(
    v1,
    &v34,
    &v31);
  LODWORD(v31) = 2;
  v32 = (__int64 *)L"WARNING";
  std::map<enum Uev::UEV_LOG_LEVEL,std::wstring const>::insert<std::pair<enum Uev::UEV_LOG_LEVEL,wchar_t const *>,0>(
    v1,
    &v34,
    &v31);
  LODWORD(v31) = 4;
  v32 = (__int64 *)L"INFO";
  std::map<enum Uev::UEV_LOG_LEVEL,std::wstring const>::insert<std::pair<enum Uev::UEV_LOG_LEVEL,wchar_t const *>,0>(
    v1,
    &v34,
    &v31);
  LODWORD(v31) = 8;
  v32 = (__int64 *)L"DEBUG";
  std::map<enum Uev::UEV_LOG_LEVEL,std::wstring const>::insert<std::pair<enum Uev::UEV_LOG_LEVEL,wchar_t const *>,0>(
    v1,
    &v34,
    &v31);
  LODWORD(v31) = 32;
  v32 = (__int64 *)L"SCOPE";
  std::map<enum Uev::UEV_LOG_LEVEL,std::wstring const>::insert<std::pair<enum Uev::UEV_LOG_LEVEL,wchar_t const *>,0>(
    v1,
    &v34,
    &v31);
  LODWORD(v31) = 16;
  v32 = (__int64 *)L"PERFORMANCE";
  std::map<enum Uev::UEV_LOG_LEVEL,std::wstring const>::insert<std::pair<enum Uev::UEV_LOG_LEVEL,wchar_t const *>,0>(
    v1,
    &v34,
    &v31);
  v31 = L"Default";
  v32 = LogDebugMessage;
  std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(
    (__int64 *)v1 + 2,
    (__int64)&v34,
    (__int64)&v31);
  v31 = L"AppAgent";
  v32 = LogDebugAppAgentMessage;
  std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(
    (__int64 *)v1 + 2,
    (__int64)&v34,
    (__int64)&v31);
  v31 = L"AgentService";
  v32 = LogDebugAgentServiceMessage;
  std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(
    (__int64 *)v1 + 2,
    (__int64)&v34,
    (__int64)&v31);
  v31 = L"AppAgentCommon";
  v32 = LogDebugAppAgentCommonMessage;
  std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(
    (__int64 *)v1 + 2,
    (__int64)&v34,
    (__int64)&v31);
  v31 = L"UevCommon";
  v32 = LogDebugUevCommonMessage;
  std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(
    (__int64 *)v1 + 2,
    (__int64)&v34,
    (__int64)&v31);
  v31 = L"ChangeManager";
  v32 = LogDebugChangeManagerMessage;
  std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(
    (__int64 *)v1 + 2,
    (__int64)&v34,
    (__int64)&v31);
  v31 = L"Configuration";
  v32 = LogDebugConfigurationMessage;
  std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(
    (__int64 *)v1 + 2,
    (__int64)&v34,
    (__int64)&v31);
  v31 = L"CscChangeManager";
  v32 = LogDebugCscChangeManagerMessage;
  std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(
    (__int64 *)v1 + 2,
    (__int64)&v34,
    (__int64)&v31);
  v31 = L"CscTool";
  v32 = LogDebugCscToolMessage;
  std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(
    (__int64 *)v1 + 2,
    (__int64)&v34,
    (__int64)&v31);
  v31 = L"LocalStore";
  v32 = LogDebugLocalStoreMessage;
  std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(
    (__int64 *)v1 + 2,
    (__int64)&v34,
    (__int64)&v31);
  v31 = L"Orchestrator";
  v32 = LogDebugOrchestratorMessage;
  std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(
    (__int64 *)v1 + 2,
    (__int64)&v34,
    (__int64)&v31);
  v31 = L"Packager";
  v32 = LogDebugPackagerMessage;
  std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(
    (__int64 *)v1 + 2,
    (__int64)&v34,
    (__int64)&v31);
  v31 = L"TemplateService";
  v32 = LogDebugTemplateServiceMessage;
  std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(
    (__int64 *)v1 + 2,
    (__int64)&v34,
    (__int64)&v31);
  v41 = 0;
  v42 = 0;
  v43 = 7;
  LOWORD(v41) = 0;
  v6 = Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance();
  if ( (unsigned __int8)Uev::Setting<std::wstring>::Get(v6 + 16224, &v41, &v24) && v42 )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      std::wstring::wstring((__int64)&v36, (__int64)&v41);
      v7 = boost::filesystem::path::parent_path(&v36, &v34);
      if ( *(_QWORD *)(v7 + 24) > 7u )
        v7 = *(_QWORD *)v7;
      FileAttributesW = GetFileAttributesW((LPCWSTR)v7);
      if ( FileAttributesW == -1 || (v9 = 1, (FileAttributesW & 0x10) == 0) )
        v9 = 0;
      std::wstring::_Tidy_deallocate(&v34);
      if ( v9 )
      {
        boost::filesystem::path::stem_v3(&v36, &v31);
        v10 = boost::filesystem::path::parent_path(&v36, v44);
        boost::filesystem::path::append_v3((boost::filesystem::path *)v10, (const struct boost::filesystem::path *)&v31);
        v34 = 0;
        v35 = 0u;
        v34 = *(_OWORD *)v10;
        v35 = *(_OWORD *)(v10 + 16);
        *(_QWORD *)(v10 + 16) = 0;
        *(_QWORD *)(v10 + 24) = 7;
        *(_WORD *)v10 = 0;
        std::wstring::_Tidy_deallocate(v44);
        std::wstring::_Tidy_deallocate(&v31);
        std::wostringstream::wostringstream(&v27);
        v11 = &v34;
        if ( *((_QWORD *)&v35 + 1) > 7u )
          v11 = (__int128 *)v34;
        v12 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(&v27, v11);
        v13 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v12, L"_");
        CurrentProcessId = GetCurrentProcessId();
        v15 = std::wostream::operator<<(v13, CurrentProcessId);
        boost::filesystem::path::extension_v3(&v36, &v31);
        v16 = &v31;
        if ( v33 > 7 )
          v16 = (const wchar_t **)v31;
        std::operator<<<wchar_t,std::char_traits<wchar_t>>(v15, v16);
        std::wstring::_Tidy_deallocate(&v31);
        std::wstringbuf::str(v28, &v39);
        if ( v4 != &v39 )
        {
          std::wstring::_Tidy_deallocate((char *)v1 + 40);
          *v4 = v39;
          *(_OWORD *)((char *)v1 + 56) = v40;
          *(_QWORD *)&v40 = 0;
          *((_QWORD *)&v40 + 1) = 7;
          LOWORD(v39) = 0;
        }
        std::wstring::_Tidy_deallocate(&v39);
        v31 = (const wchar_t *)operator new(0x108u);
        v17 = std::ofstream::ofstream((__int64)v31, (__int64)v1 + 40);
        v18 = *((_QWORD *)v1 + 9);
        *((_QWORD *)v1 + 9) = v17;
        if ( v18 )
        {
          if ( !std::filebuf::close(v18 + 8) )
            std::ios::setstate(v18 + *(int *)(*(_QWORD *)v18 + 4LL), 2);
          v19 = (void (__fastcall ***)(_QWORD, __int64))(v18 + *(int *)(*(_QWORD *)v18 + 4LL));
          (**v19)(v19, 1);
        }
        *(_QWORD *)&v28[*(int *)(v27 + 4) - 8] = &std::wostringstream::`vftable';
        *(int *)((char *)&v26 + *(int *)(v27 + 4)) = *(_DWORD *)(v27 + 4) - 136;
        std::wstringbuf::~wstringbuf(v28);
        std::wostream::~wostream<wchar_t,std::char_traits<wchar_t>>(v29);
        std::wios::~wios<wchar_t,std::char_traits<wchar_t>>(v30);
        std::wstring::_Tidy_deallocate(&v34);
      }
      std::wstring::_Tidy_deallocate(&v36);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &boost::filesystem::filesystem_error `RTTI Type Descriptor', 0) )
      {
        v21 = v25;
        v22 = *((_QWORD *)v25 + 9);
        *((_QWORD *)v25 + 9) = 0;
        if ( v22 )
        {
          if ( !std::filebuf::close(v22 + 8) )
            std::ios::setstate(v22 + *(int *)(*(_QWORD *)v22 + 4LL), 2);
          (**(void (__fastcall ***)(__int64, __int64))(*(int *)(*(_QWORD *)v22 + 4LL) + v22))(
            v22 + *(int *)(*(_QWORD *)v22 + 4LL),
            1);
        }
        v36 = 0;
        v37 = 0;
        v38 = 0;
        std::wstring::_Construct<1,wchar_t *>(&v36, L"Common", 6u);
        Uev::LogImpl::Write(
          v21,
          8,
          &v36,
          L"LogImpl::LogImpl() - An error occurred while opening the local debug log file. Debug logging to the local file"
           " will be disabled.");
        std::wstring::_Tidy_deallocate(&v36);
        v1 = v25;
        __eh34_try_continuation(0, &boost::filesystem::filesystem_error `RTTI Type Descriptor', &loc_14001FF4B);
      }
    }
  }
  std::wstring::_Tidy_deallocate(&v41);
  return v1;
}

```

## disassembly

```asm
0x14001f748  mov     [rsp+arg_8], rbx
0x14001f74d  mov     [rsp+arg_10], rsi
0x14001f752  push    rdi
0x14001f753  push    r14
0x14001f755  push    r15
0x14001f757  sub     rsp, 210h
0x14001f75e  mov     rax, cs:__security_cookie
0x14001f765  xor     rax, rsp
0x14001f768  mov     [rsp+228h+var_28], rax
0x14001f770  mov     rsi, rcx
0x14001f773  mov     [rsp+228h+var_1E8], rcx
0x14001f778  xor     r14d, r14d
0x14001f77b  mov     [rcx], r14
0x14001f77e  mov     [rcx+8], r14
0x14001f782  lea     edi, [r14+48h]
0x14001f786  mov     ecx, edi; Size
0x14001f788  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001f78d  mov     [rax], rax
0x14001f790  mov     [rax+8], rax
0x14001f794  mov     [rax+10h], rax
0x14001f798  mov     word ptr [rax+18h], 101h
0x14001f79e  mov     [rsi], rax
0x14001f7a1  lea     rbx, [rsi+10h]
0x14001f7a5  mov     [rbx], r14
0x14001f7a8  mov     [rbx+8], r14
0x14001f7ac  mov     ecx, edi; Size
0x14001f7ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001f7b3  mov     [rax], rax
0x14001f7b6  mov     [rax+8], rax
0x14001f7ba  mov     [rax+10h], rax
0x14001f7be  mov     word ptr [rax+18h], 101h
0x14001f7c4  mov     [rbx], rax
0x14001f7c7  lea     rdi, [rsi+28h]
0x14001f7cb  xorps   xmm0, xmm0
0x14001f7ce  movups  xmmword ptr [rdi], xmm0
0x14001f7d1  mov     [rdi+10h], r14
0x14001f7d5  lea     r15d, [r14+7]
0x14001f7d9  mov     [rdi+18h], r15
0x14001f7dd  mov     [rdi], r14w
0x14001f7e1  mov     [rsi+48h], r14
0x14001f7e5  mov     [rsp+228h+var_1F0], r14
0x14001f7ea  mov     [rsp+228h+var_1F8], r14d
0x14001f7ef  call    ?Instance@?$Singleton@VConfiguration@Uev@@V12@@Uev@@SAPEAVConfiguration@2@XZ; Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance(void)
0x14001f7f4  lea     rcx, [rax+34B0h]
0x14001f7fb  lea     r8, [rsp+228h+var_1F0]
0x14001f800  lea     rdx, [rsp+228h+var_1F8]
0x14001f805  call    ?Get@?$Setting@K@Uev@@QEBA_NAEAKAEAUSettingInfo@2@@Z; Uev::Setting<ulong>::Get(ulong &,Uev::SettingInfo &)
0x14001f80a  mov     eax, [rsp+228h+var_1F8]
0x14001f80e  mov     [rsi+20h], eax
0x14001f811  mov     dword ptr [rsp+228h+var_E8], r14d
0x14001f819  lea     rax, aUnknownLogLeve; "<unknown log level>"
0x14001f820  mov     [rsp+228h+var_E0], rax
0x14001f828  lea     r8, [rsp+228h+var_E8]
0x14001f830  lea     rdx, [rsp+228h+var_C8]
0x14001f838  mov     rcx, rsi
0x14001f83b  call    ??$insert@U?$pair@W4UEV_LOG_LEVEL@Uev@@PEB_W@std@@$0A@@?$map@W4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@W4UEV_LOG_LEVEL@Uev@@@4@V?$allocator@U?$pair@$$CBW4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@4@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4UEV_LOG_LEVEL@Uev@@PEB_W@1@@Z; std::map<Uev::UEV_LOG_LEVEL,std::wstring const>::insert<std::pair<Uev::UEV_LOG_LEVEL,wchar_t const *>,0>(std::pair<Uev::UEV_LOG_LEVEL,wchar_t const *> &&)
0x14001f840  mov     dword ptr [rsp+228h+var_E8], 1
0x14001f84b  lea     rax, aError_0; "ERROR"
0x14001f852  mov     [rsp+228h+var_E0], rax
0x14001f85a  lea     r8, [rsp+228h+var_E8]
0x14001f862  lea     rdx, [rsp+228h+var_C8]
0x14001f86a  mov     rcx, rsi
0x14001f86d  call    ??$insert@U?$pair@W4UEV_LOG_LEVEL@Uev@@PEB_W@std@@$0A@@?$map@W4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@W4UEV_LOG_LEVEL@Uev@@@4@V?$allocator@U?$pair@$$CBW4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@4@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4UEV_LOG_LEVEL@Uev@@PEB_W@1@@Z; std::map<Uev::UEV_LOG_LEVEL,std::wstring const>::insert<std::pair<Uev::UEV_LOG_LEVEL,wchar_t const *>,0>(std::pair<Uev::UEV_LOG_LEVEL,wchar_t const *> &&)
0x14001f872  mov     dword ptr [rsp+228h+var_E8], 2
0x14001f87d  lea     rax, aWarning; "WARNING"
0x14001f884  mov     [rsp+228h+var_E0], rax
0x14001f88c  lea     r8, [rsp+228h+var_E8]
0x14001f894  lea     rdx, [rsp+228h+var_C8]
0x14001f89c  mov     rcx, rsi
0x14001f89f  call    ??$insert@U?$pair@W4UEV_LOG_LEVEL@Uev@@PEB_W@std@@$0A@@?$map@W4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@W4UEV_LOG_LEVEL@Uev@@@4@V?$allocator@U?$pair@$$CBW4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@4@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4UEV_LOG_LEVEL@Uev@@PEB_W@1@@Z; std::map<Uev::UEV_LOG_LEVEL,std::wstring const>::insert<std::pair<Uev::UEV_LOG_LEVEL,wchar_t const *>,0>(std::pair<Uev::UEV_LOG_LEVEL,wchar_t const *> &&)
0x14001f8a4  mov     dword ptr [rsp+228h+var_E8], 4
0x14001f8af  lea     rax, aInfo; "INFO"
0x14001f8b6  mov     [rsp+228h+var_E0], rax
0x14001f8be  lea     r8, [rsp+228h+var_E8]
0x14001f8c6  lea     rdx, [rsp+228h+var_C8]
0x14001f8ce  mov     rcx, rsi
0x14001f8d1  call    ??$insert@U?$pair@W4UEV_LOG_LEVEL@Uev@@PEB_W@std@@$0A@@?$map@W4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@W4UEV_LOG_LEVEL@Uev@@@4@V?$allocator@U?$pair@$$CBW4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@4@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4UEV_LOG_LEVEL@Uev@@PEB_W@1@@Z; std::map<Uev::UEV_LOG_LEVEL,std::wstring const>::insert<std::pair<Uev::UEV_LOG_LEVEL,wchar_t const *>,0>(std::pair<Uev::UEV_LOG_LEVEL,wchar_t const *> &&)
0x14001f8d6  mov     dword ptr [rsp+228h+var_E8], 8
0x14001f8e1  lea     rax, aDebug; "DEBUG"
0x14001f8e8  mov     [rsp+228h+var_E0], rax
0x14001f8f0  lea     r8, [rsp+228h+var_E8]
0x14001f8f8  lea     rdx, [rsp+228h+var_C8]
0x14001f900  mov     rcx, rsi
0x14001f903  call    ??$insert@U?$pair@W4UEV_LOG_LEVEL@Uev@@PEB_W@std@@$0A@@?$map@W4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@W4UEV_LOG_LEVEL@Uev@@@4@V?$allocator@U?$pair@$$CBW4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@4@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4UEV_LOG_LEVEL@Uev@@PEB_W@1@@Z; std::map<Uev::UEV_LOG_LEVEL,std::wstring const>::insert<std::pair<Uev::UEV_LOG_LEVEL,wchar_t const *>,0>(std::pair<Uev::UEV_LOG_LEVEL,wchar_t const *> &&)
0x14001f908  mov     dword ptr [rsp+228h+var_E8], 20h ; ' '
0x14001f913  lea     rax, aScope; "SCOPE"
0x14001f91a  mov     [rsp+228h+var_E0], rax
0x14001f922  lea     r8, [rsp+228h+var_E8]
0x14001f92a  lea     rdx, [rsp+228h+var_C8]
0x14001f932  mov     rcx, rsi
0x14001f935  call    ??$insert@U?$pair@W4UEV_LOG_LEVEL@Uev@@PEB_W@std@@$0A@@?$map@W4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@W4UEV_LOG_LEVEL@Uev@@@4@V?$allocator@U?$pair@$$CBW4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@4@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4UEV_LOG_LEVEL@Uev@@PEB_W@1@@Z; std::map<Uev::UEV_LOG_LEVEL,std::wstring const>::insert<std::pair<Uev::UEV_LOG_LEVEL,wchar_t const *>,0>(std::pair<Uev::UEV_LOG_LEVEL,wchar_t const *> &&)
0x14001f93a  mov     dword ptr [rsp+228h+var_E8], 10h
0x14001f945  lea     rax, aPerformance; "PERFORMANCE"
0x14001f94c  mov     [rsp+228h+var_E0], rax
0x14001f954  lea     r8, [rsp+228h+var_E8]
0x14001f95c  lea     rdx, [rsp+228h+var_C8]
0x14001f964  mov     rcx, rsi
0x14001f967  call    ??$insert@U?$pair@W4UEV_LOG_LEVEL@Uev@@PEB_W@std@@$0A@@?$map@W4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@W4UEV_LOG_LEVEL@Uev@@@4@V?$allocator@U?$pair@$$CBW4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@4@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4UEV_LOG_LEVEL@Uev@@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4UEV_LOG_LEVEL@Uev@@PEB_W@1@@Z; std::map<Uev::UEV_LOG_LEVEL,std::wstring const>::insert<std::pair<Uev::UEV_LOG_LEVEL,wchar_t const *>,0>(std::pair<Uev::UEV_LOG_LEVEL,wchar_t const *> &&)
0x14001f96c  lea     rax, aDefault; "Default"
0x14001f973  mov     [rsp+228h+var_E8], rax
0x14001f97b  lea     rax, LogDebugMessage
0x14001f982  mov     [rsp+228h+var_E0], rax
0x14001f98a  lea     r8, [rsp+228h+var_E8]
0x14001f992  lea     rdx, [rsp+228h+var_C8]
0x14001f99a  mov     rcx, rbx
0x14001f99d  call    ??$insert@U?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@1@@Z; std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *> &&)
0x14001f9a2  lea     rax, aAppagent; "AppAgent"
0x14001f9a9  mov     [rsp+228h+var_E8], rax
0x14001f9b1  lea     rax, LogDebugAppAgentMessage
0x14001f9b8  mov     [rsp+228h+var_E0], rax
0x14001f9c0  lea     r8, [rsp+228h+var_E8]
0x14001f9c8  lea     rdx, [rsp+228h+var_C8]
0x14001f9d0  mov     rcx, rbx
0x14001f9d3  call    ??$insert@U?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@1@@Z; std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *> &&)
0x14001f9d8  lea     rax, aAgentservice; "AgentService"
0x14001f9df  mov     [rsp+228h+var_E8], rax
0x14001f9e7  lea     rax, LogDebugAgentServiceMessage
0x14001f9ee  mov     [rsp+228h+var_E0], rax
0x14001f9f6  lea     r8, [rsp+228h+var_E8]
0x14001f9fe  lea     rdx, [rsp+228h+var_C8]
0x14001fa06  mov     rcx, rbx
0x14001fa09  call    ??$insert@U?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@1@@Z; std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *> &&)
0x14001fa0e  lea     rax, aAppagentcommon; "AppAgentCommon"
0x14001fa15  mov     [rsp+228h+var_E8], rax
0x14001fa1d  lea     rax, LogDebugAppAgentCommonMessage
0x14001fa24  mov     [rsp+228h+var_E0], rax
0x14001fa2c  lea     r8, [rsp+228h+var_E8]
0x14001fa34  lea     rdx, [rsp+228h+var_C8]
0x14001fa3c  mov     rcx, rbx
0x14001fa3f  call    ??$insert@U?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@1@@Z; std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *> &&)
0x14001fa44  lea     rax, aUevcommon; "UevCommon"
0x14001fa4b  mov     [rsp+228h+var_E8], rax
0x14001fa53  lea     rax, LogDebugUevCommonMessage
0x14001fa5a  mov     [rsp+228h+var_E0], rax
0x14001fa62  lea     r8, [rsp+228h+var_E8]
0x14001fa6a  lea     rdx, [rsp+228h+var_C8]
0x14001fa72  mov     rcx, rbx
0x14001fa75  call    ??$insert@U?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@1@@Z; std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *> &&)
0x14001fa7a  lea     rax, aChangemanager; "ChangeManager"
0x14001fa81  mov     [rsp+228h+var_E8], rax
0x14001fa89  lea     rax, LogDebugChangeManagerMessage
0x14001fa90  mov     [rsp+228h+var_E0], rax
0x14001fa98  lea     r8, [rsp+228h+var_E8]
0x14001faa0  lea     rdx, [rsp+228h+var_C8]
0x14001faa8  mov     rcx, rbx
0x14001faab  call    ??$insert@U?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@1@@Z; std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *> &&)
0x14001fab0  lea     rax, aConfiguration; "Configuration"
0x14001fab7  mov     [rsp+228h+var_E8], rax
0x14001fabf  lea     rax, LogDebugConfigurationMessage
0x14001fac6  mov     [rsp+228h+var_E0], rax
0x14001face  lea     r8, [rsp+228h+var_E8]
0x14001fad6  lea     rdx, [rsp+228h+var_C8]
0x14001fade  mov     rcx, rbx
0x14001fae1  call    ??$insert@U?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@1@@Z; std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *> &&)
0x14001fae6  lea     rax, aCscchangemanag; "CscChangeManager"
0x14001faed  mov     [rsp+228h+var_E8], rax
0x14001faf5  lea     rax, LogDebugCscChangeManagerMessage
0x14001fafc  mov     [rsp+228h+var_E0], rax
0x14001fb04  lea     r8, [rsp+228h+var_E8]
0x14001fb0c  lea     rdx, [rsp+228h+var_C8]
0x14001fb14  mov     rcx, rbx
0x14001fb17  call    ??$insert@U?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@1@@Z; std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *> &&)
0x14001fb1c  lea     rax, aCsctool; "CscTool"
0x14001fb23  mov     [rsp+228h+var_E8], rax
0x14001fb2b  lea     rax, LogDebugCscToolMessage
0x14001fb32  mov     [rsp+228h+var_E0], rax
0x14001fb3a  lea     r8, [rsp+228h+var_E8]
0x14001fb42  lea     rdx, [rsp+228h+var_C8]
0x14001fb4a  mov     rcx, rbx
0x14001fb4d  call    ??$insert@U?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@1@@Z; std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *> &&)
0x14001fb52  lea     rax, aLocalstore; "LocalStore"
0x14001fb59  mov     [rsp+228h+var_E8], rax
0x14001fb61  lea     rax, LogDebugLocalStoreMessage
0x14001fb68  mov     [rsp+228h+var_E0], rax
0x14001fb70  lea     r8, [rsp+228h+var_E8]
0x14001fb78  lea     rdx, [rsp+228h+var_C8]
0x14001fb80  mov     rcx, rbx
0x14001fb83  call    ??$insert@U?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@1@@Z; std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *> &&)
0x14001fb88  lea     rax, aOrchestrator; "Orchestrator"
0x14001fb8f  mov     [rsp+228h+var_E8], rax
0x14001fb97  lea     rax, LogDebugOrchestratorMessage
0x14001fb9e  mov     [rsp+228h+var_E0], rax
0x14001fba6  lea     r8, [rsp+228h+var_E8]
0x14001fbae  lea     rdx, [rsp+228h+var_C8]
0x14001fbb6  mov     rcx, rbx
0x14001fbb9  call    ??$insert@U?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@1@@Z; std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *> &&)
0x14001fbbe  lea     rax, aPackager; "Packager"
0x14001fbc5  mov     [rsp+228h+var_E8], rax
0x14001fbcd  lea     rax, LogDebugPackagerMessage
0x14001fbd4  mov     [rsp+228h+var_E0], rax
0x14001fbdc  lea     r8, [rsp+228h+var_E8]
0x14001fbe4  lea     rdx, [rsp+228h+var_C8]
0x14001fbec  mov     rcx, rbx
0x14001fbef  call    ??$insert@U?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@1@@Z; std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *> &&)
0x14001fbf4  lea     rax, aTemplateservic; "TemplateService"
0x14001fbfb  mov     [rsp+228h+var_E8], rax
0x14001fc03  lea     rax, LogDebugTemplateServiceMessage
0x14001fc0a  mov     [rsp+228h+var_E0], rax
0x14001fc12  lea     r8, [rsp+228h+var_E8]
0x14001fc1a  lea     rdx, [rsp+228h+var_C8]
0x14001fc22  mov     rcx, rbx
0x14001fc25  call    ??$insert@U?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@std@@$0A@@?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBU_EVENT_DESCRIPTOR@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@PEB_WPEBU_EVENT_DESCRIPTOR@@@1@@Z; std::map<std::wstring,_EVENT_DESCRIPTOR const *>::insert<std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *>,0>(std::pair<wchar_t const *,_EVENT_DESCRIPTOR const *> &&)
0x14001fc2a  xorps   xmm0, xmm0
0x14001fc2d  movups  [rsp+228h+var_68], xmm0
0x14001fc35  mov     [rsp+228h+var_58], r14
0x14001fc3d  mov     [rsp+228h+var_50], r15
0x14001fc45  mov     word ptr [rsp+228h+var_68], r14w
0x14001fc4e  call    ?Instance@?$Singleton@VConfiguration@Uev@@V12@@Uev@@SAPEAVConfiguration@2@XZ; Uev::Singleton<Uev::Configuration,Uev::Configuration>::Instance(void)
0x14001fc53  lea     rcx, [rax+3F60h]
0x14001fc5a  lea     r8, [rsp+228h+var_1F0]
0x14001fc5f  lea     rdx, [rsp+228h+var_68]
0x14001fc67  call    ?Get@?$Setting@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Uev@@QEBA_NAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAUSettingInfo@2@@Z; Uev::Setting<std::wstring>::Get(std::wstring &,Uev::SettingInfo &)
0x14001fc6c  test    al, al
0x14001fc6e  jz      loc_14001FF50
0x14001fc74  cmp     [rsp+228h+var_58], r14
0x14001fc7c  jz      loc_14001FF50
0x14001fc82  lea     rdx, [rsp+228h+var_68]
0x14001fc8a  lea     rcx, [rsp+228h+var_A8]
0x14001fc92  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14001fc97  nop
0x14001fc98  lea     rdx, [rsp+228h+var_C8]
0x14001fca0  lea     rcx, [rsp+228h+var_A8]
0x14001fca8  call    ?parent_path@path@filesystem@boost@@QEBA?AV123@XZ; boost::filesystem::path::parent_path(void)
0x14001fcad  cmp     [rax+18h], r15
0x14001fcb1  jbe     short loc_14001FCB6
0x14001fcb3  mov     rax, [rax]
0x14001fcb6  mov     rcx, rax; lpFileName
0x14001fcb9  call    cs:__imp_GetFileAttributesW
0x14001fcbf  cmp     eax, 0FFFFFFFFh
0x14001fcc2  jz      short loc_14001FCCA
0x14001fcc4  test    al, 10h
0x14001fcc6  mov     bl, 1
0x14001fcc8  jnz     short loc_14001FCCD
0x14001fcca  mov     bl, r14b
0x14001fccd  lea     rcx, [rsp+228h+var_C8]
0x14001fcd5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001fcda  test    bl, bl
0x14001fcdc  jz      loc_14001FF3B
0x14001fce2  lea     rdx, [rsp+228h+var_E8]
0x14001fcea  lea     rcx, [rsp+228h+var_A8]
0x14001fcf2  call    ?stem_v3@path@filesystem@boost@@AEBA?AV123@XZ; boost::filesystem::path::stem_v3(void)
0x14001fcf7  nop
0x14001fcf8  lea     rdx, [rsp+228h+var_48]
0x14001fd00  lea     rcx, [rsp+228h+var_A8]
0x14001fd08  call    ?parent_path@path@filesystem@boost@@QEBA?AV123@XZ; boost::filesystem::path::parent_path(void)
0x14001fd0d  mov     rbx, rax
0x14001fd10  lea     rdx, [rsp+228h+var_E8]; struct boost::filesystem::path *
0x14001fd18  mov     rcx, rax; this
0x14001fd1b  call    ?append_v3@path@filesystem@boost@@AEAAXAEBV123@@Z; boost::filesystem::path::append_v3(boost::filesystem::path const &)
0x14001fd20  xorps   xmm0, xmm0
0x14001fd23  movups  [rsp+228h+var_C8], xmm0
0x14001fd2b  mov     qword ptr [rsp+228h+var_B8], r14
0x14001fd33  mov     qword ptr [rsp+228h+var_B8+8], r14
0x14001fd3b  movups  xmm0, xmmword ptr [rbx]
0x14001fd3e  movups  [rsp+228h+var_C8], xmm0
0x14001fd46  movups  xmm1, xmmword ptr [rbx+10h]
0x14001fd4a  movups  [rsp+228h+var_B8], xmm1
0x14001fd52  mov     [rbx+10h], r14
0x14001fd56  mov     [rbx+18h], r15
0x14001fd5a  mov     [rbx], r14w
0x14001fd5e  lea     rcx, [rsp+228h+var_48]
0x14001fd66  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001fd6b  nop
0x14001fd6c  lea     rcx, [rsp+228h+var_E8]
0x14001fd74  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001fd79  lea     rcx, [rsp+228h+var_1D8]
0x14001fd7e  call    ??0?$basic_ostringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wostringstream::wostringstream(void)
0x14001fd83  nop
0x14001fd84  lea     rdx, [rsp+228h+var_C8]
0x14001fd8c  cmp     qword ptr [rsp+228h+var_B8+8], r15
0x14001fd94  cmova   rdx, qword ptr [rsp+228h+var_C8]
0x14001fd9d  lea     rcx, [rsp+228h+var_1D8]
0x14001fda2  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x14001fda7  lea     rdx, asc_1400A79C4; "_"
0x14001fdae  mov     rcx, rax
0x14001fdb1  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x14001fdb6  mov     rbx, rax
0x14001fdb9  call    cs:__imp_GetCurrentProcessId
0x14001fdbf  mov     edx, eax
0x14001fdc1  mov     rcx, rbx
0x14001fdc4  call    cs:__imp_??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z; std::wostream::operator<<(ulong)
0x14001fdca  mov     rbx, rax
0x14001fdcd  lea     rdx, [rsp+228h+var_E8]
0x14001fdd5  lea     rcx, [rsp+228h+var_A8]
0x14001fddd  call    ?extension_v3@path@filesystem@boost@@AEBA?AV123@XZ; boost::filesystem::path::extension_v3(void)
0x14001fde2  nop
0x14001fde3  lea     rdx, [rsp+228h+var_E8]
0x14001fdeb  cmp     [rsp+228h+var_D0], r15
0x14001fdf3  cmova   rdx, [rsp+228h+var_E8]
0x14001fdfc  mov     rcx, rbx
0x14001fdff  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x14001fe04  nop
0x14001fe05  lea     rcx, [rsp+228h+var_E8]
0x14001fe0d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14001fe12  lea     rdx, [rsp+228h+var_88]
0x14001fe1a  lea     rcx, [rsp+228h+var_1D0]
0x14001fe1f  call    ?str@?$basic_stringbuf@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::wstringbuf::str(void)
0x14001fe24  lea     rax, [rsp+228h+var_88]
0x14001fe2c  cmp     rdi, rax
0x14001fe2f  jz      short loc_14001FE69
  ... truncated ...
```
