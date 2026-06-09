# AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(void)

- ea: `0x1400233dc`
- end: `0x1400235dc`
- name: `?Deinitialize@APICaller@AppVClientImpl@Service@Client@AppV@@QEAAJXZ`
- size: `512`
- prototype: `__int64 __fastcall(AppV::Client::Service::AppVClientImpl::APICaller *__hidden this)`
- caller_count: `53`
- callee_count: `11`
- tags: `authz_impersonation, service_task`

## callers

- `0x1400200dc`
- `0x140021630`
- `0x140021840`
- `0x140022090`
- `0x140022890`
- `0x1400235f0`
- `0x1400237d0`
- `0x140023c60`
- `0x140024460`
- `0x1400249a0`
- `0x140024b60`
- `0x140025240`
- `0x140025370`
- `0x140025820`
- `0x140025be0`
- `0x1400260e0`
- `0x140026330`
- `0x140026540`
- `0x140026760`
- `0x140026980`
- `0x140026c00`
- `0x140026f30`
- `0x1400271d0`
- `0x140027500`
- `0x140027750`
- `0x140027930`
- `0x140028330`
- `0x140028520`
- `0x140028710`
- `0x140029570`
- `0x1400297d0`
- `0x140029a10`
- `0x140029d60`
- `0x140029fe0`
- `0x14002a300`
- `0x14002a974`
- `0x14002ac74`
- `0x14002b080`
- `0x14002b460`
- `0x14002be30`
- `0x1400353a0`
- `0x140035710`
- `0x140035c00`
- `0x140035ea0`
- `0x140036290`
- `0x140036df0`
- `0x140036f10`
- `0x140037710`
- `0x140037880`
- `0x140037b00`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x140010158`
- `0x1400233dc`
- `0x14003592c`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`

## import_xrefs

- `KERNEL32!SetEvent` at `0x140023470`
- `KERNEL32!SetEvent` at `0x140023470`
- `KERNEL32!GetLastError` at `0x14002347f`
- `KERNEL32!GetLastError` at `0x14002347f`
- `KERNEL32!GetCurrentThreadId` at `0x14002343e`
- `KERNEL32!GetCurrentThreadId` at `0x14002343e`
- `KERNEL32!LeaveCriticalSection` at `0x140023575`
- `KERNEL32!LeaveCriticalSection` at `0x140023575`
- `KERNEL32!EnterCriticalSection` at `0x140023425`
- `KERNEL32!EnterCriticalSection` at `0x140023425`
- `ole32!CoRevertToSelf` at `0x1400235af`
- `ole32!CoRevertToSelf` at `0x1400235af`

## string_xrefs

- `0x140023489`: `AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize(
        AppV::Client::Service::AppVClientImpl::APICaller *this)
{
  int v3; // ecx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rbx
  unsigned __int64 v8; // rax
  signed int v9; // ebx
  HRESULT v10; // eax
  DWORD LastError; // [rsp+20h] [rbp-89h] BYREF
  void **v12; // [rsp+28h] [rbp-81h]
  char v13; // [rsp+30h] [rbp-79h]
  struct _RTL_CRITICAL_SECTION *v14; // [rsp+38h] [rbp-71h]
  _OWORD v15[2]; // [rsp+40h] [rbp-69h] BYREF
  _OWORD v16[2]; // [rsp+60h] [rbp-49h] BYREF
  char *v17[4]; // [rsp+80h] [rbp-29h] BYREF
  int v18; // [rsp+A0h] [rbp-9h]
  void **v19; // [rsp+A8h] [rbp-1h] BYREF
  char *v20; // [rsp+B8h] [rbp+Fh] BYREF

  if ( !*(_BYTE *)this )
    return 0;
  v12 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
  v14 = &AppV::Client::Service::AppVClientImpl::APICaller::st_lock;
  EnterCriticalSection(&AppV::Client::Service::AppVClientImpl::APICaller::st_lock);
  v3 = qword_1400B0D68 + 1;
  LODWORD(qword_1400B0D68) = v3;
  if ( v3 == 1 )
  {
    HIDWORD(qword_1400B0D68) = GetCurrentThreadId();
    v3 = qword_1400B0D68;
  }
  v13 = 1;
  if ( !--AppV::Client::Service::AppVClientImpl::APICaller::st_activeCallers )
  {
    if ( !SetEvent(AppV::Client::Service::AppVClientImpl::APICaller::st_callersIdle) )
    {
      LastError = GetLastError();
      std::string::string(v17, "AppV::Client::Service::AppVClientImpl::APICaller::Deinitialize");
      v18 = 471;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v4);
      memset(v16, 0, sizeof(v16));
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)v16,
        L"Failed to reset idle API callers event, error = %1%",
        0x33u);
      v6 = AppV::Log::fmt(v5, &v19, v16);
      v7 = AppV::LogFormatter::operator%<unsigned long>(v6, (__int64)&LastError);
      memset(v15, 0, sizeof(v15));
      std::wstring::_Construct<1,wchar_t const *>((char **)v15, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v17, 8, (int)v15, v7);
      std::wstring::~wstring((char **)v15);
      v19 = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(&v20);
      std::wstring::~wstring((char **)v16);
      std::string::~string(v17);
    }
    v3 = qword_1400B0D68;
  }
  LODWORD(qword_1400B0D68) = v3 - 1;
  if ( v3 == 1 )
    qword_1400B0D68 = 0;
  LeaveCriticalSection(&AppV::Client::Service::AppVClientImpl::APICaller::st_lock);
  v13 = 0;
  v8 = AppV::Client::Service::AppVClientImpl::ReleaseUserSession();
  v9 = v8;
  if ( (v8 & 0x8000000000LL) == 0 )
  {
    if ( (v8 & 0x2000000000LL) != 0 && (_DWORD)v8 )
    {
      if ( (int)v8 <= 0 )
        goto LABEL_19;
    }
    else
    {
      LOWORD(v9) = 1359;
    }
    v9 = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_19;
  }
  v9 = 0;
LABEL_19:
  v10 = CoRevertToSelf();
  if ( v10 < 0 && v9 >= 0 )
    v9 = v10;
  *(_BYTE *)this = 0;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400233dc  push    rbp
0x1400233de  push    rbx
0x1400233df  push    rdi
0x1400233e0  push    r14
0x1400233e2  lea     rbp, [rsp-3Fh]
0x1400233e7  sub     rsp, 0E8h
0x1400233ee  mov     rax, cs:__security_cookie
0x1400233f5  xor     rax, rsp
0x1400233f8  mov     [rbp+57h+var_28], rax
0x1400233fc  mov     rdi, rcx
0x1400233ff  cmp     byte ptr [rcx], 0
0x140023402  jnz     short loc_14002340B
0x140023404  xor     eax, eax
0x140023406  jmp     loc_1400235C3
0x14002340b  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x140023412  mov     [rsp+100h+var_D8], rax
0x140023417  lea     r14, ?st_lock@APICaller@AppVClientImpl@Service@Client@AppV@@0Vcritical_section@shared@softricity@@A; softricity::shared::critical_section AppV::Client::Service::AppVClientImpl::APICaller::st_lock
0x14002341e  mov     [rbp+57h+var_C8], r14
0x140023422  mov     rcx, r14; lpCriticalSection
0x140023425  call    cs:__imp_EnterCriticalSection
0x14002342b  mov     ecx, dword ptr cs:qword_1400B0D68
0x140023431  inc     ecx
0x140023433  mov     dword ptr cs:qword_1400B0D68, ecx
0x140023439  cmp     ecx, 1
0x14002343c  jnz     short loc_140023450
0x14002343e  call    cs:__imp_GetCurrentThreadId
0x140023444  mov     dword ptr cs:qword_1400B0D68+4, eax
0x14002344a  mov     ecx, dword ptr cs:qword_1400B0D68
0x140023450  mov     [rbp+57h+var_D0], 1
0x140023454  mov     eax, cs:?st_activeCallers@APICaller@AppVClientImpl@Service@Client@AppV@@0KA; ulong AppV::Client::Service::AppVClientImpl::APICaller::st_activeCallers
0x14002345a  add     eax, 0FFFFFFFFh
0x14002345d  mov     cs:?st_activeCallers@APICaller@AppVClientImpl@Service@Client@AppV@@0KA, eax; ulong AppV::Client::Service::AppVClientImpl::APICaller::st_activeCallers
0x140023463  jnz     loc_14002355D
0x140023469  mov     rcx, cs:?st_callersIdle@APICaller@AppVClientImpl@Service@Client@AppV@@0Vevent@shared@softricity@@A; hEvent
0x140023470  call    cs:__imp_SetEvent
0x140023476  cmp     eax, 1
0x140023479  jz      loc_140023557
0x14002347f  call    cs:__imp_GetLastError
0x140023485  mov     [rsp+100h+var_E0], eax
0x140023489  lea     rdx, aAppvClientServ_45; "AppV::Client::Service::AppVClientImpl::"...
0x140023490  lea     rcx, [rbp+57h+var_80]
0x140023494  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140023499  mov     [rbp+57h+var_60], 1D7h
0x1400234a0  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x1400234a5  xorps   xmm0, xmm0
0x1400234a8  movups  [rbp+57h+var_A0], xmm0
0x1400234ac  xorps   xmm1, xmm1
0x1400234af  movdqu  [rbp+57h+var_90], xmm1
0x1400234b4  mov     r8d, 33h ; '3'
0x1400234ba  lea     rdx, aFailedToResetI; "Failed to reset idle API callers event,"...
0x1400234c1  lea     rcx, [rbp+57h+var_A0]
0x1400234c5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400234ca  nop
0x1400234cb  lea     r8, [rbp+57h+var_A0]
0x1400234cf  lea     rdx, [rbp+57h+var_58]
0x1400234d3  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x1400234d8  nop
0x1400234d9  lea     rdx, [rsp+100h+var_E0]
0x1400234de  mov     rcx, rax
0x1400234e1  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x1400234e6  mov     rbx, rax
0x1400234e9  xorps   xmm0, xmm0
0x1400234ec  movups  [rbp+57h+var_C0], xmm0
0x1400234f0  xorps   xmm1, xmm1
0x1400234f3  movdqu  [rbp+57h+var_B0], xmm1
0x1400234f8  mov     r8d, 6
0x1400234fe  lea     rdx, aClient; "Client"
0x140023505  lea     rcx, [rbp+57h+var_C0]
0x140023509  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14002350e  nop
0x14002350f  mov     r9, rbx
0x140023512  lea     r8, [rbp+57h+var_C0]
0x140023516  mov     edx, 8
0x14002351b  lea     rcx, [rbp+57h+var_80]
0x14002351f  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140023524  nop
0x140023525  lea     rcx, [rbp+57h+var_C0]
0x140023529  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002352e  nop
0x14002352f  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140023536  mov     [rbp+57h+var_58], rax
0x14002353a  lea     rcx, [rbp+57h+var_48]
0x14002353e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140023543  nop
0x140023544  lea     rcx, [rbp+57h+var_A0]
0x140023548  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002354d  nop
0x14002354e  lea     rcx, [rbp+57h+var_80]
0x140023552  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140023557  mov     ecx, dword ptr cs:qword_1400B0D68
0x14002355d  sub     ecx, 1
0x140023560  mov     dword ptr cs:qword_1400B0D68, ecx
0x140023566  jnz     short loc_140023572
0x140023568  mov     dword ptr cs:qword_1400B0D68+4, 0
0x140023572  mov     rcx, r14; lpCriticalSection
0x140023575  call    cs:__imp_LeaveCriticalSection
0x14002357b  mov     [rbp+57h+var_D0], 0
0x14002357f  call    ?ReleaseUserSession@AppVClientImpl@Service@Client@AppV@@CA_KXZ; AppV::Client::Service::AppVClientImpl::ReleaseUserSession(void)
0x140023584  mov     rbx, rax
0x140023587  bt      rax, 27h ; '''
0x14002358c  jnb     short loc_140023592
0x14002358e  xor     ebx, ebx
0x140023590  jmp     short loc_1400235AF
0x140023592  bt      rax, 25h ; '%'
0x140023597  jnb     short loc_1400235A1
0x140023599  test    eax, eax
0x14002359b  jz      short loc_1400235A1
0x14002359d  jle     short loc_1400235AF
0x14002359f  jmp     short loc_1400235A6
0x1400235a1  mov     ebx, 54Fh
0x1400235a6  movzx   ebx, bx
0x1400235a9  or      ebx, 80070000h
0x1400235af  call    cs:__imp_CoRevertToSelf
0x1400235b5  test    eax, eax
0x1400235b7  jns     short loc_1400235BE
0x1400235b9  test    ebx, ebx
0x1400235bb  cmovns  ebx, eax
0x1400235be  mov     byte ptr [rdi], 0
0x1400235c1  mov     eax, ebx
0x1400235c3  mov     rcx, [rbp+57h+var_28]
0x1400235c7  xor     rcx, rsp; StackCookie
0x1400235ca  call    __security_check_cookie
0x1400235cf  add     rsp, 0E8h
0x1400235d6  pop     r14
0x1400235d8  pop     rdi
0x1400235d9  pop     rbx
0x1400235da  pop     rbp
0x1400235db  retn
```
