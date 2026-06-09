# ShieldProvider::CPeriodicTaskManager::Close(void)

- ea: `0x180011b84`
- end: `0x180011c5f`
- name: `?Close@CPeriodicTaskManager@ShieldProvider@@QEAAXXZ`
- size: `219`
- prototype: `void __fastcall(ShieldProvider::CPeriodicTaskManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001195c`
- `0x180011b24`

## callees

- `0x18000f02c`
- `0x18000f094`
- `0x180011b84`
- `0x1800134f8`
- `0x1800db9f8`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x180011c02`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180011c18`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180011c49`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180011c02`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180011c18`
- `KERNEL32!DeleteTimerQueueTimer` at `0x180011c49`

## pseudocode

```c
void __fastcall ShieldProvider::CPeriodicTaskManager::Close(ShieldProvider::CPeriodicTaskManager *this)
{
  void *v2; // rbx
  char i; // al
  void *v4; // rax
  void *v5; // rdx
  void *v6; // rdx
  struct tagMP_THREAD_POOL *v7; // rcx
  _BYTE v8[40]; // [rsp+20h] [rbp-28h] BYREF

  v2 = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v8,
    (char *)this + 16);
  for ( i = 1; ; i = 0 )
  {
    v8[16] = i;
    if ( !i )
      break;
    if ( *((_BYTE *)this + 56) )
    {
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v8);
      if ( v2 )
        DeleteTimerQueueTimer(0, v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      return;
    }
    v4 = v2;
    *((_BYTE *)this + 56) = 1;
    v2 = (void *)*((_QWORD *)this + 13);
    *((_QWORD *)this + 13) = v4;
  }
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v8);
  CommonUtil::UtilSetEvent(*((CommonUtil **)this + 8), v5);
  if ( v2 )
    DeleteTimerQueueTimer(0, v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v6 = (void *)*((_QWORD *)this + 11);
  if ( v6 )
  {
    DeleteTimerQueueTimer(0, v6, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    *((_QWORD *)this + 11) = 0;
  }
  v7 = (struct tagMP_THREAD_POOL *)*((_QWORD *)this + 10);
  if ( v7 )
  {
    CommonUtil::CAutoMpThreadPoolClose::Release(v7);
    *((_QWORD *)this + 10) = 0;
  }
}

```

## disassembly

```asm
0x180011b84  mov     [rsp+arg_0], rbx
0x180011b89  mov     [rsp+arg_8], rsi
0x180011b8e  push    rdi
0x180011b8f  sub     rsp, 40h
0x180011b93  mov     rdi, rcx
0x180011b96  lea     rdx, [rcx+10h]
0x180011b9a  lea     rcx, [rsp+48h+var_28]
0x180011b9f  xor     ebx, ebx
0x180011ba1  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x180011ba6  mov     al, 1
0x180011ba8  mov     [rsp+48h+var_18], al
0x180011bac  test    al, al
0x180011bae  jz      short loc_180011BDE
0x180011bb0  cmp     byte ptr [rdi+38h], 0
0x180011bb4  jnz     short loc_180011BC9
0x180011bb6  mov     rax, rbx
0x180011bb9  mov     byte ptr [rdi+38h], 1
0x180011bbd  mov     rbx, [rdi+68h]
0x180011bc1  mov     [rdi+68h], rax
0x180011bc5  xor     al, al
0x180011bc7  jmp     short loc_180011BA8
0x180011bc9  lea     rcx, [rsp+48h+var_28]
0x180011bce  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180011bd3  test    rbx, rbx
0x180011bd6  jz      short loc_180011C4F
0x180011bd8  or      r8, 0FFFFFFFFFFFFFFFFh
0x180011bdc  jmp     short loc_180011C44
0x180011bde  lea     rcx, [rsp+48h+var_28]
0x180011be3  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x180011be8  mov     rcx, [rdi+40h]; this
0x180011bec  call    ?UtilSetEvent@CommonUtil@@YAXPEAX@Z; CommonUtil::UtilSetEvent(void *)
0x180011bf1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180011bf5  test    rbx, rbx
0x180011bf8  jz      short loc_180011C0A
0x180011bfa  mov     r8, rsi; CompletionEvent
0x180011bfd  mov     rdx, rbx; Timer
0x180011c00  xor     ecx, ecx; TimerQueue
0x180011c02  call    cs:__imp_DeleteTimerQueueTimer
0x180011c08  xor     ebx, ebx
0x180011c0a  mov     rdx, [rdi+58h]; Timer
0x180011c0e  test    rdx, rdx
0x180011c11  jz      short loc_180011C26
0x180011c13  mov     r8, rsi; CompletionEvent
0x180011c16  xor     ecx, ecx; TimerQueue
0x180011c18  call    cs:__imp_DeleteTimerQueueTimer
0x180011c1e  mov     qword ptr [rdi+58h], 0
0x180011c26  mov     rcx, [rdi+50h]; struct tagMP_THREAD_POOL *
0x180011c2a  test    rcx, rcx
0x180011c2d  jz      short loc_180011C3C
0x180011c2f  call    ?Release@CAutoMpThreadPoolClose@CommonUtil@@SAXPEAUtagMP_THREAD_POOL@@@Z; CommonUtil::CAutoMpThreadPoolClose::Release(tagMP_THREAD_POOL *)
0x180011c34  mov     qword ptr [rdi+50h], 0
0x180011c3c  test    rbx, rbx
0x180011c3f  jz      short loc_180011C4F
0x180011c41  mov     r8, rsi; CompletionEvent
0x180011c44  mov     rdx, rbx; Timer
0x180011c47  xor     ecx, ecx; TimerQueue
0x180011c49  call    cs:__imp_DeleteTimerQueueTimer
0x180011c4f  mov     rbx, [rsp+48h+arg_0]
0x180011c54  mov     rsi, [rsp+48h+arg_8]
0x180011c59  add     rsp, 40h
0x180011c5d  pop     rdi
0x180011c5e  retn
```
