# CreateFileInternal

- ea: `0x18004873c`
- end: `0x180048f1f`
- name: `CreateFileInternal`
- size: `2019`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, __int64, int)`
- caller_count: `11`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180045ec0`
- `0x180047580`
- `0x1800481f0`
- `0x1800486a0`
- `0x180048ff0`
- `0x180049380`
- `0x180077bd0`
- `0x18009ce5c`
- `0x1800dfdc0`
- `0x1800e49d0`
- `0x18017fb90`

## callees

- `0x1800134a0`
- `0x18004873c`
- `0x1800edeec`
- `0x1801113e8`
- `0x18017fbb8`
- `0x180181c30`
- `0x180181d44`
- `0x180188f10`
- `0x180197010`

## import_xrefs

- `ntdll!RtlReleaseRelativeName` at `0x180048e55`
- `ntdll!RtlReleaseRelativeName` at `0x180048e55`
- `ntdll!NtQueryInformationFile` at `0x180048a2f`
- `ntdll!NtQueryInformationFile` at `0x180048a2f`
- `ntdll!SbSelectProcedure` at `0x180048c75`
- `ntdll!SbSelectProcedure` at `0x180048c75`
- `ntdll!NtSetInformationFile` at `0x180048de9`
- `ntdll!NtSetInformationFile` at `0x180048e2a`
- `ntdll!NtSetInformationFile` at `0x180048de9`
- `ntdll!NtSetInformationFile` at `0x180048e2a`
- `ntdll!NtCreateFile` at `0x180048d10`
- `ntdll!NtCreateFile` at `0x180048d7d`
- `ntdll!NtCreateFile` at `0x180048d10`
- `ntdll!NtCreateFile` at `0x180048d7d`
- `ntdll!RtlSetLastWin32Error` at `0x180048816`
- `ntdll!RtlSetLastWin32Error` at `0x1800488f0`
- `ntdll!RtlSetLastWin32Error` at `0x180048e38`
- `ntdll!RtlSetLastWin32Error` at `0x180048eed`
- `ntdll!RtlSetLastWin32Error` at `0x180048816`
- `ntdll!RtlSetLastWin32Error` at `0x1800488f0`
- `ntdll!RtlSetLastWin32Error` at `0x180048e38`
- `ntdll!RtlSetLastWin32Error` at `0x180048eed`
- `ntdll!NtQueryEaFile` at `0x180048b9b`
- `ntdll!NtQueryEaFile` at `0x180048b9b`
- `ntdll!RtlInitUnicodeStringEx` at `0x180048885`
- `ntdll!RtlInitUnicodeStringEx` at `0x180048885`
- `ntdll!NtClose` at `0x180048df4`
- `ntdll!NtClose` at `0x180048e48`
- `ntdll!NtClose` at `0x180048df4`
- `ntdll!NtClose` at `0x180048e48`
- `ntdll!RtlFreeHeap` at `0x180048bba`
- `ntdll!RtlFreeHeap` at `0x180048e6e`
- `ntdll!RtlFreeHeap` at `0x180048e8b`
- `ntdll!RtlFreeHeap` at `0x180048bba`
- `ntdll!RtlFreeHeap` at `0x180048e6e`
- `ntdll!RtlFreeHeap` at `0x180048e8b`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800488d1`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x1800488d1`
- `ntdll!RtlAllocateHeap` at `0x180048b62`
- `ntdll!RtlAllocateHeap` at `0x180048b62`

## pseudocode

```c
__int64 __fastcall CreateFileInternal(PCWSTR SourceString, int a2, ULONG a3, int a4, __int64 a5, char a6)
{
  int v7; // esi
  unsigned int v8; // edi
  ULONG v10; // r12d
  NTSTATUS inited; // eax
  HANDLE ContainingDirectory; // rax
  int v13; // r14d
  int v14; // edx
  int v15; // esi
  unsigned int v16; // ecx
  __int64 v17; // rcx
  void *EaBuffer; // rsi
  ULONG EaLength; // r13d
  char *v20; // rcx
  ULONG v21; // r14d
  int IsEnabledDeviceUsageNoInline; // eax
  ULONG v23; // r8d
  ULONG v24; // r8d
  int v25; // r15d
  PVOID Heap; // rax
  NTSTATUS v27; // r15d
  NTSTATUS v28; // ebx
  __int64 ProcessSwitchContext; // rax
  BOOL v30; // edi
  void (__fastcall *v31)(ULONG *); // rax
  ACCESS_MASK v32; // r14d
  ULONG v33; // eax
  int v34; // eax
  ULONG v35; // ecx
  ULONG v36; // ecx
  bool v37; // [rsp+60h] [rbp-A0h]
  ULONG CreateOptions; // [rsp+64h] [rbp-9Ch] BYREF
  HANDLE FileHandle; // [rsp+68h] [rbp-98h] BYREF
  ULONG FileAttributes; // [rsp+70h] [rbp-90h]
  int v41; // [rsp+74h] [rbp-8Ch] BYREF
  int v42; // [rsp+78h] [rbp-88h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  ULONG FileInformation; // [rsp+90h] [rbp-70h] BYREF
  int v45; // [rsp+94h] [rbp-6Ch]
  ULONG ShareAccess; // [rsp+98h] [rbp-68h]
  int v47; // [rsp+9Ch] [rbp-64h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v49; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE Handle; // [rsp+B8h] [rbp-48h] BYREF
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+C0h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E0h] [rbp-20h] BYREF
  PVOID P; // [rsp+110h] [rbp+10h]
  __int64 v54; // [rsp+118h] [rbp+18h] BYREF
  int v55; // [rsp+120h] [rbp+20h]
  int v56; // [rsp+198h] [rbp+98h]

  v41 = a4;
  ShareAccess = a3;
  v42 = a2;
  CreateOptions = 0;
  v49 = 0;
  FileInformation = 0;
  v54 = 0;
  v55 = 0;
  FileHandle = (HANDLE)-1LL;
  Handle = (HANDLE)-1LL;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  if ( a5 )
  {
    if ( *(_DWORD *)a5 < 0x20u )
    {
LABEL_19:
      BaseSetLastNTError(3221225485LL);
      return -1;
    }
    v7 = *(_DWORD *)(a5 + 12);
    v8 = *(_DWORD *)(a5 + 8);
    FileAttributes = *(_DWORD *)(a5 + 4);
  }
  else
  {
    v7 = 0;
    FileAttributes = 0;
    v8 = 0;
  }
  if ( (a6 & 3) != 0 )
  {
    v37 = 0;
  }
  else
  {
    v37 = (v8 & 0x10000) != 0;
    if ( (v8 & 0x10000) != 0 )
    {
      if ( !a2 || (a3 & 4) != 0 )
      {
        RtlSetLastWin32Error(0xA0u);
        return -1;
      }
    }
    else
    {
      v37 = 0;
    }
  }
  if ( a4 == 1 )
  {
    v10 = 2;
  }
  else if ( a4 == 2 )
  {
    v10 = 5;
  }
  else
  {
    if ( a4 != 3 )
    {
      if ( a4 == 4 )
      {
        v10 = 3;
        goto LABEL_24;
      }
      if ( a4 != 5 || (a2 & 0x40000000) == 0 )
        goto LABEL_19;
    }
    v10 = 1;
  }
LABEL_24:
  inited = RtlInitUnicodeStringEx(&DestinationString, SourceString);
  if ( inited < 0 )
    goto LABEL_25;
  if ( DestinationString.Length <= 1u
    || (v47 = 1, SourceString[((unsigned __int64)DestinationString.Length >> 1) - 1] != 92) )
  {
    v47 = 0;
  }
  CreateOptions = 0;
  inited = RtlDosPathNameToRelativeNtPathName_U_WithStatus(SourceString, &DestinationString, 0, &RelativeName);
  if ( inited < 0 )
  {
    if ( inited != -1073741801 && inited != -1073741670 )
    {
      RtlSetLastWin32Error(3u);
      return -1;
    }
LABEL_25:
    BaseSetLastNTError((unsigned int)inited);
    return -1;
  }
  P = DestinationString.Buffer;
  if ( RelativeName.RelativeName.Length )
  {
    DestinationString = RelativeName.RelativeName;
    ContainingDirectory = RelativeName.ContainingDirectory;
  }
  else
  {
    ContainingDirectory = 0;
    RelativeName.ContainingDirectory = 0;
  }
  ObjectAttributes.RootDirectory = ContainingDirectory;
  v13 = v8 & 0x1000000;
  ObjectAttributes.Length = 48;
  v45 = v8 & 0x1000000;
  ObjectAttributes.SecurityDescriptor = 0;
  v14 = (v8 >> 6) & 0x800;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = v14 | ((v8 & 0x1000000) == 0 ? 0x40 : 0);
  if ( (v7 & 0x100000) != 0 )
  {
    v15 = v7 & 0xF0000;
    LOBYTE(v55) = (v15 & 0x40000) != 0;
    v16 = v15 & 0xFFFBFFFF;
    if ( (v15 & 0x40000) == 0 )
      v16 = v15;
    if ( (v16 & 0x80000) != 0 )
    {
      BYTE1(v55) = 1;
      v16 &= ~0x80000u;
    }
    else
    {
      BYTE1(v55) = 0;
    }
    HIDWORD(v54) = HIWORD(v16);
  }
  else
  {
    LOWORD(v55) = 257;
    HIDWORD(v54) = 2;
  }
  LODWORD(v54) = 12;
  ObjectAttributes.SecurityQualityOfService = &v54;
  if ( a5
    && (v17 = *(_QWORD *)(a5 + 16)) != 0
    && (ObjectAttributes.SecurityDescriptor = *(PVOID *)(v17 + 8), *(_DWORD *)(v17 + 16)) )
  {
    EaBuffer = 0;
    EaLength = 0;
    ObjectAttributes.Attributes = v14 | (v13 != 0 ? 2 : 66);
  }
  else
  {
    EaBuffer = 0;
    EaLength = 0;
    if ( !a5 )
      goto LABEL_54;
  }
  v20 = *(char **)(a5 + 24);
  if ( (unsigned __int64)(v20 - 1) > 0xFFFFFFFFFFFFFFFDuLL
    || NtQueryInformationFile(v20, &IoStatusBlock, &FileInformation, 4u, FileEaInformation) < 0 )
  {
LABEL_54:
    IsEnabledDeviceUsageNoInline = Feature_TimestampsOnCreate__private_IsEnabledDeviceUsageNoInline();
    v23 = CreateOptions;
    if ( IsEnabledDeviceUsageNoInline )
      v23 = ((v8 & 0x8000) << 14) | CreateOptions;
    v24 = ((v8 & 0x2000000) != 0 ? 0x4000 : 0)
        | ~(v8 >> 25) & 0x20
        | ((int)v8 >> 31) & 2
        | ((v8 & 0x40000
          | ((v8 & 0x800000 | ((v8 & 0x10000000 | ((v8 & 0x8000000 | (v8 >> 1) & 0x10000000) >> 8)) >> 12)) >> 3)) >> 2)
        | v23;
    CreateOptions = v24;
    if ( (NtCurrentTeb()->SameTebFlags & 0x800) != 0 )
    {
      v24 |= 0x40000u;
      CreateOptions = v24;
    }
    v25 = v8 & 0x4000000;
    if ( (v8 & 0x4000000) != 0 )
    {
      v24 |= 0x1000u;
      v42 |= 0x10000u;
      CreateOptions = v24;
    }
    if ( (v8 & 0x200000) != 0 )
    {
      v24 |= 0x200000u;
      CreateOptions = v24;
    }
    if ( (v8 & 0x100000) != 0 )
    {
      v24 |= 0x400000u;
      CreateOptions = v24;
    }
    if ( (v8 & 0x2000000) != 0 )
    {
      if ( (FileAttributes & 0x10) == 0 || !v13 || v10 != 2 )
      {
LABEL_79:
        v56 = a6 & 2;
        if ( v56 )
        {
          CreateOptions = v24 | 0x20000;
          ProcessSwitchContext = SbGetProcessSwitchContext(NtCurrentPeb()->pShimData);
          if ( ProcessSwitchContext )
            ProcessSwitchContext = *(_QWORD *)(ProcessSwitchContext + 24);
          v30 = ProcessSwitchContext == 0x6000200000000LL;
        }
        else
        {
          v30 = 0;
          v31 = (void (__fastcall *)(ULONG *))SbSelectProcedure(2880154539LL, 1, "kLsE");
          if ( v31 )
            v31(&CreateOptions);
        }
        if ( v37 && ((v41 - 1) & 0xFFFFFFFC) == 0 && v41 != 3 )
        {
          v28 = BasepOpenParentDirectoryNoRedirection(&DestinationString, &Handle);
          if ( v28 < 0 )
            goto LABEL_109;
        }
        v32 = v42 | 0x100080;
        FileAttributes &= 0xDAFFA7u;
        v28 = NtCreateFile(
                &FileHandle,
                v42 | 0x100080,
                &ObjectAttributes,
                &IoStatusBlock,
                0,
                FileAttributes,
                ShareAccess,
                v10,
                CreateOptions,
                EaBuffer,
                EaLength);
        if ( v28 == -1073741790 )
        {
          if ( !v30 && v56 )
            goto LABEL_96;
          v33 = CreateOptions;
          if ( (CreateOptions & 0x20000) == 0 || (ShareAccess & 1) != 0 )
            goto LABEL_96;
          CreateOptions &= ~0x20000u;
          v28 = NtCreateFile(
                  &FileHandle,
                  v32,
                  &ObjectAttributes,
                  &IoStatusBlock,
                  0,
                  FileAttributes,
                  ShareAccess,
                  v10,
                  v33 & 0xFFFDFFFF,
                  EaBuffer,
                  EaLength);
        }
        if ( v28 < 0 )
        {
LABEL_96:
          FileHandle = (HANDLE)-1LL;
          goto LABEL_109;
        }
        if ( v37 )
        {
          v34 = (CreateOptions & 1) != 0
              ? BasepGetDirectoryRedirectionStatus(DestinationString.Buffer, FileHandle)
              : BasepGetFileRedirectionStatus(DestinationString.Buffer, FileHandle);
          v28 = v34;
          if ( v34 < 0 )
          {
            if ( v25 )
            {
              v41 = 8;
              NtSetInformationFile(FileHandle, &IoStatusBlock, &v41, 4u, (FILE_INFORMATION_CLASS)64);
            }
            goto LABEL_104;
          }
        }
        if ( v41 == 5 )
        {
          v49 = 0;
          v28 = NtSetInformationFile(FileHandle, &IoStatusBlock, &v49, 8u, FileAllocationInformation);
          if ( v28 < 0 )
          {
LABEL_104:
            NtClose(FileHandle);
            goto LABEL_96;
          }
        }
        else if ( v41 == 2 && IoStatusBlock.Information == 3 || v41 == 4 && IoStatusBlock.Information == 1 )
        {
          v35 = 183;
          goto LABEL_108;
        }
        v35 = 0;
LABEL_108:
        RtlSetLastWin32Error(v35);
LABEL_109:
        if ( Handle != (HANDLE)-1LL )
          NtClose(Handle);
        goto LABEL_111;
      }
      v24 |= 1u;
    }
    else
    {
      v24 |= 0x40u;
    }
    CreateOptions = v24;
    goto LABEL_79;
  }
  v21 = FileInformation;
  if ( !FileInformation )
  {
LABEL_53:
    v13 = v45;
    goto LABEL_54;
  }
  while ( 1 )
  {
    v21 *= 2;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v21);
    EaBuffer = Heap;
    if ( !Heap )
      break;
    v27 = NtQueryEaFile(*(HANDLE *)(a5 + 24), &IoStatusBlock, Heap, v21, 0, 0, 0, 0, 1u);
    if ( v27 >= 0 )
    {
      EaLength = IoStatusBlock.Information;
    }
    else
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, EaBuffer);
      EaBuffer = 0;
      EaLength = 0;
      IoStatusBlock.Information = 0;
    }
    if ( v27 != -2147483643 && v27 != -1073741789 )
      goto LABEL_53;
  }
  v28 = -1073741801;
LABEL_111:
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( EaBuffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, EaBuffer);
  if ( v28 >= 0 )
    return (__int64)FileHandle;
  BaseSetLastNTError((unsigned int)v28);
  if ( v28 == -1073741771 )
  {
    v36 = 80;
LABEL_124:
    RtlSetLastWin32Error(v36);
    return (__int64)FileHandle;
  }
  if ( v28 == -1073741638 )
  {
    v36 = 3;
    if ( !v47 )
      v36 = 5;
    goto LABEL_124;
  }
  return (__int64)FileHandle;
}

```

## disassembly

```asm
0x18004873c  mov     [rsp-8+arg_18], rbx
0x180048741  push    rbp
0x180048742  push    rsi
0x180048743  push    rdi
0x180048744  push    r12
0x180048746  push    r13
0x180048748  push    r14
0x18004874a  push    r15
0x18004874c  lea     rbp, [rsp-30h]
0x180048751  sub     rsp, 130h
0x180048758  mov     rax, cs:__security_cookie
0x18004875f  xor     rax, rsp
0x180048762  mov     [rbp+60h+var_38], rax
0x180048766  mov     rbx, [rbp+60h+arg_20]
0x18004876d  xorps   xmm0, xmm0
0x180048770  xor     r15d, r15d
0x180048773  mov     [rsp+160h+var_EC], r9d
0x180048778  xor     eax, eax
0x18004877a  mov     [rbp+60h+ShareAccess], r8d
0x18004877e  or      r12, 0FFFFFFFFFFFFFFFFh
0x180048782  mov     [rsp+160h+var_E8], edx
0x180048786  mov     [rsp+160h+CreateOptions], r15d
0x18004878b  xorps   xmm1, xmm1
0x18004878e  mov     [rbp+60h+var_B0], r15
0x180048792  mov     r14, rcx
0x180048795  mov     [rbp+60h+FileInformation], r15d
0x180048799  mov     [rbp+60h+var_48], rax
0x18004879d  mov     [rbp+60h+var_40], eax
0x1800487a0  mov     [rsp+160h+FileHandle], r12
0x1800487a5  mov     [rbp+60h+Handle], r12
0x1800487a9  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x1800487ad  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x1800487b1  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x1800487b5  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm0
0x1800487b9  movups  xmmword ptr [rbp+60h+IoStatusBlock], xmm1
0x1800487bd  movups  xmmword ptr [rbp+60h+RelativeName.RelativeName.Length], xmm0
0x1800487c1  movups  xmmword ptr [rbp+60h+RelativeName.ContainingDirectory], xmm0
0x1800487c5  test    rbx, rbx
0x1800487c8  jz      short loc_1800487E2
0x1800487ca  cmp     dword ptr [rbx], 20h ; ' '
0x1800487cd  jb      loc_180048857
0x1800487d3  mov     eax, [rbx+4]
0x1800487d6  mov     esi, [rbx+0Ch]
0x1800487d9  mov     edi, [rbx+8]
0x1800487dc  mov     [rsp+160h+FileAttributes], eax
0x1800487e0  jmp     short loc_1800487ED
0x1800487e2  mov     esi, r15d
0x1800487e5  mov     [rsp+160h+FileAttributes], r15d
0x1800487ea  mov     edi, r15d
0x1800487ed  test    byte ptr [rbp+60h+arg_28], 3
0x1800487f4  jnz     short loc_18004882A
0x1800487f6  bt      edi, 10h
0x1800487fa  setb    cl
0x1800487fd  mov     [rsp+160h+var_100], cl
0x180048801  bt      edi, 10h
0x180048805  jnb     short loc_180048824
0x180048807  test    edx, edx
0x180048809  jz      short loc_180048811
0x18004880b  test    r8b, 4
0x18004880f  jz      short loc_18004882F
0x180048811  mov     ecx, 0A0h; LastError
0x180048816  call    cs:__imp_RtlSetLastWin32Error
0x18004881c  mov     rax, r12
0x18004881f  jmp     loc_180048EF8
0x180048824  mov     [rsp+160h+var_100], cl
0x180048828  jmp     short loc_18004882F
0x18004882a  mov     [rsp+160h+var_100], r15b
0x18004882f  mov     eax, r9d
0x180048832  mov     r13d, 1
0x180048838  sub     eax, r13d
0x18004883b  jz      short loc_180048878
0x18004883d  sub     eax, r13d
0x180048840  jz      short loc_180048870
0x180048842  sub     eax, r13d
0x180048845  jz      short loc_18004886B
0x180048847  sub     eax, r13d
0x18004884a  jz      short loc_180048863
0x18004884c  cmp     eax, r13d
0x18004884f  jnz     short loc_180048857
0x180048851  bt      edx, 1Eh
0x180048855  jb      short loc_18004886B
0x180048857  mov     ecx, 0C000000Dh
0x18004885c  call    BaseSetLastNTError
0x180048861  jmp     short loc_18004881C
0x180048863  mov     r12d, 3
0x180048869  jmp     short loc_18004887E
0x18004886b  mov     r12d, r13d
0x18004886e  jmp     short loc_18004887E
0x180048870  mov     r12d, 5
0x180048876  jmp     short loc_18004887E
0x180048878  mov     r12d, 2
0x18004887e  mov     rdx, r14; SourceString
0x180048881  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x180048885  call    cs:__imp_RtlInitUnicodeStringEx
0x18004888b  test    eax, eax
0x18004888d  jns     short loc_18004889F
0x18004888f  mov     ecx, eax
0x180048891  call    BaseSetLastNTError
0x180048896  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004889a  jmp     loc_180048EF8
0x18004889f  cmp     [rbp+60h+DestinationString.Length], r13w
0x1800488a4  jbe     short loc_1800488BA
0x1800488a6  movzx   eax, [rbp+60h+DestinationString.Length]
0x1800488aa  shr     rax, 1
0x1800488ad  mov     [rbp+60h+var_C4], r13d
0x1800488b1  cmp     word ptr [r14+rax*2-2], 5Ch ; '\'
0x1800488b8  jz      short loc_1800488BE
0x1800488ba  mov     [rbp+60h+var_C4], r15d
0x1800488be  lea     r9, [rbp+60h+RelativeName]
0x1800488c2  mov     [rsp+160h+CreateOptions], r15d
0x1800488c7  xor     r8d, r8d
0x1800488ca  lea     rdx, [rbp+60h+DestinationString]
0x1800488ce  mov     rcx, r14
0x1800488d1  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x1800488d7  test    eax, eax
0x1800488d9  jns     short loc_1800488F8
0x1800488db  mov     ebx, 0C0000017h
0x1800488e0  cmp     eax, ebx
0x1800488e2  jz      short loc_18004888F
0x1800488e4  cmp     eax, 0C000009Ah
0x1800488e9  jz      short loc_18004888F
0x1800488eb  mov     ecx, 3; LastError
0x1800488f0  call    cs:__imp_RtlSetLastWin32Error
0x1800488f6  jmp     short loc_180048896
0x1800488f8  mov     rax, [rbp+60h+DestinationString.Buffer]
0x1800488fc  mov     [rbp+60h+P], rax
0x180048900  movzx   eax, [rbp+60h+RelativeName.RelativeName.Length]
0x180048904  test    ax, ax
0x180048907  jz      short loc_180048929
0x180048909  mov     [rbp+60h+DestinationString.Length], ax
0x18004890d  mov     eax, dword ptr [rbp+60h+RelativeName.RelativeName.MaximumLength]
0x180048910  mov     dword ptr [rbp+60h+DestinationString.MaximumLength], eax
0x180048913  movzx   eax, word ptr [rbp+60h+RelativeName.RelativeName+6]
0x180048917  mov     word ptr [rbp+60h+DestinationString+6], ax
0x18004891b  mov     rax, [rbp+60h+RelativeName.RelativeName.Buffer]
0x18004891f  mov     [rbp+60h+DestinationString.Buffer], rax
0x180048923  mov     rax, [rbp+60h+RelativeName.ContainingDirectory]
0x180048927  jmp     short loc_180048930
0x180048929  mov     rax, r15
0x18004892c  mov     [rbp+60h+RelativeName.ContainingDirectory], rax
0x180048930  mov     [rbp+60h+ObjectAttributes.RootDirectory], rax
0x180048934  mov     r14d, edi
0x180048937  and     r14d, 1000000h
0x18004893e  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x180048945  mov     eax, r14d
0x180048948  mov     [rbp+60h+var_CC], r14d
0x18004894c  mov     edx, edi
0x18004894e  mov     [rbp+60h+ObjectAttributes.SecurityDescriptor], r15
0x180048952  shr     edx, 6
0x180048955  and     edx, 800h
0x18004895b  neg     eax
0x18004895d  lea     rax, [rbp+60h+DestinationString]
0x180048961  sbb     ecx, ecx
0x180048963  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x180048967  not     ecx
0x180048969  and     ecx, 40h
0x18004896c  or      ecx, edx
0x18004896e  mov     [rbp+60h+ObjectAttributes.Attributes], ecx
0x180048971  bt      esi, 14h
0x180048975  jnb     short loc_1800489AE
0x180048977  and     esi, 0F0000h
0x18004897d  bt      esi, 12h
0x180048981  mov     ecx, esi
0x180048983  setb    byte ptr [rbp+60h+var_40]
0x180048987  btr     ecx, 12h
0x18004898b  bt      esi, 12h
0x18004898f  cmovnb  ecx, esi
0x180048992  bt      ecx, 13h
0x180048996  jnb     short loc_1800489A2
0x180048998  mov     byte ptr [rbp+60h+var_40+1], r13b
0x18004899c  btr     ecx, 13h
0x1800489a0  jmp     short loc_1800489A6
0x1800489a2  mov     byte ptr [rbp+60h+var_40+1], r15b
0x1800489a6  shr     ecx, 10h
0x1800489a9  mov     dword ptr [rbp+60h+var_48+4], ecx
0x1800489ac  jmp     short loc_1800489BB
0x1800489ae  mov     word ptr [rbp+60h+var_40], 101h
0x1800489b4  mov     dword ptr [rbp+60h+var_48+4], 2
0x1800489bb  mov     dword ptr [rbp+60h+var_48], 0Ch
0x1800489c2  lea     rax, [rbp+60h+var_48]
0x1800489c6  mov     [rbp+60h+ObjectAttributes.SecurityQualityOfService], rax
0x1800489ca  test    rbx, rbx
0x1800489cd  jz      short loc_180048A00
0x1800489cf  mov     rcx, [rbx+10h]
0x1800489d3  test    rcx, rcx
0x1800489d6  jz      short loc_180048A00
0x1800489d8  mov     rax, [rcx+8]
0x1800489dc  mov     [rbp+60h+ObjectAttributes.SecurityDescriptor], rax
0x1800489e0  cmp     [rcx+10h], r15d
0x1800489e4  jz      short loc_180048A00
0x1800489e6  mov     eax, r14d
0x1800489e9  mov     rsi, r15
0x1800489ec  neg     eax
0x1800489ee  mov     r13d, r15d
0x1800489f1  sbb     ecx, ecx
0x1800489f3  and     ecx, 0FFFFFFC0h
0x1800489f6  add     ecx, 42h ; 'B'
0x1800489f9  or      ecx, edx
0x1800489fb  mov     [rbp+60h+ObjectAttributes.Attributes], ecx
0x1800489fe  jmp     short loc_180048A0B
0x180048a00  mov     rsi, r15
0x180048a03  mov     r13d, r15d
0x180048a06  test    rbx, rbx
0x180048a09  jz      short loc_180048A4A
0x180048a0b  mov     rcx, [rbx+18h]; FileHandle
0x180048a0f  lea     rax, [rcx-1]
0x180048a13  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180048a17  ja      short loc_180048A4A
0x180048a19  mov     r9d, 4; Length
0x180048a1f  mov     [rsp+160h+FileInformationClass], 7; FileInformationClass
0x180048a27  lea     r8, [rbp+60h+FileInformation]; FileInformation
0x180048a2b  lea     rdx, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x180048a2f  call    cs:__imp_NtQueryInformationFile
0x180048a35  test    eax, eax
0x180048a37  js      short loc_180048A4A
0x180048a39  mov     r14d, [rbp+60h+FileInformation]
0x180048a3d  test    r14d, r14d
0x180048a40  jnz     loc_180048B49
0x180048a46  mov     r14d, [rbp+60h+var_CC]
0x180048a4a  call    Feature_TimestampsOnCreate__private_IsEnabledDeviceUsageNoInline
0x180048a4f  mov     r8d, [rsp+160h+CreateOptions]
0x180048a54  test    eax, eax
0x180048a56  jz      short loc_180048A65
0x180048a58  mov     eax, edi
0x180048a5a  and     eax, 8000h
0x180048a5f  shl     eax, 0Eh
0x180048a62  or      r8d, eax
0x180048a65  mov     ecx, 10000000h
0x180048a6a  mov     eax, edi
0x180048a6c  and     eax, 8000000h
0x180048a71  mov     edx, edi
0x180048a73  shr     edx, 1
0x180048a75  mov     r10d, 40000h
0x180048a7b  and     edx, ecx
0x180048a7d  mov     r9d, edi
0x180048a80  or      edx, eax
0x180048a82  and     r9d, 2000000h
0x180048a89  shr     edx, 8
0x180048a8c  mov     eax, edi
0x180048a8e  and     eax, ecx
0x180048a90  or      edx, eax
0x180048a92  mov     eax, edi
0x180048a94  and     eax, 800000h
0x180048a99  shr     edx, 0Ch
0x180048a9c  or      edx, eax
0x180048a9e  mov     eax, edi
0x180048aa0  and     eax, r10d
0x180048aa3  shr     edx, 3
0x180048aa6  or      edx, eax
0x180048aa8  mov     eax, edi
0x180048aaa  sar     eax, 1Fh
0x180048aad  and     eax, 2
0x180048ab0  shr     edx, 2
0x180048ab3  or      edx, eax
0x180048ab5  mov     eax, edi
0x180048ab7  shr     eax, 19h
0x180048aba  not     eax
0x180048abc  and     eax, 20h
0x180048abf  or      edx, eax
0x180048ac1  mov     eax, r9d
0x180048ac4  neg     eax
0x180048ac6  sbb     ecx, ecx
0x180048ac8  and     ecx, 4000h
0x180048ace  or      edx, ecx
0x180048ad0  mov     ecx, 800h
0x180048ad5  or      r8d, edx
0x180048ad8  mov     [rsp+160h+CreateOptions], r8d
0x180048add  mov     rax, gs:30h
0x180048ae6  test    [rax+17EEh], cx
0x180048aed  jz      short loc_180048AF7
0x180048aef  or      r8d, r10d
0x180048af2  mov     [rsp+160h+CreateOptions], r8d
0x180048af7  mov     r15d, edi
0x180048afa  and     r15d, 4000000h
0x180048b01  jz      short loc_180048B13
0x180048b03  bts     r8d, 0Ch
0x180048b08  bts     [rsp+160h+var_E8], 10h
0x180048b0e  mov     [rsp+160h+CreateOptions], r8d
0x180048b13  mov     eax, 200000h
0x180048b18  test    eax, edi
0x180048b1a  jz      short loc_180048B24
0x180048b1c  or      r8d, eax
0x180048b1f  mov     [rsp+160h+CreateOptions], r8d
0x180048b24  bt      edi, 14h
0x180048b28  jnb     short loc_180048B34
0x180048b2a  bts     r8d, 16h
0x180048b2f  mov     [rsp+160h+CreateOptions], r8d
0x180048b34  test    r9d, r9d
0x180048b37  jnz     loc_180048BFE
0x180048b3d  or      r8d, 40h
0x180048b41  jmp     loc_180048C15
0x180048b46  xor     r15d, r15d
0x180048b49  mov     rcx, gs:60h
0x180048b52  add     r14d, r14d
0x180048b55  mov     edx, cs:KernelBaseGlobalData; Flags
0x180048b5b  mov     r8d, r14d; Size
0x180048b5e  mov     rcx, [rcx+30h]; HeapHandle
0x180048b62  call    cs:__imp_RtlAllocateHeap
0x180048b68  mov     rsi, rax
0x180048b6b  test    rax, rax
  ... truncated ...
```
