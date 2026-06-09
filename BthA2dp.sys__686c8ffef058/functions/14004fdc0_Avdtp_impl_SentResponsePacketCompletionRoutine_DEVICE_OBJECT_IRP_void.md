# Avdtp_impl::SentResponsePacketCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14004fdc0`
- end: `0x14004ff88`
- name: `?SentResponsePacketCompletionRoutine@Avdtp_impl@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `456`
- prototype: `static int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000f570`
- `0x14001e240`
- `0x14002d890`
- `0x14004fdc0`
- `0x140056bb0`
- `0x140056fec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004ff6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ff6b`

## pseudocode

```c
__int64 __fastcall Avdtp_impl::SentResponsePacketCompletionRoutine(
        struct _DEVICE_OBJECT *a1,
        struct _IRP *a2,
        Avdtp_impl **a3,
        __int64 a4)
{
  Avdtp_impl **v4; // rdi
  struct _IRP *v5; // r14
  PDEVICE_OBJECT v6; // rcx
  char v7; // bl
  unsigned __int8 v8; // si
  unsigned __int8 v9; // bp
  unsigned int v10; // r14d
  int v11; // edx
  int v12; // r8d
  int v13; // edx
  int v15; // [rsp+20h] [rbp-88h]
  int v16; // [rsp+28h] [rbp-80h]
  int v17; // [rsp+30h] [rbp-78h]
  int v18; // [rsp+38h] [rbp-70h]
  char v19; // [rsp+B8h] [rbp+10h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = WPP_GLOBAL_Control;
  v7 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      (_DWORD)a3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      241,
      (__int64)WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids);
  v8 = *((_BYTE *)v4 + 8) >> 4;
  v9 = *((_BYTE *)v4 + 9) & 0x3F;
  if ( v5 )
  {
    v10 = 0;
    Avdtp_impl::AtomicRetrieveAndClearCmdInfo(*v4, v8, (union Avdtp_impl::CmdInfoWithSeids *)&v19, 0);
  }
  else
  {
    v10 = -1073741802;
  }
  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(v6, a2, a3, a4) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v7 = 0;
    }
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = v9;
      LOBYTE(v13) = v7;
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qavdtp_txnidLLq(
        WPP_GLOBAL_Control->AttachedDevice,
        v13,
        v12,
        WPP_GLOBAL_Control->DeviceExtension,
        v15,
        v16,
        v17,
        v18,
        (char)v4,
        v8,
        v9,
        (_BYTE)v4[1] & 3,
        (char)*v4);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v7 = 0;
    }
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = v7;
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qavdtp_txnidLL(
        WPP_GLOBAL_Control->AttachedDevice,
        v11,
        v12,
        WPP_GLOBAL_Control->DeviceExtension,
        v15,
        v16,
        v17,
        v18,
        (char)v4,
        v8,
        v9,
        (_BYTE)v4[1] & 3);
    }
  }
  ExFreePoolWithTag(v4, 0x41564431u);
  return v10;
}

```

## disassembly

```asm
0x14004fdc0  push    rbx
0x14004fdc2  push    rbp
0x14004fdc3  push    rsi
0x14004fdc4  push    rdi
0x14004fdc5  push    r13
0x14004fdc7  push    r14
0x14004fdc9  sub     rsp, 78h
0x14004fdcd  mov     rdi, r8
0x14004fdd0  mov     r14, rdx
0x14004fdd3  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fdda  lea     r13, WPP_GLOBAL_Control
0x14004fde1  mov     bl, 1
0x14004fde3  cmp     rcx, r13
0x14004fde6  jz      short loc_14004FDF9
0x14004fde8  mov     eax, [rcx+2Ch]
0x14004fdeb  test    al, 8
0x14004fded  jz      short loc_14004FDF9
0x14004fdef  cmp     byte ptr [rcx+29h], 4
0x14004fdf3  jb      short loc_14004FDF9
0x14004fdf5  mov     dl, bl
0x14004fdf7  jmp     short loc_14004FDFB
0x14004fdf9  xor     dl, dl
0x14004fdfb  lea     rax, WPP_RECORDER_INITIALIZED
0x14004fe02  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004fe09  setnz   r8b
0x14004fe0d  test    dl, dl
0x14004fe0f  jnz     short loc_14004FE16
0x14004fe11  test    r8b, r8b
0x14004fe14  jz      short loc_14004FE43
0x14004fe16  mov     r9, [rcx+40h]
0x14004fe1a  lea     rax, WPP_f66c76ca5e8c389f36f2c17712ccaac8_Traceguids
0x14004fe21  mov     rcx, [rcx+18h]
0x14004fe25  mov     [rsp+0A8h+var_70], rax
0x14004fe2a  mov     [rsp+0A8h+var_78], 0F1h
0x14004fe31  mov     [rsp+0A8h+var_80], 4
0x14004fe39  mov     [rsp+0A8h+var_88], 4
0x14004fe3e  call    WPP_RECORDER_AND_TRACE_SF_
0x14004fe43  mov     sil, [rdi+8]
0x14004fe47  mov     bpl, [rdi+9]
0x14004fe4b  shr     sil, 4
0x14004fe4f  and     bpl, 3Fh
0x14004fe53  test    r14, r14
0x14004fe56  jnz     short loc_14004FE60
0x14004fe58  mov     r14d, 0C0000016h
0x14004fe5e  jmp     short loc_14004FE7A
0x14004fe60  mov     rcx, [rdi]; this
0x14004fe63  lea     r8, [rsp+0A8h+arg_8]; union Avdtp_impl::CmdInfoWithSeids *
0x14004fe6b  xor     r14d, r14d
0x14004fe6e  movzx   edx, sil; int
0x14004fe72  xor     r9d, r9d; bool
0x14004fe75  call    ?AtomicRetrieveAndClearCmdInfo@Avdtp_impl@@AEAAXJAEATCmdInfoWithSeids@1@_N@Z; Avdtp_impl::AtomicRetrieveAndClearCmdInfo(long,Avdtp_impl::CmdInfoWithSeids &,bool)
0x14004fe7a  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14004fe7f  test    eax, eax
0x14004fe81  jz      short loc_14004FEFA
0x14004fe83  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fe8a  cmp     rcx, r13
0x14004fe8d  jz      short loc_14004FE9C
0x14004fe8f  mov     eax, [rcx+2Ch]
0x14004fe92  test    al, 8
0x14004fe94  jz      short loc_14004FE9C
0x14004fe96  cmp     byte ptr [rcx+29h], 4
0x14004fe9a  jnb     short loc_14004FE9E
0x14004fe9c  xor     bl, bl
0x14004fe9e  lea     rax, WPP_RECORDER_INITIALIZED
0x14004fea5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004feac  setnz   r8b
0x14004feb0  test    bl, bl
0x14004feb2  jnz     short loc_14004FEBD
0x14004feb4  test    r8b, r8b
0x14004feb7  jz      loc_14004FF63
0x14004febd  movzx   r10d, byte ptr [rdi+8]
0x14004fec2  mov     rax, [rdi]
0x14004fec5  and     r10d, 3
0x14004fec9  mov     [rsp+0A8h+var_48], rax
0x14004fece  mov     [rsp+0A8h+var_50], r10d
0x14004fed3  movzx   edx, bpl
0x14004fed7  mov     [rsp+0A8h+var_58], edx
0x14004fedb  mov     dl, bl
0x14004fedd  movzx   r9d, sil
0x14004fee1  mov     [rsp+0A8h+var_60], r9d
0x14004fee6  mov     r9, [rcx+40h]
0x14004feea  mov     rcx, [rcx+18h]
0x14004feee  mov     [rsp+0A8h+var_68], rdi
0x14004fef3  call    WPP_RECORDER_AND_TRACE_SF_qavdtp_txnidLLq
0x14004fef8  jmp     short loc_14004FF63
0x14004fefa  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ff01  cmp     rcx, r13
0x14004ff04  jz      short loc_14004FF13
0x14004ff06  mov     eax, [rcx+2Ch]
0x14004ff09  test    al, 8
0x14004ff0b  jz      short loc_14004FF13
0x14004ff0d  cmp     byte ptr [rcx+29h], 4
0x14004ff11  jnb     short loc_14004FF15
0x14004ff13  xor     bl, bl
0x14004ff15  lea     rax, WPP_RECORDER_INITIALIZED
0x14004ff1c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004ff23  setnz   r8b
0x14004ff27  test    bl, bl
0x14004ff29  jnz     short loc_14004FF30
0x14004ff2b  test    r8b, r8b
0x14004ff2e  jz      short loc_14004FF63
0x14004ff30  movzx   r10d, byte ptr [rdi+8]
0x14004ff35  mov     dl, bl
0x14004ff37  and     r10d, 3
0x14004ff3b  movzx   eax, bpl
0x14004ff3f  mov     [rsp+0A8h+var_50], r10d
0x14004ff44  mov     [rsp+0A8h+var_58], eax
0x14004ff48  movzx   r9d, sil
0x14004ff4c  mov     [rsp+0A8h+var_60], r9d
0x14004ff51  mov     r9, [rcx+40h]
0x14004ff55  mov     rcx, [rcx+18h]
0x14004ff59  mov     [rsp+0A8h+var_68], rdi
0x14004ff5e  call    WPP_RECORDER_AND_TRACE_SF_qavdtp_txnidLL
0x14004ff63  mov     edx, 41564431h; Tag
0x14004ff68  mov     rcx, rdi; P
0x14004ff6b  call    cs:__imp_ExFreePoolWithTag
0x14004ff72  nop     dword ptr [rax+rax+00h]
0x14004ff77  mov     eax, r14d
0x14004ff7a  add     rsp, 78h
0x14004ff7e  pop     r14
0x14004ff80  pop     r13
0x14004ff82  pop     rdi
0x14004ff83  pop     rsi
0x14004ff84  pop     rbp
0x14004ff85  pop     rbx
0x14004ff86  retn
```
