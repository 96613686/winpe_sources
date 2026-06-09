# _lambda_39c446a7a3dabdd188e7ddcdfa0817b9_::operator()

- ea: `0x18007307c`
- end: `0x1800732dd`
- name: `_lambda_39c446a7a3dabdd188e7ddcdfa0817b9_::operator()`
- size: `609`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180072c40`

## callees

- `0x1800281e0`
- `0x18002a2d0`
- `0x18002eee8`
- `0x1800323d0`
- `0x180036364`
- `0x180041a34`
- `0x180041bbc`
- `0x180047228`
- `0x180072db8`
- `0x18007307c`
- `0x180074180`
- `0x1800745dc`
- `0x1800748b0`
- `0x1800759d4`
- `0x1800809c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800732c1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800732c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800732cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800732cf`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800731cb`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800731cb`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180073192`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180073192`
- `webauthn!WebAuthNReportPasskeyHeartbeat` at `0x1800731fe`
- `webauthn!WebAuthNReportPasskeyHeartbeat` at `0x1800731fe`

## string_xrefs

- `0x1800731a3`: `onecore\ds\security\ngc\kspsvc\svc\ngcsvc.cpp`
- `0x180073214`: `onecore\ds\security\ngc\kspsvc\svc\ngcsvc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_39c446a7a3dabdd188e7ddcdfa0817b9_::operator()(__int64 a1)
{
  struct NgcSvc::ServiceInfo *v2; // rdx
  signed __int64 v3; // rax
  signed __int64 v4; // rtt
  signed int LastError; // ebx
  __int64 v6; // rsi
  _DWORD *v7; // rcx
  RTL_SRWLOCK *v8; // rax
  struct NgcKspServer::PinCacheManager *v9; // rax
  struct NgcKspServer::PinCacheManager *v11; // rax
  int v12; // eax
  int v13; // eax
  wil::details::in1diag3 *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rbx
  _DWORD *v17; // rcx
  struct NgcKspServer::PinCacheManager *v18; // rax
  RTL_SRWLOCK *v19; // rax
  struct NgcKspServer::PinCacheManager *v20; // rax
  RTL_SRWLOCK *v21; // rax
  struct NgcSvc::ServiceInfo *v22; // rax
  __int64 v23; // [rsp+20h] [rbp-10h] BYREF
  __int64 v24; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  char v26; // [rsp+58h] [rbp+28h] BYREF
  __int16 v27; // [rsp+59h] [rbp+29h]
  void *DuplicateTokenHandle; // [rsp+60h] [rbp+30h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+68h] [rbp+38h] BYREF

  v27 = 258;
  v2 = NgcSvc::ServiceInfo::Instance();
  _m_prefetchw((char *)v2 + 72);
  v3 = *((_QWORD *)v2 + 9);
  do
  {
    v4 = v3;
    v3 = _InterlockedCompareExchange64((volatile signed __int64 *)v2 + 9, v3 | 1, v3);
  }
  while ( v4 != v3 );
  if ( (v3 & 2) == 0 )
  {
    LastError = 120;
    v23 = 0;
    switch ( **(_DWORD **)a1 )
    {
      case 1:
        v22 = NgcSvc::ServiceInfo::Instance();
        if ( !SetEvent(*((HANDLE *)v22 + 8)) )
        {
          LastError = GetLastError();
          goto LABEL_13;
        }
        goto LABEL_12;
      case 4:
LABEL_12:
        LastError = 0;
        goto LABEL_13;
      case 0xE:
        v16 = **(_QWORD **)(a1 + 8);
        v17 = *(_DWORD **)(a1 + 16);
        if ( *v17 == 7 )
        {
          v20 = NgcKspServer::PinCacheManager::Instance();
          NgcKspServer::PinCacheManager::UpdateSessionTraceInfo(v20, 4);
          v21 = (RTL_SRWLOCK *)NgcKspServer::PinCacheManager::Instance();
          NgcKspServer::PinCacheManager::MarkSessionLockedAndRemoveCacheWhileUnlockedTickets(v21, *(_DWORD *)(v16 + 4));
        }
        else if ( *v17 == 8 )
        {
          v18 = NgcKspServer::PinCacheManager::Instance();
          NgcKspServer::PinCacheManager::UpdateSessionTraceInfo(v18, 3);
          v19 = (RTL_SRWLOCK *)NgcKspServer::PinCacheManager::Instance();
          NgcKspServer::PinCacheManager::MarkSessionUnlocked(v19, *(_DWORD *)(v16 + 4));
          NgcSvc::NgcServiceLaunchNgcFirstExperiment(*(_DWORD *)(v16 + 4));
        }
        goto LABEL_12;
    }
    if ( **(_DWORD **)a1 != 33 )
    {
LABEL_13:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v23);
      goto LABEL_14;
    }
    v6 = **(_QWORD **)(a1 + 8);
    v7 = *(_DWORD **)(a1 + 16);
    if ( *v7 != 5 )
    {
      if ( *v7 == 6 )
      {
        v8 = (RTL_SRWLOCK *)NgcKspServer::PinCacheManager::Instance();
        NgcKspServer::PinCacheManager::RemoveUserWithSessionOrContext(v8, *(_DWORD *)(v6 + 4), *(_QWORD *)(v6 + 8));
        v9 = NgcKspServer::PinCacheManager::Instance();
        NgcKspServer::PinCacheManager::UpdateSessionTraceInfo(v9, 2);
      }
      goto LABEL_12;
    }
    LastError = NgcSvc::NgcServiceQueryAndAssociateUser(
                  *(unsigned int *)(v6 + 4),
                  *(_QWORD *)(v6 + 8),
                  (unsigned int)(*v7 - 5));
    if ( LastError < 0 )
      goto LABEL_13;
    v11 = NgcKspServer::PinCacheManager::Instance();
    NgcKspServer::PinCacheManager::UpdateSessionTraceInfo(v11, 1);
    NgcSvc::NgcServiceLaunchNgcFirstExperiment(*(_DWORD *)(v6 + 4));
    ExistingTokenHandle = 0;
    v12 = UMgrQueryUserToken(*(_QWORD *)(v6 + 8), &ExistingTokenHandle);
    if ( v12 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4DA,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ngcsvc.cpp",
        (const char *)(unsigned int)v12,
        v23);
LABEL_26:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExistingTokenHandle);
      goto LABEL_12;
    }
    DuplicateTokenHandle = 0;
    if ( !DuplicateToken(ExistingTokenHandle, SecurityImpersonation, &DuplicateTokenHandle) )
    {
LABEL_25:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&DuplicateTokenHandle);
      goto LABEL_26;
    }
    v24 = -1;
    v13 = wil::impersonate_token_nothrow(DuplicateTokenHandle, (void **)&v24);
    v14 = retaddr;
    if ( v13 >= 0 )
    {
      v13 = WebAuthNReportPasskeyHeartbeat(1);
      v14 = retaddr;
      if ( v13 >= 0 )
      {
LABEL_24:
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v24);
        goto LABEL_25;
      }
      v15 = 1250;
    }
    else
    {
      v15 = 1248;
    }
    wil::details::in1diag3::_Log_Hr(
      v14,
      (void *)v15,
      (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ngcsvc.cpp",
      (const char *)(unsigned int)v13,
      v23);
    goto LABEL_24;
  }
  LastError = 1115;
LABEL_14:
  wil::details::ScopeExitFnGuard__lambda_14fa87c05f2a1fc876ee6ea227db70c8___::operator()(&v26);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18007307c  mov     [rsp-18h+arg_0], rbx
0x180073081  push    rbp
0x180073082  push    rsi
0x180073083  push    rdi
0x180073084  mov     rbp, rsp
0x180073087  sub     rsp, 30h
0x18007308b  mov     rdi, rcx
0x18007308e  mov     [rbp+arg_9], 102h
0x180073094  call    ?Instance@ServiceInfo@NgcSvc@@SAAEAV12@XZ; NgcSvc::ServiceInfo::Instance(void)
0x180073099  mov     rdx, rax
0x18007309c  prefetchw byte ptr [rax+48h]
0x1800730a0  mov     rax, [rax+48h]
0x1800730a4  mov     rcx, rax
0x1800730a7  or      rcx, 1
0x1800730ab  lock cmpxchg [rdx+48h], rcx
0x1800730b1  jnz     short loc_1800730A4
0x1800730b3  test    al, 2
0x1800730b5  jz      short loc_1800730BE
0x1800730b7  mov     ebx, 45Bh
0x1800730bc  jmp     short loc_18007313A
0x1800730be  mov     ebx, 78h ; 'x'
0x1800730c3  mov     [rbp+var_10], 0
0x1800730cb  mov     rcx, [rdi]
0x1800730ce  mov     edx, [rcx]
0x1800730d0  sub     edx, 1
0x1800730d3  jz      loc_1800732B8
0x1800730d9  sub     edx, 3
0x1800730dc  jz      short loc_18007312E
0x1800730de  sub     edx, 0Ah
0x1800730e1  jz      loc_180073240
0x1800730e7  cmp     edx, 13h
0x1800730ea  jnz     short loc_180073130
0x1800730ec  mov     rax, [rdi+8]
0x1800730f0  mov     rsi, [rax]
0x1800730f3  mov     rcx, [rdi+10h]
0x1800730f7  mov     r8d, [rcx]
0x1800730fa  sub     r8d, 5
0x1800730fe  jz      short loc_180073152
0x180073100  cmp     r8d, 1
0x180073104  jnz     short loc_18007312E
0x180073106  call    ?Instance@PinCacheManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::PinCacheManager::Instance(void)
0x18007310b  mov     r8, [rsi+8]; unsigned __int64
0x18007310f  mov     edx, [rsi+4]; unsigned int
0x180073112  mov     rcx, rax; SRWLock
0x180073115  call    ?RemoveUserWithSessionOrContext@PinCacheManager@NgcKspServer@@QEAAXK_K@Z; NgcKspServer::PinCacheManager::RemoveUserWithSessionOrContext(ulong,unsigned __int64)
0x18007311a  call    ?Instance@PinCacheManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::PinCacheManager::Instance(void)
0x18007311f  mov     r8d, [rsi+4]
0x180073123  lea     edx, [rbx-76h]
0x180073126  mov     rcx, rax
0x180073129  call    ?UpdateSessionTraceInfo@PinCacheManager@NgcKspServer@@QEAAXW4SessionType@12@K@Z; NgcKspServer::PinCacheManager::UpdateSessionTraceInfo(NgcKspServer::PinCacheManager::SessionType,ulong)
0x18007312e  xor     ebx, ebx
0x180073130  lea     rcx, [rbp+var_10]; void *
0x180073134  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180073139  nop
0x18007313a  lea     rcx, [rbp+arg_8]
0x18007313e  call    wil__details__ScopeExitFnGuard__lambda_14fa87c05f2a1fc876ee6ea227db70c8_____operator__
0x180073143  mov     eax, ebx
0x180073145  mov     rbx, [rsp+30h+arg_0]
0x18007314a  add     rsp, 30h
0x18007314e  pop     rdi
0x18007314f  pop     rsi
0x180073150  pop     rbp
0x180073151  retn
0x180073152  mov     rdx, [rsi+8]
0x180073156  mov     ecx, [rsi+4]
0x180073159  call    NgcSvc__NgcServiceQueryAndAssociateUser
0x18007315e  mov     ebx, eax
0x180073160  test    eax, eax
0x180073162  js      short loc_180073130
0x180073164  call    ?Instance@PinCacheManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::PinCacheManager::Instance(void)
0x180073169  mov     r8d, [rsi+4]
0x18007316d  mov     edx, 1
0x180073172  mov     rcx, rax
0x180073175  call    ?UpdateSessionTraceInfo@PinCacheManager@NgcKspServer@@QEAAXW4SessionType@12@K@Z; NgcKspServer::PinCacheManager::UpdateSessionTraceInfo(NgcKspServer::PinCacheManager::SessionType,ulong)
0x18007317a  mov     ecx, [rsi+4]; SessionId
0x18007317d  call    NgcSvc__NgcServiceLaunchNgcFirstExperiment
0x180073182  mov     [rbp+ExistingTokenHandle], 0
0x18007318a  lea     rdx, [rbp+ExistingTokenHandle]
0x18007318e  mov     rcx, [rsi+8]
0x180073192  call    cs:__imp_UMgrQueryUserToken
0x180073198  mov     rcx, [rbp+18h]; this
0x18007319c  test    eax, eax
0x18007319e  jns     short loc_1800731B6
0x1800731a0  mov     r9d, eax; char *
0x1800731a3  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x1800731aa  mov     edx, 4DAh; void *
0x1800731af  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800731b4  jmp     short loc_180073232
0x1800731b6  mov     [rbp+DuplicateTokenHandle], 0
0x1800731be  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x1800731c2  mov     edx, 2; ImpersonationLevel
0x1800731c7  mov     rcx, [rbp+ExistingTokenHandle]; ExistingTokenHandle
0x1800731cb  call    cs:__imp_DuplicateToken
0x1800731d1  test    eax, eax
0x1800731d3  jz      short loc_180073229
0x1800731d5  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFFh
0x1800731dd  lea     rdx, [rbp+var_8]
0x1800731e1  mov     rcx, [rbp+DuplicateTokenHandle]; Token
0x1800731e5  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x1800731ea  mov     rcx, [rbp+18h]
0x1800731ee  test    eax, eax
0x1800731f0  jns     short loc_1800731F9
0x1800731f2  mov     edx, 4E0h
0x1800731f7  jmp     short loc_180073211
0x1800731f9  mov     ecx, 1
0x1800731fe  call    cs:__imp_WebAuthNReportPasskeyHeartbeat
0x180073204  mov     rcx, [rbp+18h]; this
0x180073208  test    eax, eax
0x18007320a  jns     short loc_180073220
0x18007320c  mov     edx, 4E2h; void *
0x180073211  mov     r9d, eax; char *
0x180073214  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007321b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180073220  lea     rcx, [rbp+var_8]
0x180073224  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180073229  lea     rcx, [rbp+DuplicateTokenHandle]
0x18007322d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180073232  lea     rcx, [rbp+ExistingTokenHandle]
0x180073236  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18007323b  jmp     loc_18007312E
0x180073240  mov     rax, [rdi+8]
0x180073244  mov     rbx, [rax]
0x180073247  mov     rcx, [rdi+10h]
0x18007324b  mov     r8d, [rcx]
0x18007324e  sub     r8d, 7
0x180073252  jz      short loc_18007328F
0x180073254  cmp     r8d, 1
0x180073258  jnz     loc_18007312E
0x18007325e  call    ?Instance@PinCacheManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::PinCacheManager::Instance(void)
0x180073263  xor     r8d, r8d
0x180073266  lea     edx, [r8+3]
0x18007326a  mov     rcx, rax
0x18007326d  call    ?UpdateSessionTraceInfo@PinCacheManager@NgcKspServer@@QEAAXW4SessionType@12@K@Z; NgcKspServer::PinCacheManager::UpdateSessionTraceInfo(NgcKspServer::PinCacheManager::SessionType,ulong)
0x180073272  call    ?Instance@PinCacheManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::PinCacheManager::Instance(void)
0x180073277  mov     edx, [rbx+4]; unsigned int
0x18007327a  mov     rcx, rax; SRWLock
0x18007327d  call    ?MarkSessionUnlocked@PinCacheManager@NgcKspServer@@QEAAXK@Z; NgcKspServer::PinCacheManager::MarkSessionUnlocked(ulong)
0x180073282  mov     ecx, [rbx+4]; SessionId
0x180073285  call    NgcSvc__NgcServiceLaunchNgcFirstExperiment
0x18007328a  jmp     loc_18007312E
0x18007328f  call    ?Instance@PinCacheManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::PinCacheManager::Instance(void)
0x180073294  xor     r8d, r8d
0x180073297  lea     edx, [r8+4]
0x18007329b  mov     rcx, rax
0x18007329e  call    ?UpdateSessionTraceInfo@PinCacheManager@NgcKspServer@@QEAAXW4SessionType@12@K@Z; NgcKspServer::PinCacheManager::UpdateSessionTraceInfo(NgcKspServer::PinCacheManager::SessionType,ulong)
0x1800732a3  call    ?Instance@PinCacheManager@NgcKspServer@@SAAEAV12@XZ; NgcKspServer::PinCacheManager::Instance(void)
0x1800732a8  mov     edx, [rbx+4]; unsigned int
0x1800732ab  mov     rcx, rax; SRWLock
0x1800732ae  call    ?MarkSessionLockedAndRemoveCacheWhileUnlockedTickets@PinCacheManager@NgcKspServer@@QEAAXK@Z; NgcKspServer::PinCacheManager::MarkSessionLockedAndRemoveCacheWhileUnlockedTickets(ulong)
0x1800732b3  jmp     loc_18007312E
0x1800732b8  call    ?Instance@ServiceInfo@NgcSvc@@SAAEAV12@XZ; NgcSvc::ServiceInfo::Instance(void)
0x1800732bd  mov     rcx, [rax+40h]; hEvent
0x1800732c1  call    cs:__imp_SetEvent
0x1800732c7  test    eax, eax
0x1800732c9  jnz     loc_18007312E
0x1800732cf  call    cs:__imp_GetLastError
0x1800732d5  mov     ebx, eax
0x1800732d7  jmp     loc_180073130
```
