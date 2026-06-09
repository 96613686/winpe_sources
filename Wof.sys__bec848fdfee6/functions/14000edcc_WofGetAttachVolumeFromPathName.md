# WofGetAttachVolumeFromPathName

- ea: `0x14000edcc`
- end: `0x14000f142`
- name: `WofGetAttachVolumeFromPathName`
- size: `886`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _UNICODE_STRING *, PVOID *, _QWORD *)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140026440`
- `0x140026fb0`
- `0x140027870`
- `0x14002d844`

## callees

- `0x1400014d0`
- `0x14000dc88`
- `0x14000ec24`
- `0x14000edcc`
- `0x14002521c`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ef1c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14000ef1c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000ee2a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000ee2a`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ef8d`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f032`
- `ntoskrnl!ObfDereferenceObject` at `0x14000ef8d`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f032`
- `FLTMGR!FltGetVolumeFromFileObject` at `0x14000efd0`
- `FLTMGR!FltGetVolumeFromFileObject` at `0x14000efd0`
- `FLTMGR!FltCreateFileEx` at `0x14000eeac`
- `FLTMGR!FltCreateFileEx` at `0x14000eeac`
- `FLTMGR!FltAttachVolume` at `0x14000f054`
- `FLTMGR!FltAttachVolume` at `0x14000f054`
- `FLTMGR!FltObjectDereference` at `0x14000ef4e`
- `FLTMGR!FltObjectDereference` at `0x14000ef63`
- `FLTMGR!FltObjectDereference` at `0x14000ef4e`
- `FLTMGR!FltObjectDereference` at `0x14000ef63`
- `FLTMGR!FltEnumerateInstances` at `0x14000f0c6`
- `FLTMGR!FltEnumerateInstances` at `0x14000f0c6`
- `FLTMGR!FltClose` at `0x14000ef78`
- `FLTMGR!FltClose` at `0x14000f01e`
- `FLTMGR!FltClose` at `0x14000ef78`
- `FLTMGR!FltClose` at `0x14000f01e`
- `FLTMGR!FltReleaseContext` at `0x14000ef39`
- `FLTMGR!FltReleaseContext` at `0x14000ef39`

## pseudocode

```c
__int64 __fastcall WofGetAttachVolumeFromPathName(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        PVOID *a3,
        _QWORD *a4)
{
  void *v8; // rdi
  NTSTATUS VolumeFromFileObject; // ebx
  int v10; // edx
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  struct _FLT_INSTANCE *v15; // rcx
  int v16; // edx
  int v17; // r8d
  int DesiredAccess; // [rsp+20h] [rbp-E0h]
  PVOID v19; // [rsp+80h] [rbp-80h] BYREF
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-78h] BYREF
  PVOID FltObject; // [rsp+90h] [rbp-70h] BYREF
  void *v22; // [rsp+98h] [rbp-68h]
  void *FileHandle; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A8h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E8h] [rbp-18h] BYREF
  ULONG NumberInstancesReturned; // [rsp+150h] [rbp+50h] BYREF

  v19 = 0;
  FltObject = 0;
  v22 = 0;
  FileHandle = 0;
  FileObject = 0;
  v8 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  VolumeFromFileObject = FltCreateFileEx(
                           WofGlobal,
                           0,
                           &FileHandle,
                           &FileObject,
                           0x80u,
                           &ObjectAttributes,
                           &IoStatusBlock,
                           0,
                           0,
                           1u,
                           1u,
                           0x20u,
                           0,
                           0,
                           0);
  if ( VolumeFromFileObject < 0 )
    goto LABEL_6;
  if ( a2 )
  {
    VolumeFromFileObject = WofQueryVolumeRelativeName(FileObject, &DestinationString);
    if ( VolumeFromFileObject < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          4,
          15,
          (__int64)WPP_0d3c4c833653390108f193f53084a201_Traceguids,
          VolumeFromFileObject);
      }
      goto LABEL_6;
    }
    *a2 = DestinationString;
  }
  if ( !a3 )
  {
LABEL_39:
    VolumeFromFileObject = 0;
    goto LABEL_8;
  }
  VolumeFromFileObject = FltGetVolumeFromFileObject(WofGlobal, FileObject, (PFLT_VOLUME *)&v19);
  if ( VolumeFromFileObject < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_6;
    v14 = 16;
    goto LABEL_24;
  }
  FltClose(FileHandle);
  FileHandle = 0;
  ObfDereferenceObject(FileObject);
  FileObject = 0;
  VolumeFromFileObject = FltAttachVolume(WofGlobal, (PFLT_VOLUME)v19, 0, (PFLT_INSTANCE *)&FltObject);
  if ( (int)(VolumeFromFileObject + 0x80000000) < 0 || VolumeFromFileObject == -1071906798 )
  {
    if ( a4 )
    {
      v15 = (struct _FLT_INSTANCE *)FltObject;
      if ( !FltObject )
      {
        NumberInstancesReturned = 0;
        VolumeFromFileObject = FltEnumerateInstances(
                                 (PFLT_VOLUME)v19,
                                 WofGlobal,
                                 (PFLT_INSTANCE *)&FltObject,
                                 1u,
                                 &NumberInstancesReturned);
        if ( VolumeFromFileObject < 0 )
          goto LABEL_6;
        v15 = (struct _FLT_INSTANCE *)FltObject;
      }
      VolumeFromFileObject = WofGetVolumeContext(v15);
      if ( VolumeFromFileObject < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_ZD(
            WPP_GLOBAL_Control->DeviceExtension,
            v16,
            v17,
            18,
            DesiredAccess,
            (__int64)a1,
            VolumeFromFileObject);
        v8 = v22;
        goto LABEL_6;
      }
      *a4 = v22;
    }
    *a3 = v19;
    v19 = 0;
    goto LABEL_39;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v14 = 17;
LABEL_24:
    WPP_RECORDER_SF_ZD(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      v13,
      v14,
      DesiredAccess,
      (__int64)a1,
      VolumeFromFileObject);
  }
LABEL_6:
  RtlFreeUnicodeString(&DestinationString);
  if ( a2 )
    a2->Buffer = 0;
LABEL_8:
  if ( v8 )
    FltReleaseContext(v8);
  if ( FltObject )
    FltObjectDereference(FltObject);
  if ( v19 )
    FltObjectDereference(v19);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  return (unsigned int)VolumeFromFileObject;
}

```

## disassembly

```asm
0x14000edcc  push    rbp
0x14000edce  push    rbx
0x14000edcf  push    rsi
0x14000edd0  push    rdi
0x14000edd1  push    r12
0x14000edd3  push    r13
0x14000edd5  push    r14
0x14000edd7  push    r15
0x14000edd9  lea     rbp, [rsp-8]
0x14000edde  sub     rsp, 108h
0x14000ede5  xorps   xmm0, xmm0
0x14000ede8  xor     r13d, r13d
0x14000edeb  mov     rsi, rdx
0x14000edee  mov     [rbp+40h+var_C0], r13
0x14000edf2  mov     r14, rcx
0x14000edf5  mov     [rbp+40h+FltObject], r13
0x14000edf9  movups  xmmword ptr [rbp+40h+var_88.ObjectName], xmm0
0x14000edfd  xor     eax, eax
0x14000edff  mov     [rbp+40h+var_A8], r13
0x14000ee03  xor     edx, edx; SourceString
0x14000ee05  mov     [rbp+40h+FileHandle], r13
0x14000ee09  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x14000ee0d  mov     [rbp+40h+FileObject], r13
0x14000ee11  movups  xmmword ptr [rbp+40h+var_88+1Ch], xmm0
0x14000ee15  mov     r12, r9
0x14000ee18  mov     r15, r8
0x14000ee1b  mov     edi, r13d
0x14000ee1e  movups  xmmword ptr [rbp+40h+var_88.Length], xmm0
0x14000ee22  movups  xmmword ptr [rbp+40h+var_58], xmm0
0x14000ee26  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm0
0x14000ee2a  call    cs:__imp_RtlInitUnicodeString
0x14000ee31  nop     dword ptr [rax+rax+00h]
0x14000ee36  mov     rcx, cs:WofGlobal; Filter
0x14000ee3d  lea     eax, [r13+1]
0x14000ee41  mov     [rsp+140h+Flags], r13d; Flags
0x14000ee46  lea     r9, [rbp+40h+FileObject]; FileObject
0x14000ee4a  mov     [rsp+140h+EaLength], r13d; EaLength
0x14000ee4f  lea     r8, [rbp+40h+FileHandle]; FileHandle
0x14000ee53  mov     [rsp+140h+EaBuffer], r13; EaBuffer
0x14000ee58  xorps   xmm0, xmm0
0x14000ee5b  mov     [rsp+140h+CreateOptions], 20h ; ' '; CreateOptions
0x14000ee63  xor     edx, edx; Instance
0x14000ee65  mov     [rsp+140h+CreateDisposition], eax; CreateDisposition
0x14000ee69  mov     [rsp+140h+ShareAccess], eax; ShareAccess
0x14000ee6d  lea     rax, [rbp+40h+var_58]
0x14000ee71  mov     [rsp+140h+FileAttributes], r13d; FileAttributes
0x14000ee76  mov     [rsp+140h+AllocationSize], r13; AllocationSize
0x14000ee7b  mov     [rsp+140h+IoStatusBlock], rax; IoStatusBlock
0x14000ee80  lea     rax, [rbp+40h+var_88]
0x14000ee84  mov     [rsp+140h+ObjectAttributes], rax; ObjectAttributes
0x14000ee89  mov     [rsp+140h+DesiredAccess], 80h; DesiredAccess
0x14000ee91  mov     [rbp+40h+var_88.Length], 30h ; '0'
0x14000ee98  mov     [rbp+40h+var_88.RootDirectory], r13
0x14000ee9c  mov     [rbp+40h+var_88.Attributes], 240h
0x14000eea3  mov     [rbp+40h+var_88.ObjectName], r14
0x14000eea7  movdqu  xmmword ptr [rbp+40h+var_88.SecurityDescriptor], xmm0
0x14000eeac  call    cs:__imp_FltCreateFileEx
0x14000eeb3  nop     dword ptr [rax+rax+00h]
0x14000eeb8  mov     ebx, eax
0x14000eeba  test    eax, eax
0x14000eebc  js      short loc_14000EF18
0x14000eebe  test    rsi, rsi
0x14000eec1  jz      loc_14000EFB8
0x14000eec7  mov     rcx, [rbp+40h+FileObject]
0x14000eecb  lea     rdx, [rbp+40h+DestinationString]
0x14000eecf  call    WofQueryVolumeRelativeName
0x14000eed4  mov     ebx, eax
0x14000eed6  test    eax, eax
0x14000eed8  jns     loc_14000EFB0
0x14000eede  lea     rax, WPP_RECORDER_INITIALIZED
0x14000eee5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000eeec  jz      short loc_14000EF18
0x14000eeee  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eef5  lea     rax, WPP_0d3c4c833653390108f193f53084a201_Traceguids
0x14000eefc  lea     r9d, [r13+0Fh]
0x14000ef00  mov     dword ptr [rsp+140h+ObjectAttributes], ebx
0x14000ef04  lea     r8d, [r13+4]
0x14000ef08  mov     qword ptr [rsp+140h+DesiredAccess], rax
0x14000ef0d  mov     dl, 2
0x14000ef0f  mov     rcx, [rcx+40h]
0x14000ef13  call    WPP_RECORDER_SF_d
0x14000ef18  lea     rcx, [rbp+40h+DestinationString]; UnicodeString
0x14000ef1c  call    cs:__imp_RtlFreeUnicodeString
0x14000ef23  nop     dword ptr [rax+rax+00h]
0x14000ef28  test    rsi, rsi
0x14000ef2b  jz      short loc_14000EF31
0x14000ef2d  mov     [rsi+8], r13
0x14000ef31  test    rdi, rdi
0x14000ef34  jz      short loc_14000EF45
0x14000ef36  mov     rcx, rdi; Context
0x14000ef39  call    cs:__imp_FltReleaseContext
0x14000ef40  nop     dword ptr [rax+rax+00h]
0x14000ef45  mov     rcx, [rbp+40h+FltObject]; FltObject
0x14000ef49  test    rcx, rcx
0x14000ef4c  jz      short loc_14000EF5A
0x14000ef4e  call    cs:__imp_FltObjectDereference
0x14000ef55  nop     dword ptr [rax+rax+00h]
0x14000ef5a  mov     rcx, [rbp+40h+var_C0]; FltObject
0x14000ef5e  test    rcx, rcx
0x14000ef61  jz      short loc_14000EF6F
0x14000ef63  call    cs:__imp_FltObjectDereference
0x14000ef6a  nop     dword ptr [rax+rax+00h]
0x14000ef6f  mov     rcx, [rbp+40h+FileHandle]; FileHandle
0x14000ef73  test    rcx, rcx
0x14000ef76  jz      short loc_14000EF84
0x14000ef78  call    cs:__imp_FltClose
0x14000ef7f  nop     dword ptr [rax+rax+00h]
0x14000ef84  mov     rcx, [rbp+40h+FileObject]; Object
0x14000ef88  test    rcx, rcx
0x14000ef8b  jz      short loc_14000EF99
0x14000ef8d  call    cs:__imp_ObfDereferenceObject
0x14000ef94  nop     dword ptr [rax+rax+00h]
0x14000ef99  mov     eax, ebx
0x14000ef9b  add     rsp, 108h
0x14000efa2  pop     r15
0x14000efa4  pop     r14
0x14000efa6  pop     r13
0x14000efa8  pop     r12
0x14000efaa  pop     rdi
0x14000efab  pop     rsi
0x14000efac  pop     rbx
0x14000efad  pop     rbp
0x14000efae  retn
0x14000efb0  movups  xmm0, xmmword ptr [rbp+40h+DestinationString.Length]
0x14000efb4  movdqu  xmmword ptr [rsi], xmm0
0x14000efb8  test    r15, r15
0x14000efbb  jz      loc_14000F13A
0x14000efc1  mov     rdx, [rbp+40h+FileObject]; FileObject
0x14000efc5  lea     r8, [rbp+40h+var_C0]; RetVolume
0x14000efc9  mov     rcx, cs:WofGlobal; Filter
0x14000efd0  call    cs:__imp_FltGetVolumeFromFileObject
0x14000efd7  nop     dword ptr [rax+rax+00h]
0x14000efdc  mov     ebx, eax
0x14000efde  test    eax, eax
0x14000efe0  jns     short loc_14000F01A
0x14000efe2  lea     rax, WPP_RECORDER_INITIALIZED
0x14000efe9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000eff0  jz      loc_14000EF18
0x14000eff6  mov     r9d, 10h
0x14000effc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f003  mov     dword ptr [rsp+140h+IoStatusBlock], ebx
0x14000f007  mov     [rsp+140h+ObjectAttributes], r14
0x14000f00c  mov     rcx, [rcx+40h]
0x14000f010  call    WPP_RECORDER_SF_ZD
0x14000f015  jmp     loc_14000EF18
0x14000f01a  mov     rcx, [rbp+40h+FileHandle]; FileHandle
0x14000f01e  call    cs:__imp_FltClose
0x14000f025  nop     dword ptr [rax+rax+00h]
0x14000f02a  mov     rcx, [rbp+40h+FileObject]; Object
0x14000f02e  mov     [rbp+40h+FileHandle], r13
0x14000f032  call    cs:__imp_ObfDereferenceObject
0x14000f039  nop     dword ptr [rax+rax+00h]
0x14000f03e  mov     rdx, [rbp+40h+var_C0]; Volume
0x14000f042  lea     r9, [rbp+40h+FltObject]; RetInstance
0x14000f046  mov     rcx, cs:WofGlobal; Filter
0x14000f04d  xor     r8d, r8d; InstanceName
0x14000f050  mov     [rbp+40h+FileObject], r13
0x14000f054  call    cs:__imp_FltAttachVolume
0x14000f05b  nop     dword ptr [rax+rax+00h]
0x14000f060  mov     ecx, 80000000h
0x14000f065  mov     ebx, eax
0x14000f067  add     eax, ecx
0x14000f069  test    ecx, eax
0x14000f06b  jnz     short loc_14000F094
0x14000f06d  cmp     ebx, 0C01C0012h
0x14000f073  jz      short loc_14000F094
0x14000f075  lea     rax, WPP_RECORDER_INITIALIZED
0x14000f07c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000f083  jz      loc_14000EF18
0x14000f089  mov     r9d, 11h
0x14000f08f  jmp     loc_14000EFFC
0x14000f094  test    r12, r12
0x14000f097  jz      loc_14000F12F
0x14000f09d  mov     rcx, [rbp+40h+FltObject]
0x14000f0a1  test    rcx, rcx
0x14000f0a4  jnz     short loc_14000F0E0
0x14000f0a6  mov     rdx, cs:WofGlobal; Filter
0x14000f0ad  lea     rax, [rbp+40h+NumberInstancesReturned]
0x14000f0b1  lea     r9d, [rcx+1]; InstanceListSize
0x14000f0b5  mov     qword ptr [rsp+140h+DesiredAccess], rax; NumberInstancesReturned
0x14000f0ba  mov     rcx, [rbp+40h+var_C0]; Volume
0x14000f0be  lea     r8, [rbp+40h+FltObject]; InstanceList
0x14000f0c2  mov     [rbp+40h+NumberInstancesReturned], r13d
0x14000f0c6  call    cs:__imp_FltEnumerateInstances
0x14000f0cd  nop     dword ptr [rax+rax+00h]
0x14000f0d2  mov     ebx, eax
0x14000f0d4  test    eax, eax
0x14000f0d6  js      loc_14000EF18
0x14000f0dc  mov     rcx, [rbp+40h+FltObject]; Instance
0x14000f0e0  lea     rdx, [rbp+40h+var_A8]
0x14000f0e4  call    WofGetVolumeContext
0x14000f0e9  mov     ebx, eax
0x14000f0eb  test    eax, eax
0x14000f0ed  jns     short loc_14000F127
0x14000f0ef  lea     rax, WPP_RECORDER_INITIALIZED
0x14000f0f6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000f0fd  jz      short loc_14000F11E
0x14000f0ff  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f106  mov     r9d, 12h
0x14000f10c  mov     dword ptr [rsp+140h+IoStatusBlock], ebx
0x14000f110  mov     [rsp+140h+ObjectAttributes], r14
0x14000f115  mov     rcx, [rcx+40h]
0x14000f119  call    WPP_RECORDER_SF_ZD
0x14000f11e  mov     rdi, [rbp+40h+var_A8]
0x14000f122  jmp     loc_14000EF18
0x14000f127  mov     rax, [rbp+40h+var_A8]
0x14000f12b  mov     [r12], rax
0x14000f12f  mov     rax, [rbp+40h+var_C0]
0x14000f133  mov     [r15], rax
0x14000f136  mov     [rbp+40h+var_C0], r13
0x14000f13a  mov     ebx, r13d
0x14000f13d  jmp     loc_14000EF31
```
