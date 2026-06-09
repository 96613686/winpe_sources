# BfsQueueDeferredWorkItemAndWait

- ea: `0x14000ff3c`
- end: `0x140010131`
- name: `BfsQueueDeferredWorkItemAndWait`
- size: `501`
- prototype: `__int64 __usercall@<rax>(PVOID FltObject@<rcx>, PVOID@<rdx>, PFLT_CALLBACK_DATA Data@<r8>, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400055d8`
- `0x140005d4c`
- `0x14000dadc`

## callees

- `0x140001008`
- `0x14000ff3c`
- `0x140013730`
- `0x140013b40`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000ff95`
- `ntoskrnl!KeInitializeEvent` at `0x14000ff95`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400100c2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400100c2`
- `FLTMGR!FltObjectDereference` at `0x1400100f0`
- `FLTMGR!FltObjectDereference` at `0x140010106`
- `FLTMGR!FltObjectDereference` at `0x1400100f0`
- `FLTMGR!FltObjectDereference` at `0x140010106`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x1400100da`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x1400100da`
- `FLTMGR!FltQueueDeferredIoWorkItem` at `0x140010062`
- `FLTMGR!FltQueueDeferredIoWorkItem` at `0x140010062`
- `FLTMGR!FltAllocateDeferredIoWorkItem` at `0x14001002b`
- `FLTMGR!FltAllocateDeferredIoWorkItem` at `0x14001002b`
- `FLTMGR!FltObjectReference` at `0x14000ffa4`
- `FLTMGR!FltObjectReference` at `0x140010000`
- `FLTMGR!FltObjectReference` at `0x14000ffa4`
- `FLTMGR!FltObjectReference` at `0x140010000`

## pseudocode

```c
__int64 __fastcall BfsQueueDeferredWorkItemAndWait(
        PVOID FltObject,
        PVOID a2,
        PFLT_CALLBACK_DATA Data,
        __int64 a4,
        __int64 a5)
{
  NTSTATUS v9; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  NTSTATUS v12; // ebx
  __int64 v13; // rcx
  struct _FLT_DEFERRED_IO_WORKITEM *DeferredIoWorkItem; // rdi
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  int Context; // [rsp+20h] [rbp-91h]
  int Contexta; // [rsp+20h] [rbp-91h]
  _DWORD v21[4]; // [rsp+30h] [rbp-81h] BYREF
  _OWORD v22[5]; // [rsp+40h] [rbp-71h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+90h] [rbp-21h] BYREF
  _DWORD *v24; // [rsp+B0h] [rbp-1h]
  __int64 v25; // [rsp+B8h] [rbp+7h]

  memset(v22, 0, 0x48u);
  *((_QWORD *)&v22[3] + 1) = Data;
  *(_QWORD *)&v22[3] = a5;
  *((_QWORD *)&v22[2] + 1) = a4;
  KeInitializeEvent((PRKEVENT)&v22[1], SynchronizationEvent, 0);
  v9 = FltObjectReference(FltObject);
  v12 = v9;
  if ( v9 < 0 )
  {
    v13 = (unsigned int)dword_140019000;
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_17;
    v21[0] = v9;
    goto LABEL_4;
  }
  *(_QWORD *)&v22[0] = FltObject;
  if ( !a2 || (v12 = FltObjectReference(a2), v12 >= 0) )
  {
    *((_QWORD *)&v22[0] + 1) = a2;
    DeferredIoWorkItem = FltAllocateDeferredIoWorkItem();
    if ( DeferredIoWorkItem )
    {
      v12 = FltQueueDeferredIoWorkItem(
              DeferredIoWorkItem,
              Data,
              BfspSynchronousDeferredWorkItemRoutine,
              DelayedWorkQueue,
              v22);
      if ( v12 < 0 || (v12 = KeWaitForSingleObject(&v22[1], UserRequest, 0, 0, 0), v12 < 0) )
      {
        if ( (unsigned int)dword_140019000 > 3 )
        {
          v21[0] = v12;
          v24 = v21;
          v25 = 4;
          tlgWriteTransfer_EtwWriteTransfer(v15, (unsigned __int8 *)&byte_140016D91, v16, v17, Contexta, &v23);
        }
      }
      else
      {
        v12 = v22[4];
      }
      FltFreeDeferredIoWorkItem(DeferredIoWorkItem);
      goto LABEL_17;
    }
    v12 = -1073741801;
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v21[0] = v12;
LABEL_4:
    v25 = 4;
    v24 = v21;
    tlgWriteTransfer_EtwWriteTransfer(v13, (unsigned __int8 *)&byte_140016D91, v10, v11, Context, &v23);
  }
LABEL_17:
  if ( *((_QWORD *)&v22[0] + 1) )
    FltObjectDereference(a2);
  if ( *(_QWORD *)&v22[0] )
    FltObjectDereference(FltObject);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000ff3c  push    rbp
0x14000ff3e  push    rbx
0x14000ff3f  push    rsi
0x14000ff40  push    rdi
0x14000ff41  push    r14
0x14000ff43  push    r15
0x14000ff45  lea     rbp, [rsp-27h]
0x14000ff4a  sub     rsp, 0D8h
0x14000ff51  mov     rax, cs:__security_cookie
0x14000ff58  xor     rax, rsp
0x14000ff5b  mov     [rbp+4Fh+var_40], rax
0x14000ff5f  mov     rbx, [rbp+4Fh+arg_20]
0x14000ff63  mov     rsi, rdx
0x14000ff66  xor     edx, edx; Val
0x14000ff68  mov     r15, r8
0x14000ff6b  mov     r14, rcx
0x14000ff6e  mov     rdi, r9
0x14000ff71  lea     rcx, [rbp+4Fh+var_C0]; void *
0x14000ff75  lea     r8d, [rdx+48h]; Size
0x14000ff79  call    memset
0x14000ff7e  xor     r8d, r8d; State
0x14000ff81  mov     [rbp+4Fh+var_88], r15
0x14000ff85  lea     rcx, [rbp+4Fh+Event]; Event
0x14000ff89  mov     [rbp+4Fh+var_90], rbx
0x14000ff8d  mov     [rbp+4Fh+var_98], rdi
0x14000ff91  lea     edx, [r8+1]; Type
0x14000ff95  call    cs:__imp_KeInitializeEvent
0x14000ff9c  nop     dword ptr [rax+rax+00h]
0x14000ffa1  mov     rcx, r14; FltObject
0x14000ffa4  call    cs:__imp_FltObjectReference
0x14000ffab  nop     dword ptr [rax+rax+00h]
0x14000ffb0  mov     ebx, eax
0x14000ffb2  test    eax, eax
0x14000ffb4  jns     short loc_14000FFF4
0x14000ffb6  mov     ecx, cs:dword_140019000; int
0x14000ffbc  cmp     ecx, 3
0x14000ffbf  jbe     loc_1400100E6
0x14000ffc5  mov     [rsp+100h+var_D0], eax
0x14000ffc9  lea     rax, [rsp+100h+var_D0]
0x14000ffce  mov     [rbp+4Fh+var_48], 4
0x14000ffd6  mov     [rbp+4Fh+var_50], rax
0x14000ffda  lea     rdx, byte_140016D91; int
0x14000ffe1  lea     rax, [rbp+4Fh+var_70]
0x14000ffe5  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x14000ffea  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000ffef  jmp     loc_1400100E6
0x14000fff4  mov     qword ptr [rbp+4Fh+var_C0], r14
0x14000fff8  test    rsi, rsi
0x14000fffb  jz      short loc_140010027
0x14000fffd  mov     rcx, rsi; FltObject
0x140010000  call    cs:__imp_FltObjectReference
0x140010007  nop     dword ptr [rax+rax+00h]
0x14001000c  mov     ebx, eax
0x14001000e  test    eax, eax
0x140010010  jns     short loc_140010027
0x140010012  mov     eax, cs:dword_140019000
0x140010018  cmp     eax, 3
0x14001001b  jbe     loc_1400100E6
0x140010021  mov     [rsp+100h+var_D0], ebx
0x140010025  jmp     short loc_14000FFC9
0x140010027  mov     [rbp+4Fh+var_B8], rsi
0x14001002b  call    cs:__imp_FltAllocateDeferredIoWorkItem
0x140010032  nop     dword ptr [rax+rax+00h]
0x140010037  mov     rdi, rax
0x14001003a  test    rax, rax
0x14001003d  jnz     short loc_140010046
0x14001003f  mov     ebx, 0C0000017h
0x140010044  jmp     short loc_140010012
0x140010046  lea     rax, [rbp+4Fh+var_C0]
0x14001004a  mov     r9d, 1; QueueType
0x140010050  lea     r8, BfspSynchronousDeferredWorkItemRoutine; WorkerRoutine
0x140010057  mov     [rsp+100h+Context], rax; int
0x14001005c  mov     rdx, r15; Data
0x14001005f  mov     rcx, rdi; FltWorkItem
0x140010062  call    cs:__imp_FltQueueDeferredIoWorkItem
0x140010069  nop     dword ptr [rax+rax+00h]
0x14001006e  mov     ebx, eax
0x140010070  test    eax, eax
0x140010072  jns     short loc_1400100AB
0x140010074  mov     eax, cs:dword_140019000
0x14001007a  cmp     eax, 3
0x14001007d  jbe     short loc_1400100D7
0x14001007f  lea     rax, [rsp+100h+var_D0]
0x140010084  mov     [rsp+100h+var_D0], ebx
0x140010088  mov     [rbp+4Fh+var_50], rax
0x14001008c  lea     rdx, byte_140016D91; int
0x140010093  lea     rax, [rbp+4Fh+var_70]
0x140010097  mov     [rbp+4Fh+var_48], 4
0x14001009f  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x1400100a4  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400100a9  jmp     short loc_1400100D7
0x1400100ab  xor     r9d, r9d; Alertable
0x1400100ae  mov     [rsp+100h+Context], 0; Timeout
0x1400100b7  xor     r8d, r8d; WaitMode
0x1400100ba  lea     rcx, [rbp+4Fh+Event]; Object
0x1400100be  lea     edx, [r9+6]; WaitReason
0x1400100c2  call    cs:__imp_KeWaitForSingleObject
0x1400100c9  nop     dword ptr [rax+rax+00h]
0x1400100ce  mov     ebx, eax
0x1400100d0  test    eax, eax
0x1400100d2  js      short loc_140010074
0x1400100d4  mov     ebx, [rbp+4Fh+var_80]
0x1400100d7  mov     rcx, rdi; FltWorkItem
0x1400100da  call    cs:__imp_FltFreeDeferredIoWorkItem
0x1400100e1  nop     dword ptr [rax+rax+00h]
0x1400100e6  cmp     [rbp+4Fh+var_B8], 0
0x1400100eb  jz      short loc_1400100FC
0x1400100ed  mov     rcx, rsi; FltObject
0x1400100f0  call    cs:__imp_FltObjectDereference
0x1400100f7  nop     dword ptr [rax+rax+00h]
0x1400100fc  cmp     qword ptr [rbp+4Fh+var_C0], 0
0x140010101  jz      short loc_140010112
0x140010103  mov     rcx, r14; FltObject
0x140010106  call    cs:__imp_FltObjectDereference
0x14001010d  nop     dword ptr [rax+rax+00h]
0x140010112  mov     eax, ebx
0x140010114  mov     rcx, [rbp+4Fh+var_40]
0x140010118  xor     rcx, rsp; StackCookie
0x14001011b  call    __security_check_cookie
0x140010120  add     rsp, 0D8h
0x140010127  pop     r15
0x140010129  pop     r14
0x14001012b  pop     rdi
0x14001012c  pop     rsi
0x14001012d  pop     rbx
0x14001012e  pop     rbp
0x14001012f  retn
```
