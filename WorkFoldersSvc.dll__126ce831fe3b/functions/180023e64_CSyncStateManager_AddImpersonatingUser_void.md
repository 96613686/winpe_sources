# CSyncStateManager::AddImpersonatingUser(void)

- ea: `0x180023e64`
- end: `0x180024471`
- name: `?AddImpersonatingUser@CSyncStateManager@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `1549`
- prototype: `__int64 __fastcall(CSyncStateManager *this, __int64)`
- caller_count: `21`
- callee_count: `32`
- tags: `authz_impersonation`

## callers

- `0x180015e50`
- `0x180016160`
- `0x180016b60`
- `0x180016e20`
- `0x180017290`
- `0x180018ba0`
- `0x180019190`
- `0x180019380`
- `0x180019580`
- `0x180019830`
- `0x18001acf0`
- `0x18001bb00`
- `0x18001bcb0`
- `0x18001bef0`
- `0x18001c070`
- `0x18001c330`
- `0x18001c550`
- `0x18001c760`
- `0x18001cfb0`
- `0x18001d1b0`
- `0x18001d3a0`

## callees

- `0x180002ab0`
- `0x180002fa4`
- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x1800083b4`
- `0x1800084bc`
- `0x180008788`
- `0x180008b60`
- `0x180008b8c`
- `0x180009424`
- `0x180010d38`
- `0x180010ee0`
- `0x180011138`
- `0x180011314`
- `0x18001137c`
- `0x18001db80`
- `0x180022aa0`
- `0x180022b20`
- `0x1800234a4`
- `0x1800234c8`
- `0x180023ce0`
- `0x180023d04`
- `0x180023d28`
- `0x180023e64`
- `0x180025944`
- `0x180025a34`
- `0x180026bfc`
- `0x1800288b4`
- `0x180028904`
- `0x1800360ac`
- `0x18003aab0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180023f1b`
- `ADVAPI32!GetTokenInformation` at `0x180023f6d`
- `ADVAPI32!GetTokenInformation` at `0x18002403e`
- `ADVAPI32!GetTokenInformation` at `0x1800241e1`
- `ADVAPI32!GetTokenInformation` at `0x180023f6d`
- `ADVAPI32!GetTokenInformation` at `0x18002403e`
- `ADVAPI32!GetTokenInformation` at `0x1800241e1`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800240d5`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800240d5`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180024113`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002441d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002441d`

## string_xrefs

- `0x180023efc`: `CSyncStateManager::AddImpersonatingUser`

## pseudocode

```c
__int64 __fastcall CSyncStateManager::AddImpersonatingUser(CSyncStateManager *this, __int64 a2)
{
  _BYTE *v4; // rax
  char v5; // cl
  void *ImpersonatingUserToken; // rax
  HANDLE v7; // r14
  __int64 v8; // rcx
  void (__stdcall **v9)(PVOID); // rax
  void (__stdcall *v10)(PVOID); // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // r10
  __int64 v14; // rax
  __int64 v15; // r10
  __int64 v16; // r10
  CUserStateManager *v17; // r11
  __int64 v18; // rax
  __int64 v19; // r8
  _QWORD *v20; // rax
  __int64 v21; // rcx
  _QWORD *v22; // r8
  __int64 v23; // rax
  void (__stdcall *v25)(PVOID); // [rsp+48h] [rbp-89h] BYREF
  int LastFailureAsHRESULT; // [rsp+50h] [rbp-81h] BYREF
  int v27; // [rsp+54h] [rbp-7Dh]
  char v28; // [rsp+58h] [rbp-79h]
  const char *v29; // [rsp+60h] [rbp-71h]
  __int64 v30; // [rsp+68h] [rbp-69h]
  CUserStateManager *pExceptionObject[2]; // [rsp+70h] [rbp-61h] BYREF
  DWORD ReturnLength; // [rsp+80h] [rbp-51h] BYREF
  DWORD SessionId; // [rsp+84h] [rbp-4Dh] BYREF
  int TokenInformation; // [rsp+88h] [rbp-49h] BYREF
  __int64 v35[2]; // [rsp+90h] [rbp-41h] BYREF
  int v36; // [rsp+A0h] [rbp-31h]
  DWORD pBytesReturned; // [rsp+A4h] [rbp-2Dh] BYREF
  LPWSTR ppBuffer; // [rsp+A8h] [rbp-29h] BYREF
  DWORD v39; // [rsp+B0h] [rbp-21h] BYREF
  __int64 v40; // [rsp+B8h] [rbp-19h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+C0h] [rbp-11h] BYREF
  char v42; // [rsp+C8h] [rbp-9h]
  HANDLE TokenHandle[2]; // [rsp+D0h] [rbp-1h] BYREF
  _BYTE v44[8]; // [rsp+E0h] [rbp+Fh] BYREF
  _BYTE v45[16]; // [rsp+E8h] [rbp+17h] BYREF

  v36 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_7:
      v5 = 0;
      goto LABEL_8;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_f5ae0f942fdc3eab058c35939ac72ca3_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( (v4[68] & 8) == 0 )
    goto LABEL_7;
  v5 = 1;
  if ( v4[65] < 6u )
    goto LABEL_7;
LABEL_8:
  LastFailureAsHRESULT = 0;
  v27 = 39;
  v28 = v5;
  v29 = "CSyncStateManager::AddImpersonatingUser";
  v30 = 0;
  CSyncStateManager::RemoveClosedSessions(this);
  ImpersonatingUserToken = CSyncStateManager::FindImpersonatingUserToken();
  std::shared_ptr<void>::shared_ptr<void>(TokenHandle, ImpersonatingUserToken, CloseHandle);
  v7 = TokenHandle[0];
  CSyncStateManager::FindUserSidFromToken(a2, TokenHandle[0]);
  v36 = 1;
  TokenInformation = 0;
  ReturnLength = 0;
  if ( !GetTokenInformation(v7, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength) )
  {
    HIWORD(v27) = 57;
    LODWORD(pExceptionObject[0]) = EcsGetLastFailureAsHRESULT();
    throw (long *)pExceptionObject;
  }
  LOWORD(v27) = 57;
  LastFailureAsHRESULT = 0;
  if ( !TokenInformation )
  {
    LastFailureAsHRESULT = -2134375675;
    HIWORD(v27) = 61;
    LODWORD(pExceptionObject[0]) = -2134375675;
    throw (long *)pExceptionObject;
  }
  LOWORD(v27) = 61;
  LastFailureAsHRESULT = 0;
  if ( TokenInformation == 1 )
  {
    LastFailureAsHRESULT = -2134375675;
    HIWORD(v27) = 62;
    LODWORD(pExceptionObject[0]) = -2134375675;
    throw (long *)pExceptionObject;
  }
  LOWORD(v27) = 62;
  SessionId = 0;
  LastFailureAsHRESULT = 0;
  if ( !GetTokenInformation(v7, TokenSessionId, &SessionId, 4u, &ReturnLength) )
  {
    HIWORD(v27) = 76;
    LODWORD(pExceptionObject[0]) = EcsGetLastFailureAsHRESULT();
    throw (long *)pExceptionObject;
  }
  LOWORD(v27) = 76;
  LastFailureAsHRESULT = 0;
  if ( !SessionId )
  {
    LastFailureAsHRESULT = -2134375650;
    HIWORD(v27) = 78;
    LODWORD(pExceptionObject[0]) = -2134375650;
    throw (long *)pExceptionObject;
  }
  LOWORD(v27) = 78;
  ppBuffer = 0;
  pBytesReturned = 0;
  LastFailureAsHRESULT = 0;
  if ( !WTSQuerySessionInformationW(0, SessionId, WTSSessionInfo, &ppBuffer, &pBytesReturned) )
  {
    HIWORD(v27) = 86;
    LODWORD(pExceptionObject[0]) = EcsGetLastFailureAsHRESULT();
    throw (long *)pExceptionObject;
  }
  LastFailureAsHRESULT = 0;
  LOWORD(v27) = 86;
  v25 = WTSFreeMemory;
  std::unique_ptr<_WTSINFOW,void (*)(void *)>::unique_ptr<_WTSINFOW,void (*)(void *)>(v45, ppBuffer, &v25);
  v8 = *((_QWORD *)ppBuffer + 25);
  v39 = SessionId;
  v40 = v8;
  CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(&lpCriticalSection, (char *)this + 120);
  std::_Tree<std::_Tmap_traits<TSSessionInfo,std::set<std::wstring>,TSSessionInfo_Less,std::allocator<std::pair<TSSessionInfo const,std::set<std::wstring>>>,0>>::find(
    (char *)this + 16,
    &v25,
    &v39);
  std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PartnershipSyncState>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PartnershipSyncState>>>,0>>::find(
    this,
    &v25,
    a2);
  v9 = (void (__stdcall **)(PVOID))std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::end(
                                     this,
                                     pExceptionObject);
  v10 = v25;
  if ( v25 == *v9 )
    goto LABEL_34;
  v11 = std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_SYNC_GID const,FileUploadStatus>>>>::operator->(&v25);
  if ( *(_BYTE *)(std::shared_ptr<CSyncEngineRunner>::operator-><CSyncEngineRunner,0>(v11 + 32) + 248) )
  {
    LODWORD(pExceptionObject[0]) = 1;
    ReturnLength = 0;
    if ( !GetTokenInformation(v7, TokenElevationType, pExceptionObject, 4u, &ReturnLength) )
    {
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      HIWORD(v27) = 108;
      LODWORD(v25) = LastFailureAsHRESULT;
      throw (long *)&v25;
    }
    LastFailureAsHRESULT = 0;
    LOWORD(v27) = 108;
    if ( LODWORD(pExceptionObject[0]) == 3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_f5ae0f942fdc3eab058c35939ac72ca3_Traceguids);
      }
      std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<CUserStateManager>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CUserStateManager>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CUserStateManager>>>>>,0>(
        this,
        &v25,
        v10);
LABEL_34:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
      {
        v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
        WPP_SF_S(*(_QWORD *)(v15 + 56), 14, WPP_f5ae0f942fdc3eab058c35939ac72ca3_Traceguids, v14);
      }
      v25 = (void (__stdcall *)(PVOID))operator new(0x120u);
      pExceptionObject[0] = (CUserStateManager *)v35;
      std::shared_ptr<CSyncStateManager>::shared_ptr<CSyncStateManager>(v35);
      std::_Ptr_base<IDataTransferProgressCallback>::_Copy_construct_from<IDataTransferProgressCallback>(
        v35,
        TokenHandle);
      v18 = CUserStateManager::CUserStateManager(v17, (__int64)this + 64, (__int64)v35, (__int64)this + 96, v16);
      std::shared_ptr<CUserStateManager>::shared_ptr<CUserStateManager>(pExceptionObject, v18);
      std::map<std::wstring,std::shared_ptr<CUserStateManager>>::operator[](this, a2);
      std::shared_ptr<CSyncStateManager>::shared_ptr<CSyncStateManager>(v35);
      std::_Ptr_base<IDataTransferProgressCallback>::_Copy_construct_from<IDataTransferProgressCallback>(
        v35,
        pExceptionObject);
      std::shared_ptr<IDataTransferProgressCallback>::swap(v35, v19);
      std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(v35);
      std::_Tree<std::_Tmap_traits<TSSessionInfo,std::set<std::wstring>,TSSessionInfo_Less,std::allocator<std::pair<TSSessionInfo const,std::set<std::wstring>>>,0>>::find(
        (char *)this + 16,
        &v25,
        &v39);
      v20 = (_QWORD *)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::end(
                        (char *)this + 16,
                        v44);
      if ( *v22 == *v20 )
      {
        v23 = std::map<TSSessionInfo,std::set<std::wstring>,TSSessionInfo_Less,std::allocator<std::pair<TSSessionInfo const,std::set<std::wstring>>>>::operator[](
                v21,
                &v39);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
          v23,
          v35,
          a2);
      }
      CUserStateManager::RefreshState(pExceptionObject[0], *((_DWORD *)this + 42));
      std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(pExceptionObject);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
    WPP_SF_S(*(_QWORD *)(v13 + 56), 13, WPP_f5ae0f942fdc3eab058c35939ac72ca3_Traceguids, v12);
  }
  if ( v42 )
  {
    LeaveCriticalSection(lpCriticalSection);
    v42 = 0;
  }
  std::unique_ptr<_WTSINFOW,void (*)(void *)>::~unique_ptr<_WTSINFOW,void (*)(void *)>(v45);
  std::_Ptr_base<CEcsWebRequest::RequestBody>::_Decref(TokenHandle);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&LastFailureAsHRESULT);
  return a2;
}

```

## disassembly

```asm
0x180023e64  mov     rax, rsp
0x180023e67  mov     [rax+8], rbx
0x180023e6b  mov     [rax+18h], rsi
0x180023e6f  mov     [rax+10h], rdx
0x180023e73  push    rbp
0x180023e74  push    rdi
0x180023e75  push    r12
0x180023e77  push    r14
0x180023e79  push    r15
0x180023e7b  lea     rbp, [rax-5Fh]
0x180023e7f  sub     rsp, 100h
0x180023e86  mov     rax, cs:__security_cookie
0x180023e8d  xor     rax, rsp
0x180023e90  mov     [rbp+57h+var_30], rax
0x180023e94  mov     rdi, rdx
0x180023e97  mov     rsi, rcx
0x180023e9a  xor     r12d, r12d
0x180023e9d  mov     [rbp+57h+var_88], r12d
0x180023ea1  lea     rcx, WPP_GLOBAL_Control
0x180023ea8  mov     rax, cs:WPP_GLOBAL_Control
0x180023eaf  cmp     rax, rcx
0x180023eb2  jz      short loc_180023EDC
0x180023eb4  test    byte ptr [rax+44h], 8
0x180023eb8  jz      short loc_180023EEA
0x180023eba  cmp     byte ptr [rax+41h], 6
0x180023ebe  jb      short loc_180023EDC
0x180023ec0  lea     edx, [r12+0Bh]
0x180023ec5  lea     r8, WPP_f5ae0f942fdc3eab058c35939ac72ca3_Traceguids
0x180023ecc  mov     rcx, [rax+38h]
0x180023ed0  call    WPP_SF_
0x180023ed5  mov     rax, cs:WPP_GLOBAL_Control
0x180023edc  test    byte ptr [rax+44h], 8
0x180023ee0  jz      short loc_180023EEA
0x180023ee2  cmp     byte ptr [rax+41h], 6
0x180023ee6  mov     cl, 1
0x180023ee8  jnb     short loc_180023EED
0x180023eea  mov     cl, r12b
0x180023eed  mov     [rsp+120h+var_D8], r12d
0x180023ef2  mov     [rbp+57h+var_D4], 27h ; '''
0x180023ef9  mov     [rbp+57h+var_D0], cl
0x180023efc  lea     rax, aCsyncstatemana_22; "CSyncStateManager::AddImpersonatingUser"
0x180023f03  mov     [rbp+57h+var_C8], rax
0x180023f07  mov     [rbp+57h+var_C0], r12
0x180023f0b  mov     rcx, rsi; this
0x180023f0e  call    ?RemoveClosedSessions@CSyncStateManager@@QEAAXXZ; CSyncStateManager::RemoveClosedSessions(void)
0x180023f13  call    ?FindImpersonatingUserToken@CSyncStateManager@@CAPEAXXZ; CSyncStateManager::FindImpersonatingUserToken(void)
0x180023f18  mov     rdx, rax
0x180023f1b  mov     r8, cs:__imp_CloseHandle
0x180023f22  lea     rcx, [rbp+57h+TokenHandle]
0x180023f26  call    ??$?0XP6AHPEAX@Z$0A@@?$shared_ptr@X@std@@QEAA@PEAXP6AH0@Z@Z; std::shared_ptr<void>::shared_ptr<void>(void *,int (*)(void *))
0x180023f2b  nop
0x180023f2c  mov     r14, [rbp+57h+TokenHandle]
0x180023f30  mov     rdx, r14
0x180023f33  mov     rcx, rdi
0x180023f36  call    ?FindUserSidFromToken@CSyncStateManager@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; CSyncStateManager::FindUserSidFromToken(void *)
0x180023f3b  mov     [rbp+57h+var_88], 1
0x180023f42  mov     [rbp+57h+TokenInformation], r12d
0x180023f46  mov     [rbp+57h+var_A8], r12d
0x180023f4a  mov     eax, [rsp+120h+var_D8]
0x180023f4e  mov     [rsp+120h+var_D8], eax
0x180023f52  lea     rax, [rbp+57h+var_A8]
0x180023f56  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x180023f5b  mov     ebx, 4
0x180023f60  mov     r9d, ebx; TokenInformationLength
0x180023f63  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180023f67  lea     edx, [rbx+5]; TokenInformationClass
0x180023f6a  mov     rcx, r14; TokenHandle
0x180023f6d  call    cs:__imp_GetTokenInformation
0x180023f73  test    eax, eax
0x180023f75  jnz     short loc_180023F9B
0x180023f77  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x180023f7c  mov     [rsp+120h+var_D8], eax
0x180023f80  lea     ecx, [rbx+35h]
0x180023f83  mov     word ptr [rbp+57h+var_D4+2], cx
0x180023f87  mov     dword ptr [rbp+57h+pExceptionObject], eax
0x180023f8a  lea     rdx, _TI1J; pThrowInfo
0x180023f91  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180023f95  call    _CxxThrowException_0
0x180023f9b  mov     [rsp+120h+var_D8], r12d
0x180023fa0  mov     ecx, 39h ; '9'
0x180023fa5  mov     word ptr [rbp+57h+var_D4], cx
0x180023fa9  mov     [rsp+120h+var_D8], r12d
0x180023fae  mov     eax, [rbp+57h+TokenInformation]
0x180023fb1  mov     ecx, 3Dh ; '='
0x180023fb6  test    eax, eax
0x180023fb8  jnz     short loc_180023FDB
0x180023fba  mov     eax, 80C80305h
0x180023fbf  mov     [rsp+120h+var_D8], eax
0x180023fc3  mov     word ptr [rbp+57h+var_D4+2], cx
0x180023fc7  mov     dword ptr [rbp+57h+pExceptionObject], eax
0x180023fca  lea     rdx, _TI1J; pThrowInfo
0x180023fd1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180023fd5  call    _CxxThrowException_0
0x180023fdb  mov     [rsp+120h+var_D8], r12d
0x180023fe0  mov     word ptr [rbp+57h+var_D4], cx
0x180023fe4  mov     [rsp+120h+var_D8], r12d
0x180023fe9  mov     ecx, 3Eh ; '>'
0x180023fee  cmp     eax, 1
0x180023ff1  jnz     short loc_180024014
0x180023ff3  mov     eax, 80C80305h
0x180023ff8  mov     [rsp+120h+var_D8], eax
0x180023ffc  mov     word ptr [rbp+57h+var_D4+2], cx
0x180024000  mov     dword ptr [rbp+57h+pExceptionObject], eax
0x180024003  lea     rdx, _TI1J; pThrowInfo
0x18002400a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002400e  call    _CxxThrowException_0
0x180024014  mov     [rsp+120h+var_D8], r12d
0x180024019  mov     word ptr [rbp+57h+var_D4], cx
0x18002401d  mov     [rbp+57h+SessionId], r12d
0x180024021  mov     [rsp+120h+var_D8], r12d
0x180024026  lea     rax, [rbp+57h+var_A8]
0x18002402a  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18002402f  mov     r9d, ebx; TokenInformationLength
0x180024032  lea     r8, [rbp+57h+SessionId]; TokenInformation
0x180024036  mov     edx, 0Ch; TokenInformationClass
0x18002403b  mov     rcx, r14; TokenHandle
0x18002403e  call    cs:__imp_GetTokenInformation
0x180024044  test    eax, eax
0x180024046  jnz     short loc_18002406E
0x180024048  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18002404d  mov     [rsp+120h+var_D8], eax
0x180024051  mov     ecx, 4Ch ; 'L'
0x180024056  mov     word ptr [rbp+57h+var_D4+2], cx
0x18002405a  mov     dword ptr [rbp+57h+pExceptionObject], eax
0x18002405d  lea     rdx, _TI1J; pThrowInfo
0x180024064  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180024068  call    _CxxThrowException_0
0x18002406e  mov     [rsp+120h+var_D8], r12d
0x180024073  mov     ecx, 4Ch ; 'L'
0x180024078  mov     word ptr [rbp+57h+var_D4], cx
0x18002407c  mov     [rsp+120h+var_D8], r12d
0x180024081  mov     edx, [rbp+57h+SessionId]; SessionId
0x180024084  lea     eax, [rcx+2]
0x180024087  test    edx, edx
0x180024089  jnz     short loc_1800240AC
0x18002408b  mov     ecx, 80C8031Eh
0x180024090  mov     [rsp+120h+var_D8], ecx
0x180024094  mov     word ptr [rbp+57h+var_D4+2], ax
0x180024098  mov     dword ptr [rbp+57h+pExceptionObject], ecx
0x18002409b  lea     rdx, _TI1J; pThrowInfo
0x1800240a2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800240a6  call    _CxxThrowException_0
0x1800240ac  mov     [rsp+120h+var_D8], r12d
0x1800240b1  mov     word ptr [rbp+57h+var_D4], ax
0x1800240b5  mov     [rbp+57h+ppBuffer], r12
0x1800240b9  mov     [rbp+57h+pBytesReturned], r12d
0x1800240bd  mov     [rsp+120h+var_D8], r12d
0x1800240c2  lea     rax, [rbp+57h+pBytesReturned]
0x1800240c6  mov     [rsp+120h+ReturnLength], rax; pBytesReturned
0x1800240cb  lea     r9, [rbp+57h+ppBuffer]; ppBuffer
0x1800240cf  xor     ecx, ecx; hServer
0x1800240d1  lea     r8d, [rcx+18h]; WTSInfoClass
0x1800240d5  call    cs:__imp_WTSQuerySessionInformationW
0x1800240db  test    eax, eax
0x1800240dd  jnz     short loc_180024105
0x1800240df  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800240e4  mov     [rsp+120h+var_D8], eax
0x1800240e8  mov     ecx, 56h ; 'V'
0x1800240ed  mov     word ptr [rbp+57h+var_D4+2], cx
0x1800240f1  mov     dword ptr [rbp+57h+pExceptionObject], eax
0x1800240f4  lea     rdx, _TI1J; pThrowInfo
0x1800240fb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800240ff  call    _CxxThrowException_0
0x180024105  mov     [rsp+120h+var_D8], r12d
0x18002410a  mov     ecx, 56h ; 'V'
0x18002410f  mov     word ptr [rbp+57h+var_D4], cx
0x180024113  mov     rax, cs:__imp_WTSFreeMemory
0x18002411a  mov     [rsp+120h+var_E0], rax
0x18002411f  lea     r8, [rsp+120h+var_E0]
0x180024124  mov     rdx, [rbp+57h+ppBuffer]
0x180024128  lea     rcx, [rbp+57h+var_40]
0x18002412c  call    ??$?0P6AXPEAX@Z$0A@@?$unique_ptr@U_WTSINFOW@@P6AXPEAX@Z@std@@QEAA@PEAU_WTSINFOW@@$$QEAP6AXPEAX@Z@Z; std::unique_ptr<_WTSINFOW,void (*)(void *)>::unique_ptr<_WTSINFOW,void (*)(void *)>(_WTSINFOW *,void (*&&)(void *))
0x180024131  nop
0x180024132  mov     rax, [rbp+57h+ppBuffer]
0x180024136  mov     rcx, [rax+0C8h]
0x18002413d  mov     eax, [rbp+57h+SessionId]
0x180024140  mov     [rbp+57h+var_78], eax
0x180024143  mov     [rbp+57h+var_70], rcx
0x180024147  lea     rdx, [rsi+78h]
0x18002414b  lea     rcx, [rbp+57h+lpCriticalSection]
0x18002414f  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x180024154  nop
0x180024155  lea     r15, [rsi+10h]
0x180024159  lea     r8, [rbp+57h+var_78]
0x18002415d  lea     rdx, [rsp+120h+var_E0]
0x180024162  mov     rcx, r15
0x180024165  call    ?find@?$_Tree@V?$_Tmap_traits@UTSSessionInfo@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@UTSSessionInfo_Less@@V?$allocator@U?$pair@$$CBUTSSessionInfo@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUTSSessionInfo@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@std@@@std@@@2@AEBUTSSessionInfo@@@Z; std::_Tree<std::_Tmap_traits<TSSessionInfo,std::set<std::wstring>,TSSessionInfo_Less,std::allocator<std::pair<TSSessionInfo const,std::set<std::wstring>>>,0>>::find(TSSessionInfo const &)
0x18002416a  mov     r8, rdi
0x18002416d  lea     rdx, [rsp+120h+var_E0]
0x180024172  mov     rcx, rsi
0x180024175  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPartnershipSyncState@@U?$default_delete@UPartnershipSyncState@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPartnershipSyncState@@U?$default_delete@UPartnershipSyncState@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@UPartnershipSyncState@@U?$default_delete@UPartnershipSyncState@@@std@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<PartnershipSyncState>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<PartnershipSyncState>>>,0>>::find(std::wstring const &)
0x18002417a  lea     rdx, [rbp+57h+pExceptionObject]
0x18002417e  mov     rcx, rsi
0x180024181  call    ?end@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::end(void)
0x180024186  mov     rbx, [rsp+120h+var_E0]
0x18002418b  cmp     rbx, [rax]
0x18002418e  jz      loc_1800242C3
0x180024194  lea     rcx, [rsp+120h+var_E0]
0x180024199  call    ??C?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_SYNC_GID@@UFileUploadStatus@@@std@@@std@@@std@@@std@@QEBAPEAU?$pair@$$CBU_SYNC_GID@@UFileUploadStatus@@@1@XZ; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_SYNC_GID const,FileUploadStatus>>>>::operator->(void)
0x18002419e  lea     rcx, [rax+20h]
0x1800241a2  call    ??$?CVCSyncEngineRunner@@$0A@@?$shared_ptr@VCSyncEngineRunner@@@std@@QEBAPEAVCSyncEngineRunner@@XZ; std::shared_ptr<CSyncEngineRunner>::operator-><CSyncEngineRunner,0>(void)
0x1800241a7  cmp     [rax+0F8h], r12b
0x1800241ae  jz      loc_180024271
0x1800241b4  mov     dword ptr [rbp+57h+pExceptionObject], 1
0x1800241bb  mov     [rbp+57h+var_A8], r12d
0x1800241bf  mov     eax, [rsp+120h+var_D8]
0x1800241c3  mov     [rsp+120h+var_D8], eax
0x1800241c7  lea     rax, [rbp+57h+var_A8]
0x1800241cb  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x1800241d0  mov     r9d, 4; TokenInformationLength
0x1800241d6  lea     r8, [rbp+57h+pExceptionObject]; TokenInformation
0x1800241da  lea     edx, [r9+0Eh]; TokenInformationClass
0x1800241de  mov     rcx, r14; TokenHandle
0x1800241e1  call    cs:__imp_GetTokenInformation
0x1800241e7  test    eax, eax
0x1800241e9  jnz     short loc_180024213
0x1800241eb  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800241f0  mov     [rsp+120h+var_D8], eax
0x1800241f4  mov     ecx, 6Ch ; 'l'
0x1800241f9  mov     word ptr [rbp+57h+var_D4+2], cx
0x1800241fd  mov     dword ptr [rsp+120h+var_E0], eax
0x180024201  lea     rdx, _TI1J; pThrowInfo
0x180024208  lea     rcx, [rsp+120h+var_E0]; pExceptionObject
0x18002420d  call    _CxxThrowException_0
0x180024213  mov     [rsp+120h+var_D8], r12d
0x180024218  mov     ecx, 6Ch ; 'l'
0x18002421d  mov     word ptr [rbp+57h+var_D4], cx
0x180024221  cmp     dword ptr [rbp+57h+pExceptionObject], 3
0x180024225  jnz     loc_180024413
0x18002422b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024232  lea     r14, WPP_GLOBAL_Control
0x180024239  cmp     rcx, r14
0x18002423c  jz      short loc_18002425F
0x18002423e  test    byte ptr [rcx+44h], 8
0x180024242  jz      short loc_18002425F
0x180024244  cmp     byte ptr [rcx+41h], 4
0x180024248  jb      short loc_18002425F
0x18002424a  mov     edx, 0Ch
0x18002424f  lea     r8, WPP_f5ae0f942fdc3eab058c35939ac72ca3_Traceguids
0x180024256  mov     rcx, [rcx+38h]
0x18002425a  call    WPP_SF_
0x18002425f  mov     r8, rbx
0x180024262  lea     rdx, [rsp+120h+var_E0]
0x180024267  mov     rcx, rsi
0x18002426a  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCUserStateManager@@@2@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCUserStateManager@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCUserStateManager@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VCUserStateManager@@@2@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<CUserStateManager>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::shared_ptr<CUserStateManager>>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CUserStateManager>>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CUserStateManager>>>>>)
0x18002426f  jmp     short loc_1800242CA
0x180024271  mov     r10, cs:WPP_GLOBAL_Control
0x180024278  lea     r14, WPP_GLOBAL_Control
0x18002427f  cmp     r10, r14
0x180024282  jz      loc_180024413
0x180024288  test    byte ptr [r10+44h], 8
0x18002428d  jz      loc_180024413
0x180024293  cmp     byte ptr [r10+41h], 4
0x180024298  jb      loc_180024413
0x18002429e  mov     rcx, rdi
0x1800242a1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800242a6  mov     edx, 0Dh
0x1800242ab  mov     r9, rax
0x1800242ae  lea     r8, WPP_f5ae0f942fdc3eab058c35939ac72ca3_Traceguids
0x1800242b5  mov     rcx, [r10+38h]
0x1800242b9  call    WPP_SF_S
0x1800242be  jmp     loc_180024413
0x1800242c3  lea     r14, WPP_GLOBAL_Control
0x1800242ca  mov     r10, cs:WPP_GLOBAL_Control
0x1800242d1  cmp     r10, r14
0x1800242d4  jz      short loc_180024304
0x1800242d6  test    byte ptr [r10+44h], 8
0x1800242db  jz      short loc_180024304
0x1800242dd  cmp     byte ptr [r10+41h], 4
0x1800242e2  jb      short loc_180024304
0x1800242e4  mov     rcx, rdi
0x1800242e7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800242ec  mov     edx, 0Eh
0x1800242f1  mov     r9, rax
0x1800242f4  lea     r8, WPP_f5ae0f942fdc3eab058c35939ac72ca3_Traceguids
0x1800242fb  mov     rcx, [r10+38h]
0x1800242ff  call    WPP_SF_S
0x180024304  mov     ecx, 120h; Size
0x180024309  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002430e  mov     r11, rax
0x180024311  mov     [rsp+120h+var_E0], rax
0x180024316  mov     r10, [rsi+0A0h]
0x18002431d  lea     rax, [rbp+57h+var_98]
0x180024321  mov     [rbp+57h+pExceptionObject], rax
0x180024325  lea     rcx, [rbp+57h+var_98]
0x180024329  call    ??0?$shared_ptr@VCSyncStateManager@@@std@@QEAA@$$T@Z; std::shared_ptr<CSyncStateManager>::shared_ptr<CSyncStateManager>(std::nullptr_t)
0x18002432e  lea     rdx, [rbp+57h+TokenHandle]
0x180024332  lea     rcx, [rbp+57h+var_98]
0x180024336  call    ??$_Copy_construct_from@UIDataTransferProgressCallback@@@?$_Ptr_base@UIDataTransferProgressCallback@@@std@@IEAAXAEBV?$shared_ptr@UIDataTransferProgressCallback@@@1@@Z; std::_Ptr_base<IDataTransferProgressCallback>::_Copy_construct_from<IDataTransferProgressCallback>(std::shared_ptr<IDataTransferProgressCallback> const &)
0x18002433b  nop
0x18002433c  lea     rax, [rsi+60h]
0x180024340  lea     rcx, [rsi+40h]
0x180024344  lea     r9, [rsi+50h]
0x180024348  lea     r8, [rsi+30h]
0x18002434c  lea     rdx, [rsi+20h]
0x180024350  mov     [rsp+120h+var_E8], r10; __int64
0x180024355  mov     [rsp+120h+var_F0], rax; __int64
0x18002435a  lea     rax, [rbp+57h+var_98]
0x18002435e  mov     [rsp+120h+var_F8], rax; __int64
0x180024363  mov     [rsp+120h+ReturnLength], rcx; __int64
  ... truncated ...
```
