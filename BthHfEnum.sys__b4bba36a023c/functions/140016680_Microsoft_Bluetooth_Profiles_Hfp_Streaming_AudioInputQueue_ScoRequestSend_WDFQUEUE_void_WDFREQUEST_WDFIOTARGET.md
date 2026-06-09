# Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::ScoRequestSend(WDFQUEUE__ *,void (*)(WDFREQUEST__ *,WDFIOTARGET__ *,_WDF_REQUEST_COMPLETION_PARAMS *,void *),void *,WDFREQUEST__ *)

- ea: `0x140016680`
- end: `0x140016738`
- name: `?ScoRequestSend@AudioInputQueue@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@EEAAJPEAUWDFQUEUE__@@P6AXPEAUWDFREQUEST__@@PEAUWDFIOTARGET__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@PEAX@Z41@Z`
- size: `184`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue *__hidden this, struct WDFQUEUE__ *, void (*)(struct WDFREQUEST__ *, struct WDFIOTARGET__ *, struct _WDF_REQUEST_COMPLETION_PARAMS *, void *), void *, struct WDFREQUEST__ *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140011a0c`
- `0x140015e10`
- `0x140016214`
- `0x140016680`
- `0x140016c14`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioInputQueue::ScoRequestSend(
        Microsoft::Bluetooth::Foundation::SentRequestCollection **this,
        struct WDFQUEUE__ *a2,
        void (*a3)(struct WDFREQUEST__ *, struct WDFIOTARGET__ *, struct _WDF_REQUEST_COMPLETION_PARAMS *, void *),
        void *a4,
        struct WDFREQUEST__ *a5)
{
  int v9; // edi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 33, a3, a5, this - 2);
  }
  v9 = Microsoft::Bluetooth::Foundation::SentRequestCollection::Add(this[29], a5);
  if ( v9 >= 0 )
  {
    v9 = AudioQueueClient_SendTransferBrb(a2, a3, a4, a5);
    if ( v9 < 0 )
      Microsoft::Bluetooth::Foundation::SentRequestCollection::Remove(this[29], a5);
    else
      ++*((_DWORD *)this + 63);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140016680  push    rbx
0x140016682  push    rbp
0x140016683  push    rdi
0x140016684  push    r14
0x140016686  push    r15
0x140016688  sub     rsp, 30h
0x14001668c  mov     rbp, r9
0x14001668f  mov     r14, r8
0x140016692  mov     r15, rdx
0x140016695  mov     rbx, rcx
0x140016698  mov     rcx, cs:WPP_GLOBAL_Control
0x14001669f  lea     rax, WPP_GLOBAL_Control
0x1400166a6  cmp     rcx, rax
0x1400166a9  jz      short loc_1400166D7
0x1400166ab  mov     eax, [rcx+2Ch]
0x1400166ae  test    al, 20h
0x1400166b0  jz      short loc_1400166D7
0x1400166b2  cmp     byte ptr [rcx+29h], 5
0x1400166b6  jb      short loc_1400166D7
0x1400166b8  mov     r9, [rsp+58h+arg_20]
0x1400166c0  lea     rax, [rbx-10h]
0x1400166c4  mov     rcx, [rcx+18h]
0x1400166c8  mov     edx, 21h ; '!'
0x1400166cd  mov     [rsp+58h+var_38], rax
0x1400166d2  call    WPP_SF_qq
0x1400166d7  mov     rdx, [rsp+58h+arg_20]; struct WDFREQUEST__ *
0x1400166df  mov     rcx, [rbx+0E8h]; this
0x1400166e6  call    ?Add@SentRequestCollection@Foundation@Bluetooth@Microsoft@@QEAAJPEAUWDFREQUEST__@@@Z; Microsoft::Bluetooth::Foundation::SentRequestCollection::Add(WDFREQUEST__ *)
0x1400166eb  mov     edi, eax
0x1400166ed  test    eax, eax
0x1400166ef  js      short loc_140016729
0x1400166f1  mov     r9, [rsp+58h+arg_20]
0x1400166f9  mov     r8, rbp
0x1400166fc  mov     rdx, r14
0x1400166ff  mov     rcx, r15
0x140016702  call    AudioQueueClient_SendTransferBrb
0x140016707  mov     edi, eax
0x140016709  test    eax, eax
0x14001670b  js      short loc_140016715
0x14001670d  inc     dword ptr [rbx+0FCh]
0x140016713  jmp     short loc_140016729
0x140016715  mov     rdx, [rsp+58h+arg_20]; struct WDFREQUEST__ *
0x14001671d  mov     rcx, [rbx+0E8h]; this
0x140016724  call    ?Remove@SentRequestCollection@Foundation@Bluetooth@Microsoft@@QEAAXPEAUWDFREQUEST__@@@Z; Microsoft::Bluetooth::Foundation::SentRequestCollection::Remove(WDFREQUEST__ *)
0x140016729  mov     eax, edi
0x14001672b  add     rsp, 30h
0x14001672f  pop     r15
0x140016731  pop     r14
0x140016733  pop     rdi
0x140016734  pop     rbp
0x140016735  pop     rbx
0x140016736  retn
```
