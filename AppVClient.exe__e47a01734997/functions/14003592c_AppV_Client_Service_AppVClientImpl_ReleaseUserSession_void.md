# AppV::Client::Service::AppVClientImpl::ReleaseUserSession(void)

- ea: `0x14003592c`
- end: `0x140035a7f`
- name: `?ReleaseUserSession@AppVClientImpl@Service@Client@AppV@@CA_KXZ`
- size: `339`
- prototype: `unsigned __int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1400233dc`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140008e64`
- `0x140018bec`
- `0x14003592c`
- `0x140035a88`
- `0x14003c034`
- `0x14003c258`

## import_xrefs

- `KERNEL32!QueueUserWorkItem` at `0x14003596d`
- `KERNEL32!QueueUserWorkItem` at `0x14003596d`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140035a33`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140035a33`

## string_xrefs

- `0x1400359bc`: `A public API call was rejected because the Client service is in the process of shutting down.`
- `0x140035a2c`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x140035a43`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x140035990`: `AppV::Client::Service::AppVClientImpl::ReleaseUserSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
unsigned __int64 AppV::Client::Service::AppVClientImpl::ReleaseUserSession(void)
{
  char *v1; // rax
  const char *v2; // rax
  _OWORD v3[2]; // [rsp+20h] [rbp-19h] BYREF
  _OWORD v4[2]; // [rsp+40h] [rbp+7h] BYREF
  char *v5[4]; // [rsp+60h] [rbp+27h] BYREF
  int v6; // [rsp+80h] [rbp+47h]

  if ( AppV::Client::Service::AppVClientImpl::st_allowCalls
    && AppV::Client::Service::AppVClientImpl::st_controllerRequests )
  {
    if ( QueueUserWorkItem(AppV::Client::Service::AppVClientImpl::ReleaseUserSessionProc, 0, 0x100u) )
      return 0x8000000000LL;
    else
      return AppV::Client::Service::AppVClientImpl::ReleaseUserSessionInternal();
  }
  else
  {
    std::string::string(v5, "AppV::Client::Service::AppVClientImpl::ReleaseUserSession");
    v6 = 159;
    memset(v4, 0, sizeof(v4));
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)v4,
      L"A public API call was rejected because the Client service is in the process of shutting down.",
      0x5Du);
    memset(v3, 0, sizeof(v3));
    std::wstring::_Construct<1,wchar_t const *>((char **)v3, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v5, 8, (int)v3, (__int64)v4);
    std::wstring::~wstring((char **)v3);
    std::wstring::~wstring((char **)v4);
    std::string::~string(v5);
    v1 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
    if ( v1 )
      v2 = v1 + 1;
    else
      v2 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
    return (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v2) << 52)
         | 0x140300000101LL;
  }
}

```

## disassembly

```asm
0x14003592c  push    rbp
0x14003592e  lea     rbp, [rsp-57h]
0x140035933  sub     rsp, 90h
0x14003593a  mov     rax, cs:__security_cookie
0x140035941  xor     rax, rsp
0x140035944  mov     [rbp+57h+var_8], rax
0x140035948  mov     rcx, cs:?st_controllerRequests@AppVClientImpl@Service@Client@AppV@@0REAVControllerRequests@34@EA; AppV::Client::ControllerRequests * AppV::Client::Service::AppVClientImpl::st_controllerRequests
0x14003594f  mov     al, cs:?st_allowCalls@AppVClientImpl@Service@Client@AppV@@0_NC; bool volatile AppV::Client::Service::AppVClientImpl::st_allowCalls
0x140035955  test    al, al
0x140035957  jz      short loc_140035990
0x140035959  test    rcx, rcx
0x14003595c  jz      short loc_140035990
0x14003595e  xor     edx, edx; Context
0x140035960  mov     r8d, 100h; Flags
0x140035966  lea     rcx, ?ReleaseUserSessionProc@AppVClientImpl@Service@Client@AppV@@CAKPEAX@Z; Function
0x14003596d  call    cs:__imp_QueueUserWorkItem
0x140035973  test    eax, eax
0x140035975  jz      short loc_140035986
0x140035977  mov     rax, 8000000000h
0x140035981  jmp     loc_140035A6A
0x140035986  call    ?ReleaseUserSessionInternal@AppVClientImpl@Service@Client@AppV@@CA_KXZ; AppV::Client::Service::AppVClientImpl::ReleaseUserSessionInternal(void)
0x14003598b  jmp     loc_140035A6A
0x140035990  lea     rdx, aAppvClientServ_35; "AppV::Client::Service::AppVClientImpl::"...
0x140035997  lea     rcx, [rbp+57h+var_30]
0x14003599b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400359a0  mov     [rbp+57h+var_10], 9Fh
0x1400359a7  xorps   xmm0, xmm0
0x1400359aa  movups  [rbp+57h+var_50], xmm0
0x1400359ae  xorps   xmm1, xmm1
0x1400359b1  movdqu  [rbp+57h+var_40], xmm1
0x1400359b6  mov     r8d, 5Dh ; ']'
0x1400359bc  lea     rdx, aAPublicApiCall; "A public API call was rejected because "...
0x1400359c3  lea     rcx, [rbp+57h+var_50]
0x1400359c7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400359cc  nop
0x1400359cd  xorps   xmm0, xmm0
0x1400359d0  movups  [rbp+57h+var_70], xmm0
0x1400359d4  xorps   xmm1, xmm1
0x1400359d7  movdqu  [rbp+57h+var_60], xmm1
0x1400359dc  mov     r8d, 6
0x1400359e2  lea     rdx, aClient; "Client"
0x1400359e9  lea     rcx, [rbp+57h+var_70]
0x1400359ed  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400359f2  nop
0x1400359f3  lea     r9, [rbp+57h+var_50]
0x1400359f7  lea     r8, [rbp+57h+var_70]
0x1400359fb  mov     edx, 8
0x140035a00  lea     rcx, [rbp+57h+var_30]
0x140035a04  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140035a09  nop
0x140035a0a  lea     rcx, [rbp+57h+var_70]
0x140035a0e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140035a13  nop
0x140035a14  lea     rcx, [rbp+57h+var_50]
0x140035a18  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140035a1d  nop
0x140035a1e  lea     rcx, [rbp+57h+var_30]
0x140035a22  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140035a27  mov     edx, 5Ch ; '\'; Ch
0x140035a2c  lea     rcx, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140035a33  call    cs:__imp_strrchr
0x140035a39  test    rax, rax
0x140035a3c  jz      short loc_140035A43
0x140035a3e  inc     rax
0x140035a41  jmp     short loc_140035A4A
0x140035a43  lea     rax, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140035a4a  mov     rdx, rax; char *
0x140035a4d  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140035a54  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140035a59  shl     rax, 34h
0x140035a5d  mov     rcx, 140300000101h
0x140035a67  or      rax, rcx
0x140035a6a  mov     rcx, [rbp+57h+var_8]
0x140035a6e  xor     rcx, rsp; StackCookie
0x140035a71  call    __security_check_cookie
0x140035a76  add     rsp, 90h
0x140035a7d  pop     rbp
0x140035a7e  retn
```
