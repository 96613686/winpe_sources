# Avdtp_impl::HandlePacket_SET_CONFIGURATION(bool,long,_SINGLE_PCK_CMD const *,ulong,uchar,uchar)

- ea: `0x14004bb00`
- end: `0x14004c1c9`
- name: `?HandlePacket_SET_CONFIGURATION@Avdtp_impl@@AEAAX_NJPEBU_SINGLE_PCK_CMD@@KEE@Z`
- size: `1737`
- prototype: `void __fastcall(KSPIN_LOCK *this, char, unsigned int, const struct _SINGLE_PCK_CMD *, unsigned int, unsigned __int8, unsigned __int8)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting`

## callers

- `0x14004e5fc`

## callees

- `0x140003530`
- `0x14000f570`
- `0x14002d890`
- `0x140036494`
- `0x14003b244`
- `0x140049870`
- `0x14004bb00`
- `0x14004e0dc`
- `0x140050150`
- `0x140052ba8`
- `0x140052ca8`
- `0x140054528`
- `0x1400545e8`
- `0x140056048`
- `0x140056330`
- `0x140056430`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14004bfb0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004c17f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004bfb0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004c17f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004bf80`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004c14f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004bf80`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004c14f`

## pseudocode

```c
void __fastcall Avdtp_impl::HandlePacket_SET_CONFIGURATION(
        KSPIN_LOCK *this,
        char a2,
        unsigned int a3,
        const struct _SINGLE_PCK_CMD *a4,
        unsigned int a5,
        unsigned __int8 a6,
        unsigned __int8 a7)
{
  __int64 v11; // rdx
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  char v15; // si
  int IfrRecorderLog; // eax
  __int64 v17; // r11
  int v18; // edx
  int v19; // r8d
  unsigned int v20; // r13d
  int v21; // edx
  int v22; // r8d
  unsigned __int8 v23; // r9
  unsigned __int8 v24; // r8
  int v25; // edx
  int v26; // r8d
  unsigned __int8 v27; // dl
  unsigned int EndpointIndexByLocalSeid_AndReturnState; // eax
  KIRQL v29; // al
  KSPIN_LOCK v30; // rsi
  KIRQL v31; // r14
  __int64 v32; // r9
  KSPIN_LOCK v33; // rcx
  unsigned __int8 v34; // r12
  char v35; // r13
  int v36; // r8d
  unsigned __int8 v37; // bp
  unsigned __int8 v38; // r14
  int v39; // edx
  int v40; // edx
  KIRQL v41; // al
  KSPIN_LOCK v42; // rbx
  KIRQL v43; // bp
  __int64 v44; // r8
  __int64 v45; // r9
  int v46; // [rsp+C8h] [rbp+10h] BYREF

  if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline() )
  {
    v15 = 1;
    LOBYTE(v11) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      IfrRecorderLog = GetIfrRecorderLog(1, v11, v13);
      WPP_RECORDER_AND_TRACE_SF_lavdtp_txnidq(*(_QWORD *)(v17 + 24), v18, v19, IfrRecorderLog);
    }
  }
  else if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v12, v11, v13, v14) )
  {
    v12 = WPP_GLOBAL_Control;
    v15 = 1;
    LOBYTE(v11) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_lavdtp_txnidqDq(
        WPP_GLOBAL_Control->AttachedDevice,
        v11,
        v13,
        WPP_GLOBAL_Control->DeviceExtension);
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
    v15 = 1;
    LOBYTE(v11) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_lavdtp_txnidqD(
        WPP_GLOBAL_Control->AttachedDevice,
        v11,
        v13,
        WPP_GLOBAL_Control->DeviceExtension);
  }
  if ( a2 )
  {
    v20 = a5;
    if ( a5 < 6 )
    {
      if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v12, v11, v13, v14) )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          v15 = 0;
        }
        if ( v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v21) = v15;
          LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            v21,
            v22,
            WPP_GLOBAL_Control->DeviceExtension,
            2,
            4,
            163,
            (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
            (char)this);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          v15 = 0;
        }
        if ( v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v21) = v15;
          LOBYTE(v22) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            v21,
            v22,
            WPP_GLOBAL_Control->DeviceExtension,
            2,
            4,
            164,
            (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids);
        }
      }
      v23 = 17;
      v24 = -1;
      goto LABEL_45;
    }
    if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v12, v11, v13, v14) )
    {
      LOBYTE(v25) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)v25 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_avdtp_seidavdtp_seidq(
          WPP_GLOBAL_Control->AttachedDevice,
          v25,
          v26,
          WPP_GLOBAL_Control->DeviceExtension);
      }
    }
    else
    {
      LOBYTE(v25) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)v25 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_avdtp_seidavdtp_seid(
          WPP_GLOBAL_Control->AttachedDevice,
          v25,
          v26,
          WPP_GLOBAL_Control->DeviceExtension);
      }
    }
    v27 = *((_BYTE *)a4 + 2) >> 2;
    v46 = 0;
    EndpointIndexByLocalSeid_AndReturnState = Avdtp_impl::FindEndpointIndexByLocalSeid_AndReturnState(
                                                (Avdtp_impl *)this,
                                                v27,
                                                (enum TAG_AvdtpSepState *)&v46);
    switch ( *((_BYTE *)a4 + 4) )
    {
      case 1:
        if ( *((_BYTE *)a4 + 5) )
        {
          v23 = 35;
          v24 = *((_BYTE *)a4 + 2) >> 2;
          goto LABEL_45;
        }
        break;
      case 2:
        if ( *((_BYTE *)a4 + 5) )
        {
          v23 = 24;
          v24 = *((_BYTE *)a4 + 2) >> 2;
          goto LABEL_45;
        }
        break;
      case 3:
        if ( *((_BYTE *)a4 + 5) != 3 )
        {
          v23 = 37;
          v24 = *((_BYTE *)a4 + 2) >> 2;
          goto LABEL_45;
        }
        break;
      default:
        if ( *((_BYTE *)a4 + 4) != 4 )
        {
          if ( *((_BYTE *)a4 + 4) == 5 )
          {
            if ( *((_BYTE *)a4 + 5) != 1 )
            {
              v23 = 38;
              v24 = *((_BYTE *)a4 + 2) >> 2;
              goto LABEL_45;
            }
          }
          else if ( (unsigned int)*((unsigned __int8 *)a4 + 4) - 6 >= 2 )
          {
            v23 = 23;
            v24 = *((_BYTE *)a4 + 2) >> 2;
LABEL_45:
            Avdtp_impl::SetConfiguration_Rsp(a3, this, v24, v23);
            return;
          }
        }
        break;
    }
    if ( EndpointIndexByLocalSeid_AndReturnState == 4 )
    {
      v23 = 18;
      v24 = *((_BYTE *)a4 + 2) >> 2;
      goto LABEL_45;
    }
    if ( v46 )
    {
      v23 = 19;
      v24 = *((_BYTE *)a4 + 2) >> 2;
      goto LABEL_45;
    }
    v29 = KeAcquireSpinLockRaiseToDpc(this + 200);
    v30 = this[143];
    v31 = v29;
    if ( v30 )
      ((void (__fastcall *)(KSPIN_LOCK))this[146])(this[143]);
    KeReleaseSpinLock(this + 200, v31);
    if ( v30 )
    {
      LOBYTE(v32) = *((_BYTE *)a4 + 2) >> 2;
      ((void (__fastcall *)(_QWORD, KSPIN_LOCK *, KSPIN_LOCK, __int64, _BYTE, char *, unsigned int))this[157])(
        a3,
        this,
        v30,
        v32,
        *((_BYTE *)a4 + 3) >> 2,
        (char *)a4 + 4,
        v20 - 4);
      v33 = v30;
LABEL_111:
      ((void (__fastcall *)(KSPIN_LOCK))this[147])(v33);
      return;
    }
    return;
  }
  if ( (*(_BYTE *)a4 & 3) == 3 )
  {
    v34 = *((_BYTE *)a4 + 3);
    v35 = *((_BYTE *)a4 + 2);
  }
  else
  {
    v34 = 0;
    v35 = 0;
  }
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v12, v11, v13, v14) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v15 = 0;
    }
    if ( v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v37 = a7;
      v38 = a6;
      v39 = v34;
      LOBYTE(v39) = v15;
      LOBYTE(v36) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_LLavdtp_seidavdtp_seidq(
        WPP_GLOBAL_Control->AttachedDevice,
        v39,
        v36,
        WPP_GLOBAL_Control->DeviceExtension);
      goto LABEL_105;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v15 = 0;
    }
    if ( v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v37 = a7;
      v38 = a6;
      v40 = v34;
      LOBYTE(v40) = v15;
      LOBYTE(v36) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_LLavdtp_seidavdtp_seid(
        WPP_GLOBAL_Control->AttachedDevice,
        v40,
        v36,
        WPP_GLOBAL_Control->DeviceExtension);
      goto LABEL_105;
    }
  }
  v38 = a6;
  v37 = a7;
LABEL_105:
  if ( (*(_BYTE *)a4 & 3) == 2 )
    Avdtp_impl::MarkEndpointConfigured((Avdtp_impl *)this, v38, v37);
  v41 = KeAcquireSpinLockRaiseToDpc(this + 200);
  v42 = this[143];
  v43 = v41;
  if ( v42 )
    ((void (__fastcall *)(KSPIN_LOCK))this[146])(this[143]);
  KeReleaseSpinLock(this + 200, v43);
  if ( v42 )
  {
    LOBYTE(v45) = v35;
    LOBYTE(v44) = v34;
    ((void (__fastcall *)(KSPIN_LOCK *, KSPIN_LOCK, __int64, __int64))this[160])(this, v42, v44, v45);
    v33 = v42;
    goto LABEL_111;
  }
}

```

## disassembly

```asm
0x14004bb00  push    rbx
0x14004bb02  push    rbp
0x14004bb03  push    rsi
0x14004bb04  push    rdi
0x14004bb05  push    r12
0x14004bb07  push    r13
0x14004bb09  push    r14
0x14004bb0b  push    r15
0x14004bb0d  sub     rsp, 78h
0x14004bb11  mov     rbx, r9
0x14004bb14  movzx   r13d, dl
0x14004bb18  mov     r12d, r8d
0x14004bb1b  mov     rdi, rcx
0x14004bb1e  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x14004bb23  test    eax, eax
0x14004bb25  jz      loc_14004BBAB
0x14004bb2b  mov     r11, cs:WPP_GLOBAL_Control
0x14004bb32  lea     r14, WPP_GLOBAL_Control
0x14004bb39  mov     esi, 1
0x14004bb3e  mov     bpl, 8
0x14004bb41  cmp     r11, r14
0x14004bb44  jz      short loc_14004BB5B
0x14004bb46  mov     eax, [r11+2Ch]
0x14004bb4a  test    bpl, al
0x14004bb4d  jz      short loc_14004BB5B
0x14004bb4f  cmp     byte ptr [r11+29h], 4
0x14004bb54  jb      short loc_14004BB5B
0x14004bb56  mov     dl, sil
0x14004bb59  jmp     short loc_14004BB5D
0x14004bb5b  xor     dl, dl
0x14004bb5d  lea     r15, WPP_RECORDER_INITIALIZED
0x14004bb64  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004bb6b  setnz   r8b
0x14004bb6f  test    dl, dl
0x14004bb71  jnz     short loc_14004BB7C
0x14004bb73  test    r8b, r8b
0x14004bb76  jz      loc_14004BCB9
0x14004bb7c  mov     rcx, rsi
0x14004bb7f  call    ?GetIfrRecorderLog@@YAPEAURECORDER_LOG__@@W4IfrLogId@@@Z; GetIfrRecorderLog(IfrLogId)
0x14004bb84  mov     rcx, [r11+18h]
0x14004bb88  mov     r9, rax
0x14004bb8b  mov     [rsp+0B8h+var_68], rdi
0x14004bb90  mov     [rsp+0B8h+var_70], r12d
0x14004bb95  mov     dword ptr [rsp+0B8h+var_78], r13d
0x14004bb9a  mov     word ptr [rsp+0B8h+var_88], 0A0h
0x14004bba1  call    WPP_RECORDER_AND_TRACE_SF_lavdtp_txnidq
0x14004bba6  jmp     loc_14004BCB9
0x14004bbab  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14004bbb0  test    eax, eax
0x14004bbb2  jz      loc_14004BC3E
0x14004bbb8  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bbbf  lea     r14, WPP_GLOBAL_Control
0x14004bbc6  mov     esi, 1
0x14004bbcb  mov     bpl, 8
0x14004bbce  cmp     rcx, r14
0x14004bbd1  jz      short loc_14004BBE6
0x14004bbd3  mov     eax, [rcx+2Ch]
0x14004bbd6  test    bpl, al
0x14004bbd9  jz      short loc_14004BBE6
0x14004bbdb  cmp     byte ptr [rcx+29h], 4
0x14004bbdf  jb      short loc_14004BBE6
0x14004bbe1  mov     dl, sil
0x14004bbe4  jmp     short loc_14004BBE8
0x14004bbe6  xor     dl, dl
0x14004bbe8  lea     r15, WPP_RECORDER_INITIALIZED
0x14004bbef  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004bbf6  setnz   r8b
0x14004bbfa  test    dl, dl
0x14004bbfc  jnz     short loc_14004BC07
0x14004bbfe  test    r8b, r8b
0x14004bc01  jz      loc_14004BCB9
0x14004bc07  mov     r9d, [rsp+0B8h+arg_20]
0x14004bc0f  mov     [rsp+0B8h+var_58], rdi
0x14004bc14  mov     [rsp+0B8h+var_60], r9d
0x14004bc19  mov     r9, [rcx+40h]
0x14004bc1d  mov     rcx, [rcx+18h]
0x14004bc21  mov     [rsp+0B8h+var_68], rbx
0x14004bc26  mov     [rsp+0B8h+var_70], r12d
0x14004bc2b  mov     dword ptr [rsp+0B8h+var_78], r13d
0x14004bc30  mov     word ptr [rsp+0B8h+var_88], 0A1h
0x14004bc37  call    WPP_RECORDER_AND_TRACE_SF_lavdtp_txnidqDq
0x14004bc3c  jmp     short loc_14004BCB9
0x14004bc3e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bc45  lea     r14, WPP_GLOBAL_Control
0x14004bc4c  mov     esi, 1
0x14004bc51  mov     bpl, 8
0x14004bc54  cmp     rcx, r14
0x14004bc57  jz      short loc_14004BC6C
0x14004bc59  mov     eax, [rcx+2Ch]
0x14004bc5c  test    bpl, al
0x14004bc5f  jz      short loc_14004BC6C
0x14004bc61  cmp     byte ptr [rcx+29h], 4
0x14004bc65  jb      short loc_14004BC6C
0x14004bc67  mov     dl, sil
0x14004bc6a  jmp     short loc_14004BC6E
0x14004bc6c  xor     dl, dl
0x14004bc6e  lea     r15, WPP_RECORDER_INITIALIZED
0x14004bc75  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004bc7c  setnz   r8b
0x14004bc80  test    dl, dl
0x14004bc82  jnz     short loc_14004BC89
0x14004bc84  test    r8b, r8b
0x14004bc87  jz      short loc_14004BCB9
0x14004bc89  mov     r9d, [rsp+0B8h+arg_20]
0x14004bc91  mov     [rsp+0B8h+var_60], r9d
0x14004bc96  mov     r9, [rcx+40h]
0x14004bc9a  mov     rcx, [rcx+18h]
0x14004bc9e  mov     [rsp+0B8h+var_68], rbx
0x14004bca3  mov     [rsp+0B8h+var_70], r12d
0x14004bca8  mov     dword ptr [rsp+0B8h+var_78], r13d
0x14004bcad  mov     word ptr [rsp+0B8h+var_88], 0A2h
0x14004bcb4  call    WPP_RECORDER_AND_TRACE_SF_lavdtp_txnidqD
0x14004bcb9  test    r13b, r13b
0x14004bcbc  jz      loc_14004C004
0x14004bcc2  mov     r13d, [rsp+0B8h+arg_20]
0x14004bcca  cmp     r13d, 6
0x14004bcce  jnb     loc_14004BDC2
0x14004bcd4  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14004bcd9  test    eax, eax
0x14004bcdb  jz      short loc_14004BD4A
0x14004bcdd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bce4  cmp     rcx, r14
0x14004bce7  jz      short loc_14004BCF7
0x14004bce9  mov     eax, [rcx+2Ch]
0x14004bcec  test    bpl, al
0x14004bcef  jz      short loc_14004BCF7
0x14004bcf1  cmp     byte ptr [rcx+29h], 2
0x14004bcf5  jnb     short loc_14004BCFA
0x14004bcf7  xor     sil, sil
0x14004bcfa  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004bd01  setnz   r8b
0x14004bd05  test    sil, sil
0x14004bd08  jnz     short loc_14004BD13
0x14004bd0a  test    r8b, r8b
0x14004bd0d  jz      loc_14004BDAC
0x14004bd13  mov     r9, [rcx+40h]
0x14004bd17  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004bd1e  mov     rcx, [rcx+18h]
0x14004bd22  mov     dl, sil
0x14004bd25  mov     [rsp+0B8h+var_78], rdi
0x14004bd2a  mov     [rsp+0B8h+var_80], rax
0x14004bd2f  mov     word ptr [rsp+0B8h+var_88], 0A3h
0x14004bd36  mov     dword ptr [rsp+0B8h+var_90], 4
0x14004bd3e  mov     [rsp+0B8h+var_98], 2
0x14004bd43  call    WPP_RECORDER_AND_TRACE_SF_q
0x14004bd48  jmp     short loc_14004BDAC
0x14004bd4a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bd51  cmp     rcx, r14
0x14004bd54  jz      short loc_14004BD64
0x14004bd56  mov     eax, [rcx+2Ch]
0x14004bd59  test    bpl, al
0x14004bd5c  jz      short loc_14004BD64
0x14004bd5e  cmp     byte ptr [rcx+29h], 2
0x14004bd62  jnb     short loc_14004BD67
0x14004bd64  xor     sil, sil
0x14004bd67  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004bd6e  setnz   r8b
0x14004bd72  test    sil, sil
0x14004bd75  jnz     short loc_14004BD7C
0x14004bd77  test    r8b, r8b
0x14004bd7a  jz      short loc_14004BDAC
0x14004bd7c  mov     r9, [rcx+40h]
0x14004bd80  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004bd87  mov     rcx, [rcx+18h]
0x14004bd8b  mov     dl, sil
0x14004bd8e  mov     [rsp+0B8h+var_80], rax
0x14004bd93  mov     word ptr [rsp+0B8h+var_88], 0A4h
0x14004bd9a  mov     dword ptr [rsp+0B8h+var_90], 4
0x14004bda2  mov     [rsp+0B8h+var_98], 2
0x14004bda7  call    WPP_RECORDER_AND_TRACE_SF_
0x14004bdac  mov     r9b, 11h; unsigned __int8
0x14004bdaf  mov     r8b, 0FFh; unsigned __int8
0x14004bdb2  mov     rdx, rdi; void *
0x14004bdb5  mov     ecx, r12d; int
0x14004bdb8  call    ?SetConfiguration_Rsp@Avdtp_impl@@CAJJPEAXEE@Z; Avdtp_impl::SetConfiguration_Rsp(long,void *,uchar,uchar)
0x14004bdbd  jmp     loc_14004C1B7
0x14004bdc2  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14004bdc7  test    eax, eax
0x14004bdc9  jz      short loc_14004BE36
0x14004bdcb  mov     rcx, cs:WPP_GLOBAL_Control
0x14004bdd2  cmp     rcx, r14
0x14004bdd5  jz      short loc_14004BDEA
0x14004bdd7  mov     eax, [rcx+2Ch]
0x14004bdda  test    bpl, al
0x14004bddd  jz      short loc_14004BDEA
0x14004bddf  cmp     byte ptr [rcx+29h], 4
0x14004bde3  jb      short loc_14004BDEA
0x14004bde5  mov     dl, sil
0x14004bde8  jmp     short loc_14004BDEC
0x14004bdea  xor     dl, dl
0x14004bdec  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004bdf3  setnz   r8b
0x14004bdf7  test    dl, dl
0x14004bdf9  jnz     short loc_14004BE04
0x14004bdfb  test    r8b, r8b
0x14004bdfe  jz      loc_14004BE96
0x14004be04  mov     r9b, [rbx+3]
0x14004be08  mov     al, [rbx+2]
0x14004be0b  shr     r9b, 2
0x14004be0f  mov     [rsp+0B8h+var_68], rdi
0x14004be14  mov     byte ptr [rsp+0B8h+var_70], r9b
0x14004be19  mov     r9, [rcx+40h]
0x14004be1d  mov     rcx, [rcx+18h]
0x14004be21  shr     al, 2
0x14004be24  mov     byte ptr [rsp+0B8h+var_78], al
0x14004be28  mov     word ptr [rsp+0B8h+var_88], 0A5h
0x14004be2f  call    WPP_RECORDER_AND_TRACE_SF_avdtp_seidavdtp_seidq
0x14004be34  jmp     short loc_14004BE96
0x14004be36  mov     rcx, cs:WPP_GLOBAL_Control
0x14004be3d  cmp     rcx, r14
0x14004be40  jz      short loc_14004BE55
0x14004be42  mov     eax, [rcx+2Ch]
0x14004be45  test    bpl, al
0x14004be48  jz      short loc_14004BE55
0x14004be4a  cmp     byte ptr [rcx+29h], 4
0x14004be4e  jb      short loc_14004BE55
0x14004be50  mov     dl, sil
0x14004be53  jmp     short loc_14004BE57
0x14004be55  xor     dl, dl
0x14004be57  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14004be5e  setnz   r8b
0x14004be62  test    dl, dl
0x14004be64  jnz     short loc_14004BE6B
0x14004be66  test    r8b, r8b
0x14004be69  jz      short loc_14004BE96
0x14004be6b  mov     r9b, [rbx+3]
0x14004be6f  mov     al, [rbx+2]
0x14004be72  shr     r9b, 2
0x14004be76  mov     byte ptr [rsp+0B8h+var_70], r9b
0x14004be7b  mov     r9, [rcx+40h]
0x14004be7f  mov     rcx, [rcx+18h]
0x14004be83  shr     al, 2
0x14004be86  mov     byte ptr [rsp+0B8h+var_78], al
0x14004be8a  mov     word ptr [rsp+0B8h+var_88], 0A6h
0x14004be91  call    WPP_RECORDER_AND_TRACE_SF_avdtp_seidavdtp_seid
0x14004be96  mov     dl, [rbx+2]
0x14004be99  lea     r8, [rsp+0B8h+arg_8]; enum TAG_AvdtpSepState *
0x14004bea1  xor     ebp, ebp
0x14004bea3  shr     dl, 2; unsigned __int8
0x14004bea6  mov     rcx, rdi; this
0x14004bea9  mov     [rsp+0B8h+arg_8], ebp
0x14004beb0  call    ?FindEndpointIndexByLocalSeid_AndReturnState@Avdtp_impl@@AEAAKEAEAW4TAG_AvdtpSepState@@@Z; Avdtp_impl::FindEndpointIndexByLocalSeid_AndReturnState(uchar,TAG_AvdtpSepState &)
0x14004beb5  lea     r15, [rbx+4]
0x14004beb9  movzx   edx, byte ptr [r15]
0x14004bebd  sub     edx, 1
0x14004bec0  jz      short loc_14004BF32
0x14004bec2  sub     edx, 1
0x14004bec5  jz      short loc_14004BF1C
0x14004bec7  sub     edx, 1
0x14004beca  jz      short loc_14004BF06
0x14004becc  sub     edx, 1
0x14004becf  jz      short loc_14004BF48
0x14004bed1  sub     edx, 1
0x14004bed4  jz      short loc_14004BEF0
0x14004bed6  sub     edx, 1
0x14004bed9  jz      short loc_14004BF48
0x14004bedb  cmp     edx, 1
0x14004bede  jz      short loc_14004BF48
0x14004bee0  mov     r8b, [rbx+2]
0x14004bee4  mov     r9b, 17h
0x14004bee7  shr     r8b, 2
0x14004beeb  jmp     loc_14004BDB2
0x14004bef0  cmp     [rbx+5], sil
0x14004bef4  jz      short loc_14004BF48
0x14004bef6  mov     r8b, [rbx+2]
0x14004befa  mov     r9b, 26h ; '&'
0x14004befd  shr     r8b, 2
0x14004bf01  jmp     loc_14004BDB2
0x14004bf06  cmp     byte ptr [rbx+5], 3
0x14004bf0a  jz      short loc_14004BF48
0x14004bf0c  mov     r8b, [rbx+2]
0x14004bf10  mov     r9b, 25h ; '%'
0x14004bf13  shr     r8b, 2
0x14004bf17  jmp     loc_14004BDB2
0x14004bf1c  cmp     [rbx+5], bpl
0x14004bf20  jz      short loc_14004BF48
0x14004bf22  mov     r8b, [rbx+2]
0x14004bf26  mov     r9b, 18h
0x14004bf29  shr     r8b, 2
0x14004bf2d  jmp     loc_14004BDB2
0x14004bf32  cmp     [rbx+5], bpl
0x14004bf36  jz      short loc_14004BF48
0x14004bf38  mov     r8b, [rbx+2]
0x14004bf3c  mov     r9b, 23h ; '#'
0x14004bf3f  shr     r8b, 2
0x14004bf43  jmp     loc_14004BDB2
0x14004bf48  cmp     eax, 4
0x14004bf4b  jnz     short loc_14004BF5D
0x14004bf4d  mov     r8b, [rbx+2]
0x14004bf51  mov     r9b, 12h
0x14004bf54  shr     r8b, 2
0x14004bf58  jmp     loc_14004BDB2
0x14004bf5d  cmp     [rsp+0B8h+arg_8], ebp
0x14004bf64  jbe     short loc_14004BF76
0x14004bf66  mov     r8b, [rbx+2]
0x14004bf6a  mov     r9b, 13h
0x14004bf6d  shr     r8b, 2
0x14004bf71  jmp     loc_14004BDB2
0x14004bf76  lea     rbp, [rdi+640h]
0x14004bf7d  mov     rcx, rbp; SpinLock
  ... truncated ...
```
