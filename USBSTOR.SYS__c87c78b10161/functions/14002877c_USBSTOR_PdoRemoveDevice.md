# USBSTOR_PdoRemoveDevice

- ea: `0x14002877c`
- end: `0x140028903`
- name: `USBSTOR_PdoRemoveDevice`
- size: `391`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140023f70`

## callees

- `0x140003630`
- `0x14000811c`
- `0x14000a08c`
- `0x1400105e8`
- `0x140010664`
- `0x1400217c8`
- `0x14002877c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400288a7`
- `ntoskrnl!IofCompleteRequest` at `0x1400288a7`
- `ntoskrnl!IoFreeWorkItem` at `0x140028884`
- `ntoskrnl!IoFreeWorkItem` at `0x140028884`

## pseudocode

```c
__int64 __fastcall USBSTOR_PdoRemoveDevice(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  __int64 v4; // rcx
  char *DeviceExtension; // rbx
  struct _IO_WORKITEM *v6; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 121, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  v4 = *((_QWORD *)DeviceObject->DeviceExtension + 2);
  if ( (*(_DWORD *)(*(_QWORD *)(v4 + 64) + 132LL) & 0x20) != 0
    && (int)USBSTOR_IsDeviceConnected(v4) >= 0
    && Irp->Tail.Overlay.CurrentStackLocation->MinorFunction
    && (int)USBSTOR_EjectMedia(DeviceObject) < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 122, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 123, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  UsbQueueFlush(DeviceObject, DeviceExtension + 368);
  v6 = (struct _IO_WORKITEM *)*((_QWORD *)DeviceExtension + 91);
  DeviceExtension[68] = 0;
  *((_DWORD *)DeviceExtension + 10) = 8;
  if ( v6 )
  {
    IoFreeWorkItem(v6);
    *((_QWORD *)DeviceExtension + 91) = 0;
  }
  Irp->IoStatus.Status = 0;
  IofCompleteRequest(Irp, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 124, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1684894320, 0, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x14002877c  push    rbx
0x14002877e  push    rsi
0x14002877f  push    rdi
0x140028780  push    r15
0x140028782  sub     rsp, 28h
0x140028786  mov     rsi, rdx
0x140028789  mov     rdi, rcx
0x14002878c  mov     rcx, cs:WPP_GLOBAL_Control
0x140028793  lea     r15, WPP_GLOBAL_Control
0x14002879a  cmp     rcx, r15
0x14002879d  jz      short loc_1400287C1
0x14002879f  mov     eax, [rcx+2Ch]
0x1400287a2  test    al, 2
0x1400287a4  jz      short loc_1400287C1
0x1400287a6  cmp     byte ptr [rcx+29h], 4
0x1400287aa  jb      short loc_1400287C1
0x1400287ac  mov     rcx, [rcx+18h]
0x1400287b0  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400287b7  mov     edx, 79h ; 'y'
0x1400287bc  call    WPP_SF_
0x1400287c1  mov     rax, [rdi+40h]
0x1400287c5  mov     rcx, [rax+10h]
0x1400287c9  mov     rax, [rcx+40h]
0x1400287cd  mov     edx, [rax+84h]
0x1400287d3  test    dl, 20h
0x1400287d6  jz      short loc_14002882C
0x1400287d8  call    USBSTOR_IsDeviceConnected
0x1400287dd  test    eax, eax
0x1400287df  js      short loc_14002882C
0x1400287e1  mov     rax, [rsi+0B8h]
0x1400287e8  cmp     byte ptr [rax+1], 0
0x1400287ec  jz      short loc_14002882C
0x1400287ee  mov     rcx, rdi; DeviceObject
0x1400287f1  call    USBSTOR_EjectMedia
0x1400287f6  test    eax, eax
0x1400287f8  jns     short loc_14002882C
0x1400287fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140028801  cmp     rcx, r15
0x140028804  jz      short loc_14002882C
0x140028806  mov     edx, [rcx+2Ch]
0x140028809  test    dl, 1
0x14002880c  jz      short loc_14002882C
0x14002880e  cmp     byte ptr [rcx+29h], 3
0x140028812  jb      short loc_14002882C
0x140028814  mov     rcx, [rcx+18h]
0x140028818  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14002881f  mov     edx, 7Ah ; 'z'
0x140028824  mov     r9d, eax
0x140028827  call    WPP_SF_d
0x14002882c  mov     rbx, [rdi+40h]
0x140028830  mov     rcx, cs:WPP_GLOBAL_Control
0x140028837  cmp     rcx, r15
0x14002883a  jz      short loc_14002885E
0x14002883c  mov     eax, [rcx+2Ch]
0x14002883f  test    al, 2
0x140028841  jz      short loc_14002885E
0x140028843  cmp     byte ptr [rcx+29h], 4
0x140028847  jb      short loc_14002885E
0x140028849  mov     rcx, [rcx+18h]
0x14002884d  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140028854  mov     edx, 7Bh ; '{'
0x140028859  call    WPP_SF_
0x14002885e  lea     rdx, [rbx+170h]
0x140028865  mov     rcx, rdi
0x140028868  call    UsbQueueFlush
0x14002886d  mov     rcx, [rbx+2D8h]; IoWorkItem
0x140028874  mov     byte ptr [rbx+44h], 0
0x140028878  mov     dword ptr [rbx+28h], 8
0x14002887f  test    rcx, rcx
0x140028882  jz      short loc_14002889B
0x140028884  call    cs:__imp_IoFreeWorkItem
0x14002888b  nop     dword ptr [rax+rax+00h]
0x140028890  mov     qword ptr [rbx+2D8h], 0
0x14002889b  xor     edx, edx; PriorityBoost
0x14002889d  mov     dword ptr [rsi+30h], 0
0x1400288a4  mov     rcx, rsi; Irp
0x1400288a7  call    cs:__imp_IofCompleteRequest
0x1400288ae  nop     dword ptr [rax+rax+00h]
0x1400288b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400288ba  cmp     rcx, r15
0x1400288bd  jz      short loc_1400288E4
0x1400288bf  mov     eax, [rcx+2Ch]
0x1400288c2  test    al, 2
0x1400288c4  jz      short loc_1400288E4
0x1400288c6  cmp     byte ptr [rcx+29h], 4
0x1400288ca  jb      short loc_1400288E4
0x1400288cc  mov     rcx, [rcx+18h]
0x1400288d0  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400288d7  mov     edx, 7Ch ; '|'
0x1400288dc  xor     r9d, r9d
0x1400288df  call    WPP_SF_d
0x1400288e4  xor     r9d, r9d
0x1400288e7  xor     r8d, r8d
0x1400288ea  xor     edx, edx
0x1400288ec  mov     ecx, 646D7270h
0x1400288f1  call    USBSTOR_LogEntry
0x1400288f6  xor     eax, eax
0x1400288f8  add     rsp, 28h
0x1400288fc  pop     r15
0x1400288fe  pop     rdi
0x1400288ff  pop     rsi
0x140028900  pop     rbx
0x140028901  retn
```
