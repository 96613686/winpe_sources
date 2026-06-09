# Avdtp_impl::HandlePacket_GET_CONFIGURATION(bool,long,_SINGLE_PCK_CMD const *,ulong)

- ea: `0x14004ad18`
- end: `0x14004b25a`
- name: `?HandlePacket_GET_CONFIGURATION@Avdtp_impl@@AEAAX_NJPEBU_SINGLE_PCK_CMD@@K@Z`
- size: `1346`
- prototype: `void __fastcall(KSPIN_LOCK *this, char, unsigned int, const struct _SINGLE_PCK_CMD *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callers

- `0x14004e5fc`

## callees

- `0x140003530`
- `0x14000f570`
- `0x14002d890`
- `0x140036494`
- `0x14003b244`
- `0x14004980c`
- `0x140049e80`
- `0x14004ad18`
- `0x140053e54`
- `0x1400546d0`
- `0x140056048`
- `0x140056330`
- `0x140056430`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14004b0fd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004b192`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004b208`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004b0fd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004b192`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004b208`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b0cd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b162`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b1d8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b0cd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b162`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b1d8`

## pseudocode

```c
void __fastcall Avdtp_impl::HandlePacket_GET_CONFIGURATION(
        KSPIN_LOCK *this,
        char a2,
        unsigned int a3,
        const struct _SINGLE_PCK_CMD *a4,
        unsigned int a5)
{
  __int64 v9; // rdx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  char v13; // di
  int IfrRecorderLog; // eax
  __int64 v15; // r11
  int v16; // edx
  int v17; // r8d
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  PDEVICE_OBJECT v21; // rcx
  int v22; // edx
  int v23; // r8d
  unsigned int EndpointIndexByLocalSeid; // eax
  __int64 v25; // rdi
  int v26; // edx
  KIRQL v27; // al
  KSPIN_LOCK v28; // rdi
  KIRQL v29; // bp
  __int64 v30; // r9
  KIRQL v31; // al
  KIRQL v32; // bp
  char v33; // si
  KIRQL v34; // al
  KIRQL v35; // r14
  __int64 v36; // r8

  if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline() )
  {
    v13 = 1;
    LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      IfrRecorderLog = GetIfrRecorderLog(1, v9, v11);
      WPP_RECORDER_AND_TRACE_SF_lavdtp_txnidq(*(_QWORD *)(v15 + 24), v16, v17, IfrRecorderLog);
    }
  }
  else if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v10, v9, v11, v12) )
  {
    v10 = WPP_GLOBAL_Control;
    v13 = 1;
    LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_lavdtp_txnidqDq(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v11,
        WPP_GLOBAL_Control->DeviceExtension);
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    v13 = 1;
    LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_lavdtp_txnidqD(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v11,
        WPP_GLOBAL_Control->DeviceExtension);
  }
  if ( a2 )
  {
    if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v10, v9, v11, v12) )
    {
      v21 = WPP_GLOBAL_Control;
      LOBYTE(v18) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v18 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_avdtp_seidq(
          WPP_GLOBAL_Control->AttachedDevice,
          v18,
          v19,
          WPP_GLOBAL_Control->DeviceExtension);
    }
    else
    {
      v21 = WPP_GLOBAL_Control;
      LOBYTE(v18) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v18 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_avdtp_seid(
          WPP_GLOBAL_Control->AttachedDevice,
          v18,
          v19,
          WPP_GLOBAL_Control->DeviceExtension);
    }
    if ( a5 != 3 )
    {
      if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v21, v18, v19, v20) )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v13 = 0;
        }
        if ( v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v22) = v13;
          LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            v22,
            v23,
            WPP_GLOBAL_Control->DeviceExtension,
            4,
            4,
            158,
            (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
            (char)this);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v13 = 0;
        }
        if ( v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v22) = v13;
          LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v22,
            v23,
            WPP_GLOBAL_Control->DeviceExtension,
            4,
            4,
            159,
            (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids);
        }
      }
      Avdtp_impl::GetConfiguration_Rsp(a3, (Avdtp_impl *)this, 0, 0, 17);
      return;
    }
    EndpointIndexByLocalSeid = Avdtp_impl::FindEndpointIndexByLocalSeid((Avdtp_impl *)this, *((_BYTE *)a4 + 2) >> 2);
    v25 = EndpointIndexByLocalSeid;
    if ( EndpointIndexByLocalSeid == 4 )
    {
      Avdtp_impl::GetConfiguration_Rsp(a3, (Avdtp_impl *)this, 0, 0, 18);
      return;
    }
    Feature_60817472__private_IsEnabledDeviceUsageNoInline();
    v26 = this[25 * v25 + 29];
    if ( !v26 || (unsigned int)(v26 - 6) < 2 )
    {
      Avdtp_impl::GetConfiguration_Rsp(a3, (Avdtp_impl *)this, 0, 0, 49);
      return;
    }
    v27 = KeAcquireSpinLockRaiseToDpc(this + 200);
    v28 = this[143];
    v29 = v27;
    if ( v28 )
      ((void (__fastcall *)(KSPIN_LOCK))this[146])(this[143]);
    KeReleaseSpinLock(this + 200, v29);
    if ( v28 )
    {
      LOBYTE(v30) = *((_BYTE *)a4 + 2) >> 2;
      ((void (__fastcall *)(_QWORD, KSPIN_LOCK *, KSPIN_LOCK, __int64))this[161])(a3, this, v28, v30);
LABEL_82:
      ((void (__fastcall *)(KSPIN_LOCK))this[147])(v28);
    }
  }
  else if ( (*(_BYTE *)a4 & 3) == 2 )
  {
    v31 = KeAcquireSpinLockRaiseToDpc(this + 200);
    v28 = this[143];
    v32 = v31;
    if ( v28 )
      ((void (__fastcall *)(KSPIN_LOCK))this[146])(this[143]);
    KeReleaseSpinLock(this + 200, v32);
    if ( v28 )
    {
      ((void (__fastcall *)(KSPIN_LOCK *, KSPIN_LOCK, _QWORD, char *, unsigned int))this[162])(
        this,
        v28,
        0,
        (char *)a4 + 2,
        a5 - 2);
      goto LABEL_82;
    }
  }
  else
  {
    v33 = *((_BYTE *)a4 + 2);
    if ( !v33 )
      v33 = 49;
    v34 = KeAcquireSpinLockRaiseToDpc(this + 200);
    v28 = this[143];
    v35 = v34;
    if ( v28 )
      ((void (__fastcall *)(KSPIN_LOCK))this[146])(this[143]);
    KeReleaseSpinLock(this + 200, v35);
    if ( v28 )
    {
      LOBYTE(v36) = v33;
      ((void (__fastcall *)(KSPIN_LOCK *, KSPIN_LOCK, __int64, _QWORD, _DWORD))this[162])(this, v28, v36, 0, 0);
      goto LABEL_82;
    }
  }
}

```

## disassembly

```asm
0x14004ad18  push    rbx
0x14004ad1a  push    rbp
0x14004ad1b  push    rsi
0x14004ad1c  push    rdi
0x14004ad1d  push    r12
0x14004ad1f  push    r13
0x14004ad21  push    r14
0x14004ad23  push    r15
0x14004ad25  sub     rsp, 78h
0x14004ad29  mov     r15, r9
0x14004ad2c  movzx   r12d, dl
0x14004ad30  mov     r13d, r8d
0x14004ad33  mov     rbx, rcx
0x14004ad36  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x14004ad3b  test    eax, eax
0x14004ad3d  jz      loc_14004ADC3
0x14004ad43  mov     r11, cs:WPP_GLOBAL_Control
0x14004ad4a  lea     rbp, WPP_GLOBAL_Control
0x14004ad51  mov     edi, 1
0x14004ad56  mov     sil, 8
0x14004ad59  cmp     r11, rbp
0x14004ad5c  jz      short loc_14004AD73
0x14004ad5e  mov     eax, [r11+2Ch]
0x14004ad62  test    sil, al
0x14004ad65  jz      short loc_14004AD73
0x14004ad67  cmp     byte ptr [r11+29h], 4
0x14004ad6c  jb      short loc_14004AD73
0x14004ad6e  mov     dl, dil
0x14004ad71  jmp     short loc_14004AD75
0x14004ad73  xor     dl, dl
0x14004ad75  lea     r14, WPP_RECORDER_INITIALIZED
0x14004ad7c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004ad83  setnz   r8b
0x14004ad87  test    dl, dl
0x14004ad89  jnz     short loc_14004AD94
0x14004ad8b  test    r8b, r8b
0x14004ad8e  jz      loc_14004AED1
0x14004ad94  mov     rcx, rdi
0x14004ad97  call    ?GetIfrRecorderLog@@YAPEAURECORDER_LOG__@@W4IfrLogId@@@Z; GetIfrRecorderLog(IfrLogId)
0x14004ad9c  mov     rcx, [r11+18h]
0x14004ada0  mov     r9, rax
0x14004ada3  mov     [rsp+0B8h+var_68], rbx
0x14004ada8  mov     dword ptr [rsp+0B8h+var_70], r13d
0x14004adad  mov     dword ptr [rsp+0B8h+var_78], r12d
0x14004adb2  mov     [rsp+0B8h+var_88], 99h
0x14004adb9  call    WPP_RECORDER_AND_TRACE_SF_lavdtp_txnidq
0x14004adbe  jmp     loc_14004AED1
0x14004adc3  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14004adc8  test    eax, eax
0x14004adca  jz      loc_14004AE56
0x14004add0  mov     rcx, cs:WPP_GLOBAL_Control
0x14004add7  lea     rbp, WPP_GLOBAL_Control
0x14004adde  mov     edi, 1
0x14004ade3  mov     sil, 8
0x14004ade6  cmp     rcx, rbp
0x14004ade9  jz      short loc_14004ADFE
0x14004adeb  mov     eax, [rcx+2Ch]
0x14004adee  test    sil, al
0x14004adf1  jz      short loc_14004ADFE
0x14004adf3  cmp     byte ptr [rcx+29h], 4
0x14004adf7  jb      short loc_14004ADFE
0x14004adf9  mov     dl, dil
0x14004adfc  jmp     short loc_14004AE00
0x14004adfe  xor     dl, dl
0x14004ae00  lea     r14, WPP_RECORDER_INITIALIZED
0x14004ae07  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004ae0e  setnz   r8b
0x14004ae12  test    dl, dl
0x14004ae14  jnz     short loc_14004AE1F
0x14004ae16  test    r8b, r8b
0x14004ae19  jz      loc_14004AED1
0x14004ae1f  mov     r9d, [rsp+0B8h+arg_20]
0x14004ae27  mov     [rsp+0B8h+var_58], rbx
0x14004ae2c  mov     [rsp+0B8h+var_60], r9d
0x14004ae31  mov     r9, [rcx+40h]
0x14004ae35  mov     rcx, [rcx+18h]
0x14004ae39  mov     [rsp+0B8h+var_68], r15
0x14004ae3e  mov     dword ptr [rsp+0B8h+var_70], r13d
0x14004ae43  mov     dword ptr [rsp+0B8h+var_78], r12d
0x14004ae48  mov     [rsp+0B8h+var_88], 9Ah
0x14004ae4f  call    WPP_RECORDER_AND_TRACE_SF_lavdtp_txnidqDq
0x14004ae54  jmp     short loc_14004AED1
0x14004ae56  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ae5d  lea     rbp, WPP_GLOBAL_Control
0x14004ae64  mov     edi, 1
0x14004ae69  mov     sil, 8
0x14004ae6c  cmp     rcx, rbp
0x14004ae6f  jz      short loc_14004AE84
0x14004ae71  mov     eax, [rcx+2Ch]
0x14004ae74  test    sil, al
0x14004ae77  jz      short loc_14004AE84
0x14004ae79  cmp     byte ptr [rcx+29h], 4
0x14004ae7d  jb      short loc_14004AE84
0x14004ae7f  mov     dl, dil
0x14004ae82  jmp     short loc_14004AE86
0x14004ae84  xor     dl, dl
0x14004ae86  lea     r14, WPP_RECORDER_INITIALIZED
0x14004ae8d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004ae94  setnz   r8b
0x14004ae98  test    dl, dl
0x14004ae9a  jnz     short loc_14004AEA1
0x14004ae9c  test    r8b, r8b
0x14004ae9f  jz      short loc_14004AED1
0x14004aea1  mov     r9d, [rsp+0B8h+arg_20]
0x14004aea9  mov     [rsp+0B8h+var_60], r9d
0x14004aeae  mov     r9, [rcx+40h]
0x14004aeb2  mov     rcx, [rcx+18h]
0x14004aeb6  mov     [rsp+0B8h+var_68], r15
0x14004aebb  mov     dword ptr [rsp+0B8h+var_70], r13d
0x14004aec0  mov     dword ptr [rsp+0B8h+var_78], r12d
0x14004aec5  mov     [rsp+0B8h+var_88], 9Bh
0x14004aecc  call    WPP_RECORDER_AND_TRACE_SF_lavdtp_txnidqD
0x14004aed1  test    r12b, r12b
0x14004aed4  jz      loc_14004B14F
0x14004aeda  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14004aedf  test    eax, eax
0x14004aee1  jz      short loc_14004AF3E
0x14004aee3  mov     rcx, cs:WPP_GLOBAL_Control
0x14004aeea  cmp     rcx, rbp
0x14004aeed  jz      short loc_14004AF02
0x14004aeef  mov     eax, [rcx+2Ch]
0x14004aef2  test    sil, al
0x14004aef5  jz      short loc_14004AF02
0x14004aef7  cmp     byte ptr [rcx+29h], 4
0x14004aefb  jb      short loc_14004AF02
0x14004aefd  mov     dl, dil
0x14004af00  jmp     short loc_14004AF04
0x14004af02  xor     dl, dl
0x14004af04  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004af0b  setnz   r8b
0x14004af0f  test    dl, dl
0x14004af11  jnz     short loc_14004AF18
0x14004af13  test    r8b, r8b
0x14004af16  jz      short loc_14004AF92
0x14004af18  mov     al, [r15+2]
0x14004af1c  mov     r9, [rcx+40h]
0x14004af20  mov     rcx, [rcx+18h]
0x14004af24  shr     al, 2
0x14004af27  mov     [rsp+0B8h+var_70], rbx
0x14004af2c  mov     byte ptr [rsp+0B8h+var_78], al
0x14004af30  mov     [rsp+0B8h+var_88], 9Ch
0x14004af37  call    WPP_RECORDER_AND_TRACE_SF_avdtp_seidq
0x14004af3c  jmp     short loc_14004AF92
0x14004af3e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004af45  cmp     rcx, rbp
0x14004af48  jz      short loc_14004AF5D
0x14004af4a  mov     eax, [rcx+2Ch]
0x14004af4d  test    sil, al
0x14004af50  jz      short loc_14004AF5D
0x14004af52  cmp     byte ptr [rcx+29h], 4
0x14004af56  jb      short loc_14004AF5D
0x14004af58  mov     dl, dil
0x14004af5b  jmp     short loc_14004AF5F
0x14004af5d  xor     dl, dl
0x14004af5f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004af66  setnz   r8b
0x14004af6a  test    dl, dl
0x14004af6c  jnz     short loc_14004AF73
0x14004af6e  test    r8b, r8b
0x14004af71  jz      short loc_14004AF92
0x14004af73  mov     al, [r15+2]
0x14004af77  mov     r9, [rcx+40h]
0x14004af7b  mov     rcx, [rcx+18h]
0x14004af7f  shr     al, 2
0x14004af82  mov     byte ptr [rsp+0B8h+var_78], al
0x14004af86  mov     [rsp+0B8h+var_88], 9Dh
0x14004af8d  call    WPP_RECORDER_AND_TRACE_SF_avdtp_seid
0x14004af92  cmp     [rsp+0B8h+arg_20], 3
0x14004af9a  jz      loc_14004B082
0x14004afa0  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14004afa5  test    eax, eax
0x14004afa7  jz      short loc_14004B016
0x14004afa9  mov     rcx, cs:WPP_GLOBAL_Control
0x14004afb0  cmp     rcx, rbp
0x14004afb3  jz      short loc_14004AFC3
0x14004afb5  mov     eax, [rcx+2Ch]
0x14004afb8  test    sil, al
0x14004afbb  jz      short loc_14004AFC3
0x14004afbd  cmp     byte ptr [rcx+29h], 4
0x14004afc1  jnb     short loc_14004AFC6
0x14004afc3  xor     dil, dil
0x14004afc6  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004afcd  setnz   r8b
0x14004afd1  test    dil, dil
0x14004afd4  jnz     short loc_14004AFDF
0x14004afd6  test    r8b, r8b
0x14004afd9  jz      loc_14004B078
0x14004afdf  mov     r9, [rcx+40h]
0x14004afe3  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004afea  mov     rcx, [rcx+18h]
0x14004afee  mov     dl, dil
0x14004aff1  mov     [rsp+0B8h+var_78], rbx
0x14004aff6  mov     [rsp+0B8h+var_80], rax
0x14004affb  mov     [rsp+0B8h+var_88], 9Eh
0x14004b002  mov     [rsp+0B8h+var_90], 4
0x14004b00a  mov     [rsp+0B8h+var_98], 4
0x14004b00f  call    WPP_RECORDER_AND_TRACE_SF_q
0x14004b014  jmp     short loc_14004B078
0x14004b016  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b01d  cmp     rcx, rbp
0x14004b020  jz      short loc_14004B030
0x14004b022  mov     eax, [rcx+2Ch]
0x14004b025  test    sil, al
0x14004b028  jz      short loc_14004B030
0x14004b02a  cmp     byte ptr [rcx+29h], 4
0x14004b02e  jnb     short loc_14004B033
0x14004b030  xor     dil, dil
0x14004b033  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004b03a  setnz   r8b
0x14004b03e  test    dil, dil
0x14004b041  jnz     short loc_14004B048
0x14004b043  test    r8b, r8b
0x14004b046  jz      short loc_14004B078
0x14004b048  mov     r9, [rcx+40h]
0x14004b04c  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004b053  mov     rcx, [rcx+18h]
0x14004b057  mov     dl, dil
0x14004b05a  mov     [rsp+0B8h+var_80], rax
0x14004b05f  mov     [rsp+0B8h+var_88], 9Fh
0x14004b066  mov     [rsp+0B8h+var_90], 4
0x14004b06e  mov     [rsp+0B8h+var_98], 4
0x14004b073  call    WPP_RECORDER_AND_TRACE_SF_
0x14004b078  mov     [rsp+0B8h+var_98], 11h
0x14004b07d  jmp     loc_14004B139
0x14004b082  mov     dl, [r15+2]
0x14004b086  mov     rcx, rbx; this
0x14004b089  shr     dl, 2; unsigned __int8
0x14004b08c  call    ?FindEndpointIndexByLocalSeid@Avdtp_impl@@AEAAKE@Z; Avdtp_impl::FindEndpointIndexByLocalSeid(uchar)
0x14004b091  mov     edi, eax
0x14004b093  cmp     eax, 4
0x14004b096  jnz     short loc_14004B0A2
0x14004b098  mov     [rsp+0B8h+var_98], 12h
0x14004b09d  jmp     loc_14004B139
0x14004b0a2  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x14004b0a7  imul    rcx, rdi, 0C8h
0x14004b0ae  mov     edx, [rcx+rbx+0E8h]
0x14004b0b5  test    edx, edx
0x14004b0b7  jz      short loc_14004B134
0x14004b0b9  sub     edx, 6
0x14004b0bc  jz      short loc_14004B134
0x14004b0be  cmp     edx, 1
0x14004b0c1  jz      short loc_14004B134
0x14004b0c3  lea     rsi, [rbx+640h]
0x14004b0ca  mov     rcx, rsi; SpinLock
0x14004b0cd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004b0d4  nop     dword ptr [rax+rax+00h]
0x14004b0d9  mov     rdi, [rbx+478h]
0x14004b0e0  mov     bpl, al
0x14004b0e3  test    rdi, rdi
0x14004b0e6  jz      short loc_14004B0F7
0x14004b0e8  mov     rax, [rbx+490h]
0x14004b0ef  mov     rcx, rdi
0x14004b0f2  call    _guard_dispatch_icall
0x14004b0f7  mov     dl, bpl; NewIrql
0x14004b0fa  mov     rcx, rsi; SpinLock
0x14004b0fd  call    cs:__imp_KeReleaseSpinLock
0x14004b104  nop     dword ptr [rax+rax+00h]
0x14004b109  test    rdi, rdi
0x14004b10c  jz      loc_14004B248
0x14004b112  mov     r9b, [r15+2]
0x14004b116  mov     r8, rdi
0x14004b119  mov     rax, [rbx+508h]
0x14004b120  mov     rdx, rbx
0x14004b123  shr     r9b, 2
0x14004b127  mov     ecx, r13d
0x14004b12a  call    _guard_dispatch_icall
0x14004b12f  jmp     loc_14004B239
0x14004b134  mov     [rsp+0B8h+var_98], 31h ; '1'; char
0x14004b139  xor     r9d, r9d; Size
0x14004b13c  xor     r8d, r8d; Src
0x14004b13f  mov     rdx, rbx; this
0x14004b142  mov     ecx, r13d; int
0x14004b145  call    ?GetConfiguration_Rsp@Avdtp_impl@@CAJJPEAXPEBU_AVDTP_CATEGORY_HEADER@@KE@Z; Avdtp_impl::GetConfiguration_Rsp(long,void *,_AVDTP_CATEGORY_HEADER const *,ulong,uchar)
0x14004b14a  jmp     loc_14004B248
0x14004b14f  mov     al, [r15]
0x14004b152  and     al, 3
0x14004b154  cmp     al, 2
0x14004b156  jnz     short loc_14004B1BE
0x14004b158  lea     rsi, [rbx+640h]
0x14004b15f  mov     rcx, rsi; SpinLock
0x14004b162  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004b169  nop     dword ptr [rax+rax+00h]
0x14004b16e  mov     rdi, [rbx+478h]
0x14004b175  mov     bpl, al
0x14004b178  test    rdi, rdi
0x14004b17b  jz      short loc_14004B18C
0x14004b17d  mov     rax, [rbx+490h]
0x14004b184  mov     rcx, rdi
0x14004b187  call    _guard_dispatch_icall
0x14004b18c  mov     dl, bpl; NewIrql
0x14004b18f  mov     rcx, rsi; SpinLock
0x14004b192  call    cs:__imp_KeReleaseSpinLock
0x14004b199  nop     dword ptr [rax+rax+00h]
0x14004b19e  test    rdi, rdi
0x14004b1a1  jz      loc_14004B248
0x14004b1a7  mov     edx, [rsp+0B8h+arg_20]
0x14004b1ae  lea     r9, [r15+2]
0x14004b1b2  add     edx, 0FFFFFFFEh
0x14004b1b5  mov     dword ptr [rsp+0B8h+var_98], edx
0x14004b1b9  xor     r8d, r8d
  ... truncated ...
```
