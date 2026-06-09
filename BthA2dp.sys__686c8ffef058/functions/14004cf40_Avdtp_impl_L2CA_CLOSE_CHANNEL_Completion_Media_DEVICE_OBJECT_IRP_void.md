# Avdtp_impl::L2CA_CLOSE_CHANNEL_Completion_Media(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14004cf40`
- end: `0x14004d1a4`
- name: `?L2CA_CLOSE_CHANNEL_Completion_Media@Avdtp_impl@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `612`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000f6e4`
- `0x14002d890`
- `0x140048fe0`
- `0x14004cf40`
- `0x1400502f0`
- `0x140055d20`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004cf65`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004cf65`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004d0ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004d176`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004d0ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004d176`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004d0ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004d13e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004d0ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004d13e`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::L2CA_CLOSE_CHANNEL_Completion_Media(
        struct _DEVICE_OBJECT *a1,
        struct _IRP *a2,
        unsigned int *a3)
{
  __int64 v3; // rdi
  __int64 v5; // r12
  unsigned int v6; // r15d
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  PIO_SECURITY_CONTEXT SecurityContext; // rbx
  int v12; // edx
  int v13; // r8d
  int v14; // esi
  KIRQL v15; // al
  __int64 v16; // rbx
  KIRQL v17; // r14
  __int64 v18; // r8
  KIRQL v19; // si
  int v20; // ebx

  v3 = *(_QWORD *)a3;
  v5 = a3[2];
  v6 = a3[4];
  ExFreePoolWithTag(a3, 0x41564430u);
  if ( a2 )
  {
    SecurityContext = a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
    if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v8, v7, v9, v10) )
    {
      v14 = 1;
      LOBYTE(v12) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_ddqq(
          WPP_GLOBAL_Control->AttachedDevice,
          v12,
          v13,
          WPP_GLOBAL_Control->DeviceExtension);
      }
    }
    else
    {
      v14 = 1;
      LOBYTE(v12) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_llq(
          WPP_GLOBAL_Control->AttachedDevice,
          v12,
          v13,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          4,
          263,
          (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
          a2->IoStatus.Status,
          HIDWORD(SecurityContext[1].SecurityQos),
          (char)SecurityContext[5].SecurityQos);
      }
    }
    if ( !SecurityContext || a2->IoStatus.Status || HIDWORD(SecurityContext[1].SecurityQos) )
      v14 = 0;
    v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 1600));
    v16 = *(_QWORD *)(v3 + 1144);
    v17 = v15;
    if ( v16 )
      (*(void (__fastcall **)(_QWORD))(v3 + 1168))(*(_QWORD *)(v3 + 1144));
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 1600), v17);
    if ( v16 )
    {
      if ( v6 )
      {
        LOBYTE(v18) = v14 == 0 ? 0x31 : 0;
        (*(void (__fastcall **)(__int64, __int64, __int64))(v3 + 1360))(v3, v16, v18);
      }
      else
      {
        (*(void (__fastcall **)(__int64, __int64))(v3 + 1392))(v3, v16);
      }
      (*(void (__fastcall **)(__int64))(v3 + 1176))(v16);
    }
    v19 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 1600));
    if ( v6 )
      Avdtp_impl::tagSepInfo::SetState(v3 + 200 * v5 + 216, 0);
    v20 = *(_DWORD *)(v3 + 144);
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 1600), v19);
    if ( v20 == 7 )
      Avdtp_impl::Disconnect_Req((Avdtp_impl *)v3);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x14004cf40  push    rbx
0x14004cf42  push    rbp
0x14004cf43  push    rsi
0x14004cf44  push    rdi
0x14004cf45  push    r12
0x14004cf47  push    r14
0x14004cf49  push    r15
0x14004cf4b  sub     rsp, 60h
0x14004cf4f  mov     rdi, [r8]
0x14004cf52  mov     rbp, rdx
0x14004cf55  mov     r12d, [r8+8]
0x14004cf59  mov     edx, 41564430h; Tag
0x14004cf5e  mov     r15d, [r8+10h]
0x14004cf62  mov     rcx, r8; P
0x14004cf65  call    cs:__imp_ExFreePoolWithTag
0x14004cf6c  nop     dword ptr [rax+rax+00h]
0x14004cf71  test    rbp, rbp
0x14004cf74  jz      loc_14004D18F
0x14004cf7a  mov     rax, [rbp+0B8h]
0x14004cf81  mov     rbx, [rax+8]
0x14004cf85  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14004cf8a  test    eax, eax
0x14004cf8c  jz      loc_14004D012
0x14004cf92  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cf99  lea     rax, WPP_GLOBAL_Control
0x14004cfa0  mov     esi, 1
0x14004cfa5  cmp     rcx, rax
0x14004cfa8  jz      short loc_14004CFBC
0x14004cfaa  mov     eax, [rcx+2Ch]
0x14004cfad  test    al, 8
0x14004cfaf  jz      short loc_14004CFBC
0x14004cfb1  cmp     byte ptr [rcx+29h], 4
0x14004cfb5  jb      short loc_14004CFBC
0x14004cfb7  mov     dl, sil
0x14004cfba  jmp     short loc_14004CFBE
0x14004cfbc  xor     dl, dl
0x14004cfbe  lea     rax, WPP_RECORDER_INITIALIZED
0x14004cfc5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004cfcc  setnz   r8b
0x14004cfd0  test    dl, dl
0x14004cfd2  jnz     short loc_14004CFDD
0x14004cfd4  test    r8b, r8b
0x14004cfd7  jz      loc_14004D09D
0x14004cfdd  mov     rax, [rbx+78h]
0x14004cfe1  mov     r9, [rcx+40h]
0x14004cfe5  mov     rcx, [rcx+18h]
0x14004cfe9  mov     [rsp+98h+var_40], rdi
0x14004cfee  mov     [rsp+98h+var_48], rax
0x14004cff3  mov     eax, [rbx+1Ch]
0x14004cff6  mov     [rsp+98h+var_50], eax
0x14004cffa  mov     eax, [rbp+30h]
0x14004cffd  mov     [rsp+98h+var_58], eax
0x14004d001  mov     [rsp+98h+var_68], 106h
0x14004d008  call    WPP_RECORDER_AND_TRACE_SF_ddqq
0x14004d00d  jmp     loc_14004D09D
0x14004d012  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d019  lea     rax, WPP_GLOBAL_Control
0x14004d020  mov     esi, 1
0x14004d025  cmp     rcx, rax
0x14004d028  jz      short loc_14004D03C
0x14004d02a  mov     eax, [rcx+2Ch]
0x14004d02d  test    al, 8
0x14004d02f  jz      short loc_14004D03C
0x14004d031  cmp     byte ptr [rcx+29h], 4
0x14004d035  jb      short loc_14004D03C
0x14004d037  mov     dl, sil
0x14004d03a  jmp     short loc_14004D03E
0x14004d03c  xor     dl, dl
0x14004d03e  lea     rax, WPP_RECORDER_INITIALIZED
0x14004d045  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004d04c  setnz   r8b
0x14004d050  test    dl, dl
0x14004d052  jnz     short loc_14004D059
0x14004d054  test    r8b, r8b
0x14004d057  jz      short loc_14004D09D
0x14004d059  mov     rax, [rbx+78h]
0x14004d05d  mov     r9, [rcx+40h]
0x14004d061  mov     rcx, [rcx+18h]
0x14004d065  mov     [rsp+98h+var_48], rax
0x14004d06a  mov     eax, [rbx+1Ch]
0x14004d06d  mov     [rsp+98h+var_50], eax
0x14004d071  mov     eax, [rbp+30h]
0x14004d074  mov     [rsp+98h+var_58], eax
0x14004d078  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004d07f  mov     [rsp+98h+var_60], rax
0x14004d084  mov     [rsp+98h+var_68], 107h
0x14004d08b  mov     [rsp+98h+var_70], 4
0x14004d093  mov     [rsp+98h+var_78], 4
0x14004d098  call    WPP_RECORDER_AND_TRACE_SF_llq
0x14004d09d  test    rbx, rbx
0x14004d0a0  jz      short loc_14004D0AE
0x14004d0a2  cmp     dword ptr [rbp+30h], 0
0x14004d0a6  jnz     short loc_14004D0AE
0x14004d0a8  cmp     dword ptr [rbx+1Ch], 0
0x14004d0ac  jz      short loc_14004D0B0
0x14004d0ae  xor     esi, esi
0x14004d0b0  lea     rbp, [rdi+640h]
0x14004d0b7  mov     rcx, rbp; SpinLock
0x14004d0ba  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004d0c1  nop     dword ptr [rax+rax+00h]
0x14004d0c6  mov     rbx, [rdi+478h]
0x14004d0cd  mov     r14b, al
0x14004d0d0  test    rbx, rbx
0x14004d0d3  jz      short loc_14004D0E4
0x14004d0d5  mov     rax, [rdi+490h]
0x14004d0dc  mov     rcx, rbx
0x14004d0df  call    _guard_dispatch_icall
0x14004d0e4  mov     dl, r14b; NewIrql
0x14004d0e7  mov     rcx, rbp; SpinLock
0x14004d0ea  call    cs:__imp_KeReleaseSpinLock
0x14004d0f1  nop     dword ptr [rax+rax+00h]
0x14004d0f6  test    rbx, rbx
0x14004d0f9  jz      short loc_14004D13B
0x14004d0fb  mov     rdx, rbx
0x14004d0fe  mov     rcx, rdi
0x14004d101  test    r15d, r15d
0x14004d104  jz      short loc_14004D120
0x14004d106  mov     rax, [rdi+550h]
0x14004d10d  neg     esi
0x14004d10f  sbb     r8b, r8b
0x14004d112  not     r8b
0x14004d115  and     r8b, 31h
0x14004d119  call    _guard_dispatch_icall
0x14004d11e  jmp     short loc_14004D12C
0x14004d120  mov     rax, [rdi+570h]
0x14004d127  call    _guard_dispatch_icall
0x14004d12c  mov     rax, [rdi+498h]
0x14004d133  mov     rcx, rbx
0x14004d136  call    _guard_dispatch_icall
0x14004d13b  mov     rcx, rbp; SpinLock
0x14004d13e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004d145  nop     dword ptr [rax+rax+00h]
0x14004d14a  mov     sil, al
0x14004d14d  test    r15d, r15d
0x14004d150  jz      short loc_14004D16A
0x14004d152  imul    rcx, r12, 0C8h
0x14004d159  xor     edx, edx
0x14004d15b  add     rcx, 0D8h
0x14004d162  add     rcx, rdi
0x14004d165  call    ?SetState@tagSepInfo@Avdtp_impl@@QEAAXW4TAG_AvdtpSepState@@@Z; Avdtp_impl::tagSepInfo::SetState(TAG_AvdtpSepState)
0x14004d16a  mov     ebx, [rdi+90h]
0x14004d170  mov     dl, sil; NewIrql
0x14004d173  mov     rcx, rbp; SpinLock
0x14004d176  call    cs:__imp_KeReleaseSpinLock
0x14004d17d  nop     dword ptr [rax+rax+00h]
0x14004d182  cmp     ebx, 7
0x14004d185  jnz     short loc_14004D18F
0x14004d187  mov     rcx, rdi; this
0x14004d18a  call    ?Disconnect_Req@Avdtp_impl@@CAJPEAX@Z; Avdtp_impl::Disconnect_Req(void *)
0x14004d18f  mov     eax, 0C0000016h
0x14004d194  add     rsp, 60h
0x14004d198  pop     r15
0x14004d19a  pop     r14
0x14004d19c  pop     r12
0x14004d19e  pop     rdi
0x14004d19f  pop     rsi
0x14004d1a0  pop     rbp
0x14004d1a1  pop     rbx
0x14004d1a2  retn
```
