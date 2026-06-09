# EfsUnInit

- ea: `0x180033ab8`
- end: `0x180033c53`
- name: `EfsUnInit`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180010cc0`

## callees

- `0x180010bf0`
- `0x180033a10`
- `0x180033ab8`
- `0x18003593c`
- `0x1800430c4`
- `0x18004bd0c`
- `0x180052fb4`
- `0x180080da0`
- `0x1800dbf20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033acf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033aec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033acf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033aec`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180033ba3`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180033ba3`
- `ntdll!RtlDeleteResource` at `0x180033bc8`
- `ntdll!RtlDeleteResource` at `0x180033bc8`
- `ntdll!RtlIsMultiSessionSku` at `0x180033afd`
- `ntdll!RtlIsMultiSessionSku` at `0x180033afd`
- `ntdll!RtlDeleteCriticalSection` at `0x180033bf0`
- `ntdll!RtlDeleteCriticalSection` at `0x180033bf0`
- `api-ms-win-core-featurestaging-l1-1-0!UnsubscribeFeatureStateChangeNotification` at `0x180033b0f`
- `api-ms-win-core-featurestaging-l1-1-0!UnsubscribeFeatureStateChangeNotification` at `0x180033b0f`
- `EFSUTIL!EfsUtilFreeParsedRecoveryPolicy` at `0x180033bbb`
- `EFSUTIL!EfsUtilFreeParsedRecoveryPolicy` at `0x180033bbb`

## pseudocode

```c
void EfsUnInit()
{
  __int64 v0; // rdx

  EfsDllInitialized = 0;
  if ( TemplateName )
  {
    LocalFree(TemplateName);
    TemplateName = 0;
  }
  if ( SuiteBAlgorithm )
  {
    LocalFree(SuiteBAlgorithm);
    SuiteBAlgorithm = 0;
  }
  RtlIsMultiSessionSku();
  if ( g_DplFeatureStageChange )
  {
    UnsubscribeFeatureStateChangeNotification(g_DplFeatureStageChange);
    g_DplFeatureStageChange = 0;
  }
  EfsCleanupDecryptionProcessing();
  EfspCleanupFileEncryptionQueue();
  EdpCleanupAuditWorkQueue();
  EdpCleanupAuditSiteWorkQueue();
  EfspUnregisterNotifications();
  if ( DestinationString.Buffer )
    EfsFreeHeap(DestinationString.Buffer);
  if ( stru_1801171A0.Buffer )
    EfsFreeHeap(stru_1801171A0.Buffer);
  if ( EfsSidInfo )
    EfsFreeHeap(EfsSidInfo);
  if ( *(&EfsSidInfo + 1) )
    EfsFreeHeap(*(&EfsSidInfo + 1));
  *(_OWORD *)&EfsSidInfo = 0;
  DestinationString = 0;
  stru_1801171A0 = 0;
  if ( g_hAesAlg )
  {
    BCryptCloseAlgorithmProvider(g_hAesAlg, 0);
    g_hAesAlg = 0;
  }
  EfsUtilFreeParsedRecoveryPolicy(&CurrentRecoveryPolicy);
  RtlDeleteResource(&RecoveryPolicyResource);
  if ( bGuardCacheListLockInitialized )
  {
    EfsPurgeUserCache(0, v0, 0);
    bGuardCacheListLockInitialized = 0;
    RtlDeleteCriticalSection(&GuardCacheListLock);
  }
  if ( EfslCallTable )
  {
    EfsFreeHeap(EfslCallTable);
    EfslCallTable = 0;
  }
  if ( EfsxCallTable )
  {
    EfsFreeHeap(EfsxCallTable);
    EfsxCallTable = 0;
  }
  if ( EfsPFileCallTable )
  {
    EfsFreeHeap(EfsPFileCallTable);
    EfsPFileCallTable = 0;
  }
  EdpCredSvcCleanup();
}

```

## disassembly

```asm
0x180033ab8  sub     rsp, 28h
0x180033abc  mov     rcx, cs:?TemplateName@@3PEAGEA; hMem
0x180033ac3  mov     cs:?EfsDllInitialized@@3EA, 0; uchar EfsDllInitialized
0x180033aca  test    rcx, rcx
0x180033acd  jz      short loc_180033AE0
0x180033acf  call    cs:__imp_LocalFree
0x180033ad5  mov     cs:?TemplateName@@3PEAGEA, 0; ushort * TemplateName
0x180033ae0  mov     rcx, cs:?SuiteBAlgorithm@@3PEAGEA; hMem
0x180033ae7  test    rcx, rcx
0x180033aea  jz      short loc_180033AFD
0x180033aec  call    cs:__imp_LocalFree
0x180033af2  mov     cs:?SuiteBAlgorithm@@3PEAGEA, 0; ushort * SuiteBAlgorithm
0x180033afd  call    cs:__imp_RtlIsMultiSessionSku
0x180033b03  mov     rcx, cs:?g_DplFeatureStageChange@@3PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@EA; subscription
0x180033b0a  test    rcx, rcx
0x180033b0d  jz      short loc_180033B20
0x180033b0f  call    cs:__imp_UnsubscribeFeatureStateChangeNotification
0x180033b15  mov     cs:?g_DplFeatureStageChange@@3PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@EA, 0; FEATURE_STATE_CHANGE_SUBSCRIPTION__ * g_DplFeatureStageChange
0x180033b20  call    ?EfsCleanupDecryptionProcessing@@YAXXZ; EfsCleanupDecryptionProcessing(void)
0x180033b25  call    ?EfspCleanupFileEncryptionQueue@@YAXXZ; EfspCleanupFileEncryptionQueue(void)
0x180033b2a  call    EdpCleanupAuditWorkQueue
0x180033b2f  call    EdpCleanupAuditSiteWorkQueue
0x180033b34  call    ?EfspUnregisterNotifications@@YAXXZ; EfspUnregisterNotifications(void)
0x180033b39  mov     rcx, cs:DestinationString.Buffer; lpMem
0x180033b40  test    rcx, rcx
0x180033b43  jz      short loc_180033B4A
0x180033b45  call    EfsFreeHeap
0x180033b4a  mov     rcx, cs:stru_1801171A0.Buffer; lpMem
0x180033b51  test    rcx, rcx
0x180033b54  jz      short loc_180033B5B
0x180033b56  call    EfsFreeHeap
0x180033b5b  mov     rcx, qword ptr cs:?EfsSidInfo@@3U_EFS_SID_INFORMATION@@A; lpMem
0x180033b62  test    rcx, rcx
0x180033b65  jz      short loc_180033B6C
0x180033b67  call    EfsFreeHeap
0x180033b6c  mov     rcx, qword ptr cs:?EfsSidInfo@@3U_EFS_SID_INFORMATION@@A+8; lpMem
0x180033b73  test    rcx, rcx
0x180033b76  jz      short loc_180033B7D
0x180033b78  call    EfsFreeHeap
0x180033b7d  mov     rcx, cs:?g_hAesAlg@@3PEAXEA; hAlgorithm
0x180033b84  xorps   xmm0, xmm0
0x180033b87  movups  cs:?EfsSidInfo@@3U_EFS_SID_INFORMATION@@A, xmm0; _EFS_SID_INFORMATION EfsSidInfo
0x180033b8e  movups  xmmword ptr cs:DestinationString.Length, xmm0
0x180033b95  movups  xmmword ptr cs:stru_1801171A0.Length, xmm0
0x180033b9c  test    rcx, rcx
0x180033b9f  jz      short loc_180033BB4
0x180033ba1  xor     edx, edx; dwFlags
0x180033ba3  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180033ba9  mov     cs:?g_hAesAlg@@3PEAXEA, 0; void * g_hAesAlg
0x180033bb4  lea     rcx, ?CurrentRecoveryPolicy@@3U_CURRENT_RECOVERY_POLICY@@A; _CURRENT_RECOVERY_POLICY CurrentRecoveryPolicy
0x180033bbb  call    cs:__imp_EfsUtilFreeParsedRecoveryPolicy
0x180033bc1  lea     rcx, ?RecoveryPolicyResource@@3U_RTL_RESOURCE@@A; Resource
0x180033bc8  call    cs:__imp_RtlDeleteResource
0x180033bce  mov     al, cs:?bGuardCacheListLockInitialized@@3EC; uchar volatile bGuardCacheListLockInitialized
0x180033bd4  test    al, al
0x180033bd6  jz      short loc_180033BF6
0x180033bd8  xor     r8d, r8d
0x180033bdb  xor     ecx, ecx
0x180033bdd  call    EfsPurgeUserCache
0x180033be2  lea     rcx, ?GuardCacheListLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180033be9  mov     cs:?bGuardCacheListLockInitialized@@3EC, 0; uchar volatile bGuardCacheListLockInitialized
0x180033bf0  call    cs:__imp_RtlDeleteCriticalSection
0x180033bf6  mov     rcx, cs:?EfslCallTable@@3PEAU_EFS_CALLTABLE@@EA; lpMem
0x180033bfd  test    rcx, rcx
0x180033c00  jz      short loc_180033C12
0x180033c02  call    EfsFreeHeap
0x180033c07  mov     cs:?EfslCallTable@@3PEAU_EFS_CALLTABLE@@EA, 0; _EFS_CALLTABLE * EfslCallTable
0x180033c12  mov     rcx, cs:?EfsxCallTable@@3PEAU_EFS_CALLTABLE@@EA; lpMem
0x180033c19  test    rcx, rcx
0x180033c1c  jz      short loc_180033C2E
0x180033c1e  call    EfsFreeHeap
0x180033c23  mov     cs:?EfsxCallTable@@3PEAU_EFS_CALLTABLE@@EA, 0; _EFS_CALLTABLE * EfsxCallTable
0x180033c2e  mov     rcx, cs:?EfsPFileCallTable@@3PEAU_EFS_CALLTABLE@@EA; lpMem
0x180033c35  test    rcx, rcx
0x180033c38  jz      short loc_180033C4A
0x180033c3a  call    EfsFreeHeap
0x180033c3f  mov     cs:?EfsPFileCallTable@@3PEAU_EFS_CALLTABLE@@EA, 0; _EFS_CALLTABLE * EfsPFileCallTable
0x180033c4a  add     rsp, 28h
0x180033c4e  jmp     ?EdpCredSvcCleanup@@YAXXZ; EdpCredSvcCleanup(void)
```
