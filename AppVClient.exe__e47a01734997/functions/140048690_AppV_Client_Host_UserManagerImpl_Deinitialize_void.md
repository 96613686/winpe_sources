# AppV::Client::Host::UserManagerImpl::Deinitialize(void)

- ea: `0x140048690`
- end: `0x140048bb4`
- name: `?Deinitialize@UserManagerImpl@Host@Client@AppV@@UEAA_KXZ`
- size: `1316`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Host::UserManagerImpl *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140008e64`
- `0x14001624c`
- `0x140018bec`
- `0x14003c034`
- `0x14003c258`
- `0x140048690`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400486e8`
- `KERNEL32!GetCurrentThreadId` at `0x140048995`
- `KERNEL32!GetCurrentThreadId` at `0x140048a80`
- `KERNEL32!GetCurrentThreadId` at `0x1400486e8`
- `KERNEL32!GetCurrentThreadId` at `0x140048995`
- `KERNEL32!GetCurrentThreadId` at `0x140048a80`
- `KERNEL32!LeaveCriticalSection` at `0x1400487f1`
- `KERNEL32!LeaveCriticalSection` at `0x140048819`
- `KERNEL32!LeaveCriticalSection` at `0x140048a61`
- `KERNEL32!LeaveCriticalSection` at `0x140048b89`
- `KERNEL32!LeaveCriticalSection` at `0x1400487f1`
- `KERNEL32!LeaveCriticalSection` at `0x140048819`
- `KERNEL32!LeaveCriticalSection` at `0x140048a61`
- `KERNEL32!LeaveCriticalSection` at `0x140048b89`
- `KERNEL32!EnterCriticalSection` at `0x1400486d2`
- `KERNEL32!EnterCriticalSection` at `0x140048985`
- `KERNEL32!EnterCriticalSection` at `0x140048a6f`
- `KERNEL32!EnterCriticalSection` at `0x1400486d2`
- `KERNEL32!EnterCriticalSection` at `0x140048985`
- `KERNEL32!EnterCriticalSection` at `0x140048a6f`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x1400488cd`
- `KERNEL32!CloseThreadpoolCleanupGroupMembers` at `0x1400488cd`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400487a5`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400487a5`

## string_xrefs

- `0x14004879e`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x1400487b7`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x140048850`: `UserManager deinitializing, waiting for asynchronous work items to complete...`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
unsigned __int64 __fastcall AppV::Client::Host::UserManagerImpl::Deinitialize(struct _RTL_CRITICAL_SECTION *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  char *v3; // rax
  const char *v4; // rax
  unsigned __int64 v5; // rbx
  bool v6; // zf
  LONG *p_LockCount; // rdi
  __int64 *v9; // rbx
  __int64 v10; // r13
  _QWORD *v11; // r12
  __int64 v12; // rax
  __int64 **v13; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  volatile signed __int32 *SpinCount; // rbx
  __int128 v17; // [rsp+48h] [rbp-81h] BYREF
  __int128 v18; // [rsp+58h] [rbp-71h]
  __int128 v19; // [rsp+68h] [rbp-61h] BYREF
  __int128 v20; // [rsp+78h] [rbp-51h]
  _OWORD v21[2]; // [rsp+88h] [rbp-41h] BYREF
  int v22; // [rsp+A8h] [rbp-21h]
  char *v23[4]; // [rsp+B0h] [rbp-19h] BYREF
  int v24; // [rsp+D0h] [rbp+7h]

  v2 = this + 1;
  EnterCriticalSection(this + 1);
  if ( ++LODWORD(v2[1].DebugInfo) == 1 )
    HIDWORD(v2[1].DebugInfo) = GetCurrentThreadId();
  if ( this[2].LockCount == 1 )
  {
    this[2].LockCount = 2;
    v6 = LODWORD(v2[1].DebugInfo)-- == 1;
    if ( v6 )
      HIDWORD(v2[1].DebugInfo) = 0;
    LeaveCriticalSection(v2);
    std::string::string(v21, "AppV::Client::Host::UserManagerImpl::Deinitialize");
    v22 = 311;
    v19 = 0;
    v20 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v19,
      L"UserManager deinitializing, waiting for asynchronous work items to complete...",
      0x4Eu);
    v17 = 0;
    v18 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v17, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v21, 4, (int)&v17, (__int64)&v19);
    std::wstring::~wstring((char **)&v17);
    std::wstring::~wstring((char **)&v19);
    std::string::~string((char **)v21);
    CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)this[2].LockSemaphore + 10), 1, 0);
    std::string::string(v21, "AppV::Client::Host::UserManagerImpl::Deinitialize");
    v22 = 317;
    v19 = 0;
    v20 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v19,
      L"UserManager deinitializing, simulating logoff for active user sessions...",
      0x49u);
    v17 = 0;
    v18 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v17, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v21, 4, (int)&v17, (__int64)&v19);
    std::wstring::~wstring((char **)&v17);
    std::wstring::~wstring((char **)&v19);
    std::string::~string((char **)v21);
    *(_QWORD *)&v19 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
    *(_QWORD *)&v20 = this + 3;
    EnterCriticalSection(this + 3);
    if ( ++LODWORD(this[4].DebugInfo) == 1 )
      HIDWORD(this[4].DebugInfo) = GetCurrentThreadId();
    BYTE8(v19) = 1;
    p_LockCount = &this[4].LockCount;
    v9 = **(__int64 ***)&this[4].LockCount;
    v10 = 0x8000000000LL;
    while ( 1 )
    {
      v11 = *(_QWORD **)p_LockCount;
      if ( v9 == *(__int64 **)p_LockCount )
        break;
      v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9[5] + 16LL))(v9[5]);
      if ( (v12 & 0x8000000000LL) == 0 && (v10 & 0x8000000000LL) != 0 )
        v10 = v12;
      v13 = (__int64 **)v9[2];
      if ( *((_BYTE *)v13 + 25) )
      {
        for ( i = (__int64 *)v9[1]; !*((_BYTE *)i + 25) && v9 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v9 = i;
        v9 = i;
      }
      else
      {
        v9 = (__int64 *)v9[2];
        for ( j = *v13; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v9 = j;
      }
    }
    std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>,void *>>>(
      &this[4].LockCount,
      &this[4].LockCount,
      v11[1]);
    v11[1] = v11;
    *v11 = v11;
    v11[2] = v11;
    this[4].OwningThread = 0;
    v6 = LODWORD(this[4].DebugInfo)-- == 1;
    if ( v6 )
      HIDWORD(this[4].DebugInfo) = 0;
    LeaveCriticalSection(this + 3);
    BYTE8(v19) = 0;
    EnterCriticalSection(this + 1);
    if ( ++LODWORD(this[2].DebugInfo) == 1 )
      HIDWORD(this[2].DebugInfo) = GetCurrentThreadId();
    this[2].LockSemaphore = 0;
    SpinCount = (volatile signed __int32 *)this[2].SpinCount;
    this[2].SpinCount = 0;
    if ( SpinCount )
    {
      if ( _InterlockedExchangeAdd(SpinCount + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))SpinCount)(SpinCount);
        if ( _InterlockedExchangeAdd(SpinCount + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)SpinCount + 8LL))(SpinCount);
      }
    }
    this[2].OwningThread = 0;
    this[2].LockCount = 0;
    std::string::string(v23, "AppV::Client::Host::UserManagerImpl::Deinitialize");
    v24 = 344;
    memset(v21, 0, sizeof(v21));
    std::wstring::_Construct<1,wchar_t const *>((char **)v21, L"UserManager deinitialized", 0x19u);
    v17 = 0;
    v18 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v17, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v23, 4, (int)&v17, (__int64)v21);
    std::wstring::~wstring((char **)&v17);
    std::wstring::~wstring((char **)v21);
    std::string::~string(v23);
    v6 = LODWORD(this[2].DebugInfo)-- == 1;
    if ( v6 )
      HIDWORD(this[2].DebugInfo) = 0;
    LeaveCriticalSection(this + 1);
    return v10;
  }
  else
  {
    std::string::string(v21, "AppV::Client::Host::UserManagerImpl::Deinitialize");
    v22 = 300;
    v17 = 0;
    v18 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v17,
      L"UserManager recevied an operational request when not initialized",
      0x40u);
    v19 = 0;
    v20 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v19, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v21, 1, (int)&v19, (__int64)&v17);
    std::wstring::~wstring((char **)&v19);
    std::wstring::~wstring((char **)&v17);
    std::string::~string((char **)v21);
    v3 = strrchr("admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp", 92);
    if ( v3 )
      v4 = v3 + 1;
    else
      v4 = "admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp";
    v5 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v4) << 52)
       | 0x250E00000302LL;
    v6 = LODWORD(v2[1].DebugInfo)-- == 1;
    if ( v6 )
      HIDWORD(v2[1].DebugInfo) = 0;
    LeaveCriticalSection(v2);
    return v5;
  }
}

```

## disassembly

```asm
0x140048690  push    rbp
0x140048692  push    rbx
0x140048693  push    rsi
0x140048694  push    rdi
0x140048695  push    r12
0x140048697  push    r13
0x140048699  push    r14
0x14004869b  push    r15
0x14004869d  lea     rbp, [rsp-1Fh]
0x1400486a2  sub     rsp, 0E8h
0x1400486a9  mov     rax, cs:__security_cookie
0x1400486b0  xor     rax, rsp
0x1400486b3  mov     [rbp+57h+var_48], rax
0x1400486b7  mov     r14, rcx
0x1400486ba  lea     r13, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x1400486c1  mov     [rsp+120h+var_F0], r13
0x1400486c6  lea     rdi, [rcx+28h]
0x1400486ca  mov     [rsp+120h+var_E0], rdi
0x1400486cf  mov     rcx, rdi; lpCriticalSection
0x1400486d2  call    cs:__imp_EnterCriticalSection
0x1400486d8  mov     r12d, 1
0x1400486de  add     [rdi+28h], r12d
0x1400486e2  cmp     [rdi+28h], r12d
0x1400486e6  jnz     short loc_1400486F1
0x1400486e8  call    cs:__imp_GetCurrentThreadId
0x1400486ee  mov     [rdi+2Ch], eax
0x1400486f1  mov     [rsp+120h+var_E8], r12b
0x1400486f6  cmp     [r14+58h], r12d
0x1400486fa  jz      loc_1400487FF
0x140048700  lea     rdx, aAppvClientHost_12; "AppV::Client::Host::UserManagerImpl::De"...
0x140048707  lea     rcx, [rbp+57h+var_98]
0x14004870b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140048710  mov     [rbp+57h+var_78], 12Ch
0x140048717  xorps   xmm0, xmm0
0x14004871a  movups  [rsp+120h+var_D8], xmm0
0x14004871f  xorps   xmm1, xmm1
0x140048722  movdqu  [rbp+57h+var_C8], xmm1
0x140048727  mov     r8d, 40h ; '@'
0x14004872d  lea     rdx, aUsermanagerRec; "UserManager recevied an operational req"...
0x140048734  lea     rcx, [rsp+120h+var_D8]
0x140048739  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004873e  nop
0x14004873f  xorps   xmm0, xmm0
0x140048742  movups  [rbp+57h+var_B8], xmm0
0x140048746  xorps   xmm1, xmm1
0x140048749  movdqu  [rbp+57h+var_A8], xmm1
0x14004874e  mov     r8d, 6
0x140048754  lea     rdx, aClient; "Client"
0x14004875b  lea     rcx, [rbp+57h+var_B8]
0x14004875f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140048764  nop
0x140048765  lea     r9, [rsp+120h+var_D8]
0x14004876a  lea     r8, [rbp+57h+var_B8]
0x14004876e  mov     edx, r12d
0x140048771  lea     rcx, [rbp+57h+var_98]
0x140048775  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x14004877a  nop
0x14004877b  lea     rcx, [rbp+57h+var_B8]
0x14004877f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140048784  nop
0x140048785  lea     rcx, [rsp+120h+var_D8]
0x14004878a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004878f  nop
0x140048790  lea     rcx, [rbp+57h+var_98]
0x140048794  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140048799  mov     edx, 5Ch ; '\'; Ch
0x14004879e  lea     rcx, aAdminAppmanApp_17; "admin\\appman\\appv\\client\\host\\comm"...
0x1400487a5  call    cs:__imp_strrchr
0x1400487ab  xor     esi, esi
0x1400487ad  test    rax, rax
0x1400487b0  jz      short loc_1400487B7
0x1400487b2  add     rax, r12
0x1400487b5  jmp     short loc_1400487BE
0x1400487b7  lea     rax, aAdminAppmanApp_17; "admin\\appman\\appv\\client\\host\\comm"...
0x1400487be  mov     rdx, rax; char *
0x1400487c1  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x1400487c8  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400487cd  mov     rbx, rax
0x1400487d0  shl     rbx, 34h
0x1400487d4  mov     rax, 250E00000302h
0x1400487de  or      rbx, rax
0x1400487e1  or      r15d, 0FFFFFFFFh
0x1400487e5  add     [rdi+28h], r15d
0x1400487e9  jnz     short loc_1400487EE
0x1400487eb  mov     [rdi+2Ch], esi
0x1400487ee  mov     rcx, rdi; lpCriticalSection
0x1400487f1  call    cs:__imp_LeaveCriticalSection
0x1400487f7  mov     rax, rbx
0x1400487fa  jmp     loc_140048B94
0x1400487ff  mov     dword ptr [r14+58h], 2
0x140048807  xor     esi, esi
0x140048809  or      r15d, 0FFFFFFFFh
0x14004880d  add     [rdi+28h], r15d
0x140048811  jnz     short loc_140048816
0x140048813  mov     [rdi+2Ch], esi
0x140048816  mov     rcx, rdi; lpCriticalSection
0x140048819  call    cs:__imp_LeaveCriticalSection
0x14004881f  mov     [rsp+120h+var_E8], sil
0x140048824  lea     rdx, aAppvClientHost_12; "AppV::Client::Host::UserManagerImpl::De"...
0x14004882b  lea     rcx, [rbp+57h+var_98]
0x14004882f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140048834  mov     [rbp+57h+var_78], 137h
0x14004883b  xorps   xmm0, xmm0
0x14004883e  movups  [rbp+57h+var_B8], xmm0
0x140048842  xorps   xmm1, xmm1
0x140048845  movdqu  [rbp+57h+var_A8], xmm1
0x14004884a  mov     r8d, 4Eh ; 'N'
0x140048850  lea     rdx, aUsermanagerDei; "UserManager deinitializing, waiting for"...
0x140048857  lea     rcx, [rbp+57h+var_B8]
0x14004885b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140048860  nop
0x140048861  xorps   xmm0, xmm0
0x140048864  movups  [rsp+120h+var_D8], xmm0
0x140048869  xorps   xmm1, xmm1
0x14004886c  movdqu  [rbp+57h+var_C8], xmm1
0x140048871  mov     ebx, 6
0x140048876  mov     r8d, ebx
0x140048879  lea     rdx, aClient; "Client"
0x140048880  lea     rcx, [rsp+120h+var_D8]
0x140048885  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004888a  nop
0x14004888b  lea     r9, [rbp+57h+var_B8]
0x14004888f  lea     r8, [rsp+120h+var_D8]
0x140048894  lea     edx, [rbx-2]
0x140048897  lea     rcx, [rbp+57h+var_98]
0x14004889b  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x1400488a0  nop
0x1400488a1  lea     rcx, [rsp+120h+var_D8]
0x1400488a6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400488ab  nop
0x1400488ac  lea     rcx, [rbp+57h+var_B8]
0x1400488b0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400488b5  nop
0x1400488b6  lea     rcx, [rbp+57h+var_98]
0x1400488ba  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400488bf  mov     rcx, [r14+68h]
0x1400488c3  xor     r8d, r8d; pvCleanupContext
0x1400488c6  mov     edx, r12d; fCancelPendingCallbacks
0x1400488c9  mov     rcx, [rcx+50h]; ptpcg
0x1400488cd  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1400488d3  lea     rdx, aAppvClientHost_12; "AppV::Client::Host::UserManagerImpl::De"...
0x1400488da  lea     rcx, [rbp+57h+var_98]
0x1400488de  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400488e3  mov     [rbp+57h+var_78], 13Dh
0x1400488ea  xorps   xmm0, xmm0
0x1400488ed  movups  [rbp+57h+var_B8], xmm0
0x1400488f1  xorps   xmm1, xmm1
0x1400488f4  movdqu  [rbp+57h+var_A8], xmm1
0x1400488f9  lea     r8d, [rbx+43h]
0x1400488fd  lea     rdx, aUsermanagerDei_0; "UserManager deinitializing, simulating "...
0x140048904  lea     rcx, [rbp+57h+var_B8]
0x140048908  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004890d  nop
0x14004890e  xorps   xmm0, xmm0
0x140048911  movups  [rsp+120h+var_D8], xmm0
0x140048916  xorps   xmm1, xmm1
0x140048919  movdqu  [rbp+57h+var_C8], xmm1
0x14004891e  mov     r8d, ebx
0x140048921  lea     rdx, aClient; "Client"
0x140048928  lea     rcx, [rsp+120h+var_D8]
0x14004892d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140048932  nop
0x140048933  lea     r9, [rbp+57h+var_B8]
0x140048937  lea     r8, [rsp+120h+var_D8]
0x14004893c  lea     edx, [rbx-2]
0x14004893f  lea     rcx, [rbp+57h+var_98]
0x140048943  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,std::wstring const &)
0x140048948  nop
0x140048949  lea     rcx, [rsp+120h+var_D8]
0x14004894e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140048953  nop
0x140048954  lea     rcx, [rbp+57h+var_B8]
0x140048958  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004895d  nop
0x14004895e  lea     rcx, [rbp+57h+var_98]
0x140048962  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140048967  mov     rax, 8000000000h
0x140048971  mov     [rsp+120h+var_F8], rax
0x140048976  mov     qword ptr [rbp+57h+var_B8], r13
0x14004897a  lea     r13, [r14+78h]
0x14004897e  mov     qword ptr [rbp+57h+var_A8], r13
0x140048982  mov     rcx, r13; lpCriticalSection
0x140048985  call    cs:__imp_EnterCriticalSection
0x14004898b  add     [r13+28h], r12d
0x14004898f  cmp     [r13+28h], r12d
0x140048993  jnz     short loc_14004899F
0x140048995  call    cs:__imp_GetCurrentThreadId
0x14004899b  mov     [r13+2Ch], eax
0x14004899f  mov     byte ptr [rbp+57h+var_B8+8], r12b
0x1400489a3  lea     rdi, [r14+0A8h]
0x1400489aa  mov     rbx, [rdi]
0x1400489ad  mov     rbx, [rbx]
0x1400489b0  mov     r13, [rsp+120h+var_F8]
0x1400489b5  mov     r12, [rdi]
0x1400489b8  cmp     rbx, r12
0x1400489bb  jz      short loc_140048A22
0x1400489bd  mov     rcx, [rbx+28h]
0x1400489c1  mov     rax, [rcx]
0x1400489c4  mov     rax, [rax+10h]
0x1400489c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400489cd  bt      rax, 27h ; '''
0x1400489d2  jb      short loc_1400489DD
0x1400489d4  bt      r13, 27h ; '''
0x1400489d9  cmovb   r13, rax
0x1400489dd  mov     rcx, [rbx+10h]
0x1400489e1  cmp     [rcx+19h], sil
0x1400489e5  jz      short loc_140048A05
0x1400489e7  mov     rax, [rbx+8]
0x1400489eb  jmp     short loc_1400489FA
0x1400489ed  cmp     rbx, [rax+10h]
0x1400489f1  jnz     short loc_140048A00
0x1400489f3  mov     rbx, rax
0x1400489f6  mov     rax, [rax+8]
0x1400489fa  cmp     [rax+19h], sil
0x1400489fe  jz      short loc_1400489ED
0x140048a00  mov     rbx, rax
0x140048a03  jmp     short loc_1400489B5
0x140048a05  mov     rbx, rcx
0x140048a08  mov     rcx, [rcx]
0x140048a0b  cmp     [rcx+19h], sil
0x140048a0f  jnz     short loc_1400489B5
0x140048a11  mov     rbx, rcx
0x140048a14  mov     rax, [rcx]
0x140048a17  mov     rcx, rax
0x140048a1a  cmp     [rax+19h], sil
0x140048a1e  jz      short loc_140048A11
0x140048a20  jmp     short loc_1400489B5
0x140048a22  mov     [rsp+120h+var_F8], r13
0x140048a27  mov     r8, [r12+8]
0x140048a2c  mov     rdx, rdi
0x140048a2f  mov     rcx, rdi
0x140048a32  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEAUIAppVClientEventSink@@V?$shared_ptr@V?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>,void *>> &,std::_Tree_node<std::pair<IAppVClientEventSink * const,std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>>>,void *> *)
0x140048a37  mov     [r12+8], r12
0x140048a3c  mov     [r12], r12
0x140048a40  mov     [r12+10h], r12
0x140048a45  mov     [rdi+8], rsi
0x140048a49  or      r15d, 0FFFFFFFFh
0x140048a4d  add     [r14+0A0h], r15d
0x140048a54  jnz     short loc_140048A5D
0x140048a56  mov     [r14+0A4h], esi
0x140048a5d  lea     rcx, [r14+78h]; lpCriticalSection
0x140048a61  call    cs:__imp_LeaveCriticalSection
0x140048a67  mov     byte ptr [rbp+57h+var_B8+8], sil
0x140048a6b  lea     rcx, [r14+28h]; lpCriticalSection
0x140048a6f  call    cs:__imp_EnterCriticalSection
0x140048a75  inc     dword ptr [r14+50h]
0x140048a79  cmp     dword ptr [r14+50h], 1
0x140048a7e  jnz     short loc_140048A8A
0x140048a80  call    cs:__imp_GetCurrentThreadId
0x140048a86  mov     [r14+54h], eax
0x140048a8a  mov     [rsp+120h+var_E8], 1
0x140048a8f  mov     [r14+68h], rsi
0x140048a93  mov     rbx, [r14+70h]
0x140048a97  mov     [r14+70h], rsi
0x140048a9b  test    rbx, rbx
0x140048a9e  jz      short loc_140048AD7
0x140048aa0  mov     eax, r15d
0x140048aa3  lock xadd [rbx+8], eax
0x140048aa8  add     eax, r15d
0x140048aab  jnz     short loc_140048AD7
0x140048aad  mov     rax, [rbx]
0x140048ab0  mov     rcx, rbx
0x140048ab3  mov     rax, [rax]
0x140048ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048abb  mov     eax, r15d
0x140048abe  lock xadd [rbx+0Ch], eax
0x140048ac3  add     eax, r15d
0x140048ac6  jnz     short loc_140048AD7
0x140048ac8  mov     rax, [rbx]
0x140048acb  mov     rcx, rbx
0x140048ace  mov     rax, [rax+8]
0x140048ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048ad7  mov     [r14+60h], rsi
0x140048adb  mov     [r14+58h], esi
0x140048adf  lea     rdx, aAppvClientHost_12; "AppV::Client::Host::UserManagerImpl::De"...
0x140048ae6  lea     rcx, [rbp+57h+var_70]
0x140048aea  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140048aef  mov     [rbp+57h+var_50], 158h
0x140048af6  xorps   xmm0, xmm0
0x140048af9  movups  [rbp+57h+var_98], xmm0
0x140048afd  xorps   xmm1, xmm1
0x140048b00  movdqu  [rbp+57h+var_88], xmm1
0x140048b05  mov     r8d, 19h
0x140048b0b  lea     rdx, aUsermanagerDei_1; "UserManager deinitialized"
0x140048b12  lea     rcx, [rbp+57h+var_98]
0x140048b16  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140048b1b  nop
0x140048b1c  xorps   xmm0, xmm0
0x140048b1f  movups  [rsp+120h+var_D8], xmm0
0x140048b24  xorps   xmm1, xmm1
0x140048b27  movdqu  [rbp+57h+var_C8], xmm1
0x140048b2c  mov     r8d, 6
0x140048b32  lea     rdx, aClient; "Client"
0x140048b39  lea     rcx, [rsp+120h+var_D8]
0x140048b3e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140048b43  nop
0x140048b44  lea     r9, [rbp+57h+var_98]
0x140048b48  lea     r8, [rsp+120h+var_D8]
0x140048b4d  mov     edx, 4
0x140048b52  lea     rcx, [rbp+57h+var_70]
  ... truncated ...
```
