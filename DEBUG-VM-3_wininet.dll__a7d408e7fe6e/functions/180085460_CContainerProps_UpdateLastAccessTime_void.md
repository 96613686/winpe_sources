# CContainerProps::UpdateLastAccessTime(void)

- ea: `0x180085460`
- end: `0x180085890`
- name: `?UpdateLastAccessTime@CContainerProps@@QEAAJXZ`
- size: `1072`
- prototype: `__int64 __fastcall(CContainerProps *__hidden this)`
- caller_count: `20`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180023044`
- `0x180041bf0`
- `0x18007c810`
- `0x1800827a0`
- `0x180082cc0`
- `0x1800841e0`
- `0x1800863ac`
- `0x1800ab4ac`
- `0x1800f0a34`
- `0x1800f1644`
- `0x1801a52ec`
- `0x1801a55b8`
- `0x1801a5668`
- `0x1801a5788`
- `0x1801a5af8`
- `0x1801a5c88`
- `0x1801a5d70`
- `0x1801a5e74`
- `0x1801a5f34`
- `0x1801a675c`

## callees

- `0x18007ec9c`
- `0x180083dc4`
- `0x180085460`
- `0x180085924`
- `0x180086aa4`
- `0x1800eed94`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e1b60`
- `0x1801e3c24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085590`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800855ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085644`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085590`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800855ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180085644`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800854dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085544`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085603`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800854dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085544`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180085603`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800854ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800854ca`
- `ESENT!JetSetCurrentIndex2W` at `0x1800857ee`
- `ESENT!JetSetCurrentIndex2W` at `0x1800857ee`
- `ESENT!JetSetColumn` at `0x180085772`
- `ESENT!JetSetColumn` at `0x180085772`
- `ESENT!JetCommitTransaction` at `0x1800857b8`
- `ESENT!JetCommitTransaction` at `0x1800857b8`
- `ESENT!JetUpdate` at `0x180085795`
- `ESENT!JetUpdate` at `0x180085795`
- `ESENT!JetPrepareUpdate` at `0x180085726`
- `ESENT!JetPrepareUpdate` at `0x180085821`
- `ESENT!JetPrepareUpdate` at `0x180085726`
- `ESENT!JetPrepareUpdate` at `0x180085821`
- `ESENT!JetRollback` at `0x18008582d`
- `ESENT!JetRollback` at `0x18008582d`
- `ESENT!JetBeginTransaction` at `0x1800856e0`
- `ESENT!JetBeginTransaction` at `0x1800856e0`

## pseudocode

```c
__int64 __fastcall CContainerProps::UpdateLastAccessTime(CContainerProps *this)
{
  int v1; // r15d
  struct _RTL_CRITICAL_SECTION *v2; // r12
  struct CJetContext *v3; // rbx
  int v5; // r13d
  struct _FILETIME v6; // r14
  unsigned __int64 v7; // rcx
  JET_ERR v8; // edi
  char *v9; // rsi
  __int64 v10; // rsi
  __int64 v11; // rbp
  int v12; // eax
  int v13; // eax
  int v15; // r14d
  int v16; // eax
  int v17; // edx
  int v18; // ecx
  int v19; // r8d
  JET_ERR v20; // eax
  int v21; // eax
  JET_ERR v22; // eax
  JET_ERR v23; // eax
  JET_ERR v24; // eax
  JET_TABLEID v25; // rdx
  JET_SESID v26; // rcx
  JET_ERR v27; // eax
  struct CJetContext *v28; // [rsp+40h] [rbp-68h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-60h] BYREF
  struct _FILETIME pvData; // [rsp+50h] [rbp-58h] BYREF

  v1 = 0;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  v3 = 0;
  SystemTimeAsFileTime.dwHighDateTime = 0;
  v28 = 0;
  v5 = 0;
  pvData = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_q(1036, 37, &WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids, this);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v6 = SystemTimeAsFileTime;
  if ( v2 )
  {
    EnterCriticalSection(v2);
    v5 = 1;
  }
  v7 = *((_QWORD *)this + 27);
  if ( *(_QWORD *)&v6 > v7 && *(_QWORD *)&v6 - v7 < 0xC92A69C000LL )
  {
    v8 = 0;
    v9 = (char *)this + 24;
    goto LABEL_8;
  }
  v9 = (char *)this + 24;
  v16 = CJetContextList::AcquireContext(*(CJetContextList **)(*((_QWORD *)this + 3) + 320LL), &v28, 0);
  v3 = v28;
  v8 = v16;
  if ( v16 < 0 )
  {
    SystemTimeAsFileTime.dwHighDateTime = 1482;
  }
  else
  {
    HIDWORD(v28) = 0;
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      WPP_SF_qdSD(v18, v17, v19, (_DWORD)v3, 0, (__int64)L"ContainerIdIndex", 0);
    if ( *((_DWORD *)v3 + 12) )
    {
      v25 = *((_QWORD *)v3 + 4);
      v26 = *((_QWORD *)v3 + 2);
      *((_DWORD *)v3 + 12) = -1;
      v27 = JetSetCurrentIndex2W(v26, v25, L"ContainerIdIndex", 0);
      v8 = HRESULTFromJET_ERR(v27, 1);
      if ( v8 >= 0 )
        *((_DWORD *)v3 + 12) = 0;
    }
    else
    {
      v8 = 0;
    }
    if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
      WPP_SF_d(1036, 14, &WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids, (unsigned int)v8);
    if ( v8 >= 0 )
    {
      v20 = JetBeginTransaction(*((_QWORD *)v3 + 2));
      v8 = HRESULTFromJET_ERR(v20, 1);
      if ( v8 < 0 )
        goto LABEL_8;
      v21 = SeekToContainer(v3, *((_QWORD *)this + 1));
      v8 = v21;
      if ( v21 < 0 )
      {
        SystemTimeAsFileTime.dwHighDateTime = 1494;
      }
      else if ( v21 )
      {
        v8 = -2147418113;
        SystemTimeAsFileTime.dwHighDateTime = 1496;
      }
      else
      {
        v22 = JetPrepareUpdate(*((_QWORD *)v3 + 2), *((_QWORD *)v3 + 4), 2u);
        v8 = HRESULTFromJET_ERR(v22, 1);
        if ( v8 >= 0 )
        {
          pvData = v6;
          v8 = JetSetColumn(
                 *((_QWORD *)v3 + 2),
                 *((_QWORD *)v3 + 4),
                 *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v3 + 5) + 8LL) + 52LL),
                 &pvData,
                 8u,
                 0,
                 0);
          if ( v8 < 0 )
          {
            SystemTimeAsFileTime.dwHighDateTime = 1503;
          }
          else
          {
            v23 = JetUpdate(*((_QWORD *)v3 + 2), *((_QWORD *)v3 + 4), 0, 0, 0);
            v8 = HRESULTFromJET_ERR(v23, 1);
            if ( v8 >= 0 )
            {
              v24 = JetCommitTransaction(*((_QWORD *)v3 + 2), 1u);
              v8 = HRESULTFromJET_ERR(v24, 1);
              if ( v8 >= 0 )
              {
                *((struct _FILETIME *)this + 27) = v6;
                goto LABEL_8;
              }
              goto LABEL_52;
            }
          }
          JetPrepareUpdate(*((_QWORD *)v3 + 2), *((_QWORD *)v3 + 4), 3u);
        }
      }
LABEL_52:
      JetRollback(*((_QWORD *)v3 + 2), 0);
      goto LABEL_8;
    }
    SystemTimeAsFileTime.dwHighDateTime = 1484;
  }
LABEL_8:
  v10 = *(_QWORD *)(*(_QWORD *)v9 + 320LL);
  if ( v3 )
  {
    v11 = *(_QWORD *)(v10 + 80);
    if ( *(_QWORD *)(v11 + 608) )
    {
      if ( v11 != -560 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 560));
        v1 = 1;
      }
      v12 = *(_DWORD *)(v11 + 600);
      if ( v12 )
      {
        v13 = v12 - 1;
        *(_DWORD *)(v11 + 600) = v13;
        if ( !v13 )
        {
          ++*(_DWORD *)(v11 + 604);
          if ( !*(_DWORD *)(v11 + 620) )
            CCacheStore::StartActivityTimer((CCacheStore *)v11);
        }
      }
      if ( v1 && v11 != -560 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 560));
    }
    *((_QWORD *)v3 + 1) = 0;
    v15 = 0;
    if ( v10 != -8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 8));
      v15 = 1;
    }
    --*(_DWORD *)(v10 + 60);
    if ( (unsigned int)(*(_DWORD *)(v10 + 56) - *(_DWORD *)(v10 + 60)) > *(_DWORD *)(v10 + 64) )
    {
      --*(_DWORD *)(v10 + 56);
      CJetContext::Release(v3);
    }
    else
    {
      *((_QWORD *)v3 + 1) = *(_QWORD *)(v10 + 48);
      *(_QWORD *)(v10 + 48) = v3;
    }
    if ( v15 && v10 != -8 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 8));
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 38, &WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids, (unsigned int)v8);
  if ( v5 && v2 )
    LeaveCriticalSection(v2);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180085460  push    rbx
0x180085462  push    rbp
0x180085463  push    rsi
0x180085464  push    rdi
0x180085465  push    r12
0x180085467  push    r13
0x180085469  push    r14
0x18008546b  push    r15
0x18008546d  sub     rsp, 68h
0x180085471  mov     rax, cs:__security_cookie
0x180085478  xor     rax, rsp
0x18008547b  mov     [rsp+0A8h+var_50], rax
0x180085480  xor     r15d, r15d
0x180085483  lea     r12, [rcx+20h]
0x180085487  mov     ebx, r15d
0x18008548a  mov     [rsp+0A8h+SystemTimeAsFileTime.dwHighDateTime], r15d
0x18008548f  mov     [rsp+0A8h+var_68], rbx
0x180085494  mov     rbp, rcx
0x180085497  mov     r13d, r15d
0x18008549a  mov     [rsp+0A8h+pvData], r15
0x18008549f  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800854a6  jz      short loc_1800854C0
0x1800854a8  lea     edx, [r15+25h]
0x1800854ac  mov     ecx, 40Ch
0x1800854b1  mov     r9, rbp
0x1800854b4  lea     r8, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids
0x1800854bb  call    WPP_SF_q
0x1800854c0  lea     rcx, [rsp+0A8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800854c5  mov     qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime], r15
0x1800854ca  call    cs:__imp_GetSystemTimeAsFileTime
0x1800854d0  mov     r14, qword ptr [rsp+0A8h+SystemTimeAsFileTime.dwLowDateTime]
0x1800854d5  test    r12, r12
0x1800854d8  jz      short loc_1800854E9
0x1800854da  mov     rcx, r12; lpCriticalSection
0x1800854dd  call    cs:__imp_EnterCriticalSection
0x1800854e3  mov     r13d, 1
0x1800854e9  mov     rcx, [rbp+0D8h]
0x1800854f0  cmp     r14, rcx
0x1800854f3  jbe     loc_18008564F
0x1800854f9  mov     rax, r14
0x1800854fc  sub     rax, rcx
0x1800854ff  mov     rcx, 0C92A69C000h
0x180085509  cmp     rax, rcx
0x18008550c  jnb     loc_18008564F
0x180085512  mov     edi, r15d
0x180085515  lea     rsi, [rbp+18h]
0x180085519  mov     rax, [rsi]
0x18008551c  mov     rsi, [rax+140h]
0x180085523  test    rbx, rbx
0x180085526  jz      short loc_18008559B
0x180085528  mov     rbp, [rsi+50h]
0x18008552c  cmp     [rbp+260h], r15
0x180085533  jz      short loc_180085596
0x180085535  lea     r14, [rbp+230h]
0x18008553c  test    r14, r14
0x18008553f  jz      short loc_180085550
0x180085541  mov     rcx, r14; lpCriticalSection
0x180085544  call    cs:__imp_EnterCriticalSection
0x18008554a  mov     r15d, 1
0x180085550  mov     eax, [rbp+258h]
0x180085556  test    eax, eax
0x180085558  jz      short loc_18008557C
0x18008555a  sub     eax, 1
0x18008555d  mov     [rbp+258h], eax
0x180085563  jnz     short loc_18008557C
0x180085565  inc     dword ptr [rbp+25Ch]
0x18008556b  cmp     dword ptr [rbp+26Ch], 0
0x180085572  jnz     short loc_18008557C
0x180085574  mov     rcx, rbp; this
0x180085577  call    ?StartActivityTimer@CCacheStore@@AEAAXXZ; CCacheStore::StartActivityTimer(void)
0x18008557c  test    r15d, r15d
0x18008557f  jz      loc_180085875
0x180085585  xor     r15d, r15d
0x180085588  test    r14, r14
0x18008558b  jz      short loc_180085596
0x18008558d  mov     rcx, r14; lpCriticalSection
0x180085590  call    cs:__imp_LeaveCriticalSection
0x180085596  test    rbx, rbx
0x180085599  jnz     short loc_1800855F0
0x18008559b  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800855a2  jz      short loc_1800855BD
0x1800855a4  mov     edx, 26h ; '&'
0x1800855a9  lea     r8, WPP_4b302e6b786c3b7f389fd4681ef43772_Traceguids
0x1800855b0  mov     ecx, 40Ch
0x1800855b5  mov     r9d, edi
0x1800855b8  call    WPP_SF_d
0x1800855bd  test    r13d, r13d
0x1800855c0  jz      short loc_1800855D0
0x1800855c2  test    r12, r12
0x1800855c5  jz      short loc_1800855D0
0x1800855c7  mov     rcx, r12; lpCriticalSection
0x1800855ca  call    cs:__imp_LeaveCriticalSection
0x1800855d0  mov     eax, edi
0x1800855d2  mov     rcx, [rsp+0A8h+var_50]
0x1800855d7  xor     rcx, rsp; StackCookie
0x1800855da  call    __security_check_cookie
0x1800855df  add     rsp, 68h
0x1800855e3  pop     r15
0x1800855e5  pop     r14
0x1800855e7  pop     r13
0x1800855e9  pop     r12
0x1800855eb  pop     rdi
0x1800855ec  pop     rsi
0x1800855ed  pop     rbp
0x1800855ee  pop     rbx
0x1800855ef  retn
0x1800855f0  lea     rbp, [rsi+8]
0x1800855f4  mov     [rbx+8], r15
0x1800855f8  mov     r14d, r15d
0x1800855fb  test    rbp, rbp
0x1800855fe  jz      short loc_18008560F
0x180085600  mov     rcx, rbp; lpCriticalSection
0x180085603  call    cs:__imp_EnterCriticalSection
0x180085609  mov     r14d, 1
0x18008560f  dec     dword ptr [rsi+3Ch]
0x180085612  mov     ecx, [rsi+38h]
0x180085615  mov     eax, ecx
0x180085617  sub     eax, [rsi+3Ch]
0x18008561a  cmp     eax, [rsi+40h]
0x18008561d  ja      loc_18008587D
0x180085623  mov     rax, [rsi+30h]
0x180085627  mov     [rbx+8], rax
0x18008562b  mov     [rsi+30h], rbx
0x18008562f  test    r14d, r14d
0x180085632  jz      loc_18008559B
0x180085638  test    rbp, rbp
0x18008563b  jz      loc_18008559B
0x180085641  mov     rcx, rbp; lpCriticalSection
0x180085644  call    cs:__imp_LeaveCriticalSection
0x18008564a  jmp     loc_18008559B
0x18008564f  lea     rsi, [rbp+18h]
0x180085653  xor     r8d, r8d; int *
0x180085656  mov     rcx, [rsi]
0x180085659  lea     rdx, [rsp+0A8h+var_68]; struct CJetContext **
0x18008565e  mov     rcx, [rcx+140h]; this
0x180085665  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x18008566a  mov     rbx, [rsp+0A8h+var_68]
0x18008566f  mov     edi, eax
0x180085671  test    eax, eax
0x180085673  js      loc_180085838
0x180085679  mov     dword ptr [rsp+0A8h+var_68+4], r15d
0x18008567e  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180085685  lea     rdi, aContaineridind; "ContainerIdIndex"
0x18008568c  jz      short loc_1800856A5
0x18008568e  mov     dword ptr [rsp+0A8h+psetinfo], r15d
0x180085693  mov     r9, rbx
0x180085696  mov     qword ptr [rsp+0A8h+grbit], rdi
0x18008569b  mov     [rsp+0A8h+cbData], r15d
0x1800856a0  call    WPP_SF_qdSD
0x1800856a5  cmp     [rbx+30h], r15d
0x1800856a9  jnz     loc_1800857D9
0x1800856af  mov     edi, r15d
0x1800856b2  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800856b9  jz      short loc_1800856D4
0x1800856bb  mov     edx, 0Eh
0x1800856c0  lea     r8, WPP_c1dbdd081f6d3c4ce3e29e685ae804c4_Traceguids
0x1800856c7  mov     ecx, 40Ch
0x1800856cc  mov     r9d, edi
0x1800856cf  call    WPP_SF_d
0x1800856d4  test    edi, edi
0x1800856d6  js      loc_180085845
0x1800856dc  mov     rcx, [rbx+10h]; sesid
0x1800856e0  call    cs:__imp_JetBeginTransaction
0x1800856e6  mov     ecx, eax; int
0x1800856e8  mov     edx, 1; int
0x1800856ed  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800856f2  mov     edi, eax
0x1800856f4  test    eax, eax
0x1800856f6  js      loc_180085519
0x1800856fc  mov     rdx, [rbp+8]; unsigned __int64
0x180085700  mov     rcx, rbx; struct CJetContext *
0x180085703  call    ?SeekToContainer@@YAJPEAVCJetContext@@_K@Z; SeekToContainer(CJetContext *,unsigned __int64)
0x180085708  mov     edi, eax
0x18008570a  test    eax, eax
0x18008570c  js      loc_180085852
0x180085712  jnz     loc_18008585C
0x180085718  mov     rdx, [rbx+20h]; tableid
0x18008571c  mov     r8d, 2; prep
0x180085722  mov     rcx, [rbx+10h]; sesid
0x180085726  call    cs:__imp_JetPrepareUpdate
0x18008572c  mov     ecx, eax; int
0x18008572e  mov     edx, 1; int
0x180085733  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180085738  mov     edi, eax
0x18008573a  test    eax, eax
0x18008573c  js      loc_180085827
0x180085742  mov     [rsp+0A8h+pvData], r14
0x180085747  lea     r9, [rsp+0A8h+pvData]; pvData
0x18008574c  mov     rax, [rbx+28h]
0x180085750  mov     rdx, [rbx+20h]; tableid
0x180085754  mov     rcx, [rbx+10h]; sesid
0x180085758  mov     [rsp+0A8h+psetinfo], r15; psetinfo
0x18008575d  mov     r8, [rax+8]
0x180085761  mov     [rsp+0A8h+grbit], r15d; grbit
0x180085766  mov     [rsp+0A8h+cbData], 8; cbData
0x18008576e  mov     r8d, [r8+34h]; columnid
0x180085772  call    cs:__imp_JetSetColumn
0x180085778  mov     edi, eax
0x18008577a  test    eax, eax
0x18008577c  js      loc_18008586B
0x180085782  mov     rdx, [rbx+20h]; tableid
0x180085786  xor     r9d, r9d; cbBookmark
0x180085789  mov     rcx, [rbx+10h]; sesid
0x18008578d  xor     r8d, r8d; pvBookmark
0x180085790  mov     qword ptr [rsp+0A8h+cbData], r15; pcbActual
0x180085795  call    cs:__imp_JetUpdate
0x18008579b  mov     ecx, eax; int
0x18008579d  mov     edx, 1; int
0x1800857a2  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800857a7  mov     edi, eax
0x1800857a9  test    eax, eax
0x1800857ab  js      short loc_180085813
0x1800857ad  mov     rcx, [rbx+10h]; sesid
0x1800857b1  mov     edi, 1
0x1800857b6  mov     edx, edi; grbit
0x1800857b8  call    cs:__imp_JetCommitTransaction
0x1800857be  mov     ecx, eax; int
0x1800857c0  mov     edx, edi; int
0x1800857c2  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800857c7  mov     edi, eax
0x1800857c9  test    eax, eax
0x1800857cb  js      short loc_180085827
0x1800857cd  mov     [rbp+0D8h], r14
0x1800857d4  jmp     loc_180085519
0x1800857d9  mov     rdx, [rbx+20h]; tableid
0x1800857dd  xor     r9d, r9d; grbit
0x1800857e0  mov     rcx, [rbx+10h]; sesid
0x1800857e4  mov     r8, rdi; szIndexName
0x1800857e7  mov     dword ptr [rbx+30h], 0FFFFFFFFh
0x1800857ee  call    cs:__imp_JetSetCurrentIndex2W
0x1800857f4  mov     ecx, eax; int
0x1800857f6  mov     edx, 1; int
0x1800857fb  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x180085800  mov     edi, eax
0x180085802  test    eax, eax
0x180085804  js      loc_1800856B2
0x18008580a  mov     [rbx+30h], r15d
0x18008580e  jmp     loc_1800856B2
0x180085813  mov     rdx, [rbx+20h]; tableid
0x180085817  mov     r8d, 3; prep
0x18008581d  mov     rcx, [rbx+10h]; sesid
0x180085821  call    cs:__imp_JetPrepareUpdate
0x180085827  mov     rcx, [rbx+10h]; sesid
0x18008582b  xor     edx, edx; grbit
0x18008582d  call    cs:__imp_JetRollback
0x180085833  jmp     loc_180085519
0x180085838  mov     [rsp+0A8h+SystemTimeAsFileTime.dwHighDateTime], 5CAh
0x180085840  jmp     loc_180085519
0x180085845  mov     [rsp+0A8h+SystemTimeAsFileTime.dwHighDateTime], 5CCh
0x18008584d  jmp     loc_180085519
0x180085852  mov     [rsp+0A8h+SystemTimeAsFileTime.dwHighDateTime], 5D6h
0x18008585a  jmp     short loc_180085827
0x18008585c  mov     edi, 8000FFFFh
0x180085861  mov     [rsp+0A8h+SystemTimeAsFileTime.dwHighDateTime], 5D8h
0x180085869  jmp     short loc_180085827
0x18008586b  mov     [rsp+0A8h+SystemTimeAsFileTime.dwHighDateTime], 5DFh
0x180085873  jmp     short loc_180085813
0x180085875  xor     r15d, r15d
0x180085878  jmp     loc_180085596
0x18008587d  lea     eax, [rcx-1]
0x180085880  mov     rcx, rbx; this
0x180085883  mov     [rsi+38h], eax
0x180085886  call    ?Release@CJetContext@@QEAAKXZ; CJetContext::Release(void)
0x18008588b  jmp     loc_18008562F
```
