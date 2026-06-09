# KdcCleanupDomainTree(void)

- ea: `0x1800579e0`
- end: `0x180057a7c`
- name: `?KdcCleanupDomainTree@@YAXXZ`
- size: `156`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180035a44`

## callees

- `0x1800579e0`
- `0x180057d8c`
- `0x180058400`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180057a07`
- `ntdll!RtlDeleteCriticalSection` at `0x180057a71`
- `ntdll!RtlDeleteCriticalSection` at `0x180057a07`
- `ntdll!RtlDeleteCriticalSection` at `0x180057a71`

## pseudocode

```c
void KdcCleanupDomainTree(void)
{
  struct _REFERRAL_CACHE_ENTRY *v0; // rcx
  __int64 v1; // rax
  struct _REFERRAL_CACHE_ENTRY **v2; // rdx

  if ( KdcDomainListInitialized )
  {
    KdcDomainListInitialized = 0;
    KdcFreeDomainList(&KdcDomainList);
    RtlDeleteCriticalSection(&KdcDomainListLock);
  }
  if ( KdcReferralCacheInitialized )
  {
    v0 = KdcReferralCache;
    KdcReferralCacheInitialized = 0;
    if ( KdcReferralCache )
    {
      while ( v0 != (struct _REFERRAL_CACHE_ENTRY *)&KdcReferralCache )
      {
        v1 = *(_QWORD *)v0;
        if ( *(struct _REFERRAL_CACHE_ENTRY **)(*(_QWORD *)v0 + 8LL) != v0
          || (v2 = (struct _REFERRAL_CACHE_ENTRY **)*((_QWORD *)v0 + 1), *v2 != v0) )
        {
          __fastfail(3u);
        }
        *v2 = (struct _REFERRAL_CACHE_ENTRY *)v1;
        *(_QWORD *)(v1 + 8) = v2;
        *((_QWORD *)v0 + 1) = v0;
        *(_QWORD *)v0 = v0;
        KdcDereferenceReferralCacheEntry(v0);
        v0 = KdcReferralCache;
      }
    }
    RtlDeleteCriticalSection(&KdcReferralCacheLock);
  }
}

```

## disassembly

```asm
0x1800579e0  sub     rsp, 28h
0x1800579e4  cmp     cs:?KdcDomainListInitialized@@3EA, 0; uchar KdcDomainListInitialized
0x1800579eb  jz      short loc_180057A0D
0x1800579ed  lea     rcx, ?KdcDomainList@@3U_LIST_ENTRY@@A; struct _LIST_ENTRY *
0x1800579f4  mov     cs:?KdcDomainListInitialized@@3EA, 0; uchar KdcDomainListInitialized
0x1800579fb  call    ?KdcFreeDomainList@@YAXPEAU_LIST_ENTRY@@@Z; KdcFreeDomainList(_LIST_ENTRY *)
0x180057a00  lea     rcx, ?KdcDomainListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180057a07  call    cs:__imp_RtlDeleteCriticalSection
0x180057a0d  cmp     cs:?KdcReferralCacheInitialized@@3EA, 0; uchar KdcReferralCacheInitialized
0x180057a14  jz      short loc_180057A77
0x180057a16  mov     rcx, cs:?KdcReferralCache@@3U_LIST_ENTRY@@A; struct _REFERRAL_CACHE_ENTRY *
0x180057a1d  mov     cs:?KdcReferralCacheInitialized@@3EA, 0; uchar KdcReferralCacheInitialized
0x180057a24  test    rcx, rcx
0x180057a27  jz      short loc_180057A6A
0x180057a29  lea     rax, ?KdcReferralCache@@3U_LIST_ENTRY@@A; _LIST_ENTRY KdcReferralCache
0x180057a30  cmp     rcx, rax
0x180057a33  jz      short loc_180057A6A
0x180057a35  mov     rax, [rcx]
0x180057a38  cmp     [rax+8], rcx
0x180057a3c  jnz     short loc_180057A63
0x180057a3e  mov     rdx, [rcx+8]
0x180057a42  cmp     [rdx], rcx
0x180057a45  jnz     short loc_180057A63
0x180057a47  mov     [rdx], rax
0x180057a4a  mov     [rax+8], rdx
0x180057a4e  mov     [rcx+8], rcx
0x180057a52  mov     [rcx], rcx
0x180057a55  call    ?KdcDereferenceReferralCacheEntry@@YAXPEAU_REFERRAL_CACHE_ENTRY@@@Z; KdcDereferenceReferralCacheEntry(_REFERRAL_CACHE_ENTRY *)
0x180057a5a  mov     rcx, cs:?KdcReferralCache@@3U_LIST_ENTRY@@A; _LIST_ENTRY KdcReferralCache
0x180057a61  jmp     short loc_180057A29
0x180057a63  mov     ecx, 3
0x180057a68  int     29h; Win8: RtlFailFast(ecx)
0x180057a6a  lea     rcx, ?KdcReferralCacheLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180057a71  call    cs:__imp_RtlDeleteCriticalSection
0x180057a77  add     rsp, 28h
0x180057a7b  retn
```
