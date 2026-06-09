# Avdtp_impl::HandlePacket_OPEN(bool,long,_SINGLE_PCK_CMD const *,ulong,uchar)

- ea: `0x14004b260`
- end: `0x14004b72a`
- name: `?HandlePacket_OPEN@Avdtp_impl@@AEAAX_NJPEBU_SINGLE_PCK_CMD@@KE@Z`
- size: `1226`
- prototype: `void __usercall(Avdtp_impl *__hidden this@<rcx>, bool@<dl>, int@<r8d>, const struct _SINGLE_PCK_CMD *@<r9>, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x14004e5fc`

## callees

- `0x140003530`
- `0x14000e690`
- `0x14000f570`
- `0x140010628`
- `0x14002d890`
- `0x140036494`
- `0x14003b244`
- `0x1400471ec`
- `0x140049938`
- `0x14004b260`
- `0x14004e420`
- `0x140056048`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14004b579`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004b5d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004b67c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004b6d0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004b579`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004b5d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004b67c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004b6d0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b527`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b5a9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b64c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b6a0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b527`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b5a9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b64c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004b6a0`

## pseudocode

```c
void __fastcall Avdtp_impl::HandlePacket_OPEN(
        KSPIN_LOCK *this,
        __int64 a2,
        __int64 a3,
        const struct _SINGLE_PCK_CMD *a4,
        unsigned int a5,
        unsigned __int8 a6)
{
  unsigned int v7; // r13d
  __int64 v9; // rdx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  char v13; // di
  int IfrRecorderLog; // eax
  __int64 v15; // r11
  int v16; // edx
  int v17; // r8d
  int v18; // r8d
  __int64 *v19; // rdx
  __int64 *v20; // rdx
  unsigned __int8 v21; // r8
  KIRQL v22; // al
  __int64 v23; // r8
  __int64 v24; // r9
  unsigned int v25; // ebp
  KIRQL v26; // r12
  const struct _SINGLE_PCK_CMD *v27; // rdx
  __int64 v28; // r14
  int v29; // r14d
  KIRQL v30; // al
  KSPIN_LOCK v31; // rdi
  KIRQL v32; // si
  __int64 v33; // r9
  unsigned int EndpointIndexByRemoteSeid; // eax
  KIRQL v35; // al
  KIRQL v36; // bp
  __int64 v37; // r8
  KIRQL v38; // al
  KIRQL v39; // bp
  char v40; // [rsp+A8h] [rbp+10h]

  v40 = a2;
  v7 = a3;
  if ( (unsigned int)Feature_60817472__private_IsEnabledDeviceUsageNoInline(this, a2, a3, a4) )
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
      WPP_RECORDER_AND_TRACE_SF_dq(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v11,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        4,
        195,
        (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
        a5,
        (char)this);
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
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v11,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        4,
        196,
        (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
        a5);
  }
  if ( !v40 )
  {
    if ( (*(_BYTE *)a4 & 3) == 2 )
    {
      EndpointIndexByRemoteSeid = Avdtp_impl::FindEndpointIndexByRemoteSeid((Avdtp_impl *)this, a6);
      if ( (int)Avdtp_impl::BeginConnectingMediaChannel((Avdtp_impl *)this, EndpointIndexByRemoteSeid) >= 0 )
        return;
      v35 = KeAcquireSpinLockRaiseToDpc(this + 200);
      v31 = this[143];
      v36 = v35;
      if ( v31 )
        ((void (__fastcall *)(KSPIN_LOCK))this[146])(this[143]);
      KeReleaseSpinLock(this + 200, v36);
      if ( !v31 )
        return;
      LOBYTE(v37) = 25;
    }
    else
    {
      v38 = KeAcquireSpinLockRaiseToDpc(this + 200);
      v31 = this[143];
      v39 = v38;
      if ( v31 )
        ((void (__fastcall *)(KSPIN_LOCK))this[146])(this[143]);
      KeReleaseSpinLock(this + 200, v39);
      if ( !v31 )
        return;
      LOBYTE(v37) = *((_BYTE *)a4 + 2);
    }
    ((void (__fastcall *)(KSPIN_LOCK *, KSPIN_LOCK, __int64, _QWORD, _DWORD))this[165])(this, v31, v37, 0, 0);
    goto LABEL_70;
  }
  if ( a5 != 3 )
  {
    if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v10, v9, v11, v12) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        v13 = 0;
      }
      if ( v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v20 = WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids;
        LOBYTE(v20) = v13;
        LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v20,
          v18,
          WPP_GLOBAL_Control->DeviceExtension,
          3,
          4,
          197,
          (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
          (char)this);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        v13 = 0;
      }
      if ( v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v19 = WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids;
        LOBYTE(v19) = v13;
        LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v19,
          v18,
          WPP_GLOBAL_Control->DeviceExtension,
          3,
          4,
          198,
          (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids);
      }
    }
    v21 = 17;
    goto LABEL_45;
  }
  v22 = KeAcquireSpinLockRaiseToDpc(this + 200);
  v27 = a4;
  v25 = 0;
  v26 = v22;
  LOBYTE(v27) = *((_BYTE *)a4 + 2) >> 2;
  while ( 1 )
  {
    v28 = 25LL * v25;
    if ( LOBYTE(this[v28 + 28]) == (_BYTE)v27 )
      break;
    if ( ++v25 >= 4 )
    {
      v25 = 4;
      v29 = 0;
      goto LABEL_51;
    }
  }
  Feature_60817472__private_IsEnabledDeviceUsageNoInline(v25, v27, v23, v24);
  v29 = this[v28 + 29];
LABEL_51:
  KeReleaseSpinLock(this + 200, v26);
  if ( v25 == 4 )
  {
    v21 = 18;
LABEL_45:
    Avdtp_impl::Open_Rsp(v7, this, v21);
    return;
  }
  if ( v29 != 1 )
  {
    v21 = v29 == 0 ? 49 : 19;
    goto LABEL_45;
  }
  v30 = KeAcquireSpinLockRaiseToDpc(this + 200);
  v31 = this[143];
  v32 = v30;
  if ( v31 )
    ((void (__fastcall *)(KSPIN_LOCK))this[146])(v31);
  KeReleaseSpinLock(this + 200, v32);
  if ( v31 )
  {
    LOBYTE(v33) = *((_BYTE *)a4 + 2) >> 2;
    ((void (__fastcall *)(_QWORD, KSPIN_LOCK *, KSPIN_LOCK, __int64))this[166])(v7, this, v31, v33);
LABEL_70:
    ((void (__fastcall *)(KSPIN_LOCK))this[147])(v31);
  }
}

```

## disassembly

```asm
0x14004b260  mov     [rsp+arg_0], rbx
0x14004b265  mov     [rsp+arg_18], r9
0x14004b26a  mov     [rsp+arg_8], dl
0x14004b26e  push    rbp
0x14004b26f  push    rsi
0x14004b270  push    rdi
0x14004b271  push    r12
0x14004b273  push    r13
0x14004b275  push    r14
0x14004b277  push    r15
0x14004b279  sub     rsp, 60h
0x14004b27d  mov     r15, r9
0x14004b280  mov     r13d, r8d
0x14004b283  mov     rbx, rcx
0x14004b286  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x14004b28b  mov     r12d, [rsp+98h+arg_20]
0x14004b293  test    eax, eax
0x14004b295  jnz     loc_14004B3A6
0x14004b29b  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14004b2a0  test    eax, eax
0x14004b2a2  jnz     short loc_14004B323
0x14004b2a4  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b2ab  lea     rbp, WPP_GLOBAL_Control
0x14004b2b2  lea     edi, [rax+1]
0x14004b2b5  lea     esi, [rax+4]
0x14004b2b8  cmp     rcx, rbp
0x14004b2bb  jz      short loc_14004B2CF
0x14004b2bd  mov     eax, [rcx+2Ch]
0x14004b2c0  test    al, 8
0x14004b2c2  jz      short loc_14004B2CF
0x14004b2c4  cmp     [rcx+29h], sil
0x14004b2c8  jb      short loc_14004B2CF
0x14004b2ca  mov     dl, dil
0x14004b2cd  jmp     short loc_14004B2D1
0x14004b2cf  xor     dl, dl
0x14004b2d1  lea     r14, WPP_RECORDER_INITIALIZED
0x14004b2d8  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004b2df  setnz   r8b
0x14004b2e3  test    dl, dl
0x14004b2e5  jnz     short loc_14004B2F0
0x14004b2e7  test    r8b, r8b
0x14004b2ea  jz      loc_14004B424
0x14004b2f0  mov     dword ptr [rsp+98h+var_58], r12d
0x14004b2f5  lea     r9, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004b2fc  mov     [rsp+98h+var_60], r9
0x14004b301  mov     r9, [rcx+40h]
0x14004b305  mov     rcx, [rcx+18h]
0x14004b309  mov     [rsp+98h+var_68], 0C4h
0x14004b310  mov     [rsp+98h+var_70], esi
0x14004b314  mov     byte ptr [rsp+98h+var_78], sil
0x14004b319  call    WPP_RECORDER_AND_TRACE_SF_d
0x14004b31e  jmp     loc_14004B424
0x14004b323  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b32a  lea     rbp, WPP_GLOBAL_Control
0x14004b331  mov     edi, 1
0x14004b336  lea     esi, [rdi+3]
0x14004b339  cmp     rcx, rbp
0x14004b33c  jz      short loc_14004B350
0x14004b33e  mov     eax, [rcx+2Ch]
0x14004b341  test    al, 8
0x14004b343  jz      short loc_14004B350
0x14004b345  cmp     [rcx+29h], sil
0x14004b349  jb      short loc_14004B350
0x14004b34b  mov     dl, dil
0x14004b34e  jmp     short loc_14004B352
0x14004b350  xor     dl, dl
0x14004b352  lea     r14, WPP_RECORDER_INITIALIZED
0x14004b359  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004b360  setnz   r8b
0x14004b364  test    dl, dl
0x14004b366  jnz     short loc_14004B371
0x14004b368  test    r8b, r8b
0x14004b36b  jz      loc_14004B424
0x14004b371  mov     [rsp+98h+var_50], rbx
0x14004b376  lea     r9, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004b37d  mov     dword ptr [rsp+98h+var_58], r12d
0x14004b382  mov     [rsp+98h+var_60], r9
0x14004b387  mov     r9, [rcx+40h]
0x14004b38b  mov     rcx, [rcx+18h]
0x14004b38f  mov     [rsp+98h+var_68], 0C3h
0x14004b396  mov     [rsp+98h+var_70], esi
0x14004b39a  mov     byte ptr [rsp+98h+var_78], sil
0x14004b39f  call    WPP_RECORDER_AND_TRACE_SF_dq
0x14004b3a4  jmp     short loc_14004B424
0x14004b3a6  mov     r11, cs:WPP_GLOBAL_Control
0x14004b3ad  lea     rbp, WPP_GLOBAL_Control
0x14004b3b4  mov     edi, 1
0x14004b3b9  lea     esi, [rdi+3]
0x14004b3bc  cmp     r11, rbp
0x14004b3bf  jz      short loc_14004B3D4
0x14004b3c1  mov     eax, [r11+2Ch]
0x14004b3c5  test    al, 8
0x14004b3c7  jz      short loc_14004B3D4
0x14004b3c9  cmp     [r11+29h], sil
0x14004b3cd  jb      short loc_14004B3D4
0x14004b3cf  mov     dl, dil
0x14004b3d2  jmp     short loc_14004B3D6
0x14004b3d4  xor     dl, dl
0x14004b3d6  lea     r14, WPP_RECORDER_INITIALIZED
0x14004b3dd  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004b3e4  setnz   r8b
0x14004b3e8  test    dl, dl
0x14004b3ea  jnz     short loc_14004B3F1
0x14004b3ec  test    r8b, r8b
0x14004b3ef  jz      short loc_14004B424
0x14004b3f1  movzx   r10d, [rsp+98h+arg_8]
0x14004b3fa  mov     rcx, rdi
0x14004b3fd  call    ?GetIfrRecorderLog@@YAPEAURECORDER_LOG__@@W4IfrLogId@@@Z; GetIfrRecorderLog(IfrLogId)
0x14004b402  mov     rcx, [r11+18h]
0x14004b406  mov     r9, rax
0x14004b409  mov     [rsp+98h+var_48], rbx
0x14004b40e  mov     dword ptr [rsp+98h+var_50], r13d
0x14004b413  mov     dword ptr [rsp+98h+var_58], r10d
0x14004b418  mov     [rsp+98h+var_68], 0C2h
0x14004b41f  call    WPP_RECORDER_AND_TRACE_SF_lavdtp_txnidq
0x14004b424  cmp     [rsp+98h+arg_8], 0
0x14004b42c  jz      loc_14004B618
0x14004b432  cmp     r12d, 3
0x14004b436  jz      loc_14004B51D
0x14004b43c  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14004b441  test    eax, eax
0x14004b443  jnz     short loc_14004B4A8
0x14004b445  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b44c  cmp     rcx, rbp
0x14004b44f  jz      short loc_14004B45E
0x14004b451  mov     eax, [rcx+2Ch]
0x14004b454  test    al, 8
0x14004b456  jz      short loc_14004B45E
0x14004b458  cmp     byte ptr [rcx+29h], 3
0x14004b45c  jnb     short loc_14004B461
0x14004b45e  xor     dil, dil
0x14004b461  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004b468  setnz   r8b
0x14004b46c  test    dil, dil
0x14004b46f  jnz     short loc_14004B47A
0x14004b471  test    r8b, r8b
0x14004b474  jz      loc_14004B50A
0x14004b47a  mov     r9, [rcx+40h]
0x14004b47e  lea     rdx, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004b485  mov     rcx, [rcx+18h]
0x14004b489  mov     [rsp+98h+var_60], rdx
0x14004b48e  mov     dl, dil
0x14004b491  mov     [rsp+98h+var_68], 0C6h
0x14004b498  mov     [rsp+98h+var_70], esi
0x14004b49c  mov     byte ptr [rsp+98h+var_78], 3
0x14004b4a1  call    WPP_RECORDER_AND_TRACE_SF_
0x14004b4a6  jmp     short loc_14004B50A
0x14004b4a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b4af  cmp     rcx, rbp
0x14004b4b2  jz      short loc_14004B4C1
0x14004b4b4  mov     eax, [rcx+2Ch]
0x14004b4b7  test    al, 8
0x14004b4b9  jz      short loc_14004B4C1
0x14004b4bb  cmp     byte ptr [rcx+29h], 3
0x14004b4bf  jnb     short loc_14004B4C4
0x14004b4c1  xor     dil, dil
0x14004b4c4  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14004b4cb  setnz   r8b
0x14004b4cf  test    dil, dil
0x14004b4d2  jnz     short loc_14004B4D9
0x14004b4d4  test    r8b, r8b
0x14004b4d7  jz      short loc_14004B50A
0x14004b4d9  mov     r9, [rcx+40h]
0x14004b4dd  lea     rdx, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004b4e4  mov     rcx, [rcx+18h]
0x14004b4e8  mov     [rsp+98h+var_58], rbx
0x14004b4ed  mov     [rsp+98h+var_60], rdx
0x14004b4f2  mov     dl, dil
0x14004b4f5  mov     [rsp+98h+var_68], 0C5h
0x14004b4fc  mov     [rsp+98h+var_70], esi
0x14004b500  mov     byte ptr [rsp+98h+var_78], 3
0x14004b505  call    WPP_RECORDER_AND_TRACE_SF_q
0x14004b50a  mov     r8b, 11h; unsigned __int8
0x14004b50d  mov     rdx, rbx; void *
0x14004b510  mov     ecx, r13d; int
0x14004b513  call    ?Open_Rsp@Avdtp_impl@@CAJJPEAXE@Z; Avdtp_impl::Open_Rsp(long,void *,uchar)
0x14004b518  jmp     loc_14004B711
0x14004b51d  lea     r15, [rbx+640h]
0x14004b524  mov     rcx, r15; SpinLock
0x14004b527  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004b52e  nop     dword ptr [rax+rax+00h]
0x14004b533  mov     rdx, [rsp+98h+arg_18]
0x14004b53b  xor     ebp, ebp
0x14004b53d  mov     r12b, al
0x14004b540  mov     dl, [rdx+2]
0x14004b543  shr     dl, 2
0x14004b546  mov     ecx, ebp
0x14004b548  imul    r14, rcx, 0C8h
0x14004b54f  cmp     [r14+rbx+0E0h], dl
0x14004b557  jz      short loc_14004B566
0x14004b559  add     ebp, edi
0x14004b55b  cmp     ebp, esi
0x14004b55d  jb      short loc_14004B546
0x14004b55f  mov     ebp, esi
0x14004b561  xor     r14d, r14d
0x14004b564  jmp     short loc_14004B573
0x14004b566  call    Feature_60817472__private_IsEnabledDeviceUsageNoInline
0x14004b56b  mov     r14d, [r14+rbx+0E8h]
0x14004b573  mov     dl, r12b; NewIrql
0x14004b576  mov     rcx, r15; SpinLock
0x14004b579  call    cs:__imp_KeReleaseSpinLock
0x14004b580  nop     dword ptr [rax+rax+00h]
0x14004b585  cmp     ebp, esi
0x14004b587  jnz     short loc_14004B591
0x14004b589  mov     r8b, 12h
0x14004b58c  jmp     loc_14004B50D
0x14004b591  cmp     r14d, edi
0x14004b594  jz      short loc_14004B5A6
0x14004b596  sbb     r8b, r8b
0x14004b599  and     r8b, 1Eh
0x14004b59d  add     r8b, 13h
0x14004b5a1  jmp     loc_14004B50D
0x14004b5a6  mov     rcx, r15; SpinLock
0x14004b5a9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004b5b0  nop     dword ptr [rax+rax+00h]
0x14004b5b5  mov     rdi, [rbx+478h]
0x14004b5bc  mov     sil, al
0x14004b5bf  test    rdi, rdi
0x14004b5c2  jz      short loc_14004B5D3
0x14004b5c4  mov     rax, [rbx+490h]
0x14004b5cb  mov     rcx, rdi
0x14004b5ce  call    _guard_dispatch_icall
0x14004b5d3  mov     dl, sil; NewIrql
0x14004b5d6  mov     rcx, r15; SpinLock
0x14004b5d9  call    cs:__imp_KeReleaseSpinLock
0x14004b5e0  nop     dword ptr [rax+rax+00h]
0x14004b5e5  test    rdi, rdi
0x14004b5e8  jz      loc_14004B711
0x14004b5ee  mov     rax, [rsp+98h+arg_18]
0x14004b5f6  mov     r8, rdi
0x14004b5f9  mov     rdx, rbx
0x14004b5fc  mov     ecx, r13d
0x14004b5ff  mov     r9b, [rax+2]
0x14004b603  mov     rax, [rbx+530h]
0x14004b60a  shr     r9b, 2
0x14004b60e  call    _guard_dispatch_icall
0x14004b613  jmp     loc_14004B702
0x14004b618  mov     al, [r15]
0x14004b61b  and     al, 3
0x14004b61d  cmp     al, 2
0x14004b61f  jnz     short loc_14004B696
0x14004b621  mov     dl, [rsp+98h+arg_28]; unsigned __int8
0x14004b628  mov     rcx, rbx; this
0x14004b62b  call    ?FindEndpointIndexByRemoteSeid@Avdtp_impl@@AEAAKE@Z; Avdtp_impl::FindEndpointIndexByRemoteSeid(uchar)
0x14004b630  mov     edx, eax; unsigned int
0x14004b632  mov     rcx, rbx; this
0x14004b635  call    ?BeginConnectingMediaChannel@Avdtp_impl@@AEAAJK@Z; Avdtp_impl::BeginConnectingMediaChannel(ulong)
0x14004b63a  test    eax, eax
0x14004b63c  jns     loc_14004B711
0x14004b642  lea     rsi, [rbx+640h]
0x14004b649  mov     rcx, rsi; SpinLock
0x14004b64c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004b653  nop     dword ptr [rax+rax+00h]
0x14004b658  mov     rdi, [rbx+478h]
0x14004b65f  mov     bpl, al
0x14004b662  test    rdi, rdi
0x14004b665  jz      short loc_14004B676
0x14004b667  mov     rax, [rbx+490h]
0x14004b66e  mov     rcx, rdi
0x14004b671  call    _guard_dispatch_icall
0x14004b676  mov     dl, bpl; NewIrql
0x14004b679  mov     rcx, rsi; SpinLock
0x14004b67c  call    cs:__imp_KeReleaseSpinLock
0x14004b683  nop     dword ptr [rax+rax+00h]
0x14004b688  test    rdi, rdi
0x14004b68b  jz      loc_14004B711
0x14004b691  mov     r8b, 19h
0x14004b694  jmp     short loc_14004B6E5
0x14004b696  lea     rsi, [rbx+640h]
0x14004b69d  mov     rcx, rsi; SpinLock
0x14004b6a0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004b6a7  nop     dword ptr [rax+rax+00h]
0x14004b6ac  mov     rdi, [rbx+478h]
0x14004b6b3  mov     bpl, al
0x14004b6b6  test    rdi, rdi
0x14004b6b9  jz      short loc_14004B6CA
0x14004b6bb  mov     rax, [rbx+490h]
0x14004b6c2  mov     rcx, rdi
0x14004b6c5  call    _guard_dispatch_icall
0x14004b6ca  mov     dl, bpl; NewIrql
0x14004b6cd  mov     rcx, rsi; SpinLock
0x14004b6d0  call    cs:__imp_KeReleaseSpinLock
0x14004b6d7  nop     dword ptr [rax+rax+00h]
0x14004b6dc  test    rdi, rdi
0x14004b6df  jz      short loc_14004B711
0x14004b6e1  mov     r8b, [r15+2]
0x14004b6e5  mov     rax, [rbx+528h]
0x14004b6ec  xor     r9d, r9d
0x14004b6ef  mov     rdx, rdi
0x14004b6f2  mov     [rsp+98h+var_78], 0
0x14004b6fa  mov     rcx, rbx
0x14004b6fd  call    _guard_dispatch_icall
0x14004b702  mov     rax, [rbx+498h]
0x14004b709  mov     rcx, rdi
0x14004b70c  call    _guard_dispatch_icall
0x14004b711  mov     rbx, [rsp+98h+arg_0]
0x14004b719  add     rsp, 60h
0x14004b71d  pop     r15
0x14004b71f  pop     r14
0x14004b721  pop     r13
  ... truncated ...
```
