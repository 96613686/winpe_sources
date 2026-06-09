# CLocalMmcssWorkQueue::RuntimeClassInitialize(ushort const *)

- ea: `0x140031608`
- end: `0x1400316e9`
- name: `?RuntimeClassInitialize@CLocalMmcssWorkQueue@@QEAAJPEBG@Z`
- size: `225`
- prototype: `__int64 __fastcall(CLocalMmcssWorkQueue *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140006010`

## callees

- `0x140003bb0`
- `0x14000c33c`
- `0x14000f3f8`
- `0x140031608`
- `0x1400316f0`

## import_xrefs

- `RTWorkQ!RtwqGetWorkQueueMMCSSTaskId` at `0x1400316b5`
- `RTWorkQ!RtwqGetWorkQueueMMCSSTaskId` at `0x1400316b5`
- `RTWorkQ!RtwqAllocateWorkQueue` at `0x140031623`
- `RTWorkQ!RtwqAllocateWorkQueue` at `0x140031623`
- `RTWorkQ!RtwqUnlockWorkQueue` at `0x14003167b`
- `RTWorkQ!RtwqUnlockWorkQueue` at `0x14003167b`

## string_xrefs

- `0x140031634`: `avcore\audiocore\server\audiodg\exe\rtthreadmanager.cpp`
- `0x140031665`: `avcore\audiocore\server\audiodg\exe\rtthreadmanager.cpp`
- `0x14003168a`: `avcore\audiocore\server\audiodg\exe\rtthreadmanager.cpp`

## pseudocode

```c
__int64 __fastcall CLocalMmcssWorkQueue::RuntimeClassInitialize(DWORD *this, const unsigned __int16 *a2)
{
  DWORD *v2; // rbx
  HRESULT WorkQueue; // eax
  unsigned int v6; // edi
  int v8; // eax
  HRESULT v9; // eax
  DWORD v10; // ecx
  __int64 v11; // rcx
  int v12; // [rsp+20h] [rbp-38h]
  int v13; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD taskId; // [rsp+60h] [rbp+8h] BYREF

  v2 = this + 4;
  WorkQueue = RtwqAllocateWorkQueue(RTWQ_MULTITHREADED_WORKQUEUE, this + 4);
  v6 = WorkQueue;
  if ( WorkQueue < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF6,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\rtthreadmanager.cpp",
      (const char *)(unsigned int)WorkQueue,
      v12);
    return v6;
  }
  v8 = CLocalMmcssWorkQueue::RegisterWorkQueueWithMmcss((CLocalMmcssWorkQueue *)this, a2);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFD,
      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\rtthreadmanager.cpp",
      (const char *)(unsigned int)v8,
      v12);
    v9 = RtwqUnlockWorkQueue(*v2);
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xF9,
        (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\rtthreadmanager.cpp",
        (const char *)(unsigned int)v9,
        v13);
    *v2 = 0;
    return v6;
  }
  v10 = *v2;
  taskId = 0;
  RtwqGetWorkQueueMMCSSTaskId(v10, &taskId);
  if ( (byte_1400E7E41 & 8) != 0 )
    McTemplateU0pqq_EtwEventWriteTransfer(v11, AudioCore_Pump_CreateLocalWorkQueue, this, *v2, taskId);
  return 0;
}

```

## disassembly

```asm
0x140031608  push    rbx
0x14003160a  push    rbp
0x14003160b  push    rsi
0x14003160c  push    rdi
0x14003160d  sub     rsp, 38h
0x140031611  lea     rbx, [rcx+10h]
0x140031615  mov     rbp, rdx
0x140031618  mov     rsi, rcx
0x14003161b  mov     rdx, rbx; workQueueId
0x14003161e  mov     ecx, 2; WorkQueueType
0x140031623  call    cs:__imp_RtwqAllocateWorkQueue
0x140031629  mov     edi, eax
0x14003162b  test    eax, eax
0x14003162d  jns     short loc_14003164F
0x14003162f  mov     rcx, [rsp+58h]; this
0x140031634  lea     r8, aAvcoreAudiocor_38; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14003163b  mov     r9d, eax; char *
0x14003163e  mov     edx, 0F6h; void *
0x140031643  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140031648  mov     eax, edi
0x14003164a  jmp     loc_1400316E0
0x14003164f  mov     rdx, rbp; unsigned __int16 *
0x140031652  mov     rcx, rsi; this
0x140031655  call    ?RegisterWorkQueueWithMmcss@CLocalMmcssWorkQueue@@AEAAJPEBG@Z; CLocalMmcssWorkQueue::RegisterWorkQueueWithMmcss(ushort const *)
0x14003165a  mov     edi, eax
0x14003165c  test    eax, eax
0x14003165e  jns     short loc_1400316A6
0x140031660  mov     rcx, [rsp+58h]; this
0x140031665  lea     r8, aAvcoreAudiocor_38; "avcore\\audiocore\\server\\audiodg\\exe"...
0x14003166c  mov     r9d, eax; char *
0x14003166f  mov     edx, 0FDh; void *
0x140031674  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140031679  mov     ecx, [rbx]; workQueueId
0x14003167b  call    cs:__imp_RtwqUnlockWorkQueue
0x140031681  test    eax, eax
0x140031683  jns     short loc_14003169E
0x140031685  mov     rcx, [rsp+58h]; this
0x14003168a  lea     r8, aAvcoreAudiocor_38; "avcore\\audiocore\\server\\audiodg\\exe"...
0x140031691  mov     r9d, eax; char *
0x140031694  mov     edx, 0F9h; void *
0x140031699  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14003169e  mov     dword ptr [rbx], 0
0x1400316a4  jmp     short loc_140031648
0x1400316a6  mov     ecx, [rbx]; workQueueId
0x1400316a8  lea     rdx, [rsp+58h+taskId]; taskId
0x1400316ad  mov     [rsp+58h+taskId], 0
0x1400316b5  call    cs:__imp_RtwqGetWorkQueueMMCSSTaskId
0x1400316bb  test    cs:byte_1400E7E41, 8
0x1400316c2  jz      short loc_1400316DE
0x1400316c4  mov     eax, [rsp+58h+taskId]
0x1400316c8  lea     rdx, AudioCore_Pump_CreateLocalWorkQueue
0x1400316cf  mov     r9d, [rbx]
0x1400316d2  mov     r8, rsi
0x1400316d5  mov     [rsp+58h+var_38], eax
0x1400316d9  call    McTemplateU0pqq_EtwEventWriteTransfer
0x1400316de  xor     eax, eax
0x1400316e0  add     rsp, 38h
0x1400316e4  pop     rdi
0x1400316e5  pop     rsi
0x1400316e6  pop     rbp
0x1400316e7  pop     rbx
0x1400316e8  retn
```
