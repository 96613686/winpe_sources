# ConnectionAggregator::~ConnectionAggregator(void)

- ea: `0x1800889e0`
- end: `0x180088b6b`
- name: `??1ConnectionAggregator@@QEAA@XZ`
- size: `395`
- prototype: `void __fastcall(ConnectionAggregator *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180089ec0`

## callees

- `0x180011bb0`
- `0x180011c20`
- `0x1800137a0`
- `0x180027630`
- `0x180035b84`
- `0x1800664ec`
- `0x18006bfe4`
- `0x1800889e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180088acc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180088acc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088abf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180088abf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180088b64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088a45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088a45`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180088a3b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180088a3b`

## pseudocode

```c
void __fastcall ConnectionAggregator::~ConnectionAggregator(struct _RTL_CRITICAL_SECTION *this)
{
  char v2; // di
  void *SpinCount; // rcx
  DWORD LastError; // eax
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  LPCRITICAL_SECTION lpCriticalSection[3]; // [rsp+30h] [rbp-18h] BYREF

  v2 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      49,
      WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids,
      "ConnectionAggregator::~ConnectionAggregator");
  }
  SpinCount = (void *)this[1].SpinCount;
  if ( SpinCount )
  {
    if ( !DeleteTimerQueueEx(SpinCount, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 50, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids, LastError);
      }
    }
    this[1].SpinCount = 0;
  }
  lpCriticalSection[0] = 0;
  wil::EnterCriticalSection(lpCriticalSection, this);
  if ( this[1].DebugInfo != *(PRTL_CRITICAL_SECTION_DEBUG *)&this[1].LockCount )
  {
    ((void (*)(void))std::_Destroy_range<std::allocator<std::shared_ptr<PdcManager::NdisPowerInterface>>>)();
    *(_QWORD *)&this[1].LockCount = this[1].DebugInfo;
  }
  if ( lpCriticalSection[0] )
    LeaveCriticalSection(lpCriticalSection[0]);
  SetEvent(g_aggregatorExitHandle);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_sL(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      51,
      (unsigned int)WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids,
      (unsigned int)"ConnectionAggregator::~ConnectionAggregator",
      v2);
  }
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&this[1].LockSemaphore);
  DebugInfo = this[1].DebugInfo;
  if ( DebugInfo )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<PdcManager::NdisPowerInterface>>>(
      DebugInfo,
      *(_QWORD *)&this[1].LockCount);
    std::_Deallocate<16>(
      this[1].DebugInfo,
      ((PRTL_CRITICAL_SECTION_DEBUG)this[1].OwningThread - this[1].DebugInfo) & 0xFFFFFFFFFFFFFFF0uLL);
    this[1].DebugInfo = 0;
    *(_QWORD *)&this[1].LockCount = 0;
    this[1].OwningThread = 0;
  }
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x1800889e0  mov     [rsp+arg_8], rbx
0x1800889e5  mov     [rsp+arg_10], rdi
0x1800889ea  push    r14
0x1800889ec  sub     rsp, 40h
0x1800889f0  mov     rbx, rcx
0x1800889f3  xor     edi, edi
0x1800889f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800889fc  lea     r14, WPP_GLOBAL_Control
0x180088a03  cmp     rcx, r14
0x180088a06  jz      short loc_180088A2E
0x180088a08  cmp     byte ptr [rcx+19h], 5
0x180088a0c  jb      short loc_180088A2E
0x180088a0e  test    byte ptr [rcx+1Ch], 1
0x180088a12  jz      short loc_180088A2E
0x180088a14  mov     rcx, [rcx+10h]
0x180088a18  lea     edx, [rdi+31h]
0x180088a1b  lea     r9, aConnectionaggr_29; "ConnectionAggregator::~ConnectionAggreg"...
0x180088a22  lea     r8, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids
0x180088a29  call    WPP_SF_s
0x180088a2e  mov     rcx, [rbx+48h]; TimerQueue
0x180088a32  test    rcx, rcx
0x180088a35  jz      short loc_180088A85
0x180088a37  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180088a3b  call    cs:__imp_DeleteTimerQueueEx
0x180088a41  test    eax, eax
0x180088a43  jnz     short loc_180088A7D
0x180088a45  call    cs:__imp_GetLastError
0x180088a4b  mov     edi, eax
0x180088a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180088a54  cmp     rcx, r14
0x180088a57  jz      short loc_180088A7D
0x180088a59  cmp     byte ptr [rcx+19h], 1
0x180088a5d  jb      short loc_180088A7D
0x180088a5f  test    byte ptr [rcx+1Ch], 1
0x180088a63  jz      short loc_180088A7D
0x180088a65  mov     rcx, [rcx+10h]
0x180088a69  lea     r8, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids
0x180088a70  mov     edx, 32h ; '2'
0x180088a75  mov     r9d, eax
0x180088a78  call    WPP_SF_d
0x180088a7d  mov     qword ptr [rbx+48h], 0
0x180088a85  mov     rdx, rbx
0x180088a88  mov     [rsp+48h+lpCriticalSection], 0
0x180088a91  lea     rcx, [rsp+48h+lpCriticalSection]
0x180088a96  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x180088a9b  mov     rdx, [rbx+30h]
0x180088a9f  mov     rcx, [rbx+28h]
0x180088aa3  cmp     rcx, rdx
0x180088aa6  jz      short loc_180088AB5
0x180088aa8  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VNdisPowerInterface@PdcManager@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VNdisPowerInterface@PdcManager@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VNdisPowerInterface@PdcManager@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<PdcManager::NdisPowerInterface>>>(std::shared_ptr<PdcManager::NdisPowerInterface> *,std::shared_ptr<PdcManager::NdisPowerInterface> * const,std::allocator<std::shared_ptr<PdcManager::NdisPowerInterface>> &)
0x180088aad  mov     rax, [rbx+28h]
0x180088ab1  mov     [rbx+30h], rax
0x180088ab5  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x180088aba  test    rcx, rcx
0x180088abd  jz      short loc_180088AC5
0x180088abf  call    cs:__imp_LeaveCriticalSection
0x180088ac5  mov     rcx, cs:?g_aggregatorExitHandle@@3PEAXEA; hEvent
0x180088acc  call    cs:__imp_SetEvent
0x180088ad2  mov     rcx, cs:WPP_GLOBAL_Control
0x180088ad9  cmp     rcx, r14
0x180088adc  jz      short loc_180088B0A
0x180088ade  cmp     byte ptr [rcx+19h], 5
0x180088ae2  jb      short loc_180088B0A
0x180088ae4  test    byte ptr [rcx+1Ch], 1
0x180088ae8  jz      short loc_180088B0A
0x180088aea  mov     rcx, [rcx+10h]
0x180088aee  lea     r9, aConnectionaggr_29; "ConnectionAggregator::~ConnectionAggreg"...
0x180088af5  mov     edx, 33h ; '3'
0x180088afa  mov     [rsp+48h+var_28], edi
0x180088afe  lea     r8, WPP_629ff72c36873acc9d3aa94b4d8c7cd2_Traceguids
0x180088b05  call    WPP_SF_sL
0x180088b0a  lea     rcx, [rbx+40h]
0x180088b0e  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x180088b13  mov     rcx, [rbx+28h]
0x180088b17  test    rcx, rcx
0x180088b1a  jz      short loc_180088B51
0x180088b1c  mov     rdx, [rbx+30h]
0x180088b20  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VNdisPowerInterface@PdcManager@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VNdisPowerInterface@PdcManager@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VNdisPowerInterface@PdcManager@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<PdcManager::NdisPowerInterface>>>(std::shared_ptr<PdcManager::NdisPowerInterface> *,std::shared_ptr<PdcManager::NdisPowerInterface> * const,std::allocator<std::shared_ptr<PdcManager::NdisPowerInterface>> &)
0x180088b25  mov     rcx, [rbx+28h]
0x180088b29  mov     rdx, [rbx+38h]
0x180088b2d  sub     rdx, rcx
0x180088b30  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180088b34  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180088b39  mov     qword ptr [rbx+28h], 0
0x180088b41  mov     qword ptr [rbx+30h], 0
0x180088b49  mov     qword ptr [rbx+38h], 0
0x180088b51  mov     rcx, rbx
0x180088b54  mov     rbx, [rsp+48h+arg_8]
0x180088b59  mov     rdi, [rsp+48h+arg_10]
0x180088b5e  add     rsp, 40h
0x180088b62  pop     r14
0x180088b64  jmp     cs:__imp_DeleteCriticalSection
```
