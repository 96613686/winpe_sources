# AfdTdiCreateAO

- ea: `0x140046094`
- end: `0x140046b0c`
- name: `AfdTdiCreateAO`
- size: `2680`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140037e80`

## callees

- `0x14001e274`
- `0x1400309d0`
- `0x140037374`
- `0x14003f254`
- `0x14003f420`
- `0x140046094`
- `0x140046b14`
- `0x140046b80`
- `0x1400475a8`
- `0x140067b0c`
- `0x1400726a0`
- `0x140072800`
- `0x140072b00`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140046a63`
- `ntoskrnl!ZwClose` at `0x140046a63`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14004696d`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14004696d`
- `ntoskrnl!IoCreateFileEx` at `0x140046833`
- `ntoskrnl!IoCreateFileEx` at `0x140046833`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400467ae`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14004684f`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400467ae`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14004684f`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x1400465a2`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x1400465a2`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140046863`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140046a03`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140046a36`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140046863`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140046a03`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140046a36`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14004657b`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14004657b`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14004653d`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14004653d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400462d8`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400462f0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400462d8`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1400462f0`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14004628b`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14004628b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140046216`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140046245`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140046216`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140046245`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14004678b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14004678b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400461be`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400461d9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400461f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140046264`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400461be`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400461d9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400461f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x140046264`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400469b5`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400469d8`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400469b5`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400469d8`
- `ntoskrnl!ObfDereferenceObject` at `0x140046a4a`
- `ntoskrnl!ObfDereferenceObject` at `0x140046a4a`
- `ntoskrnl!IoFileObjectType` at `0x14004694e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400468ee`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400468ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046884`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046ac8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046884`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046ac8`
- `ntoskrnl!ExAllocatePool2` at `0x1400463d4`
- `ntoskrnl!ExAllocatePool2` at `0x1400466e0`
- `ntoskrnl!ExAllocatePool2` at `0x1400463d4`
- `ntoskrnl!ExAllocatePool2` at `0x1400466e0`

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
0x140046094  push    rbx
0x140046096  push    rsi
0x140046097  push    rdi
0x140046098  push    r12
0x14004609a  push    r13
0x14004609c  push    r14
0x14004609e  push    r15
0x1400460a0  sub     rsp, 410h
0x1400460a7  mov     rax, cs:__security_cookie
0x1400460ae  xor     rax, rsp
0x1400460b1  mov     [rsp+448h+var_48], rax
0x1400460b9  mov     [rsp+448h+var_368], r9
0x1400460c1  mov     r12d, r8d
0x1400460c4  mov     dword ptr [rsp+448h+Size], r8d
0x1400460cc  mov     r13, rdx
0x1400460cf  mov     rsi, rcx
0x1400460d2  mov     [rsp+448h+var_398], rcx
0x1400460da  mov     rax, [rsp+448h+arg_48]
0x1400460e2  mov     [rsp+448h+Handle], rax
0x1400460ea  xor     eax, eax
0x1400460ec  xorps   xmm0, xmm0
0x1400460ef  movups  xmmword ptr [rsp+448h+ObjectAttributes.Length], xmm0
0x1400460f7  movups  xmmword ptr [rsp+448h+ObjectAttributes.ObjectName], xmm0
0x1400460ff  movups  xmmword ptr [rsp+448h+ObjectAttributes+1Ch], xmm0
0x140046107  movups  xmmword ptr [rsp+448h+IoStatusBlock], xmm0
0x14004610f  xor     edx, edx; Val
0x140046111  mov     r8d, 1F0h; Size
0x140046117  lea     rcx, [rsp+448h+P]; void *
0x14004611f  call    memset
0x140046124  xorps   xmm0, xmm0
0x140046127  xor     eax, eax
0x140046129  movups  xmmword ptr [rsp+448h+var_2C8], xmm0
0x140046131  mov     qword ptr [rsp+448h+var_2C8+0Eh], rax
0x140046139  xor     edi, edi
0x14004613b  mov     [rsp+448h+FileHandle], rdi
0x140046143  mov     r15d, edi
0x140046146  mov     [rsp+448h+EcpList], rdi
0x14004614e  mov     [rsp+448h+var_3C0], rdi
0x140046156  movups  [rsp+448h+var_390], xmm0
0x14004615e  movups  [rsp+448h+var_380], xmm0
0x140046166  mov     word ptr [rsp+448h+var_370], ax
0x14004616e  cmp     [rsp+448h+arg_40], dil
0x140046176  jnz     loc_140046451
0x14004617c  mov     eax, [rsi+8]
0x14004617f  bt      eax, 14h
0x140046183  jnb     loc_1400463FD
0x140046189  movups  xmmword ptr [rsp+448h+DestinationString.Length], xmm0
0x140046191  xorps   xmm1, xmm1
0x140046194  movups  xmmword ptr [rsp+448h+String1.Length], xmm1
0x14004619c  movups  xmmword ptr [rsp+448h+var_308.Length], xmm0
0x1400461a4  movups  xmmword ptr [rsp+448h+Destination.Length], xmm1
0x1400461ac  mov     r14b, 1
0x1400461af  lea     rdx, aDeviceTcp6; "\\Device\\Tcp6"
0x1400461b6  lea     rcx, [rsp+448h+DestinationString]; DestinationString
0x1400461be  call    cs:__imp_RtlInitUnicodeString
0x1400461c5  nop     dword ptr [rax+rax+00h]
0x1400461ca  lea     rdx, aDeviceUdp6; "\\Device\\Udp6"
0x1400461d1  lea     rcx, [rsp+448h+String1]; DestinationString
0x1400461d9  call    cs:__imp_RtlInitUnicodeString
0x1400461e0  nop     dword ptr [rax+rax+00h]
0x1400461e5  lea     rdx, aDeviceRawip6; "\\Device\\RawIp6"
0x1400461ec  lea     rcx, [rsp+448h+var_308]; DestinationString
0x1400461f4  call    cs:__imp_RtlInitUnicodeString
0x1400461fb  nop     dword ptr [rax+rax+00h]
0x140046200  mov     rdx, [rsi+110h]
0x140046207  add     rdx, 20h ; ' '; String2
0x14004620b  mov     r8b, r14b; CaseInSensitive
0x14004620e  lea     rcx, [rsp+448h+DestinationString]; String1
0x140046216  call    cs:__imp_RtlEqualUnicodeString
0x14004621d  nop     dword ptr [rax+rax+00h]
0x140046222  test    al, al
0x140046224  jz      short loc_14004622F
0x140046226  lea     rdx, aDeviceTcp; "\\Device\\Tcp"
0x14004622d  jmp     short loc_14004625C
0x14004622f  mov     rdx, [rsi+110h]
0x140046236  add     rdx, 20h ; ' '; String2
0x14004623a  mov     r8b, r14b; CaseInSensitive
0x14004623d  lea     rcx, [rsp+448h+String1]; String1
0x140046245  call    cs:__imp_RtlEqualUnicodeString
0x14004624c  nop     dword ptr [rax+rax+00h]
0x140046251  test    al, al
0x140046253  jz      short loc_140046275
0x140046255  lea     rdx, aDeviceUdp; "\\Device\\Udp"
0x14004625c  lea     rcx, [rsp+448h+Destination]; DestinationString
0x140046264  call    cs:__imp_RtlInitUnicodeString
0x14004626b  nop     dword ptr [rax+rax+00h]
0x140046270  jmp     loc_140046309
0x140046275  mov     rdx, [rsi+110h]
0x14004627c  add     rdx, 20h ; ' '; String2
0x140046280  mov     r8b, r14b; CaseInSensitive
0x140046283  lea     rcx, [rsp+448h+var_308]; String1
0x14004628b  call    cs:__imp_RtlPrefixUnicodeString
0x140046292  nop     dword ptr [rax+rax+00h]
0x140046297  test    al, al
0x140046299  jz      short loc_140046306
0x14004629b  mov     rax, [rsi+110h]
0x1400462a2  mov     rbx, [rax+28h]
0x1400462a6  mov     [rsp+448h+var_98], di
0x1400462ae  lea     rax, [rsp+448h+var_98]
0x1400462b6  mov     [rsp+448h+Destination.Buffer], rax
0x1400462be  mov     dword ptr [rsp+448h+Destination.Length], 2A0000h
0x1400462c9  lea     rdx, Source; "\\Device\\RawIp"
0x1400462d0  lea     rcx, [rsp+448h+Destination]; Destination
0x1400462d8  call    cs:__imp_RtlAppendUnicodeToString
0x1400462df  nop     dword ptr [rax+rax+00h]
0x1400462e4  lea     rdx, [rbx+1Ch]; Source
0x1400462e8  lea     rcx, [rsp+448h+Destination]; Destination
0x1400462f0  call    cs:__imp_RtlAppendUnicodeToString
0x1400462f7  nop     dword ptr [rax+rax+00h]
0x1400462fc  mov     word ptr [rsp+448h+var_70], di
0x140046304  jmp     short loc_140046309
0x140046306  mov     r14b, dil
0x140046309  test    r14b, r14b
0x14004630c  jz      loc_1400463FD
0x140046312  cmp     word ptr [r13+6], 17h
0x140046318  jnz     loc_140046446
0x14004631e  cmp     word ptr [r13+4], 1Ah
0x140046324  jb      loc_140046446
0x14004632a  movups  xmm0, xmmword ptr [r13+6]
0x14004632f  movups  xmmword ptr [rsp+448h+a.u], xmm0
0x140046337  movups  xmm1, xmmword ptr [r13+12h]
0x14004633c  movups  xmmword ptr [rsp+448h+a.u+0Ch], xmm1
0x140046344  lea     rcx, [rsp+448h+a.u+8]; a
0x14004634c  call    IN6_IS_ADDR_V4MAPPED
0x140046351  test    al, al
0x140046353  jnz     short loc_14004636A
0x140046355  lea     rcx, [rsp+448h+a]; a
0x14004635d  call    IN6ADDR_ISUNSPECIFIED
0x140046362  test    al, al
0x140046364  jz      loc_1400463FD
0x14004636a  mov     [rsp+448h+Object], rdi
0x140046372  lea     rdx, [rsp+448h+Object]
0x14004637a  lea     rcx, [rsp+448h+Destination]; SourceString
0x140046382  call    AfdGetTransportInfo
0x140046387  mov     r14d, eax
0x14004638a  test    eax, eax
0x14004638c  jns     short loc_1400463A9
0x14004638e  mov     rcx, [rsp+448h+Object]
0x140046396  test    rcx, rcx
0x140046399  jz      loc_140046A42
0x14004639f  call    AfdDereferenceTransport
0x1400463a4  jmp     loc_140046A42
0x1400463a9  mov     rax, [rsi+110h]
0x1400463b0  mov     ecx, [rax+48h]
0x1400463b3  mov     rbx, [rsp+448h+Object]
0x1400463bb  cmp     [rbx+48h], ecx
0x1400463be  jnz     short loc_140046433
0x1400463c0  test    byte ptr [rsi+6], 1
0x1400463c4  jnz     short loc_140046433
0x1400463c6  mov     edx, 40h ; '@'
0x1400463cb  lea     ecx, [rdx+21h]
0x1400463ce  mov     r8d, 56646641h
0x1400463d4  call    cs:__imp_ExAllocatePool2
0x1400463db  nop     dword ptr [rax+rax+00h]
0x1400463e0  mov     [rsp+448h+var_2F8], rax
0x1400463e8  mov     [rsi+118h], rax
0x1400463ef  mov     [rax+18h], rbx
0x1400463f3  mov     dl, 1
0x1400463f5  mov     rcx, rsi
0x1400463f8  call    AfdTdiSetDualInet
0x1400463fd  mov     rcx, [rsi+110h]
0x140046404  mov     [rsp+448h+Object], rcx
0x14004640c  jmp     loc_1400464E0
0x140046411  mov     r14d, eax
0x140046414  mov     rcx, [rsp+448h+Object]
0x14004641c  call    AfdDereferenceTransport
0x140046421  xor     edi, edi
0x140046423  mov     r15d, edi
0x140046426  mov     rsi, [rsp+448h+var_398]
0x14004642e  jmp     loc_140046A42
0x140046433  mov     rcx, rbx
0x140046436  call    AfdDereferenceTransport
0x14004643b  mov     r14d, 0C00000BBh
0x140046441  jmp     loc_140046A42
0x140046446  mov     r14d, 0C0000141h
0x14004644c  jmp     loc_140046A42
0x140046451  movups  xmm0, xmmword ptr [r13+6]
0x140046456  movups  xmmword ptr [rsp+448h+a.u], xmm0
0x14004645e  movups  xmm1, xmmword ptr [r13+12h]
0x140046463  movups  xmmword ptr [rsp+448h+a.u+0Ch], xmm1
0x14004646b  mov     dword ptr [rsp+448h+var_2C8], 1
0x140046476  mov     dword ptr [rsp+448h+var_2C8+4], 2000Eh
0x140046481  mov     rax, qword ptr [rsp+448h+a.u+2]
0x140046489  mov     word ptr [rsp+448h+var_2C8+8], ax
0x140046491  lea     rcx, [rsp+448h+a.u+8]; a
0x140046499  call    IN6_IS_ADDR_V4MAPPED
0x14004649e  neg     al
0x1400464a0  sbb     ecx, ecx
0x1400464a2  mov     rax, [r13+1Ah]
0x1400464a6  and     ecx, eax
0x1400464a8  mov     dword ptr [rsp+448h+var_2C8+0Ah], ecx
0x1400464af  xor     eax, eax
0x1400464b1  mov     qword ptr [rsp+448h+var_2C8+0Eh], rax
0x1400464b9  lea     r13, [rsp+448h+var_2C8]
0x1400464c1  lea     r12d, [rax+16h]
0x1400464c5  mov     dword ptr [rsp+448h+Size], r12d
0x1400464cd  mov     rax, [rsi+118h]
0x1400464d4  mov     rax, [rax+18h]
0x1400464d8  mov     [rsp+448h+Object], rax
0x1400464e0  mov     eax, [rsi+8]
0x1400464e3  bt      eax, 9
0x1400464e7  jnb     loc_1400466B0
0x1400464ed  mov     dword ptr [rsp+448h+Destination.Length], 0D37479C1h
0x1400464f8  mov     dword ptr [rsp+448h+Destination+4], 4502A067h
0x140046503  mov     dword ptr [rsp+448h+Destination.Buffer], 0E352E8Ch
0x14004650e  mov     dword ptr [rsp+448h+Destination.Buffer+4], 0D59134F5h
0x140046519  cmp     cs:AfdTdxCallbackObject, 0
0x140046521  jnz     short loc_140046533
0x140046523  call    AfdTdxInitCallback
0x140046528  mov     r14d, eax
0x14004652b  test    eax, eax
0x14004652d  js      loc_140046A42
0x140046533  lea     rdx, [rsp+448h+EcpList]; EcpList
0x14004653b  xor     ecx, ecx; Flags
0x14004653d  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x140046544  nop     dword ptr [rax+rax+00h]
0x140046549  mov     r14d, eax
0x14004654c  test    eax, eax
0x14004654e  js      loc_140046A42
0x140046554  lea     rax, [rsp+448h+var_3C0]
0x14004655c  mov     [rsp+448h+EcpContext], rax; EcpContext
0x140046561  mov     [rsp+448h+PoolTag], 41646641h; PoolTag
0x140046569  xor     r9d, r9d; CleanupCallback
0x14004656c  xor     r8d, r8d; Flags
0x14004656f  lea     edx, [r9+10h]; SizeOfContext
0x140046573  lea     rcx, [rsp+448h+Destination]; EcpType
0x14004657b  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x140046582  nop     dword ptr [rax+rax+00h]
0x140046587  mov     r14d, eax
0x14004658a  mov     rcx, [rsp+448h+EcpList]; EcpList
0x140046592  test    eax, eax
0x140046594  js      loc_140046A36
0x14004659a  mov     rdx, [rsp+448h+var_3C0]; EcpContext
0x1400465a2  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x1400465a9  nop     dword ptr [rax+rax+00h]
0x1400465ae  mov     rax, [rsp+448h+var_3C0]
0x1400465b6  mov     [rax], rsi
0x1400465b9  mov     rax, [rsp+448h+var_3C0]
0x1400465c1  mov     [rax+8], rdi
0x1400465c5  cmp     [rsp+448h+arg_40], dil
0x1400465cd  jnz     loc_14004666C
0x1400465d3  cmp     [rsi+1F8h], rdi
0x1400465da  jnz     short loc_1400465E7
0x1400465dc  mov     r14d, 0C0000184h
0x1400465e2  jmp     loc_140046A2E
0x1400465e7  mov     ebx, [rsp+448h+arg_20]
0x1400465ee  lea     eax, [rbx-1]
0x1400465f1  test    eax, 0FFFFFFFDh
0x1400465f6  jnz     short loc_14004666C
0x1400465f8  xor     edx, edx; Val
0x1400465fa  lea     r8d, [rdx+50h]; Size
0x1400465fe  lea     rcx, [rsp+448h+var_98]; void *
0x140046606  call    memset
0x14004660b  mov     [rsp+448h+var_88], 1
0x140046616  mov     [rsp+448h+var_84], 0FFFFh
0x140046621  mov     edx, 4
0x140046626  mov     eax, edx
0x140046628  mov     ecx, 0FFFFFFFBh
0x14004662d  cmp     ebx, 3
0x140046630  cmovz   eax, ecx
0x140046633  mov     [rsp+448h+var_80], eax
0x14004663a  lea     rax, AfdTLSockOptEnable
0x140046641  mov     [rsp+448h+var_78], rax
0x140046649  mov     [rsp+448h+var_70], rdx
0x140046651  lea     rdx, [rsp+448h+var_98]
0x140046659  mov     rcx, rsi
0x14004665c  call    AfdTdiTlSyncIoControl
0x140046661  mov     r14d, eax
0x140046664  test    eax, eax
0x140046666  js      loc_140046A2E
0x14004666c  mov     dword ptr [rsp+448h+var_390+2], edi
0x140046673  mov     word ptr [rsp+448h+var_390+6], di
0x14004667b  xorps   xmm0, xmm0
0x14004667e  movdqu  [rsp+448h+var_380], xmm0
0x140046687  mov     eax, 28h ; '('
0x14004668c  mov     word ptr [rsp+448h+var_390], ax
0x140046694  mov     [rsp+448h+var_370], 1
0x1400466a0  mov     rax, [rsp+448h+EcpList]
0x1400466a8  mov     qword ptr [rsp+448h+var_390+8], rax
0x1400466b0  lea     r14d, [r12+1Ch]
0x1400466b5  cmp     r14d, 1Ch
0x1400466b9  jb      loc_140046A1E
0x1400466bf  cmp     r14d, 1F0h
0x1400466c6  ja      short loc_1400466D2
0x1400466c8  lea     rbx, [rsp+448h+P]
0x1400466d0  jmp     short loc_1400466F7
0x1400466d2  mov     edx, r14d
0x1400466d5  mov     ecx, 121h
0x1400466da  mov     r8d, 41646641h
0x1400466e0  call    cs:__imp_ExAllocatePool2
0x1400466e7  nop     dword ptr [rax+rax+00h]
0x1400466ec  mov     rbx, rax
0x1400466ef  mov     [rsp+448h+var_2F0], rax
0x1400466f7  mov     r12, rdi
0x1400466fa  mov     [rbx], edi
0x1400466fc  mov     word ptr [rbx+4], 1000h
0x140046702  mov     eax, dword ptr [rsp+448h+Size]
0x140046709  mov     [rbx+6], ax
0x14004670d  lea     rcx, [rbx+8]; void *
0x140046711  mov     r8d, 11h; Size
  ... truncated ...
```
