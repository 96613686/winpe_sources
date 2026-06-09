# BfsQueueDeferredWorkItemAndWait

- ea: `0x1400100e0`
- end: `0x1400102d5`
- name: `BfsQueueDeferredWorkItemAndWait`
- size: `501`
- prototype: `__int64 __fastcall(PVOID FltObject, PVOID, PFLT_CALLBACK_DATA Data, __int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140005768`
- `0x140005edc`
- `0x14000dc70`

## callees

- `0x140001008`
- `0x1400100e0`
- `0x140013860`
- `0x140013c80`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140010139`
- `ntoskrnl!KeInitializeEvent` at `0x140010139`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010266`
- `ntoskrnl!KeWaitForSingleObject` at `0x140010266`
- `FLTMGR!FltObjectDereference` at `0x140010294`
- `FLTMGR!FltObjectDereference` at `0x1400102aa`
- `FLTMGR!FltObjectDereference` at `0x140010294`
- `FLTMGR!FltObjectDereference` at `0x1400102aa`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14001027e`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14001027e`
- `FLTMGR!FltQueueDeferredIoWorkItem` at `0x140010206`
- `FLTMGR!FltQueueDeferredIoWorkItem` at `0x140010206`
- `FLTMGR!FltAllocateDeferredIoWorkItem` at `0x1400101cf`
- `FLTMGR!FltAllocateDeferredIoWorkItem` at `0x1400101cf`
- `FLTMGR!FltObjectReference` at `0x140010148`
- `FLTMGR!FltObjectReference` at `0x1400101a4`
- `FLTMGR!FltObjectReference` at `0x140010148`
- `FLTMGR!FltObjectReference` at `0x1400101a4`

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
  int v10; // r8d
  int v11; // r9d
  NTSTATUS v12; // ebx
  int v13; // ecx
  struct _FLT_DEFERRED_IO_WORKITEM *DeferredIoWorkItem; // rdi
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
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
    v13 = dword_140019000;
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
          tlgWriteTransfer_EtwWriteTransfer(v15, (int)&byte_140016D91, v16, v17, Contexta, &v23);
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
    tlgWriteTransfer_EtwWriteTransfer(v13, (int)&byte_140016D91, v10, v11, Context, &v23);
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
0x1400100e0  push    rbp
0x1400100e2  push    rbx
0x1400100e3  push    rsi
0x1400100e4  push    rdi
0x1400100e5  push    r14
0x1400100e7  push    r15
0x1400100e9  lea     rbp, [rsp-27h]
0x1400100ee  sub     rsp, 0D8h
0x1400100f5  mov     rax, cs:__security_cookie
0x1400100fc  xor     rax, rsp
0x1400100ff  mov     [rbp+4Fh+var_40], rax
0x140010103  mov     rbx, [rbp+4Fh+arg_20]
0x140010107  mov     rsi, rdx
0x14001010a  xor     edx, edx; Val
0x14001010c  mov     r15, r8
0x14001010f  mov     r14, rcx
0x140010112  mov     rdi, r9
0x140010115  lea     rcx, [rbp+4Fh+var_C0]; void *
0x140010119  lea     r8d, [rdx+48h]; Size
0x14001011d  call    memset
0x140010122  xor     r8d, r8d; State
0x140010125  mov     [rbp+4Fh+var_88], r15
0x140010129  lea     rcx, [rbp+4Fh+Event]; Event
0x14001012d  mov     [rbp+4Fh+var_90], rbx
0x140010131  mov     [rbp+4Fh+var_98], rdi
0x140010135  lea     edx, [r8+1]; Type
0x140010139  call    cs:__imp_KeInitializeEvent
0x140010140  nop     dword ptr [rax+rax+00h]
0x140010145  mov     rcx, r14; FltObject
0x140010148  call    cs:__imp_FltObjectReference
0x14001014f  nop     dword ptr [rax+rax+00h]
0x140010154  mov     ebx, eax
0x140010156  test    eax, eax
0x140010158  jns     short loc_140010198
0x14001015a  mov     ecx, cs:dword_140019000; int
0x140010160  cmp     ecx, 3
0x140010163  jbe     loc_14001028A
0x140010169  mov     [rsp+100h+var_D0], eax
0x14001016d  lea     rax, [rsp+100h+var_D0]
0x140010172  mov     [rbp+4Fh+var_48], 4
0x14001017a  mov     [rbp+4Fh+var_50], rax
0x14001017e  lea     rdx, byte_140016D91; int
0x140010185  lea     rax, [rbp+4Fh+var_70]
0x140010189  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x14001018e  call    _tlgWriteTransfer_EtwWriteTransfer
0x140010193  jmp     loc_14001028A
0x140010198  mov     qword ptr [rbp+4Fh+var_C0], r14
0x14001019c  test    rsi, rsi
0x14001019f  jz      short loc_1400101CB
0x1400101a1  mov     rcx, rsi; FltObject
0x1400101a4  call    cs:__imp_FltObjectReference
0x1400101ab  nop     dword ptr [rax+rax+00h]
0x1400101b0  mov     ebx, eax
0x1400101b2  test    eax, eax
0x1400101b4  jns     short loc_1400101CB
0x1400101b6  mov     eax, cs:dword_140019000
0x1400101bc  cmp     eax, 3
0x1400101bf  jbe     loc_14001028A
0x1400101c5  mov     [rsp+100h+var_D0], ebx
0x1400101c9  jmp     short loc_14001016D
0x1400101cb  mov     [rbp+4Fh+var_B8], rsi
0x1400101cf  call    cs:__imp_FltAllocateDeferredIoWorkItem
0x1400101d6  nop     dword ptr [rax+rax+00h]
0x1400101db  mov     rdi, rax
0x1400101de  test    rax, rax
0x1400101e1  jnz     short loc_1400101EA
0x1400101e3  mov     ebx, 0C0000017h
0x1400101e8  jmp     short loc_1400101B6
0x1400101ea  lea     rax, [rbp+4Fh+var_C0]
0x1400101ee  mov     r9d, 1; QueueType
0x1400101f4  lea     r8, BfspSynchronousDeferredWorkItemRoutine; WorkerRoutine
0x1400101fb  mov     [rsp+100h+Context], rax; int
0x140010200  mov     rdx, r15; Data
0x140010203  mov     rcx, rdi; FltWorkItem
0x140010206  call    cs:__imp_FltQueueDeferredIoWorkItem
0x14001020d  nop     dword ptr [rax+rax+00h]
0x140010212  mov     ebx, eax
0x140010214  test    eax, eax
0x140010216  jns     short loc_14001024F
0x140010218  mov     eax, cs:dword_140019000
0x14001021e  cmp     eax, 3
0x140010221  jbe     short loc_14001027B
0x140010223  lea     rax, [rsp+100h+var_D0]
0x140010228  mov     [rsp+100h+var_D0], ebx
0x14001022c  mov     [rbp+4Fh+var_50], rax
0x140010230  lea     rdx, byte_140016D91; int
0x140010237  lea     rax, [rbp+4Fh+var_70]
0x14001023b  mov     [rbp+4Fh+var_48], 4
0x140010243  mov     [rsp+100h+var_D8], rax; PEVENT_DATA_DESCRIPTOR
0x140010248  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001024d  jmp     short loc_14001027B
0x14001024f  xor     r9d, r9d; Alertable
0x140010252  mov     [rsp+100h+Context], 0; Timeout
0x14001025b  xor     r8d, r8d; WaitMode
0x14001025e  lea     rcx, [rbp+4Fh+Event]; Object
0x140010262  lea     edx, [r9+6]; WaitReason
0x140010266  call    cs:__imp_KeWaitForSingleObject
0x14001026d  nop     dword ptr [rax+rax+00h]
0x140010272  mov     ebx, eax
0x140010274  test    eax, eax
0x140010276  js      short loc_140010218
0x140010278  mov     ebx, [rbp+4Fh+var_80]
0x14001027b  mov     rcx, rdi; FltWorkItem
0x14001027e  call    cs:__imp_FltFreeDeferredIoWorkItem
0x140010285  nop     dword ptr [rax+rax+00h]
0x14001028a  cmp     [rbp+4Fh+var_B8], 0
0x14001028f  jz      short loc_1400102A0
0x140010291  mov     rcx, rsi; FltObject
0x140010294  call    cs:__imp_FltObjectDereference
0x14001029b  nop     dword ptr [rax+rax+00h]
0x1400102a0  cmp     qword ptr [rbp+4Fh+var_C0], 0
0x1400102a5  jz      short loc_1400102B6
0x1400102a7  mov     rcx, r14; FltObject
0x1400102aa  call    cs:__imp_FltObjectDereference
0x1400102b1  nop     dword ptr [rax+rax+00h]
0x1400102b6  mov     eax, ebx
0x1400102b8  mov     rcx, [rbp+4Fh+var_40]
0x1400102bc  xor     rcx, rsp; StackCookie
0x1400102bf  call    __security_check_cookie
0x1400102c4  add     rsp, 0D8h
0x1400102cb  pop     r15
0x1400102cd  pop     r14
0x1400102cf  pop     rdi
0x1400102d0  pop     rsi
0x1400102d1  pop     rbx
0x1400102d2  pop     rbp
0x1400102d3  retn
```
