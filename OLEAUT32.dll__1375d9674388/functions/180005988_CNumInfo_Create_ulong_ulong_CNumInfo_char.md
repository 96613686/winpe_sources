# CNumInfo::Create(ulong,ulong,CNumInfo * *,char * *)

- ea: `0x180005988`
- end: `0x180005c1f`
- name: `?Create@CNumInfo@@SAJKKPEAPEAV1@PEAPEAD@Z`
- size: `663`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, struct CNumInfo **, char **)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180004890`
- `0x1800057e0`

## callees

- `0x180003148`
- `0x180005988`
- `0x18000705c`
- `0x18004a8f4`
- `0x18004e530`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a95`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005aa7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005aa7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005a2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005a2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800059c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800059c5`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x1800059a7`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x1800059a7`

## pseudocode

```c
__int64 __fastcall CNumInfo::Create(unsigned int a1, signed int a2, struct CNumInfo **a3, char **a4)
{
  __int64 v4; // rbx
  int CacheUpdateCount; // r15d
  CNumInfo *v10; // rbp
  CNumInfo *v11; // rbx
  unsigned int v12; // edi
  bool v13; // zf
  __int64 v15; // rax
  __int64 v16; // rcx
  HANDLE ProcessHeap; // rax
  CNumInfo *v18; // rax
  CNumInfo *v19; // rcx
  CNumInfo *v20; // rdi
  CNumInfo *v21; // rax
  char *v22; // rdx
  char *v23; // rdx

  v4 = (__int64)*a3;
  CacheUpdateCount = NlsGetCacheUpdateCount();
  if ( v4 && *(_DWORD *)(v4 + 16) == a1 && *(_DWORD *)(v4 + 20) == a2 )
  {
    if ( !g_bPerUserNlsCache )
      goto LABEL_28;
    v22 = *(char **)(v4 + 8);
    if ( !v22 && a1 == 1033 && a2 == 0x80000000 )
      return 0;
    if ( (unsigned int)IsSameUser(*a4, v22) )
    {
LABEL_28:
      if ( a2 < 0 || *(_DWORD *)v4 == CacheUpdateCount )
        return 0;
    }
  }
  EnterCriticalSection(&NumInfo_csCacheLock);
  v10 = CNumInfo::m_pNumInfoCache;
  v11 = CNumInfo::m_pNumInfoCache;
  if ( CNumInfo::m_pNumInfoCache )
  {
    do
    {
      if ( *((_DWORD *)v11 + 4) == a1
        && *((_DWORD *)v11 + 5) == a2
        && (!g_bPerUserNlsCache
         || (v23 = (char *)*((_QWORD *)v11 + 1)) == 0 && a1 == 1033 && a2 == 0x80000000
         || (unsigned int)IsSameUser(*a4, v23)) )
      {
        if ( *((_DWORD *)v11 + 5) == 0x80000000 || *(_DWORD *)v11 == CacheUpdateCount )
        {
          if ( !v11 )
            break;
LABEL_9:
          v12 = 0;
          _InterlockedIncrement((volatile signed __int32 *)v11 + 28);
          v13 = CNumInfo::m_pNumInfoCache == v11;
          *a3 = v11;
          if ( !v13 )
            CNumInfo::m_pNumInfoCache = v11;
          goto LABEL_11;
        }
        v20 = (CNumInfo *)*((_QWORD *)v11 + 12);
        if ( v11 == v20 )
        {
          CNumInfo::m_pNumInfoCache = 0;
          CNumInfo::Release(v11);
          break;
        }
        v15 = *((_QWORD *)v11 + 13);
        if ( v15 )
          *(_QWORD *)(v15 + 96) = v20;
        v16 = *((_QWORD *)v11 + 12);
        if ( v16 )
          *(_QWORD *)(v16 + 104) = *((_QWORD *)v11 + 13);
        if ( CNumInfo::m_pNumInfoCache == v11 )
        {
          CNumInfo::m_pNumInfoCache = v20;
          v10 = v20;
        }
        CNumInfo::Release(v11);
        v11 = v20;
      }
      v11 = (CNumInfo *)*((_QWORD *)v11 + 12);
    }
    while ( v11 != v10 );
  }
  ProcessHeap = GetProcessHeap();
  v18 = (CNumInfo *)HeapAlloc(ProcessHeap, 8u, 0x78u);
  v11 = v18;
  if ( v18 )
  {
    memset_0(v18, 0, 0x60u);
    *((_QWORD *)v11 + 12) = 0;
    *((_QWORD *)v11 + 13) = 0;
    *((_DWORD *)v11 + 28) = 0;
    _InterlockedIncrement((volatile signed __int32 *)v11 + 28);
    CNumInfo::Init(v11, a1, a2, a4);
    v19 = CNumInfo::m_pNumInfoCache;
    if ( CNumInfo::m_pNumInfoCache )
    {
      *((_QWORD *)v11 + 13) = *((_QWORD *)CNumInfo::m_pNumInfoCache + 13);
      *(_QWORD *)(*((_QWORD *)v19 + 13) + 96LL) = v11;
      v21 = CNumInfo::m_pNumInfoCache;
      *((_QWORD *)v19 + 13) = v11;
      *((_QWORD *)v11 + 12) = v21;
    }
    else
    {
      *((_QWORD *)v11 + 12) = v11;
      *((_QWORD *)v11 + 13) = v11;
    }
    CNumInfo::m_pNumInfoCache = v11;
    goto LABEL_9;
  }
  v12 = -2147024882;
LABEL_11:
  LeaveCriticalSection(&NumInfo_csCacheLock);
  return v12;
}

```

## disassembly

```asm
0x180005988  push    rbx
0x18000598a  push    rbp
0x18000598b  push    rsi
0x18000598c  push    rdi
0x18000598d  push    r12
0x18000598f  push    r13
0x180005991  push    r14
0x180005993  push    r15
0x180005995  sub     rsp, 28h
0x180005999  mov     rbx, [r8]
0x18000599c  mov     r12, r9
0x18000599f  mov     r13, r8
0x1800059a2  mov     esi, edx
0x1800059a4  mov     r14d, ecx
0x1800059a7  call    cs:__imp_NlsGetCacheUpdateCount
0x1800059ad  mov     edi, 80000000h
0x1800059b2  mov     r15d, eax
0x1800059b5  test    rbx, rbx
0x1800059b8  jnz     loc_180005B13
0x1800059be  lea     rcx, ?NumInfo_csCacheLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800059c5  call    cs:__imp_EnterCriticalSection
0x1800059cb  mov     rbp, cs:?m_pNumInfoCache@CNumInfo@@0PEAV1@EA; CNumInfo * CNumInfo::m_pNumInfoCache
0x1800059d2  mov     rbx, rbp
0x1800059d5  test    rbp, rbp
0x1800059d8  jz      loc_180005A95
0x1800059de  cmp     [rbx+10h], r14d
0x1800059e2  jnz     loc_180005A88
0x1800059e8  cmp     [rbx+14h], esi
0x1800059eb  jnz     loc_180005A88
0x1800059f1  cmp     cs:?g_bPerUserNlsCache@@3KA, 0; ulong g_bPerUserNlsCache
0x1800059f8  jnz     loc_180005BDB
0x1800059fe  cmp     [rbx+14h], edi
0x180005a01  jz      short loc_180005A0C
0x180005a03  cmp     [rbx], r15d
0x180005a06  jnz     loc_180005B47
0x180005a0c  test    rbx, rbx
0x180005a0f  jz      loc_180005A95
0x180005a15  xor     edi, edi
0x180005a17  lock inc dword ptr [rbx+70h]
0x180005a1b  cmp     cs:?m_pNumInfoCache@CNumInfo@@0PEAV1@EA, rbx; CNumInfo * CNumInfo::m_pNumInfoCache
0x180005a22  mov     [r13+0], rbx
0x180005a26  jnz     short loc_180005A48
0x180005a28  lea     rcx, ?NumInfo_csCacheLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180005a2f  call    cs:__imp_LeaveCriticalSection
0x180005a35  mov     eax, edi
0x180005a37  add     rsp, 28h
0x180005a3b  pop     r15
0x180005a3d  pop     r14
0x180005a3f  pop     r13
0x180005a41  pop     r12
0x180005a43  pop     rdi
0x180005a44  pop     rsi
0x180005a45  pop     rbp
0x180005a46  pop     rbx
0x180005a47  retn
0x180005a48  mov     cs:?m_pNumInfoCache@CNumInfo@@0PEAV1@EA, rbx; CNumInfo * CNumInfo::m_pNumInfoCache
0x180005a4f  jmp     short loc_180005A28
0x180005a51  mov     rax, [rbx+68h]
0x180005a55  test    rax, rax
0x180005a58  jnz     loc_180005BFA
0x180005a5e  mov     rcx, [rbx+60h]
0x180005a62  test    rcx, rcx
0x180005a65  jnz     loc_180005C03
0x180005a6b  cmp     cs:?m_pNumInfoCache@CNumInfo@@0PEAV1@EA, rbx; CNumInfo * CNumInfo::m_pNumInfoCache
0x180005a72  jz      loc_180005C10
0x180005a78  mov     rcx, rbx; this
0x180005a7b  call    ?Release@CNumInfo@@QEAAKXZ; CNumInfo::Release(void)
0x180005a80  mov     rbx, rdi
0x180005a83  mov     edi, 80000000h
0x180005a88  mov     rbx, [rbx+60h]
0x180005a8c  cmp     rbx, rbp
0x180005a8f  jnz     loc_1800059DE
0x180005a95  call    cs:__imp_GetProcessHeap
0x180005a9b  mov     edx, 8; dwFlags
0x180005aa0  mov     rcx, rax; hHeap
0x180005aa3  lea     r8d, [rdx+70h]; dwBytes
0x180005aa7  call    cs:__imp_HeapAlloc
0x180005aad  mov     rbx, rax
0x180005ab0  test    rax, rax
0x180005ab3  jz      loc_180005B90
0x180005ab9  xor     edx, edx; Val
0x180005abb  mov     rcx, rax; void *
0x180005abe  lea     r8d, [rdx+60h]; Size
0x180005ac2  call    memset_0
0x180005ac7  mov     qword ptr [rbx+60h], 0
0x180005acf  mov     qword ptr [rbx+68h], 0
0x180005ad7  mov     dword ptr [rbx+70h], 0
0x180005ade  lock inc dword ptr [rbx+70h]
0x180005ae2  mov     r9, r12; char **
0x180005ae5  mov     r8d, esi; unsigned int
0x180005ae8  mov     edx, r14d; unsigned int
0x180005aeb  mov     rcx, rbx; this
0x180005aee  call    ?Init@CNumInfo@@AEAAJKKPEAPEAD@Z; CNumInfo::Init(ulong,ulong,char * *)
0x180005af3  mov     rcx, cs:?m_pNumInfoCache@CNumInfo@@0PEAV1@EA; CNumInfo * CNumInfo::m_pNumInfoCache
0x180005afa  test    rcx, rcx
0x180005afd  jnz     short loc_180005B6C
0x180005aff  mov     [rbx+60h], rbx
0x180005b03  mov     [rbx+68h], rbx
0x180005b07  mov     cs:?m_pNumInfoCache@CNumInfo@@0PEAV1@EA, rbx; CNumInfo * CNumInfo::m_pNumInfoCache
0x180005b0e  jmp     loc_180005A15
0x180005b13  cmp     [rbx+10h], r14d
0x180005b17  jnz     loc_1800059BE
0x180005b1d  cmp     [rbx+14h], esi
0x180005b20  jnz     loc_1800059BE
0x180005b26  cmp     cs:?g_bPerUserNlsCache@@3KA, 0; ulong g_bPerUserNlsCache
0x180005b2d  jnz     loc_180005BBC
0x180005b33  test    esi, esi
0x180005b35  js      short loc_180005B40
0x180005b37  cmp     [rbx], r15d
0x180005b3a  jnz     loc_1800059BE
0x180005b40  xor     eax, eax
0x180005b42  jmp     loc_180005A37
0x180005b47  mov     rdi, [rbx+60h]
0x180005b4b  cmp     rbx, rdi
0x180005b4e  jnz     loc_180005A51
0x180005b54  mov     rcx, rbx; this
0x180005b57  mov     cs:?m_pNumInfoCache@CNumInfo@@0PEAV1@EA, 0; CNumInfo * CNumInfo::m_pNumInfoCache
0x180005b62  call    ?Release@CNumInfo@@QEAAKXZ; CNumInfo::Release(void)
0x180005b67  jmp     loc_180005A95
0x180005b6c  mov     rax, [rcx+68h]
0x180005b70  mov     [rbx+68h], rax
0x180005b74  mov     rax, [rcx+68h]
0x180005b78  mov     [rax+60h], rbx
0x180005b7c  mov     rax, cs:?m_pNumInfoCache@CNumInfo@@0PEAV1@EA; CNumInfo * CNumInfo::m_pNumInfoCache
0x180005b83  mov     [rcx+68h], rbx
0x180005b87  mov     [rbx+60h], rax
0x180005b8b  jmp     loc_180005B07
0x180005b90  mov     edi, 8007000Eh
0x180005b95  jmp     loc_180005A28
0x180005b9a  cmp     r14d, 409h
0x180005ba1  jnz     short loc_180005BC5
0x180005ba3  cmp     esi, edi
0x180005ba5  jz      short loc_180005B40
0x180005ba7  jmp     short loc_180005BC5
0x180005ba9  cmp     r14d, 409h
0x180005bb0  jnz     short loc_180005BE4
0x180005bb2  cmp     esi, edi
0x180005bb4  jz      loc_1800059FE
0x180005bba  jmp     short loc_180005BE4
0x180005bbc  mov     rdx, [rbx+8]; char *
0x180005bc0  test    rdx, rdx
0x180005bc3  jz      short loc_180005B9A
0x180005bc5  mov     rcx, [r12]; char *
0x180005bc9  call    ?IsSameUser@@YAHPEAD0@Z; IsSameUser(char *,char *)
0x180005bce  test    eax, eax
0x180005bd0  jz      loc_1800059BE
0x180005bd6  jmp     loc_180005B33
0x180005bdb  mov     rdx, [rbx+8]; char *
0x180005bdf  test    rdx, rdx
0x180005be2  jz      short loc_180005BA9
0x180005be4  mov     rcx, [r12]; char *
0x180005be8  call    ?IsSameUser@@YAHPEAD0@Z; IsSameUser(char *,char *)
0x180005bed  test    eax, eax
0x180005bef  jz      loc_180005A88
0x180005bf5  jmp     loc_1800059FE
0x180005bfa  mov     [rax+60h], rdi
0x180005bfe  jmp     loc_180005A5E
0x180005c03  mov     rax, [rbx+68h]
0x180005c07  mov     [rcx+68h], rax
0x180005c0b  jmp     loc_180005A6B
0x180005c10  mov     cs:?m_pNumInfoCache@CNumInfo@@0PEAV1@EA, rdi; CNumInfo * CNumInfo::m_pNumInfoCache
0x180005c17  mov     rbp, rdi
0x180005c1a  jmp     loc_180005A78
```
