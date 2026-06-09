# IoDevObjCreateDeviceSecure

- ea: `0x18002b190`
- end: `0x18002b31b`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, __int64, struct _UNICODE_STRING *, ULONG, ULONG, BOOLEAN, __int64, __int64, PDEVICE_OBJECT DeviceObject)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18002b190`
- `0x18002b324`
- `0x18002b41c`
- `0x18002c124`
- `0x18002c290`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18002b2fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x18002b2fc`
- `ntoskrnl!IoDeleteDevice` at `0x18002b2d8`
- `ntoskrnl!IoDeleteDevice` at `0x18002b2d8`
- `ntoskrnl!IoCreateDevice` at `0x18002b2a9`
- `ntoskrnl!IoCreateDevice` at `0x18002b2a9`

## pseudocode

```c
__int64 __fastcall IoDevObjCreateDeviceSecure(
        PDRIVER_OBJECT DriverObject,
        __int64 a2,
        struct _UNICODE_STRING *a3,
        ULONG a4,
        ULONG a5,
        BOOLEAN a6,
        __int64 a7,
        __int64 a8,
        PDEVICE_OBJECT DeviceObject)
{
  PDEVICE_OBJECT v9; // r14
  ULONG DeviceCharacteristics; // r15d
  __int64 result; // rax
  char v14; // di
  NTSTATUS updated; // ebx
  ULONG v16; // r9d
  BOOLEAN Exclusive; // cl
  ULONG DeviceType[4]; // [rsp+40h] [rbp-30h] BYREF
  ULONG v19[2]; // [rsp+50h] [rbp-20h]
  _QWORD v20[3]; // [rsp+58h] [rbp-18h] BYREF
  ULONG DeviceExtensionSize; // [rsp+B8h] [rbp+48h]
  __int64 v22; // [rsp+C0h] [rbp+50h] BYREF
  ULONG v23; // [rsp+C8h] [rbp+58h]

  v23 = a4;
  DeviceExtensionSize = a2;
  v9 = DeviceObject;
  DeviceCharacteristics = a5;
  v22 = 0;
  *(_QWORD *)v19 = 0;
  *(_QWORD *)&DeviceObject->Type = 0;
  DeviceObject = 0;
  *(_OWORD *)DeviceType = 0;
  if ( !a3 && (DeviceCharacteristics & 0x80u) == 0 )
    return 3221225485LL;
  if ( !a8 || (result = PpRegStateReadCreateClassCreationSettings(a8, DriverObject, DeviceType), (int)result >= 0) )
  {
    v14 = DeviceType[0];
    if ( (DeviceType[0] & 2) != 0 )
      goto LABEL_10;
    updated = SeSddlSecurityDescriptorFromSDDL(a7, a2, &v22);
    if ( updated >= 0 )
    {
      v14 = 2;
      DeviceType[0] = 2;
      *(_QWORD *)&DeviceType[2] = v22;
      if ( !a8
        || (v20[0] = 2, v20[2] = 0, v20[1] = v22, updated = PpRegStateUpdateStackCreationSettings(a8, v20), updated >= 0) )
      {
LABEL_10:
        v16 = v23;
        Exclusive = a6;
        if ( (v14 & 1) != 0 )
          v16 = DeviceType[1];
        if ( (v14 & 4) != 0 )
          DeviceCharacteristics = v19[0];
        if ( (v14 & 8) != 0 )
          Exclusive = v19[1];
        updated = IoCreateDevice(
                    DriverObject,
                    DeviceExtensionSize,
                    a3,
                    v16,
                    DeviceCharacteristics,
                    Exclusive,
                    &DeviceObject);
        if ( updated >= 0 )
        {
          updated = IopDevObjApplyPostCreationSettings(DeviceObject);
          if ( updated >= 0 )
            *(_QWORD *)&v9->Type = DeviceObject;
          else
            IoDeleteDevice(DeviceObject);
        }
      }
    }
    if ( (v14 & 2) != 0 )
      ExFreePoolWithTag(*(PVOID *)&DeviceType[2], 0);
    return (unsigned int)updated;
  }
  return result;
}

```

## disassembly

```asm
0x18002b190  mov     [rsp-38h+arg_18], r9d
0x18002b195  mov     [rsp-38h+DeviceExtensionSize], edx
0x18002b199  push    rbp
0x18002b19a  push    rbx
0x18002b19b  push    rdi
0x18002b19c  push    r12
0x18002b19e  push    r13
0x18002b1a0  push    r14
0x18002b1a2  push    r15
0x18002b1a4  mov     rbp, rsp
0x18002b1a7  sub     rsp, 70h
0x18002b1ab  mov     r14, [rbp+arg_40]
0x18002b1b2  xor     ebx, ebx
0x18002b1b4  mov     r15d, [rbp+arg_20]
0x18002b1b8  xor     eax, eax
0x18002b1ba  mov     [rbp+arg_10], rbx
0x18002b1be  xorps   xmm0, xmm0
0x18002b1c1  mov     qword ptr [rbp+var_20], rax
0x18002b1c5  mov     r13, r8
0x18002b1c8  mov     [r14], rbx
0x18002b1cb  mov     r12, rcx
0x18002b1ce  mov     [rbp+arg_40], rbx
0x18002b1d5  movups  xmmword ptr [rbp+DeviceType], xmm0
0x18002b1d9  test    r8, r8
0x18002b1dc  jnz     short loc_18002B1ED
0x18002b1de  test    r15b, r15b
0x18002b1e1  js      short loc_18002B1ED
0x18002b1e3  mov     eax, 0C000000Dh
0x18002b1e8  jmp     loc_18002B30A
0x18002b1ed  cmp     [rbp+arg_38], rbx
0x18002b1f1  jz      short loc_18002B20B
0x18002b1f3  mov     rcx, [rbp+arg_38]
0x18002b1f7  lea     r8, [rbp+DeviceType]
0x18002b1fb  mov     rdx, r12
0x18002b1fe  call    PpRegStateReadCreateClassCreationSettings
0x18002b203  test    eax, eax
0x18002b205  js      loc_18002B30A
0x18002b20b  mov     edi, [rbp+DeviceType]
0x18002b20e  test    dil, 2
0x18002b212  jnz     short loc_18002B266
0x18002b214  mov     rcx, [rbp+arg_30]
0x18002b218  lea     r8, [rbp+arg_10]
0x18002b21c  call    SeSddlSecurityDescriptorFromSDDL
0x18002b221  xor     ecx, ecx
0x18002b223  mov     ebx, eax
0x18002b225  test    eax, eax
0x18002b227  js      loc_18002B2F0
0x18002b22d  lea     edx, [rcx+2]
0x18002b230  mov     rax, [rbp+arg_10]
0x18002b234  mov     edi, edx
0x18002b236  mov     [rbp+DeviceType], edx
0x18002b239  mov     qword ptr [rbp+DeviceType+8], rax
0x18002b23d  cmp     [rbp+arg_38], rcx
0x18002b241  jz      short loc_18002B266
0x18002b243  mov     [rbp+var_18], rdx
0x18002b247  lea     rdx, [rbp+var_18]
0x18002b24b  mov     [rbp+var_8], rcx
0x18002b24f  mov     rcx, [rbp+arg_38]
0x18002b253  mov     [rbp+var_10], rax
0x18002b257  call    PpRegStateUpdateStackCreationSettings
0x18002b25c  mov     ebx, eax
0x18002b25e  test    eax, eax
0x18002b260  js      loc_18002B2F0
0x18002b266  mov     r9d, [rbp+arg_18]
0x18002b26a  test    dil, 1
0x18002b26e  movzx   ecx, [rbp+arg_28]
0x18002b272  mov     r8, r13; DeviceName
0x18002b275  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x18002b27a  test    dil, 4
0x18002b27e  movzx   eax, byte ptr [rbp+var_20+4]
0x18002b282  cmovnz  r15d, [rbp+var_20]
0x18002b287  test    dil, 8
0x18002b28b  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x18002b28e  cmovnz  ecx, eax
0x18002b291  lea     rax, [rbp+arg_40]
0x18002b298  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x18002b29d  mov     [rsp+70h+Exclusive], cl; Exclusive
0x18002b2a1  mov     rcx, r12; DriverObject
0x18002b2a4  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x18002b2a9  call    cs:__imp_IoCreateDevice
0x18002b2b0  nop     dword ptr [rax+rax+00h]
0x18002b2b5  mov     ebx, eax
0x18002b2b7  test    eax, eax
0x18002b2b9  js      short loc_18002B2F0
0x18002b2bb  mov     rcx, [rbp+arg_40]; Object
0x18002b2c2  lea     rdx, [rbp+DeviceType]
0x18002b2c6  call    IopDevObjApplyPostCreationSettings
0x18002b2cb  mov     ebx, eax
0x18002b2cd  test    eax, eax
0x18002b2cf  jns     short loc_18002B2E6
0x18002b2d1  mov     rcx, [rbp+arg_40]; DeviceObject
0x18002b2d8  call    cs:__imp_IoDeleteDevice
0x18002b2df  nop     dword ptr [rax+rax+00h]
0x18002b2e4  jmp     short loc_18002B2F0
0x18002b2e6  mov     rax, [rbp+arg_40]
0x18002b2ed  mov     [r14], rax
0x18002b2f0  test    dil, 2
0x18002b2f4  jz      short loc_18002B308
0x18002b2f6  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x18002b2fa  xor     edx, edx; Tag
0x18002b2fc  call    cs:__imp_ExFreePoolWithTag
0x18002b303  nop     dword ptr [rax+rax+00h]
0x18002b308  mov     eax, ebx
0x18002b30a  add     rsp, 70h
0x18002b30e  pop     r15
0x18002b310  pop     r14
0x18002b312  pop     r13
0x18002b314  pop     r12
0x18002b316  pop     rdi
0x18002b317  pop     rbx
0x18002b318  pop     rbp
0x18002b319  retn
```
