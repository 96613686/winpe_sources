# USBSTOR_CreateChildPDO

- ea: `0x1400269ec`
- end: `0x140026ce6`
- name: `USBSTOR_CreateChildPDO`
- size: `762`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140025738`

## callees

- `0x140003630`
- `0x1400105e8`
- `0x140010e74`
- `0x140013d40`
- `0x14001f66c`
- `0x1400218f8`
- `0x1400259cc`
- `0x1400263a4`
- `0x1400269ec`

## import_xrefs

- `ntoskrnl!IoInitializeRemoveLockEx` at `0x140026c77`
- `ntoskrnl!IoInitializeRemoveLockEx` at `0x140026c77`
- `ntoskrnl!IoCreateDevice` at `0x140026b20`
- `ntoskrnl!IoCreateDevice` at `0x140026b20`

## pseudocode

```c
NTSTATUS __fastcall USBSTOR_CreateChildPDO(
        __int64 a1,
        unsigned __int8 a2,
        char a3,
        _BYTE *a4,
        _BYTE *a5,
        __int64 a6,
        __int64 a7,
        _DWORD *a8)
{
  __int64 v8; // r15
  __int64 v12; // rsi
  _BYTE *v13; // r13
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  NTSTATUS result; // eax
  struct _IO_REMOVE_LOCK *DeviceExtension; // rbx
  struct _LIST_ENTRY ***v18; // rdx
  int InquiryData; // eax
  __int64 v20; // r14
  char v21; // cl
  PDEVICE_OBJECT v22; // rax
  PDEVICE_OBJECT DeviceObject; // [rsp+90h] [rbp+48h] BYREF

  v8 = a2;
  DeviceObject = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  USBSTOR_LogEntry(1146110787, a1, v8, 0);
  v12 = *(_QWORD *)(a1 + 64);
  v13 = a5;
  *a4 = 0;
  *v13 = 0;
  if ( *(_DWORD *)(v12 + 1872) )
  {
    if ( !a3 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        return -1073741823;
      }
      v15 = 88;
LABEL_18:
      WPP_SF_q(v14->AttachedDevice, v15, WPP_354602438fa331ce245c005e63ec86c9_Traceguids, a1);
      return -1073741823;
    }
  }
  else if ( !a3 )
  {
    goto LABEL_20;
  }
  if ( *(_DWORD *)(v12 + 1868) && !*(_BYTE *)(v12 + 1866) )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      return -1073741823;
    }
    v15 = 89;
    goto LABEL_18;
  }
LABEL_20:
  result = IoCreateDevice(*(PDRIVER_OBJECT *)(a1 + 8), 0x338u, 0, 0x2Du, 0x180u, 0, &DeviceObject);
  if ( result >= 0 )
  {
    DeviceObject->StackSize = *(_BYTE *)(a1 + 76);
    DeviceExtension = (struct _IO_REMOVE_LOCK *)DeviceObject->DeviceExtension;
    memset(&DeviceExtension->Common.IoCount, 0, 0x334u);
    *(_DWORD *)&DeviceExtension->Common.Removed = 558842960;
    *(_QWORD *)&DeviceExtension->Common.RemoveEvent.Header.Lock = DeviceObject;
    DeviceExtension[1].Common.RemoveEvent.Header.SignalState = 1;
    LODWORD(DeviceExtension[1].Common.RemoveEvent.Header.WaitListHead.Flink) = 1;
    DeviceExtension[1].Common.RemoveEvent.Header.LockNV = 1;
    DeviceExtension->Common.RemoveEvent.Header.WaitListHead.Flink = (struct _LIST_ENTRY *)a1;
    BYTE2(DeviceExtension[2].Common.IoCount) = a3;
    DeviceExtension[25].Common.IoCount = 255;
    v18 = *(struct _LIST_ENTRY ****)(v12 + 40);
    if ( *v18 != (struct _LIST_ENTRY **)(v12 + 32) )
      __fastfail(3u);
    DeviceExtension->Common.RemoveEvent.Header.WaitListHead.Blink = (struct _LIST_ENTRY *)(v12 + 32);
    *(_QWORD *)&DeviceExtension[1].Common.Removed = v18;
    *v18 = &DeviceExtension->Common.RemoveEvent.Header.WaitListHead.Blink;
    *(_QWORD *)(v12 + 40) = &DeviceExtension->Common.RemoveEvent.Header.WaitListHead.Blink;
    DeviceObject->Flags |= 0x10u;
    DeviceObject->Flags |= 0x2000u;
    DeviceObject->Flags &= ~0x80u;
    HIBYTE(DeviceExtension[2].Common.IoCount) = v8;
    UsbQueueInitialize(&DeviceExtension[11].Common.RemoveEvent.Header.WaitListHead);
    InquiryData = USBSTOR_GetInquiryData(DeviceObject);
    v20 = InquiryData;
    if ( InquiryData >= 0 )
    {
      *a8 = LOBYTE(DeviceExtension[2].Common.RemoveEvent.Header.SignalState);
      v21 = DeviceExtension[2].Common.RemoveEvent.Header.Type & 0x1F;
      if ( v21 )
      {
        if ( (unsigned __int8)(v21 - 4) <= 1u || (unsigned __int8)(v21 - 7) <= 1u )
          *a4 = 1;
      }
      else
      {
        BYTE1(DeviceExtension[2].Common.IoCount) = USBSTOR_IsFloppyDevice(DeviceObject);
      }
      if ( (*(_DWORD *)(v12 + 132) & 0x40) != 0 )
        DeviceExtension[2].Common.RemoveEvent.Header.Signalling &= ~0x80u;
      if ( (DeviceExtension[2].Common.RemoveEvent.Header.Signalling & 0x80u) != 0 )
      {
        v22 = DeviceObject;
        *v13 = 1;
        v22->Characteristics |= 1u;
      }
      if ( (*(_DWORD *)(v12 + 132) & 0x10) == 0 )
        USBSTOR_GetDeviceSerialNumber((__int64)DeviceObject);
    }
    IoInitializeRemoveLockEx(DeviceExtension + 23, 0x53627355u, 0xAu, 0xFFFFFFFu, 0x20u);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 90, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
    }
    USBSTOR_LogEntry(1685087075, a1, DeviceObject, v20);
    return v20;
  }
  return result;
}

```

## disassembly

```asm
0x1400269ec  push    rbp
0x1400269ee  push    rbx
0x1400269ef  push    rsi
0x1400269f0  push    rdi
0x1400269f1  push    r12
0x1400269f3  push    r13
0x1400269f5  push    r14
0x1400269f7  push    r15
0x1400269f9  mov     rbp, rsp
0x1400269fc  sub     rsp, 48h
0x140026a00  xor     ebx, ebx
0x140026a02  movzx   r15d, dl
0x140026a06  mov     [rbp+arg_0], rbx
0x140026a0a  mov     r12, r9
0x140026a0d  mov     r14b, r8b
0x140026a10  mov     rdi, rcx
0x140026a13  mov     rcx, cs:WPP_GLOBAL_Control
0x140026a1a  lea     rax, WPP_GLOBAL_Control
0x140026a21  cmp     rcx, rax
0x140026a24  jz      short loc_140026A4B
0x140026a26  test    dword ptr [rcx+2Ch], 100h
0x140026a2d  jz      short loc_140026A4B
0x140026a2f  cmp     byte ptr [rcx+29h], 4
0x140026a33  jb      short loc_140026A4B
0x140026a35  mov     rcx, [rcx+18h]
0x140026a39  lea     edx, [rbx+57h]
0x140026a3c  mov     r9d, r15d
0x140026a3f  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140026a46  call    WPP_SF_d
0x140026a4b  mov     r8, r15
0x140026a4e  xor     r9d, r9d
0x140026a51  mov     rdx, rdi
0x140026a54  mov     ecx, 44504343h
0x140026a59  call    USBSTOR_LogEntry
0x140026a5e  mov     rsi, [rdi+40h]
0x140026a62  mov     r13, [rbp+arg_20]
0x140026a66  mov     [r12], bl
0x140026a6a  mov     [r13+0], bl
0x140026a6e  cmp     [rsi+750h], ebx
0x140026a74  jz      short loc_140026AA2
0x140026a76  test    r14b, r14b
0x140026a79  jnz     short loc_140026AA7
0x140026a7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140026a82  lea     rax, WPP_GLOBAL_Control
0x140026a89  cmp     rcx, rax
0x140026a8c  jz      short loc_140026AEF
0x140026a8e  mov     eax, [rcx+2Ch]
0x140026a91  test    al, 2
0x140026a93  jz      short loc_140026AEF
0x140026a95  cmp     byte ptr [rcx+29h], 2
0x140026a99  jb      short loc_140026AEF
0x140026a9b  mov     edx, 58h ; 'X'
0x140026aa0  jmp     short loc_140026ADC
0x140026aa2  test    r14b, r14b
0x140026aa5  jz      short loc_140026AF9
0x140026aa7  cmp     [rsi+74Ch], ebx
0x140026aad  jz      short loc_140026AF9
0x140026aaf  cmp     [rsi+74Ah], bl
0x140026ab5  jnz     short loc_140026AF9
0x140026ab7  mov     rcx, cs:WPP_GLOBAL_Control
0x140026abe  lea     rax, WPP_GLOBAL_Control
0x140026ac5  cmp     rcx, rax
0x140026ac8  jz      short loc_140026AEF
0x140026aca  mov     eax, [rcx+2Ch]
0x140026acd  test    al, 2
0x140026acf  jz      short loc_140026AEF
0x140026ad1  cmp     byte ptr [rcx+29h], 2
0x140026ad5  jb      short loc_140026AEF
0x140026ad7  mov     edx, 59h ; 'Y'
0x140026adc  mov     rcx, [rcx+18h]
0x140026ae0  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140026ae7  mov     r9, rdi
0x140026aea  call    WPP_SF_q
0x140026aef  mov     eax, 0C0000001h
0x140026af4  jmp     loc_140026CD4
0x140026af9  mov     rcx, [rdi+8]; DriverObject
0x140026afd  lea     rax, [rbp+arg_0]
0x140026b01  mov     [rsp+48h+DeviceObject], rax; DeviceObject
0x140026b06  mov     r9d, 2Dh ; '-'; DeviceType
0x140026b0c  mov     [rsp+48h+Exclusive], bl; Exclusive
0x140026b10  xor     r8d, r8d; DeviceName
0x140026b13  mov     edx, 338h; DeviceExtensionSize
0x140026b18  mov     [rsp+48h+DeviceCharacteristics], 180h; DeviceCharacteristics
0x140026b20  call    cs:__imp_IoCreateDevice
0x140026b27  nop     dword ptr [rax+rax+00h]
0x140026b2c  test    eax, eax
0x140026b2e  js      loc_140026CD4
0x140026b34  mov     rax, [rbp+arg_0]
0x140026b38  xor     edx, edx; Val
0x140026b3a  mov     cl, [rdi+4Ch]
0x140026b3d  mov     r8d, 334h; Size
0x140026b43  mov     [rax+4Ch], cl
0x140026b46  mov     rax, [rbp+arg_0]
0x140026b4a  mov     rbx, [rax+40h]
0x140026b4e  lea     rcx, [rbx+4]; void *
0x140026b52  call    memset
0x140026b57  mov     dword ptr [rbx], 214F4450h
0x140026b5d  lea     rcx, [rsi+20h]
0x140026b61  mov     rax, [rbp+arg_0]
0x140026b65  mov     [rbx+8], rax
0x140026b69  mov     eax, 1
0x140026b6e  mov     [rbx+2Ch], eax
0x140026b71  mov     [rbx+30h], eax
0x140026b74  mov     [rbx+28h], eax
0x140026b77  mov     [rbx+10h], rdi
0x140026b7b  mov     [rbx+46h], r14b
0x140026b7f  mov     dword ptr [rbx+324h], 0FFh
0x140026b89  mov     rdx, [rcx+8]
0x140026b8d  cmp     [rdx], rcx
0x140026b90  jz      short loc_140026B97
0x140026b92  lea     ecx, [rax+2]
0x140026b95  int     29h; Win8: RtlFailFast(ecx)
0x140026b97  lea     rax, [rbx+18h]
0x140026b9b  mov     [rax], rcx
0x140026b9e  mov     [rax+8], rdx
0x140026ba2  mov     [rdx], rax
0x140026ba5  mov     [rcx+8], rax
0x140026ba9  lea     rcx, [rbx+170h]
0x140026bb0  mov     rax, [rbp+arg_0]
0x140026bb4  or      dword ptr [rax+30h], 10h
0x140026bb8  mov     rax, [rbp+arg_0]
0x140026bbc  bts     dword ptr [rax+30h], 0Dh
0x140026bc1  mov     rax, [rbp+arg_0]
0x140026bc5  btr     dword ptr [rax+30h], 7
0x140026bca  mov     [rbx+47h], r15b
0x140026bce  call    UsbQueueInitialize
0x140026bd3  mov     rcx, [rbp+arg_0]; DeviceObject
0x140026bd7  call    USBSTOR_GetInquiryData
0x140026bdc  movsxd  r14, eax
0x140026bdf  test    eax, eax
0x140026be1  js      short loc_140026C57
0x140026be3  mov     rcx, [rbp+arg_38]
0x140026bea  movzx   edx, byte ptr [rbx+4Ch]
0x140026bee  mov     [rcx], edx
0x140026bf0  mov     cl, [rbx+48h]
0x140026bf3  and     cl, 1Fh
0x140026bf6  jnz     short loc_140026C0E
0x140026bf8  mov     r8, [rbp+arg_30]
0x140026bfc  mov     rdx, [rbp+arg_28]
0x140026c00  mov     rcx, [rbp+arg_0]; DeviceObject
0x140026c04  call    USBSTOR_IsFloppyDevice
0x140026c09  mov     [rbx+45h], al
0x140026c0c  jmp     short loc_140026C22
0x140026c0e  lea     eax, [rcx-4]
0x140026c11  cmp     al, 1
0x140026c13  jbe     short loc_140026C1D
0x140026c15  sub     cl, 7
0x140026c18  cmp     cl, 1
0x140026c1b  ja      short loc_140026C22
0x140026c1d  mov     byte ptr [r12], 1
0x140026c22  mov     eax, [rsi+84h]
0x140026c28  test    al, 40h
0x140026c2a  jz      short loc_140026C30
0x140026c2c  and     byte ptr [rbx+49h], 7Fh
0x140026c30  mov     al, [rbx+49h]
0x140026c33  test    al, al
0x140026c35  jns     short loc_140026C44
0x140026c37  mov     rax, [rbp+arg_0]
0x140026c3b  mov     byte ptr [r13+0], 1
0x140026c40  or      dword ptr [rax+34h], 1
0x140026c44  mov     eax, [rsi+84h]
0x140026c4a  test    al, 10h
0x140026c4c  jnz     short loc_140026C57
0x140026c4e  mov     rcx, [rbp+arg_0]
0x140026c52  call    USBSTOR_GetDeviceSerialNumber
0x140026c57  lea     rcx, [rbx+2E0h]; Lock
0x140026c5e  mov     [rsp+48h+DeviceCharacteristics], 20h ; ' '; RemlockSize
0x140026c66  mov     edx, 53627355h; AllocateTag
0x140026c6b  mov     r9d, 0FFFFFFFh; HighWatermark
0x140026c71  mov     r8d, 0Ah; MaxLockedMinutes
0x140026c77  call    cs:__imp_IoInitializeRemoveLockEx
0x140026c7e  nop     dword ptr [rax+rax+00h]
0x140026c83  mov     rcx, cs:WPP_GLOBAL_Control
0x140026c8a  lea     rax, WPP_GLOBAL_Control
0x140026c91  cmp     rcx, rax
0x140026c94  jz      short loc_140026CBD
0x140026c96  test    dword ptr [rcx+2Ch], 100h
0x140026c9d  jz      short loc_140026CBD
0x140026c9f  cmp     byte ptr [rcx+29h], 4
0x140026ca3  jb      short loc_140026CBD
0x140026ca5  mov     rcx, [rcx+18h]
0x140026ca9  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140026cb0  mov     edx, 5Ah ; 'Z'
0x140026cb5  mov     r9d, r14d
0x140026cb8  call    WPP_SF_d
0x140026cbd  mov     r8, [rbp+arg_0]
0x140026cc1  mov     r9, r14
0x140026cc4  mov     rdx, rdi
0x140026cc7  mov     ecx, 64706363h
0x140026ccc  call    USBSTOR_LogEntry
0x140026cd1  mov     eax, r14d
0x140026cd4  add     rsp, 48h
0x140026cd8  pop     r15
0x140026cda  pop     r14
0x140026cdc  pop     r13
0x140026cde  pop     r12
0x140026ce0  pop     rdi
0x140026ce1  pop     rsi
0x140026ce2  pop     rbx
0x140026ce3  pop     rbp
0x140026ce4  retn
```
