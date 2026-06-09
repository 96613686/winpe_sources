# CCacheStore::AppCachePrepareAppCacheIdForDelete(unsigned __int64,unsigned __int64,CJetContext *,CAppCacheDeleteEntry * *)

- ea: `0x1801bb82c`
- end: `0x1801bba9a`
- name: `?AppCachePrepareAppCacheIdForDelete@CCacheStore@@AEAAJ_K0PEAVCJetContext@@PEAPEAVCAppCacheDeleteEntry@@@Z`
- size: `622`
- prototype: `int(CCacheStore *__hidden this, unsigned __int64, unsigned __int64, struct CJetContext *, struct CAppCacheDeleteEntry **)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801ba648`
- `0x1801bbaa0`

## callees

- `0x180021360`
- `0x18007ec9c`
- `0x18007ed10`
- `0x1800fa844`
- `0x180147b1c`
- `0x18014a7a0`
- `0x1801b8d7c`
- `0x1801bb82c`
- `0x1801c288c`
- `0x1801de438`
- `0x1801e1790`

## import_xrefs

- `ESENT!JetCommitTransaction` at `0x1801bba50`
- `ESENT!JetCommitTransaction` at `0x1801bba50`
- `ESENT!JetUpdate` at `0x1801bba35`
- `ESENT!JetUpdate` at `0x1801bba35`
- `ESENT!JetPrepareUpdate` at `0x1801bb9d1`
- `ESENT!JetPrepareUpdate` at `0x1801bba16`
- `ESENT!JetPrepareUpdate` at `0x1801bb9d1`
- `ESENT!JetPrepareUpdate` at `0x1801bba16`
- `ESENT!JetRollback` at `0x1801bba8f`
- `ESENT!JetRollback` at `0x1801bba8f`
- `ESENT!JetBeginTransaction` at `0x1801bb948`
- `ESENT!JetBeginTransaction` at `0x1801bb948`

## string_xrefs

- `0x1801bb924`: `AppCacheIdIndex`

## pseudocode

```c
__int64 __fastcall CCacheStore::AppCachePrepareAppCacheIdForDelete(
        CAppCacheDeletionManager **this,
        unsigned __int64 a2,
        unsigned __int64 a3,
        JET_SESID *a4,
        struct CAppCacheDeleteEntry **a5)
{
  int v9; // eax
  unsigned int v10; // r9d
  unsigned int v11; // edi
  int v12; // ebx
  JET_ERR v14; // eax
  int v15; // eax
  int BasicColumn; // eax
  JET_TABLEID v17; // rdx
  JET_SESID v18; // rcx
  JET_ERR v19; // eax
  JET_ERR v20; // eax
  JET_ERR v21; // eax
  int v22; // ecx
  struct CAppCacheDeleteEntry *v23; // [rsp+48h] [rbp-18h] BYREF
  int v24; // [rsp+50h] [rbp-10h] BYREF

  v23 = 0;
  v24 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qiiqq((_DWORD)this, a2, a3, (_DWORD)this, a2, a3, (__int64)a4, (__int64)a5);
  *a5 = 0;
  v9 = CAppCacheDeletionManager::AcquireDelete(this[57], a2, a3, &v23);
  v11 = 1;
  v12 = v9;
  if ( v9 == 1 )
  {
    v12 = 1;
    goto LABEL_7;
  }
  if ( v9 < 0
    || (v9 = CJetContext::SetCurrentIndex((CJetContext *)a4, 0, L"AppCacheIdIndex", v10), v12 = v9, v9 < 0)
    || (v14 = JetBeginTransaction(a4[2]), v9 = HRESULTFromJET_ERR(v14, 1), v12 = v9, v9 < 0) )
  {
    v11 = v9;
    goto LABEL_7;
  }
  v15 = CAppCache::SeekToAppCache((struct CJetContext *)a4, a3);
  v12 = v15;
  if ( v15 == 1 )
  {
    v12 = 1;
LABEL_30:
    JetRollback(a4[2], 0);
    goto LABEL_7;
  }
  if ( v15 < 0 )
  {
LABEL_17:
    v11 = v15;
    goto LABEL_30;
  }
  BasicColumn = CJetContext::GetBasicColumn((CJetContext *)a4, 5u, &v24, 4u);
  v12 = HRESULTFromJET_ERR(BasicColumn, 1);
  if ( v12 < 0 )
  {
    v11 = v12;
    goto LABEL_30;
  }
  if ( v24 == 2 )
  {
    v22 = 1;
    v11 = v12;
  }
  else
  {
    v17 = a4[4];
    v18 = a4[2];
    v24 = 2;
    v19 = JetPrepareUpdate(v18, v17, 2u);
    v15 = HRESULTFromJET_ERR(v19, 1);
    v12 = v15;
    if ( v15 < 0 )
      goto LABEL_17;
    v12 = CJetContext::SetBasicColumn((CJetContext *)a4, 5u, &v24, 4u);
    if ( v12 < 0 || (v20 = JetUpdate(a4[2], a4[4], 0, 0, 0), v12 = HRESULTFromJET_ERR(v20, 1), v12 < 0) )
    {
      v11 = v12;
      JetPrepareUpdate(a4[2], a4[4], 3u);
      goto LABEL_30;
    }
    v21 = JetCommitTransaction(a4[2], 1u);
    v12 = HRESULTFromJET_ERR(v21, 1);
    v11 = v12;
    if ( v12 < 0 )
      goto LABEL_30;
    v22 = 0;
  }
  *a5 = v23;
  v23 = 0;
  if ( v22 )
    goto LABEL_30;
LABEL_7:
  if ( v23 )
    CAppCacheDeletionManager::ReleaseDelete(this[57], &v23);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 39, &WPP_e92de34c5eaa325d4e2e9cbe3aa0c6fa_Traceguids, (unsigned int)v12);
  return v11;
}

```

## disassembly

```asm
0x1801bb82c  mov     r11, rsp
0x1801bb82f  push    rbp
0x1801bb830  push    rbx
0x1801bb831  push    rsi
0x1801bb832  push    rdi
0x1801bb833  push    r13
0x1801bb835  push    r14
0x1801bb837  push    r15
0x1801bb839  mov     rbp, rsp
0x1801bb83c  sub     rsp, 60h
0x1801bb840  mov     rax, cs:__security_cookie
0x1801bb847  xor     rax, rsp
0x1801bb84a  mov     [rbp+var_8], rax
0x1801bb84e  mov     r15, [rbp+arg_20]
0x1801bb852  mov     rsi, r9
0x1801bb855  mov     r14, r8
0x1801bb858  mov     [rbp+var_1C], 0
0x1801bb85f  mov     rbx, rdx
0x1801bb862  mov     [rbp+var_18], 0
0x1801bb86a  mov     r13, rcx
0x1801bb86d  mov     [rbp+var_10], 0
0x1801bb874  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801bb87b  jz      short loc_1801BB895
0x1801bb87d  mov     [r11-60h], r15
0x1801bb881  mov     [r11-68h], r9
0x1801bb885  mov     r9, rcx
0x1801bb888  mov     [r11-70h], r8
0x1801bb88c  mov     [r11-78h], rdx
0x1801bb890  call    WPP_SF_qiiqq
0x1801bb895  mov     qword ptr [r15], 0
0x1801bb89c  lea     r9, [rbp+var_18]; struct CAppCacheDeleteEntry **
0x1801bb8a0  mov     rcx, [r13+1C8h]; this
0x1801bb8a7  mov     r8, r14; unsigned __int64
0x1801bb8aa  mov     rdx, rbx; unsigned __int64
0x1801bb8ad  call    ?AcquireDelete@CAppCacheDeletionManager@@QEAAJ_K0PEAPEAVCAppCacheDeleteEntry@@@Z; CAppCacheDeletionManager::AcquireDelete(unsigned __int64,unsigned __int64,CAppCacheDeleteEntry * *)
0x1801bb8b2  mov     edi, 1
0x1801bb8b7  mov     ebx, eax
0x1801bb8b9  cmp     eax, edi
0x1801bb8bb  jnz     short loc_1801BB8C1
0x1801bb8bd  mov     ebx, edi
0x1801bb8bf  jmp     short loc_1801BB8CE
0x1801bb8c1  test    eax, eax
0x1801bb8c3  jns     short loc_1801BB924
0x1801bb8c5  mov     [rbp+var_1C], 432h
0x1801bb8cc  mov     edi, eax
0x1801bb8ce  cmp     [rbp+var_18], 0
0x1801bb8d3  jz      short loc_1801BB8E5
0x1801bb8d5  mov     rcx, [r13+1C8h]; this
0x1801bb8dc  lea     rdx, [rbp+var_18]; struct CAppCacheDeleteEntry **
0x1801bb8e0  call    ?ReleaseDelete@CAppCacheDeletionManager@@QEAAXPEAPEAVCAppCacheDeleteEntry@@@Z; CAppCacheDeletionManager::ReleaseDelete(CAppCacheDeleteEntry * *)
0x1801bb8e5  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801bb8ec  jz      short loc_1801BB907
0x1801bb8ee  mov     edx, 27h ; '''
0x1801bb8f3  lea     r8, WPP_e92de34c5eaa325d4e2e9cbe3aa0c6fa_Traceguids
0x1801bb8fa  mov     ecx, 40Ch
0x1801bb8ff  mov     r9d, ebx
0x1801bb902  call    WPP_SF_d
0x1801bb907  mov     eax, edi
0x1801bb909  mov     rcx, [rbp+var_8]
0x1801bb90d  xor     rcx, rsp; StackCookie
0x1801bb910  call    __security_check_cookie
0x1801bb915  add     rsp, 60h
0x1801bb919  pop     r15
0x1801bb91b  pop     r14
0x1801bb91d  pop     r13
0x1801bb91f  pop     rdi
0x1801bb920  pop     rsi
0x1801bb921  pop     rbx
0x1801bb922  pop     rbp
0x1801bb923  retn
0x1801bb924  lea     r8, aAppcacheidinde; "AppCacheIdIndex"
0x1801bb92b  xor     edx, edx; unsigned int
0x1801bb92d  mov     rcx, rsi; this
0x1801bb930  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1801bb935  mov     ebx, eax
0x1801bb937  test    eax, eax
0x1801bb939  jns     short loc_1801BB944
0x1801bb93b  mov     [rbp+var_1C], 43Ah
0x1801bb942  jmp     short loc_1801BB8CC
0x1801bb944  mov     rcx, [rsi+10h]; sesid
0x1801bb948  call    cs:__imp_JetBeginTransaction
0x1801bb94e  mov     ecx, eax; int
0x1801bb950  mov     edx, edi; int
0x1801bb952  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801bb957  mov     ebx, eax
0x1801bb959  test    eax, eax
0x1801bb95b  js      loc_1801BB8CC
0x1801bb961  mov     rdx, r14; unsigned __int64
0x1801bb964  mov     rcx, rsi; struct CJetContext *
0x1801bb967  call    ?SeekToAppCache@CAppCache@@SAJPEAVCJetContext@@_K@Z; CAppCache::SeekToAppCache(CJetContext *,unsigned __int64)
0x1801bb96c  mov     ebx, eax
0x1801bb96e  cmp     eax, edi
0x1801bb970  jnz     short loc_1801BB979
0x1801bb972  mov     ebx, edi
0x1801bb974  jmp     loc_1801BBA89
0x1801bb979  test    eax, eax
0x1801bb97b  jns     short loc_1801BB98B
0x1801bb97d  mov     [rbp+var_1C], 445h
0x1801bb984  mov     edi, eax
0x1801bb986  jmp     loc_1801BBA89
0x1801bb98b  mov     r14d, 4
0x1801bb991  lea     r8, [rbp+var_10]; void *
0x1801bb995  mov     r9d, r14d; unsigned int
0x1801bb998  mov     rcx, rsi; this
0x1801bb99b  lea     edx, [r14+1]; unsigned int
0x1801bb99f  call    ?GetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::GetBasicColumn(ulong,void *,ulong)
0x1801bb9a4  mov     ecx, eax; int
0x1801bb9a6  mov     edx, edi; int
0x1801bb9a8  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801bb9ad  mov     ebx, eax
0x1801bb9af  test    eax, eax
0x1801bb9b1  js      loc_1801BBA87
0x1801bb9b7  lea     r8d, [r14-2]; prep
0x1801bb9bb  cmp     [rbp+var_10], r8d
0x1801bb9bf  jz      loc_1801BBA6B
0x1801bb9c5  mov     rdx, [rsi+20h]; tableid
0x1801bb9c9  mov     rcx, [rsi+10h]; sesid
0x1801bb9cd  mov     [rbp+var_10], r8d
0x1801bb9d1  call    cs:__imp_JetPrepareUpdate
0x1801bb9d7  mov     ecx, eax; int
0x1801bb9d9  mov     edx, edi; int
0x1801bb9db  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801bb9e0  mov     ebx, eax
0x1801bb9e2  test    eax, eax
0x1801bb9e4  js      short loc_1801BB984
0x1801bb9e6  mov     r9d, r14d; unsigned int
0x1801bb9e9  lea     r8, [rbp+var_10]; void *
0x1801bb9ed  lea     edx, [r14+1]; unsigned int
0x1801bb9f1  mov     rcx, rsi; this
0x1801bb9f4  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1801bb9f9  mov     ebx, eax
0x1801bb9fb  test    eax, eax
0x1801bb9fd  jns     short loc_1801BBA1E
0x1801bb9ff  mov     [rbp+var_1C], 456h
0x1801bba06  mov     rdx, [rsi+20h]; tableid
0x1801bba0a  mov     r8d, 3; prep
0x1801bba10  mov     rcx, [rsi+10h]; sesid
0x1801bba14  mov     edi, ebx
0x1801bba16  call    cs:__imp_JetPrepareUpdate
0x1801bba1c  jmp     short loc_1801BBA89
0x1801bba1e  mov     rdx, [rsi+20h]; tableid
0x1801bba22  xor     r9d, r9d; cbBookmark
0x1801bba25  mov     rcx, [rsi+10h]; sesid
0x1801bba29  xor     r8d, r8d; pvBookmark
0x1801bba2c  mov     [rsp+60h+pcbActual], 0; pcbActual
0x1801bba35  call    cs:__imp_JetUpdate
0x1801bba3b  mov     ecx, eax; int
0x1801bba3d  mov     edx, edi; int
0x1801bba3f  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801bba44  mov     ebx, eax
0x1801bba46  test    eax, eax
0x1801bba48  js      short loc_1801BBA06
0x1801bba4a  mov     rcx, [rsi+10h]; sesid
0x1801bba4e  mov     edx, edi; grbit
0x1801bba50  call    cs:__imp_JetCommitTransaction
0x1801bba56  mov     ecx, eax; int
0x1801bba58  mov     edx, edi; int
0x1801bba5a  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801bba5f  mov     ebx, eax
0x1801bba61  mov     edi, eax
0x1801bba63  test    eax, eax
0x1801bba65  js      short loc_1801BBA89
0x1801bba67  xor     ecx, ecx
0x1801bba69  jmp     short loc_1801BBA6F
0x1801bba6b  mov     ecx, edi
0x1801bba6d  mov     edi, ebx
0x1801bba6f  mov     rax, [rbp+var_18]
0x1801bba73  mov     [r15], rax
0x1801bba76  mov     [rbp+var_18], 0
0x1801bba7e  test    ecx, ecx
0x1801bba80  jnz     short loc_1801BBA89
0x1801bba82  jmp     loc_1801BB8CE
0x1801bba87  mov     edi, ebx
0x1801bba89  mov     rcx, [rsi+10h]; sesid
0x1801bba8d  xor     edx, edx; grbit
0x1801bba8f  call    cs:__imp_JetRollback
0x1801bba95  jmp     loc_1801BB8CE
```
