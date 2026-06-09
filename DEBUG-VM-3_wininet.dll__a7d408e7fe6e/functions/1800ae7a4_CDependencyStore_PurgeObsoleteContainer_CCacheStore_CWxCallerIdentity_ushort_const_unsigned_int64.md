# CDependencyStore::PurgeObsoleteContainer(CCacheStore *,CWxCallerIdentity *,ushort const *,unsigned __int64)

- ea: `0x1800ae7a4`
- end: `0x1800aea6a`
- name: `?PurgeObsoleteContainer@CDependencyStore@@AEAAJPEAVCCacheStore@@PEAVCWxCallerIdentity@@PEBG_K@Z`
- size: `710`
- prototype: `int(CDependencyStore *__hidden this, struct CCacheStore *, struct CWxCallerIdentity *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800acf80`

## callees

- `0x18001f3a4`
- `0x1800204f8`
- `0x180021360`
- `0x180025910`
- `0x18007ec9c`
- `0x18007ee10`
- `0x1800861f8`
- `0x1800aca44`
- `0x1800ae7a4`
- `0x1800aeb88`
- `0x1800af96c`
- `0x1800e28e0`
- `0x18012be98`
- `0x1801e1790`
- `0x1801e4418`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ae8bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ae8bb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ae8f0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ae8f0`
- `ESENT!JetDeleteTableW` at `0x1800aea07`
- `ESENT!JetDeleteTableW` at `0x1800aea07`
- `ESENT!JetDelete` at `0x1800aea2b`
- `ESENT!JetDelete` at `0x1800aea2b`
- `ESENT!JetCommitTransaction` at `0x1800aea4a`
- `ESENT!JetCommitTransaction` at `0x1800aea4a`
- `ESENT!JetRollback` at `0x1800ae9c7`
- `ESENT!JetRollback` at `0x1800ae9c7`
- `ESENT!JetBeginTransaction` at `0x1800ae98b`
- `ESENT!JetBeginTransaction` at `0x1800ae98b`

## pseudocode

```c
__int64 __fastcall CDependencyStore::PurgeObsoleteContainer(
        CDependencyStore *this,
        CJetContextList **a2,
        struct CWxCallerIdentity *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  int v9; // ebx
  unsigned int v10; // edi
  int v11; // eax
  DWORD FileAttributesW; // eax
  unsigned int v14; // r9d
  struct CJetContext *v15; // rsi
  JET_ERR v16; // eax
  int v17; // eax
  JET_ERR v18; // eax
  JET_ERR v19; // eax
  JET_ERR v20; // eax
  unsigned __int16 *v21; // [rsp+20h] [rbp-71h]
  unsigned __int16 *v22; // [rsp+28h] [rbp-69h]
  unsigned __int16 *v23; // [rsp+30h] [rbp-61h]
  unsigned __int16 *v24; // [rsp+38h] [rbp-59h]
  const unsigned __int16 *v25; // [rsp+40h] [rbp-51h]
  const unsigned __int16 *v26; // [rsp+48h] [rbp-49h]
  const unsigned __int16 *v27; // [rsp+50h] [rbp-41h]
  struct CJetContext *v28; // [rsp+68h] [rbp-29h] BYREF
  CDependencyContainer *v29; // [rsp+70h] [rbp-21h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+78h] [rbp-19h] BYREF
  __int64 v31; // [rsp+80h] [rbp-11h]
  JET_PCWSTR szTableName[2]; // [rsp+88h] [rbp-9h] BYREF
  LPCWSTR lpFileName[9]; // [rsp+98h] [rbp+7h] BYREF

  lpFileName[1] = 0;
  lpFileName[0] = &Data;
  v28 = 0;
  v29 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 24);
  v31 = 0;
  szTableName[0] = &Data;
  szTableName[1] = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qqqSi(
      (unsigned int)&Data,
      (_DWORD)a2,
      (_DWORD)a3,
      (_DWORD)this,
      (__int64)a2,
      (__int64)a3,
      (__int64)a4,
      (char)a5);
  if ( (unsigned int)CCacheStore::IsTerminating((CCacheStore *)a2) )
    goto LABEL_4;
  v11 = CWxString::SetPath((CWxString *)lpFileName, a4, L"container.dat", 0, v21, v22, v23, v24, v25, v26, v27);
  v9 = v11;
  if ( v11 < 0 )
    goto LABEL_6;
  FileAttributesW = GetFileAttributesW(lpFileName[0]);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x10) == 0 )
    goto LABEL_4;
  AutoCritSec::Lock((AutoCritSec *)&lpCriticalSection);
  *(_QWORD *)(*((_QWORD *)this + 1) + 8LL) = a5;
  v11 = CWxRefMap<CDependencyContainerMap,CDependencyContainer>::Find(
          *((_QWORD *)this + 2),
          *((_QWORD *)this + 1),
          &v29);
  v9 = v11;
  if ( v11 < 0 )
  {
LABEL_6:
    v10 = v11;
    goto LABEL_7;
  }
  if ( !v11 )
  {
LABEL_4:
    v9 = 0;
    v10 = 0;
    goto LABEL_7;
  }
  v11 = CCacheStore::AcquirePartitionContext((CCacheStore *)a2, &v28);
  v9 = v11;
  if ( v11 < 0 )
    goto LABEL_6;
  v15 = v28;
  v11 = CJetContext::SetCurrentIndex(v28, 1u, L"PartitionIndex", v14);
  v9 = v11;
  if ( v11 < 0 )
    goto LABEL_6;
  v16 = JetBeginTransaction(*((_QWORD *)v15 + 2));
  v11 = HRESULTFromJET_ERR(v16, 1);
  v9 = v11;
  if ( v11 < 0 )
    goto LABEL_6;
  v17 = CCacheStore::SeekToPartition(v15, a3, 1);
  v9 = v17;
  if ( v17 < 0 )
    goto LABEL_23;
  if ( v17 )
  {
    v9 = 0;
    v10 = 0;
    goto LABEL_24;
  }
  v17 = CWxString::Format((CWxString *)szTableName, L"DependencyEntryEx_%I64u", a5);
  v9 = v17;
  if ( v17 < 0 )
    goto LABEL_23;
  v18 = JetDeleteTableW(*((_QWORD *)v15 + 2), *((_DWORD *)v15 + 6), szTableName[0]);
  if ( v18 != -1305 )
  {
    v17 = HRESULTFromJET_ERR(v18, 1);
    v9 = v17;
    if ( v17 < 0 )
      goto LABEL_23;
  }
  v19 = JetDelete(*((_QWORD *)v15 + 2), *((_QWORD *)v15 + 4));
  v17 = HRESULTFromJET_ERR(v19, 1);
  v9 = v17;
  if ( v17 < 0 )
  {
LABEL_23:
    v10 = v17;
LABEL_24:
    JetRollback(*((_QWORD *)v15 + 2), 0);
    goto LABEL_7;
  }
  v20 = JetCommitTransaction(*((_QWORD *)v15 + 2), 1u);
  v9 = HRESULTFromJET_ERR(v20, 1);
  v10 = v9;
  if ( v9 < 0 )
    goto LABEL_24;
LABEL_7:
  CJetContextList::ReleaseContext(a2[55], &v28);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 13, &WPP_28c37ca9899f33ac28da9a29870553e3_Traceguids, (unsigned int)v9);
  CWxString::_Release((CWxString *)szTableName);
  if ( (_DWORD)v31 && lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  if ( v29 )
    CDependencyContainer::Release(v29);
  CWxString::_Release((CWxString *)lpFileName);
  return v10;
}

```

## disassembly

```asm
0x1800ae7a4  push    rbp
0x1800ae7a6  push    rbx
0x1800ae7a7  push    rsi
0x1800ae7a8  push    rdi
0x1800ae7a9  push    r12
0x1800ae7ab  push    r14
0x1800ae7ad  push    r15
0x1800ae7af  lea     rbp, [rsp-1Fh]
0x1800ae7b4  sub     rsp, 0B0h
0x1800ae7bb  mov     rdi, rcx
0x1800ae7be  mov     [rbp+4Fh+var_7C], 0
0x1800ae7c5  lea     rcx, Data
0x1800ae7cc  mov     [rbp+4Fh+var_40], 0
0x1800ae7d4  mov     rbx, r9
0x1800ae7d7  mov     [rbp+4Fh+lpFileName], rcx
0x1800ae7db  mov     r12, r8
0x1800ae7de  mov     [rbp+4Fh+var_78], 0
0x1800ae7e6  lea     rax, [rdi+18h]
0x1800ae7ea  mov     [rbp+4Fh+var_70], 0
0x1800ae7f2  mov     [rbp+4Fh+lpCriticalSection], rax
0x1800ae7f6  mov     r14, rdx
0x1800ae7f9  mov     [rbp+4Fh+var_60], 0
0x1800ae801  mov     [rbp+4Fh+szTableName], rcx
0x1800ae805  mov     [rbp+4Fh+var_50], 0
0x1800ae80d  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ae814  mov     r15, [rbp+4Fh+arg_20]
0x1800ae818  jz      short loc_1800AE836
0x1800ae81a  mov     [rsp+0E0h+var_A8], r15; unsigned __int16 *
0x1800ae81f  mov     r9, rdi
0x1800ae822  mov     [rsp+0E0h+var_B0], rbx; unsigned __int16 *
0x1800ae827  mov     [rsp+0E0h+var_B8], r8; unsigned __int16 *
0x1800ae82c  mov     [rsp+0E0h+var_C0], rdx; unsigned __int16 *
0x1800ae831  call    WPP_SF_qqqSi
0x1800ae836  mov     rcx, r14; this
0x1800ae839  call    ?IsTerminating@CCacheStore@@QEAAHXZ; CCacheStore::IsTerminating(void)
0x1800ae83e  test    eax, eax
0x1800ae840  jz      short loc_1800AE848
0x1800ae842  xor     ebx, ebx
0x1800ae844  xor     edi, edi
0x1800ae846  jmp     short loc_1800AE871
0x1800ae848  xor     r9d, r9d; unsigned __int16 *
0x1800ae84b  lea     r8, ?c_wszContainerCanaryFile@@3QBGB; "container.dat"
0x1800ae852  mov     rdx, rbx; unsigned __int16 *
0x1800ae855  lea     rcx, [rbp+4Fh+lpFileName]; this
0x1800ae859  call    ?SetPath@CWxString@@QEAAJPEBG000000000@Z; CWxString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800ae85e  mov     ebx, eax
0x1800ae860  test    eax, eax
0x1800ae862  jns     loc_1800AE8EC
0x1800ae868  mov     [rbp+4Fh+var_7C], 52h ; 'R'
0x1800ae86f  mov     edi, eax
0x1800ae871  mov     rcx, [r14+1B8h]; this
0x1800ae878  lea     rdx, [rbp+4Fh+var_78]; struct CJetContext **
0x1800ae87c  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x1800ae881  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ae888  jz      short loc_1800AE8A3
0x1800ae88a  mov     edx, 0Dh
0x1800ae88f  lea     r8, WPP_28c37ca9899f33ac28da9a29870553e3_Traceguids
0x1800ae896  mov     ecx, 40Ch
0x1800ae89b  mov     r9d, ebx
0x1800ae89e  call    WPP_SF_d
0x1800ae8a3  lea     rcx, [rbp+4Fh+szTableName]; this
0x1800ae8a7  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800ae8ac  cmp     dword ptr [rbp+4Fh+var_60], 0
0x1800ae8b0  jz      short loc_1800AE8C1
0x1800ae8b2  mov     rcx, [rbp+4Fh+lpCriticalSection]; lpCriticalSection
0x1800ae8b6  test    rcx, rcx
0x1800ae8b9  jz      short loc_1800AE8C1
0x1800ae8bb  call    cs:__imp_LeaveCriticalSection
0x1800ae8c1  mov     rcx, [rbp+4Fh+var_70]; this
0x1800ae8c5  test    rcx, rcx
0x1800ae8c8  jz      short loc_1800AE8CF
0x1800ae8ca  call    ?Release@CDependencyContainer@@QEAAKXZ; CDependencyContainer::Release(void)
0x1800ae8cf  lea     rcx, [rbp+4Fh+lpFileName]; this
0x1800ae8d3  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800ae8d8  mov     eax, edi
0x1800ae8da  add     rsp, 0B0h
0x1800ae8e1  pop     r15
0x1800ae8e3  pop     r14
0x1800ae8e5  pop     r12
0x1800ae8e7  pop     rdi
0x1800ae8e8  pop     rsi
0x1800ae8e9  pop     rbx
0x1800ae8ea  pop     rbp
0x1800ae8eb  retn
0x1800ae8ec  mov     rcx, [rbp+4Fh+lpFileName]; lpFileName
0x1800ae8f0  call    cs:__imp_GetFileAttributesW
0x1800ae8f6  cmp     eax, 0FFFFFFFFh
0x1800ae8f9  jz      short loc_1800AE903
0x1800ae8fb  test    al, 10h
0x1800ae8fd  jz      loc_1800AE842
0x1800ae903  lea     rcx, [rbp+4Fh+lpCriticalSection]; this
0x1800ae907  call    ?Lock@AutoCritSec@@QEAAXXZ; AutoCritSec::Lock(void)
0x1800ae90c  mov     rax, [rdi+8]
0x1800ae910  lea     r8, [rbp+4Fh+var_70]
0x1800ae914  mov     [rax+8], r15
0x1800ae918  mov     rdx, [rdi+8]
0x1800ae91c  mov     rcx, [rdi+10h]
0x1800ae920  call    ?Find@?$CWxRefMap@VCDependencyContainerMap@@VCDependencyContainer@@@@QEAAJPEAVCDependencyContainer@@PEAPEAV2@@Z; CWxRefMap<CDependencyContainerMap,CDependencyContainer>::Find(CDependencyContainer *,CDependencyContainer * *)
0x1800ae925  mov     ebx, eax
0x1800ae927  test    eax, eax
0x1800ae929  jns     short loc_1800AE937
0x1800ae92b  mov     [rbp+4Fh+var_7C], 63h ; 'c'
0x1800ae932  jmp     loc_1800AE86F
0x1800ae937  jz      loc_1800AE842
0x1800ae93d  lea     rdx, [rbp+4Fh+var_78]; struct CJetContext **
0x1800ae941  mov     rcx, r14; this
0x1800ae944  call    ?AcquirePartitionContext@CCacheStore@@QEAAJPEAPEAVCJetContext@@@Z; CCacheStore::AcquirePartitionContext(CJetContext * *)
0x1800ae949  mov     ebx, eax
0x1800ae94b  test    eax, eax
0x1800ae94d  jns     short loc_1800AE95B
0x1800ae94f  mov     [rbp+4Fh+var_7C], 6Eh ; 'n'
0x1800ae956  jmp     loc_1800AE86F
0x1800ae95b  mov     rsi, [rbp+4Fh+var_78]
0x1800ae95f  lea     r8, szIndexName; "PartitionIndex"
0x1800ae966  mov     edi, 1
0x1800ae96b  mov     rcx, rsi; this
0x1800ae96e  mov     edx, edi; unsigned int
0x1800ae970  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1800ae975  mov     ebx, eax
0x1800ae977  test    eax, eax
0x1800ae979  jns     short loc_1800AE987
0x1800ae97b  mov     [rbp+4Fh+var_7C], 71h ; 'q'
0x1800ae982  jmp     loc_1800AE86F
0x1800ae987  mov     rcx, [rsi+10h]; sesid
0x1800ae98b  call    cs:__imp_JetBeginTransaction
0x1800ae991  mov     ecx, eax; int
0x1800ae993  mov     edx, edi; int
0x1800ae995  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ae99a  mov     ebx, eax
0x1800ae99c  test    eax, eax
0x1800ae99e  js      loc_1800AE86F
0x1800ae9a4  mov     r8d, edi
0x1800ae9a7  mov     rdx, r12
0x1800ae9aa  mov     rcx, rsi
0x1800ae9ad  call    ?SeekToPartition@CCacheStore@@SAJPEAVCJetContext@@PEAVCWxCallerIdentity@@W4PartitionType@@@Z; CCacheStore::SeekToPartition(CJetContext *,CWxCallerIdentity *,PartitionType)
0x1800ae9b2  mov     ebx, eax
0x1800ae9b4  test    eax, eax
0x1800ae9b6  jns     short loc_1800AE9D2
0x1800ae9b8  mov     [rbp+4Fh+var_7C], 78h ; 'x'
0x1800ae9bf  mov     edi, eax
0x1800ae9c1  mov     rcx, [rsi+10h]; sesid
0x1800ae9c5  xor     edx, edx; grbit
0x1800ae9c7  call    cs:__imp_JetRollback
0x1800ae9cd  jmp     loc_1800AE871
0x1800ae9d2  jz      short loc_1800AE9DA
0x1800ae9d4  xor     ebx, ebx
0x1800ae9d6  xor     edi, edi
0x1800ae9d8  jmp     short loc_1800AE9C1
0x1800ae9da  mov     r8, r15
0x1800ae9dd  lea     rdx, ?c_wszDependencyEntryTable@@3QBGB; "DependencyEntryEx_%I64u"
0x1800ae9e4  lea     rcx, [rbp+4Fh+szTableName]; this
0x1800ae9e8  call    ?Format@CWxString@@QEAAJPEBGZZ; CWxString::Format(ushort const *,...)
0x1800ae9ed  mov     ebx, eax
0x1800ae9ef  test    eax, eax
0x1800ae9f1  jns     short loc_1800AE9FC
0x1800ae9f3  mov     [rbp+4Fh+var_7C], 83h
0x1800ae9fa  jmp     short loc_1800AE9BF
0x1800ae9fc  mov     r8, [rbp+4Fh+szTableName]; szTableName
0x1800aea00  mov     edx, [rsi+18h]; dbid
0x1800aea03  mov     rcx, [rsi+10h]; sesid
0x1800aea07  call    cs:__imp_JetDeleteTableW
0x1800aea0d  cmp     eax, 0FFFFFAE7h
0x1800aea12  jz      short loc_1800AEA23
0x1800aea14  mov     edx, edi; int
0x1800aea16  mov     ecx, eax; int
0x1800aea18  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800aea1d  mov     ebx, eax
0x1800aea1f  test    eax, eax
0x1800aea21  js      short loc_1800AE9BF
0x1800aea23  mov     rdx, [rsi+20h]; tableid
0x1800aea27  mov     rcx, [rsi+10h]; sesid
0x1800aea2b  call    cs:__imp_JetDelete
0x1800aea31  mov     ecx, eax; int
0x1800aea33  mov     edx, edi; int
0x1800aea35  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800aea3a  mov     ebx, eax
0x1800aea3c  test    eax, eax
0x1800aea3e  js      loc_1800AE9BF
0x1800aea44  mov     rcx, [rsi+10h]; sesid
0x1800aea48  mov     edx, edi; grbit
0x1800aea4a  call    cs:__imp_JetCommitTransaction
0x1800aea50  mov     ecx, eax; int
0x1800aea52  mov     edx, edi; int
0x1800aea54  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800aea59  mov     ebx, eax
0x1800aea5b  mov     edi, eax
0x1800aea5d  test    eax, eax
0x1800aea5f  js      loc_1800AE9C1
0x1800aea65  jmp     loc_1800AE871
```
