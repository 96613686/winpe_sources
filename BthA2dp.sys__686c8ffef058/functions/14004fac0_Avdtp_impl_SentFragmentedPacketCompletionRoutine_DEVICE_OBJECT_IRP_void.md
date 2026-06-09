# Avdtp_impl::SentFragmentedPacketCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14004fac0`
- end: `0x14004fdb6`
- name: `?SentFragmentedPacketCompletionRoutine@Avdtp_impl@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `758`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140019340`
- `0x14001e240`
- `0x14002d890`
- `0x14004fac0`
- `0x140056cb4`
- `0x140056e38`
- `0x14005ce00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004fc88`
- `ntoskrnl!ExAllocatePool2` at `0x14004fc88`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fd51`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fd93`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fd51`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004fd93`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004fd13`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004fd13`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004fcf4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004fcf4`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::SentFragmentedPacketCompletionRoutine(
        struct _DEVICE_OBJECT *a1,
        struct _IRP *a2,
        _DWORD *a3,
        __int64 a4)
{
  int v6; // edx
  int v7; // r8d
  int v8; // eax
  int v9; // edi
  int v10; // ecx
  BOOL v11; // r14d
  int v12; // ebx
  unsigned int v13; // r15d
  unsigned int v14; // edi
  unsigned int v15; // ebx
  unsigned int v16; // r13d
  __int64 Pool2; // rax
  _BYTE *v18; // r12
  char *v19; // rdx
  char v20; // al
  __int64 v21; // rbx
  KIRQL v22; // al
  void *v23; // rdi
  char v25; // [rsp+D8h] [rbp+10h] BYREF

  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(a1, a2, a3, a4) )
  {
    LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qavdtp_txnidLLDDDq(
        WPP_GLOBAL_Control->AttachedDevice,
        v6,
        v7,
        WPP_GLOBAL_Control->DeviceExtension);
    }
  }
  else
  {
    LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qavdtp_txnidLLDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        v6,
        v7,
        WPP_GLOBAL_Control->DeviceExtension);
    }
  }
  a3[7] += a3[8];
  ++a3[5];
  v8 = a3[7];
  v9 = a3[6];
  v10 = a3[5];
  a3[8] = 0;
  v11 = v9 == v8 && v10 == a3[4];
  if ( !a2 )
  {
    v12 = -1073741802;
LABEL_32:
    if ( (unsigned __int8)((a3[2] & 3) - 2) <= 1u )
      Avdtp_impl::AtomicRetrieveAndClearCmdInfo(
        *(Avdtp_impl **)a3,
        *((unsigned __int8 *)a3 + 8) >> 4,
        (union Avdtp_impl::CmdInfoWithSeids *)&v25,
        0);
    ExFreePoolWithTag(a3, 0x41564454u);
    return (unsigned int)v12;
  }
  v12 = 0;
  if ( v11 )
    goto LABEL_32;
  v13 = a3[3];
  v14 = v9 - v8;
  v15 = v14;
  if ( v13 <= v14 )
    v15 = a3[3];
  v16 = v15 + 2;
  Pool2 = ExAllocatePool2(64, v15 + 2, 1096172628);
  v18 = (_BYTE *)Pool2;
  if ( !Pool2 )
  {
    v12 = -1073741670;
    goto LABEL_32;
  }
  v19 = (char *)a3 + (unsigned int)a3[7] + 40;
  v20 = *(_BYTE *)(Pool2 + 1);
  *v18 = a3[2] & 0xF3 | (v14 < v13 ? 12 : 8);
  v18[1] = v20 ^ (*((_BYTE *)a3 + 9) ^ v20) & 0x3F;
  memmove(v18 + 2, v19, v15);
  a3[8] = v15;
  v21 = *(_QWORD *)a3;
  v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(*(_QWORD *)a3 + 1600LL));
  v23 = *(void **)(*(_QWORD *)a3 + 1432LL);
  KeReleaseSpinLock((PKSPIN_LOCK)(v21 + 1600), v22);
  v12 = Avdtp_impl::L2capWrite(
          *(BTH_ADDR **)a3,
          v23,
          v18,
          v16,
          (int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *))Avdtp_impl::SentFragmentedPacketCompletionRoutine,
          a3);
  if ( v12 < 0 )
    v11 = 1;
  ExFreePoolWithTag(v18, 0x41564454u);
  if ( v11 )
    goto LABEL_32;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14004fac0  push    rbx
0x14004fac2  push    rbp
0x14004fac3  push    rsi
0x14004fac4  push    rdi
0x14004fac5  push    r12
0x14004fac7  push    r13
0x14004fac9  push    r14
0x14004facb  push    r15
0x14004facd  sub     rsp, 88h
0x14004fad4  mov     rsi, r8
0x14004fad7  mov     rbx, rdx
0x14004fada  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14004fadf  test    eax, eax
0x14004fae1  jz      loc_14004FB8E
0x14004fae7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004faee  lea     rax, WPP_GLOBAL_Control
0x14004faf5  mov     ebp, 1
0x14004fafa  cmp     rcx, rax
0x14004fafd  jz      short loc_14004FB11
0x14004faff  mov     eax, [rcx+2Ch]
0x14004fb02  test    al, 8
0x14004fb04  jz      short loc_14004FB11
0x14004fb06  cmp     byte ptr [rcx+29h], 4
0x14004fb0a  jb      short loc_14004FB11
0x14004fb0c  mov     dl, bpl
0x14004fb0f  jmp     short loc_14004FB13
0x14004fb11  xor     dl, dl
0x14004fb13  lea     rax, WPP_RECORDER_INITIALIZED
0x14004fb1a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004fb21  setnz   r8b
0x14004fb25  test    dl, dl
0x14004fb27  jnz     short loc_14004FB32
0x14004fb29  test    r8b, r8b
0x14004fb2c  jz      loc_14004FC24
0x14004fb32  mov     rax, [rsi]
0x14004fb35  movzx   r11d, byte ptr [rsi+8]
0x14004fb3a  movzx   r9d, byte ptr [rsi+9]
0x14004fb3f  mov     r10d, r11d
0x14004fb42  mov     [rsp+0C8h+var_50], rax
0x14004fb47  and     r9d, 3Fh
0x14004fb4b  mov     eax, [rsi+20h]
0x14004fb4e  and     r10d, 3
0x14004fb52  mov     [rsp+0C8h+var_58], eax
0x14004fb56  mov     eax, [rsi+1Ch]
0x14004fb59  mov     [rsp+0C8h+var_60], eax
0x14004fb5d  mov     eax, [rsi+18h]
0x14004fb60  mov     [rsp+0C8h+var_68], eax
0x14004fb64  mov     [rsp+0C8h+var_70], r10d
0x14004fb69  mov     [rsp+0C8h+var_78], r9d
0x14004fb6e  mov     r9, [rcx+40h]
0x14004fb72  mov     rcx, [rcx+18h]
0x14004fb76  shr     r11d, 4
0x14004fb7a  mov     [rsp+0C8h+var_80], r11d
0x14004fb7f  mov     [rsp+0C8h+var_88], rsi
0x14004fb84  call    WPP_RECORDER_AND_TRACE_SF_qavdtp_txnidLLDDDq
0x14004fb89  jmp     loc_14004FC24
0x14004fb8e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fb95  lea     rax, WPP_GLOBAL_Control
0x14004fb9c  mov     ebp, 1
0x14004fba1  cmp     rcx, rax
0x14004fba4  jz      short loc_14004FBB8
0x14004fba6  mov     eax, [rcx+2Ch]
0x14004fba9  test    al, 8
0x14004fbab  jz      short loc_14004FBB8
0x14004fbad  cmp     byte ptr [rcx+29h], 4
0x14004fbb1  jb      short loc_14004FBB8
0x14004fbb3  mov     dl, bpl
0x14004fbb6  jmp     short loc_14004FBBA
0x14004fbb8  xor     dl, dl
0x14004fbba  lea     rax, WPP_RECORDER_INITIALIZED
0x14004fbc1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004fbc8  setnz   r8b
0x14004fbcc  test    dl, dl
0x14004fbce  jnz     short loc_14004FBD5
0x14004fbd0  test    r8b, r8b
0x14004fbd3  jz      short loc_14004FC24
0x14004fbd5  movzx   r11d, byte ptr [rsi+8]
0x14004fbda  mov     eax, [rsi+20h]
0x14004fbdd  mov     r10d, r11d
0x14004fbe0  movzx   r9d, byte ptr [rsi+9]
0x14004fbe5  and     r10d, 3
0x14004fbe9  mov     [rsp+0C8h+var_58], eax
0x14004fbed  and     r9d, 3Fh
0x14004fbf1  mov     eax, [rsi+1Ch]
0x14004fbf4  mov     [rsp+0C8h+var_60], eax
0x14004fbf8  mov     eax, [rsi+18h]
0x14004fbfb  mov     [rsp+0C8h+var_68], eax
0x14004fbff  mov     [rsp+0C8h+var_70], r10d
0x14004fc04  mov     [rsp+0C8h+var_78], r9d
0x14004fc09  mov     r9, [rcx+40h]
0x14004fc0d  mov     rcx, [rcx+18h]
0x14004fc11  shr     r11d, 4
0x14004fc15  mov     [rsp+0C8h+var_80], r11d
0x14004fc1a  mov     [rsp+0C8h+var_88], rsi
0x14004fc1f  call    WPP_RECORDER_AND_TRACE_SF_qavdtp_txnidLLDDD
0x14004fc24  mov     eax, [rsi+20h]
0x14004fc27  add     [rsi+1Ch], eax
0x14004fc2a  add     [rsi+14h], ebp
0x14004fc2d  mov     eax, [rsi+1Ch]
0x14004fc30  mov     edi, [rsi+18h]
0x14004fc33  mov     ecx, [rsi+14h]
0x14004fc36  mov     dword ptr [rsi+20h], 0
0x14004fc3d  cmp     edi, eax
0x14004fc3f  jnz     short loc_14004FC4B
0x14004fc41  cmp     ecx, [rsi+10h]
0x14004fc44  jnz     short loc_14004FC4B
0x14004fc46  mov     r14d, ebp
0x14004fc49  jmp     short loc_14004FC4E
0x14004fc4b  xor     r14d, r14d
0x14004fc4e  test    rbx, rbx
0x14004fc51  jnz     short loc_14004FC5D
0x14004fc53  mov     ebx, 0C0000016h
0x14004fc58  jmp     loc_14004FD62
0x14004fc5d  xor     ebx, ebx
0x14004fc5f  test    r14d, r14d
0x14004fc62  jnz     loc_14004FD62
0x14004fc68  mov     r15d, [rsi+0Ch]
0x14004fc6c  lea     ecx, [r14+40h]
0x14004fc70  sub     edi, eax
0x14004fc72  mov     r8d, 41564454h
0x14004fc78  cmp     r15d, edi
0x14004fc7b  mov     ebx, edi
0x14004fc7d  cmovbe  ebx, r15d
0x14004fc81  lea     r13d, [rbx+2]
0x14004fc85  mov     edx, r13d
0x14004fc88  call    cs:__imp_ExAllocatePool2
0x14004fc8f  nop     dword ptr [rax+rax+00h]
0x14004fc94  mov     r12, rax
0x14004fc97  test    rax, rax
0x14004fc9a  jnz     short loc_14004FCA6
0x14004fc9c  mov     ebx, 0C000009Ah
0x14004fca1  jmp     loc_14004FD62
0x14004fca6  mov     al, [rsi+8]
0x14004fca9  cmp     edi, r15d
0x14004fcac  mov     edx, [rsi+1Ch]
0x14004fcaf  sbb     cl, cl
0x14004fcb1  mov     r8d, ebx; Size
0x14004fcb4  and     cl, 4
0x14004fcb7  and     al, 0F3h
0x14004fcb9  add     cl, 8
0x14004fcbc  add     rdx, 28h ; '('
0x14004fcc0  or      cl, al
0x14004fcc2  add     rdx, rsi; Src
0x14004fcc5  mov     al, [r12+1]
0x14004fcca  mov     [r12], cl
0x14004fcce  mov     cl, al
0x14004fcd0  xor     cl, [rsi+9]
0x14004fcd3  and     cl, 3Fh
0x14004fcd6  xor     cl, al
0x14004fcd8  mov     [r12+1], cl
0x14004fcdd  lea     rcx, [r12+2]; void *
0x14004fce2  call    memmove
0x14004fce7  mov     [rsi+20h], ebx
0x14004fcea  mov     rbx, [rsi]
0x14004fced  lea     rcx, [rbx+640h]; SpinLock
0x14004fcf4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004fcfb  nop     dword ptr [rax+rax+00h]
0x14004fd00  mov     rdx, [rsi]
0x14004fd03  lea     rcx, [rbx+640h]; SpinLock
0x14004fd0a  mov     rdi, [rdx+598h]
0x14004fd11  mov     dl, al; NewIrql
0x14004fd13  call    cs:__imp_KeReleaseSpinLock
0x14004fd1a  nop     dword ptr [rax+rax+00h]
0x14004fd1f  mov     rcx, [rsi]; this
0x14004fd22  lea     rax, ?SentFragmentedPacketCompletionRoutine@Avdtp_impl@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; Avdtp_impl::SentFragmentedPacketCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x14004fd29  mov     [rsp+0C8h+var_A0], rsi; void *
0x14004fd2e  mov     r9d, r13d; unsigned int
0x14004fd31  mov     r8, r12; void *
0x14004fd34  mov     [rsp+0C8h+var_A8], rax; int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *)
0x14004fd39  mov     rdx, rdi; void *
0x14004fd3c  call    ?L2capWrite@Avdtp_impl@@AEAAJPEAX0KP6AJPEAU_DEVICE_OBJECT@@PEAU_IRP@@0@Z0@Z; Avdtp_impl::L2capWrite(void *,void *,ulong,long (*)(_DEVICE_OBJECT *,_IRP *,void *),void *)
0x14004fd41  test    eax, eax
0x14004fd43  mov     edx, 41564454h; Tag
0x14004fd48  mov     rcx, r12; P
0x14004fd4b  mov     ebx, eax
0x14004fd4d  cmovs   r14d, ebp
0x14004fd51  call    cs:__imp_ExFreePoolWithTag
0x14004fd58  nop     dword ptr [rax+rax+00h]
0x14004fd5d  test    r14d, r14d
0x14004fd60  jz      short loc_14004FD9F
0x14004fd62  movzx   eax, byte ptr [rsi+8]
0x14004fd66  mov     cl, al
0x14004fd68  and     cl, 3
0x14004fd6b  sub     cl, 2
0x14004fd6e  cmp     cl, bpl
0x14004fd71  ja      short loc_14004FD8B
0x14004fd73  mov     rcx, [rsi]; this
0x14004fd76  lea     r8, [rsp+0C8h+arg_8]; union Avdtp_impl::CmdInfoWithSeids *
0x14004fd7e  mov     edx, eax
0x14004fd80  xor     r9d, r9d; bool
0x14004fd83  shr     edx, 4; int
0x14004fd86  call    ?AtomicRetrieveAndClearCmdInfo@Avdtp_impl@@AEAAXJAEATCmdInfoWithSeids@1@_N@Z; Avdtp_impl::AtomicRetrieveAndClearCmdInfo(long,Avdtp_impl::CmdInfoWithSeids &,bool)
0x14004fd8b  mov     edx, 41564454h; Tag
0x14004fd90  mov     rcx, rsi; P
0x14004fd93  call    cs:__imp_ExFreePoolWithTag
0x14004fd9a  nop     dword ptr [rax+rax+00h]
0x14004fd9f  mov     eax, ebx
0x14004fda1  add     rsp, 88h
0x14004fda8  pop     r15
0x14004fdaa  pop     r14
0x14004fdac  pop     r13
0x14004fdae  pop     r12
0x14004fdb0  pop     rdi
0x14004fdb1  pop     rsi
0x14004fdb2  pop     rbp
0x14004fdb3  pop     rbx
0x14004fdb4  retn
```
