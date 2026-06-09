# CAdapter::CleanupDataPath(void)

- ea: `0x1400a139c`
- end: `0x1400a14e8`
- name: `?CleanupDataPath@CAdapter@@QEAAXXZ`
- size: `332`
- prototype: `void __fastcall(CAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400a8b78`

## callees

- `0x140034e04`
- `0x140034ec4`
- `0x14009d3b4`
- `0x1400a139c`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a148e`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400a148e`
- `NDIS!NdisFreeIoWorkItem` at `0x1400a1448`
- `NDIS!NdisFreeIoWorkItem` at `0x1400a1448`

## pseudocode

```c
void __fastcall CAdapter::CleanupDataPath(CAdapter *this)
{
  unsigned int m_InitializationState; // eax
  void *m_hRxWorkItem; // rcx
  int v4; // [rsp+28h] [rbp-30h]

  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      140,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids);
  }
  m_InitializationState = this->m_InitializationState;
  if ( (m_InitializationState & 0x10) != 0 )
  {
    CTxMgr::Deinitialize(&this->m_TxMgr);
    ((void (__fastcall *)(void *))this->m_MiniportDataHandlers.TalTxRxStopHandler)(this->m_MiniportTalTxRxContext);
    this->m_InitializationState &= ~0x10u;
    m_InitializationState = this->m_InitializationState;
  }
  if ( (m_InitializationState & 8) != 0 )
  {
    ((void (__fastcall *)(void *))this->m_MiniportDriver->m_MiniportWdiCharacteristics.TalTxRxDeinitializeHandler)(this->m_MiniportTalTxRxContext);
    m_hRxWorkItem = this->m_RxMgr.m_hRxWorkItem;
    if ( m_hRxWorkItem )
    {
      NdisFreeIoWorkItem(m_hRxWorkItem);
      this->m_RxMgr.m_hRxWorkItem = 0;
    }
    this->m_RxMgr.m_pAdapter = 0;
    this->m_RxMgr.m_hTalTxRx = 0;
    this->m_RxMgr.m_pWfcDataPathCapabilities = 0;
    this->m_RxMgr.m_pMpWdiDataHandlers = 0;
    this->m_InitializationState &= ~8u;
  }
  if ( this->m_WfcFrameLookasideInitialized )
  {
    ExDeleteNPagedLookasideList(&this->m_WfcFrameLookaside);
    this->m_WfcFrameLookasideInitialized = 0;
  }
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    v4 = 0;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      141,
      (__int64)WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids,
      v4);
  }
}

```

## disassembly

```asm
0x1400a139c  push    rbx
0x1400a139e  push    rsi
0x1400a139f  push    rdi
0x1400a13a0  push    r14
0x1400a13a2  sub     rsp, 38h
0x1400a13a6  mov     rbx, rcx
0x1400a13a9  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a13b0  xor     edi, edi
0x1400a13b2  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400a13b9  lea     r14, WPP_0cfa1f83e4443c7ca130a647d64f2055_Traceguids
0x1400a13c0  jz      short loc_1400A13F1
0x1400a13c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a13c9  cmp     byte ptr [rcx+29h], 5
0x1400a13cd  jnb     short loc_1400A13D5
0x1400a13cf  cmp     [rcx+48h], di
0x1400a13d3  jz      short loc_1400A13F1
0x1400a13d5  mov     rcx, [rcx+40h]
0x1400a13d9  mov     r9d, 8Ch
0x1400a13df  mov     r8d, 1
0x1400a13e5  mov     [rsp+58h+var_38], r14
0x1400a13ea  mov     dl, 5
0x1400a13ec  call    WPP_RECORDER_SF_
0x1400a13f1  mov     eax, [rbx+12F0h]
0x1400a13f7  test    al, 10h
0x1400a13f9  jz      short loc_1400A1424
0x1400a13fb  lea     rcx, [rbx+3A10h]; this
0x1400a1402  call    ?Deinitialize@CTxMgr@@QEAAHXZ; CTxMgr::Deinitialize(void)
0x1400a1407  mov     rax, [rbx+3ECCh]
0x1400a140e  mov     rcx, [rbx+70h]
0x1400a1412  call    _guard_dispatch_icall
0x1400a1417  and     dword ptr [rbx+12F0h], 0FFFFFFEFh
0x1400a141e  mov     eax, [rbx+12F0h]
0x1400a1424  test    al, 8
0x1400a1426  jz      short loc_1400A147E
0x1400a1428  mov     rax, [rbx+68h]
0x1400a142c  mov     rcx, [rbx+70h]
0x1400a1430  mov     rax, [rax+128h]
0x1400a1437  call    _guard_dispatch_icall
0x1400a143c  mov     rcx, [rbx+3BE0h]; NdisIoWorkItemHandle
0x1400a1443  test    rcx, rcx
0x1400a1446  jz      short loc_1400A145B
0x1400a1448  call    cs:__imp_NdisFreeIoWorkItem
0x1400a144f  nop     dword ptr [rax+rax+00h]
0x1400a1454  mov     [rbx+3BE0h], rdi
0x1400a145b  mov     [rbx+3BC0h], rdi
0x1400a1462  mov     [rbx+3BB8h], rdi
0x1400a1469  mov     [rbx+3BF8h], rdi
0x1400a1470  mov     [rbx+3C00h], rdi
0x1400a1477  and     dword ptr [rbx+12F0h], 0FFFFFFF7h
0x1400a147e  cmp     [rbx+15C0h], dil
0x1400a1485  jz      short loc_1400A14A1
0x1400a1487  lea     rcx, [rbx+1540h]; Lookaside
0x1400a148e  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400a1495  nop     dword ptr [rax+rax+00h]
0x1400a149a  mov     [rbx+15C0h], dil
0x1400a14a1  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400a14a8  jz      short loc_1400A14DD
0x1400a14aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a14b1  cmp     byte ptr [rcx+29h], 5
0x1400a14b5  jnb     short loc_1400A14BD
0x1400a14b7  cmp     [rcx+48h], di
0x1400a14bb  jz      short loc_1400A14DD
0x1400a14bd  mov     rcx, [rcx+40h]
0x1400a14c1  mov     r9d, 8Dh
0x1400a14c7  mov     [rsp+58h+var_30], edi
0x1400a14cb  mov     r8d, 1
0x1400a14d1  mov     dl, 5
0x1400a14d3  mov     [rsp+58h+var_38], r14
0x1400a14d8  call    WPP_RECORDER_SF_D
0x1400a14dd  add     rsp, 38h
0x1400a14e1  pop     r14
0x1400a14e3  pop     rdi
0x1400a14e4  pop     rsi
0x1400a14e5  pop     rbx
0x1400a14e6  retn
```
