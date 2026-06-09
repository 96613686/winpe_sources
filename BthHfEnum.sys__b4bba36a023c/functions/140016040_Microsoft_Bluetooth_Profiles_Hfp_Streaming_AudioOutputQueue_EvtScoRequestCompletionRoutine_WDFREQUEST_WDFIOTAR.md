# Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue::EvtScoRequestCompletionRoutine(WDFREQUEST__ *,WDFIOTARGET__ *,_WDF_REQUEST_COMPLETION_PARAMS *,void *)

- ea: `0x140016040`
- end: `0x14001608e`
- name: `?EvtScoRequestCompletionRoutine@AudioOutputQueue@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@CAXPEAUWDFREQUEST__@@PEAUWDFIOTARGET__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@PEAX@Z`
- size: `78`
- prototype: `static void(struct WDFREQUEST__ *, struct WDFIOTARGET__ *, struct _WDF_REQUEST_COMPLETION_PARAMS *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140016520`
- `0x14001ae00`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue::EvtScoRequestCompletionRoutine(
        struct WDFREQUEST__ *a1,
        struct WDFIOTARGET__ *a2,
        struct _WDF_REQUEST_COMPLETION_PARAMS *a3,
        Microsoft::Bluetooth::Foundation::SentRequestCollection **a4)
{
  struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext *v6; // rax
  struct WDFIOTARGET__ *v7; // r8

  v6 = (struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFREQUEST__ *, __int64 *))(WdfFunctions_01015 + 1616))(
                                                                                  WdfDriverGlobals,
                                                                                  a1,
                                                                                  off_140022500);
  Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue::ScoRequestCompletionRoutine(a4, v6, v7, a3);
}

```

## disassembly

```asm
0x140016040  mov     [rsp+arg_0], rbx
0x140016045  push    rdi
0x140016046  sub     rsp, 20h
0x14001604a  mov     rax, cs:WdfFunctions_01015
0x140016051  mov     rbx, r8
0x140016054  mov     r8, cs:off_140022500
0x14001605b  mov     rdx, rcx
0x14001605e  mov     rcx, cs:WdfDriverGlobals
0x140016065  mov     rdi, r9
0x140016068  mov     rax, [rax+650h]
0x14001606f  call    _guard_dispatch_icall
0x140016074  mov     r9, rbx; struct _WDF_REQUEST_COMPLETION_PARAMS *
0x140016077  mov     rdx, rax; struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext *
0x14001607a  mov     rcx, rdi; this
0x14001607d  call    ?ScoRequestCompletionRoutine@AudioOutputQueue@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@AEAAXPEAVRequestContext@23456@PEAUWDFIOTARGET__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue::ScoRequestCompletionRoutine(Microsoft::Bluetooth::Profiles::Hfp::Streaming::RequestContext *,WDFIOTARGET__ *,_WDF_REQUEST_COMPLETION_PARAMS *)
0x140016082  mov     rbx, [rsp+28h+arg_0]
0x140016087  add     rsp, 20h
0x14001608b  pop     rdi
0x14001608c  retn
```
