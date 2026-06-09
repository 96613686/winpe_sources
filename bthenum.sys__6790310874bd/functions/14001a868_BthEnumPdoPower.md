# BthEnumPdoPower

- ea: `0x14001a868`
- end: `0x14001aa04`
- name: `BthEnumPdoPower`
- size: `412`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14001d440`

## callees

- `0x1400010d0`
- `0x1400018ec`
- `0x1400019c0`
- `0x140001ab8`
- `0x14001a868`
- `0x14001dcec`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001a9e4`
- `ntoskrnl!IofCompleteRequest` at `0x14001a9e4`
- `ntoskrnl!PoSetPowerState` at `0x14001a975`
- `ntoskrnl!PoSetPowerState` at `0x14001a975`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001a9d3`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14001a9d3`

## pseudocode

```c
__int64 __fastcall BthEnumPdoPower(PDEVICE_OBJECT DeviceObject, PIRP Irp, int a3)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _DWORD *DeviceExtension; // r14
  unsigned int Status; // edi
  unsigned int Options; // r15d
  POWER_STATE v9; // ebx
  char *p_MinorFunction; // r12
  POWER_STATE_TYPE v11; // edx

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  DeviceExtension = DeviceObject->DeviceExtension;
  Status = 0;
  Options = CurrentStackLocation->Parameters.Create.Options;
  v9.SystemState = (_SYSTEM_POWER_STATE)CurrentStackLocation->Parameters.Power.State;
  p_MinorFunction = (char *)&CurrentStackLocation->MinorFunction;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qd(
      WPP_GLOBAL_Control->DeviceExtension,
      (unsigned int)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
      a3,
      100,
      (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
      (char)DeviceObject,
      *p_MinorFunction);
  if ( *p_MinorFunction )
  {
    if ( *p_MinorFunction != 1 )
    {
      if ( *p_MinorFunction != 2 )
      {
        if ( *p_MinorFunction == 3 )
          BthEnumUpdateProfileConnectionCountKey((__int64)DeviceExtension);
        else
          Status = Irp->IoStatus.Status;
        goto LABEL_21;
      }
      if ( Options )
      {
        if ( Options != 1 )
          goto LABEL_11;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_qdd(
            WPP_GLOBAL_Control->DeviceExtension,
            (unsigned int)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
            a3,
            101,
            (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
            (char)DeviceObject,
            DeviceExtension[45],
            v9.SystemState);
        if ( DeviceExtension[45] == v9.SystemState )
          goto LABEL_21;
        DeviceExtension[45] = v9.SystemState;
        v11 = DevicePowerState;
      }
      else
      {
        v11 = SystemPowerState;
      }
      PoSetPowerState(DeviceObject, v11, v9);
      goto LABEL_21;
    }
LABEL_11:
    Status = -1073741822;
LABEL_21:
    Irp->IoStatus.Status = Status;
    PoStartNextPowerIrp(Irp);
    IofCompleteRequest(Irp, 0);
    return Status;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qq(
      WPP_GLOBAL_Control->DeviceExtension,
      (unsigned int)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
      3,
      102,
      (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
      (char)Irp,
      (char)DeviceObject);
  Status = BthEnumQueueIrp(DeviceObject, Irp);
  if ( Status != 259 )
    goto LABEL_21;
  return Status;
}

```

## disassembly

```asm
0x14001a868  push    rbx
0x14001a86a  push    rbp
0x14001a86b  push    rsi
0x14001a86c  push    rdi
0x14001a86d  push    r12
0x14001a86f  push    r13
0x14001a871  push    r14
0x14001a873  push    r15
0x14001a875  sub     rsp, 48h
0x14001a879  mov     rax, [rdx+0B8h]
0x14001a880  mov     rsi, rdx
0x14001a883  mov     r14, [rcx+40h]
0x14001a887  mov     rbp, rcx
0x14001a88a  xor     edi, edi
0x14001a88c  mov     r15d, [rax+10h]
0x14001a890  mov     ebx, [rax+18h]
0x14001a893  lea     r13, WPP_RECORDER_INITIALIZED
0x14001a89a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14001a8a1  lea     r12, [rax+1]
0x14001a8a5  lea     rdx, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids
0x14001a8ac  jz      short loc_14001A8DC
0x14001a8ae  movzx   eax, byte ptr [r12]
0x14001a8b3  lea     r9d, [rdi+64h]
0x14001a8b7  mov     dword ptr [rsp+88h+var_58], eax
0x14001a8bb  mov     [rsp+88h+var_60], rcx
0x14001a8c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a8c7  mov     [rsp+88h+var_68], rdx
0x14001a8cc  mov     rcx, [rcx+40h]
0x14001a8d0  call    WPP_RECORDER_SF_qd
0x14001a8d5  lea     rdx, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids
0x14001a8dc  movzx   ecx, byte ptr [r12]
0x14001a8e1  test    ecx, ecx
0x14001a8e3  jz      loc_14001A987
0x14001a8e9  sub     ecx, 1
0x14001a8ec  jz      short loc_14001A918
0x14001a8ee  sub     ecx, 1
0x14001a8f1  jz      short loc_14001A90D
0x14001a8f3  cmp     ecx, 1
0x14001a8f6  jz      short loc_14001A900
0x14001a8f8  mov     edi, [rsi+30h]
0x14001a8fb  jmp     loc_14001A9CD
0x14001a900  mov     rcx, r14
0x14001a903  call    BthEnumUpdateProfileConnectionCountKey
0x14001a908  jmp     loc_14001A9CD
0x14001a90d  test    r15d, r15d
0x14001a910  jz      short loc_14001A983
0x14001a912  cmp     r15d, 1
0x14001a916  jz      short loc_14001A922
0x14001a918  mov     edi, 0C0000002h
0x14001a91d  jmp     loc_14001A9CD
0x14001a922  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14001a929  jz      short loc_14001A95A
0x14001a92b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a932  mov     r9d, 65h ; 'e'
0x14001a938  mov     eax, [r14+0B4h]
0x14001a93f  mov     [rsp+88h+var_50], ebx
0x14001a943  mov     dword ptr [rsp+88h+var_58], eax
0x14001a947  mov     rcx, [rcx+40h]
0x14001a94b  mov     [rsp+88h+var_60], rbp
0x14001a950  mov     [rsp+88h+var_68], rdx
0x14001a955  call    WPP_RECORDER_SF_qdd
0x14001a95a  cmp     [r14+0B4h], ebx
0x14001a961  jz      short loc_14001A9CD
0x14001a963  mov     [r14+0B4h], ebx
0x14001a96a  mov     edx, 1; Type
0x14001a96f  mov     r8d, ebx; State
0x14001a972  mov     rcx, rbp; DeviceObject
0x14001a975  call    cs:__imp_PoSetPowerState
0x14001a97c  nop     dword ptr [rax+rax+00h]
0x14001a981  jmp     short loc_14001A9CD
0x14001a983  xor     edx, edx
0x14001a985  jmp     short loc_14001A96F
0x14001a987  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14001a98e  jz      short loc_14001A9B9
0x14001a990  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a997  mov     r9d, 66h ; 'f'
0x14001a99d  mov     [rsp+88h+var_58], rbp
0x14001a9a2  mov     [rsp+88h+var_60], rsi
0x14001a9a7  mov     [rsp+88h+var_68], rdx
0x14001a9ac  mov     rcx, [rcx+40h]
0x14001a9b0  lea     r8d, [r9-63h]
0x14001a9b4  call    WPP_RECORDER_SF_qq
0x14001a9b9  mov     rdx, rsi
0x14001a9bc  mov     rcx, rbp
0x14001a9bf  call    BthEnumQueueIrp
0x14001a9c4  mov     edi, eax
0x14001a9c6  cmp     eax, 103h
0x14001a9cb  jz      short loc_14001A9F0
0x14001a9cd  mov     rcx, rsi; Irp
0x14001a9d0  mov     [rsi+30h], edi
0x14001a9d3  call    cs:__imp_PoStartNextPowerIrp
0x14001a9da  nop     dword ptr [rax+rax+00h]
0x14001a9df  xor     edx, edx; PriorityBoost
0x14001a9e1  mov     rcx, rsi; Irp
0x14001a9e4  call    cs:__imp_IofCompleteRequest
0x14001a9eb  nop     dword ptr [rax+rax+00h]
0x14001a9f0  mov     eax, edi
0x14001a9f2  add     rsp, 48h
0x14001a9f6  pop     r15
0x14001a9f8  pop     r14
0x14001a9fa  pop     r13
0x14001a9fc  pop     r12
0x14001a9fe  pop     rdi
0x14001a9ff  pop     rsi
0x14001aa00  pop     rbp
0x14001aa01  pop     rbx
0x14001aa02  retn
```
