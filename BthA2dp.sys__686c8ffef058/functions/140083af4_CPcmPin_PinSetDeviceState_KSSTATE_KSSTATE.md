# CPcmPin::PinSetDeviceState(KSSTATE,KSSTATE)

- ea: `0x140083af4`
- end: `0x14008407b`
- name: `?PinSetDeviceState@CPcmPin@@QEAAJW4KSSTATE@@0@Z`
- size: `1415`
- prototype: `__int64 __fastcall(CPcmPin *__hidden this, enum KSSTATE, enum KSSTATE)`
- caller_count: `2`
- callee_count: `28`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140083430`
- `0x1400839e0`

## callees

- `0x14000110c`
- `0x140005800`
- `0x140005a50`
- `0x140006410`
- `0x14000f570`
- `0x140010d10`
- `0x140012c7c`
- `0x140014258`
- `0x140014d0c`
- `0x14001bed0`
- `0x14001e624`
- `0x14001efb0`
- `0x14001f56c`
- `0x140020948`
- `0x14002bc28`
- `0x14002bdbc`
- `0x140032f78`
- `0x140033268`
- `0x140033440`
- `0x140033530`
- `0x14003b004`
- `0x14003b160`
- `0x14003b1a0`
- `0x14003b210`
- `0x14003b3dc`
- `0x14005903c`
- `0x14005c7d0`
- `0x140083af4`

## import_xrefs

- `ntoskrnl!ExCancelTimer` at `0x140083d3c`
- `ntoskrnl!ExCancelTimer` at `0x140083d3c`
- `ntoskrnl!EtwActivityIdControl` at `0x140083f2a`
- `ntoskrnl!EtwActivityIdControl` at `0x140083f2a`
- `ks!KsPinAttemptProcessing` at `0x140083ccc`
- `ks!KsPinAttemptProcessing` at `0x140083ccc`

## pseudocode

```c
__int64 __fastcall CPcmPin::PinSetDeviceState(CPcmPin *this, unsigned int a2, __int64 a3)
{
  unsigned int v3; // r15d
  enum KSSTATE v4; // r14d
  unsigned int v6; // edi
  __int32 v7; // esi
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // r12d
  int v11; // r13d
  int v12; // edx
  int v13; // r8d
  int v14; // edx
  A2DP_Device *v15; // rcx
  A2DP_Device *v16; // rcx
  int v17; // edx
  int v18; // r8d
  A2DP_Device *v19; // rdx
  int v20; // edx
  int v21; // r8d
  A2DP_Device *v22; // rcx
  __int64 v23; // rax
  struct _KSPIN *v24; // rdx
  unsigned __int64 v25; // rsi
  __int64 v26; // rcx
  __int64 v27; // r8
  int v29; // [rsp+20h] [rbp-E0h]
  char v30; // [rsp+60h] [rbp-A0h] BYREF
  char v31; // [rsp+61h] [rbp-9Fh] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h] BYREF
  utl::_RefCountBase *v33[2]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 Address; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v35; // [rsp+88h] [rbp-78h] BYREF
  GUID ActivityId; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v37; // [rsp+A0h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v38; // [rsp+B0h] [rbp-50h] BYREF
  utl::_RefCountBase **v39; // [rsp+D0h] [rbp-30h]
  __int64 v40; // [rsp+D8h] [rbp-28h]
  char *v41; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  char *v43; // [rsp+F0h] [rbp-10h]
  __int64 v44; // [rsp+F8h] [rbp-8h]
  __int64 *v45; // [rsp+100h] [rbp+0h]
  __int64 v46; // [rsp+108h] [rbp+8h]
  unsigned __int64 *v47; // [rsp+110h] [rbp+10h]
  __int64 v48; // [rsp+118h] [rbp+18h]
  unsigned __int64 *p_Address; // [rsp+120h] [rbp+20h]
  __int64 v50; // [rsp+128h] [rbp+28h]

  v3 = a3;
  v4 = a2;
  if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 1) != 0 )
    McTemplateK0qq_EtwWriteTransfer(this, PinSetDeviceStateStart, a3, a2, a3);
  v6 = 0;
  v32 = MEMORY[0xFFFFF78000000008];
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_qKSSTATEKSSTATE(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      a3,
      WPP_GLOBAL_Control->DeviceExtension,
      v29);
  }
  v7 = _InterlockedExchange((volatile __int32 *)this, v4);
  if ( v7 != v4 )
  {
    CPcmPin::UpdateMpmPlayStatus(this, v4);
    v10 = 0;
    v11 = 0;
    if ( v4 == KSSTATE_STOP )
    {
      CPcmPin::DepleteKlonez(this);
      *((_QWORD *)this + 7) = 0;
      *((_QWORD *)this + 8) = 0;
      *((_QWORD *)this + 9) = 0;
      *((_QWORD *)this + 5) = 0;
      CPcmPin::ResetCorrelatedPosition(this);
      v22 = (A2DP_Device *)*((_QWORD *)this + 4);
      *((_QWORD *)this + 18) = 0;
      *((_QWORD *)this + 15) = 0;
      A2DP_Device::ResetOutputCodec(v22);
      goto LABEL_61;
    }
    if ( v4 != KSSTATE_ACQUIRE )
    {
      if ( v4 == KSSTATE_PAUSE )
      {
        if ( v3 == 3 )
        {
          if ( !*((_BYTE *)this + 188) && *((_QWORD *)this + 4) )
          {
            CPcmPin::WaitForQueuesToDrain(this, 1);
            v16 = (A2DP_Device *)*((_QWORD *)this + 4);
            *(_OWORD *)v33 = 0;
            A2DP_Device::SetPinStateNotRunning(v16);
          }
          if ( (unsigned __int8)ExCancelTimer(*((_QWORD *)this + 32), 0) )
            CPcmPin::UnlockTimerDpc(this);
          CPcmPin::WaitTimerDpcGone(this);
        }
        goto LABEL_61;
      }
      if ( v4 != KSSTATE_RUN )
      {
LABEL_61:
        v23 = *((_QWORD *)this + 4);
        if ( v23 )
        {
          if ( v10 )
            v24 = (struct _KSPIN *)*((_QWORD *)this + 2);
          else
            v24 = 0;
          A2dpRole::AttachRelatedPin(*(A2dpRole **)(v23 + 8), v24);
        }
        if ( v11 )
          CPcmPin::SetTimer(this, 0);
        goto LABEL_68;
      }
      if ( A2dpRole::IsCodecConfigured(*(A2dpRole **)(*((_QWORD *)this + 4) + 8LL)) )
      {
        v15 = (A2DP_Device *)*((_QWORD *)this + 4);
        *(_OWORD *)v33 = 0;
        A2DP_Device::SetPinStateRunning(v15);
        CPcmPin::SetCorrelatedPositionUsingCurrentTimeAndBytesCompleted(this);
        if ( *((_BYTE *)this + 216) )
          *((_BYTE *)this + 216) = 0;
        KsPinAttemptProcessing(*((PKSPIN *)this + 2), 0);
        v11 = 1;
        v10 = 1;
        goto LABEL_61;
      }
      LOBYTE(v12) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
      if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v12,
          v13,
          WPP_GLOBAL_Control->DeviceExtension,
          3,
          5,
          35,
          (__int64)WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids);
      }
      v14 = 3;
LABEL_50:
      _InterlockedExchange((volatile __int32 *)this, v7);
      CPcmPin::UpdateMpmPlayStatus(this, v14);
      v6 = -1073741667;
      goto LABEL_61;
    }
    if ( !v3 )
    {
      if ( (unsigned int)A2DP_Device::GetAvdtpConnectionStatus(*((_QWORD *)this + 4), v8, v9) )
      {
        LOBYTE(v17) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
        if ( (_BYTE)v17 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v17,
            v18,
            WPP_GLOBAL_Control->DeviceExtension,
            3,
            5,
            34,
            (__int64)WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids);
        }
        goto LABEL_49;
      }
      A2DP_Device::ResetOutputCodec(*((A2DP_Device **)this + 4));
      if ( !A2dpRole::GetOpenStatus(*(A2dpRole **)(*((_QWORD *)this + 4) + 8LL)) )
        A2DP_Device::RequestStreamOpen(v19);
      if ( !A2dpRole::GetOpenStatus(*(A2dpRole **)(*((_QWORD *)this + 4) + 8LL)) )
      {
        LOBYTE(v20) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
        if ( (_BYTE)v20 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v21) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v20,
            v21,
            WPP_GLOBAL_Control->DeviceExtension,
            3,
            5,
            33,
            (__int64)WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids);
        }
LABEL_49:
        v14 = 1;
        goto LABEL_50;
      }
    }
    v10 = 1;
    goto LABEL_61;
  }
LABEL_68:
  v25 = MEMORY[0xFFFFF78000000008] - v32;
  CPcmPin::GetAudioTraceSessionId(this, &v37);
  ActivityId = 0;
  EtwActivityIdControl(1u, &ActivityId);
  if ( (unsigned int)dword_14006F0F8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14006F0F8, 0x400000000000LL, v27) )
  {
    Address = A2DP_Device::GetAddress(*((A2DP_Device **)this + 4));
    LODWORD(v32) = v6;
    v30 = v4;
    p_Address = &Address;
    v47 = &v35;
    v35 = v25 / 0x2710;
    v45 = &v32;
    v50 = 8;
    v43 = &v30;
    v41 = &v31;
    v39 = v33;
    v48 = 8;
    v40 = 8;
    v31 = v3;
    v33[0] = (utl::_RefCountBase *)50331648;
    v46 = 4;
    v44 = 1;
    v42 = 1;
    tlgWriteTransfer_EtwWriteTransfer(
      (__int64)&dword_14006F0F8,
      (unsigned __int8 *)byte_140069F9F,
      &v37,
      &ActivityId,
      8u,
      &v38);
  }
  if ( v25 >= 0x11E1A300 )
    MicrosoftTelemetryAssertTriggeredArgsMsgKM(
      v26,
      v3,
      (unsigned int)v4,
      "Device state transition took longer than expected");
  if ( (Microsoft_Windows_BTH_AudioClassDriverEnableBits & 1) != 0 )
    McTemplateK0_EtwWriteTransfer(v26, PinSetDeviceStateStop);
  return v6;
}

```

## disassembly

```asm
0x140083af4  mov     [rsp-8+arg_18], rbx
0x140083af9  push    rbp
0x140083afa  push    rsi
0x140083afb  push    rdi
0x140083afc  push    r12
0x140083afe  push    r13
0x140083b00  push    r14
0x140083b02  push    r15
0x140083b04  lea     rbp, [rsp-40h]
0x140083b09  sub     rsp, 140h
0x140083b10  mov     rax, cs:__security_cookie
0x140083b17  xor     rax, rsp
0x140083b1a  mov     [rbp+70h+var_40], rax
0x140083b1e  test    cs:Microsoft_Windows_BTH_AudioClassDriverEnableBits, 1
0x140083b25  mov     r15d, r8d
0x140083b28  mov     r14d, edx
0x140083b2b  mov     rbx, rcx
0x140083b2e  jz      short loc_140083B44
0x140083b30  mov     r9d, edx
0x140083b33  mov     [rsp+170h+var_150], r8d
0x140083b38  lea     rdx, _PinSetDeviceStateStart
0x140083b3f  call    McTemplateK0qq_EtwWriteTransfer
0x140083b44  mov     rax, 0FFFFF78000000008h
0x140083b4e  xor     edi, edi
0x140083b50  mov     rax, [rax]
0x140083b53  mov     [rsp+170h+var_108], rax
0x140083b58  mov     rcx, cs:WPP_GLOBAL_Control
0x140083b5f  lea     rax, WPP_GLOBAL_Control
0x140083b66  cmp     rcx, rax
0x140083b69  jz      short loc_140083B7C
0x140083b6b  mov     eax, [rcx+2Ch]
0x140083b6e  test    al, 10h
0x140083b70  jz      short loc_140083B7C
0x140083b72  cmp     byte ptr [rcx+29h], 4
0x140083b76  jb      short loc_140083B7C
0x140083b78  mov     dl, 1
0x140083b7a  jmp     short loc_140083B7E
0x140083b7c  xor     dl, dl
0x140083b7e  lea     rax, WPP_RECORDER_INITIALIZED
0x140083b85  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140083b8c  setnz   r8b
0x140083b90  test    dl, dl
0x140083b92  jnz     short loc_140083B99
0x140083b94  test    r8b, r8b
0x140083b97  jz      short loc_140083BB9
0x140083b99  mov     rax, [rbx+10h]
0x140083b9d  mov     r9, [rcx+40h]
0x140083ba1  mov     rcx, [rcx+18h]
0x140083ba5  mov     [rsp+170h+var_120], r14d
0x140083baa  mov     [rsp+170h+var_128], r15d
0x140083baf  mov     [rsp+170h+var_130], rax
0x140083bb4  call    WPP_RECORDER_AND_TRACE_SF_qKSSTATEKSSTATE
0x140083bb9  mov     esi, r14d
0x140083bbc  xchg    esi, [rbx]
0x140083bbe  cmp     esi, r14d
0x140083bc1  jz      loc_140083EFC
0x140083bc7  mov     edx, r14d; int
0x140083bca  mov     rcx, rbx; this
0x140083bcd  call    ?UpdateMpmPlayStatus@CPcmPin@@AEAAXJ@Z; CPcmPin::UpdateMpmPlayStatus(long)
0x140083bd2  xor     r12d, r12d
0x140083bd5  xor     r13d, r13d
0x140083bd8  mov     ecx, r14d
0x140083bdb  test    r14d, r14d
0x140083bde  jz      loc_140083E9A
0x140083be4  sub     ecx, 1
0x140083be7  jz      loc_140083D61
0x140083bed  sub     ecx, 1
0x140083bf0  jz      loc_140083CE8
0x140083bf6  cmp     ecx, 1
0x140083bf9  jnz     loc_140083ECE
0x140083bff  mov     rcx, [rbx+20h]
0x140083c03  mov     rcx, [rcx+8]; this
0x140083c07  call    ?IsCodecConfigured@A2dpRole@@QEAA_NXZ; A2dpRole::IsCodecConfigured(void)
0x140083c0c  test    al, al
0x140083c0e  jnz     short loc_140083C88
0x140083c10  mov     rcx, cs:WPP_GLOBAL_Control
0x140083c17  lea     rax, WPP_GLOBAL_Control
0x140083c1e  cmp     rcx, rax
0x140083c21  jz      short loc_140083C34
0x140083c23  mov     eax, [rcx+2Ch]
0x140083c26  test    al, 10h
0x140083c28  jz      short loc_140083C34
0x140083c2a  cmp     byte ptr [rcx+29h], 3
0x140083c2e  jb      short loc_140083C34
0x140083c30  mov     dl, 1
0x140083c32  jmp     short loc_140083C36
0x140083c34  xor     dl, dl
0x140083c36  lea     rax, WPP_RECORDER_INITIALIZED
0x140083c3d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140083c44  setnz   r8b
0x140083c48  test    dl, dl
0x140083c4a  jnz     short loc_140083C51
0x140083c4c  test    r8b, r8b
0x140083c4f  jz      short loc_140083C7E
0x140083c51  mov     r9, [rcx+40h]
0x140083c55  lea     rax, WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids
0x140083c5c  mov     rcx, [rcx+18h]
0x140083c60  mov     [rsp+170h+var_138], rax
0x140083c65  mov     [rsp+170h+var_140], 23h ; '#'
0x140083c6c  mov     dword ptr [rsp+170h+var_148], 5
0x140083c74  mov     byte ptr [rsp+170h+var_150], 3
0x140083c79  call    WPP_RECORDER_AND_TRACE_SF_
0x140083c7e  mov     edx, 3
0x140083c83  jmp     loc_140083E25
0x140083c88  mov     rcx, [rbx+20h]; this
0x140083c8c  lea     rdx, [rsp+170h+var_100]
0x140083c91  xorps   xmm0, xmm0
0x140083c94  movdqu  xmmword ptr [rsp+170h+var_100], xmm0
0x140083c9a  call    ?SetPinStateRunning@A2DP_Device@@QEAAXAEBV?$shared_ptr@V?$kernel_event_t@$00@details@wil@@@utl@@@Z; A2DP_Device::SetPinStateRunning(utl::shared_ptr<wil::details::kernel_event_t<1>> const &)
0x140083c9f  mov     rcx, [rsp+170h+var_100+8]; this
0x140083ca4  test    rcx, rcx
0x140083ca7  jz      short loc_140083CAE
0x140083ca9  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140083cae  mov     rcx, rbx; this
0x140083cb1  call    ?SetCorrelatedPositionUsingCurrentTimeAndBytesCompleted@CPcmPin@@AEAAXXZ; CPcmPin::SetCorrelatedPositionUsingCurrentTimeAndBytesCompleted(void)
0x140083cb6  cmp     [rbx+0D8h], dil
0x140083cbd  jz      short loc_140083CC6
0x140083cbf  mov     [rbx+0D8h], dil
0x140083cc6  mov     rcx, [rbx+10h]; Pin
0x140083cca  xor     edx, edx; Asynchronous
0x140083ccc  call    cs:__imp_KsPinAttemptProcessing
0x140083cd3  nop     dword ptr [rax+rax+00h]
0x140083cd8  mov     eax, 1
0x140083cdd  mov     r13d, eax
0x140083ce0  mov     r12d, eax
0x140083ce3  jmp     loc_140083ECE
0x140083ce8  cmp     r15d, 3
0x140083cec  jnz     loc_140083ECE
0x140083cf2  cmp     [rbx+0BCh], dil
0x140083cf9  jnz     short loc_140083D33
0x140083cfb  cmp     [rbx+20h], rdi
0x140083cff  jz      short loc_140083D33
0x140083d01  lea     edx, [r15-2]
0x140083d05  mov     rcx, rbx
0x140083d08  call    ?WaitForQueuesToDrain@CPcmPin@@QEAAXW4QueueDrainOptions@1@@Z; CPcmPin::WaitForQueuesToDrain(CPcmPin::QueueDrainOptions)
0x140083d0d  mov     rcx, [rbx+20h]; this
0x140083d11  lea     rdx, [rsp+170h+var_100]
0x140083d16  xorps   xmm0, xmm0
0x140083d19  movdqu  xmmword ptr [rsp+170h+var_100], xmm0
0x140083d1f  call    ?SetPinStateNotRunning@A2DP_Device@@QEAAXAEBV?$shared_ptr@V?$kernel_event_t@$00@details@wil@@@utl@@@Z; A2DP_Device::SetPinStateNotRunning(utl::shared_ptr<wil::details::kernel_event_t<1>> const &)
0x140083d24  mov     rcx, [rsp+170h+var_100+8]; this
0x140083d29  test    rcx, rcx
0x140083d2c  jz      short loc_140083D33
0x140083d2e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140083d33  mov     rcx, [rbx+100h]
0x140083d3a  xor     edx, edx
0x140083d3c  call    cs:__imp_ExCancelTimer
0x140083d43  nop     dword ptr [rax+rax+00h]
0x140083d48  test    al, al
0x140083d4a  jz      short loc_140083D54
0x140083d4c  mov     rcx, rbx; this
0x140083d4f  call    ?UnlockTimerDpc@CPcmPin@@AEAAJXZ; CPcmPin::UnlockTimerDpc(void)
0x140083d54  mov     rcx, rbx; this
0x140083d57  call    ?WaitTimerDpcGone@CPcmPin@@AEAAXXZ; CPcmPin::WaitTimerDpcGone(void)
0x140083d5c  jmp     loc_140083ECE
0x140083d61  test    r15d, r15d
0x140083d64  jnz     loc_140083E92
0x140083d6a  mov     rcx, [rbx+20h]
0x140083d6e  call    ?GetAvdtpConnectionStatus@A2DP_Device@@QEBA?AW4ConnectionStatus@@XZ; A2DP_Device::GetAvdtpConnectionStatus(void)
0x140083d73  test    eax, eax
0x140083d75  jnz     loc_140083E39
0x140083d7b  mov     rcx, [rbx+20h]; this
0x140083d7f  call    ?ResetOutputCodec@A2DP_Device@@QEAAXXZ; A2DP_Device::ResetOutputCodec(void)
0x140083d84  mov     rdx, [rbx+20h]
0x140083d88  mov     rcx, [rdx+8]; this
0x140083d8c  call    ?GetOpenStatus@A2dpRole@@QEBA_NXZ; A2dpRole::GetOpenStatus(void)
0x140083d91  cmp     al, 1
0x140083d93  jz      short loc_140083D9D
0x140083d95  mov     rcx, rdx; this
0x140083d98  call    ?RequestStreamOpen@A2DP_Device@@QEAAXXZ; A2DP_Device::RequestStreamOpen(void)
0x140083d9d  mov     rcx, [rbx+20h]
0x140083da1  mov     rcx, [rcx+8]; this
0x140083da5  call    ?GetOpenStatus@A2dpRole@@QEBA_NXZ; A2dpRole::GetOpenStatus(void)
0x140083daa  cmp     al, 1
0x140083dac  jz      loc_140083E92
0x140083db2  mov     rcx, cs:WPP_GLOBAL_Control
0x140083db9  lea     rax, WPP_GLOBAL_Control
0x140083dc0  cmp     rcx, rax
0x140083dc3  jz      short loc_140083DD6
0x140083dc5  mov     eax, [rcx+2Ch]
0x140083dc8  test    al, 10h
0x140083dca  jz      short loc_140083DD6
0x140083dcc  cmp     byte ptr [rcx+29h], 3
0x140083dd0  jb      short loc_140083DD6
0x140083dd2  mov     dl, 1
0x140083dd4  jmp     short loc_140083DD8
0x140083dd6  xor     dl, dl
0x140083dd8  lea     rax, WPP_RECORDER_INITIALIZED
0x140083ddf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140083de6  setnz   r8b
0x140083dea  test    dl, dl
0x140083dec  jnz     short loc_140083DF3
0x140083dee  test    r8b, r8b
0x140083df1  jz      short loc_140083E20
0x140083df3  lea     rax, WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids
0x140083dfa  mov     [rsp+170h+var_138], rax
0x140083dff  mov     [rsp+170h+var_140], 21h ; '!'
0x140083e06  mov     r9, [rcx+40h]
0x140083e0a  mov     rcx, [rcx+18h]
0x140083e0e  mov     dword ptr [rsp+170h+var_148], 5
0x140083e16  mov     byte ptr [rsp+170h+var_150], 3
0x140083e1b  call    WPP_RECORDER_AND_TRACE_SF_
0x140083e20  mov     edx, 1; int
0x140083e25  xchg    esi, [rbx]
0x140083e27  mov     rcx, rbx; this
0x140083e2a  call    ?UpdateMpmPlayStatus@CPcmPin@@AEAAXJ@Z; CPcmPin::UpdateMpmPlayStatus(long)
0x140083e2f  mov     edi, 0C000009Dh
0x140083e34  jmp     loc_140083ECE
0x140083e39  mov     rcx, cs:WPP_GLOBAL_Control
0x140083e40  lea     rax, WPP_GLOBAL_Control
0x140083e47  cmp     rcx, rax
0x140083e4a  jz      short loc_140083E5D
0x140083e4c  mov     eax, [rcx+2Ch]
0x140083e4f  test    al, 10h
0x140083e51  jz      short loc_140083E5D
0x140083e53  cmp     byte ptr [rcx+29h], 3
0x140083e57  jb      short loc_140083E5D
0x140083e59  mov     dl, 1
0x140083e5b  jmp     short loc_140083E5F
0x140083e5d  xor     dl, dl
0x140083e5f  lea     rax, WPP_RECORDER_INITIALIZED
0x140083e66  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140083e6d  setnz   r8b
0x140083e71  test    dl, dl
0x140083e73  jnz     short loc_140083E7A
0x140083e75  test    r8b, r8b
0x140083e78  jz      short loc_140083E20
0x140083e7a  lea     rax, WPP_ba082f9301ac38daa38d12b5f87bfe98_Traceguids
0x140083e81  mov     [rsp+170h+var_138], rax
0x140083e86  mov     [rsp+170h+var_140], 22h ; '"'
0x140083e8d  jmp     loc_140083E06
0x140083e92  mov     r12d, 1
0x140083e98  jmp     short loc_140083ECE
0x140083e9a  mov     rcx, rbx; this
0x140083e9d  call    ?DepleteKlonez@CPcmPin@@AEAAXXZ; CPcmPin::DepleteKlonez(void)
0x140083ea2  mov     rcx, rbx; this
0x140083ea5  mov     [rbx+38h], rdi
0x140083ea9  mov     [rbx+40h], rdi
0x140083ead  mov     [rbx+48h], rdi
0x140083eb1  mov     [rbx+28h], rdi
0x140083eb5  call    ?ResetCorrelatedPosition@CPcmPin@@AEAAXXZ; CPcmPin::ResetCorrelatedPosition(void)
0x140083eba  mov     rcx, [rbx+20h]; this
0x140083ebe  mov     [rbx+90h], rdi
0x140083ec5  mov     [rbx+78h], rdi
0x140083ec9  call    ?ResetOutputCodec@A2DP_Device@@QEAAXXZ; A2DP_Device::ResetOutputCodec(void)
0x140083ece  mov     rax, [rbx+20h]
0x140083ed2  test    rax, rax
0x140083ed5  jz      short loc_140083EED
0x140083ed7  mov     rcx, [rax+8]; this
0x140083edb  test    r12d, r12d
0x140083ede  jz      short loc_140083EE6
0x140083ee0  mov     rdx, [rbx+10h]
0x140083ee4  jmp     short loc_140083EE8
0x140083ee6  xor     edx, edx; struct _KSPIN *
0x140083ee8  call    ?AttachRelatedPin@A2dpRole@@QEAAXPEAU_KSPIN@@@Z; A2dpRole::AttachRelatedPin(_KSPIN *)
0x140083eed  test    r13d, r13d
0x140083ef0  jz      short loc_140083EFC
0x140083ef2  xor     edx, edx; __int64
0x140083ef4  mov     rcx, rbx; this
0x140083ef7  call    ?SetTimer@CPcmPin@@AEAAX_J@Z; CPcmPin::SetTimer(__int64)
0x140083efc  mov     rax, ds:0FFFFF78000000008h
0x140083f06  lea     rdx, [rbp+70h+var_D0]; retstr
0x140083f0a  mov     rsi, rax
0x140083f0d  mov     rcx, rbx; this
0x140083f10  sub     rsi, [rsp+170h+var_108]
0x140083f15  call    ?GetAudioTraceSessionId@CPcmPin@@QEBA?AU_GUID@@XZ; CPcmPin::GetAudioTraceSessionId(void)
0x140083f1a  xorps   xmm1, xmm1
0x140083f1d  lea     rdx, [rbp+70h+ActivityId]; ActivityId
0x140083f21  mov     ecx, 1; ControlCode
0x140083f26  movups  xmmword ptr [rbp+70h+ActivityId.Data1], xmm1
0x140083f2a  call    cs:__imp_EtwActivityIdControl
0x140083f31  nop     dword ptr [rax+rax+00h]
0x140083f36  mov     edx, cs:dword_14006F0F8
0x140083f3c  cmp     edx, 5
0x140083f3f  jbe     loc_140084021
0x140083f45  mov     rdx, 400000000000h
0x140083f4f  lea     rcx, dword_14006F0F8
0x140083f56  call    _tlgKeywordOn
0x140083f5b  test    al, al
0x140083f5d  jz      loc_140084021
0x140083f63  mov     rcx, [rbx+20h]; this
0x140083f67  call    ?GetAddress@A2DP_Device@@QEBA_KXZ; A2DP_Device::GetAddress(void)
0x140083f6c  mov     [rbp+70h+var_F0], rax
0x140083f70  lea     r9, [rbp+70h+ActivityId]
0x140083f74  mov     rax, 346DC5D63886594Bh
0x140083f7e  mov     dword ptr [rsp+170h+var_108], edi
0x140083f82  mul     rsi
0x140083f85  lea     rax, [rbp+70h+var_F0]
0x140083f89  mov     [rsp+170h+var_110], r14b
0x140083f8e  mov     [rbp+70h+var_50], rax
0x140083f92  lea     r8, [rbp+70h+var_D0]
0x140083f96  shr     rdx, 0Bh
0x140083f9a  lea     rax, [rbp+70h+var_E8]
0x140083f9e  mov     [rbp+70h+var_60], rax
0x140083fa2  lea     rcx, dword_14006F0F8
0x140083fa9  mov     [rbp+70h+var_E8], rdx
0x140083fad  lea     rax, [rsp+170h+var_108]
0x140083fb2  mov     [rbp+70h+var_70], rax
0x140083fb6  mov     edx, 8
0x140083fbb  lea     rax, [rsp+170h+var_110]
  ... truncated ...
```
