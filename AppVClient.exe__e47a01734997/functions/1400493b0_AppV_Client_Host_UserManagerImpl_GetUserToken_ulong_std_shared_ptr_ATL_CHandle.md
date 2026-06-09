# AppV::Client::Host::UserManagerImpl::GetUserToken(ulong,std::shared_ptr<ATL::CHandle> &)

- ea: `0x1400493b0`
- end: `0x14004961b`
- name: `?GetUserToken@UserManagerImpl@Host@Client@AppV@@CA_KKAEAV?$shared_ptr@VCHandle@ATL@@@std@@@Z`
- size: `619`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140049e30`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x1400493b0`
- `0x14006a010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14004953c`
- `KERNEL32!CloseHandle` at `0x1400495ea`
- `KERNEL32!CloseHandle` at `0x14004953c`
- `KERNEL32!CloseHandle` at `0x1400495ea`
- `KERNEL32!GetLastError` at `0x1400493f5`
- `KERNEL32!GetLastError` at `0x1400493f5`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400494f3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400494f3`
- `WTSAPI32!WTSQueryUserToken` at `0x1400493e7`
- `WTSAPI32!WTSQueryUserToken` at `0x1400493e7`

## string_xrefs

- `0x1400494ec`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x140049503`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x1400493fe`: `AppV::Client::Host::UserManagerImpl::GetUserToken`
- `0x140049437`: `UserManager failed to get the user token for session %1%, error = %2%`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall AppV::Client::Host::UserManagerImpl::GetUserToken(ULONG a1, _QWORD *a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rbx
  char *v8; // rax
  const char *v9; // rax
  unsigned __int64 FileId; // rax
  __int64 v11; // rbx
  _QWORD *v13; // rbx
  HANDLE v14; // rcx
  _DWORD *v15; // rax
  volatile signed __int32 *v16; // rbx
  HANDLE phToken; // [rsp+20h] [rbp-69h] BYREF
  _DWORD *v18; // [rsp+28h] [rbp-61h] BYREF
  ULONG v19; // [rsp+30h] [rbp-59h] BYREF
  __int128 v20; // [rsp+38h] [rbp-51h] BYREF
  __int64 v21; // [rsp+48h] [rbp-41h]
  __int64 v22; // [rsp+50h] [rbp-39h]
  __int128 v23; // [rsp+58h] [rbp-31h] BYREF
  __int64 v24; // [rsp+68h] [rbp-21h]
  __int64 v25; // [rsp+70h] [rbp-19h]
  char *v26[4]; // [rsp+78h] [rbp-11h] BYREF
  int v27; // [rsp+98h] [rbp+Fh]
  void **v28; // [rsp+A0h] [rbp+17h] BYREF
  char *v29; // [rsp+B0h] [rbp+27h] BYREF

  v19 = a1;
  phToken = 0;
  if ( WTSQueryUserToken(a1, &phToken) )
  {
    v13 = operator new(8u);
    v14 = phToken;
    phToken = 0;
    *v13 = v14;
    v18 = v13;
    v15 = operator new(0x18u);
    v18 = v15;
    *(_OWORD *)v15 = 0;
    v15[2] = 1;
    v15[3] = 1;
    *(_QWORD *)v15 = &std::_Ref_count<ATL::CHandle>::`vftable';
    *((_QWORD *)v15 + 2) = v13;
    *a2 = v13;
    v16 = (volatile signed __int32 *)a2[1];
    a2[1] = v15;
    if ( v16 )
    {
      if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
    if ( phToken )
      CloseHandle(phToken);
    return 0x8000000000LL;
  }
  else
  {
    LODWORD(v18) = GetLastError();
    std::string::string(v26, "AppV::Client::Host::UserManagerImpl::GetUserToken");
    v27 = 446;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v3);
    v23 = 0;
    v24 = 0;
    v25 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v23,
      L"UserManager failed to get the user token for session %1%, error = %2%",
      0x45u);
    v5 = AppV::Log::fmt(v4, &v28, &v23);
    v6 = AppV::LogFormatter::operator%<unsigned long>(v5, (__int64)&v19);
    v7 = AppV::LogFormatter::operator%<unsigned long>(v6, (__int64)&v18);
    v20 = 0;
    v21 = 0;
    v22 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v20, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v26, 1, (int)&v20, v7);
    std::wstring::~wstring((char **)&v20);
    v28 = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(&v29);
    std::wstring::~wstring((char **)&v23);
    std::string::~string(v26);
    v8 = strrchr("admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp", 92);
    if ( v8 )
      v9 = v8 + 1;
    else
      v9 = "admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v9);
    v11 = (unsigned int)v18 | (FileId << 52) | 0x372E00000000LL;
    if ( phToken )
      CloseHandle(phToken);
    return v11;
  }
}

```

## disassembly

```asm
0x1400493b0  mov     [rsp-8+arg_10], rbx
0x1400493b5  mov     [rsp-8+arg_18], rdi
0x1400493ba  push    rbp
0x1400493bb  lea     rbp, [rsp-57h]
0x1400493c0  sub     rsp, 0E0h
0x1400493c7  mov     rax, cs:__security_cookie
0x1400493ce  xor     rax, rsp
0x1400493d1  mov     [rbp+57h+var_10], rax
0x1400493d5  mov     rdi, rdx
0x1400493d8  mov     [rbp+57h+var_B0], ecx
0x1400493db  mov     [rbp+57h+phToken], 0
0x1400493e3  lea     rdx, [rbp+57h+phToken]; phToken
0x1400493e7  call    cs:__imp_WTSQueryUserToken
0x1400493ed  test    eax, eax
0x1400493ef  jnz     loc_14004954A
0x1400493f5  call    cs:__imp_GetLastError
0x1400493fb  mov     dword ptr [rbp+57h+var_B8], eax
0x1400493fe  lea     rdx, aAppvClientHost_7; "AppV::Client::Host::UserManagerImpl::Ge"...
0x140049405  lea     rcx, [rbp+57h+var_68]
0x140049409  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004940e  mov     [rbp+57h+var_48], 1BEh
0x140049415  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004941a  xorps   xmm0, xmm0
0x14004941d  movups  [rbp+57h+var_88], xmm0
0x140049421  mov     [rbp+57h+var_78], 0
0x140049429  mov     [rbp+57h+var_70], 0
0x140049431  mov     r8d, 45h ; 'E'
0x140049437  lea     rdx, aUsermanagerFai_8; "UserManager failed to get the user toke"...
0x14004943e  lea     rcx, [rbp+57h+var_88]
0x140049442  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140049447  nop
0x140049448  lea     r8, [rbp+57h+var_88]
0x14004944c  lea     rdx, [rbp+57h+var_40]
0x140049450  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140049455  nop
0x140049456  lea     rdx, [rbp+57h+var_B0]
0x14004945a  mov     rcx, rax
0x14004945d  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140049462  lea     rdx, [rbp+57h+var_B8]
0x140049466  mov     rcx, rax
0x140049469  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004946e  mov     rbx, rax
0x140049471  xorps   xmm0, xmm0
0x140049474  movups  [rbp+57h+var_A8], xmm0
0x140049478  mov     [rbp+57h+var_98], 0
0x140049480  mov     [rbp+57h+var_90], 0
0x140049488  mov     r8d, 6
0x14004948e  lea     rdx, aClient; "Client"
0x140049495  lea     rcx, [rbp+57h+var_A8]
0x140049499  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004949e  nop
0x14004949f  mov     r9, rbx
0x1400494a2  lea     r8, [rbp+57h+var_A8]
0x1400494a6  mov     edx, 1
0x1400494ab  lea     rcx, [rbp+57h+var_68]
0x1400494af  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x1400494b4  nop
0x1400494b5  lea     rcx, [rbp+57h+var_A8]
0x1400494b9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400494be  nop
0x1400494bf  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x1400494c6  mov     [rbp+57h+var_40], rax
0x1400494ca  lea     rcx, [rbp+57h+var_30]
0x1400494ce  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400494d3  nop
0x1400494d4  lea     rcx, [rbp+57h+var_88]
0x1400494d8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400494dd  nop
0x1400494de  lea     rcx, [rbp+57h+var_68]
0x1400494e2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400494e7  mov     edx, 5Ch ; '\'; Ch
0x1400494ec  lea     rcx, aAdminAppmanApp_17; "admin\\appman\\appv\\client\\host\\comm"...
0x1400494f3  call    cs:__imp_strrchr
0x1400494f9  test    rax, rax
0x1400494fc  jz      short loc_140049503
0x1400494fe  inc     rax
0x140049501  jmp     short loc_14004950A
0x140049503  lea     rax, aAdminAppmanApp_17; "admin\\appman\\appv\\client\\host\\comm"...
0x14004950a  mov     rdx, rax; char *
0x14004950d  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140049514  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x140049519  mov     rbx, rax
0x14004951c  shl     rbx, 34h
0x140049520  mov     ecx, dword ptr [rbp+57h+var_B8]
0x140049523  or      rbx, rcx
0x140049526  mov     rax, 372E00000000h
0x140049530  or      rbx, rax
0x140049533  mov     rcx, [rbp+57h+phToken]; hObject
0x140049537  test    rcx, rcx
0x14004953a  jz      short loc_140049542
0x14004953c  call    cs:__imp_CloseHandle
0x140049542  mov     rax, rbx
0x140049545  jmp     loc_1400495FA
0x14004954a  mov     ecx, 8; Size
0x14004954f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140049554  mov     rbx, rax
0x140049557  mov     rcx, [rbp+57h+phToken]
0x14004955b  mov     [rbp+57h+phToken], 0
0x140049563  mov     [rax], rcx
0x140049566  mov     [rbp+57h+var_B8], rax
0x14004956a  mov     ecx, 18h; Size
0x14004956f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140049574  mov     [rbp+57h+var_B8], rax
0x140049578  xorps   xmm0, xmm0
0x14004957b  movups  xmmword ptr [rax], xmm0
0x14004957e  mov     dword ptr [rax+8], 1
0x140049585  mov     dword ptr [rax+0Ch], 1
0x14004958c  lea     rcx, ??_7?$_Ref_count@VCHandle@ATL@@@std@@6B@; const std::_Ref_count<ATL::CHandle>::`vftable'
0x140049593  mov     [rax], rcx
0x140049596  mov     [rax+10h], rbx
0x14004959a  mov     [rdi], rbx
0x14004959d  mov     rbx, [rdi+8]
0x1400495a1  mov     [rdi+8], rax
0x1400495a5  test    rbx, rbx
0x1400495a8  jz      short loc_1400495E1
0x1400495aa  or      edi, 0FFFFFFFFh
0x1400495ad  mov     eax, edi
0x1400495af  lock xadd [rbx+8], eax
0x1400495b4  add     eax, edi
0x1400495b6  jnz     short loc_1400495E1
0x1400495b8  mov     rax, [rbx]
0x1400495bb  mov     rcx, rbx
0x1400495be  mov     rax, [rax]
0x1400495c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400495c6  mov     eax, edi
0x1400495c8  lock xadd [rbx+0Ch], eax
0x1400495cd  add     eax, edi
0x1400495cf  jnz     short loc_1400495E1
0x1400495d1  mov     rax, [rbx]
0x1400495d4  mov     rcx, rbx
0x1400495d7  mov     rax, [rax+8]
0x1400495db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400495e0  nop
0x1400495e1  mov     rcx, [rbp+57h+phToken]; hObject
0x1400495e5  test    rcx, rcx
0x1400495e8  jz      short loc_1400495F0
0x1400495ea  call    cs:__imp_CloseHandle
0x1400495f0  mov     rax, 8000000000h
0x1400495fa  mov     rcx, [rbp+57h+var_10]
0x1400495fe  xor     rcx, rsp; StackCookie
0x140049601  call    __security_check_cookie
0x140049606  lea     r11, [rsp+0E0h+var_s0]
0x14004960e  mov     rbx, [r11+20h]
0x140049612  mov     rdi, [r11+28h]
0x140049616  mov     rsp, r11
0x140049619  pop     rbp
0x14004961a  retn
```
