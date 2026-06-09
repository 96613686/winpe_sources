# TransmitQueue::Make(Fdo &,void *,utl::unique_ptr<TransmitQueue,WdfCpp::Details::ObjectContextDeleter<TransmitQueue>> &)

- ea: `0x14001a054`
- end: `0x14001a254`
- name: `?Make@TransmitQueue@@SAJAEAVFdo@@PEAXAEAV?$unique_ptr@VTransmitQueue@@U?$ObjectContextDeleter@VTransmitQueue@@@Details@WdfCpp@@@utl@@@Z`
- size: `512`
- prototype: `__int64 __fastcall(Fdo *this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140018b90`

## callees

- `0x140001ca8`
- `0x140001da0`
- `0x14000a670`
- `0x14000de00`
- `0x14000e1c0`
- `0x14001a054`

## pseudocode

```c
__int64 __fastcall TransmitQueue::Make(Fdo *this, __int64 a2, _QWORD *a3)
{
  __int64 v6; // rdx
  int v7; // ebx
  unsigned int RecorderLog; // eax
  __int64 v9; // r10
  int v10; // edx
  _QWORD *v12; // rax
  _QWORD *v13; // rbx
  _QWORD *v14; // rdx
  __int128 v15; // [rsp+50h] [rbp-59h] BYREF
  __int128 v16; // [rsp+60h] [rbp-49h]
  __int128 v17; // [rsp+70h] [rbp-39h]
  __int64 *v18; // [rsp+80h] [rbp-29h]
  _QWORD v19[12]; // [rsp+90h] [rbp-19h] BYREF
  __int64 v20; // [rsp+110h] [rbp+67h] BYREF

  memset(v19, 0, sizeof(v19));
  if ( LOBYTE(WPP_MAIN_CB.DeviceQueue.Lock) )
  {
    if ( (unsigned int)WdfStructureCount <= 0x21 )
      LODWORD(v19[0]) = -1;
    else
      LODWORD(v19[0]) = *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.32 + 264LL);
  }
  else
  {
    LODWORD(v19[0]) = 96;
  }
  *(_QWORD *)((char *)v19 + 4) = 2;
  LODWORD(v19[10]) = -1;
  v19[2] = TransmitQueue::EvtIoQueueIoDefaultThunk;
  v18 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  if ( LOBYTE(WPP_MAIN_CB.DeviceQueue.Lock) )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v15) = -1;
    else
      LODWORD(v15) = *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.32 + 304LL);
  }
  else
  {
    LODWORD(v15) = 56;
  }
  v6 = *(_QWORD *)this;
  v18 = off_1400130B0;
  *((_QWORD *)&v16 + 1) = 0x100000001LL;
  *((_QWORD *)&v15 + 1) = WdfCpp::ObjectContext<WDFQUEUE__ *,TransmitQueue,1>::EvtObjectContextCleanupThunk;
  v20 = 0;
  v7 = ((__int64 (__fastcall *)(_LIST_ENTRY *, __int64, _QWORD *, __int128 *, __int64 *))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[76].Flink)(
         WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
         v6,
         v19,
         &v15,
         &v20);
  if ( v7 >= 0 )
  {
    v12 = (_QWORD *)WdfCpp::ObjectContext<WDFQUEUE__ *,TransmitQueue,1>::EvtObjectContextCleanupThunk(v20);
    v13 = v12;
    if ( v12 )
    {
      *v12 = ((__int64 (__fastcall *)(_LIST_ENTRY *, _QWORD *))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[102].Flink)(
               WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
               v12);
      v13[1] = this;
      v13[2] = a2;
    }
    else
    {
      v13 = 0;
    }
    v14 = (_QWORD *)*a3;
    *a3 = v13;
    if ( v14 )
      ((void (__fastcall *)(_LIST_ENTRY *, _QWORD))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[104].Flink)(
        WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
        *v14);
    return 0;
  }
  else
  {
    RecorderLog = (unsigned int)Fdo::GetRecorderLog(this);
    WPP_RECORDER_AND_TRACE_SF_qd(
      *(_QWORD *)(v9 + 24),
      v10,
      *(_QWORD *)this,
      RecorderLog,
      2,
      1,
      10,
      (__int64)WPP_fa6aac3b369b3a7320c30fd5f31db9d3_Traceguids,
      *(_QWORD *)this,
      v7);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x14001a054  mov     [rsp-8+arg_8], rbx
0x14001a059  mov     [rsp-8+arg_10], rsi
0x14001a05e  push    rbp
0x14001a05f  push    rdi
0x14001a060  push    r14
0x14001a062  lea     rbp, [rsp-47h]
0x14001a067  sub     rsp, 0F0h
0x14001a06e  mov     rdi, r8
0x14001a071  mov     r14, rdx
0x14001a074  mov     rsi, rcx
0x14001a077  mov     ebx, 60h ; '`'
0x14001a07c  mov     r8d, ebx; Size
0x14001a07f  lea     rcx, [rbp+57h+var_70]; void *
0x14001a083  xor     edx, edx; Val
0x14001a085  call    memset
0x14001a08a  mov     r8b, byte ptr cs:WPP_MAIN_CB.DeviceQueue.Lock
0x14001a091  or      edx, 0FFFFFFFFh
0x14001a094  test    r8b, r8b
0x14001a097  jz      short loc_14001A0B9
0x14001a099  cmp     cs:WdfStructureCount, 21h ; '!'
0x14001a0a0  jbe     short loc_14001A0B4
0x14001a0a2  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceQueue.___u4
0x14001a0a9  mov     ecx, [rax+108h]
0x14001a0af  mov     [rbp+57h+var_70], ecx
0x14001a0b2  jmp     short loc_14001A0BC
0x14001a0b4  mov     [rbp+57h+var_70], edx
0x14001a0b7  jmp     short loc_14001A0BC
0x14001a0b9  mov     [rbp+57h+var_70], ebx
0x14001a0bc  xorps   xmm0, xmm0
0x14001a0bf  mov     [rbp+57h+var_6C], 2
0x14001a0c7  lea     rax, ?EvtIoQueueIoDefaultThunk@TransmitQueue@@CAXPEAUWDFQUEUE__@@PEAUWDFREQUEST__@@@Z; TransmitQueue::EvtIoQueueIoDefaultThunk(WDFQUEUE__ *,WDFREQUEST__ *)
0x14001a0ce  mov     [rbp+57h+var_20], edx
0x14001a0d1  mov     [rbp+57h+var_60], rax
0x14001a0d5  xor     eax, eax
0x14001a0d7  mov     [rbp+57h+var_80], rax
0x14001a0db  movups  [rbp+57h+var_B0], xmm0
0x14001a0df  movups  [rbp+57h+var_A0], xmm0
0x14001a0e3  movups  [rbp+57h+var_90], xmm0
0x14001a0e7  test    r8b, r8b
0x14001a0ea  jz      short loc_14001A10C
0x14001a0ec  cmp     cs:WdfStructureCount, 26h ; '&'
0x14001a0f3  jbe     short loc_14001A107
0x14001a0f5  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceQueue.___u4
0x14001a0fc  mov     ecx, [rax+130h]
0x14001a102  mov     dword ptr [rbp+57h+var_B0], ecx
0x14001a105  jmp     short loc_14001A113
0x14001a107  mov     dword ptr [rbp+57h+var_B0], edx
0x14001a10a  jmp     short loc_14001A113
0x14001a10c  mov     dword ptr [rbp+57h+var_B0], 38h ; '8'
0x14001a113  mov     rax, cs:off_1400130B0
0x14001a11a  lea     rcx, [rbp+57h+arg_0]
0x14001a11e  mov     rdx, [rsi]
0x14001a121  lea     r9, [rbp+57h+var_B0]
0x14001a125  mov     [rbp+57h+var_80], rax
0x14001a129  lea     r8, [rbp+57h+var_70]
0x14001a12d  lea     rax, ?EvtObjectContextCleanupThunk@?$ObjectContext@PEAUWDFQUEUE__@@VTransmitQueue@@$00@WdfCpp@@KAXPEAX@Z; WdfCpp::ObjectContext<WDFQUEUE__ *,TransmitQueue,1>::EvtObjectContextCleanupThunk(void *)
0x14001a134  mov     dword ptr [rbp+57h+var_A0+8], 1
0x14001a13b  mov     qword ptr [rbp+57h+var_B0+8], rax
0x14001a13f  mov     rax, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x14001a146  mov     dword ptr [rbp+57h+var_A0+0Ch], 1
0x14001a14d  mov     [rbp+57h+arg_0], 0
0x14001a155  mov     [rsp+100h+var_E0], rcx
0x14001a15a  mov     rax, [rax+4C0h]
0x14001a161  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x14001a168  call    _guard_dispatch_icall
0x14001a16d  mov     ebx, eax
0x14001a16f  test    eax, eax
0x14001a171  jns     short loc_14001A1D4
0x14001a173  mov     r10, cs:WPP_GLOBAL_Control
0x14001a17a  mov     ecx, [r10+2Ch]
0x14001a17e  test    cl, 1
0x14001a181  jz      short loc_14001A18E
0x14001a183  cmp     byte ptr [r10+29h], 2
0x14001a188  jb      short loc_14001A18E
0x14001a18a  mov     dl, 1
0x14001a18c  jmp     short loc_14001A190
0x14001a18e  xor     dl, dl
0x14001a190  mov     rcx, rsi; this
0x14001a193  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x14001a198  mov     r8, [rsi]
0x14001a19b  lea     rcx, WPP_fa6aac3b369b3a7320c30fd5f31db9d3_Traceguids
0x14001a1a2  mov     [rsp+100h+var_B8], ebx
0x14001a1a6  mov     r9, rax
0x14001a1a9  mov     [rsp+100h+var_C0], r8
0x14001a1ae  mov     [rsp+100h+var_C8], rcx
0x14001a1b3  mov     rcx, [r10+18h]
0x14001a1b7  mov     [rsp+100h+var_D0], 0Ah
0x14001a1be  mov     [rsp+100h+var_D8], 1
0x14001a1c6  mov     byte ptr [rsp+100h+var_E0], 2
0x14001a1cb  call    WPP_RECORDER_AND_TRACE_SF_qd
0x14001a1d0  mov     eax, ebx
0x14001a1d2  jmp     short loc_14001A23B
0x14001a1d4  mov     rcx, [rbp+57h+arg_0]
0x14001a1d8  call    ?EvtObjectContextCleanupThunk@?$ObjectContext@PEAUWDFQUEUE__@@VTransmitQueue@@$00@WdfCpp@@KAXPEAX@Z; WdfCpp::ObjectContext<WDFQUEUE__ *,TransmitQueue,1>::EvtObjectContextCleanupThunk(void *)
0x14001a1dd  mov     rbx, rax
0x14001a1e0  test    rax, rax
0x14001a1e3  jz      short loc_14001A20F
0x14001a1e5  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x14001a1ec  mov     rdx, rbx
0x14001a1ef  mov     rax, [rcx+660h]
0x14001a1f6  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x14001a1fd  call    _guard_dispatch_icall
0x14001a202  mov     [rbx], rax
0x14001a205  mov     [rbx+8], rsi
0x14001a209  mov     [rbx+10h], r14
0x14001a20d  jmp     short loc_14001A211
0x14001a20f  xor     ebx, ebx
0x14001a211  mov     rdx, [rdi]
0x14001a214  mov     [rdi], rbx
0x14001a217  test    rdx, rdx
0x14001a21a  jz      short loc_14001A239
0x14001a21c  mov     rax, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x14001a223  mov     rdx, [rdx]
0x14001a226  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x14001a22d  mov     rax, [rax+680h]
0x14001a234  call    _guard_dispatch_icall
0x14001a239  xor     eax, eax
0x14001a23b  lea     r11, [rsp+100h+var_10]
0x14001a243  mov     rbx, [r11+28h]
0x14001a247  mov     rsi, [r11+30h]
0x14001a24b  mov     rsp, r11
0x14001a24e  pop     r14
0x14001a250  pop     rdi
0x14001a251  pop     rbp
0x14001a252  retn
```
