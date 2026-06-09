# ReceiveQueue::EvtRequestCompletionRoutine(WDFREQUEST__ *,_WDF_REQUEST_COMPLETION_PARAMS *,void *)

- ea: `0x140002234`
- end: `0x1400024d6`
- name: `?EvtRequestCompletionRoutine@ReceiveQueue@@AEAAXPEAUWDFREQUEST__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@PEAX@Z`
- size: `674`
- prototype: `void __fastcall(ReceiveQueue *this, struct WDFREQUEST__ *, struct _WDF_REQUEST_COMPLETION_PARAMS *, struct _URB *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400024e0`

## callees

- `0x140002234`
- `0x1400025e4`
- `0x140002d0c`
- `0x140002dcc`
- `0x140002ec0`
- `0x140002fb4`
- `0x14000c9c0`
- `0x14000c9fc`
- `0x14000de00`

## pseudocode

```c
void __fastcall ReceiveQueue::EvtRequestCompletionRoutine(
        ReceiveQueue *this,
        struct WDFREQUEST__ *a2,
        struct _WDF_REQUEST_COMPLETION_PARAMS *a3,
        struct _URB *a4)
{
  int Status; // r14d
  unsigned int v6; // r12d
  unsigned int TransferBufferLength; // r15d
  char v10; // al
  int v11; // edx
  PDEVICE_OBJECT v12; // rcx
  char v13; // bl
  __int64 v14; // r9
  char v15; // bl
  __int64 v16; // rcx
  __int64 v17; // r8
  char v18; // bl
  void *ConfigurationHandle; // rax
  __int64 v20; // r8
  char v21; // [rsp+20h] [rbp-88h]

  Status = a3->IoStatus.Status;
  v6 = a4->UrbHeader.Status;
  TransferBufferLength = a4->UrbControlTransfer.TransferBufferLength;
  if ( Status == -1073741536 )
  {
    v10 = ((__int64 (__fastcall *)(_LIST_ENTRY *))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[128].Blink)(WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink);
    v11 = 0;
    if ( v10 )
    {
      v12 = WPP_GLOBAL_Control;
      v13 = 1;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        v13 = 0;
      v14 = *((_QWORD *)this + 1);
      v21 = 4;
LABEL_7:
      LOBYTE(v11) = v13;
      WPP_RECORDER_AND_TRACE_SF_qqdDD(v12->AttachedDevice, v11, (_DWORD)a3, *(_QWORD *)(v14 + 8), v21);
LABEL_32:
      ReceiveQueue::ReturnUrbToPool(this, a4);
      v17 = (unsigned int)Status;
      goto LABEL_33;
    }
LABEL_9:
    v12 = WPP_GLOBAL_Control;
    v13 = 1;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      v13 = 0;
    v14 = *((_QWORD *)this + 1);
    v21 = 2;
    goto LABEL_7;
  }
  v11 = 0;
  if ( Status < 0 )
    goto LABEL_9;
  if ( !v6 )
  {
    if ( TransferBufferLength )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        LOBYTE(v11) = 1;
      WPP_RECORDER_AND_TRACE_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        v11,
        (_DWORD)a3,
        *(_QWORD *)(*((_QWORD *)this + 1) + 8LL));
      ConfigurationHandle = a4->UrbSelectInterface.ConfigurationHandle;
      if ( ConfigurationHandle == *((void **)this + 3) )
      {
        v20 = 0;
      }
      else
      {
        if ( ConfigurationHandle != *((void **)this + 4) )
          MicrosoftTelemetryAssertTriggeredMsgKM("Unknown pipe handle in URB.");
        v20 = 1;
      }
      ((void (__fastcall *)(__int64, struct WDFREQUEST__ *, __int64))qword_140013298)(BthDriverGlobals, a2, v20);
      ((void (__fastcall *)(__int64, struct WDFREQUEST__ *, _QWORD, _QWORD))qword_1400132A0)(
        BthDriverGlobals,
        a2,
        0,
        a4->UrbControlTransfer.TransferBufferLength);
    }
    else
    {
      v18 = 1;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        v18 = 0;
      LOBYTE(v11) = v18;
      WPP_RECORDER_AND_TRACE_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        v11,
        (_DWORD)a3,
        *(_QWORD *)(*((_QWORD *)this + 1) + 8LL));
      ((void (__fastcall *)(__int64, struct WDFREQUEST__ *))qword_1400132B0)(BthDriverGlobals, a2);
    }
    goto LABEL_32;
  }
  v15 = 1;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    v15 = 0;
  LOBYTE(v11) = v15;
  WPP_RECORDER_AND_TRACE_SF_qqDD(
    WPP_GLOBAL_Control->AttachedDevice,
    v11,
    (_DWORD)a3,
    *(_QWORD *)(*((_QWORD *)this + 1) + 8LL));
  MicrosoftTelemetryAssertTriggeredArgsMsgKM(v16, v6, TransferBufferLength);
  ReceiveQueue::ReturnUrbToPool(this, a4);
  v17 = 3221225473LL;
LABEL_33:
  ((void (__fastcall *)(_LIST_ENTRY *, struct WDFREQUEST__ *, __int64))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[131].Blink)(
    WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
    a2,
    v17);
}

```

## disassembly

```asm
0x140002234  push    rbx
0x140002236  push    rbp
0x140002237  push    rsi
0x140002238  push    rdi
0x140002239  push    r12
0x14000223b  push    r14
0x14000223d  push    r15
0x14000223f  sub     rsp, 70h
0x140002243  mov     r14d, [r8+8]
0x140002247  mov     rbp, r9
0x14000224a  mov     r12d, [r9+4]
0x14000224e  mov     rdi, rdx
0x140002251  mov     r15d, [r9+24h]
0x140002255  mov     rsi, rcx
0x140002258  cmp     r14d, 0C0000120h
0x14000225f  jnz     short loc_1400022DA
0x140002261  mov     rax, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x140002268  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x14000226f  mov     rax, [rax+808h]
0x140002276  call    _guard_dispatch_icall
0x14000227b  xor     edx, edx
0x14000227d  test    al, al
0x14000227f  jz      short loc_1400022E1
0x140002281  mov     rcx, cs:WPP_GLOBAL_Control
0x140002288  lea     ebx, [rdx+1]
0x14000228b  mov     eax, [rcx+2Ch]
0x14000228e  test    bl, al
0x140002290  jz      short loc_140002298
0x140002292  cmp     byte ptr [rcx+29h], 4
0x140002296  jnb     short loc_14000229A
0x140002298  mov     bl, dl
0x14000229a  mov     r9, [rsi+8]
0x14000229e  mov     [rsp+0A8h+var_48], r15d
0x1400022a3  mov     [rsp+0A8h+var_50], r12d
0x1400022a8  mov     [rsp+0A8h+var_58], r14d
0x1400022ad  mov     rax, [r9]
0x1400022b0  mov     [rsp+0A8h+var_60], rdi
0x1400022b5  mov     [rsp+0A8h+var_68], rax
0x1400022ba  mov     [rsp+0A8h+var_78], 0Fh
0x1400022c1  mov     [rsp+0A8h+var_88], 4
0x1400022c6  mov     r9, [r9+8]
0x1400022ca  mov     dl, bl
0x1400022cc  mov     rcx, [rcx+18h]
0x1400022d0  call    WPP_RECORDER_AND_TRACE_SF_qqdDD
0x1400022d5  jmp     loc_14000249B
0x1400022da  xor     edx, edx
0x1400022dc  test    r14d, r14d
0x1400022df  jns     short loc_14000232A
0x1400022e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400022e8  mov     ebx, 1
0x1400022ed  mov     eax, [rcx+2Ch]
0x1400022f0  test    bl, al
0x1400022f2  jz      short loc_1400022FA
0x1400022f4  cmp     byte ptr [rcx+29h], 2
0x1400022f8  jnb     short loc_1400022FC
0x1400022fa  mov     bl, dl
0x1400022fc  mov     r9, [rsi+8]
0x140002300  mov     [rsp+0A8h+var_48], r15d
0x140002305  mov     [rsp+0A8h+var_50], r12d
0x14000230a  mov     [rsp+0A8h+var_58], r14d
0x14000230f  mov     rax, [r9]
0x140002312  mov     [rsp+0A8h+var_60], rdi
0x140002317  mov     [rsp+0A8h+var_68], rax
0x14000231c  mov     [rsp+0A8h+var_78], 10h
0x140002323  mov     [rsp+0A8h+var_88], 2
0x140002328  jmp     short loc_1400022C6
0x14000232a  test    r12d, r12d
0x14000232d  jz      short loc_140002395
0x14000232f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002336  mov     ebx, 1
0x14000233b  mov     eax, [rcx+2Ch]
0x14000233e  test    bl, al
0x140002340  jz      short loc_140002348
0x140002342  cmp     byte ptr [rcx+29h], 2
0x140002346  jnb     short loc_14000234A
0x140002348  mov     bl, dl
0x14000234a  mov     r9, [rsi+8]
0x14000234e  mov     dl, bl
0x140002350  mov     rcx, [rcx+18h]
0x140002354  mov     [rsp+0A8h+var_50], r15d
0x140002359  mov     [rsp+0A8h+var_58], r12d
0x14000235e  mov     rax, [r9]
0x140002361  mov     r9, [r9+8]
0x140002365  mov     [rsp+0A8h+var_60], rdi
0x14000236a  mov     [rsp+0A8h+var_68], rax
0x14000236f  call    WPP_RECORDER_AND_TRACE_SF_qqDD
0x140002374  mov     r8d, r15d; __annotation("Debug", "TelemetryAssert", "false", "NTSTATUS indicates success but USBD_STATUS indicates failure.")
0x140002377  mov     edx, r12d
0x14000237a  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x14000237f  mov     rdx, rbp; struct _URB *
0x140002382  mov     rcx, rsi; this
0x140002385  call    ?ReturnUrbToPool@ReceiveQueue@@AEAAXPEAU_URB@@@Z; ReceiveQueue::ReturnUrbToPool(_URB *)
0x14000238a  mov     r8d, 0C0000001h
0x140002390  jmp     loc_1400024A9
0x140002395  test    r15d, r15d
0x140002398  jnz     short loc_1400023EF
0x14000239a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023a1  lea     ebx, [r15+1]
0x1400023a5  mov     eax, [rcx+2Ch]
0x1400023a8  test    bl, al
0x1400023aa  jz      short loc_1400023B2
0x1400023ac  cmp     byte ptr [rcx+29h], 2
0x1400023b0  jnb     short loc_1400023B4
0x1400023b2  mov     bl, dl
0x1400023b4  mov     r9, [rsi+8]
0x1400023b8  mov     dl, bl
0x1400023ba  mov     rcx, [rcx+18h]
0x1400023be  mov     [rsp+0A8h+var_60], rdi
0x1400023c3  mov     rax, [r9]
0x1400023c6  mov     r9, [r9+8]
0x1400023ca  mov     [rsp+0A8h+var_68], rax
0x1400023cf  call    WPP_RECORDER_AND_TRACE_SF_qq
0x1400023d4  mov     rax, cs:qword_1400132B0
0x1400023db  mov     rdx, rdi
0x1400023de  mov     rcx, cs:BthDriverGlobals
0x1400023e5  call    _guard_dispatch_icall
0x1400023ea  jmp     loc_14000249B
0x1400023ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400023f6  mov     ebx, 1
0x1400023fb  mov     eax, [rcx+2Ch]
0x1400023fe  test    bl, al
0x140002400  jz      short loc_14000240A
0x140002402  cmp     byte ptr [rcx+29h], 4
0x140002406  jb      short loc_14000240A
0x140002408  mov     dl, bl
0x14000240a  mov     r9, [rsi+8]
0x14000240e  mov     rcx, [rcx+18h]
0x140002412  mov     [rsp+0A8h+var_58], r15d
0x140002417  mov     [rsp+0A8h+var_60], rdi
0x14000241c  mov     rax, [r9]
0x14000241f  mov     r9, [r9+8]
0x140002423  mov     [rsp+0A8h+var_68], rax
0x140002428  lea     rax, WPP_86e0affdec483798a987f478d619ae67_Traceguids
0x14000242f  mov     [rsp+0A8h+var_70], rax
0x140002434  mov     [rsp+0A8h+var_78], 13h
0x14000243b  mov     [rsp+0A8h+var_80], ebx
0x14000243f  call    WPP_RECORDER_AND_TRACE_SF_qqD
0x140002444  mov     rax, [rbp+18h]
0x140002448  cmp     rax, [rsi+18h]
0x14000244c  jnz     short loc_140002453
0x14000244e  xor     r8d, r8d
0x140002451  jmp     short loc_140002468
0x140002453  cmp     rax, [rsi+20h]
0x140002457  jz      short loc_140002465
0x140002459  lea     rcx, aUnknownPipeHan; __annotation("Debug", "TelemetryAssert", "urb->UrbBulkOrInterruptTransfer.PipeHandle == m_bulkInPipe", "Unknown pipe handle in URB.")
0x140002460  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140002465  mov     r8d, ebx
0x140002468  mov     rcx, cs:BthDriverGlobals
0x14000246f  mov     rdx, rdi
0x140002472  mov     rax, cs:qword_140013298
0x140002479  call    _guard_dispatch_icall
0x14000247e  mov     r9d, [rbp+24h]
0x140002482  xor     r8d, r8d
0x140002485  mov     rax, cs:qword_1400132A0
0x14000248c  mov     rdx, rdi
0x14000248f  mov     rcx, cs:BthDriverGlobals
0x140002496  call    _guard_dispatch_icall
0x14000249b  mov     rdx, rbp; struct _URB *
0x14000249e  mov     rcx, rsi; this
0x1400024a1  call    ?ReturnUrbToPool@ReceiveQueue@@AEAAXPEAU_URB@@@Z; ReceiveQueue::ReturnUrbToPool(_URB *)
0x1400024a6  mov     r8d, r14d
0x1400024a9  mov     rax, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x1400024b0  mov     rdx, rdi
0x1400024b3  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x1400024ba  mov     rax, [rax+838h]
0x1400024c1  call    _guard_dispatch_icall
0x1400024c6  add     rsp, 70h
0x1400024ca  pop     r15
0x1400024cc  pop     r14
0x1400024ce  pop     r12
0x1400024d0  pop     rdi
0x1400024d1  pop     rsi
0x1400024d2  pop     rbp
0x1400024d3  pop     rbx
0x1400024d4  retn
```
