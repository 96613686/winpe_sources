# VfsDeleteControlDevice

- ea: `0x140008584`
- end: `0x1400085e7`
- name: `VfsDeleteControlDevice`
- size: `99`
- prototype: `void()`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x140024008`

## callees

- `0x140008584`

## import_xrefs

- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400085b7`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400085b7`
- `ntoskrnl!IoDeleteDevice` at `0x1400085ca`
- `ntoskrnl!IoDeleteDevice` at `0x1400085ca`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400085a6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400085a6`

## pseudocode

```c
void VfsDeleteControlDevice()
{
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  if ( DeviceObject )
  {
    RtlInitUnicodeString(&DestinationString, L"\\DosDevices\\AppvVfs");
    IoDeleteSymbolicLink(&DestinationString);
    IoDeleteDevice(DeviceObject);
    DeviceObject = 0;
  }
}

```

## disassembly

```asm
0x140008584  sub     rsp, 38h
0x140008588  cmp     cs:DeviceObject, 0
0x140008590  xorps   xmm0, xmm0
0x140008593  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140008598  jz      short loc_1400085E1
0x14000859a  lea     rdx, aDosdevicesAppv; "\\DosDevices\\AppvVfs"
0x1400085a1  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400085a6  call    cs:__imp_RtlInitUnicodeString
0x1400085ad  nop     dword ptr [rax+rax+00h]
0x1400085b2  lea     rcx, [rsp+38h+DestinationString]; SymbolicLinkName
0x1400085b7  call    cs:__imp_IoDeleteSymbolicLink
0x1400085be  nop     dword ptr [rax+rax+00h]
0x1400085c3  mov     rcx, cs:DeviceObject; DeviceObject
0x1400085ca  call    cs:__imp_IoDeleteDevice
0x1400085d1  nop     dword ptr [rax+rax+00h]
0x1400085d6  mov     cs:DeviceObject, 0
0x1400085e1  add     rsp, 38h
0x1400085e5  retn
```
