# USBSTOR_Power

- ea: `0x14000cd00`
- end: `0x14000cecc`
- name: `USBSTOR_Power`
- size: `460`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003630`
- `0x14000cd00`
- `0x14000ced4`
- `0x14000d1f0`
- `0x14000de94`
- `0x1400105e8`
- `0x140011080`
- `0x14001114c`
- `0x140012c40`
- `0x140012c8c`

## import_xrefs

- `ntoskrnl!PoCallDriver` at `0x14000ce29`
- `ntoskrnl!PoCallDriver` at `0x14000ce29`
- `ntoskrnl!IofCompleteRequest` at `0x14000ce6c`
- `ntoskrnl!IofCompleteRequest` at `0x14000ce6c`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000ce0b`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000ce5b`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000ce0b`
- `ntoskrnl!PoStartNextPowerIrp` at `0x14000ce5b`

## pseudocode

```c
__int64 __fastcall USBSTOR_Power(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  PDEVICE_OBJECT *DeviceExtension; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  struct _DEVICE_OBJECT *v5; // rsi
  const char *v6; // rbp
  __int64 v7; // rax
  int v8; // edx
  __int64 v9; // r8
  int v10; // r10d
  const char *v11; // r9
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 LowPart; // rcx
  __int64 v15; // rax
  __int64 v16; // rdx
  UCHAR MinorFunction; // al
  NTSTATUS v18; // eax
  NTSTATUS Status; // edi

  DeviceExtension = (PDEVICE_OBJECT *)DeviceObject->DeviceExtension;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v5 = DeviceObject;
  v6 = "FDO";
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    LOBYTE(DeviceObject) = CurrentStackLocation->MinorFunction;
    v7 = PowerMinorFunctionString(DeviceObject);
    v11 = "FDO";
    if ( *(_DWORD *)DeviceExtension != 558842950 )
      LODWORD(v11) = v10;
    WPP_SF_sqqs(*(_QWORD *)(v9 + 24), v8, v9, (_DWORD)v11, (char)v5, (char)Irp, v7);
  }
  USBSTOR_LogEntry(1381453648, v5, Irp, CurrentStackLocation->MinorFunction);
  if ( CurrentStackLocation->MinorFunction == 2
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
    if ( CurrentStackLocation->Parameters.Create.Options )
      v15 = PowerDeviceStateString(LowPart);
    else
      v15 = PowerSystemStateString(LowPart, WPP_GLOBAL_Control, v12, v13);
    if ( *(_DWORD *)DeviceExtension != 558842950 )
      v6 = "PDO";
    WPP_SF_ss(*(_QWORD *)(v16 + 24), v16, v15, (_DWORD)v6, v15);
  }
  MinorFunction = CurrentStackLocation->MinorFunction;
  if ( *(_DWORD *)DeviceExtension == 558842950 )
  {
    if ( MinorFunction == 2 )
    {
      v18 = USBSTOR_FdoSetPower(v5, Irp);
    }
    else
    {
      PoStartNextPowerIrp(Irp);
      ++Irp->CurrentLocation;
      ++Irp->Tail.Overlay.CurrentStackLocation;
      v18 = PoCallDriver(DeviceExtension[3], Irp);
    }
  }
  else
  {
    if ( MinorFunction != 2 )
    {
      if ( MinorFunction == 3 )
      {
        Status = 0;
        Irp->IoStatus.Status = 0;
      }
      else
      {
        Status = Irp->IoStatus.Status;
      }
      PoStartNextPowerIrp(Irp);
      IofCompleteRequest(Irp, 0);
      goto LABEL_28;
    }
    v18 = USBSTOR_PdoSetPower(v5, Irp, v12, v13);
  }
  Status = v18;
LABEL_28:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1920429936, Status, 0, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x14000cd00  push    rbx
0x14000cd02  push    rbp
0x14000cd03  push    rsi
0x14000cd04  push    rdi
0x14000cd05  push    r13
0x14000cd07  push    r14
0x14000cd09  sub     rsp, 48h
0x14000cd0d  mov     r14, [rcx+40h]
0x14000cd11  mov     rbx, rdx
0x14000cd14  mov     rdi, [rdx+0B8h]
0x14000cd1b  mov     rsi, rcx
0x14000cd1e  mov     r8, cs:WPP_GLOBAL_Control
0x14000cd25  lea     r13, WPP_GLOBAL_Control
0x14000cd2c  lea     r10, aPdo; "PDO"
0x14000cd33  lea     rbp, aFdo; "FDO"
0x14000cd3a  cmp     r8, r13
0x14000cd3d  jz      short loc_14000CD7C
0x14000cd3f  mov     eax, [r8+2Ch]
0x14000cd43  test    al, 4
0x14000cd45  jz      short loc_14000CD7C
0x14000cd47  cmp     byte ptr [r8+29h], 4
0x14000cd4c  jb      short loc_14000CD7C
0x14000cd4e  mov     cl, [rdi+1]
0x14000cd51  call    PowerMinorFunctionString
0x14000cd56  cmp     dword ptr [r14], 214F4446h
0x14000cd5d  mov     r9, rbp
0x14000cd60  mov     rcx, [r8+18h]
0x14000cd64  mov     [rsp+78h+var_48], rax
0x14000cd69  cmovnz  r9, r10
0x14000cd6d  mov     [rsp+78h+var_50], rbx
0x14000cd72  mov     [rsp+78h+var_58], rsi
0x14000cd77  call    WPP_SF_sqqs
0x14000cd7c  movzx   r9d, byte ptr [rdi+1]
0x14000cd81  mov     r8, rbx
0x14000cd84  mov     rdx, rsi
0x14000cd87  mov     ecx, 52574F50h
0x14000cd8c  call    USBSTOR_LogEntry
0x14000cd91  cmp     byte ptr [rdi+1], 2
0x14000cd95  jnz     short loc_14000CDEB
0x14000cd97  mov     rdx, cs:WPP_GLOBAL_Control
0x14000cd9e  cmp     rdx, r13
0x14000cda1  jz      short loc_14000CDEB
0x14000cda3  mov     eax, [rdx+2Ch]
0x14000cda6  test    al, 4
0x14000cda8  jz      short loc_14000CDEB
0x14000cdaa  cmp     byte ptr [rdx+29h], 4
0x14000cdae  jb      short loc_14000CDEB
0x14000cdb0  cmp     dword ptr [rdi+10h], 0
0x14000cdb4  mov     ecx, [rdi+18h]
0x14000cdb7  jnz     short loc_14000CDC0
0x14000cdb9  call    PowerSystemStateString
0x14000cdbe  jmp     short loc_14000CDC5
0x14000cdc0  call    PowerDeviceStateString
0x14000cdc5  cmp     dword ptr [r14], 214F4446h
0x14000cdcc  mov     r8, rax
0x14000cdcf  mov     rcx, [rdx+18h]
0x14000cdd3  lea     rax, aPdo; "PDO"
0x14000cdda  cmovnz  rbp, rax
0x14000cdde  mov     [rsp+78h+var_58], r8
0x14000cde3  mov     r9, rbp
0x14000cde6  call    WPP_SF_ss
0x14000cdeb  cmp     dword ptr [r14], 214F4446h
0x14000cdf2  mov     al, [rdi+1]
0x14000cdf5  jnz     short loc_14000CE37
0x14000cdf7  cmp     al, 2
0x14000cdf9  jnz     short loc_14000CE08
0x14000cdfb  mov     rdx, rbx; Irp
0x14000cdfe  mov     rcx, rsi; DeviceObject
0x14000ce01  call    USBSTOR_FdoSetPower
0x14000ce06  jmp     short loc_14000CE46
0x14000ce08  mov     rcx, rbx; Irp
0x14000ce0b  call    cs:__imp_PoStartNextPowerIrp
0x14000ce12  nop     dword ptr [rax+rax+00h]
0x14000ce17  inc     byte ptr [rbx+43h]
0x14000ce1a  mov     rdx, rbx; Irp
0x14000ce1d  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x14000ce25  mov     rcx, [r14+18h]; DeviceObject
0x14000ce29  call    cs:__imp_PoCallDriver
0x14000ce30  nop     dword ptr [rax+rax+00h]
0x14000ce35  jmp     short loc_14000CE46
0x14000ce37  cmp     al, 2
0x14000ce39  jnz     short loc_14000CE4A
0x14000ce3b  mov     rdx, rbx; Irp
0x14000ce3e  mov     rcx, rsi; DeviceObject
0x14000ce41  call    USBSTOR_PdoSetPower
0x14000ce46  mov     edi, eax
0x14000ce48  jmp     short loc_14000CE78
0x14000ce4a  cmp     al, 3
0x14000ce4c  jnz     short loc_14000CE55
0x14000ce4e  xor     edi, edi
0x14000ce50  mov     [rbx+30h], edi
0x14000ce53  jmp     short loc_14000CE58
0x14000ce55  mov     edi, [rbx+30h]
0x14000ce58  mov     rcx, rbx; Irp
0x14000ce5b  call    cs:__imp_PoStartNextPowerIrp
0x14000ce62  nop     dword ptr [rax+rax+00h]
0x14000ce67  xor     edx, edx; PriorityBoost
0x14000ce69  mov     rcx, rbx; Irp
0x14000ce6c  call    cs:__imp_IofCompleteRequest
0x14000ce73  nop     dword ptr [rax+rax+00h]
0x14000ce78  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ce7f  cmp     rcx, r13
0x14000ce82  jz      short loc_14000CEA9
0x14000ce84  mov     eax, [rcx+2Ch]
0x14000ce87  test    al, 4
0x14000ce89  jz      short loc_14000CEA9
0x14000ce8b  cmp     byte ptr [rcx+29h], 4
0x14000ce8f  jb      short loc_14000CEA9
0x14000ce91  mov     rcx, [rcx+18h]
0x14000ce95  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14000ce9c  mov     edx, 1Fh
0x14000cea1  mov     r9d, edi
0x14000cea4  call    WPP_SF_d
0x14000cea9  movsxd  rdx, edi
0x14000ceac  xor     r9d, r9d
0x14000ceaf  xor     r8d, r8d
0x14000ceb2  mov     ecx, 72776F70h
0x14000ceb7  call    USBSTOR_LogEntry
0x14000cebc  mov     eax, edi
0x14000cebe  add     rsp, 48h
0x14000cec2  pop     r14
0x14000cec4  pop     r13
0x14000cec6  pop     rdi
0x14000cec7  pop     rsi
0x14000cec8  pop     rbp
0x14000cec9  pop     rbx
0x14000ceca  retn
```
