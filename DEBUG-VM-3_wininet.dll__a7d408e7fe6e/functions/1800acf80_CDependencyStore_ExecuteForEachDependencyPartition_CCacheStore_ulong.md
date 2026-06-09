# CDependencyStore::ExecuteForEachDependencyPartition(CCacheStore *,ulong)

- ea: `0x1800acf80`
- end: `0x1800ad377`
- name: `?ExecuteForEachDependencyPartition@CDependencyStore@@AEAAJPEAVCCacheStore@@K@Z`
- size: `1015`
- prototype: `int(CDependencyStore *__hidden this, struct CCacheStore *, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, installer_update, broker_com_uri`

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
- `0x1800acf80`
- `0x1800ade24`
- `0x1800ae7a4`
- `0x180126004`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e490c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ad1c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ad1c4`
- `ESENT!JetMakeKey` at `0x1800ad080`
- `ESENT!JetMakeKey` at `0x1800ad080`
- `ESENT!JetCommitTransaction` at `0x1800ad335`
- `ESENT!JetCommitTransaction` at `0x1800ad335`
- `ESENT!JetRollback` at `0x1800ad34e`
- `ESENT!JetRollback` at `0x1800ad34e`
- `ESENT!JetBeginTransaction` at `0x1800ad04c`
- `ESENT!JetBeginTransaction` at `0x1800ad04c`
- `ESENT!JetMove` at `0x1800ad25a`
- `ESENT!JetMove` at `0x1800ad25a`
- `ESENT!JetSeek` at `0x1800ad12e`
- `ESENT!JetSeek` at `0x1800ad12e`

## pseudocode

```c
__int64 __fastcall CDependencyStore::ExecuteForEachDependencyPartition(
        CDependencyStore *this,
        CJetContextList **a2,
        int a3)
{
  JET_SESID *v3; // r14
  CWxCallerIdentity *v4; // rbx
  CJetContextList **v8; // rdi
  int v9; // eax
  unsigned int v10; // r9d
  int BasicColumn; // esi
  JET_ERR v12; // eax
  JET_ERR Key; // eax
  JET_ERR i; // eax
  CWxCallerIdentity *v16; // rax
  int v17; // [rsp+48h] [rbp-31h]
  struct CJetContext *v18; // [rsp+50h] [rbp-29h] BYREF
  int v19; // [rsp+58h] [rbp-21h] BYREF
  unsigned __int16 *v20; // [rsp+60h] [rbp-19h] BYREF
  __int64 v21; // [rsp+68h] [rbp-11h]
  int pvData; // [rsp+70h] [rbp-9h] BYREF
  unsigned __int64 v23; // [rsp+78h] [rbp-1h] BYREF
  unsigned __int16 *v24; // [rsp+80h] [rbp+7h] BYREF
  __int64 v25; // [rsp+88h] [rbp+Fh]

  pvData = 1;
  v17 = 0;
  v3 = 0;
  v18 = 0;
  v4 = 0;
  v20 = (unsigned __int16 *)&Data;
  v21 = 0;
  v23 = 0;
  v24 = (unsigned __int16 *)&Data;
  v25 = 0;
  v19 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qqD(1036, 20, (unsigned int)&WPP_28c37ca9899f33ac28da9a29870553e3_Traceguids, (_DWORD)this, (__int64)a2);
  if ( (unsigned int)CCacheStore::IsTerminating((CCacheStore *)a2) )
  {
    BasicColumn = 0;
    v8 = a2 + 55;
  }
  else
  {
    v8 = a2 + 55;
    v9 = CJetContextList::AcquireContext(a2[55], &v18, 0);
    v3 = (JET_SESID *)v18;
    BasicColumn = v9;
    if ( v9 >= 0 )
    {
      BasicColumn = CJetContext::SetCurrentIndex(v18, 2u, L"PartitionTypeIndex", v10);
      if ( BasicColumn >= 0 )
      {
        v12 = JetBeginTransaction(v3[2]);
        BasicColumn = HRESULTFromJET_ERR(v12, 1);
        if ( BasicColumn >= 0 )
        {
          v17 = 1;
          Key = JetMakeKey(v3[2], v3[4], &pvData, 4u, 1u);
          BasicColumn = HRESULTFromJET_ERR(Key, 1);
          if ( BasicColumn >= 0 )
          {
            for ( i = JetSeek(v3[2], v3[4], 0x21u); i != -1603; i = JetMove(v3[2], v3[4], 1, 0) )
            {
              BasicColumn = HRESULTFromJET_ERR(i, 1);
              if ( BasicColumn < 0 )
                break;
              if ( (_DWORD)v21 )
              {
                LODWORD(v21) = 0;
                *v20 = 0;
              }
              if ( (_DWORD)v25 )
              {
                LODWORD(v25) = 0;
                *v24 = 0;
              }
              BasicColumn = CJetContext::GetBasicColumn((CJetContext *)v3, 0, &v23, 8u);
              if ( BasicColumn < 0 )
                break;
              BasicColumn = CJetContext::GetStringColumn((CJetContext *)v3, 1u, (struct CWxString *)&v24);
              if ( BasicColumn < 0 )
                break;
              if ( v4 )
                CWxCallerIdentity::Release(v4);
              v16 = (CWxCallerIdentity *)HeapAlloc(g_hWxProcessHeap, 0, 0x28u);
              v4 = v16;
              if ( !v16 )
              {
                v4 = 0;
                BasicColumn = -2147024882;
                break;
              }
              *(_QWORD *)v16 = 1;
              *((_QWORD *)v16 + 1) = &Data;
              *((_QWORD *)v16 + 2) = 0;
              *((_QWORD *)v16 + 3) = 0;
              *((_QWORD *)v16 + 4) = 0;
              BasicColumn = CWxCallerIdentity::Initialize(v16, v24);
              if ( BasicColumn < 0 )
                break;
              BasicColumn = CJetContext::GetStringColumn((CJetContext *)v3, 4u, (struct CWxString *)&v20);
              if ( BasicColumn < 0 )
                break;
              if ( (_DWORD)v21 )
              {
                if ( a3 )
                {
                  if ( a3 == 1 )
                    CDependencyStore::PurgeExpiredEntries(
                      this,
                      (struct CCacheStore *)a2,
                      (struct CJetContext *)v3,
                      v4,
                      v20,
                      v23,
                      &v19);
                }
                else
                {
                  CDependencyStore::PurgeObsoleteContainer(this, a2, v4, v20, (unsigned __int16 *)v23);
                }
              }
            }
          }
        }
      }
    }
  }
  if ( (!v19 || JetCommitTransaction(v3[2], 1u)) && v17 )
    JetRollback(v3[2], 0);
  if ( v3 )
    CJetContextList::ReleaseContext(*v8, &v18);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 21, &WPP_28c37ca9899f33ac28da9a29870553e3_Traceguids, (unsigned int)BasicColumn);
  if ( v4 )
    CWxCallerIdentity::Release(v4);
  CWxString::_Release((CWxString *)&v24);
  CWxString::_Release((CWxString *)&v20);
  return (unsigned int)BasicColumn;
}

```

## disassembly

```asm
0x1800acf80  mov     [rsp-8+arg_10], rbx
0x1800acf85  push    rbp
0x1800acf86  push    rsi
0x1800acf87  push    rdi
0x1800acf88  push    r12
0x1800acf8a  push    r13
0x1800acf8c  push    r14
0x1800acf8e  push    r15
0x1800acf90  lea     rbp, [rsp-27h]
0x1800acf95  sub     rsp, 0A0h
0x1800acf9c  mov     rax, cs:__security_cookie
0x1800acfa3  xor     rax, rsp
0x1800acfa6  mov     [rbp+57h+var_40], rax
0x1800acfaa  xor     edi, edi
0x1800acfac  mov     [rbp+57h+pvData], 1
0x1800acfb3  lea     rax, Data
0x1800acfba  mov     [rbp+57h+var_8C], edi
0x1800acfbd  mov     [rbp+57h+var_88], edi
0x1800acfc0  mov     r14d, edi
0x1800acfc3  mov     [rbp+57h+var_80], rdi
0x1800acfc7  mov     ebx, edi
0x1800acfc9  mov     [rbp+57h+var_70], rax
0x1800acfcd  mov     r12d, r8d
0x1800acfd0  mov     [rbp+57h+var_68], rdi
0x1800acfd4  mov     r15, rdx
0x1800acfd7  mov     [rbp+57h+var_58], rdi
0x1800acfdb  mov     r13, rcx
0x1800acfde  mov     [rbp+57h+var_50], rax
0x1800acfe2  mov     [rbp+57h+var_48], rdi
0x1800acfe6  mov     [rbp+57h+var_78], edi
0x1800acfe9  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800acff0  jnz     loc_1800AD2C8
0x1800acff6  mov     rcx, r15; this
0x1800acff9  call    ?IsTerminating@CCacheStore@@QEAAHXZ; CCacheStore::IsTerminating(void)
0x1800acffe  test    eax, eax
0x1800ad000  jnz     loc_1800AD107
0x1800ad006  lea     rdi, [r15+1B8h]
0x1800ad00d  xor     r8d, r8d; int *
0x1800ad010  mov     rcx, [rdi]; this
0x1800ad013  lea     rdx, [rbp+57h+var_80]; struct CJetContext **
0x1800ad017  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1800ad01c  mov     r14, [rbp+57h+var_80]
0x1800ad020  mov     esi, eax
0x1800ad022  test    eax, eax
0x1800ad024  js      loc_1800AD2F0
0x1800ad02a  lea     r8, aPartitiontypei; "PartitionTypeIndex"
0x1800ad031  mov     edx, 2; unsigned int
0x1800ad036  mov     rcx, r14; this
0x1800ad039  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1800ad03e  mov     esi, eax
0x1800ad040  test    eax, eax
0x1800ad042  js      loc_1800AD2FC
0x1800ad048  mov     rcx, [r14+10h]; sesid
0x1800ad04c  call    cs:__imp_JetBeginTransaction
0x1800ad052  mov     ecx, eax; int
0x1800ad054  mov     edx, 1; int
0x1800ad059  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ad05e  mov     esi, eax
0x1800ad060  test    eax, eax
0x1800ad062  js      short loc_1800AD099
0x1800ad064  mov     rdx, [r14+20h]; tableid
0x1800ad068  lea     r8, [rbp+57h+pvData]; pvData
0x1800ad06c  mov     rcx, [r14+10h]; sesid
0x1800ad070  mov     esi, 1
0x1800ad075  mov     [rbp+57h+var_88], esi
0x1800ad078  mov     [rsp+0D0h+grbit], esi; grbit
0x1800ad07c  lea     r9d, [rsi+3]; cbData
0x1800ad080  call    cs:__imp_JetMakeKey
0x1800ad086  mov     ecx, eax; int
0x1800ad088  mov     edx, esi; int
0x1800ad08a  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ad08f  mov     esi, eax
0x1800ad091  test    eax, eax
0x1800ad093  jns     loc_1800AD120
0x1800ad099  cmp     [rbp+57h+var_78], 0
0x1800ad09d  jnz     loc_1800AD32C
0x1800ad0a3  cmp     [rbp+57h+var_88], 0
0x1800ad0a7  jnz     loc_1800AD348
0x1800ad0ad  test    r14, r14
0x1800ad0b0  jnz     short loc_1800AD112
0x1800ad0b2  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ad0b9  jnz     loc_1800AD359
0x1800ad0bf  test    rbx, rbx
0x1800ad0c2  jz      short loc_1800AD0CC
0x1800ad0c4  mov     rcx, rbx; this
0x1800ad0c7  call    ?Release@CWxCallerIdentity@@QEAAKXZ; CWxCallerIdentity::Release(void)
0x1800ad0cc  lea     rcx, [rbp+57h+var_50]; this
0x1800ad0d0  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800ad0d5  lea     rcx, [rbp+57h+var_70]; this
0x1800ad0d9  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800ad0de  mov     eax, esi
0x1800ad0e0  mov     rcx, [rbp+57h+var_40]
0x1800ad0e4  xor     rcx, rsp; StackCookie
0x1800ad0e7  call    __security_check_cookie
0x1800ad0ec  mov     rbx, [rsp+0D0h+arg_10]
0x1800ad0f4  add     rsp, 0A0h
0x1800ad0fb  pop     r15
0x1800ad0fd  pop     r14
0x1800ad0ff  pop     r13
0x1800ad101  pop     r12
0x1800ad103  pop     rdi
0x1800ad104  pop     rsi
0x1800ad105  pop     rbp
0x1800ad106  retn
0x1800ad107  mov     esi, edi
0x1800ad109  lea     rdi, [r15+1B8h]
0x1800ad110  jmp     short loc_1800AD099
0x1800ad112  mov     rcx, [rdi]; this
0x1800ad115  lea     rdx, [rbp+57h+var_80]; struct CJetContext **
0x1800ad119  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x1800ad11e  jmp     short loc_1800AD0B2
0x1800ad120  mov     rdx, [r14+20h]; tableid
0x1800ad124  mov     r8d, 21h ; '!'; grbit
0x1800ad12a  mov     rcx, [r14+10h]; sesid
0x1800ad12e  call    cs:__imp_JetSeek
0x1800ad134  cmp     eax, 0FFFFF9BDh
0x1800ad139  jz      loc_1800AD099
0x1800ad13f  mov     edx, 1; int
0x1800ad144  mov     ecx, eax; int
0x1800ad146  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ad14b  mov     esi, eax
0x1800ad14d  test    eax, eax
0x1800ad14f  js      loc_1800AD099
0x1800ad155  xor     esi, esi
0x1800ad157  cmp     dword ptr [rbp+57h+var_68], esi
0x1800ad15a  jz      short loc_1800AD166
0x1800ad15c  mov     rax, [rbp+57h+var_70]
0x1800ad160  mov     dword ptr [rbp+57h+var_68], esi
0x1800ad163  mov     [rax], si
0x1800ad166  cmp     dword ptr [rbp+57h+var_48], esi
0x1800ad169  jnz     loc_1800AD265
0x1800ad16f  mov     r9d, 8; unsigned int
0x1800ad175  lea     r8, [rbp+57h+var_58]; void *
0x1800ad179  xor     edx, edx; unsigned int
0x1800ad17b  mov     rcx, r14; this
0x1800ad17e  call    ?GetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::GetBasicColumn(ulong,void *,ulong)
0x1800ad183  mov     esi, eax
0x1800ad185  test    eax, eax
0x1800ad187  js      loc_1800AD320
0x1800ad18d  lea     r8, [rbp+57h+var_50]; struct CWxString *
0x1800ad191  mov     edx, 1; unsigned int
0x1800ad196  mov     rcx, r14; this
0x1800ad199  call    ?GetStringColumn@CJetContext@@QEAAJKPEAVCWxString@@@Z; CJetContext::GetStringColumn(ulong,CWxString *)
0x1800ad19e  mov     esi, eax
0x1800ad1a0  test    eax, eax
0x1800ad1a2  js      loc_1800AD314
0x1800ad1a8  xor     esi, esi
0x1800ad1aa  test    rbx, rbx
0x1800ad1ad  jz      short loc_1800AD1B7
0x1800ad1af  mov     rcx, rbx; this
0x1800ad1b2  call    ?Release@CWxCallerIdentity@@QEAAKXZ; CWxCallerIdentity::Release(void)
0x1800ad1b7  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800ad1be  xor     edx, edx; dwFlags
0x1800ad1c0  lea     r8d, [rdx+28h]; dwBytes
0x1800ad1c4  call    cs:__imp_HeapAlloc
0x1800ad1ca  mov     rbx, rax
0x1800ad1cd  test    rax, rax
0x1800ad1d0  jz      loc_1800AD274
0x1800ad1d6  mov     qword ptr [rax], 1
0x1800ad1dd  lea     rax, Data
0x1800ad1e4  mov     [rbx+8], rax
0x1800ad1e8  mov     [rbx+10h], rsi
0x1800ad1ec  mov     [rbx+18h], rsi
0x1800ad1f0  mov     [rbx+20h], rsi
0x1800ad1f4  mov     rdx, [rbp+57h+var_50]; unsigned __int16 *
0x1800ad1f8  mov     rcx, rbx; this
0x1800ad1fb  call    ?Initialize@CWxCallerIdentity@@QEAAJPEBG@Z; CWxCallerIdentity::Initialize(ushort const *)
0x1800ad200  mov     esi, eax
0x1800ad202  test    eax, eax
0x1800ad204  js      loc_1800AD308
0x1800ad20a  lea     r8, [rbp+57h+var_70]; struct CWxString *
0x1800ad20e  mov     edx, 4; unsigned int
0x1800ad213  mov     rcx, r14; this
0x1800ad216  call    ?GetStringColumn@CJetContext@@QEAAJKPEAVCWxString@@@Z; CJetContext::GetStringColumn(ulong,CWxString *)
0x1800ad21b  mov     esi, eax
0x1800ad21d  test    eax, eax
0x1800ad21f  js      loc_1800AD2BC
0x1800ad225  cmp     dword ptr [rbp+57h+var_68], 0
0x1800ad229  jz      short loc_1800AD24B
0x1800ad22b  test    r12d, r12d
0x1800ad22e  jnz     short loc_1800AD288
0x1800ad230  mov     rax, [rbp+57h+var_58]
0x1800ad234  mov     r8, rbx; struct CWxCallerIdentity *
0x1800ad237  mov     r9, [rbp+57h+var_70]; unsigned __int16 *
0x1800ad23b  mov     rdx, r15; struct CCacheStore *
0x1800ad23e  mov     rcx, r13; this
0x1800ad241  mov     qword ptr [rsp+0D0h+grbit], rax; unsigned __int64
0x1800ad246  call    ?PurgeObsoleteContainer@CDependencyStore@@AEAAJPEAVCCacheStore@@PEAVCWxCallerIdentity@@PEBG_K@Z; CDependencyStore::PurgeObsoleteContainer(CCacheStore *,CWxCallerIdentity *,ushort const *,unsigned __int64)
0x1800ad24b  mov     rdx, [r14+20h]; tableid
0x1800ad24f  xor     r9d, r9d; grbit
0x1800ad252  mov     rcx, [r14+10h]; sesid
0x1800ad256  lea     r8d, [r9+1]; cRow
0x1800ad25a  call    cs:__imp_JetMove
0x1800ad260  jmp     loc_1800AD134
0x1800ad265  mov     rax, [rbp+57h+var_50]
0x1800ad269  mov     dword ptr [rbp+57h+var_48], esi
0x1800ad26c  mov     [rax], si
0x1800ad26f  jmp     loc_1800AD16F
0x1800ad274  mov     rbx, rsi
0x1800ad277  mov     [rbp+57h+var_8C], 1F7h
0x1800ad27e  mov     esi, 8007000Eh
0x1800ad283  jmp     loc_1800AD099
0x1800ad288  cmp     r12d, 1
0x1800ad28c  jnz     short loc_1800AD24B
0x1800ad28e  lea     rax, [rbp+57h+var_78]
0x1800ad292  mov     r9, rbx; struct CWxCallerIdentity *
0x1800ad295  mov     [rsp+0D0h+var_A0], rax; int *
0x1800ad29a  mov     r8, r14; struct CJetContext *
0x1800ad29d  mov     rax, [rbp+57h+var_58]
0x1800ad2a1  mov     rdx, r15; struct CCacheStore *
0x1800ad2a4  mov     [rsp+0D0h+var_A8], rax; unsigned __int64
0x1800ad2a9  mov     rcx, r13; this
0x1800ad2ac  mov     rax, [rbp+57h+var_70]
0x1800ad2b0  mov     qword ptr [rsp+0D0h+grbit], rax; unsigned __int16 *
0x1800ad2b5  call    ?PurgeExpiredEntries@CDependencyStore@@AEAAJPEAVCCacheStore@@PEAVCJetContext@@PEAVCWxCallerIdentity@@PEBG_KPEAH@Z; CDependencyStore::PurgeExpiredEntries(CCacheStore *,CJetContext *,CWxCallerIdentity *,ushort const *,unsigned __int64,int *)
0x1800ad2ba  jmp     short loc_1800AD24B
0x1800ad2bc  mov     [rbp+57h+var_8C], 1FFh
0x1800ad2c3  jmp     loc_1800AD099
0x1800ad2c8  mov     edx, 14h
0x1800ad2cd  mov     dword ptr [rsp+0D0h+var_A8], r12d
0x1800ad2d2  mov     ecx, 40Ch
0x1800ad2d7  mov     qword ptr [rsp+0D0h+grbit], r15
0x1800ad2dc  mov     r9, r13
0x1800ad2df  lea     r8, WPP_28c37ca9899f33ac28da9a29870553e3_Traceguids
0x1800ad2e6  call    WPP_SF_qqD
0x1800ad2eb  jmp     loc_1800ACFF6
0x1800ad2f0  mov     [rbp+57h+var_8C], 1C6h
0x1800ad2f7  jmp     loc_1800AD099
0x1800ad2fc  mov     [rbp+57h+var_8C], 1CAh
0x1800ad303  jmp     loc_1800AD099
0x1800ad308  mov     [rbp+57h+var_8C], 1F8h
0x1800ad30f  jmp     loc_1800AD099
0x1800ad314  mov     [rbp+57h+var_8C], 1EFh
0x1800ad31b  jmp     loc_1800AD099
0x1800ad320  mov     [rbp+57h+var_8C], 1ECh
0x1800ad327  jmp     loc_1800AD099
0x1800ad32c  mov     rcx, [r14+10h]; sesid
0x1800ad330  mov     edx, 1; grbit
0x1800ad335  call    cs:__imp_JetCommitTransaction
0x1800ad33b  test    eax, eax
0x1800ad33d  jz      loc_1800AD0AD
0x1800ad343  jmp     loc_1800AD0A3
0x1800ad348  mov     rcx, [r14+10h]; sesid
0x1800ad34c  xor     edx, edx; grbit
0x1800ad34e  call    cs:__imp_JetRollback
0x1800ad354  jmp     loc_1800AD0AD
0x1800ad359  mov     edx, 15h
0x1800ad35e  lea     r8, WPP_28c37ca9899f33ac28da9a29870553e3_Traceguids
0x1800ad365  mov     ecx, 40Ch
0x1800ad36a  mov     r9d, esi
0x1800ad36d  call    WPP_SF_d
0x1800ad372  jmp     loc_1800AD0BF
```
