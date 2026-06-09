# BthEnumFdoPower

- ea: `0x14001ccc8`
- end: `0x14001ce52`
- name: `BthEnumFdoPower`
- size: `394`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001d440`

## callees

- `0x1400018ec`
- `0x1400019c0`
- `0x14001ccc8`

## import_xrefs

- `ntoskrnl!PoSetPowerState` at `0x14001cdb6`
- `ntoskrnl!PoSetPowerState` at `0x14001cdb6`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001ce23`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001ce23`
- `ntoskrnl!PoCallDriver` at `0x14001ce36`
- `ntoskrnl!PoCallDriver` at `0x14001ce36`

## pseudocode

```c
NTSTATUS __fastcall BthEnumFdoPower(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  void *DeviceExtension; // rsi
  bool v6; // bp
  unsigned int Options; // r15d
  POWER_STATE v8; // ebx
  char *p_MinorFunction; // r14
  _IO_STACK_LOCATION *v10; // rax
  _IO_STACK_LOCATION *v11; // rax

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  DeviceExtension = DeviceObject->DeviceExtension;
  v6 = 0;
  Options = CurrentStackLocation->Parameters.Create.Options;
  v8.SystemState = (_SYSTEM_POWER_STATE)CurrentStackLocation->Parameters.Power.State;
  p_MinorFunction = (char *)&CurrentStackLocation->MinorFunction;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qd(
      WPP_GLOBAL_Control->DeviceExtension,
      (unsigned int)&WPP_RECORDER_INITIALIZED,
      (unsigned int)WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids,
      22,
      (__int64)WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids,
      (char)Irp,
      *p_MinorFunction);
  if ( *p_MinorFunction != 2 )
  {
    if ( *p_MinorFunction != 3 )
      goto LABEL_14;
    goto LABEL_7;
  }
  if ( *((_BYTE *)DeviceExtension + 34) != 1 )
  {
LABEL_7:
    Irp->IoStatus.Status = 0;
    goto LABEL_14;
  }
  if ( Options == 1 )
  {
    Irp->IoStatus.Status = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qdd(
        WPP_GLOBAL_Control->DeviceExtension,
        (unsigned int)&WPP_RECORDER_INITIALIZED,
        (unsigned int)WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids,
        23,
        (__int64)WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids,
        (char)DeviceObject,
        *((_DWORD *)DeviceExtension + 9),
        v8.SystemState);
    if ( *((_DWORD *)DeviceExtension + 9) >= v8.SystemState )
    {
      v6 = *((_DWORD *)DeviceExtension + 9) > v8.SystemState;
    }
    else
    {
      PoSetPowerState(DeviceObject, DevicePowerState, v8);
      *((POWER_STATE *)DeviceExtension + 9) = v8;
    }
  }
LABEL_14:
  v10 = Irp->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&v10[-1].MajorFunction = *(_OWORD *)&v10->MajorFunction;
  *(_OWORD *)&v10[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v10->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v10[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v10->Parameters.SetQuota + 6);
  v10[-1].FileObject = v10->FileObject;
  v10[-1].Control = 0;
  if ( v6 )
  {
    v11 = Irp->Tail.Overlay.CurrentStackLocation;
    v11[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))BthEnumFdoPowerComplete;
    v11[-1].Context = 0;
    v11[-1].Control = -32;
  }
  else
  {
    PoStartNextPowerIrp(Irp);
  }
  return PoCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 3), Irp);
}

```

## disassembly

```asm
0x14001ccc8  push    rbx
0x14001ccca  push    rbp
0x14001cccb  push    rsi
0x14001cccc  push    rdi
0x14001cccd  push    r13
0x14001cccf  push    r14
0x14001ccd1  push    r15
0x14001ccd3  sub     rsp, 40h
0x14001ccd7  mov     rax, [rdx+0B8h]
0x14001ccde  mov     rdi, rdx
0x14001cce1  mov     rsi, [rcx+40h]
0x14001cce5  mov     r13, rcx
0x14001cce8  xor     bpl, bpl
0x14001cceb  mov     r15d, [rax+10h]
0x14001ccef  mov     ebx, [rax+18h]
0x14001ccf2  lea     rdx, WPP_RECORDER_INITIALIZED
0x14001ccf9  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14001cd00  lea     r14, [rax+1]
0x14001cd04  lea     r8, WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids
0x14001cd0b  jz      short loc_14001CD43
0x14001cd0d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cd14  mov     r9d, 16h
0x14001cd1a  movzx   eax, byte ptr [r14]
0x14001cd1e  mov     [rsp+78h+var_48], eax
0x14001cd22  mov     [rsp+78h+var_50], rdi
0x14001cd27  mov     rcx, [rcx+40h]
0x14001cd2b  mov     [rsp+78h+var_58], r8
0x14001cd30  call    WPP_RECORDER_SF_qd
0x14001cd35  lea     rdx, WPP_RECORDER_INITIALIZED
0x14001cd3c  lea     r8, WPP_1bade311f6663955504d4f7ce8ae9a67_Traceguids
0x14001cd43  movzx   ecx, byte ptr [r14]
0x14001cd47  sub     ecx, 2
0x14001cd4a  jz      short loc_14001CD53
0x14001cd4c  cmp     ecx, 1
0x14001cd4f  jnz     short loc_14001CDCF
0x14001cd51  jmp     short loc_14001CD5F
0x14001cd53  mov     r14d, 1
0x14001cd59  cmp     [rsi+22h], r14b
0x14001cd5d  jz      short loc_14001CD68
0x14001cd5f  mov     dword ptr [rdi+30h], 0
0x14001cd66  jmp     short loc_14001CDCF
0x14001cd68  cmp     r15d, r14d
0x14001cd6b  jnz     short loc_14001CDCF
0x14001cd6d  mov     dword ptr [rdi+30h], 0
0x14001cd74  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14001cd7b  jz      short loc_14001CDA8
0x14001cd7d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cd84  mov     r9d, 17h
0x14001cd8a  mov     eax, [rsi+24h]
0x14001cd8d  mov     [rsp+78h+var_40], ebx
0x14001cd91  mov     [rsp+78h+var_48], eax
0x14001cd95  mov     rcx, [rcx+40h]
0x14001cd99  mov     [rsp+78h+var_50], r13
0x14001cd9e  mov     [rsp+78h+var_58], r8
0x14001cda3  call    WPP_RECORDER_SF_qdd
0x14001cda8  cmp     [rsi+24h], ebx
0x14001cdab  jge     short loc_14001CDC7
0x14001cdad  mov     r8d, ebx; State
0x14001cdb0  mov     edx, r14d; Type
0x14001cdb3  mov     rcx, r13; DeviceObject
0x14001cdb6  call    cs:__imp_PoSetPowerState
0x14001cdbd  nop     dword ptr [rax+rax+00h]
0x14001cdc2  mov     [rsi+24h], ebx
0x14001cdc5  jmp     short loc_14001CDCF
0x14001cdc7  movzx   ebp, bpl
0x14001cdcb  cmovg   ebp, r14d
0x14001cdcf  mov     rax, [rdi+0B8h]
0x14001cdd6  movups  xmm0, xmmword ptr [rax]
0x14001cdd9  movups  xmmword ptr [rax-48h], xmm0
0x14001cddd  movups  xmm1, xmmword ptr [rax+10h]
0x14001cde1  movups  xmmword ptr [rax-38h], xmm1
0x14001cde5  movups  xmm0, xmmword ptr [rax+20h]
0x14001cde9  movups  xmmword ptr [rax-28h], xmm0
0x14001cded  movsd   xmm1, qword ptr [rax+30h]
0x14001cdf2  movsd   qword ptr [rax-18h], xmm1
0x14001cdf7  mov     byte ptr [rax-45h], 0
0x14001cdfb  test    bpl, bpl
0x14001cdfe  jz      short loc_14001CE20
0x14001ce00  mov     rax, [rdi+0B8h]
0x14001ce07  lea     rcx, BthEnumFdoPowerComplete
0x14001ce0e  mov     [rax-10h], rcx
0x14001ce12  mov     qword ptr [rax-8], 0
0x14001ce1a  mov     byte ptr [rax-45h], 0E0h
0x14001ce1e  jmp     short loc_14001CE2F
0x14001ce20  mov     rcx, rdi; Irp
0x14001ce23  call    cs:__imp_PoStartNextPowerIrp
0x14001ce2a  nop     dword ptr [rax+rax+00h]
0x14001ce2f  mov     rcx, [rsi+18h]; DeviceObject
0x14001ce33  mov     rdx, rdi; Irp
0x14001ce36  call    cs:__imp_PoCallDriver
0x14001ce3d  nop     dword ptr [rax+rax+00h]
0x14001ce42  add     rsp, 40h
0x14001ce46  pop     r15
0x14001ce48  pop     r14
0x14001ce4a  pop     r13
0x14001ce4c  pop     rdi
0x14001ce4d  pop     rsi
0x14001ce4e  pop     rbp
0x14001ce4f  pop     rbx
0x14001ce50  retn
```
