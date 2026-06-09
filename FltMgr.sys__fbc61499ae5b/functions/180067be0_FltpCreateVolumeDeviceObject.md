# FltpCreateVolumeDeviceObject

- ea: `0x180067be0`
- end: `0x180067da8`
- name: `FltpCreateVolumeDeviceObject`
- size: `456`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800674b0`
- `0x180068900`
- `0x180070c80`

## callees

- `0x180009f20`
- `0x180020180`
- `0x180067be0`
- `0x180067db0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x180067c98`
- `ntoskrnl!KeInitializeEvent` at `0x180067c98`
- `ntoskrnl!IoCreateDevice` at `0x180067c2d`
- `ntoskrnl!IoCreateDevice` at `0x180067c2d`
- `ntoskrnl!IoDeleteDevice` at `0x180067d96`
- `ntoskrnl!IoDeleteDevice` at `0x180067d96`

## string_xrefs

- `0x180067d4f`: `FltpCreateVolumeDeviceObject`
- `0x180067d70`: `FltpCreateVolumeDeviceObject`

## pseudocode

```c
__int64 __fastcall FltpCreateVolumeDeviceObject(
        __int64 a1,
        void *a2,
        const UNICODE_STRING *a3,
        const UNICODE_STRING *a4,
        const UNICODE_STRING *a5,
        __int64 a6,
        PDEVICE_OBJECT *a7)
{
  ULONG v8; // r9d
  unsigned int inited; // ebx
  __int64 v12; // rcx
  __int64 v13; // rdi
  char *DeviceExtension; // rbx
  char *v15; // rsi
  __int64 v16; // rcx
  PDEVICE_OBJECT DeviceObject; // [rsp+70h] [rbp+8h] BYREF

  v8 = *(_DWORD *)(a1 + 72);
  DeviceObject = 0;
  inited = IoCreateDevice((PDRIVER_OBJECT)DriverObject, 0x58u, 0, v8, 0, 0, &DeviceObject);
  if ( (int)FltpDbgStatus(inited, "minkernel\\fs\\filtermgr\\filter\\attachdetachsup.c", 1974, 0) < 0 )
  {
    if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 0x10) != 0 )
      McTemplateU0sd_EtwWriteTransfer(v12, AttachDetachSup_c1976, "FltpCreateVolumeDeviceObject", inited);
  }
  else
  {
    v13 = a6;
    DeviceExtension = (char *)DeviceObject->DeviceExtension;
    *(_DWORD *)DeviceExtension = 5828871;
    *((_QWORD *)DeviceExtension + 2) = v13;
    *((_DWORD *)DeviceExtension + 6) = 1;
    *((_QWORD *)DeviceExtension + 4) = 0;
    *((_DWORD *)DeviceExtension + 10) = 0;
    KeInitializeEvent((PRKEVENT)DeviceExtension + 2, SynchronizationEvent, 0);
    v15 = DeviceExtension + 80;
    inited = FltpInitVolume((__int64)DeviceObject, a2, a3, a4, a5, (__int64 *)DeviceExtension + 10);
    if ( (int)FltpDbgStatus(inited, "minkernel\\fs\\filtermgr\\filter\\attachdetachsup.c", 2010, 0) < 0 )
    {
      if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 0x10) != 0 )
        McTemplateU0sd_EtwWriteTransfer(v16, AttachDetachSup_c2012, "FltpCreateVolumeDeviceObject", inited);
    }
    else
    {
      *(_QWORD *)(*(_QWORD *)v15 + 104LL) = v13;
    }
  }
  if ( (int)FltpDbgStatus(inited, "minkernel\\fs\\filtermgr\\filter\\attachdetachsup.c", 2030, 0) < 0 )
  {
    if ( DeviceObject )
      IoDeleteDevice(DeviceObject);
    *a7 = 0;
  }
  else
  {
    *a7 = DeviceObject;
  }
  return inited;
}

```

## disassembly

```asm
0x180067be0  mov     r11, rsp
0x180067be3  push    rbx
0x180067be4  push    r12
0x180067be6  sub     rsp, 58h
0x180067bea  mov     [r11+10h], rbp
0x180067bee  lea     rax, [r11+8]
0x180067bf2  mov     [r11-18h], rdi
0x180067bf6  xor     r12d, r12d
0x180067bf9  mov     [r11-20h], r14
0x180067bfd  mov     rbp, r9
0x180067c00  mov     r9d, [rcx+48h]; DeviceType
0x180067c04  mov     r14, r8
0x180067c07  mov     rcx, cs:DriverObject; DriverObject
0x180067c0e  xor     r8d, r8d; DeviceName
0x180067c11  mov     [r11-38h], rax
0x180067c15  mov     [r11-28h], r15
0x180067c19  mov     r15, rdx
0x180067c1c  mov     [r11-40h], r12b
0x180067c20  mov     edx, 58h ; 'X'; DeviceExtensionSize
0x180067c25  mov     [r11+8], r12
0x180067c29  mov     [r11-48h], r12d
0x180067c2d  call    cs:__imp_IoCreateDevice
0x180067c34  nop     dword ptr [rax+rax+00h]
0x180067c39  mov     r8d, 7B6h
0x180067c3f  lea     rdx, aMinkernelFsFil_21; "minkernel\\fs\\filtermgr\\filter\\attac"...
0x180067c46  mov     ecx, eax
0x180067c48  xor     r9d, r9d
0x180067c4b  mov     ebx, eax
0x180067c4d  call    FltpDbgStatus
0x180067c52  test    eax, eax
0x180067c54  js      loc_180067D43
0x180067c5a  mov     rax, [rsp+68h+DeviceObject]
0x180067c5f  xor     r8d, r8d; State
0x180067c62  mov     rdi, [rsp+68h+arg_28]
0x180067c6a  mov     edx, 1; Type
0x180067c6f  mov     [rsp+68h+arg_10], rsi
0x180067c77  mov     rbx, [rax+40h]
0x180067c7b  mov     dword ptr [rbx], 58F107h
0x180067c81  lea     rcx, [rbx+30h]; Event
0x180067c85  mov     [rbx+10h], rdi
0x180067c89  mov     dword ptr [rbx+18h], 1
0x180067c90  mov     [rbx+20h], r12
0x180067c94  mov     [rbx+28h], r12d
0x180067c98  call    cs:__imp_KeInitializeEvent
0x180067c9f  nop     dword ptr [rax+rax+00h]
0x180067ca4  mov     rax, [rsp+68h+arg_20]
0x180067cac  lea     rsi, [rbx+50h]
0x180067cb0  mov     rcx, [rsp+68h+DeviceObject]
0x180067cb5  mov     r9, rbp
0x180067cb8  mov     [rsp+68h+var_40], rsi
0x180067cbd  mov     r8, r14
0x180067cc0  mov     rdx, r15
0x180067cc3  mov     [rsp+68h+var_48], rax
0x180067cc8  call    FltpInitVolume
0x180067ccd  mov     r8d, 7DAh
0x180067cd3  lea     rdx, aMinkernelFsFil_21; "minkernel\\fs\\filtermgr\\filter\\attac"...
0x180067cda  xor     r9d, r9d
0x180067cdd  mov     ecx, eax
0x180067cdf  mov     ebx, eax
0x180067ce1  call    FltpDbgStatus
0x180067ce6  test    eax, eax
0x180067ce8  js      short loc_180067D64
0x180067cea  mov     rax, [rsi]
0x180067ced  mov     [rax+68h], rdi
0x180067cf1  mov     rsi, [rsp+68h+arg_10]
0x180067cf9  mov     r8d, 7EEh
0x180067cff  lea     rdx, aMinkernelFsFil_21; "minkernel\\fs\\filtermgr\\filter\\attac"...
0x180067d06  xor     r9d, r9d
0x180067d09  mov     ecx, ebx
0x180067d0b  call    FltpDbgStatus
0x180067d10  mov     r15, [rsp+68h+var_28]
0x180067d15  mov     r14, [rsp+68h+var_20]
0x180067d1a  mov     rdi, [rsp+68h+var_18]
0x180067d1f  mov     rbp, [rsp+68h+arg_8]
0x180067d24  test    eax, eax
0x180067d26  js      short loc_180067D88
0x180067d28  mov     rcx, [rsp+68h+arg_30]
0x180067d30  mov     rax, [rsp+68h+DeviceObject]
0x180067d35  mov     [rcx], rax
0x180067d38  mov     eax, ebx
0x180067d3a  add     rsp, 58h
0x180067d3e  pop     r12
0x180067d40  pop     rbx
0x180067d41  retn
0x180067d43  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 10h
0x180067d4a  jz      short loc_180067CF9
0x180067d4c  mov     r9d, ebx
0x180067d4f  lea     r8, aFltpcreatevolu; "FltpCreateVolumeDeviceObject"
0x180067d56  lea     rdx, AttachDetachSup_c1976
0x180067d5d  call    McTemplateU0sd_EtwWriteTransfer
0x180067d62  jmp     short loc_180067CF9
0x180067d64  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 10h
0x180067d6b  jz      short loc_180067CF1
0x180067d6d  mov     r9d, ebx
0x180067d70  lea     r8, aFltpcreatevolu; "FltpCreateVolumeDeviceObject"
0x180067d77  lea     rdx, AttachDetachSup_c2012
0x180067d7e  call    McTemplateU0sd_EtwWriteTransfer
0x180067d83  jmp     loc_180067CF1
0x180067d88  mov     rcx, [rsp+68h+DeviceObject]; DeviceObject
0x180067d8d  test    rcx, rcx
0x180067d90  jz      loc_18007A5F8
0x180067d96  call    cs:__imp_IoDeleteDevice
0x180067d9d  nop     dword ptr [rax+rax+00h]
0x180067da2  nop
0x180067da3  jmp     loc_18007A5F8
0x18007a5f8  mov     rax, [rsp+68h+arg_30]
0x18007a600  mov     [rax], r12
0x18007a603  jmp     loc_180067D38
```
