# BthUsb_GetInterfaceDescriptor(_DEVICE_EXTENSION *,void * *,long,long,long,long,long)

- ea: `0x14001ac7c`
- end: `0x14001acc6`
- name: `?BthUsb_GetInterfaceDescriptor@@_Y2PAGE@@APEAU_USB_INTERFACE_DESCRIPTOR@@PEAU_DEVICE_EXTENSION@@PEAPEAXJJJJJ@Z`
- size: `74`
- prototype: `struct _USB_INTERFACE_DESCRIPTOR *__fastcall(struct _DEVICE_EXTENSION *, void **, int, int, int, int, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x140004b3c`
- `0x14001accc`
- `0x14001b840`

## callees

- `0x14001ac7c`

## import_xrefs

- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14001aca7`
- `USBD!USBD_ParseConfigurationDescriptorEx` at `0x14001aca7`

## pseudocode

```c
PUSB_INTERFACE_DESCRIPTOR __fastcall BthUsb_GetInterfaceDescriptor(
        struct _DEVICE_EXTENSION *a1,
        _USB_CONFIGURATION_DESCRIPTOR **a2,
        LONG a3,
        LONG a4)
{
  _USB_CONFIGURATION_DESCRIPTOR *ConfigDescriptor; // rdx
  PUSB_INTERFACE_DESCRIPTOR result; // rax

  ConfigDescriptor = *a2;
  if ( !ConfigDescriptor )
  {
    ConfigDescriptor = a1->ConfigDescriptor;
    *a2 = ConfigDescriptor;
  }
  result = USBD_ParseConfigurationDescriptorEx(a1->ConfigDescriptor, ConfigDescriptor, a3, a4, -1, -1, -1);
  if ( result )
    *a2 = (_USB_CONFIGURATION_DESCRIPTOR *)&result[1];
  return result;
}

```

## disassembly

```asm
0x14001ac7c  push    rbx
0x14001ac7e  sub     rsp, 40h
0x14001ac82  mov     rbx, rdx
0x14001ac85  mov     rdx, [rdx]
0x14001ac88  test    rdx, rdx
0x14001ac8b  jnz     short loc_14001AC94
0x14001ac8d  mov     rdx, [rcx+68h]; StartPosition
0x14001ac91  mov     [rbx], rdx
0x14001ac94  mov     rcx, [rcx+68h]; ConfigurationDescriptor
0x14001ac98  or      eax, 0FFFFFFFFh
0x14001ac9b  mov     [rsp+48h+InterfaceProtocol], eax; InterfaceProtocol
0x14001ac9f  mov     [rsp+48h+InterfaceSubClass], eax; InterfaceSubClass
0x14001aca3  mov     [rsp+48h+InterfaceClass], eax; InterfaceClass
0x14001aca7  call    cs:__imp_USBD_ParseConfigurationDescriptorEx
0x14001acae  nop     dword ptr [rax+rax+00h]
0x14001acb3  test    rax, rax
0x14001acb6  jz      short loc_14001ACBF
0x14001acb8  lea     rcx, [rax+9]
0x14001acbc  mov     [rbx], rcx
0x14001acbf  add     rsp, 40h
0x14001acc3  pop     rbx
0x14001acc4  retn
```
