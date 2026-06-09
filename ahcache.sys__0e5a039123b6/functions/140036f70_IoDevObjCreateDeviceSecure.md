# IoDevObjCreateDeviceSecure

- ea: `0x140036f70`
- end: `0x1400370fb`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140036f70`
- `0x140037104`
- `0x1400371fc`
- `0x140037eec`
- `0x140038058`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400370dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400370dc`
- `ntoskrnl!IoDeleteDevice` at `0x1400370b8`
- `ntoskrnl!IoDeleteDevice` at `0x1400370b8`
- `ntoskrnl!IoCreateDevice` at `0x140037089`
- `ntoskrnl!IoCreateDevice` at `0x140037089`

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
0x140036f70  mov     [rsp-38h+arg_18], r9d
0x140036f75  mov     [rsp-38h+DeviceExtensionSize], edx
0x140036f79  push    rbp
0x140036f7a  push    rbx
0x140036f7b  push    rdi
0x140036f7c  push    r12
0x140036f7e  push    r13
0x140036f80  push    r14
0x140036f82  push    r15
0x140036f84  mov     rbp, rsp
0x140036f87  sub     rsp, 70h
0x140036f8b  mov     r14, [rbp+arg_40]
0x140036f92  xor     ebx, ebx
0x140036f94  mov     r15d, [rbp+arg_20]
0x140036f98  xor     eax, eax
0x140036f9a  mov     [rbp+arg_10], rbx
0x140036f9e  xorps   xmm0, xmm0
0x140036fa1  mov     qword ptr [rbp+var_20], rax
0x140036fa5  mov     r13, r8
0x140036fa8  mov     [r14], rbx
0x140036fab  mov     r12, rcx
0x140036fae  mov     [rbp+arg_40], rbx
0x140036fb5  movups  xmmword ptr [rbp+DeviceType], xmm0
0x140036fb9  test    r8, r8
0x140036fbc  jnz     short loc_140036FCD
0x140036fbe  test    r15b, r15b
0x140036fc1  js      short loc_140036FCD
0x140036fc3  mov     eax, 0C000000Dh
0x140036fc8  jmp     loc_1400370EA
0x140036fcd  cmp     [rbp+arg_38], rbx
0x140036fd1  jz      short loc_140036FEB
0x140036fd3  mov     rcx, [rbp+arg_38]
0x140036fd7  lea     r8, [rbp+DeviceType]
0x140036fdb  mov     rdx, r12
0x140036fde  call    PpRegStateReadCreateClassCreationSettings
0x140036fe3  test    eax, eax
0x140036fe5  js      loc_1400370EA
0x140036feb  mov     edi, [rbp+DeviceType]
0x140036fee  test    dil, 2
0x140036ff2  jnz     short loc_140037046
0x140036ff4  mov     rcx, [rbp+arg_30]
0x140036ff8  lea     r8, [rbp+arg_10]
0x140036ffc  call    SeSddlSecurityDescriptorFromSDDL
0x140037001  xor     ecx, ecx
0x140037003  mov     ebx, eax
0x140037005  test    eax, eax
0x140037007  js      loc_1400370D0
0x14003700d  lea     edx, [rcx+2]
0x140037010  mov     rax, [rbp+arg_10]
0x140037014  mov     edi, edx
0x140037016  mov     [rbp+DeviceType], edx
0x140037019  mov     qword ptr [rbp+DeviceType+8], rax
0x14003701d  cmp     [rbp+arg_38], rcx
0x140037021  jz      short loc_140037046
0x140037023  mov     [rbp+var_18], rdx
0x140037027  lea     rdx, [rbp+var_18]
0x14003702b  mov     [rbp+var_8], rcx
0x14003702f  mov     rcx, [rbp+arg_38]
0x140037033  mov     [rbp+var_10], rax
0x140037037  call    PpRegStateUpdateStackCreationSettings
0x14003703c  mov     ebx, eax
0x14003703e  test    eax, eax
0x140037040  js      loc_1400370D0
0x140037046  mov     r9d, [rbp+arg_18]
0x14003704a  test    dil, 1
0x14003704e  movzx   ecx, [rbp+arg_28]
0x140037052  mov     r8, r13; DeviceName
0x140037055  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x14003705a  test    dil, 4
0x14003705e  movzx   eax, byte ptr [rbp+var_20+4]
0x140037062  cmovnz  r15d, [rbp+var_20]
0x140037067  test    dil, 8
0x14003706b  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x14003706e  cmovnz  ecx, eax
0x140037071  lea     rax, [rbp+arg_40]
0x140037078  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x14003707d  mov     [rsp+70h+Exclusive], cl; Exclusive
0x140037081  mov     rcx, r12; DriverObject
0x140037084  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x140037089  call    cs:__imp_IoCreateDevice
0x140037090  nop     dword ptr [rax+rax+00h]
0x140037095  mov     ebx, eax
0x140037097  test    eax, eax
0x140037099  js      short loc_1400370D0
0x14003709b  mov     rcx, [rbp+arg_40]; Object
0x1400370a2  lea     rdx, [rbp+DeviceType]
0x1400370a6  call    IopDevObjApplyPostCreationSettings
0x1400370ab  mov     ebx, eax
0x1400370ad  test    eax, eax
0x1400370af  jns     short loc_1400370C6
0x1400370b1  mov     rcx, [rbp+arg_40]; DeviceObject
0x1400370b8  call    cs:__imp_IoDeleteDevice
0x1400370bf  nop     dword ptr [rax+rax+00h]
0x1400370c4  jmp     short loc_1400370D0
0x1400370c6  mov     rax, [rbp+arg_40]
0x1400370cd  mov     [r14], rax
0x1400370d0  test    dil, 2
0x1400370d4  jz      short loc_1400370E8
0x1400370d6  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x1400370da  xor     edx, edx; Tag
0x1400370dc  call    cs:__imp_ExFreePoolWithTag
0x1400370e3  nop     dword ptr [rax+rax+00h]
0x1400370e8  mov     eax, ebx
0x1400370ea  add     rsp, 70h
0x1400370ee  pop     r15
0x1400370f0  pop     r14
0x1400370f2  pop     r13
0x1400370f4  pop     r12
0x1400370f6  pop     rdi
0x1400370f7  pop     rbx
0x1400370f8  pop     rbp
0x1400370f9  retn
```
