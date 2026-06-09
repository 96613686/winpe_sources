# AfdCreateConnection

- ea: `0x1400391b8`
- end: `0x140039675`
- name: `AfdCreateConnection`
- size: `1213`
- prototype: `__int64 __fastcall(__int64, void *, void *, unsigned __int8, unsigned int, int, struct _KPROCESS *Process, __int64 *)`
- caller_count: `7`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400044fc`
- `0x14001a8a0`
- `0x140037ea0`
- `0x1400398d0`
- `0x14003ae50`
- `0x1400476c0`
- `0x140059ab0`

## callees

- `0x140015880`
- `0x14001c708`
- `0x14002c770`
- `0x1400391b8`
- `0x14004fc44`
- `0x140067cac`
- `0x140072840`
- `0x140093008`
- `0x1400931d0`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140039225`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140039225`
- `ntoskrnl!PsReturnPoolQuota` at `0x140039277`
- `ntoskrnl!PsReturnPoolQuota` at `0x140039277`
- `ntoskrnl!IoCreateFile` at `0x140039424`
- `ntoskrnl!IoCreateFile` at `0x140039424`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x14003951e`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x14003953f`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x14003951e`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x14003953f`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400394ce`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140039530`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400394ce`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140039530`
- `ntoskrnl!ObfReferenceObject` at `0x14003928d`
- `ntoskrnl!ObfReferenceObject` at `0x14003928d`
- `ntoskrnl!ObfDereferenceObject` at `0x140039553`
- `ntoskrnl!ObfDereferenceObject` at `0x140039562`
- `ntoskrnl!ObfDereferenceObject` at `0x140039571`
- `ntoskrnl!ObfDereferenceObject` at `0x1400395aa`
- `ntoskrnl!ObfDereferenceObject` at `0x1400395b9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400395c8`
- `ntoskrnl!ObfDereferenceObject` at `0x140039553`
- `ntoskrnl!ObfDereferenceObject` at `0x140039562`
- `ntoskrnl!ObfDereferenceObject` at `0x140039571`
- `ntoskrnl!ObfDereferenceObject` at `0x1400395aa`
- `ntoskrnl!ObfDereferenceObject` at `0x1400395b9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400395c8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140039462`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140039504`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140039462`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140039504`

## pseudocode

```c
__int64 __fastcall AfdCreateConnection(
        __int64 a1,
        void *a2,
        void *a3,
        unsigned __int8 a4,
        unsigned int a5,
        int a6,
        struct _KPROCESS *Process,
        __int64 *a8)
{
  ULONG Options; // r14d
  NTSTATUS v12; // ebx
  __int64 Connection; // rbx
  int v15; // eax
  int v16; // ecx
  PVOID v17; // r12
  ACCESS_MASK v18; // edx
  NTSTATUS Status; // edi
  void *v20; // rcx
  PVOID v21; // r8
  signed __int64 v22; // rcx
  bool v23; // cc
  signed __int64 v24; // rcx
  bool v25; // zf
  __int64 v26; // rdx
  struct _FILE_OBJECT *v27; // rdi
  PDEVICE_OBJECT DeviceAttachmentBaseRef; // rsi
  struct _DEVICE_OBJECT *RelatedDeviceObject; // rax
  PDEVICE_OBJECT v30; // rcx
  signed __int64 v31; // rax
  signed __int64 v32; // rax
  struct _FILE_OBJECT *v33; // rcx
  signed __int64 v34; // rax
  signed __int64 v35; // rax
  PVOID Object; // [rsp+70h] [rbp-79h] BYREF
  __int64 *v37; // [rsp+78h] [rbp-71h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-69h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-39h] BYREF
  int EaBuffer; // [rsp+C0h] [rbp-29h] BYREF
  int v41; // [rsp+C4h] [rbp-25h]
  char v42[18]; // [rsp+C8h] [rbp-21h] BYREF
  __int64 v43; // [rsp+DAh] [rbp-Fh]

  v37 = a8;
  Options = 256;
  Object = a2;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  v12 = PsChargeProcessPoolQuota(Process, (POOL_TYPE)512, 0x100u);
  if ( v12 < 0 )
  {
    if ( (BYTE8(xmmword_1400875E0) & 4) != 0 )
      WPP_SF_(1282, 11, WPP_5db1fecb84b833618be3860a3784a309_Traceguids);
    return (unsigned int)v12;
  }
  Connection = AfdAllocateConnection(a5);
  if ( !Connection )
  {
    PsReturnPoolQuota(Process, (POOL_TYPE)512, 0x100u);
    return 3221225626LL;
  }
  ObfReferenceObject(Process);
  v15 = *(_DWORD *)(Connection + 4);
  *(_QWORD *)(Connection + 32) = Process;
  *(_DWORD *)(Connection + 4) = v15
                              ^ ((unsigned __int8)v15
                               ^ a4)
                              & 1
                              ^ (v15
                               ^ ((unsigned __int8)v15
                                ^ a4)
                               & 1
                               ^ (a5 << 17))
                              & 0x20000;
  if ( !a4 || a5 )
  {
    *(_QWORD *)(Connection + 88) = 0;
    *(_QWORD *)(Connection + 64) = Connection + 56;
    *(_QWORD *)(Connection + 56) = Connection + 56;
    *(_QWORD *)(Connection + 112) = Connection + 104;
    *(_QWORD *)(Connection + 104) = Connection + 104;
    *(_QWORD *)(Connection + 80) = Connection + 72;
    *(_QWORD *)(Connection + 72) = Connection + 72;
    *(_QWORD *)(Connection + 96) = 0;
    *(_DWORD *)(Connection + 136) = 0;
    *(_QWORD *)(Connection + 120) = 0;
  }
  else
  {
    *(_WORD *)(Connection + 104) = 1;
  }
  v16 = AfdTcpReceiveWindowMax;
  if ( AfdTcpReceiveWindowMax && a5 && *(_DWORD *)(*(_QWORD *)(a1 + 272) + 24LL) == 6 )
  {
    if ( AfdReceiveWindowSize < (unsigned int)AfdTcpReceiveWindowMax )
      v16 = AfdReceiveWindowSize;
    *(_DWORD *)(Connection + 144) = v16;
  }
  else
  {
    *(_DWORD *)(Connection + 144) = AfdReceiveWindowSize;
  }
  *(_DWORD *)(Connection + 148) = AfdSendWindowSize;
  if ( a5 )
    goto LABEL_41;
  *(_DWORD *)(Connection + 4) |= 0x200000u;
  v25 = (*(_DWORD *)(a1 + 16) & 0x10000) == 0;
  v17 = Object;
  strcpy(v42, "ConnectionContext");
  EaBuffer = 0;
  v41 = 528640;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v43 = Connection;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)((char *)Object + 32);
  if ( !v25 || (*(_DWORD *)(a1 + 8) & 0x8000000) != 0 )
  {
    v18 = 0x2000000;
    Options = 257;
  }
  else
  {
    v18 = -1072693248;
  }
  Status = IoCreateFile(
             (PHANDLE)(Connection + 168),
             v18,
             &ObjectAttributes,
             &IoStatusBlock,
             0,
             0,
             0,
             2u,
             0,
             &EaBuffer,
             HIWORD(v41) + 9 + BYTE1(v41),
             CreateFileTypeNone,
             0,
             Options);
  if ( Status < 0 || (Status = IoStatusBlock.Status, IoStatusBlock.Status < 0) )
  {
    v34 = _InterlockedExchangeAdd64((volatile signed __int64 *)(Connection + 48), 0xFFFFFFFFFFFFFFFFuLL);
    v23 = v34 <= 1;
    v35 = v34 - 1;
    if ( v23 )
    {
      v25 = v35 == 0;
      goto LABEL_44;
    }
    return (unsigned int)Status;
  }
  v20 = *(void **)(Connection + 168);
  Object = 0;
  ObReferenceObjectByHandle(v20, 0, 0, 0, &Object, 0);
  v21 = Object;
  *(_QWORD *)(Connection + 16) = Object;
  if ( (xmmword_1400875E0 & 4) != 0 )
    WPP_SF_qq(1026, 12, WPP_5db1fecb84b833618be3860a3784a309_Traceguids, Connection, v21);
  Status = AfdTdiValidateTransportFileObject(v17, *(_QWORD *)(Connection + 16));
  if ( Status < 0 )
  {
LABEL_28:
    v22 = _InterlockedExchangeAdd64((volatile signed __int64 *)(Connection + 48), 0xFFFFFFFFFFFFFFFFuLL);
    v23 = v22 <= 1;
    v24 = v22 - 1;
    if ( v23 )
    {
      v25 = v24 == 0;
LABEL_44:
      if ( !v25 )
        __fastfail(0xEu);
      AfdCloseConnection(Connection);
      return (unsigned int)Status;
    }
    return (unsigned int)Status;
  }
  *(_QWORD *)(Connection + 24) = IoGetRelatedDeviceObject(*(PFILE_OBJECT *)(Connection + 16));
  if ( !a3 )
  {
LABEL_39:
    if ( a6 )
    {
      LOBYTE(v26) = 1;
      Status = AfdSetInLineMode(Connection, v26);
      if ( Status < 0 )
        goto LABEL_28;
    }
LABEL_41:
    *v37 = Connection;
    return 0;
  }
  Object = 0;
  Status = ObReferenceObjectByHandle(a3, 0, 0, 0, &Object, 0);
  if ( Status < 0 )
    goto LABEL_28;
  v27 = (struct _FILE_OBJECT *)Object;
  DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(*(PDEVICE_OBJECT *)(Connection + 24));
  RelatedDeviceObject = IoGetRelatedDeviceObject(v27);
  v30 = IoGetDeviceAttachmentBaseRef(RelatedDeviceObject);
  if ( DeviceAttachmentBaseRef == v30 )
  {
    ObfDereferenceObject(v30);
    ObfDereferenceObject(DeviceAttachmentBaseRef);
    ObfDereferenceObject(v27);
    v33 = *(struct _FILE_OBJECT **)(Connection + 16);
    Object = a3;
    Status = AfdIssueDeviceControl(v33, &Object, 8u, 0, 0, 1);
    if ( Status < 0 )
      goto LABEL_28;
    goto LABEL_39;
  }
  ObfDereferenceObject(v30);
  ObfDereferenceObject(DeviceAttachmentBaseRef);
  ObfDereferenceObject(v27);
  v31 = _InterlockedExchangeAdd64((volatile signed __int64 *)(Connection + 48), 0xFFFFFFFFFFFFFFFFuLL);
  v23 = v31 <= 1;
  v32 = v31 - 1;
  if ( v23 )
  {
    if ( v32 )
      __fastfail(0xEu);
    AfdCloseConnection(Connection);
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1400391b8  mov     [rsp-8+arg_0], rbx
0x1400391bd  push    rbp
0x1400391be  push    rsi
0x1400391bf  push    rdi
0x1400391c0  push    r12
0x1400391c2  push    r13
0x1400391c4  push    r14
0x1400391c6  push    r15
0x1400391c8  lea     rbp, [rsp-7]
0x1400391cd  sub     rsp, 0F0h
0x1400391d4  mov     rax, cs:__security_cookie
0x1400391db  xor     rax, rsp
0x1400391de  mov     [rbp+37h+var_38], rax
0x1400391e2  mov     rax, [rbp+37h+arg_38]
0x1400391e6  xorps   xmm0, xmm0
0x1400391e9  mov     rsi, [rbp+37h+Process]
0x1400391ed  mov     r13, r8
0x1400391f0  mov     edi, [rbp+37h+arg_20]
0x1400391f3  mov     r15, rcx
0x1400391f6  mov     [rbp+37h+var_A8], rax
0x1400391fa  mov     r14d, 100h
0x140039200  mov     [rbp+37h+Object], rdx
0x140039204  xor     eax, eax
0x140039206  movups  xmmword ptr [rbp+37h+ObjectAttributes.ObjectName], xmm0
0x14003920a  mov     r8d, r14d; Amount
0x14003920d  movzx   r12d, r9b
0x140039211  mov     edx, 200h; PoolType
0x140039216  mov     rcx, rsi; Process
0x140039219  movups  xmmword ptr [rbp+37h+IoStatusBlock], xmm0
0x14003921d  movups  xmmword ptr [rbp+37h+ObjectAttributes.Length], xmm0
0x140039221  movups  xmmword ptr [rbp+37h+ObjectAttributes+1Ch], xmm0
0x140039225  call    cs:__imp_PsChargeProcessPoolQuota
0x14003922c  nop     dword ptr [rax+rax+00h]
0x140039231  mov     ebx, eax
0x140039233  test    eax, eax
0x140039235  jns     short loc_14003925D
0x140039237  test    byte ptr cs:xmmword_1400875E0+8, 4
0x14003923e  jz      short loc_140039256
0x140039240  mov     edx, 0Bh
0x140039245  lea     r8, WPP_5db1fecb84b833618be3860a3784a309_Traceguids
0x14003924c  mov     ecx, 502h
0x140039251  call    WPP_SF_
0x140039256  mov     eax, ebx
0x140039258  jmp     loc_140039623
0x14003925d  mov     ecx, edi
0x14003925f  call    AfdAllocateConnection
0x140039264  mov     rbx, rax
0x140039267  mov     rcx, rsi; Object
0x14003926a  test    rax, rax
0x14003926d  jnz     short loc_14003928D
0x14003926f  mov     r8, r14; Amount
0x140039272  mov     edx, 200h; PoolType
0x140039277  call    cs:__imp_PsReturnPoolQuota
0x14003927e  nop     dword ptr [rax+rax+00h]
0x140039283  mov     eax, 0C000009Ah
0x140039288  jmp     loc_140039623
0x14003928d  call    cs:__imp_ObfReferenceObject
0x140039294  nop     dword ptr [rax+rax+00h]
0x140039299  mov     eax, [rbx+4]
0x14003929c  mov     ecx, r12d
0x14003929f  xor     ecx, eax
0x1400392a1  mov     [rbx+20h], rsi
0x1400392a5  and     ecx, 1
0x1400392a8  xor     edx, edx
0x1400392aa  xor     ecx, eax
0x1400392ac  mov     eax, edi
0x1400392ae  shl     eax, 11h
0x1400392b1  xor     eax, ecx
0x1400392b3  and     eax, 20000h
0x1400392b8  xor     eax, ecx
0x1400392ba  mov     [rbx+4], eax
0x1400392bd  test    r12b, r12b
0x1400392c0  jz      short loc_1400392CE
0x1400392c2  test    edi, edi
0x1400392c4  jnz     short loc_1400392CE
0x1400392c6  mov     word ptr [rbx+68h], 1
0x1400392cc  jmp     short loc_140039301
0x1400392ce  lea     rax, [rbx+38h]
0x1400392d2  mov     [rbx+58h], rdx
0x1400392d6  mov     [rax+8], rax
0x1400392da  mov     [rax], rax
0x1400392dd  lea     rax, [rbx+68h]
0x1400392e1  mov     [rax+8], rax
0x1400392e5  mov     [rax], rax
0x1400392e8  lea     rax, [rbx+48h]
0x1400392ec  mov     [rax+8], rax
0x1400392f0  mov     [rax], rax
0x1400392f3  mov     [rbx+60h], rdx
0x1400392f7  mov     [rbx+88h], edx
0x1400392fd  mov     [rbx+78h], rdx
0x140039301  mov     ecx, cs:AfdTcpReceiveWindowMax
0x140039307  test    ecx, ecx
0x140039309  jz      short loc_140039331
0x14003930b  test    edi, edi
0x14003930d  jz      short loc_140039331
0x14003930f  mov     rax, [r15+110h]
0x140039316  cmp     dword ptr [rax+18h], 6
0x14003931a  jnz     short loc_140039331
0x14003931c  cmp     cs:AfdReceiveWindowSize, ecx
0x140039322  cmovb   ecx, cs:AfdReceiveWindowSize
0x140039329  mov     [rbx+90h], ecx
0x14003932f  jmp     short loc_14003933D
0x140039331  mov     eax, cs:AfdReceiveWindowSize
0x140039337  mov     [rbx+90h], eax
0x14003933d  mov     eax, cs:AfdSendWindowSize
0x140039343  mov     [rbx+94h], eax
0x140039349  test    edi, edi
0x14003934b  jnz     loc_14003961A
0x140039351  bts     dword ptr [rbx+4], 15h
0x140039356  test    dword ptr [r15+10h], 10000h
0x14003935e  movups  xmm0, xmmword ptr cs:aConnectioncont; "ConnectionContext"
0x140039365  movzx   eax, word ptr cs:aConnectioncont+10h; "t"
0x14003936c  mov     r12, [rbp+37h+Object]
0x140039370  movups  xmmword ptr [rbp+37h+var_58], xmm0
0x140039374  mov     word ptr [rbp+37h+var_58+10h], ax
0x140039378  xorps   xmm0, xmm0
0x14003937b  mov     [rbp+37h+var_60], edx
0x14003937e  lea     rax, [r12+20h]
0x140039383  mov     [rbp+37h+var_5C], 81100h
0x14003938a  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x14003938f  mov     [rbp+37h+var_46], rbx
0x140039393  mov     [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x14003939a  mov     [rbp+37h+ObjectAttributes.RootDirectory], rdx
0x14003939e  mov     [rbp+37h+ObjectAttributes.Attributes], 240h
0x1400393a5  mov     [rbp+37h+ObjectAttributes.ObjectName], rax
0x1400393a9  jnz     short loc_1400393BC
0x1400393ab  mov     eax, [r15+8]
0x1400393af  bt      eax, 1Bh
0x1400393b3  jb      short loc_1400393BC
0x1400393b5  mov     edx, 0C0100000h
0x1400393ba  jmp     short loc_1400393C7
0x1400393bc  mov     edx, 2000000h; DesiredAccess
0x1400393c1  mov     r14d, 101h
0x1400393c7  movzx   ecx, word ptr [rbp+37h+var_5C+2]
0x1400393cb  lea     rax, [rbp+37h+var_60]
0x1400393cf  movzx   r8d, byte ptr [rbp+37h+var_5C+1]
0x1400393d4  lea     rsi, [rbx+0A8h]
0x1400393db  mov     [rsp+120h+Options], r14d; Options
0x1400393e0  lea     r9, [rbp+37h+IoStatusBlock]; IoStatusBlock
0x1400393e4  xor     r14d, r14d
0x1400393e7  add     ecx, 9
0x1400393ea  mov     [rsp+120h+InternalParameters], r14; InternalParameters
0x1400393ef  add     r8d, ecx
0x1400393f2  mov     [rsp+120h+CreateFileType], r14d; CreateFileType
0x1400393f7  mov     rcx, rsi; FileHandle
0x1400393fa  mov     [rsp+120h+EaLength], r8d; EaLength
0x1400393ff  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x140039403  mov     [rsp+120h+EaBuffer], rax; EaBuffer
0x140039408  mov     [rsp+120h+CreateOptions], r14d; CreateOptions
0x14003940d  mov     [rsp+120h+Disposition], 2; Disposition
0x140039415  mov     [rsp+120h+ShareAccess], r14d; ShareAccess
0x14003941a  mov     [rsp+120h+FileAttributes], r14d; FileAttributes
0x14003941f  mov     [rsp+120h+AllocationSize], r14; AllocationSize
0x140039424  call    cs:__imp_IoCreateFile
0x14003942b  nop     dword ptr [rax+rax+00h]
0x140039430  mov     edi, eax
0x140039432  test    eax, eax
0x140039434  js      loc_14003964B
0x14003943a  mov     edi, dword ptr [rbp+37h+IoStatusBlock]
0x14003943d  test    edi, edi
0x14003943f  js      loc_14003964B
0x140039445  mov     rcx, [rsi]; Handle
0x140039448  lea     rax, [rbp+37h+Object]
0x14003944c  mov     qword ptr [rsp+120h+FileAttributes], r14; HandleInformation
0x140039451  xor     r9d, r9d; AccessMode
0x140039454  xor     r8d, r8d; ObjectType
0x140039457  mov     [rsp+120h+AllocationSize], rax; Object
0x14003945c  xor     edx, edx; DesiredAccess
0x14003945e  mov     [rbp+37h+Object], r14
0x140039462  call    cs:__imp_ObReferenceObjectByHandle
0x140039469  nop     dword ptr [rax+rax+00h]
0x14003946e  mov     r8, [rbp+37h+Object]
0x140039472  mov     [rbx+10h], r8
0x140039476  test    byte ptr cs:xmmword_1400875E0, 4
0x14003947d  jz      short loc_14003949C
0x14003947f  mov     [rsp+120h+AllocationSize], r8
0x140039484  lea     edx, [r14+0Ch]
0x140039488  lea     r8, WPP_5db1fecb84b833618be3860a3784a309_Traceguids
0x14003948f  mov     ecx, 402h
0x140039494  mov     r9, rbx
0x140039497  call    WPP_SF_qq
0x14003949c  mov     rdx, [rbx+10h]
0x1400394a0  mov     rcx, r12
0x1400394a3  call    AfdTdiValidateTransportFileObject
0x1400394a8  mov     edi, eax
0x1400394aa  test    eax, eax
0x1400394ac  jns     short loc_1400394CA
0x1400394ae  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1400394b2  lock xadd [rbx+30h], rcx
0x1400394b8  sub     rcx, 1
0x1400394bc  jg      loc_140039671
0x1400394c2  test    rcx, rcx
0x1400394c5  jmp     loc_14003965E
0x1400394ca  mov     rcx, [rbx+10h]; FileObject
0x1400394ce  call    cs:__imp_IoGetRelatedDeviceObject
0x1400394d5  nop     dword ptr [rax+rax+00h]
0x1400394da  mov     [rbx+18h], rax
0x1400394de  test    r13, r13
0x1400394e1  jz      loc_140039600
0x1400394e7  lea     rax, [rbp+37h+Object]
0x1400394eb  mov     qword ptr [rsp+120h+FileAttributes], r14; HandleInformation
0x1400394f0  xor     r9d, r9d; AccessMode
0x1400394f3  mov     [rsp+120h+AllocationSize], rax; Object
0x1400394f8  xor     r8d, r8d; ObjectType
0x1400394fb  mov     [rbp+37h+Object], r14
0x1400394ff  xor     edx, edx; DesiredAccess
0x140039501  mov     rcx, r13; Handle
0x140039504  call    cs:__imp_ObReferenceObjectByHandle
0x14003950b  nop     dword ptr [rax+rax+00h]
0x140039510  mov     edi, eax
0x140039512  test    eax, eax
0x140039514  js      short loc_1400394AE
0x140039516  mov     rcx, [rbx+18h]; DeviceObject
0x14003951a  mov     rdi, [rbp+37h+Object]
0x14003951e  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x140039525  nop     dword ptr [rax+rax+00h]
0x14003952a  mov     rcx, rdi; FileObject
0x14003952d  mov     rsi, rax
0x140039530  call    cs:__imp_IoGetRelatedDeviceObject
0x140039537  nop     dword ptr [rax+rax+00h]
0x14003953c  mov     rcx, rax; DeviceObject
0x14003953f  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x140039546  nop     dword ptr [rax+rax+00h]
0x14003954b  mov     rcx, rax; Object
0x14003954e  cmp     rsi, rax
0x140039551  jz      short loc_1400395AA
0x140039553  call    cs:__imp_ObfDereferenceObject
0x14003955a  nop     dword ptr [rax+rax+00h]
0x14003955f  mov     rcx, rsi; Object
0x140039562  call    cs:__imp_ObfDereferenceObject
0x140039569  nop     dword ptr [rax+rax+00h]
0x14003956e  mov     rcx, rdi; Object
0x140039571  call    cs:__imp_ObfDereferenceObject
0x140039578  nop     dword ptr [rax+rax+00h]
0x14003957d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140039581  lock xadd [rbx+30h], rax
0x140039587  sub     rax, 1
0x14003958b  jg      short loc_1400395A3
0x14003958d  test    rax, rax
0x140039590  jz      short loc_14003959B
0x140039592  mov     ecx, 0Eh
0x140039597  int     29h; Win8: RtlFailFast(ecx)
0x140039599  jmp     short loc_1400395A3
0x14003959b  mov     rcx, rbx
0x14003959e  call    AfdCloseConnection
0x1400395a3  mov     eax, 0C000000Dh
0x1400395a8  jmp     short loc_140039623
0x1400395aa  call    cs:__imp_ObfDereferenceObject
0x1400395b1  nop     dword ptr [rax+rax+00h]
0x1400395b6  mov     rcx, rsi; Object
0x1400395b9  call    cs:__imp_ObfDereferenceObject
0x1400395c0  nop     dword ptr [rax+rax+00h]
0x1400395c5  mov     rcx, rdi; Object
0x1400395c8  call    cs:__imp_ObfDereferenceObject
0x1400395cf  nop     dword ptr [rax+rax+00h]
0x1400395d4  mov     rcx, [rbx+10h]; FileObject
0x1400395d8  lea     rdx, [rbp+37h+Object]; Src
0x1400395dc  xor     r9d, r9d; VirtualAddress
0x1400395df  mov     byte ptr [rsp+120h+FileAttributes], 1; char
0x1400395e4  mov     [rbp+37h+Object], r13
0x1400395e8  mov     dword ptr [rsp+120h+AllocationSize], r14d; Length
0x1400395ed  lea     r8d, [r9+8]; Size
0x1400395f1  call    AfdIssueDeviceControl
0x1400395f6  mov     edi, eax
0x1400395f8  test    eax, eax
0x1400395fa  js      loc_1400394AE
0x140039600  cmp     [rbp+37h+arg_28], r14d
0x140039604  jz      short loc_14003961A
0x140039606  mov     dl, 1
0x140039608  mov     rcx, rbx
0x14003960b  call    AfdSetInLineMode
0x140039610  mov     edi, eax
0x140039612  test    eax, eax
0x140039614  js      loc_1400394AE
0x14003961a  mov     rax, [rbp+37h+var_A8]
0x14003961e  mov     [rax], rbx
0x140039621  xor     eax, eax
0x140039623  mov     rcx, [rbp+37h+var_38]
0x140039627  xor     rcx, rsp; StackCookie
0x14003962a  call    __security_check_cookie
0x14003962f  mov     rbx, [rsp+120h+arg_0]
0x140039637  add     rsp, 0F0h
0x14003963e  pop     r15
0x140039640  pop     r14
0x140039642  pop     r13
0x140039644  pop     r12
0x140039646  pop     rdi
0x140039647  pop     rsi
0x140039648  pop     rbp
0x140039649  retn
0x14003964b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003964f  lock xadd [rbx+30h], rax
0x140039655  sub     rax, 1
0x140039659  jg      short loc_140039671
0x14003965b  test    rax, rax
0x14003965e  jz      short loc_140039669
0x140039660  mov     ecx, 0Eh
0x140039665  int     29h; Win8: RtlFailFast(ecx)
0x140039667  jmp     short loc_140039671
0x140039669  mov     rcx, rbx
  ... truncated ...
```
