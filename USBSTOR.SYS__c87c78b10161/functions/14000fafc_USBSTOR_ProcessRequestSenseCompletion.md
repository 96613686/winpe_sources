# USBSTOR_ProcessRequestSenseCompletion

- ea: `0x14000fafc`
- end: `0x14000fc44`
- name: `USBSTOR_ProcessRequestSenseCompletion`
- size: `328`
- prototype: `__int64 __fastcall(PVOID Object, PIRP Irp)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009cb0`
- `0x14000c120`

## callees

- `0x140001008`
- `0x140003630`
- `0x140003b90`
- `0x140004910`
- `0x140007ff0`
- `0x14000bdc0`
- `0x14000d7e4`
- `0x14000fafc`

## pseudocode

```c
__int64 __fastcall USBSTOR_ProcessRequestSenseCompletion(struct _DEVICE_OBJECT *Object, PIRP Irp, __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  char v7; // r14
  _BYTE *DeviceExtension; // rdi
  PIO_SECURITY_CONTEXT SecurityContext; // r15
  PUNICODE_STRING FileName; // r12
  __int64 v12; // r8
  unsigned int Status; // ebx
  char v14; // al
  __int64 v15; // rcx

  USBSTOR_LogEntry(1129534032, Object, Irp, 0);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v7 = 1;
  DeviceExtension = Object->DeviceExtension;
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  if ( a3 != 1 )
  {
    FileName = CurrentStackLocation->Parameters.QueryDirectory.FileName;
    v12 = (__int64)CurrentStackLocation->Parameters.Create.SecurityContext;
    BYTE3(SecurityContext->SecurityQos) |= 0x80u;
    USBSTOR_TranslateCDBComplete(Object, (__int64)Irp, v12);
    Status = Irp->IoStatus.Status;
    Irp->IoStatus.Information = SecurityContext->DesiredAccess;
    if ( (DeviceExtension[1208] & 0xF) == 6 )
    {
      v14 = DeviceExtension[1218];
      if ( v14 == 40 )
      {
        if ( !DeviceExtension[1812] && (*((_DWORD *)DeviceExtension + 33) & 2) != 0 )
        {
          USBSTOR_LogEntry(846426736, Object, Irp, SecurityContext);
          USBSTOR_QueueResetDevice(Object, FileName);
          return Status;
        }
      }
      else if ( v14 == 41 )
      {
        v15 = 863203952;
LABEL_14:
        USBSTOR_LogEntry(v15, Object, Irp, SecurityContext);
        DeviceExtension[1812] = v7;
        USBSTOR_SetSrbPending(DeviceExtension, 0);
        UsbStorPumpNextRequest(FileName);
        UsbStorStartNextPacket(Object);
        return Status;
      }
    }
    v7 = 0;
    v15 = 879981168;
    goto LABEL_14;
  }
  USBSTOR_LogEntry(829649520, Object, Irp, CurrentStackLocation->Parameters.WMI.ProviderId);
  if ( (DeviceExtension[1208] & 0xF) == 6 && DeviceExtension[1218] == 41 )
    DeviceExtension[1812] = 1;
  USBSTOR_IssueClientCdb(Object, Irp);
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000fafc  push    rbx
0x14000fafe  push    rbp
0x14000faff  push    rsi
0x14000fb00  push    rdi
0x14000fb01  push    r12
0x14000fb03  push    r14
0x14000fb05  push    r15
0x14000fb07  sub     rsp, 20h
0x14000fb0b  mov     rbx, r8
0x14000fb0e  mov     rbp, rdx
0x14000fb11  mov     r8, rdx
0x14000fb14  mov     rsi, rcx
0x14000fb17  mov     rdx, rcx
0x14000fb1a  xor     r9d, r9d
0x14000fb1d  mov     ecx, 43535250h
0x14000fb22  call    USBSTOR_LogEntry
0x14000fb27  mov     rax, [rbp+0B8h]
0x14000fb2e  mov     r14d, 1
0x14000fb34  mov     rdi, [rsi+40h]
0x14000fb38  mov     r15, [rax+8]
0x14000fb3c  cmp     rbx, r14
0x14000fb3f  jnz     short loc_14000FB85
0x14000fb41  mov     r9, r15
0x14000fb44  mov     r8, rbp
0x14000fb47  mov     rdx, rsi
0x14000fb4a  mov     ecx, 31737270h
0x14000fb4f  call    USBSTOR_LogEntry
0x14000fb54  mov     al, [rdi+4B8h]
0x14000fb5a  and     al, 0Fh
0x14000fb5c  cmp     al, 6
0x14000fb5e  jnz     short loc_14000FB70
0x14000fb60  cmp     byte ptr [rdi+4C2h], 29h ; ')'
0x14000fb67  jnz     short loc_14000FB70
0x14000fb69  mov     [rdi+714h], r14b
0x14000fb70  mov     rdx, rbp; Irp
0x14000fb73  mov     rcx, rsi; Object
0x14000fb76  call    USBSTOR_IssueClientCdb
0x14000fb7b  mov     eax, 0C0000016h
0x14000fb80  jmp     loc_14000FC34
0x14000fb85  mov     r12, [rax+10h]
0x14000fb89  mov     r8, r15
0x14000fb8c  or      byte ptr [r15+3], 80h
0x14000fb91  mov     rdx, rbp
0x14000fb94  mov     rcx, rsi; Object
0x14000fb97  call    USBSTOR_TranslateCDBComplete
0x14000fb9c  mov     eax, [r15+10h]
0x14000fba0  mov     ebx, [rbp+30h]
0x14000fba3  mov     [rbp+38h], rax
0x14000fba7  mov     al, [rdi+4B8h]
0x14000fbad  and     al, 0Fh
0x14000fbaf  cmp     al, 6
0x14000fbb1  jnz     short loc_14000FBFB
0x14000fbb3  mov     al, [rdi+4C2h]
0x14000fbb9  cmp     al, 28h ; '('
0x14000fbbb  jnz     short loc_14000FBF0
0x14000fbbd  cmp     byte ptr [rdi+714h], 0
0x14000fbc4  jnz     short loc_14000FBFB
0x14000fbc6  mov     eax, [rdi+84h]
0x14000fbcc  test    al, 2
0x14000fbce  jz      short loc_14000FBFB
0x14000fbd0  mov     r9, r15
0x14000fbd3  mov     r8, rbp
0x14000fbd6  mov     rdx, rsi
0x14000fbd9  mov     ecx, 32737270h
0x14000fbde  call    USBSTOR_LogEntry
0x14000fbe3  mov     rdx, r12; Context
0x14000fbe6  mov     rcx, rsi; Object
0x14000fbe9  call    USBSTOR_QueueResetDevice
0x14000fbee  jmp     short loc_14000FC32
0x14000fbf0  cmp     al, 29h ; ')'
0x14000fbf2  jnz     short loc_14000FBFB
0x14000fbf4  mov     ecx, 33737270h
0x14000fbf9  jmp     short loc_14000FC03
0x14000fbfb  xor     r14b, r14b
0x14000fbfe  mov     ecx, 34737270h
0x14000fc03  mov     r9, r15
0x14000fc06  mov     r8, rbp
0x14000fc09  mov     rdx, rsi
0x14000fc0c  call    USBSTOR_LogEntry
0x14000fc11  xor     edx, edx
0x14000fc13  mov     [rdi+714h], r14b
0x14000fc1a  mov     rcx, rdi
0x14000fc1d  call    USBSTOR_SetSrbPending
0x14000fc22  mov     rcx, r12
0x14000fc25  call    UsbStorPumpNextRequest
0x14000fc2a  mov     rcx, rsi; DeviceObject
0x14000fc2d  call    UsbStorStartNextPacket
0x14000fc32  mov     eax, ebx
0x14000fc34  add     rsp, 20h
0x14000fc38  pop     r15
0x14000fc3a  pop     r14
0x14000fc3c  pop     r12
0x14000fc3e  pop     rdi
0x14000fc3f  pop     rsi
0x14000fc40  pop     rbp
0x14000fc41  pop     rbx
0x14000fc42  retn
```
