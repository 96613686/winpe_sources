# CAppCache::UpdateFlags(ushort const *,ulong)

- ea: `0x1801c33e8`
- end: `0x1801c365f`
- name: `?UpdateFlags@CAppCache@@AEAAJPEBGK@Z`
- size: `631`
- prototype: `__int64 __fastcall(CAppCache *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801be4c0`

## callees

- `0x180021360`
- `0x18007ec9c`
- `0x18007ed10`
- `0x180083dc4`
- `0x1800861f8`
- `0x1800fa844`
- `0x18014a7a0`
- `0x1801c298c`
- `0x1801c33e8`
- `0x1801e1790`
- `0x1801e2e84`

## import_xrefs

- `ESENT!JetCommitTransaction` at `0x1801c363d`
- `ESENT!JetCommitTransaction` at `0x1801c363d`
- `ESENT!JetUpdate` at `0x1801c361e`
- `ESENT!JetUpdate` at `0x1801c361e`
- `ESENT!JetPrepareUpdate` at `0x1801c355e`
- `ESENT!JetPrepareUpdate` at `0x1801c35a8`
- `ESENT!JetPrepareUpdate` at `0x1801c355e`
- `ESENT!JetPrepareUpdate` at `0x1801c35a8`
- `ESENT!JetRollback` at `0x1801c3545`
- `ESENT!JetRollback` at `0x1801c3545`
- `ESENT!JetBeginTransaction` at `0x1801c3501`
- `ESENT!JetBeginTransaction` at `0x1801c3501`

## string_xrefs

- `0x1801c34dd`: `AppCacheIdIndex`

## pseudocode

```c
__int64 __fastcall CAppCache::UpdateFlags(CAppCache *this, const unsigned __int16 *a2)
{
  unsigned int v2; // edi
  int v5; // eax
  unsigned int v6; // r9d
  JET_SESID *v7; // rsi
  unsigned int v8; // ebx
  JET_ERR v10; // eax
  int v11; // eax
  JET_ERR v12; // eax
  int BasicColumn; // eax
  JET_ERR v14; // eax
  JET_ERR v15; // eax
  CJetContext *v16; // [rsp+38h] [rbp-18h] BYREF
  int v17; // [rsp+40h] [rbp-10h] BYREF
  int v18; // [rsp+44h] [rbp-Ch] BYREF

  v2 = 1;
  v18 = 1;
  v16 = 0;
  v17 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qSd(1036, 59, (unsigned int)&WPP_c3d0725a2afd3bb4de7e7a6d1e0eea73_Traceguids, (_DWORD)this, (__int64)a2, 1);
  v5 = CJetContextList::AcquireContext(*(CJetContextList **)(*((_QWORD *)this + 19) + 16LL), &v16, 0);
  v7 = (JET_SESID *)v16;
  v8 = v5;
  if ( v5 < 0
    || (v5 = CJetContext::SetCurrentIndex(v16, 1u, L"AppCacheIdIndex", v6), v8 = v5, v5 < 0)
    || (v10 = JetBeginTransaction(v7[2]), v5 = HRESULTFromJET_ERR(v10, 1), v8 = v5, v5 < 0) )
  {
    v2 = v5;
    goto LABEL_5;
  }
  v11 = CAppCache::SeekToAppCacheUrl(this, (struct CJetContext *)v7, a2);
  v8 = v11;
  if ( v11 == 1 )
  {
    v8 = 1;
LABEL_16:
    JetRollback(v7[2], 0);
    goto LABEL_5;
  }
  if ( v11 < 0 )
    goto LABEL_15;
  v12 = JetPrepareUpdate(v7[2], v7[4], 2u);
  v11 = HRESULTFromJET_ERR(v12, 1);
  v8 = v11;
  if ( v11 < 0 )
    goto LABEL_15;
  BasicColumn = CJetContext::GetBasicColumn((CJetContext *)v7, 4u, &v17, 4u);
  v8 = BasicColumn;
  if ( BasicColumn < 0 )
    goto LABEL_19;
  if ( (v17 & 1) != 0 )
  {
    v8 = 0;
    v2 = 0;
    goto LABEL_20;
  }
  v17 |= 1u;
  BasicColumn = CJetContext::SetBasicColumn((CJetContext *)v7, 4u, &v17, 4u);
  v8 = BasicColumn;
  if ( BasicColumn < 0
    || (BasicColumn = CJetContext::SetBasicColumn((CJetContext *)v7, 5u, &v18, 4u), v8 = BasicColumn, BasicColumn < 0)
    || (v14 = JetUpdate(v7[2], v7[4], 0, 0, 0),
        BasicColumn = HRESULTFromJET_ERR(v14, 1),
        v8 = BasicColumn,
        BasicColumn < 0) )
  {
LABEL_19:
    v2 = BasicColumn;
LABEL_20:
    JetPrepareUpdate(v7[2], v7[4], 3u);
    goto LABEL_16;
  }
  v15 = JetCommitTransaction(v7[2], 1u);
  v11 = HRESULTFromJET_ERR(v15, 1);
  v8 = v11;
  if ( v11 < 0 )
  {
LABEL_15:
    v2 = v11;
    goto LABEL_16;
  }
  v8 = 0;
  v2 = 0;
LABEL_5:
  if ( v7 )
    CJetContextList::ReleaseContext(*(CJetContextList **)(*((_QWORD *)this + 19) + 16LL), &v16);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 60, &WPP_c3d0725a2afd3bb4de7e7a6d1e0eea73_Traceguids, v8);
  return v2;
}

```

## disassembly

```asm
0x1801c33e8  mov     [rsp-28h+arg_10], rbx
0x1801c33ed  push    rbp
0x1801c33ee  push    rsi
0x1801c33ef  push    rdi
0x1801c33f0  push    r14
0x1801c33f2  push    r15
0x1801c33f4  mov     rbp, rsp
0x1801c33f7  sub     rsp, 50h
0x1801c33fb  mov     rax, cs:__security_cookie
0x1801c3402  xor     rax, rsp
0x1801c3405  mov     [rbp+var_8], rax
0x1801c3409  mov     edi, 1
0x1801c340e  mov     [rbp+var_1C], 0
0x1801c3415  mov     [rbp+var_C], edi
0x1801c3418  mov     r14, rdx
0x1801c341b  mov     r15, rcx
0x1801c341e  mov     [rbp+var_18], 0
0x1801c3426  mov     [rbp+var_10], 0
0x1801c342d  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801c3434  jz      short loc_1801C3456
0x1801c3436  lea     edx, [rdi+3Ah]
0x1801c3439  mov     [rsp+50h+var_28], edi
0x1801c343d  mov     ecx, 40Ch
0x1801c3442  mov     [rsp+50h+pcbActual], r14
0x1801c3447  mov     r9, r15
0x1801c344a  lea     r8, WPP_c3d0725a2afd3bb4de7e7a6d1e0eea73_Traceguids
0x1801c3451  call    WPP_SF_qSd
0x1801c3456  mov     rcx, [r15+98h]
0x1801c345d  lea     rdx, [rbp+var_18]; struct CJetContext **
0x1801c3461  xor     r8d, r8d; int *
0x1801c3464  mov     rcx, [rcx+10h]; this
0x1801c3468  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1801c346d  mov     rsi, [rbp+var_18]
0x1801c3471  mov     ebx, eax
0x1801c3473  test    eax, eax
0x1801c3475  jns     short loc_1801C34DD
0x1801c3477  mov     [rbp+var_1C], 727h
0x1801c347e  mov     edi, eax
0x1801c3480  test    rsi, rsi
0x1801c3483  jz      short loc_1801C3499
0x1801c3485  mov     rcx, [r15+98h]
0x1801c348c  lea     rdx, [rbp+var_18]; struct CJetContext **
0x1801c3490  mov     rcx, [rcx+10h]; this
0x1801c3494  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x1801c3499  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801c34a0  jz      short loc_1801C34BB
0x1801c34a2  mov     edx, 3Ch ; '<'
0x1801c34a7  lea     r8, WPP_c3d0725a2afd3bb4de7e7a6d1e0eea73_Traceguids
0x1801c34ae  mov     ecx, 40Ch
0x1801c34b3  mov     r9d, ebx
0x1801c34b6  call    WPP_SF_d
0x1801c34bb  mov     eax, edi
0x1801c34bd  mov     rcx, [rbp+var_8]
0x1801c34c1  xor     rcx, rsp; StackCookie
0x1801c34c4  call    __security_check_cookie
0x1801c34c9  mov     rbx, [rsp+50h+arg_10]
0x1801c34d1  add     rsp, 50h
0x1801c34d5  pop     r15
0x1801c34d7  pop     r14
0x1801c34d9  pop     rdi
0x1801c34da  pop     rsi
0x1801c34db  pop     rbp
0x1801c34dc  retn
0x1801c34dd  lea     r8, aAppcacheidinde; "AppCacheIdIndex"
0x1801c34e4  mov     edx, edi; unsigned int
0x1801c34e6  mov     rcx, rsi; this
0x1801c34e9  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1801c34ee  mov     ebx, eax
0x1801c34f0  test    eax, eax
0x1801c34f2  jns     short loc_1801C34FD
0x1801c34f4  mov     [rbp+var_1C], 72Ah
0x1801c34fb  jmp     short loc_1801C347E
0x1801c34fd  mov     rcx, [rsi+10h]; sesid
0x1801c3501  call    cs:__imp_JetBeginTransaction
0x1801c3507  mov     ecx, eax; int
0x1801c3509  mov     edx, edi; int
0x1801c350b  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801c3510  mov     ebx, eax
0x1801c3512  test    eax, eax
0x1801c3514  js      loc_1801C347E
0x1801c351a  mov     r8, r14; unsigned __int16 *
0x1801c351d  mov     rdx, rsi; struct CJetContext *
0x1801c3520  mov     rcx, r15; this
0x1801c3523  call    ?SeekToAppCacheUrl@CAppCache@@AEAAJPEAVCJetContext@@PEBG@Z; CAppCache::SeekToAppCacheUrl(CJetContext *,ushort const *)
0x1801c3528  mov     ebx, eax
0x1801c352a  cmp     eax, edi
0x1801c352c  jnz     short loc_1801C3532
0x1801c352e  mov     ebx, edi
0x1801c3530  jmp     short loc_1801C353F
0x1801c3532  test    eax, eax
0x1801c3534  jns     short loc_1801C3550
0x1801c3536  mov     [rbp+var_1C], 734h
0x1801c353d  mov     edi, eax
0x1801c353f  mov     rcx, [rsi+10h]; sesid
0x1801c3543  xor     edx, edx; grbit
0x1801c3545  call    cs:__imp_JetRollback
0x1801c354b  jmp     loc_1801C3480
0x1801c3550  mov     rdx, [rsi+20h]; tableid
0x1801c3554  mov     r8d, 2; prep
0x1801c355a  mov     rcx, [rsi+10h]; sesid
0x1801c355e  call    cs:__imp_JetPrepareUpdate
0x1801c3564  mov     ecx, eax; int
0x1801c3566  mov     edx, edi; int
0x1801c3568  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801c356d  mov     ebx, eax
0x1801c356f  test    eax, eax
0x1801c3571  js      short loc_1801C353D
0x1801c3573  mov     r14d, 4
0x1801c3579  lea     r8, [rbp+var_10]; void *
0x1801c357d  mov     r9d, r14d; unsigned int
0x1801c3580  mov     edx, r14d; unsigned int
0x1801c3583  mov     rcx, rsi; this
0x1801c3586  call    ?GetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::GetBasicColumn(ulong,void *,ulong)
0x1801c358b  mov     ebx, eax
0x1801c358d  test    eax, eax
0x1801c358f  jns     short loc_1801C35B0
0x1801c3591  mov     [rbp+var_1C], 73Dh
0x1801c3598  mov     edi, eax
0x1801c359a  mov     rdx, [rsi+20h]; tableid
0x1801c359e  mov     r8d, 3; prep
0x1801c35a4  mov     rcx, [rsi+10h]; sesid
0x1801c35a8  call    cs:__imp_JetPrepareUpdate
0x1801c35ae  jmp     short loc_1801C353F
0x1801c35b0  mov     eax, [rbp+var_10]
0x1801c35b3  test    dil, al
0x1801c35b6  jz      short loc_1801C35BE
0x1801c35b8  xor     ebx, ebx
0x1801c35ba  xor     edi, edi
0x1801c35bc  jmp     short loc_1801C359A
0x1801c35be  or      eax, edi
0x1801c35c0  lea     r8, [rbp+var_10]; void *
0x1801c35c4  mov     r9d, r14d; unsigned int
0x1801c35c7  mov     [rbp+var_10], eax
0x1801c35ca  mov     edx, r14d; unsigned int
0x1801c35cd  mov     rcx, rsi; this
0x1801c35d0  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1801c35d5  mov     ebx, eax
0x1801c35d7  test    eax, eax
0x1801c35d9  jns     short loc_1801C35E4
0x1801c35db  mov     [rbp+var_1C], 74Ch
0x1801c35e2  jmp     short loc_1801C3598
0x1801c35e4  mov     r9d, r14d; unsigned int
0x1801c35e7  lea     r8, [rbp+var_C]; void *
0x1801c35eb  mov     edx, 5; unsigned int
0x1801c35f0  mov     rcx, rsi; this
0x1801c35f3  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1801c35f8  mov     ebx, eax
0x1801c35fa  test    eax, eax
0x1801c35fc  jns     short loc_1801C3607
0x1801c35fe  mov     [rbp+var_1C], 752h
0x1801c3605  jmp     short loc_1801C3598
0x1801c3607  mov     rdx, [rsi+20h]; tableid
0x1801c360b  xor     r9d, r9d; cbBookmark
0x1801c360e  mov     rcx, [rsi+10h]; sesid
0x1801c3612  xor     r8d, r8d; pvBookmark
0x1801c3615  mov     [rsp+50h+pcbActual], 0; pcbActual
0x1801c361e  call    cs:__imp_JetUpdate
0x1801c3624  mov     ecx, eax; int
0x1801c3626  mov     edx, edi; int
0x1801c3628  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801c362d  mov     ebx, eax
0x1801c362f  test    eax, eax
0x1801c3631  js      loc_1801C3598
0x1801c3637  mov     rcx, [rsi+10h]; sesid
0x1801c363b  mov     edx, edi; grbit
0x1801c363d  call    cs:__imp_JetCommitTransaction
0x1801c3643  mov     ecx, eax; int
0x1801c3645  mov     edx, edi; int
0x1801c3647  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1801c364c  mov     ebx, eax
0x1801c364e  test    eax, eax
0x1801c3650  js      loc_1801C353D
0x1801c3656  xor     ebx, ebx
0x1801c3658  xor     edi, edi
0x1801c365a  jmp     loc_1801C3480
```
