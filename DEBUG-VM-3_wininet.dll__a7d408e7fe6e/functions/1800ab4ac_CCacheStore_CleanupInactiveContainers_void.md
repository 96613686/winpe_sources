# CCacheStore::CleanupInactiveContainers(void)

- ea: `0x1800ab4ac`
- end: `0x1800aba88`
- name: `?CleanupInactiveContainers@CCacheStore@@AEAAJXZ`
- size: `1500`
- prototype: `__int64 __fastcall(CCacheStore *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, installer_update`

## callers

- `0x1800aea70`

## callees

- `0x1800201a0`
- `0x180021414`
- `0x180021e38`
- `0x180025910`
- `0x18007ec9c`
- `0x180083dc4`
- `0x180085460`
- `0x180086300`
- `0x1800a9974`
- `0x1800ab4ac`
- `0x1800aca44`
- `0x1800acab8`
- `0x1800acdb0`
- `0x1800b64b0`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e25fc`
- `0x1801e3c78`
- `0x1801e4988`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ab8f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ab8f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ab8c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ab8c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ab80b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ab80b`
- `ESENT!JetRetrieveColumn` at `0x1800ab641`
- `ESENT!JetRetrieveColumn` at `0x1800ab701`
- `ESENT!JetRetrieveColumn` at `0x1800ab7b9`
- `ESENT!JetRetrieveColumn` at `0x1800ab641`
- `ESENT!JetRetrieveColumn` at `0x1800ab701`
- `ESENT!JetRetrieveColumn` at `0x1800ab7b9`
- `ESENT!JetRollback` at `0x1800aba5b`
- `ESENT!JetRollback` at `0x1800aba5b`
- `ESENT!JetBeginTransaction` at `0x1800ab56b`
- `ESENT!JetBeginTransaction` at `0x1800ab56b`
- `ESENT!JetMove` at `0x1800ab5ab`
- `ESENT!JetMove` at `0x1800ab5ab`

## pseudocode

```c
__int64 __fastcall CCacheStore::CleanupInactiveContainers(CCacheStore *this)
{
  int v1; // r12d
  int v2; // r13d
  JET_SESID *v3; // r15
  int v5; // eax
  int updated; // ebx
  JET_ERR v7; // eax
  int i; // edi
  JET_ERR v9; // eax
  JET_ERR v10; // eax
  char v11; // al
  JET_ERR v12; // eax
  char v13; // al
  JET_ERR v14; // eax
  CCacheStore *v15; // rcx
  const unsigned __int16 *v16; // r8
  CContainerProps *v17; // rdi
  unsigned int *pcbActual; // [rsp+28h] [rbp-71h]
  struct CJetContext *v21; // [rsp+48h] [rbp-51h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-49h] BYREF
  CContainerProps *v23; // [rsp+60h] [rbp-39h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-31h] BYREF
  int pvData; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int64 v26; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int64 v27; // [rsp+80h] [rbp-19h] BYREF
  unsigned __int16 *v28[2]; // [rsp+88h] [rbp-11h] BYREF
  _QWORD v29[2]; // [rsp+98h] [rbp-1h] BYREF

  v1 = 0;
  SystemTimeAsFileTime.dwHighDateTime = 0;
  v2 = 0;
  v22[0] = &Data;
  v3 = 0;
  v22[1] = 0;
  v28[0] = (unsigned __int16 *)&Data;
  v28[1] = 0;
  v21 = 0;
  v27 = 0;
  pvData = 0;
  v26 = 0;
  v23 = 0;
  v29[0] = &Data;
  v29[1] = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_(1036, 61, &WPP_97d300ac1e463af99b9229d7a7cae1bf_Traceguids);
  if ( (unsigned int)CCacheStore::IsTerminating(this) || !*((_DWORD *)this + 91) )
  {
    updated = 0;
  }
  else
  {
    v5 = CJetContextList::AcquireContext(*((CJetContextList **)this + 40), &v21, 0);
    v3 = (JET_SESID *)v21;
    updated = v5;
    if ( v5 < 0 )
    {
      SystemTimeAsFileTime.dwHighDateTime = 2724;
    }
    else
    {
      v7 = JetBeginTransaction(*((_QWORD *)v21 + 2));
      updated = HRESULTFromJET_ERR(v7, 1);
      if ( updated >= 0 )
      {
        v2 = 1;
        for ( i = 0x80000000; !(unsigned int)CCacheStore::IsTerminating(this); i = 1 )
        {
          v9 = JetMove(v3[2], v3[4], i, 0);
          if ( v9 == -1603 )
            break;
          updated = HRESULTFromJET_ERR(v9, 1);
          if ( updated < 0 )
            break;
          SystemTimeAsFileTime.dwLowDateTime = 0;
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            WPP_SF_dqd(1036, 17, (unsigned int)&WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 4, (__int64)&pvData);
          v10 = JetRetrieveColumn(
                  v3[2],
                  v3[4],
                  *(_DWORD *)(*(_QWORD *)(v3[5] + 8) + 16LL),
                  &pvData,
                  4u,
                  (unsigned int *)&SystemTimeAsFileTime,
                  0,
                  0);
          updated = HRESULTFromJET_ERR(v10, 1);
          if ( updated >= 0 )
          {
            if ( SystemTimeAsFileTime.dwLowDateTime == 4 )
              updated = 0;
            else
              updated = -2147418113;
          }
          v11 = BYTE1(xmmword_180266B60);
          if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
          {
            WPP_SF_d(1036, 18, &WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)updated);
            v11 = BYTE1(xmmword_180266B60);
          }
          if ( updated < 0 )
          {
            SystemTimeAsFileTime.dwHighDateTime = 2750;
            break;
          }
          if ( (pvData & 8) != 0 )
          {
            SystemTimeAsFileTime.dwLowDateTime = 0;
            if ( (v11 & 0x10) != 0 )
              WPP_SF_dqd(1036, 17, (unsigned int)&WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 0, (__int64)&v27);
            v12 = JetRetrieveColumn(
                    v3[2],
                    v3[4],
                    **(_DWORD **)(v3[5] + 8),
                    &v27,
                    8u,
                    (unsigned int *)&SystemTimeAsFileTime,
                    0,
                    0);
            updated = HRESULTFromJET_ERR(v12, 1);
            if ( updated >= 0 )
            {
              if ( SystemTimeAsFileTime.dwLowDateTime == 8 )
                updated = 0;
              else
                updated = -2147418113;
            }
            v13 = BYTE1(xmmword_180266B60);
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
            {
              WPP_SF_d(1036, 18, &WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)updated);
              v13 = BYTE1(xmmword_180266B60);
            }
            if ( updated < 0 )
            {
              SystemTimeAsFileTime.dwHighDateTime = 2756;
              break;
            }
            SystemTimeAsFileTime.dwLowDateTime = 0;
            if ( (v13 & 0x10) != 0 )
              WPP_SF_dqd(1036, 17, (unsigned int)&WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, 13, (__int64)&v26);
            v14 = JetRetrieveColumn(
                    v3[2],
                    v3[4],
                    *(_DWORD *)(*(_QWORD *)(v3[5] + 8) + 52LL),
                    &v26,
                    8u,
                    (unsigned int *)&SystemTimeAsFileTime,
                    0,
                    0);
            updated = HRESULTFromJET_ERR(v14, 1);
            if ( updated >= 0 )
            {
              if ( SystemTimeAsFileTime.dwLowDateTime == 8 )
                updated = 0;
              else
                updated = -2147418113;
            }
            if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
              WPP_SF_d(1036, 18, &WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)updated);
            if ( updated < 0 )
            {
              SystemTimeAsFileTime.dwHighDateTime = 2757;
              break;
            }
            SystemTimeAsFileTime = 0;
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
            if ( v26 > *(_QWORD *)&SystemTimeAsFileTime )
            {
              updated = CCacheStore::AcquireContainerProps(this, v27, &v23);
              if ( updated < 0 )
              {
                SystemTimeAsFileTime.dwHighDateTime = 2769;
                break;
              }
              updated = CContainerProps::UpdateLastAccessTime(v23);
              if ( updated < 0 )
              {
                SystemTimeAsFileTime.dwHighDateTime = 2770;
                break;
              }
              CCacheStore::ReleaseContainerProps(this, &v23);
            }
            else if ( (*(_QWORD *)&SystemTimeAsFileTime - v26) / 0x989680 >= *((unsigned int *)this + 91) )
            {
              updated = CJetContext::GetStringColumn((CJetContext *)v3, 7u, (struct CWxString *)v29);
              if ( updated < 0 )
              {
                SystemTimeAsFileTime.dwHighDateTime = 2787;
                break;
              }
              updated = CJetContext::GetStringColumn((CJetContext *)v3, 1u, (struct CWxString *)v28);
              if ( updated < 0 )
              {
                SystemTimeAsFileTime.dwHighDateTime = 2789;
                break;
              }
              if ( (unsigned int)CCacheStore::IsPartitionOffline(v15, v28[0], v16) )
              {
                updated = CCacheStore::CleanupContainer(this, v27, 0x64u, 0, 0, (struct CACHE_CLEANUP_STATS *)pcbActual);
                if ( updated < 0 )
                {
                  SystemTimeAsFileTime.dwHighDateTime = 2799;
                  break;
                }
              }
            }
          }
        }
      }
    }
  }
  v17 = v23;
  if ( v23 )
  {
    v23 = 0;
    if ( this != (CCacheStore *)-280LL )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)this + 7);
      v1 = 1;
    }
    if ( (*((_DWORD *)v17 + 4))-- == 1 )
      CWxRefMap<CContainerPropsMap,CContainerProps>::Delete(*((_QWORD *)this + 41), v17);
    CContainerProps::Release(v17);
    if ( v1 && this != (CCacheStore *)-280LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)this + 7);
  }
  if ( v2 )
    JetRollback(v3[2], 0);
  CCacheStore::ReleaseContainerContext(this, &v21);
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qD(1036, 62, &WPP_97d300ac1e463af99b9229d7a7cae1bf_Traceguids, this, updated);
  CWxString::_Release((CWxString *)v29);
  CWxString::_Release((CWxString *)v28);
  CWxString::_Release((CWxString *)v22);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800ab4ac  push    rbp
0x1800ab4ae  push    rbx
0x1800ab4af  push    rsi
0x1800ab4b0  push    rdi
0x1800ab4b1  push    r12
0x1800ab4b3  push    r13
0x1800ab4b5  push    r14
0x1800ab4b7  push    r15
0x1800ab4b9  lea     rbp, [rsp-1Fh]
0x1800ab4be  sub     rsp, 0B8h
0x1800ab4c5  mov     rax, cs:__security_cookie
0x1800ab4cc  xor     rax, rsp
0x1800ab4cf  mov     [rbp+57h+var_48], rax
0x1800ab4d3  xor     r12d, r12d
0x1800ab4d6  lea     rax, Data
0x1800ab4dd  mov     [rbp+57h+SystemTimeAsFileTime.dwHighDateTime], r12d
0x1800ab4e1  mov     r13d, r12d
0x1800ab4e4  mov     [rbp+57h+var_A0], rax
0x1800ab4e8  mov     r15d, r12d
0x1800ab4eb  mov     [rbp+57h+var_98], r12
0x1800ab4ef  mov     rsi, rcx
0x1800ab4f2  mov     [rbp+57h+var_68], rax
0x1800ab4f6  mov     [rbp+57h+var_60], r12
0x1800ab4fa  mov     [rbp+57h+var_A8], r12
0x1800ab4fe  mov     [rbp+57h+var_70], r12
0x1800ab502  mov     [rbp+57h+pvData], r12d
0x1800ab506  mov     [rbp+57h+var_78], r12
0x1800ab50a  mov     [rbp+57h+var_90], r12
0x1800ab50e  mov     [rbp+57h+var_58], rax
0x1800ab512  mov     [rbp+57h+var_50], r12
0x1800ab516  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ab51d  jnz     loc_1800AB99C
0x1800ab523  mov     rcx, rsi; this
0x1800ab526  call    ?IsTerminating@CCacheStore@@QEAAHXZ; CCacheStore::IsTerminating(void)
0x1800ab52b  mov     r14d, 1
0x1800ab531  test    eax, eax
0x1800ab533  jnz     loc_1800AB9B7
0x1800ab539  cmp     [rsi+16Ch], r12d
0x1800ab540  jz      loc_1800AB9B7
0x1800ab546  mov     rcx, [rsi+140h]; this
0x1800ab54d  lea     rdx, [rbp+57h+var_A8]; struct CJetContext **
0x1800ab551  xor     r8d, r8d; int *
0x1800ab554  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1800ab559  mov     r15, [rbp+57h+var_A8]
0x1800ab55d  mov     ebx, eax
0x1800ab55f  test    eax, eax
0x1800ab561  js      loc_1800AB9BF
0x1800ab567  mov     rcx, [r15+10h]; sesid
0x1800ab56b  call    cs:__imp_JetBeginTransaction
0x1800ab571  mov     ecx, eax; int
0x1800ab573  mov     edx, r14d; int
0x1800ab576  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ab57b  mov     ebx, eax
0x1800ab57d  test    eax, eax
0x1800ab57f  js      loc_1800AB8AD
0x1800ab585  mov     r13d, r14d
0x1800ab588  mov     edi, 80000000h
0x1800ab58d  mov     rcx, rsi; this
0x1800ab590  call    ?IsTerminating@CCacheStore@@QEAAHXZ; CCacheStore::IsTerminating(void)
0x1800ab595  test    eax, eax
0x1800ab597  jnz     loc_1800AB8AD
0x1800ab59d  mov     rdx, [r15+20h]; tableid
0x1800ab5a1  xor     r9d, r9d; grbit
0x1800ab5a4  mov     rcx, [r15+10h]; sesid
0x1800ab5a8  mov     r8d, edi; cRow
0x1800ab5ab  call    cs:__imp_JetMove
0x1800ab5b1  cmp     eax, 0FFFFF9BDh
0x1800ab5b6  jz      loc_1800AB8AD
0x1800ab5bc  mov     edx, r14d; int
0x1800ab5bf  mov     ecx, eax; int
0x1800ab5c1  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ab5c6  mov     ebx, eax
0x1800ab5c8  test    eax, eax
0x1800ab5ca  js      loc_1800AB8AD
0x1800ab5d0  mov     [rbp+57h+var_AC], r12d
0x1800ab5d4  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r12d
0x1800ab5d8  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ab5df  mov     edi, 40Ch
0x1800ab5e4  jz      short loc_1800AB60E
0x1800ab5e6  mov     edx, 11h
0x1800ab5eb  lea     rax, [rbp+57h+pvData]
0x1800ab5ef  mov     ecx, edi
0x1800ab5f1  lea     r8d, [rdx-0Dh]
0x1800ab5f5  mov     dword ptr [rsp+0F0h+pcbActual], r8d
0x1800ab5fa  mov     r9d, r8d
0x1800ab5fd  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800ab604  mov     qword ptr [rsp+0F0h+cbData], rax
0x1800ab609  call    WPP_SF_dqd
0x1800ab60e  mov     rax, [r15+28h]
0x1800ab612  lea     r9, [rbp+57h+pvData]; pvData
0x1800ab616  mov     rdx, [r15+20h]; tableid
0x1800ab61a  mov     rcx, [r15+10h]; sesid
0x1800ab61e  mov     [rsp+0F0h+pretinfo], r12; pretinfo
0x1800ab623  mov     r8, [rax+8]
0x1800ab627  lea     rax, [rbp+57h+SystemTimeAsFileTime]
0x1800ab62b  mov     [rsp+0F0h+grbit], r12d; grbit
0x1800ab630  mov     [rsp+0F0h+pcbActual], rax; pcbActual
0x1800ab635  mov     [rsp+0F0h+cbData], 4; cbData
0x1800ab63d  mov     r8d, [r8+10h]; columnid
0x1800ab641  call    cs:__imp_JetRetrieveColumn
0x1800ab647  mov     ecx, eax; int
0x1800ab649  mov     edx, r14d; int
0x1800ab64c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ab651  mov     ebx, eax
0x1800ab653  test    eax, eax
0x1800ab655  js      short loc_1800AB664
0x1800ab657  cmp     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 4
0x1800ab65b  jnz     loc_1800AB969
0x1800ab661  mov     ebx, r12d
0x1800ab664  mov     al, byte ptr cs:xmmword_180266B60+1
0x1800ab66a  test    al, 10h
0x1800ab66c  jz      short loc_1800AB68A
0x1800ab66e  mov     edx, 12h
0x1800ab673  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800ab67a  mov     ecx, edi
0x1800ab67c  mov     r9d, ebx
0x1800ab67f  call    WPP_SF_d
0x1800ab684  mov     al, byte ptr cs:xmmword_180266B60+1
0x1800ab68a  test    ebx, ebx
0x1800ab68c  js      loc_1800ABA49
0x1800ab692  test    byte ptr [rbp+57h+pvData], 8
0x1800ab696  jz      loc_1800AB83F
0x1800ab69c  mov     [rbp+57h+var_AC], r12d
0x1800ab6a0  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r12d
0x1800ab6a4  test    al, 10h
0x1800ab6a6  jz      short loc_1800AB6CF
0x1800ab6a8  lea     rax, [rbp+57h+var_70]
0x1800ab6ac  mov     dword ptr [rsp+0F0h+pcbActual], 8
0x1800ab6b4  mov     edx, 11h
0x1800ab6b9  mov     qword ptr [rsp+0F0h+cbData], rax
0x1800ab6be  mov     ecx, edi
0x1800ab6c0  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800ab6c7  xor     r9d, r9d
0x1800ab6ca  call    WPP_SF_dqd
0x1800ab6cf  mov     rax, [r15+28h]
0x1800ab6d3  lea     r9, [rbp+57h+var_70]; pvData
0x1800ab6d7  mov     rdx, [r15+20h]; tableid
0x1800ab6db  mov     rcx, [r15+10h]; sesid
0x1800ab6df  mov     [rsp+0F0h+pretinfo], r12; pretinfo
0x1800ab6e4  mov     r8, [rax+8]
0x1800ab6e8  lea     rax, [rbp+57h+SystemTimeAsFileTime]
0x1800ab6ec  mov     [rsp+0F0h+grbit], r12d; grbit
0x1800ab6f1  mov     [rsp+0F0h+pcbActual], rax; pcbActual
0x1800ab6f6  mov     [rsp+0F0h+cbData], 8; cbData
0x1800ab6fe  mov     r8d, [r8]; columnid
0x1800ab701  call    cs:__imp_JetRetrieveColumn
0x1800ab707  mov     ecx, eax; int
0x1800ab709  mov     edx, r14d; int
0x1800ab70c  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ab711  mov     ebx, eax
0x1800ab713  test    eax, eax
0x1800ab715  js      short loc_1800AB724
0x1800ab717  cmp     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 8
0x1800ab71b  jnz     loc_1800AB97A
0x1800ab721  mov     ebx, r12d
0x1800ab724  mov     al, byte ptr cs:xmmword_180266B60+1
0x1800ab72a  test    al, 10h
0x1800ab72c  jz      short loc_1800AB74A
0x1800ab72e  mov     edx, 12h
0x1800ab733  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800ab73a  mov     ecx, edi
0x1800ab73c  mov     r9d, ebx
0x1800ab73f  call    WPP_SF_d
0x1800ab744  mov     al, byte ptr cs:xmmword_180266B60+1
0x1800ab74a  test    ebx, ebx
0x1800ab74c  js      loc_1800ABA3D
0x1800ab752  mov     [rbp+57h+var_AC], r12d
0x1800ab756  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r12d
0x1800ab75a  test    al, 10h
0x1800ab75c  jz      short loc_1800AB786
0x1800ab75e  mov     edx, 11h
0x1800ab763  mov     dword ptr [rsp+0F0h+pcbActual], 8
0x1800ab76b  lea     rax, [rbp+57h+var_78]
0x1800ab76f  mov     ecx, edi
0x1800ab771  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800ab778  mov     qword ptr [rsp+0F0h+cbData], rax
0x1800ab77d  lea     r9d, [rdx-4]
0x1800ab781  call    WPP_SF_dqd
0x1800ab786  mov     rax, [r15+28h]
0x1800ab78a  lea     r9, [rbp+57h+var_78]; pvData
0x1800ab78e  mov     rdx, [r15+20h]; tableid
0x1800ab792  mov     rcx, [r15+10h]; sesid
0x1800ab796  mov     [rsp+0F0h+pretinfo], r12; pretinfo
0x1800ab79b  mov     r8, [rax+8]
0x1800ab79f  lea     rax, [rbp+57h+SystemTimeAsFileTime]
0x1800ab7a3  mov     [rsp+0F0h+grbit], r12d; grbit
0x1800ab7a8  mov     [rsp+0F0h+pcbActual], rax; struct CACHE_CLEANUP_STATS *
0x1800ab7ad  mov     [rsp+0F0h+cbData], 8; cbData
0x1800ab7b5  mov     r8d, [r8+34h]; columnid
0x1800ab7b9  call    cs:__imp_JetRetrieveColumn
0x1800ab7bf  mov     ecx, eax; int
0x1800ab7c1  mov     edx, r14d; int
0x1800ab7c4  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800ab7c9  mov     ebx, eax
0x1800ab7cb  test    eax, eax
0x1800ab7cd  js      short loc_1800AB7DC
0x1800ab7cf  cmp     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 8
0x1800ab7d3  jnz     loc_1800AB98B
0x1800ab7d9  mov     ebx, r12d
0x1800ab7dc  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ab7e3  jz      short loc_1800AB7FB
0x1800ab7e5  mov     edx, 12h
0x1800ab7ea  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800ab7f1  mov     ecx, edi
0x1800ab7f3  mov     r9d, ebx
0x1800ab7f6  call    WPP_SF_d
0x1800ab7fb  test    ebx, ebx
0x1800ab7fd  js      loc_1800ABA31
0x1800ab803  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800ab807  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], r12
0x1800ab80b  call    cs:__imp_GetSystemTimeAsFileTime
0x1800ab811  mov     rcx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x1800ab815  cmp     [rbp+57h+var_78], rcx
0x1800ab819  ja      loc_1800AB9CB
0x1800ab81f  sub     rcx, [rbp+57h+var_78]
0x1800ab823  mov     rax, 0D6BF94D5E57A42BDh
0x1800ab82d  mul     rcx
0x1800ab830  mov     eax, [rsi+16Ch]
0x1800ab836  shr     rdx, 17h
0x1800ab83a  cmp     rdx, rax
0x1800ab83d  jnb     short loc_1800AB847
0x1800ab83f  mov     edi, r14d
0x1800ab842  jmp     loc_1800AB58D
0x1800ab847  lea     r8, [rbp+57h+var_58]; struct CWxString *
0x1800ab84b  mov     edx, 7; unsigned int
0x1800ab850  mov     rcx, r15; this
0x1800ab853  call    ?GetStringColumn@CJetContext@@QEAAJKPEAVCWxString@@@Z; CJetContext::GetStringColumn(ulong,CWxString *)
0x1800ab858  mov     ebx, eax
0x1800ab85a  test    eax, eax
0x1800ab85c  js      loc_1800ABA25
0x1800ab862  lea     r8, [rbp+57h+var_68]; struct CWxString *
0x1800ab866  mov     edx, r14d; unsigned int
0x1800ab869  mov     rcx, r15; this
0x1800ab86c  call    ?GetStringColumn@CJetContext@@QEAAJKPEAVCWxString@@@Z; CJetContext::GetStringColumn(ulong,CWxString *)
0x1800ab871  mov     ebx, eax
0x1800ab873  test    eax, eax
0x1800ab875  js      loc_1800ABA19
0x1800ab87b  mov     rdx, [rbp+57h+var_68]; unsigned __int16 *
0x1800ab87f  call    ?IsPartitionOffline@CCacheStore@@AEAAJPEBG0@Z; CCacheStore::IsPartitionOffline(ushort const *,ushort const *)
0x1800ab884  test    eax, eax
0x1800ab886  jz      short loc_1800AB83F
0x1800ab888  mov     rdx, [rbp+57h+var_70]; unsigned __int64
0x1800ab88c  xor     r9d, r9d; unsigned int
0x1800ab88f  mov     rcx, rsi; this
0x1800ab892  mov     [rsp+0F0h+cbData], r12d; int
0x1800ab897  lea     r8d, [r9+64h]; unsigned int
0x1800ab89b  call    ?CleanupContainer@CCacheStore@@QEAAJ_KKKHPEAUCACHE_CLEANUP_STATS@@@Z; CCacheStore::CleanupContainer(unsigned __int64,ulong,ulong,int,CACHE_CLEANUP_STATS *)
0x1800ab8a0  mov     ebx, eax
0x1800ab8a2  test    eax, eax
0x1800ab8a4  jns     short loc_1800AB83F
0x1800ab8a6  mov     [rbp+57h+SystemTimeAsFileTime.dwHighDateTime], 0AEFh
0x1800ab8ad  mov     rdi, [rbp+57h+var_90]
0x1800ab8b1  test    rdi, rdi
0x1800ab8b4  jz      short loc_1800AB8F6
0x1800ab8b6  lea     r14, [rsi+118h]
0x1800ab8bd  mov     [rbp+57h+var_90], r12
0x1800ab8c1  test    r14, r14
0x1800ab8c4  jz      short loc_1800AB8D5
0x1800ab8c6  mov     rcx, r14; lpCriticalSection
0x1800ab8c9  call    cs:__imp_EnterCriticalSection
0x1800ab8cf  mov     r12d, 1
0x1800ab8d5  add     dword ptr [rdi+10h], 0FFFFFFFFh
0x1800ab8d9  jz      short loc_1800AB955
0x1800ab8db  mov     rcx, rdi; this
0x1800ab8de  call    ?Release@CContainerProps@@QEAAKXZ; CContainerProps::Release(void)
0x1800ab8e3  test    r12d, r12d
0x1800ab8e6  jz      short loc_1800AB8F6
0x1800ab8e8  test    r14, r14
0x1800ab8eb  jz      short loc_1800AB8F6
0x1800ab8ed  mov     rcx, r14; lpCriticalSection
0x1800ab8f0  call    cs:__imp_LeaveCriticalSection
0x1800ab8f6  test    r13d, r13d
0x1800ab8f9  jnz     loc_1800ABA55
0x1800ab8ff  lea     rdx, [rbp+57h+var_A8]; struct CJetContext **
0x1800ab903  mov     rcx, rsi; this
0x1800ab906  call    ?ReleaseContainerContext@CCacheStore@@QEAAXPEAPEAVCJetContext@@@Z; CCacheStore::ReleaseContainerContext(CJetContext * *)
0x1800ab90b  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800ab912  jnz     loc_1800ABA66
0x1800ab918  lea     rcx, [rbp+57h+var_58]; this
0x1800ab91c  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800ab921  lea     rcx, [rbp+57h+var_68]; this
0x1800ab925  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800ab92a  lea     rcx, [rbp+57h+var_A0]; this
0x1800ab92e  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x1800ab933  mov     eax, ebx
0x1800ab935  mov     rcx, [rbp+57h+var_48]
0x1800ab939  xor     rcx, rsp; StackCookie
0x1800ab93c  call    __security_check_cookie
0x1800ab941  add     rsp, 0B8h
0x1800ab948  pop     r15
0x1800ab94a  pop     r14
0x1800ab94c  pop     r13
0x1800ab94e  pop     r12
0x1800ab950  pop     rdi
0x1800ab951  pop     rsi
0x1800ab952  pop     rbx
0x1800ab953  pop     rbp
0x1800ab954  retn
0x1800ab955  mov     rcx, [rsi+148h]
0x1800ab95c  mov     rdx, rdi
  ... truncated ...
```
