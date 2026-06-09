# USBD_CreateHandle

- ea: `0x14000cd68`
- end: `0x14000d181`
- name: `USBD_CreateHandle`
- size: `1049`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PDEVICE_OBJECT TargetDeviceObject, ULONG USBDClientContractVersion, ULONG PoolTag, USBD_HANDLE *USBDHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1400015cc`

## callees

- `0x14000c550`
- `0x14000c9f0`
- `0x14000cd68`
- `0x14000d7f0`
- `0x14000d830`
- `0x14000dc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d16d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d16d`
- `ntoskrnl!RtlGetVersion` at `0x14000ce0f`
- `ntoskrnl!RtlGetVersion` at `0x14000ce0f`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000cda5`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000cda5`
- `ntoskrnl!DbgPrintEx` at `0x14000cdcd`
- `ntoskrnl!DbgPrintEx` at `0x14000ce7c`
- `ntoskrnl!DbgPrintEx` at `0x14000ceb5`
- `ntoskrnl!DbgPrintEx` at `0x14000cf03`
- `ntoskrnl!DbgPrintEx` at `0x14000cfba`
- `ntoskrnl!DbgPrintEx` at `0x14000d02b`
- `ntoskrnl!DbgPrintEx` at `0x14000d093`
- `ntoskrnl!DbgPrintEx` at `0x14000d0ff`
- `ntoskrnl!DbgPrintEx` at `0x14000cdcd`
- `ntoskrnl!DbgPrintEx` at `0x14000ce7c`
- `ntoskrnl!DbgPrintEx` at `0x14000ceb5`
- `ntoskrnl!DbgPrintEx` at `0x14000cf03`
- `ntoskrnl!DbgPrintEx` at `0x14000cfba`
- `ntoskrnl!DbgPrintEx` at `0x14000d02b`
- `ntoskrnl!DbgPrintEx` at `0x14000d093`
- `ntoskrnl!DbgPrintEx` at `0x14000d0ff`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ceda`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ceda`

## string_xrefs

- `0x14000cfad`: `USBD_CreateHandle Successful: usbdHandleInfo 0x%p\n`

## pseudocode

```c
NTSTATUS __stdcall USBD_CreateHandle(
        PDEVICE_OBJECT DeviceObject,
        PDEVICE_OBJECT TargetDeviceObject,
        ULONG USBDClientContractVersion,
        ULONG PoolTag,
        USBD_HANDLE *USBDHandle)
{
  NTSTATUS v7; // ebx
  POOL_TYPE v8; // ecx
  USBD_HANDLE PoolWithTag; // rax
  USBD_HANDLE v10; // rdi
  int InterfaceSynchronously; // eax
  char v12; // r15
  int v13; // eax
  int v15; // eax
  bool v16; // zf
  char v17; // al
  void (__fastcall *v18)(_QWORD); // rax
  _QWORD v19[10]; // [rsp+30h] [rbp-D0h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+80h] [rbp-80h] BYREF

  if ( !KeGetCurrentIrql() )
  {
    if ( byte_140012104
      || (PoolType = NonPagedPool,
          memset(&VersionInformation.dwMajorVersion, 0, 0x118u),
          VersionInformation.dwOSVersionInfoSize = 284,
          RtlGetVersion(&VersionInformation) < 0)
      || VersionInformation.dwMajorVersion <= 6
      && (VersionInformation.dwMajorVersion != 6 || VersionInformation.dwMinorVersion < 2) )
    {
      v8 = PoolType;
    }
    else
    {
      v8 = 512;
      PoolType = 512;
    }
    byte_140012104 = 1;
    if ( !DeviceObject )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "DeviceObject cannot be NULL\n");
LABEL_18:
      v7 = -1073741811;
      goto LABEL_19;
    }
    if ( !TargetDeviceObject )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "TargetDeviceObject cannot be NULL\n");
      goto LABEL_18;
    }
    if ( !USBDHandle )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "USBDHandle cannot be NULL\n");
      return -1073741811;
    }
    PoolWithTag = (USBD_HANDLE)ExAllocatePoolWithTag(v8, 0xE8u, 0x75617370u);
    v10 = PoolWithTag;
    if ( !PoolWithTag )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "Allocation Failed\n");
      v7 = -1073741670;
      goto LABEL_56;
    }
    memset(PoolWithTag, 0, 0xE8u);
    USBDInternal_QueryUsbVerifierSettings((__int64)DeviceObject, (__int64)(v10 + 2));
    *(_DWORD *)v10 = 1145197397;
    *((_WORD *)v10 + 5) = 1539;
    *((_DWORD *)v10 + 54) = 1539;
    *((_WORD *)v10 + 4) = 200;
    *((_DWORD *)v10 + 10) = 1538;
    *((_QWORD *)v10 + 7) = DeviceObject;
    *((_DWORD *)v10 + 16) = 1969320816;
    *((_QWORD *)v10 + 9) = v10;
    *((_QWORD *)v10 + 26) = TargetDeviceObject;
    *((_DWORD *)v10 + 55) = 1;
    InterfaceSynchronously = USBDInternal_BuildAndSendQueryInterfaceSynchronously(
                               DeviceObject,
                               TargetDeviceObject,
                               (ULONG_PTR)&GUID_USBD_INTERFACE,
                               (USHORT *)v10 + 4);
    v7 = InterfaceSynchronously;
    if ( InterfaceSynchronously < 0 )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(
          0x4Du,
          3u,
          "Core stack (TargetDevieObject 0x%p) failed USBD_INTERFACE_VERSION_603, 0x%x\n",
          TargetDeviceObject,
          InterfaceSynchronously);
      *((_WORD *)v10 + 4) = 152;
      *((_WORD *)v10 + 5) = 1538;
      *((_DWORD *)v10 + 54) = 1538;
      v15 = USBDInternal_BuildAndSendQueryInterfaceSynchronously(
              DeviceObject,
              TargetDeviceObject,
              (ULONG_PTR)&GUID_USBD_INTERFACE,
              (USHORT *)v10 + 4);
      v7 = v15;
      if ( v15 < 0 )
      {
        v16 = g_EnableDbgPrints == 0;
        v12 = 0;
        *((_DWORD *)v10 + 54) = 1536;
        if ( !v16 )
          DbgPrintEx(
            0x4Du,
            3u,
            "Core stack (TargetDevieObject 0x%p) failed USBD_INTERFACE_VERSION_602, 0x%x\n",
            TargetDeviceObject,
            v15);
        v7 = 0;
        goto LABEL_32;
      }
    }
    else
    {
      *((_DWORD *)v10 + 54) = *((unsigned __int16 *)v10 + 5);
    }
    v12 = 1;
LABEL_32:
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 3u, "USBD_CreateHandle Successful: usbdHandleInfo 0x%p\n", v10);
    if ( *((_DWORD *)v10 + 54) == 1536 )
    {
      memset(v19, 0, 0x48u);
      LODWORD(v19[0]) = 65608;
      v13 = USBDInternal_BuildAndSendQueryInterfaceSynchronously(
              DeviceObject,
              TargetDeviceObject,
              (ULONG_PTR)&USB_BUS_INTERFACE_USBDI_GUID,
              (USHORT *)v19);
      v7 = v13;
      if ( v13 >= 0 )
      {
        if ( v19[8] )
          v17 = ((__int64 (__fastcall *)(_QWORD))v19[8])(v19[1]);
        else
          v17 = 0;
        *((_BYTE *)v10 + 224) = v17;
        ((void (__fastcall *)(_QWORD))v19[3])(v19[1]);
      }
      else
      {
        if ( g_EnableDbgPrints )
          DbgPrintEx(
            0x4Du,
            0,
            "Core stack (TargetDevieObject 0x%p) failed query to USB_BUS_INTERFACE_USBDI_GUID : USB_BUSIF_USBDI_VERSION_1, 0x%x\n",
            TargetDeviceObject,
            v13);
        *((_DWORD *)v10 + 54) = -1;
        v7 = 0;
      }
    }
    else if ( v7 < 0 )
    {
      if ( v12 )
      {
        v18 = (void (__fastcall *)(_QWORD))*((_QWORD *)v10 + 14);
        if ( v18 )
          v18(*((_QWORD *)v10 + 6));
      }
      ExFreePoolWithTag(v10, 0x75617370u);
      goto LABEL_56;
    }
    *USBDHandle = v10;
    return v7;
  }
  if ( g_EnableDbgPrints )
    DbgPrintEx(0x4Du, 0, "Irql Too High\n");
  v7 = -1073741496;
LABEL_19:
  if ( USBDHandle )
LABEL_56:
    *USBDHandle = 0;
  return v7;
}

```

## disassembly

```asm
0x14000cd68  mov     [rsp-8+arg_10], rbx
0x14000cd6d  push    rbp
0x14000cd6e  push    rsi
0x14000cd6f  push    rdi
0x14000cd70  push    r12
0x14000cd72  push    r13
0x14000cd74  push    r14
0x14000cd76  push    r15
0x14000cd78  lea     rbp, [rsp-0B0h]
0x14000cd80  sub     rsp, 1B0h
0x14000cd87  mov     rax, cs:__security_cookie
0x14000cd8e  xor     rax, rsp
0x14000cd91  mov     [rbp+0E0h+var_40], rax
0x14000cd98  mov     r14, [rbp+0E0h+USBDHandle]
0x14000cd9f  mov     rsi, rdx
0x14000cda2  mov     r12, rcx
0x14000cda5  call    cs:__imp_KeGetCurrentIrql
0x14000cdac  nop     dword ptr [rax+rax+00h]
0x14000cdb1  xor     r13d, r13d
0x14000cdb4  test    al, al
0x14000cdb6  jz      short loc_14000CDE3
0x14000cdb8  cmp     cs:g_EnableDbgPrints, r13b
0x14000cdbf  jz      short loc_14000CDD9
0x14000cdc1  xor     edx, edx; Level
0x14000cdc3  lea     r8, aIrqlTooHigh; "Irql Too High\n"
0x14000cdca  lea     ecx, [rdx+4Dh]; ComponentId
0x14000cdcd  call    cs:__imp_DbgPrintEx
0x14000cdd4  nop     dword ptr [rax+rax+00h]
0x14000cdd9  mov     ebx, 0C0000148h
0x14000cdde  jmp     loc_14000CE8D
0x14000cde3  cmp     cs:byte_140012104, r13b
0x14000cdea  jnz     short loc_14000CE3A
0x14000cdec  xor     edx, edx; Val
0x14000cdee  mov     cs:PoolType, r13d
0x14000cdf5  mov     r8d, 118h; Size
0x14000cdfb  lea     rcx, [rbp+0E0h+VersionInformation.dwMajorVersion]; void *
0x14000cdff  call    memset
0x14000ce04  lea     rcx, [rbp+0E0h+VersionInformation]; lpVersionInformation
0x14000ce08  mov     [rbp+0E0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x14000ce0f  call    cs:__imp_RtlGetVersion
0x14000ce16  nop     dword ptr [rax+rax+00h]
0x14000ce1b  test    eax, eax
0x14000ce1d  js      short loc_14000CE3A
0x14000ce1f  cmp     [rbp+0E0h+VersionInformation.dwMajorVersion], 6
0x14000ce23  ja      short loc_14000CE2D
0x14000ce25  jnz     short loc_14000CE3A
0x14000ce27  cmp     [rbp+0E0h+VersionInformation.dwMinorVersion], 2
0x14000ce2b  jb      short loc_14000CE3A
0x14000ce2d  mov     ecx, 200h
0x14000ce32  mov     cs:PoolType, ecx
0x14000ce38  jmp     short loc_14000CE40
0x14000ce3a  mov     ecx, cs:PoolType; PoolType
0x14000ce40  mov     ebx, 1
0x14000ce45  mov     cs:byte_140012104, bl
0x14000ce4b  test    r12, r12
0x14000ce4e  jnz     short loc_14000CE62
0x14000ce50  cmp     cs:g_EnableDbgPrints, r13b
0x14000ce57  jz      short loc_14000CE88
0x14000ce59  lea     r8, aDeviceobjectCa; "DeviceObject cannot be NULL\n"
0x14000ce60  jmp     short loc_14000CE77
0x14000ce62  test    rsi, rsi
0x14000ce65  jnz     short loc_14000CE9B
0x14000ce67  cmp     cs:g_EnableDbgPrints, r13b
0x14000ce6e  jz      short loc_14000CE88
0x14000ce70  lea     r8, aTargetdeviceob; "TargetDeviceObject cannot be NULL\n"
0x14000ce77  xor     edx, edx; Level
0x14000ce79  lea     ecx, [rdx+4Dh]; ComponentId
0x14000ce7c  call    cs:__imp_DbgPrintEx
0x14000ce83  nop     dword ptr [rax+rax+00h]
0x14000ce88  mov     ebx, 0C000000Dh
0x14000ce8d  test    r14, r14
0x14000ce90  jz      loc_14000D047
0x14000ce96  jmp     loc_14000D179
0x14000ce9b  test    r14, r14
0x14000ce9e  jnz     short loc_14000CECB
0x14000cea0  cmp     cs:g_EnableDbgPrints, r13b
0x14000cea7  jz      short loc_14000CEC1
0x14000cea9  xor     edx, edx; Level
0x14000ceab  lea     r8, aUsbdhandleCann; "USBDHandle cannot be NULL\n"
0x14000ceb2  lea     ecx, [rdx+4Dh]; ComponentId
0x14000ceb5  call    cs:__imp_DbgPrintEx
0x14000cebc  nop     dword ptr [rax+rax+00h]
0x14000cec1  mov     ebx, 0C000000Dh
0x14000cec6  jmp     loc_14000D047
0x14000cecb  mov     r15d, 0E8h
0x14000ced1  mov     r8d, 75617370h; Tag
0x14000ced7  mov     edx, r15d; NumberOfBytes
0x14000ceda  call    cs:__imp_ExAllocatePoolWithTag
0x14000cee1  nop     dword ptr [rax+rax+00h]
0x14000cee6  mov     rdi, rax
0x14000cee9  test    rax, rax
0x14000ceec  jnz     short loc_14000CF19
0x14000ceee  cmp     cs:g_EnableDbgPrints, r13b
0x14000cef5  jz      short loc_14000CF0F
0x14000cef7  lea     r8, aAllocationFail; "Allocation Failed\n"
0x14000cefe  xor     edx, edx; Level
0x14000cf00  lea     ecx, [rax+4Dh]; ComponentId
0x14000cf03  call    cs:__imp_DbgPrintEx
0x14000cf0a  nop     dword ptr [rax+rax+00h]
0x14000cf0f  mov     ebx, 0C000009Ah
0x14000cf14  jmp     loc_14000D179
0x14000cf19  mov     r8, r15; Size
0x14000cf1c  xor     edx, edx; Val
0x14000cf1e  mov     rcx, rdi; void *
0x14000cf21  call    memset
0x14000cf26  lea     r15, [rdi+8]
0x14000cf2a  mov     rcx, r12
0x14000cf2d  mov     rdx, r15
0x14000cf30  call    USBDInternal_QueryUsbVerifierSettings
0x14000cf35  mov     eax, 603h
0x14000cf3a  mov     dword ptr [rdi], 44425355h
0x14000cf40  mov     r9, r15
0x14000cf43  mov     [rdi+0Ah], ax
0x14000cf47  lea     r8, GUID_USBD_INTERFACE
0x14000cf4e  mov     [rdi+0D8h], eax
0x14000cf54  mov     rdx, rsi; PDEVICE_OBJECT
0x14000cf57  mov     word ptr [r15], 0C8h
0x14000cf5d  mov     rcx, r12; DeviceObject
0x14000cf60  mov     dword ptr [rdi+28h], 602h
0x14000cf67  mov     [rdi+38h], r12
0x14000cf6b  mov     dword ptr [rdi+40h], 75617370h
0x14000cf72  mov     [rdi+48h], rdi
0x14000cf76  mov     [rdi+0D0h], rsi
0x14000cf7d  mov     [rdi+0DCh], ebx
0x14000cf83  call    USBDInternal_BuildAndSendQueryInterfaceSynchronously
0x14000cf88  mov     ebx, eax
0x14000cf8a  test    eax, eax
0x14000cf8c  js      loc_14000D074
0x14000cf92  movzx   eax, word ptr [rdi+0Ah]
0x14000cf96  mov     [rdi+0D8h], eax
0x14000cf9c  mov     r15b, 1
0x14000cf9f  cmp     cs:g_EnableDbgPrints, r13b
0x14000cfa6  jz      short loc_14000CFC6
0x14000cfa8  mov     edx, 3; Level
0x14000cfad  lea     r8, aUsbdCreatehand; "USBD_CreateHandle Successful: usbdHandl"...
0x14000cfb4  mov     r9, rdi
0x14000cfb7  lea     ecx, [rdx+4Ah]; ComponentId
0x14000cfba  call    cs:__imp_DbgPrintEx
0x14000cfc1  nop     dword ptr [rax+rax+00h]
0x14000cfc6  cmp     dword ptr [rdi+0D8h], 600h
0x14000cfd0  jnz     loc_14000D146
0x14000cfd6  xor     edx, edx; Val
0x14000cfd8  lea     rcx, [rsp+1E0h+var_1B0]; void *
0x14000cfdd  lea     r8d, [rdx+48h]; Size
0x14000cfe1  call    memset
0x14000cfe6  lea     r9, [rsp+1E0h+var_1B0]
0x14000cfeb  mov     [rsp+1E0h+var_1B0], 10048h
0x14000cff3  lea     r8, USB_BUS_INTERFACE_USBDI_GUID
0x14000cffa  mov     rdx, rsi; PDEVICE_OBJECT
0x14000cffd  mov     rcx, r12; DeviceObject
0x14000d000  call    USBDInternal_BuildAndSendQueryInterfaceSynchronously
0x14000d005  mov     ebx, eax
0x14000d007  test    eax, eax
0x14000d009  jns     loc_14000D113
0x14000d00f  cmp     cs:g_EnableDbgPrints, r13b
0x14000d016  jz      short loc_14000D037
0x14000d018  xor     edx, edx; Level
0x14000d01a  mov     [rsp+1E0h+var_1C0], eax
0x14000d01e  mov     r9, rsi
0x14000d021  lea     r8, aCoreStackTarge_0; "Core stack (TargetDevieObject 0x%p) fai"...
0x14000d028  lea     ecx, [rdx+4Dh]; ComponentId
0x14000d02b  call    cs:__imp_DbgPrintEx
0x14000d032  nop     dword ptr [rax+rax+00h]
0x14000d037  mov     dword ptr [rdi+0D8h], 0FFFFFFFFh
0x14000d041  mov     ebx, r13d
0x14000d044  mov     [r14], rdi
0x14000d047  mov     eax, ebx
0x14000d049  mov     rcx, [rbp+0E0h+var_40]
0x14000d050  xor     rcx, rsp; StackCookie
0x14000d053  call    __security_check_cookie
0x14000d058  mov     rbx, [rsp+1E0h+arg_10]
0x14000d060  add     rsp, 1B0h
0x14000d067  pop     r15
0x14000d069  pop     r14
0x14000d06b  pop     r13
0x14000d06d  pop     r12
0x14000d06f  pop     rdi
0x14000d070  pop     rsi
0x14000d071  pop     rbp
0x14000d072  retn
0x14000d074  cmp     cs:g_EnableDbgPrints, r13b
0x14000d07b  jz      short loc_14000D09F
0x14000d07d  mov     edx, 3; Level
0x14000d082  mov     [rsp+1E0h+var_1C0], eax
0x14000d086  mov     r9, rsi
0x14000d089  lea     r8, aCoreStackTarge_1; "Core stack (TargetDevieObject 0x%p) fai"...
0x14000d090  lea     ecx, [rdx+4Ah]; ComponentId
0x14000d093  call    cs:__imp_DbgPrintEx
0x14000d09a  nop     dword ptr [rax+rax+00h]
0x14000d09f  mov     eax, 602h
0x14000d0a4  mov     word ptr [r15], 98h
0x14000d0aa  mov     r9, r15
0x14000d0ad  mov     [rdi+0Ah], ax
0x14000d0b1  lea     r8, GUID_USBD_INTERFACE
0x14000d0b8  mov     [rdi+0D8h], eax
0x14000d0be  mov     rdx, rsi; PDEVICE_OBJECT
0x14000d0c1  mov     rcx, r12; DeviceObject
0x14000d0c4  call    USBDInternal_BuildAndSendQueryInterfaceSynchronously
0x14000d0c9  mov     ebx, eax
0x14000d0cb  test    eax, eax
0x14000d0cd  jns     loc_14000CF9C
0x14000d0d3  cmp     cs:g_EnableDbgPrints, r13b
0x14000d0da  mov     r15b, r13b
0x14000d0dd  mov     dword ptr [rdi+0D8h], 600h
0x14000d0e7  jz      short loc_14000D10B
0x14000d0e9  mov     edx, 3; Level
0x14000d0ee  mov     [rsp+1E0h+var_1C0], eax
0x14000d0f2  mov     r9, rsi
0x14000d0f5  lea     r8, aCoreStackTarge; "Core stack (TargetDevieObject 0x%p) fai"...
0x14000d0fc  lea     ecx, [rdx+4Ah]; ComponentId
0x14000d0ff  call    cs:__imp_DbgPrintEx
0x14000d106  nop     dword ptr [rax+rax+00h]
0x14000d10b  mov     ebx, r13d
0x14000d10e  jmp     loc_14000CF9F
0x14000d113  mov     rax, [rsp+1E0h+var_170]
0x14000d118  test    rax, rax
0x14000d11b  jz      short loc_14000D129
0x14000d11d  mov     rcx, [rsp+1E0h+var_1A8]
0x14000d122  call    _guard_dispatch_icall
0x14000d127  jmp     short loc_14000D12C
0x14000d129  mov     al, r13b
0x14000d12c  mov     [rdi+0E0h], al
0x14000d132  mov     rcx, [rsp+1E0h+var_1A8]
0x14000d137  mov     rax, [rsp+1E0h+var_198]
0x14000d13c  call    _guard_dispatch_icall
0x14000d141  jmp     loc_14000D044
0x14000d146  test    ebx, ebx
0x14000d148  jns     loc_14000D044
0x14000d14e  test    r15b, r15b
0x14000d151  jz      short loc_14000D165
0x14000d153  mov     rax, [rdi+70h]
0x14000d157  test    rax, rax
0x14000d15a  jz      short loc_14000D165
0x14000d15c  mov     rcx, [rdi+30h]
0x14000d160  call    _guard_dispatch_icall
0x14000d165  mov     edx, 75617370h; Tag
0x14000d16a  mov     rcx, rdi; P
0x14000d16d  call    cs:__imp_ExFreePoolWithTag
0x14000d174  nop     dword ptr [rax+rax+00h]
0x14000d179  mov     [r14], r13
0x14000d17c  jmp     loc_14000D047
```
