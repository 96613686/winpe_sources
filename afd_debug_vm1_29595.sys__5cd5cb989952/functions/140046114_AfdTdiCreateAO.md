# AfdTdiCreateAO

- ea: `0x140046114`
- end: `0x140046b8c`
- name: `AfdTdiCreateAO`
- size: `2680`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140037ea0`

## callees

- `0x14001e274`
- `0x1400309f0`
- `0x140037394`
- `0x14003f274`
- `0x14003f440`
- `0x140046114`
- `0x140046b94`
- `0x140046c00`
- `0x140047628`
- `0x140067cac`
- `0x140072840`
- `0x140072980`
- `0x140072c80`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140046ae3`
- `ntoskrnl!ZwClose` at `0x140046ae3`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400469ed`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400469ed`
- `ntoskrnl!IoCreateFileEx` at `0x1400468b3`
- `ntoskrnl!IoCreateFileEx` at `0x1400468b3`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14004682e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400468cf`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14004682e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400468cf`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140046622`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140046622`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x1400468e3`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140046a83`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140046ab6`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x1400468e3`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140046a83`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140046ab6`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x1400465fb`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x1400465fb`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x1400465bd`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x1400465bd`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140046358`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140046370`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140046358`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140046370`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14004630b`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14004630b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140046296`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400462c5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140046296`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400462c5`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14004680b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14004680b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004623e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140046259`
- `ntoskrnl!RtlInitUnicodeString` at `0x140046274`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400462e4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004623e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140046259`
- `ntoskrnl!RtlInitUnicodeString` at `0x140046274`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400462e4`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140046a35`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140046a58`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140046a35`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140046a58`
- `ntoskrnl!ObfDereferenceObject` at `0x140046aca`
- `ntoskrnl!ObfDereferenceObject` at `0x140046aca`
- `ntoskrnl!IoFileObjectType` at `0x1400469ce`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004696e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14004696e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046904`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046b48`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046904`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046b48`
- `ntoskrnl!ExAllocatePool2` at `0x140046454`
- `ntoskrnl!ExAllocatePool2` at `0x140046760`
- `ntoskrnl!ExAllocatePool2` at `0x140046454`
- `ntoskrnl!ExAllocatePool2` at `0x140046760`

## pseudocode

```c
__int64 __fastcall AfdTdiCreateAO(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        void *a4,
        int a5,
        ULONG ShareAccess,
        ULONG Options,
        KPROCESSOR_MODE AccessMode,
        char a9,
        void **a10)
{
  unsigned int v10; // r12d
  struct _FILE_OBJECT *v13; // r15
  char v14; // r14
  const WCHAR *v15; // rdx
  __int64 v16; // rbx
  NTSTATUS TransportInfo; // r14d
  PVOID v18; // rbx
  __int64 Pool2; // rax
  __int64 v20; // rdx
  struct _ECP_LIST *v21; // rcx
  int v22; // eax
  ULONG EaLength; // r14d
  _BYTE *EaBuffer; // rbx
  IRP *TopLevelIrp; // r12
  PVOID v26; // r13
  __int64 v27; // rcx
  __int64 v28; // rbx
  PVOID Object; // [rsp+80h] [rbp-3C8h] BYREF
  PVOID EcpContext; // [rsp+88h] [rbp-3C0h] BYREF
  PECP_LIST EcpList; // [rsp+90h] [rbp-3B8h] BYREF
  size_t Size; // [rsp+98h] [rbp-3B0h]
  void *FileHandle[3]; // [rsp+A0h] [rbp-3A8h] BYREF
  __int128 v35; // [rsp+B8h] [rbp-390h] BYREF
  __int128 v36; // [rsp+C8h] [rbp-380h]
  __int64 v37; // [rsp+D8h] [rbp-370h]
  void *v38; // [rsp+E0h] [rbp-368h]
  PHANDLE Handle; // [rsp+E8h] [rbp-360h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F0h] [rbp-358h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+120h] [rbp-328h] BYREF
  UNICODE_STRING String1; // [rsp+130h] [rbp-318h] BYREF
  UNICODE_STRING v43; // [rsp+140h] [rbp-308h] BYREF
  __int64 v44; // [rsp+150h] [rbp-2F8h]
  _BYTE *v45; // [rsp+158h] [rbp-2F0h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+160h] [rbp-2E8h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+170h] [rbp-2D8h] BYREF
  _QWORD v48[3]; // [rsp+180h] [rbp-2C8h] BYREF
  SOCKADDR_IN6 a; // [rsp+198h] [rbp-2B0h] BYREF
  _BYTE P[496]; // [rsp+1C0h] [rbp-288h] BYREF
  _QWORD v51[10]; // [rsp+3B0h] [rbp-98h] BYREF

  v38 = a4;
  v10 = a3;
  LODWORD(Size) = a3;
  FileHandle[2] = (void *)a1;
  Handle = a10;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  memset(P, 0, sizeof(P));
  memset(v48, 0, 22);
  FileHandle[0] = 0;
  v13 = 0;
  EcpList = 0;
  EcpContext = 0;
  v35 = 0;
  v36 = 0;
  LOWORD(v37) = 0;
  if ( !a9 )
  {
    if ( (*(_DWORD *)(a1 + 8) & 0x100000) == 0 )
    {
LABEL_20:
      Object = *(PVOID *)(a1 + 272);
      goto LABEL_24;
    }
    DestinationString = 0;
    String1 = 0;
    v43 = 0;
    Destination = 0;
    v14 = 1;
    RtlInitUnicodeString(&DestinationString, L"\\Device\\Tcp6");
    RtlInitUnicodeString(&String1, L"\\Device\\Udp6");
    RtlInitUnicodeString(&v43, L"\\Device\\RawIp6");
    if ( RtlEqualUnicodeString(&DestinationString, (PCUNICODE_STRING)(*(_QWORD *)(a1 + 272) + 32LL), 1u) )
    {
      v15 = L"\\Device\\Tcp";
    }
    else
    {
      if ( !RtlEqualUnicodeString(&String1, (PCUNICODE_STRING)(*(_QWORD *)(a1 + 272) + 32LL), 1u) )
      {
        if ( RtlPrefixUnicodeString(&v43, (PCUNICODE_STRING)(*(_QWORD *)(a1 + 272) + 32LL), 1u) )
        {
          v16 = *(_QWORD *)(*(_QWORD *)(a1 + 272) + 40LL);
          LOWORD(v51[0]) = 0;
          Destination.Buffer = (PWSTR)v51;
          *(_DWORD *)&Destination.Length = 2752512;
          RtlAppendUnicodeToString(&Destination, L"\\Device\\RawIp");
          RtlAppendUnicodeToString(&Destination, (PCWSTR)(v16 + 28));
          LOWORD(v51[5]) = 0;
        }
        else
        {
          v14 = 0;
        }
        goto LABEL_11;
      }
      v15 = L"\\Device\\Udp";
    }
    RtlInitUnicodeString(&Destination, v15);
LABEL_11:
    if ( v14 )
    {
      if ( *((_WORD *)a2 + 3) != 23 || *((_WORD *)a2 + 2) < 0x1Au )
      {
        TransportInfo = -1073741503;
        goto LABEL_66;
      }
      *(_OWORD *)&a.sin6_family = *(_OWORD *)((char *)a2 + 6);
      *(IN6_ADDR *)((char *)&a.sin6_addr + 4) = *(IN6_ADDR *)((char *)a2 + 18);
      if ( IN6_IS_ADDR_V4MAPPED(&a.sin6_addr) || IN6ADDR_ISUNSPECIFIED(&a) )
      {
        Object = 0;
        TransportInfo = AfdGetTransportInfo(&Destination);
        if ( TransportInfo < 0 )
          goto LABEL_66;
        v18 = Object;
        if ( *((_DWORD *)Object + 18) != *(_DWORD *)(*(_QWORD *)(a1 + 272) + 72LL) || (*(_BYTE *)(a1 + 6) & 1) != 0 )
        {
          AfdDereferenceTransport(Object);
          TransportInfo = -1073741637;
          goto LABEL_66;
        }
        Pool2 = ExAllocatePool2(97, 64, 1449420353);
        v44 = Pool2;
        *(_QWORD *)(a1 + 280) = Pool2;
        *(_QWORD *)(Pool2 + 24) = v18;
        LOBYTE(v20) = 1;
        AfdTdiSetDualInet(a1, v20);
      }
    }
    goto LABEL_20;
  }
  *(_OWORD *)&a.sin6_family = *(_OWORD *)((char *)a2 + 6);
  *(IN6_ADDR *)((char *)&a.sin6_addr + 4) = *(IN6_ADDR *)((char *)a2 + 18);
  v48[0] = 0x2000E00000001LL;
  LOWORD(v48[1]) = a.sin6_port;
  *(_DWORD *)((char *)&v48[1] + 2) = IN6_IS_ADDR_V4MAPPED(&a.sin6_addr) != 0 ? *(_QWORD *)((char *)a2 + 26) : 0;
  *(_QWORD *)((char *)&v48[1] + 6) = 0;
  a2 = v48;
  v10 = 22;
  LODWORD(Size) = 22;
  Object = *(PVOID *)(*(_QWORD *)(a1 + 280) + 24LL);
LABEL_24:
  if ( (*(_DWORD *)(a1 + 8) & 0x200) != 0 )
  {
    *(_DWORD *)&Destination.Length = -747341375;
    *(_DWORD *)(&Destination.MaximumLength + 1) = 1157800039;
    Destination.Buffer = (PWSTR)0xD59134F50E352E8CLL;
    if ( !AfdTdxCallbackObject )
    {
      TransportInfo = AfdTdxInitCallback();
      if ( TransportInfo < 0 )
        goto LABEL_66;
    }
    TransportInfo = FsRtlAllocateExtraCreateParameterList(0, &EcpList);
    if ( TransportInfo < 0 )
      goto LABEL_66;
    TransportInfo = FsRtlAllocateExtraCreateParameter((LPCGUID)&Destination, 0x10u, 0, 0, 0x41646641u, &EcpContext);
    v21 = EcpList;
    if ( TransportInfo < 0 )
      goto LABEL_65;
    FsRtlInsertExtraCreateParameter(EcpList, EcpContext);
    *(_QWORD *)EcpContext = a1;
    *((_QWORD *)EcpContext + 1) = 0;
    if ( !a9 )
    {
      if ( !*(_QWORD *)(a1 + 504) )
      {
        TransportInfo = -1073741436;
LABEL_64:
        v21 = EcpList;
LABEL_65:
        FsRtlFreeExtraCreateParameterList(v21);
        goto LABEL_66;
      }
      if ( ((a5 - 1) & 0xFFFFFFFD) == 0 )
      {
        memset(v51, 0, sizeof(v51));
        v51[2] = 0xFFFF00000001LL;
        v22 = 4;
        if ( a5 == 3 )
          v22 = -5;
        LODWORD(v51[3]) = v22;
        v51[4] = &AfdTLSockOptEnable;
        v51[5] = 4;
        TransportInfo = AfdTdiTlSyncIoControl(a1, v51);
        if ( TransportInfo < 0 )
          goto LABEL_64;
      }
    }
    *(_DWORD *)((char *)&v35 + 2) = 0;
    WORD3(v35) = 0;
    v36 = 0;
    LOWORD(v35) = 40;
    v37 = 1;
    *((_QWORD *)&v35 + 1) = EcpList;
  }
  EaLength = v10 + 28;
  if ( v10 >= 0xFFFFFFE4 )
  {
    TransportInfo = -1073741503;
    if ( EcpContext )
      goto LABEL_64;
  }
  else
  {
    if ( EaLength > 0x1F0 )
    {
      EaBuffer = (_BYTE *)ExAllocatePool2(289, EaLength, 1097098817);
      v45 = EaBuffer;
    }
    else
    {
      EaBuffer = P;
    }
    TopLevelIrp = 0;
    *(_DWORD *)EaBuffer = 0;
    *((_WORD *)EaBuffer + 2) = 4096;
    *((_WORD *)EaBuffer + 3) = Size;
    memmove(EaBuffer + 8, "TransportAddress", 0x11u);
    memmove(EaBuffer + 25, a2, (unsigned int)Size);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    v26 = Object;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)((char *)Object + 32);
    ObjectAttributes.SecurityDescriptor = v38;
    ObjectAttributes.SecurityQualityOfService = 0;
    if ( EcpContext )
    {
      TopLevelIrp = IoGetTopLevelIrp();
      v27 = 5;
      if ( a9 )
        v27 = 6;
      IoSetTopLevelIrp((PIRP)v27);
    }
    TransportInfo = IoCreateFileEx(
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
                      (PIO_DRIVER_CREATE_CONTEXT)((unsigned __int64)&v35 & -(__int64)(EcpContext != 0)));
    if ( EcpContext )
    {
      IoSetTopLevelIrp(TopLevelIrp);
      FsRtlFreeExtraCreateParameterList(EcpList);
    }
    if ( EaBuffer != P )
      ExFreePoolWithTag(EaBuffer, 0x41646641u);
    if ( TransportInfo < 0 )
    {
      if ( (TransportInfo == -1073741757 || TransportInfo == -1073741302) && a5 == 1 )
        TransportInfo = -1073741790;
      goto LABEL_66;
    }
    Object = 0;
    TransportInfo = ObReferenceObjectByHandle(FileHandle[0], 0, 0, 0, &Object, 0);
    v13 = (struct _FILE_OBJECT *)Object;
    if ( TransportInfo >= 0 )
    {
      TransportInfo = AfdTdiValidateTransportFileObject(v26, Object);
      if ( TransportInfo >= 0 )
      {
        if ( !Handle )
          goto LABEL_60;
        if ( (*(_DWORD *)(a1 + 8) & 0x200) != 0 )
        {
          *Handle = 0;
          goto LABEL_60;
        }
        TransportInfo = ObOpenObjectByPointer(
                          v13,
                          0x40u,
                          0,
                          0x2000000u,
                          (POBJECT_TYPE)IoFileObjectType,
                          AccessMode,
                          Handle);
        if ( TransportInfo >= 0 )
        {
LABEL_60:
          if ( a9 )
          {
            **(void ***)(a1 + 280) = FileHandle[0];
            *(_QWORD *)(*(_QWORD *)(a1 + 280) + 8LL) = v13;
            v28 = *(_QWORD *)(a1 + 280);
            *(_QWORD *)(v28 + 16) = IoGetRelatedDeviceObject(v13);
          }
          else
          {
            *(void **)(a1 + 256) = FileHandle[0];
            *(_QWORD *)(a1 + 24) = v13;
            *(_QWORD *)(a1 + 40) = IoGetRelatedDeviceObject(v13);
          }
          return (unsigned int)TransportInfo;
        }
      }
    }
  }
LABEL_66:
  if ( v13 )
    ObfDereferenceObject(v13);
  if ( FileHandle[0] )
    ZwClose(FileHandle[0]);
  if ( (*(_DWORD *)(a1 + 8) & 0x200000) != 0 )
  {
    AfdDereferenceTransport(*(_QWORD *)(a1 + 272));
    *(_QWORD *)(a1 + 272) = *(_QWORD *)(a1 + 280);
    *(_QWORD *)(a1 + 280) = 0;
    AfdTdiSetInet4Mapped(a1);
  }
  else if ( (*(_DWORD *)(a1 + 8) & 0x400000) != 0 )
  {
    AfdDereferenceTransport(*(_QWORD *)(*(_QWORD *)(a1 + 280) + 24LL));
    ExFreePoolWithTag(*(PVOID *)(a1 + 280), 0x56646641u);
    *(_QWORD *)(a1 + 280) = 0;
    AfdTdiSetDualInet(a1, 0);
  }
  return (unsigned int)TransportInfo;
}

```

## disassembly

```asm
0x140046114  push    rbx
0x140046116  push    rsi
0x140046117  push    rdi
0x140046118  push    r12
0x14004611a  push    r13
0x14004611c  push    r14
0x14004611e  push    r15
0x140046120  sub     rsp, 410h
0x140046127  mov     rax, cs:__security_cookie
0x14004612e  xor     rax, rsp
0x140046131  mov     [rsp+448h+var_48], rax
0x140046139  mov     [rsp+448h+var_368], r9
0x140046141  mov     r12d, r8d
0x140046144  mov     dword ptr [rsp+448h+Size], r8d
0x14004614c  mov     r13, rdx
0x14004614f  mov     rsi, rcx
0x140046152  mov     [rsp+448h+var_398], rcx
0x14004615a  mov     rax, [rsp+448h+arg_48]
0x140046162  mov     [rsp+448h+Handle], rax
0x14004616a  xor     eax, eax
0x14004616c  xorps   xmm0, xmm0
0x14004616f  movups  xmmword ptr [rsp+448h+ObjectAttributes.Length], xmm0
0x140046177  movups  xmmword ptr [rsp+448h+ObjectAttributes.ObjectName], xmm0
0x14004617f  movups  xmmword ptr [rsp+448h+ObjectAttributes+1Ch], xmm0
0x140046187  movups  xmmword ptr [rsp+448h+IoStatusBlock], xmm0
0x14004618f  xor     edx, edx; Val
0x140046191  mov     r8d, 1F0h; Size
0x140046197  lea     rcx, [rsp+448h+P]; void *
0x14004619f  call    memset
0x1400461a4  xorps   xmm0, xmm0
0x1400461a7  xor     eax, eax
0x1400461a9  movups  xmmword ptr [rsp+448h+var_2C8], xmm0
0x1400461b1  mov     qword ptr [rsp+448h+var_2C8+0Eh], rax
0x1400461b9  xor     edi, edi
0x1400461bb  mov     [rsp+448h+FileHandle], rdi
0x1400461c3  mov     r15d, edi
0x1400461c6  mov     [rsp+448h+EcpList], rdi
0x1400461ce  mov     [rsp+448h+var_3C0], rdi
0x1400461d6  movups  [rsp+448h+var_390], xmm0
0x1400461de  movups  [rsp+448h+var_380], xmm0
0x1400461e6  mov     word ptr [rsp+448h+var_370], ax
0x1400461ee  cmp     [rsp+448h+arg_40], dil
0x1400461f6  jnz     loc_1400464D1
0x1400461fc  mov     eax, [rsi+8]
0x1400461ff  bt      eax, 14h
0x140046203  jnb     loc_14004647D
0x140046209  movups  xmmword ptr [rsp+448h+DestinationString.Length], xmm0
0x140046211  xorps   xmm1, xmm1
0x140046214  movups  xmmword ptr [rsp+448h+String1.Length], xmm1
0x14004621c  movups  xmmword ptr [rsp+448h+var_308.Length], xmm0
0x140046224  movups  xmmword ptr [rsp+448h+Destination.Length], xmm1
0x14004622c  mov     r14b, 1
0x14004622f  lea     rdx, aDeviceTcp6; "\\Device\\Tcp6"
0x140046236  lea     rcx, [rsp+448h+DestinationString]; DestinationString
0x14004623e  call    cs:__imp_RtlInitUnicodeString
0x140046245  nop     dword ptr [rax+rax+00h]
0x14004624a  lea     rdx, aDeviceUdp6; "\\Device\\Udp6"
0x140046251  lea     rcx, [rsp+448h+String1]; DestinationString
0x140046259  call    cs:__imp_RtlInitUnicodeString
0x140046260  nop     dword ptr [rax+rax+00h]
0x140046265  lea     rdx, aDeviceRawip6; "\\Device\\RawIp6"
0x14004626c  lea     rcx, [rsp+448h+var_308]; DestinationString
0x140046274  call    cs:__imp_RtlInitUnicodeString
0x14004627b  nop     dword ptr [rax+rax+00h]
0x140046280  mov     rdx, [rsi+110h]
0x140046287  add     rdx, 20h ; ' '; String2
0x14004628b  mov     r8b, r14b; CaseInSensitive
0x14004628e  lea     rcx, [rsp+448h+DestinationString]; String1
0x140046296  call    cs:__imp_RtlEqualUnicodeString
0x14004629d  nop     dword ptr [rax+rax+00h]
0x1400462a2  test    al, al
0x1400462a4  jz      short loc_1400462AF
0x1400462a6  lea     rdx, aDeviceTcp; "\\Device\\Tcp"
0x1400462ad  jmp     short loc_1400462DC
0x1400462af  mov     rdx, [rsi+110h]
0x1400462b6  add     rdx, 20h ; ' '; String2
0x1400462ba  mov     r8b, r14b; CaseInSensitive
0x1400462bd  lea     rcx, [rsp+448h+String1]; String1
0x1400462c5  call    cs:__imp_RtlEqualUnicodeString
0x1400462cc  nop     dword ptr [rax+rax+00h]
0x1400462d1  test    al, al
0x1400462d3  jz      short loc_1400462F5
0x1400462d5  lea     rdx, aDeviceUdp; "\\Device\\Udp"
0x1400462dc  lea     rcx, [rsp+448h+Destination]; DestinationString
0x1400462e4  call    cs:__imp_RtlInitUnicodeString
0x1400462eb  nop     dword ptr [rax+rax+00h]
0x1400462f0  jmp     loc_140046389
0x1400462f5  mov     rdx, [rsi+110h]
0x1400462fc  add     rdx, 20h ; ' '; String2
0x140046300  mov     r8b, r14b; CaseInSensitive
0x140046303  lea     rcx, [rsp+448h+var_308]; String1
0x14004630b  call    cs:__imp_RtlPrefixUnicodeString
0x140046312  nop     dword ptr [rax+rax+00h]
0x140046317  test    al, al
0x140046319  jz      short loc_140046386
0x14004631b  mov     rax, [rsi+110h]
0x140046322  mov     rbx, [rax+28h]
0x140046326  mov     [rsp+448h+var_98], di
0x14004632e  lea     rax, [rsp+448h+var_98]
0x140046336  mov     [rsp+448h+Destination.Buffer], rax
0x14004633e  mov     dword ptr [rsp+448h+Destination.Length], 2A0000h
0x140046349  lea     rdx, Source; "\\Device\\RawIp"
0x140046350  lea     rcx, [rsp+448h+Destination]; Destination
0x140046358  call    cs:__imp_RtlAppendUnicodeToString
0x14004635f  nop     dword ptr [rax+rax+00h]
0x140046364  lea     rdx, [rbx+1Ch]; Source
0x140046368  lea     rcx, [rsp+448h+Destination]; Destination
0x140046370  call    cs:__imp_RtlAppendUnicodeToString
0x140046377  nop     dword ptr [rax+rax+00h]
0x14004637c  mov     word ptr [rsp+448h+var_70], di
0x140046384  jmp     short loc_140046389
0x140046386  mov     r14b, dil
0x140046389  test    r14b, r14b
0x14004638c  jz      loc_14004647D
0x140046392  cmp     word ptr [r13+6], 17h
0x140046398  jnz     loc_1400464C6
0x14004639e  cmp     word ptr [r13+4], 1Ah
0x1400463a4  jb      loc_1400464C6
0x1400463aa  movups  xmm0, xmmword ptr [r13+6]
0x1400463af  movups  xmmword ptr [rsp+448h+a.u], xmm0
0x1400463b7  movups  xmm1, xmmword ptr [r13+12h]
0x1400463bc  movups  xmmword ptr [rsp+448h+a.u+0Ch], xmm1
0x1400463c4  lea     rcx, [rsp+448h+a.u+8]; a
0x1400463cc  call    IN6_IS_ADDR_V4MAPPED
0x1400463d1  test    al, al
0x1400463d3  jnz     short loc_1400463EA
0x1400463d5  lea     rcx, [rsp+448h+a]; a
0x1400463dd  call    IN6ADDR_ISUNSPECIFIED
0x1400463e2  test    al, al
0x1400463e4  jz      loc_14004647D
0x1400463ea  mov     [rsp+448h+Object], rdi
0x1400463f2  lea     rdx, [rsp+448h+Object]
0x1400463fa  lea     rcx, [rsp+448h+Destination]; SourceString
0x140046402  call    AfdGetTransportInfo
0x140046407  mov     r14d, eax
0x14004640a  test    eax, eax
0x14004640c  jns     short loc_140046429
0x14004640e  mov     rcx, [rsp+448h+Object]
0x140046416  test    rcx, rcx
0x140046419  jz      loc_140046AC2
0x14004641f  call    AfdDereferenceTransport
0x140046424  jmp     loc_140046AC2
0x140046429  mov     rax, [rsi+110h]
0x140046430  mov     ecx, [rax+48h]
0x140046433  mov     rbx, [rsp+448h+Object]
0x14004643b  cmp     [rbx+48h], ecx
0x14004643e  jnz     short loc_1400464B3
0x140046440  test    byte ptr [rsi+6], 1
0x140046444  jnz     short loc_1400464B3
0x140046446  mov     edx, 40h ; '@'
0x14004644b  lea     ecx, [rdx+21h]
0x14004644e  mov     r8d, 56646641h
0x140046454  call    cs:__imp_ExAllocatePool2
0x14004645b  nop     dword ptr [rax+rax+00h]
0x140046460  mov     [rsp+448h+var_2F8], rax
0x140046468  mov     [rsi+118h], rax
0x14004646f  mov     [rax+18h], rbx
0x140046473  mov     dl, 1
0x140046475  mov     rcx, rsi
0x140046478  call    AfdTdiSetDualInet
0x14004647d  mov     rcx, [rsi+110h]
0x140046484  mov     [rsp+448h+Object], rcx
0x14004648c  jmp     loc_140046560
0x140046491  mov     r14d, eax
0x140046494  mov     rcx, [rsp+448h+Object]
0x14004649c  call    AfdDereferenceTransport
0x1400464a1  xor     edi, edi
0x1400464a3  mov     r15d, edi
0x1400464a6  mov     rsi, [rsp+448h+var_398]
0x1400464ae  jmp     loc_140046AC2
0x1400464b3  mov     rcx, rbx
0x1400464b6  call    AfdDereferenceTransport
0x1400464bb  mov     r14d, 0C00000BBh
0x1400464c1  jmp     loc_140046AC2
0x1400464c6  mov     r14d, 0C0000141h
0x1400464cc  jmp     loc_140046AC2
0x1400464d1  movups  xmm0, xmmword ptr [r13+6]
0x1400464d6  movups  xmmword ptr [rsp+448h+a.u], xmm0
0x1400464de  movups  xmm1, xmmword ptr [r13+12h]
0x1400464e3  movups  xmmword ptr [rsp+448h+a.u+0Ch], xmm1
0x1400464eb  mov     dword ptr [rsp+448h+var_2C8], 1
0x1400464f6  mov     dword ptr [rsp+448h+var_2C8+4], 2000Eh
0x140046501  mov     rax, qword ptr [rsp+448h+a.u+2]
0x140046509  mov     word ptr [rsp+448h+var_2C8+8], ax
0x140046511  lea     rcx, [rsp+448h+a.u+8]; a
0x140046519  call    IN6_IS_ADDR_V4MAPPED
0x14004651e  neg     al
0x140046520  sbb     ecx, ecx
0x140046522  mov     rax, [r13+1Ah]
0x140046526  and     ecx, eax
0x140046528  mov     dword ptr [rsp+448h+var_2C8+0Ah], ecx
0x14004652f  xor     eax, eax
0x140046531  mov     qword ptr [rsp+448h+var_2C8+0Eh], rax
0x140046539  lea     r13, [rsp+448h+var_2C8]
0x140046541  lea     r12d, [rax+16h]
0x140046545  mov     dword ptr [rsp+448h+Size], r12d
0x14004654d  mov     rax, [rsi+118h]
0x140046554  mov     rax, [rax+18h]
0x140046558  mov     [rsp+448h+Object], rax
0x140046560  mov     eax, [rsi+8]
0x140046563  bt      eax, 9
0x140046567  jnb     loc_140046730
0x14004656d  mov     dword ptr [rsp+448h+Destination.Length], 0D37479C1h
0x140046578  mov     dword ptr [rsp+448h+Destination+4], 4502A067h
0x140046583  mov     dword ptr [rsp+448h+Destination.Buffer], 0E352E8Ch
0x14004658e  mov     dword ptr [rsp+448h+Destination.Buffer+4], 0D59134F5h
0x140046599  cmp     cs:AfdTdxCallbackObject, 0
0x1400465a1  jnz     short loc_1400465B3
0x1400465a3  call    AfdTdxInitCallback
0x1400465a8  mov     r14d, eax
0x1400465ab  test    eax, eax
0x1400465ad  js      loc_140046AC2
0x1400465b3  lea     rdx, [rsp+448h+EcpList]; EcpList
0x1400465bb  xor     ecx, ecx; Flags
0x1400465bd  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x1400465c4  nop     dword ptr [rax+rax+00h]
0x1400465c9  mov     r14d, eax
0x1400465cc  test    eax, eax
0x1400465ce  js      loc_140046AC2
0x1400465d4  lea     rax, [rsp+448h+var_3C0]
0x1400465dc  mov     [rsp+448h+EcpContext], rax; EcpContext
0x1400465e1  mov     [rsp+448h+PoolTag], 41646641h; PoolTag
0x1400465e9  xor     r9d, r9d; CleanupCallback
0x1400465ec  xor     r8d, r8d; Flags
0x1400465ef  lea     edx, [r9+10h]; SizeOfContext
0x1400465f3  lea     rcx, [rsp+448h+Destination]; EcpType
0x1400465fb  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x140046602  nop     dword ptr [rax+rax+00h]
0x140046607  mov     r14d, eax
0x14004660a  mov     rcx, [rsp+448h+EcpList]; EcpList
0x140046612  test    eax, eax
0x140046614  js      loc_140046AB6
0x14004661a  mov     rdx, [rsp+448h+var_3C0]; EcpContext
0x140046622  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x140046629  nop     dword ptr [rax+rax+00h]
0x14004662e  mov     rax, [rsp+448h+var_3C0]
0x140046636  mov     [rax], rsi
0x140046639  mov     rax, [rsp+448h+var_3C0]
0x140046641  mov     [rax+8], rdi
0x140046645  cmp     [rsp+448h+arg_40], dil
0x14004664d  jnz     loc_1400466EC
0x140046653  cmp     [rsi+1F8h], rdi
0x14004665a  jnz     short loc_140046667
0x14004665c  mov     r14d, 0C0000184h
0x140046662  jmp     loc_140046AAE
0x140046667  mov     ebx, [rsp+448h+arg_20]
0x14004666e  lea     eax, [rbx-1]
0x140046671  test    eax, 0FFFFFFFDh
0x140046676  jnz     short loc_1400466EC
0x140046678  xor     edx, edx; Val
0x14004667a  lea     r8d, [rdx+50h]; Size
0x14004667e  lea     rcx, [rsp+448h+var_98]; void *
0x140046686  call    memset
0x14004668b  mov     [rsp+448h+var_88], 1
0x140046696  mov     [rsp+448h+var_84], 0FFFFh
0x1400466a1  mov     edx, 4
0x1400466a6  mov     eax, edx
0x1400466a8  mov     ecx, 0FFFFFFFBh
0x1400466ad  cmp     ebx, 3
0x1400466b0  cmovz   eax, ecx
0x1400466b3  mov     [rsp+448h+var_80], eax
0x1400466ba  lea     rax, AfdTLSockOptEnable
0x1400466c1  mov     [rsp+448h+var_78], rax
0x1400466c9  mov     [rsp+448h+var_70], rdx
0x1400466d1  lea     rdx, [rsp+448h+var_98]
0x1400466d9  mov     rcx, rsi
0x1400466dc  call    AfdTdiTlSyncIoControl
0x1400466e1  mov     r14d, eax
0x1400466e4  test    eax, eax
0x1400466e6  js      loc_140046AAE
0x1400466ec  mov     dword ptr [rsp+448h+var_390+2], edi
0x1400466f3  mov     word ptr [rsp+448h+var_390+6], di
0x1400466fb  xorps   xmm0, xmm0
0x1400466fe  movdqu  [rsp+448h+var_380], xmm0
0x140046707  mov     eax, 28h ; '('
0x14004670c  mov     word ptr [rsp+448h+var_390], ax
0x140046714  mov     [rsp+448h+var_370], 1
0x140046720  mov     rax, [rsp+448h+EcpList]
0x140046728  mov     qword ptr [rsp+448h+var_390+8], rax
0x140046730  lea     r14d, [r12+1Ch]
0x140046735  cmp     r14d, 1Ch
0x140046739  jb      loc_140046A9E
0x14004673f  cmp     r14d, 1F0h
0x140046746  ja      short loc_140046752
0x140046748  lea     rbx, [rsp+448h+P]
0x140046750  jmp     short loc_140046777
0x140046752  mov     edx, r14d
0x140046755  mov     ecx, 121h
0x14004675a  mov     r8d, 41646641h
0x140046760  call    cs:__imp_ExAllocatePool2
0x140046767  nop     dword ptr [rax+rax+00h]
0x14004676c  mov     rbx, rax
0x14004676f  mov     [rsp+448h+var_2F0], rax
0x140046777  mov     r12, rdi
0x14004677a  mov     [rbx], edi
0x14004677c  mov     word ptr [rbx+4], 1000h
0x140046782  mov     eax, dword ptr [rsp+448h+Size]
0x140046789  mov     [rbx+6], ax
0x14004678d  lea     rcx, [rbx+8]; void *
0x140046791  mov     r8d, 11h; Size
  ... truncated ...
```
