# CIndexClusionCache::_HandlePathCacheMiss(long,ushort const *,int *)

- ea: `0x18003bef4`
- end: `0x18003c080`
- name: `?_HandlePathCacheMiss@CIndexClusionCache@@AEAAJJPEBGPEAH@Z`
- size: `396`
- prototype: `int(CIndexClusionCache *__hidden this, int, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003e974`
- `0x18009fde0`

## callees

- `0x18003b1b0`
- `0x18003bef4`
- `0x18003c088`
- `0x180047ae0`
- `0x18006c6bc`

## import_xrefs

- `SHCORE!SHCreateThread` at `0x18003bfd3`
- `SHCORE!SHCreateThread` at `0x18003bfd3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003bf7d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003bf7d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bf13`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bf13`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c001`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003c001`

## pseudocode

```c
__int64 __fastcall CIndexClusionCache::_HandlePathCacheMiss(
        CIndexClusionCache *this,
        int a2,
        const unsigned __int16 *a3,
        int *a4)
{
  HDPA v7; // rcx
  unsigned int v8; // ebx
  int i; // edi
  int v10; // eax
  LPCWCH *Ptr; // rsi
  CIndexClusionCache *v12; // rcx
  int v14; // eax
  _QWORD pData[2]; // [rsp+30h] [rbp-28h] BYREF
  int v16; // [rsp+40h] [rbp-18h]
  int v17; // [rsp+44h] [rbp-14h]
  int v18; // [rsp+98h] [rbp+40h] BYREF

  AcquireSRWLockExclusive(&SRWLock);
  if ( dword_18011DCE4 != a2 || a2 == -1 )
  {
    v7 = hdpa;
    dword_18011DCE4 = a2;
    if ( hdpa )
    {
      g_pfn_DPA_DestroyCallback(
        hdpa,
        CDPA_Base<CScopeState<enum REMOTE_LOCATION_CSC_STATE>,CTContainer_PolicyNewMem>::_StandardDestroyCB,
        0);
      v7 = 0;
      hdpa = 0;
    }
  }
  else
  {
    v7 = hdpa;
  }
  v18 = 0;
  v8 = 1;
  if ( v7 )
  {
    for ( i = 0; ; ++i )
    {
      if ( v7 )
      {
        v10 = *(_DWORD *)v7;
      }
      else
      {
        v10 = 0;
        v7 = 0;
      }
      if ( i >= v10 || !v8 )
        break;
      Ptr = (LPCWCH *)g_pfn_DPA_GetPtr(v7, i);
      if ( CompareStringOrdinal(*Ptr, -1, a3, -1, 1) == 2 )
      {
        v14 = *((_DWORD *)Ptr + 6);
        v8 = 0;
        *((_DWORD *)Ptr + 7) = 1;
        v18 = v14;
      }
      v7 = hdpa;
    }
  }
  if ( v8 == 1 )
  {
    v18 = 0;
    pData[1] = &v18;
    pData[0] = a3;
    v17 = 0;
    v16 = -2147467259;
    if ( (SHCreateThread(
            (LPTHREAD_START_ROUTINE)CloudSearchCommand::SetReuseContext,
            pData,
            0x208u,
            CIndexClusionCache::SyncCheckCrawlScope)
       || (int)ResultFromKnownLastError() >= 0)
      && v16 >= 0 )
    {
      v8 = CIndexClusionCache::_AddPathToCache(v12, a3, v18);
    }
  }
  if ( a4 )
    *a4 = v18;
  ReleaseSRWLockExclusive(&SRWLock);
  return v8;
}

```

## disassembly

```asm
0x18003bef4  push    rbp
0x18003bef6  push    rbx
0x18003bef7  push    rsi
0x18003bef8  push    rdi
0x18003bef9  push    r14
0x18003befb  push    r15
0x18003befd  mov     rbp, rsp
0x18003bf00  sub     rsp, 58h
0x18003bf04  lea     rcx, SRWLock; SRWLock
0x18003bf0b  mov     r14, r9
0x18003bf0e  mov     r15, r8
0x18003bf11  mov     ebx, edx
0x18003bf13  call    cs:__imp_AcquireSRWLockExclusive
0x18003bf19  cmp     cs:dword_18011DCE4, ebx
0x18003bf1f  jnz     loc_18003C02A
0x18003bf25  cmp     ebx, 0FFFFFFFFh
0x18003bf28  jz      loc_18003C02A
0x18003bf2e  mov     rcx, cs:hdpa; hdpa
0x18003bf35  mov     [rbp+arg_8], 0
0x18003bf3c  mov     ebx, 1
0x18003bf41  test    rcx, rcx
0x18003bf44  jz      short loc_18003BF97
0x18003bf46  xor     edi, edi
0x18003bf48  test    rcx, rcx
0x18003bf4b  jz      loc_18003C05E
0x18003bf51  mov     eax, [rcx]
0x18003bf53  cmp     edi, eax
0x18003bf55  jge     short loc_18003BF97
0x18003bf57  test    ebx, ebx
0x18003bf59  jz      short loc_18003BF97
0x18003bf5b  movsxd  rdx, edi; i
0x18003bf5e  call    cs:g_pfn_DPA_GetPtr
0x18003bf64  mov     r8, r15; lpString2
0x18003bf67  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18003bf6f  mov     rsi, rax
0x18003bf72  or      eax, 0FFFFFFFFh
0x18003bf75  mov     r9d, eax; cchCount2
0x18003bf78  mov     edx, eax; cchCount1
0x18003bf7a  mov     rcx, [rsi]; lpString1
0x18003bf7d  call    cs:__imp_CompareStringOrdinal
0x18003bf83  cmp     eax, 2
0x18003bf86  jz      loc_18003C016
0x18003bf8c  mov     rcx, cs:hdpa
0x18003bf93  inc     edi
0x18003bf95  jmp     short loc_18003BF48
0x18003bf97  cmp     ebx, 1
0x18003bf9a  jnz     short loc_18003BFF5
0x18003bf9c  lea     rax, [rbp+arg_8]
0x18003bfa0  mov     [rbp+arg_8], 0
0x18003bfa7  mov     [rbp+var_20], rax
0x18003bfab  lea     r9, ?SyncCheckCrawlScope@CIndexClusionCache@@SAKPEAX@Z; pfnCallback
0x18003bfb2  xor     eax, eax
0x18003bfb4  mov     [rbp+pData], r15
0x18003bfb8  mov     r8d, 208h; flags
0x18003bfbe  mov     [rbp+var_14], eax
0x18003bfc1  lea     rdx, [rbp+pData]; pData
0x18003bfc5  mov     [rbp+var_18], 80004005h
0x18003bfcc  lea     rcx, ?SetReuseContext@CloudSearchCommand@@UEAAJPEAUIRowset@@@Z; pfnThreadProc
0x18003bfd3  call    cs:__imp_SHCreateThread
0x18003bfd9  test    eax, eax
0x18003bfdb  jz      loc_18003C067
0x18003bfe1  cmp     [rbp+var_18], 0
0x18003bfe5  jl      short loc_18003BFF5
0x18003bfe7  mov     r8d, [rbp+arg_8]; int
0x18003bfeb  mov     rdx, r15; unsigned __int16 *
0x18003bfee  call    ?_AddPathToCache@CIndexClusionCache@@AEAAJPEBGH@Z; CIndexClusionCache::_AddPathToCache(ushort const *,int)
0x18003bff3  mov     ebx, eax
0x18003bff5  test    r14, r14
0x18003bff8  jnz     short loc_18003C075
0x18003bffa  lea     rcx, SRWLock; SRWLock
0x18003c001  call    cs:__imp_ReleaseSRWLockExclusive
0x18003c007  mov     eax, ebx
0x18003c009  add     rsp, 58h
0x18003c00d  pop     r15
0x18003c00f  pop     r14
0x18003c011  pop     rdi
0x18003c012  pop     rsi
0x18003c013  pop     rbx
0x18003c014  pop     rbp
0x18003c015  retn
0x18003c016  mov     eax, [rsi+18h]
0x18003c019  xor     ebx, ebx
0x18003c01b  mov     dword ptr [rsi+1Ch], 1
0x18003c022  mov     [rbp+arg_8], eax
0x18003c025  jmp     loc_18003BF8C
0x18003c02a  mov     rcx, cs:hdpa; hdpa
0x18003c031  mov     cs:dword_18011DCE4, ebx
0x18003c037  test    rcx, rcx
0x18003c03a  jz      loc_18003BF35
0x18003c040  xor     r8d, r8d; pData
0x18003c043  lea     rdx, ?_StandardDestroyCB@?$CDPA_Base@V?$CScopeState@W4REMOTE_LOCATION_CSC_STATE@@@@VCTContainer_PolicyNewMem@@@@CAHPEAV?$CScopeState@W4REMOTE_LOCATION_CSC_STATE@@@@PEAX@Z; pfnCB
0x18003c04a  call    cs:g_pfn_DPA_DestroyCallback
0x18003c050  xor     ecx, ecx
0x18003c052  mov     cs:hdpa, rcx
0x18003c059  jmp     loc_18003BF35
0x18003c05e  xor     eax, eax
0x18003c060  xor     ecx, ecx
0x18003c062  jmp     loc_18003BF53
0x18003c067  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18003c06c  test    eax, eax
0x18003c06e  js      short loc_18003BFF5
0x18003c070  jmp     loc_18003BFE1
0x18003c075  mov     edx, [rbp+arg_8]
0x18003c078  mov     [r14], edx
0x18003c07b  jmp     loc_18003BFFA
```
