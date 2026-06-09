# ServiceManager::CancelOperationAndWait(ServiceManager::CANCELLATION_TYPE)

- ea: `0x1800134b8`
- end: `0x180013572`
- name: `?CancelOperationAndWait@ServiceManager@@AEAAJW4CANCELLATION_TYPE@1@@Z`
- size: `186`
- prototype: `int __fastcall(struct _RTL_CRITICAL_SECTION *, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180012cf0`
- `0x180014c00`
- `0x1800169a4`
- `0x18001cb60`

## callees

- `0x1800043e4`
- `0x180013400`
- `0x1800134b8`
- `0x180022914`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013501`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013501`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013539`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013539`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800134d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800134d0`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001352e`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180013563`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001352e`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180013563`

## string_xrefs

- `0x18001355c`: `ServiceManager::CancelOperationAndWait`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall ServiceManager::CancelOperationAndWait(struct _RTL_CRITICAL_SECTION *a1, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  int OwningThread; // ebx
  int v6; // eax
  __int64 v7; // rbx
  int v8; // ebp
  unsigned int v9; // edx
  int v10; // eax
  int v12; // r8d
  int v13; // ecx
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  v2 = a1 + 85;
  OwningThread = (int)a1[85].OwningThread;
  if ( OwningThread != GetCurrentThreadId() )
    __int2c();
  v6 = ServiceManager::CancelOperation(a1, a2);
  if ( v6 < 0 )
  {
    v12 = 2572;
    v13 = v6;
  }
  else
  {
    wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v14, (__int64)a1);
    v7 = v14;
    v8 = 0;
    EnterCriticalSection(v2);
    while ( *(_DWORD *)(v7 + 3524) > 2u )
    {
      v10 = CriticalSectionWithConditionVariable::WaitForCondition(v2, v9);
      if ( v10 < 0 )
      {
        v8 = ZTraceReportPropagation(v10, "CriticalSectionWithConditionVariable::WaitWhile", 54, v2);
        break;
      }
    }
    LeaveCriticalSection(v2);
    if ( v8 >= 0 )
      return 0;
    v12 = 2583;
    v13 = v8;
  }
  return ZTraceReportPropagation(v13, "ServiceManager::CancelOperationAndWait", v12, a1);
}

```

## disassembly

```asm
0x1800134b8  push    rbx
0x1800134ba  push    rbp
0x1800134bb  push    rsi
0x1800134bc  push    rdi
0x1800134bd  sub     rsp, 28h
0x1800134c1  lea     rdi, [rcx+0D48h]
0x1800134c8  mov     ebp, edx
0x1800134ca  mov     ebx, [rdi+10h]
0x1800134cd  mov     rsi, rcx
0x1800134d0  call    cs:__imp_GetCurrentThreadId
0x1800134d6  cmp     ebx, eax
0x1800134d8  jz      short loc_1800134DC
0x1800134da  int     2Ch; Windows NT - assertion failure
0x1800134dc  mov     edx, ebp
0x1800134de  mov     rcx, rsi
0x1800134e1  call    ?CancelOperation@ServiceManager@@AEAAJW4CANCELLATION_TYPE@1@@Z; ServiceManager::CancelOperation(ServiceManager::CANCELLATION_TYPE)
0x1800134e6  test    eax, eax
0x1800134e8  js      short loc_180013551
0x1800134ea  mov     rdx, rsi
0x1800134ed  lea     rcx, [rsp+48h+arg_0]
0x1800134f2  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800134f7  mov     rbx, [rsp+48h+arg_0]
0x1800134fc  xor     ebp, ebp
0x1800134fe  mov     rcx, rdi; lpCriticalSection
0x180013501  call    cs:__imp_EnterCriticalSection
0x180013507  cmp     dword ptr [rbx+0DC4h], 2
0x18001350e  jbe     short loc_180013536
0x180013510  mov     rcx, rdi; lpCriticalSection
0x180013513  call    ?WaitForCondition@CriticalSectionWithConditionVariable@@AEAAJK@Z; CriticalSectionWithConditionVariable::WaitForCondition(ulong)
0x180013518  test    eax, eax
0x18001351a  jns     short loc_180013507
0x18001351c  mov     r9, rdi
0x18001351f  lea     rdx, aCriticalsectio_0; "CriticalSectionWithConditionVariable::W"...
0x180013526  mov     r8d, 36h ; '6'
0x18001352c  mov     ecx, eax
0x18001352e  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180013534  mov     ebp, eax
0x180013536  mov     rcx, rdi; lpCriticalSection
0x180013539  call    cs:__imp_LeaveCriticalSection
0x18001353f  test    ebp, ebp
0x180013541  js      short loc_180013547
0x180013543  xor     eax, eax
0x180013545  jmp     short loc_180013569
0x180013547  mov     r8d, 0A17h
0x18001354d  mov     ecx, ebp
0x18001354f  jmp     short loc_180013559
0x180013551  mov     r8d, 0A0Ch
0x180013557  mov     ecx, eax
0x180013559  mov     r9, rsi
0x18001355c  lea     rdx, aServicemanager_80; "ServiceManager::CancelOperationAndWait"
0x180013563  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180013569  add     rsp, 28h
0x18001356d  pop     rdi
0x18001356e  pop     rsi
0x18001356f  pop     rbp
0x180013570  pop     rbx
0x180013571  retn
```
