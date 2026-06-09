# CHstsContainerProps::PurgeHstsEntries(int,ulong *)

- ea: `0x1801af358`
- end: `0x1801af5f7`
- name: `?PurgeHstsEntries@CHstsContainerProps@@QEAAJHPEAK@Z`
- size: `671`
- prototype: `__int64 __fastcall(CHstsContainerProps *__hidden this, int, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801aefa8`
- `0x1801af600`

## callees

- `0x180020fc4`
- `0x18007ec9c`
- `0x180083540`
- `0x1800838d8`
- `0x180083dc4`
- `0x1800861f8`
- `0x1800939b8`
- `0x18014a7a0`
- `0x1801af358`
- `0x1801e1790`
- `0x1801e59e0`
- `0x1801eb2c0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801af3e2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801af3e2`
- `ESENT!JetDelete` at `0x1801af4ee`
- `ESENT!JetDelete` at `0x1801af4ee`
- `ESENT!JetCommitTransaction` at `0x1801af556`
- `ESENT!JetCommitTransaction` at `0x1801af556`
- `ESENT!JetRollback` at `0x1801af58c`
- `ESENT!JetRollback` at `0x1801af58c`
- `ESENT!JetBeginTransaction` at `0x1801af412`
- `ESENT!JetBeginTransaction` at `0x1801af412`
- `ESENT!JetMove` at `0x1801af459`
- `ESENT!JetMove` at `0x1801af459`

## pseudocode

```c
__int64 __fastcall CHstsContainerProps::PurgeHstsEntries(CJetContextList **this, int a2, unsigned int *a3)
{
  int v4; // edi
  int v6; // r12d
  int HstsEntryAtCursor; // eax
  JET_SESID *v8; // r14
  int v9; // ebx
  JET_ERR v10; // eax
  unsigned int v11; // r15d
  int v12; // ebx
  JET_ERR v13; // eax
  JET_ERR v14; // eax
  unsigned int v15; // edi
  int v16; // edx
  int v17; // ecx
  int v18; // r8d
  JET_ERR v19; // eax
  unsigned __int64 v21; // [rsp+30h] [rbp-39h] BYREF
  int v22; // [rsp+38h] [rbp-31h]
  struct CJetContext *v23; // [rsp+40h] [rbp-29h] BYREF
  struct CInFlightEntry *v24; // [rsp+48h] [rbp-21h] BYREF
  __int128 v25; // [rsp+50h] [rbp-19h] BYREF
  __int128 v26; // [rsp+60h] [rbp-9h]
  __int64 v27; // [rsp+70h] [rbp+7h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp+Fh] BYREF

  v22 = a2;
  HIDWORD(v21) = 0;
  v23 = 0;
  v27 = 0;
  v4 = a2;
  v24 = 0;
  SystemTimeAsFileTime = 0;
  v25 = 0;
  v6 = 0;
  v26 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_dq(1036, 20, (unsigned int)&WPP_ae00b7117931323f1bc64bef90768346_Traceguids, a2, (__int64)a3);
  if ( a3 )
    *a3 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  HstsEntryAtCursor = CJetContextList::AcquireContext(this[11], &v23, 0);
  v8 = (JET_SESID *)v23;
  v9 = HstsEntryAtCursor;
  if ( HstsEntryAtCursor >= 0 )
  {
    v10 = JetBeginTransaction(*((_QWORD *)v23 + 2));
    HstsEntryAtCursor = HRESULTFromJET_ERR(v10, 1);
    v9 = HstsEntryAtCursor;
    if ( HstsEntryAtCursor >= 0 )
    {
      v11 = 0;
      v12 = 0x80000000;
      v6 = 1;
      while ( 1 )
      {
        v21 = 0;
        WxHeapFree<_WX_AVL_TABLE>(&v25);
        v13 = JetMove(v8[2], v8[4], v12, 0);
        if ( v13 == -1603 )
          break;
        HstsEntryAtCursor = HRESULTFromJET_ERR(v13, 1);
        v9 = HstsEntryAtCursor;
        if ( HstsEntryAtCursor < 0 )
          goto LABEL_27;
        HstsEntryAtCursor = GetHstsEntryAtCursor((struct CJetContext *)v8, (struct _RPC_HSTS_ENTRY *)&v25, &v21);
        v9 = HstsEntryAtCursor;
        if ( HstsEntryAtCursor < 0 )
        {
          HIDWORD(v21) = 678;
          goto LABEL_27;
        }
        if ( *((_QWORD *)&v26 + 1) != 0x7FFFFFFFFFFFFFFFLL
          && (v4
           || *(_QWORD *)&SystemTimeAsFileTime >= (unsigned __int64)v26
           || *(unsigned __int64 *)&SystemTimeAsFileTime >= *((_QWORD *)&v26 + 1) + 77760000000000LL) )
        {
          HstsEntryAtCursor = CInFlightLocks::AcquireLock(this[10], v21, &v24);
          v9 = HstsEntryAtCursor;
          if ( HstsEntryAtCursor < 0 )
          {
            HIDWORD(v21) = 705;
            goto LABEL_27;
          }
          v14 = JetDelete(v8[2], v8[4]);
          v9 = HRESULTFromJET_ERR(v14, 1);
          v15 = v9;
          if ( v9 < 0 )
            goto LABEL_28;
          CInFlightLocks::ReleaseLock(this[10], &v24);
          ++v11;
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_dS(v17, v16, v18, v11, v25);
          v4 = v22;
        }
        v12 = 1;
      }
      v19 = JetCommitTransaction(v8[2], 1u);
      HstsEntryAtCursor = HRESULTFromJET_ERR(v19, 1);
      v9 = HstsEntryAtCursor;
      if ( HstsEntryAtCursor >= 0 )
      {
        v6 = 0;
        if ( a3 )
          *a3 = v11;
      }
    }
  }
  else
  {
    HIDWORD(v21) = 660;
  }
LABEL_27:
  v15 = HstsEntryAtCursor;
LABEL_28:
  WxHeapFree<_WX_AVL_TABLE>(&v25);
  if ( v6 )
    JetRollback(v8[2], 0);
  CJetContextList::ReleaseContext(this[11], &v23);
  CInFlightLocks::ReleaseLock(this[10], &v24);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 22, &WPP_ae00b7117931323f1bc64bef90768346_Traceguids, (unsigned int)v9);
  return v15;
}

```

## disassembly

```asm
0x1801af358  mov     [rsp-8+arg_18], rbx
0x1801af35d  push    rbp
0x1801af35e  push    rsi
0x1801af35f  push    rdi
0x1801af360  push    r12
0x1801af362  push    r13
0x1801af364  push    r14
0x1801af366  push    r15
0x1801af368  lea     rbp, [rsp-27h]
0x1801af36d  sub     rsp, 90h
0x1801af374  mov     rax, cs:__security_cookie
0x1801af37b  xor     rax, rsp
0x1801af37e  mov     [rbp+57h+var_40], rax
0x1801af382  xor     ebx, ebx
0x1801af384  mov     [rbp+57h+var_88], edx
0x1801af387  xorps   xmm0, xmm0
0x1801af38a  mov     dword ptr [rbp+57h+var_90+4], ebx
0x1801af38d  xor     eax, eax
0x1801af38f  mov     [rbp+57h+var_80], rbx
0x1801af393  mov     [rbp+57h+var_50], rax
0x1801af397  mov     rsi, r8
0x1801af39a  mov     edi, edx
0x1801af39c  mov     [rbp+57h+var_78], rbx
0x1801af3a0  mov     r13, rcx
0x1801af3a3  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1801af3a7  movups  [rbp+57h+var_70], xmm0
0x1801af3ab  mov     r12d, ebx
0x1801af3ae  movups  [rbp+57h+var_60], xmm0
0x1801af3b2  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801af3b9  jz      short loc_1801AF3D7
0x1801af3bb  mov     [rsp+0C0h+var_A0], r8
0x1801af3c0  lea     edx, [rbx+14h]
0x1801af3c3  lea     r8, WPP_ae00b7117931323f1bc64bef90768346_Traceguids
0x1801af3ca  mov     ecx, 40Ch
0x1801af3cf  mov     r9d, edi
0x1801af3d2  call    WPP_SF_dq
0x1801af3d7  test    rsi, rsi
0x1801af3da  jz      short loc_1801AF3DE
0x1801af3dc  mov     [rsi], ebx
0x1801af3de  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801af3e2  call    cs:__imp_GetSystemTimeAsFileTime
0x1801af3e8  mov     rcx, [r13+58h]; this
0x1801af3ec  lea     rdx, [rbp+57h+var_80]; struct CJetContext **
0x1801af3f0  xor     r8d, r8d; int *
0x1801af3f3  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1801af3f8  mov     r14, [rbp+57h+var_80]
0x1801af3fc  mov     ebx, eax
0x1801af3fe  test    eax, eax
0x1801af400  jns     short loc_1801AF40E
0x1801af402  mov     dword ptr [rbp+57h+var_90+4], 294h
0x1801af409  jmp     loc_1801AF576
0x1801af40e  mov     rcx, [r14+10h]; sesid
0x1801af412  call    cs:__imp_JetBeginTransaction
0x1801af418  mov     ecx, eax; int
0x1801af41a  mov     edx, 1; int
0x1801af41f  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801af424  mov     ebx, eax
0x1801af426  test    eax, eax
0x1801af428  js      loc_1801AF576
0x1801af42e  xor     r15d, r15d
0x1801af431  mov     ebx, 80000000h
0x1801af436  lea     r12d, [r15+1]
0x1801af43a  lea     rcx, [rbp+57h+var_70]
0x1801af43e  mov     qword ptr [rbp-39h], 0
0x1801af446  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x1801af44b  mov     rdx, [r14+20h]; tableid
0x1801af44f  xor     r9d, r9d; grbit
0x1801af452  mov     rcx, [r14+10h]; sesid
0x1801af456  mov     r8d, ebx; cRow
0x1801af459  call    cs:__imp_JetMove
0x1801af45f  cmp     eax, 0FFFFF9BDh
0x1801af464  jz      loc_1801AF54D
0x1801af46a  mov     edx, r12d; int
0x1801af46d  mov     ecx, eax; int
0x1801af46f  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801af474  mov     ebx, eax
0x1801af476  test    eax, eax
0x1801af478  js      loc_1801AF576
0x1801af47e  lea     r8, [rbp+57h+var_90]; unsigned __int64 *
0x1801af482  mov     rcx, r14; struct CJetContext *
0x1801af485  lea     rdx, [rbp+57h+var_70]; struct _RPC_HSTS_ENTRY *
0x1801af489  call    ?GetHstsEntryAtCursor@@YAJPEAVCJetContext@@PEAU_RPC_HSTS_ENTRY@@PEA_K@Z; GetHstsEntryAtCursor(CJetContext *,_RPC_HSTS_ENTRY *,unsigned __int64 *)
0x1801af48e  mov     ebx, eax
0x1801af490  test    eax, eax
0x1801af492  js      loc_1801AF544
0x1801af498  mov     rcx, qword ptr [rbp+57h+var_60+8]
0x1801af49c  mov     rax, 7FFFFFFFFFFFFFFFh
0x1801af4a6  cmp     rcx, rax
0x1801af4a9  jz      loc_1801AF533
0x1801af4af  test    edi, edi
0x1801af4b1  jnz     short loc_1801AF4CF
0x1801af4b3  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1801af4b7  cmp     rax, qword ptr [rbp+57h+var_60]
0x1801af4bb  jnb     short loc_1801AF4CF
0x1801af4bd  mov     rdx, 46B8E92D8000h
0x1801af4c7  add     rdx, rcx
0x1801af4ca  cmp     rax, rdx
0x1801af4cd  jb      short loc_1801AF533
0x1801af4cf  mov     rdx, [rbp+57h+var_90]; unsigned __int64
0x1801af4d3  lea     r8, [rbp+57h+var_78]; struct CInFlightEntry **
0x1801af4d7  mov     rcx, [r13+50h]; this
0x1801af4db  call    ?AcquireLock@CInFlightLocks@@QEAAJ_KPEAPEAVCInFlightEntry@@@Z; CInFlightLocks::AcquireLock(unsigned __int64,CInFlightEntry * *)
0x1801af4e0  mov     ebx, eax
0x1801af4e2  test    eax, eax
0x1801af4e4  js      short loc_1801AF53B
0x1801af4e6  mov     rdx, [r14+20h]; tableid
0x1801af4ea  mov     rcx, [r14+10h]; sesid
0x1801af4ee  call    cs:__imp_JetDelete
0x1801af4f4  mov     ecx, eax; int
0x1801af4f6  mov     edx, r12d; int
0x1801af4f9  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801af4fe  mov     ebx, eax
0x1801af500  mov     edi, eax
0x1801af502  test    eax, eax
0x1801af504  js      short loc_1801AF578
0x1801af506  mov     rcx, [r13+50h]; this
0x1801af50a  lea     rdx, [rbp+57h+var_78]; struct CInFlightEntry **
0x1801af50e  call    ?ReleaseLock@CInFlightLocks@@QEAAXPEAPEAVCInFlightEntry@@@Z; CInFlightLocks::ReleaseLock(CInFlightEntry * *)
0x1801af513  inc     r15d
0x1801af516  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801af51d  jz      short loc_1801AF530
0x1801af51f  mov     rax, qword ptr [rbp+57h+var_70]
0x1801af523  mov     r9d, r15d
0x1801af526  mov     [rsp+0C0h+var_A0], rax
0x1801af52b  call    WPP_SF_dS
0x1801af530  mov     edi, [rbp+57h+var_88]
0x1801af533  mov     ebx, r12d
0x1801af536  jmp     loc_1801AF43A
0x1801af53b  mov     dword ptr [rbp+57h+var_90+4], 2C1h
0x1801af542  jmp     short loc_1801AF576
0x1801af544  mov     dword ptr [rbp+57h+var_90+4], 2A6h
0x1801af54b  jmp     short loc_1801AF576
0x1801af54d  mov     rcx, [r14+10h]; sesid
0x1801af551  mov     ebx, r12d
0x1801af554  mov     edx, ebx; grbit
0x1801af556  call    cs:__imp_JetCommitTransaction
0x1801af55c  mov     ecx, eax; int
0x1801af55e  mov     edx, ebx; int
0x1801af560  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801af565  mov     ebx, eax
0x1801af567  test    eax, eax
0x1801af569  js      short loc_1801AF576
0x1801af56b  xor     r12d, r12d
0x1801af56e  test    rsi, rsi
0x1801af571  jz      short loc_1801AF576
0x1801af573  mov     [rsi], r15d
0x1801af576  mov     edi, eax
0x1801af578  lea     rcx, [rbp+57h+var_70]
0x1801af57c  call    ??$WxHeapFree@U_WX_AVL_TABLE@@@@YAXPEAPEAU_WX_AVL_TABLE@@@Z; WxHeapFree<_WX_AVL_TABLE>(_WX_AVL_TABLE * *)
0x1801af581  test    r12d, r12d
0x1801af584  jz      short loc_1801AF592
0x1801af586  mov     rcx, [r14+10h]; sesid
0x1801af58a  xor     edx, edx; grbit
0x1801af58c  call    cs:__imp_JetRollback
0x1801af592  mov     rcx, [r13+58h]; this
0x1801af596  lea     rdx, [rbp+57h+var_80]; struct CJetContext **
0x1801af59a  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x1801af59f  mov     rcx, [r13+50h]; this
0x1801af5a3  lea     rdx, [rbp+57h+var_78]; struct CInFlightEntry **
0x1801af5a7  call    ?ReleaseLock@CInFlightLocks@@QEAAXPEAPEAVCInFlightEntry@@@Z; CInFlightLocks::ReleaseLock(CInFlightEntry * *)
0x1801af5ac  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801af5b3  jz      short loc_1801AF5CE
0x1801af5b5  mov     edx, 16h
0x1801af5ba  lea     r8, WPP_ae00b7117931323f1bc64bef90768346_Traceguids
0x1801af5c1  mov     ecx, 40Ch
0x1801af5c6  mov     r9d, ebx
0x1801af5c9  call    WPP_SF_d
0x1801af5ce  mov     eax, edi
0x1801af5d0  mov     rcx, [rbp+57h+var_40]
0x1801af5d4  xor     rcx, rsp; StackCookie
0x1801af5d7  call    __security_check_cookie
0x1801af5dc  mov     rbx, [rsp+0C0h+arg_18]
0x1801af5e4  add     rsp, 90h
0x1801af5eb  pop     r15
0x1801af5ed  pop     r14
0x1801af5ef  pop     r13
0x1801af5f1  pop     r12
0x1801af5f3  pop     rdi
0x1801af5f4  pop     rsi
0x1801af5f5  pop     rbp
0x1801af5f6  retn
```
