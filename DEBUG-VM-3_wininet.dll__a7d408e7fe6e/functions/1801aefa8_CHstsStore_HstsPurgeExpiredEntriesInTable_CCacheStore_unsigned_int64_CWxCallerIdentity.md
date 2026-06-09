# CHstsStore::HstsPurgeExpiredEntriesInTable(CCacheStore *,unsigned __int64,CWxCallerIdentity *)

- ea: `0x1801aefa8`
- end: `0x1801af233`
- name: `?HstsPurgeExpiredEntriesInTable@CHstsStore@@AEAAJPEAVCCacheStore@@_KPEAVCWxCallerIdentity@@@Z`
- size: `651`
- prototype: `__int64 __fastcall(CHstsStore *__hidden this, struct CCacheStore *, unsigned __int64, struct CWxCallerIdentity *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800ad530`

## callees

- `0x18007ec9c`
- `0x18007ee10`
- `0x1800861f8`
- `0x1800aa644`
- `0x1800aca44`
- `0x1800b5f40`
- `0x1800fa844`
- `0x18012be98`
- `0x18014a7a0`
- `0x1801aefa8`
- `0x1801af358`
- `0x1801e1790`
- `0x1801e53d0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801af123`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801af123`
- `ESENT!JetCommitTransaction` at `0x1801af213`
- `ESENT!JetCommitTransaction` at `0x1801af213`
- `ESENT!JetUpdate` at `0x1801af1f8`
- `ESENT!JetUpdate` at `0x1801af1f8`
- `ESENT!JetPrepareUpdate` at `0x1801af191`
- `ESENT!JetPrepareUpdate` at `0x1801af1d9`
- `ESENT!JetPrepareUpdate` at `0x1801af191`
- `ESENT!JetPrepareUpdate` at `0x1801af1d9`
- `ESENT!JetRollback` at `0x1801af170`
- `ESENT!JetRollback` at `0x1801af170`
- `ESENT!JetBeginTransaction` at `0x1801af131`
- `ESENT!JetBeginTransaction` at `0x1801af131`

## pseudocode

```c
__int64 __fastcall CHstsStore::HstsPurgeExpiredEntriesInTable(
        CHstsStore *this,
        CJetContextList **a2,
        unsigned __int64 a3,
        struct CWxCallerIdentity *a4)
{
  JET_SESID *v4; // rsi
  unsigned int v9; // ebx
  int v10; // edi
  int v11; // eax
  JET_ERR v13; // eax
  int v14; // eax
  JET_ERR v15; // eax
  JET_ERR v16; // eax
  JET_ERR v17; // eax
  CJetContext *v18; // [rsp+38h] [rbp-28h] BYREF
  struct CHstsContainerProps *v19; // [rsp+40h] [rbp-20h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-18h] BYREF

  v4 = 0;
  v18 = 0;
  v19 = 0;
  SystemTimeAsFileTime = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qqi(
      (_DWORD)this,
      22,
      (unsigned int)&WPP_9d52da5ef3ad3c382853cb62ff3dbf62_Traceguids,
      (_DWORD)this,
      (__int64)a2);
  if ( !a2 )
  {
    v9 = -2147024809;
    v10 = -2147024809;
    goto LABEL_13;
  }
  if ( !a4 )
  {
    v9 = -2147024809;
    v10 = -2147024809;
    goto LABEL_11;
  }
  if ( (unsigned int)CCacheStore::IsTerminating((CCacheStore *)a2) )
  {
    v10 = 0;
    v9 = 0;
    goto LABEL_11;
  }
  v9 = 1;
  v11 = CHstsStore::AcquireHstsContainerProps(this, a3, 1, a4, &v19);
  v10 = v11;
  if ( v11 < 0 )
    goto LABEL_10;
  v11 = CHstsContainerProps::PurgeHstsEntries(v19, 0, 0);
  v10 = v11;
  if ( v11 < 0 )
    goto LABEL_10;
  v11 = CCacheStore::AcquirePartitionContext((CCacheStore *)a2, &v18);
  v10 = v11;
  if ( v11 < 0 )
  {
    v4 = (JET_SESID *)v18;
LABEL_10:
    v9 = v11;
    goto LABEL_11;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v4 = (JET_SESID *)v18;
  v13 = JetBeginTransaction(*((_QWORD *)v18 + 2));
  v11 = HRESULTFromJET_ERR(v13, 1);
  v10 = v11;
  if ( v11 < 0 )
    goto LABEL_10;
  v14 = CCacheStore::SeekToPartition(v4, a4, 2);
  v10 = v14;
  if ( v14 < 0 )
    goto LABEL_21;
  if ( v14 == 1 )
  {
    v10 = 1;
    goto LABEL_22;
  }
  v15 = JetPrepareUpdate(v4[2], v4[4], 2u);
  v14 = HRESULTFromJET_ERR(v15, 1);
  v10 = v14;
  if ( v14 < 0 )
  {
LABEL_21:
    v9 = v14;
LABEL_22:
    JetRollback(v4[2], 0);
    goto LABEL_11;
  }
  v10 = CJetContext::SetBasicColumn((CJetContext *)v4, 5u, &SystemTimeAsFileTime, 8u);
  if ( v10 < 0 || (v16 = JetUpdate(v4[2], v4[4], 0, 0, 0), v10 = HRESULTFromJET_ERR(v16, 1), v10 < 0) )
  {
    v9 = v10;
    JetPrepareUpdate(v4[2], v4[4], 3u);
    goto LABEL_22;
  }
  v17 = JetCommitTransaction(v4[2], 1u);
  v10 = HRESULTFromJET_ERR(v17, 1);
  v9 = v10;
  if ( v10 < 0 )
    goto LABEL_22;
LABEL_11:
  if ( v4 )
    CJetContextList::ReleaseContext(a2[55], &v18);
LABEL_13:
  CHstsStore::ReleaseHstsContainerProps(this, &v19);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 23, &WPP_9d52da5ef3ad3c382853cb62ff3dbf62_Traceguids, (unsigned int)v10);
  return v9;
}

```

## disassembly

```asm
0x1801aefa8  push    rbp
0x1801aefaa  push    rbx
0x1801aefab  push    rsi
0x1801aefac  push    rdi
0x1801aefad  push    r12
0x1801aefaf  push    r14
0x1801aefb1  push    r15
0x1801aefb3  mov     rbp, rsp
0x1801aefb6  sub     rsp, 60h
0x1801aefba  mov     rax, cs:__security_cookie
0x1801aefc1  xor     rax, rsp
0x1801aefc4  mov     [rbp+var_10], rax
0x1801aefc8  xor     esi, esi
0x1801aefca  mov     [rbp+var_2C], 0
0x1801aefd1  mov     [rbp+var_28], rsi
0x1801aefd5  mov     r15, r9
0x1801aefd8  mov     rdi, r8
0x1801aefdb  mov     [rbp+var_20], 0
0x1801aefe3  mov     r14, rdx
0x1801aefe6  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1801aefee  mov     r12, rcx
0x1801aeff1  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801aeff8  jz      short loc_1801AF016
0x1801aeffa  mov     [rsp+60h+var_38], r8
0x1801aefff  lea     edx, [rsi+16h]
0x1801af002  lea     r8, WPP_9d52da5ef3ad3c382853cb62ff3dbf62_Traceguids
0x1801af009  mov     [rsp+60h+pcbActual], r14
0x1801af00e  mov     r9, rcx
0x1801af011  call    WPP_SF_qqi
0x1801af016  test    r14, r14
0x1801af019  jnz     short loc_1801AF02B
0x1801af01b  mov     ebx, 80070057h
0x1801af020  mov     [rbp+var_2C], 165h
0x1801af027  mov     edi, ebx
0x1801af029  jmp     short loc_1801AF095
0x1801af02b  test    r15, r15
0x1801af02e  jnz     short loc_1801AF040
0x1801af030  mov     ebx, 80070057h
0x1801af035  mov     [rbp+var_2C], 166h
0x1801af03c  mov     edi, ebx
0x1801af03e  jmp     short loc_1801AF080
0x1801af040  mov     rcx, r14; this
0x1801af043  call    ?IsTerminating@CCacheStore@@QEAAHXZ; CCacheStore::IsTerminating(void)
0x1801af048  test    eax, eax
0x1801af04a  jz      short loc_1801AF052
0x1801af04c  xor     edi, edi
0x1801af04e  xor     ebx, ebx
0x1801af050  jmp     short loc_1801AF080
0x1801af052  lea     rax, [rbp+var_20]
0x1801af056  mov     ebx, 1
0x1801af05b  mov     r8d, ebx; int
0x1801af05e  mov     [rsp+60h+pcbActual], rax; struct CHstsContainerProps **
0x1801af063  mov     r9, r15; struct CWxCallerIdentity *
0x1801af066  mov     rdx, rdi; unsigned __int64
0x1801af069  mov     rcx, r12; this
0x1801af06c  call    ?AcquireHstsContainerProps@CHstsStore@@QEAAJ_KHPEAVCWxCallerIdentity@@PEAPEAVCHstsContainerProps@@@Z; CHstsStore::AcquireHstsContainerProps(unsigned __int64,int,CWxCallerIdentity *,CHstsContainerProps * *)
0x1801af071  mov     edi, eax
0x1801af073  test    eax, eax
0x1801af075  jns     short loc_1801AF0E0
0x1801af077  mov     [rbp+var_2C], 170h
0x1801af07e  mov     ebx, eax
0x1801af080  test    rsi, rsi
0x1801af083  jz      short loc_1801AF095
0x1801af085  mov     rcx, [r14+1B8h]; this
0x1801af08c  lea     rdx, [rbp+var_28]; struct CJetContext **
0x1801af090  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x1801af095  lea     rdx, [rbp+var_20]; struct CHstsContainerProps **
0x1801af099  mov     rcx, r12; this
0x1801af09c  call    ?ReleaseHstsContainerProps@CHstsStore@@QEAAXPEAPEAVCHstsContainerProps@@@Z; CHstsStore::ReleaseHstsContainerProps(CHstsContainerProps * *)
0x1801af0a1  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801af0a8  jz      short loc_1801AF0C3
0x1801af0aa  mov     edx, 17h
0x1801af0af  lea     r8, WPP_9d52da5ef3ad3c382853cb62ff3dbf62_Traceguids
0x1801af0b6  mov     ecx, 40Ch
0x1801af0bb  mov     r9d, edi
0x1801af0be  call    WPP_SF_d
0x1801af0c3  mov     eax, ebx
0x1801af0c5  mov     rcx, [rbp+var_10]
0x1801af0c9  xor     rcx, rsp; StackCookie
0x1801af0cc  call    __security_check_cookie
0x1801af0d1  add     rsp, 60h
0x1801af0d5  pop     r15
0x1801af0d7  pop     r14
0x1801af0d9  pop     r12
0x1801af0db  pop     rdi
0x1801af0dc  pop     rsi
0x1801af0dd  pop     rbx
0x1801af0de  pop     rbp
0x1801af0df  retn
0x1801af0e0  mov     rcx, [rbp+var_20]; this
0x1801af0e4  xor     r8d, r8d; unsigned int *
0x1801af0e7  xor     edx, edx; int
0x1801af0e9  call    ?PurgeHstsEntries@CHstsContainerProps@@QEAAJHPEAK@Z; CHstsContainerProps::PurgeHstsEntries(int,ulong *)
0x1801af0ee  mov     edi, eax
0x1801af0f0  test    eax, eax
0x1801af0f2  jns     short loc_1801AF0FD
0x1801af0f4  mov     [rbp+var_2C], 172h
0x1801af0fb  jmp     short loc_1801AF07E
0x1801af0fd  lea     rdx, [rbp+var_28]; struct CJetContext **
0x1801af101  mov     rcx, r14; this
0x1801af104  call    ?AcquirePartitionContext@CCacheStore@@QEAAJPEAPEAVCJetContext@@@Z; CCacheStore::AcquirePartitionContext(CJetContext * *)
0x1801af109  mov     edi, eax
0x1801af10b  test    eax, eax
0x1801af10d  jns     short loc_1801AF11F
0x1801af10f  mov     rsi, [rbp+var_28]
0x1801af113  mov     [rbp+var_2C], 178h
0x1801af11a  jmp     loc_1801AF07E
0x1801af11f  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801af123  call    cs:__imp_GetSystemTimeAsFileTime
0x1801af129  mov     rsi, [rbp+var_28]
0x1801af12d  mov     rcx, [rsi+10h]; sesid
0x1801af131  call    cs:__imp_JetBeginTransaction
0x1801af137  mov     ecx, eax; int
0x1801af139  mov     edx, ebx; int
0x1801af13b  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801af140  mov     edi, eax
0x1801af142  test    eax, eax
0x1801af144  js      loc_1801AF07E
0x1801af14a  mov     r8d, 2
0x1801af150  mov     rdx, r15
0x1801af153  mov     rcx, rsi
0x1801af156  call    ?SeekToPartition@CCacheStore@@SAJPEAVCJetContext@@PEAVCWxCallerIdentity@@W4PartitionType@@@Z; CCacheStore::SeekToPartition(CJetContext *,CWxCallerIdentity *,PartitionType)
0x1801af15b  mov     edi, eax
0x1801af15d  test    eax, eax
0x1801af15f  jns     short loc_1801AF17B
0x1801af161  mov     [rbp+var_2C], 181h
0x1801af168  mov     ebx, eax
0x1801af16a  mov     rcx, [rsi+10h]; sesid
0x1801af16e  xor     edx, edx; grbit
0x1801af170  call    cs:__imp_JetRollback
0x1801af176  jmp     loc_1801AF080
0x1801af17b  cmp     eax, ebx
0x1801af17d  jnz     short loc_1801AF183
0x1801af17f  mov     edi, ebx
0x1801af181  jmp     short loc_1801AF16A
0x1801af183  mov     rdx, [rsi+20h]; tableid
0x1801af187  mov     r8d, 2; prep
0x1801af18d  mov     rcx, [rsi+10h]; sesid
0x1801af191  call    cs:__imp_JetPrepareUpdate
0x1801af197  mov     ecx, eax; int
0x1801af199  mov     edx, ebx; int
0x1801af19b  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801af1a0  mov     edi, eax
0x1801af1a2  test    eax, eax
0x1801af1a4  js      short loc_1801AF168
0x1801af1a6  mov     r9d, 8; unsigned int
0x1801af1ac  lea     r8, [rbp+SystemTimeAsFileTime]; void *
0x1801af1b0  mov     rcx, rsi; this
0x1801af1b3  lea     edx, [r9-3]; unsigned int
0x1801af1b7  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1801af1bc  mov     edi, eax
0x1801af1be  test    eax, eax
0x1801af1c0  jns     short loc_1801AF1E1
0x1801af1c2  mov     [rbp+var_2C], 18Fh
0x1801af1c9  mov     rdx, [rsi+20h]; tableid
0x1801af1cd  mov     r8d, 3; prep
0x1801af1d3  mov     rcx, [rsi+10h]; sesid
0x1801af1d7  mov     ebx, edi
0x1801af1d9  call    cs:__imp_JetPrepareUpdate
0x1801af1df  jmp     short loc_1801AF16A
0x1801af1e1  mov     rdx, [rsi+20h]; tableid
0x1801af1e5  xor     r9d, r9d; cbBookmark
0x1801af1e8  mov     rcx, [rsi+10h]; sesid
0x1801af1ec  xor     r8d, r8d; pvBookmark
0x1801af1ef  mov     [rsp+60h+pcbActual], 0; pcbActual
0x1801af1f8  call    cs:__imp_JetUpdate
0x1801af1fe  mov     ecx, eax; int
0x1801af200  mov     edx, ebx; int
0x1801af202  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801af207  mov     edi, eax
0x1801af209  test    eax, eax
0x1801af20b  js      short loc_1801AF1C9
0x1801af20d  mov     rcx, [rsi+10h]; sesid
0x1801af211  mov     edx, ebx; grbit
0x1801af213  call    cs:__imp_JetCommitTransaction
0x1801af219  mov     ecx, eax; int
0x1801af21b  mov     edx, ebx; int
0x1801af21d  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801af222  mov     edi, eax
0x1801af224  mov     ebx, eax
0x1801af226  test    eax, eax
0x1801af228  jns     loc_1801AF080
0x1801af22e  jmp     loc_1801AF16A
```
