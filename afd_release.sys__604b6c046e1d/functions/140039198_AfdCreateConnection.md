# AfdCreateConnection

- ea: `0x140039198`
- end: `0x140039655`
- name: `AfdCreateConnection`
- size: `1213`
- prototype: `__int64 __fastcall(__int64, void *, void *, unsigned __int8, int, int, struct _KPROCESS *Process, __int64 *)`
- caller_count: `7`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400044fc`
- `0x14001a8a0`
- `0x140037e80`
- `0x1400398b0`
- `0x14003ae30`
- `0x140047640`
- `0x140059910`

## callees

- `0x140015880`
- `0x14001c708`
- `0x14002c770`
- `0x140039198`
- `0x14004fba4`
- `0x140067b0c`
- `0x1400726a0`
- `0x140093008`
- `0x1400931d0`

## import_xrefs

- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140039205`
- `ntoskrnl!PsChargeProcessPoolQuota` at `0x140039205`
- `ntoskrnl!PsReturnPoolQuota` at `0x140039257`
- `ntoskrnl!PsReturnPoolQuota` at `0x140039257`
- `ntoskrnl!IoCreateFile` at `0x140039404`
- `ntoskrnl!IoCreateFile` at `0x140039404`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x1400394fe`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x14003951f`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x1400394fe`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x14003951f`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400394ae`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140039510`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400394ae`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140039510`
- `ntoskrnl!ObfReferenceObject` at `0x14003926d`
- `ntoskrnl!ObfReferenceObject` at `0x14003926d`
- `ntoskrnl!ObfDereferenceObject` at `0x140039533`
- `ntoskrnl!ObfDereferenceObject` at `0x140039542`
- `ntoskrnl!ObfDereferenceObject` at `0x140039551`
- `ntoskrnl!ObfDereferenceObject` at `0x14003958a`
- `ntoskrnl!ObfDereferenceObject` at `0x140039599`
- `ntoskrnl!ObfDereferenceObject` at `0x1400395a8`
- `ntoskrnl!ObfDereferenceObject` at `0x140039533`
- `ntoskrnl!ObfDereferenceObject` at `0x140039542`
- `ntoskrnl!ObfDereferenceObject` at `0x140039551`
- `ntoskrnl!ObfDereferenceObject` at `0x14003958a`
- `ntoskrnl!ObfDereferenceObject` at `0x140039599`
- `ntoskrnl!ObfDereferenceObject` at `0x1400395a8`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140039442`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400394e4`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140039442`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400394e4`

## pseudocode

```c
__int64 __fastcall AfdCreateConnection(
        __int64 a1,
        void *a2,
        void *a3,
        unsigned __int8 a4,
        int a5,
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
  int Status; // edi
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
      WPP_SF_(1282, 11, WPP_f3ccc707676b3efa4ccbbbb633e4b25e_Traceguids);
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
  if ( (*(_DWORD *)(a1 + 16) & 0x10000) != 0 || (*(_DWORD *)(a1 + 8) & 0x8000000) != 0 )
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
    WPP_SF_qq(1026, 12, WPP_f3ccc707676b3efa4ccbbbb633e4b25e_Traceguids, Connection, v21);
  Status = AfdTdiValidateTransportFileObject(v17);
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
    Status = AfdIssueDeviceControl(v33, &Object, 8u, 0, 0, 1u);
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
0x140039198  mov     [rsp-8+arg_0], rbx
0x14003919d  push    rbp
0x14003919e  push    rsi
0x14003919f  push    rdi
0x1400391a0  push    r12
0x1400391a2  push    r13
0x1400391a4  push    r14
0x1400391a6  push    r15
0x1400391a8  lea     rbp, [rsp-7]
0x1400391ad  sub     rsp, 0F0h
0x1400391b4  mov     rax, cs:__security_cookie
0x1400391bb  xor     rax, rsp
0x1400391be  mov     [rbp+37h+var_38], rax
0x1400391c2  mov     rax, [rbp+37h+arg_38]
0x1400391c6  xorps   xmm0, xmm0
0x1400391c9  mov     rsi, [rbp+37h+Process]
0x1400391cd  mov     r13, r8
0x1400391d0  mov     edi, [rbp+37h+arg_20]
0x1400391d3  mov     r15, rcx
0x1400391d6  mov     [rbp+37h+var_A8], rax
0x1400391da  mov     r14d, 100h
0x1400391e0  mov     [rbp+37h+Object], rdx
0x1400391e4  xor     eax, eax
0x1400391e6  movups  xmmword ptr [rbp+37h+ObjectAttributes.ObjectName], xmm0
0x1400391ea  mov     r8d, r14d; Amount
0x1400391ed  movzx   r12d, r9b
0x1400391f1  mov     edx, 200h; PoolType
0x1400391f6  mov     rcx, rsi; Process
0x1400391f9  movups  xmmword ptr [rbp+37h+IoStatusBlock], xmm0
0x1400391fd  movups  xmmword ptr [rbp+37h+ObjectAttributes.Length], xmm0
0x140039201  movups  xmmword ptr [rbp+37h+ObjectAttributes+1Ch], xmm0
0x140039205  call    cs:__imp_PsChargeProcessPoolQuota
0x14003920c  nop     dword ptr [rax+rax+00h]
0x140039211  mov     ebx, eax
0x140039213  test    eax, eax
0x140039215  jns     short loc_14003923D
0x140039217  test    byte ptr cs:xmmword_1400875E0+8, 4
0x14003921e  jz      short loc_140039236
0x140039220  mov     edx, 0Bh
0x140039225  lea     r8, WPP_f3ccc707676b3efa4ccbbbb633e4b25e_Traceguids
0x14003922c  mov     ecx, 502h
0x140039231  call    WPP_SF_
0x140039236  mov     eax, ebx
0x140039238  jmp     loc_140039603
0x14003923d  mov     ecx, edi
0x14003923f  call    AfdAllocateConnection
0x140039244  mov     rbx, rax
0x140039247  mov     rcx, rsi; Object
0x14003924a  test    rax, rax
0x14003924d  jnz     short loc_14003926D
0x14003924f  mov     r8, r14; Amount
0x140039252  mov     edx, 200h; PoolType
0x140039257  call    cs:__imp_PsReturnPoolQuota
0x14003925e  nop     dword ptr [rax+rax+00h]
0x140039263  mov     eax, 0C000009Ah
0x140039268  jmp     loc_140039603
0x14003926d  call    cs:__imp_ObfReferenceObject
0x140039274  nop     dword ptr [rax+rax+00h]
0x140039279  mov     eax, [rbx+4]
0x14003927c  mov     ecx, r12d
0x14003927f  xor     ecx, eax
0x140039281  mov     [rbx+20h], rsi
0x140039285  and     ecx, 1
0x140039288  xor     edx, edx
0x14003928a  xor     ecx, eax
0x14003928c  mov     eax, edi
0x14003928e  shl     eax, 11h
0x140039291  xor     eax, ecx
0x140039293  and     eax, 20000h
0x140039298  xor     eax, ecx
0x14003929a  mov     [rbx+4], eax
0x14003929d  test    r12b, r12b
0x1400392a0  jz      short loc_1400392AE
0x1400392a2  test    edi, edi
0x1400392a4  jnz     short loc_1400392AE
0x1400392a6  mov     word ptr [rbx+68h], 1
0x1400392ac  jmp     short loc_1400392E1
0x1400392ae  lea     rax, [rbx+38h]
0x1400392b2  mov     [rbx+58h], rdx
0x1400392b6  mov     [rax+8], rax
0x1400392ba  mov     [rax], rax
0x1400392bd  lea     rax, [rbx+68h]
0x1400392c1  mov     [rax+8], rax
0x1400392c5  mov     [rax], rax
0x1400392c8  lea     rax, [rbx+48h]
0x1400392cc  mov     [rax+8], rax
0x1400392d0  mov     [rax], rax
0x1400392d3  mov     [rbx+60h], rdx
0x1400392d7  mov     [rbx+88h], edx
0x1400392dd  mov     [rbx+78h], rdx
0x1400392e1  mov     ecx, cs:AfdTcpReceiveWindowMax
0x1400392e7  test    ecx, ecx
0x1400392e9  jz      short loc_140039311
0x1400392eb  test    edi, edi
0x1400392ed  jz      short loc_140039311
0x1400392ef  mov     rax, [r15+110h]
0x1400392f6  cmp     dword ptr [rax+18h], 6
0x1400392fa  jnz     short loc_140039311
0x1400392fc  cmp     cs:AfdReceiveWindowSize, ecx
0x140039302  cmovb   ecx, cs:AfdReceiveWindowSize
0x140039309  mov     [rbx+90h], ecx
0x14003930f  jmp     short loc_14003931D
0x140039311  mov     eax, cs:AfdReceiveWindowSize
0x140039317  mov     [rbx+90h], eax
0x14003931d  mov     eax, cs:AfdSendWindowSize
0x140039323  mov     [rbx+94h], eax
0x140039329  test    edi, edi
0x14003932b  jnz     loc_1400395FA
0x140039331  bts     dword ptr [rbx+4], 15h
0x140039336  movups  xmm0, xmmword ptr cs:aConnectioncont; "ConnectionContext"
0x14003933d  movzx   eax, word ptr cs:aConnectioncont+10h; "t"
0x140039344  mov     r12, [rbp+37h+Object]
0x140039348  movups  xmmword ptr [rbp+37h+var_58], xmm0
0x14003934c  mov     word ptr [rbp+37h+var_58+10h], ax
0x140039350  xorps   xmm0, xmm0
0x140039353  mov     [rbp+37h+var_60], edx
0x140039356  lea     rax, [r12+20h]
0x14003935b  mov     [rbp+37h+var_5C], 81100h
0x140039362  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x140039367  mov     [rbp+37h+var_46], rbx
0x14003936b  mov     [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x140039372  mov     [rbp+37h+ObjectAttributes.RootDirectory], rdx
0x140039376  mov     [rbp+37h+ObjectAttributes.Attributes], 240h
0x14003937d  mov     [rbp+37h+ObjectAttributes.ObjectName], rax
0x140039381  test    dword ptr [r15+10h], 10000h
0x140039389  jnz     short loc_14003939C
0x14003938b  mov     eax, [r15+8]
0x14003938f  bt      eax, 1Bh
0x140039393  jb      short loc_14003939C
0x140039395  mov     edx, 0C0100000h
0x14003939a  jmp     short loc_1400393A7
0x14003939c  mov     edx, 2000000h; DesiredAccess
0x1400393a1  mov     r14d, 101h
0x1400393a7  movzx   ecx, word ptr [rbp+37h+var_5C+2]
0x1400393ab  lea     rax, [rbp+37h+var_60]
0x1400393af  movzx   r8d, byte ptr [rbp+37h+var_5C+1]
0x1400393b4  lea     rsi, [rbx+0A8h]
0x1400393bb  mov     [rsp+120h+Options], r14d; Options
0x1400393c0  lea     r9, [rbp+37h+IoStatusBlock]; IoStatusBlock
0x1400393c4  xor     r14d, r14d
0x1400393c7  add     ecx, 9
0x1400393ca  mov     [rsp+120h+InternalParameters], r14; InternalParameters
0x1400393cf  add     r8d, ecx
0x1400393d2  mov     [rsp+120h+CreateFileType], r14d; CreateFileType
0x1400393d7  mov     rcx, rsi; FileHandle
0x1400393da  mov     [rsp+120h+EaLength], r8d; EaLength
0x1400393df  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x1400393e3  mov     [rsp+120h+EaBuffer], rax; EaBuffer
0x1400393e8  mov     [rsp+120h+CreateOptions], r14d; CreateOptions
0x1400393ed  mov     [rsp+120h+Disposition], 2; Disposition
0x1400393f5  mov     [rsp+120h+ShareAccess], r14d; ShareAccess
0x1400393fa  mov     [rsp+120h+FileAttributes], r14d; FileAttributes
0x1400393ff  mov     [rsp+120h+AllocationSize], r14; AllocationSize
0x140039404  call    cs:__imp_IoCreateFile
0x14003940b  nop     dword ptr [rax+rax+00h]
0x140039410  mov     edi, eax
0x140039412  test    eax, eax
0x140039414  js      loc_14003962B
0x14003941a  mov     edi, dword ptr [rbp+37h+IoStatusBlock]
0x14003941d  test    edi, edi
0x14003941f  js      loc_14003962B
0x140039425  mov     rcx, [rsi]; Handle
0x140039428  lea     rax, [rbp+37h+Object]
0x14003942c  mov     qword ptr [rsp+120h+FileAttributes], r14; HandleInformation
0x140039431  xor     r9d, r9d; AccessMode
0x140039434  xor     r8d, r8d; ObjectType
0x140039437  mov     [rsp+120h+AllocationSize], rax; Object
0x14003943c  xor     edx, edx; DesiredAccess
0x14003943e  mov     [rbp+37h+Object], r14
0x140039442  call    cs:__imp_ObReferenceObjectByHandle
0x140039449  nop     dword ptr [rax+rax+00h]
0x14003944e  mov     r8, [rbp+37h+Object]
0x140039452  mov     [rbx+10h], r8
0x140039456  test    byte ptr cs:xmmword_1400875E0, 4
0x14003945d  jz      short loc_14003947C
0x14003945f  mov     [rsp+120h+AllocationSize], r8
0x140039464  lea     edx, [r14+0Ch]
0x140039468  lea     r8, WPP_f3ccc707676b3efa4ccbbbb633e4b25e_Traceguids
0x14003946f  mov     ecx, 402h
0x140039474  mov     r9, rbx
0x140039477  call    WPP_SF_qq
0x14003947c  mov     rdx, [rbx+10h]
0x140039480  mov     rcx, r12
0x140039483  call    AfdTdiValidateTransportFileObject
0x140039488  mov     edi, eax
0x14003948a  test    eax, eax
0x14003948c  jns     short loc_1400394AA
0x14003948e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140039492  lock xadd [rbx+30h], rcx
0x140039498  sub     rcx, 1
0x14003949c  jg      loc_140039651
0x1400394a2  test    rcx, rcx
0x1400394a5  jmp     loc_14003963E
0x1400394aa  mov     rcx, [rbx+10h]; FileObject
0x1400394ae  call    cs:__imp_IoGetRelatedDeviceObject
0x1400394b5  nop     dword ptr [rax+rax+00h]
0x1400394ba  mov     [rbx+18h], rax
0x1400394be  test    r13, r13
0x1400394c1  jz      loc_1400395E0
0x1400394c7  lea     rax, [rbp+37h+Object]
0x1400394cb  mov     qword ptr [rsp+120h+FileAttributes], r14; HandleInformation
0x1400394d0  xor     r9d, r9d; AccessMode
0x1400394d3  mov     [rsp+120h+AllocationSize], rax; Object
0x1400394d8  xor     r8d, r8d; ObjectType
0x1400394db  mov     [rbp+37h+Object], r14
0x1400394df  xor     edx, edx; DesiredAccess
0x1400394e1  mov     rcx, r13; Handle
0x1400394e4  call    cs:__imp_ObReferenceObjectByHandle
0x1400394eb  nop     dword ptr [rax+rax+00h]
0x1400394f0  mov     edi, eax
0x1400394f2  test    eax, eax
0x1400394f4  js      short loc_14003948E
0x1400394f6  mov     rcx, [rbx+18h]; DeviceObject
0x1400394fa  mov     rdi, [rbp+37h+Object]
0x1400394fe  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x140039505  nop     dword ptr [rax+rax+00h]
0x14003950a  mov     rcx, rdi; FileObject
0x14003950d  mov     rsi, rax
0x140039510  call    cs:__imp_IoGetRelatedDeviceObject
0x140039517  nop     dword ptr [rax+rax+00h]
0x14003951c  mov     rcx, rax; DeviceObject
0x14003951f  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x140039526  nop     dword ptr [rax+rax+00h]
0x14003952b  mov     rcx, rax; Object
0x14003952e  cmp     rsi, rax
0x140039531  jz      short loc_14003958A
0x140039533  call    cs:__imp_ObfDereferenceObject
0x14003953a  nop     dword ptr [rax+rax+00h]
0x14003953f  mov     rcx, rsi; Object
0x140039542  call    cs:__imp_ObfDereferenceObject
0x140039549  nop     dword ptr [rax+rax+00h]
0x14003954e  mov     rcx, rdi; Object
0x140039551  call    cs:__imp_ObfDereferenceObject
0x140039558  nop     dword ptr [rax+rax+00h]
0x14003955d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140039561  lock xadd [rbx+30h], rax
0x140039567  sub     rax, 1
0x14003956b  jg      short loc_140039583
0x14003956d  test    rax, rax
0x140039570  jz      short loc_14003957B
0x140039572  mov     ecx, 0Eh
0x140039577  int     29h; Win8: RtlFailFast(ecx)
0x140039579  jmp     short loc_140039583
0x14003957b  mov     rcx, rbx
0x14003957e  call    AfdCloseConnection
0x140039583  mov     eax, 0C000000Dh
0x140039588  jmp     short loc_140039603
0x14003958a  call    cs:__imp_ObfDereferenceObject
0x140039591  nop     dword ptr [rax+rax+00h]
0x140039596  mov     rcx, rsi; Object
0x140039599  call    cs:__imp_ObfDereferenceObject
0x1400395a0  nop     dword ptr [rax+rax+00h]
0x1400395a5  mov     rcx, rdi; Object
0x1400395a8  call    cs:__imp_ObfDereferenceObject
0x1400395af  nop     dword ptr [rax+rax+00h]
0x1400395b4  mov     rcx, [rbx+10h]; FileObject
0x1400395b8  lea     rdx, [rbp+37h+Object]; Src
0x1400395bc  xor     r9d, r9d; VirtualAddress
0x1400395bf  mov     byte ptr [rsp+120h+FileAttributes], 1; char
0x1400395c4  mov     [rbp+37h+Object], r13
0x1400395c8  mov     dword ptr [rsp+120h+AllocationSize], r14d; Length
0x1400395cd  lea     r8d, [r9+8]; Size
0x1400395d1  call    AfdIssueDeviceControl
0x1400395d6  mov     edi, eax
0x1400395d8  test    eax, eax
0x1400395da  js      loc_14003948E
0x1400395e0  cmp     [rbp+37h+arg_28], r14d
0x1400395e4  jz      short loc_1400395FA
0x1400395e6  mov     dl, 1
0x1400395e8  mov     rcx, rbx
0x1400395eb  call    AfdSetInLineMode
0x1400395f0  mov     edi, eax
0x1400395f2  test    eax, eax
0x1400395f4  js      loc_14003948E
0x1400395fa  mov     rax, [rbp+37h+var_A8]
0x1400395fe  mov     [rax], rbx
0x140039601  xor     eax, eax
0x140039603  mov     rcx, [rbp+37h+var_38]
0x140039607  xor     rcx, rsp; StackCookie
0x14003960a  call    __security_check_cookie
0x14003960f  mov     rbx, [rsp+120h+arg_0]
0x140039617  add     rsp, 0F0h
0x14003961e  pop     r15
0x140039620  pop     r14
0x140039622  pop     r13
0x140039624  pop     r12
0x140039626  pop     rdi
0x140039627  pop     rsi
0x140039628  pop     rbp
0x140039629  retn
0x14003962b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003962f  lock xadd [rbx+30h], rax
0x140039635  sub     rax, 1
0x140039639  jg      short loc_140039651
0x14003963b  test    rax, rax
0x14003963e  jz      short loc_140039649
0x140039640  mov     ecx, 0Eh
0x140039645  int     29h; Win8: RtlFailFast(ecx)
0x140039647  jmp     short loc_140039651
0x140039649  mov     rcx, rbx
  ... truncated ...
```
