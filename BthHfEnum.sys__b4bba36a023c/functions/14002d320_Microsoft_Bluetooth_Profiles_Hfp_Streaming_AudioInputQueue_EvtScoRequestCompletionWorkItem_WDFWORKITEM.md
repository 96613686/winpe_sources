# Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::EvtScoRequestCompletionWorkItem(WDFWORKITEM__ *)

- ea: `0x14002d320`
- end: `0x14002d38f`
- name: `?EvtScoRequestCompletionWorkItem@AudioInputQueue@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@CAXPEAUWDFWORKITEM__@@@Z`
- size: `111`
- prototype: `void __fastcall(struct WDFWORKITEM__ *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1400114c8`
- `0x140016118`
- `0x14001ae00`
- `0x14002d320`
- `0x14002d474`
- `0x14002db70`
- `0x14002f250`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::EvtScoRequestCompletionWorkItem(
        struct WDFWORKITEM__ *a1)
{
  struct WDFQUEUE__ *v1; // rax
  _QWORD *v2; // rbx

  v1 = (struct WDFQUEUE__ *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFWORKITEM__ *))(WdfFunctions_01015 + 3048))(
                              WdfDriverGlobals,
                              a1);
  v2 = (_QWORD *)*((_QWORD *)Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioQueueProxy::GetContextFromObject(v1)
                 + 1);
  Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::Process((Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue *)v2);
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD *))(*v2 + 8LL))(v2) )
    AudioQueueClient_AttemptProcessing(v2[1]);
  if ( Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::IsRunning((Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue *)v2) )
    Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::ContinueReading((Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader *)(v2 + 4));
}

```

## disassembly

```asm
0x14002d320  push    rbx
0x14002d322  sub     rsp, 20h
0x14002d326  mov     rax, cs:WdfFunctions_01015
0x14002d32d  mov     rdx, rcx
0x14002d330  mov     rcx, cs:WdfDriverGlobals
0x14002d337  mov     rax, [rax+0BE8h]
0x14002d33e  call    _guard_dispatch_icall
0x14002d343  mov     rcx, rax; struct WDFQUEUE__ *
0x14002d346  call    ?GetContextFromObject@AudioQueueProxy@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@SAPEAV123456@PEAUWDFQUEUE__@@@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioQueueProxy::GetContextFromObject(WDFQUEUE__ *)
0x14002d34b  mov     rbx, [rax+8]
0x14002d34f  mov     rcx, rbx; this
0x14002d352  call    ?Process@AudioInputQueue@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@AEAAXXZ; Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::Process(void)
0x14002d357  mov     rax, [rbx]
0x14002d35a  mov     rcx, rbx
0x14002d35d  mov     rax, [rax+8]
0x14002d361  call    _guard_dispatch_icall
0x14002d366  test    al, al
0x14002d368  jz      short loc_14002D373
0x14002d36a  mov     rcx, [rbx+8]
0x14002d36e  call    AudioQueueClient_AttemptProcessing
0x14002d373  mov     rcx, rbx; this
0x14002d376  call    ?IsRunning@AudioInputQueue@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@AEBA_NXZ; Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::IsRunning(void)
0x14002d37b  test    al, al
0x14002d37d  jz      short loc_14002D388
0x14002d37f  lea     rcx, [rbx+20h]; this
0x14002d383  call    ?ContinueReading@ScoReader@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@QEAAXXZ; Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::ContinueReading(void)
0x14002d388  add     rsp, 20h
0x14002d38c  pop     rbx
0x14002d38d  retn
```
