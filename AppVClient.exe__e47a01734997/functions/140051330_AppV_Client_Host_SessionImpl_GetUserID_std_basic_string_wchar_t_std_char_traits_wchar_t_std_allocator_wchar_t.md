# AppV::Client::Host::SessionImpl::GetUserID(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x140051330`
- end: `0x14005152b`
- name: `?GetUserID@SessionImpl@Host@Client@AppV@@UEBA_KAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `507`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x140020c60`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x1400418a0`
- `0x140051330`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400513ac`
- `KERNEL32!GetLastError` at `0x1400513ac`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400514a0`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400514a0`

## string_xrefs

- `0x140051499`: `admin\appman\appv\client\host\common\sessionimpl.cpp`
- `0x1400514b0`: `admin\appman\appv\client\host\common\sessionimpl.cpp`
- `0x1400513e8`: `UserManager failed to get the SID from the user token in session %1%, error = %2%`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall AppV::Client::Host::SessionImpl::GetUserID(__int64 a1, __int64 a2)
{
  __int64 UserTokenSID; // rax
  __int64 v5; // xmm6_8
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rbx
  char *v11; // rax
  const char *v12; // rax
  unsigned __int64 FileId; // rax
  __int64 v14; // rbx
  _BYTE v16[40]; // [rsp+28h] [rbp-89h] BYREF
  _OWORD v17[2]; // [rsp+50h] [rbp-61h] BYREF
  __int128 v18; // [rsp+70h] [rbp-41h] BYREF
  __int128 v19; // [rsp+80h] [rbp-31h]
  char *v20[4]; // [rsp+90h] [rbp-21h] BYREF
  int v21; // [rsp+B0h] [rbp-1h]
  void **v22; // [rsp+B8h] [rbp+7h] BYREF
  char *v23; // [rsp+C8h] [rbp+17h] BYREF

  UserTokenSID = AppUtils::getUserTokenSID((__int64)&v16[8], **(void ***)(a1 + 24));
  v18 = *(_OWORD *)UserTokenSID;
  v19 = *(_OWORD *)(UserTokenSID + 16);
  v5 = v19;
  *(_QWORD *)(UserTokenSID + 16) = 0;
  *(_QWORD *)(UserTokenSID + 24) = 7;
  *(_WORD *)UserTokenSID = 0;
  std::wstring::~wstring((char **)&v16[8]);
  if ( v5 )
  {
    std::wstring::operator=(a2, &v18);
    v14 = 0x8000000000LL;
  }
  else
  {
    *(_DWORD *)v16 = GetLastError();
    std::string::string(v20, "AppV::Client::Host::SessionImpl::GetUserID");
    v21 = 231;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v6);
    memset(&v16[8], 0, 32);
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v16[8],
      L"UserManager failed to get the SID from the user token in session %1%, error = %2%",
      0x51u);
    v8 = AppV::Log::fmt(v7, &v22, &v16[8]);
    v9 = AppV::LogFormatter::operator%<unsigned long>(v8, a1 + 16);
    v10 = AppV::LogFormatter::operator%<unsigned long>(v9, (__int64)v16);
    memset(v17, 0, sizeof(v17));
    std::wstring::_Construct<1,wchar_t const *>((char **)v17, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v20, 2, (int)v17, v10);
    std::wstring::~wstring((char **)v17);
    v22 = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(&v23);
    std::wstring::~wstring((char **)&v16[8]);
    std::string::~string(v20);
    v11 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp", 92);
    if ( v11 )
      v12 = v11 + 1;
    else
      v12 = "admin\\appman\\appv\\client\\host\\common\\sessionimpl.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v12);
    v14 = *(unsigned int *)v16 | (FileId << 52) | 0x1D2E00000000LL;
  }
  std::wstring::~wstring((char **)&v18);
  return v14;
}

```

## disassembly

```asm
0x140051330  mov     rax, rsp
0x140051333  mov     [rax+18h], rbx
0x140051337  mov     [rax+20h], rdi
0x14005133b  push    rbp
0x14005133c  lea     rbp, [rax-5Fh]
0x140051340  sub     rsp, 100h
0x140051347  movaps  xmmword ptr [rax-18h], xmm6
0x14005134b  mov     rax, cs:__security_cookie
0x140051352  xor     rax, rsp
0x140051355  mov     [rbp+57h+var_20], rax
0x140051359  mov     rbx, rdx
0x14005135c  mov     rdi, rcx
0x14005135f  mov     rdx, [rcx+18h]
0x140051363  mov     rdx, [rdx]
0x140051366  lea     rcx, [rsp+100h+var_E0+8]
0x14005136b  call    ?getUserTokenSID@AppUtils@@SA?AV?$extended_string@_W@shared@softricity@@PEAX@Z; AppUtils::getUserTokenSID(void *)
0x140051370  movups  xmm0, xmmword ptr [rax]
0x140051373  movups  [rbp+57h+var_98], xmm0
0x140051377  movups  xmm6, xmmword ptr [rax+10h]
0x14005137b  movups  [rbp+57h+var_88], xmm6
0x14005137f  mov     qword ptr [rax+10h], 0
0x140051387  mov     qword ptr [rax+18h], 7
0x14005138f  xor     ecx, ecx
0x140051391  mov     [rax], cx
0x140051394  lea     rcx, [rsp+100h+var_E0+8]
0x140051399  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005139e  movq    rax, xmm6
0x1400513a3  test    rax, rax
0x1400513a6  jnz     loc_1400514E3
0x1400513ac  call    cs:__imp_GetLastError
0x1400513b2  mov     dword ptr [rsp+100h+var_E0], eax
0x1400513b6  lea     rdx, aAppvClientHost_15; "AppV::Client::Host::SessionImpl::GetUse"...
0x1400513bd  lea     rcx, [rbp+57h+var_78]
0x1400513c1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400513c6  mov     [rbp+57h+var_58], 0E7h
0x1400513cd  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x1400513d2  xorps   xmm0, xmm0
0x1400513d5  movups  [rsp+100h+var_E0+8], xmm0
0x1400513da  xorps   xmm1, xmm1
0x1400513dd  movdqu  [rbp+57h+var_C8], xmm1
0x1400513e2  mov     r8d, 51h ; 'Q'
0x1400513e8  lea     rdx, aUsermanagerFai_3; "UserManager failed to get the SID from "...
0x1400513ef  lea     rcx, [rsp+100h+var_E0+8]
0x1400513f4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400513f9  nop
0x1400513fa  lea     r8, [rsp+100h+var_E0+8]
0x1400513ff  lea     rdx, [rbp+57h+var_50]
0x140051403  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140051408  nop
0x140051409  lea     rdx, [rdi+10h]
0x14005140d  mov     rcx, rax
0x140051410  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140051415  lea     rdx, [rsp+100h+var_E0]
0x14005141a  mov     rcx, rax
0x14005141d  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140051422  mov     rbx, rax
0x140051425  xorps   xmm0, xmm0
0x140051428  movups  [rbp+57h+var_B8], xmm0
0x14005142c  xorps   xmm1, xmm1
0x14005142f  movdqu  [rbp+57h+var_A8], xmm1
0x140051434  mov     r8d, 6
0x14005143a  lea     rdx, aClient; "Client"
0x140051441  lea     rcx, [rbp+57h+var_B8]
0x140051445  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005144a  nop
0x14005144b  mov     r9, rbx
0x14005144e  lea     r8, [rbp+57h+var_B8]
0x140051452  mov     edx, 2
0x140051457  lea     rcx, [rbp+57h+var_78]
0x14005145b  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140051460  nop
0x140051461  lea     rcx, [rbp+57h+var_B8]
0x140051465  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005146a  nop
0x14005146b  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140051472  mov     [rbp+57h+var_50], rax
0x140051476  lea     rcx, [rbp+57h+var_40]
0x14005147a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005147f  nop
0x140051480  lea     rcx, [rsp+100h+var_E0+8]
0x140051485  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005148a  nop
0x14005148b  lea     rcx, [rbp+57h+var_78]
0x14005148f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140051494  mov     edx, 5Ch ; '\'; Ch
0x140051499  lea     rcx, aAdminAppmanApp_16; "admin\\appman\\appv\\client\\host\\comm"...
0x1400514a0  call    cs:__imp_strrchr
0x1400514a6  test    rax, rax
0x1400514a9  jz      short loc_1400514B0
0x1400514ab  inc     rax
0x1400514ae  jmp     short loc_1400514B7
0x1400514b0  lea     rax, aAdminAppmanApp_16; "admin\\appman\\appv\\client\\host\\comm"...
0x1400514b7  mov     rdx, rax; char *
0x1400514ba  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400514c1  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400514c6  mov     rbx, rax
0x1400514c9  shl     rbx, 34h
0x1400514cd  mov     ecx, dword ptr [rsp+100h+var_E0]
0x1400514d1  or      rbx, rcx
0x1400514d4  mov     rax, 1D2E00000000h
0x1400514de  or      rbx, rax
0x1400514e1  jmp     short loc_1400514F9
0x1400514e3  lea     rdx, [rbp+57h+var_98]
0x1400514e7  mov     rcx, rbx
0x1400514ea  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1400514ef  mov     rbx, 8000000000h
0x1400514f9  lea     rcx, [rbp+57h+var_98]
0x1400514fd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140051502  mov     rax, rbx
0x140051505  mov     rcx, [rbp+57h+var_20]
0x140051509  xor     rcx, rsp; StackCookie
0x14005150c  call    __security_check_cookie
0x140051511  lea     r11, [rsp+100h+var_s0]
0x140051519  mov     rbx, [r11+20h]
0x14005151d  mov     rdi, [r11+28h]
0x140051521  movaps  xmm6, xmmword ptr [r11-10h]
0x140051526  mov     rsp, r11
0x140051529  pop     rbp
0x14005152a  retn
```
