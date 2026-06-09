# IoDevObjCreateDeviceSecure

- ea: `0x1400aa8c0`
- end: `0x1400aaa4b`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject, __int64, struct _UNICODE_STRING *, ULONG, ULONG, BOOLEAN, __int64, __int64, PDEVICE_OBJECT DeviceObject)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400aa8c0`
- `0x1400aaa54`
- `0x1400aab4c`
- `0x1400ab844`
- `0x1400ab9b0`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x1400aaa08`
- `ntoskrnl!IoDeleteDevice` at `0x1400aaa08`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aaa2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aaa2c`
- `ntoskrnl!IoCreateDevice` at `0x1400aa9d9`
- `ntoskrnl!IoCreateDevice` at `0x1400aa9d9`

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
          updated = IopDevObjApplyPostCreationSettings(DeviceObject, (__int64)DeviceType);
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
0x1400aa8c0  mov     [rsp-38h+arg_18], r9d
0x1400aa8c5  mov     [rsp-38h+DeviceExtensionSize], edx
0x1400aa8c9  push    rbp
0x1400aa8ca  push    rbx
0x1400aa8cb  push    rdi
0x1400aa8cc  push    r12
0x1400aa8ce  push    r13
0x1400aa8d0  push    r14
0x1400aa8d2  push    r15
0x1400aa8d4  mov     rbp, rsp
0x1400aa8d7  sub     rsp, 70h
0x1400aa8db  mov     r14, [rbp+arg_40]
0x1400aa8e2  xor     ebx, ebx
0x1400aa8e4  mov     r15d, [rbp+arg_20]
0x1400aa8e8  xor     eax, eax
0x1400aa8ea  mov     [rbp+arg_10], rbx
0x1400aa8ee  xorps   xmm0, xmm0
0x1400aa8f1  mov     qword ptr [rbp+var_20], rax
0x1400aa8f5  mov     r13, r8
0x1400aa8f8  mov     [r14], rbx
0x1400aa8fb  mov     r12, rcx
0x1400aa8fe  mov     [rbp+arg_40], rbx
0x1400aa905  movups  xmmword ptr [rbp+DeviceType], xmm0
0x1400aa909  test    r8, r8
0x1400aa90c  jnz     short loc_1400AA91D
0x1400aa90e  test    r15b, r15b
0x1400aa911  js      short loc_1400AA91D
0x1400aa913  mov     eax, 0C000000Dh
0x1400aa918  jmp     loc_1400AAA3A
0x1400aa91d  cmp     [rbp+arg_38], rbx
0x1400aa921  jz      short loc_1400AA93B
0x1400aa923  mov     rcx, [rbp+arg_38]
0x1400aa927  lea     r8, [rbp+DeviceType]
0x1400aa92b  mov     rdx, r12
0x1400aa92e  call    PpRegStateReadCreateClassCreationSettings
0x1400aa933  test    eax, eax
0x1400aa935  js      loc_1400AAA3A
0x1400aa93b  mov     edi, [rbp+DeviceType]
0x1400aa93e  test    dil, 2
0x1400aa942  jnz     short loc_1400AA996
0x1400aa944  mov     rcx, [rbp+arg_30]
0x1400aa948  lea     r8, [rbp+arg_10]
0x1400aa94c  call    SeSddlSecurityDescriptorFromSDDL
0x1400aa951  xor     ecx, ecx
0x1400aa953  mov     ebx, eax
0x1400aa955  test    eax, eax
0x1400aa957  js      loc_1400AAA20
0x1400aa95d  lea     edx, [rcx+2]
0x1400aa960  mov     rax, [rbp+arg_10]
0x1400aa964  mov     edi, edx
0x1400aa966  mov     [rbp+DeviceType], edx
0x1400aa969  mov     qword ptr [rbp+DeviceType+8], rax
0x1400aa96d  cmp     [rbp+arg_38], rcx
0x1400aa971  jz      short loc_1400AA996
0x1400aa973  mov     [rbp+var_18], rdx
0x1400aa977  lea     rdx, [rbp+var_18]
0x1400aa97b  mov     [rbp+var_8], rcx
0x1400aa97f  mov     rcx, [rbp+arg_38]
0x1400aa983  mov     [rbp+var_10], rax
0x1400aa987  call    PpRegStateUpdateStackCreationSettings
0x1400aa98c  mov     ebx, eax
0x1400aa98e  test    eax, eax
0x1400aa990  js      loc_1400AAA20
0x1400aa996  mov     r9d, [rbp+arg_18]
0x1400aa99a  test    dil, 1
0x1400aa99e  movzx   ecx, [rbp+arg_28]
0x1400aa9a2  mov     r8, r13; DeviceName
0x1400aa9a5  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x1400aa9aa  test    dil, 4
0x1400aa9ae  movzx   eax, byte ptr [rbp+var_20+4]
0x1400aa9b2  cmovnz  r15d, [rbp+var_20]
0x1400aa9b7  test    dil, 8
0x1400aa9bb  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x1400aa9be  cmovnz  ecx, eax
0x1400aa9c1  lea     rax, [rbp+arg_40]
0x1400aa9c8  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x1400aa9cd  mov     [rsp+70h+Exclusive], cl; Exclusive
0x1400aa9d1  mov     rcx, r12; DriverObject
0x1400aa9d4  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x1400aa9d9  call    cs:__imp_IoCreateDevice
0x1400aa9e0  nop     dword ptr [rax+rax+00h]
0x1400aa9e5  mov     ebx, eax
0x1400aa9e7  test    eax, eax
0x1400aa9e9  js      short loc_1400AAA20
0x1400aa9eb  mov     rcx, [rbp+arg_40]; Object
0x1400aa9f2  lea     rdx, [rbp+DeviceType]
0x1400aa9f6  call    IopDevObjApplyPostCreationSettings
0x1400aa9fb  mov     ebx, eax
0x1400aa9fd  test    eax, eax
0x1400aa9ff  jns     short loc_1400AAA16
0x1400aaa01  mov     rcx, [rbp+arg_40]; DeviceObject
0x1400aaa08  call    cs:__imp_IoDeleteDevice
0x1400aaa0f  nop     dword ptr [rax+rax+00h]
0x1400aaa14  jmp     short loc_1400AAA20
0x1400aaa16  mov     rax, [rbp+arg_40]
0x1400aaa1d  mov     [r14], rax
0x1400aaa20  test    dil, 2
0x1400aaa24  jz      short loc_1400AAA38
0x1400aaa26  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x1400aaa2a  xor     edx, edx; Tag
0x1400aaa2c  call    cs:__imp_ExFreePoolWithTag
0x1400aaa33  nop     dword ptr [rax+rax+00h]
0x1400aaa38  mov     eax, ebx
0x1400aaa3a  add     rsp, 70h
0x1400aaa3e  pop     r15
0x1400aaa40  pop     r14
0x1400aaa42  pop     r13
0x1400aaa44  pop     r12
0x1400aaa46  pop     rdi
0x1400aaa47  pop     rbx
0x1400aaa48  pop     rbp
0x1400aaa49  retn
```
