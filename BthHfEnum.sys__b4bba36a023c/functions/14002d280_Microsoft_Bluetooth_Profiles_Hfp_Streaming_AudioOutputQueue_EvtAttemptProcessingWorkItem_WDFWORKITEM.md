# Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue::EvtAttemptProcessingWorkItem(WDFWORKITEM__ *)

- ea: `0x14002d280`
- end: `0x14002d312`
- name: `?EvtAttemptProcessingWorkItem@AudioOutputQueue@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@CAXPEAUWDFWORKITEM__@@@Z`
- size: `146`
- prototype: `void __fastcall(struct WDFWORKITEM__ *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1400114c8`
- `0x140016118`
- `0x140016a90`
- `0x14001ae00`
- `0x14002d280`
- `0x14002de78`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue::EvtAttemptProcessingWorkItem(
        struct WDFWORKITEM__ *a1)
{
  struct WDFQUEUE__ *v1; // rax
  Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue *v2; // rbx

  v1 = (struct WDFQUEUE__ *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFWORKITEM__ *))(WdfFunctions_01015 + 3048))(
                              WdfDriverGlobals,
                              a1);
  v2 = (Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue *)*((_QWORD *)Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioQueueProxy::GetContextFromObject(v1)
                                                                           + 1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_4de776f173d133e87e80f57736d58590_Traceguids, v2);
  }
  Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue::Process(v2);
  if ( (*(unsigned __int8 (__fastcall **)(Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue *))(*(_QWORD *)v2 + 8LL))(v2) )
    AudioQueueClient_AttemptProcessing(*((_QWORD *)v2 + 1));
}

```

## disassembly

```asm
0x14002d280  push    rbx
0x14002d282  sub     rsp, 20h
0x14002d286  mov     rax, cs:WdfFunctions_01015
0x14002d28d  mov     rdx, rcx
0x14002d290  mov     rcx, cs:WdfDriverGlobals
0x14002d297  mov     rax, [rax+0BE8h]
0x14002d29e  call    _guard_dispatch_icall
0x14002d2a3  mov     rcx, rax; struct WDFQUEUE__ *
0x14002d2a6  call    ?GetContextFromObject@AudioQueueProxy@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@SAPEAV123456@PEAUWDFQUEUE__@@@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioQueueProxy::GetContextFromObject(WDFQUEUE__ *)
0x14002d2ab  mov     rbx, [rax+8]
0x14002d2af  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d2b6  lea     rax, WPP_GLOBAL_Control
0x14002d2bd  cmp     rcx, rax
0x14002d2c0  jz      short loc_14002D2E7
0x14002d2c2  mov     eax, [rcx+2Ch]
0x14002d2c5  test    al, 20h
0x14002d2c7  jz      short loc_14002D2E7
0x14002d2c9  cmp     byte ptr [rcx+29h], 5
0x14002d2cd  jb      short loc_14002D2E7
0x14002d2cf  mov     rcx, [rcx+18h]
0x14002d2d3  lea     r8, WPP_4de776f173d133e87e80f57736d58590_Traceguids
0x14002d2da  mov     edx, 0Ah
0x14002d2df  mov     r9, rbx
0x14002d2e2  call    WPP_SF_q
0x14002d2e7  mov     rcx, rbx; this
0x14002d2ea  call    ?Process@AudioOutputQueue@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@AEAAXXZ; Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioOutputQueue::Process(void)
0x14002d2ef  mov     rax, [rbx]
0x14002d2f2  mov     rcx, rbx
0x14002d2f5  mov     rax, [rax+8]
0x14002d2f9  call    _guard_dispatch_icall
0x14002d2fe  test    al, al
0x14002d300  jz      short loc_14002D30B
0x14002d302  mov     rcx, [rbx+8]
0x14002d306  call    AudioQueueClient_AttemptProcessing
0x14002d30b  add     rsp, 20h
0x14002d30f  pop     rbx
0x14002d310  retn
```
