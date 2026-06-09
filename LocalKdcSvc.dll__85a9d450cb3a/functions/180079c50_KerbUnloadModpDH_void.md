# KerbUnloadModpDH(void)

- ea: `0x180079c50`
- end: `0x180079d02`
- name: `?KerbUnloadModpDH@@YAXXZ`
- size: `178`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180079bf4`

## callees

- `0x180003908`
- `0x180079c50`
- `0x180084f54`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180079c69`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180079c69`
- `ntdll!RtlDeleteCriticalSection` at `0x180079ce6`
- `ntdll!RtlDeleteCriticalSection` at `0x180079ce6`
- `ntdll!RtlLeaveCriticalSection` at `0x180079cc9`
- `ntdll!RtlLeaveCriticalSection` at `0x180079cc9`
- `ntdll!RtlEnterCriticalSection` at `0x180079c8a`
- `ntdll!RtlEnterCriticalSection` at `0x180079c8a`

## pseudocode

```c
void KerbUnloadModpDH(void)
{
  __int64 i; // rbx

  if ( KerbGlobalCSPProvider )
  {
    CryptReleaseContext(KerbGlobalCSPProvider, 0);
    KerbGlobalCSPProvider = 0;
  }
  if ( KerbGlobalWellknownDomainParamtersLockInitialized )
  {
    RtlEnterCriticalSection(&KerbGlobalWellknownDomainParamtersLock);
    for ( i = 0; (unsigned int)i < KerbGlobalWellknownDomainParamtersCount; i = (unsigned int)(i + 1) )
      KerbFreeDHParameters((struct _CERT_X942_DH_PARAMETERS *)&(&KerbGlobalWellknownDomainParamters)[9 * i]);
    KerbGlobalWellknownDomainParamtersCount = 0;
    RtlLeaveCriticalSection(&KerbGlobalWellknownDomainParamtersLock);
    memset_0(&KerbGlobalWellknownDomainParamters, 0, 0x1C20u);
    RtlDeleteCriticalSection(&KerbGlobalWellknownDomainParamtersLock);
    KerbGlobalWellknownDomainParamtersLockInitialized = 0;
  }
}

```

## disassembly

```asm
0x180079c50  mov     [rsp+arg_0], rbx
0x180079c55  push    r14
0x180079c57  sub     rsp, 20h
0x180079c5b  mov     rcx, cs:?KerbGlobalCSPProvider@@3_KA; hProv
0x180079c62  test    rcx, rcx
0x180079c65  jz      short loc_180079C7A
0x180079c67  xor     edx, edx; dwFlags
0x180079c69  call    cs:__imp_CryptReleaseContext
0x180079c6f  mov     cs:?KerbGlobalCSPProvider@@3_KA, 0; unsigned __int64 KerbGlobalCSPProvider
0x180079c7a  cmp     cs:?KerbGlobalWellknownDomainParamtersLockInitialized@@3HA, 0; int KerbGlobalWellknownDomainParamtersLockInitialized
0x180079c81  jz      short loc_180079CF6
0x180079c83  lea     rcx, ?KerbGlobalWellknownDomainParamtersLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180079c8a  call    cs:__imp_RtlEnterCriticalSection
0x180079c90  xor     ebx, ebx
0x180079c92  lea     r14, ?KerbGlobalWellknownDomainParamters@@3PAU_CERT_X942_DH_PARAMETERS@@A; _CERT_X942_DH_PARAMETERS near * KerbGlobalWellknownDomainParamters
0x180079c99  cmp     cs:?KerbGlobalWellknownDomainParamtersCount@@3KA, ebx; ulong KerbGlobalWellknownDomainParamtersCount
0x180079c9f  jbe     short loc_180079CB8
0x180079ca1  lea     rdx, [rbx+rbx*8]
0x180079ca5  lea     rcx, [r14+rdx*8]; struct _CERT_X942_DH_PARAMETERS *
0x180079ca9  call    ?KerbFreeDHParameters@@YAXPEAU_CERT_X942_DH_PARAMETERS@@@Z; KerbFreeDHParameters(_CERT_X942_DH_PARAMETERS *)
0x180079cae  inc     ebx
0x180079cb0  cmp     ebx, cs:?KerbGlobalWellknownDomainParamtersCount@@3KA; ulong KerbGlobalWellknownDomainParamtersCount
0x180079cb6  jb      short loc_180079CA1
0x180079cb8  lea     rcx, ?KerbGlobalWellknownDomainParamtersLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180079cbf  mov     cs:?KerbGlobalWellknownDomainParamtersCount@@3KA, 0; ulong KerbGlobalWellknownDomainParamtersCount
0x180079cc9  call    cs:__imp_RtlLeaveCriticalSection
0x180079ccf  xor     edx, edx; Val
0x180079cd1  mov     r8d, 1C20h; Size
0x180079cd7  mov     rcx, r14; void *
0x180079cda  call    memset_0
0x180079cdf  lea     rcx, ?KerbGlobalWellknownDomainParamtersLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180079ce6  call    cs:__imp_RtlDeleteCriticalSection
0x180079cec  mov     cs:?KerbGlobalWellknownDomainParamtersLockInitialized@@3HA, 0; int KerbGlobalWellknownDomainParamtersLockInitialized
0x180079cf6  mov     rbx, [rsp+28h+arg_0]
0x180079cfb  add     rsp, 20h
0x180079cff  pop     r14
0x180079d01  retn
```
