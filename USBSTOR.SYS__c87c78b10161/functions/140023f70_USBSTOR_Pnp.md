# USBSTOR_Pnp

- ea: `0x140023f70`
- end: `0x14002435e`
- name: `USBSTOR_Pnp`
- size: `1006`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `25`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003630`
- `0x14000811c`
- `0x140008590`
- `0x14000b0bc`
- `0x1400105e8`
- `0x140010664`
- `0x14001100c`
- `0x140012ad4`
- `0x14001f008`
- `0x14001fb7c`
- `0x14001fca8`
- `0x140020670`
- `0x14002077c`
- `0x1400209f4`
- `0x140020c90`
- `0x140023f70`
- `0x140024370`
- `0x1400244e0`
- `0x140024614`
- `0x140024870`
- `0x140024cf4`
- `0x140024fd8`
- `0x14002877c`
- `0x140028b50`
- `0x140028da0`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14002409e`
- `ntoskrnl!IofCallDriver` at `0x14002409e`
- `ntoskrnl!IofCompleteRequest` at `0x140024130`
- `ntoskrnl!IofCompleteRequest` at `0x140024130`

## pseudocode

```c
__int64 __fastcall USBSTOR_Pnp(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  _DWORD *DeviceExtension; // rbp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  PDEVICE_OBJECT *v6; // r14
  __int64 MinorFunction; // rcx
  NTSTATUS Capabilities; // eax
  NTSTATUS Status; // ebx
  __int64 v11; // rax
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // r8

  DeviceExtension = DeviceObject->DeviceExtension;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    v11 = PnPMinorFunctionString(CurrentStackLocation->MinorFunction);
    WPP_SF_s(*(_QWORD *)(v12 + 24), 50, v12, v11);
  }
  USBSTOR_LogEntry(542133840, DeviceObject, Irp, CurrentStackLocation->MinorFunction);
  v6 = (PDEVICE_OBJECT *)DeviceObject->DeviceExtension;
  MinorFunction = CurrentStackLocation->MinorFunction;
  if ( *DeviceExtension == 558842950 )
  {
    if ( (_DWORD)MinorFunction == 9 )
    {
      Capabilities = USBSTOR_FdoQueryCapabilities(DeviceObject, Irp);
    }
    else if ( (_DWORD)MinorFunction == 7 )
    {
      Capabilities = USBSTOR_FdoQueryDeviceRelations(DeviceObject, Irp);
    }
    else
    {
      switch ( CurrentStackLocation->MinorFunction )
      {
        case 0u:
          Capabilities = USBSTOR_FdoStartDevice(DeviceObject, Irp);
          break;
        case 1u:
        case 5u:
          Capabilities = USBSTOR_FdoQueryStopRemoveDevice((__int64)DeviceObject, Irp);
          break;
        case 2u:
          Capabilities = USBSTOR_FdoRemoveDevice(DeviceObject, Irp);
          break;
        case 3u:
        case 6u:
          Capabilities = USBSTOR_FdoCancelStopRemoveDevice((__int64)DeviceObject, Irp);
          break;
        case 4u:
          Capabilities = USBSTOR_FdoStopDevice(DeviceObject, Irp);
          break;
        case 0x16u:
          Capabilities = USBSTOR_FdoDeviceUsageNotification(DeviceObject, Irp);
          break;
        case 0x17u:
          Irp->IoStatus.Status = 0;
          goto LABEL_19;
        default:
LABEL_19:
          ++Irp->CurrentLocation;
          ++Irp->Tail.Overlay.CurrentStackLocation;
          Capabilities = IofCallDriver(v6[3], Irp);
          break;
      }
    }
    goto LABEL_5;
  }
  if ( !CurrentStackLocation->MinorFunction )
  {
    Capabilities = USBSTOR_PdoStartDevice(DeviceObject, Irp);
LABEL_5:
    Status = Capabilities;
    goto LABEL_6;
  }
  if ( (_DWORD)MinorFunction == 7 )
  {
    Capabilities = USBSTOR_PdoQueryDeviceRelations(DeviceObject, Irp);
    goto LABEL_5;
  }
  switch ( CurrentStackLocation->MinorFunction )
  {
    case 1u:
    case 5u:
      Capabilities = USBSTOR_PdoQueryStopRemoveDevice(DeviceObject, Irp);
      goto LABEL_5;
    case 2u:
      if ( *((_DWORD *)v6 + 10) == 8 )
        goto LABEL_26;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
      }
      USBSTOR_LogEntry(542524498, DeviceObject, Irp, 0);
      UsbQueueFlush(DeviceObject, v6 + 46);
      Capabilities = USBSTOR_PdoRemoveDevice(DeviceObject, Irp);
      goto LABEL_5;
    case 3u:
    case 6u:
      goto LABEL_25;
    case 4u:
      Capabilities = USBSTOR_PdoStopDevice(DeviceObject, Irp);
      goto LABEL_5;
    case 9u:
      Capabilities = USBSTOR_PdoQueryCapabilities(DeviceObject, Irp);
      goto LABEL_5;
    case 0xCu:
      Capabilities = USBSTOR_PdoQueryDeviceText(DeviceObject, Irp);
      goto LABEL_5;
    case 0x13u:
      Capabilities = USBSTOR_PdoQueryID(DeviceObject, Irp);
      goto LABEL_5;
    case 0x14u:
      Capabilities = USBSTOR_PdoQueryPnpDeviceState(DeviceObject, Irp);
      goto LABEL_5;
    case 0x16u:
      Capabilities = USBSTOR_PdoDeviceUsageNotification(DeviceObject, Irp);
      goto LABEL_5;
    case 0x17u:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
      }
      USBSTOR_LogEntry(1447318099, DeviceObject, Irp, 0);
      UsbQueueFlush(DeviceObject, v6 + 46);
      *((_DWORD *)v6 + 10) = 7;
LABEL_25:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v13 = PnPMinorFunctionString(CurrentStackLocation->MinorFunction);
        WPP_SF_s(*(_QWORD *)(v14 + 24), 53, v14, v13);
      }
      goto LABEL_26;
    case 0x19u:
      *((_DWORD *)v6 + 10) = 2;
LABEL_26:
      Status = 0;
      Irp->IoStatus.Status = 0;
      break;
    default:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v15 = PnPMinorFunctionString(MinorFunction);
        WPP_SF_s(*(_QWORD *)(v16 + 24), 54, v16, v15);
      }
      Status = Irp->IoStatus.Status;
      break;
  }
  IofCompleteRequest(Irp, 0);
LABEL_6:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(544239216, Status, 0, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140023f70  push    rbx
0x140023f72  push    rbp
0x140023f73  push    rsi
0x140023f74  push    rdi
0x140023f75  push    r14
0x140023f77  push    r15
0x140023f79  sub     rsp, 28h
0x140023f7d  mov     rbp, [rcx+40h]
0x140023f81  mov     rdi, rdx
0x140023f84  mov     rsi, [rdx+0B8h]
0x140023f8b  mov     rbx, rcx
0x140023f8e  mov     r8, cs:WPP_GLOBAL_Control
0x140023f95  lea     r15, WPP_GLOBAL_Control
0x140023f9c  cmp     r8, r15
0x140023f9f  jnz     short loc_14002400F
0x140023fa1  movzx   r9d, byte ptr [rsi+1]
0x140023fa6  mov     r8, rdi
0x140023fa9  mov     rdx, rbx
0x140023fac  mov     ecx, 20504E50h
0x140023fb1  call    USBSTOR_LogEntry
0x140023fb6  cmp     dword ptr [rbp+0], 214F4446h
0x140023fbd  mov     r14, [rbx+40h]
0x140023fc1  movzx   ecx, byte ptr [rsi+1]
0x140023fc5  jz      loc_140024079
0x140023fcb  test    ecx, ecx
0x140023fcd  jnz     loc_140024064
0x140023fd3  mov     rdx, rdi; Irp
0x140023fd6  mov     rcx, rbx; DeviceObject
0x140023fd9  call    USBSTOR_PdoStartDevice
0x140023fde  mov     ebx, eax
0x140023fe0  mov     rcx, cs:WPP_GLOBAL_Control
0x140023fe7  cmp     rcx, r15
0x140023fea  jnz     short loc_14002403D
0x140023fec  movsxd  rdx, ebx
0x140023fef  xor     r9d, r9d
0x140023ff2  xor     r8d, r8d
0x140023ff5  mov     ecx, 20706E70h
0x140023ffa  call    USBSTOR_LogEntry
0x140023fff  mov     eax, ebx
0x140024001  add     rsp, 28h
0x140024005  pop     r15
0x140024007  pop     r14
0x140024009  pop     rdi
0x14002400a  pop     rsi
0x14002400b  pop     rbp
0x14002400c  pop     rbx
0x14002400d  retn
0x14002400f  mov     eax, [r8+2Ch]
0x140024013  test    al, 2
0x140024015  jz      short loc_140023FA1
0x140024017  cmp     byte ptr [r8+29h], 4
0x14002401c  jb      short loc_140023FA1
0x14002401e  movzx   ecx, byte ptr [rsi+1]
0x140024022  call    PnPMinorFunctionString
0x140024027  mov     rcx, [r8+18h]
0x14002402b  mov     r9, rax
0x14002402e  mov     edx, 32h ; '2'
0x140024033  call    WPP_SF_s
0x140024038  jmp     loc_140023FA1
0x14002403d  mov     eax, [rcx+2Ch]
0x140024040  test    al, 2
0x140024042  jz      short loc_140023FEC
0x140024044  cmp     byte ptr [rcx+29h], 4
0x140024048  jb      short loc_140023FEC
0x14002404a  mov     rcx, [rcx+18h]
0x14002404e  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140024055  mov     edx, 37h ; '7'
0x14002405a  mov     r9d, ebx
0x14002405d  call    WPP_SF_d
0x140024062  jmp     short loc_140023FEC
0x140024064  cmp     ecx, 7
0x140024067  jnz     short loc_1400240AF
0x140024069  mov     rdx, rdi; Irp
0x14002406c  mov     rcx, rbx; Object
0x14002406f  call    USBSTOR_PdoQueryDeviceRelations
0x140024074  jmp     loc_140023FDE
0x140024079  cmp     ecx, 9
0x14002407c  jz      short loc_1400240E4
0x14002407e  cmp     ecx, 7
0x140024081  jz      short loc_1400240F4
0x140024083  cmp     ecx, 17h; switch 24 cases
0x140024086  jbe     loc_140024151
0x14002408c  inc     byte ptr [rdi+43h]; jumptable 000000014002416A default case, cases 7-21
0x14002408f  mov     rdx, rdi; Irp
0x140024092  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x14002409a  mov     rcx, [r14+18h]; DeviceObject
0x14002409e  call    cs:__imp_IofCallDriver
0x1400240a5  nop     dword ptr [rax+rax+00h]
0x1400240aa  jmp     loc_140023FDE
0x1400240af  lea     eax, [rcx-1]; switch 25 cases
0x1400240b2  cmp     eax, 18h
0x1400240b5  ja      def_1400240CE; jumptable 00000001400240CE default case, cases 7,8,10,11,13-18,21,24
0x1400240bb  cdqe
0x1400240bd  lea     rdx, cs:140000000h
0x1400240c4  mov     eax, ds:(jpt_1400240CE - 140000000h)[rdx+rax*4]
0x1400240cb  add     rax, rdx
0x1400240ce  jmp     rax; switch jump
0x1400240d4  mov     rdx, rdi; jumptable 00000001400240CE case 19
0x1400240d7  mov     rcx, rbx
0x1400240da  call    USBSTOR_PdoQueryID
0x1400240df  jmp     loc_140023FDE
0x1400240e4  mov     rdx, rdi
0x1400240e7  mov     rcx, rbx
0x1400240ea  call    USBSTOR_FdoQueryCapabilities
0x1400240ef  jmp     loc_140023FDE
0x1400240f4  mov     rdx, rdi
0x1400240f7  mov     rcx, rbx
0x1400240fa  call    USBSTOR_FdoQueryDeviceRelations
0x1400240ff  jmp     loc_140023FDE
0x140024104  mov     rdx, rdi; jumptable 00000001400240CE case 9
0x140024107  mov     rcx, rbx
0x14002410a  call    USBSTOR_PdoQueryCapabilities
0x14002410f  jmp     loc_140023FDE
0x140024114  mov     r8, cs:WPP_GLOBAL_Control; jumptable 00000001400240CE cases 3,6
0x14002411b  cmp     r8, r15
0x14002411e  jnz     loc_1400242EF
0x140024124  xor     eax, eax
0x140024126  mov     ebx, eax
0x140024128  mov     [rdi+30h], eax
0x14002412b  xor     edx, edx; PriorityBoost
0x14002412d  mov     rcx, rdi; Irp
0x140024130  call    cs:__imp_IofCompleteRequest
0x140024137  nop     dword ptr [rax+rax+00h]
0x14002413c  jmp     loc_140023FE0
0x140024141  mov     rdx, rdi; jumptable 00000001400240CE case 20
0x140024144  mov     rcx, rbx
0x140024147  call    USBSTOR_PdoQueryPnpDeviceState
0x14002414c  jmp     loc_140023FDE
0x140024151  lea     rdx, cs:140000000h
0x140024158  movzx   eax, ds:(byte_140017A04 - 140000000h)[rdx+rcx]
0x140024160  mov     ecx, ds:(jpt_14002416A - 140000000h)[rdx+rax*4]
0x140024167  add     rcx, rdx
0x14002416a  jmp     rcx; switch jump
0x140024170  mov     rdx, rdi; jumptable 000000014002416A case 0
0x140024173  mov     rcx, rbx; DeviceObject
0x140024176  call    USBSTOR_FdoStartDevice
0x14002417b  jmp     loc_140023FDE
0x140024180  mov     rdx, rdi; jumptable 000000014002416A case 4
0x140024183  mov     rcx, rbx; DeviceObject
0x140024186  call    USBSTOR_FdoStopDevice
0x14002418b  jmp     loc_140023FDE
0x140024190  mov     rdx, rdi; jumptable 000000014002416A case 2
0x140024193  mov     rcx, rbx; DeviceObject
0x140024196  call    USBSTOR_FdoRemoveDevice
0x14002419b  jmp     loc_140023FDE
0x1400241a0  mov     rdx, rdi; jumptable 000000014002416A cases 1,5
0x1400241a3  mov     rcx, rbx
0x1400241a6  call    USBSTOR_FdoQueryStopRemoveDevice
0x1400241ab  jmp     loc_140023FDE
0x1400241b0  mov     rdx, rdi; jumptable 000000014002416A cases 3,6
0x1400241b3  mov     rcx, rbx
0x1400241b6  call    USBSTOR_FdoCancelStopRemoveDevice
0x1400241bb  jmp     loc_140023FDE
0x1400241c0  mov     rdx, rdi; jumptable 000000014002416A case 22
0x1400241c3  mov     rcx, rbx; DeviceObject
0x1400241c6  call    USBSTOR_FdoDeviceUsageNotification
0x1400241cb  jmp     loc_140023FDE
0x1400241d0  xor     eax, eax; jumptable 000000014002416A case 23
0x1400241d2  mov     [rdi+30h], eax
0x1400241d5  jmp     def_14002416A; jumptable 000000014002416A default case, cases 7-21
0x1400241da  mov     rdx, rdi; jumptable 00000001400240CE case 12
0x1400241dd  mov     rcx, rbx
0x1400241e0  call    USBSTOR_PdoQueryDeviceText
0x1400241e5  jmp     loc_140023FDE
0x1400241ea  mov     dword ptr [r14+28h], 2; jumptable 00000001400240CE case 25
0x1400241f2  jmp     loc_140024124
0x1400241f7  cmp     dword ptr [r14+28h], 8; jumptable 00000001400240CE case 2
0x1400241fc  jz      loc_140024124
0x140024202  mov     rcx, cs:WPP_GLOBAL_Control
0x140024209  cmp     rcx, r15
0x14002420c  jz      short loc_140024230
0x14002420e  mov     eax, [rcx+2Ch]
0x140024211  test    al, 2
0x140024213  jz      short loc_140024230
0x140024215  cmp     byte ptr [rcx+29h], 4
0x140024219  jb      short loc_140024230
0x14002421b  mov     rcx, [rcx+18h]
0x14002421f  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140024226  mov     edx, 33h ; '3'
0x14002422b  call    WPP_SF_
0x140024230  xor     r9d, r9d
0x140024233  mov     r8, rdi
0x140024236  mov     rdx, rbx
0x140024239  mov     ecx, 20564452h
0x14002423e  call    USBSTOR_LogEntry
0x140024243  lea     rdx, [r14+170h]
0x14002424a  mov     rcx, rbx
0x14002424d  call    UsbQueueFlush
0x140024252  mov     rdx, rdi; Irp
0x140024255  mov     rcx, rbx; DeviceObject
0x140024258  call    USBSTOR_PdoRemoveDevice
0x14002425d  jmp     loc_140023FDE
0x140024262  mov     rdx, rdi; jumptable 00000001400240CE case 4
0x140024265  mov     rcx, rbx; DeviceObject
0x140024268  call    USBSTOR_PdoStopDevice
0x14002426d  jmp     loc_140023FDE
0x140024272  mov     rdx, rdi; jumptable 00000001400240CE case 22
0x140024275  mov     rcx, rbx; DeviceObject
0x140024278  call    USBSTOR_PdoDeviceUsageNotification
0x14002427d  jmp     loc_140023FDE
0x140024282  mov     rdx, rdi; jumptable 00000001400240CE cases 1,5
0x140024285  mov     rcx, rbx
0x140024288  call    USBSTOR_PdoQueryStopRemoveDevice
0x14002428d  jmp     loc_140023FDE
0x140024292  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 00000001400240CE case 23
0x140024299  cmp     rcx, r15
0x14002429c  jz      short loc_1400242C0
0x14002429e  mov     eax, [rcx+2Ch]
0x1400242a1  test    al, 2
0x1400242a3  jz      short loc_1400242C0
0x1400242a5  cmp     byte ptr [rcx+29h], 4
0x1400242a9  jb      short loc_1400242C0
0x1400242ab  mov     rcx, [rcx+18h]
0x1400242af  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400242b6  mov     edx, 34h ; '4'
0x1400242bb  call    WPP_SF_
0x1400242c0  xor     r9d, r9d
0x1400242c3  mov     r8, rdi
0x1400242c6  mov     rdx, rbx
0x1400242c9  mov     ecx, 56445253h
0x1400242ce  call    USBSTOR_LogEntry
0x1400242d3  lea     rdx, [r14+170h]
0x1400242da  mov     rcx, rbx
0x1400242dd  call    UsbQueueFlush
0x1400242e2  mov     dword ptr [r14+28h], 7
0x1400242ea  jmp     loc_140024114; jumptable 00000001400240CE cases 3,6
0x1400242ef  mov     eax, [r8+2Ch]
0x1400242f3  test    al, 2
0x1400242f5  jz      loc_140024124
0x1400242fb  cmp     byte ptr [r8+29h], 4
0x140024300  jb      loc_140024124
0x140024306  movzx   ecx, byte ptr [rsi+1]
0x14002430a  call    PnPMinorFunctionString
0x14002430f  mov     rcx, [r8+18h]
0x140024313  mov     r9, rax
0x140024316  mov     edx, 35h ; '5'
0x14002431b  call    WPP_SF_s
0x140024320  jmp     loc_140024124
0x140024325  mov     r8, cs:WPP_GLOBAL_Control; jumptable 00000001400240CE default case, cases 7,8,10,11,13-18,21,24
0x14002432c  cmp     r8, r15
0x14002432f  jz      short loc_140024356
0x140024331  mov     eax, [r8+2Ch]
0x140024335  test    al, 2
0x140024337  jz      short loc_140024356
0x140024339  cmp     byte ptr [r8+29h], 3
0x14002433e  jb      short loc_140024356
0x140024340  call    PnPMinorFunctionString
0x140024345  mov     rcx, [r8+18h]
0x140024349  mov     r9, rax
0x14002434c  mov     edx, 36h ; '6'
0x140024351  call    WPP_SF_s
0x140024356  mov     ebx, [rdi+30h]
0x140024359  jmp     loc_14002412B
```
