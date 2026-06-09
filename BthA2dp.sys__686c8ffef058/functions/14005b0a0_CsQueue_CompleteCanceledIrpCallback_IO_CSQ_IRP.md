# CsQueue::CompleteCanceledIrpCallback(_IO_CSQ *,_IRP *)

- ea: `0x14005b0a0`
- end: `0x14005b1ed`
- name: `?CompleteCanceledIrpCallback@CsQueue@@CAXPEAU_IO_CSQ@@PEAU_IRP@@@Z`
- size: `333`
- prototype: `IO_CSQ_COMPLETE_CANCELED_IRP`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14005bb10`

## callees

- `0x140003530`
- `0x14000f570`
- `0x14002d890`
- `0x14005afa0`
- `0x14005b0a0`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14005b1d5`
- `ntoskrnl!IofCompleteRequest` at `0x14005b1d5`

## pseudocode

```c
void __fastcall CsQueue::CompleteCanceledIrpCallback(PIO_CSQ Csq, PIRP Irp, __int64 a3, __int64 a4)
{
  __int64 v6; // rdx
  __int64 v7; // r8

  if ( (unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(Csq, Irp, a3, a4) )
  {
    LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v6,
        v7,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        1,
        23,
        (__int64)WPP_6372fbb7e78435cbabebbbab2162309b_Traceguids,
        (char)Irp);
  }
  else
  {
    LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v6,
        v7,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        1,
        24,
        (__int64)WPP_6372fbb7e78435cbabebbbab2162309b_Traceguids);
  }
  Irp->IoStatus.Status = -1073741536;
  Irp->IoStatus.Information = 0;
  if ( (*(unsigned __int8 (__fastcall **)(PIO_CSQ, __int64, __int64))(*(_QWORD *)&Csq[1].Type + 32LL))(Csq + 1, v6, v7) )
    utl::function<void (_IRP *)>::operator()(&Csq[1], Irp);
  IofCompleteRequest(Irp, 0);
}

```

## disassembly

```asm
0x14005b0a0  mov     [rsp+arg_0], rbx
0x14005b0a5  push    rdi
0x14005b0a6  sub     rsp, 50h
0x14005b0aa  mov     rbx, rdx
0x14005b0ad  mov     rdi, rcx
0x14005b0b0  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14005b0b5  test    eax, eax
0x14005b0b7  jz      short loc_14005B132
0x14005b0b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b0c0  lea     rax, WPP_GLOBAL_Control
0x14005b0c7  cmp     rcx, rax
0x14005b0ca  jz      short loc_14005B0DD
0x14005b0cc  mov     eax, [rcx+2Ch]
0x14005b0cf  test    al, 1
0x14005b0d1  jz      short loc_14005B0DD
0x14005b0d3  cmp     byte ptr [rcx+29h], 4
0x14005b0d7  jb      short loc_14005B0DD
0x14005b0d9  mov     dl, 1
0x14005b0db  jmp     short loc_14005B0DF
0x14005b0dd  xor     dl, dl
0x14005b0df  lea     rax, WPP_RECORDER_INITIALIZED
0x14005b0e6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14005b0ed  setnz   r8b
0x14005b0f1  test    dl, dl
0x14005b0f3  jnz     short loc_14005B0FE
0x14005b0f5  test    r8b, r8b
0x14005b0f8  jz      loc_14005B1A0
0x14005b0fe  mov     r9, [rcx+40h]
0x14005b102  lea     rax, WPP_6372fbb7e78435cbabebbbab2162309b_Traceguids
0x14005b109  mov     rcx, [rcx+18h]
0x14005b10d  mov     [rsp+58h+var_18], rbx
0x14005b112  mov     [rsp+58h+var_20], rax
0x14005b117  mov     [rsp+58h+var_28], 17h
0x14005b11e  mov     [rsp+58h+var_30], 1
0x14005b126  mov     [rsp+58h+var_38], 4
0x14005b12b  call    WPP_RECORDER_AND_TRACE_SF_q
0x14005b130  jmp     short loc_14005B1A0
0x14005b132  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b139  lea     rax, WPP_GLOBAL_Control
0x14005b140  cmp     rcx, rax
0x14005b143  jz      short loc_14005B156
0x14005b145  mov     eax, [rcx+2Ch]
0x14005b148  test    al, 1
0x14005b14a  jz      short loc_14005B156
0x14005b14c  cmp     byte ptr [rcx+29h], 4
0x14005b150  jb      short loc_14005B156
0x14005b152  mov     dl, 1
0x14005b154  jmp     short loc_14005B158
0x14005b156  xor     dl, dl
0x14005b158  lea     rax, WPP_RECORDER_INITIALIZED
0x14005b15f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14005b166  setnz   r8b
0x14005b16a  test    dl, dl
0x14005b16c  jnz     short loc_14005B173
0x14005b16e  test    r8b, r8b
0x14005b171  jz      short loc_14005B1A0
0x14005b173  mov     r9, [rcx+40h]
0x14005b177  lea     rax, WPP_6372fbb7e78435cbabebbbab2162309b_Traceguids
0x14005b17e  mov     rcx, [rcx+18h]
0x14005b182  mov     [rsp+58h+var_20], rax
0x14005b187  mov     [rsp+58h+var_28], 18h
0x14005b18e  mov     [rsp+58h+var_30], 1
0x14005b196  mov     [rsp+58h+var_38], 4
0x14005b19b  call    WPP_RECORDER_AND_TRACE_SF_
0x14005b1a0  mov     dword ptr [rbx+30h], 0C0000120h
0x14005b1a7  lea     rcx, [rdi+40h]
0x14005b1ab  mov     qword ptr [rbx+38h], 0
0x14005b1b3  mov     rax, [rdi+40h]
0x14005b1b7  mov     rax, [rax+20h]
0x14005b1bb  call    _guard_dispatch_icall
0x14005b1c0  test    al, al
0x14005b1c2  jz      short loc_14005B1D0
0x14005b1c4  mov     rdx, rbx
0x14005b1c7  lea     rcx, [rdi+40h]
0x14005b1cb  call    ??R?$function@$$A6AXPEAU_IRP@@@Z@utl@@QEBAXPEAU_IRP@@@Z; utl::function<void (_IRP *)>::operator()(_IRP *)
0x14005b1d0  xor     edx, edx; PriorityBoost
0x14005b1d2  mov     rcx, rbx; Irp
0x14005b1d5  call    cs:__imp_IofCompleteRequest
0x14005b1dc  nop     dword ptr [rax+rax+00h]
0x14005b1e1  mov     rbx, [rsp+58h+arg_0]
0x14005b1e6  add     rsp, 50h
0x14005b1ea  pop     rdi
0x14005b1eb  retn
```
