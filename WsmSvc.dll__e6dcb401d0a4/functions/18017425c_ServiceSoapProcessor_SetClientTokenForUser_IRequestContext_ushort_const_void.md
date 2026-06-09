# ServiceSoapProcessor::SetClientTokenForUser(IRequestContext *,ushort const *,void * *)

- ea: `0x18017425c`
- end: `0x18017462c`
- name: `?SetClientTokenForUser@ServiceSoapProcessor@@AEAA_NPEAVIRequestContext@@PEBGPEAPEAX@Z`
- size: `976`
- prototype: `char __fastcall(ServiceSoapProcessor *this, struct IRequestContext *, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008ee30`

## callees

- `0x180005d10`
- `0x180008920`
- `0x180010490`
- `0x1800120b0`
- `0x1800121d0`
- `0x180071400`
- `0x1800973c0`
- `0x1800d6d60`
- `0x180102b8c`
- `0x180104c24`
- `0x180112380`
- `0x1801123a8`
- `0x180172d34`
- `0x180173d00`
- `0x180173e74`
- `0x18017425c`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017435b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180174496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017435b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180174496`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180174351`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18017448c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180174351`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18017448c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801744f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801744f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801743ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801743ed`

## string_xrefs

- `0x1801742d1`: `onecore\admin\wmi\wmx\service\servicesoapprocessor.cpp`
- `0x1801745b2`: `onecore\admin\wmi\wmx\service\servicesoapprocessor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall ServiceSoapProcessor::SetClientTokenForUser(
        ServiceSoapProcessor *this,
        struct IRequestContext *a2,
        const unsigned __int16 *a3,
        void **a4)
{
  HANDLE v9; // rcx
  DWORD LastError; // eax
  DWORD v11; // ebx
  unsigned int v12; // eax
  struct _FILETIME v13; // rbx
  HANDLE *v14; // r14
  DWORD v15; // eax
  DWORD v16; // ebx
  unsigned int v17; // eax
  char v18; // bl
  ServiceSoapProcessor::TokenCacheMapping *v19; // rax
  void *v20; // rax
  __int64 v21; // [rsp+30h] [rbp-30h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v23[2]; // [rsp+40h] [rbp-20h] BYREF
  char *v24; // [rsp+50h] [rbp-10h] BYREF
  char v25; // [rsp+58h] [rbp-8h]
  void *phNewToken; // [rsp+98h] [rbp+38h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_b6d3b38d29aa3441062213be2537783f_Traceguids);
  if ( !a2 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\servicesoapprocessor.cpp", 0x562u, L"1378", 0x54Fu, 0);
    return 0;
  }
  if ( !a3 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\servicesoapprocessor.cpp", 0x563u, L"1379", 0x54Fu, a2);
    return 0;
  }
  if ( !a4 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\servicesoapprocessor.cpp", 0x564u, L"1380", 0x54Fu, a2);
    return 0;
  }
  v9 = *a4;
  if ( !*a4 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\servicesoapprocessor.cpp", 0x565u, L"1381", 0x54Fu, a2);
    return 0;
  }
  phNewToken = 0;
  if ( !DuplicateTokenEx(v9, 0, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_b6d3b38d29aa3441062213be2537783f_Traceguids, LastError);
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v11);
    goto LABEL_18;
  }
  v21 = 0;
  v12 = ServiceSoapProcessor::TokenCacheKey::Initialize((ServiceSoapProcessor::TokenCacheKey *)&v21, a3);
  if ( v12 )
  {
    (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v12);
LABEL_21:
    AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v21);
LABEL_18:
    AutoCleanup<AutoHandle,void *>::ReleasePtr(&phNewToken);
    return 0;
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v13 = SystemTimeAsFileTime;
  v23[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_b6d3b38d29aa3441062213be2537783f_Traceguids);
  AutoHandle::operator=(v23, 0);
  v23[1] = v13;
  v24 = (char *)this + 6336;
  v25 = 0;
  SafeMap_Lock<StringKeyStore,ExpiredOperationIdRecord *,SafeMap_Iterator<StringKeyStore,ExpiredOperationIdRecord *>>::Acquire(&v24);
  v14 = (HANDLE *)SafeMap<ServiceSoapProcessor::TokenCacheKey,ServiceSoapProcessor::TokenCacheMapping,SafeMap_Iterator<ServiceSoapProcessor::TokenCacheKey,ServiceSoapProcessor::TokenCacheMapping>>::operator[](
                    (char *)this + 6336,
                    &v21);
  if ( v14 )
  {
    AutoHandle::operator=(&phNewToken, 0);
    if ( !DuplicateTokenEx(*v14, 0, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
    {
      v15 = GetLastError();
      v16 = v15;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_b6d3b38d29aa3441062213be2537783f_Traceguids, v15);
      (*(void (__fastcall **)(struct IRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, v16);
      SafeMap_Lock<PluginKey,unsigned long,SafeMap_Iterator<PluginKey,unsigned long>>::~SafeMap_Lock<PluginKey,unsigned long,SafeMap_Iterator<PluginKey,unsigned long>>(&v24);
      AutoCleanup<AutoHandle,void *>::~AutoCleanup<AutoHandle,void *>(v23);
      goto LABEL_21;
    }
    CloseHandle(*a4);
    goto LABEL_42;
  }
  if ( (int)SafeMap<UserKey,BlockedRecord *,SafeMap_Iterator<UserKey,BlockedRecord *>>::Size((char *)this + 6336) < 10
    || ServiceSoapProcessor::RemoveOldestEntryFromTokenMap(this, a2) )
  {
    if ( (unsigned __int8)SafeMap<ServiceSoapProcessor::TokenCacheKey,ServiceSoapProcessor::TokenCacheMapping,SafeMap_Iterator<ServiceSoapProcessor::TokenCacheKey,ServiceSoapProcessor::TokenCacheMapping>>::Add(
                            (char *)this + 6336,
                            &v21,
                            v23,
                            a2) )
    {
      v19 = (ServiceSoapProcessor::TokenCacheMapping *)SafeMap<ServiceSoapProcessor::TokenCacheKey,ServiceSoapProcessor::TokenCacheMapping,SafeMap_Iterator<ServiceSoapProcessor::TokenCacheKey,ServiceSoapProcessor::TokenCacheMapping>>::operator[](
                                                         (char *)this + 6336,
                                                         &v21);
      ServiceSoapProcessor::TokenCacheMapping::InsertToken(v19, *a4);
LABEL_42:
      v20 = phNewToken;
      phNewToken = 0;
      *a4 = v20;
      v18 = 1;
      goto LABEL_43;
    }
    if ( (*(unsigned int (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 144LL))(a2) )
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\service\\servicesoapprocessor.cpp", 0x5AEu, L"1454", 0x54Fu, a2);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
  {
    v17 = (*(__int64 (__fastcall **)(struct IRequestContext *))(*(_QWORD *)a2 + 152LL))(a2);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_b6d3b38d29aa3441062213be2537783f_Traceguids, v17);
  }
  v18 = 0;
LABEL_43:
  SafeMap_Lock<PluginKey,unsigned long,SafeMap_Iterator<PluginKey,unsigned long>>::~SafeMap_Lock<PluginKey,unsigned long,SafeMap_Iterator<PluginKey,unsigned long>>(&v24);
  AutoCleanup<AutoHandle,void *>::~AutoCleanup<AutoHandle,void *>(v23);
  AutoCleanup<AutoDeleteVector<unsigned short *>,unsigned short * *>::ReleasePtr(&v21);
  AutoCleanup<AutoHandle,void *>::ReleasePtr(&phNewToken);
  return v18;
}

```

## disassembly

```asm
0x18017425c  mov     [rsp-28h+arg_0], rbx
0x180174261  mov     [rsp-28h+arg_10], rsi
0x180174266  push    rbp
0x180174267  push    rdi
0x180174268  push    r13
0x18017426a  push    r14
0x18017426c  push    r15
0x18017426e  mov     rbp, rsp
0x180174271  sub     rsp, 60h
0x180174275  mov     rsi, r9
0x180174278  mov     rbx, r8
0x18017427b  mov     rdi, rdx
0x18017427e  mov     r15, rcx
0x180174281  lea     r13, WPP_GLOBAL_Control
0x180174288  lea     r14, WPP_b6d3b38d29aa3441062213be2537783f_Traceguids
0x18017428f  mov     rcx, cs:WPP_GLOBAL_Control
0x180174296  cmp     rcx, r13
0x180174299  jz      short loc_1801742B5
0x18017429b  test    dword ptr [rcx+1Ch], 400h
0x1801742a2  jz      short loc_1801742B5
0x1801742a4  mov     edx, 41h ; 'A'
0x1801742a9  mov     r8, r14
0x1801742ac  mov     rcx, [rcx+10h]
0x1801742b0  call    WPP_SF_
0x1801742b5  test    rdi, rdi
0x1801742b8  jnz     short loc_1801742E4
0x1801742ba  mov     qword ptr [rsp+60h+TokenType], rdi; struct IRequestContext *
0x1801742bf  lea     r8, a1378; "1378"
0x1801742c6  mov     edx, 562h; unsigned int
0x1801742cb  mov     r9d, 54Fh; unsigned int
0x1801742d1  lea     rcx, aOnecoreAdminWm_60; "onecore\\admin\\wmi\\wmx\\service\\serv"...
0x1801742d8  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1801742dd  xor     al, al
0x1801742df  jmp     loc_180174613
0x1801742e4  test    rbx, rbx
0x1801742e7  jnz     short loc_1801742FC
0x1801742e9  mov     qword ptr [rsp+60h+TokenType], rdi
0x1801742ee  lea     r8, a1379; "1379"
0x1801742f5  mov     edx, 563h
0x1801742fa  jmp     short loc_1801742CB
0x1801742fc  test    rsi, rsi
0x1801742ff  jnz     short loc_180174314
0x180174301  mov     qword ptr [rsp+60h+TokenType], rdi
0x180174306  lea     r8, a1380; "1380"
0x18017430d  mov     edx, 564h
0x180174312  jmp     short loc_1801742CB
0x180174314  mov     rcx, [rsi]; hExistingToken
0x180174317  test    rcx, rcx
0x18017431a  jnz     short loc_18017432F
0x18017431c  mov     qword ptr [rsp+60h+TokenType], rdi
0x180174321  lea     r8, a1381; "1381"
0x180174328  mov     edx, 565h
0x18017432d  jmp     short loc_1801742CB
0x18017432f  mov     [rbp+arg_8], 0
0x180174337  lea     rax, [rbp+arg_8]
0x18017433b  mov     [rsp+60h+phNewToken], rax; phNewToken
0x180174340  mov     eax, 2
0x180174345  mov     [rsp+60h+TokenType], eax; TokenType
0x180174349  mov     r9d, eax; ImpersonationLevel
0x18017434c  xor     r8d, r8d; lpTokenAttributes
0x18017434f  xor     edx, edx; dwDesiredAccess
0x180174351  call    cs:__imp_DuplicateTokenEx
0x180174357  test    eax, eax
0x180174359  jnz     short loc_1801743AC
0x18017435b  call    cs:__imp_GetLastError
0x180174361  mov     ebx, eax
0x180174363  mov     rcx, cs:WPP_GLOBAL_Control
0x18017436a  cmp     rcx, r13
0x18017436d  jz      short loc_18017438C
0x18017436f  test    dword ptr [rcx+1Ch], 400000h
0x180174376  jz      short loc_18017438C
0x180174378  mov     edx, 42h ; 'B'
0x18017437d  mov     r9d, eax
0x180174380  mov     r8, r14
0x180174383  mov     rcx, [rcx+10h]
0x180174387  call    WPP_SF_d
0x18017438c  mov     rax, [rdi]
0x18017438f  mov     edx, ebx
0x180174391  mov     rcx, rdi
0x180174394  mov     rax, [rax+48h]
0x180174398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017439d  nop
0x18017439e  lea     rcx, [rbp+arg_8]
0x1801743a2  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x1801743a7  jmp     loc_1801742DD
0x1801743ac  mov     [rbp+var_30], 0
0x1801743b4  mov     rdx, rbx; unsigned __int16 *
0x1801743b7  lea     rcx, [rbp+var_30]; this
0x1801743bb  call    ?Initialize@TokenCacheKey@ServiceSoapProcessor@@QEAAKPEBG@Z; ServiceSoapProcessor::TokenCacheKey::Initialize(ushort const *)
0x1801743c0  mov     edx, eax
0x1801743c2  test    eax, eax
0x1801743c4  jz      short loc_1801743E1
0x1801743c6  mov     rcx, [rdi]
0x1801743c9  mov     rax, [rcx+48h]
0x1801743cd  mov     rcx, rdi
0x1801743d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801743d5  nop
0x1801743d6  lea     rcx, [rbp+var_30]
0x1801743da  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x1801743df  jmp     short loc_18017439E
0x1801743e1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1801743e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801743ed  call    cs:__imp_GetSystemTimeAsFileTime
0x1801743f3  mov     rbx, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1801743f7  mov     [rbp+var_20], 0
0x1801743ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180174406  cmp     rcx, r13
0x180174409  jz      short loc_180174425
0x18017440b  test    dword ptr [rcx+1Ch], 400h
0x180174412  jz      short loc_180174425
0x180174414  mov     edx, 39h ; '9'
0x180174419  mov     r8, r14
0x18017441c  mov     rcx, [rcx+10h]
0x180174420  call    WPP_SF_
0x180174425  xor     edx, edx
0x180174427  lea     rcx, [rbp+var_20]
0x18017442b  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x180174430  mov     [rbp+var_18], rbx
0x180174434  lea     rbx, [r15+18C0h]
0x18017443b  mov     [rbp+var_10], rbx
0x18017443f  mov     [rbp+var_8], 0
0x180174443  lea     rcx, [rbp+var_10]
0x180174447  call    ?Acquire@?$SafeMap_Lock@VStringKeyStore@@PEAVExpiredOperationIdRecord@@V?$SafeMap_Iterator@VStringKeyStore@@PEAVExpiredOperationIdRecord@@@@@@QEAAXXZ; SafeMap_Lock<StringKeyStore,ExpiredOperationIdRecord *,SafeMap_Iterator<StringKeyStore,ExpiredOperationIdRecord *>>::Acquire(void)
0x18017444c  nop
0x18017444d  lea     rdx, [rbp+var_30]
0x180174451  mov     rcx, rbx
0x180174454  call    ??A?$SafeMap@VTokenCacheKey@ServiceSoapProcessor@@VTokenCacheMapping@2@V?$SafeMap_Iterator@VTokenCacheKey@ServiceSoapProcessor@@VTokenCacheMapping@2@@@@@QEAAPEAVTokenCacheMapping@ServiceSoapProcessor@@AEBVTokenCacheKey@2@@Z; SafeMap<ServiceSoapProcessor::TokenCacheKey,ServiceSoapProcessor::TokenCacheMapping,SafeMap_Iterator<ServiceSoapProcessor::TokenCacheKey,ServiceSoapProcessor::TokenCacheMapping>>::operator[](ServiceSoapProcessor::TokenCacheKey const &)
0x180174459  mov     r14, rax
0x18017445c  test    rax, rax
0x18017445f  jz      loc_180174503
0x180174465  xor     edx, edx
0x180174467  lea     rcx, [rbp+arg_8]
0x18017446b  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x180174470  lea     rax, [rbp+arg_8]
0x180174474  mov     [rsp+60h+phNewToken], rax; phNewToken
0x180174479  mov     r9d, 2; ImpersonationLevel
0x18017447f  mov     [rsp+60h+TokenType], r9d; TokenType
0x180174484  xor     r8d, r8d; lpTokenAttributes
0x180174487  xor     edx, edx; dwDesiredAccess
0x180174489  mov     rcx, [r14]; hExistingToken
0x18017448c  call    cs:__imp_DuplicateTokenEx
0x180174492  test    eax, eax
0x180174494  jnz     short loc_1801744F5
0x180174496  call    cs:__imp_GetLastError
0x18017449c  mov     ebx, eax
0x18017449e  mov     rcx, cs:WPP_GLOBAL_Control
0x1801744a5  cmp     rcx, r13
0x1801744a8  jz      short loc_1801744CB
0x1801744aa  test    dword ptr [rcx+1Ch], 400000h
0x1801744b1  jz      short loc_1801744CB
0x1801744b3  mov     edx, 43h ; 'C'
0x1801744b8  mov     r9d, eax
0x1801744bb  lea     r8, WPP_b6d3b38d29aa3441062213be2537783f_Traceguids
0x1801744c2  mov     rcx, [rcx+10h]
0x1801744c6  call    WPP_SF_d
0x1801744cb  mov     rax, [rdi]
0x1801744ce  mov     edx, ebx
0x1801744d0  mov     rcx, rdi
0x1801744d3  mov     rax, [rax+48h]
0x1801744d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801744dc  nop
0x1801744dd  lea     rcx, [rbp+var_10]
0x1801744e1  call    ??1?$SafeMap_Lock@UPluginKey@@KV?$SafeMap_Iterator@UPluginKey@@K@@@@QEAA@XZ; SafeMap_Lock<PluginKey,ulong,SafeMap_Iterator<PluginKey,ulong>>::~SafeMap_Lock<PluginKey,ulong,SafeMap_Iterator<PluginKey,ulong>>(void)
0x1801744e6  nop
0x1801744e7  lea     rcx, [rbp+var_20]
0x1801744eb  call    ??1?$AutoCleanup@VAutoHandle@@PEAX@@QEAA@XZ; AutoCleanup<AutoHandle,void *>::~AutoCleanup<AutoHandle,void *>(void)
0x1801744f0  jmp     loc_1801743D6
0x1801744f5  mov     rcx, [rsi]; hObject
0x1801744f8  call    cs:__imp_CloseHandle
0x1801744fe  jmp     loc_1801745D9
0x180174503  mov     rcx, rbx
0x180174506  call    ?Size@?$SafeMap@UUserKey@@PEAVBlockedRecord@@V?$SafeMap_Iterator@UUserKey@@PEAVBlockedRecord@@@@@@QEBAHXZ; SafeMap<UserKey,BlockedRecord *,SafeMap_Iterator<UserKey,BlockedRecord *>>::Size(void)
0x18017450b  cmp     eax, 0Ah
0x18017450e  jl      short loc_18017456F
0x180174510  mov     rdx, rdi; struct IRequestContext *
0x180174513  mov     rcx, r15; this
0x180174516  call    ?RemoveOldestEntryFromTokenMap@ServiceSoapProcessor@@AEAA_NPEAVIRequestContext@@@Z; ServiceSoapProcessor::RemoveOldestEntryFromTokenMap(IRequestContext *)
0x18017451b  test    al, al
0x18017451d  jnz     short loc_18017456F
0x18017451f  mov     rax, cs:WPP_GLOBAL_Control
0x180174526  cmp     rax, r13
0x180174529  jz      loc_1801745BE
0x18017452f  test    dword ptr [rax+1Ch], 400000h
0x180174536  jz      loc_1801745BE
0x18017453c  mov     rax, [rdi]
0x18017453f  mov     rcx, rdi
0x180174542  mov     rax, [rax+98h]
0x180174549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017454e  mov     edx, 44h ; 'D'
0x180174553  mov     r9d, eax
0x180174556  lea     r8, WPP_b6d3b38d29aa3441062213be2537783f_Traceguids
0x18017455d  mov     rcx, cs:WPP_GLOBAL_Control
0x180174564  mov     rcx, [rcx+10h]
0x180174568  call    WPP_SF_d
0x18017456d  jmp     short loc_1801745BE
0x18017456f  mov     r9, rdi
0x180174572  lea     r8, [rbp+var_20]
0x180174576  lea     rdx, [rbp+var_30]
0x18017457a  mov     rcx, rbx
0x18017457d  call    ?Add@?$SafeMap@VTokenCacheKey@ServiceSoapProcessor@@VTokenCacheMapping@2@V?$SafeMap_Iterator@VTokenCacheKey@ServiceSoapProcessor@@VTokenCacheMapping@2@@@@@QEAA_NAEBVTokenCacheKey@ServiceSoapProcessor@@AEBVTokenCacheMapping@3@AEAVIRequestContext@@@Z; SafeMap<ServiceSoapProcessor::TokenCacheKey,ServiceSoapProcessor::TokenCacheMapping,SafeMap_Iterator<ServiceSoapProcessor::TokenCacheKey,ServiceSoapProcessor::TokenCacheMapping>>::Add(ServiceSoapProcessor::TokenCacheKey const &,ServiceSoapProcessor::TokenCacheMapping const &,IRequestContext &)
0x180174582  test    al, al
0x180174584  jnz     short loc_1801745C2
0x180174586  mov     rax, [rdi]
0x180174589  mov     rcx, rdi
0x18017458c  mov     rax, [rax+90h]
0x180174593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180174598  test    eax, eax
0x18017459a  jz      short loc_1801745BE
0x18017459c  mov     qword ptr [rsp+60h+TokenType], rdi; struct IRequestContext *
0x1801745a1  mov     r9d, 54Fh; unsigned int
0x1801745a7  lea     r8, a1454; "1454"
0x1801745ae  lea     edx, [r9+5Fh]; unsigned int
0x1801745b2  lea     rcx, aOnecoreAdminWm_60; "onecore\\admin\\wmi\\wmx\\service\\serv"...
0x1801745b9  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x1801745be  xor     ebx, ebx
0x1801745c0  jmp     short loc_1801745EA
0x1801745c2  lea     rdx, [rbp+var_30]
0x1801745c6  mov     rcx, rbx
0x1801745c9  call    ??A?$SafeMap@VTokenCacheKey@ServiceSoapProcessor@@VTokenCacheMapping@2@V?$SafeMap_Iterator@VTokenCacheKey@ServiceSoapProcessor@@VTokenCacheMapping@2@@@@@QEAAPEAVTokenCacheMapping@ServiceSoapProcessor@@AEBVTokenCacheKey@2@@Z; SafeMap<ServiceSoapProcessor::TokenCacheKey,ServiceSoapProcessor::TokenCacheMapping,SafeMap_Iterator<ServiceSoapProcessor::TokenCacheKey,ServiceSoapProcessor::TokenCacheMapping>>::operator[](ServiceSoapProcessor::TokenCacheKey const &)
0x1801745ce  mov     rdx, [rsi]; void *
0x1801745d1  mov     rcx, rax; this
0x1801745d4  call    ?InsertToken@TokenCacheMapping@ServiceSoapProcessor@@QEAAXPEAX@Z; ServiceSoapProcessor::TokenCacheMapping::InsertToken(void *)
0x1801745d9  mov     rax, [rbp+arg_8]
0x1801745dd  mov     [rbp+arg_8], 0
0x1801745e5  mov     [rsi], rax
0x1801745e8  mov     bl, 1
0x1801745ea  lea     rcx, [rbp+var_10]
0x1801745ee  call    ??1?$SafeMap_Lock@UPluginKey@@KV?$SafeMap_Iterator@UPluginKey@@K@@@@QEAA@XZ; SafeMap_Lock<PluginKey,ulong,SafeMap_Iterator<PluginKey,ulong>>::~SafeMap_Lock<PluginKey,ulong,SafeMap_Iterator<PluginKey,ulong>>(void)
0x1801745f3  nop
0x1801745f4  lea     rcx, [rbp+var_20]
0x1801745f8  call    ??1?$AutoCleanup@VAutoHandle@@PEAX@@QEAA@XZ; AutoCleanup<AutoHandle,void *>::~AutoCleanup<AutoHandle,void *>(void)
0x1801745fd  nop
0x1801745fe  lea     rcx, [rbp+var_30]
0x180174602  call    ?ReleasePtr@?$AutoCleanup@V?$AutoDeleteVector@PEAG@@PEAPEAG@@AEAAXXZ; AutoCleanup<AutoDeleteVector<ushort *>,ushort * *>::ReleasePtr(void)
0x180174607  nop
0x180174608  lea     rcx, [rbp+arg_8]
0x18017460c  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x180174611  mov     al, bl
0x180174613  lea     r11, [rsp+60h+var_s0]
0x180174618  mov     rbx, [r11+30h]
0x18017461c  mov     rsi, [r11+40h]
0x180174620  mov     rsp, r11
0x180174623  pop     r15
0x180174625  pop     r14
0x180174627  pop     r13
0x180174629  pop     rdi
0x18017462a  pop     rbp
0x18017462b  retn
```
