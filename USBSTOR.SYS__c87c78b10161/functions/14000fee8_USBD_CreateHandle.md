# USBD_CreateHandle

- ea: `0x14000fee8`
- end: `0x140010301`
- name: `USBD_CreateHandle`
- size: `1049`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PDEVICE_OBJECT TargetDeviceObject, ULONG USBDClientContractVersion, ULONG PoolTag, USBD_HANDLE *USBDHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140008590`

## callees

- `0x14000c570`
- `0x14000fee8`
- `0x140013230`
- `0x140013950`
- `0x140013990`
- `0x140013d40`

## import_xrefs

- `ntoskrnl!RtlGetVersion` at `0x14000ff8f`
- `ntoskrnl!RtlGetVersion` at `0x14000ff8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400102ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400102ed`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000ff25`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000ff25`
- `ntoskrnl!DbgPrintEx` at `0x14000ff4d`
- `ntoskrnl!DbgPrintEx` at `0x14000fffc`
- `ntoskrnl!DbgPrintEx` at `0x140010035`
- `ntoskrnl!DbgPrintEx` at `0x140010083`
- `ntoskrnl!DbgPrintEx` at `0x14001013a`
- `ntoskrnl!DbgPrintEx` at `0x1400101ab`
- `ntoskrnl!DbgPrintEx` at `0x140010213`
- `ntoskrnl!DbgPrintEx` at `0x14001027f`
- `ntoskrnl!DbgPrintEx` at `0x14000ff4d`
- `ntoskrnl!DbgPrintEx` at `0x14000fffc`
- `ntoskrnl!DbgPrintEx` at `0x140010035`
- `ntoskrnl!DbgPrintEx` at `0x140010083`
- `ntoskrnl!DbgPrintEx` at `0x14001013a`
- `ntoskrnl!DbgPrintEx` at `0x1400101ab`
- `ntoskrnl!DbgPrintEx` at `0x140010213`
- `ntoskrnl!DbgPrintEx` at `0x14001027f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001005a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001005a`

## string_xrefs

- `0x14001012d`: `USBD_CreateHandle Successful: usbdHandleInfo 0x%p\n`

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

  if ( KeGetCurrentIrql() )
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "Irql Too High\n");
    v7 = -1073741496;
LABEL_19:
    if ( !USBDHandle )
      return v7;
    goto LABEL_56;
  }
  if ( byte_14001A1DC
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
  byte_14001A1DC = 1;
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
  if ( USBDHandle )
  {
    PoolWithTag = (USBD_HANDLE)ExAllocatePoolWithTag(v8, 0xE8u, 0x53414D55u);
    v10 = PoolWithTag;
    if ( !PoolWithTag )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "Allocation Failed\n");
      v7 = -1073741670;
LABEL_56:
      *USBDHandle = 0;
      return v7;
    }
    memset(PoolWithTag, 0, 0xE8u);
    USBDInternal_QueryUsbVerifierSettings((__int64)DeviceObject, (__int64)(v10 + 2));
    *(_DWORD *)v10 = 1145197397;
    *((_WORD *)v10 + 5) = 1539;
    *((_DWORD *)v10 + 54) = 1539;
    *((_WORD *)v10 + 4) = 200;
    *((_DWORD *)v10 + 10) = 1538;
    *((_QWORD *)v10 + 7) = DeviceObject;
    *((_DWORD *)v10 + 16) = 1396788565;
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
          ExFreePoolWithTag(v10, 0x53414D55u);
          goto LABEL_56;
        }
        *USBDHandle = v10;
        return v7;
      }
    }
    else
    {
      *((_DWORD *)v10 + 54) = *((unsigned __int16 *)v10 + 5);
    }
    v12 = 1;
    goto LABEL_32;
  }
  if ( g_EnableDbgPrints )
    DbgPrintEx(0x4Du, 0, "USBDHandle cannot be NULL\n");
  return -1073741811;
}

```

## disassembly

```asm
0x14000fee8  mov     [rsp-8+arg_10], rbx
0x14000feed  push    rbp
0x14000feee  push    rsi
0x14000feef  push    rdi
0x14000fef0  push    r12
0x14000fef2  push    r13
0x14000fef4  push    r14
0x14000fef6  push    r15
0x14000fef8  lea     rbp, [rsp-0B0h]
0x14000ff00  sub     rsp, 1B0h
0x14000ff07  mov     rax, cs:__security_cookie
0x14000ff0e  xor     rax, rsp
0x14000ff11  mov     [rbp+0E0h+var_40], rax
0x14000ff18  mov     r14, [rbp+0E0h+USBDHandle]
0x14000ff1f  mov     rsi, rdx
0x14000ff22  mov     r12, rcx
0x14000ff25  call    cs:__imp_KeGetCurrentIrql
0x14000ff2c  nop     dword ptr [rax+rax+00h]
0x14000ff31  xor     r13d, r13d
0x14000ff34  test    al, al
0x14000ff36  jz      short loc_14000FF63
0x14000ff38  cmp     cs:g_EnableDbgPrints, r13b
0x14000ff3f  jz      short loc_14000FF59
0x14000ff41  xor     edx, edx; Level
0x14000ff43  lea     r8, aIrqlTooHigh; "Irql Too High\n"
0x14000ff4a  lea     ecx, [rdx+4Dh]; ComponentId
0x14000ff4d  call    cs:__imp_DbgPrintEx
0x14000ff54  nop     dword ptr [rax+rax+00h]
0x14000ff59  mov     ebx, 0C0000148h
0x14000ff5e  jmp     loc_14001000D
0x14000ff63  cmp     cs:byte_14001A1DC, r13b
0x14000ff6a  jnz     short loc_14000FFBA
0x14000ff6c  xor     edx, edx; Val
0x14000ff6e  mov     cs:PoolType, r13d
0x14000ff75  mov     r8d, 118h; Size
0x14000ff7b  lea     rcx, [rbp+0E0h+VersionInformation.dwMajorVersion]; void *
0x14000ff7f  call    memset
0x14000ff84  lea     rcx, [rbp+0E0h+VersionInformation]; lpVersionInformation
0x14000ff88  mov     [rbp+0E0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x14000ff8f  call    cs:__imp_RtlGetVersion
0x14000ff96  nop     dword ptr [rax+rax+00h]
0x14000ff9b  test    eax, eax
0x14000ff9d  js      short loc_14000FFBA
0x14000ff9f  cmp     [rbp+0E0h+VersionInformation.dwMajorVersion], 6
0x14000ffa3  ja      short loc_14000FFAD
0x14000ffa5  jnz     short loc_14000FFBA
0x14000ffa7  cmp     [rbp+0E0h+VersionInformation.dwMinorVersion], 2
0x14000ffab  jb      short loc_14000FFBA
0x14000ffad  mov     ecx, 200h
0x14000ffb2  mov     cs:PoolType, ecx
0x14000ffb8  jmp     short loc_14000FFC0
0x14000ffba  mov     ecx, cs:PoolType; PoolType
0x14000ffc0  mov     ebx, 1
0x14000ffc5  mov     cs:byte_14001A1DC, bl
0x14000ffcb  test    r12, r12
0x14000ffce  jnz     short loc_14000FFE2
0x14000ffd0  cmp     cs:g_EnableDbgPrints, r13b
0x14000ffd7  jz      short loc_140010008
0x14000ffd9  lea     r8, aDeviceobjectCa; "DeviceObject cannot be NULL\n"
0x14000ffe0  jmp     short loc_14000FFF7
0x14000ffe2  test    rsi, rsi
0x14000ffe5  jnz     short loc_14001001B
0x14000ffe7  cmp     cs:g_EnableDbgPrints, r13b
0x14000ffee  jz      short loc_140010008
0x14000fff0  lea     r8, aTargetdeviceob; "TargetDeviceObject cannot be NULL\n"
0x14000fff7  xor     edx, edx; Level
0x14000fff9  lea     ecx, [rdx+4Dh]; ComponentId
0x14000fffc  call    cs:__imp_DbgPrintEx
0x140010003  nop     dword ptr [rax+rax+00h]
0x140010008  mov     ebx, 0C000000Dh
0x14001000d  test    r14, r14
0x140010010  jnz     loc_1400102F9
0x140010016  jmp     loc_1400101C7
0x14001001b  test    r14, r14
0x14001001e  jnz     short loc_14001004B
0x140010020  cmp     cs:g_EnableDbgPrints, r13b
0x140010027  jz      short loc_140010041
0x140010029  xor     edx, edx; Level
0x14001002b  lea     r8, aUsbdhandleCann; "USBDHandle cannot be NULL\n"
0x140010032  lea     ecx, [rdx+4Dh]; ComponentId
0x140010035  call    cs:__imp_DbgPrintEx
0x14001003c  nop     dword ptr [rax+rax+00h]
0x140010041  mov     ebx, 0C000000Dh
0x140010046  jmp     loc_1400101C7
0x14001004b  mov     r15d, 0E8h
0x140010051  mov     r8d, 53414D55h; Tag
0x140010057  mov     edx, r15d; NumberOfBytes
0x14001005a  call    cs:__imp_ExAllocatePoolWithTag
0x140010061  nop     dword ptr [rax+rax+00h]
0x140010066  mov     rdi, rax
0x140010069  test    rax, rax
0x14001006c  jnz     short loc_140010099
0x14001006e  cmp     cs:g_EnableDbgPrints, r13b
0x140010075  jz      short loc_14001008F
0x140010077  lea     r8, aAllocationFail; "Allocation Failed\n"
0x14001007e  xor     edx, edx; Level
0x140010080  lea     ecx, [rax+4Dh]; ComponentId
0x140010083  call    cs:__imp_DbgPrintEx
0x14001008a  nop     dword ptr [rax+rax+00h]
0x14001008f  mov     ebx, 0C000009Ah
0x140010094  jmp     loc_1400102F9
0x140010099  mov     r8, r15; Size
0x14001009c  xor     edx, edx; Val
0x14001009e  mov     rcx, rdi; void *
0x1400100a1  call    memset
0x1400100a6  lea     r15, [rdi+8]
0x1400100aa  mov     rcx, r12
0x1400100ad  mov     rdx, r15
0x1400100b0  call    USBDInternal_QueryUsbVerifierSettings
0x1400100b5  mov     eax, 603h
0x1400100ba  mov     dword ptr [rdi], 44425355h
0x1400100c0  mov     r9, r15
0x1400100c3  mov     [rdi+0Ah], ax
0x1400100c7  lea     r8, GUID_USBD_INTERFACE
0x1400100ce  mov     [rdi+0D8h], eax
0x1400100d4  mov     rdx, rsi; PDEVICE_OBJECT
0x1400100d7  mov     word ptr [r15], 0C8h
0x1400100dd  mov     rcx, r12; DeviceObject
0x1400100e0  mov     dword ptr [rdi+28h], 602h
0x1400100e7  mov     [rdi+38h], r12
0x1400100eb  mov     dword ptr [rdi+40h], 53414D55h
0x1400100f2  mov     [rdi+48h], rdi
0x1400100f6  mov     [rdi+0D0h], rsi
0x1400100fd  mov     [rdi+0DCh], ebx
0x140010103  call    USBDInternal_BuildAndSendQueryInterfaceSynchronously
0x140010108  mov     ebx, eax
0x14001010a  test    eax, eax
0x14001010c  js      loc_1400101F4
0x140010112  movzx   eax, word ptr [rdi+0Ah]
0x140010116  mov     [rdi+0D8h], eax
0x14001011c  mov     r15b, 1
0x14001011f  cmp     cs:g_EnableDbgPrints, r13b
0x140010126  jz      short loc_140010146
0x140010128  mov     edx, 3; Level
0x14001012d  lea     r8, aUsbdCreatehand; "USBD_CreateHandle Successful: usbdHandl"...
0x140010134  mov     r9, rdi
0x140010137  lea     ecx, [rdx+4Ah]; ComponentId
0x14001013a  call    cs:__imp_DbgPrintEx
0x140010141  nop     dword ptr [rax+rax+00h]
0x140010146  cmp     dword ptr [rdi+0D8h], 600h
0x140010150  jnz     loc_1400102C6
0x140010156  xor     edx, edx; Val
0x140010158  lea     rcx, [rsp+1E0h+var_1B0]; void *
0x14001015d  lea     r8d, [rdx+48h]; Size
0x140010161  call    memset
0x140010166  lea     r9, [rsp+1E0h+var_1B0]
0x14001016b  mov     [rsp+1E0h+var_1B0], 10048h
0x140010173  lea     r8, USB_BUS_INTERFACE_USBDI_GUID
0x14001017a  mov     rdx, rsi; PDEVICE_OBJECT
0x14001017d  mov     rcx, r12; DeviceObject
0x140010180  call    USBDInternal_BuildAndSendQueryInterfaceSynchronously
0x140010185  mov     ebx, eax
0x140010187  test    eax, eax
0x140010189  jns     loc_140010293
0x14001018f  cmp     cs:g_EnableDbgPrints, r13b
0x140010196  jz      short loc_1400101B7
0x140010198  xor     edx, edx; Level
0x14001019a  mov     [rsp+1E0h+var_1C0], eax
0x14001019e  mov     r9, rsi
0x1400101a1  lea     r8, aCoreStackTarge_0; "Core stack (TargetDevieObject 0x%p) fai"...
0x1400101a8  lea     ecx, [rdx+4Dh]; ComponentId
0x1400101ab  call    cs:__imp_DbgPrintEx
0x1400101b2  nop     dword ptr [rax+rax+00h]
0x1400101b7  mov     dword ptr [rdi+0D8h], 0FFFFFFFFh
0x1400101c1  mov     ebx, r13d
0x1400101c4  mov     [r14], rdi
0x1400101c7  mov     eax, ebx
0x1400101c9  mov     rcx, [rbp+0E0h+var_40]
0x1400101d0  xor     rcx, rsp; StackCookie
0x1400101d3  call    __security_check_cookie
0x1400101d8  mov     rbx, [rsp+1E0h+arg_10]
0x1400101e0  add     rsp, 1B0h
0x1400101e7  pop     r15
0x1400101e9  pop     r14
0x1400101eb  pop     r13
0x1400101ed  pop     r12
0x1400101ef  pop     rdi
0x1400101f0  pop     rsi
0x1400101f1  pop     rbp
0x1400101f2  retn
0x1400101f4  cmp     cs:g_EnableDbgPrints, r13b
0x1400101fb  jz      short loc_14001021F
0x1400101fd  mov     edx, 3; Level
0x140010202  mov     [rsp+1E0h+var_1C0], eax
0x140010206  mov     r9, rsi
0x140010209  lea     r8, aCoreStackTarge_1; "Core stack (TargetDevieObject 0x%p) fai"...
0x140010210  lea     ecx, [rdx+4Ah]; ComponentId
0x140010213  call    cs:__imp_DbgPrintEx
0x14001021a  nop     dword ptr [rax+rax+00h]
0x14001021f  mov     eax, 602h
0x140010224  mov     word ptr [r15], 98h
0x14001022a  mov     r9, r15
0x14001022d  mov     [rdi+0Ah], ax
0x140010231  lea     r8, GUID_USBD_INTERFACE
0x140010238  mov     [rdi+0D8h], eax
0x14001023e  mov     rdx, rsi; PDEVICE_OBJECT
0x140010241  mov     rcx, r12; DeviceObject
0x140010244  call    USBDInternal_BuildAndSendQueryInterfaceSynchronously
0x140010249  mov     ebx, eax
0x14001024b  test    eax, eax
0x14001024d  jns     loc_14001011C
0x140010253  cmp     cs:g_EnableDbgPrints, r13b
0x14001025a  mov     r15b, r13b
0x14001025d  mov     dword ptr [rdi+0D8h], 600h
0x140010267  jz      short loc_14001028B
0x140010269  mov     edx, 3; Level
0x14001026e  mov     [rsp+1E0h+var_1C0], eax
0x140010272  mov     r9, rsi
0x140010275  lea     r8, aCoreStackTarge; "Core stack (TargetDevieObject 0x%p) fai"...
0x14001027c  lea     ecx, [rdx+4Ah]; ComponentId
0x14001027f  call    cs:__imp_DbgPrintEx
0x140010286  nop     dword ptr [rax+rax+00h]
0x14001028b  mov     ebx, r13d
0x14001028e  jmp     loc_14001011F
0x140010293  mov     rax, [rsp+1E0h+var_170]
0x140010298  test    rax, rax
0x14001029b  jz      short loc_1400102A9
0x14001029d  mov     rcx, [rsp+1E0h+var_1A8]
0x1400102a2  call    _guard_dispatch_icall
0x1400102a7  jmp     short loc_1400102AC
0x1400102a9  mov     al, r13b
0x1400102ac  mov     [rdi+0E0h], al
0x1400102b2  mov     rcx, [rsp+1E0h+var_1A8]
0x1400102b7  mov     rax, [rsp+1E0h+var_198]
0x1400102bc  call    _guard_dispatch_icall
0x1400102c1  jmp     loc_1400101C4
0x1400102c6  test    ebx, ebx
0x1400102c8  jns     loc_1400101C4
0x1400102ce  test    r15b, r15b
0x1400102d1  jz      short loc_1400102E5
0x1400102d3  mov     rax, [rdi+70h]
0x1400102d7  test    rax, rax
0x1400102da  jz      short loc_1400102E5
0x1400102dc  mov     rcx, [rdi+30h]
0x1400102e0  call    _guard_dispatch_icall
0x1400102e5  mov     edx, 53414D55h; Tag
0x1400102ea  mov     rcx, rdi; P
0x1400102ed  call    cs:__imp_ExFreePoolWithTag
0x1400102f4  nop     dword ptr [rax+rax+00h]
0x1400102f9  mov     [r14], r13
0x1400102fc  jmp     loc_1400101C7
```
