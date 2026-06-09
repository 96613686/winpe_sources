# CSampleQueue::~CSampleQueue(void)

- ea: `0x1801c83a4`
- end: `0x1801c858b`
- name: `??1CSampleQueue@@QEAA@XZ`
- size: `487`
- prototype: `void __fastcall(CSampleQueue *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18008f20c`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x18006b388`
- `0x180082ba4`
- `0x18008fd14`
- `0x18014d624`
- `0x1801c83a4`
- `0x1801c8594`
- `0x180258390`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801c844b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801c845e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801c844b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801c845e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801c849d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801c84ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801c8536`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801c849d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801c84ed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801c8536`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801c84c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801c8516`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801c855f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801c84c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801c8516`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801c855f`

## pseudocode

```c
void __fastcall CSampleQueue::~CSampleQueue(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE ProcessHeap; // rax
  struct _RTL_CRITICAL_SECTION *LockSemaphore; // r8
  void *v4; // r14
  struct _RTL_CRITICAL_SECTION *DebugInfo; // rbx
  HANDLE v6; // rax
  ULONG_PTR *OwningThread; // r8
  void *v8; // r14
  void *v9; // rdi
  HANDLE v10; // rax
  HANDLE *v11; // r8
  void *v12; // rbp
  HANDLE *v13; // rbx
  char v14; // [rsp+40h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v14, "CSampleQueue::~CSampleQueue", 56);
  if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, &WPP_90bb69a99c213163de1e2bc611cea946_Traceguids, this);
  CSampleQueue::Flush((CSampleQueue *)this, 1);
  CObjectPool::Disable((CObjectPool *)&this[33].LockSemaphore);
  CObjectPool::Disable((CObjectPool *)&this[35].OwningThread);
  operator delete(this[40].LockSemaphore);
  this[40].LockSemaphore = 0;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v14);
  DeleteCriticalSection(this + 39);
  DeleteCriticalSection(this + 38);
  this[35].OwningThread = &CObjectPoolT<CAudioDataContainer,400>::`vftable';
  CObjectPool::~CObjectPool((CObjectPool *)&this[35].OwningThread);
  this[33].LockSemaphore = &CObjectPoolT<CAudioDataContainer,400>::`vftable';
  CObjectPool::~CObjectPool((CObjectPool *)&this[33].LockSemaphore);
  CVPtrList::RemoveAll((CVPtrList *)&this[22].OwningThread);
  ProcessHeap = GetProcessHeap();
  LockSemaphore = (struct _RTL_CRITICAL_SECTION *)this[22].LockSemaphore;
  v4 = ProcessHeap;
  if ( LockSemaphore )
  {
    do
    {
      DebugInfo = (struct _RTL_CRITICAL_SECTION *)LockSemaphore->DebugInfo;
      if ( LockSemaphore != &this[23] )
        HeapFree(v4, 0, LockSemaphore);
      this[22].LockSemaphore = DebugInfo;
      LockSemaphore = DebugInfo;
    }
    while ( DebugInfo );
  }
  CVPtrList::RemoveAll((CVPtrList *)&this[11].LockCount);
  v6 = GetProcessHeap();
  OwningThread = (ULONG_PTR *)this[11].OwningThread;
  v8 = v6;
  if ( OwningThread )
  {
    do
    {
      v9 = (void *)*OwningThread;
      if ( OwningThread != &this[11].SpinCount )
        HeapFree(v8, 0, OwningThread);
      this[11].OwningThread = v9;
      OwningThread = (ULONG_PTR *)v9;
    }
    while ( v9 );
  }
  CVPtrList::RemoveAll((CVPtrList *)this);
  v10 = GetProcessHeap();
  v11 = *(HANDLE **)&this->LockCount;
  v12 = v10;
  if ( v11 )
  {
    do
    {
      v13 = (HANDLE *)*v11;
      if ( v11 != &this->LockSemaphore )
        HeapFree(v12, 0, v11);
      *(_QWORD *)&this->LockCount = v13;
      v11 = v13;
    }
    while ( v13 );
  }
}

```

## disassembly

```asm
0x1801c83a4  mov     [rsp+arg_8], rbx
0x1801c83a9  mov     [rsp+arg_10], rbp
0x1801c83ae  push    rsi
0x1801c83af  push    rdi
0x1801c83b0  push    r14
0x1801c83b2  sub     rsp, 20h
0x1801c83b6  mov     rsi, rcx
0x1801c83b9  lea     rdx, aCsamplequeueCs; "CSampleQueue::~CSampleQueue"
0x1801c83c0  lea     rcx, [rsp+38h+arg_0]; this
0x1801c83c5  mov     r8d, 38h ; '8'; int
0x1801c83cb  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1801c83d0  cmp     cs:byte_1803CECE9, 10h
0x1801c83d7  jb      short loc_1801C83F8
0x1801c83d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801c83e0  lea     r8, WPP_90bb69a99c213163de1e2bc611cea946_Traceguids
0x1801c83e7  mov     edx, 0Bh
0x1801c83ec  mov     r9, rsi
0x1801c83ef  mov     rcx, [rcx+38h]
0x1801c83f3  call    WPP_SF_q
0x1801c83f8  mov     edx, 1; int
0x1801c83fd  mov     rcx, rsi; this
0x1801c8400  call    ?Flush@CSampleQueue@@QEAAXH@Z; CSampleQueue::Flush(int)
0x1801c8405  lea     rdi, [rsi+540h]
0x1801c840c  mov     rcx, rdi; this
0x1801c840f  call    ?Disable@CObjectPool@@QEAAXXZ; CObjectPool::Disable(void)
0x1801c8414  lea     rbx, [rsi+588h]
0x1801c841b  mov     rcx, rbx; this
0x1801c841e  call    ?Disable@CObjectPool@@QEAAXXZ; CObjectPool::Disable(void)
0x1801c8423  mov     rcx, [rsi+658h]; Block
0x1801c842a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801c842f  lea     rcx, [rsp+38h+arg_0]; this
0x1801c8434  mov     qword ptr [rsi+658h], 0
0x1801c843f  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1801c8444  lea     rcx, [rsi+618h]; lpCriticalSection
0x1801c844b  call    cs:__imp_DeleteCriticalSection
0x1801c8452  nop     dword ptr [rax+rax+00h]
0x1801c8457  lea     rcx, [rsi+5F0h]; lpCriticalSection
0x1801c845e  call    cs:__imp_DeleteCriticalSection
0x1801c8465  nop     dword ptr [rax+rax+00h]
0x1801c846a  lea     rax, ??_7?$CObjectPoolT@VCAudioDataContainer@@$0BJA@@@6B@; const CObjectPoolT<CAudioDataContainer,400>::`vftable'
0x1801c8471  mov     rcx, rbx; this
0x1801c8474  mov     [rbx], rax
0x1801c8477  call    ??1CObjectPool@@UEAA@XZ; CObjectPool::~CObjectPool(void)
0x1801c847c  lea     rax, ??_7?$CObjectPoolT@VCAudioDataContainer@@$0BJA@@@6B@; const CObjectPoolT<CAudioDataContainer,400>::`vftable'
0x1801c8483  mov     rcx, rdi; this
0x1801c8486  mov     [rdi], rax
0x1801c8489  call    ??1CObjectPool@@UEAA@XZ; CObjectPool::~CObjectPool(void)
0x1801c848e  lea     rdi, [rsi+380h]
0x1801c8495  mov     rcx, rdi; this
0x1801c8498  call    ?RemoveAll@CVPtrList@@QEAAXXZ; CVPtrList::RemoveAll(void)
0x1801c849d  call    cs:__imp_GetProcessHeap
0x1801c84a4  nop     dword ptr [rax+rax+00h]
0x1801c84a9  mov     r8, [rdi+8]; lpMem
0x1801c84ad  mov     r14, rax
0x1801c84b0  test    r8, r8
0x1801c84b3  jz      short loc_1801C84DE
0x1801c84b5  lea     rbp, [rdi+18h]
0x1801c84b9  mov     rbx, [r8]
0x1801c84bc  cmp     r8, rbp
0x1801c84bf  jz      short loc_1801C84D2
0x1801c84c1  xor     edx, edx; dwFlags
0x1801c84c3  mov     rcx, r14; hHeap
0x1801c84c6  call    cs:__imp_HeapFree
0x1801c84cd  nop     dword ptr [rax+rax+00h]
0x1801c84d2  mov     [rdi+8], rbx
0x1801c84d6  mov     r8, rbx
0x1801c84d9  test    rbx, rbx
0x1801c84dc  jnz     short loc_1801C84B9
0x1801c84de  lea     rbx, [rsi+1C0h]
0x1801c84e5  mov     rcx, rbx; this
0x1801c84e8  call    ?RemoveAll@CVPtrList@@QEAAXXZ; CVPtrList::RemoveAll(void)
0x1801c84ed  call    cs:__imp_GetProcessHeap
0x1801c84f4  nop     dword ptr [rax+rax+00h]
0x1801c84f9  mov     r8, [rbx+8]; lpMem
0x1801c84fd  mov     r14, rax
0x1801c8500  test    r8, r8
0x1801c8503  jz      short loc_1801C852E
0x1801c8505  lea     rbp, [rbx+18h]
0x1801c8509  mov     rdi, [r8]
0x1801c850c  cmp     r8, rbp
0x1801c850f  jz      short loc_1801C8522
0x1801c8511  xor     edx, edx; dwFlags
0x1801c8513  mov     rcx, r14; hHeap
0x1801c8516  call    cs:__imp_HeapFree
0x1801c851d  nop     dword ptr [rax+rax+00h]
0x1801c8522  mov     [rbx+8], rdi
0x1801c8526  mov     r8, rdi
0x1801c8529  test    rdi, rdi
0x1801c852c  jnz     short loc_1801C8509
0x1801c852e  mov     rcx, rsi; this
0x1801c8531  call    ?RemoveAll@CVPtrList@@QEAAXXZ; CVPtrList::RemoveAll(void)
0x1801c8536  call    cs:__imp_GetProcessHeap
0x1801c853d  nop     dword ptr [rax+rax+00h]
0x1801c8542  mov     r8, [rsi+8]; lpMem
0x1801c8546  mov     rbp, rax
0x1801c8549  test    r8, r8
0x1801c854c  jz      short loc_1801C8577
0x1801c854e  lea     rdi, [rsi+18h]
0x1801c8552  mov     rbx, [r8]
0x1801c8555  cmp     r8, rdi
0x1801c8558  jz      short loc_1801C856B
0x1801c855a  xor     edx, edx; dwFlags
0x1801c855c  mov     rcx, rbp; hHeap
0x1801c855f  call    cs:__imp_HeapFree
0x1801c8566  nop     dword ptr [rax+rax+00h]
0x1801c856b  mov     [rsi+8], rbx
0x1801c856f  mov     r8, rbx
0x1801c8572  test    rbx, rbx
0x1801c8575  jnz     short loc_1801C8552
0x1801c8577  mov     rbx, [rsp+38h+arg_8]
0x1801c857c  mov     rbp, [rsp+38h+arg_10]
0x1801c8581  add     rsp, 20h
0x1801c8585  pop     r14
0x1801c8587  pop     rdi
0x1801c8588  pop     rsi
0x1801c8589  retn
```
