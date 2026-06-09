# IoDevObjCreateDeviceSecure

- ea: `0x140024790`
- end: `0x14002491b`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, __int64, struct _UNICODE_STRING *, ULONG, ULONG, BOOLEAN, __int64, __int64, PDEVICE_OBJECT DeviceObject)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140024790`
- `0x140024924`
- `0x140024a1c`
- `0x140025724`
- `0x140025890`

## import_xrefs

- `ntoskrnl!IoCreateDevice` at `0x1400248a9`
- `ntoskrnl!IoCreateDevice` at `0x1400248a9`
- `ntoskrnl!IoDeleteDevice` at `0x1400248d8`
- `ntoskrnl!IoDeleteDevice` at `0x1400248d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400248fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400248fc`

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
0x140024790  mov     [rsp-38h+arg_18], r9d
0x140024795  mov     [rsp-38h+DeviceExtensionSize], edx
0x140024799  push    rbp
0x14002479a  push    rbx
0x14002479b  push    rdi
0x14002479c  push    r12
0x14002479e  push    r13
0x1400247a0  push    r14
0x1400247a2  push    r15
0x1400247a4  mov     rbp, rsp
0x1400247a7  sub     rsp, 70h
0x1400247ab  mov     r14, [rbp+arg_40]
0x1400247b2  xor     ebx, ebx
0x1400247b4  mov     r15d, [rbp+arg_20]
0x1400247b8  xor     eax, eax
0x1400247ba  mov     [rbp+arg_10], rbx
0x1400247be  xorps   xmm0, xmm0
0x1400247c1  mov     qword ptr [rbp+var_20], rax
0x1400247c5  mov     r13, r8
0x1400247c8  mov     [r14], rbx
0x1400247cb  mov     r12, rcx
0x1400247ce  mov     [rbp+arg_40], rbx
0x1400247d5  movups  xmmword ptr [rbp+DeviceType], xmm0
0x1400247d9  test    r8, r8
0x1400247dc  jnz     short loc_1400247ED
0x1400247de  test    r15b, r15b
0x1400247e1  js      short loc_1400247ED
0x1400247e3  mov     eax, 0C000000Dh
0x1400247e8  jmp     loc_14002490A
0x1400247ed  cmp     [rbp+arg_38], rbx
0x1400247f1  jz      short loc_14002480B
0x1400247f3  mov     rcx, [rbp+arg_38]
0x1400247f7  lea     r8, [rbp+DeviceType]
0x1400247fb  mov     rdx, r12
0x1400247fe  call    PpRegStateReadCreateClassCreationSettings
0x140024803  test    eax, eax
0x140024805  js      loc_14002490A
0x14002480b  mov     edi, [rbp+DeviceType]
0x14002480e  test    dil, 2
0x140024812  jnz     short loc_140024866
0x140024814  mov     rcx, [rbp+arg_30]
0x140024818  lea     r8, [rbp+arg_10]
0x14002481c  call    SeSddlSecurityDescriptorFromSDDL
0x140024821  xor     ecx, ecx
0x140024823  mov     ebx, eax
0x140024825  test    eax, eax
0x140024827  js      loc_1400248F0
0x14002482d  lea     edx, [rcx+2]
0x140024830  mov     rax, [rbp+arg_10]
0x140024834  mov     edi, edx
0x140024836  mov     [rbp+DeviceType], edx
0x140024839  mov     qword ptr [rbp+DeviceType+8], rax
0x14002483d  cmp     [rbp+arg_38], rcx
0x140024841  jz      short loc_140024866
0x140024843  mov     [rbp+var_18], rdx
0x140024847  lea     rdx, [rbp+var_18]
0x14002484b  mov     [rbp+var_8], rcx
0x14002484f  mov     rcx, [rbp+arg_38]
0x140024853  mov     [rbp+var_10], rax
0x140024857  call    PpRegStateUpdateStackCreationSettings
0x14002485c  mov     ebx, eax
0x14002485e  test    eax, eax
0x140024860  js      loc_1400248F0
0x140024866  mov     r9d, [rbp+arg_18]
0x14002486a  test    dil, 1
0x14002486e  movzx   ecx, [rbp+arg_28]
0x140024872  mov     r8, r13; DeviceName
0x140024875  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x14002487a  test    dil, 4
0x14002487e  movzx   eax, byte ptr [rbp+var_20+4]
0x140024882  cmovnz  r15d, [rbp+var_20]
0x140024887  test    dil, 8
0x14002488b  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x14002488e  cmovnz  ecx, eax
0x140024891  lea     rax, [rbp+arg_40]
0x140024898  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x14002489d  mov     [rsp+70h+Exclusive], cl; Exclusive
0x1400248a1  mov     rcx, r12; DriverObject
0x1400248a4  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x1400248a9  call    cs:__imp_IoCreateDevice
0x1400248b0  nop     dword ptr [rax+rax+00h]
0x1400248b5  mov     ebx, eax
0x1400248b7  test    eax, eax
0x1400248b9  js      short loc_1400248F0
0x1400248bb  mov     rcx, [rbp+arg_40]; Object
0x1400248c2  lea     rdx, [rbp+DeviceType]
0x1400248c6  call    IopDevObjApplyPostCreationSettings
0x1400248cb  mov     ebx, eax
0x1400248cd  test    eax, eax
0x1400248cf  jns     short loc_1400248E6
0x1400248d1  mov     rcx, [rbp+arg_40]; DeviceObject
0x1400248d8  call    cs:__imp_IoDeleteDevice
0x1400248df  nop     dword ptr [rax+rax+00h]
0x1400248e4  jmp     short loc_1400248F0
0x1400248e6  mov     rax, [rbp+arg_40]
0x1400248ed  mov     [r14], rax
0x1400248f0  test    dil, 2
0x1400248f4  jz      short loc_140024908
0x1400248f6  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x1400248fa  xor     edx, edx; Tag
0x1400248fc  call    cs:__imp_ExFreePoolWithTag
0x140024903  nop     dword ptr [rax+rax+00h]
0x140024908  mov     eax, ebx
0x14002490a  add     rsp, 70h
0x14002490e  pop     r15
0x140024910  pop     r14
0x140024912  pop     r13
0x140024914  pop     r12
0x140024916  pop     rdi
0x140024917  pop     rbx
0x140024918  pop     rbp
0x140024919  retn
```
