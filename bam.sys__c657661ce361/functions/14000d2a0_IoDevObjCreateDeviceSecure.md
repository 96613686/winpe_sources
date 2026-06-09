# IoDevObjCreateDeviceSecure

- ea: `0x14000d2a0`
- end: `0x14000d42b`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000d2a0`
- `0x14000d434`
- `0x14000d52c`
- `0x14000e224`
- `0x14000e390`

## import_xrefs

- `ntoskrnl!IoDeleteDevice` at `0x14000d3e8`
- `ntoskrnl!IoDeleteDevice` at `0x14000d3e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d40c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d40c`
- `ntoskrnl!IoCreateDevice` at `0x14000d3b9`
- `ntoskrnl!IoCreateDevice` at `0x14000d3b9`

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
  int updated; // ebx
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
        || (v20[0] = 2,
            v20[2] = 0,
            v20[1] = v22,
            updated = PpRegStateUpdateStackCreationSettings(a8, (__int64)v20),
            updated >= 0) )
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
0x14000d2a0  mov     [rsp-38h+arg_18], r9d
0x14000d2a5  mov     [rsp-38h+DeviceExtensionSize], edx
0x14000d2a9  push    rbp
0x14000d2aa  push    rbx
0x14000d2ab  push    rdi
0x14000d2ac  push    r12
0x14000d2ae  push    r13
0x14000d2b0  push    r14
0x14000d2b2  push    r15
0x14000d2b4  mov     rbp, rsp
0x14000d2b7  sub     rsp, 70h
0x14000d2bb  mov     r14, [rbp+arg_40]
0x14000d2c2  xor     ebx, ebx
0x14000d2c4  mov     r15d, [rbp+arg_20]
0x14000d2c8  xor     eax, eax
0x14000d2ca  mov     [rbp+arg_10], rbx
0x14000d2ce  xorps   xmm0, xmm0
0x14000d2d1  mov     qword ptr [rbp+var_20], rax
0x14000d2d5  mov     r13, r8
0x14000d2d8  mov     [r14], rbx
0x14000d2db  mov     r12, rcx
0x14000d2de  mov     [rbp+arg_40], rbx
0x14000d2e5  movups  xmmword ptr [rbp+DeviceType], xmm0
0x14000d2e9  test    r8, r8
0x14000d2ec  jnz     short loc_14000D2FD
0x14000d2ee  test    r15b, r15b
0x14000d2f1  js      short loc_14000D2FD
0x14000d2f3  mov     eax, 0C000000Dh
0x14000d2f8  jmp     loc_14000D41A
0x14000d2fd  cmp     [rbp+arg_38], rbx
0x14000d301  jz      short loc_14000D31B
0x14000d303  mov     rcx, [rbp+arg_38]
0x14000d307  lea     r8, [rbp+DeviceType]
0x14000d30b  mov     rdx, r12
0x14000d30e  call    PpRegStateReadCreateClassCreationSettings
0x14000d313  test    eax, eax
0x14000d315  js      loc_14000D41A
0x14000d31b  mov     edi, [rbp+DeviceType]
0x14000d31e  test    dil, 2
0x14000d322  jnz     short loc_14000D376
0x14000d324  mov     rcx, [rbp+arg_30]
0x14000d328  lea     r8, [rbp+arg_10]
0x14000d32c  call    SeSddlSecurityDescriptorFromSDDL
0x14000d331  xor     ecx, ecx
0x14000d333  mov     ebx, eax
0x14000d335  test    eax, eax
0x14000d337  js      loc_14000D400
0x14000d33d  lea     edx, [rcx+2]
0x14000d340  mov     rax, [rbp+arg_10]
0x14000d344  mov     edi, edx
0x14000d346  mov     [rbp+DeviceType], edx
0x14000d349  mov     qword ptr [rbp+DeviceType+8], rax
0x14000d34d  cmp     [rbp+arg_38], rcx
0x14000d351  jz      short loc_14000D376
0x14000d353  mov     [rbp+var_18], rdx
0x14000d357  lea     rdx, [rbp+var_18]
0x14000d35b  mov     [rbp+var_8], rcx
0x14000d35f  mov     rcx, [rbp+arg_38]
0x14000d363  mov     [rbp+var_10], rax
0x14000d367  call    PpRegStateUpdateStackCreationSettings
0x14000d36c  mov     ebx, eax
0x14000d36e  test    eax, eax
0x14000d370  js      loc_14000D400
0x14000d376  mov     r9d, [rbp+arg_18]
0x14000d37a  test    dil, 1
0x14000d37e  movzx   ecx, [rbp+arg_28]
0x14000d382  mov     r8, r13; DeviceName
0x14000d385  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x14000d38a  test    dil, 4
0x14000d38e  movzx   eax, byte ptr [rbp+var_20+4]
0x14000d392  cmovnz  r15d, [rbp+var_20]
0x14000d397  test    dil, 8
0x14000d39b  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x14000d39e  cmovnz  ecx, eax
0x14000d3a1  lea     rax, [rbp+arg_40]
0x14000d3a8  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x14000d3ad  mov     [rsp+70h+Exclusive], cl; Exclusive
0x14000d3b1  mov     rcx, r12; DriverObject
0x14000d3b4  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x14000d3b9  call    cs:__imp_IoCreateDevice
0x14000d3c0  nop     dword ptr [rax+rax+00h]
0x14000d3c5  mov     ebx, eax
0x14000d3c7  test    eax, eax
0x14000d3c9  js      short loc_14000D400
0x14000d3cb  mov     rcx, [rbp+arg_40]; Object
0x14000d3d2  lea     rdx, [rbp+DeviceType]
0x14000d3d6  call    IopDevObjApplyPostCreationSettings
0x14000d3db  mov     ebx, eax
0x14000d3dd  test    eax, eax
0x14000d3df  jns     short loc_14000D3F6
0x14000d3e1  mov     rcx, [rbp+arg_40]; DeviceObject
0x14000d3e8  call    cs:__imp_IoDeleteDevice
0x14000d3ef  nop     dword ptr [rax+rax+00h]
0x14000d3f4  jmp     short loc_14000D400
0x14000d3f6  mov     rax, [rbp+arg_40]
0x14000d3fd  mov     [r14], rax
0x14000d400  test    dil, 2
0x14000d404  jz      short loc_14000D418
0x14000d406  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x14000d40a  xor     edx, edx; Tag
0x14000d40c  call    cs:__imp_ExFreePoolWithTag
0x14000d413  nop     dword ptr [rax+rax+00h]
0x14000d418  mov     eax, ebx
0x14000d41a  add     rsp, 70h
0x14000d41e  pop     r15
0x14000d420  pop     r14
0x14000d422  pop     r13
0x14000d424  pop     r12
0x14000d426  pop     rdi
0x14000d427  pop     rbx
0x14000d428  pop     rbp
0x14000d429  retn
```
