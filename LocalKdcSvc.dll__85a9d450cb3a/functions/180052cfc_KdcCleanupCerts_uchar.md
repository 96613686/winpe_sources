# KdcCleanupCerts(uchar)

- ea: `0x180052cfc`
- end: `0x180052e64`
- name: `?KdcCleanupCerts@@YAXE@Z`
- size: `360`
- prototype: `void __fastcall()`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180035a44`
- `0x18004d854`

## callees

- `0x180052cfc`
- `0x1800533e0`
- `0x18005a090`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052ddd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052ddd`
- `CRYPT32!CertCloseServerOcspResponse` at `0x180052da9`
- `CRYPT32!CertCloseServerOcspResponse` at `0x180052da9`
- `CRYPT32!CertCloseStore` at `0x180052dc4`
- `CRYPT32!CertCloseStore` at `0x180052dc4`
- `CRYPT32!CertFreeCertificateContext` at `0x180052d46`
- `CRYPT32!CertFreeCertificateContext` at `0x180052d6f`
- `CRYPT32!CertFreeCertificateContext` at `0x180052d46`
- `CRYPT32!CertFreeCertificateContext` at `0x180052d6f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180052d1e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180052d1e`
- `ntdll!RtlDeleteCriticalSection` at `0x180052e07`
- `ntdll!RtlDeleteCriticalSection` at `0x180052e07`
- `ntdll!RtlReleaseResource` at `0x180052e36`
- `ntdll!RtlReleaseResource` at `0x180052e36`
- `ntdll!RtlDeleteResource` at `0x180052e4d`
- `ntdll!RtlDeleteResource` at `0x180052e4d`
- `ntdll!RtlLeaveCriticalSection` at `0x180052dfa`
- `ntdll!RtlLeaveCriticalSection` at `0x180052dfa`
- `ntdll!RtlAcquireResourceExclusive` at `0x180052e28`
- `ntdll!RtlAcquireResourceExclusive` at `0x180052e28`
- `ntdll!RtlEnterCriticalSection` at `0x180052d34`
- `ntdll!RtlEnterCriticalSection` at `0x180052d34`

## pseudocode

```c
void __fastcall KdcCleanupCerts()
{
  PCCERT_CONTEXT *v0; // rax
  unsigned int i; // ebx

  if ( KdcCertStoreWait )
    UnregisterWaitEx(
      (HANDLE)_InterlockedExchange64((volatile __int64 *)&KdcCertStoreWait, 0),
      (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( KdcGlobalCertCritSectInitialized )
    RtlEnterCriticalSection(&KdcGlobalCertCritSect);
  if ( KdcGlobalCert )
  {
    CertFreeCertificateContext(KdcGlobalCert);
    KdcGlobalCert = 0;
  }
  v0 = (PCCERT_CONTEXT *)KdcGlobalAdditionalCertificates;
  if ( KdcGlobalAdditionalCertificates )
  {
    for ( i = 0; i < KdcGlobalAdditionalCertificatesCount; ++i )
    {
      CertFreeCertificateContext(v0[i]);
      v0 = (PCCERT_CONTEXT *)KdcGlobalAdditionalCertificates;
    }
    MIDL_user_free(v0);
    KdcGlobalAdditionalCertificates = 0;
  }
  KdcGlobalAdditionalCertificatesCount = 0;
  if ( KdcGlobalCertOcspResponse )
  {
    CertCloseServerOcspResponse(KdcGlobalCertOcspResponse, 0);
    KdcGlobalCertOcspResponse = 0;
  }
  if ( KdcCertStore )
  {
    CertCloseStore(KdcCertStore, 0);
    KdcCertStore = 0;
  }
  if ( KdcCertStoreChangeEvent )
  {
    CloseHandle(KdcCertStoreChangeEvent);
    KdcCertStoreChangeEvent = 0;
  }
  if ( KdcGlobalCertCritSectInitialized )
  {
    RtlLeaveCriticalSection(&KdcGlobalCertCritSect);
    RtlDeleteCriticalSection(&KdcGlobalCertCritSect);
    KdcGlobalCertCritSectInitialized = 0;
  }
  if ( KdcGlobalDHParametersInitialized )
  {
    RtlAcquireResourceExclusive(&KdcGlobalDHParametersLock, 1u);
    KdcFreeCachedKeys();
    RtlReleaseResource(&KdcGlobalDHParametersLock);
    KdcGlobalDHParametersInitialized = 0;
  }
  if ( KdcGlobalDHParametersLockInitialized )
  {
    RtlDeleteResource(&KdcGlobalDHParametersLock);
    KdcGlobalDHParametersLockInitialized = 0;
  }
}

```

## disassembly

```asm
0x180052cfc  mov     [rsp+arg_0], rbx
0x180052d01  push    rdi
0x180052d02  sub     rsp, 20h
0x180052d06  xor     edi, edi
0x180052d08  cmp     cs:?KdcCertStoreWait@@3PEAXEA, rdi; void * KdcCertStoreWait
0x180052d0f  jz      short loc_180052D24
0x180052d11  mov     ecx, edi
0x180052d13  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180052d17  xchg    rcx, cs:?KdcCertStoreWait@@3PEAXEA; WaitHandle
0x180052d1e  call    cs:__imp_UnregisterWaitEx
0x180052d24  cmp     cs:?KdcGlobalCertCritSectInitialized@@3EA, dil; uchar KdcGlobalCertCritSectInitialized
0x180052d2b  jz      short loc_180052D3A
0x180052d2d  lea     rcx, ?KdcGlobalCertCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180052d34  call    cs:__imp_RtlEnterCriticalSection
0x180052d3a  mov     rcx, cs:?KdcGlobalCert@@3PEBU_CERT_CONTEXT@@EB; pCertContext
0x180052d41  test    rcx, rcx
0x180052d44  jz      short loc_180052D53
0x180052d46  call    cs:__imp_CertFreeCertificateContext
0x180052d4c  mov     cs:?KdcGlobalCert@@3PEBU_CERT_CONTEXT@@EB, rdi; _CERT_CONTEXT const * const KdcGlobalCert
0x180052d53  mov     rax, cs:?KdcGlobalAdditionalCertificates@@3PEAPEBU_CERT_CONTEXT@@EA; _CERT_CONTEXT const * * KdcGlobalAdditionalCertificates
0x180052d5a  test    rax, rax
0x180052d5d  jz      short loc_180052D95
0x180052d5f  cmp     cs:?KdcGlobalAdditionalCertificatesCount@@3KA, edi; ulong KdcGlobalAdditionalCertificatesCount
0x180052d65  mov     ebx, edi
0x180052d67  jbe     short loc_180052D86
0x180052d69  mov     ecx, ebx
0x180052d6b  mov     rcx, [rax+rcx*8]; pCertContext
0x180052d6f  call    cs:__imp_CertFreeCertificateContext
0x180052d75  mov     rax, cs:?KdcGlobalAdditionalCertificates@@3PEAPEBU_CERT_CONTEXT@@EA; _CERT_CONTEXT const * * KdcGlobalAdditionalCertificates
0x180052d7c  inc     ebx
0x180052d7e  cmp     ebx, cs:?KdcGlobalAdditionalCertificatesCount@@3KA; ulong KdcGlobalAdditionalCertificatesCount
0x180052d84  jb      short loc_180052D69
0x180052d86  mov     rcx, rax; void *
0x180052d89  call    MIDL_user_free
0x180052d8e  mov     cs:?KdcGlobalAdditionalCertificates@@3PEAPEBU_CERT_CONTEXT@@EA, rdi; _CERT_CONTEXT const * * KdcGlobalAdditionalCertificates
0x180052d95  mov     rcx, cs:?KdcGlobalCertOcspResponse@@3PEAXEA; hServerOcspResponse
0x180052d9c  mov     cs:?KdcGlobalAdditionalCertificatesCount@@3KA, edi; ulong KdcGlobalAdditionalCertificatesCount
0x180052da2  test    rcx, rcx
0x180052da5  jz      short loc_180052DB6
0x180052da7  xor     edx, edx; dwFlags
0x180052da9  call    cs:__imp_CertCloseServerOcspResponse
0x180052daf  mov     cs:?KdcGlobalCertOcspResponse@@3PEAXEA, rdi; void * KdcGlobalCertOcspResponse
0x180052db6  mov     rcx, cs:?KdcCertStore@@3PEAXEA; hCertStore
0x180052dbd  test    rcx, rcx
0x180052dc0  jz      short loc_180052DD1
0x180052dc2  xor     edx, edx; dwFlags
0x180052dc4  call    cs:__imp_CertCloseStore
0x180052dca  mov     cs:?KdcCertStore@@3PEAXEA, rdi; void * KdcCertStore
0x180052dd1  mov     rcx, cs:?KdcCertStoreChangeEvent@@3PEAXEA; hObject
0x180052dd8  test    rcx, rcx
0x180052ddb  jz      short loc_180052DEA
0x180052ddd  call    cs:__imp_CloseHandle
0x180052de3  mov     cs:?KdcCertStoreChangeEvent@@3PEAXEA, rdi; void * KdcCertStoreChangeEvent
0x180052dea  cmp     cs:?KdcGlobalCertCritSectInitialized@@3EA, dil; uchar KdcGlobalCertCritSectInitialized
0x180052df1  jz      short loc_180052E14
0x180052df3  lea     rcx, ?KdcGlobalCertCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180052dfa  call    cs:__imp_RtlLeaveCriticalSection
0x180052e00  lea     rcx, ?KdcGlobalCertCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180052e07  call    cs:__imp_RtlDeleteCriticalSection
0x180052e0d  mov     cs:?KdcGlobalCertCritSectInitialized@@3EA, dil; uchar KdcGlobalCertCritSectInitialized
0x180052e14  cmp     cs:?KdcGlobalDHParametersInitialized@@3JA, edi; long KdcGlobalDHParametersInitialized
0x180052e1a  lea     rbx, ?KdcGlobalDHParametersLock@@3U_RTL_RESOURCE@@A; _RTL_RESOURCE KdcGlobalDHParametersLock
0x180052e21  jz      short loc_180052E42
0x180052e23  mov     dl, 1; Wait
0x180052e25  mov     rcx, rbx; Resource
0x180052e28  call    cs:__imp_RtlAcquireResourceExclusive
0x180052e2e  call    ?KdcFreeCachedKeys@@YAXXZ; KdcFreeCachedKeys(void)
0x180052e33  mov     rcx, rbx; Resource
0x180052e36  call    cs:__imp_RtlReleaseResource
0x180052e3c  mov     cs:?KdcGlobalDHParametersInitialized@@3JA, edi; long KdcGlobalDHParametersInitialized
0x180052e42  cmp     cs:?KdcGlobalDHParametersLockInitialized@@3KA, edi; ulong KdcGlobalDHParametersLockInitialized
0x180052e48  jz      short loc_180052E59
0x180052e4a  mov     rcx, rbx; Resource
0x180052e4d  call    cs:__imp_RtlDeleteResource
0x180052e53  mov     cs:?KdcGlobalDHParametersLockInitialized@@3KA, edi; ulong KdcGlobalDHParametersLockInitialized
0x180052e59  mov     rbx, [rsp+28h+arg_0]
0x180052e5e  add     rsp, 20h
0x180052e62  pop     rdi
0x180052e63  retn
```
