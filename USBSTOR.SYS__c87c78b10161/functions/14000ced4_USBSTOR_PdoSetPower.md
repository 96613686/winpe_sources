# USBSTOR_PdoSetPower

- ea: `0x14000ced4`
- end: `0x14000d1e8`
- name: `USBSTOR_PdoSetPower`
- size: `788`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000cd00`

## callees

- `0x140003630`
- `0x14000b2e8`
- `0x14000ced4`
- `0x14000d700`
- `0x14000de94`
- `0x1400105e8`
- `0x140010664`
- `0x140010f78`
- `0x140012c8c`

## import_xrefs

- `ntoskrnl!PoRequestPowerIrp` at `0x14000cff6`
- `ntoskrnl!PoRequestPowerIrp` at `0x14000d017`
- `ntoskrnl!PoRequestPowerIrp` at `0x14000cff6`
- `ntoskrnl!PoRequestPowerIrp` at `0x14000d017`
- `ntoskrnl!PoSetPowerState` at `0x14000d158`
- `ntoskrnl!PoSetPowerState` at `0x14000d158`
- `ntoskrnl!IofCompleteRequest` at `0x14000d183`
- `ntoskrnl!IofCompleteRequest` at `0x14000d183`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000d172`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000d172`

## pseudocode

```c
__int64 __fastcall USBSTOR_PdoSetPower(PDEVICE_OBJECT DeviceObject, PIRP Irp, __int64 a3, __int64 a4)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  unsigned int *DeviceExtension; // r15
  __int64 Options; // r12
  unsigned int LowPart; // ebx
  __int64 v10; // rax
  __int64 v11; // r8
  int v12; // esi
  unsigned int v13; // edx
  POWER_STATE v14; // r12d
  unsigned int v15; // edx
  __int64 v16; // rax
  __int64 v17; // r10
  __int64 v18; // r8
  NTSTATUS v19; // eax
  __int64 v20; // rax
  __int64 v21; // r10
  __int64 v22; // r8
  int v23; // eax

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  DeviceExtension = (unsigned int *)DeviceObject->DeviceExtension;
  Options = (int)CurrentStackLocation->Parameters.Create.Options;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    if ( (_DWORD)Options )
      v10 = PowerDeviceStateString(LowPart);
    else
      v10 = PowerSystemStateString(LowPart, Irp, WPP_GLOBAL_Control, a4);
    WPP_SF_qs(*(_QWORD *)(v11 + 24), 41, v11, (_DWORD)DeviceObject, v10);
  }
  USBSTOR_LogEntry(1347634256, DeviceObject, Irp, Options);
  v12 = 0;
  if ( (_DWORD)Options )
  {
    if ( (_DWORD)Options == 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        PowerDeviceStateString(LowPart);
        v20 = PowerDeviceStateString(DeviceExtension[12]);
        WPP_SF_qqss(*(_QWORD *)(v21 + 24), 43, v22, (_DWORD)DeviceObject, (char)Irp, v20, v22);
      }
      v23 = DeviceExtension[12];
      DeviceExtension[12] = LowPart;
      if ( v23 == 1 )
      {
        if ( (int)LowPart > 1 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
          }
          USBSTOR_LogEntry(1685223280, DeviceObject, Irp, 0);
        }
      }
      else if ( v23 > 1 && LowPart == 1 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
        }
        USBSTOR_LogEntry(1970435952, DeviceObject, Irp, 0);
        if ( !*((_BYTE *)DeviceExtension + 672) )
          UsbQueueRestart(DeviceObject);
      }
      PoSetPowerState(DeviceObject, DevicePowerState, (POWER_STATE)LowPart);
    }
    goto LABEL_43;
  }
  v13 = DeviceExtension[12];
  v14.SystemState = PowerSystemSleeping3;
  DeviceExtension[11] = LowPart;
  if ( LowPart == 1 )
    v14.SystemState = PowerSystemWorking;
  if ( v13 == v14.SystemState )
  {
LABEL_43:
    Irp->IoStatus.Status = v12;
    PoStartNextPowerIrp(Irp);
    IofCompleteRequest(Irp, 0);
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    PowerDeviceStateString((unsigned int)v14.SystemState);
    v16 = PowerDeviceStateString(v15);
    WPP_SF_qqss(*(_QWORD *)(v17 + 24), 42, v18, (_DWORD)DeviceObject, (char)Irp, v16, v18);
  }
  if ( (int)DeviceExtension[12] > v14.SystemState )
  {
    v19 = PoRequestPowerIrp(DeviceObject, 2u, v14, 0, 0, 0);
    if ( v19 < 0 )
      v12 = v19;
    goto LABEL_43;
  }
  *((_QWORD *)DeviceExtension + 7) = Irp;
  v12 = PoRequestPowerIrp(DeviceObject, 2u, v14, (PREQUEST_POWER_COMPLETE)USBSTOR_PdoSetPowerCompletion, 0, 0);
  if ( v12 < 0 )
  {
    *((_QWORD *)DeviceExtension + 7) = 0;
    goto LABEL_43;
  }
LABEL_44:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1886610544, v12, 0, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000ced4  push    rbx
0x14000ced6  push    rbp
0x14000ced7  push    rsi
0x14000ced8  push    rdi
0x14000ced9  push    r12
0x14000cedb  push    r13
0x14000cedd  push    r14
0x14000cedf  push    r15
0x14000cee1  sub     rsp, 48h
0x14000cee5  mov     rbx, [rdx+0B8h]
0x14000ceec  mov     r14, rdx
0x14000ceef  mov     r15, [rcx+40h]
0x14000cef3  mov     rbp, rcx
0x14000cef6  movsxd  r12, dword ptr [rbx+10h]
0x14000cefa  mov     ebx, [rbx+18h]
0x14000cefd  mov     r8, cs:WPP_GLOBAL_Control
0x14000cf04  lea     rax, WPP_GLOBAL_Control
0x14000cf0b  mov     r13d, 4
0x14000cf11  cmp     r8, rax
0x14000cf14  jz      short loc_14000CF4E
0x14000cf16  mov     eax, [r8+2Ch]
0x14000cf1a  test    r13b, al
0x14000cf1d  jz      short loc_14000CF4E
0x14000cf1f  cmp     [r8+29h], r13b
0x14000cf23  jb      short loc_14000CF4E
0x14000cf25  mov     ecx, ebx
0x14000cf27  test    r12d, r12d
0x14000cf2a  jnz     short loc_14000CF33
0x14000cf2c  call    PowerSystemStateString
0x14000cf31  jmp     short loc_14000CF38
0x14000cf33  call    PowerDeviceStateString
0x14000cf38  mov     rcx, [r8+18h]
0x14000cf3c  mov     edx, 29h ; ')'
0x14000cf41  mov     r9, rbp
0x14000cf44  mov     [rsp+88h+Context], rax
0x14000cf49  call    WPP_SF_qs
0x14000cf4e  mov     r9, r12
0x14000cf51  mov     r8, r14
0x14000cf54  mov     rdx, rbp
0x14000cf57  mov     ecx, 50534450h
0x14000cf5c  call    USBSTOR_LogEntry
0x14000cf61  xor     esi, esi
0x14000cf63  lea     edi, [rsi+1]
0x14000cf66  test    r12d, r12d
0x14000cf69  jnz     loc_14000D03A
0x14000cf6f  mov     edx, [r15+30h]
0x14000cf73  cmp     ebx, edi
0x14000cf75  mov     r12d, r13d
0x14000cf78  mov     [r15+2Ch], ebx
0x14000cf7c  cmovz   r12d, edi
0x14000cf80  cmp     edx, r12d
0x14000cf83  jz      loc_14000D164
0x14000cf89  mov     r10, cs:WPP_GLOBAL_Control
0x14000cf90  lea     rbx, WPP_GLOBAL_Control
0x14000cf97  cmp     r10, rbx
0x14000cf9a  jz      short loc_14000CFDB
0x14000cf9c  mov     eax, [r10+2Ch]
0x14000cfa0  test    r13b, al
0x14000cfa3  jz      short loc_14000CFDB
0x14000cfa5  cmp     [r10+29h], r13b
0x14000cfa9  jb      short loc_14000CFDB
0x14000cfab  mov     ecx, r12d
0x14000cfae  call    PowerDeviceStateString
0x14000cfb3  mov     ecx, edx
0x14000cfb5  mov     r8, rax
0x14000cfb8  call    PowerDeviceStateString
0x14000cfbd  mov     rcx, [r10+18h]
0x14000cfc1  lea     edx, [rsi+2Ah]
0x14000cfc4  mov     [rsp+88h+var_58], r8
0x14000cfc9  mov     r9, rbp
0x14000cfcc  mov     [rsp+88h+Irp], rax
0x14000cfd1  mov     [rsp+88h+Context], r14
0x14000cfd6  call    WPP_SF_qqss
0x14000cfdb  mov     r8d, r12d; PowerState
0x14000cfde  mov     [rsp+88h+Irp], rsi; Irp
0x14000cfe3  mov     dl, 2; MinorFunction
0x14000cfe5  mov     [rsp+88h+Context], rsi; Context
0x14000cfea  mov     rcx, rbp; DeviceObject
0x14000cfed  cmp     [r15+30h], r12d
0x14000cff1  jle     short loc_14000D00C
0x14000cff3  xor     r9d, r9d; CompletionFunction
0x14000cff6  call    cs:__imp_PoRequestPowerIrp
0x14000cffd  nop     dword ptr [rax+rax+00h]
0x14000d002  test    eax, eax
0x14000d004  cmovs   esi, eax
0x14000d007  jmp     loc_14000D16B
0x14000d00c  lea     r9, USBSTOR_PdoSetPowerCompletion; CompletionFunction
0x14000d013  mov     [r15+38h], r14
0x14000d017  call    cs:__imp_PoRequestPowerIrp
0x14000d01e  nop     dword ptr [rax+rax+00h]
0x14000d023  mov     esi, eax
0x14000d025  test    eax, eax
0x14000d027  jns     loc_14000D18F
0x14000d02d  mov     qword ptr [r15+38h], 0
0x14000d035  jmp     loc_14000D16B
0x14000d03a  cmp     r12d, edi
0x14000d03d  jnz     loc_14000D164
0x14000d043  mov     r10, cs:WPP_GLOBAL_Control
0x14000d04a  lea     rdx, WPP_GLOBAL_Control
0x14000d051  cmp     r10, rdx
0x14000d054  jz      short loc_14000D09F
0x14000d056  mov     eax, [r10+2Ch]
0x14000d05a  test    r13b, al
0x14000d05d  jz      short loc_14000D09F
0x14000d05f  cmp     [r10+29h], r13b
0x14000d063  jb      short loc_14000D09F
0x14000d065  mov     ecx, ebx
0x14000d067  call    PowerDeviceStateString
0x14000d06c  mov     ecx, [r15+30h]
0x14000d070  mov     r8, rax
0x14000d073  call    PowerDeviceStateString
0x14000d078  mov     rcx, [r10+18h]
0x14000d07c  mov     edx, 2Bh ; '+'
0x14000d081  mov     [rsp+88h+var_58], r8
0x14000d086  mov     r9, rbp
0x14000d089  mov     [rsp+88h+Irp], rax
0x14000d08e  mov     [rsp+88h+Context], r14
0x14000d093  call    WPP_SF_qqss
0x14000d098  lea     rdx, WPP_GLOBAL_Control
0x14000d09f  mov     eax, [r15+30h]
0x14000d0a3  mov     [r15+30h], ebx
0x14000d0a7  cmp     eax, edi
0x14000d0a9  jnz     short loc_14000D0F7
0x14000d0ab  cmp     ebx, edi
0x14000d0ad  jle     loc_14000D150
0x14000d0b3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d0ba  cmp     rcx, rdx
0x14000d0bd  jz      short loc_14000D0E2
0x14000d0bf  mov     eax, [rcx+2Ch]
0x14000d0c2  test    r13b, al
0x14000d0c5  jz      short loc_14000D0E2
0x14000d0c7  cmp     [rcx+29h], r13b
0x14000d0cb  jb      short loc_14000D0E2
0x14000d0cd  mov     rcx, [rcx+18h]
0x14000d0d1  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14000d0d8  mov     edx, 2Ch ; ','
0x14000d0dd  call    WPP_SF_
0x14000d0e2  xor     r9d, r9d
0x14000d0e5  mov     r8, r14
0x14000d0e8  mov     rdx, rbp
0x14000d0eb  mov     ecx, 64727770h
0x14000d0f0  call    USBSTOR_LogEntry
0x14000d0f5  jmp     short loc_14000D150
0x14000d0f7  jle     short loc_14000D150
0x14000d0f9  cmp     ebx, edi
0x14000d0fb  jnz     short loc_14000D150
0x14000d0fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d104  cmp     rcx, rdx
0x14000d107  jz      short loc_14000D12C
0x14000d109  mov     eax, [rcx+2Ch]
0x14000d10c  test    r13b, al
0x14000d10f  jz      short loc_14000D12C
0x14000d111  cmp     [rcx+29h], r13b
0x14000d115  jb      short loc_14000D12C
0x14000d117  mov     rcx, [rcx+18h]
0x14000d11b  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14000d122  mov     edx, 2Dh ; '-'
0x14000d127  call    WPP_SF_
0x14000d12c  xor     r9d, r9d
0x14000d12f  mov     r8, r14
0x14000d132  mov     rdx, rbp
0x14000d135  mov     ecx, 75727770h
0x14000d13a  call    USBSTOR_LogEntry
0x14000d13f  cmp     [r15+2A0h], sil
0x14000d146  jnz     short loc_14000D150
0x14000d148  mov     rcx, rbp
0x14000d14b  call    UsbQueueRestart
0x14000d150  mov     r8d, ebx; State
0x14000d153  mov     edx, edi; Type
0x14000d155  mov     rcx, rbp; DeviceObject
0x14000d158  call    cs:__imp_PoSetPowerState
0x14000d15f  nop     dword ptr [rax+rax+00h]
0x14000d164  lea     rbx, WPP_GLOBAL_Control
0x14000d16b  mov     rcx, r14; Irp
0x14000d16e  mov     [r14+30h], esi
0x14000d172  call    cs:__imp_PoStartNextPowerIrp
0x14000d179  nop     dword ptr [rax+rax+00h]
0x14000d17e  xor     edx, edx; PriorityBoost
0x14000d180  mov     rcx, r14; Irp
0x14000d183  call    cs:__imp_IofCompleteRequest
0x14000d18a  nop     dword ptr [rax+rax+00h]
0x14000d18f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d196  cmp     rcx, rbx
0x14000d199  jz      short loc_14000D1C1
0x14000d19b  mov     eax, [rcx+2Ch]
0x14000d19e  test    r13b, al
0x14000d1a1  jz      short loc_14000D1C1
0x14000d1a3  cmp     [rcx+29h], r13b
0x14000d1a7  jb      short loc_14000D1C1
0x14000d1a9  mov     rcx, [rcx+18h]
0x14000d1ad  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14000d1b4  mov     edx, 2Eh ; '.'
0x14000d1b9  mov     r9d, esi
0x14000d1bc  call    WPP_SF_d
0x14000d1c1  movsxd  rdx, esi
0x14000d1c4  xor     r9d, r9d
0x14000d1c7  xor     r8d, r8d
0x14000d1ca  mov     ecx, 70736470h
0x14000d1cf  call    USBSTOR_LogEntry
0x14000d1d4  mov     eax, esi
0x14000d1d6  add     rsp, 48h
0x14000d1da  pop     r15
0x14000d1dc  pop     r14
0x14000d1de  pop     r13
0x14000d1e0  pop     r12
0x14000d1e2  pop     rdi
0x14000d1e3  pop     rsi
0x14000d1e4  pop     rbp
0x14000d1e5  pop     rbx
0x14000d1e6  retn
```
