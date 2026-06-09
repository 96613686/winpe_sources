# CDateInfo::Create(ulong,ulong,CDateInfo * *,char * *)

- ea: `0x18002adc8`
- end: `0x18002b018`
- name: `?Create@CDateInfo@@SAJKKPEAPEAV1@PEAPEAD@Z`
- size: `592`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, struct CDateInfo **, char **)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18002ac34`

## callees

- `0x180025ce0`
- `0x18002adc8`
- `0x18002bddc`
- `0x180041ef8`
- `0x18004a8f4`
- `0x18004e530`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002af0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002af0f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002af23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002af23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002afff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002afff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ae3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ae3a`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x18002adec`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x18002adec`

## pseudocode

```c
__int64 __fastcall CDateInfo::Create(LCID a1, int a2, struct CDateInfo **a3, char **a4)
{
  struct CDateInfo *v4; // rbx
  struct CDateInfo **v6; // rdi
  int CacheUpdateCount; // r12d
  int v11; // ebp
  CDateInfo *v12; // rsi
  CDateInfo *v13; // rbx
  CDateInfo *v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rcx
  HANDLE ProcessHeap; // rax
  CDateInfo *v18; // rax
  CDateInfo *v19; // rdx
  CDateInfo *v20; // rax
  bool v21; // zf

  v4 = *a3;
  v6 = a3;
  CacheUpdateCount = NlsGetCacheUpdateCount();
  if ( v4
    && *((_DWORD *)v4 + 4) == a1
    && *((_DWORD *)v4 + 5) == a2
    && (!g_bPerUserNlsCache || !*a4 || (unsigned int)IsSameUser(*a4, *((char **)v4 + 1)))
    && *(_DWORD *)v4 == CacheUpdateCount )
  {
    return 0;
  }
  v11 = 0;
  EnterCriticalSection(&DateInfo_csCacheLock);
  v12 = CDateInfo::m_pDateInfoCache;
  v13 = CDateInfo::m_pDateInfoCache;
  if ( CDateInfo::m_pDateInfoCache )
  {
    while ( 1 )
    {
      if ( *((_DWORD *)v13 + 4) == a1
        && *((_DWORD *)v13 + 5) == a2
        && (!g_bPerUserNlsCache || !*a4 || (unsigned int)IsSameUser(*a4, *((char **)v13 + 1))) )
      {
        if ( *(_DWORD *)v13 == CacheUpdateCount )
        {
          v6 = a3;
          goto LABEL_35;
        }
        v14 = (CDateInfo *)*((_QWORD *)v13 + 407);
        if ( v13 == v14 )
        {
          CDateInfo::m_pDateInfoCache = 0;
          CDateInfo::Release(v13);
LABEL_27:
          v6 = a3;
          break;
        }
        v15 = *((_QWORD *)v13 + 408);
        if ( v15 )
          *(_QWORD *)(v15 + 3256) = v14;
        v16 = *((_QWORD *)v13 + 407);
        if ( v16 )
          *(_QWORD *)(v16 + 3264) = *((_QWORD *)v13 + 408);
        if ( CDateInfo::m_pDateInfoCache == v13 )
        {
          CDateInfo::m_pDateInfoCache = v14;
          v12 = v14;
        }
        CDateInfo::Release(v13);
        v13 = v14;
      }
      v13 = (CDateInfo *)*((_QWORD *)v13 + 407);
      if ( v13 == v12 )
        goto LABEL_27;
    }
  }
  InitializeUserCalendars();
  ProcessHeap = GetProcessHeap();
  v18 = (CDateInfo *)HeapAlloc(ProcessHeap, 8u, 0xCD0u);
  v13 = v18;
  if ( v18 )
  {
    memset_0(v18, 0, 0xCB8u);
    *((_QWORD *)v13 + 407) = 0;
    *((_QWORD *)v13 + 408) = 0;
    *((_DWORD *)v13 + 818) = 0;
    _InterlockedIncrement((volatile signed __int32 *)v13 + 818);
    v11 = CDateInfo::Init(v13, a1, a2, a4);
    if ( v11 >= 0 )
    {
      v19 = CDateInfo::m_pDateInfoCache;
      if ( CDateInfo::m_pDateInfoCache )
      {
        *((_QWORD *)v13 + 408) = *((_QWORD *)CDateInfo::m_pDateInfoCache + 408);
        *(_QWORD *)(*((_QWORD *)v19 + 408) + 3256LL) = v13;
        v20 = CDateInfo::m_pDateInfoCache;
        *((_QWORD *)v19 + 408) = v13;
        *((_QWORD *)v13 + 407) = v20;
      }
      else
      {
        *((_QWORD *)v13 + 407) = v13;
        *((_QWORD *)v13 + 408) = v13;
      }
      CDateInfo::m_pDateInfoCache = v13;
LABEL_35:
      _InterlockedIncrement((volatile signed __int32 *)v13 + 818);
      v21 = CDateInfo::m_pDateInfoCache == v13;
      *v6 = v13;
      if ( !v21 )
        CDateInfo::m_pDateInfoCache = v13;
    }
  }
  else
  {
    v11 = -2147024882;
  }
  LeaveCriticalSection(&DateInfo_csCacheLock);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002adc8  mov     [rsp+arg_10], r8
0x18002adcd  push    rbx
0x18002adce  push    rbp
0x18002adcf  push    rsi
0x18002add0  push    rdi
0x18002add1  push    r12
0x18002add3  push    r13
0x18002add5  push    r14
0x18002add7  push    r15
0x18002add9  sub     rsp, 28h
0x18002addd  mov     rbx, [r8]
0x18002ade0  mov     r13, r9
0x18002ade3  mov     rdi, r8
0x18002ade6  mov     r14d, edx
0x18002ade9  mov     r15d, ecx
0x18002adec  call    cs:__imp_NlsGetCacheUpdateCount
0x18002adf2  mov     r12d, eax
0x18002adf5  test    rbx, rbx
0x18002adf8  jz      short loc_18002AE31
0x18002adfa  cmp     [rbx+10h], r15d
0x18002adfe  jnz     short loc_18002AE31
0x18002ae00  cmp     [rbx+14h], r14d
0x18002ae04  jnz     short loc_18002AE31
0x18002ae06  cmp     cs:?g_bPerUserNlsCache@@3KA, 0; ulong g_bPerUserNlsCache
0x18002ae0d  jz      short loc_18002AE25
0x18002ae0f  mov     rcx, [r13+0]; char *
0x18002ae13  test    rcx, rcx
0x18002ae16  jz      short loc_18002AE25
0x18002ae18  mov     rdx, [rbx+8]; char *
0x18002ae1c  call    ?IsSameUser@@YAHPEAD0@Z; IsSameUser(char *,char *)
0x18002ae21  test    eax, eax
0x18002ae23  jz      short loc_18002AE31
0x18002ae25  cmp     [rbx], r12d
0x18002ae28  jnz     short loc_18002AE31
0x18002ae2a  xor     eax, eax
0x18002ae2c  jmp     loc_18002B007
0x18002ae31  lea     rcx, ?DateInfo_csCacheLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002ae38  xor     ebp, ebp
0x18002ae3a  call    cs:__imp_EnterCriticalSection
0x18002ae40  mov     rsi, cs:?m_pDateInfoCache@CDateInfo@@0PEAV1@EA; CDateInfo * CDateInfo::m_pDateInfoCache
0x18002ae47  mov     rbx, rsi
0x18002ae4a  test    rsi, rsi
0x18002ae4d  jz      loc_18002AF0A
0x18002ae53  cmp     [rbx+10h], r15d
0x18002ae57  jnz     loc_18002AEE1
0x18002ae5d  cmp     [rbx+14h], r14d
0x18002ae61  jnz     short loc_18002AEE1
0x18002ae63  cmp     cs:?g_bPerUserNlsCache@@3KA, ebp; ulong g_bPerUserNlsCache
0x18002ae69  jz      short loc_18002AE81
0x18002ae6b  mov     rcx, [r13+0]; char *
0x18002ae6f  test    rcx, rcx
0x18002ae72  jz      short loc_18002AE81
0x18002ae74  mov     rdx, [rbx+8]; char *
0x18002ae78  call    ?IsSameUser@@YAHPEAD0@Z; IsSameUser(char *,char *)
0x18002ae7d  test    eax, eax
0x18002ae7f  jz      short loc_18002AEE1
0x18002ae81  cmp     [rbx], r12d
0x18002ae84  jz      loc_18002AFCF
0x18002ae8a  mov     rdi, [rbx+0CB8h]
0x18002ae91  cmp     rbx, rdi
0x18002ae94  jz      short loc_18002AEF3
0x18002ae96  mov     rax, [rbx+0CC0h]
0x18002ae9d  test    rax, rax
0x18002aea0  jz      short loc_18002AEA9
0x18002aea2  mov     [rax+0CB8h], rdi
0x18002aea9  mov     rcx, [rbx+0CB8h]
0x18002aeb0  test    rcx, rcx
0x18002aeb3  jz      short loc_18002AEC3
0x18002aeb5  mov     rax, [rbx+0CC0h]
0x18002aebc  mov     [rcx+0CC0h], rax
0x18002aec3  cmp     cs:?m_pDateInfoCache@CDateInfo@@0PEAV1@EA, rbx; CDateInfo * CDateInfo::m_pDateInfoCache
0x18002aeca  jnz     short loc_18002AED6
0x18002aecc  mov     cs:?m_pDateInfoCache@CDateInfo@@0PEAV1@EA, rdi; CDateInfo * CDateInfo::m_pDateInfoCache
0x18002aed3  mov     rsi, rdi
0x18002aed6  mov     rcx, rbx; this
0x18002aed9  call    ?Release@CDateInfo@@QEAAKXZ; CDateInfo::Release(void)
0x18002aede  mov     rbx, rdi
0x18002aee1  mov     rbx, [rbx+0CB8h]
0x18002aee8  cmp     rbx, rsi
0x18002aeeb  jnz     loc_18002AE53
0x18002aef1  jmp     short loc_18002AF02
0x18002aef3  mov     rcx, rbx; this
0x18002aef6  mov     cs:?m_pDateInfoCache@CDateInfo@@0PEAV1@EA, rbp; CDateInfo * CDateInfo::m_pDateInfoCache
0x18002aefd  call    ?Release@CDateInfo@@QEAAKXZ; CDateInfo::Release(void)
0x18002af02  mov     rdi, [rsp+68h+arg_10]
0x18002af0a  call    ?InitializeUserCalendars@@YAXXZ; InitializeUserCalendars(void)
0x18002af0f  call    cs:__imp_GetProcessHeap
0x18002af15  mov     edx, 8; dwFlags
0x18002af1a  mov     r8d, 0CD0h; dwBytes
0x18002af20  mov     rcx, rax; hHeap
0x18002af23  call    cs:__imp_HeapAlloc
0x18002af29  xor     esi, esi
0x18002af2b  mov     rbx, rax
0x18002af2e  test    rax, rax
0x18002af31  jz      loc_18002AFF3
0x18002af37  xor     edx, edx; Val
0x18002af39  mov     r8d, 0CB8h; Size
0x18002af3f  mov     rcx, rax; void *
0x18002af42  call    memset_0
0x18002af47  mov     [rbx+0CB8h], rsi
0x18002af4e  mov     [rbx+0CC0h], rsi
0x18002af55  mov     [rbx+0CC8h], esi
0x18002af5b  lock inc dword ptr [rbx+0CC8h]
0x18002af62  mov     r9, r13; char **
0x18002af65  mov     r8d, r14d; unsigned int
0x18002af68  mov     edx, r15d; unsigned int
0x18002af6b  mov     rcx, rbx; this
0x18002af6e  call    ?Init@CDateInfo@@AEAAJKKPEAPEAD@Z; CDateInfo::Init(ulong,ulong,char * *)
0x18002af73  mov     ebp, eax
0x18002af75  test    eax, eax
0x18002af77  js      short loc_18002AFF8
0x18002af79  mov     rdx, cs:?m_pDateInfoCache@CDateInfo@@0PEAV1@EA; CDateInfo * CDateInfo::m_pDateInfoCache
0x18002af80  test    rdx, rdx
0x18002af83  jz      short loc_18002AFB8
0x18002af85  mov     rcx, [rdx+0CC0h]
0x18002af8c  mov     [rbx+0CC0h], rcx
0x18002af93  mov     rcx, [rdx+0CC0h]
0x18002af9a  mov     [rcx+0CB8h], rbx
0x18002afa1  mov     rax, cs:?m_pDateInfoCache@CDateInfo@@0PEAV1@EA; CDateInfo * CDateInfo::m_pDateInfoCache
0x18002afa8  mov     [rdx+0CC0h], rbx
0x18002afaf  mov     [rbx+0CB8h], rax
0x18002afb6  jmp     short loc_18002AFC6
0x18002afb8  mov     [rbx+0CB8h], rbx
0x18002afbf  mov     [rbx+0CC0h], rbx
0x18002afc6  mov     cs:?m_pDateInfoCache@CDateInfo@@0PEAV1@EA, rbx; CDateInfo * CDateInfo::m_pDateInfoCache
0x18002afcd  jmp     short loc_18002AFD7
0x18002afcf  mov     rdi, [rsp+68h+arg_10]
0x18002afd7  lock inc dword ptr [rbx+0CC8h]
0x18002afde  cmp     cs:?m_pDateInfoCache@CDateInfo@@0PEAV1@EA, rbx; CDateInfo * CDateInfo::m_pDateInfoCache
0x18002afe5  mov     [rdi], rbx
0x18002afe8  jz      short loc_18002AFF8
0x18002afea  mov     cs:?m_pDateInfoCache@CDateInfo@@0PEAV1@EA, rbx; CDateInfo * CDateInfo::m_pDateInfoCache
0x18002aff1  jmp     short loc_18002AFF8
0x18002aff3  mov     ebp, 8007000Eh
0x18002aff8  lea     rcx, ?DateInfo_csCacheLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002afff  call    cs:__imp_LeaveCriticalSection
0x18002b005  mov     eax, ebp
0x18002b007  add     rsp, 28h
0x18002b00b  pop     r15
0x18002b00d  pop     r14
0x18002b00f  pop     r13
0x18002b011  pop     r12
0x18002b013  pop     rdi
0x18002b014  pop     rsi
0x18002b015  pop     rbp
0x18002b016  pop     rbx
0x18002b017  retn
```
