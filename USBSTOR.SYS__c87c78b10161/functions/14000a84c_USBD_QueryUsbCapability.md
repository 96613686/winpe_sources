# USBD_QueryUsbCapability

- ea: `0x14000a84c`
- end: `0x14000a9f9`
- name: `USBD_QueryUsbCapability`
- size: `429`
- prototype: `NTSTATUS __stdcall(USBD_HANDLE USBDHandle, const GUID *CapabilityType, ULONG OutputBufferLength, PUCHAR OutputBuffer, PULONG ResultLength)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140008590`

## callees

- `0x14000a84c`
- `0x14000aa00`
- `0x140013950`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000a878`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000a878`
- `ntoskrnl!RtlCompareMemory` at `0x14000a91e`
- `ntoskrnl!RtlCompareMemory` at `0x14000a979`
- `ntoskrnl!RtlCompareMemory` at `0x14000a91e`
- `ntoskrnl!RtlCompareMemory` at `0x14000a979`
- `ntoskrnl!DbgPrintEx` at `0x14000a89d`
- `ntoskrnl!DbgPrintEx` at `0x14000a8e9`
- `ntoskrnl!DbgPrintEx` at `0x14000a94f`
- `ntoskrnl!DbgPrintEx` at `0x14000a89d`
- `ntoskrnl!DbgPrintEx` at `0x14000a8e9`
- `ntoskrnl!DbgPrintEx` at `0x14000a94f`

## pseudocode

```c
NTSTATUS __stdcall USBD_QueryUsbCapability(
        USBD_HANDLE USBDHandle,
        const GUID *CapabilityType,
        ULONG OutputBufferLength,
        PUCHAR OutputBuffer,
        PULONG ResultLength)
{
  int v7; // eax

  if ( KeGetCurrentIrql() )
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "PASSIVE_LEVEL required\n");
    return -1073741811;
  }
  if ( !USBDHandle )
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "USBDHandle cant be NULL\n");
    return -1073741811;
  }
  v7 = *((_DWORD *)USBDHandle + 54);
  if ( v7 == -1 )
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(
        0x4Du,
        0,
        "Could not exchange an interface with the Underlying USB core stack, querrying for capability is not possible\n");
    return -1073741822;
  }
  if ( v7 != 1536 )
    return USBDInternal_BuildandSendIoctlSynchronously(
             *((PDEVICE_OBJECT *)USBDHandle + 7),
             *((PDEVICE_OBJECT *)USBDHandle + 26));
  if ( RtlCompareMemory(
         &GUID_USB_CAPABILITY_DEVICE_CONNECTION_SUPER_SPEED_COMPATIBLE,
         &GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE,
         0x10u) != 16 )
  {
    if ( RtlCompareMemory(
           &GUID_USB_CAPABILITY_DEVICE_CONNECTION_SUPER_SPEED_COMPATIBLE,
           &GUID_USB_CAPABILITY_SELECTIVE_SUSPEND,
           0x10u) != 16 )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "QueryUsbCapability not supported/implemented by core stack\n");
      return -1073741822;
    }
    return 0;
  }
  if ( *((_BYTE *)USBDHandle + 224) )
    return 0;
  if ( g_EnableDbgPrints )
    DbgPrintEx(0x4Du, 3u, "Device is not High Speed\n");
  return -1073741637;
}

```

## disassembly

```asm
0x14000a84c  push    rbx
0x14000a84e  sub     rsp, 60h
0x14000a852  mov     rax, cs:__security_cookie
0x14000a859  xor     rax, rsp
0x14000a85c  mov     [rsp+68h+var_10], rax
0x14000a861  xorps   xmm0, xmm0
0x14000a864  xor     eax, eax
0x14000a866  movups  [rsp+68h+var_38], xmm0
0x14000a86b  mov     [rsp+68h+var_18], rax
0x14000a870  mov     rbx, rcx
0x14000a873  movups  [rsp+68h+var_28], xmm0
0x14000a878  call    cs:__imp_KeGetCurrentIrql
0x14000a87f  nop     dword ptr [rax+rax+00h]
0x14000a884  test    al, al
0x14000a886  jz      short loc_14000A8B3
0x14000a888  cmp     cs:g_EnableDbgPrints, 0
0x14000a88f  jz      short loc_14000A8A9
0x14000a891  lea     r8, aPassiveLevelRe; "PASSIVE_LEVEL required\n"
0x14000a898  xor     edx, edx; Level
0x14000a89a  lea     ecx, [rdx+4Dh]; ComponentId
0x14000a89d  call    cs:__imp_DbgPrintEx
0x14000a8a4  nop     dword ptr [rax+rax+00h]
0x14000a8a9  mov     eax, 0C000000Dh
0x14000a8ae  jmp     loc_14000A9E5
0x14000a8b3  test    rbx, rbx
0x14000a8b6  jnz     short loc_14000A8C9
0x14000a8b8  cmp     cs:g_EnableDbgPrints, bl
0x14000a8be  jz      short loc_14000A8A9
0x14000a8c0  lea     r8, aUsbdhandleCant; "USBDHandle cant be NULL\n"
0x14000a8c7  jmp     short loc_14000A898
0x14000a8c9  mov     eax, [rbx+0D8h]
0x14000a8cf  cmp     eax, 0FFFFFFFFh
0x14000a8d2  jnz     short loc_14000A8FF
0x14000a8d4  cmp     cs:g_EnableDbgPrints, 0
0x14000a8db  jz      short loc_14000A8F5
0x14000a8dd  lea     r8, aCouldNotExchan; "Could not exchange an interface with th"...
0x14000a8e4  xor     edx, edx; Level
0x14000a8e6  lea     ecx, [rdx+4Dh]; ComponentId
0x14000a8e9  call    cs:__imp_DbgPrintEx
0x14000a8f0  nop     dword ptr [rax+rax+00h]
0x14000a8f5  mov     eax, 0C0000002h
0x14000a8fa  jmp     loc_14000A9E5
0x14000a8ff  cmp     eax, 600h
0x14000a904  jnz     loc_14000A9A8
0x14000a90a  mov     r8d, 10h; Length
0x14000a910  lea     rdx, GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE; Source2
0x14000a917  lea     rcx, GUID_USB_CAPABILITY_DEVICE_CONNECTION_SUPER_SPEED_COMPATIBLE; Source1
0x14000a91e  call    cs:__imp_RtlCompareMemory
0x14000a925  nop     dword ptr [rax+rax+00h]
0x14000a92a  cmp     rax, 10h
0x14000a92e  jnz     short loc_14000A965
0x14000a930  cmp     byte ptr [rbx+0E0h], 0
0x14000a937  jnz     short loc_14000A98B
0x14000a939  cmp     cs:g_EnableDbgPrints, 0
0x14000a940  jz      short loc_14000A95B
0x14000a942  lea     r8, aDeviceIsNotHig; "Device is not High Speed\n"
0x14000a949  lea     edx, [rax-0Dh]; Level
0x14000a94c  lea     ecx, [rax+3Dh]; ComponentId
0x14000a94f  call    cs:__imp_DbgPrintEx
0x14000a956  nop     dword ptr [rax+rax+00h]
0x14000a95b  mov     eax, 0C00000BBh
0x14000a960  jmp     loc_14000A9E5
0x14000a965  mov     r8d, 10h; Length
0x14000a96b  lea     rdx, GUID_USB_CAPABILITY_SELECTIVE_SUSPEND; Source2
0x14000a972  lea     rcx, GUID_USB_CAPABILITY_DEVICE_CONNECTION_SUPER_SPEED_COMPATIBLE; Source1
0x14000a979  call    cs:__imp_RtlCompareMemory
0x14000a980  nop     dword ptr [rax+rax+00h]
0x14000a985  cmp     rax, 10h
0x14000a989  jnz     short loc_14000A98F
0x14000a98b  xor     eax, eax
0x14000a98d  jmp     short loc_14000A9E5
0x14000a98f  cmp     cs:g_EnableDbgPrints, 0
0x14000a996  jz      loc_14000A8F5
0x14000a99c  lea     r8, aQueryusbcapabi; "QueryUsbCapability not supported/implem"...
0x14000a9a3  jmp     loc_14000A8E4
0x14000a9a8  movups  xmm0, xmmword ptr cs:GUID_USB_CAPABILITY_DEVICE_CONNECTION_SUPER_SPEED_COMPATIBLE.Data1
0x14000a9af  mov     rax, [rbx+30h]
0x14000a9b3  lea     r9, [rsp+68h+var_38]
0x14000a9b8  mov     rdx, [rbx+0D0h]; PDEVICE_OBJECT
0x14000a9bf  mov     rcx, [rbx+38h]; DeviceObject
0x14000a9c3  movdqu  [rsp+68h+var_28], xmm0
0x14000a9c9  mov     qword ptr [rsp+68h+var_38], 280001h
0x14000a9d2  mov     [rsp+68h+var_18], 0
0x14000a9db  mov     qword ptr [rsp+68h+var_38+8], rax
0x14000a9e0  call    USBDInternal_BuildandSendIoctlSynchronously
0x14000a9e5  mov     rcx, [rsp+68h+var_10]
0x14000a9ea  xor     rcx, rsp; StackCookie
0x14000a9ed  call    __security_check_cookie
0x14000a9f2  add     rsp, 60h
0x14000a9f6  pop     rbx
0x14000a9f7  retn
```
