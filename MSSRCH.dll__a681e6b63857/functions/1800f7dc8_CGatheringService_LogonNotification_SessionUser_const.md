# CGatheringService::LogonNotification(SessionUser const &)

- ea: `0x1800f7dc8`
- end: `0x1800f811d`
- name: `?LogonNotification@CGatheringService@@QEAAJAEBUSessionUser@@@Z`
- size: `853`
- prototype: `__int64 __fastcall(CGatheringService *__hidden this, const struct SessionUser *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180142430`

## callees

- `0x18000f880`
- `0x18004b638`
- `0x180052460`
- `0x18005e788`
- `0x180079c7c`
- `0x180079d34`
- `0x1800b4938`
- `0x1800cccec`
- `0x1800ccd20`
- `0x1800ccda4`
- `0x1800e3668`
- `0x1800eb1b0`
- `0x1800f7dc8`
- `0x1800f84fc`
- `0x1800f873c`
- `0x1800f89f0`
- `0x1800f8f24`
- `0x18010c3c0`
- `0x1801244a4`
- `0x1801244c0`
- `0x18017a090`
- `0x18017d22c`
- `0x18020ef90`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f7f2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f80db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f7f2e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f80db`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800f7f5a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800f7f5a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800f8089`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800f8089`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f7eef`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f7eef`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800f7e4f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800f7e4f`

## string_xrefs

- `0x1800f809f`: `onecoreuap\base\appmodel\search\common\screenonsession\screenoneventmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CGatheringService::LogonNotification(CGatheringService *this, const struct SessionUser *a2)
{
  CRegistry *v3; // rsi
  int inited; // eax
  unsigned int LastError; // ebx
  __int64 v6; // rax
  int UserToken; // eax
  int token_information; // eax
  void *v9; // rcx
  void *v10; // rdi
  BOOL v11; // ebx
  const char *v12; // r9
  HLOCAL v13; // rcx
  bool v14; // zf
  __int64 v15; // rdx
  unsigned __int64 v16; // r9
  int v17; // eax
  int v18; // r9d
  void *v19; // r9
  int v20; // eax
  HRESULT Guid; // eax
  HLOCAL v22; // rcx
  HLOCAL hMem; // [rsp+20h] [rbp-E0h] BYREF
  void *v25; // [rsp+28h] [rbp-D8h] BYREF
  void *Block; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR StringSid[2]; // [rsp+38h] [rbp-C8h] BYREF
  char v28; // [rsp+48h] [rbp-B8h]
  _BYTE v29[2416]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A08h] [rbp+908h]

  v3 = g_pGatheringService;
  inited = CGatheringService::WaitForInitDone(g_pGatheringService);
  LastError = inited;
  if ( inited >= 0 )
  {
    ++*((_DWORD *)v3 + 974);
    _InterlockedIncrement((volatile signed __int32 *)v3 + 975);
    v25 = 0;
    v6 = wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&v25);
    UserToken = UMgrQueryUserToken(*((_QWORD *)a2 + 1), v6);
    LastError = UserToken;
    if ( UserToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA73,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
        (const char *)(unsigned int)UserToken,
        (int)hMem);
LABEL_34:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v25);
      return LastError;
    }
    Block = 0;
    token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, v25);
    LastError = token_information;
    if ( token_information < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA76,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
        (const char *)(unsigned int)token_information,
        (int)hMem);
      v9 = Block;
      if ( !Block )
        goto LABEL_34;
LABEL_7:
      operator delete(v9);
      goto LABEL_34;
    }
    hMem = 0;
    StringSid[0] = (LPWSTR)&hMem;
    StringSid[1] = 0;
    v28 = 1;
    v10 = Block;
    v11 = ConvertSidToStringSidW(*(PSID *)Block, &StringSid[1]);
    wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(StringSid);
    if ( !v11 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xA79,
                    (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
                    v12);
LABEL_10:
      v13 = hMem;
      v14 = hMem == 0;
      hMem = 0;
      if ( !v14 )
        LocalFree(v13);
      if ( !v10 )
        goto LABEL_34;
      v9 = v10;
      goto LABEL_7;
    }
    InitOnceExecuteOnce(
      &g_initOnceOnPerUserCatalogCheck,
      _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
      0,
      0);
    if ( g_isPerUserCatalogEnabled )
    {
      if ( *((_DWORD *)v3 + 1003) )
      {
        LastError = -2147218141;
        v15 = 2685;
LABEL_17:
        v16 = LastError;
LABEL_18:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
          (const char *)v16,
          (int)hMem);
        goto LABEL_10;
      }
      if ( (int)CGatheringService::HandleLogonForPerUserCatalog((CGatherApplicationCollection **)v3, (wchar_t *)hMem) < 0 )
      {
        CSearchEventEntry::CSearchEventEntry((CSearchEventEntry *)v29, *((struct CEventLog **)v3 + 49));
        CSearchEventEntry::SetError((CSearchEventEntry *)v29, v18);
        CSearchEventEntry::ReportError((CSearchEventEntry *)v29, 0xC000272B, hMem, 0);
        CSearchEventEntry::~CSearchEventEntry((CSearchEventEntry *)v29);
      }
      else
      {
        CGatheringService::CalculatePerUserCatalogResources(v3);
        CFilterPool::SetThreadsPerFilterDaemon(*((CFilterPool **)v3 + 490), *((_DWORD *)v3 + 972));
        v17 = CRobotThreadPool::SetThreads(*((CRobotThreadPool **)v3 + 488), *((_DWORD *)v3 + 971));
        if ( v17 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xA86,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
            (const char *)(unsigned int)v17,
            (int)hMem);
      }
    }
    v19 = v25;
    v25 = 0;
    v20 = CUserSettings::HandleLogonEvent((CRegistry *)((char *)v3 + 6688), a2, (const wchar_t *)hMem, v19);
    LastError = v20;
    if ( v20 < 0 )
    {
      v16 = (unsigned int)v20;
      v15 = 2704;
      goto LABEL_18;
    }
    CGatheringService::HandleDplKeyChange(v3);
    if ( IsDesktopSKU() )
    {
      *(_OWORD *)StringSid = 0;
      Guid = CoCreateGuid((GUID *)StringSid);
      LastError = Guid;
      if ( Guid < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\screenonsession\\screenoneventmanager.cpp",
          (const char *)(unsigned int)Guid,
          (int)hMem);
        v15 = 2711;
        goto LABEL_17;
      }
      LogonEventManager::OnSessionBegin((LogonEventManager *)&g_logonEventManager, (const struct _GUID *)StringSid);
    }
    v22 = hMem;
    hMem = 0;
    if ( v22 )
      LocalFree(v22);
    if ( v10 )
      operator delete(v10);
    LastError = 0;
    goto LABEL_34;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA6D,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
    (const char *)(unsigned int)inited,
    (int)hMem);
  return LastError;
}

```

## disassembly

```asm
0x1800f7dc8  push    rbp
0x1800f7dca  push    rbx
0x1800f7dcb  push    rsi
0x1800f7dcc  push    rdi
0x1800f7dcd  push    r14
0x1800f7dcf  push    r15
0x1800f7dd1  lea     rbp, [rsp-8D8h]
0x1800f7dd9  sub     rsp, 9D8h
0x1800f7de0  mov     rax, cs:__security_cookie
0x1800f7de7  xor     rax, rsp
0x1800f7dea  mov     [rbp+900h+var_40], rax
0x1800f7df1  mov     r14, rdx
0x1800f7df4  mov     rsi, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x1800f7dfb  mov     rcx, rsi; this
0x1800f7dfe  call    ?WaitForInitDone@CGatheringService@@QEAAJXZ; CGatheringService::WaitForInitDone(void)
0x1800f7e03  mov     ebx, eax
0x1800f7e05  xor     r15d, r15d
0x1800f7e08  test    eax, eax
0x1800f7e0a  jns     short loc_1800F7E2C
0x1800f7e0c  mov     rcx, [rbp+908h]; this
0x1800f7e13  mov     r9d, eax; char *
0x1800f7e16  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800f7e1d  mov     edx, 0A6Dh; void *
0x1800f7e22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f7e27  jmp     loc_1800F80FC
0x1800f7e2c  inc     dword ptr [rsi+0F38h]
0x1800f7e32  lock inc dword ptr [rsi+0F3Ch]
0x1800f7e39  mov     [rsp+0A00h+var_9D8], r15
0x1800f7e3e  lea     rcx, [rsp+0A00h+var_9D8]
0x1800f7e43  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x1800f7e48  mov     rdx, rax
0x1800f7e4b  mov     rcx, [r14+8]
0x1800f7e4f  call    cs:__imp_UMgrQueryUserToken
0x1800f7e55  mov     ebx, eax
0x1800f7e57  test    eax, eax
0x1800f7e59  jns     short loc_1800F7E7B
0x1800f7e5b  mov     rcx, [rbp+908h]; this
0x1800f7e62  mov     r9d, eax; char *
0x1800f7e65  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800f7e6c  mov     edx, 0A73h; void *
0x1800f7e71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f7e76  jmp     loc_1800F80F2
0x1800f7e7b  mov     [rsp+0A00h+Block], r15
0x1800f7e80  mov     rdx, [rsp+0A00h+var_9D8]
0x1800f7e85  lea     rcx, [rsp+0A00h+Block]
0x1800f7e8a  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800f7e8f  mov     ebx, eax
0x1800f7e91  test    eax, eax
0x1800f7e93  jns     short loc_1800F7EC9
0x1800f7e95  mov     rcx, [rbp+908h]; this
0x1800f7e9c  mov     r9d, eax; char *
0x1800f7e9f  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800f7ea6  mov     edx, 0A76h; void *
0x1800f7eab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f7eb0  nop
0x1800f7eb1  mov     rcx, [rsp+0A00h+Block]; Block
0x1800f7eb6  test    rcx, rcx
0x1800f7eb9  jz      loc_1800F80F2
0x1800f7ebf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f7ec4  jmp     loc_1800F80F2
0x1800f7ec9  mov     [rsp+0A00h+hMem], r15; int
0x1800f7ece  lea     rax, [rsp+0A00h+hMem]
0x1800f7ed3  mov     [rsp+0A00h+StringSid], rax
0x1800f7ed8  mov     [rsp+0A00h+StringSid+8], r15
0x1800f7edd  mov     [rsp+0A00h+var_9B8], 1
0x1800f7ee2  lea     rdx, [rsp+0A00h+StringSid+8]; StringSid
0x1800f7ee7  mov     rdi, [rsp+0A00h+Block]
0x1800f7eec  mov     rcx, [rdi]; Sid
0x1800f7eef  call    cs:__imp_ConvertSidToStringSidW
0x1800f7ef5  mov     ebx, eax
0x1800f7ef7  lea     rcx, [rsp+0A00h+StringSid]
0x1800f7efc  call    ??1?$out_param_t@V?$unique_ptr@_WU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<wchar_t,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800f7f01  test    ebx, ebx
0x1800f7f03  jnz     short loc_1800F7F46
0x1800f7f05  mov     rcx, [rbp+908h]; this
0x1800f7f0c  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800f7f13  mov     edx, 0A79h; void *
0x1800f7f18  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f7f1d  mov     ebx, eax
0x1800f7f1f  mov     rcx, [rsp+0A00h+hMem]; hMem
0x1800f7f24  test    rcx, rcx
0x1800f7f27  mov     [rsp+0A00h+hMem], r15
0x1800f7f2c  jz      short loc_1800F7F35
0x1800f7f2e  call    cs:__imp_LocalFree
0x1800f7f34  nop
0x1800f7f35  test    rdi, rdi
0x1800f7f38  jz      loc_1800F80F2
0x1800f7f3e  mov     rcx, rdi
0x1800f7f41  jmp     loc_1800F7EBF
0x1800f7f46  xor     r9d, r9d; Context
0x1800f7f49  xor     r8d, r8d; Parameter
0x1800f7f4c  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800f7f53  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800f7f5a  call    cs:__imp_InitOnceExecuteOnce
0x1800f7f60  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, r15b; bool g_isPerUserCatalogEnabled
0x1800f7f67  jz      loc_1800F803A
0x1800f7f6d  cmp     [rsi+0FACh], r15d
0x1800f7f74  jz      short loc_1800F7F98
0x1800f7f76  mov     ebx, 80040D23h
0x1800f7f7b  mov     edx, 0A7Dh; void *
0x1800f7f80  mov     r9d, ebx; char *
0x1800f7f83  mov     rcx, [rbp+908h]; this
0x1800f7f8a  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800f7f91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f7f96  jmp     short loc_1800F7F1F
0x1800f7f98  mov     rdx, [rsp+0A00h+hMem]; wchar_t *
0x1800f7f9d  mov     rcx, rsi; this
0x1800f7fa0  call    ?HandleLogonForPerUserCatalog@CGatheringService@@QEAAJPEB_W@Z; CGatheringService::HandleLogonForPerUserCatalog(wchar_t const *)
0x1800f7fa5  mov     r9d, eax
0x1800f7fa8  test    eax, eax
0x1800f7faa  js      short loc_1800F7FF9
0x1800f7fac  mov     rcx, rsi; this
0x1800f7faf  call    ?CalculatePerUserCatalogResources@CGatheringService@@AEAAXXZ; CGatheringService::CalculatePerUserCatalogResources(void)
0x1800f7fb4  mov     edx, [rsi+0F30h]; unsigned int
0x1800f7fba  mov     rcx, [rsi+0F50h]; this
0x1800f7fc1  call    ?SetThreadsPerFilterDaemon@CFilterPool@@QEAAXK@Z; CFilterPool::SetThreadsPerFilterDaemon(ulong)
0x1800f7fc6  mov     edx, [rsi+0F2Ch]; unsigned int
0x1800f7fcc  mov     rcx, [rsi+0F40h]; this
0x1800f7fd3  call    ?SetThreads@CRobotThreadPool@@QEAAJK@Z; CRobotThreadPool::SetThreads(ulong)
0x1800f7fd8  mov     rcx, [rbp+908h]; this
0x1800f7fdf  test    eax, eax
0x1800f7fe1  jns     short loc_1800F803A
0x1800f7fe3  mov     r9d, eax; char *
0x1800f7fe6  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800f7fed  mov     edx, 0A86h; void *
0x1800f7ff2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f7ff7  jmp     short loc_1800F803A
0x1800f7ff9  mov     rdx, [rsi+188h]; struct CEventLog *
0x1800f8000  lea     rcx, [rsp+0A00h+var_9B0]; this
0x1800f8005  call    ??0CSearchEventEntry@@QEAA@PEAVCEventLog@@@Z; CSearchEventEntry::CSearchEventEntry(CEventLog *)
0x1800f800a  nop
0x1800f800b  mov     edx, r9d; int
0x1800f800e  lea     rcx, [rsp+0A00h+var_9B0]; this
0x1800f8013  call    ?SetError@CSearchEventEntry@@QEAAXJ@Z; CSearchEventEntry::SetError(long)
0x1800f8018  xor     r9d, r9d
0x1800f801b  mov     r8, [rsp+0A00h+hMem]
0x1800f8020  mov     edx, 0C000272Bh; unsigned int
0x1800f8025  lea     rcx, [rsp+0A00h+var_9B0]; this
0x1800f802a  call    ?ReportError@CSearchEventEntry@@QEAAXKZZ; CSearchEventEntry::ReportError(ulong,...)
0x1800f802f  nop
0x1800f8030  lea     rcx, [rsp+0A00h+var_9B0]; this
0x1800f8035  call    ??1CSearchEventEntry@@QEAA@XZ; CSearchEventEntry::~CSearchEventEntry(void)
0x1800f803a  mov     r9, [rsp+0A00h+var_9D8]; void *
0x1800f803f  mov     [rsp+0A00h+var_9D8], r15
0x1800f8044  lea     rcx, [rsi+1A20h]; this
0x1800f804b  mov     r8, [rsp+0A00h+hMem]; wchar_t *
0x1800f8050  mov     rdx, r14; struct SessionUser *
0x1800f8053  call    ?HandleLogonEvent@CUserSettings@@QEAAJAEBUSessionUser@@PEB_WPEAX@Z; CUserSettings::HandleLogonEvent(SessionUser const &,wchar_t const *,void *)
0x1800f8058  mov     ebx, eax
0x1800f805a  test    eax, eax
0x1800f805c  jns     short loc_1800F806B
0x1800f805e  mov     r9d, eax
0x1800f8061  mov     edx, 0A90h
0x1800f8066  jmp     loc_1800F7F83
0x1800f806b  mov     rcx, rsi; this
0x1800f806e  call    ?HandleDplKeyChange@CGatheringService@@QEAAJXZ; CGatheringService::HandleDplKeyChange(void)
0x1800f8073  call    ?IsDesktopSKU@@YA_NXZ; IsDesktopSKU(void)
0x1800f8078  test    al, al
0x1800f807a  jz      short loc_1800F80CC
0x1800f807c  xorps   xmm0, xmm0
0x1800f807f  movups  xmmword ptr [rsp+0A00h+StringSid], xmm0
0x1800f8084  lea     rcx, [rsp+0A00h+StringSid]; pguid
0x1800f8089  call    cs:__imp_CoCreateGuid
0x1800f808f  mov     ebx, eax
0x1800f8091  test    eax, eax
0x1800f8093  jns     short loc_1800F80BA
0x1800f8095  mov     rcx, [rbp+908h]; this
0x1800f809c  mov     r9d, eax; char *
0x1800f809f  lea     r8, aOnecoreuapBase_122; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800f80a6  mov     edx, 2Dh ; '-'; void *
0x1800f80ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f80b0  mov     edx, 0A97h
0x1800f80b5  jmp     loc_1800F7F80
0x1800f80ba  lea     rdx, [rsp+0A00h+StringSid]; struct _GUID *
0x1800f80bf  lea     rcx, ?g_logonEventManager@@3VLogonEventManager@@A; this
0x1800f80c6  call    ?OnSessionBegin@LogonEventManager@@UEAAXAEBU_GUID@@@Z; LogonEventManager::OnSessionBegin(_GUID const &)
0x1800f80cb  nop
0x1800f80cc  mov     rcx, [rsp+0A00h+hMem]; hMem
0x1800f80d1  mov     [rsp+0A00h+hMem], r15
0x1800f80d6  test    rcx, rcx
0x1800f80d9  jz      short loc_1800F80E2
0x1800f80db  call    cs:__imp_LocalFree
0x1800f80e1  nop
0x1800f80e2  test    rdi, rdi
0x1800f80e5  jz      short loc_1800F80EF
0x1800f80e7  mov     rcx, rdi; Block
0x1800f80ea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800f80ef  mov     ebx, r15d
0x1800f80f2  lea     rcx, [rsp+0A00h+var_9D8]
0x1800f80f7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800f80fc  mov     eax, ebx
0x1800f80fe  mov     rcx, [rbp+900h+var_40]
0x1800f8105  xor     rcx, rsp; StackCookie
0x1800f8108  call    __security_check_cookie
0x1800f810d  add     rsp, 9D8h
0x1800f8114  pop     r15
0x1800f8116  pop     r14
0x1800f8118  pop     rdi
0x1800f8119  pop     rsi
0x1800f811a  pop     rbx
0x1800f811b  pop     rbp
0x1800f811c  retn
```
