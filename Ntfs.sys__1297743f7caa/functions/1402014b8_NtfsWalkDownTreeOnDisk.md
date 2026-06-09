# NtfsWalkDownTreeOnDisk

- ea: `0x1402014b8`
- end: `0x140201d8f`
- name: `NtfsWalkDownTreeOnDisk`
- size: `2263`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140017480`
- `0x1402022d8`

## callees

- `0x140007ea0`
- `0x140059440`
- `0x140059740`
- `0x1402014b8`
- `0x140201da0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140201999`
- `ntoskrnl!ZwClose` at `0x140201d48`
- `ntoskrnl!ZwClose` at `0x140201d6c`
- `ntoskrnl!ZwClose` at `0x1402b34ed`
- `ntoskrnl!ZwClose` at `0x1402b353e`
- `ntoskrnl!ZwClose` at `0x140201999`
- `ntoskrnl!ZwClose` at `0x140201d48`
- `ntoskrnl!ZwClose` at `0x140201d6c`
- `ntoskrnl!ZwClose` at `0x1402b34ed`
- `ntoskrnl!ZwClose` at `0x1402b353e`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x140201b16`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x140201b16`
- `ntoskrnl!IoFileObjectType` at `0x14020156f`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14020158a`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14020158a`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x14020170e`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x14020170e`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1402017a2`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1402017a2`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402015f3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402015f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140201ca4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140201d27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140201d5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b34ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b3525`
- `ntoskrnl!ExFreePoolWithTag` at `0x140201ca4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140201d27`
- `ntoskrnl!ExFreePoolWithTag` at `0x140201d5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b34ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b3525`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140201918`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140201a6e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140201918`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140201a6e`

## pseudocode

```c
__int64 __fastcall NtfsWalkDownTreeOnDisk(
        __int64 a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        PVOID FileInformation)
{
  void *v7; // r12
  __int64 v8; // r15
  unsigned int v9; // r14d
  unsigned int v10; // esi
  int v11; // eax
  NTSTATUS v12; // ebx
  _DWORD *v13; // rdi
  __int64 v14; // rdi
  unsigned int v15; // ecx
  NTSTATUS v16; // eax
  int Information; // eax
  __int64 v18; // r14
  unsigned int v19; // eax
  int v20; // eax
  int v21; // ecx
  _QWORD *PoolWithTag; // rax
  _QWORD *v23; // rdi
  __int64 v24; // r8
  __int64 v25; // rcx
  int v26; // edx
  _DWORD *v27; // rax
  HANDLE *v29; // rdi
  char v30; // [rsp+80h] [rbp-B8h]
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-A0h] BYREF
  HANDLE Handle; // [rsp+A8h] [rbp-90h] BYREF
  _QWORD *v33; // [rsp+B0h] [rbp-88h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-70h] BYREF
  unsigned int v36; // [rsp+F8h] [rbp-40h]
  __int64 v37; // [rsp+100h] [rbp-38h]
  int v39; // [rsp+158h] [rbp+20h]
  int v40; // [rsp+160h] [rbp+28h]

  v37 = *(_QWORD *)(a1 + 104);
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  IoStatusBlock = 0;
  Handle = 0;
  v7 = 0;
  v33 = 0;
  LODWORD(v8) = 0;
  v9 = 0x10000;
  v39 = 0x10000;
  v10 = 0;
  v40 = 0;
  v11 = *(_DWORD *)(a1 + 4);
  if ( (v11 & 0x200) == 0 )
  {
    v40 = 512;
    *(_DWORD *)(a1 + 4) = v11 | 0x200;
  }
  if ( !a3 || !*(_BYTE *)(a3 + 68) )
  {
    v12 = ObOpenObjectByPointer(a2, 0x200u, 0, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Handle);
    if ( v12 < 0 )
      goto LABEL_94;
LABEL_5:
    if ( a3 && *(_BYTE *)(a3 + 68) )
    {
      v12 = -1073741536;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_94;
      v24 = 1004982;
      goto LABEL_68;
    }
    if ( (_DWORD)v8 == v10 )
    {
      PoolWithTag = ExAllocatePoolWithTag(PoolType, 8LL * (unsigned int)(v8 + 3), 0x4646744Eu);
      v23 = PoolWithTag;
      if ( !PoolWithTag )
      {
        v12 = -1073741670;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_94;
        v24 = 1005001;
LABEL_68:
        NtfsStatusTraceAndDebugInternal(0, (unsigned int)v12, v24);
        goto LABEL_94;
      }
      if ( (_DWORD)v8 )
      {
        memmove(PoolWithTag, v7, 8LL * (unsigned int)v8);
        ExFreePoolWithTag(v7, 0);
      }
      *(_OWORD *)&v23[(unsigned int)v8] = 0;
      v23[(unsigned int)v8 + 2] = 0;
      v7 = v23;
      v33 = v23;
      LODWORD(v8) = v8 + 3;
      v9 = v39;
    }
    v13 = (_DWORD *)*((_QWORD *)v7 + v10);
    if ( !v13 )
    {
      do
      {
        v27 = ExAllocatePoolWithTag(PoolType, v9, 0x4646744Eu);
        v13 = v27;
        if ( v27 )
          break;
        v9 >>= 1;
        v39 = v9;
        v36 = v9;
      }
      while ( v9 > 0x1000 );
      if ( !v27 )
      {
        v12 = -1073741670;
        if ( NtfsStatusDebugFlags )
        {
          v24 = 1005039;
          goto LABEL_68;
        }
        goto LABEL_94;
      }
      memset(v27, 0, v9);
      v13[2] = v9 - 20;
      *((_QWORD *)v7 + v10) = v13;
    }
    if ( ++v10 == 1 )
    {
      RtlInitUnicodeString(&DestinationString, 0);
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = Handle;
      ObjectAttributes.Attributes = 512;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    }
    else
    {
      v13 = (_DWORD *)*((_QWORD *)v7 + v10 - 2);
      v25 = (unsigned int)v13[4];
      DestinationString.Buffer = (PWSTR)((char *)v13 + v25 + 88);
      DestinationString.MaximumLength = *(_WORD *)((char *)v13 + v25 + 80);
      DestinationString.Length = DestinationString.MaximumLength;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = *(HANDLE *)v13;
      ObjectAttributes.Attributes = 512;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v26 = *(_DWORD *)((char *)v13 + v25 + 20);
      if ( v26 )
        v13[4] += v26;
      else
        v13[4] = v13[3];
    }
    if ( v10 != 1 )
      v12 = NtfsInheritStorageReserveId(a1, *(_QWORD *)v13, (int)&DestinationString, 4, FileInformation);
    if ( v12 < 0 )
    {
      if ( NtfsStatusDebugFlags
        && (unsigned int)v12 < 0xFFFFFFED
        && v12 != -1073741802
        && v12 != -1073741807
        && (unsigned int)(v12 + 2147483643) > 1
        && v12 != -1073741608 )
      {
        v24 = 1005126;
        goto LABEL_68;
      }
    }
    else
    {
      v12 = IoCreateFileSpecifyDeviceObjectHint(
              *((PHANDLE *)v7 + v10 - 1),
              0x100001u,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              0,
              7u,
              1u,
              0x200021u,
              0,
              0,
              CreateFileTypeNone,
              0,
              0x900u,
              *(PVOID *)(*(_QWORD *)(v37 + 248) + 8LL));
      if ( v12 >= 0 )
      {
        v30 = 0;
        while ( !a3 || !*(_BYTE *)(a3 + 68) )
        {
          v14 = *((_QWORD *)v7 + v10 - 1);
          v15 = *(_DWORD *)(v14 + 16);
          if ( v15 != *(_DWORD *)(v14 + 12) )
          {
            while ( 1 )
            {
LABEL_22:
              if ( a3 && *(_BYTE *)(a3 + 68) )
              {
                v12 = -1073741536;
                if ( !NtfsStatusDebugFlags )
                  goto LABEL_94;
                v24 = 1005272;
                goto LABEL_68;
              }
              v18 = v15;
              v19 = *(_DWORD *)(v15 + v14 + 80);
              if ( v19 > 4 || *(_WORD *)(v15 + v14 + 88) != 46 || v19 == 4 && *(_WORD *)(v15 + v14 + 90) != 46 )
              {
                v20 = *(_DWORD *)(v15 + v14 + 76);
                if ( (v20 & 0x10) != 0
                  && ((v20 & 0x400) == 0
                   || (unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(*(unsigned int *)(v15 + v14 + 84))) )
                {
                  v30 = 1;
                  goto LABEL_30;
                }
                DestinationString.Buffer = (PWSTR)(v18 + v14 + 88);
                DestinationString.MaximumLength = *(_WORD *)(v18 + v14 + 80);
                DestinationString.Length = DestinationString.MaximumLength;
                v12 = NtfsInheritStorageReserveId(a1, *(_QWORD *)v14, (int)&DestinationString, 16, FileInformation);
                if ( v12 < 0 )
                  break;
              }
              v21 = *(_DWORD *)(v18 + v14 + 20);
              if ( v21 )
                v15 = *(_DWORD *)(v14 + 16) + v21;
              else
                v15 = *(_DWORD *)(v14 + 12);
              *(_DWORD *)(v14 + 16) = v15;
              if ( !*(_DWORD *)(v18 + v14 + 20) )
                goto LABEL_30;
            }
            if ( NtfsStatusDebugFlags
              && (unsigned int)v12 < 0xFFFFFFED
              && v12 != -1073741802
              && v12 != -1073741807
              && (unsigned int)(v12 + 2147483643) > 1
              && v12 != -1073741608 )
            {
              v24 = 1005313;
              goto LABEL_68;
            }
            goto LABEL_94;
          }
          v16 = ZwQueryDirectoryFile(
                  *(HANDLE *)v14,
                  0,
                  0,
                  0,
                  &IoStatusBlock,
                  (PVOID)(v14 + 20),
                  *(_DWORD *)(v14 + 8),
                  FileFullDirectoryInformation,
                  0,
                  0,
                  0);
          v12 = v16;
          if ( v16 == -1073741809 || v16 == -2147483642 )
            v12 = 0;
          if ( v12 < 0 )
            goto LABEL_94;
          *(_DWORD *)(v14 + 12) = IoStatusBlock.Information;
          Information = IoStatusBlock.Information;
          *(_DWORD *)(v14 + 16) = 0;
          v15 = 0;
          if ( Information )
            goto LABEL_22;
          ZwClose(*(HANDLE *)v14);
          *(_QWORD *)v14 = 0;
          --v10;
LABEL_30:
          if ( !v10 )
            goto LABEL_94;
          if ( v30 )
          {
            v9 = v39;
            goto LABEL_5;
          }
        }
        v12 = -1073741536;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_94;
        v24 = 1005173;
        goto LABEL_68;
      }
      if ( NtfsStatusDebugFlags
        && (unsigned int)v12 < 0xFFFFFFED
        && v12 != -1073741802
        && v12 != -1073741807
        && (unsigned int)(v12 + 2147483643) > 1
        && v12 != -1073741608 )
      {
        v24 = 1005159;
        goto LABEL_68;
      }
    }
    goto LABEL_94;
  }
  v12 = -1073741536;
  if ( NtfsStatusDebugFlags )
  {
    v24 = 1004957;
    goto LABEL_68;
  }
LABEL_94:
  while ( (_DWORD)v8 )
  {
    v8 = (unsigned int)(v8 - 1);
    v29 = (HANDLE *)*((_QWORD *)v7 + v8);
    if ( v29 )
    {
      if ( *v29 )
        ZwClose(*v29);
      ExFreePoolWithTag(v29, 0);
    }
  }
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  if ( Handle )
    ZwClose(Handle);
  if ( v40 )
    *(_DWORD *)(a1 + 4) &= ~v40;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1402014b8  mov     r11, rsp
0x1402014bb  mov     [r11+10h], rbx
0x1402014bf  mov     [r11+18h], rsi
0x1402014c3  mov     [r11+20h], r9d
0x1402014c7  mov     [r11+8], rcx
0x1402014cb  push    rdi
0x1402014cc  push    r12
0x1402014ce  push    r13
0x1402014d0  push    r14
0x1402014d2  push    r15
0x1402014d4  sub     rsp, 110h
0x1402014db  mov     r13, r8
0x1402014de  mov     r10, rdx
0x1402014e1  mov     rax, [rcx+68h]
0x1402014e5  mov     [rsp+138h+var_38], rax
0x1402014ed  xorps   xmm0, xmm0
0x1402014f0  movups  xmmword ptr [r11-70h], xmm0
0x1402014f5  movups  xmmword ptr [r11-60h], xmm0
0x1402014fa  movups  xmmword ptr [r11-54h], xmm0
0x1402014ff  movups  xmmword ptr [rsp+138h+DestinationString.Length], xmm0
0x140201507  xorps   xmm1, xmm1
0x14020150a  movups  xmmword ptr [r11-80h], xmm1
0x14020150f  xor     r8d, r8d
0x140201512  mov     [r11-90h], r8
0x140201519  mov     r12d, r8d
0x14020151c  mov     [r11-88h], r8
0x140201523  mov     r15d, r8d
0x140201526  mov     [r11-0ACh], r8d
0x14020152d  mov     r14d, 10000h
0x140201533  mov     [r11+20h], r14d
0x140201537  mov     esi, r8d
0x14020153a  mov     [rsp+138h+arg_20], r8d
0x140201542  mov     eax, [rcx+4]
0x140201545  mov     r11d, 200h
0x14020154b  test    r11d, eax
0x14020154e  jz      loc_140201D35
0x140201554  test    r13, r13
0x140201557  jnz     loc_140201C7E
0x14020155d  lea     rax, [rsp+138h+var_90]
0x140201565  mov     [rsp+138h+Handle], rax; Handle
0x14020156a  mov     [rsp+138h+AccessMode], r8b; AccessMode
0x14020156f  mov     rax, cs:__imp_IoFileObjectType
0x140201576  mov     rcx, [rax]
0x140201579  mov     [rsp+138h+ObjectType], rcx; ObjectType
0x14020157e  xor     r9d, r9d; DesiredAccess
0x140201581  xor     r8d, r8d; PassedAccessState
0x140201584  mov     edx, r11d; HandleAttributes
0x140201587  mov     rcx, r10; Object
0x14020158a  call    cs:__imp_ObOpenObjectByPointer
0x140201591  nop     dword ptr [rax+rax+00h]
0x140201596  mov     ebx, eax
0x140201598  mov     [rsp+138h+var_B4], eax
0x14020159f  test    eax, eax
0x1402015a1  js      loc_140201CC0
0x1402015a7  test    r13, r13
0x1402015aa  jnz     loc_14020196D
0x1402015b0  cmp     r15d, esi
0x1402015b3  jz      loc_140201901
0x1402015b9  mov     eax, esi
0x1402015bb  mov     rdi, [r12+rax*8]
0x1402015bf  mov     [rsp+138h+var_A8], rdi
0x1402015c7  test    rdi, rdi
0x1402015ca  jz      loc_140201A5F
0x1402015d0  mov     r14d, 1
0x1402015d6  add     esi, r14d
0x1402015d9  mov     [rsp+138h+var_B0], esi
0x1402015e0  cmp     esi, r14d
0x1402015e3  jnz     loc_1402019D3
0x1402015e9  xor     edx, edx; SourceString
0x1402015eb  lea     rcx, [rsp+138h+DestinationString]; DestinationString
0x1402015f3  call    cs:__imp_RtlInitUnicodeString
0x1402015fa  nop     dword ptr [rax+rax+00h]
0x1402015ff  mov     [rsp+138h+ObjectAttributes.Length], 30h ; '0'
0x14020160a  mov     rax, [rsp+138h+var_90]
0x140201612  mov     [rsp+138h+ObjectAttributes.RootDirectory], rax
0x14020161a  mov     [rsp+138h+ObjectAttributes.Attributes], 200h
0x140201625  lea     rax, [rsp+138h+DestinationString]
0x14020162d  mov     [rsp+138h+ObjectAttributes.ObjectName], rax
0x140201635  xorps   xmm0, xmm0
0x140201638  movdqu  xmmword ptr [rsp+138h+ObjectAttributes.SecurityDescriptor], xmm0
0x140201641  cmp     esi, r14d
0x140201644  jz      short loc_14020167A
0x140201646  mov     rax, [rsp+138h+FileInformation]
0x14020164e  mov     [rsp+138h+ObjectType], rax; FileInformation
0x140201653  mov     r9d, 4; int
0x140201659  lea     r8, [rsp+138h+DestinationString]; int
0x140201661  mov     rdx, [rdi]; int
0x140201664  mov     rcx, qword ptr [rsp+138h+arg_0]; int
0x14020166c  call    NtfsInheritStorageReserveId
0x140201671  mov     ebx, eax
0x140201673  mov     [rsp+138h+var_B4], eax
0x14020167a  test    ebx, ebx
0x14020167c  js      loc_140201C41
0x140201682  lea     eax, [rsi-1]
0x140201685  mov     rcx, [r12+rax*8]; FileHandle
0x140201689  mov     [rsp+138h+var_A8], rcx
0x140201691  mov     rax, [rsp+138h+var_38]
0x140201699  mov     rax, [rax+0F8h]
0x1402016a0  mov     rdx, [rax+8]
0x1402016a4  mov     [rsp+138h+DeviceObject], rdx; DeviceObject
0x1402016a9  mov     [rsp+138h+Options], 900h; Options
0x1402016b1  mov     [rsp+138h+InternalParameters], 0; InternalParameters
0x1402016ba  mov     [rsp+138h+CreateFileType], 0; CreateFileType
0x1402016c2  mov     [rsp+138h+EaLength], 0; EaLength
0x1402016ca  mov     [rsp+138h+EaBuffer], 0; EaBuffer
0x1402016d3  mov     [rsp+138h+CreateOptions], 200021h; CreateOptions
0x1402016db  mov     [rsp+138h+Disposition], r14d; Disposition
0x1402016e0  mov     dword ptr [rsp+138h+Handle], 7; ShareAccess
0x1402016e8  mov     dword ptr [rsp+138h+AccessMode], 0; FileAttributes
0x1402016f0  mov     [rsp+138h+ObjectType], 0; AllocationSize
0x1402016f9  lea     r9, [rsp+138h+IoStatusBlock]; IoStatusBlock
0x140201701  lea     r8, [rsp+138h+ObjectAttributes]; ObjectAttributes
0x140201709  mov     edx, 100001h; DesiredAccess
0x14020170e  call    cs:__imp_IoCreateFileSpecifyDeviceObjectHint
0x140201715  nop     dword ptr [rax+rax+00h]
0x14020171a  mov     ebx, eax
0x14020171c  mov     [rsp+138h+var_B4], eax
0x140201723  test    eax, eax
0x140201725  js      loc_140201BEC
0x14020172b  mov     [rsp+138h+var_B8], 0
0x140201733  test    r13, r13
0x140201736  jz      short loc_140201743
0x140201738  cmp     byte ptr [r13+44h], 0
0x14020173d  jnz     loc_140201BBB
0x140201743  lea     r14d, [rsi-1]
0x140201747  mov     rdi, [r12+r14*8]
0x14020174b  mov     [rsp+138h+var_A8], rdi
0x140201753  mov     ecx, [rdi+10h]
0x140201756  cmp     ecx, [rdi+0Ch]
0x140201759  jnz     loc_1402017F9
0x14020175f  lea     rcx, [rdi+14h]
0x140201763  mov     byte ptr [rsp+138h+EaLength], 0; RestartScan
0x140201768  mov     [rsp+138h+EaBuffer], 0; FileName
0x140201771  mov     byte ptr [rsp+138h+CreateOptions], 0; ReturnSingleEntry
0x140201776  mov     [rsp+138h+Disposition], 2; FileInformationClass
0x14020177e  mov     eax, [rdi+8]
0x140201781  mov     dword ptr [rsp+138h+Handle], eax; Length
0x140201785  mov     qword ptr [rsp+138h+AccessMode], rcx; FileInformation
0x14020178a  lea     rax, [rsp+138h+IoStatusBlock]
0x140201792  mov     [rsp+138h+ObjectType], rax; IoStatusBlock
0x140201797  xor     r9d, r9d; ApcContext
0x14020179a  xor     r8d, r8d; ApcRoutine
0x14020179d  xor     edx, edx; Event
0x14020179f  mov     rcx, [rdi]; FileHandle
0x1402017a2  call    cs:__imp_ZwQueryDirectoryFile
0x1402017a9  nop     dword ptr [rax+rax+00h]
0x1402017ae  mov     ebx, eax
0x1402017b0  mov     [rsp+138h+var_B4], eax
0x1402017b7  cmp     eax, 0C000000Fh
0x1402017bc  jz      loc_1402018F3
0x1402017c2  cmp     eax, 80000006h
0x1402017c7  jz      loc_1402018F3
0x1402017cd  test    ebx, ebx
0x1402017cf  js      loc_140201CC0
0x1402017d5  mov     rax, [rsp+138h+IoStatusBlock.Information]
0x1402017dd  mov     [rdi+0Ch], eax
0x1402017e0  mov     rax, [rsp+138h+IoStatusBlock.Information]
0x1402017e8  mov     dword ptr [rdi+10h], 0
0x1402017ef  xor     ecx, ecx
0x1402017f1  test    eax, eax
0x1402017f3  jz      loc_140201996
0x1402017f9  test    r13, r13
0x1402017fc  jz      short loc_140201809
0x1402017fe  cmp     byte ptr [r13+44h], 0
0x140201803  jnz     loc_140201AFA
0x140201809  mov     r14d, ecx
0x14020180c  mov     eax, [r14+rdi+50h]
0x140201811  cmp     eax, 4
0x140201814  jbe     loc_1402018D3
0x14020181a  mov     eax, [r14+rdi+4Ch]
0x14020181f  test    al, 10h
0x140201821  jnz     loc_1402019BC
0x140201827  lea     rax, [rdi+58h]
0x14020182b  add     rax, r14
0x14020182e  mov     [rsp+138h+DestinationString.Buffer], rax
0x140201836  movzx   eax, word ptr [r14+rdi+50h]
0x14020183c  mov     [rsp+138h+DestinationString.MaximumLength], ax
0x140201844  mov     [rsp+138h+DestinationString.Length], ax
0x14020184c  mov     rax, [rsp+138h+FileInformation]
0x140201854  mov     [rsp+138h+ObjectType], rax; FileInformation
0x140201859  mov     r9d, 10h; int
0x14020185f  lea     r8, [rsp+138h+DestinationString]; int
0x140201867  mov     rdx, [rdi]; int
0x14020186a  mov     rcx, qword ptr [rsp+138h+arg_0]; int
0x140201872  call    NtfsInheritStorageReserveId
0x140201877  mov     ebx, eax
0x140201879  mov     [rsp+138h+var_B4], eax
0x140201880  test    eax, eax
0x140201882  js      loc_140201BD9
0x140201888  mov     ecx, [r14+rdi+14h]
0x14020188d  test    ecx, ecx
0x14020188f  jz      short loc_1402018CE
0x140201891  add     ecx, [rdi+10h]
0x140201894  mov     [rdi+10h], ecx
0x140201897  cmp     dword ptr [r14+rdi+14h], 0
0x14020189d  jnz     loc_1402017F9
0x1402018a3  test    esi, esi
0x1402018a5  jz      loc_140201CC0
0x1402018ab  cmp     [rsp+138h+var_B8], 0
0x1402018b3  jz      loc_140201733
0x1402018b9  test    esi, esi
0x1402018bb  jz      loc_140201CC0
0x1402018c1  mov     r14d, [rsp+138h+arg_18]
0x1402018c9  jmp     loc_1402015A7
0x1402018ce  mov     ecx, [rdi+0Ch]
0x1402018d1  jmp     short loc_140201894
0x1402018d3  cmp     word ptr [r14+rdi+58h], 2Eh ; '.'
0x1402018da  jnz     loc_14020181A
0x1402018e0  cmp     eax, 4
0x1402018e3  jnz     short loc_140201888
0x1402018e5  cmp     word ptr [r14+rdi+5Ah], 2Eh ; '.'
0x1402018ec  jz      short loc_140201888
0x1402018ee  jmp     loc_14020181A
0x1402018f3  xor     ebx, ebx
0x1402018f5  mov     [rsp+138h+var_B4], ebx
0x1402018fc  jmp     loc_1402017CD
0x140201901  mov     ecx, cs:PoolType; PoolType
0x140201907  lea     r14d, [r15+3]
0x14020190b  mov     edx, r14d
0x14020190e  shl     rdx, 3; NumberOfBytes
0x140201912  mov     r8d, 4646744Eh; Tag
0x140201918  call    cs:__imp_ExAllocatePoolWithTag
0x14020191f  nop     dword ptr [rax+rax+00h]
0x140201924  mov     rdi, rax
0x140201927  test    rax, rax
0x14020192a  jz      loc_140201ACE
0x140201930  test    r15d, r15d
0x140201933  jnz     loc_140201C8D
0x140201939  mov     eax, r15d
0x14020193c  xorps   xmm0, xmm0
0x14020193f  xor     ecx, ecx
0x140201941  movups  xmmword ptr [rdi+rax*8], xmm0
0x140201945  mov     [rdi+rax*8+10h], rcx
0x14020194a  mov     r12, rdi
0x14020194d  mov     [rsp+138h+var_88], rdi
0x140201955  mov     r15d, r14d
0x140201958  mov     [rsp+138h+var_AC], r14d
0x140201960  mov     r14d, [rsp+138h+arg_18]
0x140201968  jmp     loc_1402015B9
0x14020196d  cmp     byte ptr [r13+44h], 0
0x140201972  jz      loc_1402015B0
0x140201978  mov     al, cs:NtfsStatusDebugFlags
0x14020197e  mov     ebx, 0C0000120h
0x140201983  test    al, al
0x140201985  jz      loc_140201ADD
0x14020198b  mov     r8d, 0F55B6h
0x140201991  jmp     loc_140201AEF
0x140201996  mov     rcx, [rdi]; Handle
0x140201999  call    cs:__imp_ZwClose
0x1402019a0  nop     dword ptr [rax+rax+00h]
0x1402019a5  mov     qword ptr [rdi], 0
0x1402019ac  mov     esi, r14d
0x1402019af  mov     [rsp+138h+var_B0], r14d
0x1402019b7  jmp     loc_1402018A3
0x1402019bc  bt      eax, 0Ah
0x1402019c0  jb      loc_140201B11
0x1402019c6  mov     [rsp+138h+var_B8], 1
0x1402019ce  jmp     loc_1402018A3
0x1402019d3  lea     eax, [rsi-2]
0x1402019d6  mov     rdi, [r12+rax*8]
0x1402019da  mov     [rsp+138h+var_A8], rdi
0x1402019e2  mov     ecx, [rdi+10h]
0x1402019e5  lea     rax, [rdi+58h]
0x1402019e9  add     rax, rcx
0x1402019ec  mov     [rsp+138h+DestinationString.Buffer], rax
0x1402019f4  movzx   eax, word ptr [rcx+rdi+50h]
0x1402019f9  mov     [rsp+138h+DestinationString.MaximumLength], ax
0x140201a01  mov     [rsp+138h+DestinationString.Length], ax
0x140201a09  mov     [rsp+138h+ObjectAttributes.Length], 30h ; '0'
0x140201a14  mov     rax, [rdi]
0x140201a17  mov     [rsp+138h+ObjectAttributes.RootDirectory], rax
0x140201a1f  mov     [rsp+138h+ObjectAttributes.Attributes], 200h
0x140201a2a  lea     rax, [rsp+138h+DestinationString]
0x140201a32  mov     [rsp+138h+ObjectAttributes.ObjectName], rax
0x140201a3a  xorps   xmm0, xmm0
0x140201a3d  movdqu  xmmword ptr [rsp+138h+ObjectAttributes.SecurityDescriptor], xmm0
0x140201a46  mov     edx, [rcx+rdi+14h]
0x140201a4a  test    edx, edx
0x140201a4c  jz      loc_140201CB5
0x140201a52  mov     ecx, [rdi+10h]
0x140201a55  add     ecx, edx
0x140201a57  mov     [rdi+10h], ecx
0x140201a5a  jmp     loc_140201641
0x140201a5f  mov     ecx, cs:PoolType; PoolType
0x140201a65  mov     edx, r14d; NumberOfBytes
0x140201a68  mov     r8d, 4646744Eh; Tag
0x140201a6e  call    cs:__imp_ExAllocatePoolWithTag
0x140201a75  nop     dword ptr [rax+rax+00h]
0x140201a7a  mov     rdi, rax
0x140201a7d  mov     [rsp+138h+var_A8], rax
0x140201a85  test    rax, rax
0x140201a88  jnz     short loc_140201AA6
0x140201a8a  shr     r14d, 1
0x140201a8d  mov     [rsp+138h+arg_18], r14d
0x140201a95  mov     [rsp+138h+var_40], r14d
0x140201a9d  cmp     r14d, 1000h
0x140201aa4  ja      short loc_140201A5F
0x140201aa6  test    rdi, rdi
0x140201aa9  jz      loc_140201B9D
0x140201aaf  mov     r8d, r14d; Size
  ... truncated ...
```
