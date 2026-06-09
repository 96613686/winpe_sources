# Avdtp_impl::Open_Rsp(long,void *,uchar)

- ea: `0x14004e420`
- end: `0x14004e5f5`
- name: `?Open_Rsp@Avdtp_impl@@CAJJPEAXE@Z`
- size: `469`
- prototype: `static int(int, void *, unsigned __int8)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004b260`

## callees

- `0x140006a88`
- `0x140016d48`
- `0x14002d890`
- `0x14004980c`
- `0x14004e420`
- `0x1400502f0`
- `0x140052804`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14004e5d9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004e5d9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004e5a9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004e5a9`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::Open_Rsp(__int64 a1, KSPIN_LOCK *a2, __int64 a3, __int64 a4)
{
  char v4; // bl
  __int64 v6; // rdi
  int v7; // edx
  int v8; // r8d
  __int64 EndpointIndexByLocalSeid; // rbx
  KIRQL v11; // di
  char v12; // [rsp+78h] [rbp+10h] BYREF
  __int16 v13; // [rsp+79h] [rbp+11h]
  signed __int32 v14; // [rsp+88h] [rbp+20h]

  v4 = a3;
  v6 = (int)a1;
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(a1, a2, a3, a4) )
  {
    LOBYTE(v7) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_Dq(
        WPP_GLOBAL_Control->AttachedDevice,
        v7,
        v8,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        4,
        116,
        (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
        v4,
        a2);
    }
  }
  else
  {
    LOBYTE(v7) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_L(WPP_GLOBAL_Control->AttachedDevice, v7, v8, WPP_GLOBAL_Control->DeviceExtension, 4);
    }
  }
  if ( !a2 )
    return 3221225485LL;
  v13 = 0;
  if ( v4 )
  {
    v12 = 3;
    HIBYTE(v13) = v4;
  }
  else
  {
    v12 = 2;
  }
  v14 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + v6 + 418, 0, 0);
  Avdtp_impl::CompleteHeaderAndSendSignal(
    (Avdtp_impl *)a2,
    (struct _SINGLE_PCK_CMD *)&v12,
    0,
    (unsigned int)v6,
    6,
    v12 & 3,
    (v4 != 0) + 2LL);
  if ( !v4 )
  {
    EndpointIndexByLocalSeid = Avdtp_impl::FindEndpointIndexByLocalSeid((Avdtp_impl *)a2, BYTE1(v14));
    v11 = KeAcquireSpinLockRaiseToDpc(a2 + 200);
    Avdtp_impl::tagSepInfo::SetState(&a2[25 * EndpointIndexByLocalSeid + 27], 3);
    KeReleaseSpinLock(a2 + 200, v11);
  }
  return 0;
}

```

## disassembly

```asm
0x14004e420  mov     [rsp+arg_0], rbx
0x14004e425  push    rbp
0x14004e426  push    rsi
0x14004e427  push    rdi
0x14004e428  sub     rsp, 50h
0x14004e42c  movzx   ebx, r8b
0x14004e430  mov     rbp, rdx
0x14004e433  movsxd  rdi, ecx
0x14004e436  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14004e43b  test    eax, eax
0x14004e43d  jz      short loc_14004E4BC
0x14004e43f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e446  lea     rax, WPP_GLOBAL_Control
0x14004e44d  cmp     rcx, rax
0x14004e450  jz      short loc_14004E463
0x14004e452  mov     eax, [rcx+2Ch]
0x14004e455  test    al, 8
0x14004e457  jz      short loc_14004E463
0x14004e459  cmp     byte ptr [rcx+29h], 4
0x14004e45d  jb      short loc_14004E463
0x14004e45f  mov     dl, 1
0x14004e461  jmp     short loc_14004E465
0x14004e463  xor     dl, dl
0x14004e465  lea     rax, WPP_RECORDER_INITIALIZED
0x14004e46c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004e473  setnz   r8b
0x14004e477  test    dl, dl
0x14004e479  jnz     short loc_14004E484
0x14004e47b  test    r8b, r8b
0x14004e47e  jz      loc_14004E51A
0x14004e484  mov     r9, [rcx+40h]
0x14004e488  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004e48f  mov     rcx, [rcx+18h]
0x14004e493  mov     [rsp+68h+var_20], rbp
0x14004e498  mov     [rsp+68h+var_28], ebx
0x14004e49c  mov     [rsp+68h+var_30], rax
0x14004e4a1  mov     word ptr [rsp+68h+var_38], 74h ; 't'
0x14004e4a8  mov     dword ptr [rsp+68h+var_40], 4
0x14004e4b0  mov     [rsp+68h+var_48], 4
0x14004e4b5  call    WPP_RECORDER_AND_TRACE_SF_Dq
0x14004e4ba  jmp     short loc_14004E51A
0x14004e4bc  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e4c3  lea     rax, WPP_GLOBAL_Control
0x14004e4ca  cmp     rcx, rax
0x14004e4cd  jz      short loc_14004E4E0
0x14004e4cf  mov     eax, [rcx+2Ch]
0x14004e4d2  test    al, 8
0x14004e4d4  jz      short loc_14004E4E0
0x14004e4d6  cmp     byte ptr [rcx+29h], 4
0x14004e4da  jb      short loc_14004E4E0
0x14004e4dc  mov     dl, 1
0x14004e4de  jmp     short loc_14004E4E2
0x14004e4e0  xor     dl, dl
0x14004e4e2  lea     rax, WPP_RECORDER_INITIALIZED
0x14004e4e9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004e4f0  setnz   r8b
0x14004e4f4  test    dl, dl
0x14004e4f6  jnz     short loc_14004E4FD
0x14004e4f8  test    r8b, r8b
0x14004e4fb  jz      short loc_14004E51A
0x14004e4fd  mov     r9, [rcx+40h]
0x14004e501  mov     rcx, [rcx+18h]
0x14004e505  mov     [rsp+68h+var_28], ebx
0x14004e509  mov     word ptr [rsp+68h+var_38], 75h ; 'u'
0x14004e510  mov     [rsp+68h+var_48], 4
0x14004e515  call    WPP_RECORDER_AND_TRACE_SF_L
0x14004e51a  test    rbp, rbp
0x14004e51d  jnz     short loc_14004E529
0x14004e51f  mov     eax, 0C000000Dh
0x14004e524  jmp     loc_14004E5E7
0x14004e529  xor     eax, eax
0x14004e52b  mov     [rsp+68h+arg_9], ax
0x14004e530  test    bl, bl
0x14004e532  jnz     short loc_14004E53B
0x14004e534  mov     [rsp+68h+arg_8], 2
0x14004e539  jmp     short loc_14004E544
0x14004e53b  mov     [rsp+68h+arg_8], 3
0x14004e540  mov     byte ptr [rsp+68h+arg_9+1], bl
0x14004e544  xor     r8d, r8d
0x14004e547  test    bl, bl
0x14004e549  setnz   r8b
0x14004e54d  add     r8, 2
0x14004e551  xor     ecx, ecx
0x14004e553  lock cmpxchg [rbp+rdi*4+688h], ecx
0x14004e55c  mov     [rsp+68h+var_38], r8; unsigned __int64
0x14004e561  lea     rdx, [rsp+68h+arg_8]; struct _SINGLE_PCK_CMD *
0x14004e566  mov     [rsp+68h+arg_18], eax
0x14004e56d  mov     r9d, edi; int
0x14004e570  mov     al, [rsp+68h+arg_8]
0x14004e574  xor     r8d, r8d; unsigned __int8
0x14004e577  and     al, 3
0x14004e579  mov     rcx, rbp; this
0x14004e57c  mov     [rsp+68h+var_40], al; unsigned __int8
0x14004e580  mov     [rsp+68h+var_48], 6; char
0x14004e585  call    ?CompleteHeaderAndSendSignal@Avdtp_impl@@AEAAXPEAU_SINGLE_PCK_CMD@@EJEE_K@Z; Avdtp_impl::CompleteHeaderAndSendSignal(_SINGLE_PCK_CMD *,uchar,long,uchar,uchar,unsigned __int64)
0x14004e58a  test    bl, bl
0x14004e58c  jnz     short loc_14004E5E5
0x14004e58e  mov     dl, byte ptr [rsp+68h+arg_18+1]; unsigned __int8
0x14004e595  mov     rcx, rbp; this
0x14004e598  call    ?FindEndpointIndexByLocalSeid@Avdtp_impl@@AEAAKE@Z; Avdtp_impl::FindEndpointIndexByLocalSeid(uchar)
0x14004e59d  lea     rsi, [rbp+640h]
0x14004e5a4  mov     ebx, eax
0x14004e5a6  mov     rcx, rsi; SpinLock
0x14004e5a9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004e5b0  nop     dword ptr [rax+rax+00h]
0x14004e5b5  imul    rcx, rbx, 0C8h
0x14004e5bc  mov     edx, 3
0x14004e5c1  mov     dil, al
0x14004e5c4  add     rcx, 0D8h
0x14004e5cb  add     rcx, rbp
0x14004e5ce  call    ?SetState@tagSepInfo@Avdtp_impl@@QEAAXW4TAG_AvdtpSepState@@@Z; Avdtp_impl::tagSepInfo::SetState(TAG_AvdtpSepState)
0x14004e5d3  mov     dl, dil; NewIrql
0x14004e5d6  mov     rcx, rsi; SpinLock
0x14004e5d9  call    cs:__imp_KeReleaseSpinLock
0x14004e5e0  nop     dword ptr [rax+rax+00h]
0x14004e5e5  xor     eax, eax
0x14004e5e7  mov     rbx, [rsp+68h+arg_0]
0x14004e5ec  add     rsp, 50h
0x14004e5f0  pop     rdi
0x14004e5f1  pop     rsi
0x14004e5f2  pop     rbp
0x14004e5f3  retn
```
