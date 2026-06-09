# CBlobStore::Cleanup(CCacheStore *)

- ea: `0x1800aee7c`
- end: `0x1800af244`
- name: `?Cleanup@CBlobStore@@QEAAJPEAVCCacheStore@@@Z`
- size: `968`
- prototype: `__int64 __fastcall(CBlobStore *__hidden this, struct CCacheStore *)`
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
- `0x1800ade24`
- `0x1800ae1dc`
- `0x1800aee7c`
- `0x1800af24c`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e2f30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800af0cc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800af0cc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800aef23`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800aef23`
- `ESENT!JetMakeKey` at `0x1800aefb1`
- `ESENT!JetMakeKey` at `0x1800aefb1`
- `ESENT!JetRollback` at `0x1800af1bf`
- `ESENT!JetRollback` at `0x1800af1bf`
- `ESENT!JetBeginTransaction` at `0x1800aef7c`
- `ESENT!JetBeginTransaction` at `0x1800aef7c`
- `ESENT!JetMove` at `0x1800af160`
- `ESENT!JetMove` at `0x1800af160`
- `ESENT!JetSeek` at `0x1800aefd7`
- `ESENT!JetSeek` at `0x1800aefd7`

## pseudocode

```c
__int64 __fastcall CBlobStore::Cleanup(CBlobStore *this, CJetContextList **a2)
{
  CWxCallerIdentity *v2; // rbx
  int BasicColumn; // edi
  int v6; // eax
  unsigned int v7; // r9d
  JET_SESID *v8; // rsi
  JET_ERR v9; // eax
  JET_ERR Key; // eax
  JET_ERR i; // eax
  CWxCallerIdentity *v12; // rax
  struct CJetContext *v14; // [rsp+30h] [rbp-39h] BYREF
  int v15; // [rsp+38h] [rbp-31h] BYREF
  int v16; // [rsp+3Ch] [rbp-2Dh]
  int pvData; // [rsp+40h] [rbp-29h] BYREF
  __int64 v18; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int64 v19; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int16 *v20; // [rsp+58h] [rbp-11h] BYREF
  __int64 v21; // [rsp+60h] [rbp-9h]
  unsigned __int16 *v22; // [rsp+68h] [rbp-1h] BYREF
  __int64 v23; // [rsp+70h] [rbp+7h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+78h] [rbp+Fh] BYREF

  pvData = 4;
  v16 = 0;
  v14 = 0;
  v2 = 0;
  v22 = (unsigned __int16 *)&Data;
  v23 = 0;
  v20 = (unsigned __int16 *)&Data;
  v21 = 0;
  v19 = 0;
  SystemTimeAsFileTime = 0;
  v18 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qq(1036, 20, (unsigned int)&WPP_5a95f2a397ca3ed9078c668ec868fb04_Traceguids, (_DWORD)this, (__int64)a2);
  if ( (unsigned int)CCacheStore::IsTerminating((CCacheStore *)a2) )
  {
    BasicColumn = 0;
  }
  else
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
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
              if ( (_DWORD)v23 )
              {
                LODWORD(v23) = 0;
                *v22 = 0;
              }
              if ( (_DWORD)v21 )
              {
                LODWORD(v21) = 0;
                *v20 = 0;
              }
              v18 = 0;
              v15 = 0;
              BasicColumn = CJetContext::GetBasicColumn((CJetContext *)v8, 5u, &v18, 8u);
              if ( BasicColumn < 0 )
              {
                v16 = 373;
                break;
              }
              if ( v18 + 864000000000LL <= *(unsigned __int64 *)&SystemTimeAsFileTime )
              {
                BasicColumn = CJetContext::GetBasicColumn((CJetContext *)v8, 0, &v19, 8u);
                if ( BasicColumn < 0 )
                {
                  v16 = 382;
                  break;
                }
                BasicColumn = CJetContext::GetStringColumn((CJetContext *)v8, 4u, (struct CWxString *)&v22);
                if ( BasicColumn < 0 )
                {
                  v16 = 384;
                  break;
                }
                BasicColumn = CJetContext::GetStringColumn((CJetContext *)v8, 1u, (struct CWxString *)&v20);
                if ( BasicColumn < 0 )
                {
                  v16 = 386;
                  break;
                }
                if ( v2 )
                  CWxCallerIdentity::Release(v2);
                v12 = (CWxCallerIdentity *)HeapAlloc(g_hWxProcessHeap, 0, 0x28u);
                v2 = v12;
                if ( !v12 )
                {
                  v2 = 0;
                  v16 = 394;
                  BasicColumn = -2147024882;
                  break;
                }
                *(_QWORD *)v12 = 1;
                *((_QWORD *)v12 + 1) = &Data;
                *((_QWORD *)v12 + 2) = 0;
                *((_QWORD *)v12 + 3) = 0;
                *((_QWORD *)v12 + 4) = 0;
                BasicColumn = CWxCallerIdentity::Initialize(v12, v20);
                if ( BasicColumn < 0 )
                {
                  v16 = 395;
                  break;
                }
                BasicColumn = CBlobStore::BlobDeleteObsoleteContainerIfCanaryDeleted(
                                this,
                                (struct CCacheStore *)a2,
                                v19,
                                v2,
                                v22,
                                &v15);
                if ( BasicColumn < 0 )
                {
                  v16 = 401;
                  break;
                }
                if ( !v15 )
                {
                  BasicColumn = CBlobStore::BlobPurgeExpiredEntriesInTable(this, a2, v19, v2);
                  if ( BasicColumn < 0 )
                  {
                    v16 = 407;
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
        v16 = 339;
      }
    }
    else
    {
      v16 = 335;
    }
    if ( v8 )
      CJetContextList::ReleaseContext(a2[55], &v14);
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 21, &WPP_5a95f2a397ca3ed9078c668ec868fb04_Traceguids, (unsigned int)BasicColumn);
  if ( v2 )
    CWxCallerIdentity::Release(v2);
  CWxString::_Release((CWxString *)&v20);
  CWxString::_Release((CWxString *)&v22);
  return (unsigned int)BasicColumn;
}

```

## disassembly

```asm
0x1800aee7c  mov     [rsp-8+arg_10], rbx
0x1800aee81  push    rbp
0x1800aee82  push    rsi
0x1800aee83  push    rdi
0x1800aee84  push    r12
0x1800aee86  push    r13
0x1800aee88  push    r14
0x1800aee8a  push    r15
0x1800aee8c  lea     rbp, [rsp-27h]
0x1800aee91  sub     rsp, 90h
0x1800aee98  mov     rax, cs:__security_cookie
0x1800aee9f  xor     rax, rsp
0x1800aeea2  mov     [rbp+57h+var_40], rax
0x1800aeea6  xor     r12d, r12d
0x1800aeea9  mov     [rbp+57h+pvData], 4
0x1800aeeb0  lea     rax, Data
0x1800aeeb7  mov     [rbp+57h+var_84], r12d
0x1800aeebb  mov     [rbp+57h+var_90], r12
0x1800aeebf  mov     ebx, r12d
0x1800aeec2  mov     [rbp+57h+var_58], rax
0x1800aeec6  mov     r14, rdx
0x1800aeec9  mov     [rbp+57h+var_50], r12
0x1800aeecd  mov     r15, rcx
0x1800aeed0  mov     [rbp+57h+var_68], rax
0x1800aeed4  mov     [rbp+57h+var_60], r12
0x1800aeed8  mov     [rbp+57h+var_70], r12
0x1800aeedc  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r12
0x1800aeee0  mov     [rbp+57h+var_78], r12
0x1800aeee4  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800aeeeb  jz      short loc_1800AEF0B
0x1800aeeed  lea     edx, [r12+14h]
0x1800aeef2  mov     qword ptr [rsp+0C0h+grbit], r14
0x1800aeef7  mov     ecx, 40Ch
0x1800aeefc  lea     r8, WPP_5a95f2a397ca3ed9078c668ec868fb04_Traceguids
0x1800aef03  mov     r9, r15
0x1800aef06  call    WPP_SF_qq
0x1800aef0b  mov     rcx, r14; this
0x1800aef0e  call    ?IsTerminating@CCacheStore@@QEAAHXZ; CCacheStore::IsTerminating(void)
0x1800aef13  test    eax, eax
0x1800aef15  jz      short loc_1800AEF1F
0x1800aef17  mov     edi, r12d
0x1800aef1a  jmp     loc_1800AF1DA
0x1800aef1f  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800aef23  call    cs:__imp_GetSystemTimeAsFileTime
0x1800aef29  mov     rcx, [r14+1B8h]; this
0x1800aef30  lea     rdx, [rbp+57h+var_90]; struct CJetContext **
0x1800aef34  xor     r8d, r8d; int *
0x1800aef37  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1800aef3c  mov     rsi, [rbp+57h+var_90]
0x1800aef40  mov     edi, eax
0x1800aef42  test    eax, eax
0x1800aef44  jns     short loc_1800AEF52
0x1800aef46  mov     [rbp+57h+var_84], 14Fh
0x1800aef4d  jmp     loc_1800AF1C5
0x1800aef52  lea     r8, aPartitiontypei; "PartitionTypeIndex"
0x1800aef59  mov     edx, 2; unsigned int
0x1800aef5e  mov     rcx, rsi; this
0x1800aef61  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1800aef66  mov     edi, eax
0x1800aef68  test    eax, eax
0x1800aef6a  jns     short loc_1800AEF78
0x1800aef6c  mov     [rbp+57h+var_84], 153h
0x1800aef73  jmp     loc_1800AF1C5
0x1800aef78  mov     rcx, [rsi+10h]; sesid
0x1800aef7c  call    cs:__imp_JetBeginTransaction
0x1800aef82  mov     r13d, 1
0x1800aef88  mov     ecx, eax; int
0x1800aef8a  mov     edx, r13d; int
0x1800aef8d  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800aef92  mov     edi, eax
0x1800aef94  test    eax, eax
0x1800aef96  js      loc_1800AF1C5
0x1800aef9c  mov     rdx, [rsi+20h]; tableid
0x1800aefa0  lea     r9d, [r13+3]; cbData
0x1800aefa4  mov     rcx, [rsi+10h]; sesid
0x1800aefa8  lea     r8, [rbp+57h+pvData]; pvData
0x1800aefac  mov     [rsp+0C0h+grbit], r13d; grbit
0x1800aefb1  call    cs:__imp_JetMakeKey
0x1800aefb7  mov     ecx, eax; int
0x1800aefb9  mov     edx, r13d; int
0x1800aefbc  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800aefc1  mov     edi, eax
0x1800aefc3  test    eax, eax
0x1800aefc5  js      loc_1800AF1B9
0x1800aefcb  mov     rdx, [rsi+20h]; tableid
0x1800aefcf  lea     r8d, [r13+20h]; grbit
0x1800aefd3  mov     rcx, [rsi+10h]; sesid
0x1800aefd7  call    cs:__imp_JetSeek
0x1800aefdd  cmp     eax, 0FFFFF9BDh
0x1800aefe2  jz      loc_1800AF1B9
0x1800aefe8  mov     edx, r13d; int
0x1800aefeb  mov     ecx, eax; int
0x1800aefed  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800aeff2  mov     edi, eax
0x1800aeff4  test    eax, eax
0x1800aeff6  js      loc_1800AF1B9
0x1800aeffc  cmp     dword ptr [rbp+57h+var_50], r12d
0x1800af000  jz      short loc_1800AF00E
0x1800af002  mov     rax, [rbp+57h+var_58]
0x1800af006  mov     dword ptr [rbp+57h+var_50], r12d
0x1800af00a  mov     [rax], r12w
0x1800af00e  cmp     dword ptr [rbp+57h+var_60], r12d
0x1800af012  jz      short loc_1800AF020
0x1800af014  mov     rax, [rbp+57h+var_68]
0x1800af018  mov     dword ptr [rbp+57h+var_60], r12d
0x1800af01c  mov     [rax], r12w
0x1800af020  mov     r9d, 8; unsigned int
0x1800af026  mov     [rbp+57h+var_78], r12
0x1800af02a  lea     r8, [rbp+57h+var_78]; void *
0x1800af02e  mov     [rbp+57h+var_88], r12d
0x1800af032  mov     rcx, rsi; this
0x1800af035  lea     edx, [r9-3]; unsigned int
0x1800af039  call    ?GetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::GetBasicColumn(ulong,void *,ulong)
0x1800af03e  mov     edi, eax
0x1800af040  test    eax, eax
0x1800af042  js      loc_1800AF1B2
0x1800af048  mov     rcx, 0C92A69C000h
0x1800af052  add     rcx, [rbp+57h+var_78]
0x1800af056  cmp     rcx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800af05a  ja      loc_1800AF152
0x1800af060  mov     r9d, 8; unsigned int
0x1800af066  lea     r8, [rbp+57h+var_70]; void *
0x1800af06a  xor     edx, edx; unsigned int
0x1800af06c  mov     rcx, rsi; this
0x1800af06f  call    ?GetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::GetBasicColumn(ulong,void *,ulong)
0x1800af074  mov     edi, eax
0x1800af076  test    eax, eax
0x1800af078  js      loc_1800AF1A9
0x1800af07e  lea     r8, [rbp+57h+var_58]; struct CWxString *
0x1800af082  mov     edx, 4; unsigned int
0x1800af087  mov     rcx, rsi; this
0x1800af08a  call    ?GetStringColumn@CJetContext@@QEAAJKPEAVCWxString@@@Z; CJetContext::GetStringColumn(ulong,CWxString *)
0x1800af08f  mov     edi, eax
0x1800af091  test    eax, eax
0x1800af093  js      loc_1800AF1A0
0x1800af099  lea     r8, [rbp+57h+var_68]; struct CWxString *
0x1800af09d  mov     edx, r13d; unsigned int
0x1800af0a0  mov     rcx, rsi; this
0x1800af0a3  call    ?GetStringColumn@CJetContext@@QEAAJKPEAVCWxString@@@Z; CJetContext::GetStringColumn(ulong,CWxString *)
0x1800af0a8  mov     edi, eax
0x1800af0aa  test    eax, eax
0x1800af0ac  js      loc_1800AF197
0x1800af0b2  test    rbx, rbx
0x1800af0b5  jz      short loc_1800AF0BF
0x1800af0b7  mov     rcx, rbx; this
0x1800af0ba  call    ?Release@CWxCallerIdentity@@QEAAKXZ; CWxCallerIdentity::Release(void)
0x1800af0bf  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800af0c6  xor     edx, edx; dwFlags
0x1800af0c8  lea     r8d, [rdx+28h]; dwBytes
0x1800af0cc  call    cs:__imp_HeapAlloc
0x1800af0d2  mov     rbx, rax
0x1800af0d5  test    rax, rax
0x1800af0d8  jz      loc_1800AF186
0x1800af0de  mov     [rax], r13
0x1800af0e1  lea     rax, Data
0x1800af0e8  mov     [rbx+8], rax
0x1800af0ec  mov     [rbx+10h], r12
0x1800af0f0  mov     [rbx+18h], r12
0x1800af0f4  mov     [rbx+20h], r12
0x1800af0f8  mov     rdx, [rbp+57h+var_68]; unsigned __int16 *
0x1800af0fc  mov     rcx, rbx; this
0x1800af0ff  call    ?Initialize@CWxCallerIdentity@@QEAAJPEBG@Z; CWxCallerIdentity::Initialize(ushort const *)
0x1800af104  mov     edi, eax
0x1800af106  test    eax, eax
0x1800af108  js      short loc_1800AF17D
0x1800af10a  mov     r8, [rbp+57h+var_70]; unsigned __int64
0x1800af10e  lea     rax, [rbp+57h+var_88]
0x1800af112  mov     [rsp+0C0h+var_98], rax; int *
0x1800af117  mov     r9, rbx; struct CWxCallerIdentity *
0x1800af11a  mov     rax, [rbp+57h+var_58]
0x1800af11e  mov     rdx, r14; struct CCacheStore *
0x1800af121  mov     rcx, r15; this
0x1800af124  mov     qword ptr [rsp+0C0h+grbit], rax; unsigned __int16 *
0x1800af129  call    ?BlobDeleteObsoleteContainerIfCanaryDeleted@CBlobStore@@QEAAJPEAVCCacheStore@@_KPEAVCWxCallerIdentity@@PEBGPEAH@Z; CBlobStore::BlobDeleteObsoleteContainerIfCanaryDeleted(CCacheStore *,unsigned __int64,CWxCallerIdentity *,ushort const *,int *)
0x1800af12e  mov     edi, eax
0x1800af130  test    eax, eax
0x1800af132  js      short loc_1800AF174
0x1800af134  cmp     [rbp+57h+var_88], r12d
0x1800af138  jnz     short loc_1800AF152
0x1800af13a  mov     r8, [rbp+57h+var_70]; unsigned __int64
0x1800af13e  mov     r9, rbx; struct CWxCallerIdentity *
0x1800af141  mov     rdx, r14; struct CCacheStore *
0x1800af144  mov     rcx, r15; this
0x1800af147  call    ?BlobPurgeExpiredEntriesInTable@CBlobStore@@QEAAJPEAVCCacheStore@@_KPEAVCWxCallerIdentity@@@Z; CBlobStore::BlobPurgeExpiredEntriesInTable(CCacheStore *,unsigned __int64,CWxCallerIdentity *)
0x1800af14c  mov     edi, eax
0x1800af14e  test    eax, eax
0x1800af150  js      short loc_1800AF16B
0x1800af152  mov     rdx, [rsi+20h]; tableid
0x1800af156  xor     r9d, r9d; grbit
0x1800af159  mov     rcx, [rsi+10h]; sesid
0x1800af15d  mov     r8d, r13d; cRow
0x1800af160  call    cs:__imp_JetMove
0x1800af166  jmp     loc_1800AEFDD
0x1800af16b  mov     [rbp+57h+var_84], 197h
0x1800af172  jmp     short loc_1800AF1B9
0x1800af174  mov     [rbp+57h+var_84], 191h
0x1800af17b  jmp     short loc_1800AF1B9
0x1800af17d  mov     [rbp+57h+var_84], 18Bh
0x1800af184  jmp     short loc_1800AF1B9
0x1800af186  mov     rbx, r12
0x1800af189  mov     [rbp+57h+var_84], 18Ah
0x1800af190  mov     edi, 8007000Eh
0x1800af195  jmp     short loc_1800AF1B9
0x1800af197  mov     [rbp+57h+var_84], 182h
0x1800af19e  jmp     short loc_1800AF1B9
0x1800af1a0  mov     [rbp+57h+var_84], 180h
0x1800af1a7  jmp     short loc_1800AF1B9
0x1800af1a9  mov     [rbp+57h+var_84], 17Eh
0x1800af1b0  jmp     short loc_1800AF1B9
0x1800af1b2  mov     [rbp+57h+var_84], 175h
0x1800af1b9  mov     rcx, [rsi+10h]; sesid
0x1800af1bd  xor     edx, edx; grbit
0x1800af1bf  call    cs:__imp_JetRollback
0x1800af1c5  test    rsi, rsi
0x1800af1c8  jz      short loc_1800AF1DA
0x1800af1ca  mov     rcx, [r14+1B8h]; this
0x1800af1d1  lea     rdx, [rbp+57h+var_90]; struct CJetContext **
0x1800af1d5  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x1800af1da  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800af1e1  jz      short loc_1800AF1FC
0x1800af1e3  mov     edx, 15h
0x1800af1e8  lea     r8, WPP_5a95f2a397ca3ed9078c668ec868fb04_Traceguids
0x1800af1ef  mov     ecx, 40Ch
0x1800af1f4  mov     r9d, edi
0x1800af1f7  call    WPP_SF_d
0x1800af1fc  test    rbx, rbx
0x1800af1ff  jz      short loc_1800AF209
0x1800af201  mov     rcx, rbx; this
0x1800af204  call    ?Release@CWxCallerIdentity@@QEAAKXZ; CWxCallerIdentity::Release(void)
0x1800af209  lea     rcx, [rbp+57h+var_68]; this
0x1800af20d  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800af212  lea     rcx, [rbp+57h+var_58]; this
0x1800af216  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800af21b  mov     eax, edi
0x1800af21d  mov     rcx, [rbp+57h+var_40]
0x1800af221  xor     rcx, rsp; StackCookie
0x1800af224  call    __security_check_cookie
0x1800af229  mov     rbx, [rsp+0C0h+arg_10]
0x1800af231  add     rsp, 90h
0x1800af238  pop     r15
0x1800af23a  pop     r14
0x1800af23c  pop     r13
0x1800af23e  pop     r12
0x1800af240  pop     rdi
0x1800af241  pop     rsi
0x1800af242  pop     rbp
0x1800af243  retn
```
