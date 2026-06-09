# IoDevObjCreateDeviceSecure

- ea: `0x140017230`
- end: `0x1400173bb`
- name: `IoDevObjCreateDeviceSecure`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PDRIVER_OBJECT DriverObject@<rcx>, int, char, __int64, __int64, PDEVICE_OBJECT)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140017230`
- `0x1400173c4`
- `0x1400174bc`
- `0x1400181c4`
- `0x140018330`

## import_xrefs

- `ntoskrnl!IoCreateDevice` at `0x140017349`
- `ntoskrnl!IoCreateDevice` at `0x140017349`
- `ntoskrnl!IoDeleteDevice` at `0x140017378`
- `ntoskrnl!IoDeleteDevice` at `0x140017378`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001739c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001739c`

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
0x140017230  mov     [rsp-38h+arg_18], r9d
0x140017235  mov     [rsp-38h+DeviceExtensionSize], edx
0x140017239  push    rbp
0x14001723a  push    rbx
0x14001723b  push    rdi
0x14001723c  push    r12
0x14001723e  push    r13
0x140017240  push    r14
0x140017242  push    r15
0x140017244  mov     rbp, rsp
0x140017247  sub     rsp, 70h
0x14001724b  mov     r14, [rbp+arg_40]
0x140017252  xor     ebx, ebx
0x140017254  mov     r15d, [rbp+arg_20]
0x140017258  xor     eax, eax
0x14001725a  mov     [rbp+arg_10], rbx
0x14001725e  xorps   xmm0, xmm0
0x140017261  mov     qword ptr [rbp+var_20], rax
0x140017265  mov     r13, r8
0x140017268  mov     [r14], rbx
0x14001726b  mov     r12, rcx
0x14001726e  mov     [rbp+arg_40], rbx
0x140017275  movups  xmmword ptr [rbp+DeviceType], xmm0
0x140017279  test    r8, r8
0x14001727c  jnz     short loc_14001728D
0x14001727e  test    r15b, r15b
0x140017281  js      short loc_14001728D
0x140017283  mov     eax, 0C000000Dh
0x140017288  jmp     loc_1400173AA
0x14001728d  cmp     [rbp+arg_38], rbx
0x140017291  jz      short loc_1400172AB
0x140017293  mov     rcx, [rbp+arg_38]
0x140017297  lea     r8, [rbp+DeviceType]
0x14001729b  mov     rdx, r12
0x14001729e  call    PpRegStateReadCreateClassCreationSettings
0x1400172a3  test    eax, eax
0x1400172a5  js      loc_1400173AA
0x1400172ab  mov     edi, [rbp+DeviceType]
0x1400172ae  test    dil, 2
0x1400172b2  jnz     short loc_140017306
0x1400172b4  mov     rcx, [rbp+arg_30]
0x1400172b8  lea     r8, [rbp+arg_10]
0x1400172bc  call    SeSddlSecurityDescriptorFromSDDL
0x1400172c1  xor     ecx, ecx
0x1400172c3  mov     ebx, eax
0x1400172c5  test    eax, eax
0x1400172c7  js      loc_140017390
0x1400172cd  lea     edx, [rcx+2]
0x1400172d0  mov     rax, [rbp+arg_10]
0x1400172d4  mov     edi, edx
0x1400172d6  mov     [rbp+DeviceType], edx
0x1400172d9  mov     qword ptr [rbp+DeviceType+8], rax
0x1400172dd  cmp     [rbp+arg_38], rcx
0x1400172e1  jz      short loc_140017306
0x1400172e3  mov     [rbp+var_18], rdx
0x1400172e7  lea     rdx, [rbp+var_18]
0x1400172eb  mov     [rbp+var_8], rcx
0x1400172ef  mov     rcx, [rbp+arg_38]
0x1400172f3  mov     [rbp+var_10], rax
0x1400172f7  call    PpRegStateUpdateStackCreationSettings
0x1400172fc  mov     ebx, eax
0x1400172fe  test    eax, eax
0x140017300  js      loc_140017390
0x140017306  mov     r9d, [rbp+arg_18]
0x14001730a  test    dil, 1
0x14001730e  movzx   ecx, [rbp+arg_28]
0x140017312  mov     r8, r13; DeviceName
0x140017315  cmovnz  r9d, [rbp+DeviceType+4]; DeviceType
0x14001731a  test    dil, 4
0x14001731e  movzx   eax, byte ptr [rbp+var_20+4]
0x140017322  cmovnz  r15d, [rbp+var_20]
0x140017327  test    dil, 8
0x14001732b  mov     edx, [rbp+DeviceExtensionSize]; DeviceExtensionSize
0x14001732e  cmovnz  ecx, eax
0x140017331  lea     rax, [rbp+arg_40]
0x140017338  mov     [rsp+70h+DeviceObject], rax; DeviceObject
0x14001733d  mov     [rsp+70h+Exclusive], cl; Exclusive
0x140017341  mov     rcx, r12; DriverObject
0x140017344  mov     [rsp+70h+DeviceCharacteristics], r15d; DeviceCharacteristics
0x140017349  call    cs:__imp_IoCreateDevice
0x140017350  nop     dword ptr [rax+rax+00h]
0x140017355  mov     ebx, eax
0x140017357  test    eax, eax
0x140017359  js      short loc_140017390
0x14001735b  mov     rcx, [rbp+arg_40]; Object
0x140017362  lea     rdx, [rbp+DeviceType]
0x140017366  call    IopDevObjApplyPostCreationSettings
0x14001736b  mov     ebx, eax
0x14001736d  test    eax, eax
0x14001736f  jns     short loc_140017386
0x140017371  mov     rcx, [rbp+arg_40]; DeviceObject
0x140017378  call    cs:__imp_IoDeleteDevice
0x14001737f  nop     dword ptr [rax+rax+00h]
0x140017384  jmp     short loc_140017390
0x140017386  mov     rax, [rbp+arg_40]
0x14001738d  mov     [r14], rax
0x140017390  test    dil, 2
0x140017394  jz      short loc_1400173A8
0x140017396  mov     rcx, qword ptr [rbp+DeviceType+8]; P
0x14001739a  xor     edx, edx; Tag
0x14001739c  call    cs:__imp_ExFreePoolWithTag
0x1400173a3  nop     dword ptr [rax+rax+00h]
0x1400173a8  mov     eax, ebx
0x1400173aa  add     rsp, 70h
0x1400173ae  pop     r15
0x1400173b0  pop     r14
0x1400173b2  pop     r13
0x1400173b4  pop     r12
0x1400173b6  pop     rdi
0x1400173b7  pop     rbx
0x1400173b8  pop     rbp
0x1400173b9  retn
```
