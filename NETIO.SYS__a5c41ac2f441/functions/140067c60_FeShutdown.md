# FeShutdown

- ea: `0x140067c60`
- end: `0x140067f98`
- name: `FeShutdown`
- size: `824`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140061590`
- `0x14006ad28`
- `0x1400aa530`

## callees

- `0x140006c40`
- `0x14001cfe0`
- `0x14001d050`
- `0x140041db0`
- `0x14005ba20`
- `0x140065f80`
- `0x140067c60`
- `0x140068104`
- `0x14006896c`
- `0x140068b34`
- `0x140068b68`
- `0x14006b424`
- `0x14006c620`
- `0x1400a9a70`
- `0x1400a9aa4`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140067de8`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140067de8`
- `NDIS!NdisFreeGenericObject` at `0x140067f41`
- `NDIS!NdisFreeGenericObject` at `0x140067f41`
- `NDIS!NdisFreeRWLock` at `0x140067e1b`
- `NDIS!NdisFreeRWLock` at `0x140067e97`
- `NDIS!NdisFreeRWLock` at `0x140067ecd`
- `NDIS!NdisFreeRWLock` at `0x140067f6c`
- `NDIS!NdisFreeRWLock` at `0x140067e1b`
- `NDIS!NdisFreeRWLock` at `0x140067e97`
- `NDIS!NdisFreeRWLock` at `0x140067ecd`
- `NDIS!NdisFreeRWLock` at `0x140067f6c`

## pseudocode

```c
__int64 __fastcall FeShutdown(int a1)
{
  unsigned int i; // edi
  PNPAGED_LOOKASIDE_LIST v3; // rdi
  PNPAGED_LOOKASIDE_LIST v4; // rbx
  PNPAGED_LOOKASIDE_LIST v5; // rbx
  struct _SINGLE_LIST_ENTRY *Next; // rcx
  __int16 v8; // [rsp+38h] [rbp+10h] BYREF
  char v9; // [rsp+3Ah] [rbp+12h]

  v8 = 0;
  v9 = 0;
  if ( gWfpGlobal )
  {
    if ( !a1 )
      LODWORD(gWfpGlobal[1].L.ListEntry.Flink) = 0;
    BYTE4(gWfpGlobal[1].L.Free) = 1;
    if ( !a1 )
    {
      NetioShutdownWorkQueue(&gWfpGlobal[10].L.SingleListHead + 1);
      LODWORD(gWfpGlobal[1].L.FreeEx) = 0;
    }
    while ( gWfpGlobal[9].L.Tag )
      WFPDelayExecution();
    if ( *((_DWORD *)&gWfpGlobal[1].L.SingleListHead + 3) )
      FeAcquireWriteEngineLock(&v8, 0);
    if ( HIDWORD(gWfpGlobal[1].L.Allocate) )
    {
      for ( i = 0; i < 4; ++i )
        FreeCache(&gWfpGlobal[7].L.Depth + 24 * i, (unsigned __int16)i);
      HIDWORD(gWfpGlobal[1].L.Allocate) = 0;
    }
    if ( gWfpGlobal[8].L.Future[0] == 1 )
    {
      FreeCache(&gWfpGlobal[8].L.Future[2], 0);
      gWfpGlobal[8].L.Future[0] = 0;
    }
    if ( gWfpGlobal[1].L.TotalAllocates )
    {
      FreeLayers();
      gWfpGlobal[1].L.TotalAllocates = 0;
    }
    if ( !a1 && gWfpGlobal[3].L.ListHead.Alignment )
      WfpPoolFree(&gWfpGlobal[3]);
    if ( gWfpGlobal[1].L.FreeMisses )
    {
      FilterHashTableEmpty(*(PRTL_DYNAMIC_HASH_TABLE *)&gWfpGlobal[3].L.Depth);
      DestroyCombinedHashTable((__int64)&gWfpGlobal[8].L.ListEntry.Blink);
      gWfpGlobal[1].L.FreeMisses = 0;
    }
    if ( *((_DWORD *)&gWfpGlobal[1].L.SingleListHead + 2) )
    {
      ExDeleteNPagedLookasideList(gWfpGlobal);
      *((_DWORD *)&gWfpGlobal[1].L.SingleListHead + 2) = 0;
    }
    if ( !a1 )
    {
      v3 = gWfpGlobal;
      if ( LODWORD(gWfpGlobal[1].L.AllocateEx) )
      {
        NdisFreeRWLock((PNDIS_RW_LOCK_EX)gWfpGlobal[3].L.AllocateEx);
        v3[3].L.AllocateEx = 0;
        LODWORD(gWfpGlobal[1].L.AllocateEx) = 0;
      }
    }
    if ( *((_DWORD *)&gWfpGlobal[1].L.SingleListHead + 3) )
      WfpReleaseFastWriteLock(&gWfpGlobal[1], &v8);
    if ( !a1 )
    {
      if ( gWfpGlobal[1].L.AllocateMisses )
      {
        FeDestroyCalloutTable();
        gWfpGlobal[1].L.AllocateMisses = 0;
      }
      v4 = gWfpGlobal;
      if ( *(_DWORD *)&gWfpGlobal[1].L.Depth )
      {
        NdisFreeRWLock((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink);
        v4[13].L.ListEntry.Flink = 0;
        *(_DWORD *)&gWfpGlobal[1].L.Depth = 0;
      }
      v5 = gWfpGlobal;
      if ( *((_DWORD *)&gWfpGlobal[1].L.SingleListHead + 3) )
      {
        NdisFreeRWLock((PNDIS_RW_LOCK_EX)gWfpGlobal[1].L.ListHead.Alignment);
        v5[1].L.ListHead.Alignment = 0;
        *((_DWORD *)&gWfpGlobal[1].L.SingleListHead + 3) = 0;
      }
      NetioShutdownWorkQueue(&gWfpGlobal[10].L.FreeEx);
      Next = gWfpGlobal[11].L.SingleListHead.Next;
      if ( Next )
        NetioFreeStackBlock(Next, 0x42706657u);
      WfpObjectManagerClose();
      WfpPoolFree(&gWfpGlobal);
      gWfpGlobal = 0;
      if ( gNdisGenericObject )
        NdisFreeGenericObject((PNDIS_GENERIC_OBJECT)gNdisGenericObject);
    }
    wil_details_UnregisterFeatureStagingChangeNotification();
    wil_details_UnregisterFeatureUsageProvider();
    *((_DWORD *)&WPP_MAIN_CB.Reserved + 2) = 0;
    if ( gLayerStatsLockInitialized )
    {
      NdisFreeRWLock(gLayerStatsLock);
      gLayerStatsLock = 0;
      gLayerStatsLockInitialized = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140067c60  mov     [rsp+arg_0], rbx
0x140067c65  mov     [rsp+arg_10], rsi
0x140067c6a  push    rdi
0x140067c6b  sub     rsp, 20h
0x140067c6f  xor     eax, eax
0x140067c71  xor     esi, esi
0x140067c73  mov     [rsp+28h+arg_8], ax
0x140067c78  mov     ebx, ecx
0x140067c7a  mov     [rsp+28h+arg_A], al
0x140067c7e  mov     rax, cs:gWfpGlobal
0x140067c85  test    rax, rax
0x140067c88  jz      loc_140067F85
0x140067c8e  test    ecx, ecx
0x140067c90  jnz     short loc_140067C98
0x140067c92  mov     [rax+0C0h], esi
0x140067c98  mov     rax, cs:gWfpGlobal
0x140067c9f  mov     byte ptr [rax+0BCh], 1
0x140067ca6  test    ebx, ebx
0x140067ca8  jnz     short loc_140067CD1
0x140067caa  mov     rcx, cs:gWfpGlobal
0x140067cb1  add     rcx, 508h
0x140067cb8  call    NetioShutdownWorkQueue
0x140067cbd  mov     rax, cs:gWfpGlobal
0x140067cc4  mov     [rax+0B8h], esi
0x140067cca  jmp     short loc_140067CD1
0x140067ccc  call    WFPDelayExecution
0x140067cd1  mov     rax, cs:gWfpGlobal
0x140067cd8  cmp     [rax+4A8h], esi
0x140067cde  jnz     short loc_140067CCC
0x140067ce0  cmp     [rax+8Ch], esi
0x140067ce6  jz      short loc_140067CF4
0x140067ce8  xor     edx, edx
0x140067cea  lea     rcx, [rsp+28h+arg_8]
0x140067cef  call    FeAcquireWriteEngineLock
0x140067cf4  mov     rax, cs:gWfpGlobal
0x140067cfb  cmp     [rax+0B4h], esi
0x140067d01  jz      short loc_140067D36
0x140067d03  mov     edi, esi
0x140067d05  mov     eax, edi
0x140067d07  movzx   edx, di
0x140067d0a  add     rax, 13h
0x140067d0e  lea     rcx, [rax+rax*2]
0x140067d12  shl     rcx, 4
0x140067d16  add     rcx, cs:gWfpGlobal
0x140067d1d  call    FreeCache
0x140067d22  inc     edi
0x140067d24  cmp     edi, 4
0x140067d27  jb      short loc_140067D05
0x140067d29  mov     rax, cs:gWfpGlobal
0x140067d30  mov     [rax+0B4h], esi
0x140067d36  mov     rcx, cs:gWfpGlobal
0x140067d3d  cmp     dword ptr [rcx+458h], 1
0x140067d44  jnz     short loc_140067D61
0x140067d46  xor     edx, edx
0x140067d48  add     rcx, 460h
0x140067d4f  call    FreeCache
0x140067d54  mov     rax, cs:gWfpGlobal
0x140067d5b  mov     [rax+458h], esi
0x140067d61  mov     rax, cs:gWfpGlobal
0x140067d68  cmp     [rax+94h], esi
0x140067d6e  jz      short loc_140067D82
0x140067d70  call    FreeLayers
0x140067d75  mov     rax, cs:gWfpGlobal
0x140067d7c  mov     [rax+94h], esi
0x140067d82  test    ebx, ebx
0x140067d84  jnz     short loc_140067D9E
0x140067d86  mov     rcx, cs:gWfpGlobal
0x140067d8d  add     rcx, 180h
0x140067d94  cmp     [rcx], rsi
0x140067d97  jz      short loc_140067D9E
0x140067d99  call    WfpPoolFree
0x140067d9e  mov     rcx, cs:gWfpGlobal
0x140067da5  cmp     [rcx+0A0h], esi
0x140067dab  jz      short loc_140067DD9
0x140067dad  mov     rcx, [rcx+190h]; HashTable
0x140067db4  call    FilterHashTableEmpty
0x140067db9  mov     rcx, cs:gWfpGlobal
0x140067dc0  add     rcx, 448h
0x140067dc7  call    DestroyCombinedHashTable
0x140067dcc  mov     rax, cs:gWfpGlobal
0x140067dd3  mov     [rax+0A0h], esi
0x140067dd9  mov     rcx, cs:gWfpGlobal; Lookaside
0x140067de0  cmp     [rcx+88h], esi
0x140067de6  jz      short loc_140067E01
0x140067de8  call    cs:__imp_ExDeleteNPagedLookasideList
0x140067def  nop     dword ptr [rax+rax+00h]
0x140067df4  mov     rax, cs:gWfpGlobal
0x140067dfb  mov     [rax+88h], esi
0x140067e01  test    ebx, ebx
0x140067e03  jnz     short loc_140067E3B
0x140067e05  mov     rdi, cs:gWfpGlobal
0x140067e0c  cmp     [rdi+0B0h], esi
0x140067e12  jz      short loc_140067E3B
0x140067e14  mov     rcx, [rdi+1B0h]; Lock
0x140067e1b  call    cs:__imp_NdisFreeRWLock
0x140067e22  nop     dword ptr [rax+rax+00h]
0x140067e27  mov     [rdi+1B0h], rsi
0x140067e2e  mov     rax, cs:gWfpGlobal
0x140067e35  mov     [rax+0B0h], esi
0x140067e3b  mov     rcx, cs:gWfpGlobal
0x140067e42  cmp     [rcx+8Ch], esi
0x140067e48  jz      short loc_140067E58
0x140067e4a  sub     rcx, 0FFFFFFFFFFFFFF80h
0x140067e4e  lea     rdx, [rsp+28h+arg_8]
0x140067e53  call    WfpReleaseFastWriteLock
0x140067e58  test    ebx, ebx
0x140067e5a  jnz     loc_140067F4D
0x140067e60  mov     rax, cs:gWfpGlobal
0x140067e67  cmp     [rax+98h], esi
0x140067e6d  jz      short loc_140067E81
0x140067e6f  call    FeDestroyCalloutTable
0x140067e74  mov     rax, cs:gWfpGlobal
0x140067e7b  mov     [rax+98h], esi
0x140067e81  mov     rbx, cs:gWfpGlobal
0x140067e88  cmp     [rbx+90h], esi
0x140067e8e  jz      short loc_140067EB7
0x140067e90  mov     rcx, [rbx+6C0h]; Lock
0x140067e97  call    cs:__imp_NdisFreeRWLock
0x140067e9e  nop     dword ptr [rax+rax+00h]
0x140067ea3  mov     [rbx+6C0h], rsi
0x140067eaa  mov     rax, cs:gWfpGlobal
0x140067eb1  mov     [rax+90h], esi
0x140067eb7  mov     rbx, cs:gWfpGlobal
0x140067ebe  cmp     [rbx+8Ch], esi
0x140067ec4  jz      short loc_140067EED
0x140067ec6  mov     rcx, [rbx+80h]; Lock
0x140067ecd  call    cs:__imp_NdisFreeRWLock
0x140067ed4  nop     dword ptr [rax+rax+00h]
0x140067ed9  mov     [rbx+80h], rsi
0x140067ee0  mov     rax, cs:gWfpGlobal
0x140067ee7  mov     [rax+8Ch], esi
0x140067eed  mov     rcx, cs:gWfpGlobal
0x140067ef4  add     rcx, 538h
0x140067efb  call    NetioShutdownWorkQueue
0x140067f00  mov     rax, cs:gWfpGlobal
0x140067f07  mov     rcx, [rax+580h]; P
0x140067f0e  test    rcx, rcx
0x140067f11  jz      short loc_140067F1D
0x140067f13  mov     edx, 42706657h; Tag
0x140067f18  call    NetioFreeStackBlock
0x140067f1d  call    WfpObjectManagerClose
0x140067f22  lea     rcx, gWfpGlobal
0x140067f29  call    WfpPoolFree
0x140067f2e  mov     rcx, cs:gNdisGenericObject; NdisObject
0x140067f35  mov     cs:gWfpGlobal, rsi
0x140067f3c  test    rcx, rcx
0x140067f3f  jz      short loc_140067F4D
0x140067f41  call    cs:__imp_NdisFreeGenericObject
0x140067f48  nop     dword ptr [rax+rax+00h]
0x140067f4d  call    wil_details_UnregisterFeatureStagingChangeNotification
0x140067f52  call    wil_details_UnregisterFeatureUsageProvider
0x140067f57  cmp     cs:gLayerStatsLockInitialized, esi
0x140067f5d  mov     dword ptr cs:WPP_MAIN_CB+148h, esi
0x140067f63  jz      short loc_140067F85
0x140067f65  mov     rcx, cs:gLayerStatsLock; Lock
0x140067f6c  call    cs:__imp_NdisFreeRWLock
0x140067f73  nop     dword ptr [rax+rax+00h]
0x140067f78  mov     cs:gLayerStatsLock, rsi
0x140067f7f  mov     cs:gLayerStatsLockInitialized, esi
0x140067f85  mov     rbx, [rsp+28h+arg_0]
0x140067f8a  xor     eax, eax
0x140067f8c  mov     rsi, [rsp+28h+arg_10]
0x140067f91  add     rsp, 20h
0x140067f95  pop     rdi
0x140067f96  retn
```
