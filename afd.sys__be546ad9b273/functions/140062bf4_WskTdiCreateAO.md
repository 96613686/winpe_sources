# WskTdiCreateAO

- ea: `0x140062bf4`
- end: `0x140063053`
- name: `WskTdiCreateAO`
- size: `1119`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, __int16, PHANDLE FileHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140043ac4`

## callees

- `0x140003670`
- `0x140005b60`
- `0x14003f440`
- `0x140062bf4`
- `0x140064184`
- `0x140067cac`
- `0x140072840`
- `0x140072980`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14006301a`
- `ntoskrnl!ZwClose` at `0x14006301a`
- `ntoskrnl!IoCreateFileEx` at `0x140062f2a`
- `ntoskrnl!IoCreateFileEx` at `0x140062f2a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140062ebe`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140062f41`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140062ebe`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140062f41`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140062d38`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140062d38`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140062dbd`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140062dfb`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140062f51`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140062dbd`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140062dfb`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140062f51`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140062d16`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140062d16`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x140062ce3`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x140062ce3`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140062e9f`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140062e9f`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140062fc8`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140062fc8`
- `ntoskrnl!ObfDereferenceObject` at `0x140063002`
- `ntoskrnl!ObfDereferenceObject` at `0x140063002`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140062f9b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140062f9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062f6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062f6e`

## pseudocode

```c
__int64 __fastcall WskTdiCreateAO(
        __int64 a1,
        ADDRESS_FAMILY *a2,
        void *a3,
        int a4,
        int a5,
        __int64 a6,
        unsigned __int16 a7,
        PHANDLE FileHandle)
{
  ULONG ShareAccess; // r12d
  ULONG Options; // edi
  __int64 result; // rax
  unsigned int v13; // ebx
  unsigned int v14; // eax
  __int64 v15; // r8
  ULONG EaLength; // r13d
  _BYTE *EaBuffer; // rsi
  __int64 PoolPriority; // rax
  ADDRESS_FAMILY *v19; // rdx
  ADDRESS_FAMILY *v20; // rdx
  UCHAR v21; // al
  const void *v22; // rdx
  PIRP TopLevelIrp; // rax
  __int64 v24; // rcx
  IRP *v25; // r14
  struct _IO_DRIVER_CREATE_CONTEXT *DriverContext; // rax
  NTSTATUS v27; // edi
  void *v28; // rcx
  NTSTATUS v29; // eax
  __int64 v30; // rdx
  void *v31; // rcx
  char v32; // [rsp+80h] [rbp-80h]
  PVOID EcpContext; // [rsp+88h] [rbp-78h] BYREF
  PECP_LIST EcpList; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING *v35; // [rsp+98h] [rbp-68h]
  struct _IO_DRIVER_CREATE_CONTEXT v36; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v37; // [rsp+C0h] [rbp-40h]
  ADDRESS_FAMILY *v38; // [rsp+C8h] [rbp-38h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp+0h] BYREF
  GUID EcpType; // [rsp+110h] [rbp+10h] BYREF
  _BYTE P[64]; // [rsp+120h] [rbp+20h] BYREF

  v35 = (struct _UNICODE_STRING *)a1;
  v38 = a2;
  *FileHandle = 0;
  FileHandle[1] = 0;
  *(_OWORD *)&ObjectAttributes.ObjectName = 0;
  FileHandle[2] = 0;
  *(_OWORD *)&ObjectAttributes.Length = 0;
  EcpList = 0;
  *(_OWORD *)(&ObjectAttributes.Attributes + 1) = 0;
  EcpContext = 0;
  IoStatusBlock = 0;
  LOWORD(v37) = 0;
  memset(&v36, 0, sizeof(v36));
  v32 = 0;
  if ( a5 )
  {
    a3 = 0;
  }
  else
  {
    ShareAccess = 3;
    if ( a4 )
      goto LABEL_5;
  }
  ShareAccess = 0;
LABEL_5:
  Options = *(_WORD *)(a1 + 74) & 1 | 0x100;
  if ( (*(_DWORD *)(a6 + 16) & 1) != 0 )
  {
    EcpType.Data1 = -747341375;
    *(_DWORD *)&EcpType.Data2 = 1157800039;
    *(_DWORD *)EcpType.Data4 = 238366348;
    *(_DWORD *)&EcpType.Data4[4] = -711904011;
    if ( !AfdTdxCallbackObject )
    {
      result = AfdTdxInitCallback();
      if ( (int)result < 0 )
        return result;
    }
    if ( FsRtlAllocateExtraCreateParameterList(0, &EcpList) < 0 )
      return 3221225626LL;
    if ( FsRtlAllocateExtraCreateParameter(&EcpType, 0x10u, 0, 0, 0x41646641u, &EcpContext) < 0 )
    {
      v13 = -1073741670;
LABEL_18:
      FsRtlFreeExtraCreateParameterList(EcpList);
      return v13;
    }
    FsRtlInsertExtraCreateParameter(EcpList, EcpContext);
    *(_QWORD *)EcpContext = 0;
    *((_QWORD *)EcpContext + 1) = a6;
    if ( FileHandle == (PHANDLE)(a6 + 80) )
    {
      v32 = 1;
    }
    else if ( !*(_QWORD *)(a6 + 120) )
    {
      v13 = -1073741436;
      goto LABEL_18;
    }
    *(_DWORD *)(&v36.Size + 1) = 0;
    v36.Size = 40;
    v36.ExtraCreateParameter = EcpList;
    *(&v36.Size + 3) = 0;
    *(_OWORD *)&v36.DeviceObjectHint = 0;
    v37 = 1;
  }
  v14 = SOCKADDR_SIZE(*a2) + 6;
  EcpType.Data1 = v14;
  EaLength = v14 + 25;
  if ( v14 + 25 <= 0x3B )
  {
    EaBuffer = P;
    goto LABEL_24;
  }
  PoolPriority = AfdAllocatePoolPriority(256, EaLength, 1097098817, 0);
  v15 = 0;
  EaBuffer = (_BYTE *)PoolPriority;
  if ( !PoolPriority )
  {
    if ( EcpContext )
      FsRtlFreeExtraCreateParameterList(EcpList);
    return 3221225626LL;
  }
  LOWORD(v14) = EcpType.Data1;
LABEL_24:
  *(_QWORD *)&EcpType.Data1 = v15;
  *(_DWORD *)EaBuffer = v15;
  *((_WORD *)EaBuffer + 2) = 4096;
  *((_WORD *)EaBuffer + 3) = v14;
  memmove(EaBuffer + 8, "TransportAddress", 0x11u);
  v19 = v38;
  *(_DWORD *)(EaBuffer + 25) = 1;
  *(_WORD *)(EaBuffer + 29) = SOCKADDR_SIZE(*v19) - 2;
  v21 = SOCKADDR_SIZE(*v20);
  memmove(EaBuffer + 31, v22, v21);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = v35 + 2;
  ObjectAttributes.SecurityDescriptor = a3;
  ObjectAttributes.SecurityQualityOfService = 0;
  if ( !EcpContext )
  {
    v25 = *(IRP **)&EcpType.Data1;
LABEL_30:
    DriverContext = 0;
    goto LABEL_31;
  }
  TopLevelIrp = IoGetTopLevelIrp();
  v24 = 5;
  v25 = TopLevelIrp;
  if ( v32 )
    v24 = 6;
  IoSetTopLevelIrp((PIRP)v24);
  if ( !EcpContext )
    goto LABEL_30;
  DriverContext = &v36;
LABEL_31:
  v27 = IoCreateFileEx(
          FileHandle,
          0x2000000u,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0,
          ShareAccess,
          2u,
          0,
          EaBuffer,
          EaLength,
          CreateFileTypeNone,
          0,
          Options,
          DriverContext);
  if ( EcpContext )
  {
    IoSetTopLevelIrp(v25);
    FsRtlFreeExtraCreateParameterList(EcpList);
  }
  if ( EaBuffer != P )
    ExFreePoolWithTag(EaBuffer, 0x41646641u);
  if ( v27 < 0 )
    goto LABEL_40;
  v28 = *FileHandle;
  *(_QWORD *)&EcpType.Data1 = 0;
  v29 = ObReferenceObjectByHandle(v28, 0, 0, 0, (PVOID *)&EcpType, 0);
  v30 = *(_QWORD *)&EcpType.Data1;
  v27 = v29;
  FileHandle[1] = *(void **)&EcpType.Data1;
  if ( v29 >= 0 )
  {
    v27 = AfdTdiValidateTransportFileObject(v35, v30);
    if ( v27 >= 0 )
    {
      FileHandle[2] = IoGetRelatedDeviceObject((PFILE_OBJECT)FileHandle[1]);
      v27 = WskTdiSetEventHandlers(FileHandle, a6, a7);
      if ( v27 >= 0 )
        return 0;
    }
  }
LABEL_40:
  v31 = FileHandle[1];
  FileHandle[2] = 0;
  if ( v31 )
  {
    ObfDereferenceObject(v31);
    FileHandle[1] = 0;
  }
  if ( *FileHandle )
  {
    ZwClose(*FileHandle);
    *FileHandle = 0;
  }
  return (unsigned int)v27;
}

```

## disassembly

```asm
0x140062bf4  mov     [rsp-8+arg_18], rbx
0x140062bf9  push    rbp
0x140062bfa  push    rsi
0x140062bfb  push    rdi
0x140062bfc  push    r12
0x140062bfe  push    r13
0x140062c00  push    r14
0x140062c02  push    r15
0x140062c04  lea     rbp, [rsp-70h]
0x140062c09  sub     rsp, 170h
0x140062c10  mov     rax, cs:__security_cookie
0x140062c17  xor     rax, rsp
0x140062c1a  mov     [rbp+0A0h+var_40], rax
0x140062c1e  mov     rbx, [rbp+0A0h+FileHandle]
0x140062c25  xorps   xmm0, xmm0
0x140062c28  mov     r15, [rbp+0A0h+arg_28]
0x140062c2f  mov     r14, r8
0x140062c32  xor     r8d, r8d
0x140062c35  mov     [rbp+0A0h+var_108], rcx
0x140062c39  mov     rax, rcx
0x140062c3c  mov     [rbp+0A0h+var_D8], rdx
0x140062c40  xor     ecx, ecx
0x140062c42  mov     [rbx], r8
0x140062c45  mov     rsi, rdx
0x140062c48  mov     [rbx+8], r8
0x140062c4c  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.ObjectName], xmm0
0x140062c50  mov     [rbx+10h], r8
0x140062c54  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.Length], xmm0
0x140062c58  mov     [rbp+0A0h+EcpList], r8
0x140062c5c  movups  xmmword ptr [rbp+0A0h+ObjectAttributes+1Ch], xmm0
0x140062c60  mov     [rbp+0A0h+var_118], r8
0x140062c64  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x140062c68  mov     word ptr [rbp+0A0h+var_E0], cx
0x140062c6c  movups  xmmword ptr [rbp+0A0h+var_100.Size], xmm0
0x140062c70  mov     [rbp+0A0h+var_120], r8b
0x140062c74  movups  xmmword ptr [rbp+0A0h+var_100.DeviceObjectHint], xmm0
0x140062c78  cmp     [rbp+0A0h+arg_20], r8d
0x140062c7f  jz      short loc_140062C86
0x140062c81  mov     r14d, r8d
0x140062c84  jmp     short loc_140062C91
0x140062c86  mov     r12d, 3
0x140062c8c  test    r9d, r9d
0x140062c8f  jnz     short loc_140062C94
0x140062c91  mov     r12d, r8d
0x140062c94  movzx   edi, word ptr [rax+4Ah]
0x140062c98  mov     eax, [r15+10h]
0x140062c9c  and     edi, 1
0x140062c9f  bts     edi, 8
0x140062ca3  test    al, 1
0x140062ca5  jz      loc_140062D8D
0x140062cab  cmp     cs:AfdTdxCallbackObject, r8
0x140062cb2  mov     [rbp+0A0h+EcpType.Data1], 0D37479C1h
0x140062cb9  mov     dword ptr [rbp+0A0h+EcpType.Data2], 4502A067h
0x140062cc0  mov     dword ptr [rbp+0A0h+EcpType.Data4], 0E352E8Ch
0x140062cc7  mov     dword ptr [rbp+0A0h+EcpType.Data4+4], 0D59134F5h
0x140062cce  jnz     short loc_140062CDD
0x140062cd0  call    AfdTdxInitCallback
0x140062cd5  test    eax, eax
0x140062cd7  js      loc_14006302B
0x140062cdd  lea     rdx, [rbp+0A0h+EcpList]; EcpList
0x140062ce1  xor     ecx, ecx; Flags
0x140062ce3  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x140062cea  nop     dword ptr [rax+rax+00h]
0x140062cef  test    eax, eax
0x140062cf1  js      loc_140062E07
0x140062cf7  xor     r9d, r9d; CleanupCallback
0x140062cfa  lea     rax, [rbp+0A0h+var_118]
0x140062cfe  mov     [rsp+1A0h+EcpContext], rax; EcpContext
0x140062d03  lea     rcx, [rbp+0A0h+EcpType]; EcpType
0x140062d07  xor     r8d, r8d; Flags
0x140062d0a  mov     [rsp+1A0h+PoolTag], 41646641h; PoolTag
0x140062d12  lea     edx, [r9+10h]; SizeOfContext
0x140062d16  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x140062d1d  nop     dword ptr [rax+rax+00h]
0x140062d22  test    eax, eax
0x140062d24  jns     short loc_140062D30
0x140062d26  mov     ebx, 0C000009Ah
0x140062d2b  jmp     loc_140062DB9
0x140062d30  mov     rdx, [rbp+0A0h+var_118]; EcpContext
0x140062d34  mov     rcx, [rbp+0A0h+EcpList]; EcpList
0x140062d38  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x140062d3f  nop     dword ptr [rax+rax+00h]
0x140062d44  mov     rax, [rbp+0A0h+var_118]
0x140062d48  xor     r8d, r8d
0x140062d4b  mov     [rax], r8
0x140062d4e  mov     rax, [rbp+0A0h+var_118]
0x140062d52  mov     [rax+8], r15
0x140062d56  lea     rax, [r15+50h]
0x140062d5a  cmp     rbx, rax
0x140062d5d  jnz     short loc_140062DAE
0x140062d5f  mov     [rbp+0A0h+var_120], 1
0x140062d63  mov     eax, 28h ; '('
0x140062d68  mov     dword ptr [rbp+0A0h+var_100+2], r8d
0x140062d6c  mov     [rbp+0A0h+var_100.Size], ax
0x140062d70  xorps   xmm0, xmm0
0x140062d73  mov     rax, [rbp+0A0h+EcpList]
0x140062d77  mov     [rbp+0A0h+var_100.ExtraCreateParameter], rax
0x140062d7b  mov     word ptr [rbp+0A0h+var_100+6], r8w
0x140062d80  movdqu  xmmword ptr [rbp+0A0h+var_100.DeviceObjectHint], xmm0
0x140062d85  mov     [rbp+0A0h+var_E0], 1
0x140062d8d  movzx   ecx, word ptr [rsi]; af
0x140062d90  call    SOCKADDR_SIZE
0x140062d95  movzx   eax, al
0x140062d98  add     eax, 6
0x140062d9b  mov     [rbp+0A0h+EcpType.Data1], eax
0x140062d9e  lea     r13d, [rax+19h]
0x140062da2  cmp     r13d, 3Bh ; ';'
0x140062da6  ja      short loc_140062DD0
0x140062da8  lea     rsi, [rbp+0A0h+P]
0x140062dac  jmp     short loc_140062E14
0x140062dae  cmp     [r15+78h], r8
0x140062db2  jnz     short loc_140062D63
0x140062db4  mov     ebx, 0C0000184h
0x140062db9  mov     rcx, [rbp+0A0h+EcpList]; EcpList
0x140062dbd  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x140062dc4  nop     dword ptr [rax+rax+00h]
0x140062dc9  mov     eax, ebx
0x140062dcb  jmp     loc_14006302B
0x140062dd0  mov     edx, r13d
0x140062dd3  xor     r9d, r9d
0x140062dd6  mov     ecx, 100h
0x140062ddb  mov     r8d, 41646641h
0x140062de1  call    AfdAllocatePoolPriority
0x140062de6  xor     r8d, r8d
0x140062de9  mov     rsi, rax
0x140062dec  test    rax, rax
0x140062def  jnz     short loc_140062E11
0x140062df1  cmp     [rbp+0A0h+var_118], r8
0x140062df5  jz      short loc_140062E07
0x140062df7  mov     rcx, [rbp+0A0h+EcpList]; EcpList
0x140062dfb  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x140062e02  nop     dword ptr [rax+rax+00h]
0x140062e07  mov     eax, 0C000009Ah
0x140062e0c  jmp     loc_14006302B
0x140062e11  mov     eax, [rbp+0A0h+EcpType.Data1]
0x140062e14  mov     qword ptr [rbp+0A0h+EcpType.Data1], r8
0x140062e18  lea     rcx, [rsi+8]; void *
0x140062e1c  mov     [rsi], r8d
0x140062e1f  lea     rdx, aTransportaddre; "TransportAddress"
0x140062e26  mov     r8d, 11h; Size
0x140062e2c  mov     word ptr [rsi+4], 1000h
0x140062e32  mov     [rsi+6], ax
0x140062e36  call    memmove
0x140062e3b  mov     rdx, [rbp+0A0h+var_D8]
0x140062e3f  mov     dword ptr [rsi+19h], 1
0x140062e46  movzx   ecx, word ptr [rdx]; af
0x140062e49  call    SOCKADDR_SIZE
0x140062e4e  movzx   r8d, al
0x140062e52  sub     r8w, 2
0x140062e57  mov     [rsi+1Dh], r8w
0x140062e5c  movzx   ecx, word ptr [rdx]; af
0x140062e5f  call    SOCKADDR_SIZE
0x140062e64  movzx   r8d, al; Size
0x140062e68  lea     rcx, [rsi+1Fh]; void *
0x140062e6c  call    memmove
0x140062e71  mov     rax, [rbp+0A0h+var_108]
0x140062e75  xor     ecx, ecx
0x140062e77  add     rax, 20h ; ' '
0x140062e7b  mov     [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x140062e82  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], rcx
0x140062e86  mov     [rbp+0A0h+ObjectAttributes.Attributes], 240h
0x140062e8d  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rax
0x140062e91  mov     [rbp+0A0h+ObjectAttributes.SecurityDescriptor], r14
0x140062e95  mov     [rbp+0A0h+ObjectAttributes.SecurityQualityOfService], rcx
0x140062e99  cmp     [rbp+0A0h+var_118], rcx
0x140062e9d  jz      short loc_140062ED8
0x140062e9f  call    cs:__imp_IoGetTopLevelIrp
0x140062ea6  nop     dword ptr [rax+rax+00h]
0x140062eab  cmp     [rbp+0A0h+var_120], 0
0x140062eaf  mov     ecx, 5
0x140062eb4  mov     r14, rax
0x140062eb7  jz      short loc_140062EBE
0x140062eb9  mov     ecx, 6; Irp
0x140062ebe  call    cs:__imp_IoSetTopLevelIrp
0x140062ec5  nop     dword ptr [rax+rax+00h]
0x140062eca  xor     ecx, ecx
0x140062ecc  cmp     [rbp+0A0h+var_118], rcx
0x140062ed0  jz      short loc_140062EDC
0x140062ed2  lea     rax, [rbp+0A0h+var_100]
0x140062ed6  jmp     short loc_140062EDF
0x140062ed8  mov     r14, qword ptr [rbp+0A0h+EcpType.Data1]
0x140062edc  mov     rax, rcx
0x140062edf  mov     [rsp+1A0h+DriverContext], rax; DriverContext
0x140062ee4  lea     r9, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x140062ee8  mov     [rsp+1A0h+Options], edi; Options
0x140062eec  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x140062ef0  mov     [rsp+1A0h+InternalParameters], rcx; InternalParameters
0x140062ef5  mov     edx, 2000000h; DesiredAccess
0x140062efa  mov     [rsp+1A0h+CreateFileType], ecx; CreateFileType
0x140062efe  mov     rcx, rbx; FileHandle
0x140062f01  mov     [rsp+1A0h+EaLength], r13d; EaLength
0x140062f06  xor     r13d, r13d
0x140062f09  mov     [rsp+1A0h+EaBuffer], rsi; EaBuffer
0x140062f0e  mov     [rsp+1A0h+CreateOptions], r13d; CreateOptions
0x140062f13  mov     [rsp+1A0h+Disposition], 2; Disposition
0x140062f1b  mov     [rsp+1A0h+ShareAccess], r12d; ShareAccess
0x140062f20  mov     dword ptr [rsp+1A0h+EcpContext], r13d; FileAttributes
0x140062f25  mov     qword ptr [rsp+1A0h+PoolTag], r13; AllocationSize
0x140062f2a  call    cs:__imp_IoCreateFileEx
0x140062f31  nop     dword ptr [rax+rax+00h]
0x140062f36  mov     edi, eax
0x140062f38  cmp     [rbp+0A0h+var_118], r13
0x140062f3c  jz      short loc_140062F5D
0x140062f3e  mov     rcx, r14; Irp
0x140062f41  call    cs:__imp_IoSetTopLevelIrp
0x140062f48  nop     dword ptr [rax+rax+00h]
0x140062f4d  mov     rcx, [rbp+0A0h+EcpList]; EcpList
0x140062f51  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x140062f58  nop     dword ptr [rax+rax+00h]
0x140062f5d  lea     rax, [rbp+0A0h+P]
0x140062f61  cmp     rsi, rax
0x140062f64  jz      short loc_140062F7A
0x140062f66  mov     edx, 41646641h; Tag
0x140062f6b  mov     rcx, rsi; P
0x140062f6e  call    cs:__imp_ExFreePoolWithTag
0x140062f75  nop     dword ptr [rax+rax+00h]
0x140062f7a  test    edi, edi
0x140062f7c  js      short loc_140062FF5
0x140062f7e  mov     rcx, [rbx]; Handle
0x140062f81  lea     rax, [rbp+0A0h+EcpType]
0x140062f85  mov     [rsp+1A0h+EcpContext], r13; HandleInformation
0x140062f8a  xor     r9d, r9d; AccessMode
0x140062f8d  xor     r8d, r8d; ObjectType
0x140062f90  mov     qword ptr [rsp+1A0h+PoolTag], rax; Object
0x140062f95  xor     edx, edx; DesiredAccess
0x140062f97  mov     qword ptr [rbp+0A0h+EcpType.Data1], r13
0x140062f9b  call    cs:__imp_ObReferenceObjectByHandle
0x140062fa2  nop     dword ptr [rax+rax+00h]
0x140062fa7  mov     rdx, qword ptr [rbp+0A0h+EcpType.Data1]
0x140062fab  mov     edi, eax
0x140062fad  mov     [rbx+8], rdx
0x140062fb1  test    eax, eax
0x140062fb3  js      short loc_140062FF5
0x140062fb5  mov     rcx, [rbp+0A0h+var_108]
0x140062fb9  call    AfdTdiValidateTransportFileObject
0x140062fbe  mov     edi, eax
0x140062fc0  test    eax, eax
0x140062fc2  js      short loc_140062FF5
0x140062fc4  mov     rcx, [rbx+8]; FileObject
0x140062fc8  call    cs:__imp_IoGetRelatedDeviceObject
0x140062fcf  nop     dword ptr [rax+rax+00h]
0x140062fd4  movzx   r8d, [rbp+0A0h+arg_30]
0x140062fdc  mov     rdx, r15
0x140062fdf  mov     rcx, rbx
0x140062fe2  mov     [rbx+10h], rax
0x140062fe6  call    WskTdiSetEventHandlers
0x140062feb  mov     edi, eax
0x140062fed  test    eax, eax
0x140062fef  js      short loc_140062FF5
0x140062ff1  xor     eax, eax
0x140062ff3  jmp     short loc_14006302B
0x140062ff5  mov     rcx, [rbx+8]; Object
0x140062ff9  mov     [rbx+10h], r13
0x140062ffd  test    rcx, rcx
0x140063000  jz      short loc_140063012
0x140063002  call    cs:__imp_ObfDereferenceObject
0x140063009  nop     dword ptr [rax+rax+00h]
0x14006300e  mov     [rbx+8], r13
0x140063012  mov     rcx, [rbx]; Handle
0x140063015  test    rcx, rcx
0x140063018  jz      short loc_140063029
0x14006301a  call    cs:__imp_ZwClose
0x140063021  nop     dword ptr [rax+rax+00h]
0x140063026  mov     [rbx], r13
0x140063029  mov     eax, edi
0x14006302b  mov     rcx, [rbp+0A0h+var_40]
0x14006302f  xor     rcx, rsp; StackCookie
0x140063032  call    __security_check_cookie
0x140063037  mov     rbx, [rsp+1A0h+arg_18]
0x14006303f  add     rsp, 170h
0x140063046  pop     r15
0x140063048  pop     r14
0x14006304a  pop     r13
0x14006304c  pop     r12
0x14006304e  pop     rdi
0x14006304f  pop     rsi
0x140063050  pop     rbp
0x140063051  retn
```
