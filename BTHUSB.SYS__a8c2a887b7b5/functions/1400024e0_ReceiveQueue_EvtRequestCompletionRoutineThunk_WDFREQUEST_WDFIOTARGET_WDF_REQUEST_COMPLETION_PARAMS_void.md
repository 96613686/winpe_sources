# ReceiveQueue::EvtRequestCompletionRoutineThunk(WDFREQUEST__ *,WDFIOTARGET__ *,_WDF_REQUEST_COMPLETION_PARAMS *,void *)

- ea: `0x1400024e0`
- end: `0x14000255e`
- name: `?EvtRequestCompletionRoutineThunk@ReceiveQueue@@CAXPEAUWDFREQUEST__@@PEAUWDFIOTARGET__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@PEAX@Z`
- size: `126`
- prototype: `void __fastcall(struct WDFREQUEST__ *, struct WDFIOTARGET__ *, struct _WDF_REQUEST_COMPLETION_PARAMS *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002234`
- `0x14000de00`

## pseudocode

```c
void __fastcall ReceiveQueue::EvtRequestCompletionRoutineThunk(
        struct WDFREQUEST__ *a1,
        struct WDFIOTARGET__ *a2,
        struct _WDF_REQUEST_COMPLETION_PARAMS *a3,
        struct _URB *a4)
{
  __int64 v7; // rax
  ReceiveQueue *v8; // rax

  v7 = ((__int64 (__fastcall *)(_LIST_ENTRY *, struct WDFREQUEST__ *))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[141].Flink)(
         WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
         a1);
  v8 = (ReceiveQueue *)((__int64 (__fastcall *)(_LIST_ENTRY *, __int64, __int64 *))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[101].Flink)(
                         WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
                         v7,
                         off_140013088);
  ReceiveQueue::EvtRequestCompletionRoutine(v8, a1, a3, a4);
}

```

## disassembly

```asm
0x1400024e0  mov     [rsp+arg_0], rbx
0x1400024e5  mov     [rsp+arg_8], rsi
0x1400024ea  push    rdi
0x1400024eb  sub     rsp, 20h
0x1400024ef  mov     rax, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x1400024f6  mov     rbx, rcx
0x1400024f9  mov     rdx, rcx
0x1400024fc  mov     rdi, r9
0x1400024ff  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x140002506  mov     rsi, r8
0x140002509  mov     rax, [rax+8D0h]
0x140002510  call    _guard_dispatch_icall
0x140002515  mov     rdx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x14000251c  mov     r10, rax
0x14000251f  mov     r8, cs:off_140013088
0x140002526  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x14000252d  mov     rax, [rdx+650h]
0x140002534  mov     rdx, r10
0x140002537  call    _guard_dispatch_icall
0x14000253c  mov     r9, rdi; void *
0x14000253f  mov     r8, rsi; struct _WDF_REQUEST_COMPLETION_PARAMS *
0x140002542  mov     rdx, rbx; struct WDFREQUEST__ *
0x140002545  mov     rcx, rax; this
0x140002548  call    ?EvtRequestCompletionRoutine@ReceiveQueue@@AEAAXPEAUWDFREQUEST__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@PEAX@Z; ReceiveQueue::EvtRequestCompletionRoutine(WDFREQUEST__ *,_WDF_REQUEST_COMPLETION_PARAMS *,void *)
0x14000254d  mov     rbx, [rsp+28h+arg_0]
0x140002552  mov     rsi, [rsp+28h+arg_8]
0x140002557  add     rsp, 20h
0x14000255b  pop     rdi
0x14000255c  retn
```
