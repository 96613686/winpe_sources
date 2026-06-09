# Avdtp_impl::ProcessCompletedSignallingPacket(_SINGLE_PCK_CMD const *,ulong)

- ea: `0x14004e5fc`
- end: `0x14004eb5c`
- name: `?ProcessCompletedSignallingPacket@Avdtp_impl@@AEAAXPEBU_SINGLE_PCK_CMD@@K@Z`
- size: `1376`
- prototype: `void __fastcall(KSPIN_LOCK *this, const struct _SINGLE_PCK_CMD *, __int64, __int64)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004edc8`
- `0x14004ef48`

## callees

- `0x14000700c`
- `0x140016f48`
- `0x1400174e0`
- `0x14001e240`
- `0x14002d890`
- `0x14003525c`
- `0x140046c88`
- `0x14004a2d8`
- `0x14004a81c`
- `0x14004ab38`
- `0x14004ad18`
- `0x14004b260`
- `0x14004b730`
- `0x14004bb00`
- `0x14004c1d0`
- `0x14004c654`
- `0x14004ca14`
- `0x14004e5fc`
- `0x14005492c`
- `0x140054d30`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14004e662`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004e865`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004e662`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004e865`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004e632`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004e835`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004e632`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004e835`

## pseudocode

```c
void __fastcall Avdtp_impl::ProcessCompletedSignallingPacket(
        KSPIN_LOCK *this,
        const struct _SINGLE_PCK_CMD *a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v4; // r14d
  KSPIN_LOCK *v7; // r15
  KIRQL v8; // al
  KSPIN_LOCK v9; // rsi
  KIRQL v10; // r12
  char v11; // r12
  char v12; // r15
  char v13; // si
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  PDEVICE_OBJECT v18; // rcx
  int v19; // esi
  unsigned __int8 v20; // al
  KIRQL v21; // al
  KSPIN_LOCK v22; // rdi
  KIRQL v23; // r14
  int v24; // eax
  int v25; // r8d
  int v26; // edx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  int v37; // [rsp+20h] [rbp-40h]
  unsigned int v38; // [rsp+28h] [rbp-38h]
  int v39; // [rsp+30h] [rbp-30h]
  int v40; // [rsp+38h] [rbp-28h]
  char v41; // [rsp+A0h] [rbp+40h]
  char v42; // [rsp+A8h] [rbp+48h] BYREF
  __int16 v43; // [rsp+A9h] [rbp+49h]

  v4 = a3;
  if ( this[178] )
  {
    v7 = this + 200;
    v8 = KeAcquireSpinLockRaiseToDpc(this + 200);
    v9 = this[143];
    v10 = v8;
    if ( v9 )
      ((void (__fastcall *)(KSPIN_LOCK))this[146])(this[143]);
    KeReleaseSpinLock(v7, v10);
    if ( v9 )
    {
      ((void (__fastcall *)(KSPIN_LOCK *, KSPIN_LOCK, const struct _SINGLE_PCK_CMD *, _QWORD))this[178])(
        this,
        v9,
        a2,
        v4);
      ((void (__fastcall *)(KSPIN_LOCK))this[147])(v9);
    }
  }
  v11 = 1;
  v12 = (*(_BYTE *)a2 & 3) == 0;
  v13 = (unsigned __int8)((*(_BYTE *)a2 & 3) - 2) <= 1u;
  v41 = v13;
  IsEnabledDeviceUsageNoInline = Feature_55795972__private_IsEnabledDeviceUsageNoInline(this, a2, a3, a4);
  v17 = 0;
  if ( IsEnabledDeviceUsageNoInline )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || (LOBYTE(v15) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    {
      LOBYTE(v15) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      || (LOBYTE(v16) = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v16) = 0;
    }
    if ( (_BYTE)v15 || (_BYTE)v16 )
      WPP_RECORDER_AND_TRACE_SF_qdq(
        WPP_GLOBAL_Control->AttachedDevice,
        v15,
        v16,
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        4,
        229,
        (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
        (char)a2,
        v4,
        (char)this);
  }
  else
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || (LOBYTE(v15) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    {
      LOBYTE(v15) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
      || (LOBYTE(v16) = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
    {
      LOBYTE(v16) = 0;
    }
    if ( (_BYTE)v15 || (_BYTE)v16 )
      WPP_RECORDER_AND_TRACE_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        v15,
        v16,
        WPP_GLOBAL_Control->DeviceExtension,
        5,
        4,
        230,
        (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids,
        (char)a2,
        v4);
  }
  if ( v13 != v12 )
  {
    v19 = *(unsigned __int8 *)a2 >> 4;
    v42 = 0;
    v43 = 0;
    if ( v41 )
    {
      Avdtp_impl::AtomicRetrieveAndClearCmdInfo((Avdtp_impl *)this, v19, (union Avdtp_impl::CmdInfoWithSeids *)&v42, 1);
      if ( *((_WORD *)this + 568) <= 0x102u && (v20 = *((_BYTE *)a2 + 1), (v20 & 0x3F) == 0) && v20 < 0x40u
        || (*(_BYTE *)a2 & 3) == 1 )
      {
        v21 = KeAcquireSpinLockRaiseToDpc(this + 200);
        v22 = this[143];
        v23 = v21;
        if ( v22 )
          ((void (__fastcall *)(KSPIN_LOCK))this[146])(this[143]);
        KeReleaseSpinLock(this + 200, v23);
        if ( v22 )
        {
          ((void (__fastcall *)(KSPIN_LOCK *, KSPIN_LOCK))this[177])(this, v22);
          ((void (__fastcall *)(KSPIN_LOCK))this[147])(v22);
        }
        return;
      }
      if ( (*((_BYTE *)a2 + 1) & 0x3F) != v42 )
        return;
    }
    else
    {
      v24 = Feature_55795972__private_IsEnabledDeviceUsageNoInline(v18, v15, v16, v17);
      v26 = 0;
      if ( v24 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v11 = 0;
        }
        if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v26) = v11;
          LOBYTE(v25) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_avdtp_txnidLq(
            WPP_GLOBAL_Control->AttachedDevice,
            v26,
            v25,
            WPP_GLOBAL_Control->DeviceExtension,
            v37,
            v38,
            v39,
            v40,
            v19,
            *((_BYTE *)a2 + 1) & 0x3F,
            (char)this);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v11 = 0;
        }
        if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v26) = v11;
          LOBYTE(v25) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_avdtp_txnidL(
            WPP_GLOBAL_Control->AttachedDevice,
            v26,
            v25,
            WPP_GLOBAL_Control->DeviceExtension,
            v37,
            v38,
            v39,
            v40,
            v19,
            *((_BYTE *)a2 + 1) & 0x3F);
        }
      }
      Avdtp_impl::AtomicStoreCmdInfo((Avdtp_impl *)this, v19, a2, v4, 0);
    }
    v27 = *((_BYTE *)a2 + 1) & 0x3F;
    if ( v27 > 7 )
    {
      v33 = v27 - 8;
      if ( !v33 )
      {
        Avdtp_impl::HandlePacket_CLOSE((Avdtp_impl *)this, v12, v19, a2, v4, HIBYTE(v43));
        return;
      }
      v34 = v33 - 1;
      if ( !v34 )
      {
        Avdtp_impl::HandlePacket_SUSPEND((Avdtp_impl *)this, v12, v19, a2, v4);
        return;
      }
      v35 = v34 - 1;
      if ( !v35 )
      {
        Avdtp_impl::HandlePacket_ABORT((Avdtp_impl *)this, v12, v19, a2, v4, HIBYTE(v43));
        return;
      }
      v36 = v35 - 2;
      if ( v36 )
      {
        if ( v36 == 1 )
        {
          Avdtp_impl::HandlePacket_DELAYREPORT((Avdtp_impl *)this, v12, v19, a2, v4);
          return;
        }
LABEL_74:
        Avdtp_impl::HandlePacket_UNKNOWN(
          (Avdtp_impl *)this,
          v12,
          v19,
          (union Avdtp_impl::CmdInfoWithSeids *)&v42,
          a2,
          v38);
        return;
      }
    }
    else
    {
      if ( v27 == 7 )
      {
        Avdtp_impl::HandlePacket_START((Avdtp_impl *)this, v12, v19, a2, v4, HIBYTE(v43));
        return;
      }
      v28 = v27 - 1;
      if ( !v28 )
      {
        Avdtp_impl::HandlePacket_DISCOVER((Avdtp_impl *)this, v12, v19, a2, v4);
        return;
      }
      v29 = v28 - 1;
      if ( v29 )
      {
        v30 = v29 - 1;
        if ( !v30 )
        {
          Avdtp_impl::HandlePacket_SET_CONFIGURATION((Avdtp_impl *)this, v12, v19, a2, v4, v43, HIBYTE(v43));
          return;
        }
        v31 = v30 - 1;
        if ( !v31 )
        {
          Avdtp_impl::HandlePacket_GET_CONFIGURATION((Avdtp_impl *)this, v12, v19, a2, v4);
          return;
        }
        v32 = v31 - 1;
        if ( !v32 )
        {
          Avdtp_impl::HandlePacket_RECONFIGURE((Avdtp_impl *)this, v12, v19, a2, v4);
          return;
        }
        if ( v32 == 1 )
        {
          Avdtp_impl::HandlePacket_OPEN((Avdtp_impl *)this, v12, v19, a2, v4, HIBYTE(v43));
          return;
        }
        goto LABEL_74;
      }
    }
    Avdtp_impl::HandlePacket_GET_CAPABILITIES((Avdtp_impl *)this, v12, v19, a2, v4);
  }
}

```

## disassembly

```asm
0x14004e5fc  mov     [rsp-38h+arg_10], rbx
0x14004e601  push    rbp
0x14004e602  push    rsi
0x14004e603  push    rdi
0x14004e604  push    r12
0x14004e606  push    r13
0x14004e608  push    r14
0x14004e60a  push    r15
0x14004e60c  mov     rbp, rsp
0x14004e60f  sub     rsp, 60h
0x14004e613  xor     r13d, r13d
0x14004e616  mov     r14d, r8d
0x14004e619  mov     rdi, rdx
0x14004e61c  mov     rbx, rcx
0x14004e61f  cmp     [rcx+590h], r13
0x14004e626  jz      short loc_14004E69A
0x14004e628  lea     r15, [rcx+640h]
0x14004e62f  mov     rcx, r15; SpinLock
0x14004e632  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004e639  nop     dword ptr [rax+rax+00h]
0x14004e63e  mov     rsi, [rbx+478h]
0x14004e645  mov     r12b, al
0x14004e648  test    rsi, rsi
0x14004e64b  jz      short loc_14004E65C
0x14004e64d  mov     rax, [rbx+490h]
0x14004e654  mov     rcx, rsi
0x14004e657  call    _guard_dispatch_icall
0x14004e65c  mov     dl, r12b; NewIrql
0x14004e65f  mov     rcx, r15; SpinLock
0x14004e662  call    cs:__imp_KeReleaseSpinLock
0x14004e669  nop     dword ptr [rax+rax+00h]
0x14004e66e  test    rsi, rsi
0x14004e671  jz      short loc_14004E69A
0x14004e673  mov     rax, [rbx+590h]
0x14004e67a  mov     r9d, r14d
0x14004e67d  mov     r8, rdi
0x14004e680  mov     rdx, rsi
0x14004e683  mov     rcx, rbx
0x14004e686  call    _guard_dispatch_icall
0x14004e68b  mov     rax, [rbx+498h]
0x14004e692  mov     rcx, rsi
0x14004e695  call    _guard_dispatch_icall
0x14004e69a  mov     al, [rdi]
0x14004e69c  mov     r12b, 1
0x14004e69f  and     al, 3
0x14004e6a1  setz    r15b
0x14004e6a5  sub     al, 2
0x14004e6a7  cmp     al, r12b
0x14004e6aa  setbe   sil
0x14004e6ae  mov     [rbp+arg_0], sil
0x14004e6b2  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14004e6b7  xor     r9d, r9d
0x14004e6ba  mov     r10d, 4
0x14004e6c0  test    eax, eax
0x14004e6c2  jz      loc_14004E756
0x14004e6c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e6cf  lea     r13, WPP_GLOBAL_Control
0x14004e6d6  cmp     rcx, r13
0x14004e6d9  jz      short loc_14004E6EB
0x14004e6db  mov     eax, [rcx+2Ch]
0x14004e6de  test    al, 8
0x14004e6e0  jz      short loc_14004E6EB
0x14004e6e2  cmp     byte ptr [rcx+29h], 5
0x14004e6e6  mov     dl, r12b
0x14004e6e9  jnb     short loc_14004E6EE
0x14004e6eb  mov     dl, r9b
0x14004e6ee  lea     rax, WPP_RECORDER_INITIALIZED
0x14004e6f5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004e6fc  jz      short loc_14004E708
0x14004e6fe  mov     r8b, r12b
0x14004e701  cmp     [rcx+48h], r9w
0x14004e706  jnz     short loc_14004E70B
0x14004e708  mov     r8b, r9b
0x14004e70b  test    dl, dl
0x14004e70d  jnz     short loc_14004E718
0x14004e70f  test    r8b, r8b
0x14004e712  jz      loc_14004E7D6
0x14004e718  mov     r9, [rcx+40h]
0x14004e71c  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004e723  mov     rcx, [rcx+18h]
0x14004e727  mov     [rsp+60h+var_10], rbx
0x14004e72c  mov     [rsp+60h+var_18], r14d
0x14004e731  mov     [rsp+60h+var_20], rdi
0x14004e736  mov     [rsp+60h+var_28], rax
0x14004e73b  mov     word ptr [rsp+60h+var_30], 0E5h
0x14004e742  mov     dword ptr [rsp+60h+var_38], r10d
0x14004e747  mov     byte ptr [rsp+60h+var_40], 5
0x14004e74c  call    WPP_RECORDER_AND_TRACE_SF_qdq
0x14004e751  jmp     loc_14004E7D6
0x14004e756  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e75d  lea     r13, WPP_GLOBAL_Control
0x14004e764  cmp     rcx, r13
0x14004e767  jz      short loc_14004E779
0x14004e769  mov     eax, [rcx+2Ch]
0x14004e76c  test    al, 8
0x14004e76e  jz      short loc_14004E779
0x14004e770  cmp     byte ptr [rcx+29h], 5
0x14004e774  mov     dl, r12b
0x14004e777  jnb     short loc_14004E77C
0x14004e779  mov     dl, r9b
0x14004e77c  lea     rax, WPP_RECORDER_INITIALIZED
0x14004e783  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004e78a  jz      short loc_14004E796
0x14004e78c  mov     r8b, r12b
0x14004e78f  cmp     [rcx+48h], r9w
0x14004e794  jnz     short loc_14004E799
0x14004e796  mov     r8b, r9b
0x14004e799  test    dl, dl
0x14004e79b  jnz     short loc_14004E7A2
0x14004e79d  test    r8b, r8b
0x14004e7a0  jz      short loc_14004E7D6
0x14004e7a2  mov     r9, [rcx+40h]
0x14004e7a6  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004e7ad  mov     rcx, [rcx+18h]
0x14004e7b1  mov     [rsp+60h+var_18], r14d
0x14004e7b6  mov     [rsp+60h+var_20], rdi
0x14004e7bb  mov     [rsp+60h+var_28], rax
0x14004e7c0  mov     word ptr [rsp+60h+var_30], 0E6h
0x14004e7c7  mov     dword ptr [rsp+60h+var_38], r10d; unsigned int
0x14004e7cc  mov     byte ptr [rsp+60h+var_40], 5
0x14004e7d1  call    WPP_RECORDER_AND_TRACE_SF_qD
0x14004e7d6  cmp     sil, r15b
0x14004e7d9  jz      loc_14004EB43
0x14004e7df  movzx   esi, byte ptr [rdi]
0x14004e7e2  xor     eax, eax
0x14004e7e4  shr     esi, 4
0x14004e7e7  mov     [rbp+arg_8], 0
0x14004e7eb  mov     [rbp+arg_9], ax
0x14004e7ef  cmp     [rbp+arg_0], al
0x14004e7f2  jz      loc_14004E8B3
0x14004e7f8  mov     r9b, r12b; bool
0x14004e7fb  lea     r8, [rbp+arg_8]; union Avdtp_impl::CmdInfoWithSeids *
0x14004e7ff  mov     edx, esi; int
0x14004e801  mov     rcx, rbx; this
0x14004e804  call    ?AtomicRetrieveAndClearCmdInfo@Avdtp_impl@@AEAAXJAEATCmdInfoWithSeids@1@_N@Z; Avdtp_impl::AtomicRetrieveAndClearCmdInfo(long,Avdtp_impl::CmdInfoWithSeids &,bool)
0x14004e809  mov     ecx, 102h
0x14004e80e  cmp     [rbx+470h], cx
0x14004e815  ja      short loc_14004E822
0x14004e817  mov     al, [rdi+1]
0x14004e81a  test    al, 3Fh
0x14004e81c  jnz     short loc_14004E822
0x14004e81e  cmp     al, 40h ; '@'
0x14004e820  jb      short loc_14004E82B
0x14004e822  mov     al, [rdi]
0x14004e824  and     al, 3
0x14004e826  cmp     al, r12b
0x14004e829  jnz     short loc_14004E8A0
0x14004e82b  lea     rsi, [rbx+640h]
0x14004e832  mov     rcx, rsi; SpinLock
0x14004e835  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004e83c  nop     dword ptr [rax+rax+00h]
0x14004e841  mov     rdi, [rbx+478h]
0x14004e848  mov     r14b, al
0x14004e84b  test    rdi, rdi
0x14004e84e  jz      short loc_14004E85F
0x14004e850  mov     rax, [rbx+490h]
0x14004e857  mov     rcx, rdi
0x14004e85a  call    _guard_dispatch_icall
0x14004e85f  mov     dl, r14b; NewIrql
0x14004e862  mov     rcx, rsi; SpinLock
0x14004e865  call    cs:__imp_KeReleaseSpinLock
0x14004e86c  nop     dword ptr [rax+rax+00h]
0x14004e871  test    rdi, rdi
0x14004e874  jz      loc_14004EB43
0x14004e87a  mov     rax, [rbx+588h]
0x14004e881  mov     rdx, rdi
0x14004e884  mov     rcx, rbx
0x14004e887  call    _guard_dispatch_icall
0x14004e88c  mov     rax, [rbx+498h]
0x14004e893  mov     rcx, rdi
0x14004e896  call    _guard_dispatch_icall
0x14004e89b  jmp     loc_14004EB43
0x14004e8a0  mov     al, [rdi+1]
0x14004e8a3  and     al, 3Fh
0x14004e8a5  cmp     al, [rbp+arg_8]
0x14004e8a8  jnz     loc_14004EB43
0x14004e8ae  jmp     loc_14004E988
0x14004e8b3  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14004e8b8  xor     edx, edx
0x14004e8ba  test    eax, eax
0x14004e8bc  jz      short loc_14004E91C
0x14004e8be  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e8c5  cmp     rcx, r13
0x14004e8c8  jz      short loc_14004E8D7
0x14004e8ca  mov     eax, [rcx+2Ch]
0x14004e8cd  test    al, 8
0x14004e8cf  jz      short loc_14004E8D7
0x14004e8d1  cmp     byte ptr [rcx+29h], 4
0x14004e8d5  jnb     short loc_14004E8DA
0x14004e8d7  mov     r12b, dl
0x14004e8da  lea     rax, WPP_RECORDER_INITIALIZED
0x14004e8e1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004e8e8  setnz   r8b
0x14004e8ec  test    r12b, r12b
0x14004e8ef  jnz     short loc_14004E8F6
0x14004e8f1  test    r8b, r8b
0x14004e8f4  jz      short loc_14004E973
0x14004e8f6  movzx   eax, byte ptr [rdi+1]
0x14004e8fa  mov     dl, r12b
0x14004e8fd  mov     r9, [rcx+40h]
0x14004e901  and     eax, 3Fh
0x14004e904  mov     rcx, [rcx+18h]
0x14004e908  mov     [rsp+60h+var_10], rbx
0x14004e90d  mov     [rsp+60h+var_18], eax
0x14004e911  mov     dword ptr [rsp+60h+var_20], esi
0x14004e915  call    WPP_RECORDER_AND_TRACE_SF_avdtp_txnidLq
0x14004e91a  jmp     short loc_14004E973
0x14004e91c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e923  cmp     rcx, r13
0x14004e926  jz      short loc_14004E935
0x14004e928  mov     eax, [rcx+2Ch]
0x14004e92b  test    al, 8
0x14004e92d  jz      short loc_14004E935
0x14004e92f  cmp     byte ptr [rcx+29h], 4
0x14004e933  jnb     short loc_14004E938
0x14004e935  mov     r12b, dl
0x14004e938  lea     rax, WPP_RECORDER_INITIALIZED
0x14004e93f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004e946  setnz   r8b
0x14004e94a  test    r12b, r12b
0x14004e94d  jnz     short loc_14004E954
0x14004e94f  test    r8b, r8b
0x14004e952  jz      short loc_14004E973
0x14004e954  movzx   eax, byte ptr [rdi+1]
0x14004e958  mov     dl, r12b
0x14004e95b  mov     r9, [rcx+40h]
0x14004e95f  and     eax, 3Fh
0x14004e962  mov     rcx, [rcx+18h]
0x14004e966  mov     [rsp+60h+var_18], eax
0x14004e96a  mov     dword ptr [rsp+60h+var_20], esi
0x14004e96e  call    WPP_RECORDER_AND_TRACE_SF_avdtp_txnidL
0x14004e973  mov     r9d, r14d; unsigned int
0x14004e976  mov     byte ptr [rsp+60h+var_40], 0; bool
0x14004e97b  mov     r8, rdi; struct _SINGLE_PCK_CMD *
0x14004e97e  mov     edx, esi; int
0x14004e980  mov     rcx, rbx; this
0x14004e983  call    ?AtomicStoreCmdInfo@Avdtp_impl@@AEAAXJPEBU_SINGLE_PCK_CMD@@K_N@Z; Avdtp_impl::AtomicStoreCmdInfo(long,_SINGLE_PCK_CMD const *,ulong,bool)
0x14004e988  movzx   ecx, byte ptr [rdi+1]
0x14004e98c  and     ecx, 3Fh
0x14004e98f  cmp     ecx, 7
0x14004e992  ja      loc_14004EA86
0x14004e998  jz      loc_14004EA64
0x14004e99e  sub     ecx, 1
0x14004e9a1  jz      loc_14004EA49
0x14004e9a7  sub     ecx, 1
0x14004e9aa  jz      loc_14004EAD7
0x14004e9b0  sub     ecx, 1
0x14004e9b3  jz      short loc_14004EA20
0x14004e9b5  sub     ecx, 1
0x14004e9b8  jz      short loc_14004EA05
0x14004e9ba  sub     ecx, 1
0x14004e9bd  jz      short loc_14004E9EA
0x14004e9bf  cmp     ecx, 1
0x14004e9c2  jnz     loc_14004EAA3
0x14004e9c8  mov     al, byte ptr [rbp+arg_9+1]
0x14004e9cb  mov     r9, rdi; struct _SINGLE_PCK_CMD *
0x14004e9ce  mov     [rsp+60h+var_38], al; unsigned __int8
0x14004e9d2  mov     r8d, esi; int
0x14004e9d5  mov     dl, r15b; bool
0x14004e9d8  mov     dword ptr [rsp+60h+var_40], r14d; unsigned int
0x14004e9dd  mov     rcx, rbx; this
0x14004e9e0  call    ?HandlePacket_OPEN@Avdtp_impl@@AEAAX_NJPEBU_SINGLE_PCK_CMD@@KE@Z; Avdtp_impl::HandlePacket_OPEN(bool,long,_SINGLE_PCK_CMD const *,ulong,uchar)
0x14004e9e5  jmp     loc_14004EB43
0x14004e9ea  mov     r9, rdi; struct _SINGLE_PCK_CMD *
0x14004e9ed  mov     dword ptr [rsp+60h+var_40], r14d; unsigned int
0x14004e9f2  mov     r8d, esi; int
0x14004e9f5  mov     dl, r15b; bool
0x14004e9f8  mov     rcx, rbx; this
0x14004e9fb  call    ?HandlePacket_RECONFIGURE@Avdtp_impl@@AEAAX_NJPEBU_SINGLE_PCK_CMD@@K@Z; Avdtp_impl::HandlePacket_RECONFIGURE(bool,long,_SINGLE_PCK_CMD const *,ulong)
0x14004ea00  jmp     loc_14004EB43
0x14004ea05  mov     r9, rdi; struct _SINGLE_PCK_CMD *
0x14004ea08  mov     dword ptr [rsp+60h+var_40], r14d; unsigned int
0x14004ea0d  mov     r8d, esi; int
0x14004ea10  mov     dl, r15b; bool
0x14004ea13  mov     rcx, rbx; this
0x14004ea16  call    ?HandlePacket_GET_CONFIGURATION@Avdtp_impl@@AEAAX_NJPEBU_SINGLE_PCK_CMD@@K@Z; Avdtp_impl::HandlePacket_GET_CONFIGURATION(bool,long,_SINGLE_PCK_CMD const *,ulong)
0x14004ea1b  jmp     loc_14004EB43
0x14004ea20  mov     al, byte ptr [rbp+arg_9+1]
0x14004ea23  mov     r9, rdi; struct _SINGLE_PCK_CMD *
0x14004ea26  mov     [rsp+60h+var_30], al; unsigned __int8
0x14004ea2a  mov     r8d, esi; int
0x14004ea2d  mov     al, byte ptr [rbp+arg_9]
0x14004ea30  mov     dl, r15b; bool
0x14004ea33  mov     [rsp+60h+var_38], al; unsigned __int8
0x14004ea37  mov     rcx, rbx; this
0x14004ea3a  mov     dword ptr [rsp+60h+var_40], r14d; unsigned int
0x14004ea3f  call    ?HandlePacket_SET_CONFIGURATION@Avdtp_impl@@AEAAX_NJPEBU_SINGLE_PCK_CMD@@KEE@Z; Avdtp_impl::HandlePacket_SET_CONFIGURATION(bool,long,_SINGLE_PCK_CMD const *,ulong,uchar,uchar)
0x14004ea44  jmp     loc_14004EB43
0x14004ea49  mov     r9, rdi; struct _SINGLE_PCK_CMD *
0x14004ea4c  mov     dword ptr [rsp+60h+var_40], r14d; unsigned int
0x14004ea51  mov     r8d, esi; int
0x14004ea54  mov     dl, r15b; bool
0x14004ea57  mov     rcx, rbx; this
0x14004ea5a  call    ?HandlePacket_DISCOVER@Avdtp_impl@@AEAAX_NJPEBU_SINGLE_PCK_CMD@@K@Z; Avdtp_impl::HandlePacket_DISCOVER(bool,long,_SINGLE_PCK_CMD const *,ulong)
0x14004ea5f  jmp     loc_14004EB43
0x14004ea64  mov     al, byte ptr [rbp+arg_9+1]
0x14004ea67  mov     r9, rdi; struct _SINGLE_PCK_CMD *
0x14004ea6a  mov     [rsp+60h+var_38], al; unsigned __int8
0x14004ea6e  mov     r8d, esi; int
0x14004ea71  mov     dl, r15b; bool
  ... truncated ...
```
