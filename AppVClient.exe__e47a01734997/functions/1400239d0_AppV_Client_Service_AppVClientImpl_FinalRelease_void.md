# AppV::Client::Service::AppVClientImpl::FinalRelease(void)

- ea: `0x1400239d0`
- end: `0x140023c4b`
- name: `?FinalRelease@AppVClientImpl@Service@Client@AppV@@QEAAXXZ`
- size: `635`
- prototype: `void __fastcall(AppV::Client::Service::AppVClientImpl *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x140008a8c`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x1400239d0`
- `0x1400383a0`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x14003cc80`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140023a20`
- `KERNEL32!GetCurrentThreadId` at `0x140023a20`
- `KERNEL32!LeaveCriticalSection` at `0x140023c21`
- `KERNEL32!LeaveCriticalSection` at `0x140023c21`
- `KERNEL32!EnterCriticalSection` at `0x140023a11`
- `KERNEL32!EnterCriticalSection` at `0x140023a11`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140023a5c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140023a86`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140023ab7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140023aee`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140023a5c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140023a86`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140023ab7`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140023aee`

## string_xrefs

- `0x140023a52`: `admin\appman\appv\client\host\service\publicapi.cpp`
- `0x140023b21`: `AppV::Client::Service::AppVClientImpl::FinalRelease`
- `0x140023b52`: `Failed to unregister a Client event subscriber when the caller's COM object was being destroyed, error = %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall AppV::Client::Service::AppVClientImpl::FinalRelease(AppV::Client::Service::AppVClientImpl *this)
{
  char *v2; // rdi
  struct IAppVClientEventSink *v3; // rcx
  unsigned __int64 v4; // rbx
  char *v5; // rax
  const char *v6; // rax
  char *v7; // rax
  const char *v8; // rax
  char *v9; // rax
  const char *v10; // rax
  char *v11; // rax
  const char *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 v19[2]; // [rsp+20h] [rbp-79h] BYREF
  char v20; // [rsp+30h] [rbp-69h]
  char *v21; // [rsp+38h] [rbp-61h]
  _OWORD v22[2]; // [rsp+40h] [rbp-59h] BYREF
  _OWORD v23[2]; // [rsp+60h] [rbp-39h] BYREF
  char *v24[4]; // [rsp+80h] [rbp-19h] BYREF
  int v25; // [rsp+A0h] [rbp+7h]
  void **v26; // [rsp+A8h] [rbp+Fh] BYREF
  char *v27; // [rsp+B8h] [rbp+1Fh] BYREF

  v19[1] = (__int64)&softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
  v2 = (char *)this + 64;
  v21 = (char *)this + 64;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  if ( ++*((_DWORD *)v2 + 10) == 1 )
    *((_DWORD *)v2 + 11) = GetCurrentThreadId();
  v20 = 1;
  v3 = (struct IAppVClientEventSink *)*((_QWORD *)this + 14);
  if ( v3 )
  {
    v4 = AppV::Client::Service::AppVClientImpl::UnregisterSubscriber(v3);
    if ( (v4 & 0x8000000000LL) == 0 )
    {
      v5 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
      v6 = v5 ? v5 + 1 : "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
      AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v6);
      v7 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92);
      v8 = v7 ? v7 + 1 : "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp";
      AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v8);
      if ( (v4 & 0x2000000000LL) != 0
        || ((v9 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92)) == 0
          ? (v10 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp")
          : (v10 = v9 + 1),
            (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v10),
             (BYTE4(v4) & 0x1F) != 3)
         || ((v11 = strrchr("admin\\appman\\appv\\client\\host\\service\\publicapi.cpp", 92)) == 0
           ? (v12 = "admin\\appman\\appv\\client\\host\\service\\publicapi.cpp")
           : (v12 = v11 + 1),
             AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v12),
             (_DWORD)v4 != 257)) )
      {
        std::string::string(v24, "AppV::Client::Service::AppVClientImpl::FinalRelease");
        v25 = 341;
        AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v13);
        memset(v23, 0, sizeof(v23));
        std::wstring::_Construct<1,wchar_t const *>(
          (char **)v23,
          L"Failed to unregister a Client event subscriber when the caller's COM object was being destroyed, error = %1%",
          0x6Cu);
        v15 = AppV::Log::fmt(v14, &v26, v23);
        v19[0] = v4;
        v16 = AppV::LogFormatter::operator%(v15, v19);
        memset(v22, 0, sizeof(v22));
        std::wstring::_Construct<1,wchar_t const *>((char **)v22, L"Client", 6u);
        AppV::DecoratedLog::operator()((char *)v24, 8, (int)v22, v16);
        std::wstring::~wstring((char **)v22);
        v26 = &AppV::LogFormatter::`vftable';
        std::wstring::~wstring(&v27);
        std::wstring::~wstring((char **)v23);
        std::string::~string(v24);
      }
    }
    v17 = *((_QWORD *)this + 14);
    if ( v17 )
    {
      *((_QWORD *)this + 14) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  if ( (*((_DWORD *)v2 + 10))-- == 1 )
    *((_DWORD *)v2 + 11) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)v2);
}

```

## disassembly

```asm
0x1400239d0  mov     [rsp-8+arg_8], rbx
0x1400239d5  mov     [rsp-8+arg_10], rsi
0x1400239da  push    rbp
0x1400239db  push    rdi
0x1400239dc  push    r14
0x1400239de  lea     rbp, [rsp-47h]
0x1400239e3  sub     rsp, 0E0h
0x1400239ea  mov     rax, cs:__security_cookie
0x1400239f1  xor     rax, rsp
0x1400239f4  mov     [rbp+57h+var_18], rax
0x1400239f8  mov     rsi, rcx
0x1400239fb  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x140023a02  mov     [rbp+57h+var_C8], rax
0x140023a06  lea     rdi, [rcx+40h]
0x140023a0a  mov     [rbp+57h+var_B8], rdi
0x140023a0e  mov     rcx, rdi; lpCriticalSection
0x140023a11  call    cs:__imp_EnterCriticalSection
0x140023a17  inc     dword ptr [rdi+28h]
0x140023a1a  cmp     dword ptr [rdi+28h], 1
0x140023a1e  jnz     short loc_140023A29
0x140023a20  call    cs:__imp_GetCurrentThreadId
0x140023a26  mov     [rdi+2Ch], eax
0x140023a29  mov     [rbp+57h+var_C0], 1
0x140023a2d  mov     rcx, [rsi+70h]; struct IAppVClientEventSink *
0x140023a31  test    rcx, rcx
0x140023a34  jz      loc_140023C11
0x140023a3a  call    ?UnregisterSubscriber@AppVClientImpl@Service@Client@AppV@@CA_KPEAUIAppVClientEventSink@@@Z; AppV::Client::Service::AppVClientImpl::UnregisterSubscriber(IAppVClientEventSink *)
0x140023a3f  mov     rbx, rax
0x140023a42  bt      rax, 27h ; '''
0x140023a47  jb      loc_140023BF3
0x140023a4d  mov     edx, 5Ch ; '\'; Ch
0x140023a52  lea     r14, aAdminAppmanApp_4; "admin\\appman\\appv\\client\\host\\serv"...
0x140023a59  mov     rcx, r14; Str
0x140023a5c  call    cs:__imp_strrchr
0x140023a62  test    rax, rax
0x140023a65  jz      short loc_140023A6C
0x140023a67  inc     rax
0x140023a6a  jmp     short loc_140023A6F
0x140023a6c  mov     rax, r14
0x140023a6f  mov     rdx, rax; char *
0x140023a72  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140023a79  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140023a7e  mov     edx, 5Ch ; '\'; Ch
0x140023a83  mov     rcx, r14; Str
0x140023a86  call    cs:__imp_strrchr
0x140023a8c  test    rax, rax
0x140023a8f  jz      short loc_140023A96
0x140023a91  inc     rax
0x140023a94  jmp     short loc_140023A99
0x140023a96  mov     rax, r14
0x140023a99  mov     rdx, rax; char *
0x140023a9c  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140023aa3  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140023aa8  bt      rbx, 25h ; '%'
0x140023aad  jb      short loc_140023B21
0x140023aaf  mov     edx, 5Ch ; '\'; Ch
0x140023ab4  mov     rcx, r14; Str
0x140023ab7  call    cs:__imp_strrchr
0x140023abd  test    rax, rax
0x140023ac0  jz      short loc_140023AC7
0x140023ac2  inc     rax
0x140023ac5  jmp     short loc_140023ACA
0x140023ac7  mov     rax, r14
0x140023aca  mov     rdx, rax; char *
0x140023acd  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140023ad4  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140023ad9  mov     rax, rbx
0x140023adc  shr     rax, 20h
0x140023ae0  and     al, 1Fh
0x140023ae2  cmp     al, 3
0x140023ae4  jnz     short loc_140023B21
0x140023ae6  mov     edx, 5Ch ; '\'; Ch
0x140023aeb  mov     rcx, r14; Str
0x140023aee  call    cs:__imp_strrchr
0x140023af4  test    rax, rax
0x140023af7  jz      short loc_140023AFE
0x140023af9  inc     rax
0x140023afc  jmp     short loc_140023B01
0x140023afe  mov     rax, r14
0x140023b01  mov     rdx, rax; char *
0x140023b04  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140023b0b  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140023b10  shl     rax, 34h
0x140023b14  or      eax, 101h
0x140023b19  cmp     ebx, eax
0x140023b1b  jz      loc_140023BF3
0x140023b21  lea     rdx, aAppvClientServ_4; "AppV::Client::Service::AppVClientImpl::"...
0x140023b28  lea     rcx, [rbp+57h+var_70]
0x140023b2c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140023b31  mov     [rbp+57h+var_50], 155h
0x140023b38  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140023b3d  xorps   xmm0, xmm0
0x140023b40  movups  [rbp+57h+var_90], xmm0
0x140023b44  xorps   xmm1, xmm1
0x140023b47  movdqu  [rbp+57h+var_80], xmm1
0x140023b4c  mov     r8d, 6Ch ; 'l'
0x140023b52  lea     rdx, aFailedToUnregi; "Failed to unregister a Client event sub"...
0x140023b59  lea     rcx, [rbp+57h+var_90]
0x140023b5d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140023b62  nop
0x140023b63  lea     r8, [rbp+57h+var_90]
0x140023b67  lea     rdx, [rbp+57h+var_48]
0x140023b6b  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140023b70  nop
0x140023b71  mov     [rbp+57h+var_D0], rbx
0x140023b75  lea     rdx, [rbp+57h+var_D0]
0x140023b79  mov     rcx, rax
0x140023b7c  call    ??LLogFormatter@AppV@@QEAAAEAV01@AEBVErrorCode@1@@Z; AppV::LogFormatter::operator%(AppV::ErrorCode const &)
0x140023b81  mov     rbx, rax
0x140023b84  xorps   xmm0, xmm0
0x140023b87  movups  [rbp+57h+var_B0], xmm0
0x140023b8b  xorps   xmm1, xmm1
0x140023b8e  movdqu  [rbp+57h+var_A0], xmm1
0x140023b93  mov     r8d, 6
0x140023b99  lea     rdx, aClient; "Client"
0x140023ba0  lea     rcx, [rbp+57h+var_B0]
0x140023ba4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140023ba9  nop
0x140023baa  mov     r9, rbx
0x140023bad  lea     r8, [rbp+57h+var_B0]
0x140023bb1  mov     edx, 8
0x140023bb6  lea     rcx, [rbp+57h+var_70]
0x140023bba  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140023bbf  nop
0x140023bc0  lea     rcx, [rbp+57h+var_B0]
0x140023bc4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023bc9  nop
0x140023bca  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140023bd1  mov     [rbp+57h+var_48], rax
0x140023bd5  lea     rcx, [rbp+57h+var_38]
0x140023bd9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023bde  nop
0x140023bdf  lea     rcx, [rbp+57h+var_90]
0x140023be3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023be8  nop
0x140023be9  lea     rcx, [rbp+57h+var_70]
0x140023bed  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140023bf2  nop
0x140023bf3  mov     rcx, [rsi+70h]
0x140023bf7  test    rcx, rcx
0x140023bfa  jz      short loc_140023C11
0x140023bfc  mov     qword ptr [rsi+70h], 0
0x140023c04  mov     rax, [rcx]
0x140023c07  mov     rax, [rax+10h]
0x140023c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023c10  nop
0x140023c11  sub     dword ptr [rdi+28h], 1
0x140023c15  jnz     short loc_140023C1E
0x140023c17  mov     dword ptr [rdi+2Ch], 0
0x140023c1e  mov     rcx, rdi; lpCriticalSection
0x140023c21  call    cs:__imp_LeaveCriticalSection
0x140023c27  mov     rcx, [rbp+57h+var_18]
0x140023c2b  xor     rcx, rsp; StackCookie
0x140023c2e  call    __security_check_cookie
0x140023c33  lea     r11, [rsp+0F0h+var_10]
0x140023c3b  mov     rbx, [r11+28h]
0x140023c3f  mov     rsi, [r11+30h]
0x140023c43  mov     rsp, r11
0x140023c46  pop     r14
0x140023c48  pop     rdi
0x140023c49  pop     rbp
0x140023c4a  retn
```
