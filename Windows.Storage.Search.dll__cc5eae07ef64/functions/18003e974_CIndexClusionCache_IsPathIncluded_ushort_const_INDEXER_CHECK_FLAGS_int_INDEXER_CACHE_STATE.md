# CIndexClusionCache::_IsPathIncluded(ushort const *,INDEXER_CHECK_FLAGS,int *,INDEXER_CACHE_STATE *)

- ea: `0x18003e974`
- end: `0x18003eb5b`
- name: `?_IsPathIncluded@CIndexClusionCache@@AEAAJPEBGW4INDEXER_CHECK_FLAGS@@PEAHPEAW4INDEXER_CACHE_STATE@@@Z`
- size: `487`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003c220`
- `0x18003d2e0`
- `0x18009d650`

## callees

- `0x1800182a0`
- `0x18003bef4`
- `0x18003e974`
- `0x18003eb64`
- `0x180040aa8`
- `0x180047ae0`
- `0x18006c6bc`
- `0x18009e04c`

## import_xrefs

- `SHCORE!SHCreateThread` at `0x18003eb10`
- `SHCORE!SHCreateThread` at `0x18003eb10`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003ea31`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003ea31`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003ea4e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003ea4e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003e9e0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18003e9e0`

## pseudocode

```c
__int64 __fastcall CIndexClusionCache::_IsPathIncluded(void *a1, const unsigned __int16 *a2, int a3, int *a4, int *a5)
{
  int v8; // r12d
  CIndexClusionCache *v9; // rcx
  int v10; // esi
  int Error; // ebx
  HDPA v12; // rcx
  int i; // ebp
  int v14; // eax
  LPCWCH *Ptr; // r15
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  _DWORD *v20; // rdi
  void *pData; // [rsp+80h] [rbp+8h] BYREF

  pData = a1;
  *a4 = 0;
  v8 = 0;
  if ( !(unsigned int)IsIndexerSupportedDriveType(a2) )
  {
    Error = 0;
    goto LABEL_16;
  }
  if ( g_IndexClusionCache )
    v10 = *(_DWORD *)g_IndexClusionCache;
  else
    v10 = -1;
  g_lCrawlScopeVersion = v10;
  if ( dword_18011DCE4 != v10 || v10 == -1 )
    goto LABEL_21;
  AcquireSRWLockShared(&SRWLock);
  *a4 = 0;
  Error = 1;
  v12 = hdpa;
  if ( hdpa )
  {
    for ( i = 0; ; ++i )
    {
      if ( v12 )
      {
        v14 = *(_DWORD *)v12;
      }
      else
      {
        v14 = 0;
        v12 = 0;
      }
      if ( i >= v14 || !Error )
        break;
      Ptr = (LPCWCH *)g_pfn_DPA_GetPtr(v12, i);
      if ( CompareStringOrdinal(*Ptr, -1, a2, -1, 1) == 2 )
      {
        v17 = *((_DWORD *)Ptr + 6);
        Error = 0;
        *((_DWORD *)Ptr + 7) = 1;
        *a4 = v17;
      }
      v12 = hdpa;
    }
  }
  ReleaseSRWLockShared(&SRWLock);
  if ( Error == 1 )
  {
LABEL_21:
    v8 = 1;
    if ( !a3 )
    {
      Error = CIndexClusionCache::_HandlePathCacheMiss(v9, v10, a2, a4);
      goto LABEL_16;
    }
    *a4 = 0;
    pData = 0;
    Error = CTLocalAllocPolicy::Alloc(v9, 0x40u, 0x10u, &pData);
    if ( Error < 0 )
      goto LABEL_16;
    v20 = pData;
    Error = _AllocString<CTCoAllocPolicy>(v19, v18, a2, (_QWORD *)pData + 1);
    if ( Error >= 0 )
    {
      *v20 = v10;
      if ( SHCreateThread(CIndexClusionCache::s_HandlePathCacheMiss, v20, 0xCu, 0) )
      {
        Error = 0;
LABEL_27:
        v20 = 0;
        goto LABEL_28;
      }
      Error = ResultFromKnownLastError();
      if ( Error >= 0 )
        goto LABEL_27;
    }
LABEL_28:
    ClearHCMI(v20);
  }
LABEL_16:
  if ( a5 )
    *a5 = v8;
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18003e974  mov     [rsp+pData], rcx
0x18003e979  push    rbx
0x18003e97a  push    rbp
0x18003e97b  push    rsi
0x18003e97c  push    rdi
0x18003e97d  push    r12
0x18003e97f  push    r13
0x18003e981  push    r14
0x18003e983  push    r15
0x18003e985  sub     rsp, 38h
0x18003e989  mov     rcx, rdx; unsigned __int16 *
0x18003e98c  mov     dword ptr [r9], 0
0x18003e993  mov     rdi, r9
0x18003e996  mov     r13d, r8d
0x18003e999  mov     r14, rdx
0x18003e99c  xor     r12d, r12d
0x18003e99f  call    ?IsIndexerSupportedDriveType@@YAHPEBG@Z; IsIndexerSupportedDriveType(ushort const *)
0x18003e9a4  test    eax, eax
0x18003e9a6  jz      loc_18003EB4C
0x18003e9ac  mov     rsi, cs:?g_IndexClusionCache@@3VCIndexClusionCache@@A; CIndexClusionCache g_IndexClusionCache
0x18003e9b3  test    rsi, rsi
0x18003e9b6  jz      loc_18003EA7D
0x18003e9bc  mov     esi, [rsi]
0x18003e9be  cmp     cs:dword_18011DCE4, esi
0x18003e9c4  mov     cs:?g_lCrawlScopeVersion@@3JA, esi; long g_lCrawlScopeVersion
0x18003e9ca  jnz     loc_18003EAA0
0x18003e9d0  cmp     esi, 0FFFFFFFFh
0x18003e9d3  jz      loc_18003EAA0
0x18003e9d9  lea     rcx, SRWLock; SRWLock
0x18003e9e0  call    cs:__imp_AcquireSRWLockShared
0x18003e9e6  mov     [rdi], r12d
0x18003e9e9  mov     ebx, 1
0x18003e9ee  mov     rcx, cs:hdpa; hdpa
0x18003e9f5  test    rcx, rcx
0x18003e9f8  jz      short loc_18003EA47
0x18003e9fa  xor     ebp, ebp
0x18003e9fc  test    rcx, rcx
0x18003e9ff  jz      loc_18003EA97
0x18003ea05  mov     eax, [rcx]
0x18003ea07  cmp     ebp, eax
0x18003ea09  jge     short loc_18003EA47
0x18003ea0b  test    ebx, ebx
0x18003ea0d  jz      short loc_18003EA47
0x18003ea0f  movsxd  rdx, ebp; i
0x18003ea12  call    cs:g_pfn_DPA_GetPtr
0x18003ea18  mov     r8, r14; lpString2
0x18003ea1b  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18003ea23  mov     r15, rax
0x18003ea26  or      eax, 0FFFFFFFFh
0x18003ea29  mov     r9d, eax; cchCount2
0x18003ea2c  mov     edx, eax; cchCount1
0x18003ea2e  mov     rcx, [r15]; lpString1
0x18003ea31  call    cs:__imp_CompareStringOrdinal
0x18003ea37  cmp     eax, 2
0x18003ea3a  jz      short loc_18003EA85
0x18003ea3c  mov     rcx, cs:hdpa
0x18003ea43  inc     ebp
0x18003ea45  jmp     short loc_18003E9FC
0x18003ea47  lea     rcx, SRWLock; SRWLock
0x18003ea4e  call    cs:__imp_ReleaseSRWLockShared
0x18003ea54  cmp     ebx, 1
0x18003ea57  jz      short loc_18003EAA0
0x18003ea59  mov     rax, [rsp+78h+arg_20]
0x18003ea61  test    rax, rax
0x18003ea64  jnz     loc_18003EB53
0x18003ea6a  mov     eax, ebx
0x18003ea6c  add     rsp, 38h
0x18003ea70  pop     r15
0x18003ea72  pop     r14
0x18003ea74  pop     r13
0x18003ea76  pop     r12
0x18003ea78  pop     rdi
0x18003ea79  pop     rsi
0x18003ea7a  pop     rbp
0x18003ea7b  pop     rbx
0x18003ea7c  retn
0x18003ea7d  or      esi, 0FFFFFFFFh
0x18003ea80  jmp     loc_18003E9BE
0x18003ea85  mov     eax, [r15+18h]
0x18003ea89  xor     ebx, ebx
0x18003ea8b  mov     dword ptr [r15+1Ch], 1
0x18003ea93  mov     [rdi], eax
0x18003ea95  jmp     short loc_18003EA3C
0x18003ea97  xor     eax, eax
0x18003ea99  xor     ecx, ecx
0x18003ea9b  jmp     loc_18003EA07
0x18003eaa0  mov     r12d, 1
0x18003eaa6  test    r13d, r13d
0x18003eaa9  jz      loc_18003EB38
0x18003eaaf  lea     r9, [rsp+78h+pData]; void **
0x18003eab7  mov     dword ptr [rdi], 0
0x18003eabd  lea     edx, [r12+3Fh]; unsigned int
0x18003eac2  mov     [rsp+78h+pData], 0
0x18003eace  lea     r8d, [r12+0Fh]; unsigned __int64
0x18003ead3  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18003ead8  mov     ebx, eax
0x18003eada  test    eax, eax
0x18003eadc  js      loc_18003EA59
0x18003eae2  mov     rdi, [rsp+78h+pData]
0x18003eaea  mov     r8, r14
0x18003eaed  lea     r9, [rdi+8]
0x18003eaf1  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18003eaf6  mov     ebx, eax
0x18003eaf8  test    eax, eax
0x18003eafa  js      short loc_18003EB2B
0x18003eafc  xor     r9d, r9d; pfnCallback
0x18003eaff  mov     [rdi], esi
0x18003eb01  lea     r8d, [r12+0Bh]; flags
0x18003eb06  mov     rdx, rdi; pData
0x18003eb09  lea     rcx, ?s_HandlePathCacheMiss@CIndexClusionCache@@SAKPEAX@Z; pfnThreadProc
0x18003eb10  call    cs:__imp_SHCreateThread
0x18003eb16  test    eax, eax
0x18003eb18  jz      short loc_18003EB1E
0x18003eb1a  xor     ebx, ebx
0x18003eb1c  jmp     short loc_18003EB29
0x18003eb1e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003eb23  mov     ebx, eax
0x18003eb25  test    eax, eax
0x18003eb27  js      short loc_18003EB2B
0x18003eb29  xor     edi, edi
0x18003eb2b  mov     rcx, rdi; hMem
0x18003eb2e  call    ?ClearHCMI@@YAXPEAUHANDLE_CACHE_MISS_INFO@@@Z; ClearHCMI(HANDLE_CACHE_MISS_INFO *)
0x18003eb33  jmp     loc_18003EA59
0x18003eb38  mov     r9, rdi; int *
0x18003eb3b  mov     r8, r14; unsigned __int16 *
0x18003eb3e  mov     edx, esi; int
0x18003eb40  call    ?_HandlePathCacheMiss@CIndexClusionCache@@AEAAJJPEBGPEAH@Z; CIndexClusionCache::_HandlePathCacheMiss(long,ushort const *,int *)
0x18003eb45  mov     ebx, eax
0x18003eb47  jmp     loc_18003EA59
0x18003eb4c  xor     ebx, ebx
0x18003eb4e  jmp     loc_18003EA59
0x18003eb53  mov     [rax], r12d
0x18003eb56  jmp     loc_18003EA6A
```
