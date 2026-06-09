# CTxMgr::Initialize(CAdapter *,_WFC_DATAPATH_CAPABILITIES *,uchar)

- ea: `0x14007d678`
- end: `0x14007da34`
- name: `?Initialize@CTxMgr@@QEAAHPEAVCAdapter@@PEAU_WFC_DATAPATH_CAPABILITIES@@E@Z`
- size: `956`
- prototype: `__int64 __fastcall(CTxMgr *__hidden this, struct CAdapter *, struct _WFC_DATAPATH_CAPABILITIES *, unsigned __int8)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400a38f8`

## callees

- `0x1400176b0`
- `0x140025d38`
- `0x140026490`
- `0x140034e04`
- `0x140034ec4`
- `0x1400687e0`
- `0x14007d678`
- `0x14007dd18`
- `0x14009ca2c`
- `0x14009d45c`
- `0x1400da680`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14007d7bf`
- `ntoskrnl!ExAllocatePool2` at `0x14007d7bf`
- `NDIS!NdisAllocateIoWorkItem` at `0x14007d904`
- `NDIS!NdisAllocateIoWorkItem` at `0x14007d904`

## pseudocode

```c
__int64 __fastcall CTxMgr::Initialize(CTxMgr *this, struct CAdapter *a2, struct _WFC_DATAPATH_CAPABILITIES *a3)
{
  struct CAdapter *m_pAdapter; // rsi
  _WFC_TX_QUEUEING_MODE v6; // eax
  enum _WFC_TX_QUEUEING_MODE m_QueueingMode; // r9d
  unsigned __int8 m_MaxNumPorts; // r8
  int v9; // edx
  unsigned int PropertyULong; // ebx
  int v11; // r9d
  CACList *Pool2; // rax
  CACList *v13; // rax
  int v14; // r9d
  CAdapterPropertyCache *v15; // rax
  NDIS_HANDLE IoWorkItem; // rax
  unsigned int NextActivityId; // eax
  __int64 v18; // r10
  unsigned int v19; // eax
  int v20; // edx
  __int64 v22; // [rsp+28h] [rbp-60h]

  m_pAdapter = a2;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      88,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
  }
  if ( !m_pAdapter || !a3 || !a3->MaxNumPeers )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        89,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
    }
    PropertyULong = -1073741823;
    goto LABEL_51;
  }
  this->m_pAdapter = m_pAdapter;
  this->m_pDatapathCapabilities = a3;
  this->m_MaxNumPorts = 5;
  v6 = a3->TxTargetPriorityQueueing != 0;
  this->m_QueueingMode = v6;
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v22) = v6;
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      90,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
    m_pAdapter = this->m_pAdapter;
  }
  m_QueueingMode = this->m_QueueingMode;
  if ( m_QueueingMode == PORT_QUEUEING )
    m_MaxNumPorts = this->m_MaxNumPorts;
  else
    m_MaxNumPorts = a3->MaxNumPeers;
  PropertyULong = CTxEntryTable::Initialize(&this->m_TxEntryTable, m_pAdapter, m_MaxNumPorts, m_QueueingMode);
  if ( PropertyULong )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return PropertyULong;
    v11 = 91;
    goto LABEL_16;
  }
  if ( this->m_QueueingMode == PEER_QUEUEING )
  {
    Pool2 = (CACList *)ExAllocatePool2(64, 264, 1198089303);
    v13 = Pool2 ? CACList::CACList(Pool2) : 0LL;
    this->m_pACList = v13;
    if ( !v13 )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      {
LABEL_25:
        PropertyULong = -1073741670;
        goto LABEL_51;
      }
      v14 = 92;
LABEL_24:
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        v14,
        (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
      goto LABEL_25;
    }
  }
  v15 = this->m_pAdapter->GetAdapterPropertyCache(&this->m_pAdapter->IPropertyCacheDirectory);
  PropertyULong = CPropertyCache::GetPropertyULong(v15, 0x6Eu, &this->m_BackFillSize);
  if ( PropertyULong )
  {
    if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      return PropertyULong;
    v11 = 93;
  }
  else
  {
    PropertyULong = CNdisSpinLock::CreateInstance(&this->m_TxMgrLock);
    if ( PropertyULong )
    {
      if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return PropertyULong;
      v11 = 94;
    }
    else
    {
      PropertyULong = CNdisSpinLock::CreateInstance(&this->m_TxTargetDescLock);
      if ( PropertyULong )
      {
        if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          return PropertyULong;
        v11 = 95;
      }
      else
      {
        PropertyULong = CNdisSpinLock::CreateInstance(&this->m_TxTargetDescDeinitLock);
        if ( PropertyULong )
        {
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
            return PropertyULong;
          v11 = 96;
        }
        else
        {
          PropertyULong = CNdisSpinLock::CreateInstance(&this->m_TxPrequeueLock);
          if ( !PropertyULong )
          {
            IoWorkItem = NdisAllocateIoWorkItem(this->m_pAdapter->m_MiniportAdapterHandle);
            this->m_hSendCompleteWorkItem = IoWorkItem;
            if ( IoWorkItem )
            {
              NextActivityId = IActivityId::get_NextActivityId();
              v19 = EventQueue::RegisterTimeoutCallbackWithLevelAndReuse(
                      (EventQueue *)(v18 + 808),
                      NextActivityId,
                      this,
                      0xEA60u,
                      0,
                      (enum _WDF_EXECUTION_LEVEL)v22,
                      1,
                      &this->m_pOldFrameDetectionTimerRegistrationContext,
                      &this->m_OldFrameDetectionTimerToken);
              PropertyULong = v19;
              if ( v19 )
              {
                if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
                  return PropertyULong;
                LODWORD(v22) = v19;
                LOBYTE(v20) = 2;
                WPP_RECORDER_SF_D(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v20,
                  1,
                  99,
                  (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
                  v22);
              }
              else
              {
                CDispatchRundown::WaitForRundown(&this->m_DivertCompletionRundown);
              }
              goto LABEL_51;
            }
            if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
              goto LABEL_25;
            v14 = 98;
            goto LABEL_24;
          }
          if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
            return PropertyULong;
          v11 = 97;
        }
      }
    }
  }
LABEL_16:
  LOBYTE(v9) = 2;
  WPP_RECORDER_SF_(
    WPP_GLOBAL_Control->DeviceExtension,
    v9,
    1,
    v11,
    (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids);
LABEL_51:
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v22) = PropertyULong;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      100,
      (__int64)WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids,
      v22);
  }
  return PropertyULong;
}

```

## disassembly

```asm
0x14007d678  push    rbx
0x14007d67a  push    rbp
0x14007d67b  push    rsi
0x14007d67c  push    rdi
0x14007d67d  push    r12
0x14007d67f  push    r14
0x14007d681  push    r15
0x14007d683  sub     rsp, 50h
0x14007d687  mov     rbx, r8
0x14007d68a  mov     rsi, rdx
0x14007d68d  mov     rdi, rcx
0x14007d690  xor     ebp, ebp; __annotation("TMF:",
0x14007d692  lea     r14, WPP_RECORDER_INITIALIZED
0x14007d699  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14007d6a0  lea     r12, WPP_e7b28bdb59563ac0ee8acda3f411ccd9_Traceguids
0x14007d6a7  lea     r15d, [rbp+1]
0x14007d6ab  jz      short loc_14007D6D9
0x14007d6ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d6b4  cmp     byte ptr [rcx+29h], 5
0x14007d6b8  jnb     short loc_14007D6C0
0x14007d6ba  cmp     [rcx+48h], bp
0x14007d6be  jz      short loc_14007D6D9
0x14007d6c0  mov     rcx, [rcx+40h]
0x14007d6c4  mov     r9d, 58h ; 'X'
0x14007d6ca  mov     r8d, r15d
0x14007d6cd  mov     [rsp+88h+var_68], r12
0x14007d6d2  mov     dl, 5
0x14007d6d4  call    WPP_RECORDER_SF_
0x14007d6d9  test    rsi, rsi
0x14007d6dc  jz      loc_14007D9BB
0x14007d6e2  test    rbx, rbx
0x14007d6e5  jz      loc_14007D9BB
0x14007d6eb  cmp     [rbx+4], bpl
0x14007d6ef  jz      loc_14007D9BB
0x14007d6f5  mov     eax, ebp
0x14007d6f7  mov     [rdi+10h], rsi
0x14007d6fb  mov     [rdi+150h], rbx
0x14007d702  mov     byte ptr [rdi+158h], 5
0x14007d709  cmp     [rbx+5], bpl
0x14007d70d  setnz   al
0x14007d710  mov     [rdi+0F8h], eax
0x14007d716  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14007d71d  jz      short loc_14007D747
0x14007d71f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d726  mov     r9d, 5Ah ; 'Z'
0x14007d72c  mov     dword ptr [rsp+88h+var_60], eax; enum _WDF_EXECUTION_LEVEL
0x14007d730  mov     r8d, r15d
0x14007d733  mov     dl, 4
0x14007d735  mov     [rsp+88h+var_68], r12
0x14007d73a  mov     rcx, [rcx+40h]
0x14007d73e  call    WPP_RECORDER_SF_D
0x14007d743  mov     rsi, [rdi+10h]
0x14007d747  mov     r9d, [rdi+0F8h]; enum _WFC_TX_QUEUEING_MODE
0x14007d74e  lea     rcx, [rdi+130h]; this
0x14007d755  cmp     r9d, r15d
0x14007d758  jnz     short loc_14007D763
0x14007d75a  mov     r8b, [rdi+158h]
0x14007d761  jmp     short loc_14007D767
0x14007d763  mov     r8b, [rbx+4]; unsigned __int8
0x14007d767  mov     rdx, rsi; struct CAdapter *
0x14007d76a  call    ?Initialize@CTxEntryTable@@QEAAHPEAVCAdapter@@EW4_WFC_TX_QUEUEING_MODE@@@Z; CTxEntryTable::Initialize(CAdapter *,uchar,_WFC_TX_QUEUEING_MODE)
0x14007d76f  mov     ebx, eax
0x14007d771  test    eax, eax
0x14007d773  jz      short loc_14007D7A7
0x14007d775  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14007d77c  jz      loc_14007DA22
0x14007d782  mov     r9d, 5Bh ; '['
0x14007d788  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d78f  mov     r8d, r15d
0x14007d792  mov     dl, 2
0x14007d794  mov     [rsp+88h+var_68], r12
0x14007d799  mov     rcx, [rcx+40h]
0x14007d79d  call    WPP_RECORDER_SF_
0x14007d7a2  jmp     loc_14007D9E9
0x14007d7a7  cmp     [rdi+0F8h], ebp
0x14007d7ad  jnz     short loc_14007D81A
0x14007d7af  mov     edx, 108h
0x14007d7b4  mov     ecx, 40h ; '@'
0x14007d7b9  mov     r8d, 47696457h
0x14007d7bf  call    cs:__imp_ExAllocatePool2
0x14007d7c6  nop     dword ptr [rax+rax+00h]
0x14007d7cb  test    rax, rax
0x14007d7ce  jz      short loc_14007D7DA
0x14007d7d0  mov     rcx, rax; this
0x14007d7d3  call    ??0CACList@@QEAA@XZ; CACList::CACList(void)
0x14007d7d8  jmp     short loc_14007D7DD
0x14007d7da  mov     rax, rbp
0x14007d7dd  mov     [rdi+100h], rax
0x14007d7e4  test    rax, rax
0x14007d7e7  jnz     short loc_14007D81A
0x14007d7e9  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14007d7f0  jz      short loc_14007D810
0x14007d7f2  lea     r9d, [rax+5Ch]
0x14007d7f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d7fd  mov     r8d, r15d
0x14007d800  mov     dl, 2
0x14007d802  mov     [rsp+88h+var_68], r12
0x14007d807  mov     rcx, [rcx+40h]
0x14007d80b  call    WPP_RECORDER_SF_
0x14007d810  mov     ebx, 0C000009Ah
0x14007d815  jmp     loc_14007D9E9
0x14007d81a  mov     rcx, [rdi+10h]
0x14007d81e  add     rcx, 8
0x14007d822  mov     rax, [rcx]
0x14007d825  mov     rax, [rax+8]
0x14007d829  call    _guard_dispatch_icall
0x14007d82e  lea     r8, [rdi+184h]; unsigned int *
0x14007d835  mov     edx, 6Eh ; 'n'; unsigned int
0x14007d83a  mov     rcx, rax; this
0x14007d83d  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x14007d842  mov     ebx, eax
0x14007d844  test    eax, eax
0x14007d846  jz      short loc_14007D860
0x14007d848  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14007d84f  jz      loc_14007DA22
0x14007d855  mov     r9d, 5Dh ; ']'
0x14007d85b  jmp     loc_14007D788
0x14007d860  lea     rcx, [rdi+20h]; struct CNdisSpinLock **
0x14007d864  call    ?CreateInstance@CNdisSpinLock@@SAHPEAPEAV1@@Z; CNdisSpinLock::CreateInstance(CNdisSpinLock * *)
0x14007d869  mov     ebx, eax
0x14007d86b  test    eax, eax
0x14007d86d  jz      short loc_14007D887
0x14007d86f  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14007d876  jz      loc_14007DA22
0x14007d87c  mov     r9d, 5Eh ; '^'
0x14007d882  jmp     loc_14007D788
0x14007d887  lea     rcx, [rdi+28h]; struct CNdisSpinLock **
0x14007d88b  call    ?CreateInstance@CNdisSpinLock@@SAHPEAPEAV1@@Z; CNdisSpinLock::CreateInstance(CNdisSpinLock * *)
0x14007d890  mov     ebx, eax
0x14007d892  test    eax, eax
0x14007d894  jz      short loc_14007D8AE
0x14007d896  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14007d89d  jz      loc_14007DA22
0x14007d8a3  mov     r9d, 5Fh ; '_'
0x14007d8a9  jmp     loc_14007D788
0x14007d8ae  lea     rcx, [rdi+30h]; struct CNdisSpinLock **
0x14007d8b2  call    ?CreateInstance@CNdisSpinLock@@SAHPEAPEAV1@@Z; CNdisSpinLock::CreateInstance(CNdisSpinLock * *)
0x14007d8b7  mov     ebx, eax
0x14007d8b9  test    eax, eax
0x14007d8bb  jz      short loc_14007D8D5
0x14007d8bd  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14007d8c4  jz      loc_14007DA22
0x14007d8ca  mov     r9d, 60h ; '`'
0x14007d8d0  jmp     loc_14007D788
0x14007d8d5  lea     rcx, [rdi+38h]; struct CNdisSpinLock **
0x14007d8d9  call    ?CreateInstance@CNdisSpinLock@@SAHPEAPEAV1@@Z; CNdisSpinLock::CreateInstance(CNdisSpinLock * *)
0x14007d8de  mov     ebx, eax
0x14007d8e0  test    eax, eax
0x14007d8e2  jz      short loc_14007D8FC
0x14007d8e4  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14007d8eb  jz      loc_14007DA22
0x14007d8f1  mov     r9d, 61h ; 'a'
0x14007d8f7  jmp     loc_14007D788
0x14007d8fc  mov     rcx, [rdi+10h]
0x14007d900  mov     rcx, [rcx+58h]; NdisObjectHandle
0x14007d904  call    cs:__imp_NdisAllocateIoWorkItem
0x14007d90b  nop     dword ptr [rax+rax+00h]
0x14007d910  mov     [rdi+178h], rax
0x14007d917  test    rax, rax
0x14007d91a  jnz     short loc_14007D932
0x14007d91c  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14007d923  jz      loc_14007D810
0x14007d929  lea     r9d, [rax+62h]
0x14007d92d  jmp     loc_14007D7F6
0x14007d932  mov     r10, [rdi+10h]
0x14007d936  call    ?get_NextActivityId@IActivityId@@SAKXZ; IActivityId::get_NextActivityId(void)
0x14007d93b  lea     rdx, [rdi+188h]
0x14007d942  mov     r9d, 0EA60h; unsigned int
0x14007d948  mov     [rsp+88h+var_48], rdx; unsigned int *
0x14007d94d  lea     r8, [rdi+190h]
0x14007d954  mov     [rsp+88h+var_50], r8; struct TimerRegistrationContext **
0x14007d959  lea     rcx, [r10+328h]; this
0x14007d960  mov     [rsp+88h+var_58], r15b; bool
0x14007d965  mov     r8, rdi; struct ITimerCallback *
0x14007d968  mov     edx, eax; unsigned int
0x14007d96a  mov     [rsp+88h+var_68], rbp; void *
0x14007d96f  call    ?RegisterTimeoutCallbackWithLevelAndReuse@EventQueue@@QEAAHKPEAVITimerCallback@@KPEAXW4_WDF_EXECUTION_LEVEL@@_NPEAPEAVTimerRegistrationContext@@PEAI@Z; EventQueue::RegisterTimeoutCallbackWithLevelAndReuse(ulong,ITimerCallback *,ulong,void *,_WDF_EXECUTION_LEVEL,bool,TimerRegistrationContext * *,uint *)
0x14007d974  mov     ebx, eax
0x14007d976  test    eax, eax
0x14007d978  jz      short loc_14007D9AD
0x14007d97a  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14007d981  jz      loc_14007DA22
0x14007d987  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d98e  mov     r9d, 63h ; 'c'
0x14007d994  mov     dword ptr [rsp+88h+var_60], eax
0x14007d998  mov     r8d, r15d
0x14007d99b  mov     dl, 2
0x14007d99d  mov     [rsp+88h+var_68], r12
0x14007d9a2  mov     rcx, [rcx+40h]
0x14007d9a6  call    WPP_RECORDER_SF_D
0x14007d9ab  jmp     short loc_14007D9E9
0x14007d9ad  lea     rcx, [rdi+90h]; this
0x14007d9b4  call    ?WaitForRundown@CDispatchRundown@@QEAAXXZ; CDispatchRundown::WaitForRundown(void)
0x14007d9b9  jmp     short loc_14007D9E9
0x14007d9bb  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14007d9c2  jz      short loc_14007D9E4
0x14007d9c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d9cb  mov     r9d, 59h ; 'Y'
0x14007d9d1  mov     r8d, r15d
0x14007d9d4  mov     [rsp+88h+var_68], r12
0x14007d9d9  mov     dl, 2
0x14007d9db  mov     rcx, [rcx+40h]
0x14007d9df  call    WPP_RECORDER_SF_
0x14007d9e4  mov     ebx, 0C0000001h
0x14007d9e9  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14007d9f0  jz      short loc_14007DA22
0x14007d9f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d9f9  cmp     byte ptr [rcx+29h], 5
0x14007d9fd  jnb     short loc_14007DA05
0x14007d9ff  cmp     [rcx+48h], bp
0x14007da03  jz      short loc_14007DA22
0x14007da05  mov     rcx, [rcx+40h]
0x14007da09  mov     r9d, 64h ; 'd'
0x14007da0f  mov     dword ptr [rsp+88h+var_60], ebx
0x14007da13  mov     r8d, r15d
0x14007da16  mov     dl, 5
0x14007da18  mov     [rsp+88h+var_68], r12
0x14007da1d  call    WPP_RECORDER_SF_D
0x14007da22  mov     eax, ebx
0x14007da24  add     rsp, 50h
0x14007da28  pop     r15
0x14007da2a  pop     r14
0x14007da2c  pop     r12
0x14007da2e  pop     rdi
0x14007da2f  pop     rsi
0x14007da30  pop     rbp
0x14007da31  pop     rbx
0x14007da32  retn
```
