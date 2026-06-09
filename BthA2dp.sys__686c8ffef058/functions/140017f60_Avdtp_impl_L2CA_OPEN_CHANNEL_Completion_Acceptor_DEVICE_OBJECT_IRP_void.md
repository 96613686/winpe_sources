# Avdtp_impl::L2CA_OPEN_CHANNEL_Completion_Acceptor(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140017f60`
- end: `0x1400183b0`
- name: `?L2CA_OPEN_CHANNEL_Completion_Acceptor@Avdtp_impl@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `1104`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000e690`
- `0x14000f570`
- `0x1400123a0`
- `0x140017f60`
- `0x14001c948`
- `0x140036494`
- `0x14003b244`
- `0x14004d790`
- `0x140055344`
- `0x140055a9c`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001820b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400182e8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001820b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400182e8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018031`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400182b8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018031`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400182b8`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::L2CA_OPEN_CHANNEL_Completion_Acceptor(
        struct _DEVICE_OBJECT *a1,
        struct _IRP *a2,
        char *a3)
{
  char *v3; // rbx
  PIO_SECURITY_CONTEXT SecurityContext; // rsi
  char v5; // di
  int v6; // r15d
  char v7; // r10
  char v8; // r12
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  KIRQL v12; // r13
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r8
  int IfrRecorderLog; // eax
  __int64 v17; // r10
  int v18; // edx
  int v19; // r8d
  int *v20; // r14
  int v21; // r14d
  int v22; // edx
  int v23; // r8d
  KIRQL v24; // al
  __int64 v25; // rsi
  KIRQL v26; // r14
  int v27; // edx
  int v28; // r8d

  v3 = a3;
  SecurityContext = 0;
  v5 = 1;
  if ( !a2
    || (SecurityContext = a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext) == 0
    || a2->IoStatus.Status
    || (v6 = 1, HIDWORD(SecurityContext[1].SecurityQos)) )
  {
    v6 = 0;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
    || (v7 = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
  {
    v7 = 0;
  }
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = v7;
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_ddDqbth_addr(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      (_DWORD)a3,
      WPP_GLOBAL_Control->DeviceExtension);
  }
  v8 = 0;
  v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v3 + 200);
  if ( v6 )
  {
    v13 = *((_QWORD *)v3 + 140);
    *((_QWORD *)v3 + 141) = v13;
    if ( *((_QWORD *)v3 + 143) )
    {
      *((_QWORD *)v3 + 179) = *(_QWORD *)&SecurityContext[4].DesiredAccess;
      *((_OWORD *)v3 + 90) = *(_OWORD *)&SecurityContext[15].DesiredAccess;
      *((_OWORD *)v3 + 91) = *(_OWORD *)&SecurityContext[16].AccessState;
      *((_OWORD *)v3 + 92) = *(_OWORD *)&SecurityContext[17].SecurityQos;
      *((_OWORD *)v3 + 93) = *(_OWORD *)&SecurityContext[17].DesiredAccess;
      *((_OWORD *)v3 + 94) = *(_OWORD *)&SecurityContext[18].AccessState;
      *((_OWORD *)v3 + 95) = *(_OWORD *)&SecurityContext[12].SecurityQos;
      *((_OWORD *)v3 + 96) = *(_OWORD *)&SecurityContext[12].DesiredAccess;
      *((_OWORD *)v3 + 97) = *(_OWORD *)&SecurityContext[13].AccessState;
      *((_OWORD *)v3 + 98) = *(_OWORD *)&SecurityContext[14].SecurityQos;
      *((_OWORD *)v3 + 99) = *(_OWORD *)&SecurityContext[14].DesiredAccess;
      if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(v13, v9, v10, v11) )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
          || (LOBYTE(v14) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
        {
          LOBYTE(v14) = 0;
        }
        if ( (_BYTE)v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          IfrRecorderLog = GetIfrRecorderLog(1, v14, v15);
          WPP_RECORDER_AND_TRACE_SF_bth_addrq(*(_QWORD *)(v17 + 24), v18, v19, IfrRecorderLog);
        }
      }
      Avdtp_impl::SetAvdtpState_NoLock(v3, 3);
    }
    else
    {
      v8 = 1;
    }
    v20 = (int *)(v3 + 144);
  }
  else
  {
    v20 = (int *)(v3 + 144);
    if ( *((_DWORD *)v3 + 36) == 2 )
    {
      *((_QWORD *)v3 + 179) = 0;
      *((_QWORD *)v3 + 141) = 0;
      Avdtp_impl::SetAvdtpState_NoLock(v3, 1);
    }
  }
  if ( !*((_DWORD *)v3 + 450) )
  {
    *((_QWORD *)v3 + 179) = 0;
    Avdtp_impl::SetAvdtpState_NoLock(v3, 1);
  }
  *((_DWORD *)v3 + 450) = 1;
  *((_DWORD *)v3 + 435) = 0;
  FreeRxPacketBuffer((void **)v3 + 218);
  v21 = *v20;
  *((_DWORD *)v3 + 438) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)v3 + 200, v12);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v5 = 0;
    }
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v22) = v5;
      LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v22,
        v23,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        4,
        216,
        (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids);
    }
    Avdtp_impl::L2capCloseAtShutdown((Avdtp_impl *)v3, *(void **)&SecurityContext[4].DesiredAccess);
    *((_QWORD *)v3 + 141) = 0;
  }
  else if ( v21 == 3 )
  {
    v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v3 + 200);
    v25 = *((_QWORD *)v3 + 143);
    v26 = v24;
    if ( v25 )
      (*((void (__fastcall **)(_QWORD))v3 + 146))(*((_QWORD *)v3 + 143));
    KeReleaseSpinLock((PKSPIN_LOCK)v3 + 200, v26);
    if ( v25 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v5 = 0;
      }
      if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v27) = v5;
        LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          v27,
          v28,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          4,
          217,
          (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
          v6);
      }
      (*((void (__fastcall **)(char *, __int64, _QWORD))v3 + 149))(v3, v25, *((_QWORD *)v3 + 141));
      (*((void (__fastcall **)(__int64))v3 + 147))(v25);
    }
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x140017f60  push    rbx
0x140017f62  push    rbp
0x140017f63  push    rsi
0x140017f64  push    rdi
0x140017f65  push    r12
0x140017f67  push    r13
0x140017f69  push    r14
0x140017f6b  push    r15
0x140017f6d  sub     rsp, 78h
0x140017f71  xor     r14d, r14d
0x140017f74  mov     rbx, r8
0x140017f77  mov     esi, r14d
0x140017f7a  lea     edi, [r14+1]
0x140017f7e  test    rdx, rdx
0x140017f81  jz      short loc_140017FA2
0x140017f83  mov     rax, [rdx+0B8h]
0x140017f8a  mov     rsi, [rax+8]
0x140017f8e  test    rsi, rsi
0x140017f91  jz      short loc_140017FA2
0x140017f93  cmp     [rdx+30h], r14d
0x140017f97  jnz     short loc_140017FA2
0x140017f99  mov     r15d, edi
0x140017f9c  cmp     [rsi+1Ch], r14d
0x140017fa0  jz      short loc_140017FA5
0x140017fa2  mov     r15d, r14d
0x140017fa5  mov     rcx, cs:WPP_GLOBAL_Control
0x140017fac  lea     rax, WPP_GLOBAL_Control
0x140017fb3  cmp     rcx, rax
0x140017fb6  jz      short loc_140017FC8
0x140017fb8  mov     eax, [rcx+2Ch]
0x140017fbb  test    al, 8
0x140017fbd  jz      short loc_140017FC8
0x140017fbf  cmp     byte ptr [rcx+29h], 4
0x140017fc3  mov     r10b, dil
0x140017fc6  jnb     short loc_140017FCB
0x140017fc8  mov     r10b, r14b
0x140017fcb  lea     rax, WPP_RECORDER_INITIALIZED
0x140017fd2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017fd9  setnz   r8b
0x140017fdd  test    r10b, r10b
0x140017fe0  jnz     short loc_140017FE7
0x140017fe2  test    r8b, r8b
0x140017fe5  jz      short loc_140018024
0x140017fe7  mov     rax, [rsi+80h]
0x140017fee  movzx   r9d, byte ptr [rsi+20h]
0x140017ff3  mov     [rsp+0B8h+var_58], rax
0x140017ff8  mov     rax, [rsi+70h]
0x140017ffc  mov     [rsp+0B8h+var_60], rax
0x140018001  mov     eax, [rsi+1Ch]
0x140018004  mov     [rsp+0B8h+var_68], r9d
0x140018009  mov     r9, [rcx+40h]
0x14001800d  mov     rcx, [rcx+18h]
0x140018011  mov     dword ptr [rsp+0B8h+var_70], eax
0x140018015  mov     eax, [rdx+30h]
0x140018018  mov     dl, r10b
0x14001801b  mov     dword ptr [rsp+0B8h+var_78], eax
0x14001801f  call    WPP_RECORDER_AND_TRACE_SF_ddDqbth_addr
0x140018024  lea     rbp, [rbx+640h]
0x14001802b  mov     r12b, r14b
0x14001802e  mov     rcx, rbp; SpinLock
0x140018031  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018038  nop     dword ptr [rax+rax+00h]
0x14001803d  mov     r13b, al
0x140018040  test    r15d, r15d
0x140018043  jz      loc_140018191
0x140018049  mov     rcx, [rbx+460h]
0x140018050  mov     [rbx+468h], rcx
0x140018057  cmp     [rbx+478h], r14
0x14001805e  jnz     short loc_140018068
0x140018060  mov     r12b, dil
0x140018063  jmp     loc_140018188
0x140018068  mov     rax, [rsi+70h]
0x14001806c  mov     [rbx+598h], rax
0x140018073  movups  xmm0, xmmword ptr [rsi+178h]
0x14001807a  movups  xmmword ptr [rbx+5A0h], xmm0
0x140018081  movups  xmm1, xmmword ptr [rsi+188h]
0x140018088  movups  xmmword ptr [rbx+5B0h], xmm1
0x14001808f  movups  xmm0, xmmword ptr [rsi+198h]
0x140018096  movups  xmmword ptr [rbx+5C0h], xmm0
0x14001809d  movups  xmm1, xmmword ptr [rsi+1A8h]
0x1400180a4  movups  xmmword ptr [rbx+5D0h], xmm1
0x1400180ab  movups  xmm0, xmmword ptr [rsi+1B8h]
0x1400180b2  movups  xmmword ptr [rbx+5E0h], xmm0
0x1400180b9  movups  xmm0, xmmword ptr [rsi+120h]
0x1400180c0  movups  xmmword ptr [rbx+5F0h], xmm0
0x1400180c7  movups  xmm1, xmmword ptr [rsi+130h]
0x1400180ce  movups  xmmword ptr [rbx+600h], xmm1
0x1400180d5  movups  xmm0, xmmword ptr [rsi+140h]
0x1400180dc  movups  xmmword ptr [rbx+610h], xmm0
0x1400180e3  movups  xmm1, xmmword ptr [rsi+150h]
0x1400180ea  movups  xmmword ptr [rbx+620h], xmm1
0x1400180f1  movups  xmm0, xmmword ptr [rsi+160h]
0x1400180f8  movups  xmmword ptr [rbx+630h], xmm0
0x1400180ff  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x140018104  test    eax, eax
0x140018106  jz      short loc_14001817B
0x140018108  mov     r10, cs:WPP_GLOBAL_Control
0x14001810f  lea     rax, WPP_GLOBAL_Control
0x140018116  cmp     r10, rax
0x140018119  jz      short loc_14001812D
0x14001811b  mov     eax, [r10+2Ch]
0x14001811f  test    al, 8
0x140018121  jz      short loc_14001812D
0x140018123  cmp     byte ptr [r10+29h], 4
0x140018128  mov     dl, dil
0x14001812b  jnb     short loc_140018130
0x14001812d  mov     dl, r14b
0x140018130  lea     rax, WPP_RECORDER_INITIALIZED
0x140018137  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001813e  setnz   r8b
0x140018142  test    dl, dl
0x140018144  jnz     short loc_14001814B
0x140018146  test    r8b, r8b
0x140018149  jz      short loc_14001817B
0x14001814b  mov     rcx, rdi
0x14001814e  call    ?GetIfrRecorderLog@@YAPEAURECORDER_LOG__@@W4IfrLogId@@@Z; GetIfrRecorderLog(IfrLogId)
0x140018153  mov     rcx, [r10+18h]
0x140018157  mov     r9, rax
0x14001815a  mov     rax, [rsi+70h]
0x14001815e  mov     [rsp+0B8h+var_70], rax
0x140018163  mov     rax, [rbx+468h]
0x14001816a  mov     [rsp+0B8h+var_78], rax
0x14001816f  mov     [rsp+0B8h+var_88], 0D7h
0x140018176  call    WPP_RECORDER_AND_TRACE_SF_bth_addrq
0x14001817b  mov     edx, 3
0x140018180  mov     rcx, rbx
0x140018183  call    ?SetAvdtpState_NoLock@Avdtp_impl@@AEAA?AW4TAG_AvdtpState@@W42@@Z; Avdtp_impl::SetAvdtpState_NoLock(TAG_AvdtpState)
0x140018188  lea     r14, [rbx+90h]
0x14001818f  jmp     short loc_1400181BE
0x140018191  lea     r14, [rbx+90h]
0x140018198  cmp     dword ptr [r14], 2
0x14001819c  jnz     short loc_1400181BE
0x14001819e  mov     edx, edi
0x1400181a0  mov     qword ptr [rbx+598h], 0
0x1400181ab  mov     rcx, rbx
0x1400181ae  mov     qword ptr [rbx+468h], 0
0x1400181b9  call    ?SetAvdtpState_NoLock@Avdtp_impl@@AEAA?AW4TAG_AvdtpState@@W42@@Z; Avdtp_impl::SetAvdtpState_NoLock(TAG_AvdtpState)
0x1400181be  cmp     dword ptr [rbx+708h], 0
0x1400181c5  jnz     short loc_1400181DC
0x1400181c7  mov     edx, edi
0x1400181c9  mov     qword ptr [rbx+598h], 0
0x1400181d4  mov     rcx, rbx
0x1400181d7  call    ?SetAvdtpState_NoLock@Avdtp_impl@@AEAA?AW4TAG_AvdtpState@@W42@@Z; Avdtp_impl::SetAvdtpState_NoLock(TAG_AvdtpState)
0x1400181dc  lea     rcx, [rbx+6D0h]; void **
0x1400181e3  mov     [rbx+708h], edi
0x1400181e9  mov     dword ptr [rbx+6CCh], 0
0x1400181f3  call    ?FreeRxPacketBuffer@@YAXAEAPEAX@Z; FreeRxPacketBuffer(void * &)
0x1400181f8  mov     r14d, [r14]
0x1400181fb  mov     dl, r13b; NewIrql
0x1400181fe  mov     rcx, rbp; SpinLock
0x140018201  mov     dword ptr [rbx+6D8h], 0
0x14001820b  call    cs:__imp_KeReleaseSpinLock
0x140018212  nop     dword ptr [rax+rax+00h]
0x140018217  test    r12b, r12b
0x14001821a  jz      loc_1400182AB
0x140018220  mov     rcx, cs:WPP_GLOBAL_Control
0x140018227  lea     rax, WPP_GLOBAL_Control
0x14001822e  cmp     rcx, rax
0x140018231  jz      short loc_140018240
0x140018233  mov     eax, [rcx+2Ch]
0x140018236  test    al, 8
0x140018238  jz      short loc_140018240
0x14001823a  cmp     byte ptr [rcx+29h], 4
0x14001823e  jnb     short loc_140018243
0x140018240  xor     dil, dil
0x140018243  lea     rax, WPP_RECORDER_INITIALIZED
0x14001824a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018251  setnz   r8b
0x140018255  test    dil, dil
0x140018258  jnz     short loc_14001825F
0x14001825a  test    r8b, r8b
0x14001825d  jz      short loc_14001828F
0x14001825f  mov     r9, [rcx+40h]
0x140018263  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14001826a  mov     rcx, [rcx+18h]
0x14001826e  mov     dl, dil
0x140018271  mov     [rsp+0B8h+var_80], rax
0x140018276  mov     [rsp+0B8h+var_88], 0D8h
0x14001827d  mov     [rsp+0B8h+var_90], 4
0x140018285  mov     [rsp+0B8h+var_98], 4
0x14001828a  call    WPP_RECORDER_AND_TRACE_SF_
0x14001828f  mov     rdx, [rsi+70h]; void *
0x140018293  mov     rcx, rbx; this
0x140018296  call    ?L2capCloseAtShutdown@Avdtp_impl@@AEAAXPEAX@Z; Avdtp_impl::L2capCloseAtShutdown(void *)
0x14001829b  mov     qword ptr [rbx+468h], 0
0x1400182a6  jmp     loc_140018399
0x1400182ab  cmp     r14d, 3
0x1400182af  jnz     loc_140018399
0x1400182b5  mov     rcx, rbp; SpinLock
0x1400182b8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400182bf  nop     dword ptr [rax+rax+00h]
0x1400182c4  mov     rsi, [rbx+478h]
0x1400182cb  mov     r14b, al
0x1400182ce  test    rsi, rsi
0x1400182d1  jz      short loc_1400182E2
0x1400182d3  mov     rax, [rbx+490h]
0x1400182da  mov     rcx, rsi
0x1400182dd  call    _guard_dispatch_icall
0x1400182e2  mov     dl, r14b; NewIrql
0x1400182e5  mov     rcx, rbp; SpinLock
0x1400182e8  call    cs:__imp_KeReleaseSpinLock
0x1400182ef  nop     dword ptr [rax+rax+00h]
0x1400182f4  test    rsi, rsi
0x1400182f7  jz      loc_140018399
0x1400182fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140018304  lea     rax, WPP_GLOBAL_Control
0x14001830b  cmp     rcx, rax
0x14001830e  jz      short loc_14001831D
0x140018310  mov     eax, [rcx+2Ch]
0x140018313  test    al, 8
0x140018315  jz      short loc_14001831D
0x140018317  cmp     byte ptr [rcx+29h], 4
0x14001831b  jnb     short loc_140018320
0x14001831d  xor     dil, dil
0x140018320  lea     rax, WPP_RECORDER_INITIALIZED
0x140018327  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001832e  setnz   r8b
0x140018332  test    dil, dil
0x140018335  jnz     short loc_14001833C
0x140018337  test    r8b, r8b
0x14001833a  jz      short loc_140018371
0x14001833c  mov     r9, [rcx+40h]
0x140018340  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x140018347  mov     rcx, [rcx+18h]
0x14001834b  mov     dl, dil
0x14001834e  mov     dword ptr [rsp+0B8h+var_78], r15d
0x140018353  mov     [rsp+0B8h+var_80], rax
0x140018358  mov     [rsp+0B8h+var_88], 0D9h
0x14001835f  mov     [rsp+0B8h+var_90], 4
0x140018367  mov     [rsp+0B8h+var_98], 4
0x14001836c  call    WPP_RECORDER_AND_TRACE_SF_d
0x140018371  mov     rax, [rbx+4A8h]
0x140018378  mov     rdx, rsi
0x14001837b  mov     r8, [rbx+468h]
0x140018382  mov     rcx, rbx
0x140018385  call    _guard_dispatch_icall
0x14001838a  mov     rax, [rbx+498h]
0x140018391  mov     rcx, rsi
0x140018394  call    _guard_dispatch_icall
0x140018399  mov     eax, 0C0000016h
0x14001839e  add     rsp, 78h
0x1400183a2  pop     r15
0x1400183a4  pop     r14
0x1400183a6  pop     r13
0x1400183a8  pop     r12
0x1400183aa  pop     rdi
0x1400183ab  pop     rsi
0x1400183ac  pop     rbp
0x1400183ad  pop     rbx
0x1400183ae  retn
```
