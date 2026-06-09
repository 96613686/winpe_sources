# WskTdiCreateAO

- ea: `0x140062a54`
- end: `0x140062eb3`
- name: `WskTdiCreateAO`
- size: `1119`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, __int16, PHANDLE FileHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x140043aa4`

## callees

- `0x140003670`
- `0x140005b60`
- `0x14003f420`
- `0x140062a54`
- `0x140063fe4`
- `0x140067b0c`
- `0x1400726a0`
- `0x140072800`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140062e7a`
- `ntoskrnl!ZwClose` at `0x140062e7a`
- `ntoskrnl!IoCreateFileEx` at `0x140062d8a`
- `ntoskrnl!IoCreateFileEx` at `0x140062d8a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140062d1e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140062da1`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140062d1e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140062da1`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140062b98`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140062b98`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140062c1d`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140062c5b`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140062db1`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140062c1d`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140062c5b`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140062db1`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140062b76`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140062b76`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x140062b43`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x140062b43`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140062cff`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140062cff`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140062e28`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140062e28`
- `ntoskrnl!ObfDereferenceObject` at `0x140062e62`
- `ntoskrnl!ObfDereferenceObject` at `0x140062e62`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140062dfb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140062dfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062dce`
- `ntoskrnl!ExFreePoolWithTag` at `0x140062dce`

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
0x140062a54  mov     [rsp-8+arg_18], rbx
0x140062a59  push    rbp
0x140062a5a  push    rsi
0x140062a5b  push    rdi
0x140062a5c  push    r12
0x140062a5e  push    r13
0x140062a60  push    r14
0x140062a62  push    r15
0x140062a64  lea     rbp, [rsp-70h]
0x140062a69  sub     rsp, 170h
0x140062a70  mov     rax, cs:__security_cookie
0x140062a77  xor     rax, rsp
0x140062a7a  mov     [rbp+0A0h+var_40], rax
0x140062a7e  mov     rbx, [rbp+0A0h+FileHandle]
0x140062a85  xorps   xmm0, xmm0
0x140062a88  mov     r15, [rbp+0A0h+arg_28]
0x140062a8f  mov     r14, r8
0x140062a92  xor     r8d, r8d
0x140062a95  mov     [rbp+0A0h+var_108], rcx
0x140062a99  mov     rax, rcx
0x140062a9c  mov     [rbp+0A0h+var_D8], rdx
0x140062aa0  xor     ecx, ecx
0x140062aa2  mov     [rbx], r8
0x140062aa5  mov     rsi, rdx
0x140062aa8  mov     [rbx+8], r8
0x140062aac  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.ObjectName], xmm0
0x140062ab0  mov     [rbx+10h], r8
0x140062ab4  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.Length], xmm0
0x140062ab8  mov     [rbp+0A0h+EcpList], r8
0x140062abc  movups  xmmword ptr [rbp+0A0h+ObjectAttributes+1Ch], xmm0
0x140062ac0  mov     [rbp+0A0h+var_118], r8
0x140062ac4  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x140062ac8  mov     word ptr [rbp+0A0h+var_E0], cx
0x140062acc  movups  xmmword ptr [rbp+0A0h+var_100.Size], xmm0
0x140062ad0  mov     [rbp+0A0h+var_120], r8b
0x140062ad4  movups  xmmword ptr [rbp+0A0h+var_100.DeviceObjectHint], xmm0
0x140062ad8  cmp     [rbp+0A0h+arg_20], r8d
0x140062adf  jz      short loc_140062AE6
0x140062ae1  mov     r14d, r8d
0x140062ae4  jmp     short loc_140062AF1
0x140062ae6  mov     r12d, 3
0x140062aec  test    r9d, r9d
0x140062aef  jnz     short loc_140062AF4
0x140062af1  mov     r12d, r8d
0x140062af4  movzx   edi, word ptr [rax+4Ah]
0x140062af8  mov     eax, [r15+10h]
0x140062afc  and     edi, 1
0x140062aff  bts     edi, 8
0x140062b03  test    al, 1
0x140062b05  jz      loc_140062BED
0x140062b0b  cmp     cs:AfdTdxCallbackObject, r8
0x140062b12  mov     [rbp+0A0h+EcpType.Data1], 0D37479C1h
0x140062b19  mov     dword ptr [rbp+0A0h+EcpType.Data2], 4502A067h
0x140062b20  mov     dword ptr [rbp+0A0h+EcpType.Data4], 0E352E8Ch
0x140062b27  mov     dword ptr [rbp+0A0h+EcpType.Data4+4], 0D59134F5h
0x140062b2e  jnz     short loc_140062B3D
0x140062b30  call    AfdTdxInitCallback
0x140062b35  test    eax, eax
0x140062b37  js      loc_140062E8B
0x140062b3d  lea     rdx, [rbp+0A0h+EcpList]; EcpList
0x140062b41  xor     ecx, ecx; Flags
0x140062b43  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x140062b4a  nop     dword ptr [rax+rax+00h]
0x140062b4f  test    eax, eax
0x140062b51  js      loc_140062C67
0x140062b57  xor     r9d, r9d; CleanupCallback
0x140062b5a  lea     rax, [rbp+0A0h+var_118]
0x140062b5e  mov     [rsp+1A0h+EcpContext], rax; EcpContext
0x140062b63  lea     rcx, [rbp+0A0h+EcpType]; EcpType
0x140062b67  xor     r8d, r8d; Flags
0x140062b6a  mov     [rsp+1A0h+PoolTag], 41646641h; PoolTag
0x140062b72  lea     edx, [r9+10h]; SizeOfContext
0x140062b76  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x140062b7d  nop     dword ptr [rax+rax+00h]
0x140062b82  test    eax, eax
0x140062b84  jns     short loc_140062B90
0x140062b86  mov     ebx, 0C000009Ah
0x140062b8b  jmp     loc_140062C19
0x140062b90  mov     rdx, [rbp+0A0h+var_118]; EcpContext
0x140062b94  mov     rcx, [rbp+0A0h+EcpList]; EcpList
0x140062b98  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x140062b9f  nop     dword ptr [rax+rax+00h]
0x140062ba4  mov     rax, [rbp+0A0h+var_118]
0x140062ba8  xor     r8d, r8d
0x140062bab  mov     [rax], r8
0x140062bae  mov     rax, [rbp+0A0h+var_118]
0x140062bb2  mov     [rax+8], r15
0x140062bb6  lea     rax, [r15+50h]
0x140062bba  cmp     rbx, rax
0x140062bbd  jnz     short loc_140062C0E
0x140062bbf  mov     [rbp+0A0h+var_120], 1
0x140062bc3  mov     eax, 28h ; '('
0x140062bc8  mov     dword ptr [rbp+0A0h+var_100+2], r8d
0x140062bcc  mov     [rbp+0A0h+var_100.Size], ax
0x140062bd0  xorps   xmm0, xmm0
0x140062bd3  mov     rax, [rbp+0A0h+EcpList]
0x140062bd7  mov     [rbp+0A0h+var_100.ExtraCreateParameter], rax
0x140062bdb  mov     word ptr [rbp+0A0h+var_100+6], r8w
0x140062be0  movdqu  xmmword ptr [rbp+0A0h+var_100.DeviceObjectHint], xmm0
0x140062be5  mov     [rbp+0A0h+var_E0], 1
0x140062bed  movzx   ecx, word ptr [rsi]; af
0x140062bf0  call    SOCKADDR_SIZE
0x140062bf5  movzx   eax, al
0x140062bf8  add     eax, 6
0x140062bfb  mov     [rbp+0A0h+EcpType.Data1], eax
0x140062bfe  lea     r13d, [rax+19h]
0x140062c02  cmp     r13d, 3Bh ; ';'
0x140062c06  ja      short loc_140062C30
0x140062c08  lea     rsi, [rbp+0A0h+P]
0x140062c0c  jmp     short loc_140062C74
0x140062c0e  cmp     [r15+78h], r8
0x140062c12  jnz     short loc_140062BC3
0x140062c14  mov     ebx, 0C0000184h
0x140062c19  mov     rcx, [rbp+0A0h+EcpList]; EcpList
0x140062c1d  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x140062c24  nop     dword ptr [rax+rax+00h]
0x140062c29  mov     eax, ebx
0x140062c2b  jmp     loc_140062E8B
0x140062c30  mov     edx, r13d
0x140062c33  xor     r9d, r9d
0x140062c36  mov     ecx, 100h
0x140062c3b  mov     r8d, 41646641h
0x140062c41  call    AfdAllocatePoolPriority
0x140062c46  xor     r8d, r8d
0x140062c49  mov     rsi, rax
0x140062c4c  test    rax, rax
0x140062c4f  jnz     short loc_140062C71
0x140062c51  cmp     [rbp+0A0h+var_118], r8
0x140062c55  jz      short loc_140062C67
0x140062c57  mov     rcx, [rbp+0A0h+EcpList]; EcpList
0x140062c5b  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x140062c62  nop     dword ptr [rax+rax+00h]
0x140062c67  mov     eax, 0C000009Ah
0x140062c6c  jmp     loc_140062E8B
0x140062c71  mov     eax, [rbp+0A0h+EcpType.Data1]
0x140062c74  mov     qword ptr [rbp+0A0h+EcpType.Data1], r8
0x140062c78  lea     rcx, [rsi+8]; void *
0x140062c7c  mov     [rsi], r8d
0x140062c7f  lea     rdx, aTransportaddre; "TransportAddress"
0x140062c86  mov     r8d, 11h; Size
0x140062c8c  mov     word ptr [rsi+4], 1000h
0x140062c92  mov     [rsi+6], ax
0x140062c96  call    memmove
0x140062c9b  mov     rdx, [rbp+0A0h+var_D8]
0x140062c9f  mov     dword ptr [rsi+19h], 1
0x140062ca6  movzx   ecx, word ptr [rdx]; af
0x140062ca9  call    SOCKADDR_SIZE
0x140062cae  movzx   r8d, al
0x140062cb2  sub     r8w, 2
0x140062cb7  mov     [rsi+1Dh], r8w
0x140062cbc  movzx   ecx, word ptr [rdx]; af
0x140062cbf  call    SOCKADDR_SIZE
0x140062cc4  movzx   r8d, al; Size
0x140062cc8  lea     rcx, [rsi+1Fh]; void *
0x140062ccc  call    memmove
0x140062cd1  mov     rax, [rbp+0A0h+var_108]
0x140062cd5  xor     ecx, ecx
0x140062cd7  add     rax, 20h ; ' '
0x140062cdb  mov     [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x140062ce2  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], rcx
0x140062ce6  mov     [rbp+0A0h+ObjectAttributes.Attributes], 240h
0x140062ced  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rax
0x140062cf1  mov     [rbp+0A0h+ObjectAttributes.SecurityDescriptor], r14
0x140062cf5  mov     [rbp+0A0h+ObjectAttributes.SecurityQualityOfService], rcx
0x140062cf9  cmp     [rbp+0A0h+var_118], rcx
0x140062cfd  jz      short loc_140062D38
0x140062cff  call    cs:__imp_IoGetTopLevelIrp
0x140062d06  nop     dword ptr [rax+rax+00h]
0x140062d0b  cmp     [rbp+0A0h+var_120], 0
0x140062d0f  mov     ecx, 5
0x140062d14  mov     r14, rax
0x140062d17  jz      short loc_140062D1E
0x140062d19  mov     ecx, 6; Irp
0x140062d1e  call    cs:__imp_IoSetTopLevelIrp
0x140062d25  nop     dword ptr [rax+rax+00h]
0x140062d2a  xor     ecx, ecx
0x140062d2c  cmp     [rbp+0A0h+var_118], rcx
0x140062d30  jz      short loc_140062D3C
0x140062d32  lea     rax, [rbp+0A0h+var_100]
0x140062d36  jmp     short loc_140062D3F
0x140062d38  mov     r14, qword ptr [rbp+0A0h+EcpType.Data1]
0x140062d3c  mov     rax, rcx
0x140062d3f  mov     [rsp+1A0h+DriverContext], rax; DriverContext
0x140062d44  lea     r9, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x140062d48  mov     [rsp+1A0h+Options], edi; Options
0x140062d4c  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x140062d50  mov     [rsp+1A0h+InternalParameters], rcx; InternalParameters
0x140062d55  mov     edx, 2000000h; DesiredAccess
0x140062d5a  mov     [rsp+1A0h+CreateFileType], ecx; CreateFileType
0x140062d5e  mov     rcx, rbx; FileHandle
0x140062d61  mov     [rsp+1A0h+EaLength], r13d; EaLength
0x140062d66  xor     r13d, r13d
0x140062d69  mov     [rsp+1A0h+EaBuffer], rsi; EaBuffer
0x140062d6e  mov     [rsp+1A0h+CreateOptions], r13d; CreateOptions
0x140062d73  mov     [rsp+1A0h+Disposition], 2; Disposition
0x140062d7b  mov     [rsp+1A0h+ShareAccess], r12d; ShareAccess
0x140062d80  mov     dword ptr [rsp+1A0h+EcpContext], r13d; FileAttributes
0x140062d85  mov     qword ptr [rsp+1A0h+PoolTag], r13; AllocationSize
0x140062d8a  call    cs:__imp_IoCreateFileEx
0x140062d91  nop     dword ptr [rax+rax+00h]
0x140062d96  mov     edi, eax
0x140062d98  cmp     [rbp+0A0h+var_118], r13
0x140062d9c  jz      short loc_140062DBD
0x140062d9e  mov     rcx, r14; Irp
0x140062da1  call    cs:__imp_IoSetTopLevelIrp
0x140062da8  nop     dword ptr [rax+rax+00h]
0x140062dad  mov     rcx, [rbp+0A0h+EcpList]; EcpList
0x140062db1  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x140062db8  nop     dword ptr [rax+rax+00h]
0x140062dbd  lea     rax, [rbp+0A0h+P]
0x140062dc1  cmp     rsi, rax
0x140062dc4  jz      short loc_140062DDA
0x140062dc6  mov     edx, 41646641h; Tag
0x140062dcb  mov     rcx, rsi; P
0x140062dce  call    cs:__imp_ExFreePoolWithTag
0x140062dd5  nop     dword ptr [rax+rax+00h]
0x140062dda  test    edi, edi
0x140062ddc  js      short loc_140062E55
0x140062dde  mov     rcx, [rbx]; Handle
0x140062de1  lea     rax, [rbp+0A0h+EcpType]
0x140062de5  mov     [rsp+1A0h+EcpContext], r13; HandleInformation
0x140062dea  xor     r9d, r9d; AccessMode
0x140062ded  xor     r8d, r8d; ObjectType
0x140062df0  mov     qword ptr [rsp+1A0h+PoolTag], rax; Object
0x140062df5  xor     edx, edx; DesiredAccess
0x140062df7  mov     qword ptr [rbp+0A0h+EcpType.Data1], r13
0x140062dfb  call    cs:__imp_ObReferenceObjectByHandle
0x140062e02  nop     dword ptr [rax+rax+00h]
0x140062e07  mov     rdx, qword ptr [rbp+0A0h+EcpType.Data1]
0x140062e0b  mov     edi, eax
0x140062e0d  mov     [rbx+8], rdx
0x140062e11  test    eax, eax
0x140062e13  js      short loc_140062E55
0x140062e15  mov     rcx, [rbp+0A0h+var_108]
0x140062e19  call    AfdTdiValidateTransportFileObject
0x140062e1e  mov     edi, eax
0x140062e20  test    eax, eax
0x140062e22  js      short loc_140062E55
0x140062e24  mov     rcx, [rbx+8]; FileObject
0x140062e28  call    cs:__imp_IoGetRelatedDeviceObject
0x140062e2f  nop     dword ptr [rax+rax+00h]
0x140062e34  movzx   r8d, [rbp+0A0h+arg_30]
0x140062e3c  mov     rdx, r15
0x140062e3f  mov     rcx, rbx
0x140062e42  mov     [rbx+10h], rax
0x140062e46  call    WskTdiSetEventHandlers
0x140062e4b  mov     edi, eax
0x140062e4d  test    eax, eax
0x140062e4f  js      short loc_140062E55
0x140062e51  xor     eax, eax
0x140062e53  jmp     short loc_140062E8B
0x140062e55  mov     rcx, [rbx+8]; Object
0x140062e59  mov     [rbx+10h], r13
0x140062e5d  test    rcx, rcx
0x140062e60  jz      short loc_140062E72
0x140062e62  call    cs:__imp_ObfDereferenceObject
0x140062e69  nop     dword ptr [rax+rax+00h]
0x140062e6e  mov     [rbx+8], r13
0x140062e72  mov     rcx, [rbx]; Handle
0x140062e75  test    rcx, rcx
0x140062e78  jz      short loc_140062E89
0x140062e7a  call    cs:__imp_ZwClose
0x140062e81  nop     dword ptr [rax+rax+00h]
0x140062e86  mov     [rbx], r13
0x140062e89  mov     eax, edi
0x140062e8b  mov     rcx, [rbp+0A0h+var_40]
0x140062e8f  xor     rcx, rsp; StackCookie
0x140062e92  call    __security_check_cookie
0x140062e97  mov     rbx, [rsp+1A0h+arg_18]
0x140062e9f  add     rsp, 170h
0x140062ea6  pop     r15
0x140062ea8  pop     r14
0x140062eaa  pop     r13
0x140062eac  pop     r12
0x140062eae  pop     rdi
0x140062eaf  pop     rsi
0x140062eb0  pop     rbp
0x140062eb1  retn
```
