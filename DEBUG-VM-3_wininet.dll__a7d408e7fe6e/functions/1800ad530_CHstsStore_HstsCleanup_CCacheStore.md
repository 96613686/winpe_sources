# CHstsStore::HstsCleanup(CCacheStore *)

- ea: `0x1800ad530`
- end: `0x1800ad8d8`
- name: `?HstsCleanup@CHstsStore@@QEAAJPEAVCCacheStore@@@Z`
- size: `936`
- prototype: `int(CHstsStore *__hidden this, struct CCacheStore *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800aea70`

## callees

- `0x180021360`
- `0x180025910`
- `0x180043cdc`
- `0x18007ec9c`
- `0x18007ed10`
- `0x180083dc4`
- `0x1800861f8`
- `0x1800aca44`
- `0x1800acab8`
- `0x1800ad530`
- `0x1800ade24`
- `0x1800af3d0`
- `0x18014a7a0`
- `0x1801aefa8`
- `0x1801e1790`
- `0x1801e2f30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ad746`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ad746`
- `ESENT!JetMakeKey` at `0x1800ad655`
- `ESENT!JetMakeKey` at `0x1800ad655`
- `ESENT!JetRollback` at `0x1800ad853`
- `ESENT!JetRollback` at `0x1800ad853`
- `ESENT!JetBeginTransaction` at `0x1800ad620`
- `ESENT!JetBeginTransaction` at `0x1800ad620`
- `ESENT!JetMove` at `0x1800ad7f4`
- `ESENT!JetMove` at `0x1800ad7f4`
- `ESENT!JetSeek` at `0x1800ad67b`
- `ESENT!JetSeek` at `0x1800ad67b`

## pseudocode

```c
__int64 __fastcall CHstsStore::HstsCleanup(CHstsStore *this, CJetContextList **a2)
{
  CWxCallerIdentity *v4; // rbx
  int BasicColumn; // edi
  int v6; // eax
  unsigned int v7; // r9d
  JET_SESID *v8; // rsi
  JET_ERR v9; // eax
  JET_ERR Key; // eax
  JET_ERR i; // eax
  CWxCallerIdentity *v12; // rax
  struct CJetContext *v14; // [rsp+30h] [rbp-50h] BYREF
  int v15; // [rsp+38h] [rbp-48h] BYREF
  int v16; // [rsp+3Ch] [rbp-44h]
  unsigned __int16 *v17; // [rsp+40h] [rbp-40h] BYREF
  __int64 v18; // [rsp+48h] [rbp-38h]
  int pvData; // [rsp+50h] [rbp-30h] BYREF
  __int64 v20; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v21; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int16 *v22[2]; // [rsp+68h] [rbp-18h] BYREF

  v16 = 0;
  v14 = 0;
  v17 = (unsigned __int16 *)&Data;
  v4 = 0;
  v18 = 0;
  pvData = 2;
  v22[0] = (unsigned __int16 *)&Data;
  v22[1] = 0;
  v21 = 0;
  v20 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qq(1036, 24, (unsigned int)&WPP_9d52da5ef3ad3c382853cb62ff3dbf62_Traceguids, (_DWORD)this, (__int64)a2);
  if ( (unsigned int)CCacheStore::IsTerminating((CCacheStore *)a2) )
  {
    BasicColumn = 0;
  }
  else
  {
    v6 = CJetContextList::AcquireContext(a2[55], &v14, 0);
    v8 = (JET_SESID *)v14;
    BasicColumn = v6;
    if ( v6 >= 0 )
    {
      BasicColumn = CJetContext::SetCurrentIndex(v14, 2u, L"PartitionTypeIndex", v7);
      if ( BasicColumn >= 0 )
      {
        v9 = JetBeginTransaction(v8[2]);
        BasicColumn = HRESULTFromJET_ERR(v9, 1);
        if ( BasicColumn >= 0 )
        {
          Key = JetMakeKey(v8[2], v8[4], &pvData, 4u, 1u);
          BasicColumn = HRESULTFromJET_ERR(Key, 1);
          if ( BasicColumn >= 0 )
          {
            for ( i = JetSeek(v8[2], v8[4], 0x21u); i != -1603; i = JetMove(v8[2], v8[4], 1, 0) )
            {
              BasicColumn = HRESULTFromJET_ERR(i, 1);
              if ( BasicColumn < 0 )
                break;
              if ( (_DWORD)v18 )
              {
                LODWORD(v18) = 0;
                *v17 = 0;
              }
              v20 = 0;
              v15 = 0;
              BasicColumn = CJetContext::GetBasicColumn((CJetContext *)v8, 0, &v21, 8u);
              if ( BasicColumn < 0 )
              {
                v16 = 522;
                break;
              }
              BasicColumn = CJetContext::GetStringColumn((CJetContext *)v8, 4u, (struct CWxString *)&v17);
              if ( BasicColumn < 0 )
              {
                v16 = 524;
                break;
              }
              BasicColumn = CJetContext::GetBasicColumn((CJetContext *)v8, 5u, &v20, 8u);
              if ( BasicColumn < 0 )
              {
                v16 = 528;
                break;
              }
              BasicColumn = CJetContext::GetStringColumn((CJetContext *)v8, 1u, (struct CWxString *)v22);
              if ( BasicColumn < 0 )
              {
                v16 = 530;
                break;
              }
              if ( v4 )
                CWxCallerIdentity::Release(v4);
              v12 = (CWxCallerIdentity *)HeapAlloc(g_hWxProcessHeap, 0, 0x28u);
              v4 = v12;
              if ( !v12 )
              {
                v4 = 0;
                v16 = 538;
                BasicColumn = -2147024882;
                break;
              }
              *(_QWORD *)v12 = 1;
              *((_QWORD *)v12 + 1) = &Data;
              *((_QWORD *)v12 + 2) = 0;
              *((_QWORD *)v12 + 3) = 0;
              *((_QWORD *)v12 + 4) = 0;
              BasicColumn = CWxCallerIdentity::Initialize(v12, v22[0]);
              if ( BasicColumn < 0 )
              {
                v16 = 539;
                break;
              }
              if ( (_DWORD)v18 )
              {
                BasicColumn = CHstsStore::HstsDeleteObsoleteContainerAtCursorIfCanaryDeleted(
                                this,
                                (struct CCacheStore *)a2,
                                v21,
                                v4,
                                v17,
                                &v15);
                if ( BasicColumn < 0 )
                {
                  v16 = 551;
                  break;
                }
                if ( !v15 && v20 == -6048000000000LL )
                {
                  BasicColumn = CHstsStore::HstsPurgeExpiredEntriesInTable(this, a2, v21, v4);
                  if ( BasicColumn < 0 )
                  {
                    v16 = 568;
                    break;
                  }
                }
              }
            }
          }
          JetRollback(v8[2], 0);
        }
      }
      else
      {
        v16 = 489;
      }
    }
    else
    {
      v16 = 485;
    }
    if ( v8 )
      CJetContextList::ReleaseContext(a2[55], &v14);
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 25, &WPP_9d52da5ef3ad3c382853cb62ff3dbf62_Traceguids, (unsigned int)BasicColumn);
  if ( v4 )
    CWxCallerIdentity::Release(v4);
  CWxString::_Release((CWxString *)v22);
  CWxString::_Release((CWxString *)&v17);
  return (unsigned int)BasicColumn;
}

```

## disassembly

```asm
0x1800ad530  mov     [rsp-38h+arg_10], rbx
0x1800ad535  push    rbp
0x1800ad536  push    rsi
0x1800ad537  push    rdi
0x1800ad538  push    r12
0x1800ad53a  push    r13
0x1800ad53c  push    r14
0x1800ad53e  push    r15
0x1800ad540  mov     rbp, rsp
0x1800ad543  sub     rsp, 80h
0x1800ad54a  mov     rax, cs:__security_cookie
0x1800ad551  xor     rax, rsp
0x1800ad554  mov     [rbp+var_8], rax
0x1800ad558  xor     r12d, r12d
0x1800ad55b  lea     rax, Data
0x1800ad562  mov     r14, rdx
0x1800ad565  mov     [rbp+var_44], r12d
0x1800ad569  mov     r15, rcx
0x1800ad56c  mov     [rbp+var_50], r12
0x1800ad570  mov     [rbp+var_40], rax
0x1800ad574  mov     ebx, r12d
0x1800ad577  lea     r13d, [r12+2]
0x1800ad57c  mov     [rbp+var_38], r12
0x1800ad580  mov     [rbp+pvData], r13d
0x1800ad584  mov     [rbp+var_18], rax
0x1800ad588  mov     [rbp+var_10], r12
0x1800ad58c  mov     [rbp+var_20], r12
0x1800ad590  mov     [rbp+var_28], r12
0x1800ad594  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ad59b  jz      short loc_1800AD5BB
0x1800ad59d  lea     edx, [r12+18h]
0x1800ad5a2  mov     qword ptr [rsp+80h+grbit], r14
0x1800ad5a7  mov     ecx, 40Ch
0x1800ad5ac  lea     r8, WPP_9d52da5ef3ad3c382853cb62ff3dbf62_Traceguids
0x1800ad5b3  mov     r9, r15
0x1800ad5b6  call    WPP_SF_qq
0x1800ad5bb  mov     rcx, r14; this
0x1800ad5be  call    ?IsTerminating@CCacheStore@@QEAAHXZ; CCacheStore::IsTerminating(void)
0x1800ad5c3  test    eax, eax
0x1800ad5c5  jz      short loc_1800AD5CF
0x1800ad5c7  mov     edi, r12d
0x1800ad5ca  jmp     loc_1800AD86E
0x1800ad5cf  mov     rcx, [r14+1B8h]; this
0x1800ad5d6  lea     rdx, [rbp+var_50]; struct CJetContext **
0x1800ad5da  xor     r8d, r8d; int *
0x1800ad5dd  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1800ad5e2  mov     rsi, [rbp+var_50]
0x1800ad5e6  mov     edi, eax
0x1800ad5e8  test    eax, eax
0x1800ad5ea  jns     short loc_1800AD5F8
0x1800ad5ec  mov     [rbp+var_44], 1E5h
0x1800ad5f3  jmp     loc_1800AD859
0x1800ad5f8  lea     r8, aPartitiontypei; "PartitionTypeIndex"
0x1800ad5ff  mov     edx, r13d; unsigned int
0x1800ad602  mov     rcx, rsi; this
0x1800ad605  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1800ad60a  mov     edi, eax
0x1800ad60c  test    eax, eax
0x1800ad60e  jns     short loc_1800AD61C
0x1800ad610  mov     [rbp+var_44], 1E9h
0x1800ad617  jmp     loc_1800AD859
0x1800ad61c  mov     rcx, [rsi+10h]; sesid
0x1800ad620  call    cs:__imp_JetBeginTransaction
0x1800ad626  mov     r13d, 1
0x1800ad62c  mov     ecx, eax; int
0x1800ad62e  mov     edx, r13d; int
0x1800ad631  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ad636  mov     edi, eax
0x1800ad638  test    eax, eax
0x1800ad63a  js      loc_1800AD859
0x1800ad640  mov     rdx, [rsi+20h]; tableid
0x1800ad644  lea     r9d, [r13+3]; cbData
0x1800ad648  mov     rcx, [rsi+10h]; sesid
0x1800ad64c  lea     r8, [rbp+pvData]; pvData
0x1800ad650  mov     [rsp+80h+grbit], r13d; grbit
0x1800ad655  call    cs:__imp_JetMakeKey
0x1800ad65b  mov     ecx, eax; int
0x1800ad65d  mov     edx, r13d; int
0x1800ad660  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ad665  mov     edi, eax
0x1800ad667  test    eax, eax
0x1800ad669  js      loc_1800AD84D
0x1800ad66f  mov     rdx, [rsi+20h]; tableid
0x1800ad673  lea     r8d, [r13+20h]; grbit
0x1800ad677  mov     rcx, [rsi+10h]; sesid
0x1800ad67b  call    cs:__imp_JetSeek
0x1800ad681  cmp     eax, 0FFFFF9BDh
0x1800ad686  jz      loc_1800AD84D
0x1800ad68c  mov     edx, r13d; int
0x1800ad68f  mov     ecx, eax; int
0x1800ad691  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ad696  mov     edi, eax
0x1800ad698  test    eax, eax
0x1800ad69a  js      loc_1800AD84D
0x1800ad6a0  cmp     dword ptr [rbp+var_38], r12d
0x1800ad6a4  jz      short loc_1800AD6B2
0x1800ad6a6  mov     rax, [rbp+var_40]
0x1800ad6aa  mov     dword ptr [rbp+var_38], r12d
0x1800ad6ae  mov     [rax], r12w
0x1800ad6b2  mov     r9d, 8; unsigned int
0x1800ad6b8  mov     [rbp+var_28], r12
0x1800ad6bc  lea     r8, [rbp+var_20]; void *
0x1800ad6c0  mov     [rbp+var_48], r12d
0x1800ad6c4  xor     edx, edx; unsigned int
0x1800ad6c6  mov     rcx, rsi; this
0x1800ad6c9  call    ?GetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::GetBasicColumn(ulong,void *,ulong)
0x1800ad6ce  mov     edi, eax
0x1800ad6d0  test    eax, eax
0x1800ad6d2  js      loc_1800AD846
0x1800ad6d8  lea     r8, [rbp+var_40]; struct CWxString *
0x1800ad6dc  mov     edx, 4; unsigned int
0x1800ad6e1  mov     rcx, rsi; this
0x1800ad6e4  call    ?GetStringColumn@CJetContext@@QEAAJKPEAVCWxString@@@Z; CJetContext::GetStringColumn(ulong,CWxString *)
0x1800ad6e9  mov     edi, eax
0x1800ad6eb  test    eax, eax
0x1800ad6ed  js      loc_1800AD83D
0x1800ad6f3  mov     r9d, 8; unsigned int
0x1800ad6f9  lea     r8, [rbp+var_28]; void *
0x1800ad6fd  mov     rcx, rsi; this
0x1800ad700  lea     edx, [r9-3]; unsigned int
0x1800ad704  call    ?GetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::GetBasicColumn(ulong,void *,ulong)
0x1800ad709  mov     edi, eax
0x1800ad70b  test    eax, eax
0x1800ad70d  js      loc_1800AD834
0x1800ad713  lea     r8, [rbp+var_18]; struct CWxString *
0x1800ad717  mov     edx, r13d; unsigned int
0x1800ad71a  mov     rcx, rsi; this
0x1800ad71d  call    ?GetStringColumn@CJetContext@@QEAAJKPEAVCWxString@@@Z; CJetContext::GetStringColumn(ulong,CWxString *)
0x1800ad722  mov     edi, eax
0x1800ad724  test    eax, eax
0x1800ad726  js      loc_1800AD82B
0x1800ad72c  test    rbx, rbx
0x1800ad72f  jz      short loc_1800AD739
0x1800ad731  mov     rcx, rbx; this
0x1800ad734  call    ?Release@CWxCallerIdentity@@QEAAKXZ; CWxCallerIdentity::Release(void)
0x1800ad739  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800ad740  xor     edx, edx; dwFlags
0x1800ad742  lea     r8d, [rdx+28h]; dwBytes
0x1800ad746  call    cs:__imp_HeapAlloc
0x1800ad74c  mov     rbx, rax
0x1800ad74f  test    rax, rax
0x1800ad752  jz      loc_1800AD81A
0x1800ad758  mov     [rax], r13
0x1800ad75b  lea     rax, Data
0x1800ad762  mov     [rbx+8], rax
0x1800ad766  mov     [rbx+10h], r12
0x1800ad76a  mov     [rbx+18h], r12
0x1800ad76e  mov     [rbx+20h], r12
0x1800ad772  mov     rdx, [rbp+var_18]; unsigned __int16 *
0x1800ad776  mov     rcx, rbx; this
0x1800ad779  call    ?Initialize@CWxCallerIdentity@@QEAAJPEBG@Z; CWxCallerIdentity::Initialize(ushort const *)
0x1800ad77e  mov     edi, eax
0x1800ad780  test    eax, eax
0x1800ad782  js      loc_1800AD811
0x1800ad788  cmp     dword ptr [rbp+var_38], r12d
0x1800ad78c  jz      short loc_1800AD7E6
0x1800ad78e  mov     r8, [rbp+var_20]; unsigned __int64
0x1800ad792  lea     rax, [rbp+var_48]
0x1800ad796  mov     [rsp+80h+var_58], rax; int *
0x1800ad79b  mov     r9, rbx; struct CWxCallerIdentity *
0x1800ad79e  mov     rax, [rbp+var_40]
0x1800ad7a2  mov     rdx, r14; struct CCacheStore *
0x1800ad7a5  mov     rcx, r15; this
0x1800ad7a8  mov     qword ptr [rsp+80h+grbit], rax; unsigned __int16 *
0x1800ad7ad  call    ?HstsDeleteObsoleteContainerAtCursorIfCanaryDeleted@CHstsStore@@AEAAJPEAVCCacheStore@@_KPEAVCWxCallerIdentity@@PEBGPEAH@Z; CHstsStore::HstsDeleteObsoleteContainerAtCursorIfCanaryDeleted(CCacheStore *,unsigned __int64,CWxCallerIdentity *,ushort const *,int *)
0x1800ad7b2  mov     edi, eax
0x1800ad7b4  test    eax, eax
0x1800ad7b6  js      short loc_1800AD808
0x1800ad7b8  cmp     [rbp+var_48], r12d
0x1800ad7bc  jnz     short loc_1800AD7E6
0x1800ad7be  mov     rcx, 58028E44000h
0x1800ad7c8  add     rcx, [rbp+var_28]
0x1800ad7cc  jnz     short loc_1800AD7E6
0x1800ad7ce  mov     r8, [rbp+var_20]; unsigned __int64
0x1800ad7d2  mov     r9, rbx; struct CWxCallerIdentity *
0x1800ad7d5  mov     rdx, r14; struct CCacheStore *
0x1800ad7d8  mov     rcx, r15; this
0x1800ad7db  call    ?HstsPurgeExpiredEntriesInTable@CHstsStore@@AEAAJPEAVCCacheStore@@_KPEAVCWxCallerIdentity@@@Z; CHstsStore::HstsPurgeExpiredEntriesInTable(CCacheStore *,unsigned __int64,CWxCallerIdentity *)
0x1800ad7e0  mov     edi, eax
0x1800ad7e2  test    eax, eax
0x1800ad7e4  js      short loc_1800AD7FF
0x1800ad7e6  mov     rdx, [rsi+20h]; tableid
0x1800ad7ea  xor     r9d, r9d; grbit
0x1800ad7ed  mov     rcx, [rsi+10h]; sesid
0x1800ad7f1  mov     r8d, r13d; cRow
0x1800ad7f4  call    cs:__imp_JetMove
0x1800ad7fa  jmp     loc_1800AD681
0x1800ad7ff  mov     [rbp+var_44], 238h
0x1800ad806  jmp     short loc_1800AD84D
0x1800ad808  mov     [rbp+var_44], 227h
0x1800ad80f  jmp     short loc_1800AD84D
0x1800ad811  mov     [rbp+var_44], 21Bh
0x1800ad818  jmp     short loc_1800AD84D
0x1800ad81a  mov     rbx, r12
0x1800ad81d  mov     [rbp+var_44], 21Ah
0x1800ad824  mov     edi, 8007000Eh
0x1800ad829  jmp     short loc_1800AD84D
0x1800ad82b  mov     [rbp+var_44], 212h
0x1800ad832  jmp     short loc_1800AD84D
0x1800ad834  mov     [rbp+var_44], 210h
0x1800ad83b  jmp     short loc_1800AD84D
0x1800ad83d  mov     [rbp+var_44], 20Ch
0x1800ad844  jmp     short loc_1800AD84D
0x1800ad846  mov     [rbp+var_44], 20Ah
0x1800ad84d  mov     rcx, [rsi+10h]; sesid
0x1800ad851  xor     edx, edx; grbit
0x1800ad853  call    cs:__imp_JetRollback
0x1800ad859  test    rsi, rsi
0x1800ad85c  jz      short loc_1800AD86E
0x1800ad85e  mov     rcx, [r14+1B8h]; this
0x1800ad865  lea     rdx, [rbp+var_50]; struct CJetContext **
0x1800ad869  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x1800ad86e  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ad875  jz      short loc_1800AD890
0x1800ad877  mov     edx, 19h
0x1800ad87c  lea     r8, WPP_9d52da5ef3ad3c382853cb62ff3dbf62_Traceguids
0x1800ad883  mov     ecx, 40Ch
0x1800ad888  mov     r9d, edi
0x1800ad88b  call    WPP_SF_d
0x1800ad890  test    rbx, rbx
0x1800ad893  jz      short loc_1800AD89D
0x1800ad895  mov     rcx, rbx; this
0x1800ad898  call    ?Release@CWxCallerIdentity@@QEAAKXZ; CWxCallerIdentity::Release(void)
0x1800ad89d  lea     rcx, [rbp+var_18]; this
0x1800ad8a1  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800ad8a6  lea     rcx, [rbp+var_40]; this
0x1800ad8aa  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800ad8af  mov     eax, edi
0x1800ad8b1  mov     rcx, [rbp+var_8]
0x1800ad8b5  xor     rcx, rsp; StackCookie
0x1800ad8b8  call    __security_check_cookie
0x1800ad8bd  mov     rbx, [rsp+80h+arg_10]
0x1800ad8c5  add     rsp, 80h
0x1800ad8cc  pop     r15
0x1800ad8ce  pop     r14
0x1800ad8d0  pop     r13
0x1800ad8d2  pop     r12
0x1800ad8d4  pop     rdi
0x1800ad8d5  pop     rsi
0x1800ad8d6  pop     rbp
0x1800ad8d7  retn
```
