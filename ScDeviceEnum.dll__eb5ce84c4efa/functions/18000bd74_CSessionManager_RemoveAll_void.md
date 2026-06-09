# CSessionManager::RemoveAll(void)

- ea: `0x18000bd74`
- end: `0x18000bdfb`
- name: `?RemoveAll@CSessionManager@@SAXXZ`
- size: `135`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006ad0`

## callees

- `0x1800080dc`
- `0x18000ba94`
- `0x18000bd74`
- `0x18000c108`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bdf0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bdf0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000bdb9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000bdb9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000bdcb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18000bdcb`

## pseudocode

```c
void CSessionManager::RemoveAll(void)
{
  struct CSessionManager *v0; // rax
  struct CSessionManager *v1; // rax
  struct CSessionManager *v2; // rax
  struct CSessionManager *v3; // rax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp+8h] BYREF

  v0 = CSessionManager::Instance();
  Microsoft::WRL::Wrappers::CriticalSection::Lock(&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)v0 + 16));
  v1 = CSessionManager::Instance();
  std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<CSession>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<CSession>>>,0>>::clear(v1);
  if ( *((_QWORD *)CSessionManager::Instance() + 16) )
  {
    v2 = CSessionManager::Instance();
    CloseThreadpoolCleanupGroupMembers(*((PTP_CLEANUP_GROUP *)v2 + 16), 0, 0);
    v3 = CSessionManager::Instance();
    CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)v3 + 16));
    CSessionManager::Instance();
    *((_QWORD *)CSessionManager::Instance() + 16) = 0;
  }
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18000bd74  sub     rsp, 28h
0x18000bd78  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000bd7d  lea     rdx, [rax+10h]
0x18000bd81  lea     rcx, [rsp+28h+lpCriticalSection]
0x18000bd86  call    ?Lock@CriticalSection@Wrappers@WRL@Microsoft@@SA?AVSyncLockCriticalSection@Details@234@PEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::CriticalSection::Lock(_RTL_CRITICAL_SECTION *)
0x18000bd8b  nop
0x18000bd8c  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000bd91  mov     rcx, rax
0x18000bd94  call    ?clear@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@VCSession@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@VCSession@@@std@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<CSession>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<CSession>>>,0>>::clear(void)
0x18000bd99  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000bd9e  cmp     qword ptr [rax+80h], 0
0x18000bda6  jz      short loc_18000BDE6
0x18000bda8  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000bdad  xor     r8d, r8d; pvCleanupContext
0x18000bdb0  xor     edx, edx; fCancelPendingCallbacks
0x18000bdb2  mov     rcx, [rax+80h]; ptpcg
0x18000bdb9  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18000bdbf  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000bdc4  mov     rcx, [rax+80h]; ptpcg
0x18000bdcb  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18000bdd1  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000bdd6  call    ?Instance@CSessionManager@@SAAEAV1@XZ; CSessionManager::Instance(void)
0x18000bddb  mov     qword ptr [rax+80h], 0
0x18000bde6  mov     rcx, [rsp+28h+lpCriticalSection]; lpCriticalSection
0x18000bdeb  test    rcx, rcx
0x18000bdee  jz      short loc_18000BDF6
0x18000bdf0  call    cs:__imp_LeaveCriticalSection
0x18000bdf6  add     rsp, 28h
0x18000bdfa  retn
```
