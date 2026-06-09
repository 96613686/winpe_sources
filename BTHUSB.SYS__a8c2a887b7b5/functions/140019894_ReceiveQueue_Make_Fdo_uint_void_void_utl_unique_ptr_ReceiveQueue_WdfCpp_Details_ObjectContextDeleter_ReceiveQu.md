# ReceiveQueue::Make(Fdo &,uint,void *,void *,utl::unique_ptr<ReceiveQueue,WdfCpp::Details::ObjectContextDeleter<ReceiveQueue>> &)

- ea: `0x140019894`
- end: `0x140019afa`
- name: `?Make@ReceiveQueue@@SAJAEAVFdo@@IPEAX1AEAV?$unique_ptr@VReceiveQueue@@U?$ObjectContextDeleter@VReceiveQueue@@@Details@WdfCpp@@@utl@@@Z`
- size: `614`
- prototype: `__int64 __usercall@<rax>(Fdo *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140018b90`

## callees

- `0x140001ca8`
- `0x140001da0`
- `0x140002564`
- `0x14000de00`
- `0x14000e1c0`
- `0x140019764`
- `0x140019894`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140019a5f`
- `ntoskrnl!KeInitializeSpinLock` at `0x140019a5f`

## pseudocode

```c
__int64 __fastcall ReceiveQueue::Make(Fdo *this, int a2, __int64 a3, __int64 a4, struct ReceiveQueue **a5)
{
  __int64 v9; // rdx
  int v10; // ebx
  unsigned int RecorderLog; // eax
  __int64 v12; // r10
  int v13; // edx
  struct ReceiveQueue *ContextFromObject; // rax
  struct ReceiveQueue *v16; // rbx
  int v17; // edi
  struct ReceiveQueue *v18; // rdx
  __int128 v19; // [rsp+50h] [rbp-81h] BYREF
  __int128 v20; // [rsp+60h] [rbp-71h]
  __int128 v21; // [rsp+70h] [rbp-61h]
  __int64 *v22; // [rsp+80h] [rbp-51h]
  _QWORD v23[18]; // [rsp+90h] [rbp-41h] BYREF
  struct WDFQUEUE__ *v24; // [rsp+130h] [rbp+5Fh] BYREF

  memset(v23, 0, 0x60u);
  if ( LOBYTE(WPP_MAIN_CB.DeviceQueue.Lock) )
  {
    if ( (unsigned int)WdfStructureCount <= 0x21 )
      LODWORD(v23[0]) = -1;
    else
      LODWORD(v23[0]) = *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.32 + 264LL);
  }
  else
  {
    LODWORD(v23[0]) = 96;
  }
  *(_QWORD *)((char *)v23 + 4) = 2;
  LODWORD(v23[10]) = -1;
  v23[2] = ReceiveQueue::EvtIoQueueIoDefaultThunk;
  v22 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  if ( LOBYTE(WPP_MAIN_CB.DeviceQueue.Lock) )
  {
    if ( (unsigned int)WdfStructureCount <= 0x26 )
      LODWORD(v19) = -1;
    else
      LODWORD(v19) = *(_DWORD *)(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.32 + 304LL);
  }
  else
  {
    LODWORD(v19) = 56;
  }
  v9 = *(_QWORD *)this;
  v22 = off_140013088;
  *((_QWORD *)&v20 + 1) = 0x100000001LL;
  *((_QWORD *)&v19 + 1) = WdfCpp::ObjectContext<WDFQUEUE__ *,ReceiveQueue,1>::EvtObjectContextCleanupThunk;
  v24 = 0;
  v10 = ((__int64 (__fastcall *)(_LIST_ENTRY *, __int64, _QWORD *, __int128 *, struct WDFQUEUE__ **))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[76].Flink)(
          WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
          v9,
          v23,
          &v19,
          &v24);
  if ( v10 >= 0 )
  {
    ContextFromObject = ReceiveQueue::GetContextFromObject(v24);
    v16 = ContextFromObject;
    if ( ContextFromObject )
    {
      *(_QWORD *)ContextFromObject = ((__int64 (__fastcall *)(_LIST_ENTRY *, struct ReceiveQueue *))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[102].Flink)(
                                       WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
                                       ContextFromObject);
      *((_QWORD *)v16 + 1) = this;
      *((_DWORD *)v16 + 4) = a2;
      *((_QWORD *)v16 + 3) = a3;
      *((_QWORD *)v16 + 4) = a4;
      KeInitializeSpinLock((PKSPIN_LOCK)v16 + 5);
      *((_QWORD *)v16 + 9) = 0;
      *((_QWORD *)v16 + 6) = -1;
      *((_QWORD *)v16 + 7) = -1;
      *((_QWORD *)v16 + 8) = -1;
    }
    else
    {
      v16 = 0;
    }
    v17 = ReceiveQueue::Initialize(v16);
    if ( v17 >= 0 )
    {
      v18 = *a5;
      *a5 = v16;
      if ( v18 )
        ((void (__fastcall *)(_LIST_ENTRY *, _QWORD))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[104].Flink)(
          WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
          *(_QWORD *)v18);
      return 0;
    }
    else
    {
      if ( v16 )
        ((void (__fastcall *)(_LIST_ENTRY *, _QWORD))WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink[104].Flink)(
          WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink,
          *(_QWORD *)v16);
      return (unsigned int)v17;
    }
  }
  else
  {
    RecorderLog = (unsigned int)Fdo::GetRecorderLog(this);
    WPP_RECORDER_AND_TRACE_SF_qd(
      *(_QWORD *)(v12 + 24),
      v13,
      *(_QWORD *)this,
      RecorderLog,
      2,
      1,
      10,
      (__int64)WPP_86e0affdec483798a987f478d619ae67_Traceguids,
      *(_QWORD *)this,
      v10);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x140019894  push    rbp
0x140019896  push    rbx
0x140019897  push    rsi
0x140019898  push    rdi
0x140019899  push    r14
0x14001989b  push    r15
0x14001989d  lea     rbp, [rsp-27h]
0x1400198a2  sub     rsp, 0F8h
0x1400198a9  mov     r14, r8
0x1400198ac  mov     r15d, edx
0x1400198af  mov     rdi, rcx
0x1400198b2  mov     ebx, 60h ; '`'
0x1400198b7  mov     r8d, ebx; Size
0x1400198ba  lea     rcx, [rbp+4Fh+var_90]; void *
0x1400198be  xor     edx, edx; Val
0x1400198c0  mov     rsi, r9
0x1400198c3  call    memset
0x1400198c8  mov     r10b, byte ptr cs:WPP_MAIN_CB.DeviceQueue.Lock
0x1400198cf  or      edx, 0FFFFFFFFh
0x1400198d2  test    r10b, r10b
0x1400198d5  jz      short loc_1400198F7
0x1400198d7  cmp     cs:WdfStructureCount, 21h ; '!'
0x1400198de  jbe     short loc_1400198F2
0x1400198e0  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceQueue.___u4
0x1400198e7  mov     ecx, [rax+108h]
0x1400198ed  mov     [rbp+4Fh+var_90], ecx
0x1400198f0  jmp     short loc_1400198FA
0x1400198f2  mov     [rbp+4Fh+var_90], edx
0x1400198f5  jmp     short loc_1400198FA
0x1400198f7  mov     [rbp+4Fh+var_90], ebx
0x1400198fa  xorps   xmm0, xmm0
0x1400198fd  mov     [rbp+4Fh+var_8C], 2
0x140019905  lea     rax, ?EvtIoQueueIoDefaultThunk@ReceiveQueue@@CAXPEAUWDFQUEUE__@@PEAUWDFREQUEST__@@@Z; ReceiveQueue::EvtIoQueueIoDefaultThunk(WDFQUEUE__ *,WDFREQUEST__ *)
0x14001990c  mov     [rbp+4Fh+var_40], edx
0x14001990f  mov     [rbp+4Fh+var_80], rax
0x140019913  xor     eax, eax
0x140019915  mov     [rbp+4Fh+var_A0], rax
0x140019919  movups  [rsp+120h+var_D0], xmm0
0x14001991e  movups  [rbp+4Fh+var_C0], xmm0
0x140019922  movups  [rbp+4Fh+var_B0], xmm0
0x140019926  test    r10b, r10b
0x140019929  jz      short loc_14001994D
0x14001992b  cmp     cs:WdfStructureCount, 26h ; '&'
0x140019932  jbe     short loc_140019947
0x140019934  mov     rax, qword ptr cs:WPP_MAIN_CB.DeviceQueue.___u4
0x14001993b  mov     ecx, [rax+130h]
0x140019941  mov     dword ptr [rsp+120h+var_D0], ecx
0x140019945  jmp     short loc_140019955
0x140019947  mov     dword ptr [rsp+120h+var_D0], edx
0x14001994b  jmp     short loc_140019955
0x14001994d  mov     dword ptr [rsp+120h+var_D0], 38h ; '8'
0x140019955  mov     rax, cs:off_140013088
0x14001995c  lea     rcx, [rbp+4Fh+arg_0]
0x140019960  mov     rdx, [rdi]
0x140019963  lea     r9, [rsp+120h+var_D0]
0x140019968  mov     [rbp+4Fh+var_A0], rax
0x14001996c  lea     r8, [rbp+4Fh+var_90]
0x140019970  lea     rax, ?EvtObjectContextCleanupThunk@?$ObjectContext@PEAUWDFQUEUE__@@VReceiveQueue@@$00@WdfCpp@@KAXPEAX@Z; WdfCpp::ObjectContext<WDFQUEUE__ *,ReceiveQueue,1>::EvtObjectContextCleanupThunk(void *)
0x140019977  mov     dword ptr [rbp+4Fh+var_C0+8], 1
0x14001997e  mov     qword ptr [rbp+4Fh+var_D0+8], rax
0x140019982  mov     rax, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x140019989  mov     dword ptr [rbp+4Fh+var_C0+0Ch], 1
0x140019990  mov     [rbp+4Fh+arg_0], 0
0x140019998  mov     [rsp+120h+var_100], rcx
0x14001999d  mov     rax, [rax+4C0h]
0x1400199a4  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x1400199ab  call    _guard_dispatch_icall
0x1400199b0  mov     ebx, eax
0x1400199b2  test    eax, eax
0x1400199b4  jns     short loc_140019A1A
0x1400199b6  mov     r10, cs:WPP_GLOBAL_Control
0x1400199bd  mov     ecx, [r10+2Ch]
0x1400199c1  test    cl, 1
0x1400199c4  jz      short loc_1400199D1
0x1400199c6  cmp     byte ptr [r10+29h], 2
0x1400199cb  jb      short loc_1400199D1
0x1400199cd  mov     dl, 1
0x1400199cf  jmp     short loc_1400199D3
0x1400199d1  xor     dl, dl
0x1400199d3  mov     rcx, rdi; this
0x1400199d6  call    ?GetRecorderLog@Fdo@@QEBAPEAURECORDER_LOG__@@XZ; Fdo::GetRecorderLog(void)
0x1400199db  mov     r8, [rdi]
0x1400199de  lea     rcx, WPP_86e0affdec483798a987f478d619ae67_Traceguids
0x1400199e5  mov     [rsp+120h+var_D8], ebx
0x1400199e9  mov     r9, rax
0x1400199ec  mov     [rsp+120h+var_E0], r8
0x1400199f1  mov     [rsp+120h+var_E8], rcx
0x1400199f6  mov     rcx, [r10+18h]
0x1400199fa  mov     [rsp+120h+var_F0], 0Ah
0x140019a01  mov     [rsp+120h+var_F8], 1
0x140019a09  mov     byte ptr [rsp+120h+var_100], 2
0x140019a0e  call    WPP_RECORDER_AND_TRACE_SF_qd
0x140019a13  mov     eax, ebx
0x140019a15  jmp     loc_140019AE9
0x140019a1a  mov     rcx, [rbp+4Fh+arg_0]; struct WDFQUEUE__ *
0x140019a1e  call    ?GetContextFromObject@ReceiveQueue@@CAPEAV1@PEAUWDFQUEUE__@@@Z; ReceiveQueue::GetContextFromObject(WDFQUEUE__ *)
0x140019a23  mov     rbx, rax
0x140019a26  test    rax, rax
0x140019a29  jz      short loc_140019A85
0x140019a2b  mov     rax, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x140019a32  mov     rdx, rbx
0x140019a35  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x140019a3c  mov     rax, [rax+660h]
0x140019a43  call    _guard_dispatch_icall
0x140019a48  lea     rcx, [rbx+28h]; SpinLock
0x140019a4c  mov     [rbx], rax
0x140019a4f  mov     [rbx+8], rdi
0x140019a53  mov     [rbx+10h], r15d
0x140019a57  mov     [rbx+18h], r14
0x140019a5b  mov     [rbx+20h], rsi
0x140019a5f  call    cs:__imp_KeInitializeSpinLock
0x140019a66  nop     dword ptr [rax+rax+00h]
0x140019a6b  or      rax, 0FFFFFFFFFFFFFFFFh
0x140019a6f  mov     qword ptr [rbx+48h], 0
0x140019a77  mov     [rbx+30h], rax
0x140019a7b  mov     [rbx+38h], rax
0x140019a7f  mov     [rbx+40h], rax
0x140019a83  jmp     short loc_140019A87
0x140019a85  xor     ebx, ebx
0x140019a87  mov     rcx, rbx; this
0x140019a8a  call    ?Initialize@ReceiveQueue@@AEAAJXZ; ReceiveQueue::Initialize(void)
0x140019a8f  mov     edi, eax
0x140019a91  test    eax, eax
0x140019a93  jns     short loc_140019ABB
0x140019a95  test    rbx, rbx
0x140019a98  jz      short loc_140019AB7
0x140019a9a  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x140019aa1  mov     rdx, [rbx]
0x140019aa4  mov     rax, [rcx+680h]
0x140019aab  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x140019ab2  call    _guard_dispatch_icall
0x140019ab7  mov     eax, edi
0x140019ab9  jmp     short loc_140019AE9
0x140019abb  mov     rax, [rbp+4Fh+arg_20]
0x140019abf  mov     rdx, [rax]
0x140019ac2  mov     [rax], rbx
0x140019ac5  test    rdx, rdx
0x140019ac8  jz      short loc_140019AE7
0x140019aca  mov     rax, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Flink
0x140019ad1  mov     rdx, [rdx]
0x140019ad4  mov     rcx, cs:WPP_MAIN_CB.DeviceQueue.DeviceListHead.Blink
0x140019adb  mov     rax, [rax+680h]
0x140019ae2  call    _guard_dispatch_icall
0x140019ae7  xor     eax, eax
0x140019ae9  add     rsp, 0F8h
0x140019af0  pop     r15
0x140019af2  pop     r14
0x140019af4  pop     rdi
0x140019af5  pop     rsi
0x140019af6  pop     rbx
0x140019af7  pop     rbp
0x140019af8  retn
```
