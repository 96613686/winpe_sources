# CCacheContainer::UpdateUrl(ushort const *,_URLCACHE_UPDATE_DATA const *,ulong)

- ea: `0x180082cc0`
- end: `0x180083539`
- name: `?UpdateUrl@CCacheContainer@@QEAAJPEBGPEBU_URLCACHE_UPDATE_DATA@@K@Z`
- size: `2169`
- prototype: `__int64 __fastcall(CCacheContainer *__hidden this, const unsigned __int16 *, const struct _URLCACHE_UPDATE_DATA *, unsigned int)`
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180041630`
- `0x1801c30d8`

## callees

- `0x180027ec0`
- `0x18007e620`
- `0x18007ec9c`
- `0x18007ed10`
- `0x180082700`
- `0x180082cc0`
- `0x180083540`
- `0x1800838d8`
- `0x180083dc4`
- `0x180085460`
- `0x180085898`
- `0x180086aa4`
- `0x1800eee94`
- `0x1800fa844`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801a830c`
- `0x1801e13c0`
- `0x1801e1790`
- `0x1801e1b60`
- `0x1801e1d20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180083090`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180083090`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008304f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008304f`
- `ESENT!JetSetCurrentIndex2W` at `0x180083242`
- `ESENT!JetSetCurrentIndex2W` at `0x180083242`
- `ESENT!JetSetColumn` at `0x180083151`
- `ESENT!JetSetColumn` at `0x180083211`
- `ESENT!JetSetColumn` at `0x1800832cd`
- `ESENT!JetSetColumn` at `0x180083151`
- `ESENT!JetSetColumn` at `0x180083211`
- `ESENT!JetSetColumn` at `0x1800832cd`
- `ESENT!JetCommitTransaction` at `0x180083270`
- `ESENT!JetCommitTransaction` at `0x180083270`
- `ESENT!JetUpdate` at `0x180083101`
- `ESENT!JetUpdate` at `0x180083101`
- `ESENT!JetPrepareUpdate` at `0x180082f51`
- `ESENT!JetPrepareUpdate` at `0x18008351b`
- `ESENT!JetPrepareUpdate` at `0x180082f51`
- `ESENT!JetPrepareUpdate` at `0x18008351b`
- `ESENT!JetRollback` at `0x180082db5`
- `ESENT!JetRollback` at `0x180082db5`
- `ESENT!JetBeginTransaction` at `0x180082f00`
- `ESENT!JetBeginTransaction` at `0x180082f00`

## pseudocode

```c
__int64 __fastcall CCacheContainer::UpdateUrl(
        CCacheContainer *this,
        const unsigned __int16 *a2,
        const struct _URLCACHE_UPDATE_DATA *a3,
        __int16 a4)
{
  const unsigned __int16 *v5; // r15
  CJetContext *v8; // rdi
  int v9; // r12d
  int v10; // r8d
  int v11; // ecx
  JET_ERR updated; // ebx
  int v13; // esi
  __int64 v14; // rsi
  unsigned __int64 v16; // r15
  int v17; // eax
  int v18; // edx
  JET_ERR v19; // eax
  unsigned __int64 v20; // r8
  int v21; // eax
  JET_ERR v22; // eax
  __int128 v23; // xmm1
  __int128 v24; // xmm1
  int v25; // r15d
  JET_ERR v26; // eax
  JET_TABLEID v27; // rdx
  JET_SESID v28; // rcx
  JET_ERR v29; // eax
  JET_ERR v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // edx
  __int64 v33; // r11
  unsigned int i; // r10d
  __int64 v35; // rdx
  bool v36; // r8
  bool v37; // cl
  char v38; // dl
  CJetContext *v40; // [rsp+58h] [rbp-61h] BYREF
  struct CInFlightEntry *v41[2]; // [rsp+60h] [rbp-59h] BYREF
  __int128 v42; // [rsp+70h] [rbp-49h] BYREF
  __int128 pvData; // [rsp+80h] [rbp-39h] BYREF
  unsigned int v44[4]; // [rsp+90h] [rbp-29h] BYREF
  unsigned __int8 *v45[2]; // [rsp+A0h] [rbp-19h]
  unsigned __int8 *v46[2]; // [rsp+B0h] [rbp-9h]
  unsigned int v47; // [rsp+C0h] [rbp+7h] BYREF
  unsigned __int8 *v48; // [rsp+C8h] [rbp+Fh] BYREF

  v5 = a2;
  v40 = 0;
  v41[0] = 0;
  v48 = 0;
  v47 = 0;
  v8 = 0;
  v9 = 0;
  memset_0(&v42, 0, 0x50u);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qSqd(
      1036,
      38,
      (unsigned int)&WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids,
      (_DWORD)this,
      (__int64)v5,
      (__int64)a3,
      a4);
  v11 = *((_DWORD *)this + 8) & 2;
  updated = v11 == 0 ? 0x80070005 : 0;
  if ( !v11 )
    goto LABEL_4;
  updated = CContainerProps::UpdateLastAccessTime(*((CContainerProps **)this + 5));
  if ( updated < 0 )
    goto LABEL_4;
  v16 = WxComputeUrlHash(v5);
  updated = CInFlightLocks::AcquireLock(*(CInFlightLocks **)(*((_QWORD *)this + 5) + 144LL), v16, v41);
  if ( updated < 0 )
  {
    v5 = a2;
LABEL_4:
    v13 = 0;
    goto LABEL_5;
  }
  v17 = CJetContextList::AcquireContext(*(CJetContextList **)(*((_QWORD *)this + 5) + 152LL), &v40, 0);
  v8 = v40;
  updated = v17;
  if ( v17 < 0 )
    goto LABEL_79;
  HIDWORD(v40) = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qdSD(v11, v18, v10, (_DWORD)v8, 0, (__int64)L"HashEntryIdIndex", 0);
  if ( *((_DWORD *)v8 + 12) )
  {
    v27 = *((_QWORD *)v8 + 4);
    v28 = *((_QWORD *)v8 + 2);
    *((_DWORD *)v8 + 12) = -1;
    v29 = JetSetCurrentIndex2W(v28, v27, L"HashEntryIdIndex", 0);
    updated = HRESULTFromJET_ERR(v29, 1);
    if ( updated >= 0 )
      *((_DWORD *)v8 + 12) = 0;
  }
  else
  {
    updated = 0;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 14, &WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)updated);
  if ( updated < 0
    || (v19 = JetBeginTransaction(*((_QWORD *)v8 + 2)), updated = HRESULTFromJET_ERR(v19, 1), updated < 0) )
  {
LABEL_79:
    v5 = a2;
    goto LABEL_56;
  }
  v20 = v16;
  v5 = a2;
  v9 = 1;
  v21 = SeekToEntry(v8, a2, v20);
  updated = v21;
  if ( v21 < 0 )
    goto LABEL_62;
  if ( v21 )
  {
    updated = -2147024894;
    goto LABEL_62;
  }
  v22 = JetPrepareUpdate(*((_QWORD *)v8 + 2), *((_QWORD *)v8 + 4), 2u);
  updated = HRESULTFromJET_ERR(v22, 1);
  if ( updated < 0 )
  {
LABEL_62:
    v13 = 0;
    goto LABEL_5;
  }
  v23 = *((_OWORD *)a3 + 1);
  v42 = *(_OWORD *)a3;
  pvData = v23;
  v24 = *((_OWORD *)a3 + 3);
  *(_OWORD *)v44 = *((_OWORD *)a3 + 2);
  *(_OWORD *)v45 = v24;
  *(_OWORD *)v46 = *((_OWORD *)a3 + 4);
  if ( (a4 & 0x40) == 0 )
    goto LABEL_33;
  v31 = v44[2];
  if ( v44[2] > 0x15180 )
    v31 = 86400;
  v44[2] = v31;
  updated = CJetContext::SetBasicColumn(v8, 0x16u, &v44[2], 4u);
  if ( updated < 0 )
    goto LABEL_56;
  if ( (a4 & 1) == 0 )
  {
    updated = CJetContext::GetBasicColumn(v8, 0xCu, &v42, 4u);
    if ( updated < 0 )
      goto LABEL_56;
  }
  if ( v44[2] )
  {
    LODWORD(v42) = v42 | 4;
LABEL_97:
    a4 |= 1u;
    goto LABEL_33;
  }
  updated = CJetContext::GetBinaryColumn(v8, v32, &v48, &v47);
  if ( updated < 0 )
    goto LABEL_56;
  v33 = 0;
  for ( i = v47 >> 3; (unsigned int)v33 < i; v33 = (unsigned int)(v33 + 1) )
  {
    v35 = *(_QWORD *)&v48[8 * v33];
    v36 = (v35 & 0xFFFFFFFFFFFFFFFLL) != 0;
    v37 = (v35 & 0x1000000000000000LL) != 0;
    v38 = 0;
    v11 = v37 && v36;
    if ( (*(_QWORD *)&v48[8 * v33] & 0xE000000000000000uLL) == 0 )
      v38 = v11;
    if ( v38 )
      goto LABEL_33;
  }
  if ( (_DWORD)v33 == i )
  {
    LODWORD(v42) = v42 & 0xFFFFFFFB;
    goto LABEL_97;
  }
LABEL_33:
  if ( (a4 & 1) != 0 )
  {
    updated = JetSetColumn(
                *((_QWORD *)v8 + 2),
                *((_QWORD *)v8 + 4),
                *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 5) + 8LL) + 48LL),
                &v42,
                4u,
                0,
                0);
    if ( updated < 0 )
      goto LABEL_56;
  }
  if ( (a4 & 2) != 0 )
  {
    updated = CJetContext::SetBasicColumn(v8, 0xEu, (char *)&v42 + 4, 4u);
    if ( updated < 0 )
      goto LABEL_56;
  }
  if ( (a4 & 4) != 0 )
  {
    updated = CJetContext::SetBasicColumn(v8, 0x13u, (char *)&v42 + 8, 8u);
    if ( updated < 0 )
      goto LABEL_56;
  }
  if ( (a4 & 8) != 0 )
  {
    updated = JetSetColumn(
                *((_QWORD *)v8 + 2),
                *((_QWORD *)v8 + 4),
                *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 5) + 8LL) + 60LL),
                &pvData,
                8u,
                0,
                0);
    if ( updated < 0 )
      goto LABEL_56;
  }
  if ( (a4 & 0x10) != 0 )
  {
    updated = JetSetColumn(
                *((_QWORD *)v8 + 2),
                *((_QWORD *)v8 + 4),
                *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 5) + 8LL) + 68LL),
                (char *)&pvData + 8,
                8u,
                0,
                0);
    if ( updated < 0 )
      goto LABEL_56;
  }
  if ( (a4 & 0x20) != 0 )
  {
    updated = CJetContext::SetBasicColumn(v8, 0x12u, v44, 8u);
    if ( updated < 0 )
      goto LABEL_56;
  }
  if ( (a4 & 0x80u) != 0 )
  {
    v10 = (int)v46[1];
    if ( !v46[1] && HIDWORD(v45[0]) )
    {
      updated = -2147024809;
      goto LABEL_56;
    }
    if ( HIDWORD(v45[0]) > 0x10000 )
    {
      updated = -2147024809;
      goto LABEL_56;
    }
    updated = CJetContext::SetBinaryColumn(v8, 0x18u, v46[1], HIDWORD(v45[0]));
    if ( updated < 0 )
      goto LABEL_56;
  }
  if ( (a4 & 0x100) != 0 )
  {
    v10 = (int)v45[1];
    if ( !v45[1] && v44[3] )
    {
      updated = -2147024809;
      goto LABEL_56;
    }
    if ( v44[3] > 0x10000 )
    {
      updated = -2147024809;
      goto LABEL_56;
    }
    updated = CJetContext::SetBinaryColumn(v8, 9u, v45[1], v44[3]);
    if ( updated < 0 )
      goto LABEL_56;
    v10 = (int)v46[0];
    if ( !v46[0] && LODWORD(v45[0]) )
    {
      updated = -2147024809;
      goto LABEL_56;
    }
    if ( LODWORD(v45[0]) > 0x10000 )
    {
      updated = -2147024809;
      goto LABEL_56;
    }
    updated = CJetContext::SetBinaryColumn(v8, 0xAu, v46[0], (unsigned int)v45[0]);
    if ( updated < 0 )
      goto LABEL_56;
  }
  v26 = JetUpdate(*((_QWORD *)v8 + 2), *((_QWORD *)v8 + 4), 0, 0, 0);
  updated = HRESULTFromJET_ERR(v26, 1);
  if ( updated < 0 )
  {
LABEL_56:
    v13 = v9;
    goto LABEL_5;
  }
  v13 = 0;
  v30 = JetCommitTransaction(*((_QWORD *)v8 + 2), 1u);
  updated = HRESULTFromJET_ERR(v30, 1);
  if ( updated >= 0 )
    v9 = 0;
LABEL_5:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_ISD(v11, 39, v10, *((_QWORD *)this + 3), (__int64)v5, updated);
  if ( v13 )
    JetPrepareUpdate(*((_QWORD *)v8 + 2), *((_QWORD *)v8 + 4), 3u);
  if ( v9 )
    JetRollback(*((_QWORD *)v8 + 2), 0);
  v14 = *(_QWORD *)(*((_QWORD *)this + 5) + 152LL);
  if ( v8 )
  {
    CCacheStore::EndActivity(*(CCacheStore **)(v14 + 80));
    v25 = 0;
    *((_QWORD *)v8 + 1) = 0;
    if ( v14 != -8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
      v25 = 1;
    }
    --*(_DWORD *)(v14 + 60);
    if ( (unsigned int)(*(_DWORD *)(v14 + 56) - *(_DWORD *)(v14 + 60)) > *(_DWORD *)(v14 + 64) )
    {
      --*(_DWORD *)(v14 + 56);
      CJetContext::Release(v8);
    }
    else
    {
      *((_QWORD *)v8 + 1) = *(_QWORD *)(v14 + 48);
      *(_QWORD *)(v14 + 48) = v8;
    }
    if ( v25 && v14 != -8 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
  }
  CInFlightLocks::ReleaseLock(*(CInFlightLocks **)(*((_QWORD *)this + 5) + 144LL), v41);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 40, &WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids, (unsigned int)updated);
  if ( v48 )
    WxFreeHeapEx(&v48);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180082cc0  mov     [rsp-8+arg_18], rbx
0x180082cc5  push    rbp
0x180082cc6  push    rsi
0x180082cc7  push    rdi
0x180082cc8  push    r12
0x180082cca  push    r13
0x180082ccc  push    r14
0x180082cce  push    r15
0x180082cd0  lea     rbp, [rsp-27h]
0x180082cd5  sub     rsp, 0E0h
0x180082cdc  mov     rax, cs:__security_cookie
0x180082ce3  xor     rax, rsp
0x180082ce6  mov     [rbp+57h+var_40], rax
0x180082cea  xor     ebx, ebx
0x180082cec  mov     [rbp+57h+var_C0], rdx
0x180082cf0  mov     r14, r8
0x180082cf3  mov     [rbp+57h+var_C4], ebx
0x180082cf6  mov     r15, rdx
0x180082cf9  mov     [rbp+57h+var_B8], rbx
0x180082cfd  mov     r13, rcx
0x180082d00  mov     [rbp+57h+var_D0], ebx
0x180082d03  lea     r8d, [rbx+50h]; Size
0x180082d07  mov     [rbp+57h+var_B0], rbx
0x180082d0b  xor     edx, edx; Val
0x180082d0d  mov     [rbp+57h+var_48], rbx
0x180082d11  lea     rcx, [rbp+57h+var_A0]; void *
0x180082d15  mov     [rbp+57h+var_50], ebx
0x180082d18  mov     esi, r9d
0x180082d1b  mov     edi, ebx
0x180082d1d  mov     r12d, ebx
0x180082d20  call    memset_0
0x180082d25  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180082d2c  jz      short loc_180082D53
0x180082d2e  mov     dword ptr [rsp+110h+psetinfo], esi
0x180082d32  lea     edx, [rbx+26h]
0x180082d35  mov     qword ptr [rsp+110h+grbit], r14
0x180082d3a  lea     r8, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids
0x180082d41  mov     ecx, 40Ch
0x180082d46  mov     [rsp+110h+pcbActual], r15
0x180082d4b  mov     r9, r13
0x180082d4e  call    WPP_SF_qSqd
0x180082d53  mov     ecx, [r13+20h]
0x180082d57  mov     [rbp+57h+var_C4], ebx
0x180082d5a  and     ecx, 2
0x180082d5d  jz      loc_1800832F5
0x180082d63  mov     eax, ecx
0x180082d65  neg     eax
0x180082d67  sbb     ebx, ebx
0x180082d69  not     ebx
0x180082d6b  and     ebx, 80070005h
0x180082d71  test    ecx, ecx
0x180082d73  jnz     loc_180082E37
0x180082d79  mov     [rbp+57h+var_C4], 62Bh
0x180082d80  mov     esi, edi
0x180082d82  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180082d89  jz      short loc_180082DA2
0x180082d8b  mov     r9, [r13+18h]
0x180082d8f  mov     edx, 27h ; '''
0x180082d94  mov     [rsp+110h+grbit], ebx
0x180082d98  mov     [rsp+110h+pcbActual], r15
0x180082d9d  call    WPP_SF_ISD
0x180082da2  test    esi, esi
0x180082da4  jnz     loc_18008350D
0x180082daa  test    r12d, r12d
0x180082dad  jz      short loc_180082DBB
0x180082daf  mov     rcx, [rdi+10h]; sesid
0x180082db3  xor     edx, edx; grbit
0x180082db5  call    cs:__imp_JetRollback
0x180082dbb  mov     rax, [r13+28h]
0x180082dbf  mov     rsi, [rax+98h]
0x180082dc6  test    rdi, rdi
0x180082dc9  jz      short loc_180082DDD
0x180082dcb  mov     rcx, [rsi+50h]; this
0x180082dcf  call    ?EndActivity@CCacheStore@@QEAAXXZ; CCacheStore::EndActivity(void)
0x180082dd4  test    rdi, rdi
0x180082dd7  jnz     loc_18008303C
0x180082ddd  mov     rcx, [r13+28h]
0x180082de1  lea     rdx, [rbp+57h+var_B0]; struct CInFlightEntry **
0x180082de5  mov     rcx, [rcx+90h]; this
0x180082dec  call    ?ReleaseLock@CInFlightLocks@@QEAAXPEAPEAVCInFlightEntry@@@Z; CInFlightLocks::ReleaseLock(CInFlightEntry * *)
0x180082df1  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180082df8  jnz     loc_18008309B
0x180082dfe  cmp     [rbp+57h+var_48], 0
0x180082e03  jz      short loc_180082E0E
0x180082e05  lea     rcx, [rbp+57h+var_48]
0x180082e09  call    WxFreeHeapEx
0x180082e0e  mov     eax, ebx
0x180082e10  mov     rcx, [rbp+57h+var_40]
0x180082e14  xor     rcx, rsp; StackCookie
0x180082e17  call    __security_check_cookie
0x180082e1c  mov     rbx, [rsp+110h+arg_18]
0x180082e24  add     rsp, 0E0h
0x180082e2b  pop     r15
0x180082e2d  pop     r14
0x180082e2f  pop     r13
0x180082e31  pop     r12
0x180082e33  pop     rdi
0x180082e34  pop     rsi
0x180082e35  pop     rbp
0x180082e36  retn
0x180082e37  mov     rcx, [r13+28h]; this
0x180082e3b  call    ?UpdateLastAccessTime@CContainerProps@@QEAAJXZ; CContainerProps::UpdateLastAccessTime(void)
0x180082e40  mov     ebx, eax
0x180082e42  test    eax, eax
0x180082e44  js      loc_1800832E9
0x180082e4a  mov     rcx, r15
0x180082e4d  call    WxComputeUrlHash
0x180082e52  mov     rcx, [r13+28h]
0x180082e56  lea     r8, [rbp+57h+var_B0]; struct CInFlightEntry **
0x180082e5a  mov     rdx, rax; unsigned __int64
0x180082e5d  mov     r15, rax
0x180082e60  mov     rcx, [rcx+90h]; this
0x180082e67  call    ?AcquireLock@CInFlightLocks@@QEAAJ_KPEAPEAVCInFlightEntry@@@Z; CInFlightLocks::AcquireLock(unsigned __int64,CInFlightEntry * *)
0x180082e6c  mov     ebx, eax
0x180082e6e  test    eax, eax
0x180082e70  js      loc_18008328F
0x180082e76  mov     rcx, [r13+28h]
0x180082e7a  lea     rdx, [rbp+57h+var_B8]; struct CJetContext **
0x180082e7e  xor     r8d, r8d; int *
0x180082e81  mov     rcx, [rcx+98h]; this
0x180082e88  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x180082e8d  mov     rdi, [rbp+57h+var_B8]
0x180082e91  mov     ebx, eax
0x180082e93  test    eax, eax
0x180082e95  js      loc_180083301
0x180082e9b  mov     dword ptr [rbp+57h+var_B8+4], r12d
0x180082e9f  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180082ea6  lea     rbx, aHashentryidind; "HashEntryIdIndex"
0x180082ead  jz      short loc_180082EC6
0x180082eaf  mov     dword ptr [rsp+110h+psetinfo], r12d
0x180082eb4  mov     r9, rdi
0x180082eb7  mov     qword ptr [rsp+110h+grbit], rbx
0x180082ebc  mov     dword ptr [rsp+110h+pcbActual], r12d
0x180082ec1  call    WPP_SF_qdSD
0x180082ec6  cmp     [rdi+30h], r12d
0x180082eca  jnz     loc_18008322D
0x180082ed0  xor     ebx, ebx
0x180082ed2  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180082ed9  jz      short loc_180082EF4
0x180082edb  mov     edx, 0Eh
0x180082ee0  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x180082ee7  mov     ecx, 40Ch
0x180082eec  mov     r9d, ebx
0x180082eef  call    WPP_SF_d
0x180082ef4  test    ebx, ebx
0x180082ef6  js      loc_180083311
0x180082efc  mov     rcx, [rdi+10h]; sesid
0x180082f00  call    cs:__imp_JetBeginTransaction
0x180082f06  mov     ecx, eax; int
0x180082f08  mov     edx, 1; int
0x180082f0d  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180082f12  mov     ebx, eax
0x180082f14  test    eax, eax
0x180082f16  js      loc_180083308
0x180082f1c  mov     r8, r15; unsigned __int64
0x180082f1f  mov     rcx, rdi; struct CJetContext *
0x180082f22  mov     r15, [rbp+57h+var_C0]
0x180082f26  mov     r12d, 1
0x180082f2c  mov     rdx, r15; unsigned __int16 *
0x180082f2f  call    ?SeekToEntry@@YAJPEAVCJetContext@@PEBG_K@Z; SeekToEntry(CJetContext *,ushort const *,unsigned __int64)
0x180082f34  mov     ebx, eax
0x180082f36  test    eax, eax
0x180082f38  js      loc_18008331A
0x180082f3e  jnz     loc_180083181
0x180082f44  mov     rdx, [rdi+20h]; tableid
0x180082f48  lea     r8d, [r12+1]; prep
0x180082f4d  mov     rcx, [rdi+10h]; sesid
0x180082f51  call    cs:__imp_JetPrepareUpdate
0x180082f57  mov     ecx, eax; int
0x180082f59  mov     edx, r12d; int
0x180082f5c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180082f61  mov     ebx, eax
0x180082f63  test    eax, eax
0x180082f65  js      loc_18008318D
0x180082f6b  movups  xmm0, xmmword ptr [r14]
0x180082f6f  movups  xmm1, xmmword ptr [r14+10h]
0x180082f74  movaps  [rbp+57h+var_A0], xmm0
0x180082f78  movaps  [rbp+57h+pvData], xmm1
0x180082f7c  movups  xmm0, xmmword ptr [r14+20h]
0x180082f81  movups  xmm1, xmmword ptr [r14+30h]
0x180082f86  movaps  xmmword ptr [rbp+57h+var_80], xmm0
0x180082f8a  movaps  xmmword ptr [rbp+57h+var_70], xmm1
0x180082f8e  movups  xmm0, xmmword ptr [r14+40h]
0x180082f93  lea     r14d, [r12+3]
0x180082f98  movaps  xmmword ptr [rbp+57h+var_60], xmm0
0x180082f9c  test    sil, 40h
0x180082fa0  jnz     loc_180083326
0x180082fa6  test    r12b, sil
0x180082fa9  jnz     loc_1800831E3
0x180082faf  test    sil, 2
0x180082fb3  jnz     loc_18008342D
0x180082fb9  mov     r14d, 8
0x180082fbf  test    sil, 4
0x180082fc3  jnz     loc_180083457
0x180082fc9  test    r14b, sil
0x180082fcc  jnz     loc_18008329F
0x180082fd2  test    sil, 10h
0x180082fd6  jnz     loc_180083123
0x180082fdc  test    sil, 20h
0x180082fe0  jnz     loc_180083481
0x180082fe6  mov     r14d, 10000h
0x180082fec  test    sil, sil
0x180082fef  js      loc_1800831A6
0x180082ff5  bt      esi, 8
0x180082ff9  jnb     loc_1800830EA
0x180082fff  mov     r8, [rbp+57h+var_70+8]; unsigned __int8 *
0x180083003  mov     r9d, [rbp+57h+var_80+0Ch]; unsigned int
0x180083007  test    r8, r8
0x18008300a  jz      loc_18008316A
0x180083010  cmp     r9d, r14d
0x180083013  ja      loc_180083195
0x180083019  mov     edx, 9; unsigned int
0x18008301e  mov     rcx, rdi; this
0x180083021  call    ?SetBinaryColumn@CJetContext@@QEAAJKPEBEK@Z; CJetContext::SetBinaryColumn(ulong,uchar const *,ulong)
0x180083026  mov     ebx, eax
0x180083028  test    eax, eax
0x18008302a  jns     loc_1800830B9
0x180083030  mov     [rbp+57h+var_C4], 6B8h
0x180083037  jmp     loc_18008311B
0x18008303c  xor     r15d, r15d
0x18008303f  lea     r14, [rsi+8]
0x180083043  mov     [rdi+8], r15
0x180083047  test    r14, r14
0x18008304a  jz      short loc_18008305B
0x18008304c  mov     rcx, r14; lpCriticalSection
0x18008304f  call    cs:__imp_EnterCriticalSection
0x180083055  mov     r15d, 1
0x18008305b  dec     dword ptr [rsi+3Ch]
0x18008305e  mov     ecx, [rsi+38h]
0x180083061  mov     eax, ecx
0x180083063  sub     eax, [rsi+3Ch]
0x180083066  cmp     eax, [rsi+40h]
0x180083069  ja      loc_180083526
0x18008306f  mov     rax, [rsi+30h]
0x180083073  mov     [rdi+8], rax
0x180083077  mov     [rsi+30h], rdi
0x18008307b  test    r15d, r15d
0x18008307e  jz      loc_180082DDD
0x180083084  test    r14, r14
0x180083087  jz      loc_180082DDD
0x18008308d  mov     rcx, r14; lpCriticalSection
0x180083090  call    cs:__imp_LeaveCriticalSection
0x180083096  jmp     loc_180082DDD
0x18008309b  mov     edx, 28h ; '('
0x1800830a0  lea     r8, WPP_dccf7cf37a8b34e1524f9624998e38f4_Traceguids
0x1800830a7  mov     ecx, 40Ch
0x1800830ac  mov     r9d, ebx
0x1800830af  call    WPP_SF_d
0x1800830b4  jmp     loc_180082DFE
0x1800830b9  mov     r8, [rbp+57h+var_60]; unsigned __int8 *
0x1800830bd  mov     r9d, dword ptr [rbp+57h+var_70]; unsigned int
0x1800830c1  test    r8, r8
0x1800830c4  jz      loc_1800834D6
0x1800830ca  cmp     r9d, r14d
0x1800830cd  ja      loc_1800834F0
0x1800830d3  mov     edx, 0Ah; unsigned int
0x1800830d8  mov     rcx, rdi; this
0x1800830db  call    ?SetBinaryColumn@CJetContext@@QEAAJKPEBEK@Z; CJetContext::SetBinaryColumn(ulong,uchar const *,ulong)
0x1800830e0  mov     ebx, eax
0x1800830e2  test    eax, eax
0x1800830e4  js      loc_180083501
0x1800830ea  mov     rdx, [rdi+20h]; tableid
0x1800830ee  xor     r9d, r9d; cbBookmark
0x1800830f1  mov     rcx, [rdi+10h]; sesid
0x1800830f5  xor     r8d, r8d; pvBookmark
0x1800830f8  mov     [rsp+110h+pcbActual], 0; pcbActual
0x180083101  call    cs:__imp_JetUpdate
0x180083107  mov     ecx, eax; int
0x180083109  mov     edx, r12d; int
0x18008310c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180083111  mov     ebx, eax
0x180083113  test    eax, eax
0x180083115  jns     loc_180083267
0x18008311b  mov     esi, r12d
0x18008311e  jmp     loc_180082D82
0x180083123  mov     rax, [rdi+28h]
0x180083127  lea     r9, [rbp+57h+pvData+8]; pvData
0x18008312b  mov     rdx, [rdi+20h]; tableid
0x18008312f  mov     rcx, [rdi+10h]; sesid
0x180083133  mov     [rsp+110h+psetinfo], 0; psetinfo
0x18008313c  mov     r8, [rax+8]
0x180083140  mov     [rsp+110h+grbit], 0; grbit
0x180083148  mov     dword ptr [rsp+110h+pcbActual], r14d; cbData
0x18008314d  mov     r8d, [r8+44h]; columnid
0x180083151  call    cs:__imp_JetSetColumn
0x180083157  mov     ebx, eax
0x180083159  test    eax, eax
0x18008315b  jns     loc_180082FDC
0x180083161  mov     [rbp+57h+var_C4], 6A4h
0x180083168  jmp     short loc_18008311B
0x18008316a  test    r9d, r9d
0x18008316d  jz      loc_180083010
0x180083173  mov     ebx, 80070057h
0x180083178  mov     [rbp+57h+var_C4], 6B5h
0x18008317f  jmp     short loc_18008311B
0x180083181  mov     ebx, 80070002h
0x180083186  mov     [rbp+57h+var_C4], 648h
0x18008318d  mov     esi, [rbp+57h+var_D0]
0x180083190  jmp     loc_180082D82
0x180083195  mov     ebx, 80070057h
  ... truncated ...
```
