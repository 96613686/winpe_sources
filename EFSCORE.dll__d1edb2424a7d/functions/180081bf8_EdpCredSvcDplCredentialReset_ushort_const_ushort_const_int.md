# EdpCredSvcDplCredentialReset(ushort const *,ushort const *,int)

- ea: `0x180081bf8`
- end: `0x18008221d`
- name: `?EdpCredSvcDplCredentialReset@@YAJPEBG0H@Z`
- size: `1573`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWCH lpString1, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180082374`

## callees

- `0x180001a7c`
- `0x180001f5c`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180081bf8`
- `0x180082d60`
- `0x1800857a8`
- `0x180085ba0`
- `0x1800912c4`
- `0x180096348`
- `0x18009975c`
- `0x18009ad00`
- `0x18009ca50`
- `0x18009e6bc`
- `0x18009e750`
- `0x18009e880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180081d0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180081d0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081dbc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800820e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081dbc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800820e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180081e52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180081e77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180081e52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180081e77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180081e60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180081e85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180081e60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180081e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008217f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008217f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081e3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081e3b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180081efd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180081efd`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180081e2c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180081e2c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180082172`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180082172`

## string_xrefs

- `0x1800820ac`: `Failed to create NGC Key synchronously`

## pseudocode

```c
__int64 __fastcall EdpCredSvcDplCredentialReset(const unsigned __int16 *a1, LPCWCH lpString1, int a3)
{
  CEdpCredSvcUserState *v3; // rdi
  BOOL v7; // r12d
  int v8; // ecx
  unsigned int ImpersonationCtxAndRevertToSelf; // ebx
  int v10; // ecx
  int v11; // ecx
  unsigned int v12; // r8d
  __int64 *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  void *v17; // rdi
  HANDLE ProcessHeap; // rax
  WCHAR *v19; // rdi
  HANDLE v20; // rax
  int v22; // eax
  signed int LastError; // eax
  int v24; // ecx
  int v25; // eax
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  signed int v29; // eax
  CDplServiceImpl *v30; // rcx
  char bIgnoreCase; // [rsp+20h] [rbp-50h]
  char bIgnoreCasea; // [rsp+20h] [rbp-50h]
  LPCWCH lpString2; // [rsp+40h] [rbp-30h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-28h] BYREF
  struct CDplService *v35; // [rsp+50h] [rbp-20h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-18h] BYREF
  void *v37[2]; // [rsp+60h] [rbp-10h] BYREF
  CEdpCredSvcUserState *v38; // [rsp+A0h] [rbp+30h] BYREF
  int v39; // [rsp+B8h] [rbp+48h] BYREF

  v3 = 0;
  v38 = 0;
  v35 = 0;
  hObject = 0;
  lpMem = 0;
  lpString2 = 0;
  v37[0] = 0;
  v7 = 0;
  fnEfsLogTrace1Strings((_DWORD)a1, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 38, 82);
  if ( !a1 )
  {
    bIgnoreCase = 84;
LABEL_3:
    ImpersonationCtxAndRevertToSelf = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 38, bIgnoreCase);
    goto LABEL_14;
  }
  if ( !lpString1 )
  {
    bIgnoreCase = 85;
    goto LABEL_3;
  }
  fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 92);
  ImpersonationCtxAndRevertToSelf = EdpCredSvcGetImpersonationCtxAndRevertToSelf(v37);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              ImpersonationCtxAndRevertToSelf,
              38,
              92) >= 0 )
  {
    EnterCriticalSection(&g_UserStateListLock);
    fnEfsLogTrace1Strings(v10, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 103);
    ImpersonationCtxAndRevertToSelf = CDplProtectorNgc::ResolveNgcKeyName(
                                        a1,
                                        (unsigned __int16 **)&lpMem,
                                        (unsigned __int16 **)&lpString2);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                ImpersonationCtxAndRevertToSelf,
                38,
                103) < 0 )
    {
LABEL_13:
      LeaveCriticalSection(&g_UserStateListLock);
      goto LABEL_14;
    }
    if ( a3 )
    {
      v12 = (unsigned int)lpString2;
      if ( !lpString2 )
      {
        ImpersonationCtxAndRevertToSelf = 0;
        bIgnoreCasea = 118;
        v13 = EFS_TRACE_STATUS;
LABEL_12:
        fnEfsLogTrace1(g_hPublisher, (_DWORD)v13, v12, 38, bIgnoreCasea);
        goto LABEL_13;
      }
      v22 = CompareStringOrdinal(lpString1, -1, lpString2, -1, 1);
      if ( !v22 )
      {
        LastError = GetLastError();
        ImpersonationCtxAndRevertToSelf = LastError;
        if ( LastError > 0 )
          ImpersonationCtxAndRevertToSelf = (unsigned __int16)LastError | 0x80070000;
        bIgnoreCasea = 0x80;
        goto LABEL_34;
      }
      if ( v22 != 2 )
        goto LABEL_13;
    }
    fnEfsLogTrace1Strings(v11, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 150);
    ImpersonationCtxAndRevertToSelf = CDplService::GetCreateServiceInstance(&v35);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                ImpersonationCtxAndRevertToSelf,
                38,
                150) < 0 )
      goto LABEL_13;
    fnEfsLogTrace1Strings(v24, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 158);
    ImpersonationCtxAndRevertToSelf = CEdpCredSvcUserState::GetCreateUserState(a1, 1, &v38);
    v25 = fnEfsLogTrace1String1Dword(
            g_hPublisher,
            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
            (unsigned int)&sourceString,
            ImpersonationCtxAndRevertToSelf,
            38,
            158);
    v3 = v38;
    if ( v25 < 0 )
      goto LABEL_13;
    if ( v38 )
    {
      CEdpCredSvcUserState::ResetPreferredProtectorId(v38);
      if ( a3 )
      {
        *((_DWORD *)v3 + 6) = 1;
      }
      else if ( lpString2 )
      {
        fnEfsLogTrace1Strings(v26, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 177);
        ImpersonationCtxAndRevertToSelf = CDplProtectorNgc::CheckCreateNgcKey(v3, 1);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    ImpersonationCtxAndRevertToSelf,
                    38,
                    177) < 0 )
        {
          fnEfsLogTrace1String1Dword(
            g_hPublisher,
            (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
            (unsigned int)EFS_TRACE_MSG_ERROR_EVENT,
            (unsigned int)L"Failed to create NGC Key synchronously",
            ImpersonationCtxAndRevertToSelf,
            38,
            179);
          bIgnoreCasea = -76;
LABEL_34:
          v12 = ImpersonationCtxAndRevertToSelf;
          v13 = EFS_TRACE_ERROR;
          goto LABEL_12;
        }
      }
    }
    LeaveCriticalSection(&g_UserStateListLock);
    fnEfsLogTrace1Strings(v27, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 198);
    ImpersonationCtxAndRevertToSelf = EdpCredSvcQuerySessionUserTokenBySid(a1, &hObject);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                ImpersonationCtxAndRevertToSelf,
                38,
                198) >= 0 )
    {
      if ( hObject )
      {
        v7 = ImpersonateLoggedOnUser(hObject);
        if ( v7 )
        {
          fnEfsLogTrace1Strings(v28, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 221);
          v30 = (CDplServiceImpl *)*((_QWORD *)v35 + 1);
          if ( v30 )
            ImpersonationCtxAndRevertToSelf = CDplServiceImpl::UpdateDplProtection(v30, a1, a3);
          else
            ImpersonationCtxAndRevertToSelf = -2147418113;
          fnEfsLogTrace1String1Dword(
            g_hPublisher,
            (unsigned int)EFS_TRACE_COMPLETE_EVENT,
            (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
            (unsigned int)&sourceString,
            ImpersonationCtxAndRevertToSelf,
            38,
            221);
        }
        else
        {
          v29 = GetLastError();
          ImpersonationCtxAndRevertToSelf = v29;
          if ( v29 > 0 )
            ImpersonationCtxAndRevertToSelf = (unsigned __int16)v29 | 0x80070000;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, ImpersonationCtxAndRevertToSelf, 38, 214);
        }
      }
      else
      {
        ImpersonationCtxAndRevertToSelf = -2147023888;
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147023888, 38, 204);
      }
    }
  }
LABEL_14:
  if ( (unsigned int)dword_180114250 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180114250, 0x400000000000LL) )
  {
    LODWORD(v38) = ImpersonationCtxAndRevertToSelf;
    v39 = a3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v14,
      (__int64)byte_180102C91,
      v15,
      v16,
      (__int64)&v39,
      (__int64)&v38);
  }
  if ( v3 )
    CEdpCredSvcUserState::Release(v3);
  if ( v35 )
    CDplService::ReleaseServiceInstance(v35);
  if ( v7 )
    RevertToSelf();
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  v17 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v17);
    lpMem = 0;
  }
  v19 = (WCHAR *)lpString2;
  if ( lpString2 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v19);
    lpString2 = 0;
  }
  EdpCredSvcRestoreImpersonationCtx(v37);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    ImpersonationCtxAndRevertToSelf,
    38,
    2);
  return ImpersonationCtxAndRevertToSelf;
}

```

## disassembly

```asm
0x180081bf8  mov     [rsp-28h+arg_8], rbx
0x180081bfd  mov     [rsp-28h+arg_10], rsi
0x180081c02  push    rbp
0x180081c03  push    rdi
0x180081c04  push    r12
0x180081c06  push    r14
0x180081c08  push    r15
0x180081c0a  mov     rbp, rsp
0x180081c0d  sub     rsp, 70h
0x180081c11  xor     edi, edi
0x180081c13  mov     [rsp+70h+bIgnoreCase], 0E52h
0x180081c1b  mov     r15d, r8d
0x180081c1e  mov     [rbp+arg_0], rdi
0x180081c22  mov     rsi, rdx
0x180081c25  mov     [rbp+var_20], rdi
0x180081c29  lea     r8, sourceString
0x180081c30  mov     [rbp+hObject], rdi
0x180081c34  lea     ebx, [rdi+26h]
0x180081c37  mov     [rbp+lpMem], rdi
0x180081c3b  mov     r9d, ebx
0x180081c3e  mov     [rbp+lpString2], rdi
0x180081c42  lea     rdx, EFS_TRACE_ENTER_EVENT
0x180081c49  mov     [rbp+var_10], rdi
0x180081c4d  mov     r14, rcx
0x180081c50  xor     r12d, r12d
0x180081c53  call    fnEfsLogTrace1Strings
0x180081c58  test    r14, r14
0x180081c5b  jnz     short loc_180081C8E
0x180081c5d  mov     [rsp+70h+bIgnoreCase], 0E54h
0x180081c65  mov     ebx, 80070057h
0x180081c6a  mov     r8d, 80070057h
0x180081c70  mov     rcx, cs:g_hPublisher
0x180081c77  lea     rdx, EFS_TRACE_ERROR
0x180081c7e  mov     r9d, 26h ; '&'
0x180081c84  call    fnEfsLogTrace1
0x180081c89  jmp     loc_180081DC2
0x180081c8e  test    rsi, rsi
0x180081c91  jnz     short loc_180081C9D
0x180081c93  mov     [rsp+70h+bIgnoreCase], 0E55h
0x180081c9b  jmp     short loc_180081C65
0x180081c9d  mov     r9d, ebx
0x180081ca0  mov     [rsp+70h+bIgnoreCase], 0E5Ch
0x180081ca8  lea     r8, sourceString
0x180081caf  lea     rdx, EFS_TRACE_START_EVENT
0x180081cb6  call    fnEfsLogTrace1Strings
0x180081cbb  lea     rcx, [rbp+var_10]; void **
0x180081cbf  call    ?EdpCredSvcGetImpersonationCtxAndRevertToSelf@@YAJPEAPEAX@Z; EdpCredSvcGetImpersonationCtxAndRevertToSelf(void * *)
0x180081cc4  mov     rcx, cs:g_hPublisher
0x180081ccb  lea     r9, sourceString
0x180081cd2  mov     [rsp+70h+var_40], 0E5Ch
0x180081cda  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180081ce1  mov     dword ptr [rsp+70h+var_48], 26h ; '&'
0x180081ce9  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180081cf0  mov     [rsp+70h+bIgnoreCase], eax
0x180081cf4  mov     ebx, eax
0x180081cf6  call    fnEfsLogTrace1String1Dword
0x180081cfb  test    eax, eax
0x180081cfd  js      loc_180081DC2
0x180081d03  lea     rcx, ?g_UserStateListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180081d0a  call    cs:__imp_EnterCriticalSection
0x180081d10  mov     r9d, 26h ; '&'
0x180081d16  mov     [rsp+70h+bIgnoreCase], 0E67h
0x180081d1e  lea     r8, sourceString
0x180081d25  lea     rdx, EFS_TRACE_START_EVENT
0x180081d2c  call    fnEfsLogTrace1Strings
0x180081d31  lea     r8, [rbp+lpString2]; unsigned __int16 **
0x180081d35  mov     rcx, r14; unsigned __int16 *
0x180081d38  lea     rdx, [rbp+lpMem]; unsigned __int16 **
0x180081d3c  call    ?ResolveNgcKeyName@CDplProtectorNgc@@SAJPEBGPEAPEAG1@Z; CDplProtectorNgc::ResolveNgcKeyName(ushort const *,ushort * *,ushort * *)
0x180081d41  mov     rcx, cs:g_hPublisher
0x180081d48  lea     r9, sourceString
0x180081d4f  mov     [rsp+70h+var_40], 0E67h
0x180081d57  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180081d5e  mov     dword ptr [rsp+70h+var_48], 26h ; '&'
0x180081d66  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180081d6d  mov     [rsp+70h+bIgnoreCase], eax
0x180081d71  mov     ebx, eax
0x180081d73  call    fnEfsLogTrace1String1Dword
0x180081d78  test    eax, eax
0x180081d7a  js      short loc_180081DB5
0x180081d7c  test    r15d, r15d
0x180081d7f  jz      loc_180081F3C
0x180081d85  mov     r8, [rbp+lpString2]; lpString2
0x180081d89  test    r8, r8
0x180081d8c  jnz     loc_180081EEC
0x180081d92  xor     ebx, ebx
0x180081d94  mov     [rsp+70h+bIgnoreCase], 0E76h
0x180081d9c  lea     rdx, EFS_TRACE_STATUS
0x180081da3  mov     rcx, cs:g_hPublisher
0x180081daa  mov     r9d, 26h ; '&'
0x180081db0  call    fnEfsLogTrace1
0x180081db5  lea     rcx, ?g_UserStateListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180081dbc  call    cs:__imp_LeaveCriticalSection
0x180081dc2  mov     eax, cs:dword_180114250
0x180081dc8  cmp     eax, 5
0x180081dcb  jbe     short loc_180081E0C
0x180081dcd  mov     rdx, 400000000000h
0x180081dd7  lea     rcx, dword_180114250
0x180081dde  call    _tlgKeywordOn
0x180081de3  test    al, al
0x180081de5  jz      short loc_180081E0C
0x180081de7  lea     rax, [rbp+arg_0]
0x180081deb  mov     dword ptr [rbp+arg_0], ebx
0x180081dee  mov     [rsp+70h+var_48], rax
0x180081df3  lea     rdx, byte_180102C91
0x180081dfa  lea     rax, [rbp+arg_18]
0x180081dfe  mov     [rbp+arg_18], r15d
0x180081e02  mov     qword ptr [rsp+70h+bIgnoreCase], rax
0x180081e07  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180081e0c  test    rdi, rdi
0x180081e0f  jz      short loc_180081E19
0x180081e11  mov     rcx, rdi; this
0x180081e14  call    ?Release@CEdpCredSvcUserState@@QEAAJXZ; CEdpCredSvcUserState::Release(void)
0x180081e19  mov     rcx, [rbp+var_20]; struct CDplService *
0x180081e1d  test    rcx, rcx
0x180081e20  jz      short loc_180081E27
0x180081e22  call    ?ReleaseServiceInstance@CDplService@@SAJPEAV1@@Z; CDplService::ReleaseServiceInstance(CDplService *)
0x180081e27  test    r12d, r12d
0x180081e2a  jz      short loc_180081E32
0x180081e2c  call    cs:__imp_RevertToSelf
0x180081e32  mov     rcx, [rbp+hObject]; hObject
0x180081e36  test    rcx, rcx
0x180081e39  jz      short loc_180081E49
0x180081e3b  call    cs:__imp_CloseHandle
0x180081e41  mov     [rbp+hObject], 0
0x180081e49  mov     rdi, [rbp+lpMem]
0x180081e4d  test    rdi, rdi
0x180081e50  jz      short loc_180081E6E
0x180081e52  call    cs:__imp_GetProcessHeap
0x180081e58  mov     r8, rdi; lpMem
0x180081e5b  xor     edx, edx; dwFlags
0x180081e5d  mov     rcx, rax; hHeap
0x180081e60  call    cs:__imp_HeapFree
0x180081e66  mov     [rbp+lpMem], 0
0x180081e6e  mov     rdi, [rbp+lpString2]
0x180081e72  test    rdi, rdi
0x180081e75  jz      short loc_180081E93
0x180081e77  call    cs:__imp_GetProcessHeap
0x180081e7d  mov     r8, rdi; lpMem
0x180081e80  xor     edx, edx; dwFlags
0x180081e82  mov     rcx, rax; hHeap
0x180081e85  call    cs:__imp_HeapFree
0x180081e8b  mov     [rbp+lpString2], 0
0x180081e93  lea     rcx, [rbp+var_10]; void **
0x180081e97  call    ?EdpCredSvcRestoreImpersonationCtx@@YAXPEAPEAX@Z; EdpCredSvcRestoreImpersonationCtx(void * *)
0x180081e9c  mov     rcx, cs:g_hPublisher
0x180081ea3  lea     r9, sourceString
0x180081eaa  mov     [rsp+70h+var_40], 0F02h
0x180081eb2  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x180081eb9  mov     dword ptr [rsp+70h+var_48], 26h ; '&'
0x180081ec1  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x180081ec8  mov     [rsp+70h+bIgnoreCase], ebx
0x180081ecc  call    fnEfsLogTrace1String1Dword
0x180081ed1  lea     r11, [rsp+70h+var_s0]
0x180081ed6  mov     eax, ebx
0x180081ed8  mov     rbx, [r11+38h]
0x180081edc  mov     rsi, [r11+40h]
0x180081ee0  mov     rsp, r11
0x180081ee3  pop     r15
0x180081ee5  pop     r14
0x180081ee7  pop     r12
0x180081ee9  pop     rdi
0x180081eea  pop     rbp
0x180081eeb  retn
0x180081eec  or      edx, 0FFFFFFFFh; cchCount1
0x180081eef  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x180081ef7  mov     r9d, edx; cchCount2
0x180081efa  mov     rcx, rsi; lpString1
0x180081efd  call    cs:__imp_CompareStringOrdinal
0x180081f03  test    eax, eax
0x180081f05  jnz     short loc_180081F33
0x180081f07  call    cs:__imp_GetLastError
0x180081f0d  mov     ebx, eax
0x180081f0f  test    eax, eax
0x180081f11  jle     short loc_180081F1C
0x180081f13  movzx   ebx, ax
0x180081f16  or      ebx, 80070000h
0x180081f1c  mov     [rsp+70h+bIgnoreCase], 0E80h
0x180081f24  mov     r8d, ebx
0x180081f27  lea     rdx, EFS_TRACE_ERROR
0x180081f2e  jmp     loc_180081DA3
0x180081f33  cmp     eax, 2
0x180081f36  jnz     loc_180081DB5
0x180081f3c  mov     esi, 0E96h
0x180081f41  lea     r8, sourceString
0x180081f48  mov     r9d, 26h ; '&'
0x180081f4e  mov     [rsp+70h+bIgnoreCase], esi
0x180081f52  lea     rdx, EFS_TRACE_START_EVENT
0x180081f59  call    fnEfsLogTrace1Strings
0x180081f5e  lea     rcx, [rbp+var_20]; struct CDplService **
0x180081f62  call    ?GetCreateServiceInstance@CDplService@@SAJPEAPEAV1@@Z; CDplService::GetCreateServiceInstance(CDplService * *)
0x180081f67  mov     rcx, cs:g_hPublisher
0x180081f6e  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180081f75  mov     [rsp+70h+var_40], esi
0x180081f79  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180081f80  lea     rsi, sourceString
0x180081f87  mov     dword ptr [rsp+70h+var_48], 26h ; '&'
0x180081f8f  mov     r9, rsi
0x180081f92  mov     [rsp+70h+bIgnoreCase], eax
0x180081f96  mov     ebx, eax
0x180081f98  call    fnEfsLogTrace1String1Dword
0x180081f9d  test    eax, eax
0x180081f9f  js      loc_180081DB5
0x180081fa5  mov     edi, 0E9Eh
0x180081faa  lea     rdx, EFS_TRACE_START_EVENT
0x180081fb1  mov     r9d, 26h ; '&'
0x180081fb7  mov     [rsp+70h+bIgnoreCase], edi
0x180081fbb  mov     r8, rsi
0x180081fbe  call    fnEfsLogTrace1Strings
0x180081fc3  lea     r8, [rbp+arg_0]; struct CEdpCredSvcUserState **
0x180081fc7  mov     edx, 1; int
0x180081fcc  mov     rcx, r14; unsigned __int16 *
0x180081fcf  call    ?GetCreateUserState@CEdpCredSvcUserState@@SAJPEBGHPEAPEAV1@@Z; CEdpCredSvcUserState::GetCreateUserState(ushort const *,int,CEdpCredSvcUserState * *)
0x180081fd4  mov     rcx, cs:g_hPublisher
0x180081fdb  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180081fe2  mov     [rsp+70h+var_40], edi
0x180081fe6  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180081fed  mov     dword ptr [rsp+70h+var_48], 26h ; '&'
0x180081ff5  mov     r9, rsi
0x180081ff8  mov     [rsp+70h+bIgnoreCase], eax
0x180081ffc  mov     ebx, eax
0x180081ffe  call    fnEfsLogTrace1String1Dword
0x180082003  mov     rdi, [rbp+arg_0]
0x180082007  test    eax, eax
0x180082009  js      loc_180081DB5
0x18008200f  test    rdi, rdi
0x180082012  jz      loc_1800820DB
0x180082018  mov     rcx, rdi; this
0x18008201b  call    ?ResetPreferredProtectorId@CEdpCredSvcUserState@@QEAAXXZ; CEdpCredSvcUserState::ResetPreferredProtectorId(void)
0x180082020  test    r15d, r15d
0x180082023  jnz     loc_1800820D4
0x180082029  cmp     [rbp+lpString2], r12
0x18008202d  jz      loc_1800820DB
0x180082033  mov     esi, 0EB1h
0x180082038  lea     r9d, [r15+26h]
0x18008203c  lea     r8, sourceString
0x180082043  mov     [rsp+70h+bIgnoreCase], esi
0x180082047  lea     rdx, EFS_TRACE_START_EVENT
0x18008204e  call    fnEfsLogTrace1Strings
0x180082053  lea     edx, [r15+1]; int
0x180082057  mov     rcx, rdi; struct CEdpCredSvcUserState *
0x18008205a  call    ?CheckCreateNgcKey@CDplProtectorNgc@@SAJPEAVCEdpCredSvcUserState@@H@Z; CDplProtectorNgc::CheckCreateNgcKey(CEdpCredSvcUserState *,int)
0x18008205f  mov     rcx, cs:g_hPublisher
0x180082066  lea     r9, sourceString
0x18008206d  mov     [rsp+70h+var_40], esi
0x180082071  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180082078  mov     dword ptr [rsp+70h+var_48], 26h ; '&'
0x180082080  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180082087  mov     [rsp+70h+bIgnoreCase], eax
0x18008208b  mov     ebx, eax
0x18008208d  call    fnEfsLogTrace1String1Dword
0x180082092  test    eax, eax
0x180082094  jns     short loc_1800820DB
0x180082096  mov     rcx, cs:g_hPublisher
0x18008209d  lea     rdx, EFS_TRACE_MSG_ERROR_EVENT
0x1800820a4  mov     [rsp+70h+var_40], 0EB3h
0x1800820ac  lea     r9, aFailedToCreate; "Failed to create NGC Key synchronously"
0x1800820b3  mov     r8, rdx
0x1800820b6  mov     dword ptr [rsp+70h+var_48], 26h ; '&'
0x1800820be  mov     [rsp+70h+bIgnoreCase], ebx
0x1800820c2  call    fnEfsLogTrace1String1Dword
0x1800820c7  mov     [rsp+70h+bIgnoreCase], 0EB4h
0x1800820cf  jmp     loc_180081F24
0x1800820d4  mov     dword ptr [rdi+18h], 1
0x1800820db  lea     rcx, ?g_UserStateListLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800820e2  call    cs:__imp_LeaveCriticalSection
0x1800820e8  mov     esi, 0EC6h
0x1800820ed  lea     r8, sourceString
0x1800820f4  mov     r9d, 26h ; '&'
0x1800820fa  mov     [rsp+70h+bIgnoreCase], esi
0x1800820fe  lea     rdx, EFS_TRACE_START_EVENT
0x180082105  call    fnEfsLogTrace1Strings
0x18008210a  lea     rdx, [rbp+hObject]; void **
0x18008210e  mov     rcx, r14; unsigned __int16 *
0x180082111  call    ?EdpCredSvcQuerySessionUserTokenBySid@@YAJPEBGPEAPEAX@Z; EdpCredSvcQuerySessionUserTokenBySid(ushort const *,void * *)
0x180082116  mov     rcx, cs:g_hPublisher
0x18008211d  lea     r9, sourceString
0x180082124  mov     [rsp+70h+var_40], esi
0x180082128  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x18008212f  mov     dword ptr [rsp+70h+var_48], 26h ; '&'
0x180082137  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18008213e  mov     [rsp+70h+bIgnoreCase], eax
0x180082142  mov     ebx, eax
0x180082144  call    fnEfsLogTrace1String1Dword
0x180082149  test    eax, eax
0x18008214b  js      loc_180081DC2
0x180082151  mov     rcx, [rbp+hObject]; hToken
0x180082155  test    rcx, rcx
0x180082158  jnz     short loc_180082172
0x18008215a  mov     ebx, 800703F0h
0x18008215f  mov     [rsp+70h+bIgnoreCase], 0ECCh
0x180082167  mov     r8d, 800703F0h
0x18008216d  jmp     loc_180081C70
0x180082172  call    cs:__imp_ImpersonateLoggedOnUser
0x180082178  mov     r12d, eax
0x18008217b  test    eax, eax
0x18008217d  jnz     short loc_1800821A4
0x18008217f  call    cs:__imp_GetLastError
0x180082185  mov     ebx, eax
0x180082187  test    eax, eax
  ... truncated ...
```
