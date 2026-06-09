# CTemplate::Deliver(CHitObj *)

- ea: `0x180010630`
- end: `0x1800108bc`
- name: `?Deliver@CTemplate@@QEAAJPEAVCHitObj@@@Z`
- size: `652`
- prototype: `int(CTemplate *__hidden this, struct CHitObj *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800033e8`
- `0x180003424`
- `0x180010630`
- `0x180014898`
- `0x180016b50`
- `0x180019e7c`
- `0x180023dd0`
- `0x180034a54`
- `0x1800432d8`
- `0x180044350`
- `0x18004746c`
- `0x1800474f8`
- `0x180049124`
- `0x18005b608`
- `0x18005c1e0`
- `0x18005d7e4`
- `0x18005fa20`
- `0x180062418`
- `0x180064010`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x18002acbf`
- `ADVAPI32!EqualSid` at `0x18002acd3`
- `ADVAPI32!EqualSid` at `0x18002acbf`
- `ADVAPI32!EqualSid` at `0x18002acd3`
- `ADVAPI32!AccessCheck` at `0x1800107b2`
- `ADVAPI32!AccessCheck` at `0x1800107b2`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18002ad34`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x18002ad34`
- `KERNEL32!HeapFree` at `0x18002af30`
- `KERNEL32!HeapFree` at `0x18002af7e`
- `KERNEL32!HeapFree` at `0x18002af30`
- `KERNEL32!HeapFree` at `0x18002af7e`
- `KERNEL32!LeaveCriticalSection` at `0x18002ac66`
- `KERNEL32!LeaveCriticalSection` at `0x18002af66`
- `KERNEL32!LeaveCriticalSection` at `0x18002ac66`
- `KERNEL32!LeaveCriticalSection` at `0x18002af66`
- `KERNEL32!WaitForSingleObject` at `0x1800108ad`
- `KERNEL32!WaitForSingleObject` at `0x1800108ad`
- `KERNEL32!CloseHandle` at `0x18002ad8a`
- `KERNEL32!CloseHandle` at `0x18002ad8a`
- `KERNEL32!EnterCriticalSection` at `0x18002ac43`
- `KERNEL32!EnterCriticalSection` at `0x18002af15`
- `KERNEL32!EnterCriticalSection` at `0x18002ac43`
- `KERNEL32!EnterCriticalSection` at `0x18002af15`
- `KERNEL32!GetTickCount` at `0x18002af53`
- `KERNEL32!GetTickCount` at `0x18002af53`
- `iisutil!PuDbgPrint` at `0x18002abba`
- `iisutil!PuDbgPrint` at `0x18002abba`

## string_xrefs

- `0x18002ab9d`: `inetsrv\iis\svcs\cmp\asp\template.cpp`
- `0x18002abae`: `template compile failed with %08x\n`
- `0x18002ab8f`: `CTemplate::Deliver`

## pseudocode

```c
__int64 __fastcall CTemplate::Deliver(CTemplate *this, struct CHitObj *a2)
{
  unsigned int v2; // r15d
  bool v4; // zf
  __int64 v6; // r14
  PSID v7; // rdx
  void *v8; // r10
  unsigned int FileAttributes; // r13d
  int v10; // r12d
  void *v11; // rdi
  int v12; // r9d
  PSID v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rcx
  unsigned int (__fastcall *v17)(__int64, __int64, GUID **, _QWORD, _QWORD); // rax
  const struct _GUID *v18; // rdx
  int v20; // ebx
  unsigned int v21; // eax
  CTemplate *v22; // rcx
  int SIDFromTokenHandle; // eax
  CTemplate *v24; // rcx
  unsigned int v25; // r8d
  __int64 v26; // rax
  __int64 v27; // r12
  CIsapiReqInfo *v28; // rcx
  const unsigned __int16 **v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r9
  const WCHAR *v32; // r8
  const struct _GUID *v33; // rdx
  const struct _GUID *v34; // rdx
  void *v35; // r8
  CHitObj *v36; // rcx
  CHitObj *v37; // rcx
  PSID pSid2; // [rsp+40h] [rbp-C0h] BYREF
  PSID pSid1; // [rsp+48h] [rbp-B8h]
  void *v40; // [rsp+50h] [rbp-B0h]
  void *v41; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v42; // [rsp+60h] [rbp-A0h]
  DWORD PrivilegeSetLength; // [rsp+64h] [rbp-9Ch] BYREF
  BOOL AccessStatus; // [rsp+68h] [rbp-98h] BYREF
  int v45; // [rsp+6Ch] [rbp-94h]
  unsigned int v46; // [rsp+70h] [rbp-90h] BYREF
  HANDLE TokenHandle; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hToken; // [rsp+80h] [rbp-80h] BYREF
  DWORD GrantedAccess; // [rsp+88h] [rbp-78h] BYREF
  __int64 v50; // [rsp+90h] [rbp-70h]
  GUID *v51; // [rsp+98h] [rbp-68h] BYREF
  __int128 v52; // [rsp+A0h] [rbp-60h]
  GENERIC_MAPPING GenericMapping; // [rsp+B0h] [rbp-50h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+C0h] [rbp-40h] BYREF
  CHAR MultiByteStr[1024]; // [rsp+140h] [rbp+40h] BYREF

  v2 = 0;
  v4 = (*((_BYTE *)this + 392) & 8) == 0;
  hToken = 0;
  v6 = 0;
  TokenHandle = 0;
  if ( v4 )
    WaitForSingleObject(*((HANDLE *)this + 7), 0xFFFFFFFF);
  if ( a2 )
    v6 = *((_QWORD *)a2 + 8);
  if ( *((_QWORD *)this + 8) )
  {
    if ( (*((_DWORD *)a2 + 2) & 0xF0000) != 0x10000 )
      return 0;
    v4 = (*((_DWORD *)this + 98) & 0x2000) == 0;
    v7 = 0;
    v8 = (void *)*((_QWORD *)a2 + 12);
    FileAttributes = 0;
    v40 = v8;
    v10 = 0;
    pSid2 = 0;
    v11 = 0;
    PrivilegeSetLength = 128;
    GrantedAccess = 0;
    AccessStatus = 0;
    GenericMapping.GenericRead = 1179785;
    GenericMapping.GenericWrite = 1179926;
    GenericMapping.GenericExecute = 1179808;
    GenericMapping.GenericAll = 2032127;
    PrivilegeSet.PrivilegeCount = 0;
    v46 = 0;
    v41 = 0;
    if ( v4 )
    {
      v12 = -2147467259;
      v42 = 0;
      v13 = 0;
      pSid1 = 0;
    }
    else
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
      v21 = *((_DWORD *)this + 126);
      pSid1 = (PSID)*((_QWORD *)this + 65);
      v42 = v21;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
      SIDFromTokenHandle = CTemplate::GetSIDFromTokenHandle(v22, *((void **)a2 + 12), &pSid2, &v41, &v46);
      v7 = pSid2;
      v12 = SIDFromTokenHandle;
      v8 = v40;
      v13 = pSid1;
      v11 = v41;
    }
    v45 = v12;
    if ( !*((_DWORD *)this + 74) )
    {
LABEL_20:
      if ( v11 )
        HeapFree(CTemplate::sm_hSmallHeap, 0, v11);
      goto LABEL_22;
    }
    while ( 1 )
    {
      v50 = 8LL * v2;
      v14 = *((_QWORD *)this + 34) + v50;
      if ( (*(_BYTE *)(*(_QWORD *)v14 + 76LL) & 1) == 0 || g_fUNCChangeNotificationEnabled )
      {
        if ( !*(_QWORD *)(*(_QWORD *)v14 + 64LL) )
          goto LABEL_18;
        PrivilegeSetLength = 128;
        if ( !AccessCheck(
                *(PSECURITY_DESCRIPTOR *)(*(_QWORD *)v14 + 64LL),
                v8,
                0x120089u,
                &GenericMapping,
                &PrivilegeSet,
                &PrivilegeSetLength,
                &GrantedAccess,
                &AccessStatus) )
          return 2147500037LL;
        if ( !AccessStatus )
          goto LABEL_74;
        if ( v6 )
        {
          v15 = *(_QWORD *)(v6 + 8);
          v51 = &`ActiveServerPagesASPTraceProvider::GetProviderGuid'::`2'::ProviderGuid;
          v16 = *(_QWORD *)(v15 + 8);
          v17 = *(unsigned int (__fastcall **)(__int64, __int64, GUID **, _QWORD, _QWORD))(v15 + 184);
          v52 = 0;
          if ( v17(v16, 1044, &v51, 0, 0) )
          {
            if ( DWORD2(v52) && DWORD1(v52) >= 4 )
              AspReqEvents::ASP_END_CACHE_ACCESS::RaiseEvent(
                *(struct _EXTENSION_CONTROL_BLOCK **)(v6 + 8),
                v18,
                FileAttributes,
                2u);
          }
        }
      }
      else if ( !v13
             || v12 < 0
             || !EqualSid(v13, v7)
             || EqualSid(pSid1, pSid2) && (unsigned int)CTemplate::CheckTTLTimingWindow(v24, v42, v25) )
      {
        v26 = *((_QWORD *)this + 34);
        v27 = v50;
        v28 = (CIsapiReqInfo *)*((_QWORD *)a2 + 8);
        hToken = 0;
        TokenHandle = 0;
        v29 = *(const unsigned __int16 ***)(v50 + v26);
        LODWORD(v41) = 0;
        if ( (int)CIsapiReqInfo::GetVirtualPathTokenW(v28, *v29, &hToken) >= 0 )
        {
          AspDoRevertHack(&TokenHandle);
          LODWORD(v41) = ImpersonateLoggedOnUser(hToken);
          if ( !(_DWORD)v41 )
            AspUndoRevertHack(&TokenHandle);
        }
        FileAttributes = AspGetFileAttributes(
                           *(const unsigned __int16 **)(*(_QWORD *)(v27 + *((_QWORD *)this + 34)) + 8LL),
                           0,
                           0,
                           0,
                           0);
        if ( (_DWORD)v41 )
          AspUndoRevertHack(&TokenHandle);
        v30 = (__int64)hToken;
        if ( hToken )
          CloseHandle(hToken);
        if ( (FileAttributes & 0x80000000) == 0 )
        {
          if ( v6
            && (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                               *(struct _EXTENSION_CONTROL_BLOCK **)(v6 + 8),
                               4u) )
          {
            AspReqEvents::ASP_END_CACHE_ACCESS::RaiseEvent(
              *(struct _EXTENSION_CONTROL_BLOCK **)(v6 + 8),
              v34,
              FileAttributes,
              3u);
          }
        }
        else
        {
          if ( FileAttributes == -2147024894 )
            return 2147536897LL;
          if ( FileAttributes == -2147024891 )
          {
LABEL_74:
            HandleAccessFailure(a2);
            return 2147536900LL;
          }
          if ( FileAttributes != -2147024775 )
          {
            if ( FileAttributes + 2147024845 > 0x10
              || (v30 = 73997, !_bittest((const int *)&v30, FileAttributes + 2147024845)) )
            {
              if ( FileAttributes != -2147023665 )
                return FileAttributes;
            }
          }
          LODWORD(v41) = 0;
          CAspRegistryParams::GetDisableCachedResponseOnUNCAccessFailure(
            (CAspRegistryParams *)v30,
            (unsigned int *)&v41);
          if ( !_InterlockedCompareExchange(&g_fUNCFailureLogged, 1, 0) )
          {
            v31 = -1;
            v32 = *(const WCHAR **)(*(_QWORD *)(v27 + *((_QWORD *)this + 34)) + 8LL);
            do
              ++v31;
            while ( v32[v31] );
            WstrToMBstrEx(MultiByteStr, 1024, v32, v31, *((_DWORD *)this + 100));
            MSG_Error(0xC00001F4, MultiByteStr, FileAttributes, 0);
          }
          if ( v6
            && (unsigned int)ActiveServerPagesASPTraceProvider::CheckTracingEnabled(
                               *(struct _EXTENSION_CONTROL_BLOCK **)(v6 + 8),
                               4u) )
          {
            AspReqEvents::ASP_END_CACHE_ACCESS::RaiseEvent(
              *(struct _EXTENSION_CONTROL_BLOCK **)(v6 + 8),
              v33,
              FileAttributes,
              4u);
          }
          if ( (_DWORD)v41 )
            return FileAttributes;
          FileAttributes = 0;
        }
        v10 = 1;
      }
      v13 = pSid1;
      v8 = v40;
      v7 = pSid2;
LABEL_18:
      if ( ++v2 >= *((_DWORD *)this + 74) )
      {
        if ( !v10 )
          goto LABEL_20;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
        v35 = (void *)*((_QWORD *)this + 64);
        if ( v35 )
          HeapFree(CTemplate::sm_hSmallHeap, 0, v35);
        *((_QWORD *)this + 65) = pSid2;
        *((_DWORD *)this + 132) = v46;
        *((_QWORD *)this + 64) = v11;
        *((_DWORD *)this + 126) = GetTickCount();
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
LABEL_22:
        if ( (*((_DWORD *)this + 98) & 0x400) != 0
          && (!(unsigned int)CHitObj::FHasSession(a2) || (*(_DWORD *)(*((_QWORD *)a2 + 2) + 32LL) & 0x2000) == 0) )
        {
          CHitObj::SetCodePage(v36, *((_DWORD *)this + 100));
        }
        if ( (*((_DWORD *)this + 98) & 0x800) != 0
          && (!(unsigned int)CHitObj::FHasSession(a2) || (*(_DWORD *)(*((_QWORD *)a2 + 2) + 32LL) & 0x4000) == 0) )
        {
          CHitObj::SetLCID(v37, *((_DWORD *)this + 101));
        }
        return FileAttributes;
      }
      v12 = v45;
    }
  }
  if ( (*((_BYTE *)this + 392) & 4) == 0 || *((_DWORD *)this + 92) )
  {
    SendToLog(
      *((_DWORD *)this + 92),
      *((char **)this + 40),
      *((char **)this + 41),
      *((char **)this + 42),
      *((char **)this + 43),
      *((char **)this + 44),
      *((char **)this + 45),
      a2);
    FileAttributes = -2147430397;
    goto LABEL_22;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\cmp\\asp\\template.cpp",
      1828,
      "CTemplate::Deliver",
      "template compile failed with %08x\n",
      *((_DWORD *)this + 93));
  v20 = *((_DWORD *)this + 93);
  if ( v20 < 0 )
  {
    if ( v20 == -2147430396 )
      HandleAccessFailure(a2);
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180010630  push    rbp
0x180010632  push    rbx
0x180010633  push    rsi
0x180010634  push    r14
0x180010636  push    r15
0x180010638  lea     rbp, [rsp-460h]
0x180010640  sub     rsp, 560h
0x180010647  mov     rax, cs:__security_cookie
0x18001064e  xor     rax, rsp
0x180010651  mov     [rbp+480h+var_40], rax
0x180010658  xor     r15d, r15d
0x18001065b  mov     rsi, rdx
0x18001065e  test    byte ptr [rcx+188h], 8
0x180010665  mov     rbx, rcx
0x180010668  mov     [rbp+480h+hToken], r15
0x18001066c  mov     r14d, r15d
0x18001066f  mov     [rsp+580h+TokenHandle], r15
0x180010674  jz      loc_1800108A4
0x18001067a  test    rsi, rsi
0x18001067d  jz      short loc_180010683
0x18001067f  mov     r14, [rsi+40h]
0x180010683  mov     [rsp+580h+arg_10], rdi
0x18001068b  mov     [rsp+580h+var_28], r12
0x180010693  mov     [rsp+580h+var_30], r13
0x18001069b  cmp     [rbx+40h], r15
0x18001069f  jz      loc_18002AB6E
0x1800106a5  mov     eax, [rsi+8]
0x1800106a8  and     eax, 0F0000h
0x1800106ad  cmp     eax, 10000h
0x1800106b2  jnz     loc_1800108B8
0x1800106b8  test    dword ptr [rbx+188h], 2000h
0x1800106c2  mov     rdx, r15; pSid2
0x1800106c5  mov     r10, [rsi+60h]
0x1800106c9  mov     r13d, r15d
0x1800106cc  mov     [rsp+580h+var_530], r10
0x1800106d1  mov     r12d, r15d
0x1800106d4  mov     [rsp+580h+pSid2], rdx
0x1800106d9  mov     rdi, r15
0x1800106dc  mov     [rsp+580h+var_51C], 80h
0x1800106e4  mov     [rbp+480h+var_4F8], r15d
0x1800106e8  mov     [rsp+580h+var_518], r15d
0x1800106ed  mov     [rbp+480h+GenericMapping.GenericRead], 120089h
0x1800106f4  mov     [rbp+480h+GenericMapping.GenericWrite], 120116h
0x1800106fb  mov     [rbp+480h+GenericMapping.GenericExecute], 1200A0h
0x180010702  mov     [rbp+480h+GenericMapping.GenericAll], 1F01FFh
0x180010709  mov     [rbp+480h+var_4C0.PrivilegeCount], r15d
0x18001070d  mov     [rsp+580h+var_510], r15d
0x180010712  mov     [rsp+580h+var_528], r15
0x180010717  jnz     loc_18002AC3C
0x18001071d  mov     r9d, 80004005h
0x180010723  mov     [rsp+580h+var_520], r15d
0x180010728  mov     r8, r15
0x18001072b  mov     [rsp+580h+pSid1], r15
0x180010730  mov     [rsp+580h+var_514], r9d
0x180010735  cmp     [rbx+128h], r12d
0x18001073c  jbe     loc_180010842
0x180010742  mov     eax, r15d
0x180010745  lea     rcx, ds:0[rax*8]
0x18001074d  mov     [rbp+480h+var_4F0], rcx
0x180010751  add     rcx, [rbx+110h]
0x180010758  mov     rax, [rcx]
0x18001075b  test    byte ptr [rax+4Ch], 1
0x18001075f  jnz     loc_18002ACA5
0x180010765  cmp     qword ptr [rax+40h], 0
0x18001076a  jz      loc_180010829
0x180010770  mov     [rsp+580h+var_51C], 80h
0x180010778  lea     rax, [rsp+580h+var_518]
0x18001077d  mov     rcx, [rcx]
0x180010780  lea     r9, [rbp+480h+GenericMapping]; GenericMapping
0x180010784  mov     [rsp+580h+AccessStatus], rax; AccessStatus
0x180010789  mov     r8d, 120089h; DesiredAccess
0x18001078f  lea     rax, [rbp+480h+var_4F8]
0x180010793  mov     rdx, r10; ClientToken
0x180010796  mov     [rsp+580h+GrantedAccess], rax; GrantedAccess
0x18001079b  lea     rax, [rsp+580h+var_51C]
0x1800107a0  mov     rcx, [rcx+40h]; pSecurityDescriptor
0x1800107a4  mov     [rsp+580h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800107a9  lea     rax, [rbp+480h+var_4C0]
0x1800107ad  mov     [rsp+580h+PrivilegeSet], rax; PrivilegeSet
0x1800107b2  call    cs:__imp_AccessCheck
0x1800107b8  test    eax, eax
0x1800107ba  jz      loc_18002AF04
0x1800107c0  cmp     [rsp+580h+var_518], 0
0x1800107c5  jz      loc_18002AEF2
0x1800107cb  test    r14, r14
0x1800107ce  jz      short loc_18001081A
0x1800107d0  mov     rax, [r14+8]
0x1800107d4  lea     rcx, ?ProviderGuid@?1??GetProviderGuid@ActiveServerPagesASPTraceProvider@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `ActiveServerPagesASPTraceProvider::GetProviderGuid(void)'::`2'::ProviderGuid
0x1800107db  mov     [rbp+480h+var_4E8], rcx
0x1800107df  lea     r8, [rbp+480h+var_4E8]
0x1800107e3  xorps   xmm0, xmm0
0x1800107e6  mov     [rsp+580h+PrivilegeSet], 0
0x1800107ef  xor     r9d, r9d
0x1800107f2  mov     edx, 414h
0x1800107f7  mov     rcx, [rax+8]
0x1800107fb  mov     rax, [rax+0B8h]
0x180010802  movdqu  [rbp+480h+var_4E0], xmm0
0x180010807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001080c  test    eax, eax
0x18001080e  jz      short loc_18001081A
0x180010810  cmp     dword ptr [rbp+480h+var_4E0+8], 0
0x180010814  jnz     loc_18002AEBC
0x18001081a  mov     r8, [rsp+580h+pSid1]
0x18001081f  mov     r10, [rsp+580h+var_530]
0x180010824  mov     rdx, [rsp+580h+pSid2]
0x180010829  inc     r15d
0x18001082c  cmp     r15d, [rbx+128h]
0x180010833  jb      loc_18002AEDE
0x180010839  test    r12d, r12d
0x18001083c  jnz     loc_18002AF0E
0x180010842  test    rdi, rdi
0x180010845  jnz     loc_18002AF72
0x18001084b  test    dword ptr [rbx+188h], 400h
0x180010855  jnz     loc_18002AF8A
0x18001085b  test    dword ptr [rbx+188h], 800h
0x180010865  jnz     loc_18002AFB8
0x18001086b  mov     eax, r13d
0x18001086e  mov     r13, [rsp+580h+var_30]
0x180010876  mov     r12, [rsp+580h+var_28]
0x18001087e  mov     rdi, [rsp+580h+arg_10]
0x180010886  mov     rcx, [rbp+480h+var_40]
0x18001088d  xor     rcx, rsp; StackCookie
0x180010890  call    __security_check_cookie
0x180010895  add     rsp, 560h
0x18001089c  pop     r15
0x18001089e  pop     r14
0x1800108a0  pop     rsi
0x1800108a1  pop     rbx
0x1800108a2  pop     rbp
0x1800108a3  retn
0x1800108a4  mov     rcx, [rcx+38h]; hHandle
0x1800108a8  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1800108ad  call    cs:__imp_WaitForSingleObject
0x1800108b3  jmp     loc_18001067A
0x1800108b8  xor     eax, eax
0x1800108ba  jmp     short loc_18001086E
0x18002ab6e  test    byte ptr [rbx+188h], 4
0x18002ab75  jz      short loc_18002ABE8
0x18002ab77  cmp     [rbx+170h], r15d
0x18002ab7e  jnz     short loc_18002ABE8
0x18002ab80  test    byte ptr cs:g_dwDebugFlags, 3
0x18002ab87  jz      short loc_18002ABC0
0x18002ab89  mov     eax, [rbx+174h]
0x18002ab8f  lea     r9, aCtemplateDeliv; "CTemplate::Deliver"
0x18002ab96  mov     rcx, cs:g_pDebug
0x18002ab9d  lea     rdx, aInetsrvIisSvcs_4; "inetsrv\\iis\\svcs\\cmp\\asp\\template."...
0x18002aba4  mov     dword ptr [rsp+580h+PrivilegeSetLength], eax
0x18002aba8  mov     r8d, 724h
0x18002abae  lea     rax, aTemplateCompil; "template compile failed with %08x\n"
0x18002abb5  mov     [rsp+580h+PrivilegeSet], rax
0x18002abba  call    cs:__imp_PuDbgPrint
0x18002abc0  mov     ebx, [rbx+174h]
0x18002abc6  test    ebx, ebx
0x18002abc8  js      short loc_18002ABD1
0x18002abca  mov     ebx, 80004005h
0x18002abcf  jmp     short loc_18002ABE1
0x18002abd1  cmp     ebx, 8000D004h
0x18002abd7  jnz     short loc_18002ABE1
0x18002abd9  mov     rcx, rsi; struct CHitObj *
0x18002abdc  call    HandleAccessFailure
0x18002abe1  mov     eax, ebx
0x18002abe3  jmp     loc_18001086E
0x18002abe8  mov     rax, [rbx+168h]
0x18002abef  mov     r9, [rbx+150h]; char *
0x18002abf6  mov     r8, [rbx+148h]; char *
0x18002abfd  mov     rdx, [rbx+140h]; Src
0x18002ac04  mov     ecx, [rbx+170h]; unsigned int
0x18002ac0a  mov     [rsp+580h+AccessStatus], rsi; struct CHitObj *
0x18002ac0f  mov     [rsp+580h+GrantedAccess], rax; char *
0x18002ac14  mov     rax, [rbx+160h]
0x18002ac1b  mov     [rsp+580h+PrivilegeSetLength], rax; char *
0x18002ac20  mov     rax, [rbx+158h]
0x18002ac27  mov     [rsp+580h+PrivilegeSet], rax; char *
0x18002ac2c  call    ?SendToLog@@YAXKPEAD00000PEAVCHitObj@@@Z; SendToLog(ulong,char *,char *,char *,char *,char *,char *,CHitObj *)
0x18002ac31  mov     r13d, 8000D003h
0x18002ac37  jmp     loc_18001084B
0x18002ac3c  lea     rcx, [rbx+218h]; lpCriticalSection
0x18002ac43  call    cs:__imp_EnterCriticalSection
0x18002ac49  mov     rcx, [rbx+208h]
0x18002ac50  mov     eax, [rbx+1F8h]
0x18002ac56  mov     [rsp+580h+pSid1], rcx
0x18002ac5b  lea     rcx, [rbx+218h]; lpCriticalSection
0x18002ac62  mov     [rsp+580h+var_520], eax
0x18002ac66  call    cs:__imp_LeaveCriticalSection
0x18002ac6c  mov     rdx, [rsi+60h]; void *
0x18002ac70  lea     rax, [rsp+580h+var_510]
0x18002ac75  lea     r9, [rsp+580h+var_528]; void **
0x18002ac7a  mov     [rsp+580h+PrivilegeSet], rax; unsigned int *
0x18002ac7f  lea     r8, [rsp+580h+pSid2]; void **
0x18002ac84  call    ?GetSIDFromTokenHandle@CTemplate@@QEAAJPEAXPEAPEAX1PEAK@Z; CTemplate::GetSIDFromTokenHandle(void *,void * *,void * *,ulong *)
0x18002ac89  mov     rdx, [rsp+580h+pSid2]
0x18002ac8e  mov     r9d, eax
0x18002ac91  mov     r10, [rsp+580h+var_530]
0x18002ac96  mov     r8, [rsp+580h+pSid1]
0x18002ac9b  mov     rdi, [rsp+580h+var_528]
0x18002aca0  jmp     loc_180010730
0x18002aca5  cmp     cs:?g_fUNCChangeNotificationEnabled@@3HA, 0; int g_fUNCChangeNotificationEnabled
0x18002acac  jnz     loc_180010765
0x18002acb2  test    r8, r8
0x18002acb5  jz      short loc_18002ACF2
0x18002acb7  test    r9d, r9d
0x18002acba  js      short loc_18002ACF2
0x18002acbc  mov     rcx, r8; pSid1
0x18002acbf  call    cs:__imp_EqualSid
0x18002acc5  test    eax, eax
0x18002acc7  jz      short loc_18002ACF2
0x18002acc9  mov     rdx, [rsp+580h+pSid2]; pSid2
0x18002acce  mov     rcx, [rsp+580h+pSid1]; pSid1
0x18002acd3  call    cs:__imp_EqualSid
0x18002acd9  test    eax, eax
0x18002acdb  jz      loc_18001081A
0x18002ace1  mov     edx, [rsp+580h+var_520]; unsigned int
0x18002ace5  call    ?CheckTTLTimingWindow@CTemplate@@QEAAHKK@Z; CTemplate::CheckTTLTimingWindow(ulong,ulong)
0x18002acea  test    eax, eax
0x18002acec  jz      loc_18001081A
0x18002acf2  mov     rax, [rbx+110h]
0x18002acf9  lea     r8, [rbp+480h+hToken]; void **
0x18002acfd  mov     r12, [rbp+480h+var_4F0]
0x18002ad01  xor     r13d, r13d
0x18002ad04  mov     rcx, [rsi+40h]; this
0x18002ad08  mov     [rbp+480h+hToken], r13
0x18002ad0c  mov     [rsp+580h+TokenHandle], r13
0x18002ad11  mov     rdx, [r12+rax]
0x18002ad15  mov     dword ptr [rsp+580h+var_528], r13d
0x18002ad1a  mov     rdx, [rdx]; unsigned __int16 *
0x18002ad1d  call    ?GetVirtualPathTokenW@CIsapiReqInfo@@QEAAJPEBGPEAPEAX@Z; CIsapiReqInfo::GetVirtualPathTokenW(ushort const *,void * *)
0x18002ad22  test    eax, eax
0x18002ad24  js      short loc_18002AD4C
0x18002ad26  lea     rcx, [rsp+580h+TokenHandle]; TokenHandle
0x18002ad2b  call    ?AspDoRevertHack@@YAXPEAPEAX@Z; AspDoRevertHack(void * *)
0x18002ad30  mov     rcx, [rbp+480h+hToken]; hToken
0x18002ad34  call    cs:__imp_ImpersonateLoggedOnUser
0x18002ad3a  mov     dword ptr [rsp+580h+var_528], eax
0x18002ad3e  test    eax, eax
0x18002ad40  jnz     short loc_18002AD4C
0x18002ad42  lea     rcx, [rsp+580h+TokenHandle]; void **
0x18002ad47  call    ?AspUndoRevertHack@@YAXPEAPEAX@Z; AspUndoRevertHack(void * *)
0x18002ad4c  mov     rcx, [rbx+110h]
0x18002ad53  xor     r9d, r9d; unsigned int *
0x18002ad56  xor     r8d, r8d; struct _FILETIME *
0x18002ad59  mov     [rsp+580h+PrivilegeSet], r13; unsigned int *
0x18002ad5e  xor     edx, edx; void *
0x18002ad60  mov     rcx, [r12+rcx]
0x18002ad64  mov     rcx, [rcx+8]; unsigned __int16 *
0x18002ad68  call    ?AspGetFileAttributes@@YAJPEBGPEAXPEAU_FILETIME@@PEAK3@Z; AspGetFileAttributes(ushort const *,void *,_FILETIME *,ulong *,ulong *)
0x18002ad6d  cmp     dword ptr [rsp+580h+var_528], 0
0x18002ad72  mov     r13d, eax
0x18002ad75  jz      short loc_18002AD81
0x18002ad77  lea     rcx, [rsp+580h+TokenHandle]; void **
0x18002ad7c  call    ?AspUndoRevertHack@@YAXPEAPEAX@Z; AspUndoRevertHack(void * *)
0x18002ad81  mov     rcx, [rbp+480h+hToken]; hObject
0x18002ad85  test    rcx, rcx
0x18002ad88  jz      short loc_18002AD90
0x18002ad8a  call    cs:__imp_CloseHandle
0x18002ad90  test    r13d, r13d
0x18002ad93  jns     loc_18002AE88
0x18002ad99  cmp     r13d, 80070002h
0x18002ada0  jz      loc_18002AEE8
0x18002ada6  cmp     r13d, 80070005h
0x18002adad  jz      loc_18002AEF2
0x18002adb3  cmp     r13d, 80070079h
0x18002adba  jz      short loc_18002ADDF
0x18002adbc  lea     eax, [r13+7FF8FFCDh]
0x18002adc3  cmp     eax, 10h
0x18002adc6  ja      short loc_18002ADD2
0x18002adc8  mov     ecx, 1210Dh; this
0x18002adcd  bt      ecx, eax
0x18002add0  jb      short loc_18002ADDF
0x18002add2  cmp     r13d, 800704CFh
0x18002add9  jnz     loc_18001086B
0x18002addf  lea     rdx, [rsp+580h+var_528]; unsigned int *
0x18002ade4  mov     dword ptr [rsp+580h+var_528], 0
0x18002adec  call    ?GetDisableCachedResponseOnUNCAccessFailure@CAspRegistryParams@@QEAAJPEAK@Z; CAspRegistryParams::GetDisableCachedResponseOnUNCAccessFailure(ulong *)
0x18002adf1  xor     eax, eax
0x18002adf3  mov     ecx, 1
0x18002adf8  lock cmpxchg cs:?g_fUNCFailureLogged@@3JA, ecx; long g_fUNCFailureLogged
0x18002ae00  jnz     short loc_18002AE4F
0x18002ae02  mov     rax, [rbx+110h]
0x18002ae09  mov     r9, 0FFFFFFFFFFFFFFFFh
0x18002ae10  mov     rcx, [r12+rax]
0x18002ae14  mov     r8, [rcx+8]; lpWideCharStr
0x18002ae18  inc     r9; cchWideChar
0x18002ae1b  cmp     word ptr [r8+r9*2], 0
0x18002ae21  jnz     short loc_18002AE18
0x18002ae23  mov     eax, [rbx+190h]
0x18002ae29  lea     rcx, [rbp+480h+MultiByteStr]; lpMultiByteStr
0x18002ae2d  mov     edx, 400h; cbMultiByte
0x18002ae32  mov     dword ptr [rsp+580h+PrivilegeSet], eax; CodePage
0x18002ae36  call    ?WstrToMBstrEx@@YAIPEADHPEBGHI@Z; WstrToMBstrEx(char *,int,ushort const *,int,uint)
0x18002ae3b  xor     r9d, r9d; unsigned int
0x18002ae3e  lea     rdx, [rbp+480h+MultiByteStr]; Source
0x18002ae42  mov     r8d, r13d; UINT
0x18002ae45  mov     ecx, 0C00001F4h; uID
0x18002ae4a  call    ?MSG_Error@@YAXIPEBDIK@Z; MSG_Error(uint,char const *,uint,ulong)
0x18002ae4f  test    r14, r14
0x18002ae52  jz      short loc_18002AE78
0x18002ae54  mov     rcx, [r14+8]; struct _EXTENSION_CONTROL_BLOCK *
0x18002ae58  mov     edx, 4; unsigned int
0x18002ae5d  call    ?CheckTracingEnabled@ActiveServerPagesASPTraceProvider@@SAHPEAU_EXTENSION_CONTROL_BLOCK@@K@Z; ActiveServerPagesASPTraceProvider::CheckTracingEnabled(_EXTENSION_CONTROL_BLOCK *,ulong)
0x18002ae62  test    eax, eax
  ... truncated ...
```
