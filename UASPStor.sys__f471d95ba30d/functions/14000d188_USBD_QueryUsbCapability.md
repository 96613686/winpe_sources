# USBD_QueryUsbCapability

- ea: `0x14000d188`
- end: `0x14000d369`
- name: `USBD_QueryUsbCapability`
- size: `481`
- prototype: `NTSTATUS __stdcall(USBD_HANDLE USBDHandle, const GUID *CapabilityType, ULONG OutputBufferLength, PUCHAR OutputBuffer, PULONG ResultLength)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400015cc`

## callees

- `0x14000c8a4`
- `0x14000d188`
- `0x14000d7f0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000d27a`
- `ntoskrnl!RtlCompareMemory` at `0x14000d2cb`
- `ntoskrnl!RtlCompareMemory` at `0x14000d27a`
- `ntoskrnl!RtlCompareMemory` at `0x14000d2cb`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d1bb`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d1bb`
- `ntoskrnl!DbgPrintEx` at `0x14000d1e0`
- `ntoskrnl!DbgPrintEx` at `0x14000d243`
- `ntoskrnl!DbgPrintEx` at `0x14000d2a9`
- `ntoskrnl!DbgPrintEx` at `0x14000d1e0`
- `ntoskrnl!DbgPrintEx` at `0x14000d243`
- `ntoskrnl!DbgPrintEx` at `0x14000d2a9`

## string_xrefs

- `0x14000d29d`: `OutputBuffer must be NULL for GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE\n`

## pseudocode

```c
NTSTATUS __stdcall USBD_QueryUsbCapability(
        USBD_HANDLE USBDHandle,
        const GUID *CapabilityType,
        ULONG OutputBufferLength,
        PUCHAR OutputBuffer,
        PULONG ResultLength)
{
  NTSTATUS v7; // ebx
  int v8; // eax

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
  if ( !OutputBuffer )
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "OutputBuffer cant be NULL if OutputBufferLength is not zero\n");
    return -1073741811;
  }
  v8 = *((_DWORD *)USBDHandle + 54);
  if ( v8 == -1 )
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(
        0x4Du,
        0,
        "Could not exchange an interface with the Underlying USB core stack, querrying for capability is not possible\n");
    return -1073741822;
  }
  if ( v8 != 1536 )
    return USBDInternal_BuildandSendIoctlSynchronously(
             *((PDEVICE_OBJECT *)USBDHandle + 7),
             *((PDEVICE_OBJECT *)USBDHandle + 26));
  if ( RtlCompareMemory(
         &GUID_USB_CAPABILITY_STATIC_STREAMS,
         &GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE,
         0x10u) == 16 )
  {
    v7 = -1073741811;
    if ( g_EnableDbgPrints )
      DbgPrintEx(
        0x4Du,
        0,
        "OutputBuffer must be NULL for GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE\n");
  }
  else
  {
    if ( RtlCompareMemory(&GUID_USB_CAPABILITY_STATIC_STREAMS, &GUID_USB_CAPABILITY_SELECTIVE_SUSPEND, 0x10u) != 16 )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "QueryUsbCapability not supported/implemented by core stack\n");
      return -1073741822;
    }
    v7 = -1073741811;
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "OutputBuffer must be NULL for GUID_USB_CAPABILITY_SELECTIVE_SUSPEND\n");
  }
  return v7;
}

```

## disassembly

```asm
0x14000d188  mov     [rsp+arg_8], rbx
0x14000d18d  push    rdi
0x14000d18e  sub     rsp, 60h
0x14000d192  mov     rax, cs:__security_cookie
0x14000d199  xor     rax, rsp
0x14000d19c  mov     [rsp+68h+var_10], rax
0x14000d1a1  xorps   xmm0, xmm0
0x14000d1a4  xor     eax, eax
0x14000d1a6  movups  [rsp+68h+var_38], xmm0
0x14000d1ab  mov     [rsp+68h+var_18], rax
0x14000d1b0  mov     rdi, r9
0x14000d1b3  movups  [rsp+68h+var_28], xmm0
0x14000d1b8  mov     rbx, rcx
0x14000d1bb  call    cs:__imp_KeGetCurrentIrql
0x14000d1c2  nop     dword ptr [rax+rax+00h]
0x14000d1c7  test    al, al
0x14000d1c9  jz      short loc_14000D1F6
0x14000d1cb  cmp     cs:g_EnableDbgPrints, 0
0x14000d1d2  jz      short loc_14000D1EC
0x14000d1d4  lea     r8, aPassiveLevelRe; "PASSIVE_LEVEL required\n"
0x14000d1db  xor     edx, edx; Level
0x14000d1dd  lea     ecx, [rdx+4Dh]; ComponentId
0x14000d1e0  call    cs:__imp_DbgPrintEx
0x14000d1e7  nop     dword ptr [rax+rax+00h]
0x14000d1ec  mov     ebx, 0C000000Dh
0x14000d1f1  jmp     loc_14000D34E
0x14000d1f6  test    rbx, rbx
0x14000d1f9  jnz     short loc_14000D20C
0x14000d1fb  cmp     cs:g_EnableDbgPrints, bl
0x14000d201  jz      short loc_14000D1EC
0x14000d203  lea     r8, aUsbdhandleCant; "USBDHandle cant be NULL\n"
0x14000d20a  jmp     short loc_14000D1DB
0x14000d20c  test    rdi, rdi
0x14000d20f  jnz     short loc_14000D223
0x14000d211  cmp     cs:g_EnableDbgPrints, dil
0x14000d218  jz      short loc_14000D1EC
0x14000d21a  lea     r8, aOutputbufferCa; "OutputBuffer cant be NULL if OutputBuff"...
0x14000d221  jmp     short loc_14000D1DB
0x14000d223  mov     eax, [rbx+0D8h]
0x14000d229  cmp     eax, 0FFFFFFFFh
0x14000d22c  jnz     short loc_14000D259
0x14000d22e  cmp     cs:g_EnableDbgPrints, 0
0x14000d235  jz      short loc_14000D24F
0x14000d237  lea     r8, aCouldNotExchan; "Could not exchange an interface with th"...
0x14000d23e  xor     edx, edx; Level
0x14000d240  lea     ecx, [rdx+4Dh]; ComponentId
0x14000d243  call    cs:__imp_DbgPrintEx
0x14000d24a  nop     dword ptr [rax+rax+00h]
0x14000d24f  mov     ebx, 0C0000002h
0x14000d254  jmp     loc_14000D34E
0x14000d259  cmp     eax, 600h
0x14000d25e  jnz     loc_14000D30C
0x14000d264  mov     ebx, 10h
0x14000d269  lea     rdx, GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE; Source2
0x14000d270  mov     r8d, ebx; Length
0x14000d273  lea     rcx, GUID_USB_CAPABILITY_STATIC_STREAMS; Source1
0x14000d27a  call    cs:__imp_RtlCompareMemory
0x14000d281  nop     dword ptr [rax+rax+00h]
0x14000d286  cmp     rax, rbx
0x14000d289  jnz     short loc_14000D2BA
0x14000d28b  cmp     cs:g_EnableDbgPrints, 0
0x14000d292  mov     ebx, 0C000000Dh
0x14000d297  jz      loc_14000D34E
0x14000d29d  lea     r8, aOutputbufferMu_0; "OutputBuffer must be NULL for GUID_USB_"...
0x14000d2a4  xor     edx, edx; Level
0x14000d2a6  lea     ecx, [rdx+4Dh]; ComponentId
0x14000d2a9  call    cs:__imp_DbgPrintEx
0x14000d2b0  nop     dword ptr [rax+rax+00h]
0x14000d2b5  jmp     loc_14000D34E
0x14000d2ba  mov     r8, rbx; Length
0x14000d2bd  lea     rdx, GUID_USB_CAPABILITY_SELECTIVE_SUSPEND; Source2
0x14000d2c4  lea     rcx, GUID_USB_CAPABILITY_STATIC_STREAMS; Source1
0x14000d2cb  call    cs:__imp_RtlCompareMemory
0x14000d2d2  nop     dword ptr [rax+rax+00h]
0x14000d2d7  cmp     rax, rbx
0x14000d2da  jnz     short loc_14000D2F3
0x14000d2dc  cmp     cs:g_EnableDbgPrints, 0
0x14000d2e3  mov     ebx, 0C000000Dh
0x14000d2e8  jz      short loc_14000D34E
0x14000d2ea  lea     r8, aOutputbufferMu; "OutputBuffer must be NULL for GUID_USB_"...
0x14000d2f1  jmp     short loc_14000D2A4
0x14000d2f3  cmp     cs:g_EnableDbgPrints, 0
0x14000d2fa  jz      loc_14000D24F
0x14000d300  lea     r8, aQueryusbcapabi; "QueryUsbCapability not supported/implem"...
0x14000d307  jmp     loc_14000D23E
0x14000d30c  movups  xmm0, xmmword ptr cs:GUID_USB_CAPABILITY_STATIC_STREAMS.Data1
0x14000d313  mov     rax, [rbx+30h]
0x14000d317  lea     r9, [rsp+68h+var_38]
0x14000d31c  mov     rdx, [rbx+0D0h]; PDEVICE_OBJECT
0x14000d323  mov     r8, rdi
0x14000d326  mov     rcx, [rbx+38h]; DeviceObject
0x14000d32a  movdqu  [rsp+68h+var_28], xmm0
0x14000d330  mov     qword ptr [rsp+68h+var_38], 280001h
0x14000d339  mov     [rsp+68h+var_18], 2
0x14000d342  mov     qword ptr [rsp+68h+var_38+8], rax
0x14000d347  call    USBDInternal_BuildandSendIoctlSynchronously
0x14000d34c  mov     ebx, eax
0x14000d34e  mov     eax, ebx
0x14000d350  mov     rcx, [rsp+68h+var_10]
0x14000d355  xor     rcx, rsp; StackCookie
0x14000d358  call    __security_check_cookie
0x14000d35d  mov     rbx, [rsp+68h+arg_8]
0x14000d362  add     rsp, 60h
0x14000d366  pop     rdi
0x14000d367  retn
```
