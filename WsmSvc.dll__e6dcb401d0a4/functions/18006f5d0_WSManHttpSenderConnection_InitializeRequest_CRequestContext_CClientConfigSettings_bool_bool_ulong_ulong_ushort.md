# WSManHttpSenderConnection::InitializeRequest(CRequestContext *,CClientConfigSettings *,bool,bool,ulong,ulong,ushort const *)

- ea: `0x18006f5d0`
- end: `0x18006f99a`
- name: `?InitializeRequest@WSManHttpSenderConnection@@EEAA_NPEAVCRequestContext@@PEAVCClientConfigSettings@@_N2KKPEBG@Z`
- size: `970`
- prototype: `bool __usercall@<al>(WSManHttpSenderConnection *__hidden this@<rcx>, struct CRequestContext *@<rdx>, struct CClientConfigSettings *@<r8>, bool@<r9b>, bool, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005d10`
- `0x180019950`
- `0x1800224f0`
- `0x18002c580`
- `0x180067150`
- `0x18006f5d0`
- `0x180071400`
- `0x180071468`
- `0x1800f9c40`
- `0x180112380`
- `0x1801123a8`
- `0x18013417c`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006f7af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006f7de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006f80d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006f7af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006f7de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006f80d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f87c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f87c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f894`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f61d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f61d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f75b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f75b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006f6d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006f6d2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006f6ec`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006f6ec`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18006f747`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18006f747`

## string_xrefs

- `0x18006f7cd`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`
- `0x18006f7fc`: `onecore\admin\wmi\wmx\binaries\service\cwsmancriticalsection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall WSManHttpSenderConnection::InitializeRequest(
        WSManHttpSenderConnection *this,
        struct CRequestContext *a2,
        struct CClientConfigSettings *a3,
        char a4,
        bool a5,
        unsigned int a6,
        unsigned int a7,
        const unsigned __int16 *a8)
{
  DWORD *v11; // rsi
  DWORD v12; // ecx
  int v13; // edx
  int v14; // r8d
  const unsigned __int16 *v15; // rbx
  signed __int32 v16; // eax
  __int64 v17; // rcx
  HANDLE CurrentThread; // rax
  bool v19; // r8
  void *v20; // rax
  bool v21; // bl
  void (__fastcall *v23)(struct CRequestContext *, _QWORD); // rbx
  DWORD LastError; // eax
  const unsigned __int16 *v25; // r8
  __int64 v26; // rdx
  unsigned int v27; // eax
  struct IRequestContext *v28; // [rsp+20h] [rbp-68h]
  char *v29; // [rsp+40h] [rbp-48h] BYREF
  int v30; // [rsp+48h] [rbp-40h]
  void *TokenHandle; // [rsp+90h] [rbp+8h] BYREF

  if ( a4 && (*(_BYTE *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 896LL) & 1) != 0 )
    *((_BYTE *)this + 11424) = 1;
  v11 = (DWORD *)((char *)this + 9184);
  v29 = (char *)this + 9184;
  v30 = 0;
  v12 = *((_DWORD *)this + 2296);
  if ( v12 )
  {
    SetLastError(v12);
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\cwsmancriticalsection.cpp",
      59,
      L"59",
      0x54Fu,
      0);
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 9192));
  }
  v15 = a8;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_qSqd(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v14, (_DWORD)this, (__int64)a8, *((_QWORD *)this + 1), a5);
  v16 = _InterlockedCompareExchange((volatile signed __int32 *)this + 2295, 1, 1);
  if ( v16 != 1 )
  {
    if ( (v16 & 0xFFFFFFFD) == 0 )
    {
      v25 = L"7761";
      v26 = 7761;
LABEL_36:
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", v26, v25, 0x54Fu, a2);
LABEL_31:
      InCritSecWithConditionVar::~InCritSecWithConditionVar((InCritSecWithConditionVar *)&v29);
      return 0;
    }
    if ( v16 != 3 )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\client\\remote\\wsmanhttpsender.cpp", 912, L"912", 0x54Fu, 0);
  }
  if ( !a3 )
  {
    v25 = L"7762";
    v26 = 7762;
    goto LABEL_36;
  }
  if ( a5 )
    WSManHttpSenderConnection::ResetNegotiationContext(this);
  if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_AN_SENDING_REQUEST) )
    WSMan::LogEvent<unsigned short const *,unsigned short const *,unsigned long>(
      v17,
      v15,
      *(const unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 536LL),
      *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 5) + 128LL) + 532LL));
  *((_DWORD *)this + 2267) = a7;
  *((_DWORD *)this + 2266) = a6;
  AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr((char *)this + 9104);
  *((_QWORD *)this + 1138) = a3;
  (**(void (__fastcall ***)(struct CClientConfigSettings *))a3)(a3);
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x10000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids);
  }
  AutoCleanup<AutoHandle,void *>::ReleasePtr((char *)this + 11416);
  v20 = TokenHandle;
  *((_QWORD *)this + 1427) = TokenHandle;
  if ( !v20 && GetLastError() != 1008 )
  {
    v23 = *(void (__fastcall **)(struct CRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL);
    LastError = GetLastError();
    v23(a2, LastError);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      v27 = (*(__int64 (__fastcall **)(struct CRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 421, &WPP_1a71944546983a3ae75b6cead512f96f_Traceguids, v27);
    }
    goto LABEL_31;
  }
  v21 = WSManHttpSenderConnection::InitializeRequestInternal(this, a2, v19, a5, (const unsigned __int16 *)v28);
  if ( *v11 )
  {
    SetLastError(*v11);
    WSManError(
      (wchar_t *)L"onecore\\admin\\wmi\\wmx\\binaries\\service\\cwsmancriticalsection.cpp",
      102,
      L"102",
      0x54Fu,
      0);
  }
  else
  {
    WakeAllConditionVariable((PCONDITION_VARIABLE)this + 1154);
  }
  if ( *v11 )
    SetLastError(*v11);
  else
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 9192));
  return v21;
}

```

## disassembly

```asm
0x18006f5d0  push    rbx
0x18006f5d2  push    rsi
0x18006f5d3  push    rdi
0x18006f5d4  push    r13
0x18006f5d6  push    r14
0x18006f5d8  push    r15
0x18006f5da  sub     rsp, 58h
0x18006f5de  mov     r15, r8
0x18006f5e1  mov     r14, rdx
0x18006f5e4  mov     rdi, rcx
0x18006f5e7  mov     ecx, 1
0x18006f5ec  test    r9b, r9b
0x18006f5ef  jnz     loc_18006F8C8
0x18006f5f5  lea     rsi, [rdi+23E0h]
0x18006f5fc  mov     [rsp+88h+var_48], rsi
0x18006f601  mov     [rsp+88h+var_40], 0
0x18006f609  mov     ecx, [rsi]; dwErrCode
0x18006f60b  mov     r13d, 54Fh
0x18006f611  test    ecx, ecx
0x18006f613  jnz     loc_18006F7AF
0x18006f619  lea     rcx, [rsi+8]; lpCriticalSection
0x18006f61d  call    cs:__imp_EnterCriticalSection
0x18006f623  nop
0x18006f624  lea     rax, WPP_GLOBAL_Control
0x18006f62b  mov     rbx, [rsp+88h+arg_38]
0x18006f633  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f63a  cmp     rcx, rax
0x18006f63d  jz      short loc_18006F64C
0x18006f63f  test    dword ptr [rcx+1Ch], 400h
0x18006f646  jnz     loc_18006F8EB
0x18006f64c  mov     ecx, 1
0x18006f651  mov     eax, ecx
0x18006f653  lock cmpxchg [rdi+23DCh], ecx
0x18006f65b  jnz     loc_18006F772
0x18006f661  test    r15, r15
0x18006f664  jz      loc_18006F924
0x18006f66a  cmp     [rsp+88h+arg_20], 0
0x18006f672  jnz     loc_18006F949
0x18006f678  lea     rcx, LOG_WSMAN_AN_SENDING_REQUEST; struct _EVENT_DESCRIPTOR *
0x18006f67f  call    ?IsEventEnabled@EventHandler@WSMan@@SA_NAEBU_EVENT_DESCRIPTOR@@@Z; WSMan::EventHandler::IsEventEnabled(_EVENT_DESCRIPTOR const &)
0x18006f684  test    al, al
0x18006f686  jnz     loc_18006F818
0x18006f68c  mov     eax, [rsp+88h+arg_30]
0x18006f693  mov     [rdi+236Ch], eax
0x18006f699  mov     eax, [rsp+88h+arg_28]
0x18006f6a0  mov     [rdi+2368h], eax
0x18006f6a6  lea     rbx, [rdi+2390h]
0x18006f6ad  mov     rcx, rbx
0x18006f6b0  call    ?ReleasePtr@?$AutoCleanup@V?$AutoRelease@VCServiceCommonConfigSettings@@@@PEAVCServiceCommonConfigSettings@@@@AEAAXXZ; AutoCleanup<AutoRelease<CServiceCommonConfigSettings>,CServiceCommonConfigSettings *>::ReleasePtr(void)
0x18006f6b5  mov     [rbx], r15
0x18006f6b8  mov     rax, [r15]
0x18006f6bb  mov     rcx, r15
0x18006f6be  mov     rax, [rax]
0x18006f6c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f6c6  mov     [rsp+88h+TokenHandle], 0
0x18006f6d2  call    cs:__imp_GetCurrentThread
0x18006f6d8  mov     rcx, rax; ThreadHandle
0x18006f6db  lea     r9, [rsp+88h+TokenHandle]; TokenHandle
0x18006f6e3  mov     edx, 4; DesiredAccess
0x18006f6e8  lea     r8d, [rdx-3]; OpenAsSelf
0x18006f6ec  call    cs:__imp_OpenThreadToken
0x18006f6f2  test    eax, eax
0x18006f6f4  jz      loc_18006F83E
0x18006f6fa  lea     r15, WPP_GLOBAL_Control
0x18006f701  lea     rbx, [rdi+2C98h]
0x18006f708  mov     rcx, rbx
0x18006f70b  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x18006f710  mov     rax, [rsp+88h+TokenHandle]
0x18006f718  mov     [rbx], rax
0x18006f71b  test    rax, rax
0x18006f71e  jz      loc_18006F87C
0x18006f724  mov     r9b, [rsp+88h+arg_20]; bool
0x18006f72c  mov     rdx, r14; struct CRequestContext *
0x18006f72f  mov     rcx, rdi; this
0x18006f732  call    ?InitializeRequestInternal@WSManHttpSenderConnection@@AEAA_NPEAVCRequestContext@@_N1PEBG@Z; WSManHttpSenderConnection::InitializeRequestInternal(CRequestContext *,bool,bool,ushort const *)
0x18006f737  mov     bl, al
0x18006f739  mov     ecx, [rsi]; dwErrCode
0x18006f73b  test    ecx, ecx
0x18006f73d  jnz     loc_18006F7DE
0x18006f743  lea     rcx, [rsi+30h]; ConditionVariable
0x18006f747  call    cs:__imp_WakeAllConditionVariable
0x18006f74d  mov     ecx, [rsi]; dwErrCode
0x18006f74f  test    ecx, ecx
0x18006f751  jnz     loc_18006F80D
0x18006f757  lea     rcx, [rsi+8]; lpCriticalSection
0x18006f75b  call    cs:__imp_LeaveCriticalSection
0x18006f761  nop
0x18006f762  mov     al, bl
0x18006f764  add     rsp, 58h
0x18006f768  pop     r15
0x18006f76a  pop     r14
0x18006f76c  pop     r13
0x18006f76e  pop     rdi
0x18006f76f  pop     rsi
0x18006f770  pop     rbx
0x18006f771  retn
0x18006f772  test    eax, 0FFFFFFFDh
0x18006f777  jz      loc_18006F916
0x18006f77d  cmp     eax, 3
0x18006f780  jz      loc_18006F661
0x18006f786  mov     [rsp+88h+var_68], 0; struct IRequestContext *
0x18006f78f  mov     r9d, r13d; unsigned int
0x18006f792  lea     r8, a912; "912"
0x18006f799  mov     edx, 390h; unsigned int
0x18006f79e  lea     rcx, aOnecoreAdminWm_105; "onecore\\admin\\wmi\\wmx\\client\\remot"...
0x18006f7a5  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18006f7aa  jmp     loc_18006F661
0x18006f7af  call    cs:__imp_SetLastError
0x18006f7b5  mov     [rsp+88h+var_68], 0; struct IRequestContext *
0x18006f7be  mov     r9d, r13d; unsigned int
0x18006f7c1  lea     r8, a59; "59"
0x18006f7c8  mov     edx, 3Bh ; ';'; unsigned int
0x18006f7cd  lea     rcx, aOnecoreAdminWm_164; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18006f7d4  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18006f7d9  jmp     loc_18006F624
0x18006f7de  call    cs:__imp_SetLastError
0x18006f7e4  mov     [rsp+88h+var_68], 0; struct IRequestContext *
0x18006f7ed  mov     r9d, r13d; unsigned int
0x18006f7f0  lea     r8, a102; "102"
0x18006f7f7  mov     edx, 66h ; 'f'; unsigned int
0x18006f7fc  lea     rcx, aOnecoreAdminWm_164; "onecore\\admin\\wmi\\wmx\\binaries\\ser"...
0x18006f803  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18006f808  jmp     loc_18006F74D
0x18006f80d  call    cs:__imp_SetLastError
0x18006f813  jmp     loc_18006F762
0x18006f818  mov     rax, [rdi+28h]
0x18006f81c  mov     r8, [rax+80h]
0x18006f823  mov     r9d, [r8+214h]
0x18006f82a  mov     r8, [r8+218h]
0x18006f831  mov     rdx, rbx
0x18006f834  call    ??$LogEvent@PEBGPEBGK@WSMan@@YAXAEBU_EVENT_DESCRIPTOR@@PEBG1K@Z; WSMan::LogEvent<ushort const *,ushort const *,ulong>(_EVENT_DESCRIPTOR const &,ushort const *,ushort const *,ulong)
0x18006f839  jmp     loc_18006F68C
0x18006f83e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f845  lea     r15, WPP_GLOBAL_Control
0x18006f84c  cmp     rcx, r15
0x18006f84f  jz      loc_18006F701
0x18006f855  test    dword ptr [rcx+1Ch], 10000000h
0x18006f85c  jz      loc_18006F701
0x18006f862  mov     edx, 12h
0x18006f867  lea     r8, WPP_5b789da118f632ad9796e014c1252c4d_Traceguids
0x18006f86e  mov     rcx, [rcx+10h]
0x18006f872  call    WPP_SF_
0x18006f877  jmp     loc_18006F701
0x18006f87c  call    cs:__imp_GetLastError
0x18006f882  cmp     eax, 3F0h
0x18006f887  jz      loc_18006F724
0x18006f88d  mov     rax, [r14]
0x18006f890  mov     rbx, [rax+48h]
0x18006f894  call    cs:__imp_GetLastError
0x18006f89a  mov     edx, eax
0x18006f89c  mov     rcx, r14
0x18006f89f  mov     rax, rbx
0x18006f8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f8a7  mov     rax, cs:WPP_GLOBAL_Control
0x18006f8ae  cmp     rax, r15
0x18006f8b1  jnz     loc_18006F956
0x18006f8b7  lea     rcx, [rsp+88h+var_48]; this
0x18006f8bc  call    ??1InCritSecWithConditionVar@@QEAA@XZ; InCritSecWithConditionVar::~InCritSecWithConditionVar(void)
0x18006f8c1  xor     al, al
0x18006f8c3  jmp     loc_18006F764
0x18006f8c8  mov     rax, [rdi+28h]
0x18006f8cc  mov     r9, [rax+80h]
0x18006f8d3  test    [r9+380h], cl
0x18006f8da  jz      loc_18006F5F5
0x18006f8e0  mov     [rdi+2CA0h], cl
0x18006f8e6  jmp     loc_18006F5F5
0x18006f8eb  movzx   eax, [rsp+88h+arg_20]
0x18006f8f3  mov     [rsp+88h+var_58], eax
0x18006f8f7  mov     rax, [rdi+8]
0x18006f8fb  mov     [rsp+88h+var_60], rax
0x18006f900  mov     [rsp+88h+var_68], rbx
0x18006f905  mov     r9, rdi
0x18006f908  mov     rcx, [rcx+10h]
0x18006f90c  call    WPP_SF_qSqd
0x18006f911  jmp     loc_18006F64C
0x18006f916  lea     r8, a7761; "7761"
0x18006f91d  mov     edx, 1E51h
0x18006f922  jmp     short loc_18006F930
0x18006f924  lea     r8, a7762; "7762"
0x18006f92b  mov     edx, 1E52h; unsigned int
0x18006f930  mov     r9d, r13d; unsigned int
0x18006f933  mov     [rsp+88h+var_68], r14; struct IRequestContext *
0x18006f938  lea     rcx, aOnecoreAdminWm_105; "onecore\\admin\\wmi\\wmx\\client\\remot"...
0x18006f93f  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18006f944  jmp     loc_18006F8B7
0x18006f949  mov     rcx, rdi; this
0x18006f94c  call    ?ResetNegotiationContext@WSManHttpSenderConnection@@AEAAXXZ; WSManHttpSenderConnection::ResetNegotiationContext(void)
0x18006f951  jmp     loc_18006F678
0x18006f956  test    dword ptr [rax+1Ch], 200h
0x18006f95d  jz      loc_18006F8B7
0x18006f963  mov     rax, [r14]
0x18006f966  mov     rcx, r14
0x18006f969  mov     rax, [rax+98h]
0x18006f970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f975  mov     edx, 1A5h
0x18006f97a  mov     r9d, eax
0x18006f97d  lea     r8, WPP_1a71944546983a3ae75b6cead512f96f_Traceguids
0x18006f984  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f98b  mov     rcx, [rcx+10h]
0x18006f98f  call    WPP_SF_d
0x18006f994  jmp     loc_18006F8B7
```
